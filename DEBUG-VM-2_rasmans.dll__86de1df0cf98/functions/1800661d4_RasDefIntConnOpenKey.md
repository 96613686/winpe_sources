# RasDefIntConnOpenKey

- ea: `0x1800661d4`
- end: `0x1800663b8`
- name: `RasDefIntConnOpenKey`
- size: `484`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800663c0`

## callees

- `0x1800022a0`
- `0x180059974`
- `0x1800661d4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180066266`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180066266`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006638c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006639b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006638c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006639b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800662d2`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18006632b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180066377`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800662d2`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18006632b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180066377`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineA` at `0x18006622c`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineA` at `0x18006622c`

## pseudocode

```c
__int64 __fastcall RasDefIntConnOpenKey(__int64 a1, int a2, int a3, HKEY *a4)
{
  int v7; // eax
  __int64 v9; // rcx
  const char *CommandLineA; // rax
  unsigned int v11; // ebx
  int v12; // edi
  LSTATUS v13; // eax
  HKEY hKey; // [rsp+50h] [rbp-10h] BYREF
  HKEY v15; // [rsp+58h] [rbp-8h] BYREF
  DWORD dwDisposition; // [rsp+80h] [rbp+20h] BYREF

  dwDisposition = 0;
  hKey = 0;
  v15 = 0;
  v7 = IsConsumerPlatform();
  if ( a2 )
  {
    if ( !v7 )
      return 87;
    v9 = -2147483646;
    goto LABEL_11;
  }
  CommandLineA = GetCommandLineA();
  if ( !CommandLineA || !strstr_0(CommandLineA, "-k netsvcs") )
  {
    v9 = -2147483647;
LABEL_11:
    v12 = 0;
    hKey = (HKEY)v9;
    goto LABEL_12;
  }
  v11 = RegOpenKeyExW(HKEY_CURRENT_USER, 0, 0, 0xF003Fu, &hKey);
  if ( !v11 )
  {
    v9 = (__int64)hKey;
    v12 = 1;
LABEL_12:
    v13 = RegCreateKeyExW(
            (HKEY)v9,
            L"Software\\Microsoft\\RAS AutoDial",
            0,
            0,
            0,
            a3 != 0 ? 131101 : 131103,
            0,
            &v15,
            &dwDisposition);
    v11 = v13;
    if ( !v13
      || a3
      && v13 == 5
      && (v11 = RegCreateKeyExW(hKey, L"Software\\Microsoft\\RAS AutoDial", 0, 0, 0, 0x20019u, 0, &v15, &dwDisposition)) == 0 )
    {
      v11 = RegCreateKeyExW(v15, L"Default", 0, 0, 0, a3 != 0 ? 131097 : 131103, 0, a4, &dwDisposition);
    }
    goto LABEL_17;
  }
  v12 = 0;
LABEL_17:
  if ( hKey && v12 )
    RegCloseKey(hKey);
  if ( v15 )
    RegCloseKey(v15);
  return v11;
}

```

## disassembly

```asm
0x1800661d4  mov     [rsp-18h+arg_8], rbx
0x1800661d9  mov     [rsp-18h+arg_10], rsi
0x1800661de  mov     [rsp-18h+dwDisposition], ecx
0x1800661e2  push    rbp
0x1800661e3  push    rdi
0x1800661e4  push    r14
0x1800661e6  mov     rbp, rsp
0x1800661e9  sub     rsp, 60h
0x1800661ed  mov     r14, r9
0x1800661f0  mov     [rbp+dwDisposition], 0
0x1800661f7  mov     esi, r8d
0x1800661fa  mov     [rbp+hKey], 0
0x180066202  mov     ebx, edx
0x180066204  mov     [rbp+var_8], 0
0x18006620c  call    IsConsumerPlatform
0x180066211  test    ebx, ebx
0x180066213  jz      short loc_18006622C
0x180066215  test    eax, eax
0x180066217  jnz     short loc_180066223
0x180066219  mov     eax, 57h ; 'W'
0x18006621e  jmp     loc_1800663A3
0x180066223  mov     rcx, 0FFFFFFFF80000002h
0x18006622a  jmp     short loc_180066289
0x18006622c  call    cs:__imp_GetCommandLineA
0x180066232  test    rax, rax
0x180066235  jz      short loc_180066282
0x180066237  lea     rdx, aKNetsvcs; "-k netsvcs"
0x18006623e  mov     rcx, rax; Str
0x180066241  call    strstr_0
0x180066246  test    rax, rax
0x180066249  jz      short loc_180066282
0x18006624b  lea     rax, [rbp+hKey]
0x18006624f  mov     r9d, 0F003Fh; samDesired
0x180066255  xor     r8d, r8d; ulOptions
0x180066258  mov     [rsp+60h+phkResult], rax; phkResult
0x18006625d  xor     edx, edx; lpSubKey
0x18006625f  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180066266  call    cs:__imp_RegOpenKeyExW
0x18006626c  mov     ebx, eax
0x18006626e  test    eax, eax
0x180066270  jnz     short loc_18006627B
0x180066272  mov     rcx, [rbp+hKey]
0x180066276  lea     edi, [rax+1]
0x180066279  jmp     short loc_18006628F
0x18006627b  xor     edi, edi
0x18006627d  jmp     loc_18006637F
0x180066282  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180066289  xor     edi, edi
0x18006628b  mov     [rbp+hKey], rcx
0x18006628f  mov     eax, esi
0x180066291  neg     eax
0x180066293  lea     rax, [rbp+dwDisposition]
0x180066297  sbb     edx, edx
0x180066299  mov     [rsp+60h+lpdwDisposition], rax; lpdwDisposition
0x18006629e  and     edx, 0FFFFFFFEh
0x1800662a1  lea     rax, [rbp+var_8]
0x1800662a5  mov     [rsp+60h+var_28], rax; phkResult
0x1800662aa  add     edx, 2001Fh
0x1800662b0  mov     [rsp+60h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800662b9  xor     r9d, r9d; lpClass
0x1800662bc  mov     [rsp+60h+samDesired], edx; samDesired
0x1800662c0  xor     r8d, r8d; Reserved
0x1800662c3  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\RAS AutoDial"
0x1800662ca  mov     dword ptr [rsp+60h+phkResult], 0; dwOptions
0x1800662d2  call    cs:__imp_RegCreateKeyExW
0x1800662d8  mov     ebx, eax
0x1800662da  test    eax, eax
0x1800662dc  jz      short loc_180066337
0x1800662de  test    esi, esi
0x1800662e0  jz      loc_18006637F
0x1800662e6  cmp     eax, 5
0x1800662e9  jnz     loc_18006637F
0x1800662ef  mov     rcx, [rbp+hKey]; hKey
0x1800662f3  lea     rax, [rbp+dwDisposition]
0x1800662f7  mov     [rsp+60h+lpdwDisposition], rax; lpdwDisposition
0x1800662fc  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\RAS AutoDial"
0x180066303  lea     rax, [rbp+var_8]
0x180066307  xor     r9d, r9d; lpClass
0x18006630a  mov     [rsp+60h+var_28], rax; phkResult
0x18006630f  xor     r8d, r8d; Reserved
0x180066312  mov     [rsp+60h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18006631b  mov     [rsp+60h+samDesired], 20019h; samDesired
0x180066323  mov     dword ptr [rsp+60h+phkResult], 0; dwOptions
0x18006632b  call    cs:__imp_RegCreateKeyExW
0x180066331  mov     ebx, eax
0x180066333  test    eax, eax
0x180066335  jnz     short loc_18006637F
0x180066337  neg     esi
0x180066339  lea     rcx, [rbp+dwDisposition]
0x18006633d  mov     [rsp+60h+lpdwDisposition], rcx; lpdwDisposition
0x180066342  lea     rdx, aDefault; "Default"
0x180066349  mov     rcx, [rbp+var_8]; hKey
0x18006634d  sbb     eax, eax
0x18006634f  mov     [rsp+60h+var_28], r14; phkResult
0x180066354  and     eax, 0FFFFFFFAh
0x180066357  add     eax, 2001Fh
0x18006635c  mov     [rsp+60h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180066365  mov     [rsp+60h+samDesired], eax; samDesired
0x180066369  xor     r9d, r9d; lpClass
0x18006636c  xor     r8d, r8d; Reserved
0x18006636f  mov     dword ptr [rsp+60h+phkResult], 0; dwOptions
0x180066377  call    cs:__imp_RegCreateKeyExW
0x18006637d  mov     ebx, eax
0x18006637f  mov     rcx, [rbp+hKey]; hKey
0x180066383  test    rcx, rcx
0x180066386  jz      short loc_180066392
0x180066388  test    edi, edi
0x18006638a  jz      short loc_180066392
0x18006638c  call    cs:__imp_RegCloseKey
0x180066392  mov     rcx, [rbp+var_8]; hKey
0x180066396  test    rcx, rcx
0x180066399  jz      short loc_1800663A1
0x18006639b  call    cs:__imp_RegCloseKey
0x1800663a1  mov     eax, ebx
0x1800663a3  lea     r11, [rsp+60h+var_s0]
0x1800663a8  mov     rbx, [r11+28h]
0x1800663ac  mov     rsi, [r11+30h]
0x1800663b0  mov     rsp, r11
0x1800663b3  pop     r14
0x1800663b5  pop     rdi
0x1800663b6  pop     rbp
0x1800663b7  retn
```
