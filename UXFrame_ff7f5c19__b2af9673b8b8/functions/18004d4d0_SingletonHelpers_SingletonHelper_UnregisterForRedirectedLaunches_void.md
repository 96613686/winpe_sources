# SingletonHelpers::SingletonHelper::UnregisterForRedirectedLaunches(void)

- ea: `0x18004d4d0`
- end: `0x18004d5a2`
- name: `?UnregisterForRedirectedLaunches@SingletonHelper@SingletonHelpers@@QEAAXXZ`
- size: `210`
- prototype: `void __fastcall(SingletonHelpers::SingletonHelper *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004cda8`
- `0x18004d0b8`

## callees

- `0x18000f838`
- `0x18001049c`
- `0x18001d814`
- `0x18002c4c0`
- `0x18004d4d0`
- `0x18004fd14`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004d506`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004d506`

## string_xrefs

- `0x18004d4f1`: `ShellCommon\Internal\Shell\Inc\SingletonHelpers.h`
- `0x18004d515`: `ShellCommon\Internal\Shell\Inc\SingletonHelpers.h`

## pseudocode

```c
void __fastcall SingletonHelpers::SingletonHelper::UnregisterForRedirectedLaunches(
        SingletonHelpers::SingletonHelper *this,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  _QWORD *v4; // rsi
  int v6; // ebx
  const char *v7; // r9
  _QWORD *v8; // rax
  _QWORD *v9; // rcx
  const char *v10; // r9
  _BYTE v11[16]; // [rsp+20h] [rbp-28h] BYREF
  _BYTE v12[24]; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  _QWORD *v14; // [rsp+50h] [rbp+8h] BYREF

  v4 = (_QWORD *)((char *)this + 112);
  if ( !*((_QWORD *)this + 14) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x1F6,
      (unsigned int)"ShellCommon\\Internal\\Shell\\Inc\\SingletonHelpers.h",
      a4);
  v6 = *((_DWORD *)this + 30);
  if ( v6 != GetCurrentThreadId() )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x1F8,
      (unsigned int)"ShellCommon\\Internal\\Shell\\Inc\\SingletonHelpers.h",
      v7);
  v8 = (_QWORD *)((char *)this + 40);
  if ( *((_QWORD *)this + 8) > 7u )
    v8 = (_QWORD *)*v8;
  v14 = v8;
  wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(v11, &v14);
  v9 = (_QWORD *)((char *)this + 8);
  if ( *((_QWORD *)this + 4) > 7u )
    v9 = (_QWORD *)*v9;
  v14 = v9;
  wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(v12, &v14);
  SingletonHelpers::details::ClearDataForSingletonInstance(v4, (__int64)v12, (__int64)v11, v10);
  FlowEndpointBase::Uninitialize((SingletonHelpers::SingletonHelper *)((char *)this + 128));
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    v4,
    0);
}

```

## disassembly

```asm
0x18004d4d0  mov     [rsp+arg_8], rbx
0x18004d4d5  mov     [rsp+arg_10], rsi
0x18004d4da  push    rdi
0x18004d4db  sub     rsp, 40h
0x18004d4df  lea     rsi, [rcx+70h]
0x18004d4e3  mov     rdi, rcx
0x18004d4e6  cmp     qword ptr [rsi], 0
0x18004d4ea  jnz     short loc_18004D503
0x18004d4ec  mov     rcx, [rsp+48h]; this
0x18004d4f1  lea     r8, aShellcommonInt; "ShellCommon\\Internal\\Shell\\Inc\\Sing"...
0x18004d4f8  mov     edx, 1F6h; void *
0x18004d4fd  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18004d503  mov     ebx, [rcx+78h]
0x18004d506  call    cs:__imp_GetCurrentThreadId
0x18004d50c  cmp     ebx, eax
0x18004d50e  jz      short loc_18004D527
0x18004d510  mov     rcx, [rsp+48h]; this
0x18004d515  lea     r8, aShellcommonInt; "ShellCommon\\Internal\\Shell\\Inc\\Sing"...
0x18004d51c  mov     edx, 1F8h; void *
0x18004d521  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18004d527  lea     rax, [rdi+28h]
0x18004d52b  cmp     qword ptr [rax+18h], 7
0x18004d530  jbe     short loc_18004D535
0x18004d532  mov     rax, [rax]
0x18004d535  lea     rdx, [rsp+48h+arg_0]
0x18004d53a  mov     [rsp+48h+arg_0], rax
0x18004d53f  lea     rcx, [rsp+48h+var_28]
0x18004d544  call    ??$?0PEA_W$0A@@?$basic_zstring_view@_W@wil@@QEAA@$$QEAPEA_W@Z; wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(wchar_t * &&)
0x18004d549  lea     rcx, [rdi+8]
0x18004d54d  cmp     qword ptr [rcx+18h], 7
0x18004d552  jbe     short loc_18004D557
0x18004d554  mov     rcx, [rcx]
0x18004d557  mov     [rsp+48h+arg_0], rcx
0x18004d55c  lea     rdx, [rsp+48h+arg_0]
0x18004d561  lea     rcx, [rsp+48h+var_18]
0x18004d566  call    ??$?0PEA_W$0A@@?$basic_zstring_view@_W@wil@@QEAA@$$QEAPEA_W@Z; wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(wchar_t * &&)
0x18004d56b  lea     r8, [rsp+48h+var_28]
0x18004d570  mov     rcx, rsi
0x18004d573  lea     rdx, [rsp+48h+var_18]
0x18004d578  call    ?ClearDataForSingletonInstance@details@SingletonHelpers@@YAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_zstring_view@_W@4@1@Z
0x18004d57d  lea     rcx, [rdi+80h]; this
0x18004d584  call    ?Uninitialize@FlowEndpointBase@@QEAAXXZ; FlowEndpointBase::Uninitialize(void)
0x18004d589  xor     edx, edx
0x18004d58b  mov     rcx, rsi
0x18004d58e  mov     rbx, [rsp+48h+arg_8]
0x18004d593  mov     rsi, [rsp+48h+arg_10]
0x18004d598  add     rsp, 40h
0x18004d59c  pop     rdi
0x18004d59d  jmp     ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
```
