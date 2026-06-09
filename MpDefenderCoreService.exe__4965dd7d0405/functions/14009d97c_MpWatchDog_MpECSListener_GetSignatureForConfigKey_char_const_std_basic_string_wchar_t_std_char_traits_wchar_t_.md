# MpWatchDog::MpECSListener::GetSignatureForConfigKey(char const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &)

- ea: `0x14009d97c`
- end: `0x14009e034`
- name: `?GetSignatureForConfigKey@MpECSListener@MpWatchDog@@AEAA_NPEBDAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV34@@Z`
- size: `1720`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config`

## callers

- `0x14009e52c`

## callees

- `0x14003a5c0`
- `0x14007d1e0`
- `0x14007e088`
- `0x140081fc8`
- `0x1400833d4`
- `0x140084a18`
- `0x140085218`
- `0x140085d38`
- `0x14008d34c`
- `0x14009d540`
- `0x14009d97c`
- `0x1400a28f0`
- `0x1400f9e78`
- `0x1400fab00`
- `0x1400fb44c`
- `0x1400fd420`
- `0x140166250`
- `0x140166990`

## import_xrefs

- `KERNEL32!DebugBreak` at `0x14009daaa`
- `KERNEL32!DebugBreak` at `0x14009daaa`

## string_xrefs

- `0x14009da00`: `__ConfigSignatures__`
- `0x14009dfaa`: `Left-over characters in stream after parsing a JSON value`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
char __fastcall MpWatchDog::MpECSListener::GetSignatureForConfigKey(__int64 a1, _BYTE *a2, _QWORD *a3, void *a4)
{
  __int64 v5; // rdi
  __int64 (__fastcall *v6)(__int64, _OWORD *, _OWORD *, __int128 *); // rsi
  size_t v7; // r8
  char v8; // bl
  MpWatchDog *v9; // rcx
  unsigned int v10; // r8d
  char result; // al
  __int64 v12; // r13
  unsigned __int8 *v13; // rdi
  unsigned __int8 *v14; // r15
  unsigned __int64 v15; // r12
  __int64 v16; // rbx
  unsigned __int8 *v17; // rdi
  __int64 v18; // rax
  unsigned __int8 *i; // rcx
  char *v20; // r14
  char *v21; // rcx
  unsigned __int8 *v22; // rbx
  __int64 v23; // rcx
  unsigned __int8 *v24; // rax
  unsigned __int8 *v25; // rax
  unsigned __int8 *v26; // rax
  unsigned __int8 *v27; // rax
  unsigned __int8 *v28; // rax
  __int64 *v29; // rax
  __int64 v30; // rdi
  int v31; // eax
  __int64 v32; // rax
  _QWORD *v33; // r14
  __int64 v34; // rax
  __int64 v35; // rbx
  __int64 v36; // r8
  __int64 v37; // rdx
  __int64 v38; // rdx
  __int64 v39; // r8
  __int64 v40; // rdx
  __int64 v41; // rdx
  __int64 v42; // r8
  __int64 v43; // rax
  __int64 v44; // [rsp+30h] [rbp-268h] BYREF
  __int64 v45; // [rsp+38h] [rbp-260h]
  char v46[8]; // [rsp+40h] [rbp-258h] BYREF
  _OWORD v47[2]; // [rsp+48h] [rbp-250h] BYREF
  _QWORD *v48; // [rsp+68h] [rbp-230h]
  void *v49; // [rsp+70h] [rbp-228h]
  _OWORD v50[2]; // [rsp+78h] [rbp-220h] BYREF
  const web::json::json_exception *v51; // [rsp+98h] [rbp-200h] BYREF
  _BYTE v52[256]; // [rsp+A0h] [rbp-1F8h] BYREF
  __int128 v53; // [rsp+1A0h] [rbp-F8h] BYREF
  __int64 v54; // [rsp+1B0h] [rbp-E8h]
  unsigned __int64 v55; // [rsp+1B8h] [rbp-E0h]
  int v56; // [rsp+1C0h] [rbp-D8h] BYREF
  __int128 v57; // [rsp+1C8h] [rbp-D0h] BYREF
  __int64 v58; // [rsp+1D8h] [rbp-C0h]
  __int64 v59; // [rsp+1E0h] [rbp-B8h]
  int v60; // [rsp+208h] [rbp-90h] BYREF
  void ***v61; // [rsp+210h] [rbp-88h]
  _QWORD v62[7]; // [rsp+220h] [rbp-78h] BYREF

  v49 = a4;
  v48 = a3;
  LODWORD(v44) = 0;
  v53 = 0;
  v54 = 0;
  v55 = 15;
  LOBYTE(v53) = 0;
  v5 = *(_QWORD *)(a1 + 176);
  v6 = *(__int64 (__fastcall **)(__int64, _OWORD *, _OWORD *, __int128 *))(*(_QWORD *)v5 + 152LL);
  memset(v47, 0, sizeof(v47));
  try
  {
    std::string::_Construct<1,char const *>(v47, "__ConfigSignatures__", 0x14u);
    memset(v50, 0, sizeof(v50));
    v7 = -1;
    do
      ++v7;
    while ( a2[v7] );
    std::string::_Construct<1,char const *>(v50, a2, v7);
    v8 = v6(v5, v50, v47, &v53);
    std::string::_Tidy_deallocate(v50);
    std::string::_Tidy_deallocate(v47);
    if ( MpWatchDog::MpIsCoreSvcInDevMode(v9) )
    {
      if ( v8 )
      {
        if ( !byte_1401E7360 && MpWatchDog::GetMiscConfigDword((HKEY)&stru_1401978F0, 0, v10) == 1 )
        {
          byte_1401E7360 = 1;
          DebugBreak();
        }
LABEL_13:
        v12 = v54;
        if ( v54 )
        {
          v13 = (unsigned __int8 *)&v53;
          v14 = (unsigned __int8 *)v53;
          v15 = v55;
          if ( v55 > 0xF )
            v13 = (unsigned __int8 *)v53;
          memset(v52, 0, sizeof(v52));
          v20 = " \t\n\r";
          v21 = " \t\n\r";
          do
            v52[(unsigned __int8)*v21++] = 1;
          while ( v21 != "" );
          v22 = v13;
          if ( v13 >= &v13[v12] )
          {
LABEL_17:
            v16 = -1;
          }
          else
          {
            while ( v52[*v22] )
            {
              if ( ++v22 >= &v13[v12] )
                goto LABEL_17;
            }
            v16 = v22 - v13;
          }
          v17 = (unsigned __int8 *)&v53;
          if ( v15 > 0xF )
            v17 = v14;
          v18 = v12 - 1;
          if ( !v12 )
            v18 = -1;
          v45 = v18;
          memset(v52, 0, sizeof(v52));
          do
            v52[(unsigned __int8)*v20++] = 1;
          while ( v20 != "" );
          for ( i = &v17[v45]; ; --i )
          {
            if ( !v52[*i] )
            {
              v23 = i - v17;
              goto LABEL_35;
            }
            if ( i == v17 )
              break;
          }
          v23 = -1;
LABEL_35:
          if ( v16 != -1 && v23 != -1 )
          {
            v24 = (unsigned __int8 *)&v53;
            if ( v15 > 0xF )
              v24 = v14;
            if ( v24[v16] == 123 )
            {
              v25 = (unsigned __int8 *)&v53;
              if ( v15 > 0xF )
                v25 = v14;
              if ( v25[v23] == 125 )
                goto LABEL_49;
            }
            v26 = (unsigned __int8 *)&v53;
            if ( v15 > 0xF )
              v26 = v14;
            if ( v26[v16] == 91 )
            {
              v27 = (unsigned __int8 *)&v53;
              if ( v15 > 0xF )
                v27 = v14;
              if ( v27[v23] == 93 )
              {
LABEL_49:
                v45 = 0;
                v62[1] = 1;
                v62[2] = 1;
                v62[3] = 0;
                v62[0] = &web::json::details::JSON_StringParser<char>::`vftable';
                v28 = (unsigned __int8 *)&v53;
                if ( v15 > 0xF )
                  v28 = v14;
                v62[4] = v28;
                v62[5] = v28;
                v62[6] = &v28[v12];
                v56 = 0;
                v57 = 0;
                v58 = 0;
                v59 = 15;
                LOBYTE(v57) = 0;
                v60 = 0;
                v61 = &`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static;
                web::json::details::JSON_Parser<char>::GetNextToken(v62, &v56);
                if ( v60 )
                {
                  v40 = std::error_code::message(&v60, v47);
                  v41 = utility::conversions::to_string_t(v50, v40);
                  web::json::details::CreateException<web::json::details::JSON_Parser<char>::Token>(
                    (__int64)&v56,
                    v41,
                    v42);
                }
                v45 = 0;
                v29 = (__int64 *)web::json::details::JSON_Parser<char>::_ParseValue(v62, v46, &v56);
                v30 = *v29;
                *v29 = 0;
                v45 = v30;
                LODWORD(v44) = 6;
                if ( v60 )
                {
                  v37 = std::error_code::message(&v60, v47);
                  v38 = utility::conversions::to_string_t(v50, v37);
                  web::json::details::CreateException<web::json::details::JSON_Parser<char>::Token>(
                    (__int64)&v56,
                    v38,
                    v39);
                }
                if ( v56 )
                {
                  std::wstring::wstring(v47, L"Left-over characters in stream after parsing a JSON value");
                  web::json::details::CreateException<web::json::details::JSON_Parser<char>::Token>(
                    (__int64)&v56,
                    (__int64)v47,
                    v36);
                }
                std::string::_Tidy_deallocate(&v57);
                v31 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v30 + 88LL))(v30);
                if ( v31 == 3 )
                {
                  v44 = 0;
                  v32 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v30 + 168LL))(v30);
                  v33 = v48;
                  web::json::object::find_by_key(v32, &v44, v48);
                  v34 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v30 + 168LL))(v30);
                  v35 = v44;
                  if ( v44 == *(_QWORD *)(v34 + 8)
                    || (*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)(v44 + 32) + 88LL))(*(_QWORD *)(v44 + 32)) != 2 )
                  {
                    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
                    {
                      if ( v33[3] > 7u )
                        v33 = (_QWORD *)*v33;
                      WPP_SF_S(
                        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                        59,
                        &WPP_2302b92dd89c3f461ef1ff1dfe596bd8_Traceguids,
                        v33);
                    }
                    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v30 + 192LL))(v30, 1);
                    std::string::_Tidy_deallocate(&v53);
                    return 0;
                  }
                  else
                  {
                    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v35 + 32) + 176LL))(*(_QWORD *)(v35 + 32));
                    std::wstring::operator=(v49);
                    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v30 + 192LL))(v30, 1);
                    std::string::_Tidy_deallocate(&v53);
                    return 1;
                  }
                }
                else
                {
                  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
                  {
                    WPP_SF_(
                      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                      58,
                      &WPP_2302b92dd89c3f461ef1ff1dfe596bd8_Traceguids);
                  }
                  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v30 + 192LL))(v30, 1);
                  std::string::_Tidy_deallocate(&v53);
                  return 0;
                }
              }
            }
          }
        }
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 57, &WPP_2302b92dd89c3f461ef1ff1dfe596bd8_Traceguids);
LABEL_12:
        std::string::_Tidy_deallocate(&v53);
        return 0;
      }
    }
    else if ( v8 )
    {
      goto LABEL_13;
    }
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 56, &WPP_2302b92dd89c3f461ef1ff1dfe596bd8_Traceguids);
    goto LABEL_12;
  }
  catch ( const web::json::json_exception *v51 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v43 = (*(__int64 (__fastcall **)(const web::json::json_exception *))(*(_QWORD *)v51 + 8LL))(v51);
      WPP_SF_s(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 60, &WPP_2302b92dd89c3f461ef1ff1dfe596bd8_Traceguids, v43);
    }
    return 0;
  }
  catch ( ... )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 61, &WPP_2302b92dd89c3f461ef1ff1dfe596bd8_Traceguids);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x14009d97c  push    rbx
0x14009d97e  push    rsi
0x14009d97f  push    rdi
0x14009d980  push    r12
0x14009d982  push    r13
0x14009d984  push    r14
0x14009d986  push    r15
0x14009d988  sub     rsp, 260h
0x14009d98f  mov     rax, cs:__security_cookie
0x14009d996  xor     rax, rsp
0x14009d999  mov     [rsp+298h+var_40], rax
0x14009d9a1  mov     [rsp+298h+var_228], r9
0x14009d9a6  mov     [rsp+298h+var_230], r8
0x14009d9ab  mov     rbx, rdx
0x14009d9ae  xor     r14d, r14d
0x14009d9b1  mov     dword ptr [rsp+298h+var_268], r14d
0x14009d9b6  xorps   xmm0, xmm0
0x14009d9b9  movups  [rsp+298h+var_F8], xmm0
0x14009d9c1  mov     [rsp+298h+var_E8], r14
0x14009d9c9  mov     [rsp+298h+var_E0], 0Fh
0x14009d9d5  mov     byte ptr [rsp+298h+var_F8], r14b
0x14009d9dd  mov     rdi, [rcx+0B0h]
0x14009d9e4  mov     rax, [rdi]
0x14009d9e7  mov     rsi, [rax+98h]
0x14009d9ee  movups  [rsp+298h+var_250], xmm0
0x14009d9f3  xorps   xmm1, xmm1
0x14009d9f6  movdqu  [rsp+298h+var_240], xmm1
0x14009d9fc  lea     r8d, [r14+14h]
0x14009da00  lea     rdx, aConfigsignatur; "__ConfigSignatures__"
0x14009da07  lea     rcx, [rsp+298h+var_250]
0x14009da0c  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x14009da11  nop
0x14009da12  xorps   xmm0, xmm0
0x14009da15  movups  [rsp+298h+var_220], xmm0
0x14009da1a  xorps   xmm1, xmm1
0x14009da1d  movdqu  [rsp+298h+var_210], xmm1
0x14009da26  or      r8, 0FFFFFFFFFFFFFFFFh
0x14009da2a  inc     r8
0x14009da2d  cmp     [rbx+r8], r14b
0x14009da31  jnz     short loc_14009DA2A
0x14009da33  mov     rdx, rbx
0x14009da36  lea     rcx, [rsp+298h+var_220]
0x14009da3b  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x14009da40  nop
0x14009da41  lea     r9, [rsp+298h+var_F8]
0x14009da49  lea     r8, [rsp+298h+var_250]
0x14009da4e  lea     rdx, [rsp+298h+var_220]
0x14009da53  mov     rcx, rdi
0x14009da56  mov     rax, rsi
0x14009da59  call    cs:__guard_dispatch_icall_fptr
0x14009da5f  mov     bl, al
0x14009da61  lea     rcx, [rsp+298h+var_220]
0x14009da66  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x14009da6b  nop
0x14009da6c  lea     rcx, [rsp+298h+var_250]
0x14009da71  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x14009da76  call    ?MpIsCoreSvcInDevMode@MpWatchDog@@YA_NXZ; MpWatchDog::MpIsCoreSvcInDevMode(void)
0x14009da7b  test    al, al
0x14009da7d  jz      short loc_14009DAB2
0x14009da7f  test    bl, bl
0x14009da81  jz      short loc_14009DAB6
0x14009da83  cmp     cs:byte_1401E7360, r14b
0x14009da8a  jnz     short loc_14009DAF9
0x14009da8c  xor     edx, edx; wchar_t *
0x14009da8e  lea     rcx, stru_1401978F0; this
0x14009da95  call    ?GetMiscConfigDword@MpWatchDog@@YAKPEB_WK@Z; MpWatchDog::GetMiscConfigDword(wchar_t const *,ulong)
0x14009da9a  mov     esi, 1
0x14009da9f  cmp     eax, esi
0x14009daa1  jnz     short loc_14009DAFE
0x14009daa3  mov     cs:byte_1401E7360, sil
0x14009daaa  call    cs:__imp_DebugBreak
0x14009dab0  jmp     short loc_14009DAFE
0x14009dab2  test    bl, bl
0x14009dab4  jnz     short loc_14009DAF9
0x14009dab6  lea     rax, WPP_GLOBAL_Control
0x14009dabd  mov     rcx, cs:WPP_GLOBAL_Control
0x14009dac4  cmp     rcx, rax
0x14009dac7  jz      short loc_14009DAE5
0x14009dac9  test    byte ptr [rcx+1Ch], 2
0x14009dacd  jz      short loc_14009DAE5
0x14009dacf  mov     edx, 38h ; '8'
0x14009dad4  lea     r8, WPP_2302b92dd89c3f461ef1ff1dfe596bd8_Traceguids
0x14009dadb  mov     rcx, [rcx+10h]
0x14009dadf  call    WPP_SF_
0x14009dae4  nop
0x14009dae5  lea     rcx, [rsp+298h+var_F8]
0x14009daed  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x14009daf2  xor     al, al
0x14009daf4  jmp     loc_14009DF87
0x14009daf9  mov     esi, 1
0x14009dafe  mov     r13, [rsp+298h+var_E8]
0x14009db06  test    r13, r13
0x14009db09  jz      loc_14009DF45
0x14009db0f  lea     rdi, [rsp+298h+var_F8]
0x14009db17  mov     r15, qword ptr [rsp+298h+var_F8]
0x14009db1f  mov     r12, [rsp+298h+var_E0]
0x14009db27  cmp     r12, 0Fh
0x14009db2b  cmova   rdi, r15
0x14009db2f  test    r13, r13
0x14009db32  jnz     short loc_14009DB9F
0x14009db34  lea     r14, asc_140194A18; " \t\n\r"
0x14009db3b  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14009db3f  mov     rbx, rcx
0x14009db42  lea     rdi, [rsp+298h+var_F8]
0x14009db4a  cmp     r12, 0Fh
0x14009db4e  cmova   rdi, r15
0x14009db52  lea     rax, [r13-1]
0x14009db56  cmp     rax, rcx
0x14009db59  cmovnb  rax, rcx
0x14009db5d  mov     [rsp+298h+var_260], rax
0x14009db62  xor     edx, edx; Val
0x14009db64  mov     r8d, 100h; Size
0x14009db6a  lea     rcx, [rsp+298h+var_1F8]; void *
0x14009db72  call    memset
0x14009db77  lea     rcx, asc_140194A18+4; ""
0x14009db7e  movzx   eax, byte ptr [r14]
0x14009db82  mov     [rsp+rax+298h+var_1F8], sil
0x14009db8a  add     r14, rsi
0x14009db8d  cmp     r14, rcx
0x14009db90  jnz     short loc_14009DB7E
0x14009db92  mov     rcx, [rsp+298h+var_260]
0x14009db97  add     rcx, rdi
0x14009db9a  xor     r14d, r14d
0x14009db9d  jmp     short loc_14009DC1A
0x14009db9f  xor     edx, edx; Val
0x14009dba1  mov     r8d, 100h; Size
0x14009dba7  lea     rcx, [rsp+298h+var_1F8]; void *
0x14009dbaf  call    memset
0x14009dbb4  lea     r14, asc_140194A18; " \t\n\r"
0x14009dbbb  mov     rcx, r14
0x14009dbbe  lea     rdx, asc_140194A18+4; ""
0x14009dbc5  movzx   eax, byte ptr [rcx]
0x14009dbc8  mov     [rsp+rax+298h+var_1F8], sil
0x14009dbd0  add     rcx, rsi
0x14009dbd3  cmp     rcx, rdx
0x14009dbd6  jnz     short loc_14009DBC5
0x14009dbd8  mov     rbx, rdi
0x14009dbdb  lea     rcx, [rdi+r13]
0x14009dbdf  cmp     rdi, rcx
0x14009dbe2  jnb     loc_14009DB3B
0x14009dbe8  movzx   eax, byte ptr [rbx]
0x14009dbeb  cmp     [rsp+rax+298h+var_1F8], 0
0x14009dbf3  jz      short loc_14009DC02
0x14009dbf5  add     rbx, rsi
0x14009dbf8  cmp     rbx, rcx
0x14009dbfb  jb      short loc_14009DBE8
0x14009dbfd  jmp     loc_14009DB3B
0x14009dc02  sub     rbx, rdi
0x14009dc05  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14009dc09  jmp     loc_14009DB42
0x14009dc0e  cmp     rcx, rdi
0x14009dc11  jz      loc_14009DDAC
0x14009dc17  sub     rcx, rsi
0x14009dc1a  movzx   eax, byte ptr [rcx]
0x14009dc1d  cmp     [rsp+rax+298h+var_1F8], r14b
0x14009dc25  jnz     short loc_14009DC0E
0x14009dc27  sub     rcx, rdi
0x14009dc2a  or      rax, 0FFFFFFFFFFFFFFFFh
0x14009dc2e  cmp     rbx, rax
0x14009dc31  jz      loc_14009DF45
0x14009dc37  cmp     rcx, rax
0x14009dc3a  jz      loc_14009DF45
0x14009dc40  lea     rax, [rsp+298h+var_F8]
0x14009dc48  mov     edx, 0Fh
0x14009dc4d  cmp     r12, rdx
0x14009dc50  cmova   rax, r15
0x14009dc54  cmp     byte ptr [rax+rbx], 7Bh ; '{'
0x14009dc58  jnz     short loc_14009DC6F
0x14009dc5a  lea     rax, [rsp+298h+var_F8]
0x14009dc62  cmp     r12, rdx
0x14009dc65  cmova   rax, r15
0x14009dc69  cmp     byte ptr [rax+rcx], 7Dh ; '}'
0x14009dc6d  jz      short loc_14009DCA1
0x14009dc6f  lea     rax, [rsp+298h+var_F8]
0x14009dc77  cmp     r12, rdx
0x14009dc7a  cmova   rax, r15
0x14009dc7e  cmp     byte ptr [rax+rbx], 5Bh ; '['
0x14009dc82  jnz     loc_14009DF45
0x14009dc88  lea     rax, [rsp+298h+var_F8]
0x14009dc90  cmp     r12, rdx
0x14009dc93  cmova   rax, r15
0x14009dc97  cmp     byte ptr [rax+rcx], 5Dh ; ']'
0x14009dc9b  jnz     loc_14009DF45
0x14009dca1  mov     [rsp+298h+var_260], r14
0x14009dca6  mov     [rsp+298h+var_70], rsi
0x14009dcae  mov     [rsp+298h+var_68], rsi
0x14009dcb6  mov     [rsp+298h+var_60], r14
0x14009dcbe  lea     rax, ??_7?$JSON_StringParser@D@details@json@web@@6B@; const web::json::details::JSON_StringParser<char>::`vftable'
0x14009dcc5  mov     [rsp+298h+var_78], rax
0x14009dccd  lea     rax, [rsp+298h+var_F8]
0x14009dcd5  cmp     r12, rdx
0x14009dcd8  cmova   rax, r15
0x14009dcdc  mov     [rsp+298h+var_58], rax
0x14009dce4  mov     [rsp+298h+var_50], rax
0x14009dcec  add     rax, r13
0x14009dcef  mov     [rsp+298h+var_48], rax
0x14009dcf7  mov     [rsp+298h+var_D8], r14d
0x14009dcff  xorps   xmm0, xmm0
0x14009dd02  movups  [rsp+298h+var_D0], xmm0
0x14009dd0a  mov     [rsp+298h+var_C0], r14
0x14009dd12  mov     [rsp+298h+var_B8], rdx
0x14009dd1a  mov     byte ptr [rsp+298h+var_D0], r14b
0x14009dd22  mov     [rsp+298h+var_90], r14d
0x14009dd2a  lea     rax, ?_Static@?1???$_Immortalize_memcpy_image@V_System_error_category@std@@@std@@YAAEBV_System_error_category@1@XZ@4U?$_Constexpr_immortalize_impl@V_System_error_category@std@@@1@A; std::_Constexpr_immortalize_impl<std::_System_error_category> `std::_Immortalize_memcpy_image<std::_System_error_category>(void)'::`2'::_Static
0x14009dd31  mov     [rsp+298h+var_88], rax
0x14009dd39  lea     rdx, [rsp+298h+var_D8]
0x14009dd41  lea     rcx, [rsp+298h+var_78]
0x14009dd49  call    ?GetNextToken@?$JSON_Parser@D@details@json@web@@QEAAXAEAUToken@1234@@Z; web::json::details::JSON_Parser<char>::GetNextToken(web::json::details::JSON_Parser<char>::Token &)
0x14009dd4e  cmp     [rsp+298h+var_90], r14d
0x14009dd56  jnz     loc_14009E001
0x14009dd5c  mov     [rsp+298h+var_260], r14
0x14009dd61  lea     r8, [rsp+298h+var_D8]
0x14009dd69  lea     rdx, [rsp+298h+var_258]
0x14009dd6e  lea     rcx, [rsp+298h+var_78]
0x14009dd76  call    ?_ParseValue@?$JSON_Parser@D@details@json@web@@AEAA?AV?$unique_ptr@V_Value@details@json@web@@U?$default_delete@V_Value@details@json@web@@@std@@@std@@AEAUToken@1234@@Z; web::json::details::JSON_Parser<char>::_ParseValue(web::json::details::JSON_Parser<char>::Token &)
0x14009dd7b  mov     rdi, [rax]
0x14009dd7e  mov     [rax], r14
0x14009dd81  mov     [rsp+298h+var_260], rdi
0x14009dd86  mov     dword ptr [rsp+298h+var_268], 6
0x14009dd8e  cmp     [rsp+298h+var_90], r14d
0x14009dd96  jnz     loc_14009DFCF
0x14009dd9c  cmp     [rsp+298h+var_D8], r14d
0x14009dda4  jnz     loc_14009DFAA
0x14009ddaa  jmp     short loc_14009DDB8
0x14009ddac  or      rax, 0FFFFFFFFFFFFFFFFh
0x14009ddb0  mov     rcx, rax
0x14009ddb3  jmp     loc_14009DC2E
0x14009ddb8  lea     rcx, [rsp+298h+var_D0]
0x14009ddc0  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x14009ddc5  nop
0x14009ddc6  mov     rax, [rdi]
0x14009ddc9  mov     rcx, rdi
0x14009ddcc  mov     rax, [rax+58h]
0x14009ddd0  call    cs:__guard_dispatch_icall_fptr
0x14009ddd6  cmp     eax, 3
0x14009ddd9  jz      short loc_14009DE34
0x14009dddb  lea     rax, WPP_GLOBAL_Control
0x14009dde2  mov     rcx, cs:WPP_GLOBAL_Control
0x14009dde9  cmp     rcx, rax
0x14009ddec  jz      short loc_14009DE0A
0x14009ddee  test    [rcx+1Ch], sil
0x14009ddf2  jz      short loc_14009DE0A
0x14009ddf4  mov     edx, 3Ah ; ':'
0x14009ddf9  lea     r8, WPP_2302b92dd89c3f461ef1ff1dfe596bd8_Traceguids
0x14009de00  mov     rcx, [rcx+10h]
0x14009de04  call    WPP_SF_
0x14009de09  nop
0x14009de0a  mov     rax, [rdi]
0x14009de0d  mov     edx, esi
0x14009de0f  mov     rcx, rdi
0x14009de12  mov     rax, [rax+0C0h]
0x14009de19  call    cs:__guard_dispatch_icall_fptr
0x14009de1f  nop
0x14009de20  lea     rcx, [rsp+298h+var_F8]
0x14009de28  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x14009de2d  xor     al, al
0x14009de2f  jmp     loc_14009DF87
0x14009de34  mov     [rsp+298h+var_268], r14
0x14009de39  mov     rax, [rdi]
0x14009de3c  mov     rcx, rdi
0x14009de3f  mov     rax, [rax+0A8h]
0x14009de46  call    cs:__guard_dispatch_icall_fptr
0x14009de4c  mov     r14, [rsp+298h+var_230]
0x14009de51  mov     r8, r14
0x14009de54  lea     rdx, [rsp+298h+var_268]
0x14009de59  mov     rcx, rax
0x14009de5c  call    ?find_by_key@object@json@web@@AEBA?AV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@Vvalue@json@web@@@std@@@std@@@std@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@5@@Z; web::json::object::find_by_key(std::wstring const &)
0x14009de61  mov     rax, [rdi]
0x14009de64  mov     rcx, rdi
0x14009de67  mov     rax, [rax+0A8h]
0x14009de6e  call    cs:__guard_dispatch_icall_fptr
0x14009de74  mov     rbx, [rsp+298h+var_268]
0x14009de79  cmp     rbx, [rax+8]
0x14009de7d  jz      short loc_14009DEE2
0x14009de7f  mov     rcx, [rbx+20h]
0x14009de83  mov     rax, [rcx]
0x14009de86  mov     rax, [rax+58h]
0x14009de8a  call    cs:__guard_dispatch_icall_fptr
0x14009de90  cmp     eax, 2
0x14009de93  jnz     short loc_14009DEE2
0x14009de95  mov     rcx, [rbx+20h]
0x14009de99  mov     rax, [rcx]
0x14009de9c  mov     rax, [rax+0B0h]
0x14009dea3  call    cs:__guard_dispatch_icall_fptr
0x14009dea9  mov     rdx, rax
0x14009deac  mov     rcx, [rsp+298h+var_228]; void *
0x14009deb1  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x14009deb6  nop
0x14009deb7  mov     rax, [rdi]
0x14009deba  mov     edx, esi
0x14009debc  mov     rcx, rdi
0x14009debf  mov     rax, [rax+0C0h]
0x14009dec6  call    cs:__guard_dispatch_icall_fptr
0x14009decc  nop
0x14009decd  lea     rcx, [rsp+298h+var_F8]
0x14009ded5  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x14009deda  mov     al, sil
0x14009dedd  jmp     loc_14009DF87
0x14009dee2  lea     rax, WPP_GLOBAL_Control
0x14009dee9  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
