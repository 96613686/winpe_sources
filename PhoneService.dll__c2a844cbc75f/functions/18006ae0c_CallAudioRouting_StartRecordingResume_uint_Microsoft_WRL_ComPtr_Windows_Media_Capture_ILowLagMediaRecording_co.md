# CallAudioRouting::_StartRecordingResume(uint,Microsoft::WRL::ComPtr<Windows::Media::Capture::ILowLagMediaRecording> const &)

- ea: `0x18006ae0c`
- end: `0x18006b0b1`
- name: `?_StartRecordingResume@CallAudioRouting@@AEAAJIAEBV?$ComPtr@UILowLagMediaRecording@Capture@Media@Windows@@@WRL@Microsoft@@@Z`
- size: `677`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18006b2c0`

## callees

- `0x180006e94`
- `0x180057c38`
- `0x18005f9b4`
- `0x18005f9c0`
- `0x18006ae0c`
- `0x18007f9ec`
- `0x18008d9b0`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006ae38`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006ae55`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006ae38`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006ae55`

## string_xrefs

- `0x18006ae49`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`
- `0x18006ae99`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`
- `0x18006af20`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`
- `0x18006affc`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`

## pseudocode

```c
__int64 __fastcall CallAudioRouting::_StartRecordingResume(
        __int64 a1,
        int a2,
        __int64 (__fastcall ****a3)(_QWORD, GUID *, __int64 *))
{
  __int64 v6; // rcx
  __int64 (__fastcall ***v7)(_QWORD, GUID *, __int64 *); // rcx
  int v8; // eax
  BackTraceCollection *v9; // rcx
  unsigned int v10; // ebx
  __int64 v11; // rcx
  __int64 v13; // rbx
  int v14; // eax
  BackTraceCollection *v15; // rcx
  unsigned int v16; // esi
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rdi
  int v20; // eax
  BackTraceCollection *v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // [rsp+30h] [rbp-40h] BYREF
  __int64 v25; // [rsp+38h] [rbp-38h] BYREF
  __int64 v26; // [rsp+40h] [rbp-30h]
  int v27; // [rsp+48h] [rbp-28h]
  __int64 v28; // [rsp+50h] [rbp-20h] BYREF
  __int64 v29; // [rsp+58h] [rbp-18h] BYREF

  if ( *(_DWORD *)(a1 + 104) == GetCurrentThreadId() )
  {
    Log_AssertionEvent_9(v6, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 2131);
    if ( *(_DWORD *)(a1 + 104) == GetCurrentThreadId() )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  v7 = *a3;
  v28 = 0;
  v8 = (**v7)(v7, &GUID_6369c758_5644_41e2_97af_8ef56a25e225, &v28);
  v10 = v8;
  if ( v8 < 0 )
  {
    BackTraceCollection::Capture(v9, v8);
    Log_HREvent_17(v10, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 2135);
    v11 = v28;
    if ( v28 )
    {
      v28 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    }
    return v10;
  }
  v13 = (a1 + 8) & -(__int64)(a1 != 0);
  if ( v13 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 8LL))((a1 + 8) & -(__int64)(a1 != 0));
  v29 = 0;
  v14 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v28 + 56LL))(v28, &v29);
  v16 = v14;
  if ( v14 < 0 )
  {
    BackTraceCollection::Capture(v15, v14);
    Log_HREvent_17(v16, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 2141);
LABEL_12:
    v17 = v29;
    if ( v29 )
    {
      v29 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    }
    if ( v13 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    v18 = v28;
    if ( v28 )
    {
      v28 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    }
    return v16;
  }
  v24 = 0;
  v25 = a1;
  v26 = (a1 + 8) & -(__int64)(a1 != 0);
  if ( v13 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 8LL))((a1 + 8) & -(__int64)(a1 != 0));
  v27 = a2;
  Microsoft::WRL::Callback_Windows::Foundation::IAsyncActionCompletedHandler__lambda_33b1f803884a11aaace195dbc51202a2___(
    &v24,
    &v25);
  if ( v26 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
  v19 = v24;
  v20 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v29 + 48LL))(v29, v24);
  v16 = v20;
  if ( v20 < 0 )
  {
    BackTraceCollection::Capture(v21, v20);
    Log_HREvent_17(v16, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 2158);
    if ( v19 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    goto LABEL_12;
  }
  if ( v19 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  v22 = v29;
  if ( v29 )
  {
    v29 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  }
  if ( v13 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  v23 = v28;
  if ( v28 )
  {
    v28 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
  }
  return 0;
}

```

## disassembly

```asm
0x18006ae0c  mov     [rsp-18h+arg_0], rbx
0x18006ae11  mov     [rsp-18h+arg_8], rsi
0x18006ae16  push    rbp
0x18006ae17  push    rdi
0x18006ae18  push    r14
0x18006ae1a  mov     rbp, rsp
0x18006ae1d  sub     rsp, 70h
0x18006ae21  mov     rax, cs:__security_cookie
0x18006ae28  xor     rax, rsp
0x18006ae2b  mov     [rbp+var_10], rax
0x18006ae2f  mov     rbx, r8
0x18006ae32  mov     r14d, edx
0x18006ae35  mov     rdi, rcx
0x18006ae38  call    cs:__imp_GetCurrentThreadId
0x18006ae3e  cmp     [rdi+68h], eax
0x18006ae41  jnz     short loc_18006AE65
0x18006ae43  mov     r8d, 853h
0x18006ae49  lea     rdx, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18006ae50  call    Log_AssertionEvent_9
0x18006ae55  call    cs:__imp_GetCurrentThreadId
0x18006ae5b  cmp     [rdi+68h], eax
0x18006ae5e  jnz     short loc_18006AE65
0x18006ae60  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18006ae65  mov     rcx, [rbx]
0x18006ae68  lea     r8, [rbp+var_20]
0x18006ae6c  mov     [rbp+var_20], 0
0x18006ae74  lea     rdx, _GUID_6369c758_5644_41e2_97af_8ef56a25e225
0x18006ae7b  mov     rax, [rcx]
0x18006ae7e  mov     rax, [rax]
0x18006ae81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ae86  mov     ebx, eax
0x18006ae88  test    eax, eax
0x18006ae8a  jns     short loc_18006AED0
0x18006ae8c  mov     edx, eax; int
0x18006ae8e  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18006ae93  mov     r9d, 857h
0x18006ae99  lea     r8, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18006aea0  mov     edx, 1
0x18006aea5  mov     ecx, ebx
0x18006aea7  call    Log_HREvent_17
0x18006aeac  mov     rcx, [rbp+var_20]
0x18006aeb0  test    rcx, rcx
0x18006aeb3  jz      short loc_18006AEC9
0x18006aeb5  mov     [rbp+var_20], 0
0x18006aebd  mov     rax, [rcx]
0x18006aec0  mov     rax, [rax+10h]
0x18006aec4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006aec9  mov     eax, ebx
0x18006aecb  jmp     loc_18006B090
0x18006aed0  mov     rax, rdi
0x18006aed3  lea     rcx, [rdi+8]
0x18006aed7  neg     rax
0x18006aeda  sbb     rbx, rbx
0x18006aedd  and     rbx, rcx
0x18006aee0  jz      short loc_18006AEF1
0x18006aee2  mov     rax, [rbx]
0x18006aee5  mov     rcx, rbx
0x18006aee8  mov     rax, [rax+8]
0x18006aeec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006aef1  mov     rcx, [rbp+var_20]
0x18006aef5  lea     rdx, [rbp+var_18]
0x18006aef9  mov     [rbp+var_18], 0
0x18006af01  mov     rax, [rcx]
0x18006af04  mov     rax, [rax+38h]
0x18006af08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006af0d  mov     esi, eax
0x18006af0f  test    eax, eax
0x18006af11  jns     short loc_18006AF88
0x18006af13  mov     edx, eax; int
0x18006af15  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18006af1a  mov     r9d, 85Dh
0x18006af20  lea     r8, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18006af27  mov     edx, 1
0x18006af2c  mov     ecx, esi
0x18006af2e  call    Log_HREvent_17
0x18006af33  mov     rcx, [rbp+var_18]
0x18006af37  test    rcx, rcx
0x18006af3a  jz      short loc_18006AF50
0x18006af3c  mov     [rbp+var_18], 0
0x18006af44  mov     rax, [rcx]
0x18006af47  mov     rax, [rax+10h]
0x18006af4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006af50  test    rbx, rbx
0x18006af53  jz      short loc_18006AF64
0x18006af55  mov     rax, [rbx]
0x18006af58  mov     rcx, rbx
0x18006af5b  mov     rax, [rax+10h]
0x18006af5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006af64  mov     rcx, [rbp+var_20]
0x18006af68  test    rcx, rcx
0x18006af6b  jz      short loc_18006AF81
0x18006af6d  mov     [rbp+var_20], 0
0x18006af75  mov     rax, [rcx]
0x18006af78  mov     rax, [rax+10h]
0x18006af7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006af81  mov     eax, esi
0x18006af83  jmp     loc_18006B090
0x18006af88  mov     [rbp+var_40], 0
0x18006af90  mov     [rbp+var_38], rdi
0x18006af94  mov     [rbp+var_30], rbx
0x18006af98  test    rbx, rbx
0x18006af9b  jz      short loc_18006AFAC
0x18006af9d  mov     rax, [rbx]
0x18006afa0  mov     rcx, rbx
0x18006afa3  mov     rax, [rax+8]
0x18006afa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006afac  lea     rdx, [rbp+var_38]
0x18006afb0  mov     [rbp+var_28], r14d
0x18006afb4  lea     rcx, [rbp+var_40]
0x18006afb8  call    Microsoft__WRL__Callback_Windows__Foundation__IAsyncActionCompletedHandler__lambda_33b1f803884a11aaace195dbc51202a2___
0x18006afbd  mov     rcx, [rbp+var_30]
0x18006afc1  test    rcx, rcx
0x18006afc4  jz      short loc_18006AFD2
0x18006afc6  mov     rax, [rcx]
0x18006afc9  mov     rax, [rax+10h]
0x18006afcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006afd2  mov     rcx, [rbp+var_18]
0x18006afd6  mov     rdi, [rbp+var_40]
0x18006afda  mov     rdx, rdi
0x18006afdd  mov     rax, [rcx]
0x18006afe0  mov     rax, [rax+30h]
0x18006afe4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006afe9  mov     esi, eax
0x18006afeb  test    eax, eax
0x18006afed  jns     short loc_18006B02C
0x18006afef  mov     edx, eax; int
0x18006aff1  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18006aff6  mov     r9d, 86Eh
0x18006affc  lea     r8, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18006b003  mov     edx, 1
0x18006b008  mov     ecx, esi
0x18006b00a  call    Log_HREvent_17
0x18006b00f  test    rdi, rdi
0x18006b012  jz      loc_18006AF33
0x18006b018  mov     rax, [rdi]
0x18006b01b  mov     rcx, rdi
0x18006b01e  mov     rax, [rax+10h]
0x18006b022  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b027  jmp     loc_18006AF33
0x18006b02c  test    rdi, rdi
0x18006b02f  jz      short loc_18006B040
0x18006b031  mov     rax, [rdi]
0x18006b034  mov     rcx, rdi
0x18006b037  mov     rax, [rax+10h]
0x18006b03b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b040  mov     rcx, [rbp+var_18]
0x18006b044  test    rcx, rcx
0x18006b047  jz      short loc_18006B05D
0x18006b049  mov     [rbp+var_18], 0
0x18006b051  mov     rax, [rcx]
0x18006b054  mov     rax, [rax+10h]
0x18006b058  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b05d  test    rbx, rbx
0x18006b060  jz      short loc_18006B071
0x18006b062  mov     rax, [rbx]
0x18006b065  mov     rcx, rbx
0x18006b068  mov     rax, [rax+10h]
0x18006b06c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b071  mov     rcx, [rbp+var_20]
0x18006b075  test    rcx, rcx
0x18006b078  jz      short loc_18006B08E
0x18006b07a  mov     [rbp+var_20], 0
0x18006b082  mov     rax, [rcx]
0x18006b085  mov     rax, [rax+10h]
0x18006b089  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b08e  xor     eax, eax
0x18006b090  mov     rcx, [rbp+var_10]
0x18006b094  xor     rcx, rsp; StackCookie
0x18006b097  call    __security_check_cookie
0x18006b09c  lea     r11, [rsp+70h+var_s0]
0x18006b0a1  mov     rbx, [r11+20h]
0x18006b0a5  mov     rsi, [r11+28h]
0x18006b0a9  mov     rsp, r11
0x18006b0ac  pop     r14
0x18006b0ae  pop     rdi
0x18006b0af  pop     rbp
0x18006b0b0  retn
```
