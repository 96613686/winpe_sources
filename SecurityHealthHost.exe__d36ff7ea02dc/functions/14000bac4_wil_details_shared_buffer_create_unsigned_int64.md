# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x14000bac4`
- end: `0x14000bb87`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `__int64 __fastcall(volatile signed __int32 **this, volatile signed __int32 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14000a8e8`
- `0x14000bc80`

## callees

- `0x14000bac4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000bb28`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000bb28`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000baef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000bb19`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000bb53`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000baef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000bb19`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000bb53`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000bafd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000bb61`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000bafd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000bb61`

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
0x14000bac4  push    rbx
0x14000bac6  push    rbp
0x14000bac7  push    rsi
0x14000bac8  push    rdi
0x14000bac9  sub     rsp, 28h
0x14000bacd  mov     rbp, rdx
0x14000bad0  mov     rdi, rcx
0x14000bad3  test    rdx, rdx
0x14000bad6  jnz     short loc_14000BB19
0x14000bad8  mov     rcx, [rcx]
0x14000badb  test    rcx, rcx
0x14000bade  jz      short loc_14000BB12
0x14000bae0  or      eax, 0FFFFFFFFh
0x14000bae3  lock xadd [rcx], eax
0x14000bae7  cmp     eax, 1
0x14000baea  jnz     short loc_14000BB03
0x14000baec  mov     rbx, [rdi]
0x14000baef  call    cs:__imp_GetProcessHeap
0x14000baf5  mov     r8, rbx; lpMem
0x14000baf8  xor     edx, edx; dwFlags
0x14000bafa  mov     rcx, rax; hHeap
0x14000bafd  call    cs:__imp_HeapFree
0x14000bb03  mov     qword ptr [rdi], 0
0x14000bb0a  mov     qword ptr [rdi+8], 0
0x14000bb12  mov     eax, 1
0x14000bb17  jmp     short loc_14000BB7E
0x14000bb19  call    cs:__imp_GetProcessHeap
0x14000bb1f  lea     r8, [rbp+4]; dwBytes
0x14000bb23  xor     edx, edx; dwFlags
0x14000bb25  mov     rcx, rax; hHeap
0x14000bb28  call    cs:__imp_HeapAlloc
0x14000bb2e  mov     rsi, rax
0x14000bb31  test    rax, rax
0x14000bb34  jz      short loc_14000BB7E
0x14000bb36  mov     dword ptr [rax], 0
0x14000bb3c  mov     rcx, [rdi]
0x14000bb3f  test    rcx, rcx
0x14000bb42  jz      short loc_14000BB6F
0x14000bb44  or      eax, 0FFFFFFFFh
0x14000bb47  lock xadd [rcx], eax
0x14000bb4b  cmp     eax, 1
0x14000bb4e  jnz     short loc_14000BB67
0x14000bb50  mov     rbx, [rdi]
0x14000bb53  call    cs:__imp_GetProcessHeap
0x14000bb59  mov     r8, rbx; lpMem
0x14000bb5c  xor     edx, edx; dwFlags
0x14000bb5e  mov     rcx, rax; hHeap
0x14000bb61  call    cs:__imp_HeapFree
0x14000bb67  mov     qword ptr [rdi+8], 0
0x14000bb6f  mov     [rdi], rsi
0x14000bb72  mov     eax, 1
0x14000bb77  mov     [rdi+8], rbp
0x14000bb7b  lock add [rsi], eax
0x14000bb7e  add     rsp, 28h
0x14000bb82  pop     rdi
0x14000bb83  pop     rsi
0x14000bb84  pop     rbp
0x14000bb85  pop     rbx
0x14000bb86  retn
```
