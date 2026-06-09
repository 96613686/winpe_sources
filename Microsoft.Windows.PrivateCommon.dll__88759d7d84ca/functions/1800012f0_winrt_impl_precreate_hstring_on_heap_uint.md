# winrt::impl::precreate_hstring_on_heap(uint)

- ea: `0x1800012f0`
- end: `0x18000139a`
- name: `?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z`
- size: `170`
- prototype: `struct winrt::impl::shared_hstring_header *__fastcall(winrt::impl *this, const char *)`
- caller_count: `5`
- callee_count: `6`
- tags: ``

## callers

- `0x1800013a0`
- `0x180001530`
- `0x18000c514`
- `0x18000c63a`
- `0x18000c760`

## callees

- `0x180001160`
- `0x1800011f0`
- `0x1800012f0`
- `0x18000725c`
- `0x180007262`
- `0x180008e5c`

## pseudocode

```c
struct winrt::impl::shared_hstring_header *__fastcall winrt::impl::precreate_hstring_on_heap(
        winrt::impl *this,
        const char *a2)
{
  __int64 v2; // rbx
  SIZE_T v3; // rsi
  HANDLE ProcessHeap; // rax
  struct winrt::impl::shared_hstring_header *result; // rax
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-28h] BYREF

  v2 = (unsigned int)this;
  v3 = 2LL * (unsigned int)this + 32;
  if ( v3 > 0xFFFFFFFF )
  {
    std::invalid_argument::invalid_argument((std::invalid_argument *)pExceptionObject, a2);
    throw (std::invalid_argument *)pExceptionObject;
  }
  _mm_lfence();
  ProcessHeap = WINRT_IMPL_GetProcessHeap();
  result = (struct winrt::impl::shared_hstring_header *)WINRT_IMPL_HeapAlloc(ProcessHeap, 0, v3);
  if ( !result )
  {
    std::bad_alloc::bad_alloc((std::bad_alloc *)pExceptionObject);
    throw (std::bad_alloc *)pExceptionObject;
  }
  _mm_lfence();
  *((_DWORD *)result + 1) = v2;
  *(_DWORD *)result = 0;
  *((_QWORD *)result + 2) = (char *)result + 28;
  _InterlockedExchange((volatile __int32 *)result + 6, 1);
  *((_WORD *)result + v2 + 14) = 0;
  return result;
}

```

## disassembly

```asm
0x1800012f0  mov     [rsp+arg_8], rbx
0x1800012f5  mov     [rsp+arg_10], rsi
0x1800012fa  push    rdi
0x1800012fb  sub     rsp, 40h
0x1800012ff  mov     ebx, ecx
0x180001301  mov     eax, 0FFFFFFFFh
0x180001306  lea     rsi, ds:20h[rbx*2]
0x18000130e  cmp     rsi, rax
0x180001311  ja      short loc_18000137E
0x180001313  lfence
0x180001316  call    WINRT_IMPL_GetProcessHeap
0x18000131b  mov     rcx, rax; hHeap
0x18000131e  mov     r8, rsi; dwBytes
0x180001321  xor     edx, edx; dwFlags
0x180001323  call    WINRT_IMPL_HeapAlloc
0x180001328  mov     rcx, rax
0x18000132b  test    rax, rax
0x18000132e  jz      short loc_180001362
0x180001330  lfence
0x180001333  mov     rsi, [rsp+48h+arg_10]
0x180001338  xor     edx, edx
0x18000133a  mov     [rax+4], ebx
0x18000133d  mov     [rax], edx
0x18000133f  add     rax, 1Ch
0x180001343  mov     [rcx+10h], rax
0x180001347  mov     eax, 1
0x18000134c  xchg    eax, [rcx+18h]
0x18000134f  mov     [rcx+rbx*2+1Ch], dx
0x180001354  mov     rax, rcx
0x180001357  mov     rbx, [rsp+48h+arg_8]
0x18000135c  add     rsp, 40h
0x180001360  pop     rdi
0x180001361  retn
0x180001362  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180001367  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x18000136c  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180001373  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180001378  call    _CxxThrowException
0x18000137e  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180001383  call    ??0invalid_argument@std@@QEAA@PEBD@Z; std::invalid_argument::invalid_argument(char const *)
0x180001388  lea     rdx, _TI3?AVinvalid_argument@std@@; pThrowInfo
0x18000138f  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180001394  call    _CxxThrowException
```
