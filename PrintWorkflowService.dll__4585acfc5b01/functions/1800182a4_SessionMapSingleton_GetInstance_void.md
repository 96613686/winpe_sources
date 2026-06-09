# SessionMapSingleton::GetInstance(void)

- ea: `0x1800182a4`
- end: `0x180018382`
- name: `?GetInstance@SessionMapSingleton@@SAAEAV1@XZ`
- size: `222`
- prototype: `struct SessionMapSingleton *(void)`
- caller_count: `5`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180016b40`
- `0x180016e10`
- `0x180017400`
- `0x180017890`
- `0x180019e24`

## callees

- `0x180001674`
- `0x180004194`
- `0x180004eac`
- `0x180004f14`
- `0x180018010`
- `0x1800182a4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800182df`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800182df`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800182f3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800182f3`
- `api-ms-win-core-processthreads-l1-1-1!GetCurrentProcessorNumber` at `0x1800182e9`
- `api-ms-win-core-processthreads-l1-1-1!GetCurrentProcessorNumber` at `0x1800182e9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct SessionMapSingleton *SessionMapSingleton::GetInstance(void)
{
  __int64 v0; // r8
  __int64 v1; // r9
  SessionMapSingleton *v3; // rcx
  DWORD CurrentThreadId; // [rsp+50h] [rbp+8h] BYREF
  DWORD CurrentProcessorNumber; // [rsp+58h] [rbp+10h] BYREF
  DWORD CurrentProcessId; // [rsp+60h] [rbp+18h] BYREF
  __int64 *v7; // [rsp+68h] [rbp+20h] BYREF

  if ( dword_1800844F8 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_1800844F8);
    if ( dword_1800844F8 == -1 )
    {
      SessionMapSingleton::SessionMapSingleton(v3);
      atexit(SessionMapSingleton::GetInstance_::_2_::_dynamic_atexit_destructor_for__instance__);
      Init_thread_footer(&dword_1800844F8);
    }
  }
  if ( (unsigned int)dword_180083038 > 5 )
  {
    CurrentThreadId = GetCurrentThreadId();
    CurrentProcessorNumber = GetCurrentProcessorNumber();
    CurrentProcessId = GetCurrentProcessId();
    v7 = &qword_180084500;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (__int64)&dword_180083038,
      (__int64)&byte_18006FE6F,
      v0,
      v1,
      (__int64)&v7,
      (__int64)&CurrentProcessId,
      (__int64)&CurrentProcessorNumber,
      (__int64)&CurrentThreadId);
  }
  return (struct SessionMapSingleton *)&qword_180084500;
}

```

## disassembly

```asm
0x1800182a4  push    rbx
0x1800182a6  sub     rsp, 40h
0x1800182aa  mov     ecx, cs:_tls_index
0x1800182b0  mov     rax, gs:58h
0x1800182b9  mov     edx, 4
0x1800182be  mov     rax, [rax+rcx*8]
0x1800182c2  mov     eax, [rdx+rax]
0x1800182c5  cmp     cs:dword_1800844F8, eax
0x1800182cb  jg      short loc_180018346
0x1800182cd  mov     eax, cs:dword_180083038
0x1800182d3  lea     rbx, qword_180084500
0x1800182da  cmp     eax, 5
0x1800182dd  jbe     short loc_18001833D
0x1800182df  call    cs:__imp_GetCurrentThreadId
0x1800182e5  mov     [rsp+48h+arg_0], eax
0x1800182e9  call    cs:__imp_GetCurrentProcessorNumber
0x1800182ef  mov     [rsp+48h+arg_8], eax
0x1800182f3  call    cs:__imp_GetCurrentProcessId
0x1800182f9  mov     [rsp+48h+arg_10], eax
0x1800182fd  mov     [rsp+48h+arg_18], rbx
0x180018302  lea     rcx, [rsp+48h+arg_0]
0x180018307  mov     [rsp+48h+var_10], rcx
0x18001830c  lea     rcx, [rsp+48h+arg_8]
0x180018311  mov     [rsp+48h+var_18], rcx
0x180018316  lea     rcx, [rsp+48h+arg_10]
0x18001831b  mov     [rsp+48h+var_20], rcx
0x180018320  lea     rcx, [rsp+48h+arg_18]
0x180018325  mov     [rsp+48h+var_28], rcx
0x18001832a  lea     rdx, byte_18006FE6F
0x180018331  lea     rcx, dword_180083038
0x180018338  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001833d  mov     rax, rbx
0x180018340  add     rsp, 40h
0x180018344  pop     rbx
0x180018345  retn
0x180018346  lea     rcx, dword_1800844F8
0x18001834d  call    _Init_thread_header
0x180018352  cmp     cs:dword_1800844F8, 0FFFFFFFFh
0x180018359  jnz     loc_1800182CD
0x18001835f  call    ??0SessionMapSingleton@@AEAA@XZ; SessionMapSingleton::SessionMapSingleton(void)
0x180018364  lea     rcx, _SessionMapSingleton__GetInstance____2____dynamic_atexit_destructor_for__instance__; void (__cdecl *)()
0x18001836b  call    atexit
0x180018370  nop
0x180018371  lea     rcx, dword_1800844F8
0x180018378  call    _Init_thread_footer
0x18001837d  jmp     loc_1800182CD
```
