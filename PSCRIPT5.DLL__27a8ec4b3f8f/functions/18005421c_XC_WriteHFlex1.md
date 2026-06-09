# XC_WriteHFlex1

- ea: `0x18005421c`
- end: `0x18005438e`
- name: `XC_WriteHFlex1`
- size: `370`
- prototype: `__int64 __fastcall(__int64, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180051af4`

## callees

- `0x180001f20`
- `0x180002938`
- `0x18004f8e4`
- `0x180050dd4`
- `0x1800520e8`
- `0x18005421c`

## pseudocode

```c
__int64 __fastcall XC_WriteHFlex1(__int64 a1, unsigned int a2)
{
  unsigned int v5[20]; // [rsp+80h] [rbp-B8h] BYREF
  unsigned int v6[20]; // [rsp+D0h] [rbp-68h] BYREF

  memset_0(v5, 0, 0x44u);
  memset_0(v6, 0, 0x44u);
  if ( *(_WORD *)(a1 + 22736) != 9 )
    XCF_FatalErrorHandler((_JBTYPE *)a1, 14);
  PSVSubtract(a1, v5, *(unsigned int **)(a1 + 26048), *(unsigned int **)(a1 + 21976));
  PSVSubtract(a1, v6, v5, *(unsigned int **)(a1 + 21992));
  PSVSubtract(a1, *(unsigned int **)(a1 + 26064), v6, *(unsigned int **)(a1 + 22024));
  return WriteExpandedFlexCurveTo(
           a1,
           *(unsigned int **)(a1 + 21968),
           *(unsigned int **)(a1 + 21976),
           *(unsigned int **)(a1 + 21984),
           *(unsigned int **)(a1 + 21992),
           *(unsigned int **)(a1 + 22000),
           *(unsigned int **)(a1 + 26048),
           *(_DWORD **)(a1 + 22008),
           *(_DWORD **)(a1 + 26048),
           *(_DWORD **)(a1 + 22016),
           *(_DWORD **)(a1 + 22024),
           *(_DWORD **)(a1 + 22032),
           *(_DWORD **)(a1 + 26064),
           *(_DWORD **)(a1 + 26056),
           a2);
}

```

## disassembly

```asm
0x18005421c  mov     [rsp+arg_8], rbx
0x180054221  push    rdi
0x180054222  sub     rsp, 130h
0x180054229  mov     rax, cs:__security_cookie
0x180054230  xor     rax, rsp
0x180054233  mov     [rsp+138h+var_18], rax
0x18005423b  mov     edi, edx
0x18005423d  mov     rbx, rcx
0x180054240  xor     edx, edx; Val
0x180054242  lea     rcx, [rsp+138h+var_B8]; void *
0x18005424a  lea     r8d, [rdx+44h]; Size
0x18005424e  call    memset_0
0x180054253  xor     edx, edx; Val
0x180054255  lea     rcx, [rsp+138h+var_68]; void *
0x18005425d  lea     r8d, [rdx+44h]; Size
0x180054261  call    memset_0
0x180054266  cmp     word ptr [rbx+58D0h], 9
0x18005426e  mov     rcx, rbx
0x180054271  jnz     loc_180054383
0x180054277  mov     r9, [rbx+55D8h]
0x18005427e  lea     rdx, [rsp+138h+var_B8]
0x180054286  mov     r8, [rbx+65C0h]
0x18005428d  call    PSVSubtract
0x180054292  mov     r9, [rbx+55E8h]
0x180054299  lea     r8, [rsp+138h+var_B8]
0x1800542a1  mov     rcx, rbx
0x1800542a4  lea     rdx, [rsp+138h+var_68]
0x1800542ac  call    PSVSubtract
0x1800542b1  mov     r9, [rbx+5608h]
0x1800542b8  lea     r8, [rsp+138h+var_68]
0x1800542c0  mov     rdx, [rbx+65D0h]
0x1800542c7  mov     rcx, rbx
0x1800542ca  call    PSVSubtract
0x1800542cf  mov     rdx, [rbx+65C0h]
0x1800542d6  mov     rcx, rbx
0x1800542d9  mov     rax, [rbx+65C8h]
0x1800542e0  mov     r9, [rbx+55E0h]
0x1800542e7  mov     r8, [rbx+55D8h]
0x1800542ee  mov     [rsp+138h+var_C8], edi
0x1800542f2  mov     [rsp+138h+var_D0], rax
0x1800542f7  mov     rax, [rbx+65D0h]
0x1800542fe  mov     [rsp+138h+var_D8], rax
0x180054303  mov     rax, [rbx+5610h]
0x18005430a  mov     [rsp+138h+var_E0], rax
0x18005430f  mov     rax, [rbx+5608h]
0x180054316  mov     [rsp+138h+var_E8], rax
0x18005431b  mov     rax, [rbx+5600h]
0x180054322  mov     [rsp+138h+var_F0], rax
0x180054327  mov     rax, [rbx+55F8h]
0x18005432e  mov     [rsp+138h+var_F8], rdx
0x180054333  mov     [rsp+138h+var_100], rax
0x180054338  mov     rax, [rbx+55F0h]
0x18005433f  mov     [rsp+138h+var_108], rdx
0x180054344  mov     rdx, [rbx+55D0h]
0x18005434b  mov     [rsp+138h+var_110], rax
0x180054350  mov     rax, [rbx+55E8h]
0x180054357  mov     [rsp+138h+var_118], rax
0x18005435c  call    WriteExpandedFlexCurveTo
0x180054361  mov     rcx, [rsp+138h+var_18]
0x180054369  xor     rcx, rsp; StackCookie
0x18005436c  call    __security_check_cookie
0x180054371  mov     rbx, [rsp+138h+arg_8]
0x180054379  add     rsp, 130h
0x180054380  pop     rdi
0x180054381  retn
0x180054383  mov     edx, 0Eh
0x180054388  call    XCF_FatalErrorHandler
```
