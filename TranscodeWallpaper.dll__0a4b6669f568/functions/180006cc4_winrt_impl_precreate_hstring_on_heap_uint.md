# winrt::impl::precreate_hstring_on_heap(uint)

- ea: `0x180006cc4`
- end: `0x180006d66`
- name: `?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z`
- size: `162`
- prototype: `struct winrt::impl::shared_hstring_header *__fastcall(winrt::impl *this, const char *)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x180006a74`
- `0x18000c0c8`
- `0x18000c720`

## callees

- `0x180002cc0`
- `0x180002d38`
- `0x180002d44`
- `0x180003aa4`
- `0x180003b48`
- `0x180006cc4`

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
  ProcessHeap = WINRT_IMPL_GetProcessHeap();
  result = (struct winrt::impl::shared_hstring_header *)WINRT_IMPL_HeapAlloc(ProcessHeap, 0, v3);
  if ( !result )
  {
    std::bad_alloc::bad_alloc((std::bad_alloc *)pExceptionObject);
    throw (std::bad_alloc *)pExceptionObject;
  }
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
0x180006cc4  mov     [rsp+arg_0], rbx
0x180006cc9  mov     [rsp+arg_8], rsi
0x180006cce  push    rdi
0x180006ccf  sub     rsp, 40h
0x180006cd3  mov     ebx, ecx
0x180006cd5  mov     eax, 0FFFFFFFFh
0x180006cda  lea     rsi, ds:20h[rbx*2]
0x180006ce2  cmp     rsi, rax
0x180006ce5  ja      short loc_180006D4A
0x180006ce7  call    WINRT_IMPL_GetProcessHeap
0x180006cec  mov     rcx, rax; hHeap
0x180006cef  mov     r8, rsi; dwBytes
0x180006cf2  xor     edx, edx; dwFlags
0x180006cf4  call    WINRT_IMPL_HeapAlloc
0x180006cf9  xor     ecx, ecx
0x180006cfb  mov     rdx, rax
0x180006cfe  test    rax, rax
0x180006d01  jz      short loc_180006D2E
0x180006d03  mov     rsi, [rsp+48h+arg_8]
0x180006d08  mov     [rax+4], ebx
0x180006d0b  mov     [rax], ecx
0x180006d0d  add     rax, 1Ch
0x180006d11  mov     [rdx+10h], rax
0x180006d15  lea     eax, [rcx+1]
0x180006d18  xchg    eax, [rdx+18h]
0x180006d1b  mov     [rdx+rbx*2+1Ch], cx
0x180006d20  mov     rax, rdx
0x180006d23  mov     rbx, [rsp+48h+arg_0]
0x180006d28  add     rsp, 40h
0x180006d2c  pop     rdi
0x180006d2d  retn
0x180006d2e  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180006d33  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x180006d38  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180006d3f  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180006d44  call    _CxxThrowException_0
0x180006d4a  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180006d4f  call    ??0invalid_argument@std@@QEAA@PEBD@Z; std::invalid_argument::invalid_argument(char const *)
0x180006d54  lea     rdx, _TI3?AVinvalid_argument@std@@; pThrowInfo
0x180006d5b  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180006d60  call    _CxxThrowException_0
```
