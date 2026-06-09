# _lambda_82c5026b0ba3fe7dad6ab17ea20da0fc_::operator()

- ea: `0x14005accc`
- end: `0x14005ae22`
- name: `_lambda_82c5026b0ba3fe7dad6ab17ea20da0fc_::operator()`
- size: `342`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14005c4d4`

## callees

- `0x14001f3d4`
- `0x140057a50`
- `0x1400598e0`
- `0x14005accc`
- `0x14005be78`
- `0x14005c130`
- `0x14007d010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x14005ae08`
- `KERNEL32!LocalFree` at `0x14005ae08`
- `KERNEL32!GetLastError` at `0x14005acf9`
- `KERNEL32!GetLastError` at `0x14005acf9`
- `SHELL32!CommandLineToArgvW` at `0x14005aceb`
- `SHELL32!CommandLineToArgvW` at `0x14005aceb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14005aded`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14005adfb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14005aded`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14005adfb`

## pseudocode

```c
__int64 __fastcall lambda_82c5026b0ba3fe7dad6ab17ea20da0fc_::operator()(LPCWSTR **a1)
{
  LPCWSTR *v1; // rcx
  LPWSTR *v2; // rax
  LPWSTR *v3; // rdi
  signed int LastError; // eax
  unsigned int v5; // ebx
  int StorageAdminHelper; // eax
  __int64 v7; // rdx
  __int64 v9[3]; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+20h]
  int pNumArgs; // [rsp+60h] [rbp+28h] BYREF
  HSTRING string; // [rsp+68h] [rbp+30h] BYREF
  HSTRING v13; // [rsp+70h] [rbp+38h] BYREF
  __int64 v14; // [rsp+78h] [rbp+40h] BYREF

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
        (void *)0xF0,
        (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\storage\\storageadminhelper\\storageadminops.cpp",
        (const char *)0x80028CA1LL,
        v9[0]);
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
      v9[0] = FixTrailingBackslashMarker(v3[1]);
      StorageAdminHelper = Microsoft::WRL::Wrappers::HString::Set<unsigned short *>(&string, v9);
      v5 = StorageAdminHelper;
      if ( StorageAdminHelper >= 0 )
      {
        StorageAdminHelper = StorageAdminOps::CreateStorageAdminHelper((__int64)&v14);
        v5 = StorageAdminHelper;
        if ( StorageAdminHelper >= 0 )
        {
          v5 = (*(__int64 (__fastcall **)(__int64, HSTRING, HSTRING))(*(_QWORD *)v14 + 128LL))(v14, v13, string);
          goto LABEL_16;
        }
        v7 = 247;
      }
      else
      {
        v7 = 244;
      }
    }
    else
    {
      v7 = 243;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\storage\\storageadminhelper\\storageadminops.cpp",
      (const char *)(unsigned int)StorageAdminHelper,
      v9[0]);
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
      (void *)0xEF,
      (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\storage\\storageadminhelper\\storageadminops.cpp",
      (const char *)v5,
      v9[0]);
LABEL_18:
  Microsoft::WRL::ComPtr<ICbsSession9>::InternalRelease(&v14);
  return v5;
}

```

## disassembly

```asm
0x14005accc  push    rbp
0x14005acce  push    rbx
0x14005accf  push    rsi
0x14005acd0  push    rdi
0x14005acd1  mov     rbp, rsp
0x14005acd4  sub     rsp, 38h
0x14005acd8  mov     rcx, [rcx]
0x14005acdb  lea     rdx, [rbp+pNumArgs]; pNumArgs
0x14005acdf  xor     esi, esi
0x14005ace1  mov     [rbp+arg_18], rsi
0x14005ace5  mov     [rbp+pNumArgs], esi
0x14005ace8  mov     rcx, [rcx]; lpCmdLine
0x14005aceb  call    cs:__imp_CommandLineToArgvW
0x14005acf1  mov     rdi, rax
0x14005acf4  test    rax, rax
0x14005acf7  jnz     short loc_14005AD33
0x14005acf9  call    cs:__imp_GetLastError
0x14005acff  mov     ebx, eax
0x14005ad01  test    eax, eax
0x14005ad03  jle     short loc_14005AD0E
0x14005ad05  movzx   ebx, ax
0x14005ad08  or      ebx, 80070000h
0x14005ad0e  test    ebx, ebx
0x14005ad10  jns     loc_14005AE0E
0x14005ad16  mov     rcx, [rbp+20h]; this
0x14005ad1a  lea     r8, aPcshellShellSy_8; "pcshell\\shell\\systemsettings\\adminfl"...
0x14005ad21  mov     r9d, ebx; char *
0x14005ad24  mov     edx, 0EFh; void *
0x14005ad29  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14005ad2e  jmp     loc_14005AE0E
0x14005ad33  cmp     [rbp+pNumArgs], 2
0x14005ad37  jge     short loc_14005AD5B
0x14005ad39  mov     rcx, [rbp+20h]; this
0x14005ad3d  lea     r8, aPcshellShellSy_8; "pcshell\\shell\\systemsettings\\adminfl"...
0x14005ad44  mov     ebx, 80028CA1h
0x14005ad49  mov     edx, 0F0h; void *
0x14005ad4e  mov     r9d, ebx; char *
0x14005ad51  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14005ad56  jmp     loc_14005AE05
0x14005ad5b  mov     rdx, rdi
0x14005ad5e  mov     [rbp+arg_10], rsi
0x14005ad62  lea     rcx, [rbp+arg_10]
0x14005ad66  mov     [rbp+string], rsi
0x14005ad6a  call    ??$Set@PEAG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort *>(ushort * const &,Microsoft::WRL::Details::Dummy)
0x14005ad6f  mov     ebx, eax
0x14005ad71  test    eax, eax
0x14005ad73  jns     short loc_14005AD8F
0x14005ad75  mov     edx, 0F3h; void *
0x14005ad7a  mov     rcx, [rbp+20h]; this
0x14005ad7e  lea     r8, aPcshellShellSy_8; "pcshell\\shell\\systemsettings\\adminfl"...
0x14005ad85  mov     r9d, eax; char *
0x14005ad88  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14005ad8d  jmp     short loc_14005ADE9
0x14005ad8f  mov     rcx, [rdi+8]
0x14005ad93  call    FixTrailingBackslashMarker
0x14005ad98  lea     rdx, [rbp+var_18]
0x14005ad9c  mov     [rbp+var_18], rax
0x14005ada0  lea     rcx, [rbp+string]
0x14005ada4  call    ??$Set@PEAG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort *>(ushort * const &,Microsoft::WRL::Details::Dummy)
0x14005ada9  mov     ebx, eax
0x14005adab  test    eax, eax
0x14005adad  jns     short loc_14005ADB6
0x14005adaf  mov     edx, 0F4h
0x14005adb4  jmp     short loc_14005AD7A
0x14005adb6  lea     rcx, [rbp+arg_18]
0x14005adba  call    ?CreateStorageAdminHelper@StorageAdminOps@@SAJAEAV?$ComPtr@UIStorageAdminHelperImpl@StorageHandlers@@@WRL@Microsoft@@@Z; StorageAdminOps::CreateStorageAdminHelper(Microsoft::WRL::ComPtr<StorageHandlers::IStorageAdminHelperImpl> &)
0x14005adbf  mov     ebx, eax
0x14005adc1  test    eax, eax
0x14005adc3  jns     short loc_14005ADCC
0x14005adc5  mov     edx, 0F7h
0x14005adca  jmp     short loc_14005AD7A
0x14005adcc  mov     rcx, [rbp+arg_18]
0x14005add0  mov     r8, [rbp+string]
0x14005add4  mov     rdx, [rbp+arg_10]
0x14005add8  mov     rax, [rcx]
0x14005addb  mov     rax, [rax+80h]
0x14005ade2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005ade7  mov     ebx, eax
0x14005ade9  mov     rcx, [rbp+string]; string
0x14005aded  call    cs:__imp_WindowsDeleteString
0x14005adf3  mov     rcx, [rbp+arg_10]; string
0x14005adf7  mov     [rbp+string], rsi
0x14005adfb  call    cs:__imp_WindowsDeleteString
0x14005ae01  mov     [rbp+arg_10], rsi
0x14005ae05  mov     rcx, rdi; hMem
0x14005ae08  call    cs:__imp_LocalFree
0x14005ae0e  lea     rcx, [rbp+arg_18]
0x14005ae12  call    ?InternalRelease@?$ComPtr@UICbsSession9@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICbsSession9>::InternalRelease(void)
0x14005ae17  mov     eax, ebx
0x14005ae19  add     rsp, 38h
0x14005ae1d  pop     rdi
0x14005ae1e  pop     rsi
0x14005ae1f  pop     rbx
0x14005ae20  pop     rbp
0x14005ae21  retn
```
