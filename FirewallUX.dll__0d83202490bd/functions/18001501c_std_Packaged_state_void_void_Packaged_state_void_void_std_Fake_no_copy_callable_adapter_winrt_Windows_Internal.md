# std::_Packaged_state<void (void)>::_Packaged_state<void (void)>(std::_Fake_no_copy_callable_adapter<`winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallDialogBase::CreateDialogAsync(bool)'::`2'::_lambda_1_> &&)

- ea: `0x18001501c`
- end: `0x180015105`
- name: `??$?0V?$_Fake_no_copy_callable_adapter@V_lambda_1_@?1??CreateDialogAsync@FirewallDialogBase@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@QEAAX_N@Z@@std@@$0A@@?$_Packaged_state@$$A6AXXZ@std@@QEAA@$$QEAV?$_Fake_no_copy_callable_adapter@V_lambda_1_@?1??CreateDialogAsync@FirewallDialogBase@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@QEAAX_N@Z@@1@@Z`
- size: `233`
- prototype: `__int64 __fastcall(__int64, _OWORD *)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18001510c`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180015050`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180015050`

## pseudocode

```c
__int64 __fastcall ____0V___Fake_no_copy_callable_adapter_V_lambda_1___1__CreateDialogAsync_FirewallDialogBase_implementation_Firewall_NetworkUX_Internal_Windows_winrt__QEAAX_N_Z__std___0A_____Packaged_state___A6AXXZ_std__QEAA___QEAV___Fake_no_copy_callable_adapter_V_lambda_1___1__CreateDialogAsync_FirewallDialogBase_implementation_Firewall_NetworkUX_Internal_Windows_winrt__QEAAX_N_Z__1__Z(
        __int64 a1,
        _OWORD *a2)
{
  _QWORD *v3; // rcx

  *(_QWORD *)(a1 + 8) = 1;
  *(_QWORD *)a1 = &std::_Associated_state<int>::`vftable';
  v3 = (_QWORD *)(a1 + 16);
  *v3 = 0;
  v3[1] = 0;
  __ExceptionPtrCreate(v3);
  *(_QWORD *)(a1 + 32) = 2;
  *(_OWORD *)(a1 + 56) = 0;
  *(_OWORD *)(a1 + 72) = 0;
  *(_OWORD *)(a1 + 88) = 0;
  *(_QWORD *)(a1 + 40) = 0;
  *(_QWORD *)(a1 + 48) = 0;
  *(_DWORD *)(a1 + 108) = 0;
  *(_DWORD *)(a1 + 104) = -1;
  *(_QWORD *)(a1 + 112) = 0;
  *(_QWORD *)(a1 + 120) = 0;
  *(_OWORD *)(a1 + 128) = 0;
  *(_OWORD *)(a1 + 144) = 0;
  *(_OWORD *)(a1 + 160) = 0;
  *(_QWORD *)(a1 + 176) = 0;
  *(_QWORD *)a1 = &std::_Packaged_state<void (void)>::`vftable';
  *(_BYTE *)(a1 + 184) = 0;
  *(_DWORD *)(a1 + 188) = 0;
  *(_WORD *)(a1 + 192) = 0;
  *(_BYTE *)(a1 + 194) = 0;
  *(_QWORD *)(a1 + 200) = 0;
  *(_QWORD *)(a1 + 264) = 0;
  *(_QWORD *)(a1 + 208) = &___7___Func_impl_no_alloc_V___Fake_no_copy_callable_adapter_V_lambda_1___1__CreateDialogAsync_FirewallDialogBase_implementation_Firewall_NetworkUX_Internal_Windows_winrt__QEAAX_N_Z__std__X__V_std__6B_;
  *(_OWORD *)(a1 + 216) = *a2;
  *(_QWORD *)(a1 + 264) = a1 + 208;
  return a1;
}

```

## disassembly

```asm
0x18001501c  mov     [rsp+arg_0], rbx
0x180015021  mov     [rsp+arg_8], rsi
0x180015026  push    rdi
0x180015027  sub     rsp, 20h
0x18001502b  lea     rax, ??_7?$_Associated_state@H@std@@6B@; const std::_Associated_state<int>::`vftable'
0x180015032  mov     qword ptr [rcx+8], 1
0x18001503a  mov     [rcx], rax
0x18001503d  mov     rdi, rcx
0x180015040  add     rcx, 10h
0x180015044  xor     esi, esi
0x180015046  mov     rbx, rdx
0x180015049  mov     [rcx], rsi
0x18001504c  mov     [rcx+8], rsi
0x180015050  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x180015056  mov     qword ptr [rdi+20h], 2
0x18001505e  lea     rcx, ??_7?$_Func_impl_no_alloc@V?$_Fake_no_copy_callable_adapter@V_lambda_1_@?1??CreateDialogAsync@FirewallDialogBase@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@QEAAX_N@Z@@std@@X$$V@std@@6B@; const std::_Func_impl_no_alloc<std::_Fake_no_copy_callable_adapter<`winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallDialogBase::CreateDialogAsync(bool)'::`2'::_lambda_1_>,void,>::`vftable'
0x180015065  xorps   xmm0, xmm0
0x180015068  xor     eax, eax
0x18001506a  movups  xmmword ptr [rdi+38h], xmm0
0x18001506e  movups  xmmword ptr [rdi+48h], xmm0
0x180015072  movups  xmmword ptr [rdi+58h], xmm0
0x180015076  mov     [rdi+28h], rsi
0x18001507a  mov     [rdi+30h], rsi
0x18001507e  mov     [rdi+6Ch], esi
0x180015081  mov     dword ptr [rdi+68h], 0FFFFFFFFh
0x180015088  mov     [rdi+70h], rsi
0x18001508c  mov     [rdi+78h], rsi
0x180015090  movups  xmmword ptr [rdi+80h], xmm0
0x180015097  movups  xmmword ptr [rdi+90h], xmm0
0x18001509e  movups  xmmword ptr [rdi+0A0h], xmm0
0x1800150a5  mov     [rdi+0B0h], rax
0x1800150ac  lea     rax, ??_7?$_Packaged_state@$$A6AXXZ@std@@6B@; const std::_Packaged_state<void (void)>::`vftable'
0x1800150b3  mov     [rdi], rax
0x1800150b6  lea     rax, [rdi+0D0h]
0x1800150bd  mov     [rdi+0B8h], sil
0x1800150c4  mov     [rdi+0BCh], esi
0x1800150ca  mov     [rdi+0C0h], si
0x1800150d1  mov     [rdi+0C2h], sil
0x1800150d8  mov     [rdi+0C8h], rsi
0x1800150df  mov     [rax+38h], rsi
0x1800150e3  mov     rsi, [rsp+28h+arg_8]
0x1800150e8  mov     [rax], rcx
0x1800150eb  movups  xmm0, xmmword ptr [rbx]
0x1800150ee  mov     rbx, [rsp+28h+arg_0]
0x1800150f3  movdqu  xmmword ptr [rax+8], xmm0
0x1800150f8  mov     [rax+38h], rax
0x1800150fc  mov     rax, rdi
0x1800150ff  add     rsp, 20h
0x180015103  pop     rdi
0x180015104  retn
```
