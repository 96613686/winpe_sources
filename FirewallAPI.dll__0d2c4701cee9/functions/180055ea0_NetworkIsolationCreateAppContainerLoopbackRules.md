# NetworkIsolationCreateAppContainerLoopbackRules

- ea: `0x180055ea0`
- end: `0x18005625c`
- name: `NetworkIsolationCreateAppContainerLoopbackRules`
- size: `956`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180005e0c`
- `0x18000ea10`
- `0x180026798`
- `0x1800294b0`
- `0x180055ea0`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18005612d`
- `RPCRT4!NdrClientCall3` at `0x18005612d`
- `RPCRT4!RpcBindingFree` at `0x1800561eb`
- `RPCRT4!RpcBindingFree` at `0x1800561eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055f7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005603c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055f7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005603c`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18005602c`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18005602c`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800561a4`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800561a4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180055f11`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180055f11`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180055f65`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180055f65`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180055f4b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180055f4b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180055f33`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180055f33`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180055f05`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180055f05`
- `fwbase!FwBaseFree` at `0x1800561cc`
- `fwbase!FwBaseFree` at `0x1800561cc`
- `fwbase!FwCloseHandle` at `0x1800561b8`
- `fwbase!FwCloseHandle` at `0x1800561b8`
- `fwbase!FwHResultToWindowsError` at `0x180055fed`
- `fwbase!FwHResultToWindowsError` at `0x180055fed`
- `fwbase!FwGetTokenInformation` at `0x180055fdf`
- `fwbase!FwGetTokenInformation` at `0x180055fdf`

## pseudocode

```c
__int64 __fastcall NetworkIsolationCreateAppContainerLoopbackRules(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int a7)
{
  int v9; // r12d
  HANDLE CurrentThread; // rax
  BOOL v11; // eax
  int v12; // r15d
  HANDLE CurrentProcess; // rax
  DWORD LastError; // eax
  DWORD v15; // ebx
  FwPolicy2 *v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // r9
  unsigned int TokenInformation; // eax
  unsigned int Pointer; // eax
  unsigned int v21; // eax
  __int64 v22; // rcx
  __int64 v24; // [rsp+60h] [rbp-88h]
  void *TokenHandle; // [rsp+90h] [rbp-58h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+98h] [rbp-50h] BYREF
  _QWORD *v29; // [rsp+A0h] [rbp-48h] BYREF

  Binding = 0;
  v29 = 0;
  TokenHandle = 0;
  v9 = 0;
  HIDWORD(v24) = 0;
  GetTickCount64();
  CurrentThread = GetCurrentThread();
  v11 = OpenThreadToken(CurrentThread, 0xCu, 1, &TokenHandle);
  if ( v11 )
  {
    v12 = 1;
    LODWORD(v24) = 1;
  }
  else
  {
    v12 = 0;
    LODWORD(v24) = 0;
    CurrentProcess = GetCurrentProcess();
    v11 = OpenProcessToken(CurrentProcess, 8u, &TokenHandle);
  }
  if ( v11 )
  {
    TokenInformation = FwGetTokenInformation(TokenHandle, 1, &v29, 0);
    LastError = FwHResultToWindowsError(TokenInformation);
    v15 = LastError;
    if ( !LastError )
    {
      if ( v12 == 1 )
      {
        if ( !RevertToSelf() )
        {
          LastError = GetLastError();
          v15 = LastError;
          v16 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v17 = 612;
            goto LABEL_8;
          }
          goto LABEL_28;
        }
        v9 = 1;
        HIDWORD(v24) = 1;
      }
      LastError = Int_FWLocalRpcBindingCreate(&Binding);
      v15 = LastError;
      if ( LastError )
      {
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v17 = 613;
          goto LABEL_8;
        }
      }
      else
      {
        Pointer = (unsigned int)NdrClientCall3(
                                  (MIDL_STUBLESS_PROXY_INFO *)&FW_NET_ISO_DIAG_ProxyInfo,
                                  9u,
                                  0,
                                  Binding,
                                  *v29,
                                  a1,
                                  a2,
                                  a3,
                                  a4,
                                  a5,
                                  a6,
                                  a7,
                                  v24).Pointer;
        v15 = Pointer;
        if ( Pointer )
        {
          v16 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v17 = 614;
            v18 = Pointer;
            goto LABEL_9;
          }
        }
      }
      goto LABEL_28;
    }
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v17 = 611;
      goto LABEL_8;
    }
  }
  else
  {
    LastError = GetLastError();
    v15 = LastError;
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v17 = 610;
LABEL_8:
      v18 = LastError;
LABEL_9:
      WPP_SF_d(*((_QWORD *)v16 + 2), v17, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, v18);
    }
  }
LABEL_28:
  if ( v12 == 1 && v9 == 1 )
    SetThreadToken(0, TokenHandle);
  FwCloseHandle(TokenHandle);
  FwBaseFree(v29);
  if ( Binding )
  {
    v21 = RpcBindingFree(&Binding);
    if ( v21 )
      MicrosoftTelemetryAssertTriggeredArgs(v22, v21);
    Binding = 0;
  }
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 615, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, v15);
  return v15;
}

```

## disassembly

```asm
0x180055ea0  mov     r11, rsp
0x180055ea3  push    rbx
0x180055ea4  push    rsi
0x180055ea5  push    rdi
0x180055ea6  push    r12
0x180055ea8  push    r13
0x180055eaa  push    r15
0x180055eac  sub     rsp, 0B8h
0x180055eb3  mov     rax, cs:__security_cookie
0x180055eba  xor     rax, rsp
0x180055ebd  mov     [rsp+0E8h+var_40], rax
0x180055ec5  mov     [rsp+0E8h+var_70], r9
0x180055eca  mov     [rsp+0E8h+var_68], r8
0x180055ed2  mov     r13, rdx
0x180055ed5  mov     rdi, rcx
0x180055ed8  mov     rax, [rsp+0E8h+arg_28]
0x180055ee0  mov     [rsp+0E8h+var_78], rax
0x180055ee5  mov     qword ptr [r11-50h], 0
0x180055eed  mov     qword ptr [r11-48h], 0
0x180055ef5  mov     qword ptr [r11-58h], 0
0x180055efd  xor     r12d, r12d
0x180055f00  mov     [rsp+0E8h+var_84], r12d
0x180055f05  call    cs:__imp_GetTickCount64
0x180055f0c  nop     dword ptr [rax+rax+00h]
0x180055f11  call    cs:__imp_GetCurrentThread
0x180055f18  nop     dword ptr [rax+rax+00h]
0x180055f1d  mov     rcx, rax; ThreadHandle
0x180055f20  lea     r9, [rsp+0E8h+TokenHandle]; TokenHandle
0x180055f28  lea     esi, [r12+1]
0x180055f2d  mov     r8d, esi; OpenAsSelf
0x180055f30  lea     edx, [rsi+0Bh]; DesiredAccess
0x180055f33  call    cs:__imp_OpenThreadToken
0x180055f3a  nop     dword ptr [rax+rax+00h]
0x180055f3f  test    eax, eax
0x180055f41  jnz     short loc_180055F73
0x180055f43  xor     r15d, r15d
0x180055f46  mov     [rsp+0E8h+var_88], r15d
0x180055f4b  call    cs:__imp_GetCurrentProcess
0x180055f52  nop     dword ptr [rax+rax+00h]
0x180055f57  mov     rcx, rax; ProcessHandle
0x180055f5a  lea     r8, [rsp+0E8h+TokenHandle]; TokenHandle
0x180055f62  lea     edx, [rsi+7]; DesiredAccess
0x180055f65  call    cs:__imp_OpenProcessToken
0x180055f6c  nop     dword ptr [rax+rax+00h]
0x180055f71  jmp     short loc_180055F7A
0x180055f73  mov     r15d, esi
0x180055f76  mov     [rsp+0E8h+var_88], esi
0x180055f7a  test    eax, eax
0x180055f7c  jnz     short loc_180055FCA
0x180055f7e  call    cs:__imp_GetLastError
0x180055f85  nop     dword ptr [rax+rax+00h]
0x180055f8a  mov     ebx, eax
0x180055f8c  lea     rdi, WPP_GLOBAL_Control
0x180055f93  mov     rcx, cs:WPP_GLOBAL_Control
0x180055f9a  cmp     rcx, rdi
0x180055f9d  jz      loc_180056190
0x180055fa3  test    [rcx+1Ch], sil
0x180055fa7  jz      loc_180056190
0x180055fad  mov     edx, 262h
0x180055fb2  mov     r9d, eax
0x180055fb5  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x180055fbc  mov     rcx, [rcx+10h]
0x180055fc0  call    WPP_SF_d
0x180055fc5  jmp     loc_180056190
0x180055fca  xor     r9d, r9d
0x180055fcd  lea     r8, [rsp+0E8h+var_48]
0x180055fd5  mov     edx, esi
0x180055fd7  mov     rcx, [rsp+0E8h+TokenHandle]
0x180055fdf  call    cs:__imp_FwGetTokenInformation
0x180055fe6  nop     dword ptr [rax+rax+00h]
0x180055feb  mov     ecx, eax
0x180055fed  call    cs:__imp_FwHResultToWindowsError
0x180055ff4  nop     dword ptr [rax+rax+00h]
0x180055ff9  mov     ebx, eax
0x180055ffb  test    eax, eax
0x180055ffd  jz      short loc_180056027
0x180055fff  lea     rdi, WPP_GLOBAL_Control
0x180056006  mov     rcx, cs:WPP_GLOBAL_Control
0x18005600d  cmp     rcx, rdi
0x180056010  jz      loc_180056190
0x180056016  test    [rcx+1Ch], sil
0x18005601a  jz      loc_180056190
0x180056020  mov     edx, 263h
0x180056025  jmp     short loc_180055FB2
0x180056027  cmp     r15d, esi
0x18005602a  jnz     short loc_18005607C
0x18005602c  call    cs:__imp_RevertToSelf
0x180056033  nop     dword ptr [rax+rax+00h]
0x180056038  test    eax, eax
0x18005603a  jnz     short loc_180056075
0x18005603c  call    cs:__imp_GetLastError
0x180056043  nop     dword ptr [rax+rax+00h]
0x180056048  mov     ebx, eax
0x18005604a  lea     rdi, WPP_GLOBAL_Control
0x180056051  mov     rcx, cs:WPP_GLOBAL_Control
0x180056058  cmp     rcx, rdi
0x18005605b  jz      loc_180056190
0x180056061  test    [rcx+1Ch], sil
0x180056065  jz      loc_180056190
0x18005606b  mov     edx, 264h
0x180056070  jmp     loc_180055FB2
0x180056075  mov     r12d, esi
0x180056078  mov     [rsp+0E8h+var_84], esi
0x18005607c  lea     rcx, [rsp+0E8h+Binding]
0x180056084  call    Int_FWLocalRpcBindingCreate
0x180056089  mov     ebx, eax
0x18005608b  test    eax, eax
0x18005608d  jz      short loc_1800560BA
0x18005608f  lea     rdi, WPP_GLOBAL_Control
0x180056096  mov     rcx, cs:WPP_GLOBAL_Control
0x18005609d  cmp     rcx, rdi
0x1800560a0  jz      loc_180056190
0x1800560a6  test    [rcx+1Ch], sil
0x1800560aa  jz      loc_180056190
0x1800560b0  mov     edx, 265h
0x1800560b5  jmp     loc_180055FB2
0x1800560ba  mov     rax, [rsp+0E8h+var_48]
0x1800560c2  mov     rcx, [rax]
0x1800560c5  mov     [rsp+0E8h+var_60], 0
0x1800560d1  mov     eax, [rsp+0E8h+arg_30]
0x1800560d8  mov     [rsp+0E8h+var_90], eax
0x1800560dc  mov     rax, [rsp+0E8h+var_78]
0x1800560e1  mov     [rsp+0E8h+var_98], rax
0x1800560e6  mov     eax, [rsp+0E8h+arg_20]
0x1800560ed  mov     [rsp+0E8h+var_A0], eax
0x1800560f1  mov     rax, [rsp+0E8h+var_70]
0x1800560f6  mov     [rsp+0E8h+var_A8], rax
0x1800560fb  mov     rax, [rsp+0E8h+var_68]
0x180056103  mov     [rsp+0E8h+var_B0], rax
0x180056108  mov     [rsp+0E8h+var_B8], r13
0x18005610d  mov     [rsp+0E8h+var_C0], rdi
0x180056112  mov     [rsp+0E8h+var_C8], rcx
0x180056117  mov     r9, [rsp+0E8h+Binding]
0x18005611f  xor     r8d, r8d; pReturnValue
0x180056122  lea     edx, [r8+9]; nProcNum
0x180056126  lea     rcx, ?FW_NET_ISO_DIAG_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18005612d  call    cs:__imp_NdrClientCall3
0x180056134  nop     dword ptr [rax+rax+00h]
0x180056139  mov     rbx, rax
0x18005613c  mov     [rsp+0E8h+var_60], rax
0x180056144  mov     [rsp+0E8h+var_80], eax
0x180056148  jmp     short loc_18005615F
0x18005614a  mov     ebx, eax
0x18005614c  mov     [rsp+0E8h+var_80], eax
0x180056150  mov     esi, 1
0x180056155  mov     r15d, [rsp+0E8h+var_88]
0x18005615a  mov     r12d, [rsp+0E8h+var_84]
0x18005615f  test    ebx, ebx
0x180056161  jz      short loc_180056189
0x180056163  lea     rdi, WPP_GLOBAL_Control
0x18005616a  mov     rcx, cs:WPP_GLOBAL_Control
0x180056171  cmp     rcx, rdi
0x180056174  jz      short loc_180056190
0x180056176  test    [rcx+1Ch], sil
0x18005617a  jz      short loc_180056190
0x18005617c  mov     edx, 266h
0x180056181  mov     r9d, ebx
0x180056184  jmp     loc_180055FB5
0x180056189  lea     rdi, WPP_GLOBAL_Control
0x180056190  cmp     r15d, esi
0x180056193  jnz     short loc_1800561B0
0x180056195  cmp     r12d, esi
0x180056198  jnz     short loc_1800561B0
0x18005619a  mov     rdx, [rsp+0E8h+TokenHandle]; Token
0x1800561a2  xor     ecx, ecx; Thread
0x1800561a4  call    cs:__imp_SetThreadToken
0x1800561ab  nop     dword ptr [rax+rax+00h]
0x1800561b0  mov     rcx, [rsp+0E8h+TokenHandle]
0x1800561b8  call    cs:__imp_FwCloseHandle
0x1800561bf  nop     dword ptr [rax+rax+00h]
0x1800561c4  mov     rcx, [rsp+0E8h+var_48]
0x1800561cc  call    cs:__imp_FwBaseFree
0x1800561d3  nop     dword ptr [rax+rax+00h]
0x1800561d8  cmp     [rsp+0E8h+Binding], 0
0x1800561e1  jz      short loc_18005620E
0x1800561e3  lea     rcx, [rsp+0E8h+Binding]; Binding
0x1800561eb  call    cs:__imp_RpcBindingFree
0x1800561f2  nop     dword ptr [rax+rax+00h]
0x1800561f7  test    eax, eax
0x1800561f9  jz      short loc_180056202
0x1800561fb  mov     edx, eax; __annotation("Debug", "TelemetryAssert", "status == RPC_S_OK", "RpcBindingFree")
0x1800561fd  call    MicrosoftTelemetryAssertTriggeredArgs
0x180056202  mov     [rsp+0E8h+Binding], 0
0x18005620e  mov     rcx, cs:WPP_GLOBAL_Control
0x180056215  cmp     rcx, rdi
0x180056218  jz      short loc_180056238
0x18005621a  test    byte ptr [rcx+1Ch], 8
0x18005621e  jz      short loc_180056238
0x180056220  mov     edx, 267h
0x180056225  mov     r9d, ebx
0x180056228  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x18005622f  mov     rcx, [rcx+10h]
0x180056233  call    WPP_SF_d
0x180056238  mov     eax, ebx
0x18005623a  mov     rcx, [rsp+0E8h+var_40]
0x180056242  xor     rcx, rsp; StackCookie
0x180056245  call    __security_check_cookie
0x18005624a  add     rsp, 0B8h
0x180056251  pop     r15
0x180056253  pop     r13
0x180056255  pop     r12
0x180056257  pop     rdi
0x180056258  pop     rsi
0x180056259  pop     rbx
0x18005625a  retn
0x180060408  push    rbp
0x18006040a  sub     rsp, 60h
0x18006040e  mov     rbp, rdx
0x180060411  mov     rcx, [rcx]
0x180060414  mov     ecx, [rcx]; ExceptionCode
0x180060416  call    cs:__imp_RpcExceptionFilter
0x18006041d  nop     dword ptr [rax+rax+00h]
0x180060422  nop
0x180060423  add     rsp, 60h
0x180060427  pop     rbp
0x180060428  retn
```
