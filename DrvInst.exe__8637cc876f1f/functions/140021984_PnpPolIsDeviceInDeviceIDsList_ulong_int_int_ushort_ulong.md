# PnpPolIsDeviceInDeviceIDsList(ulong,int,int *,ushort *,ulong)

- ea: `0x140021984`
- end: `0x140021c1f`
- name: `?PnpPolIsDeviceInDeviceIDsList@@YAHKHPEAHPEAGK@Z`
- size: `667`
- prototype: `__int64 __fastcall(DEVINST dnDevInst, unsigned int, int *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140022330`

## callees

- `0x14000c018`
- `0x140021984`
- `0x1400220cc`
- `0x1400242bc`
- `0x1400242e4`
- `0x140024650`
- `0x140045eea`
- `0x140045f30`

## import_xrefs

- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x140021b6d`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x140021b6d`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_PropertyW` at `0x140021b5c`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_PropertyW` at `0x140021b5c`

## string_xrefs

- `0x140021a16`: `Software\Policies\Microsoft\Windows\DeviceInstall`
- `0x140021a7d`: `Software\Policies\Microsoft\Windows\DeviceInstall`
- `0x140021ad5`: `Software\Policies\Microsoft\Windows\DeviceInstall`

## pseudocode

```c
__int64 __fastcall PnpPolIsDeviceInDeviceIDsList(DEVINST dnDevInst, unsigned int a2, int *a3, unsigned __int16 *a4)
{
  unsigned int v4; // esi
  int PolicyListStrings; // eax
  int PolicyValue; // eax
  int v11; // ecx
  int v12; // eax
  int v13; // edi
  const DEVPROPKEY *v14; // rdx
  CONFIGRET DevNode_PropertyW; // eax
  DWORD v16; // eax
  bool v17; // zf
  unsigned __int16 **v18; // r9
  unsigned __int64 *PropertyBufferSize; // [rsp+20h] [rbp-E0h]
  ULONG v21; // [rsp+30h] [rbp-D0h] BYREF
  DEVPROPTYPE PropertyType; // [rsp+34h] [rbp-CCh] BYREF
  LPVOID lpMem; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 *v24; // [rsp+40h] [rbp-C0h] BYREF
  BYTE PropertyBuffer[2]; // [rsp+50h] [rbp-B0h] BYREF
  int v26; // [rsp+84Ch] [rbp+74Ch]

  v4 = 0;
  lpMem = 0;
  v24 = 0;
  PropertyType = 0;
  v21 = 0;
  if ( a4 )
    *a4 = 0;
  if ( a2 )
  {
    if ( dword_140063FFC && dword_140063FF8
      || (PolicyListStrings = pSetupGetPolicyListStrings(
                                dnDevInst,
                                (unsigned int)L"Software\\Policies\\Microsoft\\Windows\\DeviceInstall",
                                (_DWORD)a3,
                                (unsigned int)L"DenyDeviceIDs",
                                (__int64)&lpMem),
          PolicyListStrings == 2) )
    {
      dword_140063FFC = 1;
      dword_140063FF8 = 1;
      goto LABEL_34;
    }
    if ( !PolicyListStrings )
    {
      dword_140063FFC = 1;
      if ( a3 )
      {
        if ( dword_140063FEC )
        {
          v11 = dword_140063FE8;
        }
        else
        {
          PolicyValue = pSetupGetPolicyValue(
                          -2147483646,
                          L"Software\\Policies\\Microsoft\\Windows\\DeviceInstall",
                          L"Restrictions",
                          L"DenyDeviceIDsRetroactive",
                          0,
                          1);
          dword_140063FEC = 1;
          v11 = PolicyValue == 1;
          dword_140063FE8 = v11;
        }
        *a3 = v11;
      }
      goto LABEL_20;
    }
  }
  else
  {
    if ( dword_140063FF4 && dword_140063FF0
      || (v12 = pSetupGetPolicyListStrings(
                  dnDevInst,
                  (unsigned int)L"Software\\Policies\\Microsoft\\Windows\\DeviceInstall",
                  (_DWORD)a3,
                  (unsigned int)L"AllowDeviceIDs",
                  (__int64)&lpMem),
          v12 == 2) )
    {
      dword_140063FF4 = 1;
      dword_140063FF0 = 1;
      goto LABEL_34;
    }
    if ( !v12 )
    {
      dword_140063FF4 = 1;
LABEL_20:
      v13 = 0;
      while ( 1 )
      {
        v21 = 2048;
        memset_0(PropertyBuffer, 0, 0x800u);
        v14 = &DEVPKEY_Device_HardwareIds;
        if ( v13 )
          v14 = &DEVPKEY_Device_CompatibleIds;
        DevNode_PropertyW = CM_Get_DevNode_PropertyW(dnDevInst, v14, &PropertyType, PropertyBuffer, &v21, 0);
        if ( DevNode_PropertyW )
        {
          v16 = CM_MapCrToWin32Err(DevNode_PropertyW, 0xDu);
          if ( v16 == 1168 )
          {
            *(_WORD *)PropertyBuffer = 0;
            goto LABEL_30;
          }
          v17 = v16 == 0;
        }
        else
        {
          v17 = PropertyType == 8210;
        }
        if ( !v17 )
          break;
        v26 = 0;
        if ( (unsigned int)pSetupMultiSzContainsAnyString((PCNZWCH)lpMem, (PCNZWCH)PropertyBuffer, (__int64)&v24) )
        {
          v4 = 1;
          StringCchCopyExW(a4, 0xC8u, v24, v18, PropertyBufferSize, 0x100u);
          goto LABEL_34;
        }
LABEL_30:
        if ( (unsigned int)++v13 >= 2 )
          goto LABEL_34;
      }
    }
  }
  v4 = a2;
LABEL_34:
  if ( lpMem )
    pSetupFreePolicyListStrings(lpMem);
  return v4;
}

```

## disassembly

```asm
0x140021984  mov     [rsp-8+arg_8], rsi
0x140021989  push    rbp
0x14002198a  push    rdi
0x14002198b  push    r12
0x14002198d  push    r14
0x14002198f  push    r15
0x140021991  lea     rbp, [rsp-760h]
0x140021999  sub     rsp, 860h
0x1400219a0  mov     rax, cs:__security_cookie
0x1400219a7  xor     rax, rsp
0x1400219aa  mov     [rbp+780h+var_30], rax
0x1400219b1  xor     esi, esi
0x1400219b3  mov     [rsp+880h+lpMem], 0
0x1400219bc  mov     [rsp+880h+var_840], 0
0x1400219c5  mov     r14, r9
0x1400219c8  mov     [rsp+880h+PropertyType], 0
0x1400219d0  mov     rdi, r8
0x1400219d3  mov     [rsp+880h+var_850], 0
0x1400219db  mov     r15d, edx
0x1400219de  mov     r12d, ecx
0x1400219e1  test    r9, r9
0x1400219e4  jz      short loc_1400219EC
0x1400219e6  xor     eax, eax
0x1400219e8  mov     [r9], ax
0x1400219ec  test    r15d, r15d
0x1400219ef  jz      loc_140021AB4
0x1400219f5  cmp     cs:dword_140063FFC, esi
0x1400219fb  jz      short loc_140021A05
0x1400219fd  cmp     cs:dword_140063FF8, esi
0x140021a03  jnz     short loc_140021A27
0x140021a05  lea     rax, [rsp+880h+lpMem]
0x140021a0a  lea     r9, aDenydeviceids; "DenyDeviceIDs"
0x140021a11  mov     [rsp+880h+PropertyBufferSize], rax
0x140021a16  lea     rdx, aSoftwarePolici_0; "Software\\Policies\\Microsoft\\Windows"...
0x140021a1d  call    pSetupGetPolicyListStrings
0x140021a22  cmp     eax, 2
0x140021a25  jnz     short loc_140021A40
0x140021a27  mov     cs:dword_140063FFC, 1
0x140021a31  mov     cs:dword_140063FF8, 1
0x140021a3b  jmp     loc_140021BE7
0x140021a40  test    eax, eax
0x140021a42  jnz     loc_140021BE4
0x140021a48  mov     cs:dword_140063FFC, 1
0x140021a52  test    rdi, rdi
0x140021a55  jz      loc_140021B11
0x140021a5b  cmp     cs:dword_140063FEC, esi
0x140021a61  jnz     short loc_140021AAA
0x140021a63  mov     [rsp+880h+ulFlags], 1
0x140021a6b  lea     r9, aDenydeviceidsr; "DenyDeviceIDsRetroactive"
0x140021a72  lea     r8, aRestrictions; "Restrictions"
0x140021a79  mov     dword ptr [rsp+880h+PropertyBufferSize], esi
0x140021a7d  lea     rdx, aSoftwarePolici_0; "Software\\Policies\\Microsoft\\Windows"...
0x140021a84  mov     rcx, 0FFFFFFFF80000002h
0x140021a8b  call    pSetupGetPolicyValue
0x140021a90  xor     ecx, ecx
0x140021a92  mov     cs:dword_140063FEC, 1
0x140021a9c  cmp     eax, 1
0x140021a9f  setz    cl
0x140021aa2  mov     cs:dword_140063FE8, ecx
0x140021aa8  jmp     short loc_140021AB0
0x140021aaa  mov     ecx, cs:dword_140063FE8
0x140021ab0  mov     [rdi], ecx
0x140021ab2  jmp     short loc_140021B11
0x140021ab4  cmp     cs:dword_140063FF4, esi
0x140021aba  jz      short loc_140021AC4
0x140021abc  cmp     cs:dword_140063FF0, esi
0x140021ac2  jnz     short loc_140021AE6
0x140021ac4  lea     rax, [rsp+880h+lpMem]
0x140021ac9  lea     r9, aAllowdeviceids; "AllowDeviceIDs"
0x140021ad0  mov     [rsp+880h+PropertyBufferSize], rax
0x140021ad5  lea     rdx, aSoftwarePolici_0; "Software\\Policies\\Microsoft\\Windows"...
0x140021adc  call    pSetupGetPolicyListStrings
0x140021ae1  cmp     eax, 2
0x140021ae4  jnz     short loc_140021AFF
0x140021ae6  mov     cs:dword_140063FF4, 1
0x140021af0  mov     cs:dword_140063FF0, 1
0x140021afa  jmp     loc_140021BE7
0x140021aff  test    eax, eax
0x140021b01  jnz     loc_140021BE4
0x140021b07  mov     cs:dword_140063FF4, 1
0x140021b11  xor     edi, edi
0x140021b13  xor     edx, edx; Val
0x140021b15  mov     [rsp+880h+var_850], 800h
0x140021b1d  mov     r8d, 800h; Size
0x140021b23  lea     rcx, [rsp+880h+PropertyBuffer]; void *
0x140021b28  call    memset_0
0x140021b2d  lea     rax, DEVPKEY_Device_CompatibleIds
0x140021b34  mov     [rsp+880h+ulFlags], esi; ulFlags
0x140021b38  test    edi, edi
0x140021b3a  lea     rdx, DEVPKEY_Device_HardwareIds
0x140021b41  lea     r9, [rsp+880h+PropertyBuffer]; PropertyBuffer
0x140021b46  mov     ecx, r12d; dnDevInst
0x140021b49  cmovnz  rdx, rax; PropertyKey
0x140021b4d  lea     r8, [rsp+880h+PropertyType]; PropertyType
0x140021b52  lea     rax, [rsp+880h+var_850]
0x140021b57  mov     [rsp+880h+PropertyBufferSize], rax; PropertyBufferSize
0x140021b5c  call    cs:__imp_CM_Get_DevNode_PropertyW
0x140021b62  test    eax, eax
0x140021b64  jz      short loc_140021B87
0x140021b66  mov     edx, 0Dh; DefaultErr
0x140021b6b  mov     ecx, eax; CmReturnCode
0x140021b6d  call    cs:__imp_CM_MapCrToWin32Err
0x140021b73  cmp     eax, 490h
0x140021b78  jnz     short loc_140021B83
0x140021b7a  xor     eax, eax
0x140021b7c  mov     word ptr [rsp+880h+PropertyBuffer], ax
0x140021b81  jmp     short loc_140021BB6
0x140021b83  test    eax, eax
0x140021b85  jmp     short loc_140021B8F
0x140021b87  cmp     [rsp+880h+PropertyType], 2012h
0x140021b8f  jnz     short loc_140021BE4
0x140021b91  mov     rcx, [rsp+880h+lpMem]; lpString1
0x140021b96  lea     rdx, [rsp+880h+PropertyBuffer]; lpString2
0x140021b9b  xor     eax, eax
0x140021b9d  mov     [rbp+780h+var_34], eax
0x140021ba3  lea     rax, [rsp+880h+var_840]
0x140021ba8  mov     [rsp+880h+PropertyBufferSize], rax; unsigned __int64 *
0x140021bad  call    pSetupMultiSzContainsAnyString
0x140021bb2  test    eax, eax
0x140021bb4  jnz     short loc_140021BC3
0x140021bb6  inc     edi
0x140021bb8  cmp     edi, 2
0x140021bbb  jb      loc_140021B13
0x140021bc1  jmp     short loc_140021BE7
0x140021bc3  mov     r8, [rsp+880h+var_840]; unsigned __int16 *
0x140021bc8  mov     edx, 0C8h; unsigned __int64
0x140021bcd  mov     rcx, r14; pszDest
0x140021bd0  mov     [rsp+880h+ulFlags], 100h; unsigned int
0x140021bd8  mov     esi, 1
0x140021bdd  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x140021be2  jmp     short loc_140021BE7
0x140021be4  mov     esi, r15d
0x140021be7  mov     rcx, [rsp+880h+lpMem]; lpMem
0x140021bec  test    rcx, rcx
0x140021bef  jz      short loc_140021BF6
0x140021bf1  call    pSetupFreePolicyListStrings
0x140021bf6  mov     eax, esi
0x140021bf8  mov     rcx, [rbp+780h+var_30]
0x140021bff  xor     rcx, rsp; StackCookie
0x140021c02  call    __security_check_cookie
0x140021c07  mov     rsi, [rsp+880h+arg_8]
0x140021c0f  add     rsp, 860h
0x140021c16  pop     r15
0x140021c18  pop     r14
0x140021c1a  pop     r12
0x140021c1c  pop     rdi
0x140021c1d  pop     rbp
0x140021c1e  retn
```
