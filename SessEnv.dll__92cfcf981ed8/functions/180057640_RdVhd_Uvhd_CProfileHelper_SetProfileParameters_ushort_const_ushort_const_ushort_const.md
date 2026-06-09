# RdVhd::Uvhd::CProfileHelper::SetProfileParameters(ushort const *,ushort const *,ushort const *)

- ea: `0x180057640`
- end: `0x18005797c`
- name: `?SetProfileParameters@CProfileHelper@Uvhd@RdVhd@@UEBAJPEBG00@Z`
- size: `828`
- prototype: `int(RdVhd::Uvhd::CProfileHelper *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config`

## callees

- `0x180004db0`
- `0x180019b38`
- `0x18002b5dc`
- `0x1800488e4`
- `0x180048b28`
- `0x180056af4`
- `0x180057640`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005782e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005782e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800578a0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180057901`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800578a0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180057901`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005795e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005795e`

## string_xrefs

- `0x1800576c9`: `szUserSID`

## pseudocode

```c
__int64 __fastcall RdVhd::Uvhd::CProfileHelper::SetProfileParameters(
        RdVhd::Uvhd::CProfileHelper *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  RdVhd::Uvhd::CUvhdDiskManager *v6; // rcx
  __int64 v7; // rdx
  const wchar_t *v8; // r9
  signed int ProfileKeyName; // ebx
  RdVhd::Uvhd::CUvhdDiskManager *v10; // rcx
  __int64 v11; // rdx
  DWORD cbData; // r14d
  RdVhd::Uvhd::CProfileHelper *v13; // rcx
  const unsigned __int16 *v14; // r11
  DWORD v15; // esi
  const WCHAR *v16; // rax
  LSTATUS v17; // eax
  LSTATUS v18; // eax
  LSTATUS v19; // eax
  unsigned __int64 v21; // [rsp+30h] [rbp-48h] BYREF
  unsigned __int64 v22; // [rsp+38h] [rbp-40h] BYREF
  void **v23; // [rsp+40h] [rbp-38h] BYREF
  int v24; // [rsp+48h] [rbp-30h]
  __int64 v25; // [rsp+4Ch] [rbp-2Ch]
  int v26; // [rsp+54h] [rbp-24h]
  __int64 v27; // [rsp+58h] [rbp-20h]
  int v28; // [rsp+60h] [rbp-18h]
  HKEY hKey; // [rsp+B8h] [rbp+40h] BYREF

  v25 = 128;
  v23 = &CPathString::`vftable';
  v27 = 0;
  v26 = 0;
  v28 = 0x8000000;
  v24 = 0;
  v21 = 0;
  v22 = 0;
  hKey = 0;
  if ( !a2 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    v7 = 115;
    v8 = L"szUserSID";
LABEL_6:
    WPP_SF_S(*((_QWORD *)v6 + 2), v7, WPP_8bdd996048cc3a3a6adb915db88b6959_Traceguids, v8);
LABEL_7:
    ProfileKeyName = -2147024809;
    goto LABEL_53;
  }
  if ( !a4 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    v7 = 116;
    v8 = L"szProfileDiskName";
    goto LABEL_6;
  }
  ProfileKeyName = StringCbLengthW(a4, 0x208u, &v21);
  if ( ProfileKeyName >= 0 )
  {
    cbData = v21 + 2;
    ProfileKeyName = StringCbLengthW(a3, 0x208u, &v22);
    if ( ProfileKeyName >= 0 )
    {
      v15 = v22 + 2;
      ProfileKeyName = RdVhd::Uvhd::CProfileHelper::GetProfileKeyName(v13, v14, (struct CPathString *)&v23);
      if ( ProfileKeyName >= 0 )
      {
        v16 = (const WCHAR *)CBaseStringT<unsigned short>::PContents(&v23);
        v17 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v16, 0, 2u, &hKey);
        if ( v17 )
        {
          if ( v17 > 0 )
            ProfileKeyName = (unsigned __int16)v17 | 0x80070000;
          else
            ProfileKeyName = v17;
          v10 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_53;
          }
          v11 = 120;
        }
        else
        {
          v18 = RegSetValueExW(hKey, L"ProfileDiskName", 0, 1u, (const BYTE *)a4, cbData);
          if ( v18 )
          {
            if ( v18 > 0 )
              ProfileKeyName = (unsigned __int16)v18 | 0x80070000;
            else
              ProfileKeyName = v18;
            v10 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_53;
            }
            v11 = 121;
          }
          else
          {
            v19 = RegSetValueExW(hKey, L"ProfileDiskUpn", 0, 1u, (const BYTE *)a3, v15);
            if ( !v19 )
              goto LABEL_53;
            ProfileKeyName = v19 > 0 ? (unsigned __int16)v19 | 0x80070000 : v19;
            v10 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_53;
            }
            v11 = 122;
          }
        }
        goto LABEL_52;
      }
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v11 = 119;
        goto LABEL_52;
      }
    }
    else
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v11 = 118;
        goto LABEL_52;
      }
    }
  }
  else
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v11 = 117;
LABEL_52:
      WPP_SF_d(*((_QWORD *)v10 + 2), v11, WPP_8bdd996048cc3a3a6adb915db88b6959_Traceguids, (unsigned int)ProfileKeyName);
    }
  }
LABEL_53:
  if ( hKey )
    RegCloseKey(hKey);
  CPathString::~CPathString((CPathString *)&v23);
  return (unsigned int)ProfileKeyName;
}

```

## disassembly

```asm
0x180057640  push    rbp
0x180057642  push    rbx
0x180057643  push    rsi
0x180057644  push    rdi
0x180057645  push    r14
0x180057647  push    r15
0x180057649  mov     rbp, rsp
0x18005764c  sub     rsp, 78h
0x180057650  lea     rax, ??_7CPathString@@6B@; const CPathString::`vftable'
0x180057657  mov     [rbp+var_2C], 80h
0x18005765f  mov     [rbp+var_38], rax
0x180057663  mov     rdi, r9
0x180057666  mov     r15, r8
0x180057669  mov     [rbp+var_20], 0
0x180057671  mov     r11, rdx
0x180057674  mov     [rbp+var_24], 0
0x18005767b  mov     [rbp+var_18], 8000000h
0x180057682  mov     [rbp+var_30], 0
0x180057689  mov     [rbp+var_48], 0
0x180057691  mov     [rbp+var_40], 0
0x180057699  mov     [rbp+hKey], 0
0x1800576a1  test    rdx, rdx
0x1800576a4  jnz     short loc_1800576EA
0x1800576a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800576ad  lea     rax, WPP_GLOBAL_Control
0x1800576b4  cmp     rcx, rax
0x1800576b7  jz      short loc_1800576E0
0x1800576b9  test    byte ptr [rcx+1Ch], 4
0x1800576bd  jz      short loc_1800576E0
0x1800576bf  cmp     byte ptr [rcx+19h], 2
0x1800576c3  jb      short loc_1800576E0
0x1800576c5  lea     edx, [r11+73h]
0x1800576c9  lea     r9, aSzusersid_0; "szUserSID"
0x1800576d0  mov     rcx, [rcx+10h]
0x1800576d4  lea     r8, WPP_8bdd996048cc3a3a6adb915db88b6959_Traceguids
0x1800576db  call    WPP_SF_S
0x1800576e0  mov     ebx, 80070057h
0x1800576e5  jmp     loc_180057955
0x1800576ea  test    rdi, rdi
0x1800576ed  jnz     short loc_18005771A
0x1800576ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800576f6  lea     rax, WPP_GLOBAL_Control
0x1800576fd  cmp     rcx, rax
0x180057700  jz      short loc_1800576E0
0x180057702  test    byte ptr [rcx+1Ch], 4
0x180057706  jz      short loc_1800576E0
0x180057708  cmp     byte ptr [rcx+19h], 2
0x18005770c  jb      short loc_1800576E0
0x18005770e  lea     edx, [rdi+74h]
0x180057711  lea     r9, aSzprofilediskn; "szProfileDiskName"
0x180057718  jmp     short loc_1800576D0
0x18005771a  mov     esi, 208h
0x18005771f  lea     r8, [rbp+var_48]; unsigned __int64 *
0x180057723  mov     edx, esi; unsigned __int64
0x180057725  mov     rcx, rdi; unsigned __int16 *
0x180057728  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18005772d  mov     ebx, eax
0x18005772f  test    eax, eax
0x180057731  jns     short loc_180057768
0x180057733  mov     rcx, cs:WPP_GLOBAL_Control
0x18005773a  lea     rax, WPP_GLOBAL_Control
0x180057741  cmp     rcx, rax
0x180057744  jz      loc_180057955
0x18005774a  test    byte ptr [rcx+1Ch], 4
0x18005774e  jz      loc_180057955
0x180057754  cmp     byte ptr [rcx+19h], 2
0x180057758  jb      loc_180057955
0x18005775e  mov     edx, 75h ; 'u'
0x180057763  jmp     loc_180057942
0x180057768  mov     r14, [rbp+var_48]
0x18005776c  lea     r8, [rbp+var_40]; unsigned __int64 *
0x180057770  mov     rdx, rsi; unsigned __int64
0x180057773  mov     rcx, r15; unsigned __int16 *
0x180057776  add     r14, 2
0x18005777a  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18005777f  mov     ebx, eax
0x180057781  test    eax, eax
0x180057783  jns     short loc_1800577BA
0x180057785  mov     rcx, cs:WPP_GLOBAL_Control
0x18005778c  lea     rax, WPP_GLOBAL_Control
0x180057793  cmp     rcx, rax
0x180057796  jz      loc_180057955
0x18005779c  test    byte ptr [rcx+1Ch], 4
0x1800577a0  jz      loc_180057955
0x1800577a6  cmp     byte ptr [rcx+19h], 2
0x1800577aa  jb      loc_180057955
0x1800577b0  mov     edx, 76h ; 'v'
0x1800577b5  jmp     loc_180057942
0x1800577ba  mov     rsi, [rbp+var_40]
0x1800577be  lea     r8, [rbp+var_38]; struct CPathString *
0x1800577c2  mov     rdx, r11; unsigned __int16 *
0x1800577c5  add     rsi, 2
0x1800577c9  call    ?GetProfileKeyName@CProfileHelper@Uvhd@RdVhd@@AEBAJPEBGAEAVCPathString@@@Z; RdVhd::Uvhd::CProfileHelper::GetProfileKeyName(ushort const *,CPathString &)
0x1800577ce  mov     ebx, eax
0x1800577d0  test    eax, eax
0x1800577d2  jns     short loc_180057809
0x1800577d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800577db  lea     rax, WPP_GLOBAL_Control
0x1800577e2  cmp     rcx, rax
0x1800577e5  jz      loc_180057955
0x1800577eb  test    byte ptr [rcx+1Ch], 4
0x1800577ef  jz      loc_180057955
0x1800577f5  cmp     byte ptr [rcx+19h], 2
0x1800577f9  jb      loc_180057955
0x1800577ff  mov     edx, 77h ; 'w'
0x180057804  jmp     loc_180057942
0x180057809  lea     rcx, [rbp+var_38]
0x18005780d  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x180057812  mov     rdx, rax; lpSubKey
0x180057815  mov     r9d, 2; samDesired
0x18005781b  lea     rax, [rbp+hKey]
0x18005781f  xor     r8d, r8d; ulOptions
0x180057822  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180057829  mov     [rsp+78h+phkResult], rax; phkResult
0x18005782e  call    cs:__imp_RegOpenKeyExW
0x180057834  test    eax, eax
0x180057836  jz      short loc_180057880
0x180057838  jg      short loc_18005783E
0x18005783a  mov     ebx, eax
0x18005783c  jmp     short loc_180057847
0x18005783e  movzx   ebx, ax
0x180057841  or      ebx, 80070000h
0x180057847  test    ebx, ebx
0x180057849  jns     short loc_180057880
0x18005784b  mov     rcx, cs:WPP_GLOBAL_Control
0x180057852  lea     rax, WPP_GLOBAL_Control
0x180057859  cmp     rcx, rax
0x18005785c  jz      loc_180057955
0x180057862  test    byte ptr [rcx+1Ch], 4
0x180057866  jz      loc_180057955
0x18005786c  cmp     byte ptr [rcx+19h], 2
0x180057870  jb      loc_180057955
0x180057876  mov     edx, 78h ; 'x'
0x18005787b  jmp     loc_180057942
0x180057880  mov     rcx, [rbp+hKey]; hKey
0x180057884  lea     rdx, aProfiledisknam; "ProfileDiskName"
0x18005788b  mov     [rsp+78h+cbData], r14d; cbData
0x180057890  xor     r8d, r8d; Reserved
0x180057893  mov     [rsp+78h+phkResult], rdi; lpData
0x180057898  mov     edi, 1
0x18005789d  mov     r9d, edi; dwType
0x1800578a0  call    cs:__imp_RegSetValueExW
0x1800578a6  test    eax, eax
0x1800578a8  jz      short loc_1800578E7
0x1800578aa  jg      short loc_1800578B0
0x1800578ac  mov     ebx, eax
0x1800578ae  jmp     short loc_1800578B9
0x1800578b0  movzx   ebx, ax
0x1800578b3  or      ebx, 80070000h
0x1800578b9  test    ebx, ebx
0x1800578bb  jns     short loc_1800578E7
0x1800578bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800578c4  lea     rax, WPP_GLOBAL_Control
0x1800578cb  cmp     rcx, rax
0x1800578ce  jz      loc_180057955
0x1800578d4  test    byte ptr [rcx+1Ch], 4
0x1800578d8  jz      short loc_180057955
0x1800578da  cmp     byte ptr [rcx+19h], 2
0x1800578de  jb      short loc_180057955
0x1800578e0  mov     edx, 79h ; 'y'
0x1800578e5  jmp     short loc_180057942
0x1800578e7  mov     rcx, [rbp+hKey]; hKey
0x1800578eb  lea     rdx, aProfilediskupn; "ProfileDiskUpn"
0x1800578f2  mov     [rsp+78h+cbData], esi; cbData
0x1800578f6  mov     r9d, edi; dwType
0x1800578f9  xor     r8d, r8d; Reserved
0x1800578fc  mov     [rsp+78h+phkResult], r15; lpData
0x180057901  call    cs:__imp_RegSetValueExW
0x180057907  test    eax, eax
0x180057909  jz      short loc_180057955
0x18005790b  jg      short loc_180057911
0x18005790d  mov     ebx, eax
0x18005790f  jmp     short loc_18005791A
0x180057911  movzx   ebx, ax
0x180057914  or      ebx, 80070000h
0x18005791a  test    ebx, ebx
0x18005791c  jns     short loc_180057955
0x18005791e  mov     rcx, cs:WPP_GLOBAL_Control
0x180057925  lea     rax, WPP_GLOBAL_Control
0x18005792c  cmp     rcx, rax
0x18005792f  jz      short loc_180057955
0x180057931  test    byte ptr [rcx+1Ch], 4
0x180057935  jz      short loc_180057955
0x180057937  cmp     byte ptr [rcx+19h], 2
0x18005793b  jb      short loc_180057955
0x18005793d  mov     edx, 7Ah ; 'z'
0x180057942  mov     rcx, [rcx+10h]
0x180057946  lea     r8, WPP_8bdd996048cc3a3a6adb915db88b6959_Traceguids
0x18005794d  mov     r9d, ebx
0x180057950  call    WPP_SF_d
0x180057955  mov     rcx, [rbp+hKey]; hKey
0x180057959  test    rcx, rcx
0x18005795c  jz      short loc_180057964
0x18005795e  call    cs:__imp_RegCloseKey
0x180057964  lea     rcx, [rbp+var_38]; this
0x180057968  call    ??1CPathString@@QEAA@XZ; CPathString::~CPathString(void)
0x18005796d  mov     eax, ebx
0x18005796f  add     rsp, 78h
0x180057973  pop     r15
0x180057975  pop     r14
0x180057977  pop     rdi
0x180057978  pop     rsi
0x180057979  pop     rbx
0x18005797a  pop     rbp
0x18005797b  retn
```
