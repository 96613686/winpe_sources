# BfsResealBitLockerWithRetry

- ea: `0x180048078`
- end: `0x180048418`
- name: `BfsResealBitLockerWithRetry`
- size: `928`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x18003ee78`

## callees

- `0x18000282c`
- `0x180002858`
- `0x180002ca0`
- `0x1800078b0`
- `0x1800085d4`
- `0x180048078`
- `0x180048420`
- `0x180048664`
- `0x180048690`
- `0x18004ccf0`
- `0x18004cdac`
- `0x18004cdd4`
- `0x18004d778`
- `0x18004d7b4`
- `0x18005e010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180048102`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180048102`

## string_xrefs

- `0x180048157`: `BfspOpenFveApi`
- `0x18004818c`: `FveOpenVolumeW failed.RetryCount = %dHRESULT = [%x]`
- `0x180048146`: `BfspOpenFveApi failed.RetryCount = %dFveApiFound = %d,HRESULT = [%x]`
- `0x18004819e`: `FveOpenVolumeW`
- `0x18004822a`: `BfsTryCommitFveChanges failed.RetryCount = %dHRESULT = [%x]`
- `0x18004823c`: `BfsTryCommitFveChanges`

## pseudocode

```c
__int64 __fastcall BfsResealBitLockerWithRetry(__int64 a1)
{
  unsigned int v2; // r14d
  unsigned int v3; // edi
  int v4; // ebx
  const wchar_t *v5; // rsi
  int v6; // eax
  int v7; // eax
  int v8; // eax
  int v9; // eax
  __int16 *v10; // rdx
  int v11; // r9d
  __int64 v13; // [rsp+20h] [rbp-99h]
  int v14; // [rsp+20h] [rbp-99h]
  unsigned int v15; // [rsp+30h] [rbp-89h] BYREF
  unsigned int v16; // [rsp+34h] [rbp-85h] BYREF
  unsigned int v17; // [rsp+38h] [rbp-81h] BYREF
  unsigned int v18; // [rsp+3Ch] [rbp-7Dh] BYREF
  unsigned int v19; // [rsp+40h] [rbp-79h] BYREF
  __int64 v20; // [rsp+48h] [rbp-71h] BYREF
  _QWORD v21[2]; // [rsp+50h] [rbp-69h] BYREF
  _BYTE v22[16]; // [rsp+60h] [rbp-59h] BYREF
  __int64 (__fastcall *v23)(__int64, __int64, __int64 *); // [rsp+70h] [rbp-49h]
  _QWORD *v24; // [rsp+80h] [rbp-39h]
  __int64 v25; // [rsp+88h] [rbp-31h]
  void (*v26)(void); // [rsp+90h] [rbp-29h]
  __int64 v27; // [rsp+98h] [rbp-21h]
  unsigned int *v28; // [rsp+A0h] [rbp-19h] BYREF
  __int64 v29; // [rsp+A8h] [rbp-11h]
  unsigned int *v30; // [rsp+B0h] [rbp-9h]
  __int64 v31; // [rsp+B8h] [rbp-1h]
  unsigned int *v32; // [rsp+C0h] [rbp+7h]
  __int64 v33; // [rsp+C8h] [rbp+Fh]
  unsigned int *v34; // [rsp+D0h] [rbp+17h]
  __int64 v35; // [rsp+D8h] [rbp+1Fh]

  memset_0(v22, 0, 0x80u);
  v2 = 0;
  v20 = -1;
  v16 = 0;
  v15 = 0;
  BfspLogInitializeFromFlags(80);
  v3 = 0;
  if ( !a1 )
  {
    v4 = -2147024809;
    v5 = L"InvalidArg";
LABEL_21:
    BfspLogMessage(4, L"BfsResealBitLockerWithRetry failed.RetryCount = %dHRESULT = [%x]", v3, (unsigned int)v4);
    goto LABEL_22;
  }
  v5 = L"NA";
  do
  {
    if ( v3 )
      Sleep(0x1F4u);
    if ( v20 != -1 )
    {
      v26();
      v20 = -1;
    }
    v6 = BfspOpenFveApi((__int64)v22, &v16);
    v2 = v16;
    v4 = v6;
    if ( v6 >= 0 )
    {
      v7 = v23(a1, 1, &v20);
      v4 = v7;
      if ( v7 >= 0 )
      {
        v8 = ((__int64 (__fastcall *)(__int64, __int64, unsigned int *))v29)(v20, 4, &v15);
        v4 = v8;
        if ( v8 >= 0 )
        {
          if ( (v15 & 8) != 0 )
          {
            v9 = BfsTryCommitFveChanges(v20, v22);
            v4 = v9;
            if ( v9 >= 0 )
              goto LABEL_22;
            BfspLogMessage(4, L"BfsTryCommitFveChanges failed.RetryCount = %dHRESULT = [%x]", v3, (unsigned int)v9);
            v5 = L"BfsTryCommitFveChanges";
          }
          else
          {
            v4 = -2147467259;
            BfspLogMessage(4, L"FveKeyManagement Flagout unexpected.RetryCount = %dFlagOut = %d,HRESULT = [%x]", v3);
            v5 = L"FveKeyManagementUnexpected";
          }
        }
        else
        {
          BfspLogMessage(4, L"FveKeyManagement failed.RetryCount = %dHRESULT = [%x]", v3, (unsigned int)v8);
          v5 = L"FveKeyManagement";
        }
      }
      else
      {
        BfspLogMessage(4, L"FveOpenVolumeW failed.RetryCount = %dHRESULT = [%x]", v3, (unsigned int)v7);
        v5 = L"FveOpenVolumeW";
      }
    }
    else
    {
      LODWORD(v13) = v6;
      BfspLogMessage(3, L"BfspOpenFveApi failed.RetryCount = %dFveApiFound = %d,HRESULT = [%x]", v3, v16, v13);
      v5 = L"BfspOpenFveApi";
      if ( !v2 )
      {
        v4 = 0;
        goto LABEL_22;
      }
    }
    ++v3;
  }
  while ( v3 < 3 );
  if ( v4 < 0 )
    goto LABEL_21;
LABEL_22:
  if ( v20 != -1 )
  {
    v26();
    v20 = -1;
  }
  BfspCloseFveApi(v22);
  BfspLogDestroy();
  if ( (int)RegisterBfsTelemetryProvider() >= 0 )
  {
    if ( v4 >= 0 )
    {
      if ( (unsigned int)dword_1800A3150 <= 5 || !(unsigned __int8)tlgKeywordOn(&dword_1800A3150, 0x800000000000LL) )
        goto LABEL_33;
      v21[0] = 0x1000000;
      v24 = v21;
      v10 = &word_1800955A6;
      v19 = v15;
      v26 = (void (*)(void))&v19;
      v28 = &v18;
      v30 = &v17;
      v14 = 6;
      v25 = 8;
      v27 = 4;
      v29 = 4;
      v17 = v2;
    }
    else
    {
      if ( (unsigned int)dword_1800A3150 <= 5 || !(unsigned __int8)tlgKeywordOn(&dword_1800A3150, 0x800000000000LL) )
        goto LABEL_33;
      v21[0] = 0x1000000;
      v24 = v21;
      v16 = v4;
      v26 = (void (*)(void))&v16;
      v25 = 8;
      v27 = 4;
      tlgCreate1Sz_wchar_t(&v28, v5);
      v30 = &v17;
      v10 = (__int16 *)byte_180095741;
      v17 = v15;
      v32 = &v18;
      v34 = &v19;
      v14 = v11;
      v33 = 4;
      v19 = v2;
      v35 = 4;
    }
    v18 = v3;
    v31 = 4;
    tlgWriteTransfer_EventWriteTransfer(&dword_1800A3150, v10, 0, 0, v14, v22);
LABEL_33:
    UnregisterBfsTelemetryProvider();
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180048078  mov     [rsp-8+arg_8], rbx
0x18004807d  mov     [rsp-8+arg_10], rsi
0x180048082  push    rbp
0x180048083  push    rdi
0x180048084  push    r13
0x180048086  push    r14
0x180048088  push    r15
0x18004808a  lea     rbp, [rsp-37h]
0x18004808f  sub     rsp, 0F0h
0x180048096  mov     rax, cs:__security_cookie
0x18004809d  xor     rax, rsp
0x1800480a0  mov     [rbp+57h+var_30], rax
0x1800480a4  mov     r15, rcx
0x1800480a7  xor     edx, edx; Val
0x1800480a9  lea     rcx, [rbp+57h+var_B0]; void *
0x1800480ad  mov     r8d, 80h; Size
0x1800480b3  call    memset_0
0x1800480b8  xor     r14d, r14d
0x1800480bb  mov     [rbp+57h+var_C8], 0FFFFFFFFFFFFFFFFh
0x1800480c3  mov     [rsp+110h+var_DC], r14d
0x1800480c8  mov     [rsp+110h+var_E0], r14d
0x1800480cd  lea     ecx, [r14+50h]
0x1800480d1  call    BfspLogInitializeFromFlags
0x1800480d6  xor     edi, edi
0x1800480d8  lea     r13d, [r14+4]
0x1800480dc  test    r15, r15
0x1800480df  jnz     short loc_1800480F2
0x1800480e1  mov     ebx, 80070057h
0x1800480e6  lea     rsi, aInvalidarg; "InvalidArg"
0x1800480ed  jmp     loc_180048252
0x1800480f2  lea     rsi, aNa; "NA"
0x1800480f9  test    edi, edi
0x1800480fb  jz      short loc_180048108
0x1800480fd  mov     ecx, 1F4h; dwMilliseconds
0x180048102  call    cs:__imp_Sleep
0x180048108  mov     rcx, [rbp+57h+var_C8]
0x18004810c  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180048110  jz      short loc_180048123
0x180048112  mov     rax, [rbp+57h+var_80]
0x180048116  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004811b  mov     [rbp+57h+var_C8], 0FFFFFFFFFFFFFFFFh
0x180048123  lea     rdx, [rsp+110h+var_DC]
0x180048128  lea     rcx, [rbp+57h+var_B0]
0x18004812c  call    BfspOpenFveApi
0x180048131  mov     r14d, [rsp+110h+var_DC]
0x180048136  mov     ebx, eax
0x180048138  test    eax, eax
0x18004813a  jns     short loc_18004816E
0x18004813c  mov     r9d, r14d
0x18004813f  mov     dword ptr [rsp+110h+var_F0], eax
0x180048143  mov     r8d, edi
0x180048146  lea     rdx, aBfspopenfveapi_0; "BfspOpenFveApi failed.RetryCount = %dFv"...
0x18004814d  mov     ecx, 3
0x180048152  call    BfspLogMessage
0x180048157  lea     rsi, aBfspopenfveapi; "BfspOpenFveApi"
0x18004815e  test    r14d, r14d
0x180048161  jnz     loc_180048243
0x180048167  xor     ebx, ebx
0x180048169  jmp     loc_180048267
0x18004816e  mov     rax, [rbp+57h+var_A0]
0x180048172  lea     r8, [rbp+57h+var_C8]
0x180048176  mov     edx, 1
0x18004817b  mov     rcx, r15
0x18004817e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048183  mov     ebx, eax
0x180048185  test    eax, eax
0x180048187  jns     short loc_1800481AA
0x180048189  mov     r9d, eax
0x18004818c  lea     rdx, aFveopenvolumew_0; "FveOpenVolumeW failed.RetryCount = %dHR"...
0x180048193  mov     r8d, edi
0x180048196  mov     ecx, r13d
0x180048199  call    BfspLogMessage
0x18004819e  lea     rsi, aFveopenvolumew; "FveOpenVolumeW"
0x1800481a5  jmp     loc_180048243
0x1800481aa  mov     rcx, [rbp+57h+var_C8]
0x1800481ae  lea     r8, [rsp+110h+var_E0]
0x1800481b3  mov     rax, [rbp+57h+var_68]
0x1800481b7  mov     edx, r13d
0x1800481ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800481bf  mov     ebx, eax
0x1800481c1  test    eax, eax
0x1800481c3  jns     short loc_1800481E3
0x1800481c5  mov     r9d, eax
0x1800481c8  lea     rdx, aFvekeymanageme_3; "FveKeyManagement failed.RetryCount = %d"...
0x1800481cf  mov     r8d, edi
0x1800481d2  mov     ecx, r13d
0x1800481d5  call    BfspLogMessage
0x1800481da  lea     rsi, aFvekeymanageme_0; "FveKeyManagement"
0x1800481e1  jmp     short loc_180048243
0x1800481e3  mov     r9d, [rsp+110h+var_E0]
0x1800481e8  test    r9b, 8
0x1800481ec  jnz     short loc_180048214
0x1800481ee  mov     eax, 80004005h
0x1800481f3  lea     rdx, aFvekeymanageme_1; "FveKeyManagement Flagout unexpected.Ret"...
0x1800481fa  mov     r8d, edi
0x1800481fd  mov     dword ptr [rsp+110h+var_F0], eax
0x180048201  mov     ecx, r13d
0x180048204  mov     ebx, eax
0x180048206  call    BfspLogMessage
0x18004820b  lea     rsi, aFvekeymanageme_2; "FveKeyManagementUnexpected"
0x180048212  jmp     short loc_180048243
0x180048214  mov     rcx, [rbp+57h+var_C8]
0x180048218  lea     rdx, [rbp+57h+var_B0]
0x18004821c  call    BfsTryCommitFveChanges
0x180048221  mov     ebx, eax
0x180048223  test    eax, eax
0x180048225  jns     short loc_180048267
0x180048227  mov     r9d, eax
0x18004822a  lea     rdx, aBfstrycommitfv; "BfsTryCommitFveChanges failed.RetryCoun"...
0x180048231  mov     r8d, edi
0x180048234  mov     ecx, r13d
0x180048237  call    BfspLogMessage
0x18004823c  lea     rsi, aBfstrycommitfv_0; "BfsTryCommitFveChanges"
0x180048243  inc     edi
0x180048245  cmp     edi, 3
0x180048248  jb      loc_1800480F9
0x18004824e  test    ebx, ebx
0x180048250  jns     short loc_180048267
0x180048252  mov     r9d, ebx
0x180048255  lea     rdx, aBfsresealbitlo; "BfsResealBitLockerWithRetry failed.Retr"...
0x18004825c  mov     r8d, edi
0x18004825f  mov     ecx, r13d
0x180048262  call    BfspLogMessage
0x180048267  mov     rcx, [rbp+57h+var_C8]
0x18004826b  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18004826f  jz      short loc_180048282
0x180048271  mov     rax, [rbp+57h+var_80]
0x180048275  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004827a  mov     [rbp+57h+var_C8], 0FFFFFFFFFFFFFFFFh
0x180048282  lea     rcx, [rbp+57h+var_B0]
0x180048286  call    BfspCloseFveApi
0x18004828b  call    BfspLogDestroy
0x180048290  call    RegisterBfsTelemetryProvider
0x180048295  test    eax, eax
0x180048297  js      loc_1800483EE
0x18004829d  mov     eax, cs:dword_1800A3150
0x1800482a3  test    ebx, ebx
0x1800482a5  jns     loc_180048350
0x1800482ab  cmp     eax, 5
0x1800482ae  jbe     loc_1800483E9
0x1800482b4  mov     rdx, 800000000000h
0x1800482be  lea     rcx, dword_1800A3150
0x1800482c5  call    _tlgKeywordOn
0x1800482ca  test    al, al
0x1800482cc  jz      loc_1800483E9
0x1800482d2  lea     rax, [rbp+57h+var_C0]
0x1800482d6  mov     [rbp+57h+var_C0], 1000000h
0x1800482de  mov     [rbp+57h+var_90], rax
0x1800482e2  lea     rcx, [rbp+57h+var_70]
0x1800482e6  lea     rax, [rsp+110h+var_DC]
0x1800482eb  mov     [rsp+110h+var_DC], ebx
0x1800482ef  mov     r9d, 8
0x1800482f5  mov     [rbp+57h+var_80], rax
0x1800482f9  mov     rdx, rsi
0x1800482fc  mov     [rbp+57h+var_88], r9
0x180048300  mov     [rbp+57h+var_78], r13
0x180048304  call    _tlgCreate1Sz_wchar_t
0x180048309  mov     ecx, [rsp+110h+var_E0]
0x18004830d  lea     rax, [rsp+110h+var_D8]
0x180048312  mov     [rbp+57h+var_60], rax
0x180048316  lea     rdx, byte_180095741
0x18004831d  lea     rax, [rbp+57h+var_D4]
0x180048321  mov     [rsp+110h+var_D8], ecx
0x180048325  mov     [rbp+57h+var_50], rax
0x180048329  lea     rax, [rbp+57h+var_D0]
0x18004832d  mov     [rbp+57h+var_40], rax
0x180048331  lea     rax, [rbp+57h+var_B0]
0x180048335  mov     [rsp+110h+var_E8], rax
0x18004833a  mov     dword ptr [rsp+110h+var_F0], r9d
0x18004833f  mov     [rbp+57h+var_48], r13
0x180048343  mov     [rbp+57h+var_D0], r14d
0x180048347  mov     [rbp+57h+var_38], r13
0x18004834b  jmp     loc_1800483D0
0x180048350  cmp     eax, 5
0x180048353  jbe     loc_1800483E9
0x180048359  mov     rdx, 800000000000h
0x180048363  lea     rcx, dword_1800A3150
0x18004836a  call    _tlgKeywordOn
0x18004836f  test    al, al
0x180048371  jz      short loc_1800483E9
0x180048373  lea     rax, [rbp+57h+var_C0]
0x180048377  mov     [rbp+57h+var_C0], 1000000h
0x18004837f  mov     [rbp+57h+var_90], rax
0x180048383  lea     rdx, word_1800955A6
0x18004838a  mov     eax, [rsp+110h+var_E0]
0x18004838e  mov     [rbp+57h+var_D0], eax
0x180048391  lea     rax, [rbp+57h+var_D0]
0x180048395  mov     [rbp+57h+var_80], rax
0x180048399  lea     rax, [rbp+57h+var_D4]
0x18004839d  mov     [rbp+57h+var_70], rax
0x1800483a1  lea     rax, [rsp+110h+var_D8]
0x1800483a6  mov     [rbp+57h+var_60], rax
0x1800483aa  lea     rax, [rbp+57h+var_B0]
0x1800483ae  mov     [rsp+110h+var_E8], rax
0x1800483b3  mov     dword ptr [rsp+110h+var_F0], 6
0x1800483bb  mov     [rbp+57h+var_88], 8
0x1800483c3  mov     [rbp+57h+var_78], r13
0x1800483c7  mov     [rbp+57h+var_68], r13
0x1800483cb  mov     [rsp+110h+var_D8], r14d
0x1800483d0  xor     r9d, r9d
0x1800483d3  mov     [rbp+57h+var_D4], edi
0x1800483d6  xor     r8d, r8d
0x1800483d9  mov     [rbp+57h+var_58], r13
0x1800483dd  lea     rcx, dword_1800A3150
0x1800483e4  call    _tlgWriteTransfer_EventWriteTransfer
0x1800483e9  call    UnregisterBfsTelemetryProvider
0x1800483ee  mov     eax, ebx
0x1800483f0  mov     rcx, [rbp+57h+var_30]
0x1800483f4  xor     rcx, rsp; StackCookie
0x1800483f7  call    __security_check_cookie
0x1800483fc  lea     r11, [rsp+110h+var_20]
0x180048404  mov     rbx, [r11+38h]
0x180048408  mov     rsi, [r11+40h]
0x18004840c  mov     rsp, r11
0x18004840f  pop     r15
0x180048411  pop     r14
0x180048413  pop     r13
0x180048415  pop     rdi
0x180048416  pop     rbp
0x180048417  retn
```
