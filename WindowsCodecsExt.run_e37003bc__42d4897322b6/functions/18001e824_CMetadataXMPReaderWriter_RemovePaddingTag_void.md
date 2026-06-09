# CMetadataXMPReaderWriter::RemovePaddingTag(void)

- ea: `0x18001e824`
- end: `0x18001e874`
- name: `?RemovePaddingTag@CMetadataXMPReaderWriter@@IEAAJXZ`
- size: `80`
- prototype: `__int64 __fastcall(CMetadataXMPReaderWriter *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18001e780`
- `0x18001e7c0`

## callees

- `0x1800171c4`
- `0x18001e824`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall CMetadataXMPReaderWriter::RemovePaddingTag(CMetadataXMPReaderWriter *this)
{
  unsigned int v1; // ebx

  if ( *((_DWORD *)this + 65) )
  {
    *((_DWORD *)this + 65) = 0;
    v1 = 0;
    (*(void (__fastcall **)(CMetadataXMPReaderWriter *, __int64))(*(_QWORD *)this + 128LL))(this, 1);
  }
  else
  {
    v1 = -2003292352;
    if ( g_doStackCaptures )
      DoStackCapture(-2003292352);
  }
  return v1;
}

```

## disassembly

```asm
0x18001e824  push    rbx
0x18001e826  sub     rsp, 20h
0x18001e82a  xor     eax, eax
0x18001e82c  mov     r8, rcx
0x18001e82f  cmp     [rcx+104h], eax
0x18001e835  jnz     short loc_18001E84D
0x18001e837  cmp     cs:?g_doStackCaptures@@3HA, eax; int g_doStackCaptures
0x18001e83d  mov     ebx, 88982F40h
0x18001e842  jz      short loc_18001E86C
0x18001e844  mov     ecx, ebx; int
0x18001e846  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18001e84b  jmp     short loc_18001E86C
0x18001e84d  mov     [rcx+104h], eax
0x18001e853  mov     ebx, eax
0x18001e855  mov     rcx, [rcx]
0x18001e858  mov     edx, 1
0x18001e85d  mov     rax, [rcx+80h]
0x18001e864  mov     rcx, r8
0x18001e867  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e86c  mov     eax, ebx
0x18001e86e  add     rsp, 20h
0x18001e872  pop     rbx
0x18001e873  retn
```
