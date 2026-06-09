# ?__abi_Windows_Foundation_Collections_?$IObservableVector@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@____abi_add_VectorChanged@?Q?$IObservableVector@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@@Collections@Foundation@Windows@@?$Vector@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@U?$equal_to@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@@std@@@2Platform@@UE$AAAJPE$AAV?$VectorChangedEventHandler@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@@234@PEAVEventRegistrationToken@34@@Z

- ea: `0x140030480`
- end: `0x140030510`
- name: `?__abi_Windows_Foundation_Collections_?$IObservableVector@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@____abi_add_VectorChanged@?Q?$IObservableVector@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@@Collections@Foundation@Windows@@?$Vector@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@U?$equal_to@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@@std@@@2Platform@@UE$AAAJPE$AAV?$VectorChangedEventHandler@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@@234@PEAVEventRegistrationToken@34@@Z`
- size: `144`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x14000342d`
- `0x140030480`
- `0x140031960`
- `0x140035010`

## import_xrefs

- `wincorlib!?__abi_WinRTraiseObjectDisposedException@@YAXXZ` at `0x1400304af`
- `wincorlib!?__abi_WinRTraiseObjectDisposedException@@YAXXZ` at `0x1400304af`

## pseudocode

```c
__int64 __fastcall ___abi_Windows_Foundation_Collections___IObservableVector_PE_AAUIXamlMetadataProvider_Markup_Xaml_UI_Windows______abi_add_VectorChanged__Q__IObservableVector_PE_AAUIXamlMetadataProvider_Markup_Xaml_UI_Windows___Collections_Foundation_Windows____Vector_PE_AAUIXamlMetadataProvider_Markup_Xaml_UI_Windows__U__equal_to_PE_AAUIXamlMetadataProvider_Markup_Xaml_UI_Windows___std___2Platform__UE_AAAJPE_AAV__VectorChangedEventHandler_PE_AAUIXamlMetadataProvider_Markup_Xaml_UI_Windows___234_PEAVEventRegistrationToken_34__Z(
        _BYTE *a1,
        __int64 a2,
        _QWORD *a3)
{
  __int64 v7; // [rsp+20h] [rbp-28h] BYREF

  if ( a1[168] )
  {
    __abi_WinRTraiseObjectDisposedException();
    __debugbreak();
  }
  memset_0(&v7, 0, sizeof(v7));
  try
  {
    *a3 = v7;
    (*(void (__fastcall **)(_BYTE *, __int64 *, __int64))(*(_QWORD *)a1 + 64LL))(a1, &v7, a2);
    *a3 = v7;
  }
  catch ( ... )
  {
    __abi_translateCurrentException(0);
  }
  return 0;
}

```

## disassembly

```asm
0x140030480  mov     [rsp+arg_18], rbx
0x140030485  push    rsi
0x140030486  push    rdi
0x140030487  push    r14
0x140030489  sub     rsp, 30h
0x14003048d  mov     rax, cs:__security_cookie
0x140030494  xor     rax, rsp
0x140030497  mov     [rsp+48h+var_20], rax
0x14003049c  mov     rdi, r8
0x14003049f  mov     r14, rdx
0x1400304a2  mov     rsi, rcx
0x1400304a5  xor     ebx, ebx
0x1400304a7  cmp     [rcx+0A8h], bl
0x1400304ad  jz      short loc_1400304B6
0x1400304af  call    cs:__imp_?__abi_WinRTraiseObjectDisposedException@@YAXXZ; __abi_WinRTraiseObjectDisposedException(void)
0x1400304b5  int     3; Trap to Debugger
0x1400304b6  xor     edx, edx; Val
0x1400304b8  lea     r8d, [rdx+8]; Size
0x1400304bc  lea     rcx, [rsp+48h+var_28]; void *
0x1400304c1  call    memset_0
0x1400304c6  mov     rax, [rsp+48h+var_28]
0x1400304cb  mov     [rdi], rax
0x1400304ce  mov     rax, [rsi]
0x1400304d1  mov     r8, r14
0x1400304d4  lea     rdx, [rsp+48h+var_28]
0x1400304d9  mov     rcx, rsi
0x1400304dc  mov     rax, [rax+40h]
0x1400304e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400304e5  mov     rax, [rsp+48h+var_28]
0x1400304ea  mov     [rdi], rax
0x1400304ed  jmp     short loc_1400304F3
0x1400304ef  mov     ebx, dword ptr [rsp+48h+var_28]
0x1400304f3  mov     eax, ebx
0x1400304f5  mov     rcx, [rsp+48h+var_20]
0x1400304fa  xor     rcx, rsp; StackCookie
0x1400304fd  call    __security_check_cookie
0x140030502  mov     rbx, [rsp+48h+arg_18]
0x140030507  add     rsp, 30h
0x14003050b  pop     r14
0x14003050d  pop     rdi
0x14003050e  pop     rsi
0x14003050f  retn
```
