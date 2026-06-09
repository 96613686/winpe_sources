# winrt::impl::produce_base<winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource,winrt::Microsoft::Windows::PrivateCommon::IImageBufferResource,void>::GetIids(uint *,winrt::guid * *)

- ea: `0x1800064b0`
- end: `0x18000654c`
- name: `?GetIids@?$produce_base@UImageBufferResource@implementation@PrivateCommon@Windows@Microsoft@winrt@@UIImageBufferResource@3456@X@impl@winrt@@UEAAHPEAIPEAPEAUguid@3@@Z`
- size: `156`
- prototype: `__int64 __fastcall(__int64, unsigned int *, _QWORD *)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800064b0`
- `0x180007280`
- `0x18000b813`
- `0x18000b930`
- `0x18000bd50`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce_base<winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource,winrt::Microsoft::Windows::PrivateCommon::IImageBufferResource,void>::GetIids(
        __int64 a1,
        unsigned int *a2,
        _QWORD *a3)
{
  __int64 v3; // r9
  __int64 v6; // rcx
  void *v7; // rax
  unsigned int v9; // [rsp+20h] [rbp-38h] BYREF
  void *Src; // [rsp+28h] [rbp-30h]

  v3 = a1 - 16;
  if ( !a1 )
    v3 = 0;
  (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v3 + 32LL))(v3, &v9);
  if ( v9 )
  {
    _mm_lfence();
    v6 = v9;
    *a2 = v9;
    v7 = WINRT_IMPL_CoTaskMemAlloc(16 * v6);
    *a3 = v7;
    if ( !v7 )
      return 2147942414LL;
    memmove(v7, Src, 16LL * v9);
  }
  else
  {
    *a2 = 0;
    *a3 = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x1800064b0  push    rbx
0x1800064b2  push    rsi
0x1800064b3  push    rdi
0x1800064b4  sub     rsp, 40h
0x1800064b8  mov     rax, cs:__security_cookie
0x1800064bf  xor     rax, rsp
0x1800064c2  mov     [rsp+58h+var_28], rax
0x1800064c7  lea     r9, [rcx-10h]
0x1800064cb  xor     esi, esi
0x1800064cd  test    rcx, rcx
0x1800064d0  mov     rbx, rdx
0x1800064d3  lea     rdx, [rsp+58h+var_38]
0x1800064d8  mov     rdi, r8
0x1800064db  cmovz   r9, rsi
0x1800064df  mov     rcx, r9
0x1800064e2  mov     rax, [r9]
0x1800064e5  mov     rax, [rax+20h]
0x1800064e9  call    cs:__guard_dispatch_icall_fptr
0x1800064ef  cmp     [rsp+58h+var_38], esi
0x1800064f3  jbe     short loc_180006530
0x1800064f5  lfence
0x1800064f8  mov     eax, [rsp+58h+var_38]
0x1800064fc  mov     ecx, eax
0x1800064fe  mov     [rbx], eax
0x180006500  shl     rcx, 4; cb
0x180006504  call    WINRT_IMPL_CoTaskMemAlloc
0x180006509  mov     [rdi], rax
0x18000650c  test    rax, rax
0x18000650f  jnz     short loc_180006518
0x180006511  mov     eax, 8007000Eh
0x180006516  jmp     short loc_180006537
0x180006518  mov     r8d, [rsp+58h+var_38]
0x18000651d  mov     rcx, rax; void *
0x180006520  mov     rdx, [rsp+58h+Src]; Src
0x180006525  shl     r8, 4; Size
0x180006529  call    memmove
0x18000652e  jmp     short loc_180006535
0x180006530  mov     [rbx], esi
0x180006532  mov     [rdi], rsi
0x180006535  mov     eax, esi
0x180006537  mov     rcx, [rsp+58h+var_28]
0x18000653c  xor     rcx, rsp; StackCookie
0x18000653f  call    __security_check_cookie
0x180006544  add     rsp, 40h
0x180006548  pop     rdi
0x180006549  pop     rsi
0x18000654a  pop     rbx
0x18000654b  retn
```
