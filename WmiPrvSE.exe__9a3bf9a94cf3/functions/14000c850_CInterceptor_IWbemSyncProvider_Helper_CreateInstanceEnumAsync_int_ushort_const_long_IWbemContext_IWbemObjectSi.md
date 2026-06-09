# CInterceptor_IWbemSyncProvider::Helper_CreateInstanceEnumAsync(int,ushort * const,long,IWbemContext *,IWbemObjectSink *,IWbemServices *)

- ea: `0x14000c850`
- end: `0x14000d085`
- name: `?Helper_CreateInstanceEnumAsync@CInterceptor_IWbemSyncProvider@@AEAAJHQEAGJPEAUIWbemContext@@PEAUIWbemObjectSink@@PEAUIWbemServices@@@Z`
- size: `2101`
- prototype: `__int64 __fastcall(CInterceptor_IWbemSyncProvider *this, int, unsigned __int16 *const, int, struct IWbemContext *, struct IWbemObjectSink *, struct IWbemServices *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x14000c3a0`

## callees

- `0x14000212c`
- `0x14000c190`
- `0x14000c850`
- `0x14000d860`
- `0x14000d9e4`
- `0x1400209a0`
- `0x1400234b8`
- `0x140029d44`
- `0x14002a684`
- `0x14002b716`
- `0x140048010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000cec8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000cef7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000cf22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000cf9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000cec8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000cef7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000cf22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000cf9f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000c92c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000c97f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000c9d2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000cac5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000c92c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000c97f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000c9d2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000cac5`
- `NCObjAPI!WmiSetAndCommitObject` at `0x14000cc27`
- `NCObjAPI!WmiSetAndCommitObject` at `0x14000cc27`
- `wbemcomn!GetMemLogObject` at `0x14000ceb2`
- `wbemcomn!GetMemLogObject` at `0x14000ceb2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14000cebd`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14000cebd`
- `OLEAUT32!__imp_SysAllocString` at `0x14000c8f7`
- `OLEAUT32!__imp_SysAllocString` at `0x14000c8f7`
- `OLEAUT32!__imp_SysFreeString` at `0x14000d037`
- `OLEAUT32!__imp_SysFreeString` at `0x14000d037`
- `OLEAUT32!__imp_SysStringLen` at `0x14000ca10`
- `OLEAUT32!__imp_SysStringLen` at `0x14000ca25`
- `OLEAUT32!__imp_SysStringLen` at `0x14000ca10`
- `OLEAUT32!__imp_SysStringLen` at `0x14000ca25`
- `OLEAUT32!__imp_VariantInit` at `0x14000c8c0`
- `OLEAUT32!__imp_VariantInit` at `0x14000c8c0`
- `OLEAUT32!__imp_VariantClear` at `0x14000cdda`
- `OLEAUT32!__imp_VariantClear` at `0x14000ce07`
- `OLEAUT32!__imp_VariantClear` at `0x14000cdda`
- `OLEAUT32!__imp_VariantClear` at `0x14000ce07`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x14000ca53`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x14000ca53`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x14000ce2b`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x14000cfc7`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x14000ce2b`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x14000cfc7`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14000cd28`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14000d01a`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14000cd28`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14000d01a`

## string_xrefs

- `0x14000ce47`: `CreateInstanceEnumAsync`
- `0x14000c8d5`: `__GET_EXTENSIONS`
- `0x14000ce61`: `__GET_EXTENSIONS`
- `0x14000ced5`: `CreateInstanceEnumAsync: `

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall CInterceptor_IWbemSyncProvider::Helper_CreateInstanceEnumAsync(
        CInterceptor_IWbemSyncProvider *this,
        int a2,
        unsigned __int16 *const a3,
        int a4,
        struct IWbemContext *a5,
        struct IWbemObjectSink *a6,
        struct IWbemServices *a7)
{
  int v7; // r14d
  int v10; // esi
  __int64 v11; // rbx
  unsigned __int16 *v12; // r12
  struct IErrorInfo *v13; // rdx
  void *v14; // rcx
  struct IWbemContext *v15; // rax
  volatile signed __int32 *v16; // rdi
  struct IErrorInfo *v17; // rdx
  void *v18; // rcx
  struct IWbemContext *v19; // rax
  __int64 v20; // rbx
  BSTR v21; // rdx
  void *v22; // rcx
  LPVOID v23; // rsi
  UINT v24; // r14d
  UINT v25; // r15d
  UINT v26; // ebp
  BSTR v27; // rcx
  void *v28; // rcx
  struct IWbemObjectSink *v29; // rbx
  unsigned int v30; // r15d
  char *v31; // r14
  char *v32; // rcx
  struct _FILETIME *v33; // rdx
  struct IWbemObjectSinkVtbl *lpVtbl; // r8
  HRESULT v35; // edi
  unsigned __int16 *v36; // r8
  unsigned __int16 *v37; // r9
  bool v38; // zf
  void (__fastcall *v39)(char *); // rax
  int v40; // r14d
  unsigned int v41; // r14d
  struct IWbemServices *v42; // r15
  unsigned int v43; // edx
  const wchar_t *v45; // rdx
  CMemoryLog *MemLogObject; // rax
  unsigned int v47; // r14d
  __int64 v48; // [rsp+50h] [rbp-68h] BYREF
  volatile signed __int32 *v49; // [rsp+58h] [rbp-60h]
  struct IWbemObjectSink *v50; // [rsp+60h] [rbp-58h]
  VARIANTARG pvarg; // [rsp+68h] [rbp-50h] BYREF

  v7 = a4;
  v48 = 0;
  if ( a5 )
  {
    v10 = ((__int64 (__fastcall *)(struct IWbemContext *, __int64 *))a5->lpVtbl->Clone)(a5, &v48);
    v11 = v48;
    if ( v48 )
    {
      memset(&pvarg, 0, sizeof(pvarg));
      VariantInit(&pvarg);
      if ( (*(int (__fastcall **)(__int64, const wchar_t *, _QWORD, VARIANTARG *))(*(_QWORD *)v11 + 72LL))(
             v11,
             L"__GET_EXTENSIONS",
             0,
             &pvarg) >= 0 )
      {
        VariantClear(&pvarg);
        if ( (*(int (__fastcall **)(__int64, const wchar_t *, _QWORD, VARIANTARG *))(*(_QWORD *)v11 + 72LL))(
               v11,
               L"__GET_EXT_CLIENT_REQUEST",
               0,
               &pvarg) < 0 )
        {
          (*(void (__fastcall **)(__int64, const wchar_t *, _QWORD))(*(_QWORD *)v11 + 80LL))(
            v11,
            L"__GET_EXTENSIONS",
            0);
          (*(void (__fastcall **)(__int64, const wchar_t *, _QWORD))(*(_QWORD *)v11 + 80LL))(
            v11,
            L"__GET_EXT_CLIENT_REQUEST",
            0);
          (*(void (__fastcall **)(__int64, const wchar_t *, _QWORD))(*(_QWORD *)v11 + 80LL))(
            v11,
            L"__GET_EXT_KEYS_ONLY",
            0);
          v45 = L"__GET_EXT_PROPERTIES";
        }
        else
        {
          VariantClear(&pvarg);
          v45 = L"__GET_EXT_CLIENT_REQUEST";
        }
        (*(void (__fastcall **)(__int64, const wchar_t *, _QWORD))(*(_QWORD *)v11 + 80LL))(v11, v45, 0);
      }
    }
    if ( v10 < 0 )
      goto LABEL_99;
  }
  v12 = SysAllocString(a3);
  if ( !v12 )
  {
LABEL_99:
    v35 = -2147217402;
    goto LABEL_57;
  }
  v13 = (struct IErrorInfo *)ProviderSubSystem_Globals::s_Allocator;
  v14 = (void *)*((_QWORD *)ProviderSubSystem_Globals::s_Allocator + 1);
  if ( v14 )
  {
    v15 = (struct IWbemContext *)HeapAlloc(v14, *((_DWORD *)ProviderSubSystem_Globals::s_Allocator + 4) & 5 | 8u, 0x18u);
    if ( v15 )
      goto LABEL_8;
    GetLastError();
  }
  v15 = 0;
LABEL_8:
  a5 = v15;
  if ( v15 )
    v16 = (volatile signed __int32 *)_bstr_t::Data_t::Data_t((_bstr_t::Data_t *)v15, L"CreateInstanceEnumAsync: ");
  else
    v16 = 0;
  v49 = v16;
  if ( !v16 )
    _com_raise_error(-2147024882, v13);
  v17 = (struct IErrorInfo *)ProviderSubSystem_Globals::s_Allocator;
  v18 = (void *)*((_QWORD *)ProviderSubSystem_Globals::s_Allocator + 1);
  if ( v18 )
  {
    v19 = (struct IWbemContext *)HeapAlloc(v18, *((_DWORD *)ProviderSubSystem_Globals::s_Allocator + 4) & 5 | 8u, 0x18u);
    if ( v19 )
      goto LABEL_13;
    GetLastError();
  }
  v19 = 0;
LABEL_13:
  a5 = v19;
  if ( v19 )
    v20 = _bstr_t::Data_t::Data_t((_bstr_t::Data_t *)v19, v12);
  else
    v20 = 0;
  v50 = (struct IWbemObjectSink *)v20;
  if ( !v20 )
    _com_raise_error(-2147024882, v17);
  v21 = (BSTR)ProviderSubSystem_Globals::s_Allocator;
  v22 = (void *)*((_QWORD *)ProviderSubSystem_Globals::s_Allocator + 1);
  if ( v22 )
  {
    v23 = HeapAlloc(v22, *((_DWORD *)ProviderSubSystem_Globals::s_Allocator + 4) & 5 | 8u, 0x18u);
    if ( v23 )
      goto LABEL_18;
    GetLastError();
  }
  v23 = 0;
LABEL_18:
  a5 = (struct IWbemContext *)v23;
  if ( v23 )
  {
    *((_QWORD *)v23 + 1) = 0;
    *((_DWORD *)v23 + 4) = 1;
    if ( *(_QWORD *)v16 )
      v24 = SysStringLen(*(BSTR *)v16);
    else
      v24 = 0;
    if ( *(_QWORD *)v20 )
      v25 = SysStringLen(*(BSTR *)v20);
    else
      v25 = 0;
    v26 = v25 + v24;
    if ( v25 + v24 < v24 || (v21 = (BSTR)(2LL * v26), (unsigned __int64)v21 > 0xFFFFFFFF) )
      _com_raise_error(-2147024882, (struct IErrorInfo *)v21);
    v27 = SysAllocStringByteLen(0, (UINT)v21);
    *(_QWORD *)v23 = v27;
    if ( v27 )
    {
      if ( *(_QWORD *)v16 )
        memcpy_0(v27, *(const void **)v16, 2LL * (v24 + 1));
      v21 = *(BSTR *)v20;
      if ( *(_QWORD *)v20 )
        memcpy_0((void *)(*(_QWORD *)v23 + 2LL * v24), v21, 2LL * (v25 + 1));
    }
    else if ( v26 )
    {
      _com_raise_error(-2147024882, (struct IErrorInfo *)v21);
    }
    v7 = a4;
  }
  if ( _InterlockedExchangeAdd(v16 + 4, 0xFFFFFFFF) == 1 )
    _bstr_t::Data_t::`scalar deleting destructor'((_bstr_t::Data_t *)v16, (unsigned int)v21);
  v49 = (volatile signed __int32 *)v23;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v20 + 16), 0xFFFFFFFF) == 1 )
    _bstr_t::Data_t::`scalar deleting destructor'((_bstr_t::Data_t *)v20, (unsigned int)v21);
  v28 = (void *)*((_QWORD *)ProviderSubSystem_Globals::s_Allocator + 1);
  if ( v28 )
  {
    v29 = (struct IWbemObjectSink *)HeapAlloc(
                                      v28,
                                      *((_DWORD *)ProviderSubSystem_Globals::s_Allocator + 4) & 5 | 8u,
                                      0x118u);
    if ( v29 )
      goto LABEL_35;
    GetLastError();
  }
  v29 = 0;
LABEL_35:
  v50 = v29;
  if ( v29 )
  {
    v30 = v7 & 0xFFFFFDFF;
    if ( v23 )
      a5 = *(struct IWbemContext **)v23;
    else
      a5 = 0;
    v31 = (char *)this + 232;
    v32 = (char *)this + 232;
    if ( !this )
      v32 = 0;
    CCommon_Batching_IWbemSyncObjectSink::CCommon_Batching_IWbemSyncObjectSink(
      (_DWORD)v29,
      *((_QWORD *)this + 54),
      (_DWORD)a6,
      (_DWORD)this,
      (__int64)v32);
    v29->lpVtbl = (struct IWbemObjectSinkVtbl *)&CInterceptor_Batching_IWbemSyncObjectSink::`vftable'{for `IWbemObjectSinkEx'};
    v29[1].lpVtbl = (struct IWbemObjectSinkVtbl *)&CInterceptor_Batching_IWbemSyncObjectSink::`vftable'{for `IWbemShutdown'};
    v29[2].lpVtbl = (struct IWbemObjectSinkVtbl *)&CInterceptor_Batching_IWbemSyncObjectSink::`vftable'{for `WmiContainerController<void *>::WmiContainerElement'};
    v29[31].lpVtbl = (struct IWbemObjectSinkVtbl *)this;
    v29[32].lpVtbl = 0;
    GetFileTimeInUi64((unsigned __int64 *)&v29[32], v33);
    (*((void (__fastcall **)(struct IWbemObjectSinkVtbl *))v29[31].lpVtbl->QueryInterface + 1))(v29[31].lpVtbl);
    CInterceptor_IWbemSyncProvider::TrackingOperation(
      (CInterceptor_IWbemSyncProvider *)v29[31].lpVtbl,
      (unsigned __int64 *)&v29[32],
      (unsigned __int16 *)a5);
    v29->lpVtbl = (struct IWbemObjectSinkVtbl *)&CInterceptor_IWbemSyncObjectSink_CreateInstanceEnumAsync::`vftable'{for `IWbemObjectSinkEx'};
    v29[1].lpVtbl = (struct IWbemObjectSinkVtbl *)&CInterceptor_IWbemSyncObjectSink_CreateInstanceEnumAsync::`vftable'{for `IWbemShutdown'};
    v29[2].lpVtbl = (struct IWbemObjectSinkVtbl *)&CInterceptor_IWbemSyncObjectSink_CreateInstanceEnumAsync::`vftable'{for `WmiContainerController<void *>::WmiContainerElement'};
    LODWORD(v29[33].lpVtbl) = v30;
    v29[34].lpVtbl = (struct IWbemObjectSinkVtbl *)v12;
    lpVtbl = v29[31].lpVtbl;
    if ( lpVtbl )
      WmiSetAndCommitObject(
        qword_1400613C8,
        1,
        lpVtbl[15].Indicate,
        *((_QWORD *)lpVtbl[15].QueryInterface + 8),
        lpVtbl[15].Release,
        lpVtbl[15].AddRef,
        lpVtbl[15].SetStatus,
        v30,
        v12);
  }
  else
  {
    v31 = (char *)this + 232;
  }
  if ( !v29 )
  {
    SysFreeString(v12);
    v35 = -2147217402;
    goto LABEL_54;
  }
  ((void (__fastcall *)(struct IWbemObjectSink *))v29->lpVtbl->AddRef)(v29);
  v35 = ((__int64 (__fastcall *)(struct IWbemObjectSink *))v29->lpVtbl[2].QueryInterface)(v29);
  if ( v35 < 0 )
    goto LABEL_70;
  a5 = 0;
  (*(void (__fastcall **)(char *))(*(_QWORD *)v31 + 48LL))(v31);
  v38 = (*(unsigned int (__fastcall **)(char *, struct IWbemObjectSink *, struct IWbemContext **))(*(_QWORD *)v31 + 64LL))(
          v31,
          v29 + 2,
          &a5) == 0;
  v39 = *(void (__fastcall **)(char *))(*(_QWORD *)v31 + 56LL);
  if ( !v38 )
  {
    v39(v31);
    v35 = -2147217402;
    goto LABEL_70;
  }
  v39(v31);
  v40 = -641;
  if ( *(_DWORD *)(*((_QWORD *)this + 75) + 1740LL) )
    v40 = -513;
  if ( a2 && CoImpersonateClient() < 0 )
  {
    v35 = -2147217405;
    goto LABEL_70;
  }
  v41 = a4 & v40;
  if ( ProviderSubSystem_Globals::s_SharedCounters )
    ++*((_QWORD *)ProviderSubSystem_Globals::s_SharedCounters + 22);
  ++*((_QWORD *)this + 86);
  v42 = a7;
  v35 = ((__int64 (__fastcall *)(struct IWbemServices *, unsigned __int16 *, _QWORD, __int64, struct IWbemObjectSink *))a7->lpVtbl->CreateInstanceEnumAsync)(
          a7,
          v12,
          v41,
          v48,
          v29);
  CoRevertToSelf();
  if ( v35 == -2147217355 || v35 == -2147217400 )
  {
    if ( a2 )
    {
      v35 = CoImpersonateClient();
      if ( v35 < 0 )
        goto LABEL_70;
    }
    v47 = v41 & 0xFFFFFF7F;
    if ( ProviderSubSystem_Globals::s_SharedCounters )
      ++*((_QWORD *)ProviderSubSystem_Globals::s_SharedCounters + 22);
    ++*((_QWORD *)this + 86);
    v35 = ((__int64 (__fastcall *)(struct IWbemServices *, unsigned __int16 *, _QWORD, __int64, struct IWbemObjectSink *))v42->lpVtbl->CreateInstanceEnumAsync)(
            v42,
            v12,
            v47,
            v48,
            v29);
    CoRevertToSelf();
  }
  if ( v35 < 0 )
LABEL_70:
    CInterceptor_IWbemSyncProvider::SetStatus(this, L"CreateInstanceEnumAsync", v36, v37, v35, v29);
  ((void (__fastcall *)(struct IWbemObjectSink *))v29->lpVtbl->Release)(v29);
LABEL_54:
  if ( v23 && _InterlockedExchangeAdd((volatile signed __int32 *)v23 + 4, 0xFFFFFFFF) == 1 )
    _bstr_t::Data_t::`scalar deleting destructor'((_bstr_t::Data_t *)v23, v43);
LABEL_57:
  if ( v48 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
  if ( v35 < 0 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v35);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      112,
      WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids,
      (unsigned int)v35);
  }
  return (unsigned int)v35;
}

```

## disassembly

```asm
0x14000c850  mov     [rsp+arg_0], rbx
0x14000c855  mov     [rsp+arg_18], r9d
0x14000c85a  mov     [rsp+arg_8], edx
0x14000c85e  push    rbp
0x14000c85f  push    rsi
0x14000c860  push    rdi
0x14000c861  push    r12
0x14000c863  push    r13
0x14000c865  push    r14
0x14000c867  push    r15
0x14000c869  sub     rsp, 80h
0x14000c870  mov     r14d, r9d
0x14000c873  mov     rdi, r8
0x14000c876  mov     r13, rcx
0x14000c879  mov     [rsp+0B8h+var_68], 0
0x14000c882  mov     rcx, [rsp+0B8h+arg_20]
0x14000c88a  test    rcx, rcx
0x14000c88d  jz      short loc_14000C8F4
0x14000c88f  mov     rax, [rcx]
0x14000c892  lea     rdx, [rsp+0B8h+var_68]
0x14000c897  mov     rax, [rax+18h]
0x14000c89b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c8a0  mov     esi, eax
0x14000c8a2  mov     rbx, [rsp+0B8h+var_68]
0x14000c8a7  test    rbx, rbx
0x14000c8aa  jz      short loc_14000C8EC
0x14000c8ac  xorps   xmm0, xmm0
0x14000c8af  xor     eax, eax
0x14000c8b1  movups  xmmword ptr [rsp+0B8h+pvarg], xmm0
0x14000c8b6  mov     qword ptr [rsp+0B8h+pvarg+10h], rax
0x14000c8bb  lea     rcx, [rsp+0B8h+pvarg]; pvarg
0x14000c8c0  call    cs:__imp_VariantInit
0x14000c8c6  mov     rcx, [rbx]
0x14000c8c9  mov     rax, [rcx+48h]
0x14000c8cd  lea     r9, [rsp+0B8h+pvarg]
0x14000c8d2  xor     r8d, r8d
0x14000c8d5  lea     rdx, aGetExtensions; "__GET_EXTENSIONS"
0x14000c8dc  mov     rcx, rbx
0x14000c8df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c8e4  test    eax, eax
0x14000c8e6  jns     loc_14000CDD5
0x14000c8ec  test    esi, esi
0x14000c8ee  js      loc_14000D054
0x14000c8f4  mov     rcx, rdi; psz
0x14000c8f7  call    cs:__imp_SysAllocString
0x14000c8fd  mov     r12, rax
0x14000c900  test    rax, rax
0x14000c903  jz      loc_14000D054
0x14000c909  mov     rdx, cs:?s_Allocator@ProviderSubSystem_Globals@@2PEAVWmiAllocator@@EA; WmiAllocator * ProviderSubSystem_Globals::s_Allocator
0x14000c910  mov     rcx, [rdx+8]; hHeap
0x14000c914  test    rcx, rcx
0x14000c917  jz      loc_14000CECE
0x14000c91d  mov     edx, [rdx+10h]
0x14000c920  and     edx, 5
0x14000c923  or      edx, 8; dwFlags
0x14000c926  mov     r8d, 18h; dwBytes
0x14000c92c  call    cs:__imp_HeapAlloc
0x14000c932  test    rax, rax
0x14000c935  jz      loc_14000CEC8
0x14000c93b  mov     [rsp+0B8h+arg_20], rax
0x14000c943  test    rax, rax
0x14000c946  jnz     loc_14000CED5
0x14000c94c  xor     edi, edi
0x14000c94e  mov     [rsp+0B8h+var_60], rdi
0x14000c953  test    rdi, rdi
0x14000c956  jz      loc_14000CEEC
0x14000c95c  mov     rdx, cs:?s_Allocator@ProviderSubSystem_Globals@@2PEAVWmiAllocator@@EA; WmiAllocator * ProviderSubSystem_Globals::s_Allocator
0x14000c963  mov     rcx, [rdx+8]; hHeap
0x14000c967  test    rcx, rcx
0x14000c96a  jz      loc_14000CEFD
0x14000c970  mov     edx, [rdx+10h]
0x14000c973  and     edx, 5
0x14000c976  or      edx, 8; dwFlags
0x14000c979  mov     r8d, 18h; dwBytes
0x14000c97f  call    cs:__imp_HeapAlloc
0x14000c985  test    rax, rax
0x14000c988  jz      loc_14000CEF7
0x14000c98e  mov     [rsp+0B8h+arg_20], rax
0x14000c996  test    rax, rax
0x14000c999  jnz     loc_14000CF04
0x14000c99f  xor     ebx, ebx
0x14000c9a1  mov     [rsp+0B8h+var_58], rbx
0x14000c9a6  test    rbx, rbx
0x14000c9a9  jz      loc_14000CF17
0x14000c9af  mov     rdx, cs:?s_Allocator@ProviderSubSystem_Globals@@2PEAVWmiAllocator@@EA; WmiAllocator * ProviderSubSystem_Globals::s_Allocator
0x14000c9b6  mov     rcx, [rdx+8]; hHeap
0x14000c9ba  test    rcx, rcx
0x14000c9bd  jz      loc_14000CF28
0x14000c9c3  mov     edx, [rdx+10h]
0x14000c9c6  and     edx, 5
0x14000c9c9  or      edx, 8; dwFlags
0x14000c9cc  mov     r8d, 18h; dwBytes
0x14000c9d2  call    cs:__imp_HeapAlloc
0x14000c9d8  mov     rsi, rax
0x14000c9db  test    rax, rax
0x14000c9de  jz      loc_14000CF22
0x14000c9e4  mov     [rsp+0B8h+arg_20], rsi
0x14000c9ec  test    rsi, rsi
0x14000c9ef  jz      loc_14000CA78
0x14000c9f5  mov     qword ptr [rsi+8], 0
0x14000c9fd  mov     dword ptr [rsi+10h], 1
0x14000ca04  mov     rcx, [rdi]; pbstr
0x14000ca07  test    rcx, rcx
0x14000ca0a  jz      loc_14000CF2F
0x14000ca10  call    cs:__imp_SysStringLen
0x14000ca16  mov     r14d, eax
0x14000ca19  mov     rcx, [rbx]; pbstr
0x14000ca1c  test    rcx, rcx
0x14000ca1f  jz      loc_14000CF37
0x14000ca25  call    cs:__imp_SysStringLen
0x14000ca2b  mov     r15d, eax
0x14000ca2e  lea     ebp, [r15+r14]
0x14000ca32  cmp     ebp, r14d
0x14000ca35  jb      short loc_14000CA46
0x14000ca37  mov     edx, ebp
0x14000ca39  add     rdx, rdx; struct IErrorInfo *
0x14000ca3c  mov     eax, 0FFFFFFFFh
0x14000ca41  cmp     rdx, rax
0x14000ca44  jbe     short loc_14000CA51
0x14000ca46  mov     ecx, 8007000Eh; int
0x14000ca4b  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x14000ca51  xor     ecx, ecx; psz
0x14000ca53  call    cs:__imp_SysAllocStringByteLen
0x14000ca59  mov     rcx, rax; void *
0x14000ca5c  mov     [rsi], rax
0x14000ca5f  test    rax, rax
0x14000ca62  jnz     loc_14000CF4A
0x14000ca68  test    ebp, ebp
0x14000ca6a  jnz     loc_14000CF3F
0x14000ca70  mov     r14d, [rsp+0B8h+arg_18]
0x14000ca78  mov     ebp, 0FFFFFFFFh
0x14000ca7d  mov     eax, ebp
0x14000ca7f  lock xadd [rdi+10h], eax
0x14000ca84  cmp     eax, 1
0x14000ca87  jz      loc_14000CF85
0x14000ca8d  mov     [rsp+0B8h+var_60], rsi
0x14000ca92  mov     eax, ebp
0x14000ca94  lock xadd [rbx+10h], eax
0x14000ca99  cmp     eax, 1
0x14000ca9c  jz      loc_14000CF92
0x14000caa2  mov     rdx, cs:?s_Allocator@ProviderSubSystem_Globals@@2PEAVWmiAllocator@@EA; WmiAllocator * ProviderSubSystem_Globals::s_Allocator
0x14000caa9  mov     rcx, [rdx+8]; hHeap
0x14000caad  test    rcx, rcx
0x14000cab0  jz      loc_14000CFA5
0x14000cab6  mov     edx, [rdx+10h]
0x14000cab9  and     edx, 5
0x14000cabc  or      edx, 8; dwFlags
0x14000cabf  mov     r8d, 118h; dwBytes
0x14000cac5  call    cs:__imp_HeapAlloc
0x14000cacb  mov     rbx, rax
0x14000cace  test    rax, rax
0x14000cad1  jz      loc_14000CF9F
0x14000cad7  mov     [rsp+0B8h+var_58], rbx
0x14000cadc  test    rbx, rbx
0x14000cadf  jz      loc_14000CDC9
0x14000cae5  mov     r15d, r14d
0x14000cae8  btr     r15d, 9
0x14000caed  test    rsi, rsi
0x14000caf0  jz      loc_14000CFAC
0x14000caf6  mov     rax, [rsi]
0x14000caf9  mov     [rsp+0B8h+arg_20], rax
0x14000cb01  lea     r14, [r13+0E8h]
0x14000cb08  mov     rcx, r14
0x14000cb0b  xor     eax, eax
0x14000cb0d  test    r13, r13
0x14000cb10  cmovz   rcx, rax
0x14000cb14  mov     qword ptr [rsp+0B8h+var_98], rcx
0x14000cb19  mov     r9, r13
0x14000cb1c  mov     r8, [rsp+0B8h+arg_28]
0x14000cb24  mov     rdx, [r13+1B0h]
0x14000cb2b  mov     rcx, rbx
0x14000cb2e  call    ??0CCommon_Batching_IWbemSyncObjectSink@@QEAA@AEAVWmiAllocator@@PEAUIWbemObjectSink@@PEAUIUnknown@@PEAV?$WmiContainerController@PEAX@@K@Z; CCommon_Batching_IWbemSyncObjectSink::CCommon_Batching_IWbemSyncObjectSink(WmiAllocator &,IWbemObjectSink *,IUnknown *,WmiContainerController<void *> *,ulong)
0x14000cb33  nop
0x14000cb34  lea     rax, ??_7CInterceptor_Batching_IWbemSyncObjectSink@@6BIWbemObjectSinkEx@@@; const CInterceptor_Batching_IWbemSyncObjectSink::`vftable'{for `IWbemObjectSinkEx'}
0x14000cb3b  mov     [rbx], rax
0x14000cb3e  lea     rax, ??_7CInterceptor_Batching_IWbemSyncObjectSink@@6BIWbemShutdown@@@; const CInterceptor_Batching_IWbemSyncObjectSink::`vftable'{for `IWbemShutdown'}
0x14000cb45  mov     [rbx+8], rax
0x14000cb49  lea     rax, ??_7CInterceptor_Batching_IWbemSyncObjectSink@@6BWmiContainerElement@?$WmiContainerController@PEAX@@@; const CInterceptor_Batching_IWbemSyncObjectSink::`vftable'{for `WmiContainerController<void *>::WmiContainerElement'}
0x14000cb50  mov     [rbx+10h], rax
0x14000cb54  mov     [rbx+0F8h], r13
0x14000cb5b  mov     qword ptr [rbx+100h], 0
0x14000cb66  lea     rcx, [rbx+100h]; unsigned __int64 *
0x14000cb6d  call    ?GetFileTimeInUi64@@YAXPEA_KPEAU_FILETIME@@@Z; GetFileTimeInUi64(unsigned __int64 *,_FILETIME *)
0x14000cb72  mov     rcx, [rbx+0F8h]
0x14000cb79  mov     rax, [rcx]
0x14000cb7c  mov     rax, [rax+8]
0x14000cb80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cb85  mov     r8, [rsp+0B8h+arg_20]; unsigned __int16 *
0x14000cb8d  lea     rdx, [rbx+100h]; unsigned __int64 *
0x14000cb94  mov     rcx, [rbx+0F8h]; this
0x14000cb9b  call    ?TrackingOperation@CInterceptor_IWbemSyncProvider@@QEAAHAEA_KPEAG@Z; CInterceptor_IWbemSyncProvider::TrackingOperation(unsigned __int64 &,ushort *)
0x14000cba0  nop
0x14000cba1  lea     rax, ??_7CInterceptor_IWbemSyncObjectSink_CreateInstanceEnumAsync@@6BIWbemObjectSinkEx@@@; const CInterceptor_IWbemSyncObjectSink_CreateInstanceEnumAsync::`vftable'{for `IWbemObjectSinkEx'}
0x14000cba8  mov     [rbx], rax
0x14000cbab  lea     rax, ??_7CInterceptor_IWbemSyncObjectSink_CreateInstanceEnumAsync@@6BIWbemShutdown@@@; const CInterceptor_IWbemSyncObjectSink_CreateInstanceEnumAsync::`vftable'{for `IWbemShutdown'}
0x14000cbb2  mov     [rbx+8], rax
0x14000cbb6  lea     rax, ??_7CInterceptor_IWbemSyncObjectSink_CreateInstanceEnumAsync@@6BWmiContainerElement@?$WmiContainerController@PEAX@@@; const CInterceptor_IWbemSyncObjectSink_CreateInstanceEnumAsync::`vftable'{for `WmiContainerController<void *>::WmiContainerElement'}
0x14000cbbd  mov     [rbx+10h], rax
0x14000cbc1  mov     [rbx+108h], r15d
0x14000cbc8  mov     [rbx+110h], r12
0x14000cbcf  mov     r8, [rbx+0F8h]
0x14000cbd6  test    r8, r8
0x14000cbd9  jz      short loc_14000CC2E
0x14000cbdb  mov     r9, [r8+258h]
0x14000cbe2  mov     [rsp+0B8h+var_78], r12
0x14000cbe7  mov     [rsp+0B8h+var_80], r15d
0x14000cbec  mov     rax, [r8+278h]
0x14000cbf3  mov     [rsp+0B8h+var_88], rax
0x14000cbf8  mov     rax, [r8+260h]
0x14000cbff  mov     [rsp+0B8h+var_90], rax
0x14000cc04  mov     rax, [r8+268h]
0x14000cc0b  mov     qword ptr [rsp+0B8h+var_98], rax
0x14000cc10  mov     r9, [r9+40h]
0x14000cc14  mov     r8, [r8+270h]
0x14000cc1b  mov     edx, 1
0x14000cc20  mov     rcx, cs:qword_1400613C8
0x14000cc27  call    cs:__imp_WmiSetAndCommitObject
0x14000cc2d  nop
0x14000cc2e  test    rbx, rbx
0x14000cc31  jz      loc_14000D034
0x14000cc37  mov     rax, [rbx]
0x14000cc3a  mov     rcx, rbx
0x14000cc3d  mov     rax, [rax+8]
0x14000cc41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cc46  mov     rax, [rbx]
0x14000cc49  mov     rcx, rbx
0x14000cc4c  mov     rax, [rax+50h]
0x14000cc50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cc55  mov     edi, eax
0x14000cc57  test    eax, eax
0x14000cc59  js      loc_14000CE3E
0x14000cc5f  mov     [rsp+0B8h+arg_20], 0
0x14000cc6b  mov     rax, [r14]
0x14000cc6e  mov     rcx, r14
0x14000cc71  mov     rax, [rax+30h]
0x14000cc75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cc7a  mov     rax, [r14]
0x14000cc7d  lea     rdx, [rbx+10h]
0x14000cc81  lea     r8, [rsp+0B8h+arg_20]
0x14000cc89  mov     rcx, r14
0x14000cc8c  mov     rax, [rax+40h]
0x14000cc90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cc95  mov     rdx, [r14]
0x14000cc98  mov     r8, [rdx+38h]
0x14000cc9c  mov     rcx, r14
0x14000cc9f  test    eax, eax
0x14000cca1  mov     rax, r8
0x14000cca4  jnz     loc_14000D025
0x14000ccaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ccaf  mov     rax, [r13+258h]
0x14000ccb6  mov     r14d, 0FFFFFD7Fh
0x14000ccbc  cmp     dword ptr [rax+6CCh], 0
0x14000ccc3  mov     eax, 0FFFFFDFFh
0x14000ccc8  cmovnz  r14d, eax
0x14000cccc  cmp     [rsp+0B8h+arg_8], 0
0x14000ccd4  jnz     loc_14000CE2B
0x14000ccda  and     r14d, [rsp+0B8h+arg_18]
0x14000cce2  mov     rax, cs:?s_SharedCounters@ProviderSubSystem_Globals@@2PEAVCServerObject_ProviderSubsystem_Counters@@EA; CServerObject_ProviderSubsystem_Counters * ProviderSubSystem_Globals::s_SharedCounters
0x14000cce9  test    rax, rax
0x14000ccec  jz      short loc_14000CCF5
0x14000ccee  inc     qword ptr [rax+0B0h]
0x14000ccf5  inc     qword ptr [r13+2B0h]
0x14000ccfc  mov     r15, [rsp+0B8h+arg_30]
0x14000cd04  mov     rax, [r15]
0x14000cd07  mov     qword ptr [rsp+0B8h+var_98], rbx
0x14000cd0c  mov     r9, [rsp+0B8h+var_68]
0x14000cd11  mov     r8d, r14d
0x14000cd14  mov     rdx, r12
0x14000cd17  mov     rcx, r15
0x14000cd1a  mov     rax, [rax+98h]
0x14000cd21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cd26  mov     edi, eax
0x14000cd28  call    cs:__imp_CoRevertToSelf
0x14000cd2e  cmp     edi, 80041035h
0x14000cd34  jz      loc_14000CFBD
0x14000cd3a  cmp     edi, 80041008h
0x14000cd40  jz      loc_14000CFBD
0x14000cd46  test    edi, edi
0x14000cd48  js      loc_14000CE3E
0x14000cd4e  mov     rax, [rbx]
0x14000cd51  mov     rcx, rbx
0x14000cd54  mov     rax, [rax+10h]
0x14000cd58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cd5d  nop
0x14000cd5e  test    rsi, rsi
0x14000cd61  jz      short loc_14000CD71
0x14000cd63  lock xadd [rsi+10h], ebp
0x14000cd68  cmp     ebp, 1
0x14000cd6b  jz      loc_14000D047
0x14000cd71  mov     rcx, [rsp+0B8h+var_68]
0x14000cd76  test    rcx, rcx
0x14000cd79  jz      short loc_14000CD87
0x14000cd7b  mov     rax, [rcx]
0x14000cd7e  mov     rax, [rax+10h]
0x14000cd82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cd87  test    edi, edi
0x14000cd89  js      loc_14000CEB2
0x14000cd8f  lea     rax, WPP_GLOBAL_Control
0x14000cd96  mov     rcx, cs:WPP_GLOBAL_Control
0x14000cd9d  cmp     rcx, rax
  ... truncated ...
```
