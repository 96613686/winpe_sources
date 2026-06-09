# PhoneCallSoftwareCapabilityAccessCheck(ulong)

- ea: `0x180051540`
- end: `0x1800517d0`
- name: `?PhoneCallSoftwareCapabilityAccessCheck@@YAJK@Z`
- size: `656`
- prototype: `__int64 __fastcall(int)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x180088c00`
- `0x18008b4e0`

## callees

- `0x180006e94`
- `0x180051530`
- `0x180051540`
- `0x18008d9b0`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800515cd`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180051683`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800515cd`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180051683`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800515fe`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800515fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800515b4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180051696`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800515b4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180051696`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180051577`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180051577`

## string_xrefs

- `0x1800515ad`: `Windows.Internal.CapabilityAccess.CapabilityAccess`

## pseudocode

```c
__int64 __fastcall PhoneCallSoftwareCapabilityAccessCheck(int a1)
{
  RPC_STATUS v2; // eax
  BackTraceCollection *v3; // rcx
  unsigned int v4; // ebx
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v8; // rcx
  HSTRING v9; // rbx
  int ActivationFactory; // eax
  BackTraceCollection *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // rcx
  void (*v15)(void); // rax
  __int64 v16; // rsi
  unsigned __int64 v17; // rbx
  unsigned int v18; // r14d
  __int64 (__fastcall *v19)(__int64, _QWORD, HSTRING, _QWORD, int, __int64 *); // r15
  int v20; // eax
  BackTraceCollection *v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // r9
  __int64 v25; // rcx
  __int64 v26; // rcx
  int v27; // eax
  BackTraceCollection *v28; // rcx
  __int64 v29; // rcx
  __int64 v30; // rcx
  __int64 v31; // rcx
  HSTRING string; // [rsp+40h] [rbp-29h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-21h] BYREF
  __int64 v34; // [rsp+60h] [rbp-9h] BYREF
  __int64 v35; // [rsp+68h] [rbp-1h] BYREF
  unsigned int Pid; // [rsp+70h] [rbp+7h] BYREF
  int v37; // [rsp+74h] [rbp+Bh] BYREF

  Pid = 0;
  v2 = I_RpcBindingInqLocalClientPID(0, &Pid);
  v4 = v2;
  if ( v2 < 0 )
  {
    BackTraceCollection::Capture(v3, v2);
    Log_HREvent_11(v4, v5, v6, 20);
    return v4;
  }
  v34 = 0;
  if ( WindowsCreateStringReference(
         L"Windows.Internal.CapabilityAccess.CapabilityAccess",
         0x32u,
         &hstringHeader,
         &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v8 = v34;
  v9 = string;
  if ( v34 )
  {
    v34 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  }
  ActivationFactory = RoGetActivationFactory(v9, &GUID_518f3880_4e5c_4524_ab03_cd01336b2178, &v34);
  v4 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    BackTraceCollection::Capture(v11, ActivationFactory);
    Log_HREvent_11(v4, v12, v13, 24);
    v14 = v34;
    if ( !v34 )
      return v4;
    v34 = 0;
    v15 = *(void (**)(void))(*(_QWORD *)v14 + 16LL);
LABEL_11:
    v15();
    return v4;
  }
  v16 = v34;
  v17 = -1;
  v18 = Pid;
  v35 = 0;
  v19 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING, _QWORD, int, __int64 *))(*(_QWORD *)v34 + 56LL);
  do
    ++v17;
  while ( c_szCapabilityPhoneCall[v17] );
  if ( v17 > 0xFFFFFFFF )
  {
    LODWORD(v17) = -1;
    RaiseException(0xC000000D, 1u, 0, 0);
  }
  WindowsCreateStringReference(c_szCapabilityPhoneCall, v17, &hstringHeader, &string);
  v20 = v19(v16, 0, string, v18, a1, &v35);
  v4 = v20;
  if ( v20 < 0 )
  {
    BackTraceCollection::Capture(v21, v20);
    v24 = 28;
LABEL_18:
    Log_HREvent_11(v4, v22, v23, v24);
    v25 = v35;
    if ( v35 )
    {
      v35 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    }
    v26 = v34;
    if ( !v34 )
      return v4;
    v34 = 0;
    v15 = *(void (**)(void))(*(_QWORD *)v26 + 16LL);
    goto LABEL_11;
  }
  v37 = 3;
  v27 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v35 + 152LL))(v35, &v37);
  v4 = v27;
  if ( v27 < 0 )
  {
    BackTraceCollection::Capture(v28, v27);
    v24 = 31;
    goto LABEL_18;
  }
  v29 = v35;
  if ( v37 == 3 )
  {
    if ( v35 )
    {
      v35 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
    }
    v31 = v34;
    if ( v34 )
    {
      v34 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    }
    return 0;
  }
  else
  {
    if ( v35 )
    {
      v35 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
    }
    v30 = v34;
    if ( v34 )
    {
      v34 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    }
    return 2147942405LL;
  }
}

```

## disassembly

```asm
0x180051540  push    rbp
0x180051542  push    rbx
0x180051543  push    rsi
0x180051544  push    rdi
0x180051545  push    r12
0x180051547  push    r13
0x180051549  push    r14
0x18005154b  push    r15
0x18005154d  lea     rbp, [rsp-1Fh]
0x180051552  sub     rsp, 88h
0x180051559  mov     rax, cs:__security_cookie
0x180051560  xor     rax, rsp
0x180051563  mov     [rbp+57h+var_48], rax
0x180051567  mov     r12d, ecx
0x18005156a  lea     rdx, [rbp+57h+Pid]; Pid
0x18005156e  xor     r13d, r13d
0x180051571  xor     ecx, ecx; Binding
0x180051573  mov     [rbp+57h+Pid], r13d
0x180051577  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x18005157d  mov     ebx, eax
0x18005157f  test    eax, eax
0x180051581  jns     short loc_18005159C
0x180051583  mov     edx, eax; int
0x180051585  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18005158a  lea     r9d, [r13+14h]
0x18005158e  mov     ecx, ebx
0x180051590  call    Log_HREvent_11
0x180051595  mov     eax, ebx
0x180051597  jmp     loc_1800517B0
0x18005159c  lea     r9, [rbp+57h+string]; string
0x1800515a0  mov     [rbp+57h+var_60], r13
0x1800515a4  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1800515a8  mov     edx, 32h ; '2'; length
0x1800515ad  lea     rcx, ?RuntimeClass_Windows_Internal_CapabilityAccess_CapabilityAccess@@3QBGB; "Windows.Internal.CapabilityAccess.Capab"...
0x1800515b4  call    cs:__imp_WindowsCreateStringReference
0x1800515ba  test    eax, eax
0x1800515bc  jns     short loc_1800515D3
0x1800515be  xor     r9d, r9d; lpArguments
0x1800515c1  xor     r8d, r8d; nNumberOfArguments
0x1800515c4  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800515c9  lea     edx, [r9+1]; dwExceptionFlags
0x1800515cd  call    cs:__imp_RaiseException
0x1800515d3  mov     rcx, [rbp+57h+var_60]
0x1800515d7  mov     rbx, [rbp+57h+string]
0x1800515db  test    rcx, rcx
0x1800515de  jz      short loc_1800515F0
0x1800515e0  mov     [rbp+57h+var_60], r13
0x1800515e4  mov     rax, [rcx]
0x1800515e7  mov     rax, [rax+10h]
0x1800515eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800515f0  lea     r8, [rbp+57h+var_60]
0x1800515f4  mov     rcx, rbx
0x1800515f7  lea     rdx, _GUID_518f3880_4e5c_4524_ab03_cd01336b2178
0x1800515fe  call    cs:__imp_RoGetActivationFactory
0x180051604  mov     ebx, eax
0x180051606  test    eax, eax
0x180051608  jns     short loc_180051640
0x18005160a  mov     edx, eax; int
0x18005160c  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180051611  mov     r9d, 18h
0x180051617  mov     ecx, ebx
0x180051619  call    Log_HREvent_11
0x18005161e  mov     rcx, [rbp+57h+var_60]
0x180051622  test    rcx, rcx
0x180051625  jz      loc_180051595
0x18005162b  mov     [rbp+57h+var_60], r13
0x18005162f  mov     rdx, [rcx]
0x180051632  mov     rax, [rdx+10h]
0x180051636  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005163b  jmp     loc_180051595
0x180051640  mov     rsi, [rbp+57h+var_60]
0x180051644  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180051648  mov     r14d, [rbp+57h+Pid]
0x18005164c  mov     rdi, cs:?c_szCapabilityPhoneCall@@3QEBGEB; ushort const * const c_szCapabilityPhoneCall
0x180051653  mov     [rbp+57h+var_58], r13
0x180051657  mov     rax, [rsi]
0x18005165a  mov     r15, [rax+38h]
0x18005165e  inc     rbx
0x180051661  cmp     [rdi+rbx*2], r13w
0x180051666  jnz     short loc_18005165E
0x180051668  mov     eax, 0FFFFFFFFh
0x18005166d  cmp     rbx, rax
0x180051670  jbe     short loc_180051689
0x180051672  xor     r9d, r9d; lpArguments
0x180051675  xor     r8d, r8d; nNumberOfArguments
0x180051678  mov     ecx, 0C000000Dh; dwExceptionCode
0x18005167d  mov     ebx, eax
0x18005167f  lea     edx, [r9+1]; dwExceptionFlags
0x180051683  call    cs:__imp_RaiseException
0x180051689  lea     r9, [rbp+57h+string]; string
0x18005168d  mov     edx, ebx; length
0x18005168f  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180051693  mov     rcx, rdi; sourceString
0x180051696  call    cs:__imp_WindowsCreateStringReference
0x18005169c  mov     r8, [rbp+57h+string]
0x1800516a0  lea     rax, [rbp+57h+var_58]
0x1800516a4  mov     [rsp+0C0h+var_98], rax
0x1800516a9  mov     r9d, r14d
0x1800516ac  mov     rax, r15
0x1800516af  mov     [rsp+0C0h+var_A0], r12d
0x1800516b4  xor     edx, edx
0x1800516b6  mov     rcx, rsi
0x1800516b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800516be  mov     ebx, eax
0x1800516c0  test    eax, eax
0x1800516c2  jns     short loc_18005170E
0x1800516c4  mov     edx, eax; int
0x1800516c6  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x1800516cb  mov     r9d, 1Ch
0x1800516d1  mov     ecx, ebx
0x1800516d3  call    Log_HREvent_11
0x1800516d8  mov     rcx, [rbp+57h+var_58]
0x1800516dc  test    rcx, rcx
0x1800516df  jz      short loc_1800516F1
0x1800516e1  mov     [rbp+57h+var_58], r13
0x1800516e5  mov     rdx, [rcx]
0x1800516e8  mov     rax, [rdx+10h]
0x1800516ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800516f1  mov     rcx, [rbp+57h+var_60]
0x1800516f5  test    rcx, rcx
0x1800516f8  jz      loc_180051595
0x1800516fe  mov     [rbp+57h+var_60], r13
0x180051702  mov     rax, [rcx]
0x180051705  mov     rax, [rax+10h]
0x180051709  jmp     loc_180051636
0x18005170e  mov     rcx, [rbp+57h+var_58]
0x180051712  lea     rdx, [rbp+57h+var_4C]
0x180051716  mov     [rbp+57h+var_4C], 3
0x18005171d  mov     rax, [rcx]
0x180051720  mov     rax, [rax+98h]
0x180051727  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005172c  mov     ebx, eax
0x18005172e  test    eax, eax
0x180051730  jns     short loc_180051741
0x180051732  mov     edx, eax; int
0x180051734  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180051739  mov     r9d, 1Fh
0x18005173f  jmp     short loc_1800516D1
0x180051741  cmp     [rbp+57h+var_4C], 3
0x180051745  mov     rcx, [rbp+57h+var_58]
0x180051749  jz      short loc_180051780
0x18005174b  test    rcx, rcx
0x18005174e  jz      short loc_180051760
0x180051750  mov     [rbp+57h+var_58], r13
0x180051754  mov     rax, [rcx]
0x180051757  mov     rax, [rax+10h]
0x18005175b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051760  mov     rcx, [rbp+57h+var_60]
0x180051764  test    rcx, rcx
0x180051767  jz      short loc_180051779
0x180051769  mov     [rbp+57h+var_60], r13
0x18005176d  mov     rax, [rcx]
0x180051770  mov     rax, [rax+10h]
0x180051774  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051779  mov     eax, 80070005h
0x18005177e  jmp     short loc_1800517B0
0x180051780  test    rcx, rcx
0x180051783  jz      short loc_180051795
0x180051785  mov     [rbp+57h+var_58], r13
0x180051789  mov     rax, [rcx]
0x18005178c  mov     rax, [rax+10h]
0x180051790  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051795  mov     rcx, [rbp+57h+var_60]
0x180051799  test    rcx, rcx
0x18005179c  jz      short loc_1800517AE
0x18005179e  mov     [rbp+57h+var_60], r13
0x1800517a2  mov     rax, [rcx]
0x1800517a5  mov     rax, [rax+10h]
0x1800517a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800517ae  xor     eax, eax
0x1800517b0  mov     rcx, [rbp+57h+var_48]
0x1800517b4  xor     rcx, rsp; StackCookie
0x1800517b7  call    __security_check_cookie
0x1800517bc  add     rsp, 88h
0x1800517c3  pop     r15
0x1800517c5  pop     r14
0x1800517c7  pop     r13
0x1800517c9  pop     r12
0x1800517cb  pop     rdi
0x1800517cc  pop     rsi
0x1800517cd  pop     rbx
0x1800517ce  pop     rbp
0x1800517cf  retn
```
