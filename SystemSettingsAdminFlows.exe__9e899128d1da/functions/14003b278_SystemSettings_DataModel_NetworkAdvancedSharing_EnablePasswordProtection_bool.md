# SystemSettings::DataModel::NetworkAdvancedSharing::EnablePasswordProtection(bool)

- ea: `0x14003b278`
- end: `0x14003b4e2`
- name: `?EnablePasswordProtection@NetworkAdvancedSharing@DataModel@SystemSettings@@SAJ_N@Z`
- size: `618`
- prototype: `__int64 __fastcall(bool)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140020120`

## callees

- `0x14001f3d4`
- `0x14003aed0`
- `0x14003b278`
- `0x14007d010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x14003b2b3`
- `ole32!CoCreateInstance` at `0x14003b3d5`
- `ole32!CoCreateInstance` at `0x14003b2b3`
- `ole32!CoCreateInstance` at `0x14003b3d5`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall SystemSettings::DataModel::NetworkAdvancedSharing::EnablePasswordProtection(char a1)
{
  HRESULT Instance; // eax
  unsigned int v3; // ebx
  __int64 result; // rax
  __int64 v5; // rax
  int v6; // eax
  unsigned int v7; // ebx
  const char *v8; // r9
  int v9; // eax
  unsigned int v10; // ebx
  LPVOID v11; // rcx
  HRESULT v12; // eax
  unsigned int v13; // ebx
  int v14; // eax
  unsigned int v15; // ebx
  int v16; // eax
  unsigned int v17; // ebx
  int ppv; // [rsp+20h] [rbp-18h]
  int ppva; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  LPVOID v21; // [rsp+48h] [rbp+10h] BYREF
  __int64 *v22; // [rsp+50h] [rbp+18h] BYREF

  v21 = 0;
  v22 = 0;
  Instance = CoCreateInstance(
               &CLSID_ShellLocalMachine,
               0,
               1u,
               &GUID_e93cf64b_c14d_4a1a_9572_adab3c2e9461,
               (LPVOID *)&v22);
  v3 = Instance;
  if ( Instance < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x46,
      (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\networkadvancedsharing\\lib\\networkadvancedsharing.cpp",
      (const char *)(unsigned int)Instance,
      ppv);
    wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>((__int64 *)&v21);
    wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>((__int64 *)&v22);
    return v3;
  }
  try
  {
    v5 = *v22;
    if ( a1 )
    {
      v6 = (*(__int64 (__fastcall **)(__int64 *, __int64))(v5 + 136))(v22, 2);
      v7 = v6;
      if ( v6 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x4A,
          (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\networkadvancedsharing\\lib\\networkadvancedsharing.cpp",
          (const char *)(unsigned int)v6,
          ppv);
        wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>((__int64 *)&v21);
        wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>((__int64 *)&v22);
        return v7;
      }
LABEL_8:
      v11 = v21;
      v21 = 0;
      if ( v11 )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v11 + 16LL))(v11);
      v12 = CoCreateInstance(
              &CLSID_SharingConfigurationManager,
              0,
              1u,
              &GUID_b4cd448a_9c86_4466_9201_2e62105b87ae,
              &v21);
      v13 = v12;
      if ( v12 >= 0 )
      {
        v14 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)v21 + 40LL))(v21, 1);
        v15 = v14;
        if ( v14 >= 0 )
        {
          v16 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)v21 + 24LL))(v21, 1, 2);
          v17 = v16;
          if ( v16 >= 0 )
          {
            wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>((__int64 *)&v21);
            wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>((__int64 *)&v22);
            return 0;
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x55,
              (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\networkadvancedsharing\\lib\\networkadvancedsharing.cpp",
              (const char *)(unsigned int)v16,
              ppva);
            wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>((__int64 *)&v21);
            wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>((__int64 *)&v22);
            return v17;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x53,
            (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\networkadvancedsharing\\lib\\networkadvancedsharing.cpp",
            (const char *)(unsigned int)v14,
            ppva);
          wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>((__int64 *)&v21);
          wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>((__int64 *)&v22);
          return v15;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x51,
          (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\networkadvancedsharing\\lib\\networkadvancedsharing.cpp",
          (const char *)(unsigned int)v12,
          ppva);
        wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>((__int64 *)&v21);
        wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>((__int64 *)&v22);
        return v13;
      }
    }
    v9 = (*(__int64 (__fastcall **)(__int64 *, __int64))(v5 + 128))(v22, 2);
    v10 = v9;
    if ( v9 >= 0 )
      goto LABEL_8;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4E,
      (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\networkadvancedsharing\\lib\\networkadvancedsharing.cpp",
      (const char *)(unsigned int)v9,
      ppv);
    wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>((__int64 *)&v21);
    wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>((__int64 *)&v22);
    result = v10;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x59,
                           (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\networkadvancedsharing\\lib\\networ"
                                         "kadvancedsharing.cpp",
                           v8);
  }
  return result;
}

```

## disassembly

```asm
0x14003b278  mov     r11, rsp
0x14003b27b  mov     [r11+8], rbx
0x14003b27f  push    rdi
0x14003b280  sub     rsp, 30h
0x14003b284  mov     dil, cl
0x14003b287  mov     qword ptr [r11+10h], 0
0x14003b28f  mov     qword ptr [r11+18h], 0
0x14003b297  lea     rax, [r11+18h]
0x14003b29b  mov     [r11-18h], rax
0x14003b29f  lea     r9, _GUID_e93cf64b_c14d_4a1a_9572_adab3c2e9461; riid
0x14003b2a6  xor     edx, edx; pUnkOuter
0x14003b2a8  lea     r8d, [rdx+1]; dwClsContext
0x14003b2ac  lea     rcx, CLSID_ShellLocalMachine; rclsid
0x14003b2b3  call    cs:__imp_CoCreateInstance
0x14003b2b9  mov     ebx, eax
0x14003b2bb  test    eax, eax
0x14003b2bd  jns     short loc_14003B2F5
0x14003b2bf  mov     rcx, [rsp+38h]; this
0x14003b2c4  mov     r9d, eax; char *
0x14003b2c7  lea     r8, aPcshellShellSy_16; "pcshell\\shell\\systemsettings\\adminfl"...
0x14003b2ce  mov     edx, 46h ; 'F'; void *
0x14003b2d3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003b2d8  nop
0x14003b2d9  lea     rcx, [rsp+38h+arg_8]
0x14003b2de  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x14003b2e3  nop
0x14003b2e4  lea     rcx, [rsp+38h+arg_10]
0x14003b2e9  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x14003b2ee  mov     eax, ebx
0x14003b2f0  jmp     loc_14003B4D6
0x14003b2f5  mov     rcx, [rsp+38h+arg_10]
0x14003b2fa  mov     edx, 2
0x14003b2ff  mov     rax, [rcx]
0x14003b302  test    dil, dil
0x14003b305  jz      short loc_14003B34F
0x14003b307  mov     rax, [rax+88h]
0x14003b30e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003b313  mov     ebx, eax
0x14003b315  test    eax, eax
0x14003b317  jns     short loc_14003B397
0x14003b319  mov     rcx, [rsp+38h]; this
0x14003b31e  mov     r9d, eax; char *
0x14003b321  lea     r8, aPcshellShellSy_16; "pcshell\\shell\\systemsettings\\adminfl"...
0x14003b328  mov     edx, 4Ah ; 'J'; void *
0x14003b32d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003b332  nop
0x14003b333  lea     rcx, [rsp+38h+arg_8]
0x14003b338  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x14003b33d  nop
0x14003b33e  lea     rcx, [rsp+38h+arg_10]
0x14003b343  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x14003b348  mov     eax, ebx
0x14003b34a  jmp     loc_14003B4D6
0x14003b34f  mov     rax, [rax+80h]
0x14003b356  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003b35b  mov     ebx, eax
0x14003b35d  test    eax, eax
0x14003b35f  jns     short loc_14003B397
0x14003b361  mov     rcx, [rsp+38h]; this
0x14003b366  mov     r9d, eax; char *
0x14003b369  lea     r8, aPcshellShellSy_16; "pcshell\\shell\\systemsettings\\adminfl"...
0x14003b370  mov     edx, 4Eh ; 'N'; void *
0x14003b375  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003b37a  nop
0x14003b37b  lea     rcx, [rsp+38h+arg_8]
0x14003b380  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x14003b385  nop
0x14003b386  lea     rcx, [rsp+38h+arg_10]
0x14003b38b  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x14003b390  mov     eax, ebx
0x14003b392  jmp     loc_14003B4D6
0x14003b397  mov     rcx, [rsp+38h+arg_8]
0x14003b39c  mov     [rsp+38h+arg_8], 0
0x14003b3a5  test    rcx, rcx
0x14003b3a8  jz      short loc_14003B3B7
0x14003b3aa  mov     rax, [rcx]
0x14003b3ad  mov     rax, [rax+10h]
0x14003b3b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003b3b6  nop
0x14003b3b7  lea     rax, [rsp+38h+arg_8]
0x14003b3bc  mov     qword ptr [rsp+38h+ppv], rax; int
0x14003b3c1  lea     r9, _GUID_b4cd448a_9c86_4466_9201_2e62105b87ae; riid
0x14003b3c8  xor     edx, edx; pUnkOuter
0x14003b3ca  lea     r8d, [rdx+1]; dwClsContext
0x14003b3ce  lea     rcx, CLSID_SharingConfigurationManager; rclsid
0x14003b3d5  call    cs:__imp_CoCreateInstance
0x14003b3db  mov     ebx, eax
0x14003b3dd  test    eax, eax
0x14003b3df  jns     short loc_14003B417
0x14003b3e1  mov     rcx, [rsp+38h]; this
0x14003b3e6  mov     r9d, eax; char *
0x14003b3e9  lea     r8, aPcshellShellSy_16; "pcshell\\shell\\systemsettings\\adminfl"...
0x14003b3f0  mov     edx, 51h ; 'Q'; void *
0x14003b3f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003b3fa  nop
0x14003b3fb  lea     rcx, [rsp+38h+arg_8]
0x14003b400  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x14003b405  nop
0x14003b406  lea     rcx, [rsp+38h+arg_10]
0x14003b40b  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x14003b410  mov     eax, ebx
0x14003b412  jmp     loc_14003B4D6
0x14003b417  mov     rcx, [rsp+38h+arg_8]
0x14003b41c  mov     rax, [rcx]
0x14003b41f  mov     edx, 1
0x14003b424  mov     rax, [rax+28h]
0x14003b428  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003b42d  mov     ebx, eax
0x14003b42f  test    eax, eax
0x14003b431  jns     short loc_14003B466
0x14003b433  mov     rcx, [rsp+38h]; this
0x14003b438  mov     r9d, eax; char *
0x14003b43b  lea     r8, aPcshellShellSy_16; "pcshell\\shell\\systemsettings\\adminfl"...
0x14003b442  mov     edx, 53h ; 'S'; void *
0x14003b447  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003b44c  nop
0x14003b44d  lea     rcx, [rsp+38h+arg_8]
0x14003b452  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x14003b457  nop
0x14003b458  lea     rcx, [rsp+38h+arg_10]
0x14003b45d  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x14003b462  mov     eax, ebx
0x14003b464  jmp     short loc_14003B4D6
0x14003b466  mov     rcx, [rsp+38h+arg_8]
0x14003b46b  mov     rax, [rcx]
0x14003b46e  mov     edx, 1
0x14003b473  lea     r8d, [rdx+1]
0x14003b477  mov     rax, [rax+18h]
0x14003b47b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003b480  mov     ebx, eax
0x14003b482  test    eax, eax
0x14003b484  jns     short loc_14003B4B9
0x14003b486  mov     rcx, [rsp+38h]; this
0x14003b48b  mov     r9d, eax; char *
0x14003b48e  lea     r8, aPcshellShellSy_16; "pcshell\\shell\\systemsettings\\adminfl"...
0x14003b495  mov     edx, 55h ; 'U'; void *
0x14003b49a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003b49f  nop
0x14003b4a0  lea     rcx, [rsp+38h+arg_8]
0x14003b4a5  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x14003b4aa  nop
0x14003b4ab  lea     rcx, [rsp+38h+arg_10]
0x14003b4b0  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x14003b4b5  mov     eax, ebx
0x14003b4b7  jmp     short loc_14003B4D6
0x14003b4b9  lea     rcx, [rsp+38h+arg_8]
0x14003b4be  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x14003b4c3  nop
0x14003b4c4  lea     rcx, [rsp+38h+arg_10]
0x14003b4c9  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x14003b4ce  xor     eax, eax
0x14003b4d0  jmp     short loc_14003B4D6
0x14003b4d2  mov     eax, dword ptr [rsp+38h+arg_8]
0x14003b4d6  mov     rbx, [rsp+38h+arg_0]
0x14003b4db  add     rsp, 30h
0x14003b4df  pop     rdi
0x14003b4e0  retn
```
