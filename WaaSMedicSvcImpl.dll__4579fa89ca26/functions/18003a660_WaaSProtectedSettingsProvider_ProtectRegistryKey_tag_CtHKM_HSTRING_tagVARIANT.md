# WaaSProtectedSettingsProvider::ProtectRegistryKey(tag_CtHKM,HSTRING__ *,tagVARIANT)

- ea: `0x18003a660`
- end: `0x18003a7c7`
- name: `?ProtectRegistryKey@WaaSProtectedSettingsProvider@@UEAAJW4tag_CtHKM@@PEAUHSTRING__@@UtagVARIANT@@@Z`
- size: `359`
- prototype: `int __high(enum tag_CtHKM, HSTRING, struct tagVARIANT)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x18002555c`
- `0x18002e81c`
- `0x180034ac4`
- `0x180035734`
- `0x1800358d8`
- `0x18003a660`
- `0x180068b78`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003a689`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003a689`

## string_xrefs

- `0x18003a6fa`: `Caller is not granted access to write protected keys under this path. Will return: 0x%08x`
- `0x18003a787`: `Error while attempting to determine base regkey name by index. Error code: 0x%08x.`
- `0x18003a6e2`: `Error while attempting to verify access to namespace. Error code: 0x%08x.`
- `0x18003a779`: `Caller was allowed write under this path of registry and key was created but applying the PPL ACL failed. Error code: 0x%08x`
- `0x18003a72c`: `Caller was allowed to write under this path of registry but the create key operation failed. Error code: 0x%08x`
- `0x18003a756`: `Caller was allowed write under this path of registry and key was created but applying the optional permissions failed. Error code: 0x%08x`

## pseudocode

```c
__int64 __fastcall WaaSProtectedSettingsProvider::ProtectRegistryKey(__int64 a1, int a2, HSTRING a3, __int64 a4)
{
  __int64 v4; // rbx
  const unsigned __int16 *StringRawBuffer; // rax
  bool *v7; // r9
  const WCHAR *v8; // rbp
  const WCHAR *v9; // rdi
  WaasMedic::ProtectedSettingsNamespaceMapper *v10; // rsi
  __int64 v11; // r14
  int v12; // eax
  __int64 v13; // r8
  unsigned int v14; // ebx
  int v15; // eax
  int v16; // eax
  int v17; // eax
  int v19; // [rsp+20h] [rbp-38h]
  unsigned __int16 v20; // [rsp+68h] [rbp+10h] BYREF
  HKEY handle; // [rsp+78h] [rbp+20h] BYREF

  v4 = a2;
  handle = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(a3, 0);
  v8 = StringRawBuffer;
  if ( *(_WORD *)a4 == 8 )
    v9 = *(const WCHAR **)(a4 + 8);
  else
    v9 = 0;
  if ( (unsigned int)v4 > 6 )
  {
    v14 = -2147483637;
    v10 = 0;
    LogLevelW(2u, L"Error while attempting to determine base regkey name by index. Error code: 0x%08x.", 2147483659LL);
  }
  else
  {
    LOBYTE(v20) = 0;
    v10 = (WaasMedic::ProtectedSettingsNamespaceMapper *)off_180070EA0[v4];
    v11 = v4;
    v12 = WaasMedic::ProtectedSettingsNamespaceMapper::IsCallerAllowedToWriteToRegistryPath(
            v10,
            StringRawBuffer,
            &v20,
            v7);
    v14 = v12;
    if ( v12 >= 0 )
    {
      if ( (_BYTE)v20 )
      {
        v15 = WaasMedic::RegCreateKeyHelperPrivate((HKEY)qword_180085718[v11], v8, v13, &handle, v19);
        v14 = v15;
        if ( v15 >= 0 )
        {
          if ( v9
            && *v9
            && (v16 = WaasMedic::CProtectionUtil::ApplyPermissionsOnRegistryKey(handle, v9), v14 = v16, v16 < 0) )
          {
            LogLevelW(
              2u,
              L"Caller was allowed write under this path of registry and key was created but applying the optional permiss"
               "ions failed. Error code: 0x%08x",
              (unsigned int)v16);
          }
          else
          {
            v17 = WaasMedic::CProtectionUtil::ApplySecurityDescriptorOnRegistrySubkey(
                    handle,
                    L"S:AI(TL;;KR;;;S-1-19-512-4096)");
            v14 = v17;
            if ( v17 < 0 )
              LogLevelW(
                2u,
                L"Caller was allowed write under this path of registry and key was created but applying the PPL ACL failed"
                 ". Error code: 0x%08x",
                (unsigned int)v17);
          }
        }
        else
        {
          LogLevelW(
            2u,
            L"Caller was allowed to write under this path of registry but the create key operation failed. Error code: 0x%08x",
            (unsigned int)v15);
        }
      }
      else
      {
        v14 = -2147024891;
        LogLevelW(
          3u,
          L"Caller is not granted access to write protected keys under this path. Will return: 0x%08x",
          2147942405LL);
      }
    }
    else
    {
      LogLevelW(2u, L"Error while attempting to verify access to namespace. Error code: 0x%08x.", (unsigned int)v12);
    }
  }
  WaasMedic::TelemetryProvider::ReportRegistryKeyProtectionResult(v14, (const unsigned __int16 *)v10, v8, 1);
  return v14;
}

```

## disassembly

```asm
0x18003a660  mov     [rsp+arg_0], rbx
0x18003a665  mov     [rsp+arg_10], rbp
0x18003a66a  push    rsi
0x18003a66b  push    rdi
0x18003a66c  push    r12
0x18003a66e  push    r14
0x18003a670  push    r15
0x18003a672  sub     rsp, 30h
0x18003a676  movsxd  rbx, edx
0x18003a679  xor     r15d, r15d
0x18003a67c  xor     edx, edx; length
0x18003a67e  mov     [rsp+58h+handle], r15
0x18003a683  mov     rcx, r8; string
0x18003a686  mov     rdi, r9
0x18003a689  call    cs:__imp_WindowsGetStringRawBuffer
0x18003a68f  cmp     word ptr [rdi], 8
0x18003a693  mov     rbp, rax
0x18003a696  jnz     short loc_18003A69E
0x18003a698  mov     rdi, [rdi+8]
0x18003a69c  jmp     short loc_18003A6A1
0x18003a69e  mov     rdi, r15
0x18003a6a1  test    ebx, ebx
0x18003a6a3  js      loc_18003A782
0x18003a6a9  cmp     ebx, 7
0x18003a6ac  jnb     loc_18003A782
0x18003a6b2  lea     r12, __ImageBase
0x18003a6b9  mov     byte ptr [rsp+58h+arg_8], r15b
0x18003a6be  mov     rsi, ds:rva off_180070EA0[r12+rbx*8]; "HKEY_CLASSES_ROOT\\" ...
0x18003a6c6  lea     r8, [rsp+58h+arg_8]; unsigned __int16 *
0x18003a6cb  mov     rcx, rsi; this
0x18003a6ce  mov     rdx, rbp; unsigned __int16 *
0x18003a6d1  mov     r14, rbx
0x18003a6d4  call    ?IsCallerAllowedToWriteToRegistryPath@ProtectedSettingsNamespaceMapper@WaasMedic@@YAJPEBG0AEA_N@Z; WaasMedic::ProtectedSettingsNamespaceMapper::IsCallerAllowedToWriteToRegistryPath(ushort const *,ushort const *,bool &)
0x18003a6d9  mov     ebx, eax
0x18003a6db  test    eax, eax
0x18003a6dd  jns     short loc_18003A6EE
0x18003a6df  mov     r8d, eax
0x18003a6e2  lea     rdx, aErrorWhileAtte; "Error while attempting to verify access"...
0x18003a6e9  jmp     loc_18003A794
0x18003a6ee  cmp     byte ptr [rsp+58h+arg_8], r15b
0x18003a6f3  jnz     short loc_18003A70E
0x18003a6f5  mov     ebx, 80070005h
0x18003a6fa  lea     rdx, aCallerIsNotGra; "Caller is not granted access to write p"...
0x18003a701  mov     r8d, ebx
0x18003a704  mov     ecx, 3
0x18003a709  jmp     loc_18003A799
0x18003a70e  mov     rcx, ds:rva qword_180085718[r12+r14*8]; hKey
0x18003a716  lea     r9, [rsp+58h+handle]
0x18003a71b  mov     rdx, rbp; lpSubKey
0x18003a71e  call    WaasMedic__RegCreateKeyHelperPrivate
0x18003a723  mov     ebx, eax
0x18003a725  test    eax, eax
0x18003a727  jns     short loc_18003A735
0x18003a729  mov     r8d, eax
0x18003a72c  lea     rdx, aCallerWasAllow_1; "Caller was allowed to write under this "...
0x18003a733  jmp     short loc_18003A794
0x18003a735  test    rdi, rdi
0x18003a738  jz      short loc_18003A75F
0x18003a73a  cmp     [rdi], r15w
0x18003a73e  jz      short loc_18003A75F
0x18003a740  mov     rcx, [rsp+58h+handle]; handle
0x18003a745  mov     rdx, rdi; StringSecurityDescriptor
0x18003a748  call    ?ApplyPermissionsOnRegistryKey@CProtectionUtil@WaasMedic@@SAJPEAUHKEY__@@PEBG@Z; WaasMedic::CProtectionUtil::ApplyPermissionsOnRegistryKey(HKEY__ *,ushort const *)
0x18003a74d  mov     ebx, eax
0x18003a74f  test    eax, eax
0x18003a751  jns     short loc_18003A75F
0x18003a753  mov     r8d, eax
0x18003a756  lea     rdx, aCallerWasAllow; "Caller was allowed write under this pat"...
0x18003a75d  jmp     short loc_18003A794
0x18003a75f  mov     rcx, [rsp+58h+handle]; handle
0x18003a764  lea     rdx, aSAiTlKrS119512; "S:AI(TL;;KR;;;S-1-19-512-4096)"
0x18003a76b  call    ?ApplySecurityDescriptorOnRegistrySubkey@CProtectionUtil@WaasMedic@@CAJPEAUHKEY__@@PEBG@Z; WaasMedic::CProtectionUtil::ApplySecurityDescriptorOnRegistrySubkey(HKEY__ *,ushort const *)
0x18003a770  mov     ebx, eax
0x18003a772  test    eax, eax
0x18003a774  jns     short loc_18003A79E
0x18003a776  mov     r8d, eax
0x18003a779  lea     rdx, aCallerWasAllow_2; "Caller was allowed write under this pat"...
0x18003a780  jmp     short loc_18003A794
0x18003a782  mov     ebx, 8000000Bh
0x18003a787  lea     rdx, aErrorWhileAtte_0; "Error while attempting to determine bas"...
0x18003a78e  mov     r8d, ebx
0x18003a791  mov     rsi, r15
0x18003a794  mov     ecx, 2; unsigned __int8
0x18003a799  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18003a79e  mov     r9b, 1; bool
0x18003a7a1  mov     r8, rbp; unsigned __int16 *
0x18003a7a4  mov     rdx, rsi; unsigned __int16 *
0x18003a7a7  mov     ecx, ebx; int
0x18003a7a9  call    ?ReportRegistryKeyProtectionResult@TelemetryProvider@WaasMedic@@SAXJPEBG0_N@Z; WaasMedic::TelemetryProvider::ReportRegistryKeyProtectionResult(long,ushort const *,ushort const *,bool)
0x18003a7ae  mov     rbp, [rsp+58h+arg_10]
0x18003a7b3  mov     eax, ebx
0x18003a7b5  mov     rbx, [rsp+58h+arg_0]
0x18003a7ba  add     rsp, 30h
0x18003a7be  pop     r15
0x18003a7c0  pop     r14
0x18003a7c2  pop     r12
0x18003a7c4  pop     rdi
0x18003a7c5  pop     rsi
0x18003a7c6  retn
```
