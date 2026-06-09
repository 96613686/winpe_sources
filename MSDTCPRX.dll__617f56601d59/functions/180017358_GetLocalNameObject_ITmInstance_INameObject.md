# GetLocalNameObject(ITmInstance *,INameObject * *)

- ea: `0x180017358`
- end: `0x1800176bd`
- name: `?GetLocalNameObject@@YAJPEAUITmInstance@@PEAPEAUINameObject@@@Z`
- size: `869`
- prototype: `__int64 __fastcall(struct ITmInstance *, struct INameObject **)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180021504`
- `0x180022928`

## callees

- `0x180003cf0`
- `0x180006880`
- `0x18000d5f4`
- `0x180017358`
- `0x180085010`

## import_xrefs

- `RPCRT4!RpcServerInqDefaultPrincNameW` at `0x180017550`
- `RPCRT4!RpcServerInqDefaultPrincNameW` at `0x180017550`
- `RPCRT4!RpcStringFreeW` at `0x18001766b`
- `RPCRT4!RpcStringFreeW` at `0x18001766b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001744e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017489`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800175bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001744e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017489`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800175bb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001741d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001741d`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001747f`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800175b1`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001747f`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800175b1`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180017434`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180017434`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800174dd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017603`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800174dd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017603`

## string_xrefs

- `0x1800173f3`: `com\complus\dtc\dtc\msdtcprx\src\cmutil.cpp`
- `0x18001743a`: `com\complus\dtc\dtc\msdtcprx\src\cmutil.cpp`
- `0x180017472`: `Call to OpenThreadToken Failed`
- `0x1800174a0`: `Call to SetThreadToken Failed`
- `0x1800175d0`: `Call to SetThreadToken Failed`
- `0x1800175e5`: `ReImpersonateIfNecessary`
- `0x18001738b`: `GetLocalNameObject (com\complus\dtc\dtc\msdtcprx\src\cmutil.cpp@268): GetLocalNameObject - NULL != i_pTmInstance`
- `0x18001739d`: `GetLocalNameObject (com\complus\dtc\dtc\msdtcprx\src\cmutil.cpp@269): GetLocalNameObject - NULL != o_ppNameObject`
- `0x18001761a`: `ReImpersonateIfNecessary failed`
- `0x18001763d`: `ReImpersonateIfNecessary failed in CITmProxyInit::GetNeededNameObjects`

## pseudocode

```c
__int64 __fastcall GetLocalNameObject(struct ITmInstance *a1, struct INameObject **a2)
{
  __int64 v3; // rax
  struct INameObject *v4; // rdi
  signed int v5; // ebx
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  __int64 v8; // r9
  const wchar_t *v9; // r10
  signed int v10; // eax
  void *v11; // rsi
  const wchar_t *v12; // rax
  __int64 v13; // r9
  unsigned int v14; // eax
  RPC_STATUS v15; // eax
  signed int v16; // eax
  __int64 v18; // [rsp+28h] [rbp-20h]
  RPC_WSTR PrincName; // [rsp+90h] [rbp+48h] BYREF
  struct INameObject **v20; // [rsp+98h] [rbp+50h]
  void *TokenHandle; // [rsp+A0h] [rbp+58h] BYREF
  struct IProperties *v22; // [rsp+A8h] [rbp+60h] BYREF

  v20 = a2;
  v22 = 0;
  PrincName = 0;
  if ( !a1 )
    DtcInternalErrorW(
      L"GetLocalNameObject (com\\complus\\dtc\\dtc\\msdtcprx\\src\\cmutil.cpp@268): GetLocalNameObject - NULL != i_pTmInstance");
  if ( !a2 )
    DtcInternalErrorW(
      L"GetLocalNameObject (com\\complus\\dtc\\dtc\\msdtcprx\\src\\cmutil.cpp@269): GetLocalNameObject - NULL != o_ppNameObject");
  v3 = *(_QWORD *)a1;
  *a2 = 0;
  (*(void (__fastcall **)(struct ITmInstance *, struct IProperties **))(v3 + 176))(a1, &v22);
  v4 = ContactToNameObject(v22);
  if ( !v4 )
  {
    v5 = -2147467259;
    LODWORD(v18) = -2147467259;
    TraceStringInline(
      15,
      1,
      L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\cmutil.cpp",
      284,
      L"GetLocalNameObject",
      v18,
      L"ContactToNameObject failed.");
    goto LABEL_40;
  }
  TokenHandle = 0;
  v5 = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 4u, 1, &TokenHandle) )
  {
    LastError = GetLastError();
    if ( LastError != 1008 )
    {
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      else
        v5 = LastError;
      v8 = 55;
      v9 = L"Call to OpenThreadToken Failed";
      goto LABEL_18;
    }
LABEL_21:
    v11 = TokenHandle;
    goto LABEL_22;
  }
  if ( SetThreadToken(0, 0) )
    goto LABEL_21;
  v10 = GetLastError();
  v5 = v10;
  if ( v10 > 0 )
    v5 = (unsigned __int16)v10 | 0x80070000;
  v8 = 66;
  v9 = L"Call to SetThreadToken Failed";
LABEL_18:
  LODWORD(v18) = v5;
  TraceStringInline(15, 1, L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\cmutil.cpp", v8, L"RevertIfNecessary", v18, v9);
  if ( v5 >= 0 )
    goto LABEL_21;
  v11 = TokenHandle;
  if ( TokenHandle )
  {
    CloseHandle(TokenHandle);
    TokenHandle = 0;
LABEL_23:
    v12 = L"RevertIfNecessary failed";
    v13 = 301;
LABEL_24:
    LODWORD(v18) = v5;
    TraceStringInline(15, 1, L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\cmutil.cpp", v13, L"GetLocalNameObject", v18, v12);
    goto LABEL_40;
  }
LABEL_22:
  if ( v5 < 0 )
    goto LABEL_23;
  v14 = (*(__int64 (__fastcall **)(struct ITmInstance *, const wchar_t *, __int64))(*(_QWORD *)a1 + 344LL))(
          a1,
          L"RpcAuthnSvc",
          9);
  if ( v14 != 14 )
  {
    v15 = RpcServerInqDefaultPrincNameW(v14, &PrincName);
    v5 = v15;
    if ( v15 )
    {
      if ( v15 > 0 )
        v5 = (unsigned __int16)v15 | 0x80070000;
      v12 = L"RpcServerInqDefaultPrincNameW failed.";
      v13 = 318;
      goto LABEL_24;
    }
  }
  v5 = (*(__int64 (__fastcall **)(struct INameObject *, RPC_WSTR))(*(_QWORD *)v4 + 104LL))(v4, PrincName);
  if ( v5 < 0 )
  {
    v12 = L"LocalNameObject::SetSPN failed.";
    v13 = 327;
    goto LABEL_24;
  }
  v5 = 0;
  if ( v11 )
  {
    if ( !SetThreadToken(0, v11) )
    {
      v16 = GetLastError();
      v5 = v16;
      if ( v16 > 0 )
        v5 = (unsigned __int16)v16 | 0x80070000;
      LODWORD(v18) = v5;
      TraceStringInline(
        15,
        1,
        L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\cmutil.cpp",
        119,
        L"ReImpersonateIfNecessary",
        v18,
        L"Call to SetThreadToken Failed");
    }
    CloseHandle(v11);
    if ( v5 < 0 )
    {
      LODWORD(v18) = v5;
      TraceStringInline(
        15,
        1,
        L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\cmutil.cpp",
        337,
        L"GetLocalNameObject",
        v18,
        L"ReImpersonateIfNecessary failed");
      DtcInternalErrorW(L"ReImpersonateIfNecessary failed in CITmProxyInit::GetNeededNameObjects");
    }
  }
  *v20 = v4;
  (*(void (__fastcall **)(struct INameObject *))(*(_QWORD *)v4 + 8LL))(v4);
LABEL_40:
  if ( PrincName )
  {
    RpcStringFreeW(&PrincName);
    PrincName = 0;
  }
  if ( v22 )
  {
    (*(void (__fastcall **)(struct IProperties *))(*(_QWORD *)v22 + 16LL))(v22);
    v22 = 0;
  }
  if ( v4 )
    (*(void (__fastcall **)(struct INameObject *))(*(_QWORD *)v4 + 16LL))(v4);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180017358  mov     [rsp-40h+arg_8], rdx
0x18001735d  push    rbp
0x18001735e  push    rbx
0x18001735f  push    rsi
0x180017360  push    rdi
0x180017361  push    r12
0x180017363  push    r13
0x180017365  push    r14
0x180017367  push    r15
0x180017369  mov     rbp, rsp
0x18001736c  sub     rsp, 48h
0x180017370  mov     [rbp+arg_18], 0
0x180017378  mov     rax, rdx
0x18001737b  mov     [rbp+PrincName], 0
0x180017383  mov     r13, rcx
0x180017386  test    rcx, rcx
0x180017389  jnz     short loc_180017398
0x18001738b  lea     rcx, aGetlocalnameob_1; "GetLocalNameObject (com\\complus\\dtc\\"...
0x180017392  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x180017398  test    rax, rax
0x18001739b  jnz     short loc_1800173AA
0x18001739d  lea     rcx, aGetlocalnameob_2; "GetLocalNameObject (com\\complus\\dtc\\"...
0x1800173a4  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x1800173aa  mov     rax, [rcx]
0x1800173ad  mov     qword ptr [rdx], 0
0x1800173b4  lea     rdx, [rbp+arg_18]
0x1800173b8  mov     rax, [rax+0B0h]
0x1800173bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800173c4  mov     rcx, [rbp+arg_18]; struct IProperties *
0x1800173c8  call    ?ContactToNameObject@@YAPEAUINameObject@@PEAUIProperties@@@Z; ContactToNameObject(IProperties *)
0x1800173cd  mov     rdi, rax
0x1800173d0  test    rax, rax
0x1800173d3  jnz     short loc_180017413
0x1800173d5  lea     rcx, aGetlocalnameob_0; "GetLocalNameObject"
0x1800173dc  mov     ebx, 80004005h
0x1800173e1  lea     rax, aContacttonameo_1; "ContactToNameObject failed."
0x1800173e8  mov     r9d, 11Ch
0x1800173ee  mov     [rsp+48h+var_18], rax
0x1800173f3  lea     r8, aComComplusDtcD; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x1800173fa  mov     dword ptr [rsp+48h+var_20], ebx
0x1800173fe  lea     edx, [rdi+1]
0x180017401  mov     [rsp+48h+var_28], rcx
0x180017406  lea     ecx, [rdi+0Fh]
0x180017409  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001740e  jmp     loc_180017660
0x180017413  mov     [rbp+TokenHandle], 0
0x18001741b  xor     ebx, ebx
0x18001741d  call    cs:__imp_GetCurrentThread
0x180017423  lea     r14d, [rbx+1]
0x180017427  mov     rcx, rax; ThreadHandle
0x18001742a  mov     r8d, r14d; OpenAsSelf
0x18001742d  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180017431  lea     edx, [rbx+4]; DesiredAccess
0x180017434  call    cs:__imp_OpenThreadToken
0x18001743a  lea     r15, aComComplusDtcD; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x180017441  mov     esi, 80070000h
0x180017446  lea     r12d, [rbx+0Fh]
0x18001744a  test    eax, eax
0x18001744c  jnz     short loc_18001747B
0x18001744e  call    cs:__imp_GetLastError
0x180017454  cmp     eax, 3F0h
0x180017459  jz      loc_1800174ED
0x18001745f  test    eax, eax
0x180017461  jg      short loc_180017467
0x180017463  mov     ebx, eax
0x180017465  jmp     short loc_18001746C
0x180017467  movzx   ebx, ax
0x18001746a  or      ebx, esi
0x18001746c  mov     r9d, 37h ; '7'
0x180017472  lea     r10, aCallToOpenthre; "Call to OpenThreadToken Failed"
0x180017479  jmp     short loc_1800174A7
0x18001747b  xor     edx, edx; Token
0x18001747d  xor     ecx, ecx; Thread
0x18001747f  call    cs:__imp_SetThreadToken
0x180017485  test    eax, eax
0x180017487  jnz     short loc_1800174ED
0x180017489  call    cs:__imp_GetLastError
0x18001748f  mov     ebx, eax
0x180017491  test    eax, eax
0x180017493  jle     short loc_18001749A
0x180017495  movzx   ebx, ax
0x180017498  or      ebx, esi
0x18001749a  mov     r9d, 42h ; 'B'
0x1800174a0  lea     r10, aCallToSetthrea; "Call to SetThreadToken Failed"
0x1800174a7  lea     rax, aRevertifnecess; "RevertIfNecessary"
0x1800174ae  mov     r8, r15
0x1800174b1  mov     dl, r14b
0x1800174b4  mov     ecx, r12d
0x1800174b7  mov     [rsp+48h+var_18], r10
0x1800174bc  mov     dword ptr [rsp+48h+var_20], ebx
0x1800174c0  movzx   edx, dl
0x1800174c3  mov     [rsp+48h+var_28], rax
0x1800174c8  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800174cd  test    ebx, ebx
0x1800174cf  jns     short loc_1800174ED
0x1800174d1  mov     rsi, [rbp+TokenHandle]
0x1800174d5  test    rsi, rsi
0x1800174d8  jz      short loc_1800174F1
0x1800174da  mov     rcx, rsi; hObject
0x1800174dd  call    cs:__imp_CloseHandle
0x1800174e3  mov     [rbp+TokenHandle], 0
0x1800174eb  jmp     short loc_1800174F5
0x1800174ed  mov     rsi, [rbp+TokenHandle]
0x1800174f1  test    ebx, ebx
0x1800174f3  jns     short loc_180017525
0x1800174f5  lea     rax, aRevertifnecess_0; "RevertIfNecessary failed"
0x1800174fc  mov     r9d, 12Dh
0x180017502  mov     [rsp+48h+var_18], rax
0x180017507  lea     rcx, aGetlocalnameob_0; "GetLocalNameObject"
0x18001750e  mov     dword ptr [rsp+48h+var_20], ebx
0x180017512  mov     r8, r15
0x180017515  mov     [rsp+48h+var_28], rcx
0x18001751a  mov     edx, r14d
0x18001751d  mov     ecx, r12d
0x180017520  jmp     loc_180017409
0x180017525  mov     rax, [r13+0]
0x180017529  lea     rdx, aRpcauthnsvc; "RpcAuthnSvc"
0x180017530  mov     r8d, 9
0x180017536  mov     rcx, r13
0x180017539  mov     rax, [rax+158h]
0x180017540  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017545  cmp     eax, 0Eh
0x180017548  jz      short loc_180017576
0x18001754a  lea     rdx, [rbp+PrincName]; PrincName
0x18001754e  mov     ecx, eax; AuthnSvc
0x180017550  call    cs:__imp_RpcServerInqDefaultPrincNameW
0x180017556  mov     ebx, eax
0x180017558  test    eax, eax
0x18001755a  jz      short loc_180017576
0x18001755c  jle     short loc_180017567
0x18001755e  movzx   ebx, ax
0x180017561  or      ebx, 80070000h
0x180017567  lea     rax, aRpcserverinqde; "RpcServerInqDefaultPrincNameW failed."
0x18001756e  mov     r9d, 13Eh
0x180017574  jmp     short loc_180017502
0x180017576  mov     rax, [rdi]
0x180017579  mov     rcx, rdi
0x18001757c  mov     rdx, [rbp+PrincName]
0x180017580  mov     rax, [rax+68h]
0x180017584  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017589  mov     ebx, eax
0x18001758b  test    eax, eax
0x18001758d  jns     short loc_1800175A1
0x18001758f  lea     rax, aLocalnameobjec; "LocalNameObject::SetSPN failed."
0x180017596  mov     r9d, 147h
0x18001759c  jmp     loc_180017502
0x1800175a1  xor     ebx, ebx
0x1800175a3  test    rsi, rsi
0x1800175a6  jz      loc_18001764A
0x1800175ac  mov     rdx, rsi; Token
0x1800175af  xor     ecx, ecx; Thread
0x1800175b1  call    cs:__imp_SetThreadToken
0x1800175b7  test    eax, eax
0x1800175b9  jnz     short loc_180017600
0x1800175bb  call    cs:__imp_GetLastError
0x1800175c1  mov     ebx, eax
0x1800175c3  test    eax, eax
0x1800175c5  jle     short loc_1800175D0
0x1800175c7  movzx   ebx, ax
0x1800175ca  or      ebx, 80070000h
0x1800175d0  lea     rax, aCallToSetthrea; "Call to SetThreadToken Failed"
0x1800175d7  mov     r9d, 77h ; 'w'
0x1800175dd  mov     [rsp+48h+var_18], rax
0x1800175e2  mov     r8, r15
0x1800175e5  lea     rax, aReimpersonatei_2; "ReImpersonateIfNecessary"
0x1800175ec  mov     dword ptr [rsp+48h+var_20], ebx
0x1800175f0  mov     edx, r14d
0x1800175f3  mov     [rsp+48h+var_28], rax
0x1800175f8  mov     ecx, r12d
0x1800175fb  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180017600  mov     rcx, rsi; hObject
0x180017603  call    cs:__imp_CloseHandle
0x180017609  test    ebx, ebx
0x18001760b  jns     short loc_18001764A
0x18001760d  lea     rcx, aGetlocalnameob_0; "GetLocalNameObject"
0x180017614  mov     r9d, 151h
0x18001761a  lea     rax, aReimpersonatei_1; "ReImpersonateIfNecessary failed"
0x180017621  mov     r8, r15
0x180017624  mov     [rsp+48h+var_18], rax
0x180017629  mov     edx, r14d
0x18001762c  mov     dword ptr [rsp+48h+var_20], ebx
0x180017630  mov     [rsp+48h+var_28], rcx
0x180017635  mov     ecx, r12d
0x180017638  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001763d  lea     rcx, aReimpersonatei; "ReImpersonateIfNecessary failed in CITm"...
0x180017644  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x18001764a  mov     rax, [rbp+arg_8]
0x18001764e  mov     rcx, rdi
0x180017651  mov     [rax], rdi
0x180017654  mov     rax, [rdi]
0x180017657  mov     rax, [rax+8]
0x18001765b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017660  cmp     [rbp+PrincName], 0
0x180017665  jz      short loc_180017679
0x180017667  lea     rcx, [rbp+PrincName]; String
0x18001766b  call    cs:__imp_RpcStringFreeW
0x180017671  mov     [rbp+PrincName], 0
0x180017679  mov     rcx, [rbp+arg_18]
0x18001767d  test    rcx, rcx
0x180017680  jz      short loc_180017696
0x180017682  mov     rax, [rcx]
0x180017685  mov     rax, [rax+10h]
0x180017689  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001768e  mov     [rbp+arg_18], 0
0x180017696  test    rdi, rdi
0x180017699  jz      short loc_1800176AA
0x18001769b  mov     rax, [rdi]
0x18001769e  mov     rcx, rdi
0x1800176a1  mov     rax, [rax+10h]
0x1800176a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800176aa  mov     eax, ebx
0x1800176ac  add     rsp, 48h
0x1800176b0  pop     r15
0x1800176b2  pop     r14
0x1800176b4  pop     r13
0x1800176b6  pop     r12
0x1800176b8  pop     rdi
0x1800176b9  pop     rsi
0x1800176ba  pop     rbx
0x1800176bb  pop     rbp
0x1800176bc  retn
```
