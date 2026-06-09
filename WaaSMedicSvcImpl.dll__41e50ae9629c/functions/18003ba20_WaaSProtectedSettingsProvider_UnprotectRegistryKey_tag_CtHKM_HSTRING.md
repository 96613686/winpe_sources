# WaaSProtectedSettingsProvider::UnprotectRegistryKey(tag_CtHKM,HSTRING__ *)

- ea: `0x18003ba20`
- end: `0x18003bb5c`
- name: `?UnprotectRegistryKey@WaaSProtectedSettingsProvider@@UEAAJW4tag_CtHKM@@PEAUHSTRING__@@@Z`
- size: `316`
- prototype: `int __high(enum tag_CtHKM, HSTRING)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x18002555c`
- `0x18002e81c`
- `0x180034ac4`
- `0x1800358d8`
- `0x18003ba20`
- `0x180068b78`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003bb43`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003bb43`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003ba3f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003ba3f`

## string_xrefs

- `0x18003bb15`: `Error while attempting to determine base regkey name by index. Error code: 0x%08x.`
- `0x18003ba89`: `Could not verify access to registry path. Error code: 0x%08x.`
- `0x18003bb07`: `Caller was allowed to unprotected under this path of registry but applying the non-PPL ACL failed. Error code: 0x%08x`
- `0x18003ba9c`: `Caller was not allowed to unprotect under this path of registry.`
- `0x18003bad2`: `Failed to create handle to the target registry key. Error code: 0x%08x`

## pseudocode

```c
__int64 __fastcall WaaSProtectedSettingsProvider::UnprotectRegistryKey(__int64 a1, int a2, HSTRING a3)
{
  __int64 v3; // rbx
  HKEY v4; // rdi
  const unsigned __int16 *StringRawBuffer; // rax
  bool *v6; // r9
  const WCHAR *v7; // rsi
  WaasMedic::ProtectedSettingsNamespaceMapper *v8; // rbp
  __int64 v9; // r14
  int v10; // eax
  __int64 v11; // r8
  unsigned int v12; // ebx
  int v13; // eax
  int v14; // eax
  int v16; // [rsp+20h] [rbp-38h]
  unsigned __int16 v17; // [rsp+68h] [rbp+10h] BYREF
  HKEY handle; // [rsp+78h] [rbp+20h] BYREF

  v3 = a2;
  v4 = 0;
  handle = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(a3, 0);
  v7 = StringRawBuffer;
  if ( (unsigned int)v3 > 6 )
  {
    v12 = -2147483637;
    v8 = 0;
    LogLevelW(2u, L"Error while attempting to determine base regkey name by index. Error code: 0x%08x.", 2147483659LL);
  }
  else
  {
    LOBYTE(v17) = 0;
    v8 = (WaasMedic::ProtectedSettingsNamespaceMapper *)off_180070EA0[v3];
    v9 = v3;
    v10 = WaasMedic::ProtectedSettingsNamespaceMapper::IsCallerAllowedToWriteToRegistryPath(
            v8,
            StringRawBuffer,
            &v17,
            v6);
    v12 = v10;
    if ( v10 >= 0 )
    {
      if ( (_BYTE)v17 )
      {
        v13 = WaasMedic::RegCreateKeyHelperPrivate((HKEY)qword_180085718[v9], v7, v11, &handle, v16);
        v12 = v13;
        if ( v13 >= 0 )
        {
          v4 = handle;
          v14 = WaasMedic::CProtectionUtil::ApplySecurityDescriptorOnRegistrySubkey(
                  handle,
                  L"S:AI(TL;;KR;;;S-1-19-0-0)");
          v12 = v14;
          if ( v14 < 0 )
            LogLevelW(
              2u,
              L"Caller was allowed to unprotected under this path of registry but applying the non-PPL ACL failed. Error code: 0x%08x",
              (unsigned int)v14);
        }
        else
        {
          LogLevelW(2u, L"Failed to create handle to the target registry key. Error code: 0x%08x", (unsigned int)v13);
          v4 = handle;
        }
      }
      else
      {
        LogLevelW(3u, L"Caller was not allowed to unprotect under this path of registry.");
        v12 = -2147024891;
      }
    }
    else
    {
      LogLevelW(2u, L"Could not verify access to registry path. Error code: 0x%08x.", (unsigned int)v10);
    }
  }
  WaasMedic::TelemetryProvider::ReportRegistryKeyProtectionResult(v12, (const unsigned __int16 *)v8, v7, 0);
  if ( v4 )
    RegCloseKey(v4);
  return v12;
}

```

## disassembly

```asm
0x18003ba20  mov     [rsp+arg_0], rbx
0x18003ba25  push    rbp
0x18003ba26  push    rsi
0x18003ba27  push    rdi
0x18003ba28  push    r14
0x18003ba2a  push    r15
0x18003ba2c  sub     rsp, 30h
0x18003ba30  movsxd  rbx, edx
0x18003ba33  xor     edi, edi
0x18003ba35  xor     edx, edx; length
0x18003ba37  mov     [rsp+58h+handle], rdi
0x18003ba3c  mov     rcx, r8; string
0x18003ba3f  call    cs:__imp_WindowsGetStringRawBuffer
0x18003ba45  mov     rsi, rax
0x18003ba48  test    ebx, ebx
0x18003ba4a  js      loc_18003BB10
0x18003ba50  cmp     ebx, 7
0x18003ba53  jnb     loc_18003BB10
0x18003ba59  lea     r15, __ImageBase
0x18003ba60  mov     byte ptr [rsp+58h+arg_8], dil
0x18003ba65  mov     rbp, ds:rva off_180070EA0[r15+rbx*8]; "HKEY_CLASSES_ROOT\\" ...
0x18003ba6d  lea     r8, [rsp+58h+arg_8]; unsigned __int16 *
0x18003ba72  mov     rcx, rbp; this
0x18003ba75  mov     rdx, rax; unsigned __int16 *
0x18003ba78  mov     r14, rbx
0x18003ba7b  call    ?IsCallerAllowedToWriteToRegistryPath@ProtectedSettingsNamespaceMapper@WaasMedic@@YAJPEBG0AEA_N@Z; WaasMedic::ProtectedSettingsNamespaceMapper::IsCallerAllowedToWriteToRegistryPath(ushort const *,ushort const *,bool &)
0x18003ba80  mov     ebx, eax
0x18003ba82  test    eax, eax
0x18003ba84  jns     short loc_18003BA95
0x18003ba86  mov     r8d, eax
0x18003ba89  lea     rdx, aCouldNotVerify; "Could not verify access to registry pat"...
0x18003ba90  jmp     loc_18003BB21
0x18003ba95  cmp     byte ptr [rsp+58h+arg_8], dil
0x18003ba9a  jnz     short loc_18003BAB4
0x18003ba9c  lea     rdx, aCallerWasNotAl_1; "Caller was not allowed to unprotect und"...
0x18003baa3  mov     ecx, 3; unsigned __int8
0x18003baa8  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18003baad  mov     ebx, 80070005h
0x18003bab2  jmp     short loc_18003BB2B
0x18003bab4  mov     rcx, ds:rva qword_180085718[r15+r14*8]; hKey
0x18003babc  lea     r9, [rsp+58h+handle]
0x18003bac1  mov     rdx, rsi; lpSubKey
0x18003bac4  call    WaasMedic__RegCreateKeyHelperPrivate
0x18003bac9  mov     ebx, eax
0x18003bacb  test    eax, eax
0x18003bacd  jns     short loc_18003BAEA
0x18003bacf  mov     r8d, eax
0x18003bad2  lea     rdx, aFailedToCreate_15; "Failed to create handle to the target r"...
0x18003bad9  mov     ecx, 2; unsigned __int8
0x18003bade  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18003bae3  mov     rdi, [rsp+58h+handle]
0x18003bae8  jmp     short loc_18003BB2B
0x18003baea  mov     rdi, [rsp+58h+handle]
0x18003baef  lea     rdx, aSAiTlKrS11900; "S:AI(TL;;KR;;;S-1-19-0-0)"
0x18003baf6  mov     rcx, rdi; handle
0x18003baf9  call    ?ApplySecurityDescriptorOnRegistrySubkey@CProtectionUtil@WaasMedic@@CAJPEAUHKEY__@@PEBG@Z; WaasMedic::CProtectionUtil::ApplySecurityDescriptorOnRegistrySubkey(HKEY__ *,ushort const *)
0x18003bafe  mov     ebx, eax
0x18003bb00  test    eax, eax
0x18003bb02  jns     short loc_18003BB2B
0x18003bb04  mov     r8d, eax
0x18003bb07  lea     rdx, aCallerWasAllow_3; "Caller was allowed to unprotected under"...
0x18003bb0e  jmp     short loc_18003BB21
0x18003bb10  mov     ebx, 8000000Bh
0x18003bb15  lea     rdx, aErrorWhileAtte_0; "Error while attempting to determine bas"...
0x18003bb1c  mov     r8d, ebx
0x18003bb1f  xor     ebp, ebp
0x18003bb21  mov     ecx, 2; unsigned __int8
0x18003bb26  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18003bb2b  xor     r9d, r9d; bool
0x18003bb2e  mov     r8, rsi; unsigned __int16 *
0x18003bb31  mov     rdx, rbp; unsigned __int16 *
0x18003bb34  mov     ecx, ebx; int
0x18003bb36  call    ?ReportRegistryKeyProtectionResult@TelemetryProvider@WaasMedic@@SAXJPEBG0_N@Z; WaasMedic::TelemetryProvider::ReportRegistryKeyProtectionResult(long,ushort const *,ushort const *,bool)
0x18003bb3b  test    rdi, rdi
0x18003bb3e  jz      short loc_18003BB49
0x18003bb40  mov     rcx, rdi; hKey
0x18003bb43  call    cs:__imp_RegCloseKey
0x18003bb49  mov     eax, ebx
0x18003bb4b  mov     rbx, [rsp+58h+arg_0]
0x18003bb50  add     rsp, 30h
0x18003bb54  pop     r15
0x18003bb56  pop     r14
0x18003bb58  pop     rdi
0x18003bb59  pop     rsi
0x18003bb5a  pop     rbp
0x18003bb5b  retn
```
