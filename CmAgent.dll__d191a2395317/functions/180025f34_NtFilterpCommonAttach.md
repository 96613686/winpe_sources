# NtFilterpCommonAttach

- ea: `0x180025f34`
- end: `0x18002627c`
- name: `NtFilterpCommonAttach`
- size: `840`
- prototype: `__int64 __usercall@<rax>(void *Src@<rcx>, void *@<rdx>, void *FileHandle, __int64, size_t Size)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, reparse_path, loader_planting, broker_com_uri`

## callers

- `0x180026284`

## callees

- `0x180025f34`
- `0x18002676c`
- `0x180026828`
- `0x180036190`
- `0x1800361a8`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180026136`
- `ntdll!RtlAllocateHeap` at `0x180026136`
- `ntdll!NtClose` at `0x18002621f`
- `ntdll!NtClose` at `0x180036e1d`
- `ntdll!NtClose` at `0x18002621f`
- `ntdll!NtClose` at `0x180036e1d`
- `ntdll!RtlFreeHeap` at `0x180026242`
- `ntdll!RtlFreeHeap` at `0x180026269`
- `ntdll!RtlFreeHeap` at `0x180036e42`
- `ntdll!RtlFreeHeap` at `0x180036e69`
- `ntdll!RtlFreeHeap` at `0x180026242`
- `ntdll!RtlFreeHeap` at `0x180026269`
- `ntdll!RtlFreeHeap` at `0x180036e42`
- `ntdll!RtlFreeHeap` at `0x180036e69`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180025fa1`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180025fa1`
- `ntdll!NtCreateFile` at `0x180026062`
- `ntdll!NtCreateFile` at `0x180026062`

## pseudocode

```c
__int64 __fastcall NtFilterpCommonAttach(
        _WORD *Src,
        _WORD *a2,
        __int64 a3,
        _WORD *a4,
        __int64 FileHandle,
        __int64 a6,
        size_t Size)
{
  unsigned __int16 v10; // si
  _WORD *v11; // rbx
  __int64 v12; // rdi
  unsigned int v13; // edi
  unsigned int v14; // eax
  __int64 v16; // r14
  unsigned __int16 v17; // r14
  unsigned __int16 v18; // di
  __int64 v19; // rsi
  _WORD *Heap; // rax
  __int64 v21; // rcx
  unsigned __int16 v22; // di
  __int64 v23; // [rsp+0h] [rbp-F8h] BYREF
  PLARGE_INTEGER AllocationSize; // [rsp+20h] [rbp-D8h]
  ULONG FileAttributes; // [rsp+28h] [rbp-D0h]
  struct _UNICODE_STRING NtPathName; // [rsp+60h] [rbp-98h] BYREF
  _WORD *v27; // [rsp+70h] [rbp-88h]
  size_t v28; // [rsp+78h] [rbp-80h]
  size_t v29; // [rsp+80h] [rbp-78h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+88h] [rbp-70h] BYREF
  __int64 *v31; // [rsp+B8h] [rbp-40h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+C0h] [rbp-38h] BYREF
  unsigned int v33; // [rsp+110h] [rbp+18h]

  v31 = &v23;
  v10 = 0;
  v11 = 0;
  v27 = 0;
  v12 = -1;
  FileHandle = -1;
  NtPathName = 0;
  if ( Src && a2 )
  {
    if ( RtlDosPathNameToNtPathName_U(L"\\\\.\\FltMgr", &NtPathName, 0, 0) )
    {
      *(&ObjectAttributes.Length + 1) = 0;
      memset(&ObjectAttributes.Attributes + 1, 0, 20);
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 64;
      ObjectAttributes.ObjectName = &NtPathName;
      IoStatusBlock = 0;
      v14 = NtCreateFile((PHANDLE)&FileHandle, 0x12019Fu, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 3u, 1u, 0, 0, 0);
      if ( FileHandle == -1 )
      {
        v33 = FilterHResultFromNtStatus(v14);
        local_unwind_0(v31, &loc_18002609B);
        return v33;
      }
      v16 = -1;
      do
        ++v16;
      while ( Src[v16] );
      v17 = 2 * v16;
      do
        ++v12;
      while ( a2[v12] );
      v18 = 2 * v12;
      if ( a4 )
      {
        v19 = -1;
        do
          ++v19;
        while ( a4[v19] );
        v10 = 2 * v19;
      }
      Size = v17;
      v28 = v18;
      v29 = v10;
      Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v17 + 20 + v18 + (unsigned int)v10);
      v11 = Heap;
      v27 = Heap;
      if ( Heap )
      {
        *Heap = v17;
        Heap[1] = 20;
        memcpy_0(Heap + 10, Src, Size);
        v11[2] = v18;
        v21 = (unsigned __int16)(v17 + 20);
        v11[3] = v21;
        memcpy_0((char *)v11 + v21, a2, v28);
        *((_DWORD *)v11 + 2) = 1;
        v11[6] = v10;
        if ( a4 )
        {
          v22 = v17 + v18 + 20;
          v11[7] = v22;
          memcpy_0((char *)v11 + v22, a4, v29);
        }
        else
        {
          v11[7] = 0;
        }
        *((_DWORD *)v11 + 4) = 0;
        v13 = NtFilterpDeviceIoControl((HANDLE)FileHandle, 0x88010u, (int)AllocationSize, FileAttributes, (__int64)&a6);
      }
      else
      {
        v13 = -2147024882;
      }
    }
    else
    {
      v13 = -2147024893;
    }
  }
  else
  {
    v13 = -2147024809;
  }
  if ( FileHandle != -1 )
    NtClose((HANDLE)FileHandle);
  if ( v11 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v11);
  if ( NtPathName.Buffer )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, NtPathName.Buffer);
  return v13;
}

```

## disassembly

```asm
0x180025f34  mov     rax, rsp
0x180025f37  mov     [rax+8], rbx
0x180025f3b  mov     [rax+10h], rsi
0x180025f3f  mov     [rax+18h], r8d
0x180025f43  push    rdi
0x180025f44  push    r12
0x180025f46  push    r13
0x180025f48  push    r14
0x180025f4a  push    r15
0x180025f4c  sub     rsp, 0D0h
0x180025f53  mov     [rsp+0F8h+var_40], rsp
0x180025f5b  mov     r15, r9
0x180025f5e  mov     r13, rdx
0x180025f61  mov     r12, rcx
0x180025f64  xor     esi, esi
0x180025f66  mov     ebx, esi
0x180025f68  mov     [rsp+0F8h+var_88], rbx
0x180025f6d  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180025f71  mov     [rax+28h], rdi
0x180025f75  xorps   xmm0, xmm0
0x180025f78  movups  xmmword ptr [rsp+0F8h+NtPathName.Length], xmm0
0x180025f7d  test    rcx, rcx
0x180025f80  jz      loc_18002620C
0x180025f86  test    rdx, rdx
0x180025f89  jz      loc_18002620C
0x180025f8f  xor     r9d, r9d; DirectoryInfo
0x180025f92  xor     r8d, r8d; NtFileNamePart
0x180025f95  lea     rdx, [rsp+0F8h+NtPathName]; NtPathName
0x180025f9a  lea     rcx, DosPathName; "\\\\.\\FltMgr"
0x180025fa1  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x180025fa8  nop     dword ptr [rax+rax+00h]
0x180025fad  test    al, al
0x180025faf  jnz     short loc_180025FBB
0x180025fb1  mov     edi, 80070003h
0x180025fb6  jmp     loc_180026211
0x180025fbb  xor     eax, eax
0x180025fbd  mov     dword ptr [rsp+0F8h+ObjectAttributes+4], eax
0x180025fc4  xorps   xmm0, xmm0
0x180025fc7  movups  xmmword ptr [rsp+0F8h+ObjectAttributes.Length], xmm0
0x180025fcf  movups  xmmword ptr [rsp+0F8h+ObjectAttributes.ObjectName], xmm0
0x180025fd7  movups  xmmword ptr [rsp+0F8h+ObjectAttributes+1Ch], xmm0
0x180025fdf  mov     [rsp+0F8h+ObjectAttributes.Length], 30h ; '0'
0x180025fea  mov     [rsp+0F8h+ObjectAttributes.RootDirectory], rsi
0x180025ff2  mov     [rsp+0F8h+ObjectAttributes.Attributes], 40h ; '@'
0x180025ffd  lea     rax, [rsp+0F8h+NtPathName]
0x180026002  mov     [rsp+0F8h+ObjectAttributes.ObjectName], rax
0x18002600a  movdqu  xmmword ptr [rsp+0F8h+ObjectAttributes.SecurityDescriptor], xmm0
0x180026013  movups  xmmword ptr [rsp+0F8h+IoStatusBlock], xmm0
0x18002601b  mov     [rsp+0F8h+EaLength], esi; EaLength
0x18002601f  mov     [rsp+0F8h+EaBuffer], rsi; EaBuffer
0x180026024  mov     [rsp+0F8h+CreateOptions], esi; CreateOptions
0x180026028  mov     [rsp+0F8h+CreateDisposition], 1; CreateDisposition
0x180026030  mov     [rsp+0F8h+ShareAccess], 3; ShareAccess
0x180026038  mov     [rsp+0F8h+FileAttributes], 80h; int
0x180026040  mov     [rsp+0F8h+AllocationSize], rsi; int
0x180026045  lea     r9, [rsp+0F8h+IoStatusBlock]; IoStatusBlock
0x18002604d  lea     r8, [rsp+0F8h+ObjectAttributes]; ObjectAttributes
0x180026055  mov     edx, 12019Fh; DesiredAccess
0x18002605a  lea     rcx, [rsp+0F8h+FileHandle]; FileHandle
0x180026062  call    cs:__imp_NtCreateFile
0x180026069  nop     dword ptr [rax+rax+00h]
0x18002606e  cmp     [rsp+0F8h+FileHandle], rdi
0x180026076  jnz     short loc_1800260C0
0x180026078  mov     ecx, eax
0x18002607a  call    FilterHResultFromNtStatus
0x18002607f  mov     [rsp+0F8h+arg_10], eax
0x180026086  lea     rdx, loc_18002609B
0x18002608d  mov     rcx, [rsp+0F8h+var_40]
0x180026095  call    _local_unwind_0
0x18002609a  nop
0x18002609b  mov     eax, [rsp+0F8h+arg_10]
0x1800260a2  lea     r11, [rsp+0F8h+var_28]
0x1800260aa  mov     rbx, [r11+30h]
0x1800260ae  mov     rsi, [r11+38h]
0x1800260b2  mov     rsp, r11
0x1800260b5  pop     r15
0x1800260b7  pop     r14
0x1800260b9  pop     r13
0x1800260bb  pop     r12
0x1800260bd  pop     rdi
0x1800260be  retn
0x1800260c0  mov     r14, rdi
0x1800260c3  inc     r14
0x1800260c6  cmp     [r12+r14*2], si
0x1800260cb  jnz     short loc_1800260C3
0x1800260cd  add     r14w, r14w
0x1800260d1  inc     rdi
0x1800260d4  cmp     [r13+rdi*2+0], si
0x1800260da  jnz     short loc_1800260D1
0x1800260dc  add     di, di
0x1800260df  test    r15, r15
0x1800260e2  jz      short loc_1800260F7
0x1800260e4  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800260e8  xor     eax, eax
0x1800260ea  inc     rsi
0x1800260ed  cmp     [r15+rsi*2], ax
0x1800260f2  jnz     short loc_1800260EA
0x1800260f4  add     si, si
0x1800260f7  movzx   ecx, r14w
0x1800260fb  mov     [rsp+0F8h+Size], rcx
0x180026103  movzx   edx, di
0x180026106  mov     [rsp+0F8h+var_80], rdx
0x18002610b  movzx   eax, si
0x18002610e  mov     [rsp+0F8h+var_78], rax
0x180026116  add     eax, edx
0x180026118  add     ecx, 14h
0x18002611b  add     eax, ecx
0x18002611d  mov     [rsp+0F8h+arg_10], eax
0x180026124  mov     r8d, eax; Size
0x180026127  mov     rcx, gs:60h
0x180026130  xor     edx, edx; Flags
0x180026132  mov     rcx, [rcx+30h]; HeapHandle
0x180026136  call    cs:__imp_RtlAllocateHeap
0x18002613d  nop     dword ptr [rax+rax+00h]
0x180026142  mov     rbx, rax
0x180026145  mov     [rsp+0F8h+var_88], rax
0x18002614a  test    rax, rax
0x18002614d  jnz     short loc_18002615B
0x18002614f  mov     edi, 8007000Eh
0x180026154  xor     esi, esi
0x180026156  jmp     loc_180026211
0x18002615b  mov     [rax], r14w
0x18002615f  mov     eax, 14h
0x180026164  mov     [rbx+2], ax
0x180026168  lea     rcx, [rbx+14h]; void *
0x18002616c  mov     r8, [rsp+0F8h+Size]; Size
0x180026174  mov     rdx, r12; Src
0x180026177  call    memcpy_0
0x18002617c  mov     [rbx+4], di
0x180026180  mov     r12d, 14h
0x180026186  lea     eax, [r12+r14]
0x18002618a  movzx   ecx, ax
0x18002618d  mov     [rbx+6], cx
0x180026191  add     rcx, rbx; void *
0x180026194  mov     r8, [rsp+0F8h+var_80]; Size
0x180026199  mov     rdx, r13; Src
0x18002619c  call    memcpy_0
0x1800261a1  mov     dword ptr [rbx+8], 1
0x1800261a8  mov     [rbx+0Ch], si
0x1800261ac  xor     esi, esi
0x1800261ae  test    r15, r15
0x1800261b1  jz      short loc_1800261D7
0x1800261b3  add     di, r14w
0x1800261b7  add     di, r12w
0x1800261bb  movzx   ecx, di
0x1800261be  mov     [rbx+0Eh], cx
0x1800261c2  add     rcx, rbx; void *
0x1800261c5  mov     r8, [rsp+0F8h+var_78]; Size
0x1800261cd  mov     rdx, r15; Src
0x1800261d0  call    memcpy_0
0x1800261d5  jmp     short loc_1800261DB
0x1800261d7  mov     [rbx+0Eh], si
0x1800261db  mov     [rbx+10h], esi
0x1800261de  lea     rax, [rsp+0F8h+arg_28]
0x1800261e6  mov     qword ptr [rsp+0F8h+ShareAccess], rax; __int64
0x1800261eb  mov     r9d, [rsp+0F8h+arg_10]
0x1800261f3  mov     r8, rbx
0x1800261f6  mov     edx, 88010h; FsControlCode
0x1800261fb  mov     rcx, [rsp+0F8h+FileHandle]; Handle
0x180026203  call    NtFilterpDeviceIoControl
0x180026208  mov     edi, eax
0x18002620a  jmp     short loc_180026211
0x18002620c  mov     edi, 80070057h
0x180026211  mov     rcx, [rsp+0F8h+FileHandle]; Handle
0x180026219  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18002621d  jz      short loc_18002622B
0x18002621f  call    cs:__imp_NtClose
0x180026226  nop     dword ptr [rax+rax+00h]
0x18002622b  test    rbx, rbx
0x18002622e  jz      short loc_18002624E
0x180026230  mov     rcx, gs:60h
0x180026239  mov     r8, rbx; P
0x18002623c  xor     edx, edx; Flags
0x18002623e  mov     rcx, [rcx+30h]; HeapHandle
0x180026242  call    cs:__imp_RtlFreeHeap
0x180026249  nop     dword ptr [rax+rax+00h]
0x18002624e  cmp     [rsp+0F8h+NtPathName.Buffer], rsi
0x180026253  jz      short loc_180026275
0x180026255  mov     rcx, gs:60h
0x18002625e  mov     r8, [rsp+0F8h+NtPathName.Buffer]; P
0x180026263  xor     edx, edx; Flags
0x180026265  mov     rcx, [rcx+30h]; HeapHandle
0x180026269  call    cs:__imp_RtlFreeHeap
0x180026270  nop     dword ptr [rax+rax+00h]
0x180026275  mov     eax, edi
0x180026277  jmp     loc_1800260A2
0x180036e07  push    rbp
0x180036e09  sub     rsp, 60h
0x180036e0d  mov     rbp, rdx
0x180036e10  mov     rcx, [rbp+120h]; Handle
0x180036e17  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180036e1b  jz      short loc_180036E2A
0x180036e1d  call    cs:__imp_NtClose
0x180036e24  nop     dword ptr [rax+rax+00h]
0x180036e29  nop
0x180036e2a  mov     r8, [rbp+70h]; P
0x180036e2e  test    r8, r8
0x180036e31  jz      short loc_180036E4F
0x180036e33  mov     rcx, gs:60h
0x180036e3c  xor     edx, edx; Flags
0x180036e3e  mov     rcx, [rcx+30h]; HeapHandle
0x180036e42  call    cs:__imp_RtlFreeHeap
0x180036e49  nop     dword ptr [rax+rax+00h]
0x180036e4e  nop
0x180036e4f  cmp     qword ptr [rbp+68h], 0
0x180036e54  jz      short loc_180036E76
0x180036e56  mov     rcx, gs:60h
0x180036e5f  mov     r8, [rbp+68h]; P
0x180036e63  xor     edx, edx; Flags
0x180036e65  mov     rcx, [rcx+30h]; HeapHandle
0x180036e69  call    cs:__imp_RtlFreeHeap
0x180036e70  nop     dword ptr [rax+rax+00h]
0x180036e75  nop
0x180036e76  add     rsp, 60h
0x180036e7a  pop     rbp
0x180036e7b  retn
```
