# winrt::impl::heap_implements<winrt::Microsoft::Windows::PrivateCommon::factory_implementation::ImageBufferResource>::`scalar deleting destructor'(uint)

- ea: `0x180006980`
- end: `0x1800069d2`
- name: `??_G?$heap_implements@UImageBufferResource@factory_implementation@PrivateCommon@Windows@Microsoft@winrt@@@impl@winrt@@UEAAPEAXI@Z`
- size: `82`
- prototype: `void *__fastcall(void *, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800067d0`
- `0x180006980`
- `0x180007660`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x1800069cb`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x1800069cb`

## pseudocode

```c
void *__fastcall winrt::impl::heap_implements<winrt::Microsoft::Windows::PrivateCommon::factory_implementation::ImageBufferResource>::`scalar deleting destructor'(
        void *a1,
        char a2)
{
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
0x180006980  mov     [rsp+arg_8], rbx
0x180006985  push    rdi
0x180006986  sub     rsp, 20h
0x18000698a  mov     edi, edx
0x18000698c  mov     rbx, rcx
0x18000698f  call    ?subtract_final_reference@?$root_implements@UImageBufferResource@implementation@PrivateCommon@Windows@Microsoft@winrt@@U13456@@impl@winrt@@IEAAIXZ; winrt::impl::root_implements<winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource,winrt::Microsoft::Windows::PrivateCommon::ImageBufferResource>::subtract_final_reference(void)
0x180006994  mov     eax, 0FFFFFFFFh
0x180006999  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, eax; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x1800069a1  sub     eax, 1
0x1800069a4  jnz     short loc_1800069C7
0x1800069a6  test    dil, 1
0x1800069aa  jz      short loc_1800069B9
0x1800069ac  mov     edx, 20h ; ' '; unsigned __int64
0x1800069b1  mov     rcx, rbx; void *
0x1800069b4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800069b9  mov     rax, rbx
0x1800069bc  mov     rbx, [rsp+28h+arg_8]
0x1800069c1  add     rsp, 20h
0x1800069c5  pop     rdi
0x1800069c6  retn
0x1800069c7  test    eax, eax
0x1800069c9  jns     short loc_1800069A6
0x1800069cb  call    cs:__imp_abort
```
