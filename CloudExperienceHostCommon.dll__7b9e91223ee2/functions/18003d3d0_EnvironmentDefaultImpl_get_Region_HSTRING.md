# EnvironmentDefaultImpl::get_Region(HSTRING__ * *)

- ea: `0x18003d3d0`
- end: `0x18003d49f`
- name: `?get_Region@EnvironmentDefaultImpl@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `207`
- prototype: `int(EnvironmentDefaultImpl *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180015310`
- `0x1800153f8`
- `0x18001a540`
- `0x18003d3d0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003d457`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003d457`
- `api-ms-win-core-localization-l1-2-0!GetUserGeoID` at `0x18003d3f6`
- `api-ms-win-core-localization-l1-2-0!GetUserGeoID` at `0x18003d3f6`
- `api-ms-win-core-localization-l1-2-0!GetGeoInfoW` at `0x18003d41f`
- `api-ms-win-core-localization-l1-2-0!GetGeoInfoW` at `0x18003d41f`

## string_xrefs

- `0x18003d42e`: `onecoreuap\shell\cloudexperiencehost\onecore\comapi\environment.cpp`
- `0x18003d468`: `onecoreuap\shell\cloudexperiencehost\onecore\comapi\environment.cpp`

## pseudocode

```c
__int64 __fastcall EnvironmentDefaultImpl::get_Region(EnvironmentDefaultImpl *this, HSTRING *a2)
{
  __int64 v3; // rbx
  GEOID UserGeoID; // ecx
  const char *v5; // r9
  HRESULT String; // eax
  unsigned int v8; // ebx
  int LangId; // [rsp+20h] [rbp-28h]
  WCHAR GeoData[4]; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v3 = -1;
  UserGeoID = GetUserGeoID(0x10u);
  if ( UserGeoID == -1 )
    UserGeoID = 244;
  if ( !GetGeoInfoW(UserGeoID, 4u, GeoData, 3, 0) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x2A,
             (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\comapi\\environment.cpp",
             v5);
  do
    ++v3;
  while ( GeoData[v3] );
  String = WindowsCreateString(GeoData, v3, a2);
  v8 = String;
  if ( String >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x2B,
    (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\comapi\\environment.cpp",
    (const char *)(unsigned int)String,
    LangId);
  return v8;
}

```

## disassembly

```asm
0x18003d3d0  mov     [rsp+arg_0], rbx
0x18003d3d5  mov     [rsp+arg_10], rsi
0x18003d3da  push    rdi
0x18003d3db  sub     rsp, 40h
0x18003d3df  mov     rax, cs:__security_cookie
0x18003d3e6  xor     rax, rsp
0x18003d3e9  mov     [rsp+48h+var_10], rax
0x18003d3ee  mov     ecx, 10h; GeoClass
0x18003d3f3  mov     rdi, rdx
0x18003d3f6  call    cs:__imp_GetUserGeoID
0x18003d3fc  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18003d400  lea     r8, [rsp+48h+GeoData]; lpGeoData
0x18003d405  mov     ecx, eax
0x18003d407  mov     eax, 0F4h
0x18003d40c  cmp     ecx, ebx
0x18003d40e  cmovz   ecx, eax; Location
0x18003d411  lea     r9d, [rbx+4]; cchData
0x18003d415  xor     esi, esi
0x18003d417  lea     edx, [rbx+5]; GeoType
0x18003d41a  mov     word ptr [rsp+48h+LangId], si; int
0x18003d41f  call    cs:__imp_GetGeoInfoW
0x18003d425  test    eax, eax
0x18003d427  jnz     short loc_18003D43F
0x18003d429  mov     rcx, [rsp+48h]; this
0x18003d42e  lea     r8, aOnecoreuapShel_5; "onecoreuap\\shell\\cloudexperiencehost"...
0x18003d435  lea     edx, [rbx+2Bh]; void *
0x18003d438  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003d43d  jmp     short loc_18003D482
0x18003d43f  lea     rax, [rsp+48h+GeoData]
0x18003d444  inc     rbx
0x18003d447  cmp     [rax+rbx*2], si
0x18003d44b  jnz     short loc_18003D444
0x18003d44d  mov     edx, ebx; length
0x18003d44f  lea     rcx, [rsp+48h+GeoData]; sourceString
0x18003d454  mov     r8, rdi; string
0x18003d457  call    cs:__imp_WindowsCreateString
0x18003d45d  mov     ebx, eax
0x18003d45f  test    eax, eax
0x18003d461  jns     short loc_18003D480
0x18003d463  mov     rcx, [rsp+48h]; this
0x18003d468  lea     r8, aOnecoreuapShel_5; "onecoreuap\\shell\\cloudexperiencehost"...
0x18003d46f  mov     r9d, eax; char *
0x18003d472  mov     edx, 2Bh ; '+'; void *
0x18003d477  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d47c  mov     eax, ebx
0x18003d47e  jmp     short loc_18003D482
0x18003d480  xor     eax, eax
0x18003d482  mov     rcx, [rsp+48h+var_10]
0x18003d487  xor     rcx, rsp; StackCookie
0x18003d48a  call    __security_check_cookie
0x18003d48f  mov     rbx, [rsp+48h+arg_0]
0x18003d494  mov     rsi, [rsp+48h+arg_10]
0x18003d499  add     rsp, 40h
0x18003d49d  pop     rdi
0x18003d49e  retn
```
