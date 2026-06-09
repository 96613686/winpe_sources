# AipReadFileHandle

- ea: `0x140003500`
- end: `0x140003569`
- name: `AipReadFileHandle`
- size: `105`
- prototype: `__int64 __fastcall(HANDLE Handle)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x140003500`

## import_xrefs

- `ntoskrnl!ZwWaitForSingleObject` at `0x140003552`
- `ntoskrnl!ZwWaitForSingleObject` at `0x140003552`
- `ntoskrnl!ZwReadFile` at `0x140003537`
- `ntoskrnl!ZwReadFile` at `0x140003537`

## pseudocode

```c
NTSTATUS __fastcall AipReadFileHandle(HANDLE Handle, union _LARGE_INTEGER *a2, ULONG a3, void *a4)
{
  NTSTATUS result; // eax
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-18h] BYREF

  IoStatusBlock = 0;
  result = ZwReadFile(Handle, 0, 0, 0, &IoStatusBlock, a4, a3, a2, 0);
  if ( result == 259 )
  {
    ZwWaitForSingleObject(Handle, 0, 0);
    return IoStatusBlock.Status;
  }
  return result;
}

```

## disassembly

```asm
0x140003500  mov     rax, rsp
0x140003503  push    rbx
0x140003504  sub     rsp, 60h
0x140003508  mov     qword ptr [rax-28h], 0
0x140003510  xorps   xmm0, xmm0
0x140003513  mov     [rax-30h], rdx
0x140003517  xor     edx, edx; Event
0x140003519  mov     [rax-38h], r8d
0x14000351d  xor     r8d, r8d; ApcRoutine
0x140003520  mov     [rax-40h], r9
0x140003524  xor     r9d, r9d; ApcContext
0x140003527  mov     rbx, rcx
0x14000352a  movups  xmmword ptr [rax-18h], xmm0
0x14000352e  lea     rax, [rax-18h]
0x140003532  mov     [rsp+68h+IoStatusBlock], rax; IoStatusBlock
0x140003537  call    cs:__imp_ZwReadFile
0x14000353e  nop     dword ptr [rax+rax+00h]
0x140003543  cmp     eax, 103h
0x140003548  jnz     short loc_140003562
0x14000354a  xor     r8d, r8d; Timeout
0x14000354d  xor     edx, edx; Alertable
0x14000354f  mov     rcx, rbx; Handle
0x140003552  call    cs:__imp_ZwWaitForSingleObject
0x140003559  nop     dword ptr [rax+rax+00h]
0x14000355e  mov     eax, dword ptr [rsp+68h+var_18]
0x140003562  add     rsp, 60h
0x140003566  pop     rbx
0x140003567  retn
```
