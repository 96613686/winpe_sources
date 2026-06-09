# winrt::implements<winrt::Microsoft::Windows::PrivateCommon::factory_implementation::ImageBufferResource,winrt::Windows::Foundation::IActivationFactory,winrt::Microsoft::Windows::PrivateCommon::IImageBufferResourceFactory>::GetIids(ulong *,_GUID * *)

- ea: `0x180006850`
- end: `0x1800068ea`
- name: `?GetIids@?$implements@UImageBufferResource@factory_implementation@PrivateCommon@Windows@Microsoft@winrt@@UIActivationFactory@Foundation@46@UIImageBufferResourceFactory@3456@@winrt@@QEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `154`
- prototype: `__int64 __fastcall(__int64, unsigned int *, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180005fc0`
- `0x180006280`

## callees

- `0x180006850`
- `0x180007280`
- `0x18000b813`
- `0x18000b930`
- `0x18000bd50`

## pseudocode

```c
__int64 __fastcall winrt::implements<winrt::Microsoft::Windows::PrivateCommon::factory_implementation::ImageBufferResource,winrt::Windows::Foundation::IActivationFactory,winrt::Microsoft::Windows::PrivateCommon::IImageBufferResourceFactory>::GetIids(
        __int64 a1,
        unsigned int *a2,
        _QWORD *a3)
{
  __int64 v5; // rcx
  void *v6; // rax
  unsigned int v8; // [rsp+20h] [rbp-28h] BYREF
  void *Src; // [rsp+28h] [rbp-20h]

  (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)a1 + 32LL))(a1, &v8);
  if ( v8 )
  {
    _mm_lfence();
    v5 = v8;
    *a2 = v8;
    v6 = WINRT_IMPL_CoTaskMemAlloc(16 * v5);
    *a3 = v6;
    if ( !v6 )
      return 2147942414LL;
    memmove(v6, Src, 16LL * v8);
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
0x180006850  mov     [rsp+arg_18], rbx
0x180006855  push    rdi
0x180006856  sub     rsp, 40h
0x18000685a  mov     rax, cs:__security_cookie
0x180006861  xor     rax, rsp
0x180006864  mov     [rsp+48h+var_18], rax
0x180006869  mov     rax, [rcx]
0x18000686c  mov     rbx, rdx
0x18000686f  lea     rdx, [rsp+48h+var_28]
0x180006874  mov     rdi, r8
0x180006877  mov     rax, [rax+20h]
0x18000687b  call    cs:__guard_dispatch_icall_fptr
0x180006881  cmp     [rsp+48h+var_28], 0
0x180006886  jbe     short loc_1800068C3
0x180006888  lfence
0x18000688b  mov     eax, [rsp+48h+var_28]
0x18000688f  mov     ecx, eax
0x180006891  mov     [rbx], eax
0x180006893  shl     rcx, 4; cb
0x180006897  call    WINRT_IMPL_CoTaskMemAlloc
0x18000689c  mov     [rdi], rax
0x18000689f  test    rax, rax
0x1800068a2  jnz     short loc_1800068AB
0x1800068a4  mov     eax, 8007000Eh
0x1800068a9  jmp     short loc_1800068D2
0x1800068ab  mov     r8d, [rsp+48h+var_28]
0x1800068b0  mov     rcx, rax; void *
0x1800068b3  mov     rdx, [rsp+48h+Src]; Src
0x1800068b8  shl     r8, 4; Size
0x1800068bc  call    memmove
0x1800068c1  jmp     short loc_1800068D0
0x1800068c3  mov     dword ptr [rbx], 0
0x1800068c9  mov     qword ptr [rdi], 0
0x1800068d0  xor     eax, eax
0x1800068d2  mov     rcx, [rsp+48h+var_18]
0x1800068d7  xor     rcx, rsp; StackCookie
0x1800068da  call    __security_check_cookie
0x1800068df  mov     rbx, [rsp+48h+arg_18]
0x1800068e4  add     rsp, 40h
0x1800068e8  pop     rdi
0x1800068e9  retn
```
