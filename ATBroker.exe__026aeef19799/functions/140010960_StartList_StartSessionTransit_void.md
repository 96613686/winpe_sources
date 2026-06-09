# StartList::StartSessionTransit(void)

- ea: `0x140010960`
- end: `0x140010bb4`
- name: `?StartSessionTransit@StartList@@QEAAJXZ`
- size: `596`
- prototype: `__int64 __fastcall(StartList *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000b250`

## callees

- `0x1400053cc`
- `0x14000c19c`
- `0x14000c7e0`
- `0x14000d1b8`
- `0x14000ddb0`
- `0x140010244`
- `0x140010960`
- `0x140011080`
- `0x1400111c0`
- `0x1400116c4`
- `0x140017010`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x140010a59`
- `ADVAPI32!RegOpenKeyExW` at `0x140010a59`
- `ADVAPI32!RegCloseKey` at `0x140010ace`
- `ADVAPI32!RegCloseKey` at `0x140010ace`
- `KERNEL32!RegSetValueExW` at `0x140010a8d`
- `KERNEL32!RegSetValueExW` at `0x140010a8d`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall StartList::StartSessionTransit(StartList *this)
{
  unsigned int v2; // esi
  __int64 v3; // rcx
  _QWORD *v4; // rdx
  HKEY v5; // rbx
  int v6; // eax
  __int64 v7; // r8
  __int64 **v8; // rbx
  __int64 *v9; // r14
  const wchar_t **v10; // rax
  void *v11; // r8
  const wchar_t **v12; // rdi
  int v13; // eax
  int v14; // r8d
  _QWORD *v15; // rdx
  _QWORD *v17; // rdx
  __int128 v18; // [rsp+30h] [rbp-30h] BYREF
  __int64 v19; // [rsp+40h] [rbp-20h]
  __int128 v20; // [rsp+48h] [rbp-18h]
  int v21; // [rsp+58h] [rbp-8h]
  __int64 Data; // [rsp+98h] [rbp+38h] BYREF
  __int64 v23; // [rsp+A0h] [rbp+40h] BYREF
  HKEY hKey; // [rsp+A8h] [rbp+48h] BYREF

  v18 = 0;
  v19 = 0;
  v20 = 0;
  v21 = 10;
  ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::RemoveAll(&v18);
  v2 = 0;
  Data = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  StartList::GetSessionTransitValue(v3, (__int64)&Data);
  StartList::BuildConfigList(&Data, &v18);
  v4 = (_QWORD *)(Data - 24);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(Data - 24 + 16), 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v4 + 8LL))(*v4);
  if ( v19 )
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      &v23,
      L"narrator");
    if ( ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::Find(
           &v18,
           v23) )
    {
      hKey = 0;
      if ( !RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Narrator", 0, 0x2001Fu, &hKey) )
      {
        v5 = hKey;
        LODWORD(Data) = 2;
        v6 = RegSetValueExW(hKey, L"KeyboardLayoutMigrationState", 0, 4u, (const BYTE *)&Data, 4u);
        if ( v6
          && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          if ( v6 > 0 )
            v6 = (unsigned __int16)v6 | 0x80070000;
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, v7, (unsigned int)v6);
        }
        if ( v5 )
          RegCloseKey(v5);
      }
    }
    v8 = (__int64 **)v18;
    while ( 1 )
    {
      if ( !v8 )
      {
        v15 = (_QWORD *)(v23 - 24);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v23 - 24 + 16), 0xFFFFFFFF) <= 1 )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v15 + 8LL))(*v15);
        goto LABEL_23;
      }
      v9 = *v8;
      v10 = (const wchar_t **)Accommodation::Open((const unsigned __int16 *)v8[2]);
      v12 = v10;
      if ( !v10 )
        break;
      v8 = (__int64 **)v9;
      v13 = (unsigned int)StartList::Start(this, v10, v11, 0, 0);
      if ( v13 < 0 )
      {
        v2 = v13;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, v14, (unsigned int)*v12, v13);
      }
    }
    v17 = (_QWORD *)(v23 - 24);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v23 - 24 + 16), 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v17 + 8LL))(*v17);
    v2 = -2147024882;
  }
LABEL_23:
  ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::RemoveAll(&v18);
  return v2;
}

```

## disassembly

```asm
0x140010960  mov     [rsp-28h+arg_0], rbx
0x140010965  push    rbp
0x140010966  push    rsi
0x140010967  push    rdi
0x140010968  push    r14
0x14001096a  push    r15
0x14001096c  mov     rbp, rsp
0x14001096f  sub     rsp, 60h
0x140010973  mov     r15, rcx
0x140010976  xorps   xmm0, xmm0
0x140010979  movdqu  [rbp+var_30], xmm0
0x14001097e  mov     [rbp+var_20], 0
0x140010986  movdqu  [rbp+var_18], xmm0
0x14001098b  mov     [rbp+var_8], 0Ah
0x140010992  lea     rcx, [rbp+var_30]
0x140010996  call    ?RemoveAll@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAXXZ; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::RemoveAll(void)
0x14001099b  nop
0x14001099c  xor     esi, esi
0x14001099e  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400109a5  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400109ac  mov     rax, [rax+18h]
0x1400109b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400109b5  add     rax, 18h
0x1400109b9  mov     [rbp+Data], rax
0x1400109bd  lea     rdx, [rbp+Data]
0x1400109c1  call    ?GetSessionTransitValue@StartList@@AEAAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; StartList::GetSessionTransitValue(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x1400109c6  lea     rdx, [rbp+var_30]
0x1400109ca  lea     rcx, [rbp+Data]
0x1400109ce  call    ?BuildConfigList@StartList@@SAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAV?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@3@@Z; StartList::BuildConfigList(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> &)
0x1400109d3  nop
0x1400109d4  mov     rdx, [rbp+Data]
0x1400109d8  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1400109dc  or      eax, 0FFFFFFFFh
0x1400109df  lock xadd [rdx+10h], eax
0x1400109e4  sub     eax, 1
0x1400109e7  jg      short loc_1400109F8
0x1400109e9  mov     rcx, [rdx]
0x1400109ec  mov     rax, [rcx]
0x1400109ef  mov     rax, [rax+8]
0x1400109f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400109f8  cmp     [rbp+var_20], 0
0x1400109fd  jz      loc_140010B69
0x140010a03  lea     rdx, aNarrator; "narrator"
0x140010a0a  lea     rcx, [rbp+arg_10]
0x140010a0e  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x140010a13  nop
0x140010a14  mov     rdx, [rbp+arg_10]
0x140010a18  lea     rcx, [rbp+var_30]
0x140010a1c  call    ?Find@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEBAPEAU__POSITION@@PEBGPEAU3@@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::Find(ushort const *,__POSITION *)
0x140010a21  lea     rdi, WPP_GLOBAL_Control
0x140010a28  test    rax, rax
0x140010a2b  jz      loc_140010AD4
0x140010a31  mov     [rbp+hKey], 0
0x140010a39  lea     rax, [rbp+hKey]
0x140010a3d  mov     [rsp+60h+phkResult], rax; phkResult
0x140010a42  mov     r9d, 2001Fh; samDesired
0x140010a48  xor     r8d, r8d; ulOptions
0x140010a4b  lea     rdx, aSoftwareMicros_7; "Software\\Microsoft\\Narrator"
0x140010a52  mov     rcx, 0FFFFFFFF80000001h; hKey
0x140010a59  call    cs:__imp_RegOpenKeyExW
0x140010a5f  test    eax, eax
0x140010a61  jnz     short loc_140010AD4
0x140010a63  mov     rbx, [rbp+hKey]
0x140010a67  mov     dword ptr [rbp+Data], 2
0x140010a6e  lea     r9d, [rax+4]; dwType
0x140010a72  mov     [rsp+60h+cbData], r9d; cbData
0x140010a77  lea     rax, [rbp+Data]
0x140010a7b  mov     [rsp+60h+phkResult], rax; lpData
0x140010a80  xor     r8d, r8d; Reserved
0x140010a83  lea     rdx, aKeyboardlayout; "KeyboardLayoutMigrationState"
0x140010a8a  mov     rcx, rbx; hKey
0x140010a8d  call    cs:__imp_RegSetValueExW
0x140010a93  test    eax, eax
0x140010a95  jz      short loc_140010AC6
0x140010a97  mov     rcx, cs:WPP_GLOBAL_Control
0x140010a9e  cmp     rcx, rdi
0x140010aa1  jz      short loc_140010AC6
0x140010aa3  test    byte ptr [rcx+1Ch], 8
0x140010aa7  jz      short loc_140010AC6
0x140010aa9  test    eax, eax
0x140010aab  jle     short loc_140010AB5
0x140010aad  movzx   eax, ax
0x140010ab0  or      eax, 80070000h
0x140010ab5  mov     edx, 10h
0x140010aba  mov     r9d, eax
0x140010abd  mov     rcx, [rcx+10h]
0x140010ac1  call    WPP_SF_d
0x140010ac6  test    rbx, rbx
0x140010ac9  jz      short loc_140010AD4
0x140010acb  mov     rcx, rbx; hKey
0x140010ace  call    cs:__imp_RegCloseKey
0x140010ad4  mov     rbx, qword ptr [rbp+var_30]
0x140010ad8  jmp     short loc_140010B3F
0x140010ada  mov     r14, [rbx]
0x140010add  mov     rcx, [rbx+10h]; unsigned __int16 *
0x140010ae1  call    ?Open@Accommodation@@SAPEAV1@PEBG@Z; Accommodation::Open(ushort const *)
0x140010ae6  mov     rdi, rax
0x140010ae9  test    rax, rax
0x140010aec  jz      loc_140010B88
0x140010af2  mov     rbx, r14
0x140010af5  mov     dword ptr [rsp+60h+phkResult], 0; int
0x140010afd  xor     r9d, r9d; int
0x140010b00  mov     rdx, rax; struct Accommodation *
0x140010b03  mov     rcx, r15; this
0x140010b06  call    ?Start@StartList@@QEAAJPEAVAccommodation@@PEAXHH@Z; StartList::Start(Accommodation *,void *,int,int)
0x140010b0b  test    eax, eax
0x140010b0d  jns     short loc_140010B3F
0x140010b0f  mov     esi, eax
0x140010b11  mov     rcx, cs:WPP_GLOBAL_Control
0x140010b18  lea     rdx, WPP_GLOBAL_Control
0x140010b1f  cmp     rcx, rdx
0x140010b22  jz      short loc_140010B3F
0x140010b24  test    byte ptr [rcx+1Ch], 8
0x140010b28  jz      short loc_140010B3F
0x140010b2a  mov     edx, 11h
0x140010b2f  mov     dword ptr [rsp+60h+phkResult], eax
0x140010b33  mov     r9, [rdi]
0x140010b36  mov     rcx, [rcx+10h]
0x140010b3a  call    WPP_SF_Sd
0x140010b3f  test    rbx, rbx
0x140010b42  jnz     short loc_140010ADA
0x140010b44  mov     rdx, [rbp+arg_10]
0x140010b48  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140010b4c  or      eax, 0FFFFFFFFh
0x140010b4f  lock xadd [rdx+10h], eax
0x140010b54  sub     eax, 1
0x140010b57  jg      short loc_140010B69
0x140010b59  mov     rcx, [rdx]
0x140010b5c  mov     r8, [rcx]
0x140010b5f  mov     rax, [r8+8]
0x140010b63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010b68  nop
0x140010b69  lea     rcx, [rbp+var_30]
0x140010b6d  call    ?RemoveAll@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAXXZ; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::RemoveAll(void)
0x140010b72  mov     eax, esi
0x140010b74  mov     rbx, [rsp+60h+arg_0]
0x140010b7c  add     rsp, 60h
0x140010b80  pop     r15
0x140010b82  pop     r14
0x140010b84  pop     rdi
0x140010b85  pop     rsi
0x140010b86  pop     rbp
0x140010b87  retn
0x140010b88  mov     rdx, [rbp+arg_10]
0x140010b8c  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140010b90  or      eax, 0FFFFFFFFh
0x140010b93  lock xadd [rdx+10h], eax
0x140010b98  sub     eax, 1
0x140010b9b  jg      short loc_140010BAC
0x140010b9d  mov     rcx, [rdx]
0x140010ba0  mov     rax, [rcx]
0x140010ba3  mov     rax, [rax+8]
0x140010ba7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010bac  mov     esi, 8007000Eh
0x140010bb1  jmp     short loc_140010B69
```
