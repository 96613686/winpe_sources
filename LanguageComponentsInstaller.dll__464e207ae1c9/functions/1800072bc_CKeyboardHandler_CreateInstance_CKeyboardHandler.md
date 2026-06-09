# CKeyboardHandler::CreateInstance(CKeyboardHandler * *)

- ea: `0x1800072bc`
- end: `0x18000738e`
- name: `?CreateInstance@CKeyboardHandler@@SAJPEAPEAV1@@Z`
- size: `210`
- prototype: `__int64 __fastcall(struct CKeyboardHandler **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180017e84`

## callees

- `0x180003588`
- `0x180005e38`
- `0x1800072bc`
- `0x180009284`
- `0x1800092a4`
- `0x18002a010`

## import_xrefs

- `SHCORE!__imp_SHQueueUserWorkItem` at `0x180007349`
- `SHCORE!__imp_SHQueueUserWorkItem` at `0x180007349`

## string_xrefs

- `0x18000730c`: `onecore\shell\cpls\internationalsettings\languagecomponentsinstaller\dll\keyboardhandler.cpp`
- `0x180007358`: `onecore\shell\cpls\internationalsettings\languagecomponentsinstaller\dll\keyboardhandler.cpp`

## pseudocode

```c
__int64 __fastcall CKeyboardHandler::CreateInstance(struct CKeyboardHandler **a1)
{
  CKeyboardHandler *v2; // rax
  CKeyboardHandler *v3; // rdi
  unsigned int LastError; // ebx
  const char *v6; // r9
  int v7; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  *a1 = 0;
  v2 = (CKeyboardHandler *)operator new(0x38u, (const struct std::nothrow_t *)std::nothrow);
  if ( v2 )
    v3 = CKeyboardHandler::CKeyboardHandler(v2);
  else
    v3 = 0;
  if ( !v3 )
  {
    LastError = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2D,
      (unsigned int)"onecore\\shell\\cpls\\internationalsettings\\languagecomponentsinstaller\\dll\\keyboardhandler.cpp",
      (const char *)0x8007000ELL,
      v7);
    return LastError;
  }
  if ( !(unsigned int)SHQueueUserWorkItem(CKeyboardHandler::CoreUIThreadProc, v3, 0, 0, 0, 0, 24) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x36,
                  (unsigned int)"onecore\\shell\\cpls\\internationalsettings\\languagecomponentsinstaller\\dll\\keyboardhandler.cpp",
                  v6);
    (**(void (__fastcall ***)(CKeyboardHandler *, __int64))v3)(v3, 1);
    return LastError;
  }
  *a1 = v3;
  return 0;
}

```

## disassembly

```asm
0x1800072bc  mov     [rsp+arg_8], rbx
0x1800072c1  push    rdi
0x1800072c2  sub     rsp, 50h
0x1800072c6  mov     rbx, rcx
0x1800072c9  mov     qword ptr [rcx], 0
0x1800072d0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800072d7  mov     ecx, 38h ; '8'; unsigned __int64
0x1800072dc  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800072e1  mov     [rsp+58h+var_18], rax
0x1800072e6  test    rax, rax
0x1800072e9  jz      short loc_1800072F8
0x1800072eb  mov     rcx, rax; this
0x1800072ee  call    ??0CKeyboardHandler@@IEAA@XZ; CKeyboardHandler::CKeyboardHandler(void)
0x1800072f3  mov     rdi, rax
0x1800072f6  jmp     short loc_1800072FA
0x1800072f8  xor     edi, edi
0x1800072fa  test    rdi, rdi
0x1800072fd  jnz     short loc_18000731F
0x1800072ff  mov     rcx, [rsp+58h]; this
0x180007304  mov     ebx, 8007000Eh
0x180007309  mov     r9d, ebx; char *
0x18000730c  lea     r8, aOnecoreShellCp_5; "onecore\\shell\\cpls\\internationalsett"...
0x180007313  lea     edx, [rdi+2Dh]; void *
0x180007316  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000731b  mov     eax, ebx
0x18000731d  jmp     short loc_180007383
0x18000731f  mov     [rsp+58h+var_28], 18h
0x180007327  mov     [rsp+58h+var_30], 0
0x180007330  mov     [rsp+58h+var_38], 0
0x180007339  xor     r9d, r9d
0x18000733c  xor     r8d, r8d
0x18000733f  mov     rdx, rdi
0x180007342  lea     rcx, ?CoreUIThreadProc@CKeyboardHandler@@CAKPEAX@Z; CKeyboardHandler::CoreUIThreadProc(void *)
0x180007349  call    cs:__imp_SHQueueUserWorkItem
0x18000734f  test    eax, eax
0x180007351  jnz     short loc_18000737E
0x180007353  mov     rcx, [rsp+58h]; this
0x180007358  lea     r8, aOnecoreShellCp_5; "onecore\\shell\\cpls\\internationalsett"...
0x18000735f  lea     edx, [rax+36h]; void *
0x180007362  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180007367  mov     ebx, eax
0x180007369  mov     rcx, [rdi]
0x18000736c  mov     rax, [rcx]
0x18000736f  mov     edx, 1
0x180007374  mov     rcx, rdi
0x180007377  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000737c  jmp     short loc_18000731B
0x18000737e  mov     [rbx], rdi
0x180007381  xor     eax, eax
0x180007383  mov     rbx, [rsp+58h+arg_8]
0x180007388  add     rsp, 50h
0x18000738c  pop     rdi
0x18000738d  retn
```
