# winrt::impl::precreate_hstring_on_heap(uint)

- ea: `0x1800116c4`
- end: `0x180011766`
- name: `?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z`
- size: `162`
- prototype: `struct winrt::impl::shared_hstring_header *__fastcall(winrt::impl *__hidden this, unsigned int)`
- caller_count: `11`
- callee_count: `6`
- tags: ``

## callers

- `0x18000bfcc`
- `0x18000c450`
- `0x18000c974`
- `0x18000d4d4`
- `0x18000d66c`
- `0x18000e220`
- `0x18000e4d0`
- `0x18000e520`
- `0x18000e950`
- `0x1800111c0`
- `0x180011290`

## callees

- `0x180003a50`
- `0x180003af8`
- `0x180003b1c`
- `0x18000c78c`
- `0x18000ce0c`
- `0x1800116c4`

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
0x1800116c4  mov     [rsp+arg_0], rbx
0x1800116c9  mov     [rsp+arg_8], rsi
0x1800116ce  push    rdi
0x1800116cf  sub     rsp, 40h
0x1800116d3  mov     ebx, ecx
0x1800116d5  mov     eax, 0FFFFFFFFh
0x1800116da  lea     rsi, ds:20h[rbx*2]
0x1800116e2  cmp     rsi, rax
0x1800116e5  ja      short loc_18001174A
0x1800116e7  call    WINRT_IMPL_GetProcessHeap
0x1800116ec  mov     rcx, rax; hHeap
0x1800116ef  mov     r8, rsi; dwBytes
0x1800116f2  xor     edx, edx; dwFlags
0x1800116f4  call    WINRT_IMPL_HeapAlloc
0x1800116f9  xor     ecx, ecx
0x1800116fb  mov     rdx, rax
0x1800116fe  test    rax, rax
0x180011701  jz      short loc_18001172E
0x180011703  mov     rsi, [rsp+48h+arg_8]
0x180011708  mov     [rax+4], ebx
0x18001170b  mov     [rax], ecx
0x18001170d  add     rax, 1Ch
0x180011711  mov     [rdx+10h], rax
0x180011715  lea     eax, [rcx+1]
0x180011718  xchg    eax, [rdx+18h]
0x18001171b  mov     [rdx+rbx*2+1Ch], cx
0x180011720  mov     rax, rdx
0x180011723  mov     rbx, [rsp+48h+arg_0]
0x180011728  add     rsp, 40h
0x18001172c  pop     rdi
0x18001172d  retn
0x18001172e  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180011733  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x180011738  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18001173f  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180011744  call    _CxxThrowException_0
0x18001174a  lea     rcx, [rsp+48h+pExceptionObject]; this
0x18001174f  call    ??0invalid_argument@std@@QEAA@PEBD@Z; std::invalid_argument::invalid_argument(char const *)
0x180011754  lea     rdx, _TI3?AVinvalid_argument@std@@; pThrowInfo
0x18001175b  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180011760  call    _CxxThrowException_0
```
