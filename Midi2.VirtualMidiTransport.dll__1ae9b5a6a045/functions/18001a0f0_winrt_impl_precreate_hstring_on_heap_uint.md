# winrt::impl::precreate_hstring_on_heap(uint)

- ea: `0x18001a0f0`
- end: `0x18001a192`
- name: `?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z`
- size: `162`
- prototype: `struct winrt::impl::shared_hstring_header *__fastcall(winrt::impl *__hidden this, unsigned int)`
- caller_count: `6`
- callee_count: `6`
- tags: ``

## callers

- `0x18001344c`
- `0x180013b20`
- `0x180013f64`
- `0x180015840`
- `0x1800158d0`
- `0x1800194c8`

## callees

- `0x1800046b8`
- `0x180004760`
- `0x180004784`
- `0x180013960`
- `0x18001402c`
- `0x18001a0f0`

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
0x18001a0f0  mov     [rsp+arg_0], rbx
0x18001a0f5  mov     [rsp+arg_8], rsi
0x18001a0fa  push    rdi
0x18001a0fb  sub     rsp, 40h
0x18001a0ff  mov     ebx, ecx
0x18001a101  mov     eax, 0FFFFFFFFh
0x18001a106  lea     rsi, ds:20h[rbx*2]
0x18001a10e  cmp     rsi, rax
0x18001a111  ja      short loc_18001A176
0x18001a113  call    WINRT_IMPL_GetProcessHeap
0x18001a118  mov     rcx, rax; hHeap
0x18001a11b  mov     r8, rsi; dwBytes
0x18001a11e  xor     edx, edx; dwFlags
0x18001a120  call    WINRT_IMPL_HeapAlloc
0x18001a125  xor     ecx, ecx
0x18001a127  mov     rdx, rax
0x18001a12a  test    rax, rax
0x18001a12d  jz      short loc_18001A15A
0x18001a12f  mov     rsi, [rsp+48h+arg_8]
0x18001a134  mov     [rax+4], ebx
0x18001a137  mov     [rax], ecx
0x18001a139  add     rax, 1Ch
0x18001a13d  mov     [rdx+10h], rax
0x18001a141  lea     eax, [rcx+1]
0x18001a144  xchg    eax, [rdx+18h]
0x18001a147  mov     [rdx+rbx*2+1Ch], cx
0x18001a14c  mov     rax, rdx
0x18001a14f  mov     rbx, [rsp+48h+arg_0]
0x18001a154  add     rsp, 40h
0x18001a158  pop     rdi
0x18001a159  retn
0x18001a15a  lea     rcx, [rsp+48h+pExceptionObject]; this
0x18001a15f  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x18001a164  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18001a16b  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18001a170  call    _CxxThrowException_0
0x18001a176  lea     rcx, [rsp+48h+pExceptionObject]; this
0x18001a17b  call    ??0invalid_argument@std@@QEAA@PEBD@Z; std::invalid_argument::invalid_argument(char const *)
0x18001a180  lea     rdx, _TI3?AVinvalid_argument@std@@; pThrowInfo
0x18001a187  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18001a18c  call    _CxxThrowException_0
```
