# CFileRtlFOStream::Open(ushort const *,bool)

- ea: `0x14005ff00`
- end: `0x140060064`
- name: `?Open@CFileRtlFOStream@@QEAAJPEBG_N@Z`
- size: `356`
- prototype: `int(CFileRtlFOStream *__hidden this, const unsigned __int16 *, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, loader_planting`

## callers

- `0x140060b80`

## callees

- `0x14005ff00`
- `0x140080d70`

## import_xrefs

- `ntdll!NtOpenFile` at `0x14005ffbc`
- `ntdll!NtOpenFile` at `0x14005ffbc`
- `ntdll!NtClose` at `0x14005ff3b`
- `ntdll!NtClose` at `0x14005ff3b`
- `ntdll!RtlAllocateHeap` at `0x140060022`
- `ntdll!RtlAllocateHeap` at `0x140060022`
- `ntdll!RtlInitUnicodeString` at `0x14005ff6a`
- `ntdll!RtlInitUnicodeString` at `0x14005ff6a`
- `ntdll!NtQueryInformationFile` at `0x14005fff2`
- `ntdll!NtQueryInformationFile` at `0x14005fff2`

## pseudocode

```c
__int64 __fastcall CFileRtlFOStream::Open(struct _IO_STATUS_BLOCK *this, const unsigned __int16 *a2)
{
  HANDLE *v2; // rdi
  NTSTATUS v5; // ebx
  HANDLE v6; // rcx
  PVOID Heap; // rax
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-19h] BYREF
  __int128 FileInformation; // [rsp+60h] [rbp+17h] BYREF
  __int64 v11; // [rsp+70h] [rbp+27h]
  struct _UNICODE_STRING DestinationString; // [rsp+78h] [rbp+2Fh] BYREF

  v2 = (HANDLE *)&this[1];
  if ( this[1].Pointer != (PVOID)-1LL )
  {
    NtClose(*v2);
    *v2 = (HANDLE)-1LL;
  }
  *(&ObjectAttributes.Length + 1) = 0;
  memset(&ObjectAttributes.Attributes + 1, 0, 20);
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, a2);
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  v5 = NtOpenFile(v2, 0x100001u, &ObjectAttributes, this + 3, 5u, 0x24u);
  if ( v5 >= 0 )
  {
    v6 = *v2;
    v11 = 0;
    FileInformation = 0;
    v5 = NtQueryInformationFile(v6, this + 3, &FileInformation, 0x18u, FileStandardInformation);
    if ( v5 >= 0 )
    {
      this[2].Pointer = (PVOID)*((_QWORD *)&FileInformation + 1);
      Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, *((SIZE_T *)&FileInformation + 1));
      this[1].Information = (ULONG_PTR)Heap;
      if ( !Heap )
        return (unsigned int)-1073741801;
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14005ff00  mov     [rsp-8+arg_10], rbx
0x14005ff05  mov     [rsp-8+arg_18], rsi
0x14005ff0a  push    rbp
0x14005ff0b  push    rdi
0x14005ff0c  push    r14
0x14005ff0e  lea     rbp, [rsp-47h]
0x14005ff13  sub     rsp, 90h
0x14005ff1a  mov     rax, cs:__security_cookie
0x14005ff21  xor     rax, rsp
0x14005ff24  mov     [rbp+57h+var_18], rax
0x14005ff28  lea     rdi, [rcx+10h]
0x14005ff2c  mov     rbx, rdx
0x14005ff2f  cmp     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x14005ff33  mov     rsi, rcx
0x14005ff36  jz      short loc_14005FF4E
0x14005ff38  mov     rcx, [rdi]; Handle
0x14005ff3b  call    cs:__imp_NtClose
0x14005ff42  nop     dword ptr [rax+rax+00h]
0x14005ff47  mov     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x14005ff4e  xorps   xmm0, xmm0
0x14005ff51  mov     dword ptr [rbp+57h+ObjectAttributes+4], 0
0x14005ff58  mov     rdx, rbx; SourceString
0x14005ff5b  mov     dword ptr [rbp+57h+ObjectAttributes+1Ch], 0
0x14005ff62  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14005ff66  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14005ff6a  call    cs:__imp_RtlInitUnicodeString
0x14005ff71  nop     dword ptr [rax+rax+00h]
0x14005ff76  lea     rax, [rbp+57h+DestinationString]
0x14005ff7a  mov     [rsp+0A0h+OpenOptions], 24h ; '$'; OpenOptions
0x14005ff82  xorps   xmm0, xmm0
0x14005ff85  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14005ff89  lea     r9, [rsi+30h]; IoStatusBlock
0x14005ff8d  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14005ff94  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14005ff98  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x14005ffa0  mov     edx, 100001h; DesiredAccess
0x14005ffa5  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x14005ffac  mov     rcx, rdi; FileHandle
0x14005ffaf  mov     [rsp+0A0h+ShareAccess], 5; ShareAccess
0x14005ffb7  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14005ffbc  call    cs:__imp_NtOpenFile
0x14005ffc3  nop     dword ptr [rax+rax+00h]
0x14005ffc8  mov     ebx, eax
0x14005ffca  test    eax, eax
0x14005ffcc  js      short loc_14006003D
0x14005ffce  mov     rcx, [rdi]; FileHandle
0x14005ffd1  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x14005ffd5  xor     eax, eax
0x14005ffd7  mov     [rsp+0A0h+ShareAccess], 5; FileInformationClass
0x14005ffdf  xorps   xmm0, xmm0
0x14005ffe2  mov     [rbp+57h+var_30], rax
0x14005ffe6  lea     rdx, [rsi+30h]; IoStatusBlock
0x14005ffea  movups  [rbp+57h+FileInformation], xmm0
0x14005ffee  lea     r9d, [rax+18h]; Length
0x14005fff2  call    cs:__imp_NtQueryInformationFile
0x14005fff9  nop     dword ptr [rax+rax+00h]
0x14005fffe  mov     ebx, eax
0x140060000  test    eax, eax
0x140060002  js      short loc_14006003D
0x140060004  mov     rax, qword ptr [rbp+57h+FileInformation+8]
0x140060008  mov     edx, 8; Flags
0x14006000d  mov     [rsi+20h], rax
0x140060011  mov     rcx, gs:60h
0x14006001a  mov     r8, qword ptr [rbp+57h+FileInformation+8]; Size
0x14006001e  mov     rcx, [rcx+30h]; HeapHandle
0x140060022  call    cs:__imp_RtlAllocateHeap
0x140060029  nop     dword ptr [rax+rax+00h]
0x14006002e  test    rax, rax
0x140060031  mov     [rsi+18h], rax
0x140060035  mov     ecx, 0C0000017h
0x14006003a  cmovz   ebx, ecx
0x14006003d  mov     eax, ebx
0x14006003f  mov     rcx, [rbp+57h+var_18]
0x140060043  xor     rcx, rsp; StackCookie
0x140060046  call    __security_check_cookie
0x14006004b  lea     r11, [rsp+0A0h+var_10]
0x140060053  mov     rbx, [r11+30h]
0x140060057  mov     rsi, [r11+38h]
0x14006005b  mov     rsp, r11
0x14006005e  pop     r14
0x140060060  pop     rdi
0x140060061  pop     rbp
0x140060062  retn
```
