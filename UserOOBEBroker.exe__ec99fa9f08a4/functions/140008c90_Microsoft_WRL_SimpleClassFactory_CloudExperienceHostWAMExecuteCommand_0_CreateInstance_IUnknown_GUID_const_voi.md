# Microsoft::WRL::SimpleClassFactory<CloudExperienceHostWAMExecuteCommand,0>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x140008c90`
- end: `0x140008d38`
- name: `?CreateInstance@?$SimpleClassFactory@VCloudExperienceHostWAMExecuteCommand@@$0A@@WRL@Microsoft@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `168`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140007264`
- `0x140008c90`
- `0x14000f010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x140008cba`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x140008cba`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::SimpleClassFactory<CloudExperienceHostWAMExecuteCommand,0>::CreateInstance(
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
  v6 = Microsoft::WRL::Details::MakeAndInitialize<CloudExperienceHostWAMExecuteCommand,IUnknown,>(&v10);
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
0x140008c90  mov     [rsp+arg_0], rbx
0x140008c95  mov     [rsp+arg_10], rsi
0x140008c9a  push    rdi
0x140008c9b  sub     rsp, 20h
0x140008c9f  mov     rdi, r9
0x140008ca2  mov     rsi, r8
0x140008ca5  mov     qword ptr [r9], 0
0x140008cac  test    rdx, rdx
0x140008caf  jz      short loc_140008CC4
0x140008cb1  xor     edx, edx
0x140008cb3  mov     ebx, 80040110h
0x140008cb8  mov     ecx, ebx
0x140008cba  call    cs:__imp_RoOriginateError
0x140008cc0  mov     eax, ebx
0x140008cc2  jmp     short loc_140008D28
0x140008cc4  mov     [rsp+28h+arg_8], 0
0x140008ccd  lea     rcx, [rsp+28h+arg_8]
0x140008cd2  call    ??$MakeAndInitialize@VCloudExperienceHostWAMExecuteCommand@@UIUnknown@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CloudExperienceHostWAMExecuteCommand,IUnknown,>(IUnknown * *)
0x140008cd7  mov     ebx, eax
0x140008cd9  test    eax, eax
0x140008cdb  jns     short loc_140008CF6
0x140008cdd  mov     rcx, [rsp+28h+arg_8]
0x140008ce2  test    rcx, rcx
0x140008ce5  jz      short loc_140008CF4
0x140008ce7  mov     rdx, [rcx]
0x140008cea  mov     rax, [rdx+10h]
0x140008cee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008cf3  nop
0x140008cf4  jmp     short loc_140008CC0
0x140008cf6  mov     rbx, [rsp+28h+arg_8]
0x140008cfb  mov     rax, [rbx]
0x140008cfe  mov     r8, rdi
0x140008d01  mov     rdx, rsi
0x140008d04  mov     rcx, rbx
0x140008d07  mov     rax, [rax]
0x140008d0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008d0f  mov     edi, eax
0x140008d11  test    rbx, rbx
0x140008d14  jz      short loc_140008D26
0x140008d16  mov     rdx, [rbx]
0x140008d19  mov     rcx, rbx
0x140008d1c  mov     rax, [rdx+10h]
0x140008d20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008d25  nop
0x140008d26  mov     eax, edi
0x140008d28  mov     rbx, [rsp+28h+arg_0]
0x140008d2d  mov     rsi, [rsp+28h+arg_10]
0x140008d32  add     rsp, 20h
0x140008d36  pop     rdi
0x140008d37  retn
```
