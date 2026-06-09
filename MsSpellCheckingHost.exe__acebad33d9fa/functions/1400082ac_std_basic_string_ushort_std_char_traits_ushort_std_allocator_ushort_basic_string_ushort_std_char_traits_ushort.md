# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &&)

- ea: `0x1400082ac`
- end: `0x14000832c`
- name: `??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z`
- size: `128`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x14000f170`
- `0x14001093c`
- `0x1400109c4`

## callees

- `0x1400020d2`
- `0x1400082ac`

## pseudocode

```c
_QWORD *__fastcall std::wstring::wstring(_QWORD *a1, _QWORD *a2)
{
  a1[3] = 7;
  a1[2] = 0;
  *(_WORD *)a1 = 0;
  if ( a2[3] >= 8u )
  {
    *a1 = *a2;
    *a2 = 0;
  }
  else if ( a2[2] != -1 )
  {
    memmove_0(a1, a2, 2 * (a2[2] + 1LL));
  }
  a1[2] = a2[2];
  a1[3] = a2[3];
  a2[3] = 7;
  a2[2] = 0;
  *(_WORD *)a2 = 0;
  return a1;
}

```

## disassembly

```asm
0x1400082ac  mov     [rsp+arg_0], rbx
0x1400082b1  push    rdi
0x1400082b2  sub     rsp, 20h
0x1400082b6  xor     eax, eax
0x1400082b8  mov     qword ptr [rcx+18h], 7
0x1400082c0  mov     qword ptr [rcx+10h], 0
0x1400082c8  mov     rbx, rdx
0x1400082cb  mov     [rcx], ax
0x1400082ce  mov     rdi, rcx
0x1400082d1  cmp     qword ptr [rdx+18h], 8
0x1400082d6  jnb     short loc_1400082EC
0x1400082d8  mov     r8, [rdx+10h]
0x1400082dc  add     r8, 1
0x1400082e0  jz      short loc_1400082F9
0x1400082e2  add     r8, r8; Size
0x1400082e5  call    memmove_0
0x1400082ea  jmp     short loc_1400082F9
0x1400082ec  mov     rax, [rdx]
0x1400082ef  mov     [rcx], rax
0x1400082f2  mov     qword ptr [rdx], 0
0x1400082f9  mov     rax, [rbx+10h]
0x1400082fd  mov     [rdi+10h], rax
0x140008301  mov     rax, [rbx+18h]
0x140008305  mov     [rdi+18h], rax
0x140008309  xor     eax, eax
0x14000830b  mov     qword ptr [rbx+18h], 7
0x140008313  mov     qword ptr [rbx+10h], 0
0x14000831b  mov     [rbx], ax
0x14000831e  mov     rax, rdi
0x140008321  mov     rbx, [rsp+28h+arg_0]
0x140008326  add     rsp, 20h
0x14000832a  pop     rdi
0x14000832b  retn
```
