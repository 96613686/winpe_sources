# operator delete(void *)

- ea: `0x140010994`
- end: `0x1400109b4`
- name: `??3@YAXPEAX@Z`
- size: `32`
- prototype: `void __fastcall(void *)`
- caller_count: `30`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x14001ac58`
- `0x14001b14c`
- `0x14001b1dc`
- `0x14001c6d0`
- `0x14001cfb8`
- `0x14001f80c`
- `0x14001f9ac`
- `0x1400205f4`
- `0x14002b9b4`
- `0x14002efec`
- `0x14002f138`
- `0x14002f164`
- `0x140034580`
- `0x140035b40`
- `0x140036570`
- `0x140036714`
- `0x1400379f4`
- `0x140037a50`
- `0x140037cac`
- `0x1400396d0`
- `0x14003ade0`
- `0x14003e430`
- `0x14003e4a0`
- `0x1400410c0`
- `0x140042f30`
- `0x14005a010`
- `0x14005a35c`
- `0x14005a7f0`
- `0x140086948`
- `0x140089eb0`

## callees

- `0x140010994`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400109a2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400109a2`

## pseudocode

```c
void __fastcall operator delete(void *a1)
{
  if ( a1 )
    ExFreePoolWithTag(a1, 0x646D4370u);
}

```

## disassembly

```asm
0x140010994  sub     rsp, 28h
0x140010998  test    rcx, rcx
0x14001099b  jz      short loc_1400109AE
0x14001099d  mov     edx, 646D4370h; Tag
0x1400109a2  call    cs:__imp_ExFreePoolWithTag
0x1400109a9  nop     dword ptr [rax+rax+00h]
0x1400109ae  add     rsp, 28h
0x1400109b2  retn
```
