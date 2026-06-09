# UserOOBEController::SyncTimeZone(void)

- ea: `0x180027060`
- end: `0x180027093`
- name: `?SyncTimeZone@UserOOBEController@@UEAAJXZ`
- size: `51`
- prototype: `__int64 __fastcall(UserOOBEController *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callees

- `0x18000e270`
- `0x180027060`

## import_xrefs

- `tzautoupdate!AttemptToUpdateTimeZoneAndEnableChangeDetection` at `0x180027069`
- `tzautoupdate!AttemptToUpdateTimeZoneAndEnableChangeDetection` at `0x180027069`

## string_xrefs

- `0x180027078`: `shell\oobe\user\dll\useroobecontroller.cpp`

## pseudocode

```c
__int64 __fastcall UserOOBEController::SyncTimeZone(UserOOBEController *this)
{
  int v1; // eax
  int v3; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v1 = AttemptToUpdateTimeZoneAndEnableChangeDetection(60);
  if ( v1 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x115,
      (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
      (const char *)(unsigned int)v1,
      v3);
  return 0;
}

```

## disassembly

```asm
0x180027060  sub     rsp, 28h
0x180027064  mov     ecx, 3Ch ; '<'
0x180027069  call    cs:__imp_AttemptToUpdateTimeZoneAndEnableChangeDetection
0x18002706f  test    eax, eax
0x180027071  jns     short loc_18002708C
0x180027073  mov     rcx, [rsp+28h]; this
0x180027078  lea     r8, aShellOobeUserD_0; "shell\\oobe\\user\\dll\\useroobecontrol"...
0x18002707f  mov     r9d, eax; char *
0x180027082  mov     edx, 115h; void *
0x180027087  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002708c  xor     eax, eax
0x18002708e  add     rsp, 28h
0x180027092  retn
```
