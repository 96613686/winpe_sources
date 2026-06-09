# SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton::GetPITRManager(void)

- ea: `0x180025c88`
- end: `0x180025eb3`
- name: `?GetPITRManager@CPointInTimeRestoreStateSingleton@PointInTimeRestore@SystemSettings@@QEAA?AV?$shared_ptr@VPointInTimeRestoreManager@PointInTimeRestore@SystemSettings@@@std@@XZ`
- size: `555`
- prototype: `_QWORD *__fastcall(volatile signed __int32 **this, _QWORD *)`
- caller_count: `4`
- callee_count: `8`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x180014070`
- `0x180014820`
- `0x180014bd0`
- `0x180024974`

## callees

- `0x180002890`
- `0x18000bef4`
- `0x1800240b8`
- `0x180025c88`
- `0x1800261f0`
- `0x1800265b4`
- `0x180028898`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180025d32`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180025d32`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180025e7d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180025e92`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180025e7d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180025e92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025dcf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025dcf`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180025cd7`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180025cd7`
- `WDSCORE!WdsSetupLogMessageW` at `0x180025e3a`
- `WDSCORE!WdsSetupLogMessageW` at `0x180025e3a`
- `WDSCORE!CurrentIP` at `0x180025dd7`
- `WDSCORE!CurrentIP` at `0x180025dd7`

## string_xrefs

- `0x180025de0`: `SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton::GetPITRManager: Successfully created PITR manager`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton::GetPITRManager(
        volatile signed __int32 **this,
        _QWORD *a2)
{
  _QWORD *v2; // r14
  int v4; // eax
  __int64 v5; // rax
  SystemSettings::PointInTimeRestore::PointInTimeRestoreManager *v6; // rcx
  volatile signed __int32 *v7; // rbx
  DWORD LastError; // edi
  __int64 v9; // rbx
  struct tagLOG_PARTIAL_MSG *v10; // rax
  volatile signed __int32 *v11; // rax
  volatile signed __int32 *v13; // rbx
  volatile signed __int32 *v14; // rbx
  void *v15; // [rsp+68h] [rbp-40h]
  wil::ResultException *v16; // [rsp+70h] [rbp-38h] BYREF
  PSRWLOCK SRWLock; // [rsp+C0h] [rbp+18h] BYREF
  char *v20; // [rsp+C8h] [rbp+20h] BYREF

  v2 = a2;
  LODWORD(v20) = 0;
  v4 = LUAIsUserUACAdmin(&v20) | 0x10000000;
  if ( v4 < 0 )
    goto LABEL_5;
  LODWORD(SRWLock) = -1;
  RtlGetDeviceFamilyInfoEnum(0, &SRWLock, 0);
  if ( (_DWORD)SRWLock != 16 && !(_DWORD)v20 )
  {
    v4 = -2147024891;
LABEL_5:
    SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton::SetLastPITRError(
      (SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton *)this,
      v4);
LABEL_6:
    *v2 = 0;
    v2[1] = 0;
    return v2;
  }
  if ( *((_BYTE *)this + 256) )
    goto LABEL_6;
  SRWLock = (PSRWLOCK)(this + 29);
  AcquireSRWLockExclusive((PSRWLOCK)this + 29);
  try
  {
    v20 = (char *)(this + 29);
    if ( !this[30] && !*((_BYTE *)this + 256) )
    {
      v15 = operator new(0x20u);
      v5 = std::_Ref_count_obj2<SystemSettings::PointInTimeRestore::PointInTimeRestoreManager>::_Ref_count_obj2<SystemSettings::PointInTimeRestore::PointInTimeRestoreManager>((__int64)v15);
      v6 = (SystemSettings::PointInTimeRestore::PointInTimeRestoreManager *)(v5 + 16);
      this[30] = (volatile signed __int32 *)(v5 + 16);
      v7 = this[31];
      this[31] = (volatile signed __int32 *)v5;
      if ( v7 )
      {
        if ( _InterlockedExchangeAdd(v7 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v7)(v7);
          if ( _InterlockedExchangeAdd(v7 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
        }
      }
      SystemSettings::PointInTimeRestore::PointInTimeRestoreManager::InitializeLogging(v6);
      LastError = GetLastError();
      v9 = CurrentIP();
      v10 = ConstructPartialMsgW(
              0x4000000u,
              "SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton::GetPITRManager: Successfully created PITR manager");
      WdsSetupLogMessageW(
        v10,
        0,
        L"D",
        0,
        205,
        L"pcshell\\shell\\systemsettings\\recoveryhandlers\\lib\\cpointintimerestorestatesingleton.cpp",
        L"SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton::GetPITRManager",
        v9,
        LastError,
        0,
        0);
    }
    *v2 = 0;
    v2[1] = 0;
    v11 = this[31];
    if ( v11 )
      _InterlockedIncrement(v11 + 2);
    *v2 = this[30];
    v2[1] = this[31];
    if ( this != (volatile signed __int32 **)-232LL )
      ReleaseSRWLockExclusive((PSRWLOCK)this + 29);
  }
  catch ( std::bad_alloc )
  {
    *a2 = 0;
    a2[1] = 0;
LABEL_20:
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    return a2;
  }
  catch ( wil::ResultException *v16 )
  {
    if ( *((_DWORD *)v16 + 8) == -2147023673 )
      *((_BYTE *)this + 256) = 1;
    this[30] = 0;
    v14 = this[31];
    this[31] = 0;
    if ( v14 )
    {
      if ( _InterlockedExchangeAdd(v14 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v14)(v14);
        if ( _InterlockedExchangeAdd(v14 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 8LL))(v14);
      }
    }
    *a2 = 0;
    a2[1] = 0;
    goto LABEL_20;
  }
  catch ( ... )
  {
    this[30] = 0;
    v13 = this[31];
    this[31] = 0;
    if ( v13 )
    {
      if ( _InterlockedExchangeAdd(v13 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v13)(v13);
        if ( _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
      }
    }
    *a2 = 0;
    a2[1] = 0;
    goto LABEL_20;
  }
  return v2;
}

```

## disassembly

```asm
0x180025c88  mov     rax, rsp
0x180025c8b  mov     [rax+10h], rdx
0x180025c8f  mov     [rax+8], rcx
0x180025c93  push    rbx
0x180025c94  push    rdi
0x180025c95  push    r12
0x180025c97  push    r14
0x180025c99  push    r15
0x180025c9b  sub     rsp, 80h
0x180025ca2  mov     r14, rdx
0x180025ca5  mov     r15, rcx
0x180025ca8  mov     dword ptr [rax+20h], 0
0x180025caf  lea     rcx, [rax+20h]
0x180025cb3  call    LUAIsUserUACAdmin
0x180025cb8  or      eax, 10000000h
0x180025cbd  jl      short loc_180025CF6
0x180025cbf  mov     dword ptr [rsp+0A8h+SRWLock], 0FFFFFFFFh
0x180025cca  xor     r8d, r8d
0x180025ccd  lea     rdx, [rsp+0A8h+SRWLock]
0x180025cd5  xor     ecx, ecx
0x180025cd7  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x180025cdd  cmp     dword ptr [rsp+0A8h+SRWLock], 10h
0x180025ce5  jz      short loc_180025D14
0x180025ce7  cmp     dword ptr [rsp+0A8h+arg_18], 0
0x180025cef  jnz     short loc_180025D14
0x180025cf1  mov     eax, 80070005h
0x180025cf6  mov     edx, eax; int
0x180025cf8  mov     rcx, r15; this
0x180025cfb  call    ?SetLastPITRError@CPointInTimeRestoreStateSingleton@PointInTimeRestore@SystemSettings@@QEAAXJ@Z; SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton::SetLastPITRError(long)
0x180025d00  mov     qword ptr [r14], 0
0x180025d07  mov     qword ptr [r14+8], 0
0x180025d0f  jmp     loc_180025EA0
0x180025d14  mov     al, [r15+100h]
0x180025d1b  nop
0x180025d1c  test    al, al
0x180025d1e  jnz     short loc_180025D00
0x180025d20  lea     r12, [r15+0E8h]
0x180025d27  mov     [rsp+0A8h+SRWLock], r12
0x180025d2f  mov     rcx, r12; SRWLock
0x180025d32  call    cs:__imp_AcquireSRWLockExclusive
0x180025d38  mov     [rsp+0A8h+arg_18], r12
0x180025d40  cmp     qword ptr [r15+0F0h], 0
0x180025d48  jnz     loc_180025E41
0x180025d4e  mov     al, [r15+100h]
0x180025d55  nop
0x180025d56  test    al, al
0x180025d58  jnz     loc_180025E41
0x180025d5e  mov     ecx, 20h ; ' '; Size
0x180025d63  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180025d68  mov     [rsp+0A8h+var_40], rax
0x180025d6d  mov     rcx, rax
0x180025d70  call    ??$?0$$V@?$_Ref_count_obj2@VPointInTimeRestoreManager@PointInTimeRestore@SystemSettings@@@std@@QEAA@XZ; std::_Ref_count_obj2<SystemSettings::PointInTimeRestore::PointInTimeRestoreManager>::_Ref_count_obj2<SystemSettings::PointInTimeRestore::PointInTimeRestoreManager>(void)
0x180025d75  nop
0x180025d76  lea     rcx, [rax+10h]
0x180025d7a  mov     [r15+0F0h], rcx
0x180025d81  mov     rbx, [r15+0F8h]
0x180025d88  mov     [r15+0F8h], rax
0x180025d8f  test    rbx, rbx
0x180025d92  jz      short loc_180025DCA
0x180025d94  or      edi, 0FFFFFFFFh
0x180025d97  mov     eax, edi
0x180025d99  lock xadd [rbx+8], eax
0x180025d9e  add     eax, edi
0x180025da0  jnz     short loc_180025DCA
0x180025da2  mov     rax, [rbx]
0x180025da5  mov     rcx, rbx
0x180025da8  mov     rax, [rax]
0x180025dab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025db0  mov     eax, edi
0x180025db2  lock xadd [rbx+0Ch], eax
0x180025db7  add     eax, edi
0x180025db9  jnz     short loc_180025DCA
0x180025dbb  mov     rax, [rbx]
0x180025dbe  mov     rcx, rbx
0x180025dc1  mov     rax, [rax+8]
0x180025dc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025dca  call    ?InitializeLogging@PointInTimeRestoreManager@PointInTimeRestore@SystemSettings@@QEAAXXZ; SystemSettings::PointInTimeRestore::PointInTimeRestoreManager::InitializeLogging(void)
0x180025dcf  call    cs:__imp_GetLastError
0x180025dd5  mov     edi, eax
0x180025dd7  call    cs:__imp_CurrentIP
0x180025ddd  mov     rbx, rax
0x180025de0  lea     rdx, aSystemsettings_2; "SystemSettings::PointInTimeRestore::CPo"...
0x180025de7  mov     ecx, 4000000h; unsigned int
0x180025dec  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180025df1  mov     [rsp+0A8h+var_58], 0
0x180025df9  mov     [rsp+0A8h+var_60], 0
0x180025e02  mov     [rsp+0A8h+var_68], edi
0x180025e06  mov     [rsp+0A8h+var_70], rbx
0x180025e0b  lea     rcx, aSystemsettings_113; "SystemSettings::PointInTimeRestore::CPo"...
0x180025e12  mov     [rsp+0A8h+var_78], rcx
0x180025e17  lea     rcx, aPcshellShellSy_4; "pcshell\\shell\\systemsettings\\recover"...
0x180025e1e  mov     [rsp+0A8h+var_80], rcx
0x180025e23  mov     [rsp+0A8h+var_88], 0CDh
0x180025e2b  xor     r9d, r9d
0x180025e2e  lea     r8, aD; "D"
0x180025e35  xor     edx, edx
0x180025e37  mov     rcx, rax
0x180025e3a  call    cs:__imp_WdsSetupLogMessageW
0x180025e40  nop
0x180025e41  mov     qword ptr [r14], 0
0x180025e48  mov     qword ptr [r14+8], 0
0x180025e50  mov     rax, [r15+0F8h]
0x180025e57  test    rax, rax
0x180025e5a  jz      short loc_180025E60
0x180025e5c  lock inc dword ptr [rax+8]
0x180025e60  mov     rax, [r15+0F0h]
0x180025e67  mov     [r14], rax
0x180025e6a  mov     rax, [r15+0F8h]
0x180025e71  mov     [r14+8], rax
0x180025e75  test    r12, r12
0x180025e78  jz      short loc_180025EA0
0x180025e7a  mov     rcx, r12; SRWLock
0x180025e7d  call    cs:__imp_ReleaseSRWLockExclusive
0x180025e83  jmp     short loc_180025EA0
0x180025e85  mov     rcx, [rsp+0A8h+SRWLock]; SRWLock
0x180025e8d  test    rcx, rcx
0x180025e90  jz      short loc_180025E98
0x180025e92  call    cs:__imp_ReleaseSRWLockExclusive
0x180025e98  mov     r14, [rsp+0A8h+arg_8]
0x180025ea0  mov     rax, r14
0x180025ea3  add     rsp, 80h
0x180025eaa  pop     r15
0x180025eac  pop     r14
0x180025eae  pop     r12
0x180025eb0  pop     rdi
0x180025eb1  pop     rbx
0x180025eb2  retn
```
