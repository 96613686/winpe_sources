# AslLogpWriteLog(_ASL_LOG *,char const *,unsigned __int64)

- ea: `0x180045950`
- end: `0x180045b4e`
- name: `?AslLogpWriteLog@@YAXPEAU_ASL_LOG@@PEBD_K@Z`
- size: `510`
- prototype: `void __fastcall(struct _ASL_LOG *, const char *, size_t)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callers

- `0x1800471a0`

## callees

- `0x180005914`
- `0x180007122`
- `0x180045694`
- `0x18004588c`
- `0x180045950`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180045a0a`
- `ntdll!RtlAllocateHeap` at `0x180045a0a`
- `ntdll!RtlLeaveCriticalSection` at `0x180045a84`
- `ntdll!RtlLeaveCriticalSection` at `0x180045b37`
- `ntdll!RtlLeaveCriticalSection` at `0x180045a84`
- `ntdll!RtlLeaveCriticalSection` at `0x180045b37`
- `ntdll!RtlReAllocateHeap` at `0x180045a2a`
- `ntdll!RtlReAllocateHeap` at `0x180045a2a`
- `ntdll!RtlEnterCriticalSection` at `0x18004597f`
- `ntdll!RtlEnterCriticalSection` at `0x180045b01`
- `ntdll!RtlEnterCriticalSection` at `0x18004597f`
- `ntdll!RtlEnterCriticalSection` at `0x180045b01`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180045ab3`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180045ab3`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180045aef`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180045aef`
- `api-ms-win-core-processenvironment-l1-1-0!GetStdHandle` at `0x180045aca`
- `api-ms-win-core-processenvironment-l1-1-0!GetStdHandle` at `0x180045aca`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
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
0x180045950  push    rbx
0x180045952  push    rbp
0x180045953  push    rsi
0x180045954  push    rdi
0x180045955  push    r12
0x180045957  push    r13
0x180045959  push    r14
0x18004595b  push    r15
0x18004595d  sub     rsp, 38h
0x180045961  mov     rax, [rcx]
0x180045964  mov     rdi, rcx
0x180045967  add     rcx, 68h ; 'h'; CriticalSection
0x18004596b  mov     r13, r8
0x18004596e  mov     r12, rdx
0x180045971  mov     rbp, rdx
0x180045974  mov     rsi, r8
0x180045977  mov     qword ptr [rax+40h], 0
0x18004597f  call    cs:__imp_RtlEnterCriticalSection
0x180045985  mov     rax, [rdi]
0x180045988  lea     rbx, [rdi+90h]
0x18004598f  cmp     dword ptr [rax+4Ch], 0
0x180045993  jz      short loc_1800459BF
0x180045995  mov     ecx, [rax+4Ch]
0x180045998  cmp     rsi, rcx
0x18004599b  jbe     short loc_1800459A5
0x18004599d  sub     rbp, rcx
0x1800459a0  add     rbp, rsi
0x1800459a3  mov     esi, ecx
0x1800459a5  mov     edx, [rbx+8]
0x1800459a8  lea     rax, [rdx+rsi]
0x1800459ac  cmp     rax, rcx
0x1800459af  jbe     short loc_1800459BF
0x1800459b1  sub     rdx, rcx
0x1800459b4  mov     rcx, rbx; struct _RTL_MEMORY_STREAM *
0x1800459b7  add     rdx, rsi; unsigned __int64
0x1800459ba  call    ?AslLogpRollStream@@YAXPEAU_RTL_MEMORY_STREAM@@_K@Z; AslLogpRollStream(_RTL_MEMORY_STREAM *,unsigned __int64)
0x1800459bf  test    rsi, rsi
0x1800459c2  jz      loc_180045A7D
0x1800459c8  mov     rax, [rbx+20h]
0x1800459cc  lea     rcx, [rax+rsi]
0x1800459d0  cmp     rcx, rax
0x1800459d3  jb      loc_180045A7D
0x1800459d9  cmp     rcx, [rbx+10h]
0x1800459dd  jbe     short loc_180045A40
0x1800459df  mov     r14, [rbx+18h]
0x1800459e3  dec     r14
0x1800459e6  lea     rax, [r14+rcx]
0x1800459ea  cmp     rax, rcx
0x1800459ed  jb      loc_180045A7D
0x1800459f3  mov     r8, [rbx+28h]; Ptr
0x1800459f7  not     r14
0x1800459fa  mov     rcx, [rbx]; Heap
0x1800459fd  and     r14, rax
0x180045a00  xor     edx, edx; Flags
0x180045a02  test    r8, r8
0x180045a05  jnz     short loc_180045A27
0x180045a07  mov     r8, r14; Size
0x180045a0a  call    cs:__imp_RtlAllocateHeap
0x180045a10  mov     r15, rax
0x180045a13  test    rax, rax
0x180045a16  jz      short loc_180045A33
0x180045a18  mov     r8, r14; Size
0x180045a1b  xor     edx, edx; Val
0x180045a1d  mov     rcx, rax; void *
0x180045a20  call    memset_0
0x180045a25  jmp     short loc_180045A33
0x180045a27  mov     r9, r14; Size
0x180045a2a  call    cs:__imp_RtlReAllocateHeap
0x180045a30  mov     r15, rax
0x180045a33  test    r15, r15
0x180045a36  jz      short loc_180045A7D
0x180045a38  mov     [rbx+28h], r15
0x180045a3c  mov     [rbx+10h], r14
0x180045a40  mov     rcx, [rbx+28h]
0x180045a44  mov     r8, rsi; Size
0x180045a47  add     rcx, [rbx+20h]; void *
0x180045a4b  mov     rdx, rbp; Src
0x180045a4e  call    memcpy_0
0x180045a53  mov     rax, [rbx+20h]
0x180045a57  lea     rcx, [rax+rsi]
0x180045a5b  cmp     rcx, rax
0x180045a5e  jb      short loc_180045A75
0x180045a60  mov     [rbx+20h], rcx
0x180045a64  mov     rax, [rbx+8]
0x180045a68  cmp     rax, rcx
0x180045a6b  cmovbe  rax, rcx
0x180045a6f  mov     [rbx+8], rax
0x180045a73  jmp     short loc_180045A7D
0x180045a75  mov     qword ptr [rbx+20h], 0FFFFFFFFFFFFFFFFh
0x180045a7d  lea     rbx, [rdi+68h]
0x180045a81  mov     rcx, rbx; CriticalSection
0x180045a84  call    cs:__imp_RtlLeaveCriticalSection
0x180045a8a  mov     rax, [rdi+0B8h]
0x180045a91  mov     bpl, 1
0x180045a94  mov     rcx, [rdi]
0x180045a97  mov     [rcx+40h], rax
0x180045a9b  mov     eax, [rdi+98h]
0x180045aa1  mov     rcx, [rdi]
0x180045aa4  mov     [rcx+48h], eax
0x180045aa7  mov     rax, [rdi]
0x180045aaa  test    [rax+50h], bpl
0x180045aae  jz      short loc_180045AB9
0x180045ab0  mov     rcx, r12; lpOutputString
0x180045ab3  call    cs:__imp_OutputDebugStringA
0x180045ab9  mov     rax, [rdi]
0x180045abc  test    dword ptr [rax+50h], 100h
0x180045ac3  jz      short loc_180045AF5
0x180045ac5  mov     ecx, 0FFFFFFF5h; nStdHandle
0x180045aca  call    cs:__imp_GetStdHandle
0x180045ad0  lea     rcx, [rax-1]
0x180045ad4  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180045ad8  ja      short loc_180045AF5
0x180045ada  mov     r8d, esi; nNumberOfBytesToWrite
0x180045add  mov     [rsp+78h+lpOverlapped], 0; lpOverlapped
0x180045ae6  xor     r9d, r9d; lpNumberOfBytesWritten
0x180045ae9  mov     rdx, r12; lpBuffer
0x180045aec  mov     rcx, rax; hFile
0x180045aef  call    cs:__imp_WriteFile
0x180045af5  mov     rax, [rdi]
0x180045af8  test    byte ptr [rax+50h], 4
0x180045afc  jz      short loc_180045B3D
0x180045afe  mov     rcx, rbx; CriticalSection
0x180045b01  call    cs:__imp_RtlEnterCriticalSection
0x180045b07  mov     rax, [rdi]
0x180045b0a  lea     rcx, [rdi+0C0h]; unsigned __int16 *
0x180045b11  mov     r8, r13; unsigned __int64
0x180045b14  mov     rdx, r12; char *
0x180045b17  mov     r9d, [rax+50h]
0x180045b1b  mov     eax, r9d
0x180045b1e  shr     eax, 5
0x180045b21  shr     r9d, 3
0x180045b25  and     al, bpl
0x180045b28  and     r9b, bpl; unsigned __int8
0x180045b2b  mov     byte ptr [rsp+78h+lpOverlapped], al; unsigned __int8
0x180045b2f  call    ?AslLogpAppendLog@@YAJPEBGPEBD_KEE@Z; AslLogpAppendLog(ushort const *,char const *,unsigned __int64,uchar,uchar)
0x180045b34  mov     rcx, rbx; CriticalSection
0x180045b37  call    cs:__imp_RtlLeaveCriticalSection
0x180045b3d  add     rsp, 38h
0x180045b41  pop     r15
0x180045b43  pop     r14
0x180045b45  pop     r13
0x180045b47  pop     r12
0x180045b49  pop     rdi
0x180045b4a  pop     rsi
0x180045b4b  pop     rbp
0x180045b4c  pop     rbx
0x180045b4d  retn
```
