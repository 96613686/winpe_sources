# StartList::HandleFirstTime(ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CRegKey &)

- ea: `0x14000e538`
- end: `0x14000ea31`
- name: `?HandleFirstTime@StartList@@AEAAJAEBV?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@AEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@3@AEAVCRegKey@3@@Z`
- size: `1273`
- prototype: `__int64 __fastcall(__int64, _QWORD **, __int64, ATL::CRegKey *)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x14000ee8c`

## callees

- `0x140004890`
- `0x140007708`
- `0x14000be54`
- `0x14000c19c`
- `0x14000c340`
- `0x14000c7e0`
- `0x14000ce48`
- `0x14000d118`
- `0x14000d334`
- `0x14000e538`
- `0x140011050`
- `0x1400111c0`
- `0x1400116c4`
- `0x140015ac2`
- `0x140015b00`
- `0x140017010`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x14000e741`
- `ADVAPI32!RegOpenKeyExW` at `0x14000e741`
- `ADVAPI32!RegCloseKey` at `0x14000e984`
- `ADVAPI32!RegCloseKey` at `0x14000e984`
- `KERNEL32!DeleteFileW` at `0x14000e83e`
- `KERNEL32!DeleteFileW` at `0x14000e88d`
- `KERNEL32!DeleteFileW` at `0x14000e8dc`
- `KERNEL32!DeleteFileW` at `0x14000e83e`
- `KERNEL32!DeleteFileW` at `0x14000e88d`
- `KERNEL32!DeleteFileW` at `0x14000e8dc`
- `KERNEL32!GetFileAttributesW` at `0x14000e80c`
- `KERNEL32!GetFileAttributesW` at `0x14000e868`
- `KERNEL32!GetFileAttributesW` at `0x14000e8b7`
- `KERNEL32!GetFileAttributesW` at `0x14000e80c`
- `KERNEL32!GetFileAttributesW` at `0x14000e868`
- `KERNEL32!GetFileAttributesW` at `0x14000e8b7`
- `KERNEL32!RegSetValueExW` at `0x14000e6c1`
- `KERNEL32!RegSetValueExW` at `0x14000e6c1`

## string_xrefs

- `0x14000e6b7`: `Configuration`
- `0x14000e58b`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Accessibility`

## pseudocode

```c
__int64 __fastcall StartList::HandleFirstTime(__int64 a1, _QWORD **a2, __int64 a3, ATL::CRegKey *a4)
{
  unsigned int v7; // eax
  __int64 v8; // r8
  signed int v9; // ebx
  _QWORD *v11; // rbx
  _QWORD *v12; // rdi
  BYTE *v13; // rsi
  __int64 v14; // rax
  unsigned int v15; // eax
  __int64 v16; // r8
  unsigned int v17; // eax
  __int64 v18; // r8
  LPCWSTR v19; // rdx
  LPCWSTR v20; // rdx
  LPCWSTR v21; // rdx
  struct _SECURITY_ATTRIBUTES *v22; // [rsp+30h] [rbp-D0h]
  unsigned int v23; // [rsp+40h] [rbp-C0h] BYREF
  LPCWSTR v24; // [rsp+48h] [rbp-B8h] BYREF
  LPCWSTR v25; // [rsp+50h] [rbp-B0h] BYREF
  LPCWSTR lpFileName; // [rsp+58h] [rbp-A8h] BYREF
  BYTE *lpData; // [rsp+60h] [rbp-A0h] BYREF
  HKEY phkResult; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v29[3]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v30; // [rsp+88h] [rbp-78h] BYREF
  __int64 v31; // [rsp+98h] [rbp-68h]
  __int128 v32; // [rsp+A0h] [rbp-60h]
  int v33; // [rsp+B0h] [rbp-50h]
  unsigned __int16 v34[264]; // [rsp+C0h] [rbp-40h] BYREF

  v7 = ATL::CRegKey::Create(
         a4,
         HKEY_CURRENT_USER,
         StartList::_accessibilityKeyString,
         (unsigned __int16 *)a4,
         0,
         3u,
         v22,
         &v23);
  v9 = v7;
  if ( v7 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, v8, v7);
    if ( v9 > 0 )
      return (unsigned __int16)v9 | 0x80070000;
    return (unsigned int)v9;
  }
  v30 = 0;
  v31 = 0;
  v32 = 0;
  v33 = 10;
  v11 = *a2;
  while ( v11 )
  {
    v12 = v11;
    v11 = (_QWORD *)*v11;
    if ( *((_DWORD *)Accommodation::Open((const unsigned __int16 *)v12[2]) + 20) != 1 )
      ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::AddTail(
        &v30,
        v12[2]);
  }
  lpData = (BYTE *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  StartList::BuildConfigString(&lpData, &v30);
  v13 = lpData;
  if ( !lpData )
    ATL::AtlThrowImpl(-2147467259);
  v14 = -1;
  do
    ++v14;
  while ( *(_WORD *)&lpData[2 * v14] );
  v15 = RegSetValueExW(*(HKEY *)a4, StartList::_configuration, 0, 1u, lpData, 2 * v14 + 2);
  v9 = v15;
  if ( v15 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, v16, v15);
    if ( v9 > 0 )
      v9 = (unsigned __int16)v9 | 0x80070000;
LABEL_50:
    if ( _InterlockedDecrement((volatile signed __int32 *)v13 - 2) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v13 - 3) + 8LL))(*((_QWORD *)v13 - 3));
    ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::RemoveAll(&v30);
    return (unsigned int)v9;
  }
  memset(v29, 0, sizeof(v29));
  phkResult = 0;
  v17 = RegOpenKeyExW(
          HKEY_CURRENT_USER,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\Shell Folders",
          0,
          0x20019u,
          &phkResult);
  v9 = v17;
  if ( v17 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, v18, v17);
    if ( v9 > 0 )
      v9 = (unsigned __int16)v9 | 0x80070000;
    goto LABEL_50;
  }
  v29[0] = phkResult;
  memset_0(v34, 0, 0x208u);
  v23 = 260;
  ATL::CRegKey::QueryStringValue((ATL::CRegKey *)v29, L"Startup", v34, &v23);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &lpFileName,
    v34);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v25,
    v34);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v24,
    v34);
  ATL::CSimpleStringT<unsigned short,0>::Append(&lpFileName, L"\\On-Screen Keyboard.lnk");
  ATL::CSimpleStringT<unsigned short,0>::Append(&v25, L"\\Narrator.lnk");
  ATL::CSimpleStringT<unsigned short,0>::Append(&v24, L"\\Magnifier.lnk");
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
    a3,
    &lpData);
  if ( GetFileAttributesW(lpFileName) != -1 )
  {
    ATL::CSimpleStringT<unsigned short,0>::Append(a3, L",osk");
    DeleteFileW(lpFileName);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 44);
  }
  if ( GetFileAttributesW(v25) != -1 )
  {
    ATL::CSimpleStringT<unsigned short,0>::Append(a3, L",Narrator");
    DeleteFileW(v25);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 45);
  }
  if ( GetFileAttributesW(v24) != -1 )
  {
    ATL::CSimpleStringT<unsigned short,0>::Append(a3, L",magnifierpane");
    DeleteFileW(v24);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 46);
  }
  v19 = v24 - 12;
  if ( _InterlockedDecrement((volatile signed __int32 *)v24 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v19 + 8LL))(*(_QWORD *)v19);
  v20 = v25 - 12;
  if ( _InterlockedDecrement((volatile signed __int32 *)v25 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v20 + 8LL))(*(_QWORD *)v20);
  v21 = lpFileName - 12;
  if ( _InterlockedDecrement((volatile signed __int32 *)lpFileName - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v21 + 8LL))(*(_QWORD *)v21);
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( _InterlockedDecrement((volatile signed __int32 *)v13 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v13 - 3) + 8LL))(*((_QWORD *)v13 - 3));
  ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::RemoveAll(&v30);
  return 0;
}

```

## disassembly

```asm
0x14000e538  mov     [rsp-8+arg_0], rbx
0x14000e53d  push    rbp
0x14000e53e  push    rsi
0x14000e53f  push    rdi
0x14000e540  push    r12
0x14000e542  push    r13
0x14000e544  push    r14
0x14000e546  push    r15
0x14000e548  lea     rbp, [rsp-1E0h]
0x14000e550  sub     rsp, 2E0h
0x14000e557  mov     rax, cs:__security_cookie
0x14000e55e  xor     rax, rsp
0x14000e561  mov     [rbp+210h+var_40], rax
0x14000e568  mov     r15, r9
0x14000e56b  mov     r14, r8
0x14000e56e  mov     rdi, rdx
0x14000e571  lea     rax, [rsp+310h+var_2D0]
0x14000e576  mov     [rsp+310h+var_2D8], rax; unsigned int *
0x14000e57b  mov     [rsp+310h+cbData], 3; unsigned int
0x14000e583  xor     r12d, r12d
0x14000e586  mov     dword ptr [rsp+310h+lpData], r12d; unsigned int
0x14000e58b  lea     r8, ?_accessibilityKeyString@StartList@@0PAGA; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x14000e592  mov     rdx, 0FFFFFFFF80000001h; HKEY
0x14000e599  mov     rcx, r9; this
0x14000e59c  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x14000e5a1  mov     ebx, eax
0x14000e5a3  test    eax, eax
0x14000e5a5  jz      short loc_14000E60A
0x14000e5a7  lea     rdi, WPP_GLOBAL_Control
0x14000e5ae  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e5b5  cmp     rcx, rdi
0x14000e5b8  jz      short loc_14000E5D1
0x14000e5ba  test    byte ptr [rcx+1Ch], 8
0x14000e5be  jz      short loc_14000E5D1
0x14000e5c0  lea     edx, [r12+29h]
0x14000e5c5  mov     r9d, eax
0x14000e5c8  mov     rcx, [rcx+10h]
0x14000e5cc  call    WPP_SF_d
0x14000e5d1  test    ebx, ebx
0x14000e5d3  jle     short loc_14000E5DE
0x14000e5d5  movzx   ebx, bx
0x14000e5d8  or      ebx, 80070000h
0x14000e5de  mov     eax, ebx
0x14000e5e0  mov     rcx, [rbp+210h+var_40]
0x14000e5e7  xor     rcx, rsp; StackCookie
0x14000e5ea  call    __security_check_cookie
0x14000e5ef  mov     rbx, [rsp+310h+arg_0]
0x14000e5f7  add     rsp, 2E0h
0x14000e5fe  pop     r15
0x14000e600  pop     r14
0x14000e602  pop     r13
0x14000e604  pop     r12
0x14000e606  pop     rdi
0x14000e607  pop     rsi
0x14000e608  pop     rbp
0x14000e609  retn
0x14000e60a  xorps   xmm0, xmm0
0x14000e60d  movdqu  [rbp+210h+var_288], xmm0
0x14000e612  mov     [rbp+210h+var_278], r12
0x14000e616  xorps   xmm1, xmm1
0x14000e619  movdqu  [rbp+210h+var_270], xmm1
0x14000e61e  mov     [rbp+210h+var_260], 0Ah
0x14000e625  mov     rbx, [rdi]
0x14000e628  jmp     short loc_14000E64C
0x14000e62a  lea     rdi, [rbx]
0x14000e62d  mov     rbx, [rbx]
0x14000e630  mov     rcx, [rdi+10h]; unsigned __int16 *
0x14000e634  call    ?Open@Accommodation@@SAPEAV1@PEBG@Z; Accommodation::Open(ushort const *)
0x14000e639  cmp     dword ptr [rax+50h], 1
0x14000e63d  jz      short loc_14000E64C
0x14000e63f  mov     rdx, [rdi+10h]
0x14000e643  lea     rcx, [rbp+210h+var_288]
0x14000e647  call    ?AddTail@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAPEAU__POSITION@@PEBG@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::AddTail(ushort const *)
0x14000e64c  test    rbx, rbx
0x14000e64f  jnz     short loc_14000E62A
0x14000e651  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000e658  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000e65f  mov     rax, [rax+18h]
0x14000e663  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e668  add     rax, 18h
0x14000e66c  mov     [rsp+310h+var_2B0], rax
0x14000e671  lea     rdx, [rbp+210h+var_288]
0x14000e675  lea     rcx, [rsp+310h+var_2B0]
0x14000e67a  call    ?BuildConfigString@StartList@@SAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEBV?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@3@@Z; StartList::BuildConfigString(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> const &)
0x14000e67f  mov     rsi, [rsp+310h+var_2B0]
0x14000e684  test    rsi, rsi
0x14000e687  jz      loc_14000EA26
0x14000e68d  or      r13, 0FFFFFFFFFFFFFFFFh
0x14000e691  mov     rax, r13
0x14000e694  inc     rax
0x14000e697  cmp     [rsi+rax*2], r12w
0x14000e69c  jnz     short loc_14000E694
0x14000e69e  lea     eax, ds:2[rax*2]
0x14000e6a5  mov     [rsp+310h+cbData], eax; cbData
0x14000e6a9  mov     [rsp+310h+lpData], rsi; lpData
0x14000e6ae  mov     r9d, 1; dwType
0x14000e6b4  xor     r8d, r8d; Reserved
0x14000e6b7  lea     rdx, ?_configuration@StartList@@0PAGA; "Configuration"
0x14000e6be  mov     rcx, [r15]; hKey
0x14000e6c1  call    cs:__imp_RegSetValueExW
0x14000e6c7  mov     ebx, eax
0x14000e6c9  test    eax, eax
0x14000e6cb  jz      short loc_14000E70D
0x14000e6cd  lea     rdi, WPP_GLOBAL_Control
0x14000e6d4  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e6db  cmp     rcx, rdi
0x14000e6de  jz      short loc_14000E6F7
0x14000e6e0  test    byte ptr [rcx+1Ch], 8
0x14000e6e4  jz      short loc_14000E6F7
0x14000e6e6  mov     edx, 2Ah ; '*'
0x14000e6eb  mov     r9d, eax
0x14000e6ee  mov     rcx, [rcx+10h]
0x14000e6f2  call    WPP_SF_d
0x14000e6f7  test    ebx, ebx
0x14000e6f9  jle     loc_14000E9F5
0x14000e6ff  movzx   ebx, bx
0x14000e702  or      ebx, 80070000h
0x14000e708  jmp     loc_14000E9F5
0x14000e70d  mov     [rsp+310h+var_2A0], r12
0x14000e712  mov     [rsp+310h+var_298], r12
0x14000e717  mov     [rbp+210h+var_290], r12
0x14000e71b  mov     [rsp+310h+phkResult], r12
0x14000e720  lea     rax, [rsp+310h+phkResult]
0x14000e725  mov     [rsp+310h+lpData], rax; phkResult
0x14000e72a  mov     r9d, 20019h; samDesired
0x14000e730  xor     r8d, r8d; ulOptions
0x14000e733  lea     rdx, aSoftwareMicros_5; "Software\\Microsoft\\Windows\\CurrentVe"...
0x14000e73a  mov     rcx, 0FFFFFFFF80000001h; hKey
0x14000e741  call    cs:__imp_RegOpenKeyExW
0x14000e747  mov     ebx, eax
0x14000e749  test    eax, eax
0x14000e74b  jnz     loc_14000E9BE
0x14000e751  mov     rax, [rsp+310h+phkResult]
0x14000e756  mov     [rsp+310h+var_2A0], rax
0x14000e75b  xor     edx, edx; Val
0x14000e75d  mov     r8d, 208h; Size
0x14000e763  lea     rcx, [rbp+210h+var_250]; void *
0x14000e767  call    memset_0
0x14000e76c  mov     [rsp+310h+var_2D0], 104h
0x14000e774  lea     r9, [rsp+310h+var_2D0]; unsigned int *
0x14000e779  lea     r8, [rbp+210h+var_250]; unsigned __int16 *
0x14000e77d  lea     rdx, aStartup; "Startup"
0x14000e784  lea     rcx, [rsp+310h+var_2A0]; this
0x14000e789  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEBGPEAGPEAK@Z; ATL::CRegKey::QueryStringValue(ushort const *,ushort *,ulong *)
0x14000e78e  lea     rdx, [rbp+210h+var_250]
0x14000e792  lea     rcx, [rsp+310h+lpFileName]
0x14000e797  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x14000e79c  nop
0x14000e79d  lea     rdx, [rbp+210h+var_250]
0x14000e7a1  lea     rcx, [rsp+310h+var_2C0]
0x14000e7a6  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x14000e7ab  nop
0x14000e7ac  lea     rdx, [rbp+210h+var_250]
0x14000e7b0  lea     rcx, [rsp+310h+var_2C8]
0x14000e7b5  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x14000e7ba  nop
0x14000e7bb  lea     r8d, [rbx+17h]
0x14000e7bf  lea     rdx, aOnScreenKeyboa; "\\On-Screen Keyboard.lnk"
0x14000e7c6  lea     rcx, [rsp+310h+lpFileName]
0x14000e7cb  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x14000e7d0  lea     r8d, [rbx+0Dh]
0x14000e7d4  lea     rdx, aNarratorLnk; "\\Narrator.lnk"
0x14000e7db  lea     rcx, [rsp+310h+var_2C0]
0x14000e7e0  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x14000e7e5  lea     r8d, [rbx+0Eh]
0x14000e7e9  lea     rdx, aMagnifierLnk; "\\Magnifier.lnk"
0x14000e7f0  lea     rcx, [rsp+310h+var_2C8]
0x14000e7f5  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x14000e7fa  lea     rdx, [rsp+310h+var_2B0]
0x14000e7ff  mov     rcx, r14
0x14000e802  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14000e807  mov     rcx, [rsp+310h+lpFileName]; lpFileName
0x14000e80c  call    cs:__imp_GetFileAttributesW
0x14000e812  mov     bl, 10h
0x14000e814  lea     rdi, WPP_GLOBAL_Control
0x14000e81b  or      r15d, 0FFFFFFFFh
0x14000e81f  cmp     eax, r15d
0x14000e822  jz      short loc_14000E863
0x14000e824  mov     r8d, 4
0x14000e82a  lea     rdx, aOsk_0; ",osk"
0x14000e831  mov     rcx, r14
0x14000e834  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x14000e839  mov     rcx, [rsp+310h+lpFileName]; lpFileName
0x14000e83e  call    cs:__imp_DeleteFileW
0x14000e844  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e84b  cmp     rcx, rdi
0x14000e84e  jz      short loc_14000E863
0x14000e850  test    [rcx+1Ch], bl
0x14000e853  jz      short loc_14000E863
0x14000e855  mov     edx, 2Ch ; ','
0x14000e85a  mov     rcx, [rcx+10h]
0x14000e85e  call    WPP_SF_
0x14000e863  mov     rcx, [rsp+310h+var_2C0]; lpFileName
0x14000e868  call    cs:__imp_GetFileAttributesW
0x14000e86e  cmp     eax, r15d
0x14000e871  jz      short loc_14000E8B2
0x14000e873  mov     r8d, 9
0x14000e879  lea     rdx, aNarrator_1; ",Narrator"
0x14000e880  mov     rcx, r14
0x14000e883  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x14000e888  mov     rcx, [rsp+310h+var_2C0]; lpFileName
0x14000e88d  call    cs:__imp_DeleteFileW
0x14000e893  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e89a  cmp     rcx, rdi
0x14000e89d  jz      short loc_14000E8B2
0x14000e89f  test    [rcx+1Ch], bl
0x14000e8a2  jz      short loc_14000E8B2
0x14000e8a4  mov     edx, 2Dh ; '-'
0x14000e8a9  mov     rcx, [rcx+10h]
0x14000e8ad  call    WPP_SF_
0x14000e8b2  mov     rcx, [rsp+310h+var_2C8]; lpFileName
0x14000e8b7  call    cs:__imp_GetFileAttributesW
0x14000e8bd  cmp     eax, r15d
0x14000e8c0  jz      short loc_14000E902
0x14000e8c2  mov     r8d, 0Eh
0x14000e8c8  lea     rdx, aMagnifierpane_0; ",magnifierpane"
0x14000e8cf  mov     rcx, r14
0x14000e8d2  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x14000e8d7  mov     rcx, [rsp+310h+var_2C8]; lpFileName
0x14000e8dc  call    cs:__imp_DeleteFileW
0x14000e8e2  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e8e9  cmp     rcx, rdi
0x14000e8ec  jz      short loc_14000E902
0x14000e8ee  test    [rcx+1Ch], bl
0x14000e8f1  jz      short loc_14000E902
0x14000e8f3  mov     edx, 2Eh ; '.'
0x14000e8f8  mov     rcx, [rcx+10h]
0x14000e8fc  call    WPP_SF_
0x14000e901  nop
0x14000e902  mov     rdx, [rsp+310h+var_2C8]
0x14000e907  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14000e90b  mov     eax, r13d
0x14000e90e  lock xadd [rdx+10h], eax
0x14000e913  add     eax, r13d
0x14000e916  test    eax, eax
0x14000e918  jg      short loc_14000E92A
0x14000e91a  mov     rcx, [rdx]
0x14000e91d  mov     rax, [rcx]
0x14000e920  mov     rax, [rax+8]
0x14000e924  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e929  nop
0x14000e92a  mov     rdx, [rsp+310h+var_2C0]
0x14000e92f  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14000e933  mov     eax, r13d
0x14000e936  lock xadd [rdx+10h], eax
0x14000e93b  add     eax, r13d
0x14000e93e  test    eax, eax
0x14000e940  jg      short loc_14000E952
0x14000e942  mov     rcx, [rdx]
0x14000e945  mov     rax, [rcx]
0x14000e948  mov     rax, [rax+8]
0x14000e94c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e951  nop
0x14000e952  mov     rdx, [rsp+310h+lpFileName]
0x14000e957  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14000e95b  mov     eax, r13d
0x14000e95e  lock xadd [rdx+10h], eax
0x14000e963  add     eax, r13d
0x14000e966  test    eax, eax
0x14000e968  jg      short loc_14000E97A
0x14000e96a  mov     rcx, [rdx]
0x14000e96d  mov     rax, [rcx]
0x14000e970  mov     rax, [rax+8]
0x14000e974  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e979  nop
0x14000e97a  mov     rcx, [rsp+310h+phkResult]; hKey
0x14000e97f  test    rcx, rcx
0x14000e982  jz      short loc_14000E98B
0x14000e984  call    cs:__imp_RegCloseKey
0x14000e98a  nop
0x14000e98b  lea     rdx, [rsi-18h]
0x14000e98f  mov     eax, r13d
0x14000e992  lock xadd [rdx+10h], eax
0x14000e997  add     eax, r13d
0x14000e99a  test    eax, eax
0x14000e99c  jg      short loc_14000E9AE
0x14000e99e  mov     rcx, [rdx]
0x14000e9a1  mov     rax, [rcx]
0x14000e9a4  mov     rax, [rax+8]
0x14000e9a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e9ad  nop
0x14000e9ae  lea     rcx, [rbp+210h+var_288]
0x14000e9b2  call    ?RemoveAll@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAXXZ; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::RemoveAll(void)
0x14000e9b7  xor     eax, eax
0x14000e9b9  jmp     loc_14000E5E0
0x14000e9be  lea     rdi, WPP_GLOBAL_Control
0x14000e9c5  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e9cc  cmp     rcx, rdi
0x14000e9cf  jz      short loc_14000E9E8
0x14000e9d1  test    byte ptr [rcx+1Ch], 8
0x14000e9d5  jz      short loc_14000E9E8
0x14000e9d7  mov     edx, 2Bh ; '+'
0x14000e9dc  mov     r9d, ebx
0x14000e9df  mov     rcx, [rcx+10h]
0x14000e9e3  call    WPP_SF_d
0x14000e9e8  test    ebx, ebx
0x14000e9ea  jle     short loc_14000E9F5
0x14000e9ec  movzx   ebx, bx
0x14000e9ef  or      ebx, 80070000h
0x14000e9f5  lea     rdx, [rsi-18h]
  ... truncated ...
```
