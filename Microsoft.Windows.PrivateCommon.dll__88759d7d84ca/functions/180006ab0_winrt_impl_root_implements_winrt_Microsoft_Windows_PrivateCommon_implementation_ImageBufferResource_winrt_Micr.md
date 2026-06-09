# winrt::impl::root_implements<winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource,winrt::Microsoft::Windows::PrivateCommon::ImageBufferResource>::NonDelegatingGetTrustLevel(winrt::Windows::Foundation::TrustLevel *)

- ea: `0x180006ab0`
- end: `0x180006ad7`
- name: `?NonDelegatingGetTrustLevel@?$root_implements@UImageBufferResource@implementation@PrivateCommon@Windows@Microsoft@winrt@@U13456@@impl@winrt@@IEAAHPEAW4TrustLevel@Foundation@Windows@3@@Z`
- size: `39`
- prototype: `__int64 __fastcall(__int64, _DWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180005f80`
- `0x180006240`

## callees

- `0x180006ab0`
- `0x18000b930`

## pseudocode

```c
__int64 __fastcall winrt::impl::root_implements<winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource,winrt::Microsoft::Windows::PrivateCommon::ImageBufferResource>::NonDelegatingGetTrustLevel(
        __int64 a1,
        _DWORD *a2)
{
  *a2 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 16LL))(a1);
  return 0;
}

```

## disassembly

```asm
0x180006ab0  push    rbx
0x180006ab2  sub     rsp, 20h
0x180006ab6  mov     rbx, rdx
0x180006ab9  mov     rax, [rcx]
0x180006abc  mov     rax, [rax+10h]
0x180006ac0  call    cs:__guard_dispatch_icall_fptr
0x180006ac6  mov     [rbx], eax
0x180006ac8  xor     eax, eax
0x180006aca  jmp     short loc_180006AD0
0x180006acc  mov     eax, [rsp+28h+arg_0]
0x180006ad0  add     rsp, 20h
0x180006ad4  pop     rbx
0x180006ad5  retn
```
