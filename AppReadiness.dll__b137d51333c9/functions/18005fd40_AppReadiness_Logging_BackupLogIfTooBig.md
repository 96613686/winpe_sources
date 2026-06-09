# AppReadiness::Logging::_BackupLogIfTooBig

- ea: `0x18005fd40`
- end: `0x18005fe83`
- name: `AppReadiness::Logging::_BackupLogIfTooBig`
- size: `323`
- prototype: `int __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18005fb48`

## callees

- `0x180009d80`
- `0x180038f14`
- `0x18003e210`
- `0x18005f9c0`
- `0x18005fd40`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18005fde5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18005fde5`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x18005fe59`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x18005fe59`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x18005fd9e`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x18005fd9e`

## string_xrefs

- `0x18005fe26`: `AppReadiness-%04d%02d%02d-%02d%02d%02d.etl`

## pseudocode

```c
int __fastcall AppReadiness::Logging::_BackupLogIfTooBig(_DWORD *a1)
{
  const WCHAR *v2; // rdi
  unsigned __int64 v3; // rax
  int v4; // ecx
  unsigned __int16 *v5; // r8
  unsigned __int64 v6; // r9
  int wMonth; // [rsp+20h] [rbp-E0h]
  int wDay; // [rsp+28h] [rbp-D8h]
  int wHour; // [rsp+30h] [rbp-D0h]
  int wMinute; // [rsp+38h] [rbp-C8h]
  int wSecond; // [rsp+40h] [rbp-C0h]
  struct _SYSTEMTIME SystemTime; // [rsp+50h] [rbp-B0h] BYREF
  __int128 FileInformation; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v15; // [rsp+70h] [rbp-90h]
  unsigned int v16; // [rsp+80h] [rbp-80h]
  WCHAR pszMore[264]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR NewFileName[264]; // [rsp+2A0h] [rbp+1A0h] BYREF

  if ( (a1[16] & 0x2000) != 0 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  v2 = (const WCHAR *)((char *)a1 + (unsigned int)a1[28]);
  v16 = 0;
  FileInformation = 0;
  v15 = 0;
  LODWORD(v3) = GetFileAttributesExW(v2, GetFileExInfoStandard, &FileInformation);
  if ( (_DWORD)v3 )
  {
    v4 = a1[15];
    *(_QWORD *)&SystemTime.wYear = __PAIR64__(HIDWORD(v15), v16);
    v3 = (v4 << 23) / 0xAu;
    if ( __PAIR64__(HIDWORD(v15), v16) > v3 )
    {
      SystemTime = 0;
      GetSystemTime(&SystemTime);
      wSecond = SystemTime.wSecond;
      wMinute = SystemTime.wMinute;
      wHour = SystemTime.wHour;
      wDay = SystemTime.wDay;
      wMonth = SystemTime.wMonth;
      LODWORD(v3) = StringCchPrintfW(
                      pszMore,
                      0x104u,
                      L"AppReadiness-%04d%02d%02d-%02d%02d%02d.etl",
                      SystemTime.wYear,
                      wMonth,
                      wDay,
                      wHour,
                      wMinute,
                      wSecond);
      if ( (v3 & 0x80000000) == 0LL )
      {
        LODWORD(v3) = AppReadiness::Logging::ComputeLogfilePath(pszMore, NewFileName, v5, v6);
        if ( (v3 & 0x80000000) == 0LL )
          LODWORD(v3) = MoveFileW(v2, NewFileName);
      }
    }
  }
  return v3;
}

```

## disassembly

```asm
0x18005fd40  mov     [rsp-8+arg_8], rbx
0x18005fd45  mov     [rsp-8+arg_10], rdi
0x18005fd4a  push    rbp
0x18005fd4b  lea     rbp, [rsp-3C0h]
0x18005fd53  sub     rsp, 4C0h
0x18005fd5a  mov     rax, cs:__security_cookie
0x18005fd61  xor     rax, rsp
0x18005fd64  mov     [rbp+3C0h+var_10], rax
0x18005fd6b  test    dword ptr [rcx+40h], 2000h
0x18005fd72  mov     rbx, rcx
0x18005fd75  jz      short loc_18005FD7C
0x18005fd77  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18005fd7c  mov     edi, [rbx+70h]
0x18005fd7f  lea     r8, [rsp+4C0h+FileInformation]; lpFileInformation
0x18005fd84  xorps   xmm0, xmm0
0x18005fd87  xor     eax, eax
0x18005fd89  add     rdi, rbx
0x18005fd8c  mov     [rbp+3C0h+var_440], eax
0x18005fd8f  mov     rcx, rdi; lpFileName
0x18005fd92  xor     edx, edx; fInfoLevelId
0x18005fd94  movups  [rsp+4C0h+FileInformation], xmm0
0x18005fd99  movups  [rsp+4C0h+var_450], xmm0
0x18005fd9e  call    cs:__imp_GetFileAttributesExW
0x18005fda4  test    eax, eax
0x18005fda6  jz      loc_18005FE5F
0x18005fdac  mov     eax, [rbp+3C0h+var_440]
0x18005fdaf  mov     ecx, [rbx+3Ch]
0x18005fdb2  mov     dword ptr [rsp+4C0h+SystemTime.wYear], eax
0x18005fdb6  mov     eax, dword ptr [rsp+4C0h+var_450+0Ch]
0x18005fdba  mov     dword ptr [rsp+4C0h+SystemTime.wDayOfWeek], eax
0x18005fdbe  mov     eax, 0CCCCCCCDh
0x18005fdc3  shl     ecx, 17h
0x18005fdc6  mul     ecx
0x18005fdc8  shr     edx, 3
0x18005fdcb  mov     eax, edx
0x18005fdcd  cmp     qword ptr [rsp+4C0h+SystemTime.wYear], rax
0x18005fdd2  jbe     loc_18005FE5F
0x18005fdd8  xorps   xmm0, xmm0
0x18005fddb  lea     rcx, [rsp+4C0h+SystemTime]; lpSystemTime
0x18005fde0  movups  xmmword ptr [rsp+4C0h+SystemTime.wYear], xmm0
0x18005fde5  call    cs:__imp_GetSystemTime
0x18005fdeb  movzx   ecx, [rsp+4C0h+SystemTime.wMinute]
0x18005fdf0  movzx   edx, [rsp+4C0h+SystemTime.wHour]
0x18005fdf5  movzx   r8d, [rsp+4C0h+SystemTime.wDay]
0x18005fdfb  movzx   eax, [rsp+4C0h+SystemTime.wSecond]
0x18005fe00  movzx   r10d, [rsp+4C0h+SystemTime.wMonth]
0x18005fe06  movzx   r9d, [rsp+4C0h+SystemTime.wYear]
0x18005fe0c  mov     [rsp+4C0h+var_480], eax
0x18005fe10  mov     [rsp+4C0h+var_488], ecx
0x18005fe14  lea     rcx, [rbp+3C0h+pszMore]; unsigned __int16 *
0x18005fe18  mov     [rsp+4C0h+var_490], edx
0x18005fe1c  mov     edx, 104h; unsigned __int64
0x18005fe21  mov     [rsp+4C0h+var_498], r8d
0x18005fe26  lea     r8, aAppreadiness04; "AppReadiness-%04d%02d%02d-%02d%02d%02d."...
0x18005fe2d  mov     [rsp+4C0h+var_4A0], r10d
0x18005fe32  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18005fe37  test    eax, eax
0x18005fe39  js      short loc_18005FE5F
0x18005fe3b  lea     rdx, [rbp+3C0h+NewFileName]; pszPath
0x18005fe42  lea     rcx, [rbp+3C0h+pszMore]; pszMore
0x18005fe46  call    ?ComputeLogfilePath@Logging@AppReadiness@@YAJPEBGPEAG_K@Z; AppReadiness::Logging::ComputeLogfilePath(ushort const *,ushort *,unsigned __int64)
0x18005fe4b  test    eax, eax
0x18005fe4d  js      short loc_18005FE5F
0x18005fe4f  lea     rdx, [rbp+3C0h+NewFileName]; lpNewFileName
0x18005fe56  mov     rcx, rdi; lpExistingFileName
0x18005fe59  call    cs:__imp_MoveFileW
0x18005fe5f  mov     rcx, [rbp+3C0h+var_10]
0x18005fe66  xor     rcx, rsp; StackCookie
0x18005fe69  call    __security_check_cookie
0x18005fe6e  lea     r11, [rsp+4C0h+var_s0]
0x18005fe76  mov     rbx, [r11+18h]
0x18005fe7a  mov     rdi, [r11+20h]
0x18005fe7e  mov     rsp, r11
0x18005fe81  pop     rbp
0x18005fe82  retn
```
