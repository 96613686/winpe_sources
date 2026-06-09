# Utf8StringToHString(char const *,HSTRING__ * *)

- ea: `0x1800181cc`
- end: `0x18001849d`
- name: `?Utf8StringToHString@@YAJPEBDPEAPEAUHSTRING__@@@Z`
- size: `721`
- prototype: `__int64 __fastcall(const char *Src, HSTRING *)`
- caller_count: `6`
- callee_count: `16`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800180e0`
- `0x180018130`
- `0x180018180`
- `0x1800f20e0`
- `0x1801952a0`
- `0x180195300`

## callees

- `0x1800181cc`
- `0x180019a40`
- `0x180021ae0`
- `0x180021b10`
- `0x180023530`
- `0x1800238d0`
- `0x180023fd4`
- `0x18003f11c`
- `0x180077e10`
- `0x180077e30`
- `0x1800ae89c`
- `0x1800c8458`
- `0x1801201a0`
- `0x1801202a0`
- `0x180123882`
- `0x180124088`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180018417`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180018417`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180018341`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180018341`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018448`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018448`

## string_xrefs

- `0x180018468`: `onecoreuap\shell\cloudstore\common\src\stringconversion.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Utf8StringToHString(const char *Src, HSTRING *a2)
{
  __int64 v4; // rdi
  size_t v5; // rbx
  __int64 v6; // r15
  HSTRING v7; // r14
  __int64 v8; // rdx
  int v9; // eax
  __int64 v10; // rbx
  HSTRING *v11; // r8
  const struct std::nothrow_t *v12; // rdx
  HSTRING v13; // rcx
  const WCHAR *v14; // rcx
  HRESULT v15; // ebx
  const char *v16; // r9
  HSTRING v17; // r14
  HSTRING v18; // rdi
  HSTRING v19; // rsi
  HSTRING v20; // rax
  __int64 result; // rax
  int v22[2]; // [rsp+20h] [rbp-88h] BYREF
  unsigned __int64 v23; // [rsp+28h] [rbp-80h] BYREF
  void *v24; // [rsp+30h] [rbp-78h] BYREF
  HSTRING string[2]; // [rsp+38h] [rbp-70h] BYREF
  __int128 v26; // [rsp+48h] [rbp-60h]
  PCNZWCH sourceString[2]; // [rsp+58h] [rbp-50h] BYREF
  UINT32 length; // [rsp+68h] [rbp-40h]
  unsigned __int64 v29; // [rsp+70h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  *a2 = 0;
  *(_OWORD *)string = 0;
  v26 = 0;
  v4 = -1;
  v5 = -1;
  do
    ++v5;
  while ( Src[v5] );
  try
  {
    if ( v5 > 0x7FFFFFFFFFFFFFFFLL )
      std::_Xlength_error("string too long");
    if ( v5 <= 0xF )
    {
      *(_QWORD *)&v26 = v5;
      *((_QWORD *)&v26 + 1) = 15;
      memcpy_0(string, Src, v5);
      *((_BYTE *)string + v5) = 0;
    }
    else
    {
      v6 = std::string::_Calculate_growth(v5, 15, 0x7FFFFFFFFFFFFFFFLL);
      v7 = (HSTRING)std::allocator<char>::allocate(string, v6 + 1);
      string[0] = v7;
      *(_QWORD *)&v26 = v5;
      *((_QWORD *)&v26 + 1) = v6;
      memcpy_0(v7, Src, v5);
      *((_BYTE *)v7 + v5) = 0;
    }
    v8 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
    v9 = *(_DWORD *)(v8 + 140);
    v10 = v8 + 144;
    if ( (v9 & 1) == 0 )
    {
      *(_DWORD *)(v8 + 140) = v9 | 1;
      std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>(
        v8 + 144,
        v8,
        140);
      _tlregdtor(Utf8StringToWideString_::_2_::_dynamic_atexit_destructor_for__converter_utf8_utf16__);
    }
    v11 = string;
    if ( *((_QWORD *)&v26 + 1) > 0xFu )
      v11 = (HSTRING *)string[0];
    do
      ++v4;
    while ( *((_BYTE *)v11 + v4) );
    std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::from_bytes(
      v10,
      sourceString,
      v11,
      (char *)v11 + v4);
    if ( *((_QWORD *)&v26 + 1) > 0xFu )
    {
      v12 = (const struct std::nothrow_t *)(*((_QWORD *)&v26 + 1) + 1LL);
      v23 = *((_QWORD *)&v26 + 1) + 1LL;
      v13 = string[0];
      v24 = string[0];
      if ( (unsigned __int64)(*((_QWORD *)&v26 + 1) + 1LL) >= 0x1000 )
      {
        std::_Adjust_manually_vector_aligned(&v24, &v23);
        v13 = (HSTRING)v24;
        v12 = (const struct std::nothrow_t *)v23;
      }
      operator delete(v13, v12);
    }
    *(_QWORD *)v22 = 0;
    string[0] = (HSTRING)v22;
    string[1] = 0;
    LOBYTE(v26) = 1;
    v14 = (const WCHAR *)sourceString;
    if ( v29 > 7 )
      v14 = sourceString[0];
    v15 = WindowsCreateString(v14, length, &string[1]);
    if ( (_BYTE)v26 )
    {
      v17 = string[1];
      v18 = string[0];
      v19 = *(HSTRING *)string[0];
      if ( *(_QWORD *)string[0] )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&v23);
        WindowsDeleteString(v19);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&v23);
      }
      *(_QWORD *)v18 = v17;
    }
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xAB,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\common\\src\\stringconversion.cpp",
        (const char *)(unsigned int)v15,
        v22[0]);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(v22);
      std::wstring::~wstring(sourceString);
      result = (unsigned int)v15;
    }
    else
    {
      v20 = *(HSTRING *)v22;
      *(_QWORD *)v22 = 0;
      *a2 = v20;
      if ( v29 > 7 )
        std::_Deallocate<16>((void *)sourceString[0], (const struct std::nothrow_t *)(2 * v29 + 2));
      result = 0;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xAF,
                           (unsigned int)"onecoreuap\\shell\\cloudstore\\common\\src\\stringconversion.cpp",
                           v16);
  }
  return result;
}

```

## disassembly

```asm
0x1800181cc  mov     [rsp+arg_10], rbx
0x1800181d1  push    rsi
0x1800181d2  push    rdi
0x1800181d3  push    r12
0x1800181d5  push    r14
0x1800181d7  push    r15
0x1800181d9  sub     rsp, 80h
0x1800181e0  mov     rax, cs:__security_cookie
0x1800181e7  xor     rax, rsp
0x1800181ea  mov     [rsp+0A8h+var_30], rax
0x1800181ef  mov     r12, rdx
0x1800181f2  mov     rsi, rcx
0x1800181f5  mov     qword ptr [rdx], 0
0x1800181fc  xorps   xmm0, xmm0
0x1800181ff  movups  xmmword ptr [rsp+0A8h+string], xmm0
0x180018204  xorps   xmm1, xmm1
0x180018207  movdqu  [rsp+0A8h+var_60], xmm1
0x18001820d  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180018211  mov     rbx, rdi
0x180018214  inc     rbx
0x180018217  cmp     byte ptr [rcx+rbx], 0
0x18001821b  jnz     short loc_180018214
0x18001821d  mov     r8, 7FFFFFFFFFFFFFFFh
0x180018227  cmp     rbx, r8
0x18001822a  ja      loc_180018410
0x180018230  cmp     rbx, 0Fh
0x180018234  jbe     loc_1800183C7
0x18001823a  mov     edx, 0Fh
0x18001823f  mov     rcx, rbx
0x180018242  call    ?_Calculate_growth@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@CA_K_K00@Z; std::string::_Calculate_growth(unsigned __int64,unsigned __int64,unsigned __int64)
0x180018247  mov     r15, rax
0x18001824a  lea     rdx, [rax+1]
0x18001824e  lea     rcx, [rsp+0A8h+string]
0x180018253  call    ?allocate@?$allocator@D@std@@QEAAPEAD_K@Z; std::allocator<char>::allocate(unsigned __int64)
0x180018258  mov     r14, rax
0x18001825b  mov     [rsp+0A8h+string], rax
0x180018260  mov     qword ptr [rsp+0A8h+var_60], rbx
0x180018265  mov     qword ptr [rsp+0A8h+var_60+8], r15
0x18001826a  mov     r8, rbx; Size
0x18001826d  mov     rdx, rsi; Src
0x180018270  mov     rcx, rax; void *
0x180018273  call    memcpy_0
0x180018278  mov     byte ptr [rbx+r14], 0
0x18001827d  mov     ecx, cs:_tls_index
0x180018283  mov     rax, gs:58h
0x18001828c  mov     rdx, [rax+rcx*8]
0x180018290  mov     r8d, 8Ch
0x180018296  mov     eax, [r8+rdx]
0x18001829a  mov     ebx, 90h
0x18001829f  add     rbx, rdx
0x1800182a2  test    al, 1
0x1800182a4  jz      loc_1800183EF
0x1800182aa  lea     r8, [rsp+0A8h+string]
0x1800182af  cmp     qword ptr [rsp+0A8h+var_60+8], 0Fh
0x1800182b5  cmova   r8, [rsp+0A8h+string]
0x1800182bb  inc     rdi
0x1800182be  cmp     byte ptr [r8+rdi], 0
0x1800182c3  jnz     short loc_1800182BB
0x1800182c5  lea     r9, [rdi+r8]
0x1800182c9  lea     rdx, [rsp+0A8h+sourceString]
0x1800182ce  mov     rcx, rbx
0x1800182d1  call    ?from_bytes@?$wstring_convert@V?$codecvt_utf8_utf16@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@PEBD0@Z; std::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::from_bytes(char const *,char const *)
0x1800182d6  nop
0x1800182d7  mov     rdx, qword ptr [rsp+0A8h+var_60+8]
0x1800182dc  cmp     rdx, 0Fh
0x1800182e0  jbe     short loc_180018306
0x1800182e2  inc     rdx; struct std::nothrow_t *
0x1800182e5  mov     [rsp+0A8h+var_80], rdx
0x1800182ea  mov     rcx, [rsp+0A8h+string]; void *
0x1800182ef  mov     [rsp+0A8h+var_78], rcx
0x1800182f4  cmp     rdx, 1000h
0x1800182fb  jnb     loc_18001841D
0x180018301  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180018306  mov     qword ptr [rsp+0A8h+var_88], 0; int
0x18001830f  lea     rax, [rsp+0A8h+var_88]
0x180018314  mov     [rsp+0A8h+string], rax
0x180018319  mov     [rsp+0A8h+string+8], 0
0x180018322  mov     byte ptr [rsp+0A8h+var_60], 1
0x180018327  lea     rcx, [rsp+0A8h+sourceString]
0x18001832c  cmp     [rsp+0A8h+var_38], 7
0x180018332  cmova   rcx, [rsp+0A8h+sourceString]; sourceString
0x180018338  lea     r8, [rsp+0A8h+string+8]; string
0x18001833d  mov     edx, [rsp+0A8h+length]; length
0x180018341  call    cs:__imp_WindowsCreateString
0x180018347  mov     ebx, eax
0x180018349  cmp     byte ptr [rsp+0A8h+var_60], 0
0x18001834e  jz      short loc_180018369
0x180018350  mov     r14, [rsp+0A8h+string+8]
0x180018355  mov     rdi, [rsp+0A8h+string]
0x18001835a  mov     rsi, [rdi]
0x18001835d  test    rsi, rsi
0x180018360  jnz     loc_18001843B
0x180018366  mov     [rdi], r14
0x180018369  test    ebx, ebx
0x18001836b  js      loc_18001845D
0x180018371  mov     rax, qword ptr [rsp+0A8h+var_88]
0x180018376  mov     qword ptr [rsp+0A8h+var_88], 0
0x18001837f  mov     [r12], rax
0x180018383  mov     rdx, [rsp+0A8h+var_38]
0x180018388  cmp     rdx, 7
0x18001838c  jbe     short loc_1800183A0
0x18001838e  lea     rdx, ds:2[rdx*2]
0x180018396  mov     rcx, [rsp+0A8h+sourceString]
0x18001839b  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800183a0  xor     eax, eax
0x1800183a2  mov     rcx, [rsp+0A8h+var_30]
0x1800183a7  xor     rcx, rsp; StackCookie
0x1800183aa  call    __security_check_cookie
0x1800183af  mov     rbx, [rsp+0A8h+arg_10]
0x1800183b7  add     rsp, 80h
0x1800183be  pop     r15
0x1800183c0  pop     r14
0x1800183c2  pop     r12
0x1800183c4  pop     rdi
0x1800183c5  pop     rsi
0x1800183c6  retn
0x1800183c7  mov     qword ptr [rsp+0A8h+var_60], rbx
0x1800183cc  mov     qword ptr [rsp+0A8h+var_60+8], 0Fh
0x1800183d5  mov     r8, rbx; Size
0x1800183d8  mov     rdx, rsi; Src
0x1800183db  lea     rcx, [rsp+0A8h+string]; void *
0x1800183e0  call    memcpy_0
0x1800183e5  mov     byte ptr [rsp+rbx+0A8h+string], 0
0x1800183ea  jmp     loc_18001827D
0x1800183ef  or      eax, 1
0x1800183f2  mov     [r8+rdx], eax
0x1800183f6  mov     rcx, rbx
0x1800183f9  call    ??0?$wstring_convert@V?$codecvt_utf8_utf16@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@QEAA@XZ; std::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>(void)
0x1800183fe  lea     rcx, _Utf8StringToWideString____2____dynamic_atexit_destructor_for__converter_utf8_utf16__
0x180018405  call    __tlregdtor
0x18001840a  nop
0x18001840b  jmp     loc_1800182AA
0x180018410  lea     rcx, aStringTooLong; "string too long"
0x180018417  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18001841d  lea     rdx, [rsp+0A8h+var_80]; unsigned __int64 *
0x180018422  lea     rcx, [rsp+0A8h+var_78]; void **
0x180018427  call    ?_Adjust_manually_vector_aligned@std@@YAXAEAPEAXAEA_K@Z; std::_Adjust_manually_vector_aligned(void * &,unsigned __int64 &)
0x18001842c  mov     rcx, [rsp+0A8h+var_78]
0x180018431  mov     rdx, [rsp+0A8h+var_80]
0x180018436  jmp     loc_180018301
0x18001843b  lea     rcx, [rsp+0A8h+var_80]; this
0x180018440  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180018445  mov     rcx, rsi; string
0x180018448  call    cs:__imp_WindowsDeleteString
0x18001844e  lea     rcx, [rsp+0A8h+var_80]; this
0x180018453  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180018458  jmp     loc_180018366
0x18001845d  mov     rcx, [rsp+0A8h]; this
0x180018465  mov     r9d, ebx; char *
0x180018468  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\cloudstore\\common\\"...
0x18001846f  mov     edx, 0ABh; void *
0x180018474  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018479  lea     rcx, [rsp+0A8h+var_88]
0x18001847e  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(void)
0x180018483  lea     rcx, [rsp+0A8h+sourceString]
0x180018488  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001848d  mov     eax, ebx
0x18001848f  jmp     loc_1800183A2
0x180018494  mov     eax, [rsp+0A8h+var_88]
0x180018498  jmp     loc_1800183A2
```
