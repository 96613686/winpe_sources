# CActiveXInstallBroker::UpdateLanguageCheck(ushort *,ushort const *,_FILETIME)

- ea: `0x404a9b`
- end: `0x404bfc`
- name: `?UpdateLanguageCheck@CActiveXInstallBroker@@QAGJPAGPBGU_FILETIME@@@Z`
- size: `353`
- prototype: `unsigned int __userpurge@<eax>(const unsigned __int16 *@<edx>, int@<ecx>, LPCWSTR lpSubKey, unsigned __int16 *, BYTE Data, struct _FILETIME)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x405ee0`

## callees

- `0x402eb9`
- `0x402ed3`
- `0x404a9b`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x404ba0`
- `ADVAPI32!RegSetValueExW` at `0x404ba0`
- `ADVAPI32!RegCloseKey` at `0x404bc8`
- `ADVAPI32!RegCloseKey` at `0x404bd7`
- `ADVAPI32!RegCloseKey` at `0x404be6`
- `ADVAPI32!RegCloseKey` at `0x404bc8`
- `ADVAPI32!RegCloseKey` at `0x404bd7`
- `ADVAPI32!RegCloseKey` at `0x404be6`
- `ADVAPI32!RegCreateKeyW` at `0x404b84`
- `ADVAPI32!RegCreateKeyW` at `0x404b84`
- `ADVAPI32!RegOpenKeyExW` at `0x404b3c`
- `ADVAPI32!RegOpenKeyExW` at `0x404b58`
- `ADVAPI32!RegOpenKeyExW` at `0x404b72`
- `ADVAPI32!RegOpenKeyExW` at `0x404b3c`
- `ADVAPI32!RegOpenKeyExW` at `0x404b58`
- `ADVAPI32!RegOpenKeyExW` at `0x404b72`

## string_xrefs

- `0x404b32`: `CLSID`

## pseudocode

```c
unsigned int __userpurge CActiveXInstallBroker::UpdateLanguageCheck@<eax>(
        const unsigned __int16 *a1@<edx>,
        int a2@<ecx>,
        LPCWSTR lpSubKey,
        unsigned __int16 *a4,
        BYTE Data,
        struct _FILETIME a6)
{
  unsigned int v8; // esi
  int v9; // eax
  LSTATUS v10; // eax
  HKEY phkResult; // [esp+Ch] [ebp-Ch] BYREF
  HKEY hKey; // [esp+10h] [ebp-8h] BYREF
  HKEY v14; // [esp+14h] [ebp-4h] BYREF

  phkResult = 0;
  v8 = 0;
  hKey = 0;
  v14 = 0;
  if ( CLock::Lock((CLock *)a2) )
  {
    if ( *(int *)(a2 + 28) >= 7 )
    {
      if ( a1 && lpSubKey )
      {
        v9 = wcscmp(a1, *(const unsigned __int16 **)(a2 + 36));
        if ( v9 )
          v9 = v9 < 0 ? -1 : 1;
        if ( v9 )
        {
          v8 = -2147024891;
        }
        else
        {
          v10 = RegOpenKeyExW(HKEY_CLASSES_ROOT, L"CLSID", 0, 0x20019u, &phkResult);
          if ( v10
            || (v10 = RegOpenKeyExW(phkResult, lpSubKey, 0, 0x2001Fu, &hKey)) != 0
            || RegOpenKeyExW(hKey, L"LanguageCheckPeriod", 0, 0x2001Fu, &v14)
            && (v10 = RegCreateKeyW(hKey, L"LanguageCheckPeriod", &v14)) != 0
            || (v10 = RegSetValueExW(v14, L"LastCheckedHi", 0, 4u, &Data, 4u)) != 0 )
          {
            v8 = (unsigned __int16)v10 | 0x80070000;
            if ( v10 <= 0 )
              v8 = v10;
          }
        }
      }
      else
      {
        v8 = -2147024809;
      }
    }
    else
    {
      v8 = -2147019873;
    }
  }
  else
  {
    v8 = -2147024882;
  }
  if ( v14 )
    RegCloseKey(v14);
  if ( hKey )
    RegCloseKey(hKey);
  if ( phkResult )
    RegCloseKey(phkResult);
  CLock::Unlock((CLock *)a2);
  return v8;
}

```

## disassembly

```asm
0x404a9b  mov     edi, edi
0x404a9d  push    ebp
0x404a9e  mov     ebp, esp
0x404aa0  sub     esp, 0Ch
0x404aa3  push    ebx
0x404aa4  xor     eax, eax
0x404aa6  mov     ebx, ecx
0x404aa8  push    esi
0x404aa9  push    edi
0x404aaa  mov     edi, edx
0x404aac  mov     [ebp+phkResult], eax
0x404aaf  mov     esi, eax
0x404ab1  mov     [ebp+hKey], eax
0x404ab4  mov     [ebp+var_4], eax
0x404ab7  call    ?Lock@CLock@@QAEHXZ; CLock::Lock(void)
0x404abc  test    eax, eax
0x404abe  jnz     short loc_404ACA
0x404ac0  mov     esi, 8007000Eh
0x404ac5  jmp     loc_404BBF
0x404aca  cmp     dword ptr [ebx+1Ch], 7
0x404ace  jge     short loc_404ADA
0x404ad0  mov     esi, 8007139Fh
0x404ad5  jmp     loc_404BBF
0x404ada  test    edi, edi
0x404adc  jz      loc_404BBA
0x404ae2  cmp     [ebp+lpSubKey], esi
0x404ae5  jz      loc_404BBA
0x404aeb  mov     eax, [ebx+24h]
0x404aee  mov     cx, [edi]
0x404af1  cmp     cx, [eax]
0x404af4  jnz     short loc_404B14
0x404af6  test    cx, cx
0x404af9  jz      short loc_404B10
0x404afb  mov     cx, [edi+2]
0x404aff  cmp     cx, [eax+2]
0x404b03  jnz     short loc_404B14
0x404b05  add     edi, 4
0x404b08  add     eax, 4
0x404b0b  test    cx, cx
0x404b0e  jnz     short loc_404AEE
0x404b10  xor     eax, eax
0x404b12  jmp     short loc_404B19
0x404b14  sbb     eax, eax
0x404b16  or      eax, 1
0x404b19  test    eax, eax
0x404b1b  jz      short loc_404B27
0x404b1d  mov     esi, 80070005h
0x404b22  jmp     loc_404BBF
0x404b27  lea     eax, [ebp+phkResult]
0x404b2a  push    eax; phkResult
0x404b2b  push    20019h; samDesired
0x404b30  push    0; ulOptions
0x404b32  push    offset aClsid_0; "CLSID"
0x404b37  push    80000000h; hKey
0x404b3c  call    ds:__imp__RegOpenKeyExW@20; RegOpenKeyExW(x,x,x,x,x)
0x404b42  test    eax, eax
0x404b44  jnz     short loc_404BAA
0x404b46  lea     eax, [ebp+hKey]
0x404b49  mov     edi, 2001Fh
0x404b4e  push    eax; phkResult
0x404b4f  push    edi; samDesired
0x404b50  push    0; ulOptions
0x404b52  push    [ebp+lpSubKey]; lpSubKey
0x404b55  push    [ebp+phkResult]; hKey
0x404b58  call    ds:__imp__RegOpenKeyExW@20; RegOpenKeyExW(x,x,x,x,x)
0x404b5e  test    eax, eax
0x404b60  jnz     short loc_404BAA
0x404b62  lea     eax, [ebp+var_4]
0x404b65  push    eax; phkResult
0x404b66  push    edi; samDesired
0x404b67  push    0; ulOptions
0x404b69  mov     edi, offset aLanguagecheckp; "LanguageCheckPeriod"
0x404b6e  push    edi; lpSubKey
0x404b6f  push    [ebp+hKey]; hKey
0x404b72  call    ds:__imp__RegOpenKeyExW@20; RegOpenKeyExW(x,x,x,x,x)
0x404b78  test    eax, eax
0x404b7a  jz      short loc_404B8E
0x404b7c  lea     eax, [ebp+var_4]
0x404b7f  push    eax; phkResult
0x404b80  push    edi; lpSubKey
0x404b81  push    [ebp+hKey]; hKey
0x404b84  call    ds:__imp__RegCreateKeyW@12; RegCreateKeyW(x,x,x)
0x404b8a  test    eax, eax
0x404b8c  jnz     short loc_404BAA
0x404b8e  push    4; cbData
0x404b90  lea     eax, [ebp+Data]
0x404b93  push    eax; lpData
0x404b94  push    4; dwType
0x404b96  push    0; Reserved
0x404b98  push    offset aLastcheckedhi; "LastCheckedHi"
0x404b9d  push    [ebp+var_4]; hKey
0x404ba0  call    ds:__imp__RegSetValueExW@24; RegSetValueExW(x,x,x,x,x,x)
0x404ba6  test    eax, eax
0x404ba8  jz      short loc_404BBF
0x404baa  movzx   esi, ax
0x404bad  or      esi, 80070000h
0x404bb3  test    eax, eax
0x404bb5  cmovle  esi, eax
0x404bb8  jmp     short loc_404BBF
0x404bba  mov     esi, 80070057h
0x404bbf  cmp     [ebp+var_4], 0
0x404bc3  jz      short loc_404BCE
0x404bc5  push    [ebp+var_4]; hKey
0x404bc8  call    ds:__imp__RegCloseKey@4; RegCloseKey(x)
0x404bce  cmp     [ebp+hKey], 0
0x404bd2  jz      short loc_404BDD
0x404bd4  push    [ebp+hKey]; hKey
0x404bd7  call    ds:__imp__RegCloseKey@4; RegCloseKey(x)
0x404bdd  cmp     [ebp+phkResult], 0
0x404be1  jz      short loc_404BEC
0x404be3  push    [ebp+phkResult]; hKey
0x404be6  call    ds:__imp__RegCloseKey@4; RegCloseKey(x)
0x404bec  mov     ecx, ebx; this
0x404bee  call    ?Unlock@CLock@@QAEHXZ; CLock::Unlock(void)
0x404bf3  pop     edi
0x404bf4  mov     eax, esi
0x404bf6  pop     esi
0x404bf7  pop     ebx
0x404bf8  leave
0x404bf9  retn    0Ch
```
