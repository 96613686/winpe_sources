# CspCompleteConsoleIo

- ea: `0x14001f07c`
- end: `0x14001f0d5`
- name: `CspCompleteConsoleIo`
- size: `89`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14001d83c`
- `0x14001dd4c`
- `0x14001ded4`
- `0x14001e20c`
- `0x14001e7d4`
- `0x14001e9b4`

## import_xrefs

- `ntdll!NtDeviceIoControlFile` at `0x14001f0bf`
- `ntdll!NtDeviceIoControlFile` at `0x14001f0bf`

## pseudocode

```c
__int64 __fastcall CspCompleteConsoleIo(void **a1, void *a2)
{
  void *v2; // rcx
  NTSTATUS v3; // eax
  unsigned int Status; // ecx
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-18h] BYREF

  v2 = *a1;
  IoStatusBlock = 0;
  v3 = NtDeviceIoControlFile(v2, 0, 0, 0, &IoStatusBlock, 0x50000Bu, a2, 0x28u, 0, 0);
  Status = IoStatusBlock.Status;
  if ( v3 < 0 )
    return (unsigned int)v3;
  return Status;
}

```

## disassembly

```asm
0x14001f07c  mov     rax, rsp
0x14001f07f  sub     rsp, 68h
0x14001f083  mov     rcx, [rcx]; FileHandle
0x14001f086  xorps   xmm0, xmm0
0x14001f089  mov     dword ptr [rax-20h], 0
0x14001f090  xor     r9d, r9d; ApcContext
0x14001f093  mov     qword ptr [rax-28h], 0
0x14001f09b  xor     r8d, r8d; ApcRoutine
0x14001f09e  mov     dword ptr [rax-30h], 28h ; '('
0x14001f0a5  mov     [rax-38h], rdx
0x14001f0a9  xor     edx, edx; Event
0x14001f0ab  mov     dword ptr [rax-40h], 50000Bh
0x14001f0b2  movups  xmmword ptr [rax-18h], xmm0
0x14001f0b6  lea     rax, [rax-18h]
0x14001f0ba  mov     [rsp+68h+IoStatusBlock], rax; IoStatusBlock
0x14001f0bf  call    cs:__imp_NtDeviceIoControlFile
0x14001f0c5  mov     ecx, dword ptr [rsp+68h+var_18]
0x14001f0c9  test    eax, eax
0x14001f0cb  cmovs   ecx, eax
0x14001f0ce  mov     eax, ecx
0x14001f0d0  add     rsp, 68h
0x14001f0d4  retn
```
