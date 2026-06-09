# CLicensingUIPopupCommand::get_Handler(IPopupCommandHandler * *)

- ea: `0x18000b310`
- end: `0x18000b3b3`
- name: `?get_Handler@CLicensingUIPopupCommand@@UEAAJPEAPEAUIPopupCommandHandler@@@Z`
- size: `163`
- prototype: `__int64 __fastcall(CLicensingUIPopupCommand *__hidden this, struct IPopupCommandHandler **)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001ea8`
- `0x1800090dc`
- `0x180009480`
- `0x18000b310`
- `0x180023010`

## pseudocode

```c
__int64 __fastcall CLicensingUIPopupCommand::get_Handler(
        CLicensingUIPopupCommand *this,
        struct IPopupCommandHandler **a2)
{
  unsigned int v4; // ebx
  _DWORD *v5; // rax
  _DWORD *v6; // rdi
  __int64 v7; // rbp
  __int64 v8; // rbx
  struct Microsoft::WRL::Details::ModuleBase *v9; // rcx

  if ( !a2 )
  {
    v4 = -2147024809;
LABEL_8:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v4);
    goto LABEL_9;
  }
  *a2 = 0;
  v5 = operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
  v6 = v5;
  if ( !v5 )
  {
    v4 = -2147024882;
    goto LABEL_8;
  }
  v7 = *((_QWORD *)this + 4);
  v8 = *((_QWORD *)this + 3);
  v9 = Microsoft::WRL::Details::ModuleBase::module_;
  v5[3] = 1;
  *(_QWORD *)v5 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IPopupCommandHandler>::`vftable';
  if ( v9 )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)v9 + 8LL))(v9);
  *((_QWORD *)v6 + 2) = v8;
  *(_QWORD *)v6 = &CLicensingUIPopupCommandHandler::`vftable';
  v4 = 0;
  *((_QWORD *)v6 + 3) = v7;
  *a2 = (struct IPopupCommandHandler *)v6;
LABEL_9:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v4);
  return v4;
}

```

## disassembly

```asm
0x18000b310  push    rbx
0x18000b312  push    rbp
0x18000b313  push    rsi
0x18000b314  push    rdi
0x18000b315  sub     rsp, 28h
0x18000b319  mov     rsi, rdx
0x18000b31c  mov     rbx, rcx
0x18000b31f  test    rdx, rdx
0x18000b322  jnz     short loc_18000B32B
0x18000b324  mov     ebx, 80070057h
0x18000b329  jmp     short loc_18000B39A
0x18000b32b  mov     qword ptr [rdx], 0
0x18000b332  mov     ecx, 20h ; ' '; unsigned __int64
0x18000b337  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000b33e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000b343  mov     rdi, rax
0x18000b346  test    rax, rax
0x18000b349  jz      short loc_18000B395
0x18000b34b  mov     rbp, [rbx+20h]
0x18000b34f  mov     rbx, [rbx+18h]
0x18000b353  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000b35a  mov     dword ptr [rax+0Ch], 1
0x18000b361  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIPopupCommandHandler@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IPopupCommandHandler>::`vftable'
0x18000b368  mov     [rdi], rax
0x18000b36b  test    rcx, rcx
0x18000b36e  jz      short loc_18000B37C
0x18000b370  mov     rax, [rcx]
0x18000b373  mov     rax, [rax+8]
0x18000b377  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b37c  mov     [rdi+10h], rbx
0x18000b380  lea     rax, ??_7CLicensingUIPopupCommandHandler@@6B@; const CLicensingUIPopupCommandHandler::`vftable'
0x18000b387  mov     [rdi], rax
0x18000b38a  xor     ebx, ebx
0x18000b38c  mov     [rdi+18h], rbp
0x18000b390  mov     [rsi], rdi
0x18000b393  jmp     short loc_18000B3A1
0x18000b395  mov     ebx, 8007000Eh
0x18000b39a  mov     ecx, ebx
0x18000b39c  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000b3a1  mov     ecx, ebx
0x18000b3a3  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000b3a8  mov     eax, ebx
0x18000b3aa  add     rsp, 28h
0x18000b3ae  pop     rdi
0x18000b3af  pop     rsi
0x18000b3b0  pop     rbp
0x18000b3b1  pop     rbx
0x18000b3b2  retn
```
