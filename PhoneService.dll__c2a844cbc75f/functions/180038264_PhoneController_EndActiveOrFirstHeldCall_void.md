# PhoneController::_EndActiveOrFirstHeldCall(void)

- ea: `0x180038264`
- end: `0x1800384b4`
- name: `?_EndActiveOrFirstHeldCall@PhoneController@@IEAAJXZ`
- size: `592`
- prototype: `__int64 __fastcall(PhoneController *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x180039300`

## callees

- `0x1800012b8`
- `0x180006e94`
- `0x18002c574`
- `0x18002c580`
- `0x180038264`
- `0x180038688`
- `0x18005292c`
- `0x180053254`
- `0x18007f9ec`
- `0x18008d9b0`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180038287`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800382a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180038287`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800382a7`

## string_xrefs

- `0x18003829b`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x1800383f3`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x180038409`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x18003845c`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`

## pseudocode

```c
__int64 __fastcall PhoneController::_EndActiveOrFirstHeldCall(PhoneController *this)
{
  __int64 v2; // rcx
  __int64 v3; // r8
  __int64 v4; // r9
  __int64 v5; // rcx
  struct CallInfo *v6; // rdx
  struct CallInfo **v7; // rax
  struct CallInfo *v8; // rbx
  struct CallInfo **v9; // rax
  struct CallInfo *v10; // rbx
  const char *v11; // rcx
  unsigned int v12; // ebx
  void (*v13)(void); // rax
  int v15; // eax
  BackTraceCollection *v16; // rcx
  const char *v17; // [rsp+30h] [rbp-20h] BYREF
  struct CallInfo *v18; // [rsp+38h] [rbp-18h] BYREF

  if ( *((_DWORD *)this + 60) != GetCurrentThreadId() )
  {
    Log_AssertionEvent_3(v2, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 970);
    if ( *((_DWORD *)this + 60) != GetCurrentThreadId() )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  if ( (unsigned int)dword_1800B3200 > 4 )
  {
    v17 = "PhoneController::_EndActiveOrFirstHeldCall";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      v2,
      (int)word_1800A8B6A,
      v3,
      v4,
      (const unsigned __int16 **)&v17);
  }
  v5 = *((_QWORD *)this + 12);
  v18 = 0;
  PhoneCallStorage::GetActiveCall(v5, &v18);
  v6 = v18;
  if ( !v18 )
  {
    v7 = (struct CallInfo **)PhoneCallStorage::FindCallByState(*((_QWORD *)this + 12), &v17, 2, 0);
    v6 = v18;
    v8 = *v7;
    if ( v18 != *v7 )
    {
      if ( v8 )
      {
        (*(void (__fastcall **)(struct CallInfo *))(*(_QWORD *)v8 + 8LL))(*v7);
        v6 = v18;
      }
      if ( v6 )
        (*(void (__fastcall **)(struct CallInfo *))(*(_QWORD *)v6 + 16LL))(v6);
      v6 = v8;
      v18 = v8;
    }
    if ( v17 )
    {
      (*(void (__fastcall **)(const char *))(*(_QWORD *)v17 + 16LL))(v17);
      v6 = v18;
    }
    if ( !v6 )
    {
      v9 = (struct CallInfo **)PhoneCallStorage::FindCallByState(*((_QWORD *)this + 12), &v17, 4, 0);
      v6 = v18;
      v10 = *v9;
      if ( v18 != *v9 )
      {
        if ( v10 )
        {
          (*(void (__fastcall **)(struct CallInfo *))(*(_QWORD *)v10 + 8LL))(*v9);
          v6 = v18;
        }
        if ( v6 )
          (*(void (__fastcall **)(struct CallInfo *))(*(_QWORD *)v6 + 16LL))(v6);
        v6 = v10;
        v18 = v10;
      }
      v11 = v17;
      if ( v17 )
      {
        (*(void (__fastcall **)(const char *))(*(_QWORD *)v17 + 16LL))(v17);
        v6 = v18;
      }
      if ( !v6 )
      {
        Log_AssertionEvent_3(v11, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 998);
        MicrosoftTelemetryAssertTriggeredNoArgs();
        v12 = -2147019873;
        Log_HREvent_7(2147947423LL, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 999);
        if ( !v18 )
          return v12;
        v13 = *(void (**)(void))(*(_QWORD *)v18 + 16LL);
LABEL_27:
        v13();
        return v12;
      }
    }
  }
  v15 = PhoneController::_EndCall(this, v6, 1, 1);
  v12 = v15;
  if ( v15 < 0 )
  {
    BackTraceCollection::Capture(v16, v15);
    Log_HREvent_7(v12, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 1002);
    if ( !v18 )
      return v12;
    v13 = *(void (**)(void))(*(_QWORD *)v18 + 16LL);
    goto LABEL_27;
  }
  if ( v18 )
    (*(void (__fastcall **)(struct CallInfo *))(*(_QWORD *)v18 + 16LL))(v18);
  return 0;
}

```

## disassembly

```asm
0x180038264  mov     [rsp-8+arg_8], rbx
0x180038269  mov     [rsp-8+arg_10], rdi
0x18003826e  push    rbp
0x18003826f  mov     rbp, rsp
0x180038272  sub     rsp, 50h
0x180038276  mov     rax, cs:__security_cookie
0x18003827d  xor     rax, rsp
0x180038280  mov     [rbp+var_10], rax
0x180038284  mov     rdi, rcx
0x180038287  call    cs:__imp_GetCurrentThreadId
0x18003828d  cmp     [rdi+0F0h], eax
0x180038293  jz      short loc_1800382BA
0x180038295  mov     r8d, 3CAh
0x18003829b  lea     rdx, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x1800382a2  call    Log_AssertionEvent_3
0x1800382a7  call    cs:__imp_GetCurrentThreadId
0x1800382ad  cmp     [rdi+0F0h], eax
0x1800382b3  jz      short loc_1800382BA
0x1800382b5  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800382ba  mov     eax, cs:dword_1800B3200
0x1800382c0  cmp     eax, 4
0x1800382c3  jbe     short loc_1800382E5
0x1800382c5  lea     rax, aPhonecontrolle; "PhoneController::_EndActiveOrFirstHeldC"...
0x1800382cc  mov     [rbp+var_20], rax
0x1800382d0  lea     rdx, word_1800A8B6A
0x1800382d7  lea     rax, [rbp+var_20]
0x1800382db  mov     [rsp+50h+var_30], rax
0x1800382e0  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1800382e5  mov     rcx, [rdi+60h]
0x1800382e9  lea     rdx, [rbp+var_18]
0x1800382ed  mov     [rbp+var_18], 0
0x1800382f5  call    ?GetActiveCall@PhoneCallStorage@@QEAA?AV?$CComPtr@VCallInfo@@@ATL@@XZ; PhoneCallStorage::GetActiveCall(void)
0x1800382fa  mov     rdx, [rbp+var_18]; struct CallInfo *
0x1800382fe  test    rdx, rdx
0x180038301  jnz     loc_180038438
0x180038307  mov     rcx, [rdi+60h]
0x18003830b  lea     r8d, [rdx+2]
0x18003830f  lea     rdx, [rbp+var_20]
0x180038313  xor     r9d, r9d
0x180038316  call    ?FindCallByState@PhoneCallStorage@@QEAA?AV?$CComPtr@VCallInfo@@@ATL@@W4PH_CALLSTATE@@PEAUISecurityToken@@@Z; PhoneCallStorage::FindCallByState(PH_CALLSTATE,ISecurityToken *)
0x18003831b  mov     rdx, [rbp+var_18]
0x18003831f  mov     rbx, [rax]
0x180038322  cmp     rdx, rbx
0x180038325  jz      short loc_18003835A
0x180038327  test    rbx, rbx
0x18003832a  jz      short loc_18003833F
0x18003832c  mov     rax, [rbx]
0x18003832f  mov     rcx, rbx
0x180038332  mov     rax, [rax+8]
0x180038336  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003833b  mov     rdx, [rbp+var_18]
0x18003833f  test    rdx, rdx
0x180038342  jz      short loc_180038353
0x180038344  mov     rax, [rdx]
0x180038347  mov     rcx, rdx
0x18003834a  mov     rax, [rax+10h]
0x18003834e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038353  mov     rdx, rbx
0x180038356  mov     [rbp+var_18], rbx
0x18003835a  mov     rcx, [rbp+var_20]
0x18003835e  test    rcx, rcx
0x180038361  jz      short loc_180038373
0x180038363  mov     rax, [rcx]
0x180038366  mov     rax, [rax+10h]
0x18003836a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003836f  mov     rdx, [rbp+var_18]
0x180038373  test    rdx, rdx
0x180038376  jnz     loc_180038438
0x18003837c  mov     rcx, [rdi+60h]
0x180038380  lea     r8d, [rdx+4]
0x180038384  lea     rdx, [rbp+var_20]
0x180038388  xor     r9d, r9d
0x18003838b  call    ?FindCallByState@PhoneCallStorage@@QEAA?AV?$CComPtr@VCallInfo@@@ATL@@W4PH_CALLSTATE@@PEAUISecurityToken@@@Z; PhoneCallStorage::FindCallByState(PH_CALLSTATE,ISecurityToken *)
0x180038390  mov     rdx, [rbp+var_18]
0x180038394  mov     rbx, [rax]
0x180038397  cmp     rdx, rbx
0x18003839a  jz      short loc_1800383CF
0x18003839c  test    rbx, rbx
0x18003839f  jz      short loc_1800383B4
0x1800383a1  mov     rax, [rbx]
0x1800383a4  mov     rcx, rbx
0x1800383a7  mov     rax, [rax+8]
0x1800383ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800383b0  mov     rdx, [rbp+var_18]
0x1800383b4  test    rdx, rdx
0x1800383b7  jz      short loc_1800383C8
0x1800383b9  mov     rax, [rdx]
0x1800383bc  mov     rcx, rdx
0x1800383bf  mov     rax, [rax+10h]
0x1800383c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800383c8  mov     rdx, rbx
0x1800383cb  mov     [rbp+var_18], rbx
0x1800383cf  mov     rcx, [rbp+var_20]
0x1800383d3  test    rcx, rcx
0x1800383d6  jz      short loc_1800383E8
0x1800383d8  mov     rax, [rcx]
0x1800383db  mov     rax, [rax+10h]
0x1800383df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800383e4  mov     rdx, [rbp+var_18]
0x1800383e8  test    rdx, rdx
0x1800383eb  jnz     short loc_180038438
0x1800383ed  mov     r8d, 3E6h
0x1800383f3  lea     rdx, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x1800383fa  call    Log_AssertionEvent_3
0x1800383ff  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180038404  mov     ebx, 8007139Fh
0x180038409  lea     r8, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180038410  mov     ecx, ebx
0x180038412  mov     r9d, 3E7h
0x180038418  xor     edx, edx
0x18003841a  call    Log_HREvent_7
0x18003841f  mov     rcx, [rbp+var_18]
0x180038423  test    rcx, rcx
0x180038426  jz      short loc_180038434
0x180038428  mov     rdx, [rcx]
0x18003842b  mov     rax, [rdx+10h]
0x18003842f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038434  mov     eax, ebx
0x180038436  jmp     short loc_180038498
0x180038438  mov     r9d, 1; int
0x18003843e  mov     rcx, rdi; this
0x180038441  mov     r8d, r9d; int
0x180038444  call    ?_EndCall@PhoneController@@IEAAJPEAVCallInfo@@HH@Z; PhoneController::_EndCall(CallInfo *,int,int)
0x180038449  mov     ebx, eax
0x18003844b  test    eax, eax
0x18003844d  jns     short loc_180038481
0x18003844f  mov     edx, eax; int
0x180038451  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180038456  mov     r9d, 3EAh
0x18003845c  lea     r8, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180038463  mov     edx, 1
0x180038468  mov     ecx, ebx
0x18003846a  call    Log_HREvent_7
0x18003846f  mov     rcx, [rbp+var_18]
0x180038473  test    rcx, rcx
0x180038476  jz      short loc_180038434
0x180038478  mov     rax, [rcx]
0x18003847b  mov     rax, [rax+10h]
0x18003847f  jmp     short loc_18003842F
0x180038481  mov     rcx, [rbp+var_18]
0x180038485  test    rcx, rcx
0x180038488  jz      short loc_180038496
0x18003848a  mov     rax, [rcx]
0x18003848d  mov     rax, [rax+10h]
0x180038491  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038496  xor     eax, eax
0x180038498  mov     rcx, [rbp+var_10]
0x18003849c  xor     rcx, rsp; StackCookie
0x18003849f  call    __security_check_cookie
0x1800384a4  mov     rbx, [rsp+50h+arg_8]
0x1800384a9  mov     rdi, [rsp+50h+arg_10]
0x1800384ae  add     rsp, 50h
0x1800384b2  pop     rbp
0x1800384b3  retn
```
