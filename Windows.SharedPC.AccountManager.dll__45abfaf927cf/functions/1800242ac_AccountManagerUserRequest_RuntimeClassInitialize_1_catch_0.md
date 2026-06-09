# _AccountManagerUserRequest::RuntimeClassInitialize_::_1_::catch$0

- ea: `0x1800242ac`
- end: `0x1800242e2`
- name: `_AccountManagerUserRequest::RuntimeClassInitialize_::_1_::catch$0`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000c210`

## string_xrefs

- `0x1800242bd`: `shellcommon\shell\sharedpc\accountmanager\lib\service\accountmanageruserrequest.cpp`

## pseudocode

```c
__int64 __fastcall AccountManagerUserRequest::RuntimeClassInitialize_::_1_::catch_0(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 48) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 40),
                           (void *)0x19,
                           (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\service\\accountmanageruserrequest.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x1800242ac  mov     [rsp+arg_8], rdx
0x1800242b1  push    rbp
0x1800242b2  sub     rsp, 20h
0x1800242b6  mov     rbp, rdx
0x1800242b9  mov     rcx, [rbp+28h]; this
0x1800242bd  lea     r8, aShellcommonShe_6; "shellcommon\\shell\\sharedpc\\accountma"...
0x1800242c4  mov     edx, 19h; void *
0x1800242c9  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x1800242ce  mov     [rbp+30h], eax
0x1800242d1  mov     rax, 0
0x1800242db  add     rsp, 20h
0x1800242df  pop     rbp
0x1800242e0  retn
```
