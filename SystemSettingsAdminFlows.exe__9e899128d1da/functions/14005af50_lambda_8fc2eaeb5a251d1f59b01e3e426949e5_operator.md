# _lambda_8fc2eaeb5a251d1f59b01e3e426949e5_::operator()

- ea: `0x14005af50`
- end: `0x14005b0db`
- name: `_lambda_8fc2eaeb5a251d1f59b01e3e426949e5_::operator()`
- size: `395`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x14005c6b4`

## callees

- `0x140005f30`
- `0x14001f3d4`
- `0x1400598e0`
- `0x14005af50`
- `0x14005be78`
- `0x14005c068`
- `0x14007d010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x14005b0a9`
- `KERNEL32!LocalFree` at `0x14005b0a9`
- `KERNEL32!GetLastError` at `0x14005af9c`
- `KERNEL32!GetLastError` at `0x14005af9c`
- `ole32!CLSIDFromString` at `0x14005b013`
- `ole32!CLSIDFromString` at `0x14005b031`
- `ole32!CLSIDFromString` at `0x14005b013`
- `ole32!CLSIDFromString` at `0x14005b031`
- `SHELL32!CommandLineToArgvW` at `0x14005af8e`
- `SHELL32!CommandLineToArgvW` at `0x14005af8e`

## pseudocode

```c
__int64 __fastcall lambda_8fc2eaeb5a251d1f59b01e3e426949e5_::operator()(LPCWSTR **a1)
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
            v12 = (*(__int64 (__fastcall **)(__int64 *, GUID *, GUID *, _QWORD *))(v11 + 288))(v16, &v19, &v18, v17);
            v5 = StorageAdminOps::EncodeSpacesResult(v12, (const struct StorageHandlers::SpacesRpcResult *)v17);
            goto LABEL_16;
          }
          v7 = (unsigned int)StorageAdminHelper;
          v6 = 648;
        }
        else
        {
          v7 = (unsigned int)v9;
          v6 = 645;
        }
      }
      else
      {
        v7 = (unsigned int)v8;
        v6 = 644;
      }
    }
    else
    {
      v5 = -2147316575;
      v6 = 641;
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
      (void *)0x280,
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
0x14005af50  mov     [rsp-8+arg_8], rbx
0x14005af55  mov     [rsp-8+arg_10], rdi
0x14005af5a  push    rbp
0x14005af5b  lea     rbp, [rsp-57h]
0x14005af60  sub     rsp, 0A0h
0x14005af67  mov     rax, cs:__security_cookie
0x14005af6e  xor     rax, rsp
0x14005af71  mov     [rbp+57h+var_10], rax
0x14005af75  mov     rcx, [rcx]
0x14005af78  lea     rdx, [rbp+57h+pNumArgs]; pNumArgs
0x14005af7c  mov     [rbp+57h+var_68], 0
0x14005af84  mov     [rbp+57h+pNumArgs], 0
0x14005af8b  mov     rcx, [rcx]; lpCmdLine
0x14005af8e  call    cs:__imp_CommandLineToArgvW
0x14005af94  mov     rdi, rax
0x14005af97  test    rax, rax
0x14005af9a  jnz     short loc_14005AFD6
0x14005af9c  call    cs:__imp_GetLastError
0x14005afa2  mov     ebx, eax
0x14005afa4  test    eax, eax
0x14005afa6  jle     short loc_14005AFB1
0x14005afa8  movzx   ebx, ax
0x14005afab  or      ebx, 80070000h
0x14005afb1  test    ebx, ebx
0x14005afb3  jns     loc_14005B0AF
0x14005afb9  mov     rcx, [rbp+5Fh]; this
0x14005afbd  lea     r8, aPcshellShellSy_8; "pcshell\\shell\\systemsettings\\adminfl"...
0x14005afc4  mov     r9d, ebx; char *
0x14005afc7  mov     edx, 280h; void *
0x14005afcc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14005afd1  jmp     loc_14005B0AF
0x14005afd6  cmp     [rbp+57h+pNumArgs], 2
0x14005afda  jge     short loc_14005AFFE
0x14005afdc  mov     ebx, 80028CA1h
0x14005afe1  mov     edx, 281h; void *
0x14005afe6  mov     r9d, ebx; char *
0x14005afe9  mov     rcx, [rbp+5Fh]; this
0x14005afed  lea     r8, aPcshellShellSy_8; "pcshell\\shell\\systemsettings\\adminfl"...
0x14005aff4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14005aff9  jmp     loc_14005B0A6
0x14005affe  xorps   xmm0, xmm0
0x14005b001  lea     rdx, [rbp+57h+pclsid]; pclsid
0x14005b005  xorps   xmm1, xmm1
0x14005b008  movups  xmmword ptr [rbp+57h+pclsid.Data1], xmm0
0x14005b00c  movups  xmmword ptr [rbp+57h+var_30.Data1], xmm1
0x14005b010  mov     rcx, [rax]; lpsz
0x14005b013  call    cs:__imp_CLSIDFromString
0x14005b019  mov     ebx, eax
0x14005b01b  test    eax, eax
0x14005b01d  jns     short loc_14005B029
0x14005b01f  mov     r9d, eax
0x14005b022  mov     edx, 284h
0x14005b027  jmp     short loc_14005AFE9
0x14005b029  mov     rcx, [rdi+8]; lpsz
0x14005b02d  lea     rdx, [rbp+57h+var_30]; pclsid
0x14005b031  call    cs:__imp_CLSIDFromString
0x14005b037  mov     ebx, eax
0x14005b039  test    eax, eax
0x14005b03b  jns     short loc_14005B047
0x14005b03d  mov     r9d, eax
0x14005b040  mov     edx, 285h
0x14005b045  jmp     short loc_14005AFE9
0x14005b047  lea     rcx, [rbp+57h+var_68]
0x14005b04b  call    ?CreateStorageAdminHelper@StorageAdminOps@@SAJAEAV?$ComPtr@UIStorageAdminHelperImpl@StorageHandlers@@@WRL@Microsoft@@@Z; StorageAdminOps::CreateStorageAdminHelper(Microsoft::WRL::ComPtr<StorageHandlers::IStorageAdminHelperImpl> &)
0x14005b050  mov     ebx, eax
0x14005b052  test    eax, eax
0x14005b054  jns     short loc_14005B060
0x14005b056  mov     r9d, eax
0x14005b059  mov     edx, 288h
0x14005b05e  jmp     short loc_14005AFE9
0x14005b060  mov     rcx, [rbp+57h+var_68]
0x14005b064  lea     r9, [rbp+57h+var_60]
0x14005b068  movaps  xmm0, xmmword ptr [rbp+57h+var_30.Data1]
0x14005b06c  lea     r8, [rbp+57h+var_50]
0x14005b070  movaps  xmm1, xmmword ptr [rbp+57h+pclsid.Data1]
0x14005b074  lea     rdx, [rbp+57h+var_40]
0x14005b078  mov     [rbp+57h+var_60], 0
0x14005b080  mov     rax, [rcx]
0x14005b083  movdqa  [rbp+57h+var_50], xmm0
0x14005b088  movdqa  [rbp+57h+var_40], xmm1
0x14005b08d  mov     rax, [rax+120h]
0x14005b094  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005b099  lea     rdx, [rbp+57h+var_60]; struct StorageHandlers::SpacesRpcResult *
0x14005b09d  mov     ecx, eax; int
0x14005b09f  call    ?EncodeSpacesResult@StorageAdminOps@@SAJJAEBUSpacesRpcResult@StorageHandlers@@@Z; StorageAdminOps::EncodeSpacesResult(long,StorageHandlers::SpacesRpcResult const &)
0x14005b0a4  mov     ebx, eax
0x14005b0a6  mov     rcx, rdi; hMem
0x14005b0a9  call    cs:__imp_LocalFree
0x14005b0af  lea     rcx, [rbp+57h+var_68]
0x14005b0b3  call    ?InternalRelease@?$ComPtr@UICbsSession9@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICbsSession9>::InternalRelease(void)
0x14005b0b8  mov     eax, ebx
0x14005b0ba  mov     rcx, [rbp+57h+var_10]
0x14005b0be  xor     rcx, rsp; StackCookie
0x14005b0c1  call    __security_check_cookie
0x14005b0c6  lea     r11, [rsp+0A0h+var_s0]
0x14005b0ce  mov     rbx, [r11+18h]
0x14005b0d2  mov     rdi, [r11+20h]
0x14005b0d6  mov     rsp, r11
0x14005b0d9  pop     rbp
0x14005b0da  retn
```
