# SetRegistryStringValue(HKEY__ *,ulong,ushort const *,ushort const *,long)

- ea: `0x18000f454`
- end: `0x18000f4cb`
- name: `?SetRegistryStringValue@@YAHPEAUHKEY__@@KPEBG1J@Z`
- size: `119`
- prototype: `int(HKEY, unsigned int, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180018340`

## callees

- `0x18000f454`
- `0x1800174d8`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x18000f495`
- `ADVAPI32!RegSetValueExW` at `0x18000f495`

## string_xrefs

- `0x18000f4af`: `RegSetValueEx() failed[%s], ec=%d`

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
0x18000f454  push    rbx
0x18000f456  sub     rsp, 30h
0x18000f45a  xor     ebx, ebx
0x18000f45c  test    r9, r9
0x18000f45f  jz      short loc_18000F479
0x18000f461  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000f465  inc     rax
0x18000f468  cmp     [r9+rax*2], bx
0x18000f46d  jnz     short loc_18000F465
0x18000f46f  lea     rax, ds:2[rax*2]
0x18000f477  jmp     short loc_18000F47C
0x18000f479  mov     rax, rbx
0x18000f47c  mov     [rsp+38h+cbData], eax; cbData
0x18000f480  lea     rdx, ValueName; "Name"
0x18000f487  mov     [rsp+38h+lpData], r9; lpData
0x18000f48c  xor     r8d, r8d; Reserved
0x18000f48f  mov     r9d, 1; dwType
0x18000f495  call    cs:__imp_RegSetValueExW
0x18000f49c  nop     dword ptr [rax+rax+00h]
0x18000f4a1  test    eax, eax
0x18000f4a3  jz      short loc_18000F4BF
0x18000f4a5  mov     r8d, eax
0x18000f4a8  lea     rdx, ValueName; "Name"
0x18000f4af  lea     rcx, aRegsetvalueexF; "RegSetValueEx() failed[%s], ec=%d"
0x18000f4b6  call    fax_dprintf
0x18000f4bb  xor     eax, eax
0x18000f4bd  jmp     short loc_18000F4C4
0x18000f4bf  mov     eax, 1
0x18000f4c4  add     rsp, 30h
0x18000f4c8  pop     rbx
0x18000f4c9  retn
```
