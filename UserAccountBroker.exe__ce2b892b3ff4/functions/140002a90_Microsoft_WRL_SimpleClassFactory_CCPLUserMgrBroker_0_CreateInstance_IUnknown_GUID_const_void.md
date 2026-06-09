# Microsoft::WRL::SimpleClassFactory<CCPLUserMgrBroker,0>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x140002a90`
- end: `0x140002b24`
- name: `?CreateInstance@?$SimpleClassFactory@VCCPLUserMgrBroker@@$0A@@WRL@Microsoft@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `148`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140001e98`
- `0x140002a90`
- `0x140007010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x140002aba`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x140002aba`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::SimpleClassFactory<CCPLUserMgrBroker,0>::CreateInstance(
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
    v7 = Microsoft::WRL::Details::MakeAndInitialize<CCPLUserMgrBroker,IUnknown,>(&v11);
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
0x140002a90  mov     [rsp+arg_0], rbx
0x140002a95  mov     [rsp+arg_10], rsi
0x140002a9a  push    rdi
0x140002a9b  sub     rsp, 20h
0x140002a9f  mov     qword ptr [r9], 0
0x140002aa6  mov     rdi, r9
0x140002aa9  mov     rsi, r8
0x140002aac  test    rdx, rdx
0x140002aaf  jz      short loc_140002AC2
0x140002ab1  mov     ebx, 80040110h
0x140002ab6  xor     edx, edx
0x140002ab8  mov     ecx, ebx
0x140002aba  call    cs:__imp_RoOriginateError
0x140002ac0  jmp     short loc_140002B12
0x140002ac2  lea     rcx, [rsp+28h+arg_8]
0x140002ac7  mov     [rsp+28h+arg_8], 0
0x140002ad0  call    ??$MakeAndInitialize@VCCPLUserMgrBroker@@UIUnknown@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CCPLUserMgrBroker,IUnknown,>(IUnknown * *)
0x140002ad5  mov     rcx, [rsp+28h+arg_8]
0x140002ada  mov     ebx, eax
0x140002adc  test    eax, eax
0x140002ade  js      short loc_140002AF8
0x140002ae0  mov     rax, [rcx]
0x140002ae3  mov     r8, rdi
0x140002ae6  mov     rdx, rsi
0x140002ae9  mov     rax, [rax]
0x140002aec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002af1  mov     rcx, [rsp+28h+arg_8]
0x140002af6  mov     ebx, eax
0x140002af8  test    rcx, rcx
0x140002afb  jz      short loc_140002B12
0x140002afd  mov     [rsp+28h+arg_8], 0
0x140002b06  mov     rdx, [rcx]
0x140002b09  mov     rax, [rdx+10h]
0x140002b0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002b12  mov     rsi, [rsp+28h+arg_10]
0x140002b17  mov     eax, ebx
0x140002b19  mov     rbx, [rsp+28h+arg_0]
0x140002b1e  add     rsp, 20h
0x140002b22  pop     rdi
0x140002b23  retn
```
