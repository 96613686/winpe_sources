# CheckType(_DMOMediaType const *,_GUID const * const *,uint)

- ea: `0x180003138`
- end: `0x180003235`
- name: `?CheckType@@YAJPEBU_DMOMediaType@@PEBQEBU_GUID@@I@Z`
- size: `253`
- prototype: `__int64 __fastcall(const struct _DMOMediaType *, const struct _GUID *const *, unsigned int)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180002e48`
- `0x180007800`
- `0x180007f20`

## callees

- `0x180003138`

## pseudocode

```c
__int64 __fastcall CheckType(const struct _DMOMediaType *a1, const struct _GUID *const *a2, unsigned int a3)
{
  __int64 i; // rdx
  const struct _GUID *v6; // r8

  if ( *(_OWORD *)a1 == *(_OWORD *)&MEDIATYPE_Video
    && (*(_QWORD *)((char *)a1 + 44) == *(_QWORD *)&FORMAT_VideoInfo.Data1
     && *(_QWORD *)((char *)a1 + 52) == *(_QWORD *)FORMAT_VideoInfo.Data4
     || *(_QWORD *)((char *)a1 + 44) == *(_QWORD *)&FORMAT_VideoInfo2.Data1
     && *(_QWORD *)((char *)a1 + 52) == *(_QWORD *)FORMAT_VideoInfo2.Data4
     || *(_QWORD *)((char *)a1 + 44) == *(_QWORD *)&FORMAT_MFVideoFormat.Data1
     && *(_QWORD *)((char *)a1 + 52) == *(_QWORD *)FORMAT_MFVideoFormat.Data4)
    && (*(_QWORD *)((char *)a1 + 44) != *(_QWORD *)&FORMAT_VideoInfo.Data1
     || *(_QWORD *)((char *)a1 + 52) != *(_QWORD *)FORMAT_VideoInfo.Data4
     || *((_DWORD *)a1 + 18) >= 0x58u)
    && (*(_QWORD *)((char *)a1 + 44) != *(_QWORD *)&FORMAT_VideoInfo2.Data1
     || *(_QWORD *)((char *)a1 + 52) != *(_QWORD *)FORMAT_VideoInfo2.Data4
     || *((_DWORD *)a1 + 18) >= 0x70u)
    && (*(_QWORD *)((char *)a1 + 44) != *(_QWORD *)&FORMAT_MFVideoFormat.Data1
     || *(_QWORD *)((char *)a1 + 52) != *(_QWORD *)FORMAT_MFVideoFormat.Data4
     || *((_DWORD *)a1 + 18) >= 0xB0u)
    && *((_QWORD *)a1 + 10) )
  {
    for ( i = 0; (unsigned int)i < a3; i = (unsigned int)(i + 1) )
    {
      v6 = a2[i];
      if ( *(_QWORD *)&v6->Data1 == *((_QWORD *)a1 + 2) && *(_QWORD *)v6->Data4 == *((_QWORD *)a1 + 3) )
        return 0;
    }
    if ( (_DWORD)i != a3 )
      return 0;
  }
  return 2147746309LL;
}

```

## disassembly

```asm
0x180003138  mov     [rsp+arg_0], rbx
0x18000313d  mov     [rsp+arg_8], rdi
0x180003142  mov     rax, [rcx]
0x180003145  mov     r9d, r8d
0x180003148  cmp     rax, qword ptr cs:MEDIATYPE_Video.Data1
0x18000314f  mov     rdi, rdx
0x180003152  jnz     loc_180003225
0x180003158  mov     rax, [rcx+8]
0x18000315c  cmp     rax, qword ptr cs:MEDIATYPE_Video.Data4
0x180003163  jnz     loc_180003225
0x180003169  mov     rdx, qword ptr cs:FORMAT_VideoInfo.Data1
0x180003170  mov     r11, qword ptr cs:FORMAT_MFVideoFormat.Data4
0x180003177  mov     rbx, qword ptr cs:FORMAT_MFVideoFormat.Data1
0x18000317e  mov     r10, qword ptr cs:FORMAT_VideoInfo2.Data4
0x180003185  mov     r8, qword ptr cs:FORMAT_VideoInfo2.Data1
0x18000318c  mov     rax, qword ptr cs:FORMAT_VideoInfo.Data4
0x180003193  cmp     [rcx+2Ch], rdx
0x180003197  jnz     short loc_18000319F
0x180003199  cmp     [rcx+34h], rax
0x18000319d  jz      short loc_1800031B7
0x18000319f  cmp     [rcx+2Ch], r8
0x1800031a3  jnz     short loc_1800031AB
0x1800031a5  cmp     [rcx+34h], r10
0x1800031a9  jz      short loc_1800031B7
0x1800031ab  cmp     [rcx+2Ch], rbx
0x1800031af  jnz     short loc_180003225
0x1800031b1  cmp     [rcx+34h], r11
0x1800031b5  jnz     short loc_180003225
0x1800031b7  cmp     [rcx+2Ch], rdx
0x1800031bb  jnz     short loc_1800031C9
0x1800031bd  cmp     [rcx+34h], rax
0x1800031c1  jnz     short loc_1800031C9
0x1800031c3  cmp     dword ptr [rcx+48h], 58h ; 'X'
0x1800031c7  jb      short loc_180003225
0x1800031c9  cmp     [rcx+2Ch], r8
0x1800031cd  jnz     short loc_1800031DB
0x1800031cf  cmp     [rcx+34h], r10
0x1800031d3  jnz     short loc_1800031DB
0x1800031d5  cmp     dword ptr [rcx+48h], 70h ; 'p'
0x1800031d9  jb      short loc_180003225
0x1800031db  cmp     [rcx+2Ch], rbx
0x1800031df  jnz     short loc_1800031F0
0x1800031e1  cmp     [rcx+34h], r11
0x1800031e5  jnz     short loc_1800031F0
0x1800031e7  cmp     dword ptr [rcx+48h], 0B0h
0x1800031ee  jb      short loc_180003225
0x1800031f0  cmp     qword ptr [rcx+50h], 0
0x1800031f5  jz      short loc_180003225
0x1800031f7  xor     edx, edx
0x1800031f9  test    r9d, r9d
0x1800031fc  jz      short loc_18000321C
0x1800031fe  mov     r8, [rdi+rdx*8]
0x180003202  mov     rax, [r8]
0x180003205  cmp     rax, [rcx+10h]
0x180003209  jnz     short loc_180003215
0x18000320b  mov     rax, [r8+8]
0x18000320f  cmp     rax, [rcx+18h]
0x180003213  jz      short loc_180003221
0x180003215  inc     edx
0x180003217  cmp     edx, r9d
0x18000321a  jb      short loc_1800031FE
0x18000321c  cmp     edx, r9d
0x18000321f  jz      short loc_180003225
0x180003221  xor     eax, eax
0x180003223  jmp     short loc_18000322A
0x180003225  mov     eax, 80040205h
0x18000322a  mov     rbx, [rsp+arg_0]
0x18000322f  mov     rdi, [rsp+arg_8]
0x180003234  retn
```
