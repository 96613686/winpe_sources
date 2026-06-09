# CInterceptor_IWbemSyncProvider::Helper_ExecQueryAsync(int,ushort * const,ushort * const,long,IWbemContext *,IWbemObjectSink *,IWbemServices *)

- ea: `0x14000fe70`
- end: `0x140010618`
- name: `?Helper_ExecQueryAsync@CInterceptor_IWbemSyncProvider@@AEAAJHQEAG0JPEAUIWbemContext@@PEAUIWbemObjectSink@@PEAUIWbemServices@@@Z`
- size: `1960`
- prototype: `__int64 __fastcall(CInterceptor_IWbemSyncProvider *this, struct IUnknown *, unsigned __int16 *const, unsigned __int16 *const, int, struct IWbemContext *, struct IWbemObjectSink *, struct IWbemServices *)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140028ef0`

## callees

- `0x14000212c`
- `0x140006e0c`
- `0x14000a530`
- `0x14000c190`
- `0x14000d5fc`
- `0x14000e738`
- `0x14000f600`
- `0x14000fe70`
- `0x14001b3d0`
- `0x1400209a0`
- `0x1400234b8`
- `0x140029d34`
- `0x14002a55c`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x1400105ba`
- `wbemcomn!GetMemLogObject` at `0x1400105ba`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1400105c5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1400105c5`
- `OLEAUT32!__imp_SysAllocString` at `0x14000ff80`
- `OLEAUT32!__imp_SysAllocString` at `0x140010298`
- `OLEAUT32!__imp_SysAllocString` at `0x1400102a8`
- `OLEAUT32!__imp_SysAllocString` at `0x14000ff80`
- `OLEAUT32!__imp_SysAllocString` at `0x140010298`
- `OLEAUT32!__imp_SysAllocString` at `0x1400102a8`
- `OLEAUT32!__imp_SysFreeString` at `0x140010228`
- `OLEAUT32!__imp_SysFreeString` at `0x140010566`
- `OLEAUT32!__imp_SysFreeString` at `0x14001056f`
- `OLEAUT32!__imp_SysFreeString` at `0x140010228`
- `OLEAUT32!__imp_SysFreeString` at `0x140010566`
- `OLEAUT32!__imp_SysFreeString` at `0x14001056f`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1400100fd`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x140010195`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x14001044c`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1400104cc`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1400100fd`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x140010195`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x14001044c`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1400104cc`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140010179`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1400101e6`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1400104b0`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140010524`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140010179`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1400101e6`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1400104b0`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140010524`

## string_xrefs

- `0x140010205`: `CreateInstanceEnumAsync`
- `0x14000ff92`: `CreateInstanceEnumAsync: `

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CInterceptor_IWbemSyncProvider::Helper_ExecQueryAsync(
        CInterceptor_IWbemSyncProvider *this,
        struct IUnknown *a2,
        unsigned __int16 *const a3,
        unsigned __int16 *const a4,
        int a5,
        struct IWbemContext *a6,
        struct IWbemObjectSink *a7,
        struct IWbemServices *a8)
{
  unsigned int v11; // r14d
  __int64 v12; // rax
  __int64 v13; // rdx
  unsigned __int16 *v14; // r15
  _bstr_t::Data_t *v15; // r10
  unsigned __int16 *v16; // rdx
  char *v17; // r12
  struct IWbemObjectSink *InstanceEnumAsync; // rsi
  int v19; // ebx
  unsigned __int16 *v20; // r8
  unsigned __int16 *v21; // r9
  bool v22; // zf
  void (__fastcall *v23)(char *); // rax
  int v24; // r14d
  unsigned int v25; // r14d
  unsigned int v26; // r14d
  BSTR v27; // rbx
  BSTR v28; // rax
  unsigned __int16 *v29; // r13
  _bstr_t::Data_t *v30; // rax
  unsigned int v31; // edx
  _bstr_t::Data_t *v32; // rcx
  _bstr_t::Data_t *v33; // r10
  volatile signed __int32 *v34; // r15
  unsigned __int16 *v35; // rdx
  char *v36; // r12
  struct IWbemObjectSink *Async; // rsi
  void (__fastcall *v38)(char *); // rax
  unsigned __int16 *v39; // r8
  unsigned __int16 *v40; // r9
  void *v41; // r12
  unsigned int v42; // r14d
  unsigned int v43; // edx
  CMemoryLog *MemLogObject; // rax
  int v46; // [rsp+40h] [rbp-51h]
  int v47; // [rsp+48h] [rbp-49h]
  unsigned int v48[2]; // [rsp+60h] [rbp-31h] BYREF
  __int64 v49; // [rsp+68h] [rbp-29h] BYREF
  void *v50; // [rsp+70h] [rbp-21h] BYREF
  _bstr_t::Data_t *v51; // [rsp+78h] [rbp-19h] BYREF
  _bstr_t::Data_t *v52[10]; // [rsp+80h] [rbp-11h] BYREF
  int v53; // [rsp+E8h] [rbp+57h]

  v53 = (int)a2;
  v49 = 0;
  if ( a6 && ((int (__fastcall *)(struct IWbemContext *, __int64 *))a6->lpVtbl->Clone)(a6, &v49) < 0 )
    goto LABEL_89;
  v11 = a5 & 0xFFFFFDFF;
  v12 = *((_QWORD *)this + 75);
  if ( (*(_BYTE *)(v12 + 2048) & 9) != 0 )
  {
    v27 = SysAllocString(a3);
    v50 = v27;
    v28 = SysAllocString(a4);
    v29 = v28;
    if ( v27 && v28 )
    {
      v30 = (_bstr_t::Data_t *)operator new(0x18u);
      v52[0] = v30;
      if ( v30 )
        v30 = (_bstr_t::Data_t *)_bstr_t::Data_t::Data_t(v30, L"ExecQueryAsync: ");
      v51 = v30;
      if ( !v30 )
        _com_issue_error(-2147024882);
      _bstr_t::_bstr_t((_bstr_t *)v52, v29);
      _bstr_t::operator+=(&v51, v52);
      v32 = v52[0];
      if ( v52[0] && _InterlockedExchangeAdd((volatile signed __int32 *)v52[0] + 4, 0xFFFFFFFF) == 1 && v32 )
        _bstr_t::Data_t::`scalar deleting destructor'(v32, v31);
      v33 = (_bstr_t::Data_t *)operator new(0x120u);
      v52[0] = v33;
      v34 = (volatile signed __int32 *)v51;
      if ( v33 )
      {
        if ( v51 )
          v35 = *(unsigned __int16 **)v51;
        else
          v35 = 0;
        v36 = (char *)this + 232;
        Async = (struct IWbemObjectSink *)CInterceptor_IWbemSyncObjectSink_ExecQueryAsync::CInterceptor_IWbemSyncObjectSink_ExecQueryAsync(
                                            (int)v33,
                                            *((_QWORD *)this + 54),
                                            v11,
                                            (int)v27,
                                            (__int64)v29,
                                            (__int64)this,
                                            (__int64)a7,
                                            (__int64)this,
                                            ((unsigned __int64)this + 232) & -(__int64)(this != 0),
                                            v47,
                                            v35);
      }
      else
      {
        Async = 0;
        v36 = (char *)this + 232;
      }
      if ( !Async )
      {
        SysFreeString(v29);
        SysFreeString(v27);
        v19 = -2147217402;
        goto LABEL_86;
      }
      ((void (__fastcall *)(struct IWbemObjectSink *))Async->lpVtbl->AddRef)(Async);
      v19 = ((__int64 (__fastcall *)(struct IWbemObjectSink *))Async->lpVtbl[2].QueryInterface)(Async);
      if ( v19 < 0 )
      {
LABEL_84:
        ((void (__fastcall *)(struct IWbemObjectSink *))Async->lpVtbl->Release)(Async);
LABEL_86:
        if ( v34 && _InterlockedExchangeAdd(v34 + 4, 0xFFFFFFFF) == 1 )
          _bstr_t::Data_t::`scalar deleting destructor'((_bstr_t::Data_t *)v34, v43);
        goto LABEL_90;
      }
      v52[0] = 0;
      (*(void (__fastcall **)(char *))(*(_QWORD *)v36 + 48LL))(v36);
      v22 = (*(unsigned int (__fastcall **)(char *, struct IWbemObjectSink *, _bstr_t::Data_t **))(*(_QWORD *)v36 + 64LL))(
              v36,
              Async + 2,
              v52) == 0;
      v38 = *(void (__fastcall **)(char *))(*(_QWORD *)v36 + 56LL);
      if ( !v22 )
      {
        v38(v36);
        v19 = -2147217402;
LABEL_83:
        CInterceptor_IWbemSyncProvider::SetStatus(this, L"ExecQueryAsync", v39, v40, v19, Async);
        goto LABEL_84;
      }
      v38(v36);
      if ( !*(_DWORD *)(*((_QWORD *)this + 75) + 1740LL) )
        v11 = a5 & 0xFFFFFD7F;
      if ( v53 && CoImpersonateClient() < 0 )
        goto LABEL_70;
      if ( ProviderSubSystem_Globals::s_SharedCounters )
        ++*((_QWORD *)ProviderSubSystem_Globals::s_SharedCounters + 23);
      ++*((_QWORD *)this + 87);
      v41 = v50;
      v19 = ((__int64 (__fastcall *)(struct IWbemServices *, void *, unsigned __int16 *, _QWORD, __int64, struct IWbemObjectSink *))a8->lpVtbl->ExecQueryAsync)(
              a8,
              v50,
              v29,
              v11,
              v49,
              Async);
      CoRevertToSelf();
      if ( v19 == -2147217355 || v19 == -2147217400 )
      {
        if ( v53 && CoImpersonateClient() < 0 )
        {
LABEL_70:
          v19 = -2147217405;
          goto LABEL_80;
        }
        v42 = v11 & 0xFFFFFF7F;
        if ( ProviderSubSystem_Globals::s_SharedCounters )
          ++*((_QWORD *)ProviderSubSystem_Globals::s_SharedCounters + 23);
        ++*((_QWORD *)this + 87);
        v19 = ((__int64 (__fastcall *)(struct IWbemServices *, void *, unsigned __int16 *, _QWORD, __int64, struct IWbemObjectSink *))a8->lpVtbl->ExecQueryAsync)(
                a8,
                v41,
                v29,
                v42,
                v49,
                Async);
        CoRevertToSelf();
      }
LABEL_80:
      if ( v19 >= 0 )
        goto LABEL_84;
      goto LABEL_83;
    }
LABEL_89:
    v19 = -2147217402;
    goto LABEL_90;
  }
  if ( *(_DWORD *)(v12 + 2032) )
  {
    v50 = 0;
    v48[0] = 5;
    if ( (int)ProviderSubSystem_Common_Globals::CreateInstance(&CLSID_WbemQuery, a2, v48, &IID_IWbemQuery, &v50) >= 0 )
    {
      if ( (*(int (__fastcall **)(void *, unsigned __int16 *const, unsigned __int16 *const, _QWORD))(*(_QWORD *)v50 + 48LL))(
             v50,
             a3,
             a4,
             0) < 0 )
      {
        v19 = -2147217396;
        goto LABEL_44;
      }
      *(_QWORD *)v48 = 0;
      if ( (*(int (__fastcall **)(void *, __int64, _QWORD, unsigned int *))(*(_QWORD *)v50 + 56LL))(v50, 1, 0, v48) < 0 )
      {
        v19 = -2147217379;
        goto LABEL_44;
      }
      v13 = *(_QWORD *)v48;
      if ( *(_DWORD *)(*(_QWORD *)v48 + 48LL) != 1 )
      {
        v19 = -2147217396;
        goto LABEL_41;
      }
      v14 = SysAllocString(**(const OLECHAR ***)(*(_QWORD *)v48 + 72LL));
      if ( !v14 )
      {
        v19 = -2147217402;
        goto LABEL_39;
      }
      _bstr_t::_bstr_t((_bstr_t *)&v51, L"CreateInstanceEnumAsync: ");
      _bstr_t::_bstr_t((_bstr_t *)v52, v14);
      _bstr_t::operator+=(&v51, v52);
      _bstr_t::~_bstr_t((_bstr_t *)v52);
      v15 = (_bstr_t::Data_t *)operator new(0x118u);
      v52[0] = v15;
      if ( v15 )
      {
        if ( v51 )
          v16 = *(unsigned __int16 **)v51;
        else
          v16 = 0;
        v17 = (char *)this + 232;
        InstanceEnumAsync = (struct IWbemObjectSink *)CInterceptor_IWbemSyncObjectSink_CreateInstanceEnumAsync::CInterceptor_IWbemSyncObjectSink_CreateInstanceEnumAsync(
                                                        (int)v15,
                                                        *((_QWORD *)this + 54),
                                                        v11,
                                                        (int)v14,
                                                        (struct _FILETIME)this,
                                                        (__int64)a7,
                                                        (__int64)this,
                                                        ((unsigned __int64)this + 232) & -(__int64)(this != 0),
                                                        v46,
                                                        v16);
      }
      else
      {
        InstanceEnumAsync = 0;
        v17 = (char *)this + 232;
      }
      if ( !InstanceEnumAsync )
      {
        SysFreeString(v14);
        v19 = -2147217402;
        goto LABEL_37;
      }
      ((void (__fastcall *)(struct IWbemObjectSink *))InstanceEnumAsync->lpVtbl->AddRef)(InstanceEnumAsync);
      v19 = ((__int64 (__fastcall *)(struct IWbemObjectSink *))InstanceEnumAsync->lpVtbl[2].QueryInterface)(InstanceEnumAsync);
      if ( v19 >= 0 )
      {
        ((void (__fastcall *)(struct IWbemObjectSink *, __int64, _QWORD, _QWORD, _QWORD))a7->lpVtbl->SetStatus)(
          a7,
          1,
          0,
          0,
          0);
        v52[0] = 0;
        (*(void (__fastcall **)(char *))(*(_QWORD *)v17 + 48LL))(v17);
        v22 = (*(unsigned int (__fastcall **)(char *, struct IWbemObjectSink *, _bstr_t::Data_t **))(*(_QWORD *)v17 + 64LL))(
                v17,
                InstanceEnumAsync + 2,
                v52) == 0;
        v23 = *(void (__fastcall **)(char *))(*(_QWORD *)v17 + 56LL);
        if ( v22 )
        {
          v23(v17);
          v24 = *(_DWORD *)(*((_QWORD *)this + 75) + 1740LL) != 0 ? -513 : -641;
          if ( v53 && CoImpersonateClient() < 0 )
            goto LABEL_21;
          v25 = a5 & v24;
          ((void (__fastcall *)(struct IWbemObjectSink *, __int64, _QWORD))a7->lpVtbl->SetStatus)(a7, 1, 0);
          if ( ProviderSubSystem_Globals::s_SharedCounters )
            ++*((_QWORD *)ProviderSubSystem_Globals::s_SharedCounters + 22);
          ++*((_QWORD *)this + 86);
          v19 = ((__int64 (__fastcall *)(struct IWbemServices *, unsigned __int16 *, _QWORD, __int64, struct IWbemObjectSink *))a8->lpVtbl->CreateInstanceEnumAsync)(
                  a8,
                  v14,
                  v25,
                  v49,
                  InstanceEnumAsync);
          CoRevertToSelf();
          if ( v19 == -2147217355 || v19 == -2147217400 )
          {
            if ( v53 && CoImpersonateClient() < 0 )
            {
LABEL_21:
              v19 = -2147217405;
              goto LABEL_31;
            }
            v26 = v25 & 0xFFFFFF7F;
            if ( ProviderSubSystem_Globals::s_SharedCounters )
              ++*((_QWORD *)ProviderSubSystem_Globals::s_SharedCounters + 22);
            ++*((_QWORD *)this + 86);
            v19 = ((__int64 (__fastcall *)(struct IWbemServices *, unsigned __int16 *, _QWORD, __int64, struct IWbemObjectSink *))a8->lpVtbl->CreateInstanceEnumAsync)(
                    a8,
                    v14,
                    v26,
                    v49,
                    InstanceEnumAsync);
            CoRevertToSelf();
          }
LABEL_31:
          if ( v19 >= 0 )
            goto LABEL_35;
          goto LABEL_34;
        }
        v23(v17);
        v19 = -2147217402;
      }
LABEL_34:
      CInterceptor_IWbemSyncProvider::SetStatus(this, L"CreateInstanceEnumAsync", v20, v21, v19, InstanceEnumAsync);
LABEL_35:
      ((void (__fastcall *)(struct IWbemObjectSink *))InstanceEnumAsync->lpVtbl->Release)(InstanceEnumAsync);
LABEL_37:
      _bstr_t::~_bstr_t((_bstr_t *)&v51);
LABEL_39:
      v13 = *(_QWORD *)v48;
LABEL_41:
      (*(void (__fastcall **)(void *, __int64))(*(_QWORD *)v50 + 64LL))(v50, v13);
LABEL_44:
      (*(void (__fastcall **)(void *))(*(_QWORD *)v50 + 16LL))(v50);
      goto LABEL_90;
    }
    v19 = -2147217398;
  }
  else
  {
    v19 = -2147217396;
  }
LABEL_90:
  if ( v49 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
  if ( v19 < 0 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v19);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      118,
      WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids,
      (unsigned int)v19);
  }
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x14000fe70  mov     [rsp-8+arg_8], edx
0x14000fe74  push    rbp
0x14000fe75  push    rbx
0x14000fe76  push    rsi
0x14000fe77  push    rdi
0x14000fe78  push    r12
0x14000fe7a  push    r13
0x14000fe7c  push    r14
0x14000fe7e  push    r15
0x14000fe80  lea     rbp, [rsp-7]
0x14000fe85  sub     rsp, 98h
0x14000fe8c  mov     rsi, r9
0x14000fe8f  mov     rbx, r8
0x14000fe92  mov     rdi, rcx
0x14000fe95  mov     [rbp+3Fh+var_68], 0
0x14000fe9d  mov     rcx, [rbp+3Fh+arg_28]
0x14000fea1  test    rcx, rcx
0x14000fea4  jz      short loc_14000FEBE
0x14000fea6  mov     rax, [rcx]
0x14000fea9  lea     rdx, [rbp+3Fh+var_68]
0x14000fead  mov     rax, [rax+18h]
0x14000feb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000feb6  test    eax, eax
0x14000feb8  js      loc_14001059C
0x14000febe  mov     r14d, [rbp+3Fh+arg_20]
0x14000fec2  btr     r14d, 9
0x14000fec7  mov     rax, [rdi+258h]
0x14000fece  test    byte ptr [rax+800h], 9
0x14000fed5  jnz     loc_140010295
0x14000fedb  cmp     dword ptr [rax+7F0h], 0
0x14000fee2  jz      loc_14001028B
0x14000fee8  mov     [rbp+3Fh+var_60], 0
0x14000fef0  mov     [rbp+3Fh+var_70], 5
0x14000fef7  lea     rax, [rbp+3Fh+var_60]
0x14000fefb  mov     qword ptr [rsp+0D0h+SystemTimeAsFileTime.dwLowDateTime], rax; void **
0x14000ff00  lea     r9, IID_IWbemQuery; struct _GUID *
0x14000ff07  lea     r8, [rbp+3Fh+var_70]; unsigned int *
0x14000ff0b  lea     rcx, CLSID_WbemQuery; struct _GUID *
0x14000ff12  call    ?CreateInstance@ProviderSubSystem_Common_Globals@@SAJAEBU_GUID@@PEAUIUnknown@@AEBK0PEAPEAX@Z; ProviderSubSystem_Common_Globals::CreateInstance(_GUID const &,IUnknown *,ulong const &,_GUID const &,void * *)
0x14000ff17  test    eax, eax
0x14000ff19  js      loc_140010281
0x14000ff1f  mov     rcx, [rbp+3Fh+var_60]
0x14000ff23  mov     rax, [rcx]
0x14000ff26  xor     r9d, r9d
0x14000ff29  mov     r8, rsi
0x14000ff2c  mov     rdx, rbx
0x14000ff2f  mov     rax, [rax+30h]
0x14000ff33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ff38  test    eax, eax
0x14000ff3a  js      loc_140010267
0x14000ff40  mov     qword ptr [rbp+3Fh+var_70], 0
0x14000ff48  mov     rcx, [rbp+3Fh+var_60]
0x14000ff4c  mov     rax, [rcx]
0x14000ff4f  lea     r9, [rbp+3Fh+var_70]
0x14000ff53  xor     r8d, r8d
0x14000ff56  lea     edx, [r8+1]
0x14000ff5a  mov     rax, [rax+38h]
0x14000ff5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ff63  test    eax, eax
0x14000ff65  js      loc_140010260
0x14000ff6b  mov     rdx, qword ptr [rbp+3Fh+var_70]
0x14000ff6f  cmp     dword ptr [rdx+30h], 1
0x14000ff73  jnz     loc_140010249
0x14000ff79  mov     rcx, [rdx+48h]
0x14000ff7d  mov     rcx, [rcx]; psz
0x14000ff80  call    cs:__imp_SysAllocString
0x14000ff86  mov     r15, rax
0x14000ff89  test    rax, rax
0x14000ff8c  jz      loc_14001023E
0x14000ff92  lea     rdx, aCreateinstance_0; "CreateInstanceEnumAsync: "
0x14000ff99  lea     rcx, [rbp+3Fh+var_58]; this
0x14000ff9d  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x14000ffa2  nop
0x14000ffa3  mov     rdx, r15; unsigned __int16 *
0x14000ffa6  lea     rcx, [rbp+3Fh+var_50]; this
0x14000ffaa  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x14000ffaf  nop
0x14000ffb0  lea     rdx, [rbp+3Fh+var_50]
0x14000ffb4  lea     rcx, [rbp+3Fh+var_58]
0x14000ffb8  call    ??Y_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator+=(_bstr_t const &)
0x14000ffbd  nop
0x14000ffbe  lea     rcx, [rbp+3Fh+var_50]; this
0x14000ffc2  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x14000ffc7  mov     ecx, 118h; dwBytes
0x14000ffcc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000ffd1  mov     r10, rax
0x14000ffd4  mov     [rbp+3Fh+var_50], rax
0x14000ffd8  mov     r13, [rbp+3Fh+arg_30]
0x14000ffdc  test    rax, rax
0x14000ffdf  jz      short loc_140010037
0x14000ffe1  mov     rcx, [rbp+3Fh+var_58]
0x14000ffe5  test    rcx, rcx
0x14000ffe8  jz      short loc_14000FFEF
0x14000ffea  mov     rdx, [rcx]
0x14000ffed  jmp     short loc_14000FFF1
0x14000ffef  xor     edx, edx
0x14000fff1  lea     r12, [rdi+0E8h]
0x14000fff8  mov     rax, rdi
0x14000fffb  neg     rax
0x14000fffe  sbb     rcx, rcx
0x140010001  and     rcx, r12
0x140010004  mov     [rsp+0D0h+var_88], rdx; unsigned __int16 *
0x140010009  mov     [rsp+0D0h+var_98], rcx; __int64
0x14001000e  mov     [rsp+0D0h+var_A0], rdi; __int64
0x140010013  mov     [rsp+0D0h+var_A8], r13; __int64
0x140010018  mov     qword ptr [rsp+0D0h+SystemTimeAsFileTime.dwLowDateTime], rdi; SystemTimeAsFileTime
0x14001001d  mov     r9, r15; int
0x140010020  mov     r8d, r14d; int
0x140010023  mov     rdx, [rdi+1B0h]; int
0x14001002a  mov     rcx, r10; int
0x14001002d  call    ??0CInterceptor_IWbemSyncObjectSink_CreateInstanceEnumAsync@@QEAA@AEAVWmiAllocator@@JPEAGPEAVCInterceptor_IWbemSyncProvider@@PEAUIWbemObjectSink@@PEAUIUnknown@@PEAV?$WmiContainerController@PEAX@@K1@Z; CInterceptor_IWbemSyncObjectSink_CreateInstanceEnumAsync::CInterceptor_IWbemSyncObjectSink_CreateInstanceEnumAsync(WmiAllocator &,long,ushort *,CInterceptor_IWbemSyncProvider *,IWbemObjectSink *,IUnknown *,WmiContainerController<void *> *,ulong,ushort *)
0x140010032  mov     rsi, rax
0x140010035  jmp     short loc_140010040
0x140010037  xor     esi, esi
0x140010039  lea     r12, [rdi+0E8h]
0x140010040  test    rsi, rsi
0x140010043  jz      loc_140010225
0x140010049  mov     rax, [rsi]
0x14001004c  mov     rcx, rsi
0x14001004f  mov     rax, [rax+8]
0x140010053  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010058  mov     rax, [rsi]
0x14001005b  mov     rcx, rsi
0x14001005e  mov     rax, [rax+50h]
0x140010062  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010067  mov     ebx, eax
0x140010069  test    eax, eax
0x14001006b  js      loc_1400101FC
0x140010071  mov     rax, [r13+0]
0x140010075  xor     ebx, ebx
0x140010077  mov     qword ptr [rsp+0D0h+SystemTimeAsFileTime.dwLowDateTime], rbx
0x14001007c  xor     r9d, r9d
0x14001007f  xor     r8d, r8d
0x140010082  lea     edx, [rbx+1]
0x140010085  mov     rcx, r13
0x140010088  mov     rax, [rax+20h]
0x14001008c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010091  mov     [rbp+3Fh+var_50], rbx
0x140010095  mov     rax, [r12]
0x140010099  mov     rcx, r12
0x14001009c  mov     rax, [rax+30h]
0x1400100a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400100a5  mov     rax, [r12]
0x1400100a9  lea     rdx, [rsi+10h]
0x1400100ad  lea     r8, [rbp+3Fh+var_50]
0x1400100b1  mov     rcx, r12
0x1400100b4  mov     rax, [rax+40h]
0x1400100b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400100bd  mov     rdx, [r12]
0x1400100c1  mov     r8, [rdx+38h]
0x1400100c5  mov     rcx, r12
0x1400100c8  test    eax, eax
0x1400100ca  mov     rax, r8
0x1400100cd  jnz     loc_1400101F2
0x1400100d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400100d8  mov     rax, [rdi+258h]
0x1400100df  mov     ecx, [rax+6CCh]
0x1400100e5  neg     ecx
0x1400100e7  sbb     r14d, r14d
0x1400100ea  and     r14d, 80h
0x1400100f1  add     r14d, 0FFFFFD7Fh
0x1400100f8  cmp     [rbp+3Fh+arg_8], ebx
0x1400100fb  jz      short loc_140010111
0x1400100fd  call    cs:__imp_CoImpersonateClient
0x140010103  test    eax, eax
0x140010105  jns     short loc_140010111
0x140010107  mov     ebx, 80041003h
0x14001010c  jmp     loc_1400101EC
0x140010111  and     r14d, [rbp+3Fh+arg_20]
0x140010115  mov     rax, [r13+0]
0x140010119  mov     qword ptr [rsp+0D0h+SystemTimeAsFileTime.dwLowDateTime], rbx
0x14001011e  xor     r9d, r9d
0x140010121  xor     r8d, r8d
0x140010124  lea     edx, [r9+1]
0x140010128  mov     rcx, r13
0x14001012b  mov     rax, [rax+20h]
0x14001012f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010134  mov     rax, cs:?s_SharedCounters@ProviderSubSystem_Globals@@2PEAVCServerObject_ProviderSubsystem_Counters@@EA; CServerObject_ProviderSubsystem_Counters * ProviderSubSystem_Globals::s_SharedCounters
0x14001013b  test    rax, rax
0x14001013e  jz      short loc_140010147
0x140010140  inc     qword ptr [rax+0B0h]
0x140010147  inc     qword ptr [rdi+2B0h]
0x14001014e  mov     r12, [rbp+3Fh+arg_38]
0x140010155  mov     rax, [r12]
0x140010159  mov     qword ptr [rsp+0D0h+SystemTimeAsFileTime.dwLowDateTime], rsi
0x14001015e  mov     r9, [rbp+3Fh+var_68]
0x140010162  mov     r8d, r14d
0x140010165  mov     rdx, r15
0x140010168  mov     rcx, r12
0x14001016b  mov     rax, [rax+98h]
0x140010172  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010177  mov     ebx, eax
0x140010179  call    cs:__imp_CoRevertToSelf
0x14001017f  cmp     ebx, 80041035h
0x140010185  jz      short loc_14001018F
0x140010187  cmp     ebx, 80041008h
0x14001018d  jnz     short loc_1400101EC
0x14001018f  cmp     [rbp+3Fh+arg_8], 0
0x140010193  jz      short loc_1400101A3
0x140010195  call    cs:__imp_CoImpersonateClient
0x14001019b  test    eax, eax
0x14001019d  js      loc_140010107
0x1400101a3  btr     r14d, 7
0x1400101a8  mov     rax, cs:?s_SharedCounters@ProviderSubSystem_Globals@@2PEAVCServerObject_ProviderSubsystem_Counters@@EA; CServerObject_ProviderSubsystem_Counters * ProviderSubSystem_Globals::s_SharedCounters
0x1400101af  test    rax, rax
0x1400101b2  jz      short loc_1400101BB
0x1400101b4  inc     qword ptr [rax+0B0h]
0x1400101bb  inc     qword ptr [rdi+2B0h]
0x1400101c2  mov     rax, [r12]
0x1400101c6  mov     qword ptr [rsp+0D0h+SystemTimeAsFileTime.dwLowDateTime], rsi
0x1400101cb  mov     r9, [rbp+3Fh+var_68]
0x1400101cf  mov     r8d, r14d
0x1400101d2  mov     rdx, r15
0x1400101d5  mov     rcx, r12
0x1400101d8  mov     rax, [rax+98h]
0x1400101df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400101e4  mov     ebx, eax
0x1400101e6  call    cs:__imp_CoRevertToSelf
0x1400101ec  test    ebx, ebx
0x1400101ee  js      short loc_1400101FC
0x1400101f0  jmp     short loc_140010214
0x1400101f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400101f7  mov     ebx, 80041006h
0x1400101fc  mov     [rsp+0D0h+var_A8], rsi; struct IWbemObjectSink *
0x140010201  mov     [rsp+0D0h+SystemTimeAsFileTime.dwLowDateTime], ebx; int
0x140010205  lea     rdx, aCreateinstance; "CreateInstanceEnumAsync"
0x14001020c  mov     rcx, rdi; this
0x14001020f  call    ?SetStatus@CInterceptor_IWbemSyncProvider@@AEAAJPEAG00JPEAUIWbemObjectSink@@@Z; CInterceptor_IWbemSyncProvider::SetStatus(ushort *,ushort *,ushort *,long,IWbemObjectSink *)
0x140010214  mov     rax, [rsi]
0x140010217  mov     rcx, rsi
0x14001021a  mov     rax, [rax+10h]
0x14001021e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010223  jmp     short loc_140010233
0x140010225  mov     rcx, r15; bstrString
0x140010228  call    cs:__imp_SysFreeString
0x14001022e  mov     ebx, 80041006h
0x140010233  lea     rcx, [rbp+3Fh+var_58]; this
0x140010237  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x14001023c  jmp     short loc_140010243
0x14001023e  mov     ebx, 80041006h
0x140010243  mov     rdx, qword ptr [rbp+3Fh+var_70]
0x140010247  jmp     short loc_14001024E
0x140010249  mov     ebx, 8004100Ch
0x14001024e  mov     rcx, [rbp+3Fh+var_60]
0x140010252  mov     rax, [rcx]
0x140010255  mov     rax, [rax+40h]
0x140010259  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001025e  jmp     short loc_14001026C
0x140010260  mov     ebx, 8004101Dh
0x140010265  jmp     short loc_14001026C
0x140010267  mov     ebx, 8004100Ch
0x14001026c  mov     rcx, [rbp+3Fh+var_60]
0x140010270  mov     rax, [rcx]
0x140010273  mov     rax, [rax+10h]
0x140010277  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001027c  jmp     loc_1400105A1
0x140010281  mov     ebx, 8004100Ah
0x140010286  jmp     loc_1400105A1
0x14001028b  mov     ebx, 8004100Ch
0x140010290  jmp     loc_1400105A1
0x140010295  mov     rcx, rbx; psz
0x140010298  call    cs:__imp_SysAllocString
0x14001029e  mov     rbx, rax
0x1400102a1  mov     [rbp+3Fh+var_60], rax
0x1400102a5  mov     rcx, rsi; psz
0x1400102a8  call    cs:__imp_SysAllocString
0x1400102ae  mov     r13, rax
0x1400102b1  test    rbx, rbx
0x1400102b4  jz      loc_14001059C
0x1400102ba  test    rax, rax
0x1400102bd  jz      loc_14001059C
0x1400102c3  mov     ecx, 18h; dwBytes
0x1400102c8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400102cd  mov     [rbp+3Fh+var_50], rax
0x1400102d1  test    rax, rax
0x1400102d4  jz      short loc_1400102E6
0x1400102d6  lea     rdx, aExecqueryasync; "ExecQueryAsync: "
0x1400102dd  mov     rcx, rax; this
0x1400102e0  call    ??0Data_t@_bstr_t@@QEAA@PEBG@Z; _bstr_t::Data_t::Data_t(ushort const *)
0x1400102e5  nop
0x1400102e6  mov     [rbp+3Fh+var_58], rax
0x1400102ea  test    rax, rax
0x1400102ed  jnz     short loc_1400102FA
0x1400102ef  mov     ecx, 8007000Eh; int
0x1400102f4  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x1400102fa  mov     rdx, r13; unsigned __int16 *
0x1400102fd  lea     rcx, [rbp+3Fh+var_50]; this
0x140010301  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x140010306  nop
0x140010307  lea     rdx, [rbp+3Fh+var_50]
0x14001030b  lea     rcx, [rbp+3Fh+var_58]
0x14001030f  call    ??Y_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator+=(_bstr_t const &)
0x140010314  nop
0x140010315  mov     rcx, [rbp+3Fh+var_50]; this
0x140010319  test    rcx, rcx
0x14001031c  jz      short loc_140010335
0x14001031e  or      eax, 0FFFFFFFFh
0x140010321  lock xadd [rcx+10h], eax
0x140010326  cmp     eax, 1
0x140010329  jnz     short loc_140010335
  ... truncated ...
```
