# PhoneController::_HandleRequestFailure(PhoneController::RequestInfo *,long)

- ea: `0x18003d070`
- end: `0x18003d407`
- name: `?_HandleRequestFailure@PhoneController@@IEAAXPEAURequestInfo@1@J@Z`
- size: `919`
- prototype: `void __fastcall(PhoneController *__hidden this, struct PhoneController::RequestInfo *, int)`
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180043f90`

## callees

- `0x1800012b8`
- `0x18002c574`
- `0x18002c580`
- `0x180038688`
- `0x180038d2c`
- `0x18003ca40`
- `0x18003d070`
- `0x180047c90`
- `0x180049ed0`
- `0x180052424`
- `0x1800524c8`
- `0x180071a50`
- `0x1800770e4`
- `0x18007f9ec`
- `0x18008d9b0`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003d09e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003d0be`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003d09e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003d0be`

## string_xrefs

- `0x18003d0b2`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x18003d217`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x18003d299`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x18003d2f4`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x18003d381`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x18003d3aa`: `PhoneController: A Wireless Priority Service call failed because of another active IMS call.`

## pseudocode

```c
void __fastcall PhoneController::_HandleRequestFailure(
        PhoneController *this,
        struct PhoneController::RequestInfo *a2,
        unsigned int a3)
{
  char v3; // bl
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  int v10; // ecx
  __int64 v11; // rcx
  struct CallInfo *v12; // rbx
  __int64 v13; // rax
  struct CallInfo *v14; // rcx
  struct CallInfo *v15; // rdx
  char v16; // r14
  int v17; // eax
  _QWORD *v18; // rax
  char v19; // r14
  int v20; // eax
  unsigned int v21; // ebx
  __int64 v22; // rcx
  __int64 v23; // r8
  __int64 v24; // r9
  int IsServiceOn; // r14d
  unsigned int v26; // eax
  int v27; // eax
  const char *v28; // [rsp+30h] [rbp-20h] BYREF
  struct CallInfo *v29; // [rsp+38h] [rbp-18h] BYREF

  v3 = 0;
  LODWORD(v29) = 0;
  if ( *((_DWORD *)this + 60) != GetCurrentThreadId() )
  {
    Log_AssertionEvent_3(v7, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 4140);
    if ( *((_DWORD *)this + 60) != GetCurrentThreadId() )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  if ( (unsigned int)dword_1800B3200 > 4 )
  {
    v29 = (struct CallInfo *)"PhoneController::_HandleRequestFailure";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      v7,
      (int)&byte_1800A82A7,
      v8,
      v9,
      (const unsigned __int16 **)&v29);
  }
  v10 = *((_DWORD *)a2 + 5);
  if ( ((v10 - 8) & 0xFFFFFFF7) != 0 )
  {
    if ( v10 == 512 )
    {
      v11 = *((_QWORD *)this + 12);
      v29 = 0;
      PhoneCallStorage::FindCall(v11, &v29, (char *)a2 + 16, 0);
      v12 = v29;
      if ( v29 )
      {
        if ( (*((_DWORD *)v29 + 770) & 0x400) != 0 )
        {
          *((_DWORD *)v29 + 770) &= ~0x400u;
          (*(void (__fastcall **)(PhoneController *))(*(_QWORD *)this + 872LL))(this);
        }
        v13 = *(_QWORD *)v12;
        v14 = v12;
        goto LABEL_40;
      }
    }
    goto LABEL_41;
  }
  v29 = 0;
  PhoneController::_GetInfoForCallOrRepresentativeConferenceMember(this, &v29, (char *)a2 + 16, 0);
  v15 = v29;
  if ( !v29 )
    goto LABEL_30;
  *((_DWORD *)v29 + 1706) &= ~*((_DWORD *)a2 + 5);
  if ( *((_DWORD *)a2 + 5) != 8
    || (v3 = 1, !*(_QWORD *)PhoneCallStorage::FindActiveCallOnOtherLine(*((_QWORD *)this + 12), &v28, v29)) )
  {
    v15 = v29;
    goto LABEL_18;
  }
  v15 = v29;
  if ( *((_DWORD *)v29 + 760) == 4 )
  {
LABEL_18:
    v16 = 0;
    goto LABEL_19;
  }
  v16 = 1;
LABEL_19:
  if ( (v3 & 1) != 0 )
  {
    v3 &= ~1u;
    if ( v28 )
    {
      (*(void (__fastcall **)(const char *))(*(_QWORD *)v28 + 16LL))(v28);
      v15 = v29;
    }
  }
  if ( v16 )
  {
    v17 = PhoneController::_EndCall(this, v15, 1, 1);
    if ( v17 < 0 )
      Log_HREvent_7((unsigned int)v17, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 4235);
    v15 = v29;
  }
  if ( !v15
    || (v3 |= 2u,
        v18 = (_QWORD *)PhoneCallStorage::FindActiveCallOnOtherLine(*((_QWORD *)this + 12), &v28, v15),
        v15 = v29,
        !*v18)
    || *((_DWORD *)v29 + 760) == 4 )
  {
LABEL_30:
    v19 = 0;
    goto LABEL_31;
  }
  v19 = 1;
LABEL_31:
  if ( (v3 & 2) != 0 && v28 )
  {
    (*(void (__fastcall **)(const char *, struct CallInfo *))(*(_QWORD *)v28 + 16LL))(v28, v15);
    v15 = v29;
  }
  if ( v19 )
  {
    v20 = PhoneController::_EndCall(this, v15, 1, 1);
    if ( v20 < 0 )
      Log_HREvent_7((unsigned int)v20, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 4251);
    v15 = v29;
  }
  if ( v15 )
  {
    v13 = *(_QWORD *)v15;
    v14 = v15;
LABEL_40:
    (*(void (__fastcall **)(struct CallInfo *))(v13 + 16))(v14);
  }
LABEL_41:
  if ( *((_DWORD *)a2 + 8) )
  {
    v21 = 0;
  }
  else
  {
    if ( *((_DWORD *)a2 + 5) )
    {
      v21 = *((_DWORD *)qword_18009C020 + (unsigned int)CallVerbToIndex());
      goto LABEL_56;
    }
    if ( *((_DWORD *)a2 + 6) == 1 )
    {
      v21 = 11;
      goto LABEL_56;
    }
    if ( *((_DWORD *)a2 + 6) == 2 )
    {
      v21 = 12;
      goto LABEL_56;
    }
    if ( *((_DWORD *)a2 + 6) != 4 )
    {
      if ( *((_DWORD *)a2 + 6) == 8 )
      {
        v21 = 50;
        goto LABEL_56;
      }
      if ( *((_DWORD *)a2 + 6) == 16 )
      {
        v21 = 49;
        goto LABEL_56;
      }
      Log_AssertionEvent_3(
        (unsigned int)(*((_DWORD *)a2 + 6) - 8),
        "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp",
        73);
      MicrosoftTelemetryAssertTriggeredNoArgs();
    }
    v21 = 19;
  }
LABEL_56:
  IsServiceOn = PhoneLine::IsServiceOn(*(PhoneLine **)a2);
  if ( v21 != 13 )
    goto LABEL_66;
  if ( *((_QWORD *)this + 22) )
  {
    v26 = PhoneController::_TranslateProviderError(a3, IsServiceOn == 0);
    if ( v26 == 8 )
      v26 = 0;
    else
      v21 = 0;
    v27 = PhoneController::_EndFakeOutgoingCall(this, v26);
    if ( v27 < 0 )
      Log_HREvent_7((unsigned int)v27, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 4311);
  }
  if ( a3 == -2086535156 )
  {
    v21 = 44;
    if ( (unsigned int)dword_1800B3200 > 4 )
    {
      v28 = "PhoneController: A Wireless Priority Service call failed because of another active IMS call.";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v22,
        (int)byte_1800A827B,
        v23,
        v24,
        (const unsigned __int16 **)&v28);
    }
  }
  else
  {
LABEL_66:
    if ( !v21 )
      return;
  }
  if ( !IsServiceOn )
    v21 = 18;
  PhoneController::_SendDeferredErrorNotification(this, *(_QWORD *)a2, v21, a3);
}

```

## disassembly

```asm
0x18003d070  push    rbp
0x18003d072  push    rbx
0x18003d073  push    rsi
0x18003d074  push    rdi
0x18003d075  push    r13
0x18003d077  push    r14
0x18003d079  push    r15
0x18003d07b  mov     rbp, rsp
0x18003d07e  sub     rsp, 50h
0x18003d082  mov     rax, cs:__security_cookie
0x18003d089  xor     rax, rsp
0x18003d08c  mov     [rbp+var_10], rax
0x18003d090  xor     ebx, ebx
0x18003d092  mov     r15d, r8d
0x18003d095  mov     dword ptr [rbp+var_18], ebx
0x18003d098  mov     rdi, rdx
0x18003d09b  mov     rsi, rcx
0x18003d09e  call    cs:__imp_GetCurrentThreadId
0x18003d0a4  cmp     [rsi+0F0h], eax
0x18003d0aa  jz      short loc_18003D0D1
0x18003d0ac  mov     r8d, 102Ch
0x18003d0b2  lea     rdx, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18003d0b9  call    Log_AssertionEvent_3
0x18003d0be  call    cs:__imp_GetCurrentThreadId
0x18003d0c4  cmp     [rsi+0F0h], eax
0x18003d0ca  jz      short loc_18003D0D1
0x18003d0cc  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18003d0d1  mov     eax, cs:dword_1800B3200
0x18003d0d7  cmp     eax, 4
0x18003d0da  jbe     short loc_18003D0FC
0x18003d0dc  lea     rax, aPhonecontrolle_64; "PhoneController::_HandleRequestFailure"
0x18003d0e3  mov     [rbp+var_18], rax
0x18003d0e7  lea     rdx, byte_1800A82A7
0x18003d0ee  lea     rax, [rbp+var_18]
0x18003d0f2  mov     [rsp+50h+var_30], rax
0x18003d0f7  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18003d0fc  mov     ecx, [rdi+14h]
0x18003d0ff  lea     eax, [rcx-8]
0x18003d102  test    eax, 0FFFFFFF7h
0x18003d107  jz      short loc_18003D16B
0x18003d109  cmp     ecx, 200h
0x18003d10f  jnz     loc_18003D2C1
0x18003d115  mov     rcx, [rsi+60h]
0x18003d119  lea     r8, [rdi+10h]
0x18003d11d  xor     r9d, r9d
0x18003d120  mov     [rbp+var_18], rbx
0x18003d124  lea     rdx, [rbp+var_18]
0x18003d128  call    ?FindCall@PhoneCallStorage@@QEAA?AV?$CComPtr@VCallInfo@@@ATL@@AEBIPEAUISecurityToken@@@Z; PhoneCallStorage::FindCall(uint const &,ISecurityToken *)
0x18003d12d  mov     rbx, [rbp+var_18]
0x18003d131  test    rbx, rbx
0x18003d134  jz      loc_18003D2C1
0x18003d13a  test    dword ptr [rbx+0C08h], 400h
0x18003d144  jz      short loc_18003D160
0x18003d146  btr     dword ptr [rbx+0C08h], 0Ah
0x18003d14e  mov     rcx, rsi
0x18003d151  mov     rax, [rsi]
0x18003d154  mov     rax, [rax+368h]
0x18003d15b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d160  mov     rax, [rbx]
0x18003d163  mov     rcx, rbx
0x18003d166  jmp     loc_18003D2B8
0x18003d16b  lea     r8, [rdi+10h]
0x18003d16f  mov     [rbp+var_18], rbx
0x18003d173  xor     r9d, r9d
0x18003d176  lea     rdx, [rbp+var_18]
0x18003d17a  mov     rcx, rsi
0x18003d17d  call    ?_GetInfoForCallOrRepresentativeConferenceMember@PhoneController@@IEAA?AV?$CComPtr@VCallInfo@@@ATL@@AEBIPEAUISecurityToken@@@Z; PhoneController::_GetInfoForCallOrRepresentativeConferenceMember(uint const &,ISecurityToken *)
0x18003d182  mov     rdx, [rbp+var_18]
0x18003d186  mov     r13d, 1
0x18003d18c  test    rdx, rdx
0x18003d18f  jz      loc_18003D25B
0x18003d195  mov     eax, [rdi+14h]
0x18003d198  not     eax
0x18003d19a  and     [rdx+1AA8h], eax
0x18003d1a0  cmp     dword ptr [rdi+14h], 8
0x18003d1a4  jnz     short loc_18003D1D2
0x18003d1a6  mov     r8, [rbp+var_18]
0x18003d1aa  lea     rdx, [rbp+var_20]
0x18003d1ae  mov     rcx, [rsi+60h]
0x18003d1b2  mov     ebx, r13d
0x18003d1b5  call    ?FindActiveCallOnOtherLine@PhoneCallStorage@@QEAA?AV?$CComPtr@VCallInfo@@@ATL@@PEAVCallInfo@@@Z; PhoneCallStorage::FindActiveCallOnOtherLine(CallInfo *)
0x18003d1ba  cmp     qword ptr [rax], 0
0x18003d1be  jz      short loc_18003D1D2
0x18003d1c0  mov     rdx, [rbp+var_18]
0x18003d1c4  cmp     dword ptr [rdx+0BE0h], 4
0x18003d1cb  jz      short loc_18003D1D6
0x18003d1cd  mov     r14b, r13b
0x18003d1d0  jmp     short loc_18003D1D9
0x18003d1d2  mov     rdx, [rbp+var_18]
0x18003d1d6  xor     r14b, r14b
0x18003d1d9  test    r13b, bl
0x18003d1dc  jz      short loc_18003D1FA
0x18003d1de  mov     rcx, [rbp+var_20]
0x18003d1e2  and     ebx, 0FFFFFFFEh
0x18003d1e5  test    rcx, rcx
0x18003d1e8  jz      short loc_18003D1FA
0x18003d1ea  mov     rax, [rcx]
0x18003d1ed  mov     rax, [rax+10h]
0x18003d1f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d1f6  mov     rdx, [rbp+var_18]; struct CallInfo *
0x18003d1fa  test    r14b, r14b
0x18003d1fd  jz      short loc_18003D22B
0x18003d1ff  mov     r9d, r13d; int
0x18003d202  mov     r8d, r13d; int
0x18003d205  mov     rcx, rsi; this
0x18003d208  call    ?_EndCall@PhoneController@@IEAAJPEAVCallInfo@@HH@Z; PhoneController::_EndCall(CallInfo *,int,int)
0x18003d20d  test    eax, eax
0x18003d20f  jns     short loc_18003D227
0x18003d211  mov     r9d, 108Bh
0x18003d217  lea     r8, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18003d21e  xor     edx, edx
0x18003d220  mov     ecx, eax
0x18003d222  call    Log_HREvent_7
0x18003d227  mov     rdx, [rbp+var_18]
0x18003d22b  test    rdx, rdx
0x18003d22e  jz      short loc_18003D25B
0x18003d230  mov     rcx, [rsi+60h]
0x18003d234  mov     r8, rdx
0x18003d237  lea     rdx, [rbp+var_20]
0x18003d23b  or      ebx, 2
0x18003d23e  call    ?FindActiveCallOnOtherLine@PhoneCallStorage@@QEAA?AV?$CComPtr@VCallInfo@@@ATL@@PEAVCallInfo@@@Z; PhoneCallStorage::FindActiveCallOnOtherLine(CallInfo *)
0x18003d243  mov     rdx, [rbp+var_18]
0x18003d247  cmp     qword ptr [rax], 0
0x18003d24b  jz      short loc_18003D25B
0x18003d24d  cmp     dword ptr [rdx+0BE0h], 4
0x18003d254  jz      short loc_18003D25B
0x18003d256  mov     r14b, r13b
0x18003d259  jmp     short loc_18003D25E
0x18003d25b  xor     r14b, r14b
0x18003d25e  test    bl, 2
0x18003d261  jz      short loc_18003D27C
0x18003d263  mov     rcx, [rbp+var_20]
0x18003d267  test    rcx, rcx
0x18003d26a  jz      short loc_18003D27C
0x18003d26c  mov     rax, [rcx]
0x18003d26f  mov     rax, [rax+10h]
0x18003d273  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d278  mov     rdx, [rbp+var_18]; struct CallInfo *
0x18003d27c  test    r14b, r14b
0x18003d27f  jz      short loc_18003D2AD
0x18003d281  mov     r9d, r13d; int
0x18003d284  mov     r8d, r13d; int
0x18003d287  mov     rcx, rsi; this
0x18003d28a  call    ?_EndCall@PhoneController@@IEAAJPEAVCallInfo@@HH@Z; PhoneController::_EndCall(CallInfo *,int,int)
0x18003d28f  test    eax, eax
0x18003d291  jns     short loc_18003D2A9
0x18003d293  mov     r9d, 109Bh
0x18003d299  lea     r8, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18003d2a0  xor     edx, edx
0x18003d2a2  mov     ecx, eax
0x18003d2a4  call    Log_HREvent_7
0x18003d2a9  mov     rdx, [rbp+var_18]
0x18003d2ad  test    rdx, rdx
0x18003d2b0  jz      short loc_18003D2C1
0x18003d2b2  mov     rax, [rdx]
0x18003d2b5  mov     rcx, rdx
0x18003d2b8  mov     rax, [rax+10h]
0x18003d2bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d2c1  cmp     dword ptr [rdi+20h], 0
0x18003d2c5  jz      short loc_18003D2CB
0x18003d2c7  xor     ebx, ebx
0x18003d2c9  jmp     short loc_18003D339
0x18003d2cb  mov     ecx, [rdi+14h]
0x18003d2ce  test    ecx, ecx
0x18003d2d0  jnz     short loc_18003D328
0x18003d2d2  mov     ecx, [rdi+18h]
0x18003d2d5  sub     ecx, 1
0x18003d2d8  jz      short loc_18003D321
0x18003d2da  sub     ecx, 1
0x18003d2dd  jz      short loc_18003D31A
0x18003d2df  sub     ecx, 2
0x18003d2e2  jz      short loc_18003D305
0x18003d2e4  sub     ecx, 4
0x18003d2e7  jz      short loc_18003D313
0x18003d2e9  cmp     ecx, 8
0x18003d2ec  jz      short loc_18003D30C
0x18003d2ee  mov     r8d, 49h ; 'I'
0x18003d2f4  lea     rdx, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18003d2fb  call    Log_AssertionEvent_3
0x18003d300  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18003d305  mov     ebx, 13h
0x18003d30a  jmp     short loc_18003D339
0x18003d30c  mov     ebx, 31h ; '1'
0x18003d311  jmp     short loc_18003D339
0x18003d313  mov     ebx, 32h ; '2'
0x18003d318  jmp     short loc_18003D339
0x18003d31a  mov     ebx, 0Ch
0x18003d31f  jmp     short loc_18003D339
0x18003d321  mov     ebx, 0Bh
0x18003d326  jmp     short loc_18003D339
0x18003d328  call    ?CallVerbToIndex@@YAIW4CallVerbs@@@Z; CallVerbToIndex(CallVerbs)
0x18003d32d  mov     eax, eax
0x18003d32f  lea     rbx, qword_18009C020
0x18003d336  mov     ebx, [rbx+rax*4]
0x18003d339  mov     rcx, [rdi]; this
0x18003d33c  call    ?IsServiceOn@PhoneLine@@QEBAHXZ; PhoneLine::IsServiceOn(void)
0x18003d341  xor     edx, edx
0x18003d343  mov     r14d, eax
0x18003d346  test    eax, eax
0x18003d348  setz    dl
0x18003d34b  cmp     ebx, 0Dh
0x18003d34e  jnz     short loc_18003D3CC
0x18003d350  cmp     qword ptr [rsi+0B0h], 0
0x18003d358  jz      short loc_18003D391
0x18003d35a  mov     ecx, r15d
0x18003d35d  call    ?_TranslateProviderError@PhoneController@@KA?AW4PH_CALLSTATEREASON@@JH@Z; PhoneController::_TranslateProviderError(long,int)
0x18003d362  cmp     eax, 8
0x18003d365  jnz     short loc_18003D36B
0x18003d367  xor     eax, eax
0x18003d369  jmp     short loc_18003D36D
0x18003d36b  xor     ebx, ebx
0x18003d36d  mov     edx, eax
0x18003d36f  mov     rcx, rsi
0x18003d372  call    ?_EndFakeOutgoingCall@PhoneController@@IEAAJW4PH_CALLSTATEREASON@@@Z; PhoneController::_EndFakeOutgoingCall(PH_CALLSTATEREASON)
0x18003d377  test    eax, eax
0x18003d379  jns     short loc_18003D391
0x18003d37b  mov     r9d, 10D7h
0x18003d381  lea     r8, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18003d388  xor     edx, edx
0x18003d38a  mov     ecx, eax
0x18003d38c  call    Log_HREvent_7
0x18003d391  cmp     r15d, 83A2000Ch
0x18003d398  jnz     short loc_18003D3CC
0x18003d39a  mov     eax, cs:dword_1800B3200
0x18003d3a0  mov     ebx, 2Ch ; ','
0x18003d3a5  cmp     eax, 4
0x18003d3a8  jbe     short loc_18003D3D0
0x18003d3aa  lea     rax, aPhonecontrolle_51; "PhoneController: A Wireless Priority Se"...
0x18003d3b1  mov     [rbp+var_20], rax
0x18003d3b5  lea     rdx, byte_1800A827B
0x18003d3bc  lea     rax, [rbp+var_20]
0x18003d3c0  mov     [rsp+50h+var_30], rax
0x18003d3c5  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18003d3ca  jmp     short loc_18003D3D0
0x18003d3cc  test    ebx, ebx
0x18003d3ce  jz      short loc_18003D3EC
0x18003d3d0  mov     rdx, [rdi]
0x18003d3d3  test    r14d, r14d
0x18003d3d6  mov     eax, 12h
0x18003d3db  mov     r9d, r15d
0x18003d3de  cmovz   ebx, eax
0x18003d3e1  mov     rcx, rsi
0x18003d3e4  mov     r8d, ebx
0x18003d3e7  call    ?_SendDeferredErrorNotification@PhoneController@@IEAAXPEBVPhoneLine@@W4PH_ERROR@@J@Z; PhoneController::_SendDeferredErrorNotification(PhoneLine const *,PH_ERROR,long)
0x18003d3ec  mov     rcx, [rbp+var_10]
0x18003d3f0  xor     rcx, rsp; StackCookie
0x18003d3f3  call    __security_check_cookie
0x18003d3f8  add     rsp, 50h
0x18003d3fc  pop     r15
0x18003d3fe  pop     r14
0x18003d400  pop     r13
0x18003d402  pop     rdi
0x18003d403  pop     rsi
0x18003d404  pop     rbx
0x18003d405  pop     rbp
0x18003d406  retn
```
