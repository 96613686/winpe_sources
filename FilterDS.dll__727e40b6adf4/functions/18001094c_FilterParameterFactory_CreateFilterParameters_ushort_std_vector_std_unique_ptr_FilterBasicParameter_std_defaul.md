# FilterParameterFactory::CreateFilterParameters(ushort,std::vector<std::unique_ptr<FilterBasicParameter,std::default_delete<FilterBasicParameter>>,std::allocator<std::unique_ptr<FilterBasicParameter,std::default_delete<FilterBasicParameter>>>> &)

- ea: `0x18001094c`
- end: `0x180011191`
- name: `?CreateFilterParameters@FilterParameterFactory@@SAJGAEAV?$vector@V?$unique_ptr@VFilterBasicParameter@@U?$default_delete@VFilterBasicParameter@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterBasicParameter@@U?$default_delete@VFilterBasicParameter@@@std@@@std@@@2@@std@@@Z`
- size: `2117`
- prototype: `__int64 __fastcall(unsigned __int16, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800104e4`

## callees

- `0x180001a30`
- `0x180005ca4`
- `0x18001094c`
- `0x18001161c`
- `0x180012560`
- `0x1800127b8`
- `0x180015ba0`
- `0x18001600c`
- `0x1800160c0`
- `0x180016124`
- `0x180021822`
- `0x180021850`
- `0x180024010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800109fb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010aec`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010e29`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010e3a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001109c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800110ad`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800110d5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800110e4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011145`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011154`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011166`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800109fb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010aec`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010e29`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010e3a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001109c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800110ad`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800110d5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800110e4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011145`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011154`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011166`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180010a59`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180010a59`

## string_xrefs

- `0x180010b99`: `GroupPolicyPath`
- `0x180010f19`: `GroupPolicyPath`
- `0x180010bc5`: `RegCharCodeAreaPath`
- `0x180010f80`: `RegCheckPath`
- `0x180010f01`: `RegDictionaryPath`
- `0x180010eec`: `DictionaryPath`
- `0x180010ed4`: `DGMLPath`

## pseudocode

```c
__int64 __fastcall FilterParameterFactory::CreateFilterParameters(unsigned __int16 a1, _QWORD *a2)
{
  int v3; // r13d
  _QWORD *v4; // rdi
  _QWORD *i; // rbx
  int v6; // eax
  unsigned int v7; // ebx
  DWORD v9; // r12d
  HKEY v10; // rbx
  LSTATUS v11; // eax
  bool v12; // sf
  LSTATUS v13; // edi
  HKEY v14; // rcx
  HKEY v15; // rsi
  HKEY v16; // rdi
  DWORD v17; // r9d
  DWORD v18; // r9d
  DWORD v19; // r9d
  CodeAreaFilterParameter *v20; // rax
  enum FilterType v21; // r8d
  CodeAreaFilterParameter *v22; // rax
  unsigned int v23; // r9d
  int v24; // r15d
  int v25; // r15d
  unsigned int v26; // r9d
  unsigned int v27; // edx
  unsigned int v28; // r9d
  int v29; // r15d
  unsigned int v30; // r9d
  unsigned int v31; // edx
  DWORD v32; // r9d
  DWORD v33; // r9d
  DWORD v34; // r9d
  DWORD v35; // r9d
  DWORD v36; // r9d
  DWORD v37; // r9d
  char v38; // r15
  StaticFilterParameter *v39; // rax
  enum FilterType v40; // r8d
  StaticFilterParameter *v41; // rax
  __int64 v42; // rdx
  __int64 v43; // rdx
  int lpReserved; // [rsp+20h] [rbp-E0h]
  int lpReserveda; // [rsp+20h] [rbp-E0h]
  HKEY v46; // [rsp+70h] [rbp-90h] BYREF
  DWORD cchName[2]; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v48[2]; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v49; // [rsp+88h] [rbp-78h] BYREF
  HKEY v50; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v51; // [rsp+98h] [rbp-68h] BYREF
  unsigned int v52; // [rsp+9Ch] [rbp-64h] BYREF
  unsigned int v53; // [rsp+A0h] [rbp-60h] BYREF
  unsigned int v54; // [rsp+A4h] [rbp-5Ch] BYREF
  HKEY hKey; // [rsp+A8h] [rbp-58h] BYREF
  HKEY v56; // [rsp+B0h] [rbp-50h]
  CodeAreaFilterParameter *v57; // [rsp+B8h] [rbp-48h]
  StaticFilterParameter *v58; // [rsp+C0h] [rbp-40h]
  unsigned __int16 v59[264]; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int16 v60[264]; // [rsp+2E0h] [rbp+1E0h] BYREF
  WCHAR Name; // [rsp+4F0h] [rbp+3F0h] BYREF
  _BYTE v62[526]; // [rsp+4F2h] [rbp+3F2h] BYREF
  unsigned __int16 v63[264]; // [rsp+700h] [rbp+600h] BYREF
  unsigned __int16 v64[264]; // [rsp+910h] [rbp+810h] BYREF
  unsigned __int16 Src[264]; // [rsp+B20h] [rbp+A20h] BYREF
  unsigned __int16 v66[264]; // [rsp+D30h] [rbp+C30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F98h] [rbp+E98h]

  v3 = a1;
  v4 = (_QWORD *)a2[1];
  for ( i = (_QWORD *)*a2; i != v4; ++i )
  {
    if ( *i )
      (**(void (__fastcall ***)(_QWORD, __int64))*i)(*i, 1);
  }
  a2[1] = *a2;
  hKey = 0;
  v6 = RegReader::Open((RegReader *)&hKey, HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\FilterDS");
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)9,
      (unsigned int)"mincore\\textinput\\dev\\mtf\\datasources\\filterds\\lib\\filterfactory.cpp",
      (const char *)(unsigned int)v6,
      lpReserved);
    if ( hKey )
      RegCloseKey(hKey);
    return v7;
  }
  v9 = 0;
  memset_0(v62, 0, 0x206u);
  v10 = hKey;
  while ( 1 )
  {
    cchName[0] = 260;
    Name = 0;
    v11 = RegEnumKeyExW(v10, v9, &Name, cchName, 0, 0, 0, 0);
    *(_WORD *)&v62[(v11 == 0 ? 0x206 : 0) - 2] = 0;
    v12 = v11 < 0;
    if ( v11 > 0 )
      v12 = 1;
    if ( v12 )
      break;
    v46 = 0;
    v13 = RegReader::Open((RegReader *)&v46, v10, &Name);
    if ( v13 < 0 )
    {
      v43 = 18;
      goto LABEL_73;
    }
    v49 = 0;
    v13 = RegReader::QueryDWORDValue(&v46, (BYTE *)&v49, L"LanguageID", 0);
    if ( v13 < 0 )
    {
      v43 = 20;
      goto LABEL_73;
    }
    ++v9;
    if ( v49 == v3 )
    {
      v51 = 0;
      v53 = 0;
      v52 = 0;
      v13 = RegReader::QueryDWORDValue(&v46, (BYTE *)&v51, L"FilterType", 0);
      if ( v13 < 0 )
      {
        v42 = 119;
LABEL_70:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v42,
          (unsigned int)"mincore\\textinput\\dev\\mtf\\datasources\\filterds\\lib\\filterfactory.cpp",
          (const char *)(unsigned int)v13,
          lpReserveda);
        v43 = 28;
LABEL_73:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v43,
          (unsigned int)"mincore\\textinput\\dev\\mtf\\datasources\\filterds\\lib\\filterfactory.cpp",
          (const char *)(unsigned int)v13,
          lpReserveda);
        if ( v46 )
          RegCloseKey(v46);
        if ( v10 )
          RegCloseKey(v10);
        return (unsigned int)v13;
      }
      v13 = RegReader::QueryDWORDValue(&v46, (BYTE *)&v53, L"rank", 0);
      if ( v13 < 0 )
      {
        v42 = 120;
        goto LABEL_70;
      }
      RegReader::QueryDWORDValue(&v46, (BYTE *)&v52, L"LocalCheck", 0);
      v15 = 0;
      v56 = 0;
      v16 = v46;
      if ( ((v51 - 1) & 0xFFFFFFFD) != 0 )
      {
        if ( v51 == 2 )
        {
          memset_0(Src, 0, 0x208u);
          RegReader::QueryStringValue(&v46, (BYTE *)Src, L"GroupPolicyPath", v17);
          memset_0(v64, 0, 0x208u);
          RegReader::QueryStringValue(&v46, (BYTE *)v64, L"RegCharCodeAreaPath", v18);
          memset_0(v63, 0, 0x208u);
          RegReader::QueryStringValue(&v46, (BYTE *)v63, L"MDMPolicy", v19);
          v54 = 0;
          RegReader::QueryDWORDValue(&v46, (BYTE *)&v54, L"CodePage", 0x3A4u);
          v20 = (CodeAreaFilterParameter *)operator new(0x160u);
          v57 = v20;
          if ( v20 )
            v22 = CodeAreaFilterParameter::CodeAreaFilterParameter(
                    v20,
                    v49,
                    v21,
                    v53,
                    &Name,
                    Src,
                    v64,
                    v63,
                    v54,
                    v52 != 0);
          else
            v22 = 0;
          if ( v22 )
            v15 = (HKEY)v22;
          v56 = v15;
          memset_0(v59, 0, 0x208u);
          *(_QWORD *)cchName = 0;
          v24 = RegReader::Open((RegReader *)cchName, v16, L"MDMPolicyAllowBits");
          if ( v24 < 0 )
            goto LABEL_59;
          v25 = 1;
          if ( (int)RegReader::EnumValue((RegReader *)cchName, 0, v59, v23) >= 0 )
          {
            do
            {
              v48[0] = 0;
              if ( RegReader::QueryDWORDValue((HKEY *)cchName, (BYTE *)v48, v59, 0) >= 0 )
                (*(void (__fastcall **)(HKEY, unsigned __int16 *, _QWORD))(*(_QWORD *)v15 + 72LL))(v15, v59, v48[0]);
              v27 = v25++;
            }
            while ( (int)RegReader::EnumValue((RegReader *)cchName, v27, v59, v26) >= 0 );
            v10 = hKey;
          }
          memset_0(v60, 0, 0x208u);
          v50 = 0;
          v24 = RegReader::Open((RegReader *)&v50, v16, L"MDMPolicyOnlyAllowBits");
          if ( v24 < 0 )
          {
            if ( v50 )
              RegCloseKey(v50);
LABEL_59:
            if ( *(_QWORD *)cchName )
              RegCloseKey(*(HKEY *)cchName);
            if ( v15 )
              (**(void (__fastcall ***)(HKEY, __int64))v15)(v15, 1);
            if ( v16 )
              RegCloseKey(v16);
            if ( v10 )
              RegCloseKey(v10);
            return (unsigned int)v24;
          }
          v29 = 1;
          if ( (int)RegReader::EnumValue((RegReader *)&v50, 0, v60, v28) >= 0 )
          {
            do
            {
              v48[0] = 0;
              if ( RegReader::QueryDWORDValue(&v50, (BYTE *)v48, v60, 0) >= 0 )
                (*(void (__fastcall **)(HKEY, unsigned __int16 *, _QWORD))(*(_QWORD *)v15 + 80LL))(v15, v60, v48[0]);
              v31 = v29++;
            }
            while ( (int)RegReader::EnumValue((RegReader *)&v50, v31, v60, v30) >= 0 );
            v10 = hKey;
          }
          v56 = 0;
          *(_QWORD *)v48 = v15;
          std::vector<std::unique_ptr<FilterBasicParameter>>::push_back(a2, v48);
          if ( *(_QWORD *)v48 )
            (***(void (__fastcall ****)(_QWORD, __int64))v48)(*(_QWORD *)v48, 1);
          if ( v50 )
            RegCloseKey(v50);
          if ( *(_QWORD *)cchName )
            RegCloseKey(*(HKEY *)cchName);
        }
      }
      else
      {
        memset_0(v66, 0, 0x208u);
        memset_0(v59, 0, 0x208u);
        memset_0(v60, 0, 0x208u);
        memset_0(v63, 0, 0x208u);
        cchName[0] = 0;
        memset_0(v64, 0, 0x208u);
        v48[0] = 0;
        memset_0(Src, 0, 0x208u);
        RegReader::QueryStringValue(&v46, (BYTE *)v66, L"DGMLPath", v32);
        RegReader::QueryStringValue(&v46, (BYTE *)v59, L"DictionaryPath", v33);
        RegReader::QueryStringValue(&v46, (BYTE *)v60, L"RegDictionaryPath", v34);
        RegReader::QueryStringValue(&v46, (BYTE *)v63, L"GroupPolicyPath", v35);
        RegReader::QueryDWORDValue(&v46, (BYTE *)cchName, L"GroupPolicyPositive", 1u);
        RegReader::QueryStringValue(&v46, (BYTE *)v64, L"MDMPolicy", v36);
        RegReader::QueryDWORDValue(&v46, (BYTE *)v48, L"MDMPolicyPositive", 1u);
        RegReader::QueryStringValue(&v46, (BYTE *)Src, L"RegCheckPath", v37);
        v38 = 3;
        if ( v51 == 1 )
          v38 = 1;
        v39 = (StaticFilterParameter *)operator new(0x188u);
        v58 = v39;
        v40 = 0;
        if ( v39 )
        {
          LOBYTE(v40) = v38;
          v41 = StaticFilterParameter::StaticFilterParameter(
                  v39,
                  v49,
                  v40,
                  v53,
                  &Name,
                  v66,
                  v59,
                  v60,
                  v63,
                  cchName[0] != 0,
                  v64,
                  v48[0] != 0,
                  Src,
                  v52 != 0);
        }
        else
        {
          v41 = 0;
        }
        if ( v41 )
          v15 = (HKEY)v41;
        v56 = 0;
        v50 = v15;
        std::vector<std::unique_ptr<FilterBasicParameter>>::push_back(a2, &v50);
        if ( v50 )
          (**(void (__fastcall ***)(HKEY, __int64))v50)(v50, 1);
      }
      if ( v16 )
      {
        v14 = v16;
LABEL_18:
        RegCloseKey(v14);
      }
    }
    else
    {
      v14 = v46;
      if ( v46 )
        goto LABEL_18;
    }
  }
  if ( v10 )
    RegCloseKey(v10);
  return 0;
}

```

## disassembly

```asm
0x18001094c  push    rbp
0x18001094e  push    rbx
0x18001094f  push    rsi
0x180010950  push    rdi
0x180010951  push    r12
0x180010953  push    r13
0x180010955  push    r14
0x180010957  push    r15
0x180010959  lea     rbp, [rsp-0E58h]
0x180010961  sub     rsp, 0F58h
0x180010968  mov     rax, cs:__security_cookie
0x18001096f  xor     rax, rsp
0x180010972  mov     [rbp+0E90h+var_50], rax
0x180010979  mov     r14, rdx
0x18001097c  movzx   r13d, cx
0x180010980  mov     rdi, [rdx+8]
0x180010984  mov     rbx, [rdx]
0x180010987  xor     r15d, r15d
0x18001098a  lea     esi, [r15+1]
0x18001098e  jmp     short loc_1800109A9
0x180010990  mov     rcx, [rbx]
0x180010993  test    rcx, rcx
0x180010996  jz      short loc_1800109A5
0x180010998  mov     rax, [rcx]
0x18001099b  mov     edx, esi
0x18001099d  mov     rax, [rax]
0x1800109a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800109a5  add     rbx, 8
0x1800109a9  cmp     rbx, rdi
0x1800109ac  jnz     short loc_180010990
0x1800109ae  mov     rax, [r14]
0x1800109b1  mov     [r14+8], rax
0x1800109b5  mov     [rbp+0E90h+hKey], r15
0x1800109b9  lea     r8, aSoftwareMicros; "SOFTWARE\\Microsoft\\FilterDS"
0x1800109c0  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x1800109c7  lea     rcx, [rbp+0E90h+hKey]; this
0x1800109cb  call    ?Open@RegReader@@QEAAJPEAUHKEY__@@PEBG@Z; RegReader::Open(HKEY__ *,ushort const *)
0x1800109d0  mov     ebx, eax
0x1800109d2  test    eax, eax
0x1800109d4  jns     short loc_180010A08
0x1800109d6  mov     rcx, [rbp+0E98h]; this
0x1800109dd  mov     r9d, eax; char *
0x1800109e0  lea     r8, aMincoreTextinp_14; "mincore\\textinput\\dev\\mtf\\datasourc"...
0x1800109e7  mov     edx, 9; void *
0x1800109ec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800109f1  nop
0x1800109f2  mov     rcx, [rbp+0E90h+hKey]; hKey
0x1800109f6  test    rcx, rcx
0x1800109f9  jz      short loc_180010A01
0x1800109fb  call    cs:__imp_RegCloseKey
0x180010a01  mov     eax, ebx
0x180010a03  jmp     loc_18001116E
0x180010a08  mov     r12d, r15d
0x180010a0b  xor     edx, edx; Val
0x180010a0d  mov     r8d, 206h; Size
0x180010a13  lea     rcx, [rbp+0E90h+var_A9E]; void *
0x180010a1a  call    memset_0
0x180010a1f  mov     rbx, [rbp+0E90h+hKey]
0x180010a23  mov     [rsp+0F90h+cchName], 104h
0x180010a2b  mov     [rbp+0E90h+Name], r15w
0x180010a33  mov     [rsp+0F90h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180010a38  mov     [rsp+0F90h+lpcchClass], r15; lpcchClass
0x180010a3d  mov     [rsp+0F90h+lpClass], r15; lpClass
0x180010a42  mov     [rsp+0F90h+lpReserved], r15; int
0x180010a47  lea     r9, [rsp+0F90h+cchName]; lpcchName
0x180010a4c  lea     r8, [rbp+0E90h+Name]; lpName
0x180010a53  mov     edx, r12d; dwIndex
0x180010a56  mov     rcx, rbx; hKey
0x180010a59  call    cs:__imp_RegEnumKeyExW
0x180010a5f  mov     ecx, eax
0x180010a61  neg     ecx
0x180010a63  sbb     rdx, rdx
0x180010a66  not     rdx
0x180010a69  and     edx, 206h
0x180010a6f  mov     [rbp+rdx+0E90h+Name], r15w
0x180010a78  test    eax, eax
0x180010a7a  jle     short loc_180010A86
0x180010a7c  movzx   eax, ax
0x180010a7f  or      eax, 80070000h
0x180010a84  test    eax, eax
0x180010a86  js      loc_18001115E
0x180010a8c  mov     [rsp+0F90h+var_F20], r15
0x180010a91  lea     r8, [rbp+0E90h+Name]; unsigned __int16 *
0x180010a98  mov     rdx, rbx; HKEY
0x180010a9b  lea     rcx, [rsp+0F90h+var_F20]; this
0x180010aa0  call    ?Open@RegReader@@QEAAJPEAUHKEY__@@PEBG@Z; RegReader::Open(HKEY__ *,ushort const *)
0x180010aa5  mov     edi, eax
0x180010aa7  test    eax, eax
0x180010aa9  js      loc_18001111F
0x180010aaf  mov     [rbp+0E90h+var_F08], r15d
0x180010ab3  xor     r9d, r9d; unsigned int
0x180010ab6  lea     r8, aLanguageid; "LanguageID"
0x180010abd  lea     rdx, [rbp+0E90h+var_F08]; unsigned int *
0x180010ac1  lea     rcx, [rsp+0F90h+var_F20]; this
0x180010ac6  call    ?QueryDWORDValue@RegReader@@QEAAJAEAKPEBGK@Z; RegReader::QueryDWORDValue(ulong &,ushort const *,ulong)
0x180010acb  mov     edi, eax
0x180010acd  test    eax, eax
0x180010acf  js      loc_180011118
0x180010ad5  add     r12d, esi
0x180010ad8  cmp     [rbp+0E90h+var_F08], r13d
0x180010adc  jz      short loc_180010AF7
0x180010ade  mov     rcx, [rsp+0F90h+var_F20]; hKey
0x180010ae3  test    rcx, rcx
0x180010ae6  jz      loc_180010A23
0x180010aec  call    cs:__imp_RegCloseKey
0x180010af2  jmp     loc_180010A23
0x180010af7  mov     [rbp+0E90h+var_EF8], r15d
0x180010afb  mov     [rbp+0E90h+var_EF0], r15d
0x180010aff  mov     [rbp+0E90h+var_EF4], r15d
0x180010b03  xor     r9d, r9d; unsigned int
0x180010b06  lea     r8, aFiltertype; "FilterType"
0x180010b0d  lea     rdx, [rbp+0E90h+var_EF8]; unsigned int *
0x180010b11  lea     rcx, [rsp+0F90h+var_F20]; this
0x180010b16  call    ?QueryDWORDValue@RegReader@@QEAAJAEAKPEBGK@Z; RegReader::QueryDWORDValue(ulong &,ushort const *,ulong)
0x180010b1b  mov     edi, eax
0x180010b1d  test    eax, eax
0x180010b1f  js      loc_1800110F6
0x180010b25  xor     r9d, r9d; unsigned int
0x180010b28  lea     r8, aRank; "rank"
0x180010b2f  lea     rdx, [rbp+0E90h+var_EF0]; unsigned int *
0x180010b33  lea     rcx, [rsp+0F90h+var_F20]; this
0x180010b38  call    ?QueryDWORDValue@RegReader@@QEAAJAEAKPEBGK@Z; RegReader::QueryDWORDValue(ulong &,ushort const *,ulong)
0x180010b3d  mov     edi, eax
0x180010b3f  test    eax, eax
0x180010b41  js      loc_1800110EF
0x180010b47  xor     r9d, r9d; unsigned int
0x180010b4a  lea     r8, aLocalcheck; "LocalCheck"
0x180010b51  lea     rdx, [rbp+0E90h+var_EF4]; unsigned int *
0x180010b55  lea     rcx, [rsp+0F90h+var_F20]; this
0x180010b5a  call    ?QueryDWORDValue@RegReader@@QEAAJAEAKPEBGK@Z; RegReader::QueryDWORDValue(ulong &,ushort const *,ulong)
0x180010b5f  mov     rsi, r15
0x180010b62  mov     [rbp+0E90h+var_EE0], r15
0x180010b66  mov     ecx, [rbp+0E90h+var_EF8]
0x180010b69  lea     eax, [rcx-1]
0x180010b6c  mov     rdi, [rsp+0F90h+var_F20]
0x180010b71  test    eax, 0FFFFFFFDh
0x180010b76  jz      loc_180010E56
0x180010b7c  cmp     ecx, 2
0x180010b7f  jnz     loc_180010E40
0x180010b85  xor     edx, edx; Val
0x180010b87  mov     r8d, 208h; Size
0x180010b8d  lea     rcx, [rbp+0E90h+Src]; void *
0x180010b94  call    memset_0
0x180010b99  lea     r8, aGrouppolicypat; "GroupPolicyPath"
0x180010ba0  lea     rdx, [rbp+0E90h+Src]; unsigned __int16 *
0x180010ba7  lea     rcx, [rsp+0F90h+var_F20]; this
0x180010bac  call    ?QueryStringValue@RegReader@@QEAAJPEAGPEBGK@Z; RegReader::QueryStringValue(ushort *,ushort const *,ulong)
0x180010bb1  xor     edx, edx; Val
0x180010bb3  mov     r8d, 208h; Size
0x180010bb9  lea     rcx, [rbp+0E90h+var_680]; void *
0x180010bc0  call    memset_0
0x180010bc5  lea     r8, aRegcharcodeare; "RegCharCodeAreaPath"
0x180010bcc  lea     rdx, [rbp+0E90h+var_680]; unsigned __int16 *
0x180010bd3  lea     rcx, [rsp+0F90h+var_F20]; this
0x180010bd8  call    ?QueryStringValue@RegReader@@QEAAJPEAGPEBGK@Z; RegReader::QueryStringValue(ushort *,ushort const *,ulong)
0x180010bdd  xor     edx, edx; Val
0x180010bdf  mov     r8d, 208h; Size
0x180010be5  lea     rcx, [rbp+0E90h+var_890]; void *
0x180010bec  call    memset_0
0x180010bf1  lea     r8, aMdmpolicy; "MDMPolicy"
0x180010bf8  lea     rdx, [rbp+0E90h+var_890]; unsigned __int16 *
0x180010bff  lea     rcx, [rsp+0F90h+var_F20]; this
0x180010c04  call    ?QueryStringValue@RegReader@@QEAAJPEAGPEBGK@Z; RegReader::QueryStringValue(ushort *,ushort const *,ulong)
0x180010c09  mov     [rbp+0E90h+var_EEC], r15d
0x180010c0d  mov     r9d, 3A4h; unsigned int
0x180010c13  lea     r8, aCodepage; "CodePage"
0x180010c1a  lea     rdx, [rbp+0E90h+var_EEC]; unsigned int *
0x180010c1e  lea     rcx, [rsp+0F90h+var_F20]; this
0x180010c23  call    ?QueryDWORDValue@RegReader@@QEAAJAEAKPEBGK@Z; RegReader::QueryDWORDValue(ulong &,ushort const *,ulong)
0x180010c28  mov     ecx, 160h; Size
0x180010c2d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180010c32  mov     [rbp+0E90h+var_ED8], rax
0x180010c36  test    rax, rax
0x180010c39  jz      short loc_180010C8F
0x180010c3b  cmp     [rbp+0E90h+var_EF4], r15d
0x180010c3f  setnz   cl
0x180010c42  mov     [rsp+0F90h+var_F48], cl; bool
0x180010c46  mov     ecx, [rbp+0E90h+var_EEC]
0x180010c49  mov     dword ptr [rsp+0F90h+var_F50], ecx; unsigned int
0x180010c4d  lea     rcx, [rbp+0E90h+var_890]
0x180010c54  mov     [rsp+0F90h+lpftLastWriteTime], rcx; unsigned __int16 *
0x180010c59  lea     rcx, [rbp+0E90h+var_680]
0x180010c60  mov     [rsp+0F90h+lpcchClass], rcx; unsigned __int16 *
0x180010c65  lea     rcx, [rbp+0E90h+Src]
0x180010c6c  mov     [rsp+0F90h+lpClass], rcx; Src
0x180010c71  lea     rcx, [rbp+0E90h+Name]
0x180010c78  mov     [rsp+0F90h+lpReserved], rcx; unsigned __int16 *
0x180010c7d  mov     r9b, byte ptr [rbp+0E90h+var_EF0]; unsigned __int8
0x180010c81  movzx   edx, word ptr [rbp+0E90h+var_F08]; unsigned __int16
0x180010c85  mov     rcx, rax; this
0x180010c88  call    ??0CodeAreaFilterParameter@@QEAA@GW4FilterType@@EPEBG111K_N@Z; CodeAreaFilterParameter::CodeAreaFilterParameter(ushort,FilterType,uchar,ushort const *,ushort const *,ushort const *,ushort const *,ulong,bool)
0x180010c8d  jmp     short loc_180010C92
0x180010c8f  mov     rax, r15
0x180010c92  test    rax, rax
0x180010c95  cmovnz  rsi, rax
0x180010c99  mov     [rbp+0E90h+var_EE0], rsi
0x180010c9d  xor     edx, edx; Val
0x180010c9f  mov     r8d, 208h; Size
0x180010ca5  lea     rcx, [rbp+0E90h+var_EC0]; void *
0x180010ca9  call    memset_0
0x180010cae  mov     qword ptr [rsp+0F90h+cchName], r15
0x180010cb3  lea     r8, aMdmpolicyallow; "MDMPolicyAllowBits"
0x180010cba  mov     rdx, rdi; HKEY
0x180010cbd  lea     rcx, [rsp+0F90h+cchName]; this
0x180010cc2  call    ?Open@RegReader@@QEAAJPEAUHKEY__@@PEBG@Z; RegReader::Open(HKEY__ *,ushort const *)
0x180010cc7  mov     r15d, eax
0x180010cca  test    eax, eax
0x180010ccc  js      loc_1800110A3
0x180010cd2  mov     r15d, 1
0x180010cd8  lea     r8, [rbp+0E90h+var_EC0]; unsigned __int16 *
0x180010cdc  xor     edx, edx; unsigned int
0x180010cde  lea     rcx, [rsp+0F90h+cchName]; this
0x180010ce3  call    ?EnumValue@RegReader@@QEAAJKPEAGK@Z; RegReader::EnumValue(ulong,ushort *,ulong)
0x180010ce8  test    eax, eax
0x180010cea  js      short loc_180010D3F
0x180010cec  mov     [rbp+0E90h+var_F10], 0
0x180010cf3  xor     r9d, r9d; unsigned int
0x180010cf6  lea     r8, [rbp+0E90h+var_EC0]; unsigned __int16 *
0x180010cfa  lea     rdx, [rbp+0E90h+var_F10]; unsigned int *
0x180010cfe  lea     rcx, [rsp+0F90h+cchName]; this
0x180010d03  call    ?QueryDWORDValue@RegReader@@QEAAJAEAKPEBGK@Z; RegReader::QueryDWORDValue(ulong &,ushort const *,ulong)
0x180010d08  test    eax, eax
0x180010d0a  js      short loc_180010D23
0x180010d0c  mov     rax, [rsi]
0x180010d0f  mov     r8d, [rbp+0E90h+var_F10]
0x180010d13  lea     rdx, [rbp+0E90h+var_EC0]
0x180010d17  mov     rcx, rsi
0x180010d1a  mov     rax, [rax+48h]
0x180010d1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010d23  mov     edx, r15d; unsigned int
0x180010d26  inc     r15d
0x180010d29  lea     r8, [rbp+0E90h+var_EC0]; unsigned __int16 *
0x180010d2d  lea     rcx, [rsp+0F90h+cchName]; this
0x180010d32  call    ?EnumValue@RegReader@@QEAAJKPEAGK@Z; RegReader::EnumValue(ulong,ushort *,ulong)
0x180010d37  test    eax, eax
0x180010d39  jns     short loc_180010CEC
0x180010d3b  mov     rbx, [rbp+0E90h+hKey]
0x180010d3f  xor     edx, edx; Val
0x180010d41  mov     r8d, 208h; Size
0x180010d47  lea     rcx, [rbp+0E90h+var_CB0]; void *
0x180010d4e  call    memset_0
0x180010d53  mov     [rbp+0E90h+var_F00], 0
0x180010d5b  lea     r8, aMdmpolicyonlya; "MDMPolicyOnlyAllowBits"
0x180010d62  mov     rdx, rdi; HKEY
0x180010d65  lea     rcx, [rbp+0E90h+var_F00]; this
0x180010d69  call    ?Open@RegReader@@QEAAJPEAUHKEY__@@PEBG@Z; RegReader::Open(HKEY__ *,ushort const *)
0x180010d6e  mov     r15d, eax
0x180010d71  test    eax, eax
0x180010d73  js      loc_180011093
0x180010d79  mov     r15d, 1
0x180010d7f  lea     r8, [rbp+0E90h+var_CB0]; unsigned __int16 *
0x180010d86  xor     edx, edx; unsigned int
0x180010d88  lea     rcx, [rbp+0E90h+var_F00]; this
0x180010d8c  call    ?EnumValue@RegReader@@QEAAJKPEAGK@Z; RegReader::EnumValue(ulong,ushort *,ulong)
0x180010d91  test    eax, eax
0x180010d93  js      short loc_180010DEF
0x180010d95  mov     [rbp+0E90h+var_F10], 0
0x180010d9c  xor     r9d, r9d; unsigned int
0x180010d9f  lea     r8, [rbp+0E90h+var_CB0]; unsigned __int16 *
0x180010da6  lea     rdx, [rbp+0E90h+var_F10]; unsigned int *
0x180010daa  lea     rcx, [rbp+0E90h+var_F00]; this
0x180010dae  call    ?QueryDWORDValue@RegReader@@QEAAJAEAKPEBGK@Z; RegReader::QueryDWORDValue(ulong &,ushort const *,ulong)
0x180010db3  test    eax, eax
0x180010db5  js      short loc_180010DD1
0x180010db7  mov     rax, [rsi]
0x180010dba  mov     r8d, [rbp+0E90h+var_F10]
0x180010dbe  lea     rdx, [rbp+0E90h+var_CB0]
0x180010dc5  mov     rcx, rsi
0x180010dc8  mov     rax, [rax+50h]
0x180010dcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010dd1  mov     edx, r15d; unsigned int
0x180010dd4  inc     r15d
0x180010dd7  lea     r8, [rbp+0E90h+var_CB0]; unsigned __int16 *
0x180010dde  lea     rcx, [rbp+0E90h+var_F00]; this
0x180010de2  call    ?EnumValue@RegReader@@QEAAJKPEAGK@Z; RegReader::EnumValue(ulong,ushort *,ulong)
0x180010de7  test    eax, eax
0x180010de9  jns     short loc_180010D95
0x180010deb  mov     rbx, [rbp+0E90h+hKey]
0x180010def  xor     r15d, r15d
0x180010df2  mov     [rbp+0E90h+var_EE0], r15
0x180010df6  mov     qword ptr [rbp+0E90h+var_F10], rsi
0x180010dfa  lea     rdx, [rbp+0E90h+var_F10]
0x180010dfe  mov     rcx, r14
0x180010e01  call    ?push_back@?$vector@V?$unique_ptr@VFilterBasicParameter@@U?$default_delete@VFilterBasicParameter@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterBasicParameter@@U?$default_delete@VFilterBasicParameter@@@std@@@std@@@2@@std@@QEAAX$$QEAV?$unique_ptr@VFilterBasicParameter@@U?$default_delete@VFilterBasicParameter@@@std@@@2@@Z; std::vector<std::unique_ptr<FilterBasicParameter>>::push_back(std::unique_ptr<FilterBasicParameter> &&)
0x180010e06  nop
0x180010e07  mov     rcx, qword ptr [rbp+0E90h+var_F10]
0x180010e0b  test    rcx, rcx
0x180010e0e  jz      short loc_180010E20
0x180010e10  mov     rax, [rcx]
0x180010e13  lea     edx, [r15+1]
0x180010e17  mov     rax, [rax]
0x180010e1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010e1f  nop
0x180010e20  mov     rcx, [rbp+0E90h+var_F00]; hKey
0x180010e24  test    rcx, rcx
0x180010e27  jz      short loc_180010E30
0x180010e29  call    cs:__imp_RegCloseKey
0x180010e2f  nop
0x180010e30  mov     rcx, qword ptr [rsp+0F90h+cchName]; hKey
0x180010e35  test    rcx, rcx
  ... truncated ...
```
