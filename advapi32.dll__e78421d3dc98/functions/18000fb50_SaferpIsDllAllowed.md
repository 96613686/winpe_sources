# SaferpIsDllAllowed

- ea: `0x18000fb50`
- end: `0x18000fcf3`
- name: `SaferpIsDllAllowed`
- size: `419`
- prototype: `__int64 __fastcall(__int64, const void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180010870`

## callees

- `0x18000fb50`
- `0x180065042`
- `0x18006505a`

## import_xrefs

- `ntdll!NtClose` at `0x18000fce8`
- `ntdll!NtClose` at `0x18000fce8`
- `ntdll!NtOpenFile` at `0x18000fbd8`
- `ntdll!NtOpenFile` at `0x18000fbd8`
- `ntdll!NtDeviceIoControlFile` at `0x18000fcbd`
- `ntdll!NtDeviceIoControlFile` at `0x18000fcbd`
- `ntdll!RtlFreeHeap` at `0x18000fcdd`
- `ntdll!RtlFreeHeap` at `0x18000fcdd`
- `ntdll!RtlAllocateHeap` at `0x18000fc01`
- `ntdll!RtlAllocateHeap` at `0x18000fc01`

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
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+60h] [rbp-9h] BYREF
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
0x18000fb50  mov     [rsp-8+arg_0], rbx
0x18000fb55  mov     [rsp-8+arg_8], rsi
0x18000fb5a  push    rbp
0x18000fb5b  push    rdi
0x18000fb5c  push    r12
0x18000fb5e  push    r14
0x18000fb60  push    r15
0x18000fb62  lea     rbp, [rsp-37h]
0x18000fb67  sub     rsp, 0A0h
0x18000fb6e  xor     r12d, r12d
0x18000fb71  mov     [rbp+57h+var_70], 240022h
0x18000fb79  xorps   xmm0, xmm0
0x18000fb7c  mov     [rsp+0C0h+OpenOptions], r12d; OpenOptions
0x18000fb81  lea     rax, aDeviceSrpdevic; "\\Device\\SrpDevice"
0x18000fb88  mov     [rbp+57h+FileHandle], r12
0x18000fb8c  mov     [rbp+57h+var_68], rax
0x18000fb90  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18000fb94  mov     rsi, rdx
0x18000fb97  mov     [rbp+57h+arg_10], r12d
0x18000fb9b  mov     r15, rcx
0x18000fb9e  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18000fba6  lea     rax, [rbp+57h+var_70]
0x18000fbaa  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x18000fbb2  lea     edx, [r12+1]; DesiredAccess
0x18000fbb7  mov     [rbp+57h+ObjectAttributes.RootDirectory], r12
0x18000fbbb  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18000fbbf  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18000fbc3  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x18000fbc7  mov     [rsp+0C0h+ShareAccess], 7; ShareAccess
0x18000fbcf  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x18000fbd3  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000fbd8  call    cs:__imp_NtOpenFile
0x18000fbde  mov     ebx, eax
0x18000fbe0  test    eax, eax
0x18000fbe2  js      short loc_18000FC3F
0x18000fbe4  mov     rcx, gs:60h
0x18000fbed  xor     edx, edx; Flags
0x18000fbef  movzx   r14d, word ptr [rsi]
0x18000fbf3  add     r14d, 0Ah
0x18000fbf7  mov     r8d, r14d; Size
0x18000fbfa  mov     rcx, [rcx+30h]; HeapHandle
0x18000fbfe  mov     ebx, r14d
0x18000fc01  call    cs:__imp_RtlAllocateHeap
0x18000fc07  mov     rdi, rax
0x18000fc0a  test    rax, rax
0x18000fc0d  jnz     short loc_18000FC54
0x18000fc0f  mov     ebx, 0C0000017h
0x18000fc14  mov     rcx, [rbp+57h+FileHandle]; Handle
0x18000fc18  test    rcx, rcx
0x18000fc1b  jnz     loc_18000FCE8
0x18000fc21  lea     r11, [rsp+0C0h+var_20]
0x18000fc29  mov     eax, ebx
0x18000fc2b  mov     rbx, [r11+30h]
0x18000fc2f  mov     rsi, [r11+38h]
0x18000fc33  mov     rsp, r11
0x18000fc36  pop     r15
0x18000fc38  pop     r14
0x18000fc3a  pop     r12
0x18000fc3c  pop     rdi
0x18000fc3d  pop     rbp
0x18000fc3e  retn
0x18000fc3f  cmp     eax, 0C0000034h
0x18000fc44  jnz     short loc_18000FC4B
0x18000fc46  mov     ebx, r12d
0x18000fc49  jmp     short loc_18000FC14
0x18000fc4b  cmp     eax, 0C000000Eh
0x18000fc50  jnz     short loc_18000FC14
0x18000fc52  jmp     short loc_18000FC46
0x18000fc54  mov     r8, rbx; Size
0x18000fc57  xor     edx, edx; Val
0x18000fc59  mov     rcx, rdi; void *
0x18000fc5c  call    memset_0
0x18000fc61  mov     [rdi], r15
0x18000fc64  movzx   eax, word ptr [rsi]
0x18000fc67  test    ax, ax
0x18000fc6a  jz      short loc_18000FC81
0x18000fc6c  mov     [rdi+8], ax
0x18000fc70  lea     rcx, [rdi+0Ah]; void *
0x18000fc74  movzx   r8d, word ptr [rsi]; Size
0x18000fc78  mov     rdx, [rsi+8]; Src
0x18000fc7c  call    memcpy_0
0x18000fc81  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x18000fc85  lea     rax, [rbp+57h+arg_10]
0x18000fc89  mov     [rsp+0C0h+OutputBufferLength], 4; OutputBufferLength
0x18000fc91  xor     r9d, r9d; ApcContext
0x18000fc94  mov     [rsp+0C0h+OutputBuffer], rax; OutputBuffer
0x18000fc99  xor     r8d, r8d; ApcRoutine
0x18000fc9c  mov     [rsp+0C0h+InputBufferLength], r14d; InputBufferLength
0x18000fca1  lea     rax, [rbp+57h+IoStatusBlock]
0x18000fca5  mov     [rsp+0C0h+InputBuffer], rdi; InputBuffer
0x18000fcaa  xor     edx, edx; Event
0x18000fcac  mov     [rsp+0C0h+OpenOptions], 225804h; IoControlCode
0x18000fcb4  mov     qword ptr [rsp+0C0h+ShareAccess], rax; IoStatusBlock
0x18000fcb9  mov     [rbp+57h+arg_10], r12d
0x18000fcbd  call    cs:__imp_NtDeviceIoControlFile
0x18000fcc3  mov     rcx, gs:60h
0x18000fccc  mov     r8, rdi; P
0x18000fccf  test    eax, eax
0x18000fcd1  mov     ebx, eax
0x18000fcd3  cmovns  ebx, [rbp+57h+arg_10]
0x18000fcd7  xor     edx, edx; Flags
0x18000fcd9  mov     rcx, [rcx+30h]; HeapHandle
0x18000fcdd  call    cs:__imp_RtlFreeHeap
0x18000fce3  jmp     loc_18000FC14
0x18000fce8  call    cs:__imp_NtClose
0x18000fcee  jmp     loc_18000FC21
```
