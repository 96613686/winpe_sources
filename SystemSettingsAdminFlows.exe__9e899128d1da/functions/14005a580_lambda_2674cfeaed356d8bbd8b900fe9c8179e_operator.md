# _lambda_2674cfeaed356d8bbd8b900fe9c8179e_::operator()

- ea: `0x14005a580`
- end: `0x14005a6a2`
- name: `_lambda_2674cfeaed356d8bbd8b900fe9c8179e_::operator()`
- size: `290`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14005c234`

## callees

- `0x14001f3d4`
- `0x140057a50`
- `0x1400598e0`
- `0x14005a580`
- `0x14005be78`
- `0x14007d010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x14005a689`
- `KERNEL32!LocalFree` at `0x14005a689`
- `KERNEL32!GetLastError` at `0x14005a5b2`
- `KERNEL32!GetLastError` at `0x14005a5b2`
- `SHELL32!CommandLineToArgvW` at `0x14005a5a4`
- `SHELL32!CommandLineToArgvW` at `0x14005a5a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14005a678`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14005a678`

## pseudocode

```c
__int64 __fastcall lambda_2674cfeaed356d8bbd8b900fe9c8179e_::operator()(LPCWSTR **a1)
{
  LPCWSTR *v1; // rcx
  LPWSTR *v2; // rax
  LPWSTR *v3; // rdi
  signed int LastError; // eax
  unsigned int v5; // ebx
  int StorageAdminHelper; // eax
  __int64 v7; // rdx
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+18h]
  int pNumArgs; // [rsp+40h] [rbp+20h] BYREF
  HSTRING string; // [rsp+48h] [rbp+28h] BYREF
  __int64 v13; // [rsp+50h] [rbp+30h] BYREF

  v1 = *a1;
  v13 = 0;
  pNumArgs = 0;
  v2 = CommandLineToArgvW(*v1, &pNumArgs);
  v3 = v2;
  if ( v2 )
  {
    if ( pNumArgs < 1 )
    {
      v5 = -2147316575;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x157,
        (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\storage\\storageadminhelper\\storageadminops.cpp",
        (const char *)0x80028CA1LL,
        savedregs);
LABEL_15:
      LocalFree(v3);
      goto LABEL_16;
    }
    string = 0;
    StorageAdminHelper = Microsoft::WRL::Wrappers::HString::Set<unsigned short *>(&string, v2);
    v5 = StorageAdminHelper;
    if ( StorageAdminHelper >= 0 )
    {
      StorageAdminHelper = StorageAdminOps::CreateStorageAdminHelper((__int64)&v13);
      v5 = StorageAdminHelper;
      if ( StorageAdminHelper >= 0 )
      {
        v5 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v13 + 136LL))(v13, string);
        goto LABEL_14;
      }
      v7 = 348;
    }
    else
    {
      v7 = 345;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\storage\\storageadminhelper\\storageadminops.cpp",
      (const char *)(unsigned int)StorageAdminHelper,
      savedregs);
LABEL_14:
    WindowsDeleteString(string);
    string = 0;
    goto LABEL_15;
  }
  LastError = GetLastError();
  v5 = LastError;
  if ( LastError > 0 )
    v5 = (unsigned __int16)LastError | 0x80070000;
  if ( (v5 & 0x80000000) != 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x156,
      (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\storage\\storageadminhelper\\storageadminops.cpp",
      (const char *)v5,
      savedregs);
LABEL_16:
  Microsoft::WRL::ComPtr<ICbsSession9>::InternalRelease(&v13);
  return v5;
}

```

## disassembly

```asm
0x14005a580  push    rbp
0x14005a582  push    rbx
0x14005a583  push    rdi; int
0x14005a584  mov     rbp, rsp
0x14005a587  sub     rsp, 20h
0x14005a58b  mov     rcx, [rcx]
0x14005a58e  lea     rdx, [rbp+pNumArgs]; pNumArgs
0x14005a592  mov     [rbp+arg_10], 0
0x14005a59a  mov     [rbp+pNumArgs], 0
0x14005a5a1  mov     rcx, [rcx]; lpCmdLine
0x14005a5a4  call    cs:__imp_CommandLineToArgvW
0x14005a5aa  mov     rdi, rax
0x14005a5ad  test    rax, rax
0x14005a5b0  jnz     short loc_14005A5EC
0x14005a5b2  call    cs:__imp_GetLastError
0x14005a5b8  mov     ebx, eax
0x14005a5ba  test    eax, eax
0x14005a5bc  jle     short loc_14005A5C7
0x14005a5be  movzx   ebx, ax
0x14005a5c1  or      ebx, 80070000h
0x14005a5c7  test    ebx, ebx
0x14005a5c9  jns     loc_14005A68F
0x14005a5cf  mov     rcx, [rbp+18h]; this
0x14005a5d3  lea     r8, aPcshellShellSy_8; "pcshell\\shell\\systemsettings\\adminfl"...
0x14005a5da  mov     r9d, ebx; char *
0x14005a5dd  mov     edx, 156h; void *
0x14005a5e2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14005a5e7  jmp     loc_14005A68F
0x14005a5ec  cmp     [rbp+pNumArgs], 1
0x14005a5f0  jge     short loc_14005A611
0x14005a5f2  mov     rcx, [rbp+18h]; this
0x14005a5f6  lea     r8, aPcshellShellSy_8; "pcshell\\shell\\systemsettings\\adminfl"...
0x14005a5fd  mov     ebx, 80028CA1h
0x14005a602  mov     edx, 157h; void *
0x14005a607  mov     r9d, ebx; char *
0x14005a60a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14005a60f  jmp     short loc_14005A686
0x14005a611  mov     rdx, rdi
0x14005a614  mov     [rbp+string], 0
0x14005a61c  lea     rcx, [rbp+string]
0x14005a620  call    ??$Set@PEAG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort *>(ushort * const &,Microsoft::WRL::Details::Dummy)
0x14005a625  mov     ebx, eax
0x14005a627  test    eax, eax
0x14005a629  jns     short loc_14005A645
0x14005a62b  mov     edx, 159h; void *
0x14005a630  mov     rcx, [rbp+18h]; this
0x14005a634  lea     r8, aPcshellShellSy_8; "pcshell\\shell\\systemsettings\\adminfl"...
0x14005a63b  mov     r9d, eax; char *
0x14005a63e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14005a643  jmp     short loc_14005A674
0x14005a645  lea     rcx, [rbp+arg_10]
0x14005a649  call    ?CreateStorageAdminHelper@StorageAdminOps@@SAJAEAV?$ComPtr@UIStorageAdminHelperImpl@StorageHandlers@@@WRL@Microsoft@@@Z; StorageAdminOps::CreateStorageAdminHelper(Microsoft::WRL::ComPtr<StorageHandlers::IStorageAdminHelperImpl> &)
0x14005a64e  mov     ebx, eax
0x14005a650  test    eax, eax
0x14005a652  jns     short loc_14005A65B
0x14005a654  mov     edx, 15Ch
0x14005a659  jmp     short loc_14005A630
0x14005a65b  mov     rcx, [rbp+arg_10]
0x14005a65f  mov     rdx, [rbp+string]
0x14005a663  mov     rax, [rcx]
0x14005a666  mov     rax, [rax+88h]
0x14005a66d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005a672  mov     ebx, eax
0x14005a674  mov     rcx, [rbp+string]; string
0x14005a678  call    cs:__imp_WindowsDeleteString
0x14005a67e  mov     [rbp+string], 0
0x14005a686  mov     rcx, rdi; hMem
0x14005a689  call    cs:__imp_LocalFree
0x14005a68f  lea     rcx, [rbp+arg_10]
0x14005a693  call    ?InternalRelease@?$ComPtr@UICbsSession9@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICbsSession9>::InternalRelease(void)
0x14005a698  mov     eax, ebx
0x14005a69a  add     rsp, 20h
0x14005a69e  pop     rdi
0x14005a69f  pop     rbx
0x14005a6a0  pop     rbp
0x14005a6a1  retn
```
