# RdVhd::Uvhd::CProfileHelper::IsUserProfileInUse(ushort const *,int *)

- ea: `0x180057350`
- end: `0x18005762e`
- name: `?IsUserProfileInUse@CProfileHelper@Uvhd@RdVhd@@UEBAJPEBGPEAH@Z`
- size: `734`
- prototype: `__int64 __fastcall(RdVhd::Uvhd::CProfileHelper *__hidden this, LPCWSTR lpSubKey, int *)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, registry_config`

## callees

- `0x180004db0`
- `0x180019b38`
- `0x180031b5c`
- `0x180035d40`
- `0x1800488e4`
- `0x180048b28`
- `0x180057110`
- `0x180057350`
- `0x18005d010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005757f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005757f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005759c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005759c`

## string_xrefs

- `0x1800573f6`: `szUserSID`

## pseudocode

```c
__int64 __fastcall RdVhd::Uvhd::CProfileHelper::IsUserProfileInUse(
        RdVhd::Uvhd::CProfileHelper *this,
        LPCWSTR lpSubKey,
        int *a3)
{
  RdVhd::Uvhd::CUvhdDiskManager *v5; // rcx
  __int64 v6; // rdx
  const wchar_t *v7; // r9
  int v8; // ebx
  int UserProfileDirectoryW; // eax
  RdVhd::Uvhd::CUvhdDiskManager *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rax
  unsigned int (__fastcall *v13)(__int64, __int64); // r10
  __int64 v14; // r11
  void **v16; // [rsp+30h] [rbp-50h] BYREF
  int v17; // [rsp+38h] [rbp-48h]
  __int64 v18; // [rsp+3Ch] [rbp-44h]
  int v19; // [rsp+44h] [rbp-3Ch]
  __int64 v20; // [rsp+48h] [rbp-38h]
  int v21; // [rsp+50h] [rbp-30h]
  void **v22; // [rsp+58h] [rbp-28h] BYREF
  int v23; // [rsp+60h] [rbp-20h]
  __int64 v24; // [rsp+64h] [rbp-1Ch]
  int v25; // [rsp+6Ch] [rbp-14h]
  __int64 v26; // [rsp+70h] [rbp-10h]
  int v27; // [rsp+78h] [rbp-8h]
  HKEY hKey; // [rsp+A8h] [rbp+28h] BYREF

  v18 = 128;
  v20 = 0;
  v19 = 0;
  v21 = 0x8000000;
  v27 = 0x8000000;
  v17 = 0;
  v16 = &CPathString::`vftable';
  v24 = 128;
  v26 = 0;
  v25 = 0;
  v23 = 0;
  v22 = &CPathString::`vftable';
  hKey = 0;
  if ( !lpSubKey )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    v6 = 107;
    v7 = L"szUserSID";
LABEL_6:
    WPP_SF_S(*((_QWORD *)v5 + 2), v6, WPP_8bdd996048cc3a3a6adb915db88b6959_Traceguids, v7);
LABEL_7:
    v8 = -2147024809;
    goto LABEL_34;
  }
  if ( !a3 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    v6 = 108;
    v7 = L"pfInUse";
    goto LABEL_6;
  }
  *a3 = 0;
  UserProfileDirectoryW = RdVhd::Uvhd::CProfileHelper::GetUserProfileDirectoryW(
                            this,
                            lpSubKey,
                            0,
                            (struct CPathString *)&v16);
  v8 = UserProfileDirectoryW;
  if ( (_WORD)UserProfileDirectoryW == 2 )
    goto LABEL_33;
  if ( UserProfileDirectoryW < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v11 = 109;
LABEL_19:
      WPP_SF_d(*((_QWORD *)v10 + 2), v11, WPP_8bdd996048cc3a3a6adb915db88b6959_Traceguids, (unsigned int)v8);
      goto LABEL_34;
    }
    goto LABEL_34;
  }
  if ( !(unsigned int)CBaseStringT<unsigned short>::IsEmpty(&v16) )
  {
    v8 = CPathString::BuildPath((CPathString *)&v22, (const struct CPathString *)&v16, L"NTUSER.DAT");
    if ( v8 < 0 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v11 = 111;
        goto LABEL_19;
      }
      goto LABEL_34;
    }
    v12 = CBaseStringT<unsigned short>::PContents(&v22);
    if ( v13(v14, v12) == -1 )
      goto LABEL_34;
    v8 = RegOpenKeyExW(HKEY_USERS, lpSubKey, 0, 0xF003Fu, &hKey);
    if ( v8 )
    {
      if ( v8 != 2 && v8 != 1018 )
      {
        if ( (v8 & 0xFFFF0000) == 0 )
        {
          if ( v8 > 0 )
            v8 |= 0x80070000;
          v8 = v8 & 0x8000FFFF | 0x50480000;
        }
        if ( v8 < 0 )
        {
          v10 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v11 = 112;
            goto LABEL_19;
          }
        }
        goto LABEL_34;
      }
    }
    else
    {
      *a3 = 1;
    }
LABEL_33:
    v8 = 0;
    goto LABEL_34;
  }
  v8 = -796917599;
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v11 = 110;
    goto LABEL_19;
  }
LABEL_34:
  if ( hKey )
    RegCloseKey(hKey);
  CPathString::~CPathString((CPathString *)&v22);
  CPathString::~CPathString((CPathString *)&v16);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180057350  mov     [rsp-18h+arg_0], rbx
0x180057355  mov     [rsp-18h+arg_10], rsi
0x18005735a  push    rbp
0x18005735b  push    rdi
0x18005735c  push    r14
0x18005735e  mov     rbp, rsp
0x180057361  sub     rsp, 80h
0x180057368  lea     rax, ??_7CPathString@@6B@; const CPathString::`vftable'
0x18005736f  mov     [rbp+var_44], 80h
0x180057377  mov     r14, rcx
0x18005737a  mov     [rbp+var_38], 0
0x180057382  mov     ecx, 8000000h
0x180057387  mov     [rbp+var_3C], 0
0x18005738e  mov     [rbp+var_30], ecx
0x180057391  mov     rdi, r8
0x180057394  mov     [rbp+var_8], ecx
0x180057397  mov     rsi, rdx
0x18005739a  mov     [rbp+var_48], 0
0x1800573a1  mov     [rbp+var_50], rax
0x1800573a5  mov     [rbp+var_1C], 80h
0x1800573ad  mov     [rbp+var_10], 0
0x1800573b5  mov     [rbp+var_14], 0
0x1800573bc  mov     [rbp+var_20], 0
0x1800573c3  mov     [rbp+var_28], rax
0x1800573c7  mov     [rbp+hKey], 0
0x1800573cf  test    rdx, rdx
0x1800573d2  jnz     short loc_180057417
0x1800573d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800573db  lea     rax, WPP_GLOBAL_Control
0x1800573e2  cmp     rcx, rax
0x1800573e5  jz      short loc_18005740D
0x1800573e7  test    byte ptr [rcx+1Ch], 4
0x1800573eb  jz      short loc_18005740D
0x1800573ed  cmp     byte ptr [rcx+19h], 2
0x1800573f1  jb      short loc_18005740D
0x1800573f3  lea     edx, [rsi+6Bh]
0x1800573f6  lea     r9, aSzusersid_0; "szUserSID"
0x1800573fd  mov     rcx, [rcx+10h]
0x180057401  lea     r8, WPP_8bdd996048cc3a3a6adb915db88b6959_Traceguids
0x180057408  call    WPP_SF_S
0x18005740d  mov     ebx, 80070057h
0x180057412  jmp     loc_180057593
0x180057417  test    rdi, rdi
0x18005741a  jnz     short loc_180057447
0x18005741c  mov     rcx, cs:WPP_GLOBAL_Control
0x180057423  lea     rax, WPP_GLOBAL_Control
0x18005742a  cmp     rcx, rax
0x18005742d  jz      short loc_18005740D
0x18005742f  test    byte ptr [rcx+1Ch], 4
0x180057433  jz      short loc_18005740D
0x180057435  cmp     byte ptr [rcx+19h], 2
0x180057439  jb      short loc_18005740D
0x18005743b  lea     edx, [rdi+6Ch]; unsigned __int16 *
0x18005743e  lea     r9, aPfinuse; "pfInUse"
0x180057445  jmp     short loc_1800573FD
0x180057447  mov     dword ptr [r8], 0
0x18005744e  lea     r9, [rbp+var_50]; struct CPathString *
0x180057452  xor     r8d, r8d; int
0x180057455  mov     rcx, r14; this
0x180057458  call    ?GetUserProfileDirectoryW@CProfileHelper@Uvhd@RdVhd@@UEBAJPEBGHPEAVCPathString@@@Z; RdVhd::Uvhd::CProfileHelper::GetUserProfileDirectoryW(ushort const *,int,CPathString *)
0x18005745d  mov     ebx, eax
0x18005745f  cmp     ax, 2
0x180057463  jz      loc_180057591
0x180057469  test    eax, eax
0x18005746b  jns     short loc_1800574B5
0x18005746d  mov     rcx, cs:WPP_GLOBAL_Control
0x180057474  lea     rax, WPP_GLOBAL_Control
0x18005747b  cmp     rcx, rax
0x18005747e  jz      loc_180057593
0x180057484  test    byte ptr [rcx+1Ch], 4
0x180057488  jz      loc_180057593
0x18005748e  cmp     byte ptr [rcx+19h], 2
0x180057492  jb      loc_180057593
0x180057498  mov     edx, 6Dh ; 'm'
0x18005749d  mov     rcx, [rcx+10h]
0x1800574a1  lea     r8, WPP_8bdd996048cc3a3a6adb915db88b6959_Traceguids
0x1800574a8  mov     r9d, ebx
0x1800574ab  call    WPP_SF_d
0x1800574b0  jmp     loc_180057593
0x1800574b5  lea     rcx, [rbp+var_50]
0x1800574b9  call    ?IsEmpty@?$CBaseStringT@G@@QEBAHXZ; CBaseStringT<ushort>::IsEmpty(void)
0x1800574be  test    eax, eax
0x1800574c0  jz      short loc_1800574F9
0x1800574c2  mov     ebx, 0D08000A1h
0x1800574c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800574ce  lea     rax, WPP_GLOBAL_Control
0x1800574d5  cmp     rcx, rax
0x1800574d8  jz      loc_180057593
0x1800574de  test    byte ptr [rcx+1Ch], 4
0x1800574e2  jz      loc_180057593
0x1800574e8  cmp     byte ptr [rcx+19h], 2
0x1800574ec  jb      loc_180057593
0x1800574f2  mov     edx, 6Eh ; 'n'
0x1800574f7  jmp     short loc_18005749D
0x1800574f9  lea     r8, aNtuserDat; "NTUSER.DAT"
0x180057500  lea     rdx, [rbp+var_50]; struct CPathString *
0x180057504  lea     rcx, [rbp+var_28]; this
0x180057508  call    ?BuildPath@CPathString@@QEAAJAEBV1@PEBG@Z; CPathString::BuildPath(CPathString const &,ushort const *)
0x18005750d  mov     ebx, eax
0x18005750f  test    eax, eax
0x180057511  jns     short loc_18005753C
0x180057513  mov     rcx, cs:WPP_GLOBAL_Control
0x18005751a  lea     rax, WPP_GLOBAL_Control
0x180057521  cmp     rcx, rax
0x180057524  jz      short loc_180057593
0x180057526  test    byte ptr [rcx+1Ch], 4
0x18005752a  jz      short loc_180057593
0x18005752c  cmp     byte ptr [rcx+19h], 2
0x180057530  jb      short loc_180057593
0x180057532  mov     edx, 6Fh ; 'o'
0x180057537  jmp     loc_18005749D
0x18005753c  mov     r11, [r14+8]
0x180057540  lea     rcx, [rbp+var_28]
0x180057544  mov     rax, [r11]
0x180057547  mov     r10, [rax+70h]
0x18005754b  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x180057550  mov     rdx, rax
0x180057553  mov     rcx, r11
0x180057556  mov     rax, r10
0x180057559  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005755e  cmp     eax, 0FFFFFFFFh
0x180057561  jz      short loc_180057593
0x180057563  lea     rax, [rbp+hKey]
0x180057567  mov     r9d, 0F003Fh; samDesired
0x18005756d  xor     r8d, r8d; ulOptions
0x180057570  mov     [rsp+80h+phkResult], rax; phkResult
0x180057575  mov     rdx, rsi; lpSubKey
0x180057578  mov     rcx, 0FFFFFFFF80000003h; hKey
0x18005757f  call    cs:__imp_RegOpenKeyExW
0x180057585  mov     ebx, eax
0x180057587  test    eax, eax
0x180057589  jnz     short loc_1800575CE
0x18005758b  mov     dword ptr [rdi], 1
0x180057591  xor     ebx, ebx
0x180057593  mov     rcx, [rbp+hKey]; hKey
0x180057597  test    rcx, rcx
0x18005759a  jz      short loc_1800575A2
0x18005759c  call    cs:__imp_RegCloseKey
0x1800575a2  lea     rcx, [rbp+var_28]; this
0x1800575a6  call    ??1CPathString@@QEAA@XZ; CPathString::~CPathString(void)
0x1800575ab  lea     rcx, [rbp+var_50]; this
0x1800575af  call    ??1CPathString@@QEAA@XZ; CPathString::~CPathString(void)
0x1800575b4  lea     r11, [rsp+80h+var_s0]
0x1800575bc  mov     eax, ebx
0x1800575be  mov     rbx, [r11+20h]
0x1800575c2  mov     rsi, [r11+30h]
0x1800575c6  mov     rsp, r11
0x1800575c9  pop     r14
0x1800575cb  pop     rdi
0x1800575cc  pop     rbp
0x1800575cd  retn
0x1800575ce  cmp     ebx, 2
0x1800575d1  jz      short loc_180057591
0x1800575d3  cmp     ebx, 3FAh
0x1800575d9  jz      short loc_180057591
0x1800575db  test    ebx, 0FFFF0000h
0x1800575e1  jnz     short loc_1800575F9
0x1800575e3  test    ebx, ebx
0x1800575e5  jle     short loc_1800575ED
0x1800575e7  or      ebx, 80070000h
0x1800575ed  and     ebx, 0D048FFFFh
0x1800575f3  or      ebx, 50480000h
0x1800575f9  test    ebx, ebx
0x1800575fb  jns     short loc_180057593
0x1800575fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180057604  lea     rax, WPP_GLOBAL_Control
0x18005760b  cmp     rcx, rax
0x18005760e  jz      short loc_180057593
0x180057610  test    byte ptr [rcx+1Ch], 4
0x180057614  jz      loc_180057593
0x18005761a  cmp     byte ptr [rcx+19h], 2
0x18005761e  jb      loc_180057593
0x180057624  mov     edx, 70h ; 'p'
0x180057629  jmp     loc_18005749D
```
