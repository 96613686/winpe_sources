# PrintProcessLauncher::LaunchSplWoW64(void)

- ea: `0x1800329dc`
- end: `0x180032ab3`
- name: `?LaunchSplWoW64@PrintProcessLauncher@@QEAAXXZ`
- size: `215`
- prototype: `void __fastcall(HANDLE *this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180012c50`

## callees

- `0x18001255c`
- `0x180023264`
- `0x18002b28c`
- `0x180030cb0`
- `0x1800329dc`
- `0x180032abc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180032a35`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180032a72`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180032a35`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180032a72`

## string_xrefs

- `0x180032a45`: `SetThreadToken (medium token) failed!`
- `0x180032a82`: `SetThreadToken (revert) failed!`
- `0x180032a55`: `onecoreuap\printscan\print\printscanbroker\class\printprocesslauncher.cpp`
- `0x180032a92`: `onecoreuap\printscan\print\printscanbroker\class\printprocesslauncher.cpp`

## pseudocode

```c
void __fastcall PrintProcessLauncher::LaunchSplWoW64(HANDLE *this)
{
  PrintProcessLauncher *v2; // rax
  PrintProcessLauncher *v3; // rbx
  BOOL v4; // eax
  BOOL v5; // eax
  const char *v6; // [rsp+28h] [rbp-10h]
  const char *v7; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  char v9; // [rsp+40h] [rbp+8h] BYREF
  void **v10; // [rsp+48h] [rbp+10h]

  v10 = &PrintSupportUtility::`vftable';
  v2 = (PrintProcessLauncher *)TokenUtility::CreateUserTokenForSplWoW64(this, &v9, this + 1);
  v3 = v2;
  if ( this + 7 != (HANDLE *)v2 )
  {
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      this + 7,
      *(_QWORD *)v2);
    *(_QWORD *)v3 = 0;
  }
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v9);
  v4 = SetThreadToken(0, this[7]);
  wil::details::in1diag3::Throw_GetLastErrorIfMsg(
    retaddr,
    (void *)0x12,
    (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\printprocesslauncher.cpp",
    (const char *)!v4,
    (bool)"SetThreadToken (medium token) failed!",
    v6);
  PrintProcessLauncher::_CreateSplWoW64Process((PrintProcessLauncher *)this);
  v5 = SetThreadToken(0, 0);
  wil::details::in1diag3::Throw_GetLastErrorIfMsg(
    retaddr,
    (void *)0x14,
    (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\printprocesslauncher.cpp",
    (const char *)!v5,
    (bool)"SetThreadToken (revert) failed!",
    v7);
}

```

## disassembly

```asm
0x1800329dc  mov     r11, rsp
0x1800329df  mov     [r11+18h], rbx
0x1800329e3  mov     [r11+20h], rsi
0x1800329e7  push    rdi
0x1800329e8  sub     rsp, 30h
0x1800329ec  mov     rsi, rcx
0x1800329ef  lea     rax, ??_7PrintSupportUtility@@6B@; const PrintSupportUtility::`vftable'
0x1800329f6  mov     [r11+10h], rax
0x1800329fa  lea     r8, [rcx+8]
0x1800329fe  lea     rdx, [r11+8]
0x180032a02  call    ?CreateUserTokenForSplWoW64@TokenUtility@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; TokenUtility::CreateUserTokenForSplWoW64(std::wstring const &)
0x180032a07  mov     rbx, rax
0x180032a0a  lea     rdi, [rsi+38h]
0x180032a0e  cmp     rdi, rax
0x180032a11  jz      short loc_180032A25
0x180032a13  mov     rdx, [rax]
0x180032a16  mov     rcx, rdi
0x180032a19  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180032a1e  mov     qword ptr [rbx], 0
0x180032a25  lea     rcx, [rsp+38h+arg_0]
0x180032a2a  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180032a2f  nop
0x180032a30  mov     rdx, [rdi]; Token
0x180032a33  xor     ecx, ecx; Thread
0x180032a35  call    cs:__imp_SetThreadToken
0x180032a3b  test    eax, eax
0x180032a3d  setz    al
0x180032a40  mov     rcx, [rsp+38h]; this
0x180032a45  lea     rdx, aSetthreadtoken; "SetThreadToken (medium token) failed!"
0x180032a4c  mov     qword ptr [rsp+38h+var_18], rdx; bool
0x180032a51  movzx   r9d, al; char *
0x180032a55  lea     r8, aOnecoreuapPrin_4; "onecoreuap\\printscan\\print\\printscan"...
0x180032a5c  mov     edx, 12h; void *
0x180032a61  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x180032a66  mov     rcx, rsi; this
0x180032a69  call    ?_CreateSplWoW64Process@PrintProcessLauncher@@AEAAXXZ; PrintProcessLauncher::_CreateSplWoW64Process(void)
0x180032a6e  xor     edx, edx; Token
0x180032a70  xor     ecx, ecx; Thread
0x180032a72  call    cs:__imp_SetThreadToken
0x180032a78  test    eax, eax
0x180032a7a  setz    al
0x180032a7d  mov     rcx, [rsp+38h]; this
0x180032a82  lea     rdx, aSetthreadtoken_0; "SetThreadToken (revert) failed!"
0x180032a89  mov     qword ptr [rsp+38h+var_18], rdx; bool
0x180032a8e  movzx   r9d, al; char *
0x180032a92  lea     r8, aOnecoreuapPrin_4; "onecoreuap\\printscan\\print\\printscan"...
0x180032a99  mov     edx, 14h; void *
0x180032a9e  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x180032aa3  mov     rbx, [rsp+38h+arg_10]
0x180032aa8  mov     rsi, [rsp+38h+arg_18]
0x180032aad  add     rsp, 30h
0x180032ab1  pop     rdi
0x180032ab2  retn
```
