# ?__abi_Windows_UI_Xaml_Controls_IPage____abi_set_NavigationCacheMode@?QIPage@Controls@Xaml@UI@Windows@@MainPage@CHXSmartScreen@@UE$AAAJW4NavigationCacheMode@Navigation@345@@Z

- ea: `0x140010170`
- end: `0x14001021b`
- name: `?__abi_Windows_UI_Xaml_Controls_IPage____abi_set_NavigationCacheMode@?QIPage@Controls@Xaml@UI@Windows@@MainPage@CHXSmartScreen@@UE$AAAJW4NavigationCacheMode@Navigation@345@@Z`
- size: `171`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140021cf0`

## callees

- `0x140010170`
- `0x140031960`
- `0x140035010`

## import_xrefs

- `wincorlib!?__abi_WinRTraiseObjectDisposedException@@YAXXZ` at `0x140010199`
- `wincorlib!?__abi_WinRTraiseObjectDisposedException@@YAXXZ` at `0x140010199`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ___abi_Windows_UI_Xaml_Controls_IPage____abi_set_NavigationCacheMode__QIPage_Controls_Xaml_UI_Windows__MainPage_CHXSmartScreen__UE_AAAJW4NavigationCacheMode_Navigation_345__Z(
        __int64 a1,
        unsigned int a2)
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
    v3 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v6 + 64LL))(v6, a2);
    if ( v4 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  }
  return v3;
}

```

## disassembly

```asm
0x140010170  mov     [rsp+arg_10], rbx
0x140010175  mov     [rsp+arg_18], rsi
0x14001017a  push    rdi
0x14001017b  sub     rsp, 40h
0x14001017f  mov     rax, cs:__security_cookie
0x140010186  xor     rax, rsp
0x140010189  mov     [rsp+48h+var_18], rax
0x14001018e  mov     esi, edx
0x140010190  cmp     byte ptr [rcx+1A8h], 0
0x140010197  jz      short loc_1400101A0
0x140010199  call    cs:__imp_?__abi_WinRTraiseObjectDisposedException@@YAXXZ; __abi_WinRTraiseObjectDisposedException(void)
0x14001019f  int     3; Trap to Debugger
0x1400101a0  mov     [rsp+48h+var_20], 0
0x1400101a9  mov     rcx, [rcx+48h]
0x1400101ad  mov     rax, [rcx]
0x1400101b0  lea     r8, [rsp+48h+var_20]
0x1400101b5  lea     rdx, __uuidof_?AUIPage@Controls@Xaml@UI@Windows@@
0x1400101bc  mov     rax, [rax]
0x1400101bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400101c4  mov     edi, eax
0x1400101c6  test    eax, eax
0x1400101c8  jnz     short loc_1400101FC
0x1400101ca  mov     rbx, [rsp+48h+var_20]
0x1400101cf  mov     [rsp+48h+var_28], rbx
0x1400101d4  mov     rax, [rbx]
0x1400101d7  mov     edx, esi
0x1400101d9  mov     rcx, rbx
0x1400101dc  mov     rax, [rax+40h]
0x1400101e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400101e5  mov     edi, eax
0x1400101e7  test    rbx, rbx
0x1400101ea  jz      short loc_1400101FC
0x1400101ec  mov     rax, [rbx]
0x1400101ef  mov     rcx, rbx
0x1400101f2  mov     rax, [rax+10h]
0x1400101f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400101fb  nop
0x1400101fc  mov     eax, edi
0x1400101fe  mov     rcx, [rsp+48h+var_18]
0x140010203  xor     rcx, rsp; StackCookie
0x140010206  call    __security_check_cookie
0x14001020b  mov     rbx, [rsp+48h+arg_10]
0x140010210  mov     rsi, [rsp+48h+arg_18]
0x140010215  add     rsp, 40h
0x140010219  pop     rdi
0x14001021a  retn
```
