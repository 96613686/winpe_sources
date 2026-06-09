# XC_WriteHFlex1

- ea: `0x180052898`
- end: `0x180052a09`
- name: `XC_WriteHFlex1`
- size: `369`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18005017c`

## callees

- `0x180001ee0`
- `0x1800028d8`
- `0x18004e048`
- `0x18004f464`
- `0x180050770`
- `0x180052898`

## pseudocode

```c
__int64 __fastcall XC_WriteHFlex1(__int64 a1, unsigned int a2)
{
  _BYTE v5[80]; // [rsp+80h] [rbp-B8h] BYREF
  _BYTE v6[80]; // [rsp+D0h] [rbp-68h] BYREF

  memset_0(v5, 0, 0x44u);
  memset_0(v6, 0, 0x44u);
  if ( *(_WORD *)(a1 + 22736) != 9 )
    XCF_FatalErrorHandler(a1, 14);
  PSVSubtract(a1, v5, *(_QWORD *)(a1 + 26048), *(_QWORD *)(a1 + 21976));
  PSVSubtract(a1, v6, v5, *(_QWORD *)(a1 + 21992));
  PSVSubtract(a1, *(_QWORD *)(a1 + 26064), v6, *(_QWORD *)(a1 + 22024));
  return WriteExpandedFlexCurveTo(
           a1,
           *(_QWORD *)(a1 + 21968),
           *(_QWORD *)(a1 + 21976),
           *(_QWORD *)(a1 + 21984),
           *(_QWORD *)(a1 + 21992),
           *(_QWORD *)(a1 + 22000),
           *(_QWORD *)(a1 + 26048),
           *(_QWORD *)(a1 + 22008),
           *(_QWORD *)(a1 + 26048),
           *(_QWORD *)(a1 + 22016),
           *(_QWORD *)(a1 + 22024),
           *(_QWORD *)(a1 + 22032),
           *(_QWORD *)(a1 + 26064),
           *(_QWORD *)(a1 + 26056),
           a2);
}

```

## disassembly

```asm
0x180052898  mov     [rsp+arg_8], rbx
0x18005289d  push    rdi
0x18005289e  sub     rsp, 130h
0x1800528a5  mov     rax, cs:__security_cookie
0x1800528ac  xor     rax, rsp
0x1800528af  mov     [rsp+138h+var_18], rax
0x1800528b7  mov     edi, edx
0x1800528b9  mov     rbx, rcx
0x1800528bc  xor     edx, edx; Val
0x1800528be  lea     rcx, [rsp+138h+var_B8]; void *
0x1800528c6  lea     r8d, [rdx+44h]; Size
0x1800528ca  call    memset_0
0x1800528cf  xor     edx, edx; Val
0x1800528d1  lea     rcx, [rsp+138h+var_68]; void *
0x1800528d9  lea     r8d, [rdx+44h]; Size
0x1800528dd  call    memset_0
0x1800528e2  cmp     word ptr [rbx+58D0h], 9
0x1800528ea  mov     rcx, rbx
0x1800528ed  jnz     loc_1800529FE
0x1800528f3  mov     r9, [rbx+55D8h]
0x1800528fa  lea     rdx, [rsp+138h+var_B8]
0x180052902  mov     r8, [rbx+65C0h]
0x180052909  call    PSVSubtract
0x18005290e  mov     r9, [rbx+55E8h]
0x180052915  lea     r8, [rsp+138h+var_B8]
0x18005291d  mov     rcx, rbx
0x180052920  lea     rdx, [rsp+138h+var_68]
0x180052928  call    PSVSubtract
0x18005292d  mov     r9, [rbx+5608h]
0x180052934  lea     r8, [rsp+138h+var_68]
0x18005293c  mov     rdx, [rbx+65D0h]
0x180052943  mov     rcx, rbx
0x180052946  call    PSVSubtract
0x18005294b  mov     rdx, [rbx+65C0h]
0x180052952  mov     rcx, rbx
0x180052955  mov     rax, [rbx+65C8h]
0x18005295c  mov     r9, [rbx+55E0h]
0x180052963  mov     r8, [rbx+55D8h]
0x18005296a  mov     [rsp+138h+var_C8], edi
0x18005296e  mov     [rsp+138h+var_D0], rax
0x180052973  mov     rax, [rbx+65D0h]
0x18005297a  mov     [rsp+138h+var_D8], rax
0x18005297f  mov     rax, [rbx+5610h]
0x180052986  mov     [rsp+138h+var_E0], rax
0x18005298b  mov     rax, [rbx+5608h]
0x180052992  mov     [rsp+138h+var_E8], rax
0x180052997  mov     rax, [rbx+5600h]
0x18005299e  mov     [rsp+138h+var_F0], rax
0x1800529a3  mov     rax, [rbx+55F8h]
0x1800529aa  mov     [rsp+138h+var_F8], rdx
0x1800529af  mov     [rsp+138h+var_100], rax
0x1800529b4  mov     rax, [rbx+55F0h]
0x1800529bb  mov     [rsp+138h+var_108], rdx
0x1800529c0  mov     rdx, [rbx+55D0h]
0x1800529c7  mov     [rsp+138h+var_110], rax
0x1800529cc  mov     rax, [rbx+55E8h]
0x1800529d3  mov     [rsp+138h+var_118], rax
0x1800529d8  call    WriteExpandedFlexCurveTo
0x1800529dd  mov     rcx, [rsp+138h+var_18]
0x1800529e5  xor     rcx, rsp; StackCookie
0x1800529e8  call    __security_check_cookie
0x1800529ed  mov     rbx, [rsp+138h+arg_8]
0x1800529f5  add     rsp, 130h
0x1800529fc  pop     rdi
0x1800529fd  retn
0x1800529fe  mov     edx, 0Eh
0x180052a03  call    XCF_FatalErrorHandler
```
