# GetAadTenantDetailsFromRegistry(ushort * *,ushort * *)

- ea: `0x18009d3a8`
- end: `0x18009d693`
- name: `?GetAadTenantDetailsFromRegistry@@YAJPEAPEAG0@Z`
- size: `747`
- prototype: `__int64 __fastcall(unsigned __int16 **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18009d69c`

## callees

- `0x180085db4`
- `0x180086cdc`
- `0x1800871b4`
- `0x18008aa28`
- `0x18008aa64`
- `0x18008aa9c`
- `0x18008aecc`
- `0x18008afb0`
- `0x18009d3a8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009d46f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009d46f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009d649`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009d649`

## string_xrefs

- `0x18009d5c2`: `CopyStringW`
- `0x18009d605`: `CopyStringW`
- `0x18009d507`: `RegReadStringValue`
- `0x18009d55d`: `RegReadStringValue`
- `0x18009d489`: `RegOpenKeyExW`
- `0x18009d4b5`: `RegOpenKeyExW`
- `0x18009d3ee`: `GetAadTenantDetailsFromRegistry`
- `0x18009d408`: `GetAadTenantDetailsFromRegistry`
- `0x18009d42a`: `GetAadTenantDetailsFromRegistry`
- `0x18009d49f`: `GetAadTenantDetailsFromRegistry`
- `0x18009d4c3`: `GetAadTenantDetailsFromRegistry`
- `0x18009d50e`: `GetAadTenantDetailsFromRegistry`
- `0x18009d564`: `GetAadTenantDetailsFromRegistry`
- `0x18009d5c9`: `GetAadTenantDetailsFromRegistry`
- `0x18009d618`: `GetAadTenantDetailsFromRegistry`
- `0x18009d669`: `GetAadTenantDetailsFromRegistry`
- `0x18009d624`: `%s: Either tenant name or tenant ID is empty in the registry.`
- `0x18009d4a6`: `%s: Cannot open AAD tenant info registry key "%s". RegOpenKeyExW failed with error code: 0x%08x.`

## pseudocode

```c
__int64 __fastcall GetAadTenantDetailsFromRegistry(unsigned __int16 **a1, unsigned __int16 **a2)
{
  int v4; // edi
  unsigned __int16 *v5; // rsi
  unsigned __int16 *v6; // r14
  unsigned int v7; // ebx
  const unsigned __int16 *v8; // rdx
  LSTATUS v9; // eax
  unsigned int v10; // eax
  unsigned int v11; // eax
  unsigned __int64 v12; // r15
  unsigned __int64 v13; // rdx
  int v14; // eax
  HKEY hKey; // [rsp+70h] [rbp+40h] BYREF
  unsigned __int16 *Source; // [rsp+80h] [rbp+50h] BYREF
  unsigned __int16 *v18; // [rsp+88h] [rbp+58h] BYREF

  hKey = 0;
  Source = 0;
  v4 = 0;
  v18 = 0;
  v5 = 0;
  v6 = 0;
  if ( !a1 )
  {
    v7 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"GetAadTenantDetailsFromRegistry", L"ppszTenantId");
    v8 = L"ppszTenantId";
LABEL_3:
    Logger::WriteNullOrEmptyParameterFailureEvent(L"GetAadTenantDetailsFromRegistry", v8);
    goto LABEL_25;
  }
  if ( !a2 )
  {
    v7 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"GetAadTenantDetailsFromRegistry", L"ppszTenantName");
    v8 = L"ppszTenantName";
    goto LABEL_3;
  }
  *a1 = 0;
  *a2 = 0;
  v7 = 0;
  v9 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\CDJ\\AAD", 0, 0x20019u, &hKey);
  v4 = v9;
  if ( v9 )
  {
    if ( v9 != 2 )
      Logger::WriteRegistryFailureEvent(
        v9,
        L"RegOpenKeyExW",
        L"HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\CDJ\\AAD");
    Logger::TraceInformation(
      L"%s: Cannot open AAD tenant info registry key \"%s\". RegOpenKeyExW failed with error code: 0x%08x.",
      L"GetAadTenantDetailsFromRegistry",
      L"HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\CDJ\\AAD",
      (unsigned int)v4);
    Logger::TraceError(
      L"%s: %s failed with win32 error code: 0x%08x.",
      L"GetAadTenantDetailsFromRegistry",
      L"RegOpenKeyExW",
      (unsigned int)v4);
  }
  else
  {
    v10 = RegReadStringValue(
            hKey,
            0,
            L"TenantId",
            L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\CDJ\\AAD",
            2u,
            &Source);
    v4 = v10;
    if ( v10 )
    {
      Logger::TraceError(
        L"%s: %s failed with win32 error code: 0x%08x.",
        L"GetAadTenantDetailsFromRegistry",
        L"RegReadStringValue",
        v10);
      v5 = Source;
    }
    else
    {
      v11 = RegReadStringValue(
              hKey,
              0,
              L"TenantName",
              L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\CDJ\\AAD",
              2u,
              &v18);
      v4 = v11;
      if ( v11 )
      {
        Logger::TraceError(
          L"%s: %s failed with win32 error code: 0x%08x.",
          L"GetAadTenantDetailsFromRegistry",
          L"RegReadStringValue",
          v11);
        v5 = Source;
        v6 = v18;
      }
      else
      {
        v6 = v18;
        v5 = Source;
        if ( v18 && Source )
        {
          v12 = -1;
          v13 = -1;
          do
            ++v13;
          while ( Source[v13] );
          v7 = CopyStringW(Source, v13, a1);
          if ( (v7 & 0x80000000) == 0 )
          {
            do
              ++v12;
            while ( v6[v12] );
            v14 = CopyStringW(v6, v12, a2);
            v7 = v14;
            if ( v14 < 0 )
              Logger::TraceError(
                L"%s: %s failed with error code: 0x%08x.",
                L"GetAadTenantDetailsFromRegistry",
                L"CopyStringW",
                (unsigned int)v14);
          }
          else
          {
            Logger::TraceError(
              L"%s: %s failed with error code: 0x%08x.",
              L"GetAadTenantDetailsFromRegistry",
              L"CopyStringW",
              v7);
          }
        }
        else
        {
          v7 = 1;
          Logger::TraceInformation(
            L"%s: Either tenant name or tenant ID is empty in the registry.",
            L"GetAadTenantDetailsFromRegistry");
        }
      }
    }
  }
LABEL_25:
  SafeFree(v5);
  SafeFree(v6);
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( v4 )
  {
    if ( v4 > 0 )
      v7 = (unsigned __int16)v4 | 0x80070000;
    else
      v7 = v4;
  }
  Logger::TraceVerbose(L"%s - hr: 0x%08x", L"GetAadTenantDetailsFromRegistry", v7);
  return v7;
}

```

## disassembly

```asm
0x18009d3a8  mov     [rsp-38h+arg_8], rbx
0x18009d3ad  push    rbp
0x18009d3ae  push    rsi
0x18009d3af  push    rdi
0x18009d3b0  push    r12
0x18009d3b2  push    r13
0x18009d3b4  push    r14
0x18009d3b6  push    r15
0x18009d3b8  mov     rbp, rsp
0x18009d3bb  sub     rsp, 30h
0x18009d3bf  xor     r15d, r15d
0x18009d3c2  mov     r13, rdx
0x18009d3c5  mov     [rbp+hKey], r15
0x18009d3c9  mov     r12, rcx
0x18009d3cc  mov     [rbp+Source], r15
0x18009d3d0  mov     edi, r15d
0x18009d3d3  mov     [rbp+arg_18], r15
0x18009d3d7  mov     esi, r15d
0x18009d3da  mov     r14d, r15d
0x18009d3dd  test    rcx, rcx
0x18009d3e0  jnz     short loc_18009D419
0x18009d3e2  lea     r8, aPpsztenantid; "ppszTenantId"
0x18009d3e9  mov     ebx, 80070057h
0x18009d3ee  lea     rdx, aGetaadtenantde; "GetAadTenantDetailsFromRegistry"
0x18009d3f5  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x18009d3fc  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18009d401  lea     rdx, aPpsztenantid; "ppszTenantId"
0x18009d408  lea     rcx, aGetaadtenantde; "GetAadTenantDetailsFromRegistry"
0x18009d40f  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x18009d414  jmp     loc_18009D630
0x18009d419  test    r13, r13
0x18009d41c  jnz     short loc_18009D446
0x18009d41e  lea     r8, aPpsztenantname; "ppszTenantName"
0x18009d425  mov     ebx, 80070057h
0x18009d42a  lea     rdx, aGetaadtenantde; "GetAadTenantDetailsFromRegistry"
0x18009d431  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x18009d438  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18009d43d  lea     rdx, aPpsztenantname; "ppszTenantName"
0x18009d444  jmp     short loc_18009D408
0x18009d446  mov     [rcx], r15
0x18009d449  lea     rax, [rbp+hKey]
0x18009d44d  mov     [rdx], r15
0x18009d450  mov     r9d, 20019h; samDesired
0x18009d456  lea     rdx, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18009d45d  mov     [rsp+30h+phkResult], rax; phkResult
0x18009d462  xor     r8d, r8d; ulOptions
0x18009d465  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18009d46c  mov     ebx, r15d
0x18009d46f  call    cs:__imp_RegOpenKeyExW
0x18009d475  mov     edi, eax
0x18009d477  test    eax, eax
0x18009d479  jz      short loc_18009D4D4
0x18009d47b  cmp     eax, 2
0x18009d47e  jz      short loc_18009D495
0x18009d480  lea     r8, aHkeyLocalMachi_2; "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft"...
0x18009d487  mov     ecx, eax; unsigned int
0x18009d489  lea     rdx, aRegopenkeyexw; "RegOpenKeyExW"
0x18009d490  call    ?WriteRegistryFailureEvent@Logger@@SAJKPEBG0@Z; Logger::WriteRegistryFailureEvent(ulong,ushort const *,ushort const *)
0x18009d495  mov     r9d, edi
0x18009d498  lea     r8, aHkeyLocalMachi_2; "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft"...
0x18009d49f  lea     rdx, aGetaadtenantde; "GetAadTenantDetailsFromRegistry"
0x18009d4a6  lea     rcx, aSCannotOpenAad; "%s: Cannot open AAD tenant info registr"...
0x18009d4ad  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x18009d4b2  mov     r9d, edi
0x18009d4b5  lea     r8, aRegopenkeyexw; "RegOpenKeyExW"
0x18009d4bc  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x18009d4c3  lea     rdx, aGetaadtenantde; "GetAadTenantDetailsFromRegistry"
0x18009d4ca  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18009d4cf  jmp     loc_18009D630
0x18009d4d4  mov     rcx, [rbp+hKey]; hkey
0x18009d4d8  lea     rax, [rbp+Source]
0x18009d4dc  mov     [rsp+30h+var_8], rax; unsigned __int16 **
0x18009d4e1  lea     r9, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18009d4e8  lea     r8, aTenantid_0; "TenantId"
0x18009d4ef  mov     dword ptr [rsp+30h+phkResult], 2; dwFlags
0x18009d4f7  xor     edx, edx; lpSubKey
0x18009d4f9  call    ?RegReadStringValue@@YAKPEAUHKEY__@@PEBG11KPEAPEAG@Z; RegReadStringValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong,ushort * *)
0x18009d4fe  mov     edi, eax
0x18009d500  test    eax, eax
0x18009d502  jz      short loc_18009D52A
0x18009d504  mov     r9d, eax
0x18009d507  lea     r8, aRegreadstringv; "RegReadStringValue"
0x18009d50e  lea     rdx, aGetaadtenantde; "GetAadTenantDetailsFromRegistry"
0x18009d515  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x18009d51c  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18009d521  mov     rsi, [rbp+Source]
0x18009d525  jmp     loc_18009D630
0x18009d52a  mov     rcx, [rbp+hKey]; hkey
0x18009d52e  lea     rax, [rbp+arg_18]
0x18009d532  mov     [rsp+30h+var_8], rax; unsigned __int16 **
0x18009d537  lea     r9, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18009d53e  lea     r8, aTenantname; "TenantName"
0x18009d545  mov     dword ptr [rsp+30h+phkResult], 2; dwFlags
0x18009d54d  xor     edx, edx; lpSubKey
0x18009d54f  call    ?RegReadStringValue@@YAKPEAUHKEY__@@PEBG11KPEAPEAG@Z; RegReadStringValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong,ushort * *)
0x18009d554  mov     edi, eax
0x18009d556  test    eax, eax
0x18009d558  jz      short loc_18009D584
0x18009d55a  mov     r9d, eax
0x18009d55d  lea     r8, aRegreadstringv; "RegReadStringValue"
0x18009d564  lea     rdx, aGetaadtenantde; "GetAadTenantDetailsFromRegistry"
0x18009d56b  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x18009d572  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18009d577  mov     rsi, [rbp+Source]
0x18009d57b  mov     r14, [rbp+arg_18]
0x18009d57f  jmp     loc_18009D630
0x18009d584  mov     r14, [rbp+arg_18]
0x18009d588  mov     rsi, [rbp+Source]
0x18009d58c  test    r14, r14
0x18009d58f  jz      loc_18009D618
0x18009d595  test    rsi, rsi
0x18009d598  jz      short loc_18009D618
0x18009d59a  or      r15, 0FFFFFFFFFFFFFFFFh
0x18009d59e  mov     rdx, r15
0x18009d5a1  xor     eax, eax
0x18009d5a3  inc     rdx; unsigned __int64
0x18009d5a6  cmp     [rsi+rdx*2], ax
0x18009d5aa  jnz     short loc_18009D5A3
0x18009d5ac  mov     r8, r12; unsigned __int16 **
0x18009d5af  mov     rcx, rsi; Source
0x18009d5b2  call    ?CopyStringW@@YAJPEBG_KPEAPEAG@Z; CopyStringW(ushort const *,unsigned __int64,ushort * *)
0x18009d5b7  mov     ebx, eax
0x18009d5b9  xor     eax, eax
0x18009d5bb  test    ebx, ebx
0x18009d5bd  jns     short loc_18009D5E1
0x18009d5bf  mov     r9d, ebx
0x18009d5c2  lea     r8, aCopystringw; "CopyStringW"
0x18009d5c9  lea     rdx, aGetaadtenantde; "GetAadTenantDetailsFromRegistry"
0x18009d5d0  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x18009d5d7  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18009d5dc  xor     r15d, r15d
0x18009d5df  jmp     short loc_18009D630
0x18009d5e1  inc     r15
0x18009d5e4  cmp     [r14+r15*2], ax
0x18009d5e9  jnz     short loc_18009D5E1
0x18009d5eb  mov     r8, r13; unsigned __int16 **
0x18009d5ee  mov     rdx, r15; unsigned __int64
0x18009d5f1  mov     rcx, r14; Source
0x18009d5f4  call    ?CopyStringW@@YAJPEBG_KPEAPEAG@Z; CopyStringW(ushort const *,unsigned __int64,ushort * *)
0x18009d5f9  xor     r15d, r15d
0x18009d5fc  mov     ebx, eax
0x18009d5fe  test    eax, eax
0x18009d600  jns     short loc_18009D630
0x18009d602  mov     r9d, eax
0x18009d605  lea     r8, aCopystringw; "CopyStringW"
0x18009d60c  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x18009d613  jmp     loc_18009D4C3
0x18009d618  lea     rdx, aGetaadtenantde; "GetAadTenantDetailsFromRegistry"
0x18009d61f  mov     ebx, 1
0x18009d624  lea     rcx, aSEitherTenantN; "%s: Either tenant name or tenant ID is "...
0x18009d62b  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x18009d630  mov     rcx, rsi; void *
0x18009d633  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18009d638  mov     rcx, r14; void *
0x18009d63b  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18009d640  mov     rcx, [rbp+hKey]; hKey
0x18009d644  test    rcx, rcx
0x18009d647  jz      short loc_18009D653
0x18009d649  call    cs:__imp_RegCloseKey
0x18009d64f  mov     [rbp+hKey], r15
0x18009d653  test    edi, edi
0x18009d655  jz      short loc_18009D666
0x18009d657  jg      short loc_18009D65D
0x18009d659  mov     ebx, edi
0x18009d65b  jmp     short loc_18009D666
0x18009d65d  movzx   ebx, di
0x18009d660  or      ebx, 80070000h
0x18009d666  mov     r8d, ebx
0x18009d669  lea     rdx, aGetaadtenantde; "GetAadTenantDetailsFromRegistry"
0x18009d670  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x18009d677  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18009d67c  mov     eax, ebx
0x18009d67e  mov     rbx, [rsp+30h+arg_8]
0x18009d683  add     rsp, 30h
0x18009d687  pop     r15
0x18009d689  pop     r14
0x18009d68b  pop     r13
0x18009d68d  pop     r12
0x18009d68f  pop     rdi
0x18009d690  pop     rsi
0x18009d691  pop     rbp
0x18009d692  retn
```
