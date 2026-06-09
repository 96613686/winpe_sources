# DrvRecoveryDeviceRoutine0(_DRVRECOVERY_INFO *,ulong *)

- ea: `0x18003bd90`
- end: `0x18003be72`
- name: `?DrvRecoveryDeviceRoutine0@@YAHPEAU_DRVRECOVERY_INFO@@PEAK@Z`
- size: `226`
- prototype: `__int64 __fastcall(struct _DRVRECOVERY_INFO *, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x18003bd90`
- `0x1800402f8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003be5a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003be5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003be1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003be1d`
- `DEVRTL!DevRtlWriteTextLog` at `0x18003bdc5`
- `DEVRTL!DevRtlWriteTextLog` at `0x18003bde4`
- `DEVRTL!DevRtlWriteTextLog` at `0x18003be52`
- `DEVRTL!DevRtlWriteTextLog` at `0x18003bdc5`
- `DEVRTL!DevRtlWriteTextLog` at `0x18003bde4`
- `DEVRTL!DevRtlWriteTextLog` at `0x18003be52`

## pseudocode

```c
_BOOL8 __fastcall DrvRecoveryDeviceRoutine0(struct _DRVRECOVERY_INFO *a1, unsigned int *a2)
{
  __int64 v3; // rcx
  __int64 v4; // rcx
  DWORD LastError; // ebx
  __int128 v7; // [rsp+30h] [rbp-28h] BYREF
  __int64 v8; // [rsp+40h] [rbp-18h]

  v3 = *((_QWORD *)a1 + 70);
  v8 = 0;
  v7 = 0;
  DevRtlWriteTextLog(v3, 512, 131077, "{Recover Devices}");
  DevRtlWriteTextLog(*((_QWORD *)a1 + 70), 512, 4, "Method ID: 0");
  v4 = *((_QWORD *)a1 + 68);
  *((_QWORD *)&v7 + 1) = a1;
  LODWORD(v7) = 0;
  if ( (unsigned int)pSetupStringTableEnum(
                       v4,
                       0,
                       0,
                       (unsigned int)pDrvRecoveryInstallAlternateDriverCallback,
                       (__int64)&v7) )
  {
    LastError = 0;
    if ( (_DWORD)v8 )
      LastError = 3010;
  }
  else
  {
    LastError = GetLastError();
  }
  DevRtlWriteTextLog(*((_QWORD *)a1 + 70), 512, 262149, "{Recover Devices - exit(0x%08X)}", LastError);
  SetLastError(LastError);
  return LastError == 0;
}

```

## disassembly

```asm
0x18003bd90  mov     [rsp+arg_0], rbx
0x18003bd95  push    rdi
0x18003bd96  sub     rsp, 50h
0x18003bd9a  mov     rdi, rcx
0x18003bd9d  lea     r9, aRecoverDevices; "{Recover Devices}"
0x18003bda4  mov     rcx, [rcx+230h]
0x18003bdab  xorps   xmm0, xmm0
0x18003bdae  xor     eax, eax
0x18003bdb0  mov     edx, 200h
0x18003bdb5  mov     r8d, 20005h
0x18003bdbb  mov     [rsp+58h+var_18], rax
0x18003bdc0  movups  [rsp+58h+var_28], xmm0
0x18003bdc5  call    cs:__imp_DevRtlWriteTextLog
0x18003bdcb  mov     rcx, [rdi+230h]
0x18003bdd2  lea     r9, aMethodId0; "Method ID: 0"
0x18003bdd9  mov     edx, 200h
0x18003bdde  mov     r8d, 4
0x18003bde4  call    cs:__imp_DevRtlWriteTextLog
0x18003bdea  mov     rcx, [rdi+220h]
0x18003bdf1  lea     rax, [rsp+58h+var_28]
0x18003bdf6  lea     r9, ?pDrvRecoveryInstallAlternateDriverCallback@@YAHPEAXJPEBG0I_J@Z; pDrvRecoveryInstallAlternateDriverCallback(void *,long,ushort const *,void *,uint,__int64)
0x18003bdfd  mov     [rsp+58h+var_38], rax
0x18003be02  xor     r8d, r8d
0x18003be05  mov     qword ptr [rsp+58h+var_28+8], rdi
0x18003be0a  xor     edx, edx
0x18003be0c  mov     dword ptr [rsp+58h+var_28], 0
0x18003be14  call    pSetupStringTableEnum
0x18003be19  test    eax, eax
0x18003be1b  jnz     short loc_18003BE27
0x18003be1d  call    cs:__imp_GetLastError
0x18003be23  mov     ebx, eax
0x18003be25  jmp     short loc_18003BE35
0x18003be27  xor     ebx, ebx
0x18003be29  mov     eax, 0BC2h
0x18003be2e  cmp     dword ptr [rsp+58h+var_18], ebx
0x18003be32  cmovnz  ebx, eax
0x18003be35  mov     rcx, [rdi+230h]
0x18003be3c  lea     r9, aRecoverDevices_0; "{Recover Devices - exit(0x%08X)}"
0x18003be43  mov     edx, 200h
0x18003be48  mov     dword ptr [rsp+58h+var_38], ebx
0x18003be4c  mov     r8d, 40005h
0x18003be52  call    cs:__imp_DevRtlWriteTextLog
0x18003be58  mov     ecx, ebx; dwErrCode
0x18003be5a  call    cs:__imp_SetLastError
0x18003be60  xor     eax, eax
0x18003be62  test    ebx, ebx
0x18003be64  mov     rbx, [rsp+58h+arg_0]
0x18003be69  setz    al
0x18003be6c  add     rsp, 50h
0x18003be70  pop     rdi
0x18003be71  retn
```
