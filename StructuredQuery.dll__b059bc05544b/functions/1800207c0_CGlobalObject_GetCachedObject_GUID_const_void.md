# CGlobalObject::GetCachedObject(_GUID const &,void * *)

- ea: `0x1800207c0`
- end: `0x180020bb6`
- name: `?GetCachedObject@CGlobalObject@@QEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `1014`
- prototype: `__int64 __fastcall(CGlobalObject *__hidden this, const struct _GUID *, void **)`
- caller_count: `4`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180020540`
- `0x1800205c0`
- `0x1800313f0`
- `0x180032b30`

## callees

- `0x1800205cc`
- `0x1800207c0`
- `0x180020bbc`
- `0x180020c0c`
- `0x18003ed94`
- `0x18003efb0`
- `0x18003efe0`
- `0x18005db14`
- `0x18005db64`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180020b3b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180020b3b`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180020803`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180020803`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180020810`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180020a0a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180020810`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180020a0a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800208ed`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020acc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800208ed`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020acc`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002087c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002087c`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180020b47`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180020b47`
- `api-ms-win-core-com-private-l1-1-0!CoRegisterInitializeSpy` at `0x180020946`
- `api-ms-win-core-com-private-l1-1-0!CoRegisterInitializeSpy` at `0x180020946`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180020b8a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180020b8a`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18002082c`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18002082c`

## pseudocode

```c
__int64 __fastcall CGlobalObject::GetCachedObject(CGlobalObject *this, const struct _GUID *a2, void **a3)
{
  HRESULT ApartmentType; // ebx
  const struct _GUID *v6; // r8
  DWORD v7; // r14d
  volatile signed __int32 *Value; // rax
  volatile signed __int32 *v9; // rdi
  __int64 (__fastcall ***v10)(_QWORD, GUID *, void **); // rcx
  unsigned int v12; // edi
  LPVOID v13; // rcx
  CCachedSTAObject *v14; // rax
  CCachedSTAObject *v15; // rax
  CCachedSTAObject *v16; // rsi
  const struct _GUID *v17; // rdx
  HRESULT ApartmentObject; // eax
  struct IUnknown *v19; // rdx
  __int64 (__fastcall ***v20)(_QWORD, const struct _GUID *, void **); // rcx
  void *v21; // rcx
  HRESULT v22; // eax
  CGlobalObject *pAptType; // [rsp+70h] [rbp+40h] BYREF
  APTTYPEQUALIFIER pAptQualifier; // [rsp+80h] [rbp+50h] BYREF
  void *v25; // [rsp+88h] [rbp+58h] BYREF

  pAptType = this;
  *a3 = 0;
  v25 = 0;
  InitOnceExecuteOnce(&InitOnce, _lambda_c12b5e827bbdb1597ce6a3af58750a50_::_lambda_invoker_cdecl_, &CriticalSection, 0);
  EnterCriticalSection(&CriticalSection);
  LODWORD(pAptType) = 0;
  pAptQualifier = APTTYPEQUALIFIER_NONE;
  ApartmentType = CoGetApartmentType((APTTYPE *)&pAptType, &pAptQualifier);
  if ( ApartmentType < 0 )
    goto LABEL_11;
  if ( !(_DWORD)pAptType )
  {
LABEL_3:
    ApartmentType = CApartmentLocalObject::_DelayAllocateTLS((CApartmentLocalObject *)&dwTlsIndex);
    if ( ApartmentType < 0 )
      goto LABEL_11;
    v7 = dwTlsIndex;
    ApartmentType = 1;
    v25 = 0;
    if ( dwTlsIndex == -1 )
      goto LABEL_11;
    Value = (volatile signed __int32 *)TlsGetValue(dwTlsIndex);
    v9 = Value;
    if ( Value )
    {
      if ( *((_DWORD *)Value + 10) )
      {
        _InterlockedAdd(Value + 2, 1u);
        v25 = 0;
        v10 = (__int64 (__fastcall ***)(_QWORD, GUID *, void **))*((_QWORD *)Value + 4);
        if ( v10 )
          ApartmentType = (**v10)(v10, &GUID_a6087428_3be3_4d73_b308_7c04a540bf1a, &v25);
        else
          ApartmentType = 1;
LABEL_9:
        if ( _InterlockedExchangeAdd(v9 + 2, 0xFFFFFFFF) == 1 )
          operator delete((void *)v9, (const struct std::nothrow_t *)0x30);
        goto LABEL_11;
      }
    }
    else
    {
      v9 = 0;
      v14 = (CCachedSTAObject *)operator new(0x30u, (const struct std::nothrow_t *)&std::nothrow);
      if ( v14 && (v15 = CCachedSTAObject::CCachedSTAObject(v14), (v16 = v15) != 0) )
      {
        *((_DWORD *)v15 + 6) = v7;
        ApartmentType = CoRegisterInitializeSpy((IInitializeSpy *)v15, (ULARGE_INTEGER *)v15 + 2);
        if ( ApartmentType >= 0 )
        {
          ApartmentType = 1;
          *((_DWORD *)v16 + 10) = 1;
          if ( !CCachedSTAObject::s_hmod )
            GetModuleHandleExW(4u, (LPCWSTR)&CCachedSTAObject::s_hmod, &CCachedSTAObject::s_hmod);
          TlsSetValue(v7, v16);
          v9 = (volatile signed __int32 *)v16;
          _InterlockedAdd((volatile signed __int32 *)v16 + 2, 1u);
        }
        CCachedSTAObject::Release(v16);
      }
      else
      {
        ApartmentType = -2147024882;
      }
      if ( ApartmentType >= 0 )
        goto LABEL_9;
    }
    ApartmentType = 1;
    goto LABEL_11;
  }
  if ( (_DWORD)pAptType != 1 )
  {
    if ( (_DWORD)pAptType == 2 )
    {
      ApartmentType = CApartmentLocalObject::_GetInterfaceFromGIT(0, HIDWORD(qword_1800B12D4), v6, &v25);
      goto LABEL_11;
    }
    if ( (_DWORD)pAptType != 3 )
    {
      ApartmentType = -2147221008;
      goto LABEL_11;
    }
    goto LABEL_3;
  }
  v12 = qword_1800B12D4;
  ApartmentType = 1;
  v25 = 0;
  if ( !(_DWORD)qword_1800B12D4 )
    goto LABEL_11;
  v13 = g_pgit;
  if ( !g_pgit )
  {
    ApartmentType = CoCreateInstance(
                      &CLSID_StdGlobalInterfaceTable,
                      0,
                      1u,
                      &GUID_00000146_0000_0000_c000_000000000046,
                      &g_pgit);
    if ( ApartmentType < 0 )
      goto LABEL_11;
    v13 = g_pgit;
  }
  ApartmentType = (*(__int64 (__fastcall **)(LPVOID, _QWORD, GUID *, void **))(*(_QWORD *)v13 + 40LL))(
                    v13,
                    v12,
                    &GUID_a6087428_3be3_4d73_b308_7c04a540bf1a,
                    &v25);
  if ( ApartmentType < 0 )
    ApartmentType = 1;
LABEL_11:
  LeaveCriticalSection(&CriticalSection);
  if ( ApartmentType )
  {
    if ( ApartmentType != 1 )
      return (unsigned int)ApartmentType;
    EnterCriticalSection(&stru_1800B1318);
    ApartmentObject = CApartmentLocalObject::GetApartmentObject((CApartmentLocalObject *)&dwTlsIndex, v17, &v25);
    ApartmentType = ApartmentObject;
    if ( ApartmentObject )
    {
      if ( ApartmentObject != 1 )
        goto LABEL_38;
      pAptType = 0;
      if ( qword_1800B1310
        || (ApartmentType = ((__int64 (__fastcall *)(GUID *, CGlobalObject **))qword_1800B1340)(
                              &GUID_00000000_0000_0000_c000_000000000046,
                              &pAptType),
            ApartmentType >= 0) )
      {
        ApartmentType = CApartmentLocalObject::SetApartmentObject((CApartmentLocalObject *)&dwTlsIndex, v19);
        if ( ApartmentType >= 0 )
        {
          v20 = (__int64 (__fastcall ***)(_QWORD, const struct _GUID *, void **))qword_1800B1310;
          if ( !qword_1800B1310 )
          {
            qword_1800B1310 = (__int64)pAptType;
            (*(void (__fastcall **)(CGlobalObject *))(*(_QWORD *)pAptType + 8LL))(pAptType);
            v20 = (__int64 (__fastcall ***)(_QWORD, const struct _GUID *, void **))qword_1800B1310;
          }
          ApartmentType = (**v20)(v20, a2, a3);
        }
      }
      v21 = pAptType;
      if ( !pAptType )
        goto LABEL_38;
    }
    else
    {
      v22 = (*(__int64 (__fastcall **)(void *, __int64 *, const struct _GUID *, void **))(*(_QWORD *)v25 + 24LL))(
              v25,
              &qword_18009BE10,
              a2,
              a3);
      v21 = v25;
      ApartmentType = v22;
    }
    (*(void (__fastcall **)(void *))(*(_QWORD *)v21 + 16LL))(v21);
LABEL_38:
    LeaveCriticalSection(&stru_1800B1318);
    return (unsigned int)ApartmentType;
  }
  ApartmentType = (*(__int64 (__fastcall **)(void *, __int64 *, const struct _GUID *, void **))(*(_QWORD *)v25 + 24LL))(
                    v25,
                    &qword_18009BE10,
                    a2,
                    a3);
  (*(void (__fastcall **)(void *))(*(_QWORD *)v25 + 16LL))(v25);
  return (unsigned int)ApartmentType;
}

```

## disassembly

```asm
0x1800207c0  mov     [rsp-38h+pAptType], rcx
0x1800207c5  push    rbp
0x1800207c6  push    rbx
0x1800207c7  push    rsi
0x1800207c8  push    rdi
0x1800207c9  push    r12
0x1800207cb  push    r14
0x1800207cd  push    r15
0x1800207cf  mov     rbp, rsp
0x1800207d2  sub     rsp, 30h
0x1800207d6  mov     r15, r8
0x1800207d9  mov     qword ptr [r8], 0
0x1800207e0  mov     r12, rdx
0x1800207e3  mov     [rbp+arg_18], 0
0x1800207eb  lea     r8, CriticalSection; Parameter
0x1800207f2  xor     r9d, r9d; Context
0x1800207f5  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_c12b5e827bbdb1597ce6a3af58750a50_@@CA@PEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x1800207fc  lea     rcx, InitOnce; InitOnce
0x180020803  call    cs:__imp_InitOnceExecuteOnce
0x180020809  lea     rcx, CriticalSection; lpCriticalSection
0x180020810  call    cs:__imp_EnterCriticalSection
0x180020816  lea     rdx, [rbp+pAptQualifier]; pAptQualifier
0x18002081a  mov     dword ptr [rbp+pAptType], 0
0x180020821  lea     rcx, [rbp+pAptType]; pAptType
0x180020825  mov     [rbp+pAptQualifier], 0
0x18002082c  call    cs:__imp_CoGetApartmentType
0x180020832  mov     ebx, eax
0x180020834  mov     esi, 1
0x180020839  test    eax, eax
0x18002083b  js      loc_1800208E6
0x180020841  mov     ecx, dword ptr [rbp+pAptType]
0x180020844  test    ecx, ecx
0x180020846  jnz     loc_180020972
0x18002084c  lea     rcx, dwTlsIndex; this
0x180020853  call    ?_DelayAllocateTLS@CApartmentLocalObject@@AEAAJXZ; CApartmentLocalObject::_DelayAllocateTLS(void)
0x180020858  mov     ebx, eax
0x18002085a  test    eax, eax
0x18002085c  js      loc_1800208E6
0x180020862  mov     r14d, cs:dwTlsIndex
0x180020869  mov     ebx, esi
0x18002086b  mov     [rbp+arg_18], 0
0x180020873  cmp     r14d, 0FFFFFFFFh
0x180020877  jz      short loc_1800208E6
0x180020879  mov     ecx, r14d; dwTlsIndex
0x18002087c  call    cs:__imp_TlsGetValue
0x180020882  mov     rdi, rax
0x180020885  test    rax, rax
0x180020888  jz      loc_1800209C7
0x18002088e  cmp     dword ptr [rax+28h], 0
0x180020892  jz      loc_18002096B
0x180020898  lock add [rax+8], esi
0x18002089c  mov     [rbp+arg_18], 0
0x1800208a4  mov     rcx, [rdi+20h]
0x1800208a8  test    rcx, rcx
0x1800208ab  jz      loc_180020AF1
0x1800208b1  mov     rax, [rcx]
0x1800208b4  lea     r8, [rbp+arg_18]
0x1800208b8  lea     rdx, _GUID_a6087428_3be3_4d73_b308_7c04a540bf1a
0x1800208bf  mov     rax, [rax]
0x1800208c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800208c7  mov     ebx, eax
0x1800208c9  or      eax, 0FFFFFFFFh
0x1800208cc  lock xadd [rdi+8], eax
0x1800208d1  cmp     eax, 1
0x1800208d4  jnz     short loc_1800208E1
0x1800208d6  lea     edx, [rax+2Fh]; struct std::nothrow_t *
0x1800208d9  mov     rcx, rdi; void *
0x1800208dc  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800208e1  mov     esi, 1
0x1800208e6  lea     rcx, CriticalSection; lpCriticalSection
0x1800208ed  call    cs:__imp_LeaveCriticalSection
0x1800208f3  test    ebx, ebx
0x1800208f5  jnz     loc_1800209FB
0x1800208fb  mov     rcx, [rbp+arg_18]
0x1800208ff  lea     rdx, qword_18009BE10
0x180020906  mov     r9, r15
0x180020909  mov     r8, r12
0x18002090c  mov     rax, [rcx]
0x18002090f  mov     rax, [rax+18h]
0x180020913  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020918  mov     rcx, [rbp+arg_18]
0x18002091c  mov     ebx, eax
0x18002091e  mov     rdx, [rcx]
0x180020921  mov     rax, [rdx+10h]
0x180020925  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002092a  mov     eax, ebx
0x18002092c  add     rsp, 30h
0x180020930  pop     r15
0x180020932  pop     r14
0x180020934  pop     r12
0x180020936  pop     rdi
0x180020937  pop     rsi
0x180020938  pop     rbx
0x180020939  pop     rbp
0x18002093a  retn
0x18002093b  lea     rdx, [rax+10h]; puliCookie
0x18002093f  mov     [rax+18h], r14d
0x180020943  mov     rcx, rsi; pSpy
0x180020946  call    cs:__imp_CoRegisterInitializeSpy
0x18002094c  mov     ebx, eax
0x18002094e  test    eax, eax
0x180020950  jns     loc_180020B1D
0x180020956  mov     rcx, rsi; this
0x180020959  call    ?Release@CCachedSTAObject@@UEAAKXZ; CCachedSTAObject::Release(void)
0x18002095e  test    ebx, ebx
0x180020960  jns     loc_180020BA6
0x180020966  mov     esi, 1
0x18002096b  mov     ebx, esi
0x18002096d  jmp     loc_1800208E6
0x180020972  sub     ecx, esi
0x180020974  jnz     loc_180020AD7
0x18002097a  mov     edi, dword ptr cs:qword_1800B12D4
0x180020980  mov     ebx, esi
0x180020982  mov     [rbp+arg_18], 0
0x18002098a  test    edi, edi
0x18002098c  jz      loc_1800208E6
0x180020992  mov     rcx, cs:?g_pgit@@3PEAUIGlobalInterfaceTable@@EA; IGlobalInterfaceTable * g_pgit
0x180020999  test    rcx, rcx
0x18002099c  jz      loc_180020B6B
0x1800209a2  mov     rax, [rcx]
0x1800209a5  lea     r9, [rbp+arg_18]
0x1800209a9  lea     r8, _GUID_a6087428_3be3_4d73_b308_7c04a540bf1a
0x1800209b0  mov     edx, edi
0x1800209b2  mov     rax, [rax+28h]
0x1800209b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800209bb  test    eax, eax
0x1800209bd  mov     ebx, eax
0x1800209bf  cmovs   ebx, esi
0x1800209c2  jmp     loc_1800208E6
0x1800209c7  xor     edi, edi
0x1800209c9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800209d0  lea     ecx, [rdi+30h]; unsigned __int64
0x1800209d3  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800209d8  test    rax, rax
0x1800209db  jz      short loc_1800209F1
0x1800209dd  mov     rcx, rax; this
0x1800209e0  call    ??0CCachedSTAObject@@QEAA@XZ; CCachedSTAObject::CCachedSTAObject(void)
0x1800209e5  mov     rsi, rax
0x1800209e8  test    rax, rax
0x1800209eb  jnz     loc_18002093B
0x1800209f1  mov     ebx, 8007000Eh
0x1800209f6  jmp     loc_18002095E
0x1800209fb  cmp     ebx, esi
0x1800209fd  jnz     loc_18002092A
0x180020a03  lea     rcx, stru_1800B1318; lpCriticalSection
0x180020a0a  call    cs:__imp_EnterCriticalSection
0x180020a10  lea     r8, [rbp+arg_18]; void **
0x180020a14  lea     rcx, dwTlsIndex; this
0x180020a1b  call    ?GetApartmentObject@CApartmentLocalObject@@QEAAJAEBU_GUID@@PEAPEAX@Z; CApartmentLocalObject::GetApartmentObject(_GUID const &,void * *)
0x180020a20  mov     ebx, eax
0x180020a22  test    eax, eax
0x180020a24  jz      loc_180020AF8
0x180020a2a  cmp     eax, esi
0x180020a2c  jnz     loc_180020AC5
0x180020a32  cmp     cs:qword_1800B1310, 0
0x180020a3a  mov     [rbp+pAptType], 0
0x180020a42  jnz     short loc_180020A61
0x180020a44  mov     rax, cs:qword_1800B1340
0x180020a4b  lea     rdx, [rbp+pAptType]
0x180020a4f  lea     rcx, _GUID_00000000_0000_0000_c000_000000000046
0x180020a56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020a5b  mov     ebx, eax
0x180020a5d  test    eax, eax
0x180020a5f  js      short loc_180020AB0
0x180020a61  lea     rcx, dwTlsIndex; this
0x180020a68  call    ?SetApartmentObject@CApartmentLocalObject@@QEAAJPEAUIUnknown@@@Z; CApartmentLocalObject::SetApartmentObject(IUnknown *)
0x180020a6d  mov     ebx, eax
0x180020a6f  test    eax, eax
0x180020a71  js      short loc_180020AB0
0x180020a73  mov     rcx, cs:qword_1800B1310
0x180020a7a  test    rcx, rcx
0x180020a7d  jnz     short loc_180020A9D
0x180020a7f  mov     rcx, [rbp+pAptType]
0x180020a83  mov     cs:qword_1800B1310, rcx
0x180020a8a  mov     rax, [rcx]
0x180020a8d  mov     rax, [rax+8]
0x180020a91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020a96  mov     rcx, cs:qword_1800B1310
0x180020a9d  mov     rax, [rcx]
0x180020aa0  mov     r8, r15
0x180020aa3  mov     rdx, r12
0x180020aa6  mov     rax, [rax]
0x180020aa9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020aae  mov     ebx, eax
0x180020ab0  mov     rcx, [rbp+pAptType]
0x180020ab4  test    rcx, rcx
0x180020ab7  jz      short loc_180020AC5
0x180020ab9  mov     rax, [rcx]
0x180020abc  mov     rax, [rax+10h]
0x180020ac0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020ac5  lea     rcx, stru_1800B1318; lpCriticalSection
0x180020acc  call    cs:__imp_LeaveCriticalSection
0x180020ad2  jmp     loc_18002092A
0x180020ad7  sub     ecx, esi; this
0x180020ad9  jnz     short loc_180020B59
0x180020adb  mov     edx, dword ptr cs:qword_1800B12D4+4; unsigned int
0x180020ae1  lea     r9, [rbp+arg_18]; void **
0x180020ae5  call    ?_GetInterfaceFromGIT@CApartmentLocalObject@@AEAAJKAEBU_GUID@@PEAPEAX@Z; CApartmentLocalObject::_GetInterfaceFromGIT(ulong,_GUID const &,void * *)
0x180020aea  mov     ebx, eax
0x180020aec  jmp     loc_1800208E6
0x180020af1  mov     ebx, esi
0x180020af3  jmp     loc_1800208C9
0x180020af8  mov     rcx, [rbp+arg_18]
0x180020afc  lea     rdx, qword_18009BE10
0x180020b03  mov     r9, r15
0x180020b06  mov     r8, r12
0x180020b09  mov     rax, [rcx]
0x180020b0c  mov     rax, [rax+18h]
0x180020b10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020b15  mov     rcx, [rbp+arg_18]
0x180020b19  mov     ebx, eax
0x180020b1b  jmp     short loc_180020AB9
0x180020b1d  mov     ebx, 1
0x180020b22  mov     [rsi+28h], ebx
0x180020b25  cmp     cs:?s_hmod@CCachedSTAObject@@0PEAUHINSTANCE__@@EA, rdi; HINSTANCE__ * CCachedSTAObject::s_hmod
0x180020b2c  jnz     short loc_180020B41
0x180020b2e  lea     rdx, ?s_hmod@CCachedSTAObject@@0PEAUHINSTANCE__@@EA; lpModuleName
0x180020b35  mov     r8, rdx; phModule
0x180020b38  lea     ecx, [rbx+3]; dwFlags
0x180020b3b  call    cs:__imp_GetModuleHandleExW
0x180020b41  mov     rdx, rsi; lpTlsValue
0x180020b44  mov     ecx, r14d; dwTlsIndex
0x180020b47  call    cs:__imp_TlsSetValue
0x180020b4d  mov     rdi, rsi
0x180020b50  lock add [rsi+8], ebx
0x180020b54  jmp     loc_180020956
0x180020b59  cmp     ecx, esi
0x180020b5b  jz      loc_18002084C
0x180020b61  mov     ebx, 800401F0h
0x180020b66  jmp     loc_1800208E6
0x180020b6b  lea     rax, ?g_pgit@@3PEAUIGlobalInterfaceTable@@EA; IGlobalInterfaceTable * g_pgit
0x180020b72  mov     r8d, esi; dwClsContext
0x180020b75  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180020b7c  mov     [rsp+30h+ppv], rax; ppv
0x180020b81  xor     edx, edx; pUnkOuter
0x180020b83  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180020b8a  call    cs:__imp_CoCreateInstance
0x180020b90  mov     ebx, eax
0x180020b92  test    eax, eax
0x180020b94  js      loc_1800208E6
0x180020b9a  mov     rcx, cs:?g_pgit@@3PEAUIGlobalInterfaceTable@@EA; IGlobalInterfaceTable * g_pgit
0x180020ba1  jmp     loc_1800209A2
0x180020ba6  jnz     loc_1800208C9
0x180020bac  mov     esi, 1
0x180020bb1  jmp     loc_18002089C
```
