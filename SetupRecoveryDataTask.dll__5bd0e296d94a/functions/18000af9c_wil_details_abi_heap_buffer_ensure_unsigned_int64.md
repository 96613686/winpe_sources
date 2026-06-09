# wil::details_abi::heap_buffer::ensure(unsigned __int64)

- ea: `0x18000af9c`
- end: `0x18000b06f`
- name: `?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z`
- size: `211`
- prototype: `char __fastcall(wil::details_abi::heap_buffer *this, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x1800079c8`
- `0x180008784`
- `0x180009528`
- `0x18000971c`
- `0x180009c50`

## callees

- `0x180006ffc`
- `0x18000af9c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000b01e`
- `msvcrt!memcpy_s` at `0x18000b01e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b03f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b03f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b031`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b031`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000afdd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000afdd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b001`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b05a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b001`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b05a`

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
0x18000af9c  push    rbx
0x18000af9e  push    rbp
0x18000af9f  push    rsi
0x18000afa0  push    rdi
0x18000afa1  push    r14
0x18000afa3  push    r15
0x18000afa5  sub     rsp, 28h
0x18000afa9  mov     rdi, rcx
0x18000afac  mov     rbx, rdx
0x18000afaf  mov     rcx, [rcx+10h]
0x18000afb3  mov     rax, [rdi+8]
0x18000afb7  sub     rax, [rdi]
0x18000afba  sub     rcx, [rdi]
0x18000afbd  add     rax, rdx
0x18000afc0  cmp     rax, rcx
0x18000afc3  jb      loc_18000B060
0x18000afc9  lea     rax, [rcx+rcx]
0x18000afcd  cmp     rdx, rax
0x18000afd0  cmovb   rbx, rax
0x18000afd4  cmp     rcx, rbx
0x18000afd7  jnb     loc_18000B060
0x18000afdd  call    cs:__imp_GetLastError
0x18000afe3  and     rbx, 0FFFFFFFFFFFFFFC0h
0x18000afe7  xor     ecx, ecx; dwFlags
0x18000afe9  mov     esi, eax
0x18000afeb  lea     r14, [rbx+40h]
0x18000afef  mov     rdx, r14; dwBytes
0x18000aff2  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000aff7  mov     rbx, rax
0x18000affa  test    rax, rax
0x18000affd  jnz     short loc_18000B00B
0x18000afff  mov     ecx, esi; dwErrCode
0x18000b001  call    cs:__imp_SetLastError
0x18000b007  xor     al, al
0x18000b009  jmp     short loc_18000B062
0x18000b00b  mov     r15, [rdi+8]
0x18000b00f  mov     rdx, r14; DestinationSize
0x18000b012  sub     r15, [rdi]
0x18000b015  mov     rcx, rbx; Destination
0x18000b018  mov     r8, [rdi]; Source
0x18000b01b  mov     r9, r15; SourceSize
0x18000b01e  call    cs:__imp_memcpy_s
0x18000b024  mov     rbp, [rdi+18h]
0x18000b028  mov     [rdi+18h], rbx
0x18000b02c  test    rbp, rbp
0x18000b02f  jz      short loc_18000B045
0x18000b031  call    cs:__imp_GetProcessHeap
0x18000b037  mov     r8, rbp; lpMem
0x18000b03a  xor     edx, edx; dwFlags
0x18000b03c  mov     rcx, rax; hHeap
0x18000b03f  call    cs:__imp_HeapFree
0x18000b045  lea     rax, [r15+rbx]
0x18000b049  mov     [rdi], rbx
0x18000b04c  mov     [rdi+8], rax
0x18000b050  mov     ecx, esi; dwErrCode
0x18000b052  lea     rax, [r14+rbx]
0x18000b056  mov     [rdi+10h], rax
0x18000b05a  call    cs:__imp_SetLastError
0x18000b060  mov     al, 1
0x18000b062  add     rsp, 28h
0x18000b066  pop     r15
0x18000b068  pop     r14
0x18000b06a  pop     rdi
0x18000b06b  pop     rsi
0x18000b06c  pop     rbp
0x18000b06d  pop     rbx
0x18000b06e  retn
```
