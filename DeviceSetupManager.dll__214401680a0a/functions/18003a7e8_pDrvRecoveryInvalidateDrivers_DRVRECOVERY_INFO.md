# pDrvRecoveryInvalidateDrivers(_DRVRECOVERY_INFO *)

- ea: `0x18003a7e8`
- end: `0x18003a959`
- name: `?pDrvRecoveryInvalidateDrivers@@YAHPEAU_DRVRECOVERY_INFO@@@Z`
- size: `369`
- prototype: `_BOOL8 __fastcall(struct _DRVRECOVERY_INFO *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18003a2ac`

## callees

- `0x18003a7e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003a940`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003a940`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a868`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a8c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a868`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a8c8`
- `DEVRTL!DevRtlWriteTextLog` at `0x18003a8f2`
- `DEVRTL!DevRtlWriteTextLog` at `0x18003a918`
- `DEVRTL!DevRtlWriteTextLog` at `0x18003a8f2`
- `DEVRTL!DevRtlWriteTextLog` at `0x18003a918`
- `drvstore!DriverStoreSetObjectPropertyW` at `0x18003a8be`
- `drvstore!DriverStoreSetObjectPropertyW` at `0x18003a8be`
- `drvstore!DriverStoreGetObjectPropertyW` at `0x18003a85e`
- `drvstore!DriverStoreGetObjectPropertyW` at `0x18003a85e`

## pseudocode

```c
_BOOL8 __fastcall pDrvRecoveryInvalidateDrivers(struct _DRVRECOVERY_INFO *a1)
{
  _WORD *v1; // rbx
  DWORD v2; // edi
  __int64 v4; // rcx
  bool v5; // zf
  __int64 v6; // rcx
  __int64 v7; // rax
  __int64 v9; // [rsp+28h] [rbp-28h]
  char v10; // [rsp+80h] [rbp+30h] BYREF
  int v11; // [rsp+88h] [rbp+38h] BYREF
  int v12; // [rsp+90h] [rbp+40h] BYREF

  v1 = (_WORD *)((char *)a1 + 690);
  v2 = 0;
  v11 = 0;
  v12 = 0;
  v10 = 0;
  while ( *v1 )
  {
    v4 = *((_QWORD *)a1 + 1);
    v11 = 0;
    v12 = 0;
    v10 = 0;
    if ( !(unsigned int)DriverStoreGetObjectPropertyW(
                          v4,
                          2,
                          v1,
                          DEVPKEY_DriverPackage_Invalidated,
                          &v11,
                          &v10,
                          1,
                          &v12,
                          0) )
    {
      v5 = GetLastError() == 2;
      goto LABEL_7;
    }
    if ( v11 == 17 && v12 == 1 )
    {
      v5 = v10 == -1;
LABEL_7:
      if ( v5 )
        goto LABEL_11;
    }
    v6 = *((_QWORD *)a1 + 1);
    v10 = -1;
    if ( (unsigned int)DriverStoreSetObjectPropertyW(v6, 2, v1, DEVPKEY_DriverPackage_Invalidated, 17, &v10, 1, 0) )
    {
      DevRtlWriteTextLog(*((_QWORD *)a1 + 70), 512, 4, "Driver package %ws invalidated.", v1);
    }
    else
    {
      LODWORD(v9) = GetLastError();
      v2 = v9;
      DevRtlWriteTextLog(
        *((_QWORD *)a1 + 70),
        512,
        1,
        "Failed to invalidate driver package %ws. Error = 0x%08X",
        v1,
        v9);
    }
LABEL_11:
    v7 = -1;
    do
      ++v7;
    while ( v1[v7] );
    v1 += v7 + 1;
  }
  SetLastError(v2);
  return v2 == 0;
}

```

## disassembly

```asm
0x18003a7e8  push    rbp
0x18003a7ea  push    rbx
0x18003a7eb  push    rsi
0x18003a7ec  push    rdi
0x18003a7ed  push    r14
0x18003a7ef  mov     rbp, rsp
0x18003a7f2  sub     rsp, 50h
0x18003a7f6  xor     r14d, r14d
0x18003a7f9  lea     rbx, [rcx+2B2h]
0x18003a800  mov     edi, r14d
0x18003a803  mov     [rbp+arg_8], r14d
0x18003a807  mov     [rbp+arg_10], r14d
0x18003a80b  mov     rsi, rcx
0x18003a80e  mov     [rbp+arg_0], r14b
0x18003a812  jmp     loc_18003A934
0x18003a817  mov     rcx, [rsi+8]
0x18003a81b  lea     rax, [rbp+arg_10]
0x18003a81f  mov     [rsp+50h+var_10], r14d
0x18003a824  lea     r9, DEVPKEY_DriverPackage_Invalidated
0x18003a82b  mov     [rsp+50h+var_18], rax
0x18003a830  mov     r8, rbx
0x18003a833  lea     rax, [rbp+arg_0]
0x18003a837  mov     [rsp+50h+var_20], 1
0x18003a83f  mov     [rsp+50h+var_28], rax
0x18003a844  mov     edx, 2
0x18003a849  lea     rax, [rbp+arg_8]
0x18003a84d  mov     [rbp+arg_8], r14d
0x18003a851  mov     [rsp+50h+var_30], rax
0x18003a856  mov     [rbp+arg_10], r14d
0x18003a85a  mov     [rbp+arg_0], r14b
0x18003a85e  call    cs:__imp_DriverStoreGetObjectPropertyW
0x18003a864  test    eax, eax
0x18003a866  jnz     short loc_18003A873
0x18003a868  call    cs:__imp_GetLastError
0x18003a86e  cmp     eax, 2
0x18003a871  jmp     short loc_18003A883
0x18003a873  cmp     [rbp+arg_8], 11h
0x18003a877  jnz     short loc_18003A889
0x18003a879  cmp     [rbp+arg_10], 1
0x18003a87d  jnz     short loc_18003A889
0x18003a87f  cmp     [rbp+arg_0], 0FFh
0x18003a883  jz      loc_18003A91E
0x18003a889  mov     rcx, [rsi+8]
0x18003a88d  lea     rax, [rbp+arg_0]
0x18003a891  mov     dword ptr [rsp+50h+var_18], r14d
0x18003a896  lea     r9, DEVPKEY_DriverPackage_Invalidated
0x18003a89d  mov     [rsp+50h+var_20], 1
0x18003a8a5  mov     r8, rbx
0x18003a8a8  mov     [rsp+50h+var_28], rax
0x18003a8ad  mov     edx, 2
0x18003a8b2  mov     dword ptr [rsp+50h+var_30], 11h
0x18003a8ba  mov     [rbp+arg_0], 0FFh
0x18003a8be  call    cs:__imp_DriverStoreSetObjectPropertyW
0x18003a8c4  test    eax, eax
0x18003a8c6  jnz     short loc_18003A8FA
0x18003a8c8  call    cs:__imp_GetLastError
0x18003a8ce  mov     rcx, [rsi+230h]
0x18003a8d5  lea     r9, aFailedToInvali; "Failed to invalidate driver package %ws"...
0x18003a8dc  mov     dword ptr [rsp+50h+var_28], eax
0x18003a8e0  mov     edx, 200h
0x18003a8e5  mov     r8d, 1
0x18003a8eb  mov     [rsp+50h+var_30], rbx
0x18003a8f0  mov     edi, eax
0x18003a8f2  call    cs:__imp_DevRtlWriteTextLog
0x18003a8f8  jmp     short loc_18003A91E
0x18003a8fa  mov     rcx, [rsi+230h]
0x18003a901  lea     r9, aDriverPackageW_0; "Driver package %ws invalidated."
0x18003a908  mov     edx, 200h
0x18003a90d  mov     [rsp+50h+var_30], rbx
0x18003a912  mov     r8d, 4
0x18003a918  call    cs:__imp_DevRtlWriteTextLog
0x18003a91e  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003a922  inc     rax
0x18003a925  cmp     [rbx+rax*2], r14w
0x18003a92a  jnz     short loc_18003A922
0x18003a92c  lea     rbx, [rbx+rax*2]
0x18003a930  add     rbx, 2
0x18003a934  cmp     [rbx], r14w
0x18003a938  jnz     loc_18003A817
0x18003a93e  mov     ecx, edi; dwErrCode
0x18003a940  call    cs:__imp_SetLastError
0x18003a946  test    edi, edi
0x18003a948  mov     eax, r14d
0x18003a94b  setz    al
0x18003a94e  add     rsp, 50h
0x18003a952  pop     r14
0x18003a954  pop     rdi
0x18003a955  pop     rsi
0x18003a956  pop     rbx
0x18003a957  pop     rbp
0x18003a958  retn
```
