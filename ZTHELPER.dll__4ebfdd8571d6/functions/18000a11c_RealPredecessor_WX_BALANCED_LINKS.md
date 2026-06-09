# RealPredecessor(_WX_BALANCED_LINKS *)

- ea: `0x18000a11c`
- end: `0x18000a161`
- name: `?RealPredecessor@@YAPEAU_WX_BALANCED_LINKS@@PEAU1@@Z`
- size: `69`
- prototype: `struct _WX_BALANCED_LINKS *__fastcall(struct _WX_BALANCED_LINKS *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a268`

## callees

- `0x18000a11c`

## pseudocode

```c
struct _WX_BALANCED_LINKS *__fastcall RealPredecessor(struct _WX_BALANCED_LINKS *a1)
{
  struct _WX_BALANCED_LINKS *result; // rax
  struct _WX_BALANCED_LINKS *v2; // rdx
  struct _WX_BALANCED_LINKS *v3; // rax
  struct _WX_BALANCED_LINKS *v4; // rcx

  result = (struct _WX_BALANCED_LINKS *)*((_QWORD *)a1 + 1);
  v2 = a1;
  if ( result )
  {
    while ( *((_QWORD *)result + 2) )
      result = (struct _WX_BALANCED_LINKS *)*((_QWORD *)result + 2);
  }
  else
  {
    v3 = *(struct _WX_BALANCED_LINKS **)a1;
    if ( *(struct _WX_BALANCED_LINKS **)(*(_QWORD *)a1 + 8LL) == a1 )
    {
      do
      {
        v4 = *(struct _WX_BALANCED_LINKS **)v3;
        v2 = v3;
        v3 = v4;
      }
      while ( *((struct _WX_BALANCED_LINKS **)v4 + 1) == v2 );
    }
    else
    {
      v4 = *(struct _WX_BALANCED_LINKS **)a1;
    }
    result = 0;
    if ( *((struct _WX_BALANCED_LINKS **)v4 + 2) == v2 && *(struct _WX_BALANCED_LINKS **)v4 != v4 )
      return v4;
  }
  return result;
}

```

## disassembly

```asm
0x18000a11c  mov     rax, [rcx+8]
0x18000a120  mov     rdx, rcx
0x18000a123  test    rax, rax
0x18000a126  jnz     short loc_18000A146
0x18000a128  mov     rax, [rcx]
0x18000a12b  cmp     [rax+8], rcx
0x18000a12f  jnz     short loc_18000A14E
0x18000a131  mov     rcx, [rax]
0x18000a134  mov     rdx, rax
0x18000a137  mov     rax, rcx
0x18000a13a  cmp     [rcx+8], rdx
0x18000a13e  jz      short loc_18000A131
0x18000a140  jmp     short loc_18000A151
0x18000a142  mov     rax, [rax+10h]
0x18000a146  cmp     qword ptr [rax+10h], 0
0x18000a14b  jnz     short loc_18000A142
0x18000a14d  retn
0x18000a14e  mov     rcx, rax
0x18000a151  xor     eax, eax
0x18000a153  cmp     [rcx+10h], rdx
0x18000a157  jnz     short locret_18000A160
0x18000a159  cmp     [rcx], rcx
0x18000a15c  cmovnz  rax, rcx
0x18000a160  retn
```
