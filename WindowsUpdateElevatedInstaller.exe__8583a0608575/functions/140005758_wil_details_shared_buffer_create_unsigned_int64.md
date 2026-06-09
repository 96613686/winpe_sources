# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x140005758`
- end: `0x14000581b`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `__int64 __fastcall(volatile signed __int32 **this, volatile signed __int32 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140004b90`
- `0x140005830`

## callees

- `0x140005758`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140005791`
- `KERNEL32!HeapFree` at `0x1400057f5`
- `KERNEL32!HeapFree` at `0x140005791`
- `KERNEL32!HeapFree` at `0x1400057f5`
- `KERNEL32!HeapAlloc` at `0x1400057bc`
- `KERNEL32!HeapAlloc` at `0x1400057bc`
- `KERNEL32!GetProcessHeap` at `0x140005783`
- `KERNEL32!GetProcessHeap` at `0x1400057ad`
- `KERNEL32!GetProcessHeap` at `0x1400057e7`
- `KERNEL32!GetProcessHeap` at `0x140005783`
- `KERNEL32!GetProcessHeap` at `0x1400057ad`
- `KERNEL32!GetProcessHeap` at `0x1400057e7`

## pseudocode

```c
__int64 __fastcall wil::details::shared_buffer::create(volatile signed __int32 **this, volatile signed __int32 *a2)
{
  volatile signed __int32 *v4; // rcx
  volatile signed __int32 *v5; // rbx
  HANDLE v6; // rax
  __int64 result; // rax
  HANDLE ProcessHeap; // rax
  volatile signed __int32 *v9; // rsi
  volatile signed __int32 *v10; // rbx
  HANDLE v11; // rax

  if ( a2 )
  {
    ProcessHeap = GetProcessHeap();
    result = (__int64)HeapAlloc(ProcessHeap, 0, (SIZE_T)(a2 + 1));
    v9 = (volatile signed __int32 *)result;
    if ( result )
    {
      *(_DWORD *)result = 0;
      if ( *this )
      {
        if ( _InterlockedExchangeAdd(*this, 0xFFFFFFFF) == 1 )
        {
          v10 = *this;
          v11 = GetProcessHeap();
          HeapFree(v11, 0, (LPVOID)v10);
        }
        this[1] = 0;
      }
      *this = v9;
      result = 1;
      this[1] = a2;
      _InterlockedAdd(v9, 1u);
    }
  }
  else
  {
    v4 = *this;
    if ( v4 )
    {
      if ( _InterlockedExchangeAdd(v4, 0xFFFFFFFF) == 1 )
      {
        v5 = *this;
        v6 = GetProcessHeap();
        HeapFree(v6, 0, (LPVOID)v5);
      }
      *this = 0;
      this[1] = 0;
    }
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x140005758  push    rbx
0x14000575a  push    rbp
0x14000575b  push    rsi
0x14000575c  push    rdi
0x14000575d  sub     rsp, 28h
0x140005761  mov     rbp, rdx
0x140005764  mov     rdi, rcx
0x140005767  test    rdx, rdx
0x14000576a  jnz     short loc_1400057AD
0x14000576c  mov     rcx, [rcx]
0x14000576f  test    rcx, rcx
0x140005772  jz      short loc_1400057A6
0x140005774  or      eax, 0FFFFFFFFh
0x140005777  lock xadd [rcx], eax
0x14000577b  cmp     eax, 1
0x14000577e  jnz     short loc_140005797
0x140005780  mov     rbx, [rdi]
0x140005783  call    cs:__imp_GetProcessHeap
0x140005789  mov     r8, rbx; lpMem
0x14000578c  xor     edx, edx; dwFlags
0x14000578e  mov     rcx, rax; hHeap
0x140005791  call    cs:__imp_HeapFree
0x140005797  mov     qword ptr [rdi], 0
0x14000579e  mov     qword ptr [rdi+8], 0
0x1400057a6  mov     eax, 1
0x1400057ab  jmp     short loc_140005812
0x1400057ad  call    cs:__imp_GetProcessHeap
0x1400057b3  lea     r8, [rbp+4]; dwBytes
0x1400057b7  xor     edx, edx; dwFlags
0x1400057b9  mov     rcx, rax; hHeap
0x1400057bc  call    cs:__imp_HeapAlloc
0x1400057c2  mov     rsi, rax
0x1400057c5  test    rax, rax
0x1400057c8  jz      short loc_140005812
0x1400057ca  mov     dword ptr [rax], 0
0x1400057d0  mov     rcx, [rdi]
0x1400057d3  test    rcx, rcx
0x1400057d6  jz      short loc_140005803
0x1400057d8  or      eax, 0FFFFFFFFh
0x1400057db  lock xadd [rcx], eax
0x1400057df  cmp     eax, 1
0x1400057e2  jnz     short loc_1400057FB
0x1400057e4  mov     rbx, [rdi]
0x1400057e7  call    cs:__imp_GetProcessHeap
0x1400057ed  mov     r8, rbx; lpMem
0x1400057f0  xor     edx, edx; dwFlags
0x1400057f2  mov     rcx, rax; hHeap
0x1400057f5  call    cs:__imp_HeapFree
0x1400057fb  mov     qword ptr [rdi+8], 0
0x140005803  mov     [rdi], rsi
0x140005806  mov     eax, 1
0x14000580b  mov     [rdi+8], rbp
0x14000580f  lock add [rsi], eax
0x140005812  add     rsp, 28h
0x140005816  pop     rdi
0x140005817  pop     rsi
0x140005818  pop     rbp
0x140005819  pop     rbx
0x14000581a  retn
```
