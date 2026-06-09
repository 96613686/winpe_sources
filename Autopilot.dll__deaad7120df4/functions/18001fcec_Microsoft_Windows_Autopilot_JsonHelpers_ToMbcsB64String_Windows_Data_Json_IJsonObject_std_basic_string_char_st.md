# Microsoft::Windows::Autopilot::JsonHelpers::ToMbcsB64String(Windows::Data::Json::IJsonObject *,std::basic_string<char,std::char_traits<char>,std::allocator<char>> &)

- ea: `0x18001fcec`
- end: `0x18001ff14`
- name: `?ToMbcsB64String@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z`
- size: `552`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180024878`

## callees

- `0x180004a08`
- `0x1800097cc`
- `0x1800098e7`
- `0x180010764`
- `0x180014058`
- `0x18001f508`
- `0x18001f6c4`
- `0x18001fb88`
- `0x18001fcec`
- `0x18001ff1c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001fd65`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001fd65`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001fd3d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001fe2f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001fef2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001fd3d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001fe2f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001fef2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001fdb9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001fe19`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001fedc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001fdb9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001fe19`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001fedc`
- `DMCmnUtils!UnicodeToMB` at `0x18001fd81`
- `DMCmnUtils!UnicodeToMB` at `0x18001fd81`

## string_xrefs

- `0x18001fd22`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\jsonhelpers.cpp`
- `0x18001fd9a`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\jsonhelpers.cpp`
- `0x18001fdfe`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\jsonhelpers.cpp`
- `0x18001fe65`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\jsonhelpers.cpp`

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
  HSTRING string; // [rsp+30h] [rbp-20h] BYREF
  HLOCAL hMem[3]; // [rsp+38h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  int v18; // [rsp+80h] [rbp+30h] BYREF
  int RequiredLength; // [rsp+88h] [rbp+38h] BYREF

  string = 0;
  v3 = Microsoft::Windows::Autopilot::JsonHelpers::ToString(a1, &string);
  v4 = v3;
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB7,
      (int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\jsonhelpers.cpp",
      (const char *)(unsigned int)v3);
LABEL_3:
    if ( string )
      WindowsDeleteString(string);
    return v4;
  }
  v18 = 0;
  hMem[0] = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  v7 = UnicodeToMB(StringRawBuffer, 0xFDE9u, (char **)hMem, (unsigned int *)&v18);
  v4 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBF,
      (int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\jsonhelpers.cpp",
      (const char *)(unsigned int)v7);
    if ( hMem[0] )
      LocalFree(hMem[0]);
    goto LABEL_3;
  }
  RequiredLength = ATL::Base64EncodeGetRequiredLength(v18, 0);
  v8 = operator new[](RequiredLength, (const struct std::nothrow_t *)&std::nothrow);
  v9 = v8;
  hMem[1] = v8;
  if ( !v8 )
  {
    v10 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC3,
      (int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\jsonhelpers.cpp",
      (const char *)0x8007000ELL);
LABEL_11:
    if ( hMem[0] )
      LocalFree(hMem[0]);
    if ( string )
      WindowsDeleteString(string);
    return v10;
  }
  if ( !ATL::Base64Encode((const unsigned __int8 *)hMem[0], v18, (char *)v8, &RequiredLength, v14) )
  {
    v10 = -2147467259;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCB,
      (int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\jsonhelpers.cpp",
      (const char *)0x80004005LL);
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
  Microsoft::Windows::Autopilot::JsonHelpers::RemoveTrailingNulls((const void **)a2);
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
0x18001fcec  mov     [rsp-18h+arg_0], rbx
0x18001fcf1  mov     [rsp-18h+arg_8], rsi
0x18001fcf6  push    rbp
0x18001fcf7  push    rdi
0x18001fcf8  push    r14
0x18001fcfa  mov     rbp, rsp
0x18001fcfd  sub     rsp, 50h
0x18001fd01  mov     rbx, rdx
0x18001fd04  mov     [rbp+string], 0
0x18001fd0c  lea     rdx, [rbp+string]
0x18001fd10  call    ?ToString@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; Microsoft::Windows::Autopilot::JsonHelpers::ToString(Windows::Data::Json::IJsonObject *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> &)
0x18001fd15  mov     edi, eax
0x18001fd17  test    eax, eax
0x18001fd19  jns     short loc_18001FD50
0x18001fd1b  mov     rcx, [rbp+18h]; this
0x18001fd1f  mov     r9d, eax; char *
0x18001fd22  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001fd29  mov     edx, 0B7h; void *
0x18001fd2e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fd33  nop
0x18001fd34  mov     rcx, [rbp+string]; string
0x18001fd38  test    rcx, rcx
0x18001fd3b  jz      short loc_18001FD49
0x18001fd3d  call    cs:__imp_WindowsDeleteString
0x18001fd44  nop     dword ptr [rax+rax+00h]
0x18001fd49  mov     eax, edi
0x18001fd4b  jmp     loc_18001FF00
0x18001fd50  mov     [rbp+arg_10], 0
0x18001fd57  mov     [rbp+hMem], 0
0x18001fd5f  xor     edx, edx; length
0x18001fd61  mov     rcx, [rbp+string]; string
0x18001fd65  call    cs:__imp_WindowsGetStringRawBuffer
0x18001fd6c  nop     dword ptr [rax+rax+00h]
0x18001fd71  lea     r9, [rbp+arg_10]
0x18001fd75  lea     r8, [rbp+hMem]
0x18001fd79  mov     edx, 0FDE9h
0x18001fd7e  mov     rcx, rax
0x18001fd81  call    cs:__imp_?UnicodeToMB@@YAJPEBGIPEAPEADPEAK@Z; UnicodeToMB(ushort const *,uint,char * *,ulong *)
0x18001fd88  nop     dword ptr [rax+rax+00h]
0x18001fd8d  mov     edi, eax
0x18001fd8f  test    eax, eax
0x18001fd91  jns     short loc_18001FDCA
0x18001fd93  mov     rcx, [rbp+18h]; this
0x18001fd97  mov     r9d, eax; char *
0x18001fd9a  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001fda1  mov     edx, 0BFh; void *
0x18001fda6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fdab  nop
0x18001fdac  mov     rcx, [rbp+hMem]; hMem
0x18001fdb0  test    rcx, rcx
0x18001fdb3  jz      loc_18001FD34
0x18001fdb9  call    cs:__imp_LocalFree
0x18001fdc0  nop     dword ptr [rax+rax+00h]
0x18001fdc5  jmp     loc_18001FD34
0x18001fdca  xor     edx, edx; unsigned int
0x18001fdcc  mov     ecx, [rbp+arg_10]; int
0x18001fdcf  call    ?Base64EncodeGetRequiredLength@ATL@@YAHHK@Z; ATL::Base64EncodeGetRequiredLength(int,ulong)
0x18001fdd4  mov     [rbp+arg_18], eax
0x18001fdd7  movsxd  rcx, eax; unsigned __int64
0x18001fdda  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001fde1  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001fde6  mov     rdi, rax
0x18001fde9  mov     [rbp+var_10], rax
0x18001fded  test    rax, rax
0x18001fdf0  jnz     short loc_18001FE42
0x18001fdf2  mov     rcx, [rbp+18h]; this
0x18001fdf6  mov     ebx, 8007000Eh
0x18001fdfb  mov     r9d, ebx; char *
0x18001fdfe  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001fe05  mov     edx, 0C3h; void *
0x18001fe0a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fe0f  nop
0x18001fe10  mov     rcx, [rbp+hMem]; hMem
0x18001fe14  test    rcx, rcx
0x18001fe17  jz      short loc_18001FE26
0x18001fe19  call    cs:__imp_LocalFree
0x18001fe20  nop     dword ptr [rax+rax+00h]
0x18001fe25  nop
0x18001fe26  mov     rcx, [rbp+string]; string
0x18001fe2a  test    rcx, rcx
0x18001fe2d  jz      short loc_18001FE3B
0x18001fe2f  call    cs:__imp_WindowsDeleteString
0x18001fe36  nop     dword ptr [rax+rax+00h]
0x18001fe3b  mov     eax, ebx
0x18001fe3d  jmp     loc_18001FF00
0x18001fe42  lea     r9, [rbp+arg_18]; int *
0x18001fe46  mov     r8, rdi; char *
0x18001fe49  mov     edx, [rbp+arg_10]; int
0x18001fe4c  mov     rcx, [rbp+hMem]; unsigned __int8 *
0x18001fe50  call    ?Base64Encode@ATL@@YAHPEBEHPEADPEAHK@Z; ATL::Base64Encode(uchar const *,int,char *,int *,ulong)
0x18001fe55  test    eax, eax
0x18001fe57  jnz     short loc_18001FE81
0x18001fe59  mov     rcx, [rbp+18h]; this
0x18001fe5d  mov     ebx, 80004005h
0x18001fe62  mov     r9d, ebx; char *
0x18001fe65  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001fe6c  mov     edx, 0CBh; void *
0x18001fe71  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fe76  nop
0x18001fe77  mov     rcx, rdi; void *
0x18001fe7a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001fe7f  jmp     short loc_18001FE10
0x18001fe81  movsxd  rsi, [rbp+arg_18]
0x18001fe85  cmp     rsi, [rbx+18h]
0x18001fe89  ja      short loc_18001FEB3
0x18001fe8b  cmp     qword ptr [rbx+18h], 0Fh
0x18001fe90  jbe     short loc_18001FE97
0x18001fe92  mov     r14, [rbx]
0x18001fe95  jmp     short loc_18001FE9A
0x18001fe97  mov     r14, rbx
0x18001fe9a  mov     [rbx+10h], rsi
0x18001fe9e  mov     r8, rsi; Size
0x18001fea1  mov     rdx, rdi; Src
0x18001fea4  mov     rcx, r14; void *
0x18001fea7  call    memmove_0
0x18001feac  mov     byte ptr [rsi+r14], 0
0x18001feb1  jmp     short loc_18001FEC1
0x18001feb3  mov     r9, rdi
0x18001feb6  mov     rdx, rsi
0x18001feb9  mov     rcx, rbx
0x18001febc  call    ??$_Reallocate_for@V_lambda_a132b9f505f015b07a26cb4edca31da2_@@PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_a132b9f505f015b07a26cb4edca31da2_@@PEBD@Z; std::string::_Reallocate_for<_lambda_a132b9f505f015b07a26cb4edca31da2_,char const *>(unsigned __int64,_lambda_a132b9f505f015b07a26cb4edca31da2_,char const *)
0x18001fec1  mov     rcx, rbx
0x18001fec4  call    ?RemoveTrailingNulls@JsonHelpers@Autopilot@Windows@Microsoft@@SAXAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Microsoft::Windows::Autopilot::JsonHelpers::RemoveTrailingNulls(std::string &)
0x18001fec9  nop
0x18001feca  mov     rcx, rdi; void *
0x18001fecd  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001fed2  nop
0x18001fed3  mov     rcx, [rbp+hMem]; hMem
0x18001fed7  test    rcx, rcx
0x18001feda  jz      short loc_18001FEE9
0x18001fedc  call    cs:__imp_LocalFree
0x18001fee3  nop     dword ptr [rax+rax+00h]
0x18001fee8  nop
0x18001fee9  mov     rcx, [rbp+string]; string
0x18001feed  test    rcx, rcx
0x18001fef0  jz      short loc_18001FEFE
0x18001fef2  call    cs:__imp_WindowsDeleteString
0x18001fef9  nop     dword ptr [rax+rax+00h]
0x18001fefe  xor     eax, eax
0x18001ff00  mov     rbx, [rsp+50h+arg_0]
0x18001ff05  mov     rsi, [rsp+50h+arg_8]
0x18001ff0a  add     rsp, 50h
0x18001ff0e  pop     r14
0x18001ff10  pop     rdi
0x18001ff11  pop     rbp
0x18001ff12  retn
```
