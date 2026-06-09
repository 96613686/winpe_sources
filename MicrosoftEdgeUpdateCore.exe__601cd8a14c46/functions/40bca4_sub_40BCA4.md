# sub_40BCA4

- ea: `0x40bca4`
- end: `0x40c41f`
- name: `sub_40BCA4`
- size: `1915`
- prototype: `BOOL __thiscall(_DWORD *this, int)`
- caller_count: `1`
- callee_count: `27`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x40bbe7`

## callees

- `0x4015d2`
- `0x4015fb`
- `0x401cac`
- `0x401dd4`
- `0x401fbb`
- `0x402675`
- `0x402a83`
- `0x402b86`
- `0x402d9e`
- `0x403007`
- `0x403041`
- `0x403127`
- `0x404564`
- `0x405054`
- `0x405248`
- `0x4071af`
- `0x40a793`
- `0x40a8a0`
- `0x40aa5c`
- `0x40abe5`
- `0x40b71f`
- `0x40bca4`
- `0x40c623`
- `0x40c77a`
- `0x40c7c1`
- `0x40d08d`
- `0x41e11b`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x40c10c`
- `KERNEL32!lstrcmpiW` at `0x40c120`
- `KERNEL32!lstrcmpiW` at `0x40c134`
- `KERNEL32!lstrcmpiW` at `0x40c15a`
- `KERNEL32!lstrcmpiW` at `0x40c181`
- `KERNEL32!lstrcmpiW` at `0x40c1a8`
- `KERNEL32!lstrcmpiW` at `0x40c1cf`
- `KERNEL32!lstrcmpiW` at `0x40c1f6`
- `KERNEL32!lstrcmpiW` at `0x40c21d`
- `KERNEL32!lstrcmpiW` at `0x40c2c6`
- `KERNEL32!lstrcmpiW` at `0x40c2ec`
- `KERNEL32!lstrcmpiW` at `0x40c10c`
- `KERNEL32!lstrcmpiW` at `0x40c120`
- `KERNEL32!lstrcmpiW` at `0x40c134`
- `KERNEL32!lstrcmpiW` at `0x40c15a`
- `KERNEL32!lstrcmpiW` at `0x40c181`
- `KERNEL32!lstrcmpiW` at `0x40c1a8`
- `KERNEL32!lstrcmpiW` at `0x40c1cf`
- `KERNEL32!lstrcmpiW` at `0x40c1f6`
- `KERNEL32!lstrcmpiW` at `0x40c21d`
- `KERNEL32!lstrcmpiW` at `0x40c2c6`
- `KERNEL32!lstrcmpiW` at `0x40c2ec`
- `ole32!IIDFromString` at `0x40c03f`
- `ole32!IIDFromString` at `0x40c03f`
- `ADVAPI32!RegCloseKey` at `0x40be84`
- `ADVAPI32!RegCloseKey` at `0x40c3d3`
- `ADVAPI32!RegCloseKey` at `0x40be84`
- `ADVAPI32!RegCloseKey` at `0x40c3d3`

## string_xrefs

- `0x40bef3`: `PackageCacheSizeLimit`
- `0x40bf03`: `PackageCacheLifeLimit`
- `0x40bcf8`: `HKLM\Software\Policies\Microsoft\EdgeUpdate\`
- `0x40bd41`: `HKLM\Software\Policies\Microsoft\EdgeUpdate\`
- `0x40be96`: `HKLM\Software\Policies\Microsoft\EdgeUpdate\`
- `0x40bf10`: `UpdatesSuppressedStartHour`
- `0x40bed3`: `AutoUpdateCheckPeriodMinutes`
- `0x40bf2a`: `UpdatesSuppressedDurationMin`
- `0x40bf1d`: `UpdatesSuppressedStartMin`
- `0x40c11a`: `DefaultRemoveDesktopShortcut`
- `0x40c106`: `CreateDesktopShortcut`
- `0x40c12e`: `Install`
- `0x40bf5e`: `InstallDefault`
- `0x40c154`: `Update`
- `0x40bf6b`: `UpdateDefault`
- `0x40c17b`: `RollbackToTargetVersion`
- `0x40c1f0`: `MeteredUpdates`
- `0x40bf85`: `MeteredUpdatesDefault`
- `0x40bf78`: `UpdaterExperimentationAndConfigurationServiceControl`
- `0x40c217`: `Uninstall`
- `0x40be15`: `InstallAllowed`
- `0x40be5c`: `[Failed to read Copilot AllowInstallation policy]`

## pseudocode

```c
BOOL __thiscall sub_40BCA4(_DWORD *this, int a2)
{
  _DWORD *v3; // eax
  int v4; // eax
  BOOL v5; // ebx
  signed int v6; // esi
  int *v7; // eax
  volatile signed __int32 *v8; // ecx
  int v9; // ecx
  int v10; // esi
  LPCOLESTR v11; // edi
  const WCHAR *v12; // esi
  int v13; // eax
  LPCWSTR v14; // edi
  int v15; // ebx
  int v16; // ebx
  int v17; // ebx
  int v18; // ebx
  int v19; // ebx
  int v20; // ebx
  int v21; // ebx
  int *v22; // eax
  _DWORD *v23; // ecx
  int v25; // [esp-4h] [ebp-108h]
  int v26[4]; // [esp+10h] [ebp-F4h] BYREF
  int v27[4]; // [esp+20h] [ebp-E4h] BYREF
  _DWORD *v28; // [esp+30h] [ebp-D4h]
  int v29; // [esp+34h] [ebp-D0h]
  int v30; // [esp+38h] [ebp-CCh]
  LPCOLESTR v31; // [esp+3Ch] [ebp-C8h]
  int v32; // [esp+40h] [ebp-C4h]
  int v33; // [esp+44h] [ebp-C0h] BYREF
  int v34; // [esp+48h] [ebp-BCh]
  int v35; // [esp+4Ch] [ebp-B8h]
  int v36; // [esp+50h] [ebp-B4h]
  signed int v37; // [esp+54h] [ebp-B0h]
  LPCWSTR pszValue; // [esp+58h] [ebp-ACh]
  int v39; // [esp+5Ch] [ebp-A8h]
  _BYTE v40[8]; // [esp+60h] [ebp-A4h] BYREF
  char v41[8]; // [esp+68h] [ebp-9Ch] BYREF
  char v42[8]; // [esp+70h] [ebp-94h] BYREF
  char v43[8]; // [esp+78h] [ebp-8Ch] BYREF
  char v44[8]; // [esp+80h] [ebp-84h] BYREF
  char v45[8]; // [esp+88h] [ebp-7Ch] BYREF
  char v46[8]; // [esp+90h] [ebp-74h] BYREF
  char v47[8]; // [esp+98h] [ebp-6Ch] BYREF
  char v48[4]; // [esp+A0h] [ebp-64h] BYREF
  char v49[4]; // [esp+A4h] [ebp-60h] BYREF
  char v50[4]; // [esp+A8h] [ebp-5Ch] BYREF
  char v51[4]; // [esp+ACh] [ebp-58h] BYREF
  char v52[4]; // [esp+B0h] [ebp-54h] BYREF
  char v53[4]; // [esp+B4h] [ebp-50h] BYREF
  char v54[8]; // [esp+B8h] [ebp-4Ch] BYREF
  DWORD Type; // [esp+CCh] [ebp-38h] BYREF
  int (__thiscall **v56)(void *, char); // [esp+D0h] [ebp-34h] BYREF
  HKEY hKey; // [esp+D4h] [ebp-30h]
  int v58; // [esp+D8h] [ebp-2Ch]
  __int16 v59; // [esp+DCh] [ebp-28h] BYREF
  int pvData; // [esp+E0h] [ebp-24h] BYREF
  LPCOLESTR lpsz; // [esp+E4h] [ebp-20h] BYREF
  IID iid; // [esp+E8h] [ebp-1Ch] BYREF
  int v63; // [esp+F8h] [ebp-Ch] BYREF

  sub_40A793(v40);
  v3 = (_DWORD *)this[31];
  v29 = this[33];
  v59 = 0;
  pvData = 0;
  v28 = v3;
  v39 = 0;
  if ( sub_405054() )
  {
    v40[0] = 1;
    LOBYTE(v59) = 1;
    if ( !(unsigned __int8)sub_402D9E((wchar_t *)L"HKLM\\Software\\Policies\\Microsoft\\EdgeUpdate\\") )
    {
      v40[0] = 0;
      if ( (byte_43EE81 != 0 ? (unsigned int)dword_43ED80 : 0) != 0 )
      {
        iid.Data1 = byte_43EE81 != 0 ? (unsigned int)dword_43ED80 : 0;
        *(_DWORD *)&iid.Data2 = 7;
        *(_DWORD *)iid.Data4 = 1;
        *(_DWORD *)&iid.Data4[4] = sub_4071AF(iid.Data1, 7, 1);
        sub_404564(&iid, (int)&off_43A378, L"HKLM\\Software\\Policies\\Microsoft\\EdgeUpdate\\");
      }
    }
    if ( !(unsigned __int8)sub_402D9E((wchar_t *)L"HKLM\\SOFTWARE\\Policies\\Microsoft\\Copilot") )
    {
      LOBYTE(v59) = 0;
      if ( (byte_43EE81 != 0 ? (unsigned int)dword_43ED80 : 0) != 0 )
      {
        iid.Data1 = byte_43EE81 != 0 ? (unsigned int)dword_43ED80 : 0;
        *(_DWORD *)&iid.Data2 = 7;
        *(_DWORD *)iid.Data4 = 1;
        *(_DWORD *)&iid.Data4[4] = sub_4071AF(iid.Data1, 7, 1);
        sub_404564(&iid, (int)&off_43A4A0, L"HKLM\\SOFTWARE\\Policies\\Microsoft\\Copilot");
      }
    }
  }
  else if ( (byte_43EE81 != 0 ? (unsigned int)dword_43ED80 : 0) != 0 )
  {
    iid.Data1 = byte_43EE81 != 0 ? (unsigned int)dword_43ED80 : 0;
    *(_DWORD *)&iid.Data2 = 7;
    *(_DWORD *)iid.Data4 = 1;
    *(_DWORD *)&iid.Data4[4] = sub_4071AF(iid.Data1, 7, 1);
    sub_404564(&iid, (int)&off_43A410);
  }
  *(_DWORD *)iid.Data4 = 0;
  *(_DWORD *)&iid.Data2 = &off_437C00;
  *(_DWORD *)&iid.Data4[4] = 512;
  if ( sub_402675((wchar_t *)L"HKLM\\SOFTWARE\\Policies\\Microsoft\\Copilot", 131097) < 0 )
  {
    LOBYTE(v59) = 0;
  }
  else
  {
    HIBYTE(v59) = 1;
    if ( sub_402A83(L"InstallAllowed", &pvData) < 0 )
    {
      if ( (byte_43EE81 != 0 ? (unsigned int)dword_43ED80 : 0) != 0 )
      {
        v35 = -1;
        v33 = byte_43EE81 != 0 ? (unsigned int)dword_43ED80 : 0;
        v34 = 7;
        v36 = sub_4071AF(v33, 7, -1);
        sub_404564(&v33, (int)L"[Failed to read Copilot AllowInstallation policy]");
      }
      pvData = 0;
    }
  }
  *(_DWORD *)&iid.Data2 = &off_437C00;
  if ( *(_DWORD *)iid.Data4 )
    RegCloseKey(*(HKEY *)iid.Data4);
  hKey = 0;
  v56 = &off_437C00;
  v58 = 512;
  v4 = sub_402675((wchar_t *)L"HKLM\\Software\\Policies\\Microsoft\\EdgeUpdate\\", 131097);
  v40[0] &= (v4 < 0) - 1;
  if ( !v40[0] )
  {
    v5 = (_BYTE)v59 == 0;
    goto LABEL_65;
  }
  v40[1] = 1;
  sub_40C77A(L"AutoUpdateCheckPeriodMinutes", v41);
  sub_40AA5C(L"DownloadPreference", v42);
  sub_40C77A(L"PackageCacheSizeLimit", v43);
  sub_40C77A(L"PackageCacheLifeLimit", v44);
  sub_40C77A(L"UpdatesSuppressedStartHour", v45);
  sub_40C77A(L"UpdatesSuppressedStartMin", v46);
  sub_40C77A(L"UpdatesSuppressedDurationMin", v47);
  sub_40AA5C(L"ProxyMode", v48);
  sub_40AA5C(L"ProxyServer", v49);
  sub_40AA5C(L"ProxyPacUrl", v50);
  sub_40C7C1(L"InstallDefault", v51);
  sub_40C7C1(L"UpdateDefault", v52);
  sub_40C7C1(L"UpdaterExperimentationAndConfigurationServiceControl", v53);
  sub_40C7C1(L"MeteredUpdatesDefault", v54);
  v6 = 0;
  v30 = sub_403007(&v56);
  v37 = 0;
  if ( v30 > 0 )
  {
    while ( 1 )
    {
      v63 = 0;
      v7 = sub_4015FB();
      sub_401FBB(&v63, (int)v7);
      Type = 0;
      if ( sub_403041(v6, (int)&v63, &Type) >= 0 )
      {
        v9 = sub_405248(123, 0);
        v32 = v9;
        if ( v9 > 0 )
          break;
      }
      v8 = (volatile signed __int32 *)(v63 - 16);
LABEL_63:
      sub_4015D2(v8);
      v37 = ++v6;
      if ( v6 >= v30 )
        goto LABEL_64;
    }
    _mm_lfence();
    v10 = v63;
    lpsz = 0;
    pszValue = (LPCWSTR)v63;
    sub_401DD4(&lpsz, v9, *(_DWORD *)(v63 - 12) - v9);
    memset(&iid, 0, sizeof(iid));
    v11 = lpsz;
    v31 = lpsz;
    if ( *((_DWORD *)lpsz - 3) != 38 || IIDFromString(lpsz, &iid) < 0 || !sub_41E11B(dword_4274C8, &iid, 16) )
    {
      sub_4015D2((volatile signed __int32 *)v11 - 4);
      v8 = (volatile signed __int32 *)(v10 - 16);
      goto LABEL_62;
    }
    v25 = v32;
    _mm_lfence();
    lpsz = 0;
    sub_403127(&lpsz, v25);
    v12 = lpsz;
    if ( Type != 1 )
    {
      if ( Type == 4 )
      {
        v14 = pszValue;
        v63 = 0;
        if ( sub_402A83(pszValue, &v63) >= 0
          && lstrcmpiW(v12, L"CreateDesktopShortcut")
          && lstrcmpiW(v12, L"DefaultRemoveDesktopShortcut") )
        {
          if ( lstrcmpiW(v12, L"Install") )
          {
            if ( lstrcmpiW(v12, L"Update") )
            {
              if ( lstrcmpiW(v12, L"RollbackToTargetVersion") )
              {
                if ( lstrcmpiW(v12, L"EdgePreview") )
                {
                  if ( lstrcmpiW(v12, L"EdgePreviewEnrollmentType") )
                  {
                    if ( lstrcmpiW(v12, L"MeteredUpdates") )
                    {
                      if ( lstrcmpiW(v12, L"Uninstall") )
                      {
                        if ( (byte_43EE81 != 0 ? (unsigned int)dword_43ED80 : 0) != 0 )
                        {
                          v27[2] = -1;
                          v27[0] = byte_43EE81 != 0 ? (unsigned int)dword_43ED80 : 0;
                          v27[1] = 7;
                          v27[3] = sub_4071AF(v27[0], 7, -1);
                          sub_404564(v27, (int)&off_43A548, v14, v63);
                        }
                      }
                      else
                      {
                        v21 = v63;
                        *(_DWORD *)(sub_40C623(&iid) + 32) = v21;
                      }
                    }
                    else
                    {
                      v20 = v63;
                      *(_DWORD *)(sub_40C623(&iid) + 28) = v20;
                    }
                  }
                  else
                  {
                    v19 = v63;
                    *(_DWORD *)(sub_40C623(&iid) + 24) = v19;
                  }
                }
                else
                {
                  v18 = v63;
                  *(_DWORD *)(sub_40C623(&iid) + 20) = v18;
                }
              }
              else
              {
                v17 = v63;
                *(_DWORD *)(sub_40C623(&iid) + 16) = v17;
              }
            }
            else
            {
              v16 = v63;
              *(_DWORD *)(sub_40C623(&iid) + 4) = v16;
            }
          }
          else
          {
            v15 = v63;
            *(_DWORD *)sub_40C623(&iid) = v15;
          }
        }
      }
      else if ( (byte_43EE81 != 0 ? (unsigned int)dword_43ED80 : 0) != 0 )
      {
        v35 = -1;
        v33 = byte_43EE81 != 0 ? (unsigned int)dword_43ED80 : 0;
        v34 = 7;
        v13 = sub_4071AF(v33, 7, -1);
        v14 = pszValue;
        v36 = v13;
        sub_404564(&v33, (int)&off_43A660, pszValue, Type);
      }
      else
      {
        v14 = pszValue;
      }
      goto LABEL_60;
    }
    v63 = 0;
    v22 = sub_4015FB();
    sub_401FBB(&v63, (int)v22);
    v14 = pszValue;
    if ( sub_402B86(pszValue, (int)&v63) >= 0 )
    {
      if ( lstrcmpiW(v12, L"TargetChannel") )
      {
        if ( lstrcmpiW(v12, L"TargetVersionPrefix") )
        {
          if ( (byte_43EE81 != 0 ? (unsigned int)dword_43ED80 : 0) != 0 )
          {
            v26[2] = -1;
            v26[0] = byte_43EE81 != 0 ? (unsigned int)dword_43ED80 : 0;
            v26[1] = 7;
            v26[3] = sub_4071AF(v26[0], 7, -1);
            sub_404564(v26, (int)&off_43A718, v14, v63);
          }
          goto LABEL_58;
        }
        v23 = (_DWORD *)(sub_40C623(&iid) + 12);
      }
      else
      {
        v23 = (_DWORD *)(sub_40C623(&iid) + 8);
      }
      sub_401CAC(v23, (void **)&v63);
    }
LABEL_58:
    sub_4015D2((volatile signed __int32 *)(v63 - 16));
LABEL_60:
    sub_4015D2((volatile signed __int32 *)v12 - 4);
    sub_4015D2((volatile signed __int32 *)v31 - 4);
    v8 = (volatile signed __int32 *)(v14 - 8);
LABEL_62:
    v6 = v37;
    goto LABEL_63;
  }
LABEL_64:
  v5 = 0;
LABEL_65:
  v56 = &off_437C00;
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
    v58 = 512;
  }
  sub_40ABE5(v28, (unsigned __int8 *)&v59);
  sub_40B71F(v40);
  sub_40A8A0(v40);
  return v5;
}

```

## disassembly

```asm
0x40bca4  push    ebp
0x40bca5  mov     ebp, esp
0x40bca7  sub     esp, 0F8h
0x40bcad  mov     eax, ___security_cookie
0x40bcb2  xor     eax, ebp
0x40bcb4  mov     [ebp+var_8], eax
0x40bcb7  push    ebx
0x40bcb8  push    esi
0x40bcb9  mov     esi, ecx
0x40bcbb  lea     ecx, [ebp+var_A4]
0x40bcc1  push    edi
0x40bcc2  call    sub_40A793
0x40bcc7  mov     edi, [esi+84h]
0x40bccd  xor     ecx, ecx
0x40bccf  mov     eax, [esi+7Ch]
0x40bcd2  mov     [ebp+var_D0], edi
0x40bcd8  mov     [ebp+var_28], cx
0x40bcdc  mov     [ebp+pvData], ecx
0x40bcdf  mov     [ebp+var_D4], eax
0x40bce5  mov     [ebp+var_A8], ecx
0x40bceb  call    sub_405054
0x40bcf0  test    al, al
0x40bcf2  jz      loc_40BDA8
0x40bcf8  mov     ecx, offset aHklmSoftwarePo; "HKLM\\Software\\Policies\\Microsoft\\Ed"...
0x40bcfd  mov     [ebp+var_A4], 1
0x40bd04  mov     byte ptr [ebp+var_28], 1
0x40bd08  call    sub_402D9E
0x40bd0d  mov     esi, offset dword_43ED80
0x40bd12  push    7
0x40bd14  pop     ebx
0x40bd15  test    al, al
0x40bd17  jnz     short loc_40BD5A
0x40bd19  movzx   ecx, byte_43EE81
0x40bd20  neg     ecx
0x40bd22  mov     [ebp+var_A4], al
0x40bd28  sbb     ecx, ecx
0x40bd2a  and     ecx, esi
0x40bd2c  jz      short loc_40BD5A
0x40bd2e  xor     eax, eax
0x40bd30  mov     [ebp+iid.Data1], ecx
0x40bd33  inc     eax
0x40bd34  mov     dword ptr [ebp+iid.Data2], ebx
0x40bd37  push    eax
0x40bd38  push    ebx
0x40bd39  mov     dword ptr [ebp+iid.Data4], eax
0x40bd3c  call    sub_4071AF
0x40bd41  push    offset aHklmSoftwarePo; "HKLM\\Software\\Policies\\Microsoft\\Ed"...
0x40bd46  mov     dword ptr [ebp+iid.Data4+4], eax
0x40bd49  lea     eax, [ebp+iid]
0x40bd4c  push    offset off_43A378; "䐀䔀㌀䈀㘀䔀㔀ⴀ\u3100䘀㘀㌀ⴀ㐀䘀㈀䐀ⴀ㠀䌀㠀䔀ⴀ㠀䄀㘀䐀\u3100䘀"...
0x40bd51  push    eax
0x40bd52  call    sub_404564
0x40bd57  add     esp, 0Ch
0x40bd5a  mov     ecx, offset aHklmSoftwarePo_0; "HKLM\\SOFTWARE\\Policies\\Microsoft\\Co"...
0x40bd5f  call    sub_402D9E
0x40bd64  test    al, al
0x40bd66  jnz     short loc_40BDE5
0x40bd68  movzx   ecx, byte_43EE81
0x40bd6f  neg     ecx
0x40bd71  mov     byte ptr [ebp+var_28], al
0x40bd74  sbb     ecx, ecx
0x40bd76  and     ecx, esi
0x40bd78  jz      short loc_40BDE5
0x40bd7a  xor     eax, eax
0x40bd7c  mov     [ebp+iid.Data1], ecx
0x40bd7f  inc     eax
0x40bd80  mov     dword ptr [ebp+iid.Data2], ebx
0x40bd83  push    eax
0x40bd84  push    ebx
0x40bd85  mov     dword ptr [ebp+iid.Data4], eax
0x40bd88  call    sub_4071AF
0x40bd8d  push    offset aHklmSoftwarePo_0; "HKLM\\SOFTWARE\\Policies\\Microsoft\\Co"...
0x40bd92  mov     dword ptr [ebp+iid.Data4+4], eax
0x40bd95  lea     eax, [ebp+iid]
0x40bd98  push    offset off_43A4A0; "䐀䔀㌀䈀㘀䔀㔀ⴀ\u3100䘀㘀㌀ⴀ㐀䘀㈀䐀ⴀ㠀䌀㠀䔀ⴀ㠀䄀㘀䐀\u3100䘀"...
0x40bd9d  push    eax
0x40bd9e  call    sub_404564
0x40bda3  add     esp, 0Ch
0x40bda6  jmp     short loc_40BDE5
0x40bda8  movzx   ecx, byte_43EE81
0x40bdaf  mov     esi, offset dword_43ED80
0x40bdb4  push    1
0x40bdb6  neg     ecx
0x40bdb8  pop     eax
0x40bdb9  sbb     ecx, ecx
0x40bdbb  push    7
0x40bdbd  pop     ebx
0x40bdbe  and     ecx, esi
0x40bdc0  jz      short loc_40BDE5
0x40bdc2  push    eax
0x40bdc3  push    ebx
0x40bdc4  mov     [ebp+iid.Data1], ecx
0x40bdc7  mov     dword ptr [ebp+iid.Data2], ebx
0x40bdca  mov     dword ptr [ebp+iid.Data4], eax
0x40bdcd  call    sub_4071AF
0x40bdd2  mov     dword ptr [ebp+iid.Data4+4], eax
0x40bdd5  lea     eax, [ebp+iid]
0x40bdd8  push    offset off_43A410; "䐀䔀㌀䈀㘀䔀㔀ⴀ\u3100䘀㘀㌀ⴀ㐀䘀㈀䐀ⴀ㠀䌀㠀䔀ⴀ㠀䄀㘀䐀\u3100䘀"...
0x40bddd  push    eax
0x40bdde  call    sub_404564
0x40bde3  pop     ecx
0x40bde4  pop     ecx
0x40bde5  and     dword ptr [ebp+iid.Data4], 0
0x40bde9  lea     ecx, [ebp+iid.Data2]
0x40bdec  push    20019h; int
0x40bdf1  push    offset aHklmSoftwarePo_0; "HKLM\\SOFTWARE\\Policies\\Microsoft\\Co"...
0x40bdf6  mov     dword ptr [ebp+iid.Data2], offset off_437C00
0x40bdfd  mov     dword ptr [ebp+iid.Data4+4], 200h
0x40be04  call    sub_402675
0x40be09  test    eax, eax
0x40be0b  js      short loc_40BE6F
0x40be0d  lea     eax, [ebp+pvData]
0x40be10  mov     byte ptr [ebp+var_28+1], 1
0x40be14  push    eax; pvData
0x40be15  push    offset pszValue; "InstallAllowed"
0x40be1a  lea     ecx, [ebp+iid.Data2]
0x40be1d  call    sub_402A83
0x40be22  test    eax, eax
0x40be24  jns     short loc_40BE73
0x40be26  movzx   ecx, byte_43EE81
0x40be2d  neg     ecx
0x40be2f  sbb     ecx, ecx
0x40be31  and     ecx, esi
0x40be33  jz      short loc_40BE69
0x40be35  or      [ebp+var_B8], 0FFFFFFFFh
0x40be3c  push    0FFFFFFFFh
0x40be3e  push    ebx
0x40be3f  mov     [ebp+var_C0], ecx
0x40be45  mov     [ebp+var_BC], ebx
0x40be4b  call    sub_4071AF
0x40be50  mov     [ebp+var_B4], eax
0x40be56  lea     eax, [ebp+var_C0]
0x40be5c  push    offset aFailedToReadCo; "[Failed to read Copilot AllowInstallati"...
0x40be61  push    eax
0x40be62  call    sub_404564
0x40be67  pop     ecx
0x40be68  pop     ecx
0x40be69  and     [ebp+pvData], 0
0x40be6d  jmp     short loc_40BE73
0x40be6f  mov     byte ptr [ebp+var_28], 0
0x40be73  cmp     dword ptr [ebp+iid.Data4], 0
0x40be77  mov     esi, offset off_437C00
0x40be7c  mov     dword ptr [ebp+iid.Data2], esi
0x40be7f  jz      short loc_40BE8A
0x40be81  push    dword ptr [ebp+iid.Data4]; hKey
0x40be84  call    ds:RegCloseKey
0x40be8a  and     [ebp+hKey], 0
0x40be8e  lea     ecx, [ebp+var_34]
0x40be91  push    20019h; int
0x40be96  push    offset aHklmSoftwarePo; "HKLM\\Software\\Policies\\Microsoft\\Ed"...
0x40be9b  mov     [ebp+var_34], esi
0x40be9e  mov     [ebp+var_2C], 200h
0x40bea5  call    sub_402675
0x40beaa  test    eax, eax
0x40beac  sets    al
0x40beaf  dec     al
0x40beb1  and     [ebp+var_A4], al
0x40beb7  jnz     short loc_40BEC6
0x40beb9  xor     ebx, ebx
0x40bebb  cmp     byte ptr [ebp+var_28], bl
0x40bebe  setz    bl
0x40bec1  jmp     loc_40C3C7
0x40bec6  lea     edx, [ebp+var_9C]
0x40becc  mov     [ebp+var_A3], 1
0x40bed3  mov     ecx, offset aAutoupdatechec; "AutoUpdateCheckPeriodMinutes"
0x40bed8  call    sub_40C77A
0x40bedd  lea     edx, [ebp+var_94]
0x40bee3  mov     ecx, offset aDownloadprefer; "DownloadPreference"
0x40bee8  call    sub_40AA5C
0x40beed  lea     edx, [ebp+var_8C]
0x40bef3  mov     ecx, offset aPackagecachesi; "PackageCacheSizeLimit"
0x40bef8  call    sub_40C77A
0x40befd  lea     edx, [ebp+var_84]
0x40bf03  mov     ecx, offset aPackagecacheli; "PackageCacheLifeLimit"
0x40bf08  call    sub_40C77A
0x40bf0d  lea     edx, [ebp+var_7C]
0x40bf10  mov     ecx, offset aUpdatessuppres; "UpdatesSuppressedStartHour"
0x40bf15  call    sub_40C77A
0x40bf1a  lea     edx, [ebp+var_74]
0x40bf1d  mov     ecx, offset aUpdatessuppres_0; "UpdatesSuppressedStartMin"
0x40bf22  call    sub_40C77A
0x40bf27  lea     edx, [ebp+var_6C]
0x40bf2a  mov     ecx, offset aUpdatessuppres_1; "UpdatesSuppressedDurationMin"
0x40bf2f  call    sub_40C77A
0x40bf34  lea     edx, [ebp+var_64]
0x40bf37  mov     ecx, offset aProxymode; "ProxyMode"
0x40bf3c  call    sub_40AA5C
0x40bf41  lea     edx, [ebp+var_60]
0x40bf44  mov     ecx, offset aProxyserver; "ProxyServer"
0x40bf49  call    sub_40AA5C
0x40bf4e  lea     edx, [ebp+var_5C]
0x40bf51  mov     ecx, offset aProxypacurl; "ProxyPacUrl"
0x40bf56  call    sub_40AA5C
0x40bf5b  lea     edx, [ebp+var_58]
0x40bf5e  mov     ecx, offset aInstalldefault; "InstallDefault"
0x40bf63  call    sub_40C7C1
0x40bf68  lea     edx, [ebp+var_54]
0x40bf6b  mov     ecx, offset aUpdatedefault; "UpdateDefault"
0x40bf70  call    sub_40C7C1
0x40bf75  lea     edx, [ebp+var_50]
0x40bf78  mov     ecx, offset aUpdaterexperim; "UpdaterExperimentationAndConfigurationS"...
0x40bf7d  call    sub_40C7C1
0x40bf82  lea     edx, [ebp+var_4C]
0x40bf85  mov     ecx, offset aMeteredupdates; "MeteredUpdatesDefault"
0x40bf8a  call    sub_40C7C1
0x40bf8f  lea     ecx, [ebp+var_34]
0x40bf92  call    sub_403007
0x40bf97  xor     esi, esi
0x40bf99  mov     [ebp+var_CC], eax
0x40bf9f  mov     [ebp+var_B0], esi
0x40bfa5  test    eax, eax
0x40bfa7  jle     loc_40C3C0
0x40bfad  and     [ebp+var_C], 0
0x40bfb1  call    sub_4015FB
0x40bfb6  push    eax
0x40bfb7  lea     ecx, [ebp+var_C]
0x40bfba  call    sub_401FBB
0x40bfbf  and     [ebp+Type], 0
0x40bfc3  lea     eax, [ebp+Type]
0x40bfc6  push    eax; lpType
0x40bfc7  lea     eax, [ebp+var_C]
0x40bfca  push    eax; int
0x40bfcb  push    esi; dwIndex
0x40bfcc  lea     ecx, [ebp+var_34]
0x40bfcf  call    sub_403041
0x40bfd4  test    eax, eax
0x40bfd6  jns     short loc_40BFE3
0x40bfd8  mov     ecx, [ebp+var_C]
0x40bfdb  add     ecx, 0FFFFFFF0h
0x40bfde  jmp     loc_40C39F
0x40bfe3  push    0
0x40bfe5  push    7Bh ; '{'
0x40bfe7  lea     ecx, [ebp+var_C]
0x40bfea  call    sub_405248
0x40bfef  mov     ecx, eax
0x40bff1  mov     [ebp+var_C4], ecx
0x40bff7  test    ecx, ecx
0x40bff9  jle     short loc_40BFD8
0x40bffb  lfence
0x40bffe  mov     esi, [ebp+var_C]
0x40c001  and     [ebp+lpsz], 0
0x40c005  mov     [ebp+pszValue], esi
0x40c00b  mov     eax, [esi-0Ch]
0x40c00e  sub     eax, ecx
0x40c010  push    eax
0x40c011  push    ecx
0x40c012  lea     eax, [ebp+lpsz]
0x40c015  push    eax
0x40c016  lea     ecx, [ebp+var_C]
0x40c019  call    sub_401DD4
0x40c01e  xor     eax, eax
0x40c020  lea     edi, [ebp+iid]
0x40c023  stosd
0x40c024  stosd
0x40c025  stosd
0x40c026  stosd
0x40c027  mov     edi, [ebp+lpsz]
0x40c02a  mov     [ebp+var_C8], edi
0x40c030  cmp     dword ptr [edi-0Ch], 26h ; '&'
0x40c034  jnz     loc_40C38E
0x40c03a  lea     eax, [ebp+iid]
0x40c03d  push    eax; lpiid
0x40c03e  push    edi; lpsz
0x40c03f  call    ds:IIDFromString
0x40c045  test    eax, eax
0x40c047  js      loc_40C38E
0x40c04d  push    10h
0x40c04f  lea     eax, [ebp+iid]
0x40c052  push    eax
0x40c053  push    offset dword_4274C8
0x40c058  call    sub_41E11B
0x40c05d  add     esp, 0Ch
0x40c060  test    eax, eax
0x40c062  jz      loc_40C38E
0x40c068  push    [ebp+var_C4]
0x40c06e  lea     eax, [ebp+lpsz]
0x40c071  lfence
0x40c074  and     [ebp+lpsz], 0
0x40c078  lea     ecx, [ebp+var_C]
0x40c07b  push    eax
0x40c07c  call    sub_403127
0x40c081  mov     eax, [ebp+Type]
0x40c084  mov     esi, [ebp+lpsz]
0x40c087  sub     eax, 1
0x40c08a  jz      loc_40C293
0x40c090  sub     eax, 3
0x40c093  jz      short loc_40C0E7
0x40c095  movzx   ecx, byte_43EE81
0x40c09c  neg     ecx
0x40c09e  sbb     ecx, ecx
0x40c0a0  and     ecx, offset dword_43ED80
0x40c0a6  jz      loc_40C36D
0x40c0ac  or      [ebp+var_B8], 0FFFFFFFFh
0x40c0b3  push    0FFFFFFFFh
0x40c0b5  push    ebx
0x40c0b6  mov     [ebp+var_C0], ecx
0x40c0bc  mov     [ebp+var_BC], ebx
0x40c0c2  call    sub_4071AF
0x40c0c7  push    [ebp+Type]
0x40c0ca  mov     edi, [ebp+pszValue]
  ... truncated ...
```
