# NetworkIsolationRegisterForAppContainerChanges

- ea: `0x1800580b0`
- end: `0x180058568`
- name: `NetworkIsolationRegisterForAppContainerChanges`
- size: `1208`
- prototype: `DWORD __stdcall(DWORD flags, PAC_CHANGES_CALLBACK_FN callback, PVOID context, HANDLE *registrationObject)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180005e0c`
- `0x18000ea10`
- `0x180026798`
- `0x1800294b0`
- `0x18002a1f4`
- `0x18003336c`
- `0x18004d248`
- `0x1800580b0`
- `0x1800586b0`

## import_xrefs

- `RPCRT4!RpcExceptionFilter` at `0x1800604de`
- `RPCRT4!RpcExceptionFilter` at `0x180060500`
- `RPCRT4!RpcExceptionFilter` at `0x1800604de`
- `RPCRT4!RpcExceptionFilter` at `0x180060500`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18005843d`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18005843d`
- `RPCRT4!NdrClientCall3` at `0x18005833d`
- `RPCRT4!NdrClientCall3` at `0x18005833d`
- `RPCRT4!RpcBindingFree` at `0x1800584d5`
- `RPCRT4!RpcBindingFree` at `0x1800584d5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180058226`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180058226`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800582a8`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800582a8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180058306`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180058306`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180058123`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180058123`
- `fwbase!FwBaseAlloc` at `0x180058136`
- `fwbase!FwBaseAlloc` at `0x180058136`

## pseudocode

```c
DWORD __stdcall NetworkIsolationRegisterForAppContainerChanges(
        DWORD flags,
        PAC_CHANGES_CALLBACK_FN callback,
        PVOID context,
        HANDLE *registrationObject)
{
  RPC_BINDING_HANDLE *v6; // rax
  RPC_BINDING_HANDLE *v7; // rdi
  __int64 v8; // r9
  DWORD v9; // ebx
  FwPolicy2 *v10; // rcx
  __int64 v11; // rdx
  unsigned int inited; // eax
  HANDLE EventW; // rax
  struct _TP_WAIT *ThreadpoolWait; // rax
  unsigned int Pointer; // eax
  unsigned int v16; // eax
  __int64 v17; // rcx
  RPC_BINDING_HANDLE Binding; // [rsp+80h] [rbp-38h] BYREF

  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 482, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids);
  Binding = 0;
  GetTickCount64();
  v6 = (RPC_BINDING_HANDLE *)FwBaseAlloc(192);
  v7 = v6;
  if ( v6 )
  {
    memset_0(v6, 0, 0xC0u);
    inited = Int_FWLocalRpcBindingCreate(&Binding);
    v9 = inited;
    if ( inited )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_33;
      v11 = 484;
    }
    else
    {
      *v7 = Binding;
      Binding = 0;
      v7[16] = callback;
      v7[17] = context;
      *((_DWORD *)v7 + 44) = 1;
      _InterlockedExchange((volatile __int32 *)v7 + 45, 0);
      _InterlockedExchange((volatile __int32 *)v7 + 46, 0);
      EventW = CreateEventW(0, 0, 0, 0);
      v7[18] = EventW;
      if ( !EventW )
      {
        v8 = 14;
        v9 = 14;
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v11 = 485;
          goto LABEL_8;
        }
        goto LABEL_33;
      }
      inited = Int_NetworkIsolationInitRegistrationRpcAsync((struct FW_INTCLIENT_REG_HANDLE_ *)v7);
      v9 = inited;
      if ( !inited )
      {
        ThreadpoolWait = CreateThreadpoolWait(Int_FwRegistrationCallback, v7, 0);
        v7[19] = ThreadpoolWait;
        if ( ThreadpoolWait )
        {
          SetThreadpoolWait(ThreadpoolWait, v7[7], 0);
          Pointer = (unsigned int)NdrClientCall3(
                                    (MIDL_STUBLESS_PROXY_INFO *)&FW_RESOURCE_INDICATION_ProxyInfo,
                                    8u,
                                    0,
                                    *v7,
                                    flags,
                                    v7 + 20).Pointer;
          v9 = Pointer;
          if ( !Pointer )
          {
            _InterlockedExchange((volatile __int32 *)v7 + 46, 1);
            Ndr64AsyncClientCall(
              (MIDL_STUBLESS_PROXY_INFO *)&FW_RESOURCE_INDICATION_ProxyInfo,
              9u,
              0,
              v7 + 1,
              *v7,
              v7[20],
              v7 + 21);
            _InterlockedIncrement((volatile signed __int32 *)v7 + 44);
            *registrationObject = v7;
            goto LABEL_32;
          }
          v10 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 488, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, Pointer);
            v10 = WPP_GLOBAL_Control;
          }
        }
        else
        {
          v8 = 14;
          v9 = 14;
          v10 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v11 = 487;
            goto LABEL_8;
          }
        }
        goto LABEL_33;
      }
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_33;
      v11 = 486;
    }
    v8 = inited;
    goto LABEL_8;
  }
  v8 = 14;
  v9 = 14;
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v11 = 483;
LABEL_8:
    WPP_SF_d(*((_QWORD *)v10 + 2), v11, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, v8);
LABEL_32:
    v10 = WPP_GLOBAL_Control;
  }
LABEL_33:
  if ( v9 )
  {
    if ( Binding )
    {
      v16 = RpcBindingFree(&Binding);
      if ( v16 )
        MicrosoftTelemetryAssertTriggeredArgs(v17, v16);
      Binding = 0;
      v10 = WPP_GLOBAL_Control;
    }
    if ( v7 )
    {
      _InterlockedExchange((volatile __int32 *)v7 + 46, 0);
      NetworkIsolationUnregisterForAppContainerChanges(v7);
      v10 = WPP_GLOBAL_Control;
    }
  }
  if ( v10 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)v10 + 2), 491, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, v9);
  return v9;
}

```

## disassembly

```asm
0x1800580b0  mov     [rsp+arg_8], rbx
0x1800580b5  mov     [rsp+arg_10], rsi
0x1800580ba  push    rdi
0x1800580bb  push    r12
0x1800580bd  push    r13
0x1800580bf  push    r14
0x1800580c1  push    r15
0x1800580c3  sub     rsp, 90h
0x1800580ca  mov     rax, cs:__security_cookie
0x1800580d1  xor     rax, rsp
0x1800580d4  mov     [rsp+0B8h+var_30], rax
0x1800580dc  mov     r15, r8
0x1800580df  mov     r12, rdx
0x1800580e2  mov     [rsp+0B8h+var_70], ecx
0x1800580e6  mov     [rsp+0B8h+var_40], r9
0x1800580eb  lea     r14, WPP_GLOBAL_Control
0x1800580f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800580f9  cmp     rcx, r14
0x1800580fc  jz      short loc_180058119
0x1800580fe  test    byte ptr [rcx+1Ch], 8
0x180058102  jz      short loc_180058119
0x180058104  mov     edx, 1E2h
0x180058109  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x180058110  mov     rcx, [rcx+10h]
0x180058114  call    WPP_SF_
0x180058119  xor     esi, esi
0x18005811b  mov     [rsp+0B8h+Binding], rsi
0x180058123  call    cs:__imp_GetTickCount64
0x18005812a  nop     dword ptr [rax+rax+00h]
0x18005812f  mov     ebx, 0C0h
0x180058134  mov     ecx, ebx
0x180058136  call    cs:__imp_FwBaseAlloc
0x18005813d  nop     dword ptr [rax+rax+00h]
0x180058142  mov     rdi, rax
0x180058145  mov     [rsp+0B8h+var_78], rax
0x18005814a  test    rax, rax
0x18005814d  jnz     short loc_18005818A
0x18005814f  lea     r9d, [rsi+0Eh]
0x180058153  mov     ebx, r9d
0x180058156  mov     rcx, cs:WPP_GLOBAL_Control
0x18005815d  cmp     rcx, r14
0x180058160  jz      loc_1800584BF
0x180058166  test    byte ptr [rcx+1Ch], 1
0x18005816a  jz      loc_1800584BF
0x180058170  mov     edx, 1E3h
0x180058175  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x18005817c  mov     rcx, [rcx+10h]
0x180058180  call    WPP_SF_d
0x180058185  jmp     loc_1800584B8
0x18005818a  mov     r8, rbx; Size
0x18005818d  xor     edx, edx; Val
0x18005818f  mov     rcx, rdi; void *
0x180058192  call    memset_0
0x180058197  lea     rcx, [rsp+0B8h+Binding]
0x18005819f  call    Int_FWLocalRpcBindingCreate
0x1800581a4  mov     ebx, eax
0x1800581a6  test    eax, eax
0x1800581a8  jz      short loc_1800581CE
0x1800581aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800581b1  cmp     rcx, r14
0x1800581b4  jz      loc_1800584BF
0x1800581ba  test    byte ptr [rcx+1Ch], 1
0x1800581be  jz      loc_1800584BF
0x1800581c4  mov     edx, 1E4h
0x1800581c9  mov     r9d, eax
0x1800581cc  jmp     short loc_180058175
0x1800581ce  mov     rax, [rsp+0B8h+Binding]
0x1800581d6  mov     [rdi], rax
0x1800581d9  mov     [rsp+0B8h+Binding], rsi
0x1800581e1  mov     [rdi+80h], r12
0x1800581e8  mov     [rdi+88h], r15
0x1800581ef  lea     r15, [rdi+0B0h]
0x1800581f6  mov     [rsp+0B8h+var_68], r15
0x1800581fb  mov     dword ptr [r15], 1
0x180058202  mov     eax, esi
0x180058204  xchg    eax, [rdi+0B4h]
0x18005820a  lea     r12, [rdi+0B8h]
0x180058211  mov     [rsp+0B8h+var_50], r12
0x180058216  mov     eax, esi
0x180058218  xchg    eax, [r12]
0x18005821c  xor     r9d, r9d; lpName
0x18005821f  xor     r8d, r8d; bInitialState
0x180058222  xor     edx, edx; bManualReset
0x180058224  xor     ecx, ecx; lpEventAttributes
0x180058226  call    cs:__imp_CreateEventW
0x18005822d  nop     dword ptr [rax+rax+00h]
0x180058232  mov     [rdi+90h], rax
0x180058239  test    rax, rax
0x18005823c  jnz     short loc_180058269
0x18005823e  lea     r9d, [rax+0Eh]
0x180058242  mov     ebx, r9d
0x180058245  mov     rcx, cs:WPP_GLOBAL_Control
0x18005824c  cmp     rcx, r14
0x18005824f  jz      loc_1800584BF
0x180058255  test    byte ptr [rcx+1Ch], 1
0x180058259  jz      loc_1800584BF
0x18005825f  mov     edx, 1E5h
0x180058264  jmp     loc_180058175
0x180058269  mov     rcx, rdi; struct FW_INTCLIENT_REG_HANDLE_ *
0x18005826c  call    ?Int_NetworkIsolationInitRegistrationRpcAsync@@YAKPEAUFW_INTCLIENT_REG_HANDLE_@@@Z; Int_NetworkIsolationInitRegistrationRpcAsync(FW_INTCLIENT_REG_HANDLE_ *)
0x180058271  mov     ebx, eax
0x180058273  test    eax, eax
0x180058275  jz      short loc_18005829B
0x180058277  mov     rcx, cs:WPP_GLOBAL_Control
0x18005827e  cmp     rcx, r14
0x180058281  jz      loc_1800584BF
0x180058287  test    byte ptr [rcx+1Ch], 1
0x18005828b  jz      loc_1800584BF
0x180058291  mov     edx, 1E6h
0x180058296  jmp     loc_1800581C9
0x18005829b  xor     r8d, r8d; pcbe
0x18005829e  mov     rdx, rdi; pv
0x1800582a1  lea     rcx, ?Int_FwRegistrationCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x1800582a8  call    cs:__imp_CreateThreadpoolWait
0x1800582af  nop     dword ptr [rax+rax+00h]
0x1800582b4  mov     [rdi+98h], rax
0x1800582bb  test    rax, rax
0x1800582be  jnz     short loc_1800582EB
0x1800582c0  lea     r9d, [rax+0Eh]
0x1800582c4  mov     ebx, r9d
0x1800582c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800582ce  cmp     rcx, r14
0x1800582d1  jz      loc_1800584BF
0x1800582d7  test    byte ptr [rcx+1Ch], 1
0x1800582db  jz      loc_1800584BF
0x1800582e1  mov     edx, 1E7h
0x1800582e6  jmp     loc_180058175
0x1800582eb  mov     r13, rdi
0x1800582ee  mov     [rsp+0B8h+var_58], rdi
0x1800582f3  lea     rcx, [rdi+8]
0x1800582f7  mov     [rsp+0B8h+var_48], rcx
0x1800582fc  xor     r8d, r8d; pftTimeout
0x1800582ff  mov     rdx, [rcx+30h]; h
0x180058303  mov     rcx, rax; pwa
0x180058306  call    cs:__imp_SetThreadpoolWait
0x18005830d  nop     dword ptr [rax+rax+00h]
0x180058312  nop
0x180058313  mov     [rsp+0B8h+var_60], rsi
0x180058318  lea     rax, [rdi+0A0h]
0x18005831f  mov     [rsp+0B8h+var_90], rax
0x180058324  mov     eax, [rsp+0B8h+var_70]
0x180058328  mov     dword ptr [rsp+0B8h+var_98], eax
0x18005832c  mov     r9, [rdi]
0x18005832f  xor     r8d, r8d; pReturnValue
0x180058332  lea     edx, [r8+8]; nProcNum
0x180058336  lea     rcx, ?FW_RESOURCE_INDICATION_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18005833d  call    cs:__imp_NdrClientCall3
0x180058344  nop     dword ptr [rax+rax+00h]
0x180058349  mov     rbx, rax
0x18005834c  mov     [rsp+0B8h+var_60], rax
0x180058351  mov     [rsp+0B8h+var_6C], eax
0x180058355  test    eax, eax
0x180058357  jz      short loc_18005838F
0x180058359  mov     rcx, cs:WPP_GLOBAL_Control
0x180058360  cmp     rcx, r14
0x180058363  jz      short loc_18005838A
0x180058365  test    byte ptr [rcx+1Ch], 1
0x180058369  jz      short loc_18005838A
0x18005836b  mov     edx, 1E8h
0x180058370  mov     r9d, eax
0x180058373  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x18005837a  mov     rcx, [rcx+10h]
0x18005837e  call    WPP_SF_d
0x180058383  mov     rcx, cs:WPP_GLOBAL_Control
0x18005838a  jmp     loc_1800584BF
0x18005838f  jmp     short loc_180058401
0x180058391  mov     ebx, eax
0x180058393  mov     [rsp+0B8h+var_6C], eax
0x180058397  test    eax, eax
0x180058399  jz      short loc_1800583E6
0x18005839b  lea     rdx, WPP_GLOBAL_Control
0x1800583a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800583a9  cmp     rcx, rdx
0x1800583ac  jz      short loc_1800583D3
0x1800583ae  test    byte ptr [rcx+1Ch], 1
0x1800583b2  jz      short loc_1800583D3
0x1800583b4  mov     edx, 1E9h
0x1800583b9  mov     r9d, eax
0x1800583bc  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x1800583c3  mov     rcx, [rcx+10h]
0x1800583c7  call    WPP_SF_d
0x1800583cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800583d3  lea     r14, WPP_GLOBAL_Control
0x1800583da  xor     esi, esi
0x1800583dc  mov     rdi, [rsp+0B8h+var_78]
0x1800583e1  jmp     loc_1800584BF
0x1800583e6  lea     r14, WPP_GLOBAL_Control
0x1800583ed  xor     esi, esi
0x1800583ef  mov     r13, [rsp+0B8h+var_58]
0x1800583f4  mov     rdi, r13
0x1800583f7  mov     r15, [rsp+0B8h+var_68]
0x1800583fc  mov     r12, [rsp+0B8h+var_50]
0x180058401  mov     eax, 1
0x180058406  xchg    eax, [r12]
0x18005840a  lea     rax, [r13+0A8h]
0x180058411  mov     [rsp+0B8h+var_88], rax
0x180058416  mov     rax, [r13+0A0h]
0x18005841d  mov     [rsp+0B8h+var_90], rax
0x180058422  mov     rax, [rdi]
0x180058425  mov     [rsp+0B8h+var_98], rax
0x18005842a  mov     r9, [rsp+0B8h+var_48]
0x18005842f  xor     r8d, r8d; pReturnValue
0x180058432  lea     edx, [r8+9]; nProcNum
0x180058436  lea     rcx, ?FW_RESOURCE_INDICATION_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18005843d  call    cs:__imp_Ndr64AsyncClientCall
0x180058444  nop     dword ptr [rax+rax+00h]
0x180058449  jmp     short loc_1800584AC
0x18005844b  mov     ebx, eax
0x18005844d  test    eax, eax
0x18005844f  jz      short loc_180058499
0x180058451  lea     rdx, WPP_GLOBAL_Control
0x180058458  mov     rcx, cs:WPP_GLOBAL_Control
0x18005845f  cmp     rcx, rdx
0x180058462  jz      short loc_180058489
0x180058464  test    byte ptr [rcx+1Ch], 1
0x180058468  jz      short loc_180058489
0x18005846a  mov     edx, 1EAh
0x18005846f  mov     r9d, eax
0x180058472  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x180058479  mov     rcx, [rcx+10h]
0x18005847d  call    WPP_SF_d
0x180058482  mov     rcx, cs:WPP_GLOBAL_Control
0x180058489  lea     r14, WPP_GLOBAL_Control
0x180058490  xor     esi, esi
0x180058492  mov     rdi, [rsp+0B8h+var_78]
0x180058497  jmp     short loc_1800584BF
0x180058499  lea     r14, WPP_GLOBAL_Control
0x1800584a0  xor     esi, esi
0x1800584a2  mov     rdi, [rsp+0B8h+var_78]
0x1800584a7  mov     r15, [rsp+0B8h+var_68]
0x1800584ac  lock inc dword ptr [r15]
0x1800584b0  mov     rax, [rsp+0B8h+var_40]
0x1800584b5  mov     [rax], rdi
0x1800584b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800584bf  test    ebx, ebx
0x1800584c1  jz      short loc_180058515
0x1800584c3  cmp     [rsp+0B8h+Binding], rsi
0x1800584cb  jz      short loc_1800584FB
0x1800584cd  lea     rcx, [rsp+0B8h+Binding]; Binding
0x1800584d5  call    cs:__imp_RpcBindingFree
0x1800584dc  nop     dword ptr [rax+rax+00h]
0x1800584e1  test    eax, eax
0x1800584e3  jz      short loc_1800584EC
0x1800584e5  mov     edx, eax; __annotation("Debug", "TelemetryAssert", "status == RPC_S_OK", "RpcBindingFree")
0x1800584e7  call    MicrosoftTelemetryAssertTriggeredArgs
0x1800584ec  mov     [rsp+0B8h+Binding], rsi
0x1800584f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800584fb  test    rdi, rdi
0x1800584fe  jz      short loc_180058515
0x180058500  xchg    esi, [rdi+0B8h]
0x180058506  mov     rcx, rdi; registrationObject
0x180058509  call    NetworkIsolationUnregisterForAppContainerChanges
0x18005850e  mov     rcx, cs:WPP_GLOBAL_Control
0x180058515  cmp     rcx, r14
0x180058518  jz      short loc_180058538
0x18005851a  test    byte ptr [rcx+1Ch], 8
0x18005851e  jz      short loc_180058538
0x180058520  mov     edx, 1EBh
0x180058525  mov     r9d, ebx
0x180058528  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x18005852f  mov     rcx, [rcx+10h]
0x180058533  call    WPP_SF_d
0x180058538  mov     eax, ebx
0x18005853a  mov     rcx, [rsp+0B8h+var_30]
0x180058542  xor     rcx, rsp; StackCookie
0x180058545  call    __security_check_cookie
0x18005854a  lea     r11, [rsp+0B8h+var_28]
0x180058552  mov     rbx, [r11+38h]
0x180058556  mov     rsi, [r11+40h]
0x18005855a  mov     rsp, r11
0x18005855d  pop     r15
0x18005855f  pop     r14
0x180058561  pop     r13
0x180058563  pop     r12
0x180058565  pop     rdi
0x180058566  retn
0x1800604d0  push    rbp
0x1800604d2  sub     rsp, 40h
0x1800604d6  mov     rbp, rdx
0x1800604d9  mov     rcx, [rcx]
0x1800604dc  mov     ecx, [rcx]; ExceptionCode
0x1800604de  call    cs:__imp_RpcExceptionFilter
0x1800604e5  nop     dword ptr [rax+rax+00h]
0x1800604ea  nop
0x1800604eb  add     rsp, 40h
0x1800604ef  pop     rbp
0x1800604f0  retn
0x1800604f2  push    rbp
0x1800604f4  sub     rsp, 40h
0x1800604f8  mov     rbp, rdx
0x1800604fb  mov     rcx, [rcx]
0x1800604fe  mov     ecx, [rcx]; ExceptionCode
0x180060500  call    cs:__imp_RpcExceptionFilter
0x180060507  nop     dword ptr [rax+rax+00h]
0x18006050c  nop
0x18006050d  add     rsp, 40h
0x180060511  pop     rbp
0x180060512  retn
```
