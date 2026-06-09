# MemoryManager::PrereserveRamMemoryParallel(std::vector<MemoryManager::BlockLayoutRange,std::allocator<MemoryManager::BlockLayoutRange>> &,MemoryManager::ReserveMemoryPassQosFlags const *,int)

- ea: `0x1402090a4`
- end: `0x140209783`
- name: `?PrereserveRamMemoryParallel@MemoryManager@@AEAAXAEAV?$vector@VBlockLayoutRange@MemoryManager@@V?$allocator@VBlockLayoutRange@MemoryManager@@@std@@@std@@PEBUReserveMemoryPassQosFlags@1@H@Z`
- size: `1759`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: ``

## callers

- `0x140128644`

## callees

- `0x140023f74`
- `0x140051390`
- `0x1400586c4`
- `0x140066760`
- `0x140086bc0`
- `0x1400a00bc`
- `0x1400a0154`
- `0x1400e8d20`
- `0x140132940`
- `0x14013c0c8`
- `0x14013ffc0`
- `0x140173994`
- `0x140198994`
- `0x1401feb98`
- `0x1401fecc4`
- `0x1402011ac`
- `0x140201844`
- `0x14020222c`
- `0x140207988`
- `0x1402090a4`
- `0x14020d104`
- `0x14020eab4`
- `0x14020eb78`

## import_xrefs

- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x14020954b`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x1402095d3`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x14020954b`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x1402095d3`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1402093c9`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x140209505`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1402093c9`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x140209505`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x1402093e1`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x140209572`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x1402093e1`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x140209572`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1402093f5`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1402095ef`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1402093f5`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1402095ef`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall MemoryManager::PrereserveRamMemoryParallel(
        MemoryManager *a1,
        __int64 *a2,
        __int64 a3,
        unsigned int a4)
{
  MemoryManager *v5; // r15
  char *v6; // r12
  char *v7; // r13
  unsigned __int8 VirtualNumaNodeCount; // al
  unsigned __int64 v9; // rbx
  __int64 v10; // rdx
  unsigned __int64 v11; // rcx
  MemoryManager::ReserveRamMemoryContext *v12; // rbx
  __int64 v13; // r14
  __int64 v14; // rbx
  _QWORD *v15; // rsi
  int i; // r14d
  __int64 v17; // rdx
  char *v18; // r12
  unsigned __int8 j; // si
  __int64 v20; // r8
  char *v21; // rbx
  std::thread *v22; // rbx
  std::thread *v23; // rsi
  unsigned __int8 v24; // cl
  __int64 v25; // rbx
  MemoryManager::ReserveRamMemoryContext *v26; // rdx
  unsigned __int8 v27; // r14
  __int64 v28; // rsi
  __int64 v29; // rax
  __int64 v30; // r9
  __int64 k; // r8
  __int64 v33; // rcx
  unsigned int v34; // eax
  const void *v35; // rax
  unsigned __int8 v36; // bl
  int v37; // r8d
  int v38; // r9d
  unsigned __int8 v39; // [rsp+40h] [rbp-128h] BYREF
  unsigned __int8 v40; // [rsp+41h] [rbp-127h]
  __int64 v41; // [rsp+48h] [rbp-120h] BYREF
  __int64 v42; // [rsp+50h] [rbp-118h] BYREF
  char *v43; // [rsp+58h] [rbp-110h]
  char *v44; // [rsp+60h] [rbp-108h]
  __int64 *v45; // [rsp+68h] [rbp-100h]
  __int64 *v46; // [rsp+70h] [rbp-F8h]
  _BYTE v47[12]; // [rsp+78h] [rbp-F0h] BYREF
  int v48; // [rsp+84h] [rbp-E4h]
  char *v49; // [rsp+88h] [rbp-E0h]
  MemoryManager *v50; // [rsp+90h] [rbp-D8h]
  __int64 *v51; // [rsp+98h] [rbp-D0h]
  void (__fastcall *v52)(MemoryManager *__hidden, void *); // [rsp+A0h] [rbp-C8h] BYREF
  int v53; // [rsp+A8h] [rbp-C0h]
  int v54; // [rsp+ACh] [rbp-BCh]
  _BYTE v55[16]; // [rsp+B0h] [rbp-B8h] BYREF
  MemoryManager::ReserveRamMemoryContext *v56[2]; // [rsp+C0h] [rbp-A8h] BYREF
  __int64 v57; // [rsp+D0h] [rbp-98h]
  void *v58[2]; // [rsp+D8h] [rbp-90h] BYREF
  __int64 v59; // [rsp+E8h] [rbp-80h]
  std::thread *v60[2]; // [rsp+F0h] [rbp-78h] BYREF
  __int64 v61; // [rsp+100h] [rbp-68h]
  __int128 v62; // [rsp+108h] [rbp-60h] BYREF
  __int128 v63; // [rsp+118h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+0h]

  v45 = a2;
  v5 = a1;
  v50 = a1;
  v51 = a2;
  *(_OWORD *)v58 = 0;
  v59 = 0;
  v6 = 0;
  v44 = 0;
  v7 = 0;
  v43 = 0;
  *(_OWORD *)v56 = 0;
  v57 = 0;
  VirtualNumaNodeCount = MemoryManager::GetVirtualNumaNodeCount(a1);
  v40 = VirtualNumaNodeCount;
  v41 = 0;
  v9 = VirtualNumaNodeCount;
  if ( VirtualNumaNodeCount )
  {
    if ( VirtualNumaNodeCount <= (unsigned __int64)((signed __int64)(v59 - (unsigned __int64)v58[0]) >> 3) )
      v58[1] = (void *)std::_Uninitialized_fill_n<std::allocator<unsigned __int64>>(v58[1]);
    else
      std::vector<unsigned char const *>::_Resize_reallocate<unsigned char const *>(v58, VirtualNumaNodeCount, &v41);
  }
  v10 = 0x2E8BA2E8BA2E8BA3LL;
  v11 = 0x2E8BA2E8BA2E8BA3LL * ((v56[1] - v56[0]) >> 3);
  if ( v9 >= v11 )
  {
    if ( v9 > v11 )
    {
      if ( v9 <= 0x2E8BA2E8BA2E8BA3LL * ((signed __int64)(v57 - (unsigned __int64)v56[0]) >> 3) )
        v56[1] = (MemoryManager::ReserveRamMemoryContext *)std::_Uninitialized_value_construct_n<std::allocator<MemoryManager::ReserveRamMemoryContext>>(v56[1]);
      else
        std::vector<MemoryManager::ReserveRamMemoryContext>::_Resize_reallocate<std::_Value_init_tag>(v56, v9);
    }
  }
  else
  {
    v12 = (MemoryManager::ReserveRamMemoryContext *)((char *)v56[0] + 88 * v9);
    std::_Destroy_range<std::allocator<MemoryManager::ReserveRamMemoryContext>>(v12);
    v56[1] = v12;
  }
  v46 = a2 + 1;
  v13 = a2[1];
  v14 = *a2;
  if ( *a2 != v13 )
  {
    do
    {
      if ( (*(_BYTE *)(v14 + 4) & 2) == 0 )
      {
        LOBYTE(v10) = *(_BYTE *)(v14 + 32);
        v15 = (_QWORD *)(v14 + 56);
        if ( (unsigned int)MemoryManager::GetPrimaryRamBackingType(v5, v10) )
        {
          *((_QWORD *)v5 + 23) -= *v15;
        }
        else
        {
          std::vector<unsigned __int64>::_Emplace_one_at_back<unsigned __int64>(
            (char *)v56[0] + 88 * *(unsigned __int8 *)(v14 + 32) + 32,
            v14 + 64);
          std::vector<unsigned __int64>::_Emplace_one_at_back<unsigned __int64>(
            (char *)v56[0] + 88 * *(unsigned __int8 *)(v14 + 32) + 8,
            v14 + 56);
          v10 = *(unsigned __int8 *)(v14 + 32);
          *((_QWORD *)v58[0] + v10) += *v15;
          v6 += *v15;
        }
      }
      v14 += 112;
    }
    while ( v14 != v13 );
    v44 = v6;
  }
  for ( i = 0; ; ++i )
  {
    LODWORD(v41) = i;
    v17 = a4;
    if ( i >= (int)a4 )
      break;
    v18 = (char *)v5 + 184;
    if ( !*((_QWORD *)v5 + 23) )
      break;
    v49 = (char *)v5 + 184;
    *(_OWORD *)v60 = 0;
    v61 = 0;
    for ( j = 0; ; ++j )
    {
      v39 = j;
      if ( j >= v40 )
        break;
      if ( *((_QWORD *)v58[0] + j) )
      {
        v20 = 88LL * j;
        v42 = v20;
        *((_BYTE *)v56[0] + v20) = i == (_DWORD)v17 - 1;
        *((_BYTE *)v56[0] + v20 + 1) = j;
        *(_QWORD *)((char *)v56[0] + v20 + 56) = 0;
        *(_DWORD *)((char *)v56[0] + v20 + 64) = *(_DWORD *)(a3 + 8LL * i);
        *(_DWORD *)((char *)v56[0] + v20 + 68) = *(_DWORD *)(a3 + 8LL * i + 4);
        v21 = (char *)v56[0] + v20;
        v63 = 0;
        __ExceptionPtrCreate(&v63);
        __ExceptionPtrAssign(v21 + 72, &v63);
        __ExceptionPtrDestroy(&v63);
        try
        {
          v42 += (__int64)v56[0];
          *(_QWORD *)&v63 = v5;
          v52 = MemoryManager::ReserveRamMemoryThreadRoutine;
          v53 = 0;
          v54 = v48;
          std::thread::_Start<void (MemoryManager::*)(void *),MemoryManager *,MemoryManager::ReserveRamMemoryContext *>(
            v55,
            &v52,
            &v63,
            &v42);
          std::vector<std::thread>::push_back(v60, v55);
          std::thread::~thread((std::thread *)v55);
          LODWORD(v17) = a4;
        }
        catch ( ... )
        {
          v35 = (const void *)std::current_exception(v47);
          v36 = v39;
          __ExceptionPtrAssign((char *)v56[0] + 88 * v39 + 72, v35);
          __ExceptionPtrDestroy(v47);
          if ( (unsigned int)dword_1403A98D8 > 5 )
          {
            v39 = v36;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<1>>(
              (unsigned int)&dword_1403A98D8,
              (unsigned int)byte_14034F8E9,
              v37,
              v38,
              (__int64)&v39);
          }
          v7 = v43;
          i = v41;
          v18 = v49;
          v5 = v50;
          v45 = v51;
          break;
        }
      }
    }
    v22 = v60[0];
    v23 = v60[1];
    while ( v22 != v23 )
    {
      std::thread::join(v22);
      v22 = (std::thread *)((char *)v22 + 16);
    }
    std::vector<std::thread>::clear(v60);
    v62 = 0;
    __ExceptionPtrCreate(&v62);
    v24 = 0;
    v39 = 0;
    if ( v40 )
    {
      v25 = 0;
      v26 = v56[0];
      v27 = v40;
      do
      {
        if ( *((_QWORD *)v58[0] + v25) )
        {
          v28 = 88 * v25;
          if ( __ExceptionPtrToBool((char *)v26 + 88 * v25 + 72) )
            __ExceptionPtrAssign(&v62, (char *)v56[0] + v28 + 72);
          *((_QWORD *)v58[0] + v25) -= *(_QWORD *)((char *)v56[0] + v28 + 56);
          v26 = v56[0];
          v29 = *(_QWORD *)((char *)v56[0] + v28 + 56);
          v7 += v29;
          *(_QWORD *)v18 -= v29;
          v24 = v39;
        }
        v39 = ++v24;
        ++v25;
      }
      while ( v24 < v27 );
      v43 = v7;
      i = v41;
    }
    if ( __ExceptionPtrToBool(&v62) )
    {
      v33 = std::exception_ptr::exception_ptr((std::exception_ptr *)v47, (const struct std::exception_ptr *)&v62);
      std::rethrow_exception(v33);
LABEL_52:
      MemoryManager::TraceLoggingReserveMemoryFailure(v5, 2, v18, v7, -2147023446);
      v34 = wil::verify_hresult<long>(2147943850LL);
      wil::details::in1diag3::Throw_HrMsg(
        retaddr,
        (void *)0x106C,
        (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
        (const char *)v34,
        (int)"PageCountToReserve = %I64u, PageCountReserved = %I64u",
        v18,
        v7);
    }
    __ExceptionPtrDestroy(&v62);
    if ( v60[0] )
    {
      std::_Destroy_range<std::allocator<std::thread>>(v60[0]);
      std::_Deallocate<16>(v60[0], (v61 - (unsigned __int64)v60[0]) & 0xFFFFFFFFFFFFFFF0uLL);
    }
  }
  v18 = v44;
  if ( v44 != v7 )
    goto LABEL_52;
  v30 = *v46;
  for ( k = *v45; k != v30; k += 112 )
  {
    if ( (*(_BYTE *)(k + 4) & 2) == 0 )
    {
      LOBYTE(v17) = *(_BYTE *)(k + 32);
      if ( !(unsigned int)MemoryManager::GetPrimaryRamBackingType(v5, v17) )
        *(_QWORD *)(k + 72) = *(_QWORD *)(k + 56);
    }
  }
  if ( v56[0] )
  {
    std::_Destroy_range<std::allocator<MemoryManager::ReserveRamMemoryContext>>(v56[0]);
    std::_Deallocate<16>(v56[0], 8 * ((signed __int64)(v57 - (unsigned __int64)v56[0]) >> 3));
    *(_OWORD *)v56 = 0;
    v57 = 0;
  }
  return std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned int const,std::shared_ptr<MigrationTransferEndpointTarget>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned int const,std::shared_ptr<MigrationTransferEndpointTarget>>>>>>>(v58);
}

```

## disassembly

```asm
0x1402090a4  mov     r11, rsp
0x1402090a7  mov     [r11+20h], r9d
0x1402090ab  mov     [r11+18h], r8
0x1402090af  push    rbx
0x1402090b0  push    rsi
0x1402090b1  push    r12
0x1402090b3  push    r13
0x1402090b5  push    r14
0x1402090b7  push    r15
0x1402090b9  sub     rsp, 138h
0x1402090c0  mov     rax, cs:__security_cookie
0x1402090c7  xor     rax, rsp
0x1402090ca  mov     [rsp+168h+var_40], rax
0x1402090d2  mov     rsi, rdx
0x1402090d5  mov     [rsp+168h+var_100], rdx
0x1402090da  mov     r15, rcx
0x1402090dd  mov     [rsp+168h+var_D8], rcx
0x1402090e5  mov     [rsp+168h+var_D0], rdx
0x1402090ed  xor     eax, eax
0x1402090ef  xorps   xmm1, xmm1
0x1402090f2  movdqu  xmmword ptr [rsp+168h+var_90], xmm1
0x1402090fb  mov     [r11-80h], rax
0x1402090ff  xor     r12d, r12d
0x140209102  mov     [rsp+168h+var_108], r12
0x140209107  xor     r13d, r13d
0x14020910a  mov     [rsp+168h+var_110], r13
0x14020910f  movdqu  xmmword ptr [rsp+168h+var_A8], xmm1
0x140209118  mov     [r11-98h], rax
0x14020911f  call    ?GetVirtualNumaNodeCount@MemoryManager@@AEBAEXZ; MemoryManager::GetVirtualNumaNodeCount(void)
0x140209124  mov     [rsp+168h+var_127], al
0x140209128  mov     [rsp+168h+var_120], r13
0x14020912d  movzx   ebx, al
0x140209130  mov     rdx, [rsp+168h+var_90]
0x140209138  mov     rcx, [rsp+168h+var_90+8]
0x140209140  sub     rcx, rdx
0x140209143  sar     rcx, 3
0x140209147  cmp     rbx, rcx
0x14020914a  jnb     short loc_14020915A
0x14020914c  lea     rcx, [rdx+rbx*8]
0x140209150  mov     [rsp+168h+var_90+8], rcx
0x140209158  jmp     short loc_14020919F
0x14020915a  jbe     short loc_14020919F
0x14020915c  mov     rax, [rsp+168h+var_80]
0x140209164  sub     rax, rdx
0x140209167  sar     rax, 3
0x14020916b  lea     r8, [rsp+168h+var_120]
0x140209170  mov     rdx, rbx
0x140209173  cmp     rbx, rax
0x140209176  jbe     short loc_140209187
0x140209178  lea     rcx, [rsp+168h+var_90]
0x140209180  call    ??$_Resize_reallocate@PEBE@?$vector@PEBEV?$allocator@PEBE@std@@@std@@AEAAX_KAEBQEBE@Z; std::vector<uchar const *>::_Resize_reallocate<uchar const *>(unsigned __int64,uchar const * const &)
0x140209185  jmp     short loc_14020919F
0x140209187  sub     rdx, rcx
0x14020918a  mov     rcx, [rsp+168h+var_90+8]; void *
0x140209192  call    ??$_Uninitialized_fill_n@V?$allocator@_K@std@@@std@@YAPEA_KPEA_K_KAEB_KAEAV?$allocator@_K@0@@Z; std::_Uninitialized_fill_n<std::allocator<unsigned __int64>>(unsigned __int64 *,unsigned __int64,unsigned __int64 const &,std::allocator<unsigned __int64> &)
0x140209197  mov     [rsp+168h+var_90+8], rax
0x14020919f  mov     r8, [rsp+168h+var_A8]
0x1402091a7  mov     r9, [rsp+168h+var_A8+8]
0x1402091af  mov     rcx, r9
0x1402091b2  sub     rcx, r8
0x1402091b5  sar     rcx, 3
0x1402091b9  mov     rdx, 2E8BA2E8BA2E8BA3h
0x1402091c3  imul    rcx, rdx
0x1402091c7  cmp     rbx, rcx
0x1402091ca  jnb     short loc_1402091E8
0x1402091cc  imul    rbx, 58h ; 'X'
0x1402091d0  add     rbx, r8
0x1402091d3  mov     rdx, r9
0x1402091d6  mov     rcx, rbx; this
0x1402091d9  call    ??$_Destroy_range@V?$allocator@UReserveRamMemoryContext@MemoryManager@@@std@@@std@@YAXPEAUReserveRamMemoryContext@MemoryManager@@QEAU12@AEAV?$allocator@UReserveRamMemoryContext@MemoryManager@@@0@@Z; std::_Destroy_range<std::allocator<MemoryManager::ReserveRamMemoryContext>>(MemoryManager::ReserveRamMemoryContext *,MemoryManager::ReserveRamMemoryContext * const,std::allocator<MemoryManager::ReserveRamMemoryContext> &)
0x1402091de  mov     [rsp+168h+var_A8+8], rbx
0x1402091e6  jmp     short loc_14020922A
0x1402091e8  jbe     short loc_14020922A
0x1402091ea  mov     rax, [rsp+168h+var_98]
0x1402091f2  sub     rax, r8
0x1402091f5  sar     rax, 3
0x1402091f9  imul    rax, rdx
0x1402091fd  cmp     rbx, rax
0x140209200  jbe     short loc_140209214
0x140209202  mov     rdx, rbx
0x140209205  lea     rcx, [rsp+168h+var_A8]
0x14020920d  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@UReserveRamMemoryContext@MemoryManager@@V?$allocator@UReserveRamMemoryContext@MemoryManager@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<MemoryManager::ReserveRamMemoryContext>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x140209212  jmp     short loc_14020922A
0x140209214  sub     rbx, rcx
0x140209217  mov     rdx, rbx
0x14020921a  mov     rcx, r9; this
0x14020921d  call    ??$_Uninitialized_value_construct_n@V?$allocator@UReserveRamMemoryContext@MemoryManager@@@std@@@std@@YAPEAUReserveRamMemoryContext@MemoryManager@@PEAU12@_KAEAV?$allocator@UReserveRamMemoryContext@MemoryManager@@@0@@Z; std::_Uninitialized_value_construct_n<std::allocator<MemoryManager::ReserveRamMemoryContext>>(MemoryManager::ReserveRamMemoryContext *,unsigned __int64,std::allocator<MemoryManager::ReserveRamMemoryContext> &)
0x140209222  mov     [rsp+168h+var_A8+8], rax
0x14020922a  lea     rax, [rsi+8]
0x14020922e  mov     [rsp+168h+var_F8], rax
0x140209233  mov     r14, [rax]
0x140209236  mov     rbx, [rsi]
0x140209239  cmp     rbx, r14
0x14020923c  jz      loc_1402092CE
0x140209242  test    byte ptr [rbx+4], 2
0x140209246  jnz     short loc_1402092BC
0x140209248  mov     dl, [rbx+20h]
0x14020924b  mov     rcx, r15
0x14020924e  call    ?GetPrimaryRamBackingType@MemoryManager@@AEBA?AW4MemoryBackingType@Compute@Resources@VirtualMachines@Schema@@E@Z; MemoryManager::GetPrimaryRamBackingType(uchar)
0x140209253  lea     rsi, [rbx+38h]
0x140209257  test    eax, eax
0x140209259  jz      short loc_140209267
0x14020925b  mov     rax, [rsi]
0x14020925e  sub     [r15+0B8h], rax
0x140209265  jmp     short loc_1402092BC
0x140209267  lea     rdx, [rbx+40h]
0x14020926b  movzx   eax, byte ptr [rbx+20h]
0x14020926f  imul    rcx, rax, 58h ; 'X'
0x140209273  mov     rax, [rsp+168h+var_A8]
0x14020927b  add     rax, 20h ; ' '
0x14020927f  add     rcx, rax
0x140209282  call    ??$_Emplace_one_at_back@_K@?$vector@_KV?$allocator@_K@std@@@std@@AEAAAEA_K$$QEA_K@Z; std::vector<unsigned __int64>::_Emplace_one_at_back<unsigned __int64>(unsigned __int64 &&)
0x140209287  movzx   eax, byte ptr [rbx+20h]
0x14020928b  imul    rcx, rax, 58h ; 'X'
0x14020928f  mov     rax, [rsp+168h+var_A8]
0x140209297  add     rax, 8
0x14020929b  add     rcx, rax
0x14020929e  mov     rdx, rsi
0x1402092a1  call    ??$_Emplace_one_at_back@_K@?$vector@_KV?$allocator@_K@std@@@std@@AEAAAEA_K$$QEA_K@Z; std::vector<unsigned __int64>::_Emplace_one_at_back<unsigned __int64>(unsigned __int64 &&)
0x1402092a6  movzx   edx, byte ptr [rbx+20h]
0x1402092aa  mov     rcx, [rsp+168h+var_90]
0x1402092b2  mov     rax, [rsi]
0x1402092b5  add     [rcx+rdx*8], rax
0x1402092b9  add     r12, [rsi]
0x1402092bc  add     rbx, 70h ; 'p'
0x1402092c0  cmp     rbx, r14
0x1402092c3  jnz     loc_140209242
0x1402092c9  mov     [rsp+168h+var_108], r12
0x1402092ce  xor     r14d, r14d
0x1402092d1  mov     dword ptr [rsp+168h+var_120], r14d
0x1402092d6  mov     edx, [rsp+168h+arg_18]
0x1402092dd  cmp     r14d, edx
0x1402092e0  jge     loc_14020963A
0x1402092e6  lea     r12, [r15+0B8h]
0x1402092ed  cmp     qword ptr [r12], 0
0x1402092f2  jz      loc_14020963A
0x1402092f8  mov     [rsp+168h+var_E0], r12
0x140209300  xor     eax, eax
0x140209302  xorps   xmm1, xmm1
0x140209305  movdqu  xmmword ptr [rsp+168h+var_78], xmm1
0x14020930e  mov     [rsp+168h+var_68], rax
0x140209316  xor     sil, sil
0x140209319  mov     [rsp+168h+var_128], sil
0x14020931e  cmp     sil, [rsp+168h+var_127]
0x140209323  jnb     loc_1402094C1
0x140209329  movzx   ecx, sil
0x14020932d  mov     rax, [rsp+168h+var_90]
0x140209335  cmp     qword ptr [rax+rcx*8], 0
0x14020933a  jz      loc_140209492
0x140209340  imul    r8, rcx, 58h ; 'X'
0x140209344  mov     [rsp+168h+var_118], r8
0x140209349  lea     eax, [rdx-1]
0x14020934c  cmp     r14d, eax
0x14020934f  setz    cl
0x140209352  mov     rax, [rsp+168h+var_A8]
0x14020935a  mov     [rax+r8], cl
0x14020935e  mov     rax, [rsp+168h+var_A8]
0x140209366  mov     [rax+r8+1], sil
0x14020936b  mov     rax, [rsp+168h+var_A8]
0x140209373  mov     qword ptr [rax+r8+38h], 0
0x14020937c  movsxd  rdx, r14d
0x14020937f  mov     r9, [rsp+168h+arg_10]
0x140209387  mov     ecx, [r9+rdx*8]
0x14020938b  mov     rax, [rsp+168h+var_A8]
0x140209393  mov     [rax+r8+40h], ecx
0x140209398  mov     ecx, [r9+rdx*8+4]
0x14020939d  mov     rax, [rsp+168h+var_A8]
0x1402093a5  mov     [rax+r8+44h], ecx
0x1402093aa  mov     rbx, [rsp+168h+var_A8]
0x1402093b2  add     rbx, r8
0x1402093b5  xorps   xmm0, xmm0
0x1402093b8  movdqu  [rsp+168h+var_50], xmm0
0x1402093c1  lea     rcx, [rsp+168h+var_50]
0x1402093c9  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x1402093d0  nop     dword ptr [rax+rax+00h]
0x1402093d5  lea     rdx, [rsp+168h+var_50]
0x1402093dd  lea     rcx, [rbx+48h]
0x1402093e1  call    cs:__imp_?__ExceptionPtrAssign@@YAXPEAXPEBX@Z; __ExceptionPtrAssign(void *,void const *)
0x1402093e8  nop     dword ptr [rax+rax+00h]
0x1402093ed  lea     rcx, [rsp+168h+var_50]
0x1402093f5  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x1402093fc  nop     dword ptr [rax+rax+00h]
0x140209401  nop
0x140209402  mov     rcx, [rsp+168h+var_118]
0x140209407  add     rcx, [rsp+168h+var_A8]
0x14020940f  mov     [rsp+168h+var_118], rcx
0x140209414  mov     qword ptr [rsp+168h+var_50], r15
0x14020941c  lea     rax, ?ReserveRamMemoryThreadRoutine@MemoryManager@@AEAAXPEAX@Z; MemoryManager::ReserveRamMemoryThreadRoutine(void *)
0x140209423  mov     [rsp+168h+var_C8], rax
0x14020942b  mov     [rsp+168h+var_C0], 0
0x140209436  mov     eax, [rsp+168h+var_E4]
0x14020943d  mov     [rsp+168h+var_BC], eax
0x140209444  lea     r9, [rsp+168h+var_118]
0x140209449  lea     r8, [rsp+168h+var_50]
0x140209451  lea     rdx, [rsp+168h+var_C8]
0x140209459  lea     rcx, [rsp+168h+var_B8]
0x140209461  call    ??$_Start@P8MemoryManager@@EAAXPEAX@ZPEAV1@PEAUReserveRamMemoryContext@1@@thread@std@@AEAAX$$QEAP8MemoryManager@@EAAXPEAX@Z$$QEAPEAV2@$$QEAPEAUReserveRamMemoryContext@2@@Z; std::thread::_Start<void (MemoryManager::*)(void *),MemoryManager *,MemoryManager::ReserveRamMemoryContext *>(void (MemoryManager::*&&)(void *),MemoryManager * &&,MemoryManager::ReserveRamMemoryContext * &&)
0x140209466  nop
0x140209467  lea     rdx, [rsp+168h+var_B8]
0x14020946f  lea     rcx, [rsp+168h+var_78]
0x140209477  call    ?push_back@?$vector@Vthread@std@@V?$allocator@Vthread@std@@@2@@std@@QEAAX$$QEAVthread@2@@Z; std::vector<std::thread>::push_back(std::thread &&)
0x14020947c  nop
0x14020947d  lea     rcx, [rsp+168h+var_B8]; this
0x140209485  call    ??1thread@std@@QEAA@XZ; std::thread::~thread(void)
0x14020948a  nop
0x14020948b  mov     edx, [rsp+168h+arg_18]
0x140209492  inc     sil
0x140209495  jmp     loc_140209319
0x14020949a  mov     r13, [rsp+168h+var_110]
0x14020949f  mov     r14d, dword ptr [rsp+168h+var_120]
0x1402094a4  mov     r12, [rsp+168h+var_E0]
0x1402094ac  mov     r15, [rsp+168h+var_D8]
0x1402094b4  mov     rax, [rsp+168h+var_D0]
0x1402094bc  mov     [rsp+168h+var_100], rax
0x1402094c1  mov     rbx, [rsp+168h+var_78]
0x1402094c9  mov     rsi, [rsp+168h+var_78+8]
0x1402094d1  jmp     short loc_1402094DF
0x1402094d3  mov     rcx, rbx; this
0x1402094d6  call    ?join@thread@std@@QEAAXXZ; std::thread::join(void)
0x1402094db  add     rbx, 10h
0x1402094df  cmp     rbx, rsi
0x1402094e2  jnz     short loc_1402094D3
0x1402094e4  lea     rcx, [rsp+168h+var_78]
0x1402094ec  call    ?clear@?$vector@Vthread@std@@V?$allocator@Vthread@std@@@2@@std@@QEAAXXZ; std::vector<std::thread>::clear(void)
0x1402094f1  xorps   xmm1, xmm1
0x1402094f4  movdqu  [rsp+168h+var_60], xmm1
0x1402094fd  lea     rcx, [rsp+168h+var_60]
0x140209505  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x14020950c  nop     dword ptr [rax+rax+00h]
0x140209511  nop
0x140209512  xor     cl, cl
0x140209514  mov     [rsp+168h+var_128], cl
0x140209518  cmp     [rsp+168h+var_127], cl
0x14020951c  jbe     loc_1402095CB
0x140209522  xor     ebx, ebx
0x140209524  mov     rdx, [rsp+168h+var_A8]
0x14020952c  mov     r14b, [rsp+168h+var_127]
0x140209531  mov     rax, [rsp+168h+var_90]
0x140209539  cmp     qword ptr [rax+rbx*8], 0
0x14020953e  jz      short loc_1402095AF
0x140209540  imul    rsi, rbx, 58h ; 'X'
0x140209544  lea     rcx, [rdx+48h]
0x140209548  add     rcx, rsi
0x14020954b  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x140209552  nop     dword ptr [rax+rax+00h]
0x140209557  test    al, al
0x140209559  jz      short loc_14020957E
0x14020955b  mov     rdx, [rsp+168h+var_A8]
0x140209563  add     rdx, 48h ; 'H'
0x140209567  add     rdx, rsi
0x14020956a  lea     rcx, [rsp+168h+var_60]
0x140209572  call    cs:__imp_?__ExceptionPtrAssign@@YAXPEAXPEBX@Z; __ExceptionPtrAssign(void *,void const *)
0x140209579  nop     dword ptr [rax+rax+00h]
0x14020957e  mov     rdx, [rsp+168h+var_90]
0x140209586  mov     rax, [rsp+168h+var_A8]
0x14020958e  mov     rcx, [rsi+rax+38h]
0x140209593  sub     [rdx+rbx*8], rcx
0x140209597  mov     rdx, [rsp+168h+var_A8]
0x14020959f  mov     rax, [rsi+rdx+38h]
0x1402095a4  add     r13, rax
0x1402095a7  sub     [r12], rax
0x1402095ab  mov     cl, [rsp+168h+var_128]
0x1402095af  inc     cl
0x1402095b1  mov     [rsp+168h+var_128], cl
0x1402095b5  inc     rbx
0x1402095b8  cmp     cl, r14b
0x1402095bb  jb      loc_140209531
0x1402095c1  mov     [rsp+168h+var_110], r13
0x1402095c6  mov     r14d, dword ptr [rsp+168h+var_120]
0x1402095cb  lea     rcx, [rsp+168h+var_60]
0x1402095d3  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x1402095da  nop     dword ptr [rax+rax+00h]
0x1402095df  test    al, al
0x1402095e1  jnz     loc_140209712
0x1402095e7  lea     rcx, [rsp+168h+var_60]
0x1402095ef  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x1402095f6  nop     dword ptr [rax+rax+00h]
0x1402095fb  nop
0x1402095fc  mov     rcx, [rsp+168h+var_78]; this
0x140209604  test    rcx, rcx
0x140209607  jz      short loc_140209632
0x140209609  mov     rdx, [rsp+168h+var_78+8]
0x140209611  call    ??$_Destroy_range@V?$allocator@Vthread@std@@@std@@@std@@YAXPEAVthread@0@QEAV10@AEAV?$allocator@Vthread@std@@@0@@Z; std::_Destroy_range<std::allocator<std::thread>>(std::thread *,std::thread * const,std::allocator<std::thread> &)
0x140209616  mov     rcx, [rsp+168h+var_78]
0x14020961e  mov     rdx, [rsp+168h+var_68]
0x140209626  sub     rdx, rcx
0x140209629  and     rdx, 0FFFFFFFFFFFFFFF0h
0x14020962d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x140209632  inc     r14d
0x140209635  jmp     loc_1402092D1
0x14020963a  mov     r12, [rsp+168h+var_108]
0x14020963f  cmp     r12, r13
0x140209642  jnz     loc_14020972D
0x140209648  mov     r9, [rsp+168h+var_F8]
0x14020964d  mov     r9, [r9]
0x140209650  mov     r8, [rsp+168h+var_100]
0x140209655  mov     r8, [r8]
0x140209658  jmp     short loc_14020967D
0x14020965a  test    byte ptr [r8+4], 2
0x14020965f  jnz     short loc_140209679
  ... truncated ...
```
