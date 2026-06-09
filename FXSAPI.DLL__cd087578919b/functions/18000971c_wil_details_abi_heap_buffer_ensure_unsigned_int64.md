# wil::details_abi::heap_buffer::ensure(unsigned __int64)

- ea: `0x18000971c`
- end: `0x180009814`
- name: `?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z`
- size: `248`
- prototype: `bool __fastcall(wil::details_abi::heap_buffer *__hidden this, unsigned __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180006790`
- `0x180006ddc`
- `0x180008540`
- `0x180008838`

## callees

- `0x180006468`
- `0x18000971c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800097aa`
- `msvcrt!memcpy_s` at `0x1800097aa`
- `KERNEL32!GetProcessHeap` at `0x1800097c3`
- `KERNEL32!GetProcessHeap` at `0x1800097c3`
- `KERNEL32!SetLastError` at `0x180009787`
- `KERNEL32!SetLastError` at `0x1800097f8`
- `KERNEL32!SetLastError` at `0x180009787`
- `KERNEL32!SetLastError` at `0x1800097f8`
- `KERNEL32!GetLastError` at `0x18000975d`
- `KERNEL32!GetLastError` at `0x18000975d`
- `KERNEL32!HeapFree` at `0x1800097d7`
- `KERNEL32!HeapFree` at `0x1800097d7`

## pseudocode

```c
char __fastcall wil::details_abi::heap_buffer::ensure(wil::details_abi::heap_buffer *this, unsigned __int64 a2)
{
  unsigned __int64 v3; // rbx
  unsigned __int64 v4; // rcx
  DWORD LastError; // esi
  unsigned __int64 v6; // r14
  char *v7; // rax
  char *v8; // rbx
  rsize_t v10; // r15
  void *v11; // rbp
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
0x18000971c  push    rbx
0x18000971e  push    rbp
0x18000971f  push    rsi
0x180009720  push    rdi
0x180009721  push    r14
0x180009723  push    r15
0x180009725  sub     rsp, 28h
0x180009729  mov     rdi, rcx
0x18000972c  mov     rbx, rdx
0x18000972f  mov     rcx, [rcx+10h]
0x180009733  mov     rax, [rdi+8]
0x180009737  sub     rax, [rdi]
0x18000973a  sub     rcx, [rdi]
0x18000973d  add     rax, rdx
0x180009740  cmp     rax, rcx
0x180009743  jb      loc_180009804
0x180009749  lea     rax, [rcx+rcx]
0x18000974d  cmp     rdx, rax
0x180009750  cmovb   rbx, rax
0x180009754  cmp     rcx, rbx
0x180009757  jnb     loc_180009804
0x18000975d  call    cs:__imp_GetLastError
0x180009764  nop     dword ptr [rax+rax+00h]
0x180009769  and     rbx, 0FFFFFFFFFFFFFFC0h
0x18000976d  xor     ecx, ecx; dwFlags
0x18000976f  mov     esi, eax
0x180009771  lea     r14, [rbx+40h]
0x180009775  mov     rdx, r14; dwBytes
0x180009778  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000977d  mov     rbx, rax
0x180009780  test    rax, rax
0x180009783  jnz     short loc_180009797
0x180009785  mov     ecx, esi; dwErrCode
0x180009787  call    cs:__imp_SetLastError
0x18000978e  nop     dword ptr [rax+rax+00h]
0x180009793  xor     al, al
0x180009795  jmp     short loc_180009806
0x180009797  mov     r15, [rdi+8]
0x18000979b  mov     rdx, r14; DestinationSize
0x18000979e  sub     r15, [rdi]
0x1800097a1  mov     rcx, rbx; Destination
0x1800097a4  mov     r8, [rdi]; Source
0x1800097a7  mov     r9, r15; SourceSize
0x1800097aa  call    cs:__imp_memcpy_s
0x1800097b1  nop     dword ptr [rax+rax+00h]
0x1800097b6  mov     rbp, [rdi+18h]
0x1800097ba  mov     [rdi+18h], rbx
0x1800097be  test    rbp, rbp
0x1800097c1  jz      short loc_1800097E3
0x1800097c3  call    cs:__imp_GetProcessHeap
0x1800097ca  nop     dword ptr [rax+rax+00h]
0x1800097cf  mov     r8, rbp; lpMem
0x1800097d2  xor     edx, edx; dwFlags
0x1800097d4  mov     rcx, rax; hHeap
0x1800097d7  call    cs:__imp_HeapFree
0x1800097de  nop     dword ptr [rax+rax+00h]
0x1800097e3  lea     rax, [r15+rbx]
0x1800097e7  mov     [rdi], rbx
0x1800097ea  mov     [rdi+8], rax
0x1800097ee  mov     ecx, esi; dwErrCode
0x1800097f0  lea     rax, [r14+rbx]
0x1800097f4  mov     [rdi+10h], rax
0x1800097f8  call    cs:__imp_SetLastError
0x1800097ff  nop     dword ptr [rax+rax+00h]
0x180009804  mov     al, 1
0x180009806  add     rsp, 28h
0x18000980a  pop     r15
0x18000980c  pop     r14
0x18000980e  pop     rdi
0x18000980f  pop     rsi
0x180009810  pop     rbp
0x180009811  pop     rbx
0x180009812  retn
```
