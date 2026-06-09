# CTieringEngineApiServer::SetDesiredStorageTierClass(ushort *,ulong,_GUID *,ushort *,_STORAGE_TIER_CLASS)

- ea: `0x14003b070`
- end: `0x14003b4ee`
- name: `?SetDesiredStorageTierClass@CTieringEngineApiServer@@UEAAJPEAGKPEAU_GUID@@0W4_STORAGE_TIER_CLASS@@@Z`
- size: `1150`
- prototype: `__int64 __fastcall(CTieringEngineApiServer *this, unsigned __int16 *, char, struct _GUID *, unsigned __int16 *, enum _STORAGE_TIER_CLASS)`
- caller_count: `0`
- callee_count: `13`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callees

- `0x140002db0`
- `0x140004a40`
- `0x140005db4`
- `0x140009c08`
- `0x14000b0d0`
- `0x14000f2e4`
- `0x14000f5fc`
- `0x140017cd4`
- `0x14003b070`
- `0x14003baf8`
- `0x14003bbcc`
- `0x14003c7e8`
- `0x14003e9d0`

## import_xrefs

- `msvcrt!wcsstr` at `0x14003b149`
- `msvcrt!wcsstr` at `0x14003b149`
- `ntdll!RtlDoesNameContainWildCards` at `0x14003b21a`
- `ntdll!RtlDoesNameContainWildCards` at `0x14003b21a`
- `ntdll!RtlInitUnicodeString` at `0x14003b210`
- `ntdll!RtlInitUnicodeString` at `0x14003b210`
- `ntdll!RtlCompareMemory` at `0x14003b2fe`
- `ntdll!RtlCompareMemory` at `0x14003b2fe`
- `OLEAUT32!__imp_SysFreeString` at `0x14003b4cd`
- `OLEAUT32!__imp_SysFreeString` at `0x14003b4cd`
- `api-ms-win-core-path-l1-1-0!PathCchSkipRoot` at `0x14003b0f1`
- `api-ms-win-core-path-l1-1-0!PathCchSkipRoot` at `0x14003b0f1`

## pseudocode

```c
__int64 __fastcall CTieringEngineApiServer::SetDesiredStorageTierClass(
        CTieringEngineApiServer *this,
        unsigned __int16 *a2,
        char a3,
        struct _GUID *a4,
        unsigned __int16 *a5,
        enum _STORAGE_TIER_CLASS a6)
{
  char v6; // si
  HRESULT v10; // eax
  char v11; // bl
  _QWORD *v12; // rcx
  unsigned int v13; // ebx
  char DoesNameContainWildCards; // al
  unsigned int v15; // r15d
  int VolumePathByFilePath; // eax
  OLECHAR *v17; // rsi
  _QWORD *v18; // rcx
  int v19; // edx
  int v20; // r9d
  unsigned __int16 *v21; // r9
  int v22; // eax
  int v23; // r8d
  int v24; // r14d
  int TierInfo; // eax
  char v26; // r14
  int v27; // eax
  int v28; // r8d
  PCWSTR ppszRootEnd[2]; // [rsp+40h] [rbp-20h] BYREF
  BSTR bstrString; // [rsp+50h] [rbp-10h] BYREF
  CTieredVolume *v32; // [rsp+98h] [rbp+38h] BYREF

  v32 = 0;
  bstrString = 0;
  v6 = 1;
  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, &WPP_679b317bfb4035ff28fff86d621cec42_Traceguids);
    }
    v6 = 0;
  }
  ppszRootEnd[0] = 0;
  v10 = PathCchSkipRoot(a2, ppszRootEnd);
  v11 = v10;
  if ( v10 < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
LABEL_15:
        if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 1) != 0 && *((_BYTE *)v12 + 25) >= 2u )
          WPP_SF_Sd(v12[2], 44, (unsigned int)&WPP_679b317bfb4035ff28fff86d621cec42_Traceguids, (_DWORD)a2, v11);
        return (unsigned int)ATL::AtlHresultFromWin32(0x57u);
      }
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        45,
        (unsigned int)&WPP_58242705c75132cdab80b446e38b4c82_Traceguids,
        (_DWORD)a2,
        v10);
LABEL_14:
      v12 = WPP_GLOBAL_Control;
      goto LABEL_15;
    }
    return (unsigned int)ATL::AtlHresultFromWin32(0x57u);
  }
  if ( wcsstr(ppszRootEnd[0], L":") )
  {
    v11 = 87;
    goto LABEL_14;
  }
  if ( !v6 )
    return (unsigned int)ATL::AtlHresultFromWin32(0x57u);
  if ( (a3 & 1) != 0 )
  {
    v13 = -2147467263;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        45,
        (unsigned int)&WPP_679b317bfb4035ff28fff86d621cec42_Traceguids,
        (_DWORD)a2,
        1);
    }
    return v13;
  }
  *(_OWORD *)ppszRootEnd = 0;
  RtlInitUnicodeString((PUNICODE_STRING)ppszRootEnd, a2);
  DoesNameContainWildCards = RtlDoesNameContainWildCards(ppszRootEnd);
  v15 = DoesNameContainWildCards == 0 ? 0x10 : 0;
  VolumePathByFilePath = GetVolumePathByFilePath(a2, DoesNameContainWildCards != 0, &bstrString);
  v17 = bstrString;
  v13 = VolumePathByFilePath;
  if ( VolumePathByFilePath >= 0 )
  {
    VolumePathByFilePath = CTieringEngineLib::GetTieredVolumeByVolumeName_StrongValidation(
                             (CTieringEngineLib *)TieringEngineLibInstance,
                             bstrString,
                             &v32);
    v13 = VolumePathByFilePath;
    if ( VolumePathByFilePath >= 0 )
    {
      if ( !a4 || RtlCompareMemory(a4, &NullGuid, 0x10u) == 16 )
      {
        v24 = (int)a5;
        if ( a5 )
        {
          TierInfo = CTieredVolume::GetTierInfo(v32, a5, &a6, 0);
          v13 = TierInfo;
          if ( TierInfo < 0 )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_SSd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                49,
                (unsigned int)&WPP_679b317bfb4035ff28fff86d621cec42_Traceguids,
                v24,
                (__int64)v17,
                TierInfo);
            }
            goto LABEL_66;
          }
        }
      }
      else
      {
        v22 = CTieredVolume::GetTierInfo(v32, a4, &a6, v21);
        v13 = v22;
        if ( v22 < 0 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF__guid_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, v23, (_DWORD)a4, (__int64)v17, v22);
          }
          goto LABEL_66;
        }
      }
      v26 = a6;
      if ( a6 )
      {
        v27 = CTieredVolume::PinFile_ApiHandler(v32, a2, 0, v15, a6);
        v13 = v27;
        if ( v27 >= 0 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_SLSd(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, v28, (_DWORD)a2, v26, (__int64)v17, v27);
          }
          v13 = 0;
        }
        else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_SLSd(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, v28, (_DWORD)a2, v26, (__int64)v17, v27);
        }
        goto LABEL_66;
      }
      VolumePathByFilePath = CTieredVolume::ClearPinnedFile_ApiHandler(v32, a2, v15);
      v13 = VolumePathByFilePath;
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v19 = 50;
        goto LABEL_31;
      }
    }
    else
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v19 = 47;
        v20 = (int)v17;
        goto LABEL_32;
      }
    }
  }
  else
  {
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v19 = 46;
LABEL_31:
      v20 = (int)a2;
LABEL_32:
      WPP_SF_Sd(v18[2], v19, (unsigned int)&WPP_679b317bfb4035ff28fff86d621cec42_Traceguids, v20, VolumePathByFilePath);
    }
  }
LABEL_66:
  if ( v17 )
    SysFreeString(v17);
  return v13;
}

```

## disassembly

```asm
0x14003b070  mov     [rsp-28h+arg_0], rbx
0x14003b075  mov     [rsp-28h+arg_10], rsi
0x14003b07a  push    rbp
0x14003b07b  push    rdi
0x14003b07c  push    r13
0x14003b07e  push    r14
0x14003b080  push    r15
0x14003b082  mov     rbp, rsp
0x14003b085  sub     rsp, 60h
0x14003b089  mov     [rbp+arg_8], 0
0x14003b091  mov     r13b, 1
0x14003b094  mov     [rbp+bstrString], 0
0x14003b09c  mov     sil, r13b
0x14003b09f  lea     rax, WPP_GLOBAL_Control
0x14003b0a6  mov     r14, r9
0x14003b0a9  mov     r15d, r8d
0x14003b0ac  mov     rdi, rdx
0x14003b0af  test    rdx, rdx
0x14003b0b2  jnz     short loc_14003B0E2
0x14003b0b4  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b0bb  cmp     rcx, rax
0x14003b0be  jz      short loc_14003B0DF
0x14003b0c0  test    [rcx+1Ch], r13b
0x14003b0c4  jz      short loc_14003B0DF
0x14003b0c6  cmp     byte ptr [rcx+19h], 3
0x14003b0ca  jb      short loc_14003B0DF
0x14003b0cc  mov     rcx, [rcx+10h]
0x14003b0d0  lea     edx, [rdi+2Bh]
0x14003b0d3  lea     r8, WPP_679b317bfb4035ff28fff86d621cec42_Traceguids
0x14003b0da  call    WPP_SF_
0x14003b0df  xor     sil, sil
0x14003b0e2  lea     rdx, [rbp+ppszRootEnd]; ppszRootEnd
0x14003b0e6  mov     [rbp+ppszRootEnd], 0
0x14003b0ee  mov     rcx, rdi; pszPath
0x14003b0f1  call    cs:__imp_PathCchSkipRoot
0x14003b0f7  mov     ebx, eax
0x14003b0f9  test    eax, eax
0x14003b0fb  jns     short loc_14003B13E
0x14003b0fd  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b104  lea     r15, WPP_GLOBAL_Control
0x14003b10b  cmp     rcx, r15
0x14003b10e  jz      loc_14003B19B
0x14003b114  test    [rcx+1Ch], r13b
0x14003b118  jz      short loc_14003B167
0x14003b11a  cmp     byte ptr [rcx+19h], 2
0x14003b11e  jb      short loc_14003B167
0x14003b120  mov     rcx, [rcx+10h]
0x14003b124  lea     r8, WPP_58242705c75132cdab80b446e38b4c82_Traceguids
0x14003b12b  mov     edx, 2Dh ; '-'
0x14003b130  mov     [rsp+60h+var_40], eax
0x14003b134  mov     r9, rdi
0x14003b137  call    WPP_SF_Sd
0x14003b13c  jmp     short loc_14003B160
0x14003b13e  mov     rcx, [rbp+ppszRootEnd]; Str
0x14003b142  lea     rdx, SubStr; ":"
0x14003b149  call    cs:__imp_wcsstr
0x14003b14f  test    rax, rax
0x14003b152  jz      short loc_14003B196
0x14003b154  mov     ebx, 80070057h
0x14003b159  lea     r15, WPP_GLOBAL_Control
0x14003b160  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b167  cmp     rcx, r15
0x14003b16a  jz      short loc_14003B19B
0x14003b16c  test    [rcx+1Ch], r13b
0x14003b170  jz      short loc_14003B19B
0x14003b172  cmp     byte ptr [rcx+19h], 2
0x14003b176  jb      short loc_14003B19B
0x14003b178  mov     rcx, [rcx+10h]
0x14003b17c  lea     r8, WPP_679b317bfb4035ff28fff86d621cec42_Traceguids
0x14003b183  mov     edx, 2Ch ; ','
0x14003b188  mov     [rsp+60h+var_40], ebx
0x14003b18c  mov     r9, rdi
0x14003b18f  call    WPP_SF_Sd
0x14003b194  jmp     short loc_14003B19B
0x14003b196  test    sil, sil
0x14003b199  jnz     short loc_14003B1AC
0x14003b19b  mov     ecx, 57h ; 'W'; unsigned int
0x14003b1a0  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x14003b1a5  mov     ebx, eax
0x14003b1a7  jmp     loc_14003B4D3
0x14003b1ac  test    r13b, r15b
0x14003b1af  jz      short loc_14003B202
0x14003b1b1  mov     ebx, 80004001h
0x14003b1b6  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b1bd  lea     r15, WPP_GLOBAL_Control
0x14003b1c4  cmp     rcx, r15
0x14003b1c7  jz      loc_14003B4D3
0x14003b1cd  test    [rcx+1Ch], r13b
0x14003b1d1  jz      loc_14003B4D3
0x14003b1d7  cmp     byte ptr [rcx+19h], 2
0x14003b1db  jb      loc_14003B4D3
0x14003b1e1  mov     rcx, [rcx+10h]
0x14003b1e5  lea     r8, WPP_679b317bfb4035ff28fff86d621cec42_Traceguids
0x14003b1ec  mov     edx, 2Dh ; '-'
0x14003b1f1  mov     [rsp+60h+var_40], ebx
0x14003b1f5  mov     r9, rdi
0x14003b1f8  call    WPP_SF_Sd
0x14003b1fd  jmp     loc_14003B4D3
0x14003b202  xorps   xmm0, xmm0
0x14003b205  lea     rcx, [rbp+ppszRootEnd]; DestinationString
0x14003b209  mov     rdx, rdi; SourceString
0x14003b20c  movups  xmmword ptr [rbp+ppszRootEnd], xmm0
0x14003b210  call    cs:__imp_RtlInitUnicodeString
0x14003b216  lea     rcx, [rbp+ppszRootEnd]
0x14003b21a  call    cs:__imp_RtlDoesNameContainWildCards
0x14003b220  mov     cl, al
0x14003b222  lea     r8, [rbp+bstrString]; unsigned __int16 **
0x14003b226  neg     cl
0x14003b228  mov     rcx, rdi; lpszFileName
0x14003b22b  sbb     r15d, r15d
0x14003b22e  xor     edx, edx
0x14003b230  not     r15d
0x14003b233  and     r15d, 10h
0x14003b237  test    al, al
0x14003b239  setnz   dl; int
0x14003b23c  call    ?GetVolumePathByFilePath@@YAJPEAGHPEAPEAG@Z; GetVolumePathByFilePath(ushort *,int,ushort * *)
0x14003b241  mov     rsi, [rbp+bstrString]
0x14003b245  mov     ebx, eax
0x14003b247  test    eax, eax
0x14003b249  jns     short loc_14003B297
0x14003b24b  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b252  lea     r15, WPP_GLOBAL_Control
0x14003b259  cmp     rcx, r15
0x14003b25c  jz      loc_14003B4C5
0x14003b262  test    [rcx+1Ch], r13b
0x14003b266  jz      loc_14003B4C5
0x14003b26c  cmp     byte ptr [rcx+19h], 2
0x14003b270  jb      loc_14003B4C5
0x14003b276  mov     edx, 2Eh ; '.'
0x14003b27b  mov     r9, rdi
0x14003b27e  mov     rcx, [rcx+10h]
0x14003b282  lea     r8, WPP_679b317bfb4035ff28fff86d621cec42_Traceguids
0x14003b289  mov     [rsp+60h+var_40], eax
0x14003b28d  call    WPP_SF_Sd
0x14003b292  jmp     loc_14003B4C5
0x14003b297  mov     rcx, cs:?TieringEngineLibInstance@@3PEAVCTieringEngineLib@@EA; this
0x14003b29e  lea     r8, [rbp+arg_8]; struct CTieredVolume **
0x14003b2a2  mov     rdx, rsi; unsigned __int16 *
0x14003b2a5  call    ?GetTieredVolumeByVolumeName_StrongValidation@CTieringEngineLib@@QEAAJPEAGPEAPEAVCTieredVolume@@@Z; CTieringEngineLib::GetTieredVolumeByVolumeName_StrongValidation(ushort *,CTieredVolume * *)
0x14003b2aa  mov     ebx, eax
0x14003b2ac  test    eax, eax
0x14003b2ae  jns     short loc_14003B2E5
0x14003b2b0  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b2b7  lea     r15, WPP_GLOBAL_Control
0x14003b2be  cmp     rcx, r15
0x14003b2c1  jz      loc_14003B4C5
0x14003b2c7  test    [rcx+1Ch], r13b
0x14003b2cb  jz      loc_14003B4C5
0x14003b2d1  cmp     byte ptr [rcx+19h], 2
0x14003b2d5  jb      loc_14003B4C5
0x14003b2db  mov     edx, 2Fh ; '/'
0x14003b2e0  mov     r9, rsi
0x14003b2e3  jmp     short loc_14003B27E
0x14003b2e5  test    r14, r14
0x14003b2e8  jz      loc_14003B36E
0x14003b2ee  mov     r8d, 10h; Length
0x14003b2f4  lea     rdx, ?NullGuid@@3U_GUID@@A; Source2
0x14003b2fb  mov     rcx, r14; Source1
0x14003b2fe  call    cs:__imp_RtlCompareMemory
0x14003b304  cmp     rax, 10h
0x14003b308  jz      short loc_14003B36E
0x14003b30a  mov     rcx, [rbp+arg_8]; this
0x14003b30e  lea     r8, [rbp+arg_28]; enum _STORAGE_TIER_CLASS *
0x14003b312  mov     rdx, r14; struct _GUID *
0x14003b315  call    ?GetTierInfo@CTieredVolume@@QEAAJPEBU_GUID@@PEAW4_STORAGE_TIER_CLASS@@PEAG@Z; CTieredVolume::GetTierInfo(_GUID const *,_STORAGE_TIER_CLASS *,ushort *)
0x14003b31a  mov     ebx, eax
0x14003b31c  test    eax, eax
0x14003b31e  jns     loc_14003B3E1
0x14003b324  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b32b  lea     r15, WPP_GLOBAL_Control
0x14003b332  cmp     rcx, r15
0x14003b335  jz      loc_14003B4C5
0x14003b33b  test    [rcx+1Ch], r13b
0x14003b33f  jz      loc_14003B4C5
0x14003b345  cmp     byte ptr [rcx+19h], 2
0x14003b349  jb      loc_14003B4C5
0x14003b34f  mov     rcx, [rcx+10h]
0x14003b353  mov     edx, 30h ; '0'
0x14003b358  mov     dword ptr [rsp+60h+var_38], eax
0x14003b35c  mov     r9, r14
0x14003b35f  mov     qword ptr [rsp+60h+var_40], rsi
0x14003b364  call    WPP_SF__guid_Sd
0x14003b369  jmp     loc_14003B4C5
0x14003b36e  mov     r14, [rbp+arg_20]
0x14003b372  test    r14, r14
0x14003b375  jz      short loc_14003B3E1
0x14003b377  mov     rcx, [rbp+arg_8]; this
0x14003b37b  lea     r8, [rbp+arg_28]; enum _STORAGE_TIER_CLASS *
0x14003b37f  xor     r9d, r9d; struct _GUID *
0x14003b382  mov     rdx, r14; unsigned __int16 *
0x14003b385  call    ?GetTierInfo@CTieredVolume@@QEAAJPEAGPEAW4_STORAGE_TIER_CLASS@@PEAU_GUID@@@Z; CTieredVolume::GetTierInfo(ushort *,_STORAGE_TIER_CLASS *,_GUID *)
0x14003b38a  mov     ebx, eax
0x14003b38c  test    eax, eax
0x14003b38e  jns     short loc_14003B3E1
0x14003b390  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b397  lea     r15, WPP_GLOBAL_Control
0x14003b39e  cmp     rcx, r15
0x14003b3a1  jz      loc_14003B4C5
0x14003b3a7  test    [rcx+1Ch], r13b
0x14003b3ab  jz      loc_14003B4C5
0x14003b3b1  cmp     byte ptr [rcx+19h], 2
0x14003b3b5  jb      loc_14003B4C5
0x14003b3bb  mov     rcx, [rcx+10h]
0x14003b3bf  lea     r8, WPP_679b317bfb4035ff28fff86d621cec42_Traceguids
0x14003b3c6  mov     dword ptr [rsp+60h+var_38], eax
0x14003b3ca  mov     edx, 31h ; '1'
0x14003b3cf  mov     r9, r14
0x14003b3d2  mov     qword ptr [rsp+60h+var_40], rsi
0x14003b3d7  call    WPP_SF_SSd
0x14003b3dc  jmp     loc_14003B4C5
0x14003b3e1  mov     r14d, [rbp+arg_28]
0x14003b3e5  mov     rdx, rdi; lpFileName
0x14003b3e8  mov     rcx, [rbp+arg_8]; this
0x14003b3ec  test    r14d, r14d
0x14003b3ef  jnz     short loc_14003B42F
0x14003b3f1  mov     r8d, r15d; unsigned int
0x14003b3f4  call    ?ClearPinnedFile_ApiHandler@CTieredVolume@@QEAAJPEAGK@Z; CTieredVolume::ClearPinnedFile_ApiHandler(ushort *,ulong)
0x14003b3f9  mov     ebx, eax
0x14003b3fb  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b402  lea     r15, WPP_GLOBAL_Control
0x14003b409  cmp     rcx, r15
0x14003b40c  jz      loc_14003B4C5
0x14003b412  test    [rcx+1Ch], r13b
0x14003b416  jz      loc_14003B4C5
0x14003b41c  cmp     byte ptr [rcx+19h], 2
0x14003b420  jb      loc_14003B4C5
0x14003b426  lea     edx, [r14+32h]
0x14003b42a  jmp     loc_14003B27B
0x14003b42f  mov     r9d, r15d; unsigned int
0x14003b432  mov     [rsp+60h+var_40], r14d; enum _STORAGE_TIER_CLASS
0x14003b437  xor     r8d, r8d; struct TE_FILE_ID_128 *
0x14003b43a  call    ?PinFile_ApiHandler@CTieredVolume@@QEAAJPEAGPEAUTE_FILE_ID_128@@KW4_STORAGE_TIER_CLASS@@@Z; CTieredVolume::PinFile_ApiHandler(ushort *,TE_FILE_ID_128 *,ulong,_STORAGE_TIER_CLASS)
0x14003b43f  mov     ebx, eax
0x14003b441  test    eax, eax
0x14003b443  jns     short loc_14003B485
0x14003b445  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b44c  lea     r15, WPP_GLOBAL_Control
0x14003b453  cmp     rcx, r15
0x14003b456  jz      short loc_14003B4C5
0x14003b458  test    [rcx+1Ch], r13b
0x14003b45c  jz      short loc_14003B4C5
0x14003b45e  cmp     byte ptr [rcx+19h], 2
0x14003b462  jb      short loc_14003B4C5
0x14003b464  mov     rcx, [rcx+10h]
0x14003b468  mov     edx, 33h ; '3'
0x14003b46d  mov     [rsp+60h+var_30], eax
0x14003b471  mov     r9, rdi
0x14003b474  mov     [rsp+60h+var_38], rsi
0x14003b479  mov     [rsp+60h+var_40], r14d
0x14003b47e  call    WPP_SF_SLSd
0x14003b483  jmp     short loc_14003B4C5
0x14003b485  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b48c  lea     r15, WPP_GLOBAL_Control
0x14003b493  cmp     rcx, r15
0x14003b496  jz      short loc_14003B4C3
0x14003b498  test    [rcx+1Ch], r13b
0x14003b49c  jz      short loc_14003B4C3
0x14003b49e  cmp     byte ptr [rcx+19h], 2
0x14003b4a2  jb      short loc_14003B4C3
0x14003b4a4  mov     rcx, [rcx+10h]
0x14003b4a8  mov     edx, 34h ; '4'
0x14003b4ad  mov     [rsp+60h+var_30], eax
0x14003b4b1  mov     r9, rdi
0x14003b4b4  mov     [rsp+60h+var_38], rsi
0x14003b4b9  mov     [rsp+60h+var_40], r14d
0x14003b4be  call    WPP_SF_SLSd
0x14003b4c3  xor     ebx, ebx
0x14003b4c5  test    rsi, rsi
0x14003b4c8  jz      short loc_14003B4D3
0x14003b4ca  mov     rcx, rsi; bstrString
0x14003b4cd  call    cs:__imp_SysFreeString
0x14003b4d3  lea     r11, [rsp+60h+var_s0]
0x14003b4d8  mov     eax, ebx
0x14003b4da  mov     rbx, [r11+30h]
0x14003b4de  mov     rsi, [r11+40h]
0x14003b4e2  mov     rsp, r11
0x14003b4e5  pop     r15
0x14003b4e7  pop     r14
0x14003b4e9  pop     r13
0x14003b4eb  pop     rdi
0x14003b4ec  pop     rbp
0x14003b4ed  retn
```
