# winrt::impl::precreate_hstring_on_heap(uint)

- ea: `0x18000c3d4`
- end: `0x18000c476`
- name: `?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z`
- size: `162`
- prototype: `struct winrt::impl::shared_hstring_header *__fastcall(winrt::impl *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18000c4fc`

## callees

- `0x180004190`
- `0x180004208`
- `0x180004214`
- `0x18000bfd4`
- `0x18000c024`
- `0x18000c3d4`

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
0x18000c3d4  mov     [rsp+arg_0], rbx
0x18000c3d9  mov     [rsp+arg_8], rsi
0x18000c3de  push    rdi
0x18000c3df  sub     rsp, 40h
0x18000c3e3  mov     ebx, ecx
0x18000c3e5  mov     eax, 0FFFFFFFFh
0x18000c3ea  lea     rsi, ds:20h[rbx*2]
0x18000c3f2  cmp     rsi, rax
0x18000c3f5  ja      short loc_18000C45A
0x18000c3f7  call    WINRT_IMPL_GetProcessHeap
0x18000c3fc  mov     rcx, rax; hHeap
0x18000c3ff  mov     r8, rsi; dwBytes
0x18000c402  xor     edx, edx; dwFlags
0x18000c404  call    WINRT_IMPL_HeapAlloc
0x18000c409  xor     ecx, ecx
0x18000c40b  mov     rdx, rax
0x18000c40e  test    rax, rax
0x18000c411  jz      short loc_18000C43E
0x18000c413  mov     rsi, [rsp+48h+arg_8]
0x18000c418  mov     [rax+4], ebx
0x18000c41b  mov     [rax], ecx
0x18000c41d  add     rax, 1Ch
0x18000c421  mov     [rdx+10h], rax
0x18000c425  lea     eax, [rcx+1]
0x18000c428  xchg    eax, [rdx+18h]
0x18000c42b  mov     [rdx+rbx*2+1Ch], cx
0x18000c430  mov     rax, rdx
0x18000c433  mov     rbx, [rsp+48h+arg_0]
0x18000c438  add     rsp, 40h
0x18000c43c  pop     rdi
0x18000c43d  retn
0x18000c43e  lea     rcx, [rsp+48h+pExceptionObject]; this
0x18000c443  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x18000c448  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18000c44f  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18000c454  call    _CxxThrowException_0
0x18000c45a  lea     rcx, [rsp+48h+pExceptionObject]; this
0x18000c45f  call    ??0invalid_argument@std@@QEAA@PEBD@Z; std::invalid_argument::invalid_argument(char const *)
0x18000c464  lea     rdx, _TI3?AVinvalid_argument@std@@; pThrowInfo
0x18000c46b  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18000c470  call    _CxxThrowException_0
```
