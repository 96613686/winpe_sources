# __crt_strtox::convert_hexadecimal_string_to_floating_type_common(__crt_strtox::floating_point_string const &,__crt_strtox::floating_point_value const &)

- ea: `0x140009a94`
- end: `0x140009b40`
- name: `?convert_hexadecimal_string_to_floating_type_common@__crt_strtox@@YA?AW4SLD_STATUS@@AEBUfloating_point_string@1@AEBVfloating_point_value@1@@Z`
- size: `172`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000625c`
- `0x1400063cc`

## callees

- `0x14000778c`
- `0x140009a94`

## pseudocode

```c
__int64 __fastcall __crt_strtox::convert_hexadecimal_string_to_floating_type_common(__int64 a1, __int64 a2)
{
  unsigned __int64 v3; // rcx
  unsigned __int8 *v4; // r8
  __int64 v5; // r11
  unsigned int v6; // r10d
  unsigned __int64 v7; // rdx
  __int64 v8; // rax
  bool i; // r9
  char v10; // al

  v3 = 0;
  v4 = (unsigned __int8 *)(a1 + 8);
  v5 = *(unsigned int *)(a1 + 4) + a1 + 8;
  v6 = *(_DWORD *)a1 + (*(_BYTE *)(a2 + 8) != 0 ? 52 : 23);
  if ( a1 + 8 != v5 )
  {
    v7 = (-(__int64)(*(_BYTE *)(a2 + 8) != 0) & 0x1FFFFFFF000000LL) + 0xFFFFFF;
    do
    {
      if ( v3 > v7 )
        break;
      v8 = *v4;
      v6 -= 4;
      ++v4;
      v3 = v8 + 16 * v3;
    }
    while ( v4 != (unsigned __int8 *)v5 );
  }
  for ( i = 1; v4 != (unsigned __int8 *)v5 && i; i = v10 == 0 )
    v10 = *v4++;
  LOBYTE(v4) = *(_BYTE *)(a1 + 776);
  return __crt_strtox::assemble_floating_point_value(v3, v6, v4);
}

```

## disassembly

```asm
0x140009a94  mov     [rsp+arg_8], rbx
0x140009a99  push    rdi
0x140009a9a  sub     rsp, 30h
0x140009a9e  mov     r9b, [rdx+8]
0x140009aa2  mov     rbx, rcx
0x140009aa5  mov     al, r9b
0x140009aa8  xor     ecx, ecx
0x140009aaa  neg     al
0x140009aac  mov     rdi, rdx
0x140009aaf  mov     eax, [rbx+4]
0x140009ab2  lea     r11, [rbx+8]
0x140009ab6  sbb     r10d, r10d
0x140009ab9  lea     r8, [rbx+8]
0x140009abd  and     r10d, 1Dh
0x140009ac1  add     r11, rax
0x140009ac4  add     r10d, 17h
0x140009ac8  add     r10d, [rbx]
0x140009acb  cmp     r8, r11
0x140009ace  jz      short loc_140009B06
0x140009ad0  neg     r9b
0x140009ad3  mov     rax, 1FFFFFFF000000h
0x140009add  sbb     rdx, rdx
0x140009ae0  and     rdx, rax
0x140009ae3  add     rdx, 0FFFFFFh
0x140009aea  cmp     rcx, rdx
0x140009aed  ja      short loc_140009B06
0x140009aef  movzx   eax, byte ptr [r8]
0x140009af3  sub     r10d, 4
0x140009af7  shl     rcx, 4
0x140009afb  inc     r8
0x140009afe  add     rcx, rax
0x140009b01  cmp     r8, r11
0x140009b04  jnz     short loc_140009AEA
0x140009b06  mov     r9b, 1
0x140009b09  jmp     short loc_140009B1C
0x140009b0b  test    r9b, r9b
0x140009b0e  jz      short loc_140009B21
0x140009b10  mov     al, [r8]
0x140009b13  inc     r8
0x140009b16  test    al, al
0x140009b18  setz    r9b
0x140009b1c  cmp     r8, r11
0x140009b1f  jnz     short loc_140009B0B
0x140009b21  mov     r8b, [rbx+308h]
0x140009b28  mov     edx, r10d
0x140009b2b  mov     [rsp+38h+var_18], rdi
0x140009b30  call    ?assemble_floating_point_value@__crt_strtox@@YA?AW4SLD_STATUS@@_KH_N1AEBVfloating_point_value@1@@Z
0x140009b35  mov     rbx, [rsp+38h+arg_8]
0x140009b3a  add     rsp, 30h
0x140009b3e  pop     rdi
0x140009b3f  retn
```
