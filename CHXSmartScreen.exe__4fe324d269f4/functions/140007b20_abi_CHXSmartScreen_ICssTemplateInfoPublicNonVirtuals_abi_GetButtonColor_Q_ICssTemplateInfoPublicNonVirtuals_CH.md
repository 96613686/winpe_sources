# ?__abi_CHXSmartScreen___ICssTemplateInfoPublicNonVirtuals____abi_GetButtonColor@?Q__ICssTemplateInfoPublicNonVirtuals@CHXSmartScreen@@CssTemplateInfo@2@UE$AAAJPEAPE$AAVString@Platform@@@Z

- ea: `0x140007b20`
- end: `0x140007b9f`
- name: `?__abi_CHXSmartScreen___ICssTemplateInfoPublicNonVirtuals____abi_GetButtonColor@?Q__ICssTemplateInfoPublicNonVirtuals@CHXSmartScreen@@CssTemplateInfo@2@UE$AAAJPEAPE$AAVString@Platform@@@Z`
- size: `127`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1400039c2`
- `0x140007b20`
- `0x1400086b0`
- `0x140031960`

## import_xrefs

- `wincorlib!?__abi_WinRTraiseObjectDisposedException@@YAXXZ` at `0x140007b42`
- `wincorlib!?__abi_WinRTraiseObjectDisposedException@@YAXXZ` at `0x140007b42`

## pseudocode

```c
__int64 __fastcall ___abi_CHXSmartScreen___ICssTemplateInfoPublicNonVirtuals____abi_GetButtonColor__Q__ICssTemplateInfoPublicNonVirtuals_CHXSmartScreen__CssTemplateInfo_2_UE_AAAJPEAPE_AAVString_Platform___Z(
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
  v3 = *(HSTRING *)(a1 + 72);
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
0x140007b20  mov     [rsp+arg_10], rbx
0x140007b25  push    rdi
0x140007b26  sub     rsp, 30h
0x140007b2a  mov     rax, cs:__security_cookie
0x140007b31  xor     rax, rsp
0x140007b34  mov     [rsp+38h+var_10], rax
0x140007b39  mov     rdi, rdx
0x140007b3c  cmp     byte ptr [rcx+70h], 0
0x140007b40  jz      short loc_140007B49
0x140007b42  call    cs:__imp_?__abi_WinRTraiseObjectDisposedException@@YAXXZ; __abi_WinRTraiseObjectDisposedException(void)
0x140007b48  int     3; Trap to Debugger
0x140007b49  xor     ebx, ebx
0x140007b4b  mov     [rdx], rbx
0x140007b4e  mov     rcx, [rcx+48h]; string
0x140007b52  test    rcx, rcx
0x140007b55  jz      short loc_140007B71
0x140007b57  mov     [rsp+38h+newString], rbx
0x140007b5c  lea     rdx, [rsp+38h+newString]; newString
0x140007b61  call    WindowsDuplicateString_0
0x140007b66  test    eax, eax
0x140007b68  js      short loc_140007B96
0x140007b6a  mov     rax, [rsp+38h+newString]
0x140007b6f  jmp     short loc_140007B73
0x140007b71  xor     eax, eax
0x140007b73  mov     [rdi], rax
0x140007b76  jmp     short loc_140007B7C
0x140007b78  mov     ebx, dword ptr [rsp+38h+newString]
0x140007b7c  mov     eax, ebx
0x140007b7e  mov     rcx, [rsp+38h+var_10]
0x140007b83  xor     rcx, rsp; StackCookie
0x140007b86  call    __security_check_cookie
0x140007b8b  mov     rbx, [rsp+38h+arg_10]
0x140007b90  add     rsp, 30h
0x140007b94  pop     rdi
0x140007b95  retn
0x140007b96  mov     ecx, eax; int
0x140007b98  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
```
