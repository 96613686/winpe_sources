# FaddpWriteFrameworkToStream(_FADD_FRAMEWORK *,RtlMemoryStream *)

- ea: `0x180056b18`
- end: `0x180056cda`
- name: `?FaddpWriteFrameworkToStream@@YAJPEAU_FADD_FRAMEWORK@@PEAVRtlMemoryStream@@@Z`
- size: `450`
- prototype: `__int64 __fastcall(struct _FADD_FRAMEWORK *, struct RtlMemoryStream *this)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18004dd68`

## callees

- `0x1800197d4`
- `0x18002f95c`
- `0x180056b18`
- `0x18005a8bc`

## import_xrefs

- `ntdll!RtlReAllocateHeap` at `0x180056c3f`
- `ntdll!RtlReAllocateHeap` at `0x180056c3f`
- `ntdll!RtlAllocateHeap` at `0x180056c1f`
- `ntdll!RtlAllocateHeap` at `0x180056c1f`

## string_xrefs

- `0x180056cb8`: `FaddpWriteFrameworkToStream`
- `0x180056cab`: `RtlMemoryStream failed to write ProgramUsesPrivateCopy [%x]`
- `0x180056b44`: `RtlMemoryStream failed to write Name [%x]`
- `0x180056b98`: `RtlMemoryStream failed to write Version [%x]`
- `0x180056bc2`: `RtlMemoryStream failed to write VersionUsed [%x]`
- `0x180056b6e`: `RtlMemoryStream failed to write Publisher [%x]`

## pseudocode

```c
__int64 __fastcall FaddpWriteFrameworkToStream(struct _FADD_FRAMEWORK *a1, struct RtlMemoryStream *this)
{
  int v4; // ebx
  const char *v5; // r9
  int v6; // r8d
  unsigned __int64 *v7; // rsi
  unsigned __int64 v8; // rax
  unsigned __int64 v9; // rcx
  __int64 v10; // rbx
  unsigned __int64 v11; // rax
  void *v12; // r8
  void *v13; // rcx
  SIZE_T v14; // rbx
  PVOID v15; // rax
  PVOID Heap; // rbp
  _QWORD *v17; // rcx
  unsigned __int64 v18; // rcx
  unsigned __int64 v19; // rax

  v4 = RtlMemoryStream::WriteString(this, (const unsigned __int16 *)a1, &dword_180142A84);
  if ( v4 < 0 )
  {
    v5 = "RtlMemoryStream failed to write Name [%x]";
    v6 = 2127;
LABEL_28:
    AslLogCallPrintf(1, (unsigned int)"FaddpWriteFrameworkToStream", v6, (_DWORD)v5);
    return (unsigned int)v4;
  }
  v4 = RtlMemoryStream::WriteString(this, (const unsigned __int16 *)a1 + 260, &dword_180142A84);
  if ( v4 < 0 )
  {
    v5 = "RtlMemoryStream failed to write Publisher [%x]";
    v6 = 2133;
    goto LABEL_28;
  }
  v4 = RtlMemoryStream::WriteString(this, (const unsigned __int16 *)a1 + 520, &dword_180142A84);
  if ( v4 < 0 )
  {
    v5 = "RtlMemoryStream failed to write Version [%x]";
    v6 = 2139;
    goto LABEL_28;
  }
  v4 = RtlMemoryStream::WriteString(this, (const unsigned __int16 *)a1 + 780, &dword_180142A84);
  if ( v4 < 0 )
  {
    v5 = "RtlMemoryStream failed to write VersionUsed [%x]";
    v6 = 2145;
    goto LABEL_28;
  }
  v7 = (unsigned __int64 *)((char *)this + 32);
  v8 = *((_QWORD *)this + 4);
  v9 = v8 + 4;
  if ( v8 + 4 < v8 )
  {
    v4 = -1073741811;
    goto LABEL_27;
  }
  if ( v9 <= *((_QWORD *)this + 2) )
  {
    v17 = (_QWORD *)((char *)this + 32);
  }
  else
  {
    v10 = *((_QWORD *)this + 3) - 1LL;
    v11 = v10 + v9;
    if ( v10 + v9 < v9 )
    {
LABEL_12:
      v4 = -1073741675;
LABEL_27:
      v5 = "RtlMemoryStream failed to write ProgramUsesPrivateCopy [%x]";
      v6 = 2151;
      goto LABEL_28;
    }
    v12 = (void *)*((_QWORD *)this + 5);
    v13 = *(void **)this;
    v14 = v11 & ~v10;
    if ( v12 )
    {
      Heap = RtlReAllocateHeap(v13, 0, v12, v14);
    }
    else
    {
      v15 = RtlAllocateHeap(v13, 0, v14);
      Heap = v15;
      if ( v15 )
        memset_0(v15, 0, v14);
    }
    if ( !Heap )
    {
      v4 = -1073741801;
      goto LABEL_27;
    }
    *((_QWORD *)this + 5) = Heap;
    v17 = (_QWORD *)((char *)this + 32);
    *((_QWORD *)this + 2) = v14;
  }
  *(_DWORD *)(*((_QWORD *)this + 5) + *v17) = *((_DWORD *)a1 + 520);
  v18 = *v7 + 4;
  if ( v18 < *v7 )
  {
    *v7 = -1;
    goto LABEL_12;
  }
  *v7 = v18;
  v19 = *((_QWORD *)this + 1);
  if ( v19 <= v18 )
    v19 = v18;
  v4 = 0;
  *((_QWORD *)this + 1) = v19;
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180056b18  push    rbx
0x180056b1a  push    rbp
0x180056b1b  push    rsi
0x180056b1c  push    rdi
0x180056b1d  push    r14
0x180056b1f  sub     rsp, 30h
0x180056b23  mov     rdi, rdx
0x180056b26  lea     rsi, dword_180142A84
0x180056b2d  mov     rdx, rcx; unsigned __int16 *
0x180056b30  mov     r14, rcx
0x180056b33  mov     r8, rsi; unsigned __int16 *
0x180056b36  mov     rcx, rdi; this
0x180056b39  call    ?WriteString@RtlMemoryStream@@QEAAJPEBG0@Z; RtlMemoryStream::WriteString(ushort const *,ushort const *)
0x180056b3e  mov     ebx, eax
0x180056b40  test    eax, eax
0x180056b42  jns     short loc_180056B56
0x180056b44  lea     r9, aRtlmemorystrea_5; "RtlMemoryStream failed to write Name [%"...
0x180056b4b  mov     r8d, 84Fh
0x180056b51  jmp     loc_180056CB8
0x180056b56  lea     rdx, [r14+208h]; unsigned __int16 *
0x180056b5d  mov     r8, rsi; unsigned __int16 *
0x180056b60  mov     rcx, rdi; this
0x180056b63  call    ?WriteString@RtlMemoryStream@@QEAAJPEBG0@Z; RtlMemoryStream::WriteString(ushort const *,ushort const *)
0x180056b68  mov     ebx, eax
0x180056b6a  test    eax, eax
0x180056b6c  jns     short loc_180056B80
0x180056b6e  lea     r9, aRtlmemorystrea_4; "RtlMemoryStream failed to write Publish"...
0x180056b75  mov     r8d, 855h
0x180056b7b  jmp     loc_180056CB8
0x180056b80  lea     rdx, [r14+410h]; unsigned __int16 *
0x180056b87  mov     r8, rsi; unsigned __int16 *
0x180056b8a  mov     rcx, rdi; this
0x180056b8d  call    ?WriteString@RtlMemoryStream@@QEAAJPEBG0@Z; RtlMemoryStream::WriteString(ushort const *,ushort const *)
0x180056b92  mov     ebx, eax
0x180056b94  test    eax, eax
0x180056b96  jns     short loc_180056BAA
0x180056b98  lea     r9, aRtlmemorystrea_2; "RtlMemoryStream failed to write Version"...
0x180056b9f  mov     r8d, 85Bh
0x180056ba5  jmp     loc_180056CB8
0x180056baa  lea     rdx, [r14+618h]; unsigned __int16 *
0x180056bb1  mov     r8, rsi; unsigned __int16 *
0x180056bb4  mov     rcx, rdi; this
0x180056bb7  call    ?WriteString@RtlMemoryStream@@QEAAJPEBG0@Z; RtlMemoryStream::WriteString(ushort const *,ushort const *)
0x180056bbc  mov     ebx, eax
0x180056bbe  test    eax, eax
0x180056bc0  jns     short loc_180056BD4
0x180056bc2  lea     r9, aRtlmemorystrea_7; "RtlMemoryStream failed to write Version"...
0x180056bc9  mov     r8d, 861h
0x180056bcf  jmp     loc_180056CB8
0x180056bd4  lea     rsi, [rdi+20h]
0x180056bd8  mov     rax, [rsi]
0x180056bdb  lea     rcx, [rax+4]
0x180056bdf  cmp     rcx, rax
0x180056be2  jb      loc_180056CA4
0x180056be8  cmp     rcx, [rdi+10h]
0x180056bec  jbe     short loc_180056C62
0x180056bee  mov     rbx, [rdi+18h]
0x180056bf2  dec     rbx
0x180056bf5  lea     rax, [rbx+rcx]
0x180056bf9  cmp     rax, rcx
0x180056bfc  jnb     short loc_180056C08
0x180056bfe  mov     ebx, 0C0000095h
0x180056c03  jmp     loc_180056CA9
0x180056c08  mov     r8, [rdi+28h]; Ptr
0x180056c0c  not     rbx
0x180056c0f  mov     rcx, [rdi]; Heap
0x180056c12  and     rbx, rax
0x180056c15  xor     edx, edx; Flags
0x180056c17  test    r8, r8
0x180056c1a  jnz     short loc_180056C3C
0x180056c1c  mov     r8, rbx; Size
0x180056c1f  call    cs:__imp_RtlAllocateHeap
0x180056c25  mov     rbp, rax
0x180056c28  test    rax, rax
0x180056c2b  jz      short loc_180056C48
0x180056c2d  mov     r8, rbx; Size
0x180056c30  xor     edx, edx; Val
0x180056c32  mov     rcx, rax; void *
0x180056c35  call    memset_0
0x180056c3a  jmp     short loc_180056C48
0x180056c3c  mov     r9, rbx; Size
0x180056c3f  call    cs:__imp_RtlReAllocateHeap
0x180056c45  mov     rbp, rax
0x180056c48  test    rbp, rbp
0x180056c4b  jnz     short loc_180056C54
0x180056c4d  mov     ebx, 0C0000017h
0x180056c52  jmp     short loc_180056CA9
0x180056c54  mov     [rdi+28h], rbp
0x180056c58  lea     rcx, [rdi+20h]
0x180056c5c  mov     [rdi+10h], rbx
0x180056c60  jmp     short loc_180056C65
0x180056c62  mov     rcx, rsi
0x180056c65  mov     rcx, [rcx]
0x180056c68  mov     eax, [r14+820h]
0x180056c6f  mov     rdx, [rdi+28h]
0x180056c73  mov     [rdx+rcx], eax
0x180056c76  mov     rax, [rsi]
0x180056c79  lea     rcx, [rax+4]
0x180056c7d  cmp     rcx, rax
0x180056c80  jb      short loc_180056C98
0x180056c82  mov     [rsi], rcx
0x180056c85  mov     rax, [rdi+8]
0x180056c89  cmp     rax, rcx
0x180056c8c  cmovbe  rax, rcx
0x180056c90  xor     ebx, ebx
0x180056c92  mov     [rdi+8], rax
0x180056c96  jmp     short loc_180056CCD
0x180056c98  mov     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x180056c9f  jmp     loc_180056BFE
0x180056ca4  mov     ebx, 0C000000Dh
0x180056ca9  mov     eax, ebx
0x180056cab  lea     r9, aRtlmemorystrea_0; "RtlMemoryStream failed to write Program"...
0x180056cb2  mov     r8d, 867h
0x180056cb8  lea     rdx, aFaddpwritefram; "FaddpWriteFrameworkToStream"
0x180056cbf  mov     [rsp+58h+var_38], eax
0x180056cc3  mov     ecx, 1
0x180056cc8  call    AslLogCallPrintf
0x180056ccd  mov     eax, ebx
0x180056ccf  add     rsp, 30h
0x180056cd3  pop     r14
0x180056cd5  pop     rdi
0x180056cd6  pop     rsi
0x180056cd7  pop     rbp
0x180056cd8  pop     rbx
0x180056cd9  retn
```
