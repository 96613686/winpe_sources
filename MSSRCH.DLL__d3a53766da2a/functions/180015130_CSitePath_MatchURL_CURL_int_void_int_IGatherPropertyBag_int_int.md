# CSitePath::MatchURL(CURL *,int *,void * &,int *,IGatherPropertyBag * *,int *,int *)

- ea: `0x180015130`
- end: `0x180015ad4`
- name: `?MatchURL@CSitePath@@QEAAJPEAVCURL@@PEAHAEAPEAX1PEAPEAUIGatherPropertyBag@@11@Z`
- size: `2468`
- prototype: `__int64 __fastcall(CSitePath *__hidden this, struct CURL *, int *, void **, int *, struct IGatherPropertyBag **, int *, int *)`
- caller_count: `2`
- callee_count: `27`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180014394`
- `0x180017058`

## callees

- `0x180015130`
- `0x180015ae0`
- `0x1800160f0`
- `0x180016c94`
- `0x18001b470`
- `0x18001d730`
- `0x18001f7c0`
- `0x180022b10`
- `0x1800269b0`
- `0x1800278bc`
- `0x1800296b0`
- `0x180029db0`
- `0x18003cc50`
- `0x1800903dc`
- `0x1800904ec`
- `0x18009d368`
- `0x1800ae078`
- `0x1800ae2ec`
- `0x1800af3dc`
- `0x1800c0bd0`
- `0x18010a2e4`
- `0x1801244c0`
- `0x180124990`
- `0x180124b5c`
- `0x180124bc4`
- `0x18013dd98`
- `0x180241010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800156ef`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180015717`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180015739`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800156ef`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180015717`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180015739`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180015425`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18001548f`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180015425`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18001548f`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x1800156db`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x1800156db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001563c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001563c`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x180015862`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x180015862`

## string_xrefs

- `0x180015459`: `onecoreuap\base\appmodel\Search\common\include\lmstr.hxx`
- `0x1800154c0`: `onecoreuap\base\appmodel\Search\common\include\lmstr.hxx`
- `0x180015a54`: `onecoreuap\base\appmodel\Search\common\include\lmstr.hxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CSitePath::MatchURL(
        CSitePath *this,
        struct CURL *a2,
        int *a3,
        void **a4,
        int *a5,
        struct IGatherPropertyBag **a6,
        int *a7,
        int *a8)
{
  __int16 v10; // ax
  _WORD *v11; // rdi
  __int64 v12; // rcx
  int v13; // esi
  unsigned __int64 v14; // rdx
  int v15; // ecx
  void **v16; // r15
  __int64 v17; // rdi
  void **v18; // r13
  __int64 v19; // rax
  __int16 v21; // ax
  unsigned int AnySlash; // eax
  struct IGatherPropertyBag **v23; // rbx
  int v24; // ecx
  int v25; // ecx
  wchar_t *v26; // rax
  wchar_t *v27; // rax
  int v28; // ecx
  int v29; // ecx
  __int64 matched; // rbx
  void *v31; // rcx
  const wchar_t *v32; // rdx
  wchar_t *v33; // rax
  __int64 v34; // rbx
  __int64 v35; // r15
  wchar_t *v36; // rax
  __int64 v37; // rdi
  wchar_t *v38; // rax
  wchar_t v39; // cx
  bool v40; // bl
  __int64 v41; // r9
  __int64 v42; // rcx
  char v43; // r13
  unsigned int lpDestStr; // [rsp+20h] [rbp-E0h]
  LPVOID pv; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID *p_pv; // [rsp+38h] [rbp-C8h] BYREF
  PWSTR ppszPath; // [rsp+40h] [rbp-C0h] BYREF
  char v48; // [rsp+48h] [rbp-B8h]
  int *v49; // [rsp+50h] [rbp-B0h]
  struct IGatherPropertyBag **v50; // [rsp+58h] [rbp-A8h]
  int *v51; // [rsp+60h] [rbp-A0h]
  int *v52; // [rsp+68h] [rbp-98h]
  _QWORD v53[2]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v54; // [rsp+80h] [rbp-80h] BYREF
  char v55; // [rsp+88h] [rbp-78h]
  _BYTE v56[24]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v57; // [rsp+A8h] [rbp-58h]
  __int64 v58; // [rsp+B0h] [rbp-50h]
  char v59; // [rsp+B8h] [rbp-48h]
  __int128 v60; // [rsp+C0h] [rbp-40h]
  char v61; // [rsp+D0h] [rbp-30h]
  __int64 v62; // [rsp+D8h] [rbp-28h]
  __int64 v63; // [rsp+E0h] [rbp-20h]
  char v64; // [rsp+E8h] [rbp-18h]
  _QWORD v65[2]; // [rsp+F0h] [rbp-10h] BYREF
  int v66; // [rsp+100h] [rbp+0h]
  char v67; // [rsp+108h] [rbp+8h] BYREF
  _BYTE v68[112]; // [rsp+190h] [rbp+90h] BYREF
  void **v69; // [rsp+200h] [rbp+100h] BYREF
  _BYTE *v70; // [rsp+208h] [rbp+108h]
  int v71; // [rsp+210h] [rbp+110h]
  unsigned int v72; // [rsp+214h] [rbp+114h]
  _BYTE v73[136]; // [rsp+218h] [rbp+118h] BYREF
  void **v74; // [rsp+2A0h] [rbp+1A0h] BYREF
  LPWSTR Str; // [rsp+2A8h] [rbp+1A8h]
  int v76; // [rsp+2B0h] [rbp+1B0h]
  int cchSrc; // [rsp+2B4h] [rbp+1B4h]
  char v78; // [rsp+2B8h] [rbp+1B8h] BYREF
  void **v79; // [rsp+340h] [rbp+240h] BYREF
  wchar_t *v80; // [rsp+348h] [rbp+248h]
  __int64 v81; // [rsp+350h] [rbp+250h]
  __int16 v82; // [rsp+358h] [rbp+258h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+528h] [rbp+428h]

  v49 = a3;
  v51 = a5;
  v50 = a6;
  v52 = a7;
  if ( !a2 || !a3 )
    return 2147500035LL;
  if ( a8 )
    *a8 = 0;
  v10 = *((_WORD *)a2 + 231);
  if ( (v10 & 8) != 0 )
  {
    *((_WORD *)a2 + 231) = v10 & 0xFFF7;
    CURL::ParseHost(a2);
    v11 = (_WORD *)((char *)a2 + 450);
    *((_WORD *)a2 + 226) = *((_WORD *)a2 + 227) - *((_WORD *)a2 + 225);
  }
  else
  {
    v11 = (_WORD *)((char *)a2 + 450);
  }
  v12 = *((unsigned __int16 *)a2 + 226);
  v13 = 1;
  if ( (_WORD)v12 || !*((_WORD *)a2 + 220) )
  {
    v14 = (unsigned __int16)*v11;
    if ( v14 + v12 < v14 )
      SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v12);
    if ( v14 + v12 > *((unsigned int *)a2 + 11) )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x40C,
        (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\lmstr.hxx",
        (const char *)0xCE,
        lpDestStr);
    p_pv = (LPVOID *)__PAIR64__(v12, v14);
    ppszPath = (PWSTR)((char *)a2 + 24);
  }
  else
  {
    if ( __TSS0__1__GetPathWithoutAfterPath_CURL__QEAA_AVCLMSubStr__XZ_4HA > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                                         + (unsigned int)tls_index)
                                                                                       + 4LL) )
    {
      Init_thread_header(&__TSS0__1__GetPathWithoutAfterPath_CURL__QEAA_AVCLMSubStr__XZ_4HA);
      if ( __TSS0__1__GetPathWithoutAfterPath_CURL__QEAA_AVCLMSubStr__XZ_4HA == -1 )
      {
        dword_1802DA2B4 = 1;
        dword_1802DA2B0 = 1;
        qword_1802DA2A8 = (__int64)L"/";
        `CURL::GetPathWithoutAfterPath'::`2'::slash = (__int64)&CConstString::`vftable';
        atexit(`CURL::GetPathWithoutAfterPath'::`2'::`dynamic atexit destructor for 'slash'');
        Init_thread_footer(&__TSS0__1__GetPathWithoutAfterPath_CURL__QEAA_AVCLMSubStr__XZ_4HA);
      }
    }
    LODWORD(p_pv) = 0;
    HIDWORD(p_pv) = dword_1802DA2B4;
    ppszPath = (PWSTR)&`CURL::GetPathWithoutAfterPath'::`2'::slash;
  }
  CURL::ParseAccessType(a2);
  if ( !*((_WORD *)a2 + 220) )
  {
    v21 = *((_WORD *)a2 + 231);
    if ( (v21 & 8) != 0 )
    {
      *((_WORD *)a2 + 231) = v21 & 0xFFF7;
      CURL::ParseHost(a2);
      *((_WORD *)a2 + 226) = *((_WORD *)a2 + 227) - *v11;
    }
    if ( *((_WORD *)a2 + 220) || *((_WORD *)a2 + 222) )
    {
      CLMSubStr::ReduceLeft((CLMSubStr *)&p_pv, 2u);
      AnySlash = CLMSubStr::FindAnySlash((CLMSubStr *)&p_pv, 0);
      if ( AnySlash == -1 )
        return 1;
      CLMSubStr::ReduceLeft((CLMSubStr *)&p_pv, AnySlash);
    }
  }
  CURL::ParseAccessType(a2);
  v15 = *((unsigned __int16 *)a2 + 220);
  v16 = &CURL::m_csInvalid;
  pv = (LPVOID)0xFFFFFFFFLL;
  if ( v15 )
  {
    v24 = v15 - 1;
    if ( v24 )
    {
      v25 = v24 - 5;
      if ( v25 )
      {
        v28 = v25 - 1;
        if ( v28 )
        {
          v29 = v28 - 1;
          if ( v29 )
          {
            if ( v29 == 1 )
            {
              LODWORD(v17) = dword_1802D6E0C;
              v18 = &CURL::m_csCSC;
            }
            else
            {
              LODWORD(v17) = dword_1802D6E24;
              v18 = &CURL::m_csInvalid;
            }
          }
          else
          {
            LODWORD(v17) = dword_1802D6DF4;
            v18 = &CURL::m_csWinRt;
          }
        }
        else
        {
          LODWORD(v17) = dword_1802D6DC4;
          v18 = &CURL::m_csHttps;
        }
      }
      else
      {
        if ( *((_DWORD *)a2 + 11) )
        {
          v26 = wcschr(*((const wchar_t **)a2 + 4), 0x3Au);
          if ( v26 )
            v17 = ((__int64)v26 - *((_QWORD *)a2 + 4)) >> 1;
          else
            LODWORD(v17) = -1;
        }
        else
        {
          LODWORD(v17) = -1;
        }
        v18 = (void **)((char *)a2 + 24);
        if ( (unsigned int)v17 > *((_DWORD *)a2 + 11) )
          wil::details::in1diag3::Throw_Win32(
            retaddr,
            (void *)0x40C,
            (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\lmstr.hxx",
            (const char *)0xCE,
            lpDestStr);
      }
    }
    else
    {
      LODWORD(v17) = dword_1802D6DAC;
      v18 = &CURL::m_csHttp;
    }
  }
  else
  {
    LODWORD(v17) = dword_1802D6DDC;
    v18 = &CURL::m_csFile;
  }
  CURL::ParseAccessType((CSitePath *)((char *)this + 80));
  if ( *((_WORD *)this + 260) )
  {
    switch ( *((_WORD *)this + 260) )
    {
      case 1:
        LODWORD(v19) = dword_1802D6DAC;
        v16 = &CURL::m_csHttp;
        break;
      case 6:
        if ( *((_DWORD *)this + 31) )
        {
          v27 = wcschr(*((const wchar_t **)this + 14), 0x3Au);
          if ( v27 )
            v19 = ((__int64)v27 - *((_QWORD *)this + 14)) >> 1;
          else
            LODWORD(v19) = (_DWORD)pv;
        }
        else
        {
          LODWORD(v19) = (_DWORD)pv;
        }
        v16 = (void **)((char *)this + 104);
        if ( (unsigned int)v19 > *((_DWORD *)this + 31) )
          wil::details::in1diag3::Throw_Win32(
            retaddr,
            (void *)0x40C,
            (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\lmstr.hxx",
            (const char *)0xCE,
            lpDestStr);
        break;
      case 7:
        LODWORD(v19) = dword_1802D6DC4;
        v16 = &CURL::m_csHttps;
        break;
      case 8:
        LODWORD(v19) = dword_1802D6DF4;
        v16 = &CURL::m_csWinRt;
        break;
      case 9:
        LODWORD(v19) = dword_1802D6E0C;
        v16 = &CURL::m_csCSC;
        break;
      default:
        LODWORD(v19) = dword_1802D6E24;
        break;
    }
  }
  else
  {
    LODWORD(v19) = dword_1802D6DDC;
    v16 = &CURL::m_csFile;
  }
  if ( (_DWORD)v17 != (_DWORD)v19
    || (unsigned int)NCompareStrings(1u, (const wchar_t *)v18[1], v17, (const wchar_t *)v16[1], v17, v17)
    || !(unsigned int)CPathExpression::Check(
                        *((CPathExpression **)this + 174),
                        (const struct CLMSubStr *)&p_pv,
                        *((_DWORD *)this + 232)) )
  {
    return 1;
  }
  if ( !*((_DWORD *)this + 230) )
  {
    v43 = 0;
    v32 = (const wchar_t *)*((_QWORD *)ppszPath + 1);
    v74 = &CLMString::`vftable';
    Str = (LPWSTR)&v78;
    v76 = 65;
    CLMString::AssignInConstructor((CLMString *)&v74, v32, 0xFFFFFFFF);
    v74 = (void **)&CCICommonPathString::`vftable';
    LCMapStringW(0x800u, 0x100u, Str, cchSrc, Str, cchSrc);
    v33 = wcsstr(Str, L"indexed");
    LODWORD(v34) = (_DWORD)pv;
    if ( v33 )
      v35 = v33 - Str;
    else
      LODWORD(v35) = (_DWORD)pv;
    v36 = wcsstr(Str, L"appdata");
    if ( v36 )
      v37 = v36 - Str;
    else
      LODWORD(v37) = (_DWORD)pv;
    v38 = wcsstr(Str, L"history");
    if ( v38 )
      v34 = v38 - Str;
    if ( cchSrc )
      v39 = Str[cchSrc - 1];
    else
      v39 = 0;
    if ( (unsigned int)IsSlash(v39) || (_DWORD)v37 != -1 && ((int)v35 > (int)v37 || (int)v34 > (int)v37) )
    {
      v54 = 0;
      v55 = 0;
      std::vector<unique_ptr_bytes_buffer>::vector<unique_ptr_bytes_buffer>(v56);
      v57 = 0;
      v58 = 0;
      v59 = 0;
      v60 = 0;
      v61 = 0;
      v62 = 0;
      v63 = 0;
      v64 = 0;
      v69 = &CLMString::`vftable';
      v70 = v73;
      v71 = 65;
      CLMString::AssignInConstructor((CLMString *)&v69, Str, 0xFFFFFFFF);
      v69 = (void **)&CCICommonPathString::`vftable';
      if ( (unsigned __int8)IsComplexAppDataMatch((CLMString *)&v69) )
      {
        pv = 0;
        p_pv = &pv;
        ppszPath = 0;
        v48 = 1;
        v40 = SHGetKnownFolderPath(&FOLDERID_UserProfiles, 0, 0, &ppszPath) >= 0;
        if ( v48 )
          wistd::unique_ptr<wchar_t,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
            p_pv,
            ppszPath);
        if ( v40 )
        {
          v80 = (wchar_t *)&v82;
          v81 = 193;
          v82 = 0;
          v79 = &TLMString<192,64,32767>::`vftable';
          if ( (int)IndexedVolumeIdUrlFromCurrentUrlWrap(*((_QWORD *)this + 83), pv, &v79, v41) >= 0 )
          {
            v69 = &CLMString::`vftable';
            v70 = v73;
            v71 = 65;
            CLMString::AssignInConstructor((CLMString *)&v69, v80, 0xFFFFFFFF);
            v69 = (void **)&CCICommonPathString::`vftable';
            v42 = *((_QWORD *)this + 174) + 24LL;
            LODWORD(p_pv) = 0;
            HIDWORD(p_pv) = v72;
            ppszPath = (PWSTR)&v69;
            if ( *(_DWORD *)(v42 + 20) >= v72 )
            {
              CLMString::Mid(v42, v53, 0);
              if ( (unsigned int)CLMSubStr::operator==(v53, &p_pv) )
              {
                v53[0] = v68;
                matched = std::match_results<wchar_t const *>::match_results<wchar_t const *>(v68, &v54);
                v65[0] = &CLMString::`vftable';
                v65[1] = &v67;
                v66 = 65;
                CLMString::AssignInConstructor((CLMString *)v65, Str, 0xFFFFFFFF);
                v65[0] = &CCICommonPathString::`vftable';
                if ( !(unsigned __int8)IsNestedAppDataMatchUnderProfile(v65, matched) )
                  v43 = 1;
              }
            }
            TLMString<64,64,32767>::~TLMString<64,64,32767>(&v69);
          }
          TLMString<192,64,32767>::~TLMString<192,64,32767>(&v79);
        }
        v31 = pv;
        pv = 0;
        if ( v31 )
          CoTaskMemFree(v31);
      }
      std::vector<CPriorityQueue::SPriorityWID>::_Tidy(v56);
    }
    TLMString<64,64,32767>::~TLMString<64,64,32767>(&v74);
    if ( v43 )
      return 1;
  }
  *v49 = *((_DWORD *)this + 230);
  v23 = v50;
  if ( v50 )
  {
    (*(void (__fastcall **)(CSitePath *))(*(_QWORD *)this + 8LL))(this);
    *v23 = (CSitePath *)((char *)this + 16);
  }
  if ( v51 )
    *v51 = *((_DWORD *)this + 338);
  if ( v52 )
    *v52 = *((_DWORD *)this + 339);
  if ( a8 )
  {
    if ( !*((_DWORD *)this + 230) || !*((_DWORD *)this + 343) )
      v13 = 0;
    *a8 = v13;
  }
  return 0;
}

```

## disassembly

```asm
0x180015130  mov     [rsp-8+arg_18], rbx
0x180015135  push    rbp
0x180015136  push    rsi
0x180015137  push    rdi
0x180015138  push    r12
0x18001513a  push    r13
0x18001513c  push    r14
0x18001513e  push    r15
0x180015140  lea     rbp, [rsp-3F0h]
0x180015148  sub     rsp, 4F0h
0x18001514f  mov     rax, cs:__security_cookie
0x180015156  xor     rax, rsp
0x180015159  mov     [rbp+420h+var_40], rax
0x180015160  mov     rax, r8
0x180015163  mov     [rsp+520h+var_4D0], rax
0x180015168  mov     rbx, rdx
0x18001516b  mov     r14, rcx
0x18001516e  mov     rcx, [rbp+420h+arg_20]
0x180015175  mov     [rsp+520h+var_4C0], rcx
0x18001517a  mov     rcx, [rbp+420h+arg_28]
0x180015181  mov     [rsp+520h+var_4C8], rcx
0x180015186  mov     rcx, [rbp+420h+arg_30]
0x18001518d  mov     [rsp+520h+var_4B8], rcx
0x180015192  mov     r12, [rbp+420h+arg_38]
0x180015199  test    rdx, rdx
0x18001519c  jz      loc_180015ACA
0x1800151a2  test    rax, rax
0x1800151a5  jz      loc_180015ACA
0x1800151ab  xor     r13d, r13d
0x1800151ae  test    r12, r12
0x1800151b1  jz      short loc_1800151B7
0x1800151b3  mov     [r12], r13d
0x1800151b7  movzx   eax, word ptr [rdx+1CEh]
0x1800151be  mov     r15d, 0FFF7h
0x1800151c4  test    al, 8
0x1800151c6  jz      loc_18001531A
0x1800151cc  and     ax, r15w
0x1800151d0  mov     [rdx+1CEh], ax
0x1800151d7  mov     rcx, rbx; this
0x1800151da  call    ?ParseHost@CURL@@IEAAXXZ; CURL::ParseHost(void)
0x1800151df  lea     rdi, [rbx+1C2h]
0x1800151e6  movzx   eax, word ptr [rbx+1C6h]
0x1800151ed  sub     ax, [rdi]
0x1800151f0  mov     [rbx+1C4h], ax
0x1800151f7  movzx   ecx, word ptr [rbx+1C4h]
0x1800151fe  mov     esi, 1
0x180015203  test    cx, cx
0x180015206  jz      loc_18001599B
0x18001520c  movzx   edx, word ptr [rdi]
0x18001520f  lea     r9, [rdx+rcx]
0x180015213  cmp     r9, rdx
0x180015216  jb      loc_180015A41
0x18001521c  lea     r8, [rbx+18h]
0x180015220  mov     eax, [r8+14h]
0x180015224  cmp     r9, rax
0x180015227  ja      loc_180015A47
0x18001522d  mov     dword ptr [rsp+520h+var_4E8], edx
0x180015231  mov     dword ptr [rsp+520h+var_4E8+4], ecx
0x180015235  mov     [rsp+520h+ppszPath], r8
0x18001523a  mov     rcx, rbx; this
0x18001523d  call    ?ParseAccessType@CURL@@IEAAXXZ; CURL::ParseAccessType(void)
0x180015242  cmp     [rbx+1B8h], r13w
0x18001524a  jz      loc_180015326
0x180015250  mov     rcx, rbx; this
0x180015253  call    ?ParseAccessType@CURL@@IEAAXXZ; CURL::ParseAccessType(void)
0x180015258  movzx   ecx, word ptr [rbx+1B8h]
0x18001525f  lea     r15, ?m_csInvalid@CURL@@2VCConstString@@A; CConstString CURL::m_csInvalid
0x180015266  mov     r13d, 0FFFFFFFFh
0x18001526c  mov     [rsp+520h+pv], r13
0x180015271  test    ecx, ecx
0x180015273  jnz     loc_180015402
0x180015279  mov     edi, cs:dword_1802D6DDC
0x18001527f  lea     r13, ?m_csFile@CURL@@2VCConstString@@A; CConstString CURL::m_csFile
0x180015286  lea     rcx, [r14+50h]; this
0x18001528a  call    ?ParseAccessType@CURL@@IEAAXXZ; CURL::ParseAccessType(void)
0x18001528f  movzx   ecx, word ptr [r14+208h]
0x180015297  test    ecx, ecx
0x180015299  jnz     loc_18001546B
0x18001529f  mov     eax, cs:dword_1802D6DDC
0x1800152a5  lea     r15, ?m_csFile@CURL@@2VCConstString@@A; CConstString CURL::m_csFile
0x1800152ac  cmp     edi, eax
0x1800152ae  jnz     short loc_1800152EE
0x1800152b0  mov     [rsp+520h+cchDest], edi; unsigned int
0x1800152b4  mov     dword ptr [rsp+520h+lpDestStr], edi; unsigned int
0x1800152b8  mov     r9, [r15+8]; wchar_t *
0x1800152bc  mov     r8d, edi; unsigned int
0x1800152bf  mov     rdx, [r13+8]; String1
0x1800152c3  mov     ecx, esi; dwCmpFlags
0x1800152c5  call    ?NCompareStrings@@YAHKPEB_WK0KK@Z; NCompareStrings(ulong,wchar_t const *,ulong,wchar_t const *,ulong,ulong)
0x1800152ca  test    eax, eax
0x1800152cc  jnz     short loc_1800152EE
0x1800152ce  mov     r8d, [r14+3A0h]; int
0x1800152d5  lea     rdx, [rsp+520h+var_4E8]; struct CLMSubStr *
0x1800152da  mov     rcx, [r14+570h]; this
0x1800152e1  call    ?Check@CPathExpression@@QEAAHAEBVCLMSubStr@@H@Z; CPathExpression::Check(CLMSubStr const &,int)
0x1800152e6  test    eax, eax
0x1800152e8  jnz     loc_1800153A2
0x1800152ee  mov     eax, esi
0x1800152f0  mov     rcx, [rbp+420h+var_40]
0x1800152f7  xor     rcx, rsp; StackCookie
0x1800152fa  call    __security_check_cookie
0x1800152ff  mov     rbx, [rsp+520h+arg_18]
0x180015307  add     rsp, 4F0h
0x18001530e  pop     r15
0x180015310  pop     r14
0x180015312  pop     r13
0x180015314  pop     r12
0x180015316  pop     rdi
0x180015317  pop     rsi
0x180015318  pop     rbp
0x180015319  retn
0x18001531a  lea     rdi, [rdx+1C2h]
0x180015321  jmp     loc_1800151F7
0x180015326  movzx   eax, word ptr [rbx+1CEh]
0x18001532d  test    al, 8
0x18001532f  jz      short loc_180015355
0x180015331  and     ax, r15w
0x180015335  mov     [rbx+1CEh], ax
0x18001533c  mov     rcx, rbx; this
0x18001533f  call    ?ParseHost@CURL@@IEAAXXZ; CURL::ParseHost(void)
0x180015344  movzx   eax, word ptr [rbx+1C6h]
0x18001534b  sub     ax, [rdi]
0x18001534e  mov     [rbx+1C4h], ax
0x180015355  cmp     [rbx+1B8h], r13w
0x18001535d  jnz     short loc_18001536D
0x18001535f  cmp     [rbx+1BCh], r13w
0x180015367  jz      loc_180015250
0x18001536d  mov     edx, 2; unsigned int
0x180015372  lea     rcx, [rsp+520h+var_4E8]; this
0x180015377  call    ?ReduceLeft@CLMSubStr@@QEAAXI@Z; CLMSubStr::ReduceLeft(uint)
0x18001537c  xor     edx, edx; unsigned int
0x18001537e  lea     rcx, [rsp+520h+var_4E8]; this
0x180015383  call    ?FindAnySlash@CLMSubStr@@QEBAHI@Z; CLMSubStr::FindAnySlash(uint)
0x180015388  cmp     eax, 0FFFFFFFFh
0x18001538b  jz      loc_1800152EE
0x180015391  mov     edx, eax; unsigned int
0x180015393  lea     rcx, [rsp+520h+var_4E8]; this
0x180015398  call    ?ReduceLeft@CLMSubStr@@QEAAXI@Z; CLMSubStr::ReduceLeft(uint)
0x18001539d  jmp     loc_180015250
0x1800153a2  cmp     dword ptr [r14+398h], 0
0x1800153aa  jz      loc_180015667
0x1800153b0  mov     eax, [r14+398h]
0x1800153b7  mov     rcx, [rsp+520h+var_4D0]
0x1800153bc  mov     [rcx], eax
0x1800153be  mov     rbx, [rsp+520h+var_4C8]
0x1800153c3  test    rbx, rbx
0x1800153c6  jnz     loc_180015583
0x1800153cc  mov     rcx, [rsp+520h+var_4C0]
0x1800153d1  test    rcx, rcx
0x1800153d4  jz      short loc_1800153DF
0x1800153d6  mov     eax, [r14+548h]
0x1800153dd  mov     [rcx], eax
0x1800153df  mov     rcx, [rsp+520h+var_4B8]
0x1800153e4  test    rcx, rcx
0x1800153e7  jz      short loc_1800153F2
0x1800153e9  mov     eax, [r14+54Ch]
0x1800153f0  mov     [rcx], eax
0x1800153f2  test    r12, r12
0x1800153f5  jnz     loc_1800154D2
0x1800153fb  xor     eax, eax
0x1800153fd  jmp     loc_1800152F0
0x180015402  sub     ecx, esi
0x180015404  jz      loc_180015A78
0x18001540a  sub     ecx, 5
0x18001540d  jnz     loc_1800154F1
0x180015413  cmp     [rbx+2Ch], ecx
0x180015416  jbe     loc_18001559E
0x18001541c  mov     edx, 3Ah ; ':'; Ch
0x180015421  mov     rcx, [rbx+20h]; Str
0x180015425  call    cs:__imp_wcschr
0x18001542b  mov     rdi, rax
0x18001542e  test    rax, rax
0x180015431  jz      loc_180015535
0x180015437  sub     rdi, [rbx+20h]
0x18001543b  sar     rdi, 1
0x18001543e  lea     r13, [rbx+18h]
0x180015442  cmp     edi, [r13+14h]
0x180015446  jbe     loc_180015286
0x18001544c  mov     rcx, [rbp+428h]; this
0x180015453  mov     r9d, 0CEh; char *
0x180015459  lea     r8, aOnecoreuapBase_240; "onecoreuap\\base\\appmodel\\Search\\com"...
0x180015460  mov     edx, 40Ch; void *
0x180015465  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18001546b  sub     ecx, esi
0x18001546d  jz      loc_180015A9C
0x180015473  sub     ecx, 5
0x180015476  jnz     loc_180015513
0x18001547c  cmp     [r14+7Ch], ecx
0x180015480  jbe     loc_1800155A6
0x180015486  mov     edx, 3Ah ; ':'; Ch
0x18001548b  mov     rcx, [r14+70h]; Str
0x18001548f  call    cs:__imp_wcschr
0x180015495  test    rax, rax
0x180015498  jz      loc_18001553D
0x18001549e  sub     rax, [r14+70h]
0x1800154a2  sar     rax, 1
0x1800154a5  lea     r15, [r14+68h]
0x1800154a9  cmp     eax, [r15+14h]
0x1800154ad  jbe     loc_1800152AC
0x1800154b3  mov     rcx, [rbp+428h]; this
0x1800154ba  mov     r9d, 0CEh; char *
0x1800154c0  lea     r8, aOnecoreuapBase_240; "onecoreuap\\base\\appmodel\\Search\\com"...
0x1800154c7  mov     edx, 40Ch; void *
0x1800154cc  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800154d2  cmp     dword ptr [r14+398h], 0
0x1800154da  jz      short loc_1800154E6
0x1800154dc  cmp     dword ptr [r14+55Ch], 0
0x1800154e4  jnz     short loc_1800154E8
0x1800154e6  xor     esi, esi
0x1800154e8  mov     [r12], esi
0x1800154ec  jmp     loc_1800153FB
0x1800154f1  sub     ecx, esi
0x1800154f3  jz      loc_180015A66
0x1800154f9  sub     ecx, esi
0x1800154fb  jz      short loc_180015554
0x1800154fd  cmp     ecx, esi
0x1800154ff  jnz     short loc_180015546
0x180015501  mov     edi, cs:dword_1802D6E0C
0x180015507  lea     r13, ?m_csCSC@CURL@@2VCConstString@@A; CConstString CURL::m_csCSC
0x18001550e  jmp     loc_180015286
0x180015513  sub     ecx, esi
0x180015515  jz      loc_180015A8A
0x18001551b  sub     ecx, esi
0x18001551d  jz      short loc_180015571
0x18001551f  cmp     ecx, esi
0x180015521  jnz     short loc_180015566
0x180015523  mov     eax, cs:dword_1802D6E0C
0x180015529  lea     r15, ?m_csCSC@CURL@@2VCConstString@@A; CConstString CURL::m_csCSC
0x180015530  jmp     loc_1800152AC
0x180015535  mov     edi, r13d
0x180015538  jmp     loc_18001543E
0x18001553d  mov     eax, dword ptr [rsp+520h+pv]
0x180015541  jmp     loc_1800154A5
0x180015546  mov     edi, cs:dword_1802D6E24
0x18001554c  mov     r13, r15
0x18001554f  jmp     loc_180015286
0x180015554  mov     edi, cs:dword_1802D6DF4
0x18001555a  lea     r13, ?m_csWinRt@CURL@@2VCConstString@@A; CConstString CURL::m_csWinRt
0x180015561  jmp     loc_180015286
0x180015566  mov     eax, cs:dword_1802D6E24
0x18001556c  jmp     loc_1800152AC
0x180015571  mov     eax, cs:dword_1802D6DF4
0x180015577  lea     r15, ?m_csWinRt@CURL@@2VCConstString@@A; CConstString CURL::m_csWinRt
0x18001557e  jmp     loc_1800152AC
0x180015583  mov     rax, [r14]
0x180015586  mov     rcx, r14
0x180015589  mov     rax, [rax+8]
0x18001558d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015592  lea     rax, [r14+10h]
0x180015596  mov     [rbx], rax
0x180015599  jmp     loc_1800153CC
0x18001559e  mov     edi, r13d
0x1800155a1  jmp     loc_18001543E
0x1800155a6  mov     eax, dword ptr [rsp+520h+pv]
0x1800155aa  jmp     loc_1800154A5
0x1800155af  lea     rax, [rbp+420h+var_390]
0x1800155b6  mov     [rsp+520h+var_4B0], rax
0x1800155bb  lea     rdx, [rbp+420h+var_4A0]
0x1800155bf  lea     rcx, [rbp+420h+var_390]
0x1800155c6  call    ??0?$match_results@PEB_WV?$allocator@V?$sub_match@PEB_W@std@@@std@@@std@@QEAA@AEBV01@@Z; std::match_results<wchar_t const *>::match_results<wchar_t const *>(std::match_results<wchar_t const *> const &)
0x1800155cb  mov     rbx, rax
0x1800155ce  mov     [rbp+420h+var_430], rdi
0x1800155d2  lea     rax, [rbp+420h+var_418]
0x1800155d6  mov     [rbp+420h+var_428], rax
0x1800155da  mov     [rbp+420h+var_420], 41h ; 'A'
0x1800155e1  mov     r8d, 0FFFFFFFFh; unsigned int
0x1800155e7  mov     rdx, [rbp+420h+Str]; wchar_t *
0x1800155ee  lea     rcx, [rbp+420h+var_430]; this
0x1800155f2  call    ?AssignInConstructor@CLMString@@IEAAHPEB_WI@Z; CLMString::AssignInConstructor(wchar_t const *,uint)
0x1800155f7  mov     [rbp+420h+var_430], r15
0x1800155fb  mov     rdx, rbx
0x1800155fe  lea     rcx, [rbp+420h+var_430]
0x180015602  call    ?IsNestedAppDataMatchUnderProfile@@YA_NV?$TLMString@$0EA@$0EA@$0HPPP@@@V?$match_results@PEB_WV?$allocator@V?$sub_match@PEB_W@std@@@std@@@std@@@Z; IsNestedAppDataMatchUnderProfile(TLMString<64,64,32767>,std::match_results<wchar_t const *>)
0x180015607  test    al, al
0x180015609  jz      loc_180015AC2
0x18001560f  lea     rcx, [rbp+420h+var_320]
0x180015616  call    ??1?$TLMString@$0EA@$0EA@$0HPPP@@@UEAA@XZ; TLMString<64,64,32767>::~TLMString<64,64,32767>(void)
0x18001561b  nop
0x18001561c  lea     rcx, [rbp+420h+var_1E0]; void *
0x180015623  call    ??1?$TLMString@$0MA@$0EA@$0HPPP@@@UEAA@XZ; TLMString<192,64,32767>::~TLMString<192,64,32767>(void)
0x180015628  nop
0x180015629  mov     rcx, [rsp+520h+pv]; pv
0x18001562e  mov     [rsp+520h+pv], 0
0x180015637  test    rcx, rcx
0x18001563a  jz      short loc_180015643
0x18001563c  call    cs:__imp_CoTaskMemFree
0x180015642  nop
0x180015643  lea     rcx, [rbp+420h+var_490]
0x180015647  call    ?_Tidy@?$vector@USPriorityWID@CPriorityQueue@@V?$allocator@USPriorityWID@CPriorityQueue@@@std@@@std@@AEAAXXZ; std::vector<CPriorityQueue::SPriorityWID>::_Tidy(void)
0x18001564c  nop
0x18001564d  lea     rcx, [rbp+420h+var_280]
0x180015654  call    ??1?$TLMString@$0EA@$0EA@$0HPPP@@@UEAA@XZ; TLMString<64,64,32767>::~TLMString<64,64,32767>(void)
0x180015659  test    r13b, r13b
0x18001565c  jnz     loc_1800152EE
0x180015662  jmp     loc_1800153B0
0x180015667  xor     r13b, r13b
0x18001566a  mov     rax, [rsp+520h+ppszPath]
0x18001566f  mov     rdx, [rax+8]; wchar_t *
0x180015673  lea     rax, ??_7CLMString@@6B@; const CLMString::`vftable'
0x18001567a  mov     [rbp+420h+var_280], rax
  ... truncated ...
```
