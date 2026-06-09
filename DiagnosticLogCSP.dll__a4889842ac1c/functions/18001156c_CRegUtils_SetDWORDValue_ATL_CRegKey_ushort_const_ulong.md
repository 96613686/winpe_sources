# CRegUtils::SetDWORDValue(ATL::CRegKey &,ushort const *,ulong)

- ea: `0x18001156c`
- end: `0x1800115bf`
- name: `?SetDWORDValue@CRegUtils@@SAJAEAVCRegKey@ATL@@PEBGK@Z`
- size: `83`
- prototype: `__int64 __fastcall(struct ATL::CRegKey *, const unsigned __int16 *, unsigned int)`
- caller_count: `12`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000d710`
- `0x18000d818`
- `0x18000e158`
- `0x18000e374`
- `0x18000e5f0`
- `0x18000e664`
- `0x18000e758`
- `0x18001202c`
- `0x1800120cc`
- `0x180013294`
- `0x1800133bc`
- `0x180013460`

## callees

- `0x18001156c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001159e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001159e`

## pseudocode

```c
__int64 __fastcall CRegUtils::SetDWORDValue(HKEY *a1, const unsigned __int16 *a2, int a3)
{
  unsigned int v3; // ebx
  HKEY v4; // rcx
  LSTATUS v5; // eax
  int Data; // [rsp+48h] [rbp+10h] BYREF

  if ( a2 )
  {
    v4 = *a1;
    Data = a3;
    v3 = 0;
    v5 = RegSetValueExW(v4, a2, 0, 4u, (const BYTE *)&Data, 4u);
    if ( v5 )
    {
      if ( v5 > 0 )
        return (unsigned __int16)v5 | 0x80070000;
      else
        return (unsigned int)v5;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v3;
}

```

## disassembly

```asm
0x18001156c  push    rbx
0x18001156e  sub     rsp, 30h
0x180011572  test    rdx, rdx
0x180011575  jnz     short loc_18001157E
0x180011577  mov     ebx, 80070057h
0x18001157c  jmp     short loc_1800115B7
0x18001157e  mov     rcx, [rcx]; hKey
0x180011581  lea     rax, [rsp+38h+Data]
0x180011586  mov     [rsp+38h+Data], r8d
0x18001158b  xor     ebx, ebx
0x18001158d  xor     r8d, r8d; Reserved
0x180011590  lea     r9d, [rbx+4]; dwType
0x180011594  mov     [rsp+38h+cbData], r9d; cbData
0x180011599  mov     [rsp+38h+lpData], rax; lpData
0x18001159e  call    cs:__imp_RegSetValueExW
0x1800115a4  test    eax, eax
0x1800115a6  jz      short loc_1800115B7
0x1800115a8  jg      short loc_1800115AE
0x1800115aa  mov     ebx, eax
0x1800115ac  jmp     short loc_1800115B7
0x1800115ae  movzx   ebx, ax
0x1800115b1  or      ebx, 80070000h
0x1800115b7  mov     eax, ebx
0x1800115b9  add     rsp, 30h
0x1800115bd  pop     rbx
0x1800115be  retn
```
