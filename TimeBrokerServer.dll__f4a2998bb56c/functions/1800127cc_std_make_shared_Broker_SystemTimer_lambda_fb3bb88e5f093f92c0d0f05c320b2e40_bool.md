# std::make_shared_Broker::SystemTimer__lambda_fb3bb88e5f093f92c0d0f05c320b2e40__bool_

- ea: `0x1800127cc`
- end: `0x180012870`
- name: `std::make_shared_Broker::SystemTimer__lambda_fb3bb88e5f093f92c0d0f05c320b2e40__bool_`
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
_QWORD *__fastcall std::make_shared_Broker::SystemTimer__lambda_fb3bb88e5f093f92c0d0f05c320b2e40__bool_(
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
  v7[0] = off_18001D1A8;
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
0x1800127cc  mov     [rsp+arg_8], rbx
0x1800127d1  mov     [rsp+arg_10], rsi
0x1800127d6  mov     [rsp+arg_0], rcx
0x1800127db  push    rdi
0x1800127dc  push    r14
0x1800127de  push    r15
0x1800127e0  sub     rsp, 70h
0x1800127e4  mov     r14, r8
0x1800127e7  mov     rdi, rdx
0x1800127ea  mov     r15, rcx
0x1800127ed  mov     ecx, 78h ; 'x'; Size
0x1800127f2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800127f7  mov     rsi, rax
0x1800127fa  mov     [rsp+88h+arg_0], rax
0x180012802  xorps   xmm0, xmm0
0x180012805  movups  xmmword ptr [rax], xmm0
0x180012808  mov     eax, 1
0x18001280d  mov     [rsi+8], eax
0x180012810  mov     [rsi+0Ch], eax
0x180012813  lea     rax, ??_7?$_Ref_count_obj2@VSystemTimer@Broker@@@std@@6B@; const std::_Ref_count_obj2<Broker::SystemTimer>::`vftable'
0x18001281a  mov     [rsi], rax
0x18001281d  lea     rbx, [rsi+10h]
0x180012821  lea     rax, off_18001D1A8
0x180012828  mov     [rsp+88h+var_60], rax
0x18001282d  mov     rax, [rdi]
0x180012830  mov     [rsp+88h+var_58], rax
0x180012835  lea     rax, [rsp+88h+var_60]
0x18001283a  mov     [rsp+88h+var_28], rax
0x18001283f  mov     r8b, [r14]
0x180012842  lea     rdx, [rsp+88h+var_60]
0x180012847  mov     rcx, rbx; pv
0x18001284a  call    ??0SystemTimer@Broker@@QEAA@V?$function@$$A6AXXZ@std@@_N@Z; Broker::SystemTimer::SystemTimer(std::function<void (void)>,bool)
0x18001284f  nop
0x180012850  mov     [r15], rbx
0x180012853  mov     [r15+8], rsi
0x180012857  mov     rax, r15
0x18001285a  lea     r11, [rsp+88h+var_18]
0x18001285f  mov     rbx, [r11+28h]
0x180012863  mov     rsi, [r11+30h]
0x180012867  mov     rsp, r11
0x18001286a  pop     r15
0x18001286c  pop     r14
0x18001286e  pop     rdi
0x18001286f  retn
```
