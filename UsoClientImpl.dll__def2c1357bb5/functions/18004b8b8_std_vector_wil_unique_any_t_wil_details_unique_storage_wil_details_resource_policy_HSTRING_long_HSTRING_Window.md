# std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>,std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>::~vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>,std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>(void)

- ea: `0x18004b8b8`
- end: `0x18004b964`
- name: `??1?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@QEAA@XZ`
- size: `172`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callers

- `0x18004ba04`
- `0x1800610a9`
- `0x1800610e7`

## callees

- `0x18004b8b8`
- `0x180056a08`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18004b95d`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18004b95d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004b8e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004b8e0`

## pseudocode

```c
void __fastcall std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::~vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(
        __int64 a1)
{
  HSTRING *v1; // rbx
  HSTRING *v3; // rsi
  HSTRING *v4; // rcx

  v1 = *(HSTRING **)a1;
  if ( *(_QWORD *)a1 )
  {
    v3 = *(HSTRING **)(a1 + 8);
    while ( v1 != v3 )
    {
      if ( *v1 )
        WindowsDeleteString(*v1);
      ++v1;
    }
    v4 = *(HSTRING **)a1;
    if ( ((*(_QWORD *)(a1 + 16) - *(_QWORD *)a1) & 0xFFFFFFFFFFFFFFF8uLL) >= 0x1000 )
    {
      if ( (unsigned __int64)((char *)v4 - (char *)*(v4 - 1) - 8) > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
      v4 = (HSTRING *)*(v4 - 1);
    }
    operator delete(v4);
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
    *(_QWORD *)(a1 + 16) = 0;
  }
}

```

## disassembly

```asm
0x18004b8b8  mov     [rsp+arg_8], rbx
0x18004b8bd  mov     [rsp+arg_10], rsi
0x18004b8c2  push    rdi
0x18004b8c3  sub     rsp, 30h
0x18004b8c7  mov     rbx, [rcx]
0x18004b8ca  mov     rdi, rcx
0x18004b8cd  test    rbx, rbx
0x18004b8d0  jz      short loc_18004B93A
0x18004b8d2  mov     rsi, [rcx+8]
0x18004b8d6  jmp     short loc_18004B8EA
0x18004b8d8  mov     rcx, [rbx]; string
0x18004b8db  test    rcx, rcx
0x18004b8de  jz      short loc_18004B8E6
0x18004b8e0  call    cs:__imp_WindowsDeleteString
0x18004b8e6  add     rbx, 8
0x18004b8ea  cmp     rbx, rsi
0x18004b8ed  jnz     short loc_18004B8D8
0x18004b8ef  mov     rcx, [rdi]
0x18004b8f2  mov     rdx, [rdi+10h]
0x18004b8f6  sub     rdx, rcx
0x18004b8f9  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18004b8fd  cmp     rdx, 1000h
0x18004b904  jb      short loc_18004B91E
0x18004b906  mov     rax, [rcx-8]
0x18004b90a  add     rdx, 27h ; '''
0x18004b90e  sub     rcx, rax
0x18004b911  sub     rcx, 8
0x18004b915  cmp     rcx, 1Fh
0x18004b919  ja      short loc_18004B94A
0x18004b91b  mov     rcx, rax; Block
0x18004b91e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18004b923  mov     qword ptr [rdi], 0
0x18004b92a  mov     qword ptr [rdi+8], 0
0x18004b932  mov     qword ptr [rdi+10h], 0
0x18004b93a  mov     rbx, [rsp+38h+arg_8]
0x18004b93f  mov     rsi, [rsp+38h+arg_10]
0x18004b944  add     rsp, 30h
0x18004b948  pop     rdi
0x18004b949  retn
0x18004b94a  xor     r9d, r9d; LineNo
0x18004b94d  mov     [rsp+38h+Reserved], 0; Reserved
0x18004b956  xor     r8d, r8d; FileName
0x18004b959  xor     edx, edx; FunctionName
0x18004b95b  xor     ecx, ecx; Expression
0x18004b95d  call    cs:__imp__invoke_watson
```
