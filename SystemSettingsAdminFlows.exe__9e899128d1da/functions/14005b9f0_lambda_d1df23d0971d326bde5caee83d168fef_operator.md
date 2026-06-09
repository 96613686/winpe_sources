# _lambda_d1df23d0971d326bde5caee83d168fef_::operator()

- ea: `0x14005b9f0`
- end: `0x14005bb99`
- name: `_lambda_d1df23d0971d326bde5caee83d168fef_::operator()`
- size: `425`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x14005c414`

## callees

- `0x140005f30`
- `0x14001f3d4`
- `0x140057a50`
- `0x1400598e0`
- `0x14005b9f0`
- `0x14005be78`
- `0x14005c068`
- `0x14005c130`
- `0x14007d010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x14005bb67`
- `KERNEL32!LocalFree` at `0x14005bb67`
- `KERNEL32!GetLastError` at `0x14005ba3a`
- `KERNEL32!GetLastError` at `0x14005ba3a`
- `ole32!CLSIDFromString` at `0x14005bab2`
- `ole32!CLSIDFromString` at `0x14005bab2`
- `SHELL32!CommandLineToArgvW` at `0x14005ba2c`
- `SHELL32!CommandLineToArgvW` at `0x14005ba2c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14005bb56`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14005bb56`

## pseudocode

```c
__int64 __fastcall lambda_d1df23d0971d326bde5caee83d168fef_::operator()(LPCWSTR **a1)
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
  int v11; // [rsp+20h] [rbp-60h]
  HSTRING string; // [rsp+30h] [rbp-50h] BYREF
  int pNumArgs; // [rsp+38h] [rbp-48h] BYREF
  __int64 *v14; // [rsp+40h] [rbp-40h] BYREF
  __int64 v15; // [rsp+48h] [rbp-38h] BYREF
  GUID v16; // [rsp+50h] [rbp-30h] BYREF
  GUID pclsid; // [rsp+60h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+8h]

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
        (void *)0x1D6,
        (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\storage\\storageadminhelper\\storageadminops.cpp",
        (const char *)0x80028CA1LL,
        v11);
LABEL_17:
      LocalFree(v3);
      goto LABEL_18;
    }
    string = 0;
    pclsid = 0;
    StorageAdminHelper = CLSIDFromString(*v2, &pclsid);
    v5 = StorageAdminHelper;
    if ( StorageAdminHelper >= 0 )
    {
      *(_QWORD *)&v16.Data1 = FixTrailingBackslashMarker(v3[1]);
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
          v16 = pclsid;
          v9 = (*(__int64 (__fastcall **)(__int64 *, GUID *, HSTRING, __int64 *))(v8 + 216))(v14, &v16, string, &v15);
          v5 = StorageAdminOps::EncodeSpacesResult(v9, (const struct StorageHandlers::SpacesRpcResult *)&v15);
          goto LABEL_16;
        }
        v7 = 477;
      }
      else
      {
        v7 = 474;
      }
    }
    else
    {
      v7 = 473;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\storage\\storageadminhelper\\storageadminops.cpp",
      (const char *)(unsigned int)StorageAdminHelper,
      v11);
LABEL_16:
    WindowsDeleteString(string);
    string = 0;
    goto LABEL_17;
  }
  LastError = GetLastError();
  v5 = LastError;
  if ( LastError > 0 )
    v5 = (unsigned __int16)LastError | 0x80070000;
  if ( (v5 & 0x80000000) != 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1D5,
      (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\storage\\storageadminhelper\\storageadminops.cpp",
      (const char *)v5,
      v11);
LABEL_18:
  Microsoft::WRL::ComPtr<ICbsSession9>::InternalRelease(&v14);
  return v5;
}

```

## disassembly

```asm
0x14005b9f0  mov     [rsp-8+arg_8], rbx
0x14005b9f5  mov     [rsp-8+arg_10], rdi
0x14005b9fa  push    rbp
0x14005b9fb  mov     rbp, rsp
0x14005b9fe  sub     rsp, 80h
0x14005ba05  mov     rax, cs:__security_cookie
0x14005ba0c  xor     rax, rsp
0x14005ba0f  mov     [rbp+var_10], rax
0x14005ba13  mov     rcx, [rcx]
0x14005ba16  lea     rdx, [rbp+pNumArgs]; pNumArgs
0x14005ba1a  mov     [rbp+var_40], 0
0x14005ba22  mov     [rbp+pNumArgs], 0
0x14005ba29  mov     rcx, [rcx]; lpCmdLine
0x14005ba2c  call    cs:__imp_CommandLineToArgvW
0x14005ba32  mov     rdi, rax
0x14005ba35  test    rax, rax
0x14005ba38  jnz     short loc_14005BA74
0x14005ba3a  call    cs:__imp_GetLastError
0x14005ba40  mov     ebx, eax
0x14005ba42  test    eax, eax
0x14005ba44  jle     short loc_14005BA4F
0x14005ba46  movzx   ebx, ax
0x14005ba49  or      ebx, 80070000h
0x14005ba4f  test    ebx, ebx
0x14005ba51  jns     loc_14005BB6D
0x14005ba57  mov     rcx, [rbp+8]; this
0x14005ba5b  lea     r8, aPcshellShellSy_8; "pcshell\\shell\\systemsettings\\adminfl"...
0x14005ba62  mov     r9d, ebx; char *
0x14005ba65  mov     edx, 1D5h; void *
0x14005ba6a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14005ba6f  jmp     loc_14005BB6D
0x14005ba74  cmp     [rbp+pNumArgs], 2
0x14005ba78  jge     short loc_14005BA9C
0x14005ba7a  mov     rcx, [rbp+8]; this
0x14005ba7e  lea     r8, aPcshellShellSy_8; "pcshell\\shell\\systemsettings\\adminfl"...
0x14005ba85  mov     ebx, 80028CA1h
0x14005ba8a  mov     edx, 1D6h; void *
0x14005ba8f  mov     r9d, ebx; char *
0x14005ba92  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14005ba97  jmp     loc_14005BB64
0x14005ba9c  xorps   xmm0, xmm0
0x14005ba9f  mov     [rbp+string], 0
0x14005baa7  movups  xmmword ptr [rbp+pclsid.Data1], xmm0
0x14005baab  mov     rcx, [rax]; lpsz
0x14005baae  lea     rdx, [rbp+pclsid]; pclsid
0x14005bab2  call    cs:__imp_CLSIDFromString
0x14005bab8  mov     ebx, eax
0x14005baba  test    eax, eax
0x14005babc  jns     short loc_14005BAD8
0x14005babe  mov     edx, 1D9h; void *
0x14005bac3  mov     rcx, [rbp+8]; this
0x14005bac7  lea     r8, aPcshellShellSy_8; "pcshell\\shell\\systemsettings\\adminfl"...
0x14005bace  mov     r9d, eax; char *
0x14005bad1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14005bad6  jmp     short loc_14005BB52
0x14005bad8  mov     rcx, [rdi+8]
0x14005badc  call    FixTrailingBackslashMarker
0x14005bae1  lea     rdx, [rbp+var_30]
0x14005bae5  mov     qword ptr [rbp+var_30], rax
0x14005bae9  lea     rcx, [rbp+string]
0x14005baed  call    ??$Set@PEAG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort *>(ushort * const &,Microsoft::WRL::Details::Dummy)
0x14005baf2  mov     ebx, eax
0x14005baf4  test    eax, eax
0x14005baf6  jns     short loc_14005BAFF
0x14005baf8  mov     edx, 1DAh
0x14005bafd  jmp     short loc_14005BAC3
0x14005baff  lea     rcx, [rbp+var_40]
0x14005bb03  call    ?CreateStorageAdminHelper@StorageAdminOps@@SAJAEAV?$ComPtr@UIStorageAdminHelperImpl@StorageHandlers@@@WRL@Microsoft@@@Z; StorageAdminOps::CreateStorageAdminHelper(Microsoft::WRL::ComPtr<StorageHandlers::IStorageAdminHelperImpl> &)
0x14005bb08  mov     ebx, eax
0x14005bb0a  test    eax, eax
0x14005bb0c  jns     short loc_14005BB15
0x14005bb0e  mov     edx, 1DDh
0x14005bb13  jmp     short loc_14005BAC3
0x14005bb15  mov     rcx, [rbp+var_40]
0x14005bb19  lea     r9, [rbp+var_38]
0x14005bb1d  movaps  xmm0, xmmword ptr [rbp+pclsid.Data1]
0x14005bb21  lea     rdx, [rbp+var_30]
0x14005bb25  mov     r8, [rbp+string]
0x14005bb29  mov     [rbp+var_38], 0
0x14005bb31  mov     rax, [rcx]
0x14005bb34  movdqa  [rbp+var_30], xmm0
0x14005bb39  mov     rax, [rax+0D8h]
0x14005bb40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005bb45  lea     rdx, [rbp+var_38]; struct StorageHandlers::SpacesRpcResult *
0x14005bb49  mov     ecx, eax; int
0x14005bb4b  call    ?EncodeSpacesResult@StorageAdminOps@@SAJJAEBUSpacesRpcResult@StorageHandlers@@@Z; StorageAdminOps::EncodeSpacesResult(long,StorageHandlers::SpacesRpcResult const &)
0x14005bb50  mov     ebx, eax
0x14005bb52  mov     rcx, [rbp+string]; string
0x14005bb56  call    cs:__imp_WindowsDeleteString
0x14005bb5c  mov     [rbp+string], 0
0x14005bb64  mov     rcx, rdi; hMem
0x14005bb67  call    cs:__imp_LocalFree
0x14005bb6d  lea     rcx, [rbp+var_40]
0x14005bb71  call    ?InternalRelease@?$ComPtr@UICbsSession9@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICbsSession9>::InternalRelease(void)
0x14005bb76  mov     eax, ebx
0x14005bb78  mov     rcx, [rbp+var_10]
0x14005bb7c  xor     rcx, rsp; StackCookie
0x14005bb7f  call    __security_check_cookie
0x14005bb84  lea     r11, [rsp+80h+var_s0]
0x14005bb8c  mov     rbx, [r11+18h]
0x14005bb90  mov     rdi, [r11+20h]
0x14005bb94  mov     rsp, r11
0x14005bb97  pop     rbp
0x14005bb98  retn
```
