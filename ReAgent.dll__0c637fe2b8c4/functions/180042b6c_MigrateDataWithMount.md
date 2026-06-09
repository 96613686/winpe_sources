# MigrateDataWithMount

- ea: `0x180042b6c`
- end: `0x180042fef`
- name: `MigrateDataWithMount`
- size: `1155`
- prototype: `__int64 __usercall@<rax>(unsigned __int16 *@<rcx>, unsigned __int16 *, unsigned __int16 *, __int64, int, int)`
- caller_count: `1`
- callee_count: `22`
- tags: `file_ops, reparse_path, registry_config, loader_planting, installer_update`

## callers

- `0x18002f080`

## callees

- `0x1800059fc`
- `0x18001ee2c`
- `0x18003df50`
- `0x18003e000`
- `0x180040ff0`
- `0x18004117c`
- `0x18004131c`
- `0x180041340`
- `0x1800413b4`
- `0x180041424`
- `0x180041460`
- `0x18004152c`
- `0x18004156c`
- `0x1800416f4`
- `0x180041734`
- `0x180041a20`
- `0x180041b9c`
- `0x180041de4`
- `0x180042324`
- `0x1800428d0`
- `0x180042b6c`
- `0x18005cf30`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180042c61`
- `ntdll!RtlNtStatusToDosError` at `0x180042c70`
- `ntdll!RtlNtStatusToDosError` at `0x180042f15`
- `ntdll!RtlNtStatusToDosError` at `0x180042f24`
- `ntdll!RtlNtStatusToDosError` at `0x180042c61`
- `ntdll!RtlNtStatusToDosError` at `0x180042c70`
- `ntdll!RtlNtStatusToDosError` at `0x180042f15`
- `ntdll!RtlNtStatusToDosError` at `0x180042f24`
- `KERNEL32!GetLastError` at `0x180042f7a`
- `KERNEL32!GetLastError` at `0x180042f7a`
- `KERNEL32!SetLastError` at `0x180042c8d`
- `KERNEL32!SetLastError` at `0x180042f41`
- `KERNEL32!SetLastError` at `0x180042c8d`
- `KERNEL32!SetLastError` at `0x180042f41`
- `KERNEL32!GetFileAttributesExW` at `0x180042cbe`
- `KERNEL32!GetFileAttributesExW` at `0x180042f52`
- `KERNEL32!GetFileAttributesExW` at `0x180042cbe`
- `KERNEL32!GetFileAttributesExW` at `0x180042f52`
- `DismApi!DismInitialize` at `0x180042bbe`
- `DismApi!DismInitialize` at `0x180042bbe`

## string_xrefs

- `0x180042c42`: `MigrateDataWithMount failed to mount target wim [%s]. Error:0x%08X`
- `0x180042cac`: `MigrateDataWithMount failed to get mount path for target wim. Error:0x%08X`
- `0x180042ccb`: `MigrateDataWithMount winRE File Size Before: %d`
- `0x180042d20`: `MigrateDataWithMount Clean up the trust app info in registry key.`
- `0x180042d4a`: `MigrateDataWithMount failed to delete trust app info registry key. Error:0x%08X`
- `0x180042d89`: `MigrateDataWithMount failed to migrate OEM tools.`
- `0x180042d9a`: `MigrateDataWithMount OEM tools migration not required.`
- `0x180042dc9`: `MigrateDataWithMount RemoveSetupFilter error`
- `0x180042ddd`: `MigrateDataWithMount Remove setup filter not required.`
- `0x180042df0`: `MigrateDataWithMount Driver migration not required.`
- `0x180042ea7`: `MigrateDataWithMount Source error 0x%x 0x%x`
- `0x180042e53`: `MigrateDataWithMount   winreMigrateDrivers error`
- `0x180042e8f`: `MigrateDataWithMount failed to unmount target wim [%s]. Error:0x%08X`
- `0x180042ef5`: `MigrateDataWithMount failed to unmount target wim [%s]. Error:0x%08X`
- `0x180042ed2`: `MigrateDataWithMount   Unmount target wim for cleanup`
- `0x180042f5f`: `MigrateDataWithMount winRE File Size After: %d`

## pseudocode

```c
_BOOL8 __fastcall MigrateDataWithMount(
        unsigned __int16 *a1,
        __int64 a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned __int16 *a5,
        unsigned __int16 *a6,
        unsigned __int16 *a7,
        int a8,
        int a9)
{
  unsigned __int64 v11; // rdi
  BOOL v12; // esi
  int v14; // eax
  __int64 v15; // rcx
  NTSTATUS MountPath; // ebx
  const wchar_t *v17; // rdx
  __int64 v18; // rdx
  __int64 v19; // rax
  __int64 v20; // rdx
  const unsigned __int16 *v21; // rcx
  unsigned int v22; // eax
  const unsigned __int16 *v23; // rcx
  const unsigned __int16 *v24; // rcx
  const unsigned __int16 *v25; // rdx
  int v26; // eax
  ULONG v27; // ebx
  DWORD LastError; // eax
  __int64 v29; // rdx
  __int64 v30; // rdx
  __int64 v31; // rdx
  __int64 v33; // [rsp+20h] [rbp-E0h] BYREF
  _QWORD v34[2]; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE v35[32]; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 *v36; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v37; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v38[3]; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int64 v39; // [rsp+80h] [rbp-80h]
  unsigned __int16 *v40[3]; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int64 v41; // [rsp+A0h] [rbp-60h]
  __int128 FileInformation; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v43; // [rsp+B8h] [rbp-48h]
  unsigned int v44; // [rsp+C8h] [rbp-38h]
  _BYTE v45[41]; // [rsp+D0h] [rbp-30h] BYREF
  char v46; // [rsp+F9h] [rbp-7h]

  v11 = 0;
  v36 = a7;
  v12 = 0;
  v14 = DismInitialize(0, 0, 0);
  LODWORD(v33) = v14;
  if ( v14 < 0 )
    UnattendLogW(2, L"DismInitializeClass::DismInitializeClass failed to initialize DISM error 0x%x", (unsigned int)v14);
  DismMountClass::DismMountClass((DismMountClass *)v45);
  v34[1] = 0;
  v34[0] = std::_List_alloc<0,std::_List_base_types<std::wstring>>::_Buynode0(v15, 0, 0);
  v39 = 7;
  v41 = 7;
  v38[2] = 0;
  LOWORD(v38[0]) = 0;
  v40[2] = 0;
  LOWORD(v40[0]) = 0;
  FileInformation = 0;
  v44 = 0;
  v43 = 0;
  MountPath = DismMountClass::Mount((DismMountClass *)v45, a1, 0, a5);
  if ( MountPath < 0 )
  {
    v17 = L"MigrateDataWithMount failed to mount target wim [%s]. Error:0x%08X";
LABEL_5:
    UnattendLogW(2, v17, a1, (unsigned int)MountPath, v33, v34[0]);
LABEL_6:
    if ( (MountPath & 0x10000000) != 0 )
    {
      if ( RtlNtStatusToDosError(MountPath) != 317 )
        MountPath = RtlNtStatusToDosError(MountPath);
    }
    else if ( (MountPath & 0x1FFF0000) == 0x70000 )
    {
      MountPath = (unsigned __int16)MountPath;
    }
    goto LABEL_11;
  }
  MountPath = DismMountClass::GetMountPath((__int64)v45, (__int64)v38);
  if ( MountPath < 0 )
  {
    v17 = L"MigrateDataWithMount failed to get mount path for target wim. Error:0x%08X";
    goto LABEL_5;
  }
  if ( GetFileAttributesExW(a1, GetFileExInfoStandard, &FileInformation) )
  {
    v11 = v44 | ((unsigned __int64)HIDWORD(v43) << 32);
    UnattendLogW(0, L"MigrateDataWithMount winRE File Size Before: %d", v11);
  }
  AsmMigrateDataWithMountStart(v11, v18);
  if ( !a9 )
    goto LABEL_21;
  v19 = std::operator+<unsigned short>(v35, v38);
  std::wstring::operator=(v40, v19);
  LOBYTE(v20) = 1;
  std::wstring::_Tidy(v35, v20, 0);
  UnattendLogW(0, L"MigrateDataWithMount Clean up the trust app info in registry key.");
  v21 = (const unsigned __int16 *)v40;
  if ( v41 >= 8 )
    v21 = v40[0];
  v22 = winreRemoveTrustedBootApps(v21);
  MountPath = v22;
  if ( !v22 )
  {
LABEL_21:
    if ( a4 )
    {
      v23 = (const unsigned __int16 *)v38;
      if ( v39 >= 8 )
        v23 = v38[0];
      if ( !(unsigned int)pMigrateOemTools(v23, a4, a6, v36) )
        UnattendLogW(2, L"MigrateDataWithMount failed to migrate OEM tools.");
    }
    else
    {
      UnattendLogW(0, L"MigrateDataWithMount OEM tools migration not required.");
    }
    if ( a8 )
    {
      v24 = (const unsigned __int16 *)v38;
      if ( v39 >= 8 )
        v24 = v38[0];
      if ( !(unsigned int)pRemoveSetupFilter(v24) )
      {
        UnattendLogW(2, L"MigrateDataWithMount RemoveSetupFilter error");
        goto LABEL_48;
      }
    }
    else
    {
      UnattendLogW(0, L"MigrateDataWithMount Remove setup filter not required.");
    }
    if ( !a3 )
    {
      UnattendLogW(0, L"MigrateDataWithMount Driver migration not required.");
      goto LABEL_42;
    }
    DismSessionClass::DismSessionClass((DismSessionClass *)&v36, a3);
    v25 = (const unsigned __int16 *)v38;
    if ( v39 >= 8 )
      v25 = v38[0];
    DismSessionClass::DismSessionClass((DismSessionClass *)&v37, v25);
    if ( (int)v36 < 0 || (int)v37 < 0 )
    {
      UnattendLogW(2, L"MigrateDataWithMount Source error 0x%x 0x%x", v36, v37, v33, v34[0]);
    }
    else
    {
      if ( (unsigned int)winreMigrateDrivers((struct DismSessionClass *)&v36) )
      {
        DismSessionClass::~DismSessionClass((DismSessionClass *)&v37);
        DismSessionClass::~DismSessionClass((DismSessionClass *)&v36);
LABEL_42:
        if ( !v46 || (MountPath = DismMountClass::Unmount((DismMountClass *)v45, 1), MountPath >= 0) )
        {
          v12 = 1;
          goto LABEL_48;
        }
        UnattendLogW(
          1,
          L"MigrateDataWithMount failed to unmount target wim [%s]. Error:0x%08X",
          a1,
          (unsigned int)MountPath,
          v33,
          v34[0]);
        goto LABEL_6;
      }
      UnattendLogW(2, L"MigrateDataWithMount   winreMigrateDrivers error");
    }
    DismSessionClass::~DismSessionClass((DismSessionClass *)&v37);
    DismSessionClass::~DismSessionClass((DismSessionClass *)&v36);
    goto LABEL_48;
  }
  UnattendLogW(2, L"MigrateDataWithMount failed to delete trust app info registry key. Error:0x%08X", v22);
LABEL_11:
  SetLastError(MountPath);
LABEL_48:
  if ( v46 )
  {
    UnattendLogW(0, L"MigrateDataWithMount   Unmount target wim for cleanup");
    v26 = DismMountClass::Unmount((DismMountClass *)v45, v12);
    v27 = v26;
    if ( v26 < 0 )
    {
      UnattendLogW(2, L"MigrateDataWithMount failed to unmount target wim [%s]. Error:0x%08X", a1, (unsigned int)v26);
      if ( v12 )
      {
        if ( (v27 & 0x10000000) != 0 )
        {
          if ( RtlNtStatusToDosError(v27) != 317 )
            v27 = RtlNtStatusToDosError(v27);
        }
        else if ( (v27 & 0x1FFF0000) == 0x70000 )
        {
          v27 = (unsigned __int16)v27;
        }
        SetLastError(v27);
        v12 = 0;
      }
    }
  }
  if ( GetFileAttributesExW(a1, GetFileExInfoStandard, &FileInformation) )
  {
    v11 = v44 | ((unsigned __int64)HIDWORD(v43) << 32);
    UnattendLogW(0, L"MigrateDataWithMount winRE File Size After: %d", v11);
  }
  LastError = GetLastError();
  AsmMigrateDataWithMountEnd(v12, LastError, v11);
  LOBYTE(v29) = 1;
  std::wstring::_Tidy(v40, v29, 0);
  LOBYTE(v30) = 1;
  std::wstring::_Tidy(v38, v30, 0);
  std::list<std::wstring>::~list<std::wstring>(v34);
  DismMountClass::~DismMountClass((DismMountClass *)v45, v31);
  DismInitializeClass::~DismInitializeClass((DismInitializeClass *)&v33);
  return v12;
}

```

## disassembly

```asm
0x180042b6c  mov     [rsp-8+arg_8], rbx
0x180042b71  push    rbp
0x180042b72  push    rsi
0x180042b73  push    rdi
0x180042b74  push    r12
0x180042b76  push    r13
0x180042b78  push    r14
0x180042b7a  push    r15
0x180042b7c  lea     rbp, [rsp-10h]
0x180042b81  sub     rsp, 110h
0x180042b88  mov     rax, cs:__security_cookie
0x180042b8f  xor     rax, rsp
0x180042b92  mov     [rbp+40h+var_40], rax
0x180042b96  mov     rax, [rbp+40h+arg_30]
0x180042b9d  mov     r12, r8
0x180042ba0  mov     rbx, [rbp+40h+arg_20]
0x180042ba4  mov     r14, rcx
0x180042ba7  mov     r13, [rbp+40h+arg_28]
0x180042bab  xor     edi, edi
0x180042bad  xor     r8d, r8d
0x180042bb0  mov     [rsp+140h+var_E8], rax
0x180042bb5  xor     ecx, ecx
0x180042bb7  xor     edx, edx
0x180042bb9  mov     esi, edi
0x180042bbb  mov     r15, r9
0x180042bbe  call    cs:__imp_DismInitialize
0x180042bc4  mov     dword ptr [rsp+140h+var_120], eax
0x180042bc8  test    eax, eax
0x180042bca  jns     short loc_180042BDE
0x180042bcc  mov     r8d, eax
0x180042bcf  lea     rdx, aDisminitialize_1; "DismInitializeClass::DismInitializeClas"...
0x180042bd6  lea     ecx, [rdi+2]
0x180042bd9  call    UnattendLogW
0x180042bde  lea     rcx, [rbp+40h+var_70]; this
0x180042be2  call    ??0DismMountClass@@QEAA@XZ; DismMountClass::DismMountClass(void)
0x180042be7  xor     edx, edx
0x180042be9  mov     [rsp+140h+var_110], rdi
0x180042bee  xor     r8d, r8d
0x180042bf1  call    ?_Buynode0@?$_List_alloc@$0A@U?$_List_base_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@std@@QEAAPEAU?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@2@PEAU32@0@Z; std::_List_alloc<0,std::_List_base_types<std::wstring>>::_Buynode0(std::_List_node<std::wstring,void *> *,std::_List_node<std::wstring,void *> *)
0x180042bf6  mov     ecx, 7
0x180042bfb  mov     [rsp+140h+var_118], rax
0x180042c00  xorps   xmm0, xmm0
0x180042c03  mov     [rbp+40h+var_C0], rcx
0x180042c07  mov     [rbp+40h+var_A0], rcx
0x180042c0b  xor     eax, eax
0x180042c0d  lea     rcx, [rbp+40h+var_70]; this
0x180042c11  mov     [rsp+140h+var_C8], rdi
0x180042c16  mov     r9, rbx; unsigned __int16 *
0x180042c19  mov     word ptr [rsp+140h+var_D8], di
0x180042c1e  xor     r8d, r8d; bool
0x180042c21  mov     [rbp+40h+var_A8], rdi
0x180042c25  mov     rdx, r14; unsigned __int16 *
0x180042c28  mov     word ptr [rbp+40h+var_B8], di
0x180042c2c  movups  [rbp+40h+FileInformation], xmm0
0x180042c30  mov     [rbp+40h+var_78], eax
0x180042c33  movups  [rbp+40h+var_88], xmm0
0x180042c37  call    ?Mount@DismMountClass@@QEAAJPEBG_N0@Z; DismMountClass::Mount(ushort const *,bool,ushort const *)
0x180042c3c  mov     ebx, eax
0x180042c3e  test    eax, eax
0x180042c40  jns     short loc_180042C98
0x180042c42  lea     rdx, aMigratedatawit_8; "MigrateDataWithMount failed to mount ta"...
0x180042c49  mov     ecx, 2
0x180042c4e  mov     r9d, ebx
0x180042c51  mov     r8, r14
0x180042c54  call    UnattendLogW
0x180042c59  bt      ebx, 1Ch
0x180042c5d  jnb     short loc_180042C7A
0x180042c5f  mov     ecx, ebx; Status
0x180042c61  call    cs:__imp_RtlNtStatusToDosError
0x180042c67  cmp     eax, 13Dh
0x180042c6c  jz      short loc_180042C8B
0x180042c6e  mov     ecx, ebx; Status
0x180042c70  call    cs:__imp_RtlNtStatusToDosError
0x180042c76  mov     ebx, eax
0x180042c78  jmp     short loc_180042C8B
0x180042c7a  mov     eax, ebx
0x180042c7c  and     eax, 1FFF0000h
0x180042c81  cmp     eax, 70000h
0x180042c86  jnz     short loc_180042C8B
0x180042c88  movzx   ebx, bx
0x180042c8b  mov     ecx, ebx; dwErrCode
0x180042c8d  call    cs:__imp_SetLastError
0x180042c93  jmp     loc_180042ECC
0x180042c98  lea     rdx, [rsp+140h+var_D8]
0x180042c9d  lea     rcx, [rbp+40h+var_70]
0x180042ca1  call    ?GetMountPath@DismMountClass@@QEAAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; DismMountClass::GetMountPath(std::wstring &)
0x180042ca6  mov     ebx, eax
0x180042ca8  test    eax, eax
0x180042caa  jns     short loc_180042CB5
0x180042cac  lea     rdx, aMigratedatawit_5; "MigrateDataWithMount failed to get moun"...
0x180042cb3  jmp     short loc_180042C49
0x180042cb5  lea     r8, [rbp+40h+FileInformation]; lpFileInformation
0x180042cb9  xor     edx, edx; fInfoLevelId
0x180042cbb  mov     rcx, r14; lpFileName
0x180042cbe  call    cs:__imp_GetFileAttributesExW
0x180042cc4  test    eax, eax
0x180042cc6  jz      short loc_180042CE6
0x180042cc8  mov     edi, dword ptr [rbp+40h+var_88+0Ch]
0x180042ccb  lea     rdx, aMigratedatawit; "MigrateDataWithMount winRE File Size Be"...
0x180042cd2  mov     eax, [rbp+40h+var_78]
0x180042cd5  xor     ecx, ecx
0x180042cd7  shl     rdi, 20h
0x180042cdb  or      rdi, rax
0x180042cde  mov     r8, rdi
0x180042ce1  call    UnattendLogW
0x180042ce6  mov     rcx, rdi; unsigned __int64
0x180042ce9  call    ?AsmMigrateDataWithMountStart@@YAX_K@Z; AsmMigrateDataWithMountStart(unsigned __int64)
0x180042cee  cmp     [rbp+40h+arg_40], esi
0x180042cf4  jz      short loc_180042D60
0x180042cf6  lea     rdx, [rsp+140h+var_D8]
0x180042cfb  lea     rcx, [rsp+140h+var_108]
0x180042d00  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@PEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const *)
0x180042d05  mov     rdx, rax
0x180042d08  lea     rcx, [rbp+40h+var_B8]
0x180042d0c  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180042d11  xor     r8d, r8d
0x180042d14  lea     rcx, [rsp+140h+var_108]
0x180042d19  mov     dl, 1
0x180042d1b  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180042d20  lea     rdx, aMigratedatawit_11; "MigrateDataWithMount Clean up the trust"...
0x180042d27  xor     ecx, ecx
0x180042d29  call    UnattendLogW
0x180042d2e  cmp     [rbp+40h+var_A0], 8
0x180042d33  lea     rcx, [rbp+40h+var_B8]
0x180042d37  cmovnb  rcx, [rbp+40h+var_B8]; unsigned __int16 *
0x180042d3c  call    ?winreRemoveTrustedBootApps@@YAKPEBG@Z; winreRemoveTrustedBootApps(ushort const *)
0x180042d41  mov     ebx, eax
0x180042d43  test    eax, eax
0x180042d45  jz      short loc_180042D60
0x180042d47  mov     r8d, eax
0x180042d4a  lea     rdx, aMigratedatawit_3; "MigrateDataWithMount failed to delete t"...
0x180042d51  mov     ecx, 2
0x180042d56  call    UnattendLogW
0x180042d5b  jmp     loc_180042C8B
0x180042d60  test    r15, r15
0x180042d63  jz      short loc_180042D9A
0x180042d65  cmp     [rbp+40h+var_C0], 8
0x180042d6a  lea     rcx, [rsp+140h+var_D8]
0x180042d6f  mov     r9, [rsp+140h+var_E8]; unsigned __int16 *
0x180042d74  mov     r8, r13; unsigned __int16 *
0x180042d77  cmovnb  rcx, [rsp+140h+var_D8]; unsigned __int16 *
0x180042d7d  mov     rdx, r15; unsigned __int16 *
0x180042d80  call    ?pMigrateOemTools@@YAHPEBG000@Z; pMigrateOemTools(ushort const *,ushort const *,ushort const *,ushort const *)
0x180042d85  test    eax, eax
0x180042d87  jnz     short loc_180042DA8
0x180042d89  lea     rdx, aMigratedatawit_0; "MigrateDataWithMount failed to migrate "...
0x180042d90  lea     ecx, [rax+2]
0x180042d93  call    UnattendLogW
0x180042d98  jmp     short loc_180042DA8
0x180042d9a  lea     rdx, aMigratedatawit_6; "MigrateDataWithMount OEM tools migratio"...
0x180042da1  xor     ecx, ecx
0x180042da3  call    UnattendLogW
0x180042da8  cmp     [rbp+40h+arg_38], esi
0x180042dae  jz      short loc_180042DDD
0x180042db0  cmp     [rbp+40h+var_C0], 8
0x180042db5  lea     rcx, [rsp+140h+var_D8]
0x180042dba  cmovnb  rcx, [rsp+140h+var_D8]; unsigned __int16 *
0x180042dc0  call    ?pRemoveSetupFilter@@YAHPEBG@Z; pRemoveSetupFilter(ushort const *)
0x180042dc5  test    eax, eax
0x180042dc7  jnz     short loc_180042DEB
0x180042dc9  lea     rdx, aMigratedatawit_2; "MigrateDataWithMount RemoveSetupFilter "...
0x180042dd0  lea     ecx, [rax+2]
0x180042dd3  call    UnattendLogW
0x180042dd8  jmp     loc_180042ECC
0x180042ddd  lea     rdx, aMigratedatawit_10; "MigrateDataWithMount Remove setup filte"...
0x180042de4  xor     ecx, ecx
0x180042de6  call    UnattendLogW
0x180042deb  test    r12, r12
0x180042dee  jnz     short loc_180042E00
0x180042df0  lea     rdx, aMigratedatawit_13; "MigrateDataWithMount Driver migration n"...
0x180042df7  xor     ecx, ecx
0x180042df9  call    UnattendLogW
0x180042dfe  jmp     short loc_180042E78
0x180042e00  mov     rdx, r12; unsigned __int16 *
0x180042e03  lea     rcx, [rsp+140h+var_E8]; this
0x180042e08  call    ??0DismSessionClass@@QEAA@PEBG@Z; DismSessionClass::DismSessionClass(ushort const *)
0x180042e0d  cmp     [rbp+40h+var_C0], 8
0x180042e12  lea     rdx, [rsp+140h+var_D8]
0x180042e17  lea     rcx, [rsp+140h+var_E0]; this
0x180042e1c  cmovnb  rdx, [rsp+140h+var_D8]; unsigned __int16 *
0x180042e22  call    ??0DismSessionClass@@QEAA@PEBG@Z; DismSessionClass::DismSessionClass(ushort const *)
0x180042e27  mov     r8, [rsp+140h+var_E8]
0x180042e2c  mov     r9, [rsp+140h+var_E0]
0x180042e31  test    r8d, r8d
0x180042e34  js      short loc_180042EA7
0x180042e36  test    r9d, r9d
0x180042e39  js      short loc_180042EA7
0x180042e3b  lea     r8, [rsp+140h+var_118]
0x180042e40  lea     rdx, [rsp+140h+var_E0]
0x180042e45  lea     rcx, [rsp+140h+var_E8]; struct DismSessionClass *
0x180042e4a  call    ?winreMigrateDrivers@@YAHAEAVDismSessionClass@@0AEAV?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@H@Z; winreMigrateDrivers(DismSessionClass &,DismSessionClass &,std::list<std::wstring> &,int)
0x180042e4f  test    eax, eax
0x180042e51  jnz     short loc_180042E64
0x180042e53  lea     rdx, aMigratedatawit_4; "MigrateDataWithMount   winreMigrateDriv"...
0x180042e5a  lea     ecx, [rax+2]
0x180042e5d  call    UnattendLogW
0x180042e62  jmp     short loc_180042EB8
0x180042e64  lea     rcx, [rsp+140h+var_E0]; this
0x180042e69  call    ??1DismSessionClass@@QEAA@XZ; DismSessionClass::~DismSessionClass(void)
0x180042e6e  lea     rcx, [rsp+140h+var_E8]; this
0x180042e73  call    ??1DismSessionClass@@QEAA@XZ; DismSessionClass::~DismSessionClass(void)
0x180042e78  cmp     [rbp+40h+var_47], sil
0x180042e7c  jz      short loc_180042EA0
0x180042e7e  mov     dl, 1; bool
0x180042e80  lea     rcx, [rbp+40h+var_70]; this
0x180042e84  call    ?Unmount@DismMountClass@@QEAAJ_N@Z; DismMountClass::Unmount(bool)
0x180042e89  mov     ebx, eax
0x180042e8b  test    eax, eax
0x180042e8d  jns     short loc_180042EA0
0x180042e8f  lea     rdx, aMigratedatawit_1; "MigrateDataWithMount failed to unmount "...
0x180042e96  mov     ecx, 1
0x180042e9b  jmp     loc_180042C4E
0x180042ea0  mov     esi, 1
0x180042ea5  jmp     short loc_180042ECC
0x180042ea7  lea     rdx, aMigratedatawit_9; "MigrateDataWithMount Source error 0x%x "...
0x180042eae  mov     ecx, 2
0x180042eb3  call    UnattendLogW
0x180042eb8  lea     rcx, [rsp+140h+var_E0]; this
0x180042ebd  call    ??1DismSessionClass@@QEAA@XZ; DismSessionClass::~DismSessionClass(void)
0x180042ec2  lea     rcx, [rsp+140h+var_E8]; this
0x180042ec7  call    ??1DismSessionClass@@QEAA@XZ; DismSessionClass::~DismSessionClass(void)
0x180042ecc  cmp     [rbp+40h+var_47], 0
0x180042ed0  jz      short loc_180042F49
0x180042ed2  lea     rdx, aMigratedatawit_12; "MigrateDataWithMount   Unmount target w"...
0x180042ed9  xor     ecx, ecx
0x180042edb  call    UnattendLogW
0x180042ee0  mov     dl, sil; bool
0x180042ee3  lea     rcx, [rbp+40h+var_70]; this
0x180042ee7  call    ?Unmount@DismMountClass@@QEAAJ_N@Z; DismMountClass::Unmount(bool)
0x180042eec  mov     ebx, eax
0x180042eee  test    eax, eax
0x180042ef0  jns     short loc_180042F49
0x180042ef2  mov     r9d, eax
0x180042ef5  lea     rdx, aMigratedatawit_1; "MigrateDataWithMount failed to unmount "...
0x180042efc  mov     r8, r14
0x180042eff  mov     ecx, 2
0x180042f04  call    UnattendLogW
0x180042f09  test    esi, esi
0x180042f0b  jz      short loc_180042F49
0x180042f0d  bt      ebx, 1Ch
0x180042f11  jnb     short loc_180042F2E
0x180042f13  mov     ecx, ebx; Status
0x180042f15  call    cs:__imp_RtlNtStatusToDosError
0x180042f1b  cmp     eax, 13Dh
0x180042f20  jz      short loc_180042F3F
0x180042f22  mov     ecx, ebx; Status
0x180042f24  call    cs:__imp_RtlNtStatusToDosError
0x180042f2a  mov     ebx, eax
0x180042f2c  jmp     short loc_180042F3F
0x180042f2e  mov     eax, ebx
0x180042f30  and     eax, 1FFF0000h
0x180042f35  cmp     eax, 70000h
0x180042f3a  jnz     short loc_180042F3F
0x180042f3c  movzx   ebx, bx
0x180042f3f  mov     ecx, ebx; dwErrCode
0x180042f41  call    cs:__imp_SetLastError
0x180042f47  xor     esi, esi
0x180042f49  lea     r8, [rbp+40h+FileInformation]; lpFileInformation
0x180042f4d  xor     edx, edx; fInfoLevelId
0x180042f4f  mov     rcx, r14; lpFileName
0x180042f52  call    cs:__imp_GetFileAttributesExW
0x180042f58  test    eax, eax
0x180042f5a  jz      short loc_180042F7A
0x180042f5c  mov     edi, dword ptr [rbp+40h+var_88+0Ch]
0x180042f5f  lea     rdx, aMigratedatawit_7; "MigrateDataWithMount winRE File Size Af"...
0x180042f66  mov     eax, [rbp+40h+var_78]
0x180042f69  xor     ecx, ecx
0x180042f6b  shl     rdi, 20h
0x180042f6f  or      rdi, rax
0x180042f72  mov     r8, rdi
0x180042f75  call    UnattendLogW
0x180042f7a  call    cs:__imp_GetLastError
0x180042f80  mov     r8, rdi; unsigned __int64
0x180042f83  mov     ecx, esi; int
0x180042f85  mov     edx, eax; unsigned int
0x180042f87  call    ?AsmMigrateDataWithMountEnd@@YAXHK_K@Z; AsmMigrateDataWithMountEnd(int,ulong,unsigned __int64)
0x180042f8c  xor     r8d, r8d
0x180042f8f  lea     rcx, [rbp+40h+var_B8]
0x180042f93  mov     dl, 1
0x180042f95  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180042f9a  xor     r8d, r8d
0x180042f9d  lea     rcx, [rsp+140h+var_D8]
0x180042fa2  mov     dl, 1
0x180042fa4  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180042fa9  lea     rcx, [rsp+140h+var_118]
0x180042fae  call    ??1?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::list<std::wstring>::~list<std::wstring>(void)
0x180042fb3  lea     rcx, [rbp+40h+var_70]; this
0x180042fb7  call    ??1DismMountClass@@QEAA@XZ; DismMountClass::~DismMountClass(void)
0x180042fbc  lea     rcx, [rsp+140h+var_120]; this
0x180042fc1  call    ??1DismInitializeClass@@QEAA@XZ; DismInitializeClass::~DismInitializeClass(void)
0x180042fc6  mov     eax, esi
0x180042fc8  mov     rcx, [rbp+40h+var_40]
0x180042fcc  xor     rcx, rsp; StackCookie
0x180042fcf  call    __security_check_cookie
0x180042fd4  mov     rbx, [rsp+140h+arg_8]
0x180042fdc  add     rsp, 110h
0x180042fe3  pop     r15
0x180042fe5  pop     r14
0x180042fe7  pop     r13
0x180042fe9  pop     r12
  ... truncated ...
```
