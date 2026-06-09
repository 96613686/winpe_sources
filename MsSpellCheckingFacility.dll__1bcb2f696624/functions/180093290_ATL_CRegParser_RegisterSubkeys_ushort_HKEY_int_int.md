# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x180093290`
- end: `0x18009386b`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1499`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, registry_config`

## callers

- `0x180092f6c`
- `0x180093290`

## callees

- `0x18005d14c`
- `0x180061320`
- `0x18006b8d4`
- `0x18006ba64`
- `0x18006c190`
- `0x18009129c`
- `0x180091914`
- `0x180091944`
- `0x180092434`
- `0x180092970`
- `0x180092e58`
- `0x180093290`
- `0x180093ab0`
- `0x180093bf0`
- `0x1800b7bf0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180093696`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180093696`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800934e5`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800934e5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180093597`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180093597`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18009330b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18009331e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800933f2`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180093421`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18009330b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18009331e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800933f2`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180093421`

## string_xrefs

- `0x180093314`: `ForceRemove`
- `0x1800933e8`: `NoRemove`
- `0x180093301`: `Delete`

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
  __int64 dwOptions; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v29; // [rsp+60h] [rbp-A0h]
  __int64 v30; // [rsp+68h] [rbp-98h]
  HKEY v31[3]; // [rsp+70h] [rbp-90h] BYREF
  DWORD dwDisposition; // [rsp+88h] [rbp-78h] BYREF
  HKEY phkResult; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v34[264]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR ValueName[4096]; // [rsp+2B0h] [rbp+1B0h] BYREF

  v5 = a4;
  v7 = a2;
  v8 = this;
  memset(v31, 0, sizeof(v31));
LABEL_2:
  Token = ATL::CRegParser::NextToken(this, a2);
  while ( 2 )
  {
    v10 = Token;
    if ( Token < 0 )
      goto LABEL_80;
    while ( 1 )
    {
      if ( *v7 == 125 )
        goto LABEL_80;
      v11 = lstrcmpiW(v7, L"Delete");
      if ( !lstrcmpiW(v7, L"ForceRemove") || !v11 )
      {
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_80;
        if ( v5 )
        {
          hKey = 0;
          v29 = 0;
          v30 = 0;
          if ( ATL::CRegParser::StrChrW(v7, 0x5Cu) )
          {
            ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_79:
            v10 = -2147352567;
            goto LABEL_80;
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
              goto LABEL_82;
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
          goto LABEL_80;
      }
      if ( !lstrcmpiW(v7, L"Val") )
        break;
      if ( ATL::CRegParser::StrChrW(v7, 0x5Cu) )
        goto LABEL_79;
      if ( v5 )
      {
        if ( (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v31, a3, v7, 0x2001Fu) )
        {
          if ( (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v31, a3, v7, 0x20019u) )
          {
            dwDisposition = 0;
            phkResult = 0;
            v16 = RegCreateKeyExW(a3, v7, 0, 0, 0, 0x2001Fu, 0, &phkResult, &dwDisposition);
            if ( v16 )
              goto LABEL_65;
            v16 = ATL::CRegKey::Close((ATL::CRegKey *)v31);
            v31[0] = phkResult;
            if ( v16 )
              goto LABEL_65;
          }
        }
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_80;
        if ( *v7 == 61 )
        {
          v10 = ATL::CRegParser::AddValue(v8, v31, 0, v7);
          if ( v10 < 0 )
            goto LABEL_80;
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
            v10 = ATL::CRegParser::RegisterSubkeys(v8, v7, v31[0], v5, 0);
            if ( v10 < 0 )
              goto LABEL_80;
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
          v18 = ATL::CRegKey::Open((ATL::CRegKey *)v31, a3, v7, 0x20019u);
        v19 = 1;
        if ( !v18 )
          v19 = a5;
        v20 = _o_wcsncpy_s(v34, 260, v7, -1, dwOptions);
        ATL::AtlCrtErrorCheck(v20);
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_80;
        v10 = ATL::CRegParser::SkipAssignment(v8, v7);
        v21 = 0;
        if ( v10 < 0 )
          goto LABEL_80;
        if ( *v7 == 123 )
        {
          v22 = -1;
          do
            ++v22;
          while ( v7[v22] );
          if ( v22 == 1 )
          {
            v10 = ATL::CRegParser::RegisterSubkeys(v8, v7, v31[0], 0, v19);
            if ( v10 < 0 && !v19 )
              goto LABEL_80;
            v10 = ATL::CRegParser::NextToken(v8, v7);
            if ( v10 < 0 )
              goto LABEL_80;
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
              goto LABEL_80;
            }
          }
          else if ( a5 && ATL::CRegParser::HasSubKeys(v21, v31[0]) )
          {
            if ( ATL::CRegParser::CanForceRemoveKey(v21, v34) && v14 )
              ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)v31, v34);
          }
          else
          {
            HasSubKeys = ATL::CRegParser::HasSubKeys(v21, v31[0]);
            v24 = ATL::CRegKey::Close((ATL::CRegKey *)v31);
            if ( v24 )
            {
              v16 = v24;
              goto LABEL_65;
            }
            if ( v14 && !HasSubKeys )
            {
              v29 = 0;
              v30 = 0;
              hKey = a3;
              v15 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)&hKey, v34);
              hKey = 0;
              if ( v15 )
                goto LABEL_81;
              ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
            }
          }
        }
      }
    }
    v10 = ATL::CRegParser::NextToken(v8, ValueName);
    if ( v10 < 0 )
      goto LABEL_80;
    v10 = ATL::CRegParser::NextToken(v8, v7);
    if ( v10 < 0 )
      goto LABEL_80;
    if ( *v7 != 61 )
      goto LABEL_79;
    if ( v5 )
    {
      v29 = 0;
      v30 = 0;
      hKey = a3;
      v13 = ATL::CRegParser::AddValue(v8, &hKey, ValueName, v7);
      v10 = v13;
      hKey = 0;
LABEL_15:
      if ( v13 < 0 )
        goto LABEL_82;
      ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
      goto LABEL_41;
    }
    if ( a5 || !v14 )
      goto LABEL_31;
    hKey = 0;
    v29 = 0;
    v30 = 0;
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
LABEL_81:
  v10 = ATL::AtlHresultFromWin32(v15);
LABEL_82:
  ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_80:
  ATL::CRegKey::Close((ATL::CRegKey *)v31);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180093290  push    rbp
0x180093292  push    rbx
0x180093293  push    rsi
0x180093294  push    rdi
0x180093295  push    r12
0x180093297  push    r13
0x180093299  push    r14
0x18009329b  push    r15
0x18009329d  lea     rbp, [rsp-21C8h]
0x1800932a5  mov     eax, 22C8h
0x1800932aa  call    _alloca_probe
0x1800932af  sub     rsp, rax
0x1800932b2  mov     rax, cs:__security_cookie
0x1800932b9  xor     rax, rsp
0x1800932bc  mov     [rbp+2200h+var_50], rax
0x1800932c3  mov     r15d, r9d
0x1800932c6  mov     [rsp+2300h+var_22B0], r9d
0x1800932cb  mov     r13, r8
0x1800932ce  mov     rdi, rdx
0x1800932d1  mov     rsi, rcx
0x1800932d4  xor     r14d, r14d
0x1800932d7  mov     [rsp+2300h+var_2290], r14
0x1800932dc  mov     [rsp+2300h+var_2288], r14
0x1800932e1  mov     [rbp+2200h+var_2280], r14
0x1800932e5  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800932ea  test    eax, eax
0x1800932ec  mov     ebx, eax
0x1800932ee  js      loc_18009381F
0x1800932f4  xor     r12d, r12d
0x1800932f7  cmp     word ptr [rdi], 7Dh ; '}'
0x1800932fb  jz      loc_18009381F
0x180093301  lea     rdx, aDelete; "Delete"
0x180093308  mov     rcx, rdi; lpString1
0x18009330b  call    cs:__imp_lstrcmpiW
0x180093311  mov     r14d, eax
0x180093314  lea     rdx, aForceremove; "ForceRemove"
0x18009331b  mov     rcx, rdi; lpString1
0x18009331e  call    cs:__imp_lstrcmpiW
0x180093324  test    eax, eax
0x180093326  jz      short loc_180093331
0x180093328  test    r14d, r14d
0x18009332b  jnz     loc_1800933E2
0x180093331  mov     rdx, rdi; unsigned __int16 *
0x180093334  mov     rcx, rsi; this
0x180093337  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18009333c  mov     ebx, eax
0x18009333e  test    eax, eax
0x180093340  js      loc_18009381F
0x180093346  test    r15d, r15d
0x180093349  jz      loc_1800933E2
0x18009334f  mov     [rsp+2300h+hKey], r12
0x180093354  mov     [rsp+2300h+var_22A0], r12
0x180093359  mov     [rsp+2300h+var_2298], r12
0x18009335e  mov     edx, 5Ch ; '\'; unsigned __int16
0x180093363  mov     rcx, rdi; lpsz
0x180093366  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x18009336b  test    rax, rax
0x18009336e  jnz     loc_180093810
0x180093374  mov     rdx, rdi; unsigned __int16 *
0x180093377  call    ?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEBG@Z; ATL::CRegParser::CanForceRemoveKey(ushort const *)
0x18009337c  test    eax, eax
0x18009337e  jz      short loc_180093397
0x180093380  mov     [rsp+2300h+hKey], r13
0x180093385  mov     rdx, rdi; unsigned __int16 *
0x180093388  lea     rcx, [rsp+2300h+hKey]; this
0x18009338d  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180093392  mov     [rsp+2300h+hKey], r12
0x180093397  test    r14d, r14d
0x18009339a  jnz     short loc_1800933D8
0x18009339c  mov     rdx, rdi; unsigned __int16 *
0x18009339f  mov     rcx, rsi; this
0x1800933a2  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800933a7  mov     ebx, eax
0x1800933a9  xor     r14d, r14d
0x1800933ac  test    eax, eax
0x1800933ae  js      loc_18009380E
0x1800933b4  mov     rdx, rdi; unsigned __int16 *
0x1800933b7  mov     rcx, rsi; this
0x1800933ba  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x1800933bf  mov     ebx, eax
0x1800933c1  test    eax, eax
0x1800933c3  lea     rcx, [rsp+2300h+hKey]; this
0x1800933c8  js      loc_18009385C
0x1800933ce  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800933d3  jmp     loc_1800935FC
0x1800933d8  lea     rcx, [rsp+2300h+hKey]; this
0x1800933dd  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800933e2  mov     r12d, 1
0x1800933e8  lea     rdx, aNoremove; "NoRemove"
0x1800933ef  mov     rcx, rdi; lpString1
0x1800933f2  call    cs:__imp_lstrcmpiW
0x1800933f8  xor     r14d, r14d
0x1800933fb  test    eax, eax
0x1800933fd  jnz     short loc_180093417
0x1800933ff  mov     r12d, r14d
0x180093402  mov     rdx, rdi; unsigned __int16 *
0x180093405  mov     rcx, rsi; this
0x180093408  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18009340d  mov     ebx, eax
0x18009340f  test    eax, eax
0x180093411  js      loc_18009381F
0x180093417  lea     rdx, aVal; "Val"
0x18009341e  mov     rcx, rdi; lpString1
0x180093421  call    cs:__imp_lstrcmpiW
0x180093427  test    eax, eax
0x180093429  jnz     loc_180093510
0x18009342f  lea     rdx, [rbp+2200h+ValueName]; unsigned __int16 *
0x180093436  mov     rcx, rsi; this
0x180093439  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18009343e  mov     ebx, eax
0x180093440  test    eax, eax
0x180093442  js      loc_18009381F
0x180093448  mov     rdx, rdi; unsigned __int16 *
0x18009344b  mov     rcx, rsi; this
0x18009344e  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180093453  mov     ebx, eax
0x180093455  test    eax, eax
0x180093457  js      loc_18009381F
0x18009345d  cmp     word ptr [rdi], 3Dh ; '='
0x180093461  jnz     loc_18009381A
0x180093467  test    r15d, r15d
0x18009346a  jz      short loc_18009349E
0x18009346c  mov     [rsp+2300h+var_22A0], r14
0x180093471  mov     [rsp+2300h+var_2298], r14
0x180093476  mov     [rsp+2300h+hKey], r13
0x18009347b  mov     r9, rdi; unsigned __int16 *
0x18009347e  lea     r8, [rbp+2200h+ValueName]; unsigned __int16 *
0x180093485  lea     rdx, [rsp+2300h+hKey]; struct ATL::CRegKey *
0x18009348a  mov     rcx, rsi; this
0x18009348d  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180093492  mov     ebx, eax
0x180093494  mov     [rsp+2300h+hKey], r14
0x180093499  jmp     loc_1800933C1
0x18009349e  cmp     [rbp+2200h+arg_20], r14d
0x1800934a5  jnz     short loc_180093500
0x1800934a7  test    r12d, r12d
0x1800934aa  jz      short loc_180093500
0x1800934ac  mov     [rsp+2300h+hKey], r14
0x1800934b1  mov     [rsp+2300h+var_22A0], r14
0x1800934b6  mov     [rsp+2300h+var_2298], r14
0x1800934bb  mov     r9d, 20006h; unsigned int
0x1800934c1  xor     r8d, r8d; lpSubKey
0x1800934c4  mov     rdx, r13; hKey
0x1800934c7  lea     rcx, [rsp+2300h+hKey]; this
0x1800934cc  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1800934d1  test    eax, eax
0x1800934d3  jnz     loc_18009384E
0x1800934d9  lea     rdx, [rbp+2200h+ValueName]; lpValueName
0x1800934e0  mov     rcx, [rsp+2300h+hKey]; hKey
0x1800934e5  call    cs:__imp_RegDeleteValueW
0x1800934eb  test    eax, 0FFFFFFFDh
0x1800934f0  jnz     loc_18009384E
0x1800934f6  lea     rcx, [rsp+2300h+hKey]; this
0x1800934fb  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180093500  mov     rdx, rdi; unsigned __int16 *
0x180093503  mov     rcx, rsi; this
0x180093506  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18009350b  jmp     loc_1800932EA
0x180093510  mov     edx, 5Ch ; '\'; unsigned __int16
0x180093515  mov     rcx, rdi; lpsz
0x180093518  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x18009351d  test    rax, rax
0x180093520  jnz     loc_18009381A
0x180093526  test    r15d, r15d
0x180093529  jz      loc_18009364B
0x18009352f  mov     ebx, 2001Fh
0x180093534  mov     r9d, ebx; unsigned int
0x180093537  mov     r8, rdi; lpSubKey
0x18009353a  mov     rdx, r13; hKey
0x18009353d  lea     rcx, [rsp+2300h+var_2290]; this
0x180093542  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180093547  test    eax, eax
0x180093549  jz      short loc_1800935C4
0x18009354b  lea     r9d, [rbx-6]; unsigned int
0x18009354f  mov     r8, rdi; lpSubKey
0x180093552  mov     rdx, r13; hKey
0x180093555  lea     rcx, [rsp+2300h+var_2290]; this
0x18009355a  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18009355f  test    eax, eax
0x180093561  jz      short loc_1800935C4
0x180093563  mov     [rbp+2200h+dwDisposition], r14d
0x180093567  mov     [rbp+2200h+var_2270], r14
0x18009356b  lea     rax, [rbp+2200h+dwDisposition]
0x18009356f  mov     [rsp+2300h+lpdwDisposition], rax; lpdwDisposition
0x180093574  lea     rax, [rbp+2200h+var_2270]
0x180093578  mov     [rsp+2300h+phkResult], rax; phkResult
0x18009357d  mov     [rsp+2300h+lpSecurityAttributes], r14; lpSecurityAttributes
0x180093582  mov     [rsp+2300h+samDesired], ebx; samDesired
0x180093586  mov     dword ptr [rsp+2300h+dwOptions], r14d; dwOptions
0x18009358b  xor     r9d, r9d; lpClass
0x18009358e  xor     r8d, r8d; Reserved
0x180093591  mov     rdx, rdi; lpSubKey
0x180093594  mov     rcx, r13; hKey
0x180093597  call    cs:__imp_RegCreateKeyExW
0x18009359d  mov     ecx, eax
0x18009359f  test    eax, eax
0x1800935a1  jnz     loc_18009374B
0x1800935a7  lea     rcx, [rsp+2300h+var_2290]; this
0x1800935ac  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800935b1  mov     ecx, eax
0x1800935b3  mov     rax, [rbp+2200h+var_2270]
0x1800935b7  mov     [rsp+2300h+var_2290], rax
0x1800935bc  test    ecx, ecx
0x1800935be  jnz     loc_18009374B
0x1800935c4  mov     rdx, rdi; unsigned __int16 *
0x1800935c7  mov     rcx, rsi; this
0x1800935ca  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800935cf  mov     ebx, eax
0x1800935d1  test    eax, eax
0x1800935d3  js      loc_18009381F
0x1800935d9  cmp     word ptr [rdi], 3Dh ; '='
0x1800935dd  jnz     short loc_1800935FC
0x1800935df  mov     r9, rdi; unsigned __int16 *
0x1800935e2  xor     r8d, r8d; unsigned __int16 *
0x1800935e5  lea     rdx, [rsp+2300h+var_2290]; struct ATL::CRegKey *
0x1800935ea  mov     rcx, rsi; this
0x1800935ed  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x1800935f2  mov     ebx, eax
0x1800935f4  test    eax, eax
0x1800935f6  js      loc_18009381F
0x1800935fc  cmp     word ptr [rdi], 7Bh ; '{'
0x180093600  jnz     loc_1800932F4
0x180093606  or      rax, 0FFFFFFFFFFFFFFFFh
0x18009360a  inc     rax
0x18009360d  cmp     [rdi+rax*2], r14w
0x180093612  jnz     short loc_18009360A
0x180093614  cmp     rax, 1
0x180093618  jnz     loc_1800932F4
0x18009361e  mov     dword ptr [rsp+2300h+dwOptions], r14d; int
0x180093623  mov     r9d, r15d; int
0x180093626  mov     r8, [rsp+2300h+var_2290]; HKEY
0x18009362b  mov     rdx, rdi; unsigned __int16 *
0x18009362e  mov     rcx, rsi; this
0x180093631  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180093636  mov     ebx, eax
0x180093638  test    eax, eax
0x18009363a  js      loc_18009381F
0x180093640  mov     rdx, rdi
0x180093643  mov     rcx, rsi
0x180093646  jmp     loc_1800932E5
0x18009364b  cmp     [rbp+2200h+arg_20], r14d
0x180093652  jnz     short loc_18009366F
0x180093654  mov     r9d, 20019h; unsigned int
0x18009365a  mov     r8, rdi; lpSubKey
0x18009365d  mov     rdx, r13; hKey
0x180093660  lea     rcx, [rsp+2300h+var_2290]; this
0x180093665  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18009366a  mov     r14d, eax
0x18009366d  jmp     short loc_180093675
0x18009366f  mov     r14d, 2
0x180093675  mov     r15d, 1
0x18009367b  test    r14d, r14d
0x18009367e  cmovz   r15d, [rbp+2200h+arg_20]
0x180093686  or      r9, 0FFFFFFFFFFFFFFFFh
0x18009368a  mov     r8, rdi
0x18009368d  mov     edx, 104h
0x180093692  lea     rcx, [rbp+2200h+var_2260]
0x180093696  call    cs:__imp__o_wcsncpy_s
0x18009369c  mov     ecx, eax; int
0x18009369e  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800936a3  mov     rdx, rdi; unsigned __int16 *
0x1800936a6  mov     rcx, rsi; this
0x1800936a9  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800936ae  mov     ebx, eax
0x1800936b0  test    eax, eax
0x1800936b2  js      loc_18009381F
0x1800936b8  mov     rdx, rdi; unsigned __int16 *
0x1800936bb  mov     rcx, rsi; this
0x1800936be  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x1800936c3  mov     ebx, eax
0x1800936c5  xor     ecx, ecx
0x1800936c7  test    eax, eax
0x1800936c9  js      loc_18009381F
0x1800936cf  cmp     word ptr [rdi], 7Bh ; '{'
0x1800936d3  jnz     short loc_180093724
0x1800936d5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800936d9  inc     rax
0x1800936dc  cmp     [rdi+rax*2], cx
0x1800936e0  jnz     short loc_1800936D9
0x1800936e2  cmp     rax, 1
0x1800936e6  jnz     short loc_180093724
0x1800936e8  mov     dword ptr [rsp+2300h+dwOptions], r15d; int
0x1800936ed  xor     r9d, r9d; int
0x1800936f0  mov     r8, [rsp+2300h+var_2290]; HKEY
0x1800936f5  mov     rdx, rdi; unsigned __int16 *
0x1800936f8  mov     rcx, rsi; this
0x1800936fb  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180093700  mov     ebx, eax
0x180093702  test    eax, eax
0x180093704  jns     short loc_18009370F
0x180093706  test    r15d, r15d
0x180093709  jz      loc_18009381F
0x18009370f  mov     rdx, rdi; unsigned __int16 *
0x180093712  mov     rcx, rsi; this
0x180093715  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18009371a  mov     ebx, eax
0x18009371c  test    eax, eax
0x18009371e  js      loc_18009381F
0x180093724  cmp     r14d, 2
0x180093728  mov     r15d, [rsp+2300h+var_22B0]
  ... truncated ...
```
