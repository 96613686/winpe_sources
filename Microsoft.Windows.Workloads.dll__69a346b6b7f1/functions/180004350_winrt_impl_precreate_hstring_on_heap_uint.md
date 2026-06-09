# winrt::impl::precreate_hstring_on_heap(uint)

- ea: `0x180004350`
- end: `0x180004401`
- name: `?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z`
- size: `177`
- prototype: `struct winrt::impl::shared_hstring_header *__fastcall(winrt::impl *this)`
- caller_count: `19`
- callee_count: `6`
- tags: ``

## callers

- `0x180004590`
- `0x180007a20`
- `0x18000c3c0`
- `0x18000d640`
- `0x18000efb0`
- `0x1800134c0`
- `0x1800139b0`
- `0x1800157c0`
- `0x180019180`
- `0x180024700`
- `0x1800282f0`
- `0x180029500`
- `0x18002c740`
- `0x18002cca0`
- `0x18002e220`
- `0x18003a020`
- `0x18003da54`
- `0x18003db7a`
- `0x18003dca0`

## callees

- `0x180004190`
- `0x180004280`
- `0x180004350`
- `0x180030aeb`
- `0x180030afd`
- `0x180036f4c`

## pseudocode

```c
struct winrt::impl::shared_hstring_header *__fastcall winrt::impl::precreate_hstring_on_heap(winrt::impl *this)
{
  __int64 v1; // rbx
  SIZE_T v2; // rsi
  HANDLE ProcessHeap; // rax
  struct winrt::impl::shared_hstring_header *result; // rax
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-28h] BYREF

  v1 = (unsigned int)this;
  v2 = 2LL * (unsigned int)this + 32;
  if ( v2 > 0xFFFFFFFF )
  {
    std::invalid_argument::invalid_argument((std::invalid_argument *)pExceptionObject, "length");
    throw (std::invalid_argument *)pExceptionObject;
  }
  _mm_lfence();
  ProcessHeap = WINRT_IMPL_GetProcessHeap();
  result = (struct winrt::impl::shared_hstring_header *)WINRT_IMPL_HeapAlloc(ProcessHeap, 0, v2);
  if ( !result )
  {
    std::bad_alloc::bad_alloc((std::bad_alloc *)pExceptionObject);
    throw (std::bad_alloc *)pExceptionObject;
  }
  _mm_lfence();
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
0x180004350  mov     [rsp+arg_8], rbx
0x180004355  mov     [rsp+arg_10], rsi
0x18000435a  push    rdi
0x18000435b  sub     rsp, 40h
0x18000435f  mov     ebx, ecx
0x180004361  mov     eax, 0FFFFFFFFh
0x180004366  lea     rsi, ds:20h[rbx*2]
0x18000436e  cmp     rsi, rax
0x180004371  ja      short loc_1800043DE
0x180004373  lfence
0x180004376  call    WINRT_IMPL_GetProcessHeap
0x18000437b  mov     rcx, rax; hHeap
0x18000437e  mov     r8, rsi; dwBytes
0x180004381  xor     edx, edx; dwFlags
0x180004383  call    WINRT_IMPL_HeapAlloc
0x180004388  mov     rcx, rax
0x18000438b  test    rax, rax
0x18000438e  jz      short loc_1800043C2
0x180004390  lfence
0x180004393  mov     rsi, [rsp+48h+arg_10]
0x180004398  xor     edx, edx
0x18000439a  mov     [rax+4], ebx
0x18000439d  mov     [rax], edx
0x18000439f  add     rax, 1Ch
0x1800043a3  mov     [rcx+10h], rax
0x1800043a7  mov     eax, 1
0x1800043ac  xchg    eax, [rcx+18h]
0x1800043af  mov     [rcx+rbx*2+1Ch], dx
0x1800043b4  mov     rax, rcx
0x1800043b7  mov     rbx, [rsp+48h+arg_8]
0x1800043bc  add     rsp, 40h
0x1800043c0  pop     rdi
0x1800043c1  retn
0x1800043c2  lea     rcx, [rsp+48h+pExceptionObject]; this
0x1800043c7  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x1800043cc  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x1800043d3  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x1800043d8  call    _CxxThrowException
0x1800043de  lea     rdx, aLength; "length"
0x1800043e5  lea     rcx, [rsp+48h+pExceptionObject]; this
0x1800043ea  call    ??0invalid_argument@std@@QEAA@PEBD@Z; std::invalid_argument::invalid_argument(char const *)
0x1800043ef  lea     rdx, _TI3?AVinvalid_argument@std@@; pThrowInfo
0x1800043f6  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x1800043fb  call    _CxxThrowException
```
