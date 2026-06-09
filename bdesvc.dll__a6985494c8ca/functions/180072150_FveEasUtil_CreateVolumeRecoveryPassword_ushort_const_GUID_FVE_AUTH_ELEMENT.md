# FveEasUtil::CreateVolumeRecoveryPassword(ushort const *,_GUID *,_FVE_AUTH_ELEMENT *)

- ea: `0x180072150`
- end: `0x18007253f`
- name: `?CreateVolumeRecoveryPassword@FveEasUtil@@QEBAJPEBGPEAU_GUID@@PEAU_FVE_AUTH_ELEMENT@@@Z`
- size: `1007`
- prototype: `int(FveEasUtil *__hidden this, const unsigned __int16 *, struct _GUID *, struct _FVE_AUTH_ELEMENT *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180075754`

## callees

- `0x180009f30`
- `0x180009f60`
- `0x18000dba8`
- `0x18000dc4c`
- `0x180024468`
- `0x1800282b8`
- `0x180034070`
- `0x180072150`
- `0x180073410`
- `0x18007e010`

## import_xrefs

- `FVEAPI!FveAddAuthMethodInformation` at `0x180072332`
- `FVEAPI!FveAddAuthMethodInformation` at `0x180072332`
- `FVEAPI!FveCommitChanges` at `0x180072388`
- `FVEAPI!FveCommitChanges` at `0x180072388`
- `FVEAPI!FveGetIdentity` at `0x1800723fd`
- `FVEAPI!FveGetIdentity` at `0x1800723fd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall FveEasUtil::CreateVolumeRecoveryPassword(
        FveEasUtil *this,
        const unsigned __int16 *a2,
        struct _GUID *a3,
        struct _FVE_AUTH_ELEMENT *a4)
{
  int VolumeRecoveryPassword; // eax
  int FVEVolumeHandle; // ebx
  PVOID *v10; // rcx
  __int64 v11; // rdx
  int StatusFlags; // eax
  __int64 (__fastcall ***v13)(_QWORD, __int64, __int128 *, struct _GUID *, _DWORD); // rcx
  __int64 v14; // rdx
  unsigned int v16; // [rsp+30h] [rbp-59h] BYREF
  void **v17; // [rsp+38h] [rbp-51h] BYREF
  void *v18; // [rsp+40h] [rbp-49h]
  _DWORD v19[2]; // [rsp+48h] [rbp-41h] BYREF
  __int64 v20; // [rsp+50h] [rbp-39h]
  __int128 v21; // [rsp+58h] [rbp-31h]
  __int128 v22; // [rsp+68h] [rbp-21h]
  __int64 v23; // [rsp+78h] [rbp-11h]
  struct _GUID v24; // [rsp+80h] [rbp-9h] BYREF
  __int128 v25; // [rsp+90h] [rbp+7h] BYREF

  v19[0] = 56;
  v19[1] = 1;
  v20 = 0x80000;
  v21 = 0;
  v22 = 0;
  v23 = 0;
  v16 = 0;
  v24 = 0;
  v17 = &Microsoft::WRL::Wrappers::HandleT<FveHandleTraits>::`vftable';
  v18 = 0;
  v25 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 77, &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids);
  VolumeRecoveryPassword = FveEasUtil::GetVolumeRecoveryPassword(a2, a3, a4);
  FVEVolumeHandle = VolumeRecoveryPassword;
  if ( !VolumeRecoveryPassword )
    goto LABEL_54;
  if ( VolumeRecoveryPassword == -2147023728 )
  {
    FVEVolumeHandle = FveEasUtil::I_GetFVEVolumeHandle(a2, &v17, 0);
    if ( FVEVolumeHandle )
    {
      v10 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          79,
          &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids,
          (unsigned int)FVEVolumeHandle);
        v10 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( FVEVolumeHandle < 0 )
        goto LABEL_55;
    }
    FVEVolumeHandle = FveEasUtil::EnsureVolumeDEManaged(&v17);
    if ( FVEVolumeHandle )
    {
      v10 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          80,
          &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids,
          (unsigned int)FVEVolumeHandle);
        v10 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( FVEVolumeHandle < 0 )
        goto LABEL_55;
    }
    else
    {
      v10 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( *((_BYTE *)this + 48) )
    {
      if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 8) != 0 )
        WPP_SF_(v10[2], 81, &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids);
      LODWORD(v20) = v20 | 8;
    }
    FVEVolumeHandle = FveAddAuthMethodInformation(v18, v19, &v24);
    if ( !FVEVolumeHandle )
      goto LABEL_35;
    v10 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        82,
        &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids,
        (unsigned int)FVEVolumeHandle);
      v10 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( FVEVolumeHandle >= 0 )
    {
LABEL_35:
      FVEVolumeHandle = FveCommitChanges(v18);
      if ( !FVEVolumeHandle )
        goto LABEL_61;
      v10 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          83,
          &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids,
          (unsigned int)FVEVolumeHandle);
        v10 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( FVEVolumeHandle >= 0 )
      {
LABEL_61:
        if ( *((_BYTE *)this + 48) )
        {
          if ( (StatusFlags = CFveApiWrapper::GetStatusFlags(v18, &v16), StatusFlags < 0)
            || (StatusFlags = FveGetIdentity(v18, &v25), StatusFlags < 0)
            || (v13 = (__int64 (__fastcall ***)(_QWORD, __int64, __int128 *, struct _GUID *, _DWORD))*((_QWORD *)this + 4)) != 0
            && ((v16 & 0x4000) == 0 ? (v14 = (unsigned int)((v16 & 0x400000) != 0) + 1) : (v14 = 0),
                StatusFlags = (**v13)(v13, v14, &v25, &v24, 0),
                StatusFlags < 0) )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                84,
                &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids,
                (unsigned int)StatusFlags);
          }
        }
        if ( a4 )
        {
          FVEVolumeHandle = FveEasUtil::GetVolumeRecoveryPassword(a2, a3, a4);
          if ( FVEVolumeHandle )
          {
            v10 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
              goto LABEL_58;
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
              goto LABEL_55;
            v11 = 85;
            goto LABEL_53;
          }
        }
        else
        {
          *a3 = v24;
        }
LABEL_54:
        v10 = (PVOID *)WPP_GLOBAL_Control;
      }
    }
  }
  else
  {
    v10 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_58;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      v11 = 78;
LABEL_53:
      WPP_SF_d(v10[2], v11, &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids, (unsigned int)FVEVolumeHandle);
      goto LABEL_54;
    }
  }
LABEL_55:
  if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 0x20) != 0 )
    WPP_SF_d(v10[2], 86, &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids, (unsigned int)FVEVolumeHandle);
LABEL_58:
  v17 = &Microsoft::WRL::Wrappers::HandleT<FveHandleTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<FveFindHandleTraits>::Close(&v17);
  return (unsigned int)FVEVolumeHandle;
}

```

## disassembly

```asm
0x180072150  push    rbp
0x180072152  push    rbx
0x180072153  push    rsi
0x180072154  push    rdi
0x180072155  push    r12
0x180072157  push    r14
0x180072159  push    r15
0x18007215b  lea     rbp, [rsp-27h]
0x180072160  sub     rsp, 0B0h
0x180072167  mov     rax, cs:__security_cookie
0x18007216e  xor     rax, rsp
0x180072171  mov     [rbp+57h+var_40], rax
0x180072175  mov     r15, r9
0x180072178  mov     r14, r8
0x18007217b  mov     r12, rdx
0x18007217e  mov     rsi, rcx
0x180072181  mov     [rbp+57h+var_98], 38h ; '8'
0x180072188  mov     [rbp+57h+var_94], 1
0x18007218f  mov     [rbp+57h+var_90], 80000h
0x180072197  xorps   xmm0, xmm0
0x18007219a  movdqu  [rbp+57h+var_88], xmm0
0x18007219f  xorps   xmm1, xmm1
0x1800721a2  xor     eax, eax
0x1800721a4  movups  [rbp+57h+var_78], xmm1
0x1800721a8  mov     [rbp+57h+var_68], rax
0x1800721ac  mov     [rbp+57h+var_B0], eax
0x1800721af  movups  [rbp+57h+var_60], xmm0
0x1800721b3  lea     rax, ??_7?$HandleT@UFveHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<FveHandleTraits>::`vftable'
0x1800721ba  mov     [rbp+57h+var_A8], rax
0x1800721be  mov     [rbp+57h+var_A0], 0
0x1800721c6  movups  [rbp+57h+var_50], xmm0
0x1800721ca  lea     rax, WPP_GLOBAL_Control
0x1800721d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800721d8  cmp     rcx, rax
0x1800721db  jz      short loc_1800721F8
0x1800721dd  test    byte ptr [rcx+1Ch], 20h
0x1800721e1  jz      short loc_1800721F8
0x1800721e3  mov     edx, 4Dh ; 'M'
0x1800721e8  lea     r8, WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids
0x1800721ef  mov     rcx, [rcx+10h]
0x1800721f3  call    WPP_SF_
0x1800721f8  mov     r8, r15; struct _FVE_AUTH_ELEMENT *
0x1800721fb  mov     rdx, r14; struct _GUID *
0x1800721fe  mov     rcx, r12; unsigned __int16 *
0x180072201  call    ?GetVolumeRecoveryPassword@FveEasUtil@@SAJPEBGPEAU_GUID@@PEAU_FVE_AUTH_ELEMENT@@@Z; FveEasUtil::GetVolumeRecoveryPassword(ushort const *,_GUID *,_FVE_AUTH_ELEMENT *)
0x180072206  mov     ebx, eax
0x180072208  test    eax, eax
0x18007220a  jz      loc_1800724D8
0x180072210  cmp     eax, 80070490h
0x180072215  jz      short loc_180072245
0x180072217  mov     rcx, cs:WPP_GLOBAL_Control
0x18007221e  lea     rax, WPP_GLOBAL_Control
0x180072225  cmp     rcx, rax
0x180072228  jz      loc_18007250A
0x18007222e  mov     dil, 40h ; '@'
0x180072231  test    [rcx+1Ch], dil
0x180072235  jz      loc_1800724DF
0x18007223b  mov     edx, 4Eh ; 'N'
0x180072240  jmp     loc_1800724C5
0x180072245  xor     r8d, r8d
0x180072248  lea     rdx, [rbp+57h+var_A8]
0x18007224c  mov     rcx, r12
0x18007224f  call    ?I_GetFVEVolumeHandle@FveEasUtil@@CAJPEBGAEAV?$HandleT@UFveHandleTraits@@@Wrappers@WRL@Microsoft@@_N@Z; FveEasUtil::I_GetFVEVolumeHandle(ushort const *,Microsoft::WRL::Wrappers::HandleT<FveHandleTraits> &,bool)
0x180072254  mov     ebx, eax
0x180072256  mov     dil, 40h ; '@'
0x180072259  test    eax, eax
0x18007225b  jz      short loc_18007229D
0x18007225d  mov     rcx, cs:WPP_GLOBAL_Control
0x180072264  lea     rax, WPP_GLOBAL_Control
0x18007226b  cmp     rcx, rax
0x18007226e  jz      short loc_180072295
0x180072270  test    [rcx+1Ch], dil
0x180072274  jz      short loc_180072295
0x180072276  mov     edx, 4Fh ; 'O'
0x18007227b  mov     r9d, ebx
0x18007227e  lea     r8, WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids
0x180072285  mov     rcx, [rcx+10h]
0x180072289  call    WPP_SF_d
0x18007228e  mov     rcx, cs:WPP_GLOBAL_Control
0x180072295  test    ebx, ebx
0x180072297  js      loc_1800724DF
0x18007229d  lea     rcx, [rbp+57h+var_A8]
0x1800722a1  call    ?EnsureVolumeDEManaged@FveEasUtil@@SAJAEBV?$HandleT@UFveHandleTraits@@@Wrappers@WRL@Microsoft@@@Z; FveEasUtil::EnsureVolumeDEManaged(Microsoft::WRL::Wrappers::HandleT<FveHandleTraits> const &)
0x1800722a6  mov     ebx, eax
0x1800722a8  test    eax, eax
0x1800722aa  jz      short loc_1800722EE
0x1800722ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800722b3  lea     rax, WPP_GLOBAL_Control
0x1800722ba  cmp     rcx, rax
0x1800722bd  jz      short loc_1800722E4
0x1800722bf  test    [rcx+1Ch], dil
0x1800722c3  jz      short loc_1800722E4
0x1800722c5  mov     edx, 50h ; 'P'
0x1800722ca  mov     r9d, ebx
0x1800722cd  lea     r8, WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids
0x1800722d4  mov     rcx, [rcx+10h]
0x1800722d8  call    WPP_SF_d
0x1800722dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800722e4  test    ebx, ebx
0x1800722e6  js      loc_1800724DF
0x1800722ec  jmp     short loc_1800722F5
0x1800722ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800722f5  cmp     byte ptr [rsi+30h], 0
0x1800722f9  jz      short loc_180072326
0x1800722fb  lea     rax, WPP_GLOBAL_Control
0x180072302  cmp     rcx, rax
0x180072305  jz      short loc_180072322
0x180072307  test    byte ptr [rcx+1Ch], 8
0x18007230b  jz      short loc_180072322
0x18007230d  mov     edx, 51h ; 'Q'
0x180072312  lea     r8, WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids
0x180072319  mov     rcx, [rcx+10h]
0x18007231d  call    WPP_SF_
0x180072322  or      dword ptr [rbp+57h+var_90], 8
0x180072326  lea     r8, [rbp+57h+var_60]
0x18007232a  lea     rdx, [rbp+57h+var_98]
0x18007232e  mov     rcx, [rbp+57h+var_A0]
0x180072332  call    cs:__imp_FveAddAuthMethodInformation
0x180072339  nop     dword ptr [rax+rax+00h]
0x18007233e  mov     ebx, eax
0x180072340  test    eax, eax
0x180072342  jz      short loc_180072384
0x180072344  mov     rcx, cs:WPP_GLOBAL_Control
0x18007234b  lea     rax, WPP_GLOBAL_Control
0x180072352  cmp     rcx, rax
0x180072355  jz      short loc_18007237C
0x180072357  test    [rcx+1Ch], dil
0x18007235b  jz      short loc_18007237C
0x18007235d  mov     edx, 52h ; 'R'
0x180072362  mov     r9d, ebx
0x180072365  lea     r8, WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids
0x18007236c  mov     rcx, [rcx+10h]
0x180072370  call    WPP_SF_d
0x180072375  mov     rcx, cs:WPP_GLOBAL_Control
0x18007237c  test    ebx, ebx
0x18007237e  js      loc_1800724DF
0x180072384  mov     rcx, [rbp+57h+var_A0]
0x180072388  call    cs:__imp_FveCommitChanges
0x18007238f  nop     dword ptr [rax+rax+00h]
0x180072394  mov     ebx, eax
0x180072396  test    eax, eax
0x180072398  jz      short loc_1800723DA
0x18007239a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800723a1  lea     rax, WPP_GLOBAL_Control
0x1800723a8  cmp     rcx, rax
0x1800723ab  jz      short loc_1800723D2
0x1800723ad  test    [rcx+1Ch], dil
0x1800723b1  jz      short loc_1800723D2
0x1800723b3  mov     edx, 53h ; 'S'
0x1800723b8  mov     r9d, ebx
0x1800723bb  lea     r8, WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids
0x1800723c2  mov     rcx, [rcx+10h]
0x1800723c6  call    WPP_SF_d
0x1800723cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800723d2  test    ebx, ebx
0x1800723d4  js      loc_1800724DF
0x1800723da  cmp     byte ptr [rsi+30h], 0
0x1800723de  jz      loc_180072483
0x1800723e4  lea     rdx, [rbp+57h+var_B0]; unsigned int *
0x1800723e8  mov     rcx, [rbp+57h+var_A0]; void *
0x1800723ec  call    ?GetStatusFlags@CFveApiWrapper@@SAJPEAXPEAK@Z; CFveApiWrapper::GetStatusFlags(void *,ulong *)
0x1800723f1  test    eax, eax
0x1800723f3  js      short loc_180072452
0x1800723f5  lea     rdx, [rbp+57h+var_50]
0x1800723f9  mov     rcx, [rbp+57h+var_A0]
0x1800723fd  call    cs:__imp_FveGetIdentity
0x180072404  nop     dword ptr [rax+rax+00h]
0x180072409  test    eax, eax
0x18007240b  js      short loc_180072452
0x18007240d  mov     rcx, [rsi+20h]
0x180072411  test    rcx, rcx
0x180072414  jz      short loc_180072483
0x180072416  mov     rax, [rcx]
0x180072419  mov     r10, [rax]
0x18007241c  mov     eax, [rbp+57h+var_B0]
0x18007241f  bt      eax, 0Eh
0x180072423  jnb     short loc_180072429
0x180072425  xor     edx, edx
0x180072427  jmp     short loc_180072436
0x180072429  and     eax, 400000h
0x18007242e  neg     eax
0x180072430  sbb     edx, edx
0x180072432  neg     edx
0x180072434  inc     edx
0x180072436  mov     [rsp+0E0h+var_C0], 0
0x18007243e  lea     r9, [rbp+57h+var_60]
0x180072442  lea     r8, [rbp+57h+var_50]
0x180072446  mov     rax, r10
0x180072449  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007244e  test    eax, eax
0x180072450  jns     short loc_180072483
0x180072452  mov     rcx, cs:WPP_GLOBAL_Control
0x180072459  lea     rdx, WPP_GLOBAL_Control
0x180072460  cmp     rcx, rdx
0x180072463  jz      short loc_180072483
0x180072465  test    byte ptr [rcx+1Ch], 4
0x180072469  jz      short loc_180072483
0x18007246b  mov     edx, 54h ; 'T'
0x180072470  mov     r9d, eax
0x180072473  lea     r8, WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids
0x18007247a  mov     rcx, [rcx+10h]
0x18007247e  call    WPP_SF_d
0x180072483  test    r15, r15
0x180072486  jnz     short loc_180072493
0x180072488  movups  xmm0, [rbp+57h+var_60]
0x18007248c  movdqu  xmmword ptr [r14], xmm0
0x180072491  jmp     short loc_1800724D8
0x180072493  mov     r8, r15; struct _FVE_AUTH_ELEMENT *
0x180072496  mov     rdx, r14; struct _GUID *
0x180072499  mov     rcx, r12; unsigned __int16 *
0x18007249c  call    ?GetVolumeRecoveryPassword@FveEasUtil@@SAJPEBGPEAU_GUID@@PEAU_FVE_AUTH_ELEMENT@@@Z; FveEasUtil::GetVolumeRecoveryPassword(ushort const *,_GUID *,_FVE_AUTH_ELEMENT *)
0x1800724a1  mov     ebx, eax
0x1800724a3  test    eax, eax
0x1800724a5  jz      short loc_1800724D8
0x1800724a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800724ae  lea     rax, WPP_GLOBAL_Control
0x1800724b5  cmp     rcx, rax
0x1800724b8  jz      short loc_18007250A
0x1800724ba  test    [rcx+1Ch], dil
0x1800724be  jz      short loc_1800724DF
0x1800724c0  mov     edx, 55h ; 'U'
0x1800724c5  mov     r9d, ebx
0x1800724c8  lea     r8, WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids
0x1800724cf  mov     rcx, [rcx+10h]
0x1800724d3  call    WPP_SF_d
0x1800724d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800724df  lea     rdi, WPP_GLOBAL_Control
0x1800724e6  cmp     rcx, rdi
0x1800724e9  jz      short loc_18007250A
0x1800724eb  test    byte ptr [rcx+1Ch], 20h
0x1800724ef  jz      short loc_18007250A
0x1800724f1  mov     edx, 56h ; 'V'
0x1800724f6  mov     r9d, ebx
0x1800724f9  lea     r8, WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids
0x180072500  mov     rcx, [rcx+10h]
0x180072504  call    WPP_SF_d
0x180072509  nop
0x18007250a  lea     rax, ??_7?$HandleT@UFveHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<FveHandleTraits>::`vftable'
0x180072511  mov     [rbp+57h+var_A8], rax
0x180072515  lea     rcx, [rbp+57h+var_A8]
0x180072519  call    ?Close@?$HandleT@UFveFindHandleTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<FveFindHandleTraits>::Close(void)
0x18007251e  mov     eax, ebx
0x180072520  mov     rcx, [rbp+57h+var_40]
0x180072524  xor     rcx, rsp; StackCookie
0x180072527  call    __security_check_cookie
0x18007252c  add     rsp, 0B0h
0x180072533  pop     r15
0x180072535  pop     r14
0x180072537  pop     r12
0x180072539  pop     rdi
0x18007253a  pop     rsi
0x18007253b  pop     rbx
0x18007253c  pop     rbp
0x18007253d  retn
```
