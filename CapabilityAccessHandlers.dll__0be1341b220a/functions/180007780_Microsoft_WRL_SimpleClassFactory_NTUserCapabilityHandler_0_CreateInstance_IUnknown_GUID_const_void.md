# Microsoft::WRL::SimpleClassFactory<NTUserCapabilityHandler,0>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180007780`
- end: `0x180007828`
- name: `?CreateInstance@?$SimpleClassFactory@VNTUserCapabilityHandler@@$0A@@WRL@Microsoft@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `168`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000624c`
- `0x180007780`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800077aa`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800077aa`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::SimpleClassFactory<NTUserCapabilityHandler,0>::CreateInstance(
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
  v6 = Microsoft::WRL::Details::MakeAndInitialize<NTUserCapabilityHandler,IUnknown,>(&v10);
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
0x180007780  mov     [rsp+arg_0], rbx
0x180007785  mov     [rsp+arg_10], rsi
0x18000778a  push    rdi
0x18000778b  sub     rsp, 20h
0x18000778f  mov     rdi, r9
0x180007792  mov     rsi, r8
0x180007795  mov     qword ptr [r9], 0
0x18000779c  test    rdx, rdx
0x18000779f  jz      short loc_1800077B4
0x1800077a1  xor     edx, edx
0x1800077a3  mov     ebx, 80040110h
0x1800077a8  mov     ecx, ebx
0x1800077aa  call    cs:__imp_RoOriginateError
0x1800077b0  mov     eax, ebx
0x1800077b2  jmp     short loc_180007818
0x1800077b4  mov     [rsp+28h+arg_8], 0
0x1800077bd  lea     rcx, [rsp+28h+arg_8]
0x1800077c2  call    ??$MakeAndInitialize@VNTUserCapabilityHandler@@UIUnknown@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::MakeAndInitialize<NTUserCapabilityHandler,IUnknown,>(IUnknown * *)
0x1800077c7  mov     ebx, eax
0x1800077c9  test    eax, eax
0x1800077cb  jns     short loc_1800077E6
0x1800077cd  mov     rcx, [rsp+28h+arg_8]
0x1800077d2  test    rcx, rcx
0x1800077d5  jz      short loc_1800077E4
0x1800077d7  mov     rdx, [rcx]
0x1800077da  mov     rax, [rdx+10h]
0x1800077de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077e3  nop
0x1800077e4  jmp     short loc_1800077B0
0x1800077e6  mov     rbx, [rsp+28h+arg_8]
0x1800077eb  mov     rax, [rbx]
0x1800077ee  mov     r8, rdi
0x1800077f1  mov     rdx, rsi
0x1800077f4  mov     rcx, rbx
0x1800077f7  mov     rax, [rax]
0x1800077fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077ff  mov     edi, eax
0x180007801  test    rbx, rbx
0x180007804  jz      short loc_180007816
0x180007806  mov     rdx, [rbx]
0x180007809  mov     rcx, rbx
0x18000780c  mov     rax, [rdx+10h]
0x180007810  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007815  nop
0x180007816  mov     eax, edi
0x180007818  mov     rbx, [rsp+28h+arg_0]
0x18000781d  mov     rsi, [rsp+28h+arg_10]
0x180007822  add     rsp, 20h
0x180007826  pop     rdi
0x180007827  retn
```
