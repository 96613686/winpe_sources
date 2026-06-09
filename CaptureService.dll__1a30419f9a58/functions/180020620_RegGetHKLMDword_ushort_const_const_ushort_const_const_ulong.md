# RegGetHKLMDword(ushort const * const,ushort const * const,ulong *)

- ea: `0x180020620`
- end: `0x18002068d`
- name: `?RegGetHKLMDword@@YA_NQEBG0PEAK@Z`
- size: `109`
- prototype: `bool __fastcall(const unsigned __int16 *const, const unsigned __int16 *const, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180020504`

## callees

- `0x1800205a4`
- `0x180020620`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002065c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002065c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002067a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002067a`

## pseudocode

```c
bool __fastcall RegGetHKLMDword(const unsigned __int16 *const a1, const unsigned __int16 *const a2, unsigned int *a3)
{
  bool Dword; // bl
  const unsigned __int16 *v5; // rdx
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  hKey = 0;
  Dword = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Avalon.Graphics", 0, 0x20019u, &hKey) )
  {
    Dword = RegGetDword(hKey, v5, a3);
    RegCloseKey(hKey);
  }
  return Dword;
}

```

## disassembly

```asm
0x180020620  mov     r11, rsp
0x180020623  mov     [r11+8], rbx
0x180020627  mov     [r11+10h], rdx
0x18002062b  push    rdi
0x18002062c  sub     rsp, 30h
0x180020630  mov     rdi, r8
0x180020633  mov     qword ptr [r11+10h], 0
0x18002063b  lea     rax, [r11+10h]
0x18002063f  xor     r8d, r8d; ulOptions
0x180020642  mov     r9d, 20019h; samDesired
0x180020648  mov     [r11-18h], rax
0x18002064c  lea     rdx, SubKey; "Software\\Microsoft\\Avalon.Graphics"
0x180020653  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002065a  xor     bl, bl
0x18002065c  call    cs:__imp_RegOpenKeyExW
0x180020662  test    eax, eax
0x180020664  jnz     short loc_180020680
0x180020666  mov     rcx, [rsp+38h+hKey]; HKEY
0x18002066b  mov     r8, rdi; unsigned int *
0x18002066e  call    ?RegGetDword@@YA_NQEAUHKEY__@@QEBGPEAK@Z; RegGetDword(HKEY__ * const,ushort const * const,ulong *)
0x180020673  mov     rcx, [rsp+38h+hKey]; hKey
0x180020678  mov     bl, al
0x18002067a  call    cs:__imp_RegCloseKey
0x180020680  mov     al, bl
0x180020682  mov     rbx, [rsp+38h+arg_0]
0x180020687  add     rsp, 30h
0x18002068b  pop     rdi
0x18002068c  retn
```
