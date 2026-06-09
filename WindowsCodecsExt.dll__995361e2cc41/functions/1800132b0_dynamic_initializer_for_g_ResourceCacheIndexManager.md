# _dynamic_initializer_for__g_ResourceCacheIndexManager__

- ea: `0x1800132b0`
- end: `0x180013319`
- name: `_dynamic_initializer_for__g_ResourceCacheIndexManager__`
- size: `105`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800132b0`
- `0x180013320`
- `0x1800171c4`
- `0x180021ef4`

## import_xrefs

- `ntdll!RtlInitializeBitMap` at `0x1800132f0`
- `ntdll!RtlInitializeBitMap` at `0x1800132f0`
- `ntdll!RtlSetBits` at `0x180013303`
- `ntdll!RtlSetBits` at `0x180013303`

## pseudocode

```c
int __fastcall dynamic_initializer_for__g_ResourceCacheIndexManager__(__int64 a1, unsigned int a2)
{
  int v2; // eax

  v2 = CCriticalSection::Init((LPCRITICAL_SECTION)&g_ResourceCacheIndexManager, a2);
  if ( v2 >= 0 )
  {
    BitMapBuffer = 0;
    RtlInitializeBitMap(&BitMapHeader, &BitMapBuffer, 0x20u);
    RtlSetBits(&BitMapHeader, 0, 1u);
  }
  else if ( g_doStackCaptures )
  {
    DoStackCapture(v2);
  }
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__g_ResourceCacheIndexManager__);
}

```

## disassembly

```asm
0x1800132b0  sub     rsp, 28h
0x1800132b4  lea     rcx, ?g_ResourceCacheIndexManager@@3VCMILResourceCacheIndexManager@@A; lpCriticalSection
0x1800132bb  call    ?Init@CCriticalSection@@QEAAJK@Z; CCriticalSection::Init(ulong)
0x1800132c0  test    eax, eax
0x1800132c2  jns     short loc_1800132D6
0x1800132c4  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800132cb  jz      short loc_180013309
0x1800132cd  mov     ecx, eax; int
0x1800132cf  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800132d4  jmp     short loc_180013309
0x1800132d6  xor     eax, eax
0x1800132d8  lea     rdx, BitMapBuffer; BitMapBuffer
0x1800132df  lea     rcx, BitMapHeader; BitMapHeader
0x1800132e6  mov     cs:BitMapBuffer, eax
0x1800132ec  lea     r8d, [rax+20h]; SizeOfBitMap
0x1800132f0  call    cs:__imp_RtlInitializeBitMap
0x1800132f6  xor     edx, edx; StartingIndex
0x1800132f8  lea     rcx, BitMapHeader; BitMapHeader
0x1800132ff  lea     r8d, [rdx+1]; NumberToSet
0x180013303  call    cs:__imp_RtlSetBits
0x180013309  lea     rcx, _dynamic_atexit_destructor_for__g_ResourceCacheIndexManager__
0x180013310  add     rsp, 28h
0x180013314  jmp     atexit
```
