# Broker::TimeBroker::CreateInstance(void)

- ea: `0x1800120f4`
- end: `0x1800121b6`
- name: `?CreateInstance@TimeBroker@Broker@@SAXXZ`
- size: `194`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180011ea8`

## callees

- `0x180004e18`
- `0x180005b30`
- `0x1800120f4`
- `0x1800121bc`
- `0x180012244`
- `0x180012458`
- `0x180012df4`

## pseudocode

```c
void Broker::TimeBroker::CreateInstance(void)
{
  _DWORD *v0; // [rsp+20h] [rbp-18h] BYREF
  std::_Ref_count_base *v1; // [rsp+28h] [rbp-10h]
  _DWORD *v2; // [rsp+40h] [rbp+8h]

  qword_180026660 = 0;
  WPP_MAIN_CB = 0;
  qword_180026668 = 1;
  WPP_REGISTRATION_GUIDS = (__int64)&WPP_ThisDir_CTLGUID_BrokerCommon;
  WPP_GLOBAL_Control = &WPP_MAIN_CB;
  WppInitUm();
  v2 = operator new(0xE8u);
  *(_OWORD *)v2 = 0;
  v2[2] = 1;
  v2[3] = 1;
  *(_QWORD *)v2 = &std::_Ref_count_obj2<Broker::TimeBroker>::`vftable';
  Broker::TimeBroker::TimeBroker((Broker::TimeBroker *)(v2 + 4));
  v0 = v2 + 4;
  v1 = (std::_Ref_count_base *)v2;
  std::shared_ptr<Broker::SystemTimer>::operator=(&Broker::TimeBroker::Instance, (__int64 *)&v0);
  if ( v1 )
    std::_Ref_count_base::_Decref(v1);
  Broker::TimeBroker::Init(Broker::TimeBroker::Instance);
}

```

## disassembly

```asm
0x1800120f4  mov     [rsp+arg_8], rbx
0x1800120f9  push    rdi
0x1800120fa  sub     rsp, 30h
0x1800120fe  mov     cs:qword_180026660, 0
0x180012109  mov     cs:WPP_MAIN_CB, 0
0x180012114  mov     ebx, 1
0x180012119  mov     cs:qword_180026668, rbx
0x180012120  lea     rax, WPP_ThisDir_CTLGUID_BrokerCommon
0x180012127  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x18001212e  lea     rax, WPP_MAIN_CB
0x180012135  mov     cs:WPP_GLOBAL_Control, rax
0x18001213c  call    WppInitUm
0x180012141  mov     ecx, 0E8h; Size
0x180012146  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001214b  mov     rdi, rax
0x18001214e  mov     [rsp+38h+arg_0], rax
0x180012153  xorps   xmm0, xmm0
0x180012156  movups  xmmword ptr [rax], xmm0
0x180012159  mov     [rax+8], ebx
0x18001215c  mov     [rax+0Ch], ebx
0x18001215f  lea     rax, ??_7?$_Ref_count_obj2@VTimeBroker@Broker@@@std@@6B@; const std::_Ref_count_obj2<Broker::TimeBroker>::`vftable'
0x180012166  mov     [rdi], rax
0x180012169  lea     rbx, [rdi+10h]
0x18001216d  mov     rcx, rbx; this
0x180012170  call    ??0TimeBroker@Broker@@QEAA@XZ; Broker::TimeBroker::TimeBroker(void)
0x180012175  nop
0x180012176  mov     [rsp+38h+var_18], rbx
0x18001217b  mov     [rsp+38h+var_10], rdi
0x180012180  lea     rdx, [rsp+38h+var_18]
0x180012185  lea     rcx, ?Instance@TimeBroker@Broker@@0V?$shared_ptr@VTimeBroker@Broker@@@std@@A; std::shared_ptr<Broker::TimeBroker> Broker::TimeBroker::Instance
0x18001218c  call    ??4?$shared_ptr@VSystemTimer@Broker@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Broker::SystemTimer>::operator=(std::shared_ptr<Broker::SystemTimer> &&)
0x180012191  mov     rcx, [rsp+38h+var_10]; this
0x180012196  test    rcx, rcx
0x180012199  jz      short loc_1800121A0
0x18001219b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800121a0  mov     rcx, qword ptr cs:?Instance@TimeBroker@Broker@@0V?$shared_ptr@VTimeBroker@Broker@@@std@@A; this
0x1800121a7  mov     rbx, [rsp+38h+arg_8]
0x1800121ac  add     rsp, 30h
0x1800121b0  pop     rdi
0x1800121b1  jmp     ?Init@TimeBroker@Broker@@QEAAXXZ; Broker::TimeBroker::Init(void)
```
