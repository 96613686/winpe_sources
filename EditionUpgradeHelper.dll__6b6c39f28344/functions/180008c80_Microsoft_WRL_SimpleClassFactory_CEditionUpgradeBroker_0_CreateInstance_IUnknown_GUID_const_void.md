# Microsoft::WRL::SimpleClassFactory<CEditionUpgradeBroker,0>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180008c80`
- end: `0x180008d14`
- name: `?CreateInstance@?$SimpleClassFactory@VCEditionUpgradeBroker@@$0A@@WRL@Microsoft@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `148`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180008208`
- `0x180008c80`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180008caa`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180008caa`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::SimpleClassFactory<CEditionUpgradeBroker,0>::CreateInstance(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4)
{
  unsigned int v6; // ebx
  int v7; // eax
  __int64 (__fastcall ***v8)(_QWORD, _QWORD, _QWORD *); // rcx
  unsigned int v9; // eax
  __int64 (__fastcall ***v11)(_QWORD, __int64, _QWORD *); // [rsp+38h] [rbp+10h] BYREF

  *a4 = 0;
  if ( a2 )
  {
    v6 = -2147221232;
    RoOriginateError(2147746064LL, 0);
  }
  else
  {
    v11 = 0;
    v7 = Microsoft::WRL::Details::MakeAndInitialize<CEditionUpgradeBroker,IUnknown,>(&v11);
    v8 = v11;
    v6 = v7;
    if ( v7 >= 0 )
    {
      v9 = (**v11)(v11, a3, a4);
      v8 = v11;
      v6 = v9;
    }
    if ( v8 )
    {
      v11 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD *)))(*v8)[2])(v8);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180008c80  mov     [rsp+arg_0], rbx
0x180008c85  mov     [rsp+arg_10], rsi
0x180008c8a  push    rdi
0x180008c8b  sub     rsp, 20h
0x180008c8f  mov     qword ptr [r9], 0
0x180008c96  mov     rdi, r9
0x180008c99  mov     rsi, r8
0x180008c9c  test    rdx, rdx
0x180008c9f  jz      short loc_180008CB2
0x180008ca1  mov     ebx, 80040110h
0x180008ca6  xor     edx, edx
0x180008ca8  mov     ecx, ebx
0x180008caa  call    cs:__imp_RoOriginateError
0x180008cb0  jmp     short loc_180008D02
0x180008cb2  lea     rcx, [rsp+28h+arg_8]
0x180008cb7  mov     [rsp+28h+arg_8], 0
0x180008cc0  call    ??$MakeAndInitialize@VCEditionUpgradeBroker@@UIUnknown@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CEditionUpgradeBroker,IUnknown,>(IUnknown * *)
0x180008cc5  mov     rcx, [rsp+28h+arg_8]
0x180008cca  mov     ebx, eax
0x180008ccc  test    eax, eax
0x180008cce  js      short loc_180008CE8
0x180008cd0  mov     rax, [rcx]
0x180008cd3  mov     r8, rdi
0x180008cd6  mov     rdx, rsi
0x180008cd9  mov     rax, [rax]
0x180008cdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ce1  mov     rcx, [rsp+28h+arg_8]
0x180008ce6  mov     ebx, eax
0x180008ce8  test    rcx, rcx
0x180008ceb  jz      short loc_180008D02
0x180008ced  mov     [rsp+28h+arg_8], 0
0x180008cf6  mov     rdx, [rcx]
0x180008cf9  mov     rax, [rdx+10h]
0x180008cfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d02  mov     rsi, [rsp+28h+arg_10]
0x180008d07  mov     eax, ebx
0x180008d09  mov     rbx, [rsp+28h+arg_0]
0x180008d0e  add     rsp, 20h
0x180008d12  pop     rdi
0x180008d13  retn
```
