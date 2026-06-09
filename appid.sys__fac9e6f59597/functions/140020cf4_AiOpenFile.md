# AiOpenFile

- ea: `0x140020cf4`
- end: `0x140020dad`
- name: `AiOpenFile`
- size: `185`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *, void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140020db4`

## callees

- `0x140020cf4`

## import_xrefs

- `ntoskrnl!ZwOpenFile` at `0x140020d5f`
- `ntoskrnl!ZwOpenFile` at `0x140020d5f`
- `ntoskrnl!KeDelayExecutionThread` at `0x140020d7c`
- `ntoskrnl!KeDelayExecutionThread` at `0x140020d7c`

## pseudocode

```c
__int64 __fastcall AiOpenFile(struct _UNICODE_STRING *a1, void **a2)
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
    v4 = ZwOpenFile(&FileHandle, 0x100018u, &ObjectAttributes, &IoStatusBlock, 7u, 0x20u);
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
0x140020cf4  mov     [rsp-18h+arg_8], rbx
0x140020cf9  push    rbp
0x140020cfa  push    rsi
0x140020cfb  push    rdi
0x140020cfc  mov     rbp, rsp
0x140020cff  sub     rsp, 70h
0x140020d03  xor     eax, eax
0x140020d05  mov     [rbp+FileHandle], 0
0x140020d0d  xorps   xmm0, xmm0
0x140020d10  mov     [rbp+ObjectAttributes.RootDirectory], rax
0x140020d14  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x140020d18  xor     edi, edi
0x140020d1a  mov     rsi, rdx
0x140020d1d  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140020d22  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x140020d2a  mov     qword ptr [rbp+ObjectAttributes.Attributes], 240h
0x140020d32  mov     [rbp+ObjectAttributes.ObjectName], rcx
0x140020d36  mov     qword ptr [rbp+Interval], 0FFFFFFFFFF676980h
0x140020d3e  mov     [rsp+70h+OpenOptions], 20h ; ' '; OpenOptions
0x140020d46  lea     r9, [rbp+IoStatusBlock]; IoStatusBlock
0x140020d4a  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140020d4e  mov     [rsp+70h+ShareAccess], 7; ShareAccess
0x140020d56  mov     edx, 100018h; DesiredAccess
0x140020d5b  lea     rcx, [rbp+FileHandle]; FileHandle
0x140020d5f  call    cs:__imp_ZwOpenFile
0x140020d66  nop     dword ptr [rax+rax+00h]
0x140020d6b  mov     ebx, eax
0x140020d6d  cmp     eax, 0C0000043h
0x140020d72  jnz     short loc_140020D8F
0x140020d74  lea     r8, [rbp+Interval]; Interval
0x140020d78  xor     edx, edx; Alertable
0x140020d7a  xor     ecx, ecx; WaitMode
0x140020d7c  call    cs:__imp_KeDelayExecutionThread
0x140020d83  nop     dword ptr [rax+rax+00h]
0x140020d88  inc     edi
0x140020d8a  cmp     edi, 0Ah
0x140020d8d  jb      short loc_140020D3E
0x140020d8f  test    ebx, ebx
0x140020d91  js      short loc_140020D9A
0x140020d93  mov     rax, [rbp+FileHandle]
0x140020d97  mov     [rsi], rax
0x140020d9a  mov     eax, ebx
0x140020d9c  mov     rbx, [rsp+70h+arg_8]
0x140020da4  add     rsp, 70h
0x140020da8  pop     rdi
0x140020da9  pop     rsi
0x140020daa  pop     rbp
0x140020dab  retn
```
