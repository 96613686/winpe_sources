# ?__abi_Windows_UI_Xaml_IApplicationOverrides____abi_OnFileOpenPickerActivated@?QIApplicationOverrides@Xaml@UI@Windows@@App@CHXSmartScreen@@UE$AAAJPE$AAVFileOpenPickerActivatedEventArgs@Activation@ApplicationModel@4@@Z

- ea: `0x140010630`
- end: `0x1400106dd`
- name: `?__abi_Windows_UI_Xaml_IApplicationOverrides____abi_OnFileOpenPickerActivated@?QIApplicationOverrides@Xaml@UI@Windows@@App@CHXSmartScreen@@UE$AAAJPE$AAVFileOpenPickerActivatedEventArgs@Activation@ApplicationModel@4@@Z`
- size: `173`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400106f0`

## callees

- `0x140010630`
- `0x140031960`
- `0x140035010`

## import_xrefs

- `wincorlib!?__abi_WinRTraiseObjectDisposedException@@YAXXZ` at `0x14001065a`
- `wincorlib!?__abi_WinRTraiseObjectDisposedException@@YAXXZ` at `0x14001065a`

## pseudocode

```c
__int64 __fastcall ___abi_Windows_UI_Xaml_IApplicationOverrides____abi_OnFileOpenPickerActivated__QIApplicationOverrides_Xaml_UI_Windows__App_CHXSmartScreen__UE_AAAJPE_AAVFileOpenPickerActivatedEventArgs_Activation_ApplicationModel_4__Z(
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
    v3 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v6 + 88LL))(v6, a2);
    if ( v4 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  }
  return v3;
}

```

## disassembly

```asm
0x140010630  mov     [rsp+arg_10], rbx
0x140010635  mov     [rsp+arg_18], rsi
0x14001063a  push    rdi
0x14001063b  sub     rsp, 40h
0x14001063f  mov     rax, cs:__security_cookie
0x140010646  xor     rax, rsp
0x140010649  mov     [rsp+48h+var_18], rax
0x14001064e  mov     rsi, rdx
0x140010651  cmp     byte ptr [rcx+0B8h], 0
0x140010658  jz      short loc_140010661
0x14001065a  call    cs:__imp_?__abi_WinRTraiseObjectDisposedException@@YAXXZ; __abi_WinRTraiseObjectDisposedException(void)
0x140010660  int     3; Trap to Debugger
0x140010661  mov     [rsp+48h+var_20], 0
0x14001066a  mov     rcx, [rcx+38h]
0x14001066e  mov     rax, [rcx]
0x140010671  lea     r8, [rsp+48h+var_20]
0x140010676  lea     rdx, __uuidof_?AUIApplicationOverrides@Xaml@UI@Windows@@
0x14001067d  mov     rax, [rax]
0x140010680  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010685  mov     edi, eax
0x140010687  test    eax, eax
0x140010689  jnz     short loc_1400106BE
0x14001068b  mov     rbx, [rsp+48h+var_20]
0x140010690  mov     [rsp+48h+var_28], rbx
0x140010695  mov     rax, [rbx]
0x140010698  mov     rdx, rsi
0x14001069b  mov     rcx, rbx
0x14001069e  mov     rax, [rax+58h]
0x1400106a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400106a7  mov     edi, eax
0x1400106a9  test    rbx, rbx
0x1400106ac  jz      short loc_1400106BE
0x1400106ae  mov     rax, [rbx]
0x1400106b1  mov     rcx, rbx
0x1400106b4  mov     rax, [rax+10h]
0x1400106b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400106bd  nop
0x1400106be  mov     eax, edi
0x1400106c0  mov     rcx, [rsp+48h+var_18]
0x1400106c5  xor     rcx, rsp; StackCookie
0x1400106c8  call    __security_check_cookie
0x1400106cd  mov     rbx, [rsp+48h+arg_10]
0x1400106d2  mov     rsi, [rsp+48h+arg_18]
0x1400106d7  add     rsp, 40h
0x1400106db  pop     rdi
0x1400106dc  retn
```
