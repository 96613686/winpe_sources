# BthLELib_SMPValidatePublicDHKey

- ea: `0x140208e24`
- end: `0x14020902f`
- name: `BthLELib_SMPValidatePublicDHKey`
- size: `523`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1401fdd08`

## callees

- `0x14015f170`
- `0x14015f1b0`
- `0x14015f230`
- `0x14015f298`
- `0x14015f2e0`
- `0x14015f308`
- `0x14015f3a4`
- `0x14015fa50`
- `0x140161a00`
- `0x140208e24`

## import_xrefs

- `ksecdd!BCryptOpenAlgorithmProvider` at `0x140208e63`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x140208e63`
- `ksecdd!BCryptImportKeyPair` at `0x140208fa0`
- `ksecdd!BCryptImportKeyPair` at `0x140208fa0`

## pseudocode

```c
__int64 __fastcall BthLELib_SMPValidatePublicDHKey(_OWORD *a1, _OWORD *a2)
{
  __int64 v4; // rax
  NTSTATUS v5; // ebx
  int v6; // edx
  __int64 v7; // rcx
  int v8; // r8d
  unsigned __int8 *Pool; // rax
  int v10; // edx
  __int64 v11; // r8
  __int64 v12; // rax
  PUCHAR pbInput; // r8
  int v14; // edx
  int v15; // r8d
  _QWORD v17[3]; // [rsp+40h] [rbp-30h] BYREF
  _BYTE v18[24]; // [rsp+58h] [rbp-18h] BYREF
  __int64 v19; // [rsp+A0h] [rbp+30h] BYREF
  BCRYPT_ALG_HANDLE hAlgorithm; // [rsp+A8h] [rbp+38h] BYREF

  hAlgorithm = 0;
  v4 = wil::out_param<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(
         v17,
         &hAlgorithm);
  v5 = BCryptOpenAlgorithmProvider((BCRYPT_ALG_HANDLE *)(v4 + 8), L"ECDH_P256", L"Microsoft Primitive Provider", 0);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void Details::CloseBcryptAlgHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void Details::CloseBcryptAlgHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(v17);
  if ( v5 >= 0 )
  {
    v17[0] = 0;
    v17[1] = 0;
    Pool = (unsigned __int8 *)BthLELibAllocatePoolEx(v7, 72);
    unique_bthlelib_secure_pool::reset((unique_bthlelib_secure_pool *)v17, Pool, 0x48u);
    v11 = v17[0];
    if ( v17[0] )
    {
      *(_DWORD *)v17[0] = 827016005;
      *(_DWORD *)(v11 + 4) = 32;
      *(_OWORD *)(v11 + 8) = *a1;
      *(_OWORD *)(v11 + 24) = a1[1];
      *(_OWORD *)(v11 + 40) = *a2;
      *(_OWORD *)(v11 + 56) = a2[1];
      v19 = 0;
      v12 = wil::out_param<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(
              v18,
              &v19);
      v5 = BCryptImportKeyPair(hAlgorithm, 0, L"ECCPUBLICBLOB", (BCRYPT_KEY_HANDLE *)(v12 + 8), pbInput, 0x48u, 0);
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(v18);
      if ( v5 >= 0 )
      {
        wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v19);
        unique_bthlelib_secure_pool::~unique_bthlelib_secure_pool((unique_bthlelib_secure_pool *)v17);
        v5 = 0;
        goto LABEL_13;
      }
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_sd(
          WPP_GLOBAL_Control->DeviceExtension,
          v14,
          v15,
          21,
          (__int64)WPP_272f78d0e0f932ff6a8fef96cae1cc50_Traceguids);
      wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v19);
    }
    else
    {
      v5 = -1073741670;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_sd(
          WPP_GLOBAL_Control->DeviceExtension,
          v10,
          0,
          LODWORD(v17[0]) + 20,
          (__int64)WPP_272f78d0e0f932ff6a8fef96cae1cc50_Traceguids);
    }
    unique_bthlelib_secure_pool::~unique_bthlelib_secure_pool((unique_bthlelib_secure_pool *)v17);
  }
  else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_SF_sd(
      WPP_GLOBAL_Control->DeviceExtension,
      v6,
      v8,
      19,
      (__int64)WPP_272f78d0e0f932ff6a8fef96cae1cc50_Traceguids);
  }
LABEL_13:
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void Details::CloseBcryptAlgHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void Details::CloseBcryptAlgHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hAlgorithm);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140208e24  mov     [rsp-18h+arg_0], rbx
0x140208e29  push    rbp
0x140208e2a  push    rsi
0x140208e2b  push    rdi
0x140208e2c  mov     rbp, rsp
0x140208e2f  sub     rsp, 70h
0x140208e33  mov     rdi, rdx
0x140208e36  mov     [rbp+hAlgorithm], 0
0x140208e3e  mov     rsi, rcx
0x140208e41  lea     rdx, [rbp+hAlgorithm]
0x140208e45  lea     rcx, [rbp+var_30]
0x140208e49  call    ??$out_param@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AU?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@0@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@0@@Z; wil::out_param<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &)
0x140208e4e  xor     r9d, r9d; dwFlags
0x140208e51  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x140208e58  lea     rdx, aEcdhP256; "ECDH_P256"
0x140208e5f  lea     rcx, [rax+8]; phAlgorithm
0x140208e63  call    cs:__imp_BCryptOpenAlgorithmProvider
0x140208e6a  nop     dword ptr [rax+rax+00h]
0x140208e6f  lea     rcx, [rbp+var_30]
0x140208e73  mov     ebx, eax
0x140208e75  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CloseBcryptAlgHandle@Details@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&Details::CloseBcryptAlgHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&Details::CloseBcryptAlgHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(void)
0x140208e7a  test    ebx, ebx
0x140208e7c  jns     short loc_140208EBD
0x140208e7e  lea     rcx, WPP_RECORDER_INITIALIZED
0x140208e85  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140208e8c  jz      loc_140209013
0x140208e92  mov     rcx, cs:WPP_GLOBAL_Control
0x140208e99  lea     rax, WPP_272f78d0e0f932ff6a8fef96cae1cc50_Traceguids
0x140208ea0  mov     r9d, 13h
0x140208ea6  mov     [rsp+70h+dwFlags], ebx
0x140208eaa  mov     [rsp+70h+pbInput], rax
0x140208eaf  mov     rcx, [rcx+40h]
0x140208eb3  call    WPP_RECORDER_SF_sd
0x140208eb8  jmp     loc_140209013
0x140208ebd  mov     ebx, 48h ; 'H'
0x140208ec2  mov     [rbp+var_30], 0
0x140208eca  mov     edx, ebx
0x140208ecc  mov     [rbp+var_28], 0
0x140208ed4  call    BthLELibAllocatePoolEx
0x140208ed9  mov     rdx, rax; unsigned __int8 *
0x140208edc  lea     rcx, [rbp+var_30]; this
0x140208ee0  mov     r8d, ebx; unsigned __int64
0x140208ee3  call    ?reset@unique_bthlelib_secure_pool@@QEAAXPEAE_K@Z; unique_bthlelib_secure_pool::reset(uchar *,unsigned __int64)
0x140208ee8  mov     r8, [rbp+var_30]
0x140208eec  test    r8, r8
0x140208eef  jnz     short loc_140208F38
0x140208ef1  lea     rcx, WPP_RECORDER_INITIALIZED
0x140208ef8  mov     ebx, 0C000009Ah
0x140208efd  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140208f04  jz      short loc_140208F2A
0x140208f06  mov     rcx, cs:WPP_GLOBAL_Control
0x140208f0d  lea     rax, WPP_272f78d0e0f932ff6a8fef96cae1cc50_Traceguids
0x140208f14  lea     r9d, [r8+14h]
0x140208f18  mov     [rsp+70h+dwFlags], ebx
0x140208f1c  mov     [rsp+70h+pbInput], rax
0x140208f21  mov     rcx, [rcx+40h]
0x140208f25  call    WPP_RECORDER_SF_sd
0x140208f2a  lea     rcx, [rbp+var_30]; this
0x140208f2e  call    ??1unique_bthlelib_secure_pool@@QEAA@XZ; unique_bthlelib_secure_pool::~unique_bthlelib_secure_pool(void)
0x140208f33  jmp     loc_140209013
0x140208f38  mov     dword ptr [r8], 314B4345h
0x140208f3f  lea     rdx, [rbp+arg_10]
0x140208f43  mov     dword ptr [r8+4], 20h ; ' '
0x140208f4b  lea     rcx, [rbp+var_18]
0x140208f4f  movups  xmm0, xmmword ptr [rsi]
0x140208f52  movups  xmmword ptr [r8+8], xmm0
0x140208f57  movups  xmm1, xmmword ptr [rsi+10h]
0x140208f5b  movups  xmmword ptr [r8+18h], xmm1
0x140208f60  movups  xmm0, xmmword ptr [rdi]
0x140208f63  movups  xmmword ptr [r8+28h], xmm0
0x140208f68  movups  xmm1, xmmword ptr [rdi+10h]
0x140208f6c  movups  xmmword ptr [r8+38h], xmm1
0x140208f71  mov     [rbp+arg_10], 0
0x140208f79  call    ??$out_param@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AU?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@0@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@0@@Z; wil::out_param<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &)
0x140208f7e  mov     rcx, [rbp+hAlgorithm]; hAlgorithm
0x140208f82  xor     edx, edx; hImportKey
0x140208f84  mov     [rsp+70h+dwFlags], 0; dwFlags
0x140208f8c  mov     [rsp+70h+cbInput], ebx; cbInput
0x140208f90  mov     [rsp+70h+pbInput], r8; pbInput
0x140208f95  lea     r9, [rax+8]; phKey
0x140208f99  lea     r8, aEccpublicblob; "ECCPUBLICBLOB"
0x140208fa0  call    cs:__imp_BCryptImportKeyPair
0x140208fa7  nop     dword ptr [rax+rax+00h]
0x140208fac  lea     rcx, [rbp+var_18]
0x140208fb0  mov     ebx, eax
0x140208fb2  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(void)
0x140208fb7  test    ebx, ebx
0x140208fb9  jns     short loc_140208FFF
0x140208fbb  lea     rcx, WPP_RECORDER_INITIALIZED
0x140208fc2  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140208fc9  jz      short loc_140208FF1
0x140208fcb  mov     rcx, cs:WPP_GLOBAL_Control
0x140208fd2  lea     rax, WPP_272f78d0e0f932ff6a8fef96cae1cc50_Traceguids
0x140208fd9  mov     r9d, 15h
0x140208fdf  mov     [rsp+70h+dwFlags], ebx
0x140208fe3  mov     [rsp+70h+pbInput], rax
0x140208fe8  mov     rcx, [rcx+40h]
0x140208fec  call    WPP_RECORDER_SF_sd
0x140208ff1  lea     rcx, [rbp+arg_10]
0x140208ff5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x140208ffa  jmp     loc_140208F2A
0x140208fff  lea     rcx, [rbp+arg_10]
0x140209003  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x140209008  lea     rcx, [rbp+var_30]; this
0x14020900c  call    ??1unique_bthlelib_secure_pool@@QEAA@XZ; unique_bthlelib_secure_pool::~unique_bthlelib_secure_pool(void)
0x140209011  xor     ebx, ebx
0x140209013  lea     rcx, [rbp+hAlgorithm]
0x140209017  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CloseBcryptAlgHandle@Details@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&Details::CloseBcryptAlgHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&Details::CloseBcryptAlgHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x14020901c  mov     eax, ebx
0x14020901e  mov     rbx, [rsp+70h+arg_0]
0x140209026  add     rsp, 70h
0x14020902a  pop     rdi
0x14020902b  pop     rsi
0x14020902c  pop     rbp
0x14020902d  retn
```
