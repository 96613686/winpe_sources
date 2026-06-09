# DrvRecoveryPerformAction(_DRVRECOVERY_INFO *)

- ea: `0x18003a0e8`
- end: `0x18003a2a4`
- name: `?DrvRecoveryPerformAction@@YAHPEAU_DRVRECOVERY_INFO@@@Z`
- size: `444`
- prototype: `__int64 __fastcall(struct _DRVRECOVERY_INFO *)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x1800299a0`

## callees

- `0x18003a0e8`
- `0x18003b988`
- `0x180040430`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003a283`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003a283`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a1f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a231`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a1f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a231`
- `DEVRTL!DevRtlWriteTextLog` at `0x18003a119`
- `DEVRTL!DevRtlWriteTextLog` at `0x18003a1d0`
- `DEVRTL!DevRtlWriteTextLog` at `0x18003a251`
- `DEVRTL!DevRtlWriteTextLog` at `0x18003a274`
- `DEVRTL!DevRtlWriteTextLog` at `0x18003a119`
- `DEVRTL!DevRtlWriteTextLog` at `0x18003a1d0`
- `DEVRTL!DevRtlWriteTextLog` at `0x18003a251`
- `DEVRTL!DevRtlWriteTextLog` at `0x18003a274`

## string_xrefs

- `0x18003a23e`: `Failed to write state information. Error = 0x%08X`

## pseudocode

```c
__int64 __fastcall DrvRecoveryPerformAction(struct _DRVRECOVERY_INFO *a1)
{
  unsigned int v2; // edi
  bool v3; // zf
  int v4; // ecx
  __int64 v5; // r9
  int v6; // ecx
  int v7; // eax
  __int64 v8; // r8
  DWORD v9; // eax
  int v10; // eax
  DWORD LastError; // eax
  __int64 v12; // rcx
  DWORD v13; // ecx
  DWORD dwErrCode; // [rsp+60h] [rbp+28h] BYREF

  dwErrCode = 0;
  DevRtlWriteTextLog(*((_QWORD *)a1 + 70), 512, 196612, "{Perform Recovery Action}");
  v2 = 1;
  if ( *((_DWORD *)a1 + 142) == 3 )
  {
    *((_DWORD *)a1 + 138) = 1;
    *((_DWORD *)a1 + 142) = 4;
    *((_DWORD *)a1 + 149) = 2;
    if ( !pDrvRecoveryWriteInfo(a1) )
    {
LABEL_16:
      LastError = GetLastError();
      v12 = *((_QWORD *)a1 + 70);
      dwErrCode = LastError;
      DevRtlWriteTextLog(v12, 512, 1, "Failed to write state information. Error = 0x%08X", LastError);
      goto LABEL_17;
    }
    v3 = (unsigned int)pSetupStringTableIsEmpty(*((_QWORD *)a1 + 68)) == 0;
    v4 = ~*((_DWORD *)a1 + 148);
    if ( v3 )
    {
      v5 = 2LL * *((unsigned int *)a1 + 150);
      v6 = qword_1800471B8[v5] & v4;
      if ( !v6 )
      {
        v7 = (*(__int64 (__fastcall **)(struct _DRVRECOVERY_INFO *, unsigned int *))((char *)&off_1800471B0 + v5 * 8))(
               a1,
               &dwErrCode);
        goto LABEL_10;
      }
    }
    else
    {
      v8 = 16LL * *((unsigned int *)a1 + 151);
      v6 = *(_DWORD *)&algn_1800471A8[v8] & v4;
      if ( !v6 )
      {
        v7 = (*(__int64 (__fastcall **)(struct _DRVRECOVERY_INFO *, unsigned int *))((char *)&off_1800471A0 + v8))(
               a1,
               &dwErrCode);
LABEL_10:
        if ( !v7 )
          dwErrCode = GetLastError();
LABEL_12:
        v9 = dwErrCode;
        *((_DWORD *)a1 + 152) = dwErrCode;
        if ( v9 == 3010 )
        {
          v10 = 6;
        }
        else
        {
          *((_DWORD *)a1 + 138) = 0;
          v10 = 5;
        }
        *((_DWORD *)a1 + 142) = v10;
        if ( pDrvRecoveryWriteInfo(a1) )
          goto LABEL_17;
        goto LABEL_16;
      }
    }
    DevRtlWriteTextLog(
      *((_QWORD *)a1 + 70),
      512,
      2,
      "Skipping routine because required recovery behaviors are disallowed (0x%08X)",
      v6);
    goto LABEL_12;
  }
  dwErrCode = 259;
LABEL_17:
  DevRtlWriteTextLog(*((_QWORD *)a1 + 70), 512, 327684, "{Perform Recovery Action - exit(0x%08X)}", dwErrCode);
  v13 = dwErrCode;
  *((_DWORD *)a1 + 139) = dwErrCode;
  SetLastError(v13);
  if ( dwErrCode && dwErrCode != 3010 )
    return 0;
  return v2;
}

```

## disassembly

```asm
0x18003a0e8  push    rbp
0x18003a0ea  push    rbx
0x18003a0eb  push    rsi
0x18003a0ec  push    rdi
0x18003a0ed  mov     rbp, rsp
0x18003a0f0  sub     rsp, 38h
0x18003a0f4  mov     rbx, rcx
0x18003a0f7  mov     [rbp+dwErrCode], 0
0x18003a0fe  mov     rcx, [rcx+230h]
0x18003a105  lea     r9, aPerformRecover_0; "{Perform Recovery Action}"
0x18003a10c  mov     esi, 200h
0x18003a111  mov     r8d, 30004h
0x18003a117  mov     edx, esi
0x18003a119  call    cs:__imp_DevRtlWriteTextLog
0x18003a11f  cmp     dword ptr [rbx+238h], 3
0x18003a126  mov     edi, 1
0x18003a12b  jz      short loc_18003A139
0x18003a12d  mov     [rbp+dwErrCode], 103h
0x18003a134  jmp     loc_18003A257
0x18003a139  mov     rcx, rbx; struct _DRVRECOVERY_INFO *
0x18003a13c  mov     [rbx+228h], edi
0x18003a142  mov     dword ptr [rbx+238h], 4
0x18003a14c  mov     dword ptr [rbx+254h], 2
0x18003a156  call    ?pDrvRecoveryWriteInfo@@YAHPEAU_DRVRECOVERY_INFO@@@Z; pDrvRecoveryWriteInfo(_DRVRECOVERY_INFO *)
0x18003a15b  test    eax, eax
0x18003a15d  jz      loc_18003A231
0x18003a163  mov     rcx, [rbx+220h]
0x18003a16a  call    pSetupStringTableIsEmpty
0x18003a16f  mov     ecx, [rbx+250h]
0x18003a175  test    eax, eax
0x18003a177  not     ecx
0x18003a179  lea     rax, __ImageBase
0x18003a180  jnz     short loc_18003A1A1
0x18003a182  mov     r9d, [rbx+258h]
0x18003a189  shl     r9, 4
0x18003a18d  and     ecx, [r9+rax+471B8h]
0x18003a195  jnz     short loc_18003A1B6
0x18003a197  mov     rax, [r9+rax+471B0h]
0x18003a19f  jmp     short loc_18003A1E0
0x18003a1a1  mov     r8d, [rbx+25Ch]
0x18003a1a8  shl     r8, 4
0x18003a1ac  and     ecx, [r8+rax+471A8h]
0x18003a1b4  jz      short loc_18003A1D8
0x18003a1b6  mov     [rsp+38h+var_18], ecx
0x18003a1ba  lea     r9, aSkippingRoutin; "Skipping routine because required recov"...
0x18003a1c1  mov     rcx, [rbx+230h]
0x18003a1c8  mov     r8d, 2
0x18003a1ce  mov     edx, esi
0x18003a1d0  call    cs:__imp_DevRtlWriteTextLog
0x18003a1d6  jmp     short loc_18003A1F9
0x18003a1d8  mov     rax, [r8+rax+471A0h]
0x18003a1e0  lea     rdx, [rbp+dwErrCode]
0x18003a1e4  mov     rcx, rbx
0x18003a1e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a1ec  test    eax, eax
0x18003a1ee  jnz     short loc_18003A1F9
0x18003a1f0  call    cs:__imp_GetLastError
0x18003a1f6  mov     [rbp+dwErrCode], eax
0x18003a1f9  mov     eax, [rbp+dwErrCode]
0x18003a1fc  mov     [rbx+260h], eax
0x18003a202  cmp     eax, 0BC2h
0x18003a207  jz      short loc_18003A21A
0x18003a209  mov     dword ptr [rbx+228h], 0
0x18003a213  mov     eax, 5
0x18003a218  jmp     short loc_18003A21F
0x18003a21a  mov     eax, 6
0x18003a21f  mov     rcx, rbx; struct _DRVRECOVERY_INFO *
0x18003a222  mov     [rbx+238h], eax
0x18003a228  call    ?pDrvRecoveryWriteInfo@@YAHPEAU_DRVRECOVERY_INFO@@@Z; pDrvRecoveryWriteInfo(_DRVRECOVERY_INFO *)
0x18003a22d  test    eax, eax
0x18003a22f  jnz     short loc_18003A257
0x18003a231  call    cs:__imp_GetLastError
0x18003a237  mov     rcx, [rbx+230h]
0x18003a23e  lea     r9, aFailedToWriteS; "Failed to write state information. Erro"...
0x18003a245  mov     r8d, edi
0x18003a248  mov     [rsp+38h+var_18], eax
0x18003a24c  mov     edx, esi
0x18003a24e  mov     [rbp+dwErrCode], eax
0x18003a251  call    cs:__imp_DevRtlWriteTextLog
0x18003a257  mov     eax, [rbp+dwErrCode]
0x18003a25a  lea     r9, aPerformRecover; "{Perform Recovery Action - exit(0x%08X)"...
0x18003a261  mov     rcx, [rbx+230h]
0x18003a268  mov     r8d, 50004h
0x18003a26e  mov     edx, esi
0x18003a270  mov     [rsp+38h+var_18], eax
0x18003a274  call    cs:__imp_DevRtlWriteTextLog
0x18003a27a  mov     ecx, [rbp+dwErrCode]; dwErrCode
0x18003a27d  mov     [rbx+22Ch], ecx
0x18003a283  call    cs:__imp_SetLastError
0x18003a289  mov     eax, [rbp+dwErrCode]
0x18003a28c  test    eax, eax
0x18003a28e  jz      short loc_18003A299
0x18003a290  cmp     eax, 0BC2h
0x18003a295  jz      short loc_18003A299
0x18003a297  xor     edi, edi
0x18003a299  mov     eax, edi
0x18003a29b  add     rsp, 38h
0x18003a29f  pop     rdi
0x18003a2a0  pop     rsi
0x18003a2a1  pop     rbx
0x18003a2a2  pop     rbp
0x18003a2a3  retn
```
