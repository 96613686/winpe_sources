# DefineClassDescriptors

- ea: `0x180003ab0`
- end: `0x180003b5b`
- name: `DefineClassDescriptors`
- size: `171`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180007058`

## callees

- `0x180003ab0`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180003ac9`
- `ntdll!RtlAllocateHeap` at `0x180003b0d`
- `ntdll!RtlAllocateHeap` at `0x180003ac9`
- `ntdll!RtlAllocateHeap` at `0x180003b0d`
- `ulib!??0CLASS_DESCRIPTOR@@QEAA@XZ` at `0x180003ad7`
- `ulib!??0CLASS_DESCRIPTOR@@QEAA@XZ` at `0x180003b1b`
- `ulib!??0CLASS_DESCRIPTOR@@QEAA@XZ` at `0x180003ad7`
- `ulib!??0CLASS_DESCRIPTOR@@QEAA@XZ` at `0x180003b1b`
- `ulib!?Initialize@CLASS_DESCRIPTOR@@QEAAEPEBD@Z` at `0x180003aee`
- `ulib!?Initialize@CLASS_DESCRIPTOR@@QEAAEPEBD@Z` at `0x180003b32`
- `ulib!?Initialize@CLASS_DESCRIPTOR@@QEAAEPEBD@Z` at `0x180003aee`
- `ulib!?Initialize@CLASS_DESCRIPTOR@@QEAAEPEBD@Z` at `0x180003b32`

## pseudocode

```c
bool DefineClassDescriptors()
{
  CLASS_DESCRIPTOR *Heap; // rax
  CLASS_DESCRIPTOR *v1; // rax
  CLASS_DESCRIPTOR *v2; // rax
  CLASS_DESCRIPTOR *v3; // rax

  Heap = (CLASS_DESCRIPTOR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 8u);
  if ( Heap )
  {
    v1 = CLASS_DESCRIPTOR::CLASS_DESCRIPTOR(Heap);
    FMIFS_MESSAGE_cd = v1;
    if ( v1 && CLASS_DESCRIPTOR::Initialize(v1, 0) )
    {
      v2 = (CLASS_DESCRIPTOR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 8u);
      if ( !v2 )
      {
        FMIFS_CHKMSG_cd = 0;
        return 0;
      }
      v3 = CLASS_DESCRIPTOR::CLASS_DESCRIPTOR(v2);
      FMIFS_CHKMSG_cd = v3;
      if ( v3 )
        return CLASS_DESCRIPTOR::Initialize(v3, 0) != 0;
    }
  }
  else
  {
    FMIFS_MESSAGE_cd = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x180003ab0  sub     rsp, 28h
0x180003ab4  mov     rcx, gs:60h
0x180003abd  xor     edx, edx; Flags
0x180003abf  mov     r8d, 8; Size
0x180003ac5  mov     rcx, [rcx+30h]; HeapHandle
0x180003ac9  call    cs:__imp_RtlAllocateHeap
0x180003acf  test    rax, rax
0x180003ad2  jz      short loc_180003B4D
0x180003ad4  mov     rcx, rax
0x180003ad7  call    cs:__imp_??0CLASS_DESCRIPTOR@@QEAA@XZ; CLASS_DESCRIPTOR::CLASS_DESCRIPTOR(void)
0x180003add  mov     cs:?FMIFS_MESSAGE_cd@@3PEBVCLASS_DESCRIPTOR@@EB, rax; CLASS_DESCRIPTOR const * const FMIFS_MESSAGE_cd
0x180003ae4  test    rax, rax
0x180003ae7  jz      short loc_180003B54
0x180003ae9  xor     edx, edx
0x180003aeb  mov     rcx, rax
0x180003aee  call    cs:__imp_?Initialize@CLASS_DESCRIPTOR@@QEAAEPEBD@Z; CLASS_DESCRIPTOR::Initialize(char const *)
0x180003af4  test    al, al
0x180003af6  jz      short loc_180003B54
0x180003af8  mov     rcx, gs:60h
0x180003b01  xor     edx, edx; Flags
0x180003b03  mov     r8d, 8; Size
0x180003b09  mov     rcx, [rcx+30h]; HeapHandle
0x180003b0d  call    cs:__imp_RtlAllocateHeap
0x180003b13  test    rax, rax
0x180003b16  jz      short loc_180003B3F
0x180003b18  mov     rcx, rax
0x180003b1b  call    cs:__imp_??0CLASS_DESCRIPTOR@@QEAA@XZ; CLASS_DESCRIPTOR::CLASS_DESCRIPTOR(void)
0x180003b21  mov     cs:?FMIFS_CHKMSG_cd@@3PEBVCLASS_DESCRIPTOR@@EB, rax; CLASS_DESCRIPTOR const * const FMIFS_CHKMSG_cd
0x180003b28  test    rax, rax
0x180003b2b  jz      short loc_180003B54
0x180003b2d  xor     edx, edx
0x180003b2f  mov     rcx, rax
0x180003b32  call    cs:__imp_?Initialize@CLASS_DESCRIPTOR@@QEAAEPEBD@Z; CLASS_DESCRIPTOR::Initialize(char const *)
0x180003b38  test    al, al
0x180003b3a  setnz   al
0x180003b3d  jmp     short loc_180003B56
0x180003b3f  mov     cs:?FMIFS_CHKMSG_cd@@3PEBVCLASS_DESCRIPTOR@@EB, rax; CLASS_DESCRIPTOR const * const FMIFS_CHKMSG_cd
0x180003b46  xor     al, al
0x180003b48  add     rsp, 28h
0x180003b4c  retn
0x180003b4d  mov     cs:?FMIFS_MESSAGE_cd@@3PEBVCLASS_DESCRIPTOR@@EB, rax; CLASS_DESCRIPTOR const * const FMIFS_MESSAGE_cd
0x180003b54  xor     al, al
0x180003b56  add     rsp, 28h
0x180003b5a  retn
```
