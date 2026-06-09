# __crt_strtox::convert_hexadecimal_string_to_floating_type_common(__crt_strtox::floating_point_string const &,__crt_strtox::floating_point_value const &)

- ea: `0x1800220e0`
- end: `0x18002218c`
- name: `?convert_hexadecimal_string_to_floating_type_common@__crt_strtox@@YA?AW4SLD_STATUS@@AEBUfloating_point_string@1@AEBVfloating_point_value@1@@Z`
- size: `172`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001dfd0`
- `0x18001e140`

## callees

- `0x18001fd90`
- `0x1800220e0`

## pseudocode

```c
__int64 __fastcall __crt_strtox::convert_hexadecimal_string_to_floating_type_common(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  unsigned __int64 v5; // rcx
  unsigned __int8 *v7; // r8
  __int64 v8; // r11
  unsigned int v9; // r10d
  unsigned __int64 v10; // rdx
  __int64 v11; // rax
  char v12; // al

  v5 = 0;
  v7 = (unsigned __int8 *)(a1 + 8);
  v8 = *(unsigned int *)(a1 + 4) + a1 + 8;
  v9 = *(_DWORD *)a1 + (*(_BYTE *)(a2 + 8) != 0 ? 52 : 23);
  if ( a1 + 8 != v8 )
  {
    v10 = (-(__int64)(*(_BYTE *)(a2 + 8) != 0) & 0x1FFFFFFF000000LL) + 0xFFFFFF;
    do
    {
      if ( v5 > v10 )
        break;
      v11 = *v7;
      v9 -= 4;
      ++v7;
      v5 = v11 + 16 * v5;
    }
    while ( v7 != (unsigned __int8 *)v8 );
  }
  LOBYTE(a4) = 1;
  while ( v7 != (unsigned __int8 *)v8 && (_BYTE)a4 )
  {
    v12 = *v7++;
    LOBYTE(a4) = v12 == 0;
  }
  LOBYTE(v7) = *(_BYTE *)(a1 + 776);
  return __crt_strtox::assemble_floating_point_value(v5, v9, v7, a4, a2);
}

```

## disassembly

```asm
0x1800220e0  mov     [rsp+arg_0], rbx
0x1800220e5  push    rdi
0x1800220e6  sub     rsp, 30h
0x1800220ea  mov     r9b, [rdx+8]
0x1800220ee  mov     rbx, rcx
0x1800220f1  mov     al, r9b
0x1800220f4  xor     ecx, ecx
0x1800220f6  neg     al
0x1800220f8  mov     rdi, rdx
0x1800220fb  mov     eax, [rbx+4]
0x1800220fe  lea     r11, [rbx+8]
0x180022102  sbb     r10d, r10d
0x180022105  lea     r8, [rbx+8]
0x180022109  and     r10d, 1Dh
0x18002210d  add     r11, rax
0x180022110  add     r10d, 17h
0x180022114  add     r10d, [rbx]
0x180022117  cmp     r8, r11
0x18002211a  jz      short loc_180022152
0x18002211c  neg     r9b
0x18002211f  mov     rax, 1FFFFFFF000000h
0x180022129  sbb     rdx, rdx
0x18002212c  and     rdx, rax
0x18002212f  add     rdx, 0FFFFFFh
0x180022136  cmp     rcx, rdx
0x180022139  ja      short loc_180022152
0x18002213b  movzx   eax, byte ptr [r8]
0x18002213f  sub     r10d, 4
0x180022143  shl     rcx, 4
0x180022147  inc     r8
0x18002214a  add     rcx, rax
0x18002214d  cmp     r8, r11
0x180022150  jnz     short loc_180022136
0x180022152  mov     r9b, 1
0x180022155  jmp     short loc_180022168
0x180022157  test    r9b, r9b
0x18002215a  jz      short loc_18002216D
0x18002215c  mov     al, [r8]
0x18002215f  inc     r8
0x180022162  test    al, al
0x180022164  setz    r9b
0x180022168  cmp     r8, r11
0x18002216b  jnz     short loc_180022157
0x18002216d  mov     r8b, [rbx+308h]
0x180022174  mov     edx, r10d
0x180022177  mov     [rsp+38h+var_18], rdi
0x18002217c  call    ?assemble_floating_point_value@__crt_strtox@@YA?AW4SLD_STATUS@@_KH_N1AEBVfloating_point_value@1@@Z; __crt_strtox::assemble_floating_point_value(unsigned __int64,int,bool,bool,__crt_strtox::floating_point_value const &)
0x180022181  mov     rbx, [rsp+38h+arg_0]
0x180022186  add     rsp, 30h
0x18002218a  pop     rdi
0x18002218b  retn
```
