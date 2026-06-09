# Int_FWDeleteObject

- ea: `0x1800052c0`
- end: `0x18000594c`
- name: `Int_FWDeleteObject`
- size: `1676`
- prototype: ``
- caller_count: `10`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800051c0`
- `0x18004bae0`
- `0x18004bbd0`
- `0x18004bcb0`
- `0x18004bda0`
- `0x18004be80`
- `0x18004bf60`
- `0x18004c050`
- `0x18004c140`
- `0x18004c690`

## callees

- `0x1800052c0`
- `0x180005954`
- `0x180024c3c`
- `0x18002514c`
- `0x18003104c`
- `0x1800516bc`
- `0x180051710`
- `0x180051cc0`
- `0x18005e010`

## import_xrefs

- `RPCRT4!RpcExceptionFilter` at `0x18005b778`
- `RPCRT4!RpcExceptionFilter` at `0x18005b778`
- `fwbase!FwHResultToWindowsError` at `0x180005543`
- `fwbase!FwHResultToWindowsError` at `0x18000558a`
- `fwbase!FwHResultToWindowsError` at `0x1800055df`
- `fwbase!FwHResultToWindowsError` at `0x180005634`
- `fwbase!FwHResultToWindowsError` at `0x180005543`
- `fwbase!FwHResultToWindowsError` at `0x18000558a`
- `fwbase!FwHResultToWindowsError` at `0x1800055df`
- `fwbase!FwHResultToWindowsError` at `0x180005634`
- `FWPolicyIOMgr!FwDeleteAllRules` at `0x1800055d7`
- `FWPolicyIOMgr!FwDeleteAllRules` at `0x1800055d7`
- `FWPolicyIOMgr!FwDeleteRule` at `0x18000562c`
- `FWPolicyIOMgr!FwDeleteRule` at `0x18000562c`
- `FWPolicyIOMgr!FwDeleteSet` at `0x180005582`
- `FWPolicyIOMgr!FwDeleteSet` at `0x180005582`
- `FWPolicyIOMgr!FwDeleteAllSets` at `0x18000553b`
- `FWPolicyIOMgr!FwDeleteAllSets` at `0x18000553b`

## pseudocode

```c
__int64 __fastcall Int_FWDeleteObject(
        unsigned int a1,
        __int64 a2,
        __int64 (__fastcall *a3)(__int64, __int64),
        __int64 (__fastcall *a4)(__int64, __int64),
        __int64 a5,
        __int64 a6,
        unsigned int a7)
{
  __int64 (__fastcall *v7)(__int64, __int64); // r12
  int v8; // r9d
  FwPolicy2 *v10; // rcx
  unsigned int v11; // ebx
  __int64 v12; // rdx
  __int64 v13; // rax
  unsigned int v14; // eax
  __int64 v15; // rdx
  __int64 v16; // r9
  __int64 v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // rcx
  unsigned int v21; // eax
  unsigned int v22; // eax
  __int64 v23; // rdx
  unsigned int v24; // eax
  unsigned int v25; // eax
  __int64 v26; // rdx
  __int64 v27; // rcx
  unsigned int v28; // eax
  unsigned int v29; // eax
  __int64 v30; // rdx
  __int64 v31; // rcx
  unsigned int v32; // eax
  unsigned int v33; // eax
  __int64 v34; // [rsp+38h] [rbp-30h]
  int v35; // [rsp+78h] [rbp+10h]

  v35 = a2;
  v7 = a3;
  v8 = a2;
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 314, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids);
    v10 = WPP_GLOBAL_Control;
    v8 = v35;
  }
  v34 = 0;
  if ( !a5 )
  {
    v11 = 87;
    if ( v10 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 1) != 0 )
    {
      v12 = 315;
LABEL_8:
      WPP_SF_d(*((_QWORD *)v10 + 2), v12, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, 87);
      v10 = WPP_GLOBAL_Control;
      v13 = 0;
      goto LABEL_30;
    }
    goto LABEL_112;
  }
  if ( !v8 && !a6 )
  {
    v11 = 87;
    if ( v10 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 1) != 0 )
    {
      v12 = 316;
      goto LABEL_8;
    }
LABEL_112:
    v13 = v34;
    goto LABEL_30;
  }
  if ( a1 - 3 <= 1 && a7 - 1 > 1 )
  {
    v11 = 87;
    if ( v10 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 1) != 0 )
    {
      v12 = 317;
      goto LABEL_8;
    }
    goto LABEL_112;
  }
  v34 = a5;
  a3 = (__int64 (__fastcall *)(__int64, __int64))*(unsigned int *)(a5 + 4);
  if ( (unsigned int)a3 > 1 )
  {
    if ( (_DWORD)a3 != 2 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    v14 = Int_FWOpenGPOPolicyStore(a5);
    v11 = v14;
    if ( v14 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_29;
      v15 = 325;
      goto LABEL_26;
    }
    if ( !*(_QWORD *)(a5 + 56) )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    if ( a1 <= 2 )
    {
      v23 = 0;
      if ( v35 )
      {
        v24 = FwDeleteAllRules(*(_QWORD *)(a5 + 56));
        v14 = FwHResultToWindowsError(v24);
        v11 = v14;
        if ( !v14 )
          goto LABEL_43;
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_29;
        v15 = 326;
      }
      else
      {
        if ( a1 )
        {
          LOBYTE(v23) = a1 != 1;
          v23 = (unsigned int)(v23 + 1);
        }
        v25 = FwDeleteRule(*(_QWORD *)(a5 + 56), v23, a6);
        v14 = FwHResultToWindowsError(v25);
        v11 = v14;
        if ( !v14 )
          goto LABEL_43;
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_29;
        v15 = 327;
      }
    }
    else
    {
      v18 = a1 - 3;
      if ( (unsigned int)v18 >= 2 )
      {
        MicrosoftTelemetryAssertTriggeredArgs(v18, a1);
LABEL_43:
        v14 = Int_FWCloseGPOPolicyStore(a5, 1);
        v11 = v14;
        if ( !v14 )
          goto LABEL_28;
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_29;
        v15 = 330;
        goto LABEL_26;
      }
      v19 = 0;
      v20 = *(_QWORD *)(a5 + 56);
      if ( v35 )
      {
        LOBYTE(v19) = a1 != 3;
        v21 = FwDeleteAllSets(v20, v19, a7);
        v14 = FwHResultToWindowsError(v21);
        v11 = v14;
        if ( !v14 )
          goto LABEL_43;
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_29;
        v15 = 328;
      }
      else
      {
        LOBYTE(v19) = a1 != 3;
        v22 = FwDeleteSet(v20, v19, a7, a6);
        v14 = FwHResultToWindowsError(v22);
        v11 = v14;
        if ( !v14 )
          goto LABEL_43;
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_29;
        v15 = 329;
      }
    }
LABEL_26:
    v16 = v14;
LABEL_27:
    WPP_SF_d(*((_QWORD *)v10 + 2), v15, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, v16);
LABEL_28:
    v10 = WPP_GLOBAL_Control;
LABEL_29:
    v13 = a5;
    goto LABEL_30;
  }
  if ( !*(_QWORD *)(a5 + 32) || (v11 = 0, !*(_QWORD *)(a5 + 40)) )
  {
    v16 = 87;
    v11 = 87;
    if ( v10 == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)v10 + 28) & 1) == 0 )
      goto LABEL_112;
    v15 = 318;
    goto LABEL_27;
  }
  if ( a1 < 2 )
  {
LABEL_93:
    v30 = *(_QWORD *)(a5 + 40);
    v31 = *(_QWORD *)(a5 + 32);
    if ( v8 )
    {
      if ( (_DWORD)a3 )
        v7 = a4;
      v32 = v7(v31, v30);
      v11 = v32;
      if ( !v32 )
        goto LABEL_108;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 320, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, v32);
        v10 = WPP_GLOBAL_Control;
      }
      v13 = a5;
    }
    else
    {
      if ( (_DWORD)a3 )
        v7 = a4;
      v33 = ((__int64 (__fastcall *)(__int64, __int64, __int64))v7)(v31, v30, a6);
      v11 = v33;
      if ( !v33 )
        goto LABEL_108;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 321, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, v33);
        v10 = WPP_GLOBAL_Control;
      }
      v13 = a5;
    }
    goto LABEL_30;
  }
  a2 = a1 - 2;
  if ( a1 == 2 )
  {
    if ( *(_WORD *)(a5 + 2) < 0x20Au )
    {
      v11 = 50;
      if ( v10 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)v10 + 2), 319, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, 50);
        v10 = WPP_GLOBAL_Control;
      }
      v13 = a5;
      goto LABEL_30;
    }
    goto LABEL_93;
  }
  if ( a1 - 3 >= 2 )
  {
    MicrosoftTelemetryAssertTriggeredArgs(v10, a1);
LABEL_108:
    v10 = WPP_GLOBAL_Control;
    v13 = a5;
    goto LABEL_30;
  }
  v26 = *(_QWORD *)(a5 + 40);
  v27 = *(_QWORD *)(a5 + 32);
  if ( v8 )
  {
    if ( (_DWORD)a3 )
      v7 = a4;
    v28 = ((__int64 (__fastcall *)(__int64, __int64, _QWORD))v7)(v27, v26, a7);
    v11 = v28;
    if ( !v28 )
      goto LABEL_108;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 322, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, v28);
      v10 = WPP_GLOBAL_Control;
    }
    v13 = a5;
  }
  else
  {
    if ( (_DWORD)a3 )
      v7 = a4;
    v29 = ((__int64 (__fastcall *)(__int64, __int64, _QWORD, __int64))v7)(v27, v26, a7, a6);
    v11 = v29;
    if ( !v29 )
      goto LABEL_108;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 323, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, v29);
      v10 = WPP_GLOBAL_Control;
    }
    v13 = a5;
  }
LABEL_30:
  if ( (v11 & 0xFFFFFFFD) != 0 && v13 && *(_DWORD *)(v13 + 4) == 2 )
  {
    Int_FWCleanupGPOPolicyStore(v13, a2, a3);
    v10 = WPP_GLOBAL_Control;
  }
  if ( v10 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)v10 + 2), 331, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids);
  return v11;
}

```

## disassembly

```asm
0x1800052c0  mov     rax, rsp
0x1800052c3  mov     [rax+8], rbx
0x1800052c7  mov     [rax+18h], rsi
0x1800052cb  mov     [rax+20h], r9
0x1800052cf  mov     [rax+10h], edx
0x1800052d2  push    rdi
0x1800052d3  push    r12
0x1800052d5  push    r13
0x1800052d7  push    r14
0x1800052d9  push    r15
0x1800052db  sub     rsp, 40h
0x1800052df  mov     r12, r8
0x1800052e2  mov     r9d, edx
0x1800052e5  mov     r15d, ecx
0x1800052e8  lea     rsi, WPP_GLOBAL_Control
0x1800052ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800052f6  lea     r14, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x1800052fd  cmp     rcx, rsi
0x180005300  jz      short loc_180005325
0x180005302  test    byte ptr [rcx+1Ch], 8
0x180005306  jz      short loc_180005325
0x180005308  mov     edx, 13Ah
0x18000530d  mov     r8, r14
0x180005310  mov     rcx, [rcx+10h]
0x180005314  call    WPP_SF_
0x180005319  mov     rcx, cs:WPP_GLOBAL_Control
0x180005320  mov     r9d, [rsp+68h+arg_8]
0x180005325  xor     eax, eax
0x180005327  mov     [rsp+68h+var_30], rax
0x18000532c  mov     r13, [rsp+68h+arg_20]
0x180005334  test    r13, r13
0x180005337  jnz     short loc_180005375
0x180005339  lea     r9d, [rax+57h]
0x18000533d  mov     ebx, r9d
0x180005340  cmp     rcx, rsi
0x180005343  jz      loc_180005942
0x180005349  lea     edi, [rax+1]
0x18000534c  test    [rcx+1Ch], dil
0x180005350  jz      loc_180005942
0x180005356  mov     edx, 13Bh
0x18000535b  mov     r8, r14
0x18000535e  mov     rcx, [rcx+10h]
0x180005362  call    WPP_SF_d
0x180005367  mov     rcx, cs:WPP_GLOBAL_Control
0x18000536e  xor     eax, eax
0x180005370  jmp     loc_180005453
0x180005375  test    r9d, r9d
0x180005378  jnz     short loc_1800053AB
0x18000537a  cmp     [rsp+68h+arg_28], rax
0x180005382  jnz     short loc_1800053AB
0x180005384  mov     r9d, 57h ; 'W'
0x18000538a  mov     ebx, r9d
0x18000538d  cmp     rcx, rsi
0x180005390  jz      loc_180005942
0x180005396  lea     edi, [r9-56h]
0x18000539a  test    [rcx+1Ch], dil
0x18000539e  jz      loc_180005942
0x1800053a4  mov     edx, 13Ch
0x1800053a9  jmp     short loc_18000535B
0x1800053ab  lea     eax, [r15-3]
0x1800053af  mov     edi, 1
0x1800053b4  cmp     eax, edi
0x1800053b6  ja      short loc_1800053E9
0x1800053b8  mov     eax, [rsp+68h+arg_30]
0x1800053bf  dec     eax
0x1800053c1  cmp     eax, edi
0x1800053c3  jbe     short loc_1800053E9
0x1800053c5  lea     r9d, [rdi+56h]
0x1800053c9  mov     ebx, r9d
0x1800053cc  cmp     rcx, rsi
0x1800053cf  jz      loc_180005942
0x1800053d5  test    [rcx+1Ch], dil
0x1800053d9  jz      loc_180005942
0x1800053df  mov     edx, 13Dh
0x1800053e4  jmp     loc_18000535B
0x1800053e9  mov     rax, r13
0x1800053ec  mov     [rsp+68h+var_30], rax
0x1800053f1  mov     [rsp+68h+arg_20], rax
0x1800053f9  mov     r8d, [r13+4]
0x1800053fd  cmp     r8d, edi
0x180005400  jbe     loc_180005668
0x180005406  cmp     r8d, 2
0x18000540a  jz      short loc_180005411
0x18000540c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180005411  mov     rcx, r13
0x180005414  call    Int_FWOpenGPOPolicyStore
0x180005419  mov     ebx, eax
0x18000541b  test    eax, eax
0x18000541d  jz      loc_1800054AD
0x180005423  mov     rcx, cs:WPP_GLOBAL_Control
0x18000542a  cmp     rcx, rsi
0x18000542d  jz      short loc_180005450
0x18000542f  test    [rcx+1Ch], dil
0x180005433  jz      short loc_180005450
0x180005435  mov     edx, 145h
0x18000543a  mov     r9d, eax
0x18000543d  mov     r8, r14
0x180005440  mov     rcx, [rcx+10h]
0x180005444  call    WPP_SF_d
0x180005449  mov     rcx, cs:WPP_GLOBAL_Control
0x180005450  mov     rax, r13
0x180005453  test    ebx, 0FFFFFFFDh
0x180005459  jz      short loc_180005475
0x18000545b  test    rax, rax
0x18000545e  jz      short loc_180005475
0x180005460  cmp     dword ptr [rax+4], 2
0x180005464  jnz     short loc_180005475
0x180005466  mov     rcx, rax
0x180005469  call    Int_FWCleanupGPOPolicyStore
0x18000546e  mov     rcx, cs:WPP_GLOBAL_Control
0x180005475  cmp     rcx, rsi
0x180005478  jz      short loc_180005491
0x18000547a  test    byte ptr [rcx+1Ch], 8
0x18000547e  jz      short loc_180005491
0x180005480  mov     edx, 14Bh
0x180005485  mov     r8, r14
0x180005488  mov     rcx, [rcx+10h]
0x18000548c  call    WPP_SF_
0x180005491  mov     eax, ebx
0x180005493  lea     r11, [rsp+68h+var_28]
0x180005498  mov     rbx, [r11+30h]
0x18000549c  mov     rsi, [r11+40h]
0x1800054a0  mov     rsp, r11
0x1800054a3  pop     r15
0x1800054a5  pop     r14
0x1800054a7  pop     r13
0x1800054a9  pop     r12
0x1800054ab  pop     rdi
0x1800054ac  retn
0x1800054ad  cmp     qword ptr [r13+38h], 0
0x1800054b2  jnz     short loc_1800054B9
0x1800054b4  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800054b9  mov     ecx, r15d
0x1800054bc  test    r15d, r15d
0x1800054bf  jz      loc_1800055BE
0x1800054c5  sub     ecx, edi
0x1800054c7  jz      loc_1800055BE
0x1800054cd  sub     ecx, edi
0x1800054cf  jz      loc_1800055BE
0x1800054d5  sub     ecx, edi
0x1800054d7  jz      short loc_180005520
0x1800054d9  cmp     ecx, edi
0x1800054db  jz      short loc_180005520
0x1800054dd  mov     edx, r15d
0x1800054e0  call    MicrosoftTelemetryAssertTriggeredArgs
0x1800054e5  xor     r8d, r8d
0x1800054e8  mov     edx, edi
0x1800054ea  mov     rcx, r13
0x1800054ed  call    Int_FWCloseGPOPolicyStore
0x1800054f2  mov     ebx, eax
0x1800054f4  test    eax, eax
0x1800054f6  jz      loc_180005449
0x1800054fc  mov     rcx, cs:WPP_GLOBAL_Control
0x180005503  cmp     rcx, rsi
0x180005506  jz      loc_180005450
0x18000550c  test    [rcx+1Ch], dil
0x180005510  jz      loc_180005450
0x180005516  mov     edx, 14Ah
0x18000551b  jmp     loc_18000543A
0x180005520  xor     edx, edx
0x180005522  mov     r8d, [rsp+68h+arg_30]
0x18000552a  mov     rcx, [r13+38h]
0x18000552e  cmp     [rsp+68h+arg_8], edx
0x180005532  jz      short loc_180005573
0x180005534  cmp     r15d, 3
0x180005538  setnz   dl
0x18000553b  call    cs:__imp_FwDeleteAllSets
0x180005541  mov     ecx, eax
0x180005543  call    cs:__imp_FwHResultToWindowsError
0x180005549  mov     ebx, eax
0x18000554b  test    eax, eax
0x18000554d  jz      short loc_1800054E5
0x18000554f  mov     rcx, cs:WPP_GLOBAL_Control
0x180005556  cmp     rcx, rsi
0x180005559  jz      loc_180005450
0x18000555f  test    [rcx+1Ch], dil
0x180005563  jz      loc_180005450
0x180005569  mov     edx, 148h
0x18000556e  jmp     loc_18000543A
0x180005573  cmp     r15d, 3
0x180005577  setnz   dl
0x18000557a  mov     r9, [rsp+68h+arg_28]
0x180005582  call    cs:__imp_FwDeleteSet
0x180005588  mov     ecx, eax
0x18000558a  call    cs:__imp_FwHResultToWindowsError
0x180005590  mov     ebx, eax
0x180005592  test    eax, eax
0x180005594  jz      loc_1800054E5
0x18000559a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800055a1  cmp     rcx, rsi
0x1800055a4  jz      loc_180005450
0x1800055aa  test    [rcx+1Ch], dil
0x1800055ae  jz      loc_180005450
0x1800055b4  mov     edx, 149h
0x1800055b9  jmp     loc_18000543A
0x1800055be  xor     edx, edx
0x1800055c0  cmp     [rsp+68h+arg_8], edx
0x1800055c4  jz      short loc_180005613
0x1800055c6  test    r15d, r15d
0x1800055c9  jz      short loc_1800055D3
0x1800055cb  cmp     r15d, edi
0x1800055ce  setnz   dl
0x1800055d1  add     edx, edi
0x1800055d3  mov     rcx, [r13+38h]
0x1800055d7  call    cs:__imp_FwDeleteAllRules
0x1800055dd  mov     ecx, eax
0x1800055df  call    cs:__imp_FwHResultToWindowsError
0x1800055e5  mov     ebx, eax
0x1800055e7  test    eax, eax
0x1800055e9  jz      loc_1800054E5
0x1800055ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800055f6  cmp     rcx, rsi
0x1800055f9  jz      loc_180005450
0x1800055ff  test    [rcx+1Ch], dil
0x180005603  jz      loc_180005450
0x180005609  mov     edx, 146h
0x18000560e  jmp     loc_18000543A
0x180005613  test    r15d, r15d
0x180005616  jz      short loc_180005620
0x180005618  cmp     r15d, edi
0x18000561b  setnz   dl
0x18000561e  add     edx, edi
0x180005620  mov     r8, [rsp+68h+arg_28]
0x180005628  mov     rcx, [r13+38h]
0x18000562c  call    cs:__imp_FwDeleteRule
0x180005632  mov     ecx, eax
0x180005634  call    cs:__imp_FwHResultToWindowsError
0x18000563a  mov     ebx, eax
0x18000563c  test    eax, eax
0x18000563e  jz      loc_1800054E5
0x180005644  mov     rcx, cs:WPP_GLOBAL_Control
0x18000564b  cmp     rcx, rsi
0x18000564e  jz      loc_180005450
0x180005654  test    [rcx+1Ch], dil
0x180005658  jz      loc_180005450
0x18000565e  mov     edx, 147h
0x180005663  jmp     loc_18000543A
0x180005668  mov     r10, [r13+20h]
0x18000566c  test    r10, r10
0x18000566f  jz      loc_180005924
0x180005675  xor     ebx, ebx
0x180005677  mov     r11, [r13+28h]
0x18000567b  test    r11, r11
0x18000567e  jz      loc_180005924
0x180005684  mov     edx, r15d
0x180005687  test    r15d, r15d
0x18000568a  jz      loc_1800057D3
0x180005690  sub     edx, 1
0x180005693  jz      loc_1800057D3
0x180005699  sub     edx, 1
0x18000569c  jz      loc_18000578E
0x1800056a2  sub     edx, 1
0x1800056a5  jz      short loc_1800056B9
0x1800056a7  cmp     edx, 1
0x1800056aa  jz      short loc_1800056B9
0x1800056ac  mov     edx, r15d
0x1800056af  call    MicrosoftTelemetryAssertTriggeredArgs
0x1800056b4  jmp     loc_180005894
0x1800056b9  mov     rdx, r11
0x1800056bc  mov     rcx, r10
0x1800056bf  test    r9d, r9d
0x1800056c2  jz      short loc_180005725
0x1800056c4  test    r8d, r8d
0x1800056c7  cmovnz  r12, [rsp+68h+arg_18]
0x1800056d0  mov     r8d, [rsp+68h+arg_30]
0x1800056d8  mov     rax, r12
0x1800056db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056e0  mov     ebx, eax
0x1800056e2  mov     [rsp+68h+var_38], eax
0x1800056e6  test    eax, eax
0x1800056e8  jz      loc_180005894
0x1800056ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800056f5  cmp     rcx, rsi
0x1800056f8  jz      short loc_18000571B
0x1800056fa  test    [rcx+1Ch], dil
0x1800056fe  jz      short loc_18000571B
0x180005700  mov     edx, 142h
0x180005705  mov     r9d, eax
0x180005708  mov     r8, r14
0x18000570b  mov     rcx, [rcx+10h]
0x18000570f  call    WPP_SF_d
0x180005714  mov     rcx, cs:WPP_GLOBAL_Control
0x18000571b  mov     rax, [rsp+68h+var_30]
0x180005720  jmp     loc_180005453
0x180005725  test    r8d, r8d
0x180005728  cmovnz  r12, [rsp+68h+arg_18]
0x180005731  mov     r9, [rsp+68h+arg_28]
0x180005739  mov     r8d, [rsp+68h+arg_30]
0x180005741  mov     rax, r12
0x180005744  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005749  mov     ebx, eax
0x18000574b  mov     [rsp+68h+var_38], eax
0x18000574f  test    eax, eax
0x180005751  jz      loc_180005894
0x180005757  mov     rcx, cs:WPP_GLOBAL_Control
0x18000575e  cmp     rcx, rsi
0x180005761  jz      short loc_180005784
0x180005763  test    [rcx+1Ch], dil
0x180005767  jz      short loc_180005784
0x180005769  mov     edx, 143h
  ... truncated ...
```
