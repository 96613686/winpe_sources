# wil::details_abi::heap_buffer::ensure(unsigned __int64)

- ea: `0x14000dd18`
- end: `0x14000ddea`
- name: `?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z`
- size: `210`
- prototype: `char __fastcall(wil::details_abi::heap_buffer *this, unsigned __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x14000acb4`
- `0x14000b280`
- `0x14000c67c`

## callees

- `0x140004978`
- `0x14000ac10`
- `0x14000dd18`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000ddac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000ddac`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000ddba`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000ddba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000dd59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000dd59`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000dd7d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000ddd5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000dd7d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000ddd5`

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
0x14000dd18  push    rbx
0x14000dd1a  push    rbp
0x14000dd1b  push    rsi
0x14000dd1c  push    rdi
0x14000dd1d  push    r14
0x14000dd1f  push    r15
0x14000dd21  sub     rsp, 28h
0x14000dd25  mov     rdi, rcx
0x14000dd28  mov     rbx, rdx
0x14000dd2b  mov     rcx, [rcx+10h]
0x14000dd2f  mov     rax, [rdi+8]
0x14000dd33  sub     rax, [rdi]
0x14000dd36  sub     rcx, [rdi]
0x14000dd39  add     rax, rdx
0x14000dd3c  cmp     rax, rcx
0x14000dd3f  jb      loc_14000DDDB
0x14000dd45  lea     rax, [rcx+rcx]
0x14000dd49  cmp     rdx, rax
0x14000dd4c  cmovb   rbx, rax
0x14000dd50  cmp     rcx, rbx
0x14000dd53  jnb     loc_14000DDDB
0x14000dd59  call    cs:__imp_GetLastError
0x14000dd5f  and     rbx, 0FFFFFFFFFFFFFFC0h
0x14000dd63  xor     ecx, ecx; dwFlags
0x14000dd65  mov     esi, eax
0x14000dd67  lea     r14, [rbx+40h]
0x14000dd6b  mov     rdx, r14; dwBytes
0x14000dd6e  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14000dd73  mov     rbx, rax
0x14000dd76  test    rax, rax
0x14000dd79  jnz     short loc_14000DD87
0x14000dd7b  mov     ecx, esi; dwErrCode
0x14000dd7d  call    cs:__imp_SetLastError
0x14000dd83  xor     al, al
0x14000dd85  jmp     short loc_14000DDDD
0x14000dd87  mov     r15, [rdi+8]
0x14000dd8b  mov     rdx, r14; DestinationSize
0x14000dd8e  sub     r15, [rdi]
0x14000dd91  mov     rcx, rbx; Destination
0x14000dd94  mov     r8, [rdi]; Source
0x14000dd97  mov     r9, r15; SourceSize
0x14000dd9a  call    memcpy_s
0x14000dd9f  mov     rbp, [rdi+18h]
0x14000dda3  mov     [rdi+18h], rbx
0x14000dda7  test    rbp, rbp
0x14000ddaa  jz      short loc_14000DDC0
0x14000ddac  call    cs:__imp_GetProcessHeap
0x14000ddb2  mov     r8, rbp; lpMem
0x14000ddb5  xor     edx, edx; dwFlags
0x14000ddb7  mov     rcx, rax; hHeap
0x14000ddba  call    cs:__imp_HeapFree
0x14000ddc0  lea     rax, [r15+rbx]
0x14000ddc4  mov     [rdi], rbx
0x14000ddc7  mov     [rdi+8], rax
0x14000ddcb  mov     ecx, esi; dwErrCode
0x14000ddcd  lea     rax, [r14+rbx]
0x14000ddd1  mov     [rdi+10h], rax
0x14000ddd5  call    cs:__imp_SetLastError
0x14000dddb  mov     al, 1
0x14000dddd  add     rsp, 28h
0x14000dde1  pop     r15
0x14000dde3  pop     r14
0x14000dde5  pop     rdi
0x14000dde6  pop     rsi
0x14000dde7  pop     rbp
0x14000dde8  pop     rbx
0x14000dde9  retn
```
