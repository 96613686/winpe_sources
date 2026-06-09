# RevertDeviceDriverUpdate

- ea: `0x14001bd7c`
- end: `0x14001c15a`
- name: `RevertDeviceDriverUpdate`
- size: `990`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x14001c2e4`

## callees

- `0x140011a78`
- `0x14001bd7c`
- `0x14001c22c`
- `0x1400270b4`
- `0x140027448`
- `0x14002b7ec`
- `0x140045f30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001be67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001beb3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001bfe0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001c03b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001c098`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001c121`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001be67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001beb3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001bfe0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001c03b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001c098`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001c121`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001bdf1`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001be8c`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001bed3`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001bef1`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001bf30`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001bf4a`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001bfa6`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001bfc8`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001bffa`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001c012`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001c058`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001c073`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001c0b2`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001c0dd`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001c146`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001bdf1`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001be8c`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001bed3`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001bef1`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001bf30`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001bf4a`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001bfa6`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001bfc8`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001bffa`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001c012`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001c058`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001c073`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001c0b2`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001c0dd`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001c146`
- `drvstore!DriverStoreFindW` at `0x14001be5d`
- `drvstore!DriverStoreFindW` at `0x14001be5d`

## string_xrefs

- `0x14001bebf`: `Unable to clear device need for reinstall. Error = 0x%08X`
- `0x14001bee1`: `Cleared device need for reinstall.`
- `0x14001bf26`: `Cannot install driver package '%ws' that does not apply to device.`
- `0x14001bf40`: `Restoring last installed driver '%ws' on device.`
- `0x14001bfb4`: `Unable to install driver. Error = 0x%08X`
- `0x14001bfe6`: `Unable to mark device for reinstall to reset driver. Error = 0x%08X`
- `0x14001c002`: `Device needs reinstall to reset driver.`
- `0x14001c041`: `Unable to mark device for reinstall to restore last driver. Error = 0x%08X`
- `0x14001c060`: `Device needs reinstall to restore last driver.`
- `0x14001c09e`: `Unable to clear device from being reinstalled. Error = 0x%08X`
- `0x14001c127`: `Unable to mark device for reinstall. Error = 0x%08X`
- `0x14001c133`: `Device needs reinstall.`
- `0x14001c151`: `Device no longer needs reinstall.`

## pseudocode

```c
__int64 __fastcall RevertDeviceDriverUpdate(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        int *a6,
        __int64 a7)
{
  unsigned int v7; // ebp
  int v11; // edi
  int v12; // eax
  DWORD v13; // eax
  unsigned int v14; // eax
  DWORD v15; // eax
  DWORD v16; // eax
  DWORD LastError; // eax
  const char *v18; // r9
  __int64 v20; // [rsp+20h] [rbp-2A8h]
  __int64 v21; // [rsp+28h] [rbp-2A0h]
  int v22; // [rsp+44h] [rbp-284h] BYREF
  __int64 v23; // [rsp+48h] [rbp-280h]
  int *v24; // [rsp+50h] [rbp-278h]
  _BYTE v25[528]; // [rsp+60h] [rbp-268h] BYREF

  v7 = 0;
  v24 = a6;
  v23 = a4;
  v22 = 0;
  v11 = 0;
  DevRtlWriteTextLog(a7, 1, 196612, "{Revert Device - %ws}", a3 + 16);
  v12 = *(_DWORD *)(a3 + 416);
  if ( (v12 & 1) == 0 )
  {
    if ( (v12 & 2) != 0 )
    {
      if ( (unsigned int)SetDeviceNeedsReinstall(a2, 0, &v22) )
      {
        if ( v22 )
        {
          DevRtlWriteTextLog(a7, 1, 4, "Device no longer needs reinstall.");
          goto LABEL_28;
        }
        if ( (unsigned int)SetDeviceNeedsReinstall(a2, 1, 0) )
        {
          DevRtlWriteTextLog(a7, 1, 4, "Device needs reinstall.");
          goto LABEL_28;
        }
        LastError = GetLastError();
        v18 = "Unable to mark device for reinstall. Error = 0x%08X";
      }
      else
      {
        LastError = GetLastError();
        v18 = "Unable to clear device from being reinstalled. Error = 0x%08X";
      }
      LODWORD(v20) = LastError;
      DevRtlWriteTextLog(a7, 1, 2, v18, v20);
    }
LABEL_28:
    v11 = 0;
    goto LABEL_29;
  }
  if ( !(unsigned int)DevUtilsIsDevicePresent(a2) )
  {
    if ( (unsigned int)SetDeviceNeedsReinstall(a2, 1, 0) )
    {
      DevRtlWriteTextLog(a7, 1, 4, "Device needs reinstall to restore last driver.");
    }
    else
    {
      v16 = GetLastError();
      DevRtlWriteTextLog(a7, 1, 2, "Unable to mark device for reinstall to restore last driver. Error = 0x%08X", v16);
    }
LABEL_29:
    if ( v24 )
      *v24 = v11;
    goto LABEL_31;
  }
  if ( *(_QWORD *)(a3 + 944) )
  {
    if ( !(unsigned int)DriverStoreFindW(a1, a3 + 420, 9, 0, 1, v25, 260, 0) )
    {
      LODWORD(v21) = GetLastError();
      v7 = v21;
      DevRtlWriteTextLog(a7, 1, 1, "Failed to find last driver '%ws' to restore. Error = 0x%08X", a3 + 420, v21);
      goto LABEL_31;
    }
    if ( (*(_BYTE *)(a3 + 416) & 2) != 0 )
    {
      if ( (unsigned int)SetDeviceNeedsReinstall(a2, 0, &v22) )
      {
        DevRtlWriteTextLog(a7, 1, 4, "Cleared device need for reinstall.");
      }
      else
      {
        v13 = GetLastError();
        DevRtlWriteTextLog(a7, 1, 2, "Unable to clear device need for reinstall. Error = 0x%08X", v13);
      }
    }
    if ( !(unsigned int)PnpUtilsDriverPackageAppliesToDevNode(a1, a2, v25, 0) )
    {
      DevRtlWriteTextLog(a7, 1, 2, "Cannot install driver package '%ws' that does not apply to device.", v25);
      v7 = 50;
      goto LABEL_31;
    }
    DevRtlWriteTextLog(a7, 1, 4, "Restoring last installed driver '%ws' on device.", v25);
    v14 = InstallSpecificDriver(v23, 0, a3 + 16, v25, *(_QWORD *)(a3 + 944), a5 | 0x80000000);
    v7 = v14;
    if ( !v14 )
    {
      if ( (unsigned int)DevUtilsDeviceNeedsReboot(a2) )
      {
        DevRtlWriteTextLog(a7, 1, 4, "Device needs reboot.");
        v11 = 1;
        goto LABEL_29;
      }
      goto LABEL_20;
    }
    DevRtlWriteTextLog(a7, 1, 2, "Unable to install driver. Error = 0x%08X", v14);
  }
  if ( (unsigned int)SetDeviceNeedsReinstall(a2, 1, 0) )
  {
    DevRtlWriteTextLog(a7, 1, 4, "Device needs reinstall to reset driver.");
  }
  else
  {
    v15 = GetLastError();
    DevRtlWriteTextLog(a7, 1, 2, "Unable to mark device for reinstall to reset driver. Error = 0x%08X", v15);
  }
  if ( !v7 )
  {
LABEL_20:
    v11 = 0;
    goto LABEL_29;
  }
LABEL_31:
  DevRtlWriteTextLog(a7, 1, 327684, "{Revert Device - exit(0x%08X)}", v7);
  return v7;
}

```

## disassembly

```asm
0x14001bd7c  push    rbx
0x14001bd7e  push    rbp
0x14001bd7f  push    rsi
0x14001bd80  push    rdi
0x14001bd81  push    r12
0x14001bd83  push    r13
0x14001bd85  push    r14
0x14001bd87  push    r15
0x14001bd89  sub     rsp, 288h
0x14001bd90  mov     rax, cs:__security_cookie
0x14001bd97  xor     rax, rsp
0x14001bd9a  mov     [rsp+2C8h+var_58], rax
0x14001bda2  mov     rax, [rsp+2C8h+arg_28]
0x14001bdaa  xor     ebp, ebp
0x14001bdac  mov     rbx, [rsp+2C8h+arg_30]
0x14001bdb4  mov     r15, r8
0x14001bdb7  mov     [rsp+2C8h+var_278], rax
0x14001bdbc  mov     r14d, edx
0x14001bdbf  lea     rax, [r8+10h]
0x14001bdc3  mov     [rsp+2C8h+var_280], r9
0x14001bdc8  mov     r13, rcx
0x14001bdcb  mov     [rsp+2C8h+var_284], ebp
0x14001bdcf  lea     r12d, [rbp+1]
0x14001bdd3  mov     [rsp+2C8h+var_2A8], rax
0x14001bdd8  xor     edi, edi
0x14001bdda  lea     r9, aRevertDeviceWs; "{Revert Device - %ws}"
0x14001bde1  mov     edx, r12d
0x14001bde4  mov     [rsp+2C8h+var_288], edi
0x14001bde8  mov     r8d, 30004h
0x14001bdee  mov     rcx, rbx
0x14001bdf1  call    cs:__imp_DevRtlWriteTextLog
0x14001bdf7  mov     eax, [r15+1A0h]
0x14001bdfe  test    r12b, al
0x14001be01  jz      loc_14001C07B
0x14001be07  mov     ecx, r14d
0x14001be0a  call    DevUtilsIsDevicePresent
0x14001be0f  test    eax, eax
0x14001be11  jz      loc_14001C029
0x14001be17  lea     edi, [rbp+2]
0x14001be1a  lea     esi, [rbp+4]
0x14001be1d  cmp     [r15+3B0h], rbp
0x14001be24  jz      loc_14001BFCE
0x14001be2a  mov     [rsp+2C8h+var_290], rbp
0x14001be2f  lea     rax, [rsp+2C8h+var_268]
0x14001be34  mov     [rsp+2C8h+var_298], 104h
0x14001be3c  lea     r12, [r15+1A4h]
0x14001be43  mov     [rsp+2C8h+var_2A0], rax
0x14001be48  lea     r8d, [rbp+9]
0x14001be4c  mov     rdx, r12
0x14001be4f  mov     dword ptr [rsp+2C8h+var_2A8], 1
0x14001be57  xor     r9d, r9d
0x14001be5a  mov     rcx, r13
0x14001be5d  call    cs:__imp_DriverStoreFindW
0x14001be63  test    eax, eax
0x14001be65  jnz     short loc_14001BE97
0x14001be67  call    cs:__imp_GetLastError
0x14001be6d  mov     dword ptr [rsp+2C8h+var_2A0], eax
0x14001be71  lea     r9, aFailedToFindLa; "Failed to find last driver '%ws' to res"...
0x14001be78  mov     [rsp+2C8h+var_2A8], r12
0x14001be7d  mov     rcx, rbx
0x14001be80  lea     r12d, [rdi-1]
0x14001be84  mov     ebp, eax
0x14001be86  mov     r8d, r12d
0x14001be89  mov     edx, r12d
0x14001be8c  call    cs:__imp_DevRtlWriteTextLog
0x14001be92  jmp     loc_14001C0C6
0x14001be97  test    [r15+1A0h], dil
0x14001be9e  jz      short loc_14001BEF9
0x14001bea0  lea     r8, [rsp+2C8h+var_284]
0x14001bea5  xor     edx, edx
0x14001bea7  mov     ecx, r14d
0x14001beaa  call    SetDeviceNeedsReinstall
0x14001beaf  test    eax, eax
0x14001beb1  jnz     short loc_14001BEDB
0x14001beb3  call    cs:__imp_GetLastError
0x14001beb9  mov     r12d, 1
0x14001bebf  lea     r9, aUnableToClearD_0; "Unable to clear device need for reinsta"...
0x14001bec6  mov     edx, r12d
0x14001bec9  mov     dword ptr [rsp+2C8h+var_2A8], eax
0x14001becd  mov     r8d, edi
0x14001bed0  mov     rcx, rbx
0x14001bed3  call    cs:__imp_DevRtlWriteTextLog
0x14001bed9  jmp     short loc_14001BEFF
0x14001bedb  mov     r12d, 1
0x14001bee1  lea     r9, aClearedDeviceN; "Cleared device need for reinstall."
0x14001bee8  mov     edx, r12d
0x14001beeb  mov     r8d, esi
0x14001beee  mov     rcx, rbx
0x14001bef1  call    cs:__imp_DevRtlWriteTextLog
0x14001bef7  jmp     short loc_14001BEFF
0x14001bef9  mov     r12d, 1
0x14001beff  xor     r9d, r9d
0x14001bf02  lea     r8, [rsp+2C8h+var_268]
0x14001bf07  mov     edx, r14d
0x14001bf0a  mov     rcx, r13
0x14001bf0d  call    PnpUtilsDriverPackageAppliesToDevNode
0x14001bf12  test    eax, eax
0x14001bf14  mov     edx, r12d
0x14001bf17  lea     rax, [rsp+2C8h+var_268]
0x14001bf1c  mov     rcx, rbx
0x14001bf1f  mov     [rsp+2C8h+var_2A8], rax
0x14001bf24  jnz     short loc_14001BF40
0x14001bf26  lea     r9, aCannotInstallD; "Cannot install driver package '%ws' tha"...
0x14001bf2d  mov     r8d, edi
0x14001bf30  call    cs:__imp_DevRtlWriteTextLog
0x14001bf36  mov     ebp, 32h ; '2'
0x14001bf3b  jmp     loc_14001C0C6
0x14001bf40  lea     r9, aRestoringLastI; "Restoring last installed driver '%ws' o"...
0x14001bf47  mov     r8d, esi
0x14001bf4a  call    cs:__imp_DevRtlWriteTextLog
0x14001bf50  mov     eax, [rsp+2C8h+arg_20]
0x14001bf57  lea     r9, [rsp+2C8h+var_268]
0x14001bf5c  mov     rcx, [rsp+2C8h+var_280]
0x14001bf61  lea     r8, [r15+10h]
0x14001bf65  bts     eax, 1Fh
0x14001bf69  xor     edx, edx
0x14001bf6b  mov     dword ptr [rsp+2C8h+var_2A0], eax
0x14001bf6f  mov     rax, [r15+3B0h]
0x14001bf76  mov     [rsp+2C8h+var_2A8], rax
0x14001bf7b  call    InstallSpecificDriver
0x14001bf80  mov     ebp, eax
0x14001bf82  test    eax, eax
0x14001bf84  jnz     short loc_14001BFB4
0x14001bf86  mov     ecx, r14d
0x14001bf89  call    DevUtilsDeviceNeedsReboot
0x14001bf8e  test    eax, eax
0x14001bf90  jz      loc_14001C020
0x14001bf96  lea     r9, aDeviceNeedsReb; "Device needs reboot."
0x14001bf9d  mov     r8d, esi
0x14001bfa0  mov     edx, r12d
0x14001bfa3  mov     rcx, rbx
0x14001bfa6  call    cs:__imp_DevRtlWriteTextLog
0x14001bfac  mov     edi, r12d
0x14001bfaf  jmp     loc_14001C0BA
0x14001bfb4  lea     r9, aUnableToInstal_0; "Unable to install driver. Error = 0x%08"...
0x14001bfbb  mov     dword ptr [rsp+2C8h+var_2A8], eax
0x14001bfbf  mov     r8d, edi
0x14001bfc2  mov     edx, r12d
0x14001bfc5  mov     rcx, rbx
0x14001bfc8  call    cs:__imp_DevRtlWriteTextLog
0x14001bfce  xor     r8d, r8d
0x14001bfd1  mov     edx, r12d
0x14001bfd4  mov     ecx, r14d
0x14001bfd7  call    SetDeviceNeedsReinstall
0x14001bfdc  test    eax, eax
0x14001bfde  jnz     short loc_14001C002
0x14001bfe0  call    cs:__imp_GetLastError
0x14001bfe6  lea     r9, aUnableToMarkDe_1; "Unable to mark device for reinstall to "...
0x14001bfed  mov     r8d, edi
0x14001bff0  mov     edx, r12d
0x14001bff3  mov     dword ptr [rsp+2C8h+var_2A8], eax
0x14001bff7  mov     rcx, rbx
0x14001bffa  call    cs:__imp_DevRtlWriteTextLog
0x14001c000  jmp     short loc_14001C018
0x14001c002  lea     r9, aDeviceNeedsRei_1; "Device needs reinstall to reset driver."
0x14001c009  mov     r8d, esi
0x14001c00c  mov     edx, r12d
0x14001c00f  mov     rcx, rbx
0x14001c012  call    cs:__imp_DevRtlWriteTextLog
0x14001c018  test    ebp, ebp
0x14001c01a  jnz     loc_14001C0C6
0x14001c020  mov     edi, [rsp+2C8h+var_288]
0x14001c024  jmp     loc_14001C0BA
0x14001c029  xor     r8d, r8d
0x14001c02c  mov     edx, r12d
0x14001c02f  mov     ecx, r14d
0x14001c032  call    SetDeviceNeedsReinstall
0x14001c037  test    eax, eax
0x14001c039  jnz     short loc_14001C060
0x14001c03b  call    cs:__imp_GetLastError
0x14001c041  lea     r9, aUnableToMarkDe; "Unable to mark device for reinstall to "...
0x14001c048  mov     r8d, 2
0x14001c04e  mov     edx, r12d
0x14001c051  mov     dword ptr [rsp+2C8h+var_2A8], eax
0x14001c055  mov     rcx, rbx
0x14001c058  call    cs:__imp_DevRtlWriteTextLog
0x14001c05e  jmp     short loc_14001C0BA
0x14001c060  lea     r9, aDeviceNeedsRei; "Device needs reinstall to restore last "...
0x14001c067  mov     r8d, 4
0x14001c06d  mov     edx, r12d
0x14001c070  mov     rcx, rbx
0x14001c073  call    cs:__imp_DevRtlWriteTextLog
0x14001c079  jmp     short loc_14001C0BA
0x14001c07b  mov     edi, 2
0x14001c080  test    dil, al
0x14001c083  jz      short loc_14001C0B8
0x14001c085  lea     r8, [rsp+2C8h+var_284]
0x14001c08a  xor     edx, edx
0x14001c08c  mov     ecx, r14d
0x14001c08f  call    SetDeviceNeedsReinstall
0x14001c094  test    eax, eax
0x14001c096  jnz     short loc_14001C109
0x14001c098  call    cs:__imp_GetLastError
0x14001c09e  lea     r9, aUnableToClearD; "Unable to clear device from being reins"...
0x14001c0a5  mov     r8d, edi
0x14001c0a8  mov     dword ptr [rsp+2C8h+var_2A8], eax
0x14001c0ac  mov     edx, r12d
0x14001c0af  mov     rcx, rbx
0x14001c0b2  call    cs:__imp_DevRtlWriteTextLog
0x14001c0b8  mov     edi, ebp
0x14001c0ba  mov     rax, [rsp+2C8h+var_278]
0x14001c0bf  test    rax, rax
0x14001c0c2  jz      short loc_14001C0C6
0x14001c0c4  mov     [rax], edi
0x14001c0c6  lea     r9, aRevertDeviceEx; "{Revert Device - exit(0x%08X)}"
0x14001c0cd  mov     dword ptr [rsp+2C8h+var_2A8], ebp
0x14001c0d1  mov     r8d, 50004h
0x14001c0d7  mov     edx, r12d
0x14001c0da  mov     rcx, rbx
0x14001c0dd  call    cs:__imp_DevRtlWriteTextLog
0x14001c0e3  mov     eax, ebp
0x14001c0e5  mov     rcx, [rsp+2C8h+var_58]
0x14001c0ed  xor     rcx, rsp; StackCookie
0x14001c0f0  call    __security_check_cookie
0x14001c0f5  add     rsp, 288h
0x14001c0fc  pop     r15
0x14001c0fe  pop     r14
0x14001c100  pop     r13
0x14001c102  pop     r12
0x14001c104  pop     rdi
0x14001c105  pop     rsi
0x14001c106  pop     rbp
0x14001c107  pop     rbx
0x14001c108  retn
0x14001c109  mov     edx, r12d
0x14001c10c  cmp     [rsp+2C8h+var_284], ebp
0x14001c110  jnz     short loc_14001C151
0x14001c112  xor     r8d, r8d
0x14001c115  mov     ecx, r14d
0x14001c118  call    SetDeviceNeedsReinstall
0x14001c11d  test    eax, eax
0x14001c11f  jnz     short loc_14001C133
0x14001c121  call    cs:__imp_GetLastError
0x14001c127  lea     r9, aUnableToMarkDe_0; "Unable to mark device for reinstall. Er"...
0x14001c12e  jmp     loc_14001C0A5
0x14001c133  lea     r9, aDeviceNeedsRei_0; "Device needs reinstall."
0x14001c13a  mov     edx, r12d
0x14001c13d  mov     r8d, 4
0x14001c143  mov     rcx, rbx
0x14001c146  call    cs:__imp_DevRtlWriteTextLog
0x14001c14c  jmp     loc_14001C0B8
0x14001c151  lea     r9, aDeviceNoLonger; "Device no longer needs reinstall."
0x14001c158  jmp     short loc_14001C13D
```
