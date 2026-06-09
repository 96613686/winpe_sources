# ReplaceCharsW

- ea: `0x180001f50`
- end: `0x180001f73`
- name: `ReplaceCharsW`
- size: `35`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180001cb0`
- `0x180003dc0`

## callees

- `0x180001f50`

## pseudocode

```c
__int64 __fastcall ReplaceCharsW(_WORD *a1, __int16 a2, __int16 a3)
{
  __int64 result; // rax

  result = 0;
  while ( *a1 )
  {
    if ( *a1 == a2 )
    {
      *a1 = a3;
      result = (unsigned int)(result + 1);
    }
    ++a1;
  }
  return result;
}

```

## disassembly

```asm
0x180001f50  xor     r10d, r10d
0x180001f53  mov     eax, r10d
0x180001f56  jmp     short loc_180001F68
0x180001f58  cmp     r9w, dx
0x180001f5c  jnz     short loc_180001F64
0x180001f5e  mov     [rcx], r8w
0x180001f62  inc     eax
0x180001f64  add     rcx, 2
0x180001f68  movzx   r9d, word ptr [rcx]
0x180001f6c  test    r9w, r9w
0x180001f70  jnz     short loc_180001F58
0x180001f72  retn
```
