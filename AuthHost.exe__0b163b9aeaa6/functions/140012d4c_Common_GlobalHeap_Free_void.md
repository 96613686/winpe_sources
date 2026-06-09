# Common::GlobalHeap::Free(void *)

- ea: `0x140012d4c`
- end: `0x140012d6c`
- name: `?Free@GlobalHeap@Common@@SAXPEAX@Z`
- size: `32`
- prototype: `void __fastcall(PVOID P)`
- caller_count: `23`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140002dfc`
- `0x1400034c0`
- `0x1400047c4`
- `0x140004930`
- `0x140004960`
- `0x140007040`
- `0x1400089e0`
- `0x140008a20`
- `0x140008a60`
- `0x14000d288`
- `0x14000d3a0`
- `0x14000d3e0`
- `0x14000d420`
- `0x14000d460`
- `0x14000d4a0`
- `0x14000ed20`
- `0x14000f548`
- `0x14000f998`
- `0x14000fa04`
- `0x14000fe40`
- `0x140012d04`
- `0x1400136c3`
- `0x1400136e9`

## callees

- `0x140012d4c`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x140012d61`
- `ntdll!RtlFreeHeap` at `0x140012d61`

## pseudocode

```c
void __fastcall Common::GlobalHeap::Free(PVOID P)
{
  if ( P )
    RtlFreeHeap(ReservedForLocalUse::g_heap, 0, P);
}

```

## disassembly

```asm
0x140012d4c  sub     rsp, 28h
0x140012d50  test    rcx, rcx
0x140012d53  jz      short loc_140012D67
0x140012d55  mov     r8, rcx; P
0x140012d58  xor     edx, edx; Flags
0x140012d5a  mov     rcx, cs:?g_heap@ReservedForLocalUse@@3PEAXEA; HeapHandle
0x140012d61  call    cs:__imp_RtlFreeHeap
0x140012d67  add     rsp, 28h
0x140012d6b  retn
```
