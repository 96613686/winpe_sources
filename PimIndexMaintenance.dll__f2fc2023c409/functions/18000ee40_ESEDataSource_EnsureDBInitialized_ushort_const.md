# ESEDataSource::EnsureDBInitialized(ushort const *)

- ea: `0x18000ee40`
- end: `0x18000f212`
- name: `?EnsureDBInitialized@ESEDataSource@@QEAAJPEBG@Z`
- size: `978`
- prototype: `__int64 __fastcall(ESEDataSource *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `21`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180013768`
- `0x18001626c`
- `0x180017d74`

## callees

- `0x18000c800`
- `0x18000e544`
- `0x18000e634`
- `0x18000e670`
- `0x18000ee40`
- `0x18000f730`
- `0x18000f7e0`
- `0x18000fa6c`
- `0x18000fbcc`
- `0x1800104b8`
- `0x18001087c`
- `0x1800109d4`
- `0x18001122c`
- `0x180011b6c`
- `0x180011f70`
- `0x180012264`
- `0x180012384`
- `0x1800124a8`
- `0x1800128a4`
- `0x180016978`
- `0x180016a70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ee68`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ee68`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f0ba`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f0ba`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18000f0dd`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18000f0dd`

## pseudocode

```c
__int64 __fastcall ESEDataSource::EnsureDBInitialized(ESEDataSource *this, const unsigned __int16 *a2)
{
  const unsigned __int16 *v2; // rdx
  HKEY v3; // rcx
  int v4; // esi
  int i; // r14d
  int OldIndexingStoreVolumeFolderPath; // eax
  __int64 v7; // r8
  int v8; // ebx
  __int64 v9; // rdx
  ESEDataSource *v10; // rcx
  ESEDataSource *v11; // rcx
  int v12; // edi
  __int64 v13; // r8
  struct ESESession **v14; // rax
  int Instance; // eax
  __int64 v16; // r8
  int v17; // edx
  ESEDataSource *v18; // rcx
  int OldIndexingStoreVolumePath; // eax
  __int64 v20; // r8
  ESEDataSource *v22; // rcx
  int v23; // eax
  __int64 v24; // r8
  int v25; // eax
  __int64 v26; // r8
  int v27; // eax
  __int64 v28; // r8
  __int64 v29; // r9
  __int64 v30; // rcx
  __int64 v31; // r9
  __int64 v32; // r9
  unsigned __int16 *v33[4]; // [rsp+38h] [rbp-49h] BYREF
  _BYTE v34[32]; // [rsp+58h] [rbp-29h] BYREF
  LPCWSTR pszPath[4]; // [rsp+78h] [rbp-9h] BYREF
  _QWORD v36[8]; // [rsp+98h] [rbp+17h] BYREF
  ESESession *v37; // [rsp+E8h] [rbp+67h] BYREF
  const unsigned __int16 *v38; // [rsp+F0h] [rbp+6Fh] BYREF

  v38 = a2;
  v37 = this;
  EnterCriticalSection(&CriticalSection);
  if ( qword_18002D0B8 == -1 )
  {
    v4 = 0;
    for ( i = 0; i < 1 || v4 && i < 2; ++i )
    {
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v33);
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v34);
      if ( v4 )
      {
        OldIndexingStoreVolumeFolderPath = GetOldIndexingStoreVolumeFolderPath(v33);
        v8 = OldIndexingStoreVolumeFolderPath;
        if ( OldIndexingStoreVolumeFolderPath < 0 )
        {
          v29 = 123;
          goto LABEL_63;
        }
        OldIndexingStoreVolumeFolderPath = GetOldIndexingStoreVolumePath(v34);
        v8 = OldIndexingStoreVolumeFolderPath;
        if ( OldIndexingStoreVolumeFolderPath < 0 )
        {
          v29 = 124;
          goto LABEL_63;
        }
        v4 = 0;
      }
      else
      {
        OldIndexingStoreVolumeFolderPath = GetIndexingStoreVolumeFolderPath(v33);
        v8 = OldIndexingStoreVolumeFolderPath;
        if ( OldIndexingStoreVolumeFolderPath < 0 )
        {
          v29 = 130;
LABEL_63:
          v30 = (unsigned int)OldIndexingStoreVolumeFolderPath;
LABEL_64:
          Log_HREvent_2(v30, 1, v7, v29);
          goto LABEL_65;
        }
        OldIndexingStoreVolumeFolderPath = GetIndexingStoreVolumePath(v34);
        v8 = OldIndexingStoreVolumeFolderPath;
        if ( OldIndexingStoreVolumeFolderPath < 0 )
        {
          v29 = 131;
          goto LABEL_63;
        }
      }
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::swap(
        &qword_18002D0C8,
        v34);
      v8 = ESEDataSource::_MountVolume((ESEDataSource *)&g_dataSource, v33[0]);
      if ( v8 == -2147221291 )
      {
        v4 = 1;
        dword_18002D114 = 0;
      }
      else if ( v8 < 0 )
      {
        if ( (Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits & 0x80u) != 0 )
          McTemplateU0s_EventWriteTransfer(v10, v9, "Handling Upgrade/Corruption");
        if ( v8 != -2147023538 && v8 != -2147023504 && v8 != -2147221202 )
        {
          v29 = 186;
          v30 = (unsigned int)v8;
          goto LABEL_64;
        }
        v12 = ESEDataSource::_SetCorruptionKey(v10, 1);
        if ( v12 < 0 )
        {
          v32 = 155;
LABEL_60:
          Log_HREvent_2((unsigned int)v12, 1, v13, v32);
          v8 = v12;
LABEL_65:
          utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v34);
          utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v33);
          goto LABEL_37;
        }
        v12 = ESEDataSource::SetRebuildAllIndexesKey(v11, 1);
        if ( v12 < 0 )
        {
          v32 = 158;
          goto LABEL_60;
        }
        if ( v8 == -2147221202 )
        {
          OldIndexingStoreVolumeFolderPath = ESEDataSource::_InitJetInstance((ESEDataSource *)&g_dataSource, v33[0]);
          v8 = OldIndexingStoreVolumeFolderPath;
          if ( OldIndexingStoreVolumeFolderPath < 0 )
          {
            v29 = 162;
            goto LABEL_63;
          }
          v37 = 0;
          v14 = (struct ESESession **)tlx::replace<ESESession,&void tlx::_delete<ESESession>(ESESession *)>(&v37);
          Instance = ESESession::CreateInstance(qword_18002D0B8, 1, v14);
          v8 = Instance;
          if ( Instance < 0 )
          {
            v31 = 168;
LABEL_53:
            Log_HREvent_2((unsigned int)Instance, 1, v16, v31);
            if ( v37 )
              tlx::_delete<ESESession>();
            goto LABEL_65;
          }
          Instance = ESESession::DeleteAllTables(v37);
          v8 = Instance;
          if ( Instance < 0 )
          {
            v31 = 170;
            goto LABEL_53;
          }
          if ( v37 )
            tlx::_delete<ESESession>();
        }
        else
        {
          OldIndexingStoreVolumeFolderPath = wil::RemoveDirectoryRecursiveNoThrow(v33[0], 0, -1);
          v8 = OldIndexingStoreVolumeFolderPath;
          if ( OldIndexingStoreVolumeFolderPath < 0 )
          {
            v29 = 175;
            goto LABEL_63;
          }
        }
        OldIndexingStoreVolumeFolderPath = ESEDataSource::_MountVolume((ESEDataSource *)&g_dataSource, v33[0]);
        v8 = OldIndexingStoreVolumeFolderPath;
        if ( OldIndexingStoreVolumeFolderPath < 0 )
        {
          v29 = 181;
          goto LABEL_63;
        }
      }
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v34);
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v33);
    }
    LODWORD(v38) = 0;
    if ( (int)RegistryGetDWORD(v3, v2, L"DataMigration", (unsigned int *)&v38) < 0 || !(_DWORD)v38 )
    {
      if ( dword_18002D114 )
      {
        utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(pszPath);
        OldIndexingStoreVolumePath = GetOldIndexingStoreVolumePath(pszPath);
        if ( OldIndexingStoreVolumePath < 0 )
        {
          Log_HREvent_2((unsigned int)OldIndexingStoreVolumePath, 0, v20, 208);
          utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(pszPath);
          goto LABEL_36;
        }
        if ( PathFileExistsW(pszPath[0]) )
        {
          utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v36);
          if ( (int)GetOldIndexingStoreVolumeFolderPath(v36) >= 0 )
          {
            v23 = wil::RemoveDirectoryRecursiveNoThrow(v36[0], 0, -1);
            if ( v23 < 0 )
              Log_HREvent_2((unsigned int)v23, 0, v24, 220);
          }
          v25 = ESEDataSource::SetRebuildAllIndexesKey(v22, 1);
          if ( v25 < 0 )
            Log_HREvent_2((unsigned int)v25, 0, v26, 223);
          utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v36);
        }
        utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(pszPath);
      }
      v27 = ESEDataSource::_SetDataMigrationKey(v18, v17);
      if ( v27 < 0 )
        Log_HREvent_2((unsigned int)v27, 0, v28, 227);
    }
  }
LABEL_36:
  v8 = 0;
LABEL_37:
  LeaveCriticalSection(&CriticalSection);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000ee40  mov     rax, rsp
0x18000ee43  mov     [rax+18h], rbx
0x18000ee47  mov     [rax+10h], rdx
0x18000ee4b  mov     [rax+8], rcx
0x18000ee4f  push    rbp
0x18000ee50  push    rsi
0x18000ee51  push    rdi
0x18000ee52  push    r12
0x18000ee54  push    r14
0x18000ee56  lea     rbp, [rax-5Fh]
0x18000ee5a  sub     rsp, 0B0h
0x18000ee61  lea     rcx, CriticalSection; lpCriticalSection
0x18000ee68  call    cs:__imp_EnterCriticalSection
0x18000ee6e  cmp     cs:qword_18002D0B8, 0FFFFFFFFFFFFFFFFh
0x18000ee76  jnz     loc_18000F0B1
0x18000ee7c  xor     esi, esi
0x18000ee7e  xor     r14d, r14d
0x18000ee81  lea     r12d, [rsi+1]
0x18000ee85  cmp     r14d, r12d
0x18000ee88  jl      short loc_18000EE9C
0x18000ee8a  test    esi, esi
0x18000ee8c  jz      loc_18000F055
0x18000ee92  cmp     r14d, 2
0x18000ee96  jge     loc_18000F055
0x18000ee9c  lea     rcx, [rbp+57h+var_A0]
0x18000eea0  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x18000eea5  lea     rcx, [rbp+57h+var_80]
0x18000eea9  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x18000eeae  lea     rcx, [rbp+57h+var_A0]
0x18000eeb2  test    esi, esi
0x18000eeb4  jz      short loc_18000EEDC
0x18000eeb6  call    ?GetOldIndexingStoreVolumeFolderPath@@YAJPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; GetOldIndexingStoreVolumeFolderPath(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)
0x18000eebb  mov     ebx, eax
0x18000eebd  test    eax, eax
0x18000eebf  js      loc_18000F175
0x18000eec5  lea     rcx, [rbp+57h+var_80]
0x18000eec9  call    ?GetOldIndexingStoreVolumePath@@YAJPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; GetOldIndexingStoreVolumePath(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)
0x18000eece  mov     ebx, eax
0x18000eed0  test    eax, eax
0x18000eed2  js      loc_18000F16D
0x18000eed8  xor     esi, esi
0x18000eeda  jmp     short loc_18000EEFE
0x18000eedc  call    ?GetIndexingStoreVolumeFolderPath@@YAJPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; GetIndexingStoreVolumeFolderPath(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)
0x18000eee1  mov     ebx, eax
0x18000eee3  test    eax, eax
0x18000eee5  js      loc_18000F1EB
0x18000eeeb  lea     rcx, [rbp+57h+var_80]
0x18000eeef  call    ?GetIndexingStoreVolumePath@@YAJPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; GetIndexingStoreVolumePath(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)
0x18000eef4  mov     ebx, eax
0x18000eef6  test    eax, eax
0x18000eef8  js      loc_18000F1E3
0x18000eefe  lea     rdx, [rbp+57h+var_80]
0x18000ef02  lea     rcx, qword_18002D0C8
0x18000ef09  call    ?swap@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAAXAEAV12@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::swap(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)
0x18000ef0e  mov     rdx, [rbp+57h+var_A0]; unsigned __int16 *
0x18000ef12  lea     rcx, ?g_dataSource@@3VESEDataSource@@A; this
0x18000ef19  call    ?_MountVolume@ESEDataSource@@AEAAJPEBG@Z; ESEDataSource::_MountVolume(ushort const *)
0x18000ef1e  mov     ebx, eax
0x18000ef20  cmp     eax, 800400D5h
0x18000ef25  jnz     short loc_18000EF39
0x18000ef27  mov     esi, r12d
0x18000ef2a  mov     cs:dword_18002D114, 0
0x18000ef34  jmp     loc_18000F03B
0x18000ef39  test    ebx, ebx
0x18000ef3b  jns     loc_18000F03B
0x18000ef41  cmp     byte ptr cs:Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits, 0
0x18000ef48  jge     short loc_18000EF56
0x18000ef4a  lea     r8, aHandlingUpgrad; "Handling Upgrade/Corruption"
0x18000ef51  call    McTemplateU0s_EventWriteTransfer
0x18000ef56  cmp     ebx, 8007054Eh
0x18000ef5c  jz      short loc_18000EF72
0x18000ef5e  cmp     ebx, 80070570h
0x18000ef64  jz      short loc_18000EF72
0x18000ef66  cmp     ebx, 8004012Eh
0x18000ef6c  jnz     loc_18000F17D
0x18000ef72  mov     edx, r12d; int
0x18000ef75  call    ?_SetCorruptionKey@ESEDataSource@@AEAAJH@Z; ESEDataSource::_SetCorruptionKey(int)
0x18000ef7a  mov     edi, eax
0x18000ef7c  mov     edx, r12d; int
0x18000ef7f  test    eax, eax
0x18000ef81  js      loc_18000F1D2
0x18000ef87  call    ?SetRebuildAllIndexesKey@ESEDataSource@@QEAAJH@Z; ESEDataSource::SetRebuildAllIndexesKey(int)
0x18000ef8c  mov     edi, eax
0x18000ef8e  test    eax, eax
0x18000ef90  js      loc_18000F1C7
0x18000ef96  cmp     ebx, 8004012Eh
0x18000ef9c  jnz     short loc_18000F008
0x18000ef9e  mov     rdx, [rbp+57h+var_A0]; unsigned __int16 *
0x18000efa2  lea     rcx, ?g_dataSource@@3VESEDataSource@@A; this
0x18000efa9  call    ?_InitJetInstance@ESEDataSource@@AEAAJPEBG@Z; ESEDataSource::_InitJetInstance(ushort const *)
0x18000efae  mov     ebx, eax
0x18000efb0  test    eax, eax
0x18000efb2  js      loc_18000F1AF
0x18000efb8  lea     rcx, [rbp+57h+arg_0]
0x18000efbc  mov     [rbp+57h+arg_0], 0
0x18000efc4  call    ??$replace@VESESession@@$1??$_delete@VESESession@@@tlx@@YAXPEAV1@@Z@tlx@@YAPEAPEAVESESession@@AEAV?$auto_ptr@VESESession@@$1??$_delete@VESESession@@@tlx@@YAXPEAV1@@Z@0@@Z; tlx::replace<ESESession,&tlx::_delete<ESESession>(ESESession *)>(tlx::auto_ptr<ESESession,&tlx::_delete<ESESession>(ESESession *)> &)
0x18000efc9  mov     rcx, cs:qword_18002D0B8; unsigned __int64
0x18000efd0  mov     r8, rax; struct ESESession **
0x18000efd3  mov     edx, r12d; int
0x18000efd6  call    ?CreateInstance@ESESession@@SAJ_KHPEAPEAV1@@Z; ESESession::CreateInstance(unsigned __int64,int,ESESession * *)
0x18000efdb  mov     ebx, eax
0x18000efdd  test    eax, eax
0x18000efdf  js      loc_18000F18F
0x18000efe5  mov     rcx, [rbp+57h+arg_0]; this
0x18000efe9  call    ?DeleteAllTables@ESESession@@QEAAJXZ; ESESession::DeleteAllTables(void)
0x18000efee  mov     ebx, eax
0x18000eff0  test    eax, eax
0x18000eff2  js      loc_18000F187
0x18000eff8  mov     rcx, [rbp+57h+arg_0]
0x18000effc  test    rcx, rcx
0x18000efff  jz      short loc_18000F021
0x18000f001  call    ??$_delete@VESESession@@@tlx@@YAXPEAVESESession@@@Z; tlx::_delete<ESESession>(ESESession *)
0x18000f006  jmp     short loc_18000F021
0x18000f008  mov     rcx, [rbp+57h+var_A0]
0x18000f00c  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000f010  xor     edx, edx
0x18000f012  call    ?RemoveDirectoryRecursiveNoThrow@wil@@YAJPEBGW4RemoveDirectoryOptions@1@PEAX@Z; wil::RemoveDirectoryRecursiveNoThrow(ushort const *,wil::RemoveDirectoryOptions,void *)
0x18000f017  mov     ebx, eax
0x18000f019  test    eax, eax
0x18000f01b  js      loc_18000F1BF
0x18000f021  mov     rdx, [rbp+57h+var_A0]; unsigned __int16 *
0x18000f025  lea     rcx, ?g_dataSource@@3VESEDataSource@@A; this
0x18000f02c  call    ?_MountVolume@ESEDataSource@@AEAAJPEBG@Z; ESEDataSource::_MountVolume(ushort const *)
0x18000f031  mov     ebx, eax
0x18000f033  test    eax, eax
0x18000f035  js      loc_18000F1B7
0x18000f03b  lea     rcx, [rbp+57h+var_80]
0x18000f03f  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18000f044  lea     rcx, [rbp+57h+var_A0]
0x18000f048  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18000f04d  add     r14d, r12d
0x18000f050  jmp     loc_18000EE85
0x18000f055  lea     r9, [rbp+57h+arg_8]; unsigned int *
0x18000f059  mov     dword ptr [rbp+57h+arg_8], 0
0x18000f060  lea     r8, aDatamigration; "DataMigration"
0x18000f067  call    ?RegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; RegistryGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18000f06c  test    eax, eax
0x18000f06e  js      short loc_18000F076
0x18000f070  cmp     dword ptr [rbp+57h+arg_8], 0
0x18000f074  jnz     short loc_18000F0B1
0x18000f076  cmp     cs:dword_18002D114, 0
0x18000f07d  jz      loc_18000F14C
0x18000f083  lea     rcx, [rbp+57h+pszPath]
0x18000f087  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x18000f08c  lea     rcx, [rbp+57h+pszPath]
0x18000f090  call    ?GetOldIndexingStoreVolumePath@@YAJPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; GetOldIndexingStoreVolumePath(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)
0x18000f095  test    eax, eax
0x18000f097  jns     short loc_18000F0D9
0x18000f099  xor     edx, edx
0x18000f09b  mov     r9d, 0D0h
0x18000f0a1  mov     ecx, eax
0x18000f0a3  call    Log_HREvent_2
0x18000f0a8  lea     rcx, [rbp+57h+pszPath]
0x18000f0ac  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18000f0b1  xor     ebx, ebx
0x18000f0b3  lea     rcx, CriticalSection; lpCriticalSection
0x18000f0ba  call    cs:__imp_LeaveCriticalSection
0x18000f0c0  mov     eax, ebx
0x18000f0c2  mov     rbx, [rsp+0D0h+arg_10]
0x18000f0ca  add     rsp, 0B0h
0x18000f0d1  pop     r14
0x18000f0d3  pop     r12
0x18000f0d5  pop     rdi
0x18000f0d6  pop     rsi
0x18000f0d7  pop     rbp
0x18000f0d8  retn
0x18000f0d9  mov     rcx, [rbp+57h+pszPath]; pszPath
0x18000f0dd  call    cs:__imp_PathFileExistsW
0x18000f0e3  test    eax, eax
0x18000f0e5  jz      short loc_18000F143
0x18000f0e7  lea     rcx, [rbp+57h+var_40]
0x18000f0eb  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x18000f0f0  lea     rcx, [rbp+57h+var_40]
0x18000f0f4  call    ?GetOldIndexingStoreVolumeFolderPath@@YAJPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; GetOldIndexingStoreVolumeFolderPath(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)
0x18000f0f9  test    eax, eax
0x18000f0fb  js      short loc_18000F11F
0x18000f0fd  mov     rcx, [rbp+57h+var_40]
0x18000f101  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000f105  xor     edx, edx
0x18000f107  call    ?RemoveDirectoryRecursiveNoThrow@wil@@YAJPEBGW4RemoveDirectoryOptions@1@PEAX@Z; wil::RemoveDirectoryRecursiveNoThrow(ushort const *,wil::RemoveDirectoryOptions,void *)
0x18000f10c  test    eax, eax
0x18000f10e  jns     short loc_18000F11F
0x18000f110  xor     edx, edx
0x18000f112  mov     r9d, 0DCh
0x18000f118  mov     ecx, eax
0x18000f11a  call    Log_HREvent_2
0x18000f11f  mov     edx, r12d; int
0x18000f122  call    ?SetRebuildAllIndexesKey@ESEDataSource@@QEAAJH@Z; ESEDataSource::SetRebuildAllIndexesKey(int)
0x18000f127  test    eax, eax
0x18000f129  jns     short loc_18000F13A
0x18000f12b  xor     edx, edx
0x18000f12d  mov     r9d, 0DFh
0x18000f133  mov     ecx, eax
0x18000f135  call    Log_HREvent_2
0x18000f13a  lea     rcx, [rbp+57h+var_40]
0x18000f13e  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18000f143  lea     rcx, [rbp+57h+pszPath]
0x18000f147  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18000f14c  call    ?_SetDataMigrationKey@ESEDataSource@@AEAAJH@Z; ESEDataSource::_SetDataMigrationKey(int)
0x18000f151  test    eax, eax
0x18000f153  jns     loc_18000F0B1
0x18000f159  xor     edx, edx
0x18000f15b  mov     r9d, 0E3h
0x18000f161  mov     ecx, eax
0x18000f163  call    Log_HREvent_2
0x18000f168  jmp     loc_18000F0B1
0x18000f16d  mov     r9d, 7Ch ; '|'
0x18000f173  jmp     short loc_18000F1F1
0x18000f175  mov     r9d, 7Bh ; '{'
0x18000f17b  jmp     short loc_18000F1F1
0x18000f17d  mov     r9d, 0BAh
0x18000f183  mov     ecx, ebx
0x18000f185  jmp     short loc_18000F1F3
0x18000f187  mov     r9d, 0AAh
0x18000f18d  jmp     short loc_18000F195
0x18000f18f  mov     r9d, 0A8h
0x18000f195  mov     edx, r12d
0x18000f198  mov     ecx, eax
0x18000f19a  call    Log_HREvent_2
0x18000f19f  mov     rcx, [rbp+57h+arg_0]
0x18000f1a3  test    rcx, rcx
0x18000f1a6  jz      short loc_18000F1FB
0x18000f1a8  call    ??$_delete@VESESession@@@tlx@@YAXPEAVESESession@@@Z; tlx::_delete<ESESession>(ESESession *)
0x18000f1ad  jmp     short loc_18000F1FB
0x18000f1af  mov     r9d, 0A2h
0x18000f1b5  jmp     short loc_18000F1F1
0x18000f1b7  mov     r9d, 0B5h
0x18000f1bd  jmp     short loc_18000F1F1
0x18000f1bf  mov     r9d, 0AFh
0x18000f1c5  jmp     short loc_18000F1F1
0x18000f1c7  mov     r9d, 9Eh
0x18000f1cd  mov     edx, r12d
0x18000f1d0  jmp     short loc_18000F1D8
0x18000f1d2  mov     r9d, 9Bh
0x18000f1d8  mov     ecx, edi
0x18000f1da  call    Log_HREvent_2
0x18000f1df  mov     ebx, edi
0x18000f1e1  jmp     short loc_18000F1FB
0x18000f1e3  mov     r9d, 83h
0x18000f1e9  jmp     short loc_18000F1F1
0x18000f1eb  mov     r9d, 82h
0x18000f1f1  mov     ecx, eax
0x18000f1f3  mov     edx, r12d
0x18000f1f6  call    Log_HREvent_2
0x18000f1fb  lea     rcx, [rbp+57h+var_80]
0x18000f1ff  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18000f204  lea     rcx, [rbp+57h+var_A0]
0x18000f208  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18000f20d  jmp     loc_18000F0B3
```
