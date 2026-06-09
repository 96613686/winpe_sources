# VfsInstanceTeardownComplete

- ea: `0x140024310`
- end: `0x14002436d`
- name: `VfsInstanceTeardownComplete`
- size: `93`
- prototype: `void __fastcall(__int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x14001171c`
- `0x140012acc`
- `0x140024310`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14002435b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002435b`

## string_xrefs

- `0x140024340`: `VfsInstanceTeardownComplete() - VFS detached from volume: %wZ`

## pseudocode

```c
void __fastcall VfsInstanceTeardownComplete(__int64 a1)
{
  struct _UNICODE_STRING VolumeName; // [rsp+20h] [rbp-18h] BYREF

  *(_QWORD *)&VolumeName.Length = 0;
  VolumeName.Buffer = 0;
  _InterlockedDecrement(&dword_14001F3D0);
  if ( (int)VfsGetVolumeName(*(PFLT_VOLUME *)(a1 + 16), &VolumeName) >= 0 )
  {
    LogWrite(3, 0, L"VfsInstanceTeardownComplete() - VFS detached from volume: %wZ", &VolumeName);
    if ( VolumeName.Buffer )
      ExFreePoolWithTag(VolumeName.Buffer, 0);
  }
}

```

## disassembly

```asm
0x140024310  sub     rsp, 38h
0x140024314  xor     eax, eax
0x140024316  lea     rdx, [rsp+38h+VolumeName]; VolumeName
0x14002431b  mov     qword ptr [rsp+38h+VolumeName.Length], rax
0x140024320  mov     [rsp+38h+VolumeName.Buffer], rax
0x140024325  lock dec cs:dword_14001F3D0
0x14002432c  mov     rcx, [rcx+10h]; Volume
0x140024330  call    VfsGetVolumeName
0x140024335  test    eax, eax
0x140024337  js      short loc_140024367
0x140024339  xor     edx, edx
0x14002433b  lea     r9, [rsp+38h+VolumeName]
0x140024340  lea     r8, aVfsinstancetea; "VfsInstanceTeardownComplete() - VFS det"...
0x140024347  lea     ecx, [rdx+3]
0x14002434a  call    LogWrite
0x14002434f  mov     rcx, [rsp+38h+VolumeName.Buffer]; P
0x140024354  test    rcx, rcx
0x140024357  jz      short loc_140024367
0x140024359  xor     edx, edx; Tag
0x14002435b  call    cs:__imp_ExFreePoolWithTag
0x140024362  nop     dword ptr [rax+rax+00h]
0x140024367  add     rsp, 38h
0x14002436b  retn
```
