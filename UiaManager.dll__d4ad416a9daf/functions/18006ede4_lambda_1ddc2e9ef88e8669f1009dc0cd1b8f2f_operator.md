# _lambda_1ddc2e9ef88e8669f1009dc0cd1b8f2f_::operator()

- ea: `0x18006ede4`
- end: `0x18006ee8a`
- name: `_lambda_1ddc2e9ef88e8669f1009dc0cd1b8f2f_::operator()`
- size: `166`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x18006f930`

## callees

- `0x1800054c0`
- `0x180006edc`
- `0x18000af78`
- `0x18006ede4`
- `0x180091010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006ee12`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006ee12`

## string_xrefs

- `0x18006ee31`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagerimpl.cpp`
- `0x18006ee4a`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagerimpl.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall lambda_1ddc2e9ef88e8669f1009dc0cd1b8f2f_::operator()(_QWORD *a1)
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
      (void *)0xC4,
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
0x18006ede4  mov     [rsp+arg_0], rbx
0x18006ede9  mov     [rsp+arg_8], rsi
0x18006edee  push    rdi; int
0x18006edef  sub     rsp, 20h
0x18006edf3  mov     rbx, [rcx]
0x18006edf6  mov     rdi, rcx
0x18006edf9  mov     rax, [rbx]
0x18006edfc  mov     rsi, [rax+18h]
0x18006ee00  mov     rax, [rcx+8]
0x18006ee04  test    rax, rax
0x18006ee07  jz      short loc_18006EE0E
0x18006ee09  mov     rcx, [rax]
0x18006ee0c  jmp     short loc_18006EE10
0x18006ee0e  xor     ecx, ecx; string
0x18006ee10  xor     edx, edx; length
0x18006ee12  call    cs:__imp_WindowsGetStringRawBuffer
0x18006ee18  mov     rdx, rax
0x18006ee1b  mov     rcx, rbx
0x18006ee1e  mov     rax, rsi
0x18006ee21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ee26  mov     ebx, eax
0x18006ee28  test    eax, eax
0x18006ee2a  jns     short loc_18006EE60
0x18006ee2c  mov     rcx, [rsp+28h]; this
0x18006ee31  lea     r8, aOnecoreWindows_0; "onecore\\windows\\accessibletech\\uiama"...
0x18006ee38  mov     r9d, eax; char *
0x18006ee3b  mov     edx, 0C4h; void *
0x18006ee40  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006ee45  mov     rcx, [rsp+28h]; this
0x18006ee4a  lea     r8, aOnecoreWindows_0; "onecore\\windows\\accessibletech\\uiama"...
0x18006ee51  mov     r9d, ebx; char *
0x18006ee54  mov     edx, 2Ah ; '*'; void *
0x18006ee59  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006ee5e  jmp     short loc_18006EE62
0x18006ee60  xor     ebx, ebx
0x18006ee62  add     rdi, 18h
0x18006ee66  movsxd  rcx, ebx
0x18006ee69  sar     rcx, 3Fh
0x18006ee6d  and     ecx, 10h
0x18006ee70  add     rcx, rdi
0x18006ee73  call    ?SetEvent@?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEBAXXZ
0x18006ee78  mov     rsi, [rsp+28h+arg_8]
0x18006ee7d  mov     eax, ebx
0x18006ee7f  mov     rbx, [rsp+28h+arg_0]
0x18006ee84  add     rsp, 20h
0x18006ee88  pop     rdi
0x18006ee89  retn
```
