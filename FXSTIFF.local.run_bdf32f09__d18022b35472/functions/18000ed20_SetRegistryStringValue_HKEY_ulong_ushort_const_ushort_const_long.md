# SetRegistryStringValue(HKEY__ *,ulong,ushort const *,ushort const *,long)

- ea: `0x18000ed20`
- end: `0x18000ed90`
- name: `?SetRegistryStringValue@@YAHPEAUHKEY__@@KPEBG1J@Z`
- size: `112`
- prototype: `int(HKEY, unsigned int, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800175a8`

## callees

- `0x18000ed20`
- `0x180016794`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x18000ed61`
- `ADVAPI32!RegSetValueExW` at `0x18000ed61`

## string_xrefs

- `0x18000ed75`: `RegSetValueEx() failed[%s], ec=%d`

## pseudocode

```c
__int64 __fastcall SetRegistryStringValue(HKEY a1, __int64 a2, const unsigned __int16 *a3, const BYTE *lpData)
{
  __int64 v4; // rax
  DWORD cbData; // eax
  unsigned int v6; // eax

  if ( lpData )
  {
    v4 = -1;
    do
      ++v4;
    while ( *(_WORD *)&lpData[2 * v4] );
    cbData = 2 * v4 + 2;
  }
  else
  {
    cbData = 0;
  }
  v6 = RegSetValueExW(a1, L"Name", 0, 1u, lpData, cbData);
  if ( !v6 )
    return 1;
  fax_dprintf(L"RegSetValueEx() failed[%s], ec=%d", L"Name", v6);
  return 0;
}

```

## disassembly

```asm
0x18000ed20  push    rbx
0x18000ed22  sub     rsp, 30h
0x18000ed26  xor     ebx, ebx
0x18000ed28  test    r9, r9
0x18000ed2b  jz      short loc_18000ED45
0x18000ed2d  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000ed31  inc     rax
0x18000ed34  cmp     [r9+rax*2], bx
0x18000ed39  jnz     short loc_18000ED31
0x18000ed3b  lea     rax, ds:2[rax*2]
0x18000ed43  jmp     short loc_18000ED48
0x18000ed45  mov     rax, rbx
0x18000ed48  mov     [rsp+38h+cbData], eax; cbData
0x18000ed4c  lea     rdx, ValueName; "Name"
0x18000ed53  mov     [rsp+38h+lpData], r9; lpData
0x18000ed58  xor     r8d, r8d; Reserved
0x18000ed5b  mov     r9d, 1; dwType
0x18000ed61  call    cs:__imp_RegSetValueExW
0x18000ed67  test    eax, eax
0x18000ed69  jz      short loc_18000ED85
0x18000ed6b  mov     r8d, eax
0x18000ed6e  lea     rdx, ValueName; "Name"
0x18000ed75  lea     rcx, aRegsetvalueexF; "RegSetValueEx() failed[%s], ec=%d"
0x18000ed7c  call    fax_dprintf
0x18000ed81  xor     eax, eax
0x18000ed83  jmp     short loc_18000ED8A
0x18000ed85  mov     eax, 1
0x18000ed8a  add     rsp, 30h
0x18000ed8e  pop     rbx
0x18000ed8f  retn
```
