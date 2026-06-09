# ?__abi_Windows_UI_Xaml_IApplication____abi_remove_Resuming@?QIApplication@Xaml@UI@Windows@@App@CHXSmartScreen@@UE$AAAJVEventRegistrationToken@Foundation@4@@Z

- ea: `0x140011030`
- end: `0x1400110e0`
- name: `?__abi_Windows_UI_Xaml_IApplication____abi_remove_Resuming@?QIApplication@Xaml@UI@Windows@@App@CHXSmartScreen@@UE$AAAJVEventRegistrationToken@Foundation@4@@Z`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400110f0`

## callees

- `0x140011030`
- `0x140031960`
- `0x140035010`

## import_xrefs

- `wincorlib!?__abi_WinRTraiseObjectDisposedException@@YAXXZ` at `0x14001105a`
- `wincorlib!?__abi_WinRTraiseObjectDisposedException@@YAXXZ` at `0x14001105a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ___abi_Windows_UI_Xaml_IApplication____abi_remove_Resuming__QIApplication_Xaml_UI_Windows__App_CHXSmartScreen__UE_AAAJVEventRegistrationToken_Foundation_4__Z(
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
    v3 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v6 + 128LL))(v6, a2);
    if ( v4 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  }
  return v3;
}

```

## disassembly

```asm
0x140011030  mov     [rsp+arg_10], rbx
0x140011035  mov     [rsp+arg_18], rsi
0x14001103a  push    rdi
0x14001103b  sub     rsp, 40h
0x14001103f  mov     rax, cs:__security_cookie
0x140011046  xor     rax, rsp
0x140011049  mov     [rsp+48h+var_18], rax
0x14001104e  mov     rdi, rdx
0x140011051  cmp     byte ptr [rcx+0B8h], 0
0x140011058  jz      short loc_140011061
0x14001105a  call    cs:__imp_?__abi_WinRTraiseObjectDisposedException@@YAXXZ; __abi_WinRTraiseObjectDisposedException(void)
0x140011060  int     3; Trap to Debugger
0x140011061  mov     [rsp+48h+var_20], 0
0x14001106a  mov     rcx, [rcx+38h]
0x14001106e  mov     rax, [rcx]
0x140011071  lea     r8, [rsp+48h+var_20]
0x140011076  lea     rdx, __uuidof_?AUIApplication@Xaml@UI@Windows@@
0x14001107d  mov     rax, [rax]
0x140011080  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011085  mov     esi, eax
0x140011087  test    eax, eax
0x140011089  jnz     short loc_1400110C1
0x14001108b  mov     rbx, [rsp+48h+var_20]
0x140011090  mov     [rsp+48h+var_28], rbx
0x140011095  mov     rax, [rbx]
0x140011098  mov     rdx, rdi
0x14001109b  mov     rcx, rbx
0x14001109e  mov     rax, [rax+80h]
0x1400110a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400110aa  mov     esi, eax
0x1400110ac  test    rbx, rbx
0x1400110af  jz      short loc_1400110C1
0x1400110b1  mov     rax, [rbx]
0x1400110b4  mov     rcx, rbx
0x1400110b7  mov     rax, [rax+10h]
0x1400110bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400110c0  nop
0x1400110c1  mov     eax, esi
0x1400110c3  mov     rcx, [rsp+48h+var_18]
0x1400110c8  xor     rcx, rsp; StackCookie
0x1400110cb  call    __security_check_cookie
0x1400110d0  mov     rbx, [rsp+48h+arg_10]
0x1400110d5  mov     rsi, [rsp+48h+arg_18]
0x1400110da  add     rsp, 40h
0x1400110de  pop     rdi
0x1400110df  retn
```
