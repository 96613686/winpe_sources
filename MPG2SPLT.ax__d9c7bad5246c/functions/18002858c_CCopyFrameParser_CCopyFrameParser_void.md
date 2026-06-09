# CCopyFrameParser::~CCopyFrameParser(void)

- ea: `0x18002858c`
- end: `0x180028639`
- name: `??1CCopyFrameParser@@UEAA@XZ`
- size: `173`
- prototype: `void __fastcall(CCopyFrameParser *__hidden this)`
- caller_count: `8`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18001d7f0`
- `0x18001dc40`
- `0x18001dce0`
- `0x18001de40`
- `0x180028830`
- `0x1800288f0`
- `0x180028970`
- `0x18002c59c`

## callees

- `0x180001048`
- `0x180010ea8`
- `0x18002851c`
- `0x18002858c`
- `0x180028a7c`

## pseudocode

```c
void __fastcall CCopyFrameParser::~CCopyFrameParser(CCopyFrameParser *this)
{
  CBufferSourceManager *v1; // rsi
  volatile signed __int32 *v3; // rbx
  volatile signed __int32 *v4; // rbx

  v1 = (CCopyFrameParser *)((char *)this + 48);
  *(_QWORD *)this = &CCopyFrameParser::`vftable'{for `CDemuxBaseParser'};
  *((_QWORD *)this + 6) = &CCopyFrameParser::`vftable'{for `CBufferSourceManager'};
  CBufferSourceManager::AbortBuffer((CCopyFrameParser *)((char *)this + 48));
  v3 = (volatile signed __int32 *)*((_QWORD *)this + 48);
  if ( _InterlockedExchangeAdd(v3 + 10, 0xFFFFFFFF) == 1 && v3 )
  {
    CMpeg2Stats::~CMpeg2Stats((CMpeg2Stats *)v3);
    operator delete((void *)v3);
  }
  CBufferSourceManager::~CBufferSourceManager(v1);
  v4 = (volatile signed __int32 *)*((_QWORD *)this + 2);
  *(_QWORD *)this = &CDemuxBaseParser::`vftable';
  if ( _InterlockedExchangeAdd(v4 + 10, 0xFFFFFFFF) == 1 )
  {
    if ( v4 )
    {
      CMpeg2Stats::~CMpeg2Stats((CMpeg2Stats *)v4);
      operator delete((void *)v4);
    }
  }
}

```

## disassembly

```asm
0x18002858c  mov     [rsp+arg_8], rbx
0x180028591  mov     [rsp+arg_10], rsi
0x180028596  push    rdi
0x180028597  sub     rsp, 20h
0x18002859b  lea     rsi, [rcx+30h]
0x18002859f  mov     rdi, rcx
0x1800285a2  lea     rax, ??_7CCopyFrameParser@@6BCDemuxBaseParser@@@; const CCopyFrameParser::`vftable'{for `CDemuxBaseParser'}
0x1800285a9  mov     [rcx], rax
0x1800285ac  lea     rax, ??_7CCopyFrameParser@@6BCBufferSourceManager@@@; const CCopyFrameParser::`vftable'{for `CBufferSourceManager'}
0x1800285b3  mov     rcx, rsi; this
0x1800285b6  mov     [rsi], rax
0x1800285b9  call    ?AbortBuffer@CBufferSourceManager@@IEAAXXZ; CBufferSourceManager::AbortBuffer(void)
0x1800285be  mov     rbx, [rdi+180h]
0x1800285c5  or      eax, 0FFFFFFFFh
0x1800285c8  lock xadd [rbx+28h], eax
0x1800285cd  cmp     eax, 1
0x1800285d0  jnz     short loc_1800285EC
0x1800285d2  test    rbx, rbx
0x1800285d5  jz      short loc_1800285EC
0x1800285d7  mov     rcx, rbx; this
0x1800285da  call    ??1CMpeg2Stats@@QEAA@XZ; CMpeg2Stats::~CMpeg2Stats(void)
0x1800285df  mov     edx, 2530h; unsigned __int64
0x1800285e4  mov     rcx, rbx; void *
0x1800285e7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800285ec  mov     rcx, rsi; this
0x1800285ef  call    ??1CBufferSourceManager@@UEAA@XZ; CBufferSourceManager::~CBufferSourceManager(void)
0x1800285f4  mov     rbx, [rdi+10h]
0x1800285f8  lea     rax, ??_7CDemuxBaseParser@@6B@; const CDemuxBaseParser::`vftable'
0x1800285ff  mov     [rdi], rax
0x180028602  or      eax, 0FFFFFFFFh
0x180028605  lock xadd [rbx+28h], eax
0x18002860a  cmp     eax, 1
0x18002860d  jnz     short loc_180028629
0x18002860f  test    rbx, rbx
0x180028612  jz      short loc_180028629
0x180028614  mov     rcx, rbx; this
0x180028617  call    ??1CMpeg2Stats@@QEAA@XZ; CMpeg2Stats::~CMpeg2Stats(void)
0x18002861c  mov     edx, 2530h; unsigned __int64
0x180028621  mov     rcx, rbx; void *
0x180028624  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180028629  mov     rbx, [rsp+28h+arg_8]
0x18002862e  mov     rsi, [rsp+28h+arg_10]
0x180028633  add     rsp, 20h
0x180028637  pop     rdi
0x180028638  retn
```
