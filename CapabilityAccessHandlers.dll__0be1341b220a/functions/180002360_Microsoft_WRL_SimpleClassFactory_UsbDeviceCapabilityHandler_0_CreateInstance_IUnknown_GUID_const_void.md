# Microsoft::WRL::SimpleClassFactory<UsbDeviceCapabilityHandler,0>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180002360`
- end: `0x180002408`
- name: `?CreateInstance@?$SimpleClassFactory@VUsbDeviceCapabilityHandler@@$0A@@WRL@Microsoft@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `168`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002360`
- `0x180002410`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000238a`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000238a`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::SimpleClassFactory<UsbDeviceCapabilityHandler,0>::CreateInstance(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4)
{
  int v6; // ebx
  __int64 v8; // rbx
  unsigned int v9; // edi
  __int64 v10; // [rsp+38h] [rbp+10h] BYREF

  *a4 = 0;
  if ( a2 )
  {
    v6 = -2147221232;
    RoOriginateError(2147746064LL, 0);
    return (unsigned int)v6;
  }
  v10 = 0;
  v6 = Microsoft::WRL::Details::MakeAndInitialize<UsbDeviceCapabilityHandler,IUnknown,>(&v10);
  if ( v6 < 0 )
  {
    if ( v10 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    return (unsigned int)v6;
  }
  v8 = v10;
  v9 = (**(__int64 (__fastcall ***)(__int64, __int64, _QWORD *))v10)(v10, a3, a4);
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  return v9;
}

```

## disassembly

```asm
0x180002360  mov     [rsp+arg_0], rbx
0x180002365  mov     [rsp+arg_10], rsi
0x18000236a  push    rdi
0x18000236b  sub     rsp, 20h
0x18000236f  mov     rdi, r9
0x180002372  mov     rsi, r8
0x180002375  mov     qword ptr [r9], 0
0x18000237c  test    rdx, rdx
0x18000237f  jz      short loc_180002394
0x180002381  xor     edx, edx
0x180002383  mov     ebx, 80040110h
0x180002388  mov     ecx, ebx
0x18000238a  call    cs:__imp_RoOriginateError
0x180002390  mov     eax, ebx
0x180002392  jmp     short loc_1800023F8
0x180002394  mov     [rsp+28h+arg_8], 0
0x18000239d  lea     rcx, [rsp+28h+arg_8]
0x1800023a2  call    ??$MakeAndInitialize@VUsbDeviceCapabilityHandler@@UIUnknown@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::MakeAndInitialize<UsbDeviceCapabilityHandler,IUnknown,>(IUnknown * *)
0x1800023a7  mov     ebx, eax
0x1800023a9  test    eax, eax
0x1800023ab  jns     short loc_1800023C6
0x1800023ad  mov     rcx, [rsp+28h+arg_8]
0x1800023b2  test    rcx, rcx
0x1800023b5  jz      short loc_1800023C4
0x1800023b7  mov     rdx, [rcx]
0x1800023ba  mov     rax, [rdx+10h]
0x1800023be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800023c3  nop
0x1800023c4  jmp     short loc_180002390
0x1800023c6  mov     rbx, [rsp+28h+arg_8]
0x1800023cb  mov     rax, [rbx]
0x1800023ce  mov     r8, rdi
0x1800023d1  mov     rdx, rsi
0x1800023d4  mov     rcx, rbx
0x1800023d7  mov     rax, [rax]
0x1800023da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800023df  mov     edi, eax
0x1800023e1  test    rbx, rbx
0x1800023e4  jz      short loc_1800023F6
0x1800023e6  mov     rdx, [rbx]
0x1800023e9  mov     rcx, rbx
0x1800023ec  mov     rax, [rdx+10h]
0x1800023f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800023f5  nop
0x1800023f6  mov     eax, edi
0x1800023f8  mov     rbx, [rsp+28h+arg_0]
0x1800023fd  mov     rsi, [rsp+28h+arg_10]
0x180002402  add     rsp, 20h
0x180002406  pop     rdi
0x180002407  retn
```
