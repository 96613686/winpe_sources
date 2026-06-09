# AppCompatUtility::CompareStrEx(int *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180040224`
- end: `0x1800405ab`
- name: `?CompareStrEx@AppCompatUtility@@YAJPEAHAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@111@Z`
- size: `903`
- prototype: ``
- caller_count: `4`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180020680`
- `0x1800225d4`
- `0x180032dc0`
- `0x180042764`

## callees

- `0x18003fdf0`
- `0x18003ffb4`
- `0x180040148`
- `0x180040224`
- `0x1800405b4`
- `0x1800434b8`
- `0x1800543c0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180040297`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800402ca`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800403bc`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180040511`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180040297`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800402ca`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800403bc`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180040511`
- `api-ms-win-crt-private-l1-1-0!_o_wcstod` at `0x1800403dd`
- `api-ms-win-crt-private-l1-1-0!_o_wcstod` at `0x18004046f`
- `api-ms-win-crt-private-l1-1-0!_o_wcstod` at `0x1800403dd`
- `api-ms-win-crt-private-l1-1-0!_o_wcstod` at `0x18004046f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18004042c`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180040437`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800404aa`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800404b5`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18004042c`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180040437`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800404aa`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800404b5`
- `SHLWAPI!StrToInt64ExW` at `0x1800402f0`
- `SHLWAPI!StrToInt64ExW` at `0x180040369`
- `SHLWAPI!StrToInt64ExW` at `0x1800402f0`
- `SHLWAPI!StrToInt64ExW` at `0x180040369`

## string_xrefs

- `0x180040316`: `AppCompatUtility::CompareStrEx`
- `0x180040416`: `AppCompatUtility::CompareStrEx`
- `0x18004054d`: `AppCompatUtility::CompareStrEx`

## pseudocode

```c
__int64 __fastcall AppCompatUtility::CompareStrEx(_DWORD *a1, __int64 *a2, __int64 *a3, __int64 a4, _QWORD *a5)
{
  _QWORD *v5; // r14
  bool v9; // cc
  unsigned int v11; // esi
  _QWORD *v12; // rdx
  int v13; // eax
  _QWORD *v14; // rdx
  const WCHAR *v15; // rcx
  const WCHAR *v17; // rcx
  _QWORD *v18; // rdx
  __int64 *v19; // rcx
  __int64 v20; // rcx
  const char *v21; // r9
  __int64 v22; // r8
  __int64 v23; // rcx
  int v24; // ecx
  __int64 *v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rdx
  __int64 v28; // rcx
  int v29; // ecx
  int v30; // [rsp+28h] [rbp-48h]
  __int64 v31; // [rsp+30h] [rbp-40h] BYREF
  __int64 v32; // [rsp+38h] [rbp-38h] BYREF
  LONGLONG pllRet; // [rsp+40h] [rbp-30h] BYREF
  LONGLONG v34; // [rsp+48h] [rbp-28h] BYREF
  unsigned __int16 *v35; // [rsp+A0h] [rbp+30h] BYREF

  v5 = a5;
  pllRet = 0;
  *a1 = 0;
  v9 = v5[3] <= 7u;
  v11 = 0;
  v34 = 0;
  v31 = 0;
  v32 = 0;
  v35 = 0;
  if ( v9 )
    v12 = v5;
  else
    v12 = (_QWORD *)*v5;
  if ( !(unsigned int)_o__wcsicmp(L"wstring", v12) )
  {
    v13 = AppCompatUtility::CompareStr(a2, a3, a4);
LABEL_69:
    *a1 = v13;
    return v11;
  }
  if ( v5[3] <= 7u )
    v14 = v5;
  else
    v14 = (_QWORD *)*v5;
  if ( !(unsigned int)_o__wcsicmp(L"int", v14) )
  {
    if ( (unsigned __int64)a3[3] <= 7 )
      v15 = (const WCHAR *)a3;
    else
      v15 = (const WCHAR *)*a3;
    if ( StrToInt64ExW(v15, 1, &pllRet) )
    {
      if ( (unsigned __int64)a2[3] <= 7 )
        v17 = (const WCHAR *)a2;
      else
        v17 = (const WCHAR *)*a2;
      if ( StrToInt64ExW(v17, 1, &v34) )
      {
        v13 = AppCompatUtility::CompareInt(v34, pllRet, a4);
        goto LABEL_69;
      }
      if ( (unsigned __int64)a2[3] > 7 )
        a2 = (__int64 *)*a2;
      AslLogCallPrintf(1, "AppCompatUtility::CompareStrEx", 153, "Failed to convert result value to integer: '%ls'", a2);
    }
    else
    {
      if ( (unsigned __int64)a3[3] > 7 )
        a3 = (__int64 *)*a3;
      AslLogCallPrintf(
        1,
        "AppCompatUtility::CompareStrEx",
        146,
        "Failed to convert expected value to integer: '%ls'",
        a3);
    }
    return (unsigned int)-2147024809;
  }
  if ( v5[3] <= 7u )
    v18 = v5;
  else
    v18 = (_QWORD *)*v5;
  if ( !(unsigned int)_o__wcsicmp(L"double", v18) )
  {
    if ( (unsigned __int64)a3[3] <= 7 )
      v19 = a3;
    else
      v19 = (__int64 *)*a3;
    _o_wcstod(v19, &v35);
    if ( *v35 )
    {
      if ( (unsigned __int64)a3[3] > 7 )
        a3 = (__int64 *)*a3;
      v21 = "Failed to convert expected value to double: '%ls'. Failed to parse at '%wc'.";
      v30 = *v35;
      v22 = 165;
    }
    else
    {
      if ( !*(_DWORD *)_o__errno(v20) )
      {
        if ( (unsigned __int64)a2[3] <= 7 )
          v25 = a2;
        else
          v25 = (__int64 *)*a2;
        _o_wcstod(v25, &v35);
        if ( *v35 )
        {
          if ( (unsigned __int64)a2[3] > 7 )
            a2 = (__int64 *)*a2;
          AslLogCallPrintf(
            1,
            "AppCompatUtility::CompareStrEx",
            179,
            "Failed to convert result value to double: '%ls'. Failed to parse at '%wc'.",
            a2,
            *v35);
        }
        else
        {
          if ( !*(_DWORD *)_o__errno(v26) )
          {
            v13 = AppCompatUtility::CompareDouble(v28, v27, a4);
            goto LABEL_69;
          }
          v29 = *(_DWORD *)_o__errno(v28);
          if ( (unsigned __int64)a2[3] > 7 )
            a2 = (__int64 *)*a2;
          AslLogCallPrintf(
            1,
            "AppCompatUtility::CompareStrEx",
            184,
            "Failed to convert result value to double: '%ls'. [0x%x]",
            a2,
            v29);
        }
        return (unsigned int)-2147024809;
      }
      v24 = *(_DWORD *)_o__errno(v23);
      if ( (unsigned __int64)a3[3] > 7 )
        a3 = (__int64 *)*a3;
      v30 = v24;
      v21 = "Failed to convert expected value to double: '%ls'. [0x%x]";
      v22 = 171;
    }
    AslLogCallPrintf(1, "AppCompatUtility::CompareStrEx", v22, v21, a3, v30);
    return (unsigned int)-2147024809;
  }
  if ( v5[3] > 7u )
    v5 = (_QWORD *)*v5;
  if ( (unsigned int)_o__wcsicmp(L"version", v5) )
    return (unsigned int)-2147024809;
  v11 = AppCompatUtility::ParseVersionFromString(&v31, a3);
  if ( v11 )
  {
    if ( (unsigned __int64)a3[3] > 7 )
      a3 = (__int64 *)*a3;
    AslLogCallPrintf(1, "AppCompatUtility::CompareStrEx", 197, "Failed to convert expected value to version: '%ls'", a3);
  }
  else
  {
    v11 = AppCompatUtility::ParseVersionFromString(&v32, a2);
    if ( !v11 )
    {
      v13 = AppCompatUtility::CompareVersion(v32, v31, a4);
      goto LABEL_69;
    }
    if ( (unsigned __int64)a2[3] > 7 )
      a2 = (__int64 *)*a2;
    AslLogCallPrintf(1, "AppCompatUtility::CompareStrEx", 204, "Failed to convert result value to version: '%ls'", a2);
  }
  return v11;
}

```

## disassembly

```asm
0x180040224  mov     rax, rsp
0x180040227  mov     [rax+10h], rbx
0x18004022b  mov     [rax+18h], rsi
0x18004022f  push    rbp
0x180040230  push    rdi
0x180040231  push    r12
0x180040233  push    r14
0x180040235  push    r15
0x180040237  mov     rbp, rsp
0x18004023a  sub     rsp, 70h
0x18004023e  mov     r14, [rbp+arg_20]
0x180040242  mov     r15, rcx
0x180040245  xor     ecx, ecx
0x180040247  movaps  xmmword ptr [rax-38h], xmm6
0x18004024b  movaps  xmmword ptr [rax-48h], xmm7
0x18004024f  mov     r12, r9
0x180040252  xor     eax, eax
0x180040254  mov     [rbp+pllRet], rcx
0x180040258  mov     [r15], ecx
0x18004025b  mov     rbx, r8
0x18004025e  cmp     qword ptr [r14+18h], 7
0x180040263  mov     rdi, rdx
0x180040266  mov     esi, ecx
0x180040268  mov     [rbp+var_28], rcx
0x18004026c  mov     word ptr [rbp+var_40], cx
0x180040270  mov     dword ptr [rbp+var_40+2], eax
0x180040273  mov     word ptr [rbp+var_40+6], ax
0x180040277  mov     word ptr [rbp+var_38], cx
0x18004027b  mov     dword ptr [rbp+var_38+2], eax
0x18004027e  mov     word ptr [rbp+var_38+6], ax
0x180040282  mov     [rbp+arg_0], rcx
0x180040286  jbe     short loc_18004028D
0x180040288  mov     rdx, [r14]
0x18004028b  jmp     short loc_180040290
0x18004028d  mov     rdx, r14
0x180040290  lea     rcx, aWstring; "wstring"
0x180040297  call    cs:__imp__o__wcsicmp
0x18004029d  test    eax, eax
0x18004029f  jnz     short loc_1800402B4
0x1800402a1  mov     r8, r12
0x1800402a4  mov     rdx, rbx
0x1800402a7  mov     rcx, rdi
0x1800402aa  call    ?CompareStr@AppCompatUtility@@YAHAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00@Z; AppCompatUtility::CompareStr(std::wstring const &,std::wstring const &,std::wstring const &)
0x1800402af  jmp     loc_1800405A3
0x1800402b4  cmp     qword ptr [r14+18h], 7
0x1800402b9  jbe     short loc_1800402C0
0x1800402bb  mov     rdx, [r14]
0x1800402be  jmp     short loc_1800402C3
0x1800402c0  mov     rdx, r14
0x1800402c3  lea     rcx, aInt; "int"
0x1800402ca  call    cs:__imp__o__wcsicmp
0x1800402d0  test    eax, eax
0x1800402d2  jnz     loc_1800403A6
0x1800402d8  cmp     qword ptr [rbx+18h], 7
0x1800402dd  jbe     short loc_1800402E4
0x1800402df  mov     rcx, [rbx]
0x1800402e2  jmp     short loc_1800402E7
0x1800402e4  mov     rcx, rbx; pszString
0x1800402e7  lea     r8, [rbp+pllRet]; pllRet
0x1800402eb  mov     edx, 1; dwFlags
0x1800402f0  call    cs:__imp_StrToInt64ExW
0x1800402f6  test    eax, eax
0x1800402f8  jnz     short loc_180040351
0x1800402fa  cmp     qword ptr [rbx+18h], 7
0x1800402ff  jbe     short loc_180040304
0x180040301  mov     rbx, [rbx]
0x180040304  mov     [rsp+70h+var_50], rbx
0x180040309  lea     r9, aFailedToConver_22; "Failed to convert expected value to int"...
0x180040310  mov     r8d, 92h
0x180040316  lea     rdx, aAppcompatutili_10; "AppCompatUtility::CompareStrEx"
0x18004031d  mov     ecx, 1
0x180040322  call    AslLogCallPrintf
0x180040327  mov     esi, 80070057h
0x18004032c  movaps  xmm6, [rsp+70h+var_10]
0x180040331  lea     r11, [rsp+70h+var_s0]
0x180040336  mov     rbx, [r11+38h]
0x18004033a  mov     eax, esi
0x18004033c  mov     rsi, [r11+40h]
0x180040340  movaps  xmm7, [rsp+70h+var_20]
0x180040345  mov     rsp, r11
0x180040348  pop     r15
0x18004034a  pop     r14
0x18004034c  pop     r12
0x18004034e  pop     rdi
0x18004034f  pop     rbp
0x180040350  retn
0x180040351  cmp     qword ptr [rdi+18h], 7
0x180040356  jbe     short loc_18004035D
0x180040358  mov     rcx, [rdi]
0x18004035b  jmp     short loc_180040360
0x18004035d  mov     rcx, rdi; pszString
0x180040360  lea     r8, [rbp+var_28]; pllRet
0x180040364  mov     edx, 1; dwFlags
0x180040369  call    cs:__imp_StrToInt64ExW
0x18004036f  test    eax, eax
0x180040371  jnz     short loc_180040391
0x180040373  cmp     qword ptr [rdi+18h], 7
0x180040378  jbe     short loc_18004037D
0x18004037a  mov     rdi, [rdi]
0x18004037d  mov     [rsp+70h+var_50], rdi
0x180040382  lea     r9, aFailedToConver_5; "Failed to convert result value to integ"...
0x180040389  mov     r8d, 99h
0x18004038f  jmp     short loc_180040316
0x180040391  mov     rdx, [rbp+pllRet]
0x180040395  mov     r8, r12
0x180040398  mov     rcx, [rbp+var_28]
0x18004039c  call    ?CompareInt@AppCompatUtility@@YAH_J0AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; AppCompatUtility::CompareInt(__int64,__int64,std::wstring const &)
0x1800403a1  jmp     loc_1800405A3
0x1800403a6  cmp     qword ptr [r14+18h], 7
0x1800403ab  jbe     short loc_1800403B2
0x1800403ad  mov     rdx, [r14]
0x1800403b0  jmp     short loc_1800403B5
0x1800403b2  mov     rdx, r14
0x1800403b5  lea     rcx, aDouble; "double"
0x1800403bc  call    cs:__imp__o__wcsicmp
0x1800403c2  test    eax, eax
0x1800403c4  jnz     loc_1800404FD
0x1800403ca  cmp     qword ptr [rbx+18h], 7
0x1800403cf  jbe     short loc_1800403D6
0x1800403d1  mov     rcx, [rbx]
0x1800403d4  jmp     short loc_1800403D9
0x1800403d6  mov     rcx, rbx
0x1800403d9  lea     rdx, [rbp+arg_0]
0x1800403dd  call    cs:__imp__o_wcstod
0x1800403e3  mov     rax, [rbp+arg_0]
0x1800403e7  xor     r14d, r14d
0x1800403ea  movaps  xmm7, xmm0
0x1800403ed  cmp     [rax], r14w
0x1800403f1  jz      short loc_18004042C
0x1800403f3  cmp     qword ptr [rbx+18h], 7
0x1800403f8  jbe     short loc_1800403FD
0x1800403fa  mov     rbx, [rbx]
0x1800403fd  movzx   eax, word ptr [rax]
0x180040400  lea     r9, aFailedToConver_7; "Failed to convert expected value to dou"...
0x180040407  mov     [rsp+70h+var_48], eax
0x18004040b  mov     r8d, 0A5h
0x180040411  mov     [rsp+70h+var_50], rbx
0x180040416  lea     rdx, aAppcompatutili_10; "AppCompatUtility::CompareStrEx"
0x18004041d  mov     ecx, 1
0x180040422  call    AslLogCallPrintf
0x180040427  jmp     loc_180040327
0x18004042c  call    cs:__imp__o__errno
0x180040432  cmp     [rax], r14d
0x180040435  jz      short loc_18004045C
0x180040437  call    cs:__imp__o__errno
0x18004043d  cmp     qword ptr [rbx+18h], 7
0x180040442  mov     ecx, [rax]
0x180040444  jbe     short loc_180040449
0x180040446  mov     rbx, [rbx]
0x180040449  mov     [rsp+70h+var_48], ecx
0x18004044d  lea     r9, aFailedToConver_2; "Failed to convert expected value to dou"...
0x180040454  mov     r8d, 0ABh
0x18004045a  jmp     short loc_180040411
0x18004045c  cmp     qword ptr [rdi+18h], 7
0x180040461  jbe     short loc_180040468
0x180040463  mov     rcx, [rdi]
0x180040466  jmp     short loc_18004046B
0x180040468  mov     rcx, rdi
0x18004046b  lea     rdx, [rbp+arg_0]
0x18004046f  call    cs:__imp__o_wcstod
0x180040475  mov     rax, [rbp+arg_0]
0x180040479  movaps  xmm6, xmm0
0x18004047c  cmp     [rax], r14w
0x180040480  jz      short loc_1800404AA
0x180040482  cmp     qword ptr [rdi+18h], 7
0x180040487  jbe     short loc_18004048C
0x180040489  mov     rdi, [rdi]
0x18004048c  movzx   eax, word ptr [rax]
0x18004048f  lea     r9, aFailedToConver_13; "Failed to convert result value to doubl"...
0x180040496  mov     [rsp+70h+var_48], eax
0x18004049a  mov     r8d, 0B3h
0x1800404a0  mov     [rsp+70h+var_50], rdi
0x1800404a5  jmp     loc_180040416
0x1800404aa  call    cs:__imp__o__errno
0x1800404b0  cmp     [rax], r14d
0x1800404b3  jz      short loc_1800404E2
0x1800404b5  call    cs:__imp__o__errno
0x1800404bb  cmp     qword ptr [rdi+18h], 7
0x1800404c0  mov     ecx, [rax]
0x1800404c2  jbe     short loc_1800404C7
0x1800404c4  mov     rdi, [rdi]
0x1800404c7  mov     [rsp+70h+var_48], ecx
0x1800404cb  lea     r9, aFailedToConver_11; "Failed to convert result value to doubl"...
0x1800404d2  mov     [rsp+70h+var_50], rdi
0x1800404d7  mov     r8d, 0B8h
0x1800404dd  jmp     loc_180040416
0x1800404e2  movsd   xmm3, cs:__real@3eb0c6f7a0b5ed8d
0x1800404ea  mov     r8, r12
0x1800404ed  movaps  xmm1, xmm7
0x1800404f0  movaps  xmm0, xmm6
0x1800404f3  call    ?CompareDouble@AppCompatUtility@@YAHNNAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@N@Z; AppCompatUtility::CompareDouble(double,double,std::wstring const &,double)
0x1800404f8  jmp     loc_1800405A3
0x1800404fd  cmp     qword ptr [r14+18h], 7
0x180040502  jbe     short loc_180040507
0x180040504  mov     r14, [r14]
0x180040507  mov     rdx, r14
0x18004050a  lea     rcx, aVersion; "version"
0x180040511  call    cs:__imp__o__wcsicmp
0x180040517  test    eax, eax
0x180040519  jnz     loc_180040327
0x18004051f  mov     rdx, rbx
0x180040522  lea     rcx, [rbp+var_40]
0x180040526  call    ?ParseVersionFromString@AppCompatUtility@@YAJAEAT_Version@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; AppCompatUtility::ParseVersionFromString(_Version &,std::wstring const &)
0x18004052b  mov     esi, eax
0x18004052d  test    eax, eax
0x18004052f  jz      short loc_180040563
0x180040531  cmp     qword ptr [rbx+18h], 7
0x180040536  jbe     short loc_18004053B
0x180040538  mov     rbx, [rbx]
0x18004053b  mov     [rsp+70h+var_50], rbx
0x180040540  lea     r9, aFailedToConver_14; "Failed to convert expected value to ver"...
0x180040547  mov     r8d, 0C5h
0x18004054d  lea     rdx, aAppcompatutili_10; "AppCompatUtility::CompareStrEx"
0x180040554  mov     ecx, 1
0x180040559  call    AslLogCallPrintf
0x18004055e  jmp     loc_18004032C
0x180040563  mov     rdx, rdi
0x180040566  lea     rcx, [rbp+var_38]
0x18004056a  call    ?ParseVersionFromString@AppCompatUtility@@YAJAEAT_Version@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; AppCompatUtility::ParseVersionFromString(_Version &,std::wstring const &)
0x18004056f  mov     esi, eax
0x180040571  test    eax, eax
0x180040573  jz      short loc_180040593
0x180040575  cmp     qword ptr [rdi+18h], 7
0x18004057a  jbe     short loc_18004057F
0x18004057c  mov     rdi, [rdi]
0x18004057f  mov     [rsp+70h+var_50], rdi
0x180040584  lea     r9, aFailedToConver_16; "Failed to convert result value to versi"...
0x18004058b  mov     r8d, 0CCh
0x180040591  jmp     short loc_18004054D
0x180040593  mov     rdx, [rbp+var_40]
0x180040597  mov     r8, r12
0x18004059a  mov     rcx, [rbp+var_38]
0x18004059e  call    ?CompareVersion@AppCompatUtility@@YAHT_Version@@0AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; AppCompatUtility::CompareVersion(_Version,_Version,std::wstring const &)
0x1800405a3  mov     [r15], eax
0x1800405a6  jmp     loc_18004032C
```
