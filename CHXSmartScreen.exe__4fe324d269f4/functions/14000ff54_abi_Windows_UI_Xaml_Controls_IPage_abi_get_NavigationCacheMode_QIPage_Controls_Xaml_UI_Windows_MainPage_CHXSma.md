# ?__abi_Windows_UI_Xaml_Controls_IPage____abi_get_NavigationCacheMode@?QIPage@Controls@Xaml@UI@Windows@@MainPage@CHXSmartScreen@@UE$AAAJPEAW4NavigationCacheMode@Navigation@345@@Z

- ea: `0x14000ff54`
- end: `0x140010001`
- name: `?__abi_Windows_UI_Xaml_Controls_IPage____abi_get_NavigationCacheMode@?QIPage@Controls@Xaml@UI@Windows@@MainPage@CHXSmartScreen@@UE$AAAJPEAW4NavigationCacheMode@Navigation@345@@Z`
- size: `173`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140021cc0`

## callees

- `0x14000ff54`
- `0x140031960`
- `0x140035010`

## import_xrefs

- `wincorlib!?__abi_WinRTraiseObjectDisposedException@@YAXXZ` at `0x14000ff7e`
- `wincorlib!?__abi_WinRTraiseObjectDisposedException@@YAXXZ` at `0x14000ff7e`

## pseudocode

```c
__int64 __fastcall ___abi_Windows_UI_Xaml_Controls_IPage____abi_get_NavigationCacheMode__QIPage_Controls_Xaml_UI_Windows__MainPage_CHXSmartScreen__UE_AAAJPEAW4NavigationCacheMode_Navigation_345__Z(
        __int64 a1,
        __int64 a2)
{
  unsigned int v3; // edi
  __int64 v4; // rbx
  __int64 v6; // [rsp+28h] [rbp-20h] BYREF

  if ( *(_BYTE *)(a1 + 424) )
  {
    __abi_WinRTraiseObjectDisposedException();
    __debugbreak();
  }
  v6 = 0;
  v3 = (***(__int64 (__fastcall ****)(_QWORD, __int64 *, __int64 *))(a1 + 72))(
         *(_QWORD *)(a1 + 72),
         _uuidof__AUIPage_Controls_Xaml_UI_Windows__,
         &v6);
  if ( !v3 )
  {
    v4 = v6;
    v3 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v6 + 56LL))(v6, a2);
    if ( v4 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  }
  return v3;
}

```

## disassembly

```asm
0x14000ff54  mov     [rsp+arg_10], rbx
0x14000ff59  mov     [rsp+arg_18], rsi
0x14000ff5e  push    rdi
0x14000ff5f  sub     rsp, 40h
0x14000ff63  mov     rax, cs:__security_cookie
0x14000ff6a  xor     rax, rsp
0x14000ff6d  mov     [rsp+48h+var_18], rax
0x14000ff72  mov     rsi, rdx
0x14000ff75  cmp     byte ptr [rcx+1A8h], 0
0x14000ff7c  jz      short loc_14000FF85
0x14000ff7e  call    cs:__imp_?__abi_WinRTraiseObjectDisposedException@@YAXXZ; __abi_WinRTraiseObjectDisposedException(void)
0x14000ff84  int     3; Trap to Debugger
0x14000ff85  mov     [rsp+48h+var_20], 0
0x14000ff8e  mov     rcx, [rcx+48h]
0x14000ff92  mov     rax, [rcx]
0x14000ff95  lea     r8, [rsp+48h+var_20]
0x14000ff9a  lea     rdx, __uuidof_?AUIPage@Controls@Xaml@UI@Windows@@
0x14000ffa1  mov     rax, [rax]
0x14000ffa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ffa9  mov     edi, eax
0x14000ffab  test    eax, eax
0x14000ffad  jnz     short loc_14000FFE2
0x14000ffaf  mov     rbx, [rsp+48h+var_20]
0x14000ffb4  mov     [rsp+48h+var_28], rbx
0x14000ffb9  mov     rax, [rbx]
0x14000ffbc  mov     rdx, rsi
0x14000ffbf  mov     rcx, rbx
0x14000ffc2  mov     rax, [rax+38h]
0x14000ffc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ffcb  mov     edi, eax
0x14000ffcd  test    rbx, rbx
0x14000ffd0  jz      short loc_14000FFE2
0x14000ffd2  mov     rax, [rbx]
0x14000ffd5  mov     rcx, rbx
0x14000ffd8  mov     rax, [rax+10h]
0x14000ffdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ffe1  nop
0x14000ffe2  mov     eax, edi
0x14000ffe4  mov     rcx, [rsp+48h+var_18]
0x14000ffe9  xor     rcx, rsp; StackCookie
0x14000ffec  call    __security_check_cookie
0x14000fff1  mov     rbx, [rsp+48h+arg_10]
0x14000fff6  mov     rsi, [rsp+48h+arg_18]
0x14000fffb  add     rsp, 40h
0x14000ffff  pop     rdi
0x140010000  retn
```
