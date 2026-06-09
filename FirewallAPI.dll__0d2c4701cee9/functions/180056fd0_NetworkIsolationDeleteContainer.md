# NetworkIsolationDeleteContainer

- ea: `0x180056fd0`
- end: `0x180057355`
- name: `NetworkIsolationDeleteContainer`
- size: `901`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180005e0c`
- `0x18000ea10`
- `0x180026798`
- `0x1800294b0`
- `0x18003336c`
- `0x180056fd0`
- `0x180058980`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180057232`
- `RPCRT4!NdrClientCall3` at `0x180057232`
- `RPCRT4!RpcBindingFree` at `0x1800572e2`
- `RPCRT4!RpcBindingFree` at `0x1800572e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800570f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005718f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800570f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005718f`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18005717f`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18005717f`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800572a7`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800572a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005708e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005708e`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800570dc`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800570dc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800570c5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800570c5`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800570ad`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800570ad`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18005704e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18005704e`
- `fwbase!FwBaseFree` at `0x1800572c9`
- `fwbase!FwBaseFree` at `0x1800572c9`
- `fwbase!FwCloseHandle` at `0x1800572b8`
- `fwbase!FwCloseHandle` at `0x1800572b8`
- `fwbase!FwHResultToWindowsError` at `0x180057147`
- `fwbase!FwHResultToWindowsError` at `0x180057147`
- `fwbase!FwGetTokenInformation` at `0x180057139`
- `fwbase!FwGetTokenInformation` at `0x180057139`

## pseudocode

```c
__int64 __fastcall NetworkIsolationDeleteContainer(int a1, const wchar_t *a2)
{
  int v4; // r12d
  int v5; // r8d
  const wchar_t *v6; // rax
  HANDLE CurrentThread; // rax
  BOOL v8; // eax
  int v9; // r15d
  HANDLE CurrentProcess; // rax
  DWORD LastError; // eax
  DWORD v12; // ebx
  FwPolicy2 *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // r9
  unsigned int TokenInformation; // eax
  unsigned int Pointer; // eax
  unsigned int v18; // eax
  __int64 v19; // rcx
  void *TokenHandle; // [rsp+58h] [rbp-50h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+60h] [rbp-48h] BYREF
  _QWORD *v24; // [rsp+68h] [rbp-40h] BYREF

  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 602, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids);
  Binding = 0;
  v24 = 0;
  TokenHandle = 0;
  v4 = 0;
  GetTickCount64();
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    v6 = a2;
    if ( !a2 )
      v6 = L"<null>";
    WPP_SF_DS(*((_QWORD *)WPP_GLOBAL_Control + 2), (unsigned int)L"<null>", v5, a1, (__int64)v6);
  }
  CurrentThread = GetCurrentThread();
  v8 = OpenThreadToken(CurrentThread, 0xCu, 1, &TokenHandle);
  if ( v8 )
  {
    v9 = 1;
  }
  else
  {
    v9 = 0;
    CurrentProcess = GetCurrentProcess();
    v8 = OpenProcessToken(CurrentProcess, 8u, &TokenHandle);
  }
  if ( v8 )
  {
    TokenInformation = FwGetTokenInformation(TokenHandle, 1, &v24, 0);
    LastError = FwHResultToWindowsError(TokenInformation);
    v12 = LastError;
    if ( !LastError )
    {
      if ( v9 == 1 )
      {
        if ( !RevertToSelf() )
        {
          LastError = GetLastError();
          v12 = LastError;
          v13 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v14 = 606;
            goto LABEL_16;
          }
          goto LABEL_36;
        }
        v4 = 1;
      }
      LastError = Int_FWLocalRpcBindingCreate(&Binding);
      v12 = LastError;
      if ( LastError )
      {
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v14 = 607;
          goto LABEL_16;
        }
      }
      else
      {
        Pointer = (unsigned int)NdrClientCall3(
                                  (MIDL_STUBLESS_PROXY_INFO *)&FW_NET_ISO_DIAG_ProxyInfo,
                                  3u,
                                  0,
                                  Binding,
                                  *v24,
                                  a1,
                                  a2).Pointer;
        v12 = Pointer;
        if ( Pointer )
        {
          v13 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v14 = 608;
            v15 = Pointer;
            goto LABEL_35;
          }
        }
      }
      goto LABEL_36;
    }
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v14 = 605;
      goto LABEL_16;
    }
  }
  else
  {
    LastError = GetLastError();
    v12 = LastError;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v14 = 604;
LABEL_16:
      v15 = LastError;
LABEL_35:
      WPP_SF_d(*((_QWORD *)v13 + 2), v14, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, v15);
    }
  }
LABEL_36:
  if ( v9 == 1 && v4 == 1 )
    SetThreadToken(0, TokenHandle);
  FwCloseHandle(TokenHandle);
  FwBaseFree(v24);
  if ( Binding )
  {
    v18 = RpcBindingFree(&Binding);
    if ( v18 )
      MicrosoftTelemetryAssertTriggeredArgs(v19, v18);
    Binding = 0;
  }
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 609, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, v12);
  return v12;
}

```

## disassembly

```asm
0x180056fd0  mov     [rsp+arg_10], rbx
0x180056fd5  push    rsi
0x180056fd6  push    r12
0x180056fd8  push    r13
0x180056fda  push    r14
0x180056fdc  push    r15
0x180056fde  sub     rsp, 80h
0x180056fe5  mov     rax, cs:__security_cookie
0x180056fec  xor     rax, rsp
0x180056fef  mov     [rsp+0A8h+var_38], rax
0x180056ff4  mov     r13, rdx
0x180056ff7  mov     ebx, ecx
0x180056ff9  mov     [rsp+0A8h+var_60], ecx
0x180056ffd  lea     r14, WPP_GLOBAL_Control
0x180057004  mov     rcx, cs:WPP_GLOBAL_Control
0x18005700b  cmp     rcx, r14
0x18005700e  jz      short loc_18005702B
0x180057010  test    byte ptr [rcx+1Ch], 8
0x180057014  jz      short loc_18005702B
0x180057016  mov     edx, 25Ah
0x18005701b  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x180057022  mov     rcx, [rcx+10h]
0x180057026  call    WPP_SF_
0x18005702b  mov     [rsp+0A8h+Binding], 0
0x180057034  mov     [rsp+0A8h+var_40], 0
0x18005703d  mov     [rsp+0A8h+TokenHandle], 0
0x180057046  xor     r12d, r12d
0x180057049  mov     [rsp+0A8h+var_64], r12d
0x18005704e  call    cs:__imp_GetTickCount64
0x180057055  nop     dword ptr [rax+rax+00h]
0x18005705a  mov     rcx, cs:WPP_GLOBAL_Control
0x180057061  cmp     rcx, r14
0x180057064  jz      short loc_18005708E
0x180057066  test    byte ptr [rcx+1Ch], 4
0x18005706a  jz      short loc_18005708E
0x18005706c  lea     rdx, aNull; "<null>"
0x180057073  mov     rax, r13
0x180057076  test    r13, r13
0x180057079  cmovz   rax, rdx
0x18005707d  mov     [rsp+0A8h+var_88], rax
0x180057082  mov     r9d, ebx
0x180057085  mov     rcx, [rcx+10h]
0x180057089  call    WPP_SF_DS
0x18005708e  call    cs:__imp_GetCurrentThread
0x180057095  nop     dword ptr [rax+rax+00h]
0x18005709a  mov     rcx, rax; ThreadHandle
0x18005709d  lea     r9, [rsp+0A8h+TokenHandle]; TokenHandle
0x1800570a2  mov     esi, 1
0x1800570a7  mov     r8d, esi; OpenAsSelf
0x1800570aa  lea     edx, [rsi+0Bh]; DesiredAccess
0x1800570ad  call    cs:__imp_OpenThreadToken
0x1800570b4  nop     dword ptr [rax+rax+00h]
0x1800570b9  test    eax, eax
0x1800570bb  jnz     short loc_1800570EA
0x1800570bd  xor     r15d, r15d
0x1800570c0  mov     [rsp+0A8h+var_68], r15d
0x1800570c5  call    cs:__imp_GetCurrentProcess
0x1800570cc  nop     dword ptr [rax+rax+00h]
0x1800570d1  mov     rcx, rax; ProcessHandle
0x1800570d4  lea     r8, [rsp+0A8h+TokenHandle]; TokenHandle
0x1800570d9  lea     edx, [rsi+7]; DesiredAccess
0x1800570dc  call    cs:__imp_OpenProcessToken
0x1800570e3  nop     dword ptr [rax+rax+00h]
0x1800570e8  jmp     short loc_1800570F1
0x1800570ea  mov     r15d, esi
0x1800570ed  mov     [rsp+0A8h+var_68], esi
0x1800570f1  test    eax, eax
0x1800570f3  jnz     short loc_18005712A
0x1800570f5  call    cs:__imp_GetLastError
0x1800570fc  nop     dword ptr [rax+rax+00h]
0x180057101  mov     ebx, eax
0x180057103  mov     rcx, cs:WPP_GLOBAL_Control
0x18005710a  cmp     rcx, r14
0x18005710d  jz      loc_180057296
0x180057113  test    [rcx+1Ch], sil
0x180057117  jz      loc_180057296
0x18005711d  mov     edx, 25Ch
0x180057122  mov     r9d, eax
0x180057125  jmp     loc_180057286
0x18005712a  xor     r9d, r9d
0x18005712d  lea     r8, [rsp+0A8h+var_40]
0x180057132  mov     edx, esi
0x180057134  mov     rcx, [rsp+0A8h+TokenHandle]
0x180057139  call    cs:__imp_FwGetTokenInformation
0x180057140  nop     dword ptr [rax+rax+00h]
0x180057145  mov     ecx, eax
0x180057147  call    cs:__imp_FwHResultToWindowsError
0x18005714e  nop     dword ptr [rax+rax+00h]
0x180057153  mov     ebx, eax
0x180057155  test    eax, eax
0x180057157  jz      short loc_18005717A
0x180057159  mov     rcx, cs:WPP_GLOBAL_Control
0x180057160  cmp     rcx, r14
0x180057163  jz      loc_180057296
0x180057169  test    [rcx+1Ch], sil
0x18005716d  jz      loc_180057296
0x180057173  mov     edx, 25Dh
0x180057178  jmp     short loc_180057122
0x18005717a  cmp     r15d, esi
0x18005717d  jnz     short loc_1800571C8
0x18005717f  call    cs:__imp_RevertToSelf
0x180057186  nop     dword ptr [rax+rax+00h]
0x18005718b  test    eax, eax
0x18005718d  jnz     short loc_1800571C1
0x18005718f  call    cs:__imp_GetLastError
0x180057196  nop     dword ptr [rax+rax+00h]
0x18005719b  mov     ebx, eax
0x18005719d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800571a4  cmp     rcx, r14
0x1800571a7  jz      loc_180057296
0x1800571ad  test    [rcx+1Ch], sil
0x1800571b1  jz      loc_180057296
0x1800571b7  mov     edx, 25Eh
0x1800571bc  jmp     loc_180057122
0x1800571c1  mov     r12d, esi
0x1800571c4  mov     [rsp+0A8h+var_64], esi
0x1800571c8  lea     rcx, [rsp+0A8h+Binding]
0x1800571cd  call    Int_FWLocalRpcBindingCreate
0x1800571d2  mov     ebx, eax
0x1800571d4  test    eax, eax
0x1800571d6  jz      short loc_1800571FC
0x1800571d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800571df  cmp     rcx, r14
0x1800571e2  jz      loc_180057296
0x1800571e8  test    [rcx+1Ch], sil
0x1800571ec  jz      loc_180057296
0x1800571f2  mov     edx, 25Fh
0x1800571f7  jmp     loc_180057122
0x1800571fc  mov     rax, [rsp+0A8h+var_40]
0x180057201  mov     rcx, [rax]
0x180057204  mov     [rsp+0A8h+var_58], 0
0x18005720d  mov     [rsp+0A8h+var_78], r13
0x180057212  mov     eax, [rsp+0A8h+var_60]
0x180057216  mov     [rsp+0A8h+var_80], eax
0x18005721a  mov     [rsp+0A8h+var_88], rcx
0x18005721f  mov     r9, [rsp+0A8h+Binding]
0x180057224  xor     r8d, r8d; pReturnValue
0x180057227  lea     edx, [r8+3]; nProcNum
0x18005722b  lea     rcx, ?FW_NET_ISO_DIAG_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180057232  call    cs:__imp_NdrClientCall3
0x180057239  nop     dword ptr [rax+rax+00h]
0x18005723e  mov     rbx, rax
0x180057241  mov     [rsp+0A8h+var_58], rax
0x180057246  mov     [rsp+0A8h+var_5C], eax
0x18005724a  jmp     short loc_180057268
0x18005724c  mov     ebx, eax
0x18005724e  mov     [rsp+0A8h+var_5C], eax
0x180057252  lea     r14, WPP_GLOBAL_Control
0x180057259  mov     esi, 1
0x18005725e  mov     r15d, [rsp+0A8h+var_68]
0x180057263  mov     r12d, [rsp+0A8h+var_64]
0x180057268  test    ebx, ebx
0x18005726a  jz      short loc_180057296
0x18005726c  mov     rcx, cs:WPP_GLOBAL_Control
0x180057273  cmp     rcx, r14
0x180057276  jz      short loc_180057296
0x180057278  test    [rcx+1Ch], sil
0x18005727c  jz      short loc_180057296
0x18005727e  mov     edx, 260h
0x180057283  mov     r9d, ebx
0x180057286  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x18005728d  mov     rcx, [rcx+10h]
0x180057291  call    WPP_SF_d
0x180057296  cmp     r15d, esi
0x180057299  jnz     short loc_1800572B3
0x18005729b  cmp     r12d, esi
0x18005729e  jnz     short loc_1800572B3
0x1800572a0  mov     rdx, [rsp+0A8h+TokenHandle]; Token
0x1800572a5  xor     ecx, ecx; Thread
0x1800572a7  call    cs:__imp_SetThreadToken
0x1800572ae  nop     dword ptr [rax+rax+00h]
0x1800572b3  mov     rcx, [rsp+0A8h+TokenHandle]
0x1800572b8  call    cs:__imp_FwCloseHandle
0x1800572bf  nop     dword ptr [rax+rax+00h]
0x1800572c4  mov     rcx, [rsp+0A8h+var_40]
0x1800572c9  call    cs:__imp_FwBaseFree
0x1800572d0  nop     dword ptr [rax+rax+00h]
0x1800572d5  cmp     [rsp+0A8h+Binding], 0
0x1800572db  jz      short loc_180057302
0x1800572dd  lea     rcx, [rsp+0A8h+Binding]; Binding
0x1800572e2  call    cs:__imp_RpcBindingFree
0x1800572e9  nop     dword ptr [rax+rax+00h]
0x1800572ee  test    eax, eax
0x1800572f0  jz      short loc_1800572F9
0x1800572f2  mov     edx, eax; __annotation("Debug", "TelemetryAssert", "status == RPC_S_OK", "RpcBindingFree")
0x1800572f4  call    MicrosoftTelemetryAssertTriggeredArgs
0x1800572f9  mov     [rsp+0A8h+Binding], 0
0x180057302  mov     rcx, cs:WPP_GLOBAL_Control
0x180057309  cmp     rcx, r14
0x18005730c  jz      short loc_18005732C
0x18005730e  test    byte ptr [rcx+1Ch], 8
0x180057312  jz      short loc_18005732C
0x180057314  mov     edx, 261h
0x180057319  mov     r9d, ebx
0x18005731c  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x180057323  mov     rcx, [rcx+10h]
0x180057327  call    WPP_SF_d
0x18005732c  mov     eax, ebx
0x18005732e  mov     rcx, [rsp+0A8h+var_38]
0x180057333  xor     rcx, rsp; StackCookie
0x180057336  call    __security_check_cookie
0x18005733b  mov     rbx, [rsp+0A8h+arg_10]
0x180057343  add     rsp, 80h
0x18005734a  pop     r15
0x18005734c  pop     r14
0x18005734e  pop     r13
0x180057350  pop     r12
0x180057352  pop     rsi
0x180057353  retn
0x18005fda6  push    rbp
0x18005fda8  sub     rsp, 40h
0x18005fdac  mov     rbp, rdx
0x18005fdaf  mov     rcx, [rcx]
0x18005fdb2  mov     ecx, [rcx]; ExceptionCode
0x18005fdb4  call    cs:__imp_RpcExceptionFilter
0x18005fdbb  nop     dword ptr [rax+rax+00h]
0x18005fdc0  nop
0x18005fdc1  add     rsp, 40h
0x18005fdc5  pop     rbp
0x18005fdc6  retn
```
