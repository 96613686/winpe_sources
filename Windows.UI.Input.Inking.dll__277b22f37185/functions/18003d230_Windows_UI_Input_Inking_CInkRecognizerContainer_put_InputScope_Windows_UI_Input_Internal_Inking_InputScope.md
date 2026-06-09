# Windows::UI::Input::Inking::CInkRecognizerContainer::put_InputScope(Windows::UI::Input::Internal::Inking::InputScope)

- ea: `0x18003d230`
- end: `0x18003d2de`
- name: `?put_InputScope@CInkRecognizerContainer@Inking@Input@UI@Windows@@UEAAJW4InputScope@2Internal@345@@Z`
- size: `174`
- prototype: `__int64 __fastcall(Windows::UI::Input::Inking::CInkRecognizerContainer *__hidden this, enum InputScope)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18001f73c`
- `0x18003d230`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003d2b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003d2b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003d29f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003d29f`

## pseudocode

```c
__int64 __fastcall Windows::UI::Input::Inking::CInkRecognizerContainer::put_InputScope(
        Windows::UI::Input::Inking::CInkRecognizerContainer *this,
        enum InputScope a2)
{
  unsigned int i; // eax
  wchar_t *v4; // r9
  unsigned __int64 v5; // rcx
  HRESULT v6; // ebx
  const WCHAR *v7; // r9
  HSTRING v8; // rcx
  UINT32 length; // [rsp+40h] [rbp+18h] BYREF
  HSTRING string; // [rsp+48h] [rbp+20h] BYREF

  for ( i = 0; ; ++i )
  {
    if ( i >= 0x2A )
      return (unsigned int)-2147024809;
    if ( *((_DWORD *)&off_18010D070 + 4 * (int)i + 2) == a2 )
      break;
  }
  v4 = (&off_18010D070)[2 * (int)i];
  if ( v4 )
  {
    length = 0;
    v5 = -1;
    string = 0;
    do
      ++v5;
    while ( v4[v5] );
    v6 = ULongLongToUInt(v5, &length);
    if ( v6 >= 0 )
    {
      v6 = WindowsCreateString(v7, length, &string);
      if ( v6 >= 0 )
      {
        v8 = (HSTRING)*((_QWORD *)this + 5);
        *((_QWORD *)this + 5) = string;
        WindowsDeleteString(v8);
      }
    }
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18003d230  mov     [rsp+arg_0], rbx
0x18003d235  mov     [rsp+arg_8], rsi
0x18003d23a  push    rdi
0x18003d23b  sub     rsp, 20h
0x18003d23f  xor     esi, esi
0x18003d241  lea     r9, off_18010D070; "(!IS_DEFAULT)"
0x18003d248  mov     eax, esi
0x18003d24a  mov     rdi, rcx
0x18003d24d  cmp     eax, 2Ah ; '*'
0x18003d250  jnb     short loc_18003D2C7
0x18003d252  movsxd  r8, eax
0x18003d255  add     r8, r8
0x18003d258  cmp     [r9+r8*8+8], edx
0x18003d25d  jz      short loc_18003D263
0x18003d25f  inc     eax
0x18003d261  jmp     short loc_18003D24D
0x18003d263  mov     r9, [r9+r8*8]
0x18003d267  test    r9, r9
0x18003d26a  jz      short loc_18003D2C0
0x18003d26c  mov     [rsp+28h+length], esi
0x18003d270  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18003d274  mov     [rsp+28h+string], rsi
0x18003d279  inc     rcx; unsigned __int64
0x18003d27c  cmp     [r9+rcx*2], si
0x18003d281  jnz     short loc_18003D279
0x18003d283  lea     rdx, [rsp+28h+length]; unsigned int *
0x18003d288  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x18003d28d  mov     ebx, eax
0x18003d28f  test    eax, eax
0x18003d291  js      short loc_18003D2CC
0x18003d293  mov     edx, [rsp+28h+length]; length
0x18003d297  lea     r8, [rsp+28h+string]; string
0x18003d29c  mov     rcx, r9; sourceString
0x18003d29f  call    cs:__imp_WindowsCreateString
0x18003d2a5  mov     ebx, eax
0x18003d2a7  test    eax, eax
0x18003d2a9  js      short loc_18003D2CC
0x18003d2ab  mov     rax, [rsp+28h+string]
0x18003d2b0  mov     rcx, [rdi+28h]; string
0x18003d2b4  mov     [rdi+28h], rax
0x18003d2b8  call    cs:__imp_WindowsDeleteString
0x18003d2be  jmp     short loc_18003D2CC
0x18003d2c0  mov     ebx, 80004003h
0x18003d2c5  jmp     short loc_18003D2CC
0x18003d2c7  mov     ebx, 80070057h
0x18003d2cc  mov     rsi, [rsp+28h+arg_8]
0x18003d2d1  mov     eax, ebx
0x18003d2d3  mov     rbx, [rsp+28h+arg_0]
0x18003d2d8  add     rsp, 20h
0x18003d2dc  pop     rdi
0x18003d2dd  retn
```
