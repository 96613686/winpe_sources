# ?__abi_Windows_UI_Xaml_IApplication____abi_add_UnhandledException@?QIApplication@Xaml@UI@Windows@@App@CHXSmartScreen@@UE$AAAJPE$AAVUnhandledExceptionEventHandler@234@PEAVEventRegistrationToken@Foundation@4@@Z

- ea: `0x140010cf0`
- end: `0x140010d9d`
- name: `?__abi_Windows_UI_Xaml_IApplication____abi_add_UnhandledException@?QIApplication@Xaml@UI@Windows@@App@CHXSmartScreen@@UE$AAAJPE$AAVUnhandledExceptionEventHandler@234@PEAVEventRegistrationToken@Foundation@4@@Z`
- size: `173`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140010db0`

## callees

- `0x140010cf0`
- `0x140031960`
- `0x140035010`

## import_xrefs

- `wincorlib!?__abi_WinRTraiseObjectDisposedException@@YAXXZ` at `0x140010d1a`
- `wincorlib!?__abi_WinRTraiseObjectDisposedException@@YAXXZ` at `0x140010d1a`

## pseudocode

```c
__int64 __fastcall ___abi_Windows_UI_Xaml_IApplication____abi_add_UnhandledException__QIApplication_Xaml_UI_Windows__App_CHXSmartScreen__UE_AAAJPE_AAVUnhandledExceptionEventHandler_234_PEAVEventRegistrationToken_Foundation_4__Z(
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
    v5 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v8 + 88LL))(v8, a2, a3);
    if ( v6 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  }
  return v5;
}

```

## disassembly

```asm
0x140010cf0  mov     [rsp+arg_18], rbx
0x140010cf5  push    rbp
0x140010cf6  push    rsi
0x140010cf7  push    rdi
0x140010cf8  sub     rsp, 40h
0x140010cfc  mov     rax, cs:__security_cookie
0x140010d03  xor     rax, rsp
0x140010d06  mov     [rsp+58h+var_28], rax
0x140010d0b  mov     rbp, r8
0x140010d0e  mov     rsi, rdx
0x140010d11  cmp     byte ptr [rcx+0B8h], 0
0x140010d18  jz      short loc_140010D21
0x140010d1a  call    cs:__imp_?__abi_WinRTraiseObjectDisposedException@@YAXXZ; __abi_WinRTraiseObjectDisposedException(void)
0x140010d20  int     3; Trap to Debugger
0x140010d21  mov     [rsp+58h+var_30], 0
0x140010d2a  mov     rcx, [rcx+38h]
0x140010d2e  mov     rax, [rcx]
0x140010d31  lea     r8, [rsp+58h+var_30]
0x140010d36  lea     rdx, __uuidof_?AUIApplication@Xaml@UI@Windows@@
0x140010d3d  mov     rax, [rax]
0x140010d40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010d45  mov     edi, eax
0x140010d47  test    eax, eax
0x140010d49  jnz     short loc_140010D81
0x140010d4b  mov     rbx, [rsp+58h+var_30]
0x140010d50  mov     [rsp+58h+var_38], rbx
0x140010d55  mov     rax, [rbx]
0x140010d58  mov     r8, rbp
0x140010d5b  mov     rdx, rsi
0x140010d5e  mov     rcx, rbx
0x140010d61  mov     rax, [rax+58h]
0x140010d65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010d6a  mov     edi, eax
0x140010d6c  test    rbx, rbx
0x140010d6f  jz      short loc_140010D81
0x140010d71  mov     rax, [rbx]
0x140010d74  mov     rcx, rbx
0x140010d77  mov     rax, [rax+10h]
0x140010d7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010d80  nop
0x140010d81  mov     eax, edi
0x140010d83  mov     rcx, [rsp+58h+var_28]
0x140010d88  xor     rcx, rsp; StackCookie
0x140010d8b  call    __security_check_cookie
0x140010d90  mov     rbx, [rsp+58h+arg_18]
0x140010d95  add     rsp, 40h
0x140010d99  pop     rdi
0x140010d9a  pop     rsi
0x140010d9b  pop     rbp
0x140010d9c  retn
```
