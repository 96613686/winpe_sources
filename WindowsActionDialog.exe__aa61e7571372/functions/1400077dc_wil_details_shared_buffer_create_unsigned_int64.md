# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x1400077dc`
- end: `0x14000789f`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `bool __fastcall(wil::details::shared_buffer *__hidden this, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140006844`
- `0x1400078c0`

## callees

- `0x1400077dc`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140007815`
- `KERNEL32!HeapFree` at `0x140007879`
- `KERNEL32!HeapFree` at `0x140007815`
- `KERNEL32!HeapFree` at `0x140007879`
- `KERNEL32!GetProcessHeap` at `0x140007807`
- `KERNEL32!GetProcessHeap` at `0x140007831`
- `KERNEL32!GetProcessHeap` at `0x14000786b`
- `KERNEL32!GetProcessHeap` at `0x140007807`
- `KERNEL32!GetProcessHeap` at `0x140007831`
- `KERNEL32!GetProcessHeap` at `0x14000786b`
- `KERNEL32!HeapAlloc` at `0x140007840`
- `KERNEL32!HeapAlloc` at `0x140007840`

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
0x1400077dc  push    rbx
0x1400077de  push    rbp
0x1400077df  push    rsi
0x1400077e0  push    rdi
0x1400077e1  sub     rsp, 28h
0x1400077e5  mov     rbp, rdx
0x1400077e8  mov     rdi, rcx
0x1400077eb  test    rdx, rdx
0x1400077ee  jnz     short loc_140007831
0x1400077f0  mov     rcx, [rcx]
0x1400077f3  test    rcx, rcx
0x1400077f6  jz      short loc_14000782A
0x1400077f8  or      eax, 0FFFFFFFFh
0x1400077fb  lock xadd [rcx], eax
0x1400077ff  cmp     eax, 1
0x140007802  jnz     short loc_14000781B
0x140007804  mov     rbx, [rdi]
0x140007807  call    cs:__imp_GetProcessHeap
0x14000780d  mov     r8, rbx; lpMem
0x140007810  xor     edx, edx; dwFlags
0x140007812  mov     rcx, rax; hHeap
0x140007815  call    cs:__imp_HeapFree
0x14000781b  mov     qword ptr [rdi], 0
0x140007822  mov     qword ptr [rdi+8], 0
0x14000782a  mov     eax, 1
0x14000782f  jmp     short loc_140007896
0x140007831  call    cs:__imp_GetProcessHeap
0x140007837  lea     r8, [rbp+4]; dwBytes
0x14000783b  xor     edx, edx; dwFlags
0x14000783d  mov     rcx, rax; hHeap
0x140007840  call    cs:__imp_HeapAlloc
0x140007846  mov     rsi, rax
0x140007849  test    rax, rax
0x14000784c  jz      short loc_140007896
0x14000784e  mov     dword ptr [rax], 0
0x140007854  mov     rcx, [rdi]
0x140007857  test    rcx, rcx
0x14000785a  jz      short loc_140007887
0x14000785c  or      eax, 0FFFFFFFFh
0x14000785f  lock xadd [rcx], eax
0x140007863  cmp     eax, 1
0x140007866  jnz     short loc_14000787F
0x140007868  mov     rbx, [rdi]
0x14000786b  call    cs:__imp_GetProcessHeap
0x140007871  mov     r8, rbx; lpMem
0x140007874  xor     edx, edx; dwFlags
0x140007876  mov     rcx, rax; hHeap
0x140007879  call    cs:__imp_HeapFree
0x14000787f  mov     qword ptr [rdi+8], 0
0x140007887  mov     [rdi], rsi
0x14000788a  mov     eax, 1
0x14000788f  mov     [rdi+8], rbp
0x140007893  lock add [rsi], eax
0x140007896  add     rsp, 28h
0x14000789a  pop     rdi
0x14000789b  pop     rsi
0x14000789c  pop     rbp
0x14000789d  pop     rbx
0x14000789e  retn
```
