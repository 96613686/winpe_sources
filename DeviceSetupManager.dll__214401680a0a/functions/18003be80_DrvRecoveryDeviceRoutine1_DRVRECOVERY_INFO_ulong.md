# DrvRecoveryDeviceRoutine1(_DRVRECOVERY_INFO *,ulong *)

- ea: `0x18003be80`
- end: `0x18003bf68`
- name: `?DrvRecoveryDeviceRoutine1@@YAHPEAU_DRVRECOVERY_INFO@@PEAK@Z`
- size: `232`
- prototype: `_BOOL8 __fastcall(struct _DRVRECOVERY_INFO *, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x18003be80`
- `0x1800402f8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003bf50`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003bf50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bf0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bf0d`
- `DEVRTL!DevRtlWriteTextLog` at `0x18003beb5`
- `DEVRTL!DevRtlWriteTextLog` at `0x18003bed4`
- `DEVRTL!DevRtlWriteTextLog` at `0x18003bf48`
- `DEVRTL!DevRtlWriteTextLog` at `0x18003beb5`
- `DEVRTL!DevRtlWriteTextLog` at `0x18003bed4`
- `DEVRTL!DevRtlWriteTextLog` at `0x18003bf48`

## pseudocode

```c
_BOOL8 __fastcall DrvRecoveryDeviceRoutine1(struct _DRVRECOVERY_INFO *a1, unsigned int *a2)
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
  DevRtlWriteTextLog(*((_QWORD *)a1 + 70), 512, 4, "Method ID: 1");
  v4 = *((_QWORD *)a1 + 68);
  *((_QWORD *)&v7 + 1) = a1;
  LODWORD(v7) = 8;
  if ( (unsigned int)pSetupStringTableEnum(
                       v4,
                       0,
                       0,
                       (unsigned int)pDrvRecoveryInstallAlternateDriverCallback,
                       (__int64)&v7) )
  {
    LastError = HIDWORD(v8);
    if ( !HIDWORD(v8) && (_DWORD)v8 )
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
0x18003be80  mov     [rsp+arg_0], rbx
0x18003be85  push    rdi
0x18003be86  sub     rsp, 50h
0x18003be8a  mov     rdi, rcx
0x18003be8d  lea     r9, aRecoverDevices; "{Recover Devices}"
0x18003be94  mov     rcx, [rcx+230h]
0x18003be9b  xorps   xmm0, xmm0
0x18003be9e  xor     eax, eax
0x18003bea0  mov     edx, 200h
0x18003bea5  mov     r8d, 20005h
0x18003beab  mov     [rsp+58h+var_18], rax
0x18003beb0  movups  [rsp+58h+var_28], xmm0
0x18003beb5  call    cs:__imp_DevRtlWriteTextLog
0x18003bebb  mov     rcx, [rdi+230h]
0x18003bec2  lea     r9, aMethodId1; "Method ID: 1"
0x18003bec9  mov     edx, 200h
0x18003bece  mov     r8d, 4
0x18003bed4  call    cs:__imp_DevRtlWriteTextLog
0x18003beda  mov     rcx, [rdi+220h]
0x18003bee1  lea     rax, [rsp+58h+var_28]
0x18003bee6  lea     r9, ?pDrvRecoveryInstallAlternateDriverCallback@@YAHPEAXJPEBG0I_J@Z; pDrvRecoveryInstallAlternateDriverCallback(void *,long,ushort const *,void *,uint,__int64)
0x18003beed  mov     [rsp+58h+var_38], rax
0x18003bef2  xor     r8d, r8d
0x18003bef5  mov     qword ptr [rsp+58h+var_28+8], rdi
0x18003befa  xor     edx, edx
0x18003befc  mov     dword ptr [rsp+58h+var_28], 8
0x18003bf04  call    pSetupStringTableEnum
0x18003bf09  test    eax, eax
0x18003bf0b  jnz     short loc_18003BF17
0x18003bf0d  call    cs:__imp_GetLastError
0x18003bf13  mov     ebx, eax
0x18003bf15  jmp     short loc_18003BF2B
0x18003bf17  mov     ebx, dword ptr [rsp+58h+var_18+4]
0x18003bf1b  test    ebx, ebx
0x18003bf1d  jnz     short loc_18003BF2B
0x18003bf1f  cmp     dword ptr [rsp+58h+var_18], ebx
0x18003bf23  mov     eax, 0BC2h
0x18003bf28  cmovnz  ebx, eax
0x18003bf2b  mov     rcx, [rdi+230h]
0x18003bf32  lea     r9, aRecoverDevices_0; "{Recover Devices - exit(0x%08X)}"
0x18003bf39  mov     edx, 200h
0x18003bf3e  mov     dword ptr [rsp+58h+var_38], ebx
0x18003bf42  mov     r8d, 40005h
0x18003bf48  call    cs:__imp_DevRtlWriteTextLog
0x18003bf4e  mov     ecx, ebx; dwErrCode
0x18003bf50  call    cs:__imp_SetLastError
0x18003bf56  xor     eax, eax
0x18003bf58  test    ebx, ebx
0x18003bf5a  mov     rbx, [rsp+58h+arg_0]
0x18003bf5f  setz    al
0x18003bf62  add     rsp, 50h
0x18003bf66  pop     rdi
0x18003bf67  retn
```
