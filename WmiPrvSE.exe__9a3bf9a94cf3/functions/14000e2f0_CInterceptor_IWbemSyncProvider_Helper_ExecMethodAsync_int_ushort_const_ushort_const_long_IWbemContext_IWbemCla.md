# CInterceptor_IWbemSyncProvider::Helper_ExecMethodAsync(int,ushort * const,ushort * const,long,IWbemContext *,IWbemClassObject *,IWbemObjectSink *,IWbemServices *)

- ea: `0x14000e2f0`
- end: `0x14000e72f`
- name: `?Helper_ExecMethodAsync@CInterceptor_IWbemSyncProvider@@AEAAJHQEAG0JPEAUIWbemContext@@PEAUIWbemClassObject@@PEAUIWbemObjectSink@@PEAUIWbemServices@@@Z`
- size: `1087`
- prototype: `__int64 __fastcall(CInterceptor_IWbemSyncProvider *this, int, unsigned __int16 *const, unsigned __int16 *const, int, struct IWbemContext *, struct IWbemClassObject *, struct IWbemObjectSink *, struct IWbemServices *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14000de90`

## callees

- `0x14000a530`
- `0x14000c190`
- `0x14000e2f0`
- `0x14000e8a0`
- `0x14000f600`
- `0x14001b3d0`
- `0x1400234b8`
- `0x14002a55c`
- `0x14003c7ec`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x14000e6d4`
- `wbemcomn!GetMemLogObject` at `0x14000e6d4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14000e6df`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14000e6df`
- `OLEAUT32!__imp_SysAllocString` at `0x14000e34a`
- `OLEAUT32!__imp_SysAllocString` at `0x14000e356`
- `OLEAUT32!__imp_SysAllocString` at `0x14000e34a`
- `OLEAUT32!__imp_SysAllocString` at `0x14000e356`
- `OLEAUT32!__imp_SysFreeString` at `0x14000e697`
- `OLEAUT32!__imp_SysFreeString` at `0x14000e6a0`
- `OLEAUT32!__imp_SysFreeString` at `0x14000e697`
- `OLEAUT32!__imp_SysFreeString` at `0x14000e6a0`
- `OLEAUT32!__imp_SysStringLen` at `0x14000e385`
- `OLEAUT32!__imp_SysStringLen` at `0x14000e385`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x14000e569`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x14000e5f3`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x14000e569`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x14000e5f3`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14000e5d7`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14000e655`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14000e5d7`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14000e655`

## string_xrefs

- `0x14000e371`: `ExecMethodAsync: ObjectPath (`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CInterceptor_IWbemSyncProvider::Helper_ExecMethodAsync(
        CInterceptor_IWbemSyncProvider *this,
        int a2,
        unsigned __int16 *const a3,
        unsigned __int16 *const a4,
        int a5,
        struct IWbemContext *a6,
        struct IWbemClassObject *a7,
        struct IWbemObjectSink *a8,
        struct IWbemServices *a9)
{
  int v13; // ebx
  CInterceptor_IWbemSyncProvider *v14; // rcx
  OLECHAR *v15; // r12
  BSTR v16; // rax
  OLECHAR *v17; // r15
  UINT v18; // eax
  const unsigned __int16 *v19; // rdx
  const unsigned __int16 *v20; // rdx
  struct IWbemClassObject *v21; // rbx
  void *v22; // r10
  char *v23; // r14
  struct IWbemObjectSink *v24; // rdi
  int v25; // ebx
  bool v26; // zf
  void (__fastcall *v27)(char *); // rax
  int v28; // r14d
  unsigned __int16 *v29; // r8
  unsigned __int16 *v30; // r9
  unsigned int v31; // r14d
  struct IWbemServices *v32; // r13
  unsigned int v33; // r14d
  CMemoryLog *MemLogObject; // rax
  struct IWbemContext *v36; // [rsp+60h] [rbp-18h] BYREF
  _QWORD v37[2]; // [rsp+68h] [rbp-10h] BYREF

  v36 = 0;
  if ( !a6
    || (v13 = ((__int64 (__fastcall *)(struct IWbemContext *, struct IWbemContext **))a6->lpVtbl->Clone)(a6, &v36),
        CInterceptor_IWbemSyncProvider::AdjustGetContext(v14, v36),
        v13 >= 0) )
  {
    v15 = SysAllocString(a3);
    v16 = SysAllocString(a4);
    v17 = v16;
    if ( v15 )
    {
      if ( v16 )
      {
        _bstr_t::_bstr_t((_bstr_t *)&a6, L"ExecMethodAsync: ObjectPath (");
        v18 = SysStringLen(a3);
        v19 = L"NULL";
        if ( v18 )
          v19 = a3;
        _bstr_t::_bstr_t((_bstr_t *)v37, v19);
        _bstr_t::operator+=(&a6, v37);
        _bstr_t::~_bstr_t((_bstr_t *)v37);
        _bstr_t::_bstr_t((_bstr_t *)v37, L")::");
        _bstr_t::operator+=(&a6, v37);
        _bstr_t::~_bstr_t((_bstr_t *)v37);
        _bstr_t::_bstr_t((_bstr_t *)v37, a4);
        _bstr_t::operator+=(&a6, v37);
        _bstr_t::~_bstr_t((_bstr_t *)v37);
        v20 = L"(...)";
        v21 = a7;
        if ( !a7 )
          v20 = L"( )";
        _bstr_t::_bstr_t((_bstr_t *)v37, v20);
        _bstr_t::operator+=(&a6, v37);
        _bstr_t::~_bstr_t((_bstr_t *)v37);
        v22 = operator new(0x128u);
        v37[0] = v22;
        if ( v22 )
        {
          v23 = (char *)this + 232;
          v24 = (struct IWbemObjectSink *)CInterceptor_IWbemSyncObjectSink_ExecMethodAsync::CInterceptor_IWbemSyncObjectSink_ExecMethodAsync(
                                            (_DWORD)v22,
                                            *((_QWORD *)this + 54),
                                            a5 & 0xFFFFFDFF,
                                            (_DWORD)v15,
                                            (__int64)v17,
                                            (__int64)v21,
                                            (_DWORD)this,
                                            (_DWORD)a8,
                                            (__int64)this,
                                            ((unsigned __int64)this + 232) & -(__int64)(this != 0));
        }
        else
        {
          v24 = 0;
          v23 = (char *)this + 232;
        }
        if ( !v24 )
        {
          SysFreeString(v15);
          SysFreeString(v17);
          v25 = -2147217402;
          goto LABEL_33;
        }
        ((void (__fastcall *)(struct IWbemObjectSink *))v24->lpVtbl->AddRef)(v24);
        v25 = ((__int64 (__fastcall *)(struct IWbemObjectSink *))v24->lpVtbl[2].QueryInterface)(v24);
        if ( v25 < 0 )
        {
LABEL_31:
          ((void (__fastcall *)(struct IWbemObjectSink *))v24->lpVtbl->Release)(v24);
LABEL_33:
          _bstr_t::~_bstr_t((_bstr_t *)&a6);
          goto LABEL_35;
        }
        v37[0] = 0;
        (*(void (__fastcall **)(char *))(*(_QWORD *)v23 + 48LL))(v23);
        v26 = (*(unsigned int (__fastcall **)(char *, struct IWbemObjectSink *, _QWORD *))(*(_QWORD *)v23 + 64LL))(
                v23,
                v24 + 2,
                v37) == 0;
        v27 = *(void (__fastcall **)(char *))(*(_QWORD *)v23 + 56LL);
        if ( !v26 )
        {
          v27(v23);
          v25 = -2147217402;
LABEL_30:
          CInterceptor_IWbemSyncProvider::SetStatus(this, L"ExecMethodAsync", v29, v30, v25, v24);
          goto LABEL_31;
        }
        v27(v23);
        v28 = *(_DWORD *)(*((_QWORD *)this + 75) + 1740LL) != 0 ? -513 : -641;
        if ( a2 && CoImpersonateClient() < 0 )
          goto LABEL_17;
        v31 = a5 & v28;
        if ( ProviderSubSystem_Globals::s_SharedCounters )
          ++*((_QWORD *)ProviderSubSystem_Globals::s_SharedCounters + 25);
        ++*((_QWORD *)this + 89);
        v32 = a9;
        v25 = ((__int64 (__fastcall *)(struct IWbemServices *, OLECHAR *, OLECHAR *, _QWORD, struct IWbemContext *, struct IWbemClassObject *, struct IWbemObjectSink *))a9->lpVtbl->ExecMethodAsync)(
                a9,
                v15,
                v17,
                v31,
                v36,
                a7,
                v24);
        CoRevertToSelf();
        if ( v25 == -2147217355 || v25 == -2147217400 )
        {
          if ( a2 && CoImpersonateClient() < 0 )
          {
LABEL_17:
            v25 = -2147217405;
            goto LABEL_27;
          }
          v33 = v31 & 0xFFFFFF7F;
          if ( ProviderSubSystem_Globals::s_SharedCounters )
            ++*((_QWORD *)ProviderSubSystem_Globals::s_SharedCounters + 25);
          ++*((_QWORD *)this + 89);
          v25 = ((__int64 (__fastcall *)(struct IWbemServices *, OLECHAR *, OLECHAR *, _QWORD, struct IWbemContext *, struct IWbemClassObject *, struct IWbemObjectSink *))v32->lpVtbl->ExecMethodAsync)(
                  v32,
                  v15,
                  v17,
                  v33,
                  v36,
                  a7,
                  v24);
          CoRevertToSelf();
        }
LABEL_27:
        if ( v25 >= 0 )
          goto LABEL_31;
        goto LABEL_30;
      }
    }
  }
  v25 = -2147217402;
LABEL_35:
  if ( v36 )
    ((void (__fastcall *)(struct IWbemContext *))v36->lpVtbl->Release)(v36);
  if ( v25 < 0 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v25);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      125,
      WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids,
      (unsigned int)v25);
  }
  return (unsigned int)v25;
}

```

## disassembly

```asm
0x14000e2f0  mov     [rsp-40h+arg_8], edx
0x14000e2f4  push    rbp
0x14000e2f5  push    rbx
0x14000e2f6  push    rsi
0x14000e2f7  push    rdi
0x14000e2f8  push    r12
0x14000e2fa  push    r13
0x14000e2fc  push    r14
0x14000e2fe  push    r15
0x14000e300  mov     rbp, rsp
0x14000e303  sub     rsp, 78h
0x14000e307  mov     r14, r9
0x14000e30a  mov     rdi, r8
0x14000e30d  mov     r13d, edx
0x14000e310  mov     rsi, rcx
0x14000e313  mov     [rbp+var_18], 0
0x14000e31b  mov     rcx, [rbp+arg_28]
0x14000e31f  test    rcx, rcx
0x14000e322  jz      short loc_14000E347
0x14000e324  mov     rax, [rcx]
0x14000e327  lea     rdx, [rbp+var_18]
0x14000e32b  mov     rax, [rax+18h]
0x14000e32f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e334  mov     ebx, eax
0x14000e336  mov     rdx, [rbp+var_18]; struct IWbemContext *
0x14000e33a  call    ?AdjustGetContext@CInterceptor_IWbemSyncProvider@@AEAAJPEAUIWbemContext@@@Z; CInterceptor_IWbemSyncProvider::AdjustGetContext(IWbemContext *)
0x14000e33f  test    ebx, ebx
0x14000e341  js      loc_14000E6B6
0x14000e347  mov     rcx, rdi; psz
0x14000e34a  call    cs:__imp_SysAllocString
0x14000e350  mov     r12, rax
0x14000e353  mov     rcx, r14; psz
0x14000e356  call    cs:__imp_SysAllocString
0x14000e35c  mov     r15, rax
0x14000e35f  test    r12, r12
0x14000e362  jz      loc_14000E6B6
0x14000e368  test    rax, rax
0x14000e36b  jz      loc_14000E6B6
0x14000e371  lea     rdx, aExecmethodasyn; "ExecMethodAsync: ObjectPath ("
0x14000e378  lea     rcx, [rbp+arg_28]; this
0x14000e37c  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x14000e381  nop
0x14000e382  mov     rcx, rdi; pbstr
0x14000e385  call    cs:__imp_SysStringLen
0x14000e38b  lea     rdx, aNull_0; "NULL"
0x14000e392  test    eax, eax
0x14000e394  cmovnz  rdx, rdi; unsigned __int16 *
0x14000e398  lea     rcx, [rbp+var_10]; this
0x14000e39c  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x14000e3a1  nop
0x14000e3a2  lea     rdx, [rbp+var_10]
0x14000e3a6  lea     rcx, [rbp+arg_28]
0x14000e3aa  call    ??Y_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator+=(_bstr_t const &)
0x14000e3af  nop
0x14000e3b0  lea     rcx, [rbp+var_10]; this
0x14000e3b4  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x14000e3b9  lea     rdx, asc_140052E18; ")::"
0x14000e3c0  lea     rcx, [rbp+var_10]; this
0x14000e3c4  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x14000e3c9  nop
0x14000e3ca  lea     rdx, [rbp+var_10]
0x14000e3ce  lea     rcx, [rbp+arg_28]
0x14000e3d2  call    ??Y_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator+=(_bstr_t const &)
0x14000e3d7  nop
0x14000e3d8  lea     rcx, [rbp+var_10]; this
0x14000e3dc  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x14000e3e1  mov     rdx, r14; unsigned __int16 *
0x14000e3e4  lea     rcx, [rbp+var_10]; this
0x14000e3e8  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x14000e3ed  nop
0x14000e3ee  lea     rdx, [rbp+var_10]
0x14000e3f2  lea     rcx, [rbp+arg_28]
0x14000e3f6  call    ??Y_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator+=(_bstr_t const &)
0x14000e3fb  nop
0x14000e3fc  lea     rcx, [rbp+var_10]; this
0x14000e400  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x14000e405  lea     rax, asc_140052E30; "( )"
0x14000e40c  lea     rdx, asc_140052E20; "(...)"
0x14000e413  mov     rbx, [rbp+arg_30]
0x14000e417  test    rbx, rbx
0x14000e41a  cmovz   rdx, rax; unsigned __int16 *
0x14000e41e  lea     rcx, [rbp+var_10]; this
0x14000e422  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x14000e427  nop
0x14000e428  lea     rdx, [rbp+var_10]
0x14000e42c  lea     rcx, [rbp+arg_28]
0x14000e430  call    ??Y_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator+=(_bstr_t const &)
0x14000e435  nop
0x14000e436  lea     rcx, [rbp+var_10]; this
0x14000e43a  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x14000e43f  mov     ecx, 128h; dwBytes
0x14000e444  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000e449  mov     r10, rax
0x14000e44c  mov     [rbp+var_10], rax
0x14000e450  test    rax, rax
0x14000e453  jz      short loc_14000E4C2
0x14000e455  mov     r8d, [rbp+arg_20]
0x14000e459  btr     r8d, 9
0x14000e45e  mov     rcx, [rbp+arg_28]
0x14000e462  test    rcx, rcx
0x14000e465  jz      short loc_14000E46C
0x14000e467  mov     rdx, [rcx]
0x14000e46a  jmp     short loc_14000E46E
0x14000e46c  xor     edx, edx
0x14000e46e  lea     r14, [rsi+0E8h]
0x14000e475  mov     rax, rsi
0x14000e478  neg     rax
0x14000e47b  sbb     rcx, rcx
0x14000e47e  and     rcx, r14
0x14000e481  mov     [rsp+78h+var_20], rdx
0x14000e486  mov     [rsp+78h+var_30], rcx
0x14000e48b  mov     [rsp+78h+var_38], rsi
0x14000e490  mov     rax, [rbp+arg_38]
0x14000e497  mov     [rsp+78h+var_40], rax
0x14000e49c  mov     [rsp+78h+var_48], rsi
0x14000e4a1  mov     [rsp+78h+var_50], rbx
0x14000e4a6  mov     qword ptr [rsp+78h+var_58], r15
0x14000e4ab  mov     r9, r12
0x14000e4ae  mov     rdx, [rsi+1B0h]
0x14000e4b5  mov     rcx, r10
0x14000e4b8  call    ??0CInterceptor_IWbemSyncObjectSink_ExecMethodAsync@@QEAA@AEAVWmiAllocator@@JPEAG1PEAUIWbemClassObject@@PEAVCInterceptor_IWbemSyncProvider@@PEAUIWbemObjectSink@@PEAUIUnknown@@PEAV?$WmiContainerController@PEAX@@K1@Z; CInterceptor_IWbemSyncObjectSink_ExecMethodAsync::CInterceptor_IWbemSyncObjectSink_ExecMethodAsync(WmiAllocator &,long,ushort *,ushort *,IWbemClassObject *,CInterceptor_IWbemSyncProvider *,IWbemObjectSink *,IUnknown *,WmiContainerController<void *> *,ulong,ushort *)
0x14000e4bd  mov     rdi, rax
0x14000e4c0  jmp     short loc_14000E4CB
0x14000e4c2  xor     edi, edi
0x14000e4c4  lea     r14, [rsi+0E8h]
0x14000e4cb  test    rdi, rdi
0x14000e4ce  jz      loc_14000E694
0x14000e4d4  mov     rax, [rdi]
0x14000e4d7  mov     rcx, rdi
0x14000e4da  mov     rax, [rax+8]
0x14000e4de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e4e3  mov     rax, [rdi]
0x14000e4e6  mov     rcx, rdi
0x14000e4e9  mov     rax, [rax+50h]
0x14000e4ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e4f2  mov     ebx, eax
0x14000e4f4  test    eax, eax
0x14000e4f6  js      loc_14000E683
0x14000e4fc  mov     [rbp+var_10], 0
0x14000e504  mov     rax, [r14]
0x14000e507  mov     rcx, r14
0x14000e50a  mov     rax, [rax+30h]
0x14000e50e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e513  mov     rax, [r14]
0x14000e516  lea     rdx, [rdi+10h]
0x14000e51a  lea     r8, [rbp+var_10]
0x14000e51e  mov     rcx, r14
0x14000e521  mov     rax, [rax+40h]
0x14000e525  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e52a  mov     rdx, [r14]
0x14000e52d  mov     r8, [rdx+38h]
0x14000e531  mov     rcx, r14
0x14000e534  test    eax, eax
0x14000e536  mov     rax, r8
0x14000e539  jnz     loc_14000E661
0x14000e53f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e544  mov     rax, [rsi+258h]
0x14000e54b  mov     ecx, [rax+6CCh]
0x14000e551  neg     ecx
0x14000e553  sbb     r14d, r14d
0x14000e556  and     r14d, 80h
0x14000e55d  add     r14d, 0FFFFFD7Fh
0x14000e564  test    r13d, r13d
0x14000e567  jz      short loc_14000E57D
0x14000e569  call    cs:__imp_CoImpersonateClient
0x14000e56f  test    eax, eax
0x14000e571  jns     short loc_14000E57D
0x14000e573  mov     ebx, 80041003h
0x14000e578  jmp     loc_14000E65B
0x14000e57d  and     r14d, [rbp+arg_20]
0x14000e581  mov     rax, cs:?s_SharedCounters@ProviderSubSystem_Globals@@2PEAVCServerObject_ProviderSubsystem_Counters@@EA; CServerObject_ProviderSubsystem_Counters * ProviderSubSystem_Globals::s_SharedCounters
0x14000e588  test    rax, rax
0x14000e58b  jz      short loc_14000E594
0x14000e58d  inc     qword ptr [rax+0C8h]
0x14000e594  inc     qword ptr [rsi+2C8h]
0x14000e59b  mov     r13, [rbp+arg_40]
0x14000e5a2  mov     rax, [r13+0]
0x14000e5a6  mov     [rsp+78h+var_48], rdi
0x14000e5ab  mov     rcx, [rbp+arg_30]
0x14000e5af  mov     [rsp+78h+var_50], rcx
0x14000e5b4  mov     rcx, [rbp+var_18]
0x14000e5b8  mov     qword ptr [rsp+78h+var_58], rcx
0x14000e5bd  mov     r9d, r14d
0x14000e5c0  mov     r8, r15
0x14000e5c3  mov     rdx, r12
0x14000e5c6  mov     rcx, r13
0x14000e5c9  mov     rax, [rax+0C8h]
0x14000e5d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e5d5  mov     ebx, eax
0x14000e5d7  call    cs:__imp_CoRevertToSelf
0x14000e5dd  cmp     ebx, 80041035h
0x14000e5e3  jz      short loc_14000E5ED
0x14000e5e5  cmp     ebx, 80041008h
0x14000e5eb  jnz     short loc_14000E65B
0x14000e5ed  cmp     [rbp+arg_8], 0
0x14000e5f1  jz      short loc_14000E601
0x14000e5f3  call    cs:__imp_CoImpersonateClient
0x14000e5f9  test    eax, eax
0x14000e5fb  js      loc_14000E573
0x14000e601  btr     r14d, 7
0x14000e606  mov     rax, cs:?s_SharedCounters@ProviderSubSystem_Globals@@2PEAVCServerObject_ProviderSubsystem_Counters@@EA; CServerObject_ProviderSubsystem_Counters * ProviderSubSystem_Globals::s_SharedCounters
0x14000e60d  test    rax, rax
0x14000e610  jz      short loc_14000E619
0x14000e612  inc     qword ptr [rax+0C8h]
0x14000e619  inc     qword ptr [rsi+2C8h]
0x14000e620  mov     rax, [r13+0]
0x14000e624  mov     [rsp+78h+var_48], rdi
0x14000e629  mov     rcx, [rbp+arg_30]
0x14000e62d  mov     [rsp+78h+var_50], rcx
0x14000e632  mov     rdx, [rbp+var_18]
0x14000e636  mov     qword ptr [rsp+78h+var_58], rdx
0x14000e63b  mov     r9d, r14d
0x14000e63e  mov     r8, r15
0x14000e641  mov     rdx, r12
0x14000e644  mov     rcx, r13
0x14000e647  mov     rax, [rax+0C8h]
0x14000e64e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e653  mov     ebx, eax
0x14000e655  call    cs:__imp_CoRevertToSelf
0x14000e65b  test    ebx, ebx
0x14000e65d  js      short loc_14000E66B
0x14000e65f  jmp     short loc_14000E683
0x14000e661  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e666  mov     ebx, 80041006h
0x14000e66b  mov     [rsp+78h+var_50], rdi; struct IWbemObjectSink *
0x14000e670  mov     [rsp+78h+var_58], ebx; int
0x14000e674  lea     rdx, aExecmethodasyn_0; "ExecMethodAsync"
0x14000e67b  mov     rcx, rsi; this
0x14000e67e  call    ?SetStatus@CInterceptor_IWbemSyncProvider@@AEAAJPEAG00JPEAUIWbemObjectSink@@@Z; CInterceptor_IWbemSyncProvider::SetStatus(ushort *,ushort *,ushort *,long,IWbemObjectSink *)
0x14000e683  mov     rax, [rdi]
0x14000e686  mov     rcx, rdi
0x14000e689  mov     rax, [rax+10h]
0x14000e68d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e692  jmp     short loc_14000E6AB
0x14000e694  mov     rcx, r12; bstrString
0x14000e697  call    cs:__imp_SysFreeString
0x14000e69d  mov     rcx, r15; bstrString
0x14000e6a0  call    cs:__imp_SysFreeString
0x14000e6a6  mov     ebx, 80041006h
0x14000e6ab  lea     rcx, [rbp+arg_28]; this
0x14000e6af  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x14000e6b4  jmp     short loc_14000E6BB
0x14000e6b6  mov     ebx, 80041006h
0x14000e6bb  mov     rcx, [rbp+var_18]
0x14000e6bf  test    rcx, rcx
0x14000e6c2  jz      short loc_14000E6D0
0x14000e6c4  mov     rax, [rcx]
0x14000e6c7  mov     rax, [rax+10h]
0x14000e6cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e6d0  test    ebx, ebx
0x14000e6d2  jns     short loc_14000E6E5
0x14000e6d4  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x14000e6da  mov     edx, ebx
0x14000e6dc  mov     rcx, rax
0x14000e6df  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x14000e6e5  lea     rax, WPP_GLOBAL_Control
0x14000e6ec  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e6f3  cmp     rcx, rax
0x14000e6f6  jz      short loc_14000E71C
0x14000e6f8  test    byte ptr [rcx+1Ch], 4
0x14000e6fc  jz      short loc_14000E71C
0x14000e6fe  cmp     byte ptr [rcx+19h], 2
0x14000e702  jb      short loc_14000E71C
0x14000e704  mov     edx, 7Dh ; '}'
0x14000e709  mov     r9d, ebx
0x14000e70c  lea     r8, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids
0x14000e713  mov     rcx, [rcx+10h]
0x14000e717  call    WPP_SF_d
0x14000e71c  mov     eax, ebx
0x14000e71e  add     rsp, 78h
0x14000e722  pop     r15
0x14000e724  pop     r14
0x14000e726  pop     r13
0x14000e728  pop     r12
0x14000e72a  pop     rdi
0x14000e72b  pop     rsi
0x14000e72c  pop     rbx
0x14000e72d  pop     rbp
0x14000e72e  retn
```
