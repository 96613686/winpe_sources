# GetOrigSetupData

- ea: `0x1400821e4`
- end: `0x140082496`
- name: `GetOrigSetupData`
- size: `690`
- prototype: `__int64 __fastcall(DWORD cbData, __int64)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x14004c1a4`
- `0x14004d358`

## callees

- `0x140002c73`
- `0x140004be4`
- `0x140004c78`
- `0x140004ca8`
- `0x14006af2c`
- `0x140073d5c`
- `0x140074cb4`
- `0x140074f18`
- `0x1400821e4`
- `0x140086ec0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14008240a`
- `ADVAPI32!RegCloseKey` at `0x14008240a`
- `ADVAPI32!RegDeleteKeyExW` at `0x140082429`
- `ADVAPI32!RegDeleteKeyExW` at `0x140082429`
- `KERNEL32!GetLastError` at `0x140082338`
- `KERNEL32!GetLastError` at `0x140082338`
- `KERNEL32!SetLastError` at `0x1400822c1`
- `KERNEL32!SetLastError` at `0x1400822c1`

## pseudocode

```c
__int64 __fastcall GetOrigSetupData(DWORD cbData, __int64 a2)
{
  int v4; // eax
  DWORD v5; // ebx
  int v7; // edi
  HKEY v8; // rbx
  DWORD LastError; // eax
  int RegistryDwordDefault; // eax
  int v11; // eax
  unsigned int v12; // eax
  DWORD cbDataa; // [rsp+20h] [rbp-248h]
  DWORD cbDatab; // [rsp+20h] [rbp-248h]
  BYTE Data[16]; // [rsp+30h] [rbp-238h] BYREF
  WCHAR SubKey[256]; // [rsp+40h] [rbp-228h] BYREF

  memset_0(SubKey, 0, sizeof(SubKey));
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids);
  }
  v4 = StringCchPrintfW(SubKey, 0x100u, L"%s\\%010d", L"Software\\Microsoft\\Fax\\Setup\\Original Setup Data", cbData);
  v5 = v4;
  if ( v4 < 0 )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        37,
        &WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids,
        (unsigned int)v4);
    }
    if ( (v5 & 0x1FFF0000) == 0x70000 )
      v5 = (unsigned __int16)v5;
    SetLastError(v5);
    return 0;
  }
  v7 = 1;
  v8 = (HKEY)OpenRegistryKey(-2147483646, SubKey, 0, 131097);
  if ( !v8 )
  {
    v7 = 0;
    v8 = (HKEY)OpenRegistryKey(-2147483646, L"Software\\Microsoft\\Fax\\Setup\\Original Setup Data", 0, 131097);
    if ( !v8 )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        LastError = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, &WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids, LastError);
      }
      return 0;
    }
  }
  *(_QWORD *)(a2 + 16) = StringDup((unsigned __int16 *)&Class);
  *(_QWORD *)a2 = GetRegistryStringValue(v8, 1u, L"CSID", L"Fax", cbDataa);
  *(_QWORD *)(a2 + 8) = GetRegistryStringValue(v8, 1u, L"TSID", L"Fax", cbDatab);
  *(_DWORD *)Data = 0;
  RegistryDwordDefault = GetRegistryDwordDefault(v8, L"Rings", Data);
  *(_DWORD *)(a2 + 24) = RegistryDwordDefault != 0 ? *(_DWORD *)Data : 0;
  *(_DWORD *)Data = 0;
  v11 = GetRegistryDwordDefault(v8, L"Flags", Data);
  *(_DWORD *)(a2 + 28) = v11 != 0 ? *(_DWORD *)Data : 0;
  RegCloseKey(v8);
  if ( v7 == 1 )
  {
    v12 = RegDeleteKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0);
    if ( v12 )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, &WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids, v12);
      }
    }
  }
  return 1;
}

```

## disassembly

```asm
0x1400821e4  mov     [rsp+arg_10], rbx
0x1400821e9  mov     [rsp+arg_18], rsi
0x1400821ee  push    rdi
0x1400821ef  push    r12
0x1400821f1  push    r14
0x1400821f3  sub     rsp, 250h
0x1400821fa  mov     rax, cs:__security_cookie
0x140082201  xor     rax, rsp
0x140082204  mov     [rsp+268h+var_28], rax
0x14008220c  mov     rsi, rdx
0x14008220f  mov     ebx, ecx
0x140082211  xor     edx, edx; Val
0x140082213  lea     rcx, [rsp+268h+SubKey]; void *
0x140082218  mov     r8d, 200h; Size
0x14008221e  call    memset_0
0x140082223  mov     rcx, cs:WPP_GLOBAL_Control
0x14008222a  lea     r14, WPP_GLOBAL_Control
0x140082231  cmp     rcx, r14
0x140082234  jz      short loc_140082257
0x140082236  test    byte ptr [rcx+1Ch], 2
0x14008223a  jz      short loc_140082257
0x14008223c  cmp     byte ptr [rcx+19h], 5
0x140082240  jb      short loc_140082257
0x140082242  mov     rcx, [rcx+10h]
0x140082246  lea     r8, WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids
0x14008224d  mov     edx, 24h ; '$'
0x140082252  call    WPP_SF_
0x140082257  lea     r9, aSoftwareMicros_6; "Software\\Microsoft\\Fax\\Setup\\Origin"...
0x14008225e  mov     [rsp+268h+cbData], ebx; cbData
0x140082262  lea     r8, aS010d; "%s\\%010d"
0x140082269  mov     edx, 100h; unsigned __int64
0x14008226e  lea     rcx, [rsp+268h+SubKey]; unsigned __int16 *
0x140082273  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140082278  mov     ebx, eax
0x14008227a  test    eax, eax
0x14008227c  jns     short loc_1400822D4
0x14008227e  mov     rcx, cs:WPP_GLOBAL_Control
0x140082285  cmp     rcx, r14
0x140082288  jz      short loc_1400822AE
0x14008228a  test    byte ptr [rcx+1Ch], 2
0x14008228e  jz      short loc_1400822AE
0x140082290  cmp     byte ptr [rcx+19h], 2
0x140082294  jb      short loc_1400822AE
0x140082296  mov     rcx, [rcx+10h]
0x14008229a  lea     r8, WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids
0x1400822a1  mov     edx, 25h ; '%'
0x1400822a6  mov     r9d, eax
0x1400822a9  call    WPP_SF_d
0x1400822ae  mov     eax, ebx
0x1400822b0  and     eax, 1FFF0000h
0x1400822b5  cmp     eax, 70000h
0x1400822ba  jnz     short loc_1400822BF
0x1400822bc  movzx   ebx, bx
0x1400822bf  mov     ecx, ebx; dwErrCode
0x1400822c1  call    cs:__imp_SetLastError
0x1400822c8  nop     dword ptr [rax+rax+00h]
0x1400822cd  xor     eax, eax
0x1400822cf  jmp     loc_14008246C
0x1400822d4  mov     r12, 0FFFFFFFF80000002h
0x1400822db  lea     rdx, [rsp+268h+SubKey]
0x1400822e0  mov     rcx, r12
0x1400822e3  mov     r9d, 20019h
0x1400822e9  xor     r8d, r8d
0x1400822ec  mov     edi, 1
0x1400822f1  call    OpenRegistryKey
0x1400822f6  mov     rbx, rax
0x1400822f9  test    rax, rax
0x1400822fc  jnz     short loc_140082366
0x1400822fe  mov     r9d, 20019h
0x140082304  lea     rdx, aSoftwareMicros_6; "Software\\Microsoft\\Fax\\Setup\\Origin"...
0x14008230b  xor     r8d, r8d
0x14008230e  mov     rcx, r12
0x140082311  xor     edi, edi
0x140082313  call    OpenRegistryKey
0x140082318  mov     rbx, rax
0x14008231b  test    rax, rax
0x14008231e  jnz     short loc_140082366
0x140082320  mov     rax, cs:WPP_GLOBAL_Control
0x140082327  cmp     rax, r14
0x14008232a  jz      short loc_1400822CD
0x14008232c  test    byte ptr [rax+1Ch], 2
0x140082330  jz      short loc_1400822CD
0x140082332  cmp     byte ptr [rax+19h], 2
0x140082336  jb      short loc_1400822CD
0x140082338  call    cs:__imp_GetLastError
0x14008233f  nop     dword ptr [rax+rax+00h]
0x140082344  mov     rcx, cs:WPP_GLOBAL_Control
0x14008234b  lea     edx, [rdi+26h]
0x14008234e  mov     r9d, eax
0x140082351  lea     r8, WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids
0x140082358  mov     rcx, [rcx+10h]
0x14008235c  call    WPP_SF_d
0x140082361  jmp     loc_1400822CD
0x140082366  lea     rcx, Class; unsigned __int16 *
0x14008236d  call    StringDup
0x140082372  lea     r9, SubsystemName; "Fax"
0x140082379  mov     [rsi+10h], rax
0x14008237d  lea     r8, aCsid; "CSID"
0x140082384  mov     edx, 1; dwType
0x140082389  mov     rcx, rbx; hKey
0x14008238c  call    ?GetRegistryStringValue@@YAPEAGPEAUHKEY__@@KPEBG1PEAK@Z; GetRegistryStringValue(HKEY__ *,ulong,ushort const *,ushort const *,ulong *)
0x140082391  lea     r9, SubsystemName; "Fax"
0x140082398  mov     [rsi], rax
0x14008239b  lea     r8, aTsid; "TSID"
0x1400823a2  mov     edx, 1; dwType
0x1400823a7  mov     rcx, rbx; hKey
0x1400823aa  call    ?GetRegistryStringValue@@YAPEAGPEAUHKEY__@@KPEBG1PEAK@Z; GetRegistryStringValue(HKEY__ *,ulong,ushort const *,ushort const *,ulong *)
0x1400823af  xor     r9d, r9d
0x1400823b2  mov     [rsi+8], rax
0x1400823b6  lea     r8, [rsp+268h+Data]; lpData
0x1400823bb  mov     dword ptr [rsp+268h+Data], 0
0x1400823c3  lea     rdx, aRings; "Rings"
0x1400823ca  mov     rcx, rbx; hKey
0x1400823cd  call    GetRegistryDwordDefault
0x1400823d2  neg     eax
0x1400823d4  lea     r8, [rsp+268h+Data]; lpData
0x1400823d9  lea     rdx, aFlags; "Flags"
0x1400823e0  sbb     ecx, ecx
0x1400823e2  xor     r9d, r9d
0x1400823e5  and     ecx, dword ptr [rsp+268h+Data]
0x1400823e9  mov     [rsi+18h], ecx
0x1400823ec  mov     rcx, rbx; hKey
0x1400823ef  mov     dword ptr [rsp+268h+Data], 0
0x1400823f7  call    GetRegistryDwordDefault
0x1400823fc  neg     eax
0x1400823fe  mov     rcx, rbx; hKey
0x140082401  sbb     edx, edx
0x140082403  and     edx, dword ptr [rsp+268h+Data]
0x140082407  mov     [rsi+1Ch], edx
0x14008240a  call    cs:__imp_RegCloseKey
0x140082411  nop     dword ptr [rax+rax+00h]
0x140082416  cmp     edi, 1
0x140082419  jnz     short loc_140082467
0x14008241b  xor     r9d, r9d; Reserved
0x14008241e  lea     rdx, [rsp+268h+SubKey]; lpSubKey
0x140082423  xor     r8d, r8d; samDesired
0x140082426  mov     rcx, r12; hKey
0x140082429  call    cs:__imp_RegDeleteKeyExW
0x140082430  nop     dword ptr [rax+rax+00h]
0x140082435  test    eax, eax
0x140082437  jz      short loc_140082467
0x140082439  mov     rcx, cs:WPP_GLOBAL_Control
0x140082440  cmp     rcx, r14
0x140082443  jz      short loc_140082467
0x140082445  test    byte ptr [rcx+1Ch], 2
0x140082449  jz      short loc_140082467
0x14008244b  cmp     byte ptr [rcx+19h], 2
0x14008244f  jb      short loc_140082467
0x140082451  mov     rcx, [rcx+10h]
0x140082455  lea     edx, [rdi+26h]
0x140082458  mov     r9d, eax
0x14008245b  lea     r8, WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids
0x140082462  call    WPP_SF_d
0x140082467  mov     eax, 1
0x14008246c  mov     rcx, [rsp+268h+var_28]
0x140082474  xor     rcx, rsp; StackCookie
0x140082477  call    __security_check_cookie
0x14008247c  lea     r11, [rsp+268h+var_18]
0x140082484  mov     rbx, [r11+30h]
0x140082488  mov     rsi, [r11+38h]
0x14008248c  mov     rsp, r11
0x14008248f  pop     r14
0x140082491  pop     r12
0x140082493  pop     rdi
0x140082494  retn
```
