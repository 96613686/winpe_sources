# Windows::Rtl::SystemImplementation::CFile::GetCatalogHint(Windows::Auto<_LUNICODE_STRING> *,Windows::Rtl::IRtlFile::GetCatalogHintDisposition *)

- ea: `0x180160230`
- end: `0x1801606f8`
- name: `?GetCatalogHint@CFile@SystemImplementation@Rtl@Windows@@UEAAJPEAV?$Auto@U_LUNICODE_STRING@@@4@PEAW4GetCatalogHintDisposition@IRtlFile@34@@Z`
- size: `1224`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1800031d0`
- `0x18000693e`
- `0x18000aedc`
- `0x18001625c`
- `0x180049274`
- `0x1800497c0`
- `0x18004d970`
- `0x18012e788`
- `0x18012e824`
- `0x180160230`
- `0x1801bd010`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180160436`
- `ntdll!RtlFreeHeap` at `0x18016047e`
- `ntdll!RtlFreeHeap` at `0x18016052a`
- `ntdll!RtlFreeHeap` at `0x180160594`
- `ntdll!RtlFreeHeap` at `0x18016061e`
- `ntdll!RtlFreeHeap` at `0x1801606a9`
- `ntdll!RtlFreeHeap` at `0x180160436`
- `ntdll!RtlFreeHeap` at `0x18016047e`
- `ntdll!RtlFreeHeap` at `0x18016052a`
- `ntdll!RtlFreeHeap` at `0x180160594`
- `ntdll!RtlFreeHeap` at `0x18016061e`
- `ntdll!RtlFreeHeap` at `0x1801606a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180160506`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180160570`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801605fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180160685`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180160506`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180160570`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801605fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180160685`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Windows::Rtl::SystemImplementation::CFile::GetCatalogHint(__int64 a1, _QWORD *a2, _DWORD *a3)
{
  int CatalogHintFromEA; // ebx
  __int64 v7; // rcx
  PVOID v8; // rbx
  int CatalogNameFromHint; // edi
  _WORD *v10; // rdi
  __int64 v11; // rcx
  int v12; // r14d
  __int64 v13; // r14
  const void *v14; // r13
  size_t v15; // r14
  int v16; // r12d
  int v17; // [rsp+48h] [rbp-49h] BYREF
  PVOID P; // [rsp+50h] [rbp-41h] BYREF
  const char *v19; // [rsp+58h] [rbp-39h] BYREF
  const char *v20; // [rsp+60h] [rbp-31h]
  __int64 v21; // [rsp+68h] [rbp-29h]
  const char *v22; // [rsp+70h] [rbp-21h]
  __int64 v23; // [rsp+78h] [rbp-19h]
  __int128 v24; // [rsp+80h] [rbp-11h] BYREF
  __int64 v25; // [rsp+90h] [rbp-1h]
  int v26; // [rsp+98h] [rbp+7h] BYREF
  char v27; // [rsp+9Ch] [rbp+Bh]
  _QWORD v28[2]; // [rsp+9Dh] [rbp+Ch] BYREF
  char v29; // [rsp+ADh] [rbp+1Ch]
  __int16 v30; // [rsp+AEh] [rbp+1Dh]

  v23 = -2;
  if ( a3 )
    *a3 = 0;
  if ( !a2 )
  {
    v19 = "onecore\\base\\wcp\\sil\\file.cpp";
    v20 = "Windows::Rtl::SystemImplementation::CFile::GetCatalogHint";
    v21 = 97;
    v22 = "Not-null check failed: HintName";
    RtlReportErrorOrigination(&v19, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225485LL);
    return 3221225485LL;
  }
  v26 = 0;
  v29 = 0;
  v30 = 0;
  v27 = 15;
  strcpy((char *)v28, "$CI.CatalogHint");
  v24 = 0;
  v25 = 0;
  CatalogHintFromEA = (*(__int64 (__fastcall **)(__int64, __int128 *, _QWORD, int *, int, _QWORD, _BYTE))(*(_QWORD *)a1 + 208LL))(
                        a1,
                        &v24,
                        0,
                        &v26,
                        24,
                        0,
                        0);
  v7 = v25;
  if ( CatalogHintFromEA < 0 )
    goto LABEL_6;
  if ( v25 )
  {
    if ( *(_BYTE *)(v25 + 5) == 15 )
    {
      P = 0;
      CatalogHintFromEA = CiGetCatalogHintFromEA(v25, (unsigned int)v24, &P);
      if ( CatalogHintFromEA < 0 )
      {
        if ( P )
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
        v7 = v25;
LABEL_6:
        if ( v7 )
          anonymous_namespace_::OurRtlFreeStringRoutine(v7);
        return (unsigned int)CatalogHintFromEA;
      }
      v17 = 0;
      v8 = P;
      CatalogNameFromHint = CiGetCatalogNameFromHint(P, 0, &v17);
      if ( CatalogNameFromHint >= 0 )
      {
        P = 0;
        if ( Windows::AutoNullTerminatedString<Windows::COM::CLPWSTRTraits,Windows::Auto<wchar_t *>>::ResizeBufferNoPreserve(
               &P,
               (unsigned __int64)(unsigned int)(v17 + 1) >> 1) )
        {
          v10 = P;
          v12 = CiGetCatalogNameFromHint(v8, P, &v17);
          if ( v12 >= 0 )
          {
            *a2 = 0;
            if ( v10 )
            {
              v13 = -1;
              do
                ++v13;
              while ( v10[v13] );
              v14 = v10;
              v15 = 2 * v13;
            }
            else
            {
              v15 = 0;
              v14 = 0;
            }
            if ( a2[1] >= v15 || (v16 = RtlReallocateLUnicodeString(v11, v15, a2), v16 >= 0) )
            {
              if ( v15 )
              {
                if ( v15 > a2[1] - *a2 )
                {
                  INTERNAL_ERROR_ACTION(-1073741595);
                  JUMPOUT(0x1801606F7LL);
                }
                memcpy_0((void *)(a2[2] + 2LL * (*a2 >> 1)), v14, v15);
                *a2 += v15;
              }
              if ( a3 )
                *a3 = 1;
              if ( v10 )
                CoTaskMemFree(v10);
              if ( v8 )
                RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v8);
              if ( v25 )
                anonymous_namespace_::OurRtlFreeStringRoutine(v25);
              return 0;
            }
            if ( v10 )
              CoTaskMemFree(v10);
            if ( v8 )
              RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v8);
            if ( v25 )
              anonymous_namespace_::OurRtlFreeStringRoutine(v25);
            return (unsigned int)v16;
          }
          else
          {
            if ( v10 )
              CoTaskMemFree(v10);
            if ( v8 )
              RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v8);
            if ( v25 )
              anonymous_namespace_::OurRtlFreeStringRoutine(v25);
            return (unsigned int)v12;
          }
        }
        else
        {
          v19 = "onecore\\base\\wcp\\sil\\file.cpp";
          v20 = "Windows::Rtl::SystemImplementation::CFile::GetCatalogHint";
          v21 = 142;
          v22 = "LocalHintName.ResizeBufferNoPreserve((CatalogNameSize + 1) / sizeof(WCHAR))";
          RtlReportErrorOrigination(&v19, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225495LL);
          if ( P )
            CoTaskMemFree(P);
          if ( v8 )
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v8);
          if ( v25 )
            anonymous_namespace_::OurRtlFreeStringRoutine(v25);
          return 3221225495LL;
        }
      }
      else
      {
        if ( v8 )
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v8);
        if ( v25 )
          anonymous_namespace_::OurRtlFreeStringRoutine(v25);
        return (unsigned int)CatalogNameFromHint;
      }
    }
    else
    {
      v19 = "onecore\\base\\wcp\\sil\\file.cpp";
      v20 = "Windows::Rtl::SystemImplementation::CFile::GetCatalogHint";
      v21 = 132;
      v22 = 0;
      RtlReportErrorOrigination(&v19, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 2147483667LL);
      if ( v25 )
        anonymous_namespace_::OurRtlFreeStringRoutine(v25);
      return 2147483667LL;
    }
  }
  else
  {
    if ( a3 )
    {
      *a3 = 2;
      return 0;
    }
    v19 = "onecore\\base\\wcp\\sil\\file.cpp";
    v20 = "Windows::Rtl::SystemImplementation::CFile::GetCatalogHint";
    v21 = 126;
    v22 = 0;
    RtlReportErrorOrigination(&v19, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225554LL);
    if ( v25 )
      anonymous_namespace_::OurRtlFreeStringRoutine(v25);
    return 3221225554LL;
  }
}

```

## disassembly

```asm
0x180160230  mov     rax, rsp
0x180160233  push    rbp
0x180160234  push    rsi
0x180160235  push    rdi
0x180160236  push    r12
0x180160238  push    r13
0x18016023a  push    r14
0x18016023c  push    r15
0x18016023e  lea     rbp, [rax-5Fh]
0x180160242  sub     rsp, 0B0h
0x180160249  mov     [rbp+57h+var_70], 0FFFFFFFFFFFFFFFEh
0x180160251  mov     [rax+20h], rbx
0x180160255  mov     rax, cs:__security_cookie
0x18016025c  xor     rax, rsp
0x18016025f  mov     [rbp+57h+var_38], rax
0x180160263  mov     r15, r8
0x180160266  mov     rsi, rdx
0x180160269  xor     r12d, r12d
0x18016026c  test    r8, r8
0x18016026f  jz      short loc_180160274
0x180160271  mov     [r8], r12d
0x180160274  test    rsi, rsi
0x180160277  jnz     short loc_1801602C2
0x180160279  lea     rax, aOnecoreBaseWcp_49; "onecore\\base\\wcp\\sil\\file.cpp"
0x180160280  mov     [rbp+57h+var_90], rax
0x180160284  lea     rax, aWindowsRtlSyst_19; "Windows::Rtl::SystemImplementation::CFi"...
0x18016028b  mov     [rbp+57h+var_88], rax
0x18016028f  mov     [rbp+57h+var_80], 61h ; 'a'
0x180160297  lea     rax, aNotNullCheckFa_0; "Not-null check failed: HintName"
0x18016029e  mov     [rbp+57h+var_78], rax
0x1801602a2  mov     r8d, 0C000000Dh
0x1801602a8  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x1801602af  lea     rcx, [rbp+57h+var_90]
0x1801602b3  call    RtlReportErrorOrigination
0x1801602b8  mov     eax, 0C000000Dh
0x1801602bd  jmp     loc_1801606C5
0x1801602c2  mov     [rbp+57h+var_50], r12d
0x1801602c6  mov     [rbp+57h+var_3C], r12d
0x1801602ca  mov     [rbp+57h+var_4C], 0Fh
0x1801602ce  movsd   xmm0, qword ptr cs:aCiCataloghint; "$CI.CatalogHint"
0x1801602d6  movsd   [rbp+57h+var_4B], xmm0
0x1801602db  mov     eax, dword ptr cs:aCiCataloghint+8; "logHint"
0x1801602e1  mov     [rbp+14h], eax
0x1801602e4  movzx   eax, word ptr cs:aCiCataloghint+0Ch; "int"
0x1801602eb  mov     [rbp+18h], ax
0x1801602ef  mov     al, byte ptr cs:aCiCataloghint+0Eh; "t"
0x1801602f5  mov     [rbp+1Ah], al
0x1801602f8  xorps   xmm0, xmm0
0x1801602fb  xor     eax, eax
0x1801602fd  movups  [rbp+57h+var_68], xmm0
0x180160301  mov     [rbp+57h+var_58], rax
0x180160305  mov     rax, [rcx]
0x180160308  mov     [rsp+30h], r12b
0x18016030d  mov     qword ptr [rsp+0E0h+var_B8], r12
0x180160312  mov     dword ptr [rsp+0E0h+var_C0], 18h
0x18016031a  lea     r9, [rbp+57h+var_50]
0x18016031e  xor     r8d, r8d
0x180160321  lea     rdx, [rbp+57h+var_68]
0x180160325  mov     rax, [rax+0D0h]
0x18016032c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180160331  mov     ebx, eax
0x180160333  mov     rcx, [rbp+57h+var_58]
0x180160337  test    eax, eax
0x180160339  jns     short loc_18016034C
0x18016033b  test    rcx, rcx
0x18016033e  jz      short loc_180160345
0x180160340  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x180160345  mov     eax, ebx
0x180160347  jmp     loc_1801606C5
0x18016034c  test    rcx, rcx
0x18016034f  jnz     short loc_1801603B2
0x180160351  test    r15, r15
0x180160354  jz      short loc_180160362
0x180160356  mov     dword ptr [r15], 2
0x18016035d  jmp     loc_1801606C3
0x180160362  lea     rax, aOnecoreBaseWcp_49; "onecore\\base\\wcp\\sil\\file.cpp"
0x180160369  mov     [rbp+57h+var_90], rax
0x18016036d  lea     rax, aWindowsRtlSyst_19; "Windows::Rtl::SystemImplementation::CFi"...
0x180160374  mov     [rbp+57h+var_88], rax
0x180160378  mov     [rbp+57h+var_80], 7Eh ; '~'
0x180160380  mov     [rbp+57h+var_78], r12
0x180160384  mov     r8d, 0C0000052h
0x18016038a  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x180160391  lea     rcx, [rbp+57h+var_90]
0x180160395  call    RtlReportErrorOrigination
0x18016039a  mov     rcx, [rbp+57h+var_58]
0x18016039e  test    rcx, rcx
0x1801603a1  jz      short loc_1801603A8
0x1801603a3  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x1801603a8  mov     eax, 0C0000052h
0x1801603ad  jmp     loc_1801606C5
0x1801603b2  cmp     byte ptr [rcx+5], 0Fh
0x1801603b6  jz      short loc_180160408
0x1801603b8  lea     rax, aOnecoreBaseWcp_49; "onecore\\base\\wcp\\sil\\file.cpp"
0x1801603bf  mov     [rbp+57h+var_90], rax
0x1801603c3  lea     rax, aWindowsRtlSyst_19; "Windows::Rtl::SystemImplementation::CFi"...
0x1801603ca  mov     [rbp+57h+var_88], rax
0x1801603ce  mov     [rbp+57h+var_80], 84h
0x1801603d6  mov     [rbp+57h+var_78], r12
0x1801603da  mov     r8d, 80000013h
0x1801603e0  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x1801603e7  lea     rcx, [rbp+57h+var_90]
0x1801603eb  call    RtlReportErrorOrigination
0x1801603f0  mov     rcx, [rbp+57h+var_58]
0x1801603f4  test    rcx, rcx
0x1801603f7  jz      short loc_1801603FE
0x1801603f9  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x1801603fe  mov     eax, 80000013h
0x180160403  jmp     loc_1801606C5
0x180160408  mov     [rbp+57h+P], r12
0x18016040c  lea     r8, [rbp+57h+P]
0x180160410  mov     edx, dword ptr [rbp+57h+var_68]
0x180160413  call    CiGetCatalogHintFromEA
0x180160418  mov     ebx, eax
0x18016041a  test    eax, eax
0x18016041c  jns     short loc_18016044B
0x18016041e  mov     r8, [rbp+57h+P]; P
0x180160422  test    r8, r8
0x180160425  jz      short loc_180160442
0x180160427  mov     rcx, gs:60h
0x180160430  xor     edx, edx; Flags
0x180160432  mov     rcx, [rcx+30h]; HeapHandle
0x180160436  call    cs:__imp_RtlFreeHeap
0x18016043d  nop     dword ptr [rax+rax+00h]
0x180160442  mov     rcx, [rbp+57h+var_58]
0x180160446  jmp     loc_18016033B
0x18016044b  mov     [rbp+57h+var_A0], r12d
0x18016044f  lea     r8, [rbp+57h+var_A0]
0x180160453  xor     edx, edx
0x180160455  mov     rbx, [rbp+57h+P]
0x180160459  mov     rcx, rbx
0x18016045c  call    CiGetCatalogNameFromHint
0x180160461  mov     edi, eax
0x180160463  test    eax, eax
0x180160465  jns     short loc_18016049F
0x180160467  test    rbx, rbx
0x18016046a  jz      short loc_18016048A
0x18016046c  mov     rcx, gs:60h
0x180160475  mov     r8, rbx; P
0x180160478  xor     edx, edx; Flags
0x18016047a  mov     rcx, [rcx+30h]; HeapHandle
0x18016047e  call    cs:__imp_RtlFreeHeap
0x180160485  nop     dword ptr [rax+rax+00h]
0x18016048a  mov     rcx, [rbp+57h+var_58]
0x18016048e  test    rcx, rcx
0x180160491  jz      short loc_180160498
0x180160493  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x180160498  mov     eax, edi
0x18016049a  jmp     loc_1801606C5
0x18016049f  mov     [rbp+57h+P], r12
0x1801604a3  mov     edx, [rbp+57h+var_A0]
0x1801604a6  inc     edx
0x1801604a8  shr     rdx, 1
0x1801604ab  lea     rcx, [rbp+57h+P]
0x1801604af  call    ?ResizeBufferNoPreserve@?$AutoNullTerminatedString@VCLPWSTRTraits@COM@Windows@@V?$Auto@PEA_W@3@@Windows@@QEAAPEA_W_K@Z; Windows::AutoNullTerminatedString<Windows::COM::CLPWSTRTraits,Windows::Auto<wchar_t *>>::ResizeBufferNoPreserve(unsigned __int64)
0x1801604b4  test    rax, rax
0x1801604b7  jnz     loc_18016054E
0x1801604bd  lea     rax, aOnecoreBaseWcp_49; "onecore\\base\\wcp\\sil\\file.cpp"
0x1801604c4  mov     [rbp+57h+var_90], rax
0x1801604c8  lea     rax, aWindowsRtlSyst_19; "Windows::Rtl::SystemImplementation::CFi"...
0x1801604cf  mov     [rbp+57h+var_88], rax
0x1801604d3  mov     [rbp+57h+var_80], 8Eh
0x1801604db  lea     rax, aLocalhintnameR; "LocalHintName.ResizeBufferNoPreserve((C"...
0x1801604e2  mov     [rbp+57h+var_78], rax
0x1801604e6  mov     r8d, 0C0000017h
0x1801604ec  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x1801604f3  lea     rcx, [rbp+57h+var_90]
0x1801604f7  call    RtlReportErrorOrigination
0x1801604fc  nop
0x1801604fd  mov     rcx, [rbp+57h+P]; pv
0x180160501  test    rcx, rcx
0x180160504  jz      short loc_180160513
0x180160506  call    cs:__imp_CoTaskMemFree
0x18016050d  nop     dword ptr [rax+rax+00h]
0x180160512  nop
0x180160513  test    rbx, rbx
0x180160516  jz      short loc_180160536
0x180160518  mov     rcx, gs:60h
0x180160521  mov     r8, rbx; P
0x180160524  xor     edx, edx; Flags
0x180160526  mov     rcx, [rcx+30h]; HeapHandle
0x18016052a  call    cs:__imp_RtlFreeHeap
0x180160531  nop     dword ptr [rax+rax+00h]
0x180160536  mov     rcx, [rbp+57h+var_58]
0x18016053a  test    rcx, rcx
0x18016053d  jz      short loc_180160544
0x18016053f  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x180160544  mov     eax, 0C0000017h
0x180160549  jmp     loc_1801606C5
0x18016054e  lea     r8, [rbp+57h+var_A0]
0x180160552  mov     rdi, [rbp+57h+P]
0x180160556  mov     rdx, rdi
0x180160559  mov     rcx, rbx
0x18016055c  call    CiGetCatalogNameFromHint
0x180160561  mov     r14d, eax
0x180160564  test    eax, eax
0x180160566  jns     short loc_1801605B6
0x180160568  test    rdi, rdi
0x18016056b  jz      short loc_18016057D
0x18016056d  mov     rcx, rdi; pv
0x180160570  call    cs:__imp_CoTaskMemFree
0x180160577  nop     dword ptr [rax+rax+00h]
0x18016057c  nop
0x18016057d  test    rbx, rbx
0x180160580  jz      short loc_1801605A0
0x180160582  mov     rcx, gs:60h
0x18016058b  mov     r8, rbx; P
0x18016058e  xor     edx, edx; Flags
0x180160590  mov     rcx, [rcx+30h]; HeapHandle
0x180160594  call    cs:__imp_RtlFreeHeap
0x18016059b  nop     dword ptr [rax+rax+00h]
0x1801605a0  mov     rcx, [rbp+57h+var_58]
0x1801605a4  test    rcx, rcx
0x1801605a7  jz      short loc_1801605AE
0x1801605a9  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x1801605ae  mov     eax, r14d
0x1801605b1  jmp     loc_1801606C5
0x1801605b6  mov     [rsi], r12
0x1801605b9  test    rdi, rdi
0x1801605bc  jz      short loc_1801605D4
0x1801605be  or      r14, 0FFFFFFFFFFFFFFFFh
0x1801605c2  inc     r14
0x1801605c5  cmp     [rdi+r14*2], r12w
0x1801605ca  jnz     short loc_1801605C2
0x1801605cc  mov     r13, rdi
0x1801605cf  add     r14, r14
0x1801605d2  jmp     short loc_1801605DA
0x1801605d4  mov     r14, r12
0x1801605d7  mov     r13, r12
0x1801605da  cmp     [rsi+8], r14
0x1801605de  jnb     short loc_180160640
0x1801605e0  mov     r8, rsi
0x1801605e3  mov     rdx, r14
0x1801605e6  call    RtlReallocateLUnicodeString
0x1801605eb  mov     r12d, eax
0x1801605ee  test    eax, eax
0x1801605f0  jns     short loc_180160640
0x1801605f2  test    rdi, rdi
0x1801605f5  jz      short loc_180160607
0x1801605f7  mov     rcx, rdi; pv
0x1801605fa  call    cs:__imp_CoTaskMemFree
0x180160601  nop     dword ptr [rax+rax+00h]
0x180160606  nop
0x180160607  test    rbx, rbx
0x18016060a  jz      short loc_18016062A
0x18016060c  mov     rcx, gs:60h
0x180160615  mov     r8, rbx; P
0x180160618  xor     edx, edx; Flags
0x18016061a  mov     rcx, [rcx+30h]; HeapHandle
0x18016061e  call    cs:__imp_RtlFreeHeap
0x180160625  nop     dword ptr [rax+rax+00h]
0x18016062a  mov     rcx, [rbp+57h+var_58]
0x18016062e  test    rcx, rcx
0x180160631  jz      short loc_180160638
0x180160633  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x180160638  mov     eax, r12d
0x18016063b  jmp     loc_1801606C5
0x180160640  test    r14, r14
0x180160643  jz      short loc_180160671
0x180160645  mov     rcx, [rsi]
0x180160648  mov     rax, [rsi+8]
0x18016064c  sub     rax, rcx
0x18016064f  cmp     r14, rax
0x180160652  ja      loc_1801606ED
0x180160658  shr     rcx, 1
0x18016065b  mov     rax, [rsi+10h]
0x18016065f  lea     rcx, [rax+rcx*2]; void *
0x180160663  mov     r8, r14; Size
0x180160666  mov     rdx, r13; Src
0x180160669  call    memcpy_0
0x18016066e  add     [rsi], r14
0x180160671  test    r15, r15
0x180160674  jz      short loc_18016067D
0x180160676  mov     dword ptr [r15], 1
0x18016067d  test    rdi, rdi
0x180160680  jz      short loc_180160692
0x180160682  mov     rcx, rdi; pv
0x180160685  call    cs:__imp_CoTaskMemFree
0x18016068c  nop     dword ptr [rax+rax+00h]
0x180160691  nop
0x180160692  test    rbx, rbx
0x180160695  jz      short loc_1801606B5
0x180160697  mov     rcx, gs:60h
0x1801606a0  mov     r8, rbx; P
0x1801606a3  xor     edx, edx; Flags
0x1801606a5  mov     rcx, [rcx+30h]; HeapHandle
0x1801606a9  call    cs:__imp_RtlFreeHeap
0x1801606b0  nop     dword ptr [rax+rax+00h]
0x1801606b5  mov     rcx, [rbp+57h+var_58]
0x1801606b9  test    rcx, rcx
0x1801606bc  jz      short loc_1801606C3
0x1801606be  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x1801606c3  xor     eax, eax
0x1801606c5  mov     rcx, [rbp+57h+var_38]
0x1801606c9  xor     rcx, rsp; StackCookie
0x1801606cc  call    __security_check_cookie
0x1801606d1  mov     rbx, [rsp+0E0h+arg_18]
0x1801606d9  add     rsp, 0B0h
0x1801606e0  pop     r15
0x1801606e2  pop     r14
  ... truncated ...
```
