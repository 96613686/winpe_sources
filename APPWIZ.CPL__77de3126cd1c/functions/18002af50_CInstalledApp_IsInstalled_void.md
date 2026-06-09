# CInstalledApp::IsInstalled(void)

- ea: `0x18002af50`
- end: `0x18002b03f`
- name: `?IsInstalled@CInstalledApp@@UEAAJXZ`
- size: `239`
- prototype: `__int64 __fastcall(CInstalledApp *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18002af50`
- `0x18002c7b4`
- `0x180044db4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b02e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b02e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b01c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b025`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b01c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b025`
- `msi!__imp_MsiQueryProductStateW` at `0x18002afbd`
- `msi!__imp_MsiQueryProductStateW` at `0x18002afbd`
- `msi!__imp_MsiGetPatchInfoExW` at `0x18002afa9`
- `msi!__imp_MsiGetPatchInfoExW` at `0x18002afa9`

## string_xrefs

- `0x18002affc`: `UninstallString`

## pseudocode

```c
_BOOL8 __fastcall CInstalledApp::IsInstalled(WCHAR *this)
{
  BOOL v1; // edi
  MSIINSTALLCONTEXT v2; // r9d
  UINT PatchInfo; // eax
  bool v4; // zf
  HKEY v5; // rax
  HKEY v6; // rsi
  unsigned __int16 *LocalizedStringFromRegistry; // rax
  unsigned __int16 *v8; // rbp
  unsigned __int16 *v9; // rax
  DWORD v11; // [rsp+70h] [rbp+8h] BYREF

  v1 = 1;
  if ( *((_DWORD *)this + 5) == 1 )
  {
    v5 = CInstalledApp::_OpenUninstallRegKey((CInstalledApp *)this, 0x20019u);
    v6 = v5;
    if ( v5 )
    {
      LocalizedStringFromRegistry = GetLocalizedStringFromRegistry(v5, L"DisplayName");
      v8 = LocalizedStringFromRegistry;
      if ( LocalizedStringFromRegistry )
      {
        if ( *LocalizedStringFromRegistry )
        {
          v9 = GetLocalizedStringFromRegistry(v6, L"UninstallString");
          if ( v9 )
          {
            v1 = *v9 == 0;
            CoTaskMemFree(v9);
          }
        }
        CoTaskMemFree(v8);
      }
      RegCloseKey(v6);
    }
  }
  else if ( *((_DWORD *)this + 5) == 2 )
  {
    if ( this[2666] )
    {
      v2 = *((_DWORD *)this + 8);
      v11 = 0;
      PatchInfo = MsiGetPatchInfoExW(this + 2098, this + 2666, 0, v2, L"LocalPackage", 0, &v11);
      if ( !PatchInfo )
        return 0;
      v4 = PatchInfo == 234;
    }
    else
    {
      v4 = MsiQueryProductStateW(this + 2098) == INSTALLSTATE_DEFAULT;
    }
    if ( v4 )
      return 0;
  }
  return v1;
}

```

## disassembly

```asm
0x18002af50  mov     r11, rsp
0x18002af53  push    rbx
0x18002af54  push    rbp
0x18002af55  push    rsi
0x18002af56  push    rdi
0x18002af57  sub     rsp, 48h
0x18002af5b  mov     edx, [rcx+14h]
0x18002af5e  mov     edi, 1
0x18002af63  sub     edx, edi
0x18002af65  jz      short loc_18002AFCC
0x18002af67  cmp     edx, edi
0x18002af69  jnz     loc_18002B034
0x18002af6f  lea     rdx, [rcx+14D4h]; szProductCode
0x18002af76  xor     ebx, ebx
0x18002af78  lea     rax, [rcx+1064h]
0x18002af7f  cmp     [rdx], bx
0x18002af82  jz      short loc_18002AFBA
0x18002af84  mov     r9d, [rcx+20h]; dwContext
0x18002af88  lea     r8, [r11+8]
0x18002af8c  mov     [r11-38h], r8
0x18002af90  mov     rcx, rax; szPatchCode
0x18002af93  lea     r8, aLocalpackage; "LocalPackage"
0x18002af9a  mov     [r11-40h], rbx
0x18002af9e  mov     [r11-48h], r8
0x18002afa2  xor     r8d, r8d; szUserSid
0x18002afa5  mov     [rsp+68h+arg_0], ebx
0x18002afa9  call    cs:__imp_MsiGetPatchInfoExW
0x18002afaf  test    eax, eax
0x18002afb1  jz      short loc_18002AFC8
0x18002afb3  cmp     eax, 0EAh
0x18002afb8  jmp     short loc_18002AFC6
0x18002afba  mov     rcx, rax; szProduct
0x18002afbd  call    cs:__imp_MsiQueryProductStateW
0x18002afc3  cmp     eax, 5
0x18002afc6  jnz     short loc_18002B034
0x18002afc8  mov     edi, ebx
0x18002afca  jmp     short loc_18002B034
0x18002afcc  mov     edx, 20019h; samDesired
0x18002afd1  call    ?_OpenUninstallRegKey@CInstalledApp@@AEAAPEAUHKEY__@@K@Z; CInstalledApp::_OpenUninstallRegKey(ulong)
0x18002afd6  xor     ebx, ebx
0x18002afd8  mov     rsi, rax
0x18002afdb  test    rax, rax
0x18002afde  jz      short loc_18002B034
0x18002afe0  lea     rdx, aDisplayname; "DisplayName"
0x18002afe7  mov     rcx, rax; hkey
0x18002afea  call    ?GetLocalizedStringFromRegistry@@YAPEAGPEAUHKEY__@@PEBG@Z; GetLocalizedStringFromRegistry(HKEY__ *,ushort const *)
0x18002afef  mov     rbp, rax
0x18002aff2  test    rax, rax
0x18002aff5  jz      short loc_18002B02B
0x18002aff7  cmp     [rax], bx
0x18002affa  jz      short loc_18002B022
0x18002affc  lea     rdx, aUninstallstrin; "UninstallString"
0x18002b003  mov     rcx, rsi; hkey
0x18002b006  call    ?GetLocalizedStringFromRegistry@@YAPEAGPEAUHKEY__@@PEBG@Z; GetLocalizedStringFromRegistry(HKEY__ *,ushort const *)
0x18002b00b  test    rax, rax
0x18002b00e  jz      short loc_18002B022
0x18002b010  cmp     [rax], bx
0x18002b013  mov     edi, ebx
0x18002b015  mov     rcx, rax; pv
0x18002b018  setz    dil
0x18002b01c  call    cs:__imp_CoTaskMemFree
0x18002b022  mov     rcx, rbp; pv
0x18002b025  call    cs:__imp_CoTaskMemFree
0x18002b02b  mov     rcx, rsi; hKey
0x18002b02e  call    cs:__imp_RegCloseKey
0x18002b034  mov     eax, edi
0x18002b036  add     rsp, 48h
0x18002b03a  pop     rdi
0x18002b03b  pop     rsi
0x18002b03c  pop     rbp
0x18002b03d  pop     rbx
0x18002b03e  retn
```
