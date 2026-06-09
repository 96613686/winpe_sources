# CallAudioRouting::_EnableVoipAudio(int)

- ea: `0x180064b20`
- end: `0x180064da6`
- name: `?_EnableVoipAudio@CallAudioRouting@@AEAAXH@Z`
- size: `646`
- prototype: `void __fastcall(CallAudioRouting *__hidden this, int)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800012b8`
- `0x180025ae4`
- `0x180031f6c`
- `0x18005f9b4`
- `0x18005f9c0`
- `0x180064b20`
- `0x18007f9ec`
- `0x18008d9b0`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180064d36`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180064d36`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180064d50`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180064d50`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180064d67`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180064d67`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180064d5e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180064d5e`

## string_xrefs

- `0x180064b95`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`
- `0x180064c0c`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`
- `0x180064d07`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`

## pseudocode

```c
void __fastcall CallAudioRouting::_EnableVoipAudio(CallAudioRouting *this, int a2, __int64 a3, __int64 a4)
{
  int v4; // edi
  bool v6; // zf
  __int64 v7; // rcx
  int v8; // eax
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 v11; // r9
  int v12; // eax
  int v13; // eax
  __int64 v14; // r9
  struct _TP_TIMER *v15; // rbx
  unsigned int v16[2]; // [rsp+30h] [rbp-50h] BYREF
  __int64 v17; // [rsp+38h] [rbp-48h] BYREF
  _QWORD pv[2]; // [rsp+40h] [rbp-40h] BYREF
  PTP_TIMER pti; // [rsp+50h] [rbp-30h]
  __int64 v20; // [rsp+58h] [rbp-28h]
  HLOCAL hMem; // [rsp+60h] [rbp-20h]
  __int64 v22; // [rsp+68h] [rbp-18h]

  v4 = *((_DWORD *)this + 68);
  if ( a2 )
  {
    *((_DWORD *)this + 68) = v4 + 1;
    if ( (unsigned int)dword_1800B3200 > 4 )
    {
      *(_QWORD *)v16 = "CallAudioRouting: VOIP audio count ref increased.";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (__int64)this,
        (int)&byte_1800A9897,
        a3,
        a4,
        (const unsigned __int16 **)v16);
    }
    goto LABEL_12;
  }
  if ( !v4 )
  {
    Log_AssertionEvent_9(this, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 3746);
    v6 = *((_DWORD *)this + 68) == 0;
    if ( *((_DWORD *)this + 68) )
      goto LABEL_8;
    MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  v6 = *((_DWORD *)this + 68) == 0;
LABEL_8:
  if ( !v6 )
  {
    if ( (unsigned int)dword_1800B3200 > 4 )
    {
      *(_QWORD *)v16 = "CallAudioRouting: VOIP audio count ref Decreased.";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (__int64)this,
        (int)byte_1800A986B,
        a3,
        a4,
        (const unsigned __int16 **)v16);
    }
    --*((_DWORD *)this + 68);
  }
LABEL_12:
  v7 = *((_QWORD *)this + 38);
  v17 = 0;
  v8 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v7 + 24LL))(v7, &v17);
  if ( v8 < 0 )
  {
    Log_HREvent_17(
      (unsigned int)v8,
      0,
      "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp",
      3765);
    goto LABEL_31;
  }
  v20 = 0;
  v22 = 0;
  pv[0] = &OperationWatchdog::`vftable';
  pv[1] = 0;
  pti = 0;
  hMem = 0;
  OperationWatchdog::Start(pv, 10, 0, 1000);
  v12 = *((_DWORD *)this + 68);
  if ( v12 )
  {
    if ( v12 != 1 || v4 )
      goto LABEL_27;
    if ( (unsigned int)dword_1800B3200 > 4 )
    {
      *(_QWORD *)v16 = "CallAudioRouting: VOIP unmuting audio.";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v9,
        (int)byte_1800A9819,
        v10,
        v11,
        (const unsigned __int16 **)v16);
    }
    v13 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v17 + 56LL))(v17, 0);
    if ( v13 >= 0 )
      goto LABEL_27;
    v14 = 3791;
  }
  else
  {
    if ( !v4 )
      goto LABEL_27;
    if ( (unsigned int)dword_1800B3200 > 4 )
    {
      *(_QWORD *)v16 = "CallAudioRouting: VOIP muting audio.";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v9,
        (int)byte_1800A9843,
        v10,
        v11,
        (const unsigned __int16 **)v16);
    }
    v13 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v17 + 56LL))(v17, 1);
    if ( v13 >= 0 )
      goto LABEL_27;
    v14 = 3781;
  }
  Log_HREvent_17((unsigned int)v13, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", v14);
LABEL_27:
  OperationWatchdog::End((OperationWatchdog *)pv);
  pv[0] = &OperationWatchdog::`vftable';
  OperationWatchdog::End((OperationWatchdog *)pv);
  if ( hMem )
    LocalFree(hMem);
  v15 = pti;
  if ( pti )
  {
    SetThreadpoolTimer(pti, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v15, 1);
    CloseThreadpoolTimer(v15);
  }
LABEL_31:
  if ( v17 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
}

```

## disassembly

```asm
0x180064b20  mov     [rsp-18h+arg_8], rbx
0x180064b25  mov     [rsp-18h+arg_10], rsi
0x180064b2a  push    rbp
0x180064b2b  push    rdi
0x180064b2c  push    r12
0x180064b2e  mov     rbp, rsp
0x180064b31  sub     rsp, 80h
0x180064b38  mov     rax, cs:__security_cookie
0x180064b3f  xor     rax, rsp
0x180064b42  mov     [rbp+var_10], rax
0x180064b46  mov     edi, [rcx+110h]
0x180064b4c  xor     esi, esi
0x180064b4e  mov     rbx, rcx
0x180064b51  test    edx, edx
0x180064b53  jz      short loc_180064B8B
0x180064b55  lea     eax, [rdi+1]
0x180064b58  mov     [rcx+110h], eax
0x180064b5e  mov     eax, cs:dword_1800B3200
0x180064b64  cmp     eax, 4
0x180064b67  jbe     short loc_180064BE7
0x180064b69  lea     rax, aCallaudiorouti_1; "CallAudioRouting: VOIP audio count ref "...
0x180064b70  mov     qword ptr [rbp+var_50], rax
0x180064b74  lea     rdx, byte_1800A9897
0x180064b7b  lea     rax, [rbp+var_50]
0x180064b7f  mov     qword ptr [rsp+80h+var_60], rax
0x180064b84  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180064b89  jmp     short loc_180064BE7
0x180064b8b  test    edi, edi
0x180064b8d  jnz     short loc_180064BAE
0x180064b8f  mov     r8d, 0EA2h
0x180064b95  lea     rdx, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180064b9c  call    Log_AssertionEvent_9
0x180064ba1  cmp     [rbx+110h], esi
0x180064ba7  jnz     short loc_180064BB4
0x180064ba9  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180064bae  cmp     [rbx+110h], esi
0x180064bb4  jbe     short loc_180064BE7
0x180064bb6  mov     eax, cs:dword_1800B3200
0x180064bbc  cmp     eax, 4
0x180064bbf  jbe     short loc_180064BE1
0x180064bc1  lea     rax, aCallaudiorouti_24; "CallAudioRouting: VOIP audio count ref "...
0x180064bc8  mov     qword ptr [rbp+var_50], rax
0x180064bcc  lea     rdx, byte_1800A986B
0x180064bd3  lea     rax, [rbp+var_50]
0x180064bd7  mov     qword ptr [rsp+80h+var_60], rax; unsigned int
0x180064bdc  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180064be1  dec     dword ptr [rbx+110h]
0x180064be7  mov     rcx, [rbx+130h]
0x180064bee  lea     rdx, [rbp+var_48]
0x180064bf2  mov     [rbp+var_48], rsi
0x180064bf6  mov     rax, [rcx]
0x180064bf9  mov     rax, [rax+18h]
0x180064bfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064c02  test    eax, eax
0x180064c04  jns     short loc_180064C21
0x180064c06  mov     r9d, 0EB5h
0x180064c0c  lea     r8, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180064c13  xor     edx, edx
0x180064c15  mov     ecx, eax
0x180064c17  call    Log_HREvent_17
0x180064c1c  jmp     loc_180064D6D
0x180064c21  xor     r8d, r8d; char *
0x180064c24  mov     [rbp+var_28], rsi
0x180064c28  mov     [rbp+var_18], rsi
0x180064c2c  lea     r12, ??_7OperationWatchdog@@6B@; const OperationWatchdog::`vftable'
0x180064c33  mov     [rbp+pv], r12
0x180064c37  lea     rcx, [rbp+pv]; pv
0x180064c3b  mov     [rbp+var_38], rsi
0x180064c3f  mov     r9d, 3E8h; unsigned int
0x180064c45  mov     [rbp+pti], rsi
0x180064c49  lea     edx, [r8+0Ah]; unsigned int
0x180064c4d  mov     [rbp+hMem], rsi
0x180064c51  mov     dword ptr [rbp+var_18+4], esi
0x180064c54  call    ?Start@OperationWatchdog@@QEAAXIPEBDKK@Z; OperationWatchdog::Start(uint,char const *,ulong,ulong)
0x180064c59  mov     eax, [rbx+110h]
0x180064c5f  test    eax, eax
0x180064c61  jnz     short loc_180064CB7
0x180064c63  test    edi, edi
0x180064c65  jz      loc_180064D17
0x180064c6b  mov     eax, cs:dword_1800B3200
0x180064c71  cmp     eax, 4
0x180064c74  jbe     short loc_180064C96
0x180064c76  lea     rax, aCallaudiorouti_16; "CallAudioRouting: VOIP muting audio."
0x180064c7d  mov     qword ptr [rbp+var_50], rax
0x180064c81  lea     rdx, byte_1800A9843
0x180064c88  lea     rax, [rbp+var_50]
0x180064c8c  mov     qword ptr [rsp+80h+var_60], rax
0x180064c91  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180064c96  mov     rcx, [rbp+var_48]
0x180064c9a  mov     edx, 1
0x180064c9f  mov     rax, [rcx]
0x180064ca2  mov     rax, [rax+38h]
0x180064ca6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064cab  test    eax, eax
0x180064cad  jns     short loc_180064D17
0x180064caf  mov     r9d, 0EC5h
0x180064cb5  jmp     short loc_180064D07
0x180064cb7  cmp     eax, 1
0x180064cba  jnz     short loc_180064D17
0x180064cbc  test    edi, edi
0x180064cbe  jnz     short loc_180064D17
0x180064cc0  mov     eax, cs:dword_1800B3200
0x180064cc6  cmp     eax, 4
0x180064cc9  jbe     short loc_180064CEB
0x180064ccb  lea     rax, aCallaudiorouti_3; "CallAudioRouting: VOIP unmuting audio."
0x180064cd2  mov     qword ptr [rbp+var_50], rax
0x180064cd6  lea     rdx, byte_1800A9819
0x180064cdd  lea     rax, [rbp+var_50]
0x180064ce1  mov     qword ptr [rsp+80h+var_60], rax
0x180064ce6  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180064ceb  mov     rcx, [rbp+var_48]
0x180064cef  xor     edx, edx
0x180064cf1  mov     rax, [rcx]
0x180064cf4  mov     rax, [rax+38h]
0x180064cf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064cfd  test    eax, eax
0x180064cff  jns     short loc_180064D17
0x180064d01  mov     r9d, 0ECFh
0x180064d07  lea     r8, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180064d0e  xor     edx, edx
0x180064d10  mov     ecx, eax
0x180064d12  call    Log_HREvent_17
0x180064d17  lea     rcx, [rbp+pv]; this
0x180064d1b  call    ?End@OperationWatchdog@@QEAAXXZ; OperationWatchdog::End(void)
0x180064d20  lea     rcx, [rbp+pv]; this
0x180064d24  mov     [rbp+pv], r12
0x180064d28  call    ?End@OperationWatchdog@@QEAAXXZ; OperationWatchdog::End(void)
0x180064d2d  mov     rcx, [rbp+hMem]; hMem
0x180064d31  test    rcx, rcx
0x180064d34  jz      short loc_180064D3C
0x180064d36  call    cs:__imp_LocalFree
0x180064d3c  mov     rbx, [rbp+pti]
0x180064d40  test    rbx, rbx
0x180064d43  jz      short loc_180064D6D
0x180064d45  xor     r9d, r9d; msWindowLength
0x180064d48  xor     r8d, r8d; msPeriod
0x180064d4b  xor     edx, edx; pftDueTime
0x180064d4d  mov     rcx, rbx; pti
0x180064d50  call    cs:__imp_SetThreadpoolTimer
0x180064d56  mov     edx, 1; fCancelPendingCallbacks
0x180064d5b  mov     rcx, rbx; pti
0x180064d5e  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180064d64  mov     rcx, rbx; pti
0x180064d67  call    cs:__imp_CloseThreadpoolTimer
0x180064d6d  mov     rcx, [rbp+var_48]
0x180064d71  test    rcx, rcx
0x180064d74  jz      short loc_180064D82
0x180064d76  mov     rax, [rcx]
0x180064d79  mov     rax, [rax+10h]
0x180064d7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064d82  mov     rcx, [rbp+var_10]
0x180064d86  xor     rcx, rsp; StackCookie
0x180064d89  call    __security_check_cookie
0x180064d8e  lea     r11, [rsp+80h+var_s0]
0x180064d96  mov     rbx, [r11+28h]
0x180064d9a  mov     rsi, [r11+30h]
0x180064d9e  mov     rsp, r11
0x180064da1  pop     r12
0x180064da3  pop     rdi
0x180064da4  pop     rbp
0x180064da5  retn
```
