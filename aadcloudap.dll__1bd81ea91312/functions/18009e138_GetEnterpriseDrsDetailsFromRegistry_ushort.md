# GetEnterpriseDrsDetailsFromRegistry(ushort * *)

- ea: `0x18009e138`
- end: `0x18009e2d7`
- name: `?GetEnterpriseDrsDetailsFromRegistry@@YAJPEAPEAG@Z`
- size: `415`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
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
- `0x18009e138`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009e1bc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009e1bc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009e294`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009e294`

## string_xrefs

- `0x18009e269`: `CopyStringW`
- `0x18009e1c8`: `RegOpenKeyExW`
- `0x18009e23a`: `%s: enterpriseDrsName NOT found in registry.`
- `0x18009e14a`: `GetEnterpriseDrsDetailsFromRegistry`

## pseudocode

```c
__int64 __fastcall GetEnterpriseDrsDetailsFromRegistry(unsigned __int16 **a1)
{
  unsigned __int16 *v2; // rsi
  int v3; // edi
  unsigned int v4; // ebx
  unsigned int v5; // eax
  unsigned int v6; // eax
  unsigned __int64 v7; // rdx
  int v8; // eax
  HKEY hKey; // [rsp+60h] [rbp+8h] BYREF
  unsigned __int16 *Source; // [rsp+68h] [rbp+10h] BYREF

  hKey = 0;
  Source = 0;
  v2 = 0;
  if ( a1 )
  {
    *a1 = 0;
    v4 = 0;
    v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\CDJ", 0, 0x20019u, &hKey);
    v3 = v5;
    if ( v5 )
    {
      Logger::TraceError(
        L"%s: %s failed with win32 error code: 0x%08x.",
        L"GetEnterpriseDrsDetailsFromRegistry",
        L"RegOpenKeyExW",
        v5);
    }
    else
    {
      v6 = RegReadStringValue(
             hKey,
             0,
             L"EnterpriseDrsName",
             L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\CDJ",
             2u,
             &Source);
      v3 = v6;
      if ( v6 )
      {
        Logger::TraceError(
          L"%s: %s failed with win32 error code: 0x%08x.",
          L"GetEnterpriseDrsDetailsFromRegistry",
          L"GetStringFromRegKey",
          v6);
        v2 = Source;
      }
      else
      {
        v2 = Source;
        if ( Source )
        {
          v7 = -1;
          do
            ++v7;
          while ( Source[v7] );
          v8 = CopyStringW(Source, v7, a1);
          v4 = v8;
          if ( v8 < 0 )
            Logger::TraceError(
              L"%s: %s failed with error code: 0x%08x.",
              L"GetEnterpriseDrsDetailsFromRegistry",
              L"CopyStringW",
              (unsigned int)v8);
        }
        else
        {
          v4 = 1;
          Logger::TraceInformation(
            L"%s: enterpriseDrsName NOT found in registry.",
            L"GetEnterpriseDrsDetailsFromRegistry");
        }
      }
    }
  }
  else
  {
    v3 = 0;
    v4 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"GetEnterpriseDrsDetailsFromRegistry",
      L"ppszEnterpriseDrsName");
    Logger::WriteNullOrEmptyParameterFailureEvent(L"GetEnterpriseDrsDetailsFromRegistry", L"ppszEnterpriseDrsName");
  }
  SafeFree(v2);
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( v3 )
  {
    if ( v3 > 0 )
      v4 = (unsigned __int16)v3 | 0x80070000;
    else
      v4 = v3;
  }
  Logger::TraceVerbose(L"%s - hr: 0x%08x", L"GetEnterpriseDrsDetailsFromRegistry", v4);
  return v4;
}

```

## disassembly

```asm
0x18009e138  mov     [rsp+arg_10], rbx
0x18009e13d  push    rbp
0x18009e13e  push    rsi
0x18009e13f  push    rdi
0x18009e140  push    r14
0x18009e142  push    r15
0x18009e144  sub     rsp, 30h
0x18009e148  xor     ebp, ebp
0x18009e14a  lea     r15, aGetenterprised; "GetEnterpriseDrsDetailsFromRegistry"
0x18009e151  mov     [rsp+58h+hKey], rbp
0x18009e156  mov     r14, rcx
0x18009e159  mov     [rsp+58h+Source], rbp
0x18009e15e  mov     esi, ebp
0x18009e160  test    rcx, rcx
0x18009e163  jnz     short loc_18009E196
0x18009e165  lea     r8, aPpszenterprise; "ppszEnterpriseDrsName"
0x18009e16c  mov     rdx, r15
0x18009e16f  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x18009e176  mov     edi, ebp
0x18009e178  mov     ebx, 80070057h
0x18009e17d  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18009e182  lea     rdx, aPpszenterprise; "ppszEnterpriseDrsName"
0x18009e189  mov     rcx, r15; unsigned __int16 *
0x18009e18c  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x18009e191  jmp     loc_18009E282
0x18009e196  mov     [rcx], rbp
0x18009e199  lea     rax, [rsp+58h+hKey]
0x18009e19e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18009e1a5  mov     [rsp+58h+phkResult], rax; phkResult
0x18009e1aa  mov     r9d, 20019h; samDesired
0x18009e1b0  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18009e1b7  xor     r8d, r8d; ulOptions
0x18009e1ba  mov     ebx, ebp
0x18009e1bc  call    cs:__imp_RegOpenKeyExW
0x18009e1c2  mov     edi, eax
0x18009e1c4  test    eax, eax
0x18009e1c6  jz      short loc_18009E1DB
0x18009e1c8  lea     r8, aRegopenkeyexw; "RegOpenKeyExW"
0x18009e1cf  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x18009e1d6  jmp     loc_18009E277
0x18009e1db  mov     rcx, [rsp+58h+hKey]; hkey
0x18009e1e0  lea     rax, [rsp+58h+Source]
0x18009e1e5  mov     [rsp+58h+var_30], rax; unsigned __int16 **
0x18009e1ea  lea     r9, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18009e1f1  lea     r8, aEnterprisedrsn; "EnterpriseDrsName"
0x18009e1f8  mov     dword ptr [rsp+58h+phkResult], 2; dwFlags
0x18009e200  xor     edx, edx; lpSubKey
0x18009e202  call    ?RegReadStringValue@@YAKPEAUHKEY__@@PEBG11KPEAPEAG@Z; RegReadStringValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong,ushort * *)
0x18009e207  mov     edi, eax
0x18009e209  test    eax, eax
0x18009e20b  jz      short loc_18009E22D
0x18009e20d  mov     r9d, eax
0x18009e210  lea     r8, aGetstringfromr; "GetStringFromRegKey"
0x18009e217  mov     rdx, r15
0x18009e21a  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x18009e221  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18009e226  mov     rsi, [rsp+58h+Source]
0x18009e22b  jmp     short loc_18009E282
0x18009e22d  mov     rsi, [rsp+58h+Source]
0x18009e232  test    rsi, rsi
0x18009e235  jnz     short loc_18009E24B
0x18009e237  mov     rdx, r15
0x18009e23a  lea     rcx, aSEnterprisedrs; "%s: enterpriseDrsName NOT found in regi"...
0x18009e241  lea     ebx, [rsi+1]
0x18009e244  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x18009e249  jmp     short loc_18009E282
0x18009e24b  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18009e24f  inc     rdx; unsigned __int64
0x18009e252  cmp     [rsi+rdx*2], bp
0x18009e256  jnz     short loc_18009E24F
0x18009e258  mov     r8, r14; unsigned __int16 **
0x18009e25b  mov     rcx, rsi; Source
0x18009e25e  call    ?CopyStringW@@YAJPEBG_KPEAPEAG@Z; CopyStringW(ushort const *,unsigned __int64,ushort * *)
0x18009e263  mov     ebx, eax
0x18009e265  test    eax, eax
0x18009e267  jns     short loc_18009E282
0x18009e269  lea     r8, aCopystringw; "CopyStringW"
0x18009e270  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x18009e277  mov     r9d, eax
0x18009e27a  mov     rdx, r15
0x18009e27d  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18009e282  mov     rcx, rsi; void *
0x18009e285  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18009e28a  mov     rcx, [rsp+58h+hKey]; hKey
0x18009e28f  test    rcx, rcx
0x18009e292  jz      short loc_18009E29F
0x18009e294  call    cs:__imp_RegCloseKey
0x18009e29a  mov     [rsp+58h+hKey], rbp
0x18009e29f  test    edi, edi
0x18009e2a1  jz      short loc_18009E2B2
0x18009e2a3  jg      short loc_18009E2A9
0x18009e2a5  mov     ebx, edi
0x18009e2a7  jmp     short loc_18009E2B2
0x18009e2a9  movzx   ebx, di
0x18009e2ac  or      ebx, 80070000h
0x18009e2b2  mov     r8d, ebx
0x18009e2b5  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x18009e2bc  mov     rdx, r15
0x18009e2bf  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18009e2c4  mov     eax, ebx
0x18009e2c6  mov     rbx, [rsp+58h+arg_10]
0x18009e2cb  add     rsp, 30h
0x18009e2cf  pop     r15
0x18009e2d1  pop     r14
0x18009e2d3  pop     rdi
0x18009e2d4  pop     rsi
0x18009e2d5  pop     rbp
0x18009e2d6  retn
```
