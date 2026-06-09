# ZtRegWriteSingleRule

- ea: `0x180008360`
- end: `0x1800084a7`
- name: `ZtRegWriteSingleRule`
- size: `327`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180008a60`

## callees

- `0x180008190`
- `0x180008360`
- `0x18000f78c`
- `0x180015008`
- `0x180015478`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000848f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000848f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180008448`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180008448`
- `KERNELBASE!RegCreateKeyExInternalW` at `0x1800083fd`
- `KERNELBASE!RegCreateKeyExInternalW` at `0x1800083fd`

## pseudocode

```c
__int64 __fastcall ZtRegWriteSingleRule(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v6; // ebx
  HKEY hKey; // [rsp+60h] [rbp+8h] BYREF

  hKey = 0;
  if ( (xmmword_18001F260 & 4) != 0 )
    WPP_SF_qqq(1026, 0x28u, (ULONGLONG)WPP_5daa81f1f60e30d3715838f17166c4a8_Traceguids, a1, a2, a3);
  if ( a1 && a2 )
  {
    v6 = RegCreateKeyExInternalW(a2, *(_QWORD *)(a1 + 16), 0, 0, 0, 131078, 0, &hKey, 0, a3);
    if ( !v6 )
    {
      v6 = SetRegistryString(hKey, L"Description", *(BYTE **)(a1 + 24));
      if ( !v6 )
      {
        v6 = RegSetValueExW(hKey, L"Flags", 0, 0xBu, (const BYTE *)(a1 + 8), 8u);
        if ( !v6 )
          v6 = ZtRegWriteRuleSubnets(hKey, a1);
      }
    }
  }
  else
  {
    v6 = 87;
  }
  if ( (xmmword_18001F260 & 4) != 0 )
    WPP_SF_d(1026, 0x29u, (ULONGLONG)WPP_5daa81f1f60e30d3715838f17166c4a8_Traceguids, v6);
  if ( hKey )
    RegCloseKey(hKey);
  return v6;
}

```

## disassembly

```asm
0x180008360  mov     rax, rsp
0x180008363  mov     [rax+10h], rbx
0x180008367  mov     [rax+18h], rsi
0x18000836b  push    rdi
0x18000836c  sub     rsp, 50h
0x180008370  mov     rsi, r8
0x180008373  mov     qword ptr [rax+8], 0
0x18000837b  mov     rbx, rdx
0x18000837e  mov     rdi, rcx
0x180008381  test    byte ptr cs:xmmword_18001F260, 4
0x180008388  jz      short loc_1800083AB
0x18000838a  mov     [rax-30h], r8
0x18000838e  mov     edx, 28h ; '('
0x180008393  lea     r8, WPP_5daa81f1f60e30d3715838f17166c4a8_Traceguids
0x18000839a  mov     [rax-38h], rbx
0x18000839e  mov     ecx, 402h
0x1800083a3  mov     r9, rdi
0x1800083a6  call    WPP_SF_qqq
0x1800083ab  test    rdi, rdi
0x1800083ae  jnz     short loc_1800083BA
0x1800083b0  mov     ebx, 57h ; 'W'
0x1800083b5  jmp     loc_180008463
0x1800083ba  test    rbx, rbx
0x1800083bd  jz      short loc_1800083B0
0x1800083bf  mov     rdx, [rdi+10h]
0x1800083c3  lea     rax, [rsp+58h+hKey]
0x1800083c8  mov     [rsp+58h+var_10], rsi
0x1800083cd  xor     r9d, r9d
0x1800083d0  mov     [rsp+58h+var_18], 0
0x1800083d9  xor     r8d, r8d
0x1800083dc  mov     [rsp+58h+var_20], rax
0x1800083e1  mov     rcx, rbx
0x1800083e4  mov     [rsp+58h+var_28], 0
0x1800083ed  mov     [rsp+58h+cbData], 20006h
0x1800083f5  mov     dword ptr [rsp+58h+lpData], 0
0x1800083fd  call    cs:__imp_RegCreateKeyExInternalW
0x180008403  mov     ebx, eax
0x180008405  test    eax, eax
0x180008407  jnz     short loc_180008463
0x180008409  mov     r8, [rdi+18h]; lpData
0x18000840d  lea     rdx, aDescription; "Description"
0x180008414  mov     rcx, [rsp+58h+hKey]; hKey
0x180008419  call    SetRegistryString
0x18000841e  mov     ebx, eax
0x180008420  test    eax, eax
0x180008422  jnz     short loc_180008463
0x180008424  mov     rcx, [rsp+58h+hKey]; hKey
0x180008429  lea     rax, [rdi+8]
0x18000842d  mov     [rsp+58h+cbData], 8; cbData
0x180008435  lea     r9d, [rbx+0Bh]; dwType
0x180008439  xor     r8d, r8d; Reserved
0x18000843c  mov     [rsp+58h+lpData], rax; lpData
0x180008441  lea     rdx, aFlags; "Flags"
0x180008448  call    cs:__imp_RegSetValueExW
0x18000844e  mov     ebx, eax
0x180008450  test    eax, eax
0x180008452  jnz     short loc_180008463
0x180008454  mov     rcx, [rsp+58h+hKey]; hKey
0x180008459  mov     rdx, rdi
0x18000845c  call    ZtRegWriteRuleSubnets
0x180008461  mov     ebx, eax
0x180008463  test    byte ptr cs:xmmword_18001F260, 4
0x18000846a  jz      short loc_180008485
0x18000846c  mov     edx, 29h ; ')'
0x180008471  lea     r8, WPP_5daa81f1f60e30d3715838f17166c4a8_Traceguids
0x180008478  mov     ecx, 402h
0x18000847d  mov     r9d, ebx
0x180008480  call    WPP_SF_d
0x180008485  mov     rcx, [rsp+58h+hKey]; hKey
0x18000848a  test    rcx, rcx
0x18000848d  jz      short loc_180008495
0x18000848f  call    cs:__imp_RegCloseKey
0x180008495  mov     rsi, [rsp+58h+arg_10]
0x18000849a  mov     eax, ebx
0x18000849c  mov     rbx, [rsp+58h+arg_8]
0x1800084a1  add     rsp, 50h
0x1800084a5  pop     rdi
0x1800084a6  retn
```
