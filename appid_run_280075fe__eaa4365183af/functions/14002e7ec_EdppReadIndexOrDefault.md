# EdppReadIndexOrDefault

- ea: `0x14002e7ec`
- end: `0x14002e906`
- name: `EdppReadIndexOrDefault`
- size: `282`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14002e9d8`

## callees

- `0x14002e10c`
- `0x14002e2dc`
- `0x14002e7ec`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14002e8e6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002e8e6`
- `ntoskrnl!ZwReadFile` at `0x14002e892`
- `ntoskrnl!ZwReadFile` at `0x14002e892`
- `ntoskrnl!ZwClose` at `0x14002e8c5`
- `ntoskrnl!ZwClose` at `0x14002e8c5`

## pseudocode

```c
__int64 __fastcall EdppReadIndexOrDefault(__int64 a1, __int64 a2, HANDLE *a3, unsigned int *a4)
{
  int v6; // edx
  NTSTATUS v7; // ebx
  int v8; // r8d
  int v9; // r9d
  __int64 result; // rax
  HANDLE v11; // rcx
  PVOID P; // [rsp+50h] [rbp-20h] BYREF
  union _LARGE_INTEGER ByteOffset; // [rsp+58h] [rbp-18h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+60h] [rbp-10h] BYREF
  __int16 v15; // [rsp+98h] [rbp+28h] BYREF
  unsigned int Buffer; // [rsp+A0h] [rbp+30h] BYREF
  HANDLE FileHandle; // [rsp+A8h] [rbp+38h] BYREF

  *a3 = 0;
  *a4 = 0;
  v15 = 0;
  FileHandle = 0;
  Buffer = 0;
  P = 0;
  IoStatusBlock = 0;
  ByteOffset.QuadPart = 0;
  v7 = EdppComposeFullPath(a1, 0, &P, &v15);
  if ( v7 < 0 )
  {
    if ( FileHandle )
    {
      ZwClose(FileHandle);
      FileHandle = 0;
    }
  }
  else
  {
    result = EdppCreateOrOpenFileOrDirectory((int)P, v6, v8, v9, &FileHandle);
    if ( (int)result < 0 )
      return result;
    v11 = FileHandle;
    *a3 = FileHandle;
    v7 = ZwReadFile(v11, 0, 0, 0, &IoStatusBlock, &Buffer, 4u, &ByteOffset, 0);
    if ( v7 >= 0 && LODWORD(IoStatusBlock.Information) == 4 && Buffer < 0x80 )
      *a4 = Buffer;
    else
      v7 = 0;
  }
  if ( P )
    ExFreePoolWithTag(P, 0);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14002e7ec  mov     [rsp-18h+arg_0], rbx
0x14002e7f1  mov     byte ptr [rsp-18h+arg_8], dl
0x14002e7f5  push    rbp
0x14002e7f6  push    rsi
0x14002e7f7  push    r14
0x14002e7f9  mov     rbp, rsp
0x14002e7fc  sub     rsp, 70h
0x14002e800  xor     eax, eax
0x14002e802  mov     rsi, r9
0x14002e805  mov     [r8], rax
0x14002e808  mov     r14, r8
0x14002e80b  mov     [r9], eax
0x14002e80e  lea     r8, [rbp+P]
0x14002e812  xorps   xmm0, xmm0
0x14002e815  mov     [rbp+arg_8], ax
0x14002e819  lea     r9, [rbp+arg_8]
0x14002e81d  mov     [rbp+FileHandle], rax
0x14002e821  xor     edx, edx
0x14002e823  mov     [rbp+arg_10], eax
0x14002e826  mov     [rbp+P], rax
0x14002e82a  movups  xmmword ptr [rbp+var_10], xmm0
0x14002e82e  mov     qword ptr [rbp+var_18], rax
0x14002e832  call    EdppComposeFullPath
0x14002e837  mov     ebx, eax
0x14002e839  test    eax, eax
0x14002e83b  js      short loc_14002E8BC
0x14002e83d  mov     rcx, [rbp+P]; int
0x14002e841  lea     rax, [rbp+FileHandle]
0x14002e845  mov     [rsp+70h+IoStatusBlock], rax; FileHandle
0x14002e84a  call    EdppCreateOrOpenFileOrDirectory
0x14002e84f  test    eax, eax
0x14002e851  js      loc_14002E8F4
0x14002e857  mov     rcx, [rbp+FileHandle]; FileHandle
0x14002e85b  lea     rax, [rbp+var_18]
0x14002e85f  mov     [rsp+70h+Key], 0; Key
0x14002e868  xor     r9d, r9d; ApcContext
0x14002e86b  mov     [rsp+70h+ByteOffset], rax; ByteOffset
0x14002e870  xor     r8d, r8d; ApcRoutine
0x14002e873  lea     rax, [rbp+arg_10]
0x14002e877  mov     [rsp+70h+Length], 4; Length
0x14002e87f  mov     [rsp+70h+Buffer], rax; Buffer
0x14002e884  xor     edx, edx; Event
0x14002e886  lea     rax, [rbp+var_10]
0x14002e88a  mov     [r14], rcx
0x14002e88d  mov     [rsp+70h+IoStatusBlock], rax; IoStatusBlock
0x14002e892  call    cs:__imp_ZwReadFile
0x14002e899  nop     dword ptr [rax+rax+00h]
0x14002e89e  mov     ebx, eax
0x14002e8a0  test    eax, eax
0x14002e8a2  js      short loc_14002E8B8
0x14002e8a4  cmp     dword ptr [rbp+var_10.Information], 4
0x14002e8a8  jnz     short loc_14002E8B8
0x14002e8aa  mov     eax, [rbp+arg_10]
0x14002e8ad  cmp     eax, 80h
0x14002e8b2  jnb     short loc_14002E8B8
0x14002e8b4  mov     [rsi], eax
0x14002e8b6  jmp     short loc_14002E8D9
0x14002e8b8  xor     ebx, ebx
0x14002e8ba  jmp     short loc_14002E8D9
0x14002e8bc  mov     rcx, [rbp+FileHandle]; Handle
0x14002e8c0  test    rcx, rcx
0x14002e8c3  jz      short loc_14002E8D9
0x14002e8c5  call    cs:__imp_ZwClose
0x14002e8cc  nop     dword ptr [rax+rax+00h]
0x14002e8d1  mov     [rbp+FileHandle], 0
0x14002e8d9  cmp     [rbp+P], 0
0x14002e8de  jz      short loc_14002E8F2
0x14002e8e0  mov     rcx, [rbp+P]; P
0x14002e8e4  xor     edx, edx; Tag
0x14002e8e6  call    cs:__imp_ExFreePoolWithTag
0x14002e8ed  nop     dword ptr [rax+rax+00h]
0x14002e8f2  mov     eax, ebx
0x14002e8f4  mov     rbx, [rsp+70h+arg_0]
0x14002e8fc  add     rsp, 70h
0x14002e900  pop     r14
0x14002e902  pop     rsi
0x14002e903  pop     rbp
0x14002e904  retn
```
