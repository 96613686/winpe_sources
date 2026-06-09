# _lambda_f5d14f1fb5a3e912db018d0f26085a6c_::operator()

- ea: `0x14005bba0`
- end: `0x14005bd26`
- name: `_lambda_f5d14f1fb5a3e912db018d0f26085a6c_::operator()`
- size: `390`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14005c294`

## callees

- `0x14001f3d4`
- `0x140057a50`
- `0x1400598e0`
- `0x14005bba0`
- `0x14005be78`
- `0x14005c130`
- `0x14007d010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x14005bd0c`
- `KERNEL32!LocalFree` at `0x14005bd0c`
- `KERNEL32!GetLastError` at `0x14005bbcd`
- `KERNEL32!GetLastError` at `0x14005bbcd`
- `SHELL32!CommandLineToArgvW` at `0x14005bbbf`
- `SHELL32!CommandLineToArgvW` at `0x14005bbbf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14005bce3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14005bcf1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14005bcff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14005bce3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14005bcf1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14005bcff`

## pseudocode

```c
__int64 __fastcall lambda_f5d14f1fb5a3e912db018d0f26085a6c_::operator()(LPCWSTR **a1)
{
  LPCWSTR *v1; // rcx
  LPWSTR *v2; // rax
  LPWSTR *v3; // rdi
  signed int LastError; // eax
  unsigned int v5; // ebx
  int StorageAdminHelper; // eax
  __int64 v7; // rdx
  int v9; // [rsp+20h] [rbp-28h]
  __int64 v10; // [rsp+30h] [rbp-18h] BYREF
  __int64 fixed; // [rsp+38h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+20h]
  int pNumArgs; // [rsp+70h] [rbp+28h] BYREF
  HSTRING string; // [rsp+78h] [rbp+30h] BYREF
  HSTRING v15; // [rsp+80h] [rbp+38h] BYREF
  HSTRING v16; // [rsp+88h] [rbp+40h] BYREF

  v1 = *a1;
  v10 = 0;
  pNumArgs = 0;
  v2 = CommandLineToArgvW(*v1, &pNumArgs);
  v3 = v2;
  if ( v2 )
  {
    if ( pNumArgs < 3 )
    {
      v5 = -2147316575;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x111,
        (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\storage\\storageadminhelper\\storageadminops.cpp",
        (const char *)0x80028CA1LL,
        v9);
LABEL_19:
      LocalFree(v3);
      goto LABEL_20;
    }
    v16 = 0;
    v15 = 0;
    string = 0;
    StorageAdminHelper = Microsoft::WRL::Wrappers::HString::Set<unsigned short *>(&v16, v2);
    v5 = StorageAdminHelper;
    if ( StorageAdminHelper >= 0 )
    {
      StorageAdminHelper = Microsoft::WRL::Wrappers::HString::Set<unsigned short *>(&v15, v3 + 1);
      v5 = StorageAdminHelper;
      if ( StorageAdminHelper >= 0 )
      {
        fixed = FixTrailingBackslashMarker(v3[2]);
        StorageAdminHelper = Microsoft::WRL::Wrappers::HString::Set<unsigned short *>(&string, &fixed);
        v5 = StorageAdminHelper;
        if ( StorageAdminHelper >= 0 )
        {
          StorageAdminHelper = StorageAdminOps::CreateStorageAdminHelper((__int64)&v10);
          v5 = StorageAdminHelper;
          if ( StorageAdminHelper >= 0 )
          {
            v5 = (*(__int64 (__fastcall **)(__int64, HSTRING, HSTRING, HSTRING))(*(_QWORD *)v10 + 160LL))(
                   v10,
                   v16,
                   v15,
                   string);
            goto LABEL_18;
          }
          v7 = 282;
        }
        else
        {
          v7 = 279;
        }
      }
      else
      {
        v7 = 278;
      }
    }
    else
    {
      v7 = 277;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\storage\\storageadminhelper\\storageadminops.cpp",
      (const char *)(unsigned int)StorageAdminHelper,
      v9);
LABEL_18:
    WindowsDeleteString(string);
    string = 0;
    WindowsDeleteString(v15);
    v15 = 0;
    WindowsDeleteString(v16);
    v16 = 0;
    goto LABEL_19;
  }
  LastError = GetLastError();
  v5 = LastError;
  if ( LastError > 0 )
    v5 = (unsigned __int16)LastError | 0x80070000;
  if ( (v5 & 0x80000000) != 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x110,
      (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\storage\\storageadminhelper\\storageadminops.cpp",
      (const char *)v5,
      v9);
LABEL_20:
  Microsoft::WRL::ComPtr<ICbsSession9>::InternalRelease(&v10);
  return v5;
}

```

## disassembly

```asm
0x14005bba0  push    rbp
0x14005bba2  push    rbx
0x14005bba3  push    rsi
0x14005bba4  push    rdi
0x14005bba5  mov     rbp, rsp
0x14005bba8  sub     rsp, 48h
0x14005bbac  mov     rcx, [rcx]
0x14005bbaf  lea     rdx, [rbp+pNumArgs]; pNumArgs
0x14005bbb3  xor     esi, esi
0x14005bbb5  mov     [rbp+var_18], rsi
0x14005bbb9  mov     [rbp+pNumArgs], esi
0x14005bbbc  mov     rcx, [rcx]; lpCmdLine
0x14005bbbf  call    cs:__imp_CommandLineToArgvW
0x14005bbc5  mov     rdi, rax
0x14005bbc8  test    rax, rax
0x14005bbcb  jnz     short loc_14005BC07
0x14005bbcd  call    cs:__imp_GetLastError
0x14005bbd3  mov     ebx, eax
0x14005bbd5  test    eax, eax
0x14005bbd7  jle     short loc_14005BBE2
0x14005bbd9  movzx   ebx, ax
0x14005bbdc  or      ebx, 80070000h
0x14005bbe2  test    ebx, ebx
0x14005bbe4  jns     loc_14005BD12
0x14005bbea  mov     rcx, [rbp+20h]; this
0x14005bbee  lea     r8, aPcshellShellSy_8; "pcshell\\shell\\systemsettings\\adminfl"...
0x14005bbf5  mov     r9d, ebx; char *
0x14005bbf8  mov     edx, 110h; void *
0x14005bbfd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14005bc02  jmp     loc_14005BD12
0x14005bc07  cmp     [rbp+pNumArgs], 3
0x14005bc0b  jge     short loc_14005BC2F
0x14005bc0d  mov     rcx, [rbp+20h]; this
0x14005bc11  lea     r8, aPcshellShellSy_8; "pcshell\\shell\\systemsettings\\adminfl"...
0x14005bc18  mov     ebx, 80028CA1h
0x14005bc1d  mov     edx, 111h; void *
0x14005bc22  mov     r9d, ebx; char *
0x14005bc25  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14005bc2a  jmp     loc_14005BD09
0x14005bc2f  mov     rdx, rdi
0x14005bc32  mov     [rbp+arg_18], rsi
0x14005bc36  lea     rcx, [rbp+arg_18]
0x14005bc3a  mov     [rbp+arg_10], rsi
0x14005bc3e  mov     [rbp+string], rsi
0x14005bc42  call    ??$Set@PEAG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort *>(ushort * const &,Microsoft::WRL::Details::Dummy)
0x14005bc47  mov     ebx, eax
0x14005bc49  test    eax, eax
0x14005bc4b  jns     short loc_14005BC67
0x14005bc4d  mov     edx, 115h; void *
0x14005bc52  mov     rcx, [rbp+20h]; this
0x14005bc56  lea     r8, aPcshellShellSy_8; "pcshell\\shell\\systemsettings\\adminfl"...
0x14005bc5d  mov     r9d, eax; char *
0x14005bc60  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14005bc65  jmp     short loc_14005BCDF
0x14005bc67  lea     rdx, [rdi+8]
0x14005bc6b  lea     rcx, [rbp+arg_10]
0x14005bc6f  call    ??$Set@PEAG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort *>(ushort * const &,Microsoft::WRL::Details::Dummy)
0x14005bc74  mov     ebx, eax
0x14005bc76  test    eax, eax
0x14005bc78  jns     short loc_14005BC81
0x14005bc7a  mov     edx, 116h
0x14005bc7f  jmp     short loc_14005BC52
0x14005bc81  mov     rcx, [rdi+10h]
0x14005bc85  call    FixTrailingBackslashMarker
0x14005bc8a  lea     rdx, [rbp+var_10]
0x14005bc8e  mov     [rbp+var_10], rax
0x14005bc92  lea     rcx, [rbp+string]
0x14005bc96  call    ??$Set@PEAG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort *>(ushort * const &,Microsoft::WRL::Details::Dummy)
0x14005bc9b  mov     ebx, eax
0x14005bc9d  test    eax, eax
0x14005bc9f  jns     short loc_14005BCA8
0x14005bca1  mov     edx, 117h
0x14005bca6  jmp     short loc_14005BC52
0x14005bca8  lea     rcx, [rbp+var_18]
0x14005bcac  call    ?CreateStorageAdminHelper@StorageAdminOps@@SAJAEAV?$ComPtr@UIStorageAdminHelperImpl@StorageHandlers@@@WRL@Microsoft@@@Z; StorageAdminOps::CreateStorageAdminHelper(Microsoft::WRL::ComPtr<StorageHandlers::IStorageAdminHelperImpl> &)
0x14005bcb1  mov     ebx, eax
0x14005bcb3  test    eax, eax
0x14005bcb5  jns     short loc_14005BCBE
0x14005bcb7  mov     edx, 11Ah
0x14005bcbc  jmp     short loc_14005BC52
0x14005bcbe  mov     rcx, [rbp+var_18]
0x14005bcc2  mov     r9, [rbp+string]
0x14005bcc6  mov     r8, [rbp+arg_10]
0x14005bcca  mov     rdx, [rbp+arg_18]
0x14005bcce  mov     rax, [rcx]
0x14005bcd1  mov     rax, [rax+0A0h]
0x14005bcd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005bcdd  mov     ebx, eax
0x14005bcdf  mov     rcx, [rbp+string]; string
0x14005bce3  call    cs:__imp_WindowsDeleteString
0x14005bce9  mov     rcx, [rbp+arg_10]; string
0x14005bced  mov     [rbp+string], rsi
0x14005bcf1  call    cs:__imp_WindowsDeleteString
0x14005bcf7  mov     rcx, [rbp+arg_18]; string
0x14005bcfb  mov     [rbp+arg_10], rsi
0x14005bcff  call    cs:__imp_WindowsDeleteString
0x14005bd05  mov     [rbp+arg_18], rsi
0x14005bd09  mov     rcx, rdi; hMem
0x14005bd0c  call    cs:__imp_LocalFree
0x14005bd12  lea     rcx, [rbp+var_18]
0x14005bd16  call    ?InternalRelease@?$ComPtr@UICbsSession9@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICbsSession9>::InternalRelease(void)
0x14005bd1b  mov     eax, ebx
0x14005bd1d  add     rsp, 48h
0x14005bd21  pop     rdi
0x14005bd22  pop     rsi
0x14005bd23  pop     rbx
0x14005bd24  pop     rbp
0x14005bd25  retn
```
