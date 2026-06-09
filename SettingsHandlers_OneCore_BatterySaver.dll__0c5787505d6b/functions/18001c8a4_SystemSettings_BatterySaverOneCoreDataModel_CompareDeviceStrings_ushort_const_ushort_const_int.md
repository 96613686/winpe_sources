# SystemSettings::BatterySaverOneCoreDataModel::CompareDeviceStrings(ushort const *,ushort const *,int *)

- ea: `0x18001c8a4`
- end: `0x18001c902`
- name: `?CompareDeviceStrings@BatterySaverOneCoreDataModel@SystemSettings@@YA_NPEBG0PEAH@Z`
- size: `94`
- prototype: `bool __fastcall(const WCHAR *this, const unsigned __int16 *, unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001d330`

## callees

- `0x18001c8a4`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001c8d1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001c8d1`

## pseudocode

```c
bool __fastcall SystemSettings::BatterySaverOneCoreDataModel::CompareDeviceStrings(
        const WCHAR *this,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        int *a4)
{
  int v5; // eax

  *(_DWORD *)a3 = 2;
  if ( this )
  {
    if ( a2 )
    {
      v5 = CompareStringOrdinal(this, -1, a2, -1, 1);
      *(_DWORD *)a3 = v5;
      return v5 != 2;
    }
    *(_DWORD *)a3 = 1;
    return 1;
  }
  if ( a2 )
  {
    *(_DWORD *)a3 = 3;
    return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x18001c8a4  push    rbx
0x18001c8a6  sub     rsp, 30h
0x18001c8aa  mov     dword ptr [r8], 2
0x18001c8b1  mov     rbx, r8
0x18001c8b4  test    rcx, rcx
0x18001c8b7  jz      short loc_18001C8EC
0x18001c8b9  test    rdx, rdx
0x18001c8bc  jz      short loc_18001C8E1
0x18001c8be  or      eax, 0FFFFFFFFh
0x18001c8c1  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x18001c8c9  mov     r8, rdx; lpString2
0x18001c8cc  mov     r9d, eax; cchCount2
0x18001c8cf  mov     edx, eax; cchCount1
0x18001c8d1  call    cs:__imp_CompareStringOrdinal
0x18001c8d7  cmp     eax, 2
0x18001c8da  mov     [rbx], eax
0x18001c8dc  setnz   al
0x18001c8df  jmp     short loc_18001C8FC
0x18001c8e1  mov     dword ptr [r8], 1
0x18001c8e8  mov     al, 1
0x18001c8ea  jmp     short loc_18001C8FC
0x18001c8ec  test    rdx, rdx
0x18001c8ef  jz      short loc_18001C8FA
0x18001c8f1  mov     dword ptr [r8], 3
0x18001c8f8  jmp     short loc_18001C8E8
0x18001c8fa  xor     al, al
0x18001c8fc  add     rsp, 30h
0x18001c900  pop     rbx
0x18001c901  retn
```
