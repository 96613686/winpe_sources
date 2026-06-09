# Wd1dsListener::HrOnEventRecord(_EVENT_RECORD *)

- ea: `0x1400e4424`
- end: `0x1400e4d06`
- name: `?HrOnEventRecord@Wd1dsListener@@AEAAJPEAU_EVENT_RECORD@@@Z`
- size: `2274`
- prototype: `__int64 __fastcall(Wd1dsListener *__hidden this, struct _EVENT_RECORD *)`
- caller_count: `1`
- callee_count: `26`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400e4f30`

## callees

- `0x14003a5c0`
- `0x14004f9a0`
- `0x140063750`
- `0x14007d1e0`
- `0x14007d210`
- `0x14007e20c`
- `0x140081fc8`
- `0x140082efc`
- `0x1400833d4`
- `0x140084a8c`
- `0x140085d38`
- `0x140085d94`
- `0x140086108`
- `0x14008ce88`
- `0x14008d1fc`
- `0x14008f950`
- `0x1400e3c5c`
- `0x1400e3ea0`
- `0x1400e4424`
- `0x1400e4d08`
- `0x1400e5114`
- `0x1400e5744`
- `0x1400e6560`
- `0x1400e7ae4`
- `0x1400e7f84`
- `0x140166250`

## import_xrefs

- `KERNEL32!DebugBreak` at `0x1400e4497`
- `KERNEL32!DebugBreak` at `0x1400e4bb1`
- `KERNEL32!DebugBreak` at `0x1400e4497`
- `KERNEL32!DebugBreak` at `0x1400e4bb1`
- `KERNEL32!AcquireSRWLockShared` at `0x1400e44d7`
- `KERNEL32!AcquireSRWLockShared` at `0x1400e47e3`
- `KERNEL32!AcquireSRWLockShared` at `0x1400e44d7`
- `KERNEL32!AcquireSRWLockShared` at `0x1400e47e3`
- `KERNEL32!ReleaseSRWLockShared` at `0x1400e44e6`
- `KERNEL32!ReleaseSRWLockShared` at `0x1400e47f2`
- `KERNEL32!ReleaseSRWLockShared` at `0x1400e44e6`
- `KERNEL32!ReleaseSRWLockShared` at `0x1400e47f2`

## string_xrefs

- `0x1400e479c`: `MdCommonAggregateMetric`
- `0x1400e47ba`: `MdCommonRawMetric`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Wd1dsListener::HrOnEventRecord(Wd1dsListener *this, struct _EVENT_RECORD *a2)
{
  unsigned int v4; // r12d
  MpWatchDog *v5; // rcx
  unsigned int v6; // r8d
  char v7; // al
  __int64 v8; // rcx
  __int64 v9; // rdx
  MpWatchDog::WdConfigManager *v10; // rbx
  RTL_SRWLOCK *v11; // rdi
  __int64 result; // rax
  const wchar_t *v13; // rbx
  wchar_t **v14; // rdx
  __int64 v15; // rdx
  size_t v16; // r8
  const wchar_t *v17; // rcx
  int EventInformation; // eax
  unsigned int v19; // ebx
  unsigned int *v20; // rcx
  __int64 v21; // r9
  unsigned int v22; // eax
  int v23; // ecx
  __int64 v24; // rcx
  __int64 v25; // rdx
  wchar_t **v26; // r9
  _WORD *v27; // rdx
  unsigned __int64 v28; // r8
  const wchar_t *v29; // rcx
  const wchar_t *v30; // rcx
  MpWatchDog::WdConfigManager *v31; // rbx
  RTL_SRWLOCK *v32; // rdi
  unsigned int v33; // eax
  int v34; // ecx
  __int64 v35; // rcx
  __int64 v36; // rdx
  wchar_t **v37; // r9
  wchar_t **v38; // rdx
  wchar_t **v39; // rdx
  int v40; // eax
  char *UserData; // rcx
  _DWORD *v42; // rdi
  _WORD *v43; // rdx
  unsigned __int64 v44; // r8
  int v45; // r8d
  unsigned int v46; // edx
  __int16 *v47; // rax
  const wchar_t *v48; // rdx
  wchar_t **v49; // r9
  __int16 v50; // ax
  wchar_t **v51; // r9
  int v52; // eax
  wchar_t **v53; // r9
  MpWatchDog *v54; // rcx
  unsigned int v55; // r8d
  __int64 v56; // rdi
  wchar_t **v57; // rdx
  bool v58; // [rsp+30h] [rbp-59h]
  _BYTE v59[16]; // [rsp+38h] [rbp-51h] BYREF
  void **p_Block; // [rsp+48h] [rbp-41h]
  Wd1dsListener *v61; // [rsp+50h] [rbp-39h]
  void *Block; // [rsp+58h] [rbp-31h] BYREF
  wchar_t *S1[2]; // [rsp+60h] [rbp-29h] BYREF
  size_t N[2]; // [rsp+70h] [rbp-19h]
  wchar_t *v65[2]; // [rsp+80h] [rbp-9h] BYREF
  __int128 v66; // [rsp+90h] [rbp+7h]

  v4 = 0;
  Block = 0;
  v59[8] = 0;
  p_Block = &Block;
  v61 = this;
  if ( MpWatchDog::MpIsCoreSvcInDevMode(this) )
  {
    if ( MpWatchDog::GetMiscConfigDword((HKEY)&stru_14019DC00, 0, v6) == 1 )
    {
      v7 = byte_1401E7488;
      byte_1401E7488 = 1;
      if ( !v7 )
        DebugBreak();
    }
  }
  if ( MpWatchDog::Is1dsDisabled(v5) )
  {
    v8 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    {
      v9 = 28;
LABEL_14:
      WPP_SF_(*(_QWORD *)(v8 + 16), v9, &WPP_3446203f0eb23a99ce68b6ff1fda97d5_Traceguids);
      goto LABEL_15;
    }
    goto LABEL_15;
  }
  v10 = MpWatchDog::gMpWdConfigManager;
  v11 = (RTL_SRWLOCK *)((char *)MpWatchDog::gMpWdConfigManager + 848);
  AcquireSRWLockShared((PSRWLOCK)MpWatchDog::gMpWdConfigManager + 106);
  LOBYTE(v10) = *((_BYTE *)v10 + 808);
  ReleaseSRWLockShared(v11);
  if ( !(_BYTE)v10
    && (*(unsigned __int8 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 160LL))(*((_QWORD *)this + 3)) )
  {
    v8 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    {
      v9 = 29;
      goto LABEL_14;
    }
LABEL_15:
    if ( Block )
      free(Block);
    result = 2147942421LL;
    goto LABEL_158;
  }
  if ( (unsigned __int8)MpWatchDog::WdConfigManager::IsKillbitGatedFeatureEnabled(MpWatchDog::gMpWdConfigManager, 155) )
  {
    v13 = (const wchar_t *)&qword_1401E60A0;
    if ( a2 )
    {
      ProcessNameFromPID(S1, a2->EventHeader.ProcessId);
    }
    else
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 23, &WPP_3446203f0eb23a99ce68b6ff1fda97d5_Traceguids);
      *(_OWORD *)S1 = 0;
      N[0] = 0;
      N[1] = 0;
      v14 = &qword_1401E60A0;
      if ( (unsigned __int64)qword_1401E60B8 > 7 )
        v14 = (wchar_t **)qword_1401E60A0;
      std::wstring::_Construct<2,wchar_t const *>((__int64)S1, v14, qword_1401E60B0);
    }
    if ( (unsigned __int64)qword_1401E60B8 > 7 )
      v13 = qword_1401E60A0;
    v16 = N[0];
    v17 = (const wchar_t *)S1;
    if ( N[1] > 7 )
      v17 = S1[0];
    if ( N[0] == qword_1401E60B0 && (!N[0] || !wmemcmp(v17, v13, N[0])) )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
        WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 30, &WPP_3446203f0eb23a99ce68b6ff1fda97d5_Traceguids);
      goto LABEL_37;
    }
    if ( (unsigned __int8)Wd1dsListener::IsKnownSender(S1, v15, v16) )
    {
LABEL_37:
      std::wstring::_Tidy_deallocate(S1);
      goto LABEL_38;
    }
    v22 = 100 * (dword_1401E7478 / 0x64u);
    v23 = dword_1401E7478++;
    if ( v23 == v22 )
    {
      v24 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
      {
        v25 = 31;
LABEL_53:
        v26 = S1;
        if ( N[1] > 7 )
          v26 = (wchar_t **)S1[0];
        WPP_SF_S(*(_QWORD *)(v24 + 16), v25, &WPP_3446203f0eb23a99ce68b6ff1fda97d5_Traceguids, v26);
      }
    }
    else
    {
      v24 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
      {
        v25 = 32;
        goto LABEL_53;
      }
    }
    std::wstring::_Tidy_deallocate(S1);
    if ( Block )
      free(Block);
    result = 2147942450LL;
    goto LABEL_158;
  }
LABEL_38:
  EventInformation = GetEventInformation(a2, (struct _TRACE_EVENT_INFO **)&Block);
  v19 = EventInformation;
  v20 = (unsigned int *)Block;
  if ( EventInformation )
  {
    if ( EventInformation > 0 )
      v19 = (unsigned __int16)EventInformation | 0x80070000;
    goto LABEL_151;
  }
  if ( !Block )
  {
LABEL_151:
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
    {
LABEL_155:
      if ( v20 )
        free(v20);
      goto LABEL_157;
    }
    WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 33, &WPP_3446203f0eb23a99ce68b6ff1fda97d5_Traceguids, v19);
LABEL_154:
    v20 = (unsigned int *)Block;
    goto LABEL_155;
  }
  v21 = *((unsigned int *)Block + 12);
  if ( (_DWORD)v21 != 3 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && ((unsigned __int8)(EventInformation + 1) & *(_BYTE *)(WPP_GLOBAL_Control + 28LL)) != 0 )
    {
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        (unsigned int)(EventInformation + 34),
        &WPP_3446203f0eb23a99ce68b6ff1fda97d5_Traceguids,
        v21);
      v20 = (unsigned int *)Block;
    }
    goto LABEL_79;
  }
  ++*((_QWORD *)this + 11);
  v27 = (_WORD *)((char *)v20 + v20[17]);
  *(_OWORD *)S1 = 0;
  *(_OWORD *)N = 0;
  v28 = -1;
  do
    ++v28;
  while ( v27[v28] );
  std::wstring::_Construct<1,wchar_t const *>(S1, v27, v28);
  v29 = (const wchar_t *)S1;
  if ( N[1] > 7 )
    v29 = S1[0];
  if ( !wcscmp(v29, L"MdCommonAggregateMetric") )
    goto LABEL_161;
  v30 = (const wchar_t *)S1;
  if ( N[1] > 7 )
    v30 = S1[0];
  if ( !wcscmp(v30, L"MdCommonRawMetric") )
  {
LABEL_161:
    ++*((_QWORD *)this + 12);
    v31 = MpWatchDog::gMpWdConfigManager;
    v32 = (RTL_SRWLOCK *)((char *)MpWatchDog::gMpWdConfigManager + 848);
    AcquireSRWLockShared((PSRWLOCK)MpWatchDog::gMpWdConfigManager + 106);
    LOBYTE(v31) = *((_BYTE *)v31 + 768);
    ReleaseSRWLockShared(v32);
    if ( !(_BYTE)v31 )
    {
      v33 = 100 * (dword_1401E7478 / 0x64u);
      v34 = dword_1401E7478++;
      if ( v34 == v33 )
      {
        v35 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
        {
          v36 = 35;
LABEL_75:
          v37 = S1;
          if ( N[1] > 7 )
            v37 = (wchar_t **)S1[0];
          WPP_SF_S(*(_QWORD *)(v35 + 16), v36, &WPP_3446203f0eb23a99ce68b6ff1fda97d5_Traceguids, v37);
        }
      }
      else
      {
        v35 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
        {
          v36 = 36;
          goto LABEL_75;
        }
      }
      std::wstring::_Tidy_deallocate(S1);
      v20 = (unsigned int *)Block;
LABEL_79:
      if ( v20 )
        free(v20);
      v19 = -2147024846;
LABEL_157:
      result = v19;
LABEL_158:
      *((_QWORD *)this + 10) = 0;
      *((_QWORD *)this + 9) = 0;
      return result;
    }
  }
  if ( (a2->EventHeader.Flags & 4) != 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 40, &WPP_3446203f0eb23a99ce68b6ff1fda97d5_Traceguids);
    v19 = -2147024846;
LABEL_148:
    std::wstring::_Tidy_deallocate(S1);
    goto LABEL_154;
  }
  if ( (unsigned __int8)MpWatchDog::WdConfigManager::IsKillbitGatedFeatureEnabled(MpWatchDog::gMpWdConfigManager, 153)
    && !Wd1dsListener::VerifyRequiredAttributes(this, (struct _TRACE_EVENT_INFO *)Block, a2) )
  {
    v38 = S1;
    if ( N[1] > 7 )
      v38 = (wchar_t **)S1[0];
    (*(void (__fastcall **)(_QWORD, wchar_t **))(**((_QWORD **)this + 3) + 152LL))(*((_QWORD *)this + 3), v38);
    std::wstring::_Tidy_deallocate(S1);
    if ( Block )
      free(Block);
    v19 = -2147024809;
    goto LABEL_157;
  }
  v58 = a2->EventHeader.EventDescriptor.Keyword == 0x500000000000LL;
  if ( !a2->UserData || !a2->UserDataLength )
  {
    v57 = S1;
    if ( N[1] > 7 )
      v57 = (wchar_t **)S1[0];
    (*(void (__fastcall **)(_QWORD, wchar_t **))(**((_QWORD **)this + 3) + 152LL))(*((_QWORD *)this + 3), v57);
    std::wstring::_Tidy_deallocate(S1);
    if ( Block )
      free(Block);
    v19 = -2147024883;
    goto LABEL_157;
  }
  v39 = S1;
  if ( N[1] > 7 )
    v39 = (wchar_t **)S1[0];
  v40 = (*(__int64 (__fastcall **)(_QWORD, wchar_t **))(**((_QWORD **)this + 3) + 24LL))(*((_QWORD *)this + 3), v39);
  v19 = v40;
  if ( v40 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        37,
        &WPP_3446203f0eb23a99ce68b6ff1fda97d5_Traceguids,
        (unsigned int)v40);
    std::wstring::_Tidy_deallocate(S1);
    v20 = (unsigned int *)Block;
    goto LABEL_155;
  }
  UserData = (char *)a2->UserData;
  *((_QWORD *)this + 9) = UserData;
  *((_QWORD *)this + 10) = &UserData[a2->UserDataLength];
  v42 = Block;
  if ( !*((_DWORD *)Block + 26) )
  {
LABEL_125:
    if ( (unsigned __int8)MpWatchDog::WdConfigManager::IsKillbitGatedFeatureEnabled(MpWatchDog::gMpWdConfigManager, 184) )
    {
      v52 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 32LL))(*((_QWORD *)this + 3));
      v53 = S1;
      if ( N[1] > 7 )
        v53 = (wchar_t **)S1[0];
      if ( (unsigned __int8)Wd1dsListener::ShouldSampleOutIncomingEvent(this, a2, Block, v53, v58, v52) )
      {
        if ( MpWatchDog::MpIsCoreSvcInDevMode(v54) && MpWatchDog::GetMiscConfigDword((HKEY)&stru_14019DC40, 0, v55) == 1 )
          DebugBreak();
        std::wstring::_Tidy_deallocate(S1);
        if ( Block )
          free(Block);
        v19 = -2147024875;
        goto LABEL_157;
      }
    }
    else
    {
      v56 = *((_QWORD *)this + 13);
      if ( v56 && *(_BYTE *)(v56 + 88) )
      {
        std::_Hash<std::_Umap_traits<unsigned long,EventFrequencyMonitor::SenderRecord,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,EventFrequencyMonitor::SenderRecord>>,0>>::clear(v56 + 16);
        *(_BYTE *)(v56 + 88) = 0;
        *(_QWORD *)(v56 + 80) = *(_QWORD *)std::chrono::steady_clock::now(v59);
      }
    }
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 136LL))(*((_QWORD *)this + 3));
    goto LABEL_148;
  }
  while ( 1 )
  {
    v43 = (_WORD *)((char *)v42 + (unsigned int)v42[6 * v4 + 29]);
    *(_OWORD *)v65 = 0;
    v66 = 0;
    v44 = -1;
    do
      ++v44;
    while ( v43[v44] );
    std::wstring::_Construct<1,wchar_t const *>(v65, v43, v44);
    v47 = (__int16 *)&v42[6 * v4 + 32];
    if ( (v42[6 * v4 + 28] & 0xFFFFFFBF) != 0 )
      break;
    v45 = 1;
    if ( *v47 != 1 )
      break;
    v48 = (const wchar_t *)v65;
    if ( *((_QWORD *)&v66 + 1) > 7u )
      v48 = v65[0];
    v19 = Wd1dsListener::HandleAttribute(this, v48, v42[6 * v4 + 30], HIWORD(v42[6 * v4 + 30]));
    if ( (v19 & 0x80000000) != 0 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v49 = v65;
        if ( *((_QWORD *)&v66 + 1) > 7u )
          LODWORD(v49) = v65[0];
        WPP_SF_Sd(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          39,
          (unsigned int)&WPP_3446203f0eb23a99ce68b6ff1fda97d5_Traceguids,
          (_DWORD)v49,
          v19);
      }
      std::wstring::_Tidy_deallocate(v65);
      std::wstring::_Tidy_deallocate(S1);
      if ( Block )
        free(Block);
      *((_QWORD *)this + 10) = 0;
      *((_QWORD *)this + 9) = 0;
      return v19;
    }
    std::wstring::_Tidy_deallocate(v65);
    ++v4;
    v42 = Block;
    if ( v4 >= *((_DWORD *)Block + 26) )
      goto LABEL_125;
  }
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
  {
    v50 = *v47;
    v51 = v65;
    if ( *((_QWORD *)&v66 + 1) > 7u )
      LODWORD(v51) = v65[0];
    v46 = v42[6 * v4 + 28] & 0xFFFFFFBF;
    WPP_SF_SDH(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), v46, v45, (_DWORD)v51, v46, v50);
  }
  std::wstring::_Tidy_deallocate(v65);
  std::wstring::_Tidy_deallocate(S1);
  if ( Block )
    free(Block);
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 9) = 0;
  return 2147942450LL;
}

```

## disassembly

```asm
0x1400e4424  mov     [rsp-8+arg_10], rbx
0x1400e4429  push    rbp
0x1400e442a  push    rsi
0x1400e442b  push    rdi
0x1400e442c  push    r12
0x1400e442e  push    r13
0x1400e4430  push    r14
0x1400e4432  push    r15
0x1400e4434  lea     rbp, [rsp-27h]
0x1400e4439  sub     rsp, 0B0h
0x1400e4440  mov     rax, cs:__security_cookie
0x1400e4447  xor     rax, rsp
0x1400e444a  mov     [rbp+57h+var_40], rax
0x1400e444e  mov     r13, rdx
0x1400e4451  mov     rsi, rcx
0x1400e4454  xor     r12d, r12d
0x1400e4457  mov     [rbp+57h+Block], r12
0x1400e445b  mov     [rbp+57h+var_A0], r12b
0x1400e445f  lea     rax, [rbp+57h+Block]
0x1400e4463  mov     [rbp+57h+var_98], rax
0x1400e4467  mov     [rbp+57h+var_90], rcx
0x1400e446b  call    ?MpIsCoreSvcInDevMode@MpWatchDog@@YA_NXZ; MpWatchDog::MpIsCoreSvcInDevMode(void)
0x1400e4470  lea     ebx, [r12+1]
0x1400e4475  test    al, al
0x1400e4477  jz      short loc_1400E449D
0x1400e4479  xor     edx, edx; wchar_t *
0x1400e447b  lea     rcx, stru_14019DC00; this
0x1400e4482  call    ?GetMiscConfigDword@MpWatchDog@@YAKPEB_WK@Z; MpWatchDog::GetMiscConfigDword(wchar_t const *,ulong)
0x1400e4487  cmp     eax, ebx
0x1400e4489  jnz     short loc_1400E449D
0x1400e448b  mov     eax, ebx
0x1400e448d  xchg    al, cs:byte_1401E7488
0x1400e4493  test    al, al
0x1400e4495  jnz     short loc_1400E449D
0x1400e4497  call    cs:__imp_DebugBreak
0x1400e449d  call    ?Is1dsDisabled@MpWatchDog@@YA_NXZ; MpWatchDog::Is1dsDisabled(void)
0x1400e44a2  test    al, al
0x1400e44a4  jz      short loc_1400E44C6
0x1400e44a6  lea     r14, WPP_GLOBAL_Control
0x1400e44ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e44b4  cmp     rcx, r14
0x1400e44b7  jz      short loc_1400E4537
0x1400e44b9  test    byte ptr [rcx+1Ch], 4
0x1400e44bd  jz      short loc_1400E4537
0x1400e44bf  mov     edx, 1Ch
0x1400e44c4  jmp     short loc_1400E4526
0x1400e44c6  mov     rbx, cs:?gMpWdConfigManager@MpWatchDog@@3PEAVWdConfigManager@1@EA; MpWatchDog::WdConfigManager * MpWatchDog::gMpWdConfigManager
0x1400e44cd  lea     rdi, [rbx+350h]
0x1400e44d4  mov     rcx, rdi; SRWLock
0x1400e44d7  call    cs:__imp_AcquireSRWLockShared
0x1400e44dd  mov     bl, [rbx+328h]
0x1400e44e3  mov     rcx, rdi; SRWLock
0x1400e44e6  call    cs:__imp_ReleaseSRWLockShared
0x1400e44ec  test    bl, bl
0x1400e44ee  jnz     short loc_1400E454F
0x1400e44f0  mov     rcx, [rsi+18h]
0x1400e44f4  mov     rax, [rcx]
0x1400e44f7  mov     rax, [rax+0A0h]
0x1400e44fe  call    cs:__guard_dispatch_icall_fptr
0x1400e4504  test    al, al
0x1400e4506  jz      short loc_1400E454F
0x1400e4508  lea     r14, WPP_GLOBAL_Control
0x1400e450f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e4516  cmp     rcx, r14
0x1400e4519  jz      short loc_1400E4537
0x1400e451b  test    byte ptr [rcx+1Ch], 4
0x1400e451f  jz      short loc_1400E4537
0x1400e4521  mov     edx, 1Dh
0x1400e4526  lea     r8, WPP_3446203f0eb23a99ce68b6ff1fda97d5_Traceguids
0x1400e452d  mov     rcx, [rcx+10h]
0x1400e4531  call    WPP_SF_
0x1400e4536  nop
0x1400e4537  mov     rcx, [rbp+57h+Block]; Block
0x1400e453b  test    rcx, rcx
0x1400e453e  jz      short loc_1400E4545
0x1400e4540  call    free
0x1400e4545  mov     eax, 80070015h
0x1400e454a  jmp     loc_1400E4CD7
0x1400e454f  mov     edx, 9Bh
0x1400e4554  mov     rcx, cs:?gMpWdConfigManager@MpWatchDog@@3PEAVWdConfigManager@1@EA; MpWatchDog::WdConfigManager * MpWatchDog::gMpWdConfigManager
0x1400e455b  call    ?IsKillbitGatedFeatureEnabled@WdConfigManager@MpWatchDog@@QEBA_NW4FeatureControlEnum@@@Z; MpWatchDog::WdConfigManager::IsKillbitGatedFeatureEnabled(FeatureControlEnum)
0x1400e4560  lea     r14, WPP_GLOBAL_Control
0x1400e4567  lea     r15, WPP_3446203f0eb23a99ce68b6ff1fda97d5_Traceguids
0x1400e456e  test    al, al
0x1400e4570  jz      loc_1400E4659
0x1400e4576  lea     rbx, qword_1401E60A0
0x1400e457d  test    r13, r13
0x1400e4580  jnz     short loc_1400E45DA
0x1400e4582  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e4589  cmp     rcx, r14
0x1400e458c  jz      short loc_1400E45A6
0x1400e458e  lea     eax, [r13+1]
0x1400e4592  test    [rcx+1Ch], al
0x1400e4595  jz      short loc_1400E45A6
0x1400e4597  lea     edx, [rax+16h]
0x1400e459a  mov     r8, r15
0x1400e459d  mov     rcx, [rcx+10h]
0x1400e45a1  call    WPP_SF_
0x1400e45a6  xorps   xmm0, xmm0
0x1400e45a9  movups  xmmword ptr [rbp+57h+S1], xmm0
0x1400e45ad  mov     [rbp+57h+N], r12
0x1400e45b1  mov     [rbp+57h+N+8], r12
0x1400e45b5  mov     rdx, rbx
0x1400e45b8  cmp     cs:qword_1401E60B8, 7
0x1400e45c0  cmova   rdx, cs:qword_1401E60A0
0x1400e45c8  mov     r8, cs:qword_1401E60B0
0x1400e45cf  lea     rcx, [rbp+57h+S1]
0x1400e45d3  call    ??$_Construct@$01PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<2,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1400e45d8  jmp     short loc_1400E45E8
0x1400e45da  mov     edx, [r13+0Ch]
0x1400e45de  lea     rcx, [rbp+57h+S1]
0x1400e45e2  call    ?ProcessNameFromPID@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@Z; ProcessNameFromPID(ulong)
0x1400e45e7  nop
0x1400e45e8  cmp     cs:qword_1401E60B8, 7
0x1400e45f0  cmova   rbx, cs:qword_1401E60A0
0x1400e45f8  mov     r8, [rbp+57h+N]; N
0x1400e45fc  lea     rcx, [rbp+57h+S1]
0x1400e4600  cmp     [rbp+57h+N+8], 7
0x1400e4605  cmova   rcx, [rbp+57h+S1]; S1
0x1400e460a  cmp     r8, cs:qword_1401E60B0
0x1400e4611  jnz     loc_1400E46B8
0x1400e4617  test    r8, r8
0x1400e461a  jz      short loc_1400E462C
0x1400e461c  mov     rdx, rbx; S2
0x1400e461f  call    wmemcmp
0x1400e4624  test    eax, eax
0x1400e4626  jnz     loc_1400E46B8
0x1400e462c  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e4633  cmp     rcx, r14
0x1400e4636  jz      short loc_1400E4650
0x1400e4638  test    byte ptr [rcx+1Ch], 4
0x1400e463c  jz      short loc_1400E4650
0x1400e463e  mov     edx, 1Eh
0x1400e4643  mov     r8, r15
0x1400e4646  mov     rcx, [rcx+10h]
0x1400e464a  call    WPP_SF_
0x1400e464f  nop
0x1400e4650  lea     rcx, [rbp+57h+S1]
0x1400e4654  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400e4659  lea     rdx, [rbp+57h+Block]; struct _TRACE_EVENT_INFO **
0x1400e465d  mov     rcx, r13; struct _EVENT_RECORD *
0x1400e4660  call    ?GetEventInformation@@YAKPEAU_EVENT_RECORD@@AEAPEAU_TRACE_EVENT_INFO@@@Z; GetEventInformation(_EVENT_RECORD *,_TRACE_EVENT_INFO * &)
0x1400e4665  mov     ebx, eax
0x1400e4667  mov     rcx, [rbp+57h+Block]
0x1400e466b  test    eax, eax
0x1400e466d  jnz     loc_1400E4C91
0x1400e4673  test    rcx, rcx
0x1400e4676  jz      loc_1400E4C9C
0x1400e467c  mov     r9d, [rcx+30h]
0x1400e4680  cmp     r9d, 3
0x1400e4684  jz      loc_1400E4758
0x1400e468a  mov     rax, cs:WPP_GLOBAL_Control
0x1400e4691  cmp     rax, r14
0x1400e4694  jz      short loc_1400E46B3
0x1400e4696  lea     r8d, [rbx+1]
0x1400e469a  test    [rax+1Ch], r8b
0x1400e469e  jz      short loc_1400E46B3
0x1400e46a0  lea     edx, [rbx+22h]
0x1400e46a3  mov     r8, r15
0x1400e46a6  mov     rcx, [rax+10h]
0x1400e46aa  call    WPP_SF_d
0x1400e46af  mov     rcx, [rbp+57h+Block]
0x1400e46b3  jmp     loc_1400E487F
0x1400e46b8  lea     rcx, [rbp+57h+S1]
0x1400e46bc  call    ?IsKnownSender@Wd1dsListener@@CA_NAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Wd1dsListener::IsKnownSender(std::wstring &)
0x1400e46c1  test    al, al
0x1400e46c3  jnz     short loc_1400E4650
0x1400e46c5  mov     eax, 51EB851Fh
0x1400e46ca  mov     r8d, cs:dword_1401E7478
0x1400e46d1  mul     r8d
0x1400e46d4  shr     edx, 5
0x1400e46d7  imul    eax, edx, 64h ; 'd'
0x1400e46da  mov     ecx, r8d
0x1400e46dd  inc     r8d
0x1400e46e0  mov     cs:dword_1401E7478, r8d
0x1400e46e7  cmp     ecx, eax
0x1400e46e9  jnz     short loc_1400E4704
0x1400e46eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e46f2  cmp     rcx, r14
0x1400e46f5  jz      short loc_1400E4736
0x1400e46f7  test    byte ptr [rcx+1Ch], 2
0x1400e46fb  jz      short loc_1400E4736
0x1400e46fd  mov     edx, 1Fh
0x1400e4702  jmp     short loc_1400E471B
0x1400e4704  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e470b  cmp     rcx, r14
0x1400e470e  jz      short loc_1400E4736
0x1400e4710  test    byte ptr [rcx+1Ch], 4
0x1400e4714  jz      short loc_1400E4736
0x1400e4716  mov     edx, 20h ; ' '
0x1400e471b  lea     r9, [rbp+57h+S1]
0x1400e471f  cmp     [rbp+57h+N+8], 7
0x1400e4724  cmova   r9, [rbp+57h+S1]
0x1400e4729  mov     r8, r15
0x1400e472c  mov     rcx, [rcx+10h]
0x1400e4730  call    WPP_SF_S
0x1400e4735  nop
0x1400e4736  lea     rcx, [rbp+57h+S1]
0x1400e473a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400e473f  nop
0x1400e4740  mov     rcx, [rbp+57h+Block]; Block
0x1400e4744  test    rcx, rcx
0x1400e4747  jz      short loc_1400E474E
0x1400e4749  call    free
0x1400e474e  mov     eax, 80070032h
0x1400e4753  jmp     loc_1400E4CD7
0x1400e4758  mov     edi, 1
0x1400e475d  add     [rsi+58h], rdi
0x1400e4761  mov     edx, [rcx+44h]
0x1400e4764  add     rdx, rcx
0x1400e4767  xorps   xmm0, xmm0
0x1400e476a  movups  xmmword ptr [rbp+57h+S1], xmm0
0x1400e476e  xorps   xmm1, xmm1
0x1400e4771  movdqu  xmmword ptr [rbp+57h+N], xmm1
0x1400e4776  or      r8, 0FFFFFFFFFFFFFFFFh
0x1400e477a  inc     r8
0x1400e477d  cmp     [rdx+r8*2], r12w
0x1400e4782  jnz     short loc_1400E477A
0x1400e4784  lea     rcx, [rbp+57h+S1]
0x1400e4788  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1400e478d  nop
0x1400e478e  lea     rcx, [rbp+57h+S1]
0x1400e4792  cmp     [rbp+57h+N+8], 7
0x1400e4797  cmova   rcx, [rbp+57h+S1]; String1
0x1400e479c  lea     rdx, aMdcommonaggreg; "MdCommonAggregateMetric"
0x1400e47a3  call    wcscmp
0x1400e47a8  test    eax, eax
0x1400e47aa  jz      short loc_1400E47CE
0x1400e47ac  lea     rcx, [rbp+57h+S1]
0x1400e47b0  cmp     [rbp+57h+N+8], 7
0x1400e47b5  cmova   rcx, [rbp+57h+S1]; String1
0x1400e47ba  lea     rdx, aMdcommonrawmet; "MdCommonRawMetric"
0x1400e47c1  call    wcscmp
0x1400e47c6  test    eax, eax
0x1400e47c8  jnz     loc_1400E4898
0x1400e47ce  add     [rsi+60h], rdi
0x1400e47d2  mov     rbx, cs:?gMpWdConfigManager@MpWatchDog@@3PEAVWdConfigManager@1@EA; MpWatchDog::WdConfigManager * MpWatchDog::gMpWdConfigManager
0x1400e47d9  lea     rdi, [rbx+350h]
0x1400e47e0  mov     rcx, rdi; SRWLock
0x1400e47e3  call    cs:__imp_AcquireSRWLockShared
0x1400e47e9  mov     bl, [rbx+300h]
0x1400e47ef  mov     rcx, rdi; SRWLock
0x1400e47f2  call    cs:__imp_ReleaseSRWLockShared
0x1400e47f8  test    bl, bl
0x1400e47fa  jnz     loc_1400E4893
0x1400e4800  mov     eax, 51EB851Fh
0x1400e4805  mov     r8d, cs:dword_1401E7478
0x1400e480c  mul     r8d
0x1400e480f  shr     edx, 5
0x1400e4812  imul    eax, edx, 64h ; 'd'
0x1400e4815  mov     ecx, r8d
0x1400e4818  inc     r8d
0x1400e481b  mov     cs:dword_1401E7478, r8d
0x1400e4822  cmp     ecx, eax
0x1400e4824  jnz     short loc_1400E483F
0x1400e4826  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e482d  cmp     rcx, r14
0x1400e4830  jz      short loc_1400E4871
0x1400e4832  test    byte ptr [rcx+1Ch], 2
0x1400e4836  jz      short loc_1400E4871
0x1400e4838  mov     edx, 23h ; '#'
0x1400e483d  jmp     short loc_1400E4856
0x1400e483f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e4846  cmp     rcx, r14
0x1400e4849  jz      short loc_1400E4871
0x1400e484b  test    byte ptr [rcx+1Ch], 4
0x1400e484f  jz      short loc_1400E4871
0x1400e4851  mov     edx, 24h ; '$'
0x1400e4856  lea     r9, [rbp+57h+S1]
0x1400e485a  cmp     [rbp+57h+N+8], 7
0x1400e485f  cmova   r9, [rbp+57h+S1]
0x1400e4864  mov     r8, r15
0x1400e4867  mov     rcx, [rcx+10h]
0x1400e486b  call    WPP_SF_S
0x1400e4870  nop
0x1400e4871  lea     rcx, [rbp+57h+S1]
0x1400e4875  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400e487a  nop
0x1400e487b  mov     rcx, [rbp+57h+Block]; Block
0x1400e487f  test    rcx, rcx
0x1400e4882  jz      short loc_1400E4889
0x1400e4884  call    free
0x1400e4889  mov     ebx, 80070032h
0x1400e488e  jmp     loc_1400E4CD5
0x1400e4893  mov     edi, 1
0x1400e4898  test    byte ptr [r13+4], 4
0x1400e489d  jnz     loc_1400E4C5E
0x1400e48a3  mov     edx, 99h
0x1400e48a8  mov     rcx, cs:?gMpWdConfigManager@MpWatchDog@@3PEAVWdConfigManager@1@EA; MpWatchDog::WdConfigManager * MpWatchDog::gMpWdConfigManager
0x1400e48af  call    ?IsKillbitGatedFeatureEnabled@WdConfigManager@MpWatchDog@@QEBA_NW4FeatureControlEnum@@@Z; MpWatchDog::WdConfigManager::IsKillbitGatedFeatureEnabled(FeatureControlEnum)
0x1400e48b4  test    al, al
0x1400e48b6  jz      short loc_1400E4910
0x1400e48b8  mov     r8, r13; struct _EVENT_RECORD *
0x1400e48bb  mov     rdx, [rbp+57h+Block]; struct _TRACE_EVENT_INFO *
0x1400e48bf  mov     rcx, rsi; this
0x1400e48c2  call    ?VerifyRequiredAttributes@Wd1dsListener@@AEAA_NPEAU_TRACE_EVENT_INFO@@PEAU_EVENT_RECORD@@@Z; Wd1dsListener::VerifyRequiredAttributes(_TRACE_EVENT_INFO *,_EVENT_RECORD *)
0x1400e48c7  test    al, al
0x1400e48c9  jnz     short loc_1400E4910
0x1400e48cb  mov     rcx, [rsi+18h]
0x1400e48cf  mov     rax, [rcx]
  ... truncated ...
```
