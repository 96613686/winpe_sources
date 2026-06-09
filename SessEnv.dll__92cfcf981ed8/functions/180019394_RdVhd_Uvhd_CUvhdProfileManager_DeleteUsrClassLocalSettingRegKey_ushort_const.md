# RdVhd::Uvhd::CUvhdProfileManager::DeleteUsrClassLocalSettingRegKey(ushort const *)

- ea: `0x180019394`
- end: `0x1800197ba`
- name: `?DeleteUsrClassLocalSettingRegKey@CUvhdProfileManager@Uvhd@RdVhd@@IEAAJPEBG@Z`
- size: `1062`
- prototype: `__int64 __fastcall(RdVhd::Uvhd::CUvhdProfileManager *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180045530`

## callees

- `0x180004db0`
- `0x1800141e8`
- `0x180019394`
- `0x180019b38`
- `0x180035db4`
- `0x1800486cc`
- `0x180048ab0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001961e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001961e`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x18001974a`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x18001974a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18001969e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18001969e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001972a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001972a`
- `api-ms-win-core-registry-l1-1-0!RegLoadKeyW` at `0x180019581`
- `api-ms-win-core-registry-l1-1-0!RegLoadKeyW` at `0x180019581`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180019538`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180019538`

## string_xrefs

- `0x18001943a`: `UsrClassPath.BuildPath failed for user %s`
- `0x1800194da`: `LocalSettingKeyPath.BuildPath failed for user %s`
- `0x180019644`: `RegOpenKeyEx() failed 0x%08x for user %s`
- `0x1800196c4`: `RegDeleteTree() failed 0x%08x for user %s`

## pseudocode

```c
__int64 __fastcall RdVhd::Uvhd::CUvhdProfileManager::DeleteUsrClassLocalSettingRegKey(
        RdVhd::Uvhd::CUvhdProfileManager *this,
        const unsigned __int16 *a2)
{
  int v2; // esi
  char *v3; // rbx
  unsigned int v4; // edi
  int v5; // eax
  int v6; // edx
  const unsigned __int16 *v7; // rax
  const WCHAR *v8; // rax
  const WCHAR *v9; // rax
  LPCWSTR v10; // r10
  LSTATUS KeyW; // eax
  __int64 v12; // rax
  int v13; // r8d
  int v14; // edx
  const WCHAR *v15; // rax
  LSTATUS v16; // eax
  LSTATUS v17; // eax
  const WCHAR *v18; // rax
  unsigned int v19; // r10d
  int v20; // r10d
  void **v22; // [rsp+30h] [rbp-50h] BYREF
  int v23; // [rsp+38h] [rbp-48h]
  __int64 v24; // [rsp+3Ch] [rbp-44h]
  int v25; // [rsp+44h] [rbp-3Ch]
  __int64 v26; // [rsp+48h] [rbp-38h]
  int v27; // [rsp+50h] [rbp-30h]
  void **v28; // [rsp+58h] [rbp-28h] BYREF
  int v29; // [rsp+60h] [rbp-20h]
  __int64 v30; // [rsp+64h] [rbp-1Ch]
  int v31; // [rsp+6Ch] [rbp-14h]
  __int64 v32; // [rsp+70h] [rbp-10h]
  int v33; // [rsp+78h] [rbp-8h]
  HKEY hKey; // [rsp+B0h] [rbp+30h] BYREF

  v24 = 128;
  v26 = 0;
  v25 = 0;
  v2 = 0;
  v27 = 0x8000000;
  v33 = 0x8000000;
  v23 = 0;
  v22 = &CPathString::`vftable';
  v30 = 128;
  v32 = 0;
  v31 = 0;
  v29 = 0;
  v28 = &CPathString::`vftable';
  hKey = 0;
  v3 = (char *)this + 72;
  v4 = CPathString::BuildPath((CPathString *)&v22, a2, L"\\AppData\\Local\\Microsoft\\Windows\\UsrClass.dat");
  CBaseStringT<unsigned short>::PContents(v3);
  _TraceNrmRdvVmEx(L"UVHD", v4, L"UsrClassPath.BuildPath failed for user %s");
  if ( (v4 & 0x80000000) == 0 )
  {
    v7 = (const unsigned __int16 *)CBaseStringT<unsigned short>::PContents(v3);
    v4 = CPathString::BuildPath((CPathString *)&v28, v7, L"\\Local Settings");
    CBaseStringT<unsigned short>::PContents(v3);
    _TraceNrmRdvVmEx(L"UVHD", v4, L"LocalSettingKeyPath.BuildPath failed for user %s");
    if ( (v4 & 0x80000000) == 0 )
    {
      v8 = (const WCHAR *)CBaseStringT<unsigned short>::PContents(&v22);
      if ( GetFileAttributesW(v8) == -1 )
      {
        CBaseStringT<unsigned short>::PContents(v3);
        _TraceNrmRdvVmEx(L"UVHD", v4, L"UsrClass.dat for user %s does not exist.");
        goto LABEL_42;
      }
      CBaseStringT<unsigned short>::PContents(&v22);
      v9 = (const WCHAR *)CBaseStringT<unsigned short>::PContents(v3);
      KeyW = RegLoadKeyW(HKEY_LOCAL_MACHINE, v9, v10);
      if ( KeyW )
      {
        if ( KeyW > 0 )
          v4 = (unsigned __int16)KeyW | 0x80070000;
        else
          v4 = KeyW;
        CBaseStringT<unsigned short>::PContents(v3);
        _TraceNrmRdvVmEx(L"UVHD", v4, L"RegLoadKey() failed 0x%08x for user %s");
        if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_42;
        }
        v12 = CBaseStringT<unsigned short>::PContents(v3);
        v14 = 74;
      }
      else
      {
        v2 = 1;
        v15 = (const WCHAR *)CBaseStringT<unsigned short>::PContents(v3);
        v16 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v15, 0, 0xF003Fu, &hKey);
        if ( v16 )
        {
          if ( v16 > 0 )
            v4 = (unsigned __int16)v16 | 0x80070000;
          else
            v4 = v16;
          CBaseStringT<unsigned short>::PContents(v3);
          _TraceNrmRdvVmEx(L"UVHD", v4, L"RegOpenKeyEx() failed 0x%08x for user %s");
          if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_42;
          }
          v12 = CBaseStringT<unsigned short>::PContents(v3);
          v14 = 75;
        }
        else
        {
          v17 = RegDeleteTreeW(hKey, L"Local Settings");
          if ( !v17 )
            goto LABEL_42;
          v4 = v17 > 0 ? (unsigned __int16)v17 | 0x80070000 : v17;
          CBaseStringT<unsigned short>::PContents(v3);
          _TraceNrmRdvVmEx(L"UVHD", v4, L"RegDeleteTree() failed 0x%08x for user %s");
          if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_42;
          }
          v12 = CBaseStringT<unsigned short>::PContents(v3);
          v14 = 76;
        }
      }
      WPP_SF_DSd(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, v13, v4, v12, v4);
      goto LABEL_42;
    }
    if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v5 = CBaseStringT<unsigned short>::PContents(v3);
      v6 = 73;
      goto LABEL_6;
    }
  }
  else if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v5 = CBaseStringT<unsigned short>::PContents(v3);
    v6 = 72;
LABEL_6:
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v6,
      (unsigned int)&WPP_51d6cb8edda1332360d49ca8c94b4b20_Traceguids,
      v5,
      v4);
  }
LABEL_42:
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( v2 )
  {
    v18 = (const WCHAR *)CBaseStringT<unsigned short>::PContents(v3);
    if ( RegUnLoadKeyW(HKEY_LOCAL_MACHINE, v18) )
    {
      CBaseStringT<unsigned short>::PContents(v3);
      _TraceNrmRdvVmEx(L"UVHD", v19, L"RegUnLoadKey() for user %s failed with 0x%08x.");
      if ( v20 > 0 )
        v4 = (unsigned __int16)v20 | 0x80070000;
      else
        v4 = v20;
    }
  }
  CPathString::~CPathString((CPathString *)&v28);
  CPathString::~CPathString((CPathString *)&v22);
  return v4;
}

```

## disassembly

```asm
0x180019394  mov     [rsp-28h+arg_8], rbx
0x180019399  mov     [rsp-28h+arg_10], rsi
0x18001939e  push    rbp
0x18001939f  push    rdi
0x1800193a0  push    r12
0x1800193a2  push    r13
0x1800193a4  push    r15
0x1800193a6  mov     rbp, rsp
0x1800193a9  sub     rsp, 80h
0x1800193b0  lea     rax, ??_7CPathString@@6B@; const CPathString::`vftable'
0x1800193b7  mov     [rbp+var_44], 80h
0x1800193bf  mov     rbx, rcx
0x1800193c2  mov     [rbp+var_38], 0
0x1800193ca  mov     ecx, 8000000h
0x1800193cf  mov     [rbp+var_3C], 0
0x1800193d6  xor     esi, esi
0x1800193d8  mov     [rbp+var_30], ecx
0x1800193db  mov     [rbp+var_8], ecx
0x1800193de  mov     [rbp+var_48], 0
0x1800193e5  mov     [rbp+var_50], rax
0x1800193e9  mov     [rbp+var_1C], 80h
0x1800193f1  mov     [rbp+var_10], 0
0x1800193f9  mov     [rbp+var_14], 0
0x180019400  mov     [rbp+var_20], 0
0x180019407  mov     [rbp+var_28], rax
0x18001940b  mov     [rbp+hKey], rsi
0x18001940f  lea     r8, aAppdataLocalMi; "\\AppData\\Local\\Microsoft\\Windows\\U"...
0x180019416  lea     rcx, [rbp+var_50]; this
0x18001941a  call    ?BuildPath@CPathString@@QEAAJPEBG0@Z; CPathString::BuildPath(ushort const *,ushort const *)
0x18001941f  add     rbx, 48h ; 'H'
0x180019423  mov     edi, eax
0x180019425  mov     rcx, rbx
0x180019428  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x18001942d  lea     r15, aUvhd; "UVHD"
0x180019434  mov     r9, rax
0x180019437  mov     rcx, r15; unsigned __int16 *
0x18001943a  lea     r8, aUsrclasspathBu; "UsrClassPath.BuildPath failed for user "...
0x180019441  mov     edx, edi; int
0x180019443  call    ?_TraceNrmRdvVmEx@@YAXPEBGJ0ZZ; _TraceNrmRdvVmEx(ushort const *,long,ushort const *,...)
0x180019448  mov     r13, 0FFFFFFFF80000002h
0x18001944f  mov     r12d, 80070000h
0x180019455  test    edi, edi
0x180019457  jns     short loc_1800194B2
0x180019459  mov     rcx, cs:WPP_GLOBAL_Control
0x180019460  lea     rax, WPP_GLOBAL_Control
0x180019467  cmp     rcx, rax
0x18001946a  jz      loc_180019721
0x180019470  test    byte ptr [rcx+1Ch], 4
0x180019474  jz      loc_180019721
0x18001947a  cmp     byte ptr [rcx+19h], 2
0x18001947e  jb      loc_180019721
0x180019484  mov     rcx, rbx
0x180019487  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x18001948c  lea     edx, [rsi+48h]
0x18001948f  mov     rcx, cs:WPP_GLOBAL_Control
0x180019496  lea     r8, WPP_51d6cb8edda1332360d49ca8c94b4b20_Traceguids
0x18001949d  mov     r9, rax
0x1800194a0  mov     dword ptr [rsp+80h+phkResult], edi
0x1800194a4  mov     rcx, [rcx+10h]
0x1800194a8  call    WPP_SF_Sd
0x1800194ad  jmp     loc_180019721
0x1800194b2  mov     rcx, rbx
0x1800194b5  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x1800194ba  mov     rdx, rax; unsigned __int16 *
0x1800194bd  lea     r8, aLocalSettings; "\\Local Settings"
0x1800194c4  lea     rcx, [rbp+var_28]; this
0x1800194c8  call    ?BuildPath@CPathString@@QEAAJPEBG0@Z; CPathString::BuildPath(ushort const *,ushort const *)
0x1800194cd  mov     rcx, rbx
0x1800194d0  mov     edi, eax
0x1800194d2  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x1800194d7  mov     r9, rax
0x1800194da  lea     r8, aLocalsettingke; "LocalSettingKeyPath.BuildPath failed fo"...
0x1800194e1  mov     edx, edi; int
0x1800194e3  mov     rcx, r15; unsigned __int16 *
0x1800194e6  call    ?_TraceNrmRdvVmEx@@YAXPEBGJ0ZZ; _TraceNrmRdvVmEx(ushort const *,long,ushort const *,...)
0x1800194eb  test    edi, edi
0x1800194ed  jns     short loc_18001952C
0x1800194ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800194f6  lea     rax, WPP_GLOBAL_Control
0x1800194fd  cmp     rcx, rax
0x180019500  jz      loc_180019721
0x180019506  test    byte ptr [rcx+1Ch], 4
0x18001950a  jz      loc_180019721
0x180019510  cmp     byte ptr [rcx+19h], 2
0x180019514  jb      loc_180019721
0x18001951a  mov     rcx, rbx
0x18001951d  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x180019522  mov     edx, 49h ; 'I'
0x180019527  jmp     loc_18001948F
0x18001952c  lea     rcx, [rbp+var_50]
0x180019530  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x180019535  mov     rcx, rax; lpFileName
0x180019538  call    cs:__imp_GetFileAttributesW
0x18001953e  cmp     eax, 0FFFFFFFFh
0x180019541  jnz     short loc_180019564
0x180019543  mov     rcx, rbx
0x180019546  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x18001954b  mov     r9, rax
0x18001954e  lea     r8, aUsrclassDatFor; "UsrClass.dat for user %s does not exist"...
0x180019555  mov     edx, edi; int
0x180019557  mov     rcx, r15; unsigned __int16 *
0x18001955a  call    ?_TraceNrmRdvVmEx@@YAXPEBGJ0ZZ; _TraceNrmRdvVmEx(ushort const *,long,ushort const *,...)
0x18001955f  jmp     loc_180019721
0x180019564  lea     rcx, [rbp+var_50]
0x180019568  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x18001956d  mov     rcx, rbx
0x180019570  mov     r10, rax
0x180019573  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x180019578  mov     r8, r10; lpFile
0x18001957b  mov     rdx, rax; lpSubKey
0x18001957e  mov     rcx, r13; hKey
0x180019581  call    cs:__imp_RegLoadKeyW
0x180019587  test    eax, eax
0x180019589  jz      short loc_1800195F9
0x18001958b  jg      short loc_180019591
0x18001958d  mov     edi, eax
0x18001958f  jmp     short loc_180019597
0x180019591  movzx   edi, ax
0x180019594  or      edi, r12d
0x180019597  mov     rcx, rbx
0x18001959a  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x18001959f  mov     r9d, edi
0x1800195a2  mov     [rsp+80h+phkResult], rax
0x1800195a7  lea     r8, aRegloadkeyFail; "RegLoadKey() failed 0x%08x for user %s"
0x1800195ae  mov     edx, edi; int
0x1800195b0  mov     rcx, r15; unsigned __int16 *
0x1800195b3  call    ?_TraceNrmRdvVmEx@@YAXPEBGJ0ZZ; _TraceNrmRdvVmEx(ushort const *,long,ushort const *,...)
0x1800195b8  test    edi, edi
0x1800195ba  jns     short loc_1800195F9
0x1800195bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800195c3  lea     rax, WPP_GLOBAL_Control
0x1800195ca  cmp     rcx, rax
0x1800195cd  jz      loc_180019721
0x1800195d3  test    byte ptr [rcx+1Ch], 4
0x1800195d7  jz      loc_180019721
0x1800195dd  cmp     byte ptr [rcx+19h], 2
0x1800195e1  jb      loc_180019721
0x1800195e7  mov     rcx, rbx
0x1800195ea  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x1800195ef  mov     edx, 4Ah ; 'J'
0x1800195f4  jmp     loc_180019705
0x1800195f9  mov     rcx, rbx
0x1800195fc  mov     esi, 1
0x180019601  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x180019606  mov     rdx, rax; lpSubKey
0x180019609  mov     r9d, 0F003Fh; samDesired
0x18001960f  lea     rax, [rbp+hKey]
0x180019613  xor     r8d, r8d; ulOptions
0x180019616  mov     rcx, r13; hKey
0x180019619  mov     [rsp+80h+phkResult], rax; phkResult
0x18001961e  call    cs:__imp_RegOpenKeyExW
0x180019624  test    eax, eax
0x180019626  jz      short loc_180019693
0x180019628  jg      short loc_18001962E
0x18001962a  mov     edi, eax
0x18001962c  jmp     short loc_180019634
0x18001962e  movzx   edi, ax
0x180019631  or      edi, r12d
0x180019634  mov     rcx, rbx
0x180019637  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x18001963c  mov     r9d, edi
0x18001963f  mov     [rsp+80h+phkResult], rax
0x180019644  lea     r8, aRegopenkeyexFa_4; "RegOpenKeyEx() failed 0x%08x for user %"...
0x18001964b  mov     edx, edi; int
0x18001964d  mov     rcx, r15; unsigned __int16 *
0x180019650  call    ?_TraceNrmRdvVmEx@@YAXPEBGJ0ZZ; _TraceNrmRdvVmEx(ushort const *,long,ushort const *,...)
0x180019655  test    edi, edi
0x180019657  jns     short loc_180019693
0x180019659  mov     rcx, cs:WPP_GLOBAL_Control
0x180019660  lea     rax, WPP_GLOBAL_Control
0x180019667  cmp     rcx, rax
0x18001966a  jz      loc_180019721
0x180019670  test    byte ptr [rcx+1Ch], 4
0x180019674  jz      loc_180019721
0x18001967a  cmp     byte ptr [rcx+19h], 2
0x18001967e  jb      loc_180019721
0x180019684  mov     rcx, rbx
0x180019687  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x18001968c  mov     edx, 4Bh ; 'K'
0x180019691  jmp     short loc_180019705
0x180019693  mov     rcx, [rbp+hKey]; hKey
0x180019697  lea     rdx, aLocalSettings_0; "Local Settings"
0x18001969e  call    cs:__imp_RegDeleteTreeW
0x1800196a4  test    eax, eax
0x1800196a6  jz      short loc_180019721
0x1800196a8  jg      short loc_1800196AE
0x1800196aa  mov     edi, eax
0x1800196ac  jmp     short loc_1800196B4
0x1800196ae  movzx   edi, ax
0x1800196b1  or      edi, r12d
0x1800196b4  mov     rcx, rbx
0x1800196b7  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x1800196bc  mov     r9d, edi
0x1800196bf  mov     [rsp+80h+phkResult], rax
0x1800196c4  lea     r8, aRegdeletetreeF; "RegDeleteTree() failed 0x%08x for user "...
0x1800196cb  mov     edx, edi; int
0x1800196cd  mov     rcx, r15; unsigned __int16 *
0x1800196d0  call    ?_TraceNrmRdvVmEx@@YAXPEBGJ0ZZ; _TraceNrmRdvVmEx(ushort const *,long,ushort const *,...)
0x1800196d5  test    edi, edi
0x1800196d7  jns     short loc_180019721
0x1800196d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800196e0  lea     rax, WPP_GLOBAL_Control
0x1800196e7  cmp     rcx, rax
0x1800196ea  jz      short loc_180019721
0x1800196ec  test    byte ptr [rcx+1Ch], 4
0x1800196f0  jz      short loc_180019721
0x1800196f2  cmp     byte ptr [rcx+19h], 2
0x1800196f6  jb      short loc_180019721
0x1800196f8  mov     rcx, rbx
0x1800196fb  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x180019700  mov     edx, 4Ch ; 'L'
0x180019705  mov     rcx, cs:WPP_GLOBAL_Control
0x18001970c  mov     r9d, edi
0x18001970f  mov     [rsp+80h+var_58], edi
0x180019713  mov     [rsp+80h+phkResult], rax
0x180019718  mov     rcx, [rcx+10h]
0x18001971c  call    WPP_SF_DSd
0x180019721  mov     rcx, [rbp+hKey]; hKey
0x180019725  test    rcx, rcx
0x180019728  jz      short loc_180019738
0x18001972a  call    cs:__imp_RegCloseKey
0x180019730  mov     [rbp+hKey], 0
0x180019738  test    esi, esi
0x18001973a  jz      short loc_18001978A
0x18001973c  mov     rcx, rbx
0x18001973f  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x180019744  mov     rdx, rax; lpSubKey
0x180019747  mov     rcx, r13; hKey
0x18001974a  call    cs:__imp_RegUnLoadKeyW
0x180019750  mov     r10d, eax
0x180019753  test    eax, eax
0x180019755  jz      short loc_18001978A
0x180019757  mov     rcx, rbx
0x18001975a  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x18001975f  mov     r9, rax
0x180019762  mov     dword ptr [rsp+80h+phkResult], r10d
0x180019767  lea     r8, aRegunloadkeyFo; "RegUnLoadKey() for user %s failed with "...
0x18001976e  mov     edx, r10d; int
0x180019771  mov     rcx, r15; unsigned __int16 *
0x180019774  call    ?_TraceNrmRdvVmEx@@YAXPEBGJ0ZZ; _TraceNrmRdvVmEx(ushort const *,long,ushort const *,...)
0x180019779  test    r10d, r10d
0x18001977c  jg      short loc_180019783
0x18001977e  mov     edi, r10d
0x180019781  jmp     short loc_18001978A
0x180019783  movzx   edi, r10w
0x180019787  or      edi, r12d
0x18001978a  lea     rcx, [rbp+var_28]; this
0x18001978e  call    ??1CPathString@@QEAA@XZ; CPathString::~CPathString(void)
0x180019793  lea     rcx, [rbp+var_50]; this
0x180019797  call    ??1CPathString@@QEAA@XZ; CPathString::~CPathString(void)
0x18001979c  lea     r11, [rsp+80h+var_s0]
0x1800197a4  mov     eax, edi
0x1800197a6  mov     rbx, [r11+38h]
0x1800197aa  mov     rsi, [r11+40h]
0x1800197ae  mov     rsp, r11
0x1800197b1  pop     r15
0x1800197b3  pop     r13
0x1800197b5  pop     r12
0x1800197b7  pop     rdi
0x1800197b8  pop     rbp
0x1800197b9  retn
```
