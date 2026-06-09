# PrintSupportExtensionManager::GetInstance(void)

- ea: `0x180046ca0`
- end: `0x180046d7e`
- name: `?GetInstance@PrintSupportExtensionManager@@SAAEAV1@XZ`
- size: `222`
- prototype: `struct PrintSupportExtensionManager *(void)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800267ac`
- `0x18002687c`

## callees

- `0x180001674`
- `0x180004194`
- `0x180004eac`
- `0x180004f14`
- `0x1800465e0`
- `0x180046ca0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180046cdb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180046cdb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180046cef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180046cef`
- `api-ms-win-core-processthreads-l1-1-1!GetCurrentProcessorNumber` at `0x180046ce5`
- `api-ms-win-core-processthreads-l1-1-1!GetCurrentProcessorNumber` at `0x180046ce5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct PrintSupportExtensionManager *PrintSupportExtensionManager::GetInstance(void)
{
  __int64 v0; // r8
  __int64 v1; // r9
  PrintSupportExtensionManager *v3; // rcx
  DWORD CurrentThreadId; // [rsp+50h] [rbp+8h] BYREF
  DWORD CurrentProcessorNumber; // [rsp+58h] [rbp+10h] BYREF
  DWORD CurrentProcessId; // [rsp+60h] [rbp+18h] BYREF
  __int64 *v7; // [rsp+68h] [rbp+20h] BYREF

  if ( dword_180084590 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_180084590);
    if ( dword_180084590 == -1 )
    {
      PrintSupportExtensionManager::PrintSupportExtensionManager(v3);
      atexit(PrintSupportExtensionManager::GetInstance_::_2_::_dynamic_atexit_destructor_for__instance__);
      Init_thread_footer(&dword_180084590);
    }
  }
  if ( (unsigned int)dword_180083000 > 5 )
  {
    CurrentThreadId = GetCurrentThreadId();
    CurrentProcessorNumber = GetCurrentProcessorNumber();
    CurrentProcessId = GetCurrentProcessId();
    v7 = &qword_1800845A0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (__int64)&dword_180083000,
      (__int64)byte_1800751F3,
      v0,
      v1,
      (__int64)&v7,
      (__int64)&CurrentProcessId,
      (__int64)&CurrentProcessorNumber,
      (__int64)&CurrentThreadId);
  }
  return (struct PrintSupportExtensionManager *)&qword_1800845A0;
}

```

## disassembly

```asm
0x180046ca0  push    rbx
0x180046ca2  sub     rsp, 40h
0x180046ca6  mov     ecx, cs:_tls_index
0x180046cac  mov     rax, gs:58h
0x180046cb5  mov     edx, 4
0x180046cba  mov     rax, [rax+rcx*8]
0x180046cbe  mov     eax, [rdx+rax]
0x180046cc1  cmp     cs:dword_180084590, eax
0x180046cc7  jg      short loc_180046D42
0x180046cc9  mov     eax, cs:dword_180083000
0x180046ccf  lea     rbx, qword_1800845A0
0x180046cd6  cmp     eax, 5
0x180046cd9  jbe     short loc_180046D39
0x180046cdb  call    cs:__imp_GetCurrentThreadId
0x180046ce1  mov     [rsp+48h+arg_0], eax
0x180046ce5  call    cs:__imp_GetCurrentProcessorNumber
0x180046ceb  mov     [rsp+48h+arg_8], eax
0x180046cef  call    cs:__imp_GetCurrentProcessId
0x180046cf5  mov     [rsp+48h+arg_10], eax
0x180046cf9  mov     [rsp+48h+arg_18], rbx
0x180046cfe  lea     rcx, [rsp+48h+arg_0]
0x180046d03  mov     [rsp+48h+var_10], rcx
0x180046d08  lea     rcx, [rsp+48h+arg_8]
0x180046d0d  mov     [rsp+48h+var_18], rcx
0x180046d12  lea     rcx, [rsp+48h+arg_10]
0x180046d17  mov     [rsp+48h+var_20], rcx
0x180046d1c  lea     rcx, [rsp+48h+arg_18]
0x180046d21  mov     [rsp+48h+var_28], rcx
0x180046d26  lea     rdx, byte_1800751F3
0x180046d2d  lea     rcx, dword_180083000
0x180046d34  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180046d39  mov     rax, rbx
0x180046d3c  add     rsp, 40h
0x180046d40  pop     rbx
0x180046d41  retn
0x180046d42  lea     rcx, dword_180084590
0x180046d49  call    _Init_thread_header
0x180046d4e  cmp     cs:dword_180084590, 0FFFFFFFFh
0x180046d55  jnz     loc_180046CC9
0x180046d5b  call    ??0PrintSupportExtensionManager@@AEAA@XZ; PrintSupportExtensionManager::PrintSupportExtensionManager(void)
0x180046d60  lea     rcx, _PrintSupportExtensionManager__GetInstance____2____dynamic_atexit_destructor_for__instance__; void (__cdecl *)()
0x180046d67  call    atexit
0x180046d6c  nop
0x180046d6d  lea     rcx, dword_180084590
0x180046d74  call    _Init_thread_footer
0x180046d79  jmp     loc_180046CC9
```
