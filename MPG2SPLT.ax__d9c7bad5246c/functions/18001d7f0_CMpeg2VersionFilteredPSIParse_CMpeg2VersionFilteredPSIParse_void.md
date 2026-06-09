# CMpeg2VersionFilteredPSIParse::~CMpeg2VersionFilteredPSIParse(void)

- ea: `0x18001d7f0`
- end: `0x18001d885`
- name: `??1CMpeg2VersionFilteredPSIParse@@UEAA@XZ`
- size: `149`
- prototype: `void __fastcall(CMpeg2VersionFilteredPSIParse *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18001dc90`
- `0x18001dd20`
- `0x18001df00`

## callees

- `0x180001048`
- `0x18001d7f0`
- `0x18001e6b0`
- `0x18002858c`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18001d832`
- `KERNEL32!DeleteCriticalSection` at `0x18001d832`

## pseudocode

```c
void __fastcall CMpeg2VersionFilteredPSIParse::~CMpeg2VersionFilteredPSIParse(CMpeg2VersionFilteredPSIParse *this)
{
  char *v2; // rbx
  __int64 **v3; // rbx
  __int64 *v4; // rcx
  __int64 v5; // rdx
  __int64 *v6; // rax

  *(_QWORD *)this = &CMpeg2VersionFilteredPSIParse::`vftable'{for `CDemuxBaseParser'};
  v2 = (char *)this + 416;
  *((_QWORD *)this + 6) = &CMpeg2VersionFilteredPSIParse::`vftable'{for `CBufferSourceManager'};
  TGenericMap<unsigned long,unsigned long,0,5,19>::Clear((char *)this + 416);
  *(_QWORD *)v2 = &TGenericMap<unsigned long,unsigned long,0,5,19>::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)(v2 + 384));
  v3 = (__int64 **)(v2 + 8);
  while ( 1 )
  {
    v4 = *v3;
    if ( *v3 == (__int64 *)v3 )
      break;
    v5 = *v4;
    v6 = (__int64 *)v4[1];
    *v6 = *v4;
    *(_QWORD *)(v5 + 8) = v6;
    operator delete(v4, 0x180u);
  }
  *(_QWORD *)this = &CMpeg2PSIParse::`vftable'{for `CDemuxBaseParser'};
  *((_QWORD *)this + 6) = &CMpeg2PSIParse::`vftable'{for `CBufferSourceManager'};
  CCopyFrameParser::~CCopyFrameParser(this);
}

```

## disassembly

```asm
0x18001d7f0  mov     [rsp+arg_0], rbx
0x18001d7f5  push    rdi
0x18001d7f6  sub     rsp, 20h
0x18001d7fa  lea     rax, ??_7CMpeg2VersionFilteredPSIParse@@6BCDemuxBaseParser@@@; const CMpeg2VersionFilteredPSIParse::`vftable'{for `CDemuxBaseParser'}
0x18001d801  mov     rdi, rcx
0x18001d804  mov     [rcx], rax
0x18001d807  lea     rbx, [rcx+1A0h]
0x18001d80e  lea     rax, ??_7CMpeg2VersionFilteredPSIParse@@6BCBufferSourceManager@@@; const CMpeg2VersionFilteredPSIParse::`vftable'{for `CBufferSourceManager'}
0x18001d815  mov     [rcx+30h], rax
0x18001d819  mov     rcx, rbx
0x18001d81c  call    ?Clear@?$TGenericMap@KK$0A@$04$0BD@@@QEAAXXZ; TGenericMap<ulong,ulong,0,5,19>::Clear(void)
0x18001d821  lea     rax, ??_7?$TGenericMap@KK$0A@$04$0BD@@@6B@; const TGenericMap<ulong,ulong,0,5,19>::`vftable'
0x18001d828  lea     rcx, [rbx+180h]; lpCriticalSection
0x18001d82f  mov     [rbx], rax
0x18001d832  call    cs:__imp_DeleteCriticalSection
0x18001d838  add     rbx, 8
0x18001d83c  mov     rcx, [rbx]; void *
0x18001d83f  cmp     rcx, rbx
0x18001d842  jz      short loc_18001D85E
0x18001d844  mov     rdx, [rcx]
0x18001d847  mov     rax, [rcx+8]
0x18001d84b  mov     [rax], rdx
0x18001d84e  mov     [rdx+8], rax
0x18001d852  mov     edx, 180h; unsigned __int64
0x18001d857  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001d85c  jmp     short loc_18001D83C
0x18001d85e  lea     rax, ??_7CMpeg2PSIParse@@6BCDemuxBaseParser@@@; const CMpeg2PSIParse::`vftable'{for `CDemuxBaseParser'}
0x18001d865  mov     rcx, rdi; this
0x18001d868  mov     [rdi], rax
0x18001d86b  lea     rax, ??_7CMpeg2PSIParse@@6BCBufferSourceManager@@@; const CMpeg2PSIParse::`vftable'{for `CBufferSourceManager'}
0x18001d872  mov     [rdi+30h], rax
0x18001d876  mov     rbx, [rsp+28h+arg_0]
0x18001d87b  add     rsp, 20h
0x18001d87f  pop     rdi
0x18001d880  jmp     ??1CCopyFrameParser@@UEAA@XZ; CCopyFrameParser::~CCopyFrameParser(void)
```
