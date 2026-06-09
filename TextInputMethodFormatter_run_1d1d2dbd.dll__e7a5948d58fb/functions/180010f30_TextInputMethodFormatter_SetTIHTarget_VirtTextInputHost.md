# TextInputMethodFormatter::SetTIHTarget(VirtTextInputHost *)

- ea: `0x180010f30`
- end: `0x180011143`
- name: `?SetTIHTarget@TextInputMethodFormatter@@UEAAJPEAVVirtTextInputHost@@@Z`
- size: `531`
- prototype: `int(TextInputMethodFormatter *__hidden this, struct VirtTextInputHost *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180002270`
- `0x18000271c`
- `0x18000275c`
- `0x180009924`
- `0x180010f30`
- `0x180012030`
- `0x180012074`
- `0x180058010`

## string_xrefs

- `0x180011131`: `mincore\textinput\dev\virtualization\textinputmethodformatter\dll\textinputmethodformatter.cpp`
- `0x18001111f`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall TextInputMethodFormatter::SetTIHTarget(TextInputMethodFormatter *this, struct VirtTextInputHost *a2)
{
  _DWORD *v4; // rbx
  _DWORD *v5; // rax
  _DWORD *v6; // rdi
  __int64 v7; // r9
  __int64 v8; // rcx
  int v9; // eax
  _QWORD *v10; // rsi
  __int64 v11; // r14
  __int64 v12; // rdi
  void *v13; // rcx
  int v15; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  __int64 v17; // [rsp+50h] [rbp+18h] BYREF

  v17 = 0;
  v4 = 0;
  v5 = operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
  v6 = v5;
  if ( v5 )
  {
    v5[3] = 1;
    *(_QWORD *)v5 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IRemoteTextInputHost>::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *(_QWORD *)v6 = &VirtTextInputHostProxy::`vftable';
    *((_QWORD *)v6 + 3) = 0;
    v6[8] = 0;
    *((_QWORD *)v6 + 2) = a2;
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v6 + 8LL))(v6);
    v4 = v6;
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v6 + 16LL))(v6);
    v7 = 0;
  }
  else
  {
    v7 = 2147942414LL;
  }
  if ( (int)v7 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x1F3,
      (unsigned int)"mincore\\textinput\\dev\\virtualization\\textinputmethodformatter\\dll\\textinputmethodformatter.cpp",
      (const char *)v7,
      v15);
  v8 = v17;
  v17 = 0;
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  v9 = (**(__int64 (__fastcall ***)(_DWORD *, GUID *, __int64 *))v4)(
         v4,
         &GUID_35375a37_d142_48fb_8d8e_f0c709d24f61,
         &v17);
  if ( v9 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1CBE,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)v9,
      v15);
  (*(void (__fastcall **)(_QWORD, _DWORD *))(**((_QWORD **)this + 21) + 32LL))(*((_QWORD *)this + 21), v4);
  v10 = operator new(0x28u);
  *v10 = &PduRecv_ToIRemoteTextInputHost::`vftable';
  v10[1] = 0;
  v10[2] = 0;
  v10[3] = 0;
  v10[4] = 0;
  v11 = v17;
  std::shared_ptr<IVirtualizedTextDataSender>::operator=(v10 + 1, (char *)this + 168);
  v12 = v10[3];
  v10[3] = v11;
  if ( v11 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11);
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  v13 = (void *)*((_QWORD *)this + 14);
  *((_QWORD *)this + 14) = v10;
  if ( v13 )
    operator delete(v13);
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v4 + 16LL))(v4);
  if ( v17 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  return 0;
}

```

## disassembly

```asm
0x180010f30  mov     [rsp+arg_0], rbx
0x180010f35  mov     [rsp+arg_8], rbp
0x180010f3a  push    rsi
0x180010f3b  push    rdi
0x180010f3c  push    r14; int
0x180010f3e  sub     rsp, 20h
0x180010f42  mov     rsi, rdx
0x180010f45  mov     rbp, rcx
0x180010f48  mov     [rsp+38h+arg_10], 0
0x180010f51  xor     ebx, ebx
0x180010f53  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180010f5a  lea     r14d, [rbx+28h]
0x180010f5e  mov     ecx, r14d; unsigned __int64
0x180010f61  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180010f66  mov     rdi, rax
0x180010f69  test    rax, rax
0x180010f6c  jnz     short loc_180010F76
0x180010f6e  mov     r9d, 8007000Eh
0x180010f74  jmp     short loc_180010FE3
0x180010f76  mov     dword ptr [rax+0Ch], 1
0x180010f7d  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIRemoteTextInputHost@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IRemoteTextInputHost>::`vftable'
0x180010f84  mov     [rdi], rax
0x180010f87  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180010f8e  test    rcx, rcx
0x180010f91  jz      short loc_180010FA0
0x180010f93  mov     rax, [rcx]
0x180010f96  mov     rax, [rax+8]
0x180010f9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f9f  nop
0x180010fa0  lea     rax, ??_7VirtTextInputHostProxy@@6B@; const VirtTextInputHostProxy::`vftable'
0x180010fa7  mov     [rdi], rax
0x180010faa  mov     qword ptr [rdi+18h], 0
0x180010fb2  mov     dword ptr [rdi+20h], 0
0x180010fb9  mov     [rdi+10h], rsi
0x180010fbd  mov     rax, [rdi]
0x180010fc0  mov     rcx, rdi
0x180010fc3  mov     rax, [rax+8]
0x180010fc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010fcc  nop
0x180010fcd  mov     rbx, rdi
0x180010fd0  mov     rax, [rdi]
0x180010fd3  mov     rcx, rdi
0x180010fd6  mov     rax, [rax+10h]
0x180010fda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010fdf  nop
0x180010fe0  xor     r9d, r9d; char *
0x180010fe3  mov     rcx, [rsp+38h]; this
0x180010fe8  test    r9d, r9d
0x180010feb  js      loc_180011131
0x180010ff1  mov     rcx, [rsp+38h+arg_10]
0x180010ff6  mov     [rsp+38h+arg_10], 0
0x180010fff  test    rcx, rcx
0x180011002  jz      short loc_180011011
0x180011004  mov     rax, [rcx]
0x180011007  mov     rax, [rax+10h]
0x18001100b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011010  nop
0x180011011  mov     rax, [rbx]
0x180011014  lea     r8, [rsp+38h+arg_10]
0x180011019  lea     rdx, _GUID_35375a37_d142_48fb_8d8e_f0c709d24f61
0x180011020  mov     rcx, rbx
0x180011023  mov     rax, [rax]
0x180011026  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001102b  mov     rcx, [rsp+38h]; this
0x180011030  test    eax, eax
0x180011032  js      loc_18001111C
0x180011038  lea     rdi, [rbp+0A8h]
0x18001103f  mov     rcx, [rdi]
0x180011042  mov     rax, [rcx]
0x180011045  mov     rdx, rbx
0x180011048  mov     rax, [rax+20h]
0x18001104c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011051  mov     rcx, r14; Size
0x180011054  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011059  mov     rsi, rax
0x18001105c  lea     rax, ??_7PduRecv_ToIRemoteTextInputHost@@6B@; const PduRecv_ToIRemoteTextInputHost::`vftable'
0x180011063  mov     [rsi], rax
0x180011066  lea     rcx, [rsi+8]
0x18001106a  mov     qword ptr [rcx], 0
0x180011071  mov     qword ptr [rcx+8], 0
0x180011079  mov     qword ptr [rsi+18h], 0
0x180011081  mov     qword ptr [rsi+20h], 0
0x180011089  mov     r14, [rsp+38h+arg_10]
0x18001108e  mov     rdx, rdi
0x180011091  call    ??4?$shared_ptr@UIVirtualizedTextDataSender@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<IVirtualizedTextDataSender>::operator=(std::shared_ptr<IVirtualizedTextDataSender> const &)
0x180011096  nop
0x180011097  mov     rdi, [rsi+18h]
0x18001109b  mov     [rsi+18h], r14
0x18001109f  test    r14, r14
0x1800110a2  jz      short loc_1800110B3
0x1800110a4  mov     rax, [r14]
0x1800110a7  mov     rcx, r14
0x1800110aa  mov     rax, [rax+8]
0x1800110ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800110b3  test    rdi, rdi
0x1800110b6  jz      short loc_1800110C8
0x1800110b8  mov     rax, [rdi]
0x1800110bb  mov     rcx, rdi
0x1800110be  mov     rax, [rax+10h]
0x1800110c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800110c7  nop
0x1800110c8  mov     rcx, [rbp+70h]; Block
0x1800110cc  mov     [rbp+70h], rsi
0x1800110d0  test    rcx, rcx
0x1800110d3  jz      short loc_1800110E0
0x1800110d5  mov     edx, 8
0x1800110da  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800110df  nop
0x1800110e0  mov     rax, [rbx]
0x1800110e3  mov     rcx, rbx
0x1800110e6  mov     rax, [rax+10h]
0x1800110ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800110ef  nop
0x1800110f0  mov     rcx, [rsp+38h+arg_10]
0x1800110f5  test    rcx, rcx
0x1800110f8  jz      short loc_180011107
0x1800110fa  mov     rax, [rcx]
0x1800110fd  mov     rax, [rax+10h]
0x180011101  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011106  nop
0x180011107  xor     eax, eax
0x180011109  mov     rbx, [rsp+38h+arg_0]
0x18001110e  mov     rbp, [rsp+38h+arg_8]
0x180011113  add     rsp, 20h
0x180011117  pop     r14
0x180011119  pop     rdi
0x18001111a  pop     rsi
0x18001111b  retn
0x18001111c  mov     r9d, eax; char *
0x18001111f  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180011126  mov     edx, 1CBEh; void *
0x18001112b  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180011131  lea     r8, aMincoreTextinp_5; "mincore\\textinput\\dev\\virtualization"...
0x180011138  mov     edx, 1F3h; void *
0x18001113d  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
```
