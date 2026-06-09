# GetProcessorName(ushort *,uint)

- ea: `0x180019f68`
- end: `0x18001a06e`
- name: `?GetProcessorName@@YAJPEAGI@Z`
- size: `262`
- prototype: `__int64 __fastcall(unsigned __int16 *pvData, DWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180019e64`

## callees

- `0x180019f68`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a05b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a05b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180019fa3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180019fa3`
- `api-ms-win-shcore-registry-l1-1-0!SHRegGetValueW` at `0x180019ff4`
- `api-ms-win-shcore-registry-l1-1-0!SHRegGetValueW` at `0x18001a041`
- `api-ms-win-shcore-registry-l1-1-0!SHRegGetValueW` at `0x180019ff4`
- `api-ms-win-shcore-registry-l1-1-0!SHRegGetValueW` at `0x18001a041`

## pseudocode

```c
__int64 __fastcall GetProcessorName(unsigned __int16 *pvData, DWORD a2)
{
  LSTATUS v3; // eax
  signed int v4; // ebx
  LSTATUS ValueW; // eax
  LSTATUS v6; // eax
  HKEY hkey; // [rsp+50h] [rbp+8h] BYREF
  DWORD pcbData; // [rsp+58h] [rbp+10h] BYREF

  pcbData = a2;
  *pvData = 0;
  hkey = 0;
  v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"HARDWARE\\DESCRIPTION\\System\\CentralProcessor\\0", 0, 0x20019u, &hkey);
  v4 = v3;
  if ( v3 > 0 )
    v4 = (unsigned __int16)v3 | 0x80070000;
  if ( v4 >= 0 )
  {
    pcbData = 2048;
    ValueW = SHRegGetValueW(hkey, 0, L"ProcessorNameString", 268435462, 0, pvData, &pcbData);
    v4 = ValueW;
    if ( ValueW > 0 )
      v4 = (unsigned __int16)ValueW | 0x80070000;
    if ( v4 < 0 )
    {
      pcbData = 2048;
      v6 = SHRegGetValueW(hkey, 0, L"Identifier", 268435462, 0, pvData, &pcbData);
      v4 = v6;
      if ( v6 > 0 )
        v4 = (unsigned __int16)v6 | 0x80070000;
    }
    RegCloseKey(hkey);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180019f68  mov     r11, rsp
0x180019f6b  mov     [r11+18h], rbx
0x180019f6f  mov     [rsp+arg_8], edx
0x180019f73  push    rdi
0x180019f74  sub     rsp, 40h
0x180019f78  xor     eax, eax
0x180019f7a  lea     rdx, SubKey; "HARDWARE\\DESCRIPTION\\System\\CentralP"...
0x180019f81  mov     [rcx], ax
0x180019f84  mov     rdi, rcx
0x180019f87  mov     [r11+8], rax
0x180019f8b  mov     r9d, 20019h; samDesired
0x180019f91  lea     rax, [r11+8]
0x180019f95  xor     r8d, r8d; ulOptions
0x180019f98  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180019f9f  mov     [r11-28h], rax
0x180019fa3  call    cs:__imp_RegOpenKeyExW
0x180019fa9  mov     ebx, eax
0x180019fab  test    eax, eax
0x180019fad  jle     short loc_180019FB8
0x180019faf  movzx   ebx, ax
0x180019fb2  or      ebx, 80070000h
0x180019fb8  test    ebx, ebx
0x180019fba  js      loc_18001A061
0x180019fc0  mov     rcx, [rsp+48h+hkey]; hkey
0x180019fc5  lea     rax, [rsp+48h+arg_8]
0x180019fca  mov     [rsp+48h+pcbData], rax; pcbData
0x180019fcf  lea     r8, pszValue; "ProcessorNameString"
0x180019fd6  mov     [rsp+48h+pvData], rdi; pvData
0x180019fdb  mov     r9d, 10000006h; srrfFlags
0x180019fe1  xor     edx, edx; pszSubKey
0x180019fe3  mov     [rsp+48h+pdwType], 0; pdwType
0x180019fec  mov     [rsp+48h+arg_8], 800h
0x180019ff4  call    cs:__imp_SHRegGetValueW
0x180019ffa  mov     ebx, eax
0x180019ffc  test    eax, eax
0x180019ffe  jle     short loc_18001A009
0x18001a000  movzx   ebx, ax
0x18001a003  or      ebx, 80070000h
0x18001a009  test    ebx, ebx
0x18001a00b  jns     short loc_18001A056
0x18001a00d  mov     rcx, [rsp+48h+hkey]; hkey
0x18001a012  lea     rax, [rsp+48h+arg_8]
0x18001a017  mov     [rsp+48h+pcbData], rax; pcbData
0x18001a01c  lea     r8, aIdentifier; "Identifier"
0x18001a023  mov     [rsp+48h+pvData], rdi; pvData
0x18001a028  mov     r9d, 10000006h; srrfFlags
0x18001a02e  xor     edx, edx; pszSubKey
0x18001a030  mov     [rsp+48h+pdwType], 0; pdwType
0x18001a039  mov     [rsp+48h+arg_8], 800h
0x18001a041  call    cs:__imp_SHRegGetValueW
0x18001a047  mov     ebx, eax
0x18001a049  test    eax, eax
0x18001a04b  jle     short loc_18001A056
0x18001a04d  movzx   ebx, ax
0x18001a050  or      ebx, 80070000h
0x18001a056  mov     rcx, [rsp+48h+hkey]; hKey
0x18001a05b  call    cs:__imp_RegCloseKey
0x18001a061  mov     eax, ebx
0x18001a063  mov     rbx, [rsp+48h+arg_10]
0x18001a068  add     rsp, 40h
0x18001a06c  pop     rdi
0x18001a06d  retn
```
