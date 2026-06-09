# FveEasUtil::EnableAutoUnlock(ushort const *)

- ea: `0x180072548`
- end: `0x180072798`
- name: `?EnableAutoUnlock@FveEasUtil@@SAJPEBG@Z`
- size: `592`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180079374`

## callees

- `0x180009f60`
- `0x18000dba8`
- `0x18000dc4c`
- `0x1800282b8`
- `0x18002f108`
- `0x180034070`
- `0x180072548`
- `0x18007401c`

## import_xrefs

- `FVEAPI!FveBindDataVolume` at `0x1800726f4`
- `FVEAPI!FveBindDataVolume` at `0x1800726f4`
- `FVEAPI!FveAddAuthMethodInformation` at `0x180072643`
- `FVEAPI!FveAddAuthMethodInformation` at `0x180072643`
- `FVEAPI!FveCommitChanges` at `0x180072734`
- `FVEAPI!FveCommitChanges` at `0x180072734`

## pseudocode

```c
__int64 __fastcall FveEasUtil::EnableAutoUnlock(const unsigned __int16 *a1)
{
  unsigned int FVEVolumeHandle; // eax
  int v2; // ebx
  unsigned int v3; // eax
  unsigned int v4; // eax
  PVOID *v5; // rcx
  unsigned int v6; // eax
  unsigned int v7; // eax
  unsigned int v8; // eax
  void **v10; // [rsp+30h] [rbp-39h] BYREF
  __int64 v11; // [rsp+38h] [rbp-31h]
  _DWORD v12[2]; // [rsp+40h] [rbp-29h] BYREF
  __int64 v13; // [rsp+48h] [rbp-21h]
  __int128 v14; // [rsp+50h] [rbp-19h]
  __int128 v15; // [rsp+60h] [rbp-9h]
  __int64 v16; // [rsp+70h] [rbp+7h]
  __int64 v17[2]; // [rsp+78h] [rbp+Fh] BYREF

  v12[0] = 56;
  v12[1] = 1;
  v16 = 0;
  v11 = 0;
  v10 = &Microsoft::WRL::Wrappers::HandleT<FveHandleTraits>::`vftable';
  v13 = 0x40000;
  v14 = 0;
  v15 = 0;
  *(_OWORD *)v17 = 0;
  FVEVolumeHandle = FveEasUtil::I_GetFVEVolumeHandle(a1, &v10, 0);
  v2 = FVEVolumeHandle;
  if ( !FVEVolumeHandle )
    goto LABEL_10;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      104,
      &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids,
      FVEVolumeHandle);
  if ( v2 >= 0 )
  {
LABEL_10:
    v3 = FveEasUtil::EnsureVolumeDEManaged(&v10);
    v2 = v3;
    if ( !v3 )
      goto LABEL_11;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 105, &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids, v3);
    if ( v2 >= 0 )
    {
LABEL_11:
      v4 = FveAddAuthMethodInformation(v11, v12, v17);
      v2 = v4;
      if ( !v4 )
      {
        v5 = (PVOID *)WPP_GLOBAL_Control;
LABEL_18:
        if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 8) != 0 )
          WPP_SF_S_guid_((TRACEHANDLE)v5[2], (__int64)v17);
        v6 = FveEasUtil::AllowKeyExport();
        v2 = v6;
        if ( !v6 )
          goto LABEL_26;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 108, &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids, v6);
        if ( v2 >= 0 )
        {
LABEL_26:
          v7 = FveBindDataVolume(v11, v17);
          v2 = v7;
          if ( !v7 )
            goto LABEL_31;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 109, &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids, v7);
          if ( v2 >= 0 )
          {
LABEL_31:
            v8 = FveCommitChanges(v11);
            v2 = v8;
            if ( v8 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 110, &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids, v8);
          }
        }
        goto LABEL_35;
      }
      v5 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 106, &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids, v4);
        v5 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v2 >= 0 )
        goto LABEL_18;
    }
  }
LABEL_35:
  v10 = &Microsoft::WRL::Wrappers::HandleT<FveHandleTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<FveFindHandleTraits>::Close(&v10);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180072548  push    rbp
0x18007254a  push    rbx
0x18007254b  push    rsi
0x18007254c  push    rdi
0x18007254d  push    r12
0x18007254f  push    r15
0x180072551  lea     rbp, [rsp-2Fh]
0x180072556  sub     rsp, 98h
0x18007255d  mov     rax, cs:__security_cookie
0x180072564  xor     rax, rsp
0x180072567  mov     [rbp+57h+var_38], rax
0x18007256b  xorps   xmm0, xmm0
0x18007256e  mov     [rbp+57h+var_80], 38h ; '8'
0x180072575  xor     eax, eax
0x180072577  mov     [rbp+57h+var_7C], 1
0x18007257e  xorps   xmm1, xmm1
0x180072581  mov     [rbp+57h+var_50], rax
0x180072585  lea     r12, ??_7?$HandleT@UFveHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<FveHandleTraits>::`vftable'
0x18007258c  mov     [rbp+57h+var_88], rax
0x180072590  xor     r8d, r8d
0x180072593  mov     [rbp+57h+var_90], r12
0x180072597  lea     rdx, [rbp+57h+var_90]
0x18007259b  mov     [rbp+57h+var_78], 40000h
0x1800725a3  movdqu  [rbp+57h+var_70], xmm0
0x1800725a8  mov     rdi, rcx
0x1800725ab  movups  [rbp+57h+var_60], xmm1
0x1800725af  movups  xmmword ptr [rbp+57h+var_48], xmm0
0x1800725b3  call    ?I_GetFVEVolumeHandle@FveEasUtil@@CAJPEBGAEAV?$HandleT@UFveHandleTraits@@@Wrappers@WRL@Microsoft@@_N@Z; FveEasUtil::I_GetFVEVolumeHandle(ushort const *,Microsoft::WRL::Wrappers::HandleT<FveHandleTraits> &,bool)
0x1800725b8  lea     rsi, WPP_GLOBAL_Control
0x1800725bf  mov     ebx, eax
0x1800725c1  lea     r15, WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids
0x1800725c8  test    eax, eax
0x1800725ca  jz      short loc_1800725FA
0x1800725cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800725d3  cmp     rcx, rsi
0x1800725d6  jz      short loc_1800725F2
0x1800725d8  test    byte ptr [rcx+1Ch], 40h
0x1800725dc  jz      short loc_1800725F2
0x1800725de  mov     rcx, [rcx+10h]
0x1800725e2  mov     edx, 68h ; 'h'
0x1800725e7  mov     r9d, eax
0x1800725ea  mov     r8, r15
0x1800725ed  call    WPP_SF_d
0x1800725f2  test    ebx, ebx
0x1800725f4  js      loc_18007276C
0x1800725fa  lea     rcx, [rbp+57h+var_90]
0x1800725fe  call    ?EnsureVolumeDEManaged@FveEasUtil@@SAJAEBV?$HandleT@UFveHandleTraits@@@Wrappers@WRL@Microsoft@@@Z; FveEasUtil::EnsureVolumeDEManaged(Microsoft::WRL::Wrappers::HandleT<FveHandleTraits> const &)
0x180072603  mov     ebx, eax
0x180072605  test    eax, eax
0x180072607  jz      short loc_180072637
0x180072609  mov     rcx, cs:WPP_GLOBAL_Control
0x180072610  cmp     rcx, rsi
0x180072613  jz      short loc_18007262F
0x180072615  test    byte ptr [rcx+1Ch], 40h
0x180072619  jz      short loc_18007262F
0x18007261b  mov     rcx, [rcx+10h]
0x18007261f  mov     edx, 69h ; 'i'
0x180072624  mov     r9d, eax
0x180072627  mov     r8, r15
0x18007262a  call    WPP_SF_d
0x18007262f  test    ebx, ebx
0x180072631  js      loc_18007276C
0x180072637  mov     rcx, [rbp+57h+var_88]
0x18007263b  lea     r8, [rbp+57h+var_48]
0x18007263f  lea     rdx, [rbp+57h+var_80]
0x180072643  call    cs:__imp_FveAddAuthMethodInformation
0x18007264a  nop     dword ptr [rax+rax+00h]
0x18007264f  mov     ebx, eax
0x180072651  test    eax, eax
0x180072653  jz      short loc_18007268C
0x180072655  mov     rcx, cs:WPP_GLOBAL_Control
0x18007265c  cmp     rcx, rsi
0x18007265f  jz      short loc_180072682
0x180072661  test    byte ptr [rcx+1Ch], 40h
0x180072665  jz      short loc_180072682
0x180072667  mov     rcx, [rcx+10h]
0x18007266b  mov     edx, 6Ah ; 'j'
0x180072670  mov     r9d, eax
0x180072673  mov     r8, r15
0x180072676  call    WPP_SF_d
0x18007267b  mov     rcx, cs:WPP_GLOBAL_Control
0x180072682  test    ebx, ebx
0x180072684  js      loc_18007276C
0x18007268a  jmp     short loc_180072693
0x18007268c  mov     rcx, cs:WPP_GLOBAL_Control
0x180072693  cmp     rcx, rsi
0x180072696  jz      short loc_1800726B3
0x180072698  test    byte ptr [rcx+1Ch], 8
0x18007269c  jz      short loc_1800726B3
0x18007269e  mov     rcx, [rcx+10h]; LoggerHandle
0x1800726a2  lea     rax, [rbp+57h+var_48]
0x1800726a6  mov     r9, rdi
0x1800726a9  mov     [rsp+0C0h+var_A0], rax; __int64
0x1800726ae  call    WPP_SF_S_guid_
0x1800726b3  call    ?AllowKeyExport@FveEasUtil@@CAJXZ; FveEasUtil::AllowKeyExport(void)
0x1800726b8  mov     ebx, eax
0x1800726ba  test    eax, eax
0x1800726bc  jz      short loc_1800726EC
0x1800726be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800726c5  cmp     rcx, rsi
0x1800726c8  jz      short loc_1800726E4
0x1800726ca  test    byte ptr [rcx+1Ch], 40h
0x1800726ce  jz      short loc_1800726E4
0x1800726d0  mov     rcx, [rcx+10h]
0x1800726d4  mov     edx, 6Ch ; 'l'
0x1800726d9  mov     r9d, eax
0x1800726dc  mov     r8, r15
0x1800726df  call    WPP_SF_d
0x1800726e4  test    ebx, ebx
0x1800726e6  js      loc_18007276C
0x1800726ec  mov     rcx, [rbp+57h+var_88]
0x1800726f0  lea     rdx, [rbp+57h+var_48]
0x1800726f4  call    cs:__imp_FveBindDataVolume
0x1800726fb  nop     dword ptr [rax+rax+00h]
0x180072700  mov     ebx, eax
0x180072702  test    eax, eax
0x180072704  jz      short loc_180072730
0x180072706  mov     rcx, cs:WPP_GLOBAL_Control
0x18007270d  cmp     rcx, rsi
0x180072710  jz      short loc_18007272C
0x180072712  test    byte ptr [rcx+1Ch], 40h
0x180072716  jz      short loc_18007272C
0x180072718  mov     rcx, [rcx+10h]
0x18007271c  mov     edx, 6Dh ; 'm'
0x180072721  mov     r9d, eax
0x180072724  mov     r8, r15
0x180072727  call    WPP_SF_d
0x18007272c  test    ebx, ebx
0x18007272e  js      short loc_18007276C
0x180072730  mov     rcx, [rbp+57h+var_88]
0x180072734  call    cs:__imp_FveCommitChanges
0x18007273b  nop     dword ptr [rax+rax+00h]
0x180072740  mov     ebx, eax
0x180072742  test    eax, eax
0x180072744  jz      short loc_18007276C
0x180072746  mov     rcx, cs:WPP_GLOBAL_Control
0x18007274d  cmp     rcx, rsi
0x180072750  jz      short loc_18007276C
0x180072752  test    byte ptr [rcx+1Ch], 40h
0x180072756  jz      short loc_18007276C
0x180072758  mov     rcx, [rcx+10h]
0x18007275c  mov     edx, 6Eh ; 'n'
0x180072761  mov     r9d, eax
0x180072764  mov     r8, r15
0x180072767  call    WPP_SF_d
0x18007276c  lea     rcx, [rbp+57h+var_90]
0x180072770  mov     [rbp+57h+var_90], r12
0x180072774  call    ?Close@?$HandleT@UFveFindHandleTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<FveFindHandleTraits>::Close(void)
0x180072779  mov     eax, ebx
0x18007277b  mov     rcx, [rbp+57h+var_38]
0x18007277f  xor     rcx, rsp; StackCookie
0x180072782  call    __security_check_cookie
0x180072787  add     rsp, 98h
0x18007278e  pop     r15
0x180072790  pop     r12
0x180072792  pop     rdi
0x180072793  pop     rsi
0x180072794  pop     rbx
0x180072795  pop     rbp
0x180072796  retn
```
