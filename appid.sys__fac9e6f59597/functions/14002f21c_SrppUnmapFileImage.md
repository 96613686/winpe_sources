# SrppUnmapFileImage

- ea: `0x14002f21c`
- end: `0x14002f29e`
- name: `SrppUnmapFileImage`
- size: `130`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x14002ab78`
- `0x14002f05c`
- `0x14002f434`

## callees

- `0x14002f21c`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14002f268`
- `ntoskrnl!ObfDereferenceObject` at `0x14002f268`
- `ntoskrnl!PsInitialSystemProcess` at `0x14002f249`
- `ntoskrnl!ZwClose` at `0x14002f284`
- `ntoskrnl!ZwClose` at `0x14002f284`
- `ntoskrnl!MmUnmapViewInSystemSpace` at `0x14002f23b`
- `ntoskrnl!MmUnmapViewInSystemSpace` at `0x14002f23b`
- `ntoskrnl!MmUnmapViewOfSection` at `0x14002f253`
- `ntoskrnl!MmUnmapViewOfSection` at `0x14002f253`

## pseudocode

```c
int __fastcall SrppUnmapFileImage(__int64 a1)
{
  int result; // eax
  void *v3; // rcx

  if ( a1 )
  {
    if ( *(_QWORD *)(a1 + 8) )
    {
      if ( *(_BYTE *)(a1 + 32) )
        result = MmUnmapViewInSystemSpace(*(PVOID *)(a1 + 8));
      else
        result = MmUnmapViewOfSection(PsInitialSystemProcess);
    }
    v3 = *(void **)(a1 + 24);
    if ( v3 )
    {
      result = ObfDereferenceObject(v3);
      *(_QWORD *)(a1 + 24) = 0;
    }
    if ( *(_QWORD *)a1 )
    {
      result = ZwClose(*(HANDLE *)a1);
      *(_QWORD *)a1 = 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x14002f21c  test    rcx, rcx
0x14002f21f  jz      short locret_14002F29C
0x14002f221  push    rbx
0x14002f222  sub     rsp, 20h
0x14002f226  mov     rdx, [rcx+8]
0x14002f22a  mov     rbx, rcx
0x14002f22d  test    rdx, rdx
0x14002f230  jz      short loc_14002F25F
0x14002f232  cmp     byte ptr [rcx+20h], 0
0x14002f236  jz      short loc_14002F249
0x14002f238  mov     rcx, rdx; MappedBase
0x14002f23b  call    cs:__imp_MmUnmapViewInSystemSpace
0x14002f242  nop     dword ptr [rax+rax+00h]
0x14002f247  jmp     short loc_14002F25F
0x14002f249  mov     rcx, cs:__imp_PsInitialSystemProcess
0x14002f250  mov     rcx, [rcx]
0x14002f253  call    cs:__imp_MmUnmapViewOfSection
0x14002f25a  nop     dword ptr [rax+rax+00h]
0x14002f25f  mov     rcx, [rbx+18h]; Object
0x14002f263  test    rcx, rcx
0x14002f266  jz      short loc_14002F27C
0x14002f268  call    cs:__imp_ObfDereferenceObject
0x14002f26f  nop     dword ptr [rax+rax+00h]
0x14002f274  mov     qword ptr [rbx+18h], 0
0x14002f27c  mov     rcx, [rbx]; Handle
0x14002f27f  test    rcx, rcx
0x14002f282  jz      short loc_14002F297
0x14002f284  call    cs:__imp_ZwClose
0x14002f28b  nop     dword ptr [rax+rax+00h]
0x14002f290  mov     qword ptr [rbx], 0
0x14002f297  add     rsp, 20h
0x14002f29b  pop     rbx
0x14002f29c  retn
```
