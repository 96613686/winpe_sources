# CStartMenuProgramsResultSetManager::_GetProgramsRunResult(uint,_GUID const &,void * *)

- ea: `0x1800354e8`
- end: `0x1800357b1`
- name: `?_GetProgramsRunResult@CStartMenuProgramsResultSetManager@@AEAAJIAEBU_GUID@@PEAPEAX@Z`
- size: `713`
- prototype: `__int64 __fastcall(CStartMenuProgramsResultSetManager *this, int, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180035454`

## callees

- `0x180005460`
- `0x180006900`
- `0x180021e64`
- `0x18002850c`
- `0x18002fa14`
- `0x1800354e8`
- `0x1800357b8`
- `0x18003c020`
- `0x180051010`

## import_xrefs

- `SHCORE!__imp_SHWindowsPolicy` at `0x180035591`
- `SHCORE!__imp_SHWindowsPolicy` at `0x180035591`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003561a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800356da`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003561a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800356da`
- `api-ms-win-core-localization-l1-2-0!LCMapStringEx` at `0x1800355f2`
- `api-ms-win-core-localization-l1-2-0!LCMapStringEx` at `0x1800356ac`
- `api-ms-win-core-localization-l1-2-0!LCMapStringEx` at `0x1800355f2`
- `api-ms-win-core-localization-l1-2-0!LCMapStringEx` at `0x1800356ac`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CStartMenuProgramsResultSetManager::_GetProgramsRunResult(
        CStartMenuProgramsResultSetManager *this,
        int a2,
        const struct _GUID *a3,
        void **a4)
{
  const struct _GUID *v5; // rbx
  char *v8; // r14
  const struct _GUID *v9; // r8
  int v10; // r9d
  _WORD *v11; // rax
  CStartMenuProgramsResultSetManager *v12; // rcx
  int ProgramsRunResultInternal; // edi
  int v14; // ebx
  CStartMenuProgramsResultSetManager *v15; // rcx
  const struct _GUID *v16; // r8
  int v17; // edi
  CStartMenuProgramsResultSetManager *v18; // rcx
  int FirstTwoWordPrefixValuesFromDisjunctiveCondition; // edi
  const struct _GUID *v20; // r8
  const WCHAR *v21; // rbx
  int v22; // r15d
  CStartMenuProgramsResultSetManager *v23; // rcx
  const struct _GUID *v24; // r8
  __int64 (__fastcall ***v25)(_QWORD, const struct _GUID *, void **); // rcx
  unsigned __int16 *v27; // [rsp+50h] [rbp-B0h] BYREF
  LPCWSTR lpSrcStr[2]; // [rsp+58h] [rbp-A8h] BYREF
  const struct _GUID *v29; // [rsp+68h] [rbp-98h] BYREF
  WCHAR DestStr[264]; // [rsp+80h] [rbp-80h] BYREF

  v5 = a3;
  v29 = a3;
  if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(
      (_DWORD)this,
      (unsigned int)Shell32_StartMenuQueryFactory_Programs_Run_Start,
      (_DWORD)a3,
      (_DWORD)a4,
      (__int64)lpSrcStr);
  *a4 = 0;
  v8 = (char *)this + 168;
  if ( !ATL::CComPtrBase<IResultSetManager>::operator!((_QWORD *)this + 21) )
    goto LABEL_25;
  if ( *((_DWORD *)this + 37) )
    goto LABEL_25;
  v11 = (_WORD *)*((_QWORD *)this + 12);
  if ( !v11 || !*v11 || (unsigned int)SHWindowsPolicy(POLID_NoRun) )
    goto LABEL_25;
  *((_DWORD *)this + 37) = 1;
  ProgramsRunResultInternal = CStartMenuProgramsResultSetManager::_GetProgramsRunResultInternal(
                                v12,
                                *((const unsigned __int16 **)this + 12),
                                v9,
                                (void **)this + 21);
  if ( ProgramsRunResultInternal >= 0 )
  {
LABEL_24:
    *((_DWORD *)this + 39) = a2;
LABEL_25:
    v25 = *(__int64 (__fastcall ****)(_QWORD, const struct _GUID *, void **))v8;
    if ( *(_QWORD *)v8 && a2 == *((_DWORD *)this + 39) )
      FirstTwoWordPrefixValuesFromDisjunctiveCondition = (**v25)(v25, v5, a4);
    else
      FirstTwoWordPrefixValuesFromDisjunctiveCondition = -2147467259;
    goto LABEL_29;
  }
  v14 = LCMapStringEx(*((LPCWSTR *)this + 15), 0x400000u, *((LPCWSTR *)this + 12), -1, DestStr, 260, 0, 0, 0);
  if ( (v14 || (int)ResultFromKnownLastError() >= 0)
    && CompareStringOrdinal(*((LPCWCH *)this + 12), -1, DestStr, v14 - 1, 0) != 2 )
  {
    v17 = CStartMenuProgramsResultSetManager::_GetProgramsRunResultInternal(v15, DestStr, v16, (void **)this + 21);
    if ( v17 >= 0 )
    {
LABEL_23:
      v5 = v29;
      goto LABEL_24;
    }
  }
  lpSrcStr[0] = 0;
  v27 = 0;
  FirstTwoWordPrefixValuesFromDisjunctiveCondition = GetFirstTwoWordPrefixValuesFromDisjunctiveCondition(
                                                       *((_QWORD *)this + 8),
                                                       lpSrcStr,
                                                       &v27);
  if ( FirstTwoWordPrefixValuesFromDisjunctiveCondition >= 0 )
  {
    v21 = lpSrcStr[0];
    FirstTwoWordPrefixValuesFromDisjunctiveCondition = CStartMenuProgramsResultSetManager::_GetProgramsRunResultInternal(
                                                         v18,
                                                         lpSrcStr[0],
                                                         v20,
                                                         (void **)this + 21);
    if ( FirstTwoWordPrefixValuesFromDisjunctiveCondition < 0 )
    {
      v22 = LCMapStringEx(*((LPCWSTR *)this + 15), 0x400000u, v21, -1, DestStr, 260, 0, 0, 0);
      if ( v22
        || (FirstTwoWordPrefixValuesFromDisjunctiveCondition = ResultFromKnownLastError(),
            FirstTwoWordPrefixValuesFromDisjunctiveCondition >= 0) )
      {
        if ( CompareStringOrdinal(v21, -1, DestStr, v22 - 1, 0) == 2 )
        {
          FirstTwoWordPrefixValuesFromDisjunctiveCondition = -2147467259;
        }
        else
        {
          FirstTwoWordPrefixValuesFromDisjunctiveCondition = CStartMenuProgramsResultSetManager::_GetProgramsRunResultInternal(
                                                               v23,
                                                               DestStr,
                                                               v24,
                                                               (void **)this + 21);
          if ( FirstTwoWordPrefixValuesFromDisjunctiveCondition >= 0 )
            goto LABEL_22;
        }
      }
      if ( v27 )
        FirstTwoWordPrefixValuesFromDisjunctiveCondition = CStartMenuProgramsResultSetManager::_GetProgramsRunResultInternal(
                                                             v23,
                                                             v27,
                                                             v24,
                                                             (void **)this + 21);
    }
  }
LABEL_22:
  CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>((void **)&v27);
  CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>((void **)lpSrcStr);
  if ( FirstTwoWordPrefixValuesFromDisjunctiveCondition >= 0 )
    goto LABEL_23;
LABEL_29:
  if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(
      (_DWORD)v25,
      (unsigned int)Shell32_StartMenuQueryFactory_Programs_Run_Stop,
      (_DWORD)v9,
      v10,
      (__int64)&v29);
  return (unsigned int)FirstTwoWordPrefixValuesFromDisjunctiveCondition;
}

```

## disassembly

```asm
0x1800354e8  mov     [rsp-8+arg_8], rbx
0x1800354ed  push    rbp
0x1800354ee  push    rsi
0x1800354ef  push    rdi
0x1800354f0  push    r12
0x1800354f2  push    r13
0x1800354f4  push    r14
0x1800354f6  push    r15
0x1800354f8  lea     rbp, [rsp-1A0h]
0x180035500  sub     rsp, 2A0h
0x180035507  mov     rax, cs:__security_cookie
0x18003550e  xor     rax, rsp
0x180035511  mov     [rbp+1D0h+var_40], rax
0x180035518  mov     r13, r9
0x18003551b  mov     rbx, r8
0x18003551e  mov     [rsp+2D0h+var_268], rbx
0x180035523  mov     r12d, edx
0x180035526  mov     rsi, rcx
0x180035529  test    cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x180035530  jz      short loc_180035548
0x180035532  lea     rax, [rsp+2D0h+lpSrcStr]
0x180035537  mov     [rsp+2D0h+lpDestStr], rax
0x18003553c  lea     rdx, Shell32_StartMenuQueryFactory_Programs_Run_Start
0x180035543  call    McGenEventWrite_EtwEventWriteTransfer
0x180035548  xor     r15d, r15d
0x18003554b  mov     [r13+0], r15
0x18003554f  lea     r14, [rsi+0A8h]
0x180035556  mov     rcx, r14
0x180035559  call    ??7?$CComPtrBase@UIResultSetManager@@@ATL@@QEBA_NXZ; ATL::CComPtrBase<IResultSetManager>::operator!(void)
0x18003555e  test    al, al
0x180035560  jz      loc_18003573B
0x180035566  cmp     [rsi+94h], r15d
0x18003556d  jnz     loc_18003573B
0x180035573  mov     rax, [rsi+60h]
0x180035577  test    rax, rax
0x18003557a  jz      loc_18003573B
0x180035580  cmp     [rax], r15w
0x180035584  jz      loc_18003573B
0x18003558a  lea     rcx, POLID_NoRun
0x180035591  call    cs:__imp_SHWindowsPolicy
0x180035597  test    eax, eax
0x180035599  jnz     loc_18003573B
0x18003559f  mov     dword ptr [rsi+94h], 1
0x1800355a9  mov     r9, r14; void **
0x1800355ac  mov     rdx, [rsi+60h]; unsigned __int16 *
0x1800355b0  call    ?_GetProgramsRunResultInternal@CStartMenuProgramsResultSetManager@@AEAAJPEBGAEBU_GUID@@PEAPEAX@Z; CStartMenuProgramsResultSetManager::_GetProgramsRunResultInternal(ushort const *,_GUID const &,void * *)
0x1800355b5  mov     edi, eax
0x1800355b7  test    eax, eax
0x1800355b9  jns     loc_180035730
0x1800355bf  mov     [rsp+2D0h+sortHandle], r15; sortHandle
0x1800355c4  mov     [rsp+2D0h+lpReserved], r15; lpReserved
0x1800355c9  mov     [rsp+2D0h+lpVersionInformation], r15; lpVersionInformation
0x1800355ce  mov     [rsp+2D0h+cchDest], 104h; cchDest
0x1800355d6  lea     rax, [rbp+1D0h+DestStr]
0x1800355da  mov     [rsp+2D0h+lpDestStr], rax; lpDestStr
0x1800355df  or      edi, 0FFFFFFFFh
0x1800355e2  mov     r9d, edi; cchSrc
0x1800355e5  mov     r8, [rsi+60h]; lpSrcStr
0x1800355e9  mov     edx, 400000h; dwMapFlags
0x1800355ee  mov     rcx, [rsi+78h]; lpLocaleName
0x1800355f2  call    cs:__imp_LCMapStringEx
0x1800355f8  mov     ebx, eax
0x1800355fa  test    eax, eax
0x1800355fc  jnz     short loc_180035607
0x1800355fe  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180035603  test    eax, eax
0x180035605  js      short loc_18003563B
0x180035607  lea     r9d, [rbx-1]; cchCount2
0x18003560b  mov     dword ptr [rsp+2D0h+lpDestStr], r15d; bIgnoreCase
0x180035610  lea     r8, [rbp+1D0h+DestStr]; lpString2
0x180035614  mov     edx, edi; cchCount1
0x180035616  mov     rcx, [rsi+60h]; lpString1
0x18003561a  call    cs:__imp_CompareStringOrdinal
0x180035620  cmp     eax, 2
0x180035623  jz      short loc_18003563B
0x180035625  mov     r9, r14; void **
0x180035628  lea     rdx, [rbp+1D0h+DestStr]; unsigned __int16 *
0x18003562c  call    ?_GetProgramsRunResultInternal@CStartMenuProgramsResultSetManager@@AEAAJPEBGAEBU_GUID@@PEAPEAX@Z; CStartMenuProgramsResultSetManager::_GetProgramsRunResultInternal(ushort const *,_GUID const &,void * *)
0x180035631  mov     edi, eax
0x180035633  test    eax, eax
0x180035635  jns     loc_18003572B
0x18003563b  mov     [rsp+2D0h+lpSrcStr], r15
0x180035640  mov     [rsp+2D0h+var_280], r15
0x180035645  lea     r8, [rsp+2D0h+var_280]
0x18003564a  lea     rdx, [rsp+2D0h+lpSrcStr]
0x18003564f  mov     rcx, [rsi+40h]
0x180035653  call    GetFirstTwoWordPrefixValuesFromDisjunctiveCondition
0x180035658  mov     edi, eax
0x18003565a  test    eax, eax
0x18003565c  js      loc_180035712
0x180035662  mov     r9, r14; void **
0x180035665  mov     rbx, [rsp+2D0h+lpSrcStr]
0x18003566a  mov     rdx, rbx; unsigned __int16 *
0x18003566d  call    ?_GetProgramsRunResultInternal@CStartMenuProgramsResultSetManager@@AEAAJPEBGAEBU_GUID@@PEAPEAX@Z; CStartMenuProgramsResultSetManager::_GetProgramsRunResultInternal(ushort const *,_GUID const &,void * *)
0x180035672  mov     edi, eax
0x180035674  test    eax, eax
0x180035676  jns     loc_180035712
0x18003567c  mov     [rsp+2D0h+sortHandle], r15; sortHandle
0x180035681  mov     [rsp+2D0h+lpReserved], r15; lpReserved
0x180035686  mov     [rsp+2D0h+lpVersionInformation], r15; lpVersionInformation
0x18003568b  mov     [rsp+2D0h+cchDest], 104h; cchDest
0x180035693  lea     rax, [rbp+1D0h+DestStr]
0x180035697  mov     [rsp+2D0h+lpDestStr], rax; lpDestStr
0x18003569c  or      r9d, 0FFFFFFFFh; cchSrc
0x1800356a0  mov     r8, rbx; lpSrcStr
0x1800356a3  mov     edx, 400000h; dwMapFlags
0x1800356a8  mov     rcx, [rsi+78h]; lpLocaleName
0x1800356ac  call    cs:__imp_LCMapStringEx
0x1800356b2  mov     r15d, eax
0x1800356b5  test    eax, eax
0x1800356b7  jnz     short loc_1800356C4
0x1800356b9  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800356be  mov     edi, eax
0x1800356c0  test    eax, eax
0x1800356c2  js      short loc_1800356FE
0x1800356c4  lea     r9d, [r15-1]; cchCount2
0x1800356c8  xor     r15d, r15d
0x1800356cb  mov     dword ptr [rsp+2D0h+lpDestStr], r15d; bIgnoreCase
0x1800356d0  lea     r8, [rbp+1D0h+DestStr]; lpString2
0x1800356d4  or      edx, 0FFFFFFFFh; cchCount1
0x1800356d7  mov     rcx, rbx; lpString1
0x1800356da  call    cs:__imp_CompareStringOrdinal
0x1800356e0  cmp     eax, 2
0x1800356e3  jnz     short loc_1800356EC
0x1800356e5  mov     edi, 80004005h
0x1800356ea  jmp     short loc_1800356FE
0x1800356ec  mov     r9, r14; void **
0x1800356ef  lea     rdx, [rbp+1D0h+DestStr]; unsigned __int16 *
0x1800356f3  call    ?_GetProgramsRunResultInternal@CStartMenuProgramsResultSetManager@@AEAAJPEBGAEBU_GUID@@PEAPEAX@Z; CStartMenuProgramsResultSetManager::_GetProgramsRunResultInternal(ushort const *,_GUID const &,void * *)
0x1800356f8  mov     edi, eax
0x1800356fa  test    eax, eax
0x1800356fc  jns     short loc_180035712
0x1800356fe  mov     rdx, [rsp+2D0h+var_280]; unsigned __int16 *
0x180035703  test    rdx, rdx
0x180035706  jz      short loc_180035712
0x180035708  mov     r9, r14; void **
0x18003570b  call    ?_GetProgramsRunResultInternal@CStartMenuProgramsResultSetManager@@AEAAJPEBGAEBU_GUID@@PEAPEAX@Z; CStartMenuProgramsResultSetManager::_GetProgramsRunResultInternal(ushort const *,_GUID const &,void * *)
0x180035710  mov     edi, eax
0x180035712  lea     rcx, [rsp+2D0h+var_280]; void *
0x180035717  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x18003571c  nop
0x18003571d  lea     rcx, [rsp+2D0h+lpSrcStr]; void *
0x180035722  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x180035727  test    edi, edi
0x180035729  js      short loc_180035766
0x18003572b  mov     rbx, [rsp+2D0h+var_268]
0x180035730  mov     [rsi+9Ch], r12d
0x180035737  test    edi, edi
0x180035739  js      short loc_180035766
0x18003573b  mov     rcx, [r14]
0x18003573e  test    rcx, rcx
0x180035741  jz      short loc_180035761
0x180035743  cmp     r12d, [rsi+9Ch]
0x18003574a  jnz     short loc_180035761
0x18003574c  mov     rax, [rcx]
0x18003574f  mov     r8, r13
0x180035752  mov     rdx, rbx
0x180035755  mov     rax, [rax]
0x180035758  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003575d  mov     edi, eax
0x18003575f  jmp     short loc_180035766
0x180035761  mov     edi, 80004005h
0x180035766  test    cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x18003576d  jz      short loc_180035785
0x18003576f  lea     rax, [rsp+2D0h+var_268]
0x180035774  mov     [rsp+2D0h+lpDestStr], rax
0x180035779  lea     rdx, Shell32_StartMenuQueryFactory_Programs_Run_Stop
0x180035780  call    McGenEventWrite_EtwEventWriteTransfer
0x180035785  mov     eax, edi
0x180035787  mov     rcx, [rbp+1D0h+var_40]
0x18003578e  xor     rcx, rsp; StackCookie
0x180035791  call    __security_check_cookie
0x180035796  mov     rbx, [rsp+2D0h+arg_8]
0x18003579e  add     rsp, 2A0h
0x1800357a5  pop     r15
0x1800357a7  pop     r14
0x1800357a9  pop     r13
0x1800357ab  pop     r12
0x1800357ad  pop     rdi
0x1800357ae  pop     rsi
0x1800357af  pop     rbp
0x1800357b0  retn
```
