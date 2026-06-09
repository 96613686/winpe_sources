# RegSaveRestoreW

- ea: `0x180014440`
- end: `0x18001488e`
- name: `RegSaveRestoreW`
- size: `1102`
- prototype: `HRESULT __stdcall(HWND hWnd, LPCWSTR pszTitleString, HKEY hkBckupKey, LPCWSTR pcszRootKey, LPCWSTR pcszSubKey, LPCWSTR pcszValueName, DWORD dwFlags)`
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000da30`
- `0x180012f48`
- `0x180014350`

## callees

- `0x1800022bc`
- `0x180008a6c`
- `0x1800121d8`
- `0x1800127bc`
- `0x180012d50`
- `0x180013acc`
- `0x180013c98`
- `0x180014440`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180014694`
- `KERNEL32!LocalFree` at `0x1800146f2`
- `KERNEL32!LocalFree` at `0x180014780`
- `KERNEL32!LocalFree` at `0x1800147a4`
- `KERNEL32!LocalFree` at `0x180014841`
- `KERNEL32!LocalFree` at `0x180014694`
- `KERNEL32!LocalFree` at `0x1800146f2`
- `KERNEL32!LocalFree` at `0x180014780`
- `KERNEL32!LocalFree` at `0x1800147a4`
- `KERNEL32!LocalFree` at `0x180014841`
- `KERNEL32!CloseHandle` at `0x180014824`
- `KERNEL32!CloseHandle` at `0x180014824`
- `KERNEL32!LocalAlloc` at `0x18001457c`
- `KERNEL32!LocalAlloc` at `0x180014640`
- `KERNEL32!LocalAlloc` at `0x1800146b5`
- `KERNEL32!LocalAlloc` at `0x18001457c`
- `KERNEL32!LocalAlloc` at `0x180014640`
- `KERNEL32!LocalAlloc` at `0x1800146b5`
- `KERNEL32!CompareStringW` at `0x180014550`
- `KERNEL32!CompareStringW` at `0x180014550`
- `ADVAPI32!RegCloseKey` at `0x18001461a`
- `ADVAPI32!RegCloseKey` at `0x18001461a`
- `ADVAPI32!RegOpenKeyExW` at `0x1800145e9`
- `ADVAPI32!RegOpenKeyExW` at `0x1800145e9`

## pseudocode

```c
HRESULT __stdcall RegSaveRestoreW(
        HWND hWnd,
        LPCWSTR pszTitleString,
        HKEY hkBckupKey,
        LPCWSTR pcszRootKey,
        LPCWSTR pcszSubKey,
        LPCWSTR pcszValueName,
        DWORD dwFlags)
{
  HWND v8; // r13
  __int16 v10; // r12
  DWORD v11; // ebx
  LPCWSTR v12; // rsi
  int v13; // ecx
  const WCHAR *v14; // rcx
  unsigned int i; // edi
  const unsigned __int16 *v16; // r8
  UINT v17; // edx
  int v18; // eax
  int v19; // ecx
  WCHAR *v20; // rax
  unsigned int v21; // ecx
  const unsigned __int16 *v22; // rdx
  HKEY v23; // rcx
  const unsigned __int16 *v24; // r8
  const unsigned __int16 *v25; // r9
  int v27; // eax
  const unsigned __int16 *v28; // rdx
  HKEY v29; // rcx
  const unsigned __int16 *v30; // r8
  const unsigned __int16 *v31; // r9
  const WCHAR *v33; // [rsp+80h] [rbp+8h]

  v8 = ::hWnd;
  v10 = word_1800257D2;
  v11 = dwFlags;
  v33 = ::pszTitleString;
  g_fAtleastOneRegSaved = 0;
  g_bRet = 0;
  if ( hWnd != HWND_MESSAGE|0x2LL && (dwFlags & 8) == 0 || (word_1800257D2 |= 1u, hWnd != HWND_MESSAGE|0x2LL) )
    ::hWnd = hWnd;
  if ( pszTitleString )
    ::pszTitleString = pszTitleString;
  v12 = pcszValueName;
  g_hkBckupKey = hkBckupKey;
  g_pcszRootKey = (unsigned __int16 *)pcszRootKey;
  g_pcszValueName = (unsigned __int16 *)pcszValueName;
  g_fRestore = dwFlags & 1;
  if ( (dwFlags & 0x1000) == 0 || (v13 = 1, (dwFlags & 1) == 0) )
    v13 = 0;
  g_fRemovBkData = v13;
  v14 = L"RegRestoreLogFile";
  if ( (dwFlags & 1) == 0 )
    v14 = L"RegSaveLogFile";
  StartLogging(v14);
  for ( i = 0; ; ++i )
  {
    if ( i >= 9 )
    {
      v16 = pcszRootKey;
      v17 = 1151;
      goto LABEL_51;
    }
    if ( CompareStringW(0x7Fu, 1u, (&off_180025050)[2 * (int)i], -1, pcszRootKey, -1) == 2 )
      break;
  }
  g_hkRootKey = (HKEY)*(&off_180025050 + 2 * (int)i + 1);
  g_pszCRCTempBuf = LocalAlloc(0x40u, 0xC00u);
  if ( !g_pszCRCTempBuf )
    goto LABEL_17;
  if ( g_fRestore )
  {
    if ( !v12 )
      goto LABEL_27;
LABEL_47:
    g_pszCRCSubKey = (LPWSTR)pcszSubKey;
    g_pszSubKey = pcszSubKey;
    v27 = RegSaveRestoreHelperWrapper(g_pcszValueName, g_pcszValueName);
    g_bRet = v27;
    if ( (v11 & 0x40) == 0 && v27 )
      g_bRet = AddDelMapping(v29, v28, v30, v31, v11);
    goto LABEL_52;
  }
  if ( v12 || (v11 & 0x20) != 0 )
    goto LABEL_47;
  pcszValueName = 0;
  if ( RegOpenKeyExW(g_hkRootKey, pcszSubKey, 0, 0x20019u, (PHKEY)&pcszValueName) )
  {
    v18 = MappingExists(hkBckupKey, pcszRootKey, pcszSubKey, 0);
    v19 = v11 | 0x20;
    if ( v18 )
      v19 = v11;
    v11 = v19;
  }
  else
  {
    RegCloseKey((HKEY)pcszValueName);
  }
LABEL_27:
  if ( (v11 & 0x20) != 0 )
    goto LABEL_47;
  v20 = (WCHAR *)LocalAlloc(0x40u, 0x800u);
  g_pszCRCSubKey = v20;
  if ( !v20 )
  {
LABEL_17:
    v16 = 0;
    v17 = 1102;
LABEL_51:
    MsgBox2Param(::hWnd, v17, v16, 0, 0x10u, 0);
    goto LABEL_52;
  }
  v21 = 1024;
  LODWORD(g_cchCRCSubKey) = 1024;
  if ( g_fRestore )
  {
    g_pszSubKey = pcszSubKey;
  }
  else
  {
    if ( (unsigned int)MappingExists(hkBckupKey, pcszRootKey, pcszSubKey, 0) )
    {
      g_bRet = 1;
      LocalFree(g_pszCRCSubKey);
      g_pszCRCSubKey = 0;
LABEL_32:
      LODWORD(g_cchCRCSubKey) = 0;
      goto LABEL_52;
    }
    g_pszSubKey = (LPCWSTR)LocalAlloc(0x40u, 0x800u);
    if ( !g_pszSubKey )
    {
      MsgBox2Param(::hWnd, 0x44Eu, 0, 0, 0x10u, 0);
      LocalFree(g_pszCRCSubKey);
      goto LABEL_32;
    }
    v20 = g_pszCRCSubKey;
    v21 = g_cchCRCSubKey;
  }
  g_bRet = 1;
  StringCchCopyW(v20, v21, (size_t *)pcszSubKey);
  if ( !g_fRestore )
    StringCchCopyW((unsigned __int16 *)g_pszSubKey, (unsigned int)g_cchCRCSubKey, (size_t *)pcszSubKey);
  EnumerateSubKey();
  if ( (v11 & 0x40) == 0 && !(g_fRestore ? g_bRet == 0 : g_fAtleastOneRegSaved == 0) )
    g_bRet = AddDelMapping(v23, v22, v24, v25, v11);
  LocalFree(g_pszCRCSubKey);
  g_pszCRCSubKey = 0;
  LODWORD(g_cchCRCSubKey) = 0;
  if ( !g_fRestore )
  {
    LocalFree((HLOCAL)g_pszSubKey);
    g_pszSubKey = 0;
  }
LABEL_52:
  if ( g_hLogFile != (HANDLE)-1LL )
  {
    CloseHandle(g_hLogFile);
    g_hLogFile = (HANDLE)-1LL;
  }
  if ( g_pszCRCTempBuf )
  {
    LocalFree(g_pszCRCTempBuf);
    g_pszCRCTempBuf = 0;
  }
  ::pszTitleString = v33;
  ::hWnd = v8;
  word_1800257D2 = v10;
  return g_bRet == 0 ? 0x80004005 : 0;
}

```

## disassembly

```asm
0x180014440  push    rbx
0x180014442  push    rbp
0x180014443  push    rsi
0x180014444  push    rdi
0x180014445  push    r12
0x180014447  push    r13
0x180014449  push    r14
0x18001444b  push    r15
0x18001444d  sub     rsp, 38h
0x180014451  mov     r14, cs:pszTitleString
0x180014458  mov     r15, r8
0x18001445b  mov     r13, cs:hWnd
0x180014462  mov     rbp, r9
0x180014465  movzx   r12d, cs:word_1800257D2
0x18001446d  mov     ebx, [rsp+78h+dwFlags]
0x180014474  mov     [rsp+78h+arg_0], r14
0x18001447c  xor     r14d, r14d
0x18001447f  mov     cs:?g_fAtleastOneRegSaved@@3HA, r14d; int g_fAtleastOneRegSaved
0x180014486  mov     cs:?g_bRet@@3HA, r14d; int g_bRet
0x18001448d  lea     r8d, [r14+1]
0x180014491  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180014495  jz      short loc_18001449C
0x180014497  test    bl, 8
0x18001449a  jz      short loc_1800144B1
0x18001449c  movzx   eax, r12w
0x1800144a0  or      ax, r8w
0x1800144a4  mov     cs:word_1800257D2, ax
0x1800144ab  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800144af  jz      short loc_1800144B8
0x1800144b1  mov     cs:hWnd, rcx
0x1800144b8  test    rdx, rdx
0x1800144bb  jz      short loc_1800144C4
0x1800144bd  mov     cs:pszTitleString, rdx
0x1800144c4  mov     rsi, [rsp+78h+pcszValueName]
0x1800144cc  mov     eax, ebx
0x1800144ce  and     eax, r8d
0x1800144d1  mov     cs:?g_hkBckupKey@@3PEAUHKEY__@@EA, r15; HKEY__ * g_hkBckupKey
0x1800144d8  mov     cs:?g_pcszRootKey@@3PEBGEB, rbp; ushort const * const g_pcszRootKey
0x1800144df  mov     cs:?g_pcszValueName@@3PEBGEB, rsi; ushort const * const g_pcszValueName
0x1800144e6  mov     cs:?g_fRestore@@3HA, eax; int g_fRestore
0x1800144ec  bt      ebx, 0Ch
0x1800144f0  jnb     short loc_1800144F9
0x1800144f2  mov     ecx, r8d
0x1800144f5  test    eax, eax
0x1800144f7  jnz     short loc_1800144FC
0x1800144f9  mov     ecx, r14d
0x1800144fc  mov     cs:?g_fRemovBkData@@3HA, ecx; int g_fRemovBkData
0x180014502  lea     rdx, aRegsavelogfile; "RegSaveLogFile"
0x180014509  test    eax, eax
0x18001450b  lea     rcx, aRegrestorelogf; "RegRestoreLogFile"
0x180014512  cmovz   rcx, rdx; lpValueName
0x180014516  call    ?StartLogging@@YAXPEBG@Z; StartLogging(ushort const *)
0x18001451b  lea     rax, off_180025050; "HKEY_LOCAL_MACHINE"
0x180014522  mov     edi, r14d
0x180014525  cmp     edi, 9
0x180014528  jnb     loc_1800147F0
0x18001452e  or      r9d, 0FFFFFFFFh; cchCount1
0x180014532  movsxd  r14, edi
0x180014535  add     r14, r14
0x180014538  mov     [rsp+78h+cchCount2], 0FFFFFFFFh; cchCount2
0x180014540  mov     [rsp+78h+lpString2], rbp; lpString2
0x180014545  lea     edx, [r9+2]; dwCmpFlags
0x180014549  mov     r8, [rax+r14*8]; lpString1
0x18001454d  lea     ecx, [rdx+7Eh]; Locale
0x180014550  call    cs:__imp_CompareStringW
0x180014556  cmp     eax, 2
0x180014559  lea     rax, off_180025050; "HKEY_LOCAL_MACHINE"
0x180014560  jz      short loc_180014566
0x180014562  inc     edi
0x180014564  jmp     short loc_180014525
0x180014566  mov     rax, [rax+r14*8+8]
0x18001456b  mov     edx, 0C00h; uBytes
0x180014570  mov     ecx, 40h ; '@'; uFlags
0x180014575  mov     cs:?g_hkRootKey@@3PEAUHKEY__@@EA, rax; HKEY__ * g_hkRootKey
0x18001457c  call    cs:__imp_LocalAlloc
0x180014582  xor     r14d, r14d
0x180014585  mov     cs:?g_pszCRCTempBuf@@3PEAGEA, rax; ushort * g_pszCRCTempBuf
0x18001458c  test    rax, rax
0x18001458f  jnz     short loc_18001459E
0x180014591  xor     r8d, r8d
0x180014594  mov     edx, 44Eh
0x180014599  jmp     loc_1800147FB
0x18001459e  cmp     cs:?g_fRestore@@3HA, r14d; int g_fRestore
0x1800145a5  mov     rdi, [rsp+78h+pcszSubKey]
0x1800145ad  jnz     short loc_180014622
0x1800145af  test    rsi, rsi
0x1800145b2  jnz     loc_1800147B3
0x1800145b8  test    bl, 20h
0x1800145bb  jnz     loc_1800147B3
0x1800145c1  mov     rcx, cs:?g_hkRootKey@@3PEAUHKEY__@@EA; hKey
0x1800145c8  lea     rax, [rsp+78h+pcszValueName]
0x1800145d0  mov     r9d, 20019h; samDesired
0x1800145d6  mov     [rsp+78h+lpString2], rax; phkResult
0x1800145db  xor     r8d, r8d; ulOptions
0x1800145de  mov     [rsp+78h+pcszValueName], r14
0x1800145e6  mov     rdx, rdi; lpSubKey
0x1800145e9  call    cs:__imp_RegOpenKeyExW
0x1800145ef  test    eax, eax
0x1800145f1  jz      short loc_180014612
0x1800145f3  xor     r9d, r9d; unsigned __int16 *
0x1800145f6  mov     r8, rdi; unsigned __int16 *
0x1800145f9  mov     rdx, rbp; unsigned __int16 *
0x1800145fc  mov     rcx, r15; hKey
0x1800145ff  call    ?MappingExists@@YAHPEAUHKEY__@@PEBG11@Z; MappingExists(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x180014604  mov     ecx, ebx
0x180014606  or      ecx, 20h
0x180014609  test    eax, eax
0x18001460b  cmovnz  ecx, ebx
0x18001460e  mov     ebx, ecx
0x180014610  jmp     short loc_18001462B
0x180014612  mov     rcx, [rsp+78h+pcszValueName]; hKey
0x18001461a  call    cs:__imp_RegCloseKey
0x180014620  jmp     short loc_18001462B
0x180014622  test    rsi, rsi
0x180014625  jnz     loc_1800147B3
0x18001462b  test    bl, 20h
0x18001462e  jnz     loc_1800147B3
0x180014634  mov     esi, 800h
0x180014639  mov     ecx, 40h ; '@'; uFlags
0x18001463e  mov     edx, esi; uBytes
0x180014640  call    cs:__imp_LocalAlloc
0x180014646  mov     cs:?g_pszCRCSubKey@@3PEAGEA, rax; ushort * g_pszCRCSubKey
0x18001464d  test    rax, rax
0x180014650  jz      loc_180014591
0x180014656  cmp     cs:?g_fRestore@@3HA, r14d; int g_fRestore
0x18001465d  mov     ecx, 400h
0x180014662  mov     cs:?g_cchCRCSubKey@@3IA, ecx; uint g_cchCRCSubKey
0x180014668  jnz     loc_180014709
0x18001466e  xor     r9d, r9d; unsigned __int16 *
0x180014671  mov     r8, rdi; unsigned __int16 *
0x180014674  mov     rdx, rbp; unsigned __int16 *
0x180014677  mov     rcx, r15; hKey
0x18001467a  call    ?MappingExists@@YAHPEAUHKEY__@@PEBG11@Z; MappingExists(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x18001467f  test    eax, eax
0x180014681  jz      short loc_1800146AD
0x180014683  mov     rcx, cs:?g_pszCRCSubKey@@3PEAGEA; hMem
0x18001468a  mov     cs:?g_bRet@@3HA, 1; int g_bRet
0x180014694  call    cs:__imp_LocalFree
0x18001469a  mov     cs:?g_pszCRCSubKey@@3PEAGEA, r14; ushort * g_pszCRCSubKey
0x1800146a1  mov     cs:?g_cchCRCSubKey@@3IA, r14d; uint g_cchCRCSubKey
0x1800146a8  jmp     loc_180014817
0x1800146ad  mov     rdx, rsi; uBytes
0x1800146b0  mov     ecx, 40h ; '@'; uFlags
0x1800146b5  call    cs:__imp_LocalAlloc
0x1800146bb  mov     cs:?g_pszSubKey@@3PEAGEA, rax; ushort * g_pszSubKey
0x1800146c2  test    rax, rax
0x1800146c5  jnz     short loc_1800146FA
0x1800146c7  mov     rcx, cs:hWnd; hWnd
0x1800146ce  xor     r9d, r9d; unsigned __int16 *
0x1800146d1  mov     [rsp+78h+cchCount2], r14d; unsigned int
0x1800146d6  xor     r8d, r8d; unsigned __int16 *
0x1800146d9  mov     edx, 44Eh; uID
0x1800146de  mov     dword ptr [rsp+78h+lpString2], 10h; unsigned int
0x1800146e6  call    ?MsgBox2Param@@YAHPEAUHWND__@@IPEBG1II@Z; MsgBox2Param(HWND__ *,uint,ushort const *,ushort const *,uint,uint)
0x1800146eb  mov     rcx, cs:?g_pszCRCSubKey@@3PEAGEA; hMem
0x1800146f2  call    cs:__imp_LocalFree
0x1800146f8  jmp     short loc_1800146A1
0x1800146fa  mov     rax, cs:?g_pszCRCSubKey@@3PEAGEA; ushort * g_pszCRCSubKey
0x180014701  mov     ecx, cs:?g_cchCRCSubKey@@3IA; uint g_cchCRCSubKey
0x180014707  jmp     short loc_180014710
0x180014709  mov     cs:?g_pszSubKey@@3PEAGEA, rdi; ushort * g_pszSubKey
0x180014710  mov     edx, ecx; unsigned __int64
0x180014712  mov     r8, rdi; unsigned __int16 *
0x180014715  mov     rcx, rax; unsigned __int16 *
0x180014718  mov     cs:?g_bRet@@3HA, 1; int g_bRet
0x180014722  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180014727  cmp     cs:?g_fRestore@@3HA, r14d; int g_fRestore
0x18001472e  jnz     short loc_180014745
0x180014730  mov     edx, cs:?g_cchCRCSubKey@@3IA; unsigned __int64
0x180014736  mov     r8, rdi; unsigned __int16 *
0x180014739  mov     rcx, cs:?g_pszSubKey@@3PEAGEA; unsigned __int16 *
0x180014740  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180014745  call    ?EnumerateSubKey@@YAXXZ; EnumerateSubKey(void)
0x18001474a  test    bl, 40h
0x18001474d  jnz     short loc_180014779
0x18001474f  cmp     cs:?g_fRestore@@3HA, r14d; int g_fRestore
0x180014756  jz      short loc_180014761
0x180014758  cmp     cs:?g_bRet@@3HA, r14d; int g_bRet
0x18001475f  jmp     short loc_180014768
0x180014761  cmp     cs:?g_fAtleastOneRegSaved@@3HA, r14d; int g_fAtleastOneRegSaved
0x180014768  jz      short loc_180014779
0x18001476a  mov     dword ptr [rsp+78h+lpString2], ebx; unsigned int
0x18001476e  call    ?AddDelMapping@@YAHPEAUHKEY__@@PEBG11K@Z; AddDelMapping(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong)
0x180014773  mov     cs:?g_bRet@@3HA, eax; int g_bRet
0x180014779  mov     rcx, cs:?g_pszCRCSubKey@@3PEAGEA; hMem
0x180014780  call    cs:__imp_LocalFree
0x180014786  cmp     cs:?g_fRestore@@3HA, r14d; int g_fRestore
0x18001478d  mov     cs:?g_pszCRCSubKey@@3PEAGEA, r14; ushort * g_pszCRCSubKey
0x180014794  mov     cs:?g_cchCRCSubKey@@3IA, r14d; uint g_cchCRCSubKey
0x18001479b  jnz     short loc_180014817
0x18001479d  mov     rcx, cs:?g_pszSubKey@@3PEAGEA; hMem
0x1800147a4  call    cs:__imp_LocalFree
0x1800147aa  mov     cs:?g_pszSubKey@@3PEAGEA, r14; ushort * g_pszSubKey
0x1800147b1  jmp     short loc_180014817
0x1800147b3  mov     rcx, cs:?g_pcszValueName@@3PEBGEB; unsigned __int16 *
0x1800147ba  mov     rdx, rcx; unsigned __int16 *
0x1800147bd  mov     cs:?g_pszCRCSubKey@@3PEAGEA, rdi; ushort * g_pszCRCSubKey
0x1800147c4  mov     cs:?g_pszSubKey@@3PEAGEA, rdi; ushort * g_pszSubKey
0x1800147cb  call    ?RegSaveRestoreHelperWrapper@@YAHPEBG0@Z; RegSaveRestoreHelperWrapper(ushort const *,ushort const *)
0x1800147d0  mov     cs:?g_bRet@@3HA, eax; int g_bRet
0x1800147d6  test    bl, 40h
0x1800147d9  jnz     short loc_180014817
0x1800147db  test    eax, eax
0x1800147dd  jz      short loc_180014817
0x1800147df  mov     dword ptr [rsp+78h+lpString2], ebx; unsigned int
0x1800147e3  call    ?AddDelMapping@@YAHPEAUHKEY__@@PEBG11K@Z; AddDelMapping(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong)
0x1800147e8  mov     cs:?g_bRet@@3HA, eax; int g_bRet
0x1800147ee  jmp     short loc_180014817
0x1800147f0  xor     r14d, r14d
0x1800147f3  mov     r8, rbp; unsigned __int16 *
0x1800147f6  mov     edx, 47Fh; uID
0x1800147fb  mov     rcx, cs:hWnd; hWnd
0x180014802  xor     r9d, r9d; unsigned __int16 *
0x180014805  mov     [rsp+78h+cchCount2], r14d; unsigned int
0x18001480a  mov     dword ptr [rsp+78h+lpString2], 10h; unsigned int
0x180014812  call    ?MsgBox2Param@@YAHPEAUHWND__@@IPEBG1II@Z; MsgBox2Param(HWND__ *,uint,ushort const *,ushort const *,uint,uint)
0x180014817  mov     rcx, cs:?g_hLogFile@@3PEAXEA; hObject
0x18001481e  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180014822  jz      short loc_180014835
0x180014824  call    cs:__imp_CloseHandle
0x18001482a  mov     cs:?g_hLogFile@@3PEAXEA, 0FFFFFFFFFFFFFFFFh; void * g_hLogFile
0x180014835  mov     rcx, cs:?g_pszCRCTempBuf@@3PEAGEA; hMem
0x18001483c  test    rcx, rcx
0x18001483f  jz      short loc_18001484E
0x180014841  call    cs:__imp_LocalFree
0x180014847  mov     cs:?g_pszCRCTempBuf@@3PEAGEA, r14; ushort * g_pszCRCTempBuf
0x18001484e  mov     rax, [rsp+78h+arg_0]
0x180014856  mov     cs:pszTitleString, rax
0x18001485d  mov     eax, cs:?g_bRet@@3HA; int g_bRet
0x180014863  neg     eax
0x180014865  mov     cs:hWnd, r13
0x18001486c  mov     cs:word_1800257D2, r12w
0x180014874  sbb     eax, eax
0x180014876  not     eax
0x180014878  and     eax, 80004005h
0x18001487d  add     rsp, 38h
0x180014881  pop     r15
0x180014883  pop     r14
0x180014885  pop     r13
0x180014887  pop     r12
0x180014889  pop     rdi
0x18001488a  pop     rsi
0x18001488b  pop     rbp
0x18001488c  pop     rbx
0x18001488d  retn
```
