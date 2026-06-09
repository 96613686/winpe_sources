# GetRunningModeMapping(tagMPRUNNING_MODE *)

- ea: `0x18002045c`
- end: `0x18002049e`
- name: `?GetRunningModeMapping@@YAPEBGPEAW4tagMPRUNNING_MODE@@@Z`
- size: `66`
- prototype: `const unsigned __int16 *__fastcall(enum tagMPRUNNING_MODE *)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18001e8a0`

## callees

- `0x18002045c`

## string_xrefs

- `0x18002047e`: `SideBySidePassive`

## pseudocode

```c
const unsigned __int16 *__fastcall GetRunningModeMapping(enum tagMPRUNNING_MODE *a1)
{
  int v1; // ecx
  int v2; // ecx
  int v3; // ecx

  if ( a1 )
  {
    v1 = *(_DWORD *)a1;
    if ( !v1 )
      return L"Normal";
    v2 = v1 - 1;
    if ( !v2 )
      return L"Passive";
    v3 = v2 - 1;
    if ( !v3 )
      return L"SideBySidePassive";
    if ( v3 == 1 )
      return L"NotRunning";
  }
  return L"Unknown";
}

```

## disassembly

```asm
0x18002045c  test    rcx, rcx
0x18002045f  jz      short loc_180020496
0x180020461  mov     ecx, [rcx]
0x180020463  test    ecx, ecx
0x180020465  jz      short loc_18002048E
0x180020467  sub     ecx, 1
0x18002046a  jz      short loc_180020486
0x18002046c  sub     ecx, 1
0x18002046f  jz      short loc_18002047E
0x180020471  cmp     ecx, 1
0x180020474  jnz     short loc_180020496
0x180020476  lea     rax, aNotrunning; "NotRunning"
0x18002047d  retn
0x18002047e  lea     rax, aSidebysidepass; "SideBySidePassive"
0x180020485  retn
0x180020486  lea     rax, aPassive; "Passive"
0x18002048d  retn
0x18002048e  lea     rax, aNormal; "Normal"
0x180020495  retn
0x180020496  lea     rax, aUnknown; "Unknown"
0x18002049d  retn
```
