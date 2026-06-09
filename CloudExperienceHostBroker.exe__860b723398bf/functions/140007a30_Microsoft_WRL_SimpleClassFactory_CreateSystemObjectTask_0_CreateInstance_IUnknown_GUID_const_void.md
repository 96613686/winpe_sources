# Microsoft::WRL::SimpleClassFactory<CreateSystemObjectTask,0>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x140007a30`
- end: `0x140007ab0`
- name: `?CreateInstance@?$SimpleClassFactory@VCreateSystemObjectTask@@$0A@@WRL@Microsoft@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `128`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x140004340`
- `0x140006788`
- `0x140007a30`
- `0x14000a010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x140007a5a`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x140007a5a`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::SimpleClassFactory<CreateSystemObjectTask,0>::CreateInstance(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4)
{
  int v6; // ebx
  __int64 (__fastcall ***v8)(_QWORD, __int64, _QWORD *); // [rsp+38h] [rbp+10h] BYREF

  *a4 = 0;
  if ( a2 )
  {
    v6 = -2147221232;
    RoOriginateError(2147746064LL, 0);
  }
  else
  {
    v8 = 0;
    v6 = Microsoft::WRL::Details::MakeAndInitialize<CreateSystemObjectTask,IUnknown,>(&v8);
    if ( v6 >= 0 )
      v6 = (**v8)(v8, a3, a4);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v8);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140007a30  mov     [rsp+arg_0], rbx
0x140007a35  mov     [rsp+arg_10], rsi
0x140007a3a  push    rdi
0x140007a3b  sub     rsp, 20h
0x140007a3f  mov     rdi, r9
0x140007a42  mov     rsi, r8
0x140007a45  mov     qword ptr [r9], 0
0x140007a4c  test    rdx, rdx
0x140007a4f  jz      short loc_140007A62
0x140007a51  xor     edx, edx
0x140007a53  mov     ebx, 80040110h
0x140007a58  mov     ecx, ebx
0x140007a5a  call    cs:__imp_RoOriginateError
0x140007a60  jmp     short loc_140007A9E
0x140007a62  mov     [rsp+28h+arg_8], 0
0x140007a6b  lea     rcx, [rsp+28h+arg_8]
0x140007a70  call    ??$MakeAndInitialize@VCreateSystemObjectTask@@UIUnknown@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CreateSystemObjectTask,IUnknown,>(IUnknown * *)
0x140007a75  mov     ebx, eax
0x140007a77  test    eax, eax
0x140007a79  js      short loc_140007A94
0x140007a7b  mov     rcx, [rsp+28h+arg_8]
0x140007a80  mov     rax, [rcx]
0x140007a83  mov     r8, rdi
0x140007a86  mov     rdx, rsi
0x140007a89  mov     rax, [rax]
0x140007a8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007a91  nop
0x140007a92  mov     ebx, eax
0x140007a94  lea     rcx, [rsp+28h+arg_8]
0x140007a99  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140007a9e  mov     eax, ebx
0x140007aa0  mov     rbx, [rsp+28h+arg_0]
0x140007aa5  mov     rsi, [rsp+28h+arg_10]
0x140007aaa  add     rsp, 20h
0x140007aae  pop     rdi
0x140007aaf  retn
```
