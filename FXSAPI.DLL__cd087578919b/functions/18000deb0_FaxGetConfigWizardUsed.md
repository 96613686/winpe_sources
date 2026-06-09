# FaxGetConfigWizardUsed

- ea: `0x18000deb0`
- end: `0x18000e02e`
- name: `FaxGetConfigWizardUsed`
- size: `382`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000abe4`
- `0x18000ac14`
- `0x18000deb0`
- `0x18002d770`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18000df36`
- `KERNEL32!SetLastError` at `0x18000df36`
- `ADVAPI32!RegCloseKey` at `0x18000dfdc`
- `ADVAPI32!RegCloseKey` at `0x18000dfdc`
- `ADVAPI32!RegOpenKeyExW` at `0x18000df6a`
- `ADVAPI32!RegOpenKeyExW` at `0x18000df6a`

## pseudocode

```c
__int64 __fastcall FaxGetConfigWizardUsed(_DWORD *a1)
{
  _QWORD *v2; // rcx
  DWORD v3; // ecx
  unsigned int v5; // eax
  DWORD v6; // ebx
  int RegistryDwordDefault; // eax
  unsigned int v8; // eax
  int Data; // [rsp+50h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+10h] BYREF

  hKey = 0;
  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 299, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  if ( !a1 )
  {
    if ( v2 != &WPP_GLOBAL_Control && (*((_DWORD *)v2 + 7) & 0x1000) != 0 && *((_BYTE *)v2 + 25) >= 2u )
      WPP_SF_(v2[2], 300, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids);
    v3 = 87;
LABEL_11:
    SetLastError(v3);
    return 0;
  }
  v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Fax\\Client", 0, 0x20119u, &hKey);
  v6 = v5;
  if ( v5 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 301, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids, v5);
    }
    v3 = v6;
    goto LABEL_11;
  }
  Data = 0;
  RegistryDwordDefault = GetRegistryDwordDefault(hKey, L"CfgWzdrDevice", (BYTE *)&Data);
  *a1 = RegistryDwordDefault != 0 ? Data : 0;
  v8 = RegCloseKey(hKey);
  if ( v8
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 302, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids, v8);
  }
  return 1;
}

```

## disassembly

```asm
0x18000deb0  mov     [rsp+arg_10], rbx
0x18000deb5  push    rbp
0x18000deb6  push    rsi
0x18000deb7  push    rdi
0x18000deb8  sub     rsp, 30h
0x18000debc  mov     rdi, rcx
0x18000debf  mov     [rsp+48h+hKey], 0
0x18000dec8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000decf  lea     rbp, WPP_GLOBAL_Control
0x18000ded6  mov     esi, 1000h
0x18000dedb  cmp     rcx, rbp
0x18000dede  jz      short loc_18000DF07
0x18000dee0  test    [rcx+1Ch], esi
0x18000dee3  jz      short loc_18000DF07
0x18000dee5  cmp     byte ptr [rcx+19h], 5
0x18000dee9  jb      short loc_18000DF07
0x18000deeb  mov     rcx, [rcx+10h]
0x18000deef  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x18000def6  mov     edx, 12Bh
0x18000defb  call    WPP_SF_
0x18000df00  mov     rcx, cs:WPP_GLOBAL_Control
0x18000df07  test    rdi, rdi
0x18000df0a  jnz     short loc_18000DF49
0x18000df0c  cmp     rcx, rbp
0x18000df0f  jz      short loc_18000DF31
0x18000df11  test    [rcx+1Ch], esi
0x18000df14  jz      short loc_18000DF31
0x18000df16  cmp     byte ptr [rcx+19h], 2
0x18000df1a  jb      short loc_18000DF31
0x18000df1c  mov     rcx, [rcx+10h]
0x18000df20  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x18000df27  mov     edx, 12Ch
0x18000df2c  call    WPP_SF_
0x18000df31  mov     ecx, 57h ; 'W'; dwErrCode
0x18000df36  call    cs:__imp_SetLastError
0x18000df3d  nop     dword ptr [rax+rax+00h]
0x18000df42  xor     eax, eax
0x18000df44  jmp     loc_18000E020
0x18000df49  lea     rax, [rsp+48h+hKey]
0x18000df4e  mov     r9d, 20119h; samDesired
0x18000df54  xor     r8d, r8d; ulOptions
0x18000df57  mov     [rsp+48h+phkResult], rax; phkResult
0x18000df5c  lea     rdx, SubKey; "Software\\Microsoft\\Fax\\Client"
0x18000df63  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000df6a  call    cs:__imp_RegOpenKeyExW
0x18000df71  nop     dword ptr [rax+rax+00h]
0x18000df76  mov     ebx, eax
0x18000df78  test    eax, eax
0x18000df7a  jz      short loc_18000DFAF
0x18000df7c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000df83  cmp     rcx, rbp
0x18000df86  jz      short loc_18000DFAB
0x18000df88  test    [rcx+1Ch], esi
0x18000df8b  jz      short loc_18000DFAB
0x18000df8d  cmp     byte ptr [rcx+19h], 2
0x18000df91  jb      short loc_18000DFAB
0x18000df93  mov     rcx, [rcx+10h]
0x18000df97  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x18000df9e  mov     edx, 12Dh
0x18000dfa3  mov     r9d, eax
0x18000dfa6  call    WPP_SF_d
0x18000dfab  mov     ecx, ebx
0x18000dfad  jmp     short loc_18000DF36
0x18000dfaf  mov     rcx, [rsp+48h+hKey]; hKey
0x18000dfb4  lea     r8, [rsp+48h+Data]; lpData
0x18000dfb9  lea     rdx, aCfgwzdrdevice; "CfgWzdrDevice"
0x18000dfc0  mov     [rsp+48h+Data], 0
0x18000dfc8  call    GetRegistryDwordDefault
0x18000dfcd  neg     eax
0x18000dfcf  sbb     ecx, ecx
0x18000dfd1  and     ecx, [rsp+48h+Data]
0x18000dfd5  mov     [rdi], ecx
0x18000dfd7  mov     rcx, [rsp+48h+hKey]; hKey
0x18000dfdc  call    cs:__imp_RegCloseKey
0x18000dfe3  nop     dword ptr [rax+rax+00h]
0x18000dfe8  test    eax, eax
0x18000dfea  jz      short loc_18000E01B
0x18000dfec  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dff3  cmp     rcx, rbp
0x18000dff6  jz      short loc_18000E01B
0x18000dff8  test    [rcx+1Ch], esi
0x18000dffb  jz      short loc_18000E01B
0x18000dffd  cmp     byte ptr [rcx+19h], 2
0x18000e001  jb      short loc_18000E01B
0x18000e003  mov     rcx, [rcx+10h]
0x18000e007  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x18000e00e  mov     edx, 12Eh
0x18000e013  mov     r9d, eax
0x18000e016  call    WPP_SF_d
0x18000e01b  mov     eax, 1
0x18000e020  mov     rbx, [rsp+48h+arg_10]
0x18000e025  add     rsp, 30h
0x18000e029  pop     rdi
0x18000e02a  pop     rsi
0x18000e02b  pop     rbp
0x18000e02c  retn
```
