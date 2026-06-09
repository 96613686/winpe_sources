# Windows::Rtl::SystemImplementation::CFile::GetCatalogHint(Windows::Auto<_LUNICODE_STRING> *,Windows::Rtl::IRtlFile::GetCatalogHintDisposition *)

- ea: `0x1801c3830`
- end: `0x1801c3ce8`
- name: `?GetCatalogHint@CFile@SystemImplementation@Rtl@Windows@@UEAAJPEAV?$Auto@U_LUNICODE_STRING@@@4@PEAW4GetCatalogHintDisposition@IRtlFile@34@@Z`
- size: `1208`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1800059d0`
- `0x180022940`
- `0x1800692fc`
- `0x180191a64`
- `0x180191b00`
- `0x1801c3830`
- `0x1801ee64c`
- `0x1801efdc0`
- `0x18029eaa4`
- `0x1802b1010`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x1801c3a3a`
- `ntdll!RtlFreeHeap` at `0x1801c3a89`
- `ntdll!RtlFreeHeap` at `0x1801c3b2a`
- `ntdll!RtlFreeHeap` at `0x1801c3b8f`
- `ntdll!RtlFreeHeap` at `0x1801c3c15`
- `ntdll!RtlFreeHeap` at `0x1801c3c9c`
- `ntdll!RtlFreeHeap` at `0x1801c3a3a`
- `ntdll!RtlFreeHeap` at `0x1801c3a89`
- `ntdll!RtlFreeHeap` at `0x1801c3b2a`
- `ntdll!RtlFreeHeap` at `0x1801c3b8f`
- `ntdll!RtlFreeHeap` at `0x1801c3c15`
- `ntdll!RtlFreeHeap` at `0x1801c3c9c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801c3b6c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801c3bf2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801c3c79`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801c3b6c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801c3bf2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801c3c79`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801c3aba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801c3aba`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Rtl::SystemImplementation::CFile::GetCatalogHint(__int64 a1, _QWORD *a2, _DWORD *a3)
{
  int CatalogHintFromEA; // ebx
  PVOID v7; // rbx
  int CatalogNameFromHint; // edi
  unsigned __int64 v9; // rcx
  _WORD *v10; // rax
  _WORD *v11; // rdi
  __int64 v12; // rcx
  int v13; // r14d
  __int64 v14; // r14
  const void *v15; // r13
  size_t v16; // r14
  int v17; // r12d
  int v18; // [rsp+48h] [rbp-49h] BYREF
  const char *v19; // [rsp+50h] [rbp-41h] BYREF
  const char *v20; // [rsp+58h] [rbp-39h]
  __int64 v21; // [rsp+60h] [rbp-31h]
  const char *v22; // [rsp+68h] [rbp-29h]
  PVOID P[2]; // [rsp+70h] [rbp-21h] BYREF
  __int128 v24; // [rsp+80h] [rbp-11h] BYREF
  __int64 v25; // [rsp+90h] [rbp-1h]
  int v26; // [rsp+98h] [rbp+7h] BYREF
  char v27; // [rsp+9Ch] [rbp+Bh]
  _QWORD v28[2]; // [rsp+9Dh] [rbp+Ch] BYREF
  char v29; // [rsp+ADh] [rbp+1Ch]
  __int16 v30; // [rsp+AEh] [rbp+1Dh]

  P[1] = (PVOID)-2LL;
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
  if ( CatalogHintFromEA < 0 )
  {
    Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(&v24);
    return (unsigned int)CatalogHintFromEA;
  }
  if ( !v25 )
  {
    if ( !a3 )
    {
      v19 = "onecore\\base\\wcp\\sil\\file.cpp";
      v20 = "Windows::Rtl::SystemImplementation::CFile::GetCatalogHint";
      v21 = 126;
      v22 = 0;
      RtlReportErrorOrigination(&v19, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225554LL);
      Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(&v24);
      return 3221225554LL;
    }
    *a3 = 2;
    Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(&v24);
    return 0;
  }
  if ( *(_BYTE *)(v25 + 5) != 15 )
  {
    v19 = "onecore\\base\\wcp\\sil\\file.cpp";
    v20 = "Windows::Rtl::SystemImplementation::CFile::GetCatalogHint";
    v21 = 132;
    v22 = 0;
    RtlReportErrorOrigination(&v19, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 2147483667LL);
    Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(&v24);
    return 2147483667LL;
  }
  P[0] = 0;
  CatalogHintFromEA = CiGetCatalogHintFromEA(v25, (unsigned int)v24, P);
  if ( CatalogHintFromEA < 0 )
  {
    if ( P[0] )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P[0]);
    Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(&v24);
    return (unsigned int)CatalogHintFromEA;
  }
  v18 = 0;
  v7 = P[0];
  CatalogNameFromHint = CiGetCatalogNameFromHint(P[0], 0, &v18);
  if ( CatalogNameFromHint < 0 )
  {
    if ( v7 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
    Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(&v24);
    return (unsigned int)CatalogNameFromHint;
  }
  v9 = (unsigned int)(v18 + 1);
  if ( v9 < 2 )
  {
    v11 = 0;
  }
  else
  {
    v10 = CoTaskMemAlloc(v9 & 0xFFFFFFFFFFFFFFFEuLL);
    v11 = v10;
    if ( !v10 )
    {
      v19 = "onecore\\base\\wcp\\sil\\file.cpp";
      v20 = "Windows::Rtl::SystemImplementation::CFile::GetCatalogHint";
      v21 = 142;
      v22 = "LocalHintName.ResizeBufferNoPreserve((CatalogNameSize + 1) / sizeof(WCHAR))";
      RtlReportErrorOrigination(&v19, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225495LL);
      if ( v7 )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
      Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(&v24);
      return 3221225495LL;
    }
    *v10 = 0;
  }
  v13 = CiGetCatalogNameFromHint(v7, v11, &v18);
  if ( v13 >= 0 )
  {
    *a2 = 0;
    if ( v11 )
    {
      v14 = -1;
      do
        ++v14;
      while ( v11[v14] );
      v15 = v11;
      v16 = 2 * v14;
    }
    else
    {
      v16 = 0;
      v15 = 0;
    }
    if ( a2[1] >= v16 || (v17 = RtlReallocateLUnicodeString(v12, v16, a2), v17 >= 0) )
    {
      if ( v16 )
      {
        if ( v16 > a2[1] - *a2 )
        {
          INTERNAL_ERROR_ACTION(-1073741595);
          JUMPOUT(0x1801C3CE7LL);
        }
        memcpy_0((void *)(a2[2] + 2LL * (*a2 >> 1)), v15, v16);
        *a2 += v16;
      }
      if ( a3 )
        *a3 = 1;
      if ( v11 )
        CoTaskMemFree(v11);
      if ( v7 )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
      Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(&v24);
      return 0;
    }
    if ( v11 )
      CoTaskMemFree(v11);
    if ( v7 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
    Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(&v24);
    return (unsigned int)v17;
  }
  else
  {
    if ( v11 )
      CoTaskMemFree(v11);
    if ( v7 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
    Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(&v24);
    return (unsigned int)v13;
  }
}

```

## disassembly

```asm
0x1801c3830  mov     rax, rsp
0x1801c3833  push    rbp
0x1801c3834  push    rsi
0x1801c3835  push    rdi
0x1801c3836  push    r12
0x1801c3838  push    r13
0x1801c383a  push    r14
0x1801c383c  push    r15
0x1801c383e  lea     rbp, [rax-5Fh]
0x1801c3842  sub     rsp, 0B0h
0x1801c3849  mov     [rbp+57h+var_70], 0FFFFFFFFFFFFFFFEh
0x1801c3851  mov     [rax+20h], rbx
0x1801c3855  mov     rax, cs:__security_cookie
0x1801c385c  xor     rax, rsp
0x1801c385f  mov     [rbp+57h+var_38], rax
0x1801c3863  mov     r15, r8
0x1801c3866  mov     rsi, rdx
0x1801c3869  xor     r12d, r12d
0x1801c386c  test    r8, r8
0x1801c386f  jz      short loc_1801C3874
0x1801c3871  mov     [r8], r12d
0x1801c3874  test    rsi, rsi
0x1801c3877  jnz     short loc_1801C38C2
0x1801c3879  lea     rax, aOnecoreBaseWcp_48; "onecore\\base\\wcp\\sil\\file.cpp"
0x1801c3880  mov     [rbp+57h+var_98], rax
0x1801c3884  lea     rax, aWindowsRtlSyst_19; "Windows::Rtl::SystemImplementation::CFi"...
0x1801c388b  mov     [rbp+57h+var_90], rax
0x1801c388f  mov     [rbp+57h+var_88], 61h ; 'a'
0x1801c3897  lea     rax, aNotNullCheckFa_1; "Not-null check failed: HintName"
0x1801c389e  mov     [rbp+57h+var_80], rax
0x1801c38a2  mov     r8d, 0C000000Dh
0x1801c38a8  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x1801c38af  lea     rcx, [rbp+57h+var_98]
0x1801c38b3  call    RtlReportErrorOrigination
0x1801c38b8  mov     eax, 0C000000Dh
0x1801c38bd  jmp     loc_1801C3CB5
0x1801c38c2  mov     [rbp+57h+var_50], r12d
0x1801c38c6  mov     [rbp+57h+var_3C], r12d
0x1801c38ca  mov     [rbp+57h+var_4C], 0Fh
0x1801c38ce  movsd   xmm0, qword ptr cs:aCiCataloghint; "$CI.CatalogHint"
0x1801c38d6  movsd   [rbp+57h+var_4B], xmm0
0x1801c38db  mov     eax, dword ptr cs:aCiCataloghint+8; "logHint"
0x1801c38e1  mov     [rbp+14h], eax
0x1801c38e4  movzx   eax, word ptr cs:aCiCataloghint+0Ch; "int"
0x1801c38eb  mov     [rbp+18h], ax
0x1801c38ef  mov     al, byte ptr cs:aCiCataloghint+0Eh; "t"
0x1801c38f5  mov     [rbp+1Ah], al
0x1801c38f8  xorps   xmm0, xmm0
0x1801c38fb  xor     eax, eax
0x1801c38fd  movups  [rbp+57h+var_68], xmm0
0x1801c3901  mov     [rbp+57h+var_58], rax
0x1801c3905  mov     rax, [rcx]
0x1801c3908  mov     [rsp+30h], r12b
0x1801c390d  mov     qword ptr [rsp+0E0h+var_B8], r12
0x1801c3912  mov     dword ptr [rsp+0E0h+var_C0], 18h
0x1801c391a  lea     r9, [rbp+57h+var_50]
0x1801c391e  xor     r8d, r8d
0x1801c3921  lea     rdx, [rbp+57h+var_68]
0x1801c3925  mov     rax, [rax+0D0h]
0x1801c392c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c3931  mov     ebx, eax
0x1801c3933  test    eax, eax
0x1801c3935  jns     short loc_1801C3948
0x1801c3937  lea     rcx, [rbp+57h+var_68]
0x1801c393b  call    ??1?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAA@XZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(void)
0x1801c3940  nop
0x1801c3941  mov     eax, ebx
0x1801c3943  jmp     loc_1801C3CB5
0x1801c3948  mov     rcx, [rbp+57h+var_58]
0x1801c394c  test    rcx, rcx
0x1801c394f  jnz     short loc_1801C39B9
0x1801c3951  test    r15, r15
0x1801c3954  jz      short loc_1801C396C
0x1801c3956  mov     dword ptr [r15], 2
0x1801c395d  lea     rcx, [rbp+57h+var_68]
0x1801c3961  call    ??1?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAA@XZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(void)
0x1801c3966  nop
0x1801c3967  jmp     loc_1801C3CB3
0x1801c396c  lea     rax, aOnecoreBaseWcp_48; "onecore\\base\\wcp\\sil\\file.cpp"
0x1801c3973  mov     [rbp+57h+var_98], rax
0x1801c3977  lea     rax, aWindowsRtlSyst_19; "Windows::Rtl::SystemImplementation::CFi"...
0x1801c397e  mov     [rbp+57h+var_90], rax
0x1801c3982  mov     [rbp+57h+var_88], 7Eh ; '~'
0x1801c398a  mov     [rbp+57h+var_80], r12
0x1801c398e  mov     r8d, 0C0000052h
0x1801c3994  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x1801c399b  lea     rcx, [rbp+57h+var_98]
0x1801c399f  call    RtlReportErrorOrigination
0x1801c39a4  nop
0x1801c39a5  lea     rcx, [rbp+57h+var_68]
0x1801c39a9  call    ??1?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAA@XZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(void)
0x1801c39ae  nop
0x1801c39af  mov     eax, 0C0000052h
0x1801c39b4  jmp     loc_1801C3CB5
0x1801c39b9  cmp     byte ptr [rcx+5], 0Fh
0x1801c39bd  jz      short loc_1801C3A0C
0x1801c39bf  lea     rax, aOnecoreBaseWcp_48; "onecore\\base\\wcp\\sil\\file.cpp"
0x1801c39c6  mov     [rbp+57h+var_98], rax
0x1801c39ca  lea     rax, aWindowsRtlSyst_19; "Windows::Rtl::SystemImplementation::CFi"...
0x1801c39d1  mov     [rbp+57h+var_90], rax
0x1801c39d5  mov     [rbp+57h+var_88], 84h
0x1801c39dd  mov     [rbp+57h+var_80], r12
0x1801c39e1  mov     r8d, 80000013h
0x1801c39e7  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x1801c39ee  lea     rcx, [rbp+57h+var_98]
0x1801c39f2  call    RtlReportErrorOrigination
0x1801c39f7  nop
0x1801c39f8  lea     rcx, [rbp+57h+var_68]
0x1801c39fc  call    ??1?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAA@XZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(void)
0x1801c3a01  nop
0x1801c3a02  mov     eax, 80000013h
0x1801c3a07  jmp     loc_1801C3CB5
0x1801c3a0c  mov     [rbp+57h+P], r12
0x1801c3a10  lea     r8, [rbp+57h+P]
0x1801c3a14  mov     edx, dword ptr [rbp+57h+var_68]
0x1801c3a17  call    CiGetCatalogHintFromEA
0x1801c3a1c  mov     ebx, eax
0x1801c3a1e  test    eax, eax
0x1801c3a20  jns     short loc_1801C3A56
0x1801c3a22  mov     r8, [rbp+57h+P]; P
0x1801c3a26  test    r8, r8
0x1801c3a29  jz      short loc_1801C3A47
0x1801c3a2b  mov     rcx, gs:60h
0x1801c3a34  xor     edx, edx; Flags
0x1801c3a36  mov     rcx, [rcx+30h]; HeapHandle
0x1801c3a3a  call    cs:__imp_RtlFreeHeap
0x1801c3a41  nop     dword ptr [rax+rax+00h]
0x1801c3a46  nop
0x1801c3a47  lea     rcx, [rbp+57h+var_68]
0x1801c3a4b  call    ??1?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAA@XZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(void)
0x1801c3a50  nop
0x1801c3a51  jmp     loc_1801C3941
0x1801c3a56  mov     [rbp+57h+var_A0], r12d
0x1801c3a5a  lea     r8, [rbp+57h+var_A0]
0x1801c3a5e  xor     edx, edx
0x1801c3a60  mov     rbx, [rbp+57h+P]
0x1801c3a64  mov     rcx, rbx
0x1801c3a67  call    CiGetCatalogNameFromHint
0x1801c3a6c  mov     edi, eax
0x1801c3a6e  test    eax, eax
0x1801c3a70  jns     short loc_1801C3AA7
0x1801c3a72  test    rbx, rbx
0x1801c3a75  jz      short loc_1801C3A96
0x1801c3a77  mov     rcx, gs:60h
0x1801c3a80  mov     r8, rbx; P
0x1801c3a83  xor     edx, edx; Flags
0x1801c3a85  mov     rcx, [rcx+30h]; HeapHandle
0x1801c3a89  call    cs:__imp_RtlFreeHeap
0x1801c3a90  nop     dword ptr [rax+rax+00h]
0x1801c3a95  nop
0x1801c3a96  lea     rcx, [rbp+57h+var_68]
0x1801c3a9a  call    ??1?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAA@XZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(void)
0x1801c3a9f  nop
0x1801c3aa0  mov     eax, edi
0x1801c3aa2  jmp     loc_1801C3CB5
0x1801c3aa7  mov     ecx, [rbp+57h+var_A0]
0x1801c3aaa  inc     ecx
0x1801c3aac  cmp     rcx, 2
0x1801c3ab0  jb      loc_1801C3B4B
0x1801c3ab6  and     rcx, 0FFFFFFFFFFFFFFFEh; cb
0x1801c3aba  call    cs:__imp_CoTaskMemAlloc
0x1801c3ac1  nop     dword ptr [rax+rax+00h]
0x1801c3ac6  mov     rdi, rax
0x1801c3ac9  test    rax, rax
0x1801c3acc  jz      short loc_1801C3AD4
0x1801c3ace  mov     [rax], r12w
0x1801c3ad2  jmp     short loc_1801C3B4E
0x1801c3ad4  lea     rax, aOnecoreBaseWcp_48; "onecore\\base\\wcp\\sil\\file.cpp"
0x1801c3adb  mov     [rbp+57h+var_98], rax
0x1801c3adf  lea     rax, aWindowsRtlSyst_19; "Windows::Rtl::SystemImplementation::CFi"...
0x1801c3ae6  mov     [rbp+57h+var_90], rax
0x1801c3aea  mov     [rbp+57h+var_88], 8Eh
0x1801c3af2  lea     rax, aLocalhintnameR; "LocalHintName.ResizeBufferNoPreserve((C"...
0x1801c3af9  mov     [rbp+57h+var_80], rax
0x1801c3afd  mov     r8d, 0C0000017h
0x1801c3b03  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x1801c3b0a  lea     rcx, [rbp+57h+var_98]
0x1801c3b0e  call    RtlReportErrorOrigination
0x1801c3b13  test    rbx, rbx
0x1801c3b16  jz      short loc_1801C3B37
0x1801c3b18  mov     rcx, gs:60h
0x1801c3b21  mov     r8, rbx; P
0x1801c3b24  xor     edx, edx; Flags
0x1801c3b26  mov     rcx, [rcx+30h]; HeapHandle
0x1801c3b2a  call    cs:__imp_RtlFreeHeap
0x1801c3b31  nop     dword ptr [rax+rax+00h]
0x1801c3b36  nop
0x1801c3b37  lea     rcx, [rbp+57h+var_68]
0x1801c3b3b  call    ??1?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAA@XZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(void)
0x1801c3b40  nop
0x1801c3b41  mov     eax, 0C0000017h
0x1801c3b46  jmp     loc_1801C3CB5
0x1801c3b4b  mov     rdi, r12
0x1801c3b4e  lea     r8, [rbp+57h+var_A0]
0x1801c3b52  mov     rdx, rdi
0x1801c3b55  mov     rcx, rbx
0x1801c3b58  call    CiGetCatalogNameFromHint
0x1801c3b5d  mov     r14d, eax
0x1801c3b60  test    eax, eax
0x1801c3b62  jns     short loc_1801C3BAE
0x1801c3b64  test    rdi, rdi
0x1801c3b67  jz      short loc_1801C3B78
0x1801c3b69  mov     rcx, rdi; pv
0x1801c3b6c  call    cs:__imp_CoTaskMemFree
0x1801c3b73  nop     dword ptr [rax+rax+00h]
0x1801c3b78  test    rbx, rbx
0x1801c3b7b  jz      short loc_1801C3B9C
0x1801c3b7d  mov     rcx, gs:60h
0x1801c3b86  mov     r8, rbx; P
0x1801c3b89  xor     edx, edx; Flags
0x1801c3b8b  mov     rcx, [rcx+30h]; HeapHandle
0x1801c3b8f  call    cs:__imp_RtlFreeHeap
0x1801c3b96  nop     dword ptr [rax+rax+00h]
0x1801c3b9b  nop
0x1801c3b9c  lea     rcx, [rbp+57h+var_68]
0x1801c3ba0  call    ??1?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAA@XZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(void)
0x1801c3ba5  nop
0x1801c3ba6  mov     eax, r14d
0x1801c3ba9  jmp     loc_1801C3CB5
0x1801c3bae  mov     [rsi], r12
0x1801c3bb1  test    rdi, rdi
0x1801c3bb4  jz      short loc_1801C3BCC
0x1801c3bb6  or      r14, 0FFFFFFFFFFFFFFFFh
0x1801c3bba  inc     r14
0x1801c3bbd  cmp     [rdi+r14*2], r12w
0x1801c3bc2  jnz     short loc_1801C3BBA
0x1801c3bc4  mov     r13, rdi
0x1801c3bc7  add     r14, r14
0x1801c3bca  jmp     short loc_1801C3BD2
0x1801c3bcc  mov     r14, r12
0x1801c3bcf  mov     r13, r12
0x1801c3bd2  cmp     [rsi+8], r14
0x1801c3bd6  jnb     short loc_1801C3C34
0x1801c3bd8  mov     r8, rsi
0x1801c3bdb  mov     rdx, r14
0x1801c3bde  call    RtlReallocateLUnicodeString
0x1801c3be3  mov     r12d, eax
0x1801c3be6  test    eax, eax
0x1801c3be8  jns     short loc_1801C3C34
0x1801c3bea  test    rdi, rdi
0x1801c3bed  jz      short loc_1801C3BFE
0x1801c3bef  mov     rcx, rdi; pv
0x1801c3bf2  call    cs:__imp_CoTaskMemFree
0x1801c3bf9  nop     dword ptr [rax+rax+00h]
0x1801c3bfe  test    rbx, rbx
0x1801c3c01  jz      short loc_1801C3C22
0x1801c3c03  mov     rcx, gs:60h
0x1801c3c0c  mov     r8, rbx; P
0x1801c3c0f  xor     edx, edx; Flags
0x1801c3c11  mov     rcx, [rcx+30h]; HeapHandle
0x1801c3c15  call    cs:__imp_RtlFreeHeap
0x1801c3c1c  nop     dword ptr [rax+rax+00h]
0x1801c3c21  nop
0x1801c3c22  lea     rcx, [rbp+57h+var_68]
0x1801c3c26  call    ??1?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAA@XZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(void)
0x1801c3c2b  nop
0x1801c3c2c  mov     eax, r12d
0x1801c3c2f  jmp     loc_1801C3CB5
0x1801c3c34  test    r14, r14
0x1801c3c37  jz      short loc_1801C3C65
0x1801c3c39  mov     rcx, [rsi]
0x1801c3c3c  mov     rax, [rsi+8]
0x1801c3c40  sub     rax, rcx
0x1801c3c43  cmp     r14, rax
0x1801c3c46  ja      loc_1801C3CDD
0x1801c3c4c  shr     rcx, 1
0x1801c3c4f  mov     rax, [rsi+10h]
0x1801c3c53  lea     rcx, [rax+rcx*2]; void *
0x1801c3c57  mov     r8, r14; Size
0x1801c3c5a  mov     rdx, r13; Src
0x1801c3c5d  call    memcpy_0
0x1801c3c62  add     [rsi], r14
0x1801c3c65  test    r15, r15
0x1801c3c68  jz      short loc_1801C3C71
0x1801c3c6a  mov     dword ptr [r15], 1
0x1801c3c71  test    rdi, rdi
0x1801c3c74  jz      short loc_1801C3C85
0x1801c3c76  mov     rcx, rdi; pv
0x1801c3c79  call    cs:__imp_CoTaskMemFree
0x1801c3c80  nop     dword ptr [rax+rax+00h]
0x1801c3c85  test    rbx, rbx
0x1801c3c88  jz      short loc_1801C3CA9
0x1801c3c8a  mov     rcx, gs:60h
0x1801c3c93  mov     r8, rbx; P
0x1801c3c96  xor     edx, edx; Flags
0x1801c3c98  mov     rcx, [rcx+30h]; HeapHandle
0x1801c3c9c  call    cs:__imp_RtlFreeHeap
0x1801c3ca3  nop     dword ptr [rax+rax+00h]
0x1801c3ca8  nop
0x1801c3ca9  lea     rcx, [rbp+57h+var_68]
0x1801c3cad  call    ??1?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAA@XZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(void)
0x1801c3cb2  nop
0x1801c3cb3  xor     eax, eax
0x1801c3cb5  mov     rcx, [rbp+57h+var_38]
0x1801c3cb9  xor     rcx, rsp; StackCookie
0x1801c3cbc  call    __security_check_cookie
0x1801c3cc1  mov     rbx, [rsp+0E0h+arg_18]
0x1801c3cc9  add     rsp, 0B0h
0x1801c3cd0  pop     r15
0x1801c3cd2  pop     r14
  ... truncated ...
```
