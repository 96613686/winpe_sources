# std::make_shared_Broker::SystemTimer__lambda_5558ee1e6b2dcc87304ff1cbde56dffa__bool_

- ea: `0x1800126ec`
- end: `0x180012790`
- name: `std::make_shared_Broker::SystemTimer__lambda_5558ee1e6b2dcc87304ff1cbde56dffa__bool_`
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
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall std::make_shared_Broker::SystemTimer__lambda_5558ee1e6b2dcc87304ff1cbde56dffa__bool_(
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
  v7[0] = off_18001D1D8;
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
0x1800126ec  mov     [rsp+arg_8], rbx
0x1800126f1  mov     [rsp+arg_10], rsi
0x1800126f6  mov     [rsp+arg_0], rcx
0x1800126fb  push    rdi
0x1800126fc  push    r14
0x1800126fe  push    r15
0x180012700  sub     rsp, 70h
0x180012704  mov     r14, r8
0x180012707  mov     rdi, rdx
0x18001270a  mov     r15, rcx
0x18001270d  mov     ecx, 78h ; 'x'; Size
0x180012712  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180012717  mov     rsi, rax
0x18001271a  mov     [rsp+88h+arg_0], rax
0x180012722  xorps   xmm0, xmm0
0x180012725  movups  xmmword ptr [rax], xmm0
0x180012728  mov     eax, 1
0x18001272d  mov     [rsi+8], eax
0x180012730  mov     [rsi+0Ch], eax
0x180012733  lea     rax, ??_7?$_Ref_count_obj2@VSystemTimer@Broker@@@std@@6B@; const std::_Ref_count_obj2<Broker::SystemTimer>::`vftable'
0x18001273a  mov     [rsi], rax
0x18001273d  lea     rbx, [rsi+10h]
0x180012741  lea     rax, off_18001D1D8
0x180012748  mov     [rsp+88h+var_60], rax
0x18001274d  mov     rax, [rdi]
0x180012750  mov     [rsp+88h+var_58], rax
0x180012755  lea     rax, [rsp+88h+var_60]
0x18001275a  mov     [rsp+88h+var_28], rax
0x18001275f  mov     r8b, [r14]
0x180012762  lea     rdx, [rsp+88h+var_60]
0x180012767  mov     rcx, rbx; pv
0x18001276a  call    ??0SystemTimer@Broker@@QEAA@V?$function@$$A6AXXZ@std@@_N@Z; Broker::SystemTimer::SystemTimer(std::function<void (void)>,bool)
0x18001276f  nop
0x180012770  mov     [r15], rbx
0x180012773  mov     [r15+8], rsi
0x180012777  mov     rax, r15
0x18001277a  lea     r11, [rsp+88h+var_18]
0x18001277f  mov     rbx, [r11+28h]
0x180012783  mov     rsi, [r11+30h]
0x180012787  mov     rsp, r11
0x18001278a  pop     r15
0x18001278c  pop     r14
0x18001278e  pop     rdi
0x18001278f  retn
```
