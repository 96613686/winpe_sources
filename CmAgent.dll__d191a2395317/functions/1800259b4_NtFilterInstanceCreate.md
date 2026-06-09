# NtFilterInstanceCreate

- ea: `0x1800259b4`
- end: `0x180025cfe`
- name: `NtFilterInstanceCreate`
- size: `842`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x180026284`

## callees

- `0x1800259b4`
- `0x18002676c`
- `0x180026828`
- `0x1800361a8`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180025b7d`
- `ntdll!RtlAllocateHeap` at `0x180025b7d`
- `ntdll!NtClose` at `0x180025ca4`
- `ntdll!NtClose` at `0x180036d35`
- `ntdll!NtClose` at `0x180025ca4`
- `ntdll!NtClose` at `0x180036d35`
- `ntdll!RtlFreeHeap` at `0x180025c89`
- `ntdll!RtlFreeHeap` at `0x180025cd4`
- `ntdll!RtlFreeHeap` at `0x180036d15`
- `ntdll!RtlFreeHeap` at `0x180036d63`
- `ntdll!RtlFreeHeap` at `0x180025c89`
- `ntdll!RtlFreeHeap` at `0x180025cd4`
- `ntdll!RtlFreeHeap` at `0x180036d15`
- `ntdll!RtlFreeHeap` at `0x180036d63`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180025a16`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180025a16`
- `ntdll!NtCreateFile` at `0x180025ada`
- `ntdll!NtCreateFile` at `0x180025ada`

## pseudocode

```c
__int64 __fastcall NtFilterInstanceCreate(_WORD *a1, _WORD *a2, _WORD *a3, void **a4)
{
  void **v4; // rsi
  void *v8; // rdi
  int v9; // ebx
  unsigned int v10; // eax
  int v11; // eax
  __int64 v12; // r14
  unsigned __int16 v13; // r14
  __int64 v14; // rbx
  __int64 v15; // r15
  unsigned __int16 v16; // r15
  unsigned __int16 v17; // bx
  _WORD *Heap; // rax
  _WORD *v19; // rsi
  unsigned __int16 v20; // r14
  unsigned __int16 v21; // ax
  int AllocationSize; // [rsp+20h] [rbp-F8h]
  ULONG FileAttributes; // [rsp+28h] [rbp-F0h]
  void *FileHandle; // [rsp+68h] [rbp-B0h] BYREF
  struct _UNICODE_STRING NtPathName; // [rsp+70h] [rbp-A8h] BYREF
  size_t Size; // [rsp+80h] [rbp-98h] BYREF
  _WORD *v28; // [rsp+88h] [rbp-90h]
  size_t v29; // [rsp+90h] [rbp-88h]
  size_t v30; // [rsp+98h] [rbp-80h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A0h] [rbp-78h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+D0h] [rbp-48h] BYREF

  v4 = a4;
  v8 = 0;
  v28 = 0;
  FileHandle = (void *)-1LL;
  NtPathName = 0;
  if ( !RtlDosPathNameToNtPathName_U(L"\\\\.\\FltMgr", &NtPathName, 0, 0) )
  {
    v9 = -2147024893;
    goto LABEL_20;
  }
  *(&ObjectAttributes.Length + 1) = 0;
  memset(&ObjectAttributes.Attributes + 1, 0, 20);
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = &NtPathName;
  IoStatusBlock = 0;
  v10 = NtCreateFile(&FileHandle, 0x12019Fu, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 3u, 1u, 0, 0, 0);
  if ( FileHandle == (void *)-1LL )
  {
    v11 = FilterHResultFromNtStatus(v10);
  }
  else
  {
    v12 = -1;
    do
      ++v12;
    while ( a1[v12] );
    v13 = 2 * v12;
    v14 = -1;
    v15 = -1;
    do
      ++v15;
    while ( a2[v15] );
    v16 = 2 * v15;
    if ( a3 )
    {
      do
        ++v14;
      while ( a3[v14] );
      v17 = 2 * v14;
    }
    else
    {
      v17 = 0;
    }
    Size = v13;
    v29 = v16;
    v30 = v17;
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v16 + v17 + (unsigned int)v13 + 20);
    v8 = Heap;
    v28 = Heap;
    if ( !Heap )
    {
      v9 = -2147024882;
      goto LABEL_20;
    }
    *((_DWORD *)Heap + 1) = 8;
    v19 = Heap + 4;
    *(_DWORD *)Heap = 1;
    Heap[5] = 12;
    Heap[4] = v13;
    memcpy_0((char *)Heap + (unsigned __int16)Heap[5] + 8, a1, Size);
    v20 = v19[1] + v13;
    v19[3] = v20;
    v19[2] = v16;
    memcpy_0((char *)v19 + v20, a2, v29);
    if ( a3 )
    {
      v21 = v19[3] + v19[2];
      v19[5] = v21;
      v19[4] = v17;
      memcpy_0((char *)v19 + v21, a3, v30);
    }
    else
    {
      *((_DWORD *)v19 + 2) = 0;
    }
    v11 = NtFilterpDeviceIoControl(FileHandle, 0x8400Cu, AllocationSize, FileAttributes, (__int64)&Size);
    v4 = a4;
  }
  v9 = v11;
LABEL_20:
  if ( v8 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v8);
  if ( v9 < 0 && FileHandle != (void *)-1LL )
  {
    NtClose(FileHandle);
    FileHandle = (void *)-1LL;
  }
  if ( NtPathName.Buffer )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, NtPathName.Buffer);
  *v4 = FileHandle;
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800259b4  mov     rax, rsp
0x1800259b7  mov     [rax+20h], r9
0x1800259bb  mov     [rax+10h], rdx
0x1800259bf  mov     [rax+8], rcx
0x1800259c3  push    rbx
0x1800259c4  push    rsi
0x1800259c5  push    rdi
0x1800259c6  push    r12
0x1800259c8  push    r13
0x1800259ca  push    r14
0x1800259cc  push    r15
0x1800259ce  sub     rsp, 0E0h
0x1800259d5  mov     rsi, r9
0x1800259d8  mov     r12, r8
0x1800259db  mov     r13, rdx
0x1800259de  mov     rbx, rcx
0x1800259e1  xor     r15d, r15d
0x1800259e4  mov     edi, r15d
0x1800259e7  mov     [rax-90h], r15
0x1800259ee  mov     [rsp+118h+var_B8], r15d
0x1800259f3  mov     [rsp+118h+FileHandle], 0FFFFFFFFFFFFFFFFh
0x1800259fc  xorps   xmm0, xmm0
0x1800259ff  movups  xmmword ptr [rsp+118h+NtPathName.Length], xmm0
0x180025a04  xor     r9d, r9d; DirectoryInfo
0x180025a07  xor     r8d, r8d; NtFileNamePart
0x180025a0a  lea     rdx, [rsp+118h+NtPathName]; NtPathName
0x180025a0f  lea     rcx, DosPathName; "\\\\.\\FltMgr"
0x180025a16  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x180025a1d  nop     dword ptr [rax+rax+00h]
0x180025a22  test    al, al
0x180025a24  jnz     short loc_180025A34
0x180025a26  mov     ebx, 80070003h
0x180025a2b  mov     [rsp+118h+var_B8], ebx
0x180025a2f  jmp     loc_180025C72
0x180025a34  xor     eax, eax
0x180025a36  mov     dword ptr [rsp+118h+ObjectAttributes+4], eax
0x180025a3d  xorps   xmm0, xmm0
0x180025a40  movups  xmmword ptr [rsp+118h+ObjectAttributes.Length], xmm0
0x180025a48  movups  xmmword ptr [rsp+118h+ObjectAttributes.ObjectName], xmm0
0x180025a50  movups  xmmword ptr [rsp+118h+ObjectAttributes+1Ch], xmm0
0x180025a58  mov     [rsp+118h+ObjectAttributes.Length], 30h ; '0'
0x180025a63  mov     [rsp+118h+ObjectAttributes.RootDirectory], r15
0x180025a6b  mov     [rsp+118h+ObjectAttributes.Attributes], 40h ; '@'
0x180025a76  lea     rax, [rsp+118h+NtPathName]
0x180025a7b  mov     [rsp+118h+ObjectAttributes.ObjectName], rax
0x180025a83  movdqu  xmmword ptr [rsp+118h+ObjectAttributes.SecurityDescriptor], xmm0
0x180025a8c  movups  xmmword ptr [rsp+118h+IoStatusBlock], xmm0
0x180025a94  mov     [rsp+118h+EaLength], r15d; EaLength
0x180025a99  mov     [rsp+118h+EaBuffer], r15; EaBuffer
0x180025a9e  mov     [rsp+118h+CreateOptions], r15d; CreateOptions
0x180025aa3  mov     [rsp+118h+CreateDisposition], 1; CreateDisposition
0x180025aab  mov     [rsp+118h+ShareAccess], 3; ShareAccess
0x180025ab3  mov     [rsp+118h+FileAttributes], 80h; int
0x180025abb  mov     [rsp+118h+AllocationSize], r15; int
0x180025ac0  lea     r9, [rsp+118h+IoStatusBlock]; IoStatusBlock
0x180025ac8  lea     r8, [rsp+118h+ObjectAttributes]; ObjectAttributes
0x180025ad0  mov     edx, 12019Fh; DesiredAccess
0x180025ad5  lea     rcx, [rsp+118h+FileHandle]; FileHandle
0x180025ada  call    cs:__imp_NtCreateFile
0x180025ae1  nop     dword ptr [rax+rax+00h]
0x180025ae6  cmp     [rsp+118h+FileHandle], 0FFFFFFFFFFFFFFFFh
0x180025aec  jnz     short loc_180025AFE
0x180025aee  mov     ecx, eax
0x180025af0  call    FilterHResultFromNtStatus
0x180025af5  mov     [rsp+118h+var_B8], eax
0x180025af9  jmp     loc_180025C70
0x180025afe  or      r14, 0FFFFFFFFFFFFFFFFh
0x180025b02  inc     r14
0x180025b05  cmp     [rbx+r14*2], r15w
0x180025b0a  jnz     short loc_180025B02
0x180025b0c  add     r14w, r14w
0x180025b10  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180025b14  mov     r15, rbx
0x180025b17  xor     eax, eax
0x180025b19  inc     r15
0x180025b1c  cmp     [r13+r15*2+0], ax
0x180025b22  jnz     short loc_180025B19
0x180025b24  add     r15w, r15w
0x180025b28  test    r12, r12
0x180025b2b  jz      short loc_180025B3C
0x180025b2d  inc     rbx
0x180025b30  cmp     [r12+rbx*2], ax
0x180025b35  jnz     short loc_180025B2D
0x180025b37  add     bx, bx
0x180025b3a  jmp     short loc_180025B3F
0x180025b3c  movzx   ebx, ax
0x180025b3f  movzx   ecx, r14w
0x180025b43  mov     [rsp+118h+Size], rcx
0x180025b4b  movzx   edx, r15w
0x180025b4f  mov     [rsp+118h+var_88], rdx
0x180025b57  movzx   eax, bx
0x180025b5a  mov     [rsp+118h+var_80], rax
0x180025b62  add     eax, edx
0x180025b64  lea     r13d, [rcx+14h]
0x180025b68  add     r13d, eax
0x180025b6b  mov     r8d, r13d; Size
0x180025b6e  mov     rcx, gs:60h
0x180025b77  xor     edx, edx; Flags
0x180025b79  mov     rcx, [rcx+30h]; HeapHandle
0x180025b7d  call    cs:__imp_RtlAllocateHeap
0x180025b84  nop     dword ptr [rax+rax+00h]
0x180025b89  mov     rdi, rax
0x180025b8c  mov     [rsp+118h+var_90], rax
0x180025b94  test    rax, rax
0x180025b97  jnz     short loc_180025BAA
0x180025b99  mov     ebx, 8007000Eh
0x180025b9e  mov     [rsp+118h+var_B8], ebx
0x180025ba2  xor     r15d, r15d
0x180025ba5  jmp     loc_180025C72
0x180025baa  mov     dword ptr [rax+4], 8
0x180025bb1  lea     rsi, [rax+8]
0x180025bb5  mov     dword ptr [rax], 1
0x180025bbb  mov     eax, 0Ch
0x180025bc0  mov     [rsi+2], ax
0x180025bc4  mov     [rsi], r14w
0x180025bc8  movzx   ecx, word ptr [rsi+2]
0x180025bcc  add     rcx, rsi; void *
0x180025bcf  mov     r8, [rsp+118h+Size]; Size
0x180025bd7  mov     rdx, [rsp+118h+Src]; Src
0x180025bdf  call    memcpy_0
0x180025be4  add     r14w, [rsi+2]
0x180025be9  movzx   ecx, r14w
0x180025bed  mov     [rsi+6], cx
0x180025bf1  mov     [rsi+4], r15w
0x180025bf6  add     rcx, rsi; void *
0x180025bf9  mov     r8, [rsp+118h+var_88]; Size
0x180025c01  mov     rdx, [rsp+118h+arg_8]; Src
0x180025c09  call    memcpy_0
0x180025c0e  xor     r15d, r15d
0x180025c11  test    r12, r12
0x180025c14  jz      short loc_180025C3E
0x180025c16  movzx   eax, word ptr [rsi+4]
0x180025c1a  add     ax, [rsi+6]
0x180025c1e  movzx   ecx, ax
0x180025c21  mov     [rsi+0Ah], cx
0x180025c25  mov     [rsi+8], bx
0x180025c29  add     rcx, rsi; void *
0x180025c2c  mov     r8, [rsp+118h+var_80]; Size
0x180025c34  mov     rdx, r12; Src
0x180025c37  call    memcpy_0
0x180025c3c  jmp     short loc_180025C42
0x180025c3e  mov     [rsi+8], r15d
0x180025c42  lea     rax, [rsp+118h+Size]
0x180025c4a  mov     qword ptr [rsp+118h+ShareAccess], rax; __int64
0x180025c4f  mov     r9d, r13d
0x180025c52  mov     r8, rdi
0x180025c55  mov     edx, 8400Ch; FsControlCode
0x180025c5a  mov     rcx, [rsp+118h+FileHandle]; Handle
0x180025c5f  call    NtFilterpDeviceIoControl
0x180025c64  mov     [rsp+118h+var_B8], eax
0x180025c68  mov     rsi, [rsp+118h+arg_18]
0x180025c70  mov     ebx, eax
0x180025c72  test    rdi, rdi
0x180025c75  jz      short loc_180025C95
0x180025c77  mov     rcx, gs:60h
0x180025c80  mov     r8, rdi; P
0x180025c83  xor     edx, edx; Flags
0x180025c85  mov     rcx, [rcx+30h]; HeapHandle
0x180025c89  call    cs:__imp_RtlFreeHeap
0x180025c90  nop     dword ptr [rax+rax+00h]
0x180025c95  test    ebx, ebx
0x180025c97  jns     short loc_180025CB9
0x180025c99  mov     rcx, [rsp+118h+FileHandle]; Handle
0x180025c9e  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180025ca2  jz      short loc_180025CB9
0x180025ca4  call    cs:__imp_NtClose
0x180025cab  nop     dword ptr [rax+rax+00h]
0x180025cb0  mov     [rsp+118h+FileHandle], 0FFFFFFFFFFFFFFFFh
0x180025cb9  cmp     [rsp+118h+NtPathName.Buffer], r15
0x180025cbe  jz      short loc_180025CE0
0x180025cc0  mov     rcx, gs:60h
0x180025cc9  mov     r8, [rsp+118h+NtPathName.Buffer]; P
0x180025cce  xor     edx, edx; Flags
0x180025cd0  mov     rcx, [rcx+30h]; HeapHandle
0x180025cd4  call    cs:__imp_RtlFreeHeap
0x180025cdb  nop     dword ptr [rax+rax+00h]
0x180025ce0  mov     rax, [rsp+118h+FileHandle]
0x180025ce5  mov     [rsi], rax
0x180025ce8  mov     eax, ebx
0x180025cea  add     rsp, 0E0h
0x180025cf1  pop     r15
0x180025cf3  pop     r14
0x180025cf5  pop     r13
0x180025cf7  pop     r12
0x180025cf9  pop     rdi
0x180025cfa  pop     rsi
0x180025cfb  pop     rbx
0x180025cfc  retn
0x180036cf1  push    rbp
0x180036cf3  sub     rsp, 60h
0x180036cf7  mov     rbp, rdx
0x180036cfa  mov     r8, [rbp+88h]; P
0x180036d01  test    r8, r8
0x180036d04  jz      short loc_180036D22
0x180036d06  mov     rcx, gs:60h
0x180036d0f  xor     edx, edx; Flags
0x180036d11  mov     rcx, [rcx+30h]; HeapHandle
0x180036d15  call    cs:__imp_RtlFreeHeap
0x180036d1c  nop     dword ptr [rax+rax+00h]
0x180036d21  nop
0x180036d22  test    dword ptr [rbp+60h], 80000000h
0x180036d29  jz      short loc_180036D49
0x180036d2b  mov     rcx, [rbp+68h]; Handle
0x180036d2f  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180036d33  jz      short loc_180036D49
0x180036d35  call    cs:__imp_NtClose
0x180036d3c  nop     dword ptr [rax+rax+00h]
0x180036d41  mov     qword ptr [rbp+68h], 0FFFFFFFFFFFFFFFFh
0x180036d49  cmp     qword ptr [rbp+78h], 0
0x180036d4e  jz      short loc_180036D70
0x180036d50  mov     rcx, gs:60h
0x180036d59  mov     r8, [rbp+78h]; P
0x180036d5d  xor     edx, edx; Flags
0x180036d5f  mov     rcx, [rcx+30h]; HeapHandle
0x180036d63  call    cs:__imp_RtlFreeHeap
0x180036d6a  nop     dword ptr [rax+rax+00h]
0x180036d6f  nop
0x180036d70  mov     rcx, [rbp+138h]
0x180036d77  mov     rax, [rbp+68h]
0x180036d7b  mov     [rcx], rax
0x180036d7e  add     rsp, 60h
0x180036d82  pop     rbp
0x180036d83  retn
```
