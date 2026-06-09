# winrt::impl::heap_implements<winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource>::`vector deleting destructor'(uint)

- ea: `0x180005cd0`
- end: `0x180005d5d`
- name: `??_E?$heap_implements@UImageBufferResource@implementation@PrivateCommon@Windows@Microsoft@winrt@@@impl@winrt@@UEAAPEAXI@Z`
- size: `141`
- prototype: `_QWORD *__fastcall(_QWORD *, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180005cd0`
- `0x1800067d0`
- `0x180007660`

## import_xrefs

- `KERNEL32!UnmapViewOfFile` at `0x180005cf2`
- `KERNEL32!UnmapViewOfFile` at `0x180005cf2`
- `KERNEL32!CloseHandle` at `0x180005d09`
- `KERNEL32!CloseHandle` at `0x180005d09`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180005d56`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180005d56`

## pseudocode

```c
_QWORD *__fastcall winrt::impl::heap_implements<winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource>::`vector deleting destructor'(
        _QWORD *a1,
        char a2)
{
  const void *v4; // rcx
  void *v5; // rcx

  *a1 = &winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource::`vftable';
  v4 = (const void *)a1[7];
  if ( v4 )
  {
    UnmapViewOfFile(v4);
    a1[7] = 0;
  }
  v5 = (void *)a1[5];
  if ( v5 )
  {
    CloseHandle(v5);
    a1[5] = 0;
  }
  winrt::impl::root_implements<winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource,winrt::Microsoft::Windows::PrivateCommon::ImageBufferResource>::subtract_final_reference(a1);
  if ( _InterlockedDecrement(&`winrt::get_module_lock'::`2'::s_lock) < 0 )
    abort();
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180005cd0  mov     [rsp+arg_8], rbx
0x180005cd5  push    rdi
0x180005cd6  sub     rsp, 20h
0x180005cda  lea     rax, ??_7ImageBufferResource@implementation@PrivateCommon@Windows@Microsoft@winrt@@6B@; const winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource::`vftable'
0x180005ce1  mov     rbx, rcx
0x180005ce4  mov     [rcx], rax
0x180005ce7  mov     edi, edx
0x180005ce9  mov     rcx, [rcx+38h]; lpBaseAddress
0x180005ced  test    rcx, rcx
0x180005cf0  jz      short loc_180005D00
0x180005cf2  call    cs:__imp_UnmapViewOfFile
0x180005cf8  mov     qword ptr [rbx+38h], 0
0x180005d00  mov     rcx, [rbx+28h]; hObject
0x180005d04  test    rcx, rcx
0x180005d07  jz      short loc_180005D17
0x180005d09  call    cs:__imp_CloseHandle
0x180005d0f  mov     qword ptr [rbx+28h], 0
0x180005d17  mov     rcx, rbx
0x180005d1a  call    ?subtract_final_reference@?$root_implements@UImageBufferResource@implementation@PrivateCommon@Windows@Microsoft@winrt@@U13456@@impl@winrt@@IEAAIXZ; winrt::impl::root_implements<winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource,winrt::Microsoft::Windows::PrivateCommon::ImageBufferResource>::subtract_final_reference(void)
0x180005d1f  mov     eax, 0FFFFFFFFh
0x180005d24  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, eax; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180005d2c  sub     eax, 1
0x180005d2f  jnz     short loc_180005D52
0x180005d31  test    dil, 1
0x180005d35  jz      short loc_180005D44
0x180005d37  mov     edx, 40h ; '@'; unsigned __int64
0x180005d3c  mov     rcx, rbx; void *
0x180005d3f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180005d44  mov     rax, rbx
0x180005d47  mov     rbx, [rsp+28h+arg_8]
0x180005d4c  add     rsp, 20h
0x180005d50  pop     rdi
0x180005d51  retn
0x180005d52  test    eax, eax
0x180005d54  jns     short loc_180005D31
0x180005d56  call    cs:__imp_abort
```
