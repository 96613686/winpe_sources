# HampSystemOpenKey(HKEY__ *,ushort const *,ulong,HKEY__ * *)

- ea: `0x18000f964`
- end: `0x18000f98c`
- name: `?HampSystemOpenKey@@YAJPEAUHKEY__@@PEBGKPEAPEAU1@@Z`
- size: `40`
- prototype: `LSTATUS __fastcall(HKEY, const unsigned __int16 *, REGSAM, HKEY *phkResult)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180019cd0`

## callees

- `0x18000f964`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f973`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f973`

## pseudocode

```c
LSTATUS __fastcall HampSystemOpenKey(HKEY a1, const unsigned __int16 *a2, REGSAM a3, HKEY *phkResult)
{
  LSTATUS result; // eax

  result = RegOpenKeyExW(a1, a2, 0, a3, phkResult);
  if ( result > 0 )
    return (unsigned __int16)result | 0xC0070000;
  return result;
}

```

## disassembly

```asm
0x18000f964  sub     rsp, 38h
0x18000f968  mov     [rsp+38h+phkResult], r9; phkResult
0x18000f96d  mov     r9d, r8d; samDesired
0x18000f970  xor     r8d, r8d; ulOptions
0x18000f973  call    cs:__imp_RegOpenKeyExW
0x18000f979  test    eax, eax
0x18000f97b  jg      short loc_18000F982
0x18000f97d  add     rsp, 38h
0x18000f981  retn
0x18000f982  movzx   eax, ax
0x18000f985  or      eax, 0C0070000h
0x18000f98a  jmp     short loc_18000F97D
```
