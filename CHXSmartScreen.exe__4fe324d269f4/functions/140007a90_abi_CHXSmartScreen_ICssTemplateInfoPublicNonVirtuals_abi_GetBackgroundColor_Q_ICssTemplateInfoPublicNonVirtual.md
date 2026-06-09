# ?__abi_CHXSmartScreen___ICssTemplateInfoPublicNonVirtuals____abi_GetBackgroundColor@?Q__ICssTemplateInfoPublicNonVirtuals@CHXSmartScreen@@CssTemplateInfo@2@UE$AAAJPEAPE$AAVString@Platform@@@Z

- ea: `0x140007a90`
- end: `0x140007b0f`
- name: `?__abi_CHXSmartScreen___ICssTemplateInfoPublicNonVirtuals____abi_GetBackgroundColor@?Q__ICssTemplateInfoPublicNonVirtuals@CHXSmartScreen@@CssTemplateInfo@2@UE$AAAJPEAPE$AAVString@Platform@@@Z`
- size: `127`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1400039c2`
- `0x140007a90`
- `0x1400086b0`
- `0x140031960`

## import_xrefs

- `wincorlib!?__abi_WinRTraiseObjectDisposedException@@YAXXZ` at `0x140007ab2`
- `wincorlib!?__abi_WinRTraiseObjectDisposedException@@YAXXZ` at `0x140007ab2`

## pseudocode

```c
__int64 __fastcall ___abi_CHXSmartScreen___ICssTemplateInfoPublicNonVirtuals____abi_GetBackgroundColor__Q__ICssTemplateInfoPublicNonVirtuals_CHXSmartScreen__CssTemplateInfo_2_UE_AAAJPEAPE_AAVString_Platform___Z(
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
  v3 = *(HSTRING *)(a1 + 40);
  if ( v3 )
  {
    newString = 0;
    v4 = WindowsDuplicateString_0(v3, &newString);
    if ( v4 < 0 )
    {
      try
      {
        __abi_WinRTraiseException(v4);
      }
      catch ( ... )
      {
        __abi_translateCurrentException(0);
      }
    }
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
0x140007a90  mov     [rsp+arg_10], rbx
0x140007a95  push    rdi
0x140007a96  sub     rsp, 30h
0x140007a9a  mov     rax, cs:__security_cookie
0x140007aa1  xor     rax, rsp
0x140007aa4  mov     [rsp+38h+var_10], rax
0x140007aa9  mov     rdi, rdx
0x140007aac  cmp     byte ptr [rcx+70h], 0
0x140007ab0  jz      short loc_140007AB9
0x140007ab2  call    cs:__imp_?__abi_WinRTraiseObjectDisposedException@@YAXXZ; __abi_WinRTraiseObjectDisposedException(void)
0x140007ab8  int     3; Trap to Debugger
0x140007ab9  xor     ebx, ebx
0x140007abb  mov     [rdx], rbx
0x140007abe  mov     rcx, [rcx+28h]; string
0x140007ac2  test    rcx, rcx
0x140007ac5  jz      short loc_140007AE1
0x140007ac7  mov     [rsp+38h+newString], rbx
0x140007acc  lea     rdx, [rsp+38h+newString]; newString
0x140007ad1  call    WindowsDuplicateString_0
0x140007ad6  test    eax, eax
0x140007ad8  js      short loc_140007B06
0x140007ada  mov     rax, [rsp+38h+newString]
0x140007adf  jmp     short loc_140007AE3
0x140007ae1  xor     eax, eax
0x140007ae3  mov     [rdi], rax
0x140007ae6  jmp     short loc_140007AEC
0x140007ae8  mov     ebx, dword ptr [rsp+38h+newString]
0x140007aec  mov     eax, ebx
0x140007aee  mov     rcx, [rsp+38h+var_10]
0x140007af3  xor     rcx, rsp; StackCookie
0x140007af6  call    __security_check_cookie
0x140007afb  mov     rbx, [rsp+38h+arg_10]
0x140007b00  add     rsp, 30h
0x140007b04  pop     rdi
0x140007b05  retn
0x140007b06  mov     ecx, eax; int
0x140007b08  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
```
