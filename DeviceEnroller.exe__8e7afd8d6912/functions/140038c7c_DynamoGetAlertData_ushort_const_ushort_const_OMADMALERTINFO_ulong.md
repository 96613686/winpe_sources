# DynamoGetAlertData(ushort const *,ushort const *,OMADMALERTINFO * *,ulong *)

- ea: `0x140038c7c`
- end: `0x1400390d1`
- name: `?DynamoGetAlertData@@YAJPEBG0PEAPEAUOMADMALERTINFO@@PEAK@Z`
- size: `1109`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, struct OMADMALERTINFO **, unsigned int *)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140019a6c`

## callees

- `0x1400042f0`
- `0x140004e28`
- `0x1400095b4`
- `0x14000a6a8`
- `0x140036bd0`
- `0x140036d50`
- `0x140037194`
- `0x1400382b0`
- `0x1400388b8`
- `0x140038c7c`
- `0x140039f28`
- `0x140039fe8`
- `0x14003b9d4`
- `0x14003bdac`
- `0x14005d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140038eef`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140038f83`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140038ffd`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140038eef`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140038f83`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140038ffd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140038ed3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140038ed3`

## pseudocode

```c
__int64 __fastcall DynamoGetAlertData(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        struct OMADMALERTINFO **a3,
        unsigned int *a4)
{
  __int64 v8; // rdx
  __int64 result; // rax
  __int64 v10; // rcx
  __int64 v11; // rdx
  unsigned __int64 v12; // rax
  struct OMADMALERTINFO *v13; // rsi
  unsigned __int64 v14; // rcx
  int v15; // ebx
  unsigned __int64 v16; // r15
  __int64 i; // rcx
  unsigned __int64 v18; // rbx
  __int128 *v19; // rcx
  __int128 v20; // xmm6
  __int128 v21; // xmm7
  __int128 v22; // xmm8
  __int128 v23; // xmm9
  __int64 v24; // r8
  const char *v25; // r9
  void (__fastcall ***v26)(_QWORD, __int64); // rcx
  const char *v27; // r9
  __int64 v28; // r8
  const char *v29; // r9
  void (__fastcall ***v30)(_QWORD, __int64); // rcx
  __int64 v31; // r8
  const char *v32; // r9
  void (__fastcall ***v33)(_QWORD, __int64); // rcx
  void (__fastcall ***v34)(_QWORD, __int64); // [rsp+20h] [rbp-298h] BYREF
  HANDLE hMutex; // [rsp+28h] [rbp-290h] BYREF
  LPVOID pv[2]; // [rsp+30h] [rbp-288h] BYREF
  unsigned int v37[2]; // [rsp+40h] [rbp-278h] BYREF
  __int64 v38; // [rsp+48h] [rbp-270h]
  _QWORD v39[42]; // [rsp+60h] [rbp-258h] BYREF
  char v40[144]; // [rsp+1B0h] [rbp-108h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+0h]

  memset_0(v40, 0, 0x81u);
  anonymous_namespace_::GetCorrelationVector(v40);
  wil::ActivityBase<DynamoProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DynamoProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v39,
    "GetAlertDataActivity");
  v39[0] = &DynamicManagementProvider::GetAlertDataActivity::`vftable';
  DynamicManagementProvider::GetAlertDataActivity::StartActivityWithCorrelationVector(
    (DynamicManagementProvider::GetAlertDataActivity *)v39,
    v40);
  if ( !a3 )
  {
    v8 = 686;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\dynamicmanagement.cpp",
      (const char *)0x80070057LL,
      (int)v34);
    v39[0] = &DynamicManagementProvider::GetAlertDataActivity::`vftable';
    wil::ActivityBase<DynamoProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v39);
    wil::ActivityBase<DynamoProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DynamoProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v39);
    return 2147942487LL;
  }
  *a3 = 0;
  if ( !a4 )
  {
    v8 = 689;
    goto LABEL_3;
  }
  try
  {
    *a4 = 0;
    Dynamo::DataStoreFactory_t<Dynamo::details::DataStore>::GetStore(&v34, a1, a2);
    (*v34)[5](v34, (__int64)&hMutex);
    (*v34)[13](v34, (__int64)v37);
    ((void (__fastcall *)(void (__fastcall ***)(_QWORD, __int64)))(*v34)[14])(v34);
    v10 = v38;
    v11 = *(_QWORD *)v37;
    if ( *(_QWORD *)v37 != v38 )
    {
      pv[0] = 0;
      pv[1] = 0;
      v12 = (v38 - *(_QWORD *)v37) >> 6;
      if ( v12 > 0xFFFFFFFF )
      {
        *a4 = -1;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2BF,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\dynamicmanagement.cpp",
          (const char *)0x80070216LL,
          (int)v34);
        std::vector<wil::unique_struct<OMADMALERTINFO,long (OMADMALERTINFO *),&long dmstd::LocalFreeOmadmAlertInfo(OMADMALERTINFO *),std::nullptr_t,0>>::~vector<wil::unique_struct<OMADMALERTINFO,long (OMADMALERTINFO *),&long dmstd::LocalFreeOmadmAlertInfo(OMADMALERTINFO *),std::nullptr_t,0>>(v37);
        if ( hMutex && !ReleaseMutex(hMutex) )
          wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v28, v29);
        v30 = v34;
        v34 = 0;
        if ( v30 )
          (**v30)(v30, 1);
        v39[0] = &DynamicManagementProvider::GetAlertDataActivity::`vftable';
        wil::ActivityBase<DynamoProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v39);
        wil::ActivityBase<DynamoProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DynamoProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v39);
        return 2147942934LL;
      }
      *a4 = v12;
      v13 = 0;
      pv[0] = 0;
      v14 = (v10 - v11) >> 6;
      if ( is_mul_ok(v14, 0x40u) )
      {
        v15 = CTCoAllocPolicy::Alloc((IMalloc *)v14, (v14 * (unsigned __int128)0x40uLL) >> 64, v14 << 6, pv);
        v13 = (struct OMADMALERTINFO *)pv[0];
        if ( v15 >= 0 )
        {
          v16 = 0;
          for ( i = *(_QWORD *)v37; v16 < (v38 - *(_QWORD *)v37) >> 6; i = *(_QWORD *)v37 )
          {
            v18 = v16 << 6;
            v19 = (__int128 *)((v16 << 6) + i);
            v20 = *v19;
            v21 = v19[1];
            v22 = v19[2];
            v23 = v19[3];
            memset_0(v19, 0, 0x40u);
            *(_OWORD *)((char *)v13 + v18) = v20;
            *(_OWORD *)((char *)v13 + v18 + 16) = v21;
            *(_OWORD *)((char *)v13 + v18 + 32) = v22;
            *(_OWORD *)((char *)v13 + v18 + 48) = v23;
            ++v16;
          }
          *a3 = v13;
          goto LABEL_26;
        }
      }
      else
      {
        v15 = -2147024362;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2C0,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\dynamicmanagement.cpp",
        (const char *)(unsigned int)v15,
        (int)v34);
      if ( v13 )
        CoTaskMemFree(v13);
      std::vector<wil::unique_struct<OMADMALERTINFO,long (OMADMALERTINFO *),&long dmstd::LocalFreeOmadmAlertInfo(OMADMALERTINFO *),std::nullptr_t,0>>::~vector<wil::unique_struct<OMADMALERTINFO,long (OMADMALERTINFO *),&long dmstd::LocalFreeOmadmAlertInfo(OMADMALERTINFO *),std::nullptr_t,0>>(v37);
      if ( hMutex && !ReleaseMutex(hMutex) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v24, v25);
      v26 = v34;
      v34 = 0;
      if ( v26 )
        (**v26)(v26, 1);
      v39[0] = &DynamicManagementProvider::GetAlertDataActivity::`vftable';
      wil::ActivityBase<DynamoProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v39);
      wil::ActivityBase<DynamoProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DynamoProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v39);
      return (unsigned int)v15;
    }
LABEL_26:
    wil::ActivityBase<DynamoProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v39);
    std::vector<wil::unique_struct<OMADMALERTINFO,long (OMADMALERTINFO *),&long dmstd::LocalFreeOmadmAlertInfo(OMADMALERTINFO *),std::nullptr_t,0>>::~vector<wil::unique_struct<OMADMALERTINFO,long (OMADMALERTINFO *),&long dmstd::LocalFreeOmadmAlertInfo(OMADMALERTINFO *),std::nullptr_t,0>>(v37);
    if ( hMutex && !ReleaseMutex(hMutex) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v31, v32);
    v33 = v34;
    v34 = 0;
    if ( v33 )
      (**v33)(v33, 1);
    v39[0] = &DynamicManagementProvider::GetAlertDataActivity::`vftable';
    wil::ActivityBase<DynamoProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v39);
    wil::ActivityBase<DynamoProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DynamoProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v39);
    result = 0;
  }
  catch ( ... )
  {
    LODWORD(v34) = wil::details::in1diag3::Return_CaughtException(
                     retaddr,
                     (void *)0x2CD,
                     (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\dynamicmanagement.cpp",
                     v27);
    v39[0] = &DynamicManagementProvider::GetAlertDataActivity::`vftable';
    wil::ActivityBase<DynamoProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v39);
    wil::ActivityBase<DynamoProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DynamoProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v39);
    return (unsigned int)v34;
  }
  return result;
}

```

## disassembly

```asm
0x140038c7c  mov     rax, rsp
0x140038c7f  push    rbx
0x140038c80  push    rsi
0x140038c81  push    rdi
0x140038c82  push    r14
0x140038c84  push    r15
0x140038c86  sub     rsp, 290h
0x140038c8d  movaps  xmmword ptr [rax-38h], xmm6
0x140038c91  movaps  xmmword ptr [rax-48h], xmm7
0x140038c95  movaps  xmmword ptr [rax-58h], xmm8
0x140038c9a  movaps  xmmword ptr [rax-68h], xmm9
0x140038c9f  mov     rax, cs:__security_cookie
0x140038ca6  xor     rax, rsp
0x140038ca9  mov     [rsp+2B8h+var_78], rax
0x140038cb1  mov     rbx, r9
0x140038cb4  mov     r14, r8
0x140038cb7  mov     r15, rdx
0x140038cba  mov     rsi, rcx
0x140038cbd  xor     edx, edx; Val
0x140038cbf  mov     r8d, 81h; Size
0x140038cc5  lea     rcx, [rsp+2B8h+var_108]; void *
0x140038ccd  call    memset_0
0x140038cd2  lea     rcx, [rsp+2B8h+var_108]; char *
0x140038cda  call    _anonymous_namespace___GetCorrelationVector
0x140038cdf  lea     rdx, aGetalertdataac; "GetAlertDataActivity"
0x140038ce6  lea     rcx, [rsp+2B8h+var_258]
0x140038ceb  call    ??0?$ActivityBase@VDynamoProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<DynamoProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DynamoProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x140038cf0  lea     rdi, ??_7GetAlertDataActivity@DynamicManagementProvider@@6B@; const DynamicManagementProvider::GetAlertDataActivity::`vftable'
0x140038cf7  mov     [rsp+2B8h+var_258], rdi
0x140038cfc  lea     rdx, [rsp+2B8h+var_108]; char *
0x140038d04  lea     rcx, [rsp+2B8h+var_258]; this
0x140038d09  call    ?StartActivityWithCorrelationVector@GetAlertDataActivity@DynamicManagementProvider@@QEAAXPEBD@Z; DynamicManagementProvider::GetAlertDataActivity::StartActivityWithCorrelationVector(char const *)
0x140038d0e  nop
0x140038d0f  test    r14, r14
0x140038d12  jnz     short loc_140038D56
0x140038d14  mov     edx, 2AEh; void *
0x140038d19  mov     ebx, 80070057h
0x140038d1e  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x140038d25  mov     r9d, ebx; char *
0x140038d28  mov     rcx, [rsp+2B8h]; this
0x140038d30  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140038d35  nop
0x140038d36  mov     [rsp+2B8h+var_258], rdi
0x140038d3b  lea     rcx, [rsp+2B8h+var_258]
0x140038d40  call    ?Destroy@?$ActivityBase@VDynamoProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<DynamoProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x140038d45  lea     rcx, [rsp+2B8h+var_258]
0x140038d4a  call    ??1?$ActivityBase@VDynamoProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<DynamoProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DynamoProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x140038d4f  mov     eax, ebx
0x140038d51  jmp     loc_140039078
0x140038d56  mov     qword ptr [r14], 0
0x140038d5d  test    rbx, rbx
0x140038d60  jnz     short loc_140038D69
0x140038d62  mov     edx, 2B1h
0x140038d67  jmp     short loc_140038D19
0x140038d69  mov     dword ptr [rbx], 0
0x140038d6f  mov     r8, r15
0x140038d72  mov     rdx, rsi
0x140038d75  lea     rcx, [rsp+2B8h+var_298]
0x140038d7a  call    ?GetStore@?$DataStoreFactory_t@VDataStore@details@Dynamo@@@Dynamo@@SA?AV?$unique_ptr@VIDataStore@Dynamo@@U?$default_delete@VIDataStore@Dynamo@@@wistd@@@wistd@@PEBG0@Z; Dynamo::DataStoreFactory_t<Dynamo::details::DataStore>::GetStore(ushort const *,ushort const *)
0x140038d7f  nop
0x140038d80  mov     rcx, [rsp+2B8h+var_298]
0x140038d85  mov     rax, [rcx]
0x140038d88  lea     rdx, [rsp+2B8h+hMutex]
0x140038d8d  mov     rax, [rax+28h]
0x140038d91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140038d96  nop
0x140038d97  mov     rcx, [rsp+2B8h+var_298]
0x140038d9c  mov     rax, [rcx]
0x140038d9f  lea     rdx, [rsp+2B8h+var_278]
0x140038da4  mov     rax, [rax+68h]
0x140038da8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140038dad  nop
0x140038dae  mov     rcx, [rsp+2B8h+var_298]
0x140038db3  mov     rax, [rcx]
0x140038db6  mov     rax, [rax+70h]
0x140038dba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140038dbf  mov     rcx, [rsp+2B8h+var_270]
0x140038dc4  mov     rdx, qword ptr [rsp+2B8h+var_278]; unsigned int
0x140038dc9  cmp     rdx, rcx
0x140038dcc  jz      loc_140038FDD
0x140038dd2  mov     [rsp+2B8h+pv], 0
0x140038ddb  mov     [rsp+2B8h+var_280], 0
0x140038de4  mov     rax, rcx
0x140038de7  sub     rax, rdx
0x140038dea  sar     rax, 6
0x140038dee  mov     r8d, 0FFFFFFFFh
0x140038df4  cmp     rax, r8
0x140038df7  ja      loc_140038F49
0x140038dfd  mov     [rbx], eax
0x140038dff  xor     esi, esi
0x140038e01  mov     [rsp+2B8h+pv], rsi
0x140038e06  sub     rcx, rdx
0x140038e09  sar     rcx, 6; void *
0x140038e0d  lea     eax, [rsi+40h]
0x140038e10  mul     rcx
0x140038e13  test    rdx, rdx
0x140038e16  jnz     loc_140038EA9
0x140038e1c  lea     r9, [rsp+2B8h+pv]; void **
0x140038e21  mov     r8, rax; unsigned __int64
0x140038e24  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x140038e29  mov     ebx, eax
0x140038e2b  mov     rsi, [rsp+2B8h+pv]
0x140038e30  test    eax, eax
0x140038e32  js      short loc_140038EAE
0x140038e34  xor     r15d, r15d
0x140038e37  mov     rax, [rsp+2B8h+var_270]
0x140038e3c  mov     rcx, qword ptr [rsp+2B8h+var_278]
0x140038e41  sub     rax, rcx
0x140038e44  sar     rax, 6
0x140038e48  test    rax, rax
0x140038e4b  jz      short loc_140038EA1
0x140038e4d  mov     rbx, r15
0x140038e50  shl     rbx, 6
0x140038e54  add     rcx, rbx; void *
0x140038e57  movups  xmm6, xmmword ptr [rcx]
0x140038e5a  movups  xmm7, xmmword ptr [rcx+10h]
0x140038e5e  movups  xmm8, xmmword ptr [rcx+20h]
0x140038e63  movups  xmm9, xmmword ptr [rcx+30h]
0x140038e68  xor     edx, edx; Val
0x140038e6a  lea     r8d, [rdx+40h]; Size
0x140038e6e  call    memset_0
0x140038e73  movups  xmmword ptr [rbx+rsi], xmm6
0x140038e77  movups  xmmword ptr [rbx+rsi+10h], xmm7
0x140038e7c  movups  xmmword ptr [rbx+rsi+20h], xmm8
0x140038e82  movups  xmmword ptr [rbx+rsi+30h], xmm9
0x140038e88  inc     r15
0x140038e8b  mov     rax, [rsp+2B8h+var_270]
0x140038e90  mov     rcx, qword ptr [rsp+2B8h+var_278]
0x140038e95  sub     rax, rcx
0x140038e98  sar     rax, 6
0x140038e9c  cmp     r15, rax
0x140038e9f  jb      short loc_140038E4D
0x140038ea1  mov     [r14], rsi
0x140038ea4  jmp     loc_140038FDD
0x140038ea9  mov     ebx, 80070216h
0x140038eae  mov     rcx, [rsp+2B8h]; this
0x140038eb6  mov     r9d, ebx; char *
0x140038eb9  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x140038ec0  mov     edx, 2C0h; void *
0x140038ec5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140038eca  nop
0x140038ecb  test    rsi, rsi
0x140038ece  jz      short loc_140038EDA
0x140038ed0  mov     rcx, rsi; pv
0x140038ed3  call    cs:__imp_CoTaskMemFree
0x140038ed9  nop
0x140038eda  lea     rcx, [rsp+2B8h+var_278]
0x140038edf  call    ??1?$vector@V?$unique_struct@UOMADMALERTINFO@@$$A6AJPEAU1@@Z$1?LocalFreeOmadmAlertInfo@dmstd@@YAJ0@Z$$T$0A@@wil@@V?$allocator@V?$unique_struct@UOMADMALERTINFO@@$$A6AJPEAU1@@Z$1?LocalFreeOmadmAlertInfo@dmstd@@YAJ0@Z$$T$0A@@wil@@@std@@@std@@QEAA@XZ; std::vector<wil::unique_struct<OMADMALERTINFO,long (OMADMALERTINFO *),&dmstd::LocalFreeOmadmAlertInfo(OMADMALERTINFO *),std::nullptr_t,0>>::~vector<wil::unique_struct<OMADMALERTINFO,long (OMADMALERTINFO *),&dmstd::LocalFreeOmadmAlertInfo(OMADMALERTINFO *),std::nullptr_t,0>>(void)
0x140038ee4  nop
0x140038ee5  mov     rcx, [rsp+2B8h+hMutex]; hMutex
0x140038eea  test    rcx, rcx
0x140038eed  jz      short loc_140038F05
0x140038eef  call    cs:__imp_ReleaseMutex
0x140038ef5  mov     rcx, [rsp+2B8h]; this
0x140038efd  test    eax, eax
0x140038eff  jz      loc_1400390AF
0x140038f05  mov     rcx, [rsp+2B8h+var_298]
0x140038f0a  mov     [rsp+2B8h+var_298], 0
0x140038f13  test    rcx, rcx
0x140038f16  jz      short loc_140038F29
0x140038f18  mov     rax, [rcx]
0x140038f1b  mov     edx, 1
0x140038f20  mov     rax, [rax]
0x140038f23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140038f28  nop
0x140038f29  mov     [rsp+2B8h+var_258], rdi
0x140038f2e  lea     rcx, [rsp+2B8h+var_258]
0x140038f33  call    ?Destroy@?$ActivityBase@VDynamoProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<DynamoProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x140038f38  lea     rcx, [rsp+2B8h+var_258]
0x140038f3d  call    ??1?$ActivityBase@VDynamoProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<DynamoProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DynamoProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x140038f42  mov     eax, ebx
0x140038f44  jmp     loc_140039078
0x140038f49  mov     [rbx], r8d
0x140038f4c  mov     rcx, [rsp+2B8h]; this
0x140038f54  mov     ebx, 80070216h
0x140038f59  mov     r9d, ebx; char *
0x140038f5c  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x140038f63  mov     edx, 2BFh; void *
0x140038f68  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140038f6d  nop
0x140038f6e  lea     rcx, [rsp+2B8h+var_278]
0x140038f73  call    ??1?$vector@V?$unique_struct@UOMADMALERTINFO@@$$A6AJPEAU1@@Z$1?LocalFreeOmadmAlertInfo@dmstd@@YAJ0@Z$$T$0A@@wil@@V?$allocator@V?$unique_struct@UOMADMALERTINFO@@$$A6AJPEAU1@@Z$1?LocalFreeOmadmAlertInfo@dmstd@@YAJ0@Z$$T$0A@@wil@@@std@@@std@@QEAA@XZ; std::vector<wil::unique_struct<OMADMALERTINFO,long (OMADMALERTINFO *),&dmstd::LocalFreeOmadmAlertInfo(OMADMALERTINFO *),std::nullptr_t,0>>::~vector<wil::unique_struct<OMADMALERTINFO,long (OMADMALERTINFO *),&dmstd::LocalFreeOmadmAlertInfo(OMADMALERTINFO *),std::nullptr_t,0>>(void)
0x140038f78  nop
0x140038f79  mov     rcx, [rsp+2B8h+hMutex]; hMutex
0x140038f7e  test    rcx, rcx
0x140038f81  jz      short loc_140038F99
0x140038f83  call    cs:__imp_ReleaseMutex
0x140038f89  mov     rcx, [rsp+2B8h]; this
0x140038f91  test    eax, eax
0x140038f93  jz      loc_1400390BA
0x140038f99  mov     rcx, [rsp+2B8h+var_298]
0x140038f9e  mov     [rsp+2B8h+var_298], 0
0x140038fa7  test    rcx, rcx
0x140038faa  jz      short loc_140038FBD
0x140038fac  mov     rax, [rcx]
0x140038faf  mov     edx, 1
0x140038fb4  mov     rax, [rax]
0x140038fb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140038fbc  nop
0x140038fbd  mov     [rsp+2B8h+var_258], rdi
0x140038fc2  lea     rcx, [rsp+2B8h+var_258]
0x140038fc7  call    ?Destroy@?$ActivityBase@VDynamoProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<DynamoProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x140038fcc  lea     rcx, [rsp+2B8h+var_258]
0x140038fd1  call    ??1?$ActivityBase@VDynamoProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<DynamoProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DynamoProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x140038fd6  mov     eax, ebx
0x140038fd8  jmp     loc_140039078
0x140038fdd  lea     rcx, [rsp+2B8h+var_258]
0x140038fe2  call    ?Stop@?$ActivityBase@VDynamoProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<DynamoProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x140038fe7  nop
0x140038fe8  lea     rcx, [rsp+2B8h+var_278]
0x140038fed  call    ??1?$vector@V?$unique_struct@UOMADMALERTINFO@@$$A6AJPEAU1@@Z$1?LocalFreeOmadmAlertInfo@dmstd@@YAJ0@Z$$T$0A@@wil@@V?$allocator@V?$unique_struct@UOMADMALERTINFO@@$$A6AJPEAU1@@Z$1?LocalFreeOmadmAlertInfo@dmstd@@YAJ0@Z$$T$0A@@wil@@@std@@@std@@QEAA@XZ; std::vector<wil::unique_struct<OMADMALERTINFO,long (OMADMALERTINFO *),&dmstd::LocalFreeOmadmAlertInfo(OMADMALERTINFO *),std::nullptr_t,0>>::~vector<wil::unique_struct<OMADMALERTINFO,long (OMADMALERTINFO *),&dmstd::LocalFreeOmadmAlertInfo(OMADMALERTINFO *),std::nullptr_t,0>>(void)
0x140038ff2  nop
0x140038ff3  mov     rcx, [rsp+2B8h+hMutex]; hMutex
0x140038ff8  test    rcx, rcx
0x140038ffb  jz      short loc_140039013
0x140038ffd  call    cs:__imp_ReleaseMutex
0x140039003  mov     rcx, [rsp+2B8h]; this
0x14003900b  test    eax, eax
0x14003900d  jz      loc_1400390C5
0x140039013  mov     rcx, [rsp+2B8h+var_298]
0x140039018  mov     [rsp+2B8h+var_298], 0
0x140039021  test    rcx, rcx
0x140039024  jz      short loc_140039037
0x140039026  mov     rax, [rcx]
0x140039029  mov     edx, 1
0x14003902e  mov     rax, [rax]
0x140039031  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140039036  nop
0x140039037  mov     [rsp+2B8h+var_258], rdi
0x14003903c  lea     rcx, [rsp+2B8h+var_258]
0x140039041  call    ?Destroy@?$ActivityBase@VDynamoProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<DynamoProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x140039046  lea     rcx, [rsp+2B8h+var_258]
0x14003904b  call    ??1?$ActivityBase@VDynamoProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<DynamoProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DynamoProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x140039050  xor     eax, eax
0x140039052  jmp     short loc_140039078
0x140039054  lea     rdi, ??_7GetAlertDataActivity@DynamicManagementProvider@@6B@; const DynamicManagementProvider::GetAlertDataActivity::`vftable'
0x14003905b  mov     [rsp+2B8h+var_258], rdi
0x140039060  lea     rcx, [rsp+2B8h+var_258]
0x140039065  call    ?Destroy@?$ActivityBase@VDynamoProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<DynamoProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x14003906a  lea     rcx, [rsp+2B8h+var_258]
0x14003906f  call    ??1?$ActivityBase@VDynamoProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<DynamoProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DynamoProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x140039074  mov     eax, dword ptr [rsp+2B8h+var_298]
0x140039078  mov     rcx, [rsp+2B8h+var_78]
0x140039080  xor     rcx, rsp; StackCookie
0x140039083  call    __security_check_cookie
0x140039088  lea     r11, [rsp+2B8h+var_28]
0x140039090  movaps  xmm6, xmmword ptr [r11-10h]
0x140039095  movaps  xmm7, xmmword ptr [r11-20h]
0x14003909a  movaps  xmm8, xmmword ptr [r11-30h]
0x14003909f  movaps  xmm9, xmmword ptr [r11-40h]
0x1400390a4  mov     rsp, r11
0x1400390a7  pop     r15
0x1400390a9  pop     r14
0x1400390ab  pop     rdi
0x1400390ac  pop     rsi
0x1400390ad  pop     rbx
0x1400390ae  retn
0x1400390af  mov     edx, 0A15h; void *
0x1400390b4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400390ba  mov     edx, 0A15h; void *
0x1400390bf  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400390c5  mov     edx, 0A15h; void *
0x1400390ca  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
