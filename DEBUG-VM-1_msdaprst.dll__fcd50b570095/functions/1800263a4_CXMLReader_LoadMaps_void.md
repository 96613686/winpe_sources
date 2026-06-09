# CXMLReader::LoadMaps(void)

- ea: `0x1800263a4`
- end: `0x18002655a`
- name: `?LoadMaps@CXMLReader@@AEAAJXZ`
- size: `438`
- prototype: `__int64 __fastcall(CXMLReader *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180024ac8`

## callees

- `0x1800263a4`
- `0x18002867c`
- `0x180028700`
- `0x180028fb0`

## pseudocode

```c
int __fastcall CXMLReader::LoadMaps(CXMLReader *this)
{
  CCollectionList *v1; // rsi
  int result; // eax
  unsigned int v4; // edi
  struct tagDICTENTRY near **v5; // rbx
  unsigned __int16 *v6; // rdx
  __int64 v7; // r8
  unsigned int v8; // edi
  struct tagDICTENTRY near **v9; // rbx
  unsigned __int16 *v10; // rdx
  __int64 v11; // r8
  unsigned int v12; // edi
  struct tagDICTENTRY near **v13; // rbx
  unsigned __int16 *v14; // rdx
  __int64 v15; // r8
  unsigned int v16; // edi
  struct tagDICTENTRY near **v17; // rbx
  unsigned __int16 *v18; // rdx
  __int64 v19; // r8

  v1 = (CXMLReader *)((char *)this + 208);
  result = CCollectionList::Reserve((CXMLReader *)((char *)this + 208), 0x1Au);
  if ( result >= 0 )
  {
    v4 = 0;
    v5 = &rgdictColumnAttribs;
    while ( v4 < 0x1A )
    {
      v6 = (unsigned __int16 *)*v5;
      if ( *v5 )
      {
        v7 = -1;
        do
          ++v7;
        while ( v6[v7] );
      }
      else
      {
        LODWORD(v7) = 0;
      }
      result = CCollectionList::AppendDup(v1, v6, v7, (unsigned __int64)v5[1]);
      if ( result < 0 )
        return result;
      ++v4;
      v5 += 2;
    }
    result = CCollectionList::Reserve((CXMLReader *)((char *)this + 256), 0xFu);
    if ( result >= 0 )
    {
      v8 = 0;
      v9 = &rgdictRowsetAttribs;
      while ( v8 < 0xF )
      {
        v10 = (unsigned __int16 *)*v9;
        if ( *v9 )
        {
          v11 = -1;
          do
            ++v11;
          while ( v10[v11] );
        }
        else
        {
          LODWORD(v11) = 0;
        }
        result = CCollectionList::AppendDup((CXMLReader *)((char *)this + 256), v10, v11, (unsigned __int64)v9[1]);
        if ( result < 0 )
          return result;
        ++v8;
        v9 += 2;
      }
      result = CCollectionList::Reserve((CXMLReader *)((char *)this + 352), 0xAu);
      if ( result >= 0 )
      {
        v12 = 0;
        v13 = &rgdictFlags;
        while ( v12 < 0xA )
        {
          v14 = (unsigned __int16 *)*v13;
          if ( *v13 )
          {
            v15 = -1;
            do
              ++v15;
            while ( v14[v15] );
          }
          else
          {
            LODWORD(v15) = 0;
          }
          result = CCollectionList::AppendDup((CXMLReader *)((char *)this + 352), v14, v15, (unsigned __int64)v13[1]);
          if ( result < 0 )
            return result;
          ++v12;
          v13 += 2;
        }
        result = CCollectionList::Reserve((CXMLReader *)((char *)this + 304), 0x1Fu);
        if ( result >= 0 )
        {
          v16 = 0;
          v17 = &rgdictTypes;
          while ( v16 < 0x1F )
          {
            v18 = (unsigned __int16 *)*v17;
            if ( *v17 )
            {
              v19 = -1;
              do
                ++v19;
              while ( v18[v19] );
            }
            else
            {
              LODWORD(v19) = 0;
            }
            result = CCollectionList::AppendDup((CXMLReader *)((char *)this + 304), v18, v19, (unsigned __int64)v17[1]);
            if ( result < 0 )
              return result;
            ++v16;
            v17 += 2;
          }
          return CCollectionList::Append((CXMLReader *)((char *)this + 160), L"xml", 3u, 0);
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800263a4  push    rbx
0x1800263a6  push    rbp
0x1800263a7  push    rsi
0x1800263a8  push    rdi
0x1800263a9  push    r14
0x1800263ab  push    r15
0x1800263ad  sub     rsp, 28h
0x1800263b1  lea     rsi, [rcx+0D0h]
0x1800263b8  mov     rbp, rcx
0x1800263bb  mov     rcx, rsi; this
0x1800263be  mov     edx, 1Ah; unsigned int
0x1800263c3  call    ?Reserve@CCollectionList@@QEAAJK@Z; CCollectionList::Reserve(ulong)
0x1800263c8  xor     r14d, r14d
0x1800263cb  test    eax, eax
0x1800263cd  js      loc_18002654D
0x1800263d3  mov     edi, r14d
0x1800263d6  lea     rbx, ?rgdictColumnAttribs@@3PAUtagDICTENTRY@@A; tagDICTENTRY near * rgdictColumnAttribs
0x1800263dd  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800263e1  cmp     edi, 1Ah
0x1800263e4  jnb     short loc_18002641C
0x1800263e6  mov     rdx, [rbx]; unsigned __int16 *
0x1800263e9  test    rdx, rdx
0x1800263ec  jz      short loc_1800263FD
0x1800263ee  mov     r8, r15
0x1800263f1  inc     r8
0x1800263f4  cmp     [rdx+r8*2], r14w
0x1800263f9  jnz     short loc_1800263F1
0x1800263fb  jmp     short loc_180026400
0x1800263fd  mov     r8, r14; unsigned int
0x180026400  mov     r9, [rbx+8]; unsigned __int64
0x180026404  mov     rcx, rsi; this
0x180026407  call    ?AppendDup@CCollectionList@@QEAAJPEAGK_K@Z; CCollectionList::AppendDup(ushort *,ulong,unsigned __int64)
0x18002640c  test    eax, eax
0x18002640e  js      loc_18002654D
0x180026414  inc     edi
0x180026416  add     rbx, 10h
0x18002641a  jmp     short loc_1800263E1
0x18002641c  lea     rsi, [rbp+100h]
0x180026423  mov     edx, 0Fh; unsigned int
0x180026428  mov     rcx, rsi; this
0x18002642b  call    ?Reserve@CCollectionList@@QEAAJK@Z; CCollectionList::Reserve(ulong)
0x180026430  test    eax, eax
0x180026432  js      loc_18002654D
0x180026438  mov     edi, r14d
0x18002643b  lea     rbx, ?rgdictRowsetAttribs@@3PAUtagDICTENTRY@@A; tagDICTENTRY near * rgdictRowsetAttribs
0x180026442  cmp     edi, 0Fh
0x180026445  jnb     short loc_18002647D
0x180026447  mov     rdx, [rbx]; unsigned __int16 *
0x18002644a  test    rdx, rdx
0x18002644d  jz      short loc_18002645E
0x18002644f  mov     r8, r15
0x180026452  inc     r8
0x180026455  cmp     [rdx+r8*2], r14w
0x18002645a  jnz     short loc_180026452
0x18002645c  jmp     short loc_180026461
0x18002645e  mov     r8, r14; unsigned int
0x180026461  mov     r9, [rbx+8]; unsigned __int64
0x180026465  mov     rcx, rsi; this
0x180026468  call    ?AppendDup@CCollectionList@@QEAAJPEAGK_K@Z; CCollectionList::AppendDup(ushort *,ulong,unsigned __int64)
0x18002646d  test    eax, eax
0x18002646f  js      loc_18002654D
0x180026475  inc     edi
0x180026477  add     rbx, 10h
0x18002647b  jmp     short loc_180026442
0x18002647d  lea     rsi, [rbp+160h]
0x180026484  mov     edx, 0Ah; unsigned int
0x180026489  mov     rcx, rsi; this
0x18002648c  call    ?Reserve@CCollectionList@@QEAAJK@Z; CCollectionList::Reserve(ulong)
0x180026491  test    eax, eax
0x180026493  js      loc_18002654D
0x180026499  mov     edi, r14d
0x18002649c  lea     rbx, ?rgdictFlags@@3PAUtagDICTENTRY@@A; tagDICTENTRY near * rgdictFlags
0x1800264a3  cmp     edi, 0Ah
0x1800264a6  jnb     short loc_1800264DA
0x1800264a8  mov     rdx, [rbx]; unsigned __int16 *
0x1800264ab  test    rdx, rdx
0x1800264ae  jz      short loc_1800264BF
0x1800264b0  mov     r8, r15
0x1800264b3  inc     r8
0x1800264b6  cmp     [rdx+r8*2], r14w
0x1800264bb  jnz     short loc_1800264B3
0x1800264bd  jmp     short loc_1800264C2
0x1800264bf  mov     r8, r14; unsigned int
0x1800264c2  mov     r9, [rbx+8]; unsigned __int64
0x1800264c6  mov     rcx, rsi; this
0x1800264c9  call    ?AppendDup@CCollectionList@@QEAAJPEAGK_K@Z; CCollectionList::AppendDup(ushort *,ulong,unsigned __int64)
0x1800264ce  test    eax, eax
0x1800264d0  js      short loc_18002654D
0x1800264d2  inc     edi
0x1800264d4  add     rbx, 10h
0x1800264d8  jmp     short loc_1800264A3
0x1800264da  lea     rsi, [rbp+130h]
0x1800264e1  mov     edx, 1Fh; unsigned int
0x1800264e6  mov     rcx, rsi; this
0x1800264e9  call    ?Reserve@CCollectionList@@QEAAJK@Z; CCollectionList::Reserve(ulong)
0x1800264ee  test    eax, eax
0x1800264f0  js      short loc_18002654D
0x1800264f2  mov     edi, r14d
0x1800264f5  lea     rbx, ?rgdictTypes@@3PAUtagDICTENTRY@@A; tagDICTENTRY near * rgdictTypes
0x1800264fc  cmp     edi, 1Fh
0x1800264ff  jnb     short loc_180026533
0x180026501  mov     rdx, [rbx]; unsigned __int16 *
0x180026504  test    rdx, rdx
0x180026507  jz      short loc_180026518
0x180026509  mov     r8, r15
0x18002650c  inc     r8
0x18002650f  cmp     [rdx+r8*2], r14w
0x180026514  jnz     short loc_18002650C
0x180026516  jmp     short loc_18002651B
0x180026518  mov     r8, r14; unsigned int
0x18002651b  mov     r9, [rbx+8]; unsigned __int64
0x18002651f  mov     rcx, rsi; this
0x180026522  call    ?AppendDup@CCollectionList@@QEAAJPEAGK_K@Z; CCollectionList::AppendDup(ushort *,ulong,unsigned __int64)
0x180026527  test    eax, eax
0x180026529  js      short loc_18002654D
0x18002652b  inc     edi
0x18002652d  add     rbx, 10h
0x180026531  jmp     short loc_1800264FC
0x180026533  xor     r9d, r9d; unsigned __int64
0x180026536  lea     rcx, [rbp+0A0h]; this
0x18002653d  lea     rdx, aXml; "xml"
0x180026544  lea     r8d, [r9+3]; unsigned int
0x180026548  call    ?Append@CCollectionList@@QEAAJPEAGK_K@Z; CCollectionList::Append(ushort *,ulong,unsigned __int64)
0x18002654d  add     rsp, 28h
0x180026551  pop     r15
0x180026553  pop     r14
0x180026555  pop     rdi
0x180026556  pop     rsi
0x180026557  pop     rbp
0x180026558  pop     rbx
0x180026559  retn
```
