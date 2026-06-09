# std::make_shared_Broker::SystemTimer__lambda_a04f1fa45023656142eaad50f63dd072__bool_

- ea: `0x180012878`
- end: `0x18001291c`
- name: `std::make_shared_Broker::SystemTimer__lambda_a04f1fa45023656142eaad50f63dd072__bool_`
- size: `164`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180012244`

## callees

- `0x180012df4`
- `0x180017e64`

## pseudocode

```c
_QWORD *__fastcall std::make_shared_Broker::SystemTimer__lambda_a04f1fa45023656142eaad50f63dd072__bool_(
        _QWORD *a1,
        _QWORD *a2,
        unsigned __int8 *a3)
{
  _QWORD v7[9]; // [rsp+28h] [rbp-60h] BYREF
  char *v8; // [rsp+90h] [rbp+8h]

  v8 = (char *)operator new(0x78u);
  *(_OWORD *)v8 = 0;
  *((_DWORD *)v8 + 2) = 1;
  *((_DWORD *)v8 + 3) = 1;
  *(_QWORD *)v8 = &std::_Ref_count_obj2<Broker::SystemTimer>::`vftable';
  v7[0] = off_18001D298;
  v7[1] = *a2;
  v7[7] = v7;
  Broker::SystemTimer::SystemTimer((struct _RTL_SRWLOCK *)v8 + 2, (__int64)v7, *a3);
  *a1 = v8 + 16;
  a1[1] = v8;
  return a1;
}

```

## disassembly

```asm
0x180012878  mov     [rsp+arg_8], rbx
0x18001287d  mov     [rsp+arg_10], rsi
0x180012882  mov     [rsp+arg_0], rcx
0x180012887  push    rdi
0x180012888  push    r14
0x18001288a  push    r15
0x18001288c  sub     rsp, 70h
0x180012890  mov     r14, r8
0x180012893  mov     rdi, rdx
0x180012896  mov     r15, rcx
0x180012899  mov     ecx, 78h ; 'x'; Size
0x18001289e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800128a3  mov     rsi, rax
0x1800128a6  mov     [rsp+88h+arg_0], rax
0x1800128ae  xorps   xmm0, xmm0
0x1800128b1  movups  xmmword ptr [rax], xmm0
0x1800128b4  mov     eax, 1
0x1800128b9  mov     [rsi+8], eax
0x1800128bc  mov     [rsi+0Ch], eax
0x1800128bf  lea     rax, ??_7?$_Ref_count_obj2@VSystemTimer@Broker@@@std@@6B@; const std::_Ref_count_obj2<Broker::SystemTimer>::`vftable'
0x1800128c6  mov     [rsi], rax
0x1800128c9  lea     rbx, [rsi+10h]
0x1800128cd  lea     rax, off_18001D298
0x1800128d4  mov     [rsp+88h+var_60], rax
0x1800128d9  mov     rax, [rdi]
0x1800128dc  mov     [rsp+88h+var_58], rax
0x1800128e1  lea     rax, [rsp+88h+var_60]
0x1800128e6  mov     [rsp+88h+var_28], rax
0x1800128eb  mov     r8b, [r14]
0x1800128ee  lea     rdx, [rsp+88h+var_60]
0x1800128f3  mov     rcx, rbx; pv
0x1800128f6  call    ??0SystemTimer@Broker@@QEAA@V?$function@$$A6AXXZ@std@@_N@Z; Broker::SystemTimer::SystemTimer(std::function<void (void)>,bool)
0x1800128fb  nop
0x1800128fc  mov     [r15], rbx
0x1800128ff  mov     [r15+8], rsi
0x180012903  mov     rax, r15
0x180012906  lea     r11, [rsp+88h+var_18]
0x18001290b  mov     rbx, [r11+28h]
0x18001290f  mov     rsi, [r11+30h]
0x180012913  mov     rsp, r11
0x180012916  pop     r15
0x180012918  pop     r14
0x18001291a  pop     rdi
0x18001291b  retn
```
