# std::make_shared_Broker::BILayer::WnfNotification__WNF_STATE_NAME_const_&_int__lambda_453ca5069daf25e7d2fe3ac24cb8655a___

- ea: `0x180012924`
- end: `0x1800129cf`
- name: `std::make_shared_Broker::BILayer::WnfNotification__WNF_STATE_NAME_const_&_int__lambda_453ca5069daf25e7d2fe3ac24cb8655a___`
- size: `171`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180012244`

## callees

- `0x180012df4`
- `0x180019784`

## pseudocode

```c
_QWORD *__fastcall std::make_shared_Broker::BILayer::WnfNotification__WNF_STATE_NAME_const___int__lambda_453ca5069daf25e7d2fe3ac24cb8655a___(
        _QWORD *a1,
        __int64 a2,
        int *a3,
        __int64 *a4)
{
  __int64 v8[9]; // [rsp+28h] [rbp-60h] BYREF
  _DWORD *v9; // [rsp+98h] [rbp+10h]

  v9 = operator new(0x60u);
  *(_OWORD *)v9 = 0;
  v9[2] = 1;
  v9[3] = 1;
  *(_QWORD *)v9 = &std::_Ref_count_obj2<Broker::BILayer::WnfNotification>::`vftable';
  v8[0] = (__int64)off_18001D228;
  v8[1] = *a4;
  v8[7] = (__int64)v8;
  Broker::BILayer::WnfNotification::WnfNotification((_QWORD *)v9 + 2, WNF_BI_NETWORK_LIMITED_CHANNEL, *a3, v8);
  *a1 = v9 + 4;
  a1[1] = v9;
  return a1;
}

```

## disassembly

```asm
0x180012924  mov     [rsp+arg_10], rbx
0x180012929  mov     [rsp+arg_18], rsi
0x18001292e  mov     [rsp+arg_8], rdx
0x180012933  push    rdi
0x180012934  push    r14
0x180012936  push    r15
0x180012938  sub     rsp, 70h
0x18001293c  mov     rdi, r9
0x18001293f  mov     r14, r8
0x180012942  mov     r15, rcx
0x180012945  mov     ecx, 60h ; '`'; Size
0x18001294a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001294f  mov     rsi, rax
0x180012952  mov     [rsp+88h+arg_8], rax
0x18001295a  xorps   xmm0, xmm0
0x18001295d  movups  xmmword ptr [rax], xmm0
0x180012960  mov     eax, 1
0x180012965  mov     [rsi+8], eax
0x180012968  mov     [rsi+0Ch], eax
0x18001296b  lea     rax, ??_7?$_Ref_count_obj2@VWnfNotification@BILayer@Broker@@@std@@6B@; const std::_Ref_count_obj2<Broker::BILayer::WnfNotification>::`vftable'
0x180012972  mov     [rsi], rax
0x180012975  lea     rbx, [rsi+10h]
0x180012979  lea     rax, off_18001D228
0x180012980  mov     [rsp+88h+var_60], rax
0x180012985  mov     rax, [rdi]
0x180012988  mov     [rsp+88h+var_58], rax
0x18001298d  lea     rax, [rsp+88h+var_60]
0x180012992  mov     [rsp+88h+var_28], rax
0x180012997  lea     r9, [rsp+88h+var_60]
0x18001299c  mov     r8d, [r14]
0x18001299f  mov     rdx, cs:WNF_BI_NETWORK_LIMITED_CHANNEL
0x1800129a6  mov     rcx, rbx
0x1800129a9  call    ??0WnfNotification@BILayer@Broker@@QEAA@U_WNF_STATE_NAME@@KV?$function@$$A6AX_KPEBX@Z@std@@@Z; Broker::BILayer::WnfNotification::WnfNotification(_WNF_STATE_NAME,ulong,std::function<void (unsigned __int64,void const *)>)
0x1800129ae  nop
0x1800129af  mov     [r15], rbx
0x1800129b2  mov     [r15+8], rsi
0x1800129b6  mov     rax, r15
0x1800129b9  lea     r11, [rsp+88h+var_18]
0x1800129be  mov     rbx, [r11+30h]
0x1800129c2  mov     rsi, [r11+38h]
0x1800129c6  mov     rsp, r11
0x1800129c9  pop     r15
0x1800129cb  pop     r14
0x1800129cd  pop     rdi
0x1800129ce  retn
```
