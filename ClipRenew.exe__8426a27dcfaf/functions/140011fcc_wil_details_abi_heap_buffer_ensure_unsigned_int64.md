# wil::details_abi::heap_buffer::ensure(unsigned __int64)

- ea: `0x140011fcc`
- end: `0x14001209f`
- name: `?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z`
- size: `211`
- prototype: `char __fastcall(wil::details_abi::heap_buffer *this, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x14000fc18`
- `0x14000fda8`
- `0x140010564`
- `0x1400114d4`
- `0x1400116a4`

## callees

- `0x140004a94`
- `0x140011fcc`

## import_xrefs

- `msvcrt!memcpy_s` at `0x14001204e`
- `msvcrt!memcpy_s` at `0x14001204e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140012061`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140012061`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001206f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001206f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140012031`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14001208a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140012031`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14001208a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001200d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001200d`

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
0x140011fcc  push    rbx
0x140011fce  push    rbp
0x140011fcf  push    rsi
0x140011fd0  push    rdi
0x140011fd1  push    r14
0x140011fd3  push    r15
0x140011fd5  sub     rsp, 28h
0x140011fd9  mov     rdi, rcx
0x140011fdc  mov     rbx, rdx
0x140011fdf  mov     rcx, [rcx+10h]
0x140011fe3  mov     rax, [rdi+8]
0x140011fe7  sub     rax, [rdi]
0x140011fea  sub     rcx, [rdi]
0x140011fed  add     rax, rdx
0x140011ff0  cmp     rax, rcx
0x140011ff3  jb      loc_140012090
0x140011ff9  lea     rax, [rcx+rcx]
0x140011ffd  cmp     rdx, rax
0x140012000  cmovb   rbx, rax
0x140012004  cmp     rcx, rbx
0x140012007  jnb     loc_140012090
0x14001200d  call    cs:__imp_GetLastError
0x140012013  and     rbx, 0FFFFFFFFFFFFFFC0h
0x140012017  xor     ecx, ecx; dwFlags
0x140012019  mov     esi, eax
0x14001201b  lea     r14, [rbx+40h]
0x14001201f  mov     rdx, r14; dwBytes
0x140012022  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140012027  mov     rbx, rax
0x14001202a  test    rax, rax
0x14001202d  jnz     short loc_14001203B
0x14001202f  mov     ecx, esi; dwErrCode
0x140012031  call    cs:__imp_SetLastError
0x140012037  xor     al, al
0x140012039  jmp     short loc_140012092
0x14001203b  mov     r15, [rdi+8]
0x14001203f  mov     rdx, r14; DestinationSize
0x140012042  sub     r15, [rdi]
0x140012045  mov     rcx, rbx; Destination
0x140012048  mov     r8, [rdi]; Source
0x14001204b  mov     r9, r15; SourceSize
0x14001204e  call    cs:__imp_memcpy_s
0x140012054  mov     rbp, [rdi+18h]
0x140012058  mov     [rdi+18h], rbx
0x14001205c  test    rbp, rbp
0x14001205f  jz      short loc_140012075
0x140012061  call    cs:__imp_GetProcessHeap
0x140012067  mov     r8, rbp; lpMem
0x14001206a  xor     edx, edx; dwFlags
0x14001206c  mov     rcx, rax; hHeap
0x14001206f  call    cs:__imp_HeapFree
0x140012075  lea     rax, [r15+rbx]
0x140012079  mov     [rdi], rbx
0x14001207c  mov     [rdi+8], rax
0x140012080  mov     ecx, esi; dwErrCode
0x140012082  lea     rax, [r14+rbx]
0x140012086  mov     [rdi+10h], rax
0x14001208a  call    cs:__imp_SetLastError
0x140012090  mov     al, 1
0x140012092  add     rsp, 28h
0x140012096  pop     r15
0x140012098  pop     r14
0x14001209a  pop     rdi
0x14001209b  pop     rsi
0x14001209c  pop     rbp
0x14001209d  pop     rbx
0x14001209e  retn
```
