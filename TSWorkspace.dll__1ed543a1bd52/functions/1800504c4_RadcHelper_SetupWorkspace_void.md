# RadcHelper::SetupWorkspace(void)

- ea: `0x1800504c4`
- end: `0x180050ad2`
- name: `?SetupWorkspace@RadcHelper@@QEAAJXZ`
- size: `1550`
- prototype: `__int64 __fastcall(RadcHelper *__hidden this)`
- caller_count: `2`
- callee_count: `19`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180050ad8`
- `0x180050d88`

## callees

- `0x18000b1d8`
- `0x18000c3d0`
- `0x18000ec54`
- `0x18000ec94`
- `0x18000ece0`
- `0x180010ba4`
- `0x180010d44`
- `0x1800115d4`
- `0x180011ae0`
- `0x18001e5d8`
- `0x180032684`
- `0x180032c88`
- `0x1800395d0`
- `0x18004a6d0`
- `0x18004d994`
- `0x18004f840`
- `0x18005026c`
- `0x1800504c4`
- `0x1800a3010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800508c2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800508c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005091c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005091c`

## string_xrefs

- `0x18005060b`: `CWorkspace::LockForUpdate failed`
- `0x18005075b`: `CConfigManager::CreateInstance failed`
- `0x1800506ac`: `ITSPlatform::CreateThread failed!`
- `0x180050705`: `spCurrentThread->StartThread Failed!`
- `0x1800507aa`: `CreateWaitEvent failed!`
- `0x180050897`: `m_spConfigManager::ConfigureWorkspace failed`
- `0x180050a49`: `Subscribe/Update failed!`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall RadcHelper::SetupWorkspace(RadcHelper *this)
{
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int Instance; // ebx
  RadcHelper *v4; // rsi
  unsigned int v5; // eax
  CWorkspace *v6; // rcx
  unsigned int v7; // eax
  int v8; // edx
  const char *v9; // rcx
  __int64 v10; // r12
  __int64 v11; // rdi
  CWorkspace *v12; // r15
  int v13; // esi
  BOOL v14; // r14d
  void *v15; // rax
  DWORD v16; // eax
  DWORD v17; // ebx
  unsigned int v18; // eax
  signed int LastError; // eax
  unsigned int v20; // eax
  unsigned int v21; // eax
  PVOID *v22; // rdx
  unsigned int v23; // eax
  __int64 v24; // rcx
  unsigned int v25; // eax
  __int64 v27; // [rsp+30h] [rbp-71h]
  int v28[2]; // [rsp+98h] [rbp-9h] BYREF
  __int64 v29; // [rsp+A0h] [rbp-1h]
  _BYTE v30[80]; // [rsp+A8h] [rbp+7h] BYREF
  char *v31; // [rsp+108h] [rbp+67h] BYREF
  _BYTE *v32; // [rsp+110h] [rbp+6Fh]

  v29 = -2;
  *((_DWORD *)this + 14) = -1;
  *(_QWORD *)v28 = 0;
  if ( !*((_QWORD *)this + 17) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Ds(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        53,
        (unsigned int)WPP_b74b712416693693af262b781bb28dc7_Traceguids,
        CurrentThreadActivityIdPrefix,
        (__int64)"m_spWorkspaceInSetup");
    }
    Instance = -2147467261;
    goto LABEL_7;
  }
  v31 = (char *)this + 88;
  CTSCriticalSection::Lock((RadcHelper *)((char *)this + 88));
  if ( *((_DWORD *)this + 26) )
  {
    Instance = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v5 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, WPP_b74b712416693693af262b781bb28dc7_Traceguids, v5);
    }
    goto LABEL_13;
  }
  v6 = (CWorkspace *)*((_QWORD *)this + 17);
  if ( *((_DWORD *)this + 10) == 2 )
  {
    Instance = CWorkspace::LockForUpdate(v6);
    if ( Instance < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_13;
      }
      v7 = RdpWppGetCurrentThreadActivityIdPrefix();
      v8 = 55;
      v9 = "CWorkspace::LockForUpdate failed";
LABEL_20:
      LODWORD(v27) = Instance;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v8,
        (unsigned int)WPP_b74b712416693693af262b781bb28dc7_Traceguids,
        v7,
        (__int64)v9,
        v27);
LABEL_13:
      CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v31);
LABEL_7:
      v4 = this;
      goto LABEL_78;
    }
  }
  else
  {
    *((_DWORD *)v6 + 66) = *((_DWORD *)this + 27) != 0;
  }
  if ( g_spWkspcPlatform )
  {
    Instance = (*(__int64 (__fastcall **)(__int64, __int64 (__fastcall *)(), __int64, int *))(*(_QWORD *)g_spWkspcPlatform
                                                                                            + 56LL))(
                 g_spWkspcPlatform,
                 DefaultCOMFriendlyThreadProc,
                 g_spWkspcPlatform,
                 v28);
    if ( Instance < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_13;
      }
      v7 = RdpWppGetCurrentThreadActivityIdPrefix();
      v8 = 56;
      v9 = "ITSPlatform::CreateThread failed!";
      goto LABEL_20;
    }
    Instance = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)v28 + 32LL))(*(_QWORD *)v28, 0);
    if ( Instance < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_13;
      }
      v7 = RdpWppGetCurrentThreadActivityIdPrefix();
      v8 = 57;
      v9 = "spCurrentThread->StartThread Failed!";
      goto LABEL_20;
    }
  }
  Instance = CConfigManager::CreateInstance((struct CConfigManager **)this + 16);
  if ( Instance < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_13;
    }
    v7 = RdpWppGetCurrentThreadActivityIdPrefix();
    v8 = 58;
    v9 = "CConfigManager::CreateInstance failed";
    goto LABEL_20;
  }
  Instance = RadcHelper::CreateWaitEvent(this);
  if ( Instance < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_13;
    }
    v7 = RdpWppGetCurrentThreadActivityIdPrefix();
    v8 = 59;
    v9 = "CreateWaitEvent failed!";
    goto LABEL_20;
  }
  v10 = *((_QWORD *)this + 16);
  v11 = *((_QWORD *)this + 6);
  v12 = (CWorkspace *)*((_QWORD *)this + 17);
  v13 = *((_DWORD *)this + 28);
  v14 = *((_DWORD *)this + 10) == 2;
  v32 = v30;
  v15 = (void *)std::wstring::wstring(v30, (char *)this + 144);
  Instance = CConfigManager::SetupWorkspace(
               v10,
               *(__int64 *)v28,
               *((_QWORD *)this + 15),
               v15,
               0,
               0,
               0,
               v14,
               v13,
               2,
               0,
               0,
               0,
               ((unsigned __int64)this + 16) & -(__int64)(this != 0),
               v12,
               0,
               v11);
  if ( Instance < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_13;
    }
    v7 = RdpWppGetCurrentThreadActivityIdPrefix();
    v8 = 60;
    v9 = "m_spConfigManager::ConfigureWorkspace failed";
    goto LABEL_20;
  }
  v4 = this;
  CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v31);
  while ( 1 )
  {
    v16 = WaitForSingleObject(*((HANDLE *)this + 4), 0x7D0u);
    v17 = v16;
    if ( !v16 )
      break;
    if ( v16 != 258 )
    {
      if ( v16 == -1 )
      {
        LastError = GetLastError();
        Instance = LastError;
        if ( LastError > 0 )
          Instance = (unsigned __int16)LastError | 0x80070000;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v20 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            63,
            WPP_b74b712416693693af262b781bb28dc7_Traceguids,
            v20,
            Instance);
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v21 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, WPP_b74b712416693693af262b781bb28dc7_Traceguids, v21, v17);
        }
        Instance = -2147467259;
      }
      goto LABEL_78;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v18 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, WPP_b74b712416693693af262b781bb28dc7_Traceguids, v18);
    }
  }
  v22 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v23 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, WPP_b74b712416693693af262b781bb28dc7_Traceguids, v23);
    v22 = (PVOID *)WPP_GLOBAL_Control;
  }
  v24 = *((unsigned int *)this + 14);
  if ( (_DWORD)v24 == 18 )
  {
    Instance = -2147467260;
  }
  else
  {
    Instance = MapXResultToHR(v24);
    if ( Instance >= 0 )
      goto LABEL_78;
  }
  if ( v22 != &WPP_GLOBAL_Control && (*((_BYTE *)v22 + 28) & 8) != 0 && *((_BYTE *)v22 + 25) >= 2u )
  {
    v25 = RdpWppGetCurrentThreadActivityIdPrefix();
    LODWORD(v27) = Instance;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      65,
      (unsigned int)WPP_b74b712416693693af262b781bb28dc7_Traceguids,
      v25,
      (__int64)"Subscribe/Update failed!",
      v27);
  }
LABEL_78:
  if ( !(unsigned int)CTSCriticalSection::IsLockedByCurrentThread((RadcHelper *)((char *)v4 + 88)) )
    CTSCriticalSection::Lock((RadcHelper *)((char *)v4 + 88));
  if ( *((_DWORD *)this + 10) == 2 )
    CWorkspace::UnlockForUpdate(*((CWorkspace **)this + 17));
  *((_DWORD *)this + 10) = 0;
  CTSCriticalSection::UnLock((RadcHelper *)((char *)v4 + 88));
  TCntPtr<ITSThread>::SafeRelease(v28);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1800504c4  mov     rax, rsp
0x1800504c7  push    rbp
0x1800504c8  push    rsi
0x1800504c9  push    rdi
0x1800504ca  push    r12
0x1800504cc  push    r13
0x1800504ce  push    r14
0x1800504d0  push    r15
0x1800504d2  lea     rbp, [rax-5Fh]
0x1800504d6  sub     rsp, 0C0h
0x1800504dd  mov     [rbp+57h+var_58], 0FFFFFFFFFFFFFFFEh
0x1800504e5  mov     [rax+18h], rbx
0x1800504e9  mov     r13, rcx
0x1800504ec  mov     dword ptr [rcx+38h], 0FFFFFFFFh
0x1800504f3  xor     r15d, r15d
0x1800504f6  mov     qword ptr [rbp+57h+var_60], r15
0x1800504fa  lea     esi, [r15+2]
0x1800504fe  cmp     [rcx+88h], r15
0x180050505  jnz     short loc_180050561
0x180050507  lea     rdi, WPP_GLOBAL_Control
0x18005050e  mov     rax, cs:WPP_GLOBAL_Control
0x180050515  cmp     rax, rdi
0x180050518  jz      short loc_180050554
0x18005051a  test    byte ptr [rax+1Ch], 8
0x18005051e  jz      short loc_180050554
0x180050520  cmp     [rax+19h], sil
0x180050524  jb      short loc_180050554
0x180050526  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18005052b  lea     edx, [rsi+33h]
0x18005052e  lea     rcx, aMSpworkspacein; "m_spWorkspaceInSetup"
0x180050535  mov     [rsp+0F0h+var_D0], rcx
0x18005053a  mov     r9d, eax
0x18005053d  lea     r8, WPP_b74b712416693693af262b781bb28dc7_Traceguids
0x180050544  mov     rcx, cs:WPP_GLOBAL_Control
0x18005054b  mov     rcx, [rcx+10h]
0x18005054f  call    WPP_SF_Ds
0x180050554  mov     ebx, 80004003h
0x180050559  mov     rsi, r13
0x18005055c  jmp     loc_180050A6F
0x180050561  add     rcx, 58h ; 'X'; this
0x180050565  mov     [rbp+57h+arg_0], rcx
0x180050569  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x18005056e  nop
0x18005056f  cmp     [r13+68h], r15d
0x180050573  jz      short loc_1800505CA
0x180050575  mov     ebx, r15d
0x180050578  lea     rdi, WPP_GLOBAL_Control
0x18005057f  mov     rax, cs:WPP_GLOBAL_Control
0x180050586  cmp     rax, rdi
0x180050589  jz      short loc_1800505BF
0x18005058b  mov     r14b, 1
0x18005058e  test    [rax+1Ch], r14b
0x180050592  jz      short loc_1800505BF
0x180050594  cmp     byte ptr [rax+19h], 4
0x180050598  jb      short loc_1800505BF
0x18005059a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18005059f  mov     edx, 36h ; '6'
0x1800505a4  mov     r9d, eax
0x1800505a7  lea     r8, WPP_b74b712416693693af262b781bb28dc7_Traceguids
0x1800505ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800505b5  mov     rcx, [rcx+10h]
0x1800505b9  call    WPP_SF_D
0x1800505be  nop
0x1800505bf  lea     rcx, [rbp+57h+arg_0]; this
0x1800505c3  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x1800505c8  jmp     short loc_180050559
0x1800505ca  mov     rcx, [r13+88h]; this
0x1800505d1  cmp     [r13+28h], esi
0x1800505d5  jnz     short loc_180050637
0x1800505d7  call    ?LockForUpdate@CWorkspace@@QEAAJXZ; CWorkspace::LockForUpdate(void)
0x1800505dc  mov     ebx, eax
0x1800505de  test    eax, eax
0x1800505e0  jns     short loc_180050647
0x1800505e2  lea     rdi, WPP_GLOBAL_Control
0x1800505e9  mov     rax, cs:WPP_GLOBAL_Control
0x1800505f0  cmp     rax, rdi
0x1800505f3  jz      short loc_1800505BF
0x1800505f5  test    byte ptr [rax+1Ch], 8
0x1800505f9  jz      short loc_1800505BF
0x1800505fb  cmp     [rax+19h], sil
0x1800505ff  jb      short loc_1800505BF
0x180050601  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180050606  mov     edx, 37h ; '7'
0x18005060b  lea     rcx, aCworkspaceLock; "CWorkspace::LockForUpdate failed"
0x180050612  mov     dword ptr [rsp+0F0h+var_C8], ebx
0x180050616  mov     [rsp+0F0h+var_D0], rcx
0x18005061b  mov     r9d, eax
0x18005061e  lea     r8, WPP_b74b712416693693af262b781bb28dc7_Traceguids
0x180050625  mov     rcx, cs:WPP_GLOBAL_Control
0x18005062c  mov     rcx, [rcx+10h]
0x180050630  call    WPP_SF_DsD
0x180050635  jmp     short loc_1800505BF
0x180050637  mov     eax, r15d
0x18005063a  cmp     [r13+6Ch], r15d
0x18005063e  setnz   al
0x180050641  mov     [rcx+108h], eax
0x180050647  mov     rcx, cs:?g_spWkspcPlatform@@3V?$ComPlainSmartPtr@VITSPlatform@@@@A; ComPlainSmartPtr<ITSPlatform> g_spWkspcPlatform
0x18005064e  test    rcx, rcx
0x180050651  jz      loc_180050711
0x180050657  mov     rax, [rcx]
0x18005065a  lea     r9, [rbp+57h+var_60]
0x18005065e  mov     r8, rcx
0x180050661  lea     rdx, DefaultCOMFriendlyThreadProc
0x180050668  mov     rax, [rax+38h]
0x18005066c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050671  mov     ebx, eax
0x180050673  test    eax, eax
0x180050675  jns     short loc_1800506B8
0x180050677  lea     rdi, WPP_GLOBAL_Control
0x18005067e  mov     rax, cs:WPP_GLOBAL_Control
0x180050685  cmp     rax, rdi
0x180050688  jz      loc_1800505BF
0x18005068e  test    byte ptr [rax+1Ch], 8
0x180050692  jz      loc_1800505BF
0x180050698  cmp     [rax+19h], sil
0x18005069c  jb      loc_1800505BF
0x1800506a2  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800506a7  mov     edx, 38h ; '8'
0x1800506ac  lea     rcx, aItsplatformCre; "ITSPlatform::CreateThread failed!"
0x1800506b3  jmp     loc_180050612
0x1800506b8  mov     rcx, qword ptr [rbp+57h+var_60]
0x1800506bc  mov     rax, [rcx]
0x1800506bf  xor     edx, edx
0x1800506c1  mov     rax, [rax+20h]
0x1800506c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800506ca  mov     ebx, eax
0x1800506cc  test    eax, eax
0x1800506ce  jns     short loc_180050711
0x1800506d0  lea     rdi, WPP_GLOBAL_Control
0x1800506d7  mov     rax, cs:WPP_GLOBAL_Control
0x1800506de  cmp     rax, rdi
0x1800506e1  jz      loc_1800505BF
0x1800506e7  test    byte ptr [rax+1Ch], 8
0x1800506eb  jz      loc_1800505BF
0x1800506f1  cmp     [rax+19h], sil
0x1800506f5  jb      loc_1800505BF
0x1800506fb  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180050700  mov     edx, 39h ; '9'
0x180050705  lea     rcx, aSpcurrentthrea; "spCurrentThread->StartThread Failed!"
0x18005070c  jmp     loc_180050612
0x180050711  lea     r12, [r13+80h]
0x180050718  mov     rcx, r12; struct CConfigManager **
0x18005071b  call    ?CreateInstance@CConfigManager@@SAJPEAPEAV1@@Z; CConfigManager::CreateInstance(CConfigManager * *)
0x180050720  mov     ebx, eax
0x180050722  test    eax, eax
0x180050724  jns     short loc_180050767
0x180050726  lea     rdi, WPP_GLOBAL_Control
0x18005072d  mov     rax, cs:WPP_GLOBAL_Control
0x180050734  cmp     rax, rdi
0x180050737  jz      loc_1800505BF
0x18005073d  test    byte ptr [rax+1Ch], 8
0x180050741  jz      loc_1800505BF
0x180050747  cmp     [rax+19h], sil
0x18005074b  jb      loc_1800505BF
0x180050751  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180050756  mov     edx, 3Ah ; ':'
0x18005075b  lea     rcx, aCconfigmanager_0; "CConfigManager::CreateInstance failed"
0x180050762  jmp     loc_180050612
0x180050767  mov     rcx, r13; this
0x18005076a  call    ?CreateWaitEvent@RadcHelper@@AEAAJXZ; RadcHelper::CreateWaitEvent(void)
0x18005076f  mov     ebx, eax
0x180050771  test    eax, eax
0x180050773  jns     short loc_1800507B6
0x180050775  lea     rdi, WPP_GLOBAL_Control
0x18005077c  mov     rax, cs:WPP_GLOBAL_Control
0x180050783  cmp     rax, rdi
0x180050786  jz      loc_1800505BF
0x18005078c  test    byte ptr [rax+1Ch], 8
0x180050790  jz      loc_1800505BF
0x180050796  cmp     [rax+19h], sil
0x18005079a  jb      loc_1800505BF
0x1800507a0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800507a5  mov     edx, 3Bh ; ';'
0x1800507aa  lea     rcx, aCreatewaiteven; "CreateWaitEvent failed!"
0x1800507b1  jmp     loc_180050612
0x1800507b6  mov     r12, [r12]
0x1800507ba  mov     rdi, [r13+30h]
0x1800507be  mov     r15, [r13+88h]
0x1800507c5  mov     rax, r13
0x1800507c8  lea     rcx, [r13+10h]
0x1800507cc  neg     rax
0x1800507cf  sbb     rbx, rbx
0x1800507d2  and     rbx, rcx
0x1800507d5  mov     esi, [r13+70h]
0x1800507d9  xor     r14d, r14d
0x1800507dc  cmp     dword ptr [r13+28h], 2
0x1800507e1  setz    r14b
0x1800507e5  lea     rax, [rbp+57h+var_50]
0x1800507e9  mov     [rbp+57h+arg_8], rax
0x1800507ed  lea     rdx, [r13+90h]
0x1800507f4  lea     rcx, [rbp+57h+var_50]
0x1800507f8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800507fd  nop
0x1800507fe  mov     r8, [r13+78h]; int
0x180050802  mov     rdx, qword ptr [rbp+57h+var_60]; int
0x180050806  mov     [rsp+80h], rdi; __int64
0x18005080e  mov     [rsp+0F0h+var_78], 0; int
0x180050816  mov     [rsp+0F0h+var_80], r15; CWorkspace *
0x18005081b  mov     [rsp+0F0h+var_88], rbx; __int64
0x180050820  xor     r15d, r15d
0x180050823  mov     [rsp+0F0h+var_90], r15d; int
0x180050828  mov     [rsp+0F0h+var_98], r15; __int64
0x18005082d  mov     [rsp+0F0h+var_A0], r15d; int
0x180050832  mov     [rsp+0F0h+var_A8], 2; int
0x18005083a  mov     [rsp+0F0h+var_B0], esi; int
0x18005083e  mov     [rsp+0F0h+var_B8], r14d; int
0x180050843  mov     [rsp+0F0h+var_C0], r15d; int
0x180050848  mov     dword ptr [rsp+0F0h+var_C8], r15d; int
0x18005084d  mov     [rsp+0F0h+var_D0], r15; __int64
0x180050852  mov     r9, rax; int
0x180050855  mov     rcx, r12; int
0x180050858  call    ?SetupWorkspace@CConfigManager@@QEAAJPEAVITSThread@@PEAUHWND__@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGJKHHKH3HPEAVITSWorkspaceResult@@PEAVCWorkspace@@HPEAVFeedDiagnostics@@@Z; CConfigManager::SetupWorkspace(ITSThread *,HWND__ *,std::wstring,ushort const *,long,ulong,int,int,ulong,int,ushort const *,int,ITSWorkspaceResult *,CWorkspace *,int,FeedDiagnostics *)
0x18005085d  mov     ebx, eax
0x18005085f  test    eax, eax
0x180050861  jns     short loc_1800508A3
0x180050863  lea     rdi, WPP_GLOBAL_Control
0x18005086a  mov     rax, cs:WPP_GLOBAL_Control
0x180050871  cmp     rax, rdi
0x180050874  jz      loc_1800505BF
0x18005087a  test    byte ptr [rax+1Ch], 8
0x18005087e  jz      loc_1800505BF
0x180050884  cmp     byte ptr [rax+19h], 2
0x180050888  jb      loc_1800505BF
0x18005088e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180050893  lea     edx, [r15+3Ch]
0x180050897  lea     rcx, aMSpconfigmanag; "m_spConfigManager::ConfigureWorkspace f"...
0x18005089e  jmp     loc_180050612
0x1800508a3  mov     rsi, r13
0x1800508a6  lea     rcx, [rbp+57h+arg_0]; this
0x1800508aa  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x1800508af  lea     rdi, WPP_GLOBAL_Control
0x1800508b6  mov     r14b, 1
0x1800508b9  mov     edx, 7D0h; dwMilliseconds
0x1800508be  mov     rcx, [r13+20h]; hHandle
0x1800508c2  call    cs:__imp_WaitForSingleObject
0x1800508c8  mov     ebx, eax
0x1800508ca  test    eax, eax
0x1800508cc  jz      loc_1800509CC
0x1800508d2  cmp     eax, 102h
0x1800508d7  jnz     short loc_180050917
0x1800508d9  mov     rax, cs:WPP_GLOBAL_Control
0x1800508e0  cmp     rax, rdi
0x1800508e3  jz      short loc_1800508B9
0x1800508e5  test    [rax+1Ch], r14b
0x1800508e9  jz      short loc_1800508B9
0x1800508eb  cmp     byte ptr [rax+19h], 4
0x1800508ef  jb      short loc_1800508B9
0x1800508f1  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800508f6  mov     edx, 3Eh ; '>'
0x1800508fb  mov     r9d, eax
0x1800508fe  lea     r8, WPP_b74b712416693693af262b781bb28dc7_Traceguids
0x180050905  mov     rcx, cs:WPP_GLOBAL_Control
0x18005090c  mov     rcx, [rcx+10h]
0x180050910  call    WPP_SF_D
0x180050915  jmp     short loc_1800508B9
0x180050917  cmp     ebx, 0FFFFFFFFh
0x18005091a  jnz     short loc_180050982
0x18005091c  call    cs:__imp_GetLastError
0x180050922  mov     ebx, eax
0x180050924  test    eax, eax
0x180050926  jle     short loc_180050931
0x180050928  movzx   ebx, ax
0x18005092b  or      ebx, 80070000h
0x180050931  mov     rax, cs:WPP_GLOBAL_Control
0x180050938  cmp     rax, rdi
0x18005093b  jz      loc_180050A6F
0x180050941  test    [rax+1Ch], r14b
0x180050945  jz      loc_180050A6F
0x18005094b  cmp     byte ptr [rax+19h], 2
0x18005094f  jb      loc_180050A6F
0x180050955  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18005095a  mov     edx, 3Fh ; '?'
0x18005095f  mov     dword ptr [rsp+0F0h+var_D0], ebx
0x180050963  mov     r9d, eax
0x180050966  lea     r8, WPP_b74b712416693693af262b781bb28dc7_Traceguids
0x18005096d  mov     rcx, cs:WPP_GLOBAL_Control
0x180050974  mov     rcx, [rcx+10h]
0x180050978  call    WPP_SF_Dd
0x18005097d  jmp     loc_180050A6F
0x180050982  mov     rax, cs:WPP_GLOBAL_Control
0x180050989  cmp     rax, rdi
0x18005098c  jz      short loc_1800509C2
0x18005098e  test    [rax+1Ch], r14b
0x180050992  jz      short loc_1800509C2
0x180050994  cmp     byte ptr [rax+19h], 2
0x180050998  jb      short loc_1800509C2
0x18005099a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18005099f  mov     edx, 40h ; '@'
0x1800509a4  mov     dword ptr [rsp+0F0h+var_D0], ebx
0x1800509a8  mov     r9d, eax
0x1800509ab  lea     r8, WPP_b74b712416693693af262b781bb28dc7_Traceguids
0x1800509b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800509b9  mov     rcx, [rcx+10h]
0x1800509bd  call    WPP_SF_Dd
0x1800509c2  mov     ebx, 80004005h
0x1800509c7  jmp     loc_180050A6F
0x1800509cc  mov     rdx, cs:WPP_GLOBAL_Control
0x1800509d3  cmp     rdx, rdi
0x1800509d6  jz      short loc_180050A0F
0x1800509d8  test    [rdx+1Ch], r14b
  ... truncated ...
```
