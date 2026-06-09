# OE_DPA_InsertPtr

- ea: `0x1800128f4`
- end: `0x18001297f`
- name: `OE_DPA_InsertPtr`
- size: `139`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a420`

## callees

- `0x1800127f4`
- `0x1800128f4`

## import_xrefs

- `KERNEL32!RtlMoveMemory` at `0x180012958`
- `KERNEL32!RtlMoveMemory` at `0x180012958`

## pseudocode

```c
__int64 __fastcall OE_DPA_InsertPtr(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v5; // r8d
  __int64 v6; // rdi
  __int64 result; // rax

  if ( !a1 )
    return 0xFFFFFFFFLL;
  v5 = *(_DWORD *)a1;
  v6 = 0x7FFFFFFF;
  if ( *(_DWORD *)a1 < 0x7FFFFFFFu )
    v6 = v5;
  if ( v5 + 1 < v5 )
    return 0xFFFFFFFFLL;
  if ( v5 + 1 > *(_DWORD *)(a1 + 16) )
  {
    if ( !(unsigned int)OE_DPA_Grow() )
      return 0xFFFFFFFFLL;
    v5 = *(_DWORD *)a1;
    if ( *(_DWORD *)a1 >= *(_DWORD *)(a1 + 16) )
      return 0xFFFFFFFFLL;
  }
  if ( (unsigned int)v6 < v5 )
    RtlMoveMemory(
      *(_QWORD *)(a1 + 8) + 8LL * (unsigned int)(v6 + 1),
      *(_QWORD *)(a1 + 8) + 8 * v6,
      8 * (v5 - (unsigned int)v6));
  result = (unsigned int)v6;
  *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8 * v6) = a3;
  ++*(_DWORD *)a1;
  return result;
}

```

## disassembly

```asm
0x1800128f4  mov     [rsp+arg_0], rbx
0x1800128f9  mov     [rsp+arg_8], rsi
0x1800128fe  push    rdi
0x1800128ff  sub     rsp, 20h
0x180012903  mov     rsi, r8
0x180012906  mov     rbx, rcx
0x180012909  test    rcx, rcx
0x18001290c  jz      short loc_18001296C
0x18001290e  mov     r8d, [rcx]
0x180012911  mov     edi, 7FFFFFFFh
0x180012916  cmp     r8d, edi
0x180012919  cmovb   edi, r8d
0x18001291d  lea     edx, [r8+1]
0x180012921  cmp     edx, r8d
0x180012924  jb      short loc_18001296C
0x180012926  cmp     edx, [rcx+10h]
0x180012929  jbe     short loc_18001293D
0x18001292b  call    OE_DPA_Grow
0x180012930  test    eax, eax
0x180012932  jz      short loc_18001296C
0x180012934  mov     r8d, [rbx]
0x180012937  cmp     r8d, [rbx+10h]
0x18001293b  jnb     short loc_18001296C
0x18001293d  cmp     edi, r8d
0x180012940  jnb     short loc_18001295E
0x180012942  mov     r9, [rbx+8]
0x180012946  lea     eax, [rdi+1]
0x180012949  sub     r8d, edi
0x18001294c  shl     r8d, 3
0x180012950  lea     rdx, [r9+rdi*8]
0x180012954  lea     rcx, [r9+rax*8]
0x180012958  call    cs:__imp_RtlMoveMemory
0x18001295e  mov     rcx, [rbx+8]
0x180012962  mov     eax, edi
0x180012964  mov     [rcx+rdi*8], rsi
0x180012968  inc     dword ptr [rbx]
0x18001296a  jmp     short loc_18001296F
0x18001296c  or      eax, 0FFFFFFFFh
0x18001296f  mov     rbx, [rsp+28h+arg_0]
0x180012974  mov     rsi, [rsp+28h+arg_8]
0x180012979  add     rsp, 20h
0x18001297d  pop     rdi
0x18001297e  retn
```
