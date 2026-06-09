# SaferpIsDllAllowed

- ea: `0x180034914`
- end: `0x180034ad6`
- name: `SaferpIsDllAllowed`
- size: `450`
- prototype: `__int64 __fastcall(__int64, const void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180015bd0`

## callees

- `0x180034914`
- `0x180072042`
- `0x18007205a`

## import_xrefs

- `ntdll!NtClose` at `0x180034ac5`
- `ntdll!NtClose` at `0x180034ac5`
- `ntdll!NtOpenFile` at `0x18003499c`
- `ntdll!NtOpenFile` at `0x18003499c`
- `ntdll!NtDeviceIoControlFile` at `0x180034a8e`
- `ntdll!NtDeviceIoControlFile` at `0x180034a8e`
- `ntdll!RtlFreeHeap` at `0x180034ab4`
- `ntdll!RtlFreeHeap` at `0x180034ab4`
- `ntdll!RtlAllocateHeap` at `0x1800349cb`
- `ntdll!RtlAllocateHeap` at `0x1800349cb`

## pseudocode

```c
__int64 __fastcall SaferpIsDllAllowed(__int64 a1, const void **a2)
{
  NTSTATUS v4; // eax
  unsigned int v5; // ebx
  ULONG InputBufferLength; // r14d
  _WORD *Heap; // rax
  _WORD *InputBuffer; // rdi
  NTSTATUS v10; // eax
  struct _PEB *v11; // rcx
  _QWORD v12[2]; // [rsp+50h] [rbp-19h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+60h] [rbp-9h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp+7h] BYREF
  unsigned int OutputBuffer; // [rsp+E0h] [rbp+77h] BYREF
  HANDLE FileHandle; // [rsp+E8h] [rbp+7Fh] BYREF

  v12[0] = 2359330;
  FileHandle = 0;
  v12[1] = L"\\Device\\SrpDevice";
  OutputBuffer = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)v12;
  IoStatusBlock = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v4 = NtOpenFile(&FileHandle, 1u, &ObjectAttributes, &IoStatusBlock, 7u, 0);
  v5 = v4;
  if ( v4 < 0 )
  {
    if ( v4 == -1073741772 || v4 == -1073741810 )
      v5 = 0;
  }
  else
  {
    InputBufferLength = *(unsigned __int16 *)a2 + 10;
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, InputBufferLength);
    InputBuffer = Heap;
    if ( Heap )
    {
      memset_0(Heap, 0, InputBufferLength);
      *(_QWORD *)InputBuffer = a1;
      if ( *(_WORD *)a2 )
      {
        InputBuffer[4] = *(_WORD *)a2;
        memcpy_0(InputBuffer + 5, a2[1], *(unsigned __int16 *)a2);
      }
      OutputBuffer = 0;
      v10 = NtDeviceIoControlFile(
              FileHandle,
              0,
              0,
              0,
              &IoStatusBlock,
              0x225804u,
              InputBuffer,
              InputBufferLength,
              &OutputBuffer,
              4u);
      v11 = NtCurrentPeb();
      v5 = v10;
      if ( v10 >= 0 )
        v5 = OutputBuffer;
      RtlFreeHeap(v11->ProcessHeap, 0, InputBuffer);
    }
    else
    {
      v5 = -1073741801;
    }
  }
  if ( FileHandle )
    NtClose(FileHandle);
  return v5;
}

```

## disassembly

```asm
0x180034914  mov     [rsp-8+arg_0], rbx
0x180034919  mov     [rsp-8+arg_8], rsi
0x18003491e  push    rbp
0x18003491f  push    rdi
0x180034920  push    r12
0x180034922  push    r14
0x180034924  push    r15
0x180034926  lea     rbp, [rsp-37h]
0x18003492b  sub     rsp, 0A0h
0x180034932  xor     r12d, r12d
0x180034935  mov     [rbp+57h+var_70], 240022h
0x18003493d  xorps   xmm0, xmm0
0x180034940  mov     [rsp+0C0h+OpenOptions], r12d; OpenOptions
0x180034945  lea     rax, aDeviceSrpdevic; "\\Device\\SrpDevice"
0x18003494c  mov     [rbp+57h+FileHandle], r12
0x180034950  mov     [rbp+57h+var_68], rax
0x180034954  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180034958  mov     rsi, rdx
0x18003495b  mov     [rbp+57h+arg_10], r12d
0x18003495f  mov     r15, rcx
0x180034962  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18003496a  lea     rax, [rbp+57h+var_70]
0x18003496e  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x180034976  lea     edx, [r12+1]; DesiredAccess
0x18003497b  mov     [rbp+57h+ObjectAttributes.RootDirectory], r12
0x18003497f  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180034983  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180034987  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x18003498b  mov     [rsp+0C0h+ShareAccess], 7; ShareAccess
0x180034993  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x180034997  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18003499c  call    cs:__imp_NtOpenFile
0x1800349a3  nop     dword ptr [rax+rax+00h]
0x1800349a8  mov     ebx, eax
0x1800349aa  test    eax, eax
0x1800349ac  js      short loc_180034A10
0x1800349ae  mov     rcx, gs:60h
0x1800349b7  xor     edx, edx; Flags
0x1800349b9  movzx   r14d, word ptr [rsi]
0x1800349bd  add     r14d, 0Ah
0x1800349c1  mov     r8d, r14d; Size
0x1800349c4  mov     rcx, [rcx+30h]; HeapHandle
0x1800349c8  mov     ebx, r14d
0x1800349cb  call    cs:__imp_RtlAllocateHeap
0x1800349d2  nop     dword ptr [rax+rax+00h]
0x1800349d7  mov     rdi, rax
0x1800349da  test    rax, rax
0x1800349dd  jnz     short loc_180034A25
0x1800349df  mov     ebx, 0C0000017h
0x1800349e4  mov     rcx, [rbp+57h+FileHandle]; Handle
0x1800349e8  test    rcx, rcx
0x1800349eb  jnz     loc_180034AC5
0x1800349f1  lea     r11, [rsp+0C0h+var_20]
0x1800349f9  mov     eax, ebx
0x1800349fb  mov     rbx, [r11+30h]
0x1800349ff  mov     rsi, [r11+38h]
0x180034a03  mov     rsp, r11
0x180034a06  pop     r15
0x180034a08  pop     r14
0x180034a0a  pop     r12
0x180034a0c  pop     rdi
0x180034a0d  pop     rbp
0x180034a0e  retn
0x180034a10  cmp     eax, 0C0000034h
0x180034a15  jnz     short loc_180034A1C
0x180034a17  mov     ebx, r12d
0x180034a1a  jmp     short loc_1800349E4
0x180034a1c  cmp     eax, 0C000000Eh
0x180034a21  jnz     short loc_1800349E4
0x180034a23  jmp     short loc_180034A17
0x180034a25  mov     r8, rbx; Size
0x180034a28  xor     edx, edx; Val
0x180034a2a  mov     rcx, rdi; void *
0x180034a2d  call    memset_0
0x180034a32  mov     [rdi], r15
0x180034a35  movzx   eax, word ptr [rsi]
0x180034a38  test    ax, ax
0x180034a3b  jz      short loc_180034A52
0x180034a3d  mov     [rdi+8], ax
0x180034a41  lea     rcx, [rdi+0Ah]; void *
0x180034a45  movzx   r8d, word ptr [rsi]; Size
0x180034a49  mov     rdx, [rsi+8]; Src
0x180034a4d  call    memcpy_0
0x180034a52  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x180034a56  lea     rax, [rbp+57h+arg_10]
0x180034a5a  mov     [rsp+0C0h+OutputBufferLength], 4; OutputBufferLength
0x180034a62  xor     r9d, r9d; ApcContext
0x180034a65  mov     [rsp+0C0h+OutputBuffer], rax; OutputBuffer
0x180034a6a  xor     r8d, r8d; ApcRoutine
0x180034a6d  mov     [rsp+0C0h+InputBufferLength], r14d; InputBufferLength
0x180034a72  lea     rax, [rbp+57h+IoStatusBlock]
0x180034a76  mov     [rsp+0C0h+InputBuffer], rdi; InputBuffer
0x180034a7b  xor     edx, edx; Event
0x180034a7d  mov     [rsp+0C0h+OpenOptions], 225804h; IoControlCode
0x180034a85  mov     qword ptr [rsp+0C0h+ShareAccess], rax; IoStatusBlock
0x180034a8a  mov     [rbp+57h+arg_10], r12d
0x180034a8e  call    cs:__imp_NtDeviceIoControlFile
0x180034a95  nop     dword ptr [rax+rax+00h]
0x180034a9a  mov     rcx, gs:60h
0x180034aa3  mov     r8, rdi; P
0x180034aa6  test    eax, eax
0x180034aa8  mov     ebx, eax
0x180034aaa  cmovns  ebx, [rbp+57h+arg_10]
0x180034aae  xor     edx, edx; Flags
0x180034ab0  mov     rcx, [rcx+30h]; HeapHandle
0x180034ab4  call    cs:__imp_RtlFreeHeap
0x180034abb  nop     dword ptr [rax+rax+00h]
0x180034ac0  jmp     loc_1800349E4
0x180034ac5  call    cs:__imp_NtClose
0x180034acc  nop     dword ptr [rax+rax+00h]
0x180034ad1  jmp     loc_1800349F1
```
