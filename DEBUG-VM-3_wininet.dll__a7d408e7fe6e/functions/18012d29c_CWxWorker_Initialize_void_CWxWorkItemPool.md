# CWxWorker::Initialize(void *,CWxWorkItemPool *)

- ea: `0x18012d29c`
- end: `0x18012d4d8`
- name: `?Initialize@CWxWorker@@AEAAJPEAXPEAVCWxWorkItemPool@@@Z`
- size: `572`
- prototype: `__int64 __fastcall(CWxWorker *__hidden this, void *, struct CWxWorkItemPool *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x18012aa70`

## callees

- `0x1800701d0`
- `0x1800b382c`
- `0x1800b99bc`
- `0x1800b9abc`
- `0x18012d29c`
- `0x18014a7a0`
- `0x18014b3b4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18012d321`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18012d321`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18012d37e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18012d37e`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18012d38a`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18012d38a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18012d4ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18012d4ad`
- `api-ms-win-core-kernel32-legacy-l1-1-0!WTSGetActiveConsoleSessionId` at `0x18012d3be`
- `api-ms-win-core-kernel32-legacy-l1-1-0!WTSGetActiveConsoleSessionId` at `0x18012d3be`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x18012d497`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x18012d497`
- `api-ms-win-power-setting-l1-1-0!PowerSettingRegisterNotification` at `0x18012d42a`
- `api-ms-win-power-setting-l1-1-0!PowerSettingRegisterNotification` at `0x18012d42a`
- `api-ms-win-power-base-l1-1-0!GetPwrCapabilities` at `0x18012d3cd`
- `api-ms-win-power-base-l1-1-0!GetPwrCapabilities` at `0x18012d3cd`

## pseudocode

```c
__int64 __fastcall CWxWorker::Initialize(CWxWorkItemPool **this, CWxWorkItemPool *a2, struct CWxWorkItemPool *a3)
{
  CWxWorkItemPool *EventA; // rbx
  signed int v7; // edi
  __int64 v8; // rcx
  struct _TP_CALLBACK_ENVIRON_V3 *v9; // r8
  int v10; // eax
  DWORD CurrentProcessId; // eax
  __int64 v12; // rcx
  int v13; // eax
  __int64 v14; // rcx
  int LastError; // eax
  signed int v16; // eax
  CWxWorkItemPool *v17; // rcx
  struct _TP_WAIT *v18; // rax
  HPOWERNOTIFY RegistrationHandle; // [rsp+28h] [rbp-51h] BYREF
  struct _TP_WAIT *v21; // [rsp+30h] [rbp-49h] BYREF
  __int128 Recipient; // [rsp+38h] [rbp-41h] BYREF
  DWORD pSessionId; // [rsp+48h] [rbp-31h] BYREF
  _SYSTEM_POWER_CAPABILITIES spc; // [rsp+50h] [rbp-29h] BYREF

  v21 = 0;
  Recipient = 0;
  memset_0(&spc, 0, sizeof(spc));
  RegistrationHandle = 0;
  pSessionId = 0;
  if ( a3 )
  {
    EventA = (CWxWorkItemPool *)CreateEventA(0, 0, 0, 0);
    if ( EventA )
    {
      v7 = WxCreateThreadpoolWait(
             FailFastThreadpoolWaitCallback<&private: static void CWxWorker::WaitCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long)>,
             this,
             v9,
             &v21);
      if ( v7 >= 0 )
      {
        CurrentProcessId = GetCurrentProcessId();
        if ( ProcessIdToSessionId(CurrentProcessId, &pSessionId) )
        {
          if ( pSessionId != WTSGetActiveConsoleSessionId() || GetPwrCapabilities(&spc) )
          {
            v7 = 0;
            if ( !spc.spare2[2] )
              goto LABEL_27;
            *((_QWORD *)&Recipient + 1) = this;
            *(_QWORD *)&Recipient = CWxWorker::DeviceNotifyCallback;
            v16 = PowerSettingRegisterNotification(&GUID_MONITOR_POWER_ON, 2u, &Recipient, &RegistrationHandle);
            v7 = v16;
            if ( v16 > 0 )
              v7 = (unsigned __int16)v16 | 0x80070000;
            if ( v7 >= 0 )
            {
LABEL_27:
              this[7] = EventA;
              EventA = 0;
              _InterlockedIncrement((volatile signed __int32 *)a3 + 18);
              v17 = this[6];
              if ( v17 )
                CWxWorkItemPool::Release(v17);
              v18 = v21;
              this[6] = a3;
              this[9] = v18;
              this[13] = (CWxWorkItemPool *)RegistrationHandle;
              v21 = 0;
              this[10] = a2;
              RegistrationHandle = 0;
            }
          }
          else
          {
            LastError = WxGetLastError(v14);
            v7 = LastError;
            if ( LastError > 0 )
              v7 = (unsigned __int16)LastError | 0x80070000;
            if ( v7 >= 0 )
              v7 = -2147418113;
          }
        }
        else
        {
          v13 = WxGetLastError(v12);
          v7 = v13;
          if ( v13 > 0 )
            v7 = (unsigned __int16)v13 | 0x80070000;
          if ( v7 >= 0 )
            v7 = -2147418113;
        }
      }
    }
    else
    {
      v10 = WxGetLastError(v8);
      v7 = v10;
      if ( v10 > 0 )
        v7 = (unsigned __int16)v10 | 0x80070000;
      if ( v7 >= 0 )
        v7 = -2147418113;
    }
  }
  else
  {
    EventA = 0;
    v7 = -2147024809;
  }
  WxCloseThreadpoolWait(v21);
  if ( RegistrationHandle )
  {
    PowerSettingUnregisterNotification(RegistrationHandle);
    RegistrationHandle = 0;
  }
  if ( EventA )
    CloseHandle(EventA);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18012d29c  mov     [rsp-8+arg_8], rbx
0x18012d2a1  push    rbp
0x18012d2a2  push    rsi
0x18012d2a3  push    rdi
0x18012d2a4  push    r14
0x18012d2a6  push    r15
0x18012d2a8  lea     rbp, [rsp-37h]
0x18012d2ad  sub     rsp, 0B0h
0x18012d2b4  mov     rax, cs:__security_cookie
0x18012d2bb  xor     rax, rsp
0x18012d2be  mov     [rbp+57h+var_30], rax
0x18012d2c2  mov     r15, rdx
0x18012d2c5  mov     [rbp+57h+var_AC], 0
0x18012d2cc  xor     edx, edx; Val
0x18012d2ce  mov     [rbp+57h+var_A0], 0
0x18012d2d6  mov     r14, r8
0x18012d2d9  mov     rsi, rcx
0x18012d2dc  xorps   xmm0, xmm0
0x18012d2df  lea     rcx, [rbp+57h+spc]; void *
0x18012d2e3  movups  [rbp+57h+Recipient], xmm0
0x18012d2e7  lea     r8d, [rdx+4Ch]; Size
0x18012d2eb  call    memset_0
0x18012d2f0  mov     [rbp+57h+RegistrationHandle], 0
0x18012d2f8  mov     [rbp+57h+pSessionId], 0
0x18012d2ff  test    r14, r14
0x18012d302  jnz     short loc_18012D317
0x18012d304  xor     ebx, ebx
0x18012d306  mov     [rbp+57h+var_AC], 78h ; 'x'
0x18012d30d  mov     edi, 80070057h
0x18012d312  jmp     loc_18012D485
0x18012d317  xor     r9d, r9d; lpName
0x18012d31a  xor     r8d, r8d; bInitialState
0x18012d31d  xor     edx, edx; bManualReset
0x18012d31f  xor     ecx, ecx; lpEventAttributes
0x18012d321  call    cs:__imp_CreateEventA
0x18012d327  mov     rbx, rax
0x18012d32a  test    rax, rax
0x18012d32d  jnz     short loc_18012D359
0x18012d32f  call    WxGetLastError
0x18012d334  mov     edi, eax
0x18012d336  test    eax, eax
0x18012d338  jle     short loc_18012D343
0x18012d33a  movzx   edi, ax
0x18012d33d  or      edi, 80070000h
0x18012d343  test    edi, edi
0x18012d345  mov     [rbp+57h+var_AC], 7Bh ; '{'
0x18012d34c  mov     eax, 8000FFFFh
0x18012d351  cmovns  edi, eax
0x18012d354  jmp     loc_18012D485
0x18012d359  lea     r9, [rbp+57h+var_A0]; struct _TP_WAIT **
0x18012d35d  mov     rdx, rsi; void *
0x18012d360  lea     rcx, ??$FailFastThreadpoolWaitCallback@$1?WaitCallback@CWxWorker@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; void (*)(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_WAIT *, int)
0x18012d367  call    ?WxCreateThreadpoolWait@@YAJP6AXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z1PEAU_TP_CALLBACK_ENVIRON_V3@@PEAPEAU2@@Z; WxCreateThreadpoolWait(void (*)(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long),void *,_TP_CALLBACK_ENVIRON_V3 *,_TP_WAIT * *)
0x18012d36c  mov     edi, eax
0x18012d36e  test    eax, eax
0x18012d370  jns     short loc_18012D37E
0x18012d372  mov     [rbp+57h+var_AC], 7Dh ; '}'
0x18012d379  jmp     loc_18012D485
0x18012d37e  call    cs:__imp_GetCurrentProcessId
0x18012d384  mov     ecx, eax; dwProcessId
0x18012d386  lea     rdx, [rbp+57h+pSessionId]; pSessionId
0x18012d38a  call    cs:__imp_ProcessIdToSessionId
0x18012d390  test    eax, eax
0x18012d392  jnz     short loc_18012D3BE
0x18012d394  call    WxGetLastError
0x18012d399  mov     edi, eax
0x18012d39b  test    eax, eax
0x18012d39d  jle     short loc_18012D3A8
0x18012d39f  movzx   edi, ax
0x18012d3a2  or      edi, 80070000h
0x18012d3a8  test    edi, edi
0x18012d3aa  mov     [rbp+57h+var_AC], 87h
0x18012d3b1  mov     eax, 8000FFFFh
0x18012d3b6  cmovns  edi, eax
0x18012d3b9  jmp     loc_18012D485
0x18012d3be  call    cs:__imp_WTSGetActiveConsoleSessionId
0x18012d3c4  cmp     [rbp+57h+pSessionId], eax
0x18012d3c7  jnz     short loc_18012D401
0x18012d3c9  lea     rcx, [rbp+57h+spc]; lpspc
0x18012d3cd  call    cs:__imp_GetPwrCapabilities
0x18012d3d3  test    al, al
0x18012d3d5  jnz     short loc_18012D401
0x18012d3d7  call    WxGetLastError
0x18012d3dc  mov     edi, eax
0x18012d3de  test    eax, eax
0x18012d3e0  jle     short loc_18012D3EB
0x18012d3e2  movzx   edi, ax
0x18012d3e5  or      edi, 80070000h
0x18012d3eb  test    edi, edi
0x18012d3ed  mov     [rbp+57h+var_AC], 8Ch
0x18012d3f4  mov     eax, 8000FFFFh
0x18012d3f9  cmovns  edi, eax
0x18012d3fc  jmp     loc_18012D485
0x18012d401  xor     edi, edi
0x18012d403  cmp     [rbp+57h+spc.spare2+2], dil
0x18012d407  jz      short loc_18012D44C
0x18012d409  lea     rax, ?DeviceNotifyCallback@CWxWorker@@CAKPEAXK0@Z; CWxWorker::DeviceNotifyCallback(void *,ulong,void *)
0x18012d410  mov     qword ptr [rbp+57h+Recipient+8], rsi
0x18012d414  lea     r9, [rbp+57h+RegistrationHandle]; RegistrationHandle
0x18012d418  mov     qword ptr [rbp+57h+Recipient], rax
0x18012d41c  lea     r8, [rbp+57h+Recipient]; Recipient
0x18012d420  lea     edx, [rdi+2]; Flags
0x18012d423  lea     rcx, GUID_MONITOR_POWER_ON; SettingGuid
0x18012d42a  call    cs:__imp_PowerSettingRegisterNotification
0x18012d430  mov     edi, eax
0x18012d432  test    eax, eax
0x18012d434  jle     short loc_18012D43F
0x18012d436  movzx   edi, ax
0x18012d439  or      edi, 80070000h
0x18012d43f  test    edi, edi
0x18012d441  jns     short loc_18012D44C
0x18012d443  mov     [rbp+57h+var_AC], 97h
0x18012d44a  jmp     short loc_18012D485
0x18012d44c  mov     [rsi+38h], rbx
0x18012d450  xor     ebx, ebx
0x18012d452  lock inc dword ptr [r14+48h]
0x18012d457  mov     rcx, [rsi+30h]; this
0x18012d45b  test    rcx, rcx
0x18012d45e  jz      short loc_18012D465
0x18012d460  call    ?Release@CWxWorkItemPool@@QEAAKXZ; CWxWorkItemPool::Release(void)
0x18012d465  mov     rax, [rbp+57h+var_A0]
0x18012d469  mov     [rsi+30h], r14
0x18012d46d  mov     [rsi+48h], rax
0x18012d471  mov     rax, [rbp+57h+RegistrationHandle]
0x18012d475  mov     [rsi+68h], rax
0x18012d479  mov     [rbp+57h+var_A0], rbx
0x18012d47d  mov     [rsi+50h], r15
0x18012d481  mov     [rbp+57h+RegistrationHandle], rbx
0x18012d485  mov     rcx, [rbp+57h+var_A0]; struct _TP_WAIT *
0x18012d489  call    ?WxCloseThreadpoolWait@@YAXPEAU_TP_WAIT@@@Z; WxCloseThreadpoolWait(_TP_WAIT *)
0x18012d48e  mov     rcx, [rbp+57h+RegistrationHandle]; RegistrationHandle
0x18012d492  test    rcx, rcx
0x18012d495  jz      short loc_18012D4A5
0x18012d497  call    cs:__imp_PowerSettingUnregisterNotification
0x18012d49d  mov     [rbp+57h+RegistrationHandle], 0
0x18012d4a5  test    rbx, rbx
0x18012d4a8  jz      short loc_18012D4B3
0x18012d4aa  mov     rcx, rbx; hObject
0x18012d4ad  call    cs:__imp_CloseHandle
0x18012d4b3  mov     eax, edi
0x18012d4b5  mov     rcx, [rbp+57h+var_30]
0x18012d4b9  xor     rcx, rsp; StackCookie
0x18012d4bc  call    __security_check_cookie
0x18012d4c1  mov     rbx, [rsp+0D0h+arg_8]
0x18012d4c9  add     rsp, 0B0h
0x18012d4d0  pop     r15
0x18012d4d2  pop     r14
0x18012d4d4  pop     rdi
0x18012d4d5  pop     rsi
0x18012d4d6  pop     rbp
0x18012d4d7  retn
```
