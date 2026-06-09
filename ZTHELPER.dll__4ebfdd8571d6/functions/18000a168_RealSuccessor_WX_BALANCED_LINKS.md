# RealSuccessor(_WX_BALANCED_LINKS *)

- ea: `0x18000a168`
- end: `0x18000a1a5`
- name: `?RealSuccessor@@YAPEAU_WX_BALANCED_LINKS@@PEAU1@@Z`
- size: `61`
- prototype: `struct _WX_BALANCED_LINKS *__fastcall(struct _WX_BALANCED_LINKS *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a304`

## callees

- `0x18000a168`

## pseudocode

```c
struct _WX_BALANCED_LINKS *__fastcall RealSuccessor(struct _WX_BALANCED_LINKS *a1)
{
  struct _WX_BALANCED_LINKS *result; // rax
  struct _WX_BALANCED_LINKS *v2; // rax
  __int64 v3; // rdx

  result = (struct _WX_BALANCED_LINKS *)*((_QWORD *)a1 + 2);
  if ( result )
  {
    while ( *((_QWORD *)result + 1) )
      result = (struct _WX_BALANCED_LINKS *)*((_QWORD *)result + 1);
  }
  else
  {
    v2 = *(struct _WX_BALANCED_LINKS **)a1;
    if ( *(struct _WX_BALANCED_LINKS **)(*(_QWORD *)a1 + 16LL) == a1 )
    {
      do
      {
        v3 = *(_QWORD *)v2;
        a1 = v2;
        v2 = (struct _WX_BALANCED_LINKS *)v3;
      }
      while ( *(struct _WX_BALANCED_LINKS **)(v3 + 16) == a1 );
    }
    else
    {
      v3 = *(_QWORD *)a1;
    }
    result = 0;
    if ( *(struct _WX_BALANCED_LINKS **)(v3 + 8) == a1 )
      return (struct _WX_BALANCED_LINKS *)v3;
  }
  return result;
}

```

## disassembly

```asm
0x18000a168  mov     rax, [rcx+10h]
0x18000a16c  test    rax, rax
0x18000a16f  jnz     short loc_18000A18F
0x18000a171  mov     rax, [rcx]
0x18000a174  cmp     [rax+10h], rcx
0x18000a178  jnz     short loc_18000A197
0x18000a17a  mov     rdx, [rax]
0x18000a17d  mov     rcx, rax
0x18000a180  mov     rax, rdx
0x18000a183  cmp     [rdx+10h], rcx
0x18000a187  jz      short loc_18000A17A
0x18000a189  jmp     short loc_18000A19A
0x18000a18b  mov     rax, [rax+8]
0x18000a18f  cmp     qword ptr [rax+8], 0
0x18000a194  jnz     short loc_18000A18B
0x18000a196  retn
0x18000a197  mov     rdx, rax
0x18000a19a  xor     eax, eax
0x18000a19c  cmp     [rdx+8], rcx
0x18000a1a0  cmovz   rax, rdx
0x18000a1a4  retn
```
