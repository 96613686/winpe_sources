# GetUnusedLanguageFeatures

- ea: `0x180023070`
- end: `0x180023544`
- name: `GetUnusedLanguageFeatures`
- size: `1236`
- prototype: `__int64 __fastcall(__int128 *, __int64, __int64, __int64, _QWORD *, _DWORD *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180003520`
- `0x180004118`
- `0x1800092a4`
- `0x18000c24c`
- `0x180012dc8`
- `0x1800214f4`
- `0x180023070`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800232c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800232c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180023425`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180023470`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800234b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180023425`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180023470`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800234b8`

## string_xrefs

- `0x180023241`: `onecore\shell\cpls\internationalsettings\languagecomponentsinstaller\dll\languagecomponentsinstaller.cpp`
- `0x1800232e6`: `onecore\shell\cpls\internationalsettings\languagecomponentsinstaller\dll\languagecomponentsinstaller.cpp`
- `0x180023411`: `onecore\shell\cpls\internationalsettings\languagecomponentsinstaller\dll\languagecomponentsinstaller.cpp`
- `0x18002345c`: `onecore\shell\cpls\internationalsettings\languagecomponentsinstaller\dll\languagecomponentsinstaller.cpp`
- `0x1800234a4`: `onecore\shell\cpls\internationalsettings\languagecomponentsinstaller\dll\languagecomponentsinstaller.cpp`

## pseudocode

```c
__int64 __fastcall GetUnusedLanguageFeatures(__int128 *a1, __int64 a2, __int64 a3, __int64 a4, _QWORD *a5, _DWORD *a6)
{
  __int128 v6; // xmm0
  __int128 v7; // xmm1
  __int128 v8; // xmm2
  __int128 v9; // xmm3
  __int128 v10; // xmm4
  __int128 v11; // xmm5
  __int128 v12; // xmm6
  __int128 v13; // xmm7
  __int128 v14; // xmm8
  __int128 v15; // xmm9
  __int128 v16; // xmm10
  __int128 v17; // xmm11
  __int64 v18; // rax
  int v19; // eax
  unsigned int v20; // ebx
  const char *v21; // r9
  __int64 result; // rax
  __int64 v23; // rax
  __int64 v24; // rsi
  __int64 v25; // r14
  int v26; // r15d
  __int64 v27; // rcx
  _QWORD *v28; // rax
  _QWORD *v29; // rdi
  _QWORD *v30; // r11
  _WORD *v31; // r10
  __int64 v32; // rax
  __int64 i; // rdx
  unsigned __int128 v34; // kr10_16
  unsigned __int64 v35; // r8
  __int16 *v36; // rcx
  __int64 v37; // rbx
  __int64 v38; // r9
  _WORD *v39; // rax
  __int16 v40; // r12
  _WORD *v41; // rcx
  unsigned int v42; // ebx
  _QWORD v43[2]; // [rsp+28h] [rbp-210h] BYREF
  _DWORD *v44; // [rsp+38h] [rbp-200h]
  unsigned __int128 v45; // [rsp+40h] [rbp-1F8h] BYREF
  __int64 v46; // [rsp+50h] [rbp-1E8h]
  _QWORD v47[2]; // [rsp+60h] [rbp-1D8h] BYREF
  int v48; // [rsp+70h] [rbp-1C8h]
  __int64 v49; // [rsp+78h] [rbp-1C0h]
  int v50; // [rsp+80h] [rbp-1B8h]
  int v51; // [rsp+84h] [rbp-1B4h]
  __int64 v52; // [rsp+88h] [rbp-1B0h]
  __int64 v53; // [rsp+90h] [rbp-1A8h]
  int v54; // [rsp+98h] [rbp-1A0h]
  int v55; // [rsp+9Ch] [rbp-19Ch]
  char v56; // [rsp+A0h] [rbp-198h]
  __int128 v57; // [rsp+A8h] [rbp-190h]
  __int128 v58; // [rsp+B8h] [rbp-180h]
  __int128 v59; // [rsp+C8h] [rbp-170h]
  __int128 v60; // [rsp+D8h] [rbp-160h]
  __int128 v61; // [rsp+E8h] [rbp-150h]
  __int128 v62; // [rsp+F8h] [rbp-140h]
  __int128 v63; // [rsp+108h] [rbp-130h]
  __int128 v64; // [rsp+118h] [rbp-120h]
  __int128 v65; // [rsp+128h] [rbp-110h]
  __int128 v66; // [rsp+138h] [rbp-100h]
  __int128 v67; // [rsp+148h] [rbp-F0h]
  __int128 v68; // [rsp+158h] [rbp-E0h]
  __int64 v69; // [rsp+168h] [rbp-D0h]
  __int64 v70; // [rsp+170h] [rbp-C8h]
  __int64 v71; // [rsp+178h] [rbp-C0h]
  __int64 v72; // [rsp+180h] [rbp-B8h]
  wil::details::in1diag3 *retaddr; // [rsp+238h] [rbp+0h]

  v44 = a6;
  *a5 = 0;
  *a6 = 0;
  v6 = *a1;
  v7 = a1[1];
  v8 = a1[2];
  v9 = a1[3];
  v10 = a1[4];
  v11 = a1[5];
  v12 = a1[6];
  v13 = a1[7];
  v14 = a1[8];
  v15 = a1[9];
  v16 = a1[10];
  v17 = a1[11];
  v18 = *((_QWORD *)a1 + 24);
  v47[1] = 0;
  v48 = 0;
  v49 = -1;
  v50 = 1;
  v51 = 0;
  v52 = 0;
  v53 = 0;
  _InterlockedIncrement(&CWinTaskHandler::s_cInstances);
  v47[0] = &CLanguageComponentsInstallerHandler::`vftable';
  v54 = 0;
  v55 = 2;
  v56 = 0;
  v57 = v6;
  v58 = v7;
  v59 = v8;
  v60 = v9;
  v61 = v10;
  v62 = v11;
  v63 = v12;
  v64 = v13;
  v65 = v14;
  v66 = v15;
  v67 = v16;
  v68 = v17;
  v69 = v18;
  v70 = a2;
  v71 = a3;
  v72 = a4;
  v45 = 0;
  v46 = 0;
  v43[0] = v47;
  v43[1] = &v45;
  v19 = wil::ResultFromException__lambda_258e501501491fcf521dd258d2fe6baa___(v43);
  v20 = v19;
  if ( v19 >= 0 )
  {
    v23 = v45;
    if ( (_QWORD)v45 == *((_QWORD *)&v45 + 1) )
    {
      std::vector<std::wstring>::_Tidy(&v45);
      CWinTaskHandler::~CWinTaskHandler((CWinTaskHandler *)v47);
      result = 0;
    }
    else
    {
      v24 = 1;
      v25 = 2;
      v26 = 0;
      do
      {
        v27 = *(_QWORD *)(v23 + 16);
        if ( v27 )
        {
          ++v24;
          v25 += 2 * v27 + 2;
          ++v26;
        }
        v23 += 32;
      }
      while ( v23 != *((_QWORD *)&v45 + 1) );
      v28 = CoTaskMemAlloc(v25 + v24 * 8);
      v29 = v28;
      if ( v28 )
      {
        memset_0(v28, 0, v25 + v24 * 8);
        v30 = v29;
        v31 = &v29[v24];
        v32 = *((_QWORD *)&v45 + 1);
        v34 = v45;
        v43[0] = v34 >> 64;
        for ( i = v34; i != v32; i += 32 )
        {
          if ( *(_QWORD *)(i + 16) )
          {
            *v30 = v31;
            v35 = *(_QWORD *)(i + 16) + 1LL;
            if ( *(_QWORD *)(i + 24) <= 7u )
              v36 = (__int16 *)i;
            else
              v36 = *(__int16 **)i;
            if ( *(_QWORD *)(i + 16) == -1 )
            {
              v42 = -2147024809;
              goto LABEL_30;
            }
            if ( v35 > 0x7FFFFFFF )
            {
              v42 = -2147024809;
              *v31 = 0;
LABEL_30:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x228,
                (unsigned int)"onecore\\shell\\cpls\\internationalsettings\\languagecomponentsinstaller\\dll\\languagecom"
                              "ponentsinstaller.cpp",
                (const char *)v42,
                0);
              CoTaskMemFree(v29);
              std::vector<std::wstring>::_Tidy(&v45);
              CWinTaskHandler::~CWinTaskHandler((CWinTaskHandler *)v47);
              result = v42;
              goto LABEL_38;
            }
            v37 = 2147483646;
            v38 = *(_QWORD *)(i + 16) + 1LL;
            v39 = v31;
            do
            {
              if ( !v37 )
                break;
              v40 = *v36;
              if ( !*v36 )
                break;
              ++v36;
              *v39++ = v40;
              --v37;
              --v38;
            }
            while ( v38 );
            v41 = v39 - 1;
            if ( v38 )
              v41 = v39;
            *v41 = 0;
            v42 = v38 == 0 ? 0x8007007A : 0;
            if ( !v38 )
              goto LABEL_30;
            ++v30;
            --v24;
            v31 += v35;
            v25 += -2LL * v35;
            v32 = v43[0];
          }
        }
        if ( v24 == 1 )
        {
          if ( v25 == 2 )
          {
            *a5 = v29;
            *v44 = v26;
            std::vector<std::wstring>::_Tidy(&v45);
            CWinTaskHandler::~CWinTaskHandler((CWinTaskHandler *)v47);
            result = 0;
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x230,
              (unsigned int)"onecore\\shell\\cpls\\internationalsettings\\languagecomponentsinstaller\\dll\\languagecompo"
                            "nentsinstaller.cpp",
              (const char *)0x8000FFFFLL,
              0);
            CoTaskMemFree(v29);
            std::vector<std::wstring>::_Tidy(&v45);
            CWinTaskHandler::~CWinTaskHandler((CWinTaskHandler *)v47);
            result = 2147549183LL;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x22F,
            (unsigned int)"onecore\\shell\\cpls\\internationalsettings\\languagecomponentsinstaller\\dll\\languagecompone"
                          "ntsinstaller.cpp",
            (const char *)0x8000FFFFLL,
            0);
          CoTaskMemFree(v29);
          std::vector<std::wstring>::_Tidy(&v45);
          CWinTaskHandler::~CWinTaskHandler((CWinTaskHandler *)v47);
          result = 2147549183LL;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x217,
          (unsigned int)"onecore\\shell\\cpls\\internationalsettings\\languagecomponentsinstaller\\dll\\languagecomponentsinstaller.cpp",
          (const char *)0x8007000ELL,
          0);
        std::vector<std::wstring>::_Tidy(&v45);
        CWinTaskHandler::~CWinTaskHandler((CWinTaskHandler *)v47);
        result = 2147942414LL;
      }
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1FF,
      (unsigned int)"onecore\\shell\\cpls\\internationalsettings\\languagecomponentsinstaller\\dll\\languagecomponentsinstaller.cpp",
      (const char *)(unsigned int)v19,
      0);
    std::vector<std::wstring>::_Tidy(&v45);
    CWinTaskHandler::~CWinTaskHandler((CWinTaskHandler *)v47);
    result = v20;
  }
LABEL_38:
  while ( 2 )
  {
    try
    {
    }
    catch ( ... )
    {
      result = (unsigned int)wil::details::in1diag3::Return_CaughtException(
                               retaddr,
                               (void *)0x239,
                               (unsigned int)"onecore\\shell\\cpls\\internationalsettings\\languagecomponentsinstaller\\d"
                                             "ll\\languagecomponentsinstaller.cpp",
                               v21);
      continue;
    }
    break;
  }
  return result;
}

```

## disassembly

```asm
0x180023070  mov     r11, rsp
0x180023073  push    rbx
0x180023074  push    rsi
0x180023075  push    rdi
0x180023076  push    r12
0x180023078  push    r13
0x18002307a  push    r14
0x18002307c  push    r15
0x18002307e  sub     rsp, 200h
0x180023085  movaps  xmmword ptr [r11-48h], xmm6
0x18002308a  movaps  xmmword ptr [r11-58h], xmm7
0x18002308f  movaps  xmmword ptr [r11-68h], xmm8
0x180023094  movaps  xmmword ptr [r11-78h], xmm9
0x180023099  movaps  xmmword ptr [r11-88h], xmm10
0x1800230a1  movaps  xmmword ptr [r11-98h], xmm11
0x1800230a9  mov     rax, cs:__security_cookie
0x1800230b0  xor     rax, rsp
0x1800230b3  mov     [rsp+238h+var_A8], rax
0x1800230bb  mov     r13, [rsp+238h+arg_20]
0x1800230c3  mov     r12, [rsp+238h+arg_28]
0x1800230cb  mov     [rsp+238h+var_200], r12
0x1800230d0  xor     eax, eax
0x1800230d2  mov     qword ptr [rsp+238h+var_218], rax; int
0x1800230d7  mov     [r13+0], rax
0x1800230db  mov     [r12], eax
0x1800230df  movups  xmm0, xmmword ptr [rcx]
0x1800230e2  movups  xmm1, xmmword ptr [rcx+10h]
0x1800230e6  movups  xmm2, xmmword ptr [rcx+20h]
0x1800230ea  movups  xmm3, xmmword ptr [rcx+30h]
0x1800230ee  movups  xmm4, xmmword ptr [rcx+40h]
0x1800230f2  movups  xmm5, xmmword ptr [rcx+50h]
0x1800230f6  movups  xmm6, xmmword ptr [rcx+60h]
0x1800230fa  movups  xmm7, xmmword ptr [rcx+70h]
0x1800230fe  movups  xmm8, xmmword ptr [rcx+80h]
0x180023106  movups  xmm9, xmmword ptr [rcx+90h]
0x18002310e  movups  xmm10, xmmword ptr [rcx+0A0h]
0x180023116  movups  xmm11, xmmword ptr [rcx+0B0h]
0x18002311e  mov     rax, [rcx+0C0h]
0x180023125  xor     r12d, r12d
0x180023128  mov     [rsp+238h+var_1D0], r12
0x18002312d  mov     [rsp+238h+var_1C8], r12d
0x180023132  mov     [rsp+238h+var_1C0], 0FFFFFFFFFFFFFFFFh
0x18002313b  mov     [rsp+238h+var_1B8], 1
0x180023146  mov     [r11-1B4h], r12d
0x18002314d  mov     [r11-1B0h], r12
0x180023154  mov     [r11-1A8h], r12
0x18002315b  lock inc cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x180023162  lea     rcx, ??_7CLanguageComponentsInstallerHandler@@6B@; const CLanguageComponentsInstallerHandler::`vftable'
0x180023169  mov     [rsp+238h+var_1D8], rcx
0x18002316e  mov     [r11-1A0h], r12d
0x180023175  lea     edi, [r12+2]
0x18002317a  mov     [rsp+238h+var_19C], edi
0x180023181  mov     [r11-198h], r12b
0x180023188  movups  [rsp+238h+var_190], xmm0
0x180023190  movups  [rsp+238h+var_180], xmm1
0x180023198  movups  [rsp+238h+var_170], xmm2
0x1800231a0  movups  [rsp+238h+var_160], xmm3
0x1800231a8  movups  [rsp+238h+var_150], xmm4
0x1800231b0  movups  [rsp+238h+var_140], xmm5
0x1800231b8  movups  [rsp+238h+var_130], xmm6
0x1800231c0  movups  [rsp+238h+var_120], xmm7
0x1800231c8  movups  xmmword ptr [r11-110h], xmm8
0x1800231d0  movups  xmmword ptr [r11-100h], xmm9
0x1800231d8  movups  xmmword ptr [r11-0F0h], xmm10
0x1800231e0  movups  xmmword ptr [r11-0E0h], xmm11
0x1800231e8  mov     [r11-0D0h], rax
0x1800231ef  mov     [r11-0C8h], rdx
0x1800231f6  mov     [r11-0C0h], r8
0x1800231fd  mov     [r11-0B8h], r9
0x180023204  xorps   xmm0, xmm0
0x180023207  movdqu  [rsp+238h+var_1F8], xmm0
0x18002320d  mov     [rsp+238h+var_1E8], r12
0x180023212  lea     rax, [rsp+238h+var_1D8]
0x180023217  mov     [rsp+238h+var_210], rax
0x18002321c  lea     rax, [rsp+238h+var_1F8]
0x180023221  mov     [rsp+238h+var_208], rax
0x180023226  lea     rcx, [rsp+238h+var_210]
0x18002322b  call    wil__ResultFromException__lambda_258e501501491fcf521dd258d2fe6baa___
0x180023230  mov     ebx, eax
0x180023232  test    eax, eax
0x180023234  jns     short loc_18002326D
0x180023236  mov     rcx, [rsp+238h]; this
0x18002323e  mov     r9d, eax; char *
0x180023241  lea     r8, aOnecoreShellCp_1; "onecore\\shell\\cpls\\internationalsett"...
0x180023248  mov     edx, 1FFh; void *
0x18002324d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023252  lea     rcx, [rsp+238h+var_1F8]
0x180023257  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18002325c  lea     rcx, [rsp+238h+var_1D8]; this
0x180023261  call    ??1CWinTaskHandler@@MEAA@XZ; CWinTaskHandler::~CWinTaskHandler(void)
0x180023266  mov     eax, ebx
0x180023268  jmp     loc_1800234FE
0x18002326d  mov     rax, qword ptr [rsp+238h+var_1F8]
0x180023272  cmp     rax, qword ptr [rsp+238h+var_1F8+8]
0x180023277  jnz     short loc_180023294
0x180023279  lea     rcx, [rsp+238h+var_1F8]
0x18002327e  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180023283  lea     rcx, [rsp+238h+var_1D8]; this
0x180023288  call    ??1CWinTaskHandler@@MEAA@XZ; CWinTaskHandler::~CWinTaskHandler(void)
0x18002328d  xor     eax, eax
0x18002328f  jmp     loc_1800234FE
0x180023294  mov     esi, 8
0x180023299  mov     r14, rdi
0x18002329c  mov     r15, r12
0x18002329f  mov     rcx, [rax+10h]
0x1800232a3  test    rcx, rcx
0x1800232a6  jz      short loc_1800232B6
0x1800232a8  add     rsi, 8
0x1800232ac  lea     r14, [r14+rcx*2]
0x1800232b0  add     r14, rdi
0x1800232b3  inc     r15
0x1800232b6  add     rax, 20h ; ' '
0x1800232ba  cmp     rax, qword ptr [rsp+238h+var_1F8+8]
0x1800232bf  jnz     short loc_18002329F
0x1800232c1  lea     rbx, [r14+rsi]
0x1800232c5  mov     rcx, rbx; cb
0x1800232c8  call    cs:__imp_CoTaskMemAlloc
0x1800232ce  mov     rdi, rax
0x1800232d1  test    rax, rax
0x1800232d4  jnz     short loc_180023312
0x1800232d6  mov     rcx, [rsp+238h]; this
0x1800232de  mov     ebx, 8007000Eh
0x1800232e3  mov     r9d, ebx; char *
0x1800232e6  lea     r8, aOnecoreShellCp_1; "onecore\\shell\\cpls\\internationalsett"...
0x1800232ed  mov     edx, 217h; void *
0x1800232f2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800232f7  lea     rcx, [rsp+238h+var_1F8]
0x1800232fc  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180023301  lea     rcx, [rsp+238h+var_1D8]; this
0x180023306  call    ??1CWinTaskHandler@@MEAA@XZ; CWinTaskHandler::~CWinTaskHandler(void)
0x18002330b  mov     eax, ebx
0x18002330d  jmp     loc_1800234FE
0x180023312  mov     r8, rbx; Size
0x180023315  xor     edx, edx; Val
0x180023317  mov     rcx, rdi; void *
0x18002331a  call    memset_0
0x18002331f  mov     r11, rdi
0x180023322  lea     r10, [rdi+rsi]
0x180023326  mov     rdx, qword ptr [rsp+238h+var_1F8]
0x18002332b  mov     rax, qword ptr [rsp+238h+var_1F8+8]
0x180023330  mov     [rsp+238h+var_210], rax
0x180023335  cmp     rdx, rax
0x180023338  jz      loc_180023446
0x18002333e  cmp     [rdx+10h], r12
0x180023342  jz      loc_1800233E8
0x180023348  mov     [r11], r10
0x18002334b  mov     r8, [rdx+10h]
0x18002334f  inc     r8
0x180023352  cmp     qword ptr [rdx+18h], 7
0x180023357  jbe     short loc_18002335E
0x180023359  mov     rcx, [rdx]
0x18002335c  jmp     short loc_180023361
0x18002335e  mov     rcx, rdx
0x180023361  test    r8, r8
0x180023364  jz      loc_1800233F8
0x18002336a  cmp     r8, 7FFFFFFFh
0x180023371  ja      short loc_1800233F1
0x180023373  mov     ebx, 7FFFFFFEh
0x180023378  mov     r9, r8
0x18002337b  mov     rax, r10
0x18002337e  test    rbx, rbx
0x180023381  jz      short loc_1800233AC
0x180023383  movzx   r12d, word ptr [rcx]
0x180023387  cmp     r12w, word ptr [rsp+238h+var_218]
0x18002338d  jz      short loc_1800233A9
0x18002338f  add     rcx, 2
0x180023393  mov     [rax], r12w
0x180023397  add     rax, 2
0x18002339b  dec     rbx
0x18002339e  xor     r12d, r12d
0x1800233a1  sub     r9, 1
0x1800233a5  jnz     short loc_18002337E
0x1800233a7  jmp     short loc_1800233AC
0x1800233a9  xor     r12d, r12d
0x1800233ac  lea     rcx, [rax-2]
0x1800233b0  test    r9, r9
0x1800233b3  cmovnz  rcx, rax
0x1800233b7  mov     [rcx], r12w
0x1800233bb  mov     rax, r9
0x1800233be  neg     rax
0x1800233c1  sbb     ebx, ebx
0x1800233c3  not     ebx
0x1800233c5  and     ebx, 8007007Ah
0x1800233cb  test    r9, r9
0x1800233ce  jz      short loc_180023406
0x1800233d0  add     r11, 8
0x1800233d4  sub     rsi, 8
0x1800233d8  lea     r10, [r10+r8*2]
0x1800233dc  imul    rax, r8, -2
0x1800233e0  add     r14, rax
0x1800233e3  mov     rax, [rsp+238h+var_210]
0x1800233e8  add     rdx, 20h ; ' '
0x1800233ec  jmp     loc_180023335
0x1800233f1  mov     ebx, 80070057h
0x1800233f6  jmp     short loc_180023402
0x1800233f8  mov     ebx, 80070057h
0x1800233fd  test    r8, r8
0x180023400  jz      short loc_180023406
0x180023402  mov     [r10], r12w
0x180023406  mov     rcx, [rsp+238h]; this
0x18002340e  mov     r9d, ebx; char *
0x180023411  lea     r8, aOnecoreShellCp_1; "onecore\\shell\\cpls\\internationalsett"...
0x180023418  mov     edx, 228h; void *
0x18002341d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023422  mov     rcx, rdi; pv
0x180023425  call    cs:__imp_CoTaskMemFree
0x18002342b  lea     rcx, [rsp+238h+var_1F8]
0x180023430  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180023435  lea     rcx, [rsp+238h+var_1D8]; this
0x18002343a  call    ??1CWinTaskHandler@@MEAA@XZ; CWinTaskHandler::~CWinTaskHandler(void)
0x18002343f  mov     eax, ebx
0x180023441  jmp     loc_1800234FE
0x180023446  cmp     rsi, 8
0x18002344a  jz      short loc_18002348E
0x18002344c  mov     rcx, [rsp+238h]; this
0x180023454  mov     ebx, 8000FFFFh
0x180023459  mov     r9d, ebx; char *
0x18002345c  lea     r8, aOnecoreShellCp_1; "onecore\\shell\\cpls\\internationalsett"...
0x180023463  mov     edx, 22Fh; void *
0x180023468  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002346d  mov     rcx, rdi; pv
0x180023470  call    cs:__imp_CoTaskMemFree
0x180023476  lea     rcx, [rsp+238h+var_1F8]
0x18002347b  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180023480  lea     rcx, [rsp+238h+var_1D8]; this
0x180023485  call    ??1CWinTaskHandler@@MEAA@XZ; CWinTaskHandler::~CWinTaskHandler(void)
0x18002348a  mov     eax, ebx
0x18002348c  jmp     short loc_1800234FE
0x18002348e  cmp     r14, 2
0x180023492  jz      short loc_1800234D6
0x180023494  mov     rcx, [rsp+238h]; this
0x18002349c  mov     ebx, 8000FFFFh
0x1800234a1  mov     r9d, ebx; char *
0x1800234a4  lea     r8, aOnecoreShellCp_1; "onecore\\shell\\cpls\\internationalsett"...
0x1800234ab  mov     edx, 230h; void *
0x1800234b0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800234b5  mov     rcx, rdi; pv
0x1800234b8  call    cs:__imp_CoTaskMemFree
0x1800234be  lea     rcx, [rsp+238h+var_1F8]
0x1800234c3  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800234c8  lea     rcx, [rsp+238h+var_1D8]; this
0x1800234cd  call    ??1CWinTaskHandler@@MEAA@XZ; CWinTaskHandler::~CWinTaskHandler(void)
0x1800234d2  mov     eax, ebx
0x1800234d4  jmp     short loc_1800234FE
0x1800234d6  mov     [r13+0], rdi
0x1800234da  mov     rax, [rsp+238h+var_200]
0x1800234df  mov     [rax], r15d
0x1800234e2  lea     rcx, [rsp+238h+var_1F8]
0x1800234e7  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800234ec  lea     rcx, [rsp+238h+var_1D8]; this
0x1800234f1  call    ??1CWinTaskHandler@@MEAA@XZ; CWinTaskHandler::~CWinTaskHandler(void)
0x1800234f6  xor     eax, eax
0x1800234f8  jmp     short loc_1800234FE
0x1800234fa  mov     eax, [rsp+238h+var_218]
0x1800234fe  mov     rcx, [rsp+238h+var_A8]
0x180023506  xor     rcx, rsp; StackCookie
0x180023509  call    __security_check_cookie
0x18002350e  lea     r11, [rsp+238h+var_38]
0x180023516  movaps  xmm6, xmmword ptr [r11-10h]
0x18002351b  movaps  xmm7, xmmword ptr [r11-20h]
0x180023520  movaps  xmm8, xmmword ptr [r11-30h]
0x180023525  movaps  xmm9, xmmword ptr [r11-40h]
0x18002352a  movaps  xmm10, xmmword ptr [r11-50h]
0x18002352f  movaps  xmm11, xmmword ptr [r11-60h]
0x180023534  mov     rsp, r11
0x180023537  pop     r15
0x180023539  pop     r14
0x18002353b  pop     r13
0x18002353d  pop     r12
0x18002353f  pop     rdi
0x180023540  pop     rsi
0x180023541  pop     rbx
0x180023542  retn
```
