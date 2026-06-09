# StartList::SaveSessionKey(void)

- ea: `0x14000f9c0`
- end: `0x14000fd00`
- name: `?SaveSessionKey@StartList@@AEAAXXZ`
- size: `832`
- prototype: `void __fastcall(StartList *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140010244`

## callees

- `0x140004890`
- `0x14000abd8`
- `0x14000be54`
- `0x14000c220`
- `0x14000c2bc`
- `0x14000d334`
- `0x14000f9c0`
- `0x140011080`
- `0x1400111c0`
- `0x140015830`
- `0x140017010`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x14000fa32`
- `ADVAPI32!RegOpenKeyExW` at `0x14000fa32`
- `ADVAPI32!RegCloseKey` at `0x14000fccc`
- `ADVAPI32!RegCloseKey` at `0x14000fccc`
- `KERNEL32!RegSetValueExW` at `0x14000fbc9`
- `KERNEL32!RegSetValueExW` at `0x14000fc47`
- `KERNEL32!RegSetValueExW` at `0x14000fbc9`
- `KERNEL32!RegSetValueExW` at `0x14000fc47`

## string_xrefs

- `0x14000fbbf`: `SecureConfiguration`
- `0x14000fc3d`: `Configuration`

## pseudocode

```c
void __fastcall StartList::SaveSessionKey(StartList *this)
{
  char v2; // di
  HKEY v3; // rbx
  LPCWSTR *v4; // rax
  LSTATUS v5; // esi
  _QWORD *v6; // rdx
  const unsigned __int16 **v7; // rax
  unsigned __int16 *v8; // r9
  int v9; // ebx
  _QWORD *v10; // rdx
  _QWORD *v11; // rax
  int v12; // r8d
  HKEY v13; // rdx
  HKEY v14; // rcx
  __int64 v15; // rax
  unsigned int v16; // eax
  __int64 v17; // r8
  HKEY v18; // rdi
  __int64 v19; // rax
  unsigned int v20; // eax
  __int64 v21; // r8
  struct _SECURITY_ATTRIBUTES *v22; // [rsp+30h] [rbp-40h]
  _BYTE v23[16]; // [rsp+40h] [rbp-30h] BYREF
  _QWORD v24[4]; // [rsp+50h] [rbp-20h] BYREF
  HKEY hKey; // [rsp+A8h] [rbp+38h] BYREF
  __int64 v26; // [rsp+B0h] [rbp+40h] BYREF

  v2 = 0;
  LODWORD(hKey) = 0;
  _Trace::_Trace((_Trace *)v23, L"StartList::SaveSessionKey", 0);
  v3 = 0;
  memset(v24, 0, 24);
  v4 = (LPCWSTR *)CATUtils::SessionKeyString((__int64)&v26);
  hKey = 0;
  v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, *v4, 0, 0x20006u, &hKey);
  if ( !v5 )
    v3 = hKey;
  v24[0] = v3;
  v6 = (_QWORD *)(v26 - 24);
  if ( _InterlockedDecrement((volatile signed __int32 *)(v26 - 24 + 16)) <= 0 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v6 + 8LL))(*v6);
  if ( v5 )
  {
    v7 = (const unsigned __int16 **)CATUtils::SessionKeyString((__int64)&v26);
    v9 = ATL::CRegKey::Create((ATL::CRegKey *)v24, HKEY_LOCAL_MACHINE, *v7, v8, 1u, 3u, v22, (unsigned int *)&hKey);
    v10 = (_QWORD *)(v26 - 24);
    if ( _InterlockedDecrement((volatile signed __int32 *)(v26 - 24 + 16)) <= 0 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v10 + 8LL))(*v10);
    if ( v9 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        v11 = (_QWORD *)CATUtils::SessionKeyString((__int64)&hKey);
        v2 = 1;
        WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, v12, *v11, v9);
      }
      if ( (v2 & 1) != 0 )
      {
        v13 = hKey - 6;
        if ( _InterlockedDecrement((volatile signed __int32 *)hKey - 2) <= 0 )
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v13 + 8LL))(*(_QWORD *)v13);
      }
      v14 = (HKEY)v24[0];
      if ( v24[0] )
        goto LABEL_39;
      goto LABEL_40;
    }
    v3 = (HKEY)v24[0];
  }
  hKey = (HKEY)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  StartList::BuildConfigString(&hKey, (char *)this + 96);
  if ( !hKey )
    goto LABEL_41;
  v15 = -1;
  do
    ++v15;
  while ( *((_WORD *)hKey + v15) );
  v16 = RegSetValueExW(v3, L"SecureConfiguration", 0, 1u, (const BYTE *)hKey, 2 * v15 + 2);
  if ( v16 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v17, v16);
  StartList::BuildConfigString(&hKey, (char *)this + 48);
  v18 = hKey;
  if ( !hKey )
LABEL_41:
    ATL::AtlThrowImpl(-2147467259);
  v19 = -1;
  do
    ++v19;
  while ( *((_WORD *)hKey + v19) );
  v20 = RegSetValueExW(v3, StartList::_configuration, 0, 1u, (const BYTE *)hKey, 2 * v19 + 2);
  if ( v20 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, v21, v20);
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_0cfc691c390c3581aa6c7b8081e34e7b_Traceguids, v18);
  }
  if ( _InterlockedDecrement((volatile signed __int32 *)v18 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v18 - 3) + 8LL))(*((_QWORD *)v18 - 3));
  if ( v3 )
  {
    v14 = v3;
LABEL_39:
    RegCloseKey(v14);
  }
LABEL_40:
  _Trace::~_Trace((_Trace *)v23);
}

```

## disassembly

```asm
0x14000f9c0  mov     [rsp-28h+arg_0], rbx
0x14000f9c5  mov     [rsp-28h+arg_18], rsi
0x14000f9ca  push    rbp
0x14000f9cb  push    rdi
0x14000f9cc  push    r12
0x14000f9ce  push    r14
0x14000f9d0  push    r15
0x14000f9d2  mov     rbp, rsp
0x14000f9d5  sub     rsp, 70h
0x14000f9d9  mov     r14, rcx
0x14000f9dc  xor     r15d, r15d
0x14000f9df  mov     edi, r15d
0x14000f9e2  mov     dword ptr [rbp+hKey], r15d
0x14000f9e6  xor     r8d, r8d; int *
0x14000f9e9  lea     rdx, aStartlistSaves; "StartList::SaveSessionKey"
0x14000f9f0  lea     rcx, [rbp+var_30]; this
0x14000f9f4  call    ??0_Trace@@QEAA@PEBGPEAJ@Z; _Trace::_Trace(ushort const *,long *)
0x14000f9f9  nop
0x14000f9fa  mov     ebx, r15d
0x14000f9fd  mov     [rbp+var_20], rbx
0x14000fa01  mov     [rbp+var_18], r15
0x14000fa05  mov     [rbp+var_10], r15
0x14000fa09  lea     rcx, [rbp+arg_10]
0x14000fa0d  call    ?SessionKeyString@CATUtils@@SA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@XZ; CATUtils::SessionKeyString(void)
0x14000fa12  mov     [rbp+hKey], r15
0x14000fa16  lea     rcx, [rbp+hKey]
0x14000fa1a  mov     [rsp+70h+phkResult], rcx; phkResult
0x14000fa1f  mov     r9d, 20006h; samDesired
0x14000fa25  xor     r8d, r8d; ulOptions
0x14000fa28  mov     rdx, [rax]; lpSubKey
0x14000fa2b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14000fa32  call    cs:__imp_RegOpenKeyExW
0x14000fa38  mov     esi, eax
0x14000fa3a  test    eax, eax
0x14000fa3c  cmovz   rbx, [rbp+hKey]
0x14000fa41  mov     [rbp+var_20], rbx
0x14000fa45  mov     rdx, [rbp+arg_10]
0x14000fa49  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14000fa4d  or      r12, 0FFFFFFFFFFFFFFFFh
0x14000fa51  mov     ecx, r12d
0x14000fa54  lock xadd [rdx+10h], ecx
0x14000fa59  add     ecx, r12d
0x14000fa5c  test    ecx, ecx
0x14000fa5e  jg      short loc_14000FA6F
0x14000fa60  mov     rcx, [rdx]
0x14000fa63  mov     rax, [rcx]
0x14000fa66  mov     rax, [rax+8]
0x14000fa6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fa6f  test    esi, esi
0x14000fa71  jz      loc_14000FB60
0x14000fa77  lea     rcx, [rbp+arg_10]
0x14000fa7b  call    ?SessionKeyString@CATUtils@@SA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@XZ; CATUtils::SessionKeyString(void)
0x14000fa80  lea     rcx, [rbp+hKey]
0x14000fa84  mov     [rsp+70h+var_38], rcx; unsigned int *
0x14000fa89  mov     [rsp+70h+cbData], 3; unsigned int
0x14000fa91  mov     dword ptr [rsp+70h+phkResult], 1; unsigned int
0x14000fa99  mov     r8, [rax]; unsigned __int16 *
0x14000fa9c  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x14000faa3  lea     rcx, [rbp+var_20]; this
0x14000faa7  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x14000faac  mov     ebx, eax
0x14000faae  mov     rdx, [rbp+arg_10]
0x14000fab2  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14000fab6  mov     ecx, r12d
0x14000fab9  lock xadd [rdx+10h], ecx
0x14000fabe  add     ecx, r12d
0x14000fac1  test    ecx, ecx
0x14000fac3  jg      short loc_14000FAD4
0x14000fac5  mov     rcx, [rdx]
0x14000fac8  mov     r8, [rcx]
0x14000facb  mov     rax, [r8+8]
0x14000facf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fad4  test    ebx, ebx
0x14000fad6  jz      loc_14000FB5C
0x14000fadc  lea     rsi, WPP_GLOBAL_Control
0x14000fae3  mov     rax, cs:WPP_GLOBAL_Control
0x14000faea  cmp     rax, rsi
0x14000faed  jz      short loc_14000FB1D
0x14000faef  test    byte ptr [rax+1Ch], 8
0x14000faf3  jz      short loc_14000FB1D
0x14000faf5  lea     rcx, [rbp+hKey]
0x14000faf9  call    ?SessionKeyString@CATUtils@@SA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@XZ; CATUtils::SessionKeyString(void)
0x14000fafe  mov     edi, 1
0x14000fb03  lea     edx, [rdi+18h]
0x14000fb06  mov     dword ptr [rsp+70h+phkResult], ebx
0x14000fb0a  mov     r9, [rax]
0x14000fb0d  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fb14  mov     rcx, [rcx+10h]
0x14000fb18  call    WPP_SF_Sd
0x14000fb1d  test    dil, 1
0x14000fb21  jz      short loc_14000FB4A
0x14000fb23  mov     rdx, [rbp+hKey]
0x14000fb27  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14000fb2b  mov     eax, r12d
0x14000fb2e  lock xadd [rdx+10h], eax
0x14000fb33  add     eax, r12d
0x14000fb36  test    eax, eax
0x14000fb38  jg      short loc_14000FB4A
0x14000fb3a  mov     rcx, [rdx]
0x14000fb3d  mov     rax, [rcx]
0x14000fb40  mov     rax, [rax+8]
0x14000fb44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fb49  nop
0x14000fb4a  mov     rcx, [rbp+var_20]
0x14000fb4e  test    rcx, rcx
0x14000fb51  jz      loc_14000FCD3
0x14000fb57  jmp     loc_14000FCCC
0x14000fb5c  mov     rbx, [rbp+var_20]
0x14000fb60  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000fb67  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000fb6e  mov     rax, [rax+18h]
0x14000fb72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fb77  add     rax, 18h
0x14000fb7b  mov     [rbp+hKey], rax
0x14000fb7f  lea     rdx, [r14+60h]
0x14000fb83  lea     rcx, [rbp+hKey]
0x14000fb87  call    ?BuildConfigString@StartList@@SAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEBV?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@3@@Z; StartList::BuildConfigString(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> const &)
0x14000fb8c  mov     rcx, [rbp+hKey]
0x14000fb90  test    rcx, rcx
0x14000fb93  jz      loc_14000FCF5
0x14000fb99  mov     rax, r12
0x14000fb9c  inc     rax
0x14000fb9f  cmp     [rcx+rax*2], r15w
0x14000fba4  jnz     short loc_14000FB9C
0x14000fba6  lea     eax, ds:2[rax*2]
0x14000fbad  mov     [rsp+70h+cbData], eax; cbData
0x14000fbb1  mov     [rsp+70h+phkResult], rcx; lpData
0x14000fbb6  mov     r9d, 1; dwType
0x14000fbbc  xor     r8d, r8d; Reserved
0x14000fbbf  lea     rdx, ?c_secureConfiguration@StartList@@0QBGB; "SecureConfiguration"
0x14000fbc6  mov     rcx, rbx; hKey
0x14000fbc9  call    cs:__imp_RegSetValueExW
0x14000fbcf  lea     rsi, WPP_GLOBAL_Control
0x14000fbd6  test    eax, eax
0x14000fbd8  jz      short loc_14000FBFD
0x14000fbda  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fbe1  cmp     rcx, rsi
0x14000fbe4  jz      short loc_14000FBFD
0x14000fbe6  test    byte ptr [rcx+1Ch], 8
0x14000fbea  jz      short loc_14000FBFD
0x14000fbec  mov     edx, 1Ah
0x14000fbf1  mov     r9d, eax
0x14000fbf4  mov     rcx, [rcx+10h]
0x14000fbf8  call    WPP_SF_d
0x14000fbfd  lea     rdx, [r14+30h]
0x14000fc01  lea     rcx, [rbp+hKey]
0x14000fc05  call    ?BuildConfigString@StartList@@SAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEBV?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@3@@Z; StartList::BuildConfigString(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> const &)
0x14000fc0a  mov     rdi, [rbp+hKey]
0x14000fc0e  test    rdi, rdi
0x14000fc11  jz      loc_14000FCF5
0x14000fc17  mov     rax, r12
0x14000fc1a  inc     rax
0x14000fc1d  cmp     [rdi+rax*2], r15w
0x14000fc22  jnz     short loc_14000FC1A
0x14000fc24  lea     eax, ds:2[rax*2]
0x14000fc2b  mov     [rsp+70h+cbData], eax; cbData
0x14000fc2f  mov     [rsp+70h+phkResult], rdi; lpData
0x14000fc34  mov     r9d, 1; dwType
0x14000fc3a  xor     r8d, r8d; Reserved
0x14000fc3d  lea     rdx, ?_configuration@StartList@@0PAGA; "Configuration"
0x14000fc44  mov     rcx, rbx; hKey
0x14000fc47  call    cs:__imp_RegSetValueExW
0x14000fc4d  test    eax, eax
0x14000fc4f  jz      short loc_14000FC76
0x14000fc51  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fc58  cmp     rcx, rsi
0x14000fc5b  jz      short loc_14000FCA1
0x14000fc5d  test    byte ptr [rcx+1Ch], 8
0x14000fc61  jz      short loc_14000FCA1
0x14000fc63  mov     edx, 1Bh
0x14000fc68  mov     r9d, eax
0x14000fc6b  mov     rcx, [rcx+10h]
0x14000fc6f  call    WPP_SF_d
0x14000fc74  jmp     short loc_14000FCA1
0x14000fc76  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fc7d  cmp     rcx, rsi
0x14000fc80  jz      short loc_14000FCA1
0x14000fc82  test    byte ptr [rcx+1Ch], 10h
0x14000fc86  jz      short loc_14000FCA1
0x14000fc88  mov     edx, 1Ch
0x14000fc8d  mov     r9, rdi
0x14000fc90  lea     r8, WPP_0cfc691c390c3581aa6c7b8081e34e7b_Traceguids
0x14000fc97  mov     rcx, [rcx+10h]
0x14000fc9b  call    WPP_SF_S
0x14000fca0  nop
0x14000fca1  lea     rdx, [rdi-18h]
0x14000fca5  mov     eax, r12d
0x14000fca8  lock xadd [rdx+10h], eax
0x14000fcad  add     eax, r12d
0x14000fcb0  test    eax, eax
0x14000fcb2  jg      short loc_14000FCC4
0x14000fcb4  mov     rcx, [rdx]
0x14000fcb7  mov     rax, [rcx]
0x14000fcba  mov     rax, [rax+8]
0x14000fcbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fcc3  nop
0x14000fcc4  test    rbx, rbx
0x14000fcc7  jz      short loc_14000FCD3
0x14000fcc9  mov     rcx, rbx; hKey
0x14000fccc  call    cs:__imp_RegCloseKey
0x14000fcd2  nop
0x14000fcd3  lea     rcx, [rbp+var_30]; this
0x14000fcd7  call    ??1_Trace@@QEAA@XZ; _Trace::~_Trace(void)
0x14000fcdc  lea     r11, [rsp+70h+var_s0]
0x14000fce1  mov     rbx, [r11+30h]
0x14000fce5  mov     rsi, [r11+48h]
0x14000fce9  mov     rsp, r11
0x14000fcec  pop     r15
0x14000fcee  pop     r14
0x14000fcf0  pop     r12
0x14000fcf2  pop     rdi
0x14000fcf3  pop     rbp
0x14000fcf4  retn
0x14000fcf5  mov     ecx, 80004005h; int
0x14000fcfa  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
