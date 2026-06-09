# BfsRemoveFileEntryFromDeleteList

- ea: `0x14000d6f0`
- end: `0x14000d72c`
- name: `BfsRemoveFileEntryFromDeleteList`
- size: `60`
- prototype: `_QWORD *__fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x14000c4ac`
- `0x14000c7e8`

## callees

- `0x14000d6f0`

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
0x14000d6f0  xor     r9d, r9d
0x14000d6f3  lea     rax, [rcx+18h]
0x14000d6f7  mov     [rcx+28h], r9b
0x14000d6fb  mov     r8, [rax]
0x14000d6fe  cmp     [r8+8], rax
0x14000d702  jnz     short loc_14000D725
0x14000d704  mov     rdx, [rax+8]
0x14000d708  cmp     [rdx], rax
0x14000d70b  jnz     short loc_14000D725
0x14000d70d  mov     [rdx], r8
0x14000d710  mov     [r8+8], rdx
0x14000d714  mov     [rax], r9
0x14000d717  mov     [rcx+20h], r9
0x14000d71b  mov     [rcx+30h], r9
0x14000d71f  mov     [rcx+38h], r9
0x14000d723  retn
0x14000d725  mov     ecx, 3
0x14000d72a  int     29h; Win8: RtlFailFast(ecx)
```
