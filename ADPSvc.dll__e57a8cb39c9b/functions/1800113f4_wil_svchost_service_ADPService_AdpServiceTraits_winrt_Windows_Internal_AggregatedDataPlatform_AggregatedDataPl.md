# wil::svchost_service<ADPService::AdpServiceTraits,winrt::Windows::Internal::AggregatedDataPlatform::AggregatedDataPlatform>::~svchost_service<ADPService::AdpServiceTraits,winrt::Windows::Internal::AggregatedDataPlatform::AggregatedDataPlatform>(void)

- ea: `0x1800113f4`
- end: `0x180011463`
- name: `??1?$svchost_service@UAdpServiceTraits@ADPService@@UAggregatedDataPlatform@3Internal@Windows@winrt@@@wil@@QEAA@XZ`
- size: `111`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, service_task`

## callers

- `0x1800c96f0`

## callees

- `0x1800026f0`
- `0x18000771c`
- `0x1800112d0`
- `0x1800113f4`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011428`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011428`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x18001143b`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x18001143b`

## string_xrefs

- `0x180011451`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall wil::svchost_service<ADPService::AdpServiceTraits,winrt::Windows::Internal::AggregatedDataPlatform::AggregatedDataPlatform>::~svchost_service<ADPService::AdpServiceTraits,winrt::Windows::Internal::AggregatedDataPlatform::AggregatedDataPlatform>(
        _QWORD *a1)
{
  void *v1; // rdi
  void *v3; // rcx
  const char *v4; // r9
  void *v5; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v1 = (void *)a1[3];
  if ( v1 )
  {
    wil::details::svchost_module<winrt::Windows::Internal::AggregatedDataPlatform::AggregatedDataPlatform>::~svchost_module<winrt::Windows::Internal::AggregatedDataPlatform::AggregatedDataPlatform>((_QWORD *)a1[3]);
    operator delete(v1, 0x18u);
  }
  v3 = (void *)a1[2];
  if ( v3 && !CloseHandle(v3) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v4);
  v5 = (void *)a1[1];
  if ( v5 )
    UnregisterWait(v5);
}

```

## disassembly

```asm
0x1800113f4  mov     [rsp+arg_0], rbx
0x1800113f9  push    rdi
0x1800113fa  sub     rsp, 20h
0x1800113fe  mov     rdi, [rcx+18h]
0x180011402  mov     rbx, rcx
0x180011405  test    rdi, rdi
0x180011408  jz      short loc_18001141F
0x18001140a  mov     rcx, rdi
0x18001140d  call    ??1?$svchost_module@UAggregatedDataPlatform@1Internal@Windows@winrt@@@details@wil@@QEAA@XZ; wil::details::svchost_module<winrt::Windows::Internal::AggregatedDataPlatform::AggregatedDataPlatform>::~svchost_module<winrt::Windows::Internal::AggregatedDataPlatform::AggregatedDataPlatform>(void)
0x180011412  mov     edx, 18h; unsigned __int64
0x180011417  mov     rcx, rdi; void *
0x18001141a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001141f  mov     rcx, [rbx+10h]; hObject
0x180011423  test    rcx, rcx
0x180011426  jz      short loc_180011432
0x180011428  call    cs:__imp_CloseHandle
0x18001142e  test    eax, eax
0x180011430  jz      short loc_18001144C
0x180011432  mov     rcx, [rbx+8]; WaitHandle
0x180011436  test    rcx, rcx
0x180011439  jz      short loc_180011441
0x18001143b  call    cs:__imp_UnregisterWait
0x180011441  mov     rbx, [rsp+28h+arg_0]
0x180011446  add     rsp, 20h
0x18001144a  pop     rdi
0x18001144b  retn
0x18001144c  mov     rcx, [rsp+28h]; this
0x180011451  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180011458  mov     edx, 0A0Bh; void *
0x18001145d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
