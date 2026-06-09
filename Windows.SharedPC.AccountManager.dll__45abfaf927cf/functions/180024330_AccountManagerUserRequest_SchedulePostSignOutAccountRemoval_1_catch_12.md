# _AccountManagerUserRequest::SchedulePostSignOutAccountRemoval_::_1_::catch$12

- ea: `0x180024330`
- end: `0x180024369`
- name: `_AccountManagerUserRequest::SchedulePostSignOutAccountRemoval_::_1_::catch$12`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000c210`

## string_xrefs

- `0x180024344`: `shellcommon\shell\sharedpc\accountmanager\lib\service\accountmanageruserrequest.cpp`

## pseudocode

```c
__int64 __fastcall AccountManagerUserRequest::SchedulePostSignOutAccountRemoval_::_1_::catch_12(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 80) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 152),
                           (void *)0x36,
                           (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\service\\accountmanageruserrequest.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x180024330  mov     [rsp+arg_8], rdx
0x180024335  push    rbp
0x180024336  sub     rsp, 50h
0x18002433a  mov     rbp, rdx
0x18002433d  mov     rcx, [rbp+98h]; this
0x180024344  lea     r8, aShellcommonShe_6; "shellcommon\\shell\\sharedpc\\accountma"...
0x18002434b  mov     edx, 36h ; '6'; void *
0x180024350  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180024355  mov     [rbp+50h], eax
0x180024358  mov     rax, 0
0x180024362  add     rsp, 50h
0x180024366  pop     rbp
0x180024367  retn
```
