# CreateSavedPlatformClaim(void)

- ea: `0x18000fdb0`
- end: `0x18000ff32`
- name: `?CreateSavedPlatformClaim@@YAJXZ`
- size: `386`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001e5d0`

## callees

- `0x18000dd54`
- `0x18000e5a8`
- `0x18000ea88`
- `0x18000fdb0`
- `0x18001a42c`

## import_xrefs

- `ncrypt!NCryptFreeObject` at `0x18000fe4a`
- `ncrypt!NCryptFreeObject` at `0x18000fea9`
- `ncrypt!NCryptFreeObject` at `0x18000fe4a`
- `ncrypt!NCryptFreeObject` at `0x18000fea9`
- `ncrypt!NCryptOpenStorageProvider` at `0x18000fe6b`
- `ncrypt!NCryptOpenStorageProvider` at `0x18000fe6b`
- `ncrypt!NCryptCreateClaim` at `0x18000fefd`
- `ncrypt!NCryptCreateClaim` at `0x18000fefd`
- `tbs!Tbsi_Get_TCG_Log_Ex` at `0x18000fe01`
- `tbs!Tbsi_Get_TCG_Log_Ex` at `0x18000fe01`
- `TpmCoreProvisioning!TpmGetTpmVersion` at `0x18000fe18`
- `TpmCoreProvisioning!TpmGetTpmVersion` at `0x18000fe18`
- `TpmCoreProvisioning!TpmCertGetWindowsAik` at `0x18000fec4`
- `TpmCoreProvisioning!TpmCertGetWindowsAik` at `0x18000fec4`

## string_xrefs

- `0x18000fe7c`: `onecore\base\ngscb\tpm\task\dll\tpmtasks.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 CreateSavedPlatformClaim(void)
{
  SECURITY_STATUS TpmVersion; // eax
  unsigned int v1; // ebx
  __int64 v2; // rdx
  int v4; // [rsp+20h] [rbp-50h]
  NCRYPT_HANDLE v5; // [rsp+40h] [rbp-30h] BYREF
  NCRYPT_HANDLE hObject; // [rsp+48h] [rbp-28h] BYREF
  _DWORD v7[2]; // [rsp+50h] [rbp-20h] BYREF
  int *v8; // [rsp+58h] [rbp-18h]
  _DWORD v9[2]; // [rsp+60h] [rbp-10h] BYREF
  _DWORD *v10; // [rsp+68h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]
  int v12; // [rsp+90h] [rbp+20h] BYREF
  unsigned int v13; // [rsp+98h] [rbp+28h] BYREF
  int v14; // [rsp+A0h] [rbp+30h] BYREF
  int v15; // [rsp+A8h] [rbp+38h]

  hObject = 0;
  v5 = 0;
  v13 = 0;
  v14 = 1;
  v7[0] = 4;
  v7[1] = 82;
  v8 = &v14;
  v9[0] = 0;
  v9[1] = 1;
  v10 = v7;
  v15 = 0;
  v12 = 0;
  if ( (int)Tbsi_Get_TCG_Log_Ex(3, 0, &v12) >= 0 && v12 )
    goto LABEL_13;
  TpmVersion = TpmGetTpmVersion(&v13);
  v1 = TpmVersion;
  if ( TpmVersion >= 0 )
  {
    if ( v13 == 2 )
    {
      hObject = 0;
      TpmVersion = NCryptOpenStorageProvider(&hObject, L"Microsoft Platform Crypto Provider", 0);
      v1 = TpmVersion;
      if ( TpmVersion < 0 )
      {
        v2 = 1723;
        goto LABEL_8;
      }
      v5 = 0;
      TpmVersion = TpmCertGetWindowsAik(hObject, &v5);
      v1 = TpmVersion;
      if ( TpmVersion < 0 )
      {
        v2 = 1725;
        goto LABEL_8;
      }
      v4 = 0;
      TpmVersion = NCryptCreateClaim(0, v5, 0x10000, v9);
      v1 = TpmVersion;
      if ( TpmVersion < 0 )
      {
        v2 = 1735;
        goto LABEL_8;
      }
    }
LABEL_13:
    v1 = 0;
    goto LABEL_14;
  }
  v2 = 1717;
LABEL_8:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v2,
    (unsigned int)"onecore\\base\\ngscb\\tpm\\task\\dll\\tpmtasks.cpp",
    (const char *)(unsigned int)TpmVersion,
    v4);
LABEL_14:
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&v5);
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hObject);
  return v1;
}

```

## disassembly

```asm
0x18000fdb0  push    rbp
0x18000fdb2  push    rbx
0x18000fdb3  push    rdi
0x18000fdb4  mov     rbp, rsp
0x18000fdb7  sub     rsp, 70h
0x18000fdbb  xor     edi, edi
0x18000fdbd  mov     [rbp+hObject], rdi
0x18000fdc1  mov     [rbp+var_30], rdi
0x18000fdc5  mov     [rbp+arg_8], edi
0x18000fdc8  lea     ecx, [rdi+1]
0x18000fdcb  mov     [rbp+arg_10], ecx
0x18000fdce  mov     [rbp+var_20], 4
0x18000fdd5  mov     [rbp+var_1C], 52h ; 'R'
0x18000fddc  lea     rax, [rbp+arg_10]
0x18000fde0  mov     [rbp+var_18], rax
0x18000fde4  mov     [rbp+var_10], edi
0x18000fde7  mov     [rbp+var_C], ecx
0x18000fdea  lea     rax, [rbp+var_20]
0x18000fdee  mov     [rbp+var_8], rax
0x18000fdf2  mov     [rbp+arg_18], edi
0x18000fdf5  mov     [rbp+arg_0], edi
0x18000fdf8  lea     r8, [rbp+arg_0]
0x18000fdfc  xor     edx, edx
0x18000fdfe  lea     ecx, [rdi+3]
0x18000fe01  call    cs:__imp_Tbsi_Get_TCG_Log_Ex
0x18000fe07  test    eax, eax
0x18000fe09  js      short loc_18000FE14
0x18000fe0b  cmp     [rbp+arg_0], edi
0x18000fe0e  jnz     loc_18000FF13
0x18000fe14  lea     rcx, [rbp+arg_8]
0x18000fe18  call    cs:__imp_?TpmGetTpmVersion@@YAJPEAI@Z; TpmGetTpmVersion(uint *)
0x18000fe1e  mov     ebx, eax
0x18000fe20  test    eax, eax
0x18000fe22  jns     short loc_18000FE2B
0x18000fe24  mov     edx, 6B5h
0x18000fe29  jmp     short loc_18000FE7C
0x18000fe2b  cmp     [rbp+arg_8], 2
0x18000fe2f  jnz     loc_18000FF13
0x18000fe35  mov     rbx, [rbp+hObject]
0x18000fe39  test    rbx, rbx
0x18000fe3c  jz      short loc_18000FE59
0x18000fe3e  lea     rcx, [rbp+arg_0]; this
0x18000fe42  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000fe47  mov     rcx, rbx; hObject
0x18000fe4a  call    cs:__imp_NCryptFreeObject
0x18000fe50  lea     rcx, [rbp+arg_0]; this
0x18000fe54  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000fe59  mov     [rbp+hObject], rdi
0x18000fe5d  xor     r8d, r8d; dwFlags
0x18000fe60  lea     rdx, pszProviderName; "Microsoft Platform Crypto Provider"
0x18000fe67  lea     rcx, [rbp+hObject]; phProvider
0x18000fe6b  call    cs:__imp_NCryptOpenStorageProvider
0x18000fe71  mov     ebx, eax
0x18000fe73  test    eax, eax
0x18000fe75  jns     short loc_18000FE94
0x18000fe77  mov     edx, 6BBh; void *
0x18000fe7c  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\tpm\\task\\dll\\t"...
0x18000fe83  mov     r9d, eax; char *
0x18000fe86  mov     rcx, [rbp+18h]; this
0x18000fe8a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000fe8f  jmp     loc_18000FF15
0x18000fe94  mov     rbx, [rbp+var_30]
0x18000fe98  test    rbx, rbx
0x18000fe9b  jz      short loc_18000FEB8
0x18000fe9d  lea     rcx, [rbp+arg_0]; this
0x18000fea1  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000fea6  mov     rcx, rbx; hObject
0x18000fea9  call    cs:__imp_NCryptFreeObject
0x18000feaf  lea     rcx, [rbp+arg_0]; this
0x18000feb3  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000feb8  mov     [rbp+var_30], rdi
0x18000febc  lea     rdx, [rbp+var_30]
0x18000fec0  mov     rcx, [rbp+hObject]
0x18000fec4  call    cs:__imp_?TpmCertGetWindowsAik@@YAJ_KPEA_K@Z; TpmCertGetWindowsAik(unsigned __int64,unsigned __int64 *)
0x18000feca  mov     ebx, eax
0x18000fecc  test    eax, eax
0x18000fece  jns     short loc_18000FED7
0x18000fed0  mov     edx, 6BDh
0x18000fed5  jmp     short loc_18000FE7C
0x18000fed7  mov     [rsp+70h+var_38], edi
0x18000fedb  lea     rax, [rbp+arg_18]
0x18000fedf  mov     [rsp+70h+var_40], rax
0x18000fee4  mov     [rsp+70h+var_48], edi
0x18000fee8  mov     [rsp+70h+var_50], rdi
0x18000feed  lea     r9, [rbp+var_10]
0x18000fef1  mov     r8d, 10000h
0x18000fef7  mov     rdx, [rbp+var_30]
0x18000fefb  xor     ecx, ecx
0x18000fefd  call    cs:__imp_NCryptCreateClaim
0x18000ff03  mov     ebx, eax
0x18000ff05  test    eax, eax
0x18000ff07  jns     short loc_18000FF13
0x18000ff09  mov     edx, 6C7h
0x18000ff0e  jmp     loc_18000FE7C
0x18000ff13  mov     ebx, edi
0x18000ff15  lea     rcx, [rbp+var_30]
0x18000ff19  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18000ff1e  nop
0x18000ff1f  lea     rcx, [rbp+hObject]
0x18000ff23  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18000ff28  mov     eax, ebx
0x18000ff2a  add     rsp, 70h
0x18000ff2e  pop     rdi
0x18000ff2f  pop     rbx
0x18000ff30  pop     rbp
0x18000ff31  retn
```
