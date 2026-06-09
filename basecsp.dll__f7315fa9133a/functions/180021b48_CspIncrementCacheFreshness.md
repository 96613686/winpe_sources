# CspIncrementCacheFreshness

- ea: `0x180021b48`
- end: `0x180021bc0`
- name: `CspIncrementCacheFreshness`
- size: `120`
- prototype: `__int64 __fastcall(struct _CARD_STATE *)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x18001da50`
- `0x18001db2c`
- `0x18001dbec`
- `0x18001dd04`
- `0x18001ebf4`

## callees

- `0x18002140c`
- `0x180021554`
- `0x180021b48`

## pseudocode

```c
unsigned int __fastcall CspIncrementCacheFreshness(struct _CARD_STATE *a1, char a2, __int64 a3)
{
  unsigned int result; // eax
  __int64 v7; // rcx

  *(_DWORD *)a3 = 0;
  *(_WORD *)(a3 + 4) = 0;
  result = I_CspReadCardCacheFile(a1, (struct _CARD_CACHE_FILE_FORMAT *)a3);
  if ( !result )
  {
    if ( (a2 & 1) != 0 )
      ++*(_BYTE *)(a3 + 1);
    if ( (a2 & 2) != 0 )
      ++*(_WORD *)(a3 + 2);
    if ( (a2 & 4) != 0 )
      ++*(_WORD *)(a3 + 4);
    v7 = *((_QWORD *)a1 + 76);
    *(_DWORD *)v7 = *(_DWORD *)a3;
    *(_WORD *)(v7 + 4) = *(_WORD *)(a3 + 4);
    return I_CspWriteCardCacheFile(a1);
  }
  return result;
}

```

## disassembly

```asm
0x180021b48  mov     [rsp+arg_0], rbx
0x180021b4d  mov     [rsp+arg_8], rsi
0x180021b52  push    rdi
0x180021b53  sub     rsp, 20h
0x180021b57  xor     eax, eax
0x180021b59  mov     edi, edx
0x180021b5b  mov     [r8], eax
0x180021b5e  mov     rdx, r8; struct _CARD_CACHE_FILE_FORMAT *
0x180021b61  mov     [r8+4], ax
0x180021b66  mov     rbx, r8
0x180021b69  mov     rsi, rcx
0x180021b6c  call    ?I_CspReadCardCacheFile@@YAKPEAU_CARD_STATE@@PEAU_CARD_CACHE_FILE_FORMAT@@@Z; I_CspReadCardCacheFile(_CARD_STATE *,_CARD_CACHE_FILE_FORMAT *)
0x180021b71  test    eax, eax
0x180021b73  jnz     short loc_180021BB0
0x180021b75  mov     ax, 1
0x180021b79  test    al, dil
0x180021b7c  jz      short loc_180021B81
0x180021b7e  add     [rbx+1], al
0x180021b81  test    dil, 2
0x180021b85  jz      short loc_180021B8B
0x180021b87  add     [rbx+2], ax
0x180021b8b  test    dil, 4
0x180021b8f  jz      short loc_180021B95
0x180021b91  add     [rbx+4], ax
0x180021b95  mov     rcx, [rsi+260h]
0x180021b9c  mov     eax, [rbx]
0x180021b9e  mov     [rcx], eax
0x180021ba0  movzx   eax, word ptr [rbx+4]
0x180021ba4  mov     [rcx+4], ax
0x180021ba8  mov     rcx, rsi; struct _CARD_STATE *
0x180021bab  call    ?I_CspWriteCardCacheFile@@YAKPEAU_CARD_STATE@@@Z; I_CspWriteCardCacheFile(_CARD_STATE *)
0x180021bb0  mov     rbx, [rsp+28h+arg_0]
0x180021bb5  mov     rsi, [rsp+28h+arg_8]
0x180021bba  add     rsp, 20h
0x180021bbe  pop     rdi
0x180021bbf  retn
```
