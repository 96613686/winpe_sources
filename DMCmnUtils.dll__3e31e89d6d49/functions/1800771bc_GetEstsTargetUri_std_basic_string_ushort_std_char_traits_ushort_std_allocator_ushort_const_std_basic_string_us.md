# GetEstsTargetUri(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x1800771bc`
- end: `0x180077596`
- name: `?GetEstsTargetUri@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV12@@Z`
- size: `986`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x1800754f0`

## callees

- `0x180007270`
- `0x180007c7c`
- `0x180057c4c`
- `0x180057c6c`
- `0x18005b73c`
- `0x18005bb6c`
- `0x18005bbf0`
- `0x18005d7b8`
- `0x180072a70`
- `0x180072a9c`
- `0x180072ad0`
- `0x180073d1c`
- `0x180074c9c`
- `0x1800771bc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180077317`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180077317`
- `WININET!InternetCrackUrlW` at `0x180077263`
- `WININET!InternetCrackUrlW` at `0x180077263`

## string_xrefs

- `0x1800771fd`: `onecoreuap\admin\dm\dmcmnutils\tokenutils\tokenutils.cpp`
- `0x18007727b`: `onecoreuap\admin\dm\dmcmnutils\tokenutils\tokenutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=14 #try_helpers=1
__int64 __fastcall GetEstsTargetUri(__int64 a1, __int64 a2)
{
  __int64 v5; // rax
  __int64 v6; // rbx
  const WCHAR *v7; // rax
  const char *v8; // r9
  bool v9; // di
  char *i; // rbx
  __int64 v11; // rax
  __int64 v12; // rdi
  __int64 v13; // rbx
  __int64 v14; // r8
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  _BYTE *v20; // rcx
  __int64 v21; // rbx
  __int64 v22; // r8
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rax
  int v26; // [rsp+20h] [rbp-228h]
  _QWORD v27[4]; // [rsp+28h] [rbp-220h] BYREF
  char v28; // [rsp+48h] [rbp-200h] BYREF
  $2B4FDC4BF487E67F052937EE78FAE255 UrlComponents; // [rsp+50h] [rbp-1F8h] BYREF
  _BYTE v30[32]; // [rsp+C0h] [rbp-188h] BYREF
  _BYTE v31[32]; // [rsp+E0h] [rbp-168h] BYREF
  _BYTE v32[32]; // [rsp+100h] [rbp-148h] BYREF
  _BYTE v33[32]; // [rsp+120h] [rbp-128h] BYREF
  _BYTE v34[32]; // [rsp+140h] [rbp-108h] BYREF
  _BYTE v35[32]; // [rsp+160h] [rbp-E8h] BYREF
  _BYTE v36[32]; // [rsp+180h] [rbp-C8h] BYREF
  _BYTE v37[32]; // [rsp+1A0h] [rbp-A8h] BYREF
  _BYTE v38[32]; // [rsp+1C0h] [rbp-88h] BYREF
  _BYTE v39[32]; // [rsp+1E0h] [rbp-68h] BYREF
  _BYTE v40[32]; // [rsp+200h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+248h] [rbp+0h]

  if ( *(_QWORD *)(a1 + 16) )
  {
    memset_0(&UrlComponents, 0, sizeof(UrlComponents));
    UrlComponents.dwStructSize = 104;
    UrlComponents.dwSchemeLength = -1;
    UrlComponents.dwHostNameLength = -1;
    v5 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1);
    v6 = -1;
    do
      ++v6;
    while ( *(_WORD *)(v5 + 2 * v6) );
    v7 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1);
    if ( InternetCrackUrlW(v7, v6, 0, &UrlComponents) )
    {
      std::wstring::wstring(v31, UrlComponents.lpszHostName, UrlComponents.dwHostNameLength);
      std::wstring::wstring(v30, UrlComponents.lpszScheme, UrlComponents.dwSchemeLength);
      v9 = UrlComponents.nPort != 0;
      v27[0] = L"http";
      v27[1] = 80;
      v27[2] = L"https";
      v27[3] = 443;
      for ( i = (char *)v27; i != &v28; i += 16 )
      {
        v11 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v30);
        if ( !(unsigned int)_o__wcsicmp(*(_QWORD *)i, v11) && UrlComponents.nPort == *((_DWORD *)i + 2) )
        {
          v9 = 0;
          break;
        }
      }
      if ( v9 )
      {
        v12 = std::wstring::wstring(v36, L"/");
        std::_Integral_to_string<unsigned short,int>(v37, UrlComponents.nPort);
        v13 = std::wstring::wstring(v35, L":");
        v14 = std::wstring::wstring(v34, L"://");
        v15 = std::operator+<unsigned short>(v33, v30, v14);
        v16 = std::operator+<unsigned short>(v32, v15, v31);
        v17 = std::operator+<unsigned short>(v40, v16, v13);
        v18 = std::operator+<unsigned short>(v39, v17, v37);
        v19 = std::operator+<unsigned short>(v38, v18, v12);
        std::wstring::operator=(a2, v19);
        std::wstring::_Tidy_deallocate(v38);
        std::wstring::_Tidy_deallocate(v39);
        std::wstring::_Tidy_deallocate(v40);
        std::wstring::_Tidy_deallocate(v32);
        std::wstring::_Tidy_deallocate(v33);
        std::wstring::_Tidy_deallocate(v34);
        std::wstring::_Tidy_deallocate(v35);
        std::wstring::_Tidy_deallocate(v37);
        v20 = v36;
      }
      else
      {
        v21 = std::wstring::wstring(v32, L"/");
        v22 = std::wstring::wstring(v33, L"://");
        v23 = std::operator+<unsigned short>(v34, v30, v22);
        v24 = std::operator+<unsigned short>(v35, v23, v31);
        v25 = std::operator+<unsigned short>(v36, v24, v21);
        std::wstring::operator=(a2, v25);
        std::wstring::_Tidy_deallocate(v36);
        std::wstring::_Tidy_deallocate(v35);
        std::wstring::_Tidy_deallocate(v34);
        std::wstring::_Tidy_deallocate(v33);
        v20 = v32;
      }
      std::wstring::_Tidy_deallocate(v20);
      std::wstring::_Tidy_deallocate(v30);
      std::wstring::_Tidy_deallocate(v31);
      return 0;
    }
    else
    {
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0x336,
               (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\tokenutils\\tokenutils.cpp",
               v8);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x329,
      (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\tokenutils\\tokenutils.cpp",
      (const char *)0x80070057LL,
      v26);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x1800771bc  mov     [rsp+arg_10], rbx
0x1800771c1  push    rsi
0x1800771c2  push    rdi
0x1800771c3  push    r14
0x1800771c5  sub     rsp, 230h
0x1800771cc  mov     rax, cs:__security_cookie
0x1800771d3  xor     rax, rsp
0x1800771d6  mov     [rsp+248h+var_28], rax
0x1800771de  mov     rsi, rdx
0x1800771e1  mov     rdi, rcx
0x1800771e4  xor     r14d, r14d
0x1800771e7  cmp     [rcx+10h], r14
0x1800771eb  jnz     short loc_180077215
0x1800771ed  mov     rcx, [rsp+248h]; this
0x1800771f5  mov     ebx, 80070057h
0x1800771fa  mov     r9d, ebx; char *
0x1800771fd  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\dm\\dmcmnutils\\toke"...
0x180077204  mov     edx, 329h; void *
0x180077209  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007720e  mov     eax, ebx
0x180077210  jmp     loc_180077571
0x180077215  mov     ebx, 68h ; 'h'
0x18007721a  mov     r8d, ebx; Size
0x18007721d  xor     edx, edx; Val
0x18007721f  lea     rcx, [rsp+248h+UrlComponents]; void *
0x180077224  call    memset_0
0x180077229  mov     [rsp+248h+UrlComponents.dwStructSize], ebx
0x18007722d  or      eax, 0FFFFFFFFh
0x180077230  mov     [rsp+248h+UrlComponents.dwSchemeLength], eax
0x180077234  mov     [rsp+248h+UrlComponents.dwHostNameLength], eax
0x180077238  mov     rcx, rdi
0x18007723b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180077240  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180077244  inc     rbx
0x180077247  cmp     [rax+rbx*2], r14w
0x18007724c  jnz     short loc_180077244
0x18007724e  mov     rcx, rdi
0x180077251  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180077256  lea     r9, [rsp+248h+UrlComponents]; lpUrlComponents
0x18007725b  xor     r8d, r8d; dwFlags
0x18007725e  mov     edx, ebx; dwUrlLength
0x180077260  mov     rcx, rax; lpszUrl
0x180077263  call    cs:__imp_InternetCrackUrlW
0x18007726a  nop     dword ptr [rax+rax+00h]
0x18007726f  test    eax, eax
0x180077271  jnz     short loc_180077291
0x180077273  mov     rcx, [rsp+248h]; this
0x18007727b  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\dm\\dmcmnutils\\toke"...
0x180077282  mov     edx, 336h; void *
0x180077287  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18007728c  jmp     loc_180077571
0x180077291  mov     r8d, [rsp+248h+UrlComponents.dwHostNameLength]
0x180077296  mov     rdx, [rsp+248h+UrlComponents.lpszHostName]
0x18007729b  lea     rcx, [rsp+248h+var_168]
0x1800772a3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG_K@Z; std::wstring::wstring(ushort const * const,unsigned __int64)
0x1800772a8  nop
0x1800772a9  mov     r8d, [rsp+248h+UrlComponents.dwSchemeLength]
0x1800772ae  mov     rdx, [rsp+248h+UrlComponents.lpszScheme]
0x1800772b3  lea     rcx, [rsp+248h+var_188]
0x1800772bb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG_K@Z; std::wstring::wstring(ushort const * const,unsigned __int64)
0x1800772c0  nop
0x1800772c1  cmp     [rsp+248h+UrlComponents.nPort], r14w
0x1800772c7  setnz   dil
0x1800772cb  lea     rax, aHttp; "http"
0x1800772d2  mov     [rsp+248h+var_220], rax
0x1800772d7  mov     [rsp+248h+var_218], 50h ; 'P'
0x1800772e0  lea     rax, aHttps_0; "https"
0x1800772e7  mov     [rsp+248h+var_210], rax
0x1800772ec  mov     [rsp+248h+var_208], 1BBh
0x1800772f5  lea     rbx, [rsp+248h+var_220]
0x1800772fa  lea     rax, [rsp+248h+var_200]
0x1800772ff  cmp     rbx, rax
0x180077302  jz      short loc_18007733A
0x180077304  lea     rcx, [rsp+248h+var_188]
0x18007730c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180077311  mov     rdx, rax
0x180077314  mov     rcx, [rbx]
0x180077317  call    cs:__imp__o__wcsicmp
0x18007731e  nop     dword ptr [rax+rax+00h]
0x180077323  test    eax, eax
0x180077325  jnz     short loc_180077331
0x180077327  movzx   eax, [rsp+248h+UrlComponents.nPort]
0x18007732c  cmp     eax, [rbx+8]
0x18007732f  jz      short loc_180077337
0x180077331  add     rbx, 10h
0x180077335  jmp     short loc_1800772FA
0x180077337  mov     dil, r14b
0x18007733a  lea     rdx, S2; "/"
0x180077341  test    dil, dil
0x180077344  jz      loc_180077493
0x18007734a  lea     rcx, [rsp+248h+var_C8]
0x180077352  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180077357  mov     rdi, rax
0x18007735a  movzx   edx, [rsp+248h+UrlComponents.nPort]
0x18007735f  lea     rcx, [rsp+248h+var_A8]
0x180077367  call    ??$_Integral_to_string@GH@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@H@Z; std::_Integral_to_string<ushort,int>(int)
0x18007736c  nop
0x18007736d  lea     rdx, asc_1800D22B4; ":"
0x180077374  lea     rcx, [rsp+248h+var_E8]
0x18007737c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180077381  mov     rbx, rax
0x180077384  lea     rdx, asc_1800D22E0; "://"
0x18007738b  lea     rcx, [rsp+248h+var_108]
0x180077393  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180077398  nop
0x180077399  mov     r8, rax
0x18007739c  lea     rdx, [rsp+248h+var_188]
0x1800773a4  lea     rcx, [rsp+248h+var_128]
0x1800773ac  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@$$QEAV10@@Z; std::operator+<ushort>(std::wstring const &,std::wstring &&)
0x1800773b1  nop
0x1800773b2  lea     r8, [rsp+248h+var_168]
0x1800773ba  mov     rdx, rax
0x1800773bd  lea     rcx, [rsp+248h+var_148]
0x1800773c5  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x1800773ca  nop
0x1800773cb  mov     r8, rbx
0x1800773ce  mov     rdx, rax
0x1800773d1  lea     rcx, [rsp+248h+var_48]
0x1800773d9  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@0@Z; std::operator+<ushort>(std::wstring &&,std::wstring &&)
0x1800773de  nop
0x1800773df  lea     r8, [rsp+248h+var_A8]
0x1800773e7  mov     rdx, rax
0x1800773ea  lea     rcx, [rsp+248h+var_68]
0x1800773f2  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@0@Z; std::operator+<ushort>(std::wstring &&,std::wstring &&)
0x1800773f7  nop
0x1800773f8  mov     r8, rdi
0x1800773fb  mov     rdx, rax
0x1800773fe  lea     rcx, [rsp+248h+var_88]
0x180077406  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@0@Z; std::operator+<ushort>(std::wstring &&,std::wstring &&)
0x18007740b  mov     rdx, rax
0x18007740e  mov     rcx, rsi
0x180077411  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180077416  lea     rcx, [rsp+248h+var_88]
0x18007741e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180077423  nop
0x180077424  lea     rcx, [rsp+248h+var_68]
0x18007742c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180077431  nop
0x180077432  lea     rcx, [rsp+248h+var_48]
0x18007743a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007743f  nop
0x180077440  lea     rcx, [rsp+248h+var_148]
0x180077448  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007744d  nop
0x18007744e  lea     rcx, [rsp+248h+var_128]
0x180077456  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007745b  nop
0x18007745c  lea     rcx, [rsp+248h+var_108]
0x180077464  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180077469  nop
0x18007746a  lea     rcx, [rsp+248h+var_E8]
0x180077472  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180077477  nop
0x180077478  lea     rcx, [rsp+248h+var_A8]
0x180077480  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180077485  nop
0x180077486  lea     rcx, [rsp+248h+var_C8]
0x18007748e  jmp     loc_180077548
0x180077493  lea     rcx, [rsp+248h+var_148]
0x18007749b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800774a0  mov     rbx, rax
0x1800774a3  lea     rdx, asc_1800D22E0; "://"
0x1800774aa  lea     rcx, [rsp+248h+var_128]
0x1800774b2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800774b7  nop
0x1800774b8  mov     r8, rax
0x1800774bb  lea     rdx, [rsp+248h+var_188]
0x1800774c3  lea     rcx, [rsp+248h+var_108]
0x1800774cb  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@$$QEAV10@@Z; std::operator+<ushort>(std::wstring const &,std::wstring &&)
0x1800774d0  nop
0x1800774d1  lea     r8, [rsp+248h+var_168]
0x1800774d9  mov     rdx, rax
0x1800774dc  lea     rcx, [rsp+248h+var_E8]
0x1800774e4  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x1800774e9  nop
0x1800774ea  mov     r8, rbx
0x1800774ed  mov     rdx, rax
0x1800774f0  lea     rcx, [rsp+248h+var_C8]
0x1800774f8  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@0@Z; std::operator+<ushort>(std::wstring &&,std::wstring &&)
0x1800774fd  mov     rdx, rax
0x180077500  mov     rcx, rsi
0x180077503  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180077508  lea     rcx, [rsp+248h+var_C8]
0x180077510  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180077515  nop
0x180077516  lea     rcx, [rsp+248h+var_E8]
0x18007751e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180077523  nop
0x180077524  lea     rcx, [rsp+248h+var_108]
0x18007752c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180077531  nop
0x180077532  lea     rcx, [rsp+248h+var_128]
0x18007753a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007753f  nop
0x180077540  lea     rcx, [rsp+248h+var_148]
0x180077548  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007754d  nop
0x18007754e  lea     rcx, [rsp+248h+var_188]
0x180077556  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007755b  nop
0x18007755c  lea     rcx, [rsp+248h+var_168]
0x180077564  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180077569  xor     eax, eax
0x18007756b  jmp     short loc_180077571
0x18007756d  mov     eax, [rsp+248h+var_228]
0x180077571  mov     rcx, [rsp+248h+var_28]
0x180077579  xor     rcx, rsp; StackCookie
0x18007757c  call    __security_check_cookie
0x180077581  mov     rbx, [rsp+248h+arg_10]
0x180077589  add     rsp, 230h
0x180077590  pop     r14
0x180077592  pop     rdi
0x180077593  pop     rsi
0x180077594  retn
```
