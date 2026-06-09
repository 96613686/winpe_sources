# wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::make(ushort const *,unsigned __int64)

- ea: `0x180010c08`
- end: `0x180010caf`
- name: `?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEBG_K@Z`
- size: `167`
- prototype: `__int64 __fastcall(HSTRING *string, PCNZWCH sourceString, UINT32 length)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000a3ec`

## callees

- `0x180007fac`
- `0x180010c08`
- `0x180011398`
- `0x1800113ec`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180010c34`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180010c34`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPreallocateStringBuffer` at `0x180010c9c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPreallocateStringBuffer` at `0x180010c9c`

## string_xrefs

- `0x180010c4a`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 __fastcall wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::make(
        HSTRING *string,
        PCNZWCH sourceString,
        UINT32 length)
{
  HRESULT v6; // ebx
  __int64 v7; // rdx
  int v9; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( sourceString )
  {
    wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
      string,
      0);
    v6 = WindowsCreateString(sourceString, length, string);
    if ( v6 < 0 )
    {
      v7 = 5474;
LABEL_4:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v7,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        (const char *)(unsigned int)v6,
        v9);
      return (unsigned int)v6;
    }
    string[2] = 0;
    wil::details::unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&long WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>::reset(
      string + 1,
      0);
  }
  else
  {
    wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
      string,
      0);
    wil::details::unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&long WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>::reset(
      string + 1,
      0);
    v6 = WindowsPreallocateStringBuffer(length, (WCHAR **)string + 2, (HSTRING_BUFFER *)string + 1);
    if ( v6 < 0 )
    {
      v7 = 5482;
      goto LABEL_4;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180010c08  mov     [rsp+arg_0], rbx
0x180010c0d  mov     [rsp+arg_8], rsi
0x180010c12  push    rdi; int
0x180010c13  sub     rsp, 20h
0x180010c17  mov     rsi, r8
0x180010c1a  mov     rbx, rdx
0x180010c1d  mov     rdi, rcx
0x180010c20  test    rdx, rdx
0x180010c23  jz      short loc_180010C82
0x180010c25  xor     edx, edx
0x180010c27  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x180010c2c  mov     r8, rdi; string
0x180010c2f  mov     edx, esi; length
0x180010c31  mov     rcx, rbx; sourceString
0x180010c34  call    cs:__imp_WindowsCreateString
0x180010c3a  mov     ebx, eax
0x180010c3c  test    eax, eax
0x180010c3e  jns     short loc_180010C5D
0x180010c40  mov     edx, 1562h; void *
0x180010c45  mov     rcx, [rsp+28h]; this
0x180010c4a  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180010c51  mov     r9d, ebx; char *
0x180010c54  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010c59  mov     eax, ebx
0x180010c5b  jmp     short loc_180010C72
0x180010c5d  lea     rcx, [rdi+8]
0x180010c61  mov     qword ptr [rdi+10h], 0
0x180010c69  xor     edx, edx
0x180010c6b  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING_BUFFER__@@P6AJPEAU1@@Z$1?WindowsDeleteStringBuffer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING_BUFFER__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>::reset(HSTRING_BUFFER__ *)
0x180010c70  xor     eax, eax
0x180010c72  mov     rbx, [rsp+28h+arg_0]
0x180010c77  mov     rsi, [rsp+28h+arg_8]
0x180010c7c  add     rsp, 20h
0x180010c80  pop     rdi
0x180010c81  retn
0x180010c82  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x180010c87  xor     edx, edx
0x180010c89  lea     rcx, [rdi+8]
0x180010c8d  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING_BUFFER__@@P6AJPEAU1@@Z$1?WindowsDeleteStringBuffer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING_BUFFER__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>::reset(HSTRING_BUFFER__ *)
0x180010c92  lea     rdx, [rdi+10h]; charBuffer
0x180010c96  mov     ecx, esi; length
0x180010c98  lea     r8, [rdi+8]; bufferHandle
0x180010c9c  call    cs:__imp_WindowsPreallocateStringBuffer
0x180010ca2  mov     ebx, eax
0x180010ca4  test    eax, eax
0x180010ca6  jns     short loc_180010C70
0x180010ca8  mov     edx, 156Ah
0x180010cad  jmp     short loc_180010C45
```
