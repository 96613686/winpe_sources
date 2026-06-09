# std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>,std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>::_Reallocation_guard::~_Reallocation_guard(void)

- ea: `0x18004b488`
- end: `0x18004b51e`
- name: `??1_Reallocation_guard@?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@QEAA@XZ`
- size: `150`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callers

- `0x18004b5f0`

## callees

- `0x18004b488`
- `0x180056a08`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18004b517`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18004b517`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004b4b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004b4b3`

## pseudocode

```c
void __fastcall std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::_Reallocation_guard::~_Reallocation_guard(
        _QWORD *a1)
{
  HSTRING *v2; // rsi
  HSTRING *i; // rbx
  _QWORD *v4; // rcx

  if ( a1[1] )
  {
    v2 = (HSTRING *)a1[4];
    for ( i = (HSTRING *)a1[3]; i != v2; ++i )
    {
      if ( *i )
        WindowsDeleteString(*i);
    }
    v4 = (_QWORD *)a1[1];
    if ( (unsigned __int64)(8LL * a1[2]) >= 0x1000 )
    {
      if ( (unsigned __int64)v4 - *(v4 - 1) - 8 > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
      v4 = (_QWORD *)*(v4 - 1);
    }
    operator delete(v4);
  }
}

```

## disassembly

```asm
0x18004b488  mov     [rsp+arg_8], rbx
0x18004b48d  mov     [rsp+arg_10], rsi
0x18004b492  push    rdi
0x18004b493  sub     rsp, 30h
0x18004b497  cmp     qword ptr [rcx+8], 0
0x18004b49c  mov     rdi, rcx
0x18004b49f  jz      short loc_18004B4F4
0x18004b4a1  mov     rsi, [rcx+20h]
0x18004b4a5  mov     rbx, [rcx+18h]
0x18004b4a9  jmp     short loc_18004B4BD
0x18004b4ab  mov     rcx, [rbx]; string
0x18004b4ae  test    rcx, rcx
0x18004b4b1  jz      short loc_18004B4B9
0x18004b4b3  call    cs:__imp_WindowsDeleteString
0x18004b4b9  add     rbx, 8
0x18004b4bd  cmp     rbx, rsi
0x18004b4c0  jnz     short loc_18004B4AB
0x18004b4c2  mov     rdx, [rdi+10h]
0x18004b4c6  mov     rcx, [rdi+8]
0x18004b4ca  shl     rdx, 3
0x18004b4ce  cmp     rdx, 1000h
0x18004b4d5  jb      short loc_18004B4EF
0x18004b4d7  mov     rax, [rcx-8]
0x18004b4db  add     rdx, 27h ; '''
0x18004b4df  sub     rcx, rax
0x18004b4e2  sub     rcx, 8
0x18004b4e6  cmp     rcx, 1Fh
0x18004b4ea  ja      short loc_18004B504
0x18004b4ec  mov     rcx, rax; Block
0x18004b4ef  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18004b4f4  mov     rbx, [rsp+38h+arg_8]
0x18004b4f9  mov     rsi, [rsp+38h+arg_10]
0x18004b4fe  add     rsp, 30h
0x18004b502  pop     rdi
0x18004b503  retn
0x18004b504  xor     r9d, r9d; LineNo
0x18004b507  mov     [rsp+38h+Reserved], 0; Reserved
0x18004b510  xor     r8d, r8d; FileName
0x18004b513  xor     edx, edx; FunctionName
0x18004b515  xor     ecx, ecx; Expression
0x18004b517  call    cs:__imp__invoke_watson
```
