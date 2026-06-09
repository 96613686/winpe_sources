# CloudExperienceHostBroker::Account::LocalAccountManager::s_ValidatePassword(ushort const *,ushort const *)

- ea: `0x180027510`
- end: `0x18002761d`
- name: `?s_ValidatePassword@LocalAccountManager@Account@CloudExperienceHostBroker@@CAJPEBG0@Z`
- size: `269`
- prototype: `__int64 __fastcall(unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002695c`

## callees

- `0x180005fe0`
- `0x180006330`
- `0x180008344`
- `0x1800096a4`
- `0x180009f30`
- `0x180027510`
- `0x180035abc`

## import_xrefs

- `SspiCli!LogonUserExExW` at `0x1800275db`
- `SspiCli!LogonUserExExW` at `0x1800275db`

## string_xrefs

- `0x180027558`: `shell\cloudexperiencehost\broker\lib\localaccountmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CloudExperienceHostBroker::Account::LocalAccountManager::s_ValidatePassword(
        unsigned __int16 *a1,
        const unsigned __int16 *a2)
{
  int v3; // eax
  unsigned int LastErrorFailHr; // ebx
  wil::details *v5; // rcx
  int v7; // [rsp+20h] [rbp-488h]
  _QWORD v8[2]; // [rsp+60h] [rbp-448h] BYREF
  unsigned __int16 v9[264]; // [rsp+70h] [rbp-438h] BYREF
  unsigned __int16 v10[264]; // [rsp+280h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4A8h] [rbp+0h]

  v3 = SHParseUserName(a1, v9, 0x101u, v10);
  LastErrorFailHr = v3;
  if ( v3 >= 0 )
  {
    v8[0] = 0;
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      v8,
      0);
    if ( (unsigned int)LogonUserExExW(v10, v9, a2, 2, 0, 0, v8, 0, 0, 0, 0) )
      LastErrorFailHr = 0;
    else
      LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v8);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A2,
      (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\localaccountmanager.cpp",
      (const char *)(unsigned int)v3,
      v7);
  }
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x180027510  mov     [rsp+arg_10], rbx
0x180027515  push    rdi
0x180027516  sub     rsp, 4A0h
0x18002751d  mov     rax, cs:__security_cookie
0x180027524  xor     rax, rsp
0x180027527  mov     [rsp+4A8h+var_18], rax
0x18002752f  mov     rdi, rdx
0x180027532  lea     r9, [rsp+4A8h+var_228]; unsigned __int16 *
0x18002753a  lea     rdx, [rsp+4A8h+var_438]; unsigned __int16 *
0x18002753f  mov     r8d, 101h; unsigned __int64
0x180027545  call    SHParseUserName
0x18002754a  mov     ebx, eax
0x18002754c  test    eax, eax
0x18002754e  jns     short loc_180027571
0x180027550  mov     rcx, [rsp+4A8h]; this
0x180027558  lea     r8, aShellCloudexpe_4; "shell\\cloudexperiencehost\\broker\\lib"...
0x18002755f  mov     r9d, eax; char *
0x180027562  mov     edx, 1A2h; void *
0x180027567  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002756c  jmp     loc_1800275FA
0x180027571  xor     edx, edx
0x180027573  mov     [rsp+4A8h+var_448], 0
0x18002757c  lea     rcx, [rsp+4A8h+var_448]
0x180027581  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180027586  mov     [rsp+4A8h+var_458], 0
0x18002758f  lea     rax, [rsp+4A8h+var_448]
0x180027594  mov     [rsp+4A8h+var_460], 0
0x18002759d  lea     rdx, [rsp+4A8h+var_438]
0x1800275a2  mov     [rsp+4A8h+var_468], 0
0x1800275ab  lea     rcx, [rsp+4A8h+var_228]
0x1800275b3  mov     [rsp+4A8h+var_470], 0
0x1800275bc  mov     r9d, 2
0x1800275c2  mov     [rsp+4A8h+var_478], rax
0x1800275c7  mov     r8, rdi
0x1800275ca  mov     [rsp+4A8h+var_480], 0
0x1800275d3  mov     [rsp+4A8h+var_488], 0
0x1800275db  call    cs:__imp_LogonUserExExW
0x1800275e1  test    eax, eax
0x1800275e3  jnz     short loc_1800275EE
0x1800275e5  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800275ea  mov     ebx, eax
0x1800275ec  jmp     short loc_1800275F0
0x1800275ee  xor     ebx, ebx
0x1800275f0  lea     rcx, [rsp+4A8h+var_448]
0x1800275f5  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800275fa  mov     eax, ebx
0x1800275fc  mov     rcx, [rsp+4A8h+var_18]
0x180027604  xor     rcx, rsp; StackCookie
0x180027607  call    __security_check_cookie
0x18002760c  mov     rbx, [rsp+4A8h+arg_10]
0x180027614  add     rsp, 4A0h
0x18002761b  pop     rdi
0x18002761c  retn
```
