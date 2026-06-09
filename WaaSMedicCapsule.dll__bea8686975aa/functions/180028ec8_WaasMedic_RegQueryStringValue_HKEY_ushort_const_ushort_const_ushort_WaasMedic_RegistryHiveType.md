# WaasMedic::RegQueryStringValue(HKEY__ *,ushort const *,ushort const *,ushort * *,WaasMedic::RegistryHiveType)

- ea: `0x180028ec8`
- end: `0x180029090`
- name: `?RegQueryStringValue@WaasMedic@@YAJPEAUHKEY__@@PEBG1PEAPEAGW4RegistryHiveType@1@@Z`
- size: `456`
- prototype: `int __high(HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **, enum WaasMedic::RegistryHiveType)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x18000c228`
- `0x18000d750`
- `0x180023e50`

## callees

- `0x180024fc4`
- `0x1800251a8`
- `0x180028ec8`
- `0x180031df4`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x180028f37`
- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x180028f37`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180028fc3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002901b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180028fc3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002901b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180028f93`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180028f93`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180029078`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180029078`

## pseudocode

```c
__int64 __fastcall WaasMedic::RegQueryStringValue(
        __int64 a1,
        const WCHAR *a2,
        const WCHAR *a3,
        WaasMedic **a4,
        DWORD cbData)
{
  bool v9; // zf
  REGSAM v10; // r9d
  LSTATUS v11; // eax
  void *v12; // rdx
  signed int v13; // ebx
  bool v14; // cc
  bool v15; // r8
  DWORD v16; // eax
  BYTE *v17; // rax
  struct _SYSTEM_INFO SystemInfo; // [rsp+30h] [rbp-30h] BYREF
  DWORD Type; // [rsp+80h] [rbp+20h] BYREF
  int v20; // [rsp+84h] [rbp+24h]
  HKEY hKey; // [rsp+98h] [rbp+38h] BYREF

  v20 = HIDWORD(a1);
  Type = 0;
  hKey = 0;
  cbData = 0;
  if ( !a4 )
    return 2147500035LL;
  v9 = dword_180098D58 == 0;
  *a4 = 0;
  if ( v9 )
  {
    dword_180098D54 = 0;
    memset(&SystemInfo, 0, sizeof(SystemInfo));
    GetNativeSystemInfo(&SystemInfo);
    if ( SystemInfo.wProcessorArchitecture == 6 || SystemInfo.wProcessorArchitecture == 9 )
      dword_180098D54 = 1;
    dword_180098D58 = 1;
  }
  v10 = 1;
  if ( dword_180098D54 )
    v10 = 257;
  v11 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, v10, &hKey);
  v13 = v11;
  v14 = v11 <= 0;
  if ( !v11 )
  {
    v11 = RegQueryValueExW(hKey, a3, 0, &Type, 0, &cbData);
    v13 = v11;
    v14 = v11 <= 0;
    if ( !v11 )
    {
      v16 = cbData;
      if ( !cbData )
        goto LABEL_21;
      if ( Type != 1 )
      {
        v13 = -2147024883;
        goto LABEL_22;
      }
      cbData += 2;
      v17 = (BYTE *)WaasMedic::SafeAlloc((WaasMedic *)(v16 + 2), (unsigned __int64)v12, v15);
      *a4 = (WaasMedic *)v17;
      if ( !v17 )
      {
        v13 = -2147024882;
        goto LABEL_22;
      }
      v11 = RegQueryValueExW(hKey, a3, 0, &Type, v17, &cbData);
      v13 = v11;
      v14 = v11 <= 0;
      if ( !v11 )
      {
        *(_WORD *)((char *)*a4 + (cbData & 0xFFFFFFFE)) = 0;
        goto LABEL_24;
      }
    }
  }
  if ( !v14 )
    v13 = (unsigned __int16)v11 | 0x80070000;
LABEL_21:
  if ( v13 < 0 )
  {
LABEL_22:
    WaasMedic::SafeFree(*a4, v12);
    *a4 = 0;
    if ( v13 != -2147024894 )
      WaasMedic::TelemetryProvider::ReportRegUtilQueryValueFailed(L"string", a3, v13);
  }
LABEL_24:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180028ec8  mov     [rsp-18h+arg_8], rbx
0x180028ecd  mov     qword ptr [rsp-18h+Type], rcx
0x180028ed2  push    rbp
0x180028ed3  push    rsi
0x180028ed4  push    rdi
0x180028ed5  mov     rbp, rsp
0x180028ed8  sub     rsp, 60h
0x180028edc  mov     [rbp+Type], 0
0x180028ee3  mov     rdi, r9
0x180028ee6  mov     [rbp+hKey], 0
0x180028eee  mov     rsi, r8
0x180028ef1  mov     [rbp+cbData], 0
0x180028ef8  mov     rbx, rdx
0x180028efb  test    r9, r9
0x180028efe  jnz     short loc_180028F0A
0x180028f00  mov     eax, 80004003h
0x180028f05  jmp     loc_180029080
0x180028f0a  cmp     cs:dword_180098D58, 0
0x180028f11  mov     qword ptr [r9], 0
0x180028f18  jnz     short loc_180028F67
0x180028f1a  xorps   xmm0, xmm0
0x180028f1d  mov     cs:dword_180098D54, 0
0x180028f27  lea     rcx, [rbp+SystemInfo]; lpSystemInfo
0x180028f2b  movups  xmmword ptr [rbp+SystemInfo], xmm0
0x180028f2f  movups  xmmword ptr [rbp+SystemInfo.lpMaximumApplicationAddress], xmm0
0x180028f33  movups  xmmword ptr [rbp+SystemInfo.dwNumberOfProcessors], xmm0
0x180028f37  call    cs:__imp_GetNativeSystemInfo
0x180028f3d  mov     eax, 6
0x180028f42  cmp     ax, word ptr [rbp+SystemInfo]
0x180028f46  jz      short loc_180028F53
0x180028f48  mov     eax, 9
0x180028f4d  cmp     ax, word ptr [rbp+SystemInfo]
0x180028f51  jnz     short loc_180028F5D
0x180028f53  mov     cs:dword_180098D54, 1
0x180028f5d  mov     cs:dword_180098D58, 1
0x180028f67  cmp     cs:dword_180098D54, 0
0x180028f6e  mov     eax, 101h
0x180028f73  mov     r9d, 1
0x180028f79  cmovnz  r9d, eax; samDesired
0x180028f7d  lea     rax, [rbp+hKey]
0x180028f81  xor     r8d, r8d; ulOptions
0x180028f84  mov     rdx, rbx; lpSubKey
0x180028f87  mov     [rsp+60h+phkResult], rax; phkResult
0x180028f8c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180028f93  call    cs:__imp_RegOpenKeyExW
0x180028f99  mov     ebx, eax
0x180028f9b  test    eax, eax
0x180028f9d  jnz     loc_180029037
0x180028fa3  mov     rcx, [rbp+hKey]; hKey
0x180028fa7  lea     rax, [rbp+cbData]
0x180028fab  mov     [rsp+60h+lpcbData], rax; lpcbData
0x180028fb0  lea     r9, [rbp+Type]; lpType
0x180028fb4  xor     r8d, r8d; lpReserved
0x180028fb7  mov     [rsp+60h+phkResult], 0; lpData
0x180028fc0  mov     rdx, rsi; lpValueName
0x180028fc3  call    cs:__imp_RegQueryValueExW
0x180028fc9  mov     ebx, eax
0x180028fcb  test    eax, eax
0x180028fcd  jnz     short loc_180029037
0x180028fcf  mov     eax, [rbp+cbData]
0x180028fd2  test    eax, eax
0x180028fd4  jz      short loc_180029042
0x180028fd6  cmp     [rbp+Type], 1
0x180028fda  jz      short loc_180028FE3
0x180028fdc  mov     ebx, 8007000Dh
0x180028fe1  jmp     short loc_180029046
0x180028fe3  add     eax, 2
0x180028fe6  mov     ecx, eax; this
0x180028fe8  mov     [rbp+cbData], eax
0x180028feb  call    ?SafeAlloc@WaasMedic@@YAPEAX_K_N@Z; WaasMedic::SafeAlloc(unsigned __int64,bool)
0x180028ff0  mov     [rdi], rax
0x180028ff3  test    rax, rax
0x180028ff6  jnz     short loc_180028FFF
0x180028ff8  mov     ebx, 8007000Eh
0x180028ffd  jmp     short loc_180029046
0x180028fff  lea     rcx, [rbp+cbData]
0x180029003  xor     r8d, r8d; lpReserved
0x180029006  mov     [rsp+60h+lpcbData], rcx; lpcbData
0x18002900b  lea     r9, [rbp+Type]; lpType
0x18002900f  mov     rcx, [rbp+hKey]; hKey
0x180029013  mov     rdx, rsi; lpValueName
0x180029016  mov     [rsp+60h+phkResult], rax; lpData
0x18002901b  call    cs:__imp_RegQueryValueExW
0x180029021  mov     ebx, eax
0x180029023  test    eax, eax
0x180029025  jnz     short loc_180029037
0x180029027  mov     edx, [rbp+cbData]
0x18002902a  mov     rcx, [rdi]
0x18002902d  and     rdx, 0FFFFFFFFFFFFFFFEh
0x180029031  mov     [rdx+rcx], ax
0x180029035  jmp     short loc_18002906F
0x180029037  jle     short loc_180029042
0x180029039  movzx   ebx, ax
0x18002903c  or      ebx, 80070000h
0x180029042  test    ebx, ebx
0x180029044  jns     short loc_18002906F
0x180029046  mov     rcx, [rdi]; this
0x180029049  call    ?SafeFree@WaasMedic@@YAJPEAX@Z; WaasMedic::SafeFree(void *)
0x18002904e  mov     qword ptr [rdi], 0
0x180029055  cmp     ebx, 80070002h
0x18002905b  jz      short loc_18002906F
0x18002905d  mov     r8d, ebx; int
0x180029060  lea     rcx, aString_0; "string"
0x180029067  mov     rdx, rsi; unsigned __int16 *
0x18002906a  call    ?ReportRegUtilQueryValueFailed@TelemetryProvider@WaasMedic@@SAXPEBG0J@Z; WaasMedic::TelemetryProvider::ReportRegUtilQueryValueFailed(ushort const *,ushort const *,long)
0x18002906f  mov     rcx, [rbp+hKey]; hKey
0x180029073  test    rcx, rcx
0x180029076  jz      short loc_18002907E
0x180029078  call    cs:__imp_RegCloseKey
0x18002907e  mov     eax, ebx
0x180029080  mov     rbx, [rsp+60h+arg_8]
0x180029088  add     rsp, 60h
0x18002908c  pop     rdi
0x18002908d  pop     rsi
0x18002908e  pop     rbp
0x18002908f  retn
```
