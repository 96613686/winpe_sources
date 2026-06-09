# RegGetHKLMDword(ushort const * const,ushort const * const,ulong *)

- ea: `0x1800e09d4`
- end: `0x1800e0a48`
- name: `?RegGetHKLMDword@@YA_NQEBG0PEAK@Z`
- size: `116`
- prototype: `bool __fastcall(LPCWSTR lpSubKey, const unsigned __int16 *const, unsigned int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800e0858`
- `0x1800e08b0`

## callees

- `0x1800e0964`
- `0x1800e09d4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800e0a30`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800e0a30`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800e0a0f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800e0a0f`

## pseudocode

```c
bool __fastcall RegGetHKLMDword(LPCWSTR lpSubKey, const unsigned __int16 *a2, unsigned int *a3)
{
  bool Dword; // bl
  HKEY hKey; // [rsp+58h] [rbp+20h] BYREF

  hKey = 0;
  Dword = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20019u, &hKey) )
  {
    Dword = RegGetDword(hKey, a2, a3);
    RegCloseKey(hKey);
  }
  return Dword;
}

```

## disassembly

```asm
0x1800e09d4  mov     r11, rsp
0x1800e09d7  mov     [r11+8], rbx
0x1800e09db  mov     [r11+10h], rsi
0x1800e09df  push    rdi
0x1800e09e0  sub     rsp, 30h
0x1800e09e4  mov     rsi, rdx
0x1800e09e7  mov     qword ptr [r11+20h], 0
0x1800e09ef  mov     rdx, rcx; lpSubKey
0x1800e09f2  lea     rax, [r11+20h]
0x1800e09f6  mov     rdi, r8
0x1800e09f9  mov     [r11-18h], rax
0x1800e09fd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800e0a04  mov     r9d, 20019h; samDesired
0x1800e0a0a  xor     r8d, r8d; ulOptions
0x1800e0a0d  xor     bl, bl
0x1800e0a0f  call    cs:__imp_RegOpenKeyExW
0x1800e0a15  test    eax, eax
0x1800e0a17  jnz     short loc_1800E0A36
0x1800e0a19  mov     rcx, [rsp+38h+hKey]; HKEY
0x1800e0a1e  mov     r8, rdi; unsigned int *
0x1800e0a21  mov     rdx, rsi; unsigned __int16 *
0x1800e0a24  call    ?RegGetDword@@YA_NQEAUHKEY__@@QEBGPEAK@Z; RegGetDword(HKEY__ * const,ushort const * const,ulong *)
0x1800e0a29  mov     rcx, [rsp+38h+hKey]; hKey
0x1800e0a2e  mov     bl, al
0x1800e0a30  call    cs:__imp_RegCloseKey
0x1800e0a36  mov     rsi, [rsp+38h+arg_8]
0x1800e0a3b  mov     al, bl
0x1800e0a3d  mov     rbx, [rsp+38h+arg_0]
0x1800e0a42  add     rsp, 30h
0x1800e0a46  pop     rdi
0x1800e0a47  retn
```
