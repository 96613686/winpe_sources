# SPTelemetry::ModelUpdate::StartEventLocal(unsigned __int64,bool)

- ea: `0x1400087c0`
- end: `0x140008854`
- name: `?StartEventLocal@ModelUpdate@SPTelemetry@@UEAAX_K_N@Z`
- size: `148`
- prototype: `void __fastcall(SPTelemetry::ModelUpdate *this, __int64, unsigned __int8)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x140001360`
- `0x1400077b0`
- `0x1400087c0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400087fd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400087fd`

## pseudocode

```c
void __fastcall SPTelemetry::ModelUpdate::StartEventLocal(
        SPTelemetry::ModelUpdate *this,
        __int64 a2,
        unsigned __int8 a3)
{
  int v3; // esi
  const struct _tlgProvider_t *v6; // rax
  __int64 v7; // rbx
  __int64 v8; // rax
  DWORD CurrentThreadId; // eax
  __int64 v10; // r9
  int v11; // [rsp+40h] [rbp-38h] BYREF
  _QWORD v12[6]; // [rsp+48h] [rbp-30h] BYREF
  DWORD v13; // [rsp+98h] [rbp+20h] BYREF

  v3 = a3;
  v6 = SPTraceLoggingClass::Provider();
  v7 = (__int64)v6;
  if ( *(_DWORD *)v6 > 4u )
  {
    v8 = *((_QWORD *)v6 + 3);
    if ( (*(_QWORD *)(v7 + 16) & 1) != 0 && (v8 & 1) == v8 )
    {
      CurrentThreadId = GetCurrentThreadId();
      v10 = *((_QWORD *)this + 6);
      v13 = CurrentThreadId;
      v11 = v3;
      v12[0] = a2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v7,
        (__int64)byte_140029C69,
        (__int64)this + 32,
        v10,
        (__int64)v12,
        (__int64)&v11,
        (__int64)&v13);
    }
  }
}

```

## disassembly

```asm
0x1400087c0  push    rbx
0x1400087c2  push    rbp
0x1400087c3  push    rsi
0x1400087c4  push    rdi
0x1400087c5  sub     rsp, 58h
0x1400087c9  movzx   esi, r8b
0x1400087cd  mov     rbp, rdx
0x1400087d0  mov     rdi, rcx
0x1400087d3  call    ?Provider@SPTraceLoggingClass@@SAPEBU_tlgProvider_t@@XZ; SPTraceLoggingClass::Provider(void)
0x1400087d8  mov     rbx, rax
0x1400087db  mov     r9d, [rax]
0x1400087de  cmp     r9d, 4
0x1400087e2  jbe     short loc_14000884B
0x1400087e4  mov     rax, [rax+18h]
0x1400087e8  mov     r9, [rbx+10h]
0x1400087ec  test    r9b, 1
0x1400087f0  jz      short loc_14000884B
0x1400087f2  mov     rcx, rax
0x1400087f5  and     ecx, 1
0x1400087f8  cmp     rcx, rax
0x1400087fb  jnz     short loc_14000884B
0x1400087fd  call    cs:__imp_GetCurrentThreadId
0x140008803  mov     r9, [rdi+30h]
0x140008807  lea     r8, [rdi+20h]
0x14000880b  mov     [rsp+78h+arg_18], eax
0x140008812  lea     rdx, byte_140029C69
0x140008819  lea     rax, [rsp+78h+arg_18]
0x140008821  mov     [rsp+78h+var_38], esi
0x140008825  mov     [rsp+78h+var_48], rax
0x14000882a  mov     rcx, rbx
0x14000882d  lea     rax, [rsp+78h+var_38]
0x140008832  mov     [rsp+78h+var_30], rbp
0x140008837  mov     [rsp+78h+var_50], rax
0x14000883c  lea     rax, [rsp+78h+var_30]
0x140008841  mov     [rsp+78h+var_58], rax
0x140008846  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14000884b  add     rsp, 58h
0x14000884f  pop     rdi
0x140008850  pop     rsi
0x140008851  pop     rbp
0x140008852  pop     rbx
0x140008853  retn
```
