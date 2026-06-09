# DMGetKnownRegPath(REFKNOWNREGID)

- ea: `0x180005a38`
- end: `0x180005a6e`
- name: `?DMGetKnownRegPath@@YAPEBGW4REFKNOWNREGID@@@Z`
- size: `54`
- prototype: ``
- caller_count: `7`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180005bfc`
- `0x180005fbc`
- `0x1800060d8`
- `0x18000649c`
- `0x18000a464`
- `0x18001a7a0`
- `0x18001c220`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x180005a41`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180005a41`

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
0x180005a38  push    rbx
0x180005a3a  sub     rsp, 20h
0x180005a3e  movsxd  rbx, ecx
0x180005a41  call    cs:__imp_RtlIsStateSeparationEnabled
0x180005a48  nop     dword ptr [rax+rax+00h]
0x180005a4d  neg     al
0x180005a4f  lea     rcx, ?Paths@?1??DMGetKnownRegPath@@YAPEBGW4REFKNOWNREGID@@@Z@4QAY01QEBGA; ushort const * (near * `DMGetKnownRegPath(REFKNOWNREGID)'::`2'::Paths)[2]
0x180005a56  sbb     rax, rax
0x180005a59  shl     rbx, 4
0x180005a5d  and     eax, 8
0x180005a60  add     rax, rbx
0x180005a63  mov     rax, [rax+rcx]
0x180005a67  add     rsp, 20h
0x180005a6b  pop     rbx
0x180005a6c  retn
```
