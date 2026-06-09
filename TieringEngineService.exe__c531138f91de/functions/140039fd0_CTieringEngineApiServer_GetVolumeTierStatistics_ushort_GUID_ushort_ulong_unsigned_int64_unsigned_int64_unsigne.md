# CTieringEngineApiServer::GetVolumeTierStatistics(ushort *,_GUID *,ushort *,ulong *,unsigned __int64 *,unsigned __int64 *,unsigned __int64 *,unsigned __int64 *)

- ea: `0x140039fd0`
- end: `0x14003a3c4`
- name: `?GetVolumeTierStatistics@CTieringEngineApiServer@@UEAAJPEAGPEAU_GUID@@0PEAKPEA_K333@Z`
- size: `1012`
- prototype: `__int64 __fastcall(CTieringEngineApiServer *this, unsigned __int16 *, struct _GUID *, unsigned __int16 *, unsigned int *, unsigned __int64 *, unsigned __int64 *, unsigned __int64 *, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140002db0`
- `0x140004a40`
- `0x140004a68`
- `0x140005db4`
- `0x140009c08`
- `0x14000f2e4`
- `0x140017cd4`
- `0x140039fd0`
- `0x14003b7f4`
- `0x14003e49c`
- `0x14003fbb0`

## import_xrefs

- `ntdll!RtlCompareMemory` at `0x14003a280`
- `ntdll!RtlCompareMemory` at `0x14003a280`

## pseudocode

```c
__int64 __fastcall CTieringEngineApiServer::GetVolumeTierStatistics(
        CTieringEngineApiServer *this,
        unsigned __int16 *a2,
        struct _GUID *a3,
        unsigned __int16 *a4,
        unsigned int *a5,
        unsigned __int64 *a6,
        unsigned __int64 *a7,
        unsigned __int64 *a8,
        unsigned __int64 *a9)
{
  unsigned int *v10; // rdx
  struct _GUID *v11; // rbp
  bool v12; // zf
  unsigned int v13; // edi
  char v15; // di
  _QWORD *v16; // rcx
  int TieredVolumeByVolumeName_StrongValidation; // eax
  int v18; // ebp
  unsigned int TierInfo; // eax
  unsigned __int64 *v20; // rsi
  unsigned int VolumeTierStatistics_ApiHandler; // eax
  int v22; // edx
  int v23; // r8d
  struct CTieredVolume *v24; // [rsp+50h] [rbp-78h] BYREF
  unsigned __int64 *v25; // [rsp+58h] [rbp-70h]
  unsigned int *v26; // [rsp+60h] [rbp-68h]
  unsigned __int16 *v27; // [rsp+68h] [rbp-60h]
  struct _GUID v28; // [rsp+70h] [rbp-58h] BYREF

  v10 = a5;
  v11 = a3;
  v12 = *((_BYTE *)TieringEngineLibInstance + 140) == 1;
  v27 = a4;
  v26 = a5;
  v25 = a8;
  v24 = 0;
  v28 = 0;
  if ( !v12 )
  {
    v13 = -2147467263;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 127, &WPP_679b317bfb4035ff28fff86d621cec42_Traceguids, 2147500033LL);
    }
    return v13;
  }
  v15 = 1;
  if ( a3 || a4 )
    goto LABEL_13;
  v15 = 0;
  v16 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 128, &WPP_679b317bfb4035ff28fff86d621cec42_Traceguids);
    v10 = v26;
LABEL_13:
    v16 = WPP_GLOBAL_Control;
  }
  if ( v10 )
  {
    *v10 = 0;
    v16 = WPP_GLOBAL_Control;
  }
  else
  {
    if ( v16 != &WPP_GLOBAL_Control && (*((_BYTE *)v16 + 28) & 1) != 0 && *((_BYTE *)v16 + 25) >= 3u )
    {
      WPP_SF_(v16[2], 129, &WPP_679b317bfb4035ff28fff86d621cec42_Traceguids);
      v16 = WPP_GLOBAL_Control;
    }
    v15 = 0;
  }
  if ( a6 )
  {
    *a6 = 0;
    v16 = WPP_GLOBAL_Control;
  }
  else
  {
    if ( v16 != &WPP_GLOBAL_Control && (*((_BYTE *)v16 + 28) & 1) != 0 && *((_BYTE *)v16 + 25) >= 3u )
    {
      WPP_SF_(v16[2], 130, &WPP_679b317bfb4035ff28fff86d621cec42_Traceguids);
      v16 = WPP_GLOBAL_Control;
    }
    v15 = 0;
  }
  if ( a7 )
  {
    *a7 = 0;
    v16 = WPP_GLOBAL_Control;
  }
  else
  {
    if ( v16 != &WPP_GLOBAL_Control && (*((_BYTE *)v16 + 28) & 1) != 0 && *((_BYTE *)v16 + 25) >= 3u )
    {
      WPP_SF_(v16[2], 131, &WPP_679b317bfb4035ff28fff86d621cec42_Traceguids);
      v16 = WPP_GLOBAL_Control;
    }
    v15 = 0;
  }
  if ( v25 )
  {
    *v25 = 0;
    v16 = WPP_GLOBAL_Control;
  }
  else
  {
    if ( v16 != &WPP_GLOBAL_Control && (*((_BYTE *)v16 + 28) & 1) != 0 && *((_BYTE *)v16 + 25) >= 3u )
    {
      WPP_SF_(v16[2], 132, &WPP_679b317bfb4035ff28fff86d621cec42_Traceguids);
      v16 = WPP_GLOBAL_Control;
    }
    v15 = 0;
  }
  if ( a9 )
  {
    *a9 = 0;
    if ( v15 )
    {
      TieredVolumeByVolumeName_StrongValidation = CTieringEngineLib::GetTieredVolumeByVolumeName_StrongValidation(
                                                    (CTieringEngineLib *)TieringEngineLibInstance,
                                                    a2,
                                                    &v24);
      v13 = TieredVolumeByVolumeName_StrongValidation;
      if ( TieredVolumeByVolumeName_StrongValidation >= 0 )
      {
        if ( !v11 || RtlCompareMemory(v11, &NullGuid, 0x10u) == 16 )
        {
          v18 = (int)v27;
          TierInfo = CTieredVolume::GetTierInfo((RTL_SRWLOCK *)v24, v27, 0, &v28);
          v13 = TierInfo;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_SSd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              135,
              (unsigned int)&WPP_679b317bfb4035ff28fff86d621cec42_Traceguids,
              v18,
              (__int64)a2,
              TierInfo);
          }
          if ( (v13 & 0x80000000) != 0 )
            return v13;
          v11 = &v28;
        }
        v20 = v25;
        VolumeTierStatistics_ApiHandler = CTieredVolume::GetVolumeTierStatistics_ApiHandler(
                                            v24,
                                            v11,
                                            v26,
                                            a6,
                                            a7,
                                            v25,
                                            a9);
        v13 = VolumeTierStatistics_ApiHandler;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_IIIISd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v22,
            v23,
            *a6,
            *a7,
            *v20,
            *a9,
            (__int64)a2,
            VolumeTierStatistics_ApiHandler);
        }
      }
      else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          134,
          (unsigned int)&WPP_679b317bfb4035ff28fff86d621cec42_Traceguids,
          (_DWORD)a2,
          TieredVolumeByVolumeName_StrongValidation);
      }
      return v13;
    }
  }
  else if ( v16 != &WPP_GLOBAL_Control && (*((_BYTE *)v16 + 28) & 1) != 0 && *((_BYTE *)v16 + 25) >= 3u )
  {
    WPP_SF_(v16[2], 133, &WPP_679b317bfb4035ff28fff86d621cec42_Traceguids);
  }
  return ATL::AtlHresultFromWin32(87);
}

```

## disassembly

```asm
0x140039fd0  mov     [rsp+arg_0], rbx
0x140039fd5  push    rbp
0x140039fd6  push    rsi
0x140039fd7  push    rdi
0x140039fd8  push    r12
0x140039fda  push    r13
0x140039fdc  push    r14
0x140039fde  push    r15
0x140039fe0  sub     rsp, 90h
0x140039fe7  mov     rax, cs:__security_cookie
0x140039fee  xor     rax, rsp
0x140039ff1  mov     [rsp+0C8h+var_48], rax
0x140039ff9  mov     rax, cs:?TieringEngineLibInstance@@3PEAVCTieringEngineLib@@EA; CTieringEngineLib * TieringEngineLibInstance
0x14003a000  mov     r15, rdx
0x14003a003  mov     rdx, [rsp+0C8h+arg_20]
0x14003a00b  xorps   xmm0, xmm0
0x14003a00e  mov     rsi, [rsp+0C8h+arg_38]
0x14003a016  mov     rbp, r8
0x14003a019  mov     r12, [rsp+0C8h+arg_28]
0x14003a021  cmp     byte ptr [rax+8Ch], 1
0x14003a028  mov     r13, [rsp+0C8h+arg_30]
0x14003a030  mov     r14, [rsp+0C8h+arg_40]
0x14003a038  mov     [rsp+0C8h+var_60], r9
0x14003a03d  mov     [rsp+0C8h+var_68], rdx
0x14003a042  mov     [rsp+0C8h+var_70], rsi
0x14003a047  mov     [rsp+0C8h+var_78], 0
0x14003a050  movups  xmmword ptr [rsp+0C8h+var_58.Data1], xmm0
0x14003a055  jz      short loc_14003A09A
0x14003a057  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a05e  lea     rbx, WPP_GLOBAL_Control
0x14003a065  mov     edi, 80004001h
0x14003a06a  cmp     rcx, rbx
0x14003a06d  jz      short loc_14003A093
0x14003a06f  test    byte ptr [rcx+1Ch], 1
0x14003a073  jz      short loc_14003A093
0x14003a075  cmp     byte ptr [rcx+19h], 2
0x14003a079  jb      short loc_14003A093
0x14003a07b  mov     rcx, [rcx+10h]
0x14003a07f  lea     r8, WPP_679b317bfb4035ff28fff86d621cec42_Traceguids
0x14003a086  mov     edx, 7Fh
0x14003a08b  mov     r9d, edi
0x14003a08e  call    WPP_SF_d
0x14003a093  mov     eax, edi
0x14003a095  jmp     loc_14003A399
0x14003a09a  lea     rsi, WPP_679b317bfb4035ff28fff86d621cec42_Traceguids
0x14003a0a1  mov     dil, 1
0x14003a0a4  lea     rbx, WPP_GLOBAL_Control
0x14003a0ab  test    rbp, rbp
0x14003a0ae  jnz     short loc_14003A0E6
0x14003a0b0  test    r9, r9
0x14003a0b3  jnz     short loc_14003A0E6
0x14003a0b5  xor     dil, dil
0x14003a0b8  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a0bf  cmp     rcx, rbx
0x14003a0c2  jz      short loc_14003A0ED
0x14003a0c4  test    byte ptr [rcx+1Ch], 1
0x14003a0c8  jz      short loc_14003A0ED
0x14003a0ca  cmp     byte ptr [rcx+19h], 3
0x14003a0ce  jb      short loc_14003A0ED
0x14003a0d0  mov     rcx, [rcx+10h]
0x14003a0d4  mov     edx, 80h
0x14003a0d9  mov     r8, rsi
0x14003a0dc  call    WPP_SF_
0x14003a0e1  mov     rdx, [rsp+0C8h+var_68]
0x14003a0e6  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a0ed  test    rdx, rdx
0x14003a0f0  jz      short loc_14003A101
0x14003a0f2  mov     dword ptr [rdx], 0
0x14003a0f8  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a0ff  jmp     short loc_14003A12D
0x14003a101  cmp     rcx, rbx
0x14003a104  jz      short loc_14003A12A
0x14003a106  test    byte ptr [rcx+1Ch], 1
0x14003a10a  jz      short loc_14003A12A
0x14003a10c  cmp     byte ptr [rcx+19h], 3
0x14003a110  jb      short loc_14003A12A
0x14003a112  mov     rcx, [rcx+10h]
0x14003a116  mov     edx, 81h
0x14003a11b  mov     r8, rsi
0x14003a11e  call    WPP_SF_
0x14003a123  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a12a  xor     dil, dil
0x14003a12d  test    r12, r12
0x14003a130  jz      short loc_14003A143
0x14003a132  mov     qword ptr [r12], 0
0x14003a13a  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a141  jmp     short loc_14003A16F
0x14003a143  cmp     rcx, rbx
0x14003a146  jz      short loc_14003A16C
0x14003a148  test    byte ptr [rcx+1Ch], 1
0x14003a14c  jz      short loc_14003A16C
0x14003a14e  cmp     byte ptr [rcx+19h], 3
0x14003a152  jb      short loc_14003A16C
0x14003a154  mov     rcx, [rcx+10h]
0x14003a158  mov     edx, 82h
0x14003a15d  mov     r8, rsi
0x14003a160  call    WPP_SF_
0x14003a165  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a16c  xor     dil, dil
0x14003a16f  test    r13, r13
0x14003a172  jz      short loc_14003A185
0x14003a174  mov     qword ptr [r13+0], 0
0x14003a17c  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a183  jmp     short loc_14003A1B1
0x14003a185  cmp     rcx, rbx
0x14003a188  jz      short loc_14003A1AE
0x14003a18a  test    byte ptr [rcx+1Ch], 1
0x14003a18e  jz      short loc_14003A1AE
0x14003a190  cmp     byte ptr [rcx+19h], 3
0x14003a194  jb      short loc_14003A1AE
0x14003a196  mov     rcx, [rcx+10h]
0x14003a19a  mov     edx, 83h
0x14003a19f  mov     r8, rsi
0x14003a1a2  call    WPP_SF_
0x14003a1a7  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a1ae  xor     dil, dil
0x14003a1b1  mov     rax, [rsp+0C8h+var_70]
0x14003a1b6  test    rax, rax
0x14003a1b9  jz      short loc_14003A1CB
0x14003a1bb  mov     qword ptr [rax], 0
0x14003a1c2  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a1c9  jmp     short loc_14003A1F7
0x14003a1cb  cmp     rcx, rbx
0x14003a1ce  jz      short loc_14003A1F4
0x14003a1d0  test    byte ptr [rcx+1Ch], 1
0x14003a1d4  jz      short loc_14003A1F4
0x14003a1d6  cmp     byte ptr [rcx+19h], 3
0x14003a1da  jb      short loc_14003A1F4
0x14003a1dc  mov     rcx, [rcx+10h]
0x14003a1e0  mov     edx, 84h
0x14003a1e5  mov     r8, rsi
0x14003a1e8  call    WPP_SF_
0x14003a1ed  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a1f4  xor     dil, dil
0x14003a1f7  test    r14, r14
0x14003a1fa  jz      loc_14003A36D
0x14003a200  mov     qword ptr [r14], 0
0x14003a207  test    dil, dil
0x14003a20a  jz      loc_14003A38F
0x14003a210  mov     rcx, cs:?TieringEngineLibInstance@@3PEAVCTieringEngineLib@@EA; this
0x14003a217  lea     r8, [rsp+0C8h+var_78]; struct CTieredVolume **
0x14003a21c  mov     rdx, r15; unsigned __int16 *
0x14003a21f  call    ?GetTieredVolumeByVolumeName_StrongValidation@CTieringEngineLib@@QEAAJPEAGPEAPEAVCTieredVolume@@@Z; CTieringEngineLib::GetTieredVolumeByVolumeName_StrongValidation(ushort *,CTieredVolume * *)
0x14003a224  mov     edi, eax
0x14003a226  test    eax, eax
0x14003a228  jns     short loc_14003A26B
0x14003a22a  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a231  cmp     rcx, rbx
0x14003a234  jz      loc_14003A093
0x14003a23a  test    byte ptr [rcx+1Ch], 1
0x14003a23e  jz      loc_14003A093
0x14003a244  cmp     byte ptr [rcx+19h], 2
0x14003a248  jb      loc_14003A093
0x14003a24e  mov     rcx, [rcx+10h]
0x14003a252  mov     edx, 86h
0x14003a257  mov     r9, r15
0x14003a25a  mov     dword ptr [rsp+0C8h+var_A8], eax
0x14003a25e  mov     r8, rsi
0x14003a261  call    WPP_SF_Sd
0x14003a266  jmp     loc_14003A093
0x14003a26b  test    rbp, rbp
0x14003a26e  jz      short loc_14003A28C
0x14003a270  mov     r8d, 10h; Length
0x14003a276  lea     rdx, ?NullGuid@@3U_GUID@@A; Source2
0x14003a27d  mov     rcx, rbp; Source1
0x14003a280  call    cs:__imp_RtlCompareMemory
0x14003a286  cmp     rax, 10h
0x14003a28a  jnz     short loc_14003A2EA
0x14003a28c  mov     rbp, [rsp+0C8h+var_60]
0x14003a291  lea     r9, [rsp+0C8h+var_58]; struct _GUID *
0x14003a296  mov     rcx, [rsp+0C8h+var_78]; this
0x14003a29b  mov     rdx, rbp; unsigned __int16 *
0x14003a29e  xor     r8d, r8d; enum _STORAGE_TIER_CLASS *
0x14003a2a1  call    ?GetTierInfo@CTieredVolume@@QEAAJPEAGPEAW4_STORAGE_TIER_CLASS@@PEAU_GUID@@@Z; CTieredVolume::GetTierInfo(ushort *,_STORAGE_TIER_CLASS *,_GUID *)
0x14003a2a6  mov     edi, eax
0x14003a2a8  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a2af  cmp     rcx, rbx
0x14003a2b2  jz      short loc_14003A2DD
0x14003a2b4  test    byte ptr [rcx+1Ch], 1
0x14003a2b8  jz      short loc_14003A2DD
0x14003a2ba  cmp     byte ptr [rcx+19h], 2
0x14003a2be  jb      short loc_14003A2DD
0x14003a2c0  mov     rcx, [rcx+10h]
0x14003a2c4  mov     edx, 87h
0x14003a2c9  mov     dword ptr [rsp+0C8h+var_A0], eax
0x14003a2cd  mov     r9, rbp
0x14003a2d0  mov     r8, rsi
0x14003a2d3  mov     [rsp+0C8h+var_A8], r15
0x14003a2d8  call    WPP_SF_SSd
0x14003a2dd  test    edi, edi
0x14003a2df  js      loc_14003A093
0x14003a2e5  lea     rbp, [rsp+0C8h+var_58]
0x14003a2ea  mov     rsi, [rsp+0C8h+var_70]
0x14003a2ef  mov     r9, r12; unsigned __int64 *
0x14003a2f2  mov     r8, [rsp+0C8h+var_68]; unsigned int *
0x14003a2f7  mov     rdx, rbp; struct _GUID *
0x14003a2fa  mov     rcx, [rsp+0C8h+var_78]; this
0x14003a2ff  mov     [rsp+0C8h+var_98], r14; unsigned __int64 *
0x14003a304  mov     [rsp+0C8h+var_A0], rsi; unsigned __int64 *
0x14003a309  mov     [rsp+0C8h+var_A8], r13; unsigned __int64 *
0x14003a30e  call    ?GetVolumeTierStatistics_ApiHandler@CTieredVolume@@QEAAJPEAU_GUID@@PEAKPEA_K222@Z; CTieredVolume::GetVolumeTierStatistics_ApiHandler(_GUID *,ulong *,unsigned __int64 *,unsigned __int64 *,unsigned __int64 *,unsigned __int64 *)
0x14003a313  mov     edi, eax
0x14003a315  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a31c  cmp     rcx, rbx
0x14003a31f  jz      loc_14003A093
0x14003a325  test    byte ptr [rcx+1Ch], 1
0x14003a329  jz      loc_14003A093
0x14003a32f  cmp     byte ptr [rcx+19h], 2
0x14003a333  jb      loc_14003A093
0x14003a339  mov     r9, [r12]
0x14003a33d  mov     rcx, [rcx+10h]
0x14003a341  mov     [rsp+0C8h+var_88], eax
0x14003a345  mov     rax, [r14]
0x14003a348  mov     [rsp+0C8h+var_90], r15
0x14003a34d  mov     [rsp+0C8h+var_98], rax
0x14003a352  mov     rax, [rsi]
0x14003a355  mov     [rsp+0C8h+var_A0], rax
0x14003a35a  mov     rax, [r13+0]
0x14003a35e  mov     [rsp+0C8h+var_A8], rax
0x14003a363  call    WPP_SF_IIIISd
0x14003a368  jmp     loc_14003A093
0x14003a36d  cmp     rcx, rbx
0x14003a370  jz      short loc_14003A38F
0x14003a372  test    byte ptr [rcx+1Ch], 1
0x14003a376  jz      short loc_14003A38F
0x14003a378  cmp     byte ptr [rcx+19h], 3
0x14003a37c  jb      short loc_14003A38F
0x14003a37e  mov     rcx, [rcx+10h]
0x14003a382  mov     edx, 85h
0x14003a387  mov     r8, rsi
0x14003a38a  call    WPP_SF_
0x14003a38f  mov     ecx, 57h ; 'W'; unsigned int
0x14003a394  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x14003a399  mov     rcx, [rsp+0C8h+var_48]
0x14003a3a1  xor     rcx, rsp; StackCookie
0x14003a3a4  call    __security_check_cookie
0x14003a3a9  mov     rbx, [rsp+0C8h+arg_0]
0x14003a3b1  add     rsp, 90h
0x14003a3b8  pop     r15
0x14003a3ba  pop     r14
0x14003a3bc  pop     r13
0x14003a3be  pop     r12
0x14003a3c0  pop     rdi
0x14003a3c1  pop     rsi
0x14003a3c2  pop     rbp
0x14003a3c3  retn
```
