# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x18000a874`
- end: `0x18000a937`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `__int64 __fastcall(volatile signed __int32 **this, volatile signed __int32 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800095b4`
- `0x18000aa40`

## callees

- `0x18000a874`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a8ad`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a911`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a8ad`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a911`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a89f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a8c9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a903`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a89f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a8c9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a903`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a8d8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a8d8`

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
0x18000a874  push    rbx
0x18000a876  push    rbp
0x18000a877  push    rsi
0x18000a878  push    rdi
0x18000a879  sub     rsp, 28h
0x18000a87d  mov     rbp, rdx
0x18000a880  mov     rdi, rcx
0x18000a883  test    rdx, rdx
0x18000a886  jnz     short loc_18000A8C9
0x18000a888  mov     rcx, [rcx]
0x18000a88b  test    rcx, rcx
0x18000a88e  jz      short loc_18000A8C2
0x18000a890  or      eax, 0FFFFFFFFh
0x18000a893  lock xadd [rcx], eax
0x18000a897  cmp     eax, 1
0x18000a89a  jnz     short loc_18000A8B3
0x18000a89c  mov     rbx, [rdi]
0x18000a89f  call    cs:__imp_GetProcessHeap
0x18000a8a5  mov     r8, rbx; lpMem
0x18000a8a8  xor     edx, edx; dwFlags
0x18000a8aa  mov     rcx, rax; hHeap
0x18000a8ad  call    cs:__imp_HeapFree
0x18000a8b3  mov     qword ptr [rdi], 0
0x18000a8ba  mov     qword ptr [rdi+8], 0
0x18000a8c2  mov     eax, 1
0x18000a8c7  jmp     short loc_18000A92E
0x18000a8c9  call    cs:__imp_GetProcessHeap
0x18000a8cf  lea     r8, [rbp+4]; dwBytes
0x18000a8d3  xor     edx, edx; dwFlags
0x18000a8d5  mov     rcx, rax; hHeap
0x18000a8d8  call    cs:__imp_HeapAlloc
0x18000a8de  mov     rsi, rax
0x18000a8e1  test    rax, rax
0x18000a8e4  jz      short loc_18000A92E
0x18000a8e6  mov     dword ptr [rax], 0
0x18000a8ec  mov     rcx, [rdi]
0x18000a8ef  test    rcx, rcx
0x18000a8f2  jz      short loc_18000A91F
0x18000a8f4  or      eax, 0FFFFFFFFh
0x18000a8f7  lock xadd [rcx], eax
0x18000a8fb  cmp     eax, 1
0x18000a8fe  jnz     short loc_18000A917
0x18000a900  mov     rbx, [rdi]
0x18000a903  call    cs:__imp_GetProcessHeap
0x18000a909  mov     r8, rbx; lpMem
0x18000a90c  xor     edx, edx; dwFlags
0x18000a90e  mov     rcx, rax; hHeap
0x18000a911  call    cs:__imp_HeapFree
0x18000a917  mov     qword ptr [rdi+8], 0
0x18000a91f  mov     [rdi], rsi
0x18000a922  mov     eax, 1
0x18000a927  mov     [rdi+8], rbp
0x18000a92b  lock add [rsi], eax
0x18000a92e  add     rsp, 28h
0x18000a932  pop     rdi
0x18000a933  pop     rsi
0x18000a934  pop     rbp
0x18000a935  pop     rbx
0x18000a936  retn
```
