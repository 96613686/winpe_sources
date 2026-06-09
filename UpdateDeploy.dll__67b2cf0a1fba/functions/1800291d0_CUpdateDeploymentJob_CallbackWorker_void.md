# CUpdateDeploymentJob::CallbackWorker(void *)

- ea: `0x1800291d0`
- end: `0x1800294de`
- name: `?CallbackWorker@CUpdateDeploymentJob@@CAKPEAX@Z`
- size: `782`
- prototype: `__int64 __fastcall(HANDLE *Parameter)`
- caller_count: `0`
- callee_count: `10`
- tags: `installer_update`

## callees

- `0x180003180`
- `0x180007b6c`
- `0x18000c0ac`
- `0x1800110fc`
- `0x180011b44`
- `0x180029034`
- `0x1800291d0`
- `0x180032338`
- `0x180061960`
- `0x180068ea0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029431`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029431`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18002929f`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18002929f`

## string_xrefs

- `0x18002920d`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\UpdateDeploymentJob.cpp`
- `0x180029275`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\UpdateDeploymentJob.cpp`
- `0x180029316`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\UpdateDeploymentJob.cpp`
- `0x180029355`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\UpdateDeploymentJob.cpp`
- `0x180029384`: `CUpdateDeploymentJob::CallbackWorker`

## pseudocode

```c
__int64 __fastcall CUpdateDeploymentJob::CallbackWorker(HANDLE *Parameter)
{
  int v3; // edi
  char v4; // r12
  __int64 (__fastcall **v5)(HANDLE *, struct _GUID *); // rax
  char v6; // r13
  DWORD v7; // r14d
  DWORD v8; // r15d
  int v9; // eax
  unsigned int v10; // esi
  DWORD v11; // eax
  int CallbackThread; // eax
  __int64 v13; // rdx
  int v14; // eax
  int v15; // [rsp+28h] [rbp-69h]
  wchar_t v16[40]; // [rsp+48h] [rbp-49h] BYREF
  struct _GUID v17; // [rsp+98h] [rbp+7h] BYREF
  HANDLE Handles[2]; // [rsp+A8h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F0h] [rbp+5Fh]

  if ( !Parameter )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x24B,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\UpdateDeploymentJob.cpp",
      (const char *)0x80004003LL,
      v15);
    return 2147500035LL;
  }
  Handles[0] = Parameter[97];
  v3 = 0;
  Handles[1] = Parameter[92];
  v4 = 0;
  v5 = (__int64 (__fastcall **)(HANDLE *, struct _GUID *))*Parameter;
  v6 = 0;
  v17 = 0;
  v7 = 2;
  v8 = -1;
  v9 = v5[3](Parameter, &v17);
  v10 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x258,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\UpdateDeploymentJob.cpp",
      (const char *)(unsigned int)v9,
      v15);
    return v10;
  }
  while ( 1 )
  {
    v11 = WaitForMultipleObjects(v7, Handles, 0, v8);
    if ( !v11 )
    {
      v3 = 0;
      CallbackThread = CUpdateDeploymentJob::CreateCallbackThread((CUpdateDeploymentJob *)Parameter, 0);
      if ( CallbackThread >= 0 )
        goto LABEL_20;
      v13 = 613;
LABEL_19:
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)v13,
        (int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\UpdateDeploymentJob.cpp",
        (const char *)(unsigned int)CallbackThread);
      goto LABEL_20;
    }
    if ( v11 == 1 )
    {
      v3 = 0;
      v6 = 1;
      v14 = CUpdateDeploymentJob::WaitForCallbackThreads((CUpdateDeploymentJob *)Parameter);
      if ( v14 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x272,
          (int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\UpdateDeploymentJob.cpp",
          (const char *)(unsigned int)v14);
      v4 = *((_BYTE *)Parameter + 856);
      v8 = 0;
      v7 = 1;
      goto LABEL_20;
    }
    if ( v11 != 258 )
      break;
    if ( !v6 )
    {
      v3 = 0;
      goto LABEL_20;
    }
    v8 = 50;
    v7 = 1;
    if ( *((_BYTE *)Parameter + 856) )
      goto LABEL_27;
    if ( (unsigned int)++v3 >= 0xA )
    {
      WUTrace("CUpdateDeploymentJob::CallbackWorker", 668, 32, 3);
      WUTelemetryAssertTriggered(0xFFFFFFFF, 0xFFFFFFFF);
      Trace::GuidToString::GuidToString(v16, &v17);
      WUTrace(0, 0, 0x1000000, 3);
      goto LABEL_27;
    }
    CallbackThread = CUpdateDeploymentJob::CreateCallbackThread((CUpdateDeploymentJob *)Parameter, 1);
    if ( CallbackThread < 0 )
    {
      v13 = 684;
      goto LABEL_19;
    }
LABEL_20:
    if ( v4 )
      goto LABEL_27;
  }
  if ( v11 == -1 )
  {
    Trace::GuidToString::GuidToString(v16, &v17);
    GetLastError();
  }
  else
  {
    Trace::GuidToString::GuidToString(v16, &v17);
  }
  WUTrace(0, 0, 0x1000000, 3);
LABEL_27:
  Trace::GuidToString::GuidToString(v16, &v17);
  WUTrace(0, 0, 0x1000000, 4);
  return 0;
}

```

## disassembly

```asm
0x1800291d0  mov     rax, rsp
0x1800291d3  mov     [rax+10h], rbx
0x1800291d7  mov     [rax+18h], rsi
0x1800291db  mov     [rax+20h], rdi
0x1800291df  push    rbp
0x1800291e0  push    r12
0x1800291e2  push    r13
0x1800291e4  push    r14
0x1800291e6  push    r15
0x1800291e8  lea     rbp, [rax-5Fh]
0x1800291ec  sub     rsp, 0C0h
0x1800291f3  mov     rax, cs:__security_cookie
0x1800291fa  xor     rax, rsp
0x1800291fd  mov     [rbp+57h+var_30], rax
0x180029201  mov     rbx, rcx
0x180029204  test    rcx, rcx
0x180029207  jnz     short loc_18002922E
0x180029209  mov     rcx, [rbp+5Fh]; this
0x18002920d  lea     r8, aCW1SSrcClientU_10; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x180029214  mov     r9d, 80004003h; char *
0x18002921a  mov     edx, 24Bh; void *
0x18002921f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029224  mov     eax, 80004003h
0x180029229  jmp     loc_1800294B1
0x18002922e  mov     rax, [rcx+308h]
0x180029235  lea     rdx, [rbp+57h+var_50]
0x180029239  mov     [rbp+57h+Handles], rax
0x18002923d  xorps   xmm0, xmm0
0x180029240  mov     rax, [rcx+2E0h]
0x180029247  xor     edi, edi
0x180029249  mov     [rbp+57h+var_38], rax
0x18002924d  xor     r12b, r12b
0x180029250  mov     rax, [rcx]
0x180029253  xor     r13b, r13b
0x180029256  movups  xmmword ptr [rbp+57h+var_50.Data1], xmm0
0x18002925a  lea     r14d, [rdi+2]
0x18002925e  or      r15d, 0FFFFFFFFh
0x180029262  mov     rax, [rax+18h]
0x180029266  call    _guard_dispatch_icall
0x18002926b  mov     esi, eax
0x18002926d  test    eax, eax
0x18002926f  jns     short loc_180029290
0x180029271  mov     rcx, [rbp+5Fh]; this
0x180029275  lea     r8, aCW1SSrcClientU_10; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x18002927c  mov     r9d, eax; char *
0x18002927f  mov     edx, 258h; void *
0x180029284  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029289  mov     eax, esi
0x18002928b  jmp     loc_1800294B1
0x180029290  xor     esi, esi
0x180029292  mov     r9d, r15d; dwMilliseconds
0x180029295  lea     rdx, [rbp+57h+Handles]; lpHandles
0x180029299  xor     r8d, r8d; bWaitAll
0x18002929c  mov     ecx, r14d; nCount
0x18002929f  call    cs:__imp_WaitForMultipleObjects
0x1800292a5  test    eax, eax
0x1800292a7  jz      loc_18002933C
0x1800292ad  cmp     eax, 1
0x1800292b0  jz      short loc_180029301
0x1800292b2  cmp     eax, 102h
0x1800292b7  jnz     loc_1800293FC
0x1800292bd  test    r13b, r13b
0x1800292c0  jnz     short loc_1800292C9
0x1800292c2  mov     edi, esi
0x1800292c4  jmp     loc_180029364
0x1800292c9  mov     r15d, 32h ; '2'
0x1800292cf  lea     r14d, [r15-31h]
0x1800292d3  cmp     [rbx+358h], sil
0x1800292da  jnz     loc_180029479
0x1800292e0  inc     edi
0x1800292e2  cmp     edi, 0Ah
0x1800292e5  jnb     loc_180029372
0x1800292eb  mov     dl, r14b; bool
0x1800292ee  mov     rcx, rbx; this
0x1800292f1  call    ?CreateCallbackThread@CUpdateDeploymentJob@@AEAAJ_N@Z; CUpdateDeploymentJob::CreateCallbackThread(bool)
0x1800292f6  test    eax, eax
0x1800292f8  jns     short loc_180029364
0x1800292fa  mov     edx, 2ACh
0x1800292ff  jmp     short loc_180029351
0x180029301  mov     rcx, rbx; this
0x180029304  mov     edi, esi
0x180029306  mov     r13b, 1
0x180029309  call    ?WaitForCallbackThreads@CUpdateDeploymentJob@@AEAAJXZ; CUpdateDeploymentJob::WaitForCallbackThreads(void)
0x18002930e  test    eax, eax
0x180029310  jns     short loc_18002932A
0x180029312  mov     rcx, [rbp+5Fh]; this
0x180029316  lea     r8, aCW1SSrcClientU_10; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x18002931d  mov     r9d, eax; char *
0x180029320  mov     edx, 272h; void *
0x180029325  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002932a  mov     r12b, [rbx+358h]
0x180029331  mov     r15d, esi
0x180029334  mov     r14d, 1
0x18002933a  jmp     short loc_180029364
0x18002933c  xor     edx, edx; bool
0x18002933e  mov     rcx, rbx; this
0x180029341  mov     edi, esi
0x180029343  call    ?CreateCallbackThread@CUpdateDeploymentJob@@AEAAJ_N@Z; CUpdateDeploymentJob::CreateCallbackThread(bool)
0x180029348  test    eax, eax
0x18002934a  jns     short loc_180029364
0x18002934c  mov     edx, 265h; void *
0x180029351  mov     rcx, [rbp+5Fh]; this
0x180029355  lea     r8, aCW1SSrcClientU_10; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x18002935c  mov     r9d, eax; char *
0x18002935f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180029364  test    r12b, r12b
0x180029367  jz      loc_180029292
0x18002936d  jmp     loc_180029479
0x180029372  lea     rax, aFailed; "Failed"
0x180029379  mov     r9d, 3
0x18002937f  mov     [rsp+0E0h+var_A8], rax
0x180029384  lea     rcx, aCupdatedeploym_2; "CUpdateDeploymentJob::CallbackWorker"
0x18002938b  lea     rax, aCtimeoutwaitsD; "cTimeoutWaits < dwMaxSuccessiveTimeoutW"...
0x180029392  mov     edx, 29Ch
0x180029397  mov     [rsp+0E0h+var_B0], rax
0x18002939c  lea     rax, aTelemetryasser; "TelemetryAssert (%ws): %ws"
0x1800293a3  mov     [rsp+0E0h+var_B8], rax
0x1800293a8  lea     r8d, [r9+1Dh]
0x1800293ac  mov     [rsp+0E0h+var_C0], rsi
0x1800293b1  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800293b6  or      edx, 0FFFFFFFFh; unsigned int
0x1800293b9  or      ecx, edx; unsigned int
0x1800293bb  call    ?WUTelemetryAssertTriggered@@YAXII@Z; WUTelemetryAssertTriggered(uint,uint)
0x1800293c0  lea     rdx, [rbp+57h+var_50]; struct _GUID *
0x1800293c4  lea     rcx, [rbp+57h+var_A0]; this
0x1800293c8  call    ??0GuidToString@Trace@@QEAA@AEBU_GUID@@@Z; Trace::GuidToString::GuidToString(_GUID const &)
0x1800293cd  mov     dword ptr [rsp+0E0h+var_A8], edi
0x1800293d1  xor     edx, edx
0x1800293d3  mov     [rsp+0E0h+var_B0], rax
0x1800293d8  xor     ecx, ecx
0x1800293da  lea     rax, aDeploymentJobI_47; "Deployment job Id %ws : CallbackWorker "...
0x1800293e1  mov     r8d, 1000000h
0x1800293e7  mov     [rsp+0E0h+var_B8], rax
0x1800293ec  lea     r9d, [rdx+3]
0x1800293f0  mov     [rsp+0E0h+var_C0], rsi
0x1800293f5  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800293fa  jmp     short loc_180029479
0x1800293fc  lea     rdx, [rbp+57h+var_50]; struct _GUID *
0x180029400  lea     rcx, [rbp+57h+var_A0]; this
0x180029404  cmp     eax, 0FFFFFFFFh
0x180029407  jz      short loc_180029429
0x180029409  call    ??0GuidToString@Trace@@QEAA@AEBU_GUID@@@Z; Trace::GuidToString::GuidToString(_GUID const &)
0x18002940e  mov     [rsp+0E0h+var_B0], rax
0x180029413  lea     rax, aDeploymentJobI_38; "Deployment job Id %ws : CallbackWorker "...
0x18002941a  mov     [rsp+0E0h+var_B8], rax
0x18002941f  mov     dword ptr [rsp+0E0h+var_C0], 80240FFFh
0x180029427  jmp     short loc_180029464
0x180029429  call    ??0GuidToString@Trace@@QEAA@AEBU_GUID@@@Z; Trace::GuidToString::GuidToString(_GUID const &)
0x18002942e  mov     rbx, rax
0x180029431  call    cs:__imp_GetLastError
0x180029437  movzx   ecx, ax
0x18002943a  or      ecx, 80070000h
0x180029440  mov     [rsp+0E0h+var_B0], rbx
0x180029445  test    eax, eax
0x180029447  cmovle  ecx, eax
0x18002944a  mov     eax, 8000FFFFh
0x18002944f  test    ecx, ecx
0x180029451  cmovns  ecx, eax
0x180029454  lea     rax, aDeploymentJobI_34; "Deployment job Id %ws : CallbackWorker "...
0x18002945b  mov     [rsp+0E0h+var_B8], rax
0x180029460  mov     dword ptr [rsp+0E0h+var_C0], ecx
0x180029464  mov     r9d, 3
0x18002946a  mov     r8d, 1000000h
0x180029470  xor     edx, edx
0x180029472  xor     ecx, ecx
0x180029474  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180029479  lea     rdx, [rbp+57h+var_50]; struct _GUID *
0x18002947d  lea     rcx, [rbp+57h+var_A0]; this
0x180029481  call    ??0GuidToString@Trace@@QEAA@AEBU_GUID@@@Z; Trace::GuidToString::GuidToString(_GUID const &)
0x180029486  mov     [rsp+0E0h+var_B0], rax
0x18002948b  xor     edx, edx
0x18002948d  lea     rax, aDeploymentJobI_29; "Deployment job Id %ws : CallbackWorker "...
0x180029494  xor     ecx, ecx
0x180029496  mov     [rsp+0E0h+var_B8], rax
0x18002949b  mov     r8d, 1000000h
0x1800294a1  mov     [rsp+0E0h+var_C0], rsi
0x1800294a6  lea     r9d, [rdx+4]
0x1800294aa  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800294af  xor     eax, eax
0x1800294b1  mov     rcx, [rbp+57h+var_30]
0x1800294b5  xor     rcx, rsp; StackCookie
0x1800294b8  call    __security_check_cookie
0x1800294bd  lea     r11, [rsp+0E0h+var_20]
0x1800294c5  mov     rbx, [r11+38h]
0x1800294c9  mov     rsi, [r11+40h]
0x1800294cd  mov     rdi, [r11+48h]
0x1800294d1  mov     rsp, r11
0x1800294d4  pop     r15
0x1800294d6  pop     r14
0x1800294d8  pop     r13
0x1800294da  pop     r12
0x1800294dc  pop     rbp
0x1800294dd  retn
```
