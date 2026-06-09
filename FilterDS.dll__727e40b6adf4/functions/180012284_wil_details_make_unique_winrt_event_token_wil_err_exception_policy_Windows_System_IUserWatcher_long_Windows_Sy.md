# wil::details::make_unique_winrt_event_token<wil::err_exception_policy,Windows::System::IUserWatcher,long (Windows::System::IUserWatcher::*)(Windows::Foundation::ITypedEventHandler<Windows::System::UserWatcher *,Windows::System::UserChangedEventArgs *> *,EventRegistrationToken *),long (Windows::System::IUserWatcher::*)(EventRegistrationToken),Windows::Foundation::ITypedEventHandler<Windows::System::UserWatcher *,Windows::System::UserChangedEventArgs *> *>(Windows::System::IUserWatcher *,long (Windows::System::IUserWatcher::*)(Windows::Foundation::ITypedEventHandler<Windows::System::UserWatcher *,Windows::System::UserChangedEventArgs *> *,EventRegistrationToken *),long (Windows::System::IUserWatcher::*)(EventRegistrationToken),Windows::Foundation::ITypedEventHandler<Windows::System::UserWatcher *,Windows::System::UserChangedEventArgs *> *)

- ea: `0x180012284`
- end: `0x1800123a8`
- name: `??$make_unique_winrt_event_token@Uerr_exception_policy@wil@@UIUserWatcher@System@Windows@@P8345@EAAJPEAU?$ITypedEventHandler@PEAVUserWatcher@System@Windows@@PEAVUserChangedEventArgs@23@@Foundation@5@PEAUEventRegistrationToken@@@ZP8345@EAAJU8@@ZPEAU675@@details@wil@@YA?AV?$unique_winrt_event_token@UIUserWatcher@System@Windows@@@1@PEAUIUserWatcher@System@Windows@@P8345@EAAJPEAU?$ITypedEventHandler@PEAVUserWatcher@System@Windows@@PEAVUserChangedEventArgs@23@@Foundation@5@PEAUEventRegistrationToken@@@ZP8345@EAAJU8@@Z1@Z`
- size: `292`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64 (__fastcall *)(_QWORD, __int64, _QWORD *), __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180014c20`

## callees

- `0x18000c6bc`
- `0x18000cd18`
- `0x180012284`
- `0x180024010`

## string_xrefs

- `0x180012396`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x180012381`: `onecore\internal\sdk\inc\wil\opensource\wil\com.h`

## pseudocode

```c
_QWORD *__fastcall wil::details::make_unique_winrt_event_token<wil::err_exception_policy,Windows::System::IUserWatcher,long (Windows::System::IUserWatcher::*)(Windows::Foundation::ITypedEventHandler<Windows::System::UserWatcher *,Windows::System::UserChangedEventArgs *> *,EventRegistrationToken *),long (Windows::System::IUserWatcher::*)(EventRegistrationToken),Windows::Foundation::ITypedEventHandler<Windows::System::UserWatcher *,Windows::System::UserChangedEventArgs *> *>(
        _QWORD *a1,
        __int64 (__fastcall ***a2)(_QWORD, GUID *, __int64 *),
        __int64 (__fastcall *a3)(_QWORD, __int64, _QWORD *),
        __int64 a4,
        __int64 a5)
{
  int v8; // eax
  __int64 (__fastcall **v9)(_QWORD, GUID *, __int64 *); // rax
  int v10; // edi
  __int64 v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rdx
  int v15; // [rsp+20h] [rbp-28h]
  __int64 v16; // [rsp+28h] [rbp-20h] BYREF
  _QWORD v17[3]; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+20h]
  __int64 v19; // [rsp+80h] [rbp+38h] BYREF

  v17[0] = 0;
  v8 = a3(a2, a5, v17);
  if ( v8 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1CBE,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)v8,
      v15);
  *a1 = v17[0];
  a1[1] = 0;
  a1[2] = a4;
  v19 = 0;
  v9 = *a2;
  v16 = 0;
  v10 = (*v9)(a2, &GUID_00000038_0000_0000_c000_000000000046, &v16);
  if ( v10 >= 0 )
    v10 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v16 + 24LL))(v16, &v19);
  if ( v16 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  if ( v10 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x7A0,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\com.h",
      (const char *)(unsigned int)v10,
      v15);
  v11 = v19;
  v12 = 0;
  v19 = 0;
  v13 = a1[1];
  a1[1] = v11;
  if ( v13 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    v12 = v19;
  }
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  return a1;
}

```

## disassembly

```asm
0x180012284  push    rbp
0x180012286  push    rbx
0x180012287  push    rsi
0x180012288  push    rdi
0x180012289  mov     rbp, rsp
0x18001228c  sub     rsp, 48h
0x180012290  mov     rsi, r9
0x180012293  mov     rax, r8
0x180012296  mov     rdi, rdx
0x180012299  mov     rbx, rcx
0x18001229c  mov     [rbp+var_18], 0
0x1800122a4  lea     r8, [rbp+var_18]
0x1800122a8  mov     rdx, [rbp+arg_20]
0x1800122ac  mov     rcx, rdi
0x1800122af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800122b4  mov     rcx, [rbp+20h]; this
0x1800122b8  test    eax, eax
0x1800122ba  js      loc_180012393
0x1800122c0  mov     rax, [rbp+var_18]
0x1800122c4  mov     [rbx], rax
0x1800122c7  mov     qword ptr [rbx+8], 0
0x1800122cf  mov     [rbx+10h], rsi
0x1800122d3  mov     [rbp+arg_10], 0
0x1800122db  mov     rax, [rdi]
0x1800122de  mov     [rbp+var_20], 0
0x1800122e6  lea     r8, [rbp+var_20]
0x1800122ea  lea     rdx, _GUID_00000038_0000_0000_c000_000000000046
0x1800122f1  mov     rcx, rdi
0x1800122f4  mov     rax, [rax]
0x1800122f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800122fc  mov     edi, eax
0x1800122fe  test    eax, eax
0x180012300  js      short loc_180012318
0x180012302  mov     rcx, [rbp+var_20]
0x180012306  mov     rax, [rcx]
0x180012309  lea     rdx, [rbp+arg_10]
0x18001230d  mov     rax, [rax+18h]
0x180012311  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012316  mov     edi, eax
0x180012318  mov     rcx, [rbp+var_20]
0x18001231c  test    rcx, rcx
0x18001231f  jz      short loc_18001232E
0x180012321  mov     rax, [rcx]
0x180012324  mov     rax, [rax+10h]
0x180012328  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001232d  nop
0x18001232e  mov     rcx, [rbp+20h]; this
0x180012332  test    edi, edi
0x180012334  js      short loc_18001237E
0x180012336  mov     rax, [rbp+arg_10]
0x18001233a  xor     ecx, ecx
0x18001233c  mov     [rbp+arg_10], rcx
0x180012340  mov     rdx, [rbx+8]
0x180012344  mov     [rbx+8], rax
0x180012348  test    rdx, rdx
0x18001234b  jz      short loc_180012360
0x18001234d  mov     rax, [rdx]
0x180012350  mov     rcx, rdx
0x180012353  mov     rax, [rax+10h]
0x180012357  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001235c  mov     rcx, [rbp+arg_10]
0x180012360  test    rcx, rcx
0x180012363  jz      short loc_180012372
0x180012365  mov     rax, [rcx]
0x180012368  mov     rax, [rax+10h]
0x18001236c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012371  nop
0x180012372  mov     rax, rbx
0x180012375  add     rsp, 48h
0x180012379  pop     rdi
0x18001237a  pop     rsi
0x18001237b  pop     rbx
0x18001237c  pop     rbp
0x18001237d  retn
0x18001237e  mov     r9d, edi; char *
0x180012381  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180012388  mov     edx, 7A0h; void *
0x18001238d  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180012393  mov     r9d, eax; char *
0x180012396  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001239d  mov     edx, 1CBEh; void *
0x1800123a2  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
