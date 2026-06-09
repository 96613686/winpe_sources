# _lambda_34db8dbad50a816b25c6ea35d69edceb_::operator()

- ea: `0x14005ab38`
- end: `0x14005acc3`
- name: `_lambda_34db8dbad50a816b25c6ea35d69edceb_::operator()`
- size: `395`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x14005c3b4`

## callees

- `0x140005f30`
- `0x14001f3d4`
- `0x1400598e0`
- `0x14005ab38`
- `0x14005be78`
- `0x14005c068`
- `0x14007d010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x14005ac91`
- `KERNEL32!LocalFree` at `0x14005ac91`
- `KERNEL32!GetLastError` at `0x14005ab84`
- `KERNEL32!GetLastError` at `0x14005ab84`
- `ole32!CLSIDFromString` at `0x14005abfb`
- `ole32!CLSIDFromString` at `0x14005ac19`
- `ole32!CLSIDFromString` at `0x14005abfb`
- `ole32!CLSIDFromString` at `0x14005ac19`
- `SHELL32!CommandLineToArgvW` at `0x14005ab76`
- `SHELL32!CommandLineToArgvW` at `0x14005ab76`

## pseudocode

```c
__int64 __fastcall lambda_34db8dbad50a816b25c6ea35d69edceb_::operator()(LPCWSTR **a1)
{
  LPCWSTR *v1; // rcx
  LPWSTR *v2; // rax
  LPCOLESTR *v3; // rdi
  signed int LastError; // eax
  unsigned int v5; // ebx
  __int64 v6; // rdx
  __int64 v7; // r9
  HRESULT v8; // eax
  HRESULT v9; // eax
  int StorageAdminHelper; // eax
  __int64 v11; // rax
  int v12; // eax
  int v14; // [rsp+20h] [rbp-29h]
  int pNumArgs; // [rsp+30h] [rbp-19h] BYREF
  __int64 *v16; // [rsp+38h] [rbp-11h] BYREF
  _QWORD v17[2]; // [rsp+40h] [rbp-9h] BYREF
  GUID v18; // [rsp+50h] [rbp+7h] BYREF
  GUID v19; // [rsp+60h] [rbp+17h] BYREF
  GUID v20; // [rsp+70h] [rbp+27h] BYREF
  GUID pclsid; // [rsp+80h] [rbp+37h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  v1 = *a1;
  v16 = 0;
  pNumArgs = 0;
  v2 = CommandLineToArgvW(*v1, &pNumArgs);
  v3 = (LPCOLESTR *)v2;
  if ( v2 )
  {
    if ( pNumArgs >= 2 )
    {
      pclsid = 0;
      v20 = 0;
      v8 = CLSIDFromString(*v2, &pclsid);
      v5 = v8;
      if ( v8 >= 0 )
      {
        v9 = CLSIDFromString(v3[1], &v20);
        v5 = v9;
        if ( v9 >= 0 )
        {
          StorageAdminHelper = StorageAdminOps::CreateStorageAdminHelper((__int64)&v16);
          v5 = StorageAdminHelper;
          if ( StorageAdminHelper >= 0 )
          {
            v17[0] = 0;
            v11 = *v16;
            v18 = v20;
            v19 = pclsid;
            v12 = (*(__int64 (__fastcall **)(__int64 *, GUID *, GUID *, _QWORD *))(v11 + 280))(v16, &v19, &v18, v17);
            v5 = StorageAdminOps::EncodeSpacesResult(v12, (const struct StorageHandlers::SpacesRpcResult *)v17);
            goto LABEL_16;
          }
          v7 = (unsigned int)StorageAdminHelper;
          v6 = 613;
        }
        else
        {
          v7 = (unsigned int)v9;
          v6 = 610;
        }
      }
      else
      {
        v7 = (unsigned int)v8;
        v6 = 609;
      }
    }
    else
    {
      v5 = -2147316575;
      v6 = 606;
      v7 = 2147650721LL;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\storage\\storageadminhelper\\storageadminops.cpp",
      (const char *)v7,
      v14);
LABEL_16:
    LocalFree(v3);
    goto LABEL_17;
  }
  LastError = GetLastError();
  v5 = LastError;
  if ( LastError > 0 )
    v5 = (unsigned __int16)LastError | 0x80070000;
  if ( (v5 & 0x80000000) != 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x25D,
      (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\storage\\storageadminhelper\\storageadminops.cpp",
      (const char *)v5,
      v14);
LABEL_17:
  Microsoft::WRL::ComPtr<ICbsSession9>::InternalRelease(&v16);
  return v5;
}

```

## disassembly

```asm
0x14005ab38  mov     [rsp-8+arg_8], rbx
0x14005ab3d  mov     [rsp-8+arg_10], rdi
0x14005ab42  push    rbp
0x14005ab43  lea     rbp, [rsp-57h]
0x14005ab48  sub     rsp, 0A0h
0x14005ab4f  mov     rax, cs:__security_cookie
0x14005ab56  xor     rax, rsp
0x14005ab59  mov     [rbp+57h+var_10], rax
0x14005ab5d  mov     rcx, [rcx]
0x14005ab60  lea     rdx, [rbp+57h+pNumArgs]; pNumArgs
0x14005ab64  mov     [rbp+57h+var_68], 0
0x14005ab6c  mov     [rbp+57h+pNumArgs], 0
0x14005ab73  mov     rcx, [rcx]; lpCmdLine
0x14005ab76  call    cs:__imp_CommandLineToArgvW
0x14005ab7c  mov     rdi, rax
0x14005ab7f  test    rax, rax
0x14005ab82  jnz     short loc_14005ABBE
0x14005ab84  call    cs:__imp_GetLastError
0x14005ab8a  mov     ebx, eax
0x14005ab8c  test    eax, eax
0x14005ab8e  jle     short loc_14005AB99
0x14005ab90  movzx   ebx, ax
0x14005ab93  or      ebx, 80070000h
0x14005ab99  test    ebx, ebx
0x14005ab9b  jns     loc_14005AC97
0x14005aba1  mov     rcx, [rbp+5Fh]; this
0x14005aba5  lea     r8, aPcshellShellSy_8; "pcshell\\shell\\systemsettings\\adminfl"...
0x14005abac  mov     r9d, ebx; char *
0x14005abaf  mov     edx, 25Dh; void *
0x14005abb4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14005abb9  jmp     loc_14005AC97
0x14005abbe  cmp     [rbp+57h+pNumArgs], 2
0x14005abc2  jge     short loc_14005ABE6
0x14005abc4  mov     ebx, 80028CA1h
0x14005abc9  mov     edx, 25Eh; void *
0x14005abce  mov     r9d, ebx; char *
0x14005abd1  mov     rcx, [rbp+5Fh]; this
0x14005abd5  lea     r8, aPcshellShellSy_8; "pcshell\\shell\\systemsettings\\adminfl"...
0x14005abdc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14005abe1  jmp     loc_14005AC8E
0x14005abe6  xorps   xmm0, xmm0
0x14005abe9  lea     rdx, [rbp+57h+pclsid]; pclsid
0x14005abed  xorps   xmm1, xmm1
0x14005abf0  movups  xmmword ptr [rbp+57h+pclsid.Data1], xmm0
0x14005abf4  movups  xmmword ptr [rbp+57h+var_30.Data1], xmm1
0x14005abf8  mov     rcx, [rax]; lpsz
0x14005abfb  call    cs:__imp_CLSIDFromString
0x14005ac01  mov     ebx, eax
0x14005ac03  test    eax, eax
0x14005ac05  jns     short loc_14005AC11
0x14005ac07  mov     r9d, eax
0x14005ac0a  mov     edx, 261h
0x14005ac0f  jmp     short loc_14005ABD1
0x14005ac11  mov     rcx, [rdi+8]; lpsz
0x14005ac15  lea     rdx, [rbp+57h+var_30]; pclsid
0x14005ac19  call    cs:__imp_CLSIDFromString
0x14005ac1f  mov     ebx, eax
0x14005ac21  test    eax, eax
0x14005ac23  jns     short loc_14005AC2F
0x14005ac25  mov     r9d, eax
0x14005ac28  mov     edx, 262h
0x14005ac2d  jmp     short loc_14005ABD1
0x14005ac2f  lea     rcx, [rbp+57h+var_68]
0x14005ac33  call    ?CreateStorageAdminHelper@StorageAdminOps@@SAJAEAV?$ComPtr@UIStorageAdminHelperImpl@StorageHandlers@@@WRL@Microsoft@@@Z; StorageAdminOps::CreateStorageAdminHelper(Microsoft::WRL::ComPtr<StorageHandlers::IStorageAdminHelperImpl> &)
0x14005ac38  mov     ebx, eax
0x14005ac3a  test    eax, eax
0x14005ac3c  jns     short loc_14005AC48
0x14005ac3e  mov     r9d, eax
0x14005ac41  mov     edx, 265h
0x14005ac46  jmp     short loc_14005ABD1
0x14005ac48  mov     rcx, [rbp+57h+var_68]
0x14005ac4c  lea     r9, [rbp+57h+var_60]
0x14005ac50  movaps  xmm0, xmmword ptr [rbp+57h+var_30.Data1]
0x14005ac54  lea     r8, [rbp+57h+var_50]
0x14005ac58  movaps  xmm1, xmmword ptr [rbp+57h+pclsid.Data1]
0x14005ac5c  lea     rdx, [rbp+57h+var_40]
0x14005ac60  mov     [rbp+57h+var_60], 0
0x14005ac68  mov     rax, [rcx]
0x14005ac6b  movdqa  [rbp+57h+var_50], xmm0
0x14005ac70  movdqa  [rbp+57h+var_40], xmm1
0x14005ac75  mov     rax, [rax+118h]
0x14005ac7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005ac81  lea     rdx, [rbp+57h+var_60]; struct StorageHandlers::SpacesRpcResult *
0x14005ac85  mov     ecx, eax; int
0x14005ac87  call    ?EncodeSpacesResult@StorageAdminOps@@SAJJAEBUSpacesRpcResult@StorageHandlers@@@Z; StorageAdminOps::EncodeSpacesResult(long,StorageHandlers::SpacesRpcResult const &)
0x14005ac8c  mov     ebx, eax
0x14005ac8e  mov     rcx, rdi; hMem
0x14005ac91  call    cs:__imp_LocalFree
0x14005ac97  lea     rcx, [rbp+57h+var_68]
0x14005ac9b  call    ?InternalRelease@?$ComPtr@UICbsSession9@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICbsSession9>::InternalRelease(void)
0x14005aca0  mov     eax, ebx
0x14005aca2  mov     rcx, [rbp+57h+var_10]
0x14005aca6  xor     rcx, rsp; StackCookie
0x14005aca9  call    __security_check_cookie
0x14005acae  lea     r11, [rsp+0A0h+var_s0]
0x14005acb6  mov     rbx, [r11+18h]
0x14005acba  mov     rdi, [r11+20h]
0x14005acbe  mov     rsp, r11
0x14005acc1  pop     rbp
0x14005acc2  retn
```
