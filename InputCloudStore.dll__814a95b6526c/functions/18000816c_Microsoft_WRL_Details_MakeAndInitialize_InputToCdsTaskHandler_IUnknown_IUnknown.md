# Microsoft::WRL::Details::MakeAndInitialize<InputToCdsTaskHandler,IUnknown,>(IUnknown * *)

- ea: `0x18000816c`
- end: `0x18000826b`
- name: `??$MakeAndInitialize@VInputToCdsTaskHandler@@UIUnknown@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIUnknown@@@Z`
- size: `255`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180008740`

## callees

- `0x18000396c`
- `0x18000816c`
- `0x1800082c0`
- `0x180008408`
- `0x180008634`
- `0x180008ad8`
- `0x180008db0`
- `0x180031010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::MakeAndInitialize<InputToCdsTaskHandler,IUnknown,>(void **a1)
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
    *v3 = &InputToCdsTaskHandler::`vftable'{for `ITaskHandler'};
    v3[1] = &InputToCdsTaskHandler::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
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
0x18000816c  mov     [rsp+arg_8], rbx
0x180008171  mov     [rsp+arg_10], rsi
0x180008176  push    rdi
0x180008177  sub     rsp, 20h
0x18000817b  mov     rsi, rcx
0x18000817e  mov     qword ptr [rcx], 0
0x180008185  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000818c  mov     ecx, 30h ; '0'; unsigned __int64
0x180008191  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180008196  mov     rbx, rax
0x180008199  mov     [rsp+28h+arg_0], rax
0x18000819e  test    rax, rax
0x1800081a1  jnz     short loc_1800081AD
0x1800081a3  mov     edi, 8007000Eh
0x1800081a8  jmp     loc_18000824F
0x1800081ad  mov     rcx, rbx
0x1800081b0  call    ??0?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UITaskHandler@@VFtmBase@23@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ITaskHandler,Microsoft::WRL::FtmBase>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ITaskHandler,Microsoft::WRL::FtmBase>(void)
0x1800081b5  lea     rax, ??_7InputToCdsTaskHandler@@6BITaskHandler@@@; const InputToCdsTaskHandler::`vftable'{for `ITaskHandler'}
0x1800081bc  mov     [rbx], rax
0x1800081bf  lea     rax, ??_7InputToCdsTaskHandler@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const InputToCdsTaskHandler::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1800081c6  mov     [rbx+8], rax
0x1800081ca  mov     [rsp+28h+arg_0], 0
0x1800081d3  mov     qword ptr [rsi], 0
0x1800081da  lea     rcx, _GUID_00000000_0000_0000_c000_000000000046
0x1800081e1  mov     rdx, rcx
0x1800081e4  call    InlineIsEqualGUID
0x1800081e9  test    eax, eax
0x1800081eb  jnz     short loc_180008233
0x1800081ed  lea     rdx, _GUID_839d7762_5121_4009_9234_4f0d19394f04
0x1800081f4  call    InlineIsEqualGUID
0x1800081f9  test    eax, eax
0x1800081fb  jz      short loc_180008204
0x1800081fd  mov     [rsi], rbx
0x180008200  xor     edi, edi
0x180008202  jmp     short loc_180008222
0x180008204  mov     r8, rsi; void **
0x180008207  mov     rdx, rcx; struct _GUID *
0x18000820a  lea     rcx, [rbx+8]; this
0x18000820e  call    ?CanCastTo@FtmBase@WRL@Microsoft@@IEAAJAEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::FtmBase::CanCastTo(_GUID const &,void * *)
0x180008213  mov     edi, 80004002h
0x180008218  cmp     eax, edi
0x18000821a  jz      short loc_180008247
0x18000821c  mov     edi, eax
0x18000821e  test    eax, eax
0x180008220  js      short loc_180008247
0x180008222  mov     rcx, [rsi]
0x180008225  mov     rax, [rcx]
0x180008228  mov     rax, [rax+8]
0x18000822c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008231  jmp     short loc_180008247
0x180008233  mov     [rsi], rbx
0x180008236  mov     rax, [rbx]
0x180008239  mov     rcx, rbx
0x18000823c  mov     rax, [rax+8]
0x180008240  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008245  xor     edi, edi
0x180008247  mov     rcx, rbx
0x18000824a  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UITaskHandler@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ITaskHandler,Microsoft::WRL::FtmBase>::Release(void)
0x18000824f  lea     rcx, [rsp+28h+arg_0]
0x180008254  call    ??1?$MakeAllocator@VCdsToInputTaskHandler@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<CdsToInputTaskHandler>::~MakeAllocator<CdsToInputTaskHandler>(void)
0x180008259  mov     eax, edi
0x18000825b  mov     rbx, [rsp+28h+arg_8]
0x180008260  mov     rsi, [rsp+28h+arg_10]
0x180008265  add     rsp, 20h
0x180008269  pop     rdi
0x18000826a  retn
```
