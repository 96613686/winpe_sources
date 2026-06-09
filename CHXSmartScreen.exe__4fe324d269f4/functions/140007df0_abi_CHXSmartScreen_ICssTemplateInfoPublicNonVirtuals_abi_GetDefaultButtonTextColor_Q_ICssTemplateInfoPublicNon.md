# ?__abi_CHXSmartScreen___ICssTemplateInfoPublicNonVirtuals____abi_GetDefaultButtonTextColor@?Q__ICssTemplateInfoPublicNonVirtuals@CHXSmartScreen@@CssTemplateInfo@2@UE$AAAJPEAPE$AAVString@Platform@@@Z

- ea: `0x140007df0`
- end: `0x140007e6f`
- name: `?__abi_CHXSmartScreen___ICssTemplateInfoPublicNonVirtuals____abi_GetDefaultButtonTextColor@?Q__ICssTemplateInfoPublicNonVirtuals@CHXSmartScreen@@CssTemplateInfo@2@UE$AAAJPEAPE$AAVString@Platform@@@Z`
- size: `127`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1400039c2`
- `0x140007df0`
- `0x1400086b0`
- `0x140031960`

## import_xrefs

- `wincorlib!?__abi_WinRTraiseObjectDisposedException@@YAXXZ` at `0x140007e12`
- `wincorlib!?__abi_WinRTraiseObjectDisposedException@@YAXXZ` at `0x140007e12`

## pseudocode

```c
__int64 __fastcall ___abi_CHXSmartScreen___ICssTemplateInfoPublicNonVirtuals____abi_GetDefaultButtonTextColor__Q__ICssTemplateInfoPublicNonVirtuals_CHXSmartScreen__CssTemplateInfo_2_UE_AAAJPEAPE_AAVString_Platform___Z(
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
  v3 = *(HSTRING *)(a1 + 56);
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
0x140007df0  mov     [rsp+arg_10], rbx
0x140007df5  push    rdi
0x140007df6  sub     rsp, 30h
0x140007dfa  mov     rax, cs:__security_cookie
0x140007e01  xor     rax, rsp
0x140007e04  mov     [rsp+38h+var_10], rax
0x140007e09  mov     rdi, rdx
0x140007e0c  cmp     byte ptr [rcx+70h], 0
0x140007e10  jz      short loc_140007E19
0x140007e12  call    cs:__imp_?__abi_WinRTraiseObjectDisposedException@@YAXXZ; __abi_WinRTraiseObjectDisposedException(void)
0x140007e18  int     3; Trap to Debugger
0x140007e19  xor     ebx, ebx
0x140007e1b  mov     [rdx], rbx
0x140007e1e  mov     rcx, [rcx+38h]; string
0x140007e22  test    rcx, rcx
0x140007e25  jz      short loc_140007E41
0x140007e27  mov     [rsp+38h+newString], rbx
0x140007e2c  lea     rdx, [rsp+38h+newString]; newString
0x140007e31  call    WindowsDuplicateString_0
0x140007e36  test    eax, eax
0x140007e38  js      short loc_140007E66
0x140007e3a  mov     rax, [rsp+38h+newString]
0x140007e3f  jmp     short loc_140007E43
0x140007e41  xor     eax, eax
0x140007e43  mov     [rdi], rax
0x140007e46  jmp     short loc_140007E4C
0x140007e48  mov     ebx, dword ptr [rsp+38h+newString]
0x140007e4c  mov     eax, ebx
0x140007e4e  mov     rcx, [rsp+38h+var_10]
0x140007e53  xor     rcx, rsp; StackCookie
0x140007e56  call    __security_check_cookie
0x140007e5b  mov     rbx, [rsp+38h+arg_10]
0x140007e60  add     rsp, 30h
0x140007e64  pop     rdi
0x140007e65  retn
0x140007e66  mov     ecx, eax; int
0x140007e68  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
```
