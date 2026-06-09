# DrvRecoveryDriverRoutine0(_DRVRECOVERY_INFO *,ulong *)

- ea: `0x18003c060`
- end: `0x18003c124`
- name: `?DrvRecoveryDriverRoutine0@@YAHPEAU_DRVRECOVERY_INFO@@PEAK@Z`
- size: `196`
- prototype: `__int64 __fastcall(struct _DRVRECOVERY_INFO *, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x18003c060`
- `0x18003e2e4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003c10c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003c10c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c0d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c0d9`
- `DEVRTL!DevRtlWriteTextLog` at `0x18003c08e`
- `DEVRTL!DevRtlWriteTextLog` at `0x18003c0ad`
- `DEVRTL!DevRtlWriteTextLog` at `0x18003c104`
- `DEVRTL!DevRtlWriteTextLog` at `0x18003c08e`
- `DEVRTL!DevRtlWriteTextLog` at `0x18003c0ad`
- `DEVRTL!DevRtlWriteTextLog` at `0x18003c104`

## pseudocode

```c
_BOOL8 __fastcall DrvRecoveryDriverRoutine0(struct _DRVRECOVERY_INFO *a1, unsigned int *a2)
{
  __int64 v3; // rcx
  __int64 v4; // rcx
  DWORD LastError; // ebx
  __int128 v7; // [rsp+30h] [rbp-18h] BYREF

  v3 = *((_QWORD *)a1 + 70);
  v7 = 0;
  DevRtlWriteTextLog(v3, 512, 131077, "{Recover Drivers}");
  DevRtlWriteTextLog(*((_QWORD *)a1 + 70), 512, 4, "Method ID: 0");
  v4 = *((_QWORD *)a1 + 67);
  *(_QWORD *)&v7 = a1;
  if ( (unsigned int)DrvUtilsUpdateInfoEnumDriverInfs(v4, 15, pDrvRecoveryDeleteDriverInfCallback, &v7) )
    LastError = DWORD2(v7);
  else
    LastError = GetLastError();
  DevRtlWriteTextLog(*((_QWORD *)a1 + 70), 512, 262149, "{Recover Drivers - exit(0x%08X)}", LastError);
  SetLastError(LastError);
  return LastError == 0;
}

```

## disassembly

```asm
0x18003c060  mov     [rsp+arg_0], rbx
0x18003c065  push    rdi
0x18003c066  sub     rsp, 40h
0x18003c06a  mov     rdi, rcx
0x18003c06d  lea     r9, aRecoverDrivers; "{Recover Drivers}"
0x18003c074  mov     rcx, [rcx+230h]
0x18003c07b  xorps   xmm0, xmm0
0x18003c07e  mov     edx, 200h
0x18003c083  mov     r8d, 20005h
0x18003c089  movups  [rsp+48h+var_18], xmm0
0x18003c08e  call    cs:__imp_DevRtlWriteTextLog
0x18003c094  mov     rcx, [rdi+230h]
0x18003c09b  lea     r9, aMethodId0; "Method ID: 0"
0x18003c0a2  mov     edx, 200h
0x18003c0a7  mov     r8d, 4
0x18003c0ad  call    cs:__imp_DevRtlWriteTextLog
0x18003c0b3  mov     rcx, [rdi+218h]
0x18003c0ba  lea     r9, [rsp+48h+var_18]
0x18003c0bf  lea     r8, ?pDrvRecoveryDeleteDriverInfCallback@@YAHPEAU_DRVUTILS_UPDATE_INFO@@PEBGW4_DRVUTILS_UPDATE_INFO_DRIVER_FLAG@@W4_DRVUTILS_DRIVER_TYPE_FLAG@@_J@Z; pDrvRecoveryDeleteDriverInfCallback(_DRVUTILS_UPDATE_INFO *,ushort const *,_DRVUTILS_UPDATE_INFO_DRIVER_FLAG,_DRVUTILS_DRIVER_TYPE_FLAG,__int64)
0x18003c0c6  mov     qword ptr [rsp+48h+var_18], rdi
0x18003c0cb  mov     edx, 0Fh
0x18003c0d0  call    DrvUtilsUpdateInfoEnumDriverInfs
0x18003c0d5  test    eax, eax
0x18003c0d7  jnz     short loc_18003C0E3
0x18003c0d9  call    cs:__imp_GetLastError
0x18003c0df  mov     ebx, eax
0x18003c0e1  jmp     short loc_18003C0E7
0x18003c0e3  mov     ebx, dword ptr [rsp+48h+var_18+8]
0x18003c0e7  mov     rcx, [rdi+230h]
0x18003c0ee  lea     r9, aRecoverDrivers_0; "{Recover Drivers - exit(0x%08X)}"
0x18003c0f5  mov     edx, 200h
0x18003c0fa  mov     [rsp+48h+var_28], ebx
0x18003c0fe  mov     r8d, 40005h
0x18003c104  call    cs:__imp_DevRtlWriteTextLog
0x18003c10a  mov     ecx, ebx; dwErrCode
0x18003c10c  call    cs:__imp_SetLastError
0x18003c112  xor     eax, eax
0x18003c114  test    ebx, ebx
0x18003c116  mov     rbx, [rsp+48h+arg_0]
0x18003c11b  setz    al
0x18003c11e  add     rsp, 40h
0x18003c122  pop     rdi
0x18003c123  retn
```
