# BthLELib_SMPGenerateDHKeyPairs

- ea: `0x140208088`
- end: `0x14020833d`
- name: `BthLELib_SMPGenerateDHKeyPairs`
- size: `693`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1401f30d4`
- `0x1401fd1bc`

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
- `0x140208088`

## import_xrefs

- `ksecdd!BCryptOpenAlgorithmProvider` at `0x1402080cb`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x1402080cb`
- `ksecdd!BCryptGenerateKeyPair` at `0x14020814b`
- `ksecdd!BCryptGenerateKeyPair` at `0x14020814b`
- `ksecdd!BCryptFinalizeKeyPair` at `0x1402081b0`
- `ksecdd!BCryptFinalizeKeyPair` at `0x1402081b0`
- `ksecdd!BCryptExportKey` at `0x140208281`
- `ksecdd!BCryptExportKey` at `0x140208281`

## pseudocode

```c
__int64 __fastcall BthLELib_SMPGenerateDHKeyPairs(_OWORD *a1, _OWORD *a2, _OWORD *a3)
{
  __int64 v6; // rax
  NTSTATUS KeyPair; // ebx
  int v8; // edx
  int v9; // r8d
  __int64 v10; // rax
  int v11; // edx
  int v12; // r8d
  int v13; // r9d
  __int64 v14; // rcx
  unsigned __int8 *Pool; // rax
  int v16; // edx
  int v17; // r8d
  PUCHAR v18; // rbx
  int v19; // edx
  NTSTATUS v20; // edi
  int v21; // r8d
  BCRYPT_KEY_HANDLE hKey; // [rsp+40h] [rbp-38h] BYREF
  BCRYPT_ALG_HANDLE hAlgorithm; // [rsp+48h] [rbp-30h] BYREF
  PUCHAR pbOutput[5]; // [rsp+50h] [rbp-28h] BYREF
  ULONG pcbResult; // [rsp+C8h] [rbp+50h] BYREF

  hAlgorithm = 0;
  v6 = wil::out_param<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(
         pbOutput,
         &hAlgorithm);
  KeyPair = BCryptOpenAlgorithmProvider((BCRYPT_ALG_HANDLE *)(v6 + 8), L"ECDH_P256", L"Microsoft Primitive Provider", 0);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void Details::CloseBcryptAlgHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void Details::CloseBcryptAlgHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(pbOutput);
  if ( KeyPair < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_sd(
        WPP_GLOBAL_Control->DeviceExtension,
        v8,
        v9,
        14,
        (__int64)WPP_272f78d0e0f932ff6a8fef96cae1cc50_Traceguids);
    goto LABEL_21;
  }
  hKey = 0;
  v10 = wil::out_param<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(
          pbOutput,
          &hKey);
  KeyPair = BCryptGenerateKeyPair(hAlgorithm, (BCRYPT_KEY_HANDLE *)(v10 + 8), 0x100u, 0);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(pbOutput);
  if ( KeyPair < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
LABEL_8:
      wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hKey);
      goto LABEL_21;
    }
    v13 = 15;
LABEL_7:
    WPP_RECORDER_SF_sd(
      WPP_GLOBAL_Control->DeviceExtension,
      v11,
      v12,
      v13,
      (__int64)WPP_272f78d0e0f932ff6a8fef96cae1cc50_Traceguids);
    goto LABEL_8;
  }
  KeyPair = BCryptFinalizeKeyPair(hKey, 0);
  if ( KeyPair < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_8;
    v13 = 16;
    goto LABEL_7;
  }
  pbOutput[0] = 0;
  pbOutput[1] = 0;
  Pool = (unsigned __int8 *)BthLELibAllocatePoolEx(v14, 104);
  unique_bthlelib_secure_pool::reset((unique_bthlelib_secure_pool *)pbOutput, Pool, 0x68u);
  v18 = pbOutput[0];
  if ( !pbOutput[0] )
  {
    KeyPair = -1073741670;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_sd(
        WPP_GLOBAL_Control->DeviceExtension,
        v16,
        v17,
        17,
        (__int64)WPP_272f78d0e0f932ff6a8fef96cae1cc50_Traceguids);
    unique_bthlelib_secure_pool::~unique_bthlelib_secure_pool((unique_bthlelib_secure_pool *)pbOutput);
    goto LABEL_8;
  }
  pcbResult = 104;
  v20 = BCryptExportKey(hKey, 0, L"ECCPRIVATEBLOB", pbOutput[0], 0x68u, &pcbResult, 0);
  if ( v20 >= 0 )
  {
    *a2 = *(_OWORD *)(v18 + 8);
    a2[1] = *(_OWORD *)(v18 + 24);
    *a3 = *(_OWORD *)(v18 + 40);
    a3[1] = *(_OWORD *)(v18 + 56);
    *a1 = *(_OWORD *)(v18 + 72);
    a1[1] = *(_OWORD *)(v18 + 88);
    unique_bthlelib_secure_pool::~unique_bthlelib_secure_pool((unique_bthlelib_secure_pool *)pbOutput);
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hKey);
    KeyPair = 0;
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_sd(
        WPP_GLOBAL_Control->DeviceExtension,
        v19,
        v21,
        18,
        (__int64)WPP_272f78d0e0f932ff6a8fef96cae1cc50_Traceguids);
    unique_bthlelib_secure_pool::~unique_bthlelib_secure_pool((unique_bthlelib_secure_pool *)pbOutput);
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hKey);
    KeyPair = v20;
  }
LABEL_21:
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void Details::CloseBcryptAlgHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void Details::CloseBcryptAlgHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hAlgorithm);
  return (unsigned int)KeyPair;
}

```

## disassembly

```asm
0x140208088  push    rbp
0x14020808a  push    rbx
0x14020808b  push    rsi
0x14020808c  push    rdi
0x14020808d  push    r14
0x14020808f  push    r15
0x140208091  mov     rbp, rsp
0x140208094  sub     rsp, 78h
0x140208098  mov     r14, rdx
0x14020809b  mov     [rbp+hAlgorithm], 0
0x1402080a3  mov     r15, rcx
0x1402080a6  lea     rdx, [rbp+hAlgorithm]
0x1402080aa  lea     rcx, [rbp+pbOutput]
0x1402080ae  mov     rsi, r8
0x1402080b1  call    ??$out_param@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AU?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@0@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@0@@Z; wil::out_param<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &)
0x1402080b6  xor     r9d, r9d; dwFlags
0x1402080b9  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x1402080c0  lea     rdx, aEcdhP256; "ECDH_P256"
0x1402080c7  lea     rcx, [rax+8]; phAlgorithm
0x1402080cb  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1402080d2  nop     dword ptr [rax+rax+00h]
0x1402080d7  lea     rcx, [rbp+pbOutput]
0x1402080db  mov     ebx, eax
0x1402080dd  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CloseBcryptAlgHandle@Details@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&Details::CloseBcryptAlgHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&Details::CloseBcryptAlgHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(void)
0x1402080e2  test    ebx, ebx
0x1402080e4  jns     short loc_140208125
0x1402080e6  lea     rcx, WPP_RECORDER_INITIALIZED
0x1402080ed  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1402080f4  jz      loc_140208324
0x1402080fa  lea     rcx, WPP_272f78d0e0f932ff6a8fef96cae1cc50_Traceguids
0x140208101  mov     [rsp+78h+dwFlags], ebx
0x140208105  mov     qword ptr [rsp+78h+cbOutput], rcx
0x14020810a  mov     r9d, 0Eh
0x140208110  mov     rcx, cs:WPP_GLOBAL_Control
0x140208117  mov     rcx, [rcx+40h]
0x14020811b  call    WPP_RECORDER_SF_sd
0x140208120  jmp     loc_140208324
0x140208125  lea     rdx, [rbp+hKey]
0x140208129  mov     [rbp+hKey], 0
0x140208131  lea     rcx, [rbp+pbOutput]
0x140208135  call    ??$out_param@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AU?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@0@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@0@@Z; wil::out_param<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &)
0x14020813a  mov     rcx, [rbp+hAlgorithm]; hAlgorithm
0x14020813e  xor     r9d, r9d; dwFlags
0x140208141  mov     r8d, 100h; dwLength
0x140208147  lea     rdx, [rax+8]; phKey
0x14020814b  call    cs:__imp_BCryptGenerateKeyPair
0x140208152  nop     dword ptr [rax+rax+00h]
0x140208157  lea     rcx, [rbp+pbOutput]
0x14020815b  mov     ebx, eax
0x14020815d  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(void)
0x140208162  test    ebx, ebx
0x140208164  jns     short loc_1402081AA
0x140208166  lea     rcx, WPP_RECORDER_INITIALIZED
0x14020816d  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140208174  jz      short loc_14020819C
0x140208176  mov     r9d, 0Fh
0x14020817c  mov     [rsp+78h+dwFlags], ebx
0x140208180  lea     rcx, WPP_272f78d0e0f932ff6a8fef96cae1cc50_Traceguids
0x140208187  mov     qword ptr [rsp+78h+cbOutput], rcx
0x14020818c  mov     rcx, cs:WPP_GLOBAL_Control
0x140208193  mov     rcx, [rcx+40h]
0x140208197  call    WPP_RECORDER_SF_sd
0x14020819c  lea     rcx, [rbp+hKey]
0x1402081a0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1402081a5  jmp     loc_140208324
0x1402081aa  mov     rcx, [rbp+hKey]; hKey
0x1402081ae  xor     edx, edx; dwFlags
0x1402081b0  call    cs:__imp_BCryptFinalizeKeyPair
0x1402081b7  nop     dword ptr [rax+rax+00h]
0x1402081bc  mov     ebx, eax
0x1402081be  test    eax, eax
0x1402081c0  jns     short loc_1402081DE
0x1402081c2  lea     rcx, WPP_RECORDER_INITIALIZED
0x1402081c9  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1402081d0  jz      short loc_14020819C
0x1402081d2  mov     r9d, 10h
0x1402081d8  mov     [rsp+78h+dwFlags], eax
0x1402081dc  jmp     short loc_140208180
0x1402081de  mov     edi, 68h ; 'h'
0x1402081e3  mov     [rbp+pbOutput], 0
0x1402081eb  mov     edx, edi
0x1402081ed  mov     [rbp+var_20], 0
0x1402081f5  call    BthLELibAllocatePoolEx
0x1402081fa  mov     rdx, rax; unsigned __int8 *
0x1402081fd  lea     rcx, [rbp+pbOutput]; this
0x140208201  mov     r8d, edi; unsigned __int64
0x140208204  call    ?reset@unique_bthlelib_secure_pool@@QEAAXPEAE_K@Z; unique_bthlelib_secure_pool::reset(uchar *,unsigned __int64)
0x140208209  mov     rbx, [rbp+pbOutput]
0x14020820d  test    rbx, rbx
0x140208210  jnz     short loc_140208259
0x140208212  lea     rcx, WPP_RECORDER_INITIALIZED
0x140208219  mov     ebx, 0C000009Ah
0x14020821e  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140208225  jz      short loc_14020824B
0x140208227  lea     rcx, WPP_272f78d0e0f932ff6a8fef96cae1cc50_Traceguids
0x14020822e  mov     [rsp+78h+dwFlags], ebx
0x140208232  mov     qword ptr [rsp+78h+cbOutput], rcx
0x140208237  lea     r9d, [rdi-57h]
0x14020823b  mov     rcx, cs:WPP_GLOBAL_Control
0x140208242  mov     rcx, [rcx+40h]
0x140208246  call    WPP_RECORDER_SF_sd
0x14020824b  lea     rcx, [rbp+pbOutput]; this
0x14020824f  call    ??1unique_bthlelib_secure_pool@@QEAA@XZ; unique_bthlelib_secure_pool::~unique_bthlelib_secure_pool(void)
0x140208254  jmp     loc_14020819C
0x140208259  mov     rcx, [rbp+hKey]; hKey
0x14020825d  lea     rax, [rbp+arg_18]
0x140208261  mov     [rsp+78h+dwFlags], 0; dwFlags
0x140208269  lea     r8, aEccprivateblob; "ECCPRIVATEBLOB"
0x140208270  mov     [rsp+78h+pcbResult], rax; pcbResult
0x140208275  mov     r9, rbx; pbOutput
0x140208278  xor     edx, edx; hExportKey
0x14020827a  mov     [rsp+78h+cbOutput], edi; cbOutput
0x14020827e  mov     [rbp+arg_18], edi
0x140208281  call    cs:__imp_BCryptExportKey
0x140208288  nop     dword ptr [rax+rax+00h]
0x14020828d  mov     edi, eax
0x14020828f  test    eax, eax
0x140208291  jns     short loc_1402082DF
0x140208293  lea     rcx, WPP_RECORDER_INITIALIZED
0x14020829a  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1402082a1  jz      short loc_1402082C9
0x1402082a3  lea     rcx, WPP_272f78d0e0f932ff6a8fef96cae1cc50_Traceguids
0x1402082aa  mov     [rsp+78h+dwFlags], eax
0x1402082ae  mov     qword ptr [rsp+78h+cbOutput], rcx
0x1402082b3  mov     r9d, 12h
0x1402082b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1402082c0  mov     rcx, [rcx+40h]
0x1402082c4  call    WPP_RECORDER_SF_sd
0x1402082c9  lea     rcx, [rbp+pbOutput]; this
0x1402082cd  call    ??1unique_bthlelib_secure_pool@@QEAA@XZ; unique_bthlelib_secure_pool::~unique_bthlelib_secure_pool(void)
0x1402082d2  lea     rcx, [rbp+hKey]
0x1402082d6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1402082db  mov     ebx, edi
0x1402082dd  jmp     short loc_140208324
0x1402082df  movups  xmm0, xmmword ptr [rbx+8]
0x1402082e3  lea     rcx, [rbp+pbOutput]; this
0x1402082e7  movups  xmmword ptr [r14], xmm0
0x1402082eb  movups  xmm1, xmmword ptr [rbx+18h]
0x1402082ef  movups  xmmword ptr [r14+10h], xmm1
0x1402082f4  movups  xmm0, xmmword ptr [rbx+28h]
0x1402082f8  movups  xmmword ptr [rsi], xmm0
0x1402082fb  movups  xmm1, xmmword ptr [rbx+38h]
0x1402082ff  movups  xmmword ptr [rsi+10h], xmm1
0x140208303  movups  xmm0, xmmword ptr [rbx+48h]
0x140208307  movups  xmmword ptr [r15], xmm0
0x14020830b  movups  xmm1, xmmword ptr [rbx+58h]
0x14020830f  movups  xmmword ptr [r15+10h], xmm1
0x140208314  call    ??1unique_bthlelib_secure_pool@@QEAA@XZ; unique_bthlelib_secure_pool::~unique_bthlelib_secure_pool(void)
0x140208319  lea     rcx, [rbp+hKey]
0x14020831d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x140208322  xor     ebx, ebx
0x140208324  lea     rcx, [rbp+hAlgorithm]
0x140208328  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CloseBcryptAlgHandle@Details@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&Details::CloseBcryptAlgHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&Details::CloseBcryptAlgHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x14020832d  mov     eax, ebx
0x14020832f  add     rsp, 78h
0x140208333  pop     r15
0x140208335  pop     r14
0x140208337  pop     rdi
0x140208338  pop     rsi
0x140208339  pop     rbx
0x14020833a  pop     rbp
0x14020833b  retn
```
