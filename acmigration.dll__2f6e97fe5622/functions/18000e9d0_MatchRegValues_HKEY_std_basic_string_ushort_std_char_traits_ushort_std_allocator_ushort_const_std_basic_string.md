# MatchRegValues(HKEY__ *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,__int64,bool,AppCompatUtility::_RegexCondition *,unsigned __int64,__int64 *,int *)

- ea: `0x18000e9d0`
- end: `0x18000ef86`
- name: `?MatchRegValues@@YA_NPEAUHKEY__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1111_J_NPEAU_RegexCondition@AppCompatUtility@@_KPEA_JPEAH@Z`
- size: `1462`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, LPCWSTR lpSubKey@<rdx>, __int64, __int64, __int64, char, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000e5a4`

## callees

- `0x180001cf0`
- `0x180002874`
- `0x18000b5fc`
- `0x18000b720`
- `0x18000e0e4`
- `0x18000e428`
- `0x18000e9d0`
- `0x18003ffb4`
- `0x180040148`
- `0x1800424b0`
- `0x180042764`
- `0x1800543c0`
- `0x180054d54`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18000eb45`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18000eb45`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000ef5a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000ef5a`
- `ADVAPI32!RegCloseKey` at `0x18000ef47`
- `ADVAPI32!RegCloseKey` at `0x18000ef47`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18000eb17`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18000eb17`
- `ADVAPI32!RegEnumValueW` at `0x18000ebb5`
- `ADVAPI32!RegEnumValueW` at `0x18000ebb5`
- `ADVAPI32!RegOpenKeyExW` at `0x18000ea9d`
- `ADVAPI32!RegOpenKeyExW` at `0x18000ea9d`

## string_xrefs

- `0x18000eab1`: `RegOpenKeyEx failed, %d, %ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall MatchRegValues(
        HKEY hKey,
        LPCWSTR lpSubKey,
        wchar_t *a3,
        __int64 a4,
        wchar_t *a5,
        __int64 a6,
        __int64 a7,
        char a8,
        __int64 a9,
        __int64 a10,
        _QWORD *a11,
        _DWORD *a12)
{
  BYTE *v15; // rsi
  char v16; // r15
  const WCHAR *v17; // rdx
  LSTATUS v18; // eax
  const char *v19; // r9
  __int64 v20; // r8
  DWORD i; // edx
  LSTATUS v22; // r15d
  unsigned __int64 v23; // r14
  const wchar_t *v24; // rcx
  size_t v25; // r8
  __int64 v26; // rcx
  LPCWSTR v27; // rax
  unsigned __int64 v28; // r14
  wchar_t *v29; // rcx
  size_t v30; // r8
  wchar_t *v31; // r14
  wchar_t *v32; // rax
  __int64 v33; // rcx
  int v34; // eax
  BYTE *v35; // rcx
  __int64 v36; // rax
  BYTE *v37; // rax
  __int64 v38; // r14
  __int64 v39; // r8
  __int64 v40; // r8
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  PHKEY phkResulta; // [rsp+20h] [rbp-E0h]
  DWORD cbMaxValueLen; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD Type; // [rsp+68h] [rbp-98h] BYREF
  DWORD cbData; // [rsp+6Ch] [rbp-94h] BYREF
  DWORD cchValueName; // [rsp+70h] [rbp-90h] BYREF
  HKEY hKeya; // [rsp+78h] [rbp-88h] BYREF
  DWORD v49; // [rsp+80h] [rbp-80h]
  wchar_t *S1; // [rsp+88h] [rbp-78h]
  _QWORD *v51; // [rsp+90h] [rbp-70h]
  __int64 v52; // [rsp+98h] [rbp-68h]
  wchar_t *v53; // [rsp+A0h] [rbp-60h]
  __int64 v54; // [rsp+A8h] [rbp-58h]
  _BYTE *v55; // [rsp+B0h] [rbp-50h]
  _BYTE v56[32]; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v57; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v58; // [rsp+F0h] [rbp-10h]
  WCHAR ValueName[264]; // [rsp+100h] [rbp+0h] BYREF

  v54 = -2;
  S1 = a3;
  v53 = a5;
  v52 = a6;
  v51 = a11;
  memset_0(ValueName, 0, 0x20Au);
  cchValueName = 261;
  v15 = 0;
  cbMaxValueLen = 520;
  cbData = 0;
  Type = 0;
  v16 = 0;
  hKeya = 0;
  if ( *((_QWORD *)lpSubKey + 3) <= 7u )
    v17 = lpSubKey;
  else
    v17 = *(const WCHAR **)lpSubKey;
  v18 = RegOpenKeyExW(hKey, v17, 0, 0x20019u, &hKeya);
  if ( v18 )
  {
    if ( *((_QWORD *)lpSubKey + 3) > 7u )
      lpSubKey = *(LPCWSTR *)lpSubKey;
    v19 = "RegOpenKeyEx failed, %d, %ws";
    v20 = 222;
LABEL_8:
    LODWORD(phkResult) = v18;
    AslLogCallPrintf(1, "MatchRegValues", v20, v19, phkResult, lpSubKey);
    goto LABEL_76;
  }
  v18 = RegQueryInfoKeyW(hKeya, 0, 0, 0, 0, 0, 0, 0, 0, &cbMaxValueLen, 0, 0);
  if ( v18 )
  {
    if ( *((_QWORD *)lpSubKey + 3) > 7u )
      lpSubKey = *(LPCWSTR *)lpSubKey;
    v19 = "RegQueryInfoKeyW failed, %d, %ws";
    v20 = 240;
    goto LABEL_8;
  }
  v15 = (BYTE *)calloc(cbMaxValueLen, 1u);
  if ( !v15 )
  {
    AslLogCallPrintf(1, "MatchRegValues", 247, "Out of memory.");
    goto LABEL_76;
  }
  v49 = 0;
  for ( i = 0; ; i = v49 )
  {
    cbData = cbMaxValueLen;
    cchValueName = 261;
    v22 = RegEnumValueW(hKeya, i, ValueName, &cchValueName, 0, &Type, v15, &cbData);
    if ( v22 )
      goto LABEL_41;
    v23 = *(_QWORD *)(a4 + 16);
    if ( *(_QWORD *)(a4 + 24) <= 7u )
      v24 = (const wchar_t *)a4;
    else
      v24 = *(const wchar_t **)a4;
    v25 = *(_QWORD *)(a4 + 16);
    if ( v23 > 9 )
      v25 = 9;
    if ( wmemcmp(v24, L"(Default)", v25) || v23 != 9 || ValueName[0] )
    {
      v26 = *(_QWORD *)(a4 + 24) <= 7u ? a4 : *(_QWORD *)a4;
      if ( !(unsigned int)AslStringPatternMatchExW(v26, ValueName) )
        goto LABEL_72;
    }
    ++*v51;
    if ( *((_QWORD *)lpSubKey + 3) <= 7u )
      v27 = lpSubKey;
    else
      v27 = *(LPCWSTR *)lpSubKey;
    AslLogCallPrintf(3, "MatchRegValues", 277, "Found a matched reg value name: %ws under %ws", ValueName, v27);
    v28 = *((_QWORD *)S1 + 2);
    if ( *((_QWORD *)S1 + 3) <= 7u )
      v29 = S1;
    else
      v29 = *(wchar_t **)S1;
    v30 = *((_QWORD *)S1 + 2);
    if ( v28 > 9 )
      v30 = 9;
    if ( !wmemcmp(v29, L"count_gte", v30) && v28 == 9 )
      break;
    v31 = v53;
    if ( !(unsigned __int8)AppCompatUtility::IsRegValueTypeMatch(v53) )
    {
      if ( *((_QWORD *)v31 + 3) <= 7u )
        v32 = v31;
      else
        v32 = *(wchar_t **)v31;
      LODWORD(phkResulta) = Type;
      AslLogCallPrintf(
        3,
        "MatchRegValues",
        294,
        "Reg value type not match: %d, %ws; for %ws",
        phkResulta,
        v32,
        ValueName);
      goto LABEL_72;
    }
    switch ( Type )
    {
      case 4u:
        v33 = *(unsigned int *)v15;
        goto LABEL_54;
      case 0xBu:
        v33 = *(_QWORD *)v15;
LABEL_54:
        v34 = AppCompatUtility::CompareInt(v33, a7, S1);
        *a12 = v34;
        if ( v34 == 1 )
          goto LABEL_41;
        goto LABEL_72;
      case 7u:
        if ( cbMaxValueLen < 4 )
        {
          AslLogCallPrintf(1, "MatchRegValues", 325, "Unexpected value data size.");
          goto LABEL_74;
        }
        *(_WORD *)&v15[2 * (cbMaxValueLen >> 1) - 2] = 0;
        *(_WORD *)&v15[2 * (cbMaxValueLen >> 1) - 4] = 0;
        v35 = v15;
        if ( *(_WORD *)v15 )
        {
          do
          {
            v36 = -1;
            do
              ++v36;
            while ( *(_WORD *)&v35[2 * v36] );
            v37 = &v35[2 * v36];
            *(_WORD *)v37 = 59;
            v35 = v37 + 2;
          }
          while ( *((_WORD *)v37 + 1) );
        }
        AslLogCallPrintf(3, "MatchRegValues", 332, "Multi sz value is: %ws", v15);
        break;
    }
    if ( a8 )
    {
      v55 = v56;
      v38 = std::wstring::wstring(v56, v52);
      v57 = 0;
      v58 = 0u;
      v39 = -1;
      do
        ++v39;
      while ( *(_WORD *)&v15[2 * v39] );
      std::wstring::_Construct<1,unsigned short const *>(&v57, v15, v39);
      if ( (unsigned int)AppCompatUtility::MatchRegexValue(a12, &v57, v38, a9, a10) )
      {
        AslLogCallPrintf(1, "MatchRegValues", 344, "Failed to do regex matching. [0x%x]", 0);
        v16 = 0;
        goto LABEL_76;
      }
    }
    else
    {
      v57 = 0;
      v58 = 0;
      v40 = -1;
      do
        ++v40;
      while ( *(_WORD *)&v15[2 * v40] );
      std::wstring::_Construct<1,unsigned short const *>(&v57, v15, v40);
      *a12 = AppCompatUtility::CompareStr(&v57, v52, S1);
      std::wstring::~wstring(&v57);
    }
    if ( *a12 == 1 )
      goto LABEL_41;
LABEL_72:
    ++v49;
  }
  if ( *v51 < a7 )
    goto LABEL_72;
  *a12 = 1;
LABEL_41:
  if ( v22 != 259 && v22 )
  {
    AslLogCallPrintf(1, "MatchRegValues", 362, "RegEnumKeyEx failed, %d", v22);
LABEL_74:
    v16 = 0;
    goto LABEL_76;
  }
  v16 = 1;
LABEL_76:
  if ( hKeya )
  {
    RegCloseKey(hKeya);
    hKeya = 0;
  }
  if ( v15 )
    free(v15);
  return v16;
}

```

## disassembly

```asm
0x18000e9d0  push    rbp
0x18000e9d2  push    rbx
0x18000e9d3  push    rsi
0x18000e9d4  push    rdi
0x18000e9d5  push    r12
0x18000e9d7  push    r13
0x18000e9d9  push    r14
0x18000e9db  push    r15
0x18000e9dd  lea     rbp, [rsp-228h]
0x18000e9e5  sub     rsp, 328h
0x18000e9ec  mov     [rbp+260h+var_2B8], 0FFFFFFFFFFFFFFFEh
0x18000e9f4  mov     rax, cs:__security_cookie
0x18000e9fb  xor     rax, rsp
0x18000e9fe  mov     [rbp+260h+var_50], rax
0x18000ea05  mov     r12, r9
0x18000ea08  mov     [rbp+260h+S1], r8
0x18000ea0c  mov     rdi, rdx
0x18000ea0f  mov     rbx, rcx
0x18000ea12  mov     rax, [rbp+260h+arg_20]
0x18000ea19  mov     [rbp+260h+var_2C0], rax
0x18000ea1d  mov     rax, [rbp+260h+arg_28]
0x18000ea24  mov     [rbp+260h+var_2C8], rax
0x18000ea28  mov     rcx, [rbp+260h+arg_50]
0x18000ea2f  mov     [rbp+260h+var_2D0], rcx
0x18000ea33  mov     r13, [rbp+260h+arg_58]
0x18000ea3a  xor     edx, edx; Val
0x18000ea3c  mov     r8d, 20Ah; Size
0x18000ea42  lea     rcx, [rbp+260h+ValueName]; void *
0x18000ea46  call    memset_0
0x18000ea4b  mov     [rsp+360h+cchValueName], 105h
0x18000ea53  xor     r14d, r14d
0x18000ea56  mov     esi, r14d
0x18000ea59  mov     [rsp+360h+cbMaxValueLen], 208h
0x18000ea61  mov     [rsp+360h+cbData], r14d
0x18000ea66  mov     [rsp+360h+Type], r14d
0x18000ea6b  mov     r15b, r14b
0x18000ea6e  mov     [rsp+360h+var_300], r14b
0x18000ea73  mov     [rsp+360h+hKey], r14
0x18000ea78  cmp     qword ptr [rdi+18h], 7
0x18000ea7d  jbe     short loc_18000EA84
0x18000ea7f  mov     rdx, [rdi]
0x18000ea82  jmp     short loc_18000EA87
0x18000ea84  mov     rdx, rdi; lpSubKey
0x18000ea87  lea     rax, [rsp+360h+hKey]
0x18000ea8c  mov     [rsp+360h+phkResult], rax; phkResult
0x18000ea91  mov     r9d, 20019h; samDesired
0x18000ea97  xor     r8d, r8d; ulOptions
0x18000ea9a  mov     rcx, rbx; hKey
0x18000ea9d  call    cs:__imp_RegOpenKeyExW
0x18000eaa3  test    eax, eax
0x18000eaa5  jz      short loc_18000EADD
0x18000eaa7  cmp     qword ptr [rdi+18h], 7
0x18000eaac  jbe     short loc_18000EAB1
0x18000eaae  mov     rdi, [rdi]
0x18000eab1  lea     r9, aRegopenkeyexFa; "RegOpenKeyEx failed, %d, %ws"
0x18000eab8  mov     r8d, 0DEh
0x18000eabe  mov     [rsp+360h+lpcbMaxSubKeyLen], rdi
0x18000eac3  mov     dword ptr [rsp+360h+phkResult], eax
0x18000eac7  lea     rdx, aMatchregvalues_0; "MatchRegValues"
0x18000eace  mov     ecx, 1
0x18000ead3  call    AslLogCallPrintf
0x18000ead8  jmp     loc_18000EF3B
0x18000eadd  mov     [rsp+360h+lpftLastWriteTime], r14; lpftLastWriteTime
0x18000eae2  mov     [rsp+360h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x18000eae7  lea     rax, [rsp+360h+cbMaxValueLen]
0x18000eaec  mov     [rsp+360h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x18000eaf1  mov     [rsp+360h+lpcbMaxValueNameLen], r14; lpcbMaxValueNameLen
0x18000eaf6  mov     [rsp+360h+lpcValues], r14; lpcValues
0x18000eafb  mov     [rsp+360h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x18000eb00  mov     [rsp+360h+lpcbMaxSubKeyLen], r14; lpcbMaxSubKeyLen
0x18000eb05  mov     [rsp+360h+phkResult], r14; lpcSubKeys
0x18000eb0a  xor     r9d, r9d; lpReserved
0x18000eb0d  xor     r8d, r8d; lpcchClass
0x18000eb10  xor     edx, edx; lpClass
0x18000eb12  mov     rcx, [rsp+360h+hKey]; hKey
0x18000eb17  call    cs:__imp_RegQueryInfoKeyW
0x18000eb1d  test    eax, eax
0x18000eb1f  jz      short loc_18000EB3A
0x18000eb21  cmp     qword ptr [rdi+18h], 7
0x18000eb26  jbe     short loc_18000EB2B
0x18000eb28  mov     rdi, [rdi]
0x18000eb2b  lea     r9, aRegqueryinfoke; "RegQueryInfoKeyW failed, %d, %ws"
0x18000eb32  mov     r8d, 0F0h
0x18000eb38  jmp     short loc_18000EABE
0x18000eb3a  mov     ecx, [rsp+360h+cbMaxValueLen]; Count
0x18000eb3e  mov     ebx, 1
0x18000eb43  mov     edx, ebx; Size
0x18000eb45  call    cs:__imp_calloc
0x18000eb4b  mov     rsi, rax
0x18000eb4e  test    rax, rax
0x18000eb51  jnz     short loc_18000EB73
0x18000eb53  lea     r9, aOutOfMemory_0; "Out of memory."
0x18000eb5a  mov     r8d, 0F7h
0x18000eb60  lea     rdx, aMatchregvalues_0; "MatchRegValues"
0x18000eb67  mov     ecx, ebx
0x18000eb69  call    AslLogCallPrintf
0x18000eb6e  jmp     loc_18000EF3B
0x18000eb73  mov     [rbp+260h+var_2E0], r14d
0x18000eb77  xor     edx, edx; dwIndex
0x18000eb79  mov     eax, [rsp+360h+cbMaxValueLen]
0x18000eb7d  mov     [rsp+360h+cbData], eax
0x18000eb81  lea     rax, [rsp+360h+cbData]
0x18000eb86  mov     [rsp+360h+lpcValues], rax; lpcbData
0x18000eb8b  mov     [rsp+360h+lpcbMaxClassLen], rsi; lpData
0x18000eb90  lea     rax, [rsp+360h+Type]
0x18000eb95  mov     [rsp+360h+lpcbMaxSubKeyLen], rax; lpType
0x18000eb9a  mov     [rsp+360h+phkResult], r14; lpReserved
0x18000eb9f  mov     [rsp+360h+cchValueName], 105h
0x18000eba7  lea     r9, [rsp+360h+cchValueName]; lpcchValueName
0x18000ebac  lea     r8, [rbp+260h+ValueName]; lpValueName
0x18000ebb0  mov     rcx, [rsp+360h+hKey]; hKey
0x18000ebb5  call    cs:__imp_RegEnumValueW
0x18000ebbb  test    eax, eax
0x18000ebbd  mov     r15d, eax
0x18000ebc0  jnz     loc_18000ECC8
0x18000ebc6  mov     eax, 9
0x18000ebcb  mov     r14, [r12+10h]
0x18000ebd0  cmp     qword ptr [r12+18h], 7
0x18000ebd6  jbe     short loc_18000EBDE
0x18000ebd8  mov     rcx, [r12]
0x18000ebdc  jmp     short loc_18000EBE1
0x18000ebde  mov     rcx, r12; S1
0x18000ebe1  mov     r8, r14
0x18000ebe4  cmp     r14, rax
0x18000ebe7  cmova   r8, rax; N
0x18000ebeb  lea     rdx, aDefault_0; "(Default)"
0x18000ebf2  call    wmemcmp
0x18000ebf7  test    eax, eax
0x18000ebf9  jnz     short loc_18000EC0D
0x18000ebfb  cmp     r14, 9
0x18000ebff  jnz     short loc_18000EC0D
0x18000ec01  xor     r14d, r14d
0x18000ec04  cmp     r14w, [rbp+260h+ValueName]
0x18000ec09  jz      short loc_18000EC32
0x18000ec0b  jmp     short loc_18000EC10
0x18000ec0d  xor     r14d, r14d
0x18000ec10  cmp     qword ptr [r12+18h], 7
0x18000ec16  jbe     short loc_18000EC1E
0x18000ec18  mov     rcx, [r12]
0x18000ec1c  jmp     short loc_18000EC21
0x18000ec1e  mov     rcx, r12
0x18000ec21  lea     rdx, [rbp+260h+ValueName]
0x18000ec25  call    AslStringPatternMatchExW
0x18000ec2a  test    eax, eax
0x18000ec2c  jz      loc_18000EF07
0x18000ec32  mov     rax, [rbp+260h+var_2D0]
0x18000ec36  add     [rax], rbx
0x18000ec39  cmp     qword ptr [rdi+18h], 7
0x18000ec3e  jbe     short loc_18000EC45
0x18000ec40  mov     rax, [rdi]
0x18000ec43  jmp     short loc_18000EC48
0x18000ec45  mov     rax, rdi
0x18000ec48  mov     [rsp+360h+lpcbMaxSubKeyLen], rax
0x18000ec4d  lea     rax, [rbp+260h+ValueName]
0x18000ec51  mov     [rsp+360h+phkResult], rax
0x18000ec56  lea     r9, aFoundAMatchedR; "Found a matched reg value name: %ws und"...
0x18000ec5d  mov     r8d, 115h
0x18000ec63  lea     rdx, aMatchregvalues_0; "MatchRegValues"
0x18000ec6a  mov     ecx, 3
0x18000ec6f  call    AslLogCallPrintf
0x18000ec74  mov     rax, [rbp+260h+S1]
0x18000ec78  mov     r14, [rax+10h]
0x18000ec7c  cmp     qword ptr [rax+18h], 7
0x18000ec81  jbe     short loc_18000EC88
0x18000ec83  mov     rcx, [rax]
0x18000ec86  jmp     short loc_18000EC8B
0x18000ec88  mov     rcx, rax; S1
0x18000ec8b  mov     r8, r14
0x18000ec8e  mov     eax, 9
0x18000ec93  cmp     r14, rax
0x18000ec96  cmova   r8, rax; N
0x18000ec9a  lea     rdx, aCountGte; "count_gte"
0x18000eca1  call    wmemcmp
0x18000eca6  test    eax, eax
0x18000eca8  jnz     short loc_18000ED03
0x18000ecaa  cmp     r14, 9
0x18000ecae  jnz     short loc_18000ED03
0x18000ecb0  mov     rax, [rbp+260h+arg_30]
0x18000ecb7  mov     rcx, [rbp+260h+var_2D0]
0x18000ecbb  cmp     [rcx], rax
0x18000ecbe  jl      loc_18000ED5A
0x18000ecc4  mov     [r13+0], ebx
0x18000ecc8  cmp     r15d, 103h
0x18000eccf  jz      loc_18000EF38
0x18000ecd5  test    r15d, r15d
0x18000ecd8  jz      loc_18000EF38
0x18000ecde  mov     dword ptr [rsp+360h+phkResult], r15d
0x18000ece3  lea     r9, aRegenumkeyexFa; "RegEnumKeyEx failed, %d"
0x18000ecea  mov     r8d, 16Ah
0x18000ecf0  lea     rdx, aMatchregvalues_0; "MatchRegValues"
0x18000ecf7  mov     ecx, ebx
0x18000ecf9  call    AslLogCallPrintf
0x18000ecfe  jmp     loc_18000EF31
0x18000ed03  mov     edx, [rsp+360h+Type]
0x18000ed07  mov     r14, [rbp+260h+var_2C0]
0x18000ed0b  mov     rcx, r14; S1
0x18000ed0e  call    ?IsRegValueTypeMatch@AppCompatUtility@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; AppCompatUtility::IsRegValueTypeMatch(std::wstring const &,ulong)
0x18000ed13  test    al, al
0x18000ed15  jnz     short loc_18000ED62
0x18000ed17  cmp     qword ptr [r14+18h], 7
0x18000ed1c  jbe     short loc_18000ED23
0x18000ed1e  mov     rax, [r14]
0x18000ed21  jmp     short loc_18000ED26
0x18000ed23  mov     rax, r14
0x18000ed26  lea     rcx, [rbp+260h+ValueName]
0x18000ed2a  mov     [rsp+360h+lpcbMaxClassLen], rcx
0x18000ed2f  mov     [rsp+360h+lpcbMaxSubKeyLen], rax
0x18000ed34  mov     eax, [rsp+360h+Type]
0x18000ed38  mov     dword ptr [rsp+360h+phkResult], eax
0x18000ed3c  lea     r9, aRegValueTypeNo_0; "Reg value type not match: %d, %ws; for "...
0x18000ed43  mov     r8d, 126h
0x18000ed49  lea     rdx, aMatchregvalues_0; "MatchRegValues"
0x18000ed50  mov     ecx, 3
0x18000ed55  call    AslLogCallPrintf
0x18000ed5a  xor     r14d, r14d
0x18000ed5d  jmp     loc_18000EF07
0x18000ed62  mov     eax, [rsp+360h+Type]
0x18000ed66  cmp     eax, 4
0x18000ed69  jnz     short loc_18000ED6F
0x18000ed6b  mov     ecx, [rsi]
0x18000ed6d  jmp     short loc_18000ED77
0x18000ed6f  cmp     eax, 0Bh
0x18000ed72  jnz     short loc_18000ED95
0x18000ed74  mov     rcx, [rsi]
0x18000ed77  mov     rdx, [rbp+260h+arg_30]
0x18000ed7e  mov     r8, [rbp+260h+S1]
0x18000ed82  call    ?CompareInt@AppCompatUtility@@YAH_J0AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; AppCompatUtility::CompareInt(__int64,__int64,std::wstring const &)
0x18000ed87  mov     [r13+0], eax
0x18000ed8b  cmp     eax, ebx
0x18000ed8d  jz      loc_18000ECC8
0x18000ed93  jmp     short loc_18000ED5A
0x18000ed95  cmp     eax, 7
0x18000ed98  jnz     short loc_18000EE10
0x18000ed9a  mov     eax, [rsp+360h+cbMaxValueLen]
0x18000ed9e  cmp     eax, 4
0x18000eda1  jb      loc_18000EF16
0x18000eda7  shr     eax, 1
0x18000eda9  sub     eax, ebx
0x18000edab  xor     r14d, r14d
0x18000edae  mov     [rsi+rax*2], r14w
0x18000edb3  mov     eax, [rsp+360h+cbMaxValueLen]
0x18000edb7  shr     eax, 1
0x18000edb9  sub     eax, 2
0x18000edbc  mov     [rsi+rax*2], r14w
0x18000edc1  mov     rcx, rsi
0x18000edc4  cmp     [rsi], r14w
0x18000edc8  jz      short loc_18000EDEB
0x18000edca  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000edce  inc     rax
0x18000edd1  cmp     [rcx+rax*2], r14w
0x18000edd6  jnz     short loc_18000EDCE
0x18000edd8  lea     rax, [rcx+rax*2]
0x18000eddc  mov     word ptr [rax], 3Bh ; ';'
0x18000ede1  lea     rcx, [rax+2]
0x18000ede5  cmp     [rcx], r14w
0x18000ede9  jnz     short loc_18000EDCA
0x18000edeb  mov     [rsp+360h+phkResult], rsi
0x18000edf0  lea     r9, aMultiSzValueIs; "Multi sz value is: %ws"
0x18000edf7  mov     r8d, 14Ch
0x18000edfd  lea     rdx, aMatchregvalues_0; "MatchRegValues"
0x18000ee04  mov     ecx, 3
0x18000ee09  call    AslLogCallPrintf
0x18000ee0e  jmp     short loc_18000EE13
0x18000ee10  xor     r14d, r14d
0x18000ee13  cmp     [rbp+260h+arg_38], r14b
0x18000ee1a  jz      loc_18000EEB5
0x18000ee20  lea     rax, [rbp+260h+var_2A0]
0x18000ee24  mov     [rbp+260h+var_2B0], rax
0x18000ee28  mov     rdx, [rbp+260h+var_2C8]
0x18000ee2c  lea     rcx, [rbp+260h+var_2A0]
0x18000ee30  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000ee35  mov     r14, rax
0x18000ee38  xorps   xmm0, xmm0
0x18000ee3b  movups  [rbp+260h+var_280], xmm0
0x18000ee3f  xor     eax, eax
0x18000ee41  mov     qword ptr [rbp+260h+var_270], rax
0x18000ee45  mov     qword ptr [rbp+260h+var_270+8], rax
0x18000ee49  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000ee4d  inc     r8
0x18000ee50  cmp     [rsi+r8*2], ax
0x18000ee55  jnz     short loc_18000EE4D
0x18000ee57  mov     rdx, rsi
0x18000ee5a  lea     rcx, [rbp+260h+var_280]
0x18000ee5e  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000ee63  nop
0x18000ee64  mov     rax, [rbp+260h+arg_48]
0x18000ee6b  mov     [rsp+360h+phkResult], rax
0x18000ee70  mov     r9, [rbp+260h+arg_40]
0x18000ee77  mov     r8, r14
0x18000ee7a  lea     rdx, [rbp+260h+var_280]
0x18000ee7e  mov     rcx, r13
0x18000ee81  call    ?MatchRegexValue@AppCompatUtility@@YAJPEAHV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1PEAU_RegexCondition@1@_K@Z; AppCompatUtility::MatchRegexValue(int *,std::wstring,std::wstring,AppCompatUtility::_RegexCondition *,unsigned __int64)
0x18000ee86  xor     r14d, r14d
0x18000ee89  test    eax, eax
0x18000ee8b  jz      short loc_18000EEFD
0x18000ee8d  mov     dword ptr [rsp+360h+phkResult], r14d
0x18000ee92  lea     r9, aFailedToDoRege; "Failed to do regex matching. [0x%x]"
0x18000ee99  mov     r8d, 158h
0x18000ee9f  lea     rdx, aMatchregvalues_0; "MatchRegValues"
0x18000eea6  mov     ecx, ebx
  ... truncated ...
```
