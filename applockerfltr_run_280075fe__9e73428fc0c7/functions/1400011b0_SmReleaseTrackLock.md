# SmReleaseTrackLock

- ea: `0x1400011b0`
- end: `0x1400011cd`
- name: `SmReleaseTrackLock`
- size: `29`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x140007e00`

## import_xrefs

- `FLTMGR!FltReleaseResource` at `0x1400011bb`
- `FLTMGR!FltReleaseResource` at `0x1400011bb`

## pseudocode

```c
void SmReleaseTrackLock()
{
  FltReleaseResource(Resource);
}

```

## disassembly

```asm
0x1400011b0  sub     rsp, 28h
0x1400011b4  mov     rcx, cs:Resource; Resource
0x1400011bb  call    cs:__imp_FltReleaseResource
0x1400011c2  nop     dword ptr [rax+rax+00h]
0x1400011c7  add     rsp, 28h
0x1400011cb  retn
```
