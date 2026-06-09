# CheckType(_DMOMediaType const *,_GUID const * const *,uint)

- ea: `0x1800031f8`
- end: `0x1800032f5`
- name: `?CheckType@@YAJPEBU_DMOMediaType@@PEBQEBU_GUID@@I@Z`
- size: `253`
- prototype: `__int64 __fastcall(const struct _DMOMediaType *, const struct _GUID *const *, unsigned int)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180002f08`
- `0x1800078c0`
- `0x180007fe0`

## callees

- `0x1800031f8`

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
0x1800031f8  mov     [rsp+arg_0], rbx
0x1800031fd  mov     [rsp+arg_8], rdi
0x180003202  mov     rax, [rcx]
0x180003205  mov     r9d, r8d
0x180003208  cmp     rax, qword ptr cs:MEDIATYPE_Video.Data1
0x18000320f  mov     rdi, rdx
0x180003212  jnz     loc_1800032E5
0x180003218  mov     rax, [rcx+8]
0x18000321c  cmp     rax, qword ptr cs:MEDIATYPE_Video.Data4
0x180003223  jnz     loc_1800032E5
0x180003229  mov     rdx, qword ptr cs:FORMAT_VideoInfo.Data1
0x180003230  mov     r11, qword ptr cs:FORMAT_MFVideoFormat.Data4
0x180003237  mov     rbx, qword ptr cs:FORMAT_MFVideoFormat.Data1
0x18000323e  mov     r10, qword ptr cs:FORMAT_VideoInfo2.Data4
0x180003245  mov     r8, qword ptr cs:FORMAT_VideoInfo2.Data1
0x18000324c  mov     rax, qword ptr cs:FORMAT_VideoInfo.Data4
0x180003253  cmp     [rcx+2Ch], rdx
0x180003257  jnz     short loc_18000325F
0x180003259  cmp     [rcx+34h], rax
0x18000325d  jz      short loc_180003277
0x18000325f  cmp     [rcx+2Ch], r8
0x180003263  jnz     short loc_18000326B
0x180003265  cmp     [rcx+34h], r10
0x180003269  jz      short loc_180003277
0x18000326b  cmp     [rcx+2Ch], rbx
0x18000326f  jnz     short loc_1800032E5
0x180003271  cmp     [rcx+34h], r11
0x180003275  jnz     short loc_1800032E5
0x180003277  cmp     [rcx+2Ch], rdx
0x18000327b  jnz     short loc_180003289
0x18000327d  cmp     [rcx+34h], rax
0x180003281  jnz     short loc_180003289
0x180003283  cmp     dword ptr [rcx+48h], 58h ; 'X'
0x180003287  jb      short loc_1800032E5
0x180003289  cmp     [rcx+2Ch], r8
0x18000328d  jnz     short loc_18000329B
0x18000328f  cmp     [rcx+34h], r10
0x180003293  jnz     short loc_18000329B
0x180003295  cmp     dword ptr [rcx+48h], 70h ; 'p'
0x180003299  jb      short loc_1800032E5
0x18000329b  cmp     [rcx+2Ch], rbx
0x18000329f  jnz     short loc_1800032B0
0x1800032a1  cmp     [rcx+34h], r11
0x1800032a5  jnz     short loc_1800032B0
0x1800032a7  cmp     dword ptr [rcx+48h], 0B0h
0x1800032ae  jb      short loc_1800032E5
0x1800032b0  cmp     qword ptr [rcx+50h], 0
0x1800032b5  jz      short loc_1800032E5
0x1800032b7  xor     edx, edx
0x1800032b9  test    r9d, r9d
0x1800032bc  jz      short loc_1800032DC
0x1800032be  mov     r8, [rdi+rdx*8]
0x1800032c2  mov     rax, [r8]
0x1800032c5  cmp     rax, [rcx+10h]
0x1800032c9  jnz     short loc_1800032D5
0x1800032cb  mov     rax, [r8+8]
0x1800032cf  cmp     rax, [rcx+18h]
0x1800032d3  jz      short loc_1800032E1
0x1800032d5  inc     edx
0x1800032d7  cmp     edx, r9d
0x1800032da  jb      short loc_1800032BE
0x1800032dc  cmp     edx, r9d
0x1800032df  jz      short loc_1800032E5
0x1800032e1  xor     eax, eax
0x1800032e3  jmp     short loc_1800032EA
0x1800032e5  mov     eax, 80040205h
0x1800032ea  mov     rbx, [rsp+arg_0]
0x1800032ef  mov     rdi, [rsp+arg_8]
0x1800032f4  retn
```
