# winrt::impl::precreate_hstring_on_heap(uint)

- ea: `0x180007340`
- end: `0x18000742e`
- name: `?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z`
- size: `238`
- prototype: `struct winrt::impl::shared_hstring_header *__fastcall(winrt::impl *this)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180007164`
- `0x1800095d0`

## callees

- `0x180002a66`
- `0x180002b84`
- `0x180002c20`
- `0x180002c38`
- `0x180007340`

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
  __int128 v11; // [rsp+38h] [rbp-20h] BYREF

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
    o___std_exception_copy_0(&v5, &v11);
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
0x180007340  push    rbp
0x180007342  push    rbx
0x180007343  push    rsi
0x180007344  push    rdi
0x180007345  mov     rbp, rsp
0x180007348  sub     rsp, 58h
0x18000734c  mov     ebx, ecx
0x18000734e  mov     eax, 0FFFFFFFFh
0x180007353  lea     rsi, ds:20h[rbx*2]
0x18000735b  cmp     rsi, rax
0x18000735e  jbe     short loc_1800073BA
0x180007360  lea     rax, ??_7exception@std@@6B@; const std::exception::`vftable'
0x180007367  xorps   xmm0, xmm0
0x18000736a  mov     [rbp+pExceptionObject], rax
0x18000736e  lea     rdx, [rbp+var_20]
0x180007372  lea     rax, aLength; "length"
0x180007379  mov     [rbp+var_38], rax
0x18000737d  lea     rcx, [rbp+var_38]
0x180007381  mov     eax, 1
0x180007386  mov     [rbp+var_30], al
0x180007389  xor     eax, eax
0x18000738b  mov     [rbp+var_2F], eax
0x18000738e  mov     [rbp+var_2B], ax
0x180007392  mov     [rbp+var_29], al
0x180007395  movups  [rbp+var_20], xmm0
0x180007399  call    _o___std_exception_copy_0
0x18000739e  lea     rax, ??_7logic_error@std@@6B@; const std::logic_error::`vftable'
0x1800073a5  lea     rdx, _TI3?AVinvalid_argument@std@@; pThrowInfo
0x1800073ac  mov     [rbp+pExceptionObject], rax
0x1800073b0  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800073b4  call    _CxxThrowException_0
0x1800073ba  call    WINRT_IMPL_GetProcessHeap
0x1800073bf  mov     rcx, rax; hHeap
0x1800073c2  mov     r8, rsi; dwBytes
0x1800073c5  xor     edx, edx; dwFlags
0x1800073c7  call    WINRT_IMPL_HeapAlloc
0x1800073cc  mov     rcx, rax
0x1800073cf  test    rax, rax
0x1800073d2  jnz     short loc_180007402
0x1800073d4  xorps   xmm0, xmm0
0x1800073d7  lea     rax, aBadAllocation; "bad allocation"
0x1800073de  movups  [rbp+var_20], xmm0
0x1800073e2  mov     qword ptr [rbp+var_20], rax
0x1800073e6  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x1800073ed  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x1800073f4  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800073f8  mov     [rbp+pExceptionObject], rax
0x1800073fc  call    _CxxThrowException_0
0x180007402  mov     dword ptr [rax], 0
0x180007408  mov     [rax+4], ebx
0x18000740b  add     rax, 1Ch
0x18000740f  mov     [rcx+10h], rax
0x180007413  mov     eax, 1
0x180007418  xchg    eax, [rcx+18h]
0x18000741b  xor     eax, eax
0x18000741d  mov     [rcx+rbx*2+1Ch], ax
0x180007422  mov     rax, rcx
0x180007425  add     rsp, 58h
0x180007429  pop     rdi
0x18000742a  pop     rsi
0x18000742b  pop     rbx
0x18000742c  pop     rbp
0x18000742d  retn
```
