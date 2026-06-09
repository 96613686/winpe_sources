# ?__abi_CHXSmartScreen___ICssTemplateInfoPublicNonVirtuals____abi_GetForegroundTextColor@?Q__ICssTemplateInfoPublicNonVirtuals@CHXSmartScreen@@CssTemplateInfo@2@UE$AAAJPEAPE$AAVString@Platform@@@Z

- ea: `0x140007e80`
- end: `0x140007eff`
- name: `?__abi_CHXSmartScreen___ICssTemplateInfoPublicNonVirtuals____abi_GetForegroundTextColor@?Q__ICssTemplateInfoPublicNonVirtuals@CHXSmartScreen@@CssTemplateInfo@2@UE$AAAJPEAPE$AAVString@Platform@@@Z`
- size: `127`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1400039c2`
- `0x140007e80`
- `0x1400086b0`
- `0x140031960`

## import_xrefs

- `wincorlib!?__abi_WinRTraiseObjectDisposedException@@YAXXZ` at `0x140007ea2`
- `wincorlib!?__abi_WinRTraiseObjectDisposedException@@YAXXZ` at `0x140007ea2`

## pseudocode

```c
__int64 __fastcall ___abi_CHXSmartScreen___ICssTemplateInfoPublicNonVirtuals____abi_GetForegroundTextColor__Q__ICssTemplateInfoPublicNonVirtuals_CHXSmartScreen__CssTemplateInfo_2_UE_AAAJPEAPE_AAVString_Platform___Z(
        __int64 a1,
        HSTRING *a2)
{
  HSTRING v3; // rcx
  HRESULT v4; // eax
  HSTRING v5; // rax
  HSTRING newString; // [rsp+20h] [rbp-18h] BYREF

  if ( *(_BYTE *)(a1 + 112) )
  {
    __abi_WinRTraiseObjectDisposedException();
    __debugbreak();
  }
  *a2 = 0;
  v3 = *(HSTRING *)(a1 + 32);
  if ( v3 )
  {
    newString = 0;
    v4 = WindowsDuplicateString_0(v3, &newString);
    if ( v4 < 0 )
      __abi_WinRTraiseException(v4);
    v5 = newString;
  }
  else
  {
    v5 = 0;
  }
  *a2 = v5;
  return 0;
}

```

## disassembly

```asm
0x140007e80  mov     [rsp+arg_10], rbx
0x140007e85  push    rdi
0x140007e86  sub     rsp, 30h
0x140007e8a  mov     rax, cs:__security_cookie
0x140007e91  xor     rax, rsp
0x140007e94  mov     [rsp+38h+var_10], rax
0x140007e99  mov     rdi, rdx
0x140007e9c  cmp     byte ptr [rcx+70h], 0
0x140007ea0  jz      short loc_140007EA9
0x140007ea2  call    cs:__imp_?__abi_WinRTraiseObjectDisposedException@@YAXXZ; __abi_WinRTraiseObjectDisposedException(void)
0x140007ea8  int     3; Trap to Debugger
0x140007ea9  xor     ebx, ebx
0x140007eab  mov     [rdx], rbx
0x140007eae  mov     rcx, [rcx+20h]; string
0x140007eb2  test    rcx, rcx
0x140007eb5  jz      short loc_140007ED1
0x140007eb7  mov     [rsp+38h+newString], rbx
0x140007ebc  lea     rdx, [rsp+38h+newString]; newString
0x140007ec1  call    WindowsDuplicateString_0
0x140007ec6  test    eax, eax
0x140007ec8  js      short loc_140007EF6
0x140007eca  mov     rax, [rsp+38h+newString]
0x140007ecf  jmp     short loc_140007ED3
0x140007ed1  xor     eax, eax
0x140007ed3  mov     [rdi], rax
0x140007ed6  jmp     short loc_140007EDC
0x140007ed8  mov     ebx, dword ptr [rsp+38h+newString]
0x140007edc  mov     eax, ebx
0x140007ede  mov     rcx, [rsp+38h+var_10]
0x140007ee3  xor     rcx, rsp; StackCookie
0x140007ee6  call    __security_check_cookie
0x140007eeb  mov     rbx, [rsp+38h+arg_10]
0x140007ef0  add     rsp, 30h
0x140007ef4  pop     rdi
0x140007ef5  retn
0x140007ef6  mov     ecx, eax; int
0x140007ef8  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
```
