# CWorkspaceFileAssociation::Install(CWorkspaceFtaAppRegistration *,std::map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,KeyCompareLess,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>>>> &,int)

- ea: `0x180054b64`
- end: `0x1800551e9`
- name: `?Install@CWorkspaceFileAssociation@@QEAAJPEAVCWorkspaceFtaAppRegistration@@AEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@UKeyCompareLess@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@@std@@H@Z`
- size: `1669`
- prototype: `__int64 __fastcall(CWorkspaceFileAssociation *this, __int64, __int64)`
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180034224`

## callees

- `0x18000b1d8`
- `0x18000d8d4`
- `0x18000ec94`
- `0x18000ece0`
- `0x18001e5d8`
- `0x18001e6bc`
- `0x18001e820`
- `0x18001eac4`
- `0x180020a68`
- `0x180020bf0`
- `0x180028444`
- `0x180028ca0`
- `0x18003c894`
- `0x18004ecd0`
- `0x18005228c`
- `0x180053028`
- `0x18005342c`
- `0x18005371c`
- `0x180054b64`
- `0x1800551f0`
- `0x1800553d0`
- `0x180055a18`
- `0x18009a520`

## import_xrefs

- `ADVAPI32!RegCreateKeyTransactedW` at `0x180054cc1`
- `ADVAPI32!RegCreateKeyTransactedW` at `0x180054cc1`
- `ADVAPI32!RegCloseKey` at `0x1800551a9`
- `ADVAPI32!RegCloseKey` at `0x1800551a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054c14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054c51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054f86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054fc3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054c14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054c51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054f86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054fc3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800551b8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800551b8`
- `SHELL32!SHChangeNotify` at `0x18005511f`
- `SHELL32!SHChangeNotify` at `0x18005511f`
- `ktmw32!CreateTransaction` at `0x180054be1`
- `ktmw32!CreateTransaction` at `0x180054be1`
- `ktmw32!CommitTransaction` at `0x180054f5d`
- `ktmw32!CommitTransaction` at `0x180054f5d`

## string_xrefs

- `0x180054e00`: `CWorkspaceFileAssociation::SaveProgIdToRegistry failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CWorkspaceFileAssociation::Install(CWorkspaceFileAssociation *this, __int64 a2, __int64 a3)
{
  HANDLE hTransaction; // rax
  void *v7; // r14
  signed int LastError; // eax
  unsigned int v9; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  signed int v11; // eax
  int v12; // ebx
  unsigned int v13; // esi
  unsigned int v14; // eax
  unsigned int v15; // eax
  unsigned int v16; // eax
  HKEY v17; // rbx
  HKEY v18; // rax
  unsigned int v19; // eax
  unsigned int v20; // eax
  signed int v21; // eax
  unsigned int v22; // ebx
  unsigned int v23; // eax
  signed int v24; // eax
  __int64 v25; // rbx
  unsigned int v26; // eax
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rax
  unsigned int v30; // eax
  __int64 Timeout; // [rsp+28h] [rbp-110h]
  int v33; // [rsp+68h] [rbp-D0h] BYREF
  DWORD dwDisposition; // [rsp+70h] [rbp-C8h] BYREF
  HANDLE v35; // [rsp+78h] [rbp-C0h]
  HKEY hKey; // [rsp+80h] [rbp-B8h] BYREF
  _QWORD v37[2]; // [rsp+88h] [rbp-B0h] BYREF
  _BYTE v38[32]; // [rsp+98h] [rbp-A0h] BYREF
  __int64 v39; // [rsp+B8h] [rbp-80h]
  _BYTE *v40; // [rsp+C0h] [rbp-78h]
  _BYTE v41[64]; // [rsp+C8h] [rbp-70h] BYREF

  v39 = -2;
  hKey = 0;
  dwDisposition = 0;
  hTransaction = CreateTransaction(0, 0, 1u, 0, 0, 0x2710u, (LPWSTR)L"Registering per-FTA File Association information");
  v7 = hTransaction;
  v35 = hTransaction;
  if ( hTransaction == (HANDLE)-1LL )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LastError = GetLastError();
      v9 = LastError;
      if ( LastError > 0 )
        v9 = (unsigned __int16)LastError | 0x80070000;
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        49,
        WPP_1b4a91e28c533a877c5d59eaaa244463_Traceguids,
        CurrentThreadActivityIdPrefix,
        v9);
    }
    v11 = GetLastError();
    v12 = v11;
    if ( v11 > 0 )
      v12 = (unsigned __int16)v11 | 0x80070000;
  }
  else
  {
    v12 = RegCreateKeyTransactedW(
            HKEY_CURRENT_USER,
            L"Software\\classes",
            0,
            0,
            0,
            0x20006u,
            0,
            &hKey,
            &dwDisposition,
            hTransaction,
            0);
    if ( v12 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        if ( v12 > 0 )
          v13 = (unsigned __int16)v12 | 0x80070000;
        else
          v13 = v12;
        v14 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, WPP_1b4a91e28c533a877c5d59eaaa244463_Traceguids, v14, v13);
      }
      if ( v12 > 0 )
        v12 = (unsigned __int16)v12 | 0x80070000;
    }
    else
    {
      v33 = 0;
      v12 = CWorkspaceFileAssociation::ClassifyCurrentPrimaryHandler(
              this,
              v7,
              (enum CWorkspaceFileAssociation::CURRENT_HANDLER_STATE *)&v33);
      if ( v12 >= 0 )
      {
        v12 = CWorkspaceFileAssociation::SaveProgIdToRegistry(this, v7, hKey);
        if ( v12 >= 0 )
        {
          v40 = v38;
          v17 = (HKEY)std::wstring::wstring(v38, (char *)this + 216);
          v37[0] = v41;
          v18 = (HKEY)std::wstring::wstring(v41, (char *)this + 48);
          v12 = CWorkspaceFtaAppRegistration::RegisterFileAssociation(a2, v7, v18, v17);
          if ( v12 >= 0 )
          {
            v12 = CWorkspaceFileAssociation::RegisterSecondaryHandler(this, v7);
            if ( v12 >= 0 )
            {
              if ( CommitTransaction(v7) )
              {
                if ( !*((_DWORD *)this + 52) || v33 == 2 )
                  goto LABEL_64;
                if ( v33 == 3 )
                {
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    v25 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 48);
                    v26 = RdpWppGetCurrentThreadActivityIdPrefix();
                    WPP_SF_DS(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      56,
                      (unsigned int)WPP_1b4a91e28c533a877c5d59eaaa244463_Traceguids,
                      v26,
                      v25);
                  }
                  std::_Tree<std::_Tmap_traits<std::wstring,std::vector<unsigned short const *>,KeyCompareLess,std::allocator<std::pair<std::wstring const,std::vector<unsigned short const *>>>,0>>::find(
                    a3,
                    &v33,
                    (char *)this + 48);
                  v27 = std::vector<unsigned int>::begin(a3, v37);
                  if ( (unsigned __int8)std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,ResourceTypeInfo>>>>::operator==(
                                          &v33,
                                          v27) )
                  {
                    std::vector<ComPlainSmartPtr<CTenantFeedInfo>>::vector<ComPlainSmartPtr<CTenantFeedInfo>>(v38);
                    std::vector<std::wstring>::push_back(v38, (char *)this + 80);
                    v28 = std::pair<std::wstring,std::vector<std::wstring>>::pair<std::wstring,std::vector<std::wstring>>(
                            v41,
                            (char *)this + 48,
                            v38);
                    std::_Tree<std::_Tmap_traits<std::wstring,std::vector<std::wstring>,KeyCompareLess,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>,0>>::insert<std::pair<std::wstring,std::vector<std::wstring>>>(
                      a3,
                      v37,
                      v28);
                    std::pair<std::wstring,std::vector<std::wstring>>::~pair<std::wstring,std::vector<std::wstring>>(v41);
                    std::vector<std::wstring>::~vector<std::wstring>(v38);
                  }
                  else
                  {
                    v29 = std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>>::operator->(&v33);
                    std::vector<std::wstring>::push_back(v29 + 32, (char *)this + 80);
                  }
                }
                SHChangeNotify(0x8000000, 0, 0, 0);
                v12 = CWorkspaceFileAssociation::RegisterPrimaryHandler(this, v7);
                if ( v12 >= 0 )
                {
LABEL_64:
                  v12 = 0;
                }
                else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                       && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                       && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v30 = RdpWppGetCurrentThreadActivityIdPrefix();
                  LODWORD(Timeout) = v12;
                  WPP_SF_DsD(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    57,
                    (unsigned int)WPP_1b4a91e28c533a877c5d59eaaa244463_Traceguids,
                    v30,
                    (__int64)"CWorkspaceFileAssociation::RegisterPrimaryHandler failed",
                    Timeout);
                }
              }
              else
              {
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v21 = GetLastError();
                  v22 = v21;
                  if ( v21 > 0 )
                    v22 = (unsigned __int16)v21 | 0x80070000;
                  v23 = RdpWppGetCurrentThreadActivityIdPrefix();
                  WPP_SF_Dd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    55,
                    WPP_1b4a91e28c533a877c5d59eaaa244463_Traceguids,
                    v23,
                    v22);
                }
                v24 = GetLastError();
                v12 = v24;
                if ( v24 > 0 )
                  v12 = (unsigned __int16)v24 | 0x80070000;
              }
            }
            else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                   && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                   && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v20 = RdpWppGetCurrentThreadActivityIdPrefix();
              LODWORD(Timeout) = v12;
              WPP_SF_DsD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                54,
                (unsigned int)WPP_1b4a91e28c533a877c5d59eaaa244463_Traceguids,
                v20,
                (__int64)"CWorkspaceFileAssociation::RegisterSecondaryHandler failed",
                Timeout);
            }
          }
          else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v19 = RdpWppGetCurrentThreadActivityIdPrefix();
            LODWORD(Timeout) = v12;
            WPP_SF_DsD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              53,
              (unsigned int)WPP_1b4a91e28c533a877c5d59eaaa244463_Traceguids,
              v19,
              (__int64)"CWorkspaceFtaAppRegistration::RegisterFileAssociation failed",
              Timeout);
          }
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v16 = RdpWppGetCurrentThreadActivityIdPrefix();
          LODWORD(Timeout) = v12;
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            52,
            (unsigned int)WPP_1b4a91e28c533a877c5d59eaaa244463_Traceguids,
            v16,
            (__int64)"CWorkspaceFileAssociation::SaveProgIdToRegistry failed",
            Timeout);
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v15 = RdpWppGetCurrentThreadActivityIdPrefix();
        LODWORD(Timeout) = v12;
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          51,
          (unsigned int)WPP_1b4a91e28c533a877c5d59eaaa244463_Traceguids,
          v15,
          (__int64)"ClassifyCurrentPrimaryHandler failed",
          Timeout);
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( v7 != (void *)-1LL )
    CloseHandle(v7);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180054b64  mov     r11, rsp
0x180054b67  push    rsi
0x180054b68  push    r12
0x180054b6a  push    r13
0x180054b6c  push    r14
0x180054b6e  push    r15
0x180054b70  sub     rsp, 110h
0x180054b77  mov     qword ptr [r11-80h], 0FFFFFFFFFFFFFFFEh
0x180054b7f  mov     [r11+20h], rbx
0x180054b83  mov     rax, cs:__security_cookie
0x180054b8a  xor     rax, rsp
0x180054b8d  mov     [rsp+138h+var_30], rax
0x180054b95  mov     r13, r8
0x180054b98  mov     rsi, rdx
0x180054b9b  mov     r15, rcx
0x180054b9e  mov     qword ptr [r11-0B8h], 0
0x180054ba9  mov     [rsp+138h+dwDisposition], 0
0x180054bb1  mov     [rsp+138h+var_C0], 0FFFFFFFFFFFFFFFFh
0x180054bba  lea     rax, aRegisteringPer_0; "Registering per-FTA File Association in"...
0x180054bc1  mov     [rsp+138h+Description], rax; Description
0x180054bc6  mov     dword ptr [rsp+138h+Timeout], 2710h; Timeout
0x180054bce  mov     [rsp+138h+IsolationFlags], 0; IsolationFlags
0x180054bd6  xor     r9d, r9d; IsolationLevel
0x180054bd9  xor     edx, edx; UOW
0x180054bdb  xor     ecx, ecx; lpTransactionAttributes
0x180054bdd  lea     r8d, [r9+1]; CreateOptions
0x180054be1  call    cs:__imp_CreateTransaction
0x180054be7  mov     r14, rax
0x180054bea  mov     [rsp+138h+var_C0], rax
0x180054bef  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180054bf3  jnz     short loc_180054C6F
0x180054bf5  lea     rsi, WPP_GLOBAL_Control
0x180054bfc  mov     rax, cs:WPP_GLOBAL_Control
0x180054c03  cmp     rax, rsi
0x180054c06  jz      short loc_180054C51
0x180054c08  test    byte ptr [rax+1Ch], 8
0x180054c0c  jz      short loc_180054C51
0x180054c0e  cmp     byte ptr [rax+19h], 2
0x180054c12  jb      short loc_180054C51
0x180054c14  call    cs:__imp_GetLastError
0x180054c1a  mov     ebx, eax
0x180054c1c  test    eax, eax
0x180054c1e  jle     short loc_180054C29
0x180054c20  movzx   ebx, ax
0x180054c23  or      ebx, 80070000h
0x180054c29  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180054c2e  mov     edx, 31h ; '1'
0x180054c33  mov     [rsp+138h+IsolationFlags], ebx
0x180054c37  mov     r9d, eax
0x180054c3a  lea     r8, WPP_1b4a91e28c533a877c5d59eaaa244463_Traceguids
0x180054c41  mov     rcx, cs:WPP_GLOBAL_Control
0x180054c48  mov     rcx, [rcx+10h]
0x180054c4c  call    WPP_SF_Dd
0x180054c51  call    cs:__imp_GetLastError
0x180054c57  mov     ebx, eax
0x180054c59  test    eax, eax
0x180054c5b  jle     short loc_180054C66
0x180054c5d  movzx   ebx, ax
0x180054c60  or      ebx, 80070000h
0x180054c66  mov     [rsp+138h+var_D8], ebx
0x180054c6a  jmp     loc_18005519C
0x180054c6f  mov     [rsp+138h+pExtendedParemeter], 0; pExtendedParemeter
0x180054c78  mov     [rsp+138h+hTransaction], r14; hTransaction
0x180054c7d  lea     rax, [rsp+138h+dwDisposition]
0x180054c82  mov     [rsp+138h+lpdwDisposition], rax; lpdwDisposition
0x180054c87  lea     rax, [rsp+138h+hKey]
0x180054c8f  mov     [rsp+138h+phkResult], rax; phkResult
0x180054c94  mov     [rsp+138h+Description], 0; lpSecurityAttributes
0x180054c9d  mov     dword ptr [rsp+138h+Timeout], 20006h; samDesired
0x180054ca5  mov     [rsp+138h+IsolationFlags], 0; dwOptions
0x180054cad  xor     r9d, r9d; lpClass
0x180054cb0  xor     r8d, r8d; Reserved
0x180054cb3  lea     rdx, aSoftwareClasse; "Software\\classes"
0x180054cba  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180054cc1  call    cs:__imp_RegCreateKeyTransactedW
0x180054cc7  mov     ebx, eax
0x180054cc9  test    eax, eax
0x180054ccb  jz      short loc_180054D3B
0x180054ccd  lea     rsi, WPP_GLOBAL_Control
0x180054cd4  mov     rax, cs:WPP_GLOBAL_Control
0x180054cdb  cmp     rax, rsi
0x180054cde  jz      short loc_180054D25
0x180054ce0  test    byte ptr [rax+1Ch], 8
0x180054ce4  jz      short loc_180054D25
0x180054ce6  cmp     byte ptr [rax+19h], 2
0x180054cea  jb      short loc_180054D25
0x180054cec  test    ebx, ebx
0x180054cee  jg      short loc_180054CF4
0x180054cf0  mov     esi, ebx
0x180054cf2  jmp     short loc_180054CFD
0x180054cf4  movzx   esi, bx
0x180054cf7  or      esi, 80070000h
0x180054cfd  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180054d02  mov     edx, 32h ; '2'
0x180054d07  mov     [rsp+138h+IsolationFlags], esi
0x180054d0b  mov     r9d, eax
0x180054d0e  lea     r8, WPP_1b4a91e28c533a877c5d59eaaa244463_Traceguids
0x180054d15  mov     rcx, cs:WPP_GLOBAL_Control
0x180054d1c  mov     rcx, [rcx+10h]
0x180054d20  call    WPP_SF_Dd
0x180054d25  test    ebx, ebx
0x180054d27  jle     short loc_180054D32
0x180054d29  movzx   ebx, bx
0x180054d2c  or      ebx, 80070000h
0x180054d32  mov     [rsp+138h+var_D8], ebx
0x180054d36  jmp     loc_18005519C
0x180054d3b  mov     [rsp+138h+var_D0], 0
0x180054d43  lea     r8, [rsp+138h+var_D0]; enum CWorkspaceFileAssociation::CURRENT_HANDLER_STATE *
0x180054d48  mov     rdx, r14; void *
0x180054d4b  mov     rcx, r15; this
0x180054d4e  call    ?ClassifyCurrentPrimaryHandler@CWorkspaceFileAssociation@@IEAAJPEAXPEAW4CURRENT_HANDLER_STATE@1@@Z; CWorkspaceFileAssociation::ClassifyCurrentPrimaryHandler(void *,CWorkspaceFileAssociation::CURRENT_HANDLER_STATE *)
0x180054d53  mov     ebx, eax
0x180054d55  mov     [rsp+138h+var_D8], eax
0x180054d59  test    eax, eax
0x180054d5b  jns     short loc_180054DB6
0x180054d5d  lea     rsi, WPP_GLOBAL_Control
0x180054d64  mov     rax, cs:WPP_GLOBAL_Control
0x180054d6b  cmp     rax, rsi
0x180054d6e  jz      short loc_180054DB1
0x180054d70  test    byte ptr [rax+1Ch], 8
0x180054d74  jz      short loc_180054DB1
0x180054d76  cmp     byte ptr [rax+19h], 2
0x180054d7a  jb      short loc_180054DB1
0x180054d7c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180054d81  mov     edx, 33h ; '3'
0x180054d86  mov     dword ptr [rsp+138h+Timeout], ebx
0x180054d8a  lea     rcx, aClassifycurren; "ClassifyCurrentPrimaryHandler failed"
0x180054d91  mov     qword ptr [rsp+138h+IsolationFlags], rcx
0x180054d96  mov     r9d, eax
0x180054d99  lea     r8, WPP_1b4a91e28c533a877c5d59eaaa244463_Traceguids
0x180054da0  mov     rcx, cs:WPP_GLOBAL_Control
0x180054da7  mov     rcx, [rcx+10h]
0x180054dab  call    WPP_SF_DsD
0x180054db0  nop
0x180054db1  jmp     loc_18005519C
0x180054db6  mov     r8, [rsp+138h+hKey]; HKEY
0x180054dbe  mov     rdx, r14; void *
0x180054dc1  mov     rcx, r15; this
0x180054dc4  call    ?SaveProgIdToRegistry@CWorkspaceFileAssociation@@IEAAJPEAXPEAUHKEY__@@@Z; CWorkspaceFileAssociation::SaveProgIdToRegistry(void *,HKEY__ *)
0x180054dc9  mov     ebx, eax
0x180054dcb  mov     [rsp+138h+var_D8], eax
0x180054dcf  test    eax, eax
0x180054dd1  jns     short loc_180054E2C
0x180054dd3  lea     rsi, WPP_GLOBAL_Control
0x180054dda  mov     rax, cs:WPP_GLOBAL_Control
0x180054de1  cmp     rax, rsi
0x180054de4  jz      short loc_180054E27
0x180054de6  test    byte ptr [rax+1Ch], 8
0x180054dea  jz      short loc_180054E27
0x180054dec  cmp     byte ptr [rax+19h], 2
0x180054df0  jb      short loc_180054E27
0x180054df2  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180054df7  mov     edx, 34h ; '4'
0x180054dfc  mov     dword ptr [rsp+138h+Timeout], ebx
0x180054e00  lea     rcx, aCworkspacefile_0; "CWorkspaceFileAssociation::SaveProgIdTo"...
0x180054e07  mov     qword ptr [rsp+138h+IsolationFlags], rcx
0x180054e0c  mov     r9d, eax
0x180054e0f  lea     r8, WPP_1b4a91e28c533a877c5d59eaaa244463_Traceguids
0x180054e16  mov     rcx, cs:WPP_GLOBAL_Control
0x180054e1d  mov     rcx, [rcx+10h]
0x180054e21  call    WPP_SF_DsD
0x180054e26  nop
0x180054e27  jmp     loc_18005519C
0x180054e2c  lea     rax, [rsp+138h+var_A0]
0x180054e34  mov     [rsp+138h+var_78], rax
0x180054e3c  lea     rdx, [r15+0D8h]
0x180054e43  lea     rcx, [rsp+138h+var_A0]
0x180054e4b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180054e50  mov     rbx, rax
0x180054e53  lea     rax, [rsp+138h+var_70]
0x180054e5b  mov     [rsp+138h+var_B0], rax
0x180054e63  lea     r12, [r15+30h]
0x180054e67  mov     rdx, r12
0x180054e6a  lea     rcx, [rsp+138h+var_70]
0x180054e72  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180054e77  nop
0x180054e78  mov     r9, rbx
0x180054e7b  mov     r8, rax
0x180054e7e  mov     rdx, r14
0x180054e81  mov     rcx, rsi
0x180054e84  call    ?RegisterFileAssociation@CWorkspaceFtaAppRegistration@@QEAAJPEAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1@Z; CWorkspaceFtaAppRegistration::RegisterFileAssociation(void *,std::wstring,std::wstring)
0x180054e89  mov     ebx, eax
0x180054e8b  mov     [rsp+138h+var_D8], eax
0x180054e8f  test    eax, eax
0x180054e91  jns     short loc_180054EEC
0x180054e93  lea     rsi, WPP_GLOBAL_Control
0x180054e9a  mov     rax, cs:WPP_GLOBAL_Control
0x180054ea1  cmp     rax, rsi
0x180054ea4  jz      short loc_180054EE7
0x180054ea6  test    byte ptr [rax+1Ch], 8
0x180054eaa  jz      short loc_180054EE7
0x180054eac  cmp     byte ptr [rax+19h], 2
0x180054eb0  jb      short loc_180054EE7
0x180054eb2  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180054eb7  mov     edx, 35h ; '5'
0x180054ebc  mov     dword ptr [rsp+138h+Timeout], ebx
0x180054ec0  lea     rcx, aCworkspaceftaa_2; "CWorkspaceFtaAppRegistration::RegisterF"...
0x180054ec7  mov     qword ptr [rsp+138h+IsolationFlags], rcx
0x180054ecc  mov     r9d, eax
0x180054ecf  lea     r8, WPP_1b4a91e28c533a877c5d59eaaa244463_Traceguids
0x180054ed6  mov     rcx, cs:WPP_GLOBAL_Control
0x180054edd  mov     rcx, [rcx+10h]
0x180054ee1  call    WPP_SF_DsD
0x180054ee6  nop
0x180054ee7  jmp     loc_18005519C
0x180054eec  mov     rdx, r14; void *
0x180054eef  mov     rcx, r15; this
0x180054ef2  call    ?RegisterSecondaryHandler@CWorkspaceFileAssociation@@IEAAJPEAX@Z; CWorkspaceFileAssociation::RegisterSecondaryHandler(void *)
0x180054ef7  mov     ebx, eax
0x180054ef9  mov     [rsp+138h+var_D8], eax
0x180054efd  test    eax, eax
0x180054eff  jns     short loc_180054F5A
0x180054f01  lea     rsi, WPP_GLOBAL_Control
0x180054f08  mov     rax, cs:WPP_GLOBAL_Control
0x180054f0f  cmp     rax, rsi
0x180054f12  jz      short loc_180054F55
0x180054f14  test    byte ptr [rax+1Ch], 8
0x180054f18  jz      short loc_180054F55
0x180054f1a  cmp     byte ptr [rax+19h], 2
0x180054f1e  jb      short loc_180054F55
0x180054f20  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180054f25  mov     edx, 36h ; '6'
0x180054f2a  mov     dword ptr [rsp+138h+Timeout], ebx
0x180054f2e  lea     rcx, aCworkspacefile_3; "CWorkspaceFileAssociation::RegisterSeco"...
0x180054f35  mov     qword ptr [rsp+138h+IsolationFlags], rcx
0x180054f3a  mov     r9d, eax
0x180054f3d  lea     r8, WPP_1b4a91e28c533a877c5d59eaaa244463_Traceguids
0x180054f44  mov     rcx, cs:WPP_GLOBAL_Control
0x180054f4b  mov     rcx, [rcx+10h]
0x180054f4f  call    WPP_SF_DsD
0x180054f54  nop
0x180054f55  jmp     loc_18005519C
0x180054f5a  mov     rcx, r14; TransactionHandle
0x180054f5d  call    cs:__imp_CommitTransaction
0x180054f63  test    eax, eax
0x180054f65  jnz     short loc_180054FE1
0x180054f67  lea     rsi, WPP_GLOBAL_Control
0x180054f6e  mov     rax, cs:WPP_GLOBAL_Control
0x180054f75  cmp     rax, rsi
0x180054f78  jz      short loc_180054FC3
0x180054f7a  test    byte ptr [rax+1Ch], 8
0x180054f7e  jz      short loc_180054FC3
0x180054f80  cmp     byte ptr [rax+19h], 2
0x180054f84  jb      short loc_180054FC3
0x180054f86  call    cs:__imp_GetLastError
0x180054f8c  mov     ebx, eax
0x180054f8e  test    eax, eax
0x180054f90  jle     short loc_180054F9B
0x180054f92  movzx   ebx, ax
0x180054f95  or      ebx, 80070000h
0x180054f9b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180054fa0  mov     edx, 37h ; '7'
0x180054fa5  mov     [rsp+138h+IsolationFlags], ebx
0x180054fa9  mov     r9d, eax
0x180054fac  lea     r8, WPP_1b4a91e28c533a877c5d59eaaa244463_Traceguids
0x180054fb3  mov     rcx, cs:WPP_GLOBAL_Control
0x180054fba  mov     rcx, [rcx+10h]
0x180054fbe  call    WPP_SF_Dd
0x180054fc3  call    cs:__imp_GetLastError
0x180054fc9  mov     ebx, eax
0x180054fcb  test    eax, eax
0x180054fcd  jle     short loc_180054FD8
0x180054fcf  movzx   ebx, ax
0x180054fd2  or      ebx, 80070000h
0x180054fd8  mov     [rsp+138h+var_D8], ebx
0x180054fdc  jmp     loc_18005519C
0x180054fe1  cmp     dword ptr [r15+0D0h], 0
0x180054fe9  jz      loc_180055189
0x180054fef  cmp     [rsp+138h+var_D0], 2
0x180054ff4  jz      loc_180055189
0x180054ffa  cmp     [rsp+138h+var_D0], 3
0x180054fff  jnz     loc_18005510B
0x180055005  lea     rsi, WPP_GLOBAL_Control
0x18005500c  mov     rax, cs:WPP_GLOBAL_Control
0x180055013  cmp     rax, rsi
0x180055016  jz      short loc_180055058
0x180055018  test    byte ptr [rax+1Ch], 1
0x18005501c  jz      short loc_180055058
0x18005501e  cmp     byte ptr [rax+19h], 2
0x180055022  jb      short loc_180055058
0x180055024  mov     rcx, r12
0x180055027  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18005502c  mov     rbx, rax
0x18005502f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180055034  mov     edx, 38h ; '8'
0x180055039  mov     qword ptr [rsp+138h+IsolationFlags], rbx
0x18005503e  mov     r9d, eax
0x180055041  lea     r8, WPP_1b4a91e28c533a877c5d59eaaa244463_Traceguids
0x180055048  mov     rcx, cs:WPP_GLOBAL_Control
0x18005504f  mov     rcx, [rcx+10h]
0x180055053  call    WPP_SF_DS
0x180055058  mov     r8, r12
0x18005505b  lea     rdx, [rsp+138h+var_D0]
0x180055060  mov     rcx, r13
0x180055063  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@PEBGV?$allocator@PEBG@std@@@2@UKeyCompareLess@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@PEBGV?$allocator@PEBG@std@@@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@PEBGV?$allocator@PEBG@std@@@2@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::vector<ushort const *>,KeyCompareLess,std::allocator<std::pair<std::wstring const,std::vector<ushort const *>>>,0>>::find(std::wstring const &)
0x180055068  lea     rdx, [rsp+138h+var_B0]
0x180055070  mov     rcx, r13
0x180055073  call    ?begin@?$vector@IV?$allocator@_N@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@I@std@@@std@@@2@XZ; std::vector<uint>::begin(void)
0x180055078  mov     rdx, rax
0x18005507b  lea     rcx, [rsp+138h+var_D0]
  ... truncated ...
```
