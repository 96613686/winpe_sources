# ?__abi_Windows_UI_Xaml_IApplicationOverrides____abi_OnWindowCreated@?QIApplicationOverrides@Xaml@UI@Windows@@App@CHXSmartScreen@@UE$AAAJPE$AAVWindowCreatedEventArgs@234@@Z

- ea: `0x1400109c0`
- end: `0x140010a6d`
- name: `?__abi_Windows_UI_Xaml_IApplicationOverrides____abi_OnWindowCreated@?QIApplicationOverrides@Xaml@UI@Windows@@App@CHXSmartScreen@@UE$AAAJPE$AAVWindowCreatedEventArgs@234@@Z`
- size: `173`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140010a80`

## callees

- `0x1400109c0`
- `0x140031960`
- `0x140035010`

## import_xrefs

- `wincorlib!?__abi_WinRTraiseObjectDisposedException@@YAXXZ` at `0x1400109ea`
- `wincorlib!?__abi_WinRTraiseObjectDisposedException@@YAXXZ` at `0x1400109ea`

## pseudocode

```c
__int64 __fastcall ___abi_Windows_UI_Xaml_IApplicationOverrides____abi_OnWindowCreated__QIApplicationOverrides_Xaml_UI_Windows__App_CHXSmartScreen__UE_AAAJPE_AAVWindowCreatedEventArgs_234__Z(
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
    v3 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v6 + 112LL))(v6, a2);
    if ( v4 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  }
  return v3;
}

```

## disassembly

```asm
0x1400109c0  mov     [rsp+arg_10], rbx
0x1400109c5  mov     [rsp+arg_18], rsi
0x1400109ca  push    rdi
0x1400109cb  sub     rsp, 40h
0x1400109cf  mov     rax, cs:__security_cookie
0x1400109d6  xor     rax, rsp
0x1400109d9  mov     [rsp+48h+var_18], rax
0x1400109de  mov     rsi, rdx
0x1400109e1  cmp     byte ptr [rcx+0B8h], 0
0x1400109e8  jz      short loc_1400109F1
0x1400109ea  call    cs:__imp_?__abi_WinRTraiseObjectDisposedException@@YAXXZ; __abi_WinRTraiseObjectDisposedException(void)
0x1400109f0  int     3; Trap to Debugger
0x1400109f1  mov     [rsp+48h+var_20], 0
0x1400109fa  mov     rcx, [rcx+38h]
0x1400109fe  mov     rax, [rcx]
0x140010a01  lea     r8, [rsp+48h+var_20]
0x140010a06  lea     rdx, __uuidof_?AUIApplicationOverrides@Xaml@UI@Windows@@
0x140010a0d  mov     rax, [rax]
0x140010a10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010a15  mov     edi, eax
0x140010a17  test    eax, eax
0x140010a19  jnz     short loc_140010A4E
0x140010a1b  mov     rbx, [rsp+48h+var_20]
0x140010a20  mov     [rsp+48h+var_28], rbx
0x140010a25  mov     rax, [rbx]
0x140010a28  mov     rdx, rsi
0x140010a2b  mov     rcx, rbx
0x140010a2e  mov     rax, [rax+70h]
0x140010a32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010a37  mov     edi, eax
0x140010a39  test    rbx, rbx
0x140010a3c  jz      short loc_140010A4E
0x140010a3e  mov     rax, [rbx]
0x140010a41  mov     rcx, rbx
0x140010a44  mov     rax, [rax+10h]
0x140010a48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010a4d  nop
0x140010a4e  mov     eax, edi
0x140010a50  mov     rcx, [rsp+48h+var_18]
0x140010a55  xor     rcx, rsp; StackCookie
0x140010a58  call    __security_check_cookie
0x140010a5d  mov     rbx, [rsp+48h+arg_10]
0x140010a62  mov     rsi, [rsp+48h+arg_18]
0x140010a67  add     rsp, 40h
0x140010a6b  pop     rdi
0x140010a6c  retn
```
