# WaasMedic::RegQueryStringValue(HKEY__ *,ushort const *,ushort const *,ushort * *,WaasMedic::RegistryHiveType)

- ea: `0x180026e38`
- end: `0x180027000`
- name: `?RegQueryStringValue@WaasMedic@@YAJPEAUHKEY__@@PEBG1PEAPEAGW4RegistryHiveType@1@@Z`
- size: `456`
- prototype: `int __high(HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **, enum WaasMedic::RegistryHiveType)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x1800247c0`

## callees

- `0x180026e38`
- `0x18002a300`
- `0x18002a4e4`
- `0x180034964`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x180026ea7`
- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x180026ea7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180026f03`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180026f03`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180026f33`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180026f8b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180026f33`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180026f8b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026fe8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026fe8`

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
  v9 = dword_1800A55AC == 0;
  *a4 = 0;
  if ( v9 )
  {
    dword_1800A55B0 = 0;
    memset(&SystemInfo, 0, sizeof(SystemInfo));
    GetNativeSystemInfo(&SystemInfo);
    if ( SystemInfo.wProcessorArchitecture == 6 || SystemInfo.wProcessorArchitecture == 9 )
      dword_1800A55B0 = 1;
    dword_1800A55AC = 1;
  }
  v10 = 1;
  if ( dword_1800A55B0 )
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
0x180026e38  mov     [rsp-18h+arg_8], rbx
0x180026e3d  mov     qword ptr [rsp-18h+Type], rcx
0x180026e42  push    rbp
0x180026e43  push    rsi
0x180026e44  push    rdi
0x180026e45  mov     rbp, rsp
0x180026e48  sub     rsp, 60h
0x180026e4c  mov     [rbp+Type], 0
0x180026e53  mov     rdi, r9
0x180026e56  mov     [rbp+hKey], 0
0x180026e5e  mov     rsi, r8
0x180026e61  mov     [rbp+cbData], 0
0x180026e68  mov     rbx, rdx
0x180026e6b  test    r9, r9
0x180026e6e  jnz     short loc_180026E7A
0x180026e70  mov     eax, 80004003h
0x180026e75  jmp     loc_180026FF0
0x180026e7a  cmp     cs:dword_1800A55AC, 0
0x180026e81  mov     qword ptr [r9], 0
0x180026e88  jnz     short loc_180026ED7
0x180026e8a  xorps   xmm0, xmm0
0x180026e8d  mov     cs:dword_1800A55B0, 0
0x180026e97  lea     rcx, [rbp+SystemInfo]; lpSystemInfo
0x180026e9b  movups  xmmword ptr [rbp+SystemInfo], xmm0
0x180026e9f  movups  xmmword ptr [rbp+SystemInfo.lpMaximumApplicationAddress], xmm0
0x180026ea3  movups  xmmword ptr [rbp+SystemInfo.dwNumberOfProcessors], xmm0
0x180026ea7  call    cs:__imp_GetNativeSystemInfo
0x180026ead  mov     eax, 6
0x180026eb2  cmp     ax, word ptr [rbp+SystemInfo]
0x180026eb6  jz      short loc_180026EC3
0x180026eb8  mov     eax, 9
0x180026ebd  cmp     ax, word ptr [rbp+SystemInfo]
0x180026ec1  jnz     short loc_180026ECD
0x180026ec3  mov     cs:dword_1800A55B0, 1
0x180026ecd  mov     cs:dword_1800A55AC, 1
0x180026ed7  cmp     cs:dword_1800A55B0, 0
0x180026ede  mov     eax, 101h
0x180026ee3  mov     r9d, 1
0x180026ee9  cmovnz  r9d, eax; samDesired
0x180026eed  lea     rax, [rbp+hKey]
0x180026ef1  xor     r8d, r8d; ulOptions
0x180026ef4  mov     rdx, rbx; lpSubKey
0x180026ef7  mov     [rsp+60h+phkResult], rax; phkResult
0x180026efc  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180026f03  call    cs:__imp_RegOpenKeyExW
0x180026f09  mov     ebx, eax
0x180026f0b  test    eax, eax
0x180026f0d  jnz     loc_180026FA7
0x180026f13  mov     rcx, [rbp+hKey]; hKey
0x180026f17  lea     rax, [rbp+cbData]
0x180026f1b  mov     [rsp+60h+lpcbData], rax; lpcbData
0x180026f20  lea     r9, [rbp+Type]; lpType
0x180026f24  xor     r8d, r8d; lpReserved
0x180026f27  mov     [rsp+60h+phkResult], 0; lpData
0x180026f30  mov     rdx, rsi; lpValueName
0x180026f33  call    cs:__imp_RegQueryValueExW
0x180026f39  mov     ebx, eax
0x180026f3b  test    eax, eax
0x180026f3d  jnz     short loc_180026FA7
0x180026f3f  mov     eax, [rbp+cbData]
0x180026f42  test    eax, eax
0x180026f44  jz      short loc_180026FB2
0x180026f46  cmp     [rbp+Type], 1
0x180026f4a  jz      short loc_180026F53
0x180026f4c  mov     ebx, 8007000Dh
0x180026f51  jmp     short loc_180026FB6
0x180026f53  add     eax, 2
0x180026f56  mov     ecx, eax; this
0x180026f58  mov     [rbp+cbData], eax
0x180026f5b  call    ?SafeAlloc@WaasMedic@@YAPEAX_K_N@Z; WaasMedic::SafeAlloc(unsigned __int64,bool)
0x180026f60  mov     [rdi], rax
0x180026f63  test    rax, rax
0x180026f66  jnz     short loc_180026F6F
0x180026f68  mov     ebx, 8007000Eh
0x180026f6d  jmp     short loc_180026FB6
0x180026f6f  lea     rcx, [rbp+cbData]
0x180026f73  xor     r8d, r8d; lpReserved
0x180026f76  mov     [rsp+60h+lpcbData], rcx; lpcbData
0x180026f7b  lea     r9, [rbp+Type]; lpType
0x180026f7f  mov     rcx, [rbp+hKey]; hKey
0x180026f83  mov     rdx, rsi; lpValueName
0x180026f86  mov     [rsp+60h+phkResult], rax; lpData
0x180026f8b  call    cs:__imp_RegQueryValueExW
0x180026f91  mov     ebx, eax
0x180026f93  test    eax, eax
0x180026f95  jnz     short loc_180026FA7
0x180026f97  mov     edx, [rbp+cbData]
0x180026f9a  mov     rcx, [rdi]
0x180026f9d  and     rdx, 0FFFFFFFFFFFFFFFEh
0x180026fa1  mov     [rdx+rcx], ax
0x180026fa5  jmp     short loc_180026FDF
0x180026fa7  jle     short loc_180026FB2
0x180026fa9  movzx   ebx, ax
0x180026fac  or      ebx, 80070000h
0x180026fb2  test    ebx, ebx
0x180026fb4  jns     short loc_180026FDF
0x180026fb6  mov     rcx, [rdi]; this
0x180026fb9  call    ?SafeFree@WaasMedic@@YAJPEAX@Z; WaasMedic::SafeFree(void *)
0x180026fbe  mov     qword ptr [rdi], 0
0x180026fc5  cmp     ebx, 80070002h
0x180026fcb  jz      short loc_180026FDF
0x180026fcd  mov     r8d, ebx; int
0x180026fd0  lea     rcx, aString_0; "string"
0x180026fd7  mov     rdx, rsi; unsigned __int16 *
0x180026fda  call    ?ReportRegUtilQueryValueFailed@TelemetryProvider@WaasMedic@@SAXPEBG0J@Z; WaasMedic::TelemetryProvider::ReportRegUtilQueryValueFailed(ushort const *,ushort const *,long)
0x180026fdf  mov     rcx, [rbp+hKey]; hKey
0x180026fe3  test    rcx, rcx
0x180026fe6  jz      short loc_180026FEE
0x180026fe8  call    cs:__imp_RegCloseKey
0x180026fee  mov     eax, ebx
0x180026ff0  mov     rbx, [rsp+60h+arg_8]
0x180026ff8  add     rsp, 60h
0x180026ffc  pop     rdi
0x180026ffd  pop     rsi
0x180026ffe  pop     rbp
0x180026fff  retn
```
