# ?__abi_CHXSmartScreen___ICssTemplateInfoPublicNonVirtuals____abi_GetDefaultButtonColor@?Q__ICssTemplateInfoPublicNonVirtuals@CHXSmartScreen@@CssTemplateInfo@2@UE$AAAJPEAPE$AAVString@Platform@@@Z

- ea: `0x140007cd0`
- end: `0x140007d4f`
- name: `?__abi_CHXSmartScreen___ICssTemplateInfoPublicNonVirtuals____abi_GetDefaultButtonColor@?Q__ICssTemplateInfoPublicNonVirtuals@CHXSmartScreen@@CssTemplateInfo@2@UE$AAAJPEAPE$AAVString@Platform@@@Z`
- size: `127`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1400039c2`
- `0x140007cd0`
- `0x1400086b0`
- `0x140031960`

## import_xrefs

- `wincorlib!?__abi_WinRTraiseObjectDisposedException@@YAXXZ` at `0x140007cf2`
- `wincorlib!?__abi_WinRTraiseObjectDisposedException@@YAXXZ` at `0x140007cf2`

## pseudocode

```c
__int64 __fastcall ___abi_CHXSmartScreen___ICssTemplateInfoPublicNonVirtuals____abi_GetDefaultButtonColor__Q__ICssTemplateInfoPublicNonVirtuals_CHXSmartScreen__CssTemplateInfo_2_UE_AAAJPEAPE_AAVString_Platform___Z(
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
  v3 = *(HSTRING *)(a1 + 48);
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
0x140007cd0  mov     [rsp+arg_10], rbx
0x140007cd5  push    rdi
0x140007cd6  sub     rsp, 30h
0x140007cda  mov     rax, cs:__security_cookie
0x140007ce1  xor     rax, rsp
0x140007ce4  mov     [rsp+38h+var_10], rax
0x140007ce9  mov     rdi, rdx
0x140007cec  cmp     byte ptr [rcx+70h], 0
0x140007cf0  jz      short loc_140007CF9
0x140007cf2  call    cs:__imp_?__abi_WinRTraiseObjectDisposedException@@YAXXZ; __abi_WinRTraiseObjectDisposedException(void)
0x140007cf8  int     3; Trap to Debugger
0x140007cf9  xor     ebx, ebx
0x140007cfb  mov     [rdx], rbx
0x140007cfe  mov     rcx, [rcx+30h]; string
0x140007d02  test    rcx, rcx
0x140007d05  jz      short loc_140007D21
0x140007d07  mov     [rsp+38h+newString], rbx
0x140007d0c  lea     rdx, [rsp+38h+newString]; newString
0x140007d11  call    WindowsDuplicateString_0
0x140007d16  test    eax, eax
0x140007d18  js      short loc_140007D46
0x140007d1a  mov     rax, [rsp+38h+newString]
0x140007d1f  jmp     short loc_140007D23
0x140007d21  xor     eax, eax
0x140007d23  mov     [rdi], rax
0x140007d26  jmp     short loc_140007D2C
0x140007d28  mov     ebx, dword ptr [rsp+38h+newString]
0x140007d2c  mov     eax, ebx
0x140007d2e  mov     rcx, [rsp+38h+var_10]
0x140007d33  xor     rcx, rsp; StackCookie
0x140007d36  call    __security_check_cookie
0x140007d3b  mov     rbx, [rsp+38h+arg_10]
0x140007d40  add     rsp, 30h
0x140007d44  pop     rdi
0x140007d45  retn
0x140007d46  mov     ecx, eax; int
0x140007d48  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
```
