# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x180019820`
- end: `0x180019dd3`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1459`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `16`
- tags: `file_ops, registry_config`

## callers

- `0x180019514`
- `0x180019820`

## callees

- `0x18000dd14`
- `0x18000de7c`
- `0x18001108c`
- `0x180017b88`
- `0x180018110`
- `0x180018160`
- `0x180018274`
- `0x180018314`
- `0x180018af8`
- `0x180018f74`
- `0x180019400`
- `0x180019820`
- `0x18001a108`
- `0x18001a1d8`
- `0x180043090`
- `0x180043150`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x180019bf0`
- `msvcrt!wcsncpy_s` at `0x180019bf0`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180019a7c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180019a7c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180019894`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800198a7`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001998b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800199ba`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180019894`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800198a7`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001998b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800199ba`

## string_xrefs

- `0x18001989a`: `ForceRemove`
- `0x18001997b`: `NoRemove`
- `0x18001988a`: `Delete`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::RegisterSubkeys(
        ATL::CRegParser *this,
        unsigned __int16 *a2,
        HKEY a3,
        int a4,
        int a5)
{
  int v5; // r15d
  unsigned __int16 *v7; // rdi
  ATL::CRegParser *i; // rsi
  int Token; // eax
  int v10; // r14d
  int v11; // ebx
  ATL::CRegParser *v12; // rcx
  int v13; // eax
  int v14; // r12d
  unsigned int v15; // eax
  unsigned __int16 *v16; // r9
  unsigned int v17; // ebx
  __int64 v18; // rax
  unsigned int v19; // r14d
  int v20; // r15d
  errno_t v21; // eax
  int v22; // eax
  ATL::CRegParser *v23; // rcx
  __int64 v24; // rax
  int HasSubKeys; // r15d
  LSTATUS v26; // r14d
  unsigned int v28; // ecx
  unsigned int v29; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v32; // [rsp+50h] [rbp-B0h]
  __int64 v33; // [rsp+58h] [rbp-A8h]
  HKEY v34[4]; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t Destination[264]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR ValueName[4096]; // [rsp+290h] [rbp+190h] BYREF

  memset(v34, 0, 24);
  v5 = a4;
  v7 = a2;
  for ( i = this; ; this = i )
  {
    Token = ATL::CRegParser::NextToken(this, a2);
LABEL_31:
    v11 = Token;
    if ( Token < 0 )
      break;
    while ( 1 )
    {
      while ( 1 )
      {
        if ( *v7 == 125 )
          goto LABEL_78;
        v10 = lstrcmpiW(v7, L"Delete");
        if ( !lstrcmpiW(v7, L"ForceRemove") || !v10 )
        {
          v11 = ATL::CRegParser::NextToken(i, v7);
          if ( v11 < 0 )
            goto LABEL_78;
          if ( v5 )
          {
            hKey = 0;
            v32 = 0;
            v33 = 0;
            if ( ATL::CRegParser::StrChrW(v7, 0x5Cu) )
            {
              ATL::CRegKey::Close(&hKey);
LABEL_77:
              v11 = -2147352567;
              goto LABEL_78;
            }
            if ( (unsigned int)ATL::CRegParser::CanForceRemoveKey(v12, v7) )
            {
              hKey = a3;
              ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)&hKey, v7);
              hKey = 0;
            }
            if ( !v10 )
            {
              v11 = ATL::CRegParser::NextToken(i, v7);
              if ( v11 < 0 )
                goto LABEL_80;
              v13 = ATL::CRegParser::SkipAssignment(i, v7);
LABEL_14:
              v11 = v13;
              if ( v13 < 0 )
                goto LABEL_80;
              ATL::CRegKey::Close(&hKey);
              goto LABEL_41;
            }
            ATL::CRegKey::Close(&hKey);
          }
        }
        v14 = 1;
        if ( !lstrcmpiW(v7, L"NoRemove") )
        {
          v14 = 0;
          v11 = ATL::CRegParser::NextToken(i, v7);
          if ( v11 < 0 )
            goto LABEL_78;
        }
        if ( !lstrcmpiW(v7, L"Val") )
        {
          v11 = ATL::CRegParser::NextToken(i, ValueName);
          if ( v11 < 0 )
            goto LABEL_78;
          v11 = ATL::CRegParser::NextToken(i, v7);
          if ( v11 < 0 )
            goto LABEL_78;
          if ( *v7 != 61 )
            goto LABEL_77;
          if ( !v5 )
          {
            if ( a5 || !v14 )
              goto LABEL_30;
            hKey = 0;
            v32 = 0;
            v33 = 0;
            v15 = ATL::CRegKey::Open((ATL::CRegKey *)&hKey, a3, 0, 0x20006u);
            if ( !v15 )
            {
              v15 = RegDeleteValueW(hKey, ValueName);
              if ( (v15 & 0xFFFFFFFD) == 0 )
              {
                ATL::CRegKey::Close(&hKey);
LABEL_30:
                Token = ATL::CRegParser::SkipAssignment(i, v7);
                goto LABEL_31;
              }
            }
LABEL_79:
            v11 = ATL::AtlHresultFromWin32(v15);
LABEL_80:
            ATL::CRegKey::Close(&hKey);
            goto LABEL_78;
          }
          v32 = 0;
          v33 = 0;
          hKey = a3;
          v13 = ATL::CRegParser::AddValue(i, (struct ATL::CRegKey *)&hKey, ValueName, v7);
          hKey = 0;
          goto LABEL_14;
        }
        if ( ATL::CRegParser::StrChrW(v7, 0x5Cu) )
          goto LABEL_77;
        if ( v5 )
          break;
        if ( a5 )
          v19 = 2;
        else
          v19 = ATL::CRegKey::Open((ATL::CRegKey *)v34, a3, v7, 0x20019u);
        v20 = 1;
        if ( !v19 )
          v20 = a5;
        v21 = wcsncpy_s(Destination, 0x104u, v7, 0xFFFFFFFFFFFFFFFFuLL);
        ATL::AtlCrtErrorCheck(v21);
        v11 = ATL::CRegParser::NextToken(i, v7);
        if ( v11 < 0 )
          goto LABEL_78;
        v22 = ATL::CRegParser::SkipAssignment(i, v7);
        v23 = 0;
        v11 = v22;
        if ( v22 < 0 )
          goto LABEL_78;
        if ( *v7 == 123 )
        {
          v24 = -1;
          do
            ++v24;
          while ( v7[v24] );
          if ( v24 == 1 )
          {
            v11 = ATL::CRegParser::RegisterSubkeys(i, v7, v34[0], 0, v20);
            if ( v11 < 0 && !v20 )
              goto LABEL_78;
            v11 = ATL::CRegParser::NextToken(i, v7);
            if ( v11 < 0 )
              goto LABEL_78;
          }
        }
        v5 = a4;
        if ( v19 != 2 )
        {
          if ( v19 )
          {
            if ( !a5 )
            {
              v11 = ATL::AtlHresultFromWin32(v19);
              goto LABEL_78;
            }
          }
          else if ( a5 && ATL::CRegParser::HasSubKeys(v23, v34[0]) )
          {
            if ( (unsigned int)ATL::CRegParser::CanForceRemoveKey(v23, Destination) && v14 )
              ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)v34, Destination);
          }
          else
          {
            HasSubKeys = ATL::CRegParser::HasSubKeys(v23, v34[0]);
            v26 = ATL::CRegKey::Close(v34);
            if ( v26 )
            {
              ATL::CRegKey::Close(v34);
              v28 = v26;
              return ATL::AtlHresultFromWin32(v28);
            }
            if ( v14 && !HasSubKeys )
            {
              v32 = 0;
              v33 = 0;
              hKey = a3;
              v15 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)&hKey, Destination);
              hKey = 0;
              if ( v15 )
                goto LABEL_79;
              ATL::CRegKey::Close(&hKey);
            }
            v5 = a4;
          }
        }
      }
      if ( (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v34, a3, v7, 0x2001Fu) )
      {
        if ( (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v34, a3, v7, 0x20019u) )
        {
          v17 = ATL::CRegKey::Create(v34, a3, v7, v16, v29);
          if ( v17 )
          {
            ATL::CRegKey::Close(v34);
            v28 = v17;
            return ATL::AtlHresultFromWin32(v28);
          }
        }
      }
      v11 = ATL::CRegParser::NextToken(i, v7);
      if ( v11 < 0 )
        goto LABEL_78;
      if ( *v7 == 61 )
      {
        v11 = ATL::CRegParser::AddValue(i, (struct ATL::CRegKey *)v34, 0, v7);
        if ( v11 < 0 )
          goto LABEL_78;
      }
LABEL_41:
      if ( *v7 == 123 )
      {
        v18 = -1;
        do
          ++v18;
        while ( v7[v18] );
        if ( v18 == 1 )
          break;
      }
    }
    v11 = ATL::CRegParser::RegisterSubkeys(i, v7, v34[0], v5, 0);
    if ( v11 < 0 )
      break;
    a2 = v7;
  }
LABEL_78:
  ATL::CRegKey::Close(v34);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180019820  push    rbp
0x180019822  push    rbx
0x180019823  push    rsi
0x180019824  push    rdi
0x180019825  push    r12
0x180019827  push    r13
0x180019829  push    r14
0x18001982b  push    r15
0x18001982d  lea     rbp, [rsp-21A8h]
0x180019835  mov     eax, 22A8h
0x18001983a  call    _alloca_probe
0x18001983f  sub     rsp, rax
0x180019842  mov     rax, cs:__security_cookie
0x180019849  xor     rax, rsp
0x18001984c  mov     [rbp+21E0h+var_50], rax
0x180019853  xor     r14d, r14d
0x180019856  mov     [rsp+22E0h+var_22A0], r9d
0x18001985b  mov     [rsp+22E0h+var_2280], r14
0x180019860  mov     r15d, r9d
0x180019863  mov     [rsp+22E0h+var_2278], r14
0x180019868  mov     r13, r8
0x18001986b  mov     [rsp+22E0h+var_2270], r14
0x180019870  mov     rdi, rdx
0x180019873  mov     rsi, rcx
0x180019876  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001987b  jmp     loc_180019AA2
0x180019880  cmp     word ptr [rdi], 7Dh ; '}'
0x180019884  jz      loc_180019D6D
0x18001988a  lea     rdx, aDelete; "Delete"
0x180019891  mov     rcx, rdi; lpString1
0x180019894  call    cs:__imp_lstrcmpiW
0x18001989a  lea     rdx, aForceremove; "ForceRemove"
0x1800198a1  mov     rcx, rdi; lpString1
0x1800198a4  mov     r14d, eax
0x1800198a7  call    cs:__imp_lstrcmpiW
0x1800198ad  test    eax, eax
0x1800198af  jz      short loc_1800198BA
0x1800198b1  test    r14d, r14d
0x1800198b4  jnz     loc_18001997B
0x1800198ba  mov     rdx, rdi; unsigned __int16 *
0x1800198bd  mov     rcx, rsi; this
0x1800198c0  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800198c5  mov     ebx, eax
0x1800198c7  test    eax, eax
0x1800198c9  js      loc_180019D6D
0x1800198cf  test    r15d, r15d
0x1800198d2  jz      loc_18001997B
0x1800198d8  mov     edx, 5Ch ; '\'; unsigned __int16
0x1800198dd  mov     [rsp+22E0h+hKey], 0
0x1800198e6  mov     rcx, rdi; lpsz
0x1800198e9  mov     [rsp+22E0h+var_2290], 0
0x1800198f2  mov     [rsp+22E0h+var_2288], 0
0x1800198fb  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x180019900  test    rax, rax
0x180019903  jnz     loc_180019D5E
0x180019909  mov     rdx, rdi; unsigned __int16 *
0x18001990c  call    ?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEBG@Z; ATL::CRegParser::CanForceRemoveKey(ushort const *)
0x180019911  test    eax, eax
0x180019913  jz      short loc_180019930
0x180019915  mov     rdx, rdi; unsigned __int16 *
0x180019918  mov     [rsp+22E0h+hKey], r13
0x18001991d  lea     rcx, [rsp+22E0h+hKey]; this
0x180019922  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180019927  mov     [rsp+22E0h+hKey], 0
0x180019930  test    r14d, r14d
0x180019933  jnz     short loc_180019971
0x180019935  mov     rdx, rdi; unsigned __int16 *
0x180019938  mov     rcx, rsi; this
0x18001993b  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180019940  xor     r14d, r14d
0x180019943  mov     ebx, eax
0x180019945  test    eax, eax
0x180019947  js      loc_180019DA5
0x18001994d  mov     rdx, rdi; unsigned __int16 *
0x180019950  mov     rcx, rsi; this
0x180019953  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180019958  lea     rcx, [rsp+22E0h+hKey]; this
0x18001995d  mov     ebx, eax
0x18001995f  test    eax, eax
0x180019961  js      loc_180019DAA
0x180019967  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001996c  jmp     loc_180019B56
0x180019971  lea     rcx, [rsp+22E0h+hKey]; this
0x180019976  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001997b  lea     rdx, aNoremove; "NoRemove"
0x180019982  mov     rcx, rdi; lpString1
0x180019985  mov     r12d, 1
0x18001998b  call    cs:__imp_lstrcmpiW
0x180019991  xor     r14d, r14d
0x180019994  test    eax, eax
0x180019996  jnz     short loc_1800199B0
0x180019998  mov     rdx, rdi; unsigned __int16 *
0x18001999b  mov     rcx, rsi; this
0x18001999e  mov     r12d, r14d
0x1800199a1  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800199a6  mov     ebx, eax
0x1800199a8  test    eax, eax
0x1800199aa  js      loc_180019D6D
0x1800199b0  lea     rdx, aVal; "Val"
0x1800199b7  mov     rcx, rdi; lpString1
0x1800199ba  call    cs:__imp_lstrcmpiW
0x1800199c0  test    eax, eax
0x1800199c2  jnz     loc_180019AB1
0x1800199c8  lea     rdx, [rbp+21E0h+ValueName]; unsigned __int16 *
0x1800199cf  mov     rcx, rsi; this
0x1800199d2  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800199d7  mov     ebx, eax
0x1800199d9  test    eax, eax
0x1800199db  js      loc_180019D6D
0x1800199e1  mov     rdx, rdi; unsigned __int16 *
0x1800199e4  mov     rcx, rsi; this
0x1800199e7  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800199ec  mov     ebx, eax
0x1800199ee  test    eax, eax
0x1800199f0  js      loc_180019D6D
0x1800199f6  cmp     word ptr [rdi], 3Dh ; '='
0x1800199fa  jnz     loc_180019D68
0x180019a00  test    r15d, r15d
0x180019a03  jz      short loc_180019A35
0x180019a05  mov     r9, rdi; unsigned __int16 *
0x180019a08  mov     [rsp+22E0h+var_2290], r14
0x180019a0d  lea     r8, [rbp+21E0h+ValueName]; unsigned __int16 *
0x180019a14  mov     [rsp+22E0h+var_2288], r14
0x180019a19  lea     rdx, [rsp+22E0h+hKey]; struct ATL::CRegKey *
0x180019a1e  mov     [rsp+22E0h+hKey], r13
0x180019a23  mov     rcx, rsi; this
0x180019a26  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180019a2b  mov     [rsp+22E0h+hKey], r14
0x180019a30  jmp     loc_180019958
0x180019a35  cmp     [rbp+21E0h+arg_20], r14d
0x180019a3c  jnz     short loc_180019A97
0x180019a3e  test    r12d, r12d
0x180019a41  jz      short loc_180019A97
0x180019a43  mov     r9d, 20006h; unsigned int
0x180019a49  mov     [rsp+22E0h+hKey], r14
0x180019a4e  xor     r8d, r8d; lpSubKey
0x180019a51  mov     [rsp+22E0h+var_2290], r14
0x180019a56  mov     rdx, r13; hKey
0x180019a59  mov     [rsp+22E0h+var_2288], r14
0x180019a5e  lea     rcx, [rsp+22E0h+hKey]; this
0x180019a63  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180019a68  test    eax, eax
0x180019a6a  jnz     loc_180019D9C
0x180019a70  mov     rcx, [rsp+22E0h+hKey]; hKey
0x180019a75  lea     rdx, [rbp+21E0h+ValueName]; lpValueName
0x180019a7c  call    cs:__imp_RegDeleteValueW
0x180019a82  test    eax, 0FFFFFFFDh
0x180019a87  jnz     loc_180019D9C
0x180019a8d  lea     rcx, [rsp+22E0h+hKey]; this
0x180019a92  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180019a97  mov     rdx, rdi; unsigned __int16 *
0x180019a9a  mov     rcx, rsi; this
0x180019a9d  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180019aa2  mov     ebx, eax
0x180019aa4  test    eax, eax
0x180019aa6  jns     loc_180019880
0x180019aac  jmp     loc_180019D6D
0x180019ab1  mov     edx, 5Ch ; '\'; unsigned __int16
0x180019ab6  mov     rcx, rdi; lpsz
0x180019ab9  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x180019abe  test    rax, rax
0x180019ac1  jnz     loc_180019D68
0x180019ac7  test    r15d, r15d
0x180019aca  jz      loc_180019BA5
0x180019ad0  mov     r9d, 2001Fh; unsigned int
0x180019ad6  lea     rcx, [rsp+22E0h+var_2280]; this
0x180019adb  mov     r8, rdi; lpSubKey
0x180019ade  mov     rdx, r13; hKey
0x180019ae1  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180019ae6  test    eax, eax
0x180019ae8  jz      short loc_180019B1E
0x180019aea  mov     r9d, 20019h; unsigned int
0x180019af0  lea     rcx, [rsp+22E0h+var_2280]; this
0x180019af5  mov     r8, rdi; lpSubKey
0x180019af8  mov     rdx, r13; hKey
0x180019afb  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180019b00  test    eax, eax
0x180019b02  jz      short loc_180019B1E
0x180019b04  mov     r8, rdi; lpSubKey
0x180019b07  lea     rcx, [rsp+22E0h+var_2280]; this
0x180019b0c  mov     rdx, r13; hKey
0x180019b0f  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x180019b14  mov     ebx, eax
0x180019b16  test    eax, eax
0x180019b18  jnz     loc_180019DB1
0x180019b1e  mov     rdx, rdi; unsigned __int16 *
0x180019b21  mov     rcx, rsi; this
0x180019b24  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180019b29  mov     ebx, eax
0x180019b2b  test    eax, eax
0x180019b2d  js      loc_180019D6D
0x180019b33  cmp     word ptr [rdi], 3Dh ; '='
0x180019b37  jnz     short loc_180019B56
0x180019b39  mov     r9, rdi; unsigned __int16 *
0x180019b3c  lea     rdx, [rsp+22E0h+var_2280]; struct ATL::CRegKey *
0x180019b41  xor     r8d, r8d; unsigned __int16 *
0x180019b44  mov     rcx, rsi; this
0x180019b47  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180019b4c  mov     ebx, eax
0x180019b4e  test    eax, eax
0x180019b50  js      loc_180019D6D
0x180019b56  cmp     word ptr [rdi], 7Bh ; '{'
0x180019b5a  jnz     loc_180019880
0x180019b60  or      rax, 0FFFFFFFFFFFFFFFFh
0x180019b64  inc     rax
0x180019b67  cmp     [rdi+rax*2], r14w
0x180019b6c  jnz     short loc_180019B64
0x180019b6e  cmp     rax, 1
0x180019b72  jnz     loc_180019880
0x180019b78  mov     r8, [rsp+22E0h+var_2280]; HKEY
0x180019b7d  mov     r9d, r15d; int
0x180019b80  mov     rdx, rdi; unsigned __int16 *
0x180019b83  mov     [rsp+22E0h+var_22C0], r14d; int
0x180019b88  mov     rcx, rsi; this
0x180019b8b  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180019b90  mov     ebx, eax
0x180019b92  test    eax, eax
0x180019b94  js      loc_180019D6D
0x180019b9a  mov     rdx, rdi
0x180019b9d  mov     rcx, rsi
0x180019ba0  jmp     loc_180019876
0x180019ba5  cmp     [rbp+21E0h+arg_20], r14d
0x180019bac  jnz     short loc_180019BC9
0x180019bae  mov     r9d, 20019h; unsigned int
0x180019bb4  lea     rcx, [rsp+22E0h+var_2280]; this
0x180019bb9  mov     r8, rdi; lpSubKey
0x180019bbc  mov     rdx, r13; hKey
0x180019bbf  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180019bc4  mov     r14d, eax
0x180019bc7  jmp     short loc_180019BCF
0x180019bc9  mov     r14d, 2
0x180019bcf  test    r14d, r14d
0x180019bd2  lea     rcx, [rbp+21E0h+Destination]; Destination
0x180019bd6  mov     r15d, 1
0x180019bdc  mov     r8, rdi; Source
0x180019bdf  cmovz   r15d, [rbp+21E0h+arg_20]
0x180019be7  mov     edx, 104h; SizeInWords
0x180019bec  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x180019bf0  call    cs:__imp_wcsncpy_s
0x180019bf6  mov     ecx, eax; int
0x180019bf8  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180019bfd  mov     rdx, rdi; unsigned __int16 *
0x180019c00  mov     rcx, rsi; this
0x180019c03  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180019c08  mov     ebx, eax
0x180019c0a  test    eax, eax
0x180019c0c  js      loc_180019D6D
0x180019c12  mov     rdx, rdi; unsigned __int16 *
0x180019c15  mov     rcx, rsi; this
0x180019c18  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180019c1d  xor     ecx, ecx
0x180019c1f  mov     ebx, eax
0x180019c21  test    eax, eax
0x180019c23  js      loc_180019D6D
0x180019c29  cmp     word ptr [rdi], 7Bh ; '{'
0x180019c2d  jnz     short loc_180019C7E
0x180019c2f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180019c33  inc     rax
0x180019c36  cmp     [rdi+rax*2], cx
0x180019c3a  jnz     short loc_180019C33
0x180019c3c  cmp     rax, 1
0x180019c40  jnz     short loc_180019C7E
0x180019c42  mov     r8, [rsp+22E0h+var_2280]; HKEY
0x180019c47  xor     r9d, r9d; int
0x180019c4a  mov     rdx, rdi; unsigned __int16 *
0x180019c4d  mov     [rsp+22E0h+var_22C0], r15d; int
0x180019c52  mov     rcx, rsi; this
0x180019c55  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180019c5a  mov     ebx, eax
0x180019c5c  test    eax, eax
0x180019c5e  jns     short loc_180019C69
0x180019c60  test    r15d, r15d
0x180019c63  jz      loc_180019D6D
0x180019c69  mov     rdx, rdi; unsigned __int16 *
0x180019c6c  mov     rcx, rsi; this
0x180019c6f  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180019c74  mov     ebx, eax
0x180019c76  test    eax, eax
0x180019c78  js      loc_180019D6D
0x180019c7e  mov     r15d, [rsp+22E0h+var_22A0]
0x180019c83  cmp     r14d, 2
0x180019c87  jz      loc_180019880
0x180019c8d  test    r14d, r14d
0x180019c90  jz      short loc_180019CAE
0x180019c92  cmp     [rbp+21E0h+arg_20], 0
0x180019c99  jnz     loc_180019880
0x180019c9f  mov     ecx, r14d; unsigned int
0x180019ca2  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180019ca7  mov     ebx, eax
0x180019ca9  jmp     loc_180019D6D
0x180019cae  xor     r14d, r14d
0x180019cb1  cmp     [rbp+21E0h+arg_20], r14d
0x180019cb8  jz      short loc_180019CF5
0x180019cba  mov     rdx, [rsp+22E0h+var_2280]; HKEY
0x180019cbf  call    ?HasSubKeys@CRegParser@ATL@@IEAAHPEAUHKEY__@@@Z; ATL::CRegParser::HasSubKeys(HKEY__ *)
0x180019cc4  test    eax, eax
0x180019cc6  jz      short loc_180019CF5
0x180019cc8  lea     rdx, [rbp+21E0h+Destination]; unsigned __int16 *
0x180019ccc  call    ?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEBG@Z; ATL::CRegParser::CanForceRemoveKey(ushort const *)
0x180019cd1  test    eax, eax
  ... truncated ...
```
