# CActiveXInstallBroker::InstallCatalogFile(ushort *,ushort *)

- ea: `0x40494e`
- end: `0x404a95`
- name: `?InstallCatalogFile@CActiveXInstallBroker@@QAGJPAG0@Z`
- size: `327`
- prototype: `int __userpurge@<eax>(_WORD *@<edx>, int *@<ecx>, PWSTR pwszCatalogFile, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x405eb0`

## callees

- `0x402eb9`
- `0x402ed3`
- `0x403094`
- `0x40494e`
- `0x408a2f`
- `0x40cb60`

## import_xrefs

- `WINTRUST!CryptCATAdminReleaseContext` at `0x404a75`
- `WINTRUST!CryptCATAdminReleaseContext` at `0x404a75`
- `WINTRUST!CryptCATAdminAddCatalog` at `0x404a3f`
- `WINTRUST!CryptCATAdminAddCatalog` at `0x404a3f`
- `WINTRUST!CryptCATAdminAcquireContext` at `0x404a26`
- `WINTRUST!CryptCATAdminAcquireContext` at `0x404a26`
- `WINTRUST!CryptCATAdminReleaseCatalogContext` at `0x404a69`
- `WINTRUST!CryptCATAdminReleaseCatalogContext` at `0x404a69`

## pseudocode

```c
int __userpurge CActiveXInstallBroker::InstallCatalogFile@<eax>(
        _WORD *a1@<edx>,
        int *a2@<ecx>,
        PWSTR pwszCatalogFile,
        unsigned __int16 *a4,
        unsigned __int16 *a5)
{
  int v7; // ecx
  int IsAuthorized; // esi
  _WORD *v9; // eax
  bool v10; // cf
  int v11; // eax
  HCATINFO v12; // ecx
  HCATADMIN v13; // eax
  HCATADMIN phCatAdmin; // [esp+Ch] [ebp-1Ch] BYREF
  void *v16; // [esp+10h] [ebp-18h]
  GUID pgSubsystem; // [esp+14h] [ebp-14h] BYREF

  pgSubsystem.Data1 = -145692989;
  *(_DWORD *)&pgSubsystem.Data2 = 298924270;
  phCatAdmin = 0;
  v16 = 0;
  *(_DWORD *)pgSubsystem.Data4 = -1073683067;
  *(_DWORD *)&pgSubsystem.Data4[4] = -292175281;
  if ( !CLock::Lock((CLock *)a2) )
  {
    IsAuthorized = -2147024882;
LABEL_24:
    v12 = v16;
    goto LABEL_25;
  }
  if ( a2[7] < 2 )
  {
    IsAuthorized = -2147019873;
    goto LABEL_24;
  }
  if ( !a1 || !pwszCatalogFile )
  {
    IsAuthorized = -2147024809;
    goto LABEL_24;
  }
  v9 = (_WORD *)a2[9];
  while ( 1 )
  {
    LOWORD(v7) = *a1;
    v10 = *a1 < *v9;
    if ( *a1 != *v9 )
      break;
    if ( !(_WORD)v7 )
      goto LABEL_12;
    LOWORD(v7) = a1[1];
    v10 = (unsigned __int16)v7 < v9[1];
    if ( (_WORD)v7 != v9[1] )
      break;
    a1 += 2;
    v9 += 2;
    if ( !(_WORD)v7 )
    {
LABEL_12:
      v11 = 0;
      goto LABEL_14;
    }
  }
  v11 = v10 ? -1 : 1;
LABEL_14:
  if ( v11 )
    goto LABEL_15;
  IsAuthorized = CActiveXInstallBroker::FileIsAuthorized((CActiveXInstallBroker *)a2, pwszCatalogFile, v7);
  if ( IsAuthorized < 0 )
    goto LABEL_24;
  if ( !a2[21] && !ContainingPathIsTamperProof(pwszCatalogFile) )
  {
LABEL_15:
    IsAuthorized = -2147024891;
    goto LABEL_24;
  }
  if ( !CryptCATAdminAcquireContext(&phCatAdmin, &pgSubsystem, 0) )
  {
    IsAuthorized = -2147467259;
    goto LABEL_24;
  }
  v12 = CryptCATAdminAddCatalog(phCatAdmin, pwszCatalogFile, 0, 0);
  if ( !v12 )
    IsAuthorized = -2147467259;
LABEL_25:
  v13 = phCatAdmin;
  if ( phCatAdmin )
  {
    if ( v12 )
    {
      CryptCATAdminReleaseCatalogContext(phCatAdmin, v12, 0);
      v13 = phCatAdmin;
    }
    CryptCATAdminReleaseContext(v13, 0);
  }
  CLock::Unlock((CLock *)a2);
  return IsAuthorized;
}

```

## disassembly

```asm
0x40494e  mov     edi, edi
0x404950  push    ebp
0x404951  mov     ebp, esp
0x404953  sub     esp, 1Ch
0x404956  mov     eax, ___security_cookie
0x40495b  xor     eax, ebp
0x40495d  mov     [ebp+var_4], eax
0x404960  push    ebx
0x404961  mov     ebx, [ebp+pwszCatalogFile]
0x404964  push    esi
0x404965  push    edi; unsigned __int16 *
0x404966  mov     edi, ecx
0x404968  mov     [ebp+pgSubsystem.Data1], 0F750E6C3h
0x40496f  xor     ecx, ecx
0x404971  mov     dword ptr [ebp+pgSubsystem.Data2], 11D138EEh
0x404978  mov     [ebp+phCatAdmin], ecx
0x40497b  mov     esi, edx
0x40497d  mov     [ebp+var_18], ecx
0x404980  mov     ecx, edi; this
0x404982  mov     dword ptr [ebp+pgSubsystem.Data4], 0C000E585h
0x404989  mov     dword ptr [ebp+pgSubsystem.Data4+4], 0EE95C24Fh
0x404990  call    ?Lock@CLock@@QAEHXZ; CLock::Lock(void)
0x404995  test    eax, eax
0x404997  jnz     short loc_4049A3
0x404999  mov     esi, 8007000Eh
0x40499e  jmp     loc_404A57
0x4049a3  cmp     dword ptr [edi+1Ch], 2
0x4049a7  jge     short loc_4049B3
0x4049a9  mov     esi, 8007139Fh
0x4049ae  jmp     loc_404A57
0x4049b3  test    esi, esi
0x4049b5  jz      loc_404A52
0x4049bb  test    ebx, ebx
0x4049bd  jz      loc_404A52
0x4049c3  mov     eax, [edi+24h]
0x4049c6  mov     cx, [esi]
0x4049c9  cmp     cx, [eax]
0x4049cc  jnz     short loc_4049EC
0x4049ce  test    cx, cx
0x4049d1  jz      short loc_4049E8
0x4049d3  mov     cx, [esi+2]
0x4049d7  cmp     cx, [eax+2]
0x4049db  jnz     short loc_4049EC
0x4049dd  add     esi, 4
0x4049e0  add     eax, 4
0x4049e3  test    cx, cx
0x4049e6  jnz     short loc_4049C6
0x4049e8  xor     eax, eax
0x4049ea  jmp     short loc_4049F1
0x4049ec  sbb     eax, eax
0x4049ee  or      eax, 1
0x4049f1  test    eax, eax
0x4049f3  jz      short loc_4049FC
0x4049f5  mov     esi, 80070005h
0x4049fa  jmp     short loc_404A57
0x4049fc  push    ecx; int
0x4049fd  push    ebx; unsigned __int16 *
0x4049fe  mov     ecx, edi; this
0x404a00  call    ?FileIsAuthorized@CActiveXInstallBroker@@AAEJPBGH@Z; CActiveXInstallBroker::FileIsAuthorized(ushort const *,int)
0x404a05  mov     esi, eax
0x404a07  test    esi, esi
0x404a09  js      short loc_404A57
0x404a0b  cmp     dword ptr [edi+54h], 0
0x404a0f  jnz     short loc_404A1C
0x404a11  mov     ecx, ebx
0x404a13  call    ?ContainingPathIsTamperProof@@YGHPBG@Z; ContainingPathIsTamperProof(ushort const *)
0x404a18  test    eax, eax
0x404a1a  jz      short loc_4049F5
0x404a1c  push    0; dwFlags
0x404a1e  lea     eax, [ebp+pgSubsystem]
0x404a21  push    eax; pgSubsystem
0x404a22  lea     eax, [ebp+phCatAdmin]
0x404a25  push    eax; phCatAdmin
0x404a26  call    ds:__imp__CryptCATAdminAcquireContext@12; CryptCATAdminAcquireContext(x,x,x)
0x404a2c  test    eax, eax
0x404a2e  jnz     short loc_404A37
0x404a30  mov     esi, 80004005h
0x404a35  jmp     short loc_404A57
0x404a37  push    0; dwFlags
0x404a39  push    0; pwszSelectBaseName
0x404a3b  push    ebx; pwszCatalogFile
0x404a3c  push    [ebp+phCatAdmin]; hCatAdmin
0x404a3f  call    ds:__imp__CryptCATAdminAddCatalog@16; CryptCATAdminAddCatalog(x,x,x,x)
0x404a45  mov     ecx, eax
0x404a47  test    ecx, ecx
0x404a49  jnz     short loc_404A5A
0x404a4b  mov     esi, 80004005h
0x404a50  jmp     short loc_404A5A
0x404a52  mov     esi, 80070057h
0x404a57  mov     ecx, [ebp+var_18]
0x404a5a  mov     eax, [ebp+phCatAdmin]
0x404a5d  test    eax, eax
0x404a5f  jz      short loc_404A7B
0x404a61  test    ecx, ecx
0x404a63  jz      short loc_404A72
0x404a65  push    0; dwFlags
0x404a67  push    ecx; hCatInfo
0x404a68  push    eax; hCatAdmin
0x404a69  call    ds:__imp__CryptCATAdminReleaseCatalogContext@12; CryptCATAdminReleaseCatalogContext(x,x,x)
0x404a6f  mov     eax, [ebp+phCatAdmin]
0x404a72  push    0; dwFlags
0x404a74  push    eax; hCatAdmin
0x404a75  call    ds:__imp__CryptCATAdminReleaseContext@8; CryptCATAdminReleaseContext(x,x)
0x404a7b  mov     ecx, edi; this
0x404a7d  call    ?Unlock@CLock@@QAEHXZ; CLock::Unlock(void)
0x404a82  mov     ecx, [ebp+var_4]
0x404a85  mov     eax, esi
0x404a87  pop     edi
0x404a88  pop     esi
0x404a89  xor     ecx, ebp; StackCookie
0x404a8b  pop     ebx
0x404a8c  call    @__security_check_cookie@4; __security_check_cookie(x)
0x404a91  leave
0x404a92  retn    4
```
