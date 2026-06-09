# CallAudioRouting::_EnableCellularProviderChange(uint,CellularAudioType,AudioProviderChangeOperation)

- ea: `0x180064710`
- end: `0x180064a15`
- name: `?_EnableCellularProviderChange@CallAudioRouting@@AEAAXIW4CellularAudioType@@W4AudioProviderChangeOperation@@@Z`
- size: `773`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800011fc`
- `0x180006e94`
- `0x18005f9b4`
- `0x18005f9c0`
- `0x180062b88`
- `0x180064710`
- `0x180064dac`
- `0x18007f9ec`
- `0x18008d9b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800647b0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800648bd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800647b0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800648bd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800647f3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006482f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180064905`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006493a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800647f3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006482f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180064905`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006493a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180064746`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006476b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180064746`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006476b`

## string_xrefs

- `0x180064750`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`
- `0x1800648aa`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`
- `0x1800648f2`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`
- `0x180064911`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`
- `0x1800649a4`: `CallAudioRouting: Invalid cellular provider change attempted`

## pseudocode

```c
void __fastcall CallAudioRouting::_EnableCellularProviderChange(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4)
{
  __int64 v8; // rcx
  BackTraceCollection *v9; // rcx
  __int64 v10; // r9
  __int64 v11; // rcx
  int v12; // r12d
  int v13; // r14d
  int v14; // eax
  BackTraceCollection *v15; // rcx
  struct CallAudioRouting::CellularAudioState *v16; // rcx
  unsigned int v17; // [rsp+30h] [rbp-A9h] BYREF
  BOOL v18; // [rsp+34h] [rbp-A5h] BYREF
  struct CallAudioRouting::CellularAudioState *v19; // [rsp+38h] [rbp-A1h] BYREF
  int v20; // [rsp+40h] [rbp-99h] BYREF
  unsigned int v21; // [rsp+44h] [rbp-95h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v22; // [rsp+60h] [rbp-79h] BYREF
  const char *v23; // [rsp+80h] [rbp-59h]
  __int64 v24; // [rsp+88h] [rbp-51h]
  unsigned int *v25; // [rsp+90h] [rbp-49h]
  __int64 v26; // [rsp+98h] [rbp-41h]
  struct CallAudioRouting::CellularAudioState **v27; // [rsp+A0h] [rbp-39h]
  __int64 v28; // [rsp+A8h] [rbp-31h]
  int *v29; // [rsp+B0h] [rbp-29h]
  __int64 v30; // [rsp+B8h] [rbp-21h]
  int *v31; // [rsp+C0h] [rbp-19h]
  __int64 v32; // [rsp+C8h] [rbp-11h]
  BOOL *v33; // [rsp+D0h] [rbp-9h]
  __int64 v34; // [rsp+D8h] [rbp-1h]

  v17 = a2;
  if ( *(_DWORD *)(a1 + 104) == GetCurrentThreadId() )
  {
    Log_AssertionEvent_9(v8, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 3056);
    if ( *(_DWORD *)(a1 + 104) == GetCurrentThreadId() )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  if ( ((a3 - 1) & a3) != 0 )
  {
    Log_AssertionEvent_9(v8, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 3058);
    MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  if ( !a3 )
  {
    Log_AssertionEvent_9(v8, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 3059);
    MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 88));
  v19 = 0;
  if ( !(unsigned int)CallAudioRouting::_FindCellularState((CallAudioRouting *)a1, a2, &v19) )
  {
    BackTraceCollection::Capture(v9, -2147023728);
    Log_HREvent_17(2147943568LL, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 3818);
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 88));
    v10 = 3071;
LABEL_10:
    v11 = 2147943568LL;
LABEL_11:
    Log_HREvent_17(v11, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", v10);
    return;
  }
  v12 = *((_DWORD *)v19 + 2);
  v13 = *((_DWORD *)v19 + 1);
  v18 = v12 != 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 88));
  if ( a4 != 1 )
    goto LABEL_17;
  if ( v12 )
    goto LABEL_32;
  if ( v13 == a3 )
  {
LABEL_17:
    if ( a4 )
      goto LABEL_20;
    if ( !v12 )
      goto LABEL_32;
    if ( v13 != a3 )
    {
LABEL_20:
      if ( a4 != 2 || !v12 || v13 == a3 )
        goto LABEL_32;
    }
  }
  if ( !v13 || !a3 )
  {
LABEL_32:
    if ( (unsigned int)dword_1800B3200 > 4 )
    {
      v20 = v13;
      v33 = &v18;
      v31 = &v20;
      v29 = (int *)&v21;
      v27 = &v19;
      v25 = &v17;
      v23 = "CallAudioRouting: Invalid cellular provider change attempted";
      v34 = 4;
      v32 = 4;
      v30 = 4;
      v28 = 4;
      v26 = 4;
      v21 = a4;
      LODWORD(v19) = a3;
      v24 = 61;
      tlgWriteTransfer_EventWriteTransfer((int)&dword_1800B3200, (int)&byte_1800A9C91, 0, 0, 8u, &v22);
    }
    return;
  }
  v14 = CallAudioRouting::_CallAudioRoutingManagerToEnableProviderChange(a1, v17, a3, a4);
  if ( v14 < 0 )
  {
    v10 = 3112;
    v11 = (unsigned int)v14;
    goto LABEL_11;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 88));
  v19 = 0;
  if ( !(unsigned int)CallAudioRouting::_FindCellularState((CallAudioRouting *)a1, v17, &v19) )
  {
    BackTraceCollection::Capture(v15, -2147023728);
    Log_HREvent_17(2147943568LL, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 3818);
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 88));
    v10 = 3130;
    goto LABEL_10;
  }
  v16 = v19;
  if ( a4 != 1 )
  {
    if ( !a4 )
      *((_DWORD *)v19 + 1) = *((_DWORD *)v19 + 2);
    a3 = 0;
  }
  *((_DWORD *)v16 + 2) = a3;
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 88));
}

```

## disassembly

```asm
0x180064710  push    rbp
0x180064712  push    rbx
0x180064713  push    rsi
0x180064714  push    rdi
0x180064715  push    r12
0x180064717  push    r13
0x180064719  push    r14
0x18006471b  push    r15
0x18006471d  lea     rbp, [rsp-1Fh]
0x180064722  sub     rsp, 0F8h
0x180064729  mov     rax, cs:__security_cookie
0x180064730  xor     rax, rsp
0x180064733  mov     [rbp+57h+var_50], rax
0x180064737  mov     edi, r9d
0x18006473a  mov     [rsp+130h+var_100], edx
0x18006473e  mov     ebx, r8d
0x180064741  mov     esi, edx
0x180064743  mov     r13, rcx
0x180064746  call    cs:__imp_GetCurrentThreadId
0x18006474c  lea     r15, [r13+58h]
0x180064750  lea     r14, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180064757  cmp     [r15+10h], eax
0x18006475b  jnz     short loc_18006477C
0x18006475d  mov     r8d, 0BF0h
0x180064763  mov     rdx, r14
0x180064766  call    Log_AssertionEvent_9
0x18006476b  call    cs:__imp_GetCurrentThreadId
0x180064771  cmp     [r13+68h], eax
0x180064775  jnz     short loc_18006477C
0x180064777  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18006477c  lea     eax, [rbx-1]
0x18006477f  test    ebx, eax
0x180064781  jz      short loc_180064796
0x180064783  mov     r8d, 0BF2h
0x180064789  mov     rdx, r14
0x18006478c  call    Log_AssertionEvent_9
0x180064791  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180064796  test    ebx, ebx
0x180064798  jnz     short loc_1800647AD
0x18006479a  mov     r8d, 0BF3h
0x1800647a0  mov     rdx, r14
0x1800647a3  call    Log_AssertionEvent_9
0x1800647a8  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800647ad  mov     rcx, r15; lpCriticalSection
0x1800647b0  call    cs:__imp_EnterCriticalSection
0x1800647b6  lea     r8, [rsp+130h+var_F8]; struct CallAudioRouting::CellularAudioState **
0x1800647bb  mov     [rsp+130h+var_F8], 0
0x1800647c4  mov     edx, esi; unsigned int
0x1800647c6  mov     rcx, r13; this
0x1800647c9  call    ?_FindCellularState@CallAudioRouting@@AEAAHIPEAPEAUCellularAudioState@1@@Z; CallAudioRouting::_FindCellularState(uint,CallAudioRouting::CellularAudioState * *)
0x1800647ce  test    eax, eax
0x1800647d0  jnz     short loc_180064813
0x1800647d2  mov     ebx, 80070490h
0x1800647d7  mov     edx, ebx; int
0x1800647d9  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x1800647de  mov     r9d, 0EEAh
0x1800647e4  mov     r8, r14
0x1800647e7  xor     edx, edx
0x1800647e9  mov     ecx, ebx
0x1800647eb  call    Log_HREvent_17
0x1800647f0  mov     rcx, r15; lpCriticalSection
0x1800647f3  call    cs:__imp_LeaveCriticalSection
0x1800647f9  mov     r9d, 0BFFh
0x1800647ff  mov     r8, r14
0x180064802  mov     edx, 1
0x180064807  mov     ecx, ebx
0x180064809  call    Log_HREvent_17
0x18006480e  jmp     loc_1800649F5
0x180064813  mov     rax, [rsp+130h+var_F8]
0x180064818  xor     ecx, ecx
0x18006481a  mov     r12d, [rax+8]
0x18006481e  test    r12d, r12d
0x180064821  mov     r14d, [rax+4]
0x180064825  setnz   cl
0x180064828  mov     [rsp+130h+var_FC], ecx
0x18006482c  mov     rcx, r15; lpCriticalSection
0x18006482f  call    cs:__imp_LeaveCriticalSection
0x180064835  mov     esi, 1
0x18006483a  cmp     edi, esi
0x18006483c  jnz     short loc_18006484C
0x18006483e  test    r12d, r12d
0x180064841  jnz     loc_180064945
0x180064847  cmp     r14d, ebx
0x18006484a  jnz     short loc_180064879
0x18006484c  test    edi, edi
0x18006484e  jnz     short loc_18006485E
0x180064850  test    r12d, r12d
0x180064853  jz      loc_180064945
0x180064859  cmp     r14d, ebx
0x18006485c  jz      short loc_180064879
0x18006485e  cmp     edi, 2
0x180064861  jnz     loc_180064945
0x180064867  test    r12d, r12d
0x18006486a  jz      loc_180064945
0x180064870  cmp     r14d, ebx
0x180064873  jz      loc_180064945
0x180064879  test    r14d, r14d
0x18006487c  jz      loc_180064945
0x180064882  test    ebx, ebx
0x180064884  jz      loc_180064945
0x18006488a  mov     r14d, [rsp+130h+var_100]
0x18006488f  mov     r9d, edi
0x180064892  mov     edx, r14d
0x180064895  mov     r8d, ebx
0x180064898  mov     rcx, r13
0x18006489b  call    ?_CallAudioRoutingManagerToEnableProviderChange@CallAudioRouting@@AEAAJIW4CellularAudioType@@W4AudioProviderChangeOperation@@@Z; CallAudioRouting::_CallAudioRoutingManagerToEnableProviderChange(uint,CellularAudioType,AudioProviderChangeOperation)
0x1800648a0  test    eax, eax
0x1800648a2  jns     short loc_1800648BA
0x1800648a4  mov     r9d, 0C28h
0x1800648aa  lea     r8, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x1800648b1  mov     edx, esi
0x1800648b3  mov     ecx, eax
0x1800648b5  jmp     loc_180064809
0x1800648ba  mov     rcx, r15; lpCriticalSection
0x1800648bd  call    cs:__imp_EnterCriticalSection
0x1800648c3  lea     r8, [rsp+130h+var_F8]; struct CallAudioRouting::CellularAudioState **
0x1800648c8  mov     [rsp+130h+var_F8], 0
0x1800648d1  mov     edx, r14d; unsigned int
0x1800648d4  mov     rcx, r13; this
0x1800648d7  call    ?_FindCellularState@CallAudioRouting@@AEAAHIPEAPEAUCellularAudioState@1@@Z; CallAudioRouting::_FindCellularState(uint,CallAudioRouting::CellularAudioState * *)
0x1800648dc  test    eax, eax
0x1800648de  jnz     short loc_18006491F
0x1800648e0  mov     ebx, 80070490h
0x1800648e5  mov     edx, ebx; int
0x1800648e7  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x1800648ec  mov     r9d, 0EEAh
0x1800648f2  lea     r8, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x1800648f9  xor     edx, edx
0x1800648fb  mov     ecx, ebx
0x1800648fd  call    Log_HREvent_17
0x180064902  mov     rcx, r15; lpCriticalSection
0x180064905  call    cs:__imp_LeaveCriticalSection
0x18006490b  mov     r9d, 0C3Ah
0x180064911  lea     r8, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180064918  mov     edx, esi
0x18006491a  jmp     loc_180064807
0x18006491f  mov     rcx, [rsp+130h+var_F8]
0x180064924  cmp     edi, esi
0x180064926  jz      short loc_180064934
0x180064928  test    edi, edi
0x18006492a  jnz     short loc_180064932
0x18006492c  mov     eax, [rcx+8]
0x18006492f  mov     [rcx+4], eax
0x180064932  xor     ebx, ebx
0x180064934  mov     [rcx+8], ebx
0x180064937  mov     rcx, r15; lpCriticalSection
0x18006493a  call    cs:__imp_LeaveCriticalSection
0x180064940  jmp     loc_1800649F5
0x180064945  mov     eax, cs:dword_1800B3200
0x18006494b  mov     ecx, 4
0x180064950  cmp     eax, ecx
0x180064952  jbe     loc_1800649F5
0x180064958  mov     eax, [rsp+130h+var_FC]
0x18006495c  lea     rdx, byte_1800A9C91; int
0x180064963  mov     [rsp+130h+var_FC], eax
0x180064967  xor     r9d, r9d; int
0x18006496a  lea     rax, [rsp+130h+var_FC]
0x18006496f  mov     [rsp+130h+var_F0], r14d
0x180064974  mov     r14d, [rsp+130h+var_100]
0x180064979  xor     r8d, r8d; int
0x18006497c  mov     [rbp+57h+var_60], rax
0x180064980  lea     rax, [rsp+130h+var_F0]
0x180064985  mov     [rbp+57h+var_70], rax
0x180064989  lea     rax, [rsp+130h+var_EC]
0x18006498e  mov     [rbp+57h+var_80], rax
0x180064992  lea     rax, [rsp+130h+var_F8]
0x180064997  mov     [rbp+57h+var_90], rax
0x18006499b  lea     rax, [rsp+130h+var_100]
0x1800649a0  mov     [rbp+57h+var_A0], rax
0x1800649a4  lea     rax, aCallaudiorouti_7; "CallAudioRouting: Invalid cellular prov"...
0x1800649ab  mov     [rbp+57h+var_B0], rax
0x1800649af  lea     rax, [rbp+57h+var_D0]
0x1800649b3  mov     [rbp+57h+var_58], rcx
0x1800649b7  mov     [rbp+57h+var_68], rcx
0x1800649bb  mov     [rbp+57h+var_78], rcx
0x1800649bf  mov     [rbp+57h+var_88], rcx
0x1800649c3  mov     [rbp+57h+var_98], rcx
0x1800649c7  lea     rcx, dword_1800B3200; int
0x1800649ce  mov     [rsp+130h+var_108], rax; PEVENT_DATA_DESCRIPTOR
0x1800649d3  mov     [rsp+130h+var_110], 8; ULONG
0x1800649db  mov     [rsp+130h+var_EC], edi
0x1800649df  mov     dword ptr [rsp+130h+var_F8], ebx
0x1800649e3  mov     [rsp+130h+var_100], r14d
0x1800649e8  mov     [rbp+57h+var_A8], 3Dh ; '='
0x1800649f0  call    _tlgWriteTransfer_EventWriteTransfer
0x1800649f5  mov     rcx, [rbp+57h+var_50]
0x1800649f9  xor     rcx, rsp; StackCookie
0x1800649fc  call    __security_check_cookie
0x180064a01  add     rsp, 0F8h
0x180064a08  pop     r15
0x180064a0a  pop     r14
0x180064a0c  pop     r13
0x180064a0e  pop     r12
0x180064a10  pop     rdi
0x180064a11  pop     rsi
0x180064a12  pop     rbx
0x180064a13  pop     rbp
0x180064a14  retn
```
