# _tlgWrapSz<char>::Fill(_EVENT_DATA_DESCRIPTOR *)

- ea: `0x180001a64`
- end: `0x180001a9a`
- name: `?Fill@?$_tlgWrapSz@D@@QEBAPEAXPEAU_EVENT_DATA_DESCRIPTOR@@@Z`
- size: `54`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180001e8c`
- `0x18000244c`
- `0x180002560`

## callees

- `0x180001a64`

## pseudocode

```c
__int64 __fastcall _tlgWrapSz<char>::Fill(const unsigned __int16 **a1, __int64 a2)
{
  const unsigned __int16 *v2; // rax
  __int64 v3; // rcx
  int v4; // ecx
  __int64 result; // rax

  v2 = *a1;
  if ( *a1 )
  {
    v3 = -1;
    do
      ++v3;
    while ( *((_BYTE *)v2 + v3) );
    v4 = v3 + 1;
  }
  else
  {
    v2 = &word_18001EE3A;
    v4 = 1;
  }
  *(_QWORD *)a2 = v2;
  result = a2;
  *(_DWORD *)(a2 + 8) = v4;
  *(_DWORD *)(a2 + 12) = 0;
  return result;
}

```

## disassembly

```asm
0x180001a64  mov     rax, [rcx]
0x180001a67  test    rax, rax
0x180001a6a  jz      short loc_180001A7D
0x180001a6c  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180001a70  inc     rcx
0x180001a73  cmp     byte ptr [rax+rcx], 0
0x180001a77  jnz     short loc_180001A70
0x180001a79  inc     ecx
0x180001a7b  jmp     short loc_180001A89
0x180001a7d  lea     rax, word_18001EE3A
0x180001a84  mov     ecx, 1
0x180001a89  mov     [rdx], rax
0x180001a8c  mov     rax, rdx
0x180001a8f  mov     [rdx+8], ecx
0x180001a92  mov     dword ptr [rdx+0Ch], 0
0x180001a99  retn
```
