# PnpPolIsDeviceInstallAllowed

- ea: `0x140022330`
- end: `0x140022bbf`
- name: `PnpPolIsDeviceInstallAllowed`
- size: `2191`
- prototype: `_BOOL8 __fastcall(HANDLE TokenHandle, DEVINSTID_W pDeviceID, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `23`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x140011f24`

## callees

- `0x14000ad64`
- `0x14000ae24`
- `0x1400214f4`
- `0x140021560`
- `0x1400215cc`
- `0x140021638`
- `0x140021738`
- `0x140021850`
- `0x14002191c`
- `0x140021984`
- `0x140021c28`
- `0x140021d84`
- `0x140021e58`
- `0x140021eb8`
- `0x140021f50`
- `0x140021ff4`
- `0x140022060`
- `0x140022330`
- `0x140023b08`
- `0x140023b40`
- `0x1400272a0`
- `0x14002b7ec`
- `0x140045f30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140022563`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140022563`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140022b88`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140022b88`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x140022499`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x1400224fc`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x140022499`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x1400224fc`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x140022488`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x140022488`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_PropertyW` at `0x1400224ed`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_PropertyW` at `0x1400224ed`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x140022446`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x140022446`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x140022423`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x140022423`
- `DEVRTL!DevRtlWriteTextLog` at `0x140022621`
- `DEVRTL!DevRtlWriteTextLog` at `0x140022910`
- `DEVRTL!DevRtlWriteTextLog` at `0x140022931`
- `DEVRTL!DevRtlWriteTextLog` at `0x140022950`
- `DEVRTL!DevRtlWriteTextLog` at `0x14002297a`
- `DEVRTL!DevRtlWriteTextLog` at `0x14002299d`
- `DEVRTL!DevRtlWriteTextLog` at `0x1400229c5`
- `DEVRTL!DevRtlWriteTextLog` at `0x1400229e3`
- `DEVRTL!DevRtlWriteTextLog` at `0x140022a0b`
- `DEVRTL!DevRtlWriteTextLog` at `0x140022a1d`
- `DEVRTL!DevRtlWriteTextLog` at `0x140022a43`
- `DEVRTL!DevRtlWriteTextLog` at `0x140022a6d`
- `DEVRTL!DevRtlWriteTextLog` at `0x140022ac2`
- `DEVRTL!DevRtlWriteTextLog` at `0x140022add`
- `DEVRTL!DevRtlWriteTextLog` at `0x140022b04`
- `DEVRTL!DevRtlWriteTextLog` at `0x140022b24`
- `DEVRTL!DevRtlWriteTextLog` at `0x140022b58`
- `DEVRTL!DevRtlWriteTextLog` at `0x140022b79`
- `DEVRTL!DevRtlWriteTextLog` at `0x140022621`
- `DEVRTL!DevRtlWriteTextLog` at `0x140022910`
- `DEVRTL!DevRtlWriteTextLog` at `0x140022931`
- `DEVRTL!DevRtlWriteTextLog` at `0x140022950`
- `DEVRTL!DevRtlWriteTextLog` at `0x14002297a`
- `DEVRTL!DevRtlWriteTextLog` at `0x14002299d`
- `DEVRTL!DevRtlWriteTextLog` at `0x1400229c5`
- `DEVRTL!DevRtlWriteTextLog` at `0x1400229e3`
- `DEVRTL!DevRtlWriteTextLog` at `0x140022a0b`
- `DEVRTL!DevRtlWriteTextLog` at `0x140022a1d`
- `DEVRTL!DevRtlWriteTextLog` at `0x140022a43`
- `DEVRTL!DevRtlWriteTextLog` at `0x140022a6d`
- `DEVRTL!DevRtlWriteTextLog` at `0x140022ac2`
- `DEVRTL!DevRtlWriteTextLog` at `0x140022add`
- `DEVRTL!DevRtlWriteTextLog` at `0x140022b04`
- `DEVRTL!DevRtlWriteTextLog` at `0x140022b24`
- `DEVRTL!DevRtlWriteTextLog` at `0x140022b58`
- `DEVRTL!DevRtlWriteTextLog` at `0x140022b79`
- `DEVRTL!DevRtlGetThreadLogToken` at `0x14002239c`
- `DEVRTL!DevRtlGetThreadLogToken` at `0x14002239c`
- `drvstore!DriverStoreGetObjectPropertyW` at `0x140022559`
- `drvstore!DriverStoreGetObjectPropertyW` at `0x140022559`

## string_xrefs

- `0x14002260c`: `Device installation policy not enforced for driver update`
- `0x14002263d`: `Only administrators are allowed to install a NULL driver on this device`
- `0x14002266f`: `Installation of device is restricted for this user, based on selected driver`
- `0x140022692`: `Installation of device is restricted for this user, selected driver does not match device`
- `0x140022828`: `Device installation restriction for unspecified device not enforced when layered evaluation is enabled`
- `0x14002285d`: `Device installation policy not enforced for unspecified device during OS Upgrade`
- `0x1400228f4`: `{Device installation policy check [%ws]}`
- `0x140022969`: `[-] Restricted hardware or compatible ID: %ws`
- `0x1400229d1`: `[-] Restricted installation of devices not described by policy`
- `0x140022a16`: `[*] One or more matching policy restrictions that allow installation overrides the device restrictions:`
- `0x140022a5c`: `[+] Hardware or Compatible ID: %ws`
- `0x140022af3`: `[+] Hardware or Compatible ID: %ws`
- `0x140022ab0`: `Device installation policy allows installation of %ws`
- `0x140022b46`: `Device installation policy will be deferred until a driver is selected for %ws`
- `0x140022b62`: `{Device installation policy check [%ws] exit(0x%08x)}`

## pseudocode

```c
_BOOL8 __fastcall PnpPolIsDeviceInstallAllowed(HANDLE TokenHandle, DEVINSTID_W pDeviceID, unsigned __int16 *a3, int a4)
{
  DWORD v4; // edi
  char v5; // r13
  __int64 ThreadLogToken; // rsi
  int HasBuiltinGroup; // eax
  int v11; // r14d
  int v12; // r13d
  BOOL v13; // r14d
  CONFIGRET v14; // eax
  DWORD LastError; // eax
  int v16; // r12d
  CONFIGRET DevNode_PropertyW; // eax
  int v18; // r15d
  const char *v19; // r9
  __int64 v20; // r8
  unsigned int v21; // r13d
  unsigned int v22; // r14d
  BOOL v23; // r15d
  int IsDeviceInInstanceIDsList; // eax
  int v25; // ecx
  int IsClassInDeviceAllowList; // eax
  int v27; // ebx
  int v28; // ecx
  PCNZWCH v29; // r12
  DEVPROPTYPE *nSubAuthority2; // [rsp+20h] [rbp-E0h]
  unsigned int nSubAuthority2a; // [rsp+20h] [rbp-E0h]
  BYTE *nSubAuthority3; // [rsp+28h] [rbp-D8h]
  int v34; // [rsp+60h] [rbp-A0h]
  BOOL v35; // [rsp+60h] [rbp-A0h]
  DEVNODE pdnDevInst; // [rsp+64h] [rbp-9Ch] BYREF
  BOOL v37; // [rsp+68h] [rbp-98h]
  int v38; // [rsp+6Ch] [rbp-94h] BYREF
  int v39; // [rsp+70h] [rbp-90h]
  DEVPROPTYPE PropertyType; // [rsp+74h] [rbp-8Ch] BYREF
  ULONG PropertyBufferSize; // [rsp+78h] [rbp-88h] BYREF
  int v42; // [rsp+7Ch] [rbp-84h]
  int v43; // [rsp+80h] [rbp-80h]
  int v44; // [rsp+84h] [rbp-7Ch]
  int IsDeviceInDeviceIDsList; // [rsp+88h] [rbp-78h]
  int v46; // [rsp+8Ch] [rbp-74h]
  int v47; // [rsp+90h] [rbp-70h]
  int v48; // [rsp+94h] [rbp-6Ch]
  int v49; // [rsp+98h] [rbp-68h]
  BOOL v50; // [rsp+9Ch] [rbp-64h]
  PSID SidToCheck; // [rsp+A0h] [rbp-60h] BYREF
  PCNZWCH lpString2; // [rsp+A8h] [rbp-58h]
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+B0h] [rbp-50h] BYREF
  BYTE PropertyBuffer[16]; // [rsp+B8h] [rbp-48h] BYREF
  WCHAR String2[40]; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int16 v56[200]; // [rsp+120h] [rbp+20h] BYREF
  unsigned __int16 v57[200]; // [rsp+2B0h] [rbp+1B0h] BYREF

  v47 = a4;
  SidToCheck = 0;
  v4 = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_OWORD *)PropertyBuffer = 0;
  v38 = 0;
  v5 = a4;
  pdnDevInst = 0;
  PropertyType = 0;
  PropertyBufferSize = 0;
  lpString2 = pDeviceID;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  ThreadLogToken = DevRtlGetThreadLogToken();
  HasBuiltinGroup = pSetupTokenHasBuiltinGroup(TokenHandle, 0x220u);
  v34 = HasBuiltinGroup;
  v11 = HasBuiltinGroup;
  if ( (v5 & 1) != 0 )
  {
    if ( !HasBuiltinGroup && !(unsigned int)pSetupTokenHasBuiltinGroup(TokenHandle, 0x221u) )
    {
      v4 = 5;
      goto LABEL_134;
    }
    v13 = 0;
    v12 = 1;
    if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 4u, 0, 0, 0, 0, 0, 0, 0, &SidToCheck) )
    {
      v13 = pSetupTokenHasGroupSID(TokenHandle, SidToCheck) != 0;
      FreeSid(SidToCheck);
    }
    if ( (unsigned int)PnpPolAllowAdminDeviceInstall() && v34 && v13 )
      goto LABEL_134;
    v11 = v34;
  }
  else
  {
    v12 = 0;
  }
  if ( !pDeviceID )
  {
    v4 = 87;
    goto LABEL_134;
  }
  v14 = CM_Locate_DevNodeW(&pdnDevInst, pDeviceID, 1u);
  if ( v14 )
  {
    LastError = CM_MapCrToWin32Err(v14, 0xDu);
LABEL_16:
    v4 = LastError;
    goto LABEL_134;
  }
  v16 = v47 & 0x80;
  if ( a3 )
  {
    nSubAuthority3 = PropertyBuffer;
    nSubAuthority2 = &PropertyType;
    if ( !(unsigned int)DriverStoreGetObjectPropertyW(0, 2, a3, DEVPKEY_DriverPackage_ClassGuid) )
    {
      LastError = GetLastError();
      goto LABEL_16;
    }
    if ( PropertyType != 13 || (v42 = 1, PropertyBufferSize != 16) )
    {
      v4 = 13;
      goto LABEL_134;
    }
  }
  else
  {
    v42 = 0;
    if ( (v47 & 0x80) != 0 )
    {
      PropertyBufferSize = 16;
      DevNode_PropertyW = CM_Get_DevNode_PropertyW(
                            pdnDevInst,
                            &DEVPKEY_Device_ClassGuid,
                            &PropertyType,
                            PropertyBuffer,
                            &PropertyBufferSize,
                            0);
      if ( DevNode_PropertyW )
      {
        v4 = CM_MapCrToWin32Err(DevNode_PropertyW, 0xDu);
        if ( v4 )
          goto LABEL_134;
      }
      else if ( PropertyType != 13 )
      {
        v4 = 1804;
        goto LABEL_134;
      }
    }
  }
  v18 = 0;
  v39 = 0;
  if ( !(unsigned int)SpUtilsIsGuidNull(PropertyBuffer) )
  {
    v4 = SpUtilsStringFromGuid(PropertyBuffer, String2);
    if ( v4 )
      goto LABEL_134;
    v18 = 1;
    v39 = 1;
  }
  if ( v12 || !(unsigned int)PnpPolIsDevicePolicyExempt(lpString2, a3, (struct _GUID *)PropertyBuffer) )
  {
    if ( !v16
      && (unsigned int)PnpPolIsDeviceDriverUpdated(pdnDevInst)
      && (!v42 || (unsigned int)DevUtilsInfInstalledOnDevNode(pdnDevInst, a3)) )
    {
      v19 = "Device installation policy not enforced for driver update";
LABEL_38:
      v20 = 5;
LABEL_39:
      DevRtlWriteTextLog(ThreadLogToken, 0x800000, v20, v19);
      goto LABEL_134;
    }
    if ( v12 && !v11 )
    {
      if ( !v42 )
      {
        v19 = "Only administrators are allowed to install a NULL driver on this device";
LABEL_44:
        v4 = 5;
LABEL_45:
        v20 = 2;
        goto LABEL_39;
      }
      if ( v18 && !(unsigned int)PnpPolIsClassInUserDriverAllowList((struct _GUID *)PropertyBuffer)
        || !(unsigned int)PnpPolIsDriverSignedByTrustedPublisher(a3) )
      {
        v19 = "Installation of device is restricted for this user, based on selected driver";
        goto LABEL_44;
      }
      if ( !(unsigned int)PnpUtilsDriverPackageAppliesToDevNode(0, pdnDevInst, a3, 0) )
      {
        v4 = -536870328;
        v19 = "Installation of device is restricted for this user, selected driver does not match device";
        goto LABEL_45;
      }
    }
    v21 = 0;
    v22 = 0;
    v43 = 0;
    v23 = 0;
    v35 = 0;
    v44 = 0;
    v49 = 0;
    v48 = PnpPolAllowDenyLayeredEvaluation();
    if ( (unsigned int)PnpPolIsDeviceRemovable(pdnDevInst) )
      v23 = PnpPolRestrictRemovableDevices() != 0;
    v50 = v23;
    IsDeviceInDeviceIDsList = PnpPolIsDeviceInDeviceIDsList(pdnDevInst, 0, 0, v56, (unsigned int)nSubAuthority2);
    v37 = IsDeviceInDeviceIDsList != 0;
    if ( (unsigned int)PnpPolIsDeviceInDeviceIDsList(pdnDevInst, 1, &v38, v57, nSubAuthority2a) && (!v16 || v38) )
    {
      v23 = 1;
      v43 = 1;
    }
    IsDeviceInInstanceIDsList = PnpPolIsDeviceInInstanceIDsList(lpString2, 0, 0);
    v25 = v37;
    v46 = IsDeviceInInstanceIDsList;
    if ( IsDeviceInInstanceIDsList )
      v25 = 1;
    v37 = v25;
    if ( (unsigned int)PnpPolIsDeviceInInstanceIDsList(lpString2, 1, &v38) && (!v16 || v38) )
    {
      v23 = 1;
      v44 = 1;
    }
    if ( v39 )
    {
      IsClassInDeviceAllowList = PnpPolIsClassInDeviceAllowList(String2);
      v27 = v37;
      if ( IsClassInDeviceAllowList )
        v27 = 1;
      v37 = v27;
      v35 = IsClassInDeviceAllowList != 0;
      if ( (unsigned int)PnpPolIsClassInDeviceDenyList(String2, &v38) && (!v16 || v38) )
      {
        v23 = 1;
        v39 = 1;
        v28 = 1;
        goto LABEL_90;
      }
    }
    else
    {
      v27 = v37;
    }
    v28 = 0;
    v39 = 0;
    if ( !v23 )
    {
      if ( !v27 )
      {
        if ( v16 || !(unsigned int)PnpPolRestrictUnspecifiedDevices() )
          goto LABEL_134;
        if ( v48 )
        {
          v19 = "Device installation restriction for unspecified device not enforced when layered evaluation is enabled";
          goto LABEL_45;
        }
        if ( v42 || (unsigned int)PnpPolIsClassDeviceAllowListEmpty() )
        {
          if ( (v47 & 0x20) != 0 && (unsigned int)PnpPolIsSetupUpgradeInProgress() )
          {
            v19 = "Device installation policy not enforced for unspecified device during OS Upgrade";
            goto LABEL_38;
          }
          v23 = 1;
          v49 = 1;
          goto LABEL_86;
        }
        v4 = -536870397;
      }
LABEL_102:
      v29 = lpString2;
      DevRtlWriteTextLog(ThreadLogToken, 0x800000, 196612, "{Device installation policy check [%ws]}", lpString2);
      if ( v23 )
      {
        DevRtlWriteTextLog(
          ThreadLogToken,
          0x800000,
          1,
          "The device is explicitly restricted by the following policy settings:");
        if ( v50 )
          DevRtlWriteTextLog(ThreadLogToken, 0x800000, 1, "[-] Removable devices are restricted");
        if ( v43 )
          DevRtlWriteTextLog(ThreadLogToken, 0x800000, 1, "[-] Restricted hardware or compatible ID: %ws", v57);
        if ( v44 )
          DevRtlWriteTextLog(ThreadLogToken, 0x800000, 1, "[-] Restricted instance ID: %ws", v29);
        if ( v39 )
          DevRtlWriteTextLog(ThreadLogToken, 0x800000, 1, "[-] Restricted setup class of selected driver: %ws", String2);
        if ( v49 )
          DevRtlWriteTextLog(
            ThreadLogToken,
            0x800000,
            1,
            "[-] Restricted installation of devices not described by policy");
        if ( v37 )
        {
          if ( v22 > v21 )
          {
            DevRtlWriteTextLog(
              ThreadLogToken,
              0x800000,
              2,
              "[*] One or more matching policy restrictions that allow installation overrides the device restrictions:");
            if ( v46 )
              DevRtlWriteTextLog(ThreadLogToken, 0x800000, 524290, "[+] Instance ID: %ws", v29);
            if ( IsDeviceInDeviceIDsList && v22 > 2 )
              DevRtlWriteTextLog(ThreadLogToken, 0x800000, 524290, "[+] Hardware or Compatible ID: %ws", v56);
            if ( v35 && v22 > 3 )
              DevRtlWriteTextLog(ThreadLogToken, 0x800000, 524290, "[+] Setup class of selected driver: %ws", String2);
          }
          else
          {
            DevRtlWriteTextLog(
              ThreadLogToken,
              0x800000,
              2,
              "[*] One or more matching policy restrictions that would allow the device have been ignored");
          }
        }
      }
      else if ( v37 )
      {
        DevRtlWriteTextLog(ThreadLogToken, 0x800000, 5, "Device installation policy allows installation of %ws", v29);
        DevRtlWriteTextLog(
          ThreadLogToken,
          0x800000,
          524293,
          "The device is explicitly allowed by the following policy settings:");
        if ( IsDeviceInDeviceIDsList )
          DevRtlWriteTextLog(ThreadLogToken, 0x800000, 524293, "[+] Hardware or Compatible ID: %ws", v56);
        if ( v46 )
          DevRtlWriteTextLog(ThreadLogToken, 0x800000, 524293, "[+] Instance ID: %ws", v29);
        if ( v35 )
          DevRtlWriteTextLog(ThreadLogToken, 0x800000, 524293, "[+] Setup class of the selected driver: %ws", String2);
      }
      else
      {
        DevRtlWriteTextLog(
          ThreadLogToken,
          0x800000,
          2,
          "Device installation policy will be deferred until a driver is selected for %ws",
          v29);
      }
      LODWORD(nSubAuthority3) = v4;
      DevRtlWriteTextLog(
        ThreadLogToken,
        0x800000,
        262148,
        "{Device installation policy check [%ws] exit(0x%08x)}",
        v29,
        nSubAuthority3);
      goto LABEL_134;
    }
LABEL_90:
    if ( v48 )
    {
      if ( v27 )
      {
        if ( v44 )
        {
          v22 = 1;
        }
        else if ( v43 )
        {
          v22 = 2;
        }
        else
        {
          v22 = 4 - (v28 != 0);
        }
        if ( v46 )
          v21 = 1;
        else
          v21 = 3 - (IsDeviceInDeviceIDsList != 0);
        if ( v21 < v22 )
          goto LABEL_102;
        goto LABEL_101;
      }
      goto LABEL_87;
    }
LABEL_86:
    if ( v27 )
    {
LABEL_101:
      v4 = -536870328;
      goto LABEL_102;
    }
LABEL_87:
    v4 = -536870328;
    if ( v16 && !MEMORY[0] )
      goto LABEL_134;
    goto LABEL_102;
  }
LABEL_134:
  SetLastError(v4);
  return v4 == 0;
}

```

## disassembly

```asm
0x140022330  mov     [rsp-8+arg_18], rbx
0x140022335  push    rbp
0x140022336  push    rsi
0x140022337  push    rdi
0x140022338  push    r12
0x14002233a  push    r13
0x14002233c  push    r14
0x14002233e  push    r15
0x140022340  lea     rbp, [rsp-350h]
0x140022348  sub     rsp, 450h
0x14002234f  mov     rax, cs:__security_cookie
0x140022356  xor     rax, rsp
0x140022359  mov     [rbp+380h+var_40], rax
0x140022360  xor     eax, eax
0x140022362  mov     [rbp+380h+var_3F0], r9d
0x140022366  xorps   xmm0, xmm0
0x140022369  mov     [rbp+380h+SidToCheck], rax
0x14002236d  mov     edi, eax
0x14002236f  mov     dword ptr [rbp+380h+pIdentifierAuthority.Value], eax
0x140022372  movups  xmmword ptr [rbp+380h+PropertyBuffer], xmm0
0x140022376  mov     [rsp+480h+var_414], eax
0x14002237a  mov     r13d, r9d
0x14002237d  mov     [rsp+480h+pdnDevInst], eax
0x140022381  mov     rbx, r8
0x140022384  mov     [rsp+480h+PropertyType], eax
0x140022388  mov     r12, rdx
0x14002238b  mov     [rsp+480h+PropertyBufferSize], eax
0x14002238f  mov     r15, rcx
0x140022392  mov     [rbp+380h+lpString2], rdx
0x140022396  mov     word ptr [rbp+380h+pIdentifierAuthority.Value+4], 500h
0x14002239c  call    cs:__imp_DevRtlGetThreadLogToken
0x1400223a2  mov     edx, 220h; nSubAuthority1
0x1400223a7  mov     rcx, r15; TokenHandle
0x1400223aa  mov     rsi, rax
0x1400223ad  call    pSetupTokenHasBuiltinGroup
0x1400223b2  mov     edx, 1
0x1400223b7  mov     [rsp+480h+var_420], eax
0x1400223bb  mov     r14d, eax
0x1400223be  test    dl, r13b
0x1400223c1  jnz     short loc_1400223CB
0x1400223c3  xor     r13d, r13d
0x1400223c6  jmp     loc_14002246E
0x1400223cb  xor     ecx, ecx
0x1400223cd  test    eax, eax
0x1400223cf  jnz     short loc_1400223F1
0x1400223d1  mov     edx, 221h; nSubAuthority1
0x1400223d6  mov     rcx, r15; TokenHandle
0x1400223d9  call    pSetupTokenHasBuiltinGroup
0x1400223de  xor     ecx, ecx
0x1400223e0  test    eax, eax
0x1400223e2  jnz     short loc_1400223EC
0x1400223e4  lea     edi, [rcx+5]
0x1400223e7  jmp     loc_140022B86
0x1400223ec  mov     edx, 1; nSubAuthorityCount
0x1400223f1  lea     rax, [rbp+380h+SidToCheck]
0x1400223f5  xor     r9d, r9d; nSubAuthority1
0x1400223f8  mov     [rsp+480h+pSid], rax; pSid
0x1400223fd  mov     r14d, ecx
0x140022400  mov     [rsp+480h+nSubAuthority7], ecx; nSubAuthority7
0x140022404  mov     r13d, edx
0x140022407  mov     [rsp+480h+nSubAuthority6], ecx; nSubAuthority6
0x14002240b  mov     [rsp+480h+nSubAuthority5], ecx; nSubAuthority5
0x14002240f  lea     r8d, [r9+4]; nSubAuthority0
0x140022413  mov     [rsp+480h+nSubAuthority4], ecx; nSubAuthority4
0x140022417  mov     [rsp+480h+nSubAuthority3], ecx; nSubAuthority3
0x14002241b  mov     [rsp+480h+nSubAuthority2], ecx; nSubAuthority2
0x14002241f  lea     rcx, [rbp+380h+pIdentifierAuthority]; pIdentifierAuthority
0x140022423  call    cs:__imp_AllocateAndInitializeSid
0x140022429  test    eax, eax
0x14002242b  jz      short loc_14002244C
0x14002242d  mov     rdx, [rbp+380h+SidToCheck]; SidToCheck
0x140022431  mov     rcx, r15; TokenHandle
0x140022434  call    pSetupTokenHasGroupSID
0x140022439  mov     rcx, [rbp+380h+SidToCheck]; pSid
0x14002243d  xor     r14d, r14d
0x140022440  test    eax, eax
0x140022442  setnz   r14b
0x140022446  call    cs:__imp_FreeSid
0x14002244c  call    ?PnpPolAllowAdminDeviceInstall@@YAHXZ; PnpPolAllowAdminDeviceInstall(void)
0x140022451  test    eax, eax
0x140022453  jz      short loc_140022464
0x140022455  cmp     [rsp+480h+var_420], edi
0x140022459  jz      short loc_140022464
0x14002245b  test    r14d, r14d
0x14002245e  jnz     loc_140022B86
0x140022464  mov     r14d, [rsp+480h+var_420]
0x140022469  mov     edx, 1
0x14002246e  test    r12, r12
0x140022471  jnz     short loc_14002247D
0x140022473  lea     edi, [r12+57h]
0x140022478  jmp     loc_140022B86
0x14002247d  mov     r8d, edx; ulFlags
0x140022480  lea     rcx, [rsp+480h+pdnDevInst]; pdnDevInst
0x140022485  mov     rdx, r12; pDeviceID
0x140022488  call    cs:__imp_CM_Locate_DevNodeW
0x14002248e  test    eax, eax
0x140022490  jz      short loc_1400224A6
0x140022492  mov     edx, 0Dh; DefaultErr
0x140022497  mov     ecx, eax; CmReturnCode
0x140022499  call    cs:__imp_CM_MapCrToWin32Err
0x14002249f  mov     edi, eax
0x1400224a1  jmp     loc_140022B86
0x1400224a6  mov     r12d, [rbp+380h+var_3F0]
0x1400224aa  and     r12d, 80h
0x1400224b1  test    rbx, rbx
0x1400224b4  jnz     short loc_14002251F
0x1400224b6  mov     [rsp+480h+var_404], edi
0x1400224ba  test    r12d, r12d
0x1400224bd  jz      loc_14002258C
0x1400224c3  mov     ecx, [rsp+480h+pdnDevInst]; dnDevInst
0x1400224c7  lea     rax, [rsp+480h+PropertyBufferSize]
0x1400224cc  mov     [rsp+480h+nSubAuthority3], edi; ulFlags
0x1400224d0  lea     r9, [rbp+380h+PropertyBuffer]; PropertyBuffer
0x1400224d4  lea     r8, [rsp+480h+PropertyType]; PropertyType
0x1400224d9  mov     qword ptr [rsp+480h+nSubAuthority2], rax; PropertyBufferSize
0x1400224de  lea     rdx, DEVPKEY_Device_ClassGuid; PropertyKey
0x1400224e5  mov     [rsp+480h+PropertyBufferSize], 10h
0x1400224ed  call    cs:__imp_CM_Get_DevNode_PropertyW
0x1400224f3  test    eax, eax
0x1400224f5  jz      short loc_14002250E
0x1400224f7  lea     edx, [rbx+0Dh]; DefaultErr
0x1400224fa  mov     ecx, eax; CmReturnCode
0x1400224fc  call    cs:__imp_CM_MapCrToWin32Err
0x140022502  mov     edi, eax
0x140022504  test    eax, eax
0x140022506  jnz     loc_140022B86
0x14002250c  jmp     short loc_14002258C
0x14002250e  cmp     [rsp+480h+PropertyType], 0Dh
0x140022513  jz      short loc_14002258C
0x140022515  mov     edi, 70Ch
0x14002251a  jmp     loc_140022B86
0x14002251f  mov     [rsp+480h+nSubAuthority6], edi
0x140022523  lea     rax, [rsp+480h+PropertyBufferSize]
0x140022528  mov     qword ptr [rsp+480h+nSubAuthority5], rax
0x14002252d  lea     r9, DEVPKEY_DriverPackage_ClassGuid
0x140022534  lea     rax, [rbp+380h+PropertyBuffer]
0x140022538  mov     [rsp+480h+nSubAuthority4], 10h
0x140022540  mov     qword ptr [rsp+480h+nSubAuthority3], rax
0x140022545  mov     r8, rbx
0x140022548  lea     rax, [rsp+480h+PropertyType]
0x14002254d  mov     edx, 2
0x140022552  xor     ecx, ecx
0x140022554  mov     qword ptr [rsp+480h+nSubAuthority2], rax; unsigned int
0x140022559  call    cs:__imp_DriverStoreGetObjectPropertyW
0x14002255f  test    eax, eax
0x140022561  jnz     short loc_14002256E
0x140022563  call    cs:__imp_GetLastError
0x140022569  jmp     loc_14002249F
0x14002256e  cmp     [rsp+480h+PropertyType], 0Dh
0x140022573  jnz     loc_140022B81
0x140022579  cmp     [rsp+480h+PropertyBufferSize], 10h
0x14002257e  mov     [rsp+480h+var_404], 1
0x140022586  jnz     loc_140022B81
0x14002258c  xor     r15d, r15d
0x14002258f  lea     rcx, [rbp+380h+PropertyBuffer]
0x140022593  mov     [rsp+480h+var_410], r15d
0x140022598  call    SpUtilsIsGuidNull
0x14002259d  test    eax, eax
0x14002259f  jnz     short loc_1400225C1
0x1400225a1  lea     rdx, [rbp+380h+String2]
0x1400225a5  lea     rcx, [rbp+380h+PropertyBuffer]
0x1400225a9  call    SpUtilsStringFromGuid
0x1400225ae  mov     edi, eax
0x1400225b0  test    eax, eax
0x1400225b2  jnz     loc_140022B86
0x1400225b8  lea     r15d, [rax+1]
0x1400225bc  mov     [rsp+480h+var_410], r15d
0x1400225c1  test    r13d, r13d
0x1400225c4  jnz     short loc_1400225DE
0x1400225c6  mov     rcx, [rbp+380h+lpString2]; unsigned __int16 *
0x1400225ca  lea     r8, [rbp+380h+PropertyBuffer]; struct _GUID *
0x1400225ce  mov     rdx, rbx; unsigned __int16 *
0x1400225d1  call    ?PnpPolIsDevicePolicyExempt@@YAHPEBG0PEAU_GUID@@@Z; PnpPolIsDevicePolicyExempt(ushort const *,ushort const *,_GUID *)
0x1400225d6  test    eax, eax
0x1400225d8  jnz     loc_140022B86
0x1400225de  test    r12d, r12d
0x1400225e1  jnz     short loc_14002262C
0x1400225e3  mov     ecx, [rsp+480h+pdnDevInst]; unsigned int
0x1400225e7  call    ?PnpPolIsDeviceDriverUpdated@@YAHK@Z; PnpPolIsDeviceDriverUpdated(ulong)
0x1400225ec  test    eax, eax
0x1400225ee  jz      short loc_14002262C
0x1400225f0  cmp     [rsp+480h+var_404], r12d
0x1400225f5  jz      short loc_14002260C
0x1400225f7  mov     ecx, [rsp+480h+pdnDevInst]; dnDevInst
0x1400225fb  lea     r8d, [r12+3]
0x140022600  mov     rdx, rbx; String2
0x140022603  call    DevUtilsInfInstalledOnDevNode
0x140022608  test    eax, eax
0x14002260a  jz      short loc_14002262C
0x14002260c  lea     r9, aDeviceInstalla_4; "Device installation policy not enforced"...
0x140022613  mov     r8d, 5
0x140022619  mov     edx, 800000h
0x14002261e  mov     rcx, rsi
0x140022621  call    cs:__imp_DevRtlWriteTextLog
0x140022627  jmp     loc_140022B86
0x14002262c  test    r13d, r13d
0x14002262f  jz      short loc_14002269B
0x140022631  test    r14d, r14d
0x140022634  jnz     short loc_14002269B
0x140022636  cmp     [rsp+480h+var_404], r14d
0x14002263b  jnz     short loc_140022651
0x14002263d  lea     r9, aOnlyAdministra; "Only administrators are allowed to inst"...
0x140022644  mov     edi, 5
0x140022649  mov     r8d, 2
0x14002264f  jmp     short loc_140022619
0x140022651  test    r15d, r15d
0x140022654  jz      short loc_140022663
0x140022656  lea     rcx, [rbp+380h+PropertyBuffer]; struct _GUID *
0x14002265a  call    ?PnpPolIsClassInUserDriverAllowList@@YAHPEAU_GUID@@@Z; PnpPolIsClassInUserDriverAllowList(_GUID *)
0x14002265f  test    eax, eax
0x140022661  jz      short loc_14002266F
0x140022663  mov     rcx, rbx; unsigned __int16 *
0x140022666  call    ?PnpPolIsDriverSignedByTrustedPublisher@@YAHPEBG@Z; PnpPolIsDriverSignedByTrustedPublisher(ushort const *)
0x14002266b  test    eax, eax
0x14002266d  jnz     short loc_140022678
0x14002266f  lea     r9, aInstallationOf_2; "Installation of device is restricted fo"...
0x140022676  jmp     short loc_140022644
0x140022678  mov     edx, [rsp+480h+pdnDevInst]
0x14002267c  xor     r9d, r9d
0x14002267f  mov     r8, rbx
0x140022682  xor     ecx, ecx
0x140022684  call    PnpUtilsDriverPackageAppliesToDevNode
0x140022689  test    eax, eax
0x14002268b  jnz     short loc_14002269B
0x14002268d  mov     edi, 0E0000248h
0x140022692  lea     r9, aInstallationOf; "Installation of device is restricted fo"...
0x140022699  jmp     short loc_140022649
0x14002269b  xor     r13d, r13d
0x14002269e  xor     r14d, r14d
0x1400226a1  mov     [rbp+380h+var_400], r13d
0x1400226a5  xor     r15d, r15d
0x1400226a8  mov     [rsp+480h+var_420], r13d
0x1400226ad  mov     [rbp+380h+var_3FC], r13d
0x1400226b1  mov     [rbp+380h+var_3E8], r13d
0x1400226b5  call    ?PnpPolAllowDenyLayeredEvaluation@@YAHXZ; PnpPolAllowDenyLayeredEvaluation(void)
0x1400226ba  mov     ecx, [rsp+480h+pdnDevInst]; unsigned int
0x1400226be  mov     [rbp+380h+var_3EC], eax
0x1400226c1  call    ?PnpPolIsDeviceRemovable@@YAHK@Z; PnpPolIsDeviceRemovable(ulong)
0x1400226c6  test    eax, eax
0x1400226c8  jz      short loc_1400226DB
0x1400226ca  call    ?PnpPolRestrictRemovableDevices@@YAHXZ; PnpPolRestrictRemovableDevices(void)
0x1400226cf  test    eax, eax
0x1400226d1  lea     ebx, [r14+1]
0x1400226d5  cmovnz  r15d, ebx
0x1400226d9  jmp     short loc_1400226E0
0x1400226db  mov     ebx, 1
0x1400226e0  mov     ecx, [rsp+480h+pdnDevInst]; dnDevInst
0x1400226e4  lea     r9, [rbp+380h+var_360]; unsigned __int16 *
0x1400226e8  xor     r8d, r8d; int *
0x1400226eb  mov     [rbp+380h+var_3E4], r15d
0x1400226ef  xor     edx, edx; int
0x1400226f1  call    ?PnpPolIsDeviceInDeviceIDsList@@YAHKHPEAHPEAGK@Z; PnpPolIsDeviceInDeviceIDsList(ulong,int,int *,ushort *,ulong)
0x1400226f6  mov     ecx, eax
0x1400226f8  mov     [rbp+380h+var_3F8], eax
0x1400226fb  xor     eax, eax
0x1400226fd  lea     r9, [rbp+380h+var_1D0]; unsigned __int16 *
0x140022704  test    ecx, ecx
0x140022706  lea     r8, [rsp+480h+var_414]; int *
0x14002270b  mov     ecx, [rsp+480h+pdnDevInst]; dnDevInst
0x14002270f  mov     edx, ebx; int
0x140022711  setnz   al
0x140022714  mov     [rsp+480h+var_418], eax
0x140022718  call    ?PnpPolIsDeviceInDeviceIDsList@@YAHKHPEAHPEAGK@Z; PnpPolIsDeviceInDeviceIDsList(ulong,int,int *,ushort *,ulong)
0x14002271d  test    eax, eax
0x14002271f  jz      short loc_140022733
0x140022721  test    r12d, r12d
0x140022724  jz      short loc_14002272D
0x140022726  cmp     [rsp+480h+var_414], r13d
0x14002272b  jz      short loc_140022733
0x14002272d  mov     r15d, ebx
0x140022730  mov     [rbp+380h+var_400], ebx
0x140022733  mov     rcx, [rbp+380h+lpString2]; lpString2
0x140022737  xor     r8d, r8d; int *
0x14002273a  xor     edx, edx; int
0x14002273c  call    ?PnpPolIsDeviceInInstanceIDsList@@YAHPEBGHPEAH@Z; PnpPolIsDeviceInInstanceIDsList(ushort const *,int,int *)
0x140022741  mov     ecx, [rsp+480h+var_418]
0x140022745  lea     r8, [rsp+480h+var_414]; int *
0x14002274a  test    eax, eax
0x14002274c  mov     [rbp+380h+var_3F4], eax
0x14002274f  mov     eax, 1
0x140022754  cmovnz  ecx, eax
0x140022757  mov     edx, eax; int
0x140022759  mov     [rsp+480h+var_418], ecx
0x14002275d  mov     rcx, [rbp+380h+lpString2]; lpString2
0x140022761  call    ?PnpPolIsDeviceInInstanceIDsList@@YAHPEBGHPEAH@Z; PnpPolIsDeviceInInstanceIDsList(ushort const *,int,int *)
0x140022766  test    eax, eax
0x140022768  jz      short loc_140022781
0x14002276a  test    r12d, r12d
0x14002276d  jz      short loc_140022776
0x14002276f  cmp     [rsp+480h+var_414], r13d
0x140022774  jz      short loc_140022781
0x140022776  mov     eax, 1
0x14002277b  mov     r15d, eax
0x14002277e  mov     [rbp+380h+var_3FC], eax
0x140022781  cmp     [rsp+480h+var_410], r13d
0x140022786  jz      short loc_1400227F1
0x140022788  lea     rcx, [rbp+380h+String2]; unsigned __int16 *
0x14002278c  call    ?PnpPolIsClassInDeviceAllowList@@YAHPEBG@Z; PnpPolIsClassInDeviceAllowList(ushort const *)
0x140022791  mov     ebx, [rsp+480h+var_418]
0x140022795  lea     rdx, [rsp+480h+var_414]; int *
  ... truncated ...
```
