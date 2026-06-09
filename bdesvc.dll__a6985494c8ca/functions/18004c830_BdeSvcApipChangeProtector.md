# BdeSvcApipChangeProtector

- ea: `0x18004c830`
- end: `0x18004d228`
- name: `BdeSvcApipChangeProtector`
- size: `2552`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180009f30`
- `0x180009f60`
- `0x18000daf8`
- `0x18001bd60`
- `0x180027780`
- `0x18002d424`
- `0x180034070`
- `0x180034d28`
- `0x18003999c`
- `0x1800488b4`
- `0x180049a54`
- `0x180049e70`
- `0x18004c830`
- `0x180069bf8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004d0b4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004d0b4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004d0cf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004d0cf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004d1c5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004d1c5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004c9de`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004c9de`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004c9c7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004d1b1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004c9c7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004d1b1`
- `FVEAPI!FveValidateExistingPassphraseW` at `0x18004cf6f`
- `FVEAPI!FveValidateExistingPassphraseW` at `0x18004cf6f`
- `FVEAPI!FveUpdatePinW` at `0x18004cefb`
- `FVEAPI!FveUpdatePinW` at `0x18004cefb`
- `FVEAPI!FveValidateExistingPinW` at `0x18004ce6b`
- `FVEAPI!FveValidateExistingPinW` at `0x18004ce6b`
- `FVEAPI!FveSetAllowKeyExport` at `0x18004ce0c`
- `FVEAPI!FveSetAllowKeyExport` at `0x18004ce0c`
- `FVEAPI!FveCommitChanges` at `0x18004d06e`
- `FVEAPI!FveCommitChanges` at `0x18004d06e`
- `FVEAPI!FveOpenVolumeW` at `0x18004ca6b`
- `FVEAPI!FveOpenVolumeW` at `0x18004ca6b`
- `FVEAPI!FveGetStatus` at `0x18004cac2`
- `FVEAPI!FveGetStatus` at `0x18004cac2`
- `FVEAPI!FveCloseVolume` at `0x18004d197`
- `FVEAPI!FveCloseVolume` at `0x18004d197`

## pseudocode

```c
__int64 __fastcall BdeSvcApipChangeProtector(
        __int64 a1,
        void *a2,
        _WORD *a3,
        const unsigned __int16 *a4,
        unsigned int a5)
{
  int v5; // r14d
  void *v8; // r13
  PVOID *v10; // rcx
  int updated; // ebx
  __int64 v12; // rdx
  __int64 v13; // r9
  int ClientIntegrityLevel; // eax
  _QWORD *v15; // rcx
  __int64 v16; // rdx
  HANDLE ProcessHeap; // rax
  LPVOID v18; // rax
  unsigned int v19; // ebx
  _QWORD *v20; // rcx
  __int64 v21; // rdx
  int v22; // edi
  __int64 v23; // rcx
  int v24; // eax
  unsigned int v25; // edx
  _QWORD *v26; // rcx
  __int64 v27; // rdx
  int v28; // eax
  unsigned int v29; // eax
  HANDLE v30; // rax
  unsigned int v32; // [rsp+30h] [rbp-D0h] BYREF
  void **v33; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v34; // [rsp+40h] [rbp-C0h]
  void *v35; // [rsp+48h] [rbp-B8h] BYREF
  int v36; // [rsp+50h] [rbp-B0h] BYREF
  struct _GUID v37; // [rsp+58h] [rbp-A8h] BYREF
  _DWORD v38[3]; // [rsp+70h] [rbp-90h] BYREF
  int v39; // [rsp+7Ch] [rbp-84h]

  v5 = 0;
  v35 = (void *)-1LL;
  v36 = 0;
  v32 = 0;
  v34 = 0;
  v33 = &CFvePolicy::`vftable';
  v8 = 0;
  v37 = 0;
  memset_0(v38, 0, 0x90u);
  if ( a5 != 2 && a5 != 8 )
  {
    v10 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 146, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids, a5);
      v10 = (PVOID *)WPP_GLOBAL_Control;
    }
    updated = 87;
    if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 0x40) != 0 )
    {
      v12 = 147;
LABEL_9:
      v13 = (unsigned int)updated;
LABEL_138:
      WPP_SF_d(v10[2], v12, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids, v13);
      goto LABEL_139;
    }
    goto LABEL_139;
  }
  ClientIntegrityLevel = BdeSvcpGetClientIntegrityLevel(&v32);
  updated = ClientIntegrityLevel;
  if ( ClientIntegrityLevel < 0 )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_139;
    v16 = 148;
    goto LABEL_14;
  }
  if ( v32 >= 0x2000 )
  {
    if ( !a2 )
    {
      ProcessHeap = GetProcessHeap();
      v18 = HeapAlloc(ProcessHeap, 0, 0x208u);
      v8 = v18;
      if ( !v18 )
      {
        updated = -2147024882;
        v10 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        {
          v12 = 151;
          goto LABEL_9;
        }
        goto LABEL_139;
      }
      ClientIntegrityLevel = NgscbGetOSVolume(v18);
      updated = ClientIntegrityLevel;
      if ( ClientIntegrityLevel < 0 )
      {
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_139;
        v16 = 152;
        goto LABEL_14;
      }
      a2 = v8;
    }
    ClientIntegrityLevel = FveOpenVolumeW(a2, 1, &v35);
    updated = ClientIntegrityLevel;
    if ( ClientIntegrityLevel < 0 )
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_139;
      v16 = 153;
      goto LABEL_14;
    }
    v38[0] = 144;
    v38[1] = 10;
    ClientIntegrityLevel = FveGetStatus(v35, v38);
    updated = ClientIntegrityLevel;
    if ( ClientIntegrityLevel < 0 )
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_139;
      v16 = 154;
      goto LABEL_14;
    }
    if ( (v39 & 0x400000) != 0 )
    {
      v19 = 2;
      if ( !(unsigned int)NgscbIsServerSku() )
        goto LABEL_42;
    }
    else
    {
      v19 = (v39 & 0x4000) == 0;
    }
    v5 = 1;
    if ( (unsigned int)CBdeSvcSharedState::RegisterProtectorChangeAttempt(a5) )
    {
      if ( a5 == 2 )
      {
        v10 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 155, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids);
          v10 = (PVOID *)WPP_GLOBAL_Control;
        }
        updated = -2144272221;
        if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 0x40) != 0 )
        {
          v12 = 156;
          goto LABEL_9;
        }
      }
      else
      {
        v10 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 157, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids);
          v10 = (PVOID *)WPP_GLOBAL_Control;
        }
        updated = -2144272192;
        if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 0x40) != 0 )
        {
          v12 = 158;
          goto LABEL_9;
        }
      }
      goto LABEL_139;
    }
LABEL_42:
    if ( !a3 || !a4 )
    {
      v10 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 159, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids);
        v10 = (PVOID *)WPP_GLOBAL_Control;
      }
      v13 = 2147942487LL;
      updated = -2147024809;
      if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 0x40) != 0 )
      {
        v12 = 160;
        goto LABEL_138;
      }
      goto LABEL_139;
    }
    if ( v32 < 0x3000 )
    {
      updated = CFvePolicy::Init(&v33, v19);
      if ( updated < 0 )
      {
        v20 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_139;
        v21 = 161;
        goto LABEL_49;
      }
      v22 = 0;
      if ( a5 == 2 )
        v23 = v34 + 40;
      else
        v23 = v34 + 72;
      v32 = 0;
      updated = CFvePolicySettings::ReadPolicyBool(v23, 0, 146, &v32, 0);
      if ( updated < 0 )
      {
        v20 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_139;
        v21 = 164;
LABEL_49:
        WPP_SF_(v20[2], v21, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids);
        goto LABEL_139;
      }
      LOBYTE(v22) = v32 == 0;
      if ( !v22 )
      {
        if ( a5 == 2 )
        {
          v10 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 165, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids);
            v10 = (PVOID *)WPP_GLOBAL_Control;
          }
          updated = -2144272222;
          if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 0x40) != 0 )
          {
            v12 = 166;
            goto LABEL_9;
          }
        }
        else
        {
          v10 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 167, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids);
            v10 = (PVOID *)WPP_GLOBAL_Control;
          }
          updated = -2144272191;
          if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 0x40) != 0 )
          {
            v12 = 168;
            goto LABEL_9;
          }
        }
        goto LABEL_139;
      }
    }
    ClientIntegrityLevel = FveSetAllowKeyExport(1);
    updated = ClientIntegrityLevel;
    if ( ClientIntegrityLevel < 0 )
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_139;
      v16 = 169;
      goto LABEL_14;
    }
    if ( a5 == 2 )
    {
      v24 = FveValidateExistingPinW(v35, a3, &v36, &v37);
      updated = v24;
      if ( v24 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            170,
            &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids,
            (unsigned int)v24);
LABEL_95:
        v25 = 2;
LABEL_96:
        BdeSvcLogEventAsUser(updated, v25);
        goto LABEL_139;
      }
      if ( !v36 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 171, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids);
        updated = -2144272223;
        goto LABEL_95;
      }
      updated = FveUpdatePinW(v35, a4, &v37);
      BdeSvcLogEventAsUser(updated, 2u);
      if ( updated < 0 )
      {
        v26 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_139;
        v27 = 172;
        goto LABEL_106;
      }
      goto LABEL_126;
    }
    v28 = FveValidateExistingPassphraseW(v35, a3, &v36, &v37);
    updated = v28;
    if ( v28 >= 0 )
    {
      if ( v36 )
      {
        v29 = BdeSvcpUpdatePassphrase(v35, &v37, a4);
        updated = v29;
        if ( v29 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 175, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids, v29);
          if ( updated < 0 )
            goto LABEL_139;
        }
        BdeSvcLogEventAsUser(updated, 8u);
        if ( updated < 0 )
        {
          v26 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
            goto LABEL_139;
          v27 = 176;
LABEL_106:
          WPP_SF_d(v26[2], v27, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids, (unsigned int)updated);
          goto LABEL_139;
        }
LABEL_126:
        ClientIntegrityLevel = FveCommitChanges(v35);
        updated = ClientIntegrityLevel;
        if ( ClientIntegrityLevel >= 0 )
        {
          if ( v5 )
          {
            EnterCriticalSection(&CBdeSvcSharedState::sm_acsProtectorChangeAttemptsLock);
            CBdeSvcSharedState::sm_dwProtectorChangeAttempts = 0;
            LeaveCriticalSection(&CBdeSvcSharedState::sm_acsProtectorChangeAttemptsLock);
          }
          goto LABEL_139;
        }
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_139;
        v16 = 179;
LABEL_14:
        WPP_SF_d(v15[2], v16, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids, (unsigned int)ClientIntegrityLevel);
        goto LABEL_139;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 174, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids);
      updated = -2144272215;
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        173,
        &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids,
        (unsigned int)v28);
    }
    v25 = 8;
    goto LABEL_96;
  }
  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 149, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids);
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  updated = -2147024891;
  if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 0x40) != 0 )
  {
    v12 = 150;
    goto LABEL_9;
  }
LABEL_139:
  if ( v35 != (void *)-1LL )
  {
    FveCloseVolume(v35);
    v35 = (void *)-1LL;
  }
  if ( v8 )
  {
    v30 = GetProcessHeap();
    HeapFree(v30, 0, v8);
  }
  while ( *a3 )
    *a3++ = 0;
  while ( *a4 )
    *a4++ = 0;
  CFvePolicy::~CFvePolicy((CFvePolicy *)&v33);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x18004c830  mov     [rsp-8+arg_0], rbx
0x18004c835  push    rbp
0x18004c836  push    rsi
0x18004c837  push    rdi
0x18004c838  push    r12
0x18004c83a  push    r13
0x18004c83c  push    r14
0x18004c83e  push    r15
0x18004c840  lea     rbp, [rsp-10h]
0x18004c845  sub     rsp, 110h
0x18004c84c  mov     rax, cs:__security_cookie
0x18004c853  xor     rax, rsp
0x18004c856  mov     [rbp+40h+var_40], rax
0x18004c85a  xor     r14d, r14d
0x18004c85d  mov     [rsp+140h+var_F8], 0FFFFFFFFFFFFFFFFh
0x18004c866  mov     r12, r8
0x18004c869  mov     [rsp+140h+var_F0], r14d
0x18004c86e  mov     rdi, rdx
0x18004c871  mov     [rsp+140h+var_110], r14d
0x18004c876  xorps   xmm0, xmm0
0x18004c879  mov     [rsp+140h+var_100], r14
0x18004c87e  lea     rax, ??_7CFvePolicy@@6B@; const CFvePolicy::`vftable'
0x18004c885  xor     edx, edx; Val
0x18004c887  mov     r8d, 90h; Size
0x18004c88d  mov     [rsp+140h+var_108], rax
0x18004c892  lea     rcx, [rsp+140h+var_D0]; void *
0x18004c897  mov     r13d, r14d
0x18004c89a  movups  xmmword ptr [rsp+140h+var_E8.Data1], xmm0
0x18004c89f  mov     r15, r9
0x18004c8a2  call    memset_0
0x18004c8a7  mov     esi, [rbp+40h+arg_20]
0x18004c8aa  cmp     esi, 2
0x18004c8ad  jz      short loc_18004C90F
0x18004c8af  cmp     esi, 8
0x18004c8b2  jz      short loc_18004C90F
0x18004c8b4  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c8bb  lea     rdi, WPP_GLOBAL_Control
0x18004c8c2  cmp     rcx, rdi
0x18004c8c5  jz      short loc_18004C8EC
0x18004c8c7  test    byte ptr [rcx+1Ch], 2
0x18004c8cb  jz      short loc_18004C8EC
0x18004c8cd  mov     rcx, [rcx+10h]
0x18004c8d1  lea     r8, WPP_951aaf4f82a831773594a9234edf98f2_Traceguids
0x18004c8d8  mov     edx, 92h
0x18004c8dd  mov     r9d, esi
0x18004c8e0  call    WPP_SF_d
0x18004c8e5  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c8ec  mov     ebx, 57h ; 'W'
0x18004c8f1  cmp     rcx, rdi
0x18004c8f4  jz      loc_18004D18A
0x18004c8fa  test    byte ptr [rcx+1Ch], 40h
0x18004c8fe  jz      loc_18004D18A
0x18004c904  lea     edx, [rbx+3Ch]
0x18004c907  mov     r9d, ebx
0x18004c90a  jmp     loc_18004D17A
0x18004c90f  lea     rcx, [rsp+140h+var_110]; unsigned int *
0x18004c914  call    ?BdeSvcpGetClientIntegrityLevel@@YAJPEAK@Z; BdeSvcpGetClientIntegrityLevel(ulong *)
0x18004c919  mov     ebx, eax
0x18004c91b  test    eax, eax
0x18004c91d  jns     short loc_18004C95D
0x18004c91f  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c926  lea     rdi, WPP_GLOBAL_Control
0x18004c92d  cmp     rcx, rdi
0x18004c930  jz      loc_18004D18A
0x18004c936  test    byte ptr [rcx+1Ch], 2
0x18004c93a  jz      loc_18004D18A
0x18004c940  mov     edx, 94h
0x18004c945  mov     rcx, [rcx+10h]
0x18004c949  lea     r8, WPP_951aaf4f82a831773594a9234edf98f2_Traceguids
0x18004c950  mov     r9d, eax
0x18004c953  call    WPP_SF_d
0x18004c958  jmp     loc_18004D18A
0x18004c95d  cmp     [rsp+140h+var_110], 2000h
0x18004c965  jnb     short loc_18004C9BE
0x18004c967  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c96e  lea     rdi, WPP_GLOBAL_Control
0x18004c975  cmp     rcx, rdi
0x18004c978  jz      short loc_18004C99C
0x18004c97a  test    byte ptr [rcx+1Ch], 2
0x18004c97e  jz      short loc_18004C99C
0x18004c980  mov     rcx, [rcx+10h]
0x18004c984  lea     r8, WPP_951aaf4f82a831773594a9234edf98f2_Traceguids
0x18004c98b  mov     edx, 95h
0x18004c990  call    WPP_SF_
0x18004c995  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c99c  mov     ebx, 80070005h
0x18004c9a1  cmp     rcx, rdi
0x18004c9a4  jz      loc_18004D18A
0x18004c9aa  test    byte ptr [rcx+1Ch], 40h
0x18004c9ae  jz      loc_18004D18A
0x18004c9b4  mov     edx, 96h
0x18004c9b9  jmp     loc_18004C907
0x18004c9be  test    rdi, rdi
0x18004c9c1  jnz     loc_18004CA5E
0x18004c9c7  call    cs:__imp_GetProcessHeap
0x18004c9ce  nop     dword ptr [rax+rax+00h]
0x18004c9d3  xor     edx, edx; dwFlags
0x18004c9d5  mov     r8d, 208h; dwBytes
0x18004c9db  mov     rcx, rax; hHeap
0x18004c9de  call    cs:__imp_HeapAlloc
0x18004c9e5  nop     dword ptr [rax+rax+00h]
0x18004c9ea  mov     r13, rax
0x18004c9ed  test    rax, rax
0x18004c9f0  jnz     short loc_18004CA22
0x18004c9f2  mov     ebx, 8007000Eh
0x18004c9f7  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c9fe  lea     rdi, WPP_GLOBAL_Control
0x18004ca05  cmp     rcx, rdi
0x18004ca08  jz      loc_18004D18A
0x18004ca0e  test    byte ptr [rcx+1Ch], 40h
0x18004ca12  jz      loc_18004D18A
0x18004ca18  mov     edx, 97h
0x18004ca1d  jmp     loc_18004C907
0x18004ca22  mov     rcx, r13
0x18004ca25  call    NgscbGetOSVolume
0x18004ca2a  mov     ebx, eax
0x18004ca2c  test    eax, eax
0x18004ca2e  jns     short loc_18004CA5B
0x18004ca30  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ca37  lea     rdi, WPP_GLOBAL_Control
0x18004ca3e  cmp     rcx, rdi
0x18004ca41  jz      loc_18004D18A
0x18004ca47  test    byte ptr [rcx+1Ch], 2
0x18004ca4b  jz      loc_18004D18A
0x18004ca51  mov     edx, 98h
0x18004ca56  jmp     loc_18004C945
0x18004ca5b  mov     rdi, r13
0x18004ca5e  lea     r8, [rsp+140h+var_F8]
0x18004ca63  mov     edx, 1
0x18004ca68  mov     rcx, rdi
0x18004ca6b  call    cs:__imp_FveOpenVolumeW
0x18004ca72  nop     dword ptr [rax+rax+00h]
0x18004ca77  mov     ebx, eax
0x18004ca79  test    eax, eax
0x18004ca7b  jns     short loc_18004CAA8
0x18004ca7d  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ca84  lea     rdi, WPP_GLOBAL_Control
0x18004ca8b  cmp     rcx, rdi
0x18004ca8e  jz      loc_18004D18A
0x18004ca94  test    byte ptr [rcx+1Ch], 2
0x18004ca98  jz      loc_18004D18A
0x18004ca9e  mov     edx, 99h
0x18004caa3  jmp     loc_18004C945
0x18004caa8  mov     rcx, [rsp+140h+var_F8]
0x18004caad  lea     rdx, [rsp+140h+var_D0]
0x18004cab2  mov     [rsp+140h+var_D0], 90h
0x18004caba  mov     [rsp+140h+var_CC], 0Ah
0x18004cac2  call    cs:__imp_FveGetStatus
0x18004cac9  nop     dword ptr [rax+rax+00h]
0x18004cace  mov     ebx, eax
0x18004cad0  test    eax, eax
0x18004cad2  jns     short loc_18004CAFF
0x18004cad4  mov     rcx, cs:WPP_GLOBAL_Control
0x18004cadb  lea     rdi, WPP_GLOBAL_Control
0x18004cae2  cmp     rcx, rdi
0x18004cae5  jz      loc_18004D18A
0x18004caeb  test    byte ptr [rcx+1Ch], 2
0x18004caef  jz      loc_18004D18A
0x18004caf5  mov     edx, 9Ah
0x18004cafa  jmp     loc_18004C945
0x18004caff  mov     ebx, [rsp+140h+var_C4]
0x18004cb03  bt      ebx, 16h
0x18004cb07  jnb     loc_18004CB90
0x18004cb0d  mov     ebx, 2
0x18004cb12  call    ?NgscbIsServerSku@@YAHXZ; NgscbIsServerSku(void)
0x18004cb17  xor     edx, edx
0x18004cb19  test    eax, eax
0x18004cb1b  jnz     short loc_18004CB98
0x18004cb1d  test    r12, r12
0x18004cb20  jz      loc_18004D12C
0x18004cb26  test    r15, r15
0x18004cb29  jz      loc_18004D12C
0x18004cb2f  cmp     [rsp+140h+var_110], 3000h
0x18004cb37  jnb     loc_18004CE07
0x18004cb3d  mov     edx, ebx
0x18004cb3f  lea     rcx, [rsp+140h+var_108]
0x18004cb44  call    ?Init@CFvePolicy@@UEAAJW4eFveVolumeType@@@Z; CFvePolicy::Init(eFveVolumeType)
0x18004cb49  xor     edx, edx
0x18004cb4b  mov     ebx, eax
0x18004cb4d  test    eax, eax
0x18004cb4f  jns     loc_18004CC69
0x18004cb55  mov     rcx, cs:WPP_GLOBAL_Control
0x18004cb5c  lea     rdi, WPP_GLOBAL_Control
0x18004cb63  cmp     rcx, rdi
0x18004cb66  jz      loc_18004D18A
0x18004cb6c  test    byte ptr [rcx+1Ch], 2
0x18004cb70  jz      loc_18004D18A
0x18004cb76  mov     edx, 0A1h
0x18004cb7b  mov     rcx, [rcx+10h]
0x18004cb7f  lea     r8, WPP_951aaf4f82a831773594a9234edf98f2_Traceguids
0x18004cb86  call    WPP_SF_
0x18004cb8b  jmp     loc_18004D18A
0x18004cb90  shr     ebx, 0Eh
0x18004cb93  not     ebx
0x18004cb95  and     ebx, 1
0x18004cb98  mov     ecx, esi; int
0x18004cb9a  mov     r14d, 1
0x18004cba0  call    ?RegisterProtectorChangeAttempt@CBdeSvcSharedState@@SAHJ@Z; CBdeSvcSharedState::RegisterProtectorChangeAttempt(long)
0x18004cba5  test    eax, eax
0x18004cba7  jz      loc_18004CB1D
0x18004cbad  cmp     esi, 2
0x18004cbb0  jnz     short loc_18004CC09
0x18004cbb2  mov     rcx, cs:WPP_GLOBAL_Control
0x18004cbb9  lea     rdi, WPP_GLOBAL_Control
0x18004cbc0  cmp     rcx, rdi
0x18004cbc3  jz      short loc_18004CBE7
0x18004cbc5  test    [rcx+1Ch], sil
0x18004cbc9  jz      short loc_18004CBE7
0x18004cbcb  mov     rcx, [rcx+10h]
0x18004cbcf  lea     r8, WPP_951aaf4f82a831773594a9234edf98f2_Traceguids
0x18004cbd6  mov     edx, 9Bh
0x18004cbdb  call    WPP_SF_
0x18004cbe0  mov     rcx, cs:WPP_GLOBAL_Control
0x18004cbe7  mov     ebx, 803100A3h
0x18004cbec  cmp     rcx, rdi
0x18004cbef  jz      loc_18004D18A
0x18004cbf5  test    byte ptr [rcx+1Ch], 40h
0x18004cbf9  jz      loc_18004D18A
0x18004cbff  mov     edx, 9Ch
0x18004cc04  jmp     loc_18004C907
0x18004cc09  cmp     esi, 8
0x18004cc0c  jnz     loc_18004CB1D
0x18004cc12  mov     rcx, cs:WPP_GLOBAL_Control
0x18004cc19  lea     rdi, WPP_GLOBAL_Control
0x18004cc20  cmp     rcx, rdi
0x18004cc23  jz      short loc_18004CC47
0x18004cc25  test    byte ptr [rcx+1Ch], 2
0x18004cc29  jz      short loc_18004CC47
0x18004cc2b  mov     rcx, [rcx+10h]
0x18004cc2f  lea     r8, WPP_951aaf4f82a831773594a9234edf98f2_Traceguids
0x18004cc36  mov     edx, 9Dh
0x18004cc3b  call    WPP_SF_
0x18004cc40  mov     rcx, cs:WPP_GLOBAL_Control
0x18004cc47  mov     ebx, 803100C0h
0x18004cc4c  cmp     rcx, rdi
0x18004cc4f  jz      loc_18004D18A
0x18004cc55  test    byte ptr [rcx+1Ch], 40h
0x18004cc59  jz      loc_18004D18A
0x18004cc5f  mov     edx, 9Eh
0x18004cc64  jmp     loc_18004C907
0x18004cc69  mov     edi, edx
0x18004cc6b  cmp     esi, 2
0x18004cc6e  jnz     short loc_18004CC7B
0x18004cc70  mov     rcx, [rsp+140h+var_100]
0x18004cc75  add     rcx, 28h ; '('
0x18004cc79  jmp     short loc_18004CC8D
0x18004cc7b  cmp     esi, 8
0x18004cc7e  jnz     loc_18004CDA9
0x18004cc84  mov     rcx, [rsp+140h+var_100]
0x18004cc89  add     rcx, 48h ; 'H'
0x18004cc8d  lea     r9, [rsp+140h+var_110]
0x18004cc92  mov     [rsp+140h+var_120], rdx
0x18004cc97  mov     r8d, 92h
0x18004cc9d  mov     [rsp+140h+var_110], edx
0x18004cca1  call    ?ReadPolicyBool@CFvePolicySettings@@IEBAJHW4eFveGpDwSetting@@PEAH1@Z; CFvePolicySettings::ReadPolicyBool(int,eFveGpDwSetting,int *,int *)
0x18004cca6  xor     edx, edx
0x18004cca8  mov     ebx, eax
0x18004ccaa  test    eax, eax
0x18004ccac  js      short loc_18004CCB6
0x18004ccae  cmp     [rsp+140h+var_110], edx
0x18004ccb2  setz    dil
0x18004ccb6  test    ebx, ebx
0x18004ccb8  jns     short loc_18004CCE5
0x18004ccba  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ccc1  lea     rdi, WPP_GLOBAL_Control
0x18004ccc8  cmp     rcx, rdi
0x18004cccb  jz      loc_18004D18A
0x18004ccd1  test    byte ptr [rcx+1Ch], 2
0x18004ccd5  jz      loc_18004D18A
0x18004ccdb  mov     edx, 0A4h
0x18004cce0  jmp     loc_18004CB7B
0x18004cce5  test    edi, edi
0x18004cce7  jnz     loc_18004CE07
0x18004cced  cmp     esi, 2
0x18004ccf0  jnz     short loc_18004CD49
0x18004ccf2  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ccf9  lea     rdi, WPP_GLOBAL_Control
0x18004cd00  cmp     rcx, rdi
0x18004cd03  jz      short loc_18004CD27
0x18004cd05  test    [rcx+1Ch], sil
0x18004cd09  jz      short loc_18004CD27
0x18004cd0b  mov     rcx, [rcx+10h]
0x18004cd0f  lea     r8, WPP_951aaf4f82a831773594a9234edf98f2_Traceguids
0x18004cd16  mov     edx, 0A5h
0x18004cd1b  call    WPP_SF_
0x18004cd20  mov     rcx, cs:WPP_GLOBAL_Control
0x18004cd27  mov     ebx, 803100A2h
0x18004cd2c  cmp     rcx, rdi
0x18004cd2f  jz      loc_18004D18A
0x18004cd35  test    byte ptr [rcx+1Ch], 40h
0x18004cd39  jz      loc_18004D18A
0x18004cd3f  mov     edx, 0A6h
0x18004cd44  jmp     loc_18004C907
0x18004cd49  cmp     esi, 8
0x18004cd4c  jnz     loc_18004CE07
0x18004cd52  mov     rcx, cs:WPP_GLOBAL_Control
0x18004cd59  lea     rdi, WPP_GLOBAL_Control
0x18004cd60  cmp     rcx, rdi
0x18004cd63  jz      short loc_18004CD87
0x18004cd65  test    byte ptr [rcx+1Ch], 2
  ... truncated ...
```
