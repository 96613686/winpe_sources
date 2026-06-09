# NtFilterLoad

- ea: `0x180025d04`
- end: `0x180025f2b`
- name: `NtFilterLoad`
- size: `551`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x180026600`

## callees

- `0x180025d04`
- `0x18002676c`
- `0x180026828`
- `0x1800361a8`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180025e52`
- `ntdll!RtlAllocateHeap` at `0x180025e52`
- `ntdll!NtClose` at `0x180025eb9`
- `ntdll!NtClose` at `0x180036da1`
- `ntdll!NtClose` at `0x180025eb9`
- `ntdll!NtClose` at `0x180036da1`
- `ntdll!RtlFreeHeap` at `0x180025edc`
- `ntdll!RtlFreeHeap` at `0x180025f03`
- `ntdll!RtlFreeHeap` at `0x180036dc6`
- `ntdll!RtlFreeHeap` at `0x180036ded`
- `ntdll!RtlFreeHeap` at `0x180025edc`
- `ntdll!RtlFreeHeap` at `0x180025f03`
- `ntdll!RtlFreeHeap` at `0x180036dc6`
- `ntdll!RtlFreeHeap` at `0x180036ded`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180025d48`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180025d48`
- `ntdll!NtCreateFile` at `0x180025e05`
- `ntdll!NtCreateFile` at `0x180025e05`

## pseudocode

```c
__int64 __fastcall NtFilterLoad(_WORD *Src)
{
  void *v2; // rbx
  unsigned int v3; // edi
  unsigned int v4; // eax
  unsigned int v5; // eax
  __int64 v6; // rax
  size_t v7; // rsi
  _WORD *Heap; // rax
  int AllocationSize; // [rsp+20h] [rbp-B8h]
  ULONG FileAttributes; // [rsp+28h] [rbp-B0h]
  struct _UNICODE_STRING v12; // [rsp+68h] [rbp-70h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+78h] [rbp-60h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+88h] [rbp-50h] BYREF
  __int64 v15; // [rsp+E8h] [rbp+10h] BYREF
  void *FileHandle; // [rsp+F0h] [rbp+18h] BYREF

  FileHandle = (void *)-1LL;
  v2 = 0;
  v12 = 0;
  if ( !RtlDosPathNameToNtPathName_U(L"\\\\.\\FltMgr", &v12, 0, 0) )
  {
    v3 = -2147024893;
    goto LABEL_11;
  }
  *(&ObjectAttributes.Length + 1) = 0;
  memset(&ObjectAttributes.Attributes + 1, 0, 20);
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = &v12;
  IoStatusBlock = 0;
  v4 = NtCreateFile(&FileHandle, 0x120116u, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 2u, 1u, 0, 0, 0);
  if ( FileHandle == (void *)-1LL )
  {
    v5 = FilterHResultFromNtStatus(v4);
  }
  else
  {
    v6 = -1;
    do
      ++v6;
    while ( Src[v6] );
    v7 = (unsigned __int16)(2 * v6);
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, (unsigned int)(v7 + 2));
    v2 = Heap;
    if ( !Heap )
    {
      v3 = -2147024882;
      goto LABEL_11;
    }
    *Heap = v7;
    memcpy_0(Heap + 1, Src, v7);
    v5 = NtFilterpDeviceIoControl(FileHandle, 0x88004u, AllocationSize, FileAttributes, (__int64)&v15);
  }
  v3 = v5;
LABEL_11:
  if ( FileHandle != (void *)-1LL )
    NtClose(FileHandle);
  if ( v2 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v2);
  if ( v12.Buffer )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v12.Buffer);
  return v3;
}

```

## disassembly

```asm
0x180025d04  mov     rax, rsp
0x180025d07  mov     [rax+8], rbx
0x180025d0b  mov     [rax+20h], rsi
0x180025d0f  push    rdi
0x180025d10  push    r14
0x180025d12  push    r15
0x180025d14  sub     rsp, 0C0h
0x180025d1b  mov     rdi, rcx
0x180025d1e  mov     qword ptr [rax+18h], 0FFFFFFFFFFFFFFFFh
0x180025d26  xor     r15d, r15d
0x180025d29  mov     ebx, r15d
0x180025d2c  mov     [rax-78h], rbx
0x180025d30  xorps   xmm0, xmm0
0x180025d33  movups  xmmword ptr [rax-70h], xmm0
0x180025d37  xor     r9d, r9d; DirectoryInfo
0x180025d3a  xor     r8d, r8d; NtFileNamePart
0x180025d3d  lea     rdx, [rax-70h]; NtPathName
0x180025d41  lea     rcx, DosPathName; "\\\\.\\FltMgr"
0x180025d48  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x180025d4f  nop     dword ptr [rax+rax+00h]
0x180025d54  test    al, al
0x180025d56  jnz     short loc_180025D62
0x180025d58  mov     edi, 80070003h
0x180025d5d  jmp     loc_180025EAB
0x180025d62  xor     eax, eax
0x180025d64  mov     dword ptr [rsp+0D8h+ObjectAttributes+4], eax
0x180025d6b  xorps   xmm0, xmm0
0x180025d6e  movups  xmmword ptr [rsp+0D8h+ObjectAttributes.Length], xmm0
0x180025d76  movups  xmmword ptr [rsp+0D8h+ObjectAttributes.ObjectName], xmm0
0x180025d7e  movups  xmmword ptr [rsp+0D8h+ObjectAttributes+1Ch], xmm0
0x180025d86  mov     [rsp+0D8h+ObjectAttributes.Length], 30h ; '0'
0x180025d91  mov     [rsp+0D8h+ObjectAttributes.RootDirectory], r15
0x180025d99  mov     [rsp+0D8h+ObjectAttributes.Attributes], 40h ; '@'
0x180025da4  lea     rax, [rsp+0D8h+var_70]
0x180025da9  mov     [rsp+0D8h+ObjectAttributes.ObjectName], rax
0x180025db1  movdqu  xmmword ptr [rsp+0D8h+ObjectAttributes.SecurityDescriptor], xmm0
0x180025dba  movups  xmmword ptr [rsp+0D8h+IoStatusBlock], xmm0
0x180025dbf  mov     [rsp+0D8h+EaLength], r15d; EaLength
0x180025dc4  mov     [rsp+0D8h+EaBuffer], r15; EaBuffer
0x180025dc9  mov     [rsp+0D8h+CreateOptions], r15d; CreateOptions
0x180025dce  mov     [rsp+0D8h+CreateDisposition], 1; CreateDisposition
0x180025dd6  mov     [rsp+0D8h+ShareAccess], 2; ShareAccess
0x180025dde  mov     [rsp+0D8h+FileAttributes], 80h; int
0x180025de6  mov     [rsp+0D8h+AllocationSize], r15; int
0x180025deb  lea     r9, [rsp+0D8h+IoStatusBlock]; IoStatusBlock
0x180025df0  lea     r8, [rsp+0D8h+ObjectAttributes]; ObjectAttributes
0x180025df8  mov     edx, 120116h; DesiredAccess
0x180025dfd  lea     rcx, [rsp+0D8h+FileHandle]; FileHandle
0x180025e05  call    cs:__imp_NtCreateFile
0x180025e0c  nop     dword ptr [rax+rax+00h]
0x180025e11  cmp     [rsp+0D8h+FileHandle], 0FFFFFFFFFFFFFFFFh
0x180025e1a  jnz     short loc_180025E28
0x180025e1c  mov     ecx, eax
0x180025e1e  call    FilterHResultFromNtStatus
0x180025e23  jmp     loc_180025EA9
0x180025e28  or      rax, 0FFFFFFFFFFFFFFFFh
0x180025e2c  inc     rax
0x180025e2f  cmp     [rdi+rax*2], r15w
0x180025e34  jnz     short loc_180025E2C
0x180025e36  add     ax, ax
0x180025e39  movzx   esi, ax
0x180025e3c  lea     r14d, [rsi+2]
0x180025e40  mov     r8d, r14d; Size
0x180025e43  mov     rcx, gs:60h
0x180025e4c  xor     edx, edx; Flags
0x180025e4e  mov     rcx, [rcx+30h]; HeapHandle
0x180025e52  call    cs:__imp_RtlAllocateHeap
0x180025e59  nop     dword ptr [rax+rax+00h]
0x180025e5e  mov     rbx, rax
0x180025e61  mov     [rsp+0D8h+var_78], rax
0x180025e66  test    rax, rax
0x180025e69  jnz     short loc_180025E72
0x180025e6b  mov     edi, 8007000Eh
0x180025e70  jmp     short loc_180025EAB
0x180025e72  mov     [rax], si
0x180025e75  mov     r8, rsi; Size
0x180025e78  lea     rcx, [rax+2]; void *
0x180025e7c  mov     rdx, rdi; Src
0x180025e7f  call    memcpy_0
0x180025e84  lea     rax, [rsp+0D8h+arg_8]
0x180025e8c  mov     qword ptr [rsp+0D8h+ShareAccess], rax; __int64
0x180025e91  mov     r9d, r14d
0x180025e94  mov     r8, rbx
0x180025e97  mov     edx, 88004h; FsControlCode
0x180025e9c  mov     rcx, [rsp+0D8h+FileHandle]; Handle
0x180025ea4  call    NtFilterpDeviceIoControl
0x180025ea9  mov     edi, eax
0x180025eab  mov     rcx, [rsp+0D8h+FileHandle]; Handle
0x180025eb3  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180025eb7  jz      short loc_180025EC5
0x180025eb9  call    cs:__imp_NtClose
0x180025ec0  nop     dword ptr [rax+rax+00h]
0x180025ec5  test    rbx, rbx
0x180025ec8  jz      short loc_180025EE8
0x180025eca  mov     rcx, gs:60h
0x180025ed3  mov     r8, rbx; P
0x180025ed6  xor     edx, edx; Flags
0x180025ed8  mov     rcx, [rcx+30h]; HeapHandle
0x180025edc  call    cs:__imp_RtlFreeHeap
0x180025ee3  nop     dword ptr [rax+rax+00h]
0x180025ee8  cmp     [rsp+0D8h+P], r15
0x180025eed  jz      short loc_180025F0F
0x180025eef  mov     rcx, gs:60h
0x180025ef8  mov     r8, [rsp+0D8h+P]; P
0x180025efd  xor     edx, edx; Flags
0x180025eff  mov     rcx, [rcx+30h]; HeapHandle
0x180025f03  call    cs:__imp_RtlFreeHeap
0x180025f0a  nop     dword ptr [rax+rax+00h]
0x180025f0f  mov     eax, edi
0x180025f11  lea     r11, [rsp+0D8h+var_18]
0x180025f19  mov     rbx, [r11+20h]
0x180025f1d  mov     rsi, [r11+38h]
0x180025f21  mov     rsp, r11
0x180025f24  pop     r15
0x180025f26  pop     r14
0x180025f28  pop     rdi
0x180025f29  retn
0x180036d8b  push    rbp
0x180036d8d  sub     rsp, 60h
0x180036d91  mov     rbp, rdx
0x180036d94  mov     rcx, [rbp+0F0h]; Handle
0x180036d9b  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180036d9f  jz      short loc_180036DAE
0x180036da1  call    cs:__imp_NtClose
0x180036da8  nop     dword ptr [rax+rax+00h]
0x180036dad  nop
0x180036dae  mov     r8, [rbp+60h]; P
0x180036db2  test    r8, r8
0x180036db5  jz      short loc_180036DD3
0x180036db7  mov     rcx, gs:60h
0x180036dc0  xor     edx, edx; Flags
0x180036dc2  mov     rcx, [rcx+30h]; HeapHandle
0x180036dc6  call    cs:__imp_RtlFreeHeap
0x180036dcd  nop     dword ptr [rax+rax+00h]
0x180036dd2  nop
0x180036dd3  cmp     qword ptr [rbp+70h], 0
0x180036dd8  jz      short loc_180036DFA
0x180036dda  mov     rcx, gs:60h
0x180036de3  mov     r8, [rbp+70h]; P
0x180036de7  xor     edx, edx; Flags
0x180036de9  mov     rcx, [rcx+30h]; HeapHandle
0x180036ded  call    cs:__imp_RtlFreeHeap
0x180036df4  nop     dword ptr [rax+rax+00h]
0x180036df9  nop
0x180036dfa  add     rsp, 60h
0x180036dfe  pop     rbp
0x180036dff  retn
```
