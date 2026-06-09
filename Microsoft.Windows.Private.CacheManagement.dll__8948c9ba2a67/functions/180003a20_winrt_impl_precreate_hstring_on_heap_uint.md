# winrt::impl::precreate_hstring_on_heap(uint)

- ea: `0x180003a20`
- end: `0x180003ad1`
- name: `?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z`
- size: `177`
- prototype: `struct winrt::impl::shared_hstring_header *__fastcall(winrt::impl *this)`
- caller_count: `9`
- callee_count: `6`
- tags: ``

## callers

- `0x180003c60`
- `0x180009a00`
- `0x1800120d0`
- `0x1800127e0`
- `0x180012f10`
- `0x180013ff0`
- `0x18001e4d4`
- `0x18001e5fa`
- `0x18001e720`

## callees

- `0x180003860`
- `0x180003950`
- `0x180003a20`
- `0x18001629e`
- `0x1800162a4`
- `0x180019c0c`

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
0x180003a20  mov     [rsp+arg_8], rbx
0x180003a25  mov     [rsp+arg_10], rsi
0x180003a2a  push    rdi
0x180003a2b  sub     rsp, 40h
0x180003a2f  mov     ebx, ecx
0x180003a31  mov     eax, 0FFFFFFFFh
0x180003a36  lea     rsi, ds:20h[rbx*2]
0x180003a3e  cmp     rsi, rax
0x180003a41  ja      short loc_180003AAE
0x180003a43  lfence
0x180003a46  call    WINRT_IMPL_GetProcessHeap
0x180003a4b  mov     rcx, rax; hHeap
0x180003a4e  mov     r8, rsi; dwBytes
0x180003a51  xor     edx, edx; dwFlags
0x180003a53  call    WINRT_IMPL_HeapAlloc
0x180003a58  mov     rcx, rax
0x180003a5b  test    rax, rax
0x180003a5e  jz      short loc_180003A92
0x180003a60  lfence
0x180003a63  mov     rsi, [rsp+48h+arg_10]
0x180003a68  xor     edx, edx
0x180003a6a  mov     [rax+4], ebx
0x180003a6d  mov     [rax], edx
0x180003a6f  add     rax, 1Ch
0x180003a73  mov     [rcx+10h], rax
0x180003a77  mov     eax, 1
0x180003a7c  xchg    eax, [rcx+18h]
0x180003a7f  mov     [rcx+rbx*2+1Ch], dx
0x180003a84  mov     rax, rcx
0x180003a87  mov     rbx, [rsp+48h+arg_8]
0x180003a8c  add     rsp, 40h
0x180003a90  pop     rdi
0x180003a91  retn
0x180003a92  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180003a97  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x180003a9c  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180003aa3  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180003aa8  call    _CxxThrowException
0x180003aae  lea     rdx, aLength; "length"
0x180003ab5  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180003aba  call    ??0invalid_argument@std@@QEAA@PEBD@Z; std::invalid_argument::invalid_argument(char const *)
0x180003abf  lea     rdx, _TI3?AVinvalid_argument@std@@; pThrowInfo
0x180003ac6  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180003acb  call    _CxxThrowException
```
