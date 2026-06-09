# FWGetIndicatedPortInUse

- ea: `0x180010400`
- end: `0x180010814`
- name: `FWGetIndicatedPortInUse`
- size: `1044`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800102d0`

## callees

- `0x180005954`
- `0x18000e960`
- `0x180010400`
- `0x180024c3c`
- `0x1800277b0`
- `0x18003104c`
- `0x180051410`

## import_xrefs

- `RPCRT4!RpcExceptionFilter` at `0x18005b956`
- `RPCRT4!RpcExceptionFilter` at `0x18005b956`
- `RPCRT4!NdrClientCall3` at `0x180010502`
- `RPCRT4!NdrClientCall3` at `0x180010502`
- `RPCRT4!RpcBindingFree` at `0x1800107df`
- `RPCRT4!RpcBindingFree` at `0x1800107df`
- `fwbase!FwIOReadPortUseIndications` at `0x1800105c2`
- `fwbase!FwIOReadPortUseIndications` at `0x1800105c2`
- `fwbase!FwCriticalSectionEnter` at `0x1800105aa`
- `fwbase!FwCriticalSectionEnter` at `0x1800105aa`
- `fwbase!FwCriticalSectionLeave` at `0x18001071c`
- `fwbase!FwCriticalSectionLeave` at `0x18001071c`
- `fwbase!FwBaseFree` at `0x18001073a`
- `fwbase!FwBaseFree` at `0x180010748`
- `fwbase!FwBaseFree` at `0x1800107c6`
- `fwbase!FwBaseFree` at `0x18001073a`
- `fwbase!FwBaseFree` at `0x180010748`
- `fwbase!FwBaseFree` at `0x1800107c6`
- `fwbase!FwHResultToWindowsError` at `0x180010760`
- `fwbase!FwHResultToWindowsError` at `0x180010760`

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
0x180010400  mov     r11, rsp
0x180010403  push    rbx
0x180010404  push    rsi
0x180010405  push    r12
0x180010407  push    r13
0x180010409  push    r14
0x18001040b  push    r15
0x18001040d  sub     rsp, 0A8h
0x180010414  mov     rax, cs:__security_cookie
0x18001041b  xor     rax, rsp
0x18001041e  mov     [rsp+0D8h+var_40], rax
0x180010426  mov     [rsp+0D8h+var_90], r9
0x18001042b  mov     r13, r8
0x18001042e  mov     r12, rdx
0x180010431  mov     esi, ecx
0x180010433  mov     [rsp+0D8h+var_78], ecx
0x180010437  mov     [rsp+0D8h+var_68], rdx
0x18001043c  mov     [rsp+0D8h+var_60], r8
0x180010441  mov     [rsp+0D8h+var_58], r9
0x180010449  mov     qword ptr [r11-50h], 0
0x180010451  xor     ecx, ecx
0x180010453  mov     [rsp+0D8h+var_98], ecx
0x180010457  mov     [r11-48h], rcx
0x18001045b  cmp     esi, 8
0x18001045e  ja      loc_1800106CC
0x180010464  xor     r15d, r15d
0x180010467  mov     [rsp+0D8h+var_84], r15d
0x18001046c  mov     [rsp+0D8h+var_94], ecx
0x180010470  mov     [rdx], ecx
0x180010472  mov     [r8], rcx
0x180010475  mov     [r9], rcx
0x180010478  lea     rcx, [r11-48h]
0x18001047c  call    Int_FWLocalRpcBindingCreate
0x180010481  mov     ebx, eax
0x180010483  test    eax, eax
0x180010485  jz      short loc_1800104C8
0x180010487  lea     rsi, WPP_GLOBAL_Control
0x18001048e  mov     rcx, cs:WPP_GLOBAL_Control
0x180010495  lea     r14d, [r15+1]
0x180010499  cmp     rcx, rsi
0x18001049c  jz      loc_18001070E
0x1800104a2  test    [rcx+1Ch], r14b
0x1800104a6  jz      loc_18001070E
0x1800104ac  lea     edx, [r15+27h]
0x1800104b0  mov     r9d, eax
0x1800104b3  lea     r8, WPP_a5b3657941d83b93491a297b9144c2a3_Traceguids
0x1800104ba  mov     rcx, [rcx+10h]
0x1800104be  call    WPP_SF_d
0x1800104c3  jmp     loc_180010707
0x1800104c8  mov     [rsp+0D8h+var_70], 0
0x1800104d1  mov     rax, [rsp+0D8h+var_90]
0x1800104d6  mov     [rsp+0D8h+var_A0], rax
0x1800104db  mov     [rsp+0D8h+var_A8], r13
0x1800104e0  mov     [rsp+0D8h+var_B0], r12
0x1800104e5  mov     [rsp+0D8h+var_B8], esi
0x1800104e9  mov     r9, [rsp+0D8h+Binding]
0x1800104f1  xor     r8d, r8d; pReturnValue
0x1800104f4  lea     r14d, [r8+1]
0x1800104f8  mov     edx, r14d; nProcNum
0x1800104fb  lea     rcx, ?FW_RESOURCE_INDICATION_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180010502  call    cs:__imp_NdrClientCall3
0x180010508  mov     rbx, rax
0x18001050b  mov     [rsp+0D8h+var_70], rax
0x180010510  mov     [rsp+0D8h+var_88], ebx
0x180010514  xor     eax, eax
0x180010516  test    ebx, ebx
0x180010518  cmovz   eax, r14d
0x18001051c  mov     [rsp+0D8h+var_94], eax
0x180010520  jmp     short loc_180010557
0x180010522  mov     ebx, eax
0x180010524  mov     [rsp+0D8h+var_88], eax
0x180010528  mov     r14d, 1
0x18001052e  mov     r15d, [rsp+0D8h+var_84]
0x180010533  mov     eax, [rsp+0D8h+var_94]
0x180010537  mov     [rsp+0D8h+var_98], r15d
0x18001053c  mov     esi, [rsp+0D8h+var_78]
0x180010540  mov     r12, [rsp+0D8h+var_68]
0x180010545  mov     r13, [rsp+0D8h+var_60]
0x18001054a  mov     rcx, [rsp+0D8h+var_58]
0x180010552  mov     [rsp+0D8h+var_90], rcx
0x180010557  cmp     ebx, 6D9h
0x18001055d  jz      short loc_180010567
0x18001055f  cmp     ebx, 80320044h
0x180010565  jnz     short loc_180010569
0x180010567  xor     ebx, ebx
0x180010569  test    ebx, ebx
0x18001056b  jz      short loc_18001059B
0x18001056d  lea     rsi, WPP_GLOBAL_Control
0x180010574  mov     rcx, cs:WPP_GLOBAL_Control
0x18001057b  cmp     rcx, rsi
0x18001057e  jz      loc_18001070E
0x180010584  test    [rcx+1Ch], r14b
0x180010588  jz      loc_18001070E
0x18001058e  mov     edx, 28h ; '('
0x180010593  mov     r9d, ebx
0x180010596  jmp     loc_1800104B3
0x18001059b  test    eax, eax
0x18001059d  jnz     loc_1800106C3
0x1800105a3  lea     rcx, g_FwPortKeywordLock
0x1800105aa  call    cs:__imp_FwCriticalSectionEnter
0x1800105b0  mov     [rsp+0D8h+var_98], r14d
0x1800105b5  mov     r8, r12
0x1800105b8  lea     rdx, [rsp+0D8h+var_50]
0x1800105c0  mov     ecx, esi
0x1800105c2  call    cs:__imp_FwIOReadPortUseIndications
0x1800105c8  mov     r15d, eax
0x1800105cb  test    eax, eax
0x1800105cd  jns     short loc_1800105FD
0x1800105cf  lea     rsi, WPP_GLOBAL_Control
0x1800105d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800105dd  cmp     rcx, rsi
0x1800105e0  jz      loc_18001070E
0x1800105e6  test    [rcx+1Ch], r14b
0x1800105ea  jz      loc_18001070E
0x1800105f0  mov     edx, 29h ; ')'
0x1800105f5  mov     r9d, eax
0x1800105f8  jmp     loc_1800106F7
0x1800105fd  mov     edx, [r12]
0x180010601  mov     r8, r13
0x180010604  mov     ecx, 2
0x180010609  call    FwAllocCheckSize
0x18001060e  mov     r15d, eax
0x180010611  test    eax, eax
0x180010613  jns     short loc_18001063D
0x180010615  lea     rsi, WPP_GLOBAL_Control
0x18001061c  mov     rcx, cs:WPP_GLOBAL_Control
0x180010623  cmp     rcx, rsi
0x180010626  jz      loc_18001070E
0x18001062c  test    [rcx+1Ch], r14b
0x180010630  jz      loc_18001070E
0x180010636  mov     edx, 2Ah ; '*'
0x18001063b  jmp     short loc_1800105F5
0x18001063d  mov     edx, [r12]
0x180010641  mov     rsi, [rsp+0D8h+var_90]
0x180010646  mov     r8, rsi
0x180010649  mov     ecx, 2
0x18001064e  call    FwAllocCheckSize
0x180010653  mov     r15d, eax
0x180010656  test    eax, eax
0x180010658  jns     short loc_180010685
0x18001065a  lea     rsi, WPP_GLOBAL_Control
0x180010661  mov     rcx, cs:WPP_GLOBAL_Control
0x180010668  cmp     rcx, rsi
0x18001066b  jz      loc_18001070E
0x180010671  test    [rcx+1Ch], r14b
0x180010675  jz      loc_18001070E
0x18001067b  mov     edx, 2Bh ; '+'
0x180010680  jmp     loc_1800105F5
0x180010685  xor     r9d, r9d
0x180010688  cmp     [r12], r9d
0x18001068c  jbe     short loc_1800106C3
0x18001068e  mov     rdx, [r13+0]
0x180010692  mov     rax, [rsp+0D8h+var_50]
0x18001069a  movzx   ecx, word ptr [rax+r9*4]
0x18001069f  mov     [rdx+r9*2], cx
0x1800106a4  mov     rdx, [rsi]
0x1800106a7  mov     rax, [rsp+0D8h+var_50]
0x1800106af  movzx   ecx, word ptr [rax+r9*4+2]
0x1800106b5  mov     [rdx+r9*2], cx
0x1800106ba  add     r9d, r14d
0x1800106bd  cmp     r9d, [r12]
0x1800106c1  jb      short loc_18001068E
0x1800106c3  lea     rsi, WPP_GLOBAL_Control
0x1800106ca  jmp     short loc_180010707
0x1800106cc  xor     ebx, ebx
0x1800106ce  mov     r15d, 80070057h
0x1800106d4  lea     rsi, WPP_GLOBAL_Control
0x1800106db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800106e2  lea     r14d, [rbx+1]
0x1800106e6  cmp     rcx, rsi
0x1800106e9  jz      short loc_18001070E
0x1800106eb  test    [rcx+1Ch], r14b
0x1800106ef  jz      short loc_18001070E
0x1800106f1  lea     edx, [rbx+26h]
0x1800106f4  mov     r9d, r15d
0x1800106f7  lea     r8, WPP_a5b3657941d83b93491a297b9144c2a3_Traceguids
0x1800106fe  mov     rcx, [rcx+10h]
0x180010702  call    WPP_SF_d
0x180010707  mov     rcx, cs:WPP_GLOBAL_Control
0x18001070e  cmp     [rsp+0D8h+var_98], r14d
0x180010713  jnz     short loc_180010729
0x180010715  lea     rcx, g_FwPortKeywordLock
0x18001071c  call    cs:__imp_FwCriticalSectionLeave
0x180010722  mov     rcx, cs:WPP_GLOBAL_Control
0x180010729  test    r15d, r15d
0x18001072c  jns     short loc_18001076F
0x18001072e  mov     dword ptr [r12], 0
0x180010736  mov     rcx, [r13+0]
0x18001073a  call    cs:__imp_FwBaseFree
0x180010740  mov     rbx, [rsp+0D8h+var_90]
0x180010745  mov     rcx, [rbx]
0x180010748  call    cs:__imp_FwBaseFree
0x18001074e  mov     qword ptr [rbx], 0
0x180010755  mov     qword ptr [r13+0], 0
0x18001075d  mov     ecx, r15d
0x180010760  call    cs:__imp_FwHResultToWindowsError
0x180010766  mov     ebx, eax
0x180010768  mov     rcx, cs:WPP_GLOBAL_Control
0x18001076f  cmp     rcx, rsi
0x180010772  jz      short loc_180010799
0x180010774  test    [rcx+1Ch], r14b
0x180010778  jz      short loc_180010799
0x18001077a  mov     edx, 2Ch ; ','
0x18001077f  mov     r9d, ebx
0x180010782  lea     r8, WPP_a5b3657941d83b93491a297b9144c2a3_Traceguids
0x180010789  mov     rcx, [rcx+10h]
0x18001078d  call    WPP_SF_d
0x180010792  mov     rcx, cs:WPP_GLOBAL_Control
0x180010799  cmp     ebx, 5
0x18001079c  jnz     short loc_1800107BE
0x18001079e  cmp     rcx, rsi
0x1800107a1  jz      short loc_1800107BC
0x1800107a3  test    [rcx+1Ch], r14b
0x1800107a7  jz      short loc_1800107BC
0x1800107a9  lea     edx, [rbx+28h]
0x1800107ac  lea     r8, WPP_a5b3657941d83b93491a297b9144c2a3_Traceguids
0x1800107b3  mov     rcx, [rcx+10h]
0x1800107b7  call    WPP_SF_
0x1800107bc  xor     ebx, ebx
0x1800107be  mov     rcx, [rsp+0D8h+var_50]
0x1800107c6  call    cs:__imp_FwBaseFree
0x1800107cc  cmp     [rsp+0D8h+Binding], 0
0x1800107d5  jz      short loc_1800107F0
0x1800107d7  lea     rcx, [rsp+0D8h+Binding]; Binding
0x1800107df  call    cs:__imp_RpcBindingFree
0x1800107e5  test    eax, eax
0x1800107e7  jz      short loc_1800107F0
0x1800107e9  mov     edx, eax
0x1800107eb  call    MicrosoftTelemetryAssertTriggeredArgs
0x1800107f0  mov     eax, ebx
0x1800107f2  mov     rcx, [rsp+0D8h+var_40]
0x1800107fa  xor     rcx, rsp; StackCookie
0x1800107fd  call    __security_check_cookie
0x180010802  add     rsp, 0A8h
0x180010809  pop     r15
0x18001080b  pop     r14
0x18001080d  pop     r13
0x18001080f  pop     r12
0x180010811  pop     rsi
0x180010812  pop     rbx
0x180010813  retn
0x18005b948  push    rbp
0x18005b94a  sub     rsp, 40h
0x18005b94e  mov     rbp, rdx
0x18005b951  mov     rcx, [rcx]
0x18005b954  mov     ecx, [rcx]; ExceptionCode
0x18005b956  call    cs:__imp_RpcExceptionFilter
0x18005b95c  nop
0x18005b95d  add     rsp, 40h
0x18005b961  pop     rbp
0x18005b962  retn
```
