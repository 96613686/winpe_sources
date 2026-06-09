# SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)

- ea: `0x1800170d0`
- end: `0x180017198`
- name: `?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z`
- size: `200`
- prototype: `__int64 __fastcall(HKEY hKey, const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `5`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180016e10`
- `0x180016f34`
- `0x18002639c`
- `0x180035608`
- `0x180060310`

## callees

- `0x1800170d0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001712e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001712e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001711c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001711c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180017182`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180017182`

## pseudocode

```c
__int64 __fastcall SHRegSetDWORD(HKEY hKey, const unsigned __int16 *a2, const unsigned __int16 *a3, int a4)
{
  HKEY v4; // rdi
  LSTATUS v6; // ebx
  HKEY hKeya; // [rsp+68h] [rbp+10h] BYREF
  int Data; // [rsp+78h] [rbp+20h] BYREF

  Data = a4;
  v4 = hKey;
  hKeya = 0;
  if ( a2 && *a2 )
  {
    v6 = RegCreateKeyExW(hKey, a2, 0, 0, 0, 2u, 0, &hKeya, 0);
    if ( v6 )
      goto LABEL_5;
    hKey = hKeya;
  }
  else
  {
    hKeya = hKey;
  }
  v6 = RegSetValueExW(hKey, a3, 0, 4u, (const BYTE *)&Data, 4u);
  if ( hKeya != v4 )
    RegCloseKey(hKeya);
LABEL_5:
  if ( v6 > 0 )
    return (unsigned __int16)v6 | 0x80070000;
  else
    return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800170d0  mov     [rsp+arg_0], rbx
0x1800170d5  mov     [rsp+arg_10], rsi
0x1800170da  mov     [rsp+Data], r9d
0x1800170df  push    rdi
0x1800170e0  sub     rsp, 50h
0x1800170e4  mov     rdi, rcx
0x1800170e7  mov     rsi, r8
0x1800170ea  xor     ecx, ecx
0x1800170ec  mov     [rsp+58h+hKey], rcx
0x1800170f1  test    rdx, rdx
0x1800170f4  jnz     short loc_180017154
0x1800170f6  mov     rcx, rdi; hKey
0x1800170f9  mov     [rsp+58h+hKey], rcx
0x1800170fe  lea     rax, [rsp+58h+Data]
0x180017103  mov     [rsp+58h+cbData], 4; cbData
0x18001710b  mov     r9d, 4; dwType
0x180017111  mov     [rsp+58h+lpData], rax; lpData
0x180017116  xor     r8d, r8d; Reserved
0x180017119  mov     rdx, rsi; lpValueName
0x18001711c  call    cs:__imp_RegSetValueExW
0x180017122  mov     rcx, [rsp+58h+hKey]; hKey
0x180017127  mov     ebx, eax
0x180017129  cmp     rcx, rdi
0x18001712c  jz      short loc_180017134
0x18001712e  call    cs:__imp_RegCloseKey
0x180017134  test    ebx, ebx
0x180017136  jg      short loc_18001714A
0x180017138  mov     eax, ebx
0x18001713a  mov     rbx, [rsp+58h+arg_0]
0x18001713f  mov     rsi, [rsp+58h+arg_10]
0x180017144  add     rsp, 50h
0x180017148  pop     rdi
0x180017149  retn
0x18001714a  movzx   eax, bx
0x18001714d  or      eax, 80070000h
0x180017152  jmp     short loc_18001713A
0x180017154  cmp     [rdx], cx
0x180017157  jz      short loc_1800170F6
0x180017159  mov     [rsp+58h+lpdwDisposition], rcx; lpdwDisposition
0x18001715e  lea     rax, [rsp+58h+hKey]
0x180017163  mov     [rsp+58h+phkResult], rax; phkResult
0x180017168  xor     r9d, r9d; lpClass
0x18001716b  mov     [rsp+58h+lpSecurityAttributes], rcx; lpSecurityAttributes
0x180017170  xor     r8d, r8d; Reserved
0x180017173  mov     [rsp+58h+cbData], 2; samDesired
0x18001717b  mov     dword ptr [rsp+58h+lpData], ecx; dwOptions
0x18001717f  mov     rcx, rdi; hKey
0x180017182  call    cs:__imp_RegCreateKeyExW
0x180017188  mov     ebx, eax
0x18001718a  test    eax, eax
0x18001718c  jnz     short loc_180017134
0x18001718e  mov     rcx, [rsp+58h+hKey]
0x180017193  jmp     loc_1800170FE
```
