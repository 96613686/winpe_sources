# Microsoft::WRL::SimpleClassFactory<HidDeviceCapabilityHandler,0>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x1800026f0`
- end: `0x180002793`
- name: `?CreateInstance@?$SimpleClassFactory@VHidDeviceCapabilityHandler@@$0A@@WRL@Microsoft@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `163`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800026f0`
- `0x18000279c`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180002757`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180002757`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::SimpleClassFactory<HidDeviceCapabilityHandler,0>::CreateInstance(
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
  v6 = Microsoft::WRL::Details::MakeAndInitialize<HidDeviceCapabilityHandler,IUnknown,>(&v10);
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
0x1800026f0  mov     rax, rsp
0x1800026f3  mov     [rax+8], rbx
0x1800026f7  mov     [rax+18h], rsi
0x1800026fb  push    rdi
0x1800026fc  sub     rsp, 20h
0x180002700  mov     rdi, r9
0x180002703  mov     rsi, r8
0x180002706  mov     qword ptr [r9], 0
0x18000270d  test    rdx, rdx
0x180002710  jnz     short loc_18000274E
0x180002712  mov     [rax+10h], rdx
0x180002716  lea     rcx, [rax+10h]
0x18000271a  call    ??$MakeAndInitialize@VHidDeviceCapabilityHandler@@UIUnknown@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::MakeAndInitialize<HidDeviceCapabilityHandler,IUnknown,>(IUnknown * *)
0x18000271f  mov     ebx, eax
0x180002721  test    eax, eax
0x180002723  jns     short loc_18000275F
0x180002725  mov     rcx, [rsp+28h+arg_8]
0x18000272a  test    rcx, rcx
0x18000272d  jz      short loc_18000273C
0x18000272f  mov     rdx, [rcx]
0x180002732  mov     rax, [rdx+10h]
0x180002736  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000273b  nop
0x18000273c  mov     eax, ebx
0x18000273e  mov     rbx, [rsp+28h+arg_0]
0x180002743  mov     rsi, [rsp+28h+arg_10]
0x180002748  add     rsp, 20h
0x18000274c  pop     rdi
0x18000274d  retn
0x18000274e  xor     edx, edx
0x180002750  mov     ebx, 80040110h
0x180002755  mov     ecx, ebx
0x180002757  call    cs:__imp_RoOriginateError
0x18000275d  jmp     short loc_18000273C
0x18000275f  mov     rbx, [rsp+28h+arg_8]
0x180002764  mov     rax, [rbx]
0x180002767  mov     r8, rdi
0x18000276a  mov     rdx, rsi
0x18000276d  mov     rcx, rbx
0x180002770  mov     rax, [rax]
0x180002773  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002778  mov     edi, eax
0x18000277a  test    rbx, rbx
0x18000277d  jz      short loc_18000278F
0x18000277f  mov     rdx, [rbx]
0x180002782  mov     rcx, rbx
0x180002785  mov     rax, [rdx+10h]
0x180002789  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000278e  nop
0x18000278f  mov     eax, edi
0x180002791  jmp     short loc_18000273E
```
