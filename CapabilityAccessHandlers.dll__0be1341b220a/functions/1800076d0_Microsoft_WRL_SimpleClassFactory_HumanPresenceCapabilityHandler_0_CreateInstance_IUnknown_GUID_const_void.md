# Microsoft::WRL::SimpleClassFactory<HumanPresenceCapabilityHandler,0>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x1800076d0`
- end: `0x180007778`
- name: `?CreateInstance@?$SimpleClassFactory@VHumanPresenceCapabilityHandler@@$0A@@WRL@Microsoft@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `168`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180006150`
- `0x1800076d0`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800076fa`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800076fa`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::SimpleClassFactory<HumanPresenceCapabilityHandler,0>::CreateInstance(
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
  v6 = Microsoft::WRL::Details::MakeAndInitialize<HumanPresenceCapabilityHandler,IUnknown,>(&v10);
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
0x1800076d0  mov     [rsp+arg_0], rbx
0x1800076d5  mov     [rsp+arg_10], rsi
0x1800076da  push    rdi
0x1800076db  sub     rsp, 20h
0x1800076df  mov     rdi, r9
0x1800076e2  mov     rsi, r8
0x1800076e5  mov     qword ptr [r9], 0
0x1800076ec  test    rdx, rdx
0x1800076ef  jz      short loc_180007704
0x1800076f1  xor     edx, edx
0x1800076f3  mov     ebx, 80040110h
0x1800076f8  mov     ecx, ebx
0x1800076fa  call    cs:__imp_RoOriginateError
0x180007700  mov     eax, ebx
0x180007702  jmp     short loc_180007768
0x180007704  mov     [rsp+28h+arg_8], 0
0x18000770d  lea     rcx, [rsp+28h+arg_8]
0x180007712  call    ??$MakeAndInitialize@VHumanPresenceCapabilityHandler@@UIUnknown@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::MakeAndInitialize<HumanPresenceCapabilityHandler,IUnknown,>(IUnknown * *)
0x180007717  mov     ebx, eax
0x180007719  test    eax, eax
0x18000771b  jns     short loc_180007736
0x18000771d  mov     rcx, [rsp+28h+arg_8]
0x180007722  test    rcx, rcx
0x180007725  jz      short loc_180007734
0x180007727  mov     rdx, [rcx]
0x18000772a  mov     rax, [rdx+10h]
0x18000772e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007733  nop
0x180007734  jmp     short loc_180007700
0x180007736  mov     rbx, [rsp+28h+arg_8]
0x18000773b  mov     rax, [rbx]
0x18000773e  mov     r8, rdi
0x180007741  mov     rdx, rsi
0x180007744  mov     rcx, rbx
0x180007747  mov     rax, [rax]
0x18000774a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000774f  mov     edi, eax
0x180007751  test    rbx, rbx
0x180007754  jz      short loc_180007766
0x180007756  mov     rdx, [rbx]
0x180007759  mov     rcx, rbx
0x18000775c  mov     rax, [rdx+10h]
0x180007760  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007765  nop
0x180007766  mov     eax, edi
0x180007768  mov     rbx, [rsp+28h+arg_0]
0x18000776d  mov     rsi, [rsp+28h+arg_10]
0x180007772  add     rsp, 20h
0x180007776  pop     rdi
0x180007777  retn
```
