# TsSessionIdGetAppsBlockedTillConsoleUnlocked(ulong)

- ea: `0x180020e80`
- end: `0x180021181`
- name: `?TsSessionIdGetAppsBlockedTillConsoleUnlocked@@YA?AW4AppTypesBlockedTillConsoleUnlocked@@K@Z`
- size: `769`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180020e20`

## callees

- `0x180001d40`
- `0x18000a384`
- `0x18001d580`
- `0x180020e80`
- `0x18002acfc`
- `0x180031960`
- `0x180041d00`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180020eaf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180020eaf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021161`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021161`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180021152`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180021152`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180020f4a`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180020f4a`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180020eef`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180020eef`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TsSessionIdGetAppsBlockedTillConsoleUnlocked(unsigned int a1)
{
  struct _RTL_CRITICAL_SECTION *v2; // rdi
  unsigned int v3; // ebx
  const char *v4; // r9
  int v5; // eax
  DWORD v6; // edx
  int v7; // ecx
  __int64 v8; // r10
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  ULONG UserDataCount; // [rsp+20h] [rbp-E0h]
  bool v14; // [rsp+30h] [rbp-D0h] BYREF
  bool v15; // [rsp+31h] [rbp-CFh] BYREF
  bool v16; // [rsp+32h] [rbp-CEh] BYREF
  bool v17; // [rsp+33h] [rbp-CDh] BYREF
  WINBOOL fPending; // [rsp+34h] [rbp-CCh] BYREF
  int v19; // [rsp+38h] [rbp-C8h] BYREF
  int v20; // [rsp+3Ch] [rbp-C4h] BYREF
  int v21; // [rsp+40h] [rbp-C0h] BYREF
  int v22; // [rsp+44h] [rbp-BCh] BYREF
  struct TSSession *v23; // [rsp+48h] [rbp-B8h] BYREF
  struct _RTL_CRITICAL_SECTION *v24; // [rsp+50h] [rbp-B0h]
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+58h] [rbp-A8h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+70h] [rbp-90h] BYREF
  char *v27; // [rsp+80h] [rbp-80h]
  int v28; // [rsp+88h] [rbp-78h]
  int v29; // [rsp+8Ch] [rbp-74h]
  int *v30; // [rsp+90h] [rbp-70h]
  __int64 v31; // [rsp+98h] [rbp-68h]
  int *v32; // [rsp+A0h] [rbp-60h]
  __int64 v33; // [rsp+A8h] [rbp-58h]
  int *v34; // [rsp+B0h] [rbp-50h]
  __int64 v35; // [rsp+B8h] [rbp-48h]
  bool *v36; // [rsp+C0h] [rbp-40h]
  __int64 v37; // [rsp+C8h] [rbp-38h]
  bool *v38; // [rsp+D0h] [rbp-30h]
  __int64 v39; // [rsp+D8h] [rbp-28h]
  bool *v40; // [rsp+E0h] [rbp-20h]
  __int64 v41; // [rsp+E8h] [rbp-18h]
  bool *v42; // [rsp+F0h] [rbp-10h]
  __int64 v43; // [rsp+F8h] [rbp-8h]
  int *v44; // [rsp+100h] [rbp+0h]
  __int64 v45; // [rsp+108h] [rbp+8h]
  WINBOOL *p_fPending; // [rsp+110h] [rbp+10h]
  __int64 v47; // [rsp+118h] [rbp+18h]
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)g_ApplicationManager + 32);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_ApplicationManager + 32));
  v24 = v2;
  v23 = 0;
  if ( (int)TsSessionFromSessionId(a1, 0, &v23) < 0 )
  {
    v3 = 0;
    goto LABEL_22;
  }
  fPending = 0;
  if ( InitOnceBeginInitialize(&InitOnce, 0, &fPending, 0) )
  {
    if ( fPending )
    {
      v5 = lambda_1cba0c56c11df3097c8f2ad02e3e4fb7_::operator()();
      if ( v5 >= 0 )
      {
        v6 = 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x37F,
          (unsigned int)"wil",
          (const char *)(unsigned int)v5,
          UserDataCount);
        v6 = 4;
      }
      InitOnceComplete(&InitOnce, v6, 0);
    }
  }
  else
  {
    wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0x37A, (unsigned int)"wil", v4);
  }
  if ( !g_GlobalUserPresent )
  {
    v3 = 3;
    goto LABEL_22;
  }
  if ( g_bLowPowerEpoch || g_bApmSuspended || g_PoBlockAudioPlayback )
  {
    v3 = g_AppTypesBlockedTillConsoleUnlocked;
    goto LABEL_22;
  }
  v7 = *((_DWORD *)v23 + 254);
  if ( v7 != 1 )
  {
    if ( !v7 )
      g_AppTypesBlockedTillConsoleUnlocked = 0;
    goto LABEL_20;
  }
  v3 = g_AppTypesBlockedTillConsoleUnlocked;
  if ( !g_AppTypesBlockedTillConsoleUnlocked )
LABEL_20:
    v3 = 0;
LABEL_22:
  v8 = *((_QWORD *)AudioSrvPolicyManagerTelemetryProvider::Instance() + 1);
  if ( *(_DWORD *)v8 > 4u )
  {
    fPending = v3;
    v19 = g_AppTypesBlockedTillConsoleUnlocked;
    v14 = g_PoBlockAudioPlayback;
    v15 = g_bApmSuspended;
    v16 = g_bLowPowerEpoch;
    v17 = g_GlobalUserPresent;
    if ( v23 )
      v9 = *((_DWORD *)v23 + 253);
    else
      v9 = 0;
    v20 = v9;
    if ( v23 )
      v10 = *((_DWORD *)v23 + 254);
    else
      v10 = 0;
    v21 = v10;
    if ( v23 )
      v11 = *(_DWORD *)v23;
    else
      v11 = -1;
    v22 = v11;
    p_fPending = &fPending;
    v47 = 4;
    v44 = &v19;
    v45 = 4;
    v42 = &v14;
    v43 = 1;
    v40 = &v15;
    v41 = 1;
    v38 = &v16;
    v39 = 1;
    v36 = &v17;
    v37 = 1;
    v34 = &v20;
    v35 = 4;
    v32 = &v21;
    v33 = 4;
    v30 = &v22;
    v31 = 4;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    *(_DWORD *)&EventDescriptor.Level = 4;
    EventDescriptor.Keyword = 0;
    UserData.Ptr = *(_QWORD *)(v8 + 8);
    UserData.Size = *(unsigned __int16 *)UserData.Ptr;
    UserData.Reserved = 2;
    v27 = &byte_1800582FF;
    v28 = 201;
    v29 = 1;
    LODWORD(v24) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(*(_QWORD *)(v8 + 32), &EventDescriptor, 0, 0, 0xBu, &UserData);
  }
  if ( v2 )
    LeaveCriticalSection(v2);
  return v3;
}

```

## disassembly

```asm
0x180020e80  push    rbp
0x180020e82  push    rbx
0x180020e83  push    rsi
0x180020e84  push    rdi
0x180020e85  lea     rbp, [rsp-38h]
0x180020e8a  sub     rsp, 138h
0x180020e91  mov     rax, cs:__security_cookie
0x180020e98  xor     rax, rsp
0x180020e9b  mov     [rbp+50h+var_30], rax
0x180020e9f  mov     ebx, ecx
0x180020ea1  mov     rdi, cs:?g_ApplicationManager@@3PEAVCApplicationManager@@EA; CApplicationManager * g_ApplicationManager
0x180020ea8  add     rdi, 20h ; ' '
0x180020eac  mov     rcx, rdi; lpCriticalSection
0x180020eaf  call    cs:__imp_EnterCriticalSection
0x180020eb5  mov     [rsp+150h+var_100], rdi
0x180020eba  xor     esi, esi
0x180020ebc  mov     [rsp+150h+var_108], rsi
0x180020ec1  lea     r8, [rsp+150h+var_108]; struct TSSession **
0x180020ec6  xor     edx, edx; int
0x180020ec8  mov     ecx, ebx; unsigned int
0x180020eca  call    ?TsSessionFromSessionId@@YAJKHPEAPEAVTSSession@@@Z; TsSessionFromSessionId(ulong,int,TSSession * *)
0x180020ecf  test    eax, eax
0x180020ed1  jns     short loc_180020EDA
0x180020ed3  mov     ebx, esi
0x180020ed5  jmp     loc_180020FAB
0x180020eda  mov     [rsp+150h+fPending], esi
0x180020ede  xor     r9d, r9d; lpContext
0x180020ee1  lea     r8, [rsp+150h+fPending]; fPending
0x180020ee6  xor     edx, edx; dwFlags
0x180020ee8  lea     rcx, InitOnce; lpInitOnce
0x180020eef  call    cs:__imp_InitOnceBeginInitialize
0x180020ef5  test    eax, eax
0x180020ef7  jnz     short loc_180020F10
0x180020ef9  mov     rcx, [rbp+58h]; this
0x180020efd  lea     r8, aWil; "wil"
0x180020f04  mov     edx, 37Ah; void *
0x180020f09  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180020f0e  jmp     short loc_180020F50
0x180020f10  cmp     [rsp+150h+fPending], esi
0x180020f14  jz      short loc_180020F50
0x180020f16  call    _lambda_1cba0c56c11df3097c8f2ad02e3e4fb7___operator__
0x180020f1b  test    eax, eax
0x180020f1d  jns     short loc_180020F3E
0x180020f1f  mov     rcx, [rbp+58h]; this
0x180020f23  mov     r9d, eax; char *
0x180020f26  lea     r8, aWil; "wil"
0x180020f2d  mov     edx, 37Fh; void *
0x180020f32  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020f37  mov     edx, 4
0x180020f3c  jmp     short loc_180020F40
0x180020f3e  xor     edx, edx; dwFlags
0x180020f40  xor     r8d, r8d; lpContext
0x180020f43  lea     rcx, InitOnce; lpInitOnce
0x180020f4a  call    cs:__imp_InitOnceComplete
0x180020f50  cmp     cs:?g_GlobalUserPresent@@3_NA, sil; bool g_GlobalUserPresent
0x180020f57  jnz     short loc_180020F60
0x180020f59  mov     ebx, 3
0x180020f5e  jmp     short loc_180020FAB
0x180020f60  cmp     cs:?g_bLowPowerEpoch@@3_NA, sil; bool g_bLowPowerEpoch
0x180020f67  jnz     short loc_180020FA5
0x180020f69  cmp     cs:?g_bApmSuspended@@3_NA, sil; bool g_bApmSuspended
0x180020f70  jnz     short loc_180020FA5
0x180020f72  cmp     cs:?g_PoBlockAudioPlayback@@3_NA, sil; bool g_PoBlockAudioPlayback
0x180020f79  jnz     short loc_180020FA5
0x180020f7b  mov     rax, [rsp+150h+var_108]
0x180020f80  mov     ecx, [rax+3F8h]
0x180020f86  cmp     ecx, 1
0x180020f89  jnz     short loc_180020F97
0x180020f8b  mov     ebx, cs:?g_AppTypesBlockedTillConsoleUnlocked@@3W4AppTypesBlockedTillConsoleUnlocked@@A; AppTypesBlockedTillConsoleUnlocked g_AppTypesBlockedTillConsoleUnlocked
0x180020f91  test    ebx, ebx
0x180020f93  jz      short loc_180020FA1
0x180020f95  jmp     short loc_180020FAB
0x180020f97  test    ecx, ecx
0x180020f99  jnz     short loc_180020FA1
0x180020f9b  mov     cs:?g_AppTypesBlockedTillConsoleUnlocked@@3W4AppTypesBlockedTillConsoleUnlocked@@A, esi; AppTypesBlockedTillConsoleUnlocked g_AppTypesBlockedTillConsoleUnlocked
0x180020fa1  mov     ebx, esi
0x180020fa3  jmp     short loc_180020FAB
0x180020fa5  mov     ebx, cs:?g_AppTypesBlockedTillConsoleUnlocked@@3W4AppTypesBlockedTillConsoleUnlocked@@A; AppTypesBlockedTillConsoleUnlocked g_AppTypesBlockedTillConsoleUnlocked
0x180020fab  call    ?Instance@AudioSrvPolicyManagerTelemetryProvider@@KAPEAV1@XZ; AudioSrvPolicyManagerTelemetryProvider::Instance(void)
0x180020fb0  mov     r10, [rax+8]
0x180020fb4  mov     eax, [r10]
0x180020fb7  cmp     eax, 4
0x180020fba  jbe     loc_180021159
0x180020fc0  mov     [rsp+150h+fPending], ebx
0x180020fc4  mov     eax, cs:?g_AppTypesBlockedTillConsoleUnlocked@@3W4AppTypesBlockedTillConsoleUnlocked@@A; AppTypesBlockedTillConsoleUnlocked g_AppTypesBlockedTillConsoleUnlocked
0x180020fca  mov     [rsp+150h+var_118], eax
0x180020fce  movzx   eax, cs:?g_PoBlockAudioPlayback@@3_NA; bool g_PoBlockAudioPlayback
0x180020fd5  mov     [rsp+150h+var_120], al
0x180020fd9  movzx   eax, cs:?g_bApmSuspended@@3_NA; bool g_bApmSuspended
0x180020fe0  mov     [rsp+150h+var_11F], al
0x180020fe4  movzx   eax, cs:?g_bLowPowerEpoch@@3_NA; bool g_bLowPowerEpoch
0x180020feb  mov     [rsp+150h+var_11E], al
0x180020fef  movzx   eax, cs:?g_GlobalUserPresent@@3_NA; bool g_GlobalUserPresent
0x180020ff6  mov     [rsp+150h+var_11D], al
0x180020ffa  mov     rax, [rsp+150h+var_108]
0x180020fff  test    rax, rax
0x180021002  jz      short loc_18002100C
0x180021004  mov     ecx, [rax+3F4h]
0x18002100a  jmp     short loc_18002100E
0x18002100c  mov     ecx, esi
0x18002100e  mov     [rsp+150h+var_114], ecx
0x180021012  test    rax, rax
0x180021015  jz      short loc_18002101F
0x180021017  mov     ecx, [rax+3F8h]
0x18002101d  jmp     short loc_180021021
0x18002101f  mov     ecx, esi
0x180021021  mov     [rsp+150h+var_110], ecx
0x180021025  test    rax, rax
0x180021028  jz      short loc_18002102E
0x18002102a  mov     ecx, [rax]
0x18002102c  jmp     short loc_180021033
0x18002102e  mov     ecx, 0FFFFFFFFh
0x180021033  mov     [rsp+150h+var_10C], ecx
0x180021037  lea     rax, [rsp+150h+fPending]
0x18002103c  mov     [rbp+50h+var_40], rax
0x180021040  mov     [rbp+50h+var_38], 4
0x180021048  lea     rax, [rsp+150h+var_118]
0x18002104d  mov     [rbp+50h+var_50], rax
0x180021051  mov     [rbp+50h+var_48], 4
0x180021059  lea     rax, [rsp+150h+var_120]
0x18002105e  mov     [rbp+50h+var_60], rax
0x180021062  mov     [rbp+50h+var_58], 1
0x18002106a  lea     rax, [rsp+150h+var_11F]
0x18002106f  mov     [rbp+50h+var_70], rax
0x180021073  mov     [rbp+50h+var_68], 1
0x18002107b  lea     rax, [rsp+150h+var_11E]
0x180021080  mov     [rbp+50h+var_80], rax
0x180021084  mov     [rbp+50h+var_78], 1
0x18002108c  lea     rax, [rsp+150h+var_11D]
0x180021091  mov     [rbp+50h+var_90], rax
0x180021095  mov     [rbp+50h+var_88], 1
0x18002109d  lea     rax, [rsp+150h+var_114]
0x1800210a2  mov     [rbp+50h+var_A0], rax
0x1800210a6  mov     [rbp+50h+var_98], 4
0x1800210ae  lea     rax, [rsp+150h+var_110]
0x1800210b3  mov     [rbp+50h+var_B0], rax
0x1800210b7  mov     [rbp+50h+var_A8], 4
0x1800210bf  lea     rax, [rsp+150h+var_10C]
0x1800210c4  mov     [rbp+50h+var_C0], rax
0x1800210c8  mov     [rbp+50h+var_B8], 4
0x1800210d0  mov     dword ptr [rsp+150h+EventDescriptor.Id], 0B000000h
0x1800210d8  movzx   eax, cs:word_1800582F5
0x1800210df  mov     dword ptr [rsp+150h+EventDescriptor.Level], eax
0x1800210e3  mov     [rsp+150h+EventDescriptor.Keyword], rsi
0x1800210e8  mov     rax, [r10+8]
0x1800210ec  mov     [rsp+150h+var_E0.Ptr], rax
0x1800210f1  movzx   eax, word ptr [rax]
0x1800210f4  mov     [rsp+150h+var_E0.Size], eax
0x1800210f8  mov     dword ptr [rsp+150h+var_E0.0Ch], 2
0x180021100  lea     rax, byte_1800582FF
0x180021107  mov     [rbp+50h+var_D0], rax
0x18002110b  mov     [rbp+50h+var_C8], 0C9h
0x180021112  mov     [rbp+50h+var_C4], 1
0x180021119  lea     rax, _TraceLoggingMetadataEnd
0x180021120  lea     rcx, _TraceLoggingMetadata
0x180021127  sub     eax, ecx
0x180021129  mov     dword ptr [rsp+150h+var_100], eax
0x18002112d  mov     eax, dword ptr [rsp+150h+var_100]
0x180021131  lea     rax, [rsp+150h+var_E0]
0x180021136  mov     [rsp+150h+UserData], rax; UserData
0x18002113b  mov     [rsp+150h+UserDataCount], 0Bh; UserDataCount
0x180021143  xor     r9d, r9d; RelatedActivityId
0x180021146  xor     r8d, r8d; ActivityId
0x180021149  lea     rdx, [rsp+150h+EventDescriptor]; EventDescriptor
0x18002114e  mov     rcx, [r10+20h]; RegHandle
0x180021152  call    cs:__imp_EventWriteTransfer
0x180021158  nop
0x180021159  test    rdi, rdi
0x18002115c  jz      short loc_180021167
0x18002115e  mov     rcx, rdi; lpCriticalSection
0x180021161  call    cs:__imp_LeaveCriticalSection
0x180021167  mov     eax, ebx
0x180021169  mov     rcx, [rbp+50h+var_30]
0x18002116d  xor     rcx, rsp; StackCookie
0x180021170  call    __security_check_cookie
0x180021175  add     rsp, 138h
0x18002117c  pop     rdi
0x18002117d  pop     rsi
0x18002117e  pop     rbx
0x18002117f  pop     rbp
0x180021180  retn
```
