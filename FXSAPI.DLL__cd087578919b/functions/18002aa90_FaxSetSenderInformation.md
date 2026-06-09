# FaxSetSenderInformation

- ea: `0x18002aa90`
- end: `0x18002ad83`
- name: `FaxSetSenderInformation`
- size: `755`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x18000abe4`
- `0x18002aa90`
- `0x18002d4cc`
- `0x18002d854`
- `0x18002d934`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18002acc7`
- `ADVAPI32!RegCloseKey` at `0x18002ad0c`
- `ADVAPI32!RegCloseKey` at `0x18002acc7`
- `ADVAPI32!RegCloseKey` at `0x18002ad0c`

## string_xrefs

- `0x18002ab91`: `Company`

## pseudocode

```c
__int64 __fastcall FaxSetSenderInformation(__int64 a1)
{
  _DWORD *v2; // rcx
  __int64 v3; // rdx
  unsigned int v4; // ebx
  HKEY v5; // rax
  HKEY v6; // rsi
  HKEY v7; // rax
  HKEY v8; // rdi

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_e8cc5d09478f38214c8caffa112c128f_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  if ( !a1 )
  {
    if ( v2 == (_DWORD *)&WPP_GLOBAL_Control || (v2[7] & 0x1000) == 0 || *((_BYTE *)v2 + 25) < 2u )
      return (unsigned int)-2147024809;
    v3 = 11;
LABEL_10:
    WPP_SF_(*((_QWORD *)v2 + 2), v3, WPP_e8cc5d09478f38214c8caffa112c128f_Traceguids);
    return (unsigned int)-2147024809;
  }
  if ( *(_DWORD *)a1 != 136 )
  {
    if ( v2 == (_DWORD *)&WPP_GLOBAL_Control || (v2[7] & 0x1000) == 0 || *((_BYTE *)v2 + 25) < 2u )
      return (unsigned int)-2147024809;
    v3 = 12;
    goto LABEL_10;
  }
  v5 = OpenRegistryKey(HKEY_CURRENT_USER, L"Software\\Microsoft\\Fax\\UserInfo", 1, 0xF003Fu);
  v6 = v5;
  if ( v5 )
  {
    v4 = 0;
    SetRegistryStringValue(v5, 1u, L"FullName", *(const BYTE **)(a1 + 8));
    SetRegistryStringValue(v6, 1u, L"FaxNumber", *(const BYTE **)(a1 + 16));
    SetRegistryStringValue(v6, 1u, L"Company", *(const BYTE **)(a1 + 24));
    SetRegistryStringValue(v6, 1u, L"Address", *(const BYTE **)(a1 + 32));
    SetRegistryStringValue(v6, 1u, L"City", *(const BYTE **)(a1 + 40));
    SetRegistryStringValue(v6, 1u, L"State", *(const BYTE **)(a1 + 48));
    SetRegistryStringValue(v6, 1u, L"ZIP", *(const BYTE **)(a1 + 56));
    SetRegistryStringValue(v6, 1u, L"Country", *(const BYTE **)(a1 + 64));
    SetRegistryStringValue(v6, 1u, L"Title", *(const BYTE **)(a1 + 72));
    SetRegistryStringValue(v6, 1u, L"Department", *(const BYTE **)(a1 + 80));
    SetRegistryStringValue(v6, 1u, L"Office", *(const BYTE **)(a1 + 88));
    SetRegistryStringValue(v6, 1u, L"HomePhone", *(const BYTE **)(a1 + 96));
    SetRegistryStringValue(v6, 1u, L"OfficePhone", *(const BYTE **)(a1 + 104));
    SetRegistryStringValue(v6, 1u, L"BillingCode", *(const BYTE **)(a1 + 120));
    SetRegistryStringValue(v6, 1u, L"Mailbox", *(const BYTE **)(a1 + 112));
    SetRegistryStringValue(v6, 1u, L"TSID", *(const BYTE **)(a1 + 128));
    RegCloseKey(v6);
    v7 = OpenRegistryKey(HKEY_CURRENT_USER, L"Software\\Microsoft\\Fax\\Setup", 1, 0xF003Fu);
    v8 = v7;
    if ( v7 )
    {
      SetRegistryDword(v7, L"CfgWzdrUserInfo", 1);
      RegCloseKey(v8);
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
           && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_e8cc5d09478f38214c8caffa112c128f_Traceguids);
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_e8cc5d09478f38214c8caffa112c128f_Traceguids);
    }
    return (unsigned int)-2147467259;
  }
  return v4;
}

```

## disassembly

```asm
0x18002aa90  push    rbx
0x18002aa92  push    rbp
0x18002aa93  push    rsi
0x18002aa94  push    rdi
0x18002aa95  push    r12
0x18002aa97  push    r14
0x18002aa99  push    r15
0x18002aa9b  sub     rsp, 30h
0x18002aa9f  mov     rdi, rcx
0x18002aaa2  mov     rcx, cs:WPP_GLOBAL_Control
0x18002aaa9  lea     r14, WPP_GLOBAL_Control
0x18002aab0  lea     r15, WPP_e8cc5d09478f38214c8caffa112c128f_Traceguids
0x18002aab7  mov     ebp, 1000h
0x18002aabc  cmp     rcx, r14
0x18002aabf  jz      short loc_18002AAE4
0x18002aac1  test    [rcx+1Ch], ebp
0x18002aac4  jz      short loc_18002AAE4
0x18002aac6  cmp     byte ptr [rcx+19h], 5
0x18002aaca  jb      short loc_18002AAE4
0x18002aacc  mov     rcx, [rcx+10h]
0x18002aad0  mov     edx, 0Ah
0x18002aad5  mov     r8, r15
0x18002aad8  call    WPP_SF_
0x18002aadd  mov     rcx, cs:WPP_GLOBAL_Control
0x18002aae4  test    rdi, rdi
0x18002aae7  jnz     short loc_18002AB12
0x18002aae9  cmp     rcx, r14
0x18002aaec  jz      short loc_18002AB08
0x18002aaee  test    [rcx+1Ch], ebp
0x18002aaf1  jz      short loc_18002AB08
0x18002aaf3  cmp     byte ptr [rcx+19h], 2
0x18002aaf7  jb      short loc_18002AB08
0x18002aaf9  lea     edx, [rdi+0Bh]
0x18002aafc  mov     rcx, [rcx+10h]
0x18002ab00  mov     r8, r15
0x18002ab03  call    WPP_SF_
0x18002ab08  mov     ebx, 80070057h
0x18002ab0d  jmp     loc_18002AD71
0x18002ab12  cmp     dword ptr [rdi], 88h
0x18002ab18  jz      short loc_18002AB31
0x18002ab1a  cmp     rcx, r14
0x18002ab1d  jz      short loc_18002AB08
0x18002ab1f  test    [rcx+1Ch], ebp
0x18002ab22  jz      short loc_18002AB08
0x18002ab24  cmp     byte ptr [rcx+19h], 2
0x18002ab28  jb      short loc_18002AB08
0x18002ab2a  mov     edx, 0Ch
0x18002ab2f  jmp     short loc_18002AAFC
0x18002ab31  mov     r12d, 1
0x18002ab37  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Fax\\UserInfo"
0x18002ab3e  mov     r8d, r12d
0x18002ab41  mov     r9d, 0F003Fh
0x18002ab47  mov     rcx, 0FFFFFFFF80000001h
0x18002ab4e  call    OpenRegistryKey
0x18002ab53  mov     rsi, rax
0x18002ab56  test    rax, rax
0x18002ab59  jz      loc_18002AD44
0x18002ab5f  mov     r9, [rdi+8]; unsigned __int16 *
0x18002ab63  lea     r8, ValueName; "FullName"
0x18002ab6a  mov     edx, r12d; unsigned int
0x18002ab6d  mov     rcx, rax; HKEY
0x18002ab70  xor     ebx, ebx
0x18002ab72  call    ?SetRegistryStringValue@@YAHPEAUHKEY__@@KPEBG1J@Z; SetRegistryStringValue(HKEY__ *,ulong,ushort const *,ushort const *,long)
0x18002ab77  mov     r9, [rdi+10h]; unsigned __int16 *
0x18002ab7b  lea     r8, aFaxnumber; "FaxNumber"
0x18002ab82  mov     edx, r12d; unsigned int
0x18002ab85  mov     rcx, rsi; HKEY
0x18002ab88  call    ?SetRegistryStringValue@@YAHPEAUHKEY__@@KPEBG1J@Z; SetRegistryStringValue(HKEY__ *,ulong,ushort const *,ushort const *,long)
0x18002ab8d  mov     r9, [rdi+18h]; unsigned __int16 *
0x18002ab91  lea     r8, aCompany; "Company"
0x18002ab98  mov     edx, r12d; unsigned int
0x18002ab9b  mov     rcx, rsi; HKEY
0x18002ab9e  call    ?SetRegistryStringValue@@YAHPEAUHKEY__@@KPEBG1J@Z; SetRegistryStringValue(HKEY__ *,ulong,ushort const *,ushort const *,long)
0x18002aba3  mov     r9, [rdi+20h]; unsigned __int16 *
0x18002aba7  lea     r8, aAddress; "Address"
0x18002abae  mov     edx, r12d; unsigned int
0x18002abb1  mov     rcx, rsi; HKEY
0x18002abb4  call    ?SetRegistryStringValue@@YAHPEAUHKEY__@@KPEBG1J@Z; SetRegistryStringValue(HKEY__ *,ulong,ushort const *,ushort const *,long)
0x18002abb9  mov     r9, [rdi+28h]; unsigned __int16 *
0x18002abbd  lea     r8, aCity; "City"
0x18002abc4  mov     edx, r12d; unsigned int
0x18002abc7  mov     rcx, rsi; HKEY
0x18002abca  call    ?SetRegistryStringValue@@YAHPEAUHKEY__@@KPEBG1J@Z; SetRegistryStringValue(HKEY__ *,ulong,ushort const *,ushort const *,long)
0x18002abcf  mov     r9, [rdi+30h]; unsigned __int16 *
0x18002abd3  lea     r8, aState; "State"
0x18002abda  mov     edx, r12d; unsigned int
0x18002abdd  mov     rcx, rsi; HKEY
0x18002abe0  call    ?SetRegistryStringValue@@YAHPEAUHKEY__@@KPEBG1J@Z; SetRegistryStringValue(HKEY__ *,ulong,ushort const *,ushort const *,long)
0x18002abe5  mov     r9, [rdi+38h]; unsigned __int16 *
0x18002abe9  lea     r8, aZip; "ZIP"
0x18002abf0  mov     edx, r12d; unsigned int
0x18002abf3  mov     rcx, rsi; HKEY
0x18002abf6  call    ?SetRegistryStringValue@@YAHPEAUHKEY__@@KPEBG1J@Z; SetRegistryStringValue(HKEY__ *,ulong,ushort const *,ushort const *,long)
0x18002abfb  mov     r9, [rdi+40h]; unsigned __int16 *
0x18002abff  lea     r8, aCountry; "Country"
0x18002ac06  mov     edx, r12d; unsigned int
0x18002ac09  mov     rcx, rsi; HKEY
0x18002ac0c  call    ?SetRegistryStringValue@@YAHPEAUHKEY__@@KPEBG1J@Z; SetRegistryStringValue(HKEY__ *,ulong,ushort const *,ushort const *,long)
0x18002ac11  mov     r9, [rdi+48h]; unsigned __int16 *
0x18002ac15  lea     r8, aTitle; "Title"
0x18002ac1c  mov     edx, r12d; unsigned int
0x18002ac1f  mov     rcx, rsi; HKEY
0x18002ac22  call    ?SetRegistryStringValue@@YAHPEAUHKEY__@@KPEBG1J@Z; SetRegistryStringValue(HKEY__ *,ulong,ushort const *,ushort const *,long)
0x18002ac27  mov     r9, [rdi+50h]; unsigned __int16 *
0x18002ac2b  lea     r8, aDepartment; "Department"
0x18002ac32  mov     edx, r12d; unsigned int
0x18002ac35  mov     rcx, rsi; HKEY
0x18002ac38  call    ?SetRegistryStringValue@@YAHPEAUHKEY__@@KPEBG1J@Z; SetRegistryStringValue(HKEY__ *,ulong,ushort const *,ushort const *,long)
0x18002ac3d  mov     r9, [rdi+58h]; unsigned __int16 *
0x18002ac41  lea     r8, aOffice; "Office"
0x18002ac48  mov     edx, r12d; unsigned int
0x18002ac4b  mov     rcx, rsi; HKEY
0x18002ac4e  call    ?SetRegistryStringValue@@YAHPEAUHKEY__@@KPEBG1J@Z; SetRegistryStringValue(HKEY__ *,ulong,ushort const *,ushort const *,long)
0x18002ac53  mov     r9, [rdi+60h]; unsigned __int16 *
0x18002ac57  lea     r8, aHomephone; "HomePhone"
0x18002ac5e  mov     edx, r12d; unsigned int
0x18002ac61  mov     rcx, rsi; HKEY
0x18002ac64  call    ?SetRegistryStringValue@@YAHPEAUHKEY__@@KPEBG1J@Z; SetRegistryStringValue(HKEY__ *,ulong,ushort const *,ushort const *,long)
0x18002ac69  mov     r9, [rdi+68h]; unsigned __int16 *
0x18002ac6d  lea     r8, aOfficephone; "OfficePhone"
0x18002ac74  mov     edx, r12d; unsigned int
0x18002ac77  mov     rcx, rsi; HKEY
0x18002ac7a  call    ?SetRegistryStringValue@@YAHPEAUHKEY__@@KPEBG1J@Z; SetRegistryStringValue(HKEY__ *,ulong,ushort const *,ushort const *,long)
0x18002ac7f  mov     r9, [rdi+78h]; unsigned __int16 *
0x18002ac83  lea     r8, aBillingcode; "BillingCode"
0x18002ac8a  mov     edx, r12d; unsigned int
0x18002ac8d  mov     rcx, rsi; HKEY
0x18002ac90  call    ?SetRegistryStringValue@@YAHPEAUHKEY__@@KPEBG1J@Z; SetRegistryStringValue(HKEY__ *,ulong,ushort const *,ushort const *,long)
0x18002ac95  mov     r9, [rdi+70h]; unsigned __int16 *
0x18002ac99  lea     r8, aMailbox; "Mailbox"
0x18002aca0  mov     edx, r12d; unsigned int
0x18002aca3  mov     rcx, rsi; HKEY
0x18002aca6  call    ?SetRegistryStringValue@@YAHPEAUHKEY__@@KPEBG1J@Z; SetRegistryStringValue(HKEY__ *,ulong,ushort const *,ushort const *,long)
0x18002acab  mov     r9, [rdi+80h]; unsigned __int16 *
0x18002acb2  lea     r8, aTsid; "TSID"
0x18002acb9  mov     edx, r12d; unsigned int
0x18002acbc  mov     rcx, rsi; HKEY
0x18002acbf  call    ?SetRegistryStringValue@@YAHPEAUHKEY__@@KPEBG1J@Z; SetRegistryStringValue(HKEY__ *,ulong,ushort const *,ushort const *,long)
0x18002acc4  mov     rcx, rsi; hKey
0x18002acc7  call    cs:__imp_RegCloseKey
0x18002acce  nop     dword ptr [rax+rax+00h]
0x18002acd3  mov     r9d, 0F003Fh
0x18002acd9  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Fax\\Setup"
0x18002ace0  mov     r8d, r12d
0x18002ace3  mov     rcx, 0FFFFFFFF80000001h
0x18002acea  call    OpenRegistryKey
0x18002acef  mov     rdi, rax
0x18002acf2  test    rax, rax
0x18002acf5  jz      short loc_18002AD1A
0x18002acf7  mov     r8d, r12d
0x18002acfa  lea     rdx, aCfgwzdruserinf; "CfgWzdrUserInfo"
0x18002ad01  mov     rcx, rax
0x18002ad04  call    SetRegistryDword
0x18002ad09  mov     rcx, rdi; hKey
0x18002ad0c  call    cs:__imp_RegCloseKey
0x18002ad13  nop     dword ptr [rax+rax+00h]
0x18002ad18  jmp     short loc_18002AD71
0x18002ad1a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ad21  cmp     rcx, r14
0x18002ad24  jz      short loc_18002AD71
0x18002ad26  test    [rcx+1Ch], ebp
0x18002ad29  jz      short loc_18002AD71
0x18002ad2b  cmp     byte ptr [rcx+19h], 2
0x18002ad2f  jb      short loc_18002AD71
0x18002ad31  mov     rcx, [rcx+10h]
0x18002ad35  mov     edx, 0Eh
0x18002ad3a  mov     r8, r15
0x18002ad3d  call    WPP_SF_
0x18002ad42  jmp     short loc_18002AD71
0x18002ad44  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ad4b  cmp     rcx, r14
0x18002ad4e  jz      short loc_18002AD6C
0x18002ad50  test    [rcx+1Ch], ebp
0x18002ad53  jz      short loc_18002AD6C
0x18002ad55  cmp     byte ptr [rcx+19h], 2
0x18002ad59  jb      short loc_18002AD6C
0x18002ad5b  mov     rcx, [rcx+10h]
0x18002ad5f  mov     edx, 0Dh
0x18002ad64  mov     r8, r15
0x18002ad67  call    WPP_SF_
0x18002ad6c  mov     ebx, 80004005h
0x18002ad71  mov     eax, ebx
0x18002ad73  add     rsp, 30h
0x18002ad77  pop     r15
0x18002ad79  pop     r14
0x18002ad7b  pop     r12
0x18002ad7d  pop     rdi
0x18002ad7e  pop     rsi
0x18002ad7f  pop     rbp
0x18002ad80  pop     rbx
0x18002ad81  retn
```
