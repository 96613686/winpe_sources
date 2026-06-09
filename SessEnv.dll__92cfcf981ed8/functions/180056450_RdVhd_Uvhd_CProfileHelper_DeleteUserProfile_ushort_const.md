# RdVhd::Uvhd::CProfileHelper::DeleteUserProfile(ushort const *)

- ea: `0x180056450`
- end: `0x180056865`
- name: `?DeleteUserProfile@CProfileHelper@Uvhd@RdVhd@@UEBAJPEBG@Z`
- size: `1045`
- prototype: `__int64 __fastcall(RdVhd::Uvhd::CProfileHelper *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180054fe0`

## callees

- `0x180004db0`
- `0x1800141e8`
- `0x180019b38`
- `0x180031178`
- `0x180043df0`
- `0x1800488e4`
- `0x180048b28`
- `0x1800561c0`
- `0x180056450`
- `0x180056af4`
- `0x180057110`
- `0x18005d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800564d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800564d8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180056655`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180056655`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005668f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180056845`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005668f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180056845`
- `USERENV!DeleteProfileW` at `0x1800564ca`
- `USERENV!DeleteProfileW` at `0x1800564ca`

## string_xrefs

- `0x1800564a2`: `szUserSID`
- `0x1800567da`: `RegOpenKeyEx(%s), backup profile key`

## pseudocode

```c
__int64 __fastcall RdVhd::Uvhd::CProfileHelper::DeleteUserProfile(
        RdVhd::Uvhd::CProfileHelper *this,
        const unsigned __int16 *a2)
{
  int ProfileKeyName; // ebx
  signed int LastError; // eax
  RdVhd::Uvhd::CUvhdDiskManager *v6; // rcx
  __int64 v7; // rdx
  const WCHAR *v8; // rax
  RdVhd::Uvhd::CUvhdDiskManager *v9; // rcx
  __int64 v10; // rdx
  const unsigned __int16 *v11; // rax
  RdVhd::Uvhd::CProfileHelper *v12; // rcx
  __int64 v13; // rax
  __int64 (__fastcall *v14)(__int64, __int64, __int64); // r10
  __int64 v15; // r11
  int v16; // eax
  void **v18; // [rsp+30h] [rbp-39h] BYREF
  int v19; // [rsp+38h] [rbp-31h]
  __int64 v20; // [rsp+3Ch] [rbp-2Dh]
  int v21; // [rsp+44h] [rbp-25h]
  __int64 v22; // [rsp+48h] [rbp-21h]
  int v23; // [rsp+50h] [rbp-19h]
  void **v24; // [rsp+58h] [rbp-11h] BYREF
  int v25; // [rsp+60h] [rbp-9h]
  __int64 v26; // [rsp+64h] [rbp-5h]
  int v27; // [rsp+6Ch] [rbp+3h]
  __int64 v28; // [rsp+70h] [rbp+7h]
  int v29; // [rsp+78h] [rbp+Fh]
  void **v30; // [rsp+80h] [rbp+17h] BYREF
  int v31; // [rsp+88h] [rbp+1Fh]
  __int64 v32; // [rsp+8Ch] [rbp+23h]
  int v33; // [rsp+94h] [rbp+2Bh]
  __int64 v34; // [rsp+98h] [rbp+2Fh]
  int v35; // [rsp+A0h] [rbp+37h]
  HKEY hKey; // [rsp+D8h] [rbp+6Fh] BYREF

  hKey = 0;
  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_8bdd996048cc3a3a6adb915db88b6959_Traceguids, L"szUserSID");
    }
    ProfileKeyName = -2147024809;
    goto LABEL_63;
  }
  ProfileKeyName = 0;
  if ( !DeleteProfileW(a2, 0, 0) )
  {
    LastError = GetLastError();
    ProfileKeyName = LastError;
    if ( LastError && (LastError & 0xFFFF0000) == 0 )
    {
      if ( LastError > 0 )
        ProfileKeyName = (unsigned __int16)LastError | 0x80070000;
      ProfileKeyName = ProfileKeyName & 0x8000FFFF | 0x50260000;
    }
    if ( (_WORD)ProfileKeyName == 2 )
    {
      v26 = 128;
      v29 = 0x8000000;
      v24 = &CPathString::`vftable';
      v23 = 0x8000000;
      v18 = &CPathString::`vftable';
      v28 = 0;
      v27 = 0;
      v25 = 0;
      v20 = 128;
      v22 = 0;
      v21 = 0;
      v19 = 0;
      ProfileKeyName = RdVhd::Uvhd::CProfileHelper::GetProfileKeyName(
                         (RdVhd::Uvhd::CProfileHelper *)&CPathString::`vftable',
                         a2,
                         (struct CPathString *)&v24);
      if ( ProfileKeyName < 0 )
      {
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_62;
        }
        v7 = 20;
        goto LABEL_61;
      }
      ProfileKeyName = CBaseStringT<unsigned short>::Set<unsigned short>(&v18, &v24);
      if ( ProfileKeyName < 0 )
      {
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_62;
        }
        v7 = 21;
        goto LABEL_61;
      }
      ProfileKeyName = CBaseStringT<unsigned short>::Append((__int64)&v18, L".bak", 4u);
      if ( ProfileKeyName < 0 )
      {
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_62;
        }
        v7 = 22;
        goto LABEL_61;
      }
      v8 = (const WCHAR *)CBaseStringT<unsigned short>::PContents(&v18);
      ProfileKeyName = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v8, 0, 1u, &hKey);
      if ( ProfileKeyName )
      {
        if ( ProfileKeyName != 2 )
        {
          if ( (ProfileKeyName & 0xFFFF0000) == 0 )
          {
            if ( ProfileKeyName > 0 )
              ProfileKeyName |= 0x80070000;
            ProfileKeyName = ProfileKeyName & 0x8000FFFF | 0x50280000;
          }
          _TraceNrmRdvVmEx(L"UVHD", (unsigned int)ProfileKeyName, L"RegOpenKeyEx(%s), backup profile key");
          if ( ProfileKeyName >= 0 )
            goto LABEL_62;
          v6 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_62;
          }
          v7 = 26;
LABEL_61:
          WPP_SF_d(
            *((_QWORD *)v6 + 2),
            v7,
            WPP_8bdd996048cc3a3a6adb915db88b6959_Traceguids,
            (unsigned int)ProfileKeyName);
          goto LABEL_62;
        }
        ProfileKeyName = 1;
LABEL_62:
        CPathString::~CPathString((CPathString *)&v18);
        CPathString::~CPathString((CPathString *)&v24);
        goto LABEL_63;
      }
      v30 = &CPathString::`vftable';
      v32 = 128;
      v34 = 0;
      v33 = 0;
      v35 = 0x8000000;
      v31 = 0;
      RegCloseKey(hKey);
      hKey = 0;
      ProfileKeyName = RdVhd::Uvhd::CProfileHelper::GetUserProfileDirectoryW(this, a2, 1, (struct CPathString *)&v30);
      if ( ProfileKeyName >= 0 )
      {
        v11 = (const unsigned __int16 *)CBaseStringT<unsigned short>::PContents(&v18);
        ProfileKeyName = RdVhd::Uvhd::CProfileHelper::DeleteRegistryTree(v12, v11);
        if ( ProfileKeyName >= 0 )
        {
          v13 = CBaseStringT<unsigned short>::PContents(&v30);
          ProfileKeyName = v14(v15, v13, 16);
          if ( ProfileKeyName >= 0 )
          {
            CPathString::~CPathString((CPathString *)&v30);
            v16 = 0;
            if ( ProfileKeyName != 1 )
              v16 = ProfileKeyName;
            ProfileKeyName = v16;
            goto LABEL_62;
          }
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_36;
          }
          v10 = 25;
        }
        else
        {
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_36;
          }
          v10 = 24;
        }
      }
      else
      {
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_36;
        }
        v10 = 23;
      }
      WPP_SF_d(*((_QWORD *)v9 + 2), v10, WPP_8bdd996048cc3a3a6adb915db88b6959_Traceguids, (unsigned int)ProfileKeyName);
LABEL_36:
      CPathString::~CPathString((CPathString *)&v30);
      goto LABEL_62;
    }
  }
LABEL_63:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)ProfileKeyName;
}

```

## disassembly

```asm
0x180056450  mov     [rsp-8+arg_0], rbx
0x180056455  mov     [rsp-8+arg_10], rsi
0x18005645a  push    rbp
0x18005645b  push    rdi
0x18005645c  push    r14
0x18005645e  lea     rbp, [rsp-47h]
0x180056463  sub     rsp, 0B0h
0x18005646a  xor     r14d, r14d
0x18005646d  mov     rdi, rdx
0x180056470  mov     [rbp+57h+hKey], r14
0x180056474  mov     rsi, rcx
0x180056477  test    rdx, rdx
0x18005647a  jnz     short loc_1800564BF
0x18005647c  mov     rcx, cs:WPP_GLOBAL_Control
0x180056483  lea     rax, WPP_GLOBAL_Control
0x18005648a  cmp     rcx, rax
0x18005648d  jz      short loc_1800564B5
0x18005648f  test    byte ptr [rcx+1Ch], 4
0x180056493  jz      short loc_1800564B5
0x180056495  cmp     byte ptr [rcx+19h], 2
0x180056499  jb      short loc_1800564B5
0x18005649b  mov     rcx, [rcx+10h]
0x18005649f  lea     edx, [rdi+13h]
0x1800564a2  lea     r9, aSzusersid_0; "szUserSID"
0x1800564a9  lea     r8, WPP_8bdd996048cc3a3a6adb915db88b6959_Traceguids
0x1800564b0  call    WPP_SF_S
0x1800564b5  mov     ebx, 80070057h
0x1800564ba  jmp     loc_18005683C
0x1800564bf  xor     r8d, r8d; lpComputerName
0x1800564c2  xor     edx, edx; lpProfilePath
0x1800564c4  mov     rcx, rdi; lpSidString
0x1800564c7  mov     ebx, r14d
0x1800564ca  call    cs:__imp_DeleteProfileW
0x1800564d0  test    eax, eax
0x1800564d2  jnz     loc_18005683C
0x1800564d8  call    cs:__imp_GetLastError
0x1800564de  mov     ebx, eax
0x1800564e0  test    eax, eax
0x1800564e2  jz      short loc_180056504
0x1800564e4  test    eax, 0FFFF0000h
0x1800564e9  jnz     short loc_180056504
0x1800564eb  test    eax, eax
0x1800564ed  jle     short loc_1800564F8
0x1800564ef  movzx   ebx, ax
0x1800564f2  or      ebx, 80070000h
0x1800564f8  and     ebx, 0D026FFFFh
0x1800564fe  or      ebx, 50260000h
0x180056504  cmp     bx, 2
0x180056508  jnz     loc_18005683C
0x18005650e  mov     eax, 8000000h
0x180056513  mov     [rbp+57h+var_5C], 80h
0x18005651b  lea     rcx, ??_7CPathString@@6B@; this
0x180056522  mov     [rbp+57h+var_48], eax
0x180056525  lea     r8, [rbp+57h+var_68]; struct CPathString *
0x180056529  mov     [rbp+57h+var_68], rcx
0x18005652d  mov     rdx, rdi; unsigned __int16 *
0x180056530  mov     [rbp+57h+var_70], eax
0x180056533  mov     [rbp+57h+var_90], rcx
0x180056537  mov     [rbp+57h+var_50], r14
0x18005653b  mov     [rbp+57h+var_54], r14d
0x18005653f  mov     [rbp+57h+var_60], r14d
0x180056543  mov     [rbp+57h+var_84], 80h
0x18005654b  mov     [rbp+57h+var_78], r14
0x18005654f  mov     [rbp+57h+var_7C], r14d
0x180056553  mov     [rbp+57h+var_88], r14d
0x180056557  call    ?GetProfileKeyName@CProfileHelper@Uvhd@RdVhd@@AEBAJPEBGAEAVCPathString@@@Z; RdVhd::Uvhd::CProfileHelper::GetProfileKeyName(ushort const *,CPathString &)
0x18005655c  mov     ebx, eax
0x18005655e  test    eax, eax
0x180056560  jns     short loc_180056597
0x180056562  mov     rcx, cs:WPP_GLOBAL_Control
0x180056569  lea     rax, WPP_GLOBAL_Control
0x180056570  cmp     rcx, rax
0x180056573  jz      loc_18005682A
0x180056579  test    byte ptr [rcx+1Ch], 4
0x18005657d  jz      loc_18005682A
0x180056583  cmp     byte ptr [rcx+19h], 2
0x180056587  jb      loc_18005682A
0x18005658d  mov     edx, 14h
0x180056592  jmp     loc_180056817
0x180056597  lea     rdx, [rbp+57h+var_68]
0x18005659b  lea     rcx, [rbp+57h+var_90]
0x18005659f  call    ??$Set@G@?$CBaseStringT@G@@QEAAJAEBV0@@Z; CBaseStringT<ushort>::Set<ushort>(CBaseStringT<ushort> const &)
0x1800565a4  mov     ebx, eax
0x1800565a6  test    eax, eax
0x1800565a8  jns     short loc_1800565DF
0x1800565aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800565b1  lea     rax, WPP_GLOBAL_Control
0x1800565b8  cmp     rcx, rax
0x1800565bb  jz      loc_18005682A
0x1800565c1  test    byte ptr [rcx+1Ch], 4
0x1800565c5  jz      loc_18005682A
0x1800565cb  cmp     byte ptr [rcx+19h], 2
0x1800565cf  jb      loc_18005682A
0x1800565d5  mov     edx, 15h
0x1800565da  jmp     loc_180056817
0x1800565df  mov     r8d, 4
0x1800565e5  lea     rdx, aBak; ".bak"
0x1800565ec  lea     rcx, [rbp+57h+var_90]
0x1800565f0  call    ?Append@?$CBaseStringT@G@@QEAAJPEBGK@Z; CBaseStringT<ushort>::Append(ushort const *,ulong)
0x1800565f5  mov     ebx, eax
0x1800565f7  test    eax, eax
0x1800565f9  jns     short loc_180056630
0x1800565fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180056602  lea     rax, WPP_GLOBAL_Control
0x180056609  cmp     rcx, rax
0x18005660c  jz      loc_18005682A
0x180056612  test    byte ptr [rcx+1Ch], 4
0x180056616  jz      loc_18005682A
0x18005661c  cmp     byte ptr [rcx+19h], 2
0x180056620  jb      loc_18005682A
0x180056626  mov     edx, 16h
0x18005662b  jmp     loc_180056817
0x180056630  lea     rcx, [rbp+57h+var_90]
0x180056634  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x180056639  mov     rdx, rax; lpSubKey
0x18005663c  mov     r9d, 1; samDesired
0x180056642  lea     rax, [rbp+57h+hKey]
0x180056646  xor     r8d, r8d; ulOptions
0x180056649  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180056650  mov     [rsp+0C0h+phkResult], rax; phkResult
0x180056655  call    cs:__imp_RegOpenKeyExW
0x18005665b  mov     ebx, eax
0x18005665d  test    eax, eax
0x18005665f  jnz     loc_1800567AD
0x180056665  mov     rcx, [rbp+57h+hKey]; hKey
0x180056669  lea     rax, ??_7CPathString@@6B@; const CPathString::`vftable'
0x180056670  mov     [rbp+57h+var_40], rax
0x180056674  mov     [rbp+57h+var_34], 80h
0x18005667c  mov     [rbp+57h+var_28], r14
0x180056680  mov     [rbp+57h+var_2C], r14d
0x180056684  mov     [rbp+57h+var_20], 8000000h
0x18005668b  mov     [rbp+57h+var_38], r14d
0x18005668f  call    cs:__imp_RegCloseKey
0x180056695  lea     r9, [rbp+57h+var_40]; struct CPathString *
0x180056699  mov     [rbp+57h+hKey], r14
0x18005669d  lea     r8d, [rbx+1]; int
0x1800566a1  mov     rdx, rdi; unsigned __int16 *
0x1800566a4  mov     rcx, rsi; this
0x1800566a7  call    ?GetUserProfileDirectoryW@CProfileHelper@Uvhd@RdVhd@@UEBAJPEBGHPEAVCPathString@@@Z; RdVhd::Uvhd::CProfileHelper::GetUserProfileDirectoryW(ushort const *,int,CPathString *)
0x1800566ac  mov     ebx, eax
0x1800566ae  test    eax, eax
0x1800566b0  jns     short loc_1800566F7
0x1800566b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800566b9  lea     rax, WPP_GLOBAL_Control
0x1800566c0  cmp     rcx, rax
0x1800566c3  jz      short loc_1800566E9
0x1800566c5  test    byte ptr [rcx+1Ch], 4
0x1800566c9  jz      short loc_1800566E9
0x1800566cb  cmp     byte ptr [rcx+19h], 2
0x1800566cf  jb      short loc_1800566E9
0x1800566d1  mov     edx, 17h
0x1800566d6  mov     rcx, [rcx+10h]
0x1800566da  lea     r8, WPP_8bdd996048cc3a3a6adb915db88b6959_Traceguids
0x1800566e1  mov     r9d, ebx
0x1800566e4  call    WPP_SF_d
0x1800566e9  lea     rcx, [rbp+57h+var_40]; this
0x1800566ed  call    ??1CPathString@@QEAA@XZ; CPathString::~CPathString(void)
0x1800566f2  jmp     loc_18005682A
0x1800566f7  lea     rcx, [rbp+57h+var_90]
0x1800566fb  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x180056700  mov     rdx, rax; unsigned __int16 *
0x180056703  call    ?DeleteRegistryTree@CProfileHelper@Uvhd@RdVhd@@AEBAJPEBG@Z; RdVhd::Uvhd::CProfileHelper::DeleteRegistryTree(ushort const *)
0x180056708  mov     ebx, eax
0x18005670a  test    eax, eax
0x18005670c  jns     short loc_180056734
0x18005670e  mov     rcx, cs:WPP_GLOBAL_Control
0x180056715  lea     rax, WPP_GLOBAL_Control
0x18005671c  cmp     rcx, rax
0x18005671f  jz      short loc_1800566E9
0x180056721  test    byte ptr [rcx+1Ch], 4
0x180056725  jz      short loc_1800566E9
0x180056727  cmp     byte ptr [rcx+19h], 2
0x18005672b  jb      short loc_1800566E9
0x18005672d  mov     edx, 18h
0x180056732  jmp     short loc_1800566D6
0x180056734  mov     r11, [rsi+8]
0x180056738  lea     rcx, [rbp+57h+var_40]
0x18005673c  mov     rax, [r11]
0x18005673f  mov     r10, [rax+40h]
0x180056743  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x180056748  mov     rdx, rax
0x18005674b  mov     r8d, 10h
0x180056751  mov     rax, r10
0x180056754  mov     rcx, r11
0x180056757  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005675c  mov     ebx, eax
0x18005675e  test    eax, eax
0x180056760  jns     short loc_180056797
0x180056762  mov     rcx, cs:WPP_GLOBAL_Control
0x180056769  lea     rax, WPP_GLOBAL_Control
0x180056770  cmp     rcx, rax
0x180056773  jz      loc_1800566E9
0x180056779  test    byte ptr [rcx+1Ch], 4
0x18005677d  jz      loc_1800566E9
0x180056783  cmp     byte ptr [rcx+19h], 2
0x180056787  jb      loc_1800566E9
0x18005678d  mov     edx, 19h
0x180056792  jmp     loc_1800566D6
0x180056797  lea     rcx, [rbp+57h+var_40]; this
0x18005679b  call    ??1CPathString@@QEAA@XZ; CPathString::~CPathString(void)
0x1800567a0  cmp     ebx, 1
0x1800567a3  mov     eax, r14d
0x1800567a6  cmovnz  eax, ebx
0x1800567a9  mov     ebx, eax
0x1800567ab  jmp     short loc_18005682A
0x1800567ad  cmp     ebx, 2
0x1800567b0  jnz     short loc_1800567B9
0x1800567b2  mov     ebx, 1
0x1800567b7  jmp     short loc_18005682A
0x1800567b9  test    ebx, 0FFFF0000h
0x1800567bf  jnz     short loc_1800567D7
0x1800567c1  test    ebx, ebx
0x1800567c3  jle     short loc_1800567CB
0x1800567c5  or      ebx, 80070000h
0x1800567cb  and     ebx, 0D028FFFFh
0x1800567d1  or      ebx, 50280000h
0x1800567d7  mov     r9, rdi
0x1800567da  lea     r8, aRegopenkeyexSB; "RegOpenKeyEx(%s), backup profile key"
0x1800567e1  mov     edx, ebx; int
0x1800567e3  lea     rcx, aUvhd; "UVHD"
0x1800567ea  call    ?_TraceNrmRdvVmEx@@YAXPEBGJ0ZZ; _TraceNrmRdvVmEx(ushort const *,long,ushort const *,...)
0x1800567ef  test    ebx, ebx
0x1800567f1  jns     short loc_18005682A
0x1800567f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800567fa  lea     rax, WPP_GLOBAL_Control
0x180056801  cmp     rcx, rax
0x180056804  jz      short loc_18005682A
0x180056806  test    byte ptr [rcx+1Ch], 4
0x18005680a  jz      short loc_18005682A
0x18005680c  cmp     byte ptr [rcx+19h], 2
0x180056810  jb      short loc_18005682A
0x180056812  mov     edx, 1Ah
0x180056817  mov     rcx, [rcx+10h]
0x18005681b  lea     r8, WPP_8bdd996048cc3a3a6adb915db88b6959_Traceguids
0x180056822  mov     r9d, ebx
0x180056825  call    WPP_SF_d
0x18005682a  lea     rcx, [rbp+57h+var_90]; this
0x18005682e  call    ??1CPathString@@QEAA@XZ; CPathString::~CPathString(void)
0x180056833  lea     rcx, [rbp+57h+var_68]; this
0x180056837  call    ??1CPathString@@QEAA@XZ; CPathString::~CPathString(void)
0x18005683c  mov     rcx, [rbp+57h+hKey]; hKey
0x180056840  test    rcx, rcx
0x180056843  jz      short loc_18005684B
0x180056845  call    cs:__imp_RegCloseKey
0x18005684b  lea     r11, [rsp+0C0h+var_10]
0x180056853  mov     eax, ebx
0x180056855  mov     rbx, [r11+20h]
0x180056859  mov     rsi, [r11+30h]
0x18005685d  mov     rsp, r11
0x180056860  pop     r14
0x180056862  pop     rdi
0x180056863  pop     rbp
0x180056864  retn
```
