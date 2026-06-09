# UserOOBEController::DeleteCloudExperienceHostRecoveryDefaultAccount(void)

- ea: `0x1800237e0`
- end: `0x18002380e`
- name: `?DeleteCloudExperienceHostRecoveryDefaultAccount@UserOOBEController@@UEAAJXZ`
- size: `46`
- prototype: `__int64 __fastcall(UserOOBEController *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000e270`
- `0x1800237e0`

## import_xrefs

- `ext-ms-win-security-cfl-l1-1-0!CflClearTempUserAccount` at `0x1800237e4`
- `ext-ms-win-security-cfl-l1-1-0!CflClearTempUserAccount` at `0x1800237e4`

## string_xrefs

- `0x1800237f3`: `shell\oobe\user\dll\useroobecontroller.cpp`

## pseudocode

```c
__int64 __fastcall UserOOBEController::DeleteCloudExperienceHostRecoveryDefaultAccount(UserOOBEController *this)
{
  int v1; // eax
  int v3; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v1 = CflClearTempUserAccount(this);
  if ( v1 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x10D,
      (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
      (const char *)(unsigned int)v1,
      v3);
  return 0;
}

```

## disassembly

```asm
0x1800237e0  sub     rsp, 28h
0x1800237e4  call    cs:__imp_CflClearTempUserAccount
0x1800237ea  test    eax, eax
0x1800237ec  jns     short loc_180023807
0x1800237ee  mov     rcx, [rsp+28h]; this
0x1800237f3  lea     r8, aShellOobeUserD_0; "shell\\oobe\\user\\dll\\useroobecontrol"...
0x1800237fa  mov     r9d, eax; char *
0x1800237fd  mov     edx, 10Dh; void *
0x180023802  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180023807  xor     eax, eax
0x180023809  add     rsp, 28h
0x18002380d  retn
```
