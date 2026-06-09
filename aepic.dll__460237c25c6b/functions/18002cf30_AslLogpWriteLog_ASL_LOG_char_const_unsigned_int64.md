# AslLogpWriteLog(_ASL_LOG *,char const *,unsigned __int64)

- ea: `0x18002cf30`
- end: `0x18002d12e`
- name: `?AslLogpWriteLog@@YAXPEAU_ASL_LOG@@PEBD_K@Z`
- size: `510`
- prototype: `void(struct _ASL_LOG *, const char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callers

- `0x18002db68`

## callees

- `0x180006920`
- `0x180006938`
- `0x18002cc48`
- `0x18002ce70`
- `0x18002cf30`

## import_xrefs

- `ntdll!RtlReAllocateHeap` at `0x18002d00a`
- `ntdll!RtlReAllocateHeap` at `0x18002d00a`
- `ntdll!RtlEnterCriticalSection` at `0x18002cf5f`
- `ntdll!RtlEnterCriticalSection` at `0x18002d0e1`
- `ntdll!RtlEnterCriticalSection` at `0x18002cf5f`
- `ntdll!RtlEnterCriticalSection` at `0x18002d0e1`
- `ntdll!RtlAllocateHeap` at `0x18002cfea`
- `ntdll!RtlAllocateHeap` at `0x18002cfea`
- `ntdll!RtlLeaveCriticalSection` at `0x18002d064`
- `ntdll!RtlLeaveCriticalSection` at `0x18002d117`
- `ntdll!RtlLeaveCriticalSection` at `0x18002d064`
- `ntdll!RtlLeaveCriticalSection` at `0x18002d117`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18002d093`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18002d093`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002d0cf`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002d0cf`
- `api-ms-win-core-processenvironment-l1-1-0!GetStdHandle` at `0x18002d0aa`
- `api-ms-win-core-processenvironment-l1-1-0!GetStdHandle` at `0x18002d0aa`

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
0x18002cf30  push    rbx
0x18002cf32  push    rbp
0x18002cf33  push    rsi
0x18002cf34  push    rdi
0x18002cf35  push    r12
0x18002cf37  push    r13
0x18002cf39  push    r14
0x18002cf3b  push    r15
0x18002cf3d  sub     rsp, 38h
0x18002cf41  mov     rax, [rcx]
0x18002cf44  mov     rdi, rcx
0x18002cf47  add     rcx, 68h ; 'h'; CriticalSection
0x18002cf4b  mov     r13, r8
0x18002cf4e  mov     r12, rdx
0x18002cf51  mov     rbp, rdx
0x18002cf54  mov     rsi, r8
0x18002cf57  mov     qword ptr [rax+40h], 0
0x18002cf5f  call    cs:__imp_RtlEnterCriticalSection
0x18002cf65  mov     rax, [rdi]
0x18002cf68  lea     rbx, [rdi+90h]
0x18002cf6f  cmp     dword ptr [rax+4Ch], 0
0x18002cf73  jz      short loc_18002CF9F
0x18002cf75  mov     ecx, [rax+4Ch]
0x18002cf78  cmp     rsi, rcx
0x18002cf7b  jbe     short loc_18002CF85
0x18002cf7d  sub     rbp, rcx
0x18002cf80  add     rbp, rsi
0x18002cf83  mov     esi, ecx
0x18002cf85  mov     edx, [rbx+8]
0x18002cf88  lea     rax, [rdx+rsi]
0x18002cf8c  cmp     rax, rcx
0x18002cf8f  jbe     short loc_18002CF9F
0x18002cf91  sub     rdx, rcx
0x18002cf94  mov     rcx, rbx; struct _RTL_MEMORY_STREAM *
0x18002cf97  add     rdx, rsi; unsigned __int64
0x18002cf9a  call    ?AslLogpRollStream@@YAXPEAU_RTL_MEMORY_STREAM@@_K@Z; AslLogpRollStream(_RTL_MEMORY_STREAM *,unsigned __int64)
0x18002cf9f  test    rsi, rsi
0x18002cfa2  jz      loc_18002D05D
0x18002cfa8  mov     rax, [rbx+20h]
0x18002cfac  lea     rcx, [rax+rsi]
0x18002cfb0  cmp     rcx, rax
0x18002cfb3  jb      loc_18002D05D
0x18002cfb9  cmp     rcx, [rbx+10h]
0x18002cfbd  jbe     short loc_18002D020
0x18002cfbf  mov     r14, [rbx+18h]
0x18002cfc3  dec     r14
0x18002cfc6  lea     rax, [r14+rcx]
0x18002cfca  cmp     rax, rcx
0x18002cfcd  jb      loc_18002D05D
0x18002cfd3  mov     r8, [rbx+28h]; Ptr
0x18002cfd7  not     r14
0x18002cfda  mov     rcx, [rbx]; Heap
0x18002cfdd  and     r14, rax
0x18002cfe0  xor     edx, edx; Flags
0x18002cfe2  test    r8, r8
0x18002cfe5  jnz     short loc_18002D007
0x18002cfe7  mov     r8, r14; Size
0x18002cfea  call    cs:__imp_RtlAllocateHeap
0x18002cff0  mov     r15, rax
0x18002cff3  test    rax, rax
0x18002cff6  jz      short loc_18002D013
0x18002cff8  mov     r8, r14; Size
0x18002cffb  xor     edx, edx; Val
0x18002cffd  mov     rcx, rax; void *
0x18002d000  call    memset_0
0x18002d005  jmp     short loc_18002D013
0x18002d007  mov     r9, r14; Size
0x18002d00a  call    cs:__imp_RtlReAllocateHeap
0x18002d010  mov     r15, rax
0x18002d013  test    r15, r15
0x18002d016  jz      short loc_18002D05D
0x18002d018  mov     [rbx+28h], r15
0x18002d01c  mov     [rbx+10h], r14
0x18002d020  mov     rcx, [rbx+28h]
0x18002d024  mov     r8, rsi; Size
0x18002d027  add     rcx, [rbx+20h]; void *
0x18002d02b  mov     rdx, rbp; Src
0x18002d02e  call    memcpy_0
0x18002d033  mov     rax, [rbx+20h]
0x18002d037  lea     rcx, [rax+rsi]
0x18002d03b  cmp     rcx, rax
0x18002d03e  jb      short loc_18002D055
0x18002d040  mov     [rbx+20h], rcx
0x18002d044  mov     rax, [rbx+8]
0x18002d048  cmp     rax, rcx
0x18002d04b  cmovbe  rax, rcx
0x18002d04f  mov     [rbx+8], rax
0x18002d053  jmp     short loc_18002D05D
0x18002d055  mov     qword ptr [rbx+20h], 0FFFFFFFFFFFFFFFFh
0x18002d05d  lea     rbx, [rdi+68h]
0x18002d061  mov     rcx, rbx; CriticalSection
0x18002d064  call    cs:__imp_RtlLeaveCriticalSection
0x18002d06a  mov     rax, [rdi+0B8h]
0x18002d071  mov     bpl, 1
0x18002d074  mov     rcx, [rdi]
0x18002d077  mov     [rcx+40h], rax
0x18002d07b  mov     eax, [rdi+98h]
0x18002d081  mov     rcx, [rdi]
0x18002d084  mov     [rcx+48h], eax
0x18002d087  mov     rax, [rdi]
0x18002d08a  test    [rax+50h], bpl
0x18002d08e  jz      short loc_18002D099
0x18002d090  mov     rcx, r12; lpOutputString
0x18002d093  call    cs:__imp_OutputDebugStringA
0x18002d099  mov     rax, [rdi]
0x18002d09c  test    dword ptr [rax+50h], 100h
0x18002d0a3  jz      short loc_18002D0D5
0x18002d0a5  mov     ecx, 0FFFFFFF5h; nStdHandle
0x18002d0aa  call    cs:__imp_GetStdHandle
0x18002d0b0  lea     rcx, [rax-1]
0x18002d0b4  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18002d0b8  ja      short loc_18002D0D5
0x18002d0ba  mov     r8d, esi; nNumberOfBytesToWrite
0x18002d0bd  mov     [rsp+78h+lpOverlapped], 0; lpOverlapped
0x18002d0c6  xor     r9d, r9d; lpNumberOfBytesWritten
0x18002d0c9  mov     rdx, r12; lpBuffer
0x18002d0cc  mov     rcx, rax; hFile
0x18002d0cf  call    cs:__imp_WriteFile
0x18002d0d5  mov     rax, [rdi]
0x18002d0d8  test    byte ptr [rax+50h], 4
0x18002d0dc  jz      short loc_18002D11D
0x18002d0de  mov     rcx, rbx; CriticalSection
0x18002d0e1  call    cs:__imp_RtlEnterCriticalSection
0x18002d0e7  mov     rax, [rdi]
0x18002d0ea  lea     rcx, [rdi+0C0h]; unsigned __int16 *
0x18002d0f1  mov     r8, r13; unsigned __int64
0x18002d0f4  mov     rdx, r12; char *
0x18002d0f7  mov     r9d, [rax+50h]
0x18002d0fb  mov     eax, r9d
0x18002d0fe  shr     eax, 5
0x18002d101  shr     r9d, 3
0x18002d105  and     al, bpl
0x18002d108  and     r9b, bpl; unsigned __int8
0x18002d10b  mov     byte ptr [rsp+78h+lpOverlapped], al; unsigned __int8
0x18002d10f  call    ?AslLogpAppendLog@@YAJPEBGPEBD_KEE@Z; AslLogpAppendLog(ushort const *,char const *,unsigned __int64,uchar,uchar)
0x18002d114  mov     rcx, rbx; CriticalSection
0x18002d117  call    cs:__imp_RtlLeaveCriticalSection
0x18002d11d  add     rsp, 38h
0x18002d121  pop     r15
0x18002d123  pop     r14
0x18002d125  pop     r13
0x18002d127  pop     r12
0x18002d129  pop     rdi
0x18002d12a  pop     rsi
0x18002d12b  pop     rbp
0x18002d12c  pop     rbx
0x18002d12d  retn
```
