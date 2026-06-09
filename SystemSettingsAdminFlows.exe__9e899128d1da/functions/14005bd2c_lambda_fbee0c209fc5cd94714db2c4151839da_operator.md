# _lambda_fbee0c209fc5cd94714db2c4151839da_::operator()

- ea: `0x14005bd2c`
- end: `0x14005be72`
- name: `_lambda_fbee0c209fc5cd94714db2c4151839da_::operator()`
- size: `326`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14005bf48`

## callees

- `0x14001f3d4`
- `0x140057a50`
- `0x1400598e0`
- `0x14005bd2c`
- `0x14005be78`
- `0x14007d010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x14005be58`
- `KERNEL32!LocalFree` at `0x14005be58`
- `KERNEL32!GetLastError` at `0x14005bd59`
- `KERNEL32!GetLastError` at `0x14005bd59`
- `SHELL32!CommandLineToArgvW` at `0x14005bd4b`
- `SHELL32!CommandLineToArgvW` at `0x14005bd4b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14005be3d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14005be4b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14005be3d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14005be4b`

## pseudocode

```c
__int64 __fastcall lambda_fbee0c209fc5cd94714db2c4151839da_::operator()(LPCWSTR **a1)
{
  LPCWSTR *v1; // rcx
  LPWSTR *v2; // rax
  LPWSTR *v3; // rdi
  signed int LastError; // eax
  unsigned int v5; // ebx
  int StorageAdminHelper; // eax
  __int64 v7; // rdx
  int v9; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+20h]
  int pNumArgs; // [rsp+50h] [rbp+28h] BYREF
  HSTRING string; // [rsp+58h] [rbp+30h] BYREF
  HSTRING v13; // [rsp+60h] [rbp+38h] BYREF
  __int64 v14; // [rsp+68h] [rbp+40h] BYREF

  v1 = *a1;
  v14 = 0;
  pNumArgs = 0;
  v2 = CommandLineToArgvW(*v1, &pNumArgs);
  v3 = v2;
  if ( v2 )
  {
    if ( pNumArgs < 2 )
    {
      v5 = -2147316575;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xCF,
        (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\storage\\storageadminhelper\\storageadminops.cpp",
        (const char *)0x80028CA1LL,
        v9);
LABEL_17:
      LocalFree(v3);
      goto LABEL_18;
    }
    v13 = 0;
    string = 0;
    StorageAdminHelper = Microsoft::WRL::Wrappers::HString::Set<unsigned short *>(&v13, v2);
    v5 = StorageAdminHelper;
    if ( StorageAdminHelper >= 0 )
    {
      StorageAdminHelper = Microsoft::WRL::Wrappers::HString::Set<unsigned short *>(&string, v3 + 1);
      v5 = StorageAdminHelper;
      if ( StorageAdminHelper >= 0 )
      {
        StorageAdminHelper = StorageAdminOps::CreateStorageAdminHelper((__int64)&v14);
        v5 = StorageAdminHelper;
        if ( StorageAdminHelper >= 0 )
        {
          v5 = (*(__int64 (__fastcall **)(__int64, HSTRING, HSTRING))(*(_QWORD *)v14 + 104LL))(v14, v13, string);
          goto LABEL_16;
        }
        v7 = 214;
      }
      else
      {
        v7 = 211;
      }
    }
    else
    {
      v7 = 210;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\storage\\storageadminhelper\\storageadminops.cpp",
      (const char *)(unsigned int)StorageAdminHelper,
      v9);
LABEL_16:
    WindowsDeleteString(string);
    string = 0;
    WindowsDeleteString(v13);
    v13 = 0;
    goto LABEL_17;
  }
  LastError = GetLastError();
  v5 = LastError;
  if ( LastError > 0 )
    v5 = (unsigned __int16)LastError | 0x80070000;
  if ( (v5 & 0x80000000) != 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCE,
      (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\storage\\storageadminhelper\\storageadminops.cpp",
      (const char *)v5,
      v9);
LABEL_18:
  Microsoft::WRL::ComPtr<ICbsSession9>::InternalRelease(&v14);
  return v5;
}

```

## disassembly

```asm
0x14005bd2c  push    rbp
0x14005bd2e  push    rbx
0x14005bd2f  push    rsi
0x14005bd30  push    rdi
0x14005bd31  mov     rbp, rsp
0x14005bd34  sub     rsp, 28h
0x14005bd38  mov     rcx, [rcx]
0x14005bd3b  lea     rdx, [rbp+pNumArgs]; pNumArgs
0x14005bd3f  xor     esi, esi
0x14005bd41  mov     [rbp+arg_18], rsi
0x14005bd45  mov     [rbp+pNumArgs], esi
0x14005bd48  mov     rcx, [rcx]; lpCmdLine
0x14005bd4b  call    cs:__imp_CommandLineToArgvW
0x14005bd51  mov     rdi, rax
0x14005bd54  test    rax, rax
0x14005bd57  jnz     short loc_14005BD93
0x14005bd59  call    cs:__imp_GetLastError
0x14005bd5f  mov     ebx, eax
0x14005bd61  test    eax, eax
0x14005bd63  jle     short loc_14005BD6E
0x14005bd65  movzx   ebx, ax
0x14005bd68  or      ebx, 80070000h
0x14005bd6e  test    ebx, ebx
0x14005bd70  jns     loc_14005BE5E
0x14005bd76  mov     rcx, [rbp+20h]; this
0x14005bd7a  lea     r8, aPcshellShellSy_8; "pcshell\\shell\\systemsettings\\adminfl"...
0x14005bd81  mov     r9d, ebx; char *
0x14005bd84  mov     edx, 0CEh; void *
0x14005bd89  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14005bd8e  jmp     loc_14005BE5E
0x14005bd93  cmp     [rbp+pNumArgs], 2
0x14005bd97  jge     short loc_14005BDBB
0x14005bd99  mov     rcx, [rbp+20h]; this
0x14005bd9d  lea     r8, aPcshellShellSy_8; "pcshell\\shell\\systemsettings\\adminfl"...
0x14005bda4  mov     ebx, 80028CA1h
0x14005bda9  mov     edx, 0CFh; void *
0x14005bdae  mov     r9d, ebx; char *
0x14005bdb1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14005bdb6  jmp     loc_14005BE55
0x14005bdbb  mov     rdx, rdi
0x14005bdbe  mov     [rbp+arg_10], rsi
0x14005bdc2  lea     rcx, [rbp+arg_10]
0x14005bdc6  mov     [rbp+string], rsi
0x14005bdca  call    ??$Set@PEAG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort *>(ushort * const &,Microsoft::WRL::Details::Dummy)
0x14005bdcf  mov     ebx, eax
0x14005bdd1  test    eax, eax
0x14005bdd3  jns     short loc_14005BDEF
0x14005bdd5  mov     edx, 0D2h; void *
0x14005bdda  mov     rcx, [rbp+20h]; this
0x14005bdde  lea     r8, aPcshellShellSy_8; "pcshell\\shell\\systemsettings\\adminfl"...
0x14005bde5  mov     r9d, eax; char *
0x14005bde8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14005bded  jmp     short loc_14005BE39
0x14005bdef  lea     rdx, [rdi+8]
0x14005bdf3  lea     rcx, [rbp+string]
0x14005bdf7  call    ??$Set@PEAG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort *>(ushort * const &,Microsoft::WRL::Details::Dummy)
0x14005bdfc  mov     ebx, eax
0x14005bdfe  test    eax, eax
0x14005be00  jns     short loc_14005BE09
0x14005be02  mov     edx, 0D3h
0x14005be07  jmp     short loc_14005BDDA
0x14005be09  lea     rcx, [rbp+arg_18]
0x14005be0d  call    ?CreateStorageAdminHelper@StorageAdminOps@@SAJAEAV?$ComPtr@UIStorageAdminHelperImpl@StorageHandlers@@@WRL@Microsoft@@@Z; StorageAdminOps::CreateStorageAdminHelper(Microsoft::WRL::ComPtr<StorageHandlers::IStorageAdminHelperImpl> &)
0x14005be12  mov     ebx, eax
0x14005be14  test    eax, eax
0x14005be16  jns     short loc_14005BE1F
0x14005be18  mov     edx, 0D6h
0x14005be1d  jmp     short loc_14005BDDA
0x14005be1f  mov     rcx, [rbp+arg_18]
0x14005be23  mov     r8, [rbp+string]
0x14005be27  mov     rdx, [rbp+arg_10]
0x14005be2b  mov     rax, [rcx]
0x14005be2e  mov     rax, [rax+68h]
0x14005be32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005be37  mov     ebx, eax
0x14005be39  mov     rcx, [rbp+string]; string
0x14005be3d  call    cs:__imp_WindowsDeleteString
0x14005be43  mov     rcx, [rbp+arg_10]; string
0x14005be47  mov     [rbp+string], rsi
0x14005be4b  call    cs:__imp_WindowsDeleteString
0x14005be51  mov     [rbp+arg_10], rsi
0x14005be55  mov     rcx, rdi; hMem
0x14005be58  call    cs:__imp_LocalFree
0x14005be5e  lea     rcx, [rbp+arg_18]
0x14005be62  call    ?InternalRelease@?$ComPtr@UICbsSession9@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICbsSession9>::InternalRelease(void)
0x14005be67  mov     eax, ebx
0x14005be69  add     rsp, 28h
0x14005be6d  pop     rdi
0x14005be6e  pop     rsi
0x14005be6f  pop     rbx
0x14005be70  pop     rbp
0x14005be71  retn
```
