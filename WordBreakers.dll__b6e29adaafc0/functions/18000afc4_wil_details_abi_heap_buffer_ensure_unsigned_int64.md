# wil::details_abi::heap_buffer::ensure(unsigned __int64)

- ea: `0x18000afc4`
- end: `0x18000b097`
- name: `?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z`
- size: `211`
- prototype: `char __fastcall(wil::details_abi::heap_buffer *this, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800094b0`
- `0x180009a58`
- `0x18000a9e0`

## callees

- `0x180005678`
- `0x18000afc4`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000b046`
- `msvcrt!memcpy_s` at `0x18000b046`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b005`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b005`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b029`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b082`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b029`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b082`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b059`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b059`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b067`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b067`

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
0x18000afc4  push    rbx
0x18000afc6  push    rbp
0x18000afc7  push    rsi
0x18000afc8  push    rdi
0x18000afc9  push    r14
0x18000afcb  push    r15
0x18000afcd  sub     rsp, 28h
0x18000afd1  mov     rdi, rcx
0x18000afd4  mov     rbx, rdx
0x18000afd7  mov     rcx, [rcx+10h]
0x18000afdb  mov     rax, [rdi+8]
0x18000afdf  sub     rax, [rdi]
0x18000afe2  sub     rcx, [rdi]
0x18000afe5  add     rax, rdx
0x18000afe8  cmp     rax, rcx
0x18000afeb  jb      loc_18000B088
0x18000aff1  lea     rax, [rcx+rcx]
0x18000aff5  cmp     rdx, rax
0x18000aff8  cmovb   rbx, rax
0x18000affc  cmp     rcx, rbx
0x18000afff  jnb     loc_18000B088
0x18000b005  call    cs:__imp_GetLastError
0x18000b00b  and     rbx, 0FFFFFFFFFFFFFFC0h
0x18000b00f  xor     ecx, ecx; dwFlags
0x18000b011  mov     esi, eax
0x18000b013  lea     r14, [rbx+40h]
0x18000b017  mov     rdx, r14; dwBytes
0x18000b01a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000b01f  mov     rbx, rax
0x18000b022  test    rax, rax
0x18000b025  jnz     short loc_18000B033
0x18000b027  mov     ecx, esi; dwErrCode
0x18000b029  call    cs:__imp_SetLastError
0x18000b02f  xor     al, al
0x18000b031  jmp     short loc_18000B08A
0x18000b033  mov     r15, [rdi+8]
0x18000b037  mov     rdx, r14; DestinationSize
0x18000b03a  sub     r15, [rdi]
0x18000b03d  mov     rcx, rbx; Destination
0x18000b040  mov     r8, [rdi]; Source
0x18000b043  mov     r9, r15; SourceSize
0x18000b046  call    cs:__imp_memcpy_s
0x18000b04c  mov     rbp, [rdi+18h]
0x18000b050  mov     [rdi+18h], rbx
0x18000b054  test    rbp, rbp
0x18000b057  jz      short loc_18000B06D
0x18000b059  call    cs:__imp_GetProcessHeap
0x18000b05f  mov     r8, rbp; lpMem
0x18000b062  xor     edx, edx; dwFlags
0x18000b064  mov     rcx, rax; hHeap
0x18000b067  call    cs:__imp_HeapFree
0x18000b06d  lea     rax, [r15+rbx]
0x18000b071  mov     [rdi], rbx
0x18000b074  mov     [rdi+8], rax
0x18000b078  mov     ecx, esi; dwErrCode
0x18000b07a  lea     rax, [r14+rbx]
0x18000b07e  mov     [rdi+10h], rax
0x18000b082  call    cs:__imp_SetLastError
0x18000b088  mov     al, 1
0x18000b08a  add     rsp, 28h
0x18000b08e  pop     r15
0x18000b090  pop     r14
0x18000b092  pop     rdi
0x18000b093  pop     rsi
0x18000b094  pop     rbp
0x18000b095  pop     rbx
0x18000b096  retn
```
