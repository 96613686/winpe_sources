# NetworkIsolationRegisterForAppContainerChanges

- ea: `0x1800546e0`
- end: `0x180054b67`
- name: `NetworkIsolationRegisterForAppContainerChanges`
- size: `1159`
- prototype: `DWORD __stdcall(DWORD flags, PAC_CHANGES_CALLBACK_FN callback, PVOID context, HANDLE *registrationObject)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180005954`
- `0x18000e960`
- `0x180024c3c`
- `0x1800277b0`
- `0x1800284c4`
- `0x18003104c`
- `0x180049bb0`
- `0x1800546e0`
- `0x180054c90`

## import_xrefs

- `RPCRT4!RpcExceptionFilter` at `0x18005c23e`
- `RPCRT4!RpcExceptionFilter` at `0x18005c25a`
- `RPCRT4!RpcExceptionFilter` at `0x18005c23e`
- `RPCRT4!RpcExceptionFilter` at `0x18005c25a`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180054a49`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180054a49`
- `RPCRT4!NdrClientCall3` at `0x18005494f`
- `RPCRT4!NdrClientCall3` at `0x18005494f`
- `RPCRT4!RpcBindingFree` at `0x180054adb`
- `RPCRT4!RpcBindingFree` at `0x180054adb`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005484a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005484a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800548c6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800548c6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18005491e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18005491e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180054753`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180054753`
- `fwbase!FwBaseAlloc` at `0x180054760`
- `fwbase!FwBaseAlloc` at `0x180054760`

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
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 483, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids);
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
      v11 = 485;
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
          v11 = 486;
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
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 489, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, Pointer);
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
            v11 = 488;
            goto LABEL_8;
          }
        }
        goto LABEL_33;
      }
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_33;
      v11 = 487;
    }
    v8 = inited;
    goto LABEL_8;
  }
  v8 = 14;
  v9 = 14;
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v11 = 484;
LABEL_8:
    WPP_SF_d(*((_QWORD *)v10 + 2), v11, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, v8);
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
    WPP_SF_d(*((_QWORD *)v10 + 2), 492, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, v9);
  return v9;
}

```

## disassembly

```asm
0x1800546e0  mov     [rsp+arg_8], rbx
0x1800546e5  mov     [rsp+arg_10], rsi
0x1800546ea  push    rdi
0x1800546eb  push    r12
0x1800546ed  push    r13
0x1800546ef  push    r14
0x1800546f1  push    r15
0x1800546f3  sub     rsp, 90h
0x1800546fa  mov     rax, cs:__security_cookie
0x180054701  xor     rax, rsp
0x180054704  mov     [rsp+0B8h+var_30], rax
0x18005470c  mov     r15, r8
0x18005470f  mov     r12, rdx
0x180054712  mov     [rsp+0B8h+var_70], ecx
0x180054716  mov     [rsp+0B8h+var_40], r9
0x18005471b  lea     r14, WPP_GLOBAL_Control
0x180054722  mov     rcx, cs:WPP_GLOBAL_Control
0x180054729  cmp     rcx, r14
0x18005472c  jz      short loc_180054749
0x18005472e  test    byte ptr [rcx+1Ch], 8
0x180054732  jz      short loc_180054749
0x180054734  mov     edx, 1E3h
0x180054739  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x180054740  mov     rcx, [rcx+10h]
0x180054744  call    WPP_SF_
0x180054749  xor     esi, esi
0x18005474b  mov     [rsp+0B8h+Binding], rsi
0x180054753  call    cs:__imp_GetTickCount64
0x180054759  mov     ebx, 0C0h
0x18005475e  mov     ecx, ebx
0x180054760  call    cs:__imp_FwBaseAlloc
0x180054766  mov     rdi, rax
0x180054769  mov     [rsp+0B8h+var_78], rax
0x18005476e  test    rax, rax
0x180054771  jnz     short loc_1800547AE
0x180054773  lea     r9d, [rsi+0Eh]
0x180054777  mov     ebx, r9d
0x18005477a  mov     rcx, cs:WPP_GLOBAL_Control
0x180054781  cmp     rcx, r14
0x180054784  jz      loc_180054AC5
0x18005478a  test    byte ptr [rcx+1Ch], 1
0x18005478e  jz      loc_180054AC5
0x180054794  mov     edx, 1E4h
0x180054799  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x1800547a0  mov     rcx, [rcx+10h]
0x1800547a4  call    WPP_SF_d
0x1800547a9  jmp     loc_180054ABE
0x1800547ae  mov     r8, rbx; Size
0x1800547b1  xor     edx, edx; Val
0x1800547b3  mov     rcx, rdi; void *
0x1800547b6  call    memset_0
0x1800547bb  lea     rcx, [rsp+0B8h+Binding]
0x1800547c3  call    Int_FWLocalRpcBindingCreate
0x1800547c8  mov     ebx, eax
0x1800547ca  test    eax, eax
0x1800547cc  jz      short loc_1800547F2
0x1800547ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800547d5  cmp     rcx, r14
0x1800547d8  jz      loc_180054AC5
0x1800547de  test    byte ptr [rcx+1Ch], 1
0x1800547e2  jz      loc_180054AC5
0x1800547e8  mov     edx, 1E5h
0x1800547ed  mov     r9d, eax
0x1800547f0  jmp     short loc_180054799
0x1800547f2  mov     rax, [rsp+0B8h+Binding]
0x1800547fa  mov     [rdi], rax
0x1800547fd  mov     [rsp+0B8h+Binding], rsi
0x180054805  mov     [rdi+80h], r12
0x18005480c  mov     [rdi+88h], r15
0x180054813  lea     r15, [rdi+0B0h]
0x18005481a  mov     [rsp+0B8h+var_68], r15
0x18005481f  mov     dword ptr [r15], 1
0x180054826  mov     eax, esi
0x180054828  xchg    eax, [rdi+0B4h]
0x18005482e  lea     r12, [rdi+0B8h]
0x180054835  mov     [rsp+0B8h+var_50], r12
0x18005483a  mov     eax, esi
0x18005483c  xchg    eax, [r12]
0x180054840  xor     r9d, r9d; lpName
0x180054843  xor     r8d, r8d; bInitialState
0x180054846  xor     edx, edx; bManualReset
0x180054848  xor     ecx, ecx; lpEventAttributes
0x18005484a  call    cs:__imp_CreateEventW
0x180054850  mov     [rdi+90h], rax
0x180054857  test    rax, rax
0x18005485a  jnz     short loc_180054887
0x18005485c  lea     r9d, [rax+0Eh]
0x180054860  mov     ebx, r9d
0x180054863  mov     rcx, cs:WPP_GLOBAL_Control
0x18005486a  cmp     rcx, r14
0x18005486d  jz      loc_180054AC5
0x180054873  test    byte ptr [rcx+1Ch], 1
0x180054877  jz      loc_180054AC5
0x18005487d  mov     edx, 1E6h
0x180054882  jmp     loc_180054799
0x180054887  mov     rcx, rdi; struct FW_INTCLIENT_REG_HANDLE_ *
0x18005488a  call    ?Int_NetworkIsolationInitRegistrationRpcAsync@@YAKPEAUFW_INTCLIENT_REG_HANDLE_@@@Z; Int_NetworkIsolationInitRegistrationRpcAsync(FW_INTCLIENT_REG_HANDLE_ *)
0x18005488f  mov     ebx, eax
0x180054891  test    eax, eax
0x180054893  jz      short loc_1800548B9
0x180054895  mov     rcx, cs:WPP_GLOBAL_Control
0x18005489c  cmp     rcx, r14
0x18005489f  jz      loc_180054AC5
0x1800548a5  test    byte ptr [rcx+1Ch], 1
0x1800548a9  jz      loc_180054AC5
0x1800548af  mov     edx, 1E7h
0x1800548b4  jmp     loc_1800547ED
0x1800548b9  xor     r8d, r8d; pcbe
0x1800548bc  mov     rdx, rdi; pv
0x1800548bf  lea     rcx, ?Int_FwRegistrationCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x1800548c6  call    cs:__imp_CreateThreadpoolWait
0x1800548cc  mov     [rdi+98h], rax
0x1800548d3  test    rax, rax
0x1800548d6  jnz     short loc_180054903
0x1800548d8  lea     r9d, [rax+0Eh]
0x1800548dc  mov     ebx, r9d
0x1800548df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800548e6  cmp     rcx, r14
0x1800548e9  jz      loc_180054AC5
0x1800548ef  test    byte ptr [rcx+1Ch], 1
0x1800548f3  jz      loc_180054AC5
0x1800548f9  mov     edx, 1E8h
0x1800548fe  jmp     loc_180054799
0x180054903  mov     r13, rdi
0x180054906  mov     [rsp+0B8h+var_58], rdi
0x18005490b  lea     rcx, [rdi+8]
0x18005490f  mov     [rsp+0B8h+var_48], rcx
0x180054914  xor     r8d, r8d; pftTimeout
0x180054917  mov     rdx, [rcx+30h]; h
0x18005491b  mov     rcx, rax; pwa
0x18005491e  call    cs:__imp_SetThreadpoolWait
0x180054924  nop
0x180054925  mov     [rsp+0B8h+var_60], rsi
0x18005492a  lea     rax, [rdi+0A0h]
0x180054931  mov     [rsp+0B8h+var_90], rax
0x180054936  mov     eax, [rsp+0B8h+var_70]
0x18005493a  mov     dword ptr [rsp+0B8h+var_98], eax
0x18005493e  mov     r9, [rdi]
0x180054941  xor     r8d, r8d; pReturnValue
0x180054944  lea     edx, [r8+8]; nProcNum
0x180054948  lea     rcx, ?FW_RESOURCE_INDICATION_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18005494f  call    cs:__imp_NdrClientCall3
0x180054955  mov     rbx, rax
0x180054958  mov     [rsp+0B8h+var_60], rax
0x18005495d  mov     [rsp+0B8h+var_6C], eax
0x180054961  test    eax, eax
0x180054963  jz      short loc_18005499B
0x180054965  mov     rcx, cs:WPP_GLOBAL_Control
0x18005496c  cmp     rcx, r14
0x18005496f  jz      short loc_180054996
0x180054971  test    byte ptr [rcx+1Ch], 1
0x180054975  jz      short loc_180054996
0x180054977  mov     edx, 1E9h
0x18005497c  mov     r9d, eax
0x18005497f  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x180054986  mov     rcx, [rcx+10h]
0x18005498a  call    WPP_SF_d
0x18005498f  mov     rcx, cs:WPP_GLOBAL_Control
0x180054996  jmp     loc_180054AC5
0x18005499b  jmp     short loc_180054A0D
0x18005499d  mov     ebx, eax
0x18005499f  mov     [rsp+0B8h+var_6C], eax
0x1800549a3  test    eax, eax
0x1800549a5  jz      short loc_1800549F2
0x1800549a7  lea     rdx, WPP_GLOBAL_Control
0x1800549ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800549b5  cmp     rcx, rdx
0x1800549b8  jz      short loc_1800549DF
0x1800549ba  test    byte ptr [rcx+1Ch], 1
0x1800549be  jz      short loc_1800549DF
0x1800549c0  mov     edx, 1EAh
0x1800549c5  mov     r9d, eax
0x1800549c8  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x1800549cf  mov     rcx, [rcx+10h]
0x1800549d3  call    WPP_SF_d
0x1800549d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800549df  lea     r14, WPP_GLOBAL_Control
0x1800549e6  xor     esi, esi
0x1800549e8  mov     rdi, [rsp+0B8h+var_78]
0x1800549ed  jmp     loc_180054AC5
0x1800549f2  lea     r14, WPP_GLOBAL_Control
0x1800549f9  xor     esi, esi
0x1800549fb  mov     r13, [rsp+0B8h+var_58]
0x180054a00  mov     rdi, r13
0x180054a03  mov     r15, [rsp+0B8h+var_68]
0x180054a08  mov     r12, [rsp+0B8h+var_50]
0x180054a0d  mov     eax, 1
0x180054a12  xchg    eax, [r12]
0x180054a16  lea     rax, [r13+0A8h]
0x180054a1d  mov     [rsp+0B8h+var_88], rax
0x180054a22  mov     rax, [r13+0A0h]
0x180054a29  mov     [rsp+0B8h+var_90], rax
0x180054a2e  mov     rax, [rdi]
0x180054a31  mov     [rsp+0B8h+var_98], rax
0x180054a36  mov     r9, [rsp+0B8h+var_48]
0x180054a3b  xor     r8d, r8d; pReturnValue
0x180054a3e  lea     edx, [r8+9]; nProcNum
0x180054a42  lea     rcx, ?FW_RESOURCE_INDICATION_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180054a49  call    cs:__imp_Ndr64AsyncClientCall
0x180054a4f  jmp     short loc_180054AB2
0x180054a51  mov     ebx, eax
0x180054a53  test    eax, eax
0x180054a55  jz      short loc_180054A9F
0x180054a57  lea     rdx, WPP_GLOBAL_Control
0x180054a5e  mov     rcx, cs:WPP_GLOBAL_Control
0x180054a65  cmp     rcx, rdx
0x180054a68  jz      short loc_180054A8F
0x180054a6a  test    byte ptr [rcx+1Ch], 1
0x180054a6e  jz      short loc_180054A8F
0x180054a70  mov     edx, 1EBh
0x180054a75  mov     r9d, eax
0x180054a78  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x180054a7f  mov     rcx, [rcx+10h]
0x180054a83  call    WPP_SF_d
0x180054a88  mov     rcx, cs:WPP_GLOBAL_Control
0x180054a8f  lea     r14, WPP_GLOBAL_Control
0x180054a96  xor     esi, esi
0x180054a98  mov     rdi, [rsp+0B8h+var_78]
0x180054a9d  jmp     short loc_180054AC5
0x180054a9f  lea     r14, WPP_GLOBAL_Control
0x180054aa6  xor     esi, esi
0x180054aa8  mov     rdi, [rsp+0B8h+var_78]
0x180054aad  mov     r15, [rsp+0B8h+var_68]
0x180054ab2  lock inc dword ptr [r15]
0x180054ab6  mov     rax, [rsp+0B8h+var_40]
0x180054abb  mov     [rax], rdi
0x180054abe  mov     rcx, cs:WPP_GLOBAL_Control
0x180054ac5  test    ebx, ebx
0x180054ac7  jz      short loc_180054B15
0x180054ac9  cmp     [rsp+0B8h+Binding], rsi
0x180054ad1  jz      short loc_180054AFB
0x180054ad3  lea     rcx, [rsp+0B8h+Binding]; Binding
0x180054adb  call    cs:__imp_RpcBindingFree
0x180054ae1  test    eax, eax
0x180054ae3  jz      short loc_180054AEC
0x180054ae5  mov     edx, eax
0x180054ae7  call    MicrosoftTelemetryAssertTriggeredArgs
0x180054aec  mov     [rsp+0B8h+Binding], rsi
0x180054af4  mov     rcx, cs:WPP_GLOBAL_Control
0x180054afb  test    rdi, rdi
0x180054afe  jz      short loc_180054B15
0x180054b00  xchg    esi, [rdi+0B8h]
0x180054b06  mov     rcx, rdi; registrationObject
0x180054b09  call    NetworkIsolationUnregisterForAppContainerChanges
0x180054b0e  mov     rcx, cs:WPP_GLOBAL_Control
0x180054b15  cmp     rcx, r14
0x180054b18  jz      short loc_180054B38
0x180054b1a  test    byte ptr [rcx+1Ch], 8
0x180054b1e  jz      short loc_180054B38
0x180054b20  mov     edx, 1ECh
0x180054b25  mov     r9d, ebx
0x180054b28  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x180054b2f  mov     rcx, [rcx+10h]
0x180054b33  call    WPP_SF_d
0x180054b38  mov     eax, ebx
0x180054b3a  mov     rcx, [rsp+0B8h+var_30]
0x180054b42  xor     rcx, rsp; StackCookie
0x180054b45  call    __security_check_cookie
0x180054b4a  lea     r11, [rsp+0B8h+var_28]
0x180054b52  mov     rbx, [r11+38h]
0x180054b56  mov     rsi, [r11+40h]
0x180054b5a  mov     rsp, r11
0x180054b5d  pop     r15
0x180054b5f  pop     r14
0x180054b61  pop     r13
0x180054b63  pop     r12
0x180054b65  pop     rdi
0x180054b66  retn
0x18005c230  push    rbp
0x18005c232  sub     rsp, 40h
0x18005c236  mov     rbp, rdx
0x18005c239  mov     rcx, [rcx]
0x18005c23c  mov     ecx, [rcx]; ExceptionCode
0x18005c23e  call    cs:__imp_RpcExceptionFilter
0x18005c244  nop
0x18005c245  add     rsp, 40h
0x18005c249  pop     rbp
0x18005c24a  retn
0x18005c24c  push    rbp
0x18005c24e  sub     rsp, 40h
0x18005c252  mov     rbp, rdx
0x18005c255  mov     rcx, [rcx]
0x18005c258  mov     ecx, [rcx]; ExceptionCode
0x18005c25a  call    cs:__imp_RpcExceptionFilter
0x18005c260  nop
0x18005c261  add     rsp, 40h
0x18005c265  pop     rbp
0x18005c266  retn
```
