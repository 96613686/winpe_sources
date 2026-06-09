# CShutdownPopupCommand::get_Handler(IPopupCommandHandler * *)

- ea: `0x140008fb0`
- end: `0x14000905d`
- name: `?get_Handler@CShutdownPopupCommand@@UEAAJPEAPEAUIPopupCommandHandler@@@Z`
- size: `173`
- prototype: `__int64 __fastcall(CShutdownPopupCommand *__hidden this, struct IPopupCommandHandler **)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1400014c8`
- `0x1400080f4`
- `0x140008fb0`
- `0x14000a010`

## string_xrefs

- `0x140009039`: `drivers\mobilepc\location\product\winactiondialog\lib\popupcommand.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CShutdownPopupCommand::get_Handler(CShutdownPopupCommand *this, struct IPopupCommandHandler **a2)
{
  _DWORD *v4; // rax
  _DWORD *v5; // rbx
  __int64 v6; // rbp
  __int64 v7; // rdi
  int v9; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *a2 = 0;
  v4 = operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
  v5 = v4;
  if ( v4 )
  {
    v6 = *((_QWORD *)this + 4);
    v7 = *((_QWORD *)this + 3);
    v4[3] = 1;
    *(_QWORD *)v4 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IPopupCommandHandler>::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *(_QWORD *)v5 = &CShutdownPopupCommandHandler::`vftable';
    *((_QWORD *)v5 + 2) = v7;
    *((_QWORD *)v5 + 3) = v6;
  }
  else
  {
    v5 = 0;
  }
  if ( v5 )
  {
    *a2 = (struct IPopupCommandHandler *)v5;
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x24,
      (unsigned int)"drivers\\mobilepc\\location\\product\\winactiondialog\\lib\\popupcommand.cpp",
      (const char *)0x8007000ELL,
      v9);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x140008fb0  push    rbx
0x140008fb2  push    rbp
0x140008fb3  push    rsi
0x140008fb4  push    rdi
0x140008fb5  sub     rsp, 28h
0x140008fb9  mov     rsi, rdx
0x140008fbc  mov     rdi, rcx
0x140008fbf  mov     qword ptr [rdx], 0
0x140008fc6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140008fcd  mov     ecx, 20h ; ' '; unsigned __int64
0x140008fd2  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140008fd7  mov     rbx, rax
0x140008fda  test    rax, rax
0x140008fdd  jz      short loc_140009025
0x140008fdf  mov     rbp, [rdi+20h]
0x140008fe3  mov     rdi, [rdi+18h]
0x140008fe7  mov     dword ptr [rax+0Ch], 1
0x140008fee  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIPopupCommandHandler@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IPopupCommandHandler>::`vftable'
0x140008ff5  mov     [rbx], rax
0x140008ff8  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x140008fff  test    rcx, rcx
0x140009002  jz      short loc_140009011
0x140009004  mov     rax, [rcx]
0x140009007  mov     rax, [rax+8]
0x14000900b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009010  nop
0x140009011  lea     rax, ??_7CShutdownPopupCommandHandler@@6B@; const CShutdownPopupCommandHandler::`vftable'
0x140009018  mov     [rbx], rax
0x14000901b  mov     [rbx+10h], rdi
0x14000901f  mov     [rbx+18h], rbp
0x140009023  jmp     short loc_140009027
0x140009025  xor     ebx, ebx
0x140009027  test    rbx, rbx
0x14000902a  jnz     short loc_14000904F
0x14000902c  mov     rcx, [rsp+48h]; this
0x140009031  mov     ebx, 8007000Eh
0x140009036  mov     r9d, ebx; char *
0x140009039  lea     r8, aDriversMobilep_0; "drivers\\mobilepc\\location\\product\\w"...
0x140009040  mov     edx, 24h ; '$'; void *
0x140009045  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000904a  nop
0x14000904b  mov     eax, ebx
0x14000904d  jmp     short loc_140009054
0x14000904f  mov     [rsi], rbx
0x140009052  xor     eax, eax
0x140009054  add     rsp, 28h
0x140009058  pop     rdi
0x140009059  pop     rsi
0x14000905a  pop     rbp
0x14000905b  pop     rbx
0x14000905c  retn
```
