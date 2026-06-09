# CRegUtils::SetDWORDValue(ATL::CRegKey &,ushort const *,ulong)

- ea: `0x180011e94`
- end: `0x180011eee`
- name: `?SetDWORDValue@CRegUtils@@SAJAEAVCRegKey@ATL@@PEBGK@Z`
- size: `90`
- prototype: `__int64 __fastcall(struct ATL::CRegKey *, const unsigned __int16 *, unsigned int)`
- caller_count: `12`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000ddbc`
- `0x18000dec8`
- `0x18000e858`
- `0x18000ea88`
- `0x18000ed10`
- `0x18000ed88`
- `0x18000ee84`
- `0x1800129e4`
- `0x180012a88`
- `0x180013cd0`
- `0x180013e08`
- `0x180013eac`

## callees

- `0x180011e94`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180011ec6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180011ec6`

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
0x180011e94  push    rbx
0x180011e96  sub     rsp, 30h
0x180011e9a  test    rdx, rdx
0x180011e9d  jnz     short loc_180011EA6
0x180011e9f  mov     ebx, 80070057h
0x180011ea4  jmp     short loc_180011EE5
0x180011ea6  mov     rcx, [rcx]; hKey
0x180011ea9  lea     rax, [rsp+38h+Data]
0x180011eae  mov     [rsp+38h+Data], r8d
0x180011eb3  xor     ebx, ebx
0x180011eb5  xor     r8d, r8d; Reserved
0x180011eb8  lea     r9d, [rbx+4]; dwType
0x180011ebc  mov     [rsp+38h+cbData], r9d; cbData
0x180011ec1  mov     [rsp+38h+lpData], rax; lpData
0x180011ec6  call    cs:__imp_RegSetValueExW
0x180011ecd  nop     dword ptr [rax+rax+00h]
0x180011ed2  test    eax, eax
0x180011ed4  jz      short loc_180011EE5
0x180011ed6  jg      short loc_180011EDC
0x180011ed8  mov     ebx, eax
0x180011eda  jmp     short loc_180011EE5
0x180011edc  movzx   ebx, ax
0x180011edf  or      ebx, 80070000h
0x180011ee5  mov     eax, ebx
0x180011ee7  add     rsp, 30h
0x180011eeb  pop     rbx
0x180011eec  retn
```
