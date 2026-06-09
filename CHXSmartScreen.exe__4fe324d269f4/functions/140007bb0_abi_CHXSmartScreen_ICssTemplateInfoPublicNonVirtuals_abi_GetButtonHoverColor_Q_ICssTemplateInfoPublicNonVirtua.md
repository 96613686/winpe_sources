# ?__abi_CHXSmartScreen___ICssTemplateInfoPublicNonVirtuals____abi_GetButtonHoverColor@?Q__ICssTemplateInfoPublicNonVirtuals@CHXSmartScreen@@CssTemplateInfo@2@UE$AAAJPEAPE$AAVString@Platform@@@Z

- ea: `0x140007bb0`
- end: `0x140007c2f`
- name: `?__abi_CHXSmartScreen___ICssTemplateInfoPublicNonVirtuals____abi_GetButtonHoverColor@?Q__ICssTemplateInfoPublicNonVirtuals@CHXSmartScreen@@CssTemplateInfo@2@UE$AAAJPEAPE$AAVString@Platform@@@Z`
- size: `127`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1400039c2`
- `0x140007bb0`
- `0x1400086b0`
- `0x140031960`

## import_xrefs

- `wincorlib!?__abi_WinRTraiseObjectDisposedException@@YAXXZ` at `0x140007bd2`
- `wincorlib!?__abi_WinRTraiseObjectDisposedException@@YAXXZ` at `0x140007bd2`

## pseudocode

```c
__int64 __fastcall ___abi_CHXSmartScreen___ICssTemplateInfoPublicNonVirtuals____abi_GetButtonHoverColor__Q__ICssTemplateInfoPublicNonVirtuals_CHXSmartScreen__CssTemplateInfo_2_UE_AAAJPEAPE_AAVString_Platform___Z(
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
  v3 = *(HSTRING *)(a1 + 80);
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
0x140007bb0  mov     [rsp+arg_10], rbx
0x140007bb5  push    rdi
0x140007bb6  sub     rsp, 30h
0x140007bba  mov     rax, cs:__security_cookie
0x140007bc1  xor     rax, rsp
0x140007bc4  mov     [rsp+38h+var_10], rax
0x140007bc9  mov     rdi, rdx
0x140007bcc  cmp     byte ptr [rcx+70h], 0
0x140007bd0  jz      short loc_140007BD9
0x140007bd2  call    cs:__imp_?__abi_WinRTraiseObjectDisposedException@@YAXXZ; __abi_WinRTraiseObjectDisposedException(void)
0x140007bd8  int     3; Trap to Debugger
0x140007bd9  xor     ebx, ebx
0x140007bdb  mov     [rdx], rbx
0x140007bde  mov     rcx, [rcx+50h]; string
0x140007be2  test    rcx, rcx
0x140007be5  jz      short loc_140007C01
0x140007be7  mov     [rsp+38h+newString], rbx
0x140007bec  lea     rdx, [rsp+38h+newString]; newString
0x140007bf1  call    WindowsDuplicateString_0
0x140007bf6  test    eax, eax
0x140007bf8  js      short loc_140007C26
0x140007bfa  mov     rax, [rsp+38h+newString]
0x140007bff  jmp     short loc_140007C03
0x140007c01  xor     eax, eax
0x140007c03  mov     [rdi], rax
0x140007c06  jmp     short loc_140007C0C
0x140007c08  mov     ebx, dword ptr [rsp+38h+newString]
0x140007c0c  mov     eax, ebx
0x140007c0e  mov     rcx, [rsp+38h+var_10]
0x140007c13  xor     rcx, rsp; StackCookie
0x140007c16  call    __security_check_cookie
0x140007c1b  mov     rbx, [rsp+38h+arg_10]
0x140007c20  add     rsp, 30h
0x140007c24  pop     rdi
0x140007c25  retn
0x140007c26  mov     ecx, eax; int
0x140007c28  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
```
