# FSMConfigurationsManager::InternalUpdateWSEOptInState_Save(IFSConfigurationKey *,bool)

- ea: `0x180028d70`
- end: `0x18002909c`
- name: `?InternalUpdateWSEOptInState_Save@FSMConfigurationsManager@@MEAAJPEAUIFSConfigurationKey@@_N@Z`
- size: `812`
- prototype: `int(FSMConfigurationsManager *__hidden this, struct IFSConfigurationKey *, bool)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x1800019f0`
- `0x180005f98`
- `0x180006a68`
- `0x180006a98`
- `0x18000d778`
- `0x180028d70`
- `0x180039f6c`
- `0x18003bcb0`
- `0x18003c898`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x180028f6c`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x180028f6c`

## pseudocode

```c
__int64 __fastcall FSMConfigurationsManager::InternalUpdateWSEOptInState_Save(
        FSMConfigurationsManager *this,
        struct IFSConfigurationKey *a2,
        char a3)
{
  int v6; // eax
  int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // rax
  __int64 v10; // rdx
  __int64 v12; // rcx
  __int64 (__fastcall **v13)(struct IFSConfigurationKey *, GUID *, __int64 *); // rax
  __int64 (__fastcall *v14)(struct IFSConfigurationKey *, GUID *, __int64 *); // rbx
  struct IFSConfiguration *v15; // rsi
  __int64 (__fastcall *v16)(struct IFSConfiguration *, __int64 *, __int64, _QWORD); // rdi
  unsigned int v17; // ebx
  __int64 v18; // rax
  struct IFSConfiguration *v19; // [rsp+30h] [rbp-29h] BYREF
  __int64 v20; // [rsp+38h] [rbp-21h] BYREF
  int v21; // [rsp+40h] [rbp-19h] BYREF
  unsigned int v22; // [rsp+44h] [rbp-15h] BYREF
  __int64 v23; // [rsp+48h] [rbp-11h] BYREF
  __int128 v24; // [rsp+50h] [rbp-9h] BYREF
  __int64 v25; // [rsp+60h] [rbp+7h] BYREF
  __int128 v26; // [rsp+68h] [rbp+Fh] BYREF
  __int64 v27; // [rsp+78h] [rbp+1Fh]

  v19 = 0;
  v27 = 0;
  v26 = 0;
  v20 = 0;
  v23 = 0;
  v22 = 0;
  if ( (unsigned __int8)byte_18005E5A5 >= 8u )
    WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 27), 46, &WPP_a34380bbb6b43d25e2b3a85add1dbda1_Traceguids, this, a2);
  wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset((__int64 *)&v19);
  if ( (int)FSLoadPublicDataDeviceConfiguration(a2, &v19) < 0 )
  {
    wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset((__int64 *)&v19);
    v6 = FSConfiguration::CreateConfiguration(a2, 1, &v19);
    v7 = v6;
    if ( v6 < 0 )
    {
      if ( g_wppLevels )
      {
        v8 = 47;
LABEL_35:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, &WPP_a34380bbb6b43d25e2b3a85add1dbda1_Traceguids, this, v6);
        goto LABEL_36;
      }
      goto LABEL_36;
    }
    goto LABEL_10;
  }
  v7 = 0;
  v21 = 0;
  if ( (*(int (__fastcall **)(struct IFSConfiguration *, __int64 *, __int128 *, __int64, int *))(*(_QWORD *)v19 + 120LL))(
         v19,
         FSM_WSEOPTIN_CONFIGURATION_INFO,
         &v26,
         24,
         &v21) < 0
    || v21 != 24 )
  {
LABEL_10:
    v9 = 0;
    v27 = 0;
    goto LABEL_11;
  }
  v9 = v27;
LABEL_11:
  if ( a3 || !v9 )
  {
    v12 = v20;
    v25 = 0;
    v13 = *(__int64 (__fastcall ***)(struct IFSConfigurationKey *, GUID *, __int64 *))a2;
    v20 = 0;
    v24 = 0;
    v14 = *v13;
    if ( v12 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    v6 = v14(a2, &GUID_d8ebce9c_16ac_4353_8b31_c7afd4fc67c1, &v20);
    v7 = v6;
    if ( v6 < 0 )
    {
      if ( g_wppLevels )
      {
        v8 = 48;
        goto LABEL_35;
      }
LABEL_36:
      if ( !byte_18005E5A5 )
        goto LABEL_17;
      v10 = 53;
      goto LABEL_16;
    }
    *((_QWORD *)&v24 + 1) |= 1uLL;
    *(_QWORD *)&v24 = 0x1800000001LL;
    GetSystemTimePreciseAsFileTime(&v25);
    v6 = (*(__int64 (__fastcall **)(struct IFSConfiguration *, __int64 *, __int128 *, __int64))(*(_QWORD *)v19 + 208LL))(
           v19,
           FSM_WSEOPTIN_CONFIGURATION_INFO,
           &v24,
           24);
    v7 = v6;
    if ( v6 < 0 )
    {
      if ( g_wppLevels )
      {
        v8 = 49;
        goto LABEL_35;
      }
      goto LABEL_36;
    }
    v15 = v19;
    v16 = *(__int64 (__fastcall **)(struct IFSConfiguration *, __int64 *, __int64, _QWORD))(*(_QWORD *)v19 + 208LL);
    v17 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v20 + 88LL))(v20);
    v18 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v20 + 80LL))(v20);
    v6 = v16(v15, FSM_WSEOPTIN_CONFIGURATION_KEY_INFO, v18, v17);
    v7 = v6;
    if ( v6 < 0 )
    {
      if ( g_wppLevels )
      {
        v8 = 50;
        goto LABEL_35;
      }
      goto LABEL_36;
    }
    v6 = (*(__int64 (__fastcall **)(struct IFSConfiguration *, __int64 *, unsigned int *))(*(_QWORD *)v19 + 280LL))(
           v19,
           &v23,
           &v22);
    v7 = v6;
    if ( v6 < 0 )
    {
      if ( g_wppLevels )
      {
        v8 = 51;
        goto LABEL_35;
      }
      goto LABEL_36;
    }
    v6 = FSSavePublicDataDeviceConfiguration(a2, v23, v22);
    v7 = v6;
    if ( v6 < 0 )
    {
      if ( g_wppLevels )
      {
        v8 = 52;
        goto LABEL_35;
      }
      goto LABEL_36;
    }
  }
  else if ( v7 < 0 )
  {
    goto LABEL_36;
  }
  if ( (unsigned __int8)byte_18005E5A5 >= 8u )
  {
    v10 = 54;
LABEL_16:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), v10, &WPP_a34380bbb6b43d25e2b3a85add1dbda1_Traceguids, this, v7);
  }
LABEL_17:
  wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(&v20);
  wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&v19);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180028d70  mov     [rsp-8+arg_10], rbx
0x180028d75  push    rbp
0x180028d76  push    rsi
0x180028d77  push    rdi
0x180028d78  push    r14
0x180028d7a  push    r15
0x180028d7c  lea     rbp, [rsp-37h]
0x180028d81  sub     rsp, 90h
0x180028d88  mov     rax, cs:__security_cookie
0x180028d8f  xor     rax, rsp
0x180028d92  mov     [rbp+57h+var_30], rax
0x180028d96  xor     eax, eax
0x180028d98  mov     [rbp+57h+var_80], 0
0x180028da0  xorps   xmm0, xmm0
0x180028da3  mov     [rbp+57h+var_38], rax
0x180028da7  movups  [rbp+57h+var_48], xmm0
0x180028dab  mov     [rbp+57h+var_78], rax
0x180028daf  mov     dil, r8b
0x180028db2  mov     [rbp+57h+var_68], rax
0x180028db6  mov     r15, rdx
0x180028db9  mov     [rbp+57h+var_6C], eax
0x180028dbc  mov     r14, rcx
0x180028dbf  cmp     cs:byte_18005E5A5, 8
0x180028dc6  jb      short loc_180028DED
0x180028dc8  mov     r9, rcx
0x180028dcb  mov     [rsp+0B0h+var_90], r15
0x180028dd0  mov     rcx, cs:WPP_GLOBAL_Control
0x180028dd7  lea     edx, [rax+2Eh]
0x180028dda  lea     r8, WPP_a34380bbb6b43d25e2b3a85add1dbda1_Traceguids
0x180028de1  mov     rcx, [rcx+0D8h]
0x180028de8  call    WPP_SF_qq
0x180028ded  lea     rcx, [rbp+57h+var_80]
0x180028df1  call    ?reset@?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(void)
0x180028df6  lea     rdx, [rbp+57h+var_80]
0x180028dfa  mov     rcx, r15
0x180028dfd  call    FSLoadPublicDataDeviceConfiguration
0x180028e02  mov     esi, 18h
0x180028e07  test    eax, eax
0x180028e09  jns     short loc_180028E3D
0x180028e0b  lea     rcx, [rbp+57h+var_80]
0x180028e0f  call    ?reset@?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(void)
0x180028e14  lea     r8, [rbp+57h+var_80]; struct IFSConfiguration **
0x180028e18  mov     dl, 1; bool
0x180028e1a  mov     rcx, r15; struct IFSConfigurationKey *
0x180028e1d  call    ?CreateConfiguration@FSConfiguration@@SAJPEAUIFSConfigurationKey@@_NPEAPEAUIFSConfiguration@@@Z; FSConfiguration::CreateConfiguration(IFSConfigurationKey *,bool,IFSConfiguration * *)
0x180028e22  mov     ebx, eax
0x180028e24  test    eax, eax
0x180028e26  jns     short loc_180028E78
0x180028e28  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180028e2f  jb      loc_180029085
0x180028e35  lea     edx, [rsi+17h]
0x180028e38  jmp     loc_180029067
0x180028e3d  mov     rcx, [rbp+57h+var_80]
0x180028e41  lea     rdx, [rbp+57h+var_70]
0x180028e45  mov     [rsp+0B0h+var_90], rdx
0x180028e4a  lea     r8, [rbp+57h+var_48]
0x180028e4e  xor     ebx, ebx
0x180028e50  lea     rdx, FSM_WSEOPTIN_CONFIGURATION_INFO
0x180028e57  mov     [rbp+57h+var_70], ebx
0x180028e5a  mov     r9d, esi
0x180028e5d  mov     rax, [rcx]
0x180028e60  mov     rax, [rax+78h]
0x180028e64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028e69  test    eax, eax
0x180028e6b  js      short loc_180028E78
0x180028e6d  cmp     [rbp+57h+var_70], esi
0x180028e70  jnz     short loc_180028E78
0x180028e72  mov     rax, [rbp+57h+var_38]
0x180028e76  jmp     short loc_180028E7E
0x180028e78  xor     eax, eax
0x180028e7a  mov     [rbp+57h+var_38], rax
0x180028e7e  test    dil, dil
0x180028e81  jnz     short loc_180028EF6
0x180028e83  test    rax, rax
0x180028e86  jz      short loc_180028EF6
0x180028e88  test    ebx, ebx
0x180028e8a  js      loc_180029085
0x180028e90  cmp     cs:byte_18005E5A5, 8
0x180028e97  jb      short loc_180028EBF
0x180028e99  mov     edx, 36h ; '6'
0x180028e9e  mov     rcx, cs:WPP_GLOBAL_Control
0x180028ea5  lea     r8, WPP_a34380bbb6b43d25e2b3a85add1dbda1_Traceguids
0x180028eac  mov     r9, r14
0x180028eaf  mov     dword ptr [rsp+0B0h+var_90], ebx
0x180028eb3  mov     rcx, [rcx+0D8h]
0x180028eba  call    WPP_SF_qD
0x180028ebf  lea     rcx, [rbp+57h+var_78]
0x180028ec3  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x180028ec8  lea     rcx, [rbp+57h+var_80]
0x180028ecc  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x180028ed1  mov     eax, ebx
0x180028ed3  mov     rcx, [rbp+57h+var_30]
0x180028ed7  xor     rcx, rsp; StackCookie
0x180028eda  call    __security_check_cookie
0x180028edf  mov     rbx, [rsp+0B0h+arg_10]
0x180028ee7  add     rsp, 90h
0x180028eee  pop     r15
0x180028ef0  pop     r14
0x180028ef2  pop     rdi
0x180028ef3  pop     rsi
0x180028ef4  pop     rbp
0x180028ef5  retn
0x180028ef6  mov     rcx, [rbp+57h+var_78]
0x180028efa  xor     eax, eax
0x180028efc  mov     [rbp+57h+var_50], rax
0x180028f00  xorps   xmm0, xmm0
0x180028f03  mov     rax, [r15]
0x180028f06  mov     [rbp+57h+var_78], 0
0x180028f0e  movups  [rbp+57h+var_60], xmm0
0x180028f12  mov     rbx, [rax]
0x180028f15  test    rcx, rcx
0x180028f18  jz      short loc_180028F26
0x180028f1a  mov     rdx, [rcx]
0x180028f1d  mov     rax, [rdx+10h]
0x180028f21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028f26  lea     r8, [rbp+57h+var_78]
0x180028f2a  mov     rcx, r15
0x180028f2d  lea     rdx, _GUID_d8ebce9c_16ac_4353_8b31_c7afd4fc67c1
0x180028f34  mov     rax, rbx
0x180028f37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028f3c  mov     ebx, eax
0x180028f3e  test    eax, eax
0x180028f40  jns     short loc_180028F59
0x180028f42  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180028f49  jb      loc_180029085
0x180028f4f  mov     edx, 30h ; '0'
0x180028f54  jmp     loc_180029067
0x180028f59  or      qword ptr [rbp+57h+var_60+8], 1
0x180028f5e  lea     rcx, [rbp+57h+var_50]
0x180028f62  mov     dword ptr [rbp+57h+var_60], 1
0x180028f69  mov     dword ptr [rbp+57h+var_60+4], esi
0x180028f6c  call    cs:__imp_GetSystemTimePreciseAsFileTime
0x180028f72  mov     rcx, [rbp+57h+var_80]
0x180028f76  lea     r8, [rbp+57h+var_60]
0x180028f7a  mov     r9d, esi
0x180028f7d  lea     rdx, FSM_WSEOPTIN_CONFIGURATION_INFO
0x180028f84  mov     rax, [rcx]
0x180028f87  mov     rax, [rax+0D0h]
0x180028f8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028f93  mov     ebx, eax
0x180028f95  test    eax, eax
0x180028f97  jns     short loc_180028FB0
0x180028f99  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180028fa0  jb      loc_180029085
0x180028fa6  mov     edx, 31h ; '1'
0x180028fab  jmp     loc_180029067
0x180028fb0  mov     rsi, [rbp+57h+var_80]
0x180028fb4  mov     rcx, [rbp+57h+var_78]
0x180028fb8  mov     rax, [rsi]
0x180028fbb  mov     rdi, [rax+0D0h]
0x180028fc2  mov     rax, [rcx]
0x180028fc5  mov     rax, [rax+58h]
0x180028fc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028fce  mov     rcx, [rbp+57h+var_78]
0x180028fd2  mov     ebx, eax
0x180028fd4  mov     rdx, [rcx]
0x180028fd7  mov     rax, [rdx+50h]
0x180028fdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028fe0  mov     r8, rax
0x180028fe3  lea     rdx, FSM_WSEOPTIN_CONFIGURATION_KEY_INFO
0x180028fea  mov     rax, rdi
0x180028fed  mov     r9d, ebx
0x180028ff0  mov     rcx, rsi
0x180028ff3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028ff8  mov     ebx, eax
0x180028ffa  test    eax, eax
0x180028ffc  jns     short loc_18002900E
0x180028ffe  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180029005  jb      short loc_180029085
0x180029007  mov     edx, 32h ; '2'
0x18002900c  jmp     short loc_180029067
0x18002900e  mov     rcx, [rbp+57h+var_80]
0x180029012  lea     r8, [rbp+57h+var_6C]
0x180029016  lea     rdx, [rbp+57h+var_68]
0x18002901a  mov     rax, [rcx]
0x18002901d  mov     rax, [rax+118h]
0x180029024  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029029  mov     ebx, eax
0x18002902b  test    eax, eax
0x18002902d  jns     short loc_18002903F
0x18002902f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180029036  jb      short loc_180029085
0x180029038  mov     edx, 33h ; '3'
0x18002903d  jmp     short loc_180029067
0x18002903f  mov     r8d, [rbp+57h+var_6C]
0x180029043  mov     rcx, r15
0x180029046  mov     rdx, [rbp+57h+var_68]
0x18002904a  call    FSSavePublicDataDeviceConfiguration
0x18002904f  mov     ebx, eax
0x180029051  test    eax, eax
0x180029053  jns     loc_180028E90
0x180029059  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180029060  jb      short loc_180029085
0x180029062  mov     edx, 34h ; '4'
0x180029067  mov     rcx, cs:WPP_GLOBAL_Control
0x18002906e  lea     r8, WPP_a34380bbb6b43d25e2b3a85add1dbda1_Traceguids
0x180029075  mov     r9, r14
0x180029078  mov     dword ptr [rsp+0B0h+var_90], eax
0x18002907c  mov     rcx, [rcx+10h]
0x180029080  call    WPP_SF_qD
0x180029085  cmp     cs:byte_18005E5A5, 1
0x18002908c  jb      loc_180028EBF
0x180029092  mov     edx, 35h ; '5'
0x180029097  jmp     loc_180028E9E
```
