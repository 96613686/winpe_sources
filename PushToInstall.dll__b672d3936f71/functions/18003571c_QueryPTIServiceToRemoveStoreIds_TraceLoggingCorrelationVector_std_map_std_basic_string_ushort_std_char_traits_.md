# QueryPTIServiceToRemoveStoreIds(TraceLoggingCorrelationVector *,std::map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,long,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,long>>> const &)

- ea: `0x18003571c`
- end: `0x1800357d0`
- name: `?QueryPTIServiceToRemoveStoreIds@@YAXPEAVTraceLoggingCorrelationVector@@AEBV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@JU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@J@std@@@2@@std@@@Z`
- size: `180`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, installer_update`

## callers

- `0x180032ac0`
- `0x180032cfc`

## callees

- `0x180030a68`
- `0x1800350d0`
- `0x1800354bc`
- `0x18003571c`
- `0x18004f010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180035751`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180035751`

## string_xrefs

- `0x1800357bb`: `onecoreuap\enduser\winstore\pushtoinstall\lib\nexus.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct TraceLoggingCorrelationVector *__fastcall QueryPTIServiceToRemoveStoreIds(struct HttpRequest *a1, __int64 ***a2)
{
  const char *v3; // r9
  struct TraceLoggingCorrelationVector *result; // rax
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v6; // [rsp+40h] [rbp+18h] BYREF
  __int64 v7; // [rsp+48h] [rbp+20h] BYREF

  CreatePTIRemoveRequestBody(&v6, a2);
  if ( !InitOnceExecuteOnce(&InitOnce, (PINIT_ONCE_FN)Nexus::InitializeOnce, &g_nexus, 0) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x49,
      (int)"onecoreuap\\enduser\\winstore\\pushtoinstall\\lib\\nexus.cpp",
      v3);
  result = MakePostRequest(
             (struct TraceLoggingCorrelationVector *)&v7,
             a1,
             (const unsigned __int16 *)qword_180066510,
             (__int64)&v6);
  if ( v7 )
    result = (struct TraceLoggingCorrelationVector *)(*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v7 + 192LL))(
                                                       v7,
                                                       1);
  if ( v6 )
    return (struct TraceLoggingCorrelationVector *)(*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v6 + 192LL))(
                                                     v6,
                                                     1);
  return result;
}

```

## disassembly

```asm
0x18003571c  mov     [rsp+arg_0], rbx
0x180035721  push    rdi
0x180035722  sub     rsp, 20h
0x180035726  mov     rdi, rcx
0x180035729  lea     rcx, [rsp+28h+arg_10]
0x18003572e  call    ?CreatePTIRemoveRequestBody@@YA?AVvalue@json@web@@AEBV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@JU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@J@std@@@2@@std@@@Z; CreatePTIRemoveRequestBody(std::map<std::wstring,long> const &)
0x180035733  nop
0x180035734  mov     rbx, [rsp+28h]
0x180035739  xor     r9d, r9d; Context
0x18003573c  lea     r8, ?g_nexus@@3VNexus@@A; Parameter
0x180035743  lea     rdx, ?InitializeOnce@Nexus@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18003574a  lea     rcx, InitOnce; InitOnce
0x180035751  call    cs:__imp_InitOnceExecuteOnce
0x180035757  test    eax, eax
0x180035759  jz      short loc_1800357BB
0x18003575b  lea     r9, [rsp+28h+arg_10]
0x180035760  lea     r8, qword_180066510
0x180035767  mov     rdx, rdi
0x18003576a  lea     rcx, [rsp+28h+arg_18]
0x18003576f  call    ?MakePostRequest@@YA?AVvalue@json@web@@PEAVTraceLoggingCorrelationVector@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV123@@Z; MakePostRequest(TraceLoggingCorrelationVector *,std::wstring const &,web::json::value const &)
0x180035774  mov     rcx, [rsp+28h+arg_18]
0x180035779  mov     ebx, 1
0x18003577e  test    rcx, rcx
0x180035781  jz      short loc_180035795
0x180035783  mov     rax, [rcx]
0x180035786  mov     edx, ebx
0x180035788  mov     rax, [rax+0C0h]
0x18003578f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035794  nop
0x180035795  mov     rcx, [rsp+28h+arg_10]
0x18003579a  test    rcx, rcx
0x18003579d  jz      short loc_1800357B0
0x18003579f  mov     rax, [rcx]
0x1800357a2  mov     edx, ebx
0x1800357a4  mov     rax, [rax+0C0h]
0x1800357ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800357b0  mov     rbx, [rsp+28h+arg_0]
0x1800357b5  add     rsp, 20h
0x1800357b9  pop     rdi
0x1800357ba  retn
0x1800357bb  lea     r8, aOnecoreuapEndu_4; "onecoreuap\\enduser\\winstore\\pushtoin"...
0x1800357c2  mov     edx, 49h ; 'I'; void *
0x1800357c7  mov     rcx, rbx; this
0x1800357ca  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
