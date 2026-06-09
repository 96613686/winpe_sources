# ResumeWithOSVolume::CheckOSVolumeAndResumeFDVs(std::map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,VolumeEntry,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,VolumeEntry>>> *)

- ea: `0x18000a800`
- end: `0x18000af12`
- name: `?CheckOSVolumeAndResumeFDVs@ResumeWithOSVolume@@SAJPEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UVolumeEntry@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UVolumeEntry@@@std@@@2@@std@@@Z`
- size: `1810`
- prototype: `__int64 __fastcall(__int64 **, __int64, __int64)`
- caller_count: `1`
- callee_count: `16`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180007d90`

## callees

- `0x180006260`
- `0x180009f30`
- `0x180009f60`
- `0x18000a800`
- `0x18000af20`
- `0x18000af90`
- `0x18000c240`
- `0x18000dba8`
- `0x18000dc4c`
- `0x18001c6c8`
- `0x18002ae7c`
- `0x18002afa4`
- `0x18002cac4`
- `0x180034070`
- `0x180048198`
- `0x1800717fc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000a982`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000a982`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a95d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a95d`
- `FVEAPI!FveCommitChanges` at `0x18000ae8d`
- `FVEAPI!FveCommitChanges` at `0x18000ae8d`
- `FVEAPI!FveIsAnyDataVolumeBoundToOSVolume` at `0x18000aaa9`
- `FVEAPI!FveIsAnyDataVolumeBoundToOSVolume` at `0x18000aaa9`
- `FVEAPI!FveIsBoundDataVolumeToOSVolume` at `0x18000adac`
- `FVEAPI!FveIsBoundDataVolumeToOSVolume` at `0x18000adac`

## pseudocode

```c
__int64 __fastcall ResumeWithOSVolume::CheckOSVolumeAndResumeFDVs(__int64 **a1, __int64 a2, __int64 a3)
{
  unsigned __int8 v4; // r12
  __int64 v5; // r13
  unsigned __int8 v6; // r14
  PVOID *v7; // r10
  __int64 v8; // rbx
  int v9; // ebx
  unsigned int v11; // edi
  __int64 v12; // rdx
  bool v13; // si
  int LastError; // eax
  __int64 v15; // rdx
  unsigned int FVEVolumeHandle; // eax
  unsigned int IsAnyDataVolumeBoundToOSVolume; // eax
  __int64 v18; // r9
  struct VolumeEntry *v19; // rsi
  unsigned int v20; // ecx
  int v21; // eax
  _QWORD *v22; // rdi
  __int64 v23; // r8
  _QWORD *v24; // r10
  __int64 v25; // rdx
  __int64 i; // rax
  __int64 v27; // rdx
  int IsBoundDataVolumeToOSVolume; // eax
  _QWORD *v29; // r10
  int v30; // edx
  __int64 j; // [rsp+30h] [rbp-48h] BYREF
  void **v32; // [rsp+38h] [rbp-40h] BYREF
  void *v33; // [rsp+40h] [rbp-38h]
  unsigned int v34; // [rsp+48h] [rbp-30h] BYREF
  int v35; // [rsp+4Ch] [rbp-2Ch] BYREF
  __int128 v36; // [rsp+50h] [rbp-28h] BYREF

  v34 = 0;
  v36 = 0;
  v4 = 0;
  v35 = 0;
  v5 = 0;
  v6 = 0;
  v32 = &Microsoft::WRL::Wrappers::HandleT<FveHandleTraits>::`vftable';
  v33 = 0;
  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_5b7979a4272d38ac815aa338f62bc0f6_Traceguids);
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  v8 = **a1;
  while ( !*(_BYTE *)(v8 + 25) )
  {
    v11 = *(_DWORD *)(v8 + 64);
    if ( (v11 & 0x4000) != 0 )
    {
      if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 8) != 0 )
      {
        WPP_SF_d(v7[2], 12, &WPP_5b7979a4272d38ac815aa338f62bc0f6_Traceguids, v11);
        v7 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( (v11 & 0x101) == 0x101 && (v11 & 0x416) == 0 )
      {
        if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 8) != 0 )
        {
          WPP_SF_(v7[2], 13, &WPP_5b7979a4272d38ac815aa338f62bc0f6_Traceguids);
          v7 = (PVOID *)WPP_GLOBAL_Control;
        }
        v6 = 1;
        if ( *(_QWORD *)(v8 + 128) <= 7u )
          v5 = v8 + 104;
        else
          v5 = *(_QWORD *)(v8 + 104);
      }
    }
    else if ( (v11 & 0x400000) == 0 )
    {
      v12 = *(_QWORD *)(v8 + 152);
      v13 = (*(_DWORD *)(v8 + 64) & 0x401) == 0x401 && (v11 & 0x14) == 0 && (v12 & 0x10) != 0;
      if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 8) != 0 )
      {
        WPP_SF_lLi(v7[2], v12, a3, v13, v11, *(_QWORD *)(v8 + 152));
        v7 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v13 )
      {
        if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 8) != 0 )
        {
          if ( *(_QWORD *)(v8 + 128) <= 7u )
            v18 = v8 + 104;
          else
            v18 = *(_QWORD *)(v8 + 104);
          WPP_SF_S(v7[2], 14, &WPP_5b7979a4272d38ac815aa338f62bc0f6_Traceguids, v18);
          v7 = (PVOID *)WPP_GLOBAL_Control;
        }
        v4 = 1;
      }
    }
    if ( *(_BYTE *)(*(_QWORD *)(v8 + 16) + 25LL) )
    {
      for ( i = *(_QWORD *)(v8 + 8); !*(_BYTE *)(i + 25); i = *(_QWORD *)(i + 8) )
      {
        if ( v8 != *(_QWORD *)(i + 16) )
          break;
        v8 = i;
      }
      v8 = i;
    }
    else
    {
      v8 = std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,std::shared_ptr<CSessionState>>>>::_Min();
    }
  }
  if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 8) != 0 )
  {
    WPP_SF_DD(v7[2], 15, &WPP_5b7979a4272d38ac815aa338f62bc0f6_Traceguids, v6, v4);
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !v6 || !v4 )
  {
    v9 = 0;
    if ( v7 == &WPP_GLOBAL_Control )
      goto LABEL_7;
    goto LABEL_23;
  }
  LOBYTE(a3) = 1;
  FVEVolumeHandle = FveEasUtil::I_GetFVEVolumeHandle(v5, &v32, a3);
  v9 = FVEVolumeHandle;
  if ( !FVEVolumeHandle )
    goto LABEL_43;
  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_5b7979a4272d38ac815aa338f62bc0f6_Traceguids, FVEVolumeHandle);
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v9 >= 0 )
  {
LABEL_43:
    IsAnyDataVolumeBoundToOSVolume = FveIsAnyDataVolumeBoundToOSVolume(v33, &v34);
    v9 = IsAnyDataVolumeBoundToOSVolume;
    if ( !IsAnyDataVolumeBoundToOSVolume )
      goto LABEL_44;
    v7 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        18,
        &WPP_5b7979a4272d38ac815aa338f62bc0f6_Traceguids,
        IsAnyDataVolumeBoundToOSVolume);
      v7 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v9 >= 0 )
    {
LABEL_44:
      Microsoft::WRL::Wrappers::HandleT<FveFindHandleTraits>::Close(&v32);
      if ( !v34 )
      {
        v7 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
          goto LABEL_7;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
          goto LABEL_26;
        v15 = 19;
        goto LABEL_25;
      }
      v7 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_5b7979a4272d38ac815aa338f62bc0f6_Traceguids, v34);
        v7 = (PVOID *)WPP_GLOBAL_Control;
      }
      v27 = **a1;
      for ( j = v27; ; v27 = j )
      {
        if ( *(_BYTE *)(v27 + 25) )
          goto LABEL_26;
        v19 = (struct VolumeEntry *)(v27 + 64);
        v20 = *(_DWORD *)(v27 + 64);
        v21 = 0;
        if ( (v20 & 0x4000) == 0 )
        {
          LOBYTE(v21) = (v20 & 0x400000) != 0;
          ++v21;
        }
        v22 = (_QWORD *)(v27 + 104);
        if ( *(_QWORD *)(v27 + 128) > 7u )
          v22 = (_QWORD *)*v22;
        if ( v21 == 1 )
        {
          if ( ResumeWithOSVolume::IsFdvReadyForResume(v20, *(_QWORD *)(v27 + 152)) )
          {
            LOBYTE(v23) = 1;
            IsBoundDataVolumeToOSVolume = FveEasUtil::I_GetFVEVolumeHandle(v22, &v32, v23);
            if ( IsBoundDataVolumeToOSVolume < 0 )
            {
              v29 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              {
                v30 = 22;
                goto LABEL_92;
              }
              goto LABEL_93;
            }
            IsBoundDataVolumeToOSVolume = FveIsBoundDataVolumeToOSVolume(v33, &v35, &v36);
            v9 = IsBoundDataVolumeToOSVolume;
            if ( IsBoundDataVolumeToOSVolume < 0 )
            {
              v29 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              {
                v30 = 23;
                goto LABEL_92;
              }
              goto LABEL_93;
            }
            if ( v35 )
            {
              IsBoundDataVolumeToOSVolume = FveEasUtil::I_GetFVEVolumeHandle(v22, &v32, 0);
              if ( IsBoundDataVolumeToOSVolume < 0 )
              {
                v29 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                {
                  v30 = 25;
                  goto LABEL_92;
                }
                goto LABEL_93;
              }
              IsBoundDataVolumeToOSVolume = CFveApiWrapper::DeleteClearKey(v33);
              if ( IsBoundDataVolumeToOSVolume < 0 )
              {
                v29 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                {
                  v30 = 26;
                  goto LABEL_92;
                }
                goto LABEL_93;
              }
              IsBoundDataVolumeToOSVolume = FveCommitChanges(v33);
              v9 = IsBoundDataVolumeToOSVolume;
              if ( IsBoundDataVolumeToOSVolume < 0 )
              {
                v29 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                {
                  v30 = 27;
LABEL_92:
                  WPP_SF_Sd(
                    v29[2],
                    v30,
                    (unsigned int)&WPP_5b7979a4272d38ac815aa338f62bc0f6_Traceguids,
                    (_DWORD)v22,
                    IsBoundDataVolumeToOSVolume);
                }
LABEL_93:
                v9 = 0;
                goto LABEL_117;
              }
              Microsoft::WRL::Wrappers::HandleT<FveFindHandleTraits>::Close(&v32);
              UpdateVolumeEntryFlags(v19);
              v24 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
              {
                v25 = 28;
                goto LABEL_87;
              }
            }
            else
            {
              v24 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
              {
                v25 = 24;
                goto LABEL_87;
              }
            }
          }
          else
          {
            v24 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            {
              v25 = 21;
LABEL_87:
              WPP_SF_S(v24[2], v25, &WPP_5b7979a4272d38ac815aa338f62bc0f6_Traceguids, v22);
            }
          }
        }
LABEL_117:
        std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,HCMNOTIFICATION__ *>>>,std::_Iterator_base0>::operator++(&j);
      }
    }
  }
  while ( 1 )
  {
LABEL_26:
    if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 0x20) != 0 )
      WPP_SF_d(v7[2], 29, &WPP_5b7979a4272d38ac815aa338f62bc0f6_Traceguids, (unsigned int)v9);
LABEL_7:
    v32 = &Microsoft::WRL::Wrappers::HandleT<FveHandleTraits>::`vftable';
    if ( !v33 || (unsigned __int8)Microsoft::WRL::Wrappers::HandleT<FveHandleTraits>::InternalClose(&v32) )
      return (unsigned int)v9;
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    RaiseException(LastError, 1u, 0, 0);
LABEL_23:
    if ( (*((_BYTE *)v7 + 28) & 8) != 0 )
    {
      v15 = 16;
LABEL_25:
      WPP_SF_(v7[2], v15, &WPP_5b7979a4272d38ac815aa338f62bc0f6_Traceguids);
      v7 = (PVOID *)WPP_GLOBAL_Control;
      continue;
    }
  }
}

```

## disassembly

```asm
0x18000a800  push    rbp
0x18000a802  push    rbx
0x18000a803  push    rsi
0x18000a804  push    rdi
0x18000a805  push    r12
0x18000a807  push    r13
0x18000a809  push    r14
0x18000a80b  push    r15
0x18000a80d  mov     rbp, rsp
0x18000a810  sub     rsp, 78h
0x18000a814  mov     rax, cs:__security_cookie
0x18000a81b  xor     rax, rsp
0x18000a81e  mov     [rbp+var_18], rax
0x18000a822  mov     r15, rcx
0x18000a825  xor     edi, edi
0x18000a827  mov     [rbp+var_30], edi
0x18000a82a  xorps   xmm0, xmm0
0x18000a82d  movups  [rbp+var_28], xmm0
0x18000a831  xor     r12b, r12b
0x18000a834  mov     [rbp+var_2C], edi
0x18000a837  mov     r13d, edi
0x18000a83a  xor     r14b, r14b
0x18000a83d  lea     rax, ??_7?$HandleT@UFveHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<FveHandleTraits>::`vftable'
0x18000a844  mov     [rbp+var_40], rax
0x18000a848  mov     [rbp+var_38], rdi
0x18000a84c  lea     rsi, WPP_GLOBAL_Control
0x18000a853  mov     r10, cs:WPP_GLOBAL_Control
0x18000a85a  cmp     r10, rsi
0x18000a85d  jnz     loc_18000A9E3
0x18000a863  mov     rbx, [r15]
0x18000a866  mov     rbx, [rbx]
0x18000a869  cmp     byte ptr [rbx+19h], 0
0x18000a86d  jz      short loc_18000A8C2
0x18000a86f  cmp     r10, rsi
0x18000a872  jnz     loc_18000AA0F
0x18000a878  test    r14b, r14b
0x18000a87b  jnz     loc_18000AA47
0x18000a881  xor     ebx, ebx
0x18000a883  cmp     r10, rsi
0x18000a886  jnz     loc_18000A98F
0x18000a88c  lea     rax, ??_7?$HandleT@UFveHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<FveHandleTraits>::`vftable'
0x18000a893  mov     [rbp+var_40], rax
0x18000a897  cmp     [rbp+var_38], 0
0x18000a89c  jnz     loc_18000A94C
0x18000a8a2  mov     eax, ebx
0x18000a8a4  mov     rcx, [rbp+var_18]
0x18000a8a8  xor     rcx, rsp; StackCookie
0x18000a8ab  call    __security_check_cookie
0x18000a8b0  add     rsp, 78h
0x18000a8b4  pop     r15
0x18000a8b6  pop     r14
0x18000a8b8  pop     r13
0x18000a8ba  pop     r12
0x18000a8bc  pop     rdi
0x18000a8bd  pop     rsi
0x18000a8be  pop     rbx
0x18000a8bf  pop     rbp
0x18000a8c0  retn
0x18000a8c2  mov     edi, [rbx+40h]
0x18000a8c5  bt      edi, 0Eh
0x18000a8c9  jb      loc_18000AB30
0x18000a8cf  bt      edi, 16h
0x18000a8d3  jb      short loc_18000A931
0x18000a8d5  mov     rdx, [rbx+98h]
0x18000a8dc  mov     eax, edi
0x18000a8de  and     eax, 401h
0x18000a8e3  cmp     eax, 401h
0x18000a8e8  jz      loc_18000AC7C
0x18000a8ee  xor     sil, sil
0x18000a8f1  lea     rax, WPP_GLOBAL_Control
0x18000a8f8  cmp     r10, rax
0x18000a8fb  jz      short loc_18000A921
0x18000a8fd  test    byte ptr [r10+1Ch], 8
0x18000a902  jz      short loc_18000A921
0x18000a904  movzx   r9d, sil
0x18000a908  mov     [rsp+78h+var_50], rdx
0x18000a90d  mov     [rsp+78h+var_58], edi
0x18000a911  mov     rcx, [r10+10h]
0x18000a915  call    WPP_SF_lLi
0x18000a91a  mov     r10, cs:WPP_GLOBAL_Control
0x18000a921  test    sil, sil
0x18000a924  jnz     loc_18000AC99
0x18000a92a  lea     rsi, WPP_GLOBAL_Control
0x18000a931  mov     rcx, [rbx+10h]
0x18000a935  cmp     byte ptr [rcx+19h], 0
0x18000a939  jnz     loc_18000ACB9
0x18000a93f  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$shared_ptr@VCSessionState@@@std@@@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@$$CBKV?$shared_ptr@VCSessionState@@@std@@@std@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,std::shared_ptr<CSessionState>>>>::_Min(std::_Tree_node<std::pair<ulong const,std::shared_ptr<CSessionState>>,void *> *)
0x18000a944  mov     rbx, rax
0x18000a947  jmp     loc_18000A869
0x18000a94c  lea     rcx, [rbp+var_40]
0x18000a950  call    ?InternalClose@?$HandleT@UFveHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<FveHandleTraits>::InternalClose(void)
0x18000a955  test    al, al
0x18000a957  jnz     loc_18000A8A2
0x18000a95d  call    cs:__imp_GetLastError
0x18000a964  nop     dword ptr [rax+rax+00h]
0x18000a969  test    eax, eax
0x18000a96b  jle     short loc_18000A975
0x18000a96d  movzx   eax, ax
0x18000a970  or      eax, 80070000h
0x18000a975  xor     r9d, r9d; lpArguments
0x18000a978  xor     r8d, r8d; nNumberOfArguments
0x18000a97b  mov     edx, 1; dwExceptionFlags
0x18000a980  mov     ecx, eax; dwExceptionCode
0x18000a982  call    cs:__imp_RaiseException
0x18000a989  nop     dword ptr [rax+rax+00h]
0x18000a98e  nop
0x18000a98f  test    byte ptr [r10+1Ch], 8
0x18000a994  jz      short loc_18000A9B2
0x18000a996  mov     edx, 10h
0x18000a99b  lea     r8, WPP_5b7979a4272d38ac815aa338f62bc0f6_Traceguids
0x18000a9a2  mov     rcx, [r10+10h]
0x18000a9a6  call    WPP_SF_
0x18000a9ab  mov     r10, cs:WPP_GLOBAL_Control
0x18000a9b2  cmp     r10, rsi
0x18000a9b5  jz      loc_18000A88C
0x18000a9bb  test    byte ptr [r10+1Ch], 20h
0x18000a9c0  jz      loc_18000A88C
0x18000a9c6  mov     edx, 1Dh
0x18000a9cb  mov     r9d, ebx
0x18000a9ce  lea     r8, WPP_5b7979a4272d38ac815aa338f62bc0f6_Traceguids
0x18000a9d5  mov     rcx, [r10+10h]
0x18000a9d9  call    WPP_SF_d
0x18000a9de  jmp     loc_18000A88C
0x18000a9e3  test    byte ptr [r10+1Ch], 20h
0x18000a9e8  jz      loc_18000A863
0x18000a9ee  mov     edx, 0Bh
0x18000a9f3  lea     r8, WPP_5b7979a4272d38ac815aa338f62bc0f6_Traceguids
0x18000a9fa  mov     rcx, [r10+10h]
0x18000a9fe  call    WPP_SF_
0x18000aa03  mov     r10, cs:WPP_GLOBAL_Control
0x18000aa0a  jmp     loc_18000A863
0x18000aa0f  test    byte ptr [r10+1Ch], 8
0x18000aa14  jz      loc_18000A878
0x18000aa1a  movzx   eax, r12b
0x18000aa1e  movzx   r9d, r14b
0x18000aa22  mov     edx, 0Fh
0x18000aa27  mov     [rsp+78h+var_58], eax
0x18000aa2b  lea     r8, WPP_5b7979a4272d38ac815aa338f62bc0f6_Traceguids
0x18000aa32  mov     rcx, [r10+10h]
0x18000aa36  call    WPP_SF_DD
0x18000aa3b  mov     r10, cs:WPP_GLOBAL_Control
0x18000aa42  jmp     loc_18000A878
0x18000aa47  test    r12b, r12b
0x18000aa4a  jz      loc_18000A881
0x18000aa50  mov     r8b, 1
0x18000aa53  lea     rdx, [rbp+var_40]
0x18000aa57  mov     rcx, r13
0x18000aa5a  call    ?I_GetFVEVolumeHandle@FveEasUtil@@CAJPEBGAEAV?$HandleT@UFveHandleTraits@@@Wrappers@WRL@Microsoft@@_N@Z; FveEasUtil::I_GetFVEVolumeHandle(ushort const *,Microsoft::WRL::Wrappers::HandleT<FveHandleTraits> &,bool)
0x18000aa5f  mov     ebx, eax
0x18000aa61  xor     edi, edi
0x18000aa63  test    eax, eax
0x18000aa65  jz      short loc_18000AAA1
0x18000aa67  mov     r10, cs:WPP_GLOBAL_Control
0x18000aa6e  cmp     r10, rsi
0x18000aa71  jz      short loc_18000AA99
0x18000aa73  test    byte ptr [r10+1Ch], 40h
0x18000aa78  jz      short loc_18000AA99
0x18000aa7a  mov     edx, 11h
0x18000aa7f  mov     r9d, eax
0x18000aa82  lea     r8, WPP_5b7979a4272d38ac815aa338f62bc0f6_Traceguids
0x18000aa89  mov     rcx, [r10+10h]
0x18000aa8d  call    WPP_SF_d
0x18000aa92  mov     r10, cs:WPP_GLOBAL_Control
0x18000aa99  test    ebx, ebx
0x18000aa9b  js      loc_18000A9B2
0x18000aaa1  lea     rdx, [rbp+var_30]
0x18000aaa5  mov     rcx, [rbp+var_38]
0x18000aaa9  call    cs:__imp_FveIsAnyDataVolumeBoundToOSVolume
0x18000aab0  nop     dword ptr [rax+rax+00h]
0x18000aab5  mov     ebx, eax
0x18000aab7  test    eax, eax
0x18000aab9  jz      short loc_18000AAF5
0x18000aabb  mov     r10, cs:WPP_GLOBAL_Control
0x18000aac2  cmp     r10, rsi
0x18000aac5  jz      short loc_18000AAED
0x18000aac7  test    byte ptr [r10+1Ch], 40h
0x18000aacc  jz      short loc_18000AAED
0x18000aace  mov     edx, 12h
0x18000aad3  mov     r9d, eax
0x18000aad6  lea     r8, WPP_5b7979a4272d38ac815aa338f62bc0f6_Traceguids
0x18000aadd  mov     rcx, [r10+10h]
0x18000aae1  call    WPP_SF_d
0x18000aae6  mov     r10, cs:WPP_GLOBAL_Control
0x18000aaed  test    ebx, ebx
0x18000aaef  js      loc_18000A9B2
0x18000aaf5  lea     rcx, [rbp+var_40]
0x18000aaf9  call    ?Close@?$HandleT@UFveFindHandleTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<FveFindHandleTraits>::Close(void)
0x18000aafe  mov     r9d, [rbp+var_30]
0x18000ab02  test    r9d, r9d
0x18000ab05  jnz     loc_18000ACDE
0x18000ab0b  mov     r10, cs:WPP_GLOBAL_Control
0x18000ab12  cmp     r10, rsi
0x18000ab15  jz      loc_18000A88C
0x18000ab1b  test    byte ptr [r10+1Ch], 8
0x18000ab20  jz      loc_18000A9B2
0x18000ab26  mov     edx, 13h
0x18000ab2b  jmp     loc_18000A99B
0x18000ab30  cmp     r10, rsi
0x18000ab33  jz      short loc_18000AB40
0x18000ab35  test    byte ptr [r10+1Ch], 8
0x18000ab3a  jnz     loc_18000AC58
0x18000ab40  mov     eax, edi
0x18000ab42  and     eax, 101h
0x18000ab47  cmp     eax, 101h
0x18000ab4c  jnz     loc_18000A931
0x18000ab52  test    edi, 416h
0x18000ab58  jnz     loc_18000A931
0x18000ab5e  cmp     r10, rsi
0x18000ab61  jz      short loc_18000AB86
0x18000ab63  test    byte ptr [r10+1Ch], 8
0x18000ab68  jz      short loc_18000AB86
0x18000ab6a  mov     edx, 0Dh
0x18000ab6f  lea     r8, WPP_5b7979a4272d38ac815aa338f62bc0f6_Traceguids
0x18000ab76  mov     rcx, [r10+10h]
0x18000ab7a  call    WPP_SF_
0x18000ab7f  mov     r10, cs:WPP_GLOBAL_Control
0x18000ab86  mov     r14b, 1
0x18000ab89  cmp     qword ptr [rbx+80h], 7
0x18000ab91  jbe     short loc_18000AB9C
0x18000ab93  mov     r13, [rbx+68h]
0x18000ab97  jmp     loc_18000A931
0x18000ab9c  lea     r13, [rbx+68h]
0x18000aba0  jmp     loc_18000A931
0x18000aba5  cmp     qword ptr [rbx+80h], 7
0x18000abad  jbe     short loc_18000ABD7
0x18000abaf  mov     r9, [rbx+68h]
0x18000abb3  mov     edx, 0Eh
0x18000abb8  lea     r8, WPP_5b7979a4272d38ac815aa338f62bc0f6_Traceguids
0x18000abbf  mov     rcx, [r10+10h]
0x18000abc3  call    WPP_SF_S
0x18000abc8  mov     r10, cs:WPP_GLOBAL_Control
0x18000abcf  mov     r12b, 1
0x18000abd2  jmp     loc_18000A931
0x18000abd7  lea     r9, [rbx+68h]
0x18000abdb  jmp     short loc_18000ABB3
0x18000abdd  cmp     byte ptr [rdx+19h], 0
0x18000abe1  jnz     loc_18000A9B2
0x18000abe7  lea     rsi, [rdx+40h]
0x18000abeb  mov     ecx, [rsi]; unsigned int
0x18000abed  mov     eax, edi
0x18000abef  bt      ecx, 0Eh
0x18000abf3  jb      short loc_18000ABFE
0x18000abf5  bt      ecx, 16h
0x18000abf9  setb    al
0x18000abfc  inc     eax
0x18000abfe  lea     rdi, [rdx+68h]
0x18000ac02  cmp     qword ptr [rdx+80h], 7
0x18000ac0a  jbe     short loc_18000AC0F
0x18000ac0c  mov     rdi, [rdi]
0x18000ac0f  cmp     eax, 1
0x18000ac12  jnz     loc_18000AEF6
0x18000ac18  mov     rdx, [rdx+98h]; unsigned __int64
0x18000ac1f  call    ?IsFdvReadyForResume@ResumeWithOSVolume@@KA_NK_K@Z; ResumeWithOSVolume::IsFdvReadyForResume(ulong,unsigned __int64)
0x18000ac24  test    al, al
0x18000ac26  jnz     loc_18000AD40
0x18000ac2c  mov     r10, cs:WPP_GLOBAL_Control
0x18000ac33  lea     rsi, WPP_GLOBAL_Control
0x18000ac3a  cmp     r10, rsi
0x18000ac3d  jz      loc_18000AEFD
0x18000ac43  test    byte ptr [r10+1Ch], 8
0x18000ac48  jz      loc_18000AEFD
0x18000ac4e  mov     edx, 15h
0x18000ac53  jmp     loc_18000AD21
0x18000ac58  mov     edx, 0Ch
0x18000ac5d  mov     r9d, edi
0x18000ac60  lea     r8, WPP_5b7979a4272d38ac815aa338f62bc0f6_Traceguids
0x18000ac67  mov     rcx, [r10+10h]
0x18000ac6b  call    WPP_SF_d
0x18000ac70  mov     r10, cs:WPP_GLOBAL_Control
0x18000ac77  jmp     loc_18000AB40
0x18000ac7c  test    dil, 14h
0x18000ac80  setz    cl
0x18000ac83  test    dl, 10h
0x18000ac86  setnz   al
0x18000ac89  test    al, cl
0x18000ac8b  jz      loc_18000A8EE
0x18000ac91  mov     sil, 1
0x18000ac94  jmp     loc_18000A8F1
0x18000ac99  lea     rsi, WPP_GLOBAL_Control
0x18000aca0  cmp     r10, rsi
0x18000aca3  jz      loc_18000ABCF
0x18000aca9  test    byte ptr [r10+1Ch], 8
0x18000acae  jz      loc_18000ABCF
0x18000acb4  jmp     loc_18000ABA5
0x18000acb9  mov     rax, [rbx+8]
0x18000acbd  cmp     byte ptr [rax+19h], 0
0x18000acc1  jnz     short loc_18000ACD6
0x18000acc3  cmp     rbx, [rax+10h]
0x18000acc7  jnz     short loc_18000ACD6
0x18000acc9  mov     rbx, rax
0x18000accc  mov     rax, [rax+8]
0x18000acd0  cmp     byte ptr [rax+19h], 0
0x18000acd4  jz      short loc_18000ACC3
0x18000acd6  mov     rbx, rax
0x18000acd9  jmp     loc_18000A869
0x18000acde  mov     r10, cs:WPP_GLOBAL_Control
0x18000ace5  cmp     r10, rsi
0x18000ace8  jz      short loc_18000AD0D
0x18000acea  test    byte ptr [r10+1Ch], 8
0x18000acef  jz      short loc_18000AD0D
  ... truncated ...
```
