# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x18083d2c8`
- end: `0x18083d8c5`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1533`
- prototype: `HRESULT __fastcall(ATL::CRegParser *this, wchar_t *szToken, HKEY__ *hkParent, int bRegister, int bRecover)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, registry_config`

## callers

- `0x18083cfbc`
- `0x18083d2c8`

## callees

- `0x18076e110`
- `0x18083aa00`
- `0x18083b948`
- `0x18083b9b8`
- `0x18083bbdc`
- `0x18083bcf4`
- `0x18083c160`
- `0x18083c8a4`
- `0x18083c928`
- `0x18083cbac`
- `0x18083cea8`
- `0x18083d2c8`
- `0x18083e03c`
- `0x18083e2d0`
- `0x180c010f0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18083d6e2`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18083d6e2`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18083d5e3`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18083d5e3`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18083d523`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18083d523`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18083d33b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18083d34e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18083d432`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18083d461`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18083d33b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18083d34e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18083d432`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18083d461`

## string_xrefs

- `0x18083d331`: `Delete`
- `0x18083d341`: `ForceRemove`
- `0x18083d422`: `NoRemove`

## pseudocode

```c
HRESULT __fastcall ATL::CRegParser::RegisterSubkeys(
        ATL::CRegParser *this,
        wchar_t *szToken,
        HKEY__ *hkParent,
        int bRegister,
        int bRecover)
{
  int v5; // r15d
  wchar_t *v7; // rdi
  ATL::CRegParser *i; // rsi
  int Token; // eax
  int v10; // r14d
  HRESULT v11; // ebx
  ATL::CRegParser *v12; // rcx
  HRESULT v13; // eax
  int v14; // r12d
  LSTATUS v15; // eax
  LSTATUS v16; // ebx
  __int64 v17; // rax
  unsigned int v18; // r14d
  int v19; // r15d
  int v20; // eax
  int v21; // eax
  ATL::CRegParser *v22; // rcx
  __int64 v23; // rax
  int HasSubKeys; // r15d
  int v25; // r14d
  unsigned int v27; // ecx
  __int64 dwOptions; // [rsp+20h] [rbp-E0h]
  ATL::CRegKey rkParent; // [rsp+58h] [rbp-A8h] BYREF
  ATL::CRegKey keyCur; // [rsp+70h] [rbp-90h] BYREF
  DWORD dwDisposition; // [rsp+88h] [rbp-78h] BYREF
  HKEY__ *phkResult; // [rsp+90h] [rbp-70h] BYREF
  wchar_t szKey[264]; // [rsp+A0h] [rbp-60h] BYREF
  wchar_t szValueName[4096]; // [rsp+2B0h] [rbp+1B0h] BYREF

  memset(&keyCur, 0, sizeof(keyCur));
  v5 = bRegister;
  v7 = szToken;
  for ( i = this; ; this = i )
  {
    Token = ATL::CRegParser::NextToken(this, szToken);
LABEL_31:
    v11 = Token;
    if ( Token < 0 )
      break;
    while ( 1 )
    {
      while ( 1 )
      {
        if ( *v7 == 125 )
          goto LABEL_79;
        v10 = lstrcmpiW(v7, L"Delete");
        if ( !lstrcmpiW(v7, L"ForceRemove") || !v10 )
        {
          v11 = ATL::CRegParser::NextToken(i, v7);
          if ( v11 < 0 )
            goto LABEL_79;
          if ( v5 )
          {
            memset(&rkParent, 0, sizeof(rkParent));
            if ( ATL::CRegParser::StrChr(v7, 0x5Cu) )
            {
              ATL::CRegKey::Close(&rkParent);
LABEL_78:
              v11 = -2147352567;
              goto LABEL_79;
            }
            if ( ATL::CRegParser::CanForceRemoveKey(v12, v7) )
            {
              rkParent.m_hKey = hkParent;
              ATL::CRegKey::RecurseDeleteKey(&rkParent, v7);
              rkParent.m_hKey = 0;
            }
            if ( !v10 )
            {
              v11 = ATL::CRegParser::NextToken(i, v7);
              if ( v11 < 0 )
                goto LABEL_81;
              v13 = ATL::CRegParser::SkipAssignment(i, v7);
LABEL_14:
              v11 = v13;
              if ( v13 < 0 )
                goto LABEL_81;
              ATL::CRegKey::Close(&rkParent);
              goto LABEL_42;
            }
            ATL::CRegKey::Close(&rkParent);
          }
        }
        v14 = 1;
        if ( !lstrcmpiW(v7, L"NoRemove") )
        {
          v14 = 0;
          v11 = ATL::CRegParser::NextToken(i, v7);
          if ( v11 < 0 )
            goto LABEL_79;
        }
        if ( !lstrcmpiW(v7, L"Val") )
        {
          v11 = ATL::CRegParser::NextToken(i, szValueName);
          if ( v11 < 0 )
            goto LABEL_79;
          v11 = ATL::CRegParser::NextToken(i, v7);
          if ( v11 < 0 )
            goto LABEL_79;
          if ( *v7 != 61 )
            goto LABEL_78;
          if ( !v5 )
          {
            if ( bRecover || !v14 )
              goto LABEL_30;
            memset(&rkParent, 0, sizeof(rkParent));
            v15 = ATL::CRegKey::Open(&rkParent, hkParent, 0, 0x20006u);
            if ( !v15 )
            {
              v15 = RegDeleteValueW(rkParent.m_hKey, szValueName);
              if ( (v15 & 0xFFFFFFFD) == 0 )
              {
                ATL::CRegKey::Close(&rkParent);
LABEL_30:
                Token = ATL::CRegParser::SkipAssignment(i, v7);
                goto LABEL_31;
              }
            }
LABEL_80:
            v11 = ATL::AtlHresultFromWin32(v15);
LABEL_81:
            ATL::CRegKey::Close(&rkParent);
            goto LABEL_79;
          }
          rkParent.pfnDeleteKeyEx = 0;
          rkParent.pfnDeleteKey = 0;
          rkParent.m_hKey = hkParent;
          v13 = ATL::CRegParser::AddValue(
                  i,
                  &rkParent,
                  szValueName,
                  (ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::CAtlSafeAllocBufferNode *)v7);
          rkParent.m_hKey = 0;
          goto LABEL_14;
        }
        if ( ATL::CRegParser::StrChr(v7, 0x5Cu) )
          goto LABEL_78;
        if ( v5 )
          break;
        if ( bRecover )
          v18 = 2;
        else
          v18 = ATL::CRegKey::Open(&keyCur, hkParent, v7, 0x20019u);
        v19 = 1;
        if ( !v18 )
          v19 = bRecover;
        v20 = _o_wcsncpy_s(szKey, 260, v7, -1, dwOptions);
        ATL::AtlCrtErrorCheck(v20);
        v11 = ATL::CRegParser::NextToken(i, v7);
        if ( v11 < 0 )
          goto LABEL_79;
        v21 = ATL::CRegParser::SkipAssignment(i, v7);
        v22 = 0;
        v11 = v21;
        if ( v21 < 0 )
          goto LABEL_79;
        if ( *v7 == 123 )
        {
          v23 = -1;
          do
            ++v23;
          while ( v7[v23] );
          if ( v23 == 1 )
          {
            v11 = ATL::CRegParser::RegisterSubkeys(i, v7, keyCur.m_hKey, 0, v19);
            if ( v11 < 0 && !v19 )
              goto LABEL_79;
            v11 = ATL::CRegParser::NextToken(i, v7);
            if ( v11 < 0 )
              goto LABEL_79;
          }
        }
        v5 = bRegister;
        if ( v18 != 2 )
        {
          if ( v18 )
          {
            if ( !bRecover )
            {
              v11 = ATL::AtlHresultFromWin32(v18);
              goto LABEL_79;
            }
          }
          else if ( bRecover && ATL::CRegParser::HasSubKeys(v22, keyCur.m_hKey) )
          {
            if ( ATL::CRegParser::CanForceRemoveKey(v22, szKey) && v14 )
              ATL::CRegKey::RecurseDeleteKey(&keyCur, szKey);
          }
          else
          {
            HasSubKeys = ATL::CRegParser::HasSubKeys(v22, keyCur.m_hKey);
            v25 = ATL::CRegKey::Close(&keyCur);
            if ( v25 )
            {
              ATL::CRegKey::Close(&keyCur);
              v27 = v25;
              return ATL::AtlHresultFromWin32(v27);
            }
            if ( v14 && !HasSubKeys )
            {
              rkParent.pfnDeleteKeyEx = 0;
              rkParent.pfnDeleteKey = 0;
              rkParent.m_hKey = hkParent;
              v15 = ATL::CRegKey::DeleteSubKey(&rkParent, szKey);
              rkParent.m_hKey = 0;
              if ( v15 )
                goto LABEL_80;
              ATL::CRegKey::Close(&rkParent);
            }
            v5 = bRegister;
          }
        }
      }
      if ( ATL::CRegKey::Open(&keyCur, hkParent, v7, 0x2001Fu) )
      {
        if ( ATL::CRegKey::Open(&keyCur, hkParent, v7, 0x20019u) )
        {
          dwDisposition = 0;
          phkResult = 0;
          v16 = RegCreateKeyExW(hkParent, v7, 0, 0, 0, 0x2001Fu, 0, &phkResult, &dwDisposition);
          if ( v16 || (v16 = ATL::CRegKey::Close(&keyCur), keyCur.m_hKey = phkResult, v16) )
          {
            ATL::CRegKey::Close(&keyCur);
            v27 = v16;
            return ATL::AtlHresultFromWin32(v27);
          }
        }
      }
      v11 = ATL::CRegParser::NextToken(i, v7);
      if ( v11 < 0 )
        goto LABEL_79;
      if ( *v7 == 61 )
      {
        v11 = ATL::CRegParser::AddValue(
                i,
                &keyCur,
                0,
                (ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::CAtlSafeAllocBufferNode *)v7);
        if ( v11 < 0 )
          goto LABEL_79;
      }
LABEL_42:
      if ( *v7 == 123 )
      {
        v17 = -1;
        do
          ++v17;
        while ( v7[v17] );
        if ( v17 == 1 )
          break;
      }
    }
    v11 = ATL::CRegParser::RegisterSubkeys(i, v7, keyCur.m_hKey, v5, 0);
    if ( v11 < 0 )
      break;
    szToken = v7;
  }
LABEL_79:
  ATL::CRegKey::Close(&keyCur);
  return v11;
}

```

## disassembly

```asm
0x18083d2c8  push    rbp
0x18083d2ca  push    rbx
0x18083d2cb  push    rsi
0x18083d2cc  push    rdi
0x18083d2cd  push    r12
0x18083d2cf  push    r13
0x18083d2d1  push    r14
0x18083d2d3  push    r15
0x18083d2d5  lea     rbp, [rsp-21C8h]
0x18083d2dd  mov     eax, 22C8h
0x18083d2e2  call    _alloca_probe
0x18083d2e7  sub     rsp, rax
0x18083d2ea  mov     rax, cs:__security_cookie
0x18083d2f1  xor     rax, rsp
0x18083d2f4  mov     [rbp+2200h+var_50], rax
0x18083d2fb  xor     r14d, r14d
0x18083d2fe  mov     [rsp+2300h+var_22B0], bRegister
0x18083d303  mov     [rsp+2300h+keyCur.m_hKey], r14
0x18083d308  mov     r15d, bRegister
0x18083d30b  mov     [rsp+2300h+keyCur.pfnDeleteKeyEx], r14
0x18083d310  mov     r13, hkParent
0x18083d313  mov     [rbp+2200h+keyCur.pfnDeleteKey], r14
0x18083d317  mov     rdi, szToken
0x18083d31a  mov     rsi, this
0x18083d31d  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18083d322  jmp     loc_18083D549
0x18083d327  cmp     word ptr [rdi], 7Dh ; '}'
0x18083d32b  jz      loc_18083D85F
0x18083d331  lea     szToken, aDelete; "Delete"
0x18083d338  mov     this, rdi; lpString1
0x18083d33b  call    cs:__imp_lstrcmpiW
0x18083d341  lea     szToken, aForceremove; "ForceRemove"
0x18083d348  mov     this, rdi; lpString1
0x18083d34b  mov     r14d, eax
0x18083d34e  call    cs:__imp_lstrcmpiW
0x18083d354  test    eax, eax
0x18083d356  jz      short loc_18083D361
0x18083d358  test    r14d, r14d
0x18083d35b  jnz     loc_18083D422
0x18083d361  mov     szToken, rdi; szToken
0x18083d364  mov     this, rsi; this
0x18083d367  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18083d36c  mov     ebx, eax
0x18083d36e  test    eax, eax
0x18083d370  js      loc_18083D85F
0x18083d376  test    r15d, r15d
0x18083d379  jz      loc_18083D422
0x18083d37f  mov     edx, 5Ch ; '\'; ch
0x18083d384  mov     [rsp+2300h+rkParent.m_hKey], 0
0x18083d38d  mov     this, rdi; lpsz
0x18083d390  mov     [rsp+2300h+rkParent.pfnDeleteKeyEx], 0
0x18083d399  mov     [rsp+2300h+rkParent.pfnDeleteKey], 0
0x18083d3a2  call    ?StrChr@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChr(ushort *,ushort)
0x18083d3a7  test    rax, rax
0x18083d3aa  jnz     loc_18083D850
0x18083d3b0  mov     szToken, rdi; szKey
0x18083d3b3  call    ?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEBG@Z; ATL::CRegParser::CanForceRemoveKey(ushort const *)
0x18083d3b8  test    eax, eax
0x18083d3ba  jz      short loc_18083D3D7
0x18083d3bc  mov     szToken, rdi; lpszKey
0x18083d3bf  mov     [rsp+2300h+rkParent.m_hKey], r13
0x18083d3c4  lea     this, [rsp+2300h+rkParent]; this
0x18083d3c9  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x18083d3ce  mov     [rsp+2300h+rkParent.m_hKey], 0
0x18083d3d7  test    r14d, r14d
0x18083d3da  jnz     short loc_18083D418
0x18083d3dc  mov     szToken, rdi; szToken
0x18083d3df  mov     this, rsi; this
0x18083d3e2  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18083d3e7  xor     r14d, r14d
0x18083d3ea  mov     ebx, eax
0x18083d3ec  test    eax, eax
0x18083d3ee  js      loc_18083D897
0x18083d3f4  mov     szToken, rdi; szToken
0x18083d3f7  mov     this, rsi; this
0x18083d3fa  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18083d3ff  lea     this, [rsp+2300h+rkParent]; this
0x18083d404  mov     ebx, eax
0x18083d406  test    eax, eax
0x18083d408  js      loc_18083D89C
0x18083d40e  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18083d413  jmp     loc_18083D648
0x18083d418  lea     this, [rsp+2300h+rkParent]; this
0x18083d41d  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18083d422  lea     szToken, aNoremove; "NoRemove"
0x18083d429  mov     this, rdi; lpString1
0x18083d42c  mov     r12d, 1
0x18083d432  call    cs:__imp_lstrcmpiW
0x18083d438  xor     r14d, r14d
0x18083d43b  test    eax, eax
0x18083d43d  jnz     short loc_18083D457
0x18083d43f  mov     szToken, rdi; szToken
0x18083d442  mov     this, rsi; this
0x18083d445  mov     r12d, r14d
0x18083d448  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18083d44d  mov     ebx, eax
0x18083d44f  test    eax, eax
0x18083d451  js      loc_18083D85F
0x18083d457  lea     szToken, aVal; "Val"
0x18083d45e  mov     this, rdi; lpString1
0x18083d461  call    cs:__imp_lstrcmpiW
0x18083d467  test    eax, eax
0x18083d469  jnz     loc_18083D558
0x18083d46f  lea     szToken, [rbp+2200h+szValueName]; szToken
0x18083d476  mov     this, rsi; this
0x18083d479  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18083d47e  mov     ebx, eax
0x18083d480  test    eax, eax
0x18083d482  js      loc_18083D85F
0x18083d488  mov     szToken, rdi; szToken
0x18083d48b  mov     this, rsi; this
0x18083d48e  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18083d493  mov     ebx, eax
0x18083d495  test    eax, eax
0x18083d497  js      loc_18083D85F
0x18083d49d  cmp     word ptr [rdi], 3Dh ; '='
0x18083d4a1  jnz     loc_18083D85A
0x18083d4a7  test    r15d, r15d
0x18083d4aa  jz      short loc_18083D4DC
0x18083d4ac  mov     r9, rdi; szToken
0x18083d4af  mov     [rsp+2300h+rkParent.pfnDeleteKeyEx], r14
0x18083d4b4  lea     hkParent, [rbp+2200h+szValueName]; szValueName
0x18083d4bb  mov     [rsp+2300h+rkParent.pfnDeleteKey], r14
0x18083d4c0  lea     szToken, [rsp+2300h+rkParent]; rkParent
0x18083d4c5  mov     [rsp+2300h+rkParent.m_hKey], r13
0x18083d4ca  mov     this, rsi; this
0x18083d4cd  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x18083d4d2  mov     [rsp+2300h+rkParent.m_hKey], r14
0x18083d4d7  jmp     loc_18083D3FF
0x18083d4dc  cmp     [rbp+2200h+arg_20], r14d
0x18083d4e3  jnz     short loc_18083D53E
0x18083d4e5  test    r12d, r12d
0x18083d4e8  jz      short loc_18083D53E
0x18083d4ea  mov     bRegister, 20006h; samDesired
0x18083d4f0  mov     [rsp+2300h+rkParent.m_hKey], r14
0x18083d4f5  xor     r8d, r8d; lpszKeyName
0x18083d4f8  mov     [rsp+2300h+rkParent.pfnDeleteKeyEx], r14
0x18083d4fd  mov     szToken, r13; hKeyParent
0x18083d500  mov     [rsp+2300h+rkParent.pfnDeleteKey], r14
0x18083d505  lea     this, [rsp+2300h+rkParent]; this
0x18083d50a  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18083d50f  test    eax, eax
0x18083d511  jnz     loc_18083D88E
0x18083d517  mov     this, [rsp+2300h+rkParent.m_hKey]; hKey
0x18083d51c  lea     szToken, [rbp+2200h+szValueName]; lpValueName
0x18083d523  call    cs:__imp_RegDeleteValueW
0x18083d529  test    eax, 0FFFFFFFDh
0x18083d52e  jnz     loc_18083D88E
0x18083d534  lea     this, [rsp+2300h+rkParent]; this
0x18083d539  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18083d53e  mov     szToken, rdi; szToken
0x18083d541  mov     this, rsi; this
0x18083d544  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18083d549  mov     ebx, eax
0x18083d54b  test    eax, eax
0x18083d54d  jns     loc_18083D327
0x18083d553  jmp     loc_18083D85F
0x18083d558  mov     edx, 5Ch ; '\'; ch
0x18083d55d  mov     this, rdi; lpsz
0x18083d560  call    ?StrChr@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChr(ushort *,ushort)
0x18083d565  test    rax, rax
0x18083d568  jnz     loc_18083D85A
0x18083d56e  test    r15d, r15d
0x18083d571  jz      loc_18083D697
0x18083d577  mov     bRegister, 2001Fh; samDesired
0x18083d57d  lea     this, [rsp+2300h+keyCur]; this
0x18083d582  mov     hkParent, rdi; lpszKeyName
0x18083d585  mov     szToken, r13; hKeyParent
0x18083d588  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18083d58d  test    eax, eax
0x18083d58f  jz      short loc_18083D610
0x18083d591  mov     bRegister, 20019h; samDesired
0x18083d597  lea     this, [rsp+2300h+keyCur]; this
0x18083d59c  mov     hkParent, rdi; lpszKeyName
0x18083d59f  mov     szToken, r13; hKeyParent
0x18083d5a2  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18083d5a7  test    eax, eax
0x18083d5a9  jz      short loc_18083D610
0x18083d5ab  lea     rax, [rbp+2200h+dwDisposition]
0x18083d5af  mov     [rbp+2200h+dwDisposition], r14d
0x18083d5b3  mov     [rsp+2300h+lpdwDisposition], rax; lpdwDisposition
0x18083d5b8  xor     bRegister, bRegister; lpClass
0x18083d5bb  lea     rax, [rbp+2200h+var_2270]
0x18083d5bf  mov     [rbp+2200h+var_2270], r14
0x18083d5c3  mov     [rsp+2300h+phkResult], rax; phkResult
0x18083d5c8  xor     r8d, r8d; Reserved
0x18083d5cb  mov     [rsp+2300h+lpSecurityAttributes], r14; lpSecurityAttributes
0x18083d5d0  mov     szToken, rdi; lpSubKey
0x18083d5d3  mov     [rsp+2300h+samDesired], 2001Fh; samDesired
0x18083d5db  mov     this, r13; hKey
0x18083d5de  mov     dword ptr [rsp+2300h+dwOptions], r14d; dwOptions
0x18083d5e3  call    cs:__imp_RegCreateKeyExW
0x18083d5e9  mov     ebx, eax
0x18083d5eb  test    eax, eax
0x18083d5ed  jnz     loc_18083D8A3
0x18083d5f3  lea     this, [rsp+2300h+keyCur]; this
0x18083d5f8  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18083d5fd  mov     ebx, eax
0x18083d5ff  mov     rax, [rbp+2200h+var_2270]
0x18083d603  mov     [rsp+2300h+keyCur.m_hKey], rax
0x18083d608  test    ebx, ebx
0x18083d60a  jnz     loc_18083D8A3
0x18083d610  mov     szToken, rdi; szToken
0x18083d613  mov     this, rsi; this
0x18083d616  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18083d61b  mov     ebx, eax
0x18083d61d  test    eax, eax
0x18083d61f  js      loc_18083D85F
0x18083d625  cmp     word ptr [rdi], 3Dh ; '='
0x18083d629  jnz     short loc_18083D648
0x18083d62b  mov     r9, rdi; szToken
0x18083d62e  lea     szToken, [rsp+2300h+keyCur]; rkParent
0x18083d633  xor     r8d, r8d; szValueName
0x18083d636  mov     this, rsi; this
0x18083d639  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x18083d63e  mov     ebx, eax
0x18083d640  test    eax, eax
0x18083d642  js      loc_18083D85F
0x18083d648  cmp     word ptr [rdi], 7Bh ; '{'
0x18083d64c  jnz     loc_18083D327
0x18083d652  or      rax, 0FFFFFFFFFFFFFFFFh
0x18083d656  inc     rax
0x18083d659  cmp     [rdi+rax*2], r14w
0x18083d65e  jnz     short loc_18083D656
0x18083d660  cmp     rax, 1
0x18083d664  jnz     loc_18083D327
0x18083d66a  mov     hkParent, [rsp+2300h+keyCur.m_hKey]; hkParent
0x18083d66f  mov     bRegister, r15d; bRegister
0x18083d672  mov     szToken, rdi; szToken
0x18083d675  mov     dword ptr [rsp+2300h+dwOptions], r14d; bRecover
0x18083d67a  mov     this, rsi; this
0x18083d67d  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18083d682  mov     ebx, eax
0x18083d684  test    eax, eax
0x18083d686  js      loc_18083D85F
0x18083d68c  mov     szToken, rdi
0x18083d68f  mov     this, rsi
0x18083d692  jmp     loc_18083D31D
0x18083d697  cmp     [rbp+2200h+arg_20], r14d
0x18083d69e  jnz     short loc_18083D6BB
0x18083d6a0  mov     bRegister, 20019h; samDesired
0x18083d6a6  lea     this, [rsp+2300h+keyCur]; this
0x18083d6ab  mov     hkParent, rdi; lpszKeyName
0x18083d6ae  mov     szToken, r13; hKeyParent
0x18083d6b1  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18083d6b6  mov     r14d, eax
0x18083d6b9  jmp     short loc_18083D6C1
0x18083d6bb  mov     r14d, 2
0x18083d6c1  test    r14d, r14d
0x18083d6c4  lea     this, [rbp+2200h+szKey]
0x18083d6c8  mov     r15d, 1
0x18083d6ce  mov     hkParent, rdi
0x18083d6d1  cmovz   r15d, [rbp+2200h+arg_20]
0x18083d6d9  mov     edx, 104h
0x18083d6de  or      r9, 0FFFFFFFFFFFFFFFFh
0x18083d6e2  call    cs:__imp__o_wcsncpy_s
0x18083d6e8  mov     ecx, eax; nError
0x18083d6ea  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18083d6ef  mov     szToken, rdi; szToken
0x18083d6f2  mov     this, rsi; this
0x18083d6f5  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18083d6fa  mov     ebx, eax
0x18083d6fc  test    eax, eax
0x18083d6fe  js      loc_18083D85F
0x18083d704  mov     szToken, rdi; szToken
0x18083d707  mov     this, rsi; this
0x18083d70a  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18083d70f  xor     ecx, ecx
0x18083d711  mov     ebx, eax
0x18083d713  test    eax, eax
0x18083d715  js      loc_18083D85F
0x18083d71b  cmp     word ptr [rdi], 7Bh ; '{'
0x18083d71f  jnz     short loc_18083D770
0x18083d721  or      rax, 0FFFFFFFFFFFFFFFFh
0x18083d725  inc     rax
0x18083d728  cmp     [rdi+rax*2], cx
0x18083d72c  jnz     short loc_18083D725
0x18083d72e  cmp     rax, 1
0x18083d732  jnz     short loc_18083D770
0x18083d734  mov     hkParent, [rsp+2300h+keyCur.m_hKey]; hkParent
0x18083d739  xor     bRegister, bRegister; bRegister
0x18083d73c  mov     szToken, rdi; szToken
0x18083d73f  mov     dword ptr [rsp+2300h+dwOptions], r15d; bRecover
0x18083d744  mov     this, rsi; this
0x18083d747  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18083d74c  mov     ebx, eax
0x18083d74e  test    eax, eax
0x18083d750  jns     short loc_18083D75B
0x18083d752  test    r15d, r15d
0x18083d755  jz      loc_18083D85F
0x18083d75b  mov     szToken, rdi; szToken
0x18083d75e  mov     this, rsi; this
0x18083d761  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18083d766  mov     ebx, eax
0x18083d768  test    eax, eax
0x18083d76a  js      loc_18083D85F
0x18083d770  mov     r15d, [rsp+2300h+var_22B0]
0x18083d775  cmp     r14d, 2
0x18083d779  jz      loc_18083D327
0x18083d77f  test    r14d, r14d
  ... truncated ...
```
