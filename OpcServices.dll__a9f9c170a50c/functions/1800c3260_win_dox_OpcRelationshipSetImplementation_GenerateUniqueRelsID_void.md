# win_dox::OpcRelationshipSetImplementation::GenerateUniqueRelsID(void)

- ea: `0x1800c3260`
- end: `0x1800c33d7`
- name: `?GenerateUniqueRelsID@OpcRelationshipSetImplementation@win_dox@@AEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@XZ`
- size: `375`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800f53cc`

## callees

- `0x180015a68`
- `0x18001c900`
- `0x1800517a0`
- `0x18007809c`
- `0x18009703c`
- `0x1800c3260`
- `0x1800cd38c`
- `0x1800d5fe4`
- `0x1800f6318`
- `0x180117740`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800c32fa`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800c32fa`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800c32df`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800c32df`

## string_xrefs

- `0x1800c337d`: `Call to ::CoCreateGuid failed with HResult 0x%X.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall win_dox::OpcRelationshipSetImplementation::GenerateUniqueRelsID(
        win_dox::OpcRelationshipSetImplementation *this,
        __int64 a2)
{
  HRESULT v4; // edi
  const wchar_t *v5; // rdx
  GUID pguid_8; // [rsp+60h] [rbp-A8h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+78h] [rbp-90h] BYREF
  OLECHAR sz; // [rsp+118h] [rbp+10h] BYREF
  _BYTE v10[126]; // [rsp+11Ah] [rbp+12h] BYREF
  wchar_t v11[512]; // [rsp+198h] [rbp+90h] BYREF

  win_dox::OpcRelationshipSetImplementation::Initialize(this, 0);
  *(_QWORD *)(a2 + 32) = 7;
  *(_QWORD *)(a2 + 24) = 0;
  *(_WORD *)(a2 + 8) = 0;
  pguid_8 = 0;
  do
  {
    v4 = CoCreateGuid(&pguid_8);
    if ( v4 < 0 )
    {
      memset_0(v11, 0, sizeof(v11));
      StringCchPrintfW(v11, 0x200u, L"Call to ::CoCreateGuid failed with HResult 0x%X.", (unsigned int)v4);
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x119u,
        v4,
        (struct win_musl::TStringEllipseBase *)v11);
      throw (SplException::THResultException *)pExceptionObject;
    }
    StringFromGUID2(&pguid_8, &sz, 64);
    std::wstring::assign(a2, L"R");
    std::wstring::append(a2, v10, 8);
    if ( *(_QWORD *)(a2 + 32) < 8u )
      v5 = (const wchar_t *)(a2 + 8);
    else
      v5 = *(const wchar_t **)(a2 + 8);
  }
  while ( win_dox::OpcRelationshipSetImplementation::RelationshipExists(this, v5) );
  return a2;
}

```

## disassembly

```asm
0x1800c3260  mov     rax, rsp
0x1800c3263  push    rbp
0x1800c3264  push    rdi
0x1800c3265  push    r14
0x1800c3267  lea     rbp, [rax-4B8h]
0x1800c326e  sub     rsp, 5A0h
0x1800c3275  mov     [rsp+5B0h+var_568], 0FFFFFFFFFFFFFFFEh
0x1800c327e  mov     [rax+18h], rbx
0x1800c3282  mov     [rax+20h], rsi
0x1800c3286  mov     rax, cs:__security_cookie
0x1800c328d  xor     rax, rsp
0x1800c3290  mov     [rbp+4B0h+var_20], rax
0x1800c3297  mov     rbx, rdx
0x1800c329a  mov     r14, rcx
0x1800c329d  mov     qword ptr [rsp+5B0h+pguid.Data1], rdx
0x1800c32a2  mov     dword ptr [rsp+5B0h+var_570], 0
0x1800c32aa  xor     edx, edx; bool
0x1800c32ac  call    ?Initialize@OpcRelationshipSetImplementation@win_dox@@AEAAX_N@Z; win_dox::OpcRelationshipSetImplementation::Initialize(bool)
0x1800c32b1  mov     qword ptr [rbx+20h], 7
0x1800c32b9  lea     rsi, [rbx+8]
0x1800c32bd  mov     qword ptr [rbx+18h], 0
0x1800c32c5  xor     eax, eax
0x1800c32c7  mov     [rsi], ax
0x1800c32ca  mov     dword ptr [rsp+5B0h+var_570], 1
0x1800c32d2  xorps   xmm0, xmm0
0x1800c32d5  movups  xmmword ptr [rsp+5B0h+pguid.Data4], xmm0
0x1800c32da  lea     rcx, [rsp+5B0h+pguid.Data4]; pguid
0x1800c32df  call    cs:__imp_CoCreateGuid
0x1800c32e5  mov     edi, eax
0x1800c32e7  test    eax, eax
0x1800c32e9  js      short loc_1800C3366
0x1800c32eb  mov     r8d, 40h ; '@'; cchMax
0x1800c32f1  lea     rdx, [rbp+4B0h+sz]; lpsz
0x1800c32f5  lea     rcx, [rsp+5B0h+pguid.Data4]; rguid
0x1800c32fa  call    cs:__imp_StringFromGUID2
0x1800c3300  lea     rdx, aR; "R"
0x1800c3307  mov     rcx, rbx
0x1800c330a  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAAAEAV12@PEB_W@Z; std::wstring::assign(wchar_t const *)
0x1800c330f  mov     r8d, 8
0x1800c3315  lea     rdx, [rbp+4B0h+var_49E]
0x1800c3319  mov     rcx, rbx
0x1800c331c  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAAAEAV12@PEB_W_K@Z; std::wstring::append(wchar_t const *,unsigned __int64)
0x1800c3321  cmp     qword ptr [rbx+20h], 8
0x1800c3326  jb      short loc_1800C332D
0x1800c3328  mov     rdx, [rsi]
0x1800c332b  jmp     short loc_1800C3330
0x1800c332d  mov     rdx, rsi; wchar_t *
0x1800c3330  mov     rcx, r14; this
0x1800c3333  call    ?RelationshipExists@OpcRelationshipSetImplementation@win_dox@@QEAA_NPEB_W@Z; win_dox::OpcRelationshipSetImplementation::RelationshipExists(wchar_t const *)
0x1800c3338  test    al, al
0x1800c333a  jnz     short loc_1800C32DA
0x1800c333c  mov     rax, rbx
0x1800c333f  mov     rcx, [rbp+4B0h+var_20]
0x1800c3346  xor     rcx, rsp; StackCookie
0x1800c3349  call    __security_check_cookie
0x1800c334e  lea     r11, [rsp+5B0h+var_10]
0x1800c3356  mov     rbx, [r11+30h]
0x1800c335a  mov     rsi, [r11+38h]
0x1800c335e  mov     rsp, r11
0x1800c3361  pop     r14
0x1800c3363  pop     rdi
0x1800c3364  pop     rbp
0x1800c3365  retn
0x1800c3366  xor     edx, edx; Val
0x1800c3368  mov     r8d, 400h; Size
0x1800c336e  lea     rcx, [rbp+4B0h+var_420]; void *
0x1800c3375  call    memset_0
0x1800c337a  mov     r9d, edi
0x1800c337d  lea     r8, aCallToCocreate_1; "Call to ::CoCreateGuid failed with HRes"...
0x1800c3384  mov     edx, 200h; unsigned __int64
0x1800c3389  lea     rcx, [rbp+4B0h+var_420]; wchar_t *
0x1800c3390  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800c3395  lea     rax, [rbp+4B0h+var_420]
0x1800c339c  mov     [rsp+5B0h+var_580], rax; struct win_musl::TStringEllipseBase *
0x1800c33a1  mov     [rsp+5B0h+var_588], edi; unsigned int
0x1800c33a5  mov     [rsp+5B0h+var_590], 119h; unsigned int
0x1800c33ad  lea     r9, word_18013A0B6
0x1800c33b4  lea     r8, aNoFilename; "(no filename)"
0x1800c33bb  lea     rcx, [rsp+5B0h+pExceptionObject]; this
0x1800c33c0  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800c33c5  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800c33cc  lea     rcx, [rsp+5B0h+pExceptionObject]; pExceptionObject
0x1800c33d1  call    _CxxThrowException_0
```
