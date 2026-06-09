# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x18000e810`
- end: `0x18000ede9`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1497`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, registry_config`

## callers

- `0x18000e458`
- `0x18000e810`

## callees

- `0x180001720`
- `0x1800096cc`
- `0x180009da8`
- `0x180009e18`
- `0x180009f24`
- `0x18000a1a0`
- `0x18000a880`
- `0x18000bd00`
- `0x18000d0c0`
- `0x18000d354`
- `0x18000e344`
- `0x18000e810`
- `0x18000fb80`
- `0x18000fe0c`
- `0x1800142b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18000ec16`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18000ec16`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000ea65`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000ea65`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000eb17`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000eb17`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000e88b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000e89e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000e972`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000e9a1`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000e88b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000e89e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000e972`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000e9a1`

## string_xrefs

- `0x18000e894`: `ForceRemove`
- `0x18000e968`: `NoRemove`
- `0x18000e881`: `Delete`

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
          v29 = 0;
          v30 = 0;
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
          goto LABEL_79;
        if ( *v7 == 61 )
        {
          v10 = ATL::CRegParser::AddValue(v8, v31, 0, v7);
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
            v10 = ATL::CRegParser::RegisterSubkeys(v8, v7, v31[0], v5, 0);
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
          v18 = ATL::CRegKey::Open((ATL::CRegKey *)v31, a3, v7, 0x20019u);
        v19 = 1;
        if ( !v18 )
          v19 = a5;
        v20 = _o_wcsncpy_s(v34, 260, v7, -1, dwOptions);
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
            v10 = ATL::CRegParser::RegisterSubkeys(v8, v7, v31[0], 0, v19);
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
      v29 = 0;
      v30 = 0;
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
LABEL_80:
  v10 = ATL::AtlHresultFromWin32(v15);
LABEL_81:
  ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_79:
  ATL::CRegKey::Close((ATL::CRegKey *)v31);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18000e810  push    rbp
0x18000e812  push    rbx
0x18000e813  push    rsi
0x18000e814  push    rdi
0x18000e815  push    r12
0x18000e817  push    r13
0x18000e819  push    r14
0x18000e81b  push    r15
0x18000e81d  lea     rbp, [rsp-21C8h]
0x18000e825  mov     eax, 22C8h
0x18000e82a  call    _alloca_probe
0x18000e82f  sub     rsp, rax
0x18000e832  mov     rax, cs:__security_cookie
0x18000e839  xor     rax, rsp
0x18000e83c  mov     [rbp+2200h+var_50], rax
0x18000e843  mov     r15d, r9d
0x18000e846  mov     [rsp+2300h+var_22B0], r9d
0x18000e84b  mov     r13, r8
0x18000e84e  mov     rdi, rdx
0x18000e851  mov     rsi, rcx
0x18000e854  xor     r14d, r14d
0x18000e857  mov     [rsp+2300h+var_2290], r14
0x18000e85c  mov     [rsp+2300h+var_2288], r14
0x18000e861  mov     [rbp+2200h+var_2280], r14
0x18000e865  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000e86a  test    eax, eax
0x18000e86c  mov     ebx, eax
0x18000e86e  js      loc_18000ED9D
0x18000e874  xor     r12d, r12d
0x18000e877  cmp     word ptr [rdi], 7Dh ; '}'
0x18000e87b  jz      loc_18000ED9D
0x18000e881  lea     rdx, aDelete; "Delete"
0x18000e888  mov     rcx, rdi; lpString1
0x18000e88b  call    cs:__imp_lstrcmpiW
0x18000e891  mov     r14d, eax
0x18000e894  lea     rdx, aForceremove; "ForceRemove"
0x18000e89b  mov     rcx, rdi; lpString1
0x18000e89e  call    cs:__imp_lstrcmpiW
0x18000e8a4  test    eax, eax
0x18000e8a6  jz      short loc_18000E8B1
0x18000e8a8  test    r14d, r14d
0x18000e8ab  jnz     loc_18000E962
0x18000e8b1  mov     rdx, rdi; unsigned __int16 *
0x18000e8b4  mov     rcx, rsi; this
0x18000e8b7  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000e8bc  mov     ebx, eax
0x18000e8be  test    eax, eax
0x18000e8c0  js      loc_18000ED9D
0x18000e8c6  test    r15d, r15d
0x18000e8c9  jz      loc_18000E962
0x18000e8cf  mov     [rsp+2300h+hKey], r12
0x18000e8d4  mov     [rsp+2300h+var_22A0], r12
0x18000e8d9  mov     [rsp+2300h+var_2298], r12
0x18000e8de  mov     edx, 5Ch ; '\'; unsigned __int16
0x18000e8e3  mov     rcx, rdi; lpsz
0x18000e8e6  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x18000e8eb  test    rax, rax
0x18000e8ee  jnz     loc_18000ED8E
0x18000e8f4  mov     rdx, rdi; unsigned __int16 *
0x18000e8f7  call    ?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEBG@Z; ATL::CRegParser::CanForceRemoveKey(ushort const *)
0x18000e8fc  test    eax, eax
0x18000e8fe  jz      short loc_18000E917
0x18000e900  mov     [rsp+2300h+hKey], r13
0x18000e905  mov     rdx, rdi; unsigned __int16 *
0x18000e908  lea     rcx, [rsp+2300h+hKey]; this
0x18000e90d  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x18000e912  mov     [rsp+2300h+hKey], r12
0x18000e917  test    r14d, r14d
0x18000e91a  jnz     short loc_18000E958
0x18000e91c  mov     rdx, rdi; unsigned __int16 *
0x18000e91f  mov     rcx, rsi; this
0x18000e922  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000e927  mov     ebx, eax
0x18000e929  xor     r14d, r14d
0x18000e92c  test    eax, eax
0x18000e92e  js      loc_18000EDD5
0x18000e934  mov     rdx, rdi; unsigned __int16 *
0x18000e937  mov     rcx, rsi; this
0x18000e93a  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18000e93f  mov     ebx, eax
0x18000e941  test    eax, eax
0x18000e943  lea     rcx, [rsp+2300h+hKey]; this
0x18000e948  js      loc_18000EDDA
0x18000e94e  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000e953  jmp     loc_18000EB7C
0x18000e958  lea     rcx, [rsp+2300h+hKey]; this
0x18000e95d  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000e962  mov     r12d, 1
0x18000e968  lea     rdx, aNoremove; "NoRemove"
0x18000e96f  mov     rcx, rdi; lpString1
0x18000e972  call    cs:__imp_lstrcmpiW
0x18000e978  xor     r14d, r14d
0x18000e97b  test    eax, eax
0x18000e97d  jnz     short loc_18000E997
0x18000e97f  mov     r12d, r14d
0x18000e982  mov     rdx, rdi; unsigned __int16 *
0x18000e985  mov     rcx, rsi; this
0x18000e988  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000e98d  mov     ebx, eax
0x18000e98f  test    eax, eax
0x18000e991  js      loc_18000ED9D
0x18000e997  lea     rdx, aVal; "Val"
0x18000e99e  mov     rcx, rdi; lpString1
0x18000e9a1  call    cs:__imp_lstrcmpiW
0x18000e9a7  test    eax, eax
0x18000e9a9  jnz     loc_18000EA90
0x18000e9af  lea     rdx, [rbp+2200h+ValueName]; unsigned __int16 *
0x18000e9b6  mov     rcx, rsi; this
0x18000e9b9  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000e9be  mov     ebx, eax
0x18000e9c0  test    eax, eax
0x18000e9c2  js      loc_18000ED9D
0x18000e9c8  mov     rdx, rdi; unsigned __int16 *
0x18000e9cb  mov     rcx, rsi; this
0x18000e9ce  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000e9d3  mov     ebx, eax
0x18000e9d5  test    eax, eax
0x18000e9d7  js      loc_18000ED9D
0x18000e9dd  cmp     word ptr [rdi], 3Dh ; '='
0x18000e9e1  jnz     loc_18000ED98
0x18000e9e7  test    r15d, r15d
0x18000e9ea  jz      short loc_18000EA1E
0x18000e9ec  mov     [rsp+2300h+var_22A0], r14
0x18000e9f1  mov     [rsp+2300h+var_2298], r14
0x18000e9f6  mov     [rsp+2300h+hKey], r13
0x18000e9fb  mov     r9, rdi; unsigned __int16 *
0x18000e9fe  lea     r8, [rbp+2200h+ValueName]; unsigned __int16 *
0x18000ea05  lea     rdx, [rsp+2300h+hKey]; struct ATL::CRegKey *
0x18000ea0a  mov     rcx, rsi; this
0x18000ea0d  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x18000ea12  mov     ebx, eax
0x18000ea14  mov     [rsp+2300h+hKey], r14
0x18000ea19  jmp     loc_18000E941
0x18000ea1e  cmp     [rbp+2200h+arg_20], r14d
0x18000ea25  jnz     short loc_18000EA80
0x18000ea27  test    r12d, r12d
0x18000ea2a  jz      short loc_18000EA80
0x18000ea2c  mov     [rsp+2300h+hKey], r14
0x18000ea31  mov     [rsp+2300h+var_22A0], r14
0x18000ea36  mov     [rsp+2300h+var_2298], r14
0x18000ea3b  mov     r9d, 20006h; unsigned int
0x18000ea41  xor     r8d, r8d; lpSubKey
0x18000ea44  mov     rdx, r13; hKey
0x18000ea47  lea     rcx, [rsp+2300h+hKey]; this
0x18000ea4c  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18000ea51  test    eax, eax
0x18000ea53  jnz     loc_18000EDCC
0x18000ea59  lea     rdx, [rbp+2200h+ValueName]; lpValueName
0x18000ea60  mov     rcx, [rsp+2300h+hKey]; hKey
0x18000ea65  call    cs:__imp_RegDeleteValueW
0x18000ea6b  test    eax, 0FFFFFFFDh
0x18000ea70  jnz     loc_18000EDCC
0x18000ea76  lea     rcx, [rsp+2300h+hKey]; this
0x18000ea7b  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000ea80  mov     rdx, rdi; unsigned __int16 *
0x18000ea83  mov     rcx, rsi; this
0x18000ea86  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18000ea8b  jmp     loc_18000E86A
0x18000ea90  mov     edx, 5Ch ; '\'; unsigned __int16
0x18000ea95  mov     rcx, rdi; lpsz
0x18000ea98  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x18000ea9d  test    rax, rax
0x18000eaa0  jnz     loc_18000ED98
0x18000eaa6  test    r15d, r15d
0x18000eaa9  jz      loc_18000EBCB
0x18000eaaf  mov     ebx, 2001Fh
0x18000eab4  mov     r9d, ebx; unsigned int
0x18000eab7  mov     r8, rdi; lpSubKey
0x18000eaba  mov     rdx, r13; hKey
0x18000eabd  lea     rcx, [rsp+2300h+var_2290]; this
0x18000eac2  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18000eac7  test    eax, eax
0x18000eac9  jz      short loc_18000EB44
0x18000eacb  lea     r9d, [rbx-6]; unsigned int
0x18000eacf  mov     r8, rdi; lpSubKey
0x18000ead2  mov     rdx, r13; hKey
0x18000ead5  lea     rcx, [rsp+2300h+var_2290]; this
0x18000eada  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18000eadf  test    eax, eax
0x18000eae1  jz      short loc_18000EB44
0x18000eae3  mov     [rbp+2200h+dwDisposition], r14d
0x18000eae7  mov     [rbp+2200h+var_2270], r14
0x18000eaeb  lea     rax, [rbp+2200h+dwDisposition]
0x18000eaef  mov     [rsp+2300h+lpdwDisposition], rax; lpdwDisposition
0x18000eaf4  lea     rax, [rbp+2200h+var_2270]
0x18000eaf8  mov     [rsp+2300h+phkResult], rax; phkResult
0x18000eafd  mov     [rsp+2300h+lpSecurityAttributes], r14; lpSecurityAttributes
0x18000eb02  mov     [rsp+2300h+samDesired], ebx; samDesired
0x18000eb06  mov     dword ptr [rsp+2300h+dwOptions], r14d; dwOptions
0x18000eb0b  xor     r9d, r9d; lpClass
0x18000eb0e  xor     r8d, r8d; Reserved
0x18000eb11  mov     rdx, rdi; lpSubKey
0x18000eb14  mov     rcx, r13; hKey
0x18000eb17  call    cs:__imp_RegCreateKeyExW
0x18000eb1d  mov     ecx, eax
0x18000eb1f  test    eax, eax
0x18000eb21  jnz     loc_18000ECCB
0x18000eb27  lea     rcx, [rsp+2300h+var_2290]; this
0x18000eb2c  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000eb31  mov     ecx, eax
0x18000eb33  mov     rax, [rbp+2200h+var_2270]
0x18000eb37  mov     [rsp+2300h+var_2290], rax
0x18000eb3c  test    ecx, ecx
0x18000eb3e  jnz     loc_18000ECCB
0x18000eb44  mov     rdx, rdi; unsigned __int16 *
0x18000eb47  mov     rcx, rsi; this
0x18000eb4a  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000eb4f  mov     ebx, eax
0x18000eb51  test    eax, eax
0x18000eb53  js      loc_18000ED9D
0x18000eb59  cmp     word ptr [rdi], 3Dh ; '='
0x18000eb5d  jnz     short loc_18000EB7C
0x18000eb5f  mov     r9, rdi; unsigned __int16 *
0x18000eb62  xor     r8d, r8d; unsigned __int16 *
0x18000eb65  lea     rdx, [rsp+2300h+var_2290]; struct ATL::CRegKey *
0x18000eb6a  mov     rcx, rsi; this
0x18000eb6d  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x18000eb72  mov     ebx, eax
0x18000eb74  test    eax, eax
0x18000eb76  js      loc_18000ED9D
0x18000eb7c  cmp     word ptr [rdi], 7Bh ; '{'
0x18000eb80  jnz     loc_18000E874
0x18000eb86  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000eb8a  inc     rax
0x18000eb8d  cmp     [rdi+rax*2], r14w
0x18000eb92  jnz     short loc_18000EB8A
0x18000eb94  cmp     rax, 1
0x18000eb98  jnz     loc_18000E874
0x18000eb9e  mov     dword ptr [rsp+2300h+dwOptions], r14d; int
0x18000eba3  mov     r9d, r15d; int
0x18000eba6  mov     r8, [rsp+2300h+var_2290]; HKEY
0x18000ebab  mov     rdx, rdi; unsigned __int16 *
0x18000ebae  mov     rcx, rsi; this
0x18000ebb1  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18000ebb6  mov     ebx, eax
0x18000ebb8  test    eax, eax
0x18000ebba  js      loc_18000ED9D
0x18000ebc0  mov     rdx, rdi
0x18000ebc3  mov     rcx, rsi
0x18000ebc6  jmp     loc_18000E865
0x18000ebcb  cmp     [rbp+2200h+arg_20], r14d
0x18000ebd2  jnz     short loc_18000EBEF
0x18000ebd4  mov     r9d, 20019h; unsigned int
0x18000ebda  mov     r8, rdi; lpSubKey
0x18000ebdd  mov     rdx, r13; hKey
0x18000ebe0  lea     rcx, [rsp+2300h+var_2290]; this
0x18000ebe5  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18000ebea  mov     r14d, eax
0x18000ebed  jmp     short loc_18000EBF5
0x18000ebef  mov     r14d, 2
0x18000ebf5  mov     r15d, 1
0x18000ebfb  test    r14d, r14d
0x18000ebfe  cmovz   r15d, [rbp+2200h+arg_20]
0x18000ec06  or      r9, 0FFFFFFFFFFFFFFFFh
0x18000ec0a  mov     r8, rdi
0x18000ec0d  mov     edx, 104h
0x18000ec12  lea     rcx, [rbp+2200h+var_2260]
0x18000ec16  call    cs:__imp__o_wcsncpy_s
0x18000ec1c  mov     ecx, eax; int
0x18000ec1e  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18000ec23  mov     rdx, rdi; unsigned __int16 *
0x18000ec26  mov     rcx, rsi; this
0x18000ec29  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000ec2e  mov     ebx, eax
0x18000ec30  test    eax, eax
0x18000ec32  js      loc_18000ED9D
0x18000ec38  mov     rdx, rdi; unsigned __int16 *
0x18000ec3b  mov     rcx, rsi; this
0x18000ec3e  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18000ec43  mov     ebx, eax
0x18000ec45  xor     ecx, ecx
0x18000ec47  test    eax, eax
0x18000ec49  js      loc_18000ED9D
0x18000ec4f  cmp     word ptr [rdi], 7Bh ; '{'
0x18000ec53  jnz     short loc_18000ECA4
0x18000ec55  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000ec59  inc     rax
0x18000ec5c  cmp     [rdi+rax*2], cx
0x18000ec60  jnz     short loc_18000EC59
0x18000ec62  cmp     rax, 1
0x18000ec66  jnz     short loc_18000ECA4
0x18000ec68  mov     dword ptr [rsp+2300h+dwOptions], r15d; int
0x18000ec6d  xor     r9d, r9d; int
0x18000ec70  mov     r8, [rsp+2300h+var_2290]; HKEY
0x18000ec75  mov     rdx, rdi; unsigned __int16 *
0x18000ec78  mov     rcx, rsi; this
0x18000ec7b  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18000ec80  mov     ebx, eax
0x18000ec82  test    eax, eax
0x18000ec84  jns     short loc_18000EC8F
0x18000ec86  test    r15d, r15d
0x18000ec89  jz      loc_18000ED9D
0x18000ec8f  mov     rdx, rdi; unsigned __int16 *
0x18000ec92  mov     rcx, rsi; this
0x18000ec95  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000ec9a  mov     ebx, eax
0x18000ec9c  test    eax, eax
0x18000ec9e  js      loc_18000ED9D
0x18000eca4  cmp     r14d, 2
0x18000eca8  mov     r15d, [rsp+2300h+var_22B0]
  ... truncated ...
```
