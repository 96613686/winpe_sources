# CMetadataRDFReaderWriter::SetDepth(uint)

- ea: `0x180002920`
- end: `0x180002952`
- name: `?SetDepth@CMetadataRDFReaderWriter@@QEAAJI@Z`
- size: `50`
- prototype: `__int64 __fastcall(CMetadataRDFReaderWriter *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180003350`
- `0x1800156a8`

## callees

- `0x180002920`
- `0x1800171c4`

## pseudocode

```c
__int64 __fastcall CMetadataRDFReaderWriter::SetDepth(CMetadataRDFReaderWriter *this, unsigned int a2)
{
  unsigned int v2; // ebx

  if ( a2 >= 0x32 )
  {
    v2 = -2003292334;
    if ( g_doStackCaptures )
      DoStackCapture(-2003292334);
  }
  else
  {
    v2 = 0;
    *((_DWORD *)this + 50) = a2;
  }
  return v2;
}

```

## disassembly

```asm
0x180002920  push    rbx
0x180002922  sub     rsp, 20h
0x180002926  cmp     edx, 32h ; '2'
0x180002929  jnb     short loc_18000293B
0x18000292b  xor     ebx, ebx
0x18000292d  mov     [rcx+0C8h], edx
0x180002933  mov     eax, ebx
0x180002935  add     rsp, 20h
0x180002939  pop     rbx
0x18000293a  retn
0x18000293b  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180002942  mov     ebx, 88982F52h
0x180002947  jz      short loc_180002933
0x180002949  mov     ecx, ebx; int
0x18000294b  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180002950  jmp     short loc_180002933
```
