# SensorGroupId::CreateInstanceEntry(ushort const *)

- ea: `0x180009ed0`
- end: `0x18000a072`
- name: `?CreateInstanceEntry@SensorGroupId@@SAJPEBG@Z`
- size: `418`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180009bf0`

## callees

- `0x180005fa0`
- `0x180009b74`
- `0x180009ed0`
- `0x18000ec30`
- `0x180031920`
- `0x18003491c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009faf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a03e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a04c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009faf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a03e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a04c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000a001`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000a001`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a05f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a05f`

## pseudocode

```c
__int64 __fastcall SensorGroupId::CreateInstanceEntry(LPCWSTR lpSubKey)
{
  HKEY v2; // rbx
  int v3; // eax
  signed int v4; // edi
  int v5; // eax
  HKEY v6; // rbx
  LSTATUS v7; // eax
  void **v9; // [rsp+50h] [rbp-20h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+58h] [rbp-18h] BYREF
  HKEY v11; // [rsp+A8h] [rbp+38h] BYREF
  HKEY hKey; // [rsp+B0h] [rbp+40h] BYREF
  char v13; // [rsp+B8h] [rbp+48h] BYREF

  v9 = &AutoSecurityAttributes::`vftable';
  v2 = 0;
  hKey = 0;
  v11 = 0;
  memset(&SecurityAttributes, 0, sizeof(SecurityAttributes));
  v3 = AutoSecurityAttributes::Set(
         (AutoSecurityAttributes *)&v9,
         L"D:(A;;GA;;;BA)(A;;GA;;;OW)(A;;GA;;;LS)(A;;GRGX;;;WD)(A;;GRGX;;;S-1-15-3-3845273463-1331427702-1186551195-1148109977)");
  v4 = v3;
  if ( v3 >= 0 )
  {
    v5 = OpenSensorGroupRegistryKey(0, 0x20106u, 0, &v11);
    v4 = v5;
    if ( v5 >= 0 )
    {
      v6 = hKey;
      if ( hKey )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&v13);
        RegCloseKey(v6);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&v13);
      }
      v2 = v11;
      hKey = 0;
      v7 = RegCreateKeyExW(v11, lpSubKey, 0, 0, 0, 0x20106u, &SecurityAttributes, &hKey, 0);
      v4 = v7;
      if ( v7 )
      {
        if ( v7 > 0 )
          v4 = (unsigned __int16)v7 | 0x80070000;
        if ( v4 < 0 && g_wppLevels )
          WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, &WPP_c6ec3a891c39353f20252a4447583601_Traceguids, 0, v4);
      }
      else
      {
        v4 = 0;
      }
    }
    else
    {
      if ( g_wppLevels )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, &WPP_c6ec3a891c39353f20252a4447583601_Traceguids, 0, v5);
      v2 = v11;
    }
  }
  else if ( g_wppLevels )
  {
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, &WPP_c6ec3a891c39353f20252a4447583601_Traceguids, 0, v3);
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( v2 )
    RegCloseKey(v2);
  v9 = &AutoSecurityAttributes::`vftable';
  if ( SecurityAttributes.lpSecurityDescriptor )
    LocalFree(SecurityAttributes.lpSecurityDescriptor);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180009ed0  push    rbp
0x180009ed2  push    rbx
0x180009ed3  push    rsi
0x180009ed4  push    rdi
0x180009ed5  push    r12
0x180009ed7  mov     rbp, rsp
0x180009eda  sub     rsp, 70h
0x180009ede  xor     eax, eax
0x180009ee0  lea     r12, ??_7AutoSecurityAttributes@@6B@; const AutoSecurityAttributes::`vftable'
0x180009ee7  mov     rsi, rcx
0x180009eea  mov     [rbp+var_20], r12
0x180009eee  xorps   xmm0, xmm0
0x180009ef1  mov     qword ptr [rbp+SecurityAttributes.bInheritHandle], rax
0x180009ef5  xor     ebx, ebx
0x180009ef7  mov     [rbp+hKey], rax
0x180009efb  lea     rcx, [rbp+var_20]; this
0x180009eff  mov     [rbp+arg_8], rbx
0x180009f03  lea     rdx, StringSecurityDescriptor; "D:(A;;GA;;;BA)(A;;GA;;;OW)(A;;GA;;;LS)("...
0x180009f0a  movups  xmmword ptr [rbp+SecurityAttributes.nLength], xmm0
0x180009f0e  call    ?Set@AutoSecurityAttributes@@QEAAJPEBG@Z; AutoSecurityAttributes::Set(ushort const *)
0x180009f13  mov     edi, eax
0x180009f15  test    eax, eax
0x180009f17  jns     short loc_180009F4C
0x180009f19  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180009f20  jb      loc_18000A035
0x180009f26  lea     edx, [rbx+3Dh]
0x180009f29  mov     [rsp+70h+dwOptions], eax
0x180009f2d  mov     rcx, cs:WPP_GLOBAL_Control
0x180009f34  lea     r8, WPP_c6ec3a891c39353f20252a4447583601_Traceguids
0x180009f3b  xor     r9d, r9d
0x180009f3e  mov     rcx, [rcx+10h]
0x180009f42  call    WPP_SF_qD
0x180009f47  jmp     loc_18000A035
0x180009f4c  lea     r9, [rbp+arg_8]; HKEY *
0x180009f50  xor     r8d, r8d; bool *
0x180009f53  mov     edx, 20106h; unsigned int
0x180009f58  xor     ecx, ecx; unsigned __int16 *
0x180009f5a  call    ?OpenSensorGroupRegistryKey@@YAJPEBGKPEA_NPEAPEAUHKEY__@@@Z; OpenSensorGroupRegistryKey(ushort const *,ulong,bool *,HKEY__ * *)
0x180009f5f  mov     edi, eax
0x180009f61  test    eax, eax
0x180009f63  jns     short loc_180009F9A
0x180009f65  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180009f6c  jb      short loc_180009F91
0x180009f6e  mov     rcx, cs:WPP_GLOBAL_Control
0x180009f75  lea     r8, WPP_c6ec3a891c39353f20252a4447583601_Traceguids
0x180009f7c  mov     edx, 3Eh ; '>'
0x180009f81  mov     [rsp+70h+dwOptions], eax
0x180009f85  xor     r9d, r9d
0x180009f88  mov     rcx, [rcx+10h]
0x180009f8c  call    WPP_SF_qD
0x180009f91  mov     rbx, [rbp+arg_8]
0x180009f95  jmp     loc_18000A035
0x180009f9a  mov     rbx, [rbp+hKey]
0x180009f9e  test    rbx, rbx
0x180009fa1  jz      short loc_180009FBE
0x180009fa3  lea     rcx, [rbp+arg_18]; this
0x180009fa7  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180009fac  mov     rcx, rbx; hKey
0x180009faf  call    cs:__imp_RegCloseKey
0x180009fb5  lea     rcx, [rbp+arg_18]; this
0x180009fb9  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180009fbe  mov     rbx, [rbp+arg_8]
0x180009fc2  lea     rax, [rbp+hKey]
0x180009fc6  mov     [rsp+70h+lpdwDisposition], 0; lpdwDisposition
0x180009fcf  xor     r9d, r9d; lpClass
0x180009fd2  mov     [rsp+70h+phkResult], rax; phkResult
0x180009fd7  xor     r8d, r8d; Reserved
0x180009fda  lea     rax, [rbp+SecurityAttributes]
0x180009fde  mov     [rbp+hKey], 0
0x180009fe6  mov     [rsp+70h+lpSecurityAttributes], rax; lpSecurityAttributes
0x180009feb  mov     rdx, rsi; lpSubKey
0x180009fee  mov     [rsp+70h+samDesired], 20106h; samDesired
0x180009ff6  mov     rcx, rbx; hKey
0x180009ff9  mov     [rsp+70h+dwOptions], 0; dwOptions
0x18000a001  call    cs:__imp_RegCreateKeyExW
0x18000a007  mov     edi, eax
0x18000a009  test    eax, eax
0x18000a00b  jz      short loc_18000A033
0x18000a00d  jle     short loc_18000A018
0x18000a00f  movzx   edi, ax
0x18000a012  or      edi, 80070000h
0x18000a018  test    edi, edi
0x18000a01a  jns     short loc_18000A035
0x18000a01c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000a023  jb      short loc_18000A035
0x18000a025  mov     edx, 3Fh ; '?'
0x18000a02a  mov     [rsp+70h+dwOptions], edi
0x18000a02e  jmp     loc_180009F2D
0x18000a033  xor     edi, edi
0x18000a035  mov     rcx, [rbp+hKey]; hKey
0x18000a039  test    rcx, rcx
0x18000a03c  jz      short loc_18000A044
0x18000a03e  call    cs:__imp_RegCloseKey
0x18000a044  test    rbx, rbx
0x18000a047  jz      short loc_18000A052
0x18000a049  mov     rcx, rbx; hKey
0x18000a04c  call    cs:__imp_RegCloseKey
0x18000a052  mov     rcx, [rbp+SecurityAttributes.lpSecurityDescriptor]; hMem
0x18000a056  mov     [rbp+var_20], r12
0x18000a05a  test    rcx, rcx
0x18000a05d  jz      short loc_18000A065
0x18000a05f  call    cs:__imp_LocalFree
0x18000a065  mov     eax, edi
0x18000a067  add     rsp, 70h
0x18000a06b  pop     r12
0x18000a06d  pop     rdi
0x18000a06e  pop     rsi
0x18000a06f  pop     rbx
0x18000a070  pop     rbp
0x18000a071  retn
```
