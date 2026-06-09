# mmioCreateChunk

- ea: `0x18000e660`
- end: `0x18000e70c`
- name: `mmioCreateChunk`
- size: `172`
- prototype: `MMRESULT __stdcall(HMMIO hmmio, LPMMCKINFO pmmcki, UINT fuCreate)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800085a0`
- `0x18000e660`
- `0x18000e720`

## pseudocode

```c
MMRESULT __stdcall mmioCreateChunk(HMMIO hmmio, LPMMCKINFO pmmcki, UINT fuCreate)
{
  char v3; // di
  LONG v7; // eax
  LONG v8; // edi

  v3 = fuCreate;
  if ( (fuCreate & 0xFFFFFF9F) != 0 )
    return 10;
  if ( !pmmcki )
    return 11;
  v7 = mmioSeek(hmmio, 0, 1);
  if ( v7 == -1 )
    return 263;
  pmmcki->dwDataOffset = v7 + 8;
  if ( (v3 & 0x20) != 0 )
  {
    pmmcki->ckid = 1179011410;
  }
  else
  {
    if ( (v3 & 0x40) == 0 )
    {
      v8 = 8;
      goto LABEL_13;
    }
    pmmcki->ckid = 1414744396;
  }
  v8 = 12;
LABEL_13:
  if ( !hmmio || mmioWrite(hmmio, (const char *)pmmcki, v8) != v8 )
    return 262;
  pmmcki->dwFlags = 0x10000000;
  return 0;
}

```

## disassembly

```asm
0x18000e660  mov     [rsp+arg_0], rbx
0x18000e665  mov     [rsp+arg_8], rsi
0x18000e66a  push    rdi
0x18000e66b  sub     rsp, 20h
0x18000e66f  mov     edi, r8d
0x18000e672  mov     rbx, rdx
0x18000e675  mov     rsi, rcx
0x18000e678  test    r8d, 0FFFFFF9Fh
0x18000e67f  jz      short loc_18000E688
0x18000e681  mov     eax, 0Ah
0x18000e686  jmp     short loc_18000E6FC
0x18000e688  test    rbx, rbx
0x18000e68b  jnz     short loc_18000E692
0x18000e68d  lea     eax, [rbx+0Bh]
0x18000e690  jmp     short loc_18000E6FC
0x18000e692  xor     edx, edx; lOffset
0x18000e694  lea     r8d, [rdx+1]; iOrigin
0x18000e698  call    mmioSeek
0x18000e69d  cmp     eax, 0FFFFFFFFh
0x18000e6a0  jnz     short loc_18000E6A9
0x18000e6a2  mov     eax, 107h
0x18000e6a7  jmp     short loc_18000E6FC
0x18000e6a9  add     eax, 8
0x18000e6ac  mov     [rbx+0Ch], eax
0x18000e6af  test    dil, 20h
0x18000e6b3  jz      short loc_18000E6BD
0x18000e6b5  mov     dword ptr [rbx], 46464952h
0x18000e6bb  jmp     short loc_18000E6C9
0x18000e6bd  test    dil, 40h
0x18000e6c1  jz      short loc_18000E6D0
0x18000e6c3  mov     dword ptr [rbx], 5453494Ch
0x18000e6c9  mov     edi, 0Ch
0x18000e6ce  jmp     short loc_18000E6D5
0x18000e6d0  mov     edi, 8
0x18000e6d5  test    rsi, rsi
0x18000e6d8  jz      short loc_18000E6F7
0x18000e6da  mov     r8d, edi; cch
0x18000e6dd  mov     rdx, rbx; pch
0x18000e6e0  mov     rcx, rsi; hmmio
0x18000e6e3  call    mmioWrite
0x18000e6e8  cmp     eax, edi
0x18000e6ea  jnz     short loc_18000E6F7
0x18000e6ec  mov     dword ptr [rbx+10h], 10000000h
0x18000e6f3  xor     eax, eax
0x18000e6f5  jmp     short loc_18000E6FC
0x18000e6f7  mov     eax, 106h
0x18000e6fc  mov     rbx, [rsp+28h+arg_0]
0x18000e701  mov     rsi, [rsp+28h+arg_8]
0x18000e706  add     rsp, 20h
0x18000e70a  pop     rdi
0x18000e70b  retn
```
