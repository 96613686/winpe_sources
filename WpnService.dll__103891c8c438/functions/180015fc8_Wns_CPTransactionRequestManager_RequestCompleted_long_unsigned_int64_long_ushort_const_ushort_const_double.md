# Wns::CPTransactionRequestManager::RequestCompleted(long,unsigned __int64,long,ushort const *,ushort const *,double)

- ea: `0x180015fc8`
- end: `0x1800161ba`
- name: `?RequestCompleted@CPTransactionRequestManager@Wns@@AEAAXJ_KJPEBG1N@Z`
- size: `498`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this, int, __int64, int, unsigned __int16 *, unsigned __int16 *, double)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180015f48`
- `0x180020b74`

## callees

- `0x180004c4c`
- `0x1800156dc`
- `0x180015fc8`
- `0x1800161c0`
- `0x180017060`
- `0x1800239ec`
- `0x180031c5c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016007`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016007`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016128`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016128`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall Wns::CPTransactionRequestManager::RequestCompleted(
        struct _RTL_CRITICAL_SECTION *this,
        int a2,
        __int64 a3,
        int a4,
        unsigned __int16 *a5,
        unsigned __int16 *a6,
        double a7)
{
  __m128i v11; // xmm6
  __int64 v12; // rbx
  struct _RTL_CRITICAL_SECTION *v13; // r13
  unsigned __int64 v14; // rdx
  __int64 v15; // r8
  char v16; // r12
  __int64 v17; // rax
  ULONG_PTR SpinCount; // rcx
  char *OwningThread; // r8
  bool v20; // zf
  unsigned __int64 v21; // rbp
  PRTL_CRITICAL_SECTION_DEBUG i; // rsi
  const char *v23; // [rsp+30h] [rbp-68h]
  _BYTE v24[16]; // [rsp+40h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]
  __int64 v26; // [rsp+A0h] [rbp+8h] BYREF
  int v27; // [rsp+A8h] [rbp+10h]
  int v28; // [rsp+B8h] [rbp+20h]

  v28 = a4;
  v27 = a2;
  v11 = 0;
  v12 = 0;
  v26 = 0;
  v13 = this + 6;
  EnterCriticalSection(this + 6);
  v14 = 0;
  v15 = 0xCBF29CE484222325uLL;
  v16 = 1;
  do
    v15 = 0x100000001B3LL * (*((unsigned __int8 *)&v28 + v14++) ^ (unsigned __int64)v15);
  while ( v14 < 4 );
  v17 = 2 * (v15 & (__int64)this[1].OwningThread);
  SpinCount = this->SpinCount;
  OwningThread = *(char **)(SpinCount + 16 * (v15 & (__int64)this[1].OwningThread) + 8);
  if ( OwningThread == this->OwningThread )
  {
LABEL_7:
    OwningThread = 0;
  }
  else
  {
    while ( a4 != *((_DWORD *)OwningThread + 4) )
    {
      if ( OwningThread == *(char **)(SpinCount + 8 * v17) )
        goto LABEL_7;
      OwningThread = (char *)*((_QWORD *)OwningThread + 1);
    }
  }
  if ( !OwningThread )
    OwningThread = (char *)this->OwningThread;
  if ( OwningThread == this->OwningThread )
  {
    v16 = 0;
    v21 = 0;
  }
  else
  {
    v11 = *(__m128i *)(OwningThread + 24);
    std::_Hash<std::_Umap_traits<long,Wns::ChannelRequestContext,std::_Uhash_compare<long,std::hash<long>,std::equal_to<long>>,std::allocator<std::pair<long const,Wns::ChannelRequestContext>>,0>>::erase<std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<long const,Wns::ChannelRequestContext>>>>,0>(
      &this->LockCount,
      v24);
    v20 = a2 == -2147023436;
    v21 = v11.m128i_i64[0];
    if ( !v20 )
      wil::details::in1diag3::Log_HrIfFalseMsg(
        retaddr,
        (void *)0x1D2,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\mux\\cptransactionrequestmanager.cpp",
        (const char *)0x8000FFFFLL,
        v11.m128i_i64[0] == a3,
        (bool)"Fishiness: why are we getting a different userId?",
        v23);
  }
  for ( i = this[2].DebugInfo;
        i != *(PRTL_CRITICAL_SECTION_DEBUG *)&this[2].LockCount;
        i = (PRTL_CRITICAL_SECTION_DEBUG)((char *)i + 8) )
  {
    if ( *(_DWORD *)(*(_QWORD *)&i->Type + 16LL) == a4 )
    {
      std::unique_ptr<Wns::CPTransactionRequestManager::TimerContext>::operator=<std::default_delete<Wns::CPTransactionRequestManager::TimerContext>,0>(
        &v26,
        i);
      std::vector<std::unique_ptr<Wns::CPTransactionRequestManager::TimerContext>>::erase(&this[2], v24, i);
      v12 = v26;
      break;
    }
  }
  if ( v13 )
    LeaveCriticalSection(v13);
  v26 = 0;
  if ( v12 )
    std::default_delete<Wns::Callback>::operator()(SpinCount, v12);
  if ( v16 )
    Wns::ConnectionMultiplexer::OnChannelReceived(
      *(Wns::ConnectionMultiplexer **)(this[5].SpinCount + 360),
      v27,
      v21,
      _mm_cvtsi128_si32(_mm_srli_si128(v11, 8)),
      a5,
      a6,
      a7);
}

```

## disassembly

```asm
0x180015fc8  mov     rax, rsp
0x180015fcb  mov     [rax+18h], rbx
0x180015fcf  mov     [rax+20h], r9d
0x180015fd3  mov     [rax+10h], edx
0x180015fd6  push    rbp
0x180015fd7  push    rsi
0x180015fd8  push    rdi
0x180015fd9  push    r12
0x180015fdb  push    r13
0x180015fdd  push    r14
0x180015fdf  push    r15
0x180015fe1  sub     rsp, 60h
0x180015fe5  movaps  xmmword ptr [rax-48h], xmm6
0x180015fe9  mov     edi, r9d
0x180015fec  mov     rsi, r8
0x180015fef  mov     ebp, edx
0x180015ff1  mov     r15, rcx
0x180015ff4  xorps   xmm6, xmm6
0x180015ff7  xor     ebx, ebx
0x180015ff9  mov     [rax+8], rbx
0x180015ffd  lea     r13, [rcx+0F0h]
0x180016004  mov     rcx, r13; lpCriticalSection
0x180016007  call    cs:__imp_EnterCriticalSection
0x18001600d  xor     edx, edx
0x18001600f  mov     r8, 0CBF29CE484222325h
0x180016019  lea     r12d, [rbx+1]
0x18001601d  movzx   eax, byte ptr [rsp+rdx+98h+arg_18]
0x180016025  xor     r8, rax
0x180016028  mov     rcx, 100000001B3h
0x180016032  imul    r8, rcx
0x180016036  add     rdx, r12
0x180016039  cmp     rdx, 4
0x18001603d  jb      short loc_18001601D
0x18001603f  mov     rax, [r15+38h]
0x180016043  and     rax, r8
0x180016046  add     rax, rax
0x180016049  mov     rcx, [r15+20h]
0x18001604d  mov     r8, [rcx+rax*8+8]
0x180016052  cmp     r8, [r15+10h]
0x180016056  jz      short loc_18001606D
0x180016058  mov     rdx, [rcx+rax*8]
0x18001605c  cmp     edi, [r8+10h]
0x180016060  jz      short loc_180016070
0x180016062  cmp     r8, rdx
0x180016065  jz      short loc_18001606D
0x180016067  mov     r8, [r8+8]
0x18001606b  jmp     short loc_18001605C
0x18001606d  xor     r8d, r8d
0x180016070  test    r8, r8
0x180016073  cmovz   r8, [r15+10h]
0x180016078  cmp     r8, [r15+10h]
0x18001607c  jz      short loc_1800160D5
0x18001607e  movups  xmm6, xmmword ptr [r8+18h]
0x180016083  lea     rcx, [r15+8]
0x180016087  lea     rdx, [rsp+98h+var_58]
0x18001608c  call    ??$erase@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBJUChannelRequestContext@Wns@@@std@@@std@@@std@@@std@@$0A@@?$_Hash@V?$_Umap_traits@JUChannelRequestContext@Wns@@V?$_Uhash_compare@JU?$hash@J@std@@U?$equal_to@J@2@@std@@V?$allocator@U?$pair@$$CBJUChannelRequestContext@Wns@@@std@@@4@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBJUChannelRequestContext@Wns@@@std@@@std@@@std@@@1@V21@@Z; std::_Hash<std::_Umap_traits<long,Wns::ChannelRequestContext,std::_Uhash_compare<long,std::hash<long>,std::equal_to<long>>,std::allocator<std::pair<long const,Wns::ChannelRequestContext>>,0>>::erase<std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<long const,Wns::ChannelRequestContext>>>>,0>(std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<long const,Wns::ChannelRequestContext>>>>)
0x180016091  cmp     ebp, 800705B4h
0x180016097  movq    rbp, xmm6
0x18001609c  jz      short loc_1800160DD
0x18001609e  cmp     rbp, rsi
0x1800160a1  setz    al
0x1800160a4  mov     rcx, [rsp+98h]; this
0x1800160ac  lea     rdx, aFishinessWhyAr; "Fishiness: why are we getting a differe"...
0x1800160b3  mov     [rsp+98h+var_70], rdx; bool
0x1800160b8  mov     byte ptr [rsp+98h+var_78], al; char
0x1800160bc  mov     r9d, 8000FFFFh; char *
0x1800160c2  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800160c9  mov     edx, 1D2h; void *
0x1800160ce  call    ?Log_HrIfFalseMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Log_HrIfFalseMsg(void *,uint,char const *,long,bool,char const *,...)
0x1800160d3  jmp     short loc_1800160DD
0x1800160d5  xor     r12b, r12b
0x1800160d8  movq    rbp, xmm6
0x1800160dd  mov     rsi, [r15+50h]
0x1800160e1  jmp     short loc_1800160EF
0x1800160e3  mov     rax, [rsi]
0x1800160e6  cmp     [rax+10h], edi
0x1800160e9  jz      short loc_1800160F7
0x1800160eb  add     rsi, 8
0x1800160ef  cmp     rsi, [r15+58h]
0x1800160f3  jnz     short loc_1800160E3
0x1800160f5  jmp     short loc_180016120
0x1800160f7  mov     rdx, rsi
0x1800160fa  lea     rcx, [rsp+98h+arg_0]
0x180016102  call    ??$?4U?$default_delete@VTimerContext@CPTransactionRequestManager@Wns@@@std@@$0A@@?$unique_ptr@VTimerContext@CPTransactionRequestManager@Wns@@U?$default_delete@VTimerContext@CPTransactionRequestManager@Wns@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<Wns::CPTransactionRequestManager::TimerContext>::operator=<std::default_delete<Wns::CPTransactionRequestManager::TimerContext>,0>(std::unique_ptr<Wns::CPTransactionRequestManager::TimerContext> &&)
0x180016107  mov     r8, rsi
0x18001610a  lea     rdx, [rsp+98h+var_58]
0x18001610f  lea     rcx, [r15+50h]
0x180016113  call    ?erase@?$vector@V?$unique_ptr@VTimerContext@CPTransactionRequestManager@Wns@@U?$default_delete@VTimerContext@CPTransactionRequestManager@Wns@@@std@@@std@@V?$allocator@V?$unique_ptr@VTimerContext@CPTransactionRequestManager@Wns@@U?$default_delete@VTimerContext@CPTransactionRequestManager@Wns@@@std@@@std@@@2@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$unique_ptr@VTimerContext@CPTransactionRequestManager@Wns@@U?$default_delete@VTimerContext@CPTransactionRequestManager@Wns@@@std@@@std@@@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@V?$unique_ptr@VTimerContext@CPTransactionRequestManager@Wns@@U?$default_delete@VTimerContext@CPTransactionRequestManager@Wns@@@std@@@std@@@std@@@std@@@2@@Z; std::vector<std::unique_ptr<Wns::CPTransactionRequestManager::TimerContext>>::erase(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::unique_ptr<Wns::CPTransactionRequestManager::TimerContext>>>>)
0x180016118  mov     rbx, [rsp+98h+arg_0]
0x180016120  test    r13, r13
0x180016123  jz      short loc_18001612E
0x180016125  mov     rcx, r13; lpCriticalSection
0x180016128  call    cs:__imp_LeaveCriticalSection
0x18001612e  mov     [rsp+98h+arg_0], 0
0x18001613a  test    rbx, rbx
0x18001613d  jz      short loc_180016147
0x18001613f  mov     rdx, rbx
0x180016142  call    ??R?$default_delete@UCallback@Wns@@@std@@QEBAXPEAUCallback@Wns@@@Z; std::default_delete<Wns::Callback>::operator()(Wns::Callback *)
0x180016147  test    r12b, r12b
0x18001614a  jz      short loc_18001619D
0x18001614c  mov     rcx, [r15+0E8h]
0x180016153  movsd   xmm0, [rsp+98h+arg_30]
0x18001615c  movsd   [rsp+98h+var_68], xmm0; double
0x180016162  mov     rax, [rsp+98h+arg_28]
0x18001616a  mov     [rsp+98h+var_70], rax; unsigned __int16 *
0x18001616f  mov     rax, [rsp+98h+arg_20]
0x180016177  mov     [rsp+98h+var_78], rax; unsigned __int16 *
0x18001617c  psrldq  xmm6, 8
0x180016181  movd    r9d, xmm6; int
0x180016186  mov     r8, rbp; unsigned __int64
0x180016189  mov     edx, [rsp+98h+arg_8]; int
0x180016190  mov     rcx, [rcx+168h]; this
0x180016197  call    ?OnChannelReceived@ConnectionMultiplexer@Wns@@QEAAXJ_KJPEBG1N@Z; Wns::ConnectionMultiplexer::OnChannelReceived(long,unsigned __int64,long,ushort const *,ushort const *,double)
0x18001619c  nop
0x18001619d  mov     rbx, [rsp+98h+arg_10]
0x1800161a5  movaps  xmm6, [rsp+98h+var_48]
0x1800161aa  add     rsp, 60h
0x1800161ae  pop     r15
0x1800161b0  pop     r14
0x1800161b2  pop     r13
0x1800161b4  pop     r12
0x1800161b6  pop     rdi
0x1800161b7  pop     rsi
0x1800161b8  pop     rbp
0x1800161b9  retn
```
