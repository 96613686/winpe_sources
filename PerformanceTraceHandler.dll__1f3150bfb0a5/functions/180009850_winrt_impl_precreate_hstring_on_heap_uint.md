# winrt::impl::precreate_hstring_on_heap(uint)

- ea: `0x180009850`
- end: `0x18000993e`
- name: `?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z`
- size: `238`
- prototype: `struct winrt::impl::shared_hstring_header *__fastcall(winrt::impl *this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180009654`

## callees

- `0x180003606`
- `0x180003734`
- `0x180003859`
- `0x180003871`
- `0x180009850`

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
0x180009850  push    rbp
0x180009852  push    rbx
0x180009853  push    rsi
0x180009854  push    rdi
0x180009855  mov     rbp, rsp
0x180009858  sub     rsp, 58h
0x18000985c  mov     ebx, ecx
0x18000985e  mov     eax, 0FFFFFFFFh
0x180009863  lea     rsi, ds:20h[rbx*2]
0x18000986b  cmp     rsi, rax
0x18000986e  jbe     short loc_1800098CA
0x180009870  lea     rax, ??_7exception@std@@6B@; const std::exception::`vftable'
0x180009877  xorps   xmm0, xmm0
0x18000987a  mov     [rbp+pExceptionObject], rax
0x18000987e  lea     rdx, [rbp+var_20]
0x180009882  lea     rax, aLength; "length"
0x180009889  mov     [rbp+var_38], rax
0x18000988d  lea     rcx, [rbp+var_38]
0x180009891  mov     eax, 1
0x180009896  mov     [rbp+var_30], al
0x180009899  xor     eax, eax
0x18000989b  mov     [rbp+var_2F], eax
0x18000989e  mov     [rbp+var_2B], ax
0x1800098a2  mov     [rbp+var_29], al
0x1800098a5  movups  [rbp+var_20], xmm0
0x1800098a9  call    _o___std_exception_copy_0
0x1800098ae  lea     rax, ??_7logic_error@std@@6B@; const std::logic_error::`vftable'
0x1800098b5  lea     rdx, _TI3?AVinvalid_argument@std@@; pThrowInfo
0x1800098bc  mov     [rbp+pExceptionObject], rax
0x1800098c0  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800098c4  call    _CxxThrowException_0
0x1800098ca  call    WINRT_IMPL_GetProcessHeap
0x1800098cf  mov     rcx, rax; hHeap
0x1800098d2  mov     r8, rsi; dwBytes
0x1800098d5  xor     edx, edx; dwFlags
0x1800098d7  call    WINRT_IMPL_HeapAlloc
0x1800098dc  mov     rcx, rax
0x1800098df  test    rax, rax
0x1800098e2  jnz     short loc_180009912
0x1800098e4  xorps   xmm0, xmm0
0x1800098e7  lea     rax, aBadAllocation; "bad allocation"
0x1800098ee  movups  [rbp+var_20], xmm0
0x1800098f2  mov     qword ptr [rbp+var_20], rax
0x1800098f6  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x1800098fd  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x180009904  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180009908  mov     [rbp+pExceptionObject], rax
0x18000990c  call    _CxxThrowException_0
0x180009912  mov     dword ptr [rax], 0
0x180009918  mov     [rax+4], ebx
0x18000991b  add     rax, 1Ch
0x18000991f  mov     [rcx+10h], rax
0x180009923  mov     eax, 1
0x180009928  xchg    eax, [rcx+18h]
0x18000992b  xor     eax, eax
0x18000992d  mov     [rcx+rbx*2+1Ch], ax
0x180009932  mov     rax, rcx
0x180009935  add     rsp, 58h
0x180009939  pop     rdi
0x18000993a  pop     rsi
0x18000993b  pop     rbx
0x18000993c  pop     rbp
0x18000993d  retn
```
