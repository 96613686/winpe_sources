# SEReader::Initialize(ushort *,std::shared_ptr<RoutingMgr>)

- ea: `0x180016e48`
- end: `0x18001708e`
- name: `?Initialize@SEReader@@QEAAJPEAGV?$shared_ptr@VRoutingMgr@@@std@@@Z`
- size: `582`
- prototype: `__int64 __fastcall(SEReader *this, void *Src)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001089c`

## callees

- `0x180001194`
- `0x18000584c`
- `0x180013014`
- `0x180016e48`
- `0x180017094`
- `0x180017a60`
- `0x18009d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001700e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001700e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017005`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017005`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016e7e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016e7e`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180016fa2`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180016fa2`

## string_xrefs

- `0x180016e8e`: `SEReader::Initialize`
- `0x180016fd8`: `SEReader::Initialize`
- `0x180016e9a`: `SEReader::Initialize starts`
- `0x180016fcd`: `SEReader::Initialize ends`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall SEReader::Initialize(SEReader *this, _WORD *Src, _QWORD *a3)
{
  struct _RTL_CRITICAL_SECTION *v6; // r12
  __int64 v7; // r8
  int v8; // r9d
  char **v9; // rcx
  unsigned __int64 v10; // rdx
  char *v11; // rsi
  __int64 v12; // rbx
  __int64 v13; // rax
  __int64 v14; // rcx
  volatile signed __int32 *v15; // rbx
  int v16; // ecx
  int v17; // esi
  int v18; // r8d
  int v19; // r9d
  int v20; // esi
  volatile signed __int32 *v21; // rbx
  const char *v23; // [rsp+A0h] [rbp+40h] BYREF
  _QWORD *v24; // [rsp+B0h] [rbp+50h]
  const char *v25; // [rsp+B8h] [rbp+58h] BYREF

  v24 = a3;
  v6 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 32);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  if ( (unsigned int)dword_18012F048 > 5 )
  {
    v23 = "SEReader::Initialize starts";
    v25 = "SEReader::Initialize";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(
      (unsigned int)"SEReader::Initialize",
      (unsigned int)word_180119E02,
      v7,
      v8,
      (__int64)&v25,
      (__int64)&v23);
  }
  v9 = (char **)((char *)this + 96);
  v10 = -1;
  do
    ++v10;
  while ( Src[v10] );
  if ( v10 > *((_QWORD *)this + 15) )
  {
    ____Reallocate_for_V_lambda_1___1_____Assign_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV23_QEBG_K_Z_PEBG___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1_____Assign_G_01_AEAAAEAV01_QEBG0_Z_PEBG_Z(
      v9,
      v10,
      v7,
      Src);
  }
  else
  {
    if ( *((_QWORD *)this + 15) <= 7u )
      v11 = (char *)this + 96;
    else
      v11 = *v9;
    *((_QWORD *)this + 14) = v10;
    v12 = 2 * v10;
    memmove_0(v11, Src, 2 * v10);
    *(_WORD *)&v11[v12] = 0;
  }
  v13 = *a3;
  v14 = a3[1];
  *a3 = 0;
  a3[1] = 0;
  *((_QWORD *)this + 16) = v13;
  v15 = (volatile signed __int32 *)*((_QWORD *)this + 17);
  *((_QWORD *)this + 17) = v14;
  if ( v15 )
  {
    if ( _InterlockedExchangeAdd(v15 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
      if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
    }
  }
  v17 = RtlSubscribeWnfStateChangeNotification(
          (char *)this + 400,
          WNF_NFC_SE_CARD_EMULATION_STATE_CHANGED,
          0,
          SEReader::WNFApplyPolicyStateChangeCallback,
          this,
          0,
          0,
          0);
  if ( v17 < 0 )
  {
    v20 = v17 | 0x10000000;
    if ( v20 >= 0 )
      goto LABEL_18;
    goto LABEL_17;
  }
  v20 = SEReader::InitializeHardwareDependant(this);
  if ( v20 < 0 )
  {
LABEL_17:
    SEReader::Uninitialize(this);
    goto LABEL_18;
  }
  *((_DWORD *)this + 19) = 1;
LABEL_18:
  if ( (unsigned int)dword_18012F048 > 5 )
  {
    v23 = "SEReader::Initialize ends";
    v25 = "SEReader::Initialize";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v16,
      (unsigned int)byte_180119C93,
      v18,
      v19,
      (__int64)&v25,
      (__int64)&v23);
  }
  LeaveCriticalSection(v6);
  CoTaskMemFree(0);
  v21 = (volatile signed __int32 *)a3[1];
  if ( v21 )
  {
    if ( _InterlockedExchangeAdd(v21 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v21)(v21);
      if ( _InterlockedExchangeAdd(v21 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v21 + 8LL))(v21);
    }
  }
  return (unsigned int)v20;
}

```

## disassembly

```asm
0x180016e48  mov     [rsp-38h+arg_8], rbx
0x180016e4d  mov     [rsp-38h+arg_10], r8
0x180016e52  push    rbp
0x180016e53  push    rsi
0x180016e54  push    rdi
0x180016e55  push    r12
0x180016e57  push    r13
0x180016e59  push    r14
0x180016e5b  push    r15
0x180016e5d  mov     rbp, rsp
0x180016e60  sub     rsp, 60h
0x180016e64  mov     r14, r8
0x180016e67  mov     r15, rdx
0x180016e6a  mov     rdi, rcx
0x180016e6d  xor     esi, esi
0x180016e6f  mov     [rbp+var_20], rsi
0x180016e73  lea     r12, [rcx+20h]
0x180016e77  mov     [rbp+var_18], r12
0x180016e7b  mov     rcx, r12; lpCriticalSection
0x180016e7e  call    cs:__imp_EnterCriticalSection
0x180016e84  mov     [rbp+var_10], 1
0x180016e88  mov     eax, cs:dword_18012F048
0x180016e8e  lea     rcx, aSereaderInitia_0; "SEReader::Initialize"
0x180016e95  cmp     eax, 5
0x180016e98  jbe     short loc_180016EC7
0x180016e9a  lea     rax, aSereaderInitia_1; "SEReader::Initialize starts"
0x180016ea1  mov     [rbp+arg_0], rax
0x180016ea5  mov     [rbp+arg_18], rcx
0x180016ea9  lea     rax, [rbp+arg_0]
0x180016ead  mov     [rsp+60h+var_38], rax
0x180016eb2  lea     rax, [rbp+arg_18]
0x180016eb6  mov     [rsp+60h+var_40], rax
0x180016ebb  lea     rdx, word_180119E02
0x180016ec2  call    ??$Write@U?$_tlgWrapSz@D@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180016ec7  lea     rcx, [rdi+60h]
0x180016ecb  or      r13, 0FFFFFFFFFFFFFFFFh
0x180016ecf  mov     rdx, r13
0x180016ed2  inc     rdx
0x180016ed5  cmp     [r15+rdx*2], si
0x180016eda  jnz     short loc_180016ED2
0x180016edc  cmp     rdx, [rcx+18h]
0x180016ee0  ja      short loc_180016F11
0x180016ee2  cmp     qword ptr [rcx+18h], 7
0x180016ee7  jbe     short loc_180016EEE
0x180016ee9  mov     rsi, [rcx]
0x180016eec  jmp     short loc_180016EF1
0x180016eee  mov     rsi, rcx
0x180016ef1  mov     [rcx+10h], rdx
0x180016ef5  lea     rbx, [rdx+rdx]
0x180016ef9  mov     r8, rbx; Size
0x180016efc  mov     rdx, r15; Src
0x180016eff  mov     rcx, rsi; void *
0x180016f02  call    memmove_0
0x180016f07  xor     eax, eax
0x180016f09  mov     [rbx+rsi], ax
0x180016f0d  xor     esi, esi
0x180016f0f  jmp     short loc_180016F19
0x180016f11  mov     r9, r15
0x180016f14  call    ??$_Reallocate_for@V_lambda_1_@?1???$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV23@QEBG_K@Z@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Assign@G@01@AEAAAEAV01@QEBG0@Z@PEBG@Z; std::wstring::_Reallocate_for<`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *>(unsigned __int64,`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *)
0x180016f19  mov     rax, [r14]
0x180016f1c  mov     rcx, [r14+8]
0x180016f20  mov     [r14], rsi
0x180016f23  mov     [r14+8], rsi
0x180016f27  mov     [rdi+80h], rax
0x180016f2e  mov     rbx, [rdi+88h]
0x180016f35  mov     [rdi+88h], rcx
0x180016f3c  test    rbx, rbx
0x180016f3f  jz      short loc_180016F78
0x180016f41  mov     eax, r13d
0x180016f44  lock xadd [rbx+8], eax
0x180016f49  add     eax, r13d
0x180016f4c  jnz     short loc_180016F78
0x180016f4e  mov     rax, [rbx]
0x180016f51  mov     rcx, rbx
0x180016f54  mov     rax, [rax]
0x180016f57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016f5c  mov     eax, r13d
0x180016f5f  lock xadd [rbx+0Ch], eax
0x180016f64  add     eax, r13d
0x180016f67  jnz     short loc_180016F78
0x180016f69  mov     rax, [rbx]
0x180016f6c  mov     rcx, rbx
0x180016f6f  mov     rax, [rax+8]
0x180016f73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016f78  lea     rcx, [rdi+190h]
0x180016f7f  mov     [rsp+60h+var_28], esi
0x180016f83  mov     [rsp+60h+var_30], esi
0x180016f87  mov     [rsp+60h+var_38], rsi
0x180016f8c  mov     [rsp+60h+var_40], rdi
0x180016f91  lea     r9, ?WNFApplyPolicyStateChangeCallback@SEReader@@CAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z; SEReader::WNFApplyPolicyStateChangeCallback(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)
0x180016f98  xor     r8d, r8d
0x180016f9b  mov     rdx, cs:WNF_NFC_SE_CARD_EMULATION_STATE_CHANGED
0x180016fa2  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x180016fa8  mov     esi, eax
0x180016faa  test    eax, eax
0x180016fac  jns     loc_18001706F
0x180016fb2  or      esi, 10000000h
0x180016fb8  jge     short loc_180016FC2
0x180016fba  mov     rcx, rdi; this
0x180016fbd  call    ?Uninitialize@SEReader@@AEAAXXZ; SEReader::Uninitialize(void)
0x180016fc2  mov     eax, cs:dword_18012F048
0x180016fc8  cmp     eax, 5
0x180016fcb  jbe     short loc_180017002
0x180016fcd  lea     rax, aSereaderInitia; "SEReader::Initialize ends"
0x180016fd4  mov     [rbp+arg_0], rax
0x180016fd8  lea     rax, aSereaderInitia_0; "SEReader::Initialize"
0x180016fdf  mov     [rbp+arg_18], rax
0x180016fe3  lea     rax, [rbp+arg_0]
0x180016fe7  mov     [rsp+60h+var_38], rax
0x180016fec  lea     rax, [rbp+arg_18]
0x180016ff0  mov     [rsp+60h+var_40], rax
0x180016ff5  lea     rdx, byte_180119C93
0x180016ffc  call    ??$Write@U?$_tlgWrapSz@D@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180017001  nop
0x180017002  mov     rcx, r12; lpCriticalSection
0x180017005  call    cs:__imp_LeaveCriticalSection
0x18001700b  nop
0x18001700c  xor     ecx, ecx; pv
0x18001700e  call    cs:__imp_CoTaskMemFree
0x180017014  nop
0x180017015  mov     rbx, [r14+8]
0x180017019  test    rbx, rbx
0x18001701c  jz      short loc_180017055
0x18001701e  mov     eax, r13d
0x180017021  lock xadd [rbx+8], eax
0x180017026  add     eax, r13d
0x180017029  jnz     short loc_180017055
0x18001702b  mov     rax, [rbx]
0x18001702e  mov     rcx, rbx
0x180017031  mov     rax, [rax]
0x180017034  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017039  mov     eax, r13d
0x18001703c  lock xadd [rbx+0Ch], eax
0x180017041  add     eax, r13d
0x180017044  jnz     short loc_180017055
0x180017046  mov     rax, [rbx]
0x180017049  mov     rcx, rbx
0x18001704c  mov     rax, [rax+8]
0x180017050  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017055  mov     eax, esi
0x180017057  mov     rbx, [rsp+60h+arg_8]
0x18001705f  add     rsp, 60h
0x180017063  pop     r15
0x180017065  pop     r14
0x180017067  pop     r13
0x180017069  pop     r12
0x18001706b  pop     rdi
0x18001706c  pop     rsi
0x18001706d  pop     rbp
0x18001706e  retn
0x18001706f  mov     rcx, rdi; this
0x180017072  call    ?InitializeHardwareDependant@SEReader@@AEAAJXZ; SEReader::InitializeHardwareDependant(void)
0x180017077  mov     esi, eax
0x180017079  test    eax, eax
0x18001707b  js      loc_180016FBA
0x180017081  mov     dword ptr [rdi+4Ch], 1
0x180017088  jmp     loc_180016FC2
```
