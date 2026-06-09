# Common::ArrayOperations<StateRepository::CacheContextEntry,StateRepository::CacheContextEntry>::MemFree(StateRepository::CacheContextEntry * *)

- ea: `0x18000e670`
- end: `0x18000e696`
- name: `?MemFree@?$ArrayOperations@VCacheContextEntry@StateRepository@@V12@@Common@@SAXPEAPEAVCacheContextEntry@StateRepository@@@Z`
- size: `38`
- prototype: `BOOLEAN __fastcall(PVOID P)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000e3e0`
- `0x18000f7c0`

## callees

- `0x18000e670`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18000e68b`
- `ntdll!RtlFreeHeap` at `0x18000e68b`

## pseudocode

```c
BOOLEAN __fastcall Common::ArrayOperations<StateRepository::CacheContextEntry,StateRepository::CacheContextEntry>::MemFree(
        PVOID P)
{
  BOOLEAN result; // al

  if ( P )
    return RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  return result;
}

```

## disassembly

```asm
0x18000e670  sub     rsp, 28h
0x18000e674  mov     r8, rcx; P
0x18000e677  test    rcx, rcx
0x18000e67a  jz      short loc_18000E691
0x18000e67c  mov     rcx, gs:60h
0x18000e685  xor     edx, edx; Flags
0x18000e687  mov     rcx, [rcx+30h]; HeapHandle
0x18000e68b  call    cs:__imp_RtlFreeHeap
0x18000e691  add     rsp, 28h
0x18000e695  retn
```
