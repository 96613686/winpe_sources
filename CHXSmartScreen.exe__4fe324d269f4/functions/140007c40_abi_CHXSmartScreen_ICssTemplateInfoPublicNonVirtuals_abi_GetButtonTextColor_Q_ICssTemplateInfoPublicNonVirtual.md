# ?__abi_CHXSmartScreen___ICssTemplateInfoPublicNonVirtuals____abi_GetButtonTextColor@?Q__ICssTemplateInfoPublicNonVirtuals@CHXSmartScreen@@CssTemplateInfo@2@UE$AAAJPEAPE$AAVString@Platform@@@Z

- ea: `0x140007c40`
- end: `0x140007cbf`
- name: `?__abi_CHXSmartScreen___ICssTemplateInfoPublicNonVirtuals____abi_GetButtonTextColor@?Q__ICssTemplateInfoPublicNonVirtuals@CHXSmartScreen@@CssTemplateInfo@2@UE$AAAJPEAPE$AAVString@Platform@@@Z`
- size: `127`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1400039c2`
- `0x140007c40`
- `0x1400086b0`
- `0x140031960`

## import_xrefs

- `wincorlib!?__abi_WinRTraiseObjectDisposedException@@YAXXZ` at `0x140007c62`
- `wincorlib!?__abi_WinRTraiseObjectDisposedException@@YAXXZ` at `0x140007c62`

## pseudocode

```c
__int64 __fastcall ___abi_CHXSmartScreen___ICssTemplateInfoPublicNonVirtuals____abi_GetButtonTextColor__Q__ICssTemplateInfoPublicNonVirtuals_CHXSmartScreen__CssTemplateInfo_2_UE_AAAJPEAPE_AAVString_Platform___Z(
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
  v3 = *(HSTRING *)(a1 + 88);
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
0x140007c40  mov     [rsp+arg_10], rbx
0x140007c45  push    rdi
0x140007c46  sub     rsp, 30h
0x140007c4a  mov     rax, cs:__security_cookie
0x140007c51  xor     rax, rsp
0x140007c54  mov     [rsp+38h+var_10], rax
0x140007c59  mov     rdi, rdx
0x140007c5c  cmp     byte ptr [rcx+70h], 0
0x140007c60  jz      short loc_140007C69
0x140007c62  call    cs:__imp_?__abi_WinRTraiseObjectDisposedException@@YAXXZ; __abi_WinRTraiseObjectDisposedException(void)
0x140007c68  int     3; Trap to Debugger
0x140007c69  xor     ebx, ebx
0x140007c6b  mov     [rdx], rbx
0x140007c6e  mov     rcx, [rcx+58h]; string
0x140007c72  test    rcx, rcx
0x140007c75  jz      short loc_140007C91
0x140007c77  mov     [rsp+38h+newString], rbx
0x140007c7c  lea     rdx, [rsp+38h+newString]; newString
0x140007c81  call    WindowsDuplicateString_0
0x140007c86  test    eax, eax
0x140007c88  js      short loc_140007CB6
0x140007c8a  mov     rax, [rsp+38h+newString]
0x140007c8f  jmp     short loc_140007C93
0x140007c91  xor     eax, eax
0x140007c93  mov     [rdi], rax
0x140007c96  jmp     short loc_140007C9C
0x140007c98  mov     ebx, dword ptr [rsp+38h+newString]
0x140007c9c  mov     eax, ebx
0x140007c9e  mov     rcx, [rsp+38h+var_10]
0x140007ca3  xor     rcx, rsp; StackCookie
0x140007ca6  call    __security_check_cookie
0x140007cab  mov     rbx, [rsp+38h+arg_10]
0x140007cb0  add     rsp, 30h
0x140007cb4  pop     rdi
0x140007cb5  retn
0x140007cb6  mov     ecx, eax; int
0x140007cb8  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
```
