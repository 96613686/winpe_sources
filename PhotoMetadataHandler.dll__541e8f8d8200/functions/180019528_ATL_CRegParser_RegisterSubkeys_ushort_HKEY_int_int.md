# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x180019528`
- end: `0x180019b01`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1497`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, registry_config`

## callers

- `0x18001916c`
- `0x180019528`

## callees

- `0x18000f620`
- `0x18000f678`
- `0x180010e60`
- `0x180016020`
- `0x180017adc`
- `0x180018324`
- `0x180018738`
- `0x180018998`
- `0x180018b78`
- `0x180018bfc`
- `0x180019058`
- `0x180019528`
- `0x180019c24`
- `0x180019cf4`
- `0x180026420`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18001992e`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18001992e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001982f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001982f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18001977d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18001977d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800195a3`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800195b6`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001968a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800196b9`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800195a3`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800195b6`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001968a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800196b9`

## string_xrefs

- `0x1800195ac`: `ForceRemove`
- `0x180019680`: `NoRemove`
- `0x180019599`: `Delete`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CRegParser::RegisterSubkeys(
        ATL::CRegParser *this,
        unsigned __int16 *a2,
        HKEY a3,
        int a4,
        int a5)
{
  int v5; // r15d
  unsigned __int16 *v7; // rdi
  ATL::CRegParser *v8; // rsi
  int Token; // eax
  int v10; // ebx
  int v11; // r14d
  ATL::CRegParser *v12; // rcx
  int v13; // eax
  int v14; // r12d
  LSTATUS v15; // eax
  LSTATUS v16; // ecx
  __int64 v17; // rax
  int v18; // r14d
  int v19; // r15d
  int v20; // eax
  ATL::CRegParser *v21; // rcx
  __int64 v22; // rax
  int HasSubKeys; // r14d
  LSTATUS v24; // eax
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v28; // [rsp+60h] [rbp-A0h]
  __int64 v29; // [rsp+68h] [rbp-98h]
  HKEY v30[3]; // [rsp+70h] [rbp-90h] BYREF
  DWORD dwDisposition; // [rsp+88h] [rbp-78h] BYREF
  HKEY phkResult; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v33[264]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR ValueName[4096]; // [rsp+2B0h] [rbp+1B0h] BYREF

  v5 = a4;
  v7 = a2;
  v8 = this;
  memset(v30, 0, sizeof(v30));
LABEL_2:
  Token = ATL::CRegParser::NextToken(this, a2);
  while ( 2 )
  {
    v10 = Token;
    if ( Token < 0 )
      goto LABEL_79;
    while ( 1 )
    {
      if ( *v7 == 125 )
        goto LABEL_79;
      v11 = lstrcmpiW(v7, L"Delete");
      if ( !lstrcmpiW(v7, L"ForceRemove") || !v11 )
      {
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_79;
        if ( v5 )
        {
          hKey = 0;
          v28 = 0;
          v29 = 0;
          if ( ATL::CRegParser::StrChrW(v7, 0x5Cu) )
          {
            ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_78:
            v10 = -2147352567;
            goto LABEL_79;
          }
          if ( ATL::CRegParser::CanForceRemoveKey(v12, v7) )
          {
            hKey = a3;
            ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)&hKey, v7);
            hKey = 0;
          }
          if ( !v11 )
          {
            v10 = ATL::CRegParser::NextToken(v8, v7);
            if ( v10 < 0 )
              goto LABEL_81;
            v13 = ATL::CRegParser::SkipAssignment(v8, v7);
            v10 = v13;
            goto LABEL_15;
          }
          ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
        }
      }
      v14 = 1;
      if ( !lstrcmpiW(v7, L"NoRemove") )
      {
        v14 = 0;
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_79;
      }
      if ( !lstrcmpiW(v7, L"Val") )
        break;
      if ( ATL::CRegParser::StrChrW(v7, 0x5Cu) )
        goto LABEL_78;
      if ( v5 )
      {
        if ( (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v30, a3, v7, 0x2001Fu) )
        {
          if ( (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v30, a3, v7, 0x20019u) )
          {
            dwDisposition = 0;
            phkResult = 0;
            v16 = RegCreateKeyExW(a3, v7, 0, 0, 0, 0x2001Fu, 0, &phkResult, &dwDisposition);
            if ( v16 )
              goto LABEL_65;
            v16 = ATL::CRegKey::Close((ATL::CRegKey *)v30);
            v30[0] = phkResult;
            if ( v16 )
              goto LABEL_65;
          }
        }
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_79;
        if ( *v7 == 61 )
        {
          v10 = ATL::CRegParser::AddValue(v8, v30, 0, v7);
          if ( v10 < 0 )
            goto LABEL_79;
        }
LABEL_41:
        if ( *v7 == 123 )
        {
          v17 = -1;
          do
            ++v17;
          while ( v7[v17] );
          if ( v17 == 1 )
          {
            v10 = ATL::CRegParser::RegisterSubkeys(v8, v7, v30[0], v5, 0);
            if ( v10 < 0 )
              goto LABEL_79;
            a2 = v7;
            this = v8;
            goto LABEL_2;
          }
        }
      }
      else
      {
        if ( a5 )
          v18 = 2;
        else
          v18 = ATL::CRegKey::Open((ATL::CRegKey *)v30, a3, v7, 0x20019u);
        v19 = 1;
        if ( !v18 )
          v19 = a5;
        v20 = _o_wcsncpy_s(v33, 260, v7, -1);
        ATL::AtlCrtErrorCheck(v20);
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_79;
        v10 = ATL::CRegParser::SkipAssignment(v8, v7);
        v21 = 0;
        if ( v10 < 0 )
          goto LABEL_79;
        if ( *v7 == 123 )
        {
          v22 = -1;
          do
            ++v22;
          while ( v7[v22] );
          if ( v22 == 1 )
          {
            v10 = ATL::CRegParser::RegisterSubkeys(v8, v7, v30[0], 0, v19);
            if ( v10 < 0 && !v19 )
              goto LABEL_79;
            v10 = ATL::CRegParser::NextToken(v8, v7);
            if ( v10 < 0 )
              goto LABEL_79;
          }
        }
        v5 = a4;
        if ( v18 != 2 )
        {
          if ( v18 )
          {
            if ( !a5 )
            {
              v16 = v18;
LABEL_65:
              v10 = ATL::AtlHresultFromWin32(v16);
              goto LABEL_79;
            }
          }
          else if ( a5 && ATL::CRegParser::HasSubKeys(v21, v30[0]) )
          {
            if ( ATL::CRegParser::CanForceRemoveKey(v21, v33) && v14 )
              ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)v30, v33);
          }
          else
          {
            HasSubKeys = ATL::CRegParser::HasSubKeys(v21, v30[0]);
            v24 = ATL::CRegKey::Close((ATL::CRegKey *)v30);
            if ( v24 )
            {
              v16 = v24;
              goto LABEL_65;
            }
            if ( v14 && !HasSubKeys )
            {
              v28 = 0;
              v29 = 0;
              hKey = a3;
              v15 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)&hKey, v33);
              hKey = 0;
              if ( v15 )
                goto LABEL_80;
              ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
            }
          }
        }
      }
    }
    v10 = ATL::CRegParser::NextToken(v8, ValueName);
    if ( v10 < 0 )
      goto LABEL_79;
    v10 = ATL::CRegParser::NextToken(v8, v7);
    if ( v10 < 0 )
      goto LABEL_79;
    if ( *v7 != 61 )
      goto LABEL_78;
    if ( v5 )
    {
      v28 = 0;
      v29 = 0;
      hKey = a3;
      v13 = ATL::CRegParser::AddValue(v8, &hKey, ValueName, v7);
      v10 = v13;
      hKey = 0;
LABEL_15:
      if ( v13 < 0 )
        goto LABEL_81;
      ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
      goto LABEL_41;
    }
    if ( a5 || !v14 )
      goto LABEL_31;
    hKey = 0;
    v28 = 0;
    v29 = 0;
    v15 = ATL::CRegKey::Open((ATL::CRegKey *)&hKey, a3, 0, 0x20006u);
    if ( !v15 )
    {
      v15 = RegDeleteValueW(hKey, ValueName);
      if ( (v15 & 0xFFFFFFFD) == 0 )
      {
        ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_31:
        Token = ATL::CRegParser::SkipAssignment(v8, v7);
        continue;
      }
    }
    break;
  }
LABEL_80:
  v10 = ATL::AtlHresultFromWin32(v15);
LABEL_81:
  ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_79:
  ATL::CRegKey::Close((ATL::CRegKey *)v30);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180019528  push    rbp
0x18001952a  push    rbx
0x18001952b  push    rsi
0x18001952c  push    rdi
0x18001952d  push    r12
0x18001952f  push    r13
0x180019531  push    r14
0x180019533  push    r15
0x180019535  lea     rbp, [rsp-21C8h]
0x18001953d  mov     eax, 22C8h
0x180019542  call    _alloca_probe
0x180019547  sub     rsp, rax
0x18001954a  mov     rax, cs:__security_cookie
0x180019551  xor     rax, rsp
0x180019554  mov     [rbp+2200h+var_50], rax
0x18001955b  mov     r15d, r9d
0x18001955e  mov     [rsp+2300h+var_22B0], r9d
0x180019563  mov     r13, r8
0x180019566  mov     rdi, rdx
0x180019569  mov     rsi, rcx
0x18001956c  xor     r14d, r14d
0x18001956f  mov     [rsp+2300h+var_2290], r14
0x180019574  mov     [rsp+2300h+var_2288], r14
0x180019579  mov     [rbp+2200h+var_2280], r14
0x18001957d  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180019582  test    eax, eax
0x180019584  mov     ebx, eax
0x180019586  js      loc_180019AB5
0x18001958c  xor     r12d, r12d
0x18001958f  cmp     word ptr [rdi], 7Dh ; '}'
0x180019593  jz      loc_180019AB5
0x180019599  lea     rdx, aDelete; "Delete"
0x1800195a0  mov     rcx, rdi; lpString1
0x1800195a3  call    cs:__imp_lstrcmpiW
0x1800195a9  mov     r14d, eax
0x1800195ac  lea     rdx, aForceremove; "ForceRemove"
0x1800195b3  mov     rcx, rdi; lpString1
0x1800195b6  call    cs:__imp_lstrcmpiW
0x1800195bc  test    eax, eax
0x1800195be  jz      short loc_1800195C9
0x1800195c0  test    r14d, r14d
0x1800195c3  jnz     loc_18001967A
0x1800195c9  mov     rdx, rdi; unsigned __int16 *
0x1800195cc  mov     rcx, rsi; this
0x1800195cf  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800195d4  mov     ebx, eax
0x1800195d6  test    eax, eax
0x1800195d8  js      loc_180019AB5
0x1800195de  test    r15d, r15d
0x1800195e1  jz      loc_18001967A
0x1800195e7  mov     [rsp+2300h+hKey], r12
0x1800195ec  mov     [rsp+2300h+var_22A0], r12
0x1800195f1  mov     [rsp+2300h+var_2298], r12
0x1800195f6  mov     edx, 5Ch ; '\'; unsigned __int16
0x1800195fb  mov     rcx, rdi; lpsz
0x1800195fe  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x180019603  test    rax, rax
0x180019606  jnz     loc_180019AA6
0x18001960c  mov     rdx, rdi; unsigned __int16 *
0x18001960f  call    ?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEBG@Z; ATL::CRegParser::CanForceRemoveKey(ushort const *)
0x180019614  test    eax, eax
0x180019616  jz      short loc_18001962F
0x180019618  mov     [rsp+2300h+hKey], r13
0x18001961d  mov     rdx, rdi; unsigned __int16 *
0x180019620  lea     rcx, [rsp+2300h+hKey]; this
0x180019625  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x18001962a  mov     [rsp+2300h+hKey], r12
0x18001962f  test    r14d, r14d
0x180019632  jnz     short loc_180019670
0x180019634  mov     rdx, rdi; unsigned __int16 *
0x180019637  mov     rcx, rsi; this
0x18001963a  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001963f  mov     ebx, eax
0x180019641  xor     r14d, r14d
0x180019644  test    eax, eax
0x180019646  js      loc_180019AED
0x18001964c  mov     rdx, rdi; unsigned __int16 *
0x18001964f  mov     rcx, rsi; this
0x180019652  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180019657  mov     ebx, eax
0x180019659  test    eax, eax
0x18001965b  lea     rcx, [rsp+2300h+hKey]; this
0x180019660  js      loc_180019AF2
0x180019666  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001966b  jmp     loc_180019894
0x180019670  lea     rcx, [rsp+2300h+hKey]; this
0x180019675  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001967a  mov     r12d, 1
0x180019680  lea     rdx, aNoremove; "NoRemove"
0x180019687  mov     rcx, rdi; lpString1
0x18001968a  call    cs:__imp_lstrcmpiW
0x180019690  xor     r14d, r14d
0x180019693  test    eax, eax
0x180019695  jnz     short loc_1800196AF
0x180019697  mov     r12d, r14d
0x18001969a  mov     rdx, rdi; unsigned __int16 *
0x18001969d  mov     rcx, rsi; this
0x1800196a0  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800196a5  mov     ebx, eax
0x1800196a7  test    eax, eax
0x1800196a9  js      loc_180019AB5
0x1800196af  lea     rdx, aVal; "Val"
0x1800196b6  mov     rcx, rdi; lpString1
0x1800196b9  call    cs:__imp_lstrcmpiW
0x1800196bf  test    eax, eax
0x1800196c1  jnz     loc_1800197A8
0x1800196c7  lea     rdx, [rbp+2200h+ValueName]; unsigned __int16 *
0x1800196ce  mov     rcx, rsi; this
0x1800196d1  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800196d6  mov     ebx, eax
0x1800196d8  test    eax, eax
0x1800196da  js      loc_180019AB5
0x1800196e0  mov     rdx, rdi; unsigned __int16 *
0x1800196e3  mov     rcx, rsi; this
0x1800196e6  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800196eb  mov     ebx, eax
0x1800196ed  test    eax, eax
0x1800196ef  js      loc_180019AB5
0x1800196f5  cmp     word ptr [rdi], 3Dh ; '='
0x1800196f9  jnz     loc_180019AB0
0x1800196ff  test    r15d, r15d
0x180019702  jz      short loc_180019736
0x180019704  mov     [rsp+2300h+var_22A0], r14
0x180019709  mov     [rsp+2300h+var_2298], r14
0x18001970e  mov     [rsp+2300h+hKey], r13
0x180019713  mov     r9, rdi; unsigned __int16 *
0x180019716  lea     r8, [rbp+2200h+ValueName]; unsigned __int16 *
0x18001971d  lea     rdx, [rsp+2300h+hKey]; struct ATL::CRegKey *
0x180019722  mov     rcx, rsi; this
0x180019725  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x18001972a  mov     ebx, eax
0x18001972c  mov     [rsp+2300h+hKey], r14
0x180019731  jmp     loc_180019659
0x180019736  cmp     [rbp+2200h+arg_20], r14d
0x18001973d  jnz     short loc_180019798
0x18001973f  test    r12d, r12d
0x180019742  jz      short loc_180019798
0x180019744  mov     [rsp+2300h+hKey], r14
0x180019749  mov     [rsp+2300h+var_22A0], r14
0x18001974e  mov     [rsp+2300h+var_2298], r14
0x180019753  mov     r9d, 20006h; unsigned int
0x180019759  xor     r8d, r8d; lpSubKey
0x18001975c  mov     rdx, r13; hKey
0x18001975f  lea     rcx, [rsp+2300h+hKey]; this
0x180019764  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180019769  test    eax, eax
0x18001976b  jnz     loc_180019AE4
0x180019771  lea     rdx, [rbp+2200h+ValueName]; lpValueName
0x180019778  mov     rcx, [rsp+2300h+hKey]; hKey
0x18001977d  call    cs:__imp_RegDeleteValueW
0x180019783  test    eax, 0FFFFFFFDh
0x180019788  jnz     loc_180019AE4
0x18001978e  lea     rcx, [rsp+2300h+hKey]; this
0x180019793  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180019798  mov     rdx, rdi; unsigned __int16 *
0x18001979b  mov     rcx, rsi; this
0x18001979e  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x1800197a3  jmp     loc_180019582
0x1800197a8  mov     edx, 5Ch ; '\'; unsigned __int16
0x1800197ad  mov     rcx, rdi; lpsz
0x1800197b0  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x1800197b5  test    rax, rax
0x1800197b8  jnz     loc_180019AB0
0x1800197be  test    r15d, r15d
0x1800197c1  jz      loc_1800198E3
0x1800197c7  mov     ebx, 2001Fh
0x1800197cc  mov     r9d, ebx; unsigned int
0x1800197cf  mov     r8, rdi; lpSubKey
0x1800197d2  mov     rdx, r13; hKey
0x1800197d5  lea     rcx, [rsp+2300h+var_2290]; this
0x1800197da  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1800197df  test    eax, eax
0x1800197e1  jz      short loc_18001985C
0x1800197e3  lea     r9d, [rbx-6]; unsigned int
0x1800197e7  mov     r8, rdi; lpSubKey
0x1800197ea  mov     rdx, r13; hKey
0x1800197ed  lea     rcx, [rsp+2300h+var_2290]; this
0x1800197f2  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1800197f7  test    eax, eax
0x1800197f9  jz      short loc_18001985C
0x1800197fb  mov     [rbp+2200h+dwDisposition], r14d
0x1800197ff  mov     [rbp+2200h+var_2270], r14
0x180019803  lea     rax, [rbp+2200h+dwDisposition]
0x180019807  mov     [rsp+2300h+lpdwDisposition], rax; lpdwDisposition
0x18001980c  lea     rax, [rbp+2200h+var_2270]
0x180019810  mov     [rsp+2300h+phkResult], rax; phkResult
0x180019815  mov     [rsp+2300h+lpSecurityAttributes], r14; lpSecurityAttributes
0x18001981a  mov     [rsp+2300h+samDesired], ebx; samDesired
0x18001981e  mov     [rsp+2300h+dwOptions], r14d; dwOptions
0x180019823  xor     r9d, r9d; lpClass
0x180019826  xor     r8d, r8d; Reserved
0x180019829  mov     rdx, rdi; lpSubKey
0x18001982c  mov     rcx, r13; hKey
0x18001982f  call    cs:__imp_RegCreateKeyExW
0x180019835  mov     ecx, eax
0x180019837  test    eax, eax
0x180019839  jnz     loc_1800199E3
0x18001983f  lea     rcx, [rsp+2300h+var_2290]; this
0x180019844  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180019849  mov     ecx, eax
0x18001984b  mov     rax, [rbp+2200h+var_2270]
0x18001984f  mov     [rsp+2300h+var_2290], rax
0x180019854  test    ecx, ecx
0x180019856  jnz     loc_1800199E3
0x18001985c  mov     rdx, rdi; unsigned __int16 *
0x18001985f  mov     rcx, rsi; this
0x180019862  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180019867  mov     ebx, eax
0x180019869  test    eax, eax
0x18001986b  js      loc_180019AB5
0x180019871  cmp     word ptr [rdi], 3Dh ; '='
0x180019875  jnz     short loc_180019894
0x180019877  mov     r9, rdi; unsigned __int16 *
0x18001987a  xor     r8d, r8d; unsigned __int16 *
0x18001987d  lea     rdx, [rsp+2300h+var_2290]; struct ATL::CRegKey *
0x180019882  mov     rcx, rsi; this
0x180019885  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x18001988a  mov     ebx, eax
0x18001988c  test    eax, eax
0x18001988e  js      loc_180019AB5
0x180019894  cmp     word ptr [rdi], 7Bh ; '{'
0x180019898  jnz     loc_18001958C
0x18001989e  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800198a2  inc     rax
0x1800198a5  cmp     [rdi+rax*2], r14w
0x1800198aa  jnz     short loc_1800198A2
0x1800198ac  cmp     rax, 1
0x1800198b0  jnz     loc_18001958C
0x1800198b6  mov     [rsp+2300h+dwOptions], r14d; int
0x1800198bb  mov     r9d, r15d; int
0x1800198be  mov     r8, [rsp+2300h+var_2290]; HKEY
0x1800198c3  mov     rdx, rdi; unsigned __int16 *
0x1800198c6  mov     rcx, rsi; this
0x1800198c9  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x1800198ce  mov     ebx, eax
0x1800198d0  test    eax, eax
0x1800198d2  js      loc_180019AB5
0x1800198d8  mov     rdx, rdi
0x1800198db  mov     rcx, rsi
0x1800198de  jmp     loc_18001957D
0x1800198e3  cmp     [rbp+2200h+arg_20], r14d
0x1800198ea  jnz     short loc_180019907
0x1800198ec  mov     r9d, 20019h; unsigned int
0x1800198f2  mov     r8, rdi; lpSubKey
0x1800198f5  mov     rdx, r13; hKey
0x1800198f8  lea     rcx, [rsp+2300h+var_2290]; this
0x1800198fd  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180019902  mov     r14d, eax
0x180019905  jmp     short loc_18001990D
0x180019907  mov     r14d, 2
0x18001990d  mov     r15d, 1
0x180019913  test    r14d, r14d
0x180019916  cmovz   r15d, [rbp+2200h+arg_20]
0x18001991e  or      r9, 0FFFFFFFFFFFFFFFFh
0x180019922  mov     r8, rdi
0x180019925  mov     edx, 104h
0x18001992a  lea     rcx, [rbp+2200h+var_2260]
0x18001992e  call    cs:__imp__o_wcsncpy_s
0x180019934  mov     ecx, eax; int
0x180019936  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18001993b  mov     rdx, rdi; unsigned __int16 *
0x18001993e  mov     rcx, rsi; this
0x180019941  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180019946  mov     ebx, eax
0x180019948  test    eax, eax
0x18001994a  js      loc_180019AB5
0x180019950  mov     rdx, rdi; unsigned __int16 *
0x180019953  mov     rcx, rsi; this
0x180019956  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18001995b  mov     ebx, eax
0x18001995d  xor     ecx, ecx
0x18001995f  test    eax, eax
0x180019961  js      loc_180019AB5
0x180019967  cmp     word ptr [rdi], 7Bh ; '{'
0x18001996b  jnz     short loc_1800199BC
0x18001996d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180019971  inc     rax
0x180019974  cmp     [rdi+rax*2], cx
0x180019978  jnz     short loc_180019971
0x18001997a  cmp     rax, 1
0x18001997e  jnz     short loc_1800199BC
0x180019980  mov     [rsp+2300h+dwOptions], r15d; int
0x180019985  xor     r9d, r9d; int
0x180019988  mov     r8, [rsp+2300h+var_2290]; HKEY
0x18001998d  mov     rdx, rdi; unsigned __int16 *
0x180019990  mov     rcx, rsi; this
0x180019993  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180019998  mov     ebx, eax
0x18001999a  test    eax, eax
0x18001999c  jns     short loc_1800199A7
0x18001999e  test    r15d, r15d
0x1800199a1  jz      loc_180019AB5
0x1800199a7  mov     rdx, rdi; unsigned __int16 *
0x1800199aa  mov     rcx, rsi; this
0x1800199ad  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800199b2  mov     ebx, eax
0x1800199b4  test    eax, eax
0x1800199b6  js      loc_180019AB5
0x1800199bc  cmp     r14d, 2
0x1800199c0  mov     r15d, [rsp+2300h+var_22B0]
  ... truncated ...
```
