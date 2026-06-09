# GetHandle(ushort const *,void * *)

- ea: `0x1800190a0`
- end: `0x1800191d4`
- name: `?GetHandle@@YAJPEBGPEAPEAX@Z`
- size: `308`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, void **)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180019de0`
- `0x18001ca14`

## callees

- `0x1800152d4`
- `0x1800190a0`
- `0x18001b528`

## import_xrefs

- `ntdll!NtCreateFile` at `0x180019188`
- `ntdll!NtCreateFile` at `0x180019188`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180019102`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180019102`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
unsigned int __fastcall GetHandle(const unsigned __int16 *a1, void **a2)
{
  unsigned int v3; // ebx
  __int64 v4; // rdx
  NTSTATUS v6; // eax
  int AllocationSize; // [rsp+20h] [rbp-39h]
  _UNICODE_STRING NtPathName; // [rsp+60h] [rbp+7h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp+17h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  NtPathName = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  IoStatusBlock = 0;
  if ( !a2 )
  {
    v3 = -2147024809;
    v4 = 3049;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\storageusage\\storagegrovelerscans.cpp",
      (const char *)v3,
      AllocationSize);
    return v3;
  }
  if ( !RtlDosPathNameToNtPathName_U(a1, &NtPathName, 0, 0) )
  {
    v3 = -2147467259;
    v4 = 3054;
    goto LABEL_3;
  }
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = &NtPathName;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v6 = NtCreateFile(a2, 0x100180u, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 7u, 1u, 0x20u, 0, 0);
  if ( v6 < 0 )
    return wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)0xC00,
             (unsigned int)"onecore\\drivers\\storage\\storsvc\\storageusage\\storagegrovelerscans.cpp",
             (const char *)(unsigned int)v6,
             AllocationSize);
  if ( *a2 == (void *)-1LL )
  {
    v3 = -2147024890;
    v4 = 3074;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x1800190a0  mov     [rsp-8+arg_0], rbx
0x1800190a5  push    rbp
0x1800190a6  lea     rbp, [rsp-57h]
0x1800190ab  sub     rsp, 0B0h
0x1800190b2  xorps   xmm1, xmm1
0x1800190b5  xorps   xmm0, xmm0
0x1800190b8  mov     rbx, rdx
0x1800190bb  movups  xmmword ptr [rbp+57h+NtPathName.Length], xmm0
0x1800190bf  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm1
0x1800190c3  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm1
0x1800190c7  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm1
0x1800190cb  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x1800190cf  test    rdx, rdx
0x1800190d2  jnz     short loc_1800190F8
0x1800190d4  mov     ebx, 80070057h
0x1800190d9  mov     edx, 0BE9h; void *
0x1800190de  mov     rcx, [rbp+5Fh]; this
0x1800190e2  lea     r8, aOnecoreDrivers; "onecore\\drivers\\storage\\storsvc\\sto"...
0x1800190e9  mov     r9d, ebx; char *
0x1800190ec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800190f1  mov     eax, ebx
0x1800190f3  jmp     loc_1800191C3
0x1800190f8  xor     r9d, r9d; DirectoryInfo
0x1800190fb  lea     rdx, [rbp+57h+NtPathName]; NtPathName
0x1800190ff  xor     r8d, r8d; NtFileNamePart
0x180019102  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x180019108  test    al, al
0x18001910a  jnz     short loc_180019118
0x18001910c  mov     ebx, 80004005h
0x180019111  mov     edx, 0BEEh
0x180019116  jmp     short loc_1800190DE
0x180019118  mov     [rsp+0B0h+EaLength], 0; EaLength
0x180019120  lea     rax, [rbp+57h+NtPathName]
0x180019124  mov     [rsp+0B0h+EaBuffer], 0; EaBuffer
0x18001912d  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180019131  mov     [rsp+0B0h+CreateOptions], 20h ; ' '; CreateOptions
0x180019139  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18001913d  mov     [rsp+0B0h+CreateDisposition], 1; CreateDisposition
0x180019145  xorps   xmm0, xmm0
0x180019148  mov     [rsp+0B0h+ShareAccess], 7; ShareAccess
0x180019150  mov     edx, 100180h; DesiredAccess
0x180019155  mov     [rsp+0B0h+FileAttributes], 80h; FileAttributes
0x18001915d  mov     rcx, rbx; FileHandle
0x180019160  mov     [rsp+0B0h+AllocationSize], 0; int
0x180019169  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180019170  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x180019178  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x18001917f  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180019183  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180019188  call    cs:__imp_NtCreateFile
0x18001918e  test    eax, eax
0x180019190  jns     short loc_1800191AC
0x180019192  mov     rcx, [rbp+5Fh]; this
0x180019196  lea     r8, aOnecoreDrivers; "onecore\\drivers\\storage\\storsvc\\sto"...
0x18001919d  mov     r9d, eax; char *
0x1800191a0  mov     edx, 0C00h; void *
0x1800191a5  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800191aa  jmp     short loc_1800191C3
0x1800191ac  cmp     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x1800191b0  jnz     short loc_1800191C1
0x1800191b2  mov     ebx, 80070006h
0x1800191b7  mov     edx, 0C02h
0x1800191bc  jmp     loc_1800190DE
0x1800191c1  xor     eax, eax
0x1800191c3  mov     rbx, [rsp+0B0h+arg_0]
0x1800191cb  add     rsp, 0B0h
0x1800191d2  pop     rbp
0x1800191d3  retn
```
