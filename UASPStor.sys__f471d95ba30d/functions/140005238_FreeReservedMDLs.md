# FreeReservedMDLs

- ea: `0x140005238`
- end: `0x1400052b1`
- name: `FreeReservedMDLs`
- size: `121`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140003618`
- `0x140004120`
- `0x140005108`

## callees

- `0x140005238`

## import_xrefs

- `ntoskrnl!IoFreeMdl` at `0x14000524d`
- `ntoskrnl!IoFreeMdl` at `0x140005270`
- `ntoskrnl!IoFreeMdl` at `0x140005293`
- `ntoskrnl!IoFreeMdl` at `0x14000524d`
- `ntoskrnl!IoFreeMdl` at `0x140005270`
- `ntoskrnl!IoFreeMdl` at `0x140005293`

## pseudocode

```c
void __fastcall FreeReservedMDLs(_QWORD *a1)
{
  struct _MDL *v2; // rcx
  struct _MDL *v3; // rcx
  struct _MDL *v4; // rcx

  v2 = (struct _MDL *)a1[180];
  if ( v2 )
  {
    IoFreeMdl(v2);
    a1[180] = 0;
  }
  v3 = (struct _MDL *)a1[182];
  if ( v3 )
  {
    IoFreeMdl(v3);
    a1[182] = 0;
  }
  v4 = (struct _MDL *)a1[181];
  if ( v4 )
  {
    IoFreeMdl(v4);
    a1[181] = 0;
  }
}

```

## disassembly

```asm
0x140005238  push    rbx
0x14000523a  sub     rsp, 20h
0x14000523e  mov     rbx, rcx
0x140005241  mov     rcx, [rcx+5A0h]; Mdl
0x140005248  test    rcx, rcx
0x14000524b  jz      short loc_140005264
0x14000524d  call    cs:__imp_IoFreeMdl
0x140005254  nop     dword ptr [rax+rax+00h]
0x140005259  mov     qword ptr [rbx+5A0h], 0
0x140005264  mov     rcx, [rbx+5B0h]; Mdl
0x14000526b  test    rcx, rcx
0x14000526e  jz      short loc_140005287
0x140005270  call    cs:__imp_IoFreeMdl
0x140005277  nop     dword ptr [rax+rax+00h]
0x14000527c  mov     qword ptr [rbx+5B0h], 0
0x140005287  mov     rcx, [rbx+5A8h]; Mdl
0x14000528e  test    rcx, rcx
0x140005291  jz      short loc_1400052AA
0x140005293  call    cs:__imp_IoFreeMdl
0x14000529a  nop     dword ptr [rax+rax+00h]
0x14000529f  mov     qword ptr [rbx+5A8h], 0
0x1400052aa  add     rsp, 20h
0x1400052ae  pop     rbx
0x1400052af  retn
```
