# ?__abi_Windows_UI_Xaml_IApplication____abi_add_Suspending@?QIApplication@Xaml@UI@Windows@@App@CHXSmartScreen@@UE$AAAJPE$AAVSuspendingEventHandler@234@PEAVEventRegistrationToken@Foundation@4@@Z

- ea: `0x140010c20`
- end: `0x140010ccd`
- name: `?__abi_Windows_UI_Xaml_IApplication____abi_add_Suspending@?QIApplication@Xaml@UI@Windows@@App@CHXSmartScreen@@UE$AAAJPE$AAVSuspendingEventHandler@234@PEAVEventRegistrationToken@Foundation@4@@Z`
- size: `173`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140010ce0`

## callees

- `0x140010c20`
- `0x140031960`
- `0x140035010`

## import_xrefs

- `wincorlib!?__abi_WinRTraiseObjectDisposedException@@YAXXZ` at `0x140010c4a`
- `wincorlib!?__abi_WinRTraiseObjectDisposedException@@YAXXZ` at `0x140010c4a`

## pseudocode

```c
__int64 __fastcall ___abi_Windows_UI_Xaml_IApplication____abi_add_Suspending__QIApplication_Xaml_UI_Windows__App_CHXSmartScreen__UE_AAAJPE_AAVSuspendingEventHandler_234_PEAVEventRegistrationToken_Foundation_4__Z(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  unsigned int v5; // edi
  __int64 v6; // rbx
  __int64 v8; // [rsp+28h] [rbp-30h] BYREF

  if ( *(_BYTE *)(a1 + 184) )
  {
    __abi_WinRTraiseObjectDisposedException();
    __debugbreak();
  }
  v8 = 0;
  v5 = (***(__int64 (__fastcall ****)(_QWORD, __int64 *, __int64 *))(a1 + 56))(
         *(_QWORD *)(a1 + 56),
         _uuidof__AUIApplication_Xaml_UI_Windows__,
         &v8);
  if ( !v5 )
  {
    v6 = v8;
    v5 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v8 + 104LL))(v8, a2, a3);
    if ( v6 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  }
  return v5;
}

```

## disassembly

```asm
0x140010c20  mov     [rsp+arg_18], rbx
0x140010c25  push    rbp
0x140010c26  push    rsi
0x140010c27  push    rdi
0x140010c28  sub     rsp, 40h
0x140010c2c  mov     rax, cs:__security_cookie
0x140010c33  xor     rax, rsp
0x140010c36  mov     [rsp+58h+var_28], rax
0x140010c3b  mov     rbp, r8
0x140010c3e  mov     rsi, rdx
0x140010c41  cmp     byte ptr [rcx+0B8h], 0
0x140010c48  jz      short loc_140010C51
0x140010c4a  call    cs:__imp_?__abi_WinRTraiseObjectDisposedException@@YAXXZ; __abi_WinRTraiseObjectDisposedException(void)
0x140010c50  int     3; Trap to Debugger
0x140010c51  mov     [rsp+58h+var_30], 0
0x140010c5a  mov     rcx, [rcx+38h]
0x140010c5e  mov     rax, [rcx]
0x140010c61  lea     r8, [rsp+58h+var_30]
0x140010c66  lea     rdx, __uuidof_?AUIApplication@Xaml@UI@Windows@@
0x140010c6d  mov     rax, [rax]
0x140010c70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010c75  mov     edi, eax
0x140010c77  test    eax, eax
0x140010c79  jnz     short loc_140010CB1
0x140010c7b  mov     rbx, [rsp+58h+var_30]
0x140010c80  mov     [rsp+58h+var_38], rbx
0x140010c85  mov     rax, [rbx]
0x140010c88  mov     r8, rbp
0x140010c8b  mov     rdx, rsi
0x140010c8e  mov     rcx, rbx
0x140010c91  mov     rax, [rax+68h]
0x140010c95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010c9a  mov     edi, eax
0x140010c9c  test    rbx, rbx
0x140010c9f  jz      short loc_140010CB1
0x140010ca1  mov     rax, [rbx]
0x140010ca4  mov     rcx, rbx
0x140010ca7  mov     rax, [rax+10h]
0x140010cab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010cb0  nop
0x140010cb1  mov     eax, edi
0x140010cb3  mov     rcx, [rsp+58h+var_28]
0x140010cb8  xor     rcx, rsp; StackCookie
0x140010cbb  call    __security_check_cookie
0x140010cc0  mov     rbx, [rsp+58h+arg_18]
0x140010cc5  add     rsp, 40h
0x140010cc9  pop     rdi
0x140010cca  pop     rsi
0x140010ccb  pop     rbp
0x140010ccc  retn
```
