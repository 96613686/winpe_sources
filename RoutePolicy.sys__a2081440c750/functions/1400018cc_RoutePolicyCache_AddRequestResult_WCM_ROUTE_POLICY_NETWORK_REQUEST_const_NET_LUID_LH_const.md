# RoutePolicyCache::AddRequestResult(_WCM_ROUTE_POLICY_NETWORK_REQUEST const &,_NET_LUID_LH const &)

- ea: `0x1400018cc`
- end: `0x140001aa3`
- name: `?AddRequestResult@RoutePolicyCache@@YAJAEBU_WCM_ROUTE_POLICY_NETWORK_REQUEST@@AEBT_NET_LUID_LH@@@Z`
- size: `471`
- prototype: `__int64 __fastcall(RoutePolicyCache *__hidden this, const struct _WCM_ROUTE_POLICY_NETWORK_REQUEST *, const union _NET_LUID_LH *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140007280`

## callees

- `0x140001008`
- `0x140001580`
- `0x1400018cc`
- `0x140001ed8`
- `0x140007d28`
- `0x140007d7c`
- `0x14000935c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140001a1e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001a1e`
- `ntoskrnl!ExAllocatePool2` at `0x140001931`
- `ntoskrnl!ExAllocatePool2` at `0x140001931`

## string_xrefs

- `0x140001959`: `Failed to allocate cache entry`
- `0x1400019f4`: `DeepCopyNetworkRequest failed`

## pseudocode

```c
__int64 __fastcall RoutePolicyCache::AddRequestResult(
        RoutePolicyCache *this,
        const struct _WCM_ROUTE_POLICY_NETWORK_REQUEST *a2,
        const union _NET_LUID_LH *a3)
{
  PVOID *i; // rbx
  __int64 Pool2; // rax
  int v7; // r8d
  int v8; // r9d
  _QWORD *v9; // rbx
  int v11; // eax
  int v12; // r8d
  int v13; // r9d
  unsigned int v14; // edi
  _QWORD *v15; // rax
  bool v16; // zf
  __int128 v17; // [rsp+30h] [rbp-20h] BYREF
  int v18; // [rsp+40h] [rbp-10h] BYREF
  const char *v19; // [rsp+48h] [rbp-8h] BYREF

  AcquireSpinLock(&v17, &g_cacheLock);
  for ( i = (PVOID *)g_cacheListHead; ; i = (PVOID *)*i )
  {
    if ( i == &g_cacheListHead )
    {
      Pool2 = ExAllocatePool2(64, 72, 1684435058);
      v9 = (_QWORD *)Pool2;
      if ( Pool2 )
      {
        v11 = DeepCopyNetworkRequest(Pool2 + 16, this);
        v14 = v11;
        if ( v11 >= 0 )
        {
          v9[8] = *(_QWORD *)a2;
          v15 = (_QWORD *)qword_1400123B0;
          if ( *(PVOID **)qword_1400123B0 != &g_cacheListHead )
            __fastfail(3u);
          v16 = (_QWORD)v17 == 0;
          *v9 = &g_cacheListHead;
          v9[1] = v15;
          *v15 = v9;
          qword_1400123B0 = (__int64)v9;
          if ( !v16 )
            SpinLockAndSavedIrql::Release((const struct SpinLockAndSavedIrql *)&v17);
          return 0;
        }
        else
        {
          if ( (unsigned int)dword_140012050 > 2 )
          {
            v18 = v11;
            v19 = "DeepCopyNetworkRequest failed";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
              dword_140012050,
              (unsigned int)&byte_14000E7C7,
              v12,
              v13,
              (__int64)&v19,
              (__int64)&v18);
          }
          ExFreePoolWithTag(v9, 0x64667072u);
          if ( (_QWORD)v17 )
            SpinLockAndSavedIrql::Release((const struct SpinLockAndSavedIrql *)&v17);
          return v14;
        }
      }
      else
      {
        if ( (unsigned int)dword_140012050 > 2 )
        {
          v18 = -1073741670;
          v19 = "Failed to allocate cache entry";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            (unsigned int)&v19,
            (unsigned int)&word_14000E5EE,
            v7,
            v8,
            (__int64)&v19,
            (__int64)&v18);
        }
        if ( (_QWORD)v17 )
          SpinLockAndSavedIrql::Release((const struct SpinLockAndSavedIrql *)&v17);
        return 3221225626LL;
      }
    }
    if ( (unsigned __int8)operator__(i + 2, this) )
      break;
  }
  MicrosoftTelemetryAssertTriggeredNoArgsKM();
  if ( (_QWORD)v17 )
    SpinLockAndSavedIrql::Release((const struct SpinLockAndSavedIrql *)&v17);
  return 3221226768LL;
}

```

## disassembly

```asm
0x1400018cc  mov     [rsp-18h+arg_8], rbx
0x1400018d1  mov     [rsp-18h+arg_10], rsi
0x1400018d6  push    rbp
0x1400018d7  push    rdi
0x1400018d8  push    r15
0x1400018da  mov     rbp, rsp
0x1400018dd  sub     rsp, 50h
0x1400018e1  mov     rsi, rdx
0x1400018e4  mov     rdi, rcx
0x1400018e7  lea     rdx, ?g_cacheLock@@3_KA; unsigned __int64 g_cacheLock
0x1400018ee  lea     rcx, [rbp+var_20]
0x1400018f2  call    ?AcquireSpinLock@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_K$$A6AXAEBUSpinLockAndSavedIrql@@@Z$1?Release@1@SAX0@ZU?$integral_constant@_K$01@wistd@@U1@PEA_K$0A@$$T@details@wil@@@details@wil@@@wil@@PEA_K@Z; AcquireSpinLock(unsigned __int64 *)
0x1400018f7  mov     rbx, cs:?g_cacheListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_cacheListHead
0x1400018fe  lea     r15, ?g_cacheListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_cacheListHead
0x140001905  jmp     short loc_14000191E
0x140001907  lea     rcx, [rbx+10h]
0x14000190b  mov     rdx, rdi
0x14000190e  call    operator__
0x140001913  test    al, al
0x140001915  jnz     loc_1400019A5
0x14000191b  mov     rbx, [rbx]
0x14000191e  cmp     rbx, r15
0x140001921  jnz     short loc_140001907
0x140001923  mov     edx, 48h ; 'H'
0x140001928  mov     r8d, 64667072h
0x14000192e  lea     ecx, [rdx-8]
0x140001931  call    cs:__imp_ExAllocatePool2
0x140001938  nop     dword ptr [rax+rax+00h]
0x14000193d  mov     rbx, rax
0x140001940  test    rax, rax
0x140001943  jnz     loc_1400019CD
0x140001949  mov     eax, cs:dword_140012050
0x14000194f  mov     ebx, 0C000009Ah
0x140001954  cmp     eax, 2
0x140001957  jbe     short loc_140001985
0x140001959  lea     rax, aFailedToAlloca; "Failed to allocate cache entry"
0x140001960  mov     [rbp+var_10], ebx
0x140001963  mov     [rbp+var_8], rax
0x140001967  lea     rcx, [rbp+var_8]
0x14000196b  lea     rax, [rbp+var_10]
0x14000196f  mov     [rsp+50h+var_28], rax
0x140001974  lea     rdx, word_14000E5EE
0x14000197b  mov     [rsp+50h+var_30], rcx
0x140001980  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140001985  cmp     qword ptr [rbp+var_20], 0
0x14000198a  jz      short loc_14000199E
0x14000198c  movaps  xmm0, [rbp+var_20]
0x140001990  lea     rcx, [rbp+var_20]; struct SpinLockAndSavedIrql *
0x140001994  movdqa  [rbp+var_20], xmm0
0x140001999  call    ?Release@SpinLockAndSavedIrql@@SAXAEBU1@@Z; SpinLockAndSavedIrql::Release(SpinLockAndSavedIrql const &)
0x14000199e  mov     eax, ebx
0x1400019a0  jmp     loc_140001A8D
0x1400019a5  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x1400019aa  cmp     qword ptr [rbp+var_20], 0
0x1400019af  jz      short loc_1400019C3
0x1400019b1  movaps  xmm0, [rbp+var_20]
0x1400019b5  lea     rcx, [rbp+var_20]; struct SpinLockAndSavedIrql *
0x1400019b9  movdqa  [rbp+var_20], xmm0
0x1400019be  call    ?Release@SpinLockAndSavedIrql@@SAXAEBU1@@Z; SpinLockAndSavedIrql::Release(SpinLockAndSavedIrql const &)
0x1400019c3  mov     eax, 0C0000510h
0x1400019c8  jmp     loc_140001A8D
0x1400019cd  lea     rcx, [rax+10h]
0x1400019d1  mov     rdx, rdi
0x1400019d4  call    DeepCopyNetworkRequest
0x1400019d9  mov     edi, eax
0x1400019db  test    eax, eax
0x1400019dd  jns     short loc_140001A47
0x1400019df  mov     ecx, cs:dword_140012050
0x1400019e5  cmp     ecx, 2
0x1400019e8  jbe     short loc_140001A16
0x1400019ea  mov     [rbp+var_10], eax
0x1400019ed  lea     rdx, byte_14000E7C7
0x1400019f4  lea     rax, aDeepcopynetwor; "DeepCopyNetworkRequest failed"
0x1400019fb  mov     [rbp+var_8], rax
0x1400019ff  lea     rax, [rbp+var_10]
0x140001a03  mov     [rsp+50h+var_28], rax
0x140001a08  lea     rax, [rbp+var_8]
0x140001a0c  mov     [rsp+50h+var_30], rax
0x140001a11  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140001a16  mov     edx, 64667072h; Tag
0x140001a1b  mov     rcx, rbx; P
0x140001a1e  call    cs:__imp_ExFreePoolWithTag
0x140001a25  nop     dword ptr [rax+rax+00h]
0x140001a2a  cmp     qword ptr [rbp+var_20], 0
0x140001a2f  jz      short loc_140001A43
0x140001a31  movaps  xmm0, [rbp+var_20]
0x140001a35  lea     rcx, [rbp+var_20]; struct SpinLockAndSavedIrql *
0x140001a39  movdqa  [rbp+var_20], xmm0
0x140001a3e  call    ?Release@SpinLockAndSavedIrql@@SAXAEBU1@@Z; SpinLockAndSavedIrql::Release(SpinLockAndSavedIrql const &)
0x140001a43  mov     eax, edi
0x140001a45  jmp     short loc_140001A8D
0x140001a47  mov     rax, [rsi]
0x140001a4a  mov     [rbx+40h], rax
0x140001a4e  mov     rax, cs:qword_1400123B0
0x140001a55  cmp     [rax], r15
0x140001a58  jz      short loc_140001A61
0x140001a5a  mov     ecx, 3
0x140001a5f  int     29h; Win8: RtlFailFast(ecx)
0x140001a61  cmp     qword ptr [rbp+var_20], 0
0x140001a66  mov     [rbx], r15
0x140001a69  mov     [rbx+8], rax
0x140001a6d  mov     [rax], rbx
0x140001a70  mov     cs:qword_1400123B0, rbx
0x140001a77  jz      short loc_140001A8B
0x140001a79  movaps  xmm0, [rbp+var_20]
0x140001a7d  lea     rcx, [rbp+var_20]; struct SpinLockAndSavedIrql *
0x140001a81  movdqa  [rbp+var_20], xmm0
0x140001a86  call    ?Release@SpinLockAndSavedIrql@@SAXAEBU1@@Z; SpinLockAndSavedIrql::Release(SpinLockAndSavedIrql const &)
0x140001a8b  xor     eax, eax
0x140001a8d  lea     r11, [rsp+50h+var_s0]
0x140001a92  mov     rbx, [r11+28h]
0x140001a96  mov     rsi, [r11+30h]
0x140001a9a  mov     rsp, r11
0x140001a9d  pop     r15
0x140001a9f  pop     rdi
0x140001aa0  pop     rbp
0x140001aa1  retn
```
