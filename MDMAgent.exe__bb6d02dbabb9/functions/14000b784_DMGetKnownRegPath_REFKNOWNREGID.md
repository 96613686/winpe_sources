# DMGetKnownRegPath(REFKNOWNREGID)

- ea: `0x14000b784`
- end: `0x14000b7ba`
- name: `?DMGetKnownRegPath@@YAPEBGW4REFKNOWNREGID@@@Z`
- size: `54`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x14000bac4`
- `0x1400126d4`
- `0x140012ac0`
- `0x140012be4`
- `0x140012e74`
- `0x140018d74`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x14000b78d`
- `ntdll!RtlIsStateSeparationEnabled` at `0x14000b78d`

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
0x14000b784  push    rbx
0x14000b786  sub     rsp, 20h
0x14000b78a  movsxd  rbx, ecx
0x14000b78d  call    cs:__imp_RtlIsStateSeparationEnabled
0x14000b794  nop     dword ptr [rax+rax+00h]
0x14000b799  neg     al
0x14000b79b  lea     rcx, ?Paths@?1??DMGetKnownRegPath@@YAPEBGW4REFKNOWNREGID@@@Z@4QAY01QEBGA; ushort const * (near * `DMGetKnownRegPath(REFKNOWNREGID)'::`2'::Paths)[2]
0x14000b7a2  sbb     rax, rax
0x14000b7a5  shl     rbx, 4
0x14000b7a9  and     eax, 8
0x14000b7ac  add     rax, rbx
0x14000b7af  mov     rax, [rax+rcx]
0x14000b7b3  add     rsp, 20h
0x14000b7b7  pop     rbx
0x14000b7b8  retn
```
