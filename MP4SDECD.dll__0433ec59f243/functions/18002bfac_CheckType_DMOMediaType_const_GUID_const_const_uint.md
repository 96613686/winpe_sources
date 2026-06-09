# CheckType(_DMOMediaType const *,_GUID const * const *,uint)

- ea: `0x18002bfac`
- end: `0x18002c0a9`
- name: `?CheckType@@YAJPEBU_DMOMediaType@@PEBQEBU_GUID@@I@Z`
- size: `253`
- prototype: `__int64 __fastcall(const struct _DMOMediaType *, const struct _GUID *const *, unsigned int)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180013fa0`
- `0x18002bc14`
- `0x18002dc70`

## callees

- `0x18002bfac`

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
0x18002bfac  mov     [rsp+arg_0], rbx
0x18002bfb1  mov     [rsp+arg_8], rdi
0x18002bfb6  mov     rax, [rcx]
0x18002bfb9  mov     r9d, r8d
0x18002bfbc  cmp     rax, qword ptr cs:MEDIATYPE_Video.Data1
0x18002bfc3  mov     rdi, rdx
0x18002bfc6  jnz     loc_18002C099
0x18002bfcc  mov     rax, [rcx+8]
0x18002bfd0  cmp     rax, qword ptr cs:MEDIATYPE_Video.Data4
0x18002bfd7  jnz     loc_18002C099
0x18002bfdd  mov     rdx, qword ptr cs:FORMAT_VideoInfo.Data1
0x18002bfe4  mov     r11, qword ptr cs:FORMAT_MFVideoFormat.Data4
0x18002bfeb  mov     rbx, qword ptr cs:FORMAT_MFVideoFormat.Data1
0x18002bff2  mov     r10, qword ptr cs:FORMAT_VideoInfo2.Data4
0x18002bff9  mov     r8, qword ptr cs:FORMAT_VideoInfo2.Data1
0x18002c000  mov     rax, qword ptr cs:FORMAT_VideoInfo.Data4
0x18002c007  cmp     [rcx+2Ch], rdx
0x18002c00b  jnz     short loc_18002C013
0x18002c00d  cmp     [rcx+34h], rax
0x18002c011  jz      short loc_18002C02B
0x18002c013  cmp     [rcx+2Ch], r8
0x18002c017  jnz     short loc_18002C01F
0x18002c019  cmp     [rcx+34h], r10
0x18002c01d  jz      short loc_18002C02B
0x18002c01f  cmp     [rcx+2Ch], rbx
0x18002c023  jnz     short loc_18002C099
0x18002c025  cmp     [rcx+34h], r11
0x18002c029  jnz     short loc_18002C099
0x18002c02b  cmp     [rcx+2Ch], rdx
0x18002c02f  jnz     short loc_18002C03D
0x18002c031  cmp     [rcx+34h], rax
0x18002c035  jnz     short loc_18002C03D
0x18002c037  cmp     dword ptr [rcx+48h], 58h ; 'X'
0x18002c03b  jb      short loc_18002C099
0x18002c03d  cmp     [rcx+2Ch], r8
0x18002c041  jnz     short loc_18002C04F
0x18002c043  cmp     [rcx+34h], r10
0x18002c047  jnz     short loc_18002C04F
0x18002c049  cmp     dword ptr [rcx+48h], 70h ; 'p'
0x18002c04d  jb      short loc_18002C099
0x18002c04f  cmp     [rcx+2Ch], rbx
0x18002c053  jnz     short loc_18002C064
0x18002c055  cmp     [rcx+34h], r11
0x18002c059  jnz     short loc_18002C064
0x18002c05b  cmp     dword ptr [rcx+48h], 0B0h
0x18002c062  jb      short loc_18002C099
0x18002c064  cmp     qword ptr [rcx+50h], 0
0x18002c069  jz      short loc_18002C099
0x18002c06b  xor     edx, edx
0x18002c06d  test    r9d, r9d
0x18002c070  jz      short loc_18002C090
0x18002c072  mov     r8, [rdi+rdx*8]
0x18002c076  mov     rax, [r8]
0x18002c079  cmp     rax, [rcx+10h]
0x18002c07d  jnz     short loc_18002C089
0x18002c07f  mov     rax, [r8+8]
0x18002c083  cmp     rax, [rcx+18h]
0x18002c087  jz      short loc_18002C095
0x18002c089  inc     edx
0x18002c08b  cmp     edx, r9d
0x18002c08e  jb      short loc_18002C072
0x18002c090  cmp     edx, r9d
0x18002c093  jz      short loc_18002C099
0x18002c095  xor     eax, eax
0x18002c097  jmp     short loc_18002C09E
0x18002c099  mov     eax, 80040205h
0x18002c09e  mov     rbx, [rsp+arg_0]
0x18002c0a3  mov     rdi, [rsp+arg_8]
0x18002c0a8  retn
```
