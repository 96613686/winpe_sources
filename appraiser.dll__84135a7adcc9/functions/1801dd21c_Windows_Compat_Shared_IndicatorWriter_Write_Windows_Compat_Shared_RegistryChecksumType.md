# Windows::Compat::Shared::IndicatorWriter::Write(Windows::Compat::Shared::RegistryChecksumType)

- ea: `0x1801dd21c`
- end: `0x1801dd417`
- name: `?Write@IndicatorWriter@Shared@Compat@Windows@@QEAAJW4RegistryChecksumType@234@@Z`
- size: `507`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800df914`
- `0x1800e09dc`

## callees

- `0x180008570`
- `0x180011d94`
- `0x1801dcfd0`
- `0x1801dd21c`
- `0x1801de8fc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1801dd3c4`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1801dd3c4`
- `ntdll!RtlTimeToSecondsSince1970` at `0x1801dd274`
- `ntdll!RtlTimeToSecondsSince1970` at `0x1801dd274`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1801dd25e`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1801dd25e`
- `KERNEL32!GetLastError` at `0x1801dd3db`
- `KERNEL32!GetLastError` at `0x1801dd3db`
- `ADVAPI32!RegSetValueExW` at `0x1801dd2e8`
- `ADVAPI32!RegSetValueExW` at `0x1801dd342`
- `ADVAPI32!RegSetValueExW` at `0x1801dd3a4`
- `ADVAPI32!RegSetValueExW` at `0x1801dd2e8`
- `ADVAPI32!RegSetValueExW` at `0x1801dd342`
- `ADVAPI32!RegSetValueExW` at `0x1801dd3a4`
- `ktmw32!CommitTransaction` at `0x1801dd3d1`
- `ktmw32!CommitTransaction` at `0x1801dd3d1`

## pseudocode

```c
__int64 __fastcall Windows::Compat::Shared::IndicatorWriter::Write(HKEY *a1)
{
  struct _FILETIME v2; // rbx
  signed int v3; // edi
  __int64 v4; // rax
  LSTATUS v5; // eax
  HKEY v6; // rcx
  LSTATUS v7; // eax
  int v8; // eax
  BYTE *v9; // rbx
  LSTATUS v10; // eax
  signed int LastError; // eax
  ULONG ElapsedSeconds; // [rsp+30h] [rbp-29h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+38h] [rbp-21h] BYREF
  BYTE lpData[8]; // [rsp+40h] [rbp-19h] BYREF
  union _LARGE_INTEGER Time; // [rsp+48h] [rbp-11h] BYREF
  unsigned __int16 Data[24]; // [rsp+50h] [rbp-9h] BYREF

  Time.QuadPart = 0;
  ElapsedSeconds = 0;
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v2 = SystemTimeAsFileTime;
  Time = (union _LARGE_INTEGER)SystemTimeAsFileTime;
  if ( RtlTimeToSecondsSince1970(&Time, &ElapsedSeconds) )
  {
    v3 = StringCchPrintfW(Data, 0x15u, L"%u", ElapsedSeconds);
    if ( v3 >= 0 )
    {
      v4 = -1;
      do
        ++v4;
      while ( Data[v4] );
      v5 = RegSetValueExW(a1[2], L"TimestampEpochString", 0, 1u, (const BYTE *)Data, 2 * v4 + 2);
      v3 = v5;
      if ( v5 > 0 )
        v3 = (unsigned __int16)v5 | 0x80070000;
      if ( v3 >= 0 )
      {
        v3 = Windows::Compat::Shared::IndicatorWriter::SendFinalTelemetry((Windows::Compat::Shared::IndicatorWriter *)a1);
        if ( v3 >= 0 )
        {
          v6 = a1[2];
          *(struct _FILETIME *)lpData = v2;
          v7 = RegSetValueExW(v6, L"Timestamp", 0, 0xBu, lpData, 8u);
          v3 = v7;
          if ( v7 > 0 )
            v3 = (unsigned __int16)v7 | 0x80070000;
          if ( v3 >= 0 )
          {
            *(_QWORD *)lpData = 0;
            SystemTimeAsFileTime.dwLowDateTime = 0;
            v8 = Windows::Compat::Shared::RegistryChecksum::CalculateRegistryChecksumAlloc(
                   lpData,
                   &SystemTimeAsFileTime,
                   a1 + 2,
                   3);
            v9 = *(BYTE **)lpData;
            v3 = v8;
            if ( v8 >= 0 )
            {
              v10 = RegSetValueExW(
                      a1[3],
                      L"checksum",
                      0,
                      3u,
                      *(const BYTE **)lpData,
                      SystemTimeAsFileTime.dwLowDateTime);
              v3 = v10;
              if ( v10 > 0 )
                v3 = (unsigned __int16)v10 | 0x80070000;
              if ( v3 >= 0 )
                v3 = 0;
            }
            if ( v9 )
              free(v9);
            if ( v3 >= 0 && !CommitTransaction(*a1) )
            {
              LastError = GetLastError();
              v3 = LastError;
              if ( LastError > 0 )
                return (unsigned __int16)LastError | 0x80070000;
            }
          }
        }
      }
    }
  }
  else
  {
    return (unsigned int)-2147467259;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1801dd21c  mov     [rsp-8+arg_8], rbx
0x1801dd221  mov     [rsp-8+arg_10], rsi
0x1801dd226  push    rbp
0x1801dd227  push    rdi
0x1801dd228  push    r12
0x1801dd22a  push    r14
0x1801dd22c  push    r15
0x1801dd22e  lea     rbp, [rsp-37h]
0x1801dd233  sub     rsp, 90h
0x1801dd23a  mov     rax, cs:__security_cookie
0x1801dd241  xor     rax, rsp
0x1801dd244  mov     [rbp+57h+var_30], rax
0x1801dd248  xor     r15d, r15d
0x1801dd24b  mov     rsi, rcx
0x1801dd24e  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1801dd252  mov     qword ptr [rbp+57h+Time], r15
0x1801dd256  mov     [rbp+57h+ElapsedSeconds], r15d
0x1801dd25a  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], r15
0x1801dd25e  call    cs:__imp_GetSystemTimeAsFileTime
0x1801dd264  mov     rbx, qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime]
0x1801dd268  lea     rdx, [rbp+57h+ElapsedSeconds]; ElapsedSeconds
0x1801dd26c  lea     rcx, [rbp+57h+Time]; Time
0x1801dd270  mov     qword ptr [rbp+57h+Time], rbx
0x1801dd274  call    cs:__imp_RtlTimeToSecondsSince1970
0x1801dd27a  test    al, al
0x1801dd27c  jnz     short loc_1801DD288
0x1801dd27e  mov     edi, 80004005h
0x1801dd283  jmp     loc_1801DD3ED
0x1801dd288  mov     r9d, [rbp+57h+ElapsedSeconds]
0x1801dd28c  lea     r8, aU_0; "%u"
0x1801dd293  mov     edx, 15h; unsigned __int64
0x1801dd298  lea     rcx, [rbp+57h+Data]; unsigned __int16 *
0x1801dd29c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1801dd2a1  mov     edi, eax
0x1801dd2a3  test    eax, eax
0x1801dd2a5  js      loc_1801DD3ED
0x1801dd2ab  lea     rcx, [rbp+57h+Data]
0x1801dd2af  or      rax, 0FFFFFFFFFFFFFFFFh
0x1801dd2b3  inc     rax
0x1801dd2b6  cmp     [rcx+rax*2], r15w
0x1801dd2bb  jnz     short loc_1801DD2B3
0x1801dd2bd  lea     eax, ds:2[rax*2]
0x1801dd2c4  mov     r9d, 1; dwType
0x1801dd2ca  mov     [rsp+0B0h+cbData], eax; cbData
0x1801dd2ce  lea     r14, [rsi+10h]
0x1801dd2d2  mov     rcx, [r14]; hKey
0x1801dd2d5  lea     rax, [rbp+57h+Data]
0x1801dd2d9  xor     r8d, r8d; Reserved
0x1801dd2dc  mov     [rsp+0B0h+lpData], rax; lpData
0x1801dd2e1  lea     rdx, aTimestampepoch; "TimestampEpochString"
0x1801dd2e8  call    cs:__imp_RegSetValueExW
0x1801dd2ee  mov     edi, eax
0x1801dd2f0  mov     r12d, 80070000h
0x1801dd2f6  test    eax, eax
0x1801dd2f8  jle     short loc_1801DD300
0x1801dd2fa  movzx   edi, ax
0x1801dd2fd  or      edi, r12d
0x1801dd300  test    edi, edi
0x1801dd302  js      loc_1801DD3ED
0x1801dd308  mov     rcx, rsi; this
0x1801dd30b  call    ?SendFinalTelemetry@IndicatorWriter@Shared@Compat@Windows@@AEAAJXZ; Windows::Compat::Shared::IndicatorWriter::SendFinalTelemetry(void)
0x1801dd310  mov     edi, eax
0x1801dd312  test    eax, eax
0x1801dd314  js      loc_1801DD3ED
0x1801dd31a  mov     rcx, [r14]; hKey
0x1801dd31d  lea     rax, [rbp+57h+var_70]
0x1801dd321  mov     [rsp+0B0h+cbData], 8; cbData
0x1801dd329  lea     rdx, aTimestamp_0; "Timestamp"
0x1801dd330  mov     r9d, 0Bh; dwType
0x1801dd336  mov     [rsp+0B0h+lpData], rax; lpData
0x1801dd33b  xor     r8d, r8d; Reserved
0x1801dd33e  mov     qword ptr [rbp+57h+var_70], rbx
0x1801dd342  call    cs:__imp_RegSetValueExW
0x1801dd348  mov     edi, eax
0x1801dd34a  test    eax, eax
0x1801dd34c  jle     short loc_1801DD354
0x1801dd34e  movzx   edi, ax
0x1801dd351  or      edi, r12d
0x1801dd354  test    edi, edi
0x1801dd356  js      loc_1801DD3ED
0x1801dd35c  mov     r9d, 3
0x1801dd362  mov     qword ptr [rbp+57h+var_70], r15
0x1801dd366  mov     r8, r14
0x1801dd369  mov     [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], r15d
0x1801dd36d  lea     rdx, [rbp+57h+SystemTimeAsFileTime]
0x1801dd371  lea     rcx, [rbp+57h+var_70]
0x1801dd375  call    ?CalculateRegistryChecksumAlloc@RegistryChecksum@Shared@Compat@Windows@@CAJPEAPEAEPEAKPEAVRegistryKey@234@W4RegistryChecksumType@234@@Z; Windows::Compat::Shared::RegistryChecksum::CalculateRegistryChecksumAlloc(uchar * *,ulong *,Windows::Compat::Shared::RegistryKey *,Windows::Compat::Shared::RegistryChecksumType)
0x1801dd37a  mov     rbx, qword ptr [rbp+57h+var_70]
0x1801dd37e  mov     edi, eax
0x1801dd380  test    eax, eax
0x1801dd382  js      short loc_1801DD3BC
0x1801dd384  mov     eax, [rbp+57h+SystemTimeAsFileTime.dwLowDateTime]
0x1801dd387  lea     rdx, aChecksum; "checksum"
0x1801dd38e  mov     rcx, [rsi+18h]; hKey
0x1801dd392  mov     r9d, 3; dwType
0x1801dd398  mov     [rsp+0B0h+cbData], eax; cbData
0x1801dd39c  xor     r8d, r8d; Reserved
0x1801dd39f  mov     [rsp+0B0h+lpData], rbx; lpData
0x1801dd3a4  call    cs:__imp_RegSetValueExW
0x1801dd3aa  mov     edi, eax
0x1801dd3ac  test    eax, eax
0x1801dd3ae  jle     short loc_1801DD3B6
0x1801dd3b0  movzx   edi, ax
0x1801dd3b3  or      edi, r12d
0x1801dd3b6  test    edi, edi
0x1801dd3b8  cmovns  edi, r15d
0x1801dd3bc  test    rbx, rbx
0x1801dd3bf  jz      short loc_1801DD3CA
0x1801dd3c1  mov     rcx, rbx; Block
0x1801dd3c4  call    cs:__imp_free
0x1801dd3ca  test    edi, edi
0x1801dd3cc  js      short loc_1801DD3ED
0x1801dd3ce  mov     rcx, [rsi]; TransactionHandle
0x1801dd3d1  call    cs:__imp_CommitTransaction
0x1801dd3d7  test    eax, eax
0x1801dd3d9  jnz     short loc_1801DD3ED
0x1801dd3db  call    cs:__imp_GetLastError
0x1801dd3e1  mov     edi, eax
0x1801dd3e3  test    eax, eax
0x1801dd3e5  jle     short loc_1801DD3ED
0x1801dd3e7  movzx   edi, ax
0x1801dd3ea  or      edi, r12d
0x1801dd3ed  mov     eax, edi
0x1801dd3ef  mov     rcx, [rbp+57h+var_30]
0x1801dd3f3  xor     rcx, rsp; StackCookie
0x1801dd3f6  call    __security_check_cookie
0x1801dd3fb  lea     r11, [rsp+0B0h+var_20]
0x1801dd403  mov     rbx, [r11+38h]
0x1801dd407  mov     rsi, [r11+40h]
0x1801dd40b  mov     rsp, r11
0x1801dd40e  pop     r15
0x1801dd410  pop     r14
0x1801dd412  pop     r12
0x1801dd414  pop     rdi
0x1801dd415  pop     rbp
0x1801dd416  retn
```
