# InstallLayoutOrTipPrivateHelpers::WriteSortOrder(CInputDllRegKey &,CInputDllRegKey &,CSortOrder &)

- ea: `0x1800040e0`
- end: `0x18000450d`
- name: `?WriteSortOrder@InstallLayoutOrTipPrivateHelpers@@SAXAEAVCInputDllRegKey@@0AEAVCSortOrder@@@Z`
- size: `1069`
- prototype: `void __fastcall(struct CInputDllRegKey *this, struct CInputDllRegKey *, struct CSortOrder *)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180005500`
- `0x180096a78`

## callees

- `0x180002820`
- `0x180002d2c`
- `0x1800040e0`
- `0x180004b70`
- `0x180007fc0`
- `0x18006c000`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180004132`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180004132`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000432a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004410`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000432a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004410`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004261`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004368`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800043af`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800043f3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004261`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004368`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800043af`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800043f3`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000430b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800044e6`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000430b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800044e6`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180004490`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180004490`

## string_xrefs

- `0x18000439d`: `CLSID`

## pseudocode

```c
void __fastcall InstallLayoutOrTipPrivateHelpers::WriteSortOrder(
        HKEY *this,
        struct CInputDllRegKey *a2,
        struct CSortOrder *a3)
{
  HKEY *v4; // rsi
  struct CSortOrder *v5; // rdi
  _QWORD *i; // rbx
  __int64 *v7; // r13
  unsigned int v8; // edx
  unsigned int v9; // ebx
  _QWORD *j; // rax
  __int64 v11; // rcx
  _QWORD *v12; // rdi
  unsigned int v13; // r12d
  __int64 v14; // rax
  bool v15; // zf
  _QWORD *v16; // r14
  int v17; // r15d
  struct CInputDllRegKey *v18; // r13
  HKEY v19; // rsi
  HKEY v20; // rdi
  LSTATUS v21; // eax
  LSTATUS v22; // ebx
  __int64 v23; // rax
  const BYTE *v24; // rcx
  __int64 v25; // rax
  const BYTE *v26; // rdx
  __int64 cbData; // [rsp+28h] [rbp-D8h]
  DWORD dwDisposition; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v29; // [rsp+54h] [rbp-ACh]
  HKEY phkResult; // [rsp+58h] [rbp-A8h] BYREF
  struct CSortOrder *v31; // [rsp+60h] [rbp-A0h]
  BYTE lpData[8]; // [rsp+68h] [rbp-98h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-90h] BYREF
  LPOLESTR lpsz; // [rsp+78h] [rbp-88h] BYREF
  __int64 *v35; // [rsp+80h] [rbp-80h]
  void **v36; // [rsp+88h] [rbp-78h] BYREF
  __int64 v37; // [rsp+90h] [rbp-70h]
  struct CInputDllRegKey *v38; // [rsp+98h] [rbp-68h]
  struct CInputDllRegKey *v39; // [rsp+A0h] [rbp-60h]
  unsigned __int16 Data[12]; // [rsp+A8h] [rbp-58h] BYREF
  WCHAR ValueName[16]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR SubKey[256]; // [rsp+E0h] [rbp-20h] BYREF

  v38 = a2;
  v4 = this;
  v39 = (struct CInputDllRegKey *)this;
  v31 = a3;
  lpsz = 0;
  v5 = a3;
  StringFromCLSID(&GUID_TFCAT_TIP_KEYBOARD, &lpsz);
  CInputDllRegKey::RecurseDeleteKey((CInputDllRegKey *)v4, &sourceString, 0);
  CInputDllRegKey::RecurseDeleteKey(a2, &sourceString, 0);
  CList<SortOrderItem *>::QuickSort(v5);
  for ( i = (_QWORD *)*((_QWORD *)v5 + 8); i; i = (_QWORD *)*i )
    CList<SortOrderItem *>::QuickSort(i[2] + 8LL);
  v7 = *(__int64 **)v5;
  v8 = 0;
  v35 = v7;
  while ( v7 )
  {
    v9 = *(unsigned __int16 *)v7[2];
    for ( j = (_QWORD *)*((_QWORD *)v5 + 8); ; j = (_QWORD *)*j )
    {
      if ( !j )
        goto LABEL_31;
      v11 = j[2];
      if ( *(_WORD *)v11 == (_WORD)v9 )
        break;
    }
    v12 = (_QWORD *)(v11 + 8);
    if ( v11 != -8 && *(_DWORD *)(v11 + 24) )
    {
      v29 = v8 + 1;
      StringCchPrintfW(ValueName, 9u, L"%08d", v8);
      v13 = v9;
      StringCchPrintfW(Data, 9u, L"%08x", v9);
      v14 = -1;
      do
        v15 = Data[++v14] == 0;
      while ( !v15 );
      RegSetValueExW(v4[1], ValueName, 0, 1u, (const BYTE *)Data, 2 * v14 + 2);
      v16 = (_QWORD *)*v12;
      v17 = 0;
      if ( *v12 )
      {
        v18 = v38;
        while ( 1 )
        {
          v36 = &CInputDllRegKey::`vftable';
          v37 = 0;
          LODWORD(cbData) = v17;
          v19 = 0;
          ++v17;
          StringCchPrintfW(SubKey, 0x100u, L"0x%08x\\%s\\%08d", v13, lpsz, cbData);
          v20 = (HKEY)*((_QWORD *)v18 + 1);
          dwDisposition = 0;
          phkResult = 0;
          hKey = 0;
          if ( v20 == HKEY_CURRENT_USER && !RegOpenCurrentUser(0x2001Fu, &hKey) )
            v20 = hKey;
          v21 = RegCreateKeyExW(v20, SubKey, 0, 0, 0, 0x2001Fu, 0, &phkResult, &dwDisposition);
          v22 = v21;
          if ( v21 )
          {
            if ( v21 != 5 )
              goto LABEL_17;
            v22 = RegCreateKeyExW(v20, SubKey, 0, 0, 4u, 0x2001Fu, 0, &phkResult, &dwDisposition);
            if ( v22 )
              goto LABEL_17;
            v22 = CInputDllRegKey::Close((CInputDllRegKey *)&v36);
          }
          v19 = phkResult;
LABEL_17:
          if ( hKey )
            RegCloseKey(hKey);
          if ( !v22 )
          {
            *(_DWORD *)lpData = *(_DWORD *)(v16[2] + 4LL);
            RegSetValueExW(v19, L"KeyboardLayout", 0, 4u, lpData, 4u);
            v23 = -1;
            v24 = (const BYTE *)(v16[2] + 20LL);
            do
              v15 = *(_WORD *)&v24[2 * v23++ + 2] == 0;
            while ( !v15 );
            RegSetValueExW(v19, L"CLSID", 0, 1u, v24, 2 * v23 + 2);
            v25 = -1;
            v26 = (const BYTE *)(v16[2] + 98LL);
            do
              v15 = *(_WORD *)&v26[2 * v25++ + 2] == 0;
            while ( !v15 );
            RegSetValueExW(v19, L"Profile", 0, 1u, v26, 2 * v25 + 2);
          }
          v36 = &CInputDllRegKey::`vftable';
          if ( v19 )
          {
            RegCloseKey(v19);
            v37 = 0;
          }
          v16 = (_QWORD *)*v16;
          if ( !v16 )
          {
            v7 = v35;
            v4 = (HKEY *)v39;
            break;
          }
        }
      }
      v8 = v29;
    }
    v5 = v31;
LABEL_31:
    v7 = (__int64 *)*v7;
    v35 = v7;
  }
}

```

## disassembly

```asm
0x1800040e0  push    rbp
0x1800040e2  push    rbx
0x1800040e3  push    rsi
0x1800040e4  push    rdi
0x1800040e5  push    r13
0x1800040e7  lea     rbp, [rsp-200h]
0x1800040ef  sub     rsp, 300h
0x1800040f6  mov     rax, cs:__security_cookie
0x1800040fd  xor     rax, rsp
0x180004100  mov     [rbp+220h+var_40], rax
0x180004107  mov     rbx, rdx
0x18000410a  mov     [rbp+220h+var_288], rdx
0x18000410e  mov     rsi, rcx
0x180004111  mov     [rbp+220h+var_280], rcx
0x180004115  lea     rdx, [rsp+320h+lpsz]; lplpsz
0x18000411a  mov     [rsp+320h+var_2C0], r8
0x18000411f  lea     rcx, GUID_TFCAT_TIP_KEYBOARD; rclsid
0x180004126  mov     [rsp+320h+lpsz], 0
0x18000412f  mov     rdi, r8
0x180004132  call    cs:__imp_StringFromCLSID
0x180004138  xor     r8d, r8d; int
0x18000413b  lea     rdx, sourceString; unsigned __int16 *
0x180004142  mov     rcx, rsi; this
0x180004145  call    ?RecurseDeleteKey@CInputDllRegKey@@QEAAJPEBGH@Z; CInputDllRegKey::RecurseDeleteKey(ushort const *,int)
0x18000414a  xor     r8d, r8d; int
0x18000414d  lea     rdx, sourceString; unsigned __int16 *
0x180004154  mov     rcx, rbx; this
0x180004157  call    ?RecurseDeleteKey@CInputDllRegKey@@QEAAJPEBGH@Z; CInputDllRegKey::RecurseDeleteKey(ushort const *,int)
0x18000415c  mov     rcx, rdi
0x18000415f  call    ?QuickSort@?$CList@PEAUSortOrderItem@@@@QEAAJP6AHPEAX0@Z@Z; CList<SortOrderItem *>::QuickSort(int (*)(void *,void *))
0x180004164  mov     rbx, [rdi+40h]
0x180004168  test    rbx, rbx
0x18000416b  jz      short loc_180004185
0x18000416d  nop     dword ptr [rax]
0x180004170  mov     rcx, [rbx+10h]
0x180004174  add     rcx, 8
0x180004178  call    ?QuickSort@?$CList@PEAUSortOrderItem@@@@QEAAJP6AHPEAX0@Z@Z; CList<SortOrderItem *>::QuickSort(int (*)(void *,void *))
0x18000417d  mov     rbx, [rbx]
0x180004180  test    rbx, rbx
0x180004183  jnz     short loc_180004170
0x180004185  mov     r13, [rdi]
0x180004188  xor     edx, edx
0x18000418a  mov     [rbp+220h+var_2A0], r13
0x18000418e  test    r13, r13
0x180004191  jz      loc_180004469
0x180004197  mov     [rsp+320h+arg_18], r12
0x18000419f  mov     [rsp+320h+var_28], r14
0x1800041a7  mov     [rsp+320h+var_30], r15
0x1800041af  nop
0x1800041b0  mov     rax, [r13+10h]
0x1800041b4  movzx   ebx, word ptr [rax]
0x1800041b7  mov     rax, [rdi+40h]
0x1800041bb  test    rax, rax
0x1800041be  jz      loc_180004440
0x1800041c4  mov     rcx, [rax+10h]
0x1800041c8  cmp     [rcx], bx
0x1800041cb  jz      short loc_1800041D2
0x1800041cd  mov     rax, [rax]
0x1800041d0  jmp     short loc_1800041BB
0x1800041d2  lea     rdi, [rcx+8]
0x1800041d6  test    rdi, rdi
0x1800041d9  jz      loc_18000443B
0x1800041df  cmp     dword ptr [rdi+10h], 0
0x1800041e3  jbe     loc_18000443B
0x1800041e9  mov     r9d, edx
0x1800041ec  lea     r8, a08d; "%08d"
0x1800041f3  inc     edx
0x1800041f5  lea     rcx, [rbp+220h+ValueName]; unsigned __int16 *
0x1800041f9  mov     [rsp+320h+var_2CC], edx
0x1800041fd  mov     edx, 9; unsigned __int64
0x180004202  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180004207  mov     r9d, ebx
0x18000420a  lea     r8, a08x_1; "%08x"
0x180004211  mov     edx, 9; unsigned __int64
0x180004216  lea     rcx, [rbp+220h+Data]; unsigned __int16 *
0x18000421a  mov     r12d, ebx
0x18000421d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180004222  lea     rcx, [rbp+220h+Data]
0x180004226  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000422d  nop     dword ptr [rax]
0x180004230  cmp     word ptr [rcx+rax*2+2], 0
0x180004236  lea     rax, [rax+1]
0x18000423a  jnz     short loc_180004230
0x18000423c  mov     rcx, [rsi+8]; hKey
0x180004240  lea     eax, ds:2[rax*2]
0x180004247  mov     dword ptr [rsp+320h+cbData], eax; cbData
0x18000424b  lea     rdx, [rbp+220h+ValueName]; lpValueName
0x18000424f  lea     rax, [rbp+220h+Data]
0x180004253  mov     r9d, 1; dwType
0x180004259  xor     r8d, r8d; Reserved
0x18000425c  mov     [rsp+320h+lpData], rax; lpData
0x180004261  call    cs:__imp_RegSetValueExW
0x180004267  mov     r14, [rdi]
0x18000426a  xor     ebx, ebx
0x18000426c  mov     r15d, ebx
0x18000426f  test    r14, r14
0x180004272  jz      loc_180004437
0x180004278  mov     r13, [rbp+220h+var_288]
0x18000427c  lea     rax, ??_7CInputDllRegKey@@6B@; const CInputDllRegKey::`vftable'
0x180004283  mov     [rbp+220h+var_298], rax
0x180004287  lea     r8, a0x08xS08d; "0x%08x\\%s\\%08d"
0x18000428e  mov     eax, r15d
0x180004291  mov     [rbp+220h+var_290], rbx
0x180004295  mov     dword ptr [rsp+320h+cbData], eax
0x180004299  lea     rcx, [rbp+220h+SubKey]; unsigned __int16 *
0x18000429d  mov     rax, [rsp+320h+lpsz]
0x1800042a2  mov     r9d, r12d
0x1800042a5  mov     edx, 100h; unsigned __int64
0x1800042aa  mov     [rsp+320h+lpData], rax
0x1800042af  mov     rsi, rbx
0x1800042b2  inc     r15d
0x1800042b5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800042ba  mov     rdi, [r13+8]
0x1800042be  mov     [rsp+320h+dwDisposition], ebx
0x1800042c2  mov     [rsp+320h+var_2C8], rbx
0x1800042c7  mov     [rsp+320h+hKey], rbx
0x1800042cc  cmp     rdi, 0FFFFFFFF80000001h
0x1800042d3  jz      loc_180004486
0x1800042d9  lea     rax, [rsp+320h+dwDisposition]
0x1800042de  xor     r9d, r9d; lpClass
0x1800042e1  mov     [rsp+320h+lpdwDisposition], rax; lpdwDisposition
0x1800042e6  lea     rdx, [rbp+220h+SubKey]; lpSubKey
0x1800042ea  lea     rax, [rsp+320h+var_2C8]
0x1800042ef  xor     r8d, r8d; Reserved
0x1800042f2  mov     [rsp+320h+phkResult], rax; phkResult
0x1800042f7  mov     rcx, rdi; hKey
0x1800042fa  mov     [rsp+320h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x1800042ff  mov     dword ptr [rsp+320h+cbData], 2001Fh; samDesired
0x180004307  mov     dword ptr [rsp+320h+lpData], ebx; dwOptions
0x18000430b  call    cs:__imp_RegCreateKeyExW
0x180004311  mov     ebx, eax
0x180004313  test    eax, eax
0x180004315  jnz     loc_1800044A3
0x18000431b  mov     rsi, [rsp+320h+var_2C8]
0x180004320  mov     rcx, [rsp+320h+hKey]; hKey
0x180004325  test    rcx, rcx
0x180004328  jz      short loc_180004330
0x18000432a  call    cs:__imp_RegCloseKey
0x180004330  test    ebx, ebx
0x180004332  jnz     loc_1800043F9
0x180004338  mov     rax, [r14+10h]
0x18000433c  lea     rdx, ?c_szKeyboardLayout@@3QBGB; "KeyboardLayout"
0x180004343  mov     dword ptr [rsp+320h+cbData], 4; cbData
0x18000434b  mov     r9d, 4; dwType
0x180004351  xor     r8d, r8d; Reserved
0x180004354  mov     ecx, [rax+4]
0x180004357  lea     rax, [rsp+320h+var_2B8]
0x18000435c  mov     dword ptr [rsp+320h+var_2B8], ecx
0x180004360  mov     rcx, rsi; hKey
0x180004363  mov     [rsp+320h+lpData], rax; lpData
0x180004368  call    cs:__imp_RegSetValueExW
0x18000436e  mov     rcx, [r14+10h]
0x180004372  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180004379  add     rcx, 14h
0x18000437d  nop     dword ptr [rax]
0x180004380  cmp     word ptr [rcx+rax*2+2], 0
0x180004386  lea     rax, [rax+1]
0x18000438a  jnz     short loc_180004380
0x18000438c  lea     eax, ds:2[rax*2]
0x180004393  mov     r9d, 1; dwType
0x180004399  mov     dword ptr [rsp+320h+cbData], eax; cbData
0x18000439d  lea     rdx, ?c_szCLSID@@3QBGB; "CLSID"
0x1800043a4  mov     [rsp+320h+lpData], rcx; lpData
0x1800043a9  xor     r8d, r8d; Reserved
0x1800043ac  mov     rcx, rsi; hKey
0x1800043af  call    cs:__imp_RegSetValueExW
0x1800043b5  mov     rdx, [r14+10h]
0x1800043b9  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800043c0  add     rdx, 62h ; 'b'
0x1800043c4  cmp     word ptr [rdx+rax*2+2], 0
0x1800043ca  lea     rax, [rax+1]
0x1800043ce  jnz     short loc_1800043C4
0x1800043d0  lea     eax, ds:2[rax*2]
0x1800043d7  mov     r9d, 1; dwType
0x1800043dd  mov     dword ptr [rsp+320h+cbData], eax; cbData
0x1800043e1  xor     r8d, r8d; Reserved
0x1800043e4  mov     [rsp+320h+lpData], rdx; lpData
0x1800043e9  mov     rcx, rsi; hKey
0x1800043ec  lea     rdx, ?c_szProfile@@3QBGB; "Profile"
0x1800043f3  call    cs:__imp_RegSetValueExW
0x1800043f9  lea     rax, ??_7CInputDllRegKey@@6B@; const CInputDllRegKey::`vftable'
0x180004400  mov     [rbp+220h+var_298], rax
0x180004404  test    rsi, rsi
0x180004407  jz      loc_180004506
0x18000440d  mov     rcx, rsi; hKey
0x180004410  call    cs:__imp_RegCloseKey
0x180004416  xor     ebx, ebx
0x180004418  lea     rax, ??_7CInputDllRegKey@@6B@; const CInputDllRegKey::`vftable'
0x18000441f  mov     [rbp+220h+var_290], rbx
0x180004423  mov     r14, [r14]
0x180004426  test    r14, r14
0x180004429  jnz     loc_180004283
0x18000442f  mov     r13, [rbp+220h+var_2A0]
0x180004433  mov     rsi, [rbp+220h+var_280]
0x180004437  mov     edx, [rsp+320h+var_2CC]
0x18000443b  mov     rdi, [rsp+320h+var_2C0]
0x180004440  mov     r13, [r13+0]
0x180004444  mov     [rbp+220h+var_2A0], r13
0x180004448  test    r13, r13
0x18000444b  jnz     loc_1800041B0
0x180004451  mov     r15, [rsp+320h+var_30]
0x180004459  mov     r14, [rsp+320h+var_28]
0x180004461  mov     r12, [rsp+320h+arg_18]
0x180004469  mov     rcx, [rbp+220h+var_40]
0x180004470  xor     rcx, rsp; StackCookie
0x180004473  call    __security_check_cookie
0x180004478  add     rsp, 300h
0x18000447f  pop     r13
0x180004481  pop     rdi
0x180004482  pop     rsi
0x180004483  pop     rbx
0x180004484  pop     rbp
0x180004485  retn
0x180004486  lea     rdx, [rsp+320h+hKey]; phkResult
0x18000448b  mov     ecx, 2001Fh; samDesired
0x180004490  call    cs:__imp_RegOpenCurrentUser
0x180004496  test    eax, eax
0x180004498  cmovz   rdi, [rsp+320h+hKey]
0x18000449e  jmp     loc_1800042D9
0x1800044a3  cmp     eax, 5
0x1800044a6  jnz     loc_180004320
0x1800044ac  lea     rax, [rsp+320h+dwDisposition]
0x1800044b1  xor     r9d, r9d; lpClass
0x1800044b4  mov     [rsp+320h+lpdwDisposition], rax; lpdwDisposition
0x1800044b9  lea     rdx, [rbp+220h+SubKey]; lpSubKey
0x1800044bd  lea     rax, [rsp+320h+var_2C8]
0x1800044c2  xor     r8d, r8d; Reserved
0x1800044c5  mov     [rsp+320h+phkResult], rax; phkResult
0x1800044ca  mov     rcx, rdi; hKey
0x1800044cd  mov     [rsp+320h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800044d6  mov     dword ptr [rsp+320h+cbData], 2001Fh; samDesired
0x1800044de  mov     dword ptr [rsp+320h+lpData], 4; dwOptions
0x1800044e6  call    cs:__imp_RegCreateKeyExW
0x1800044ec  mov     ebx, eax
0x1800044ee  test    eax, eax
0x1800044f0  jnz     loc_180004320
0x1800044f6  lea     rcx, [rbp+220h+var_298]; this
0x1800044fa  call    ?Close@CInputDllRegKey@@QEAAJXZ; CInputDllRegKey::Close(void)
0x1800044ff  mov     ebx, eax
0x180004501  jmp     loc_18000431B
0x180004506  xor     ebx, ebx
0x180004508  jmp     loc_180004423
```
