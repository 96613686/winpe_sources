# UndefineClassDescriptors

- ea: `0x180003a20`
- end: `0x180003a80`
- name: `UndefineClassDescriptors`
- size: `96`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180007058`

## callees

- `0x180003a20`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180003a41`
- `ntdll!RtlFreeHeap` at `0x180003a6b`
- `ntdll!RtlFreeHeap` at `0x180003a41`
- `ntdll!RtlFreeHeap` at `0x180003a6b`

## pseudocode

```c
char UndefineClassDescriptors()
{
  char result; // al

  if ( FMIFS_MESSAGE_cd )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, FMIFS_MESSAGE_cd);
  FMIFS_MESSAGE_cd = 0;
  if ( FMIFS_CHKMSG_cd )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, FMIFS_CHKMSG_cd);
  result = 1;
  FMIFS_CHKMSG_cd = 0;
  return result;
}

```

## disassembly

```asm
0x180003a20  push    rbx
0x180003a22  sub     rsp, 20h
0x180003a26  mov     r8, cs:?FMIFS_MESSAGE_cd@@3PEBVCLASS_DESCRIPTOR@@EB; P
0x180003a2d  test    r8, r8
0x180003a30  jz      short loc_180003A47
0x180003a32  mov     rcx, gs:60h
0x180003a3b  xor     edx, edx; Flags
0x180003a3d  mov     rcx, [rcx+30h]; HeapHandle
0x180003a41  call    cs:__imp_RtlFreeHeap
0x180003a47  mov     r8, cs:?FMIFS_CHKMSG_cd@@3PEBVCLASS_DESCRIPTOR@@EB; P
0x180003a4e  xor     ebx, ebx
0x180003a50  mov     cs:?FMIFS_MESSAGE_cd@@3PEBVCLASS_DESCRIPTOR@@EB, rbx; CLASS_DESCRIPTOR const * const FMIFS_MESSAGE_cd
0x180003a57  test    r8, r8
0x180003a5a  jz      short loc_180003A71
0x180003a5c  mov     rcx, gs:60h
0x180003a65  xor     edx, edx; Flags
0x180003a67  mov     rcx, [rcx+30h]; HeapHandle
0x180003a6b  call    cs:__imp_RtlFreeHeap
0x180003a71  mov     al, 1
0x180003a73  mov     cs:?FMIFS_CHKMSG_cd@@3PEBVCLASS_DESCRIPTOR@@EB, rbx; CLASS_DESCRIPTOR const * const FMIFS_CHKMSG_cd
0x180003a7a  add     rsp, 20h
0x180003a7e  pop     rbx
0x180003a7f  retn
```
