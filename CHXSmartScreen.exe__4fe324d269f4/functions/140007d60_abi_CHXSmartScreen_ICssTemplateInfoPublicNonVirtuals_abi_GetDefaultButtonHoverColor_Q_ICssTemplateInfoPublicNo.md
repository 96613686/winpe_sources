# ?__abi_CHXSmartScreen___ICssTemplateInfoPublicNonVirtuals____abi_GetDefaultButtonHoverColor@?Q__ICssTemplateInfoPublicNonVirtuals@CHXSmartScreen@@CssTemplateInfo@2@UE$AAAJPEAPE$AAVString@Platform@@@Z

- ea: `0x140007d60`
- end: `0x140007ddf`
- name: `?__abi_CHXSmartScreen___ICssTemplateInfoPublicNonVirtuals____abi_GetDefaultButtonHoverColor@?Q__ICssTemplateInfoPublicNonVirtuals@CHXSmartScreen@@CssTemplateInfo@2@UE$AAAJPEAPE$AAVString@Platform@@@Z`
- size: `127`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1400039c2`
- `0x140007d60`
- `0x1400086b0`
- `0x140031960`

## import_xrefs

- `wincorlib!?__abi_WinRTraiseObjectDisposedException@@YAXXZ` at `0x140007d82`
- `wincorlib!?__abi_WinRTraiseObjectDisposedException@@YAXXZ` at `0x140007d82`

## pseudocode

```c
__int64 __fastcall ___abi_CHXSmartScreen___ICssTemplateInfoPublicNonVirtuals____abi_GetDefaultButtonHoverColor__Q__ICssTemplateInfoPublicNonVirtuals_CHXSmartScreen__CssTemplateInfo_2_UE_AAAJPEAPE_AAVString_Platform___Z(
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
  v3 = *(HSTRING *)(a1 + 64);
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
0x140007d60  mov     [rsp+arg_10], rbx
0x140007d65  push    rdi
0x140007d66  sub     rsp, 30h
0x140007d6a  mov     rax, cs:__security_cookie
0x140007d71  xor     rax, rsp
0x140007d74  mov     [rsp+38h+var_10], rax
0x140007d79  mov     rdi, rdx
0x140007d7c  cmp     byte ptr [rcx+70h], 0
0x140007d80  jz      short loc_140007D89
0x140007d82  call    cs:__imp_?__abi_WinRTraiseObjectDisposedException@@YAXXZ; __abi_WinRTraiseObjectDisposedException(void)
0x140007d88  int     3; Trap to Debugger
0x140007d89  xor     ebx, ebx
0x140007d8b  mov     [rdx], rbx
0x140007d8e  mov     rcx, [rcx+40h]; string
0x140007d92  test    rcx, rcx
0x140007d95  jz      short loc_140007DB1
0x140007d97  mov     [rsp+38h+newString], rbx
0x140007d9c  lea     rdx, [rsp+38h+newString]; newString
0x140007da1  call    WindowsDuplicateString_0
0x140007da6  test    eax, eax
0x140007da8  js      short loc_140007DD6
0x140007daa  mov     rax, [rsp+38h+newString]
0x140007daf  jmp     short loc_140007DB3
0x140007db1  xor     eax, eax
0x140007db3  mov     [rdi], rax
0x140007db6  jmp     short loc_140007DBC
0x140007db8  mov     ebx, dword ptr [rsp+38h+newString]
0x140007dbc  mov     eax, ebx
0x140007dbe  mov     rcx, [rsp+38h+var_10]
0x140007dc3  xor     rcx, rsp; StackCookie
0x140007dc6  call    __security_check_cookie
0x140007dcb  mov     rbx, [rsp+38h+arg_10]
0x140007dd0  add     rsp, 30h
0x140007dd4  pop     rdi
0x140007dd5  retn
0x140007dd6  mov     ecx, eax; int
0x140007dd8  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
```
