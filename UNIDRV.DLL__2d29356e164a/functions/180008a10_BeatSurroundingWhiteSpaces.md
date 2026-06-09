# BeatSurroundingWhiteSpaces

- ea: `0x180008a10`
- end: `0x180008a9f`
- name: `BeatSurroundingWhiteSpaces`
- size: `143`
- prototype: ``
- caller_count: `12`
- callee_count: `2`
- tags: ``

## callers

- `0x180005ee0`
- `0x180008ab0`
- `0x180008ee4`
- `0x180009370`
- `0x180009c6c`
- `0x18000b5d0`
- `0x18000bcf0`
- `0x180037994`
- `0x18003f1c0`
- `0x1800711c0`
- `0x180072260`
- `0x180072870`

## callees

- `0x180007220`
- `0x180008a10`

## string_xrefs

- `0x180008a81`: `more than one token found where only one was expected: %0.*s`

## pseudocode

```c
__int64 __fastcall BeatSurroundingWhiteSpaces(__int64 a1)
{
  int v1; // eax
  _BYTE *i; // rdx
  int v3; // r8d

  v1 = *(_DWORD *)(a1 + 8);
  for ( i = *(_BYTE **)a1; v1; --v1 )
  {
    if ( *i != 32 && *i != 9 )
      break;
    ++i;
  }
  v3 = 0;
  for ( *(_QWORD *)a1 = i; v1; --v1 )
  {
    if ( *i == 9 )
      break;
    if ( *i == 32 )
      break;
    ++i;
    ++v3;
  }
  *(_DWORD *)(a1 + 8) = v3;
  if ( !v1 )
    return 1;
  do
  {
    if ( *i != 32 && *i != 9 )
      break;
    ++i;
    --v1;
  }
  while ( v1 );
  if ( !v1 )
    return 1;
  WriteDbgTraceErrorGpd(
    "BeatSurroundingWhiteSpaces",
    "more than one token found where only one was expected: %0.*s",
    v3,
    *(const char **)a1);
  return 0;
}

```

## disassembly

```asm
0x180008a10  sub     rsp, 28h
0x180008a14  mov     eax, [rcx+8]
0x180008a17  or      r9d, 0FFFFFFFFh
0x180008a1b  mov     rdx, [rcx]
0x180008a1e  mov     r10b, 20h ; ' '
0x180008a21  mov     r11b, 9
0x180008a24  test    eax, eax
0x180008a26  jz      short loc_180008A32
0x180008a28  cmp     [rdx], r10b
0x180008a2b  jz      short loc_180008A63
0x180008a2d  cmp     [rdx], r11b
0x180008a30  jz      short loc_180008A63
0x180008a32  xor     r8d, r8d
0x180008a35  mov     [rcx], rdx
0x180008a38  test    eax, eax
0x180008a3a  jz      short loc_180008A51
0x180008a3c  cmp     [rdx], r11b
0x180008a3f  jz      short loc_180008A51
0x180008a41  cmp     [rdx], r10b
0x180008a44  jz      short loc_180008A51
0x180008a46  inc     rdx
0x180008a49  inc     r8d
0x180008a4c  add     eax, r9d
0x180008a4f  jnz     short loc_180008A3C
0x180008a51  mov     [rcx+8], r8d
0x180008a55  test    eax, eax
0x180008a57  jnz     short loc_180008A6D
0x180008a59  mov     eax, 1
0x180008a5e  add     rsp, 28h
0x180008a62  retn
0x180008a63  inc     rdx
0x180008a66  add     eax, r9d
0x180008a69  jnz     short loc_180008A28
0x180008a6b  jmp     short loc_180008A32
0x180008a6d  cmp     [rdx], r10b
0x180008a70  jnz     short loc_180008A98
0x180008a72  inc     rdx
0x180008a75  add     eax, r9d
0x180008a78  jnz     short loc_180008A6D
0x180008a7a  test    eax, eax
0x180008a7c  jz      short loc_180008A59
0x180008a7e  mov     r9, [rcx]
0x180008a81  lea     rdx, aMoreThanOneTok; "more than one token found where only on"...
0x180008a88  lea     rcx, aBeatsurroundin; "BeatSurroundingWhiteSpaces"
0x180008a8f  call    WriteDbgTraceErrorGpd
0x180008a94  xor     eax, eax
0x180008a96  jmp     short loc_180008A5E
0x180008a98  cmp     [rdx], r11b
0x180008a9b  jz      short loc_180008A72
0x180008a9d  jmp     short loc_180008A7A
```
