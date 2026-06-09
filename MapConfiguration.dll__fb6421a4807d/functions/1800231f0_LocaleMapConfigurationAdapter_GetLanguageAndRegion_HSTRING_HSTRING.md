# LocaleMapConfigurationAdapter::GetLanguageAndRegion(HSTRING__ * *,HSTRING__ * *)

- ea: `0x1800231f0`
- end: `0x1800232b6`
- name: `?GetLanguageAndRegion@LocaleMapConfigurationAdapter@@UEAAJPEAPEAUHSTRING__@@0@Z`
- size: `198`
- prototype: `int(LocaleMapConfigurationAdapter *__hidden this, HSTRING *, HSTRING *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000c2f8`
- `0x1800231f0`
- `0x18002337c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180023246`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180023280`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180023246`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180023280`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002328d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800232a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002328d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800232a1`

## pseudocode

```c
__int64 __fastcall LocaleMapConfigurationAdapter::GetLanguageAndRegion(
        LocaleMapConfigurationAdapter *this,
        HSTRING *a2,
        HSTRING *a3)
{
  __int64 v3; // rbp
  const unsigned __int16 *v6; // rax
  __int64 v7; // r8
  HRESULT v8; // ebx
  const unsigned __int16 *v9; // rax
  __int64 v10; // r8
  HSTRING v12; // [rsp+40h] [rbp+8h] BYREF
  HSTRING string; // [rsp+58h] [rbp+20h] BYREF

  v3 = *((_QWORD *)this + 4);
  string = 0;
  v12 = 0;
  v6 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v3 + 384);
  v8 = Microsoft::WRL::Wrappers::HString::Set((Microsoft::WRL::Wrappers::HString *)&string, v6, *(_DWORD *)(v7 + 16));
  if ( v8 >= 0 )
  {
    v8 = WindowsDuplicateString(string, a2);
    if ( v8 >= 0 )
    {
      v9 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v3 + 352);
      v8 = Microsoft::WRL::Wrappers::HString::Set((Microsoft::WRL::Wrappers::HString *)&v12, v9, *(_DWORD *)(v10 + 16));
      if ( v8 >= 0 )
        v8 = WindowsDuplicateString(v12, a3);
    }
  }
  WindowsDeleteString(v12);
  v12 = 0;
  WindowsDeleteString(string);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800231f0  mov     [rsp+arg_8], rbx
0x1800231f5  push    rbp
0x1800231f6  push    rsi
0x1800231f7  push    rdi
0x1800231f8  sub     rsp, 20h
0x1800231fc  mov     rbp, [rcx+20h]
0x180023200  mov     rsi, r8
0x180023203  mov     rdi, rdx
0x180023206  mov     [rsp+38h+string], 0
0x18002320f  mov     [rsp+38h+arg_0], 0
0x180023218  lea     r8, [rbp+180h]
0x18002321f  mov     rcx, r8
0x180023222  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180023227  mov     r8d, [r8+10h]; unsigned int
0x18002322b  lea     rcx, [rsp+38h+string]; this
0x180023230  mov     rdx, rax; unsigned __int16 *
0x180023233  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x180023238  mov     ebx, eax
0x18002323a  test    eax, eax
0x18002323c  js      short loc_180023288
0x18002323e  mov     rcx, [rsp+38h+string]; string
0x180023243  mov     rdx, rdi; newString
0x180023246  call    cs:__imp_WindowsDuplicateString
0x18002324c  mov     ebx, eax
0x18002324e  test    eax, eax
0x180023250  js      short loc_180023288
0x180023252  lea     r8, [rbp+160h]
0x180023259  mov     rcx, r8
0x18002325c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180023261  mov     r8d, [r8+10h]; unsigned int
0x180023265  lea     rcx, [rsp+38h+arg_0]; this
0x18002326a  mov     rdx, rax; unsigned __int16 *
0x18002326d  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x180023272  mov     ebx, eax
0x180023274  test    eax, eax
0x180023276  js      short loc_180023288
0x180023278  mov     rcx, [rsp+38h+arg_0]; string
0x18002327d  mov     rdx, rsi; newString
0x180023280  call    cs:__imp_WindowsDuplicateString
0x180023286  mov     ebx, eax
0x180023288  mov     rcx, [rsp+38h+arg_0]; string
0x18002328d  call    cs:__imp_WindowsDeleteString
0x180023293  mov     rcx, [rsp+38h+string]; string
0x180023298  mov     [rsp+38h+arg_0], 0
0x1800232a1  call    cs:__imp_WindowsDeleteString
0x1800232a7  mov     eax, ebx
0x1800232a9  mov     rbx, [rsp+38h+arg_8]
0x1800232ae  add     rsp, 20h
0x1800232b2  pop     rdi
0x1800232b3  pop     rsi
0x1800232b4  pop     rbp
0x1800232b5  retn
```
