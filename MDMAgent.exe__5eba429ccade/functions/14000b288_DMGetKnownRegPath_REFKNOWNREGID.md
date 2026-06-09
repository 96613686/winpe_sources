# DMGetKnownRegPath(REFKNOWNREGID)

- ea: `0x14000b288`
- end: `0x14000b2b7`
- name: `?DMGetKnownRegPath@@YAPEBGW4REFKNOWNREGID@@@Z`
- size: `47`
- prototype: `__int64 __fastcall(int)`
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x14000b5a0`
- `0x140011eb4`
- `0x140012220`
- `0x140012330`
- `0x140012574`
- `0x140018060`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x14000b291`
- `ntdll!RtlIsStateSeparationEnabled` at `0x14000b291`

## pseudocode

```c
__int64 __fastcall DMGetKnownRegPath(int a1)
{
  return *(__int64 *)((char *)&`DMGetKnownRegPath'::`2'::Paths[2 * a1]
                    + ((unsigned __int8)RtlIsStateSeparationEnabled() != 0 ? 8 : 0));
}

```

## disassembly

```asm
0x14000b288  push    rbx
0x14000b28a  sub     rsp, 20h
0x14000b28e  movsxd  rbx, ecx
0x14000b291  call    cs:__imp_RtlIsStateSeparationEnabled
0x14000b297  neg     al
0x14000b299  lea     rcx, ?Paths@?1??DMGetKnownRegPath@@YAPEBGW4REFKNOWNREGID@@@Z@4QAY01QEBGA; ushort const * (near * `DMGetKnownRegPath(REFKNOWNREGID)'::`2'::Paths)[2]
0x14000b2a0  sbb     rax, rax
0x14000b2a3  shl     rbx, 4
0x14000b2a7  and     eax, 8
0x14000b2aa  add     rax, rbx
0x14000b2ad  mov     rax, [rax+rcx]
0x14000b2b1  add     rsp, 20h
0x14000b2b5  pop     rbx
0x14000b2b6  retn
```
