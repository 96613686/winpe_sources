# std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>,std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>::_Change_array(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> * const,unsigned __int64,unsigned __int64)

- ea: `0x18004b524`
- end: `0x18004b5e7`
- name: `?_Change_array@?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@AEAAXQEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@_K1@Z`
- size: `195`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callers

- `0x18004b5f0`
- `0x18004b74c`

## callees

- `0x18004b524`
- `0x180056a08`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18004b5e0`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18004b5e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004b55e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004b55e`

## pseudocode

```c
__int64 __fastcall std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::_Change_array(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  HSTRING *v4; // rbx
  HSTRING *v9; // rbp
  HSTRING *v10; // rcx
  __int64 result; // rax

  v4 = *(HSTRING **)a1;
  if ( *(_QWORD *)a1 )
  {
    v9 = *(HSTRING **)(a1 + 8);
    while ( v4 != v9 )
    {
      if ( *v4 )
        WindowsDeleteString(*v4);
      ++v4;
    }
    v10 = *(HSTRING **)a1;
    if ( ((*(_QWORD *)(a1 + 16) - *(_QWORD *)a1) & 0xFFFFFFFFFFFFFFF8uLL) >= 0x1000 )
    {
      if ( (unsigned __int64)((char *)v10 - (char *)*(v10 - 1) - 8) > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
      v10 = (HSTRING *)*(v10 - 1);
    }
    operator delete(v10);
  }
  *(_QWORD *)a1 = a2;
  *(_QWORD *)(a1 + 8) = a2 + 8 * a3;
  result = a2 + 8 * a4;
  *(_QWORD *)(a1 + 16) = result;
  return result;
}

```

## disassembly

```asm
0x18004b524  mov     [rsp+arg_8], rbx
0x18004b529  mov     [rsp+arg_10], rbp
0x18004b52e  mov     [rsp+arg_18], rsi
0x18004b533  push    rdi
0x18004b534  push    r14
0x18004b536  push    r15
0x18004b538  sub     rsp, 30h
0x18004b53c  mov     rbx, [rcx]
0x18004b53f  mov     r14, r9
0x18004b542  mov     r15, r8
0x18004b545  mov     rsi, rdx
0x18004b548  mov     rdi, rcx
0x18004b54b  test    rbx, rbx
0x18004b54e  jz      short loc_18004B5A1
0x18004b550  mov     rbp, [rcx+8]
0x18004b554  jmp     short loc_18004B568
0x18004b556  mov     rcx, [rbx]; string
0x18004b559  test    rcx, rcx
0x18004b55c  jz      short loc_18004B564
0x18004b55e  call    cs:__imp_WindowsDeleteString
0x18004b564  add     rbx, 8
0x18004b568  cmp     rbx, rbp
0x18004b56b  jnz     short loc_18004B556
0x18004b56d  mov     rcx, [rdi]
0x18004b570  mov     rdx, [rdi+10h]
0x18004b574  sub     rdx, rcx
0x18004b577  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18004b57b  cmp     rdx, 1000h
0x18004b582  jb      short loc_18004B59C
0x18004b584  mov     rax, [rcx-8]
0x18004b588  add     rdx, 27h ; '''
0x18004b58c  sub     rcx, rax
0x18004b58f  sub     rcx, 8
0x18004b593  cmp     rcx, 1Fh
0x18004b597  ja      short loc_18004B5CD
0x18004b599  mov     rcx, rax; Block
0x18004b59c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18004b5a1  mov     rbx, [rsp+48h+arg_8]
0x18004b5a6  lea     rax, [rsi+r15*8]
0x18004b5aa  mov     rbp, [rsp+48h+arg_10]
0x18004b5af  mov     [rdi], rsi
0x18004b5b2  mov     [rdi+8], rax
0x18004b5b6  lea     rax, [rsi+r14*8]
0x18004b5ba  mov     rsi, [rsp+48h+arg_18]
0x18004b5bf  mov     [rdi+10h], rax
0x18004b5c3  add     rsp, 30h
0x18004b5c7  pop     r15
0x18004b5c9  pop     r14
0x18004b5cb  pop     rdi
0x18004b5cc  retn
0x18004b5cd  xor     r9d, r9d; LineNo
0x18004b5d0  mov     [rsp+48h+Reserved], 0; Reserved
0x18004b5d9  xor     r8d, r8d; FileName
0x18004b5dc  xor     edx, edx; FunctionName
0x18004b5de  xor     ecx, ecx; Expression
0x18004b5e0  call    cs:__imp__invoke_watson
```
