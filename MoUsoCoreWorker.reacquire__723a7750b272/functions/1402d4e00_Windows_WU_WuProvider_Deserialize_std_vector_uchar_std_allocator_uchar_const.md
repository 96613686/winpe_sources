# Windows::WU::WuProvider::Deserialize(std::vector<uchar,std::allocator<uchar>> const &)

- ea: `0x1402d4e00`
- end: `0x1402d53e5`
- name: `?Deserialize@WuProvider@WU@Windows@@UEAA?AV?$optional@V?$shared_ptr@VUpdate@@@std@@@std@@AEBV?$vector@EV?$allocator@E@std@@@5@@Z`
- size: `1509`
- prototype: ``
- caller_count: `0`
- callee_count: `21`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x14003fee4`
- `0x1400413a8`
- `0x140045404`
- `0x140075a18`
- `0x14007c004`
- `0x1400d1a58`
- `0x14012d7d8`
- `0x1402d4e00`
- `0x1402d9040`
- `0x1402da44c`
- `0x1402dab7c`
- `0x1402e3a40`
- `0x1402e3b10`
- `0x1402e5b20`
- `0x1402f6a94`
- `0x140379070`
- `0x1403790cc`
- `0x1403790d8`
- `0x14037b4b0`
- `0x140380b50`
- `0x140380bd0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1402d4e67`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1402d4e67`
- `OLEAUT32!__imp_SysFreeString` at `0x1402d52a5`
- `OLEAUT32!__imp_SysFreeString` at `0x1402d5335`
- `OLEAUT32!__imp_SysFreeString` at `0x1402d52a5`
- `OLEAUT32!__imp_SysFreeString` at `0x1402d5335`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x1402d4e94`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x1402d4e94`

## string_xrefs

- `0x1402d5382`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\wuprovider\WuProvider.cpp`
- `0x1402d5397`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\wuprovider\WuProvider.cpp`
- `0x1402d53d3`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\wuprovider\WuProvider.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=25
__int64 __fastcall Windows::WU::WuProvider::Deserialize(_QWORD *a1, __int64 a2, __int64 a3)
{
  HRESULT v6; // eax
  __int64 v7; // rdx
  OLECHAR *v8; // rdi
  const char *v9; // r9
  __int64 v10; // rax
  int v11; // eax
  _QWORD *v12; // rax
  __int64 v13; // rcx
  _QWORD *v14; // rax
  __int64 v15; // rcx
  __int64 v16; // rax
  __int64 v17; // r14
  __int64 v18; // rbx
  volatile signed __int32 *v19; // r15
  __int64 v20; // rax
  volatile signed __int32 *v21; // r14
  volatile signed __int32 *v22; // rbx
  char v23; // si
  __int64 System; // rax
  __int64 (__fastcall ***v25)(_QWORD, __int128 *); // rcx
  _QWORD *v26; // rax
  bool v27; // r14
  volatile signed __int32 *v28; // rbx
  volatile signed __int32 *v29; // rbx
  void *v30; // rbx
  void (*v31)(void); // rax
  void *v32; // rbx
  int ppv; // [rsp+20h] [rbp-E0h]
  __int64 v35; // [rsp+28h] [rbp-D8h]
  bool v36[4]; // [rsp+30h] [rbp-D0h] BYREF
  int v37; // [rsp+34h] [rbp-CCh]
  __int128 v38; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v39; // [rsp+50h] [rbp-B0h] BYREF
  void *Block; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v41; // [rsp+60h] [rbp-A0h] BYREF
  __int128 pExceptionObject; // [rsp+70h] [rbp-90h] BYREF
  __int64 v43; // [rsp+80h] [rbp-80h]
  OLECHAR *v44; // [rsp+90h] [rbp-70h]
  _BYTE v45[32]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v46[32]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v47[32]; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v48; // [rsp+F8h] [rbp-8h] BYREF
  LPVOID v49; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v50[32]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v51[40]; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v52[36]; // [rsp+158h] [rbp+58h] BYREF
  int v53; // [rsp+17Ch] [rbp+7Ch]
  char v54; // [rsp+180h] [rbp+80h]
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+D8h]

  *(_QWORD *)&v38 = a2;
  v37 = 0;
  v49 = 0;
  v6 = CoCreateInstance(&CLSID_UpdateDeserializer, 0, 1u, &GUID_84db9afd_0ddb_424d_a25d_5bc47c4451d4, &v49);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2ED,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\WuProvider.cpp",
      (const char *)(unsigned int)v6,
      ppv);
  v7 = (unsigned int)(*(_DWORD *)(a3 + 8) - *(_DWORD *)a3 - 1);
  if ( v7 != *(_QWORD *)(a3 + 8) - *(_QWORD *)a3 - 1LL )
  {
    pExceptionObject = 0;
    v43 = 0;
    Concurrency::task_canceled::task_canceled((Concurrency::task_canceled *)&pExceptionObject);
    throw (gsl::narrowing_error *)&pExceptionObject;
  }
  v8 = SysAllocStringByteLen(*(LPCSTR *)a3, v7);
  v44 = v8;
  if ( !v8 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x2F0,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\WuProvider.cpp",
      v9);
  v48 = 0;
  v10 = *(_QWORD *)v49;
  v48 = 0;
  v11 = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *, __int64 *))(v10 + 24))(v49, v8, &v48);
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2F3,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\WuProvider.cpp",
      (const char *)(unsigned int)v11,
      ppv);
  *(_QWORD *)&v38 = operator new(0x90u);
  memset((void *)v38, 0, 0x90u);
  Block = (void *)Windows::WU::WuUpdateInternalImpl::WuUpdateInternalImpl(v38, &v48, a1 + 1);
  v39 = 0;
  v36[0] = Windows::WU::WuUpdateInternalImpl::FeatureUpdate((Windows::WU::WuUpdateInternalImpl *)Block);
  v12 = (_QWORD *)Windows::WU::WuUpdateInternalImpl::UniqueId(Block, v47);
  v13 = v12[2];
  if ( v12[3] > 7u )
    v12 = (_QWORD *)*v12;
  *(_QWORD *)&v41 = v12;
  *((_QWORD *)&v41 + 1) = v13;
  v14 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD *, _BYTE *))(*a1 + 8LL))(a1, v46);
  v15 = v14[2];
  if ( v14[3] > 7u )
    v14 = (_QWORD *)*v14;
  *(_QWORD *)&v38 = v14;
  *((_QWORD *)&v38 + 1) = v15;
  pExceptionObject = v41;
  v41 = v38;
  v16 = CreateStorageReserveIdentity(v45, &v41, &pExceptionObject);
  std::make_unique<Windows::WU::StorageReserveImpl,std::wstring,bool,0>(&v39, v16, v36);
  std::wstring::~wstring(v45);
  std::wstring::~wstring(v46);
  std::wstring::~wstring(v47);
  v17 = a1[5];
  v18 = *(_QWORD *)(a3 + 8);
  v19 = (volatile signed __int32 *)operator new(0x1F8u);
  *(_QWORD *)&v41 = v19;
  *(_OWORD *)v19 = 0;
  *((_DWORD *)v19 + 2) = 1;
  *((_DWORD *)v19 + 3) = 1;
  *(_QWORD *)v19 = &std::_Ref_count_obj2<Windows::WU::WuUpdate>::`vftable';
  LODWORD(v18) = *(unsigned __int8 *)(v18 - 1);
  v20 = v39;
  v39 = 0;
  *(_QWORD *)&v38 = v20;
  std::shared_ptr<Windows::WU::WuUpdateInternal>::shared_ptr<Windows::WU::WuUpdateInternal>(&pExceptionObject, &Block);
  v35 = v17;
  v21 = v19 + 4;
  Windows::WU::WuUpdate::WuUpdate(
    (_DWORD)v19 + 16,
    (unsigned int)&pExceptionObject,
    (unsigned int)&v38,
    v18,
    (__int64)(a1 + 3),
    v35);
  v22 = (volatile signed __int32 *)*((_QWORD *)&pExceptionObject + 1);
  if ( *((_QWORD *)&pExceptionObject + 1) )
  {
    if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&pExceptionObject + 1) + 8LL)) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v22)(v22);
      if ( !_InterlockedDecrement(v22 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v22 + 8LL))(v22);
    }
  }
  if ( (_QWORD)v38 )
    (**(void (__fastcall ***)(_QWORD, __int64))v38)(v38, 1);
  v23 = 24;
  *(_QWORD *)&pExceptionObject = v19 + 4;
  *((_QWORD *)&pExceptionObject + 1) = v19;
  UpdateDatabase::GetLatestActionRecord(a1[5], v50, v19 + 4);
  if ( v54 )
  {
    v27 = 0;
    if ( v53 < 0 )
    {
      if ( (*(unsigned __int8 (__fastcall **)(_QWORD *))(*a1 + 224LL))(a1) )
      {
        System = SystemInterface::Providers::GetSystem(&v38);
        v37 = 25;
        v25 = (__int64 (__fastcall ***)(_QWORD, __int128 *))(*(_QWORD *)System
                                                           + 8LL
                                                           + *(int *)(*(_QWORD *)(*(_QWORD *)System + 8LL) + 4LL));
        v26 = (_QWORD *)(**v25)(v25, &v41);
        v23 = 27;
        v37 = 27;
        if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)*v26 + 136LL))(*v26) )
          v27 = 1;
      }
    }
    if ( (v23 & 2) != 0 )
    {
      v23 &= ~2u;
      v28 = (volatile signed __int32 *)*((_QWORD *)&v41 + 1);
      if ( *((_QWORD *)&v41 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v41 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v28)(v28);
          if ( _InterlockedExchangeAdd(v28 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v28 + 8LL))(v28);
        }
      }
    }
    if ( (v23 & 1) != 0 )
    {
      v29 = (volatile signed __int32 *)*((_QWORD *)&v38 + 1);
      if ( *((_QWORD *)&v38 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v38 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v29)(v29);
          if ( _InterlockedExchangeAdd(v29 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v29 + 8LL))(v29);
        }
      }
    }
    if ( v27 )
    {
      *(_BYTE *)(a2 + 16) = 0;
      if ( v54 )
      {
        std::wstring::~wstring(v52);
        std::wstring::~wstring(v51);
        std::wstring::~wstring(v50);
      }
      if ( _InterlockedExchangeAdd(v19 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v19)(v19);
        if ( _InterlockedExchangeAdd(v19 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v19 + 8LL))(v19);
      }
      v30 = Block;
      if ( Block )
      {
        Windows::WU::WuUpdateInternalImpl::~WuUpdateInternalImpl((Windows::WU::WuUpdateInternalImpl *)Block);
        operator delete(v30);
      }
      if ( v48 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
      SysFreeString(v8);
      if ( v49 )
      {
        v31 = *(void (**)(void))(*(_QWORD *)v49 + 16LL);
LABEL_52:
        v31();
        return a2;
      }
      return a2;
    }
    v21 = v19 + 4;
  }
  if ( v54 )
  {
    std::wstring::~wstring(v52);
    std::wstring::~wstring(v51);
    std::wstring::~wstring(v50);
  }
  *(_QWORD *)a2 = v21;
  *(_QWORD *)(a2 + 8) = v19;
  *(_BYTE *)(a2 + 16) = 1;
  v32 = Block;
  if ( Block )
  {
    Windows::WU::WuUpdateInternalImpl::~WuUpdateInternalImpl((Windows::WU::WuUpdateInternalImpl *)Block);
    operator delete(v32);
  }
  if ( v48 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
  SysFreeString(v8);
  if ( v49 )
  {
    v31 = *(void (**)(void))(*(_QWORD *)v49 + 16LL);
    goto LABEL_52;
  }
  return a2;
}

```

## disassembly

```asm
0x1402d4e00  mov     [rsp-8+arg_18], rbx
0x1402d4e05  push    rbp
0x1402d4e06  push    rsi
0x1402d4e07  push    rdi
0x1402d4e08  push    r12
0x1402d4e0a  push    r13
0x1402d4e0c  push    r14
0x1402d4e0e  push    r15
0x1402d4e10  lea     rbp, [rsp-0A0h]
0x1402d4e18  sub     rsp, 1A0h
0x1402d4e1f  mov     rax, cs:__security_cookie
0x1402d4e26  xor     rax, rsp
0x1402d4e29  mov     [rbp+0D0h+var_40], rax
0x1402d4e30  mov     rsi, r8
0x1402d4e33  mov     r12, rdx
0x1402d4e36  mov     r13, rcx
0x1402d4e39  mov     qword ptr [rsp+1D0h+var_190], rdx
0x1402d4e3e  xor     r14d, r14d
0x1402d4e41  mov     [rsp+1D0h+var_19C], r14d
0x1402d4e46  mov     [rbp+0D0h+var_D0], r14
0x1402d4e4a  lea     rax, [rbp+0D0h+var_D0]
0x1402d4e4e  mov     [rsp+1D0h+ppv], rax; int
0x1402d4e53  lea     r9, _GUID_84db9afd_0ddb_424d_a25d_5bc47c4451d4; riid
0x1402d4e5a  xor     edx, edx; pUnkOuter
0x1402d4e5c  lea     r8d, [r14+1]; dwClsContext
0x1402d4e60  lea     rcx, CLSID_UpdateDeserializer; rclsid
0x1402d4e67  call    cs:__imp_CoCreateInstance
0x1402d4e6d  mov     rcx, [rbp+0D8h]; this
0x1402d4e74  test    eax, eax
0x1402d4e76  js      loc_1402D5394
0x1402d4e7c  mov     rax, [rsi+8]
0x1402d4e80  sub     rax, [rsi]
0x1402d4e83  dec     rax
0x1402d4e86  mov     edx, eax; len
0x1402d4e88  cmp     rdx, rax
0x1402d4e8b  jnz     loc_1402D53A9
0x1402d4e91  mov     rcx, [rsi]; psz
0x1402d4e94  call    cs:__imp_SysAllocStringByteLen
0x1402d4e9a  mov     rdi, rax
0x1402d4e9d  mov     [rbp+0D0h+var_140], rax
0x1402d4ea1  mov     rcx, [rbp+0D8h]; this
0x1402d4ea8  test    rax, rax
0x1402d4eab  jz      loc_1402D53D3
0x1402d4eb1  mov     [rbp+0D0h+var_D8], r14
0x1402d4eb5  mov     rcx, [rbp+0D0h+var_D0]
0x1402d4eb9  mov     rax, [rcx]
0x1402d4ebc  mov     [rbp+0D0h+var_D8], r14
0x1402d4ec0  lea     r8, [rbp+0D0h+var_D8]
0x1402d4ec4  mov     rdx, rdi
0x1402d4ec7  mov     rax, [rax+18h]
0x1402d4ecb  call    _guard_dispatch_icall
0x1402d4ed0  mov     rcx, [rbp+0D8h]; this
0x1402d4ed7  test    eax, eax
0x1402d4ed9  js      loc_1402D537F
0x1402d4edf  mov     r15d, 90h
0x1402d4ee5  mov     ecx, r15d; Size
0x1402d4ee8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1402d4eed  mov     rbx, rax
0x1402d4ef0  mov     qword ptr [rsp+1D0h+var_190], rax
0x1402d4ef5  mov     r8d, r15d; Size
0x1402d4ef8  xor     edx, edx; Val
0x1402d4efa  mov     rcx, rax; void *
0x1402d4efd  call    memset
0x1402d4f02  lea     r8, [r13+8]
0x1402d4f06  lea     rdx, [rbp+0D0h+var_D8]
0x1402d4f0a  mov     rcx, rbx
0x1402d4f0d  call    ??0WuUpdateInternalImpl@WU@Windows@@QEAA@$$QEAV?$com_ptr_t@UIUpdate@@Uerr_exception_policy@wil@@@wil@@AEBV?$com_ptr_t@UIUpdateSession3@@Uerr_exception_policy@wil@@@4@@Z; Windows::WU::WuUpdateInternalImpl::WuUpdateInternalImpl(wil::com_ptr_t<IUpdate,wil::err_exception_policy> &&,wil::com_ptr_t<IUpdateSession3,wil::err_exception_policy> const &)
0x1402d4f12  mov     rbx, rax
0x1402d4f15  mov     [rsp+1D0h+Block], rax
0x1402d4f1a  mov     [rsp+1D0h+var_180], r14
0x1402d4f1f  mov     rcx, rax; this
0x1402d4f22  call    ?FeatureUpdate@WuUpdateInternalImpl@WU@Windows@@UEBA_NXZ; Windows::WU::WuUpdateInternalImpl::FeatureUpdate(void)
0x1402d4f27  mov     [rsp+1D0h+var_1A0], al
0x1402d4f2b  lea     rdx, [rbp+0D0h+var_F8]
0x1402d4f2f  mov     rcx, rbx
0x1402d4f32  call    ?UniqueId@WuUpdateInternalImpl@WU@Windows@@UEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; Windows::WU::WuUpdateInternalImpl::UniqueId(void)
0x1402d4f37  nop
0x1402d4f38  mov     rcx, [rax+10h]
0x1402d4f3c  cmp     qword ptr [rax+18h], 7
0x1402d4f41  jbe     short loc_1402D4F46
0x1402d4f43  mov     rax, [rax]
0x1402d4f46  mov     qword ptr [rsp+1D0h+var_170], rax
0x1402d4f4b  mov     qword ptr [rsp+1D0h+var_170+8], rcx
0x1402d4f50  mov     rax, [r13+0]
0x1402d4f54  lea     rdx, [rbp+0D0h+var_118]
0x1402d4f58  mov     rcx, r13
0x1402d4f5b  mov     rax, [rax+8]
0x1402d4f5f  call    _guard_dispatch_icall
0x1402d4f64  nop
0x1402d4f65  mov     rcx, [rax+10h]
0x1402d4f69  cmp     qword ptr [rax+18h], 7
0x1402d4f6e  jbe     short loc_1402D4F73
0x1402d4f70  mov     rax, [rax]
0x1402d4f73  mov     qword ptr [rsp+1D0h+var_190], rax
0x1402d4f78  mov     qword ptr [rsp+1D0h+var_190+8], rcx
0x1402d4f7d  movups  xmm0, [rsp+1D0h+var_170]
0x1402d4f82  movdqu  [rsp+1D0h+pExceptionObject], xmm0
0x1402d4f88  movaps  xmm1, [rsp+1D0h+var_190]
0x1402d4f8d  movdqa  [rsp+1D0h+var_170], xmm1
0x1402d4f93  lea     r8, [rsp+1D0h+pExceptionObject]
0x1402d4f98  lea     rdx, [rsp+1D0h+var_170]
0x1402d4f9d  lea     rcx, [rbp+0D0h+var_138]
0x1402d4fa1  call    ?CreateStorageReserveIdentity@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_zstring_view@_W@wil@@0@Z; CreateStorageReserveIdentity(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)
0x1402d4fa6  nop
0x1402d4fa7  lea     r8, [rsp+1D0h+var_1A0]
0x1402d4fac  mov     rdx, rax
0x1402d4faf  lea     rcx, [rsp+1D0h+var_180]
0x1402d4fb4  call    ??$make_unique@VStorageReserveImpl@WU@Windows@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_N$0A@@std@@YA?AV?$unique_ptr@VStorageReserveImpl@WU@Windows@@U?$default_delete@VStorageReserveImpl@WU@Windows@@@std@@@0@$$QEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEA_N@Z; std::make_unique<Windows::WU::StorageReserveImpl,std::wstring,bool,0>(std::wstring &&,bool &&)
0x1402d4fb9  nop
0x1402d4fba  lea     rcx, [rbp+0D0h+var_138]
0x1402d4fbe  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1402d4fc3  nop
0x1402d4fc4  lea     rcx, [rbp+0D0h+var_118]
0x1402d4fc8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1402d4fcd  nop
0x1402d4fce  lea     rcx, [rbp+0D0h+var_F8]
0x1402d4fd2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1402d4fd7  mov     r14, [r13+28h]
0x1402d4fdb  mov     rbx, [rsi+8]
0x1402d4fdf  lea     rsi, [r13+18h]
0x1402d4fe3  mov     ecx, 1F8h; Size
0x1402d4fe8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1402d4fed  mov     r15, rax
0x1402d4ff0  mov     qword ptr [rsp+1D0h+var_170], rax
0x1402d4ff5  xorps   xmm0, xmm0
0x1402d4ff8  movups  xmmword ptr [rax], xmm0
0x1402d4ffb  mov     eax, 1
0x1402d5000  mov     [r15+8], eax
0x1402d5004  mov     [r15+0Ch], eax
0x1402d5008  lea     rax, ??_7?$_Ref_count_obj2@VWuUpdate@WU@Windows@@@std@@6B@; const std::_Ref_count_obj2<Windows::WU::WuUpdate>::`vftable'
0x1402d500f  mov     [r15], rax
0x1402d5012  movzx   ebx, byte ptr [rbx-1]
0x1402d5016  mov     rax, [rsp+1D0h+var_180]
0x1402d501b  mov     [rsp+1D0h+var_180], 0
0x1402d5024  mov     qword ptr [rsp+1D0h+var_190], rax
0x1402d5029  lea     rdx, [rsp+1D0h+Block]
0x1402d502e  lea     rcx, [rsp+1D0h+pExceptionObject]
0x1402d5033  call    ??$?0VWuUpdateInternalImpl@WU@Windows@@U?$default_delete@VWuUpdateInternalImpl@WU@Windows@@@std@@$0A@@?$shared_ptr@VWuUpdateInternal@WU@Windows@@@std@@QEAA@$$QEAV?$unique_ptr@VWuUpdateInternalImpl@WU@Windows@@U?$default_delete@VWuUpdateInternalImpl@WU@Windows@@@std@@@1@@Z; std::shared_ptr<Windows::WU::WuUpdateInternal>::shared_ptr<Windows::WU::WuUpdateInternal>(std::unique_ptr<Windows::WU::WuUpdateInternalImpl> &&)
0x1402d5038  nop
0x1402d5039  mov     [rsp+1D0h+var_1A8], r14
0x1402d503e  mov     [rsp+1D0h+ppv], rsi
0x1402d5043  mov     r9d, ebx
0x1402d5046  lea     r8, [rsp+1D0h+var_190]
0x1402d504b  lea     rdx, [rsp+1D0h+pExceptionObject]
0x1402d5050  lea     r14, [r15+10h]
0x1402d5054  mov     rcx, r14
0x1402d5057  call    ??0WuUpdate@WU@Windows@@QEAA@$$QEAV?$shared_ptr@VWuUpdateInternal@WU@Windows@@@std@@$$QEAV?$unique_ptr@VStorageReserve@WU@Windows@@U?$default_delete@VStorageReserve@WU@Windows@@@std@@@4@IAEAV?$shared_ptr@V?$DecisionEngine@VConditionContext@Providers@SystemInterface@@@@@4@AEAVUpdateDatabase@@@Z; Windows::WU::WuUpdate::WuUpdate(std::shared_ptr<Windows::WU::WuUpdateInternal> &&,std::unique_ptr<Windows::WU::StorageReserve> &&,uint,std::shared_ptr<DecisionEngine<SystemInterface::Providers::ConditionContext>> &,UpdateDatabase &)
0x1402d505c  nop
0x1402d505d  or      esi, 0FFFFFFFFh
0x1402d5060  mov     rbx, qword ptr [rsp+1D0h+pExceptionObject+8]
0x1402d5065  test    rbx, rbx
0x1402d5068  jz      short loc_1402D509E
0x1402d506a  mov     eax, esi
0x1402d506c  lock xadd [rbx+8], eax
0x1402d5071  add     eax, esi
0x1402d5073  jnz     short loc_1402D509E
0x1402d5075  mov     rax, [rbx]
0x1402d5078  mov     rcx, rbx
0x1402d507b  mov     rax, [rax]
0x1402d507e  call    _guard_dispatch_icall
0x1402d5083  mov     eax, esi
0x1402d5085  lock xadd [rbx+0Ch], eax
0x1402d508a  add     eax, esi
0x1402d508c  jnz     short loc_1402D509E
0x1402d508e  mov     rax, [rbx]
0x1402d5091  mov     rcx, rbx
0x1402d5094  mov     rax, [rax+8]
0x1402d5098  call    _guard_dispatch_icall
0x1402d509d  nop
0x1402d509e  mov     rcx, qword ptr [rsp+1D0h+var_190]
0x1402d50a3  test    rcx, rcx
0x1402d50a6  jz      short loc_1402D50B9
0x1402d50a8  mov     rax, [rcx]
0x1402d50ab  mov     edx, 1
0x1402d50b0  mov     rax, [rax]
0x1402d50b3  call    _guard_dispatch_icall
0x1402d50b8  nop
0x1402d50b9  xorps   xmm0, xmm0
0x1402d50bc  movups  [rsp+1D0h+pExceptionObject], xmm0
0x1402d50c1  mov     esi, 18h
0x1402d50c6  mov     qword ptr [rsp+1D0h+pExceptionObject], r14
0x1402d50cb  mov     qword ptr [rsp+1D0h+pExceptionObject+8], r15
0x1402d50d0  mov     r8, r14
0x1402d50d3  lea     rdx, [rbp+0D0h+var_C0]
0x1402d50d7  mov     rcx, [r13+28h]
0x1402d50db  call    ?GetLatestActionRecord@UpdateDatabase@@QEBA?AV?$optional@UActionRecord@SystemInterface@@@std@@AEBVUpdate@@@Z; UpdateDatabase::GetLatestActionRecord(Update const &)
0x1402d50e0  nop
0x1402d50e1  cmp     [rbp+0D0h+var_50], 0
0x1402d50e8  jz      loc_1402D52C9
0x1402d50ee  cmp     [rbp+0D0h+var_54], 0
0x1402d50f2  jge     short loc_1402D5165
0x1402d50f4  mov     rax, [r13+0]
0x1402d50f8  mov     rcx, r13
0x1402d50fb  mov     rax, [rax+0E0h]
0x1402d5102  call    _guard_dispatch_icall
0x1402d5107  test    al, al
0x1402d5109  jz      short loc_1402D5165
0x1402d510b  lea     rcx, [rsp+1D0h+var_190]
0x1402d5110  call    ?GetSystem@Providers@SystemInterface@@YA?AV?$shared_ptr@VSystem@Providers@SystemInterface@@@std@@XZ; SystemInterface::Providers::GetSystem(void)
0x1402d5115  nop
0x1402d5116  mov     [rsp+1D0h+var_19C], 19h
0x1402d511e  mov     rdx, [rax]
0x1402d5121  mov     rax, [rdx+8]
0x1402d5125  movsxd  rcx, dword ptr [rax+4]
0x1402d5129  add     rdx, 8
0x1402d512d  add     rcx, rdx
0x1402d5130  mov     rax, [rcx]
0x1402d5133  lea     rdx, [rsp+1D0h+var_170]
0x1402d5138  mov     rax, [rax]
0x1402d513b  call    _guard_dispatch_icall
0x1402d5140  nop
0x1402d5141  mov     esi, 1Bh
0x1402d5146  mov     [rsp+1D0h+var_19C], esi
0x1402d514a  mov     rcx, [rax]
0x1402d514d  mov     rax, [rcx]
0x1402d5150  mov     rax, [rax+88h]
0x1402d5157  call    _guard_dispatch_icall
0x1402d515c  test    al, al
0x1402d515e  jz      short loc_1402D5165
0x1402d5160  mov     r14b, 1
0x1402d5163  jmp     short loc_1402D5168
0x1402d5165  xor     r14b, r14b
0x1402d5168  or      r13d, 0FFFFFFFFh
0x1402d516c  test    sil, 2
0x1402d5170  jz      short loc_1402D51B7
0x1402d5172  and     esi, 0FFFFFFFDh
0x1402d5175  mov     rbx, qword ptr [rsp+1D0h+var_170+8]
0x1402d517a  test    rbx, rbx
0x1402d517d  jz      short loc_1402D51B7
0x1402d517f  mov     eax, r13d
0x1402d5182  lock xadd [rbx+8], eax
0x1402d5187  add     eax, r13d
0x1402d518a  jnz     short loc_1402D51B7
0x1402d518c  mov     rax, [rbx]
0x1402d518f  mov     rcx, rbx
0x1402d5192  mov     rax, [rax]
0x1402d5195  call    _guard_dispatch_icall
0x1402d519a  mov     eax, r13d
0x1402d519d  lock xadd [rbx+0Ch], eax
0x1402d51a2  add     eax, r13d
0x1402d51a5  jnz     short loc_1402D51B7
0x1402d51a7  mov     rax, [rbx]
0x1402d51aa  mov     rcx, rbx
0x1402d51ad  mov     rax, [rax+8]
0x1402d51b1  call    _guard_dispatch_icall
0x1402d51b6  nop
0x1402d51b7  test    sil, 1
0x1402d51bb  jz      short loc_1402D51FE
0x1402d51bd  mov     rbx, qword ptr [rsp+1D0h+var_190+8]
0x1402d51c2  test    rbx, rbx
0x1402d51c5  jz      short loc_1402D51FE
0x1402d51c7  mov     eax, r13d
0x1402d51ca  lock xadd [rbx+8], eax
0x1402d51cf  add     eax, r13d
0x1402d51d2  jnz     short loc_1402D51FE
0x1402d51d4  mov     rax, [rbx]
0x1402d51d7  mov     rcx, rbx
0x1402d51da  mov     rax, [rax]
0x1402d51dd  call    _guard_dispatch_icall
0x1402d51e2  mov     eax, r13d
0x1402d51e5  lock xadd [rbx+0Ch], eax
0x1402d51ea  add     eax, r13d
0x1402d51ed  jnz     short loc_1402D51FE
0x1402d51ef  mov     rax, [rbx]
0x1402d51f2  mov     rcx, rbx
0x1402d51f5  mov     rax, [rax+8]
0x1402d51f9  call    _guard_dispatch_icall
0x1402d51fe  test    r14b, r14b
0x1402d5201  jz      loc_1402D52C5
0x1402d5207  mov     byte ptr [r12+10h], 0
0x1402d520d  cmp     [rbp+0D0h+var_50], 0
0x1402d5214  jz      short loc_1402D5232
0x1402d5216  lea     rcx, [rbp+0D0h+var_78]
0x1402d521a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1402d521f  lea     rcx, [rbp+0D0h+var_A0]
0x1402d5223  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1402d5228  lea     rcx, [rbp+0D0h+var_C0]
0x1402d522c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1402d5231  nop
0x1402d5232  mov     eax, r13d
0x1402d5235  lock xadd [r15+8], eax
0x1402d523b  add     eax, r13d
0x1402d523e  jnz     short loc_1402D526C
0x1402d5240  mov     rax, [r15]
0x1402d5243  mov     rcx, r15
0x1402d5246  mov     rax, [rax]
0x1402d5249  call    _guard_dispatch_icall
0x1402d524e  mov     eax, r13d
0x1402d5251  lock xadd [r15+0Ch], eax
0x1402d5257  add     eax, r13d
0x1402d525a  jnz     short loc_1402D526C
0x1402d525c  mov     rax, [r15]
0x1402d525f  mov     rcx, r15
0x1402d5262  mov     rax, [rax+8]
0x1402d5266  call    _guard_dispatch_icall
0x1402d526b  nop
0x1402d526c  mov     rbx, [rsp+1D0h+Block]
0x1402d5271  test    rbx, rbx
0x1402d5274  jz      short loc_1402D528C
0x1402d5276  mov     rcx, rbx; this
  ... truncated ...
```
