# ScheduledToasts::RemoveByAppId(ushort const *)

- ea: `0x18008de10`
- end: `0x18008dff8`
- name: `?RemoveByAppId@ScheduledToasts@@QEAAJPEBG@Z`
- size: `488`
- prototype: `int(ScheduledToasts *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18008f84c`

## callees

- `0x1800264a4`
- `0x18004aefc`
- `0x18006b4b8`
- `0x18008a97c`
- `0x18008de10`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18008de54`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18008de54`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008de92`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008de92`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008de39`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008de39`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008dfb9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008dfb9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008dfc7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008dfc7`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18008dee3`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18008dee3`
- `OLEAUT32!__imp_SysFreeString` at `0x18008dfa8`
- `OLEAUT32!__imp_SysFreeString` at `0x18008dfa8`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtDeleteEvent` at `0x18008ded1`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtDeleteEvent` at `0x18008ded1`
- `TimeBrokerClient!TbDeleteEvent` at `0x18008debe`
- `TimeBrokerClient!TbDeleteEvent` at `0x18008debe`

## string_xrefs

- `0x18008df0e`: `RemoveAllScheduledToastUpdates`

## pseudocode

```c
__int64 __fastcall ScheduledToasts::RemoveByAppId(RTL_SRWLOCK *this, const unsigned __int16 *a2)
{
  int v2; // r13d
  RTL_SRWLOCK *v3; // r14
  _QWORD *v4; // rdi
  int v7; // esi
  _QWORD *Ptr; // rbx
  int v9; // eax
  RTL_SRWLOCK *v10; // rcx
  RTL_SRWLOCK **v11; // rax
  __int64 v12; // rcx
  int v13; // eax
  WpnTelemetryAggregator *v14; // rbx
  const unsigned __int16 *v15; // rax
  __int64 v16; // r8
  int v17; // ecx
  int v18; // r8d
  int v19; // r9d
  OLECHAR *v20; // rcx
  HANDLE ProcessHeap; // rax
  __int64 v23; // [rsp+40h] [rbp-58h] BYREF
  __int128 v24[4]; // [rsp+50h] [rbp-48h] BYREF
  int v25; // [rsp+B0h] [rbp+18h] BYREF
  const unsigned __int16 *v26; // [rsp+B8h] [rbp+20h] BYREF

  v2 = 0;
  v3 = this + 2;
  v4 = 0;
  do
  {
    v7 = 0;
    AcquireSRWLockExclusive(this + 4);
    Ptr = v3->Ptr;
    if ( v3->Ptr != v3 )
    {
      while ( 1 )
      {
        v4 = Ptr;
        v9 = _o__wcsicmp(a2, Ptr[41]);
        v10 = (RTL_SRWLOCK *)*Ptr;
        if ( !v9 )
          break;
        Ptr = (_QWORD *)*Ptr;
        if ( v10 == v3 )
          goto LABEL_9;
      }
      if ( v10[1].Ptr != Ptr || (v11 = (RTL_SRWLOCK **)Ptr[1], *v11 != (RTL_SRWLOCK *)Ptr) )
        __fastfail(3u);
      *v11 = v10;
      v7 = 1;
      v10[1].Ptr = v11;
    }
LABEL_9:
    ReleaseSRWLockExclusive(this + 4);
    if ( v7 )
    {
      v12 = ((unsigned __int64)v4 + 68) & -(__int64)(*((_DWORD *)v4 + 16) != 0);
      v24[0] = *((_OWORD *)v4 + 2);
      v13 = TbDeleteEvent(v12, v24);
      v2 = 0;
      if ( v13 >= 0 )
        v2 = v13;
      if ( (int)BiPtDeleteEvent(v4 + 6) < 0 )
        v2 = 0;
      RtlUnsubscribeWnfNotificationWaitForCompletion(v4[3]);
      v4[3] = 0;
    }
    else
    {
      v4 = 0;
    }
    v14 = (WpnTelemetryAggregator *)*((_QWORD *)this[5].Ptr + 43);
    v15 = CensorFilePath(a2);
    if ( WpnTelemetryAggregator::AddEventCount(v14, L"RemoveAllScheduledToastUpdates", v15, L"Toast")
      && (unsigned int)dword_18015C038 > 5
      && (unsigned __int8)tlgKeywordOn(&dword_18015C038, 0x400000000000LL, v16) )
    {
      v26 = CensorFilePath(a2);
      v25 = v2;
      v23 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
        v17,
        (unsigned int)&dword_180138A2C,
        v18,
        v19,
        (__int64)&v23,
        (__int64)&v25,
        (__int64)&v26);
    }
    if ( v4 )
    {
      v20 = (OLECHAR *)v4[41];
      if ( v20 )
      {
        SysFreeString(v20);
        v4[41] = 0;
      }
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v4);
      v4 = 0;
    }
  }
  while ( v7 );
  return 0;
}

```

## disassembly

```asm
0x18008de10  mov     [rsp+arg_0], rbx
0x18008de15  push    rbp
0x18008de16  push    rsi
0x18008de17  push    rdi
0x18008de18  push    r12
0x18008de1a  push    r13
0x18008de1c  push    r14
0x18008de1e  push    r15
0x18008de20  sub     rsp, 60h
0x18008de24  xor     r13d, r13d
0x18008de27  lea     r14, [rcx+10h]
0x18008de2b  xor     edi, edi
0x18008de2d  mov     r15, rdx
0x18008de30  mov     rbp, rcx
0x18008de33  lea     rcx, [rbp+20h]; SRWLock
0x18008de37  xor     esi, esi
0x18008de39  call    cs:__imp_AcquireSRWLockExclusive
0x18008de3f  mov     rbx, [r14]
0x18008de42  cmp     rbx, r14
0x18008de45  jz      short loc_18008DE8E
0x18008de47  mov     rdx, [rbx+148h]
0x18008de4e  mov     rcx, r15
0x18008de51  mov     rdi, rbx
0x18008de54  call    cs:__imp__o__wcsicmp
0x18008de5a  mov     rcx, [rbx]
0x18008de5d  test    eax, eax
0x18008de5f  jz      short loc_18008DE6B
0x18008de61  mov     rbx, rcx
0x18008de64  cmp     rcx, r14
0x18008de67  jnz     short loc_18008DE47
0x18008de69  jmp     short loc_18008DE8E
0x18008de6b  cmp     [rcx+8], rbx
0x18008de6f  jnz     loc_18008DFF1
0x18008de75  mov     rax, [rbx+8]
0x18008de79  cmp     [rax], rbx
0x18008de7c  jnz     loc_18008DFF1
0x18008de82  mov     [rax], rcx
0x18008de85  mov     esi, 1
0x18008de8a  mov     [rcx+8], rax
0x18008de8e  lea     rcx, [rbp+20h]; SRWLock
0x18008de92  call    cs:__imp_ReleaseSRWLockExclusive
0x18008de98  test    esi, esi
0x18008de9a  jnz     short loc_18008DEA0
0x18008de9c  xor     edi, edi
0x18008de9e  jmp     short loc_18008DEF1
0x18008dea0  mov     eax, [rdi+40h]
0x18008dea3  lea     rdx, [rdi+44h]
0x18008dea7  movups  xmm0, xmmword ptr [rdi+20h]
0x18008deab  neg     eax
0x18008dead  sbb     rcx, rcx
0x18008deb0  and     rcx, rdx
0x18008deb3  lea     rdx, [rsp+98h+var_48]
0x18008deb8  movdqu  [rsp+98h+var_48], xmm0
0x18008debe  call    cs:__imp_TbDeleteEvent
0x18008dec4  xor     r13d, r13d
0x18008dec7  lea     rcx, [rdi+30h]
0x18008decb  test    eax, eax
0x18008decd  cmovns  r13d, eax
0x18008ded1  call    cs:__imp_BiPtDeleteEvent
0x18008ded7  xor     ecx, ecx
0x18008ded9  test    eax, eax
0x18008dedb  cmovs   r13d, ecx
0x18008dedf  mov     rcx, [rdi+18h]
0x18008dee3  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x18008dee9  mov     qword ptr [rdi+18h], 0
0x18008def1  mov     rax, [rbp+28h]
0x18008def5  mov     rcx, r15; pszPath
0x18008def8  mov     rbx, [rax+158h]
0x18008deff  call    ?CensorFilePath@@YAPEBGPEBG@Z; CensorFilePath(ushort const *)
0x18008df04  lea     r9, aToast; "Toast"
0x18008df0b  mov     r8, rax; unsigned __int16 *
0x18008df0e  lea     rdx, aRemoveallsched_1; "RemoveAllScheduledToastUpdates"
0x18008df15  mov     rcx, rbx; this
0x18008df18  call    ?AddEventCount@WpnTelemetryAggregator@@QEAA_NPEBG00@Z; WpnTelemetryAggregator::AddEventCount(ushort const *,ushort const *,ushort const *)
0x18008df1d  test    al, al
0x18008df1f  jz      short loc_18008DF97
0x18008df21  mov     eax, cs:dword_18015C038
0x18008df27  cmp     eax, 5
0x18008df2a  jbe     short loc_18008DF97
0x18008df2c  mov     rdx, 400000000000h
0x18008df36  lea     rcx, dword_18015C038
0x18008df3d  call    _tlgKeywordOn
0x18008df42  test    al, al
0x18008df44  jz      short loc_18008DF97
0x18008df46  mov     rcx, r15; pszPath
0x18008df49  call    ?CensorFilePath@@YAPEBGPEBG@Z; CensorFilePath(ushort const *)
0x18008df4e  mov     [rsp+98h+arg_18], rax
0x18008df56  lea     rdx, dword_180138A2C
0x18008df5d  lea     rax, [rsp+98h+arg_18]
0x18008df65  mov     [rsp+98h+arg_10], r13d
0x18008df6d  mov     [rsp+98h+var_68], rax
0x18008df72  lea     rax, [rsp+98h+arg_10]
0x18008df7a  mov     [rsp+98h+var_70], rax
0x18008df7f  lea     rax, [rsp+98h+var_58]
0x18008df84  mov     [rsp+98h+var_78], rax
0x18008df89  mov     [rsp+98h+var_58], 1000000h
0x18008df92  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x18008df97  test    rdi, rdi
0x18008df9a  jz      short loc_18008DFCF
0x18008df9c  mov     rcx, [rdi+148h]; bstrString
0x18008dfa3  test    rcx, rcx
0x18008dfa6  jz      short loc_18008DFB9
0x18008dfa8  call    cs:__imp_SysFreeString
0x18008dfae  mov     qword ptr [rdi+148h], 0
0x18008dfb9  call    cs:__imp_GetProcessHeap
0x18008dfbf  mov     r8, rdi; lpMem
0x18008dfc2  xor     edx, edx; dwFlags
0x18008dfc4  mov     rcx, rax; hHeap
0x18008dfc7  call    cs:__imp_HeapFree
0x18008dfcd  xor     edi, edi
0x18008dfcf  test    esi, esi
0x18008dfd1  jnz     loc_18008DE33
0x18008dfd7  mov     rbx, [rsp+98h+arg_0]
0x18008dfdf  xor     eax, eax
0x18008dfe1  add     rsp, 60h
0x18008dfe5  pop     r15
0x18008dfe7  pop     r14
0x18008dfe9  pop     r13
0x18008dfeb  pop     r12
0x18008dfed  pop     rdi
0x18008dfee  pop     rsi
0x18008dfef  pop     rbp
0x18008dff0  retn
0x18008dff1  mov     ecx, 3
0x18008dff6  int     29h; Win8: RtlFailFast(ecx)
```
