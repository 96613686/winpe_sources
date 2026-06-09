# DeleteSystemDataFolderForUser(void *,SYSTEM_DATA_FOLDER_USER_ACCESS,ushort const *,bool)

- ea: `0x180004578`
- end: `0x180004ae0`
- name: `?DeleteSystemDataFolderForUser@@YAJPEAXW4SYSTEM_DATA_FOLDER_USER_ACCESS@@PEBG_N@Z`
- size: `1384`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x18000bf20`
- `0x180079880`

## callees

- `0x180004578`
- `0x180004e00`
- `0x18003aa84`
- `0x180044d0c`
- `0x180050ba0`
- `0x1800e5010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18000468f`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800046a9`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180004843`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18000485d`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18000468f`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800046a9`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180004843`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18000485d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000473c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800048eb`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000473c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800048eb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004aae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004aae`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180004671`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180004825`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180004671`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180004825`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalizeEx` at `0x1800046c8`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalizeEx` at `0x180004881`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalizeEx` at `0x1800046c8`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalizeEx` at `0x180004881`
- `SHELL32!SHGetFolderPathEx` at `0x1800045f1`
- `SHELL32!SHGetFolderPathEx` at `0x1800045f1`
- `SHELL32!SHCreateItemFromParsingName` at `0x1800049e8`
- `SHELL32!SHCreateItemFromParsingName` at `0x1800049e8`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180004a3c`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180004a3c`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800045be`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800045be`

## pseudocode

```c
void __fastcall __noreturn DeleteSystemDataFolderForUser(void *a1, int a2, const WCHAR *a3)
{
  int v3; // r13d
  __int64 v5; // rdi
  __int64 v6; // r15
  WCHAR *v7; // rcx
  __int64 v8; // rax
  WCHAR *v9; // r8
  __int64 v10; // rdx
  WCHAR *v11; // rcx
  wchar_t *i; // rax
  unsigned __int64 v13; // r14
  unsigned __int64 v14; // rsi
  unsigned __int64 v15; // rax
  __int64 v16; // rax
  WCHAR *v17; // rcx
  __int64 v18; // rdx
  WCHAR *v19; // r8
  WCHAR *v20; // rcx
  __int64 v21; // rax
  WCHAR *v22; // rcx
  __int64 v23; // rdx
  WCHAR *v24; // r8
  WCHAR *v25; // rcx
  HRESULT v26; // ebx
  wchar_t *v27; // rax
  unsigned __int64 v28; // rsi
  WCHAR *v29; // rcx
  WCHAR *v30; // rax
  WCHAR *v31; // rcx
  unsigned int v32; // edx
  HWND v33; // rcx
  const struct _GUID *v34; // r8
  IUnknown *pProxy; // [rsp+40h] [rbp-C0h] BYREF
  LPWSTR StringSid; // [rsp+48h] [rbp-B8h] BYREF
  void *ppv; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR String1[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR pszPathOut[264]; // [rsp+270h] [rbp+170h] BYREF
  WCHAR pszPath[264]; // [rsp+480h] [rbp+380h] BYREF

  v3 = a2;
  LODWORD(pProxy) = a2;
  StringSid = 0;
  if ( ConvertSidToStringSidW(a1, &StringSid) || (int)ResultFromKnownLastError() >= 0 )
  {
    v5 = 260;
    if ( (int)SHGetFolderPathEx(&FOLDERID_ProgramData, 0, 0, String1, 260) < 0 )
      goto LABEL_70;
    v6 = 2147483646;
    v7 = String1;
    v8 = 2147483646;
    v9 = pszPath;
    v10 = 260;
    do
    {
      if ( !v8 )
        break;
      if ( !*v7 )
        break;
      *v9++ = *v7++;
      --v8;
      --v10;
    }
    while ( v10 );
    v11 = v9 - 1;
    if ( v10 )
      v11 = v9;
    *v11 = 0;
    if ( !v10 || PathCchAppend(pszPath, 0x104u, L"Microsoft\\Windows\\SystemData") < 0 )
      goto LABEL_70;
    for ( i = wcsstr(pszPath, L"/"); i; i = wcsstr(i, L"/") )
      *i = 92;
    if ( PathCchCanonicalizeEx(pszPathOut, 0x104u, pszPath, 0) < 0 )
      goto LABEL_70;
    v13 = -1;
    v14 = -1;
    do
      ++v14;
    while ( String1[v14] );
    if ( v14 > 0xFFFFFFFF )
      goto LABEL_70;
    v15 = -1;
    do
      ++v15;
    while ( pszPathOut[v15] );
    if ( v15 > 0xFFFFFFFF
      || (unsigned int)v15 <= (unsigned int)v14
      || CompareStringOrdinal(String1, v14, pszPathOut, v14, 0) != 2
      || pszPathOut[(unsigned int)v14] != 92 )
    {
      goto LABEL_70;
    }
    v16 = 2147483646;
    v17 = pszPathOut;
    v18 = 260;
    v19 = String1;
    do
    {
      if ( !v16 )
        break;
      if ( !*v17 )
        break;
      *v19++ = *v17++;
      --v16;
      --v18;
    }
    while ( v18 );
    v20 = v19 - 1;
    if ( v18 )
      v20 = v19;
    *v20 = 0;
    if ( !v18 )
      goto LABEL_70;
    v21 = 2147483646;
    v22 = String1;
    v23 = 260;
    v24 = pszPath;
    do
    {
      if ( !v21 )
        break;
      if ( !*v22 )
        break;
      *v24++ = *v22++;
      --v21;
      --v23;
    }
    while ( v23 );
    v25 = v24 - 1;
    if ( v23 )
      v25 = v24;
    *v25 = 0;
    if ( !v23 )
      goto LABEL_70;
    v26 = PathCchAppend(pszPath, 0x104u, StringSid);
    if ( v26 >= 0 )
    {
      v27 = wcsstr(pszPath, L"/");
      if ( v27 )
      {
        do
        {
          *v27 = 92;
          v27 = wcsstr(v27, L"/");
        }
        while ( v27 );
        v3 = (int)pProxy;
      }
      v26 = PathCchCanonicalizeEx(pszPathOut, 0x104u, pszPath, 0);
      if ( v26 >= 0 )
      {
        v28 = -1;
        do
          ++v28;
        while ( String1[v28] );
        if ( v28 > 0xFFFFFFFF )
          goto LABEL_70;
        do
          ++v13;
        while ( pszPathOut[v13] );
        if ( v13 > 0xFFFFFFFF )
        {
LABEL_70:
          LocalFree(StringSid);
          return;
        }
        v26 = -2147024809;
        if ( (unsigned int)v13 > (unsigned int)v28
          && CompareStringOrdinal(String1, v28, pszPathOut, v28, 0) == 2
          && pszPathOut[(unsigned int)v28] == 92 )
        {
          v29 = pszPathOut;
          v30 = String1;
          do
          {
            if ( !v6 )
              break;
            if ( !*v29 )
              break;
            *v30++ = *v29++;
            --v6;
            --v5;
          }
          while ( v5 );
          v31 = v30 - 1;
          if ( v5 )
            v31 = v30;
          v26 = v5 == 0 ? 0x8007007A : 0;
          *v31 = 0;
        }
      }
    }
    if ( v26 >= 0
      && (!a3
       || !*a3
       || (int)_AppendPathAndCreateFolder(off_1800F8018[3 * v3], StringSid, v3, 0, 0, String1) >= 0
       && (int)_AppendPathAndCreateFolder(a3, StringSid, v3, 0, 0, String1) >= 0) )
    {
      ppv = 0;
      if ( SHCreateItemFromParsingName(String1, 0, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &ppv) >= 0 )
      {
        pProxy = 0;
        if ( (int)SHCreateFileOperation(v33, v32, v34, (void **)&pProxy) >= 0 )
        {
          if ( CoSetProxyBlanket(pProxy, 0xFFFFFFFF, 0xFFFFFFFF, 0, 0, 3u, 0, 0x40u) >= 0
            && ((int (__fastcall *)(IUnknown *, void *, _QWORD))pProxy->lpVtbl[6].QueryInterface)(pProxy, ppv, 0) >= 0 )
          {
            ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl[7].QueryInterface)(pProxy);
          }
          ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
        }
        (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
      }
    }
    goto LABEL_70;
  }
}

```

## disassembly

```asm
0x180004578  mov     [rsp-8+arg_18], rbx
0x18000457d  push    rbp
0x18000457e  push    rsi
0x18000457f  push    rdi
0x180004580  push    r12
0x180004582  push    r13
0x180004584  push    r14
0x180004586  push    r15
0x180004588  lea     rbp, [rsp-5A0h]
0x180004590  sub     rsp, 6A0h
0x180004597  mov     rax, cs:__security_cookie
0x18000459e  xor     rax, rsp
0x1800045a1  mov     [rbp+5D0h+var_40], rax
0x1800045a8  mov     r13d, edx
0x1800045ab  mov     dword ptr [rsp+6D0h+pProxy], edx
0x1800045af  xor     esi, esi
0x1800045b1  lea     rdx, [rsp+6D0h+StringSid]; StringSid
0x1800045b6  mov     [rsp+6D0h+StringSid], rsi
0x1800045bb  mov     r12, r8
0x1800045be  call    cs:__imp_ConvertSidToStringSidW
0x1800045c4  test    eax, eax
0x1800045c6  jnz     short loc_1800045D7
0x1800045c8  call    ?ResultFromKnownLastError@@YAJXZ
0x1800045cd  mov     ebx, eax
0x1800045cf  test    eax, eax
0x1800045d1  js      loc_180004AB4
0x1800045d7  mov     edi, 104h
0x1800045dc  lea     r9, [rsp+6D0h+String1]
0x1800045e1  xor     r8d, r8d
0x1800045e4  mov     [rsp+6D0h+bIgnoreCase], edi
0x1800045e8  xor     edx, edx
0x1800045ea  lea     rcx, FOLDERID_ProgramData
0x1800045f1  call    cs:__imp_SHGetFolderPathEx
0x1800045f7  mov     ebx, eax
0x1800045f9  test    eax, eax
0x1800045fb  js      loc_180004AA9
0x180004601  mov     r15d, 7FFFFFFEh
0x180004607  lea     rcx, [rsp+6D0h+String1]
0x18000460c  mov     eax, r15d
0x18000460f  lea     r8, [rbp+5D0h+pszPath]
0x180004616  mov     edx, edi
0x180004618  test    rax, rax
0x18000461b  jz      short loc_18000463C
0x18000461d  movzx   r9d, word ptr [rcx]
0x180004621  test    r9w, r9w
0x180004625  jz      short loc_18000463C
0x180004627  mov     [r8], r9w
0x18000462b  add     rcx, 2
0x18000462f  add     r8, 2
0x180004633  dec     rax
0x180004636  sub     rdx, 1
0x18000463a  jnz     short loc_180004618
0x18000463c  mov     rax, rdx
0x18000463f  lea     rcx, [r8-2]
0x180004643  neg     rax
0x180004646  sbb     ebx, ebx
0x180004648  not     ebx
0x18000464a  and     ebx, 8007007Ah
0x180004650  test    rdx, rdx
0x180004653  cmovnz  rcx, r8
0x180004657  mov     [rcx], si
0x18000465a  jz      loc_180004AA9
0x180004660  lea     r8, pszMore
0x180004667  mov     rdx, rdi; cchPath
0x18000466a  lea     rcx, [rbp+5D0h+pszPath]; pszPath
0x180004671  call    cs:__imp_PathCchAppend
0x180004677  mov     ebx, eax
0x180004679  test    eax, eax
0x18000467b  js      loc_180004AA9
0x180004681  lea     rdx, SubStr
0x180004688  lea     rcx, [rbp+5D0h+pszPath]; Str
0x18000468f  call    cs:__imp_wcsstr
0x180004695  test    rax, rax
0x180004698  jz      short loc_1800046B4
0x18000469a  lea     rdx, SubStr
0x1800046a1  mov     word ptr [rax], 5Ch ; '\'
0x1800046a6  mov     rcx, rax; Str
0x1800046a9  call    cs:__imp_wcsstr
0x1800046af  test    rax, rax
0x1800046b2  jnz     short loc_18000469A
0x1800046b4  xor     r9d, r9d; dwFlags
0x1800046b7  lea     r8, [rbp+5D0h+pszPath]; pszPathIn
0x1800046be  mov     rdx, rdi; cchPathOut
0x1800046c1  lea     rcx, [rbp+5D0h+pszPathOut]; pszPathOut
0x1800046c8  call    cs:__imp_PathCchCanonicalizeEx
0x1800046ce  mov     ebx, eax
0x1800046d0  test    eax, eax
0x1800046d2  js      loc_180004AA9
0x1800046d8  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800046dc  lea     rax, [rsp+6D0h+String1]
0x1800046e1  mov     rsi, r14
0x1800046e4  xor     ecx, ecx
0x1800046e6  inc     rsi
0x1800046e9  cmp     [rax+rsi*2], cx
0x1800046ed  jnz     short loc_1800046E6
0x1800046ef  mov     r8d, 0FFFFFFFFh
0x1800046f5  cmp     rsi, r8
0x1800046f8  ja      loc_180004AA4
0x1800046fe  lea     rdx, [rbp+5D0h+pszPathOut]
0x180004705  mov     rax, r14
0x180004708  inc     rax
0x18000470b  cmp     [rdx+rax*2], cx
0x18000470f  jnz     short loc_180004708
0x180004711  cmp     rax, r8
0x180004714  ja      loc_180004AA4
0x18000471a  mov     ebx, 80070057h
0x18000471f  cmp     eax, esi
0x180004721  jbe     loc_180004AA9
0x180004727  mov     [rsp+6D0h+bIgnoreCase], ecx; bIgnoreCase
0x18000472b  lea     r8, [rbp+5D0h+pszPathOut]; lpString2
0x180004732  lea     rcx, [rsp+6D0h+String1]; lpString1
0x180004737  mov     r9d, esi; cchCount2
0x18000473a  mov     edx, esi; cchCount1
0x18000473c  call    cs:__imp_CompareStringOrdinal
0x180004742  cmp     eax, 2
0x180004745  jnz     loc_180004AA9
0x18000474b  mov     eax, esi
0x18000474d  mov     ecx, 5Ch ; '\'
0x180004752  cmp     [rbp+rax*2+5D0h+pszPathOut], cx
0x18000475a  jnz     loc_180004AA9
0x180004760  mov     rax, r15
0x180004763  lea     rcx, [rbp+5D0h+pszPathOut]
0x18000476a  mov     rdx, rdi
0x18000476d  lea     r8, [rsp+6D0h+String1]
0x180004772  xor     esi, esi
0x180004774  test    rax, rax
0x180004777  jz      short loc_180004798
0x180004779  movzx   r9d, word ptr [rcx]
0x18000477d  test    r9w, r9w
0x180004781  jz      short loc_180004798
0x180004783  mov     [r8], r9w
0x180004787  add     rcx, 2
0x18000478b  add     r8, 2
0x18000478f  dec     rax
0x180004792  sub     rdx, 1
0x180004796  jnz     short loc_180004774
0x180004798  mov     rax, rdx
0x18000479b  lea     rcx, [r8-2]
0x18000479f  neg     rax
0x1800047a2  mov     r10d, 8007007Ah
0x1800047a8  sbb     ebx, ebx
0x1800047aa  not     ebx
0x1800047ac  and     ebx, r10d
0x1800047af  test    rdx, rdx
0x1800047b2  cmovnz  rcx, r8
0x1800047b6  mov     [rcx], si
0x1800047b9  jz      loc_180004AA9
0x1800047bf  mov     rax, r15
0x1800047c2  lea     rcx, [rsp+6D0h+String1]
0x1800047c7  mov     rdx, rdi
0x1800047ca  lea     r8, [rbp+5D0h+pszPath]
0x1800047d1  test    rax, rax
0x1800047d4  jz      short loc_1800047F5
0x1800047d6  movzx   r9d, word ptr [rcx]
0x1800047da  test    r9w, r9w
0x1800047de  jz      short loc_1800047F5
0x1800047e0  mov     [r8], r9w
0x1800047e4  add     rcx, 2
0x1800047e8  add     r8, 2
0x1800047ec  dec     rax
0x1800047ef  sub     rdx, 1
0x1800047f3  jnz     short loc_1800047D1
0x1800047f5  mov     rax, rdx
0x1800047f8  lea     rcx, [r8-2]
0x1800047fc  neg     rax
0x1800047ff  sbb     ebx, ebx
0x180004801  not     ebx
0x180004803  and     ebx, r10d
0x180004806  test    rdx, rdx
0x180004809  cmovnz  rcx, r8
0x18000480d  mov     [rcx], si
0x180004810  jz      loc_180004AA9
0x180004816  mov     r8, [rsp+6D0h+StringSid]; pszMore
0x18000481b  lea     rcx, [rbp+5D0h+pszPath]; pszPath
0x180004822  mov     rdx, rdi; cchPath
0x180004825  call    cs:__imp_PathCchAppend
0x18000482b  mov     ebx, eax
0x18000482d  test    eax, eax
0x18000482f  js      loc_180004955
0x180004835  lea     rdx, SubStr
0x18000483c  lea     rcx, [rbp+5D0h+pszPath]; Str
0x180004843  call    cs:__imp_wcsstr
0x180004849  test    rax, rax
0x18000484c  jz      short loc_18000486D
0x18000484e  lea     rdx, SubStr
0x180004855  mov     word ptr [rax], 5Ch ; '\'
0x18000485a  mov     rcx, rax; Str
0x18000485d  call    cs:__imp_wcsstr
0x180004863  test    rax, rax
0x180004866  jnz     short loc_18000484E
0x180004868  mov     r13d, dword ptr [rsp+6D0h+pProxy]
0x18000486d  xor     r9d, r9d; dwFlags
0x180004870  lea     r8, [rbp+5D0h+pszPath]; pszPathIn
0x180004877  mov     rdx, rdi; cchPathOut
0x18000487a  lea     rcx, [rbp+5D0h+pszPathOut]; pszPathOut
0x180004881  call    cs:__imp_PathCchCanonicalizeEx
0x180004887  mov     ebx, eax
0x180004889  test    eax, eax
0x18000488b  js      loc_180004955
0x180004891  lea     rax, [rsp+6D0h+String1]
0x180004896  mov     rsi, r14
0x180004899  xor     ecx, ecx
0x18000489b  inc     rsi
0x18000489e  cmp     [rax+rsi*2], cx
0x1800048a2  jnz     short loc_18000489B
0x1800048a4  mov     edx, 0FFFFFFFFh
0x1800048a9  cmp     rsi, rdx
0x1800048ac  ja      loc_180004AA4
0x1800048b2  lea     rax, [rbp+5D0h+pszPathOut]
0x1800048b9  inc     r14
0x1800048bc  cmp     [rax+r14*2], cx
0x1800048c1  jnz     short loc_1800048B9
0x1800048c3  cmp     r14, rdx
0x1800048c6  ja      loc_180004AA4
0x1800048cc  mov     ebx, 80070057h
0x1800048d1  cmp     r14d, esi
0x1800048d4  jbe     short loc_180004953
0x1800048d6  mov     [rsp+6D0h+bIgnoreCase], ecx; bIgnoreCase
0x1800048da  lea     r8, [rbp+5D0h+pszPathOut]; lpString2
0x1800048e1  lea     rcx, [rsp+6D0h+String1]; lpString1
0x1800048e6  mov     r9d, esi; cchCount2
0x1800048e9  mov     edx, esi; cchCount1
0x1800048eb  call    cs:__imp_CompareStringOrdinal
0x1800048f1  cmp     eax, 2
0x1800048f4  jnz     short loc_180004953
0x1800048f6  mov     eax, esi
0x1800048f8  mov     ecx, 5Ch ; '\'
0x1800048fd  xor     esi, esi
0x1800048ff  cmp     [rbp+rax*2+5D0h+pszPathOut], cx
0x180004907  jnz     short loc_180004955
0x180004909  lea     rcx, [rbp+5D0h+pszPathOut]
0x180004910  lea     rax, [rsp+6D0h+String1]
0x180004915  test    r15, r15
0x180004918  jz      short loc_180004936
0x18000491a  movzx   edx, word ptr [rcx]
0x18000491d  test    dx, dx
0x180004920  jz      short loc_180004936
0x180004922  mov     [rax], dx
0x180004925  add     rcx, 2
0x180004929  add     rax, 2
0x18000492d  dec     r15
0x180004930  sub     rdi, 1
0x180004934  jnz     short loc_180004915
0x180004936  test    rdi, rdi
0x180004939  lea     rcx, [rax-2]
0x18000493d  cmovnz  rcx, rax
0x180004941  neg     rdi
0x180004944  sbb     ebx, ebx
0x180004946  not     ebx
0x180004948  and     ebx, 8007007Ah
0x18000494e  mov     [rcx], si
0x180004951  jmp     short loc_180004955
0x180004953  xor     esi, esi
0x180004955  test    ebx, ebx
0x180004957  js      loc_180004AA9
0x18000495d  test    r12, r12
0x180004960  jz      short loc_1800049D0
0x180004962  cmp     [r12], si
0x180004967  jz      short loc_1800049D0
0x180004969  mov     rdx, [rsp+6D0h+StringSid]
0x18000496e  lea     r10, off_1800F8018
0x180004975  movsxd  rax, r13d
0x180004978  xor     r9d, r9d
0x18000497b  mov     r8d, r13d
0x18000497e  lea     rcx, [rax+rax*2]
0x180004982  mov     rcx, [r10+rcx*8]
0x180004986  lea     rax, [rsp+6D0h+String1]
0x18000498b  mov     qword ptr [rsp+6D0h+dwImpLevel], rax
0x180004990  mov     byte ptr [rsp+6D0h+bIgnoreCase], sil
0x180004995  call    ?_AppendPathAndCreateFolder@@YAJPEBG0W4SYSTEM_DATA_FOLDER_USER_ACCESS@@W4SYSTEM_DATA_FOLDER_FLAGS@@_NPEAGI@Z
0x18000499a  mov     ebx, eax
0x18000499c  test    eax, eax
0x18000499e  js      loc_180004AA9
0x1800049a4  mov     rdx, [rsp+6D0h+StringSid]
0x1800049a9  lea     rax, [rsp+6D0h+String1]
0x1800049ae  mov     qword ptr [rsp+6D0h+dwImpLevel], rax
0x1800049b3  xor     r9d, r9d
0x1800049b6  mov     r8d, r13d
0x1800049b9  mov     byte ptr [rsp+6D0h+bIgnoreCase], sil
0x1800049be  mov     rcx, r12
0x1800049c1  call    ?_AppendPathAndCreateFolder@@YAJPEBG0W4SYSTEM_DATA_FOLDER_USER_ACCESS@@W4SYSTEM_DATA_FOLDER_FLAGS@@_NPEAGI@Z
0x1800049c6  mov     ebx, eax
0x1800049c8  test    eax, eax
0x1800049ca  js      loc_180004AA9
0x1800049d0  lea     r9, [rsp+6D0h+ppv]; ppv
0x1800049d5  mov     [rsp+6D0h+ppv], rsi
0x1800049da  lea     r8, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x1800049e1  xor     edx, edx; pbc
0x1800049e3  lea     rcx, [rsp+6D0h+String1]; pszPath
0x1800049e8  call    cs:__imp_SHCreateItemFromParsingName
0x1800049ee  mov     ebx, eax
0x1800049f0  test    eax, eax
0x1800049f2  js      loc_180004AA9
0x1800049f8  lea     r9, [rsp+6D0h+pProxy]; void **
0x1800049fd  mov     [rsp+6D0h+pProxy], rsi
0x180004a02  call    ?SHCreateFileOperation@@YAJPEAUHWND__@@KAEBU_GUID@@PEAPEAX@Z
0x180004a07  mov     ebx, eax
0x180004a09  test    eax, eax
0x180004a0b  js      loc_180004A91
0x180004a11  mov     rcx, [rsp+6D0h+pProxy]; pProxy
  ... truncated ...
```
