# UserOOBEController::CleanupEnduserSession(void)

- ea: `0x1800232b0`
- end: `0x180023352`
- name: `?CleanupEnduserSession@UserOOBEController@@UEAAJXZ`
- size: `162`
- prototype: `__int64 __fastcall(UserOOBEController *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180007134`
- `0x18001f6c4`
- `0x1800232b0`
- `0x180026c00`

## import_xrefs

- `api-ms-win-stateseparation-helpers-l1-1-1!DeletePersistedRegistryValue` at `0x1800232cb`
- `api-ms-win-stateseparation-helpers-l1-1-1!DeletePersistedRegistryValue` at `0x1800232cb`
- `ntdll!RtlPublishWnfStateData` at `0x18002331d`
- `ntdll!RtlPublishWnfStateData` at `0x18002331d`

## string_xrefs

- `0x1800232da`: `shell\oobe\user\dll\useroobecontroller.cpp`
- `0x180023332`: `shell\oobe\user\dll\useroobecontroller.cpp`

## pseudocode

```c
int __fastcall UserOOBEController::CleanupEnduserSession(
        UserOOBEController *this,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5)
{
  unsigned int v5; // eax
  int v7; // eax
  unsigned int v8; // ebx
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  int v10; // [rsp+48h] [rbp+10h] BYREF

  v5 = DeletePersistedRegistryValue(
         L"OOBE",
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\OOBE",
         L"ContinueOobeInEnduserSession");
  if ( v5 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x196,
             (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
             (const char *)v5,
             a5);
  StopOobeLoggingElevatedOperations();
  v10 = 1;
  v7 = RtlPublishWnfStateData(WNF_SHEL_OOBE_USER_LOGON_COMPLETE, 0, &v10, 4);
  v8 = v7 | 0x10000000;
  if ( v7 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x19E,
    (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
    (const char *)v8,
    0);
  return v8;
}

```

## disassembly

```asm
0x1800232b0  push    rbx
0x1800232b2  sub     rsp, 30h
0x1800232b6  lea     r8, aContinueoobein; "ContinueOobeInEnduserSession"
0x1800232bd  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800232c4  lea     rcx, aOobe_0; "OOBE"
0x1800232cb  call    cs:__imp_DeletePersistedRegistryValue
0x1800232d1  test    eax, eax
0x1800232d3  jz      short loc_1800232F3
0x1800232d5  mov     rcx, [rsp+38h]; this
0x1800232da  lea     r8, aShellOobeUserD_0; "shell\\oobe\\user\\dll\\useroobecontrol"...
0x1800232e1  mov     r9d, eax; char *
0x1800232e4  mov     edx, 196h; void *
0x1800232e9  add     rsp, 30h
0x1800232ed  pop     rbx
0x1800232ee  jmp     ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800232f3  call    ?StopOobeLoggingElevatedOperations@@YAXXZ; StopOobeLoggingElevatedOperations(void)
0x1800232f8  mov     rcx, cs:WNF_SHEL_OOBE_USER_LOGON_COMPLETE
0x1800232ff  lea     r8, [rsp+38h+arg_8]
0x180023304  mov     r9d, 4
0x18002330a  mov     [rsp+38h+arg_8], 1
0x180023312  xor     edx, edx
0x180023314  mov     qword ptr [rsp+38h+var_18], 0; int
0x18002331d  call    cs:__imp_RtlPublishWnfStateData
0x180023323  mov     ebx, eax
0x180023325  or      ebx, 10000000h
0x18002332b  jge     short loc_18002334A
0x18002332d  mov     rcx, [rsp+38h]; this
0x180023332  lea     r8, aShellOobeUserD_0; "shell\\oobe\\user\\dll\\useroobecontrol"...
0x180023339  mov     r9d, ebx; char *
0x18002333c  mov     edx, 19Eh; void *
0x180023341  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023346  mov     eax, ebx
0x180023348  jmp     short loc_18002334C
0x18002334a  xor     eax, eax
0x18002334c  add     rsp, 30h
0x180023350  pop     rbx
0x180023351  retn
```
