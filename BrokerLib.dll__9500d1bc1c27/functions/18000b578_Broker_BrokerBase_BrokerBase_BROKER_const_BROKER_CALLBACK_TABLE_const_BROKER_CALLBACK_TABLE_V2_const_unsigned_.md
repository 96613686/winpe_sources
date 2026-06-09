# Broker::BrokerBase::BrokerBase(_BROKER * const,_BROKER_CALLBACK_TABLE const *,_BROKER_CALLBACK_TABLE_V2 const *,unsigned __int64,ulong const *)

- ea: `0x18000b578`
- end: `0x18000b7c6`
- name: `??0BrokerBase@Broker@@QEAA@QEAU_BROKER@@PEBU_BROKER_CALLBACK_TABLE@@PEBU_BROKER_CALLBACK_TABLE_V2@@_KPEBK@Z`
- size: `590`
- prototype: `__int64 __fastcall(Broker::BrokerBase *__hidden this, struct _BROKER *const, const struct _BROKER_CALLBACK_TABLE *, const struct _BROKER_CALLBACK_TABLE_V2 *, unsigned __int64, const unsigned int *Src)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180018004`

## callees

- `0x180005b50`
- `0x18000b578`
- `0x18000b7cc`
- `0x18000b864`
- `0x18000b954`
- `0x18000b9d0`
- `0x18000fab8`
- `0x180015b14`
- `0x1800165b6`
- `0x1800165c2`

## import_xrefs

- `ntdll!RtlInitializeSRWLock` at `0x18000b6dc`
- `ntdll!RtlInitializeSRWLock` at `0x18000b6dc`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
Broker::BrokerBase *__fastcall Broker::BrokerBase::BrokerBase(
        Broker::BrokerBase *this,
        struct _BROKER *const a2,
        const struct _BROKER_CALLBACK_TABLE *a3,
        const struct _BROKER_CALLBACK_TABLE_V2 *a4,
        unsigned __int64 a5,
        const unsigned int *Src)
{
  _QWORD *v9; // rax
  char *v10; // rsi
  size_t v11; // rbx
  __int64 v12; // rax
  _QWORD v14[2]; // [rsp+20h] [rbp-30h] BYREF
  void *v15[2]; // [rsp+30h] [rbp-20h] BYREF
  __int64 v16; // [rsp+40h] [rbp-10h]
  void *v17; // [rsp+88h] [rbp+38h]

  *((_QWORD *)this + 1) = a2;
  Broker::BrokeredEventTable::BrokeredEventTable((Broker::BrokerBase *)((char *)this + 208));
  *((_QWORD *)this + 32) = 0;
  *((_QWORD *)this + 33) = 0;
  v9 = operator new(0x48u);
  *v9 = v9;
  v9[1] = v9;
  v9[2] = v9;
  *((_WORD *)v9 + 12) = 257;
  *((_QWORD *)this + 32) = v9;
  *((_QWORD *)this + 34) = 0;
  *((_QWORD *)this + 35) = 0;
  *((_QWORD *)this + 36) = 0;
  *((_QWORD *)this + 37) = 0;
  *((_QWORD *)this + 38) = 0;
  *((_QWORD *)this + 39) = 0;
  *((_QWORD *)this + 40) = 0;
  *((_BYTE *)this + 328) = 0;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    WPP_SF__guid_(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      14,
      &WPP_4753d2a3665d3618996ed9ba7dd16268_Traceguids,
      *((_QWORD *)this + 1));
  if ( a3 )
  {
    *((_OWORD *)this + 1) = *(_OWORD *)a3;
    *((_OWORD *)this + 2) = *((_OWORD *)a3 + 1);
    *((_OWORD *)this + 3) = *((_OWORD *)a3 + 2);
    *((_OWORD *)this + 4) = *((_OWORD *)a3 + 3);
    *((_OWORD *)this + 5) = *((_OWORD *)a3 + 4);
    *((_OWORD *)this + 6) = *((_OWORD *)a3 + 5);
    *((_QWORD *)this + 14) = *((_QWORD *)a3 + 12);
  }
  else
  {
    memset_0((char *)this + 16, 0, 0x68u);
  }
  if ( a4 )
  {
    *(_OWORD *)((char *)this + 120) = *(_OWORD *)a4;
    *(_OWORD *)((char *)this + 136) = *((_OWORD *)a4 + 1);
    *((_QWORD *)this + 19) = *((_QWORD *)a4 + 4);
  }
  else
  {
    *(_OWORD *)((char *)this + 120) = 0;
    *(_OWORD *)((char *)this + 136) = 0;
    *((_QWORD *)this + 19) = 0;
  }
  RtlInitializeSRWLock(this);
  *(_OWORD *)v15 = 0;
  v16 = 0;
  v10 = 0;
  if ( a5 )
  {
    std::vector<unsigned long>::_Buy_nonzero(v15, a5);
    v10 = (char *)v15[0];
    v11 = 4 * a5;
    memset_0(v15[0], 0, 4 * a5);
    v15[1] = &v10[4 * a5];
  }
  else
  {
    v11 = 0;
  }
  memmove_0(v10, Src, v11);
  v17 = operator new(0x40u);
  v12 = std::_Ref_count_obj2<Broker::ApplicationStateTable>::_Ref_count_obj2<Broker::ApplicationStateTable>(v17, v15);
  v14[0] = *((_QWORD *)this + 34);
  *((_QWORD *)this + 34) = v12 + 16;
  v14[1] = *((_QWORD *)this + 35);
  *((_QWORD *)this + 35) = v12;
  std::shared_ptr<Broker::ApplicationStateTable::State>::~shared_ptr<Broker::ApplicationStateTable::State>((__int64)v14);
  *((_OWORD *)this + 10) = 0;
  *((_OWORD *)this + 11) = 0;
  *((_OWORD *)this + 12) = 0;
  std::vector<unsigned long>::_Tidy(v15);
  return this;
}

```

## disassembly

```asm
0x18000b578  mov     [rsp-28h+arg_10], rbx
0x18000b57d  mov     [rsp-28h+arg_18], rsi
0x18000b582  mov     [rsp-28h+arg_0], rcx
0x18000b587  push    rbp
0x18000b588  push    rdi
0x18000b589  push    r12
0x18000b58b  push    r14
0x18000b58d  push    r15
0x18000b58f  mov     rbp, rsp
0x18000b592  sub     rsp, 50h
0x18000b596  mov     r14, r9
0x18000b599  mov     rsi, r8
0x18000b59c  mov     rdi, rcx
0x18000b59f  mov     r15, [rbp+arg_20]
0x18000b5a3  xor     r12d, r12d
0x18000b5a6  mov     [rcx+8], rdx
0x18000b5aa  add     rcx, 0D0h; this
0x18000b5b1  call    ??0BrokeredEventTable@Broker@@QEAA@XZ; Broker::BrokeredEventTable::BrokeredEventTable(void)
0x18000b5b6  nop
0x18000b5b7  lea     rbx, [rdi+100h]
0x18000b5be  mov     [rbx], r12
0x18000b5c1  mov     [rbx+8], r12
0x18000b5c5  lea     ecx, [r12+48h]; Size
0x18000b5ca  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000b5cf  mov     [rax], rax
0x18000b5d2  mov     [rax+8], rax
0x18000b5d6  mov     [rax+10h], rax
0x18000b5da  mov     word ptr [rax+18h], 101h
0x18000b5e0  mov     [rbx], rax
0x18000b5e3  mov     [rdi+110h], r12
0x18000b5ea  mov     [rdi+118h], r12
0x18000b5f1  mov     [rdi+120h], r12
0x18000b5f8  mov     [rdi+128h], r12
0x18000b5ff  mov     [rdi+130h], r12
0x18000b606  mov     [rdi+138h], r12
0x18000b60d  mov     [rdi+140h], r12
0x18000b614  mov     [rdi+148h], r12b
0x18000b61b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b622  test    dword ptr [rcx+1Ch], 800h
0x18000b629  jz      short loc_18000B64A
0x18000b62b  cmp     byte ptr [rcx+19h], 5
0x18000b62f  jb      short loc_18000B64A
0x18000b631  lea     edx, [r12+0Eh]
0x18000b636  mov     r9, [rdi+8]
0x18000b63a  lea     r8, WPP_4753d2a3665d3618996ed9ba7dd16268_Traceguids
0x18000b641  mov     rcx, [rcx+10h]
0x18000b645  call    WPP_SF__guid_
0x18000b64a  test    rsi, rsi
0x18000b64d  jz      short loc_18000B68A
0x18000b64f  movups  xmm0, xmmword ptr [rsi]
0x18000b652  movups  xmmword ptr [rdi+10h], xmm0
0x18000b656  movups  xmm1, xmmword ptr [rsi+10h]
0x18000b65a  movups  xmmword ptr [rdi+20h], xmm1
0x18000b65e  movups  xmm0, xmmword ptr [rsi+20h]
0x18000b662  movups  xmmword ptr [rdi+30h], xmm0
0x18000b666  movups  xmm1, xmmword ptr [rsi+30h]
0x18000b66a  movups  xmmword ptr [rdi+40h], xmm1
0x18000b66e  movups  xmm0, xmmword ptr [rsi+40h]
0x18000b672  movups  xmmword ptr [rdi+50h], xmm0
0x18000b676  movups  xmm1, xmmword ptr [rsi+50h]
0x18000b67a  movups  xmmword ptr [rdi+60h], xmm1
0x18000b67e  movsd   xmm0, qword ptr [rsi+60h]
0x18000b683  movsd   qword ptr [rdi+70h], xmm0
0x18000b688  jmp     short loc_18000B699
0x18000b68a  lea     rcx, [rdi+10h]; void *
0x18000b68e  xor     edx, edx; Val
0x18000b690  lea     r8d, [rdx+68h]; Size
0x18000b694  call    memset_0
0x18000b699  test    r14, r14
0x18000b69c  jz      short loc_18000B6C2
0x18000b69e  movups  xmm0, xmmword ptr [r14]
0x18000b6a2  movups  xmmword ptr [rdi+78h], xmm0
0x18000b6a6  movups  xmm1, xmmword ptr [r14+10h]
0x18000b6ab  movups  xmmword ptr [rdi+88h], xmm1
0x18000b6b2  movsd   xmm0, qword ptr [r14+20h]
0x18000b6b8  movsd   qword ptr [rdi+98h], xmm0
0x18000b6c0  jmp     short loc_18000B6D9
0x18000b6c2  xorps   xmm0, xmm0
0x18000b6c5  xor     eax, eax
0x18000b6c7  movups  xmmword ptr [rdi+78h], xmm0
0x18000b6cb  movups  xmmword ptr [rdi+88h], xmm0
0x18000b6d2  mov     [rdi+98h], rax
0x18000b6d9  mov     rcx, rdi
0x18000b6dc  call    cs:__imp_RtlInitializeSRWLock
0x18000b6e2  xorps   xmm0, xmm0
0x18000b6e5  movdqu  xmmword ptr [rbp+var_20], xmm0
0x18000b6ea  mov     [rbp+var_10], r12
0x18000b6ee  mov     rsi, r12
0x18000b6f1  test    r15, r15
0x18000b6f4  jz      short loc_18000B725
0x18000b6f6  mov     rdx, r15
0x18000b6f9  lea     rcx, [rbp+var_20]
0x18000b6fd  call    ?_Buy_nonzero@?$vector@KV?$allocator@K@std@@@std@@AEAAX_K@Z; std::vector<ulong>::_Buy_nonzero(unsigned __int64)
0x18000b702  mov     rsi, [rbp+var_20]
0x18000b706  lea     rbx, ds:0[r15*4]
0x18000b70e  mov     r8, rbx; Size
0x18000b711  xor     edx, edx; Val
0x18000b713  mov     rcx, rsi; void *
0x18000b716  call    memset_0
0x18000b71b  lea     rax, [rbx+rsi]
0x18000b71f  mov     [rbp+var_20+8], rax
0x18000b723  jmp     short loc_18000B72D
0x18000b725  lea     rbx, ds:0[r15*4]
0x18000b72d  mov     r8, rbx; Size
0x18000b730  mov     rdx, [rbp+Src]; Src
0x18000b734  mov     rcx, rsi; void *
0x18000b737  call    memmove_0
0x18000b73c  mov     ecx, 40h ; '@'; Size
0x18000b741  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000b746  mov     [rbp+arg_8], rax
0x18000b74a  lea     rdx, [rbp+var_20]
0x18000b74e  mov     rcx, rax
0x18000b751  call    ??$?0AEAV?$vector@KV?$allocator@K@std@@@std@@@?$_Ref_count_obj2@VApplicationStateTable@Broker@@@std@@QEAA@AEAV?$vector@KV?$allocator@K@std@@@1@@Z; std::_Ref_count_obj2<Broker::ApplicationStateTable>::_Ref_count_obj2<Broker::ApplicationStateTable>(std::vector<ulong> &)
0x18000b756  nop
0x18000b757  mov     rcx, [rdi+110h]
0x18000b75e  mov     [rbp+var_30], rcx
0x18000b762  lea     rcx, [rax+10h]
0x18000b766  mov     [rdi+110h], rcx
0x18000b76d  mov     rcx, [rdi+118h]
0x18000b774  mov     [rbp+var_28], rcx
0x18000b778  mov     [rdi+118h], rax
0x18000b77f  lea     rcx, [rbp+var_30]
0x18000b783  call    ??1?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@QEAA@XZ; std::shared_ptr<Broker::ApplicationStateTable::State>::~shared_ptr<Broker::ApplicationStateTable::State>(void)
0x18000b788  xorps   xmm0, xmm0
0x18000b78b  movups  xmmword ptr [rdi+0A0h], xmm0
0x18000b792  movups  xmmword ptr [rdi+0B0h], xmm0
0x18000b799  movups  xmmword ptr [rdi+0C0h], xmm0
0x18000b7a0  lea     rcx, [rbp+var_20]
0x18000b7a4  call    ?_Tidy@?$vector@KV?$allocator@K@std@@@std@@AEAAXXZ; std::vector<ulong>::_Tidy(void)
0x18000b7a9  nop
0x18000b7aa  mov     rax, rdi
0x18000b7ad  lea     r11, [rsp+50h+var_s0]
0x18000b7b2  mov     rbx, [r11+40h]
0x18000b7b6  mov     rsi, [r11+48h]
0x18000b7ba  mov     rsp, r11
0x18000b7bd  pop     r15
0x18000b7bf  pop     r14
0x18000b7c1  pop     r12
0x18000b7c3  pop     rdi
0x18000b7c4  pop     rbp
0x18000b7c5  retn
```
