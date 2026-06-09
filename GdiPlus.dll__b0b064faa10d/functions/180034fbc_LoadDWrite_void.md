# LoadDWrite(void)

- ea: `0x180034fbc`
- end: `0x180035256`
- name: `?LoadDWrite@@YAHXZ`
- size: `666`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180034ce8`
- `0x180035bc8`
- `0x180120440`

## callees

- `0x180034fbc`
- `0x18003525c`
- `0x180035278`
- `0x1800f1964`
- `0x180169010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180034fc9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180034fc9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003509d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180035182`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003509d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180035182`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180035008`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180035033`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800350ca`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180035008`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180035033`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800350ca`
- `DWrite!DWriteCreateFactory` at `0x180034fed`
- `DWrite!DWriteCreateFactory` at `0x180034fed`

## pseudocode

```c
__int64 LoadDWrite(void)
{
  GpFontCollectionFileLoader *v0; // rax
  GpFontCollectionStreamLoader *v1; // rax
  GpFontFileLoader *v3; // rax

  EnterCriticalSection(&LoadLibraryCriticalSection::critSec);
  if ( Globals::g_DWriteFactory )
    goto LABEL_23;
  if ( (int)DWriteCreateFactory(0, &GUID_b859ee5a_d838_4b5b_a2e8_1adc7d93db48, &Globals::g_DWriteFactory) >= 0 )
  {
    v0 = (GpFontCollectionFileLoader *)HeapAlloc(GpRuntime::GpMemHeap, 0, 0x10u);
    if ( v0 )
    {
      Globals::g_GpFontCollectionFileLoader = GpFontCollectionFileLoader::GpFontCollectionFileLoader(v0);
      if ( Globals::g_GpFontCollectionFileLoader )
      {
        v1 = (GpFontCollectionStreamLoader *)HeapAlloc(GpRuntime::GpMemHeap, 0, 0x10u);
        if ( !v1 )
          goto LABEL_6;
        Globals::g_GpFontCollectionStreamLoader = GpFontCollectionStreamLoader::GpFontCollectionStreamLoader(v1);
        if ( !Globals::g_GpFontCollectionStreamLoader )
          goto LABEL_9;
        v3 = (GpFontFileLoader *)HeapAlloc(GpRuntime::GpMemHeap, 0, 0x10u);
        if ( v3 )
        {
          Globals::g_GpFontFileLoader = GpFontFileLoader::GpFontFileLoader(v3);
          if ( Globals::g_GpFontFileLoader
            && (*(int (__fastcall **)(struct IDWriteFactory *, struct IDWriteFontFileLoader *))(*(_QWORD *)Globals::g_DWriteFactory
                                                                                              + 104LL))(
                 Globals::g_DWriteFactory,
                 Globals::g_GpFontFileLoader) >= 0
            && (*(int (__fastcall **)(struct IDWriteFactory *, struct IDWriteFontCollectionLoader *))(*(_QWORD *)Globals::g_DWriteFactory + 40LL))(
                 Globals::g_DWriteFactory,
                 Globals::g_GpFontCollectionFileLoader) >= 0
            && (*(int (__fastcall **)(struct IDWriteFactory *, struct IDWriteFontCollectionLoader *))(*(_QWORD *)Globals::g_DWriteFactory + 40LL))(
                 Globals::g_DWriteFactory,
                 Globals::g_GpFontCollectionStreamLoader) >= 0
            && (*(int (__fastcall **)(struct IDWriteFactory *, struct IDWriteTextAnalyzer **))(*(_QWORD *)Globals::g_DWriteFactory
                                                                                             + 168LL))(
                 Globals::g_DWriteFactory,
                 &Globals::g_DWriteTextAnalyzer) >= 0 )
          {
LABEL_23:
            LeaveCriticalSection(&LoadLibraryCriticalSection::critSec);
            return 1;
          }
        }
        else
        {
          Globals::g_GpFontFileLoader = 0;
        }
      }
    }
    else
    {
      Globals::g_GpFontCollectionFileLoader = 0;
    }
  }
  if ( !Globals::g_GpFontCollectionStreamLoader )
    goto LABEL_9;
  (*(void (__fastcall **)(struct IDWriteFactory *))(*(_QWORD *)Globals::g_DWriteFactory + 48LL))(Globals::g_DWriteFactory);
  (*(void (__fastcall **)(struct IDWriteFontCollectionLoader *))(*(_QWORD *)Globals::g_GpFontCollectionStreamLoader
                                                               + 16LL))(Globals::g_GpFontCollectionStreamLoader);
LABEL_6:
  Globals::g_GpFontCollectionStreamLoader = 0;
LABEL_9:
  if ( Globals::g_GpFontCollectionFileLoader )
  {
    (*(void (__fastcall **)(struct IDWriteFactory *))(*(_QWORD *)Globals::g_DWriteFactory + 48LL))(Globals::g_DWriteFactory);
    (*(void (__fastcall **)(struct IDWriteFontCollectionLoader *))(*(_QWORD *)Globals::g_GpFontCollectionFileLoader
                                                                 + 16LL))(Globals::g_GpFontCollectionFileLoader);
    Globals::g_GpFontCollectionFileLoader = 0;
  }
  if ( Globals::g_GpFontFileLoader )
  {
    (*(void (__fastcall **)(struct IDWriteFactory *))(*(_QWORD *)Globals::g_DWriteFactory + 112LL))(Globals::g_DWriteFactory);
    (*(void (__fastcall **)(struct IDWriteFontFileLoader *))(*(_QWORD *)Globals::g_GpFontFileLoader + 16LL))(Globals::g_GpFontFileLoader);
    Globals::g_GpFontFileLoader = 0;
  }
  if ( Globals::g_DWriteFactory )
  {
    (*(void (__fastcall **)(struct IDWriteFactory *))(*(_QWORD *)Globals::g_DWriteFactory + 16LL))(Globals::g_DWriteFactory);
    Globals::g_DWriteFactory = 0;
  }
  LeaveCriticalSection(&LoadLibraryCriticalSection::critSec);
  return 0;
}

```

## disassembly

```asm
0x180034fbc  push    rsi
0x180034fbe  sub     rsp, 20h
0x180034fc2  lea     rcx, ?critSec@LoadLibraryCriticalSection@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180034fc9  call    cs:__imp_EnterCriticalSection
0x180034fcf  cmp     cs:?g_DWriteFactory@Globals@@3PEAUIDWriteFactory@@EA, 0; IDWriteFactory * Globals::g_DWriteFactory
0x180034fd7  jnz     loc_18003517B
0x180034fdd  lea     r8, ?g_DWriteFactory@Globals@@3PEAUIDWriteFactory@@EA; IDWriteFactory * Globals::g_DWriteFactory
0x180034fe4  xor     ecx, ecx
0x180034fe6  lea     rdx, _GUID_b859ee5a_d838_4b5b_a2e8_1adc7d93db48
0x180034fed  call    cs:__imp_DWriteCreateFactory
0x180034ff3  test    eax, eax
0x180034ff5  js      short loc_180035056
0x180034ff7  mov     rcx, cs:?GpMemHeap@GpRuntime@@3PEAXEA; hHeap
0x180034ffe  mov     esi, 10h
0x180035003  mov     r8d, esi; dwBytes
0x180035006  xor     edx, edx; dwFlags
0x180035008  call    cs:__imp_HeapAlloc
0x18003500e  test    rax, rax
0x180035011  jz      short loc_18003504B
0x180035013  mov     rcx, rax; this
0x180035016  call    ??0GpFontCollectionFileLoader@@QEAA@XZ; GpFontCollectionFileLoader::GpFontCollectionFileLoader(void)
0x18003501b  mov     cs:?g_GpFontCollectionFileLoader@Globals@@3PEAUIDWriteFontCollectionLoader@@EA, rax; IDWriteFontCollectionLoader * Globals::g_GpFontCollectionFileLoader
0x180035022  test    rax, rax
0x180035025  jz      short loc_180035056
0x180035027  mov     rcx, cs:?GpMemHeap@GpRuntime@@3PEAXEA; hHeap
0x18003502e  mov     r8d, esi; dwBytes
0x180035031  xor     edx, edx; dwFlags
0x180035033  call    cs:__imp_HeapAlloc
0x180035039  test    rax, rax
0x18003503c  jnz     short loc_1800350AA
0x18003503e  mov     cs:?g_GpFontCollectionStreamLoader@Globals@@3PEAUIDWriteFontCollectionLoader@@EA, 0; IDWriteFontCollectionLoader * Globals::g_GpFontCollectionStreamLoader
0x180035049  jmp     short loc_180035066
0x18003504b  mov     cs:?g_GpFontCollectionFileLoader@Globals@@3PEAUIDWriteFontCollectionLoader@@EA, 0; IDWriteFontCollectionLoader * Globals::g_GpFontCollectionFileLoader
0x180035056  mov     rdx, cs:?g_GpFontCollectionStreamLoader@Globals@@3PEAUIDWriteFontCollectionLoader@@EA; IDWriteFontCollectionLoader * Globals::g_GpFontCollectionStreamLoader
0x18003505d  test    rdx, rdx
0x180035060  jnz     loc_1800351A3
0x180035066  mov     rdx, cs:?g_GpFontCollectionFileLoader@Globals@@3PEAUIDWriteFontCollectionLoader@@EA; IDWriteFontCollectionLoader * Globals::g_GpFontCollectionFileLoader
0x18003506d  test    rdx, rdx
0x180035070  jnz     loc_1800351CE
0x180035076  mov     rdx, cs:?g_GpFontFileLoader@Globals@@3PEAUIDWriteFontFileLoader@@EA; IDWriteFontFileLoader * Globals::g_GpFontFileLoader
0x18003507d  test    rdx, rdx
0x180035080  jnz     loc_180035204
0x180035086  mov     rcx, cs:?g_DWriteFactory@Globals@@3PEAUIDWriteFactory@@EA; IDWriteFactory * Globals::g_DWriteFactory
0x18003508d  test    rcx, rcx
0x180035090  jnz     loc_18003523A
0x180035096  lea     rcx, ?critSec@LoadLibraryCriticalSection@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18003509d  call    cs:__imp_LeaveCriticalSection
0x1800350a3  xor     eax, eax
0x1800350a5  jmp     loc_18003518D
0x1800350aa  mov     rcx, rax; this
0x1800350ad  call    ??0GpFontCollectionStreamLoader@@QEAA@XZ; GpFontCollectionStreamLoader::GpFontCollectionStreamLoader(void)
0x1800350b2  mov     cs:?g_GpFontCollectionStreamLoader@Globals@@3PEAUIDWriteFontCollectionLoader@@EA, rax; IDWriteFontCollectionLoader * Globals::g_GpFontCollectionStreamLoader
0x1800350b9  test    rax, rax
0x1800350bc  jz      short loc_180035066
0x1800350be  mov     rcx, cs:?GpMemHeap@GpRuntime@@3PEAXEA; hHeap
0x1800350c5  mov     r8, rsi; dwBytes
0x1800350c8  xor     edx, edx; dwFlags
0x1800350ca  call    cs:__imp_HeapAlloc
0x1800350d0  test    rax, rax
0x1800350d3  jz      loc_180035193
0x1800350d9  mov     rcx, rax; this
0x1800350dc  call    ??0GpFontFileLoader@@QEAA@XZ; GpFontFileLoader::GpFontFileLoader(void)
0x1800350e1  mov     cs:?g_GpFontFileLoader@Globals@@3PEAUIDWriteFontFileLoader@@EA, rax; IDWriteFontFileLoader * Globals::g_GpFontFileLoader
0x1800350e8  mov     rdx, rax
0x1800350eb  test    rax, rax
0x1800350ee  jz      loc_180035056
0x1800350f4  mov     r8, cs:?g_DWriteFactory@Globals@@3PEAUIDWriteFactory@@EA; IDWriteFactory * Globals::g_DWriteFactory
0x1800350fb  mov     rcx, [r8]
0x1800350fe  mov     rax, [rcx+68h]
0x180035102  mov     rcx, r8
0x180035105  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003510a  test    eax, eax
0x18003510c  js      loc_180035056
0x180035112  mov     rcx, cs:?g_DWriteFactory@Globals@@3PEAUIDWriteFactory@@EA; IDWriteFactory * Globals::g_DWriteFactory
0x180035119  mov     rdx, cs:?g_GpFontCollectionFileLoader@Globals@@3PEAUIDWriteFontCollectionLoader@@EA; IDWriteFontCollectionLoader * Globals::g_GpFontCollectionFileLoader
0x180035120  mov     rax, [rcx]
0x180035123  mov     rax, [rax+28h]
0x180035127  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003512c  test    eax, eax
0x18003512e  js      loc_180035056
0x180035134  mov     rcx, cs:?g_DWriteFactory@Globals@@3PEAUIDWriteFactory@@EA; IDWriteFactory * Globals::g_DWriteFactory
0x18003513b  mov     rdx, cs:?g_GpFontCollectionStreamLoader@Globals@@3PEAUIDWriteFontCollectionLoader@@EA; IDWriteFontCollectionLoader * Globals::g_GpFontCollectionStreamLoader
0x180035142  mov     rax, [rcx]
0x180035145  mov     rax, [rax+28h]
0x180035149  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003514e  test    eax, eax
0x180035150  js      loc_180035056
0x180035156  mov     rcx, cs:?g_DWriteFactory@Globals@@3PEAUIDWriteFactory@@EA; IDWriteFactory * Globals::g_DWriteFactory
0x18003515d  lea     rdx, ?g_DWriteTextAnalyzer@Globals@@3PEAUIDWriteTextAnalyzer@@EA; IDWriteTextAnalyzer * Globals::g_DWriteTextAnalyzer
0x180035164  mov     rax, [rcx]
0x180035167  mov     rax, [rax+0A8h]
0x18003516e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035173  test    eax, eax
0x180035175  js      loc_180035056
0x18003517b  lea     rcx, ?critSec@LoadLibraryCriticalSection@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180035182  call    cs:__imp_LeaveCriticalSection
0x180035188  mov     eax, 1
0x18003518d  add     rsp, 20h
0x180035191  pop     rsi
0x180035192  retn
0x180035193  mov     cs:?g_GpFontFileLoader@Globals@@3PEAUIDWriteFontFileLoader@@EA, 0; IDWriteFontFileLoader * Globals::g_GpFontFileLoader
0x18003519e  jmp     loc_180035056
0x1800351a3  mov     rcx, cs:?g_DWriteFactory@Globals@@3PEAUIDWriteFactory@@EA; IDWriteFactory * Globals::g_DWriteFactory
0x1800351aa  mov     rax, [rcx]
0x1800351ad  mov     rax, [rax+30h]
0x1800351b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800351b6  mov     rcx, cs:?g_GpFontCollectionStreamLoader@Globals@@3PEAUIDWriteFontCollectionLoader@@EA; IDWriteFontCollectionLoader * Globals::g_GpFontCollectionStreamLoader
0x1800351bd  mov     rax, [rcx]
0x1800351c0  mov     rax, [rax+10h]
0x1800351c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800351c9  jmp     loc_18003503E
0x1800351ce  mov     rcx, cs:?g_DWriteFactory@Globals@@3PEAUIDWriteFactory@@EA; IDWriteFactory * Globals::g_DWriteFactory
0x1800351d5  mov     rax, [rcx]
0x1800351d8  mov     rax, [rax+30h]
0x1800351dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800351e1  mov     rcx, cs:?g_GpFontCollectionFileLoader@Globals@@3PEAUIDWriteFontCollectionLoader@@EA; IDWriteFontCollectionLoader * Globals::g_GpFontCollectionFileLoader
0x1800351e8  mov     rax, [rcx]
0x1800351eb  mov     rax, [rax+10h]
0x1800351ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800351f4  mov     cs:?g_GpFontCollectionFileLoader@Globals@@3PEAUIDWriteFontCollectionLoader@@EA, 0; IDWriteFontCollectionLoader * Globals::g_GpFontCollectionFileLoader
0x1800351ff  jmp     loc_180035076
0x180035204  mov     rcx, cs:?g_DWriteFactory@Globals@@3PEAUIDWriteFactory@@EA; IDWriteFactory * Globals::g_DWriteFactory
0x18003520b  mov     rax, [rcx]
0x18003520e  mov     rax, [rax+70h]
0x180035212  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035217  mov     rcx, cs:?g_GpFontFileLoader@Globals@@3PEAUIDWriteFontFileLoader@@EA; IDWriteFontFileLoader * Globals::g_GpFontFileLoader
0x18003521e  mov     rax, [rcx]
0x180035221  mov     rax, [rax+10h]
0x180035225  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003522a  mov     cs:?g_GpFontFileLoader@Globals@@3PEAUIDWriteFontFileLoader@@EA, 0; IDWriteFontFileLoader * Globals::g_GpFontFileLoader
0x180035235  jmp     loc_180035086
0x18003523a  mov     rax, [rcx]
0x18003523d  mov     rax, [rax+10h]
0x180035241  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035246  mov     cs:?g_DWriteFactory@Globals@@3PEAUIDWriteFactory@@EA, 0; IDWriteFactory * Globals::g_DWriteFactory
0x180035251  jmp     loc_180035096
```
