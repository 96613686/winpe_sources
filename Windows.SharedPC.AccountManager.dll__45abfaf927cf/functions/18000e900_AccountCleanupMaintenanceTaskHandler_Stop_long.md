# AccountCleanupMaintenanceTaskHandler::Stop(long *)

- ea: `0x18000e900`
- end: `0x18000e939`
- name: `?Stop@AccountCleanupMaintenanceTaskHandler@@UEAAJPEAJ@Z`
- size: `57`
- prototype: `__int64 __fastcall(AccountCleanupMaintenanceTaskHandler *__hidden this, int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180008a38`
- `0x18000e900`

## string_xrefs

- `0x18000e90e`: `shellcommon\shell\sharedpc\accountmanager\lib\service\accountcleanupmaintenancetaskhandler.cpp`

## pseudocode

```c
__int64 __fastcall AccountCleanupMaintenanceTaskHandler::Stop(AccountCleanupMaintenanceTaskHandler *this, int *a2)
{
  int v3; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( a2 )
  {
    *a2 = 0;
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2B,
      (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\service\\accountcleanupmaintenancetaskhandler.cpp",
      (const char *)0x80004003LL,
      v3);
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x18000e900  sub     rsp, 28h
0x18000e904  test    rdx, rdx
0x18000e907  jnz     short loc_18000E92C
0x18000e909  mov     rcx, [rsp+28h]; this
0x18000e90e  lea     r8, aShellcommonShe_16; "shellcommon\\shell\\sharedpc\\accountma"...
0x18000e915  mov     r9d, 80004003h; char *
0x18000e91b  mov     edx, 2Bh ; '+'; void *
0x18000e920  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e925  mov     eax, 80004003h
0x18000e92a  jmp     short loc_18000E934
0x18000e92c  mov     dword ptr [rdx], 0
0x18000e932  xor     eax, eax
0x18000e934  add     rsp, 28h
0x18000e938  retn
```
