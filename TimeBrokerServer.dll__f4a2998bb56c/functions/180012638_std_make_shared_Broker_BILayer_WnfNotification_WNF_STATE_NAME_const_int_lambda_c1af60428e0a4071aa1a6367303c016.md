# std::make_shared_Broker::BILayer::WnfNotification__WNF_STATE_NAME_const_&_int__lambda_c1af60428e0a4071aa1a6367303c0166___

- ea: `0x180012638`
- end: `0x1800126e3`
- name: `std::make_shared_Broker::BILayer::WnfNotification__WNF_STATE_NAME_const_&_int__lambda_c1af60428e0a4071aa1a6367303c0166___`
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
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall std::make_shared_Broker::BILayer::WnfNotification__WNF_STATE_NAME_const___int__lambda_c1af60428e0a4071aa1a6367303c0166___(
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
  v8[0] = (__int64)off_18001D258;
  v8[1] = *a4;
  v8[7] = (__int64)v8;
  Broker::BILayer::WnfNotification::WnfNotification((_QWORD *)v9 + 2, WNF_BI_BROKER_WAKEUP_CHANNEL, *a3, v8);
  *a1 = v9 + 4;
  a1[1] = v9;
  return a1;
}

```

## disassembly

```asm
0x180012638  mov     [rsp+arg_10], rbx
0x18001263d  mov     [rsp+arg_18], rsi
0x180012642  mov     [rsp+arg_8], rdx
0x180012647  push    rdi
0x180012648  push    r14
0x18001264a  push    r15
0x18001264c  sub     rsp, 70h
0x180012650  mov     rdi, r9
0x180012653  mov     r14, r8
0x180012656  mov     r15, rcx
0x180012659  mov     ecx, 60h ; '`'; Size
0x18001265e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180012663  mov     rsi, rax
0x180012666  mov     [rsp+88h+arg_8], rax
0x18001266e  xorps   xmm0, xmm0
0x180012671  movups  xmmword ptr [rax], xmm0
0x180012674  mov     eax, 1
0x180012679  mov     [rsi+8], eax
0x18001267c  mov     [rsi+0Ch], eax
0x18001267f  lea     rax, ??_7?$_Ref_count_obj2@VWnfNotification@BILayer@Broker@@@std@@6B@; const std::_Ref_count_obj2<Broker::BILayer::WnfNotification>::`vftable'
0x180012686  mov     [rsi], rax
0x180012689  lea     rbx, [rsi+10h]
0x18001268d  lea     rax, off_18001D258
0x180012694  mov     [rsp+88h+var_60], rax
0x180012699  mov     rax, [rdi]
0x18001269c  mov     [rsp+88h+var_58], rax
0x1800126a1  lea     rax, [rsp+88h+var_60]
0x1800126a6  mov     [rsp+88h+var_28], rax
0x1800126ab  lea     r9, [rsp+88h+var_60]
0x1800126b0  mov     r8d, [r14]
0x1800126b3  mov     rdx, cs:WNF_BI_BROKER_WAKEUP_CHANNEL
0x1800126ba  mov     rcx, rbx
0x1800126bd  call    ??0WnfNotification@BILayer@Broker@@QEAA@U_WNF_STATE_NAME@@KV?$function@$$A6AX_KPEBX@Z@std@@@Z; Broker::BILayer::WnfNotification::WnfNotification(_WNF_STATE_NAME,ulong,std::function<void (unsigned __int64,void const *)>)
0x1800126c2  nop
0x1800126c3  mov     [r15], rbx
0x1800126c6  mov     [r15+8], rsi
0x1800126ca  mov     rax, r15
0x1800126cd  lea     r11, [rsp+88h+var_18]
0x1800126d2  mov     rbx, [r11+30h]
0x1800126d6  mov     rsi, [r11+38h]
0x1800126da  mov     rsp, r11
0x1800126dd  pop     r15
0x1800126df  pop     r14
0x1800126e1  pop     rdi
0x1800126e2  retn
```
