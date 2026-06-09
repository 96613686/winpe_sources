# Microsoft::WRL::SimpleClassFactory<WiFiDirectCapabilityHandler,0>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180001600`
- end: `0x1800016a8`
- name: `?CreateInstance@?$SimpleClassFactory@VWiFiDirectCapabilityHandler@@$0A@@WRL@Microsoft@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `168`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001600`
- `0x1800016b0`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000162a`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000162a`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::SimpleClassFactory<WiFiDirectCapabilityHandler,0>::CreateInstance(
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
  v6 = Microsoft::WRL::Details::MakeAndInitialize<WiFiDirectCapabilityHandler,IUnknown,>(&v10);
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
0x180001600  mov     [rsp+arg_0], rbx
0x180001605  mov     [rsp+arg_10], rsi
0x18000160a  push    rdi
0x18000160b  sub     rsp, 20h
0x18000160f  mov     rdi, r9
0x180001612  mov     rsi, r8
0x180001615  mov     qword ptr [r9], 0
0x18000161c  test    rdx, rdx
0x18000161f  jz      short loc_180001634
0x180001621  xor     edx, edx
0x180001623  mov     ebx, 80040110h
0x180001628  mov     ecx, ebx
0x18000162a  call    cs:__imp_RoOriginateError
0x180001630  mov     eax, ebx
0x180001632  jmp     short loc_180001698
0x180001634  mov     [rsp+28h+arg_8], 0
0x18000163d  lea     rcx, [rsp+28h+arg_8]
0x180001642  call    ??$MakeAndInitialize@VWiFiDirectCapabilityHandler@@UIUnknown@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::MakeAndInitialize<WiFiDirectCapabilityHandler,IUnknown,>(IUnknown * *)
0x180001647  mov     ebx, eax
0x180001649  test    eax, eax
0x18000164b  jns     short loc_180001666
0x18000164d  mov     rcx, [rsp+28h+arg_8]
0x180001652  test    rcx, rcx
0x180001655  jz      short loc_180001664
0x180001657  mov     rdx, [rcx]
0x18000165a  mov     rax, [rdx+10h]
0x18000165e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001663  nop
0x180001664  jmp     short loc_180001630
0x180001666  mov     rbx, [rsp+28h+arg_8]
0x18000166b  mov     rax, [rbx]
0x18000166e  mov     r8, rdi
0x180001671  mov     rdx, rsi
0x180001674  mov     rcx, rbx
0x180001677  mov     rax, [rax]
0x18000167a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000167f  mov     edi, eax
0x180001681  test    rbx, rbx
0x180001684  jz      short loc_180001696
0x180001686  mov     rdx, [rbx]
0x180001689  mov     rcx, rbx
0x18000168c  mov     rax, [rdx+10h]
0x180001690  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001695  nop
0x180001696  mov     eax, edi
0x180001698  mov     rbx, [rsp+28h+arg_0]
0x18000169d  mov     rsi, [rsp+28h+arg_10]
0x1800016a2  add     rsp, 20h
0x1800016a6  pop     rdi
0x1800016a7  retn
```
