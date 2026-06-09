# UpdateInternalStatsOnFlush

- ea: `0x1400260f4`
- end: `0x140026136`
- name: `UpdateInternalStatsOnFlush`
- size: `66`
- prototype: `void __fastcall(__int64, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140026004`
- `0x14003d61c`

## callees

- `0x1400260f4`

## pseudocode

```c
void __fastcall UpdateInternalStatsOnFlush(__int64 a1, unsigned int a2)
{
  __int64 *v2; // r8
  __int64 v3; // rax

  if ( a2 )
  {
    v2 = (__int64 *)(a1 + 296);
    if ( *(_DWORD *)(a1 + 312) > a2 || (v3 = *v2) == 0 )
    {
      v3 = *v2;
      *(_DWORD *)(a1 + 312) = a2;
    }
    if ( *(_DWORD *)(a1 + 308) < a2 )
      *(_DWORD *)(a1 + 308) = a2;
    *v2 = v3 + 1;
    *(_QWORD *)(a1 + 288) += a2;
  }
}

```

## disassembly

```asm
0x1400260f4  test    edx, edx
0x1400260f6  jz      short locret_140026135
0x1400260f8  lea     r8, [rcx+128h]
0x1400260ff  cmp     [rcx+138h], edx
0x140026105  ja      short loc_14002610F
0x140026107  mov     rax, [r8]
0x14002610a  test    rax, rax
0x14002610d  jnz     short loc_140026118
0x14002610f  mov     rax, [r8]
0x140026112  mov     [rcx+138h], edx
0x140026118  cmp     [rcx+134h], edx
0x14002611e  jnb     short loc_140026126
0x140026120  mov     [rcx+134h], edx
0x140026126  inc     rax
0x140026129  mov     [r8], rax
0x14002612c  mov     eax, edx
0x14002612e  add     [rcx+120h], rax
0x140026135  retn
```
