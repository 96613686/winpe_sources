# CTieringEngineApiServer::GetTieringMovementsPending(ushort *,_STORAGE_TIER_CLASS,ulong,unsigned __int64 *,int *,long *,__MIDL___MIDL_itf_tieringengine_0000_0000_0005 * *)

- ea: `0x140039b10`
- end: `0x140039dd0`
- name: `?GetTieringMovementsPending@CTieringEngineApiServer@@UEAAJPEAGW4_STORAGE_TIER_CLASS@@KPEA_KPEAHPEAJPEAPEAU__MIDL___MIDL_itf_tieringengine_0000_0000_0005@@@Z`
- size: `704`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *this, unsigned __int16 *, enum _STORAGE_TIER_CLASS, unsigned int, unsigned __int64 *, int *, int *, struct __MIDL___MIDL_itf_tieringengine_0000_0000_0005 **)`
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140002db0`
- `0x140004a40`
- `0x140004a68`
- `0x140005db4`
- `0x140009c08`
- `0x140039b10`
- `0x14003b8d4`
- `0x14003b9a0`
- `0x14003c21c`
- `0x14003c390`
- `0x14003ddd4`

## pseudocode

```c
__int64 __fastcall CTieringEngineApiServer::GetTieringMovementsPending(
        RTL_SRWLOCK *this,
        unsigned __int16 *a2,
        enum _STORAGE_TIER_CLASS a3,
        unsigned int a4,
        unsigned __int64 *a5,
        int *a6,
        int *a7,
        struct __MIDL___MIDL_itf_tieringengine_0000_0000_0005 **a8)
{
  char v9; // si
  char v11; // al
  _QWORD *v12; // rcx
  int v13; // edx
  int TieredVolumeByVolumeName_StrongValidation; // edi
  int v15; // r8d
  struct _TE_ENUM_INTERNAL_RESUME_KEY *InternalResumeKey; // rax
  int v18; // edx
  int v19; // r8d
  struct CTieredVolume *v20; // [rsp+40h] [rbp-38h] BYREF

  v20 = 0;
  v9 = a4;
  if ( a6 )
  {
    *a6 = 0;
    v11 = 1;
    v12 = WPP_GLOBAL_Control;
  }
  else
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 76, &WPP_679b317bfb4035ff28fff86d621cec42_Traceguids);
      v12 = WPP_GLOBAL_Control;
    }
    v11 = 0;
  }
  if ( a7 )
  {
    *a7 = 0;
    v12 = WPP_GLOBAL_Control;
  }
  else
  {
    if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 1) != 0 && *((_BYTE *)v12 + 25) >= 3u )
    {
      WPP_SF_(v12[2], 77, &WPP_679b317bfb4035ff28fff86d621cec42_Traceguids);
      v12 = WPP_GLOBAL_Control;
    }
    v11 = 0;
  }
  if ( !a8 )
  {
    if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 1) != 0 && *((_BYTE *)v12 + 25) >= 3u )
      WPP_SF_(v12[2], 78, &WPP_679b317bfb4035ff28fff86d621cec42_Traceguids);
    return ATL::AtlHresultFromWin32(87);
  }
  *a8 = 0;
  if ( !v11 )
    return ATL::AtlHresultFromWin32(87);
  TieredVolumeByVolumeName_StrongValidation = CTieringEngineLib::GetTieredVolumeByVolumeName_StrongValidation(
                                                (CTieringEngineLib *)TieringEngineLibInstance,
                                                a2,
                                                &v20);
  if ( TieredVolumeByVolumeName_StrongValidation >= 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_LDS(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, v15, a3, v9, (__int64)a2);
    }
    InternalResumeKey = ResumeKeyManager::GetOrCreateInternalResumeKey((ResumeKeyManager *)&this[8], a5);
    if ( InternalResumeKey )
    {
      TieredVolumeByVolumeName_StrongValidation = CTieredVolume::GetTieringMovementsPending_ApiHandler(
                                                    v20,
                                                    a3,
                                                    a4,
                                                    InternalResumeKey,
                                                    a6,
                                                    a7,
                                                    a8);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_LDDSd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v18,
          v19,
          a3,
          *a7,
          *a6,
          (__int64)a2,
          TieredVolumeByVolumeName_StrongValidation);
      }
      ResumeKeyManager::CompleteUsageWithKey(this + 8, a5);
    }
    else
    {
      TieredVolumeByVolumeName_StrongValidation = ATL::AtlHresultFromWin32(14);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          81,
          &WPP_679b317bfb4035ff28fff86d621cec42_Traceguids,
          (unsigned int)TieredVolumeByVolumeName_StrongValidation);
      }
    }
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      79,
      (unsigned int)&WPP_679b317bfb4035ff28fff86d621cec42_Traceguids,
      (_DWORD)a2,
      TieredVolumeByVolumeName_StrongValidation);
  }
  return (unsigned int)TieredVolumeByVolumeName_StrongValidation;
}

```

## disassembly

```asm
0x140039b10  mov     rax, rsp
0x140039b13  mov     [rax+10h], rbp
0x140039b17  mov     [rax+18h], rsi
0x140039b1b  mov     [rax+20h], r9d
0x140039b1f  mov     [rax+8], rcx
0x140039b23  push    rdi
0x140039b24  push    r12
0x140039b26  push    r13
0x140039b28  push    r14
0x140039b2a  push    r15
0x140039b2c  sub     rsp, 50h
0x140039b30  mov     r12, [rsp+78h+arg_28]
0x140039b38  xor     edi, edi
0x140039b3a  mov     [rax-38h], rdi
0x140039b3e  mov     rbp, rdx
0x140039b41  lea     rdx, WPP_GLOBAL_Control
0x140039b48  mov     esi, r9d
0x140039b4b  mov     r13d, r8d
0x140039b4e  test    r12, r12
0x140039b51  jz      short loc_140039B62
0x140039b53  mov     [r12], edi
0x140039b57  mov     al, 1
0x140039b59  mov     rcx, cs:WPP_GLOBAL_Control
0x140039b60  jmp     short loc_140039BA0
0x140039b62  mov     rcx, cs:WPP_GLOBAL_Control
0x140039b69  cmp     rcx, rdx
0x140039b6c  jz      short loc_140039B9D
0x140039b6e  test    byte ptr [rcx+1Ch], 1
0x140039b72  jz      short loc_140039B9D
0x140039b74  cmp     byte ptr [rcx+19h], 3
0x140039b78  jb      short loc_140039B9D
0x140039b7a  mov     rcx, [rcx+10h]
0x140039b7e  lea     r8, WPP_679b317bfb4035ff28fff86d621cec42_Traceguids
0x140039b85  mov     edx, 4Ch ; 'L'
0x140039b8a  call    WPP_SF_
0x140039b8f  mov     rcx, cs:WPP_GLOBAL_Control
0x140039b96  lea     rdx, WPP_GLOBAL_Control
0x140039b9d  mov     al, dil
0x140039ba0  mov     r15, [rsp+78h+arg_30]
0x140039ba8  test    r15, r15
0x140039bab  jz      short loc_140039BB9
0x140039bad  mov     [r15], edi
0x140039bb0  mov     rcx, cs:WPP_GLOBAL_Control
0x140039bb7  jmp     short loc_140039BF0
0x140039bb9  cmp     rcx, rdx
0x140039bbc  jz      short loc_140039BED
0x140039bbe  test    byte ptr [rcx+1Ch], 1
0x140039bc2  jz      short loc_140039BED
0x140039bc4  cmp     byte ptr [rcx+19h], 3
0x140039bc8  jb      short loc_140039BED
0x140039bca  mov     rcx, [rcx+10h]
0x140039bce  lea     r8, WPP_679b317bfb4035ff28fff86d621cec42_Traceguids
0x140039bd5  mov     edx, 4Dh ; 'M'
0x140039bda  call    WPP_SF_
0x140039bdf  mov     rcx, cs:WPP_GLOBAL_Control
0x140039be6  lea     rdx, WPP_GLOBAL_Control
0x140039bed  mov     al, dil
0x140039bf0  mov     r14, [rsp+78h+arg_38]
0x140039bf8  test    r14, r14
0x140039bfb  jz      loc_140039D86
0x140039c01  mov     [r14], rdi
0x140039c04  test    al, al
0x140039c06  jz      loc_140039DAC
0x140039c0c  mov     rcx, cs:?TieringEngineLibInstance@@3PEAVCTieringEngineLib@@EA; this
0x140039c13  lea     r8, [rsp+78h+var_38]; struct CTieredVolume **
0x140039c18  mov     rdx, rbp; unsigned __int16 *
0x140039c1b  call    ?GetTieredVolumeByVolumeName_StrongValidation@CTieringEngineLib@@QEAAJPEAGPEAPEAVCTieredVolume@@@Z; CTieringEngineLib::GetTieredVolumeByVolumeName_StrongValidation(ushort *,CTieredVolume * *)
0x140039c20  mov     edi, eax
0x140039c22  test    eax, eax
0x140039c24  jns     short loc_140039C68
0x140039c26  mov     rcx, cs:WPP_GLOBAL_Control
0x140039c2d  lea     rax, WPP_GLOBAL_Control
0x140039c34  cmp     rcx, rax
0x140039c37  jz      short loc_140039C61
0x140039c39  test    byte ptr [rcx+1Ch], 1
0x140039c3d  jz      short loc_140039C61
0x140039c3f  cmp     byte ptr [rcx+19h], 2
0x140039c43  jb      short loc_140039C61
0x140039c45  mov     rcx, [rcx+10h]
0x140039c49  lea     r8, WPP_679b317bfb4035ff28fff86d621cec42_Traceguids
0x140039c50  mov     edx, 4Fh ; 'O'
0x140039c55  mov     dword ptr [rsp+78h+var_58], edi
0x140039c59  mov     r9, rbp
0x140039c5c  call    WPP_SF_Sd
0x140039c61  mov     eax, edi
0x140039c63  jmp     loc_140039DB6
0x140039c68  mov     rcx, cs:WPP_GLOBAL_Control
0x140039c6f  lea     rax, WPP_GLOBAL_Control
0x140039c76  cmp     rcx, rax
0x140039c79  jz      short loc_140039C9C
0x140039c7b  test    byte ptr [rcx+1Ch], 1
0x140039c7f  jz      short loc_140039C9C
0x140039c81  cmp     byte ptr [rcx+19h], 5
0x140039c85  jb      short loc_140039C9C
0x140039c87  mov     rcx, [rcx+10h]
0x140039c8b  mov     r9d, r13d
0x140039c8e  mov     [rsp+78h+var_50], rbp
0x140039c93  mov     dword ptr [rsp+78h+var_58], esi
0x140039c97  call    WPP_SF_LDS
0x140039c9c  mov     rsi, [rsp+78h+arg_0]
0x140039ca4  mov     rdx, [rsp+78h+arg_20]; unsigned __int64 *
0x140039cac  lea     rcx, [rsi+40h]; this
0x140039cb0  call    ?GetOrCreateInternalResumeKey@ResumeKeyManager@@QEAAPEAU_TE_ENUM_INTERNAL_RESUME_KEY@@PEA_K@Z; ResumeKeyManager::GetOrCreateInternalResumeKey(unsigned __int64 *)
0x140039cb5  test    rax, rax
0x140039cb8  jnz     short loc_140039D04
0x140039cba  lea     ecx, [rax+0Eh]; unsigned int
0x140039cbd  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x140039cc2  mov     edi, eax
0x140039cc4  mov     rcx, cs:WPP_GLOBAL_Control
0x140039ccb  lea     rax, WPP_GLOBAL_Control
0x140039cd2  cmp     rcx, rax
0x140039cd5  jz      short loc_140039C61
0x140039cd7  test    byte ptr [rcx+1Ch], 1
0x140039cdb  jz      short loc_140039C61
0x140039cdd  cmp     byte ptr [rcx+19h], 2
0x140039ce1  jb      loc_140039C61
0x140039ce7  mov     rcx, [rcx+10h]
0x140039ceb  lea     r8, WPP_679b317bfb4035ff28fff86d621cec42_Traceguids
0x140039cf2  mov     edx, 51h ; 'Q'
0x140039cf7  mov     r9d, edi
0x140039cfa  call    WPP_SF_d
0x140039cff  jmp     loc_140039C61
0x140039d04  mov     r8d, [rsp+78h+arg_18]; unsigned int
0x140039d0c  mov     r9, rax; struct _TE_ENUM_INTERNAL_RESUME_KEY *
0x140039d0f  mov     rcx, [rsp+78h+var_38]; this
0x140039d14  mov     edx, r13d; enum _STORAGE_TIER_CLASS
0x140039d17  mov     [rsp+78h+var_48], r14; struct __MIDL___MIDL_itf_tieringengine_0000_0000_0005 **
0x140039d1c  mov     [rsp+78h+var_50], r15; int *
0x140039d21  mov     [rsp+78h+var_58], r12; int *
0x140039d26  call    ?GetTieringMovementsPending_ApiHandler@CTieredVolume@@QEAAJW4_STORAGE_TIER_CLASS@@KPEAU_TE_ENUM_INTERNAL_RESUME_KEY@@PEAHPEAJPEAPEAU__MIDL___MIDL_itf_tieringengine_0000_0000_0005@@@Z; CTieredVolume::GetTieringMovementsPending_ApiHandler(_STORAGE_TIER_CLASS,ulong,_TE_ENUM_INTERNAL_RESUME_KEY *,int *,long *,__MIDL___MIDL_itf_tieringengine_0000_0000_0005 * *)
0x140039d2b  mov     edi, eax
0x140039d2d  mov     rcx, cs:WPP_GLOBAL_Control
0x140039d34  lea     rax, WPP_GLOBAL_Control
0x140039d3b  cmp     rcx, rax
0x140039d3e  jz      short loc_140039D70
0x140039d40  test    byte ptr [rcx+1Ch], 1
0x140039d44  jz      short loc_140039D70
0x140039d46  cmp     byte ptr [rcx+19h], 2
0x140039d4a  jb      short loc_140039D70
0x140039d4c  mov     eax, [r12]
0x140039d50  mov     r9d, r13d
0x140039d53  mov     rcx, [rcx+10h]
0x140039d57  mov     [rsp+78h+var_40], edi
0x140039d5b  mov     [rsp+78h+var_48], rbp
0x140039d60  mov     dword ptr [rsp+78h+var_50], eax
0x140039d64  mov     eax, [r15]
0x140039d67  mov     dword ptr [rsp+78h+var_58], eax
0x140039d6b  call    WPP_SF_LDDSd
0x140039d70  mov     rdx, [rsp+78h+arg_20]; unsigned __int64 *
0x140039d78  lea     rcx, [rsi+40h]; this
0x140039d7c  call    ?CompleteUsageWithKey@ResumeKeyManager@@QEAAXPEA_K@Z; ResumeKeyManager::CompleteUsageWithKey(unsigned __int64 *)
0x140039d81  jmp     loc_140039C61
0x140039d86  cmp     rcx, rdx
0x140039d89  jz      short loc_140039DAC
0x140039d8b  test    byte ptr [rcx+1Ch], 1
0x140039d8f  jz      short loc_140039DAC
0x140039d91  cmp     byte ptr [rcx+19h], 3
0x140039d95  jb      short loc_140039DAC
0x140039d97  mov     rcx, [rcx+10h]
0x140039d9b  lea     r8, WPP_679b317bfb4035ff28fff86d621cec42_Traceguids
0x140039da2  mov     edx, 4Eh ; 'N'
0x140039da7  call    WPP_SF_
0x140039dac  mov     ecx, 57h ; 'W'; unsigned int
0x140039db1  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x140039db6  lea     r11, [rsp+78h+var_28]
0x140039dbb  mov     rbp, [r11+38h]
0x140039dbf  mov     rsi, [r11+40h]
0x140039dc3  mov     rsp, r11
0x140039dc6  pop     r15
0x140039dc8  pop     r14
0x140039dca  pop     r13
0x140039dcc  pop     r12
0x140039dce  pop     rdi
0x140039dcf  retn
```
