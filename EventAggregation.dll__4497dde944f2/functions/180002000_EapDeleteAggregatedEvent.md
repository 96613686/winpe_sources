# EapDeleteAggregatedEvent

- ea: `0x180002000`
- end: `0x18000209b`
- name: `EapDeleteAggregatedEvent`
- size: `155`
- prototype: `__int64 __fastcall(_QWORD *P)`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001170`
- `0x180001d50`
- `0x180001e00`

## callees

- `0x180002000`
- `0x180002130`
- `0x180002e30`
- `0x1800088d0`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180002046`
- `ntdll!RtlFreeHeap` at `0x180002065`
- `ntdll!RtlFreeHeap` at `0x180002046`
- `ntdll!RtlFreeHeap` at `0x180002065`

## pseudocode

```c
__int64 __fastcall EapDeleteAggregatedEvent(_QWORD *P)
{
  __int64 result; // rax

  if ( !P )
    return 3221225485LL;
  if ( P[1] )
  {
    result = EapDeleteAggregatedEventCondition();
    if ( (int)result < 0 )
      return result;
    EaLibFree(P[1]);
    P[1] = 0;
  }
  if ( *P )
  {
    result = BriDeleteBrokeredEvent((void *)(*P + 8LL));
    if ( (int)result < 0 )
      return result;
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, (PVOID)*P);
    *P = 0;
  }
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  return 0;
}

```

## disassembly

```asm
0x180002000  mov     [rsp+arg_0], rbx
0x180002005  push    rdi
0x180002006  sub     rsp, 20h
0x18000200a  mov     edi, edx
0x18000200c  mov     rbx, rcx
0x18000200f  test    rcx, rcx
0x180002012  jz      short loc_180002078
0x180002014  mov     rcx, [rcx+8]
0x180002018  test    rcx, rcx
0x18000201b  jnz     short loc_18000207F
0x18000201d  mov     rcx, [rbx]
0x180002020  test    rcx, rcx
0x180002023  jz      short loc_180002053
0x180002025  add     rcx, 8; Source1
0x180002029  mov     edx, edi
0x18000202b  call    BriDeleteBrokeredEvent
0x180002030  test    eax, eax
0x180002032  js      short loc_18000206D
0x180002034  mov     rcx, gs:60h
0x18000203d  xor     edx, edx; Flags
0x18000203f  mov     r8, [rbx]; P
0x180002042  mov     rcx, [rcx+30h]; HeapHandle
0x180002046  call    cs:__imp_RtlFreeHeap
0x18000204c  mov     qword ptr [rbx], 0
0x180002053  mov     rcx, gs:60h
0x18000205c  mov     r8, rbx; P
0x18000205f  xor     edx, edx; Flags
0x180002061  mov     rcx, [rcx+30h]; HeapHandle
0x180002065  call    cs:__imp_RtlFreeHeap
0x18000206b  xor     eax, eax
0x18000206d  mov     rbx, [rsp+28h+arg_0]
0x180002072  add     rsp, 20h
0x180002076  pop     rdi
0x180002077  retn
0x180002078  mov     eax, 0C000000Dh
0x18000207d  jmp     short loc_18000206D
0x18000207f  call    EapDeleteAggregatedEventCondition
0x180002084  test    eax, eax
0x180002086  js      short loc_18000206D
0x180002088  mov     rcx, [rbx+8]
0x18000208c  call    EaLibFree
0x180002091  mov     qword ptr [rbx+8], 0
0x180002099  jmp     short loc_18000201D
```
