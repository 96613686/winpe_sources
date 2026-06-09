# ?__abi_Windows_UI_Xaml_IApplication____abi_add_Resuming@?QIApplication@Xaml@UI@Windows@@App@CHXSmartScreen@@UE$AAAJPE$AAV?$EventHandler@PE$AAVObject@Platform@@@Foundation@4@PEAVEventRegistrationToken@84@@Z

- ea: `0x140010b50`
- end: `0x140010bfd`
- name: `?__abi_Windows_UI_Xaml_IApplication____abi_add_Resuming@?QIApplication@Xaml@UI@Windows@@App@CHXSmartScreen@@UE$AAAJPE$AAV?$EventHandler@PE$AAVObject@Platform@@@Foundation@4@PEAVEventRegistrationToken@84@@Z`
- size: `173`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140010c10`

## callees

- `0x140010b50`
- `0x140031960`
- `0x140035010`

## import_xrefs

- `wincorlib!?__abi_WinRTraiseObjectDisposedException@@YAXXZ` at `0x140010b7a`
- `wincorlib!?__abi_WinRTraiseObjectDisposedException@@YAXXZ` at `0x140010b7a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ___abi_Windows_UI_Xaml_IApplication____abi_add_Resuming__QIApplication_Xaml_UI_Windows__App_CHXSmartScreen__UE_AAAJPE_AAV__EventHandler_PE_AAVObject_Platform___Foundation_4_PEAVEventRegistrationToken_84__Z(
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
    v5 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v8 + 120LL))(v8, a2, a3);
    if ( v6 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  }
  return v5;
}

```

## disassembly

```asm
0x140010b50  mov     [rsp+arg_18], rbx
0x140010b55  push    rbp
0x140010b56  push    rsi
0x140010b57  push    rdi
0x140010b58  sub     rsp, 40h
0x140010b5c  mov     rax, cs:__security_cookie
0x140010b63  xor     rax, rsp
0x140010b66  mov     [rsp+58h+var_28], rax
0x140010b6b  mov     rbp, r8
0x140010b6e  mov     rsi, rdx
0x140010b71  cmp     byte ptr [rcx+0B8h], 0
0x140010b78  jz      short loc_140010B81
0x140010b7a  call    cs:__imp_?__abi_WinRTraiseObjectDisposedException@@YAXXZ; __abi_WinRTraiseObjectDisposedException(void)
0x140010b80  int     3; Trap to Debugger
0x140010b81  mov     [rsp+58h+var_30], 0
0x140010b8a  mov     rcx, [rcx+38h]
0x140010b8e  mov     rax, [rcx]
0x140010b91  lea     r8, [rsp+58h+var_30]
0x140010b96  lea     rdx, __uuidof_?AUIApplication@Xaml@UI@Windows@@
0x140010b9d  mov     rax, [rax]
0x140010ba0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010ba5  mov     edi, eax
0x140010ba7  test    eax, eax
0x140010ba9  jnz     short loc_140010BE1
0x140010bab  mov     rbx, [rsp+58h+var_30]
0x140010bb0  mov     [rsp+58h+var_38], rbx
0x140010bb5  mov     rax, [rbx]
0x140010bb8  mov     r8, rbp
0x140010bbb  mov     rdx, rsi
0x140010bbe  mov     rcx, rbx
0x140010bc1  mov     rax, [rax+78h]
0x140010bc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010bca  mov     edi, eax
0x140010bcc  test    rbx, rbx
0x140010bcf  jz      short loc_140010BE1
0x140010bd1  mov     rax, [rbx]
0x140010bd4  mov     rcx, rbx
0x140010bd7  mov     rax, [rax+10h]
0x140010bdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010be0  nop
0x140010be1  mov     eax, edi
0x140010be3  mov     rcx, [rsp+58h+var_28]
0x140010be8  xor     rcx, rsp; StackCookie
0x140010beb  call    __security_check_cookie
0x140010bf0  mov     rbx, [rsp+58h+arg_18]
0x140010bf5  add     rsp, 40h
0x140010bf9  pop     rdi
0x140010bfa  pop     rsi
0x140010bfb  pop     rbp
0x140010bfc  retn
```
