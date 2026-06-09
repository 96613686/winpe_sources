# Microsoft::WRL::Details::MakeAndInitialize<CdsToInputTaskHandler,IUnknown,>(IUnknown * *)

- ea: `0x180008064`
- end: `0x180008163`
- name: `??$MakeAndInitialize@VCdsToInputTaskHandler@@UIUnknown@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIUnknown@@@Z`
- size: `255`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800086b0`

## callees

- `0x18000396c`
- `0x180008064`
- `0x1800082c0`
- `0x180008408`
- `0x180008634`
- `0x180008ad8`
- `0x180008db0`
- `0x180031010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::MakeAndInitialize<CdsToInputTaskHandler,IUnknown,>(void **a1)
{
  _QWORD *v2; // rax
  _QWORD *v3; // rbx
  unsigned int v4; // edi
  __int64 v5; // rcx
  const struct _GUID *v6; // rcx
  int CanCastTo; // eax
  _QWORD *v9; // [rsp+30h] [rbp+8h] BYREF

  *a1 = 0;
  v2 = operator new(0x30u, (const struct std::nothrow_t *)&std::nothrow);
  v3 = v2;
  v9 = v2;
  if ( v2 )
  {
    Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ITaskHandler,Microsoft::WRL::FtmBase>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ITaskHandler,Microsoft::WRL::FtmBase>(v2);
    *v3 = &CdsToInputTaskHandler::`vftable'{for `ITaskHandler'};
    v3[1] = &CdsToInputTaskHandler::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
    v9 = 0;
    *a1 = 0;
    if ( (unsigned int)InlineIsEqualGUID(
                         &GUID_00000000_0000_0000_c000_000000000046,
                         &GUID_00000000_0000_0000_c000_000000000046) )
    {
      *a1 = v3;
      (*(void (__fastcall **)(_QWORD *))(*v3 + 8LL))(v3);
      v4 = 0;
    }
    else
    {
      if ( (unsigned int)InlineIsEqualGUID(v5, &GUID_839d7762_5121_4009_9234_4f0d19394f04) )
      {
        *a1 = v3;
        v4 = 0;
      }
      else
      {
        CanCastTo = Microsoft::WRL::FtmBase::CanCastTo((Microsoft::WRL::FtmBase *)(v3 + 1), v6, a1);
        v4 = -2147467262;
        if ( CanCastTo == -2147467262 )
          goto LABEL_10;
        v4 = CanCastTo;
        if ( CanCastTo < 0 )
          goto LABEL_10;
      }
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a1 + 8LL))(*a1);
    }
LABEL_10:
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ITaskHandler,Microsoft::WRL::FtmBase>::Release(v3);
    goto LABEL_11;
  }
  v4 = -2147024882;
LABEL_11:
  Microsoft::WRL::Details::MakeAllocator<CdsToInputTaskHandler>::~MakeAllocator<CdsToInputTaskHandler>(&v9);
  return v4;
}

```

## disassembly

```asm
0x180008064  mov     [rsp+arg_8], rbx
0x180008069  mov     [rsp+arg_10], rsi
0x18000806e  push    rdi
0x18000806f  sub     rsp, 20h
0x180008073  mov     rsi, rcx
0x180008076  mov     qword ptr [rcx], 0
0x18000807d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180008084  mov     ecx, 30h ; '0'; unsigned __int64
0x180008089  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000808e  mov     rbx, rax
0x180008091  mov     [rsp+28h+arg_0], rax
0x180008096  test    rax, rax
0x180008099  jnz     short loc_1800080A5
0x18000809b  mov     edi, 8007000Eh
0x1800080a0  jmp     loc_180008147
0x1800080a5  mov     rcx, rbx
0x1800080a8  call    ??0?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UITaskHandler@@VFtmBase@23@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ITaskHandler,Microsoft::WRL::FtmBase>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ITaskHandler,Microsoft::WRL::FtmBase>(void)
0x1800080ad  lea     rax, ??_7CdsToInputTaskHandler@@6BITaskHandler@@@; const CdsToInputTaskHandler::`vftable'{for `ITaskHandler'}
0x1800080b4  mov     [rbx], rax
0x1800080b7  lea     rax, ??_7CdsToInputTaskHandler@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const CdsToInputTaskHandler::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1800080be  mov     [rbx+8], rax
0x1800080c2  mov     [rsp+28h+arg_0], 0
0x1800080cb  mov     qword ptr [rsi], 0
0x1800080d2  lea     rcx, _GUID_00000000_0000_0000_c000_000000000046
0x1800080d9  mov     rdx, rcx
0x1800080dc  call    InlineIsEqualGUID
0x1800080e1  test    eax, eax
0x1800080e3  jnz     short loc_18000812B
0x1800080e5  lea     rdx, _GUID_839d7762_5121_4009_9234_4f0d19394f04
0x1800080ec  call    InlineIsEqualGUID
0x1800080f1  test    eax, eax
0x1800080f3  jz      short loc_1800080FC
0x1800080f5  mov     [rsi], rbx
0x1800080f8  xor     edi, edi
0x1800080fa  jmp     short loc_18000811A
0x1800080fc  mov     r8, rsi; void **
0x1800080ff  mov     rdx, rcx; struct _GUID *
0x180008102  lea     rcx, [rbx+8]; this
0x180008106  call    ?CanCastTo@FtmBase@WRL@Microsoft@@IEAAJAEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::FtmBase::CanCastTo(_GUID const &,void * *)
0x18000810b  mov     edi, 80004002h
0x180008110  cmp     eax, edi
0x180008112  jz      short loc_18000813F
0x180008114  mov     edi, eax
0x180008116  test    eax, eax
0x180008118  js      short loc_18000813F
0x18000811a  mov     rcx, [rsi]
0x18000811d  mov     rax, [rcx]
0x180008120  mov     rax, [rax+8]
0x180008124  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008129  jmp     short loc_18000813F
0x18000812b  mov     [rsi], rbx
0x18000812e  mov     rax, [rbx]
0x180008131  mov     rcx, rbx
0x180008134  mov     rax, [rax+8]
0x180008138  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000813d  xor     edi, edi
0x18000813f  mov     rcx, rbx
0x180008142  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UITaskHandler@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ITaskHandler,Microsoft::WRL::FtmBase>::Release(void)
0x180008147  lea     rcx, [rsp+28h+arg_0]
0x18000814c  call    ??1?$MakeAllocator@VCdsToInputTaskHandler@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<CdsToInputTaskHandler>::~MakeAllocator<CdsToInputTaskHandler>(void)
0x180008151  mov     eax, edi
0x180008153  mov     rbx, [rsp+28h+arg_8]
0x180008158  mov     rsi, [rsp+28h+arg_10]
0x18000815d  add     rsp, 20h
0x180008161  pop     rdi
0x180008162  retn
```
