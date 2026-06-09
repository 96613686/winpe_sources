# winrt::impl::precreate_hstring_on_heap(uint)

- ea: `0x18000b058`
- end: `0x18000b0fa`
- name: `?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z`
- size: `162`
- prototype: `struct winrt::impl::shared_hstring_header *__fastcall(winrt::impl *__hidden this, unsigned int)`
- caller_count: `22`
- callee_count: `6`
- tags: ``

## callers

- `0x180004c0c`
- `0x180005188`
- `0x180007220`
- `0x180007270`
- `0x180007940`
- `0x1800079c0`
- `0x180007a10`
- `0x180007a60`
- `0x180007ab0`
- `0x180009e90`
- `0x180009f40`
- `0x18000ad28`
- `0x180011b80`
- `0x180012160`
- `0x180014058`
- `0x180014700`
- `0x180016dbc`
- `0x18001d568`
- `0x18001dec4`
- `0x180021d68`
- `0x180028b14`
- `0x180029540`

## callees

- `0x180002c10`
- `0x180002d79`
- `0x180002d91`
- `0x180004fd0`
- `0x180005554`
- `0x18000b058`

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
0x18000b058  mov     [rsp+arg_0], rbx
0x18000b05d  mov     [rsp+arg_8], rsi
0x18000b062  push    rdi
0x18000b063  sub     rsp, 40h
0x18000b067  mov     ebx, ecx
0x18000b069  mov     eax, 0FFFFFFFFh
0x18000b06e  lea     rsi, ds:20h[rbx*2]
0x18000b076  cmp     rsi, rax
0x18000b079  ja      short loc_18000B0DE
0x18000b07b  call    WINRT_IMPL_GetProcessHeap
0x18000b080  mov     rcx, rax; hHeap
0x18000b083  mov     r8, rsi; dwBytes
0x18000b086  xor     edx, edx; dwFlags
0x18000b088  call    WINRT_IMPL_HeapAlloc
0x18000b08d  xor     ecx, ecx
0x18000b08f  mov     rdx, rax
0x18000b092  test    rax, rax
0x18000b095  jz      short loc_18000B0C2
0x18000b097  mov     rsi, [rsp+48h+arg_8]
0x18000b09c  mov     [rax+4], ebx
0x18000b09f  mov     [rax], ecx
0x18000b0a1  add     rax, 1Ch
0x18000b0a5  mov     [rdx+10h], rax
0x18000b0a9  lea     eax, [rcx+1]
0x18000b0ac  xchg    eax, [rdx+18h]
0x18000b0af  mov     [rdx+rbx*2+1Ch], cx
0x18000b0b4  mov     rax, rdx
0x18000b0b7  mov     rbx, [rsp+48h+arg_0]
0x18000b0bc  add     rsp, 40h
0x18000b0c0  pop     rdi
0x18000b0c1  retn
0x18000b0c2  lea     rcx, [rsp+48h+pExceptionObject]; this
0x18000b0c7  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x18000b0cc  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18000b0d3  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18000b0d8  call    _CxxThrowException_0
0x18000b0de  lea     rcx, [rsp+48h+pExceptionObject]; this
0x18000b0e3  call    ??0invalid_argument@std@@QEAA@PEBD@Z; std::invalid_argument::invalid_argument(char const *)
0x18000b0e8  lea     rdx, _TI3?AVinvalid_argument@std@@; pThrowInfo
0x18000b0ef  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18000b0f4  call    _CxxThrowException_0
```
