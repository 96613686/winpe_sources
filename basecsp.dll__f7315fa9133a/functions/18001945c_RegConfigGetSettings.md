# RegConfigGetSettings

- ea: `0x18001945c`
- end: `0x180019647`
- name: `RegConfigGetSettings`
- size: `491`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000ed1c`

## callees

- `0x18000de80`
- `0x180015a74`
- `0x180015af0`
- `0x180019430`
- `0x18001945c`
- `0x18001c71c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001952f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800195ef`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001952f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800195ef`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001950e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001950e`

## pseudocode

```c
__int64 __fastcall RegConfigGetSettings(_DWORD *a1)
{
  __int64 v2; // rax
  size_t v3; // rbx
  wchar_t *v4; // rsi
  unsigned int DwordValue; // ebx
  DWORD dwDisposition; // [rsp+78h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+80h] [rbp+30h] BYREF

  v2 = -1;
  dwDisposition = 0;
  hKey = 0;
  do
    ++v2;
  while ( SourceString[v2] );
  v3 = (unsigned int)(2 * v2 + 102);
  v4 = (wchar_t *)MIDL_user_allocate(v3);
  if ( !v4 )
  {
    DwordValue = 8;
    goto LABEL_6;
  }
  StringCbPrintfW(v4, v3, L"%s%s", L"SOFTWARE\\Microsoft\\Cryptography\\Defaults\\Provider\\", SourceString);
  DwordValue = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v4, 0, (LPWSTR)&Class, 0, 0x20019u, 0, &hKey, &dwDisposition);
  CspFreeH(v4);
  if ( DwordValue )
  {
LABEL_6:
    if ( hKey )
      RegCloseKey(hKey);
    goto LABEL_15;
  }
  DwordValue = RegConfigReadDwordValue(hKey, L"DefaultPrivateKeyLenBits", a1 + 1);
  if ( !DwordValue )
  {
    DwordValue = RegConfigReadFlag(hKey, L"RequireOnCardPrivateKeyGen", a1 + 2);
    if ( !DwordValue )
    {
      DwordValue = RegConfigReadDwordValue(hKey, L"TransactionTimeoutMilliseconds", a1 + 3);
      if ( !DwordValue )
      {
        DwordValue = RegConfigReadFlag(hKey, L"AllowPrivateSignatureKeyImport", a1 + 4);
        if ( !DwordValue )
        {
          DwordValue = RegConfigReadFlag(hKey, L"AllowPrivateExchangeKeyImport", a1 + 5);
          if ( !DwordValue )
          {
            DwordValue = RegConfigReadFlag(hKey, L"DisableUncaughtExceptionHandler", a1 + 6);
            if ( !DwordValue )
            {
              *a1 = 1;
              DwordValue = 0;
            }
          }
        }
      }
    }
  }
LABEL_15:
  if ( hKey )
    RegCloseKey(hKey);
  if ( DwordValue )
  {
    dword_18003BE38 = 0;
    qword_18003BE3C = 2048;
    dword_18003BE44 = 1500;
    dword_18003BE4C = 1;
    dword_18003BE48 = 1;
    dword_18003BE50 = 0;
  }
  return DwordValue;
}

```

## disassembly

```asm
0x18001945c  mov     [rsp-18h+arg_0], rbx
0x180019461  mov     [rsp-18h+arg_18], rsi
0x180019466  push    rbp
0x180019467  push    rdi
0x180019468  push    r14
0x18001946a  mov     rbp, rsp
0x18001946d  sub     rsp, 50h
0x180019471  xor     r14d, r14d
0x180019474  mov     rdi, rcx
0x180019477  mov     rcx, cs:SourceString
0x18001947e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180019482  mov     [rbp+dwDisposition], r14d
0x180019486  mov     [rbp+hKey], r14
0x18001948a  inc     rax
0x18001948d  cmp     [rcx+rax*2], r14w
0x180019492  jnz     short loc_18001948A
0x180019494  lea     eax, ds:66h[rax*2]
0x18001949b  mov     ecx, eax; size
0x18001949d  mov     ebx, eax
0x18001949f  call    MIDL_user_allocate
0x1800194a4  mov     rsi, rax
0x1800194a7  test    rax, rax
0x1800194aa  jnz     short loc_1800194B1
0x1800194ac  lea     ebx, [rax+8]
0x1800194af  jmp     short loc_180019522
0x1800194b1  mov     rax, cs:SourceString
0x1800194b8  lea     r9, aSoftwareMicros; "SOFTWARE\\Microsoft\\Cryptography\\Defa"...
0x1800194bf  lea     r8, aSS_0; "%s%s"
0x1800194c6  mov     qword ptr [rsp+50h+dwOptions], rax
0x1800194cb  mov     rdx, rbx; cbDest
0x1800194ce  mov     rcx, rsi; pszDest
0x1800194d1  call    StringCbPrintfW
0x1800194d6  lea     rax, [rbp+dwDisposition]
0x1800194da  xor     r8d, r8d; Reserved
0x1800194dd  mov     [rsp+50h+lpdwDisposition], rax; lpdwDisposition
0x1800194e2  lea     r9, Class; lpClass
0x1800194e9  lea     rax, [rbp+hKey]
0x1800194ed  mov     rdx, rsi; lpSubKey
0x1800194f0  mov     [rsp+50h+phkResult], rax; phkResult
0x1800194f5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800194fc  mov     [rsp+50h+lpSecurityAttributes], r14; lpSecurityAttributes
0x180019501  mov     [rsp+50h+samDesired], 20019h; samDesired
0x180019509  mov     [rsp+50h+dwOptions], r14d; dwOptions
0x18001950e  call    cs:__imp_RegCreateKeyExW
0x180019514  mov     ebx, eax
0x180019516  mov     rcx, rsi
0x180019519  call    CspFreeH
0x18001951e  test    ebx, ebx
0x180019520  jz      short loc_18001953D
0x180019522  mov     rcx, [rbp+hKey]; hKey
0x180019526  test    rcx, rcx
0x180019529  jz      loc_1800195E6
0x18001952f  call    cs:__imp_RegCloseKey
0x180019535  test    ebx, ebx
0x180019537  jnz     loc_1800195E6
0x18001953d  mov     rcx, [rbp+hKey]; HKEY
0x180019541  lea     r8, [rdi+4]; unsigned int *
0x180019545  lea     rdx, aDefaultprivate; "DefaultPrivateKeyLenBits"
0x18001954c  call    ?RegConfigReadDwordValue@@YAKPEAUHKEY__@@PEBGPEAK@Z; RegConfigReadDwordValue(HKEY__ *,ushort const *,ulong *)
0x180019551  mov     ebx, eax
0x180019553  test    eax, eax
0x180019555  jnz     loc_1800195E6
0x18001955b  mov     rcx, [rbp+hKey]; HKEY
0x18001955f  lea     r8, [rdi+8]; int *
0x180019563  lea     rdx, aRequireoncardp; "RequireOnCardPrivateKeyGen"
0x18001956a  call    ?RegConfigReadFlag@@YAKPEAUHKEY__@@PEBGPEAH@Z; RegConfigReadFlag(HKEY__ *,ushort const *,int *)
0x18001956f  mov     ebx, eax
0x180019571  test    eax, eax
0x180019573  jnz     short loc_1800195E6
0x180019575  mov     rcx, [rbp+hKey]; HKEY
0x180019579  lea     r8, [rdi+0Ch]; unsigned int *
0x18001957d  lea     rdx, aTransactiontim; "TransactionTimeoutMilliseconds"
0x180019584  call    ?RegConfigReadDwordValue@@YAKPEAUHKEY__@@PEBGPEAK@Z; RegConfigReadDwordValue(HKEY__ *,ushort const *,ulong *)
0x180019589  mov     ebx, eax
0x18001958b  test    eax, eax
0x18001958d  jnz     short loc_1800195E6
0x18001958f  mov     rcx, [rbp+hKey]; HKEY
0x180019593  lea     r8, [rdi+10h]; int *
0x180019597  lea     rdx, aAllowprivatesi; "AllowPrivateSignatureKeyImport"
0x18001959e  call    ?RegConfigReadFlag@@YAKPEAUHKEY__@@PEBGPEAH@Z; RegConfigReadFlag(HKEY__ *,ushort const *,int *)
0x1800195a3  mov     ebx, eax
0x1800195a5  test    eax, eax
0x1800195a7  jnz     short loc_1800195E6
0x1800195a9  mov     rcx, [rbp+hKey]; HKEY
0x1800195ad  lea     r8, [rdi+14h]; int *
0x1800195b1  lea     rdx, aAllowprivateex; "AllowPrivateExchangeKeyImport"
0x1800195b8  call    ?RegConfigReadFlag@@YAKPEAUHKEY__@@PEBGPEAH@Z; RegConfigReadFlag(HKEY__ *,ushort const *,int *)
0x1800195bd  mov     ebx, eax
0x1800195bf  test    eax, eax
0x1800195c1  jnz     short loc_1800195E6
0x1800195c3  mov     rcx, [rbp+hKey]; HKEY
0x1800195c7  lea     r8, [rdi+18h]; int *
0x1800195cb  lea     rdx, aDisableuncaugh; "DisableUncaughtExceptionHandler"
0x1800195d2  call    ?RegConfigReadFlag@@YAKPEAUHKEY__@@PEBGPEAH@Z; RegConfigReadFlag(HKEY__ *,ushort const *,int *)
0x1800195d7  mov     ebx, eax
0x1800195d9  test    eax, eax
0x1800195db  jnz     short loc_1800195E6
0x1800195dd  mov     dword ptr [rdi], 1
0x1800195e3  mov     ebx, r14d
0x1800195e6  mov     rcx, [rbp+hKey]; hKey
0x1800195ea  test    rcx, rcx
0x1800195ed  jz      short loc_1800195F5
0x1800195ef  call    cs:__imp_RegCloseKey
0x1800195f5  test    ebx, ebx
0x1800195f7  jz      short loc_180019630
0x1800195f9  mov     cs:dword_18003BE38, r14d
0x180019600  mov     cs:qword_18003BE3C, 800h
0x18001960b  mov     cs:dword_18003BE44, 5DCh
0x180019615  mov     cs:dword_18003BE4C, 1
0x18001961f  mov     cs:dword_18003BE48, 1
0x180019629  mov     cs:dword_18003BE50, r14d
0x180019630  lea     r11, [rsp+50h+var_s0]
0x180019635  mov     eax, ebx
0x180019637  mov     rbx, [r11+20h]
0x18001963b  mov     rsi, [r11+38h]
0x18001963f  mov     rsp, r11
0x180019642  pop     r14
0x180019644  pop     rdi
0x180019645  pop     rbp
0x180019646  retn
```
