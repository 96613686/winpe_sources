# ?__abi_Windows_UI_Xaml_IApplication____abi_remove_UnhandledException@?QIApplication@Xaml@UI@Windows@@App@CHXSmartScreen@@UE$AAAJVEventRegistrationToken@Foundation@4@@Z

- ea: `0x1400111d0`
- end: `0x14001127d`
- name: `?__abi_Windows_UI_Xaml_IApplication____abi_remove_UnhandledException@?QIApplication@Xaml@UI@Windows@@App@CHXSmartScreen@@UE$AAAJVEventRegistrationToken@Foundation@4@@Z`
- size: `173`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140011290`

## callees

- `0x1400111d0`
- `0x140031960`
- `0x140035010`

## import_xrefs

- `wincorlib!?__abi_WinRTraiseObjectDisposedException@@YAXXZ` at `0x1400111fa`
- `wincorlib!?__abi_WinRTraiseObjectDisposedException@@YAXXZ` at `0x1400111fa`

## pseudocode

```c
__int64 __fastcall ___abi_Windows_UI_Xaml_IApplication____abi_remove_UnhandledException__QIApplication_Xaml_UI_Windows__App_CHXSmartScreen__UE_AAAJVEventRegistrationToken_Foundation_4__Z(
        __int64 a1,
        __int64 a2)
{
  unsigned int v3; // esi
  __int64 v4; // rbx
  __int64 v6; // [rsp+28h] [rbp-20h] BYREF

  if ( *(_BYTE *)(a1 + 184) )
  {
    __abi_WinRTraiseObjectDisposedException();
    __debugbreak();
  }
  v6 = 0;
  v3 = (***(__int64 (__fastcall ****)(_QWORD, __int64 *, __int64 *))(a1 + 56))(
         *(_QWORD *)(a1 + 56),
         _uuidof__AUIApplication_Xaml_UI_Windows__,
         &v6);
  if ( !v3 )
  {
    v4 = v6;
    v3 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v6 + 96LL))(v6, a2);
    if ( v4 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  }
  return v3;
}

```

## disassembly

```asm
0x1400111d0  mov     [rsp+arg_10], rbx
0x1400111d5  mov     [rsp+arg_18], rsi
0x1400111da  push    rdi
0x1400111db  sub     rsp, 40h
0x1400111df  mov     rax, cs:__security_cookie
0x1400111e6  xor     rax, rsp
0x1400111e9  mov     [rsp+48h+var_18], rax
0x1400111ee  mov     rdi, rdx
0x1400111f1  cmp     byte ptr [rcx+0B8h], 0
0x1400111f8  jz      short loc_140011201
0x1400111fa  call    cs:__imp_?__abi_WinRTraiseObjectDisposedException@@YAXXZ; __abi_WinRTraiseObjectDisposedException(void)
0x140011200  int     3; Trap to Debugger
0x140011201  mov     [rsp+48h+var_20], 0
0x14001120a  mov     rcx, [rcx+38h]
0x14001120e  mov     rax, [rcx]
0x140011211  lea     r8, [rsp+48h+var_20]
0x140011216  lea     rdx, __uuidof_?AUIApplication@Xaml@UI@Windows@@
0x14001121d  mov     rax, [rax]
0x140011220  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011225  mov     esi, eax
0x140011227  test    eax, eax
0x140011229  jnz     short loc_14001125E
0x14001122b  mov     rbx, [rsp+48h+var_20]
0x140011230  mov     [rsp+48h+var_28], rbx
0x140011235  mov     rax, [rbx]
0x140011238  mov     rdx, rdi
0x14001123b  mov     rcx, rbx
0x14001123e  mov     rax, [rax+60h]
0x140011242  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011247  mov     esi, eax
0x140011249  test    rbx, rbx
0x14001124c  jz      short loc_14001125E
0x14001124e  mov     rax, [rbx]
0x140011251  mov     rcx, rbx
0x140011254  mov     rax, [rax+10h]
0x140011258  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001125d  nop
0x14001125e  mov     eax, esi
0x140011260  mov     rcx, [rsp+48h+var_18]
0x140011265  xor     rcx, rsp; StackCookie
0x140011268  call    __security_check_cookie
0x14001126d  mov     rbx, [rsp+48h+arg_10]
0x140011272  mov     rsi, [rsp+48h+arg_18]
0x140011277  add     rsp, 40h
0x14001127b  pop     rdi
0x14001127c  retn
```
