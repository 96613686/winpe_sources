# SetRegistryStringValue(HKEY__ *,ulong,ushort const *,ushort const *,long)

- ea: `0x18002d4cc`
- end: `0x18002d544`
- name: `?SetRegistryStringValue@@YAHPEAUHKEY__@@KPEBG1J@Z`
- size: `120`
- prototype: `__int64 __fastcall(HKEY, DWORD, const unsigned __int16 *, const BYTE *lpData)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180028c8c`
- `0x180028ef0`
- `0x18002aa90`

## callees

- `0x18002d0e4`
- `0x18002d4cc`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x18002d50d`
- `ADVAPI32!RegSetValueExW` at `0x18002d50d`

## string_xrefs

- `0x18002d520`: `RegSetValueEx() failed[%s], ec=%d`

## pseudocode

```c
__int64 __fastcall SetRegistryStringValue(HKEY a1, DWORD a2, const unsigned __int16 *a3, const BYTE *lpData)
{
  __int64 v5; // rax
  DWORD cbData; // eax
  unsigned int v7; // eax

  if ( lpData )
  {
    v5 = -1;
    do
      ++v5;
    while ( *(_WORD *)&lpData[2 * v5] );
    cbData = 2 * v5 + 2;
  }
  else
  {
    cbData = 0;
  }
  v7 = RegSetValueExW(a1, a3, 0, a2, lpData, cbData);
  if ( !v7 )
    return 1;
  fax_dprintf(L"RegSetValueEx() failed[%s], ec=%d", a3, v7);
  return 0;
}

```

## disassembly

```asm
0x18002d4cc  mov     [rsp+arg_0], rbx
0x18002d4d1  push    rdi
0x18002d4d2  sub     rsp, 30h
0x18002d4d6  xor     edi, edi
0x18002d4d8  mov     rbx, r8
0x18002d4db  test    r9, r9
0x18002d4de  jz      short loc_18002D4F8
0x18002d4e0  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002d4e4  inc     rax
0x18002d4e7  cmp     [r9+rax*2], di
0x18002d4ec  jnz     short loc_18002D4E4
0x18002d4ee  lea     rax, ds:2[rax*2]
0x18002d4f6  jmp     short loc_18002D4FB
0x18002d4f8  mov     rax, rdi
0x18002d4fb  mov     [rsp+38h+cbData], eax; cbData
0x18002d4ff  xor     r8d, r8d; Reserved
0x18002d502  mov     [rsp+38h+lpData], r9; lpData
0x18002d507  mov     r9d, edx; dwType
0x18002d50a  mov     rdx, rbx; lpValueName
0x18002d50d  call    cs:__imp_RegSetValueExW
0x18002d514  nop     dword ptr [rax+rax+00h]
0x18002d519  test    eax, eax
0x18002d51b  jz      short loc_18002D533
0x18002d51d  mov     r8d, eax
0x18002d520  lea     rcx, aRegsetvalueexF; "RegSetValueEx() failed[%s], ec=%d"
0x18002d527  mov     rdx, rbx
0x18002d52a  call    fax_dprintf
0x18002d52f  xor     eax, eax
0x18002d531  jmp     short loc_18002D538
0x18002d533  mov     eax, 1
0x18002d538  mov     rbx, [rsp+38h+arg_0]
0x18002d53d  add     rsp, 30h
0x18002d541  pop     rdi
0x18002d542  retn
```
