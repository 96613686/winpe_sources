# UpdateDiagnostics::update_diagnostics::_CreateHStringArray(std::span<std::basic_string_view<wchar_t,std::char_traits<wchar_t>> const,-1>)

- ea: `0x18004b74c`
- end: `0x18004b8b2`
- name: `?_CreateHStringArray@update_diagnostics@UpdateDiagnostics@@CA?AV?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@V?$span@$$CBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@$0?0@4@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update`

## callers

- `0x18004ba04`

## callees

- `0x18000a1f8`
- `0x18001b95c`
- `0x180034a30`
- `0x18004b524`
- `0x18004b5f0`
- `0x18004b74c`
- `0x180056500`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004b868`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004b868`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18004b822`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18004b822`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall UpdateDiagnostics::update_diagnostics::_CreateHStringArray(__int64 a1, __int64 *a2)
{
  unsigned __int64 v4; // rsi
  __int64 v5; // r10
  _QWORD *v6; // r8
  _QWORD *v7; // rcx
  _QWORD *v8; // rdx
  __int64 v9; // rdi
  __int64 v10; // rsi
  HRESULT v11; // eax
  HSTRING *v12; // rdx
  HSTRING v13; // rcx
  int v15; // [rsp+20h] [rbp-28h]
  HSTRING string; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *(_OWORD *)a1 = 0;
  *(_QWORD *)a1 = 0;
  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 16) = 0;
  v15 = 1;
  v4 = a2[1];
  if ( v4 )
  {
    if ( v4 > 0x1FFFFFFFFFFFFFFFLL )
      std::vector<wchar_t>::_Xlength(a1, a2);
    v5 = std::_Allocate<16,std::_Default_allocate_traits>(8 * v4);
    v6 = *(_QWORD **)(a1 + 8);
    v7 = *(_QWORD **)a1;
    v8 = (_QWORD *)v5;
    while ( v7 != v6 )
    {
      *v8 = *v7;
      *v7 = 0;
      ++v8;
      ++v7;
    }
    std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::_Change_array(
      a1,
      v5,
      0,
      v4,
      1,
      a1);
  }
  v9 = *a2;
  v10 = v9 + 16 * v4;
  while ( v9 != v10 )
  {
    if ( *(_QWORD *)(v9 + 8) )
    {
      string = 0;
      v11 = WindowsCreateString(*(PCNZWCH *)v9, *(_DWORD *)(v9 + 8), &string);
      if ( v11 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x1AE,
          (unsigned int)"C:\\__w\\1\\s\\src\\Calliope\\inc\\UpDiag.hpp",
          (const char *)(unsigned int)v11,
          v15);
      v12 = *(HSTRING **)(a1 + 8);
      if ( v12 == *(HSTRING **)(a1 + 16) )
      {
        std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::_Emplace_reallocate<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(
          a1,
          v12,
          &string);
        v13 = string;
      }
      else
      {
        *v12 = string;
        v13 = 0;
        string = 0;
        *(_QWORD *)(a1 + 8) += 8LL;
      }
      if ( v13 )
        WindowsDeleteString(v13);
    }
    v9 += 16;
  }
  return a1;
}

```

## disassembly

```asm
0x18004b74c  mov     [rsp+arg_10], rbx
0x18004b751  mov     [rsp+arg_18], rsi
0x18004b756  push    rdi
0x18004b757  sub     rsp, 40h
0x18004b75b  mov     rax, cs:__security_cookie
0x18004b762  xor     rax, rsp
0x18004b765  mov     [rsp+48h+var_10], rax
0x18004b76a  mov     rdi, rdx
0x18004b76d  mov     rbx, rcx
0x18004b770  mov     [rsp+48h+var_20], rcx
0x18004b775  mov     [rsp+48h+var_28], 0
0x18004b77d  xorps   xmm0, xmm0
0x18004b780  xor     eax, eax
0x18004b782  movups  xmmword ptr [rcx], xmm0
0x18004b785  mov     [rcx], rax
0x18004b788  mov     [rcx+8], rax
0x18004b78c  mov     [rcx+10h], rax
0x18004b790  mov     [rsp+48h+var_28], 1
0x18004b798  mov     rsi, [rdx+8]
0x18004b79c  test    rsi, rsi
0x18004b79f  jz      short loc_18004B7FB
0x18004b7a1  mov     rax, 1FFFFFFFFFFFFFFFh
0x18004b7ab  cmp     rsi, rax
0x18004b7ae  ja      loc_18004B897
0x18004b7b4  lea     rcx, ds:0[rsi*8]
0x18004b7bc  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18004b7c1  mov     r10, rax
0x18004b7c4  mov     r8, [rbx+8]
0x18004b7c8  mov     rcx, [rbx]
0x18004b7cb  mov     rdx, rax
0x18004b7ce  jmp     short loc_18004B7E5
0x18004b7d0  mov     rax, [rcx]
0x18004b7d3  mov     [rdx], rax
0x18004b7d6  mov     qword ptr [rcx], 0
0x18004b7dd  lea     rdx, [rdx+8]
0x18004b7e1  add     rcx, 8
0x18004b7e5  cmp     rcx, r8
0x18004b7e8  jnz     short loc_18004B7D0
0x18004b7ea  mov     r9, rsi
0x18004b7ed  xor     r8d, r8d
0x18004b7f0  mov     rdx, r10
0x18004b7f3  mov     rcx, rbx
0x18004b7f6  call    ?_Change_array@?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@AEAAXQEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@_K1@Z; std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::_Change_array(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> * const,unsigned __int64,unsigned __int64)
0x18004b7fb  mov     rdi, [rdi]
0x18004b7fe  shl     rsi, 4
0x18004b802  add     rsi, rdi
0x18004b805  jmp     short loc_18004B872
0x18004b807  cmp     qword ptr [rdi+8], 0
0x18004b80c  jz      short loc_18004B86E
0x18004b80e  mov     [rsp+48h+string], 0
0x18004b817  lea     r8, [rsp+48h+string]; string
0x18004b81c  mov     edx, [rdi+8]; length
0x18004b81f  mov     rcx, [rdi]; sourceString
0x18004b822  call    cs:__imp_WindowsCreateString
0x18004b828  mov     rcx, [rsp+48h]; this
0x18004b82d  test    eax, eax
0x18004b82f  js      short loc_18004B89D
0x18004b831  mov     rdx, [rbx+8]
0x18004b835  cmp     rdx, [rbx+10h]
0x18004b839  jz      short loc_18004B851
0x18004b83b  mov     rax, [rsp+48h+string]
0x18004b840  mov     [rdx], rax
0x18004b843  xor     ecx, ecx
0x18004b845  mov     [rsp+48h+string], rcx
0x18004b84a  add     qword ptr [rbx+8], 8
0x18004b84f  jmp     short loc_18004B863
0x18004b851  lea     r8, [rsp+48h+string]
0x18004b856  mov     rcx, rbx
0x18004b859  call    ??$_Emplace_reallocate@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@AEAAPEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAV23@$$QEAV23@@Z; std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::_Emplace_reallocate<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> * const,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> &&)
0x18004b85e  mov     rcx, [rsp+48h+string]; string
0x18004b863  test    rcx, rcx
0x18004b866  jz      short loc_18004B86E
0x18004b868  call    cs:__imp_WindowsDeleteString
0x18004b86e  add     rdi, 10h
0x18004b872  cmp     rdi, rsi
0x18004b875  jnz     short loc_18004B807
0x18004b877  mov     rax, rbx
0x18004b87a  mov     rcx, [rsp+48h+var_10]
0x18004b87f  xor     rcx, rsp; StackCookie
0x18004b882  call    __security_check_cookie
0x18004b887  mov     rbx, [rsp+48h+arg_10]
0x18004b88c  mov     rsi, [rsp+48h+arg_18]
0x18004b891  add     rsp, 40h
0x18004b895  pop     rdi
0x18004b896  retn
0x18004b897  call    ?_Xlength@?$vector@_WV?$allocator@_W@std@@@std@@CAXXZ; std::vector<wchar_t>::_Xlength(void)
0x18004b89d  mov     r9d, eax; char *
0x18004b8a0  lea     r8, aCW1SSrcCalliop; "C:\\__w\\1\\s\\src\\Calliope\\inc\\UpDi"...
0x18004b8a7  mov     edx, 1AEh; void *
0x18004b8ac  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
