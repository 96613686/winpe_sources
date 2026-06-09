# TimerBrokerHelper::AddToList(_WPN_TIMER_PERSISTENCE *,_GUID const *,unsigned __int64,int)

- ea: `0x1800330f0`
- end: `0x18003348c`
- name: `?AddToList@TimerBrokerHelper@@QEAAJPEAU_WPN_TIMER_PERSISTENCE@@PEBU_GUID@@_KH@Z`
- size: `924`
- prototype: `__int64 __usercall@<rax>(TimerBrokerHelper *__hidden this@<rcx>, struct _WPN_TIMER_PERSISTENCE *@<rdx>, const struct _GUID *@<r8>, unsigned __int64@<r9>, int)`
- caller_count: `4`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800317e4`
- `0x180032b54`
- `0x18008e7b0`
- `0x1800d8340`

## callees

- `0x18002ee38`
- `0x1800330f0`
- `0x1800a0b2c`
- `0x1800af0a4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800332b9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800332b9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180033271`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180033271`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180033141`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180033141`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003312d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180033473`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003312d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180033473`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180033481`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180033481`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18003345a`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18003345a`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180033206`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180033206`
- `ntdll!RtlNtStatusToDosError` at `0x18003330e`
- `ntdll!RtlNtStatusToDosError` at `0x18003330e`
- `OLEAUT32!__imp_SysAllocString` at `0x180033157`
- `OLEAUT32!__imp_SysAllocString` at `0x180033157`
- `OLEAUT32!__imp_SysFreeString` at `0x180033468`
- `OLEAUT32!__imp_SysFreeString` at `0x180033468`

## string_xrefs

- `0x180033331`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\timerbrokerhelper.cpp`
- `0x1800333b5`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\timerbrokerhelper.cpp`
- `0x18003341c`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\timerbrokerhelper.cpp`

## pseudocode

```c
__int64 __fastcall TimerBrokerHelper::AddToList(
        TimerBrokerHelper *this,
        struct _WPN_TIMER_PERSISTENCE *a2,
        const struct _GUID *a3,
        unsigned __int64 a4,
        int a5)
{
  HANDLE ProcessHeap; // rax
  char *v10; // rbx
  OLECHAR *v11; // rbp
  unsigned int v12; // edi
  _OWORD *v13; // rax
  __int128 *v14; // rcx
  __int64 v15; // rdx
  __int128 v16; // xmm0
  NTSTATUS v17; // eax
  _QWORD *v18; // rax
  _QWORD *i; // rcx
  _QWORD *v20; // rcx
  signed int v22; // eax
  _QWORD *v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // r9
  _QWORD *v26; // rax
  HANDLE v27; // rax
  int v28; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  __int64 v30; // [rsp+78h] [rbp+10h] BYREF

  v30 = 0;
  if ( !a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs(this, 0, a3);
  if ( !a3 )
    MicrosoftTelemetryAssertTriggeredNoArgs(this, a2, a3);
  ProcessHeap = GetProcessHeap();
  v10 = (char *)HeapAlloc(ProcessHeap, 8u, 0x188u);
  if ( !v10 )
  {
    v11 = 0;
    v12 = -2147024882;
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x11A,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\timerbrokerhelper.cpp",
      (const char *)0x8007000ELL,
      v28);
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_22;
    v24 = 12;
LABEL_34:
    v25 = 2147942414LL;
LABEL_40:
    WPP_SF_d(v23[2], v24, WPP_ac311802d7f83fbc35c813d130b35da9_Traceguids, v25);
    goto LABEL_22;
  }
  v11 = SysAllocString((const OLECHAR *)a2 + 40);
  if ( !v11 )
  {
    v12 = -2147024882;
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x11D,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\timerbrokerhelper.cpp",
      (const char *)0x8007000ELL,
      v28);
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_22;
    v24 = 13;
    goto LABEL_34;
  }
  v12 = 0;
  if ( *((_DWORD *)a2 + 19) )
  {
    v13 = v10 + 120;
    v14 = (__int128 *)((char *)a2 + 340);
    v15 = 2;
    do
    {
      v16 = *v14;
      v14 += 8;
      *v13 = v16;
      v13 += 8;
      *(v13 - 7) = *(v14 - 7);
      *(v13 - 6) = *(v14 - 6);
      *(v13 - 5) = *(v14 - 5);
      *(v13 - 4) = *(v14 - 4);
      *(v13 - 3) = *(v14 - 3);
      *(v13 - 2) = *(v14 - 2);
      *(v13 - 1) = *(v14 - 1);
      --v15;
    }
    while ( v15 );
    *((_DWORD *)v10 + 29) = 1;
  }
  if ( !a5 )
    goto LABEL_14;
  v17 = RtlSubscribeWnfStateChangeNotification(
          &v30,
          *(_QWORD *)((char *)a2 + 68),
          0,
          TimerBrokerHelper::TimerWnfCallback);
  if ( v17 < 0 )
  {
    v22 = RtlNtStatusToDosError(v17);
    v12 = v22;
    if ( v22 > 0 )
      v12 = (unsigned __int16)v22 | 0x80070000;
  }
  if ( (v12 & 0x80000000) == 0 )
  {
LABEL_14:
    *((_OWORD *)v10 + 2) = *((_OWORD *)a2 + 1);
    *((_OWORD *)v10 + 3) = *(_OWORD *)a2;
    *((_QWORD *)v10 + 2) = *(_QWORD *)((char *)a2 + 68);
    *((struct _GUID *)v10 + 4) = *a3;
    *((_OWORD *)v10 + 5) = *((_OWORD *)a2 + 2);
    *((_DWORD *)v10 + 24) = *((_DWORD *)a2 + 12);
    *(_OWORD *)(v10 + 100) = *(_OWORD *)((char *)a2 + 52);
    *((_QWORD *)v10 + 3) = v30;
    *((_QWORD *)v10 + 47) = v11;
    *((_QWORD *)v10 + 48) = a4;
    AcquireSRWLockExclusive((PSRWLOCK)this + 5);
    v18 = (_QWORD *)((char *)this + 24);
    if ( a4 )
    {
      for ( i = (_QWORD *)*v18; ; i = (_QWORD *)*i )
      {
        if ( i == v18 )
          goto LABEL_19;
        if ( a4 < i[48] )
          break;
      }
      v26 = (_QWORD *)i[1];
      if ( (_QWORD *)*v26 == i )
      {
        *(_QWORD *)v10 = i;
        *((_QWORD *)v10 + 1) = v26;
        *v26 = v10;
        i[1] = v10;
        goto LABEL_21;
      }
    }
    else
    {
LABEL_19:
      v20 = (_QWORD *)*((_QWORD *)this + 4);
      if ( (_QWORD *)*v20 == v18 )
      {
        *(_QWORD *)v10 = v18;
        *((_QWORD *)v10 + 1) = v20;
        *v20 = v10;
        *((_QWORD *)this + 4) = v10;
LABEL_21:
        ReleaseSRWLockExclusive((PSRWLOCK)this + 5);
        v11 = 0;
        v30 = 0;
        v10 = 0;
        _InterlockedIncrement((volatile signed __int32 *)this + 4);
        goto LABEL_22;
      }
    }
    __fastfail(3u);
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x131,
    (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\timerbrokerhelper.cpp",
    (const char *)v12,
    (int)this);
  v23 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
  {
    v24 = 14;
    v25 = v12;
    goto LABEL_40;
  }
LABEL_22:
  if ( v30 )
    RtlUnsubscribeWnfNotificationWaitForCompletion(v30);
  if ( v11 )
    SysFreeString(v11);
  if ( v10 )
  {
    v27 = GetProcessHeap();
    HeapFree(v27, 0, v10);
  }
  return v12;
}

```

## disassembly

```asm
0x1800330f0  mov     [rsp+arg_0], rbx
0x1800330f5  mov     [rsp+arg_10], rbp
0x1800330fa  push    rsi
0x1800330fb  push    rdi
0x1800330fc  push    r12
0x1800330fe  push    r14
0x180033100  push    r15
0x180033102  sub     rsp, 40h
0x180033106  mov     [rsp+68h+arg_8], 0
0x18003310f  mov     r12, r9
0x180033112  mov     r15, r8
0x180033115  mov     rsi, rdx
0x180033118  mov     r14, rcx
0x18003311b  test    rdx, rdx
0x18003311e  jz      loc_18003339C
0x180033124  test    r15, r15
0x180033127  jz      loc_1800333A6
0x18003312d  call    cs:__imp_GetProcessHeap
0x180033133  mov     edx, 8; dwFlags
0x180033138  mov     r8d, 188h; dwBytes
0x18003313e  mov     rcx, rax; hHeap
0x180033141  call    cs:__imp_HeapAlloc
0x180033147  mov     rbx, rax
0x18003314a  test    rax, rax
0x18003314d  jz      loc_1800333B0
0x180033153  lea     rcx, [rsi+50h]; psz
0x180033157  call    cs:__imp_SysAllocString
0x18003315d  mov     rbp, rax
0x180033160  test    rax, rax
0x180033163  jz      loc_18003332C
0x180033169  xor     edi, edi
0x18003316b  lea     r8d, [rdi+1]
0x18003316f  cmp     [rsi+4Ch], edi
0x180033172  jz      short loc_1800331D7
0x180033174  lea     rax, [rbx+78h]
0x180033178  lea     rcx, [rsi+154h]
0x18003317f  lea     edx, [rdi+2]
0x180033182  movups  xmm0, xmmword ptr [rcx]
0x180033185  lea     rcx, [rcx+80h]
0x18003318c  movups  xmmword ptr [rax], xmm0
0x18003318f  lea     rax, [rax+80h]
0x180033196  movups  xmm1, xmmword ptr [rcx-70h]
0x18003319a  movups  xmmword ptr [rax-70h], xmm1
0x18003319e  movups  xmm0, xmmword ptr [rcx-60h]
0x1800331a2  movups  xmmword ptr [rax-60h], xmm0
0x1800331a6  movups  xmm1, xmmword ptr [rcx-50h]
0x1800331aa  movups  xmmword ptr [rax-50h], xmm1
0x1800331ae  movups  xmm0, xmmword ptr [rcx-40h]
0x1800331b2  movups  xmmword ptr [rax-40h], xmm0
0x1800331b6  movups  xmm1, xmmword ptr [rcx-30h]
0x1800331ba  movups  xmmword ptr [rax-30h], xmm1
0x1800331be  movups  xmm0, xmmword ptr [rcx-20h]
0x1800331c2  movups  xmmword ptr [rax-20h], xmm0
0x1800331c6  movups  xmm1, xmmword ptr [rcx-10h]
0x1800331ca  movups  xmmword ptr [rax-10h], xmm1
0x1800331ce  sub     rdx, r8
0x1800331d1  jnz     short loc_180033182
0x1800331d3  mov     [rbx+74h], r8d
0x1800331d7  cmp     [rsp+68h+arg_20], edi
0x1800331de  jz      short loc_18003321C
0x1800331e0  mov     rdx, [rsi+44h]
0x1800331e4  lea     r9, ?TimerWnfCallback@TimerBrokerHelper@@CAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z; TimerBrokerHelper::TimerWnfCallback(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)
0x1800331eb  mov     [rsp+68h+var_30], r8d
0x1800331f0  lea     rcx, [rsp+68h+arg_8]
0x1800331f5  mov     [rsp+68h+var_38], edi
0x1800331f9  xor     r8d, r8d
0x1800331fc  mov     [rsp+68h+var_40], rdi
0x180033201  mov     qword ptr [rsp+68h+var_48], r14; int
0x180033206  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x18003320c  test    eax, eax
0x18003320e  js      loc_18003330C
0x180033214  test    edi, edi
0x180033216  js      loc_180033417
0x18003321c  movups  xmm0, xmmword ptr [rsi+10h]
0x180033220  lea     rcx, [r14+28h]; SRWLock
0x180033224  movdqu  xmmword ptr [rbx+20h], xmm0
0x180033229  movups  xmm1, xmmword ptr [rsi]
0x18003322c  movdqu  xmmword ptr [rbx+30h], xmm1
0x180033231  mov     rax, [rsi+44h]
0x180033235  mov     [rbx+10h], rax
0x180033239  movups  xmm0, xmmword ptr [r15]
0x18003323d  movdqu  xmmword ptr [rbx+40h], xmm0
0x180033242  movups  xmm1, xmmword ptr [rsi+20h]
0x180033246  movdqu  xmmword ptr [rbx+50h], xmm1
0x18003324b  mov     eax, [rsi+30h]
0x18003324e  mov     [rbx+60h], eax
0x180033251  movups  xmm0, xmmword ptr [rsi+34h]
0x180033255  movdqu  xmmword ptr [rbx+64h], xmm0
0x18003325a  mov     rax, [rsp+68h+arg_8]
0x18003325f  mov     [rbx+18h], rax
0x180033263  mov     [rbx+178h], rbp
0x18003326a  mov     [rbx+180h], r12
0x180033271  call    cs:__imp_AcquireSRWLockExclusive
0x180033277  lea     rax, [r14+18h]
0x18003327b  test    r12, r12
0x18003327e  jz      short loc_18003329A
0x180033280  mov     rcx, [rax]
0x180033283  cmp     rcx, rax
0x180033286  jz      short loc_18003329A
0x180033288  cmp     r12, [rcx+180h]
0x18003328f  jb      loc_18003337C
0x180033295  mov     rcx, [rcx]
0x180033298  jmp     short loc_180033283
0x18003329a  mov     rcx, [rax+8]
0x18003329e  cmp     [rcx], rax
0x1800332a1  jnz     loc_180033453
0x1800332a7  mov     [rbx], rax
0x1800332aa  mov     [rbx+8], rcx
0x1800332ae  mov     [rcx], rbx
0x1800332b1  mov     [rax+8], rbx
0x1800332b5  lea     rcx, [r14+28h]; SRWLock
0x1800332b9  call    cs:__imp_ReleaseSRWLockExclusive
0x1800332bf  xor     ebp, ebp
0x1800332c1  mov     [rsp+68h+arg_8], 0
0x1800332ca  xor     ebx, ebx
0x1800332cc  lock inc dword ptr [r14+10h]
0x1800332d1  mov     rcx, [rsp+68h+arg_8]
0x1800332d6  test    rcx, rcx
0x1800332d9  jnz     loc_18003345A
0x1800332df  test    rbp, rbp
0x1800332e2  jnz     loc_180033465
0x1800332e8  test    rbx, rbx
0x1800332eb  jnz     loc_180033473
0x1800332f1  lea     r11, [rsp+68h+var_28]
0x1800332f6  mov     eax, edi
0x1800332f8  mov     rbx, [r11+30h]
0x1800332fc  mov     rbp, [r11+40h]
0x180033300  mov     rsp, r11
0x180033303  pop     r15
0x180033305  pop     r14
0x180033307  pop     r12
0x180033309  pop     rdi
0x18003330a  pop     rsi
0x18003330b  retn
0x18003330c  mov     ecx, eax; Status
0x18003330e  call    cs:__imp_RtlNtStatusToDosError
0x180033314  mov     edi, eax
0x180033316  test    eax, eax
0x180033318  jle     loc_180033214
0x18003331e  movzx   edi, ax
0x180033321  or      edi, 80070000h
0x180033327  jmp     loc_180033214
0x18003332c  mov     rcx, [rsp+68h]; this
0x180033331  lea     r8, aOnecoreuapBase_155; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180033338  mov     r9d, 8007000Eh; char *
0x18003333e  mov     edx, 11Dh; void *
0x180033343  mov     edi, r9d
0x180033346  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003334b  mov     rcx, cs:WPP_GLOBAL_Control
0x180033352  lea     rax, WPP_GLOBAL_Control
0x180033359  cmp     rcx, rax
0x18003335c  jz      loc_1800332D1
0x180033362  test    byte ptr [rcx+1Ch], 80h
0x180033366  jz      loc_1800332D1
0x18003336c  mov     edx, 0Dh
0x180033371  mov     r9d, 8007000Eh
0x180033377  jmp     loc_180033402
0x18003337c  mov     rax, [rcx+8]
0x180033380  cmp     [rax], rcx
0x180033383  jnz     loc_180033453
0x180033389  mov     [rbx], rcx
0x18003338c  mov     [rbx+8], rax
0x180033390  mov     [rax], rbx
0x180033393  mov     [rcx+8], rbx
0x180033397  jmp     loc_1800332B5
0x18003339c  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "PersistentEntry != NULL")
0x1800333a1  jmp     loc_180033124
0x1800333a6  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "PersistenceEventId != NULL")
0x1800333ab  jmp     loc_18003312D
0x1800333b0  mov     rcx, [rsp+68h]; this
0x1800333b5  lea     r8, aOnecoreuapBase_155; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800333bc  mov     r9d, 8007000Eh; char *
0x1800333c2  xor     ebp, ebp
0x1800333c4  mov     edx, 11Ah; void *
0x1800333c9  mov     edi, r9d
0x1800333cc  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800333d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800333d8  lea     rax, WPP_GLOBAL_Control
0x1800333df  cmp     rcx, rax
0x1800333e2  jz      loc_1800332D1
0x1800333e8  test    byte ptr [rcx+1Ch], 80h
0x1800333ec  jz      loc_1800332D1
0x1800333f2  lea     edx, [rbp+0Ch]
0x1800333f5  jmp     loc_180033371
0x1800333fa  mov     edx, 0Eh
0x1800333ff  mov     r9d, edi
0x180033402  mov     rcx, [rcx+10h]
0x180033406  lea     r8, WPP_ac311802d7f83fbc35c813d130b35da9_Traceguids
0x18003340d  call    WPP_SF_d
0x180033412  jmp     loc_1800332D1
0x180033417  mov     rcx, [rsp+68h]; this
0x18003341c  lea     r8, aOnecoreuapBase_155; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180033423  mov     r9d, edi; char *
0x180033426  mov     edx, 131h; void *
0x18003342b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180033430  mov     rcx, cs:WPP_GLOBAL_Control
0x180033437  lea     rax, WPP_GLOBAL_Control
0x18003343e  cmp     rcx, rax
0x180033441  jz      loc_1800332D1
0x180033447  test    byte ptr [rcx+1Ch], 80h
0x18003344b  jz      loc_1800332D1
0x180033451  jmp     short loc_1800333FA
0x180033453  mov     ecx, 3
0x180033458  int     29h; Win8: RtlFailFast(ecx)
0x18003345a  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x180033460  jmp     loc_1800332DF
0x180033465  mov     rcx, rbp; bstrString
0x180033468  call    cs:__imp_SysFreeString
0x18003346e  jmp     loc_1800332E8
0x180033473  call    cs:__imp_GetProcessHeap
0x180033479  mov     r8, rbx; lpMem
0x18003347c  xor     edx, edx; dwFlags
0x18003347e  mov     rcx, rax; hHeap
0x180033481  call    cs:__imp_HeapFree
0x180033487  jmp     loc_1800332F1
```
