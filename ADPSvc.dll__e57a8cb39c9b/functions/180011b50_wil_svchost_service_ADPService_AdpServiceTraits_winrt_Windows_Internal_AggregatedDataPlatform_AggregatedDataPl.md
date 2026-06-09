# wil::svchost_service<ADPService::AdpServiceTraits,winrt::Windows::Internal::AggregatedDataPlatform::AggregatedDataPlatform>::stop(ulong)

- ea: `0x180011b50`
- end: `0x180011c35`
- name: `?stop@?$svchost_service@UAdpServiceTraits@ADPService@@UAggregatedDataPlatform@3Internal@Windows@winrt@@@wil@@AEAAXK@Z`
- size: `229`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x180010070`
- `0x1800c7f12`

## callees

- `0x1800026f0`
- `0x18000771c`
- `0x1800112d0`
- `0x180011878`
- `0x180011b50`
- `0x180011ec8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011b87`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011bb5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011b87`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011bb5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011b74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011b9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011b74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011b9e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011ba9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011ba9`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x180011b7f`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x180011b7f`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x180011bc7`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x180011bc7`

## string_xrefs

- `0x180011c23`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
BOOL __fastcall wil::svchost_service<ADPService::AdpServiceTraits,winrt::Windows::Internal::AggregatedDataPlatform::AggregatedDataPlatform>::stop(
        _QWORD *a1,
        DWORD a2)
{
  void *v4; // rsi
  DWORD LastError; // ebx
  void *v6; // rbx
  DWORD v7; // esi
  const char *v8; // r9
  int v9; // eax
  void *v10; // rdx
  __int64 v11; // r8
  _QWORD *v12; // rbx
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  wil::svchost_service<ADPService::AdpServiceTraits,winrt::Windows::Internal::AggregatedDataPlatform::AggregatedDataPlatform>::update_status(
    (__int64)a1,
    3u,
    a2);
  v4 = (void *)a1[1];
  if ( v4 )
  {
    LastError = GetLastError();
    UnregisterWait(v4);
    SetLastError(LastError);
  }
  a1[1] = 0;
  v6 = (void *)a1[2];
  if ( v6 )
  {
    v7 = GetLastError();
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v8);
    SetLastError(v7);
  }
  a1[2] = 0;
  v9 = CoRegisterServerShutdownDelay(0, 0);
  if ( v9 < 0 )
    wil::details::in1diag3::_Log_Hr(retaddr, v10, v11, (const char *)(unsigned int)v9);
  v12 = (_QWORD *)a1[3];
  a1[3] = 0;
  if ( v12 )
  {
    wil::details::svchost_module<winrt::Windows::Internal::AggregatedDataPlatform::AggregatedDataPlatform>::~svchost_module<winrt::Windows::Internal::AggregatedDataPlatform::AggregatedDataPlatform>(v12);
    operator delete(v12);
  }
  return wil::svchost_service<ADPService::AdpServiceTraits,winrt::Windows::Internal::AggregatedDataPlatform::AggregatedDataPlatform>::update_status(
           (__int64)a1,
           1u,
           a2);
}

```

## disassembly

```asm
0x180011b50  push    rbx
0x180011b52  push    rbp
0x180011b53  push    rsi
0x180011b54  push    rdi
0x180011b55  sub     rsp, 28h
0x180011b59  mov     ebp, edx
0x180011b5b  mov     rdi, rcx
0x180011b5e  mov     r8d, edx
0x180011b61  mov     edx, 3
0x180011b66  call    ?update_status@?$svchost_service@UAdpServiceTraits@ADPService@@UAggregatedDataPlatform@3Internal@Windows@winrt@@@wil@@AEAAXKK@Z; wil::svchost_service<ADPService::AdpServiceTraits,winrt::Windows::Internal::AggregatedDataPlatform::AggregatedDataPlatform>::update_status(ulong,ulong)
0x180011b6b  mov     rsi, [rdi+8]
0x180011b6f  test    rsi, rsi
0x180011b72  jz      short loc_180011B8D
0x180011b74  call    cs:__imp_GetLastError
0x180011b7a  mov     ebx, eax
0x180011b7c  mov     rcx, rsi; WaitHandle
0x180011b7f  call    cs:__imp_UnregisterWait
0x180011b85  mov     ecx, ebx; dwErrCode
0x180011b87  call    cs:__imp_SetLastError
0x180011b8d  mov     qword ptr [rdi+8], 0
0x180011b95  mov     rbx, [rdi+10h]
0x180011b99  test    rbx, rbx
0x180011b9c  jz      short loc_180011BBB
0x180011b9e  call    cs:__imp_GetLastError
0x180011ba4  mov     esi, eax
0x180011ba6  mov     rcx, rbx; hObject
0x180011ba9  call    cs:__imp_CloseHandle
0x180011baf  test    eax, eax
0x180011bb1  jz      short loc_180011C1E
0x180011bb3  mov     ecx, esi; dwErrCode
0x180011bb5  call    cs:__imp_SetLastError
0x180011bbb  mov     qword ptr [rdi+10h], 0
0x180011bc3  xor     edx, edx
0x180011bc5  xor     ecx, ecx
0x180011bc7  call    cs:__imp_CoRegisterServerShutdownDelay
0x180011bcd  test    eax, eax
0x180011bcf  jns     short loc_180011BDE
0x180011bd1  mov     rcx, [rsp+48h]; this
0x180011bd6  mov     r9d, eax; char *
0x180011bd9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180011bde  mov     rbx, [rdi+18h]
0x180011be2  mov     qword ptr [rdi+18h], 0
0x180011bea  test    rbx, rbx
0x180011bed  jz      short loc_180011C04
0x180011bef  mov     rcx, rbx
0x180011bf2  call    ??1?$svchost_module@UAggregatedDataPlatform@1Internal@Windows@winrt@@@details@wil@@QEAA@XZ; wil::details::svchost_module<winrt::Windows::Internal::AggregatedDataPlatform::AggregatedDataPlatform>::~svchost_module<winrt::Windows::Internal::AggregatedDataPlatform::AggregatedDataPlatform>(void)
0x180011bf7  mov     edx, 18h; unsigned __int64
0x180011bfc  mov     rcx, rbx; void *
0x180011bff  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180011c04  mov     r8d, ebp
0x180011c07  mov     edx, 1
0x180011c0c  mov     rcx, rdi
0x180011c0f  call    ?update_status@?$svchost_service@UAdpServiceTraits@ADPService@@UAggregatedDataPlatform@3Internal@Windows@winrt@@@wil@@AEAAXKK@Z; wil::svchost_service<ADPService::AdpServiceTraits,winrt::Windows::Internal::AggregatedDataPlatform::AggregatedDataPlatform>::update_status(ulong,ulong)
0x180011c14  nop
0x180011c15  add     rsp, 28h
0x180011c19  pop     rdi
0x180011c1a  pop     rsi
0x180011c1b  pop     rbp
0x180011c1c  pop     rbx
0x180011c1d  retn
0x180011c1e  mov     rcx, [rsp+48h]; this
0x180011c23  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180011c2a  mov     edx, 0A0Bh; void *
0x180011c2f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
