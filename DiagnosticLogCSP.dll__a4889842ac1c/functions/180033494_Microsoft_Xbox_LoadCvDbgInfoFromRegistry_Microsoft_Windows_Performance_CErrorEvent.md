# Microsoft::Xbox::LoadCvDbgInfoFromRegistry(Microsoft::Windows::Performance::CErrorEvent *)

- ea: `0x180033494`
- end: `0x180033a7a`
- name: `?LoadCvDbgInfoFromRegistry@Xbox@Microsoft@@YAJPEAVCErrorEvent@Performance@Windows@2@@Z`
- size: `1510`
- prototype: `__int64 __fastcall(Microsoft::Xbox *__hidden this, struct Microsoft::Windows::Performance::CErrorEvent *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180020204`

## callees

- `0x180001b60`
- `0x180001b84`
- `0x18000262c`
- `0x180002cf5`
- `0x18000bb3c`
- `0x1800305e0`
- `0x180030804`
- `0x18003237c`
- `0x180032ab8`
- `0x180032e2c`
- `0x180033494`
- `0x180037010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18003357c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18003357c`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1800338d5`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1800338d5`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180033877`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180033877`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180033748`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180033790`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180033821`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180033748`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180033790`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180033821`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180033918`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180033918`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800335b8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800336a7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800335b8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800336a7`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180033539`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180033539`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033a3e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033a3e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800334eb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800334eb`

## string_xrefs

- `0x1800334f7`: `Unable to open RegKey HKLM\System\Software\Microsoft (%x)`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall Microsoft::Xbox::LoadCvDbgInfoFromRegistry(
        Microsoft::Xbox *this,
        struct Microsoft::Windows::Performance::CErrorEvent *a2)
{
  int v3; // edi
  const wchar_t *v4; // rdx
  DWORD i; // ebx
  unsigned __int64 v6; // rax
  LSTATUS v7; // ebx
  size_t v8; // r15
  BYTE *v9; // rax
  void *v10; // rax
  void *v11; // rcx
  BYTE *v12; // rbx
  LSTATUS v13; // ebx
  unsigned __int64 v14; // r15
  LPBYTE v15; // r12
  __int64 v16; // rbx
  DWORD v17; // ecx
  const wchar_t *v18; // r12
  wchar_t *v19; // rax
  wchar_t *v20; // rax
  wchar_t *v21; // r13
  __int64 v22; // rcx
  __int64 v23; // r9
  DWORD cbData; // [rsp+40h] [rbp-AB8h] BYREF
  DWORD cchValueName[2]; // [rsp+48h] [rbp-AB0h] BYREF
  char v27; // [rsp+50h] [rbp-AA8h]
  HKEY hKey; // [rsp+58h] [rbp-AA0h] BYREF
  LPBYTE v29[2]; // [rsp+60h] [rbp-A98h] BYREF
  BYTE *v30; // [rsp+70h] [rbp-A88h]
  DWORD Type; // [rsp+78h] [rbp-A80h] BYREF
  wchar_t *v32; // [rsp+80h] [rbp-A78h]
  wchar_t *v33; // [rsp+88h] [rbp-A70h]
  _BYTE Src[520]; // [rsp+90h] [rbp-A68h] BYREF
  int v35; // [rsp+298h] [rbp-860h]
  _BYTE v36[16]; // [rsp+29Ch] [rbp-85Ch] BYREF
  int v37; // [rsp+2ACh] [rbp-84Ch]
  CHAR MultiByteStr[1552]; // [rsp+2B0h] [rbp-848h] BYREF
  WCHAR ValueName[256]; // [rsp+8C0h] [rbp-238h] BYREF

  hKey = 0;
  v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\Software\\Microsoft", 0, 0x20019u, &hKey);
  if ( v3 )
  {
    v4 = L"Unable to open RegKey HKLM\\System\\Software\\Microsoft (%x)";
LABEL_53:
    (*(void (__fastcall **)(Microsoft::Xbox *, const wchar_t *, _QWORD))(*(_QWORD *)this + 8LL))(
      this,
      v4,
      (unsigned int)v3);
    if ( v3 > 0 )
    {
      v3 = (unsigned __int16)v3;
LABEL_55:
      v3 |= 0x80070000;
    }
  }
  else
  {
    for ( i = 0; ; ++i )
    {
      cchValueName[0] = 256;
      v3 = RegEnumValueW(hKey, i, ValueName, cchValueName, 0, 0, 0, 0);
      if ( v3 )
      {
        v4 = L"Unable to enum reg values (%x)";
        goto LABEL_53;
      }
      v6 = -1;
      do
        ++v6;
      while ( ValueName[v6] );
      if ( v6 >= 4 && !(unsigned int)_o__wcsnicmp(&MultiByteStr[2 * v6 + 1544], L"_vbi", 4) )
        break;
    }
    v3 = 0;
    Type = 0;
    cbData = 0;
    v7 = RegQueryValueExW(hKey, ValueName, 0, &Type, 0, &cbData);
    if ( v7 )
    {
      (*(void (__fastcall **)(Microsoft::Xbox *, const wchar_t *, _QWORD))(*(_QWORD *)this + 8LL))(
        this,
        L"unable to query vbi reg value for size",
        (unsigned int)v7);
      if ( v7 <= 0 )
      {
        v3 = v7;
        goto LABEL_56;
      }
      v3 = (unsigned __int16)v7;
      goto LABEL_55;
    }
    *(_OWORD *)v29 = 0;
    v30 = 0;
    if ( cbData )
    {
      v8 = 2LL * cbData;
      if ( v8 )
      {
        if ( v8 < 0x1000 )
        {
          v9 = (BYTE *)operator new(v8);
        }
        else
        {
          if ( v8 + 39 < v8 )
            __scrt_throw_std_bad_array_new_length();
          v10 = operator new(v8 + 39);
          v11 = v10;
          if ( !v10 )
            __fastfail(5u);
          v9 = (BYTE *)(((unsigned __int64)v10 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
          *((_QWORD *)v9 - 1) = v11;
        }
      }
      else
      {
        v9 = 0;
      }
      v29[0] = v9;
      v12 = &v9[v8];
      v30 = &v9[v8];
      memset_0(v9, 0, v8);
      v29[1] = v12;
      *(_QWORD *)cchValueName = 0;
      std::_Tidy_guard<std::vector<unsigned short>>::~_Tidy_guard<std::vector<unsigned short>>(cchValueName);
    }
    v13 = RegQueryValueExW(hKey, ValueName, 0, 0, v29[0], &cbData);
    if ( v13 )
    {
      (*(void (__fastcall **)(Microsoft::Xbox *, const wchar_t *, _QWORD))(*(_QWORD *)this + 8LL))(
        this,
        L"unable to query vbi reg value for data",
        (unsigned int)v13);
      if ( v13 > 0 )
        v3 = (unsigned __int16)v13 | 0x80070000;
      else
        v3 = v13;
      std::vector<unsigned short>::~vector<unsigned short>(v29);
    }
    else
    {
      v14 = 0;
      v15 = v29[0];
      v16 = -1;
      do
        ++v16;
      while ( *(_WORD *)&v29[0][2 * v16] );
      v17 = cbData;
      while ( v16 && v14 < v17 )
      {
        memset_0(Src, 0, 0x830u);
        v35 = 1396986706;
        v18 = (const wchar_t *)&v15[2 * v14];
        v19 = wcsstr(v18, L"@");
        *(_QWORD *)cchValueName = v19;
        if ( !v19 )
          goto LABEL_38;
        v20 = wcsstr(v19, L"}");
        v21 = v20;
        if ( !v20
          || v20 + 1 >= &v18[v16 - 1]
          || (v32 = v20 + 2, (v33 = wcsstr(v20 + 2, L" ")) == 0)
          || (**(_WORD **)cchValueName = 0,
              _o_wcscpy_s(Src, 260, v18),
              *v21 = 0,
              *(_QWORD *)cchValueName += 4LL,
              !tlx::string_to_guid<unsigned short *>(v36, cchValueName))
          || (v37 = _o__wtoi(v32), WideCharToMultiByte(0, 0, v33 + 1, -1, MultiByteStr, 780, 0, 0) <= 0) )
        {
LABEL_38:
          (*(void (**)(Microsoft::Xbox *, const wchar_t *, ...))(*(_QWORD *)this + 8LL))(
            this,
            L"malformed VBI Dbg Id entry: %s",
            v18);
          v3 = -2147467259;
          std::vector<unsigned short>::~vector<unsigned short>(v29);
          goto LABEL_56;
        }
        if ( qword_18004B700 == (void *)qword_18004B708 )
        {
          std::vector<Microsoft::Xbox::PdbInfoRecord>::_Emplace_reallocate<Microsoft::Xbox::PdbInfoRecord const &>(
            v22,
            qword_18004B700,
            Src);
        }
        else
        {
          memcpy_0(qword_18004B700, Src, 0x830u);
          qword_18004B700 = (char *)qword_18004B700 + 2096;
        }
        v14 += v16 + 1;
        v15 = v29[0];
        if ( !*(_WORD *)&v29[0][2 * v14] )
          ++v14;
        v17 = cbData;
        if ( v14 < cbData )
        {
          v16 = -1;
          do
            ++v16;
          while ( *(_WORD *)&v29[0][2 * v14 + 2 * v16] );
        }
      }
      std::vector<unsigned short>::~vector<unsigned short>(v29);
      LOBYTE(v23) = v27;
      std::_Sort_unchecked_Microsoft::Xbox::PdbInfoRecord____lambda_f7a8b1b861ea55e52666277e77b7ead8___(
        Microsoft::Xbox::pdbRecords,
        qword_18004B700,
        0x3E88CB3C9484E2BLL * (((_BYTE *)qword_18004B700 - (_BYTE *)Microsoft::Xbox::pdbRecords) >> 4),
        v23);
    }
  }
LABEL_56:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180033494  mov     [rsp+arg_8], rbx
0x180033499  mov     [rsp+arg_10], rsi
0x18003349e  push    rdi
0x18003349f  push    r12
0x1800334a1  push    r13
0x1800334a3  push    r14
0x1800334a5  push    r15
0x1800334a7  sub     rsp, 0AD0h
0x1800334ae  mov     rax, cs:__security_cookie
0x1800334b5  xor     rax, rsp
0x1800334b8  mov     [rsp+0AF8h+var_38], rax
0x1800334c0  mov     r14, rcx
0x1800334c3  xor     esi, esi
0x1800334c5  mov     [rsp+0AF8h+hKey], rsi
0x1800334ca  lea     rax, [rsp+0AF8h+hKey]
0x1800334cf  mov     [rsp+0AF8h+phkResult], rax; phkResult
0x1800334d4  mov     r9d, 20019h; samDesired
0x1800334da  xor     r8d, r8d; ulOptions
0x1800334dd  lea     rdx, aSystemSoftware; "System\\Software\\Microsoft"
0x1800334e4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800334eb  call    cs:__imp_RegOpenKeyExW
0x1800334f1  mov     edi, eax
0x1800334f3  test    eax, eax
0x1800334f5  jz      short loc_180033503
0x1800334f7  lea     rdx, aUnableToOpenRe; "Unable to open RegKey HKLM\\System\\Sof"...
0x1800334fe  jmp     loc_180033A15
0x180033503  mov     ebx, esi
0x180033505  or      r13, 0FFFFFFFFFFFFFFFFh
0x180033509  mov     [rsp+0AF8h+cchValueName], 100h
0x180033511  mov     [rsp+0AF8h+lpcbData], rsi; lpcbData
0x180033516  mov     [rsp+0AF8h+lpData], rsi; lpData
0x18003351b  mov     [rsp+0AF8h+lpType], rsi; lpType
0x180033520  mov     [rsp+0AF8h+phkResult], rsi; lpReserved
0x180033525  lea     r9, [rsp+0AF8h+cchValueName]; lpcchValueName
0x18003352a  lea     r8, [rsp+0AF8h+ValueName]; lpValueName
0x180033532  mov     edx, ebx; dwIndex
0x180033534  mov     rcx, [rsp+0AF8h+hKey]; hKey
0x180033539  call    cs:__imp_RegEnumValueW
0x18003353f  mov     edi, eax
0x180033541  test    eax, eax
0x180033543  jnz     loc_180033A0E
0x180033549  lea     rcx, [rsp+0AF8h+ValueName]
0x180033551  mov     rax, r13
0x180033554  inc     rax
0x180033557  cmp     [rcx+rax*2], si
0x18003355b  jnz     short loc_180033554
0x18003355d  cmp     rax, 4
0x180033561  jb      loc_180033A07
0x180033567  lea     rcx, [rsp+rax*2+0AF8h+var_240]
0x18003356f  mov     r8d, 4
0x180033575  lea     rdx, aVbi; "_vbi"
0x18003357c  call    cs:__imp__o__wcsnicmp
0x180033582  test    eax, eax
0x180033584  jnz     loc_180033A07
0x18003358a  mov     edi, esi
0x18003358c  mov     [rsp+0AF8h+Type], esi
0x180033590  mov     [rsp+0AF8h+cbData], esi
0x180033594  lea     rax, [rsp+0AF8h+cbData]
0x180033599  mov     [rsp+0AF8h+lpType], rax; lpcbData
0x18003359e  mov     [rsp+0AF8h+phkResult], rsi; lpData
0x1800335a3  lea     r9, [rsp+0AF8h+Type]; lpType
0x1800335a8  xor     r8d, r8d; lpReserved
0x1800335ab  lea     rdx, [rsp+0AF8h+ValueName]; lpValueName
0x1800335b3  mov     rcx, [rsp+0AF8h+hKey]; hKey
0x1800335b8  call    cs:__imp_RegQueryValueExW
0x1800335be  mov     ebx, eax
0x1800335c0  test    eax, eax
0x1800335c2  jz      short loc_1800335F0
0x1800335c4  mov     rcx, [r14]
0x1800335c7  mov     rax, [rcx+8]
0x1800335cb  mov     r8d, ebx
0x1800335ce  lea     rdx, aUnableToQueryV; "unable to query vbi reg value for size"
0x1800335d5  mov     rcx, r14
0x1800335d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800335dd  test    ebx, ebx
0x1800335df  jg      short loc_1800335E8
0x1800335e1  mov     edi, ebx
0x1800335e3  jmp     loc_180033A34
0x1800335e8  movzx   edi, bx
0x1800335eb  jmp     loc_180033A2E
0x1800335f0  mov     r15d, [rsp+0AF8h+cbData]
0x1800335f5  xorps   xmm0, xmm0
0x1800335f8  movdqu  xmmword ptr [rsp+0AF8h+var_A98], xmm0
0x1800335fe  mov     [rsp+0AF8h+var_A88], rsi
0x180033603  test    r15, r15
0x180033606  jz      short loc_180033680
0x180033608  add     r15, r15
0x18003360b  jnz     short loc_180033612
0x18003360d  mov     rax, rsi
0x180033610  jmp     short loc_180033650
0x180033612  cmp     r15, 1000h
0x180033619  jb      short loc_180033648
0x18003361b  lea     rcx, [r15+27h]; Size
0x18003361f  cmp     rcx, r15
0x180033622  jbe     loc_180033A73
0x180033628  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003362d  mov     rcx, rax
0x180033630  test    rax, rax
0x180033633  jnz     short loc_18003363A
0x180033635  lea     ecx, [rax+5]
0x180033638  int     29h; Win8: RtlFailFast(ecx)
0x18003363a  add     rax, 27h ; '''
0x18003363e  and     rax, 0FFFFFFFFFFFFFFE0h
0x180033642  mov     [rax-8], rcx
0x180033646  jmp     short loc_180033650
0x180033648  mov     rcx, r15; Size
0x18003364b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180033650  mov     [rsp+0AF8h+var_A98], rax
0x180033655  lea     rbx, [rax+r15]
0x180033659  mov     [rsp+0AF8h+var_A88], rbx
0x18003365e  mov     r8, r15; Size
0x180033661  xor     edx, edx; Val
0x180033663  mov     rcx, rax; void *
0x180033666  call    memset_0
0x18003366b  mov     [rsp+0AF8h+var_A98+8], rbx
0x180033670  mov     qword ptr [rsp+0AF8h+cchValueName], rsi
0x180033675  lea     rcx, [rsp+0AF8h+cchValueName]
0x18003367a  call    ??1?$_Tidy_guard@V?$vector@GV?$allocator@G@std@@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<ushort>>::~_Tidy_guard<std::vector<ushort>>(void)
0x18003367f  nop
0x180033680  mov     rax, [rsp+0AF8h+var_A98]
0x180033685  lea     rcx, [rsp+0AF8h+cbData]
0x18003368a  mov     [rsp+0AF8h+lpType], rcx; lpcbData
0x18003368f  mov     [rsp+0AF8h+phkResult], rax; lpData
0x180033694  xor     r9d, r9d; lpType
0x180033697  xor     r8d, r8d; lpReserved
0x18003369a  lea     rdx, [rsp+0AF8h+ValueName]; lpValueName
0x1800336a2  mov     rcx, [rsp+0AF8h+hKey]; hKey
0x1800336a7  call    cs:__imp_RegQueryValueExW
0x1800336ad  mov     ebx, eax
0x1800336af  test    eax, eax
0x1800336b1  jz      short loc_1800336ED
0x1800336b3  mov     rcx, [r14]
0x1800336b6  mov     rax, [rcx+8]
0x1800336ba  mov     r8d, ebx
0x1800336bd  lea     rdx, aUnableToQueryV_0; "unable to query vbi reg value for data"
0x1800336c4  mov     rcx, r14
0x1800336c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800336cc  test    ebx, ebx
0x1800336ce  jg      short loc_1800336D4
0x1800336d0  mov     edi, ebx
0x1800336d2  jmp     short loc_1800336DD
0x1800336d4  movzx   edi, bx
0x1800336d7  or      edi, 80070000h
0x1800336dd  lea     rcx, [rsp+0AF8h+var_A98]
0x1800336e2  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x1800336e7  nop
0x1800336e8  jmp     loc_180033A34
0x1800336ed  mov     r15, rsi
0x1800336f0  mov     r12, [rsp+0AF8h+var_A98]
0x1800336f5  mov     rbx, r13
0x1800336f8  inc     rbx
0x1800336fb  cmp     [r12+rbx*2], si
0x180033700  jnz     short loc_1800336F8
0x180033702  mov     ecx, [rsp+0AF8h+cbData]
0x180033706  test    rbx, rbx
0x180033709  jz      loc_1800339C4
0x18003370f  mov     eax, ecx
0x180033711  cmp     r15, rax
0x180033714  jnb     loc_1800339C4
0x18003371a  xor     edx, edx; Val
0x18003371c  mov     r8d, 830h; Size
0x180033722  lea     rcx, [rsp+0AF8h+Src]; void *
0x18003372a  call    memset_0
0x18003372f  mov     [rsp+0AF8h+var_860], 53445352h
0x18003373a  lea     r12, [r12+r15*2]
0x18003373e  lea     rdx, asc_18003DBF0; "@"
0x180033745  mov     rcx, r12; Str
0x180033748  call    cs:__imp_wcsstr
0x18003374e  mov     qword ptr [rsp+0AF8h+cchValueName], rax
0x180033753  test    rax, rax
0x180033756  jnz     short loc_180033786
0x180033758  mov     rax, [r14]
0x18003375b  mov     r8, r12
0x18003375e  lea     rdx, aMalformedVbiDb; "malformed VBI Dbg Id entry: %s"
0x180033765  mov     rcx, r14
0x180033768  mov     rax, [rax+8]
0x18003376c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033771  mov     edi, 80004005h
0x180033776  lea     rcx, [rsp+0AF8h+var_A98]
0x18003377b  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180033780  nop
0x180033781  jmp     loc_180033A34
0x180033786  lea     rdx, asc_18003DC38; "}"
0x18003378d  mov     rcx, rax; Str
0x180033790  call    cs:__imp_wcsstr
0x180033796  mov     r13, rax
0x180033799  test    rax, rax
0x18003379c  jnz     short loc_1800337CC
0x18003379e  mov     rax, [r14]
0x1800337a1  mov     r8, r12
0x1800337a4  lea     rdx, aMalformedVbiDb; "malformed VBI Dbg Id entry: %s"
0x1800337ab  mov     rcx, r14
0x1800337ae  mov     rax, [rax+8]
0x1800337b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800337b7  mov     edi, 80004005h
0x1800337bc  lea     rcx, [rsp+0AF8h+var_A98]
0x1800337c1  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x1800337c6  nop
0x1800337c7  jmp     loc_180033A34
0x1800337cc  lea     rcx, [rax+2]
0x1800337d0  lea     rax, [rbx-1]
0x1800337d4  lea     rax, [r12+rax*2]
0x1800337d8  cmp     rcx, rax
0x1800337db  jb      short loc_18003380B
0x1800337dd  mov     rax, [r14]
0x1800337e0  mov     r8, r12
0x1800337e3  lea     rdx, aMalformedVbiDb; "malformed VBI Dbg Id entry: %s"
0x1800337ea  mov     rcx, r14
0x1800337ed  mov     rax, [rax+8]
0x1800337f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800337f6  mov     edi, 80004005h
0x1800337fb  lea     rcx, [rsp+0AF8h+var_A98]
0x180033800  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180033805  nop
0x180033806  jmp     loc_180033A34
0x18003380b  lea     rax, [rcx+2]
0x18003380f  mov     [rsp+0AF8h+var_A78], rax
0x180033817  lea     rdx, asc_18003DC3C; " "
0x18003381e  mov     rcx, rax; Str
0x180033821  call    cs:__imp_wcsstr
0x180033827  mov     [rsp+0AF8h+var_A70], rax
0x18003382f  mov     r8, r12
0x180033832  test    rax, rax
0x180033835  jnz     short loc_180033862
0x180033837  mov     rax, [r14]
0x18003383a  lea     rdx, aMalformedVbiDb; "malformed VBI Dbg Id entry: %s"
0x180033841  mov     rcx, r14
0x180033844  mov     rax, [rax+8]
0x180033848  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003384d  mov     edi, 80004005h
0x180033852  lea     rcx, [rsp+0AF8h+var_A98]
0x180033857  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18003385c  nop
0x18003385d  jmp     loc_180033A34
0x180033862  mov     rax, qword ptr [rsp+0AF8h+cchValueName]
0x180033867  mov     [rax], si
0x18003386a  mov     edx, 104h
0x18003386f  lea     rcx, [rsp+0AF8h+Src]
0x180033877  call    cs:__imp__o_wcscpy_s
0x18003387d  mov     [r13+0], si
0x180033882  add     qword ptr [rsp+0AF8h+cchValueName], 4
0x180033888  lea     rdx, [rsp+0AF8h+cchValueName]
0x18003388d  lea     rcx, [rsp+0AF8h+var_85C]
0x180033895  call    ??$string_to_guid@PEAG@tlx@@YAPEAGPEAU_GUID@@AEBQEAG@Z; tlx::string_to_guid<ushort *>(_GUID *,ushort * const &)
0x18003389a  test    rax, rax
0x18003389d  jnz     short loc_1800338CD
0x18003389f  mov     rax, [r14]
0x1800338a2  mov     r8, r12
0x1800338a5  lea     rdx, aMalformedVbiDb; "malformed VBI Dbg Id entry: %s"
0x1800338ac  mov     rcx, r14
0x1800338af  mov     rax, [rax+8]
0x1800338b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800338b8  mov     edi, 80004005h
0x1800338bd  lea     rcx, [rsp+0AF8h+var_A98]
0x1800338c2  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x1800338c7  nop
0x1800338c8  jmp     loc_180033A34
0x1800338cd  mov     rcx, [rsp+0AF8h+var_A78]
0x1800338d5  call    cs:__imp__o__wtoi
0x1800338db  mov     [rsp+0AF8h+var_84C], eax
0x1800338e2  mov     r8, [rsp+0AF8h+var_A70]
0x1800338ea  add     r8, 2; lpWideCharStr
0x1800338ee  mov     [rsp+0AF8h+lpcbData], rsi; lpUsedDefaultChar
0x1800338f3  mov     [rsp+0AF8h+lpData], rsi; lpDefaultChar
0x1800338f8  mov     dword ptr [rsp+0AF8h+lpType], 30Ch; cbMultiByte
0x180033900  lea     rax, [rsp+0AF8h+MultiByteStr]
0x180033908  mov     [rsp+0AF8h+phkResult], rax; lpMultiByteStr
0x18003390d  or      r13, 0FFFFFFFFFFFFFFFFh
0x180033911  mov     r9d, r13d; cchWideChar
0x180033914  xor     edx, edx; dwFlags
0x180033916  xor     ecx, ecx; CodePage
0x180033918  call    cs:__imp_WideCharToMultiByte
0x18003391e  test    eax, eax
0x180033920  jle     short loc_180033999
0x180033922  mov     rdx, cs:qword_18004B700
0x180033929  cmp     rdx, cs:qword_18004B708
0x180033930  jz      short loc_180033955
0x180033932  mov     rcx, rdx; void *
0x180033935  lea     rdx, [rsp+0AF8h+Src]; Src
0x18003393d  mov     r8d, 830h; Size
0x180033943  call    memcpy_0
0x180033948  add     cs:qword_18004B700, 830h
0x180033953  jmp     short loc_180033962
0x180033955  lea     r8, [rsp+0AF8h+Src]
0x18003395d  call    ??$_Emplace_reallocate@AEBUPdbInfoRecord@Xbox@Microsoft@@@?$vector@UPdbInfoRecord@Xbox@Microsoft@@V?$allocator@UPdbInfoRecord@Xbox@Microsoft@@@std@@@std@@AEAAPEAUPdbInfoRecord@Xbox@Microsoft@@QEAU234@AEBU234@@Z; std::vector<Microsoft::Xbox::PdbInfoRecord>::_Emplace_reallocate<Microsoft::Xbox::PdbInfoRecord const &>(Microsoft::Xbox::PdbInfoRecord * const,Microsoft::Xbox::PdbInfoRecord const &)
0x180033962  inc     r15
0x180033965  add     r15, rbx
0x180033968  mov     r12, [rsp+0AF8h+var_A98]
0x18003396d  cmp     [r12+r15*2], si
0x180033972  jnz     short loc_180033977
0x180033974  inc     r15
0x180033977  mov     ecx, [rsp+0AF8h+cbData]
0x18003397b  cmp     r15, rcx
0x18003397e  jnb     loc_180033706
0x180033984  lea     rax, [r12+r15*2]
0x180033988  mov     rbx, r13
0x18003398b  inc     rbx
0x18003398e  cmp     [rax+rbx*2], si
0x180033992  jnz     short loc_18003398B
0x180033994  jmp     loc_180033706
  ... truncated ...
```
