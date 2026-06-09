# CTieringEngineApiServer::PinFile(ushort *,_FILE_ID_128 *,_GUID *,ushort *,_STORAGE_TIER_CLASS)

- ea: `0x14003aa90`
- end: `0x14003ad68`
- name: `?PinFile@CTieringEngineApiServer@@UEAAJPEAGPEAU_FILE_ID_128@@PEAU_GUID@@0W4_STORAGE_TIER_CLASS@@@Z`
- size: `728`
- prototype: `__int64 __fastcall(CTieringEngineApiServer *this, unsigned __int16 *, struct _FILE_ID_128 *, struct _GUID *, unsigned __int16 *, enum _STORAGE_TIER_CLASS)`
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140002db0`
- `0x140004a40`
- `0x140005db4`
- `0x140009c08`
- `0x14000f2e4`
- `0x14000f5fc`
- `0x140017cd4`
- `0x14003aa90`
- `0x14003bbcc`
- `0x14003bc60`
- `0x14003e9d0`

## import_xrefs

- `ntdll!RtlCompareMemory` at `0x14003ab17`
- `ntdll!RtlCompareMemory` at `0x14003abe9`
- `ntdll!RtlCompareMemory` at `0x14003ab17`
- `ntdll!RtlCompareMemory` at `0x14003abe9`

## pseudocode

```c
__int64 __fastcall CTieringEngineApiServer::PinFile(
        CTieringEngineApiServer *this,
        unsigned __int16 *a2,
        struct _FILE_ID_128 *a3,
        struct _GUID *a4,
        unsigned __int16 *a5,
        enum _STORAGE_TIER_CLASS a6)
{
  char v9; // bl
  _QWORD *v10; // rcx
  enum _STORAGE_TIER_CLASS v11; // ebp
  int TieredVolumeByVolumeName_StrongValidation; // eax
  unsigned int v14; // ebx
  unsigned __int16 *v15; // r9
  int v16; // r8d
  _QWORD *v17; // rcx
  int v18; // edx
  int TierInfo; // eax
  int v20; // edx
  CTieredVolume *v21; // [rsp+90h] [rbp+18h] BYREF

  v21 = 0;
  v9 = 1;
  if ( a3 )
  {
    v10 = WPP_GLOBAL_Control;
  }
  else
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_679b317bfb4035ff28fff86d621cec42_Traceguids);
      v10 = WPP_GLOBAL_Control;
    }
    v9 = 0;
  }
  v11 = a6;
  if ( a4 )
  {
    if ( RtlCompareMemory(a4, &NullGuid, 0x10u) != 16 )
      goto LABEL_17;
    v10 = WPP_GLOBAL_Control;
  }
  if ( !a5 && v11 == StorageTierClassUnspecified )
  {
    if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 1) != 0 && *((_BYTE *)v10 + 25) >= 3u )
      WPP_SF_(v10[2], 37, &WPP_679b317bfb4035ff28fff86d621cec42_Traceguids);
    return ATL::AtlHresultFromWin32(0x57u);
  }
LABEL_17:
  if ( !v9 )
    return ATL::AtlHresultFromWin32(0x57u);
  TieredVolumeByVolumeName_StrongValidation = CTieringEngineLib::GetTieredVolumeByVolumeName_StrongValidation(
                                                (CTieringEngineLib *)TieringEngineLibInstance,
                                                a2,
                                                &v21);
  v14 = TieredVolumeByVolumeName_StrongValidation;
  if ( TieredVolumeByVolumeName_StrongValidation < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        38,
        (unsigned int)&WPP_679b317bfb4035ff28fff86d621cec42_Traceguids,
        (_DWORD)a2,
        TieredVolumeByVolumeName_StrongValidation);
    }
    return v14;
  }
  if ( !a4 || RtlCompareMemory(a4, &NullGuid, 0x10u) == 16 )
  {
    if ( !a5 )
      goto LABEL_38;
    TierInfo = CTieredVolume::GetTierInfo(v21, a5, &a6, 0);
    v14 = TierInfo;
    if ( TierInfo < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_SSd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          40,
          (unsigned int)&WPP_679b317bfb4035ff28fff86d621cec42_Traceguids,
          (_DWORD)a5,
          (__int64)a2,
          TierInfo);
      }
      return v14;
    }
  }
  else
  {
    v14 = CTieredVolume::GetTierInfo(v21, a4, &a6, v15);
    if ( (v14 & 0x80000000) != 0 )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return v14;
      }
      v18 = 39;
      goto LABEL_43;
    }
  }
  v11 = a6;
LABEL_38:
  v14 = CTieredVolume::PinFile_ApiHandler(v21, 0, (struct TE_FILE_ID_128 *)a3, 0, v11);
  if ( (v14 & 0x80000000) == 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_iiLSd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v20,
        v16,
        *(_QWORD *)&a3->Identifier[8],
        *(_QWORD *)a3->Identifier,
        v11,
        (__int64)a2,
        v14);
    }
    return v14;
  }
  v17 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v18 = 41;
LABEL_43:
    WPP_SF__guid_Sd(v17[2], v18, v16, (_DWORD)a4, (__int64)a2, v14);
  }
  return v14;
}

```

## disassembly

```asm
0x14003aa90  mov     rax, rsp
0x14003aa93  push    rbx
0x14003aa94  push    rbp
0x14003aa95  push    rsi
0x14003aa96  push    rdi
0x14003aa97  push    r13
0x14003aa99  push    r15
0x14003aa9b  sub     rsp, 48h
0x14003aa9f  mov     qword ptr [rax+18h], 0
0x14003aaa7  mov     rdi, r9
0x14003aaaa  lea     r13, WPP_GLOBAL_Control
0x14003aab1  mov     r15, r8
0x14003aab4  mov     rsi, rdx
0x14003aab7  mov     bl, 1
0x14003aab9  test    r8, r8
0x14003aabc  jnz     short loc_14003AAF4
0x14003aabe  mov     rcx, cs:WPP_GLOBAL_Control
0x14003aac5  cmp     rcx, r13
0x14003aac8  jz      short loc_14003AAF0
0x14003aaca  test    [rcx+1Ch], bl
0x14003aacd  jz      short loc_14003AAF0
0x14003aacf  cmp     byte ptr [rcx+19h], 3
0x14003aad3  jb      short loc_14003AAF0
0x14003aad5  mov     rcx, [rcx+10h]
0x14003aad9  lea     edx, [r8+24h]
0x14003aadd  lea     r8, WPP_679b317bfb4035ff28fff86d621cec42_Traceguids
0x14003aae4  call    WPP_SF_
0x14003aae9  mov     rcx, cs:WPP_GLOBAL_Control
0x14003aaf0  xor     bl, bl
0x14003aaf2  jmp     short loc_14003AAFB
0x14003aaf4  mov     rcx, cs:WPP_GLOBAL_Control
0x14003aafb  mov     ebp, [rsp+78h+arg_28]
0x14003ab02  test    rdi, rdi
0x14003ab05  jz      short loc_14003AB2A
0x14003ab07  mov     r8d, 10h; Length
0x14003ab0d  lea     rdx, ?NullGuid@@3U_GUID@@A; Source2
0x14003ab14  mov     rcx, rdi; Source1
0x14003ab17  call    cs:__imp_RtlCompareMemory
0x14003ab1d  cmp     rax, 10h
0x14003ab21  jnz     short loc_14003AB5F
0x14003ab23  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ab2a  cmp     [rsp+78h+arg_20], 0
0x14003ab33  jnz     short loc_14003AB5F
0x14003ab35  test    ebp, ebp
0x14003ab37  jnz     short loc_14003AB5F
0x14003ab39  cmp     rcx, r13
0x14003ab3c  jz      short loc_14003AB63
0x14003ab3e  test    byte ptr [rcx+1Ch], 1
0x14003ab42  jz      short loc_14003AB63
0x14003ab44  cmp     byte ptr [rcx+19h], 3
0x14003ab48  jb      short loc_14003AB63
0x14003ab4a  mov     rcx, [rcx+10h]
0x14003ab4e  lea     edx, [rbp+25h]
0x14003ab51  lea     r8, WPP_679b317bfb4035ff28fff86d621cec42_Traceguids
0x14003ab58  call    WPP_SF_
0x14003ab5d  jmp     short loc_14003AB63
0x14003ab5f  test    bl, bl
0x14003ab61  jnz     short loc_14003AB72
0x14003ab63  mov     ecx, 57h ; 'W'; unsigned int
0x14003ab68  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x14003ab6d  jmp     loc_14003AD5B
0x14003ab72  mov     rcx, cs:?TieringEngineLibInstance@@3PEAVCTieringEngineLib@@EA; this
0x14003ab79  lea     r8, [rsp+78h+arg_10]; struct CTieredVolume **
0x14003ab81  mov     rdx, rsi; unsigned __int16 *
0x14003ab84  call    ?GetTieredVolumeByVolumeName_StrongValidation@CTieringEngineLib@@QEAAJPEAGPEAPEAVCTieredVolume@@@Z; CTieringEngineLib::GetTieredVolumeByVolumeName_StrongValidation(ushort *,CTieredVolume * *)
0x14003ab89  mov     ebx, eax
0x14003ab8b  test    eax, eax
0x14003ab8d  jns     short loc_14003ABD4
0x14003ab8f  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ab96  cmp     rcx, r13
0x14003ab99  jz      loc_14003AD59
0x14003ab9f  test    byte ptr [rcx+1Ch], 1
0x14003aba3  jz      loc_14003AD59
0x14003aba9  cmp     byte ptr [rcx+19h], 2
0x14003abad  jb      loc_14003AD59
0x14003abb3  mov     rcx, [rcx+10h]
0x14003abb7  lea     r8, WPP_679b317bfb4035ff28fff86d621cec42_Traceguids
0x14003abbe  mov     edx, 26h ; '&'
0x14003abc3  mov     [rsp+78h+var_58], eax
0x14003abc7  mov     r9, rsi
0x14003abca  call    WPP_SF_Sd
0x14003abcf  jmp     loc_14003AD59
0x14003abd4  test    rdi, rdi
0x14003abd7  jz      short loc_14003AC45
0x14003abd9  mov     r8d, 10h; Length
0x14003abdf  lea     rdx, ?NullGuid@@3U_GUID@@A; Source2
0x14003abe6  mov     rcx, rdi; Source1
0x14003abe9  call    cs:__imp_RtlCompareMemory
0x14003abef  cmp     rax, 10h
0x14003abf3  jz      short loc_14003AC45
0x14003abf5  mov     rcx, [rsp+78h+arg_10]; this
0x14003abfd  lea     r8, [rsp+78h+arg_28]; enum _STORAGE_TIER_CLASS *
0x14003ac05  mov     rdx, rdi; struct _GUID *
0x14003ac08  call    ?GetTierInfo@CTieredVolume@@QEAAJPEBU_GUID@@PEAW4_STORAGE_TIER_CLASS@@PEAG@Z; CTieredVolume::GetTierInfo(_GUID const *,_STORAGE_TIER_CLASS *,ushort *)
0x14003ac0d  mov     ebx, eax
0x14003ac0f  test    eax, eax
0x14003ac11  jns     loc_14003ACC5
0x14003ac17  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ac1e  cmp     rcx, r13
0x14003ac21  jz      loc_14003AD59
0x14003ac27  test    byte ptr [rcx+1Ch], 1
0x14003ac2b  jz      loc_14003AD59
0x14003ac31  cmp     byte ptr [rcx+19h], 2
0x14003ac35  jb      loc_14003AD59
0x14003ac3b  mov     edx, 27h ; '''
0x14003ac40  jmp     loc_14003AD08
0x14003ac45  cmp     [rsp+78h+arg_20], 0
0x14003ac4e  jz      short loc_14003ACCC
0x14003ac50  mov     rdx, [rsp+78h+arg_20]; unsigned __int16 *
0x14003ac58  lea     r8, [rsp+78h+arg_28]; enum _STORAGE_TIER_CLASS *
0x14003ac60  mov     rcx, [rsp+78h+arg_10]; this
0x14003ac68  xor     r9d, r9d; struct _GUID *
0x14003ac6b  call    ?GetTierInfo@CTieredVolume@@QEAAJPEAGPEAW4_STORAGE_TIER_CLASS@@PEAU_GUID@@@Z; CTieredVolume::GetTierInfo(ushort *,_STORAGE_TIER_CLASS *,_GUID *)
0x14003ac70  mov     ebx, eax
0x14003ac72  test    eax, eax
0x14003ac74  jns     short loc_14003ACC5
0x14003ac76  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ac7d  cmp     rcx, r13
0x14003ac80  jz      loc_14003AD59
0x14003ac86  test    byte ptr [rcx+1Ch], 1
0x14003ac8a  jz      loc_14003AD59
0x14003ac90  cmp     byte ptr [rcx+19h], 2
0x14003ac94  jb      loc_14003AD59
0x14003ac9a  mov     r9, [rsp+78h+arg_20]
0x14003aca2  lea     r8, WPP_679b317bfb4035ff28fff86d621cec42_Traceguids
0x14003aca9  mov     rcx, [rcx+10h]
0x14003acad  mov     edx, 28h ; '('
0x14003acb2  mov     [rsp+78h+var_50], eax
0x14003acb6  mov     qword ptr [rsp+78h+var_58], rsi
0x14003acbb  call    WPP_SF_SSd
0x14003acc0  jmp     loc_14003AD59
0x14003acc5  mov     ebp, [rsp+78h+arg_28]
0x14003accc  mov     rcx, [rsp+78h+arg_10]; this
0x14003acd4  xor     r9d, r9d; unsigned int
0x14003acd7  mov     r8, r15; struct TE_FILE_ID_128 *
0x14003acda  mov     [rsp+78h+var_58], ebp; enum _STORAGE_TIER_CLASS
0x14003acde  xor     edx, edx; lpFileName
0x14003ace0  call    ?PinFile_ApiHandler@CTieredVolume@@QEAAJPEAGPEAUTE_FILE_ID_128@@KW4_STORAGE_TIER_CLASS@@@Z; CTieredVolume::PinFile_ApiHandler(ushort *,TE_FILE_ID_128 *,ulong,_STORAGE_TIER_CLASS)
0x14003ace5  mov     ebx, eax
0x14003ace7  test    eax, eax
0x14003ace9  jns     short loc_14003AD1F
0x14003aceb  mov     rcx, cs:WPP_GLOBAL_Control
0x14003acf2  cmp     rcx, r13
0x14003acf5  jz      short loc_14003AD59
0x14003acf7  test    byte ptr [rcx+1Ch], 1
0x14003acfb  jz      short loc_14003AD59
0x14003acfd  cmp     byte ptr [rcx+19h], 2
0x14003ad01  jb      short loc_14003AD59
0x14003ad03  mov     edx, 29h ; ')'
0x14003ad08  mov     rcx, [rcx+10h]
0x14003ad0c  mov     r9, rdi
0x14003ad0f  mov     [rsp+78h+var_50], ebx
0x14003ad13  mov     qword ptr [rsp+78h+var_58], rsi
0x14003ad18  call    WPP_SF__guid_Sd
0x14003ad1d  jmp     short loc_14003AD59
0x14003ad1f  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ad26  cmp     rcx, r13
0x14003ad29  jz      short loc_14003AD59
0x14003ad2b  test    byte ptr [rcx+1Ch], 1
0x14003ad2f  jz      short loc_14003AD59
0x14003ad31  cmp     byte ptr [rcx+19h], 2
0x14003ad35  jb      short loc_14003AD59
0x14003ad37  mov     rax, [r15]
0x14003ad3a  mov     r9, [r15+8]
0x14003ad3e  mov     rcx, [rcx+10h]
0x14003ad42  mov     [rsp+78h+var_40], ebx
0x14003ad46  mov     [rsp+78h+var_48], rsi
0x14003ad4b  mov     [rsp+78h+var_50], ebp
0x14003ad4f  mov     qword ptr [rsp+78h+var_58], rax
0x14003ad54  call    WPP_SF_iiLSd
0x14003ad59  mov     eax, ebx
0x14003ad5b  add     rsp, 48h
0x14003ad5f  pop     r15
0x14003ad61  pop     r13
0x14003ad63  pop     rdi
0x14003ad64  pop     rsi
0x14003ad65  pop     rbp
0x14003ad66  pop     rbx
0x14003ad67  retn
```
