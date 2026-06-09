# BaseSrvFreeWOWRecord

- ea: `0x18000a894`
- end: `0x18000a8f3`
- name: `BaseSrvFreeWOWRecord`
- size: `95`
- prototype: `BOOLEAN __fastcall(_QWORD *P)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000821c`
- `0x180008d80`
- `0x18000a0a0`
- `0x18000a674`
- `0x18000c454`

## callees

- `0x18000a72c`
- `0x18000a894`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18000a8b9`
- `ntdll!RtlFreeHeap` at `0x18000a8e0`
- `ntdll!RtlFreeHeap` at `0x18000a8b9`
- `ntdll!RtlFreeHeap` at `0x18000a8e0`

## pseudocode

```c
BOOLEAN __fastcall BaseSrvFreeWOWRecord(_QWORD *P)
{
  void *v1; // r8
  BOOLEAN result; // al

  if ( P )
  {
    v1 = (void *)P[6];
    if ( v1 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v1);
    BaseSrvFreeVDMInfo((_QWORD *)P[3]);
    return RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  }
  return result;
}

```

## disassembly

```asm
0x18000a894  test    rcx, rcx
0x18000a897  jz      short locret_18000A8F1
0x18000a899  push    rbx
0x18000a89a  sub     rsp, 20h
0x18000a89e  mov     r8, [rcx+30h]; P
0x18000a8a2  mov     rbx, rcx
0x18000a8a5  test    r8, r8
0x18000a8a8  jz      short loc_18000A8C5
0x18000a8aa  mov     rcx, gs:60h
0x18000a8b3  xor     edx, edx; Flags
0x18000a8b5  mov     rcx, [rcx+30h]; HeapHandle
0x18000a8b9  call    cs:__imp_RtlFreeHeap
0x18000a8c0  nop     dword ptr [rax+rax+00h]
0x18000a8c5  mov     rcx, [rbx+18h]; P
0x18000a8c9  call    BaseSrvFreeVDMInfo
0x18000a8ce  mov     rcx, gs:60h
0x18000a8d7  mov     r8, rbx; P
0x18000a8da  xor     edx, edx; Flags
0x18000a8dc  mov     rcx, [rcx+30h]; HeapHandle
0x18000a8e0  call    cs:__imp_RtlFreeHeap
0x18000a8e7  nop     dword ptr [rax+rax+00h]
0x18000a8ec  add     rsp, 20h
0x18000a8f0  pop     rbx
0x18000a8f1  retn
```
