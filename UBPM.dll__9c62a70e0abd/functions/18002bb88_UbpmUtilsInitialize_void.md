# UbpmUtilsInitialize(void)

- ea: `0x18002bb88`
- end: `0x18002c054`
- name: `?UbpmUtilsInitialize@@YAKXZ`
- size: `1228`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002c420`

## callees

- `0x18000fbf0`
- `0x1800150c0`
- `0x18002bb88`
- `0x18002deb0`
- `0x180030390`
- `0x1800351ec`
- `0x180036484`
- `0x18003819c`
- `0x18004022e`
- `0x180040260`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18002bcff`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18002bd55`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18002bcff`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18002bd55`
- `ntdll!RtlInitializeSRWLock` at `0x18002be41`
- `ntdll!RtlInitializeSRWLock` at `0x18002be41`
- `ntdll!NtPowerInformation` at `0x18002be1f`
- `ntdll!NtPowerInformation` at `0x18002be1f`
- `ntdll!RtlNtStatusToDosError` at `0x18002bc85`
- `ntdll!RtlNtStatusToDosError` at `0x18002bc85`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002bbed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002bbed`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002bc0c`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002bc0c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18002bf22`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18002bf22`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x18002bf78`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x18002bf78`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x18002be4f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x18002be4f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x18002bee0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x18002bee0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bc1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bd13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bd65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002be67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bef0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bf3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bc1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bd13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bd65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002be67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bef0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bf3a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c013`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c013`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupOpenLocalPolicy` at `0x18002bc73`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupOpenLocalPolicy` at `0x18002bc73`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupGetDomainInfo` at `0x18002bca4`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupGetDomainInfo` at `0x18002bca4`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupClose` at `0x18002c028`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupClose` at `0x18002c028`

## pseudocode

```c
__int64 UbpmUtilsInitialize(void)
{
  HANDLE CurrentProcess; // rax
  DWORD LastError; // eax
  unsigned int CriticalActionsGuids; // ebx
  _QWORD *v3; // rcx
  __int64 v4; // rdx
  int v5; // eax
  ULONG v6; // eax
  unsigned int i; // r14d
  WELL_KNOWN_SID_TYPE v8; // ecx
  void *v9; // r12
  void *v10; // r15
  void *v11; // rax
  DWORD v12; // eax
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // r9
  struct _TP_POOL *Threadpool; // rax
  DWORD cbSid; // [rsp+30h] [rbp-89h] BYREF
  PVOID DomainInfo; // [rsp+38h] [rbp-81h] BYREF
  PVOID PolicyHandle; // [rsp+40h] [rbp-79h] BYREF
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+48h] [rbp-71h] BYREF
  _BYTE OutputBuffer[80]; // [rsp+80h] [rbp-39h] BYREF

  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  memset_0(OutputBuffer, 0, 0x4Cu);
  PolicyHandle = 0;
  DomainInfo = 0;
  cbSid = 0;
  if ( g_Globals || (CurrentProcess = GetCurrentProcess(), OpenProcessToken(CurrentProcess, 0xAu, &g_Globals)) )
  {
    v5 = LsaLookupOpenLocalPolicy(&ObjectAttributes, 1u, &PolicyHandle);
    if ( v5 < 0 || (v5 = LsaLookupGetDomainInfo(PolicyHandle, AccountDomainInformation, &DomainInfo), v5 < 0) )
    {
      v6 = RtlNtStatusToDosError(v5);
LABEL_49:
      CriticalActionsGuids = v6;
    }
    else
    {
      for ( i = 0; i < 5; ++i )
      {
        if ( !**((_QWORD **)&g_SidData.Revision + 2 * (int)i) )
        {
          v8 = g_SidData.SubAuthority[4 * i];
          v9 = 0;
          if ( v8 == (WinLocalAccountAndAdministratorSid|WinCreatorGroupSid) )
            v9 = (void *)*((_QWORD *)DomainInfo + 2);
          v10 = 0;
          if ( !CreateWellKnownSid(v8, v9, 0, &cbSid) )
          {
            LastError = GetLastError();
            CriticalActionsGuids = LastError;
            if ( LastError != 122 )
            {
              v3 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v4 = 11;
                goto LABEL_6;
              }
              goto LABEL_50;
            }
            v11 = UbpmAlloc(cbSid);
            v10 = v11;
            if ( !v11 )
            {
              CriticalActionsGuids = 14;
              goto LABEL_50;
            }
            if ( !CreateWellKnownSid((WELL_KNOWN_SID_TYPE)g_SidData.SubAuthority[4 * i], v9, v11, &cbSid) )
            {
              v12 = GetLastError();
              CriticalActionsGuids = v12;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_53cebd00d02b39c67ce9f6460dbe4812_Traceguids, v12);
              UBPM_MIDL_user_free(v10, v13, v14, v15);
              goto LABEL_50;
            }
          }
          **((_QWORD **)&g_SidData.Revision + 2 * (int)i) = v10;
          cbSid = 0;
        }
      }
      if ( NtPowerInformation(SystemPowerCapabilities, 0, 0, OutputBuffer, 0x4Cu) >= 0 )
        g_pCriticalActions.Data4[0] = OutputBuffer[20] != 0;
      RtlInitializeSRWLock(&g_TpSubmitLock);
      Threadpool = CreateThreadpool(0);
      g_pThreadpool = Threadpool;
      if ( Threadpool )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_53cebd00d02b39c67ce9f6460dbe4812_Traceguids, Threadpool);
          Threadpool = g_pThreadpool;
        }
        if ( SetThreadpoolThreadMinimum(Threadpool, 1u) )
        {
          g_pCleanupGroup = CreateThreadpoolCleanupGroup();
          if ( g_pCleanupGroup )
          {
            SetThreadpoolThreadMaximum(g_pThreadpool, 0x3E8u);
            g_CallbackEnv.Pool = g_pThreadpool;
            g_CallbackEnv.CleanupGroup = g_pCleanupGroup;
            g_CallbackEnv.CleanupGroupCancelCallback = (PTP_CLEANUP_GROUP_CANCEL_CALLBACK)UbpmUtilsThreadPoolCancelCallback;
            g_CallbackEnv.Version = 3;
            *(_OWORD *)&g_CallbackEnv.RaceDll = 0;
            g_CallbackEnv.FinalizationCallback = 0;
            g_CallbackEnv.u.Flags = 0;
            g_CallbackEnv.CallbackPriority = TP_CALLBACK_PRIORITY_NORMAL;
            g_CallbackEnv.Size = 72;
            CriticalActionsGuids = UbpmpGetCriticalActionsGuids();
            if ( !CriticalActionsGuids )
            {
              CriticalActionsGuids = UbpmInitializeMaintenance();
              if ( !CriticalActionsGuids )
              {
                v6 = UbpmSystemInterfaceStart();
                goto LABEL_49;
              }
            }
          }
          else
          {
            LastError = GetLastError();
            CriticalActionsGuids = LastError;
            v3 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v4 = 16;
              goto LABEL_6;
            }
          }
        }
        else
        {
          LastError = GetLastError();
          CriticalActionsGuids = LastError;
          v3 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v4 = 15;
            goto LABEL_6;
          }
        }
      }
      else
      {
        LastError = GetLastError();
        CriticalActionsGuids = LastError;
        v3 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v4 = 13;
          goto LABEL_6;
        }
      }
    }
  }
  else
  {
    LastError = GetLastError();
    CriticalActionsGuids = LastError;
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v4 = 10;
LABEL_6:
      WPP_SF_d(v3[2], v4, WPP_53cebd00d02b39c67ce9f6460dbe4812_Traceguids, LastError);
    }
  }
LABEL_50:
  if ( DomainInfo )
    LocalFree(DomainInfo);
  if ( PolicyHandle )
    LsaLookupClose(PolicyHandle);
  return CriticalActionsGuids;
}

```

## disassembly

```asm
0x18002bb88  push    rbp
0x18002bb8a  push    rbx
0x18002bb8b  push    rdi
0x18002bb8c  push    r12
0x18002bb8e  push    r14
0x18002bb90  push    r15
0x18002bb92  lea     rbp, [rsp-2Fh]
0x18002bb97  sub     rsp, 0E8h
0x18002bb9e  mov     rax, cs:__security_cookie
0x18002bba5  xor     rax, rsp
0x18002bba8  mov     [rbp+57h+var_40], rax
0x18002bbac  xorps   xmm0, xmm0
0x18002bbaf  lea     rcx, [rbp+57h+OutputBuffer]; void *
0x18002bbb3  xor     edx, edx; Val
0x18002bbb5  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18002bbb9  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18002bbbd  lea     r8d, [rdx+4Ch]; Size
0x18002bbc1  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18002bbc5  call    memset_0
0x18002bbca  cmp     cs:?g_Globals@@3U_UBPM_GLOBAL_DATA@@A, 0; _UBPM_GLOBAL_DATA g_Globals
0x18002bbd2  mov     [rbp+57h+PolicyHandle], 0
0x18002bbda  mov     [rsp+110h+DomainInfo], 0
0x18002bbe3  mov     [rsp+110h+cbSid], 0
0x18002bbeb  jnz     short loc_18002BC66
0x18002bbed  call    cs:__imp_GetCurrentProcess
0x18002bbf4  nop     dword ptr [rax+rax+00h]
0x18002bbf9  mov     r14d, 0Ah
0x18002bbff  lea     r8, ?g_Globals@@3U_UBPM_GLOBAL_DATA@@A; TokenHandle
0x18002bc06  mov     rcx, rax; ProcessHandle
0x18002bc09  mov     edx, r14d; DesiredAccess
0x18002bc0c  call    cs:__imp_OpenProcessToken
0x18002bc13  nop     dword ptr [rax+rax+00h]
0x18002bc18  test    eax, eax
0x18002bc1a  jnz     short loc_18002BC66
0x18002bc1c  call    cs:__imp_GetLastError
0x18002bc23  nop     dword ptr [rax+rax+00h]
0x18002bc28  mov     ebx, eax
0x18002bc2a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bc31  lea     rdi, WPP_GLOBAL_Control
0x18002bc38  cmp     rcx, rdi
0x18002bc3b  jz      loc_18002C009
0x18002bc41  test    byte ptr [rcx+1Ch], 1
0x18002bc45  jz      loc_18002C009
0x18002bc4b  mov     edx, r14d
0x18002bc4e  mov     rcx, [rcx+10h]
0x18002bc52  lea     r8, WPP_53cebd00d02b39c67ce9f6460dbe4812_Traceguids
0x18002bc59  mov     r9d, eax
0x18002bc5c  call    WPP_SF_d
0x18002bc61  jmp     loc_18002C009
0x18002bc66  lea     r8, [rbp+57h+PolicyHandle]; PolicyHandle
0x18002bc6a  mov     edx, 1; AccessMask
0x18002bc6f  lea     rcx, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18002bc73  call    cs:__imp_LsaLookupOpenLocalPolicy
0x18002bc7a  nop     dword ptr [rax+rax+00h]
0x18002bc7f  test    eax, eax
0x18002bc81  jns     short loc_18002BC96
0x18002bc83  mov     ecx, eax; Status
0x18002bc85  call    cs:__imp_RtlNtStatusToDosError
0x18002bc8c  nop     dword ptr [rax+rax+00h]
0x18002bc91  jmp     loc_18002C007
0x18002bc96  mov     rcx, [rbp+57h+PolicyHandle]; PolicyHandle
0x18002bc9a  lea     r8, [rsp+110h+DomainInfo]; DomainInfo
0x18002bc9f  mov     edx, 5; DomainInfoClass
0x18002bca4  call    cs:__imp_LsaLookupGetDomainInfo
0x18002bcab  nop     dword ptr [rax+rax+00h]
0x18002bcb0  test    eax, eax
0x18002bcb2  js      short loc_18002BC83
0x18002bcb4  xor     r14d, r14d
0x18002bcb7  lea     rcx, ?g_SidData@@3PAU_SID_DATA@@A; _SID_DATA near * g_SidData
0x18002bcbe  cmp     r14d, 5
0x18002bcc2  jnb     loc_18002BE0B
0x18002bcc8  movsxd  rdi, r14d
0x18002bccb  add     rdi, rdi
0x18002bcce  mov     rax, [rcx+rdi*8]
0x18002bcd2  cmp     qword ptr [rax], 0
0x18002bcd6  jnz     loc_18002BDCE
0x18002bcdc  mov     ecx, [rcx+rdi*8+8]; WellKnownSidType
0x18002bce0  xor     r12d, r12d
0x18002bce3  cmp     ecx, 6Eh ; 'n'
0x18002bce6  jnz     short loc_18002BCF1
0x18002bce8  mov     rax, [rsp+110h+DomainInfo]
0x18002bced  mov     r12, [rax+10h]
0x18002bcf1  lea     r9, [rsp+110h+cbSid]; cbSid
0x18002bcf6  xor     r8d, r8d; pSid
0x18002bcf9  mov     rdx, r12; DomainSid
0x18002bcfc  xor     r15d, r15d
0x18002bcff  call    cs:__imp_CreateWellKnownSid
0x18002bd06  nop     dword ptr [rax+rax+00h]
0x18002bd0b  test    eax, eax
0x18002bd0d  jnz     loc_18002BDB1
0x18002bd13  call    cs:__imp_GetLastError
0x18002bd1a  nop     dword ptr [rax+rax+00h]
0x18002bd1f  mov     ebx, eax
0x18002bd21  cmp     eax, 7Ah ; 'z'
0x18002bd24  jnz     loc_18002BDE0
0x18002bd2a  mov     ecx, [rsp+110h+cbSid]; Size
0x18002bd2e  call    ?UbpmAlloc@@YAPEAXK@Z; UbpmAlloc(ulong)
0x18002bd33  mov     r15, rax
0x18002bd36  test    rax, rax
0x18002bd39  jz      loc_18002BDD6
0x18002bd3f  lea     rbx, ?g_SidData@@3PAU_SID_DATA@@A; _SID_DATA near * g_SidData
0x18002bd46  mov     r8, rax; pSid
0x18002bd49  mov     ecx, [rbx+rdi*8+8]; WellKnownSidType
0x18002bd4d  lea     r9, [rsp+110h+cbSid]; cbSid
0x18002bd52  mov     rdx, r12; DomainSid
0x18002bd55  call    cs:__imp_CreateWellKnownSid
0x18002bd5c  nop     dword ptr [rax+rax+00h]
0x18002bd61  test    eax, eax
0x18002bd63  jnz     short loc_18002BDB8
0x18002bd65  call    cs:__imp_GetLastError
0x18002bd6c  nop     dword ptr [rax+rax+00h]
0x18002bd71  mov     ebx, eax
0x18002bd73  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bd7a  lea     rdi, WPP_GLOBAL_Control
0x18002bd81  cmp     rcx, rdi
0x18002bd84  jz      short loc_18002BDA4
0x18002bd86  test    byte ptr [rcx+1Ch], 1
0x18002bd8a  jz      short loc_18002BDA4
0x18002bd8c  mov     rcx, [rcx+10h]
0x18002bd90  lea     r8, WPP_53cebd00d02b39c67ce9f6460dbe4812_Traceguids
0x18002bd97  mov     edx, 0Ch
0x18002bd9c  mov     r9d, eax
0x18002bd9f  call    WPP_SF_d
0x18002bda4  mov     rcx, r15
0x18002bda7  call    UBPM_MIDL_user_free
0x18002bdac  jmp     loc_18002C009
0x18002bdb1  lea     rbx, ?g_SidData@@3PAU_SID_DATA@@A; _SID_DATA near * g_SidData
0x18002bdb8  mov     rcx, [rbx+rdi*8]
0x18002bdbc  mov     [rcx], r15
0x18002bdbf  lea     rcx, ?g_SidData@@3PAU_SID_DATA@@A; _SID_DATA near * g_SidData
0x18002bdc6  mov     [rsp+110h+cbSid], 0
0x18002bdce  inc     r14d
0x18002bdd1  jmp     loc_18002BCBE
0x18002bdd6  mov     ebx, 0Eh
0x18002bddb  jmp     loc_18002C009
0x18002bde0  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bde7  lea     rdi, WPP_GLOBAL_Control
0x18002bdee  cmp     rcx, rdi
0x18002bdf1  jz      loc_18002C009
0x18002bdf7  test    byte ptr [rcx+1Ch], 1
0x18002bdfb  jz      loc_18002C009
0x18002be01  mov     edx, 0Bh
0x18002be06  jmp     loc_18002BC4E
0x18002be0b  xor     edx, edx; InputBuffer
0x18002be0d  mov     [rsp+110h+OutputBufferLength], 4Ch ; 'L'; OutputBufferLength
0x18002be15  lea     r9, [rbp+57h+OutputBuffer]; OutputBuffer
0x18002be19  xor     r8d, r8d; InputBufferLength
0x18002be1c  lea     ecx, [rdx+4]; PowerInformationLevel
0x18002be1f  call    cs:__imp_NtPowerInformation
0x18002be26  nop     dword ptr [rax+rax+00h]
0x18002be2b  test    eax, eax
0x18002be2d  js      short loc_18002BE3A
0x18002be2f  cmp     [rbp+57h+var_7C], 0
0x18002be33  setnz   cs:?g_pCriticalActions@@3PEAU_GUID@@EA.Data4; _GUID * g_pCriticalActions ...
0x18002be3a  lea     rcx, ?g_TpSubmitLock@@3U_UBPM_SRWLOCK@@A; _UBPM_SRWLOCK g_TpSubmitLock
0x18002be41  call    cs:__imp_RtlInitializeSRWLock
0x18002be48  nop     dword ptr [rax+rax+00h]
0x18002be4d  xor     ecx, ecx; reserved
0x18002be4f  call    cs:__imp_CreateThreadpool
0x18002be56  nop     dword ptr [rax+rax+00h]
0x18002be5b  mov     cs:?g_pThreadpool@@3PEAU_TP_POOL@@EA, rax; _TP_POOL * g_pThreadpool
0x18002be62  test    rax, rax
0x18002be65  jnz     short loc_18002BEA0
0x18002be67  call    cs:__imp_GetLastError
0x18002be6e  nop     dword ptr [rax+rax+00h]
0x18002be73  mov     ebx, eax
0x18002be75  mov     rcx, cs:WPP_GLOBAL_Control
0x18002be7c  lea     rdi, WPP_GLOBAL_Control
0x18002be83  cmp     rcx, rdi
0x18002be86  jz      loc_18002C009
0x18002be8c  test    byte ptr [rcx+1Ch], 1
0x18002be90  jz      loc_18002C009
0x18002be96  mov     edx, 0Dh
0x18002be9b  jmp     loc_18002BC4E
0x18002bea0  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bea7  lea     rdi, WPP_GLOBAL_Control
0x18002beae  cmp     rcx, rdi
0x18002beb1  jz      short loc_18002BED8
0x18002beb3  test    byte ptr [rcx+1Ch], 4
0x18002beb7  jz      short loc_18002BED8
0x18002beb9  mov     rcx, [rcx+10h]
0x18002bebd  lea     r8, WPP_53cebd00d02b39c67ce9f6460dbe4812_Traceguids
0x18002bec4  mov     edx, 0Eh
0x18002bec9  mov     r9, rax
0x18002becc  call    WPP_SF_q
0x18002bed1  mov     rax, cs:?g_pThreadpool@@3PEAU_TP_POOL@@EA; _TP_POOL * g_pThreadpool
0x18002bed8  mov     edx, 1; cthrdMic
0x18002bedd  mov     rcx, rax; ptpp
0x18002bee0  call    cs:__imp_SetThreadpoolThreadMinimum
0x18002bee7  nop     dword ptr [rax+rax+00h]
0x18002beec  test    eax, eax
0x18002beee  jnz     short loc_18002BF22
0x18002bef0  call    cs:__imp_GetLastError
0x18002bef7  nop     dword ptr [rax+rax+00h]
0x18002befc  mov     ebx, eax
0x18002befe  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bf05  cmp     rcx, rdi
0x18002bf08  jz      loc_18002C009
0x18002bf0e  test    byte ptr [rcx+1Ch], 1
0x18002bf12  jz      loc_18002C009
0x18002bf18  mov     edx, 0Fh
0x18002bf1d  jmp     loc_18002BC4E
0x18002bf22  call    cs:__imp_CreateThreadpoolCleanupGroup
0x18002bf29  nop     dword ptr [rax+rax+00h]
0x18002bf2e  mov     cs:?g_pCleanupGroup@@3PEAU_TP_CLEANUP_GROUP@@EA, rax; _TP_CLEANUP_GROUP * g_pCleanupGroup
0x18002bf35  test    rax, rax
0x18002bf38  jnz     short loc_18002BF6C
0x18002bf3a  call    cs:__imp_GetLastError
0x18002bf41  nop     dword ptr [rax+rax+00h]
0x18002bf46  mov     ebx, eax
0x18002bf48  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bf4f  cmp     rcx, rdi
0x18002bf52  jz      loc_18002C009
0x18002bf58  test    byte ptr [rcx+1Ch], 1
0x18002bf5c  jz      loc_18002C009
0x18002bf62  mov     edx, 10h
0x18002bf67  jmp     loc_18002BC4E
0x18002bf6c  mov     rcx, cs:?g_pThreadpool@@3PEAU_TP_POOL@@EA; ptpp
0x18002bf73  mov     edx, 3E8h; cthrdMost
0x18002bf78  call    cs:__imp_SetThreadpoolThreadMaximum
0x18002bf7f  nop     dword ptr [rax+rax+00h]
0x18002bf84  mov     rax, cs:?g_pThreadpool@@3PEAU_TP_POOL@@EA; _TP_POOL * g_pThreadpool
0x18002bf8b  xorps   xmm0, xmm0
0x18002bf8e  mov     cs:?g_CallbackEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.Pool, rax; _TP_CALLBACK_ENVIRON_V3 g_CallbackEnv ...
0x18002bf95  mov     rax, cs:?g_pCleanupGroup@@3PEAU_TP_CLEANUP_GROUP@@EA; _TP_CLEANUP_GROUP * g_pCleanupGroup
0x18002bf9c  mov     cs:?g_CallbackEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.CleanupGroup, rax; _TP_CALLBACK_ENVIRON_V3 g_CallbackEnv ...
0x18002bfa3  lea     rax, ?UbpmUtilsThreadPoolCancelCallback@@YAXPEAX0@Z; UbpmUtilsThreadPoolCancelCallback(void *,void *)
0x18002bfaa  mov     cs:?g_CallbackEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.CleanupGroupCancelCallback, rax; _TP_CALLBACK_ENVIRON_V3 g_CallbackEnv ...
0x18002bfb1  mov     cs:?g_CallbackEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.Version, 3; _TP_CALLBACK_ENVIRON_V3 g_CallbackEnv ...
0x18002bfbb  movdqa  xmmword ptr cs:?g_CallbackEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.RaceDll, xmm0; _TP_CALLBACK_ENVIRON_V3 g_CallbackEnv ...
0x18002bfc3  mov     cs:?g_CallbackEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.FinalizationCallback, 0; _TP_CALLBACK_ENVIRON_V3 g_CallbackEnv ...
0x18002bfce  mov     dword ptr cs:?g_CallbackEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.u, 0; _TP_CALLBACK_ENVIRON_V3 g_CallbackEnv ...
0x18002bfd8  mov     cs:?g_CallbackEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.CallbackPriority, 1; _TP_CALLBACK_ENVIRON_V3 g_CallbackEnv ...
0x18002bfe2  mov     cs:?g_CallbackEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.Size, 48h ; 'H'; _TP_CALLBACK_ENVIRON_V3 g_CallbackEnv ...
0x18002bfec  call    ?UbpmpGetCriticalActionsGuids@@YAKXZ; UbpmpGetCriticalActionsGuids(void)
0x18002bff1  mov     ebx, eax
0x18002bff3  test    eax, eax
0x18002bff5  jnz     short loc_18002C009
0x18002bff7  call    UbpmInitializeMaintenance
0x18002bffc  mov     ebx, eax
0x18002bffe  test    eax, eax
0x18002c000  jnz     short loc_18002C009
0x18002c002  call    ?UbpmSystemInterfaceStart@@YAKXZ; UbpmSystemInterfaceStart(void)
0x18002c007  mov     ebx, eax
0x18002c009  mov     rcx, [rsp+110h+DomainInfo]; hMem
0x18002c00e  test    rcx, rcx
0x18002c011  jz      short loc_18002C01F
0x18002c013  call    cs:__imp_LocalFree
0x18002c01a  nop     dword ptr [rax+rax+00h]
0x18002c01f  mov     rcx, [rbp+57h+PolicyHandle]; ObjectHandle
0x18002c023  test    rcx, rcx
0x18002c026  jz      short loc_18002C034
0x18002c028  call    cs:__imp_LsaLookupClose
0x18002c02f  nop     dword ptr [rax+rax+00h]
0x18002c034  mov     eax, ebx
0x18002c036  mov     rcx, [rbp+57h+var_40]
0x18002c03a  xor     rcx, rsp; StackCookie
0x18002c03d  call    __security_check_cookie
0x18002c042  add     rsp, 0E8h
0x18002c049  pop     r15
0x18002c04b  pop     r14
0x18002c04d  pop     r12
0x18002c04f  pop     rdi
0x18002c050  pop     rbx
0x18002c051  pop     rbp
0x18002c052  retn
```
