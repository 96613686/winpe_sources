# WerpReadMaxLogLevel(int)

- ea: `0x18002a94c`
- end: `0x18002aa1e`
- name: `?WerpReadMaxLogLevel@@YAKH@Z`
- size: `210`
- prototype: `unsigned int __fastcall(int)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003285c`
- `0x180072164`

## callees

- `0x18002a94c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002a9c9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002a9c9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a9ff`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a9ff`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002a98e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002a98e`

## pseudocode

```c
__int64 __fastcall WerpReadMaxLogLevel(int a1)
{
  int ValueW; // eax
  bool v3; // cc
  char v4; // bl
  unsigned int v5; // edi
  int pvData; // [rsp+68h] [rbp+10h] BYREF
  DWORD pcbData; // [rsp+70h] [rbp+18h] BYREF
  HKEY hkey; // [rsp+78h] [rbp+20h] BYREF

  pvData = 1;
  pcbData = 4;
  hkey = 0;
  ValueW = RegOpenKeyExW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Microsoft\\Windows\\Windows Error Reporting\\Debug",
             0,
             0x101u,
             &hkey);
  v3 = ValueW <= 0;
  if ( ValueW || (ValueW = RegGetValueW(hkey, 0, L"LogLevel", 0x10u, 0, &pvData, &pcbData), v3 = ValueW <= 0, ValueW) )
  {
    if ( !v3 )
      ValueW = (unsigned __int16)ValueW | 0x80070000;
    v4 = 0;
    if ( ValueW < 0 )
    {
      pvData = 1;
      v4 = 1;
    }
  }
  else
  {
    v4 = 0;
  }
  v5 = pvData;
  if ( hkey )
    RegCloseKey(hkey);
  if ( v4 )
    return a1 != 0 ? 3 : 1;
  else
    return v5;
}

```

## disassembly

```asm
0x18002a94c  mov     rax, rsp
0x18002a94f  push    rbx
0x18002a950  push    rsi
0x18002a951  push    rdi
0x18002a952  sub     rsp, 40h
0x18002a956  mov     dword ptr [rax+10h], 1
0x18002a95d  mov     esi, ecx
0x18002a95f  mov     dword ptr [rax+18h], 4
0x18002a966  mov     r9d, 101h; samDesired
0x18002a96c  mov     qword ptr [rax+20h], 0
0x18002a974  lea     rax, [rax+20h]
0x18002a978  xor     r8d, r8d; ulOptions
0x18002a97b  mov     [rsp+58h+phkResult], rax; phkResult
0x18002a980  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\Windows E"...
0x18002a987  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002a98e  call    cs:__imp_RegOpenKeyExW
0x18002a994  test    eax, eax
0x18002a996  jnz     short loc_18002A9D3
0x18002a998  mov     rcx, [rsp+58h+hkey]; hkey
0x18002a99d  lea     rax, [rsp+58h+arg_10]
0x18002a9a2  mov     [rsp+58h+pcbData], rax; pcbData
0x18002a9a7  lea     r8, aLoglevel; "LogLevel"
0x18002a9ae  lea     rax, [rsp+58h+arg_8]
0x18002a9b3  mov     r9d, 10h; dwFlags
0x18002a9b9  mov     [rsp+58h+pvData], rax; pvData
0x18002a9be  xor     edx, edx; lpSubKey
0x18002a9c0  mov     [rsp+58h+phkResult], 0; pdwType
0x18002a9c9  call    cs:__imp_RegGetValueW
0x18002a9cf  test    eax, eax
0x18002a9d1  jz      short loc_18002A9EF
0x18002a9d3  jle     short loc_18002A9DD
0x18002a9d5  movzx   eax, ax
0x18002a9d8  or      eax, 80070000h
0x18002a9dd  xor     bl, bl
0x18002a9df  test    eax, eax
0x18002a9e1  jns     short loc_18002A9F1
0x18002a9e3  mov     [rsp+58h+arg_8], 1
0x18002a9eb  mov     bl, 1
0x18002a9ed  jmp     short loc_18002A9F1
0x18002a9ef  xor     bl, bl
0x18002a9f1  mov     rcx, [rsp+58h+hkey]; hKey
0x18002a9f6  mov     edi, [rsp+58h+arg_8]
0x18002a9fa  test    rcx, rcx
0x18002a9fd  jz      short loc_18002AA05
0x18002a9ff  call    cs:__imp_RegCloseKey
0x18002aa05  test    bl, bl
0x18002aa07  jnz     short loc_18002AA0D
0x18002aa09  mov     eax, edi
0x18002aa0b  jmp     short loc_18002AA16
0x18002aa0d  neg     esi
0x18002aa0f  sbb     eax, eax
0x18002aa11  and     eax, 2
0x18002aa14  inc     eax
0x18002aa16  add     rsp, 40h
0x18002aa1a  pop     rdi
0x18002aa1b  pop     rsi
0x18002aa1c  pop     rbx
0x18002aa1d  retn
```
