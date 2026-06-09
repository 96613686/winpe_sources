# BiGetSystemPartition

- ea: `0x14001c458`
- end: `0x14001c502`
- name: `BiGetSystemPartition`
- size: `170`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14001c14c`
- `0x14001c508`

## callees

- `0x140013814`
- `0x14001c458`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x14001c4a7`
- `ntdll!RtlAllocateHeap` at `0x14001c4a7`
- `ntdll!RtlFreeHeap` at `0x14001c4e5`
- `ntdll!RtlFreeHeap` at `0x14001c4e5`

## pseudocode

```c
__int64 __fastcall BiGetSystemPartition(_QWORD *a1)
{
  int FirmwarePartition; // eax
  int v3; // ebx
  PVOID Heap; // rax
  void *v5; // rdi

  FirmwarePartition = SyspartGetFirmwarePartition(0);
  v3 = FirmwarePartition;
  if ( FirmwarePartition == -1073741789 )
  {
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0);
    v5 = Heap;
    if ( Heap )
    {
      v3 = SyspartGetFirmwarePartition(Heap);
      if ( v3 >= 0 )
        *a1 = v5;
      else
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
    }
    else
    {
      return (unsigned int)-1073741801;
    }
  }
  else if ( FirmwarePartition >= 0 )
  {
    return (unsigned int)-1073741823;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x14001c458  mov     rax, rsp
0x14001c45b  mov     [rax+8], rbx
0x14001c45f  mov     [rax+18h], rsi
0x14001c463  push    rdi
0x14001c464  sub     rsp, 20h
0x14001c468  mov     rsi, rcx
0x14001c46b  mov     dword ptr [rax+10h], 0
0x14001c472  xor     ecx, ecx; void *
0x14001c474  lea     r8, [rax+10h]
0x14001c478  xor     edx, edx
0x14001c47a  call    SyspartGetFirmwarePartition
0x14001c47f  mov     ebx, eax
0x14001c481  cmp     eax, 0C0000023h
0x14001c486  jz      short loc_14001C493
0x14001c488  test    eax, eax
0x14001c48a  js      short loc_14001C4F0
0x14001c48c  mov     ebx, 0C0000001h
0x14001c491  jmp     short loc_14001C4F0
0x14001c493  mov     rcx, gs:60h
0x14001c49c  xor     edx, edx; Flags
0x14001c49e  mov     r8d, dword ptr [rsp+28h+Size]; Size
0x14001c4a3  mov     rcx, [rcx+30h]; HeapHandle
0x14001c4a7  call    cs:__imp_RtlAllocateHeap
0x14001c4ad  mov     rdi, rax
0x14001c4b0  test    rax, rax
0x14001c4b3  jnz     short loc_14001C4BC
0x14001c4b5  mov     ebx, 0C0000017h
0x14001c4ba  jmp     short loc_14001C4F0
0x14001c4bc  mov     edx, dword ptr [rsp+28h+Size]
0x14001c4c0  lea     r8, [rsp+28h+Size]
0x14001c4c5  mov     rcx, rdi; void *
0x14001c4c8  call    SyspartGetFirmwarePartition
0x14001c4cd  mov     ebx, eax
0x14001c4cf  test    eax, eax
0x14001c4d1  jns     short loc_14001C4ED
0x14001c4d3  mov     rcx, gs:60h
0x14001c4dc  mov     r8, rdi; P
0x14001c4df  xor     edx, edx; Flags
0x14001c4e1  mov     rcx, [rcx+30h]; HeapHandle
0x14001c4e5  call    cs:__imp_RtlFreeHeap
0x14001c4eb  jmp     short loc_14001C4F0
0x14001c4ed  mov     [rsi], rdi
0x14001c4f0  mov     rsi, [rsp+28h+arg_10]
0x14001c4f5  mov     eax, ebx
0x14001c4f7  mov     rbx, [rsp+28h+arg_0]
0x14001c4fc  add     rsp, 20h
0x14001c500  pop     rdi
0x14001c501  retn
```
