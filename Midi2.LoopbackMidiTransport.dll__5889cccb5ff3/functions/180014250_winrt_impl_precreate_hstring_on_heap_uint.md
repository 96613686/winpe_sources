# winrt::impl::precreate_hstring_on_heap(uint)

- ea: `0x180014250`
- end: `0x1800142f2`
- name: `?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z`
- size: `162`
- prototype: `struct winrt::impl::shared_hstring_header *__fastcall(winrt::impl *__hidden this, unsigned int)`
- caller_count: `7`
- callee_count: `6`
- tags: ``

## callers

- `0x18000ee00`
- `0x18000f3e8`
- `0x18000f82c`
- `0x180010e90`
- `0x180010f20`
- `0x1800139ac`
- `0x180017fd4`

## callees

- `0x18000503c`
- `0x1800050e4`
- `0x180005108`
- `0x18000f228`
- `0x18000f8f4`
- `0x180014250`

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
0x180014250  mov     [rsp+arg_0], rbx
0x180014255  mov     [rsp+arg_8], rsi
0x18001425a  push    rdi
0x18001425b  sub     rsp, 40h
0x18001425f  mov     ebx, ecx
0x180014261  mov     eax, 0FFFFFFFFh
0x180014266  lea     rsi, ds:20h[rbx*2]
0x18001426e  cmp     rsi, rax
0x180014271  ja      short loc_1800142D6
0x180014273  call    WINRT_IMPL_GetProcessHeap
0x180014278  mov     rcx, rax; hHeap
0x18001427b  mov     r8, rsi; dwBytes
0x18001427e  xor     edx, edx; dwFlags
0x180014280  call    WINRT_IMPL_HeapAlloc
0x180014285  xor     ecx, ecx
0x180014287  mov     rdx, rax
0x18001428a  test    rax, rax
0x18001428d  jz      short loc_1800142BA
0x18001428f  mov     rsi, [rsp+48h+arg_8]
0x180014294  mov     [rax+4], ebx
0x180014297  mov     [rax], ecx
0x180014299  add     rax, 1Ch
0x18001429d  mov     [rdx+10h], rax
0x1800142a1  lea     eax, [rcx+1]
0x1800142a4  xchg    eax, [rdx+18h]
0x1800142a7  mov     [rdx+rbx*2+1Ch], cx
0x1800142ac  mov     rax, rdx
0x1800142af  mov     rbx, [rsp+48h+arg_0]
0x1800142b4  add     rsp, 40h
0x1800142b8  pop     rdi
0x1800142b9  retn
0x1800142ba  lea     rcx, [rsp+48h+pExceptionObject]; this
0x1800142bf  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x1800142c4  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x1800142cb  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x1800142d0  call    _CxxThrowException_0
0x1800142d6  lea     rcx, [rsp+48h+pExceptionObject]; this
0x1800142db  call    ??0invalid_argument@std@@QEAA@PEBD@Z; std::invalid_argument::invalid_argument(char const *)
0x1800142e0  lea     rdx, _TI3?AVinvalid_argument@std@@; pThrowInfo
0x1800142e7  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x1800142ec  call    _CxxThrowException_0
```
