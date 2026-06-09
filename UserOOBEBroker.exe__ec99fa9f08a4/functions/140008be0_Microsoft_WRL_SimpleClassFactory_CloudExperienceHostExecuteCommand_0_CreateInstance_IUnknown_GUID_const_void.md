# Microsoft::WRL::SimpleClassFactory<CloudExperienceHostExecuteCommand,0>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x140008be0`
- end: `0x140008c88`
- name: `?CreateInstance@?$SimpleClassFactory@VCloudExperienceHostExecuteCommand@@$0A@@WRL@Microsoft@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `168`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1400071ac`
- `0x140008be0`
- `0x14000f010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x140008c0a`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x140008c0a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::WRL::SimpleClassFactory<CloudExperienceHostExecuteCommand,0>::CreateInstance(
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
  v6 = Microsoft::WRL::Details::MakeAndInitialize<CloudExperienceHostExecuteCommand,IUnknown,>(&v10);
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
0x140008be0  mov     [rsp+arg_0], rbx
0x140008be5  mov     [rsp+arg_10], rsi
0x140008bea  push    rdi
0x140008beb  sub     rsp, 20h
0x140008bef  mov     rdi, r9
0x140008bf2  mov     rsi, r8
0x140008bf5  mov     qword ptr [r9], 0
0x140008bfc  test    rdx, rdx
0x140008bff  jz      short loc_140008C14
0x140008c01  xor     edx, edx
0x140008c03  mov     ebx, 80040110h
0x140008c08  mov     ecx, ebx
0x140008c0a  call    cs:__imp_RoOriginateError
0x140008c10  mov     eax, ebx
0x140008c12  jmp     short loc_140008C78
0x140008c14  mov     [rsp+28h+arg_8], 0
0x140008c1d  lea     rcx, [rsp+28h+arg_8]
0x140008c22  call    ??$MakeAndInitialize@VCloudExperienceHostExecuteCommand@@UIUnknown@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CloudExperienceHostExecuteCommand,IUnknown,>(IUnknown * *)
0x140008c27  mov     ebx, eax
0x140008c29  test    eax, eax
0x140008c2b  jns     short loc_140008C46
0x140008c2d  mov     rcx, [rsp+28h+arg_8]
0x140008c32  test    rcx, rcx
0x140008c35  jz      short loc_140008C44
0x140008c37  mov     rdx, [rcx]
0x140008c3a  mov     rax, [rdx+10h]
0x140008c3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008c43  nop
0x140008c44  jmp     short loc_140008C10
0x140008c46  mov     rbx, [rsp+28h+arg_8]
0x140008c4b  mov     rax, [rbx]
0x140008c4e  mov     r8, rdi
0x140008c51  mov     rdx, rsi
0x140008c54  mov     rcx, rbx
0x140008c57  mov     rax, [rax]
0x140008c5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008c5f  mov     edi, eax
0x140008c61  test    rbx, rbx
0x140008c64  jz      short loc_140008C76
0x140008c66  mov     rdx, [rbx]
0x140008c69  mov     rcx, rbx
0x140008c6c  mov     rax, [rdx+10h]
0x140008c70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008c75  nop
0x140008c76  mov     eax, edi
0x140008c78  mov     rbx, [rsp+28h+arg_0]
0x140008c7d  mov     rsi, [rsp+28h+arg_10]
0x140008c82  add     rsp, 20h
0x140008c86  pop     rdi
0x140008c87  retn
```
