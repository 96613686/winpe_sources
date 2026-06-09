# DockedClient::DoStoreBizCritUpdates(ushort *,int *,ushort * *)

- ea: `0x180030980`
- end: `0x1800310b6`
- name: `?DoStoreBizCritUpdates@DockedClient@@UEAAJPEAGPEAHPEAPEAG@Z`
- size: `1846`
- prototype: `__int64 __fastcall(DockedClient *__hidden this, unsigned __int16 *, int *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `24`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x180007660`
- `0x180007dfc`
- `0x18000bbb0`
- `0x18000bc20`
- `0x18000bda0`
- `0x18000f6e0`
- `0x180010500`
- `0x1800183f4`
- `0x18001ba70`
- `0x18001ee04`
- `0x18002178c`
- `0x180021a34`
- `0x180023a34`
- `0x180024030`
- `0x18002778c`
- `0x180027858`
- `0x180027c14`
- `0x180029f10`
- `0x18002a0c0`
- `0x18002bd54`
- `0x180030980`
- `0x180036568`
- `0x18003a290`
- `0x180071010`

## import_xrefs

- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x180030fe8`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x180030fe8`
- `msvcp_win!??1?$basic_ostream@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x180030fda`
- `msvcp_win!??1?$basic_ostream@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x180030fda`
- `OLEAUT32!__imp_SysAllocString` at `0x180030f5d`
- `OLEAUT32!__imp_SysAllocString` at `0x180030f5d`

## string_xrefs

- `0x1800310a3`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800309f3`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\docked\dll\dockedclient.cpp`
- `0x180030a20`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\docked\dll\dockedclient.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=21
__int64 __fastcall DockedClient::DoStoreBizCritUpdates(
        DockedClient *this,
        unsigned __int16 *a2,
        int *a3,
        unsigned __int16 **a4)
{
  unsigned __int16 **v4; // r13
  int *v5; // rdi
  __int64 result; // rax
  char *v7; // r14
  void *v8; // rax
  __int64 v9; // r15
  int v10; // r12d
  void (__fastcall *v11)(__int64, _BYTE *, __int128 *); // rbx
  web::json::value *v12; // rcx
  struct web::json::array *v13; // rax
  __int64 i; // rbx
  __int64 v15; // rdi
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  const char *v19; // r9
  __int64 v20; // rax
  _QWORD *v21; // rax
  __int64 v22; // r8
  web::json::value *v23; // rax
  bool v24; // r13
  web::json::value *v25; // rax
  bool v26; // cl
  __int64 v27; // rdx
  int v28; // ebx
  int v29; // ecx
  unsigned int v30; // ebx
  int v31; // r12d
  const OLECHAR *v32; // rcx
  BSTR v33; // rax
  const char *v34; // r9
  const char *v35; // r9
  int v36; // [rsp+20h] [rbp-2B8h]
  char v37[4]; // [rsp+30h] [rbp-2A8h] BYREF
  int v38; // [rsp+34h] [rbp-2A4h]
  OLECHAR *psz[2]; // [rsp+38h] [rbp-2A0h] BYREF
  __int64 v40; // [rsp+48h] [rbp-290h]
  unsigned __int64 v41; // [rsp+50h] [rbp-288h]
  __int128 v42; // [rsp+58h] [rbp-280h] BYREF
  __int64 v43; // [rsp+68h] [rbp-270h]
  unsigned __int16 **v44; // [rsp+70h] [rbp-268h]
  __int128 v45; // [rsp+78h] [rbp-260h] BYREF
  __int64 v46; // [rsp+88h] [rbp-250h]
  __int64 v47; // [rsp+90h] [rbp-248h]
  bool v48; // [rsp+98h] [rbp-240h]
  bool v49; // [rsp+99h] [rbp-23Fh]
  int v50; // [rsp+9Ah] [rbp-23Eh]
  __int16 v51; // [rsp+9Eh] [rbp-23Ah]
  unsigned __int16 *v52; // [rsp+A0h] [rbp-238h]
  int *v53; // [rsp+A8h] [rbp-230h]
  int *v54; // [rsp+B0h] [rbp-228h]
  unsigned __int16 **v55; // [rsp+B8h] [rbp-220h]
  unsigned __int16 *v56; // [rsp+C0h] [rbp-218h]
  char *v57; // [rsp+C8h] [rbp-210h]
  char *v58; // [rsp+D0h] [rbp-208h]
  __int128 v59; // [rsp+D8h] [rbp-200h] BYREF
  __int64 v60; // [rsp+E8h] [rbp-1F0h]
  __int64 v61; // [rsp+F0h] [rbp-1E8h]
  __int128 v62; // [rsp+F8h] [rbp-1E0h] BYREF
  __int64 v63; // [rsp+108h] [rbp-1D0h]
  __int64 v64; // [rsp+110h] [rbp-1C8h]
  __int128 v65; // [rsp+118h] [rbp-1C0h] BYREF
  __int64 v66; // [rsp+128h] [rbp-1B0h]
  __int64 v67; // [rsp+130h] [rbp-1A8h]
  __int128 v68; // [rsp+138h] [rbp-1A0h] BYREF
  __int64 v69; // [rsp+148h] [rbp-190h]
  __int128 v70; // [rsp+150h] [rbp-188h] BYREF
  __int64 v71; // [rsp+160h] [rbp-178h]
  _BYTE v72[32]; // [rsp+168h] [rbp-170h] BYREF
  char v73; // [rsp+188h] [rbp-150h]
  char v74; // [rsp+190h] [rbp-148h]
  int v75; // [rsp+19Ch] [rbp-13Ch]
  __int64 v76; // [rsp+1A0h] [rbp-138h] BYREF
  char v77[8]; // [rsp+1A8h] [rbp-130h] BYREF
  char v78[120]; // [rsp+1B0h] [rbp-128h] BYREF
  char v79[104]; // [rsp+228h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+0h]

  v4 = a4;
  v55 = a4;
  v5 = a3;
  v54 = a3;
  v52 = a2;
  v56 = a2;
  v53 = a3;
  v44 = a4;
  v38 = 0;
  if ( a3 )
  {
    if ( a4 )
    {
      try
      {
        v7 = (char *)operator new(0x18u);
        *((_DWORD *)v7 + 2) = 1;
        *((_DWORD *)v7 + 3) = 1;
        *(_QWORD *)v7 = &std::_Ref_count_obj2<Windows::Network>::`vftable';
        *((_QWORD *)v7 + 2) = &Windows::Registry::`vftable';
        v57 = v7 + 16;
        v58 = v7;
        v8 = operator new(0x88u);
        v43 = (__int64)v8;
        v42 = 0;
        if ( v7 )
          _InterlockedIncrement((volatile signed __int32 *)v7 + 2);
        *(_QWORD *)&v42 = v7 + 16;
        *((_QWORD *)&v42 + 1) = v7;
        v9 = Windows::Settings::Settings(v8, &v42, 0);
        v43 = v9;
        v10 = 3;
        v38 = 3;
        v11 = *(void (__fastcall **)(__int64, _BYTE *, __int128 *))(*(_QWORD *)v9 + 32LL);
        v59 = 0;
        v60 = 0;
        v61 = 0;
        std::wstring::_Construct<1,unsigned short const *>(&v59, L"StoreBizCriticalApps");
        v11(v9, v72, &v59);
        std::wstring::_Tidy_deallocate(&v59);
        if ( v74 && v73 == 2 )
        {
          try
          {
            v68 = 0;
            v69 = 0;
            v12 = (web::json::value *)web::json::value::parse(&v42, v72);
            v13 = web::json::value::as_array(v12);
            v70 = 0;
            v71 = 0;
            std::vector<web::json::value>::_Construct_n<web::json::value * const &,web::json::value * const &>(
              &v70,
              (__int64)(*((_QWORD *)v13 + 1) - *(_QWORD *)v13) >> 3,
              v13);
            if ( (_QWORD)v42 )
              (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)v42 + 192LL))(v42, 1);
            v15 = *((_QWORD *)&v70 + 1);
            for ( i = v70; i != v15; i += 8 )
            {
              *(_OWORD *)psz = 0;
              v40 = 0;
              v41 = 0;
              std::wstring::_Construct<1,unsigned short const *>(psz, L"pfn");
              v20 = web::json::value::at(i, psz);
              v21 = (_QWORD *)web::json::value::as_string(v20);
              v45 = 0;
              v46 = 0;
              v47 = 0;
              v22 = v21[2];
              if ( v21[3] > 7u )
                v21 = (_QWORD *)*v21;
              std::wstring::_Construct<2,unsigned short const *>(&v45, v21, v22);
              v65 = 0;
              v66 = 0;
              v67 = 0;
              std::wstring::_Construct<1,unsigned short const *>(&v65, L"forcerestart");
              v23 = (web::json::value *)web::json::value::at(i, &v65);
              v24 = web::json::value::as_bool(v23);
              v48 = v24;
              v62 = 0;
              v63 = 0;
              v64 = 0;
              std::wstring::_Construct<1,unsigned short const *>(&v62, L"sendrestartnotification");
              v25 = (web::json::value *)web::json::value::at(i, &v62);
              v26 = web::json::value::as_bool(v25);
              v49 = v26;
              v50 = 0;
              v51 = 0;
              v27 = *((_QWORD *)&v68 + 1);
              if ( *((_QWORD *)&v68 + 1) == v69 )
              {
                std::vector<Windows::AppInstaller::AppToInstall>::_Emplace_reallocate<Windows::AppInstaller::AppToInstall>(
                  &v68,
                  *((_QWORD *)&v68 + 1),
                  &v45);
              }
              else
              {
                **((_WORD **)&v68 + 1) = v45;
                *(_QWORD *)(v27 + 2) = *(_QWORD *)((char *)&v45 + 2);
                *(_DWORD *)(v27 + 10) = *(_DWORD *)((char *)&v45 + 10);
                *(_WORD *)(v27 + 14) = HIWORD(v45);
                *(_QWORD *)(v27 + 16) = v46;
                *(_QWORD *)(v27 + 24) = v47;
                v46 = 0;
                v47 = 7;
                LOWORD(v45) = 0;
                *(_BYTE *)(v27 + 32) = v24;
                *(_BYTE *)(v27 + 33) = v26;
                *((_QWORD *)&v68 + 1) += 40LL;
              }
              std::wstring::_Tidy_deallocate(&v45);
              std::wstring::_Tidy_deallocate(&v62);
              std::wstring::_Tidy_deallocate(&v65);
              std::wstring::_Tidy_deallocate(psz);
            }
            v16 = g_appsToInstall;
            *(_QWORD *)&g_appsToInstall = v68;
            *(_QWORD *)&v68 = v16;
            v17 = *((_QWORD *)&g_appsToInstall + 1);
            *((_QWORD *)&g_appsToInstall + 1) = *((_QWORD *)&v68 + 1);
            *((_QWORD *)&v68 + 1) = v17;
            v18 = qword_180096170;
            qword_180096170 = v69;
            v69 = v18;
            std::vector<web::json::value>::_Tidy(&v70);
            std::vector<Windows::AppInstaller::AppToInstall>::_Tidy(&v68);
            v5 = v54;
            v4 = v55;
          }
          catch ( ... )
          {
            wil::details::in1diag3::Log_CaughtException(
              retaddr,
              (void *)0xC7,
              (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\docked\\dll\\dockedclient.cpp",
              v19);
            v7 = v58;
            v9 = v43;
            v10 = v38;
            v52 = v56;
            v5 = v53;
            v4 = v44;
          }
        }
        std::basic_ostringstream<unsigned short>::basic_ostringstream<unsigned short>(&v76);
        v37[0] = 1;
        v44 = (unsigned __int16 **)&v70;
        v28 = std::vector<Windows::AppInstaller::AppToInstall>::vector<Windows::AppInstaller::AppToInstall>(
                &v70,
                &g_appsToInstall);
        *(_OWORD *)psz = 0;
        v40 = 0;
        v41 = 0;
        std::wstring::_Construct<1,unsigned short const *>(psz, L"IA");
        v30 = DockedClient::PerformExpeditedStoreUpdates(
                v29,
                (unsigned int)psz,
                v28,
                (_DWORD)v52,
                (__int64)v37,
                (__int64)&v76);
        *v5 = v37[0] != 0;
        std::basic_stringbuf<unsigned short>::str(v77, psz);
        v31 = v10 | 4;
        v32 = (const OLECHAR *)psz;
        if ( v41 > 7 )
          v32 = psz[0];
        v33 = SysAllocString(v32);
        v44 = (unsigned __int16 **)v33;
        v38 = v31 | 8;
        if ( !v33 )
          wil::details::in1diag3::_Throw_NullAlloc(
            retaddr,
            (void *)0x15F3,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
            v34);
        *v4 = v33;
        std::wstring::_Tidy_deallocate(psz);
        *(_QWORD *)&v77[*(int *)(v76 + 4) - 8] = &std::basic_ostringstream<unsigned short>::`vftable';
        *(int *)((char *)&v75 + *(int *)(v76 + 4)) = *(_DWORD *)(v76 + 4) - 136;
        std::basic_stringbuf<unsigned short>::~basic_stringbuf<unsigned short>(v77);
        std::basic_ostream<unsigned short>::~basic_ostream<unsigned short,std::char_traits<unsigned short>>(v78);
        std::basic_ios<unsigned short>::~basic_ios<unsigned short,std::char_traits<unsigned short>>(v79);
        if ( v74 && v73 != -1 && v73 && v73 != 1 )
          std::wstring::_Tidy_deallocate(v72);
        if ( v9 )
          (**(void (__fastcall ***)(__int64, __int64))v9)(v9, 1);
        if ( v7 )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v7 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(void *))v7)(v7);
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)v7 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(char *))(*(_QWORD *)v7 + 8LL))(v7);
          }
        }
        result = v30;
      }
      catch ( ... )
      {
        return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                               retaddr,
                               (void *)0xD3,
                               (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\docke"
                                             "d\\dll\\dockedclient.cpp",
                               v35);
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB2,
        (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\docked\\dll\\dockedclient.cpp",
        (const char *)0x80004003LL,
        v36);
      return 2147500035LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB1,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\docked\\dll\\dockedclient.cpp",
      (const char *)0x80004003LL,
      v36);
    return 2147500035LL;
  }
  return result;
}

```

## disassembly

```asm
0x180030980  push    rbx
0x180030982  push    rsi
0x180030983  push    rdi
0x180030984  push    r12
0x180030986  push    r13
0x180030988  push    r14
0x18003098a  push    r15
0x18003098c  sub     rsp, 2A0h
0x180030993  mov     rax, cs:__security_cookie
0x18003099a  xor     rax, rsp
0x18003099d  mov     [rsp+2D8h+var_48], rax
0x1800309a5  mov     r13, r9
0x1800309a8  mov     [rsp+2D8h+var_220], r9
0x1800309b0  mov     rdi, r8
0x1800309b3  mov     [rsp+2D8h+var_228], r8
0x1800309bb  mov     [rsp+2D8h+var_238], rdx
0x1800309c3  mov     [rsp+2D8h+var_218], rdx
0x1800309cb  mov     [rsp+2D8h+var_230], r8
0x1800309d3  mov     [rsp+2D8h+var_268], r9
0x1800309d8  xor     esi, esi
0x1800309da  mov     [rsp+2D8h+var_2A4], esi
0x1800309de  test    r8, r8
0x1800309e1  jnz     short loc_180030A0B
0x1800309e3  mov     rcx, [rsp+2D8h]; this
0x1800309eb  mov     ebx, 80004003h
0x1800309f0  mov     r9d, ebx; char *
0x1800309f3  lea     r8, aOnecoreEnduser_23; "onecore\\enduser\\windowsupdate\\muse\\"...
0x1800309fa  mov     edx, 0B1h; void *
0x1800309ff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030a04  mov     eax, ebx
0x180030a06  jmp     loc_180031080
0x180030a0b  test    r9, r9
0x180030a0e  jnz     short loc_180030A38
0x180030a10  mov     rcx, [rsp+2D8h]; this
0x180030a18  mov     ebx, 80004003h
0x180030a1d  mov     r9d, ebx; char *
0x180030a20  lea     r8, aOnecoreEnduser_23; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180030a27  mov     edx, 0B2h; void *
0x180030a2c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030a31  mov     eax, ebx
0x180030a33  jmp     loc_180031080
0x180030a38  mov     ecx, 18h; Size
0x180030a3d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180030a42  mov     r14, rax
0x180030a45  mov     dword ptr [rax+8], 1
0x180030a4c  mov     dword ptr [rax+0Ch], 1
0x180030a53  lea     rax, ??_7?$_Ref_count_obj2@VNetwork@Windows@@@std@@6B@; const std::_Ref_count_obj2<Windows::Network>::`vftable'
0x180030a5a  mov     [r14], rax
0x180030a5d  lea     rbx, [r14+10h]
0x180030a61  lea     rax, ??_7Registry@Windows@@6B@; const Windows::Registry::`vftable'
0x180030a68  mov     [rbx], rax
0x180030a6b  mov     [rsp+2D8h+var_210], rbx
0x180030a73  mov     [rsp+2D8h+var_208], r14
0x180030a7b  mov     ecx, 88h; Size
0x180030a80  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180030a85  mov     [rsp+2D8h+var_270], rax
0x180030a8a  xorps   xmm0, xmm0
0x180030a8d  movdqu  [rsp+2D8h+var_280], xmm0
0x180030a93  test    r14, r14
0x180030a96  jz      short loc_180030A9D
0x180030a98  lock inc dword ptr [r14+8]
0x180030a9d  mov     qword ptr [rsp+2D8h+var_280], rbx
0x180030aa2  mov     qword ptr [rsp+2D8h+var_280+8], r14
0x180030aa7  xor     r8d, r8d
0x180030aaa  lea     rdx, [rsp+2D8h+var_280]
0x180030aaf  mov     rcx, rax
0x180030ab2  call    ??0Settings@Windows@@QEAA@V?$shared_ptr@VRegistry@SystemInterface@@@std@@_N@Z; Windows::Settings::Settings(std::shared_ptr<SystemInterface::Registry>,bool)
0x180030ab7  mov     r15, rax
0x180030aba  mov     [rsp+2D8h+var_270], rax
0x180030abf  mov     r12d, 3
0x180030ac5  mov     [rsp+2D8h+var_2A4], r12d
0x180030aca  mov     rax, [rax]
0x180030acd  mov     rbx, [rax+20h]
0x180030ad1  xorps   xmm0, xmm0
0x180030ad4  movups  [rsp+2D8h+var_200], xmm0
0x180030adc  mov     [rsp+2D8h+var_1F0], rsi
0x180030ae4  mov     [rsp+2D8h+var_1E8], rsi
0x180030aec  lea     r8d, [r12+11h]
0x180030af1  lea     rdx, aStorebizcritic; "StoreBizCriticalApps"
0x180030af8  lea     rcx, [rsp+2D8h+var_200]
0x180030b00  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180030b05  nop
0x180030b06  lea     r8, [rsp+2D8h+var_200]
0x180030b0e  lea     rdx, [rsp+2D8h+var_170]
0x180030b16  mov     rcx, r15
0x180030b19  mov     rax, rbx
0x180030b1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030b21  nop
0x180030b22  lea     rcx, [rsp+2D8h+var_200]
0x180030b2a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180030b2f  cmp     [rsp+2D8h+var_148], sil
0x180030b37  jz      loc_180030E9B
0x180030b3d  cmp     [rsp+2D8h+var_150], 2
0x180030b45  jnz     loc_180030E9B
0x180030b4b  xorps   xmm0, xmm0
0x180030b4e  movdqu  [rsp+2D8h+var_1A0], xmm0
0x180030b57  mov     [rsp+2D8h+var_190], rsi
0x180030b5f  lea     rdx, [rsp+2D8h+var_170]
0x180030b67  lea     rcx, [rsp+2D8h+var_280]
0x180030b6c  call    ?parse@value@json@web@@SA?AV123@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::value::parse(std::wstring const &)
0x180030b71  nop
0x180030b72  mov     rcx, rax; this
0x180030b75  call    ?as_array@value@json@web@@QEAAAEAVarray@23@XZ; web::json::value::as_array(void)
0x180030b7a  xorps   xmm0, xmm0
0x180030b7d  movdqu  [rsp+2D8h+var_188], xmm0
0x180030b86  mov     [rsp+2D8h+var_178], rsi
0x180030b8e  lea     r9, [rax+8]
0x180030b92  mov     rdx, [r9]
0x180030b95  sub     rdx, [rax]
0x180030b98  sar     rdx, 3
0x180030b9c  mov     r8, rax
0x180030b9f  lea     rcx, [rsp+2D8h+var_188]
0x180030ba7  call    ??$_Construct_n@AEBQEAVvalue@json@web@@AEBQEAV123@@?$vector@Vvalue@json@web@@V?$allocator@Vvalue@json@web@@@std@@@std@@AEAAX_KAEBQEAVvalue@json@web@@1@Z; std::vector<web::json::value>::_Construct_n<web::json::value * const &,web::json::value * const &>(unsigned __int64,web::json::value * const &,web::json::value * const &)
0x180030bac  nop
0x180030bad  mov     rcx, qword ptr [rsp+2D8h+var_280]
0x180030bb2  test    rcx, rcx
0x180030bb5  jz      short loc_180030BCB
0x180030bb7  mov     rax, [rcx]
0x180030bba  lea     edx, [r12-2]
0x180030bbf  mov     rax, [rax+0C0h]
0x180030bc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030bcb  mov     rbx, qword ptr [rsp+2D8h+var_188]
0x180030bd3  mov     rdi, qword ptr [rsp+2D8h+var_188+8]
0x180030bdb  cmp     rbx, rdi
0x180030bde  jnz     loc_180030C6F
0x180030be4  mov     rcx, qword ptr cs:?g_appsToInstall@@3V?$vector@UAppToInstall@AppInstaller@Windows@@V?$allocator@UAppToInstall@AppInstaller@Windows@@@std@@@std@@A; std::vector<Windows::AppInstaller::AppToInstall> g_appsToInstall
0x180030beb  mov     rax, qword ptr [rsp+2D8h+var_1A0]
0x180030bf3  mov     qword ptr cs:?g_appsToInstall@@3V?$vector@UAppToInstall@AppInstaller@Windows@@V?$allocator@UAppToInstall@AppInstaller@Windows@@@std@@@std@@A, rax; std::vector<Windows::AppInstaller::AppToInstall> g_appsToInstall
0x180030bfa  mov     qword ptr [rsp+2D8h+var_1A0], rcx
0x180030c02  mov     rcx, qword ptr cs:?g_appsToInstall@@3V?$vector@UAppToInstall@AppInstaller@Windows@@V?$allocator@UAppToInstall@AppInstaller@Windows@@@std@@@std@@A+8; std::vector<Windows::AppInstaller::AppToInstall> g_appsToInstall
0x180030c09  mov     rax, qword ptr [rsp+2D8h+var_1A0+8]
0x180030c11  mov     qword ptr cs:?g_appsToInstall@@3V?$vector@UAppToInstall@AppInstaller@Windows@@V?$allocator@UAppToInstall@AppInstaller@Windows@@@std@@@std@@A+8, rax; std::vector<Windows::AppInstaller::AppToInstall> g_appsToInstall
0x180030c18  mov     qword ptr [rsp+2D8h+var_1A0+8], rcx
0x180030c20  mov     rcx, cs:qword_180096170
0x180030c27  mov     rax, [rsp+2D8h+var_190]
0x180030c2f  mov     cs:qword_180096170, rax
0x180030c36  mov     [rsp+2D8h+var_190], rcx
0x180030c3e  lea     rcx, [rsp+2D8h+var_188]
0x180030c46  call    ?_Tidy@?$vector@Vvalue@json@web@@V?$allocator@Vvalue@json@web@@@std@@@std@@AEAAXXZ; std::vector<web::json::value>::_Tidy(void)
0x180030c4b  nop
0x180030c4c  lea     rcx, [rsp+2D8h+var_1A0]
0x180030c54  call    ?_Tidy@?$vector@UAppToInstall@AppInstaller@Windows@@V?$allocator@UAppToInstall@AppInstaller@Windows@@@std@@@std@@AEAAXXZ; std::vector<Windows::AppInstaller::AppToInstall>::_Tidy(void)
0x180030c59  nop
0x180030c5a  mov     rdi, [rsp+2D8h+var_228]
0x180030c62  mov     r13, [rsp+2D8h+var_220]
0x180030c6a  jmp     loc_180030E9B
0x180030c6f  xorps   xmm0, xmm0
0x180030c72  movups  xmmword ptr [rsp+2D8h+psz], xmm0
0x180030c77  mov     [rsp+2D8h+var_290], rsi
0x180030c7c  mov     [rsp+2D8h+var_288], rsi
0x180030c81  mov     r8, r12
0x180030c84  lea     rdx, aPfn; "pfn"
0x180030c8b  lea     rcx, [rsp+2D8h+psz]
0x180030c90  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180030c95  nop
0x180030c96  lea     rdx, [rsp+2D8h+psz]
0x180030c9b  mov     rcx, rbx
0x180030c9e  call    ?at@value@json@web@@QEAAAEAV123@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::value::at(std::wstring const &)
0x180030ca3  mov     rcx, rax
0x180030ca6  call    ?as_string@value@json@web@@QEBAAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; web::json::value::as_string(void)
0x180030cab  xorps   xmm0, xmm0
0x180030cae  movups  [rsp+2D8h+var_260], xmm0
0x180030cb3  mov     [rsp+2D8h+var_250], rsi
0x180030cbb  mov     [rsp+2D8h+var_248], rsi
0x180030cc3  mov     r8, [rax+10h]
0x180030cc7  cmp     qword ptr [rax+18h], 7
0x180030ccc  jbe     short loc_180030CD1
0x180030cce  mov     rax, [rax]
0x180030cd1  mov     rdx, rax
0x180030cd4  lea     rcx, [rsp+2D8h+var_260]
0x180030cd9  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x180030cde  nop
0x180030cdf  xorps   xmm0, xmm0
0x180030ce2  movups  [rsp+2D8h+var_1C0], xmm0
0x180030cea  mov     [rsp+2D8h+var_1B0], rsi
0x180030cf2  mov     [rsp+2D8h+var_1A8], rsi
0x180030cfa  mov     r8d, 0Ch
0x180030d00  lea     rdx, aForcerestart; "forcerestart"
0x180030d07  lea     rcx, [rsp+2D8h+var_1C0]
0x180030d0f  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180030d14  nop
0x180030d15  lea     rdx, [rsp+2D8h+var_1C0]
0x180030d1d  mov     rcx, rbx
0x180030d20  call    ?at@value@json@web@@QEAAAEAV123@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::value::at(std::wstring const &)
0x180030d25  mov     rcx, rax; this
0x180030d28  call    ?as_bool@value@json@web@@QEBA_NXZ; web::json::value::as_bool(void)
0x180030d2d  mov     r13b, al
0x180030d30  mov     [rsp+2D8h+var_240], al
0x180030d37  xorps   xmm0, xmm0
0x180030d3a  movups  [rsp+2D8h+var_1E0], xmm0
0x180030d42  mov     [rsp+2D8h+var_1D0], rsi
0x180030d4a  mov     [rsp+2D8h+var_1C8], rsi
0x180030d52  mov     r8d, 17h
0x180030d58  lea     rdx, aSendrestartnot; "sendrestartnotification"
0x180030d5f  lea     rcx, [rsp+2D8h+var_1E0]
0x180030d67  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180030d6c  nop
0x180030d6d  lea     rdx, [rsp+2D8h+var_1E0]
0x180030d75  mov     rcx, rbx
0x180030d78  call    ?at@value@json@web@@QEAAAEAV123@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::value::at(std::wstring const &)
0x180030d7d  mov     rcx, rax; this
0x180030d80  call    ?as_bool@value@json@web@@QEBA_NXZ; web::json::value::as_bool(void)
0x180030d85  mov     cl, al
0x180030d87  mov     [rsp+2D8h+var_23F], al
0x180030d8e  xor     eax, eax
0x180030d90  mov     [rsp+2D8h+var_23E], eax
0x180030d97  mov     [rsp+2D8h+var_23A], ax
0x180030d9f  mov     rdx, qword ptr [rsp+2D8h+var_1A0+8]
0x180030da7  cmp     rdx, [rsp+2D8h+var_190]
0x180030daf  jz      short loc_180030E1D
0x180030db1  movzx   eax, word ptr [rsp+2D8h+var_260]
0x180030db6  mov     [rdx], ax
0x180030db9  movsd   xmm0, qword ptr [rsp+2D8h+var_260+2]
0x180030dbf  movsd   qword ptr [rdx+2], xmm0
0x180030dc4  mov     eax, dword ptr [rsp+2D8h+var_260+0Ah]
0x180030dcb  mov     [rdx+0Ah], eax
0x180030dce  movzx   eax, word ptr [rsp+2D8h+var_260+0Eh]
0x180030dd6  mov     [rdx+0Eh], ax
0x180030dda  mov     rax, [rsp+2D8h+var_250]
0x180030de2  mov     [rdx+10h], rax
0x180030de6  mov     rax, [rsp+2D8h+var_248]
0x180030dee  mov     [rdx+18h], rax
0x180030df2  mov     [rsp+2D8h+var_250], rsi
0x180030dfa  mov     [rsp+2D8h+var_248], 7
0x180030e06  mov     word ptr [rsp+2D8h+var_260], si
0x180030e0b  mov     [rdx+20h], r13b
0x180030e0f  mov     [rdx+21h], cl
0x180030e12  add     qword ptr [rsp+2D8h+var_1A0+8], 28h ; '('
0x180030e1b  jmp     short loc_180030E30
0x180030e1d  lea     r8, [rsp+2D8h+var_260]
0x180030e22  lea     rcx, [rsp+2D8h+var_1A0]
0x180030e2a  call    ??$_Emplace_reallocate@UAppToInstall@AppInstaller@Windows@@@?$vector@UAppToInstall@AppInstaller@Windows@@V?$allocator@UAppToInstall@AppInstaller@Windows@@@std@@@std@@AEAAPEAUAppToInstall@AppInstaller@Windows@@QEAU234@$$QEAU234@@Z; std::vector<Windows::AppInstaller::AppToInstall>::_Emplace_reallocate<Windows::AppInstaller::AppToInstall>(Windows::AppInstaller::AppToInstall * const,Windows::AppInstaller::AppToInstall &&)
0x180030e2f  nop
0x180030e30  lea     rcx, [rsp+2D8h+var_260]
0x180030e35  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180030e3a  nop
0x180030e3b  lea     rcx, [rsp+2D8h+var_1E0]
0x180030e43  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180030e48  nop
0x180030e49  lea     rcx, [rsp+2D8h+var_1C0]
0x180030e51  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180030e56  nop
0x180030e57  lea     rcx, [rsp+2D8h+psz]
0x180030e5c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180030e61  add     rbx, 8
0x180030e65  jmp     loc_180030BDB
0x180030e6a  xor     esi, esi
0x180030e6c  mov     r14, [rsp+2D8h+var_208]
0x180030e74  mov     r15, [rsp+2D8h+var_270]
0x180030e79  mov     r12d, [rsp+2D8h+var_2A4]
0x180030e7e  mov     rax, [rsp+2D8h+var_218]
0x180030e86  mov     [rsp+2D8h+var_238], rax
0x180030e8e  mov     rdi, [rsp+2D8h+var_230]
0x180030e96  mov     r13, [rsp+2D8h+var_268]
0x180030e9b  lea     rcx, [rsp+2D8h+var_138]
0x180030ea3  call    ??0?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_ostringstream<ushort>::basic_ostringstream<ushort>(void)
0x180030ea8  nop
0x180030ea9  mov     [rsp+2D8h+var_2A8], 1
0x180030eae  lea     rax, [rsp+2D8h+var_188]
0x180030eb6  mov     [rsp+2D8h+var_268], rax
0x180030ebb  lea     rdx, ?g_appsToInstall@@3V?$vector@UAppToInstall@AppInstaller@Windows@@V?$allocator@UAppToInstall@AppInstaller@Windows@@@std@@@std@@A; std::vector<Windows::AppInstaller::AppToInstall> g_appsToInstall
0x180030ec2  lea     rcx, [rsp+2D8h+var_188]
0x180030eca  call    ??0?$vector@UAppToInstall@AppInstaller@Windows@@V?$allocator@UAppToInstall@AppInstaller@Windows@@@std@@@std@@QEAA@AEBV01@@Z; std::vector<Windows::AppInstaller::AppToInstall>::vector<Windows::AppInstaller::AppToInstall>(std::vector<Windows::AppInstaller::AppToInstall> const &)
0x180030ecf  mov     rbx, rax
0x180030ed2  xorps   xmm0, xmm0
0x180030ed5  movups  xmmword ptr [rsp+2D8h+psz], xmm0
0x180030eda  mov     [rsp+2D8h+var_290], rsi
0x180030edf  mov     [rsp+2D8h+var_288], rsi
0x180030ee4  mov     r8d, 2
0x180030eea  lea     rdx, aIa; "IA"
0x180030ef1  lea     rcx, [rsp+2D8h+psz]
0x180030ef6  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180030efb  nop
0x180030efc  lea     rax, [rsp+2D8h+var_138]
0x180030f04  mov     [rsp+2D8h+var_2B0], rax
0x180030f09  lea     rax, [rsp+2D8h+var_2A8]
0x180030f0e  mov     [rsp+2D8h+var_2B8], rax
0x180030f13  mov     r9, [rsp+2D8h+var_238]
0x180030f1b  mov     r8, rbx
0x180030f1e  lea     rdx, [rsp+2D8h+psz]
0x180030f23  call    ?PerformExpeditedStoreUpdates@DockedClient@@AEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@UAppToInstall@AppInstaller@Windows@@V?$allocator@UAppToInstall@AppInstaller@Windows@@@std@@@3@PEAGAEA_NAEAV?$basic_ostream@GU?$char_traits@G@std@@@3@@Z; DockedClient::PerformExpeditedStoreUpdates(std::wstring,std::vector<Windows::AppInstaller::AppToInstall>,ushort *,bool &,std::basic_ostream<ushort> &)
0x180030f28  mov     ebx, eax
0x180030f2a  mov     ecx, esi
0x180030f2c  cmp     [rsp+2D8h+var_2A8], sil
0x180030f31  setnz   cl
0x180030f34  mov     [rdi], ecx
0x180030f36  lea     rdx, [rsp+2D8h+psz]
0x180030f3b  lea     rcx, [rsp+2D8h+var_130]
0x180030f43  call    ?str@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::basic_stringbuf<ushort>::str(void)
0x180030f48  or      r12d, 4
0x180030f4c  lea     rcx, [rsp+2D8h+psz]
0x180030f51  cmp     [rsp+2D8h+var_288], 7
0x180030f57  cmova   rcx, [rsp+2D8h+psz]; psz
0x180030f5d  call    cs:__imp_SysAllocString
0x180030f63  mov     [rsp+2D8h+var_268], rax
0x180030f68  or      r12d, 8
0x180030f6c  mov     [rsp+2D8h+var_2A4], r12d
0x180030f71  mov     rcx, [rsp+2D8h]; this
0x180030f79  test    rax, rax
0x180030f7c  jz      loc_1800310A3
  ... truncated ...
```
