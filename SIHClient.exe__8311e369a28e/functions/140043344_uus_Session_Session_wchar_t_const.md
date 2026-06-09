# uus::Session::Session(wchar_t const *)

- ea: `0x140043344`
- end: `0x140043503`
- name: `??0Session@uus@@QEAA@PEB_W@Z`
- size: `447`
- prototype: `uus::Session *__fastcall(uus::Session *this, const wchar_t *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140040ef8`

## callees

- `0x140005eec`
- `0x1400071c0`
- `0x1400073f0`
- `0x140042c88`
- `0x140042e00`
- `0x140042ec8`
- `0x140043210`
- `0x140043344`
- `0x140043c40`
- `0x140044450`
- `0x140045dc0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400433fe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400433fe`

## pseudocode

```c
uus::Session *__fastcall uus::Session::Session(uus::Session *this, const wchar_t *a2)
{
  __int64 v3; // rbx
  unsigned __int64 v4; // r8
  __int64 GuestOrNativeArchFolder; // rax
  __int64 HostArchFolder; // rax
  LPVOID pv; // [rsp+20h] [rbp-E0h] BYREF
  __int128 v9; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v10; // [rsp+38h] [rbp-C8h]
  __int64 v11; // [rsp+40h] [rbp-C0h]
  _BYTE v12[40]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v13[32]; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v14[4]; // [rsp+98h] [rbp-68h] BYREF
  __int128 v15; // [rsp+B8h] [rbp-48h] BYREF
  __m128i v16; // [rsp+C8h] [rbp-38h]
  char v17; // [rsp+D8h] [rbp-28h]
  _OWORD v18[2]; // [rsp+E0h] [rbp-20h] BYREF
  char v19; // [rsp+100h] [rbp+0h]
  char v20[16]; // [rsp+108h] [rbp+8h] BYREF
  __m128i si128; // [rsp+118h] [rbp+18h]

  v3 = 0;
  *(_QWORD *)this = &uus::Session::`vftable';
  v14[0] = 32;
  v14[1] = 3;
  v14[2] = &_ImageBase;
  v14[3] = a2;
  *(_OWORD *)v20 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  *(_WORD *)v20 = 0;
  pv = 0;
  wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>((char *)&pv);
  v4 = -1;
  do
    ++v4;
  while ( *((_WORD *)pv + v4) );
  v9 = 0;
  v10 = 0;
  v11 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v9, pv, v4);
  if ( pv )
    CoTaskMemFree(pv);
  GuestOrNativeArchFolder = uus::Utility::GetGuestOrNativeArchFolder(v13, &v9);
  uus::Utility::FindFileInSubFolder(&v15, GuestOrNativeArchFolder);
  std::wstring::~wstring(v13);
  if ( v17 )
  {
    v18[0] = v15;
    v18[1] = v16;
    v16 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v15) = 0;
    v19 = 1;
LABEL_10:
    std::wstring::~wstring(&v15);
    goto LABEL_11;
  }
  HostArchFolder = uus::Utility::GetHostArchFolder(v12, &v9);
  uus::Utility::FindFileInSubFolder(v18, HostArchFolder);
  if ( v12[32] )
    std::wstring::~wstring(v12);
  if ( v17 )
    goto LABEL_10;
LABEL_11:
  std::wstring::~wstring(&v9);
  if ( v19 )
  {
    std::wstring::operator=(v20, v18);
    if ( v19 )
      std::wstring::~wstring(v18);
    v3 = uus::Utility::GetBrainSession<uus::Brain3>(v20, (__int64)v14);
  }
  std::wstring::~wstring(v20);
  *((_QWORD *)this + 1) = v3;
  return this;
}

```

## disassembly

```asm
0x140043344  mov     [rsp-8+arg_10], rbx
0x140043349  mov     [rsp-8+arg_18], rdi
0x14004334e  push    rbp
0x14004334f  lea     rbp, [rsp-30h]
0x140043354  sub     rsp, 130h
0x14004335b  mov     rax, cs:__security_cookie
0x140043362  xor     rax, rsp
0x140043365  mov     [rbp+30h+var_8], rax
0x140043369  mov     rdi, rcx
0x14004336c  mov     [rsp+130h+pv], rcx
0x140043371  xor     ebx, ebx
0x140043373  lea     rax, ??_7Session@uus@@6B@; const uus::Session::`vftable'
0x14004337a  mov     [rcx], rax
0x14004337d  mov     [rbp+30h+var_98], 20h ; ' '
0x140043385  mov     [rbp+30h+var_90], 3
0x14004338d  lea     rax, __ImageBase
0x140043394  mov     [rbp+30h+var_88], rax
0x140043398  mov     [rbp+30h+var_80], rdx
0x14004339c  xorps   xmm0, xmm0
0x14004339f  movups  xmmword ptr [rbp+30h+var_28], xmm0
0x1400433a3  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1400433ab  movdqu  [rbp+30h+var_18], xmm1
0x1400433b0  mov     word ptr [rbp+30h+var_28], bx
0x1400433b4  mov     [rsp+130h+pv], rbx
0x1400433b9  lea     rcx, [rsp+130h+pv]
0x1400433be  call    ??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEB_W@Z; wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(wchar_t const *)
0x1400433c3  nop
0x1400433c4  mov     rdx, [rsp+130h+pv]
0x1400433c9  or      r8, 0FFFFFFFFFFFFFFFFh
0x1400433cd  inc     r8
0x1400433d0  cmp     [rdx+r8*2], bx
0x1400433d5  jnz     short loc_1400433CD
0x1400433d7  xorps   xmm0, xmm0
0x1400433da  movups  [rsp+130h+var_108], xmm0
0x1400433df  mov     [rsp+130h+var_F8], rbx
0x1400433e4  mov     [rsp+130h+var_F0], rbx
0x1400433e9  lea     rcx, [rsp+130h+var_108]
0x1400433ee  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1400433f3  nop
0x1400433f4  mov     rcx, [rsp+130h+pv]; pv
0x1400433f9  test    rcx, rcx
0x1400433fc  jz      short loc_140043405
0x1400433fe  call    cs:__imp_CoTaskMemFree
0x140043404  nop
0x140043405  lea     rdx, [rsp+130h+var_108]
0x14004340a  lea     rcx, [rsp+130h+var_B8]
0x14004340f  call    ?GetGuestOrNativeArchFolder@Utility@uus@@SA?AVpath@filesystem@std@@AEBV345@@Z; uus::Utility::GetGuestOrNativeArchFolder(std::filesystem::path const &)
0x140043414  nop
0x140043415  mov     rdx, rax
0x140043418  lea     rcx, [rbp+30h+var_78]
0x14004341c  call    ?FindFileInSubFolder@Utility@uus@@SA?AV?$optional@Vpath@filesystem@std@@@std@@AEBVpath@filesystem@4@PEB_W@Z; uus::Utility::FindFileInSubFolder(std::filesystem::path const &,wchar_t const *)
0x140043421  nop
0x140043422  lea     rcx, [rsp+130h+var_B8]; void *
0x140043427  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004342c  cmp     [rbp+30h+var_58], bl
0x14004342f  jz      short loc_140043458
0x140043431  movups  xmm1, [rbp+30h+var_78]
0x140043435  movups  [rbp+30h+var_50], xmm1
0x140043439  movups  xmm0, [rbp+30h+var_68]
0x14004343d  movups  [rbp+30h+var_40], xmm0
0x140043441  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x140043449  movdqu  [rbp+30h+var_68], xmm1
0x14004344e  mov     word ptr [rbp+30h+var_78], bx
0x140043452  mov     [rbp+30h+var_30], 1
0x140043456  jmp     short loc_14004348B
0x140043458  lea     rdx, [rsp+130h+var_108]
0x14004345d  lea     rcx, [rsp+130h+var_E0]
0x140043462  call    ?GetHostArchFolder@Utility@uus@@SA?AV?$optional@Vpath@filesystem@std@@@std@@AEBVpath@filesystem@4@@Z; uus::Utility::GetHostArchFolder(std::filesystem::path const &)
0x140043467  nop
0x140043468  mov     rdx, rax
0x14004346b  lea     rcx, [rbp+30h+var_50]
0x14004346f  call    ?FindFileInSubFolder@Utility@uus@@SA?AV?$optional@Vpath@filesystem@std@@@std@@AEBV34@PEB_W@Z; uus::Utility::FindFileInSubFolder(std::optional<std::filesystem::path> const &,wchar_t const *)
0x140043474  nop
0x140043475  cmp     [rsp+130h+var_C0], bl
0x140043479  jz      short loc_140043486
0x14004347b  lea     rcx, [rsp+130h+var_E0]; void *
0x140043480  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140043485  nop
0x140043486  cmp     [rbp+30h+var_58], bl
0x140043489  jz      short loc_140043495
0x14004348b  lea     rcx, [rbp+30h+var_78]; void *
0x14004348f  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140043494  nop
0x140043495  lea     rcx, [rsp+130h+var_108]; void *
0x14004349a  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004349f  cmp     [rbp+30h+var_30], bl
0x1400434a2  jnz     short loc_1400434A6
0x1400434a4  jmp     short loc_1400434D2
0x1400434a6  lea     rdx, [rbp+30h+var_50]
0x1400434aa  lea     rcx, [rbp+30h+var_28]
0x1400434ae  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1400434b3  nop
0x1400434b4  cmp     [rbp+30h+var_30], bl
0x1400434b7  jz      short loc_1400434C2
0x1400434b9  lea     rcx, [rbp+30h+var_50]; void *
0x1400434bd  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400434c2  lea     rdx, [rbp+30h+var_98]
0x1400434c6  lea     rcx, [rbp+30h+var_28]; char *
0x1400434ca  call    ??$GetBrainSession@UBrain3@uus@@@Utility@uus@@SAPEAUBrain3@1@AEBVpath@filesystem@std@@AEBUPinkyContext@1@@Z; uus::Utility::GetBrainSession<uus::Brain3>(std::filesystem::path const &,uus::PinkyContext const &)
0x1400434cf  mov     rbx, rax
0x1400434d2  lea     rcx, [rbp+30h+var_28]; void *
0x1400434d6  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400434db  mov     [rdi+8], rbx
0x1400434df  mov     rax, rdi
0x1400434e2  mov     rcx, [rbp+30h+var_8]
0x1400434e6  xor     rcx, rsp; StackCookie
0x1400434e9  call    __security_check_cookie
0x1400434ee  lea     r11, [rsp+130h+var_s0]
0x1400434f6  mov     rbx, [r11+20h]
0x1400434fa  mov     rdi, [r11+28h]
0x1400434fe  mov     rsp, r11
0x140043501  pop     rbp
0x140043502  retn
```
