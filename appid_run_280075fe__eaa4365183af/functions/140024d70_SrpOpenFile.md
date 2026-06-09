# SrpOpenFile

- ea: `0x140024d70`
- end: `0x140024e29`
- name: `SrpOpenFile`
- size: `185`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14002459c`
- `0x140024978`
- `0x140024c50`

## callees

- `0x140024d70`

## import_xrefs

- `ntoskrnl!ZwOpenFile` at `0x140024ddb`
- `ntoskrnl!ZwOpenFile` at `0x140024ddb`
- `ntoskrnl!KeDelayExecutionThread` at `0x140024df8`
- `ntoskrnl!KeDelayExecutionThread` at `0x140024df8`

## pseudocode

```c
__int64 __fastcall SrpOpenFile(struct _UNICODE_STRING *a1, void **a2)
{
  unsigned int v2; // edi
  NTSTATUS v4; // ebx
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+30h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  void *FileHandle; // [rsp+90h] [rbp+20h] BYREF
  union _LARGE_INTEGER Interval; // [rsp+A0h] [rbp+30h] BYREF

  FileHandle = 0;
  ObjectAttributes.RootDirectory = 0;
  IoStatusBlock = 0;
  v2 = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  ObjectAttributes.ObjectName = a1;
  Interval.QuadPart = -10000000;
  do
  {
    v4 = ZwOpenFile(&FileHandle, 0x80100000, &ObjectAttributes, &IoStatusBlock, 1u, 0x20u);
    if ( v4 != -1073741757 )
      break;
    KeDelayExecutionThread(0, 0, &Interval);
    ++v2;
  }
  while ( v2 < 0xA );
  if ( v4 >= 0 )
    *a2 = FileHandle;
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140024d70  mov     [rsp-18h+arg_8], rbx
0x140024d75  push    rbp
0x140024d76  push    rsi
0x140024d77  push    rdi
0x140024d78  mov     rbp, rsp
0x140024d7b  sub     rsp, 70h
0x140024d7f  xor     eax, eax
0x140024d81  mov     [rbp+FileHandle], 0
0x140024d89  xorps   xmm0, xmm0
0x140024d8c  mov     [rbp+ObjectAttributes.RootDirectory], rax
0x140024d90  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x140024d94  xor     edi, edi
0x140024d96  mov     rsi, rdx
0x140024d99  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140024d9e  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x140024da6  mov     qword ptr [rbp+ObjectAttributes.Attributes], 240h
0x140024dae  mov     [rbp+ObjectAttributes.ObjectName], rcx
0x140024db2  mov     qword ptr [rbp+Interval], 0FFFFFFFFFF676980h
0x140024dba  mov     [rsp+70h+OpenOptions], 20h ; ' '; OpenOptions
0x140024dc2  lea     r9, [rbp+IoStatusBlock]; IoStatusBlock
0x140024dc6  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140024dca  mov     [rsp+70h+ShareAccess], 1; ShareAccess
0x140024dd2  mov     edx, 80100000h; DesiredAccess
0x140024dd7  lea     rcx, [rbp+FileHandle]; FileHandle
0x140024ddb  call    cs:__imp_ZwOpenFile
0x140024de2  nop     dword ptr [rax+rax+00h]
0x140024de7  mov     ebx, eax
0x140024de9  cmp     eax, 0C0000043h
0x140024dee  jnz     short loc_140024E0B
0x140024df0  lea     r8, [rbp+Interval]; Interval
0x140024df4  xor     edx, edx; Alertable
0x140024df6  xor     ecx, ecx; WaitMode
0x140024df8  call    cs:__imp_KeDelayExecutionThread
0x140024dff  nop     dword ptr [rax+rax+00h]
0x140024e04  inc     edi
0x140024e06  cmp     edi, 0Ah
0x140024e09  jb      short loc_140024DBA
0x140024e0b  test    ebx, ebx
0x140024e0d  js      short loc_140024E16
0x140024e0f  mov     rax, [rbp+FileHandle]
0x140024e13  mov     [rsi], rax
0x140024e16  mov     eax, ebx
0x140024e18  mov     rbx, [rsp+70h+arg_8]
0x140024e20  add     rsp, 70h
0x140024e24  pop     rdi
0x140024e25  pop     rsi
0x140024e26  pop     rbp
0x140024e27  retn
```
