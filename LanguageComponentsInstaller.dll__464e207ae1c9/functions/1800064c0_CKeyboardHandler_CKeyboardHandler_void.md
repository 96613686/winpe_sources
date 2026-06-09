# CKeyboardHandler::~CKeyboardHandler(void)

- ea: `0x1800064c0`
- end: `0x180006639`
- name: `??1CKeyboardHandler@@UEAA@XZ`
- size: `377`
- prototype: `void __fastcall(CKeyboardHandler *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800069b0`

## callees

- `0x1800064c0`
- `0x1800074c4`
- `0x18000a374`
- `0x18000a390`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180006525`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180006525`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180006506`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180006506`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800065a3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800065bb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800065a3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800065bb`

## string_xrefs

- `0x180006611`: `onecore\shell\cpls\internationalsettings\languagecomponentsinstaller\dll\keyboardhandler.cpp`

## pseudocode

```c
void __fastcall CKeyboardHandler::~CKeyboardHandler(CKeyboardHandler *this)
{
  __int64 *v2; // rsi
  __int64 v3; // rcx
  unsigned int v4; // r8d
  const char *v5; // r9
  DWORD v6; // eax
  unsigned int v7; // r8d
  const char *v8; // r9
  char v9; // al
  volatile signed __int32 *v10; // rdi
  void *v11; // rcx
  unsigned int v12; // r8d
  const char *v13; // r9
  void *v14; // rcx
  unsigned int v15; // r8d
  const char *v16; // r9
  __int64 v17; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  *(_QWORD *)this = &CKeyboardHandler::`vftable';
  v2 = (__int64 *)((char *)this + 8);
  v3 = *((_QWORD *)this + 1);
  if ( v3 )
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v3 + 72LL))(v3, *((_QWORD *)this + 6));
  if ( !SetEvent(*((HANDLE *)this + 2)) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA01, v4, v5);
  v6 = WaitForSingleObjectEx(*((HANDLE *)this + 3), 0xEA60u, 0);
  if ( v6 == 258 )
  {
    v9 = 1;
  }
  else
  {
    if ( v6 )
      wil::details::in1diag3::FailFast_Unexpected(retaddr, (void *)0xB0F, v7, v8);
    v9 = 0;
  }
  if ( v9 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x23,
      (unsigned int)"onecore\\shell\\cpls\\internationalsettings\\languagecomponentsinstaller\\dll\\keyboardhandler.cpp",
      v8);
  v10 = (volatile signed __int32 *)*((_QWORD *)this + 5);
  if ( v10 )
  {
    if ( _InterlockedExchangeAdd(v10 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
      if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
    }
  }
  v11 = (void *)*((_QWORD *)this + 3);
  if ( v11 && !CloseHandle(v11) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v12, v13);
  v14 = (void *)*((_QWORD *)this + 2);
  if ( v14 && !CloseHandle(v14) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v15, v16);
  v17 = *v2;
  if ( *v2 )
  {
    *v2 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  }
}

```

## disassembly

```asm
0x1800064c0  mov     [rsp+arg_10], rbx
0x1800064c5  mov     [rsp+arg_18], rsi
0x1800064ca  mov     [rsp+arg_0], rcx
0x1800064cf  push    rdi
0x1800064d0  sub     rsp, 20h
0x1800064d4  mov     rbx, rcx
0x1800064d7  lea     rax, ??_7CKeyboardHandler@@6B@; const CKeyboardHandler::`vftable'
0x1800064de  mov     [rcx], rax
0x1800064e1  lea     rsi, [rcx+8]
0x1800064e5  mov     [rsp+28h+arg_8], rsi
0x1800064ea  mov     rcx, [rsi]
0x1800064ed  test    rcx, rcx
0x1800064f0  jz      short loc_180006502
0x1800064f2  mov     rax, [rcx]
0x1800064f5  mov     rdx, [rbx+30h]
0x1800064f9  mov     rax, [rax+48h]
0x1800064fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006502  mov     rcx, [rbx+10h]; hEvent
0x180006506  call    cs:__imp_SetEvent
0x18000650c  mov     rcx, [rsp+28h]; this
0x180006511  test    eax, eax
0x180006513  jz      loc_1800065F6
0x180006519  xor     r8d, r8d; bAlertable
0x18000651c  mov     edx, 0EA60h; dwMilliseconds
0x180006521  mov     rcx, [rbx+18h]; hHandle
0x180006525  call    cs:__imp_WaitForSingleObjectEx
0x18000652b  cmp     eax, 102h
0x180006530  jz      short loc_18000653E
0x180006532  test    eax, eax
0x180006534  jnz     loc_180006601
0x18000653a  xor     al, al
0x18000653c  jmp     short loc_180006540
0x18000653e  mov     al, 1
0x180006540  mov     rcx, [rsp+28h]; this
0x180006545  test    al, al
0x180006547  jnz     loc_180006611
0x18000654d  jmp     short loc_180006559
0x18000654f  mov     rbx, [rsp+28h+arg_0]
0x180006554  mov     rsi, [rsp+28h+arg_8]
0x180006559  mov     rdi, [rbx+28h]
0x18000655d  test    rdi, rdi
0x180006560  jz      short loc_18000659A
0x180006562  or      eax, 0FFFFFFFFh
0x180006565  lock xadd [rdi+8], eax
0x18000656a  cmp     eax, 1
0x18000656d  jnz     short loc_18000659A
0x18000656f  mov     rax, [rdi]
0x180006572  mov     rcx, rdi
0x180006575  mov     rax, [rax]
0x180006578  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000657d  or      eax, 0FFFFFFFFh
0x180006580  lock xadd [rdi+0Ch], eax
0x180006585  cmp     eax, 1
0x180006588  jnz     short loc_18000659A
0x18000658a  mov     rax, [rdi]
0x18000658d  mov     rcx, rdi
0x180006590  mov     rax, [rax+8]
0x180006594  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006599  nop
0x18000659a  mov     rcx, [rbx+18h]; hObject
0x18000659e  test    rcx, rcx
0x1800065a1  jz      short loc_1800065B2
0x1800065a3  call    cs:__imp_CloseHandle
0x1800065a9  mov     rcx, [rsp+28h]; this
0x1800065ae  test    eax, eax
0x1800065b0  jz      short loc_180006623
0x1800065b2  mov     rcx, [rbx+10h]; hObject
0x1800065b6  test    rcx, rcx
0x1800065b9  jz      short loc_1800065CA
0x1800065bb  call    cs:__imp_CloseHandle
0x1800065c1  mov     rcx, [rsp+28h]; this
0x1800065c6  test    eax, eax
0x1800065c8  jz      short loc_18000662E
0x1800065ca  mov     rcx, [rsi]
0x1800065cd  test    rcx, rcx
0x1800065d0  jz      short loc_1800065E6
0x1800065d2  mov     qword ptr [rsi], 0
0x1800065d9  mov     rax, [rcx]
0x1800065dc  mov     rax, [rax+10h]
0x1800065e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065e5  nop
0x1800065e6  mov     rbx, [rsp+28h+arg_10]
0x1800065eb  mov     rsi, [rsp+28h+arg_18]
0x1800065f0  add     rsp, 20h
0x1800065f4  pop     rdi
0x1800065f5  retn
0x1800065f6  mov     edx, 0A01h; void *
0x1800065fb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006601  mov     rcx, [rsp+28h]; this
0x180006606  mov     edx, 0B0Fh; void *
0x18000660b  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180006611  lea     r8, aOnecoreShellCp_5; "onecore\\shell\\cpls\\internationalsett"...
0x180006618  mov     edx, 23h ; '#'; void *
0x18000661d  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180006623  mov     edx, 0A0Bh; void *
0x180006628  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000662e  mov     edx, 0A0Bh; void *
0x180006633  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
