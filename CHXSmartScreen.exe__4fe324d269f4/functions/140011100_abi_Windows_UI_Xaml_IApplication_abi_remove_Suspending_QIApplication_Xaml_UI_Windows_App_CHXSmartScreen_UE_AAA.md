# ?__abi_Windows_UI_Xaml_IApplication____abi_remove_Suspending@?QIApplication@Xaml@UI@Windows@@App@CHXSmartScreen@@UE$AAAJVEventRegistrationToken@Foundation@4@@Z

- ea: `0x140011100`
- end: `0x1400111ad`
- name: `?__abi_Windows_UI_Xaml_IApplication____abi_remove_Suspending@?QIApplication@Xaml@UI@Windows@@App@CHXSmartScreen@@UE$AAAJVEventRegistrationToken@Foundation@4@@Z`
- size: `173`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400111c0`

## callees

- `0x140011100`
- `0x140031960`
- `0x140035010`

## import_xrefs

- `wincorlib!?__abi_WinRTraiseObjectDisposedException@@YAXXZ` at `0x14001112a`
- `wincorlib!?__abi_WinRTraiseObjectDisposedException@@YAXXZ` at `0x14001112a`

## pseudocode

```c
__int64 __fastcall ___abi_Windows_UI_Xaml_IApplication____abi_remove_Suspending__QIApplication_Xaml_UI_Windows__App_CHXSmartScreen__UE_AAAJVEventRegistrationToken_Foundation_4__Z(
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
    v3 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v6 + 112LL))(v6, a2);
    if ( v4 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  }
  return v3;
}

```

## disassembly

```asm
0x140011100  mov     [rsp+arg_10], rbx
0x140011105  mov     [rsp+arg_18], rsi
0x14001110a  push    rdi
0x14001110b  sub     rsp, 40h
0x14001110f  mov     rax, cs:__security_cookie
0x140011116  xor     rax, rsp
0x140011119  mov     [rsp+48h+var_18], rax
0x14001111e  mov     rdi, rdx
0x140011121  cmp     byte ptr [rcx+0B8h], 0
0x140011128  jz      short loc_140011131
0x14001112a  call    cs:__imp_?__abi_WinRTraiseObjectDisposedException@@YAXXZ; __abi_WinRTraiseObjectDisposedException(void)
0x140011130  int     3; Trap to Debugger
0x140011131  mov     [rsp+48h+var_20], 0
0x14001113a  mov     rcx, [rcx+38h]
0x14001113e  mov     rax, [rcx]
0x140011141  lea     r8, [rsp+48h+var_20]
0x140011146  lea     rdx, __uuidof_?AUIApplication@Xaml@UI@Windows@@
0x14001114d  mov     rax, [rax]
0x140011150  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011155  mov     esi, eax
0x140011157  test    eax, eax
0x140011159  jnz     short loc_14001118E
0x14001115b  mov     rbx, [rsp+48h+var_20]
0x140011160  mov     [rsp+48h+var_28], rbx
0x140011165  mov     rax, [rbx]
0x140011168  mov     rdx, rdi
0x14001116b  mov     rcx, rbx
0x14001116e  mov     rax, [rax+70h]
0x140011172  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011177  mov     esi, eax
0x140011179  test    rbx, rbx
0x14001117c  jz      short loc_14001118E
0x14001117e  mov     rax, [rbx]
0x140011181  mov     rcx, rbx
0x140011184  mov     rax, [rax+10h]
0x140011188  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001118d  nop
0x14001118e  mov     eax, esi
0x140011190  mov     rcx, [rsp+48h+var_18]
0x140011195  xor     rcx, rsp; StackCookie
0x140011198  call    __security_check_cookie
0x14001119d  mov     rbx, [rsp+48h+arg_10]
0x1400111a2  mov     rsi, [rsp+48h+arg_18]
0x1400111a7  add     rsp, 40h
0x1400111ab  pop     rdi
0x1400111ac  retn
```
