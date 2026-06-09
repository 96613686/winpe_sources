# RtdspTriggerRegKeyExists

- ea: `0x1800045f0`
- end: `0x180004671`
- name: `RtdspTriggerRegKeyExists`
- size: `129`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180003f78`

## callees

- `0x1800045f0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000465e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000465e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004628`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004628`

## pseudocode

```c
__int64 __fastcall RtdspTriggerRegKeyExists(LPCWSTR lpSubKey, _DWORD *a2)
{
  LSTATUS v3; // eax
  int v4; // ebx
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  *a2 = 0;
  hKey = 0;
  v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20019u, &hKey);
  v4 = v3;
  if ( v3 == 2 )
  {
    v4 = 0;
  }
  else if ( !v3 )
  {
    *a2 = 1;
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( v4 > 0 )
    return (unsigned __int16)v4 | 0x80070000;
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800045f0  mov     r11, rsp
0x1800045f3  mov     [r11+8], rbx
0x1800045f7  push    rdi
0x1800045f8  sub     rsp, 30h
0x1800045fc  mov     rdi, rdx
0x1800045ff  mov     dword ptr [rdx], 0
0x180004605  mov     rdx, rcx; lpSubKey
0x180004608  mov     qword ptr [r11+10h], 0
0x180004610  lea     rax, [r11+10h]
0x180004614  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000461b  mov     r9d, 20019h; samDesired
0x180004621  mov     [r11-18h], rax
0x180004625  xor     r8d, r8d; ulOptions
0x180004628  call    cs:__imp_RegOpenKeyExW
0x18000462e  mov     ebx, eax
0x180004630  cmp     eax, 2
0x180004633  jnz     short loc_180004652
0x180004635  xor     ebx, ebx
0x180004637  mov     rcx, [rsp+38h+hKey]; hKey
0x18000463c  test    rcx, rcx
0x18000463f  jnz     short loc_18000465E
0x180004641  test    ebx, ebx
0x180004643  jg      short loc_180004666
0x180004645  mov     eax, ebx
0x180004647  mov     rbx, [rsp+38h+arg_0]
0x18000464c  add     rsp, 30h
0x180004650  pop     rdi
0x180004651  retn
0x180004652  test    eax, eax
0x180004654  jnz     short loc_180004637
0x180004656  mov     dword ptr [rdi], 1
0x18000465c  jmp     short loc_180004637
0x18000465e  call    cs:__imp_RegCloseKey
0x180004664  jmp     short loc_180004641
0x180004666  movzx   ebx, bx
0x180004669  or      ebx, 80070000h
0x18000466f  jmp     short loc_180004645
```
