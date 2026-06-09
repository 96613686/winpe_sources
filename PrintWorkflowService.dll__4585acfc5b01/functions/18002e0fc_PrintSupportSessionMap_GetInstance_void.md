# PrintSupportSessionMap::GetInstance(void)

- ea: `0x18002e0fc`
- end: `0x18002e1da`
- name: `?GetInstance@PrintSupportSessionMap@@SAAEAV1@XZ`
- size: `222`
- prototype: `struct PrintSupportSessionMap *(void)`
- caller_count: `8`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180025e30`
- `0x180026140`
- `0x180026590`
- `0x180026d28`
- `0x180026dac`
- `0x180026e30`
- `0x180027510`
- `0x180034aac`

## callees

- `0x180001674`
- `0x180004194`
- `0x180004eac`
- `0x180004f14`
- `0x18002dec4`
- `0x18002e0fc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002e137`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002e137`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002e14b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002e14b`
- `api-ms-win-core-processthreads-l1-1-1!GetCurrentProcessorNumber` at `0x18002e141`
- `api-ms-win-core-processthreads-l1-1-1!GetCurrentProcessorNumber` at `0x18002e141`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct PrintSupportSessionMap *PrintSupportSessionMap::GetInstance(void)
{
  __int64 v0; // r8
  __int64 v1; // r9
  PrintSupportSessionMap *v3; // rcx
  DWORD CurrentThreadId; // [rsp+50h] [rbp+8h] BYREF
  DWORD CurrentProcessorNumber; // [rsp+58h] [rbp+10h] BYREF
  DWORD CurrentProcessId; // [rsp+60h] [rbp+18h] BYREF
  __int64 *v7; // [rsp+68h] [rbp+20h] BYREF

  if ( dword_180084568 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_180084568);
    if ( dword_180084568 == -1 )
    {
      PrintSupportSessionMap::PrintSupportSessionMap(v3);
      atexit(PrintSupportSessionMap::GetInstance_::_2_::_dynamic_atexit_destructor_for__instance__);
      Init_thread_footer(&dword_180084568);
    }
  }
  if ( (unsigned int)dword_180083000 > 5 )
  {
    CurrentThreadId = GetCurrentThreadId();
    CurrentProcessorNumber = GetCurrentProcessorNumber();
    CurrentProcessId = GetCurrentProcessId();
    v7 = &qword_180084570;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (__int64)&dword_180083000,
      (__int64)byte_1800735D3,
      v0,
      v1,
      (__int64)&v7,
      (__int64)&CurrentProcessId,
      (__int64)&CurrentProcessorNumber,
      (__int64)&CurrentThreadId);
  }
  return (struct PrintSupportSessionMap *)&qword_180084570;
}

```

## disassembly

```asm
0x18002e0fc  push    rbx
0x18002e0fe  sub     rsp, 40h
0x18002e102  mov     ecx, cs:_tls_index
0x18002e108  mov     rax, gs:58h
0x18002e111  mov     edx, 4
0x18002e116  mov     rax, [rax+rcx*8]
0x18002e11a  mov     eax, [rdx+rax]
0x18002e11d  cmp     cs:dword_180084568, eax
0x18002e123  jg      short loc_18002E19E
0x18002e125  mov     eax, cs:dword_180083000
0x18002e12b  lea     rbx, qword_180084570
0x18002e132  cmp     eax, 5
0x18002e135  jbe     short loc_18002E195
0x18002e137  call    cs:__imp_GetCurrentThreadId
0x18002e13d  mov     [rsp+48h+arg_0], eax
0x18002e141  call    cs:__imp_GetCurrentProcessorNumber
0x18002e147  mov     [rsp+48h+arg_8], eax
0x18002e14b  call    cs:__imp_GetCurrentProcessId
0x18002e151  mov     [rsp+48h+arg_10], eax
0x18002e155  mov     [rsp+48h+arg_18], rbx
0x18002e15a  lea     rcx, [rsp+48h+arg_0]
0x18002e15f  mov     [rsp+48h+var_10], rcx
0x18002e164  lea     rcx, [rsp+48h+arg_8]
0x18002e169  mov     [rsp+48h+var_18], rcx
0x18002e16e  lea     rcx, [rsp+48h+arg_10]
0x18002e173  mov     [rsp+48h+var_20], rcx
0x18002e178  lea     rcx, [rsp+48h+arg_18]
0x18002e17d  mov     [rsp+48h+var_28], rcx
0x18002e182  lea     rdx, byte_1800735D3
0x18002e189  lea     rcx, dword_180083000
0x18002e190  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18002e195  mov     rax, rbx
0x18002e198  add     rsp, 40h
0x18002e19c  pop     rbx
0x18002e19d  retn
0x18002e19e  lea     rcx, dword_180084568
0x18002e1a5  call    _Init_thread_header
0x18002e1aa  cmp     cs:dword_180084568, 0FFFFFFFFh
0x18002e1b1  jnz     loc_18002E125
0x18002e1b7  call    ??0PrintSupportSessionMap@@AEAA@XZ; PrintSupportSessionMap::PrintSupportSessionMap(void)
0x18002e1bc  lea     rcx, _PrintSupportSessionMap__GetInstance____2____dynamic_atexit_destructor_for__instance__; void (__cdecl *)()
0x18002e1c3  call    atexit
0x18002e1c8  nop
0x18002e1c9  lea     rcx, dword_180084568
0x18002e1d0  call    _Init_thread_footer
0x18002e1d5  jmp     loc_18002E125
```
