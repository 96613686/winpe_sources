# AccessibilityCplPage::Notify(ushort const *)

- ea: `0x18001c610`
- end: `0x18001c6c0`
- name: `?Notify@AccessibilityCplPage@@UEAAJPEBG@Z`
- size: `176`
- prototype: `__int64 __fastcall(AccessibilityCplPage *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, service_task`

## callees

- `0x18001c610`
- `0x18002c8cc`
- `0x18002e010`

## import_xrefs

- `SHLWAPI!__imp_StrCmpICW` at `0x18001c62a`
- `SHLWAPI!__imp_StrCmpICW` at `0x18001c62a`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18001c654`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18001c654`
- `PROPSYS!PSPropertyBag_ReadInt` at `0x18001c677`
- `PROPSYS!PSPropertyBag_ReadInt` at `0x18001c677`

## string_xrefs

- `0x18001c623`: `ControlPanelNavLinkClicked`
- `0x18001c668`: `ControlPanelNavLinkClicked`

## pseudocode

```c
__int64 __fastcall AccessibilityCplPage::Notify(AccessibilityCplPage *this, const unsigned __int16 *a2)
{
  IUnknown *v4; // rcx
  INT value; // [rsp+40h] [rbp+18h] BYREF
  void *ppvOut; // [rsp+48h] [rbp+20h] BYREF

  if ( StrCmpICW(a2, L"ControlPanelNavLinkClicked") )
  {
    CControlPanelPage::Notify(this, a2);
  }
  else
  {
    v4 = (IUnknown *)*((_QWORD *)this - 1);
    ppvOut = 0;
    if ( IUnknown_QueryService(
           v4,
           (const GUID *const)&SID_PerLayoutPropertyBag,
           &GUID_55272a00_42cb_11ce_8135_00aa004bb851,
           &ppvOut) >= 0 )
    {
      value = 0;
      if ( PSPropertyBag_ReadInt((IPropertyBag *)ppvOut, L"ControlPanelNavLinkClicked", &value) >= 0 )
        (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 4) + 24LL))(
          *((_QWORD *)this + 4),
          (unsigned int)value);
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18001c610  mov     [rsp+arg_0], rbx
0x18001c615  push    rdi
0x18001c616  sub     rsp, 20h
0x18001c61a  mov     rdi, rdx
0x18001c61d  mov     rbx, rcx
0x18001c620  mov     rcx, rdi; pszStr1
0x18001c623  lea     rdx, pszStr2; "ControlPanelNavLinkClicked"
0x18001c62a  call    cs:__imp_StrCmpICW
0x18001c630  test    eax, eax
0x18001c632  jnz     short loc_18001C6A8
0x18001c634  mov     rcx, [rbx-8]; punk
0x18001c638  lea     r9, [rsp+28h+ppvOut]; ppvOut
0x18001c63d  lea     r8, _GUID_55272a00_42cb_11ce_8135_00aa004bb851; riid
0x18001c644  mov     [rsp+28h+ppvOut], 0
0x18001c64d  lea     rdx, SID_PerLayoutPropertyBag; guidService
0x18001c654  call    cs:__imp_IUnknown_QueryService
0x18001c65a  test    eax, eax
0x18001c65c  js      short loc_18001C6B3
0x18001c65e  mov     rcx, [rsp+28h+ppvOut]; propBag
0x18001c663  lea     r8, [rsp+28h+value]; value
0x18001c668  lea     rdx, pszStr2; "ControlPanelNavLinkClicked"
0x18001c66f  mov     [rsp+28h+value], 0
0x18001c677  call    cs:__imp_PSPropertyBag_ReadInt
0x18001c67d  test    eax, eax
0x18001c67f  js      short loc_18001C695
0x18001c681  mov     rcx, [rbx+20h]
0x18001c685  mov     edx, [rsp+28h+value]
0x18001c689  mov     rax, [rcx]
0x18001c68c  mov     rax, [rax+18h]
0x18001c690  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c695  mov     rcx, [rsp+28h+ppvOut]
0x18001c69a  mov     rax, [rcx]
0x18001c69d  mov     rax, [rax+10h]
0x18001c6a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c6a6  jmp     short loc_18001C6B3
0x18001c6a8  mov     rdx, rdi; unsigned __int16 *
0x18001c6ab  mov     rcx, rbx; this
0x18001c6ae  call    ?Notify@CControlPanelPage@@UEAAJPEBG@Z; CControlPanelPage::Notify(ushort const *)
0x18001c6b3  mov     rbx, [rsp+28h+arg_0]
0x18001c6b8  xor     eax, eax
0x18001c6ba  add     rsp, 20h
0x18001c6be  pop     rdi
0x18001c6bf  retn
```
