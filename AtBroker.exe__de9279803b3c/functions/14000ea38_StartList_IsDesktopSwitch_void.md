# StartList::IsDesktopSwitch(void)

- ea: `0x14000ea38`
- end: `0x14000ec9e`
- name: `?IsDesktopSwitch@StartList@@AEAAHXZ`
- size: `614`
- prototype: `__int64 __fastcall(const WCHAR *this)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140010714`

## callees

- `0x140003ea0`
- `0x140004890`
- `0x140006c00`
- `0x14000be54`
- `0x14000c220`
- `0x14000c2bc`
- `0x14000ce48`
- `0x14000d118`
- `0x14000ea38`
- `0x140011080`
- `0x140015830`
- `0x140017010`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x14000ebca`
- `ADVAPI32!RegOpenKeyExW` at `0x14000ebca`
- `ADVAPI32!RegCloseKey` at `0x14000ec6d`
- `ADVAPI32!RegCloseKey` at `0x14000ec6d`

## pseudocode

```c
__int64 __fastcall StartList::IsDesktopSwitch(const WCHAR *this)
{
  __int64 *v1; // rax
  HKEY v2; // rdx
  __int64 v3; // rcx
  __int64 v4; // rcx
  HKEY v5; // rbx
  __int64 v6; // r8
  const unsigned __int16 *v7; // rbx
  int v8; // r8d
  unsigned __int16 *v9; // r9
  HKEY v10; // rdi
  unsigned int v11; // esi
  int v12; // eax
  const unsigned __int16 *v13; // rdx
  struct _SECURITY_ATTRIBUTES *v15; // [rsp+30h] [rbp-40h]
  _BYTE v16[16]; // [rsp+40h] [rbp-30h] BYREF
  HKEY v17[4]; // [rsp+50h] [rbp-20h] BYREF
  LPCWSTR lpSubKey; // [rsp+A0h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+A8h] [rbp+38h] BYREF

  lpSubKey = this;
  _Trace::_Trace((_Trace *)v16, L"StartList::IsDesktopSwitch", 0);
  memset(v17, 0, 24);
  lpSubKey = (LPCWSTR)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  v1 = (__int64 *)CATUtils::SessionKeyString(&hKey);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
    (__int64 *)&lpSubKey,
    v1);
  v2 = hKey - 6;
  if ( _InterlockedDecrement((volatile signed __int32 *)hKey - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v2 + 8LL))(*(_QWORD *)v2);
  v3 = *((_QWORD *)lpSubKey - 3);
  if ( !v3 || (v4 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 32LL))(v3)) == 0 )
  {
    v4 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[4])(&ATL::g_strmgr);
    if ( !v4 )
      ATL::AtlThrowImpl(-2147467259);
  }
  hKey = (HKEY)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 24LL))(v4) + 24);
  if ( (unsigned __int64)"\\" >= 0x10000 )
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
      (LPWSTR *)&hKey,
      "\\");
  else
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::LoadStringW(
      &hKey,
      (unsigned __int16)"\\");
  v5 = hKey;
  ATL::CSimpleStringT<unsigned short,0>::Append((__int64 *)&lpSubKey, hKey, *((_DWORD *)hKey - 4));
  if ( _InterlockedDecrement((volatile signed __int32 *)v5 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v5 - 3) + 8LL))(*((_QWORD *)v5 - 3));
  v6 = -1;
  do
    ++v6;
  while ( *((_WORD *)&StartList::_switchApps + v6) );
  ATL::CSimpleStringT<unsigned short,0>::Append((__int64 *)&lpSubKey, &StartList::_switchApps, v6);
  hKey = 0;
  v7 = lpSubKey;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20006u, &hKey) )
  {
    v12 = ATL::CRegKey::Create(v17, HKEY_LOCAL_MACHINE, v7, v9, 1u, 3u, v15, (unsigned int *)&lpSubKey);
    if ( v12 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, v8, (_DWORD)v7, v12);
    v11 = 0;
    v10 = v17[0];
  }
  else
  {
    v10 = hKey;
    v17[0] = hKey;
    v11 = 1;
  }
  v13 = v7 - 12;
  if ( _InterlockedDecrement((volatile signed __int32 *)v7 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v13 + 8LL))(*(_QWORD *)v13);
  if ( v10 )
    RegCloseKey(v10);
  _Trace::~_Trace((_Trace *)v16, (__int64)v13, v8);
  return v11;
}

```

## disassembly

```asm
0x14000ea38  mov     [rsp-28h+arg_10], rbx
0x14000ea3d  mov     [rsp-28h+lpSubKey], rcx
0x14000ea42  push    rbp
0x14000ea43  push    rsi
0x14000ea44  push    rdi
0x14000ea45  push    r14
0x14000ea47  push    r15
0x14000ea49  mov     rbp, rsp
0x14000ea4c  sub     rsp, 70h
0x14000ea50  xor     r8d, r8d; int *
0x14000ea53  lea     rdx, aStartlistIsdes; "StartList::IsDesktopSwitch"
0x14000ea5a  lea     rcx, [rbp+var_30]; this
0x14000ea5e  call    ??0_Trace@@QEAA@PEBGPEAJ@Z; _Trace::_Trace(ushort const *,long *)
0x14000ea63  nop
0x14000ea64  xor     r14d, r14d
0x14000ea67  mov     [rbp+var_20], r14
0x14000ea6b  mov     [rbp+var_18], r14
0x14000ea6f  mov     [rbp+var_10], r14
0x14000ea73  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000ea7a  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000ea81  mov     rax, [rax+18h]
0x14000ea85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ea8a  add     rax, 18h
0x14000ea8e  mov     [rbp+lpSubKey], rax
0x14000ea92  lea     rcx, [rbp+hKey]
0x14000ea96  call    ?SessionKeyString@CATUtils@@SA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@XZ; CATUtils::SessionKeyString(void)
0x14000ea9b  nop
0x14000ea9c  mov     rdx, rax
0x14000ea9f  lea     rcx, [rbp+lpSubKey]
0x14000eaa3  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14000eaa8  nop
0x14000eaa9  mov     rdx, [rbp+hKey]
0x14000eaad  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14000eab1  or      r15, 0FFFFFFFFFFFFFFFFh
0x14000eab5  mov     eax, r15d
0x14000eab8  lock xadd [rdx+10h], eax
0x14000eabd  add     eax, r15d
0x14000eac0  test    eax, eax
0x14000eac2  jg      short loc_14000EAD3
0x14000eac4  mov     rcx, [rdx]
0x14000eac7  mov     rax, [rcx]
0x14000eaca  mov     rax, [rax+8]
0x14000eace  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ead3  mov     rax, [rbp+lpSubKey]
0x14000ead7  mov     rcx, [rax-18h]
0x14000eadb  test    rcx, rcx
0x14000eade  jz      short loc_14000EAF4
0x14000eae0  mov     rax, [rcx]
0x14000eae3  mov     rax, [rax+20h]
0x14000eae7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000eaec  mov     rcx, rax
0x14000eaef  test    rax, rax
0x14000eaf2  jnz     short loc_14000EB17
0x14000eaf4  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000eafb  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000eb02  mov     rax, [rax+20h]
0x14000eb06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000eb0b  mov     rcx, rax
0x14000eb0e  test    rax, rax
0x14000eb11  jz      loc_14000EC93
0x14000eb17  mov     rax, [rcx]
0x14000eb1a  mov     rax, [rax+18h]
0x14000eb1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000eb23  add     rax, 18h
0x14000eb27  mov     [rbp+hKey], rax
0x14000eb2b  lea     rdx, asc_140019A98; "\\"
0x14000eb32  lea     rcx, [rbp+hKey]
0x14000eb36  cmp     rdx, 10000h
0x14000eb3d  jnb     short loc_14000EB49
0x14000eb3f  movzx   edx, dx
0x14000eb42  call    ?LoadStringW@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHI@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::LoadStringW(uint)
0x14000eb47  jmp     short loc_14000EB4F
0x14000eb49  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(char const *)
0x14000eb4e  nop
0x14000eb4f  mov     rbx, [rbp+hKey]
0x14000eb53  mov     r8d, [rbx-10h]
0x14000eb57  mov     rdx, rbx
0x14000eb5a  lea     rcx, [rbp+lpSubKey]
0x14000eb5e  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x14000eb63  nop
0x14000eb64  lea     rdx, [rbx-18h]
0x14000eb68  mov     eax, r15d
0x14000eb6b  lock xadd [rdx+10h], eax
0x14000eb70  add     eax, r15d
0x14000eb73  test    eax, eax
0x14000eb75  jg      short loc_14000EB86
0x14000eb77  mov     rcx, [rdx]
0x14000eb7a  mov     rax, [rcx]
0x14000eb7d  mov     rax, [rax+8]
0x14000eb81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000eb86  lea     rdx, ?_switchApps@StartList@@0PAGA; "SwitchApps"
0x14000eb8d  mov     r8, r15
0x14000eb90  inc     r8
0x14000eb93  cmp     [rdx+r8*2], r14w
0x14000eb98  jnz     short loc_14000EB90
0x14000eb9a  lea     rcx, [rbp+lpSubKey]
0x14000eb9e  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x14000eba3  mov     [rbp+hKey], r14
0x14000eba7  lea     rax, [rbp+hKey]
0x14000ebab  mov     [rsp+70h+phkResult], rax; phkResult
0x14000ebb0  mov     r9d, 20006h; samDesired
0x14000ebb6  xor     r8d, r8d; ulOptions
0x14000ebb9  mov     rbx, [rbp+lpSubKey]
0x14000ebbd  mov     rdx, rbx; lpSubKey
0x14000ebc0  mov     rdi, 0FFFFFFFF80000002h
0x14000ebc7  mov     rcx, rdi; hKey
0x14000ebca  call    cs:__imp_RegOpenKeyExW
0x14000ebd0  test    eax, eax
0x14000ebd2  jnz     short loc_14000EBE1
0x14000ebd4  mov     rdi, [rbp+hKey]
0x14000ebd8  mov     [rbp+var_20], rdi
0x14000ebdc  lea     esi, [rax+1]
0x14000ebdf  jmp     short loc_14000EC42
0x14000ebe1  lea     rax, [rbp+lpSubKey]
0x14000ebe5  mov     [rsp+70h+var_38], rax; unsigned int *
0x14000ebea  mov     [rsp+70h+var_48], 3; unsigned int
0x14000ebf2  mov     dword ptr [rsp+70h+phkResult], 1; unsigned int
0x14000ebfa  mov     r8, rbx; unsigned __int16 *
0x14000ebfd  mov     rdx, rdi; HKEY
0x14000ec00  lea     rcx, [rbp+var_20]; this
0x14000ec04  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x14000ec09  test    eax, eax
0x14000ec0b  jz      short loc_14000EC3B
0x14000ec0d  lea     rdx, WPP_GLOBAL_Control
0x14000ec14  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ec1b  cmp     rcx, rdx
0x14000ec1e  jz      short loc_14000EC3B
0x14000ec20  test    byte ptr [rcx+1Ch], 8
0x14000ec24  jz      short loc_14000EC3B
0x14000ec26  mov     edx, 1Fh
0x14000ec2b  mov     dword ptr [rsp+70h+phkResult], eax
0x14000ec2f  mov     r9, rbx
0x14000ec32  mov     rcx, [rcx+10h]
0x14000ec36  call    WPP_SF_Sd
0x14000ec3b  mov     esi, r14d
0x14000ec3e  mov     rdi, [rbp+var_20]
0x14000ec42  lea     rdx, [rbx-18h]
0x14000ec46  mov     eax, r15d
0x14000ec49  lock xadd [rdx+10h], eax
0x14000ec4e  add     eax, r15d
0x14000ec51  test    eax, eax
0x14000ec53  jg      short loc_14000EC65
0x14000ec55  mov     rcx, [rdx]
0x14000ec58  mov     rax, [rcx]
0x14000ec5b  mov     rax, [rax+8]
0x14000ec5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ec64  nop
0x14000ec65  test    rdi, rdi
0x14000ec68  jz      short loc_14000EC74
0x14000ec6a  mov     rcx, rdi; hKey
0x14000ec6d  call    cs:__imp_RegCloseKey
0x14000ec73  nop
0x14000ec74  lea     rcx, [rbp+var_30]; this
0x14000ec78  call    ??1_Trace@@QEAA@XZ; _Trace::~_Trace(void)
0x14000ec7d  mov     eax, esi
0x14000ec7f  mov     rbx, [rsp+70h+arg_10]
0x14000ec87  add     rsp, 70h
0x14000ec8b  pop     r15
0x14000ec8d  pop     r14
0x14000ec8f  pop     rdi
0x14000ec90  pop     rsi
0x14000ec91  pop     rbp
0x14000ec92  retn
0x14000ec93  mov     ecx, 80004005h; int
0x14000ec98  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
