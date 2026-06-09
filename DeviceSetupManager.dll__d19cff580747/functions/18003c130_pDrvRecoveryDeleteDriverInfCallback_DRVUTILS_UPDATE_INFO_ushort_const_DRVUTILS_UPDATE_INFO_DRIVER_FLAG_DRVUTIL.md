# pDrvRecoveryDeleteDriverInfCallback(_DRVUTILS_UPDATE_INFO *,ushort const *,_DRVUTILS_UPDATE_INFO_DRIVER_FLAG,_DRVUTILS_DRIVER_TYPE_FLAG,__int64)

- ea: `0x18003c130`
- end: `0x18003c2a7`
- name: `?pDrvRecoveryDeleteDriverInfCallback@@YAHPEAU_DRVUTILS_UPDATE_INFO@@PEBGW4_DRVUTILS_UPDATE_INFO_DRIVER_FLAG@@W4_DRVUTILS_DRIVER_TYPE_FLAG@@_J@Z`
- size: `375`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, installer_update`

## callees

- `0x18001af70`
- `0x18003c130`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c19c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c19c`
- `DEVRTL!DevRtlWriteTextLog` at `0x18003c1cc`
- `DEVRTL!DevRtlWriteTextLog` at `0x18003c1ec`
- `DEVRTL!DevRtlWriteTextLog` at `0x18003c222`
- `DEVRTL!DevRtlWriteTextLog` at `0x18003c277`
- `DEVRTL!DevRtlWriteTextLog` at `0x18003c1cc`
- `DEVRTL!DevRtlWriteTextLog` at `0x18003c1ec`
- `DEVRTL!DevRtlWriteTextLog` at `0x18003c222`
- `DEVRTL!DevRtlWriteTextLog` at `0x18003c277`
- `drvstore!DriverStoreDeleteW` at `0x18003c237`
- `drvstore!DriverStoreDeleteW` at `0x18003c237`
- `drvstore!DriverStoreFindW` at `0x18003c192`
- `drvstore!DriverStoreFindW` at `0x18003c192`

## string_xrefs

- `0x18003c256`: `Failed to delete driver package %ws. Error = 0x%08X`
- `0x18003c265`: `Deleted driver package %ws.`

## pseudocode

```c
__int64 __fastcall pDrvRecoveryDeleteDriverInfCallback(__int64 a1, __int64 a2, __int64 a3, __int64 a4, _DWORD *a5)
{
  DWORD LastError; // eax
  DWORD v7; // edi
  __int64 v8; // rcx
  DWORD v9; // eax
  __int64 v10; // rcx
  __int64 v12; // [rsp+28h] [rbp-240h]
  _BYTE v13[528]; // [rsp+40h] [rbp-228h] BYREF

  if ( (unsigned int)DriverStoreFindW(*(_QWORD *)(*(_QWORD *)a5 + 8LL), a2, 0xFFFF, 0, 2, v13, 260, 0) )
  {
    DevRtlWriteTextLog(*(_QWORD *)(*(_QWORD *)a5 + 560LL), 512, 65540, "Deleting driver package %ws.", a2);
    v9 = DriverStoreDeleteW(*(_QWORD *)(*(_QWORD *)a5 + 8LL), v13, 0);
    v7 = v9;
    v10 = *(_QWORD *)(*(_QWORD *)a5 + 560LL);
    if ( !v9 )
    {
      DevRtlWriteTextLog(v10, 512, 65540, "Deleted driver package %ws.", a2);
      return 1;
    }
    LODWORD(v12) = v9;
    DevRtlWriteTextLog(v10, 512, 65537, "Failed to delete driver package %ws. Error = 0x%08X", a2, v12);
  }
  else
  {
    LastError = GetLastError();
    v7 = LastError;
    v8 = *(_QWORD *)(*(_QWORD *)a5 + 560LL);
    if ( LastError == 1168 )
    {
      DevRtlWriteTextLog(v8, 512, 4, "Driver package %ws no longer present.", a2);
      v7 = 0;
    }
    else
    {
      LODWORD(v12) = LastError;
      DevRtlWriteTextLog(v8, 512, 1, "Failed to locate driver package %ws. Error = 0x%08X", a2, v12);
    }
  }
  if ( !a5[2] )
    a5[2] = v7;
  return 1;
}

```

## disassembly

```asm
0x18003c130  mov     [rsp+arg_0], rbx
0x18003c135  mov     [rsp+arg_10], rsi
0x18003c13a  push    rdi
0x18003c13b  sub     rsp, 260h
0x18003c142  mov     rax, cs:__security_cookie
0x18003c149  xor     rax, rsp
0x18003c14c  mov     [rsp+268h+var_18], rax
0x18003c154  mov     rbx, [rsp+268h+arg_20]
0x18003c15c  lea     rax, [rsp+268h+var_228]
0x18003c161  mov     [rsp+268h+var_230], 0
0x18003c16a  mov     r8d, 0FFFFh
0x18003c170  mov     [rsp+268h+var_238], 104h
0x18003c178  xor     r9d, r9d
0x18003c17b  mov     [rsp+268h+var_240], rax
0x18003c180  mov     rsi, rdx
0x18003c183  mov     rcx, [rbx]
0x18003c186  mov     dword ptr [rsp+268h+var_248], 2
0x18003c18e  mov     rcx, [rcx+8]
0x18003c192  call    cs:__imp_DriverStoreFindW
0x18003c198  test    eax, eax
0x18003c19a  jnz     short loc_18003C201
0x18003c19c  call    cs:__imp_GetLastError
0x18003c1a2  mov     rcx, [rbx]
0x18003c1a5  mov     edx, 200h
0x18003c1aa  mov     edi, eax
0x18003c1ac  mov     rcx, [rcx+230h]
0x18003c1b3  cmp     eax, 490h
0x18003c1b8  jnz     short loc_18003C1D6
0x18003c1ba  lea     r9, aDriverPackageW_1; "Driver package %ws no longer present."
0x18003c1c1  mov     [rsp+268h+var_248], rsi
0x18003c1c6  mov     r8d, 4
0x18003c1cc  call    cs:__imp_DevRtlWriteTextLog
0x18003c1d2  xor     edi, edi
0x18003c1d4  jmp     short loc_18003C1F2
0x18003c1d6  mov     dword ptr [rsp+268h+var_240], eax
0x18003c1da  lea     r9, aFailedToLocate; "Failed to locate driver package %ws. Er"...
0x18003c1e1  mov     r8d, 1
0x18003c1e7  mov     [rsp+268h+var_248], rsi
0x18003c1ec  call    cs:__imp_DevRtlWriteTextLog
0x18003c1f2  cmp     dword ptr [rbx+8], 0
0x18003c1f6  jnz     loc_18003C27D
0x18003c1fc  mov     [rbx+8], edi
0x18003c1ff  jmp     short loc_18003C27D
0x18003c201  mov     rcx, [rbx]
0x18003c204  lea     r9, aDeletingDriver; "Deleting driver package %ws."
0x18003c20b  mov     edx, 200h
0x18003c210  mov     [rsp+268h+var_248], rsi
0x18003c215  mov     r8d, 10004h
0x18003c21b  mov     rcx, [rcx+230h]
0x18003c222  call    cs:__imp_DevRtlWriteTextLog
0x18003c228  mov     rcx, [rbx]
0x18003c22b  lea     rdx, [rsp+268h+var_228]
0x18003c230  xor     r8d, r8d
0x18003c233  mov     rcx, [rcx+8]
0x18003c237  call    cs:__imp_DriverStoreDeleteW
0x18003c23d  mov     rcx, [rbx]
0x18003c240  mov     edx, 200h
0x18003c245  mov     edi, eax
0x18003c247  mov     rcx, [rcx+230h]
0x18003c24e  test    eax, eax
0x18003c250  jz      short loc_18003C265
0x18003c252  mov     dword ptr [rsp+268h+var_240], eax
0x18003c256  lea     r9, aFailedToDelete; "Failed to delete driver package %ws. Er"...
0x18003c25d  mov     r8d, 10001h
0x18003c263  jmp     short loc_18003C1E7
0x18003c265  lea     r9, aDeletedDriverP; "Deleted driver package %ws."
0x18003c26c  mov     [rsp+268h+var_248], rsi
0x18003c271  mov     r8d, 10004h
0x18003c277  call    cs:__imp_DevRtlWriteTextLog
0x18003c27d  mov     eax, 1
0x18003c282  mov     rcx, [rsp+268h+var_18]
0x18003c28a  xor     rcx, rsp; StackCookie
0x18003c28d  call    __security_check_cookie
0x18003c292  lea     r11, [rsp+268h+var_8]
0x18003c29a  mov     rbx, [r11+10h]
0x18003c29e  mov     rsi, [r11+20h]
0x18003c2a2  mov     rsp, r11
0x18003c2a5  pop     rdi
0x18003c2a6  retn
```
