# FExistsRegisteredTypelib(HKEY__ *,ushort const *,ushort const * *)

- ea: `0x1800154dc`
- end: `0x1800155a8`
- name: `?FExistsRegisteredTypelib@@YAHPEAUHKEY__@@PEBGPEAPEBG@Z`
- size: `204`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, const unsigned __int16 **)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180015414`

## callees

- `0x1800154dc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015562`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015572`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015562`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015572`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180015512`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180015550`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001559c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180015512`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180015550`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001559c`

## pseudocode

```c
__int64 __fastcall FExistsRegisteredTypelib(HKEY a1, const unsigned __int16 *a2, const unsigned __int16 **a3)
{
  unsigned int v4; // ebx
  const unsigned __int16 *v6; // rsi
  HKEY v7; // rcx
  HKEY hKey; // [rsp+30h] [rbp-18h] BYREF
  HKEY phkResult; // [rsp+68h] [rbp+20h] BYREF

  hKey = 0;
  phkResult = 0;
  v4 = 0;
  if ( !RegOpenKeyExW(a1, a2, 0, 0x2000000u, &hKey) )
  {
    v6 = L"win64";
    if ( !RegOpenKeyExW(hKey, L"win64", 0, 0x2000000u, &phkResult)
      || (v6 = L"win32", !RegOpenKeyExW(hKey, L"win32", 0, 0x2000000u, &phkResult)) )
    {
      v7 = phkResult;
      *a3 = v6;
      RegCloseKey(v7);
      v4 = 1;
    }
    RegCloseKey(hKey);
  }
  return v4;
}

```

## disassembly

```asm
0x1800154dc  mov     r11, rsp
0x1800154df  mov     [r11+8], rbx
0x1800154e3  mov     [r11+10h], rsi
0x1800154e7  push    rdi
0x1800154e8  sub     rsp, 40h
0x1800154ec  mov     rdi, r8
0x1800154ef  mov     qword ptr [r11-18h], 0
0x1800154f7  lea     rax, [r11-18h]
0x1800154fb  mov     qword ptr [r11+20h], 0
0x180015503  xor     r8d, r8d; ulOptions
0x180015506  mov     [r11-28h], rax
0x18001550a  mov     r9d, 2000000h; samDesired
0x180015510  xor     ebx, ebx
0x180015512  call    cs:__imp_RegOpenKeyExW
0x180015518  test    eax, eax
0x18001551a  jz      short loc_18001552E
0x18001551c  mov     rsi, [rsp+48h+arg_8]
0x180015521  mov     eax, ebx
0x180015523  mov     rbx, [rsp+48h+arg_0]
0x180015528  add     rsp, 40h
0x18001552c  pop     rdi
0x18001552d  retn
0x18001552e  mov     rcx, [rsp+48h+hKey]; hKey
0x180015533  lea     rax, [rsp+48h+arg_18]
0x180015538  lea     rsi, aWin64; "win64"
0x18001553f  mov     [rsp+48h+phkResult], rax; phkResult
0x180015544  mov     rdx, rsi; lpSubKey
0x180015547  mov     r9d, 2000000h; samDesired
0x18001554d  xor     r8d, r8d; ulOptions
0x180015550  call    cs:__imp_RegOpenKeyExW
0x180015556  test    eax, eax
0x180015558  jnz     short loc_18001557A
0x18001555a  mov     rcx, [rsp+48h+arg_18]; hKey
0x18001555f  mov     [rdi], rsi
0x180015562  call    cs:__imp_RegCloseKey
0x180015568  mov     ebx, 1
0x18001556d  mov     rcx, [rsp+48h+hKey]; hKey
0x180015572  call    cs:__imp_RegCloseKey
0x180015578  jmp     short loc_18001551C
0x18001557a  mov     rcx, [rsp+48h+hKey]; hKey
0x18001557f  lea     rax, [rsp+48h+arg_18]
0x180015584  lea     rsi, aWin32; "win32"
0x18001558b  mov     [rsp+48h+phkResult], rax; phkResult
0x180015590  mov     rdx, rsi; lpSubKey
0x180015593  mov     r9d, 2000000h; samDesired
0x180015599  xor     r8d, r8d; ulOptions
0x18001559c  call    cs:__imp_RegOpenKeyExW
0x1800155a2  test    eax, eax
0x1800155a4  jz      short loc_18001555A
0x1800155a6  jmp     short loc_18001556D
```
