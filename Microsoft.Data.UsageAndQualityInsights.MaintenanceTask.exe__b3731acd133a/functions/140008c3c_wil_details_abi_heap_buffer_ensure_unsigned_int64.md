# wil::details_abi::heap_buffer::ensure(unsigned __int64)

- ea: `0x140008c3c`
- end: `0x140008d0e`
- name: `?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z`
- size: `210`
- prototype: `char __fastcall(wil::details_abi::heap_buffer *this, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x140005e58`
- `0x140006698`
- `0x140007e64`
- `0x14000806c`
- `0x14000aa8c`

## callees

- `0x140005d18`
- `0x140008c3c`
- `0x140009088`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008cd0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008cd0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008cde`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008cde`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008c7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008c7d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140008ca1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140008cf9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140008ca1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140008cf9`

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
0x140008c3c  push    rbx
0x140008c3e  push    rbp
0x140008c3f  push    rsi
0x140008c40  push    rdi
0x140008c41  push    r14
0x140008c43  push    r15
0x140008c45  sub     rsp, 28h
0x140008c49  mov     rdi, rcx
0x140008c4c  mov     rbx, rdx
0x140008c4f  mov     rcx, [rcx+10h]
0x140008c53  mov     rax, [rdi+8]
0x140008c57  sub     rax, [rdi]
0x140008c5a  sub     rcx, [rdi]
0x140008c5d  add     rax, rdx
0x140008c60  cmp     rax, rcx
0x140008c63  jb      loc_140008CFF
0x140008c69  lea     rax, [rcx+rcx]
0x140008c6d  cmp     rdx, rax
0x140008c70  cmovb   rbx, rax
0x140008c74  cmp     rcx, rbx
0x140008c77  jnb     loc_140008CFF
0x140008c7d  call    cs:__imp_GetLastError
0x140008c83  and     rbx, 0FFFFFFFFFFFFFFC0h
0x140008c87  xor     ecx, ecx; dwFlags
0x140008c89  mov     esi, eax
0x140008c8b  lea     r14, [rbx+40h]
0x140008c8f  mov     rdx, r14; dwBytes
0x140008c92  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140008c97  mov     rbx, rax
0x140008c9a  test    rax, rax
0x140008c9d  jnz     short loc_140008CAB
0x140008c9f  mov     ecx, esi; dwErrCode
0x140008ca1  call    cs:__imp_SetLastError
0x140008ca7  xor     al, al
0x140008ca9  jmp     short loc_140008D01
0x140008cab  mov     r15, [rdi+8]
0x140008caf  mov     rdx, r14; DestinationSize
0x140008cb2  sub     r15, [rdi]
0x140008cb5  mov     rcx, rbx; Destination
0x140008cb8  mov     r8, [rdi]; Source
0x140008cbb  mov     r9, r15; SourceSize
0x140008cbe  call    memcpy_s
0x140008cc3  mov     rbp, [rdi+18h]
0x140008cc7  mov     [rdi+18h], rbx
0x140008ccb  test    rbp, rbp
0x140008cce  jz      short loc_140008CE4
0x140008cd0  call    cs:__imp_GetProcessHeap
0x140008cd6  mov     r8, rbp; lpMem
0x140008cd9  xor     edx, edx; dwFlags
0x140008cdb  mov     rcx, rax; hHeap
0x140008cde  call    cs:__imp_HeapFree
0x140008ce4  lea     rax, [r15+rbx]
0x140008ce8  mov     [rdi], rbx
0x140008ceb  mov     [rdi+8], rax
0x140008cef  mov     ecx, esi; dwErrCode
0x140008cf1  lea     rax, [r14+rbx]
0x140008cf5  mov     [rdi+10h], rax
0x140008cf9  call    cs:__imp_SetLastError
0x140008cff  mov     al, 1
0x140008d01  add     rsp, 28h
0x140008d05  pop     r15
0x140008d07  pop     r14
0x140008d09  pop     rdi
0x140008d0a  pop     rsi
0x140008d0b  pop     rbp
0x140008d0c  pop     rbx
0x140008d0d  retn
```
