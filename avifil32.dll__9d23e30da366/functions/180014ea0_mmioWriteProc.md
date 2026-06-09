# mmioWriteProc

- ea: `0x180014ea0`
- end: `0x180014ee5`
- name: `mmioWriteProc`
- size: `69`
- prototype: `__int64 __fastcall(HMMIO hmmio)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180014ea0`

## import_xrefs

- `WINMM!mmioWrite` at `0x180014ecb`
- `WINMM!mmioWrite` at `0x180014ecb`
- `WINMM!mmioSeek` at `0x180014eb5`
- `WINMM!mmioSeek` at `0x180014eb5`

## pseudocode

```c
__int64 __fastcall mmioWriteProc(HMMIO hmmio, LONG a2, unsigned int a3, const char *a4)
{
  if ( mmioSeek(hmmio, a2, 0) == -1 )
    return 0xFFFFFFFFLL;
  if ( mmioWrite(hmmio, a4, a3) != a3 )
    return (unsigned int)-1;
  return a3;
}

```

## disassembly

```asm
0x180014ea0  push    rbx
0x180014ea2  push    rbp
0x180014ea3  push    rsi
0x180014ea4  push    rdi
0x180014ea5  sub     rsp, 28h
0x180014ea9  mov     ebx, r8d
0x180014eac  mov     rsi, r9
0x180014eaf  xor     r8d, r8d; iOrigin
0x180014eb2  mov     rdi, rcx
0x180014eb5  call    cs:__imp_mmioSeek
0x180014ebb  or      ebp, 0FFFFFFFFh
0x180014ebe  cmp     eax, ebp
0x180014ec0  jz      short loc_180014EDA
0x180014ec2  mov     r8d, ebx; cch
0x180014ec5  mov     rdx, rsi; pch
0x180014ec8  mov     rcx, rdi; hmmio
0x180014ecb  call    cs:__imp_mmioWrite
0x180014ed1  cmp     eax, ebx
0x180014ed3  cmovnz  ebx, ebp
0x180014ed6  mov     eax, ebx
0x180014ed8  jmp     short loc_180014EDC
0x180014eda  mov     eax, ebp
0x180014edc  add     rsp, 28h
0x180014ee0  pop     rdi
0x180014ee1  pop     rsi
0x180014ee2  pop     rbp
0x180014ee3  pop     rbx
0x180014ee4  retn
```
