# winrt::impl::produce_base<winrt::Microsoft::Windows::PrivateCommon::factory_implementation::ImageBufferResource,winrt::Windows::Foundation::IActivationFactory,void>::Release(void)

- ea: `0x1800062a0`
- end: `0x1800062f4`
- name: `?Release@?$produce_base@UImageBufferResource@factory_implementation@PrivateCommon@Windows@Microsoft@winrt@@UIActivationFactory@Foundation@46@X@impl@winrt@@UEAAIXZ`
- size: `84`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800062a0`
- `0x1800067d0`
- `0x18000b930`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce_base<winrt::Microsoft::Windows::PrivateCommon::factory_implementation::ImageBufferResource,winrt::Windows::Foundation::IActivationFactory,void>::Release(
        __int64 a1)
{
  _QWORD *v1; // rbx
  __int64 result; // rax
  unsigned int v3; // edi

  v1 = (_QWORD *)(a1 - 16);
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
0x1800062a0  mov     [rsp+arg_8], rbx
0x1800062a5  push    rdi
0x1800062a6  sub     rsp, 20h
0x1800062aa  xor     eax, eax
0x1800062ac  lea     rbx, [rcx-10h]
0x1800062b0  test    rcx, rcx
0x1800062b3  cmovz   rbx, rax
0x1800062b7  mov     rcx, rbx
0x1800062ba  call    ?subtract_final_reference@?$root_implements@UImageBufferResource@implementation@PrivateCommon@Windows@Microsoft@winrt@@U13456@@impl@winrt@@IEAAIXZ; winrt::impl::root_implements<winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource,winrt::Microsoft::Windows::PrivateCommon::ImageBufferResource>::subtract_final_reference(void)
0x1800062bf  mov     edi, eax
0x1800062c1  test    eax, eax
0x1800062c3  jnz     short loc_1800062E9
0x1800062c5  mov     qword ptr [rbx+8], 1
0x1800062cd  test    rbx, rbx
0x1800062d0  jz      short loc_1800062E9
0x1800062d2  mov     r8, [rbx]
0x1800062d5  mov     edx, 1
0x1800062da  mov     rcx, rbx
0x1800062dd  mov     rax, [r8+8]
0x1800062e1  call    cs:__guard_dispatch_icall_fptr
0x1800062e7  mov     eax, edi
0x1800062e9  mov     rbx, [rsp+28h+arg_8]
0x1800062ee  add     rsp, 20h
0x1800062f2  pop     rdi
0x1800062f3  retn
```
