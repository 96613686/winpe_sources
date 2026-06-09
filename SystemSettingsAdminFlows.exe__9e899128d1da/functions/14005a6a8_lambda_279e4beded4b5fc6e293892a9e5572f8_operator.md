# _lambda_279e4beded4b5fc6e293892a9e5572f8_::operator()

- ea: `0x14005a6a8`
- end: `0x14005a88a`
- name: `_lambda_279e4beded4b5fc6e293892a9e5572f8_::operator()`
- size: `482`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x14005c474`

## callees

- `0x140005f30`
- `0x14001f3d4`
- `0x140057a50`
- `0x1400598e0`
- `0x14005a6a8`
- `0x14005be78`
- `0x14005c068`
- `0x14005c130`
- `0x14007d010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x14005a858`
- `KERNEL32!LocalFree` at `0x14005a858`
- `KERNEL32!GetLastError` at `0x14005a6f4`
- `KERNEL32!GetLastError` at `0x14005a6f4`
- `ole32!CLSIDFromString` at `0x14005a773`
- `ole32!CLSIDFromString` at `0x14005a7a4`
- `ole32!CLSIDFromString` at `0x14005a773`
- `ole32!CLSIDFromString` at `0x14005a7a4`
- `SHELL32!CommandLineToArgvW` at `0x14005a6e6`
- `SHELL32!CommandLineToArgvW` at `0x14005a6e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14005a847`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14005a847`

## pseudocode

```c
__int64 __fastcall lambda_279e4beded4b5fc6e293892a9e5572f8_::operator()(LPCWSTR **a1)
{
  LPCWSTR *v1; // rcx
  LPWSTR *v2; // rax
  LPWSTR *v3; // rdi
  signed int LastError; // eax
  unsigned int v5; // ebx
  int StorageAdminHelper; // eax
  __int64 v7; // rdx
  __int64 v8; // rax
  int v9; // eax
  int v11; // [rsp+20h] [rbp-29h]
  HSTRING string; // [rsp+30h] [rbp-19h] BYREF
  int pNumArgs; // [rsp+38h] [rbp-11h] BYREF
  __int64 *v14; // [rsp+40h] [rbp-9h] BYREF
  __int64 v15; // [rsp+48h] [rbp-1h] BYREF
  GUID v16; // [rsp+50h] [rbp+7h] BYREF
  GUID v17; // [rsp+60h] [rbp+17h] BYREF
  GUID v18; // [rsp+70h] [rbp+27h] BYREF
  GUID pclsid; // [rsp+80h] [rbp+37h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  v1 = *a1;
  v14 = 0;
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
        (void *)0x2A4,
        (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\storage\\storageadminhelper\\storageadminops.cpp",
        (const char *)0x80028CA1LL,
        v11);
LABEL_19:
      LocalFree(v3);
      goto LABEL_20;
    }
    string = 0;
    pclsid = 0;
    v18 = 0;
    StorageAdminHelper = CLSIDFromString(*v2, &pclsid);
    v5 = StorageAdminHelper;
    if ( StorageAdminHelper >= 0 )
    {
      StorageAdminHelper = CLSIDFromString(v3[1], &v18);
      v5 = StorageAdminHelper;
      if ( StorageAdminHelper >= 0 )
      {
        *(_QWORD *)&v16.Data1 = FixTrailingBackslashMarker(v3[2]);
        StorageAdminHelper = Microsoft::WRL::Wrappers::HString::Set<unsigned short *>(&string, &v16);
        v5 = StorageAdminHelper;
        if ( StorageAdminHelper >= 0 )
        {
          StorageAdminHelper = StorageAdminOps::CreateStorageAdminHelper((__int64)&v14);
          v5 = StorageAdminHelper;
          if ( StorageAdminHelper >= 0 )
          {
            v15 = 0;
            v8 = *v14;
            v16 = v18;
            v17 = pclsid;
            v9 = (*(__int64 (__fastcall **)(__int64 *, GUID *, GUID *, HSTRING, __int64 *))(v8 + 296))(
                   v14,
                   &v17,
                   &v16,
                   string,
                   &v15);
            v5 = StorageAdminOps::EncodeSpacesResult(v9, (const struct StorageHandlers::SpacesRpcResult *)&v15);
            goto LABEL_18;
          }
          v7 = 685;
        }
        else
        {
          v7 = 682;
        }
      }
      else
      {
        v7 = 681;
      }
    }
    else
    {
      v7 = 680;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\storage\\storageadminhelper\\storageadminops.cpp",
      (const char *)(unsigned int)StorageAdminHelper,
      v11);
LABEL_18:
    WindowsDeleteString(string);
    string = 0;
    goto LABEL_19;
  }
  LastError = GetLastError();
  v5 = LastError;
  if ( LastError > 0 )
    v5 = (unsigned __int16)LastError | 0x80070000;
  if ( (v5 & 0x80000000) != 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2A3,
      (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\storage\\storageadminhelper\\storageadminops.cpp",
      (const char *)v5,
      v11);
LABEL_20:
  Microsoft::WRL::ComPtr<ICbsSession9>::InternalRelease(&v14);
  return v5;
}

```

## disassembly

```asm
0x14005a6a8  mov     [rsp-8+arg_8], rbx
0x14005a6ad  mov     [rsp-8+arg_10], rdi
0x14005a6b2  push    rbp
0x14005a6b3  lea     rbp, [rsp-57h]
0x14005a6b8  sub     rsp, 0A0h
0x14005a6bf  mov     rax, cs:__security_cookie
0x14005a6c6  xor     rax, rsp
0x14005a6c9  mov     [rbp+57h+var_10], rax
0x14005a6cd  mov     rcx, [rcx]
0x14005a6d0  lea     rdx, [rbp+57h+pNumArgs]; pNumArgs
0x14005a6d4  mov     [rbp+57h+var_60], 0
0x14005a6dc  mov     [rbp+57h+pNumArgs], 0
0x14005a6e3  mov     rcx, [rcx]; lpCmdLine
0x14005a6e6  call    cs:__imp_CommandLineToArgvW
0x14005a6ec  mov     rdi, rax
0x14005a6ef  test    rax, rax
0x14005a6f2  jnz     short loc_14005A72E
0x14005a6f4  call    cs:__imp_GetLastError
0x14005a6fa  mov     ebx, eax
0x14005a6fc  test    eax, eax
0x14005a6fe  jle     short loc_14005A709
0x14005a700  movzx   ebx, ax
0x14005a703  or      ebx, 80070000h
0x14005a709  test    ebx, ebx
0x14005a70b  jns     loc_14005A85E
0x14005a711  mov     rcx, [rbp+5Fh]; this
0x14005a715  lea     r8, aPcshellShellSy_8; "pcshell\\shell\\systemsettings\\adminfl"...
0x14005a71c  mov     r9d, ebx; char *
0x14005a71f  mov     edx, 2A3h; void *
0x14005a724  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14005a729  jmp     loc_14005A85E
0x14005a72e  cmp     [rbp+57h+pNumArgs], 3
0x14005a732  jge     short loc_14005A756
0x14005a734  mov     rcx, [rbp+5Fh]; this
0x14005a738  lea     r8, aPcshellShellSy_8; "pcshell\\shell\\systemsettings\\adminfl"...
0x14005a73f  mov     ebx, 80028CA1h
0x14005a744  mov     edx, 2A4h; void *
0x14005a749  mov     r9d, ebx; char *
0x14005a74c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14005a751  jmp     loc_14005A855
0x14005a756  xorps   xmm0, xmm0
0x14005a759  mov     [rbp+57h+string], 0
0x14005a761  xorps   xmm1, xmm1
0x14005a764  lea     rdx, [rbp+57h+pclsid]; pclsid
0x14005a768  movups  xmmword ptr [rbp+57h+pclsid.Data1], xmm0
0x14005a76c  movups  xmmword ptr [rbp+57h+var_30.Data1], xmm1
0x14005a770  mov     rcx, [rax]; lpsz
0x14005a773  call    cs:__imp_CLSIDFromString
0x14005a779  mov     ebx, eax
0x14005a77b  test    eax, eax
0x14005a77d  jns     short loc_14005A79C
0x14005a77f  mov     edx, 2A8h; void *
0x14005a784  mov     rcx, [rbp+5Fh]; this
0x14005a788  lea     r8, aPcshellShellSy_8; "pcshell\\shell\\systemsettings\\adminfl"...
0x14005a78f  mov     r9d, eax; char *
0x14005a792  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14005a797  jmp     loc_14005A843
0x14005a79c  mov     rcx, [rdi+8]; lpsz
0x14005a7a0  lea     rdx, [rbp+57h+var_30]; pclsid
0x14005a7a4  call    cs:__imp_CLSIDFromString
0x14005a7aa  mov     ebx, eax
0x14005a7ac  test    eax, eax
0x14005a7ae  jns     short loc_14005A7B7
0x14005a7b0  mov     edx, 2A9h
0x14005a7b5  jmp     short loc_14005A784
0x14005a7b7  mov     rcx, [rdi+10h]
0x14005a7bb  call    FixTrailingBackslashMarker
0x14005a7c0  lea     rdx, [rbp+57h+var_50]
0x14005a7c4  mov     qword ptr [rbp+57h+var_50], rax
0x14005a7c8  lea     rcx, [rbp+57h+string]
0x14005a7cc  call    ??$Set@PEAG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort *>(ushort * const &,Microsoft::WRL::Details::Dummy)
0x14005a7d1  mov     ebx, eax
0x14005a7d3  test    eax, eax
0x14005a7d5  jns     short loc_14005A7DE
0x14005a7d7  mov     edx, 2AAh
0x14005a7dc  jmp     short loc_14005A784
0x14005a7de  lea     rcx, [rbp+57h+var_60]
0x14005a7e2  call    ?CreateStorageAdminHelper@StorageAdminOps@@SAJAEAV?$ComPtr@UIStorageAdminHelperImpl@StorageHandlers@@@WRL@Microsoft@@@Z; StorageAdminOps::CreateStorageAdminHelper(Microsoft::WRL::ComPtr<StorageHandlers::IStorageAdminHelperImpl> &)
0x14005a7e7  mov     ebx, eax
0x14005a7e9  test    eax, eax
0x14005a7eb  jns     short loc_14005A7F4
0x14005a7ed  mov     edx, 2ADh
0x14005a7f2  jmp     short loc_14005A784
0x14005a7f4  mov     rcx, [rbp+57h+var_60]
0x14005a7f8  lea     rdx, [rbp+57h+var_58]
0x14005a7fc  movaps  xmm0, xmmword ptr [rbp+57h+var_30.Data1]
0x14005a800  lea     r8, [rbp+57h+var_50]
0x14005a804  movaps  xmm1, xmmword ptr [rbp+57h+pclsid.Data1]
0x14005a808  mov     r9, [rbp+57h+string]
0x14005a80c  mov     [rbp+57h+var_58], 0
0x14005a814  mov     rax, [rcx]
0x14005a817  mov     qword ptr [rsp+0A0h+var_80], rdx
0x14005a81c  lea     rdx, [rbp+57h+var_40]
0x14005a820  movdqa  [rbp+57h+var_50], xmm0
0x14005a825  movdqa  [rbp+57h+var_40], xmm1
0x14005a82a  mov     rax, [rax+128h]
0x14005a831  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005a836  lea     rdx, [rbp+57h+var_58]; struct StorageHandlers::SpacesRpcResult *
0x14005a83a  mov     ecx, eax; int
0x14005a83c  call    ?EncodeSpacesResult@StorageAdminOps@@SAJJAEBUSpacesRpcResult@StorageHandlers@@@Z; StorageAdminOps::EncodeSpacesResult(long,StorageHandlers::SpacesRpcResult const &)
0x14005a841  mov     ebx, eax
0x14005a843  mov     rcx, [rbp+57h+string]; string
0x14005a847  call    cs:__imp_WindowsDeleteString
0x14005a84d  mov     [rbp+57h+string], 0
0x14005a855  mov     rcx, rdi; hMem
0x14005a858  call    cs:__imp_LocalFree
0x14005a85e  lea     rcx, [rbp+57h+var_60]
0x14005a862  call    ?InternalRelease@?$ComPtr@UICbsSession9@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICbsSession9>::InternalRelease(void)
0x14005a867  mov     eax, ebx
0x14005a869  mov     rcx, [rbp+57h+var_10]
0x14005a86d  xor     rcx, rsp; StackCookie
0x14005a870  call    __security_check_cookie
0x14005a875  lea     r11, [rsp+0A0h+var_s0]
0x14005a87d  mov     rbx, [r11+18h]
0x14005a881  mov     rdi, [r11+20h]
0x14005a885  mov     rsp, r11
0x14005a888  pop     rbp
0x14005a889  retn
```
