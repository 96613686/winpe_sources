# SpeechPlatform::Settings::Details::RegistryStorage<bool>::SetValue(HKEY__ * const,ushort const * const,bool)

- ea: `0x140017d30`
- end: `0x140017d6b`
- name: `?SetValue@?$RegistryStorage@_N@Details@Settings@SpeechPlatform@@SAJQEAUHKEY__@@QEBG_N@Z`
- size: `59`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140013588`

## callees

- `0x140017d30`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140017d54`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140017d54`

## pseudocode

```c
LSTATUS __fastcall SpeechPlatform::Settings::Details::RegistryStorage<bool>::SetValue(
        HKEY a1,
        const WCHAR *a2,
        unsigned __int8 a3)
{
  LSTATUS result; // eax
  int Data; // [rsp+50h] [rbp+18h] BYREF

  Data = a3;
  result = RegSetValueExW(a1, a2, 0, 4u, (const BYTE *)&Data, 4u);
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x140017d30  sub     rsp, 38h
0x140017d34  movzx   eax, r8b
0x140017d38  mov     r9d, 4; dwType
0x140017d3e  mov     [rsp+38h+Data], eax
0x140017d42  xor     r8d, r8d; Reserved
0x140017d45  lea     rax, [rsp+38h+Data]
0x140017d4a  mov     [rsp+38h+cbData], r9d; cbData
0x140017d4f  mov     [rsp+38h+lpData], rax; lpData
0x140017d54  call    cs:__imp_RegSetValueExW
0x140017d5a  test    eax, eax
0x140017d5c  jle     short loc_140017D66
0x140017d5e  movzx   eax, ax
0x140017d61  or      eax, 80070000h
0x140017d66  add     rsp, 38h
0x140017d6a  retn
```
