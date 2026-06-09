# DIGEST_CONTEXT_CACHE::Initialize(int)

- ea: `0x180004a18`
- end: `0x180004b13`
- name: `?Initialize@DIGEST_CONTEXT_CACHE@@QEAAJH@Z`
- size: `251`
- prototype: `__int64 __fastcall(PVOID Parameter, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x180002fb0`

## callees

- `0x180004a18`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004af4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004af4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004a70`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004a70`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004abe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004abe`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180004aa7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180004aa7`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x180004aea`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x180004aea`

## string_xrefs

- `0x180004a38`: `DigestContextCacheTTL`
- `0x180004a2e`: `DigestPartialContextCacheTTL`
- `0x180004a56`: `System\CurrentControlSet\Services\inetinfo\Parameters`

## pseudocode

```c
signed int __fastcall DIGEST_CONTEXT_CACHE::Initialize(void **Parameter, int a2)
{
  const WCHAR *v3; // rsi
  int v4; // ebx
  signed int result; // eax
  int Data; // [rsp+70h] [rbp+28h] BYREF
  DWORD Type; // [rsp+78h] [rbp+30h] BYREF
  DWORD cbData; // [rsp+80h] [rbp+38h] BYREF
  HKEY hKey; // [rsp+88h] [rbp+40h] BYREF

  hKey = 0;
  v3 = L"DigestContextCacheTTL";
  if ( !a2 )
    v3 = L"DigestPartialContextCacheTTL";
  v4 = a2 != 0 ? 300 : 30;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"System\\CurrentControlSet\\Services\\inetinfo\\Parameters",
          0,
          0x20019u,
          &hKey) )
  {
    Data = 0;
    Type = 0;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, v3, 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 )
      v4 = Data;
    RegCloseKey(hKey);
  }
  if ( CreateTimerQueueTimer(
         Parameter + 11,
         0,
         DIGEST_CONTEXT_CACHE::ScavengerCallback,
         Parameter,
         1000 * v4,
         1000 * v4,
         0x10u) )
  {
    return 0;
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180004a18  push    rbp
0x180004a1a  push    rbx
0x180004a1b  push    rsi
0x180004a1c  push    rdi
0x180004a1d  mov     rbp, rsp
0x180004a20  sub     rsp, 48h
0x180004a24  test    edx, edx
0x180004a26  mov     [rbp+hKey], 0
0x180004a2e  lea     rax, ValueName; "DigestPartialContextCacheTTL"
0x180004a35  mov     rdi, rcx
0x180004a38  lea     rsi, aDigestcontextc; "DigestContextCacheTTL"
0x180004a3f  mov     r9d, 20019h; samDesired
0x180004a45  cmovz   rsi, rax
0x180004a49  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180004a50  neg     edx
0x180004a52  lea     rax, [rbp+hKey]
0x180004a56  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\in"...
0x180004a5d  mov     [rsp+48h+phkResult], rax; phkResult
0x180004a62  sbb     ebx, ebx
0x180004a64  xor     r8d, r8d; ulOptions
0x180004a67  and     ebx, 10Eh
0x180004a6d  add     ebx, 1Eh
0x180004a70  call    cs:__imp_RegOpenKeyExW
0x180004a76  test    eax, eax
0x180004a78  jnz     short loc_180004AC4
0x180004a7a  mov     rcx, [rbp+hKey]; hKey
0x180004a7e  lea     r9, [rbp+Type]; lpType
0x180004a82  mov     [rbp+Data], eax
0x180004a85  xor     r8d, r8d; lpReserved
0x180004a88  mov     [rbp+Type], eax
0x180004a8b  mov     rdx, rsi; lpValueName
0x180004a8e  lea     rax, [rbp+cbData]
0x180004a92  mov     [rbp+cbData], 4
0x180004a99  mov     [rsp+48h+lpcbData], rax; lpcbData
0x180004a9e  lea     rax, [rbp+Data]
0x180004aa2  mov     [rsp+48h+phkResult], rax; lpData
0x180004aa7  call    cs:__imp_RegQueryValueExW
0x180004aad  test    eax, eax
0x180004aaf  jnz     short loc_180004ABA
0x180004ab1  cmp     [rbp+Type], 4
0x180004ab5  jnz     short loc_180004ABA
0x180004ab7  mov     ebx, [rbp+Data]
0x180004aba  mov     rcx, [rbp+hKey]; hKey
0x180004abe  call    cs:__imp_RegCloseKey
0x180004ac4  imul    eax, ebx, 3E8h
0x180004aca  lea     rcx, [rdi+58h]; phNewTimer
0x180004ace  mov     [rsp+48h+Flags], 10h; Flags
0x180004ad6  lea     r8, ?ScavengerCallback@DIGEST_CONTEXT_CACHE@@CAXPEAXE@Z; Callback
0x180004add  mov     r9, rdi; Parameter
0x180004ae0  xor     edx, edx; TimerQueue
0x180004ae2  mov     dword ptr [rsp+48h+lpcbData], eax; Period
0x180004ae6  mov     dword ptr [rsp+48h+phkResult], eax; DueTime
0x180004aea  call    cs:__imp_CreateTimerQueueTimer
0x180004af0  test    eax, eax
0x180004af2  jnz     short loc_180004B08
0x180004af4  call    cs:__imp_GetLastError
0x180004afa  test    eax, eax
0x180004afc  jle     short loc_180004B0A
0x180004afe  movzx   eax, ax
0x180004b01  or      eax, 80070000h
0x180004b06  jmp     short loc_180004B0A
0x180004b08  xor     eax, eax
0x180004b0a  add     rsp, 48h
0x180004b0e  pop     rdi
0x180004b0f  pop     rsi
0x180004b10  pop     rbx
0x180004b11  pop     rbp
0x180004b12  retn
```
