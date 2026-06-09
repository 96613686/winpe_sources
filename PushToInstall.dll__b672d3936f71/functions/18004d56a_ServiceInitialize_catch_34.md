# ServiceInitialize$catch$34

- ea: `0x18004d56a`
- end: `0x18004d5c5`
- name: `ServiceInitialize$catch$34`
- size: `91`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, installer_update`

## callees

- `0x18002c4b8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d577`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d577`

## string_xrefs

- `0x18004d5a2`: `onecoreuap\enduser\winstore\pushtoinstall\lib\service.cpp`
- `0x18004d595`: `ServiceInitialize`
- `0x18004d581`: `Uninstalling tencent failed with error code: %d`

## pseudocode

```c
__int64 ServiceInitialize_catch_34()
{
  DWORD LastError; // [rsp+30h] [rbp-18h]

  LastError = GetLastError();
  LogMessage(
    2u,
    "onecoreuap\\enduser\\winstore\\pushtoinstall\\lib\\service.cpp",
    0x16Au,
    "ServiceInitialize",
    -1,
    L"Uninstalling tencent failed with error code: %d",
    LastError);
  return 0;
}

```

## disassembly

```asm
0x18004d56a  mov     [rsp+arg_8], rdx
0x18004d56f  push    rbp
0x18004d570  sub     rsp, 40h
0x18004d574  mov     rbp, rdx
0x18004d577  call    cs:__imp_GetLastError
0x18004d57d  mov     [rsp+48h+var_18], eax
0x18004d581  lea     rax, aUninstallingTe; "Uninstalling tencent failed with error "...
0x18004d588  mov     [rsp+48h+var_20], rax; unsigned __int16 *
0x18004d58d  mov     [rsp+48h+var_28], 0FFFFFFFFh; int
0x18004d595  lea     r9, aServiceinitial; "ServiceInitialize"
0x18004d59c  mov     r8d, 16Ah; unsigned int
0x18004d5a2  lea     rdx, aOnecoreuapEndu_14; "onecoreuap\\enduser\\winstore\\pushtoin"...
0x18004d5a9  mov     ecx, 2; unsigned int
0x18004d5ae  call    ?LogMessage@@YAXIPEBDI0JPEBGZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,...)
0x18004d5b3  nop
0x18004d5b4  mov     rax, 0
0x18004d5be  add     rsp, 40h
0x18004d5c2  pop     rbp
0x18004d5c3  retn
```
