# UpdateMiniportsEnabledRegistry

- ea: `0x1800081c0`
- end: `0x180008274`
- name: `UpdateMiniportsEnabledRegistry`
- size: `180`
- prototype: `__int64 __fastcall(int, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180006214`

## callees

- `0x18000692c`
- `0x1800081c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000824f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000824f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000825c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000825c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008221`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008221`

## string_xrefs

- `0x180008213`: `SYSTEM\CurrentControlSet\Services\RasMan\Parameters`
- `0x180008248`: `MiniportsInstalled`

## pseudocode

```c
__int64 __fastcall UpdateMiniportsEnabledRegistry(int a1, int a2)
{
  int MiniportsEnabledRegistry; // eax
  int v5; // ebx
  unsigned int v6; // edi
  int Data; // [rsp+48h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF

  hKey = 0;
  Data = 0;
  MiniportsEnabledRegistry = GetMiniportsEnabledRegistry();
  if ( a2 == 8 )
  {
    v5 = MiniportsEnabledRegistry & ~a1;
  }
  else
  {
    v6 = 0;
    if ( a2 != 1 )
      goto LABEL_7;
    v5 = MiniportsEnabledRegistry | a1;
  }
  Data = v5;
  v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Services\\RasMan\\Parameters", 0, 0x20006u, &hKey);
  if ( !v6 )
    v6 = RegSetValueExW(hKey, L"MiniportsInstalled", 0, 4u, (const BYTE *)&Data, 4u);
LABEL_7:
  RegCloseKey(hKey);
  return v6;
}

```

## disassembly

```asm
0x1800081c0  mov     rax, rsp
0x1800081c3  mov     [rax+8], rbx
0x1800081c7  mov     [rax+20h], rsi
0x1800081cb  push    rdi
0x1800081cc  sub     rsp, 30h
0x1800081d0  mov     esi, edx
0x1800081d2  mov     qword ptr [rax+18h], 0
0x1800081da  mov     ebx, ecx
0x1800081dc  mov     dword ptr [rax+10h], 0
0x1800081e3  call    GetMiniportsEnabledRegistry
0x1800081e8  cmp     esi, 8
0x1800081eb  jnz     short loc_1800081F3
0x1800081ed  not     ebx
0x1800081ef  and     ebx, eax
0x1800081f1  jmp     short loc_1800081FC
0x1800081f3  xor     edi, edi
0x1800081f5  cmp     esi, 1
0x1800081f8  jnz     short loc_180008257
0x1800081fa  or      ebx, eax
0x1800081fc  lea     rax, [rsp+38h+hKey]
0x180008201  mov     [rsp+38h+Data], ebx
0x180008205  mov     r9d, 20006h; samDesired
0x18000820b  mov     [rsp+38h+phkResult], rax; phkResult
0x180008210  xor     r8d, r8d; ulOptions
0x180008213  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\Ra"...
0x18000821a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180008221  call    cs:__imp_RegOpenKeyExW
0x180008227  mov     edi, eax
0x180008229  test    eax, eax
0x18000822b  jnz     short loc_180008257
0x18000822d  mov     rcx, [rsp+38h+hKey]; hKey
0x180008232  lea     r9d, [rax+4]; dwType
0x180008236  lea     rax, [rsp+38h+Data]
0x18000823b  mov     [rsp+38h+cbData], r9d; cbData
0x180008240  xor     r8d, r8d; Reserved
0x180008243  mov     [rsp+38h+phkResult], rax; lpData
0x180008248  lea     rdx, ValueName; "MiniportsInstalled"
0x18000824f  call    cs:__imp_RegSetValueExW
0x180008255  mov     edi, eax
0x180008257  mov     rcx, [rsp+38h+hKey]; hKey
0x18000825c  call    cs:__imp_RegCloseKey
0x180008262  mov     rbx, [rsp+38h+arg_0]
0x180008267  mov     eax, edi
0x180008269  mov     rsi, [rsp+38h+arg_18]
0x18000826e  add     rsp, 30h
0x180008272  pop     rdi
0x180008273  retn
```
