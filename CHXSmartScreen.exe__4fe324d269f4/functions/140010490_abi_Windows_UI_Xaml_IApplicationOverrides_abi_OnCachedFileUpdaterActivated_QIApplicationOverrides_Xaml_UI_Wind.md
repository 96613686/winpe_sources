# ?__abi_Windows_UI_Xaml_IApplicationOverrides____abi_OnCachedFileUpdaterActivated@?QIApplicationOverrides@Xaml@UI@Windows@@App@CHXSmartScreen@@UE$AAAJPE$AAVCachedFileUpdaterActivatedEventArgs@Activation@ApplicationModel@4@@Z

- ea: `0x140010490`
- end: `0x14001053d`
- name: `?__abi_Windows_UI_Xaml_IApplicationOverrides____abi_OnCachedFileUpdaterActivated@?QIApplicationOverrides@Xaml@UI@Windows@@App@CHXSmartScreen@@UE$AAAJPE$AAVCachedFileUpdaterActivatedEventArgs@Activation@ApplicationModel@4@@Z`
- size: `173`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x140010550`

## callees

- `0x140010490`
- `0x140031960`
- `0x140035010`

## import_xrefs

- `wincorlib!?__abi_WinRTraiseObjectDisposedException@@YAXXZ` at `0x1400104ba`
- `wincorlib!?__abi_WinRTraiseObjectDisposedException@@YAXXZ` at `0x1400104ba`

## pseudocode

```c
__int64 __fastcall ___abi_Windows_UI_Xaml_IApplicationOverrides____abi_OnCachedFileUpdaterActivated__QIApplicationOverrides_Xaml_UI_Windows__App_CHXSmartScreen__UE_AAAJPE_AAVCachedFileUpdaterActivatedEventArgs_Activation_ApplicationModel_4__Z(
        __int64 a1,
        __int64 a2)
{
  unsigned int v3; // edi
  __int64 v4; // rbx
  __int64 v6; // [rsp+28h] [rbp-20h] BYREF

  if ( *(_BYTE *)(a1 + 184) )
  {
    __abi_WinRTraiseObjectDisposedException();
    __debugbreak();
  }
  v6 = 0;
  v3 = (***(__int64 (__fastcall ****)(_QWORD, char *, __int64 *))(a1 + 56))(
         *(_QWORD *)(a1 + 56),
         _uuidof__AUIApplicationOverrides_Xaml_UI_Windows__,
         &v6);
  if ( !v3 )
  {
    v4 = v6;
    v3 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v6 + 104LL))(v6, a2);
    if ( v4 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  }
  return v3;
}

```

## disassembly

```asm
0x140010490  mov     [rsp+arg_10], rbx
0x140010495  mov     [rsp+arg_18], rsi
0x14001049a  push    rdi
0x14001049b  sub     rsp, 40h
0x14001049f  mov     rax, cs:__security_cookie
0x1400104a6  xor     rax, rsp
0x1400104a9  mov     [rsp+48h+var_18], rax
0x1400104ae  mov     rsi, rdx
0x1400104b1  cmp     byte ptr [rcx+0B8h], 0
0x1400104b8  jz      short loc_1400104C1
0x1400104ba  call    cs:__imp_?__abi_WinRTraiseObjectDisposedException@@YAXXZ; __abi_WinRTraiseObjectDisposedException(void)
0x1400104c0  int     3; Trap to Debugger
0x1400104c1  mov     [rsp+48h+var_20], 0
0x1400104ca  mov     rcx, [rcx+38h]
0x1400104ce  mov     rax, [rcx]
0x1400104d1  lea     r8, [rsp+48h+var_20]
0x1400104d6  lea     rdx, __uuidof_?AUIApplicationOverrides@Xaml@UI@Windows@@
0x1400104dd  mov     rax, [rax]
0x1400104e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400104e5  mov     edi, eax
0x1400104e7  test    eax, eax
0x1400104e9  jnz     short loc_14001051E
0x1400104eb  mov     rbx, [rsp+48h+var_20]
0x1400104f0  mov     [rsp+48h+var_28], rbx
0x1400104f5  mov     rax, [rbx]
0x1400104f8  mov     rdx, rsi
0x1400104fb  mov     rcx, rbx
0x1400104fe  mov     rax, [rax+68h]
0x140010502  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010507  mov     edi, eax
0x140010509  test    rbx, rbx
0x14001050c  jz      short loc_14001051E
0x14001050e  mov     rax, [rbx]
0x140010511  mov     rcx, rbx
0x140010514  mov     rax, [rax+10h]
0x140010518  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001051d  nop
0x14001051e  mov     eax, edi
0x140010520  mov     rcx, [rsp+48h+var_18]
0x140010525  xor     rcx, rsp; StackCookie
0x140010528  call    __security_check_cookie
0x14001052d  mov     rbx, [rsp+48h+arg_10]
0x140010532  mov     rsi, [rsp+48h+arg_18]
0x140010537  add     rsp, 40h
0x14001053b  pop     rdi
0x14001053c  retn
```
