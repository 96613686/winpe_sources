# SPTelemetry::ModelUpdate::StartEvent(unsigned __int64,bool)

- ea: `0x140008710`
- end: `0x1400087ad`
- name: `?StartEvent@ModelUpdate@SPTelemetry@@UEAAX_K_N@Z`
- size: `157`
- prototype: `void __fastcall(SPTelemetry::ModelUpdate *this, __int64, unsigned __int8)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x140001360`
- `0x1400077b0`
- `0x140008710`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140008756`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140008756`

## pseudocode

```c
void __fastcall SPTelemetry::ModelUpdate::StartEvent(SPTelemetry::ModelUpdate *this, __int64 a2, unsigned __int8 a3)
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
    if ( (*(_QWORD *)(v7 + 16) & 0x400000000000LL) != 0 && (v8 & 0x400000000000LL) == v8 )
    {
      CurrentThreadId = GetCurrentThreadId();
      v10 = *((_QWORD *)this + 6);
      v13 = CurrentThreadId;
      v11 = v3;
      v12[0] = a2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v7,
        (__int64)&byte_140029CB7,
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
0x140008710  push    rbx
0x140008712  push    rbp
0x140008713  push    rsi
0x140008714  push    rdi
0x140008715  sub     rsp, 58h
0x140008719  movzx   esi, r8b
0x14000871d  mov     rbp, rdx
0x140008720  mov     rdi, rcx
0x140008723  call    ?Provider@SPTraceLoggingClass@@SAPEBU_tlgProvider_t@@XZ; SPTraceLoggingClass::Provider(void)
0x140008728  mov     rbx, rax
0x14000872b  mov     r9d, [rax]
0x14000872e  cmp     r9d, 4
0x140008732  jbe     short loc_1400087A4
0x140008734  mov     rax, [rax+18h]
0x140008738  mov     rdx, 400000000000h
0x140008742  mov     r9, [rbx+10h]
0x140008746  test    rdx, r9
0x140008749  jz      short loc_1400087A4
0x14000874b  mov     rcx, rax
0x14000874e  and     rcx, rdx
0x140008751  cmp     rcx, rax
0x140008754  jnz     short loc_1400087A4
0x140008756  call    cs:__imp_GetCurrentThreadId
0x14000875c  mov     r9, [rdi+30h]
0x140008760  lea     r8, [rdi+20h]
0x140008764  mov     [rsp+78h+arg_18], eax
0x14000876b  lea     rdx, byte_140029CB7
0x140008772  lea     rax, [rsp+78h+arg_18]
0x14000877a  mov     [rsp+78h+var_38], esi
0x14000877e  mov     [rsp+78h+var_48], rax
0x140008783  mov     rcx, rbx
0x140008786  lea     rax, [rsp+78h+var_38]
0x14000878b  mov     [rsp+78h+var_30], rbp
0x140008790  mov     [rsp+78h+var_50], rax
0x140008795  lea     rax, [rsp+78h+var_30]
0x14000879a  mov     [rsp+78h+var_58], rax
0x14000879f  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1400087a4  add     rsp, 58h
0x1400087a8  pop     rdi
0x1400087a9  pop     rsi
0x1400087aa  pop     rbp
0x1400087ab  pop     rbx
0x1400087ac  retn
```
