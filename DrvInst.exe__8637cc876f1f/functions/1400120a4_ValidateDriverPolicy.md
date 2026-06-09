# ValidateDriverPolicy

- ea: `0x1400120a4`
- end: `0x1400121f6`
- name: `ValidateDriverPolicy`
- size: `338`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140011f24`
- `0x140012200`

## callees

- `0x1400120a4`
- `0x1400231e4`
- `0x14002332c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001211b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001211b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400121d4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400121d4`
- `DEVRTL!DevRtlWriteTextLog` at `0x140012159`
- `DEVRTL!DevRtlWriteTextLog` at `0x1400121cc`
- `DEVRTL!DevRtlWriteTextLog` at `0x140012159`
- `DEVRTL!DevRtlWriteTextLog` at `0x1400121cc`

## string_xrefs

- `0x140012124`: `extension driver`
- `0x140012188`: `Installation of driver '%ws' is blocked by policy. Error = 0x%08X`
- `0x1400121ae`: `Extension driver`
- `0x1400121b9`: `%ws '%ws' policy evaluation complete`

## pseudocode

```c
_BOOL8 __fastcall ValidateDriverPolicy(__int64 a1, __int64 a2, int a3, unsigned __int64 a4)
{
  DWORD LastError; // eax
  const wchar_t *v8; // rcx
  DWORD v9; // ebx
  const wchar_t *v10; // rax
  __int64 v12; // [rsp+28h] [rbp-48h]
  int v13; // [rsp+40h] [rbp-30h] BYREF
  int v14; // [rsp+44h] [rbp-2Ch] BYREF
  __int64 v15; // [rsp+48h] [rbp-28h] BYREF
  _QWORD v16[4]; // [rsp+50h] [rbp-20h] BYREF
  int v17; // [rsp+90h] [rbp+20h] BYREF

  v13 = 0;
  v16[0] = &InstallRegOpenKeyCallback;
  v14 = 0;
  v16[1] = InstallRegCloseKeyCallback;
  v17 = 0;
  v15 = -1;
  v16[2] = a1;
  if ( (unsigned int)DrvPolQueryDriverProperties(
                       a1,
                       a2,
                       (unsigned int)&v13,
                       (unsigned int)&v14,
                       (__int64)&v17,
                       (__int64)&v15) )
  {
    if ( (unsigned int)DrvPolIsDriverBlockedByPolicy((struct _DRVPOL_REG_CONTEXT *)v16, a4) )
    {
      v9 = -536870328;
      LODWORD(v12) = -536870328;
      DevRtlWriteTextLog(a4, 1, 1, "Installation of driver '%ws' is blocked by policy. Error = 0x%08X", a2, v12);
    }
    else
    {
      v9 = 0;
      v10 = L"Extension driver";
      if ( !a3 )
        v10 = L"Driver";
      DevRtlWriteTextLog(a4, 1, 6, "%ws '%ws' policy evaluation complete", v10, a2);
    }
  }
  else
  {
    LastError = GetLastError();
    v8 = L"extension driver";
    v9 = LastError;
    if ( !a3 )
      v8 = L"driver";
    DevRtlWriteTextLog(
      a4,
      1,
      2,
      "Unable to retrieve properties for %ws '%ws' to evaluate driver package against policy. Error = 0x%08X",
      v8,
      a2,
      LastError);
  }
  SetLastError(v9);
  return v9 == 0;
}

```

## disassembly

```asm
0x1400120a4  mov     r11, rsp
0x1400120a7  mov     [r11+10h], rbx
0x1400120ab  mov     [r11+18h], rsi
0x1400120af  push    rbp
0x1400120b0  push    rdi
0x1400120b1  push    r14
0x1400120b3  mov     rbp, rsp
0x1400120b6  sub     rsp, 70h
0x1400120ba  lea     rax, InstallRegOpenKeyCallback
0x1400120c1  mov     [rbp+var_30], 0
0x1400120c8  mov     [rbp+var_20], rax
0x1400120cc  mov     rdi, r9
0x1400120cf  lea     rax, InstallRegCloseKeyCallback
0x1400120d6  mov     [rbp+var_2C], 0
0x1400120dd  mov     [rbp+var_18], rax
0x1400120e1  lea     r9, [rbp+var_2C]
0x1400120e5  lea     rax, [rbp+var_28]
0x1400120e9  mov     [rbp+arg_0], 0
0x1400120f0  mov     [r11-60h], rax
0x1400120f4  mov     r14d, r8d
0x1400120f7  lea     rax, [rbp+arg_0]
0x1400120fb  mov     [rbp+var_28], 0FFFFFFFFFFFFFFFFh
0x140012103  lea     r8, [rbp+var_30]
0x140012107  mov     [r11-68h], rax
0x14001210b  mov     rsi, rdx
0x14001210e  mov     [rbp+var_10], rcx
0x140012112  call    DrvPolQueryDriverProperties
0x140012117  test    eax, eax
0x140012119  jnz     short loc_140012161
0x14001211b  call    cs:__imp_GetLastError
0x140012121  test    r14d, r14d
0x140012124  lea     rcx, aExtensionDrive; "extension driver"
0x14001212b  mov     ebx, eax
0x14001212d  lea     r9, aUnableToRetrie_0; "Unable to retrieve properties for %ws '"...
0x140012134  lea     rax, aDriver_0; "driver"
0x14001213b  mov     [rsp+70h+var_40], ebx
0x14001213f  cmovz   rcx, rax
0x140012143  mov     [rsp+70h+var_48], rsi
0x140012148  mov     edx, 1
0x14001214d  mov     [rsp+70h+var_50], rcx
0x140012152  mov     rcx, rdi
0x140012155  lea     r8d, [rdx+1]
0x140012159  call    cs:__imp_DevRtlWriteTextLog
0x14001215f  jmp     short loc_1400121D2
0x140012161  mov     r9, [rbp+var_28]
0x140012165  lea     rcx, [rbp+var_20]; struct _DRVPOL_REG_CONTEXT *
0x140012169  mov     r8d, [rbp+arg_0]
0x14001216d  mov     edx, [rbp+var_30]
0x140012170  mov     [rsp+70h+var_50], rdi; unsigned __int64
0x140012175  call    DrvPolIsDriverBlockedByPolicy
0x14001217a  mov     edx, 1
0x14001217f  test    eax, eax
0x140012181  jz      short loc_14001219D
0x140012183  mov     ebx, 0E0000248h
0x140012188  lea     r9, aInstallationOf_3; "Installation of driver '%ws' is blocked"...
0x14001218f  mov     dword ptr [rsp+70h+var_48], ebx
0x140012193  mov     r8d, edx
0x140012196  mov     [rsp+70h+var_50], rsi
0x14001219b  jmp     short loc_1400121C9
0x14001219d  xor     ebx, ebx
0x14001219f  mov     [rsp+70h+var_48], rsi
0x1400121a4  test    r14d, r14d
0x1400121a7  lea     rcx, aDriver; "Driver"
0x1400121ae  lea     rax, aExtensionDrive_0; "Extension driver"
0x1400121b5  cmovz   rax, rcx
0x1400121b9  lea     r9, aWsWsPolicyEval; "%ws '%ws' policy evaluation complete"
0x1400121c0  mov     [rsp+70h+var_50], rax
0x1400121c5  lea     r8d, [rbx+6]
0x1400121c9  mov     rcx, rdi
0x1400121cc  call    cs:__imp_DevRtlWriteTextLog
0x1400121d2  mov     ecx, ebx; dwErrCode
0x1400121d4  call    cs:__imp_SetLastError
0x1400121da  xor     eax, eax
0x1400121dc  lea     r11, [rsp+70h+var_s0]
0x1400121e1  mov     rsi, [r11+30h]
0x1400121e5  test    ebx, ebx
0x1400121e7  mov     rbx, [r11+28h]
0x1400121eb  setz    al
0x1400121ee  mov     rsp, r11
0x1400121f1  pop     r14
0x1400121f3  pop     rdi
0x1400121f4  pop     rbp
0x1400121f5  retn
```
