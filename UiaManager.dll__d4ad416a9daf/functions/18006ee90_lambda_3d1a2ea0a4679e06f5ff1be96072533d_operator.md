# _lambda_3d1a2ea0a4679e06f5ff1be96072533d_::operator()

- ea: `0x18006ee90`
- end: `0x18006ef36`
- name: `_lambda_3d1a2ea0a4679e06f5ff1be96072533d_::operator()`
- size: `166`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x18006f960`

## callees

- `0x1800054c0`
- `0x180006edc`
- `0x18000af78`
- `0x18006ee90`
- `0x180091010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006eebe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006eebe`

## string_xrefs

- `0x18006eedd`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagerimpl.cpp`
- `0x18006eef6`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagerimpl.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall lambda_3d1a2ea0a4679e06f5ff1be96072533d_::operator()(_QWORD *a1)
{
  __int64 v1; // rbx
  __int64 (__fastcall *v3)(__int64, PCWSTR); // rsi
  HSTRING *v4; // rax
  HSTRING v5; // rcx
  PCWSTR StringRawBuffer; // rax
  int v7; // eax
  int v8; // ebx
  int v10; // [rsp+20h] [rbp-8h]
  int v11; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v1 = *a1;
  v3 = *(__int64 (__fastcall **)(__int64, PCWSTR))(*(_QWORD *)*a1 + 24LL);
  v4 = (HSTRING *)a1[1];
  if ( v4 )
    v5 = *v4;
  else
    v5 = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(v5, 0);
  v7 = v3(v1, StringRawBuffer);
  v8 = v7;
  if ( v7 >= 0 )
  {
    v8 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1BE,
      (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagerimpl.cpp",
      (const char *)(unsigned int)v7,
      v10);
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x2A,
      (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagerimpl.cpp",
      (const char *)(unsigned int)v8,
      v11);
  }
  _SetEvent___event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil__QEBAXXZ((char *)a1 + ((v8 >> 31) & 0x10) + 24);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18006ee90  mov     [rsp+arg_0], rbx
0x18006ee95  mov     [rsp+arg_8], rsi
0x18006ee9a  push    rdi; int
0x18006ee9b  sub     rsp, 20h
0x18006ee9f  mov     rbx, [rcx]
0x18006eea2  mov     rdi, rcx
0x18006eea5  mov     rax, [rbx]
0x18006eea8  mov     rsi, [rax+18h]
0x18006eeac  mov     rax, [rcx+8]
0x18006eeb0  test    rax, rax
0x18006eeb3  jz      short loc_18006EEBA
0x18006eeb5  mov     rcx, [rax]
0x18006eeb8  jmp     short loc_18006EEBC
0x18006eeba  xor     ecx, ecx; string
0x18006eebc  xor     edx, edx; length
0x18006eebe  call    cs:__imp_WindowsGetStringRawBuffer
0x18006eec4  mov     rdx, rax
0x18006eec7  mov     rcx, rbx
0x18006eeca  mov     rax, rsi
0x18006eecd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006eed2  mov     ebx, eax
0x18006eed4  test    eax, eax
0x18006eed6  jns     short loc_18006EF0C
0x18006eed8  mov     rcx, [rsp+28h]; this
0x18006eedd  lea     r8, aOnecoreWindows_0; "onecore\\windows\\accessibletech\\uiama"...
0x18006eee4  mov     r9d, eax; char *
0x18006eee7  mov     edx, 1BEh; void *
0x18006eeec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006eef1  mov     rcx, [rsp+28h]; this
0x18006eef6  lea     r8, aOnecoreWindows_0; "onecore\\windows\\accessibletech\\uiama"...
0x18006eefd  mov     r9d, ebx; char *
0x18006ef00  mov     edx, 2Ah ; '*'; void *
0x18006ef05  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006ef0a  jmp     short loc_18006EF0E
0x18006ef0c  xor     ebx, ebx
0x18006ef0e  add     rdi, 18h
0x18006ef12  movsxd  rcx, ebx
0x18006ef15  sar     rcx, 3Fh
0x18006ef19  and     ecx, 10h
0x18006ef1c  add     rcx, rdi
0x18006ef1f  call    ?SetEvent@?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEBAXXZ
0x18006ef24  mov     rsi, [rsp+28h+arg_8]
0x18006ef29  mov     eax, ebx
0x18006ef2b  mov     rbx, [rsp+28h+arg_0]
0x18006ef30  add     rsp, 20h
0x18006ef34  pop     rdi
0x18006ef35  retn
```
