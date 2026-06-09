# winrt::impl::produce_base<winrt::Microsoft::Windows::PrivateCommon::factory_implementation::ImageBufferResource,winrt::Microsoft::Windows::PrivateCommon::IImageBufferResourceFactory,void>::Release(void)

- ea: `0x180005fe0`
- end: `0x180006034`
- name: `?Release@?$produce_base@UImageBufferResource@factory_implementation@PrivateCommon@Windows@Microsoft@winrt@@UIImageBufferResourceFactory@3456@X@impl@winrt@@UEAAIXZ`
- size: `84`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180005fe0`
- `0x1800067d0`
- `0x18000b930`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce_base<winrt::Microsoft::Windows::PrivateCommon::factory_implementation::ImageBufferResource,winrt::Microsoft::Windows::PrivateCommon::IImageBufferResourceFactory,void>::Release(
        __int64 a1)
{
  _QWORD *v1; // rbx
  __int64 result; // rax
  unsigned int v3; // edi

  v1 = (_QWORD *)(a1 - 24);
  if ( !a1 )
    v1 = 0;
  result = winrt::impl::root_implements<winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource,winrt::Microsoft::Windows::PrivateCommon::ImageBufferResource>::subtract_final_reference(v1);
  v3 = result;
  if ( !(_DWORD)result )
  {
    v1[1] = 1;
    if ( v1 )
    {
      (*(void (__fastcall **)(_QWORD *, __int64))(*v1 + 8LL))(v1, 1);
      return v3;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180005fe0  mov     [rsp+arg_8], rbx
0x180005fe5  push    rdi
0x180005fe6  sub     rsp, 20h
0x180005fea  xor     eax, eax
0x180005fec  lea     rbx, [rcx-18h]
0x180005ff0  test    rcx, rcx
0x180005ff3  cmovz   rbx, rax
0x180005ff7  mov     rcx, rbx
0x180005ffa  call    ?subtract_final_reference@?$root_implements@UImageBufferResource@implementation@PrivateCommon@Windows@Microsoft@winrt@@U13456@@impl@winrt@@IEAAIXZ; winrt::impl::root_implements<winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource,winrt::Microsoft::Windows::PrivateCommon::ImageBufferResource>::subtract_final_reference(void)
0x180005fff  mov     edi, eax
0x180006001  test    eax, eax
0x180006003  jnz     short loc_180006029
0x180006005  mov     qword ptr [rbx+8], 1
0x18000600d  test    rbx, rbx
0x180006010  jz      short loc_180006029
0x180006012  mov     r8, [rbx]
0x180006015  mov     edx, 1
0x18000601a  mov     rcx, rbx
0x18000601d  mov     rax, [r8+8]
0x180006021  call    cs:__guard_dispatch_icall_fptr
0x180006027  mov     eax, edi
0x180006029  mov     rbx, [rsp+28h+arg_8]
0x18000602e  add     rsp, 20h
0x180006032  pop     rdi
0x180006033  retn
```
