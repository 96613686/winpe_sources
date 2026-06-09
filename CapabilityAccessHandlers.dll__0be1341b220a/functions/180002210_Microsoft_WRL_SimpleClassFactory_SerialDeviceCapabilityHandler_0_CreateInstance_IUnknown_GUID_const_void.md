# Microsoft::WRL::SimpleClassFactory<SerialDeviceCapabilityHandler,0>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180002210`
- end: `0x1800022b8`
- name: `?CreateInstance@?$SimpleClassFactory@VSerialDeviceCapabilityHandler@@$0A@@WRL@Microsoft@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `168`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002210`
- `0x1800022c0`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000223a`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000223a`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::SimpleClassFactory<SerialDeviceCapabilityHandler,0>::CreateInstance(
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
  v6 = Microsoft::WRL::Details::MakeAndInitialize<SerialDeviceCapabilityHandler,IUnknown,>(&v10);
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
0x180002210  mov     [rsp+arg_0], rbx
0x180002215  mov     [rsp+arg_10], rsi
0x18000221a  push    rdi
0x18000221b  sub     rsp, 20h
0x18000221f  mov     rdi, r9
0x180002222  mov     rsi, r8
0x180002225  mov     qword ptr [r9], 0
0x18000222c  test    rdx, rdx
0x18000222f  jz      short loc_180002244
0x180002231  xor     edx, edx
0x180002233  mov     ebx, 80040110h
0x180002238  mov     ecx, ebx
0x18000223a  call    cs:__imp_RoOriginateError
0x180002240  mov     eax, ebx
0x180002242  jmp     short loc_1800022A8
0x180002244  mov     [rsp+28h+arg_8], 0
0x18000224d  lea     rcx, [rsp+28h+arg_8]
0x180002252  call    ??$MakeAndInitialize@VSerialDeviceCapabilityHandler@@UIUnknown@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::MakeAndInitialize<SerialDeviceCapabilityHandler,IUnknown,>(IUnknown * *)
0x180002257  mov     ebx, eax
0x180002259  test    eax, eax
0x18000225b  jns     short loc_180002276
0x18000225d  mov     rcx, [rsp+28h+arg_8]
0x180002262  test    rcx, rcx
0x180002265  jz      short loc_180002274
0x180002267  mov     rdx, [rcx]
0x18000226a  mov     rax, [rdx+10h]
0x18000226e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002273  nop
0x180002274  jmp     short loc_180002240
0x180002276  mov     rbx, [rsp+28h+arg_8]
0x18000227b  mov     rax, [rbx]
0x18000227e  mov     r8, rdi
0x180002281  mov     rdx, rsi
0x180002284  mov     rcx, rbx
0x180002287  mov     rax, [rax]
0x18000228a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000228f  mov     edi, eax
0x180002291  test    rbx, rbx
0x180002294  jz      short loc_1800022A6
0x180002296  mov     rdx, [rbx]
0x180002299  mov     rcx, rbx
0x18000229c  mov     rax, [rdx+10h]
0x1800022a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800022a5  nop
0x1800022a6  mov     eax, edi
0x1800022a8  mov     rbx, [rsp+28h+arg_0]
0x1800022ad  mov     rsi, [rsp+28h+arg_10]
0x1800022b2  add     rsp, 20h
0x1800022b6  pop     rdi
0x1800022b7  retn
```
