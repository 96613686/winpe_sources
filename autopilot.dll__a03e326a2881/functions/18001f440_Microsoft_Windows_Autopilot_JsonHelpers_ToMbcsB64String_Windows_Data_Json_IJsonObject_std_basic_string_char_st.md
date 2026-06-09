# Microsoft::Windows::Autopilot::JsonHelpers::ToMbcsB64String(Windows::Data::Json::IJsonObject *,std::basic_string<char,std::char_traits<char>,std::allocator<char>> &)

- ea: `0x18001f440`
- end: `0x18001f630`
- name: `?ToMbcsB64String@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z`
- size: `496`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180023cb0`

## callees

- `0x1800049f4`
- `0x18000983c`
- `0x180009957`
- `0x1800105f4`
- `0x180013cac`
- `0x18001ec74`
- `0x18001ee30`
- `0x18001f2dc`
- `0x18001f440`
- `0x18001f638`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001f4b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001f4b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f491`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f55e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f615`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f491`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f55e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f615`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f4f7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f54e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f605`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f4f7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f54e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f605`
- `DMCmnUtils!UnicodeToMB` at `0x18001f4c9`
- `DMCmnUtils!UnicodeToMB` at `0x18001f4c9`

## string_xrefs

- `0x18001f476`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\jsonhelpers.cpp`
- `0x18001f4dc`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\jsonhelpers.cpp`
- `0x18001f533`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\jsonhelpers.cpp`
- `0x18001f58e`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\jsonhelpers.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Microsoft::Windows::Autopilot::JsonHelpers::ToMbcsB64String(__int64 a1, void **a2)
{
  int v3; // eax
  unsigned int v4; // edi
  const unsigned __int16 *StringRawBuffer; // rax
  int v7; // eax
  void *v8; // rax
  void *v9; // rdi
  unsigned int v10; // ebx
  __int64 v11; // r8
  size_t v12; // rsi
  void *v13; // r14
  unsigned int v14; // [rsp+20h] [rbp-30h]
  int v15; // [rsp+20h] [rbp-30h]
  HSTRING string; // [rsp+30h] [rbp-20h] BYREF
  HLOCAL hMem[3]; // [rsp+38h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  int v19; // [rsp+80h] [rbp+30h] BYREF
  int RequiredLength; // [rsp+88h] [rbp+38h] BYREF

  string = 0;
  v3 = Microsoft::Windows::Autopilot::JsonHelpers::ToString(a1, &string);
  v4 = v3;
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB7,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\jsonhelpers.cpp",
      (const char *)(unsigned int)v3,
      v14);
LABEL_3:
    if ( string )
      WindowsDeleteString(string);
    return v4;
  }
  v19 = 0;
  hMem[0] = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  v7 = UnicodeToMB(StringRawBuffer, 0xFDE9u, (char **)hMem, (unsigned int *)&v19);
  v4 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBF,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\jsonhelpers.cpp",
      (const char *)(unsigned int)v7,
      v14);
    if ( hMem[0] )
      LocalFree(hMem[0]);
    goto LABEL_3;
  }
  RequiredLength = ATL::Base64EncodeGetRequiredLength(v19, 0);
  v8 = operator new[](RequiredLength, (const struct std::nothrow_t *)&std::nothrow);
  v9 = v8;
  hMem[1] = v8;
  if ( !v8 )
  {
    v10 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC3,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\jsonhelpers.cpp",
      (const char *)0x8007000ELL,
      v14);
LABEL_11:
    if ( hMem[0] )
      LocalFree(hMem[0]);
    if ( string )
      WindowsDeleteString(string);
    return v10;
  }
  if ( !ATL::Base64Encode((const unsigned __int8 *)hMem[0], v19, (char *)v8, &RequiredLength, v14) )
  {
    v10 = -2147467259;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCB,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\jsonhelpers.cpp",
      (const char *)0x80004005LL,
      v15);
    operator delete(v9);
    goto LABEL_11;
  }
  v12 = RequiredLength;
  if ( RequiredLength > (unsigned __int64)a2[3] )
  {
    std::string::_Reallocate_for<_lambda_a132b9f505f015b07a26cb4edca31da2_,char const *>(a2, RequiredLength, v11, v9);
  }
  else
  {
    if ( (unsigned __int64)a2[3] <= 0xF )
      v13 = a2;
    else
      v13 = *a2;
    a2[2] = (void *)RequiredLength;
    memmove_0(v13, v9, v12);
    *((_BYTE *)v13 + v12) = 0;
  }
  Microsoft::Windows::Autopilot::JsonHelpers::RemoveTrailingNulls(a2);
  operator delete(v9);
  if ( hMem[0] )
    LocalFree(hMem[0]);
  if ( string )
    WindowsDeleteString(string);
  return 0;
}

```

## disassembly

```asm
0x18001f440  mov     [rsp-18h+arg_0], rbx
0x18001f445  mov     [rsp-18h+arg_8], rsi
0x18001f44a  push    rbp
0x18001f44b  push    rdi
0x18001f44c  push    r14
0x18001f44e  mov     rbp, rsp
0x18001f451  sub     rsp, 50h
0x18001f455  mov     rbx, rdx
0x18001f458  mov     [rbp+string], 0
0x18001f460  lea     rdx, [rbp+string]
0x18001f464  call    ?ToString@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; Microsoft::Windows::Autopilot::JsonHelpers::ToString(Windows::Data::Json::IJsonObject *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> &)
0x18001f469  mov     edi, eax
0x18001f46b  test    eax, eax
0x18001f46d  jns     short loc_18001F49E
0x18001f46f  mov     rcx, [rbp+18h]; this
0x18001f473  mov     r9d, eax; char *
0x18001f476  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001f47d  mov     edx, 0B7h; void *
0x18001f482  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f487  nop
0x18001f488  mov     rcx, [rbp+string]; string
0x18001f48c  test    rcx, rcx
0x18001f48f  jz      short loc_18001F497
0x18001f491  call    cs:__imp_WindowsDeleteString
0x18001f497  mov     eax, edi
0x18001f499  jmp     loc_18001F61D
0x18001f49e  mov     [rbp+arg_10], 0
0x18001f4a5  mov     [rbp+hMem], 0
0x18001f4ad  xor     edx, edx; length
0x18001f4af  mov     rcx, [rbp+string]; string
0x18001f4b3  call    cs:__imp_WindowsGetStringRawBuffer
0x18001f4b9  lea     r9, [rbp+arg_10]
0x18001f4bd  lea     r8, [rbp+hMem]
0x18001f4c1  mov     edx, 0FDE9h
0x18001f4c6  mov     rcx, rax
0x18001f4c9  call    cs:__imp_?UnicodeToMB@@YAJPEBGIPEAPEADPEAK@Z; UnicodeToMB(ushort const *,uint,char * *,ulong *)
0x18001f4cf  mov     edi, eax
0x18001f4d1  test    eax, eax
0x18001f4d3  jns     short loc_18001F4FF
0x18001f4d5  mov     rcx, [rbp+18h]; this
0x18001f4d9  mov     r9d, eax; char *
0x18001f4dc  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001f4e3  mov     edx, 0BFh; void *
0x18001f4e8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f4ed  nop
0x18001f4ee  mov     rcx, [rbp+hMem]; hMem
0x18001f4f2  test    rcx, rcx
0x18001f4f5  jz      short loc_18001F488
0x18001f4f7  call    cs:__imp_LocalFree
0x18001f4fd  jmp     short loc_18001F488
0x18001f4ff  xor     edx, edx; unsigned int
0x18001f501  mov     ecx, [rbp+arg_10]; int
0x18001f504  call    ?Base64EncodeGetRequiredLength@ATL@@YAHHK@Z; ATL::Base64EncodeGetRequiredLength(int,ulong)
0x18001f509  mov     [rbp+arg_18], eax
0x18001f50c  movsxd  rcx, eax; unsigned __int64
0x18001f50f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001f516  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001f51b  mov     rdi, rax
0x18001f51e  mov     [rbp+var_10], rax
0x18001f522  test    rax, rax
0x18001f525  jnz     short loc_18001F56B
0x18001f527  mov     rcx, [rbp+18h]; this
0x18001f52b  mov     ebx, 8007000Eh
0x18001f530  mov     r9d, ebx; char *
0x18001f533  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001f53a  mov     edx, 0C3h; void *
0x18001f53f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f544  nop
0x18001f545  mov     rcx, [rbp+hMem]; hMem
0x18001f549  test    rcx, rcx
0x18001f54c  jz      short loc_18001F555
0x18001f54e  call    cs:__imp_LocalFree
0x18001f554  nop
0x18001f555  mov     rcx, [rbp+string]; string
0x18001f559  test    rcx, rcx
0x18001f55c  jz      short loc_18001F564
0x18001f55e  call    cs:__imp_WindowsDeleteString
0x18001f564  mov     eax, ebx
0x18001f566  jmp     loc_18001F61D
0x18001f56b  lea     r9, [rbp+arg_18]; int *
0x18001f56f  mov     r8, rdi; char *
0x18001f572  mov     edx, [rbp+arg_10]; int
0x18001f575  mov     rcx, [rbp+hMem]; unsigned __int8 *
0x18001f579  call    ?Base64Encode@ATL@@YAHPEBEHPEADPEAHK@Z; ATL::Base64Encode(uchar const *,int,char *,int *,ulong)
0x18001f57e  test    eax, eax
0x18001f580  jnz     short loc_18001F5AA
0x18001f582  mov     rcx, [rbp+18h]; this
0x18001f586  mov     ebx, 80004005h
0x18001f58b  mov     r9d, ebx; char *
0x18001f58e  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001f595  mov     edx, 0CBh; void *
0x18001f59a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f59f  nop
0x18001f5a0  mov     rcx, rdi; Block
0x18001f5a3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001f5a8  jmp     short loc_18001F545
0x18001f5aa  movsxd  rsi, [rbp+arg_18]
0x18001f5ae  cmp     rsi, [rbx+18h]
0x18001f5b2  ja      short loc_18001F5DC
0x18001f5b4  cmp     qword ptr [rbx+18h], 0Fh
0x18001f5b9  jbe     short loc_18001F5C0
0x18001f5bb  mov     r14, [rbx]
0x18001f5be  jmp     short loc_18001F5C3
0x18001f5c0  mov     r14, rbx
0x18001f5c3  mov     [rbx+10h], rsi
0x18001f5c7  mov     r8, rsi; Size
0x18001f5ca  mov     rdx, rdi; Src
0x18001f5cd  mov     rcx, r14; void *
0x18001f5d0  call    memmove_0
0x18001f5d5  mov     byte ptr [rsi+r14], 0
0x18001f5da  jmp     short loc_18001F5EA
0x18001f5dc  mov     r9, rdi
0x18001f5df  mov     rdx, rsi
0x18001f5e2  mov     rcx, rbx
0x18001f5e5  call    ??$_Reallocate_for@V_lambda_a132b9f505f015b07a26cb4edca31da2_@@PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_a132b9f505f015b07a26cb4edca31da2_@@PEBD@Z; std::string::_Reallocate_for<_lambda_a132b9f505f015b07a26cb4edca31da2_,char const *>(unsigned __int64,_lambda_a132b9f505f015b07a26cb4edca31da2_,char const *)
0x18001f5ea  mov     rcx, rbx
0x18001f5ed  call    ?RemoveTrailingNulls@JsonHelpers@Autopilot@Windows@Microsoft@@SAXAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Microsoft::Windows::Autopilot::JsonHelpers::RemoveTrailingNulls(std::string &)
0x18001f5f2  nop
0x18001f5f3  mov     rcx, rdi; Block
0x18001f5f6  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001f5fb  nop
0x18001f5fc  mov     rcx, [rbp+hMem]; hMem
0x18001f600  test    rcx, rcx
0x18001f603  jz      short loc_18001F60C
0x18001f605  call    cs:__imp_LocalFree
0x18001f60b  nop
0x18001f60c  mov     rcx, [rbp+string]; string
0x18001f610  test    rcx, rcx
0x18001f613  jz      short loc_18001F61B
0x18001f615  call    cs:__imp_WindowsDeleteString
0x18001f61b  xor     eax, eax
0x18001f61d  mov     rbx, [rsp+50h+arg_0]
0x18001f622  mov     rsi, [rsp+50h+arg_8]
0x18001f627  add     rsp, 50h
0x18001f62b  pop     r14
0x18001f62d  pop     rdi
0x18001f62e  pop     rbp
0x18001f62f  retn
```
