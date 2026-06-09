# WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics::_ActivateInternal(ushort const *)

- ea: `0x180012410`
- end: `0x1800127d0`
- name: `?_ActivateInternal@IncomingCallToastStatics@Calls@ApplicationModel@WindowsInternal@@MEAAJPEBG@Z`
- size: `960`
- prototype: `__int64 __fastcall(WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x1800011fc`
- `0x180001dc0`
- `0x1800027c0`
- `0x18000cf20`
- `0x18000cf2c`
- `0x180011e5c`
- `0x180011e68`
- `0x180012410`
- `0x180015944`
- `0x1800165c4`
- `0x180019010`

## import_xrefs

- `PhoneOm!PhoneAcceptIncomingEx` at `0x180012713`
- `PhoneOm!PhoneAcceptIncomingEx` at `0x180012713`
- `PhoneOm!PhoneRejectIncomingForTextReply` at `0x180012774`
- `PhoneOm!PhoneRejectIncomingForTextReply` at `0x180012774`
- `PhoneOm!PhoneDropAcceptEx` at `0x18001268c`
- `PhoneOm!PhoneDropAcceptEx` at `0x18001268c`
- `PhoneOm!PhoneRejectIncoming` at `0x180012605`
- `PhoneOm!PhoneRejectIncoming` at `0x180012605`
- `PhoneOm!PhoneAPIUninitialize` at `0x1800124d2`
- `PhoneOm!PhoneAPIUninitialize` at `0x1800125bb`
- `PhoneOm!PhoneAPIUninitialize` at `0x180012633`
- `PhoneOm!PhoneAPIUninitialize` at `0x1800126be`
- `PhoneOm!PhoneAPIUninitialize` at `0x180012745`
- `PhoneOm!PhoneAPIUninitialize` at `0x1800127a6`
- `PhoneOm!PhoneAPIUninitialize` at `0x1800124d2`
- `PhoneOm!PhoneAPIUninitialize` at `0x1800125bb`
- `PhoneOm!PhoneAPIUninitialize` at `0x180012633`
- `PhoneOm!PhoneAPIUninitialize` at `0x1800126be`
- `PhoneOm!PhoneAPIUninitialize` at `0x180012745`
- `PhoneOm!PhoneAPIUninitialize` at `0x1800127a6`
- `PhoneOm!PhoneAPIInitialize` at `0x18001243e`
- `PhoneOm!PhoneAPIInitialize` at `0x18001243e`

## pseudocode

```c
__int64 __fastcall WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics::_ActivateInternal(
        WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics *this,
        const unsigned __int16 *a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  __int64 v6; // r8
  __int64 v8; // rax
  int v9; // eax
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // rcx
  unsigned int v13; // edi
  __int64 v14; // rcx
  __int64 v15; // rcx
  int v16; // eax
  __int64 v17; // r8
  int v18; // eax
  __int64 v19; // r8
  int v20; // eax
  __int64 v21; // r8
  int v22; // eax
  __int64 v23; // r8
  unsigned int v24; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v25; // [rsp+34h] [rbp-CCh] BYREF
  unsigned int v26; // [rsp+38h] [rbp-C8h] BYREF
  _DWORD v27[2]; // [rsp+40h] [rbp-C0h] BYREF
  BOOL v28; // [rsp+48h] [rbp-B8h]
  char v29[420]; // [rsp+4Ch] [rbp-B4h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v30; // [rsp+1F0h] [rbp+F0h] BYREF
  unsigned int *v31; // [rsp+210h] [rbp+110h]
  __int64 v32; // [rsp+218h] [rbp+118h]

  v4 = PhoneAPIInitialize();
  v5 = v4;
  if ( v4 < 0 )
  {
    Log_HREvent_0((unsigned int)v4, 1, "OnecoreUAP\\internal\\Net\\inc\\phsmartpointers.h");
    Log_HREvent_1(v5, 1, v6, 879);
    return v5;
  }
  v8 = *(_QWORD *)this;
  v26 = -1;
  v25 = 0;
  v9 = (*(__int64 (__fastcall **)(WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics *, const unsigned __int16 *, unsigned int *, unsigned int *))(v8 + 184))(
         this,
         a2,
         &v26,
         &v25);
  v5 = v9;
  if ( v9 < 0 )
  {
    Log_HREvent_1((unsigned int)v9, 1, v11, 889);
    TraceLogging::IncomingCallToastActivated(v25, v26, v5);
    if ( (int)PhoneAPIUninitialize() >= 0 )
      return v5;
LABEL_30:
    Log_AssertionEvent_1(v12, "OnecoreUAP\\internal\\Net\\inc\\phsmartpointers.h", 62);
    MicrosoftTelemetryAssertTriggeredNoArgs();
    return v5;
  }
  v13 = v26;
  switch ( v26 )
  {
    case 0u:
      v22 = PhoneRejectIncomingForTextReply(&v25);
      v5 = v22;
      if ( v22 < 0 )
      {
        Log_HREvent_1((unsigned int)v22, 1, v23, 927);
        TraceLogging::IncomingCallToastActivated(v25, v26, v5);
        if ( (int)PhoneAPIUninitialize() >= 0 )
          return v5;
        goto LABEL_30;
      }
      break;
    case 1u:
      goto LABEL_25;
    case 2u:
      memset_0(v29, 0, 0x198u);
      v27[1] = v25;
      v27[0] = 0;
      v28 = 0;
      v18 = PhoneDropAcceptEx(v27);
      v5 = v18;
      if ( v18 < 0 )
      {
        Log_HREvent_1((unsigned int)v18, 1, v19, 907);
        TraceLogging::IncomingCallToastActivated(v25, v26, v5);
        if ( (int)PhoneAPIUninitialize() >= 0 )
          return v5;
        goto LABEL_30;
      }
      break;
    case 3u:
      v16 = PhoneRejectIncoming(&v25);
      v5 = v16;
      if ( v16 < 0 )
      {
        Log_HREvent_1((unsigned int)v16, 1, v17, 895);
        TraceLogging::IncomingCallToastActivated(v25, v26, v5);
        if ( (int)PhoneAPIUninitialize() >= 0 )
          return v5;
        goto LABEL_30;
      }
      break;
    default:
      if ( v26 != 4 )
      {
        v14 = v26 - 5;
        if ( (unsigned int)v14 >= 2 )
        {
          if ( (unsigned int)dword_180025038 > 4 )
          {
            v24 = v26;
            v32 = 4;
            v31 = &v24;
            tlgWriteTransfer_EventWriteTransfer((int)&dword_180025038, (int)&byte_180020A83, 0, 0, 3u, &v30);
          }
          v26 = -1;
          Log_AssertionEvent_2(v14, v10, 937);
          MicrosoftTelemetryAssertTriggeredNoArgs();
          break;
        }
      }
LABEL_25:
      memset_0(v27, 0, 0x1A4u);
      v27[0] = v25;
      v28 = v13 == 5;
      v20 = PhoneAcceptIncomingEx(v27);
      v5 = v20;
      if ( v20 < 0 )
      {
        Log_HREvent_1((unsigned int)v20, 1, v21, 921);
        TraceLogging::IncomingCallToastActivated(v25, v26, v5);
        if ( (int)PhoneAPIUninitialize() >= 0 )
          return v5;
        goto LABEL_30;
      }
      break;
  }
  TraceLogging::IncomingCallToastActivated(v25, v26, v5);
  if ( (int)PhoneAPIUninitialize() < 0 )
  {
    Log_AssertionEvent_1(v15, "OnecoreUAP\\internal\\Net\\inc\\phsmartpointers.h", 62);
    MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  return 0;
}

```

## disassembly

```asm
0x180012410  mov     [rsp-8+arg_10], rbx
0x180012415  push    rbp
0x180012416  push    rsi
0x180012417  push    rdi
0x180012418  lea     rbp, [rsp-130h]
0x180012420  sub     rsp, 230h
0x180012427  mov     rax, cs:__security_cookie
0x18001242e  xor     rax, rsp
0x180012431  mov     [rbp+140h+var_20], rax
0x180012438  mov     rsi, rdx
0x18001243b  mov     rdi, rcx
0x18001243e  call    cs:__imp_PhoneAPIInitialize
0x180012444  mov     ebx, eax
0x180012446  test    eax, eax
0x180012448  jns     short loc_18001247B
0x18001244a  mov     r9d, 33h ; '3'
0x180012450  lea     r8, aOnecoreuapInte_0; "OnecoreUAP\\internal\\Net\\inc\\phsmart"...
0x180012457  mov     ecx, eax
0x180012459  lea     edx, [r9-32h]
0x18001245d  call    Log_HREvent_0
0x180012462  mov     edx, 1
0x180012467  mov     r9d, 36Fh
0x18001246d  mov     ecx, ebx
0x18001246f  call    Log_HREvent_1
0x180012474  mov     eax, ebx
0x180012476  jmp     loc_1800125DE
0x18001247b  mov     rax, [rdi]
0x18001247e  lea     r9, [rsp+240h+var_20C]
0x180012483  lea     r8, [rsp+240h+var_208]
0x180012488  mov     [rsp+240h+var_208], 0FFFFFFFFh
0x180012490  mov     rdx, rsi
0x180012493  mov     [rsp+240h+var_20C], 0
0x18001249b  mov     rcx, rdi
0x18001249e  mov     rax, [rax+0B8h]
0x1800124a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800124aa  mov     ebx, eax
0x1800124ac  test    eax, eax
0x1800124ae  jns     short loc_1800124F8
0x1800124b0  mov     edx, 1
0x1800124b5  mov     r9d, 379h
0x1800124bb  mov     ecx, eax
0x1800124bd  call    Log_HREvent_1
0x1800124c2  mov     edx, [rsp+240h+var_208]
0x1800124c6  mov     r8d, ebx
0x1800124c9  mov     ecx, [rsp+240h+var_20C]
0x1800124cd  call    ?IncomingCallToastActivated@TraceLogging@@SAXIW4IncomingToastAction@Calls@ApplicationModel@WindowsInternal@@J@Z; TraceLogging::IncomingCallToastActivated(uint,WindowsInternal::ApplicationModel::Calls::IncomingToastAction,long)
0x1800124d2  call    cs:__imp_PhoneAPIUninitialize
0x1800124d8  test    eax, eax
0x1800124da  jns     short loc_180012474
0x1800124dc  mov     r8d, 3Eh ; '>'
0x1800124e2  lea     rdx, aOnecoreuapInte_0; "OnecoreUAP\\internal\\Net\\inc\\phsmart"...
0x1800124e9  call    Log_AssertionEvent_1
0x1800124ee  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800124f3  jmp     loc_180012474
0x1800124f8  mov     edi, [rsp+240h+var_208]
0x1800124fc  mov     ecx, edi
0x1800124fe  test    edi, edi
0x180012500  jz      loc_18001276F
0x180012506  sub     ecx, 1
0x180012509  jz      loc_1800126E8
0x18001250f  sub     ecx, 1
0x180012512  jz      loc_18001265D
0x180012518  sub     ecx, 1
0x18001251b  jz      loc_180012600
0x180012521  sub     ecx, 1
0x180012524  jz      loc_1800126E8
0x18001252a  sub     ecx, 1
0x18001252d  jz      loc_1800126E8
0x180012533  cmp     ecx, 1
0x180012536  jz      loc_1800126E8
0x18001253c  mov     eax, cs:dword_180025038
0x180012542  cmp     eax, 4
0x180012545  jbe     short loc_180012593
0x180012547  mov     eax, [rsp+240h+var_208]
0x18001254b  lea     rdx, byte_180020A83; int
0x180012552  mov     [rsp+240h+var_210], eax
0x180012556  lea     rcx, dword_180025038; int
0x18001255d  lea     rax, [rsp+240h+var_210]
0x180012562  mov     [rbp+140h+var_28], 4
0x18001256d  mov     [rbp+140h+var_30], rax
0x180012574  xor     r9d, r9d; int
0x180012577  lea     rax, [rbp+140h+var_50]
0x18001257e  xor     r8d, r8d; int
0x180012581  mov     [rsp+240h+var_218], rax; PEVENT_DATA_DESCRIPTOR
0x180012586  mov     [rsp+240h+var_220], 3; ULONG
0x18001258e  call    _tlgWriteTransfer_EventWriteTransfer
0x180012593  mov     r8d, 3A9h
0x180012599  mov     [rsp+240h+var_208], 0FFFFFFFFh
0x1800125a1  call    Log_AssertionEvent_2
0x1800125a6  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800125ab  mov     edx, [rsp+240h+var_208]
0x1800125af  mov     r8d, ebx
0x1800125b2  mov     ecx, [rsp+240h+var_20C]
0x1800125b6  call    ?IncomingCallToastActivated@TraceLogging@@SAXIW4IncomingToastAction@Calls@ApplicationModel@WindowsInternal@@J@Z; TraceLogging::IncomingCallToastActivated(uint,WindowsInternal::ApplicationModel::Calls::IncomingToastAction,long)
0x1800125bb  call    cs:__imp_PhoneAPIUninitialize
0x1800125c1  test    eax, eax
0x1800125c3  jns     short loc_1800125DC
0x1800125c5  mov     r8d, 3Eh ; '>'
0x1800125cb  lea     rdx, aOnecoreuapInte_0; "OnecoreUAP\\internal\\Net\\inc\\phsmart"...
0x1800125d2  call    Log_AssertionEvent_1
0x1800125d7  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800125dc  xor     eax, eax
0x1800125de  mov     rcx, [rbp+140h+var_20]
0x1800125e5  xor     rcx, rsp; StackCookie
0x1800125e8  call    __security_check_cookie
0x1800125ed  mov     rbx, [rsp+240h+arg_10]
0x1800125f5  add     rsp, 230h
0x1800125fc  pop     rdi
0x1800125fd  pop     rsi
0x1800125fe  pop     rbp
0x1800125ff  retn
0x180012600  lea     rcx, [rsp+240h+var_20C]
0x180012605  call    cs:__imp_PhoneRejectIncoming
0x18001260b  mov     ebx, eax
0x18001260d  test    eax, eax
0x18001260f  jns     short loc_1800125AB
0x180012611  mov     edx, 1
0x180012616  mov     r9d, 37Fh
0x18001261c  mov     ecx, eax
0x18001261e  call    Log_HREvent_1
0x180012623  mov     edx, [rsp+240h+var_208]
0x180012627  mov     r8d, ebx
0x18001262a  mov     ecx, [rsp+240h+var_20C]
0x18001262e  call    ?IncomingCallToastActivated@TraceLogging@@SAXIW4IncomingToastAction@Calls@ApplicationModel@WindowsInternal@@J@Z; TraceLogging::IncomingCallToastActivated(uint,WindowsInternal::ApplicationModel::Calls::IncomingToastAction,long)
0x180012633  call    cs:__imp_PhoneAPIUninitialize
0x180012639  test    eax, eax
0x18001263b  jns     loc_180012474
0x180012641  mov     r8d, 3Eh ; '>'
0x180012647  lea     rdx, aOnecoreuapInte_0; "OnecoreUAP\\internal\\Net\\inc\\phsmart"...
0x18001264e  call    Log_AssertionEvent_1
0x180012653  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180012658  jmp     loc_180012474
0x18001265d  xor     edx, edx; Val
0x18001265f  lea     rcx, [rsp+240h+var_1F4]; void *
0x180012664  mov     r8d, 198h; Size
0x18001266a  call    memset_0
0x18001266f  mov     eax, [rsp+240h+var_20C]
0x180012673  lea     rcx, [rsp+240h+var_200]
0x180012678  mov     [rsp+240h+var_1FC], eax
0x18001267c  mov     [rsp+240h+var_200], 0
0x180012684  mov     [rsp+240h+var_1F8], 0
0x18001268c  call    cs:__imp_PhoneDropAcceptEx
0x180012692  mov     ebx, eax
0x180012694  test    eax, eax
0x180012696  jns     loc_1800125AB
0x18001269c  mov     edx, 1
0x1800126a1  mov     r9d, 38Bh
0x1800126a7  mov     ecx, eax
0x1800126a9  call    Log_HREvent_1
0x1800126ae  mov     edx, [rsp+240h+var_208]
0x1800126b2  mov     r8d, ebx
0x1800126b5  mov     ecx, [rsp+240h+var_20C]
0x1800126b9  call    ?IncomingCallToastActivated@TraceLogging@@SAXIW4IncomingToastAction@Calls@ApplicationModel@WindowsInternal@@J@Z; TraceLogging::IncomingCallToastActivated(uint,WindowsInternal::ApplicationModel::Calls::IncomingToastAction,long)
0x1800126be  call    cs:__imp_PhoneAPIUninitialize
0x1800126c4  test    eax, eax
0x1800126c6  jns     loc_180012474
0x1800126cc  mov     r8d, 3Eh ; '>'
0x1800126d2  lea     rdx, aOnecoreuapInte_0; "OnecoreUAP\\internal\\Net\\inc\\phsmart"...
0x1800126d9  call    Log_AssertionEvent_1
0x1800126de  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800126e3  jmp     loc_180012474
0x1800126e8  xor     edx, edx; Val
0x1800126ea  lea     rcx, [rsp+240h+var_200]; void *
0x1800126ef  mov     r8d, 1A4h; Size
0x1800126f5  call    memset_0
0x1800126fa  mov     eax, [rsp+240h+var_20C]
0x1800126fe  lea     rcx, [rsp+240h+var_200]
0x180012703  mov     [rsp+240h+var_200], eax
0x180012707  xor     eax, eax
0x180012709  cmp     edi, 5
0x18001270c  setz    al
0x18001270f  mov     [rsp+240h+var_1F8], eax
0x180012713  call    cs:__imp_PhoneAcceptIncomingEx
0x180012719  mov     ebx, eax
0x18001271b  test    eax, eax
0x18001271d  jns     loc_1800125AB
0x180012723  mov     edx, 1
0x180012728  mov     r9d, 399h
0x18001272e  mov     ecx, eax
0x180012730  call    Log_HREvent_1
0x180012735  mov     edx, [rsp+240h+var_208]
0x180012739  mov     r8d, ebx
0x18001273c  mov     ecx, [rsp+240h+var_20C]
0x180012740  call    ?IncomingCallToastActivated@TraceLogging@@SAXIW4IncomingToastAction@Calls@ApplicationModel@WindowsInternal@@J@Z; TraceLogging::IncomingCallToastActivated(uint,WindowsInternal::ApplicationModel::Calls::IncomingToastAction,long)
0x180012745  call    cs:__imp_PhoneAPIUninitialize
0x18001274b  test    eax, eax
0x18001274d  jns     loc_180012474
0x180012753  mov     r8d, 3Eh ; '>'
0x180012759  lea     rdx, aOnecoreuapInte_0; "OnecoreUAP\\internal\\Net\\inc\\phsmart"...
0x180012760  call    Log_AssertionEvent_1
0x180012765  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001276a  jmp     loc_180012474
0x18001276f  lea     rcx, [rsp+240h+var_20C]
0x180012774  call    cs:__imp_PhoneRejectIncomingForTextReply
0x18001277a  mov     ebx, eax
0x18001277c  test    eax, eax
0x18001277e  jns     loc_1800125AB
0x180012784  mov     edx, 1
0x180012789  mov     r9d, 39Fh
0x18001278f  mov     ecx, eax
0x180012791  call    Log_HREvent_1
0x180012796  mov     edx, [rsp+240h+var_208]
0x18001279a  mov     r8d, ebx
0x18001279d  mov     ecx, [rsp+240h+var_20C]
0x1800127a1  call    ?IncomingCallToastActivated@TraceLogging@@SAXIW4IncomingToastAction@Calls@ApplicationModel@WindowsInternal@@J@Z; TraceLogging::IncomingCallToastActivated(uint,WindowsInternal::ApplicationModel::Calls::IncomingToastAction,long)
0x1800127a6  call    cs:__imp_PhoneAPIUninitialize
0x1800127ac  test    eax, eax
0x1800127ae  jns     loc_180012474
0x1800127b4  mov     r8d, 3Eh ; '>'
0x1800127ba  lea     rdx, aOnecoreuapInte_0; "OnecoreUAP\\internal\\Net\\inc\\phsmart"...
0x1800127c1  call    Log_AssertionEvent_1
0x1800127c6  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800127cb  jmp     loc_180012474
```
