# ScheduledToasts::SubscribeAndAddToList(_WNF_STATE_NAME,_GUID,_GUID,ushort const *,ushort *)

- ea: `0x1800734c0`
- end: `0x1800737a4`
- name: `?SubscribeAndAddToList@ScheduledToasts@@AEAAJU_WNF_STATE_NAME@@U_GUID@@1PEBGPEAG@Z`
- size: `740`
- prototype: `__int64 __usercall@<rax>(ScheduledToasts *__hidden this@<rcx>, struct _WNF_STATE_NAME@<rdx>, struct _GUID *__struct_ptr@<r8>, struct _GUID *__struct_ptr@<r9>, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800200b4`
- `0x1800730b4`

## callees

- `0x18002ee38`
- `0x1800734c0`
- `0x1800af0a4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007363a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007363a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18007360f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18007360f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007355a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007355a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180073546`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180073546`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180073782`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180073782`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x18007352e`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x18007352e`
- `ntdll!RtlNtStatusToDosError` at `0x1800736be`
- `ntdll!RtlNtStatusToDosError` at `0x1800736be`
- `OLEAUT32!__imp_SysAllocString` at `0x1800734ec`
- `OLEAUT32!__imp_SysAllocString` at `0x1800734ec`
- `OLEAUT32!__imp_SysFreeString` at `0x180073799`
- `OLEAUT32!__imp_SysFreeString` at `0x180073799`

## string_xrefs

- `0x180073675`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\scheduledtoasts.cpp`
- `0x1800736e4`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\scheduledtoasts.cpp`
- `0x18007373e`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\scheduledtoasts.cpp`

## pseudocode

```c
__int64 __fastcall ScheduledToasts::SubscribeAndAddToList(
        RTL_SRWLOCK *this,
        struct _WNF_STATE_NAME a2,
        struct _GUID *a3,
        struct _GUID *a4,
        OLECHAR *psz,
        unsigned __int16 *a6)
{
  OLECHAR *v10; // rbp
  NTSTATUS v11; // eax
  unsigned int v12; // edi
  HANDLE ProcessHeap; // rax
  _QWORD *v14; // rax
  _QWORD *v15; // rsi
  unsigned __int16 *v16; // rax
  _OWORD *v17; // rcx
  __int64 v18; // rdx
  __int128 v19; // xmm0
  __int128 v20; // xmm1
  ScheduledToasts **Ptr; // rcx
  _QWORD *v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // r9
  signed int v26; // eax
  int v27; // [rsp+20h] [rbp-68h]
  _QWORD v28[9]; // [rsp+40h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v28[0] = 0;
  v10 = SysAllocString(psz);
  if ( !v10 )
  {
    v12 = -2147024882;
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x324,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\scheduledtoasts.cpp",
      (const char *)0x8007000ELL,
      v27);
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_12;
    v24 = 53;
    goto LABEL_26;
  }
  v11 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))RtlSubscribeWnfStateChangeNotification)(
          v28,
          a2,
          0,
          ScheduledToasts::WnfCallback);
  if ( v11 < 0 )
  {
    v26 = RtlNtStatusToDosError(v11);
    v12 = v26;
    if ( v26 > 0 )
      v12 = (unsigned __int16)v26 | 0x80070000;
  }
  else
  {
    v12 = 0;
  }
  if ( (v12 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x332,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\scheduledtoasts.cpp",
      (const char *)v12,
      (int)this);
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_12;
    v24 = 54;
    v25 = v12;
LABEL_20:
    WPP_SF_d(v23[2], v24, WPP_7a7099aae5df3fa656003ab1196d31fe_Traceguids, v25);
    goto LABEL_12;
  }
  ProcessHeap = GetProcessHeap();
  v14 = HeapAlloc(ProcessHeap, 8u, 0x150u);
  v15 = v14;
  if ( !v14 )
  {
    v12 = -2147024882;
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x335,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\scheduledtoasts.cpp",
      (const char *)0x8007000ELL,
      (int)this);
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_12;
    v24 = 55;
LABEL_26:
    v25 = 2147942414LL;
    goto LABEL_20;
  }
  v14[41] = v10;
  v14[3] = v28[0];
  v16 = a6;
  v28[0] = 0;
  if ( a6 )
  {
    v17 = (_OWORD *)((char *)v15 + 68);
    v18 = 2;
    do
    {
      v19 = *(_OWORD *)v16;
      v16 += 64;
      *v17 = v19;
      v17 += 8;
      *(v17 - 7) = *((_OWORD *)v16 - 7);
      *(v17 - 6) = *((_OWORD *)v16 - 6);
      *(v17 - 5) = *((_OWORD *)v16 - 5);
      *(v17 - 4) = *((_OWORD *)v16 - 4);
      *(v17 - 3) = *((_OWORD *)v16 - 3);
      *(v17 - 2) = *((_OWORD *)v16 - 2);
      *(v17 - 1) = *((_OWORD *)v16 - 1);
      --v18;
    }
    while ( v18 );
    *((_DWORD *)v15 + 16) = 1;
  }
  v20 = (__int128)*a4;
  *((struct _GUID *)v15 + 2) = *a3;
  v15[2] = a2;
  *((_OWORD *)v15 + 3) = v20;
  AcquireSRWLockExclusive(this + 4);
  Ptr = (ScheduledToasts **)this[3].Ptr;
  if ( *Ptr != (ScheduledToasts *)&this[2] )
    __fastfail(3u);
  v15[1] = Ptr;
  v10 = 0;
  *v15 = this + 2;
  *Ptr = (ScheduledToasts *)v15;
  this[3].Ptr = v15;
  ReleaseSRWLockExclusive(this + 4);
  v28[0] = 0;
LABEL_12:
  if ( v28[0] )
  {
    RtlUnsubscribeWnfNotificationWaitForCompletion(v28[0]);
    v28[0] = 0;
  }
  if ( v10 )
    SysFreeString(v10);
  return v12;
}

```

## disassembly

```asm
0x1800734c0  push    rbx
0x1800734c2  push    rbp
0x1800734c3  push    rsi
0x1800734c4  push    rdi
0x1800734c5  push    r12
0x1800734c7  push    r14
0x1800734c9  push    r15
0x1800734cb  sub     rsp, 50h
0x1800734cf  mov     r14, rcx
0x1800734d2  mov     [rsp+88h+var_48], 0
0x1800734db  mov     rcx, [rsp+88h+psz]; psz
0x1800734e3  mov     r15, r9
0x1800734e6  mov     r12, r8
0x1800734e9  mov     rbx, rdx
0x1800734ec  call    cs:__imp_SysAllocString
0x1800734f2  mov     rbp, rax
0x1800734f5  test    rax, rax
0x1800734f8  jz      loc_1800736DC
0x1800734fe  mov     [rsp+88h+var_50], 1
0x180073506  lea     r9, ?WnfCallback@ScheduledToasts@@CAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z; ScheduledToasts::WnfCallback(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)
0x18007350d  mov     [rsp+88h+var_58], 0
0x180073515  lea     rcx, [rsp+88h+var_48]
0x18007351a  mov     [rsp+88h+var_60], 0
0x180073523  xor     r8d, r8d
0x180073526  mov     rdx, rbx
0x180073529  mov     qword ptr [rsp+88h+var_68], r14; int
0x18007352e  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x180073534  test    eax, eax
0x180073536  js      loc_1800736BC
0x18007353c  xor     edi, edi
0x18007353e  test    edi, edi
0x180073540  js      loc_18007366D
0x180073546  call    cs:__imp_GetProcessHeap
0x18007354c  mov     edx, 8; dwFlags
0x180073551  mov     r8d, 150h; dwBytes
0x180073557  mov     rcx, rax; hHeap
0x18007355a  call    cs:__imp_HeapAlloc
0x180073560  mov     rsi, rax
0x180073563  test    rax, rax
0x180073566  jz      loc_180073736
0x18007356c  mov     [rax+148h], rbp
0x180073573  mov     rax, [rsp+88h+var_48]
0x180073578  mov     [rsi+18h], rax
0x18007357c  mov     rax, [rsp+88h+arg_28]
0x180073584  mov     [rsp+88h+var_48], 0
0x18007358d  test    rax, rax
0x180073590  jz      short loc_1800735F4
0x180073592  lea     rcx, [rsi+44h]
0x180073596  mov     edx, 2
0x18007359b  movups  xmm0, xmmword ptr [rax]
0x18007359e  lea     rax, [rax+80h]
0x1800735a5  movups  xmmword ptr [rcx], xmm0
0x1800735a8  lea     rcx, [rcx+80h]
0x1800735af  movups  xmm1, xmmword ptr [rax-70h]
0x1800735b3  movups  xmmword ptr [rcx-70h], xmm1
0x1800735b7  movups  xmm0, xmmword ptr [rax-60h]
0x1800735bb  movups  xmmword ptr [rcx-60h], xmm0
0x1800735bf  movups  xmm1, xmmword ptr [rax-50h]
0x1800735c3  movups  xmmword ptr [rcx-50h], xmm1
0x1800735c7  movups  xmm0, xmmword ptr [rax-40h]
0x1800735cb  movups  xmmword ptr [rcx-40h], xmm0
0x1800735cf  movups  xmm1, xmmword ptr [rax-30h]
0x1800735d3  movups  xmmword ptr [rcx-30h], xmm1
0x1800735d7  movups  xmm0, xmmword ptr [rax-20h]
0x1800735db  movups  xmmword ptr [rcx-20h], xmm0
0x1800735df  movups  xmm1, xmmword ptr [rax-10h]
0x1800735e3  movups  xmmword ptr [rcx-10h], xmm1
0x1800735e7  sub     rdx, 1
0x1800735eb  jnz     short loc_18007359B
0x1800735ed  mov     dword ptr [rsi+40h], 1
0x1800735f4  movaps  xmm0, xmmword ptr [r12]
0x1800735f9  lea     rcx, [r14+20h]; SRWLock
0x1800735fd  movaps  xmm1, xmmword ptr [r15]
0x180073601  movdqu  xmmword ptr [rsi+20h], xmm0
0x180073606  mov     [rsi+10h], rbx
0x18007360a  movdqu  xmmword ptr [rsi+30h], xmm1
0x18007360f  call    cs:__imp_AcquireSRWLockExclusive
0x180073615  lea     rax, [r14+10h]
0x180073619  mov     rcx, [rax+8]
0x18007361d  cmp     [rcx], rax
0x180073620  jnz     loc_18007377B
0x180073626  mov     [rsi+8], rcx
0x18007362a  xor     ebp, ebp
0x18007362c  mov     [rsi], rax
0x18007362f  mov     [rcx], rsi
0x180073632  lea     rcx, [r14+20h]; SRWLock
0x180073636  mov     [rax+8], rsi
0x18007363a  call    cs:__imp_ReleaseSRWLockExclusive
0x180073640  mov     [rsp+88h+var_48], rbp
0x180073645  mov     rcx, [rsp+88h+var_48]
0x18007364a  test    rcx, rcx
0x18007364d  jnz     loc_180073782
0x180073653  test    rbp, rbp
0x180073656  jnz     loc_180073796
0x18007365c  mov     eax, edi
0x18007365e  add     rsp, 50h
0x180073662  pop     r15
0x180073664  pop     r14
0x180073666  pop     r12
0x180073668  pop     rdi
0x180073669  pop     rsi
0x18007366a  pop     rbp
0x18007366b  pop     rbx
0x18007366c  retn
0x18007366d  mov     rcx, [rsp+88h]; this
0x180073675  lea     r8, aOnecoreuapBase_56; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18007367c  mov     r9d, edi; char *
0x18007367f  mov     edx, 332h; void *
0x180073684  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180073689  mov     rcx, cs:WPP_GLOBAL_Control
0x180073690  lea     rax, WPP_GLOBAL_Control
0x180073697  cmp     rcx, rax
0x18007369a  jz      short loc_180073645
0x18007369c  test    byte ptr [rcx+1Ch], 80h
0x1800736a0  jz      short loc_180073645
0x1800736a2  mov     edx, 36h ; '6'
0x1800736a7  mov     r9d, edi
0x1800736aa  mov     rcx, [rcx+10h]
0x1800736ae  lea     r8, WPP_7a7099aae5df3fa656003ab1196d31fe_Traceguids
0x1800736b5  call    WPP_SF_d
0x1800736ba  jmp     short loc_180073645
0x1800736bc  mov     ecx, eax; Status
0x1800736be  call    cs:__imp_RtlNtStatusToDosError
0x1800736c4  mov     edi, eax
0x1800736c6  test    eax, eax
0x1800736c8  jle     loc_18007353E
0x1800736ce  movzx   edi, ax
0x1800736d1  or      edi, 80070000h
0x1800736d7  jmp     loc_18007353E
0x1800736dc  mov     rcx, [rsp+88h]; this
0x1800736e4  lea     r8, aOnecoreuapBase_56; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800736eb  mov     r9d, 8007000Eh; char *
0x1800736f1  mov     edx, 324h; void *
0x1800736f6  mov     edi, r9d
0x1800736f9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800736fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180073705  lea     rax, WPP_GLOBAL_Control
0x18007370c  cmp     rcx, rax
0x18007370f  jz      loc_180073645
0x180073715  test    byte ptr [rcx+1Ch], 80h
0x180073719  jz      loc_180073645
0x18007371f  mov     edx, 35h ; '5'
0x180073724  jmp     short loc_18007372B
0x180073726  mov     edx, 37h ; '7'
0x18007372b  mov     r9d, 8007000Eh
0x180073731  jmp     loc_1800736AA
0x180073736  mov     rcx, [rsp+88h]; this
0x18007373e  lea     r8, aOnecoreuapBase_56; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180073745  mov     r9d, 8007000Eh; char *
0x18007374b  mov     edx, 335h; void *
0x180073750  mov     edi, r9d
0x180073753  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180073758  mov     rcx, cs:WPP_GLOBAL_Control
0x18007375f  lea     rax, WPP_GLOBAL_Control
0x180073766  cmp     rcx, rax
0x180073769  jz      loc_180073645
0x18007376f  test    byte ptr [rcx+1Ch], 80h
0x180073773  jz      loc_180073645
0x180073779  jmp     short loc_180073726
0x18007377b  mov     ecx, 3
0x180073780  int     29h; Win8: RtlFailFast(ecx)
0x180073782  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x180073788  mov     [rsp+88h+var_48], 0
0x180073791  jmp     loc_180073653
0x180073796  mov     rcx, rbp; bstrString
0x180073799  call    cs:__imp_SysFreeString
0x18007379f  jmp     loc_18007365C
```
