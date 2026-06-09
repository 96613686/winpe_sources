# _QueryRemoteQueueForAllUsersAndInstallWithImpersonation_::_1_::catch$16

- ea: `0x18004d28f`
- end: `0x18004d2f2`
- name: `_QueryRemoteQueueForAllUsersAndInstallWithImpersonation_::_1_::catch$16`
- size: `99`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, service_task, installer_update`

## callees

- `0x18002c4b8`

## string_xrefs

- `0x18004d2cf`: `onecoreuap\enduser\winstore\pushtoinstall\lib\service.cpp`
- `0x18004d2a8`: `Could not obtain OR impersonate the user CV:%hs`
- `0x18004d2c2`: `QueryRemoteQueueForAllUsersAndInstallWithImpersonation`

## pseudocode

```c
__int64 __fastcall QueryRemoteQueueForAllUsersAndInstallWithImpersonation_::_1_::catch_16(__int64 a1, __int64 a2)
{
  LogMessage(
    2u,
    "onecoreuap\\enduser\\winstore\\pushtoinstall\\lib\\service.cpp",
    0xD7u,
    "QueryRemoteQueueForAllUsersAndInstallWithImpersonation",
    *(_DWORD *)(*(_QWORD *)(a2 + 160) + 32LL),
    L"Could not obtain OR impersonate the user CV:%hs",
    a2 + 176);
  return 0;
}

```

## disassembly

```asm
0x18004d28f  mov     [rsp+arg_8], rdx
0x18004d294  push    rbp
0x18004d295  sub     rsp, 40h
0x18004d299  mov     rbp, rdx
0x18004d29c  lea     rax, [rbp+0B0h]
0x18004d2a3  mov     [rsp+48h+var_18], rax
0x18004d2a8  lea     rax, aCouldNotObtain; "Could not obtain OR impersonate the use"...
0x18004d2af  mov     [rsp+48h+var_20], rax; unsigned __int16 *
0x18004d2b4  mov     rax, [rbp+0A0h]
0x18004d2bb  mov     ecx, [rax+20h]
0x18004d2be  mov     [rsp+48h+var_28], ecx; int
0x18004d2c2  lea     r9, aQueryremoteque_0; "QueryRemoteQueueForAllUsersAndInstallWi"...
0x18004d2c9  mov     r8d, 0D7h; unsigned int
0x18004d2cf  lea     rdx, aOnecoreuapEndu_14; "onecoreuap\\enduser\\winstore\\pushtoin"...
0x18004d2d6  mov     ecx, 2; unsigned int
0x18004d2db  call    ?LogMessage@@YAXIPEBDI0JPEBGZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,...)
0x18004d2e0  nop
0x18004d2e1  mov     rax, 0
0x18004d2eb  add     rsp, 40h
0x18004d2ef  pop     rbp
0x18004d2f0  retn
```
