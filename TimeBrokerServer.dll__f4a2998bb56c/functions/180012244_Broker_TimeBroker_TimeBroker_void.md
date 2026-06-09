# Broker::TimeBroker::TimeBroker(void)

- ea: `0x180012244`
- end: `0x180012452`
- name: `??0TimeBroker@Broker@@QEAA@XZ`
- size: `526`
- prototype: `Broker::TimeBroker *__fastcall(Broker::TimeBroker *this)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1800120f4`

## callees

- `0x180004e18`
- `0x180005b30`
- `0x180012244`
- `0x180012628`
- `0x180012638`
- `0x1800126ec`
- `0x1800127a0`
- `0x1800127cc`
- `0x180012878`
- `0x180012924`
- `0x1800132f8`

## pseudocode

```c
Broker::TimeBroker *__fastcall Broker::TimeBroker::TimeBroker(Broker::TimeBroker *this)
{
  __int64 v2; // rax
  __int64 v3; // rax
  __int64 v4; // rax
  __int64 v5; // rdx
  __int64 v6; // rax
  __int64 v7; // rdx
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  _BYTE v14[8]; // [rsp+30h] [rbp-10h] BYREF
  std::_Ref_count_base *v15; // [rsp+38h] [rbp-8h]
  int v16; // [rsp+88h] [rbp+48h] BYREF
  Broker::TimeBroker *v17; // [rsp+90h] [rbp+50h] BYREF

  `eh vector constructor iterator'(
    this,
    0x10u,
    2u,
    (void (*)(void *))Broker::TimerWheel::TimerWheel,
    (void (*)(void *))Broker::TimerWheel::~TimerWheel);
  `eh vector constructor iterator'(
    (char *)this + 32,
    0x10u,
    2u,
    (void (*)(void *))Broker::TimerWheel::TimerWheel,
    (void (*)(void *))Broker::TimerWheel::~TimerWheel);
  Broker::TimerWheel::TimerWheel((Broker::TimeBroker *)((char *)this + 64));
  `eh vector constructor iterator'(
    (char *)this + 80,
    0x10u,
    2u,
    (void (*)(void *))std::shared_ptr<Broker::SystemTimer>::shared_ptr<Broker::SystemTimer>,
    std::shared_ptr<Broker::ApplicationStateTable::State>::~shared_ptr<Broker::ApplicationStateTable::State>);
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 15) = 0;
  *((_QWORD *)this + 16) = 0;
  *((_QWORD *)this + 17) = 0;
  *((_QWORD *)this + 18) = 0;
  *((_QWORD *)this + 19) = 0;
  *((_QWORD *)this + 24) = 0;
  *((_DWORD *)this + 42) = 1;
  *((_DWORD *)this + 41) = 600000000;
  *((_BYTE *)this + 160) = 0;
  *((_BYTE *)this + 184) = 0;
  *((_QWORD *)this + 22) = 0;
  LOBYTE(v16) = 0;
  v2 = lambda_fb3bb88e5f093f92c0d0f05c320b2e40_::_lambda_fb3bb88e5f093f92c0d0f05c320b2e40_(&v17, this);
  v3 = std::make_shared_Broker::SystemTimer__lambda_fb3bb88e5f093f92c0d0f05c320b2e40__bool_(v14, v2, &v16);
  std::shared_ptr<Broker::SystemTimer>::operator=((char *)this + 112, v3);
  if ( v15 )
    std::_Ref_count_base::_Decref(v15);
  v4 = lambda_fb3bb88e5f093f92c0d0f05c320b2e40_::_lambda_fb3bb88e5f093f92c0d0f05c320b2e40_(&v17, this);
  v16 = 0;
  v6 = std::make_shared_Broker::BILayer::WnfNotification__WNF_STATE_NAME_const___int__lambda_c1af60428e0a4071aa1a6367303c0166___(
         v14,
         v5,
         &v16,
         v4);
  std::shared_ptr<Broker::SystemTimer>::operator=((char *)this + 128, v6);
  if ( v15 )
    std::_Ref_count_base::_Decref(v15);
  v17 = this;
  v16 = 0;
  v8 = std::make_shared_Broker::BILayer::WnfNotification__WNF_STATE_NAME_const___int__lambda_453ca5069daf25e7d2fe3ac24cb8655a___(
         v14,
         v7,
         &v16,
         &v17);
  std::shared_ptr<Broker::SystemTimer>::operator=((char *)this + 144, v8);
  if ( v15 )
    std::_Ref_count_base::_Decref(v15);
  LOBYTE(v16) = 0;
  v9 = lambda_fb3bb88e5f093f92c0d0f05c320b2e40_::_lambda_fb3bb88e5f093f92c0d0f05c320b2e40_(&v17, this);
  v10 = std::make_shared_Broker::SystemTimer__lambda_a04f1fa45023656142eaad50f63dd072__bool_(v14, v9, &v16);
  std::shared_ptr<Broker::SystemTimer>::operator=((char *)this + 80, v10);
  if ( v15 )
    std::_Ref_count_base::_Decref(v15);
  LOBYTE(v16) = 1;
  v11 = lambda_fb3bb88e5f093f92c0d0f05c320b2e40_::_lambda_fb3bb88e5f093f92c0d0f05c320b2e40_(&v17, this);
  v12 = std::make_shared_Broker::SystemTimer__lambda_5558ee1e6b2dcc87304ff1cbde56dffa__bool_(v14, v11, &v16);
  std::shared_ptr<Broker::SystemTimer>::operator=((char *)this + 96, v12);
  if ( v15 )
    std::_Ref_count_base::_Decref(v15);
  return this;
}

```

## disassembly

```asm
0x180012244  mov     [rsp-38h+arg_0], rcx
0x180012249  push    rbp
0x18001224a  push    rbx
0x18001224b  push    rsi
0x18001224c  push    rdi
0x18001224d  push    r12
0x18001224f  push    r14
0x180012251  push    r15
0x180012253  mov     rbp, rsp
0x180012256  sub     rsp, 40h
0x18001225a  mov     rdi, rcx
0x18001225d  lea     rbx, ??1TimerWheel@Broker@@QEAA@XZ; Broker::TimerWheel::~TimerWheel(void)
0x180012264  mov     [rsp+40h+var_20], rbx; void (*)(void *)
0x180012269  lea     r9, ??0TimerWheel@Broker@@QEAA@XZ; void (*)(void *)
0x180012270  mov     r15d, 2
0x180012276  mov     r8d, r15d; unsigned __int64
0x180012279  lea     r14d, [r15+0Eh]
0x18001227d  mov     edx, r14d; unsigned __int64
0x180012280  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x180012285  nop
0x180012286  lea     rcx, [rdi+20h]; void *
0x18001228a  mov     [rsp+40h+var_20], rbx; void (*)(void *)
0x18001228f  lea     r9, ??0TimerWheel@Broker@@QEAA@XZ; void (*)(void *)
0x180012296  mov     r8d, r15d; unsigned __int64
0x180012299  mov     edx, r14d; unsigned __int64
0x18001229c  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x1800122a1  nop
0x1800122a2  lea     rcx, [rdi+40h]; this
0x1800122a6  call    ??0TimerWheel@Broker@@QEAA@XZ; Broker::TimerWheel::TimerWheel(void)
0x1800122ab  nop
0x1800122ac  lea     rax, ??1?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@QEAA@XZ; std::shared_ptr<Broker::ApplicationStateTable::State>::~shared_ptr<Broker::ApplicationStateTable::State>(void)
0x1800122b3  mov     [rsp+40h+var_20], rax; void (*)(void *)
0x1800122b8  lea     r9, ??0?$shared_ptr@VSystemTimer@Broker@@@std@@QEAA@XZ; void (*)(void *)
0x1800122bf  mov     r8d, r15d; unsigned __int64
0x1800122c2  mov     edx, r14d; unsigned __int64
0x1800122c5  lea     rcx, [rdi+50h]; void *
0x1800122c9  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x1800122ce  nop
0x1800122cf  xor     r12d, r12d
0x1800122d2  mov     [rdi+70h], r12
0x1800122d6  mov     [rdi+78h], r12
0x1800122da  lea     r15, [rdi+80h]
0x1800122e1  mov     [r15], r12
0x1800122e4  mov     [r15+8], r12
0x1800122e8  lea     r14, [rdi+90h]
0x1800122ef  mov     [r14], r12
0x1800122f2  mov     [r14+8], r12
0x1800122f6  mov     [rdi+0C0h], r12
0x1800122fd  mov     dword ptr [rdi+0A8h], 1
0x180012307  mov     dword ptr [rdi+0A4h], 23C34600h
0x180012311  mov     [rdi+0A0h], r12b
0x180012318  mov     [rdi+0B8h], r12b
0x18001231f  mov     [rdi+0B0h], r12
0x180012326  mov     byte ptr [rbp+arg_8], r12b
0x18001232a  mov     rdx, rdi
0x18001232d  lea     rcx, [rbp+arg_10]
0x180012331  call    _lambda_fb3bb88e5f093f92c0d0f05c320b2e40____lambda_fb3bb88e5f093f92c0d0f05c320b2e40_
0x180012336  mov     rdx, rax
0x180012339  lea     r8, [rbp+arg_8]
0x18001233d  lea     rcx, [rbp+var_10]
0x180012341  call    std__make_shared_Broker__SystemTimer__lambda_fb3bb88e5f093f92c0d0f05c320b2e40__bool_
0x180012346  mov     rdx, rax
0x180012349  lea     rcx, [rdi+70h]
0x18001234d  call    ??4?$shared_ptr@VSystemTimer@Broker@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Broker::SystemTimer>::operator=(std::shared_ptr<Broker::SystemTimer> &&)
0x180012352  mov     rcx, [rbp+var_8]; this
0x180012356  test    rcx, rcx
0x180012359  jz      short loc_180012360
0x18001235b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180012360  mov     rdx, rdi
0x180012363  lea     rcx, [rbp+arg_10]
0x180012367  call    _lambda_fb3bb88e5f093f92c0d0f05c320b2e40____lambda_fb3bb88e5f093f92c0d0f05c320b2e40_
0x18001236c  mov     [rbp+arg_8], r12d
0x180012370  mov     r9, rax
0x180012373  lea     r8, [rbp+arg_8]
0x180012377  lea     rcx, [rbp+var_10]
0x18001237b  call    std__make_shared_Broker__BILayer__WnfNotification__WNF_STATE_NAME_const___int__lambda_c1af60428e0a4071aa1a6367303c0166___
0x180012380  mov     rdx, rax
0x180012383  mov     rcx, r15
0x180012386  call    ??4?$shared_ptr@VSystemTimer@Broker@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Broker::SystemTimer>::operator=(std::shared_ptr<Broker::SystemTimer> &&)
0x18001238b  mov     rcx, [rbp+var_8]; this
0x18001238f  test    rcx, rcx
0x180012392  jz      short loc_180012399
0x180012394  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180012399  mov     [rbp+arg_10], rdi
0x18001239d  mov     [rbp+arg_8], r12d
0x1800123a1  lea     r9, [rbp+arg_10]
0x1800123a5  lea     r8, [rbp+arg_8]
0x1800123a9  lea     rcx, [rbp+var_10]
0x1800123ad  call    std__make_shared_Broker__BILayer__WnfNotification__WNF_STATE_NAME_const___int__lambda_453ca5069daf25e7d2fe3ac24cb8655a___
0x1800123b2  mov     rdx, rax
0x1800123b5  mov     rcx, r14
0x1800123b8  call    ??4?$shared_ptr@VSystemTimer@Broker@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Broker::SystemTimer>::operator=(std::shared_ptr<Broker::SystemTimer> &&)
0x1800123bd  mov     rcx, [rbp+var_8]; this
0x1800123c1  test    rcx, rcx
0x1800123c4  jz      short loc_1800123CB
0x1800123c6  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800123cb  mov     byte ptr [rbp+arg_8], r12b
0x1800123cf  mov     rdx, rdi
0x1800123d2  lea     rcx, [rbp+arg_10]
0x1800123d6  call    _lambda_fb3bb88e5f093f92c0d0f05c320b2e40____lambda_fb3bb88e5f093f92c0d0f05c320b2e40_
0x1800123db  mov     rdx, rax
0x1800123de  lea     r8, [rbp+arg_8]
0x1800123e2  lea     rcx, [rbp+var_10]
0x1800123e6  call    std__make_shared_Broker__SystemTimer__lambda_a04f1fa45023656142eaad50f63dd072__bool_
0x1800123eb  mov     rdx, rax
0x1800123ee  lea     rcx, [rdi+50h]
0x1800123f2  call    ??4?$shared_ptr@VSystemTimer@Broker@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Broker::SystemTimer>::operator=(std::shared_ptr<Broker::SystemTimer> &&)
0x1800123f7  mov     rcx, [rbp+var_8]; this
0x1800123fb  test    rcx, rcx
0x1800123fe  jz      short loc_180012405
0x180012400  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180012405  mov     byte ptr [rbp+arg_8], 1
0x180012409  mov     rdx, rdi
0x18001240c  lea     rcx, [rbp+arg_10]
0x180012410  call    _lambda_fb3bb88e5f093f92c0d0f05c320b2e40____lambda_fb3bb88e5f093f92c0d0f05c320b2e40_
0x180012415  mov     rdx, rax
0x180012418  lea     r8, [rbp+arg_8]
0x18001241c  lea     rcx, [rbp+var_10]
0x180012420  call    std__make_shared_Broker__SystemTimer__lambda_5558ee1e6b2dcc87304ff1cbde56dffa__bool_
0x180012425  lea     rcx, [rdi+60h]
0x180012429  mov     rdx, rax
0x18001242c  call    ??4?$shared_ptr@VSystemTimer@Broker@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Broker::SystemTimer>::operator=(std::shared_ptr<Broker::SystemTimer> &&)
0x180012431  mov     rcx, [rbp+var_8]; this
0x180012435  test    rcx, rcx
0x180012438  jz      short loc_180012440
0x18001243a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001243f  nop
0x180012440  mov     rax, rdi
0x180012443  add     rsp, 40h
0x180012447  pop     r15
0x180012449  pop     r14
0x18001244b  pop     r12
0x18001244d  pop     rdi
0x18001244e  pop     rsi
0x18001244f  pop     rbx
0x180012450  pop     rbp
0x180012451  retn
```
