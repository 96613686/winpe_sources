# PromoteNode(_WX_BALANCED_LINKS *)

- ea: `0x18000a0c8`
- end: `0x18000a115`
- name: `?PromoteNode@@YAXPEAU_WX_BALANCED_LINKS@@@Z`
- size: `77`
- prototype: `void __fastcall(__int64 **)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a1ac`

## callees

- `0x18000a0c8`

## pseudocode

```c
void __fastcall PromoteNode(__int64 **a1)
{
  __int64 *v1; // rax
  __int64 *v2; // rdx
  __int64 **v3; // r8
  __int64 **v4; // r8

  v1 = *a1;
  v2 = (__int64 *)**a1;
  if ( (__int64 **)(*a1)[1] == a1 )
  {
    v3 = (__int64 **)a1[2];
    v1[1] = (__int64)v3;
    if ( v3 )
      *v3 = v1;
    a1[2] = v1;
  }
  else
  {
    v4 = (__int64 **)a1[1];
    v1[2] = (__int64)v4;
    if ( v4 )
      *v4 = v1;
    a1[1] = v1;
  }
  *v1 = (__int64)a1;
  if ( (__int64 *)v2[1] == v1 )
    v2[1] = (__int64)a1;
  else
    v2[2] = (__int64)a1;
  *a1 = v2;
}

```

## disassembly

```asm
0x18000a0c8  mov     rax, [rcx]
0x18000a0cb  mov     rdx, [rax]
0x18000a0ce  cmp     [rax+8], rcx
0x18000a0d2  jnz     short loc_18000A0EA
0x18000a0d4  mov     r8, [rcx+10h]
0x18000a0d8  mov     [rax+8], r8
0x18000a0dc  test    r8, r8
0x18000a0df  jz      short loc_18000A0E4
0x18000a0e1  mov     [r8], rax
0x18000a0e4  mov     [rcx+10h], rax
0x18000a0e8  jmp     short loc_18000A0FE
0x18000a0ea  mov     r8, [rcx+8]
0x18000a0ee  mov     [rax+10h], r8
0x18000a0f2  test    r8, r8
0x18000a0f5  jz      short loc_18000A0FA
0x18000a0f7  mov     [r8], rax
0x18000a0fa  mov     [rcx+8], rax
0x18000a0fe  mov     [rax], rcx
0x18000a101  cmp     [rdx+8], rax
0x18000a105  jnz     short loc_18000A10D
0x18000a107  mov     [rdx+8], rcx
0x18000a10b  jmp     short loc_18000A111
0x18000a10d  mov     [rdx+10h], rcx
0x18000a111  mov     [rcx], rdx
0x18000a114  retn
```
