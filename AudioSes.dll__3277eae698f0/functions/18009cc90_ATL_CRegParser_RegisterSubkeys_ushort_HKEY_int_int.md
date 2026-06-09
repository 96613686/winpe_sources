# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x18009cc90`
- end: `0x18009d269`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1497`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, registry_config`

## callers

- `0x18009c96c`
- `0x18009cc90`

## callees

- `0x180087e80`
- `0x18008c518`
- `0x18008c9c0`
- `0x18008cbb0`
- `0x18008d964`
- `0x18009aafc`
- `0x18009b194`
- `0x18009b278`
- `0x18009be2c`
- `0x18009bf68`
- `0x18009c858`
- `0x18009cc90`
- `0x18009d5a0`
- `0x18009d670`
- `0x18011ddd0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18009d096`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18009d096`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18009cf97`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18009cf97`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18009cee5`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18009cee5`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18009cd0b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18009cd1e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18009cdf2`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18009ce21`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18009cd0b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18009cd1e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18009cdf2`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18009ce21`

## string_xrefs

- `0x18009cd14`: `ForceRemove`
- `0x18009cde8`: `NoRemove`
- `0x18009cd01`: `Delete`

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
0x18009cc90  push    rbp
0x18009cc92  push    rbx
0x18009cc93  push    rsi
0x18009cc94  push    rdi
0x18009cc95  push    r12
0x18009cc97  push    r13
0x18009cc99  push    r14
0x18009cc9b  push    r15
0x18009cc9d  lea     rbp, [rsp-21C8h]
0x18009cca5  mov     eax, 22C8h
0x18009ccaa  call    _alloca_probe
0x18009ccaf  sub     rsp, rax
0x18009ccb2  mov     rax, cs:__security_cookie
0x18009ccb9  xor     rax, rsp
0x18009ccbc  mov     [rbp+2200h+var_50], rax
0x18009ccc3  mov     r15d, r9d
0x18009ccc6  mov     [rsp+2300h+var_22B0], r9d
0x18009cccb  mov     r13, r8
0x18009ccce  mov     rdi, rdx
0x18009ccd1  mov     rsi, rcx
0x18009ccd4  xor     r14d, r14d
0x18009ccd7  mov     [rsp+2300h+var_2290], r14
0x18009ccdc  mov     [rsp+2300h+var_2288], r14
0x18009cce1  mov     [rbp+2200h+var_2280], r14
0x18009cce5  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18009ccea  test    eax, eax
0x18009ccec  mov     ebx, eax
0x18009ccee  js      loc_18009D21D
0x18009ccf4  xor     r12d, r12d
0x18009ccf7  cmp     word ptr [rdi], 7Dh ; '}'
0x18009ccfb  jz      loc_18009D21D
0x18009cd01  lea     rdx, aDelete; "Delete"
0x18009cd08  mov     rcx, rdi; lpString1
0x18009cd0b  call    cs:__imp_lstrcmpiW
0x18009cd11  mov     r14d, eax
0x18009cd14  lea     rdx, aForceremove; "ForceRemove"
0x18009cd1b  mov     rcx, rdi; lpString1
0x18009cd1e  call    cs:__imp_lstrcmpiW
0x18009cd24  test    eax, eax
0x18009cd26  jz      short loc_18009CD31
0x18009cd28  test    r14d, r14d
0x18009cd2b  jnz     loc_18009CDE2
0x18009cd31  mov     rdx, rdi; unsigned __int16 *
0x18009cd34  mov     rcx, rsi; this
0x18009cd37  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18009cd3c  mov     ebx, eax
0x18009cd3e  test    eax, eax
0x18009cd40  js      loc_18009D21D
0x18009cd46  test    r15d, r15d
0x18009cd49  jz      loc_18009CDE2
0x18009cd4f  mov     [rsp+2300h+hKey], r12
0x18009cd54  mov     [rsp+2300h+var_22A0], r12
0x18009cd59  mov     [rsp+2300h+var_2298], r12
0x18009cd5e  mov     edx, 5Ch ; '\'; unsigned __int16
0x18009cd63  mov     rcx, rdi; lpsz
0x18009cd66  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x18009cd6b  test    rax, rax
0x18009cd6e  jnz     loc_18009D20E
0x18009cd74  mov     rdx, rdi; unsigned __int16 *
0x18009cd77  call    ?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEBG@Z; ATL::CRegParser::CanForceRemoveKey(ushort const *)
0x18009cd7c  test    eax, eax
0x18009cd7e  jz      short loc_18009CD97
0x18009cd80  mov     [rsp+2300h+hKey], r13
0x18009cd85  mov     rdx, rdi; unsigned __int16 *
0x18009cd88  lea     rcx, [rsp+2300h+hKey]; this
0x18009cd8d  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x18009cd92  mov     [rsp+2300h+hKey], r12
0x18009cd97  test    r14d, r14d
0x18009cd9a  jnz     short loc_18009CDD8
0x18009cd9c  mov     rdx, rdi; unsigned __int16 *
0x18009cd9f  mov     rcx, rsi; this
0x18009cda2  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18009cda7  mov     ebx, eax
0x18009cda9  xor     r14d, r14d
0x18009cdac  test    eax, eax
0x18009cdae  js      loc_18009D255
0x18009cdb4  mov     rdx, rdi; unsigned __int16 *
0x18009cdb7  mov     rcx, rsi; this
0x18009cdba  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18009cdbf  mov     ebx, eax
0x18009cdc1  test    eax, eax
0x18009cdc3  lea     rcx, [rsp+2300h+hKey]; this
0x18009cdc8  js      loc_18009D25A
0x18009cdce  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18009cdd3  jmp     loc_18009CFFC
0x18009cdd8  lea     rcx, [rsp+2300h+hKey]; this
0x18009cddd  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18009cde2  mov     r12d, 1
0x18009cde8  lea     rdx, aNoremove; "NoRemove"
0x18009cdef  mov     rcx, rdi; lpString1
0x18009cdf2  call    cs:__imp_lstrcmpiW
0x18009cdf8  xor     r14d, r14d
0x18009cdfb  test    eax, eax
0x18009cdfd  jnz     short loc_18009CE17
0x18009cdff  mov     r12d, r14d
0x18009ce02  mov     rdx, rdi; unsigned __int16 *
0x18009ce05  mov     rcx, rsi; this
0x18009ce08  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18009ce0d  mov     ebx, eax
0x18009ce0f  test    eax, eax
0x18009ce11  js      loc_18009D21D
0x18009ce17  lea     rdx, aVal; "Val"
0x18009ce1e  mov     rcx, rdi; lpString1
0x18009ce21  call    cs:__imp_lstrcmpiW
0x18009ce27  test    eax, eax
0x18009ce29  jnz     loc_18009CF10
0x18009ce2f  lea     rdx, [rbp+2200h+ValueName]; unsigned __int16 *
0x18009ce36  mov     rcx, rsi; this
0x18009ce39  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18009ce3e  mov     ebx, eax
0x18009ce40  test    eax, eax
0x18009ce42  js      loc_18009D21D
0x18009ce48  mov     rdx, rdi; unsigned __int16 *
0x18009ce4b  mov     rcx, rsi; this
0x18009ce4e  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18009ce53  mov     ebx, eax
0x18009ce55  test    eax, eax
0x18009ce57  js      loc_18009D21D
0x18009ce5d  cmp     word ptr [rdi], 3Dh ; '='
0x18009ce61  jnz     loc_18009D218
0x18009ce67  test    r15d, r15d
0x18009ce6a  jz      short loc_18009CE9E
0x18009ce6c  mov     [rsp+2300h+var_22A0], r14
0x18009ce71  mov     [rsp+2300h+var_2298], r14
0x18009ce76  mov     [rsp+2300h+hKey], r13
0x18009ce7b  mov     r9, rdi; unsigned __int16 *
0x18009ce7e  lea     r8, [rbp+2200h+ValueName]; unsigned __int16 *
0x18009ce85  lea     rdx, [rsp+2300h+hKey]; struct ATL::CRegKey *
0x18009ce8a  mov     rcx, rsi; this
0x18009ce8d  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x18009ce92  mov     ebx, eax
0x18009ce94  mov     [rsp+2300h+hKey], r14
0x18009ce99  jmp     loc_18009CDC1
0x18009ce9e  cmp     [rbp+2200h+arg_20], r14d
0x18009cea5  jnz     short loc_18009CF00
0x18009cea7  test    r12d, r12d
0x18009ceaa  jz      short loc_18009CF00
0x18009ceac  mov     [rsp+2300h+hKey], r14
0x18009ceb1  mov     [rsp+2300h+var_22A0], r14
0x18009ceb6  mov     [rsp+2300h+var_2298], r14
0x18009cebb  mov     r9d, 20006h; unsigned int
0x18009cec1  xor     r8d, r8d; lpSubKey
0x18009cec4  mov     rdx, r13; hKey
0x18009cec7  lea     rcx, [rsp+2300h+hKey]; this
0x18009cecc  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18009ced1  test    eax, eax
0x18009ced3  jnz     loc_18009D24C
0x18009ced9  lea     rdx, [rbp+2200h+ValueName]; lpValueName
0x18009cee0  mov     rcx, [rsp+2300h+hKey]; hKey
0x18009cee5  call    cs:__imp_RegDeleteValueW
0x18009ceeb  test    eax, 0FFFFFFFDh
0x18009cef0  jnz     loc_18009D24C
0x18009cef6  lea     rcx, [rsp+2300h+hKey]; this
0x18009cefb  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18009cf00  mov     rdx, rdi; unsigned __int16 *
0x18009cf03  mov     rcx, rsi; this
0x18009cf06  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18009cf0b  jmp     loc_18009CCEA
0x18009cf10  mov     edx, 5Ch ; '\'; unsigned __int16
0x18009cf15  mov     rcx, rdi; lpsz
0x18009cf18  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x18009cf1d  test    rax, rax
0x18009cf20  jnz     loc_18009D218
0x18009cf26  test    r15d, r15d
0x18009cf29  jz      loc_18009D04B
0x18009cf2f  mov     ebx, 2001Fh
0x18009cf34  mov     r9d, ebx; unsigned int
0x18009cf37  mov     r8, rdi; lpSubKey
0x18009cf3a  mov     rdx, r13; hKey
0x18009cf3d  lea     rcx, [rsp+2300h+var_2290]; this
0x18009cf42  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18009cf47  test    eax, eax
0x18009cf49  jz      short loc_18009CFC4
0x18009cf4b  lea     r9d, [rbx-6]; unsigned int
0x18009cf4f  mov     r8, rdi; lpSubKey
0x18009cf52  mov     rdx, r13; hKey
0x18009cf55  lea     rcx, [rsp+2300h+var_2290]; this
0x18009cf5a  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18009cf5f  test    eax, eax
0x18009cf61  jz      short loc_18009CFC4
0x18009cf63  mov     [rbp+2200h+dwDisposition], r14d
0x18009cf67  mov     [rbp+2200h+var_2270], r14
0x18009cf6b  lea     rax, [rbp+2200h+dwDisposition]
0x18009cf6f  mov     [rsp+2300h+lpdwDisposition], rax; lpdwDisposition
0x18009cf74  lea     rax, [rbp+2200h+var_2270]
0x18009cf78  mov     [rsp+2300h+phkResult], rax; phkResult
0x18009cf7d  mov     [rsp+2300h+lpSecurityAttributes], r14; lpSecurityAttributes
0x18009cf82  mov     [rsp+2300h+samDesired], ebx; samDesired
0x18009cf86  mov     [rsp+2300h+dwOptions], r14d; dwOptions
0x18009cf8b  xor     r9d, r9d; lpClass
0x18009cf8e  xor     r8d, r8d; Reserved
0x18009cf91  mov     rdx, rdi; lpSubKey
0x18009cf94  mov     rcx, r13; hKey
0x18009cf97  call    cs:__imp_RegCreateKeyExW
0x18009cf9d  mov     ecx, eax
0x18009cf9f  test    eax, eax
0x18009cfa1  jnz     loc_18009D14B
0x18009cfa7  lea     rcx, [rsp+2300h+var_2290]; this
0x18009cfac  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18009cfb1  mov     ecx, eax
0x18009cfb3  mov     rax, [rbp+2200h+var_2270]
0x18009cfb7  mov     [rsp+2300h+var_2290], rax
0x18009cfbc  test    ecx, ecx
0x18009cfbe  jnz     loc_18009D14B
0x18009cfc4  mov     rdx, rdi; unsigned __int16 *
0x18009cfc7  mov     rcx, rsi; this
0x18009cfca  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18009cfcf  mov     ebx, eax
0x18009cfd1  test    eax, eax
0x18009cfd3  js      loc_18009D21D
0x18009cfd9  cmp     word ptr [rdi], 3Dh ; '='
0x18009cfdd  jnz     short loc_18009CFFC
0x18009cfdf  mov     r9, rdi; unsigned __int16 *
0x18009cfe2  xor     r8d, r8d; unsigned __int16 *
0x18009cfe5  lea     rdx, [rsp+2300h+var_2290]; struct ATL::CRegKey *
0x18009cfea  mov     rcx, rsi; this
0x18009cfed  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x18009cff2  mov     ebx, eax
0x18009cff4  test    eax, eax
0x18009cff6  js      loc_18009D21D
0x18009cffc  cmp     word ptr [rdi], 7Bh ; '{'
0x18009d000  jnz     loc_18009CCF4
0x18009d006  or      rax, 0FFFFFFFFFFFFFFFFh
0x18009d00a  inc     rax
0x18009d00d  cmp     [rdi+rax*2], r14w
0x18009d012  jnz     short loc_18009D00A
0x18009d014  cmp     rax, 1
0x18009d018  jnz     loc_18009CCF4
0x18009d01e  mov     [rsp+2300h+dwOptions], r14d; int
0x18009d023  mov     r9d, r15d; int
0x18009d026  mov     r8, [rsp+2300h+var_2290]; HKEY
0x18009d02b  mov     rdx, rdi; unsigned __int16 *
0x18009d02e  mov     rcx, rsi; this
0x18009d031  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18009d036  mov     ebx, eax
0x18009d038  test    eax, eax
0x18009d03a  js      loc_18009D21D
0x18009d040  mov     rdx, rdi
0x18009d043  mov     rcx, rsi
0x18009d046  jmp     loc_18009CCE5
0x18009d04b  cmp     [rbp+2200h+arg_20], r14d
0x18009d052  jnz     short loc_18009D06F
0x18009d054  mov     r9d, 20019h; unsigned int
0x18009d05a  mov     r8, rdi; lpSubKey
0x18009d05d  mov     rdx, r13; hKey
0x18009d060  lea     rcx, [rsp+2300h+var_2290]; this
0x18009d065  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18009d06a  mov     r14d, eax
0x18009d06d  jmp     short loc_18009D075
0x18009d06f  mov     r14d, 2
0x18009d075  mov     r15d, 1
0x18009d07b  test    r14d, r14d
0x18009d07e  cmovz   r15d, [rbp+2200h+arg_20]
0x18009d086  or      r9, 0FFFFFFFFFFFFFFFFh
0x18009d08a  mov     r8, rdi
0x18009d08d  mov     edx, 104h
0x18009d092  lea     rcx, [rbp+2200h+var_2260]
0x18009d096  call    cs:__imp__o_wcsncpy_s
0x18009d09c  mov     ecx, eax; int
0x18009d09e  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18009d0a3  mov     rdx, rdi; unsigned __int16 *
0x18009d0a6  mov     rcx, rsi; this
0x18009d0a9  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18009d0ae  mov     ebx, eax
0x18009d0b0  test    eax, eax
0x18009d0b2  js      loc_18009D21D
0x18009d0b8  mov     rdx, rdi; unsigned __int16 *
0x18009d0bb  mov     rcx, rsi; this
0x18009d0be  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18009d0c3  mov     ebx, eax
0x18009d0c5  xor     ecx, ecx
0x18009d0c7  test    eax, eax
0x18009d0c9  js      loc_18009D21D
0x18009d0cf  cmp     word ptr [rdi], 7Bh ; '{'
0x18009d0d3  jnz     short loc_18009D124
0x18009d0d5  or      rax, 0FFFFFFFFFFFFFFFFh
0x18009d0d9  inc     rax
0x18009d0dc  cmp     [rdi+rax*2], cx
0x18009d0e0  jnz     short loc_18009D0D9
0x18009d0e2  cmp     rax, 1
0x18009d0e6  jnz     short loc_18009D124
0x18009d0e8  mov     [rsp+2300h+dwOptions], r15d; int
0x18009d0ed  xor     r9d, r9d; int
0x18009d0f0  mov     r8, [rsp+2300h+var_2290]; HKEY
0x18009d0f5  mov     rdx, rdi; unsigned __int16 *
0x18009d0f8  mov     rcx, rsi; this
0x18009d0fb  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18009d100  mov     ebx, eax
0x18009d102  test    eax, eax
0x18009d104  jns     short loc_18009D10F
0x18009d106  test    r15d, r15d
0x18009d109  jz      loc_18009D21D
0x18009d10f  mov     rdx, rdi; unsigned __int16 *
0x18009d112  mov     rcx, rsi; this
0x18009d115  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18009d11a  mov     ebx, eax
0x18009d11c  test    eax, eax
0x18009d11e  js      loc_18009D21D
0x18009d124  cmp     r14d, 2
0x18009d128  mov     r15d, [rsp+2300h+var_22B0]
  ... truncated ...
```
