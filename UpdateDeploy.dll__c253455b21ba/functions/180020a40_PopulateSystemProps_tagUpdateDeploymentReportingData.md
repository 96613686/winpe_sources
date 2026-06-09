# PopulateSystemProps(tagUpdateDeploymentReportingData *)

- ea: `0x180020a40`
- end: `0x180020b53`
- name: `?PopulateSystemProps@@YAXPEAUtagUpdateDeploymentReportingData@@@Z`
- size: `275`
- prototype: `void __fastcall(struct tagUpdateDeploymentReportingData *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, installer_update`

## callers

- `0x1800330b8`

## callees

- `0x180020a40`
- `0x18004b4a0`
- `0x180061960`
- `0x180068f20`

## import_xrefs

- `api-ms-win-core-kernel32-legacy-l1-1-0!GetSystemPowerStatus` at `0x180020b03`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetSystemPowerStatus` at `0x180020b03`
- `api-ms-win-power-base-l1-1-0!CallNtPowerInformation` at `0x180020ac6`
- `api-ms-win-power-base-l1-1-0!CallNtPowerInformation` at `0x180020ac6`

## pseudocode

```c
void __fastcall PopulateSystemProps(struct tagUpdateDeploymentReportingData *a1)
{
  int v2; // eax
  unsigned int v3; // eax
  BOOL v4; // esi
  int v5; // edi
  unsigned int v6; // ecx
  int v7; // eax
  unsigned int v8; // eax
  bool v9; // [rsp+30h] [rbp-88h] BYREF
  _SYSTEM_POWER_STATUS SystemPowerStatus; // [rsp+38h] [rbp-80h] BYREF
  _BYTE OutputBuffer[80]; // [rsp+50h] [rbp-68h] BYREF

  if ( a1 )
  {
    v9 = 0;
    GetStandbyState(&v9, (unsigned __int64 *)a1 + 47);
    v2 = *((_DWORD *)a1 + 92);
    if ( v9 )
      v3 = v2 | 4;
    else
      v3 = v2 & 0xFFFFFFFB;
    v4 = 0;
    *((_DWORD *)a1 + 92) = v3;
    memset(OutputBuffer, 0, 0x4Cu);
    v5 = 1;
    if ( !CallNtPowerInformation(SystemPowerCapabilities, 0, 0, OutputBuffer, 0x4Cu) )
      v4 = OutputBuffer[20] != 0;
    v6 = *((_DWORD *)a1 + 92) | 1;
    if ( !v4 )
      v6 = *((_DWORD *)a1 + 92) & 0xFFFFFFFE;
    *((_DWORD *)a1 + 92) = v6;
    *(_QWORD *)&SystemPowerStatus.ACLineStatus = 0;
    SystemPowerStatus.BatteryFullLifeTime = 0;
    if ( !GetSystemPowerStatus(&SystemPowerStatus) || SystemPowerStatus.ACLineStatus != 1 )
      v5 = 0;
    v7 = *((_DWORD *)a1 + 92);
    if ( v5 )
      v8 = v7 | 2;
    else
      v8 = v7 & 0xFFFFFFFD;
    *((_DWORD *)a1 + 92) = v8;
  }
}

```

## disassembly

```asm
0x180020a40  test    rcx, rcx
0x180020a43  jz      locret_180020B52
0x180020a49  mov     [rsp+arg_8], rbx
0x180020a4e  mov     [rsp+arg_10], rsi
0x180020a53  push    rdi
0x180020a54  sub     rsp, 0B0h
0x180020a5b  mov     rax, cs:__security_cookie
0x180020a62  xor     rax, rsp
0x180020a65  mov     [rsp+0B8h+var_18], rax
0x180020a6d  mov     rbx, rcx
0x180020a70  mov     [rsp+0B8h+var_88], 0
0x180020a75  lea     rdx, [rcx+178h]; unsigned __int64 *
0x180020a7c  lea     rcx, [rsp+0B8h+var_88]; bool *
0x180020a81  call    ?GetStandbyState@@YAXPEA_NPEA_K@Z; GetStandbyState(bool *,unsigned __int64 *)
0x180020a86  cmp     [rsp+0B8h+var_88], 0
0x180020a8b  mov     eax, [rbx+170h]
0x180020a91  jz      short loc_180020A98
0x180020a93  or      eax, 4
0x180020a96  jmp     short loc_180020A9B
0x180020a98  and     eax, 0FFFFFFFBh
0x180020a9b  xor     esi, esi
0x180020a9d  mov     [rbx+170h], eax
0x180020aa3  xor     edx, edx; Val
0x180020aa5  lea     rcx, [rsp+0B8h+OutputBuffer]; void *
0x180020aaa  lea     edi, [rsi+4Ch]
0x180020aad  mov     r8d, edi; Size
0x180020ab0  call    memset
0x180020ab5  lea     r9, [rsp+0B8h+OutputBuffer]; OutputBuffer
0x180020aba  mov     [rsp+0B8h+OutputBufferLength], edi; OutputBufferLength
0x180020abe  xor     r8d, r8d; InputBufferLength
0x180020ac1  lea     ecx, [rsi+4]; InformationLevel
0x180020ac4  xor     edx, edx; InputBuffer
0x180020ac6  call    cs:__imp_CallNtPowerInformation
0x180020acc  lea     edi, [rsi+1]
0x180020acf  test    eax, eax
0x180020ad1  jnz     short loc_180020ADB
0x180020ad3  cmp     [rsp+0B8h+var_54], sil
0x180020ad8  cmovnz  esi, edi
0x180020adb  mov     ecx, [rbx+170h]
0x180020ae1  mov     eax, ecx
0x180020ae3  and     eax, 0FFFFFFFEh
0x180020ae6  or      ecx, edi
0x180020ae8  test    esi, esi
0x180020aea  cmovz   ecx, eax
0x180020aed  xor     eax, eax
0x180020aef  mov     [rbx+170h], ecx
0x180020af5  lea     rcx, [rsp+0B8h+SystemPowerStatus]; lpSystemPowerStatus
0x180020afa  mov     qword ptr [rsp+0B8h+SystemPowerStatus.ACLineStatus], rax
0x180020aff  mov     [rsp+0B8h+SystemPowerStatus.BatteryFullLifeTime], eax
0x180020b03  call    cs:__imp_GetSystemPowerStatus
0x180020b09  test    eax, eax
0x180020b0b  jz      short loc_180020B14
0x180020b0d  cmp     [rsp+0B8h+SystemPowerStatus.ACLineStatus], dil
0x180020b12  jz      short loc_180020B16
0x180020b14  xor     edi, edi
0x180020b16  mov     eax, [rbx+170h]
0x180020b1c  test    edi, edi
0x180020b1e  jz      short loc_180020B25
0x180020b20  or      eax, 2
0x180020b23  jmp     short loc_180020B28
0x180020b25  and     eax, 0FFFFFFFDh
0x180020b28  mov     [rbx+170h], eax
0x180020b2e  mov     rcx, [rsp+0B8h+var_18]
0x180020b36  xor     rcx, rsp; StackCookie
0x180020b39  call    __security_check_cookie
0x180020b3e  lea     r11, [rsp+0B8h+var_8]
0x180020b46  mov     rbx, [r11+18h]
0x180020b4a  mov     rsi, [r11+20h]
0x180020b4e  mov     rsp, r11
0x180020b51  pop     rdi
0x180020b52  retn
```
