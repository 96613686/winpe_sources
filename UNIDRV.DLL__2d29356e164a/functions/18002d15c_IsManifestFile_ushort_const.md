# IsManifestFile(ushort const *)

- ea: `0x18002d15c`
- end: `0x18002d193`
- name: `?IsManifestFile@@YA_NPEBG@Z`
- size: `55`
- prototype: `bool __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18002d070`

## callees

- `0x18002d15c`
- `0x180049128`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18002d16a`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18002d16a`

## string_xrefs

- `0x18002d17c`: `-manifest.ini`

## pseudocode

```c
bool __fastcall IsManifestFile(const unsigned __int16 *a1)
{
  wchar_t *v1; // rax
  bool result; // al

  result = 0;
  if ( a1 )
  {
    v1 = wcsrchr(a1, 0x2Du);
    if ( v1 )
    {
      if ( !wcsicmp(v1, L"-manifest.ini") )
        return 1;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002d15c  sub     rsp, 28h
0x18002d160  test    rcx, rcx
0x18002d163  jz      short loc_18002D175
0x18002d165  mov     edx, 2Dh ; '-'; Ch
0x18002d16a  call    cs:__imp_wcsrchr
0x18002d170  test    rax, rax
0x18002d173  jnz     short loc_18002D17C
0x18002d175  xor     al, al
0x18002d177  add     rsp, 28h
0x18002d17b  retn
0x18002d17c  lea     rdx, aManifestIni; "-manifest.ini"
0x18002d183  mov     rcx, rax; String1
0x18002d186  call    _wcsicmp
0x18002d18b  test    eax, eax
0x18002d18d  jnz     short loc_18002D175
0x18002d18f  mov     al, 1
0x18002d191  jmp     short loc_18002D177
```
