# DeviceCastle::Library::Internal::Authorization::Manager::Initialize(void)

- ea: `0x180051d84`
- end: `0x180051f34`
- name: `?Initialize@Manager@Authorization@Internal@Library@DeviceCastle@@QEAAJXZ`
- size: `432`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18004c438`

## callees

- `0x18004bf9c`
- `0x180051d84`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051dfd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051dfd`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180051dee`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180051dee`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180051e56`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180051ef6`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180051e56`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180051ef6`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180051dc7`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180051dc7`

## string_xrefs

- `0x180051e8c`: `Could not create the authorization notifier.  The error code was %1!#08I32x!.`

## pseudocode

```c
__int64 __fastcall DeviceCastle::Library::Internal::Authorization::Manager::Initialize(char *pv)
{
  __int64 v2; // rcx
  LONG v3; // eax
  FILETIME v4; // rcx
  PTP_TIMER ThreadpoolTimer; // rax
  signed int LastError; // eax
  signed int v7; // ebx
  char *v8; // rdi
  int v9; // eax
  int v10; // eax
  int v11; // ecx
  __int64 v13; // [rsp+20h] [rbp-28h]
  __int64 v14; // [rsp+20h] [rbp-28h]
  __int64 v15; // [rsp+20h] [rbp-28h]
  __int64 v16; // [rsp+20h] [rbp-28h]
  FILETIME FileTime2; // [rsp+50h] [rbp+8h] BYREF

  v2 = *((unsigned int *)DeviceCastle::Library::Internal::g_pCastleInstance + 41);
  if ( (_DWORD)v2 )
  {
    FileTime2 = (FILETIME)(10000000 * v2);
    v3 = CompareFileTime(&DeviceCastle::Library::Internal::Authorization::MaxTimeout, &FileTime2);
    v4 = FileTime2;
    if ( v3 == -1 )
      v4 = DeviceCastle::Library::Internal::Authorization::MaxTimeout;
    *((FILETIME *)pv + 2) = v4;
  }
  ThreadpoolTimer = CreateThreadpoolTimer(
                      DeviceCastle::Library::Internal::Authorization::Manager::ReaperCallback,
                      pv,
                      0);
  *((_QWORD *)pv + 3) = ThreadpoolTimer;
  if ( ThreadpoolTimer )
  {
    v8 = pv + 72;
    v9 = RtlSubscribeWnfStateChangeNotification(
           pv + 88,
           WNF_NGC_GESTURE_AUTHENTICATED,
           0,
           DeviceCastle::Library::Internal::Authorization::Notifier::NgcContainerAuthenticationCallback,
           pv + 72,
           0,
           0,
           4);
    v7 = 0;
    if ( v9 < 0 )
      v7 = v9;
    if ( v7 < 0 )
    {
      LODWORD(v14) = v7;
      DeviceCastle::Library::DeviceCastleInternal::LogFormattedMessage(
        DeviceCastle::Library::Internal::g_pCastleInstance,
        2u,
        0,
        L"Could not register for container authorization events.  The error code was %1!#08I32x!.",
        v14);
      LODWORD(v15) = v7;
      DeviceCastle::Library::DeviceCastleInternal::LogFormattedMessage(
        DeviceCastle::Library::Internal::g_pCastleInstance,
        2u,
        0,
        L"Could not create the authorization notifier.  The error code was %1!#08I32x!.",
        v15);
LABEL_14:
      LODWORD(v13) = v7;
      DeviceCastle::Library::DeviceCastleInternal::LogFormattedMessage(
        DeviceCastle::Library::Internal::g_pCastleInstance,
        2u,
        0,
        L"Could not initialize authorization manager.  The error code was %1!#08I32x!.",
        v13);
      return (unsigned int)v7;
    }
    v10 = RtlSubscribeWnfStateChangeNotification(
            v8 + 24,
            WNF_EDP_DPL_KEYS_STATE,
            0,
            DeviceCastle::Library::Internal::Authorization::Notifier::EdpDplKeyStateCallback,
            v8,
            0,
            0,
            4);
    v11 = 0;
    if ( v10 < 0 )
      v11 = v10;
    if ( v11 < 0 )
    {
      LODWORD(v16) = v11;
      DeviceCastle::Library::DeviceCastleInternal::LogFormattedMessage(
        DeviceCastle::Library::Internal::g_pCastleInstance,
        2u,
        0,
        L"Could not register for EPL DPL key state events.  The error code was %1!#08I32x!.",
        v16);
    }
    return 0;
  }
  else
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    if ( v7 < 0 )
      goto LABEL_14;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180051d84  mov     [rsp+arg_8], rbx
0x180051d89  push    rdi
0x180051d8a  sub     rsp, 40h
0x180051d8e  mov     rax, cs:?g_pCastleInstance@Internal@Library@DeviceCastle@@3PEAVDeviceCastleInternal@23@EA; DeviceCastle::Library::DeviceCastleInternal * DeviceCastle::Library::Internal::g_pCastleInstance
0x180051d95  mov     rbx, rcx
0x180051d98  mov     ecx, [rax+0A4h]
0x180051d9e  test    ecx, ecx
0x180051da0  jz      short loc_180051DE1
0x180051da2  imul    rdx, rcx, 989680h
0x180051da9  imul    eax, ecx, 989680h
0x180051daf  lea     rcx, ?MaxTimeout@Authorization@Internal@Library@DeviceCastle@@3U_FILETIME@@B; lpFileTime1
0x180051db6  shr     rdx, 20h
0x180051dba  mov     [rsp+48h+FileTime2.dwHighDateTime], edx
0x180051dbe  lea     rdx, [rsp+48h+FileTime2]; lpFileTime2
0x180051dc3  mov     [rsp+48h+FileTime2.dwLowDateTime], eax
0x180051dc7  call    cs:__imp_CompareFileTime
0x180051dcd  mov     rcx, qword ptr [rsp+48h+FileTime2.dwLowDateTime]
0x180051dd2  cmp     eax, 0FFFFFFFFh
0x180051dd5  cmovz   rcx, qword ptr cs:?MaxTimeout@Authorization@Internal@Library@DeviceCastle@@3U_FILETIME@@B.dwLowDateTime; _FILETIME const DeviceCastle::Library::Internal::Authorization::MaxTimeout ...
0x180051ddd  mov     [rbx+10h], rcx
0x180051de1  xor     r8d, r8d; pcbe
0x180051de4  lea     rcx, ?ReaperCallback@Manager@Authorization@Internal@Library@DeviceCastle@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180051deb  mov     rdx, rbx; pv
0x180051dee  call    cs:__imp_CreateThreadpoolTimer
0x180051df4  mov     [rbx+18h], rax
0x180051df8  test    rax, rax
0x180051dfb  jnz     short loc_180051E1F
0x180051dfd  call    cs:__imp_GetLastError
0x180051e03  mov     ebx, eax
0x180051e05  test    eax, eax
0x180051e07  jle     short loc_180051E12
0x180051e09  movzx   ebx, ax
0x180051e0c  or      ebx, 80070000h
0x180051e12  test    ebx, ebx
0x180051e14  jns     loc_180051F27
0x180051e1a  jmp     loc_180051EA3
0x180051e1f  mov     rdx, cs:WNF_NGC_GESTURE_AUTHENTICATED
0x180051e26  lea     rdi, [rbx+48h]
0x180051e2a  mov     [rsp+48h+var_10], 4
0x180051e32  lea     rcx, [rdi+10h]
0x180051e36  mov     [rsp+48h+var_18], 0
0x180051e3e  lea     r9, ?NgcContainerAuthenticationCallback@Notifier@Authorization@Internal@Library@DeviceCastle@@CAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z; DeviceCastle::Library::Internal::Authorization::Notifier::NgcContainerAuthenticationCallback(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)
0x180051e45  mov     [rsp+48h+var_20], 0
0x180051e4e  xor     r8d, r8d
0x180051e51  mov     [rsp+48h+var_28], rdi
0x180051e56  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x180051e5c  xor     ebx, ebx
0x180051e5e  test    eax, eax
0x180051e60  cmovs   ebx, eax
0x180051e63  test    ebx, ebx
0x180051e65  jns     short loc_180051EC3
0x180051e67  mov     rcx, cs:?g_pCastleInstance@Internal@Library@DeviceCastle@@3PEAVDeviceCastleInternal@23@EA; this
0x180051e6e  lea     r9, aCouldNotRegist_0; "Could not register for container author"...
0x180051e75  xor     r8d, r8d; struct DeviceCastle::Library::CallerIdentity *
0x180051e78  mov     dword ptr [rsp+48h+var_28], ebx
0x180051e7c  lea     edx, [r8+2]; unsigned int
0x180051e80  call    ?LogFormattedMessage@DeviceCastleInternal@Library@DeviceCastle@@QEBAXKPEAVCallerIdentity@23@PEBGZZ; DeviceCastle::Library::DeviceCastleInternal::LogFormattedMessage(ulong,DeviceCastle::Library::CallerIdentity *,ushort const *,...)
0x180051e85  mov     rcx, cs:?g_pCastleInstance@Internal@Library@DeviceCastle@@3PEAVDeviceCastleInternal@23@EA; this
0x180051e8c  lea     r9, aCouldNotCreate; "Could not create the authorization noti"...
0x180051e93  xor     r8d, r8d; struct DeviceCastle::Library::CallerIdentity *
0x180051e96  mov     dword ptr [rsp+48h+var_28], ebx
0x180051e9a  lea     edx, [r8+2]; unsigned int
0x180051e9e  call    ?LogFormattedMessage@DeviceCastleInternal@Library@DeviceCastle@@QEBAXKPEAVCallerIdentity@23@PEBGZZ; DeviceCastle::Library::DeviceCastleInternal::LogFormattedMessage(ulong,DeviceCastle::Library::CallerIdentity *,ushort const *,...)
0x180051ea3  mov     rcx, cs:?g_pCastleInstance@Internal@Library@DeviceCastle@@3PEAVDeviceCastleInternal@23@EA; this
0x180051eaa  lea     r9, aCouldNotInitia; "Could not initialize authorization mana"...
0x180051eb1  xor     r8d, r8d; struct DeviceCastle::Library::CallerIdentity *
0x180051eb4  mov     dword ptr [rsp+48h+var_28], ebx
0x180051eb8  lea     edx, [r8+2]; unsigned int
0x180051ebc  call    ?LogFormattedMessage@DeviceCastleInternal@Library@DeviceCastle@@QEBAXKPEAVCallerIdentity@23@PEBGZZ; DeviceCastle::Library::DeviceCastleInternal::LogFormattedMessage(ulong,DeviceCastle::Library::CallerIdentity *,ushort const *,...)
0x180051ec1  jmp     short loc_180051F27
0x180051ec3  mov     rdx, cs:WNF_EDP_DPL_KEYS_STATE
0x180051eca  lea     rcx, [rdi+18h]
0x180051ece  mov     [rsp+48h+var_10], 4
0x180051ed6  lea     r9, ?EdpDplKeyStateCallback@Notifier@Authorization@Internal@Library@DeviceCastle@@CAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z; DeviceCastle::Library::Internal::Authorization::Notifier::EdpDplKeyStateCallback(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)
0x180051edd  mov     [rsp+48h+var_18], 0
0x180051ee5  xor     r8d, r8d
0x180051ee8  mov     [rsp+48h+var_20], 0
0x180051ef1  mov     [rsp+48h+var_28], rdi
0x180051ef6  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x180051efc  xor     ecx, ecx
0x180051efe  test    eax, eax
0x180051f00  cmovs   ecx, eax
0x180051f03  test    ecx, ecx
0x180051f05  jns     short loc_180051F25
0x180051f07  xor     r8d, r8d; struct DeviceCastle::Library::CallerIdentity *
0x180051f0a  mov     dword ptr [rsp+48h+var_28], ecx
0x180051f0e  mov     rcx, cs:?g_pCastleInstance@Internal@Library@DeviceCastle@@3PEAVDeviceCastleInternal@23@EA; this
0x180051f15  lea     r9, aCouldNotRegist; "Could not register for EPL DPL key stat"...
0x180051f1c  lea     edx, [r8+2]; unsigned int
0x180051f20  call    ?LogFormattedMessage@DeviceCastleInternal@Library@DeviceCastle@@QEBAXKPEAVCallerIdentity@23@PEBGZZ; DeviceCastle::Library::DeviceCastleInternal::LogFormattedMessage(ulong,DeviceCastle::Library::CallerIdentity *,ushort const *,...)
0x180051f25  xor     ebx, ebx
0x180051f27  mov     eax, ebx
0x180051f29  mov     rbx, [rsp+48h+arg_8]
0x180051f2e  add     rsp, 40h
0x180051f32  pop     rdi
0x180051f33  retn
```
