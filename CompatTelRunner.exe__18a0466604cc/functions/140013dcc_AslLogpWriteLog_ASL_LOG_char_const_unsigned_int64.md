# AslLogpWriteLog(_ASL_LOG *,char const *,unsigned __int64)

- ea: `0x140013dcc`
- end: `0x140013fca`
- name: `?AslLogpWriteLog@@YAXPEAU_ASL_LOG@@PEBD_K@Z`
- size: `510`
- prototype: `void __fastcall(struct _ASL_LOG *, const char *, size_t)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callers

- `0x140014870`

## callees

- `0x1400026c0`
- `0x140013b10`
- `0x140013d08`
- `0x140013dcc`
- `0x1400a7308`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x140013f00`
- `ntdll!RtlLeaveCriticalSection` at `0x140013fb3`
- `ntdll!RtlLeaveCriticalSection` at `0x140013f00`
- `ntdll!RtlLeaveCriticalSection` at `0x140013fb3`
- `ntdll!RtlEnterCriticalSection` at `0x140013dfb`
- `ntdll!RtlEnterCriticalSection` at `0x140013f7d`
- `ntdll!RtlEnterCriticalSection` at `0x140013dfb`
- `ntdll!RtlEnterCriticalSection` at `0x140013f7d`
- `ntdll!RtlReAllocateHeap` at `0x140013ea6`
- `ntdll!RtlReAllocateHeap` at `0x140013ea6`
- `ntdll!RtlAllocateHeap` at `0x140013e86`
- `ntdll!RtlAllocateHeap` at `0x140013e86`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x140013f2f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x140013f2f`
- `api-ms-win-core-processenvironment-l1-1-0!GetStdHandle` at `0x140013f46`
- `api-ms-win-core-processenvironment-l1-1-0!GetStdHandle` at `0x140013f46`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140013f6b`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140013f6b`

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
0x140013dcc  push    rbx
0x140013dce  push    rbp
0x140013dcf  push    rsi
0x140013dd0  push    rdi
0x140013dd1  push    r12
0x140013dd3  push    r13
0x140013dd5  push    r14
0x140013dd7  push    r15
0x140013dd9  sub     rsp, 38h
0x140013ddd  mov     rax, [rcx]
0x140013de0  mov     rdi, rcx
0x140013de3  add     rcx, 68h ; 'h'; CriticalSection
0x140013de7  mov     r13, r8
0x140013dea  mov     r12, rdx
0x140013ded  mov     rbp, rdx
0x140013df0  mov     rsi, r8
0x140013df3  mov     qword ptr [rax+40h], 0
0x140013dfb  call    cs:__imp_RtlEnterCriticalSection
0x140013e01  mov     rax, [rdi]
0x140013e04  lea     rbx, [rdi+90h]
0x140013e0b  cmp     dword ptr [rax+4Ch], 0
0x140013e0f  jz      short loc_140013E3B
0x140013e11  mov     ecx, [rax+4Ch]
0x140013e14  cmp     rsi, rcx
0x140013e17  jbe     short loc_140013E21
0x140013e19  sub     rbp, rcx
0x140013e1c  add     rbp, rsi
0x140013e1f  mov     esi, ecx
0x140013e21  mov     edx, [rbx+8]
0x140013e24  lea     rax, [rdx+rsi]
0x140013e28  cmp     rax, rcx
0x140013e2b  jbe     short loc_140013E3B
0x140013e2d  sub     rdx, rcx
0x140013e30  mov     rcx, rbx; struct _RTL_MEMORY_STREAM *
0x140013e33  add     rdx, rsi; unsigned __int64
0x140013e36  call    ?AslLogpRollStream@@YAXPEAU_RTL_MEMORY_STREAM@@_K@Z; AslLogpRollStream(_RTL_MEMORY_STREAM *,unsigned __int64)
0x140013e3b  test    rsi, rsi
0x140013e3e  jz      loc_140013EF9
0x140013e44  mov     rax, [rbx+20h]
0x140013e48  lea     rcx, [rax+rsi]
0x140013e4c  cmp     rcx, rax
0x140013e4f  jb      loc_140013EF9
0x140013e55  cmp     rcx, [rbx+10h]
0x140013e59  jbe     short loc_140013EBC
0x140013e5b  mov     r14, [rbx+18h]
0x140013e5f  dec     r14
0x140013e62  lea     rax, [r14+rcx]
0x140013e66  cmp     rax, rcx
0x140013e69  jb      loc_140013EF9
0x140013e6f  mov     r8, [rbx+28h]; Ptr
0x140013e73  not     r14
0x140013e76  mov     rcx, [rbx]; Heap
0x140013e79  and     r14, rax
0x140013e7c  xor     edx, edx; Flags
0x140013e7e  test    r8, r8
0x140013e81  jnz     short loc_140013EA3
0x140013e83  mov     r8, r14; Size
0x140013e86  call    cs:__imp_RtlAllocateHeap
0x140013e8c  mov     r15, rax
0x140013e8f  test    rax, rax
0x140013e92  jz      short loc_140013EAF
0x140013e94  mov     r8, r14; Size
0x140013e97  xor     edx, edx; Val
0x140013e99  mov     rcx, rax; void *
0x140013e9c  call    memset_0
0x140013ea1  jmp     short loc_140013EAF
0x140013ea3  mov     r9, r14; Size
0x140013ea6  call    cs:__imp_RtlReAllocateHeap
0x140013eac  mov     r15, rax
0x140013eaf  test    r15, r15
0x140013eb2  jz      short loc_140013EF9
0x140013eb4  mov     [rbx+28h], r15
0x140013eb8  mov     [rbx+10h], r14
0x140013ebc  mov     rcx, [rbx+28h]
0x140013ec0  mov     r8, rsi; Size
0x140013ec3  add     rcx, [rbx+20h]; void *
0x140013ec7  mov     rdx, rbp; Src
0x140013eca  call    memcpy_0
0x140013ecf  mov     rax, [rbx+20h]
0x140013ed3  lea     rcx, [rax+rsi]
0x140013ed7  cmp     rcx, rax
0x140013eda  jb      short loc_140013EF1
0x140013edc  mov     [rbx+20h], rcx
0x140013ee0  mov     rax, [rbx+8]
0x140013ee4  cmp     rax, rcx
0x140013ee7  cmovbe  rax, rcx
0x140013eeb  mov     [rbx+8], rax
0x140013eef  jmp     short loc_140013EF9
0x140013ef1  mov     qword ptr [rbx+20h], 0FFFFFFFFFFFFFFFFh
0x140013ef9  lea     rbx, [rdi+68h]
0x140013efd  mov     rcx, rbx; CriticalSection
0x140013f00  call    cs:__imp_RtlLeaveCriticalSection
0x140013f06  mov     rax, [rdi+0B8h]
0x140013f0d  mov     bpl, 1
0x140013f10  mov     rcx, [rdi]
0x140013f13  mov     [rcx+40h], rax
0x140013f17  mov     eax, [rdi+98h]
0x140013f1d  mov     rcx, [rdi]
0x140013f20  mov     [rcx+48h], eax
0x140013f23  mov     rax, [rdi]
0x140013f26  test    [rax+50h], bpl
0x140013f2a  jz      short loc_140013F35
0x140013f2c  mov     rcx, r12; lpOutputString
0x140013f2f  call    cs:__imp_OutputDebugStringA
0x140013f35  mov     rax, [rdi]
0x140013f38  test    dword ptr [rax+50h], 100h
0x140013f3f  jz      short loc_140013F71
0x140013f41  mov     ecx, 0FFFFFFF5h; nStdHandle
0x140013f46  call    cs:__imp_GetStdHandle
0x140013f4c  lea     rcx, [rax-1]
0x140013f50  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x140013f54  ja      short loc_140013F71
0x140013f56  mov     r8d, esi; nNumberOfBytesToWrite
0x140013f59  mov     [rsp+78h+lpOverlapped], 0; lpOverlapped
0x140013f62  xor     r9d, r9d; lpNumberOfBytesWritten
0x140013f65  mov     rdx, r12; lpBuffer
0x140013f68  mov     rcx, rax; hFile
0x140013f6b  call    cs:__imp_WriteFile
0x140013f71  mov     rax, [rdi]
0x140013f74  test    byte ptr [rax+50h], 4
0x140013f78  jz      short loc_140013FB9
0x140013f7a  mov     rcx, rbx; CriticalSection
0x140013f7d  call    cs:__imp_RtlEnterCriticalSection
0x140013f83  mov     rax, [rdi]
0x140013f86  lea     rcx, [rdi+0C0h]; unsigned __int16 *
0x140013f8d  mov     r8, r13; unsigned __int64
0x140013f90  mov     rdx, r12; char *
0x140013f93  mov     r9d, [rax+50h]
0x140013f97  mov     eax, r9d
0x140013f9a  shr     eax, 5
0x140013f9d  shr     r9d, 3
0x140013fa1  and     al, bpl
0x140013fa4  and     r9b, bpl; unsigned __int8
0x140013fa7  mov     byte ptr [rsp+78h+lpOverlapped], al; unsigned __int8
0x140013fab  call    ?AslLogpAppendLog@@YAJPEBGPEBD_KEE@Z; AslLogpAppendLog(ushort const *,char const *,unsigned __int64,uchar,uchar)
0x140013fb0  mov     rcx, rbx; CriticalSection
0x140013fb3  call    cs:__imp_RtlLeaveCriticalSection
0x140013fb9  add     rsp, 38h
0x140013fbd  pop     r15
0x140013fbf  pop     r14
0x140013fc1  pop     r13
0x140013fc3  pop     r12
0x140013fc5  pop     rdi
0x140013fc6  pop     rsi
0x140013fc7  pop     rbp
0x140013fc8  pop     rbx
0x140013fc9  retn
```
