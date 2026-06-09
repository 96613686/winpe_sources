# _lambda_8ac2dc41bc5b40e4470f18e1dfd627c4_::operator()

- ea: `0x14005ae28`
- end: `0x14005af4a`
- name: `_lambda_8ac2dc41bc5b40e4470f18e1dfd627c4_::operator()`
- size: `290`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14005c654`

## callees

- `0x14001f3d4`
- `0x140057a50`
- `0x1400598e0`
- `0x14005ae28`
- `0x14005be78`
- `0x14007d010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x14005af31`
- `KERNEL32!LocalFree` at `0x14005af31`
- `KERNEL32!GetLastError` at `0x14005ae5a`
- `KERNEL32!GetLastError` at `0x14005ae5a`
- `SHELL32!CommandLineToArgvW` at `0x14005ae4c`
- `SHELL32!CommandLineToArgvW` at `0x14005ae4c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14005af20`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14005af20`

## pseudocode

```c
__int64 __fastcall lambda_8ac2dc41bc5b40e4470f18e1dfd627c4_::operator()(LPCWSTR **a1)
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
        (void *)0x195,
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
        v5 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v13 + 152LL))(v13, string);
        goto LABEL_14;
      }
      v7 = 410;
    }
    else
    {
      v7 = 407;
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
      (void *)0x194,
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
0x14005ae28  push    rbp
0x14005ae2a  push    rbx
0x14005ae2b  push    rdi; int
0x14005ae2c  mov     rbp, rsp
0x14005ae2f  sub     rsp, 20h
0x14005ae33  mov     rcx, [rcx]
0x14005ae36  lea     rdx, [rbp+pNumArgs]; pNumArgs
0x14005ae3a  mov     [rbp+arg_10], 0
0x14005ae42  mov     [rbp+pNumArgs], 0
0x14005ae49  mov     rcx, [rcx]; lpCmdLine
0x14005ae4c  call    cs:__imp_CommandLineToArgvW
0x14005ae52  mov     rdi, rax
0x14005ae55  test    rax, rax
0x14005ae58  jnz     short loc_14005AE94
0x14005ae5a  call    cs:__imp_GetLastError
0x14005ae60  mov     ebx, eax
0x14005ae62  test    eax, eax
0x14005ae64  jle     short loc_14005AE6F
0x14005ae66  movzx   ebx, ax
0x14005ae69  or      ebx, 80070000h
0x14005ae6f  test    ebx, ebx
0x14005ae71  jns     loc_14005AF37
0x14005ae77  mov     rcx, [rbp+18h]; this
0x14005ae7b  lea     r8, aPcshellShellSy_8; "pcshell\\shell\\systemsettings\\adminfl"...
0x14005ae82  mov     r9d, ebx; char *
0x14005ae85  mov     edx, 194h; void *
0x14005ae8a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14005ae8f  jmp     loc_14005AF37
0x14005ae94  cmp     [rbp+pNumArgs], 1
0x14005ae98  jge     short loc_14005AEB9
0x14005ae9a  mov     rcx, [rbp+18h]; this
0x14005ae9e  lea     r8, aPcshellShellSy_8; "pcshell\\shell\\systemsettings\\adminfl"...
0x14005aea5  mov     ebx, 80028CA1h
0x14005aeaa  mov     edx, 195h; void *
0x14005aeaf  mov     r9d, ebx; char *
0x14005aeb2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14005aeb7  jmp     short loc_14005AF2E
0x14005aeb9  mov     rdx, rdi
0x14005aebc  mov     [rbp+string], 0
0x14005aec4  lea     rcx, [rbp+string]
0x14005aec8  call    ??$Set@PEAG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort *>(ushort * const &,Microsoft::WRL::Details::Dummy)
0x14005aecd  mov     ebx, eax
0x14005aecf  test    eax, eax
0x14005aed1  jns     short loc_14005AEED
0x14005aed3  mov     edx, 197h; void *
0x14005aed8  mov     rcx, [rbp+18h]; this
0x14005aedc  lea     r8, aPcshellShellSy_8; "pcshell\\shell\\systemsettings\\adminfl"...
0x14005aee3  mov     r9d, eax; char *
0x14005aee6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14005aeeb  jmp     short loc_14005AF1C
0x14005aeed  lea     rcx, [rbp+arg_10]
0x14005aef1  call    ?CreateStorageAdminHelper@StorageAdminOps@@SAJAEAV?$ComPtr@UIStorageAdminHelperImpl@StorageHandlers@@@WRL@Microsoft@@@Z; StorageAdminOps::CreateStorageAdminHelper(Microsoft::WRL::ComPtr<StorageHandlers::IStorageAdminHelperImpl> &)
0x14005aef6  mov     ebx, eax
0x14005aef8  test    eax, eax
0x14005aefa  jns     short loc_14005AF03
0x14005aefc  mov     edx, 19Ah
0x14005af01  jmp     short loc_14005AED8
0x14005af03  mov     rcx, [rbp+arg_10]
0x14005af07  mov     rdx, [rbp+string]
0x14005af0b  mov     rax, [rcx]
0x14005af0e  mov     rax, [rax+98h]
0x14005af15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005af1a  mov     ebx, eax
0x14005af1c  mov     rcx, [rbp+string]; string
0x14005af20  call    cs:__imp_WindowsDeleteString
0x14005af26  mov     [rbp+string], 0
0x14005af2e  mov     rcx, rdi; hMem
0x14005af31  call    cs:__imp_LocalFree
0x14005af37  lea     rcx, [rbp+arg_10]
0x14005af3b  call    ?InternalRelease@?$ComPtr@UICbsSession9@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICbsSession9>::InternalRelease(void)
0x14005af40  mov     eax, ebx
0x14005af42  add     rsp, 20h
0x14005af46  pop     rdi
0x14005af47  pop     rbx
0x14005af48  pop     rbp
0x14005af49  retn
```
