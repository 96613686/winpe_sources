# GetNextNewCalendarColor

- ea: `0x180007b00`
- end: `0x180007c88`
- name: `GetNextNewCalendarColor`
- size: `392`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180007b00`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007b19`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007b19`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007c73`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007c73`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180007b63`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180007b63`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007c5e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007c5e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180007c40`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180007c40`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180007c11`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180007c11`

## pseudocode

```c
__int64 __fastcall GetNextNewCalendarColor(_DWORD *a1)
{
  LSTATUS ValueW; // eax
  signed int v3; // ebx
  DWORD v4; // r8d
  int v5; // esi
  LSTATUS v6; // eax
  bool v7; // cc
  DWORD pvData; // [rsp+78h] [rbp+28h] BYREF
  DWORD pcbData; // [rsp+80h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+88h] [rbp+38h] BYREF

  EnterCriticalSection(&g_calendarColorLock);
  pvData = 0;
  pcbData = 4;
  ValueW = RegGetValueW(
             HKEY_CURRENT_USER,
             L"Software\\Microsoft\\POOM",
             L"calendarColorIndex",
             0x20000018u,
             0,
             &pvData,
             &pcbData);
  v3 = ValueW;
  if ( ValueW > 0 )
    v3 = (unsigned __int16)ValueW | 0x80070000;
  if ( v3 == -2147024894 )
  {
    v4 = 0;
  }
  else
  {
    if ( v3 < 0 )
      goto LABEL_15;
    v4 = pvData;
  }
  hKey = 0;
  v5 = *((_DWORD *)&xmmword_18000D378 + v4 % 9);
  pvData = (v4 + 1) % 9;
  pcbData = pvData;
  v6 = RegCreateKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\POOM", 0, 0, 0, 0x20006u, 0, &hKey, 0);
  v3 = v6;
  v7 = v6 <= 0;
  if ( !v6 )
  {
    v6 = RegSetValueExW(hKey, L"calendarColorIndex", 0, 4u, (const BYTE *)&pcbData, 4u);
    v3 = v6;
    v7 = v6 <= 0;
  }
  if ( !v7 )
    v3 = (unsigned __int16)v6 | 0x80070000;
  if ( hKey )
    RegCloseKey(hKey);
  if ( v3 >= 0 )
  {
    *a1 = v5;
    v3 = 0;
  }
LABEL_15:
  LeaveCriticalSection(&g_calendarColorLock);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180007b00  mov     [rsp-18h+arg_0], rbx
0x180007b05  push    rbp
0x180007b06  push    rsi
0x180007b07  push    rdi
0x180007b08  mov     rbp, rsp
0x180007b0b  sub     rsp, 50h
0x180007b0f  mov     rdi, rcx
0x180007b12  lea     rcx, ?g_calendarColorLock@@3Vrecursive_mutex@utl@@A; lpCriticalSection
0x180007b19  call    cs:__imp_EnterCriticalSection
0x180007b1f  lea     rax, [rbp+arg_10]
0x180007b23  mov     [rbp+arg_8], 0
0x180007b2a  mov     [rsp+50h+pcbData], rax; pcbData
0x180007b2f  lea     r8, ?c_calendarColorIndexValueName@@3QBGB; "calendarColorIndex"
0x180007b36  lea     rax, [rbp+arg_8]
0x180007b3a  mov     [rbp+arg_10], 4
0x180007b41  mov     [rsp+50h+pvData], rax; pvData
0x180007b46  lea     rdx, ?c_poomRegistryKey@@3QBGB; "Software\\Microsoft\\POOM"
0x180007b4d  mov     r9d, 20000018h; dwFlags
0x180007b53  mov     [rsp+50h+pdwType], 0; pdwType
0x180007b5c  mov     rcx, 0FFFFFFFF80000001h; hkey
0x180007b63  call    cs:__imp_RegGetValueW
0x180007b69  mov     ebx, eax
0x180007b6b  test    eax, eax
0x180007b6d  jle     short loc_180007B78
0x180007b6f  movzx   ebx, ax
0x180007b72  or      ebx, 80070000h
0x180007b78  cmp     ebx, 80070002h
0x180007b7e  jnz     short loc_180007B85
0x180007b80  xor     r8d, r8d
0x180007b83  jmp     short loc_180007B91
0x180007b85  test    ebx, ebx
0x180007b87  js      loc_180007C6C
0x180007b8d  mov     r8d, [rbp+arg_8]
0x180007b91  mov     r9d, 38E38E39h
0x180007b97  mov     [rsp+50h+lpdwDisposition], 0; lpdwDisposition
0x180007ba0  mov     eax, r9d
0x180007ba3  mov     [rbp+hKey], 0
0x180007bab  mul     r8d
0x180007bae  mov     eax, r9d
0x180007bb1  lea     rsi, xmmword_18000D378
0x180007bb8  shr     edx, 1
0x180007bba  xor     r9d, r9d; lpClass
0x180007bbd  lea     ecx, [rdx+rdx*8]
0x180007bc0  mov     edx, r8d
0x180007bc3  sub     edx, ecx
0x180007bc5  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180007bcc  inc     r8d
0x180007bcf  mov     esi, [rsi+rdx*4]
0x180007bd2  mul     r8d
0x180007bd5  shr     edx, 1
0x180007bd7  lea     eax, [rdx+rdx*8]
0x180007bda  sub     r8d, eax
0x180007bdd  lea     rdx, ?c_poomRegistryKey@@3QBGB; "Software\\Microsoft\\POOM"
0x180007be4  lea     rax, [rbp+hKey]
0x180007be8  mov     [rbp+arg_8], r8d
0x180007bec  mov     [rsp+50h+phkResult], rax; phkResult
0x180007bf1  mov     [rsp+50h+pcbData], 0; lpSecurityAttributes
0x180007bfa  mov     [rbp+arg_10], r8d
0x180007bfe  xor     r8d, r8d; Reserved
0x180007c01  mov     dword ptr [rsp+50h+pvData], 20006h; samDesired
0x180007c09  mov     dword ptr [rsp+50h+pdwType], 0; dwOptions
0x180007c11  call    cs:__imp_RegCreateKeyExW
0x180007c17  mov     ebx, eax
0x180007c19  test    eax, eax
0x180007c1b  jnz     short loc_180007C4A
0x180007c1d  mov     rcx, [rbp+hKey]; hKey
0x180007c21  lea     rax, [rbp+arg_10]
0x180007c25  mov     dword ptr [rsp+50h+pvData], 4; cbData
0x180007c2d  lea     r9d, [rbx+4]; dwType
0x180007c31  xor     r8d, r8d; Reserved
0x180007c34  mov     [rsp+50h+pdwType], rax; lpData
0x180007c39  lea     rdx, ?c_calendarColorIndexValueName@@3QBGB; "calendarColorIndex"
0x180007c40  call    cs:__imp_RegSetValueExW
0x180007c46  mov     ebx, eax
0x180007c48  test    eax, eax
0x180007c4a  jle     short loc_180007C55
0x180007c4c  movzx   ebx, ax
0x180007c4f  or      ebx, 80070000h
0x180007c55  mov     rcx, [rbp+hKey]; hKey
0x180007c59  test    rcx, rcx
0x180007c5c  jz      short loc_180007C64
0x180007c5e  call    cs:__imp_RegCloseKey
0x180007c64  test    ebx, ebx
0x180007c66  js      short loc_180007C6C
0x180007c68  mov     [rdi], esi
0x180007c6a  xor     ebx, ebx
0x180007c6c  lea     rcx, ?g_calendarColorLock@@3Vrecursive_mutex@utl@@A; lpCriticalSection
0x180007c73  call    cs:__imp_LeaveCriticalSection
0x180007c79  mov     eax, ebx
0x180007c7b  mov     rbx, [rsp+50h+arg_0]
0x180007c80  add     rsp, 50h
0x180007c84  pop     rdi
0x180007c85  pop     rsi
0x180007c86  pop     rbp
0x180007c87  retn
```
