# winrt::impl::precreate_hstring_on_heap(uint)

- ea: `0x140007a2c`
- end: `0x140007b1a`
- name: `?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z`
- size: `238`
- prototype: `struct winrt::impl::shared_hstring_header *__fastcall(winrt::impl *this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140007e80`

## callees

- `0x140002c0e`
- `0x140002d80`
- `0x140002e48`
- `0x140002e60`
- `0x140007a2c`

## pseudocode

```c
struct winrt::impl::shared_hstring_header *__fastcall winrt::impl::precreate_hstring_on_heap(winrt::impl *this)
{
  __int64 v1; // rbx
  SIZE_T v2; // rsi
  HANDLE ProcessHeap; // rax
  struct winrt::impl::shared_hstring_header *result; // rax
  const char *v5; // [rsp+20h] [rbp-38h] BYREF
  char v6; // [rsp+28h] [rbp-30h]
  int v7; // [rsp+29h] [rbp-2Fh]
  __int16 v8; // [rsp+2Dh] [rbp-2Bh]
  char v9; // [rsp+2Fh] [rbp-29h]
  void **pExceptionObject; // [rsp+30h] [rbp-28h] BYREF
  __int128 v11; // [rsp+38h] [rbp-20h]

  v1 = (unsigned int)this;
  v2 = 2LL * (unsigned int)this + 32;
  if ( v2 > 0xFFFFFFFF )
  {
    pExceptionObject = &std::exception::`vftable';
    v5 = "length";
    v6 = 1;
    v7 = 0;
    v8 = 0;
    v9 = 0;
    v11 = 0;
    o___std_exception_copy_0(&v5);
    pExceptionObject = &std::logic_error::`vftable';
    throw (std::invalid_argument *)&pExceptionObject;
  }
  ProcessHeap = WINRT_IMPL_GetProcessHeap();
  result = (struct winrt::impl::shared_hstring_header *)WINRT_IMPL_HeapAlloc(ProcessHeap, 0, v2);
  if ( !result )
  {
    *((_QWORD *)&v11 + 1) = 0;
    *(_QWORD *)&v11 = "bad allocation";
    pExceptionObject = &std::bad_alloc::`vftable';
    throw (std::bad_alloc *)&pExceptionObject;
  }
  *(_DWORD *)result = 0;
  *((_DWORD *)result + 1) = v1;
  *((_QWORD *)result + 2) = (char *)result + 28;
  _InterlockedExchange((volatile __int32 *)result + 6, 1);
  *((_WORD *)result + v1 + 14) = 0;
  return result;
}

```

## disassembly

```asm
0x140007a2c  push    rbp
0x140007a2e  push    rbx
0x140007a2f  push    rsi
0x140007a30  push    rdi
0x140007a31  mov     rbp, rsp
0x140007a34  sub     rsp, 58h
0x140007a38  mov     ebx, ecx
0x140007a3a  mov     eax, 0FFFFFFFFh
0x140007a3f  lea     rsi, ds:20h[rbx*2]
0x140007a47  cmp     rsi, rax
0x140007a4a  jbe     short loc_140007AA6
0x140007a4c  lea     rax, ??_7exception@std@@6B@; const std::exception::`vftable'
0x140007a53  xorps   xmm0, xmm0
0x140007a56  mov     [rbp+pExceptionObject], rax
0x140007a5a  lea     rdx, [rbp+var_20]
0x140007a5e  lea     rax, aLength; "length"
0x140007a65  mov     [rbp+var_38], rax
0x140007a69  lea     rcx, [rbp+var_38]
0x140007a6d  mov     eax, 1
0x140007a72  mov     [rbp+var_30], al
0x140007a75  xor     eax, eax
0x140007a77  mov     [rbp+var_2F], eax
0x140007a7a  mov     [rbp+var_2B], ax
0x140007a7e  mov     [rbp+var_29], al
0x140007a81  movups  [rbp+var_20], xmm0
0x140007a85  call    _o___std_exception_copy_0
0x140007a8a  lea     rax, ??_7logic_error@std@@6B@; const std::logic_error::`vftable'
0x140007a91  lea     rdx, _TI3?AVinvalid_argument@std@@; pThrowInfo
0x140007a98  mov     [rbp+pExceptionObject], rax
0x140007a9c  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x140007aa0  call    _CxxThrowException_0
0x140007aa6  call    WINRT_IMPL_GetProcessHeap
0x140007aab  mov     rcx, rax; hHeap
0x140007aae  mov     r8, rsi; dwBytes
0x140007ab1  xor     edx, edx; dwFlags
0x140007ab3  call    WINRT_IMPL_HeapAlloc
0x140007ab8  mov     rcx, rax
0x140007abb  test    rax, rax
0x140007abe  jnz     short loc_140007AEE
0x140007ac0  xorps   xmm0, xmm0
0x140007ac3  lea     rax, aBadAllocation; "bad allocation"
0x140007aca  movups  [rbp+var_20], xmm0
0x140007ace  mov     qword ptr [rbp+var_20], rax
0x140007ad2  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x140007ad9  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x140007ae0  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x140007ae4  mov     [rbp+pExceptionObject], rax
0x140007ae8  call    _CxxThrowException_0
0x140007aee  mov     dword ptr [rax], 0
0x140007af4  mov     [rax+4], ebx
0x140007af7  add     rax, 1Ch
0x140007afb  mov     [rcx+10h], rax
0x140007aff  mov     eax, 1
0x140007b04  xchg    eax, [rcx+18h]
0x140007b07  xor     eax, eax
0x140007b09  mov     [rcx+rbx*2+1Ch], ax
0x140007b0e  mov     rax, rcx
0x140007b11  add     rsp, 58h
0x140007b15  pop     rdi
0x140007b16  pop     rsi
0x140007b17  pop     rbx
0x140007b18  pop     rbp
0x140007b19  retn
```
