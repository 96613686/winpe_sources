# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x18000a9c4`
- end: `0x18000aa87`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `__int64 __fastcall(volatile signed __int32 **this, volatile signed __int32 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180009744`
- `0x18000abe0`

## callees

- `0x18000a9c4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a9ef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000aa19`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000aa53`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a9ef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000aa19`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000aa53`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a9fd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000aa61`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a9fd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000aa61`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000aa28`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000aa28`

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
0x18000a9c4  push    rbx
0x18000a9c6  push    rbp
0x18000a9c7  push    rsi
0x18000a9c8  push    rdi
0x18000a9c9  sub     rsp, 28h
0x18000a9cd  mov     rbp, rdx
0x18000a9d0  mov     rdi, rcx
0x18000a9d3  test    rdx, rdx
0x18000a9d6  jnz     short loc_18000AA19
0x18000a9d8  mov     rcx, [rcx]
0x18000a9db  test    rcx, rcx
0x18000a9de  jz      short loc_18000AA12
0x18000a9e0  or      eax, 0FFFFFFFFh
0x18000a9e3  lock xadd [rcx], eax
0x18000a9e7  cmp     eax, 1
0x18000a9ea  jnz     short loc_18000AA03
0x18000a9ec  mov     rbx, [rdi]
0x18000a9ef  call    cs:__imp_GetProcessHeap
0x18000a9f5  mov     r8, rbx; lpMem
0x18000a9f8  xor     edx, edx; dwFlags
0x18000a9fa  mov     rcx, rax; hHeap
0x18000a9fd  call    cs:__imp_HeapFree
0x18000aa03  mov     qword ptr [rdi], 0
0x18000aa0a  mov     qword ptr [rdi+8], 0
0x18000aa12  mov     eax, 1
0x18000aa17  jmp     short loc_18000AA7E
0x18000aa19  call    cs:__imp_GetProcessHeap
0x18000aa1f  lea     r8, [rbp+4]; dwBytes
0x18000aa23  xor     edx, edx; dwFlags
0x18000aa25  mov     rcx, rax; hHeap
0x18000aa28  call    cs:__imp_HeapAlloc
0x18000aa2e  mov     rsi, rax
0x18000aa31  test    rax, rax
0x18000aa34  jz      short loc_18000AA7E
0x18000aa36  mov     dword ptr [rax], 0
0x18000aa3c  mov     rcx, [rdi]
0x18000aa3f  test    rcx, rcx
0x18000aa42  jz      short loc_18000AA6F
0x18000aa44  or      eax, 0FFFFFFFFh
0x18000aa47  lock xadd [rcx], eax
0x18000aa4b  cmp     eax, 1
0x18000aa4e  jnz     short loc_18000AA67
0x18000aa50  mov     rbx, [rdi]
0x18000aa53  call    cs:__imp_GetProcessHeap
0x18000aa59  mov     r8, rbx; lpMem
0x18000aa5c  xor     edx, edx; dwFlags
0x18000aa5e  mov     rcx, rax; hHeap
0x18000aa61  call    cs:__imp_HeapFree
0x18000aa67  mov     qword ptr [rdi+8], 0
0x18000aa6f  mov     [rdi], rsi
0x18000aa72  mov     eax, 1
0x18000aa77  mov     [rdi+8], rbp
0x18000aa7b  lock add [rsi], eax
0x18000aa7e  add     rsp, 28h
0x18000aa82  pop     rdi
0x18000aa83  pop     rsi
0x18000aa84  pop     rbp
0x18000aa85  pop     rbx
0x18000aa86  retn
```
