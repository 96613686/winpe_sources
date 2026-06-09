# SystemSettings::PenSettings::GetLaunchableAppInfo(Windows::Internal::StateRepository::IApplication *,Windows::Internal::StateRepository::IApplicationResourceResolverStatics *,SystemSettings::PenSettings::AppInfo *)

- ea: `0x180054048`
- end: `0x18005432a`
- name: `?GetLaunchableAppInfo@PenSettings@SystemSettings@@YAJPEAUIApplication@StateRepository@Internal@Windows@@PEAUIApplicationResourceResolverStatics@456@PEAUAppInfo@12@@Z`
- size: `738`
- prototype: `__int64 __fastcall(SystemSettings::PenSettings *__hidden this, struct Windows::Internal::StateRepository::IApplication *, struct Windows::Internal::StateRepository::IApplicationResourceResolverStatics *, struct SystemSettings::PenSettings::AppInfo *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180022654`
- `0x180051f70`

## callees

- `0x180008128`
- `0x18000a2bc`
- `0x18001acf8`
- `0x18001cff8`
- `0x180054048`
- `0x180054330`
- `0x180054424`
- `0x18005d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18005421f`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18005421f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800541c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180054240`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005427c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005429f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800541c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180054240`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005427c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005429f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800540cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180054175`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800541b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800542c2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800542dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800542fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005431f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800540cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180054175`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800541b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800542c2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800542dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800542fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005431f`

## string_xrefs

- `0x18005408a`: `shellcommon\shell\settingshandlers\pen\lib\penblocklist.cpp`
- `0x1800540f4`: `shellcommon\shell\settingshandlers\pen\lib\penblocklist.cpp`
- `0x180054141`: `shellcommon\shell\settingshandlers\pen\lib\penblocklist.cpp`
- `0x18005419e`: `shellcommon\shell\settingshandlers\pen\lib\penblocklist.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall SystemSettings::PenSettings::GetLaunchableAppInfo(
        SystemSettings::PenSettings *this,
        struct Windows::Internal::StateRepository::IApplication *a2,
        struct Windows::Internal::StateRepository::IApplicationResourceResolverStatics *a3,
        struct SystemSettings::PenSettings::AppInfo *a4)
{
  int v7; // eax
  unsigned int v8; // ebx
  char v10; // r14
  bool v11; // al
  __int64 (__fastcall *v12)(SystemSettings::PenSettings *, HSTRING *); // rbx
  int v13; // eax
  __int64 (__fastcall *v14)(struct Windows::Internal::StateRepository::IApplication *, SystemSettings::PenSettings *, __int64 *); // rbx
  int v15; // eax
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, HSTRING *); // rbx
  int v18; // eax
  const wchar_t *StringRawBuffer; // rdi
  const unsigned __int16 *v20; // r9
  const unsigned __int16 *v21; // r9
  const unsigned __int16 *v22; // rdx
  const wchar_t **i; // rbx
  PCWSTR v24; // rax
  unsigned __int64 v25; // rcx
  PCWSTR v26; // rax
  __int64 v27; // rcx
  PCWSTR v28; // rax
  __int64 v29; // rdx
  const char *v30; // r9
  HSTRING string; // [rsp+20h] [rbp-48h] BYREF
  __int64 v32; // [rsp+28h] [rbp-40h] BYREF
  HSTRING v33[7]; // [rsp+30h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  int v35; // [rsp+70h] [rbp+8h] BYREF
  __int64 v36; // [rsp+88h] [rbp+20h]

  v35 = 0;
  v7 = (*(__int64 (__fastcall **)(SystemSettings::PenSettings *, int *, struct Windows::Internal::StateRepository::IApplicationResourceResolverStatics *, struct SystemSettings::PenSettings::AppInfo *))(*(_QWORD *)this + 528LL))(
         this,
         &v35,
         a3,
         a4);
  v8 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x33,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\penblocklist.cpp",
      (const char *)(unsigned int)v7,
      (int)string);
    return v8;
  }
  v10 = 1;
  v11 = v35 != 1;
  *((_BYTE *)a3 + 64) = v35 != 1;
  if ( v11 )
  {
    v33[0] = 0;
    v12 = *(__int64 (__fastcall **)(SystemSettings::PenSettings *, HSTRING *))(*(_QWORD *)this + 232LL);
    WindowsDeleteString(0);
    v33[0] = 0;
    v13 = v12(this, v33);
    v8 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x39,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\penblocklist.cpp",
        (const char *)(unsigned int)v13,
        (int)string);
LABEL_29:
      WindowsDeleteString(v33[0]);
      return v8;
    }
    v32 = 0;
    v14 = *(__int64 (__fastcall **)(struct Windows::Internal::StateRepository::IApplication *, SystemSettings::PenSettings *, __int64 *))(*(_QWORD *)a2 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
    v15 = v14(a2, this, &v32);
    v8 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3D,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\penblocklist.cpp",
        (const char *)(unsigned int)v15,
        (int)string);
LABEL_9:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
      goto LABEL_29;
    }
    string = 0;
    v16 = v32;
    v17 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v32 + 48LL);
    WindowsDeleteString(0);
    string = 0;
    v18 = v17(v16, &string);
    v8 = v18;
    if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3F,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\penblocklist.cpp",
        (const char *)(unsigned int)v18,
        (int)string);
      WindowsDeleteString(string);
      string = 0;
      goto LABEL_9;
    }
    StringRawBuffer = WindowsGetStringRawBuffer(v33[0], 0);
    if ( SystemSettings::PenSettings::IsAppIdInTheList(
           (SystemSettings::PenSettings *)off_180063D80,
           (const unsigned __int16 *const *)2,
           (unsigned int)StringRawBuffer,
           v20)
      || SystemSettings::PenSettings::IsAppIdInTheList(
           (SystemSettings::PenSettings *)off_180063CB0,
           (const unsigned __int16 *const *)0x19,
           (unsigned int)StringRawBuffer,
           v21) )
    {
      goto LABEL_25;
    }
    for ( i = (const wchar_t **)off_180063D90; i != (const wchar_t **)&load_config_used; ++i )
    {
      if ( wcsstr(StringRawBuffer, *i) )
        goto LABEL_25;
    }
    if ( SystemSettings::PenSettings::IsSearchAumId(StringRawBuffer, v22) )
      goto LABEL_25;
    v24 = WindowsGetStringRawBuffer(string, 0);
    v25 = -1;
    do
      ++v25;
    while ( v24[v25] );
    if ( v25 >= 3 && *v24 == 64 && v24[1] == 123 && v24[v25 - 1] == 125 )
LABEL_25:
      v10 = 0;
    *((_BYTE *)a3 + 64) = v10;
    try
    {
      v26 = WindowsGetStringRawBuffer(v33[0], 0);
      std::_WChar_traits<unsigned short>::length(v26);
      std::wstring::_Assign<unsigned short>(a3, v27);
      v28 = WindowsGetStringRawBuffer(string, 0);
      std::_WChar_traits<unsigned short>::length(v28);
      std::wstring::_Assign<unsigned short>((char *)a3 + 32, v29);
    }
    catch ( ... )
    {
      LODWORD(v36) = wil::details::in1diag3::Return_CaughtException(
                       retaddr,
                       (void *)0x49,
                       (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\penblocklist.cpp",
                       v30);
      WindowsDeleteString(string);
      string = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
      v8 = v36;
      goto LABEL_29;
    }
    WindowsDeleteString(string);
    string = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
    WindowsDeleteString(v33[0]);
  }
  return 0;
}

```

## disassembly

```asm
0x180054048  mov     [rsp+arg_8], rbx
0x18005404d  push    rsi
0x18005404e  push    rdi
0x18005404f  push    r12
0x180054051  push    r14
0x180054053  push    r15
0x180054055  sub     rsp, 40h
0x180054059  mov     r15, r8
0x18005405c  mov     r12, rdx
0x18005405f  mov     rdi, rcx
0x180054062  xor     esi, esi
0x180054064  mov     [rsp+68h+arg_0], esi
0x180054068  mov     rax, [rcx]
0x18005406b  lea     rdx, [rsp+68h+arg_0]
0x180054070  mov     rax, [rax+210h]
0x180054077  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005407c  mov     ebx, eax
0x18005407e  test    eax, eax
0x180054080  jns     short loc_1800540A0
0x180054082  mov     rcx, [rsp+68h]; this
0x180054087  mov     r9d, eax; char *
0x18005408a  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\settingshandlers\\p"...
0x180054091  lea     edx, [rsi+33h]; void *
0x180054094  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180054099  mov     eax, ebx
0x18005409b  jmp     loc_1800542E5
0x1800540a0  mov     r14d, 1
0x1800540a6  cmp     [rsp+68h+arg_0], r14d
0x1800540ab  setnz   al
0x1800540ae  mov     [r15+40h], al
0x1800540b2  test    al, al
0x1800540b4  jz      loc_1800542E3
0x1800540ba  mov     [rsp+68h+var_38], rsi
0x1800540bf  mov     rax, [rdi]
0x1800540c2  mov     rbx, [rax+0E8h]
0x1800540c9  xor     ecx, ecx; string
0x1800540cb  call    cs:__imp_WindowsDeleteString
0x1800540d1  mov     [rsp+68h+var_38], rsi
0x1800540d6  lea     rdx, [rsp+68h+var_38]
0x1800540db  mov     rcx, rdi
0x1800540de  mov     rax, rbx
0x1800540e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800540e6  mov     ebx, eax
0x1800540e8  test    eax, eax
0x1800540ea  jns     short loc_180054109
0x1800540ec  mov     rcx, [rsp+68h]; this
0x1800540f1  mov     r9d, eax; char *
0x1800540f4  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\settingshandlers\\p"...
0x1800540fb  lea     edx, [r14+38h]; void *
0x1800540ff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180054104  jmp     loc_18005431A
0x180054109  mov     [rsp+68h+var_40], rsi
0x18005410e  mov     rax, [r12]
0x180054112  mov     rbx, [rax+30h]
0x180054116  lea     rcx, [rsp+68h+var_40]
0x18005411b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180054120  lea     r8, [rsp+68h+var_40]
0x180054125  mov     rdx, rdi
0x180054128  mov     rcx, r12
0x18005412b  mov     rax, rbx
0x18005412e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054133  mov     ebx, eax
0x180054135  test    eax, eax
0x180054137  jns     short loc_180054162
0x180054139  mov     rcx, [rsp+68h]; this
0x18005413e  mov     r9d, eax; char *
0x180054141  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\settingshandlers\\p"...
0x180054148  mov     edx, 3Dh ; '='; void *
0x18005414d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180054152  nop
0x180054153  lea     rcx, [rsp+68h+var_40]
0x180054158  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005415d  jmp     loc_18005431A
0x180054162  mov     [rsp+68h+string], rsi
0x180054167  mov     rdi, [rsp+68h+var_40]
0x18005416c  mov     rax, [rdi]
0x18005416f  mov     rbx, [rax+30h]
0x180054173  xor     ecx, ecx; string
0x180054175  call    cs:__imp_WindowsDeleteString
0x18005417b  mov     [rsp+68h+string], rsi; int
0x180054180  lea     rdx, [rsp+68h+string]
0x180054185  mov     rcx, rdi
0x180054188  mov     rax, rbx
0x18005418b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054190  mov     ebx, eax
0x180054192  test    eax, eax
0x180054194  jns     short loc_1800541C2
0x180054196  mov     rcx, [rsp+68h]; this
0x18005419b  mov     r9d, eax; char *
0x18005419e  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\settingshandlers\\p"...
0x1800541a5  mov     edx, 3Fh ; '?'; void *
0x1800541aa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800541af  nop
0x1800541b0  mov     rcx, [rsp+68h+string]; string
0x1800541b5  call    cs:__imp_WindowsDeleteString
0x1800541bb  mov     [rsp+68h+string], rsi
0x1800541c0  jmp     short loc_180054153
0x1800541c2  xor     edx, edx; length
0x1800541c4  mov     rcx, [rsp+68h+var_38]; string
0x1800541c9  call    cs:__imp_WindowsGetStringRawBuffer
0x1800541cf  mov     rdi, rax
0x1800541d2  mov     r8, rax; unsigned int
0x1800541d5  mov     edx, 2; unsigned __int16 **
0x1800541da  lea     rcx, off_180063D80; this
0x1800541e1  call    ?IsAppIdInTheList@PenSettings@SystemSettings@@YA_NPEBQEBGIPEBG@Z; SystemSettings::PenSettings::IsAppIdInTheList(ushort const * const *,uint,ushort const *)
0x1800541e6  test    al, al
0x1800541e8  jnz     loc_18005426E
0x1800541ee  mov     r8, rdi; unsigned int
0x1800541f1  mov     edx, 19h; unsigned __int16 **
0x1800541f6  lea     rcx, off_180063CB0; this
0x1800541fd  call    ?IsAppIdInTheList@PenSettings@SystemSettings@@YA_NPEBQEBGIPEBG@Z; SystemSettings::PenSettings::IsAppIdInTheList(ushort const * const *,uint,ushort const *)
0x180054202  test    al, al
0x180054204  jnz     short loc_18005426E
0x180054206  lea     rbx, off_180063D90; "ExperienceHost_cw5n1h2txyewy"
0x18005420d  lea     rax, _load_config_used
0x180054214  mov     rcx, rdi; lpString1
0x180054217  cmp     rbx, rax
0x18005421a  jz      short loc_180054230
0x18005421c  mov     rdx, [rbx]; SubStr
0x18005421f  call    cs:__imp_wcsstr
0x180054225  test    rax, rax
0x180054228  jnz     short loc_18005426E
0x18005422a  add     rbx, 8
0x18005422e  jmp     short loc_18005420D
0x180054230  call    ?IsSearchAumId@PenSettings@SystemSettings@@YA_NPEBG@Z; SystemSettings::PenSettings::IsSearchAumId(ushort const *)
0x180054235  test    al, al
0x180054237  jnz     short loc_18005426E
0x180054239  xor     edx, edx; length
0x18005423b  mov     rcx, [rsp+68h+string]; string
0x180054240  call    cs:__imp_WindowsGetStringRawBuffer
0x180054246  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18005424a  inc     rcx
0x18005424d  cmp     [rax+rcx*2], si
0x180054251  jnz     short loc_18005424A
0x180054253  cmp     rcx, 3
0x180054257  jb      short loc_180054271
0x180054259  cmp     word ptr [rax], 40h ; '@'
0x18005425d  jnz     short loc_180054271
0x18005425f  cmp     word ptr [rax+2], 7Bh ; '{'
0x180054264  jnz     short loc_180054271
0x180054266  cmp     word ptr [rax+rcx*2-2], 7Dh ; '}'
0x18005426c  jnz     short loc_180054271
0x18005426e  mov     r14b, sil
0x180054271  mov     [r15+40h], r14b
0x180054275  xor     edx, edx; length
0x180054277  mov     rcx, [rsp+68h+var_38]; string
0x18005427c  call    cs:__imp_WindowsGetStringRawBuffer
0x180054282  mov     rcx, rax
0x180054285  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18005428a  mov     r8, rax
0x18005428d  mov     rdx, rcx
0x180054290  mov     rcx, r15
0x180054293  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180054298  xor     edx, edx; length
0x18005429a  mov     rcx, [rsp+68h+string]; string
0x18005429f  call    cs:__imp_WindowsGetStringRawBuffer
0x1800542a5  mov     rdx, rax
0x1800542a8  mov     rcx, rax
0x1800542ab  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x1800542b0  lea     rcx, [r15+20h]
0x1800542b4  mov     r8, rax
0x1800542b7  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800542bc  nop
0x1800542bd  mov     rcx, [rsp+68h+string]; string
0x1800542c2  call    cs:__imp_WindowsDeleteString
0x1800542c8  mov     [rsp+68h+string], rsi
0x1800542cd  lea     rcx, [rsp+68h+var_40]
0x1800542d2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800542d7  nop
0x1800542d8  mov     rcx, [rsp+68h+var_38]; string
0x1800542dd  call    cs:__imp_WindowsDeleteString
0x1800542e3  xor     eax, eax
0x1800542e5  mov     rbx, [rsp+68h+arg_8]
0x1800542ea  add     rsp, 40h
0x1800542ee  pop     r15
0x1800542f0  pop     r14
0x1800542f2  pop     r12
0x1800542f4  pop     rdi
0x1800542f5  pop     rsi
0x1800542f6  retn
0x1800542f7  mov     rcx, [rsp+68h+string]; string
0x1800542fc  call    cs:__imp_WindowsDeleteString
0x180054302  xor     esi, esi
0x180054304  mov     [rsp+68h+string], rsi
0x180054309  lea     rcx, [rsp+68h+var_40]
0x18005430e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180054313  mov     ebx, dword ptr [rsp+68h+arg_18]
0x18005431a  mov     rcx, [rsp+68h+var_38]; string
0x18005431f  call    cs:__imp_WindowsDeleteString
0x180054325  jmp     loc_180054099
```
