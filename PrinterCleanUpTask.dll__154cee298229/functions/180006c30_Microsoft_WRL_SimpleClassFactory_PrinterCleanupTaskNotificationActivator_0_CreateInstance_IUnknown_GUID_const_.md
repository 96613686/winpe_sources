# Microsoft::WRL::SimpleClassFactory<PrinterCleanupTaskNotificationActivator,0>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180006c30`
- end: `0x180006ce7`
- name: `?CreateInstance@?$SimpleClassFactory@VPrinterCleanupTaskNotificationActivator@@$0A@@WRL@Microsoft@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `183`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800068c0`
- `0x180006c30`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180006c5a`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180006c5a`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::SimpleClassFactory<PrinterCleanupTaskNotificationActivator,0>::CreateInstance(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4)
{
  int v6; // ebx
  __int64 (__fastcall ***v7)(_QWORD, _QWORD, _QWORD *); // rcx
  __int64 (__fastcall ***v8)(_QWORD, _QWORD, _QWORD *); // rcx
  __int64 (__fastcall ***v10)(_QWORD, __int64, _QWORD *); // [rsp+38h] [rbp+10h] BYREF

  *a4 = 0;
  if ( a2 )
  {
    v6 = -2147221232;
    RoOriginateError(2147746064LL, 0);
  }
  else
  {
    v10 = 0;
    v6 = Microsoft::WRL::Details::MakeAndInitialize<PrinterCleanupTaskNotificationActivator,IUnknown,>(&v10);
    if ( v6 >= 0 )
    {
      v6 = (**v10)(v10, a3, a4);
      v8 = v10;
      if ( v10 )
      {
        v10 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD *)))(*v8)[2])(v8);
      }
    }
    else
    {
      v7 = v10;
      if ( v10 )
      {
        v10 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD *)))(*v7)[2])(v7);
      }
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180006c30  mov     [rsp+arg_0], rbx
0x180006c35  mov     [rsp+arg_10], rsi
0x180006c3a  push    rdi
0x180006c3b  sub     rsp, 20h
0x180006c3f  mov     rdi, r9
0x180006c42  mov     rsi, r8
0x180006c45  mov     qword ptr [r9], 0
0x180006c4c  test    rdx, rdx
0x180006c4f  jz      short loc_180006C62
0x180006c51  xor     edx, edx
0x180006c53  mov     ebx, 80040110h
0x180006c58  mov     ecx, ebx
0x180006c5a  call    cs:__imp_RoOriginateError
0x180006c60  jmp     short loc_180006CD5
0x180006c62  mov     [rsp+28h+arg_8], 0
0x180006c6b  lea     rcx, [rsp+28h+arg_8]
0x180006c70  call    ??$MakeAndInitialize@VPrinterCleanupTaskNotificationActivator@@UIUnknown@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::MakeAndInitialize<PrinterCleanupTaskNotificationActivator,IUnknown,>(IUnknown * *)
0x180006c75  mov     ebx, eax
0x180006c77  test    eax, eax
0x180006c79  jns     short loc_180006C9D
0x180006c7b  mov     rcx, [rsp+28h+arg_8]
0x180006c80  test    rcx, rcx
0x180006c83  jz      short loc_180006C9B
0x180006c85  mov     [rsp+28h+arg_8], 0
0x180006c8e  mov     rdx, [rcx]
0x180006c91  mov     rax, [rdx+10h]
0x180006c95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c9a  nop
0x180006c9b  jmp     short loc_180006CD5
0x180006c9d  mov     rcx, [rsp+28h+arg_8]
0x180006ca2  mov     rax, [rcx]
0x180006ca5  mov     r8, rdi
0x180006ca8  mov     rdx, rsi
0x180006cab  mov     rax, [rax]
0x180006cae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006cb3  mov     ebx, eax
0x180006cb5  mov     rcx, [rsp+28h+arg_8]
0x180006cba  test    rcx, rcx
0x180006cbd  jz      short loc_180006CD5
0x180006cbf  mov     [rsp+28h+arg_8], 0
0x180006cc8  mov     rdx, [rcx]
0x180006ccb  mov     rax, [rdx+10h]
0x180006ccf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006cd4  nop
0x180006cd5  mov     eax, ebx
0x180006cd7  mov     rbx, [rsp+28h+arg_0]
0x180006cdc  mov     rsi, [rsp+28h+arg_10]
0x180006ce1  add     rsp, 20h
0x180006ce5  pop     rdi
0x180006ce6  retn
```
