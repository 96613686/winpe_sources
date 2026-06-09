# WakeTimer::CreateWakeTimer(ulong,ushort *,void *,void (*)(void *,_CBROKERED_EVENT_ID,void *,void *,ulong,ulong,_BI_ACTIVATION_STATUS *),void * *)

- ea: `0x18002a22c`
- end: `0x18002a4e7`
- name: `?CreateWakeTimer@WakeTimer@@SAKKPEAGPEAXP6AX1U_CBROKERED_EVENT_ID@@11KKPEAW4_BI_ACTIVATION_STATUS@@@ZPEAPEAX@Z`
- size: `699`
- prototype: `__int64 __fastcall(unsigned int, unsigned __int16 *, void *, void (__high *)(void *, struct _CBROKERED_EVENT_ID, void *, void *, unsigned int, unsigned int, enum _BI_ACTIVATION_STATUS *), void **)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180027ba8`
- `0x180027c50`

## callees

- `0x180003ed0`
- `0x18000a0a0`
- `0x180014130`
- `0x18001d8e0`
- `0x18001e368`
- `0x18002a22c`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18002a486`
- `ntdll!RtlNtStatusToDosError` at `0x18002a486`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a2be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a309`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a345`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a389`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a2be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a309`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a345`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a389`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002a2a1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002a2a1`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002a2b4`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002a2b4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a4b8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a4b8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002a2ff`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002a37f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002a2ff`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002a37f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002a398`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002a398`
- `EventAggregation!EaCreateAggregatedEvent` at `0x18002a478`
- `EventAggregation!EaCreateAggregatedEvent` at `0x18002a478`

## string_xrefs

- `0x18002a2d6`: `CreateWakeTimer: OpenProcessToken failed with`
- `0x18002a323`: `CreateWakeTimer: GetTokenInformation failed with`
- `0x18002a35a`: `CreateWakeTimer: Allocation for TokenData failed with`
- `0x18002a497`: `CreateWakeTimer: EaCreateAggregatedEvent failed with`

## pseudocode

```c
__int64 __fastcall WakeTimer::CreateWakeTimer(
        unsigned int a1,
        unsigned __int16 *a2,
        void *a3,
        void (__high *a4)(void *, struct _CBROKERED_EVENT_ID, void *, void *, unsigned int, unsigned int, enum _BI_ACTIVATION_STATUS *),
        void **a5)
{
  void (__high *v5)(void *, struct _CBROKERED_EVENT_ID, void *, void *, unsigned int, unsigned int, enum _BI_ACTIVATION_STATUS *); // rbx
  __int64 v6; // r15
  _QWORD *v8; // rsi
  HANDLE CurrentProcess; // rax
  DWORD LastError; // eax
  __int64 v11; // rdx
  __int64 v12; // rcx
  DWORD v13; // ebx
  const wchar_t *v14; // r8
  NTSTATUS AggregatedEvent; // eax
  DWORD TokenInformationLength; // [rsp+50h] [rbp-B0h] BYREF
  void *TokenHandle; // [rsp+58h] [rbp-A8h] BYREF
  void (__high *v19)(void *, struct _CBROKERED_EVENT_ID, void *, void *, unsigned int, unsigned int, enum _BI_ACTIVATION_STATUS *); // [rsp+60h] [rbp-A0h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v21[10]; // [rsp+70h] [rbp-90h] BYREF
  int v22; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v23[28]; // [rsp+C4h] [rbp-3Ch]
  const wchar_t *v24; // [rsp+E0h] [rbp-20h] BYREF
  int v25; // [rsp+E8h] [rbp-18h]
  int v26; // [rsp+F0h] [rbp-10h]
  const wchar_t *v27; // [rsp+100h] [rbp+0h]
  int v28; // [rsp+108h] [rbp+8h]
  __int64 v29; // [rsp+110h] [rbp+10h]
  const wchar_t *v30; // [rsp+120h] [rbp+20h]
  int v31; // [rsp+128h] [rbp+28h]
  int v32; // [rsp+130h] [rbp+30h]
  const wchar_t *v33; // [rsp+140h] [rbp+40h]
  int v34; // [rsp+148h] [rbp+48h]
  unsigned int v35; // [rsp+150h] [rbp+50h]

  v5 = a4;
  v6 = a1;
  v19 = a4;
  TokenHandle = 0;
  TokenInformationLength = 0;
  SystemTimeAsFileTime = 0;
  v8 = 0;
  memset_0(v21, 0, 0x48u);
  v22 = 0;
  *(_OWORD *)v23 = 0;
  *a5 = 0;
  *(_OWORD *)&v23[12] = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 0x20008u, &TokenHandle) )
  {
    LastError = GetLastError();
    v13 = LastError;
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) == 0 )
      goto LABEL_18;
    v14 = L"CreateWakeTimer: OpenProcessToken failed with";
    goto LABEL_17;
  }
  if ( !GetTokenInformation(TokenHandle, TokenUser, 0, TokenInformationLength, &TokenInformationLength) )
  {
    LastError = GetLastError();
    v13 = LastError;
    if ( LastError != 122 )
    {
LABEL_6:
      if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) == 0 )
        goto LABEL_18;
      v14 = L"CreateWakeTimer: GetTokenInformation failed with";
      goto LABEL_17;
    }
    v5 = v19;
  }
  v8 = MALLOC(TokenInformationLength);
  if ( !v8 )
  {
    LastError = GetLastError();
    v13 = LastError;
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) == 0 )
      goto LABEL_18;
    v14 = L"CreateWakeTimer: Allocation for TokenData failed with";
    goto LABEL_17;
  }
  if ( !GetTokenInformation(TokenHandle, TokenUser, v8, TokenInformationLength, &TokenInformationLength) )
  {
    LastError = GetLastError();
    v13 = LastError;
    goto LABEL_6;
  }
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v19 = (void (__high *)(void *, struct _CBROKERED_EVENT_ID, void *, void *, unsigned int, unsigned int, enum _BI_ACTIVATION_STATUS *))SystemTimeAsFileTime;
  v24 = L"Type";
  v27 = L"InitialDueTime";
  v30 = L"WakeEnabled";
  v33 = L"WindowInSeconds";
  *(_QWORD *)v23 = *(_QWORD *)&GUID_TIME_BROKER.Data2;
  *(_DWORD *)&v23[8] = *(_DWORD *)&GUID_TIME_BROKER.Data4[4];
  *(_QWORD *)&v23[20] = &v24;
  v35 = (unsigned int)v6 / 0x4E20 + 1;
  v26 = 4;
  v29 = *(_QWORD *)&SystemTimeAsFileTime + 10000 * v6;
  *(_WORD *)&v23[12] = 4;
  v25 = 0;
  v28 = 1;
  v31 = 0;
  v32 = 1;
  v34 = 0;
  v22 = -1244867089;
  v21[0] = &v22;
  v21[7] = a2;
  v21[8] = *v8;
  AggregatedEvent = EaCreateAggregatedEvent(v21, 0, v5);
  v13 = 0;
  if ( AggregatedEvent < 0 )
  {
    LastError = RtlNtStatusToDosError(AggregatedEvent);
    v13 = LastError;
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
    {
      v14 = L"CreateWakeTimer: EaCreateAggregatedEvent failed with";
LABEL_17:
      McTemplateU0zq_EventWriteTransfer(v12, v11, v14, LastError);
    }
  }
LABEL_18:
  VpnFree(v8);
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return v13;
}

```

## disassembly

```asm
0x18002a22c  mov     [rsp-8+arg_0], rbx
0x18002a231  push    rbp
0x18002a232  push    rsi
0x18002a233  push    rdi
0x18002a234  push    r12
0x18002a236  push    r13
0x18002a238  push    r14
0x18002a23a  push    r15
0x18002a23c  lea     rbp, [rsp-70h]
0x18002a241  sub     rsp, 170h
0x18002a248  mov     rax, cs:__security_cookie
0x18002a24f  xor     rax, rsp
0x18002a252  mov     [rbp+0A0h+var_40], rax
0x18002a256  mov     r14, [rbp+0A0h+arg_20]
0x18002a25d  xor     edi, edi
0x18002a25f  mov     rbx, r9
0x18002a262  mov     r15d, ecx
0x18002a265  mov     r13, r8
0x18002a268  mov     [rsp+1A0h+var_140], rbx
0x18002a26d  mov     r12, rdx
0x18002a270  mov     [rsp+1A0h+TokenHandle], rdi
0x18002a275  lea     r8d, [rdi+48h]; Size
0x18002a279  mov     [rsp+1A0h+TokenInformationLength], edi
0x18002a27d  xor     edx, edx; Val
0x18002a27f  mov     qword ptr [rsp+1A0h+SystemTimeAsFileTime.dwLowDateTime], rdi
0x18002a284  lea     rcx, [rsp+1A0h+var_130]; void *
0x18002a289  mov     esi, edi
0x18002a28b  call    memset_0
0x18002a290  xorps   xmm0, xmm0
0x18002a293  mov     [rbp+0A0h+var_E0], edi
0x18002a296  movups  [rbp+0A0h+var_DC], xmm0
0x18002a29a  mov     [r14], rdi
0x18002a29d  movups  [rbp+0A0h+var_DC+0Ch], xmm0
0x18002a2a1  call    cs:__imp_GetCurrentProcess
0x18002a2a7  lea     r8, [rsp+1A0h+TokenHandle]; TokenHandle
0x18002a2ac  mov     edx, 20008h; DesiredAccess
0x18002a2b1  mov     rcx, rax; ProcessHandle
0x18002a2b4  call    cs:__imp_OpenProcessToken
0x18002a2ba  test    eax, eax
0x18002a2bc  jnz     short loc_18002A2E2
0x18002a2be  call    cs:__imp_GetLastError
0x18002a2c4  lea     edi, [rsi+1]
0x18002a2c7  mov     ebx, eax
0x18002a2c9  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, dil
0x18002a2d0  jz      loc_18002A4A6
0x18002a2d6  lea     r8, aCreatewaketime_0; "CreateWakeTimer: OpenProcessToken faile"...
0x18002a2dd  jmp     loc_18002A49E
0x18002a2e2  mov     r9d, [rsp+1A0h+TokenInformationLength]; TokenInformationLength
0x18002a2e7  lea     rax, [rsp+1A0h+TokenInformationLength]
0x18002a2ec  mov     rcx, [rsp+1A0h+TokenHandle]; TokenHandle
0x18002a2f1  xor     r8d, r8d; TokenInformation
0x18002a2f4  mov     [rsp+1A0h+ReturnLength], rax; ReturnLength
0x18002a2f9  lea     edi, [r8+1]
0x18002a2fd  mov     edx, edi; TokenInformationClass
0x18002a2ff  call    cs:__imp_GetTokenInformation
0x18002a305  test    eax, eax
0x18002a307  jnz     short loc_18002A334
0x18002a309  call    cs:__imp_GetLastError
0x18002a30f  mov     ebx, eax
0x18002a311  cmp     eax, 7Ah ; 'z'
0x18002a314  jz      short loc_18002A32F
0x18002a316  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, dil
0x18002a31d  jz      loc_18002A4A6
0x18002a323  lea     r8, aCreatewaketime_1; "CreateWakeTimer: GetTokenInformation fa"...
0x18002a32a  jmp     loc_18002A49E
0x18002a32f  mov     rbx, [rsp+1A0h+var_140]
0x18002a334  mov     ecx, [rsp+1A0h+TokenInformationLength]; dwBytes
0x18002a338  call    ?MALLOC@@YAPEAX_K@Z; MALLOC(unsigned __int64)
0x18002a33d  mov     rsi, rax
0x18002a340  test    rax, rax
0x18002a343  jnz     short loc_18002A366
0x18002a345  call    cs:__imp_GetLastError
0x18002a34b  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, dil
0x18002a352  mov     ebx, eax
0x18002a354  jz      loc_18002A4A6
0x18002a35a  lea     r8, aCreatewaketime; "CreateWakeTimer: Allocation for TokenDa"...
0x18002a361  jmp     loc_18002A49E
0x18002a366  mov     r9d, [rsp+1A0h+TokenInformationLength]; TokenInformationLength
0x18002a36b  lea     rax, [rsp+1A0h+TokenInformationLength]
0x18002a370  mov     rcx, [rsp+1A0h+TokenHandle]; TokenHandle
0x18002a375  mov     r8, rsi; TokenInformation
0x18002a378  mov     edx, edi; TokenInformationClass
0x18002a37a  mov     [rsp+1A0h+ReturnLength], rax; ReturnLength
0x18002a37f  call    cs:__imp_GetTokenInformation
0x18002a385  test    eax, eax
0x18002a387  jnz     short loc_18002A393
0x18002a389  call    cs:__imp_GetLastError
0x18002a38f  mov     ebx, eax
0x18002a391  jmp     short loc_18002A316
0x18002a393  lea     rcx, [rsp+1A0h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18002a398  call    cs:__imp_GetSystemTimeAsFileTime
0x18002a39e  mov     eax, [rsp+1A0h+SystemTimeAsFileTime.dwHighDateTime]
0x18002a3a2  xor     r9d, r9d
0x18002a3a5  movsd   xmm0, qword ptr cs:GUID_TIME_BROKER.Data2
0x18002a3ad  mov     dword ptr [rsp+1A0h+var_140+4], eax
0x18002a3b1  mov     eax, [rsp+1A0h+SystemTimeAsFileTime.dwLowDateTime]
0x18002a3b5  mov     dword ptr [rsp+1A0h+var_140], eax
0x18002a3b9  lea     r8d, [r9+4]
0x18002a3bd  mov     [rsp+1A0h+var_160], r14
0x18002a3c2  lea     rax, aType; "Type"
0x18002a3c9  mov     [rbp+0A0h+var_C0], rax
0x18002a3cd  lea     rax, aInitialduetime; "InitialDueTime"
0x18002a3d4  mov     [rbp+0A0h+var_A0], rax
0x18002a3d8  lea     rax, aWakeenabled; "WakeEnabled"
0x18002a3df  mov     [rbp+0A0h+var_80], rax
0x18002a3e3  lea     rax, aWindowinsecond; "WindowInSeconds"
0x18002a3ea  mov     [rbp+0A0h+var_60], rax
0x18002a3ee  mov     eax, 0D1B71759h
0x18002a3f3  mul     r15d
0x18002a3f6  movsd   qword ptr [rbp+0A0h+var_DC], xmm0
0x18002a3fb  imul    rcx, r15, 2710h
0x18002a402  mov     eax, dword ptr cs:GUID_TIME_BROKER.Data4+4
0x18002a408  mov     dword ptr [rbp+0A0h+var_DC+8], eax
0x18002a40b  lea     rax, [rbp+0A0h+var_C0]
0x18002a40f  mov     [rsp+1A0h+var_168], r9d
0x18002a414  shr     edx, 0Eh
0x18002a417  add     rcx, [rsp+1A0h+var_140]
0x18002a41c  add     edx, edi
0x18002a41e  mov     [rbp+0A0h+var_C8], rax
0x18002a422  lea     rax, [rbp+0A0h+var_E0]
0x18002a426  mov     [rbp+0A0h+var_50], edx
0x18002a429  xor     edx, edx
0x18002a42b  mov     [rbp+0A0h+var_B0], r8d
0x18002a42f  mov     [rbp+0A0h+var_90], rcx
0x18002a433  lea     rcx, [rsp+1A0h+var_130]
0x18002a438  mov     word ptr [rbp+0A0h+var_DC+0Ch], r8w
0x18002a43d  mov     r8, rbx
0x18002a440  mov     [rbp+0A0h+var_B8], r9d
0x18002a444  mov     [rbp+0A0h+var_98], edi
0x18002a447  mov     [rbp+0A0h+var_78], r9d
0x18002a44b  mov     [rbp+0A0h+var_70], edi
0x18002a44e  mov     [rbp+0A0h+var_58], r9d
0x18002a452  mov     [rbp+0A0h+var_E0], 0B5CCD5EFh
0x18002a459  mov     [rsp+1A0h+var_130], rax
0x18002a45e  mov     [rbp+0A0h+var_F8], r12
0x18002a462  mov     rax, [rsi]
0x18002a465  mov     [rsp+1A0h+var_170], r13
0x18002a46a  mov     [rsp+1A0h+var_178], r9
0x18002a46f  mov     [rbp+0A0h+var_F0], rax
0x18002a473  mov     [rsp+1A0h+ReturnLength], r9
0x18002a478  call    cs:__imp_EaCreateAggregatedEvent
0x18002a47e  xor     ebx, ebx
0x18002a480  test    eax, eax
0x18002a482  jns     short loc_18002A4A6
0x18002a484  mov     ecx, eax; Status
0x18002a486  call    cs:__imp_RtlNtStatusToDosError
0x18002a48c  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, dil
0x18002a493  mov     ebx, eax
0x18002a495  jz      short loc_18002A4A6
0x18002a497  lea     r8, aCreatewaketime_2; "CreateWakeTimer: EaCreateAggregatedEven"...
0x18002a49e  mov     r9d, eax
0x18002a4a1  call    McTemplateU0zq_EventWriteTransfer
0x18002a4a6  mov     rcx, rsi; lpMem
0x18002a4a9  call    VpnFree
0x18002a4ae  mov     rcx, [rsp+1A0h+TokenHandle]; hObject
0x18002a4b3  test    rcx, rcx
0x18002a4b6  jz      short loc_18002A4BE
0x18002a4b8  call    cs:__imp_CloseHandle
0x18002a4be  mov     eax, ebx
0x18002a4c0  mov     rcx, [rbp+0A0h+var_40]
0x18002a4c4  xor     rcx, rsp; StackCookie
0x18002a4c7  call    __security_check_cookie
0x18002a4cc  mov     rbx, [rsp+1A0h+arg_0]
0x18002a4d4  add     rsp, 170h
0x18002a4db  pop     r15
0x18002a4dd  pop     r14
0x18002a4df  pop     r13
0x18002a4e1  pop     r12
0x18002a4e3  pop     rdi
0x18002a4e4  pop     rsi
0x18002a4e5  pop     rbp
0x18002a4e6  retn
```
