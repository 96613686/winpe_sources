# ESEDataSource::_MountVolume(ushort const *)

- ea: `0x180011f70`
- end: `0x18001220c`
- name: `?_MountVolume@ESEDataSource@@AEAAJPEBG@Z`
- size: `668`
- prototype: `__int64 __fastcall(ESEDataSource *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000ee40`

## callees

- `0x18000c800`
- `0x18000e544`
- `0x18000e634`
- `0x18000e660`
- `0x18000e838`
- `0x180010478`
- `0x1800104b8`
- `0x18001087c`
- `0x18001122c`
- `0x18001134c`
- `0x180011930`
- `0x180011b6c`
- `0x180011f70`
- `0x180012264`
- `0x180016978`
- `0x18001706c`
- `0x180017f74`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011fc9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011fc9`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x180011fbb`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x180011fbb`
- `api-ms-win-shell-shdirectory-l1-1-0!__imp_SHCreateDirectoryExW` at `0x180012014`
- `api-ms-win-shell-shdirectory-l1-1-0!__imp_SHCreateDirectoryExW` at `0x180012014`

## string_xrefs

- `0x180011f89`: `Mounting Indexing Volume`

## pseudocode

```c
__int64 __fastcall ESEDataSource::_MountVolume(ESEDataSource *this, const unsigned __int16 *a2)
{
  ESEDataSource *v4; // rcx
  signed int LastError; // eax
  __int64 v6; // r8
  unsigned int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // rcx
  int v10; // eax
  __int64 v11; // r8
  __int64 v12; // rdx
  __int64 v13; // r9
  __int64 v14; // rcx
  int inited; // eax
  ESESession **v16; // rbx
  struct ESESession **v17; // rax
  int Instance; // eax
  __int64 v19; // r8
  int v20; // esi
  __int64 v21; // r8
  __int64 v22; // r9
  const unsigned __int16 *v23; // rdx
  ESEDataSource *v24; // rcx
  ESEDataSource *v25; // rcx
  int DWORD; // eax
  ESEDataSource *v27; // rcx
  BOOL v28; // eax
  ESEDataSource *v29; // rcx
  __int64 v31; // [rsp+30h] [rbp-38h] BYREF
  char v32; // [rsp+38h] [rbp-30h]
  unsigned int v33; // [rsp+80h] [rbp+18h] BYREF

  if ( (Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits & 0x80u) != 0 )
    McTemplateU0s_EventWriteTransfer(this, a2, "Mounting Indexing Volume");
  v32 = 1;
  v31 = *(_QWORD *)lambda_7255da319444d40a48fc2fbaf62da9e9_::_lambda_7255da319444d40a48fc2fbaf62da9e9_(&v33, this);
  if ( !PathFileExistsW(a2) )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( (unsigned int)(LastError - 2) > 1 )
    {
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
      Log_HREvent_2(v7, 0, v6, 569);
      if ( !v7 )
        Log_AssertionEvent_1(v9, v8, 569);
      goto LABEL_49;
    }
    v10 = SHCreateDirectoryExW(0, a2, 0);
    v7 = v10;
    if ( v10 != 183 && v10 != 80 && v10 )
    {
      if ( v10 > 0 )
        v7 = (unsigned __int16)v10 | 0x80070000;
      v12 = 0;
      v13 = 576;
      v14 = v7;
      goto LABEL_15;
    }
  }
  v33 = 0;
  ESEDataSource::_GetCorruptionKey(v4, (int *)&v33);
  inited = ESEDataSource::_InitJetInstance(this, a2);
  v7 = inited;
  if ( inited < 0 )
  {
    v13 = 583;
LABEL_18:
    v12 = 1;
    v14 = (unsigned int)inited;
LABEL_15:
    Log_HREvent_2(v14, v12, v11, v13);
    goto LABEL_49;
  }
  v16 = (ESESession **)((char *)this + 16);
  if ( !*((_QWORD *)this + 2) )
  {
    v17 = (struct ESESession **)tlx::replace<ESESession,&void tlx::_delete<ESESession>(ESESession *)>((char *)this + 16);
    Instance = ESESession::CreateInstance(*((_QWORD *)this + 1), 1, v17);
    v20 = Instance;
    if ( Instance < 0 )
    {
      Log_HREvent_2((unsigned int)Instance, 1, v19, 645);
      v22 = 586;
      goto LABEL_22;
    }
  }
  v20 = ESESession::EnsureIndexInfoTable(*v16);
  if ( v20 != -2147221202 )
  {
    if ( v20 >= 0 )
    {
      if ( v33 )
      {
        v20 = ESEDataSource::SetRebuildAllIndexesKey(v24, 1);
        if ( v20 < 0 )
        {
          v22 = 603;
          goto LABEL_22;
        }
        v20 = ESEDataSource::_SetCorruptionKey(v25, 0);
        if ( v20 < 0 )
        {
          v22 = 606;
          goto LABEL_22;
        }
      }
      v33 = 0;
      DWORD = RegistryGetDWORD((HKEY)v24, v23, L"RebuildUnicodeIndexes", &v33);
      if ( DWORD == -2147024894 )
        v28 = 0;
      else
        v28 = DWORD < 0 || v33 != 0;
      if ( *((_DWORD *)this + 24) || v28 )
      {
        v20 = ESEDataSource::SetRebuildUnicodeIndexesKey(v27, 1);
        if ( v20 < 0 )
        {
          v22 = 620;
          goto LABEL_22;
        }
        inited = ESESession::UpdateUnicodeIndexes(*v16);
        v7 = inited;
        if ( inited < 0 )
        {
          v13 = 622;
          goto LABEL_18;
        }
        inited = ESEDataSource::SetRebuildUnicodeIndexesKey(v29, 0);
        v7 = inited;
        if ( inited < 0 )
        {
          v13 = 624;
          goto LABEL_18;
        }
        *((_DWORD *)this + 24) = 0;
      }
      v32 = 0;
      v7 = 0;
      goto LABEL_49;
    }
    v22 = 597;
LABEL_22:
    Log_HREvent_2((unsigned int)v20, 1, v21, v22);
    v7 = v20;
    goto LABEL_49;
  }
  if ( *v16 )
  {
    tlx::_delete<ESESession>();
    *v16 = 0;
  }
  Log_HREvent_2(2147746094LL, 0, v21, 593);
  v7 = -2147221202;
LABEL_49:
  tlx::_UndoSolo__lambda_1fb8751aff92b07bb4d4dd00c3ca69f0___::__UndoSolo__lambda_1fb8751aff92b07bb4d4dd00c3ca69f0___(&v31);
  return v7;
}

```

## disassembly

```asm
0x180011f70  push    rbx
0x180011f72  push    rsi
0x180011f73  push    rdi
0x180011f74  push    r14
0x180011f76  sub     rsp, 48h
0x180011f7a  test    byte ptr cs:Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits, 80h
0x180011f81  mov     rsi, rdx
0x180011f84  mov     rdi, rcx
0x180011f87  jz      short loc_180011F95
0x180011f89  lea     r8, aMountingIndexi; "Mounting Indexing Volume"
0x180011f90  call    McTemplateU0s_EventWriteTransfer
0x180011f95  mov     rdx, rdi
0x180011f98  lea     rcx, [rsp+68h+arg_10]
0x180011fa0  call    _lambda_7255da319444d40a48fc2fbaf62da9e9____lambda_7255da319444d40a48fc2fbaf62da9e9_
0x180011fa5  mov     r14d, 1
0x180011fab  mov     rcx, rsi; pszPath
0x180011fae  mov     [rsp+68h+var_30], r14b
0x180011fb3  mov     rdx, [rax]
0x180011fb6  mov     [rsp+68h+var_38], rdx
0x180011fbb  call    cs:__imp_PathFileExistsW
0x180011fc1  test    eax, eax
0x180011fc3  jnz     loc_18001204B
0x180011fc9  call    cs:__imp_GetLastError
0x180011fcf  mov     ebx, eax
0x180011fd1  lea     ecx, [rax-2]
0x180011fd4  cmp     ecx, r14d
0x180011fd7  jbe     short loc_18001200C
0x180011fd9  test    eax, eax
0x180011fdb  jle     short loc_180011FE6
0x180011fdd  movzx   ebx, ax
0x180011fe0  or      ebx, 80070000h
0x180011fe6  mov     edi, 239h
0x180011feb  xor     edx, edx
0x180011fed  mov     r9d, edi
0x180011ff0  mov     ecx, ebx
0x180011ff2  call    Log_HREvent_2
0x180011ff7  test    ebx, ebx
0x180011ff9  jnz     loc_1800121F6
0x180011fff  mov     r8d, edi
0x180012002  call    Log_AssertionEvent_1
0x180012007  jmp     loc_1800121F6
0x18001200c  xor     r8d, r8d; psa
0x18001200f  mov     rdx, rsi; pszPath
0x180012012  xor     ecx, ecx; hwnd
0x180012014  call    cs:__imp_SHCreateDirectoryExW
0x18001201a  mov     ebx, eax
0x18001201c  cmp     eax, 0B7h
0x180012021  jz      short loc_18001204B
0x180012023  cmp     eax, 50h ; 'P'
0x180012026  jz      short loc_18001204B
0x180012028  test    eax, eax
0x18001202a  jz      short loc_18001204B
0x18001202c  jle     short loc_180012037
0x18001202e  movzx   ebx, ax
0x180012031  or      ebx, 80070000h
0x180012037  xor     edx, edx
0x180012039  mov     r9d, 240h
0x18001203f  mov     ecx, ebx
0x180012041  call    Log_HREvent_2
0x180012046  jmp     loc_1800121F6
0x18001204b  lea     rdx, [rsp+68h+arg_10]; int *
0x180012053  mov     [rsp+68h+arg_10], 0
0x18001205e  call    ?_GetCorruptionKey@ESEDataSource@@AEAAXPEAH@Z; ESEDataSource::_GetCorruptionKey(int *)
0x180012063  mov     rdx, rsi; unsigned __int16 *
0x180012066  mov     rcx, rdi; this
0x180012069  call    ?_InitJetInstance@ESEDataSource@@AEAAJPEBG@Z; ESEDataSource::_InitJetInstance(ushort const *)
0x18001206e  mov     ebx, eax
0x180012070  test    eax, eax
0x180012072  jns     short loc_180012081
0x180012074  mov     r9d, 247h
0x18001207a  mov     edx, r14d
0x18001207d  mov     ecx, eax
0x18001207f  jmp     short loc_180012041
0x180012081  lea     rbx, [rdi+10h]
0x180012085  cmp     qword ptr [rbx], 0
0x180012089  jnz     short loc_1800120CF
0x18001208b  mov     rcx, rbx
0x18001208e  call    ??$replace@VESESession@@$1??$_delete@VESESession@@@tlx@@YAXPEAV1@@Z@tlx@@YAPEAPEAVESESession@@AEAV?$auto_ptr@VESESession@@$1??$_delete@VESESession@@@tlx@@YAXPEAV1@@Z@0@@Z; tlx::replace<ESESession,&tlx::_delete<ESESession>(ESESession *)>(tlx::auto_ptr<ESESession,&tlx::_delete<ESESession>(ESESession *)> &)
0x180012093  mov     rcx, [rdi+8]; unsigned __int64
0x180012097  mov     r8, rax; struct ESESession **
0x18001209a  mov     edx, r14d; int
0x18001209d  call    ?CreateInstance@ESESession@@SAJ_KHPEAPEAV1@@Z; ESESession::CreateInstance(unsigned __int64,int,ESESession * *)
0x1800120a2  mov     esi, eax
0x1800120a4  test    eax, eax
0x1800120a6  jns     short loc_1800120CF
0x1800120a8  mov     r9d, 285h
0x1800120ae  mov     edx, r14d
0x1800120b1  mov     ecx, eax
0x1800120b3  call    Log_HREvent_2
0x1800120b8  mov     r9d, 24Ah
0x1800120be  mov     edx, r14d
0x1800120c1  mov     ecx, esi
0x1800120c3  call    Log_HREvent_2
0x1800120c8  mov     ebx, esi
0x1800120ca  jmp     loc_1800121F6
0x1800120cf  mov     rcx, [rbx]; this
0x1800120d2  call    ?EnsureIndexInfoTable@ESESession@@QEAAJXZ; ESESession::EnsureIndexInfoTable(void)
0x1800120d7  mov     esi, eax
0x1800120d9  cmp     eax, 8004012Eh
0x1800120de  jnz     short loc_180012110
0x1800120e0  mov     rcx, [rbx]
0x1800120e3  test    rcx, rcx
0x1800120e6  jz      short loc_1800120F4
0x1800120e8  call    ??$_delete@VESESession@@@tlx@@YAXPEAVESESession@@@Z; tlx::_delete<ESESession>(ESESession *)
0x1800120ed  mov     qword ptr [rbx], 0
0x1800120f4  xor     edx, edx
0x1800120f6  mov     ecx, 8004012Eh
0x1800120fb  mov     r9d, 251h
0x180012101  call    Log_HREvent_2
0x180012106  mov     ebx, 8004012Eh
0x18001210b  jmp     loc_1800121F6
0x180012110  test    esi, esi
0x180012112  jns     short loc_18001211C
0x180012114  mov     r9d, 255h
0x18001211a  jmp     short loc_1800120BE
0x18001211c  cmp     [rsp+68h+arg_10], 0
0x180012124  jz      short loc_180012154
0x180012126  mov     edx, r14d; int
0x180012129  call    ?SetRebuildAllIndexesKey@ESEDataSource@@QEAAJH@Z; ESEDataSource::SetRebuildAllIndexesKey(int)
0x18001212e  mov     esi, eax
0x180012130  test    eax, eax
0x180012132  jns     short loc_18001213C
0x180012134  mov     r9d, 25Bh
0x18001213a  jmp     short loc_1800120BE
0x18001213c  xor     edx, edx; int
0x18001213e  call    ?_SetCorruptionKey@ESEDataSource@@AEAAJH@Z; ESEDataSource::_SetCorruptionKey(int)
0x180012143  mov     esi, eax
0x180012145  test    eax, eax
0x180012147  jns     short loc_180012154
0x180012149  mov     r9d, 25Eh
0x18001214f  jmp     loc_1800120BE
0x180012154  lea     r9, [rsp+68h+arg_10]; unsigned int *
0x18001215c  mov     [rsp+68h+arg_10], 0
0x180012167  lea     r8, aRebuildunicode; "RebuildUnicodeIndexes"
0x18001216e  call    ?RegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; RegistryGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x180012173  cmp     eax, 80070002h
0x180012178  jnz     short loc_18001217E
0x18001217a  xor     eax, eax
0x18001217c  jmp     short loc_180012194
0x18001217e  test    eax, eax
0x180012180  jns     short loc_180012187
0x180012182  mov     eax, r14d
0x180012185  jmp     short loc_180012194
0x180012187  xor     eax, eax
0x180012189  cmp     [rsp+68h+arg_10], eax
0x180012190  cmovnz  eax, r14d
0x180012194  cmp     dword ptr [rdi+60h], 0
0x180012198  jnz     short loc_18001219E
0x18001219a  test    eax, eax
0x18001219c  jz      short loc_1800121EF
0x18001219e  mov     edx, r14d; int
0x1800121a1  call    ?SetRebuildUnicodeIndexesKey@ESEDataSource@@QEAAJH@Z; ESEDataSource::SetRebuildUnicodeIndexesKey(int)
0x1800121a6  mov     esi, eax
0x1800121a8  test    eax, eax
0x1800121aa  jns     short loc_1800121B7
0x1800121ac  mov     r9d, 26Ch
0x1800121b2  jmp     loc_1800120BE
0x1800121b7  mov     rcx, [rbx]; this
0x1800121ba  call    ?UpdateUnicodeIndexes@ESESession@@QEAAJXZ; ESESession::UpdateUnicodeIndexes(void)
0x1800121bf  mov     ebx, eax
0x1800121c1  test    eax, eax
0x1800121c3  jns     short loc_1800121D0
0x1800121c5  mov     r9d, 26Eh
0x1800121cb  jmp     loc_18001207A
0x1800121d0  xor     edx, edx; int
0x1800121d2  call    ?SetRebuildUnicodeIndexesKey@ESEDataSource@@QEAAJH@Z; ESEDataSource::SetRebuildUnicodeIndexesKey(int)
0x1800121d7  mov     ebx, eax
0x1800121d9  test    eax, eax
0x1800121db  jns     short loc_1800121E8
0x1800121dd  mov     r9d, 270h
0x1800121e3  jmp     loc_18001207A
0x1800121e8  mov     dword ptr [rdi+60h], 0
0x1800121ef  mov     [rsp+68h+var_30], 0
0x1800121f4  xor     ebx, ebx
0x1800121f6  lea     rcx, [rsp+68h+var_38]
0x1800121fb  call    tlx___UndoSolo__lambda_1fb8751aff92b07bb4d4dd00c3ca69f0_______UndoSolo__lambda_1fb8751aff92b07bb4d4dd00c3ca69f0___
0x180012200  mov     eax, ebx
0x180012202  add     rsp, 48h
0x180012206  pop     r14
0x180012208  pop     rdi
0x180012209  pop     rsi
0x18001220a  pop     rbx
0x18001220b  retn
```
