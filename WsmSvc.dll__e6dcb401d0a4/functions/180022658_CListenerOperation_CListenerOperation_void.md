# CListenerOperation::~CListenerOperation(void)

- ea: `0x180022658`
- end: `0x180022869`
- name: `??1CListenerOperation@@UEAA@XZ`
- size: `529`
- prototype: `void __fastcall(CListenerOperation *__hidden this)`
- caller_count: `15`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800c4ae4`
- `0x1800c5708`
- `0x1800e8f88`
- `0x1800fe8e8`
- `0x180176a40`
- `0x18017b3cc`
- `0x18018195c`
- `0x180185b88`
- `0x18018748c`
- `0x180187ff4`
- `0x180188444`
- `0x1801893f8`
- `0x180189994`
- `0x180189ef0`
- `0x1801bd195`

## callees

- `0x180010030`
- `0x1800224f0`
- `0x180022560`
- `0x180022620`
- `0x180022658`
- `0x180023730`
- `0x180026310`
- `0x180028070`
- `0x180028b48`
- `0x18011a6d4`
- `0x18011aed0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800227b3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800227be`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800227b3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800227be`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800227f0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800227f0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180022712`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002275c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180022712`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002275c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180022806`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180022806`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CListenerOperation::~CListenerOperation(CListenerOperation *this)
{
  volatile __int32 *v2; // rsi
  void *v3; // rcx
  struct _TP_WORK *v4; // rcx
  DWORD *v5; // rdi
  DWORD *v6; // rdi

  *(_QWORD *)this = &CListenerOperation::`vftable'{for `IOperation'};
  *((_QWORD *)this + 2) = &CListenerOperation::`vftable'{for `IChannelObserver'};
  v2 = (volatile __int32 *)((char *)this + 32);
  *((_QWORD *)this + 4) = &CListenerOperation::`vftable'{for `Timer'};
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_75752af15f5d369c87e52fdd3e6b012d_Traceguids, this);
  v3 = (void *)*((_QWORD *)this + 19);
  if ( v3 )
  {
    CloseHandle(v3);
    *((_QWORD *)this + 19) = 0;
  }
  v4 = (struct _TP_WORK *)*((_QWORD *)this + 150);
  if ( v4 )
    CloseThreadpoolWork(v4);
  AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr((char *)this + 2112);
  AutoCleanup<AutoRelease<CServiceCommonConfigSettings>,CServiceCommonConfigSettings *>::ReleasePtr((char *)this + 2088);
  CWSManResourceNoResourceUri::~CWSManResourceNoResourceUri((CListenerOperation *)((char *)this + 1216));
  v5 = (DWORD *)((char *)this + 1136);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000000) != 0 )
    WPP_SF_qqd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      12,
      WPP_16fef4f4c93331ed15954a465be26bf2_Traceguids,
      (char *)this + 1136,
      (char *)this + 1144,
      *v5);
  if ( *v5 )
    SetLastError(*v5);
  else
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 1144));
  AutoCleanup<AutoRelease<UserRecord>,UserRecord *>::ReleasePtr((char *)this + 1112);
  CRequestContext::~CRequestContext((CListenerOperation *)((char *)this + 400));
  v6 = (DWORD *)((char *)this + 168);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000000) != 0 )
    WPP_SF_qqd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      12,
      WPP_16fef4f4c93331ed15954a465be26bf2_Traceguids,
      (char *)this + 168,
      (char *)this + 176,
      *v6);
  if ( *v6 )
    SetLastError(*v6);
  else
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 176));
  *(_QWORD *)v2 = &Timer::`vftable';
  _InterlockedExchange(v2 + 14, 1);
  SlimTimer::FireTimer((SlimTimer *)v2, 1);
  _InterlockedExchange(v2 + 14, 0);
  *((_QWORD *)v2 + 8) = &PushSubscription::`vftable'{for `IRemoteOperation'};
  SlimTimer::~SlimTimer((SlimTimer *)v2);
  *((_QWORD *)this + 2) = &IChannelObserver::`vftable';
  IOperation::~IOperation(this);
}

```

## disassembly

```asm
0x180022658  push    rbx
0x18002265a  push    rbp
0x18002265b  push    rsi
0x18002265c  push    rdi
0x18002265d  sub     rsp, 38h
0x180022661  mov     rbx, rcx
0x180022664  lea     rax, ??_7CListenerOperation@@6BIOperation@@@; const CListenerOperation::`vftable'{for `IOperation'}
0x18002266b  mov     [rcx], rax
0x18002266e  lea     rax, ??_7CListenerOperation@@6BIChannelObserver@@@; const CListenerOperation::`vftable'{for `IChannelObserver'}
0x180022675  mov     [rcx+10h], rax
0x180022679  lea     rsi, [rcx+20h]
0x18002267d  lea     rax, ??_7CListenerOperation@@6BTimer@@@; const CListenerOperation::`vftable'{for `Timer'}
0x180022684  mov     [rsi], rax
0x180022687  lea     rbp, WPP_GLOBAL_Control
0x18002268e  mov     rcx, cs:WPP_GLOBAL_Control
0x180022695  cmp     rcx, rbp
0x180022698  jnz     loc_1800227C6
0x18002269e  mov     rcx, [rbx+98h]; hObject
0x1800226a5  test    rcx, rcx
0x1800226a8  jnz     loc_1800227F0
0x1800226ae  mov     rcx, [rbx+4B0h]; pwk
0x1800226b5  test    rcx, rcx
0x1800226b8  jnz     loc_180022806
0x1800226be  lea     rcx, [rbx+840h]
0x1800226c5  call    ?ReleasePtr@?$AutoCleanup@V?$AutoRelease@VWSManHttpListener@@@@PEAVWSManHttpListener@@@@AEAAXXZ; AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(void)
0x1800226ca  nop
0x1800226cb  lea     rcx, [rbx+828h]
0x1800226d2  call    ?ReleasePtr@?$AutoCleanup@V?$AutoRelease@VCServiceCommonConfigSettings@@@@PEAVCServiceCommonConfigSettings@@@@AEAAXXZ; AutoCleanup<AutoRelease<CServiceCommonConfigSettings>,CServiceCommonConfigSettings *>::ReleasePtr(void)
0x1800226d7  nop
0x1800226d8  lea     rcx, [rbx+4C0h]; this
0x1800226df  call    ??1CWSManResourceNoResourceUri@@UEAA@XZ; CWSManResourceNoResourceUri::~CWSManResourceNoResourceUri(void)
0x1800226e4  lea     rdi, [rbx+470h]
0x1800226eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800226f2  cmp     rcx, rbp
0x1800226f5  jz      short loc_180022704
0x1800226f7  test    dword ptr [rcx+1Ch], 1000000h
0x1800226fe  jnz     loc_180022811
0x180022704  mov     ecx, [rdi]; dwErrCode
0x180022706  test    ecx, ecx
0x180022708  jnz     loc_1800227B3
0x18002270e  lea     rcx, [rdi+8]; lpCriticalSection
0x180022712  call    cs:__imp_DeleteCriticalSection
0x180022718  nop
0x180022719  lea     rcx, [rbx+458h]
0x180022720  call    ?ReleasePtr@?$AutoCleanup@V?$AutoRelease@VUserRecord@@@@PEAVUserRecord@@@@AEAAXXZ; AutoCleanup<AutoRelease<UserRecord>,UserRecord *>::ReleasePtr(void)
0x180022725  nop
0x180022726  lea     rcx, [rbx+190h]; this
0x18002272d  call    ??1CRequestContext@@UEAA@XZ; CRequestContext::~CRequestContext(void)
0x180022732  lea     rdi, [rbx+0A8h]
0x180022739  mov     rcx, cs:WPP_GLOBAL_Control
0x180022740  cmp     rcx, rbp
0x180022743  jz      short loc_180022752
0x180022745  test    dword ptr [rcx+1Ch], 1000000h
0x18002274c  jnz     loc_18002283D
0x180022752  mov     ecx, [rdi]; dwErrCode
0x180022754  test    ecx, ecx
0x180022756  jnz     short loc_1800227BE
0x180022758  lea     rcx, [rdi+8]; lpCriticalSection
0x18002275c  call    cs:__imp_DeleteCriticalSection
0x180022762  nop
0x180022763  lea     rax, ??_7Timer@@6B@; const Timer::`vftable'
0x18002276a  mov     [rsi], rax
0x18002276d  mov     eax, 1
0x180022772  xchg    eax, [rsi+38h]
0x180022775  mov     dl, 1; bool
0x180022777  mov     rcx, rsi; this
0x18002277a  call    ?FireTimer@SlimTimer@@UEAAX_N@Z; SlimTimer::FireTimer(bool)
0x18002277f  xor     eax, eax
0x180022781  xchg    eax, [rsi+38h]
0x180022784  lea     rcx, ??_7PushSubscription@@6BIRemoteOperation@@@; const PushSubscription::`vftable'{for `IRemoteOperation'}
0x18002278b  mov     [rsi+40h], rcx
0x18002278f  mov     rcx, rsi; this
0x180022792  call    ??1SlimTimer@@UEAA@XZ; SlimTimer::~SlimTimer(void)
0x180022797  nop
0x180022798  lea     rax, ??_7IChannelObserver@@6B@; const IChannelObserver::`vftable'
0x18002279f  mov     [rbx+10h], rax
0x1800227a3  mov     rcx, rbx; this
0x1800227a6  add     rsp, 38h
0x1800227aa  pop     rdi
0x1800227ab  pop     rsi
0x1800227ac  pop     rbp
0x1800227ad  pop     rbx
0x1800227ae  jmp     ??1IOperation@@UEAA@XZ; IOperation::~IOperation(void)
0x1800227b3  call    cs:__imp_SetLastError
0x1800227b9  jmp     loc_180022719
0x1800227be  call    cs:__imp_SetLastError
0x1800227c4  jmp     short loc_180022763
0x1800227c6  test    dword ptr [rcx+1Ch], 400h
0x1800227cd  jz      loc_18002269E
0x1800227d3  mov     edx, 0Ch
0x1800227d8  mov     r9, rbx
0x1800227db  lea     r8, WPP_75752af15f5d369c87e52fdd3e6b012d_Traceguids
0x1800227e2  mov     rcx, [rcx+10h]
0x1800227e6  call    WPP_SF_q
0x1800227eb  jmp     loc_18002269E
0x1800227f0  call    cs:__imp_CloseHandle
0x1800227f6  mov     qword ptr [rbx+98h], 0
0x180022801  jmp     loc_1800226AE
0x180022806  call    cs:__imp_CloseThreadpoolWork
0x18002280c  jmp     loc_1800226BE
0x180022811  lea     r8, [rdi+8]
0x180022815  mov     edx, 0Ch
0x18002281a  mov     eax, [rdi]
0x18002281c  mov     [rsp+58h+var_30], eax
0x180022820  mov     [rsp+58h+var_38], r8
0x180022825  mov     r9, rdi
0x180022828  lea     r8, WPP_16fef4f4c93331ed15954a465be26bf2_Traceguids
0x18002282f  mov     rcx, [rcx+10h]
0x180022833  call    WPP_SF_qqd
0x180022838  jmp     loc_180022704
0x18002283d  lea     r9, [rdi+8]
0x180022841  mov     edx, 0Ch
0x180022846  mov     eax, [rdi]
0x180022848  mov     [rsp+58h+var_30], eax
0x18002284c  mov     [rsp+58h+var_38], r9
0x180022851  mov     r9, rdi
0x180022854  lea     r8, WPP_16fef4f4c93331ed15954a465be26bf2_Traceguids
0x18002285b  mov     rcx, [rcx+10h]
0x18002285f  call    WPP_SF_qqd
0x180022864  jmp     loc_180022752
```
