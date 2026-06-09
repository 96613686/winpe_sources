# wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(wchar_t const *,unsigned __int64)

- ea: `0x1800a61a8`
- end: `0x1800a61db`
- name: `??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@0@PEB_W_K@Z`
- size: `51`
- prototype: `HSTRING *__fastcall(HSTRING *string, PCNZWCH sourceString)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800a7810`

## callees

- `0x1800a61a8`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800a61cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800a61cc`

## pseudocode

```c
HSTRING *__fastcall wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(
        HSTRING *string,
        PCNZWCH sourceString)
{
  __int64 v4; // rdx

  v4 = -1;
  do
    ++v4;
  while ( sourceString[v4] );
  *string = 0;
  WindowsCreateString(sourceString, v4, string);
  return string;
}

```

## disassembly

```asm
0x1800a61a8  push    rbx
0x1800a61aa  sub     rsp, 20h
0x1800a61ae  mov     rax, rdx
0x1800a61b1  mov     rbx, rcx
0x1800a61b4  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800a61b8  xor     ecx, ecx
0x1800a61ba  inc     rdx; length
0x1800a61bd  cmp     [rax+rdx*2], cx
0x1800a61c1  jnz     short loc_1800A61BA
0x1800a61c3  mov     [rbx], rcx
0x1800a61c6  mov     r8, rbx; string
0x1800a61c9  mov     rcx, rax; sourceString
0x1800a61cc  call    cs:__imp_WindowsCreateString
0x1800a61d2  mov     rax, rbx
0x1800a61d5  add     rsp, 20h
0x1800a61d9  pop     rbx
0x1800a61da  retn
```
