# BthLELib_CalculateAesCmac

- ea: `0x140207524`
- end: `0x1402076ee`
- name: `BthLELib_CalculateAesCmac`
- size: `458`
- prototype: `__int64 __fastcall(PUCHAR pbInput, ULONG cbInput, PUCHAR pbSecret, PUCHAR pbOutput)`
- caller_count: `7`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x140206e30`
- `0x1402076f4`
- `0x140207828`
- `0x140207960`
- `0x140207b14`
- `0x140208344`
- `0x140208588`

## callees

- `0x14015f170`
- `0x14015f18c`
- `0x14015f230`
- `0x14015f274`
- `0x14015f2e0`
- `0x14015fa50`
- `0x140207524`

## import_xrefs

- `ksecdd!BCryptOpenAlgorithmProvider` at `0x140207569`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x140207569`
- `ksecdd!BCryptCreateHash` at `0x1402075fb`
- `ksecdd!BCryptCreateHash` at `0x1402075fb`
- `ksecdd!BCryptHashData` at `0x140207664`
- `ksecdd!BCryptHashData` at `0x140207664`
- `ksecdd!BCryptFinishHash` at `0x1402076a0`
- `ksecdd!BCryptFinishHash` at `0x1402076a0`

## pseudocode

```c
__int64 __fastcall BthLELib_CalculateAesCmac(PUCHAR pbInput, ULONG cbInput, PUCHAR pbSecret, PUCHAR pbOutput)
{
  __int64 v8; // rax
  NTSTATUS Hash; // ebx
  int v10; // edx
  int v11; // r8d
  __int64 v12; // rax
  int v13; // edx
  int v14; // r8d
  int v15; // r9d
  BCRYPT_HASH_HANDLE hHash; // [rsp+40h] [rbp-38h] BYREF
  BCRYPT_ALG_HANDLE hAlgorithm; // [rsp+48h] [rbp-30h] BYREF
  _BYTE v19[40]; // [rsp+50h] [rbp-28h] BYREF

  hAlgorithm = 0;
  v8 = wil::out_param<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(
         v19,
         &hAlgorithm);
  Hash = BCryptOpenAlgorithmProvider((BCRYPT_ALG_HANDLE *)(v8 + 8), L"AES-CMAC", L"Microsoft Primitive Provider", 0);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void Details::CloseBcryptAlgHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void Details::CloseBcryptAlgHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(v19);
  if ( Hash >= 0 )
  {
    hHash = 0;
    v12 = wil::out_param<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(
            v19,
            &hHash);
    Hash = BCryptCreateHash(hAlgorithm, (BCRYPT_HASH_HANDLE *)(v12 + 8), 0, 0, pbSecret, 0x10u, 0);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(v19);
    if ( Hash >= 0 )
    {
      Hash = BCryptHashData(hHash, pbInput, cbInput, 0);
      if ( Hash >= 0 )
      {
        Hash = BCryptFinishHash(hHash, pbOutput, 0x10u, 0);
        if ( Hash >= 0 )
        {
          wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hHash);
          Hash = 0;
          goto LABEL_16;
        }
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_8;
        v15 = 13;
      }
      else
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_8;
        v15 = 12;
      }
    }
    else
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
LABEL_8:
        wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hHash);
        goto LABEL_16;
      }
      v15 = 11;
    }
    WPP_RECORDER_SF_sd(
      WPP_GLOBAL_Control->DeviceExtension,
      v13,
      v14,
      v15,
      (__int64)WPP_272f78d0e0f932ff6a8fef96cae1cc50_Traceguids);
    goto LABEL_8;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_sd(
      WPP_GLOBAL_Control->DeviceExtension,
      v10,
      v11,
      10,
      (__int64)WPP_272f78d0e0f932ff6a8fef96cae1cc50_Traceguids);
LABEL_16:
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void Details::CloseBcryptAlgHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void Details::CloseBcryptAlgHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hAlgorithm);
  return (unsigned int)Hash;
}

```

## disassembly

```asm
0x140207524  push    rbp
0x140207526  push    rbx
0x140207527  push    rsi
0x140207528  push    rdi
0x140207529  push    r14
0x14020752b  push    r15
0x14020752d  mov     rbp, rsp
0x140207530  sub     rsp, 78h
0x140207534  mov     esi, edx
0x140207536  mov     [rbp+hAlgorithm], 0
0x14020753e  mov     r14, rcx
0x140207541  lea     rdx, [rbp+hAlgorithm]
0x140207545  lea     rcx, [rbp+var_28]
0x140207549  mov     rdi, r9
0x14020754c  mov     r15, r8
0x14020754f  call    ??$out_param@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AU?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@0@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@0@@Z; wil::out_param<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &)
0x140207554  xor     r9d, r9d; dwFlags
0x140207557  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x14020755e  lea     rdx, aAesCmac; "AES-CMAC"
0x140207565  lea     rcx, [rax+8]; phAlgorithm
0x140207569  call    cs:__imp_BCryptOpenAlgorithmProvider
0x140207570  nop     dword ptr [rax+rax+00h]
0x140207575  lea     rcx, [rbp+var_28]
0x140207579  mov     ebx, eax
0x14020757b  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CloseBcryptAlgHandle@Details@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&Details::CloseBcryptAlgHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&Details::CloseBcryptAlgHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(void)
0x140207580  test    ebx, ebx
0x140207582  jns     short loc_1402075C3
0x140207584  lea     rcx, WPP_RECORDER_INITIALIZED
0x14020758b  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140207592  jz      loc_1402076D5
0x140207598  lea     rcx, WPP_272f78d0e0f932ff6a8fef96cae1cc50_Traceguids
0x14020759f  mov     [rsp+78h+dwFlags], ebx
0x1402075a3  mov     [rsp+78h+pbSecret], rcx
0x1402075a8  mov     r9d, 0Ah
0x1402075ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1402075b5  mov     rcx, [rcx+40h]
0x1402075b9  call    WPP_RECORDER_SF_sd
0x1402075be  jmp     loc_1402076D5
0x1402075c3  lea     rdx, [rbp+hHash]
0x1402075c7  mov     [rbp+hHash], 0
0x1402075cf  lea     rcx, [rbp+var_28]
0x1402075d3  call    ??$out_param@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AU?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@0@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@0@@Z; wil::out_param<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &)
0x1402075d8  mov     rcx, [rbp+hAlgorithm]; hAlgorithm
0x1402075dc  xor     r9d, r9d; cbHashObject
0x1402075df  mov     [rsp+78h+dwFlags], 0; dwFlags
0x1402075e7  xor     r8d, r8d; pbHashObject
0x1402075ea  mov     [rsp+78h+cbSecret], 10h; cbSecret
0x1402075f2  lea     rdx, [rax+8]; phHash
0x1402075f6  mov     [rsp+78h+pbSecret], r15; pbSecret
0x1402075fb  call    cs:__imp_BCryptCreateHash
0x140207602  nop     dword ptr [rax+rax+00h]
0x140207607  lea     rcx, [rbp+var_28]
0x14020760b  mov     ebx, eax
0x14020760d  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(void)
0x140207612  test    ebx, ebx
0x140207614  jns     short loc_140207657
0x140207616  lea     rcx, WPP_RECORDER_INITIALIZED
0x14020761d  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140207624  jz      short loc_14020764C
0x140207626  mov     r9d, 0Bh
0x14020762c  mov     [rsp+78h+dwFlags], ebx
0x140207630  lea     rcx, WPP_272f78d0e0f932ff6a8fef96cae1cc50_Traceguids
0x140207637  mov     [rsp+78h+pbSecret], rcx
0x14020763c  mov     rcx, cs:WPP_GLOBAL_Control
0x140207643  mov     rcx, [rcx+40h]
0x140207647  call    WPP_RECORDER_SF_sd
0x14020764c  lea     rcx, [rbp+hHash]
0x140207650  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x140207655  jmp     short loc_1402076D5
0x140207657  mov     rcx, [rbp+hHash]; hHash
0x14020765b  xor     r9d, r9d; dwFlags
0x14020765e  mov     r8d, esi; cbInput
0x140207661  mov     rdx, r14; pbInput
0x140207664  call    cs:__imp_BCryptHashData
0x14020766b  nop     dword ptr [rax+rax+00h]
0x140207670  mov     ebx, eax
0x140207672  test    eax, eax
0x140207674  jns     short loc_140207692
0x140207676  lea     rcx, WPP_RECORDER_INITIALIZED
0x14020767d  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140207684  jz      short loc_14020764C
0x140207686  mov     r9d, 0Ch
0x14020768c  mov     [rsp+78h+dwFlags], eax
0x140207690  jmp     short loc_140207630
0x140207692  mov     rcx, [rbp+hHash]; hHash
0x140207696  xor     r9d, r9d; dwFlags
0x140207699  mov     rdx, rdi; pbOutput
0x14020769c  lea     r8d, [r9+10h]; cbOutput
0x1402076a0  call    cs:__imp_BCryptFinishHash
0x1402076a7  nop     dword ptr [rax+rax+00h]
0x1402076ac  mov     ebx, eax
0x1402076ae  test    eax, eax
0x1402076b0  jns     short loc_1402076CA
0x1402076b2  lea     rcx, WPP_RECORDER_INITIALIZED
0x1402076b9  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1402076c0  jz      short loc_14020764C
0x1402076c2  mov     r9d, 0Dh
0x1402076c8  jmp     short loc_14020768C
0x1402076ca  lea     rcx, [rbp+hHash]
0x1402076ce  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1402076d3  xor     ebx, ebx
0x1402076d5  lea     rcx, [rbp+hAlgorithm]
0x1402076d9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CloseBcryptAlgHandle@Details@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&Details::CloseBcryptAlgHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&Details::CloseBcryptAlgHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1402076de  mov     eax, ebx
0x1402076e0  add     rsp, 78h
0x1402076e4  pop     r15
0x1402076e6  pop     r14
0x1402076e8  pop     rdi
0x1402076e9  pop     rsi
0x1402076ea  pop     rbx
0x1402076eb  pop     rbp
0x1402076ec  retn
```
