# winrt::impl::precreate_hstring_on_heap(uint)

- ea: `0x18001c4e8`
- end: `0x18001c5b5`
- name: `?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z`
- size: `205`
- prototype: `struct winrt::impl::shared_hstring_header *__fastcall(winrt::impl *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18001b3b0`

## callees

- `0x180002154`
- `0x1800021cc`
- `0x1800021d8`
- `0x1800116d8`
- `0x18001c4e8`

## pseudocode

```c
struct winrt::impl::shared_hstring_header *__fastcall winrt::impl::precreate_hstring_on_heap(winrt::impl *this)
{
  __int64 v1; // rbx
  SIZE_T v2; // rsi
  HANDLE ProcessHeap; // rax
  struct winrt::impl::shared_hstring_header *result; // rax
  _QWORD pExceptionObject[5]; // [rsp+20h] [rbp-28h] BYREF

  v1 = (unsigned int)this;
  v2 = 2LL * (unsigned int)this + 32;
  if ( v2 > 0xFFFFFFFF )
  {
    std::exception::exception((std::exception *)pExceptionObject, "length");
    pExceptionObject[0] = &std::logic_error::`vftable';
    throw (std::invalid_argument *)pExceptionObject;
  }
  ProcessHeap = WINRT_IMPL_GetProcessHeap();
  result = (struct winrt::impl::shared_hstring_header *)WINRT_IMPL_HeapAlloc(ProcessHeap, 0, v2);
  if ( !result )
  {
    pExceptionObject[2] = 0;
    pExceptionObject[1] = "bad allocation";
    pExceptionObject[0] = &std::bad_alloc::`vftable';
    throw (std::bad_alloc *)pExceptionObject;
  }
  *((_DWORD *)result + 1) = v1;
  *(_DWORD *)result = 0;
  *((_QWORD *)result + 2) = (char *)result + 28;
  _InterlockedExchange((volatile __int32 *)result + 6, 1);
  *((_WORD *)result + v1 + 14) = 0;
  return result;
}

```

## disassembly

```asm
0x18001c4e8  mov     [rsp+arg_0], rbx
0x18001c4ed  mov     [rsp+arg_8], rsi
0x18001c4f2  push    rdi
0x18001c4f3  sub     rsp, 40h
0x18001c4f7  mov     ebx, ecx
0x18001c4f9  mov     eax, 0FFFFFFFFh
0x18001c4fe  lea     rsi, ds:20h[rbx*2]
0x18001c506  cmp     rsi, rax
0x18001c509  jbe     short loc_18001C53A
0x18001c50b  lea     rdx, aLength_0; "length"
0x18001c512  lea     rcx, [rsp+48h+pExceptionObject]; this
0x18001c517  call    ??0exception@std@@QEAA@QEBD@Z; std::exception::exception(char const * const)
0x18001c51c  lea     rax, ??_7logic_error@std@@6B@; const std::logic_error::`vftable'
0x18001c523  lea     rdx, _TI3?AVinvalid_argument@std@@; pThrowInfo
0x18001c52a  mov     [rsp+48h+pExceptionObject], rax
0x18001c52f  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18001c534  call    _CxxThrowException_0
0x18001c53a  call    WINRT_IMPL_GetProcessHeap
0x18001c53f  mov     rcx, rax; hHeap
0x18001c542  mov     r8, rsi; dwBytes
0x18001c545  xor     edx, edx; dwFlags
0x18001c547  call    WINRT_IMPL_HeapAlloc
0x18001c54c  xor     ecx, ecx
0x18001c54e  mov     rdx, rax
0x18001c551  test    rax, rax
0x18001c554  jnz     short loc_18001C588
0x18001c556  xorps   xmm0, xmm0
0x18001c559  lea     rax, aBadAllocation; "bad allocation"
0x18001c560  movups  [rsp+48h+var_20], xmm0
0x18001c565  mov     qword ptr [rsp+48h+var_20], rax
0x18001c56a  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18001c571  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x18001c578  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18001c57d  mov     [rsp+48h+pExceptionObject], rax
0x18001c582  call    _CxxThrowException_0
0x18001c588  mov     rsi, [rsp+48h+arg_8]
0x18001c58d  mov     [rax+4], ebx
0x18001c590  mov     [rax], ecx
0x18001c592  add     rax, 1Ch
0x18001c596  mov     [rdx+10h], rax
0x18001c59a  mov     eax, 1
0x18001c59f  xchg    eax, [rdx+18h]
0x18001c5a2  mov     [rdx+rbx*2+1Ch], cx
0x18001c5a7  mov     rax, rdx
0x18001c5aa  mov     rbx, [rsp+48h+arg_0]
0x18001c5af  add     rsp, 40h
0x18001c5b3  pop     rdi
0x18001c5b4  retn
```
