# Private::WorkItemBase::QueueTimerCallback(stdext::shared_ref<Private::WorkItemBase>,TimeSpan const *,TimeSpan const *,ComApartments::ComApartment)

- ea: `0x180047200`
- end: `0x1800474cd`
- name: `?QueueTimerCallback@WorkItemBase@Private@@SA?AV?$shared_ptr@UITimerCallback@@@std@@V?$shared_ref@VWorkItemBase@Private@@@stdext@@PEBVTimeSpan@@1W4ComApartment@ComApartments@@@Z`
- size: `717`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180066b80`
- `0x180066cd8`

## callees

- `0x180006108`
- `0x180006ee0`
- `0x18000ecc0`
- `0x180035e0c`
- `0x180047200`
- `0x1800ae010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004744b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004744b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18004734b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18004734b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800472ef`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800472ef`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall Private::WorkItemBase::QueueTimerCallback(_QWORD *a1, __int64 *a2, _QWORD *a3, _QWORD *a4)
{
  _QWORD *v7; // rax
  __int64 v8; // rbx
  __int64 v9; // rdx
  signed __int32 v10; // eax
  signed __int32 v11; // ett
  volatile signed __int32 *v12; // rbx
  struct _TP_CALLBACK_ENVIRON_V3 *v13; // rdi
  __int64 v14; // r14
  _QWORD *v15; // rcx
  struct _TP_TIMER *ThreadpoolTimer; // rdi
  unsigned __int64 v17; // rdx
  char *v18; // rdx
  _QWORD *v19; // r8
  __int64 v20; // rax
  PVOID v21; // rax
  __int64 v22; // rcx
  volatile signed __int32 *v23; // rbx
  signed int LastError; // eax
  unsigned int v26; // ebx
  __int64 v27; // [rsp+38h] [rbp-38h] BYREF
  _QWORD *v28; // [rsp+40h] [rbp-30h]
  _BYTE pExceptionObject[40]; // [rsp+48h] [rbp-28h] BYREF
  struct _FILETIME pftDueTime; // [rsp+B0h] [rbp+40h] BYREF

  if ( !a3 && !a4 )
  {
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, -2147418113);
    throw (ErrorCodeException *)pExceptionObject;
  }
  *(_DWORD *)(*a2 + 28) = 0;
  v7 = a4;
  if ( a3 )
    v7 = a3;
  pftDueTime = (struct _FILETIME)-*v7;
  v8 = *a2;
  v9 = *(_QWORD *)(*a2 + 40);
  if ( v9 )
  {
    v10 = *(_DWORD *)(v9 + 8);
    while ( v10 )
    {
      v11 = v10;
      v10 = _InterlockedCompareExchange((volatile signed __int32 *)(v9 + 8), v10 + 1, v10);
      if ( v11 == v10 )
      {
        v13 = *(struct _TP_CALLBACK_ENVIRON_V3 **)(v8 + 32);
        v12 = *(volatile signed __int32 **)(v8 + 40);
        goto LABEL_10;
      }
    }
  }
  v12 = 0;
  v13 = 0;
LABEL_10:
  if ( v13 )
  {
    v14 = *a2;
    (*((void (__fastcall **)(PTP_CLEANUP_GROUP *, __int64 *))v13[1].CleanupGroup + 6))(&v13[1].CleanupGroup, &v27);
    v15 = v28;
    if ( *v28 )
    {
      *(_QWORD *)(*v28 + 80LL) = v14;
      v15 = v28;
    }
    *(_QWORD *)(v14 + 80) = 0;
    *(_QWORD *)(v14 + 88) = *v15;
    *v15 = v14;
    v13 = (struct _TP_CALLBACK_ENVIRON_V3 *)((char *)v13 + 8);
    if ( v27 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 24LL))(v27);
  }
  ThreadpoolTimer = CreateThreadpoolTimer(Private::WorkItemBase::TimerCallback, (PVOID)*a2, v13);
  if ( !ThreadpoolTimer )
  {
    LastError = GetLastError();
    v26 = LastError;
    if ( LastError > 0 )
      v26 = (unsigned __int16)LastError | 0x80070000;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 13, WPP_a6e5c4a2fee73d0f0f64a9c4f51812c4_Traceguids, v26);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v26);
    throw (ErrorCodeException *)pExceptionObject;
  }
  if ( !a4 )
  {
    LODWORD(v17) = 0;
    goto LABEL_22;
  }
  if ( *a4 < TimeSpan::Zero || *a4 > TimeSpan::Zero )
  {
    v17 = *a4 / 0x2710uLL;
LABEL_22:
    SetThreadpoolTimer(ThreadpoolTimer, &pftDueTime, v17, 0);
  }
  v18 = (char *)operator new(0x30u);
  *(_OWORD *)v18 = 0;
  *((_DWORD *)v18 + 2) = 1;
  *((_DWORD *)v18 + 3) = 1;
  *(_QWORD *)v18 = &std::_Ref_count_obj2<Private::TimerCallback>::`vftable';
  v19 = v18 + 16;
  v20 = a2[1];
  if ( v20 )
    _InterlockedIncrement((volatile signed __int32 *)(v20 + 8));
  v21 = (PVOID)*a2;
  v22 = a2[1];
  *v19 = &Private::TimerCallback::`vftable';
  *((_QWORD *)v18 + 3) = v21;
  *((_QWORD *)v18 + 4) = v22;
  *((_QWORD *)v18 + 5) = ThreadpoolTimer;
  *a1 = v19;
  a1[1] = v18;
  if ( v12 )
  {
    if ( _InterlockedExchangeAdd(v12 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
      if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
    }
  }
  v23 = (volatile signed __int32 *)a2[1];
  if ( v23 )
  {
    if ( _InterlockedExchangeAdd(v23 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v23)(v23);
      if ( _InterlockedExchangeAdd(v23 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v23 + 8LL))(v23);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x180047200  mov     [rsp-28h+arg_0], rbx
0x180047205  mov     [rsp-28h+arg_18], rsi
0x18004720a  mov     [rsp-28h+arg_8], rdx
0x18004720f  push    rbp
0x180047210  push    rdi
0x180047211  push    r12
0x180047213  push    r14
0x180047215  push    r15
0x180047217  mov     rbp, rsp
0x18004721a  sub     rsp, 70h
0x18004721e  mov     r15, r9
0x180047221  mov     rsi, rdx
0x180047224  mov     r12, rcx
0x180047227  test    r8, r8
0x18004722a  jnz     short loc_180047235
0x18004722c  test    r9, r9
0x18004722f  jz      loc_1800474AE
0x180047235  mov     rax, [rdx]
0x180047238  mov     dword ptr [rax+1Ch], 0
0x18004723f  mov     rax, r15
0x180047242  test    r8, r8
0x180047245  cmovnz  rax, r8
0x180047249  mov     rax, [rax]
0x18004724c  neg     rax
0x18004724f  mov     qword ptr [rbp+pftDueTime.dwLowDateTime], rax
0x180047253  mov     rbx, [rdx]
0x180047256  xorps   xmm0, xmm0
0x180047259  movdqu  xmmword ptr [rbp+pcbe], xmm0
0x18004725e  mov     rdx, [rbx+28h]
0x180047262  test    rdx, rdx
0x180047265  jz      short loc_18004727E
0x180047267  mov     eax, [rdx+8]
0x18004726a  jmp     short loc_18004727A
0x18004726c  lea     ecx, [rax+1]
0x18004726f  lock cmpxchg [rdx+8], ecx
0x180047274  jz      loc_180047327
0x18004727a  test    eax, eax
0x18004727c  jnz     short loc_18004726C
0x18004727e  mov     rdi, [rbp+pcbe]
0x180047282  mov     rbx, [rbp+pcbe+8]
0x180047286  test    rdi, rdi
0x180047289  jz      short loc_1800472E2
0x18004728b  mov     r14, [rsi]
0x18004728e  lea     rcx, [rdi+58h]
0x180047292  mov     rax, [rcx]
0x180047295  lea     rdx, [rbp+var_38]
0x180047299  mov     rax, [rax+30h]
0x18004729d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800472a2  mov     rcx, [rbp+var_30]
0x1800472a6  mov     rax, [rcx]
0x1800472a9  test    rax, rax
0x1800472ac  jz      short loc_1800472B6
0x1800472ae  mov     [rax+50h], r14
0x1800472b2  mov     rcx, [rbp+var_30]
0x1800472b6  mov     qword ptr [r14+50h], 0
0x1800472be  mov     rax, [rcx]
0x1800472c1  mov     [r14+58h], rax
0x1800472c5  mov     [rcx], r14
0x1800472c8  add     rdi, 8
0x1800472cc  mov     rcx, [rbp+var_38]
0x1800472d0  test    rcx, rcx
0x1800472d3  jz      short loc_1800472E2
0x1800472d5  mov     rax, [rcx]
0x1800472d8  mov     rax, [rax+18h]
0x1800472dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800472e1  nop
0x1800472e2  mov     r8, rdi; pcbe
0x1800472e5  mov     rdx, [rsi]; pv
0x1800472e8  lea     rcx, ?TimerCallback@WorkItemBase@Private@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800472ef  call    cs:__imp_CreateThreadpoolTimer
0x1800472f5  mov     rdi, rax
0x1800472f8  test    rax, rax
0x1800472fb  jz      loc_18004744B
0x180047301  test    r15, r15
0x180047304  jz      short loc_18004733C
0x180047306  mov     rax, cs:?Zero@TimeSpan@@2V1@B; TimeSpan const TimeSpan::Zero
0x18004730d  cmp     [r15], rax
0x180047310  jb      short loc_180047314
0x180047312  jbe     short loc_180047351
0x180047314  mov     rax, 346DC5D63886594Bh
0x18004731e  mul     qword ptr [r15]
0x180047321  shr     rdx, 0Bh
0x180047325  jmp     short loc_18004733E
0x180047327  mov     rdi, [rbx+20h]
0x18004732b  mov     [rbp+pcbe], rdi
0x18004732f  mov     rbx, [rbx+28h]
0x180047333  mov     [rbp+pcbe+8], rbx
0x180047337  jmp     loc_180047286
0x18004733c  xor     edx, edx
0x18004733e  xor     r9d, r9d; msWindowLength
0x180047341  mov     r8d, edx; msPeriod
0x180047344  lea     rdx, [rbp+pftDueTime]; pftDueTime
0x180047348  mov     rcx, rdi; pti
0x18004734b  call    cs:__imp_SetThreadpoolTimer
0x180047351  mov     ecx, 30h ; '0'; Size
0x180047356  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004735b  mov     rdx, rax
0x18004735e  mov     [rbp+pcbe], rax
0x180047362  xorps   xmm0, xmm0
0x180047365  movups  xmmword ptr [rax], xmm0
0x180047368  mov     dword ptr [rax+8], 1
0x18004736f  mov     dword ptr [rax+0Ch], 1
0x180047376  lea     rax, ??_7?$_Ref_count_obj2@VTimerCallback@Private@@@std@@6B@; const std::_Ref_count_obj2<Private::TimerCallback>::`vftable'
0x18004737d  mov     [rdx], rax
0x180047380  lea     r8, [rdx+10h]
0x180047384  mov     rax, [rsi+8]
0x180047388  test    rax, rax
0x18004738b  jz      short loc_180047391
0x18004738d  lock inc dword ptr [rax+8]
0x180047391  mov     rax, [rsi]
0x180047394  mov     rcx, [rsi+8]
0x180047398  lea     r9, ??_7TimerCallback@Private@@6B@; const Private::TimerCallback::`vftable'
0x18004739f  mov     [r8], r9
0x1800473a2  mov     [r8+8], rax
0x1800473a6  mov     [r8+10h], rcx
0x1800473aa  mov     [r8+18h], rdi
0x1800473ae  mov     [r12], r8
0x1800473b2  mov     [r12+8], rdx
0x1800473b7  or      edi, 0FFFFFFFFh
0x1800473ba  test    rbx, rbx
0x1800473bd  jz      short loc_1800473F3
0x1800473bf  mov     eax, edi
0x1800473c1  lock xadd [rbx+8], eax
0x1800473c6  add     eax, edi
0x1800473c8  jnz     short loc_1800473F3
0x1800473ca  mov     rax, [rbx]
0x1800473cd  mov     rcx, rbx
0x1800473d0  mov     rax, [rax]
0x1800473d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800473d8  mov     eax, edi
0x1800473da  lock xadd [rbx+0Ch], eax
0x1800473df  add     eax, edi
0x1800473e1  jnz     short loc_1800473F3
0x1800473e3  mov     rax, [rbx]
0x1800473e6  mov     rcx, rbx
0x1800473e9  mov     rax, [rax+8]
0x1800473ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800473f2  nop
0x1800473f3  mov     rbx, [rsi+8]
0x1800473f7  test    rbx, rbx
0x1800473fa  jz      short loc_18004742F
0x1800473fc  mov     eax, edi
0x1800473fe  lock xadd [rbx+8], eax
0x180047403  add     eax, edi
0x180047405  jnz     short loc_18004742F
0x180047407  mov     rax, [rbx]
0x18004740a  mov     rcx, rbx
0x18004740d  mov     rax, [rax]
0x180047410  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047415  mov     eax, edi
0x180047417  lock xadd [rbx+0Ch], eax
0x18004741c  add     eax, edi
0x18004741e  jnz     short loc_18004742F
0x180047420  mov     rax, [rbx]
0x180047423  mov     rcx, rbx
0x180047426  mov     rax, [rax+8]
0x18004742a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004742f  mov     rax, r12
0x180047432  lea     r11, [rsp+70h+var_s0]
0x180047437  mov     rbx, [r11+30h]
0x18004743b  mov     rsi, [r11+48h]
0x18004743f  mov     rsp, r11
0x180047442  pop     r15
0x180047444  pop     r14
0x180047446  pop     r12
0x180047448  pop     rdi
0x180047449  pop     rbp
0x18004744a  retn
0x18004744b  call    cs:__imp_GetLastError
0x180047451  nop
0x180047452  mov     ebx, eax
0x180047454  test    eax, eax
0x180047456  jle     short loc_180047461
0x180047458  movzx   ebx, ax
0x18004745b  or      ebx, 80070000h
0x180047461  lea     rax, WPP_GLOBAL_Control
0x180047468  mov     rcx, cs:WPP_GLOBAL_Control
0x18004746f  cmp     rcx, rax
0x180047472  jz      short loc_180047492
0x180047474  test    byte ptr [rcx+1Ch], 1
0x180047478  jz      short loc_180047492
0x18004747a  mov     edx, 0Dh
0x18004747f  mov     r9d, ebx
0x180047482  lea     r8, WPP_a6e5c4a2fee73d0f0f64a9c4f51812c4_Traceguids
0x180047489  mov     rcx, [rcx+10h]
0x18004748d  call    WPP_SF_d
0x180047492  mov     edx, ebx; int
0x180047494  lea     rcx, [rbp+pExceptionObject]; this
0x180047498  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x18004749d  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x1800474a4  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800474a8  call    _CxxThrowException_0
0x1800474ae  mov     edx, 8000FFFFh; int
0x1800474b3  lea     rcx, [rbp+pExceptionObject]; this
0x1800474b7  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x1800474bc  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x1800474c3  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800474c7  call    _CxxThrowException_0
```
