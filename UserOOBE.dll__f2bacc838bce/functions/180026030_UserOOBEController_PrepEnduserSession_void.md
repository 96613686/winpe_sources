# UserOOBEController::PrepEnduserSession(void)

- ea: `0x180026030`
- end: `0x18002607d`
- name: `?PrepEnduserSession@UserOOBEController@@UEAAJXZ`
- size: `77`
- prototype: `__int64 __fastcall(UserOOBEController *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18001f6c4`
- `0x180026030`

## import_xrefs

- `api-ms-win-stateseparation-helpers-l1-1-1!SetPersistedRegistryDWORD` at `0x18002604f`
- `api-ms-win-stateseparation-helpers-l1-1-1!SetPersistedRegistryDWORD` at `0x18002604f`

## string_xrefs

- `0x18002605e`: `shell\oobe\user\dll\useroobecontroller.cpp`

## pseudocode

```c
int __fastcall UserOOBEController::PrepEnduserSession(
        UserOOBEController *this,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5)
{
  unsigned int v5; // eax
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v5 = SetPersistedRegistryDWORD(
         L"OOBE",
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\OOBE",
         L"ContinueOobeInEnduserSession",
         1);
  if ( v5 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x190,
             (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
             (const char *)v5,
             a5);
  else
    return 0;
}

```

## disassembly

```asm
0x180026030  sub     rsp, 28h
0x180026034  mov     r9d, 1
0x18002603a  lea     r8, aContinueoobein; "ContinueOobeInEnduserSession"
0x180026041  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180026048  lea     rcx, aOobe_0; "OOBE"
0x18002604f  call    cs:__imp_SetPersistedRegistryDWORD
0x180026055  test    eax, eax
0x180026057  jz      short loc_180026076
0x180026059  mov     rcx, [rsp+28h]; this
0x18002605e  lea     r8, aShellOobeUserD_0; "shell\\oobe\\user\\dll\\useroobecontrol"...
0x180026065  mov     r9d, eax; char *
0x180026068  mov     edx, 190h; void *
0x18002606d  add     rsp, 28h
0x180026071  jmp     ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180026076  xor     eax, eax
0x180026078  add     rsp, 28h
0x18002607c  retn
```
