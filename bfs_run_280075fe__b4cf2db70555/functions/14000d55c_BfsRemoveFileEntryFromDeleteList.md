# BfsRemoveFileEntryFromDeleteList

- ea: `0x14000d55c`
- end: `0x14000d598`
- name: `BfsRemoveFileEntryFromDeleteList`
- size: `60`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x14000c31c`
- `0x14000c658`

## callees

- `0x14000d55c`

## pseudocode

```c
_QWORD *__fastcall BfsRemoveFileEntryFromDeleteList(__int64 a1)
{
  _QWORD *result; // rax
  __int64 v2; // r8
  _QWORD *v3; // rdx

  result = (_QWORD *)(a1 + 24);
  *(_BYTE *)(a1 + 40) = 0;
  v2 = *(_QWORD *)(a1 + 24);
  if ( *(_QWORD *)(v2 + 8) != a1 + 24 || (v3 = *(_QWORD **)(a1 + 32), (_QWORD *)*v3 != result) )
    __fastfail(3u);
  *v3 = v2;
  *(_QWORD *)(v2 + 8) = v3;
  *result = 0;
  *(_QWORD *)(a1 + 32) = 0;
  *(_QWORD *)(a1 + 48) = 0;
  *(_QWORD *)(a1 + 56) = 0;
  return result;
}

```

## disassembly

```asm
0x14000d55c  xor     r9d, r9d
0x14000d55f  lea     rax, [rcx+18h]
0x14000d563  mov     [rcx+28h], r9b
0x14000d567  mov     r8, [rax]
0x14000d56a  cmp     [r8+8], rax
0x14000d56e  jnz     short loc_14000D591
0x14000d570  mov     rdx, [rax+8]
0x14000d574  cmp     [rdx], rax
0x14000d577  jnz     short loc_14000D591
0x14000d579  mov     [rdx], r8
0x14000d57c  mov     [r8+8], rdx
0x14000d580  mov     [rax], r9
0x14000d583  mov     [rcx+20h], r9
0x14000d587  mov     [rcx+30h], r9
0x14000d58b  mov     [rcx+38h], r9
0x14000d58f  retn
0x14000d591  mov     ecx, 3
0x14000d596  int     29h; Win8: RtlFailFast(ecx)
```
