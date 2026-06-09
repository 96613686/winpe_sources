# VfsGetVolumeName

- ea: `0x14001171c`
- end: `0x1400117e5`
- name: `VfsGetVolumeName`
- size: `201`
- prototype: `__int64 __fastcall(PFLT_VOLUME Volume, PUNICODE_STRING VolumeName)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140001de0`
- `0x140011438`
- `0x140024310`

## callees

- `0x14001171c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400117b7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400117b7`
- `ntoskrnl!ExAllocatePool2` at `0x140011771`
- `ntoskrnl!ExAllocatePool2` at `0x140011771`
- `FLTMGR!FltGetVolumeName` at `0x14001174a`
- `FLTMGR!FltGetVolumeName` at `0x14001179a`
- `FLTMGR!FltGetVolumeName` at `0x14001174a`
- `FLTMGR!FltGetVolumeName` at `0x14001179a`

## pseudocode

```c
__int64 __fastcall VfsGetVolumeName(PFLT_VOLUME Volume, PUNICODE_STRING VolumeName)
{
  NTSTATUS v4; // edi
  unsigned __int16 v5; // di
  wchar_t *Pool2; // rax
  wchar_t *Buffer; // rcx
  ULONG BufferSizeNeeded; // [rsp+38h] [rbp+10h] BYREF

  BufferSizeNeeded = 0;
  *(_DWORD *)&VolumeName->Length = 0;
  VolumeName->Buffer = 0;
  v4 = FltGetVolumeName(Volume, VolumeName, &BufferSizeNeeded);
  if ( v4 != -1073741789 )
    return (unsigned int)v4;
  v5 = BufferSizeNeeded;
  Pool2 = (wchar_t *)ExAllocatePool2(256, (unsigned __int16)BufferSizeNeeded, 1851147862);
  VolumeName->Buffer = Pool2;
  if ( Pool2 )
  {
    VolumeName->MaximumLength = v5;
    VolumeName->Length = 0;
    v4 = FltGetVolumeName(Volume, VolumeName, &BufferSizeNeeded);
    if ( v4 < 0 )
    {
      Buffer = VolumeName->Buffer;
      if ( Buffer )
      {
        ExFreePoolWithTag(Buffer, 0);
        VolumeName->Buffer = 0;
      }
    }
    return (unsigned int)v4;
  }
  return 3221225626LL;
}

```

## disassembly

```asm
0x14001171c  mov     [rsp+arg_0], rbx
0x140011721  mov     [rsp+arg_10], rsi
0x140011726  push    rdi
0x140011727  sub     rsp, 20h
0x14001172b  xor     eax, eax
0x14001172d  mov     [rsp+28h+BufferSizeNeeded], 0
0x140011735  lea     r8, [rsp+28h+BufferSizeNeeded]; BufferSizeNeeded
0x14001173a  mov     [rdx], eax
0x14001173c  mov     rbx, rdx
0x14001173f  mov     qword ptr [rdx+8], 0
0x140011747  mov     rsi, rcx
0x14001174a  call    cs:__imp_FltGetVolumeName
0x140011751  nop     dword ptr [rax+rax+00h]
0x140011756  mov     edi, eax
0x140011758  cmp     eax, 0C0000023h
0x14001175d  jnz     short loc_1400117CB
0x14001175f  movzx   edi, word ptr [rsp+28h+BufferSizeNeeded]
0x140011764  mov     ecx, 100h
0x140011769  mov     edx, edi
0x14001176b  mov     r8d, 6E564656h
0x140011771  call    cs:__imp_ExAllocatePool2
0x140011778  nop     dword ptr [rax+rax+00h]
0x14001177d  mov     [rbx+8], rax
0x140011781  test    rax, rax
0x140011784  jz      short loc_1400117DE
0x140011786  xor     eax, eax
0x140011788  mov     [rbx+2], di
0x14001178c  lea     r8, [rsp+28h+BufferSizeNeeded]; BufferSizeNeeded
0x140011791  mov     [rbx], ax
0x140011794  mov     rdx, rbx; VolumeName
0x140011797  mov     rcx, rsi; Volume
0x14001179a  call    cs:__imp_FltGetVolumeName
0x1400117a1  nop     dword ptr [rax+rax+00h]
0x1400117a6  mov     edi, eax
0x1400117a8  test    eax, eax
0x1400117aa  jns     short loc_1400117CB
0x1400117ac  mov     rcx, [rbx+8]; P
0x1400117b0  test    rcx, rcx
0x1400117b3  jz      short loc_1400117CB
0x1400117b5  xor     edx, edx; Tag
0x1400117b7  call    cs:__imp_ExFreePoolWithTag
0x1400117be  nop     dword ptr [rax+rax+00h]
0x1400117c3  mov     qword ptr [rbx+8], 0
0x1400117cb  mov     eax, edi
0x1400117cd  mov     rbx, [rsp+28h+arg_0]
0x1400117d2  mov     rsi, [rsp+28h+arg_10]
0x1400117d7  add     rsp, 20h
0x1400117db  pop     rdi
0x1400117dc  retn
0x1400117de  mov     eax, 0C000009Ah
0x1400117e3  jmp     short loc_1400117CD
```
