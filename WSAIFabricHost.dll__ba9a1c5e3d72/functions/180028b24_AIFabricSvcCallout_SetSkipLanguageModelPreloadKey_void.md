# AIFabricSvcCallout::SetSkipLanguageModelPreloadKey(void)

- ea: `0x180028b24`
- end: `0x180028c18`
- name: `?SetSkipLanguageModelPreloadKey@AIFabricSvcCallout@@CAXXZ`
- size: `244`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180024bc4`
- `0x180081c2c`

## callees

- `0x18001896c`
- `0x1800275dc`
- `0x180028b24`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028bd8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028bd8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180028beb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180028beb`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180028ba0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180028ba0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028be3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028bfd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028be3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028bfd`

## string_xrefs

- `0x180028bae`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\aifabricsvccallout.cpp`

## pseudocode

```c
void AIFabricSvcCallout::SetSkipLanguageModelPreloadKey(void)
{
  LSTATUS v0; // eax
  HKEY v1; // r14
  HKEY v2; // rsi
  DWORD LastError; // ebx
  DWORD dwOptions; // [rsp+20h] [rbp-50h]
  HKEY phkResult; // [rsp+58h] [rbp-18h] BYREF
  char v6; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]
  DWORD dwDisposition; // [rsp+90h] [rbp+20h] BYREF
  HKEY hKey; // [rsp+98h] [rbp+28h]

  TelemetryLogger::LanguageModelNotAvailableForPreload();
  hKey = 0;
  dwDisposition = 0;
  phkResult = 0;
  v6 = 1;
  v0 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows NT\\CurrentVersion\\WorkloadManager\\SkipLanguageModelPreload",
         0,
         0,
         1u,
         0xF003Fu,
         0,
         &phkResult,
         &dwDisposition);
  if ( v0 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x129,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\aifabricsvccallout.cpp",
      (const char *)(unsigned int)v0,
      dwOptions);
  if ( v6 )
  {
    v1 = phkResult;
    v2 = hKey;
    if ( hKey )
    {
      LastError = GetLastError();
      RegCloseKey(v2);
      SetLastError(LastError);
    }
    hKey = v1;
  }
  if ( hKey )
    RegCloseKey(hKey);
}

```

## disassembly

```asm
0x180028b24  mov     [rsp-18h+arg_10], rbx
0x180028b29  mov     [rsp-18h+arg_18], rsi
0x180028b2e  push    rbp
0x180028b2f  push    rdi
0x180028b30  push    r14
0x180028b32  mov     rbp, rsp
0x180028b35  sub     rsp, 70h
0x180028b39  call    ?LanguageModelNotAvailableForPreload@TelemetryLogger@@SAXXZ; TelemetryLogger::LanguageModelNotAvailableForPreload(void)
0x180028b3e  lea     rax, [rbp+hKey]
0x180028b42  mov     [rbp+hKey], 0
0x180028b4a  mov     [rbp+var_20], rax
0x180028b4e  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\Windows NT\\Curren"...
0x180028b55  lea     rax, [rbp+dwDisposition]
0x180028b59  mov     [rbp+dwDisposition], 0
0x180028b60  mov     [rsp+70h+lpdwDisposition], rax; lpdwDisposition
0x180028b65  xor     r9d, r9d; lpClass
0x180028b68  lea     rax, [rbp+var_18]
0x180028b6c  mov     [rbp+var_18], 0
0x180028b74  mov     [rsp+70h+phkResult], rax; phkResult
0x180028b79  xor     r8d, r8d; Reserved
0x180028b7c  mov     [rsp+70h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180028b85  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180028b8c  mov     [rsp+70h+samDesired], 0F003Fh; samDesired
0x180028b94  mov     [rsp+70h+dwOptions], 1; int
0x180028b9c  mov     [rbp+var_10], 1
0x180028ba0  call    cs:__imp_RegCreateKeyExW
0x180028ba6  test    eax, eax
0x180028ba8  jns     short loc_180028BC2
0x180028baa  mov     rcx, [rbp+18h]; this
0x180028bae  lea     r8, aOnecoreuapBase_7; "onecoreuap\\base\\appmodel\\search\\com"...
0x180028bb5  mov     r9d, eax; char *
0x180028bb8  mov     edx, 129h; void *
0x180028bbd  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180028bc2  cmp     [rbp+var_10], 0
0x180028bc6  jz      short loc_180028BF4
0x180028bc8  mov     rdi, [rbp+var_20]
0x180028bcc  mov     r14, [rbp+var_18]
0x180028bd0  mov     rsi, [rdi]
0x180028bd3  test    rsi, rsi
0x180028bd6  jz      short loc_180028BF1
0x180028bd8  call    cs:__imp_GetLastError
0x180028bde  mov     rcx, rsi; hKey
0x180028be1  mov     ebx, eax
0x180028be3  call    cs:__imp_RegCloseKey
0x180028be9  mov     ecx, ebx; dwErrCode
0x180028beb  call    cs:__imp_SetLastError
0x180028bf1  mov     [rdi], r14
0x180028bf4  mov     rcx, [rbp+hKey]; hKey
0x180028bf8  test    rcx, rcx
0x180028bfb  jz      short loc_180028C03
0x180028bfd  call    cs:__imp_RegCloseKey
0x180028c03  lea     r11, [rsp+70h+var_s0]
0x180028c08  mov     rbx, [r11+30h]
0x180028c0c  mov     rsi, [r11+38h]
0x180028c10  mov     rsp, r11
0x180028c13  pop     r14
0x180028c15  pop     rdi
0x180028c16  pop     rbp
0x180028c17  retn
```
