# AslLogpWriteLog(_ASL_LOG *,char const *,unsigned __int64)

- ea: `0x1800695f4`
- end: `0x1800697f2`
- name: `?AslLogpWriteLog@@YAXPEAU_ASL_LOG@@PEBD_K@Z`
- size: `510`
- prototype: `void(struct _ASL_LOG *, const char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callers

- `0x180028b98`

## callees

- `0x18005a8bc`
- `0x1800693f8`
- `0x180069534`
- `0x1800695f4`
- `0x180125490`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180069728`
- `ntdll!RtlLeaveCriticalSection` at `0x1800697db`
- `ntdll!RtlLeaveCriticalSection` at `0x180069728`
- `ntdll!RtlLeaveCriticalSection` at `0x1800697db`
- `ntdll!RtlEnterCriticalSection` at `0x180069623`
- `ntdll!RtlEnterCriticalSection` at `0x1800697a5`
- `ntdll!RtlEnterCriticalSection` at `0x180069623`
- `ntdll!RtlEnterCriticalSection` at `0x1800697a5`
- `ntdll!RtlReAllocateHeap` at `0x1800696ce`
- `ntdll!RtlReAllocateHeap` at `0x1800696ce`
- `ntdll!RtlAllocateHeap` at `0x1800696ae`
- `ntdll!RtlAllocateHeap` at `0x1800696ae`
- `KERNEL32!GetStdHandle` at `0x18006976e`
- `KERNEL32!GetStdHandle` at `0x18006976e`
- `KERNEL32!WriteFile` at `0x180069793`
- `KERNEL32!WriteFile` at `0x180069793`
- `KERNEL32!OutputDebugStringA` at `0x180069757`
- `KERNEL32!OutputDebugStringA` at `0x180069757`

## pseudocode

```c
void __fastcall AslLogpWriteLog(struct _ASL_LOG *a1, const char *a2, size_t a3)
{
  DWORD v4; // r13d
  const char *v6; // rbp
  size_t v7; // rsi
  size_t v8; // rcx
  __int64 v9; // rdx
  size_t v10; // rax
  unsigned __int64 v11; // rcx
  __int64 v12; // r14
  unsigned __int64 v13; // rax
  void *v14; // r8
  void *v15; // rcx
  SIZE_T v16; // r14
  PVOID v17; // rax
  PVOID Heap; // r15
  size_t v19; // rax
  size_t v20; // rcx
  size_t v21; // rax
  char *StdHandle; // rax

  v4 = a3;
  v6 = a2;
  v7 = a3;
  *(_QWORD *)(*(_QWORD *)a1 + 64LL) = 0;
  RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)((char *)a1 + 104));
  if ( *(_DWORD *)(*(_QWORD *)a1 + 76LL) )
  {
    v8 = *(unsigned int *)(*(_QWORD *)a1 + 76LL);
    if ( v7 > v8 )
    {
      v6 = &v6[v7 - v8];
      v7 = (unsigned int)v8;
    }
    v9 = *((unsigned int *)a1 + 38);
    if ( v9 + v7 > v8 )
      AslLogpRollStream((struct _RTL_MEMORY_STREAM *)((char *)a1 + 144), v7 + v9 - v8);
  }
  if ( v7 )
  {
    v10 = *((_QWORD *)a1 + 22);
    v11 = v10 + v7;
    if ( v10 + v7 >= v10 )
    {
      if ( v11 <= *((_QWORD *)a1 + 20) )
        goto LABEL_16;
      v12 = *((_QWORD *)a1 + 21) - 1LL;
      v13 = v12 + v11;
      if ( v12 + v11 >= v11 )
      {
        v14 = (void *)*((_QWORD *)a1 + 23);
        v15 = (void *)*((_QWORD *)a1 + 18);
        v16 = v13 & ~v12;
        if ( v14 )
        {
          Heap = RtlReAllocateHeap(v15, 0, v14, v16);
        }
        else
        {
          v17 = RtlAllocateHeap(v15, 0, v16);
          Heap = v17;
          if ( v17 )
            memset_0(v17, 0, v16);
        }
        if ( Heap )
        {
          *((_QWORD *)a1 + 23) = Heap;
          *((_QWORD *)a1 + 20) = v16;
LABEL_16:
          memcpy_0((void *)(*((_QWORD *)a1 + 22) + *((_QWORD *)a1 + 23)), v6, v7);
          v19 = *((_QWORD *)a1 + 22);
          v20 = v19 + v7;
          if ( v19 + v7 < v19 )
          {
            *((_QWORD *)a1 + 22) = -1;
          }
          else
          {
            *((_QWORD *)a1 + 22) = v20;
            v21 = *((_QWORD *)a1 + 19);
            if ( v21 <= v20 )
              v21 = v20;
            *((_QWORD *)a1 + 19) = v21;
          }
        }
      }
    }
  }
  RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)((char *)a1 + 104));
  *(_QWORD *)(*(_QWORD *)a1 + 64LL) = *((_QWORD *)a1 + 23);
  *(_DWORD *)(*(_QWORD *)a1 + 72LL) = *((_DWORD *)a1 + 38);
  if ( (*(_BYTE *)(*(_QWORD *)a1 + 80LL) & 1) != 0 )
    OutputDebugStringA(a2);
  if ( (*(_DWORD *)(*(_QWORD *)a1 + 80LL) & 0x100) != 0 )
  {
    StdHandle = (char *)GetStdHandle(0xFFFFFFF5);
    if ( (unsigned __int64)(StdHandle - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      WriteFile(StdHandle, a2, v7, 0, 0);
  }
  if ( (*(_BYTE *)(*(_QWORD *)a1 + 80LL) & 4) != 0 )
  {
    RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)((char *)a1 + 104));
    AslLogpAppendLog(
      (const unsigned __int16 *)a1 + 96,
      a2,
      v4,
      (*(_DWORD *)(*(_QWORD *)a1 + 80LL) & 8) != 0,
      (*(_DWORD *)(*(_QWORD *)a1 + 80LL) & 0x20) != 0);
    RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)((char *)a1 + 104));
  }
}

```

## disassembly

```asm
0x1800695f4  push    rbx
0x1800695f6  push    rbp
0x1800695f7  push    rsi
0x1800695f8  push    rdi
0x1800695f9  push    r12
0x1800695fb  push    r13
0x1800695fd  push    r14
0x1800695ff  push    r15
0x180069601  sub     rsp, 38h
0x180069605  mov     rax, [rcx]
0x180069608  mov     rdi, rcx
0x18006960b  add     rcx, 68h ; 'h'; CriticalSection
0x18006960f  mov     r13, r8
0x180069612  mov     r12, rdx
0x180069615  mov     rbp, rdx
0x180069618  mov     rsi, r8
0x18006961b  mov     qword ptr [rax+40h], 0
0x180069623  call    cs:__imp_RtlEnterCriticalSection
0x180069629  mov     rax, [rdi]
0x18006962c  lea     rbx, [rdi+90h]
0x180069633  cmp     dword ptr [rax+4Ch], 0
0x180069637  jz      short loc_180069663
0x180069639  mov     ecx, [rax+4Ch]
0x18006963c  cmp     rsi, rcx
0x18006963f  jbe     short loc_180069649
0x180069641  sub     rbp, rcx
0x180069644  add     rbp, rsi
0x180069647  mov     esi, ecx
0x180069649  mov     edx, [rbx+8]
0x18006964c  lea     rax, [rdx+rsi]
0x180069650  cmp     rax, rcx
0x180069653  jbe     short loc_180069663
0x180069655  sub     rdx, rcx
0x180069658  mov     rcx, rbx; struct _RTL_MEMORY_STREAM *
0x18006965b  add     rdx, rsi; unsigned __int64
0x18006965e  call    ?AslLogpRollStream@@YAXPEAU_RTL_MEMORY_STREAM@@_K@Z; AslLogpRollStream(_RTL_MEMORY_STREAM *,unsigned __int64)
0x180069663  test    rsi, rsi
0x180069666  jz      loc_180069721
0x18006966c  mov     rax, [rbx+20h]
0x180069670  lea     rcx, [rax+rsi]
0x180069674  cmp     rcx, rax
0x180069677  jb      loc_180069721
0x18006967d  cmp     rcx, [rbx+10h]
0x180069681  jbe     short loc_1800696E4
0x180069683  mov     r14, [rbx+18h]
0x180069687  dec     r14
0x18006968a  lea     rax, [r14+rcx]
0x18006968e  cmp     rax, rcx
0x180069691  jb      loc_180069721
0x180069697  mov     r8, [rbx+28h]; Ptr
0x18006969b  not     r14
0x18006969e  mov     rcx, [rbx]; Heap
0x1800696a1  and     r14, rax
0x1800696a4  xor     edx, edx; Flags
0x1800696a6  test    r8, r8
0x1800696a9  jnz     short loc_1800696CB
0x1800696ab  mov     r8, r14; Size
0x1800696ae  call    cs:__imp_RtlAllocateHeap
0x1800696b4  mov     r15, rax
0x1800696b7  test    rax, rax
0x1800696ba  jz      short loc_1800696D7
0x1800696bc  mov     r8, r14; Size
0x1800696bf  xor     edx, edx; Val
0x1800696c1  mov     rcx, rax; void *
0x1800696c4  call    memset_0
0x1800696c9  jmp     short loc_1800696D7
0x1800696cb  mov     r9, r14; Size
0x1800696ce  call    cs:__imp_RtlReAllocateHeap
0x1800696d4  mov     r15, rax
0x1800696d7  test    r15, r15
0x1800696da  jz      short loc_180069721
0x1800696dc  mov     [rbx+28h], r15
0x1800696e0  mov     [rbx+10h], r14
0x1800696e4  mov     rcx, [rbx+28h]
0x1800696e8  mov     r8, rsi; Size
0x1800696eb  add     rcx, [rbx+20h]; void *
0x1800696ef  mov     rdx, rbp; Src
0x1800696f2  call    memcpy_0
0x1800696f7  mov     rax, [rbx+20h]
0x1800696fb  lea     rcx, [rax+rsi]
0x1800696ff  cmp     rcx, rax
0x180069702  jb      short loc_180069719
0x180069704  mov     [rbx+20h], rcx
0x180069708  mov     rax, [rbx+8]
0x18006970c  cmp     rax, rcx
0x18006970f  cmovbe  rax, rcx
0x180069713  mov     [rbx+8], rax
0x180069717  jmp     short loc_180069721
0x180069719  mov     qword ptr [rbx+20h], 0FFFFFFFFFFFFFFFFh
0x180069721  lea     rbx, [rdi+68h]
0x180069725  mov     rcx, rbx; CriticalSection
0x180069728  call    cs:__imp_RtlLeaveCriticalSection
0x18006972e  mov     rax, [rdi+0B8h]
0x180069735  mov     bpl, 1
0x180069738  mov     rcx, [rdi]
0x18006973b  mov     [rcx+40h], rax
0x18006973f  mov     eax, [rdi+98h]
0x180069745  mov     rcx, [rdi]
0x180069748  mov     [rcx+48h], eax
0x18006974b  mov     rax, [rdi]
0x18006974e  test    [rax+50h], bpl
0x180069752  jz      short loc_18006975D
0x180069754  mov     rcx, r12; lpOutputString
0x180069757  call    cs:__imp_OutputDebugStringA
0x18006975d  mov     rax, [rdi]
0x180069760  test    dword ptr [rax+50h], 100h
0x180069767  jz      short loc_180069799
0x180069769  mov     ecx, 0FFFFFFF5h; nStdHandle
0x18006976e  call    cs:__imp_GetStdHandle
0x180069774  lea     rcx, [rax-1]
0x180069778  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18006977c  ja      short loc_180069799
0x18006977e  mov     r8d, esi; nNumberOfBytesToWrite
0x180069781  mov     [rsp+78h+lpOverlapped], 0; lpOverlapped
0x18006978a  xor     r9d, r9d; lpNumberOfBytesWritten
0x18006978d  mov     rdx, r12; lpBuffer
0x180069790  mov     rcx, rax; hFile
0x180069793  call    cs:__imp_WriteFile
0x180069799  mov     rax, [rdi]
0x18006979c  test    byte ptr [rax+50h], 4
0x1800697a0  jz      short loc_1800697E1
0x1800697a2  mov     rcx, rbx; CriticalSection
0x1800697a5  call    cs:__imp_RtlEnterCriticalSection
0x1800697ab  mov     rax, [rdi]
0x1800697ae  lea     rcx, [rdi+0C0h]; unsigned __int16 *
0x1800697b5  mov     r8, r13; unsigned __int64
0x1800697b8  mov     rdx, r12; char *
0x1800697bb  mov     r9d, [rax+50h]
0x1800697bf  mov     eax, r9d
0x1800697c2  shr     eax, 5
0x1800697c5  shr     r9d, 3
0x1800697c9  and     al, bpl
0x1800697cc  and     r9b, bpl; unsigned __int8
0x1800697cf  mov     byte ptr [rsp+78h+lpOverlapped], al; unsigned __int8
0x1800697d3  call    ?AslLogpAppendLog@@YAJPEBGPEBD_KEE@Z; AslLogpAppendLog(ushort const *,char const *,unsigned __int64,uchar,uchar)
0x1800697d8  mov     rcx, rbx; CriticalSection
0x1800697db  call    cs:__imp_RtlLeaveCriticalSection
0x1800697e1  add     rsp, 38h
0x1800697e5  pop     r15
0x1800697e7  pop     r14
0x1800697e9  pop     r13
0x1800697eb  pop     r12
0x1800697ed  pop     rdi
0x1800697ee  pop     rsi
0x1800697ef  pop     rbp
0x1800697f0  pop     rbx
0x1800697f1  retn
```
