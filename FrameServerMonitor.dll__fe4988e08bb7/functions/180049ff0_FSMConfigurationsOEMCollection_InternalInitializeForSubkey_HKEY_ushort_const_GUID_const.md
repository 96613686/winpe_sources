# FSMConfigurationsOEMCollection::InternalInitializeForSubkey(HKEY__ *,ushort const *,_GUID const &)

- ea: `0x180049ff0`
- end: `0x18004a224`
- name: `?InternalInitializeForSubkey@FSMConfigurationsOEMCollection@@MEAAJPEAUHKEY__@@PEBGAEBU_GUID@@@Z`
- size: `564`
- prototype: `int(FSMConfigurationsOEMCollection *__hidden this, HKEY, const unsigned __int16 *, const struct _GUID *)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800019f0`
- `0x180002346`
- `0x180005f98`
- `0x180006a98`
- `0x180007348`
- `0x18000e6bc`
- `0x180017b98`
- `0x180049ff0`
- `0x18004aacc`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004a0b8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004a0b8`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18004a115`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18004a115`

## pseudocode

```c
__int64 __fastcall FSMConfigurationsOEMCollection::InternalInitializeForSubkey(
        FSMConfigurationsOEMCollection *this,
        HKEY a2,
        const unsigned __int16 *a3,
        const struct _GUID *a4)
{
  unsigned int v8; // ebx
  __int64 v9; // rdx
  DWORD v10; // esi
  LSTATUS v11; // eax
  int v12; // eax
  __int64 v13; // rdx
  struct IFSMConfigurationsOEM *v15; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cchName[4]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Name[264]; // [rsp+60h] [rbp-A0h] BYREF

  hKey = 0;
  if ( !a2 )
  {
    v8 = -2147024809;
    if ( !g_wppLevels )
      goto LABEL_25;
    v9 = 43;
LABEL_4:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v9,
      WPP_05511007120d3393f1a8ac4501dd3aa6_Traceguids,
      this,
      -2147024809);
    goto LABEL_25;
  }
  if ( !a3 )
  {
    v8 = -2147024809;
    if ( !g_wppLevels )
      goto LABEL_25;
    v9 = 44;
    goto LABEL_4;
  }
  v8 = 0;
  v10 = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  if ( RegOpenKeyExW(a2, a3, 0, 0x20019u, &hKey) )
    goto LABEL_25;
  while ( 1 )
  {
    memset_0(Name, 0, 0x208u);
    cchName[0] = 260;
    v11 = RegEnumKeyExW(hKey, v10, Name, cchName, 0, 0, 0, 0);
    if ( v11 )
    {
      if ( v11 == 259 )
        goto LABEL_25;
      goto LABEL_18;
    }
    v15 = 0;
    v12 = FSMConfigurationsOEM::CreateInstance(hKey, a4, Name, &v15);
    v8 = v12;
    if ( v12 < 0 )
      break;
    if ( (*(unsigned int (__fastcall **)(struct IFSMConfigurationsOEM *))(*(_QWORD *)v15 + 24LL))(v15) )
    {
      if ( !(unsigned int)CTUnkArray<IFSCameraControlState>::Add((__int64 *)this + 7, (__int64)v15) )
      {
        v12 = -2147024882;
        v8 = -2147024882;
        if ( !g_wppLevels )
          goto LABEL_24;
        v13 = 46;
        goto LABEL_23;
      }
    }
    else if ( !(unsigned int)CTUnkArray<IFSCameraControlState>::Add((__int64 *)this + 10, (__int64)v15) )
    {
      v12 = -2147024882;
      v8 = -2147024882;
      if ( !g_wppLevels )
        goto LABEL_24;
      v13 = 47;
      goto LABEL_23;
    }
    wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&v15);
LABEL_18:
    ++v10;
  }
  if ( !g_wppLevels )
    goto LABEL_24;
  v13 = 45;
LABEL_23:
  WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, WPP_05511007120d3393f1a8ac4501dd3aa6_Traceguids, this, v12);
LABEL_24:
  wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&v15);
LABEL_25:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return v8;
}

```

## disassembly

```asm
0x180049ff0  push    rbp
0x180049ff2  push    rbx
0x180049ff3  push    rsi
0x180049ff4  push    rdi
0x180049ff5  push    r12
0x180049ff7  push    r14
0x180049ff9  push    r15
0x180049ffb  lea     rbp, [rsp-180h]
0x18004a003  sub     rsp, 280h
0x18004a00a  mov     rax, cs:__security_cookie
0x18004a011  xor     rax, rsp
0x18004a014  mov     [rbp+1B0h+var_40], rax
0x18004a01b  mov     [rsp+2B0h+hKey], 0
0x18004a024  mov     r12, r9
0x18004a027  mov     r14, r8
0x18004a02a  mov     r15, rdx
0x18004a02d  mov     rdi, rcx
0x18004a030  test    rdx, rdx
0x18004a033  jnz     short loc_18004A070
0x18004a035  mov     eax, 80070057h
0x18004a03a  mov     ebx, eax
0x18004a03c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004a043  jb      loc_18004A1F7
0x18004a049  lea     edx, [r15+2Bh]
0x18004a04d  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a054  lea     r8, WPP_05511007120d3393f1a8ac4501dd3aa6_Traceguids
0x18004a05b  mov     r9, rdi
0x18004a05e  mov     dword ptr [rsp+2B0h+phkResult], eax
0x18004a062  mov     rcx, [rcx+10h]
0x18004a066  call    WPP_SF_qD
0x18004a06b  jmp     loc_18004A1F7
0x18004a070  test    r14, r14
0x18004a073  jnz     short loc_18004A08F
0x18004a075  mov     eax, 80070057h
0x18004a07a  mov     ebx, eax
0x18004a07c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004a083  jb      loc_18004A1F7
0x18004a089  lea     edx, [r14+2Ch]
0x18004a08d  jmp     short loc_18004A04D
0x18004a08f  xor     edx, edx
0x18004a091  lea     rcx, [rsp+2B0h+hKey]
0x18004a096  xor     ebx, ebx
0x18004a098  xor     esi, esi
0x18004a09a  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18004a09f  lea     rax, [rsp+2B0h+hKey]
0x18004a0a4  mov     r9d, 20019h; samDesired
0x18004a0aa  xor     r8d, r8d; ulOptions
0x18004a0ad  mov     [rsp+2B0h+phkResult], rax; phkResult
0x18004a0b2  mov     rdx, r14; lpSubKey
0x18004a0b5  mov     rcx, r15; hKey
0x18004a0b8  call    cs:__imp_RegOpenKeyExW
0x18004a0be  test    eax, eax
0x18004a0c0  jnz     loc_18004A1F7
0x18004a0c6  xor     edx, edx; Val
0x18004a0c8  lea     rcx, [rsp+2B0h+Name]; void *
0x18004a0cd  mov     r8d, 208h; Size
0x18004a0d3  call    memset_0
0x18004a0d8  mov     rcx, [rsp+2B0h+hKey]; hKey
0x18004a0dd  lea     r9, [rsp+2B0h+cchName]; lpcchName
0x18004a0e2  mov     [rsp+2B0h+lpftLastWriteTime], 0; lpftLastWriteTime
0x18004a0eb  lea     r8, [rsp+2B0h+Name]; lpName
0x18004a0f0  mov     [rsp+2B0h+lpcchClass], 0; lpcchClass
0x18004a0f9  mov     edx, esi; dwIndex
0x18004a0fb  mov     [rsp+2B0h+lpClass], 0; lpClass
0x18004a104  mov     [rsp+2B0h+phkResult], 0; lpReserved
0x18004a10d  mov     [rsp+2B0h+cchName], 104h
0x18004a115  call    cs:__imp_RegEnumKeyExW
0x18004a11b  test    eax, eax
0x18004a11d  jnz     short loc_18004A19C
0x18004a11f  mov     rcx, [rsp+2B0h+hKey]; HKEY
0x18004a124  lea     r9, [rsp+2B0h+var_270]; struct IFSMConfigurationsOEM **
0x18004a129  lea     r8, [rsp+2B0h+Name]; unsigned __int16 *
0x18004a12e  mov     [rsp+2B0h+var_270], 0
0x18004a137  mov     rdx, r12; struct _GUID *
0x18004a13a  call    ?CreateInstance@FSMConfigurationsOEM@@SAJPEAUHKEY__@@AEBU_GUID@@PEBGPEAPEAUIFSMConfigurationsOEM@@@Z; FSMConfigurationsOEM::CreateInstance(HKEY__ *,_GUID const &,ushort const *,IFSMConfigurationsOEM * *)
0x18004a13f  mov     ebx, eax
0x18004a141  test    eax, eax
0x18004a143  js      short loc_18004A1C1
0x18004a145  mov     rcx, [rsp+2B0h+var_270]
0x18004a14a  mov     rdx, [rcx]
0x18004a14d  mov     rax, [rdx+18h]
0x18004a151  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a156  mov     rdx, [rsp+2B0h+var_270]
0x18004a15b  test    eax, eax
0x18004a15d  jz      short loc_18004A183
0x18004a15f  lea     rcx, [rdi+38h]
0x18004a163  call    ?Add@?$CTUnkArray@UIFSCameraControlState@@@@QEAAHPEAUIFSCameraControlState@@@Z; CTUnkArray<IFSCameraControlState>::Add(IFSCameraControlState *)
0x18004a168  test    eax, eax
0x18004a16a  jnz     short loc_18004A190
0x18004a16c  mov     eax, 8007000Eh
0x18004a171  mov     ebx, eax
0x18004a173  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004a17a  jb      short loc_18004A1ED
0x18004a17c  mov     edx, 2Eh ; '.'
0x18004a181  jmp     short loc_18004A1CF
0x18004a183  lea     rcx, [rdi+50h]
0x18004a187  call    ?Add@?$CTUnkArray@UIFSCameraControlState@@@@QEAAHPEAUIFSCameraControlState@@@Z; CTUnkArray<IFSCameraControlState>::Add(IFSCameraControlState *)
0x18004a18c  test    eax, eax
0x18004a18e  jz      short loc_18004A1AA
0x18004a190  lea     rcx, [rsp+2B0h+var_270]
0x18004a195  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x18004a19a  jmp     short loc_18004A1A3
0x18004a19c  cmp     eax, 103h
0x18004a1a1  jz      short loc_18004A1F7
0x18004a1a3  inc     esi
0x18004a1a5  jmp     loc_18004A0C6
0x18004a1aa  mov     eax, 8007000Eh
0x18004a1af  mov     ebx, eax
0x18004a1b1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004a1b8  jb      short loc_18004A1ED
0x18004a1ba  mov     edx, 2Fh ; '/'
0x18004a1bf  jmp     short loc_18004A1CF
0x18004a1c1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004a1c8  jb      short loc_18004A1ED
0x18004a1ca  mov     edx, 2Dh ; '-'
0x18004a1cf  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a1d6  lea     r8, WPP_05511007120d3393f1a8ac4501dd3aa6_Traceguids
0x18004a1dd  mov     r9, rdi
0x18004a1e0  mov     dword ptr [rsp+2B0h+phkResult], eax
0x18004a1e4  mov     rcx, [rcx+10h]
0x18004a1e8  call    WPP_SF_qD
0x18004a1ed  lea     rcx, [rsp+2B0h+var_270]
0x18004a1f2  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x18004a1f7  lea     rcx, [rsp+2B0h+hKey]
0x18004a1fc  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18004a201  mov     eax, ebx
0x18004a203  mov     rcx, [rbp+1B0h+var_40]
0x18004a20a  xor     rcx, rsp; StackCookie
0x18004a20d  call    __security_check_cookie
0x18004a212  add     rsp, 280h
0x18004a219  pop     r15
0x18004a21b  pop     r14
0x18004a21d  pop     r12
0x18004a21f  pop     rdi
0x18004a220  pop     rsi
0x18004a221  pop     rbx
0x18004a222  pop     rbp
0x18004a223  retn
```
