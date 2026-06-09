# StartList::HandleFirstTime(ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CRegKey &)

- ea: `0x18023c890`
- end: `0x18023cd2a`
- name: `?HandleFirstTime@StartList@@AEAAJAEBV?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@AEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@3@AEAVCRegKey@3@@Z`
- size: `1178`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18023cfa4`

## callees

- `0x18000c840`
- `0x18000d44c`
- `0x180014950`
- `0x180014a30`
- `0x1800176bc`
- `0x18001a330`
- `0x180083c30`
- `0x180228360`
- `0x180228398`
- `0x180238c70`
- `0x180238cdc`
- `0x180238e50`
- `0x180239100`
- `0x180239a30`
- `0x180239f74`
- `0x180239fa4`
- `0x18023a4b8`
- `0x18023ac78`
- `0x18023afd0`
- `0x18023b8b0`
- `0x18023c890`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18023cba0`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18023cc06`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18023cc60`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18023cba0`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18023cc06`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18023cc60`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18023cbd6`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18023cc30`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18023cc8a`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18023cbd6`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18023cc30`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18023cc8a`

## string_xrefs

- `0x18023c8df`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Accessibility`
- `0x18023c9bf`: `Configuration`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall StartList::HandleFirstTime(__int64 a1, _QWORD *a2, _QWORD *a3, ATL::CRegKey *a4)
{
  unsigned int v7; // eax
  __int64 v8; // rcx
  int v9; // ebx
  const unsigned __int16 **Next; // rbx
  unsigned __int16 *v12; // rbx
  unsigned int v13; // r9d
  unsigned int v14; // eax
  signed int v15; // edi
  unsigned int v16; // eax
  ATL::CStringData *v17; // r15
  int *v18; // rdi
  __int64 v19; // rbx
  HKEY v20; // [rsp+30h] [rbp-D0h]
  unsigned int v21[2]; // [rsp+40h] [rbp-C0h] BYREF
  LPCWSTR v22; // [rsp+48h] [rbp-B8h] BYREF
  LPCWSTR v23; // [rsp+50h] [rbp-B0h] BYREF
  LPCWSTR lpFileName; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 *v25; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v26[3]; // [rsp+68h] [rbp-98h] BYREF
  __int128 v27; // [rsp+80h] [rbp-80h] BYREF
  __int64 v28; // [rsp+90h] [rbp-70h]
  __int128 v29; // [rsp+98h] [rbp-68h]
  int v30; // [rsp+A8h] [rbp-58h]
  unsigned __int16 v31[264]; // [rsp+B0h] [rbp-50h] BYREF

  v7 = ATL::CRegKey::Create(
         a4,
         HKEY_CURRENT_USER,
         StartList::_accessibilityKeyString,
         (unsigned __int16 *)a4,
         0,
         3u,
         v20,
         v21);
  v9 = v7;
  if ( !v7 )
  {
    v27 = 0;
    v28 = 0;
    v29 = 0;
    v30 = 10;
    *(_QWORD *)v21 = *a2;
    while ( *(_QWORD *)v21 )
    {
      Next = (const unsigned __int16 **)ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::GetNext(
                                          v8,
                                          v21);
      if ( *((_DWORD *)Accommodation::Open(*Next) + 20) != 1 )
        ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::AddTail(
          &v27,
          *Next);
    }
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v25);
    StartList::BuildConfigString(&v25, &v27);
    v12 = v25;
    v14 = ATL::CRegKey::SetStringValue(a4, StartList::_configuration, v25, v13);
    v15 = v14;
    if ( v14 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, &WPP_0cfc691c390c3581aa6c7b8081e34e7b_Traceguids, v14);
      if ( v15 > 0 )
        v15 = (unsigned __int16)v15 | 0x80070000;
    }
    else
    {
      memset(v26, 0, sizeof(v26));
      v16 = ATL::CRegKey::Open(
              (ATL::CRegKey *)v26,
              HKEY_CURRENT_USER,
              L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\Shell Folders",
              0x20019u);
      v15 = v16;
      if ( !v16 )
      {
        memset_0(v31, 0, 0x208u);
        v21[0] = 260;
        ATL::CRegKey::QueryStringValue((ATL::CRegKey *)v26, L"Startup", v31, v21);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
          &lpFileName,
          v31);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
          &v23,
          v31);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
          &v22,
          v31);
        ATL::CSimpleStringT<unsigned short,0>::Append(&lpFileName, L"\\On-Screen Keyboard.lnk", 23);
        ATL::CSimpleStringT<unsigned short,0>::Append(&v23, L"\\Narrator.lnk", 13);
        ATL::CSimpleStringT<unsigned short,0>::Append(&v22, L"\\Magnifier.lnk", 14);
        v17 = (ATL::CStringData *)(v12 - 12);
        v18 = (int *)(*a3 - 24LL);
        if ( v12 - 12 != (unsigned __int16 *)v18 )
        {
          if ( v18[4] >= 0 && *(_QWORD *)v17 == *(_QWORD *)v18 )
          {
            v19 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v12 - 12);
            ATL::CStringData::Release((ATL::CStringData *)v18);
            *a3 = v19 + 24;
          }
          else
          {
            ATL::CSimpleStringT<unsigned short,0>::SetString(a3, v12, *((unsigned int *)v12 - 4));
          }
        }
        if ( GetFileAttributesW(lpFileName) != -1 )
        {
          ATL::CSimpleStringT<unsigned short,0>::Append(a3, L",osk", 4);
          DeleteFileW(lpFileName);
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 44);
          }
        }
        if ( GetFileAttributesW(v23) != -1 )
        {
          ATL::CSimpleStringT<unsigned short,0>::Append(a3, L",Narrator", 9);
          DeleteFileW(v23);
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 45);
          }
        }
        if ( GetFileAttributesW(v22) != -1 )
        {
          ATL::CSimpleStringT<unsigned short,0>::Append(a3, L",magnifierpane", 14);
          DeleteFileW(v22);
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 46);
          }
        }
        ATL::CStringData::Release((ATL::CStringData *)(v22 - 12));
        ATL::CStringData::Release((ATL::CStringData *)(v23 - 12));
        ATL::CStringData::Release((ATL::CStringData *)(lpFileName - 12));
        ATL::CRegKey::Close((ATL::CRegKey *)v26);
        ATL::CStringData::Release(v17);
        v15 = 0;
        goto LABEL_44;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, &WPP_0cfc691c390c3581aa6c7b8081e34e7b_Traceguids, v16);
      if ( v15 > 0 )
        v15 = (unsigned __int16)v15 | 0x80070000;
      ATL::CRegKey::Close((ATL::CRegKey *)v26);
    }
    ATL::CStringData::Release((ATL::CStringData *)(v12 - 12));
LABEL_44:
    ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::RemoveAll(&v27);
    return (unsigned int)v15;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, &WPP_0cfc691c390c3581aa6c7b8081e34e7b_Traceguids, v7);
  if ( v9 > 0 )
    return (unsigned __int16)v9 | 0x80070000;
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18023c890  mov     [rsp-8+arg_0], rbx
0x18023c895  push    rbp
0x18023c896  push    rsi
0x18023c897  push    rdi
0x18023c898  push    r14
0x18023c89a  push    r15
0x18023c89c  lea     rbp, [rsp-1D0h]
0x18023c8a4  sub     rsp, 2D0h
0x18023c8ab  mov     rax, cs:__security_cookie
0x18023c8b2  xor     rax, rsp
0x18023c8b5  mov     [rbp+1F0h+var_30], rax
0x18023c8bc  mov     rdi, r9
0x18023c8bf  mov     r14, r8
0x18023c8c2  mov     rsi, rdx
0x18023c8c5  lea     rax, [rsp+2F0h+var_2B0]
0x18023c8ca  mov     [rsp+2F0h+var_2B8], rax; unsigned int *
0x18023c8cf  mov     [rsp+2F0h+var_2C8], 3; REGSAM
0x18023c8d7  mov     [rsp+2F0h+var_2D0], 0; DWORD
0x18023c8df  lea     r8, ?_accessibilityKeyString@StartList@@0PAGA; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18023c8e6  mov     r15, 0FFFFFFFF80000001h
0x18023c8ed  mov     rdx, r15; hKey
0x18023c8f0  mov     rcx, r9; this
0x18023c8f3  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x18023c8f8  mov     ebx, eax
0x18023c8fa  test    eax, eax
0x18023c8fc  jz      short loc_18023C943
0x18023c8fe  lea     rsi, WPP_GLOBAL_Control
0x18023c905  mov     rcx, cs:WPP_GLOBAL_Control
0x18023c90c  cmp     rcx, rsi
0x18023c90f  jz      short loc_18023C92F
0x18023c911  test    byte ptr [rcx+1Ch], 8
0x18023c915  jz      short loc_18023C92F
0x18023c917  mov     edx, 29h ; ')'
0x18023c91c  mov     r9d, eax
0x18023c91f  lea     r8, WPP_0cfc691c390c3581aa6c7b8081e34e7b_Traceguids
0x18023c926  mov     rcx, [rcx+10h]
0x18023c92a  call    WPP_SF_d
0x18023c92f  test    ebx, ebx
0x18023c931  jle     short loc_18023C93C
0x18023c933  movzx   ebx, bx
0x18023c936  or      ebx, 80070000h
0x18023c93c  mov     eax, ebx
0x18023c93e  jmp     loc_18023CD03
0x18023c943  xorps   xmm0, xmm0
0x18023c946  movdqu  [rbp+1F0h+var_270], xmm0
0x18023c94b  mov     [rbp+1F0h+var_260], 0
0x18023c953  xorps   xmm1, xmm1
0x18023c956  movdqu  [rbp+1F0h+var_258], xmm1
0x18023c95b  mov     [rbp+1F0h+var_248], 0Ah
0x18023c962  mov     rax, [rsi]
0x18023c965  mov     qword ptr [rsp+2F0h+var_2B0], rax
0x18023c96a  test    rax, rax
0x18023c96d  jz      short loc_18023C99E
0x18023c96f  lea     rdx, [rsp+2F0h+var_2B0]
0x18023c974  call    ?GetNext@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEBAAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@2@AEAPEAU__POSITION@@@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::GetNext(__POSITION * &)
0x18023c979  mov     rbx, rax
0x18023c97c  mov     rcx, [rax]; unsigned __int16 *
0x18023c97f  call    ?Open@Accommodation@@SAPEAV1@PEBG@Z; Accommodation::Open(ushort const *)
0x18023c984  cmp     dword ptr [rax+50h], 1
0x18023c988  jz      short loc_18023C996
0x18023c98a  mov     rdx, [rbx]
0x18023c98d  lea     rcx, [rbp+1F0h+var_270]
0x18023c991  call    ?AddTail@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAPEAU__POSITION@@PEBG@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::AddTail(ushort const *)
0x18023c996  cmp     qword ptr [rsp+2F0h+var_2B0], 0
0x18023c99c  jnz     short loc_18023C96F
0x18023c99e  lea     rcx, [rsp+2F0h+var_290]
0x18023c9a3  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18023c9a8  nop
0x18023c9a9  lea     rdx, [rbp+1F0h+var_270]
0x18023c9ad  lea     rcx, [rsp+2F0h+var_290]
0x18023c9b2  call    ?BuildConfigString@StartList@@SAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEBV?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@3@@Z; StartList::BuildConfigString(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> const &)
0x18023c9b7  mov     rbx, [rsp+2F0h+var_290]
0x18023c9bc  mov     r8, rbx; unsigned __int16 *
0x18023c9bf  lea     rdx, ?_configuration@StartList@@0PAGA; "Configuration"
0x18023c9c6  mov     rcx, rdi; this
0x18023c9c9  call    ?SetStringValue@CRegKey@ATL@@QEAAJPEBG0K@Z; ATL::CRegKey::SetStringValue(ushort const *,ushort const *,ulong)
0x18023c9ce  mov     edi, eax
0x18023c9d0  test    eax, eax
0x18023c9d2  jz      short loc_18023CA1B
0x18023c9d4  lea     rsi, WPP_GLOBAL_Control
0x18023c9db  mov     rcx, cs:WPP_GLOBAL_Control
0x18023c9e2  cmp     rcx, rsi
0x18023c9e5  jz      short loc_18023CA05
0x18023c9e7  test    byte ptr [rcx+1Ch], 8
0x18023c9eb  jz      short loc_18023CA05
0x18023c9ed  mov     edx, 2Ah ; '*'
0x18023c9f2  mov     r9d, eax
0x18023c9f5  lea     r8, WPP_0cfc691c390c3581aa6c7b8081e34e7b_Traceguids
0x18023c9fc  mov     rcx, [rcx+10h]
0x18023ca00  call    WPP_SF_d
0x18023ca05  test    edi, edi
0x18023ca07  jle     loc_18023CA9F
0x18023ca0d  movzx   edi, di
0x18023ca10  or      edi, 80070000h
0x18023ca16  jmp     loc_18023CA9F
0x18023ca1b  mov     [rsp+2F0h+var_288], 0
0x18023ca24  mov     [rsp+2F0h+var_280], 0
0x18023ca2d  mov     [rsp+2F0h+var_278], 0
0x18023ca36  mov     r9d, 20019h; unsigned int
0x18023ca3c  lea     r8, aSoftwareMicros_73; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18023ca43  mov     rdx, r15; hKey
0x18023ca46  lea     rcx, [rsp+2F0h+var_288]; this
0x18023ca4b  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18023ca50  mov     edi, eax
0x18023ca52  test    eax, eax
0x18023ca54  jz      short loc_18023CAAD
0x18023ca56  lea     rsi, WPP_GLOBAL_Control
0x18023ca5d  mov     rcx, cs:WPP_GLOBAL_Control
0x18023ca64  cmp     rcx, rsi
0x18023ca67  jz      short loc_18023CA87
0x18023ca69  test    byte ptr [rcx+1Ch], 8
0x18023ca6d  jz      short loc_18023CA87
0x18023ca6f  mov     edx, 2Bh ; '+'
0x18023ca74  mov     r9d, eax
0x18023ca77  lea     r8, WPP_0cfc691c390c3581aa6c7b8081e34e7b_Traceguids
0x18023ca7e  mov     rcx, [rcx+10h]
0x18023ca82  call    WPP_SF_d
0x18023ca87  test    edi, edi
0x18023ca89  jle     short loc_18023CA94
0x18023ca8b  movzx   edi, di
0x18023ca8e  or      edi, 80070000h
0x18023ca94  lea     rcx, [rsp+2F0h+var_288]; this
0x18023ca99  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18023ca9e  nop
0x18023ca9f  lea     rcx, [rbx-18h]; this
0x18023caa3  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18023caa8  jmp     loc_18023CCF8
0x18023caad  xor     edx, edx; Val
0x18023caaf  mov     r8d, 208h; Size
0x18023cab5  lea     rcx, [rbp+1F0h+var_240]; void *
0x18023cab9  call    memset_0
0x18023cabe  mov     [rsp+2F0h+var_2B0], 104h
0x18023cac6  lea     r9, [rsp+2F0h+var_2B0]; unsigned int *
0x18023cacb  lea     r8, [rbp+1F0h+var_240]; unsigned __int16 *
0x18023cacf  lea     rdx, aStartup; "Startup"
0x18023cad6  lea     rcx, [rsp+2F0h+var_288]; this
0x18023cadb  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEBGPEAGPEAK@Z; ATL::CRegKey::QueryStringValue(ushort const *,ushort *,ulong *)
0x18023cae0  lea     rdx, [rbp+1F0h+var_240]
0x18023cae4  lea     rcx, [rsp+2F0h+lpFileName]
0x18023cae9  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18023caee  nop
0x18023caef  lea     rdx, [rbp+1F0h+var_240]
0x18023caf3  lea     rcx, [rsp+2F0h+var_2A0]
0x18023caf8  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18023cafd  nop
0x18023cafe  lea     rdx, [rbp+1F0h+var_240]
0x18023cb02  lea     rcx, [rsp+2F0h+var_2A8]
0x18023cb07  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18023cb0c  nop
0x18023cb0d  mov     r8d, 17h
0x18023cb13  lea     rdx, aOnScreenKeyboa; "\\On-Screen Keyboard.lnk"
0x18023cb1a  lea     rcx, [rsp+2F0h+lpFileName]
0x18023cb1f  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x18023cb24  mov     r8d, 0Dh
0x18023cb2a  lea     rdx, aNarratorLnk; "\\Narrator.lnk"
0x18023cb31  lea     rcx, [rsp+2F0h+var_2A0]
0x18023cb36  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x18023cb3b  mov     r8d, 0Eh
0x18023cb41  lea     rdx, aMagnifierLnk; "\\Magnifier.lnk"
0x18023cb48  lea     rcx, [rsp+2F0h+var_2A8]
0x18023cb4d  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x18023cb52  lea     r15, [rbx-18h]
0x18023cb56  mov     rdi, [r14]
0x18023cb59  add     rdi, 0FFFFFFFFFFFFFFE8h
0x18023cb5d  cmp     r15, rdi
0x18023cb60  jz      short loc_18023CB9B
0x18023cb62  cmp     dword ptr [rdi+10h], 0
0x18023cb66  jl      short loc_18023CB8C
0x18023cb68  mov     rax, [rdi]
0x18023cb6b  cmp     [r15], rax
0x18023cb6e  jnz     short loc_18023CB8C
0x18023cb70  mov     rcx, r15
0x18023cb73  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x18023cb78  mov     rbx, rax
0x18023cb7b  mov     rcx, rdi; this
0x18023cb7e  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18023cb83  lea     rax, [rbx+18h]
0x18023cb87  mov     [r14], rax
0x18023cb8a  jmp     short loc_18023CB9B
0x18023cb8c  mov     r8d, [rbx-10h]
0x18023cb90  mov     rdx, rbx
0x18023cb93  mov     rcx, r14
0x18023cb96  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18023cb9b  mov     rcx, [rsp+2F0h+lpFileName]; lpFileName
0x18023cba0  call    cs:__imp_GetFileAttributesW
0x18023cba7  nop     dword ptr [rax+rax+00h]
0x18023cbac  mov     bl, 10h
0x18023cbae  lea     rsi, WPP_GLOBAL_Control
0x18023cbb5  or      edi, 0FFFFFFFFh
0x18023cbb8  cmp     eax, edi
0x18023cbba  jz      short loc_18023CC01
0x18023cbbc  mov     r8d, 4
0x18023cbc2  lea     rdx, aOsk_0; ",osk"
0x18023cbc9  mov     rcx, r14
0x18023cbcc  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x18023cbd1  mov     rcx, [rsp+2F0h+lpFileName]; lpFileName
0x18023cbd6  call    cs:__imp_DeleteFileW
0x18023cbdd  nop     dword ptr [rax+rax+00h]
0x18023cbe2  mov     rcx, cs:WPP_GLOBAL_Control
0x18023cbe9  cmp     rcx, rsi
0x18023cbec  jz      short loc_18023CC01
0x18023cbee  test    [rcx+1Ch], bl
0x18023cbf1  jz      short loc_18023CC01
0x18023cbf3  mov     edx, 2Ch ; ','
0x18023cbf8  mov     rcx, [rcx+10h]
0x18023cbfc  call    WPP_SF_
0x18023cc01  mov     rcx, [rsp+2F0h+var_2A0]; lpFileName
0x18023cc06  call    cs:__imp_GetFileAttributesW
0x18023cc0d  nop     dword ptr [rax+rax+00h]
0x18023cc12  cmp     eax, edi
0x18023cc14  jz      short loc_18023CC5B
0x18023cc16  mov     r8d, 9
0x18023cc1c  lea     rdx, aNarrator_0; ",Narrator"
0x18023cc23  mov     rcx, r14
0x18023cc26  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x18023cc2b  mov     rcx, [rsp+2F0h+var_2A0]; lpFileName
0x18023cc30  call    cs:__imp_DeleteFileW
0x18023cc37  nop     dword ptr [rax+rax+00h]
0x18023cc3c  mov     rcx, cs:WPP_GLOBAL_Control
0x18023cc43  cmp     rcx, rsi
0x18023cc46  jz      short loc_18023CC5B
0x18023cc48  test    [rcx+1Ch], bl
0x18023cc4b  jz      short loc_18023CC5B
0x18023cc4d  mov     edx, 2Dh ; '-'
0x18023cc52  mov     rcx, [rcx+10h]
0x18023cc56  call    WPP_SF_
0x18023cc5b  mov     rcx, [rsp+2F0h+var_2A8]; lpFileName
0x18023cc60  call    cs:__imp_GetFileAttributesW
0x18023cc67  nop     dword ptr [rax+rax+00h]
0x18023cc6c  cmp     eax, edi
0x18023cc6e  jz      short loc_18023CCB6
0x18023cc70  mov     r8d, 0Eh
0x18023cc76  lea     rdx, aMagnifierpane_0; ",magnifierpane"
0x18023cc7d  mov     rcx, r14
0x18023cc80  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x18023cc85  mov     rcx, [rsp+2F0h+var_2A8]; lpFileName
0x18023cc8a  call    cs:__imp_DeleteFileW
0x18023cc91  nop     dword ptr [rax+rax+00h]
0x18023cc96  mov     rcx, cs:WPP_GLOBAL_Control
0x18023cc9d  cmp     rcx, rsi
0x18023cca0  jz      short loc_18023CCB6
0x18023cca2  test    [rcx+1Ch], bl
0x18023cca5  jz      short loc_18023CCB6
0x18023cca7  mov     edx, 2Eh ; '.'
0x18023ccac  mov     rcx, [rcx+10h]
0x18023ccb0  call    WPP_SF_
0x18023ccb5  nop
0x18023ccb6  mov     rcx, [rsp+2F0h+var_2A8]
0x18023ccbb  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18023ccbf  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18023ccc4  nop
0x18023ccc5  mov     rcx, [rsp+2F0h+var_2A0]
0x18023ccca  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18023ccce  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18023ccd3  nop
0x18023ccd4  mov     rcx, [rsp+2F0h+lpFileName]
0x18023ccd9  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18023ccdd  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18023cce2  nop
0x18023cce3  lea     rcx, [rsp+2F0h+var_288]; this
0x18023cce8  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18023cced  nop
0x18023ccee  mov     rcx, r15; this
0x18023ccf1  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18023ccf6  xor     edi, edi
0x18023ccf8  lea     rcx, [rbp+1F0h+var_270]
0x18023ccfc  call    ?RemoveAll@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAXXZ; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::RemoveAll(void)
0x18023cd01  mov     eax, edi
0x18023cd03  mov     rcx, [rbp+1F0h+var_30]
0x18023cd0a  xor     rcx, rsp; StackCookie
0x18023cd0d  call    __security_check_cookie
0x18023cd12  mov     rbx, [rsp+2F0h+arg_0]
0x18023cd1a  add     rsp, 2D0h
0x18023cd21  pop     r15
0x18023cd23  pop     r14
0x18023cd25  pop     rdi
0x18023cd26  pop     rsi
0x18023cd27  pop     rbp
0x18023cd28  retn
```
