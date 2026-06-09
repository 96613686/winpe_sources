# wil::details_abi::heap_buffer::ensure(unsigned __int64)

- ea: `0x18000ac4c`
- end: `0x18000ad1e`
- name: `?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z`
- size: `210`
- prototype: `char __fastcall(wil::details_abi::heap_buffer *this, unsigned __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18000824c`
- `0x180008888`
- `0x18000a150`

## callees

- `0x1800081a8`
- `0x18000ac4c`
- `0x18000b080`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ac8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ac8d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000acb1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ad09`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000acb1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ad09`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000acee`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000acee`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ace0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ace0`

## pseudocode

```c
char __fastcall wil::details_abi::heap_buffer::ensure(wil::details_abi::heap_buffer *this, unsigned __int64 a2)
{
  unsigned __int64 v3; // rbx
  unsigned __int64 v4; // rcx
  DWORD LastError; // esi
  unsigned __int64 v6; // r14
  unsigned __int64 v7; // r8
  char *v8; // rax
  char *v9; // rbx
  rsize_t v11; // r15
  void *v12; // rbp
  HANDLE ProcessHeap; // rax

  v3 = a2;
  v4 = *((_QWORD *)this + 2) - *(_QWORD *)this;
  if ( a2 + *((_QWORD *)this + 1) - *(_QWORD *)this >= v4 )
  {
    if ( a2 < 2 * v4 )
      v3 = 2 * v4;
    if ( v4 < v3 )
    {
      LastError = GetLastError();
      v6 = (v3 & 0xFFFFFFFFFFFFFFC0uLL) + 64;
      v8 = (char *)wil::details::ProcessHeapAlloc(0, v6, v7);
      v9 = v8;
      if ( !v8 )
      {
        SetLastError(LastError);
        return 0;
      }
      v11 = *((_QWORD *)this + 1) - *(_QWORD *)this;
      memcpy_s(v8, v6, *(const void *const *)this, v11);
      v12 = (void *)*((_QWORD *)this + 3);
      *((_QWORD *)this + 3) = v9;
      if ( v12 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v12);
      }
      *(_QWORD *)this = v9;
      *((_QWORD *)this + 1) = &v9[v11];
      *((_QWORD *)this + 2) = &v9[v6];
      SetLastError(LastError);
    }
  }
  return 1;
}

```

## disassembly

```asm
0x18000ac4c  push    rbx
0x18000ac4e  push    rbp
0x18000ac4f  push    rsi
0x18000ac50  push    rdi
0x18000ac51  push    r14
0x18000ac53  push    r15
0x18000ac55  sub     rsp, 28h
0x18000ac59  mov     rdi, rcx
0x18000ac5c  mov     rbx, rdx
0x18000ac5f  mov     rcx, [rcx+10h]
0x18000ac63  mov     rax, [rdi+8]
0x18000ac67  sub     rax, [rdi]
0x18000ac6a  sub     rcx, [rdi]
0x18000ac6d  add     rax, rdx
0x18000ac70  cmp     rax, rcx
0x18000ac73  jb      loc_18000AD0F
0x18000ac79  lea     rax, [rcx+rcx]
0x18000ac7d  cmp     rdx, rax
0x18000ac80  cmovb   rbx, rax
0x18000ac84  cmp     rcx, rbx
0x18000ac87  jnb     loc_18000AD0F
0x18000ac8d  call    cs:__imp_GetLastError
0x18000ac93  and     rbx, 0FFFFFFFFFFFFFFC0h
0x18000ac97  xor     ecx, ecx; dwFlags
0x18000ac99  mov     esi, eax
0x18000ac9b  lea     r14, [rbx+40h]
0x18000ac9f  mov     rdx, r14; dwBytes
0x18000aca2  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000aca7  mov     rbx, rax
0x18000acaa  test    rax, rax
0x18000acad  jnz     short loc_18000ACBB
0x18000acaf  mov     ecx, esi; dwErrCode
0x18000acb1  call    cs:__imp_SetLastError
0x18000acb7  xor     al, al
0x18000acb9  jmp     short loc_18000AD11
0x18000acbb  mov     r15, [rdi+8]
0x18000acbf  mov     rdx, r14; DestinationSize
0x18000acc2  sub     r15, [rdi]
0x18000acc5  mov     rcx, rbx; Destination
0x18000acc8  mov     r8, [rdi]; Source
0x18000accb  mov     r9, r15; SourceSize
0x18000acce  call    memcpy_s
0x18000acd3  mov     rbp, [rdi+18h]
0x18000acd7  mov     [rdi+18h], rbx
0x18000acdb  test    rbp, rbp
0x18000acde  jz      short loc_18000ACF4
0x18000ace0  call    cs:__imp_GetProcessHeap
0x18000ace6  mov     r8, rbp; lpMem
0x18000ace9  xor     edx, edx; dwFlags
0x18000aceb  mov     rcx, rax; hHeap
0x18000acee  call    cs:__imp_HeapFree
0x18000acf4  lea     rax, [r15+rbx]
0x18000acf8  mov     [rdi], rbx
0x18000acfb  mov     [rdi+8], rax
0x18000acff  mov     ecx, esi; dwErrCode
0x18000ad01  lea     rax, [r14+rbx]
0x18000ad05  mov     [rdi+10h], rax
0x18000ad09  call    cs:__imp_SetLastError
0x18000ad0f  mov     al, 1
0x18000ad11  add     rsp, 28h
0x18000ad15  pop     r15
0x18000ad17  pop     r14
0x18000ad19  pop     rdi
0x18000ad1a  pop     rsi
0x18000ad1b  pop     rbp
0x18000ad1c  pop     rbx
0x18000ad1d  retn
```
