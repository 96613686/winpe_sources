# AxiPreScanPathW(ushort const *)

- ea: `0x408301`
- end: `0x40836d`
- name: `?AxiPreScanPathW@@YGJPBG@Z`
- size: `108`
- prototype: `int __thiscall(_WORD *this)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x40373b`
- `0x403d84`
- `0x404214`
- `0x4044ae`
- `0x407d14`
- `0x407eab`

## callees

- `0x408235`
- `0x408301`

## import_xrefs

- `msvcrt!iswascii` at `0x40833e`
- `msvcrt!iswascii` at `0x40833e`
- `msvcrt!iswcntrl` at `0x40834e`
- `msvcrt!iswcntrl` at `0x40834e`

## pseudocode

```c
int __thiscall AxiPreScanPathW(_WORD *this)
{
  int result; // eax
  int i; // esi
  int v4; // ecx
  int v5; // eax

  result = 0;
  if ( this )
  {
    for ( i = 0; ; ++i )
    {
      v4 = (unsigned __int16)this[i];
      result = 0;
      if ( !(_WORD)v4 )
        return result;
      if ( v4 == 34 || v4 == 42 || v4 == 60 || v4 == 62 || v4 == 63 || v4 == 124 )
      {
        v5 = FilenameDisallowCharacter(v4);
      }
      else
      {
        if ( !_iswascii(this[i]) )
          continue;
        v5 = _iswcntrl(this[i]);
      }
      if ( v5 )
        return -2147024809;
    }
  }
  return result;
}

```

## disassembly

```asm
0x408301  mov     edi, edi
0x408303  push    edi
0x408304  mov     edi, ecx
0x408306  xor     eax, eax
0x408308  test    edi, edi
0x40830a  jz      short loc_40836B
0x40830c  push    esi
0x40830d  xor     esi, esi
0x40830f  movzx   ecx, word ptr [edi+esi*2]
0x408313  xor     eax, eax
0x408315  test    cx, cx
0x408318  jz      short loc_40836A
0x40831a  mov     edx, ecx
0x40831c  mov     eax, ecx
0x40831e  sub     eax, 22h ; '"'
0x408321  jz      short loc_408357
0x408323  sub     eax, 8
0x408326  jz      short loc_408357
0x408328  sub     eax, 12h
0x40832b  jz      short loc_408357
0x40832d  dec     eax
0x40832e  sub     eax, 1
0x408331  jz      short loc_408357
0x408333  sub     eax, 1
0x408336  jz      short loc_408357
0x408338  sub     eax, 3Dh ; '='
0x40833b  jz      short loc_408357
0x40833d  push    ecx; C
0x40833e  call    ds:__imp__iswascii
0x408344  pop     ecx
0x408345  test    eax, eax
0x408347  jz      short loc_408362
0x408349  movzx   eax, word ptr [edi+esi*2]
0x40834d  push    eax; C
0x40834e  call    ds:__imp__iswcntrl
0x408354  pop     ecx
0x408355  jmp     short loc_40835E
0x408357  mov     ecx, edx
0x408359  call    FilenameDisallowCharacter
0x40835e  test    eax, eax
0x408360  jnz     short loc_408365
0x408362  inc     esi
0x408363  jmp     short loc_40830F
0x408365  mov     eax, 80070057h
0x40836a  pop     esi
0x40836b  pop     edi
0x40836c  retn
```
