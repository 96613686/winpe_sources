# CKeyboardHandler::CKeyboardHandler(void)

- ea: `0x180005e38`
- end: `0x180005fa8`
- name: `??0CKeyboardHandler@@IEAA@XZ`
- size: `368`
- prototype: `CKeyboardHandler *__fastcall(CKeyboardHandler *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x1800072bc`

## callees

- `0x180005e38`
- `0x180009d6c`
- `0x18000a374`
- `0x18000a940`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180005e91`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180005ee9`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180005f3a`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180005e91`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180005ee9`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180005f3a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005ed2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005f22`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005ed2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005f22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005ea3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005eb2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005ef7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005f06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005f48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005ea3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005eb2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005ef7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005f06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005f48`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005ebd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005f11`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005ebd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005f11`

## pseudocode

```c
CKeyboardHandler *__fastcall CKeyboardHandler::CKeyboardHandler(CKeyboardHandler *this)
{
  void *v2; // rdx
  HANDLE Event; // rbp
  unsigned int v4; // r8d
  const char *v5; // r9
  void *v6; // rdi
  DWORD LastError; // esi
  unsigned int v8; // r8d
  const char *v9; // r9
  void *v10; // rdx
  HANDLE v11; // rbp
  unsigned int v12; // r8d
  const char *v13; // r9
  void *v14; // rdi
  DWORD v15; // esi
  unsigned int v16; // r8d
  const char *v17; // r9
  void *v18; // rdx
  HANDLE v19; // rdi
  unsigned int v20; // r8d
  const char *v21; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  *(_QWORD *)this = &CKeyboardHandler::`vftable';
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  Event = CreateEventExW(0, 0, 0, 0x1F0003u);
  if ( !Event )
    wil::details::in1diag3::Throw_GetLastError(retaddr, v2, v4, v5);
  GetLastError();
  v6 = (void *)*((_QWORD *)this + 2);
  if ( v6 )
  {
    LastError = GetLastError();
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v8, v9);
    SetLastError(LastError);
  }
  *((_QWORD *)this + 2) = Event;
  v11 = CreateEventExW(0, 0, 0, 0x1F0003u);
  if ( !v11 )
    wil::details::in1diag3::Throw_GetLastError(retaddr, v10, v12, v13);
  GetLastError();
  v14 = (void *)*((_QWORD *)this + 3);
  if ( v14 )
  {
    v15 = GetLastError();
    if ( !CloseHandle(v14) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v16, v17);
    SetLastError(v15);
  }
  *((_QWORD *)this + 3) = v11;
  v19 = CreateEventExW(0, 0, 1u, 0x1F0003u);
  if ( !v19 )
    wil::details::in1diag3::Throw_GetLastError(retaddr, v18, v20, v21);
  GetLastError();
  _reset___shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__QEAAXPEAX_Z(
    (char *)this + 32,
    v19);
  return this;
}

```

## disassembly

```asm
0x180005e38  mov     [rsp+arg_8], rbx
0x180005e3d  mov     [rsp+arg_10], rbp
0x180005e42  mov     [rsp+arg_0], rcx
0x180005e47  push    rsi
0x180005e48  push    rdi
0x180005e49  push    r14
0x180005e4b  sub     rsp, 20h
0x180005e4f  mov     rbx, rcx
0x180005e52  lea     rax, ??_7CKeyboardHandler@@6B@; const CKeyboardHandler::`vftable'
0x180005e59  mov     [rcx], rax
0x180005e5c  mov     qword ptr [rcx+8], 0
0x180005e64  mov     qword ptr [rcx+10h], 0
0x180005e6c  mov     qword ptr [rcx+18h], 0
0x180005e74  mov     qword ptr [rcx+20h], 0
0x180005e7c  mov     qword ptr [rcx+28h], 0
0x180005e84  mov     r9d, 1F0003h; dwDesiredAccess
0x180005e8a  xor     r8d, r8d; dwFlags
0x180005e8d  xor     edx, edx; lpName
0x180005e8f  xor     ecx, ecx; lpEventAttributes
0x180005e91  call    cs:__imp_CreateEventExW
0x180005e97  mov     rbp, rax
0x180005e9a  test    rax, rax
0x180005e9d  jz      loc_180005F7C
0x180005ea3  call    cs:__imp_GetLastError
0x180005ea9  mov     rdi, [rbx+10h]
0x180005ead  test    rdi, rdi
0x180005eb0  jz      short loc_180005ED8
0x180005eb2  call    cs:__imp_GetLastError
0x180005eb8  mov     esi, eax
0x180005eba  mov     rcx, rdi; hObject
0x180005ebd  call    cs:__imp_CloseHandle
0x180005ec3  mov     rcx, [rsp+38h]; this
0x180005ec8  test    eax, eax
0x180005eca  jz      loc_180005F87
0x180005ed0  mov     ecx, esi; dwErrCode
0x180005ed2  call    cs:__imp_SetLastError
0x180005ed8  mov     [rbx+10h], rbp
0x180005edc  mov     r9d, 1F0003h; dwDesiredAccess
0x180005ee2  xor     r8d, r8d; dwFlags
0x180005ee5  xor     edx, edx; lpName
0x180005ee7  xor     ecx, ecx; lpEventAttributes
0x180005ee9  call    cs:__imp_CreateEventExW
0x180005eef  mov     rbp, rax
0x180005ef2  test    rax, rax
0x180005ef5  jz      short loc_180005F71
0x180005ef7  call    cs:__imp_GetLastError
0x180005efd  mov     rdi, [rbx+18h]
0x180005f01  test    rdi, rdi
0x180005f04  jz      short loc_180005F28
0x180005f06  call    cs:__imp_GetLastError
0x180005f0c  mov     esi, eax
0x180005f0e  mov     rcx, rdi; hObject
0x180005f11  call    cs:__imp_CloseHandle
0x180005f17  mov     rcx, [rsp+38h]; this
0x180005f1c  test    eax, eax
0x180005f1e  jz      short loc_180005F92
0x180005f20  mov     ecx, esi; dwErrCode
0x180005f22  call    cs:__imp_SetLastError
0x180005f28  mov     [rbx+18h], rbp
0x180005f2c  xor     edx, edx; lpName
0x180005f2e  xor     ecx, ecx; lpEventAttributes
0x180005f30  mov     r9d, 1F0003h; dwDesiredAccess
0x180005f36  lea     r8d, [rdx+1]; dwFlags
0x180005f3a  call    cs:__imp_CreateEventExW
0x180005f40  mov     rdi, rax
0x180005f43  test    rax, rax
0x180005f46  jz      short loc_180005F9D
0x180005f48  call    cs:__imp_GetLastError
0x180005f4e  mov     rdx, rdi
0x180005f51  lea     rcx, [rbx+20h]
0x180005f55  call    ?reset@?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@QEAAXPEAX@Z
0x180005f5a  nop
0x180005f5b  mov     rax, rbx
0x180005f5e  mov     rbx, [rsp+38h+arg_8]
0x180005f63  mov     rbp, [rsp+38h+arg_10]
0x180005f68  add     rsp, 20h
0x180005f6c  pop     r14
0x180005f6e  pop     rdi
0x180005f6f  pop     rsi
0x180005f70  retn
0x180005f71  mov     rcx, [rsp+38h]; this
0x180005f76  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180005f7c  mov     rcx, [rsp+38h]; this
0x180005f81  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180005f87  mov     edx, 0A0Bh; void *
0x180005f8c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005f92  mov     edx, 0A0Bh; void *
0x180005f97  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005f9d  mov     rcx, [rsp+38h]; this
0x180005fa2  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
