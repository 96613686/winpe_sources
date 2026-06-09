# CInterceptor_IWbemSyncProvider::Helper_CreateClassEnumAsync(int,ushort * const,long,IWbemContext *,IWbemObjectSink *,IWbemServices *)

- ea: `0x14000f1b8`
- end: `0x14000f5f6`
- name: `?Helper_CreateClassEnumAsync@CInterceptor_IWbemSyncProvider@@AEAAJHQEAGJPEAUIWbemContext@@PEAUIWbemObjectSink@@PEAUIWbemServices@@@Z`
- size: `1086`
- prototype: `__int64 __usercall@<rax>(CInterceptor_IWbemSyncProvider *__hidden this@<rcx>, int@<edx>, unsigned __int16 *const@<r8>, int@<r9d>, struct IWbemContext *, struct IWbemObjectSink *, struct IWbemServices *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14000ed60`

## callees

- `0x14000212c`
- `0x14000a530`
- `0x14000c190`
- `0x14000f1b8`
- `0x14000f600`
- `0x14000fd74`
- `0x1400209a0`
- `0x1400234b8`
- `0x140029d34`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x14000f5b9`
- `wbemcomn!GetMemLogObject` at `0x14000f5b9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14000f5c4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14000f5c4`
- `OLEAUT32!__imp_SysAllocString` at `0x14000f208`
- `OLEAUT32!__imp_SysAllocString` at `0x14000f208`
- `OLEAUT32!__imp_SysFreeString` at `0x14000f49e`
- `OLEAUT32!__imp_SysFreeString` at `0x14000f49e`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x14000f4ae`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x14000f51d`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x14000f4ae`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x14000f51d`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14000f38f`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14000f567`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14000f38f`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14000f567`

## string_xrefs

- `0x14000f4c6`: `CreateClassEnumAsync: `
- `0x14000f585`: `CreateClassEnumAsync`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CInterceptor_IWbemSyncProvider::Helper_CreateClassEnumAsync(
        CInterceptor_IWbemSyncProvider *this,
        int a2,
        unsigned __int16 *const a3,
        int a4,
        struct IWbemContext *a5,
        struct IWbemObjectSink *a6,
        struct IWbemServices *a7)
{
  unsigned __int16 *v10; // r12
  struct IWbemContext *v11; // rax
  struct IErrorInfo *v12; // rdx
  _bstr_t::Data_t *v13; // rax
  struct IErrorInfo *v14; // rdx
  volatile signed __int32 *v15; // rbx
  unsigned int v16; // edx
  LPVOID v17; // r10
  volatile signed __int32 *v18; // rsi
  struct IWbemObjectSink *ClassEnumAsync; // rdi
  char *v20; // r14
  int v21; // ebx
  bool v22; // zf
  void (__fastcall *v23)(char *); // rax
  int v24; // r14d
  unsigned int v25; // r14d
  struct IWbemServices *v26; // r13
  struct IWbemClassObject *v27; // r8
  unsigned __int16 *v28; // r9
  unsigned int v29; // edx
  __int64 result; // rax
  unsigned __int16 *lpVtbl; // rdx
  unsigned int v32; // r14d
  CMemoryLog *MemLogObject; // rax
  int v34; // [rsp+40h] [rbp-20h]
  __int64 v35; // [rsp+50h] [rbp-10h] BYREF
  LPVOID v36; // [rsp+58h] [rbp-8h] BYREF

  v35 = 0;
  if ( a5 && ((int (__fastcall *)(struct IWbemContext *, __int64 *))a5->lpVtbl->Clone)(a5, &v35) < 0
    || (v10 = SysAllocString(a3)) == 0 )
  {
    v21 = -2147217402;
    goto LABEL_27;
  }
  v11 = (struct IWbemContext *)operator new(0x18u);
  a5 = v11;
  if ( v11 )
    v11 = (struct IWbemContext *)_bstr_t::Data_t::Data_t((_bstr_t::Data_t *)v11, L"CreateClassEnumAsync: ");
  a5 = v11;
  if ( !v11 )
    _com_issue_error(-2147024882, v12);
  v13 = (_bstr_t::Data_t *)operator new(0x18u);
  v36 = v13;
  if ( v13 )
    v15 = (volatile signed __int32 *)_bstr_t::Data_t::Data_t(v13, v10);
  else
    v15 = 0;
  v36 = (LPVOID)v15;
  if ( !v15 )
    _com_issue_error(-2147024882, v14);
  _bstr_t::operator+=(&a5, &v36);
  if ( _InterlockedExchangeAdd(v15 + 4, 0xFFFFFFFF) == 1 )
    _bstr_t::Data_t::`scalar deleting destructor'((_bstr_t::Data_t *)v15, v16);
  v17 = operator new(0x118u);
  v36 = v17;
  v18 = (volatile signed __int32 *)a5;
  if ( v17 )
  {
    if ( a5 )
      lpVtbl = (unsigned __int16 *)a5->lpVtbl;
    else
      lpVtbl = 0;
    v20 = (char *)this + 232;
    ClassEnumAsync = (struct IWbemObjectSink *)CInterceptor_IWbemSyncObjectSink_CreateClassEnumAsync::CInterceptor_IWbemSyncObjectSink_CreateClassEnumAsync(
                                                 (__int64)v17,
                                                 *((_QWORD *)this + 54),
                                                 a4 & 0xFFFFFDFF,
                                                 (__int64)v10,
                                                 (int)this,
                                                 (int)a6,
                                                 (__int64)this,
                                                 ((unsigned __int64)this + 232) & -(__int64)(this != 0),
                                                 v34,
                                                 lpVtbl);
  }
  else
  {
    ClassEnumAsync = 0;
    v20 = (char *)this + 232;
  }
  if ( !ClassEnumAsync )
  {
    SysFreeString(v10);
    v21 = -2147217402;
    goto LABEL_24;
  }
  ((void (__fastcall *)(struct IWbemObjectSink *))ClassEnumAsync->lpVtbl->AddRef)(ClassEnumAsync);
  v21 = ((__int64 (__fastcall *)(struct IWbemObjectSink *))ClassEnumAsync->lpVtbl[2].QueryInterface)(ClassEnumAsync);
  if ( v21 >= 0 )
  {
    v36 = 0;
    (*(void (__fastcall **)(char *))(*(_QWORD *)v20 + 48LL))(v20);
    v22 = (*(unsigned int (__fastcall **)(char *, struct IWbemObjectSink *, LPVOID *))(*(_QWORD *)v20 + 64LL))(
            v20,
            ClassEnumAsync + 2,
            &v36) == 0;
    v23 = *(void (__fastcall **)(char *))(*(_QWORD *)v20 + 56LL);
    if ( !v22 )
    {
      v23(v20);
      v21 = -2147217402;
      goto LABEL_52;
    }
    v23(v20);
    v24 = *(_DWORD *)(*((_QWORD *)this + 75) + 1740LL) != 0 ? -513 : -641;
    if ( a2 && CoImpersonateClient() < 0 )
      goto LABEL_41;
    v25 = a4 & v24;
    if ( ProviderSubSystem_Globals::s_SharedCounters )
      ++*((_QWORD *)ProviderSubSystem_Globals::s_SharedCounters + 19);
    ++*((_QWORD *)this + 83);
    v26 = a7;
    v21 = ((__int64 (__fastcall *)(struct IWbemServices *, unsigned __int16 *, _QWORD, __int64, struct IWbemObjectSink *))a7->lpVtbl->CreateClassEnumAsync)(
            a7,
            v10,
            v25,
            v35,
            ClassEnumAsync);
    CoRevertToSelf();
    if ( v21 == -2147217355 || v21 == -2147217400 )
    {
      if ( a2 && CoImpersonateClient() < 0 )
      {
LABEL_41:
        v21 = -2147217405;
        goto LABEL_22;
      }
      v32 = v25 & 0xFFFFFF7F;
      if ( ProviderSubSystem_Globals::s_SharedCounters )
        ++*((_QWORD *)ProviderSubSystem_Globals::s_SharedCounters + 19);
      ++*((_QWORD *)this + 83);
      v21 = ((__int64 (__fastcall *)(struct IWbemServices *, unsigned __int16 *, _QWORD, __int64, struct IWbemObjectSink *))v26->lpVtbl->CreateClassEnumAsync)(
              v26,
              v10,
              v32,
              v35,
              ClassEnumAsync);
      CoRevertToSelf();
    }
LABEL_22:
    if ( v21 >= 0 )
      goto LABEL_23;
LABEL_52:
    CInterceptor_IWbemSyncProvider::SetStatus(this, L"CreateClassEnumAsync", v27, v28, v21, ClassEnumAsync);
  }
LABEL_23:
  ((void (__fastcall *)(struct IWbemObjectSink *))ClassEnumAsync->lpVtbl->Release)(ClassEnumAsync);
LABEL_24:
  if ( v18 && _InterlockedExchangeAdd(v18 + 4, 0xFFFFFFFF) == 1 )
    _bstr_t::Data_t::`scalar deleting destructor'((_bstr_t::Data_t *)v18, v29);
LABEL_27:
  if ( v35 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
  result = 2147749890LL;
  if ( v21 != -2147217406 )
  {
    if ( v21 < 0 )
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, v21);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        98,
        WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids,
        (unsigned int)v21);
    }
    return (unsigned int)v21;
  }
  return result;
}

```

## disassembly

```asm
0x14000f1b8  mov     [rsp-38h+arg_0], rbx
0x14000f1bd  mov     [rsp-38h+arg_8], edx
0x14000f1c1  push    rbp
0x14000f1c2  push    rsi
0x14000f1c3  push    rdi
0x14000f1c4  push    r12
0x14000f1c6  push    r13
0x14000f1c8  push    r14
0x14000f1ca  push    r15
0x14000f1cc  mov     rbp, rsp
0x14000f1cf  sub     rsp, 60h
0x14000f1d3  mov     r13d, r9d
0x14000f1d6  mov     rbx, r8
0x14000f1d9  mov     r15, rcx
0x14000f1dc  mov     [rbp+var_10], 0
0x14000f1e4  mov     rcx, [rbp+arg_20]
0x14000f1e8  test    rcx, rcx
0x14000f1eb  jz      short loc_14000F205
0x14000f1ed  mov     rax, [rcx]
0x14000f1f0  lea     rdx, [rbp+var_10]
0x14000f1f4  mov     rax, [rax+18h]
0x14000f1f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f1fd  test    eax, eax
0x14000f1ff  js      loc_14000F5AF
0x14000f205  mov     rcx, rbx; psz
0x14000f208  call    cs:__imp_SysAllocString
0x14000f20e  mov     r12, rax
0x14000f211  test    rax, rax
0x14000f214  jz      loc_14000F5AF
0x14000f21a  mov     ebx, 18h
0x14000f21f  mov     ecx, ebx; dwBytes
0x14000f221  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000f226  mov     [rbp+arg_20], rax
0x14000f22a  test    rax, rax
0x14000f22d  jnz     loc_14000F4C6
0x14000f233  mov     [rbp+arg_20], rax
0x14000f237  test    rax, rax
0x14000f23a  jz      loc_14000F4DA
0x14000f240  mov     rcx, rbx; dwBytes
0x14000f243  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000f248  mov     [rbp+var_8], rax
0x14000f24c  test    rax, rax
0x14000f24f  jnz     loc_14000F4E5
0x14000f255  xor     ebx, ebx
0x14000f257  mov     [rbp+var_8], rbx
0x14000f25b  test    rbx, rbx
0x14000f25e  jz      loc_14000F4F8
0x14000f264  lea     rdx, [rbp+var_8]
0x14000f268  lea     rcx, [rbp+arg_20]
0x14000f26c  call    ??Y_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator+=(_bstr_t const &)
0x14000f271  nop
0x14000f272  or      eax, 0FFFFFFFFh
0x14000f275  lock xadd [rbx+10h], eax
0x14000f27a  cmp     eax, 1
0x14000f27d  jz      loc_14000F503
0x14000f283  mov     ecx, 118h; dwBytes
0x14000f288  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000f28d  mov     r10, rax
0x14000f290  mov     [rbp+var_8], rax
0x14000f294  mov     rsi, [rbp+arg_20]
0x14000f298  test    rax, rax
0x14000f29b  jnz     loc_14000F411
0x14000f2a1  xor     edi, edi
0x14000f2a3  lea     r14, [r15+0E8h]
0x14000f2aa  test    rdi, rdi
0x14000f2ad  jz      loc_14000F49B
0x14000f2b3  mov     rax, [rdi]
0x14000f2b6  mov     rcx, rdi
0x14000f2b9  mov     rax, [rax+8]
0x14000f2bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f2c2  mov     rax, [rdi]
0x14000f2c5  mov     rcx, rdi
0x14000f2c8  mov     rax, [rax+50h]
0x14000f2cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f2d1  mov     ebx, eax
0x14000f2d3  test    eax, eax
0x14000f2d5  js      loc_14000F3B5
0x14000f2db  mov     [rbp+var_8], 0
0x14000f2e3  mov     rax, [r14]
0x14000f2e6  mov     rcx, r14
0x14000f2e9  mov     rax, [rax+30h]
0x14000f2ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f2f2  mov     rax, [r14]
0x14000f2f5  lea     rdx, [rdi+10h]
0x14000f2f9  lea     r8, [rbp+var_8]
0x14000f2fd  mov     rcx, r14
0x14000f300  mov     rax, [rax+40h]
0x14000f304  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f309  mov     rdx, [r14]
0x14000f30c  mov     r8, [rdx+38h]
0x14000f310  mov     rcx, r14
0x14000f313  test    eax, eax
0x14000f315  mov     rax, r8
0x14000f318  jnz     loc_14000F572
0x14000f31e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f323  mov     rax, [r15+258h]
0x14000f32a  mov     ecx, [rax+6CCh]
0x14000f330  neg     ecx
0x14000f332  sbb     r14d, r14d
0x14000f335  and     r14d, 80h
0x14000f33c  add     r14d, 0FFFFFD7Fh
0x14000f343  cmp     [rbp+arg_8], 0
0x14000f347  jnz     loc_14000F4AE
0x14000f34d  and     r14d, r13d
0x14000f350  mov     rax, cs:?s_SharedCounters@ProviderSubSystem_Globals@@2PEAVCServerObject_ProviderSubsystem_Counters@@EA; CServerObject_ProviderSubsystem_Counters * ProviderSubSystem_Globals::s_SharedCounters
0x14000f357  test    rax, rax
0x14000f35a  jz      short loc_14000F363
0x14000f35c  inc     qword ptr [rax+98h]
0x14000f363  inc     qword ptr [r15+298h]
0x14000f36a  mov     r13, [rbp+arg_30]
0x14000f36e  mov     rax, [r13+0]
0x14000f372  mov     qword ptr [rsp+60h+var_40], rdi
0x14000f377  mov     r9, [rbp+var_10]
0x14000f37b  mov     r8d, r14d
0x14000f37e  mov     rdx, r12
0x14000f381  mov     rcx, r13
0x14000f384  mov     rax, [rax+68h]
0x14000f388  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f38d  mov     ebx, eax
0x14000f38f  call    cs:__imp_CoRevertToSelf
0x14000f395  cmp     ebx, 80041035h
0x14000f39b  jz      loc_14000F517
0x14000f3a1  cmp     ebx, 80041008h
0x14000f3a7  jz      loc_14000F517
0x14000f3ad  test    ebx, ebx
0x14000f3af  js      loc_14000F57C
0x14000f3b5  mov     rax, [rdi]
0x14000f3b8  mov     rcx, rdi
0x14000f3bb  mov     rax, [rax+10h]
0x14000f3bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f3c4  nop
0x14000f3c5  test    rsi, rsi
0x14000f3c8  jz      short loc_14000F3DB
0x14000f3ca  or      eax, 0FFFFFFFFh
0x14000f3cd  lock xadd [rsi+10h], eax
0x14000f3d2  cmp     eax, 1
0x14000f3d5  jz      loc_14000F599
0x14000f3db  mov     rcx, [rbp+var_10]
0x14000f3df  test    rcx, rcx
0x14000f3e2  jz      short loc_14000F3F0
0x14000f3e4  mov     rax, [rcx]
0x14000f3e7  mov     rax, [rax+10h]
0x14000f3eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f3f0  mov     eax, 80041002h
0x14000f3f5  cmp     ebx, eax
0x14000f3f7  jnz     short loc_14000F46F
0x14000f3f9  mov     rbx, [rsp+60h+arg_0]
0x14000f401  add     rsp, 60h
0x14000f405  pop     r15
0x14000f407  pop     r14
0x14000f409  pop     r13
0x14000f40b  pop     r12
0x14000f40d  pop     rdi
0x14000f40e  pop     rsi
0x14000f40f  pop     rbp
0x14000f410  retn
0x14000f411  mov     r8d, r13d
0x14000f414  btr     r8d, 9
0x14000f419  test    rsi, rsi
0x14000f41c  jz      loc_14000F510
0x14000f422  mov     rdx, [rsi]
0x14000f425  lea     r14, [r15+0E8h]
0x14000f42c  mov     rax, r15
0x14000f42f  neg     rax
0x14000f432  sbb     rcx, rcx
0x14000f435  and     rcx, r14
0x14000f438  mov     [rsp+60h+var_18], rdx
0x14000f43d  mov     [rsp+60h+var_28], rcx
0x14000f442  mov     [rsp+60h+var_30], r15
0x14000f447  mov     rax, [rbp+arg_28]
0x14000f44b  mov     [rsp+60h+var_38], rax
0x14000f450  mov     qword ptr [rsp+60h+var_40], r15
0x14000f455  mov     r9, r12
0x14000f458  mov     rdx, [r15+1B0h]
0x14000f45f  mov     rcx, r10
0x14000f462  call    ??0CInterceptor_IWbemSyncObjectSink_CreateClassEnumAsync@@QEAA@AEAVWmiAllocator@@JPEAGPEAVCInterceptor_IWbemSyncProvider@@PEAUIWbemObjectSink@@PEAUIUnknown@@PEAV?$WmiContainerController@PEAX@@K1@Z; CInterceptor_IWbemSyncObjectSink_CreateClassEnumAsync::CInterceptor_IWbemSyncObjectSink_CreateClassEnumAsync(WmiAllocator &,long,ushort *,CInterceptor_IWbemSyncProvider *,IWbemObjectSink *,IUnknown *,WmiContainerController<void *> *,ulong,ushort *)
0x14000f467  mov     rdi, rax
0x14000f46a  jmp     loc_14000F2AA
0x14000f46f  test    ebx, ebx
0x14000f471  js      loc_14000F5B9
0x14000f477  lea     rax, WPP_GLOBAL_Control
0x14000f47e  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f485  cmp     rcx, rax
0x14000f488  jz      short loc_14000F494
0x14000f48a  test    byte ptr [rcx+1Ch], 4
0x14000f48e  jnz     loc_14000F5CF
0x14000f494  mov     eax, ebx
0x14000f496  jmp     loc_14000F3F9
0x14000f49b  mov     rcx, r12; bstrString
0x14000f49e  call    cs:__imp_SysFreeString
0x14000f4a4  mov     ebx, 80041006h
0x14000f4a9  jmp     loc_14000F3C5
0x14000f4ae  call    cs:__imp_CoImpersonateClient
0x14000f4b4  test    eax, eax
0x14000f4b6  jns     loc_14000F34D
0x14000f4bc  mov     ebx, 80041003h
0x14000f4c1  jmp     loc_14000F3AD
0x14000f4c6  lea     rdx, aCreateclassenu_0; "CreateClassEnumAsync: "
0x14000f4cd  mov     rcx, rax; this
0x14000f4d0  call    ??0Data_t@_bstr_t@@QEAA@PEBG@Z; _bstr_t::Data_t::Data_t(ushort const *)
0x14000f4d5  jmp     loc_14000F233
0x14000f4da  mov     ecx, 8007000Eh; int
0x14000f4df  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x14000f4e5  mov     rdx, r12; unsigned __int16 *
0x14000f4e8  mov     rcx, rax; this
0x14000f4eb  call    ??0Data_t@_bstr_t@@QEAA@PEBG@Z; _bstr_t::Data_t::Data_t(ushort const *)
0x14000f4f0  mov     rbx, rax
0x14000f4f3  jmp     loc_14000F257
0x14000f4f8  mov     ecx, 8007000Eh; int
0x14000f4fd  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x14000f503  mov     rcx, rbx; this
0x14000f506  call    ??_GData_t@_bstr_t@@AEAAPEAXI@Z; _bstr_t::Data_t::`scalar deleting destructor'(uint)
0x14000f50b  jmp     loc_14000F283
0x14000f510  xor     edx, edx
0x14000f512  jmp     loc_14000F425
0x14000f517  cmp     [rbp+arg_8], 0
0x14000f51b  jz      short loc_14000F527
0x14000f51d  call    cs:__imp_CoImpersonateClient
0x14000f523  test    eax, eax
0x14000f525  js      short loc_14000F4BC
0x14000f527  btr     r14d, 7
0x14000f52c  mov     rax, cs:?s_SharedCounters@ProviderSubSystem_Globals@@2PEAVCServerObject_ProviderSubsystem_Counters@@EA; CServerObject_ProviderSubsystem_Counters * ProviderSubSystem_Globals::s_SharedCounters
0x14000f533  test    rax, rax
0x14000f536  jz      short loc_14000F53F
0x14000f538  inc     qword ptr [rax+98h]
0x14000f53f  inc     qword ptr [r15+298h]
0x14000f546  mov     rax, [r13+0]
0x14000f54a  mov     qword ptr [rsp+60h+var_40], rdi
0x14000f54f  mov     r9, [rbp+var_10]
0x14000f553  mov     r8d, r14d
0x14000f556  mov     rdx, r12
0x14000f559  mov     rcx, r13
0x14000f55c  mov     rax, [rax+68h]
0x14000f560  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f565  mov     ebx, eax
0x14000f567  call    cs:__imp_CoRevertToSelf
0x14000f56d  jmp     loc_14000F3AD
0x14000f572  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f577  mov     ebx, 80041006h
0x14000f57c  mov     [rsp+60h+var_38], rdi; struct IWbemObjectSink *
0x14000f581  mov     [rsp+60h+var_40], ebx; int
0x14000f585  lea     rdx, aCreateclassenu; "CreateClassEnumAsync"
0x14000f58c  mov     rcx, r15; this
0x14000f58f  call    ?SetStatus@CInterceptor_IWbemSyncProvider@@AEAAJPEAG00JPEAUIWbemObjectSink@@@Z; CInterceptor_IWbemSyncProvider::SetStatus(ushort *,ushort *,ushort *,long,IWbemObjectSink *)
0x14000f594  jmp     loc_14000F3B5
0x14000f599  test    rsi, rsi
0x14000f59c  jz      loc_14000F3DB
0x14000f5a2  mov     rcx, rsi; this
0x14000f5a5  call    ??_GData_t@_bstr_t@@AEAAPEAXI@Z; _bstr_t::Data_t::`scalar deleting destructor'(uint)
0x14000f5aa  jmp     loc_14000F3DB
0x14000f5af  mov     ebx, 80041006h
0x14000f5b4  jmp     loc_14000F3DB
0x14000f5b9  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x14000f5bf  mov     edx, ebx
0x14000f5c1  mov     rcx, rax
0x14000f5c4  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x14000f5ca  jmp     loc_14000F477
0x14000f5cf  cmp     byte ptr [rcx+19h], 2
0x14000f5d3  jb      loc_14000F494
0x14000f5d9  mov     edx, 62h ; 'b'
0x14000f5de  mov     r9d, ebx
0x14000f5e1  lea     r8, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids
0x14000f5e8  mov     rcx, [rcx+10h]
0x14000f5ec  call    WPP_SF_d
0x14000f5f1  jmp     loc_14000F494
```
