# OrchestrateSetCompletionStatusEx

- ea: `0x180048320`
- end: `0x180048428`
- name: `OrchestrateSetCompletionStatusEx`
- size: `264`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180048308`

## callees

- `0x180048320`
- `0x1800488e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800483e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048400`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800483e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048400`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800483d7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800483d7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180048398`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180048398`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800483c2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800483c2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800483cf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800483cf`

## string_xrefs

- `0x18004835b`: `System\Setup\Status\ChildCompletion`

## pseudocode

```c
signed int __fastcall OrchestrateSetCompletionStatusEx(__int64 a1, HKEY a2, __int64 a3, const WCHAR *a4, DWORD a5)
{
  LSTATUS v6; // ebx
  HKEY v7; // rdx
  HKEY v8; // rcx
  const unsigned __int16 *v9; // r8
  signed int result; // eax
  signed int LastError; // eax
  bool v12; // sf
  HKEY hKey; // [rsp+68h] [rbp+10h] BYREF
  __int64 Data; // [rsp+70h] [rbp+18h] BYREF

  Data = a3;
  hKey = a2;
  if ( !a4 || !*a4 )
    return -2147024809;
  LODWORD(Data) = 0;
  hKey = 0;
  a5 = 0;
  v6 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\Setup\\Status\\ChildCompletion",
         0,
         (LPWSTR)&Class,
         0,
         0x20006u,
         0,
         &hKey,
         &a5);
  if ( !v6 )
  {
    v6 = RegSetValueExW(hKey, a4, 0, 4u, (const BYTE *)&Data, 4u);
    RegCloseKey(hKey);
  }
  SetLastError(v6);
  if ( !v6 )
    return OrchestrateUpdateImageState(v8, v7, v9);
  LastError = GetLastError();
  v12 = LastError < 0;
  if ( LastError > 0 )
    v12 = 1;
  if ( !v12 )
    return -2147467259;
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180048320  mov     r11, rsp
0x180048323  mov     [r11+8], rbx
0x180048327  mov     [r11+18h], r8
0x18004832b  mov     [r11+10h], rdx
0x18004832f  push    rdi
0x180048330  sub     rsp, 50h
0x180048334  mov     rdi, r9
0x180048337  test    r9, r9
0x18004833a  jz      loc_180048418
0x180048340  xor     eax, eax
0x180048342  cmp     ax, [r9]
0x180048346  jz      loc_180048418
0x18004834c  mov     dword ptr [rsp+58h+Data], eax
0x180048350  lea     r9, Class; lpClass
0x180048357  mov     [r11+10h], rax
0x18004835b  lea     rdx, aSystemSetupSta_1; "System\\Setup\\Status\\ChildCompletion"
0x180048362  mov     [r11+28h], eax
0x180048366  xor     r8d, r8d; Reserved
0x180048369  lea     rax, [r11+28h]
0x18004836d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180048374  mov     [r11-18h], rax
0x180048378  lea     rax, [r11+10h]
0x18004837c  mov     [r11-20h], rax
0x180048380  mov     qword ptr [r11-28h], 0
0x180048388  mov     [rsp+58h+samDesired], 20006h; samDesired
0x180048390  mov     [rsp+58h+dwOptions], 0; dwOptions
0x180048398  call    cs:__imp_RegCreateKeyExW
0x18004839e  mov     ebx, eax
0x1800483a0  test    eax, eax
0x1800483a2  jnz     short loc_1800483D5
0x1800483a4  mov     rcx, [rsp+58h+hKey]; hKey
0x1800483a9  lea     r9d, [rax+4]; dwType
0x1800483ad  lea     rax, [rsp+58h+Data]
0x1800483b2  mov     [rsp+58h+samDesired], r9d; cbData
0x1800483b7  xor     r8d, r8d; Reserved
0x1800483ba  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x1800483bf  mov     rdx, rdi; lpValueName
0x1800483c2  call    cs:__imp_RegSetValueExW
0x1800483c8  mov     rcx, [rsp+58h+hKey]; hKey
0x1800483cd  mov     ebx, eax
0x1800483cf  call    cs:__imp_RegCloseKey
0x1800483d5  mov     ecx, ebx; dwErrCode
0x1800483d7  call    cs:__imp_SetLastError
0x1800483dd  test    ebx, ebx
0x1800483df  jnz     short loc_1800483E8
0x1800483e1  call    ?OrchestrateUpdateImageState@@YAJPEAUHKEY__@@0PEBG@Z; OrchestrateUpdateImageState(HKEY__ *,HKEY__ *,ushort const *)
0x1800483e6  jmp     short loc_18004841D
0x1800483e8  call    cs:__imp_GetLastError
0x1800483ee  mov     ebx, 80070000h
0x1800483f3  test    eax, eax
0x1800483f5  jle     short loc_1800483FE
0x1800483f7  movzx   eax, ax
0x1800483fa  or      eax, ebx
0x1800483fc  test    eax, eax
0x1800483fe  jns     short loc_180048411
0x180048400  call    cs:__imp_GetLastError
0x180048406  test    eax, eax
0x180048408  jle     short loc_18004841D
0x18004840a  movzx   eax, ax
0x18004840d  or      eax, ebx
0x18004840f  jmp     short loc_18004841D
0x180048411  mov     eax, 80004005h
0x180048416  jmp     short loc_18004841D
0x180048418  mov     eax, 80070057h
0x18004841d  mov     rbx, [rsp+58h+arg_0]
0x180048422  add     rsp, 50h
0x180048426  pop     rdi
0x180048427  retn
```
