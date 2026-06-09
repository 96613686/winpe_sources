# _lambda_aebfdf0e950c8b7c14ecf7abb4892b1b_::operator()

- ea: `0x14005b20c`
- end: `0x14005b38f`
- name: `_lambda_aebfdf0e950c8b7c14ecf7abb4892b1b_::operator()`
- size: `387`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14005c354`

## callees

- `0x14001f3d4`
- `0x140057a50`
- `0x1400598e0`
- `0x14005b20c`
- `0x14005be78`
- `0x14005c130`
- `0x14007d010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x14005b375`
- `KERNEL32!LocalFree` at `0x14005b375`
- `KERNEL32!GetLastError` at `0x14005b239`
- `KERNEL32!GetLastError` at `0x14005b239`
- `SHELL32!CommandLineToArgvW` at `0x14005b22b`
- `SHELL32!CommandLineToArgvW` at `0x14005b22b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14005b34c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14005b35a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14005b368`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14005b34c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14005b35a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14005b368`

## pseudocode

```c
__int64 __fastcall lambda_aebfdf0e950c8b7c14ecf7abb4892b1b_::operator()(LPCWSTR **a1)
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
        (void *)0x134,
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
            v5 = (*(__int64 (__fastcall **)(__int64, HSTRING, HSTRING, HSTRING))(*(_QWORD *)v10 + 120LL))(
                   v10,
                   v16,
                   v15,
                   string);
            goto LABEL_18;
          }
          v7 = 317;
        }
        else
        {
          v7 = 314;
        }
      }
      else
      {
        v7 = 313;
      }
    }
    else
    {
      v7 = 312;
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
      (void *)0x133,
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
0x14005b20c  push    rbp
0x14005b20e  push    rbx
0x14005b20f  push    rsi
0x14005b210  push    rdi
0x14005b211  mov     rbp, rsp
0x14005b214  sub     rsp, 48h
0x14005b218  mov     rcx, [rcx]
0x14005b21b  lea     rdx, [rbp+pNumArgs]; pNumArgs
0x14005b21f  xor     esi, esi
0x14005b221  mov     [rbp+var_18], rsi
0x14005b225  mov     [rbp+pNumArgs], esi
0x14005b228  mov     rcx, [rcx]; lpCmdLine
0x14005b22b  call    cs:__imp_CommandLineToArgvW
0x14005b231  mov     rdi, rax
0x14005b234  test    rax, rax
0x14005b237  jnz     short loc_14005B273
0x14005b239  call    cs:__imp_GetLastError
0x14005b23f  mov     ebx, eax
0x14005b241  test    eax, eax
0x14005b243  jle     short loc_14005B24E
0x14005b245  movzx   ebx, ax
0x14005b248  or      ebx, 80070000h
0x14005b24e  test    ebx, ebx
0x14005b250  jns     loc_14005B37B
0x14005b256  mov     rcx, [rbp+20h]; this
0x14005b25a  lea     r8, aPcshellShellSy_8; "pcshell\\shell\\systemsettings\\adminfl"...
0x14005b261  mov     r9d, ebx; char *
0x14005b264  mov     edx, 133h; void *
0x14005b269  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14005b26e  jmp     loc_14005B37B
0x14005b273  cmp     [rbp+pNumArgs], 3
0x14005b277  jge     short loc_14005B29B
0x14005b279  mov     rcx, [rbp+20h]; this
0x14005b27d  lea     r8, aPcshellShellSy_8; "pcshell\\shell\\systemsettings\\adminfl"...
0x14005b284  mov     ebx, 80028CA1h
0x14005b289  mov     edx, 134h; void *
0x14005b28e  mov     r9d, ebx; char *
0x14005b291  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14005b296  jmp     loc_14005B372
0x14005b29b  mov     rdx, rdi
0x14005b29e  mov     [rbp+arg_18], rsi
0x14005b2a2  lea     rcx, [rbp+arg_18]
0x14005b2a6  mov     [rbp+arg_10], rsi
0x14005b2aa  mov     [rbp+string], rsi
0x14005b2ae  call    ??$Set@PEAG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort *>(ushort * const &,Microsoft::WRL::Details::Dummy)
0x14005b2b3  mov     ebx, eax
0x14005b2b5  test    eax, eax
0x14005b2b7  jns     short loc_14005B2D3
0x14005b2b9  mov     edx, 138h; void *
0x14005b2be  mov     rcx, [rbp+20h]; this
0x14005b2c2  lea     r8, aPcshellShellSy_8; "pcshell\\shell\\systemsettings\\adminfl"...
0x14005b2c9  mov     r9d, eax; char *
0x14005b2cc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14005b2d1  jmp     short loc_14005B348
0x14005b2d3  lea     rdx, [rdi+8]
0x14005b2d7  lea     rcx, [rbp+arg_10]
0x14005b2db  call    ??$Set@PEAG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort *>(ushort * const &,Microsoft::WRL::Details::Dummy)
0x14005b2e0  mov     ebx, eax
0x14005b2e2  test    eax, eax
0x14005b2e4  jns     short loc_14005B2ED
0x14005b2e6  mov     edx, 139h
0x14005b2eb  jmp     short loc_14005B2BE
0x14005b2ed  mov     rcx, [rdi+10h]
0x14005b2f1  call    FixTrailingBackslashMarker
0x14005b2f6  lea     rdx, [rbp+var_10]
0x14005b2fa  mov     [rbp+var_10], rax
0x14005b2fe  lea     rcx, [rbp+string]
0x14005b302  call    ??$Set@PEAG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort *>(ushort * const &,Microsoft::WRL::Details::Dummy)
0x14005b307  mov     ebx, eax
0x14005b309  test    eax, eax
0x14005b30b  jns     short loc_14005B314
0x14005b30d  mov     edx, 13Ah
0x14005b312  jmp     short loc_14005B2BE
0x14005b314  lea     rcx, [rbp+var_18]
0x14005b318  call    ?CreateStorageAdminHelper@StorageAdminOps@@SAJAEAV?$ComPtr@UIStorageAdminHelperImpl@StorageHandlers@@@WRL@Microsoft@@@Z; StorageAdminOps::CreateStorageAdminHelper(Microsoft::WRL::ComPtr<StorageHandlers::IStorageAdminHelperImpl> &)
0x14005b31d  mov     ebx, eax
0x14005b31f  test    eax, eax
0x14005b321  jns     short loc_14005B32A
0x14005b323  mov     edx, 13Dh
0x14005b328  jmp     short loc_14005B2BE
0x14005b32a  mov     rcx, [rbp+var_18]
0x14005b32e  mov     r9, [rbp+string]
0x14005b332  mov     r8, [rbp+arg_10]
0x14005b336  mov     rdx, [rbp+arg_18]
0x14005b33a  mov     rax, [rcx]
0x14005b33d  mov     rax, [rax+78h]
0x14005b341  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005b346  mov     ebx, eax
0x14005b348  mov     rcx, [rbp+string]; string
0x14005b34c  call    cs:__imp_WindowsDeleteString
0x14005b352  mov     rcx, [rbp+arg_10]; string
0x14005b356  mov     [rbp+string], rsi
0x14005b35a  call    cs:__imp_WindowsDeleteString
0x14005b360  mov     rcx, [rbp+arg_18]; string
0x14005b364  mov     [rbp+arg_10], rsi
0x14005b368  call    cs:__imp_WindowsDeleteString
0x14005b36e  mov     [rbp+arg_18], rsi
0x14005b372  mov     rcx, rdi; hMem
0x14005b375  call    cs:__imp_LocalFree
0x14005b37b  lea     rcx, [rbp+var_18]
0x14005b37f  call    ?InternalRelease@?$ComPtr@UICbsSession9@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICbsSession9>::InternalRelease(void)
0x14005b384  mov     eax, ebx
0x14005b386  add     rsp, 48h
0x14005b38a  pop     rdi
0x14005b38b  pop     rsi
0x14005b38c  pop     rbx
0x14005b38d  pop     rbp
0x14005b38e  retn
```
