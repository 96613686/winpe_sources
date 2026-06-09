# LoadCursorSchemeNames(void)

- ea: `0x18001e7b0`
- end: `0x18001e97b`
- name: `?LoadCursorSchemeNames@@YAXXZ`
- size: `459`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18001e22c`
- `0x18001e670`

## callees

- `0x18001a67c`
- `0x18001e7b0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e96e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e96e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001e955`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001e955`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001e8ae`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001e8ae`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001e918`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001e918`

## pseudocode

```c
void LoadCursorSchemeNames(void)
{
  unsigned int v0; // r11d
  unsigned int v1; // r11d
  unsigned int v2; // r11d
  unsigned int v3; // r11d
  unsigned int v4; // r11d
  unsigned int v5; // r11d
  unsigned int v6; // r11d
  unsigned int i; // ebx
  const WCHAR *v8; // r8
  DWORD pcbData; // [rsp+60h] [rbp+8h] BYREF
  DWORD pdwType; // [rsp+68h] [rbp+10h] BYREF
  DWORD cbData; // [rsp+70h] [rbp+18h] BYREF
  HKEY hkey; // [rsp+78h] [rbp+20h] BYREF

  if ( !dword_1800442C8 )
  {
    dword_1800442C8 = 1;
    StringCchCopyW(&g_szSchemeNames, 0x64u, L"Windows Standard (large)");
    StringCchCopyW(&qword_1800415D8, v0, L"Windows Standard (extra large)");
    StringCchCopyW(&qword_1800416A0, v1, L"Windows Black");
    StringCchCopyW(&qword_180041768, v2, L"Windows Black (large)");
    StringCchCopyW(&qword_180041830, v3, L"Windows Black (extra large)");
    StringCchCopyW(&qword_1800418F8, v4, L"Windows Inverted");
    StringCchCopyW(&qword_1800419C0, v5, L"Windows Inverted (large)");
    StringCchCopyW(&qword_180041A88, v6, L"Windows Inverted (extra large)");
    hkey = 0;
    if ( !RegOpenKeyExW(HKEY_CURRENT_USER, L"Control Panel\\Cursors", 0, 0x20019u, &hkey) )
    {
      for ( i = 0; i < 0x12; ++i )
      {
        pcbData = 520;
        v8 = off_180030150[i];
        pdwType = 0;
        LOWORD((&g_szOrigCursors)[65 * (int)i]) = 0;
        RegGetValueW(hkey, 0, v8, 0x20000002u, &pdwType, &(&g_szOrigCursors)[65 * (int)i], &pcbData);
      }
      cbData = 4;
      if ( RegQueryValueExW(hkey, L"Scheme Source", 0, 0, &g_dwOrigSchemeSource, &cbData) )
        *(_DWORD *)&g_dwOrigSchemeSource = 1;
      RegCloseKey(hkey);
    }
  }
}

```

## disassembly

```asm
0x18001e7b0  push    rbx
0x18001e7b2  push    rsi
0x18001e7b3  sub     rsp, 48h
0x18001e7b7  cmp     cs:dword_1800442C8, 0
0x18001e7be  jnz     loc_18001E974
0x18001e7c4  mov     r11d, 64h ; 'd'
0x18001e7ca  mov     cs:dword_1800442C8, 1
0x18001e7d4  mov     edx, r11d; unsigned __int64
0x18001e7d7  lea     r8, aWindowsStandar_0; "Windows Standard (large)"
0x18001e7de  lea     rcx, ?g_szSchemeNames@@3PAY0GE@GA; unsigned __int16 *
0x18001e7e5  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001e7ea  lea     r8, aWindowsStandar; "Windows Standard (extra large)"
0x18001e7f1  mov     edx, r11d; unsigned __int64
0x18001e7f4  lea     rcx, qword_1800415D8; unsigned __int16 *
0x18001e7fb  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001e800  lea     r8, aWindowsBlack; "Windows Black"
0x18001e807  mov     edx, r11d; unsigned __int64
0x18001e80a  lea     rcx, qword_1800416A0; unsigned __int16 *
0x18001e811  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001e816  lea     r8, aWindowsBlackLa; "Windows Black (large)"
0x18001e81d  mov     edx, r11d; unsigned __int64
0x18001e820  lea     rcx, qword_180041768; unsigned __int16 *
0x18001e827  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001e82c  lea     r8, aWindowsBlackEx; "Windows Black (extra large)"
0x18001e833  mov     edx, r11d; unsigned __int64
0x18001e836  lea     rcx, qword_180041830; unsigned __int16 *
0x18001e83d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001e842  lea     r8, aWindowsInverte_1; "Windows Inverted"
0x18001e849  mov     edx, r11d; unsigned __int64
0x18001e84c  lea     rcx, qword_1800418F8; unsigned __int16 *
0x18001e853  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001e858  lea     r8, aWindowsInverte_0; "Windows Inverted (large)"
0x18001e85f  mov     edx, r11d; unsigned __int64
0x18001e862  lea     rcx, qword_1800419C0; unsigned __int16 *
0x18001e869  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001e86e  lea     r8, aWindowsInverte; "Windows Inverted (extra large)"
0x18001e875  mov     edx, r11d; unsigned __int64
0x18001e878  lea     rcx, qword_180041A88; unsigned __int16 *
0x18001e87f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001e884  lea     rax, [rsp+58h+hkey]
0x18001e889  mov     [rsp+58h+hkey], 0
0x18001e892  mov     r9d, 20019h; samDesired
0x18001e898  mov     [rsp+58h+phkResult], rax; phkResult
0x18001e89d  xor     r8d, r8d; ulOptions
0x18001e8a0  lea     rdx, SubKey; "Control Panel\\Cursors"
0x18001e8a7  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18001e8ae  call    cs:__imp_RegOpenKeyExW
0x18001e8b4  test    eax, eax
0x18001e8b6  jnz     loc_18001E974
0x18001e8bc  xor     ebx, ebx
0x18001e8be  lea     rsi, __ImageBase
0x18001e8c5  movsxd  r8, ebx
0x18001e8c8  lea     rcx, rva ?g_szOrigCursors@@3PAY0BAE@GA[rsi]; ushort (near * g_szOrigCursors)[260] ...
0x18001e8cf  imul    rax, r8, 208h
0x18001e8d6  mov     r9d, 20000002h; dwFlags
0x18001e8dc  mov     [rsp+58h+arg_0], 208h
0x18001e8e4  mov     r8, ds:rva off_180030150[rsi+r8*8]; lpValue
0x18001e8ec  add     rcx, rax
0x18001e8ef  xor     eax, eax
0x18001e8f1  xor     edx, edx; lpSubKey
0x18001e8f3  mov     [rsp+58h+pdwType], eax
0x18001e8f7  mov     [rcx], ax
0x18001e8fa  lea     rax, [rsp+58h+arg_0]
0x18001e8ff  mov     [rsp+58h+pcbData], rax; pcbData
0x18001e904  lea     rax, [rsp+58h+pdwType]
0x18001e909  mov     [rsp+58h+pvData], rcx; pvData
0x18001e90e  mov     rcx, [rsp+58h+hkey]; hkey
0x18001e913  mov     [rsp+58h+phkResult], rax; pdwType
0x18001e918  call    cs:__imp_RegGetValueW
0x18001e91e  inc     ebx
0x18001e920  cmp     ebx, 12h
0x18001e923  jb      short loc_18001E8C5
0x18001e925  mov     rcx, [rsp+58h+hkey]; hKey
0x18001e92a  lea     rax, [rsp+58h+cbData]
0x18001e92f  mov     [rsp+58h+pvData], rax; lpcbData
0x18001e934  lea     rdx, ValueName; "Scheme Source"
0x18001e93b  lea     rax, ?g_dwOrigSchemeSource@@3KA; ulong g_dwOrigSchemeSource
0x18001e942  mov     [rsp+58h+cbData], 4
0x18001e94a  xor     r9d, r9d; lpType
0x18001e94d  mov     [rsp+58h+phkResult], rax; lpData
0x18001e952  xor     r8d, r8d; lpReserved
0x18001e955  call    cs:__imp_RegQueryValueExW
0x18001e95b  test    eax, eax
0x18001e95d  jz      short loc_18001E969
0x18001e95f  mov     cs:?g_dwOrigSchemeSource@@3KA, 1; ulong g_dwOrigSchemeSource
0x18001e969  mov     rcx, [rsp+58h+hkey]; hKey
0x18001e96e  call    cs:__imp_RegCloseKey
0x18001e974  add     rsp, 48h
0x18001e978  pop     rsi
0x18001e979  pop     rbx
0x18001e97a  retn
```
