# WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics::_ShowOrUpdate(uint)

- ea: `0x1800152a0`
- end: `0x18001564c`
- name: `?_ShowOrUpdate@IncomingCallToastStatics@Calls@ApplicationModel@WindowsInternal@@MEAAJI@Z`
- size: `940`
- prototype: `__int64 __fastcall(WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x180001dc0`
- `0x1800021b4`
- `0x1800027c0`
- `0x18000cf20`
- `0x18000cf2c`
- `0x1800117e4`
- `0x180011e68`
- `0x1800152a0`
- `0x180015b3c`
- `0x1800165c4`
- `0x1800187e0`
- `0x180019010`

## import_xrefs

- `PhoneOm!PhoneGetCallInfo` at `0x18001532c`
- `PhoneOm!PhoneGetCallInfo` at `0x18001532c`
- `PhoneOm!PhoneAPIUninitialize` at `0x18001533b`
- `PhoneOm!PhoneAPIUninitialize` at `0x18001537b`
- `PhoneOm!PhoneAPIUninitialize` at `0x180015422`
- `PhoneOm!PhoneAPIUninitialize` at `0x1800154d9`
- `PhoneOm!PhoneAPIUninitialize` at `0x180015599`
- `PhoneOm!PhoneAPIUninitialize` at `0x180015607`
- `PhoneOm!PhoneAPIUninitialize` at `0x18001533b`
- `PhoneOm!PhoneAPIUninitialize` at `0x18001537b`
- `PhoneOm!PhoneAPIUninitialize` at `0x180015422`
- `PhoneOm!PhoneAPIUninitialize` at `0x1800154d9`
- `PhoneOm!PhoneAPIUninitialize` at `0x180015599`
- `PhoneOm!PhoneAPIUninitialize` at `0x180015607`
- `PhoneOm!PhoneAPIInitialize` at `0x1800152d5`
- `PhoneOm!PhoneAPIInitialize` at `0x1800152d5`

## string_xrefs

- `0x180015508`: `IncomingCall`

## pseudocode

```c
__int64 __fastcall WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics::_ShowOrUpdate(
        WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics *this,
        unsigned int a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  __int64 v5; // r8
  int v7; // eax
  __int64 v8; // r8
  __int64 v9; // rcx
  __int64 v10; // rcx
  int v11; // eax
  __int64 v12; // r8
  unsigned int v13; // edi
  __int64 v14; // rcx
  int v15; // eax
  __int64 v16; // r8
  int v17; // eax
  __int64 v18; // r8
  unsigned int v19; // [rsp+50h] [rbp-B0h] BYREF
  void *Block[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int16 v21; // [rsp+68h] [rbp-98h] BYREF
  __int64 v22; // [rsp+6Ah] [rbp-96h]
  int v23; // [rsp+72h] [rbp-8Eh]
  __int16 v24; // [rsp+76h] [rbp-8Ah]
  void *v25[2]; // [rsp+78h] [rbp-88h] BYREF
  __int16 v26; // [rsp+88h] [rbp-78h] BYREF
  __int64 v27; // [rsp+8Ah] [rbp-76h]
  int v28; // [rsp+92h] [rbp-6Eh]
  __int16 v29; // [rsp+96h] [rbp-6Ah]
  _BYTE v30[6608]; // [rsp+A0h] [rbp-60h] BYREF

  v19 = a2;
  v3 = PhoneAPIInitialize();
  v4 = v3;
  if ( v3 < 0 )
  {
    Log_HREvent_0((unsigned int)v3, 1, "OnecoreUAP\\internal\\Net\\inc\\phsmartpointers.h");
    Log_HREvent_1(v4, 1, v5, 183);
    return v4;
  }
  memset_0(v30, 0, 0x19C8u);
  v7 = PhoneGetCallInfo(&v19, v30);
  v4 = v7;
  if ( v7 != -2147023728 )
  {
    if ( v7 < 0 )
    {
      Log_HREvent_1((unsigned int)v7, 1, v8, 193);
      if ( (int)PhoneAPIUninitialize() < 0 )
      {
        Log_AssertionEvent_1(v10, "OnecoreUAP\\internal\\Net\\inc\\phsmartpointers.h", 62);
        MicrosoftTelemetryAssertTriggeredNoArgs();
      }
      return v4;
    }
    v22 = 0;
    v24 = 0;
    v23 = 0;
    Block[0] = &v21;
    Block[1] = &v21;
    v21 = 0;
    v11 = (*(__int64 (__fastcall **)(WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics *, _BYTE *, void **, _QWORD))(*(_QWORD *)this + 80LL))(
            this,
            v30,
            Block,
            0);
    v13 = v11;
    if ( v11 >= 0 )
    {
      v27 = 0;
      v29 = 0;
      v28 = 0;
      v25[0] = &v26;
      v25[1] = &v26;
      v26 = 0;
      v15 = tlx::assign_sprintf<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(
              v25,
              L"%u",
              v19);
      v13 = v15;
      if ( v15 >= 0 )
      {
        v17 = (*(__int64 (__fastcall **)(WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics *, _QWORD, const unsigned __int16 *, const unsigned __int16 *, void *, void *, const unsigned __int16 *, _DWORD))(*(_QWORD *)this + 104LL))(
                this,
                v19,
                L"NonImmersivePackage",
                L"Windows.Systemtoast.Calling",
                Block[0],
                v25[0],
                L"IncomingCall",
                0);
        v13 = v17;
        if ( v17 >= 0 )
        {
          TraceLogging::IncomingCallToastNotificationSent(v19, v4, (struct PH_CALL_INFO *)v30);
          if ( v25[0] != &v26 )
            operator delete(v25[0]);
          if ( Block[0] != &v21 )
            operator delete(Block[0]);
          if ( (int)PhoneAPIUninitialize() >= 0 )
            return 0;
          goto LABEL_35;
        }
        Log_HREvent_1((unsigned int)v17, 1, v18, 202);
        if ( v25[0] != &v26 )
          operator delete(v25[0]);
        if ( Block[0] != &v21 )
          operator delete(Block[0]);
        if ( (int)PhoneAPIUninitialize() >= 0 )
          return v13;
      }
      else
      {
        Log_HREvent_1((unsigned int)v15, 1, v16, 199);
        if ( v25[0] != &v26 )
          operator delete(v25[0]);
        if ( Block[0] != &v21 )
          operator delete(Block[0]);
        if ( (int)PhoneAPIUninitialize() >= 0 )
          return v13;
      }
    }
    else
    {
      Log_HREvent_1((unsigned int)v11, 1, v12, 196);
      if ( Block[0] != &v21 )
        operator delete(Block[0]);
      if ( (int)PhoneAPIUninitialize() >= 0 )
        return v13;
    }
    Log_AssertionEvent_1(v14, "OnecoreUAP\\internal\\Net\\inc\\phsmartpointers.h", 62);
    MicrosoftTelemetryAssertTriggeredNoArgs();
    return v13;
  }
  if ( (int)PhoneAPIUninitialize() < 0 )
  {
LABEL_35:
    Log_AssertionEvent_1(v9, "OnecoreUAP\\internal\\Net\\inc\\phsmartpointers.h", 62);
    MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  return 0;
}

```

## disassembly

```asm
0x1800152a0  mov     [rsp-8+arg_10], rbx
0x1800152a5  push    rbp
0x1800152a6  push    rsi
0x1800152a7  push    rdi
0x1800152a8  lea     rbp, [rsp-1980h]
0x1800152b0  mov     eax, 1A80h
0x1800152b5  call    _alloca_probe
0x1800152ba  sub     rsp, rax
0x1800152bd  mov     rax, cs:__security_cookie
0x1800152c4  xor     rax, rsp
0x1800152c7  mov     [rbp+1990h+var_20], rax
0x1800152ce  mov     rsi, rcx
0x1800152d1  mov     [rsp+1A90h+var_1A40], edx
0x1800152d5  call    cs:__imp_PhoneAPIInitialize
0x1800152db  mov     ebx, eax
0x1800152dd  test    eax, eax
0x1800152df  jns     short loc_180015312
0x1800152e1  mov     r9d, 33h ; '3'
0x1800152e7  lea     r8, aOnecoreuapInte_0; "OnecoreUAP\\internal\\Net\\inc\\phsmart"...
0x1800152ee  mov     ecx, eax
0x1800152f0  lea     edx, [r9-32h]
0x1800152f4  call    Log_HREvent_0
0x1800152f9  mov     edx, 1
0x1800152fe  mov     r9d, 0B7h
0x180015304  mov     ecx, ebx
0x180015306  call    Log_HREvent_1
0x18001530b  mov     eax, ebx
0x18001530d  jmp     loc_18001562A
0x180015312  xor     edx, edx; Val
0x180015314  lea     rcx, [rbp+1990h+var_19F0]; void *
0x180015318  mov     r8d, 19C8h; Size
0x18001531e  call    memset_0
0x180015323  lea     rdx, [rbp+1990h+var_19F0]
0x180015327  lea     rcx, [rsp+1A90h+var_1A40]
0x18001532c  call    cs:__imp_PhoneGetCallInfo
0x180015332  mov     ebx, eax
0x180015334  cmp     eax, 80070490h
0x180015339  jnz     short loc_180015365
0x18001533b  call    cs:__imp_PhoneAPIUninitialize
0x180015341  test    eax, eax
0x180015343  jns     loc_180015628
0x180015349  mov     r8d, 3Eh ; '>'
0x18001534f  lea     rdx, aOnecoreuapInte_0; "OnecoreUAP\\internal\\Net\\inc\\phsmart"...
0x180015356  call    Log_AssertionEvent_1
0x18001535b  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180015360  jmp     loc_180015628
0x180015365  test    ebx, ebx
0x180015367  jns     short loc_1800153A1
0x180015369  mov     edx, 1
0x18001536e  mov     r9d, 0C1h
0x180015374  mov     ecx, ebx
0x180015376  call    Log_HREvent_1
0x18001537b  call    cs:__imp_PhoneAPIUninitialize
0x180015381  test    eax, eax
0x180015383  jns     short loc_18001530B
0x180015385  mov     r8d, 3Eh ; '>'
0x18001538b  lea     rdx, aOnecoreuapInte_0; "OnecoreUAP\\internal\\Net\\inc\\phsmart"...
0x180015392  call    Log_AssertionEvent_1
0x180015397  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001539c  jmp     loc_18001530B
0x1800153a1  xor     eax, eax
0x1800153a3  mov     [rsp+1A90h+var_1A26], 0
0x1800153ac  mov     [rsp+1A90h+var_1A1A], ax
0x1800153b1  lea     r8, [rsp+1A90h+Block]
0x1800153b6  lea     rax, [rsp+1A90h+var_1A28]
0x1800153bb  mov     [rsp+1A90h+var_1A1E], 0
0x1800153c3  mov     [rsp+1A90h+Block], rax
0x1800153c8  lea     rdx, [rbp+1990h+var_19F0]
0x1800153cc  lea     rax, [rsp+1A90h+var_1A28]
0x1800153d1  xor     r9d, r9d
0x1800153d4  mov     [rsp+1A90h+var_1A30], rax
0x1800153d9  mov     rcx, rsi
0x1800153dc  xor     eax, eax
0x1800153de  mov     [rsp+1A90h+var_1A28], ax
0x1800153e3  mov     rax, [rsi]
0x1800153e6  mov     rax, [rax+50h]
0x1800153ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800153ef  mov     edi, eax
0x1800153f1  test    eax, eax
0x1800153f3  jns     short loc_18001544A
0x1800153f5  mov     edx, 1
0x1800153fa  mov     r9d, 0C4h
0x180015400  mov     ecx, eax
0x180015402  call    Log_HREvent_1
0x180015407  mov     rcx, [rsp+1A90h+Block]; Block
0x18001540c  lea     rax, [rsp+1A90h+var_1A28]
0x180015411  cmp     rcx, rax
0x180015414  jz      short loc_180015422
0x180015416  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18001541d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180015422  call    cs:__imp_PhoneAPIUninitialize
0x180015428  test    eax, eax
0x18001542a  jns     short loc_180015443
0x18001542c  mov     r8d, 3Eh ; '>'
0x180015432  lea     rdx, aOnecoreuapInte_0; "OnecoreUAP\\internal\\Net\\inc\\phsmart"...
0x180015439  call    Log_AssertionEvent_1
0x18001543e  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180015443  mov     eax, edi
0x180015445  jmp     loc_18001562A
0x18001544a  mov     r8d, [rsp+1A90h+var_1A40]
0x18001544f  lea     rdx, aU; "%u"
0x180015456  xor     eax, eax
0x180015458  mov     [rbp+1990h+var_1A06], 0
0x180015460  mov     [rbp+1990h+var_19FA], ax
0x180015464  lea     rcx, [rsp+1A90h+var_1A18]
0x180015469  lea     rax, [rbp+1990h+var_1A08]
0x18001546d  mov     [rbp+1990h+var_19FE], 0
0x180015474  mov     [rsp+1A90h+var_1A18], rax
0x180015479  lea     rax, [rbp+1990h+var_1A08]
0x18001547d  mov     [rbp+1990h+var_1A10], rax
0x180015481  xor     eax, eax
0x180015483  mov     [rbp+1990h+var_1A08], ax
0x180015487  call    ??$assign_sprintf@GU?$char_traits@G@utl@@V?$allocator@G@2@@tlx@@YAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@PEBGZZ; tlx::assign_sprintf<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,ushort const *,...)
0x18001548c  mov     edi, eax
0x18001548e  test    eax, eax
0x180015490  jns     short loc_180015503
0x180015492  mov     edx, 1
0x180015497  mov     r9d, 0C7h
0x18001549d  mov     ecx, eax
0x18001549f  call    Log_HREvent_1
0x1800154a4  mov     rcx, [rsp+1A90h+var_1A18]; Block
0x1800154a9  lea     rax, [rbp+1990h+var_1A08]
0x1800154ad  cmp     rcx, rax
0x1800154b0  jz      short loc_1800154BE
0x1800154b2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800154b9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800154be  mov     rcx, [rsp+1A90h+Block]; Block
0x1800154c3  lea     rax, [rsp+1A90h+var_1A28]
0x1800154c8  cmp     rcx, rax
0x1800154cb  jz      short loc_1800154D9
0x1800154cd  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800154d4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800154d9  call    cs:__imp_PhoneAPIUninitialize
0x1800154df  test    eax, eax
0x1800154e1  jns     loc_180015443
0x1800154e7  mov     r8d, 3Eh ; '>'
0x1800154ed  lea     rdx, aOnecoreuapInte_0; "OnecoreUAP\\internal\\Net\\inc\\phsmart"...
0x1800154f4  call    Log_AssertionEvent_1
0x1800154f9  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800154fe  jmp     loc_180015443
0x180015503  mov     r8, [rsp+1A90h+var_1A18]
0x180015508  lea     rcx, aIncomingcall; "IncomingCall"
0x18001550f  mov     r9, [rsp+1A90h+Block]
0x180015514  mov     rax, [rsi]
0x180015517  mov     edx, [rsp+1A90h+var_1A40]
0x18001551b  mov     [rsp+1A90h+var_1A58], 0
0x180015523  mov     [rsp+1A90h+var_1A60], rcx
0x180015528  mov     rcx, rsi
0x18001552b  mov     rax, [rax+68h]
0x18001552f  mov     [rsp+1A90h+var_1A68], r8
0x180015534  lea     r8, aNonimmersivepa; "NonImmersivePackage"
0x18001553b  mov     [rsp+1A90h+var_1A70], r9
0x180015540  lea     r9, aWindowsSystemt; "Windows.Systemtoast.Calling"
0x180015547  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001554c  mov     edi, eax
0x18001554e  test    eax, eax
0x180015550  jns     short loc_1800155C3
0x180015552  mov     edx, 1
0x180015557  mov     r9d, 0CAh
0x18001555d  mov     ecx, eax
0x18001555f  call    Log_HREvent_1
0x180015564  mov     rcx, [rsp+1A90h+var_1A18]; Block
0x180015569  lea     rax, [rbp+1990h+var_1A08]
0x18001556d  cmp     rcx, rax
0x180015570  jz      short loc_18001557E
0x180015572  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180015579  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001557e  mov     rcx, [rsp+1A90h+Block]; Block
0x180015583  lea     rax, [rsp+1A90h+var_1A28]
0x180015588  cmp     rcx, rax
0x18001558b  jz      short loc_180015599
0x18001558d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180015594  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180015599  call    cs:__imp_PhoneAPIUninitialize
0x18001559f  test    eax, eax
0x1800155a1  jns     loc_180015443
0x1800155a7  mov     r8d, 3Eh ; '>'
0x1800155ad  lea     rdx, aOnecoreuapInte_0; "OnecoreUAP\\internal\\Net\\inc\\phsmart"...
0x1800155b4  call    Log_AssertionEvent_1
0x1800155b9  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800155be  jmp     loc_180015443
0x1800155c3  mov     ecx, [rsp+1A90h+var_1A40]; unsigned int
0x1800155c7  lea     r8, [rbp+1990h+var_19F0]; struct PH_CALL_INFO *
0x1800155cb  mov     edx, ebx; int
0x1800155cd  call    ?IncomingCallToastNotificationSent@TraceLogging@@SAXIJPEAUPH_CALL_INFO@@@Z; TraceLogging::IncomingCallToastNotificationSent(uint,long,PH_CALL_INFO *)
0x1800155d2  mov     rcx, [rsp+1A90h+var_1A18]; Block
0x1800155d7  lea     rax, [rbp+1990h+var_1A08]
0x1800155db  cmp     rcx, rax
0x1800155de  jz      short loc_1800155EC
0x1800155e0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800155e7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800155ec  mov     rcx, [rsp+1A90h+Block]; Block
0x1800155f1  lea     rax, [rsp+1A90h+var_1A28]
0x1800155f6  cmp     rcx, rax
0x1800155f9  jz      short loc_180015607
0x1800155fb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180015602  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180015607  call    cs:__imp_PhoneAPIUninitialize
0x18001560d  test    eax, eax
0x18001560f  jns     short loc_180015628
0x180015611  mov     r8d, 3Eh ; '>'
0x180015617  lea     rdx, aOnecoreuapInte_0; "OnecoreUAP\\internal\\Net\\inc\\phsmart"...
0x18001561e  call    Log_AssertionEvent_1
0x180015623  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180015628  xor     eax, eax
0x18001562a  mov     rcx, [rbp+1990h+var_20]
0x180015631  xor     rcx, rsp; StackCookie
0x180015634  call    __security_check_cookie
0x180015639  mov     rbx, [rsp+1A90h+arg_10]
0x180015641  add     rsp, 1A80h
0x180015648  pop     rdi
0x180015649  pop     rsi
0x18001564a  pop     rbp
0x18001564b  retn
```
