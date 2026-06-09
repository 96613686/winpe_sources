# wil::details_abi::heap_buffer::ensure(unsigned __int64)

- ea: `0x18001685c`
- end: `0x180016956`
- name: `?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z`
- size: `250`
- prototype: `bool __fastcall(wil::details_abi::heap_buffer *__hidden this, unsigned __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180013c64`
- `0x1800142ac`
- `0x180015900`
- `0x180015bf8`

## callees

- `0x18001393c`
- `0x18001685c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800168eb`
- `msvcrt!memcpy_s` at `0x1800168eb`
- `KERNEL32!HeapFree` at `0x180016918`
- `KERNEL32!HeapFree` at `0x180016918`
- `KERNEL32!GetProcessHeap` at `0x180016904`
- `KERNEL32!GetProcessHeap` at `0x180016904`
- `KERNEL32!GetLastError` at `0x18001689d`
- `KERNEL32!GetLastError` at `0x18001689d`
- `KERNEL32!SetLastError` at `0x1800168c7`
- `KERNEL32!SetLastError` at `0x180016939`
- `KERNEL32!SetLastError` at `0x1800168c7`
- `KERNEL32!SetLastError` at `0x180016939`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall wil::details_abi::heap_buffer::ensure(wil::details_abi::heap_buffer *this, unsigned __int64 a2)
{
  unsigned __int64 v2; // rbx
  unsigned __int64 v4; // rcx
  DWORD LastError; // esi
  unsigned __int64 v6; // r14
  char *v7; // rax
  char *v8; // rbx
  rsize_t v10; // r15
  void *v11; // rbp
  HANDLE ProcessHeap; // rax

  v2 = a2;
  v4 = *((_QWORD *)this + 2) - *(_QWORD *)this;
  if ( a2 + *((_QWORD *)this + 1) - *(_QWORD *)this >= v4 )
  {
    if ( a2 < 2 * v4 )
      v2 = 2 * v4;
    if ( v4 < v2 )
    {
      LastError = GetLastError();
      v6 = (v2 & 0xFFFFFFFFFFFFFFC0uLL) + 64;
      v7 = (char *)wil::details::ProcessHeapAlloc(0, v6);
      v8 = v7;
      if ( !v7 )
      {
        SetLastError(LastError);
        return 0;
      }
      v10 = *((_QWORD *)this + 1) - *(_QWORD *)this;
      memcpy_s(v7, v6, *(const void *const *)this, v10);
      v11 = (void *)*((_QWORD *)this + 3);
      *((_QWORD *)this + 3) = v8;
      if ( v11 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v11);
      }
      *(_QWORD *)this = v8;
      *((_QWORD *)this + 1) = &v8[v10];
      *((_QWORD *)this + 2) = &v8[v6];
      SetLastError(LastError);
    }
  }
  return 1;
}

```

## disassembly

```asm
0x18001685c  push    rbx
0x18001685e  push    rbp
0x18001685f  push    rsi
0x180016860  push    rdi
0x180016861  push    r14
0x180016863  push    r15
0x180016865  sub     rsp, 28h
0x180016869  mov     rbx, rdx
0x18001686c  mov     rdi, rcx
0x18001686f  mov     rcx, [rcx+10h]
0x180016873  sub     rcx, [rdi]
0x180016876  mov     rax, [rdi+8]
0x18001687a  sub     rax, [rdi]
0x18001687d  add     rax, rdx
0x180016880  cmp     rax, rcx
0x180016883  jb      loc_180016946
0x180016889  lea     rax, [rcx+rcx]
0x18001688d  cmp     rdx, rax
0x180016890  cmovb   rbx, rax
0x180016894  cmp     rcx, rbx
0x180016897  jnb     loc_180016946
0x18001689d  call    cs:__imp_GetLastError
0x1800168a4  nop     dword ptr [rax+rax+00h]
0x1800168a9  mov     esi, eax
0x1800168ab  and     rbx, 0FFFFFFFFFFFFFFC0h
0x1800168af  lea     r14, [rbx+40h]
0x1800168b3  mov     rdx, r14; dwBytes
0x1800168b6  xor     ecx, ecx; dwFlags
0x1800168b8  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800168bd  mov     rbx, rax
0x1800168c0  test    rax, rax
0x1800168c3  jnz     short loc_1800168D8
0x1800168c5  mov     ecx, esi; dwErrCode
0x1800168c7  call    cs:__imp_SetLastError
0x1800168ce  nop     dword ptr [rax+rax+00h]
0x1800168d3  nop
0x1800168d4  xor     al, al
0x1800168d6  jmp     short loc_180016948
0x1800168d8  mov     r15, [rdi+8]
0x1800168dc  sub     r15, [rdi]
0x1800168df  mov     r9, r15; SourceSize
0x1800168e2  mov     r8, [rdi]; Source
0x1800168e5  mov     rdx, r14; DestinationSize
0x1800168e8  mov     rcx, rbx; Destination
0x1800168eb  call    cs:__imp_memcpy_s
0x1800168f2  nop     dword ptr [rax+rax+00h]
0x1800168f7  mov     rbp, [rdi+18h]
0x1800168fb  mov     [rdi+18h], rbx
0x1800168ff  test    rbp, rbp
0x180016902  jz      short loc_180016924
0x180016904  call    cs:__imp_GetProcessHeap
0x18001690b  nop     dword ptr [rax+rax+00h]
0x180016910  mov     rcx, rax; hHeap
0x180016913  mov     r8, rbp; lpMem
0x180016916  xor     edx, edx; dwFlags
0x180016918  call    cs:__imp_HeapFree
0x18001691f  nop     dword ptr [rax+rax+00h]
0x180016924  mov     [rdi], rbx
0x180016927  lea     rax, [r15+rbx]
0x18001692b  mov     [rdi+8], rax
0x18001692f  lea     rax, [r14+rbx]
0x180016933  mov     [rdi+10h], rax
0x180016937  mov     ecx, esi; dwErrCode
0x180016939  call    cs:__imp_SetLastError
0x180016940  nop     dword ptr [rax+rax+00h]
0x180016945  nop
0x180016946  mov     al, 1
0x180016948  add     rsp, 28h
0x18001694c  pop     r15
0x18001694e  pop     r14
0x180016950  pop     rdi
0x180016951  pop     rsi
0x180016952  pop     rbp
0x180016953  pop     rbx
0x180016954  retn
```
