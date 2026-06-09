# CTieringEngineApiServer::IsFilePinned(ushort *,_FILE_ID_128 *,int *,long *,_GUID *,ushort * *,_STORAGE_TIER_CLASS *)

- ea: `0x14003a610`
- end: `0x14003a8e0`
- name: `?IsFilePinned@CTieringEngineApiServer@@UEAAJPEAGPEAU_FILE_ID_128@@PEAHPEAJPEAU_GUID@@PEAPEAGPEAW4_STORAGE_TIER_CLASS@@@Z`
- size: `720`
- prototype: `__int64 __fastcall(CTieringEngineApiServer *this, unsigned __int16 *, struct _FILE_ID_128 *, int *, int *, struct _GUID *, unsigned __int16 **, enum _STORAGE_TIER_CLASS *)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x140002db0`
- `0x140004a40`
- `0x140004a68`
- `0x140005db4`
- `0x140009c08`
- `0x14000f728`
- `0x14003a610`
- `0x14003ba40`
- `0x14003e794`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14003a86d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14003a86d`

## pseudocode

```c
__int64 __fastcall CTieringEngineApiServer::IsFilePinned(
        CTieringEngineApiServer *this,
        unsigned __int16 *a2,
        struct _FILE_ID_128 *a3,
        int *a4,
        int *a5,
        struct _GUID *a6,
        unsigned __int16 **a7,
        enum _STORAGE_TIER_CLASS *a8)
{
  struct _GUID *v10; // r14
  bool v11; // zf
  char v13; // al
  _QWORD *v14; // rcx
  enum _STORAGE_TIER_CLASS *v15; // rdi
  int TieredVolumeByVolumeName_StrongValidation; // esi
  _QWORD *v17; // rcx
  int v18; // edx
  int v19; // edx
  int v20; // r8d
  unsigned __int16 *v21; // rax
  int v22; // [rsp+40h] [rbp-68h] BYREF
  CTieredVolume *v23; // [rsp+48h] [rbp-60h] BYREF
  int *v24; // [rsp+50h] [rbp-58h]
  __int128 v25; // [rsp+58h] [rbp-50h] BYREF

  v10 = a6;
  v11 = *((_BYTE *)TieringEngineLibInstance + 140) == 1;
  v24 = a4;
  v23 = 0;
  v25 = 0;
  v22 = 0;
  if ( v11 )
  {
    v13 = 1;
    if ( a3 )
    {
      v14 = WPP_GLOBAL_Control;
    }
    else
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_679b317bfb4035ff28fff86d621cec42_Traceguids);
        v14 = WPP_GLOBAL_Control;
        a4 = v24;
      }
      v13 = 0;
    }
    if ( a4 )
    {
      *a4 = 0;
      v14 = WPP_GLOBAL_Control;
    }
    else
    {
      if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 1) != 0 && *((_BYTE *)v14 + 25) >= 3u )
      {
        WPP_SF_(v14[2], 31, &WPP_679b317bfb4035ff28fff86d621cec42_Traceguids);
        v14 = WPP_GLOBAL_Control;
      }
      v13 = 0;
    }
    if ( !a6 )
    {
      if ( a5 )
      {
        *a5 = 0;
      }
      else
      {
        if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 1) != 0 && *((_BYTE *)v14 + 25) >= 3u )
          WPP_SF_(v14[2], 32, &WPP_679b317bfb4035ff28fff86d621cec42_Traceguids);
        v13 = 0;
      }
      v10 = (struct _GUID *)&v25;
    }
    *v10 = 0;
    if ( a7 )
      *a7 = 0;
    v15 = (enum _STORAGE_TIER_CLASS *)&v22;
    if ( a8 )
      v15 = a8;
    *v15 = StorageTierClassUnspecified;
    if ( !v13 )
      return ATL::AtlHresultFromWin32(87);
    TieredVolumeByVolumeName_StrongValidation = CTieringEngineLib::GetTieredVolumeByVolumeName_StrongValidation(
                                                  (CTieringEngineLib *)TieringEngineLibInstance,
                                                  a2,
                                                  &v23);
    if ( TieredVolumeByVolumeName_StrongValidation >= 0 )
    {
      TieredVolumeByVolumeName_StrongValidation = CTieredVolume::IsFilePinned_ApiHandler(
                                                    v23,
                                                    (struct TE_FILE_ID_128 *)a3,
                                                    v15);
      if ( TieredVolumeByVolumeName_StrongValidation >= 0 )
      {
        if ( *v15 )
        {
          v21 = 0;
          if ( a7 )
          {
            v21 = (unsigned __int16 *)CoTaskMemAlloc(0x200u);
            *a7 = v21;
          }
          *v24 = 1;
          CTieredVolume::GetTierInfo(v23, *v15, v10, v21);
        }
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_LiiS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v19,
            v20,
            *v15,
            *(_QWORD *)&a3->Identifier[8],
            *(_QWORD *)a3->Identifier,
            (__int64)a2);
        }
        return (unsigned int)TieredVolumeByVolumeName_StrongValidation;
      }
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return (unsigned int)TieredVolumeByVolumeName_StrongValidation;
      }
      v18 = 34;
    }
    else
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return (unsigned int)TieredVolumeByVolumeName_StrongValidation;
      }
      v18 = 33;
    }
    WPP_SF_Sd(
      v17[2],
      v18,
      (unsigned int)&WPP_679b317bfb4035ff28fff86d621cec42_Traceguids,
      (_DWORD)a2,
      TieredVolumeByVolumeName_StrongValidation);
    return (unsigned int)TieredVolumeByVolumeName_StrongValidation;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_679b317bfb4035ff28fff86d621cec42_Traceguids, 2147500033LL);
  }
  return 2147500033LL;
}

```

## disassembly

```asm
0x14003a610  push    rbx
0x14003a612  push    rsi
0x14003a613  push    rdi
0x14003a614  push    r12
0x14003a616  push    r13
0x14003a618  push    r14
0x14003a61a  push    r15
0x14003a61c  sub     rsp, 70h
0x14003a620  mov     rax, cs:?TieringEngineLibInstance@@3PEAVCTieringEngineLib@@EA; CTieringEngineLib * TieringEngineLibInstance
0x14003a627  xorps   xmm0, xmm0
0x14003a62a  mov     rsi, [rsp+0A8h+arg_38]
0x14003a632  mov     r13, r8
0x14003a635  mov     rdi, [rsp+0A8h+arg_20]
0x14003a63d  mov     r12, rdx
0x14003a640  mov     r14, [rsp+0A8h+arg_28]
0x14003a648  cmp     byte ptr [rax+8Ch], 1
0x14003a64f  mov     r15, [rsp+0A8h+arg_30]
0x14003a657  mov     [rsp+0A8h+var_58], r9
0x14003a65c  mov     [rsp+0A8h+var_60], 0
0x14003a665  movups  [rsp+0A8h+var_50], xmm0
0x14003a66a  mov     [rsp+0A8h+var_68], 0
0x14003a672  jz      short loc_14003A6B7
0x14003a674  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a67b  lea     rbx, WPP_GLOBAL_Control
0x14003a682  mov     edi, 80004001h
0x14003a687  cmp     rcx, rbx
0x14003a68a  jz      short loc_14003A6B0
0x14003a68c  test    byte ptr [rcx+1Ch], 1
0x14003a690  jz      short loc_14003A6B0
0x14003a692  cmp     byte ptr [rcx+19h], 2
0x14003a696  jb      short loc_14003A6B0
0x14003a698  mov     rcx, [rcx+10h]
0x14003a69c  lea     r8, WPP_679b317bfb4035ff28fff86d621cec42_Traceguids
0x14003a6a3  mov     edx, 1Dh
0x14003a6a8  mov     r9d, edi
0x14003a6ab  call    WPP_SF_d
0x14003a6b0  mov     eax, edi
0x14003a6b2  jmp     loc_14003A8D0
0x14003a6b7  lea     rbx, WPP_GLOBAL_Control
0x14003a6be  mov     al, 1
0x14003a6c0  test    r13, r13
0x14003a6c3  jnz     short loc_14003A700
0x14003a6c5  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a6cc  cmp     rcx, rbx
0x14003a6cf  jz      short loc_14003A6FC
0x14003a6d1  test    [rcx+1Ch], al
0x14003a6d4  jz      short loc_14003A6FC
0x14003a6d6  cmp     byte ptr [rcx+19h], 3
0x14003a6da  jb      short loc_14003A6FC
0x14003a6dc  mov     rcx, [rcx+10h]
0x14003a6e0  lea     edx, [r13+1Eh]
0x14003a6e4  lea     r8, WPP_679b317bfb4035ff28fff86d621cec42_Traceguids
0x14003a6eb  call    WPP_SF_
0x14003a6f0  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a6f7  mov     r9, [rsp+0A8h+var_58]
0x14003a6fc  xor     al, al
0x14003a6fe  jmp     short loc_14003A707
0x14003a700  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a707  test    r9, r9
0x14003a70a  jz      short loc_14003A71C
0x14003a70c  mov     dword ptr [r9], 0
0x14003a713  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a71a  jmp     short loc_14003A74B
0x14003a71c  cmp     rcx, rbx
0x14003a71f  jz      short loc_14003A749
0x14003a721  test    byte ptr [rcx+1Ch], 1
0x14003a725  jz      short loc_14003A749
0x14003a727  cmp     byte ptr [rcx+19h], 3
0x14003a72b  jb      short loc_14003A749
0x14003a72d  mov     rcx, [rcx+10h]
0x14003a731  lea     r8, WPP_679b317bfb4035ff28fff86d621cec42_Traceguids
0x14003a738  mov     edx, 1Fh
0x14003a73d  call    WPP_SF_
0x14003a742  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a749  xor     al, al
0x14003a74b  test    r14, r14
0x14003a74e  jnz     short loc_14003A787
0x14003a750  test    rdi, rdi
0x14003a753  jz      short loc_14003A75A
0x14003a755  mov     [rdi], r14d
0x14003a758  jmp     short loc_14003A782
0x14003a75a  cmp     rcx, rbx
0x14003a75d  jz      short loc_14003A780
0x14003a75f  test    byte ptr [rcx+1Ch], 1
0x14003a763  jz      short loc_14003A780
0x14003a765  cmp     byte ptr [rcx+19h], 3
0x14003a769  jb      short loc_14003A780
0x14003a76b  mov     rcx, [rcx+10h]
0x14003a76f  lea     r8, WPP_679b317bfb4035ff28fff86d621cec42_Traceguids
0x14003a776  mov     edx, 20h ; ' '
0x14003a77b  call    WPP_SF_
0x14003a780  xor     al, al
0x14003a782  lea     r14, [rsp+0A8h+var_50]
0x14003a787  xorps   xmm0, xmm0
0x14003a78a  movups  xmmword ptr [r14], xmm0
0x14003a78e  test    r15, r15
0x14003a791  jz      short loc_14003A79A
0x14003a793  mov     qword ptr [r15], 0
0x14003a79a  test    rsi, rsi
0x14003a79d  lea     rdi, [rsp+0A8h+var_68]
0x14003a7a2  cmovnz  rdi, rsi
0x14003a7a6  mov     dword ptr [rdi], 0
0x14003a7ac  test    al, al
0x14003a7ae  jnz     short loc_14003A7BF
0x14003a7b0  mov     ecx, 57h ; 'W'; unsigned int
0x14003a7b5  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x14003a7ba  jmp     loc_14003A8D0
0x14003a7bf  mov     rcx, cs:?TieringEngineLibInstance@@3PEAVCTieringEngineLib@@EA; this
0x14003a7c6  lea     r8, [rsp+0A8h+var_60]; struct CTieredVolume **
0x14003a7cb  mov     rdx, r12; unsigned __int16 *
0x14003a7ce  call    ?GetTieredVolumeByVolumeName_StrongValidation@CTieringEngineLib@@QEAAJPEAGPEAPEAVCTieredVolume@@@Z; CTieringEngineLib::GetTieredVolumeByVolumeName_StrongValidation(ushort *,CTieredVolume * *)
0x14003a7d3  mov     esi, eax
0x14003a7d5  test    eax, eax
0x14003a7d7  jns     short loc_14003A804
0x14003a7d9  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a7e0  cmp     rcx, rbx
0x14003a7e3  jz      loc_14003A8CE
0x14003a7e9  test    byte ptr [rcx+1Ch], 1
0x14003a7ed  jz      loc_14003A8CE
0x14003a7f3  cmp     byte ptr [rcx+19h], 2
0x14003a7f7  jb      loc_14003A8CE
0x14003a7fd  mov     edx, 21h ; '!'
0x14003a802  jmp     short loc_14003A843
0x14003a804  mov     rcx, [rsp+0A8h+var_60]; this
0x14003a809  mov     r8, rdi; enum _STORAGE_TIER_CLASS *
0x14003a80c  mov     rdx, r13; struct TE_FILE_ID_128 *
0x14003a80f  call    ?IsFilePinned_ApiHandler@CTieredVolume@@QEAAJPEAUTE_FILE_ID_128@@PEAW4_STORAGE_TIER_CLASS@@@Z; CTieredVolume::IsFilePinned_ApiHandler(TE_FILE_ID_128 *,_STORAGE_TIER_CLASS *)
0x14003a814  mov     esi, eax
0x14003a816  test    eax, eax
0x14003a818  jns     short loc_14003A85C
0x14003a81a  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a821  cmp     rcx, rbx
0x14003a824  jz      loc_14003A8CE
0x14003a82a  test    byte ptr [rcx+1Ch], 1
0x14003a82e  jz      loc_14003A8CE
0x14003a834  cmp     byte ptr [rcx+19h], 2
0x14003a838  jb      loc_14003A8CE
0x14003a83e  mov     edx, 22h ; '"'
0x14003a843  mov     rcx, [rcx+10h]
0x14003a847  lea     r8, WPP_679b317bfb4035ff28fff86d621cec42_Traceguids
0x14003a84e  mov     r9, r12
0x14003a851  mov     dword ptr [rsp+0A8h+var_88], esi
0x14003a855  call    WPP_SF_Sd
0x14003a85a  jmp     short loc_14003A8CE
0x14003a85c  cmp     dword ptr [rdi], 0
0x14003a85f  jz      short loc_14003A893
0x14003a861  xor     eax, eax
0x14003a863  test    r15, r15
0x14003a866  jz      short loc_14003A876
0x14003a868  mov     ecx, 200h; cb
0x14003a86d  call    cs:__imp_CoTaskMemAlloc
0x14003a873  mov     [r15], rax
0x14003a876  mov     rcx, [rsp+0A8h+var_58]
0x14003a87b  mov     r9, rax; unsigned __int16 *
0x14003a87e  mov     r8, r14; struct _GUID *
0x14003a881  mov     dword ptr [rcx], 1
0x14003a887  mov     edx, [rdi]; enum _STORAGE_TIER_CLASS
0x14003a889  mov     rcx, [rsp+0A8h+var_60]; this
0x14003a88e  call    ?GetTierInfo@CTieredVolume@@QEAAJW4_STORAGE_TIER_CLASS@@PEAU_GUID@@PEAG@Z; CTieredVolume::GetTierInfo(_STORAGE_TIER_CLASS,_GUID *,ushort *)
0x14003a893  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a89a  cmp     rcx, rbx
0x14003a89d  jz      short loc_14003A8CE
0x14003a89f  test    byte ptr [rcx+1Ch], 1
0x14003a8a3  jz      short loc_14003A8CE
0x14003a8a5  cmp     byte ptr [rcx+19h], 5
0x14003a8a9  jb      short loc_14003A8CE
0x14003a8ab  mov     rax, [r13+0]
0x14003a8af  mov     r9d, [rdi]
0x14003a8b2  mov     rcx, [rcx+10h]
0x14003a8b6  mov     [rsp+0A8h+var_78], r12
0x14003a8bb  mov     [rsp+0A8h+var_80], rax
0x14003a8c0  mov     rax, [r13+8]
0x14003a8c4  mov     [rsp+0A8h+var_88], rax
0x14003a8c9  call    WPP_SF_LiiS
0x14003a8ce  mov     eax, esi
0x14003a8d0  add     rsp, 70h
0x14003a8d4  pop     r15
0x14003a8d6  pop     r14
0x14003a8d8  pop     r13
0x14003a8da  pop     r12
0x14003a8dc  pop     rdi
0x14003a8dd  pop     rsi
0x14003a8de  pop     rbx
0x14003a8df  retn
```
