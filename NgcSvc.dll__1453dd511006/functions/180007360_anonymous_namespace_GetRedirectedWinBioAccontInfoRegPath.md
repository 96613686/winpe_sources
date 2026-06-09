# _anonymous_namespace_::GetRedirectedWinBioAccontInfoRegPath

- ea: `0x180007360`
- end: `0x180007826`
- name: `_anonymous_namespace_::GetRedirectedWinBioAccontInfoRegPath`
- size: `1222`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800448a0`
- `0x1800896c0`

## callees

- `0x180007360`
- `0x18000782c`
- `0x1800164b0`
- `0x180048304`
- `0x180049a90`
- `0x18005dd38`
- `0x180062abc`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007442`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800074ce`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007527`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000772e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007757`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000778a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800077e4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007442`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800074ce`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007527`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000772e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007757`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000778a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800077e4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800073b7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007606`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800073b7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007606`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18000739c`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x1800074a2`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18000739c`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x1800074a2`

## string_xrefs

- `0x180007415`: `onecore\ds\security\ngc\utils\common\lib\stringutils.cpp`
- `0x18000771a`: `onecore\ds\security\ngc\utils\common\lib\stringutils.cpp`
- `0x180007743`: `onecore\ds\security\ngc\utils\common\lib\stringutils.cpp`
- `0x1800077d0`: `onecore\ds\security\ngc\utils\common\lib\stringutils.cpp`
- `0x1800073d6`: `onecore\ds\security\ngc\utils\common\lib\registryutils.cpp`
- `0x18000742e`: `onecore\ds\security\ngc\utils\common\lib\registryutils.cpp`
- `0x1800074b8`: `onecore\ds\security\ngc\utils\common\lib\registryutils.cpp`
- `0x180007594`: `onecore\ds\security\ngc\utils\common\lib\registryutils.cpp`
- `0x180007450`: `onecore\ds\security\ngc\utils\bio\lib\securebioutils.cpp`
- `0x1800077af`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall anonymous_namespace_::GetRedirectedWinBioAccontInfoRegPath(char **a1)
{
  unsigned __int16 *v2; // rsi
  int PersistedRegistryLocationW; // eax
  __int64 v4; // r8
  unsigned int v5; // edi
  __int64 v6; // rdi
  _BYTE *v7; // rax
  _WORD *v8; // rbx
  __int64 v9; // r8
  __int64 v10; // rcx
  _WORD *v11; // rax
  __int64 v12; // rdx
  _BYTE *i; // r8
  unsigned int v15; // eax
  unsigned __int64 v16; // rdx
  unsigned __int64 v17; // rax
  char *v18; // rdi
  __int64 v19; // rbx
  __int64 v20; // rdx
  const unsigned __int16 *v21; // rsi
  const unsigned __int16 *v22; // rax
  const char *v23; // r9
  const unsigned __int16 *v24; // rax
  unsigned __int64 v25; // rbp
  unsigned __int16 *v26; // r14
  __int64 v27; // r10
  __int64 v28; // rcx
  unsigned __int16 *v29; // rdx
  unsigned __int64 v30; // r8
  unsigned __int16 *v31; // r9
  unsigned __int16 v32; // ax
  unsigned __int16 *v33; // rcx
  unsigned __int64 v34; // rcx
  unsigned __int16 *v35; // rax
  unsigned __int64 v36; // rdx
  unsigned __int16 *v37; // r8
  unsigned __int16 v38; // ax
  unsigned __int16 *v39; // rcx
  int v40; // eax
  int v41; // [rsp+20h] [rbp-38h]
  int v42; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  SIZE_T uBytes; // [rsp+68h] [rbp+10h] BYREF
  unsigned __int16 *v45; // [rsp+70h] [rbp+18h]

  v2 = 0;
  v45 = 0;
  LODWORD(uBytes) = 0;
  PersistedRegistryLocationW = GetPersistedRegistryLocationW(
                                 L"WinBio",
                                 L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WinBio\\",
                                 0,
                                 0);
  v5 = PersistedRegistryLocationW;
  if ( PersistedRegistryLocationW != 234 )
  {
    if ( PersistedRegistryLocationW > 0 )
      v5 = (unsigned __int16)PersistedRegistryLocationW | 0x80070000;
    if ( (v5 & 0x80000000) == 0 )
      goto LABEL_15;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB6,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\registryutils.cpp",
      (const char *)v5,
      (int)&uBytes);
    goto LABEL_14;
  }
  v6 = (unsigned int)uBytes;
  v7 = LocalAlloc(0, (unsigned int)uBytes);
  v8 = v7;
  if ( !v7 )
  {
    v5 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB9,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\registryutils.cpp",
      (const char *)0x8007000ELL,
      (int)&uBytes);
LABEL_10:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x20,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\bio\\lib\\securebioutils.cpp",
      (const char *)v5,
      v41);
    return v5;
  }
  for ( i = &v7[v6]; v7 != i; ++v7 )
    *v7 = 0;
  v15 = GetPersistedRegistryLocationW(
          L"WinBio",
          L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WinBio\\",
          v8,
          (unsigned int)uBytes);
  if ( !v15 )
  {
    v9 = 260;
    v10 = 260;
    v11 = v8;
    while ( *v11 )
    {
      ++v11;
      if ( !--v10 )
      {
        v5 = -2147024809;
        v12 = 179;
        goto LABEL_8;
      }
    }
    v20 = 260;
    v21 = L"\\";
    v22 = L"\\";
    v23 = (const char *)(260 - v10);
    while ( *v22 )
    {
      ++v22;
      if ( !--v20 )
      {
        v5 = -2147024809;
        v12 = 185;
        goto LABEL_8;
      }
    }
    v24 = L"AccountInfo\\";
    while ( *v24 )
    {
      ++v24;
      if ( !--v9 )
      {
        v5 = -2147024809;
        v12 = 191;
        goto LABEL_8;
      }
    }
    v25 = (unsigned __int64)&v23[260 - v20 - v9 + 261];
    if ( v25 == -1 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xF89,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v23);
    v26 = (unsigned __int16 *)LocalAlloc(0, 2 * v25 + 2);
    if ( v26 )
    {
      *v26 = 0;
      v26[v25] = 0;
      if ( v25 )
      {
        if ( v25 > 0x7FFFFFFF )
        {
          v5 = -2147024809;
          *v26 = 0;
        }
        else
        {
          v27 = 2147483646;
          v28 = 2147483646;
          v29 = v8;
          v30 = v25;
          v31 = v26;
          do
          {
            if ( !v28 )
              break;
            v32 = *v29;
            if ( !*v29 )
              break;
            ++v29;
            *v31++ = v32;
            --v28;
            --v30;
          }
          while ( v30 );
          v33 = v31 - 1;
          if ( v30 )
            v33 = v31;
          *v33 = 0;
          v5 = -2147024774;
          if ( v30 )
          {
            v34 = v25;
            v35 = v26;
            do
            {
              if ( !*v35 )
                break;
              ++v35;
              --v34;
            }
            while ( v34 );
            v5 = -2147024809;
            if ( !v34 )
              goto LABEL_61;
            v36 = v34;
            v37 = &v26[v25 - v34];
            if ( v25 != v25 - v34 )
            {
              do
              {
                if ( !v27 )
                  break;
                v38 = *v21;
                if ( !*v21 )
                  break;
                ++v21;
                *v37++ = v38;
                --v27;
                --v36;
              }
              while ( v36 );
            }
            v5 = -2147024774;
            if ( v36 )
              v5 = 0;
            v39 = v37 - 1;
            if ( v36 )
              v39 = v37;
            *v39 = 0;
            if ( v36 )
            {
              v40 = StringCchCatW(v26, v25, L"AccountInfo\\");
              v5 = v40;
              if ( v40 >= 0 )
              {
                v2 = v26;
                v45 = v26;
                LocalFree(v8);
                goto LABEL_15;
              }
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xD7,
                (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\stringutils.cpp",
                (const char *)(unsigned int)v40,
                (int)&uBytes);
              LocalFree(v26);
            }
            else
            {
LABEL_61:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xD2,
                (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\stringutils.cpp",
                (const char *)v5,
                (int)&uBytes);
              LocalFree(v26);
            }
LABEL_9:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xC9,
              (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\registryutils.cpp",
              (const char *)v5,
              v42);
            LocalFree(v8);
            goto LABEL_10;
          }
        }
      }
      else
      {
        v5 = -2147024809;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xCD,
        (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\stringutils.cpp",
        (const char *)v5,
        (int)&uBytes);
      LocalFree(v26);
      goto LABEL_9;
    }
    v5 = -2147024882;
    v12 = 199;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\stringutils.cpp",
      (const char *)v5,
      (int)&uBytes);
    goto LABEL_9;
  }
  v5 = wil::details::in1diag3::Return_Win32(
         retaddr,
         (void *)0xC0,
         (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\registryutils.cpp",
         (const char *)v15,
         (unsigned int)&uBytes);
  LocalFree(v8);
LABEL_14:
  if ( (v5 & 0x80000000) != 0 )
    goto LABEL_10;
LABEL_15:
  v16 = -1;
  do
    ++v16;
  while ( v2[v16] );
  v17 = (unsigned __int64)a1[3];
  if ( v16 > v17 )
  {
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(a1, v16, v4, v2);
  }
  else
  {
    if ( v17 <= 7 )
      v18 = (char *)a1;
    else
      v18 = *a1;
    a1[2] = (char *)v16;
    v19 = 2 * v16;
    memmove_0(v18, v2, 2 * v16);
    *(_WORD *)&v18[v19] = 0;
  }
  if ( v2 )
    LocalFree(v2);
  return 0;
}

```

## disassembly

```asm
0x180007360  mov     [rsp+arg_0], rbx
0x180007365  push    rbp
0x180007366  push    rsi
0x180007367  push    rdi
0x180007368  push    r14
0x18000736a  push    r15
0x18000736c  sub     rsp, 30h
0x180007370  mov     r15, rcx
0x180007373  xor     esi, esi
0x180007375  mov     [rsp+58h+arg_10], rsi
0x18000737a  mov     dword ptr [rsp+58h+uBytes], esi
0x18000737e  lea     rax, [rsp+58h+uBytes]
0x180007383  mov     qword ptr [rsp+58h+var_38], rax; int
0x180007388  xor     r9d, r9d
0x18000738b  xor     r8d, r8d
0x18000738e  lea     rdx, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180007395  lea     rcx, aWinbio; "WinBio"
0x18000739c  call    cs:__imp_GetPersistedRegistryLocationW
0x1800073a2  mov     edi, eax
0x1800073a4  cmp     eax, 0EAh
0x1800073a9  jnz     loc_180007577
0x1800073af  mov     edi, dword ptr [rsp+58h+uBytes]
0x1800073b3  mov     edx, edi; uBytes
0x1800073b5  xor     ecx, ecx; uFlags
0x1800073b7  call    cs:__imp_LocalAlloc
0x1800073bd  mov     rbx, rax
0x1800073c0  test    rax, rax
0x1800073c3  jnz     loc_180007475
0x1800073c9  mov     rcx, [rsp+58h]; this
0x1800073ce  mov     edi, 8007000Eh
0x1800073d3  mov     r9d, edi; char *
0x1800073d6  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x1800073dd  mov     edx, 0B9h; void *
0x1800073e2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800073e7  jmp     short loc_180007448
0x1800073e9  mov     r8d, 104h
0x1800073ef  mov     ecx, r8d
0x1800073f2  mov     rax, rbx
0x1800073f5  cmp     [rax], si
0x1800073f8  jz      loc_180007545
0x1800073fe  add     rax, 2
0x180007402  sub     rcx, 1
0x180007406  jnz     short loc_1800073F5
0x180007408  mov     edi, 80070057h
0x18000740d  mov     edx, 0B3h; void *
0x180007412  mov     r9d, edi; char *
0x180007415  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18000741c  mov     rcx, [rsp+58h]; this
0x180007421  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007426  mov     rcx, [rsp+58h]; this
0x18000742b  mov     r9d, edi; char *
0x18000742e  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180007435  mov     edx, 0C9h; void *
0x18000743a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000743f  mov     rcx, rbx; hMem
0x180007442  call    cs:__imp_LocalFree
0x180007448  mov     rcx, [rsp+58h]; this
0x18000744d  mov     r9d, edi; char *
0x180007450  lea     r8, aOnecoreDsSecur_40; "onecore\\ds\\security\\ngc\\utils\\bio"...
0x180007457  mov     edx, 20h ; ' '; void *
0x18000745c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007461  nop
0x180007462  mov     eax, edi
0x180007464  mov     rbx, [rsp+58h+arg_0]
0x180007469  add     rsp, 30h
0x18000746d  pop     r15
0x18000746f  pop     r14
0x180007471  pop     rdi
0x180007472  pop     rsi
0x180007473  pop     rbp
0x180007474  retn
0x180007475  lea     r8, [rax+rdi]
0x180007479  cmp     rbx, r8
0x18000747c  jnz     loc_180007795
0x180007482  lea     rax, [rsp+58h+uBytes]
0x180007487  mov     qword ptr [rsp+58h+var_38], rax; int
0x18000748c  mov     r9d, dword ptr [rsp+58h+uBytes]
0x180007491  mov     r8, rbx
0x180007494  lea     rdx, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18000749b  lea     rcx, aWinbio; "WinBio"
0x1800074a2  call    cs:__imp_GetPersistedRegistryLocationW
0x1800074a8  test    eax, eax
0x1800074aa  jz      loc_1800073E9
0x1800074b0  mov     rcx, [rsp+58h]; this
0x1800074b5  mov     r9d, eax; char *
0x1800074b8  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x1800074bf  mov     edx, 0C0h; void *
0x1800074c4  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800074c9  mov     edi, eax
0x1800074cb  mov     rcx, rbx; hMem
0x1800074ce  call    cs:__imp_LocalFree
0x1800074d4  test    edi, edi
0x1800074d6  js      loc_180007448
0x1800074dc  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x1800074e3  inc     rdx
0x1800074e6  cmp     word ptr [rsi+rdx*2], 0
0x1800074eb  jnz     short loc_1800074E3
0x1800074ed  mov     rax, [r15+18h]
0x1800074f1  cmp     rdx, rax
0x1800074f4  ja      loc_180007806
0x1800074fa  cmp     rax, 7
0x1800074fe  jbe     short loc_180007540
0x180007500  mov     rdi, [r15]
0x180007503  mov     [r15+10h], rdx
0x180007507  lea     rbx, [rdx+rdx]
0x18000750b  mov     r8, rbx; Size
0x18000750e  mov     rdx, rsi; Src
0x180007511  mov     rcx, rdi; void *
0x180007514  call    memmove_0
0x180007519  xor     eax, eax
0x18000751b  mov     [rdi+rbx], ax
0x18000751f  test    rsi, rsi
0x180007522  jz      short loc_18000752D
0x180007524  mov     rcx, rsi; hMem
0x180007527  call    cs:__imp_LocalFree
0x18000752d  xor     eax, eax
0x18000752f  mov     rbx, [rsp+58h+arg_0]
0x180007534  add     rsp, 30h
0x180007538  pop     r15
0x18000753a  pop     r14
0x18000753c  pop     rdi
0x18000753d  pop     rsi
0x18000753e  pop     rbp
0x18000753f  retn
0x180007540  mov     rdi, r15
0x180007543  jmp     short loc_180007503
0x180007545  mov     rdx, r8
0x180007548  lea     rsi, asc_1800DB4FC; "\\"
0x18000754f  mov     rax, rsi
0x180007552  mov     r9, r8
0x180007555  sub     r9, rcx; char *
0x180007558  cmp     word ptr [rax], 0
0x18000755c  jz      short loc_1800075AA
0x18000755e  add     rax, 2
0x180007562  sub     rdx, 1
0x180007566  jnz     short loc_180007558
0x180007568  mov     edi, 80070057h
0x18000756d  mov     edx, 0B9h
0x180007572  jmp     loc_180007412
0x180007577  test    eax, eax
0x180007579  jle     short loc_180007584
0x18000757b  movzx   edi, ax
0x18000757e  or      edi, 80070000h
0x180007584  test    edi, edi
0x180007586  jns     loc_1800074DC
0x18000758c  mov     rcx, [rsp+58h]; this
0x180007591  mov     r9d, edi; char *
0x180007594  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18000759b  mov     edx, 0B6h; void *
0x1800075a0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800075a5  jmp     loc_1800074D4
0x1800075aa  lea     rax, aAccountinfo; "AccountInfo\\"
0x1800075b1  mov     rcx, r8
0x1800075b4  sub     rcx, rdx
0x1800075b7  cmp     word ptr [rax], 0
0x1800075bb  jz      short loc_1800075D6
0x1800075bd  add     rax, 2
0x1800075c1  sub     r8, 1
0x1800075c5  jnz     short loc_1800075B7
0x1800075c7  mov     edi, 80070057h
0x1800075cc  mov     edx, 0BFh
0x1800075d1  jmp     loc_180007412
0x1800075d6  sub     rcx, r8
0x1800075d9  lea     rbp, [rcx+105h]
0x1800075e0  add     rbp, r9
0x1800075e3  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x1800075e7  jnz     loc_1800077A8
0x1800075ed  mov     al, 1
0x1800075ef  mov     rcx, [rsp+58h]; this
0x1800075f4  test    al, al
0x1800075f6  jnz     loc_1800077AF
0x1800075fc  lea     rdx, ds:2[rbp*2]; uBytes
0x180007604  xor     ecx, ecx; uFlags
0x180007606  call    cs:__imp_LocalAlloc
0x18000760c  mov     r14, rax
0x18000760f  test    rax, rax
0x180007612  jz      loc_180007816
0x180007618  xor     eax, eax
0x18000761a  mov     [r14], ax
0x18000761e  mov     [r14+rbp*2], ax
0x180007623  test    rbp, rbp
0x180007626  jz      loc_1800077EF
0x18000762c  cmp     rbp, 7FFFFFFFh
0x180007633  ja      loc_1800077C1
0x180007639  mov     r10d, 7FFFFFFEh
0x18000763f  mov     ecx, r10d
0x180007642  mov     rdx, rbx
0x180007645  mov     r8, rbp
0x180007648  mov     r9, r14
0x18000764b  nop     dword ptr [rax+rax+00h]
0x180007650  test    rcx, rcx
0x180007653  jz      short loc_180007672
0x180007655  movzx   eax, word ptr [rdx]
0x180007658  test    ax, ax
0x18000765b  jz      short loc_180007672
0x18000765d  add     rdx, 2
0x180007661  mov     [r9], ax
0x180007665  add     r9, 2
0x180007669  dec     rcx
0x18000766c  sub     r8, 1
0x180007670  jnz     short loc_180007650
0x180007672  lea     rcx, [r9-2]
0x180007676  test    r8, r8
0x180007679  cmovnz  rcx, r9
0x18000767d  xor     eax, eax
0x18000767f  mov     [rcx], ax
0x180007682  mov     edi, 8007007Ah
0x180007687  test    r8, r8
0x18000768a  cmovnz  edi, eax
0x18000768d  jz      loc_180007739
0x180007693  mov     rcx, rbp
0x180007696  mov     rax, r14
0x180007699  nop     dword ptr [rax+00000000h]
0x1800076a0  cmp     word ptr [rax], 0
0x1800076a4  jz      short loc_1800076B0
0x1800076a6  add     rax, 2
0x1800076aa  sub     rcx, 1
0x1800076ae  jnz     short loc_1800076A0
0x1800076b0  mov     edi, 80070057h
0x1800076b5  xor     eax, eax
0x1800076b7  test    rcx, rcx
0x1800076ba  cmovnz  edi, eax
0x1800076bd  jz      short loc_180007712
0x1800076bf  mov     rax, rbp
0x1800076c2  sub     rax, rcx
0x1800076c5  test    rcx, rcx
0x1800076c8  jz      short loc_180007712
0x1800076ca  mov     rdx, rbp
0x1800076cd  sub     rdx, rax
0x1800076d0  lea     r8, [r14+rax*2]
0x1800076d4  jz      short loc_1800076F8
0x1800076d6  test    r10, r10
0x1800076d9  jz      short loc_1800076F8
0x1800076db  movzx   eax, word ptr [rsi]
0x1800076de  test    ax, ax
0x1800076e1  jz      short loc_1800076F8
0x1800076e3  add     rsi, 2
0x1800076e7  mov     [r8], ax
0x1800076eb  add     r8, 2
0x1800076ef  dec     r10
0x1800076f2  sub     rdx, 1
0x1800076f6  jnz     short loc_1800076D6
0x1800076f8  mov     edi, 8007007Ah
0x1800076fd  xor     eax, eax
0x1800076ff  test    rdx, rdx
0x180007702  cmovnz  edi, eax
0x180007705  lea     rcx, [r8-2]
0x180007709  cmovnz  rcx, r8
0x18000770d  mov     [rcx], ax
0x180007710  jnz     short loc_180007767
0x180007712  mov     rcx, [rsp+58h]; this
0x180007717  mov     r9d, edi; char *
0x18000771a  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180007721  mov     edx, 0D2h; void *
0x180007726  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000772b  mov     rcx, r14; hMem
0x18000772e  call    cs:__imp_LocalFree
0x180007734  jmp     loc_180007426
0x180007739  xor     esi, esi
0x18000773b  mov     rcx, [rsp+58h]; this
0x180007740  mov     r9d, edi; char *
0x180007743  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18000774a  mov     edx, 0CDh; void *
0x18000774f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007754  mov     rcx, r14; hMem
0x180007757  call    cs:__imp_LocalFree
0x18000775d  test    edi, edi
0x18000775f  js      loc_180007426
0x180007765  jmp     short loc_180007782
0x180007767  lea     r8, aAccountinfo; "AccountInfo\\"
0x18000776e  mov     rdx, rbp; unsigned __int64
0x180007771  mov     rcx, r14; unsigned __int16 *
0x180007774  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180007779  mov     edi, eax
0x18000777b  test    eax, eax
0x18000777d  js      short loc_1800077C8
0x18000777f  mov     rsi, r14
0x180007782  mov     [rsp+58h+arg_10], rsi
0x180007787  mov     rcx, rbx; hMem
0x18000778a  call    cs:__imp_LocalFree
0x180007790  jmp     loc_1800074DC
0x180007795  xor     r9d, r9d
0x180007798  mov     [rax], r9b
0x18000779b  inc     rax
0x18000779e  cmp     rax, r8
0x1800077a1  jnz     short loc_180007795
0x1800077a3  jmp     loc_180007482
0x1800077a8  xor     al, al
0x1800077aa  jmp     loc_1800075EF
0x1800077af  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800077b6  mov     edx, 0F89h; void *
0x1800077bb  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800077c1  mov     edi, 80070057h
0x1800077c6  jmp     short loc_1800077FD
0x1800077c8  mov     rcx, [rsp+58h]; this
0x1800077cd  mov     r9d, eax; char *
0x1800077d0  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x1800077d7  mov     edx, 0D7h; void *
0x1800077dc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800077e1  mov     rcx, r14; hMem
  ... truncated ...
```
