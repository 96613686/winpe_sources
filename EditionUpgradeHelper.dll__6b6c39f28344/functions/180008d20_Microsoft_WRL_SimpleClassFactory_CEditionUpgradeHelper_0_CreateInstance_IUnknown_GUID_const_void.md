# Microsoft::WRL::SimpleClassFactory<CEditionUpgradeHelper,0>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180008d20`
- end: `0x180008db4`
- name: `?CreateInstance@?$SimpleClassFactory@VCEditionUpgradeHelper@@$0A@@WRL@Microsoft@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `148`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800082fc`
- `0x180008d20`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180008d4a`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180008d4a`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::SimpleClassFactory<CEditionUpgradeHelper,0>::CreateInstance(
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
    v7 = Microsoft::WRL::Details::MakeAndInitialize<CEditionUpgradeHelper,IUnknown,>(&v11);
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
0x180008d20  mov     [rsp+arg_0], rbx
0x180008d25  mov     [rsp+arg_10], rsi
0x180008d2a  push    rdi
0x180008d2b  sub     rsp, 20h
0x180008d2f  mov     qword ptr [r9], 0
0x180008d36  mov     rdi, r9
0x180008d39  mov     rsi, r8
0x180008d3c  test    rdx, rdx
0x180008d3f  jz      short loc_180008D52
0x180008d41  mov     ebx, 80040110h
0x180008d46  xor     edx, edx
0x180008d48  mov     ecx, ebx
0x180008d4a  call    cs:__imp_RoOriginateError
0x180008d50  jmp     short loc_180008DA2
0x180008d52  lea     rcx, [rsp+28h+arg_8]
0x180008d57  mov     [rsp+28h+arg_8], 0
0x180008d60  call    ??$MakeAndInitialize@VCEditionUpgradeHelper@@UIUnknown@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CEditionUpgradeHelper,IUnknown,>(IUnknown * *)
0x180008d65  mov     rcx, [rsp+28h+arg_8]
0x180008d6a  mov     ebx, eax
0x180008d6c  test    eax, eax
0x180008d6e  js      short loc_180008D88
0x180008d70  mov     rax, [rcx]
0x180008d73  mov     r8, rdi
0x180008d76  mov     rdx, rsi
0x180008d79  mov     rax, [rax]
0x180008d7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d81  mov     rcx, [rsp+28h+arg_8]
0x180008d86  mov     ebx, eax
0x180008d88  test    rcx, rcx
0x180008d8b  jz      short loc_180008DA2
0x180008d8d  mov     [rsp+28h+arg_8], 0
0x180008d96  mov     rdx, [rcx]
0x180008d99  mov     rax, [rdx+10h]
0x180008d9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008da2  mov     rsi, [rsp+28h+arg_10]
0x180008da7  mov     eax, ebx
0x180008da9  mov     rbx, [rsp+28h+arg_0]
0x180008dae  add     rsp, 20h
0x180008db2  pop     rdi
0x180008db3  retn
```
