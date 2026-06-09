# _anonymous_namespace_::ServiceLifetimeManager::AddSession

- ea: `0x1400051d0`
- end: `0x1400053f7`
- name: `_anonymous_namespace_::ServiceLifetimeManager::AddSession`
- size: `551`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400051d0`
- `0x140006c80`
- `0x140006ed0`
- `0x14000a278`
- `0x140013834`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x1400053f0`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140005200`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140005200`
- `KERNEL32!IsThreadpoolTimerSet` at `0x1400053b0`
- `KERNEL32!IsThreadpoolTimerSet` at `0x1400053b0`
- `KERNEL32!SetThreadpoolTimer` at `0x1400053c6`
- `KERNEL32!SetThreadpoolTimer` at `0x1400053c6`
- `MSVCP140!?_Xlength_error@std@@YAXPEBD@Z` at `0x14000528f`
- `MSVCP140!?_Xlength_error@std@@YAXPEBD@Z` at `0x14000528f`

## string_xrefs

- `0x140005394`: `D:\a\_work\1\s\sources\Base\Collection\StandardCollector.Service\StandardCollectorHost.cpp`
- `0x14000538d`: `New collection session. Cancelling service shutdown`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall anonymous_namespace_::ServiceLifetimeManager::AddSession(__int64 a1, _OWORD *a2)
{
  RTL_SRWLOCK *v4; // r13
  __int64 v5; // rsi
  __int64 v6; // rcx
  unsigned __int64 i; // rdx
  unsigned __int64 j; // rdx
  __int64 v9; // rsi
  _OWORD *v10; // rbx
  __int64 v11; // rcx
  float v12; // xmm0_4
  __int64 v13; // rcx
  float v14; // xmm1_4
  __int64 v15; // rax
  __int64 v16; // rdx
  _QWORD *v17; // r8
  __int64 v18; // rax
  __int64 v19; // rcx
  __int64 v20; // r9
  struct _TP_TIMER *v21; // rcx
  __int128 v22; // [rsp+20h] [rbp-58h] BYREF
  __int64 v23; // [rsp+30h] [rbp-48h] BYREF
  _OWORD *v24; // [rsp+38h] [rbp-40h]
  PSRWLOCK v25; // [rsp+40h] [rbp-38h]
  int v26; // [rsp+48h] [rbp-30h]

  v4 = (RTL_SRWLOCK *)(a1 + 40);
  v25 = (PSRWLOCK)(a1 + 40);
  v26 = 1;
  AcquireSRWLockExclusive((PSRWLOCK)(a1 + 40));
  v5 = 0xCBF29CE484222325uLL;
  v6 = 0xCBF29CE484222325uLL;
  for ( i = 0; i < 8; ++i )
    v6 = 0x100000001B3LL * (*((unsigned __int8 *)a2 + i) ^ (unsigned __int64)v6);
  for ( j = 0; j < 8; ++j )
    v5 = 0x100000001B3LL * (*((unsigned __int8 *)a2 + j + 8) ^ (unsigned __int64)v5);
  v9 = v6 ^ v5;
  std::_Hash<std::_Uset_traits<_GUID,std::_Uhash_compare<_GUID,DiagHubCommon::GuidHash,DiagHubCommon::GuidEqualTo>,std::allocator<_GUID>,0>>::_Find_last<_GUID>(
    a1 + 48,
    &v22,
    a2,
    v9);
  if ( *((_QWORD *)&v22 + 1) )
    goto LABEL_29;
  try
  {
    if ( *(_QWORD *)(a1 + 64) == 0x7FFFFFFFFFFFFFFLL )
      std::_Xlength_error("unordered_map/set too long");
    v23 = a1 + 56;
    v24 = 0;
    v10 = operator new(0x20u);
    v24 = v10;
    v10[1] = *a2;
    v11 = *(_QWORD *)(a1 + 64) + 1LL;
    if ( v11 < 0 )
      v12 = (float)(v11 & 1 | (unsigned int)((unsigned __int64)v11 >> 1))
          + (float)(v11 & 1 | (unsigned int)((unsigned __int64)v11 >> 1));
    else
      v12 = (float)(int)v11;
    v13 = *(_QWORD *)(a1 + 104);
    if ( v13 < 0 )
    {
      v15 = *(_QWORD *)(a1 + 104) & 1LL | ((unsigned __int64)v13 >> 1);
      v14 = (float)(int)v15 + (float)(int)v15;
    }
    else
    {
      v14 = (float)(int)v13;
    }
    if ( (float)(v12 / v14) > *(float *)(a1 + 48) )
    {
      std::_Hash<std::_Uset_traits<_GUID,std::_Uhash_compare<_GUID,DiagHubCommon::GuidHash,DiagHubCommon::GuidEqualTo>,std::allocator<_GUID>,0>>::_Rehash_for_1(a1 + 48);
      v22 = *(_OWORD *)std::_Hash<std::_Uset_traits<_GUID,std::_Uhash_compare<_GUID,DiagHubCommon::GuidHash,DiagHubCommon::GuidEqualTo>,std::allocator<_GUID>,0>>::_Find_last<_GUID>(
                         a1 + 48,
                         &v23,
                         v10 + 1,
                         v9);
    }
    v16 = v22;
    v17 = *(_QWORD **)(v22 + 8);
    ++*(_QWORD *)(a1 + 64);
    *(_QWORD *)v10 = v16;
    *((_QWORD *)v10 + 1) = v17;
    *v17 = v10;
    *(_QWORD *)(v16 + 8) = v10;
    v18 = 2 * (v9 & *(_QWORD *)(a1 + 96));
    v19 = *(_QWORD *)(a1 + 72);
    v20 = *(_QWORD *)(v19 + 16 * (v9 & *(_QWORD *)(a1 + 96)));
    if ( v20 == *(_QWORD *)(a1 + 56) )
    {
      *(_QWORD *)(v19 + 16 * (v9 & *(_QWORD *)(a1 + 96))) = v10;
LABEL_22:
      *(_QWORD *)(v19 + 8 * v18 + 8) = v10;
      goto LABEL_29;
    }
    if ( v20 == v16 )
    {
      *(_QWORD *)(v19 + 16 * (v9 & *(_QWORD *)(a1 + 96))) = v10;
      goto LABEL_29;
    }
    if ( *(_QWORD **)(v19 + 16 * (v9 & *(_QWORD *)(a1 + 96)) + 8) == v17 )
      goto LABEL_22;
  }
  catch ( std::bad_alloc )
  {
    ReleaseSRWLockExclusive(v25);
    return;
  }
LABEL_29:
  DiagHubCommon::LogStream::Write(
    _logger,
    L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Service\\StandardCollectorHost.cpp",
    L"New collection session. Cancelling service shutdown");
  v21 = *(struct _TP_TIMER **)(a1 + 24);
  if ( v21 && IsThreadpoolTimerSet(v21) )
    SetThreadpoolTimer(*(PTP_TIMER *)(a1 + 24), 0, 0, 0);
  ReleaseSRWLockExclusive(v4);
}

```

## disassembly

```asm
0x1400051d0  mov     rax, rsp
0x1400051d3  mov     [rax+18h], rbx
0x1400051d7  mov     [rax+20h], rsi
0x1400051db  push    rdi
0x1400051dc  push    r12
0x1400051de  push    r13
0x1400051e0  push    r14
0x1400051e2  push    r15
0x1400051e4  sub     rsp, 50h
0x1400051e8  mov     r14, rdx
0x1400051eb  mov     r15, rcx
0x1400051ee  lea     r13, [rcx+28h]
0x1400051f2  mov     [rax-38h], r13
0x1400051f6  mov     dword ptr [rax-30h], 1
0x1400051fd  mov     rcx, r13; SRWLock
0x140005200  call    cs:__imp_AcquireSRWLockExclusive
0x140005206  nop
0x140005207  lea     rdi, [r15+30h]
0x14000520b  mov     rsi, 0CBF29CE484222325h
0x140005215  mov     rcx, rsi
0x140005218  xor     edx, edx
0x14000521a  mov     r8, 100000001B3h
0x140005224  movzx   eax, byte ptr [r14+rdx]
0x140005229  xor     rcx, rax
0x14000522c  imul    rcx, r8
0x140005230  inc     rdx
0x140005233  cmp     rdx, 8
0x140005237  jb      short loc_140005224
0x140005239  xor     edx, edx
0x14000523b  movzx   eax, byte ptr [r14+rdx+8]
0x140005241  xor     rsi, rax
0x140005244  imul    rsi, r8
0x140005248  inc     rdx
0x14000524b  cmp     rdx, 8
0x14000524f  jb      short loc_14000523B
0x140005251  xor     rsi, rcx
0x140005254  mov     r9, rsi
0x140005257  mov     r8, r14
0x14000525a  lea     rdx, [rsp+78h+var_58]
0x14000525f  mov     rcx, rdi
0x140005262  call    ??$_Find_last@U_GUID@@@?$_Hash@V?$_Uset_traits@U_GUID@@V?$_Uhash_compare@U_GUID@@UGuidHash@DiagHubCommon@@UGuidEqualTo@3@@std@@V?$allocator@U_GUID@@@3@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U_GUID@@PEAX@std@@@1@AEBU_GUID@@_K@Z; std::_Hash<std::_Uset_traits<_GUID,std::_Uhash_compare<_GUID,DiagHubCommon::GuidHash,DiagHubCommon::GuidEqualTo>,std::allocator<_GUID>,0>>::_Find_last<_GUID>(_GUID const &,unsigned __int64)
0x140005267  cmp     qword ptr [rsp+78h+var_58+8], 0
0x14000526d  jnz     loc_14000538D
0x140005273  lea     r12, [rdi+8]
0x140005277  mov     rax, 7FFFFFFFFFFFFFFh
0x140005281  cmp     [r12+8], rax
0x140005286  jnz     short loc_140005295
0x140005288  lea     rcx, aUnorderedMapSe; "unordered_map/set too long"
0x14000528f  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x140005295  mov     [rsp+78h+var_48], r12
0x14000529a  mov     [rsp+78h+var_40], 0
0x1400052a3  mov     ecx, 20h ; ' '; Size
0x1400052a8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400052ad  mov     rbx, rax
0x1400052b0  mov     [rsp+78h+var_40], rax
0x1400052b5  movups  xmm0, xmmword ptr [r14]
0x1400052b9  movdqu  xmmword ptr [rax+10h], xmm0
0x1400052be  mov     rcx, [rdi+10h]
0x1400052c2  add     rcx, 1
0x1400052c6  xorps   xmm0, xmm0
0x1400052c9  js      short loc_1400052D2
0x1400052cb  cvtsi2ss xmm0, rcx
0x1400052d0  jmp     short loc_1400052E7
0x1400052d2  mov     rax, rcx
0x1400052d5  shr     rax, 1
0x1400052d8  and     ecx, 1
0x1400052db  or      rax, rcx
0x1400052de  cvtsi2ss xmm0, rax
0x1400052e3  addss   xmm0, xmm0
0x1400052e7  mov     rcx, [rdi+38h]
0x1400052eb  xorps   xmm1, xmm1
0x1400052ee  test    rcx, rcx
0x1400052f1  js      short loc_1400052FA
0x1400052f3  cvtsi2ss xmm1, rcx
0x1400052f8  jmp     short loc_14000530F
0x1400052fa  mov     rax, rcx
0x1400052fd  shr     rax, 1
0x140005300  and     ecx, 1
0x140005303  or      rax, rcx
0x140005306  cvtsi2ss xmm1, rax
0x14000530b  addss   xmm1, xmm1
0x14000530f  divss   xmm0, xmm1
0x140005313  comiss  xmm0, dword ptr [rdi]
0x140005316  jbe     short loc_14000533D
0x140005318  mov     rcx, rdi
0x14000531b  call    ?_Rehash_for_1@?$_Hash@V?$_Uset_traits@U_GUID@@V?$_Uhash_compare@U_GUID@@UGuidHash@DiagHubCommon@@UGuidEqualTo@3@@std@@V?$allocator@U_GUID@@@3@$0A@@std@@@std@@IEAAXXZ; std::_Hash<std::_Uset_traits<_GUID,std::_Uhash_compare<_GUID,DiagHubCommon::GuidHash,DiagHubCommon::GuidEqualTo>,std::allocator<_GUID>,0>>::_Rehash_for_1(void)
0x140005320  mov     r9, rsi
0x140005323  lea     r8, [rbx+10h]
0x140005327  lea     rdx, [rsp+78h+var_48]
0x14000532c  mov     rcx, rdi
0x14000532f  call    ??$_Find_last@U_GUID@@@?$_Hash@V?$_Uset_traits@U_GUID@@V?$_Uhash_compare@U_GUID@@UGuidHash@DiagHubCommon@@UGuidEqualTo@3@@std@@V?$allocator@U_GUID@@@3@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U_GUID@@PEAX@std@@@1@AEBU_GUID@@_K@Z; std::_Hash<std::_Uset_traits<_GUID,std::_Uhash_compare<_GUID,DiagHubCommon::GuidHash,DiagHubCommon::GuidEqualTo>,std::allocator<_GUID>,0>>::_Find_last<_GUID>(_GUID const &,unsigned __int64)
0x140005334  movups  xmm0, xmmword ptr [rax]
0x140005337  movdqu  [rsp+78h+var_58], xmm0
0x14000533d  mov     rdx, qword ptr [rsp+78h+var_58]
0x140005342  mov     r8, [rdx+8]
0x140005346  inc     qword ptr [rdi+10h]
0x14000534a  mov     [rbx], rdx
0x14000534d  mov     [rbx+8], r8
0x140005351  mov     [r8], rbx
0x140005354  mov     [rdx+8], rbx
0x140005358  mov     rax, [rdi+30h]
0x14000535c  and     rax, rsi
0x14000535f  add     rax, rax
0x140005362  mov     rcx, [rdi+18h]
0x140005366  mov     r9, [rcx+rax*8]
0x14000536a  cmp     r9, [r12]
0x14000536e  jnz     short loc_140005376
0x140005370  mov     [rcx+rax*8], rbx
0x140005374  jmp     short loc_140005388
0x140005376  cmp     r9, rdx
0x140005379  jnz     short loc_140005381
0x14000537b  mov     [rcx+rax*8], rbx
0x14000537f  jmp     short loc_14000538D
0x140005381  cmp     [rcx+rax*8+8], r8
0x140005386  jnz     short loc_14000538D
0x140005388  mov     [rcx+rax*8+8], rbx
0x14000538d  lea     r8, aNewCollectionS; "New collection session. Cancelling serv"...
0x140005394  lea     rdx, aDAWork1SSource_0; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x14000539b  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; this
0x1400053a2  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x1400053a7  mov     rcx, [r15+18h]; pti
0x1400053ab  test    rcx, rcx
0x1400053ae  jz      short loc_1400053CD
0x1400053b0  call    cs:__imp_IsThreadpoolTimerSet
0x1400053b6  test    eax, eax
0x1400053b8  jz      short loc_1400053CD
0x1400053ba  xor     r9d, r9d; msWindowLength
0x1400053bd  xor     r8d, r8d; msPeriod
0x1400053c0  xor     edx, edx; pftDueTime
0x1400053c2  mov     rcx, [r15+18h]; pti
0x1400053c6  call    cs:__imp_SetThreadpoolTimer
0x1400053cc  nop
0x1400053cd  mov     rcx, r13
0x1400053d0  jmp     short loc_1400053D7
0x1400053d2  mov     rcx, [rsp+78h+var_38]
0x1400053d7  lea     r11, [rsp+78h+var_28]
0x1400053dc  mov     rbx, [r11+40h]
0x1400053e0  mov     rsi, [r11+48h]
0x1400053e4  mov     rsp, r11
0x1400053e7  pop     r15
0x1400053e9  pop     r14
0x1400053eb  pop     r13
0x1400053ed  pop     r12
0x1400053ef  pop     rdi
0x1400053f0  jmp     cs:__imp_ReleaseSRWLockExclusive
```
