# TlmiInitializeProviderGlobalData

- ea: `0x180018ce0`
- end: `0x180018e1c`
- name: `TlmiInitializeProviderGlobalData`
- size: `316`
- prototype: `__int64 __fastcall(void *Src, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180011d18`
- `0x180019c8c`

## callees

- `0x180018ce0`
- `0x18001be5c`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x180018d2c`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x180018d45`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x180018d2c`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x180018d45`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180018d07`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180018d07`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180018e0a`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180018e0a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180018d88`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180018d88`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180018d99`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180018d99`

## pseudocode

```c
char __fastcall TlmiInitializeProviderGlobalData(const wchar_t *Src, const wchar_t *a2)
{
  char result; // al
  unsigned int v5; // eax
  __int64 v6; // rbx
  unsigned int v7; // eax
  size_t v8; // r15
  size_t v9; // r14
  HANDLE ProcessHeap; // rax
  char *v11; // rax

  result = byte_180028938;
  if ( !byte_180028938 )
  {
    RtlAcquireSRWLockExclusive(&qword_180028940);
    if ( !byte_180028938 )
    {
      if ( Src )
        v5 = wcsnlen(Src, 0xFFu);
      else
        v5 = 0;
      v6 = v5;
      if ( a2 )
        v7 = wcsnlen(a2, 0xFFu);
      else
        v7 = 0;
      if ( (unsigned __int64)(2 * v6 - 3) <= 0x1FA && 2 * (unsigned __int64)v7 - 3 <= 0x1FA )
      {
        v8 = 2LL * v7 + 2;
        v9 = 2 * v6 + 2;
        ProcessHeap = GetProcessHeap();
        v11 = (char *)HeapAlloc(ProcessHeap, 8u, v8 + v9);
        if ( v11 )
        {
          lpMem = v11;
          qword_180028960 = &v11[v9];
          memcpy_0(v11, Src, v9);
          memcpy_0(qword_180028960, a2, v8);
          HIWORD(dword_180028948) = 2 * v6 + 2;
          LOWORD(dword_180028948) = 2 * v6;
          LOWORD(dword_180028958) = v8 - 2;
          HIWORD(dword_180028958) = v8;
          byte_180028938 = 1;
        }
      }
    }
    return RtlReleaseSRWLockExclusive(&qword_180028940);
  }
  return result;
}

```

## disassembly

```asm
0x180018ce0  push    rbx
0x180018ce2  push    rsi
0x180018ce3  push    rdi
0x180018ce4  push    r14
0x180018ce6  push    r15
0x180018ce8  sub     rsp, 20h
0x180018cec  mov     al, cs:byte_180028938
0x180018cf2  mov     rsi, rdx
0x180018cf5  mov     rdi, rcx
0x180018cf8  test    al, al
0x180018cfa  jnz     loc_180018E10
0x180018d00  lea     rcx, qword_180028940
0x180018d07  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180018d0d  mov     al, cs:byte_180028938
0x180018d13  test    al, al
0x180018d15  jnz     loc_180018E03
0x180018d1b  test    rdi, rdi
0x180018d1e  jnz     short loc_180018D24
0x180018d20  xor     eax, eax
0x180018d22  jmp     short loc_180018D32
0x180018d24  mov     edx, 0FFh; MaxCount
0x180018d29  mov     rcx, rdi; Source
0x180018d2c  call    cs:__imp_wcsnlen
0x180018d32  mov     ebx, eax
0x180018d34  test    rsi, rsi
0x180018d37  jnz     short loc_180018D3D
0x180018d39  xor     eax, eax
0x180018d3b  jmp     short loc_180018D4B
0x180018d3d  mov     edx, 0FFh; MaxCount
0x180018d42  mov     rcx, rsi; Source
0x180018d45  call    cs:__imp_wcsnlen
0x180018d4b  lea     rcx, ds:0FFFFFFFFFFFFFFFDh[rbx*2]
0x180018d53  mov     edx, 1FAh
0x180018d58  cmp     rcx, rdx
0x180018d5b  ja      loc_180018E03
0x180018d61  mov     ecx, eax
0x180018d63  lea     rax, ds:0FFFFFFFFFFFFFFFDh[rcx*2]
0x180018d6b  cmp     rax, rdx
0x180018d6e  ja      loc_180018E03
0x180018d74  lea     r15, ds:2[rcx*2]
0x180018d7c  lea     r14, ds:2[rbx*2]
0x180018d84  lea     rbx, [r15+r14]
0x180018d88  call    cs:__imp_GetProcessHeap
0x180018d8e  mov     r8, rbx; dwBytes
0x180018d91  mov     edx, 8; dwFlags
0x180018d96  mov     rcx, rax; hHeap
0x180018d99  call    cs:__imp_HeapAlloc
0x180018d9f  test    rax, rax
0x180018da2  jz      short loc_180018E03
0x180018da4  lea     rcx, [r14+rax]
0x180018da8  mov     cs:lpMem, rax
0x180018daf  mov     cs:qword_180028960, rcx
0x180018db6  mov     r8, r14; Size
0x180018db9  mov     rcx, rax; void *
0x180018dbc  mov     rdx, rdi; Src
0x180018dbf  call    memcpy_0
0x180018dc4  mov     rcx, cs:qword_180028960; void *
0x180018dcb  mov     r8, r15; Size
0x180018dce  mov     rdx, rsi; Src
0x180018dd1  call    memcpy_0
0x180018dd6  lea     eax, [r14-2]
0x180018dda  mov     word ptr cs:dword_180028948+2, r14w
0x180018de2  mov     word ptr cs:dword_180028948, ax
0x180018de9  lea     eax, [r15-2]
0x180018ded  mov     word ptr cs:dword_180028958, ax
0x180018df4  mov     word ptr cs:dword_180028958+2, r15w
0x180018dfc  mov     cs:byte_180028938, 1
0x180018e03  lea     rcx, qword_180028940
0x180018e0a  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180018e10  add     rsp, 20h
0x180018e14  pop     r15
0x180018e16  pop     r14
0x180018e18  pop     rdi
0x180018e19  pop     rsi
0x180018e1a  pop     rbx
0x180018e1b  retn
```
