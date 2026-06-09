# SecurityMitigationsBrokerStatics::NotifyDisplayDriverUpdate(unsigned __int64)

- ea: `0x180002d70`
- end: `0x18000304b`
- name: `?NotifyDisplayDriverUpdate@SecurityMitigationsBrokerStatics@@UEAAJ_K@Z`
- size: `731`
- prototype: `__int64 __fastcall(SecurityMitigationsBrokerStatics *this, void *, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x180002288`
- `0x180002d70`
- `0x18000342c`
- `0x180006980`
- `0x180007010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180002e97`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180002e97`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180002eb1`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180002eb1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180002ee5`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180002ee5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002efa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002fe1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002efa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002fe1`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x180002dd5`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x180002dd5`

## pseudocode

```c
__int64 __fastcall SecurityMitigationsBrokerStatics::NotifyDisplayDriverUpdate(
        SecurityMitigationsBrokerStatics *this,
        void *a2,
        __int64 a3)
{
  HRESULT v4; // eax
  __int64 v5; // rcx
  __int64 v6; // r8
  unsigned int v7; // ebx
  DWORD *p_TokenInformation; // rax
  __int64 *v9; // rdx
  __int64 v10; // r9
  DWORD ProcessId; // eax
  unsigned int v12; // r15d
  bool v13; // bl
  signed int v14; // eax
  __int64 *v15; // rdx
  HANDLE v16; // rcx
  void *v17; // rcx
  HRESULT TokenInformation; // [rsp+30h] [rbp-39h] BYREF
  DWORD ReturnLength; // [rsp+38h] [rbp-31h] BYREF
  HANDLE Process; // [rsp+40h] [rbp-29h] BYREF
  void *ppInterface; // [rsp+48h] [rbp-21h] BYREF
  void *TokenHandle[2]; // [rsp+50h] [rbp-19h] BYREF
  _BYTE v24[16]; // [rsp+60h] [rbp-9h] BYREF
  void **v25; // [rsp+70h] [rbp+7h]
  __int64 v26; // [rsp+78h] [rbp+Fh]
  DWORD *p_ReturnLength; // [rsp+80h] [rbp+17h]
  __int64 v28; // [rsp+88h] [rbp+1Fh]
  HRESULT *v29; // [rsp+90h] [rbp+27h]
  __int64 v30; // [rsp+98h] [rbp+2Fh]

  Process = 0;
  if ( (Microsoft_Windows_SecurityMitigationsBrokerEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(this, NotifyDisplayDriverUpdateStart, a3, 1, TokenHandle);
  ppInterface = 0;
  v4 = CoGetCallContext(&GUID_68c6a1b9_de39_42c3_8d28_bf40a5126541, &ppInterface);
  v7 = v4;
  if ( v4 == -2147417833 )
  {
    if ( (Microsoft_Windows_SecurityMitigationsBrokerEnableBits & 4) != 0 )
    {
      TokenInformation = 0;
      v25 = TokenHandle;
      p_TokenInformation = (DWORD *)&TokenInformation;
LABEL_25:
      v15 = NonAppContainerProcess;
      goto LABEL_26;
    }
    goto LABEL_27;
  }
  if ( v4 < 0 )
  {
    if ( (Microsoft_Windows_SecurityMitigationsBrokerEnableBits & 2) == 0 )
      goto LABEL_28;
    v9 = CoGetCallContextFailed;
LABEL_9:
    TokenInformation = v4;
    v10 = 3;
    v25 = TokenHandle;
    p_ReturnLength = (DWORD *)&TokenInformation;
    goto LABEL_10;
  }
  v4 = (*(__int64 (__fastcall **)(void *, __int64, HANDLE *))(*(_QWORD *)ppInterface + 24LL))(
         ppInterface,
         0x1FFFFF,
         &Process);
  v7 = v4;
  if ( v4 < 0 )
  {
    if ( (Microsoft_Windows_SecurityMitigationsBrokerEnableBits & 2) == 0 )
      goto LABEL_28;
    v9 = OpenCallerProcessHandleFailed;
    goto LABEL_9;
  }
  ProcessId = GetProcessId(Process);
  TokenHandle[0] = 0;
  v12 = ProcessId;
  if ( OpenProcessToken(Process, 8u, TokenHandle) )
  {
    TokenInformation = 0;
    ReturnLength = 0;
    v13 = 0;
    if ( GetTokenInformation(TokenHandle[0], TokenIsAppContainer, &TokenInformation, 4u, &ReturnLength) )
      v13 = TokenInformation != 0;
    CloseHandle(TokenHandle[0]);
    if ( v13 )
    {
      v14 = AdjustACGProtectionStatus(Process, v12, (unsigned __int64)a2);
      v7 = v14;
      if ( v14 >= 0 )
      {
        if ( (Microsoft_Windows_SecurityMitigationsBrokerEnableBits & 0x10) != 0 )
        {
          ReturnLength = v12;
          v25 = TokenHandle;
          v15 = AppliedReportedDriverUpdate;
          p_TokenInformation = &ReturnLength;
LABEL_26:
          p_ReturnLength = p_TokenInformation;
          TokenHandle[0] = a2;
          v26 = 8;
          v28 = 4;
          McGenEventWrite_EventWriteTransfer(v5, v15, v6, 3, v24);
          goto LABEL_27;
        }
        goto LABEL_27;
      }
      if ( (Microsoft_Windows_SecurityMitigationsBrokerEnableBits & 8) == 0 )
        goto LABEL_28;
      TokenInformation = v14;
      v9 = AdjustACGProtectionStatusFailed;
      ReturnLength = v12;
      v25 = TokenHandle;
      v10 = 4;
      v30 = 4;
      p_ReturnLength = &ReturnLength;
      v29 = &TokenInformation;
LABEL_10:
      TokenHandle[0] = a2;
      v26 = 8;
      v28 = 4;
      McGenEventWrite_EventWriteTransfer(v5, v9, v6, v10, v24);
      goto LABEL_28;
    }
  }
  if ( (Microsoft_Windows_SecurityMitigationsBrokerEnableBits & 4) != 0 )
  {
    ReturnLength = v12;
    v25 = TokenHandle;
    p_TokenInformation = &ReturnLength;
    goto LABEL_25;
  }
LABEL_27:
  v7 = 0;
LABEL_28:
  v16 = Process;
  if ( Process )
    CloseHandle(Process);
  if ( (Microsoft_Windows_SecurityMitigationsBrokerEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(v16, NotifyDisplayDriverUpdateStop, v6, 1, TokenHandle);
  v17 = ppInterface;
  if ( ppInterface )
  {
    ppInterface = 0;
    (*(void (__fastcall **)(void *))(*(_QWORD *)v17 + 16LL))(v17);
  }
  return v7;
}

```

## disassembly

```asm
0x180002d70  mov     [rsp-8+arg_0], rbx
0x180002d75  mov     [rsp-8+arg_10], r12
0x180002d7a  push    rbp
0x180002d7b  push    r14
0x180002d7d  push    r15
0x180002d7f  lea     rbp, [rsp-47h]
0x180002d84  sub     rsp, 0B0h
0x180002d8b  mov     rax, cs:__security_cookie
0x180002d92  xor     rax, rsp
0x180002d95  mov     [rbp+57h+var_20], rax
0x180002d99  xor     r12d, r12d
0x180002d9c  mov     r14, rdx
0x180002d9f  test    byte ptr cs:Microsoft_Windows_SecurityMitigationsBrokerEnableBits, 1
0x180002da6  mov     [rbp+57h+Process], r12
0x180002daa  jz      short loc_180002DC6
0x180002dac  lea     rax, [rbp+57h+TokenHandle]
0x180002db0  lea     r9d, [r12+1]
0x180002db5  mov     [rsp+0C0h+ReturnLength], rax
0x180002dba  lea     rdx, NotifyDisplayDriverUpdateStart
0x180002dc1  call    McGenEventWrite_EventWriteTransfer
0x180002dc6  lea     rdx, [rbp+57h+ppInterface]; ppInterface
0x180002dca  mov     [rbp+57h+ppInterface], r12
0x180002dce  lea     rcx, _GUID_68c6a1b9_de39_42c3_8d28_bf40a5126541; riid
0x180002dd5  call    cs:__imp_CoGetCallContext
0x180002ddb  mov     ebx, eax
0x180002ddd  cmp     eax, 80010117h
0x180002de2  jnz     short loc_180002E06
0x180002de4  test    byte ptr cs:Microsoft_Windows_SecurityMitigationsBrokerEnableBits, 4
0x180002deb  jz      loc_180002FD5
0x180002df1  lea     rax, [rbp+57h+TokenHandle]
0x180002df5  mov     [rbp+57h+TokenInformation], r12d
0x180002df9  mov     [rbp+57h+var_50], rax
0x180002dfd  lea     rax, [rbp+57h+TokenInformation]
0x180002e01  jmp     loc_180002FA2
0x180002e06  test    eax, eax
0x180002e08  jns     short loc_180002E5E
0x180002e0a  test    byte ptr cs:Microsoft_Windows_SecurityMitigationsBrokerEnableBits, 2
0x180002e11  jz      loc_180002FD8
0x180002e17  lea     rdx, CoGetCallContextFailed
0x180002e1e  mov     [rbp+57h+TokenInformation], eax
0x180002e21  mov     r9d, 3
0x180002e27  lea     rax, [rbp+57h+TokenHandle]
0x180002e2b  mov     [rbp+57h+var_50], rax
0x180002e2f  lea     rax, [rbp+57h+TokenInformation]
0x180002e33  mov     [rbp+57h+var_40], rax
0x180002e37  lea     rax, [rbp+57h+var_60]
0x180002e3b  mov     [rbp+57h+TokenHandle], r14
0x180002e3f  mov     [rbp+57h+var_48], 8
0x180002e47  mov     [rbp+57h+var_38], 4
0x180002e4f  mov     [rsp+0C0h+ReturnLength], rax
0x180002e54  call    McGenEventWrite_EventWriteTransfer
0x180002e59  jmp     loc_180002FD8
0x180002e5e  mov     rcx, [rbp+57h+ppInterface]
0x180002e62  lea     r8, [rbp+57h+Process]
0x180002e66  mov     edx, 1FFFFFh
0x180002e6b  mov     rax, [rcx]
0x180002e6e  mov     rax, [rax+18h]
0x180002e72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e77  mov     ebx, eax
0x180002e79  test    eax, eax
0x180002e7b  jns     short loc_180002E93
0x180002e7d  test    byte ptr cs:Microsoft_Windows_SecurityMitigationsBrokerEnableBits, 2
0x180002e84  jz      loc_180002FD8
0x180002e8a  lea     rdx, OpenCallerProcessHandleFailed
0x180002e91  jmp     short loc_180002E1E
0x180002e93  mov     rcx, [rbp+57h+Process]; Process
0x180002e97  call    cs:__imp_GetProcessId
0x180002e9d  mov     rcx, [rbp+57h+Process]; ProcessHandle
0x180002ea1  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x180002ea5  mov     edx, 8; DesiredAccess
0x180002eaa  mov     [rbp+57h+TokenHandle], r12
0x180002eae  mov     r15d, eax
0x180002eb1  call    cs:__imp_OpenProcessToken
0x180002eb7  test    eax, eax
0x180002eb9  jz      loc_180002F89
0x180002ebf  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x180002ec3  lea     rax, [rbp+57h+var_88]
0x180002ec7  mov     r9d, 4; TokenInformationLength
0x180002ecd  mov     [rbp+57h+TokenInformation], r12d
0x180002ed1  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x180002ed5  mov     [rbp+57h+var_88], r12d
0x180002ed9  mov     bl, r12b
0x180002edc  mov     [rsp+0C0h+ReturnLength], rax; ReturnLength
0x180002ee1  lea     edx, [r9+19h]; TokenInformationClass
0x180002ee5  call    cs:__imp_GetTokenInformation
0x180002eeb  test    eax, eax
0x180002eed  jz      short loc_180002EF6
0x180002eef  cmp     [rbp+57h+TokenInformation], r12d
0x180002ef3  setnz   bl
0x180002ef6  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x180002efa  call    cs:__imp_CloseHandle
0x180002f00  test    bl, bl
0x180002f02  jz      loc_180002F89
0x180002f08  mov     rcx, [rbp+57h+Process]; ProcessHandle
0x180002f0c  mov     r8, r14; unsigned __int64
0x180002f0f  mov     edx, r15d; unsigned int
0x180002f12  call    ?AdjustACGProtectionStatus@@YAJPEAXK_K@Z; AdjustACGProtectionStatus(void *,ulong,unsigned __int64)
0x180002f17  mov     ebx, eax
0x180002f19  test    eax, eax
0x180002f1b  jns     short loc_180002F67
0x180002f1d  test    byte ptr cs:Microsoft_Windows_SecurityMitigationsBrokerEnableBits, 8
0x180002f24  jz      loc_180002FD8
0x180002f2a  mov     [rbp+57h+TokenInformation], eax
0x180002f2d  lea     rdx, AdjustACGProtectionStatusFailed
0x180002f34  lea     rax, [rbp+57h+TokenHandle]
0x180002f38  mov     [rbp+57h+var_88], r15d
0x180002f3c  mov     [rbp+57h+var_50], rax
0x180002f40  mov     r9d, 4
0x180002f46  lea     rax, [rbp+57h+var_88]
0x180002f4a  mov     [rbp+57h+var_28], 4
0x180002f52  mov     [rbp+57h+var_40], rax
0x180002f56  lea     rax, [rbp+57h+TokenInformation]
0x180002f5a  mov     [rbp+57h+var_30], rax
0x180002f5e  lea     rax, [rbp+57h+var_60]
0x180002f62  jmp     loc_180002E3B
0x180002f67  test    byte ptr cs:Microsoft_Windows_SecurityMitigationsBrokerEnableBits, 10h
0x180002f6e  jz      short loc_180002FD5
0x180002f70  lea     rax, [rbp+57h+TokenHandle]
0x180002f74  mov     [rbp+57h+var_88], r15d
0x180002f78  mov     [rbp+57h+var_50], rax
0x180002f7c  lea     rdx, AppliedReportedDriverUpdate
0x180002f83  lea     rax, [rbp+57h+var_88]
0x180002f87  jmp     short loc_180002FA9
0x180002f89  test    byte ptr cs:Microsoft_Windows_SecurityMitigationsBrokerEnableBits, 4
0x180002f90  jz      short loc_180002FD5
0x180002f92  lea     rax, [rbp+57h+TokenHandle]
0x180002f96  mov     [rbp+57h+var_88], r15d
0x180002f9a  mov     [rbp+57h+var_50], rax
0x180002f9e  lea     rax, [rbp+57h+var_88]
0x180002fa2  lea     rdx, NonAppContainerProcess
0x180002fa9  mov     [rbp+57h+var_40], rax
0x180002fad  mov     r9d, 3
0x180002fb3  lea     rax, [rbp+57h+var_60]
0x180002fb7  mov     [rbp+57h+TokenHandle], r14
0x180002fbb  mov     [rsp+0C0h+ReturnLength], rax
0x180002fc0  mov     [rbp+57h+var_48], 8
0x180002fc8  mov     [rbp+57h+var_38], 4
0x180002fd0  call    McGenEventWrite_EventWriteTransfer
0x180002fd5  mov     ebx, r12d
0x180002fd8  mov     rcx, [rbp+57h+Process]; hObject
0x180002fdc  test    rcx, rcx
0x180002fdf  jz      short loc_180002FE7
0x180002fe1  call    cs:__imp_CloseHandle
0x180002fe7  test    byte ptr cs:Microsoft_Windows_SecurityMitigationsBrokerEnableBits, 1
0x180002fee  jz      short loc_18000300B
0x180002ff0  lea     rax, [rbp+57h+TokenHandle]
0x180002ff4  mov     r9d, 1
0x180002ffa  lea     rdx, NotifyDisplayDriverUpdateStop
0x180003001  mov     [rsp+0C0h+ReturnLength], rax
0x180003006  call    McGenEventWrite_EventWriteTransfer
0x18000300b  mov     rcx, [rbp+57h+ppInterface]
0x18000300f  test    rcx, rcx
0x180003012  jz      short loc_180003024
0x180003014  mov     [rbp+57h+ppInterface], r12
0x180003018  mov     rax, [rcx]
0x18000301b  mov     rax, [rax+10h]
0x18000301f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003024  mov     eax, ebx
0x180003026  mov     rcx, [rbp+57h+var_20]
0x18000302a  xor     rcx, rsp; StackCookie
0x18000302d  call    __security_check_cookie
0x180003032  lea     r11, [rsp+0C0h+var_10]
0x18000303a  mov     rbx, [r11+20h]
0x18000303e  mov     r12, [r11+30h]
0x180003042  mov     rsp, r11
0x180003045  pop     r15
0x180003047  pop     r14
0x180003049  pop     rbp
0x18000304a  retn
```
