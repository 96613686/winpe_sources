# StringCchLengthW

- ea: `0x180007640`
- end: `0x18000766f`
- name: `StringCchLengthW`
- size: `47`
- prototype: `HRESULT __stdcall(STRSAFE_PCNZWCH psz, size_t cchMax, size_t *pcchLength)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180005910`
- `0x18000b030`
- `0x18000b0ec`
- `0x18000b400`

## callees

- `0x180007640`
- `0x180007680`

## pseudocode

```c
HRESULT __stdcall StringCchLengthW(STRSAFE_PCNZWCH psz, size_t cchMax, size_t *pcchLength)
{
  HRESULT result; // eax

  if ( psz )
  {
    result = StringLengthWorkerW(psz, 0x7FFFFFFFu, pcchLength);
    if ( result >= 0 )
      return result;
  }
  else
  {
    result = -2147024809;
  }
  if ( pcchLength )
    *pcchLength = 0;
  return result;
}

```

## disassembly

```asm
0x180007640  sub     rsp, 28h
0x180007644  test    rcx, rcx
0x180007647  jz      short loc_18000765C
0x180007649  mov     edx, 7FFFFFFFh; cchMax
0x18000764e  call    StringLengthWorkerW
0x180007653  test    eax, eax
0x180007655  js      short loc_180007661
0x180007657  add     rsp, 28h
0x18000765b  retn
0x18000765c  mov     eax, 80070057h
0x180007661  test    r8, r8
0x180007664  jz      short loc_180007657
0x180007666  mov     qword ptr [r8], 0
0x18000766d  jmp     short loc_180007657
```
