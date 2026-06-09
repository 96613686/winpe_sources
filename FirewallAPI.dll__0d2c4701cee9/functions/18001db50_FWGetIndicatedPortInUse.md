# FWGetIndicatedPortInUse

- ea: `0x18001db50`
- end: `0x18001df9b`
- name: `FWGetIndicatedPortInUse`
- size: `1099`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001da20`

## callees

- `0x180005e0c`
- `0x18000ea10`
- `0x18001db50`
- `0x180026798`
- `0x1800294b0`
- `0x18003336c`
- `0x180054a80`

## import_xrefs

- `RPCRT4!RpcExceptionFilter` at `0x18005fc34`
- `RPCRT4!RpcExceptionFilter` at `0x18005fc34`
- `RPCRT4!NdrClientCall3` at `0x18001dc52`
- `RPCRT4!NdrClientCall3` at `0x18001dc52`
- `RPCRT4!RpcBindingFree` at `0x18001df5f`
- `RPCRT4!RpcBindingFree` at `0x18001df5f`
- `fwbase!FwIOReadPortUseIndications` at `0x18001dd1e`
- `fwbase!FwIOReadPortUseIndications` at `0x18001dd1e`
- `fwbase!FwCriticalSectionEnter` at `0x18001dd00`
- `fwbase!FwCriticalSectionEnter` at `0x18001dd00`
- `fwbase!FwCriticalSectionLeave` at `0x18001de7e`
- `fwbase!FwCriticalSectionLeave` at `0x18001de7e`
- `fwbase!FwBaseFree` at `0x18001dea2`
- `fwbase!FwBaseFree` at `0x18001deb6`
- `fwbase!FwBaseFree` at `0x18001df40`
- `fwbase!FwBaseFree` at `0x18001dea2`
- `fwbase!FwBaseFree` at `0x18001deb6`
- `fwbase!FwBaseFree` at `0x18001df40`
- `fwbase!FwHResultToWindowsError` at `0x18001ded4`
- `fwbase!FwHResultToWindowsError` at `0x18001ded4`

## pseudocode

```c
__int64 __fastcall FWGetIndicatedPortInUse(unsigned int a1, _DWORD *a2, _QWORD *a3, _QWORD *a4)
{
  int v7; // r15d
  unsigned int v8; // eax
  unsigned int Pointer; // ebx
  FwPolicy2 *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r9
  BOOL v13; // eax
  int v14; // eax
  __int64 v15; // rdx
  __int64 v16; // r9
  __int64 i; // r9
  unsigned int v18; // eax
  __int64 v19; // rcx
  int v21; // [rsp+40h] [rbp-98h]
  __int64 v23; // [rsp+88h] [rbp-50h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+90h] [rbp-48h] BYREF

  v23 = 0;
  v21 = 0;
  Binding = 0;
  if ( a1 > 8 )
  {
    Pointer = 0;
    v7 = -2147024809;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_36;
    v15 = 38;
    v16 = 2147942487LL;
    goto LABEL_34;
  }
  v7 = 0;
  *a2 = 0;
  *a3 = 0;
  *a4 = 0;
  v8 = Int_FWLocalRpcBindingCreate(&Binding);
  Pointer = v8;
  if ( v8 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v11 = 39;
      v12 = v8;
LABEL_6:
      WPP_SF_d(*((_QWORD *)v10 + 2), v11, WPP_a5b3657941d83b93491a297b9144c2a3_Traceguids, v12);
LABEL_35:
      v10 = WPP_GLOBAL_Control;
      goto LABEL_36;
    }
    goto LABEL_36;
  }
  Pointer = (unsigned int)NdrClientCall3(
                            (MIDL_STUBLESS_PROXY_INFO *)&FW_RESOURCE_INDICATION_ProxyInfo,
                            1u,
                            0,
                            Binding,
                            a1,
                            a2,
                            a3,
                            a4).Pointer;
  v13 = Pointer == 0;
  if ( Pointer == 1753 || Pointer == -2144206780 )
    Pointer = 0;
  if ( !Pointer )
  {
    if ( v13 )
      goto LABEL_35;
    FwCriticalSectionEnter(g_FwPortKeywordLock);
    v21 = 1;
    v14 = FwIOReadPortUseIndications(a1, &v23, a2);
    v7 = v14;
    if ( v14 >= 0 )
    {
      v14 = FwAllocCheckSize(2, (unsigned int)*a2, a3);
      v7 = v14;
      if ( v14 >= 0 )
      {
        v14 = FwAllocCheckSize(2, (unsigned int)*a2, a4);
        v7 = v14;
        if ( v14 >= 0 )
        {
          for ( i = 0; (unsigned int)i < *a2; i = (unsigned int)(i + 1) )
          {
            *(_WORD *)(*a3 + 2 * i) = *(_WORD *)(v23 + 4 * i);
            *(_WORD *)(*a4 + 2 * i) = *(_WORD *)(v23 + 4 * i + 2);
          }
          goto LABEL_35;
        }
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_36;
        v15 = 43;
      }
      else
      {
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_36;
        v15 = 42;
      }
    }
    else
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_36;
      v15 = 41;
    }
    v16 = (unsigned int)v14;
LABEL_34:
    WPP_SF_d(*((_QWORD *)v10 + 2), v15, WPP_a5b3657941d83b93491a297b9144c2a3_Traceguids, v16);
    goto LABEL_35;
  }
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v11 = 40;
    v12 = Pointer;
    goto LABEL_6;
  }
LABEL_36:
  if ( v21 == 1 )
  {
    FwCriticalSectionLeave(g_FwPortKeywordLock);
    v10 = WPP_GLOBAL_Control;
  }
  if ( v7 < 0 )
  {
    *a2 = 0;
    FwBaseFree(*a3);
    FwBaseFree(*a4);
    *a4 = 0;
    *a3 = 0;
    Pointer = FwHResultToWindowsError((unsigned int)v7);
    v10 = WPP_GLOBAL_Control;
  }
  if ( v10 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)v10 + 2), 44, WPP_a5b3657941d83b93491a297b9144c2a3_Traceguids, Pointer);
    v10 = WPP_GLOBAL_Control;
  }
  if ( Pointer == 5 )
  {
    if ( v10 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)v10 + 2), 45, WPP_a5b3657941d83b93491a297b9144c2a3_Traceguids);
    Pointer = 0;
  }
  FwBaseFree(v23);
  if ( Binding )
  {
    v18 = RpcBindingFree(&Binding);
    if ( v18 )
      MicrosoftTelemetryAssertTriggeredArgs(v19, v18);
  }
  return Pointer;
}

```

## disassembly

```asm
0x18001db50  mov     r11, rsp
0x18001db53  push    rbx
0x18001db54  push    rsi
0x18001db55  push    r12
0x18001db57  push    r13
0x18001db59  push    r14
0x18001db5b  push    r15
0x18001db5d  sub     rsp, 0A8h
0x18001db64  mov     rax, cs:__security_cookie
0x18001db6b  xor     rax, rsp
0x18001db6e  mov     [rsp+0D8h+var_40], rax
0x18001db76  mov     [rsp+0D8h+var_90], r9
0x18001db7b  mov     r13, r8
0x18001db7e  mov     r12, rdx
0x18001db81  mov     esi, ecx
0x18001db83  mov     [rsp+0D8h+var_78], ecx
0x18001db87  mov     [rsp+0D8h+var_68], rdx
0x18001db8c  mov     [rsp+0D8h+var_60], r8
0x18001db91  mov     [rsp+0D8h+var_58], r9
0x18001db99  mov     qword ptr [r11-50h], 0
0x18001dba1  xor     ecx, ecx
0x18001dba3  mov     [rsp+0D8h+var_98], ecx
0x18001dba7  mov     [r11-48h], rcx
0x18001dbab  cmp     esi, 8
0x18001dbae  ja      loc_18001DE2E
0x18001dbb4  xor     r15d, r15d
0x18001dbb7  mov     [rsp+0D8h+var_84], r15d
0x18001dbbc  mov     [rsp+0D8h+var_94], ecx
0x18001dbc0  mov     [rdx], ecx
0x18001dbc2  mov     [r8], rcx
0x18001dbc5  mov     [r9], rcx
0x18001dbc8  lea     rcx, [r11-48h]
0x18001dbcc  call    Int_FWLocalRpcBindingCreate
0x18001dbd1  mov     ebx, eax
0x18001dbd3  test    eax, eax
0x18001dbd5  jz      short loc_18001DC18
0x18001dbd7  lea     rsi, WPP_GLOBAL_Control
0x18001dbde  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dbe5  lea     r14d, [r15+1]
0x18001dbe9  cmp     rcx, rsi
0x18001dbec  jz      loc_18001DE70
0x18001dbf2  test    [rcx+1Ch], r14b
0x18001dbf6  jz      loc_18001DE70
0x18001dbfc  lea     edx, [r15+27h]
0x18001dc00  mov     r9d, eax
0x18001dc03  lea     r8, WPP_a5b3657941d83b93491a297b9144c2a3_Traceguids
0x18001dc0a  mov     rcx, [rcx+10h]
0x18001dc0e  call    WPP_SF_d
0x18001dc13  jmp     loc_18001DE69
0x18001dc18  mov     [rsp+0D8h+var_70], 0
0x18001dc21  mov     rax, [rsp+0D8h+var_90]
0x18001dc26  mov     [rsp+0D8h+var_A0], rax
0x18001dc2b  mov     [rsp+0D8h+var_A8], r13
0x18001dc30  mov     [rsp+0D8h+var_B0], r12
0x18001dc35  mov     [rsp+0D8h+var_B8], esi
0x18001dc39  mov     r9, [rsp+0D8h+Binding]
0x18001dc41  xor     r8d, r8d; pReturnValue
0x18001dc44  lea     r14d, [r8+1]
0x18001dc48  mov     edx, r14d; nProcNum
0x18001dc4b  lea     rcx, ?FW_RESOURCE_INDICATION_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18001dc52  call    cs:__imp_NdrClientCall3
0x18001dc59  nop     dword ptr [rax+rax+00h]
0x18001dc5e  mov     rbx, rax
0x18001dc61  mov     [rsp+0D8h+var_70], rax
0x18001dc66  mov     [rsp+0D8h+var_88], ebx
0x18001dc6a  xor     eax, eax
0x18001dc6c  test    ebx, ebx
0x18001dc6e  cmovz   eax, r14d
0x18001dc72  mov     [rsp+0D8h+var_94], eax
0x18001dc76  jmp     short loc_18001DCAD
0x18001dc78  mov     ebx, eax
0x18001dc7a  mov     [rsp+0D8h+var_88], eax
0x18001dc7e  mov     r14d, 1
0x18001dc84  mov     r15d, [rsp+0D8h+var_84]
0x18001dc89  mov     eax, [rsp+0D8h+var_94]
0x18001dc8d  mov     [rsp+0D8h+var_98], r15d
0x18001dc92  mov     esi, [rsp+0D8h+var_78]
0x18001dc96  mov     r12, [rsp+0D8h+var_68]
0x18001dc9b  mov     r13, [rsp+0D8h+var_60]
0x18001dca0  mov     rcx, [rsp+0D8h+var_58]
0x18001dca8  mov     [rsp+0D8h+var_90], rcx
0x18001dcad  cmp     ebx, 6D9h
0x18001dcb3  jz      short loc_18001DCBD
0x18001dcb5  cmp     ebx, 80320044h
0x18001dcbb  jnz     short loc_18001DCBF
0x18001dcbd  xor     ebx, ebx
0x18001dcbf  test    ebx, ebx
0x18001dcc1  jz      short loc_18001DCF1
0x18001dcc3  lea     rsi, WPP_GLOBAL_Control
0x18001dcca  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dcd1  cmp     rcx, rsi
0x18001dcd4  jz      loc_18001DE70
0x18001dcda  test    [rcx+1Ch], r14b
0x18001dcde  jz      loc_18001DE70
0x18001dce4  mov     edx, 28h ; '('
0x18001dce9  mov     r9d, ebx
0x18001dcec  jmp     loc_18001DC03
0x18001dcf1  test    eax, eax
0x18001dcf3  jnz     loc_18001DE25
0x18001dcf9  lea     rcx, g_FwPortKeywordLock
0x18001dd00  call    cs:__imp_FwCriticalSectionEnter
0x18001dd07  nop     dword ptr [rax+rax+00h]
0x18001dd0c  mov     [rsp+0D8h+var_98], r14d
0x18001dd11  mov     r8, r12
0x18001dd14  lea     rdx, [rsp+0D8h+var_50]
0x18001dd1c  mov     ecx, esi
0x18001dd1e  call    cs:__imp_FwIOReadPortUseIndications
0x18001dd25  nop     dword ptr [rax+rax+00h]
0x18001dd2a  mov     r15d, eax
0x18001dd2d  test    eax, eax
0x18001dd2f  jns     short loc_18001DD5F
0x18001dd31  lea     rsi, WPP_GLOBAL_Control
0x18001dd38  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dd3f  cmp     rcx, rsi
0x18001dd42  jz      loc_18001DE70
0x18001dd48  test    [rcx+1Ch], r14b
0x18001dd4c  jz      loc_18001DE70
0x18001dd52  mov     edx, 29h ; ')'
0x18001dd57  mov     r9d, eax
0x18001dd5a  jmp     loc_18001DE59
0x18001dd5f  mov     edx, [r12]
0x18001dd63  mov     r8, r13
0x18001dd66  mov     ecx, 2
0x18001dd6b  call    FwAllocCheckSize
0x18001dd70  mov     r15d, eax
0x18001dd73  test    eax, eax
0x18001dd75  jns     short loc_18001DD9F
0x18001dd77  lea     rsi, WPP_GLOBAL_Control
0x18001dd7e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dd85  cmp     rcx, rsi
0x18001dd88  jz      loc_18001DE70
0x18001dd8e  test    [rcx+1Ch], r14b
0x18001dd92  jz      loc_18001DE70
0x18001dd98  mov     edx, 2Ah ; '*'
0x18001dd9d  jmp     short loc_18001DD57
0x18001dd9f  mov     edx, [r12]
0x18001dda3  mov     rsi, [rsp+0D8h+var_90]
0x18001dda8  mov     r8, rsi
0x18001ddab  mov     ecx, 2
0x18001ddb0  call    FwAllocCheckSize
0x18001ddb5  mov     r15d, eax
0x18001ddb8  test    eax, eax
0x18001ddba  jns     short loc_18001DDE7
0x18001ddbc  lea     rsi, WPP_GLOBAL_Control
0x18001ddc3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ddca  cmp     rcx, rsi
0x18001ddcd  jz      loc_18001DE70
0x18001ddd3  test    [rcx+1Ch], r14b
0x18001ddd7  jz      loc_18001DE70
0x18001dddd  mov     edx, 2Bh ; '+'
0x18001dde2  jmp     loc_18001DD57
0x18001dde7  xor     r9d, r9d
0x18001ddea  cmp     [r12], r9d
0x18001ddee  jbe     short loc_18001DE25
0x18001ddf0  mov     rdx, [r13+0]
0x18001ddf4  mov     rax, [rsp+0D8h+var_50]
0x18001ddfc  movzx   ecx, word ptr [rax+r9*4]
0x18001de01  mov     [rdx+r9*2], cx
0x18001de06  mov     rdx, [rsi]
0x18001de09  mov     rax, [rsp+0D8h+var_50]
0x18001de11  movzx   ecx, word ptr [rax+r9*4+2]
0x18001de17  mov     [rdx+r9*2], cx
0x18001de1c  add     r9d, r14d
0x18001de1f  cmp     r9d, [r12]
0x18001de23  jb      short loc_18001DDF0
0x18001de25  lea     rsi, WPP_GLOBAL_Control
0x18001de2c  jmp     short loc_18001DE69
0x18001de2e  xor     ebx, ebx
0x18001de30  mov     r15d, 80070057h
0x18001de36  lea     rsi, WPP_GLOBAL_Control
0x18001de3d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001de44  lea     r14d, [rbx+1]
0x18001de48  cmp     rcx, rsi
0x18001de4b  jz      short loc_18001DE70
0x18001de4d  test    [rcx+1Ch], r14b
0x18001de51  jz      short loc_18001DE70
0x18001de53  lea     edx, [rbx+26h]
0x18001de56  mov     r9d, r15d
0x18001de59  lea     r8, WPP_a5b3657941d83b93491a297b9144c2a3_Traceguids
0x18001de60  mov     rcx, [rcx+10h]
0x18001de64  call    WPP_SF_d
0x18001de69  mov     rcx, cs:WPP_GLOBAL_Control
0x18001de70  cmp     [rsp+0D8h+var_98], r14d
0x18001de75  jnz     short loc_18001DE91
0x18001de77  lea     rcx, g_FwPortKeywordLock
0x18001de7e  call    cs:__imp_FwCriticalSectionLeave
0x18001de85  nop     dword ptr [rax+rax+00h]
0x18001de8a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001de91  test    r15d, r15d
0x18001de94  jns     short loc_18001DEE9
0x18001de96  mov     dword ptr [r12], 0
0x18001de9e  mov     rcx, [r13+0]
0x18001dea2  call    cs:__imp_FwBaseFree
0x18001dea9  nop     dword ptr [rax+rax+00h]
0x18001deae  mov     rbx, [rsp+0D8h+var_90]
0x18001deb3  mov     rcx, [rbx]
0x18001deb6  call    cs:__imp_FwBaseFree
0x18001debd  nop     dword ptr [rax+rax+00h]
0x18001dec2  mov     qword ptr [rbx], 0
0x18001dec9  mov     qword ptr [r13+0], 0
0x18001ded1  mov     ecx, r15d
0x18001ded4  call    cs:__imp_FwHResultToWindowsError
0x18001dedb  nop     dword ptr [rax+rax+00h]
0x18001dee0  mov     ebx, eax
0x18001dee2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dee9  cmp     rcx, rsi
0x18001deec  jz      short loc_18001DF13
0x18001deee  test    [rcx+1Ch], r14b
0x18001def2  jz      short loc_18001DF13
0x18001def4  mov     edx, 2Ch ; ','
0x18001def9  mov     r9d, ebx
0x18001defc  lea     r8, WPP_a5b3657941d83b93491a297b9144c2a3_Traceguids
0x18001df03  mov     rcx, [rcx+10h]
0x18001df07  call    WPP_SF_d
0x18001df0c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001df13  cmp     ebx, 5
0x18001df16  jnz     short loc_18001DF38
0x18001df18  cmp     rcx, rsi
0x18001df1b  jz      short loc_18001DF36
0x18001df1d  test    [rcx+1Ch], r14b
0x18001df21  jz      short loc_18001DF36
0x18001df23  lea     edx, [rbx+28h]
0x18001df26  lea     r8, WPP_a5b3657941d83b93491a297b9144c2a3_Traceguids
0x18001df2d  mov     rcx, [rcx+10h]
0x18001df31  call    WPP_SF_
0x18001df36  xor     ebx, ebx
0x18001df38  mov     rcx, [rsp+0D8h+var_50]
0x18001df40  call    cs:__imp_FwBaseFree
0x18001df47  nop     dword ptr [rax+rax+00h]
0x18001df4c  cmp     [rsp+0D8h+Binding], 0
0x18001df55  jz      short loc_18001DF76
0x18001df57  lea     rcx, [rsp+0D8h+Binding]; Binding
0x18001df5f  call    cs:__imp_RpcBindingFree
0x18001df66  nop     dword ptr [rax+rax+00h]
0x18001df6b  test    eax, eax
0x18001df6d  jz      short loc_18001DF76
0x18001df6f  mov     edx, eax; __annotation("Debug", "TelemetryAssert", "status == RPC_S_OK", "RpcBindingFree")
0x18001df71  call    MicrosoftTelemetryAssertTriggeredArgs
0x18001df76  mov     eax, ebx
0x18001df78  mov     rcx, [rsp+0D8h+var_40]
0x18001df80  xor     rcx, rsp; StackCookie
0x18001df83  call    __security_check_cookie
0x18001df88  add     rsp, 0A8h
0x18001df8f  pop     r15
0x18001df91  pop     r14
0x18001df93  pop     r13
0x18001df95  pop     r12
0x18001df97  pop     rsi
0x18001df98  pop     rbx
0x18001df99  retn
0x18005fc26  push    rbp
0x18005fc28  sub     rsp, 40h
0x18005fc2c  mov     rbp, rdx
0x18005fc2f  mov     rcx, [rcx]
0x18005fc32  mov     ecx, [rcx]; ExceptionCode
0x18005fc34  call    cs:__imp_RpcExceptionFilter
0x18005fc3b  nop     dword ptr [rax+rax+00h]
0x18005fc40  nop
0x18005fc41  add     rsp, 40h
0x18005fc45  pop     rbp
0x18005fc46  retn
```
