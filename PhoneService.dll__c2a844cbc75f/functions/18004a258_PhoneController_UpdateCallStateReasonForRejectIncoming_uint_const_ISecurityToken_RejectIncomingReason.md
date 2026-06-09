# PhoneController::_UpdateCallStateReasonForRejectIncoming(uint const &,ISecurityToken *,RejectIncomingReason)

- ea: `0x18004a258`
- end: `0x18004a47a`
- name: `?_UpdateCallStateReasonForRejectIncoming@PhoneController@@IEAAJAEBIPEAUISecurityToken@@W4RejectIncomingReason@@@Z`
- size: `546`
- prototype: `int __high(const unsigned int *, struct ISecurityToken *, enum RejectIncomingReason)`
- caller_count: `1`
- callee_count: `13`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18002f6d0`

## callees

- `0x180001348`
- `0x180006e94`
- `0x18002c574`
- `0x18002c580`
- `0x1800368d0`
- `0x18004a258`
- `0x18004f300`
- `0x18004f76c`
- `0x1800524c8`
- `0x18007f9ec`
- `0x18008d95a`
- `0x18008d9b0`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004a28b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004a2ab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004a28b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004a2ab`

## string_xrefs

- `0x18004a29f`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x18004a316`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x18004a34b`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x18004a419`: `PhoneController: Update callInfo callStateReason for reject incoming`

## pseudocode

```c
__int64 __fastcall PhoneController::_UpdateCallStateReasonForRejectIncoming(
        __int64 a1,
        _DWORD *a2,
        struct ISecurityToken *a3,
        unsigned int a4)
{
  __int64 v8; // rcx
  struct CallInfo **v9; // rax
  struct CallInfo *v10; // rbx
  BackTraceCollection *v11; // rcx
  int v13; // eax
  BackTraceCollection *v14; // rcx
  unsigned int v15; // edi
  __int64 v16; // r9
  __int64 v17; // rdx
  __int64 v18; // rcx
  int v19; // eax
  int v20; // eax
  BackTraceCollection *v21; // rcx
  __int64 v22; // r8
  __int64 v23; // r9
  unsigned int v24; // [rsp+40h] [rbp-C0h] BYREF
  BackTraceCollection *v25; // [rsp+48h] [rbp-B8h] BYREF
  const char *v26; // [rsp+50h] [rbp-B0h] BYREF
  _DWORD v27[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v28; // [rsp+68h] [rbp-98h]
  char v29[748]; // [rsp+70h] [rbp-90h] BYREF
  int v30; // [rsp+35Ch] [rbp+25Ch]

  if ( *(_DWORD *)(a1 + 240) != GetCurrentThreadId() )
  {
    Log_AssertionEvent_3(v8, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 6842);
    if ( *(_DWORD *)(a1 + 240) != GetCurrentThreadId() )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  v9 = (struct CallInfo **)PhoneCallStorage::FindCall(*(_QWORD *)(a1 + 96), &v25, a2, a3);
  v10 = *v9;
  if ( *v9 )
    (*(void (__fastcall **)(struct CallInfo *))(*(_QWORD *)v10 + 8LL))(*v9);
  v11 = v25;
  if ( v25 )
    (*(void (__fastcall **)(BackTraceCollection *))(*(_QWORD *)v25 + 16LL))(v25);
  if ( !v10 )
  {
    BackTraceCollection::Capture(v11, -2147023728);
    Log_HREvent_7(2147943568LL, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 6847);
    return 2147943568LL;
  }
  v13 = PhoneController::_CheckLineOwnershipForCall(v11, v10, a3);
  v15 = v13;
  if ( v13 < 0 )
  {
    BackTraceCollection::Capture(v14, v13);
    v16 = 6849;
LABEL_12:
    Log_HREvent_7(v15, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", v16);
    (*(void (__fastcall **)(struct CallInfo *))(*(_QWORD *)v10 + 16LL))(v10);
    return v15;
  }
  v27[0] = *((_DWORD *)v10 + 767);
  v28 = 64;
  v27[1] = 0;
  memset_0(v29, 0, 0xF30u);
  if ( a4 <= 2 || (v18 = a4 - 3, (unsigned int)v18 < 2) )
  {
    v19 = 17;
  }
  else
  {
    Log_AssertionEvent_5(v18, v17, 155);
    MicrosoftTelemetryAssertTriggeredNoArgs();
    v19 = 0;
  }
  v30 = v19;
  v20 = CallInfo::UpdateCall(v10, (const struct CallUpdate *)v27, 0);
  v15 = v20;
  if ( v20 < 0 )
  {
    BackTraceCollection::Capture(v21, v20);
    v16 = 6856;
    goto LABEL_12;
  }
  if ( (unsigned int)dword_1800B3200 > 4 )
  {
    LODWORD(v25) = *a2;
    v26 = "PhoneController: Update callInfo callStateReason for reject incoming";
    v24 = a4;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (__int64)v21,
      (int)&unk_1800A7DD8,
      v22,
      v23,
      (const unsigned __int16 **)&v26,
      (__int64)&v25,
      (__int64)&v24);
  }
  (*(void (__fastcall **)(struct CallInfo *))(*(_QWORD *)v10 + 16LL))(v10);
  return 0;
}

```

## disassembly

```asm
0x18004a258  push    rbp
0x18004a25a  push    rbx
0x18004a25b  push    rsi
0x18004a25c  push    rdi
0x18004a25d  push    r14
0x18004a25f  lea     rbp, [rsp-0EB0h]
0x18004a267  sub     rsp, 0FB0h
0x18004a26e  mov     rax, cs:__security_cookie
0x18004a275  xor     rax, rsp
0x18004a278  mov     [rbp+0ED0h+var_30], rax
0x18004a27f  mov     esi, r9d
0x18004a282  mov     rdi, r8
0x18004a285  mov     r14, rdx
0x18004a288  mov     rbx, rcx
0x18004a28b  call    cs:__imp_GetCurrentThreadId
0x18004a291  cmp     [rbx+0F0h], eax
0x18004a297  jz      short loc_18004A2BE
0x18004a299  mov     r8d, 1ABAh
0x18004a29f  lea     rdx, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18004a2a6  call    Log_AssertionEvent_3
0x18004a2ab  call    cs:__imp_GetCurrentThreadId
0x18004a2b1  cmp     [rbx+0F0h], eax
0x18004a2b7  jz      short loc_18004A2BE
0x18004a2b9  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18004a2be  mov     rcx, [rbx+60h]
0x18004a2c2  lea     rdx, [rsp+0FD0h+var_F88]
0x18004a2c7  mov     r9, rdi
0x18004a2ca  mov     r8, r14
0x18004a2cd  call    ?FindCall@PhoneCallStorage@@QEAA?AV?$CComPtr@VCallInfo@@@ATL@@AEBIPEAUISecurityToken@@@Z; PhoneCallStorage::FindCall(uint const &,ISecurityToken *)
0x18004a2d2  mov     rbx, [rax]
0x18004a2d5  test    rbx, rbx
0x18004a2d8  jz      short loc_18004A2E9
0x18004a2da  mov     rax, [rbx]
0x18004a2dd  mov     rcx, rbx
0x18004a2e0  mov     rax, [rax+8]
0x18004a2e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a2e9  mov     rcx, [rsp+0FD0h+var_F88]
0x18004a2ee  test    rcx, rcx
0x18004a2f1  jz      short loc_18004A2FF
0x18004a2f3  mov     rax, [rcx]
0x18004a2f6  mov     rax, [rax+10h]
0x18004a2fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a2ff  test    rbx, rbx
0x18004a302  jnz     short loc_18004A32D
0x18004a304  mov     ebx, 80070490h
0x18004a309  mov     edx, ebx; int
0x18004a30b  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18004a310  mov     r9d, 1ABFh
0x18004a316  lea     r8, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18004a31d  xor     edx, edx
0x18004a31f  mov     ecx, ebx
0x18004a321  call    Log_HREvent_7
0x18004a326  mov     eax, ebx
0x18004a328  jmp     loc_18004A45D
0x18004a32d  mov     r8, rdi; struct ISecurityToken *
0x18004a330  mov     rdx, rbx; struct CallInfo *
0x18004a333  call    ?_CheckLineOwnershipForCall@PhoneController@@AEAAJPEAVCallInfo@@PEAUISecurityToken@@@Z; PhoneController::_CheckLineOwnershipForCall(CallInfo *,ISecurityToken *)
0x18004a338  mov     edi, eax
0x18004a33a  test    eax, eax
0x18004a33c  jns     short loc_18004A374
0x18004a33e  mov     edx, eax; int
0x18004a340  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18004a345  mov     r9d, 1AC1h
0x18004a34b  lea     r8, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18004a352  mov     edx, 1
0x18004a357  mov     ecx, edi
0x18004a359  call    Log_HREvent_7
0x18004a35e  mov     rcx, [rbx]
0x18004a361  mov     rax, [rcx+10h]
0x18004a365  mov     rcx, rbx
0x18004a368  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a36d  mov     eax, edi
0x18004a36f  jmp     loc_18004A45D
0x18004a374  mov     eax, [rbx+0BFCh]
0x18004a37a  lea     rcx, [rsp+0FD0h+var_F60]; void *
0x18004a37f  mov     [rsp+0FD0h+var_F70], eax
0x18004a383  xor     edx, edx; Val
0x18004a385  xor     eax, eax
0x18004a387  mov     [rsp+0FD0h+var_F68], 40h ; '@'
0x18004a390  mov     r8d, 0F30h; Size
0x18004a396  mov     [rsp+0FD0h+var_F6C], eax
0x18004a39a  call    memset_0
0x18004a39f  mov     ecx, esi
0x18004a3a1  test    esi, esi
0x18004a3a3  jz      short loc_18004A3CD
0x18004a3a5  sub     ecx, 1
0x18004a3a8  jz      short loc_18004A3CD
0x18004a3aa  sub     ecx, 1
0x18004a3ad  jz      short loc_18004A3CD
0x18004a3af  sub     ecx, 1
0x18004a3b2  jz      short loc_18004A3CD
0x18004a3b4  cmp     ecx, 1
0x18004a3b7  jz      short loc_18004A3CD
0x18004a3b9  mov     r8d, 9Bh
0x18004a3bf  call    Log_AssertionEvent_5
0x18004a3c4  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18004a3c9  xor     eax, eax
0x18004a3cb  jmp     short loc_18004A3D2
0x18004a3cd  mov     eax, 11h
0x18004a3d2  xor     r8d, r8d; int
0x18004a3d5  mov     [rbp+0ED0h+var_C74], eax
0x18004a3db  lea     rdx, [rsp+0FD0h+var_F70]; struct CallUpdate *
0x18004a3e0  mov     rcx, rbx; this
0x18004a3e3  call    ?UpdateCall@CallInfo@@QEAAJPEBUCallUpdate@@H@Z; CallInfo::UpdateCall(CallUpdate const *,int)
0x18004a3e8  mov     edi, eax
0x18004a3ea  test    eax, eax
0x18004a3ec  jns     short loc_18004A400
0x18004a3ee  mov     edx, eax; int
0x18004a3f0  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18004a3f5  mov     r9d, 1AC8h
0x18004a3fb  jmp     loc_18004A34B
0x18004a400  mov     eax, cs:dword_1800B3200
0x18004a406  cmp     eax, 4
0x18004a409  jbe     short loc_18004A44C
0x18004a40b  mov     eax, [r14]
0x18004a40e  lea     rdx, unk_1800A7DD8
0x18004a415  mov     dword ptr [rsp+0FD0h+var_F88], eax
0x18004a419  lea     rax, aPhonecontrolle_23; "PhoneController: Update callInfo callSt"...
0x18004a420  mov     [rsp+0FD0h+var_F80], rax
0x18004a425  lea     rax, [rsp+0FD0h+var_F90]
0x18004a42a  mov     [rsp+0FD0h+var_FA0], rax
0x18004a42f  lea     rax, [rsp+0FD0h+var_F88]
0x18004a434  mov     [rsp+0FD0h+var_FA8], rax
0x18004a439  lea     rax, [rsp+0FD0h+var_F80]
0x18004a43e  mov     [rsp+0FD0h+var_FB0], rax
0x18004a443  mov     [rsp+0FD0h+var_F90], esi
0x18004a447  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18004a44c  mov     rax, [rbx]
0x18004a44f  mov     rcx, rbx
0x18004a452  mov     rax, [rax+10h]
0x18004a456  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a45b  xor     eax, eax
0x18004a45d  mov     rcx, [rbp+0ED0h+var_30]
0x18004a464  xor     rcx, rsp; StackCookie
0x18004a467  call    __security_check_cookie
0x18004a46c  add     rsp, 0FB0h
0x18004a473  pop     r14
0x18004a475  pop     rdi
0x18004a476  pop     rsi
0x18004a477  pop     rbx
0x18004a478  pop     rbp
0x18004a479  retn
```
