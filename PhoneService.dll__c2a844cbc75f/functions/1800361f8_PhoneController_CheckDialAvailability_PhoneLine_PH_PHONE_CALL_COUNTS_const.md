# PhoneController::_CheckDialAvailability(PhoneLine *,PH_PHONE_CALL_COUNTS const &)

- ea: `0x1800361f8`
- end: `0x180036498`
- name: `?_CheckDialAvailability@PhoneController@@AEAAJPEAVPhoneLine@@AEBUPH_PHONE_CALL_COUNTS@@@Z`
- size: `672`
- prototype: `__int64 __fastcall(PhoneController *__hidden this, struct PhoneLine *, const struct PH_PHONE_CALL_COUNTS *)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x180037804`

## callees

- `0x180004660`
- `0x180006e94`
- `0x18002c574`
- `0x18002c580`
- `0x1800361f8`
- `0x18003c7d8`
- `0x180047c90`
- `0x18007f9ec`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180036210`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180036230`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180036210`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180036230`

## string_xrefs

- `0x180036224`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x180036291`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x180036476`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x180036324`: `PhoneController: Dialing: Failed because the line attempt to dial is not free.`
- `0x180036433`: `PhoneController: Dialing: Failed because there are already two calls.`

## pseudocode

```c
__int64 __fastcall PhoneController::_CheckDialAvailability(
        PhoneController *this,
        struct PhoneLine *a2,
        const struct PH_PHONE_CALL_COUNTS *a3)
{
  __int64 v6; // rcx
  __int128 v7; // xmm0
  __int128 v8; // xmm1
  __int128 v9; // xmm0
  __int128 v10; // xmm1
  int GlobalDialAvailability; // eax
  BackTraceCollection *v12; // rcx
  __int64 v13; // r8
  __int64 v14; // r9
  unsigned int v15; // edi
  __int64 v17; // rcx
  const char *v18; // rax
  char *v19; // rdx
  __int128 v20; // [rsp+30h] [rbp-40h] BYREF
  _OWORD v21[3]; // [rsp+40h] [rbp-30h] BYREF
  const char *v22; // [rsp+90h] [rbp+20h] BYREF
  __int64 v23; // [rsp+98h] [rbp+28h] BYREF

  if ( *((_DWORD *)this + 60) != GetCurrentThreadId() )
  {
    Log_AssertionEvent_3(v6, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 5453);
    if ( *((_DWORD *)this + 60) != GetCurrentThreadId() )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  v7 = *(_OWORD *)((char *)a2 + 88);
  v8 = *(_OWORD *)a3;
  LODWORD(v22) = 0;
  v20 = v7;
  v9 = *((_OWORD *)a3 + 1);
  v21[0] = v8;
  v10 = *((_OWORD *)a3 + 2);
  v21[1] = v9;
  v21[2] = v10;
  GlobalDialAvailability = PhoneController::_GetGlobalDialAvailability(this, &v20, v21, &v22);
  v15 = GlobalDialAvailability;
  if ( GlobalDialAvailability < 0 )
  {
    BackTraceCollection::Capture(v12, GlobalDialAvailability);
    Log_HREvent_7(v15, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 5456);
    return v15;
  }
  if ( (_DWORD)v22 == 1 )
  {
    PhoneController::_SendDeferredErrorNotification(this, a2, 20, 20);
    if ( (unsigned int)dword_1800B3200 <= 2 )
      goto LABEL_28;
    v17 = 0x200000000000LL;
    if ( (qword_1800B3210 & 0x200000000000LL) == 0 || (qword_1800B3218 & 0x200000000000LL) != qword_1800B3218 )
      goto LABEL_28;
    v18 = "PhoneController: Dialing: Failed because there are already two calls.";
    v19 = byte_1800A8073;
    goto LABEL_27;
  }
  v17 = (unsigned int)((_DWORD)v22 - 2);
  if ( (_DWORD)v22 == 2 )
  {
    if ( (unsigned int)dword_1800B3200 <= 2 )
      goto LABEL_28;
    v17 = 0x200000000000LL;
    if ( (qword_1800B3210 & 0x200000000000LL) == 0 || (qword_1800B3218 & 0x200000000000LL) != qword_1800B3218 )
      goto LABEL_28;
    v18 = "PhoneController: Dialing: Failed due to existing outgoing call";
    v19 = (char *)&word_1800A8166;
    goto LABEL_27;
  }
  if ( (_DWORD)v22 == 3 )
  {
    PhoneController::_SendDeferredErrorNotification(this, a2, 20, 20);
    if ( (unsigned int)dword_1800B3200 <= 2 )
      goto LABEL_28;
    v17 = 0x200000000000LL;
    if ( (qword_1800B3210 & 0x200000000000LL) == 0 || (qword_1800B3218 & 0x200000000000LL) != qword_1800B3218 )
      goto LABEL_28;
    v18 = "PhoneController: Dialing: Failed because the active call cannot be held.";
    v19 = (char *)&dword_1800A80C4;
    goto LABEL_27;
  }
  if ( (_DWORD)v22 != 4 )
    return 0;
  PhoneController::_SendDeferredErrorNotification(this, a2, 20, 20);
  if ( (unsigned int)dword_1800B3200 > 2 )
  {
    v17 = 0x200000000000LL;
    if ( (qword_1800B3210 & 0x200000000000LL) != 0 && (qword_1800B3218 & 0x200000000000LL) == qword_1800B3218 )
    {
      v18 = "PhoneController: Dialing: Failed because the line attempt to dial is not free.";
      v19 = byte_1800A811D;
LABEL_27:
      v22 = v18;
      v23 = 2048;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>>(
        0x200000000000LL,
        (int)v19,
        v13,
        v14,
        (__int64)&v23,
        (const unsigned __int16 **)&v22);
    }
  }
LABEL_28:
  BackTraceCollection::Capture((BackTraceCollection *)v17, -2147020579);
  Log_HREvent_7(2147946717LL, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 5512);
  return 2147946717LL;
}

```

## disassembly

```asm
0x1800361f8  mov     [rsp-18h+arg_10], rbx
0x1800361fd  push    rbp
0x1800361fe  push    rsi
0x1800361ff  push    rdi
0x180036200  mov     rbp, rsp
0x180036203  sub     rsp, 70h
0x180036207  mov     rdi, r8
0x18003620a  mov     rsi, rdx
0x18003620d  mov     rbx, rcx
0x180036210  call    cs:__imp_GetCurrentThreadId
0x180036216  cmp     [rbx+0F0h], eax
0x18003621c  jz      short loc_180036243
0x18003621e  mov     r8d, 154Dh
0x180036224  lea     rdx, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18003622b  call    Log_AssertionEvent_3
0x180036230  call    cs:__imp_GetCurrentThreadId
0x180036236  cmp     [rbx+0F0h], eax
0x18003623c  jz      short loc_180036243
0x18003623e  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180036243  movups  xmm0, xmmword ptr [rsi+58h]
0x180036247  lea     r9, [rbp+arg_0]
0x18003624b  mov     rcx, rbx
0x18003624e  movups  xmm1, xmmword ptr [rdi]
0x180036251  lea     r8, [rbp+var_30]
0x180036255  mov     dword ptr [rbp+arg_0], 0
0x18003625c  movdqu  [rbp+var_40], xmm0
0x180036261  lea     rdx, [rbp+var_40]
0x180036265  movups  xmm0, xmmword ptr [rdi+10h]
0x180036269  movaps  [rbp+var_30], xmm1
0x18003626d  movups  xmm1, xmmword ptr [rdi+20h]
0x180036271  movaps  [rbp+var_20], xmm0
0x180036275  movaps  [rbp+var_10], xmm1
0x180036279  call    ?_GetGlobalDialAvailability@PhoneController@@AEAAJAEBU_GUID@@UPH_PHONE_CALL_COUNTS@@PEAW4DialAvailability@@@Z; PhoneController::_GetGlobalDialAvailability(_GUID const &,PH_PHONE_CALL_COUNTS,DialAvailability *)
0x18003627e  mov     edi, eax
0x180036280  test    eax, eax
0x180036282  jns     short loc_1800362AB
0x180036284  mov     edx, eax; int
0x180036286  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18003628b  mov     r9d, 1550h
0x180036291  lea     r8, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180036298  mov     edx, 1
0x18003629d  mov     ecx, edi
0x18003629f  call    Log_HREvent_7
0x1800362a4  mov     eax, edi
0x1800362a6  jmp     loc_180036488
0x1800362ab  mov     ecx, dword ptr [rbp+arg_0]
0x1800362ae  sub     ecx, 1
0x1800362b1  jz      loc_1800363EC
0x1800362b7  sub     ecx, 1
0x1800362ba  jz      loc_18003639D
0x1800362c0  sub     ecx, 1
0x1800362c3  jz      short loc_180036337
0x1800362c5  cmp     ecx, 1
0x1800362c8  jz      short loc_1800362D1
0x1800362ca  xor     eax, eax
0x1800362cc  jmp     loc_180036488
0x1800362d1  mov     r8d, 14h
0x1800362d7  mov     rdx, rsi
0x1800362da  mov     r9d, r8d
0x1800362dd  mov     rcx, rbx
0x1800362e0  call    ?_SendDeferredErrorNotification@PhoneController@@IEAAXPEBVPhoneLine@@W4PH_ERROR@@J@Z; PhoneController::_SendDeferredErrorNotification(PhoneLine const *,PH_ERROR,long)
0x1800362e5  mov     eax, cs:dword_1800B3200
0x1800362eb  cmp     eax, 2
0x1800362ee  jbe     loc_180036464
0x1800362f4  mov     rdx, cs:qword_1800B3218
0x1800362fb  mov     rcx, 200000000000h
0x180036305  mov     rax, cs:qword_1800B3210
0x18003630c  test    rcx, rax
0x18003630f  jz      loc_180036464
0x180036315  mov     rax, rdx
0x180036318  and     rax, rcx
0x18003631b  cmp     rax, rdx
0x18003631e  jnz     loc_180036464
0x180036324  lea     rax, aPhonecontrolle_50; "PhoneController: Dialing: Failed becaus"...
0x18003632b  lea     rdx, byte_1800A811D
0x180036332  jmp     loc_180036441
0x180036337  mov     r8d, 14h
0x18003633d  mov     rdx, rsi
0x180036340  mov     r9d, r8d
0x180036343  mov     rcx, rbx
0x180036346  call    ?_SendDeferredErrorNotification@PhoneController@@IEAAXPEBVPhoneLine@@W4PH_ERROR@@J@Z; PhoneController::_SendDeferredErrorNotification(PhoneLine const *,PH_ERROR,long)
0x18003634b  mov     eax, cs:dword_1800B3200
0x180036351  cmp     eax, 2
0x180036354  jbe     loc_180036464
0x18003635a  mov     rdx, cs:qword_1800B3218
0x180036361  mov     rcx, 200000000000h
0x18003636b  mov     rax, cs:qword_1800B3210
0x180036372  test    rcx, rax
0x180036375  jz      loc_180036464
0x18003637b  mov     rax, rdx
0x18003637e  and     rax, rcx
0x180036381  cmp     rax, rdx
0x180036384  jnz     loc_180036464
0x18003638a  lea     rax, aPhonecontrolle_66; "PhoneController: Dialing: Failed becaus"...
0x180036391  lea     rdx, dword_1800A80C4
0x180036398  jmp     loc_180036441
0x18003639d  mov     eax, cs:dword_1800B3200
0x1800363a3  cmp     eax, 2
0x1800363a6  jbe     loc_180036464
0x1800363ac  mov     rdx, cs:qword_1800B3218
0x1800363b3  mov     rcx, 200000000000h
0x1800363bd  mov     rax, cs:qword_1800B3210
0x1800363c4  test    rcx, rax
0x1800363c7  jz      loc_180036464
0x1800363cd  mov     rax, rdx
0x1800363d0  and     rax, rcx
0x1800363d3  cmp     rax, rdx
0x1800363d6  jnz     loc_180036464
0x1800363dc  lea     rax, aPhonecontrolle_87; "PhoneController: Dialing: Failed due to"...
0x1800363e3  lea     rdx, word_1800A8166
0x1800363ea  jmp     short loc_180036441
0x1800363ec  mov     r8d, 14h
0x1800363f2  mov     rdx, rsi
0x1800363f5  mov     r9d, r8d
0x1800363f8  mov     rcx, rbx
0x1800363fb  call    ?_SendDeferredErrorNotification@PhoneController@@IEAAXPEBVPhoneLine@@W4PH_ERROR@@J@Z; PhoneController::_SendDeferredErrorNotification(PhoneLine const *,PH_ERROR,long)
0x180036400  mov     eax, cs:dword_1800B3200
0x180036406  cmp     eax, 2
0x180036409  jbe     short loc_180036464
0x18003640b  mov     rdx, cs:qword_1800B3218
0x180036412  mov     rcx, 200000000000h
0x18003641c  mov     rax, cs:qword_1800B3210
0x180036423  test    rcx, rax
0x180036426  jz      short loc_180036464
0x180036428  mov     rax, rdx
0x18003642b  and     rax, rcx
0x18003642e  cmp     rax, rdx
0x180036431  jnz     short loc_180036464
0x180036433  lea     rax, aPhonecontrolle_115; "PhoneController: Dialing: Failed becaus"...
0x18003643a  lea     rdx, byte_1800A8073
0x180036441  mov     [rbp+arg_0], rax
0x180036445  lea     rax, [rbp+arg_0]
0x180036449  mov     [rsp+70h+var_48], rax
0x18003644e  lea     rax, [rbp+arg_8]
0x180036452  mov     [rsp+70h+var_50], rax
0x180036457  mov     [rbp+arg_8], 800h
0x18003645f  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &)
0x180036464  mov     ebx, 800710DDh
0x180036469  mov     edx, ebx; int
0x18003646b  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180036470  mov     r9d, 1588h
0x180036476  lea     r8, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18003647d  xor     edx, edx
0x18003647f  mov     ecx, ebx
0x180036481  call    Log_HREvent_7
0x180036486  mov     eax, ebx
0x180036488  mov     rbx, [rsp+70h+arg_10]
0x180036490  add     rsp, 70h
0x180036494  pop     rdi
0x180036495  pop     rsi
0x180036496  pop     rbp
0x180036497  retn
```
