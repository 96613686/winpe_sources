# winrt::impl::precreate_hstring_on_heap(uint)

- ea: `0x18000f09c`
- end: `0x18000f13e`
- name: `?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z`
- size: `162`
- prototype: `struct winrt::impl::shared_hstring_header *__fastcall(winrt::impl *this, const char *)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x180004cf4`
- `0x180005314`
- `0x18000ed6c`

## callees

- `0x180002e04`
- `0x180002ea0`
- `0x180002eb8`
- `0x1800050e8`
- `0x1800056e0`
- `0x18000f09c`

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
0x18000f09c  mov     [rsp+arg_0], rbx
0x18000f0a1  mov     [rsp+arg_8], rsi
0x18000f0a6  push    rdi
0x18000f0a7  sub     rsp, 40h
0x18000f0ab  mov     ebx, ecx
0x18000f0ad  mov     eax, 0FFFFFFFFh
0x18000f0b2  lea     rsi, ds:20h[rbx*2]
0x18000f0ba  cmp     rsi, rax
0x18000f0bd  ja      short loc_18000F122
0x18000f0bf  call    WINRT_IMPL_GetProcessHeap
0x18000f0c4  mov     rcx, rax; hHeap
0x18000f0c7  mov     r8, rsi; dwBytes
0x18000f0ca  xor     edx, edx; dwFlags
0x18000f0cc  call    WINRT_IMPL_HeapAlloc
0x18000f0d1  xor     ecx, ecx
0x18000f0d3  mov     rdx, rax
0x18000f0d6  test    rax, rax
0x18000f0d9  jz      short loc_18000F106
0x18000f0db  mov     rsi, [rsp+48h+arg_8]
0x18000f0e0  mov     [rax+4], ebx
0x18000f0e3  mov     [rax], ecx
0x18000f0e5  add     rax, 1Ch
0x18000f0e9  mov     [rdx+10h], rax
0x18000f0ed  lea     eax, [rcx+1]
0x18000f0f0  xchg    eax, [rdx+18h]
0x18000f0f3  mov     [rdx+rbx*2+1Ch], cx
0x18000f0f8  mov     rax, rdx
0x18000f0fb  mov     rbx, [rsp+48h+arg_0]
0x18000f100  add     rsp, 40h
0x18000f104  pop     rdi
0x18000f105  retn
0x18000f106  lea     rcx, [rsp+48h+pExceptionObject]; this
0x18000f10b  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x18000f110  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18000f117  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18000f11c  call    _CxxThrowException_0
0x18000f122  lea     rcx, [rsp+48h+pExceptionObject]; this
0x18000f127  call    ??0invalid_argument@std@@QEAA@PEBD@Z; std::invalid_argument::invalid_argument(char const *)
0x18000f12c  lea     rdx, _TI3?AVinvalid_argument@std@@; pThrowInfo
0x18000f133  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18000f138  call    _CxxThrowException_0
```
