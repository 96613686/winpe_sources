# CallbackDecrementClearKeyCounterOrResumeProtection(ushort const *,bool)

- ea: `0x180032b74`
- end: `0x180032f57`
- name: `?CallbackDecrementClearKeyCounterOrResumeProtection@@YAJPEBG_N@Z`
- size: `995`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int8)`
- caller_count: `2`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180032b20`
- `0x180047e6c`

## callees

- `0x180009f30`
- `0x180009f60`
- `0x18000dba8`
- `0x18000dc4c`
- `0x180032b74`
- `0x180034070`
- `0x180039cb4`
- `0x1800471f4`
- `0x180047a40`
- `0x180048480`
- `0x1800717fc`

## import_xrefs

- `FVEAPI!FveDecrementClearKeyCounter` at `0x180032cd8`
- `FVEAPI!FveDecrementClearKeyCounter` at `0x180032e82`
- `FVEAPI!FveDecrementClearKeyCounter` at `0x180032cd8`
- `FVEAPI!FveDecrementClearKeyCounter` at `0x180032e82`
- `FVEAPI!FveCommitChangesEx` at `0x180032ca8`
- `FVEAPI!FveCommitChangesEx` at `0x180032ca8`
- `FVEAPI!FveCommitChanges` at `0x180032e51`
- `FVEAPI!FveCommitChanges` at `0x180032e51`

## pseudocode

```c
__int64 __fastcall CallbackDecrementClearKeyCounterOrResumeProtection(const unsigned __int16 *a1, unsigned __int8 a2)
{
  unsigned int v2; // r15d
  bool v4; // si
  PVOID *v5; // rcx
  __int64 v6; // rdx
  unsigned int v7; // eax
  int v8; // ebx
  int v9; // eax
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rdx
  unsigned __int16 v13; // r14
  unsigned int v14; // ecx
  int v15; // eax
  unsigned int FVEVolumeHandle; // eax
  int v17; // eax
  _QWORD *v18; // rcx
  __int64 v19; // rdx
  bool v21; // [rsp+20h] [rbp-20h] BYREF
  void **v22; // [rsp+28h] [rbp-18h] BYREF
  void *v23; // [rsp+30h] [rbp-10h]

  v2 = a2;
  v4 = 0;
  v21 = 0;
  v5 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids);
      v5 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 8) != 0 )
      WPP_SF_d(v5[2], 35, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids, v2);
  }
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BitLocker_Improve_Backup_On_Resume_Logic>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BitLocker_Improve_Backup_On_Resume_Logic>::GetImpl'::`2'::impl) )
  {
    LOBYTE(v6) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_BitLocker_Backup_RP_On_Resume>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_BitLocker_Backup_RP_On_Resume>::GetImpl'::`2'::impl,
      v6);
    v13 = 0;
    while ( 1 )
    {
      LOBYTE(v12) = 1;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_BitLocker_Backup_RP_On_Resume>::ReportUsage(
        `wil::Feature<__WilFeatureTraits_Feature_BitLocker_Backup_RP_On_Resume>::GetImpl'::`2'::impl,
        v12);
      if ( !v4 )
      {
        v15 = CheckIsInternetAvailable(v14, &v21);
        if ( v15 >= 0 )
        {
          v4 = v21;
          if ( !v21 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids);
        }
        else
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              40,
              WPP_09423e3e68a53bdf96979f905547dd55_Traceguids,
              (unsigned int)v15);
          v4 = 0;
          v21 = 0;
        }
      }
      v22 = &Microsoft::WRL::Wrappers::HandleT<FveHandleTraits>::`vftable';
      v23 = 0;
      FVEVolumeHandle = FveEasUtil::I_GetFVEVolumeHandle(a1, &v22, 0);
      v8 = FVEVolumeHandle;
      if ( FVEVolumeHandle )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            42,
            WPP_09423e3e68a53bdf96979f905547dd55_Traceguids,
            FVEVolumeHandle);
        if ( v8 < 0 )
          goto LABEL_63;
      }
      if ( (_BYTE)v2 )
      {
        v17 = CFveApiWrapper::DeleteClearKey(v23);
        v8 = v17;
        if ( v17 >= 0 )
        {
          v17 = FveCommitChanges(v23);
          v8 = v17;
          if ( v17 >= 0 )
            goto LABEL_63;
          v18 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            v19 = 44;
            goto LABEL_58;
          }
        }
        else
        {
          v18 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            v19 = 43;
LABEL_58:
            WPP_SF_d(v18[2], v19, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids, (unsigned int)v17);
          }
        }
      }
      else
      {
        v17 = FveDecrementClearKeyCounter(v23, 0);
        v8 = v17;
        if ( v17 >= 0 )
          goto LABEL_63;
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          v19 = 45;
          goto LABEL_58;
        }
      }
      if ( v13 >= 2u )
      {
        BdeSvcLogEventResumeFailure(v23, v8);
        goto LABEL_63;
      }
      Microsoft::WRL::Wrappers::HandleT<FveFindHandleTraits>::Close(&v22);
      v22 = &Microsoft::WRL::Wrappers::HandleT<FveHandleTraits>::`vftable';
      Microsoft::WRL::Wrappers::HandleT<FveFindHandleTraits>::Close(&v22);
      if ( ++v13 >= 3u )
        goto LABEL_64;
    }
  }
  v22 = &Microsoft::WRL::Wrappers::HandleT<FveHandleTraits>::`vftable';
  v23 = 0;
  v7 = FveEasUtil::I_GetFVEVolumeHandle(a1, &v22, 0);
  v8 = v7;
  if ( v7 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids, v7);
    if ( v8 < 0 )
      goto LABEL_63;
  }
  if ( !(_BYTE)v2 )
  {
    v9 = FveDecrementClearKeyCounter(v23, 13);
    v8 = v9;
    if ( v9 < 0 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_27;
      v11 = 39;
      goto LABEL_26;
    }
LABEL_28:
    Microsoft::WRL::Wrappers::HandleT<FveFindHandleTraits>::Close(&v22);
    goto LABEL_63;
  }
  v9 = CFveApiWrapper::DeleteClearKey(v23);
  v8 = v9;
  if ( v9 >= 0 )
  {
    v9 = FveCommitChangesEx(v23, 13);
    v8 = v9;
    if ( v9 < 0 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_27;
      v11 = 38;
      goto LABEL_26;
    }
    goto LABEL_28;
  }
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
    goto LABEL_27;
  v11 = 37;
LABEL_26:
  WPP_SF_d(v10[2], v11, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids, (unsigned int)v9);
LABEL_27:
  BdeSvcLogEventResumeFailure(v23, v8);
LABEL_63:
  v22 = &Microsoft::WRL::Wrappers::HandleT<FveHandleTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<FveFindHandleTraits>::Close(&v22);
LABEL_64:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids, (unsigned int)v8);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180032b74  mov     [rsp-38h+arg_10], rbx
0x180032b79  push    rbp
0x180032b7a  push    rsi
0x180032b7b  push    rdi
0x180032b7c  push    r12
0x180032b7e  push    r13
0x180032b80  push    r14
0x180032b82  push    r15
0x180032b84  mov     rbp, rsp
0x180032b87  sub     rsp, 40h
0x180032b8b  mov     rax, cs:__security_cookie
0x180032b92  xor     rax, rsp
0x180032b95  mov     [rbp+var_8], rax
0x180032b99  movzx   r15d, dl
0x180032b9d  mov     r12, rcx
0x180032ba0  xor     sil, sil
0x180032ba3  mov     [rbp+var_20], sil
0x180032ba7  lea     r13, WPP_GLOBAL_Control
0x180032bae  mov     rcx, cs:WPP_GLOBAL_Control
0x180032bb5  cmp     rcx, r13
0x180032bb8  jz      short loc_180032BFF
0x180032bba  test    byte ptr [rcx+1Ch], 20h
0x180032bbe  jz      short loc_180032BDC
0x180032bc0  mov     edx, 22h ; '"'
0x180032bc5  lea     r8, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids
0x180032bcc  mov     rcx, [rcx+10h]
0x180032bd0  call    WPP_SF_
0x180032bd5  mov     rcx, cs:WPP_GLOBAL_Control
0x180032bdc  cmp     rcx, r13
0x180032bdf  jz      short loc_180032BFF
0x180032be1  test    byte ptr [rcx+1Ch], 8
0x180032be5  jz      short loc_180032BFF
0x180032be7  mov     r9d, r15d
0x180032bea  mov     edx, 23h ; '#'
0x180032bef  lea     r8, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids
0x180032bf6  mov     rcx, [rcx+10h]
0x180032bfa  call    WPP_SF_d
0x180032bff  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BitLocker_Improve_Backup_On_Resume_Logic@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BitLocker_Improve_Backup_On_Resume_Logic@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BitLocker_Improve_Backup_On_Resume_Logic> `wil::Feature<__WilFeatureTraits_Feature_BitLocker_Improve_Backup_On_Resume_Logic>::GetImpl(void)'::`2'::impl
0x180032c06  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BitLocker_Improve_Backup_On_Resume_Logic@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BitLocker_Improve_Backup_On_Resume_Logic>::__private_IsEnabled(void)
0x180032c0b  test    al, al
0x180032c0d  jz      loc_180032D32
0x180032c13  lea     rdi, ??_7?$HandleT@UFveHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<FveHandleTraits>::`vftable'
0x180032c1a  mov     [rbp+var_18], rdi
0x180032c1e  mov     [rbp+var_10], 0
0x180032c26  xor     r8d, r8d
0x180032c29  lea     rdx, [rbp+var_18]
0x180032c2d  mov     rcx, r12
0x180032c30  call    ?I_GetFVEVolumeHandle@FveEasUtil@@CAJPEBGAEAV?$HandleT@UFveHandleTraits@@@Wrappers@WRL@Microsoft@@_N@Z; FveEasUtil::I_GetFVEVolumeHandle(ushort const *,Microsoft::WRL::Wrappers::HandleT<FveHandleTraits> &,bool)
0x180032c35  mov     ebx, eax
0x180032c37  test    eax, eax
0x180032c39  jz      short loc_180032C6E
0x180032c3b  mov     rcx, cs:WPP_GLOBAL_Control
0x180032c42  cmp     rcx, r13
0x180032c45  jz      short loc_180032C65
0x180032c47  test    byte ptr [rcx+1Ch], 40h
0x180032c4b  jz      short loc_180032C65
0x180032c4d  mov     edx, 24h ; '$'
0x180032c52  mov     r9d, eax
0x180032c55  lea     r8, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids
0x180032c5c  mov     rcx, [rcx+10h]
0x180032c60  call    WPP_SF_d
0x180032c65  test    ebx, ebx
0x180032c67  jns     short loc_180032C6E
0x180032c69  jmp     loc_180032EF9
0x180032c6e  mov     rcx, [rbp+var_10]; void *
0x180032c72  test    r15b, r15b
0x180032c75  jz      short loc_180032CD3
0x180032c77  call    ?DeleteClearKey@CFveApiWrapper@@SAJPEAX@Z; CFveApiWrapper::DeleteClearKey(void *)
0x180032c7c  mov     ebx, eax
0x180032c7e  test    eax, eax
0x180032c80  jns     short loc_180032C9F
0x180032c82  mov     rcx, cs:WPP_GLOBAL_Control
0x180032c89  cmp     rcx, r13
0x180032c8c  jz      loc_180032D14
0x180032c92  test    byte ptr [rcx+1Ch], 2
0x180032c96  jz      short loc_180032D14
0x180032c98  mov     edx, 25h ; '%'
0x180032c9d  jmp     short loc_180032D01
0x180032c9f  mov     edx, 0Dh
0x180032ca4  mov     rcx, [rbp+var_10]
0x180032ca8  call    cs:__imp_FveCommitChangesEx
0x180032caf  nop     dword ptr [rax+rax+00h]
0x180032cb4  mov     ebx, eax
0x180032cb6  test    eax, eax
0x180032cb8  jns     short loc_180032D24
0x180032cba  mov     rcx, cs:WPP_GLOBAL_Control
0x180032cc1  cmp     rcx, r13
0x180032cc4  jz      short loc_180032D14
0x180032cc6  test    byte ptr [rcx+1Ch], 2
0x180032cca  jz      short loc_180032D14
0x180032ccc  mov     edx, 26h ; '&'
0x180032cd1  jmp     short loc_180032D01
0x180032cd3  mov     edx, 0Dh
0x180032cd8  call    cs:__imp_FveDecrementClearKeyCounter
0x180032cdf  nop     dword ptr [rax+rax+00h]
0x180032ce4  mov     ebx, eax
0x180032ce6  test    eax, eax
0x180032ce8  jns     short loc_180032D24
0x180032cea  mov     rcx, cs:WPP_GLOBAL_Control
0x180032cf1  cmp     rcx, r13
0x180032cf4  jz      short loc_180032D14
0x180032cf6  test    byte ptr [rcx+1Ch], 2
0x180032cfa  jz      short loc_180032D14
0x180032cfc  mov     edx, 27h ; '''
0x180032d01  mov     r9d, eax
0x180032d04  lea     r8, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids
0x180032d0b  mov     rcx, [rcx+10h]
0x180032d0f  call    WPP_SF_d
0x180032d14  mov     edx, ebx; int
0x180032d16  mov     rcx, [rbp+var_10]; void *
0x180032d1a  call    ?BdeSvcLogEventResumeFailure@@YAXPEAXJ@Z; BdeSvcLogEventResumeFailure(void *,long)
0x180032d1f  jmp     loc_180032C69
0x180032d24  lea     rcx, [rbp+var_18]
0x180032d28  call    ?Close@?$HandleT@UFveFindHandleTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<FveFindHandleTraits>::Close(void)
0x180032d2d  jmp     loc_180032C69
0x180032d32  mov     dl, 1
0x180032d34  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BitLocker_Backup_RP_On_Resume@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BitLocker_Backup_RP_On_Resume@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BitLocker_Backup_RP_On_Resume> `wil::Feature<__WilFeatureTraits_Feature_BitLocker_Backup_RP_On_Resume>::GetImpl(void)'::`2'::impl
0x180032d3b  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_BitLocker_Backup_RP_On_Resume@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BitLocker_Backup_RP_On_Resume>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180032d40  xor     r14d, r14d
0x180032d43  lea     rdi, ??_7?$HandleT@UFveHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<FveHandleTraits>::`vftable'
0x180032d4a  mov     dl, 1
0x180032d4c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BitLocker_Backup_RP_On_Resume@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BitLocker_Backup_RP_On_Resume@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BitLocker_Backup_RP_On_Resume> `wil::Feature<__WilFeatureTraits_Feature_BitLocker_Backup_RP_On_Resume>::GetImpl(void)'::`2'::impl
0x180032d53  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_BitLocker_Backup_RP_On_Resume@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BitLocker_Backup_RP_On_Resume>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180032d58  test    sil, sil
0x180032d5b  jnz     short loc_180032DCD
0x180032d5d  lea     rdx, [rbp+var_20]; bool *
0x180032d61  call    ?CheckIsInternetAvailable@@YAJKPEA_N@Z; CheckIsInternetAvailable(ulong,bool *)
0x180032d66  test    eax, eax
0x180032d68  jns     short loc_180032D9D
0x180032d6a  mov     rcx, cs:WPP_GLOBAL_Control
0x180032d71  cmp     rcx, r13
0x180032d74  jz      short loc_180032D94
0x180032d76  test    byte ptr [rcx+1Ch], 2
0x180032d7a  jz      short loc_180032D94
0x180032d7c  mov     edx, 28h ; '('
0x180032d81  mov     r9d, eax
0x180032d84  lea     r8, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids
0x180032d8b  mov     rcx, [rcx+10h]
0x180032d8f  call    WPP_SF_d
0x180032d94  xor     sil, sil
0x180032d97  mov     [rbp+var_20], sil
0x180032d9b  jmp     short loc_180032DCD
0x180032d9d  mov     sil, [rbp+var_20]
0x180032da1  test    sil, sil
0x180032da4  jnz     short loc_180032DCD
0x180032da6  mov     rcx, cs:WPP_GLOBAL_Control
0x180032dad  cmp     rcx, r13
0x180032db0  jz      short loc_180032DCD
0x180032db2  test    byte ptr [rcx+1Ch], 8
0x180032db6  jz      short loc_180032DCD
0x180032db8  mov     edx, 29h ; ')'
0x180032dbd  lea     r8, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids
0x180032dc4  mov     rcx, [rcx+10h]
0x180032dc8  call    WPP_SF_
0x180032dcd  mov     [rbp+var_18], rdi
0x180032dd1  mov     [rbp+var_10], 0
0x180032dd9  xor     r8d, r8d
0x180032ddc  lea     rdx, [rbp+var_18]
0x180032de0  mov     rcx, r12
0x180032de3  call    ?I_GetFVEVolumeHandle@FveEasUtil@@CAJPEBGAEAV?$HandleT@UFveHandleTraits@@@Wrappers@WRL@Microsoft@@_N@Z; FveEasUtil::I_GetFVEVolumeHandle(ushort const *,Microsoft::WRL::Wrappers::HandleT<FveHandleTraits> &,bool)
0x180032de8  mov     ebx, eax
0x180032dea  test    eax, eax
0x180032dec  jz      short loc_180032E20
0x180032dee  mov     rcx, cs:WPP_GLOBAL_Control
0x180032df5  cmp     rcx, r13
0x180032df8  jz      short loc_180032E18
0x180032dfa  test    byte ptr [rcx+1Ch], 40h
0x180032dfe  jz      short loc_180032E18
0x180032e00  mov     edx, 2Ah ; '*'
0x180032e05  mov     r9d, eax
0x180032e08  lea     r8, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids
0x180032e0f  mov     rcx, [rcx+10h]
0x180032e13  call    WPP_SF_d
0x180032e18  test    ebx, ebx
0x180032e1a  js      loc_180032EF9
0x180032e20  mov     rcx, [rbp+var_10]; void *
0x180032e24  test    r15b, r15b
0x180032e27  jz      short loc_180032E80
0x180032e29  call    ?DeleteClearKey@CFveApiWrapper@@SAJPEAX@Z; CFveApiWrapper::DeleteClearKey(void *)
0x180032e2e  mov     ebx, eax
0x180032e30  test    eax, eax
0x180032e32  jns     short loc_180032E4D
0x180032e34  mov     rcx, cs:WPP_GLOBAL_Control
0x180032e3b  cmp     rcx, r13
0x180032e3e  jz      short loc_180032EBE
0x180032e40  test    byte ptr [rcx+1Ch], 2
0x180032e44  jz      short loc_180032EBE
0x180032e46  mov     edx, 2Bh ; '+'
0x180032e4b  jmp     short loc_180032EAB
0x180032e4d  mov     rcx, [rbp+var_10]
0x180032e51  call    cs:__imp_FveCommitChanges
0x180032e58  nop     dword ptr [rax+rax+00h]
0x180032e5d  mov     ebx, eax
0x180032e5f  test    eax, eax
0x180032e61  jns     loc_180032EF9
0x180032e67  mov     rcx, cs:WPP_GLOBAL_Control
0x180032e6e  cmp     rcx, r13
0x180032e71  jz      short loc_180032EBE
0x180032e73  test    byte ptr [rcx+1Ch], 2
0x180032e77  jz      short loc_180032EBE
0x180032e79  mov     edx, 2Ch ; ','
0x180032e7e  jmp     short loc_180032EAB
0x180032e80  xor     edx, edx
0x180032e82  call    cs:__imp_FveDecrementClearKeyCounter
0x180032e89  nop     dword ptr [rax+rax+00h]
0x180032e8e  mov     ebx, eax
0x180032e90  test    eax, eax
0x180032e92  jns     short loc_180032EF9
0x180032e94  mov     rcx, cs:WPP_GLOBAL_Control
0x180032e9b  cmp     rcx, r13
0x180032e9e  jz      short loc_180032EBE
0x180032ea0  test    byte ptr [rcx+1Ch], 2
0x180032ea4  jz      short loc_180032EBE
0x180032ea6  mov     edx, 2Dh ; '-'
0x180032eab  mov     r9d, eax
0x180032eae  lea     r8, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids
0x180032eb5  mov     rcx, [rcx+10h]
0x180032eb9  call    WPP_SF_d
0x180032ebe  cmp     r14w, 2
0x180032ec3  jnb     short loc_180032EED
0x180032ec5  lea     rcx, [rbp+var_18]
0x180032ec9  call    ?Close@?$HandleT@UFveFindHandleTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<FveFindHandleTraits>::Close(void)
0x180032ece  nop
0x180032ecf  mov     [rbp+var_18], rdi
0x180032ed3  lea     rcx, [rbp+var_18]
0x180032ed7  call    ?Close@?$HandleT@UFveFindHandleTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<FveFindHandleTraits>::Close(void)
0x180032edc  inc     r14w
0x180032ee0  cmp     r14w, 3
0x180032ee5  jb      loc_180032D4A
0x180032eeb  jmp     short loc_180032F06
0x180032eed  mov     edx, ebx; int
0x180032eef  mov     rcx, [rbp+var_10]; void *
0x180032ef3  call    ?BdeSvcLogEventResumeFailure@@YAXPEAXJ@Z; BdeSvcLogEventResumeFailure(void *,long)
0x180032ef8  nop
0x180032ef9  mov     [rbp+var_18], rdi
0x180032efd  lea     rcx, [rbp+var_18]
0x180032f01  call    ?Close@?$HandleT@UFveFindHandleTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<FveFindHandleTraits>::Close(void)
0x180032f06  mov     rcx, cs:WPP_GLOBAL_Control
0x180032f0d  cmp     rcx, r13
0x180032f10  jz      short loc_180032F30
0x180032f12  test    byte ptr [rcx+1Ch], 20h
0x180032f16  jz      short loc_180032F30
0x180032f18  mov     edx, 2Eh ; '.'
0x180032f1d  mov     r9d, ebx
0x180032f20  lea     r8, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids
0x180032f27  mov     rcx, [rcx+10h]
0x180032f2b  call    WPP_SF_d
0x180032f30  mov     eax, ebx
0x180032f32  mov     rcx, [rbp+var_8]
0x180032f36  xor     rcx, rsp; StackCookie
0x180032f39  call    __security_check_cookie
0x180032f3e  mov     rbx, [rsp+40h+arg_10]
0x180032f46  add     rsp, 40h
0x180032f4a  pop     r15
0x180032f4c  pop     r14
0x180032f4e  pop     r13
0x180032f50  pop     r12
0x180032f52  pop     rdi
0x180032f53  pop     rsi
0x180032f54  pop     rbp
0x180032f55  retn
```
