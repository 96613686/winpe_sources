# IsManifestFile(ushort const *)

- ea: `0x18002d9dc`
- end: `0x18002da1a`
- name: `?IsManifestFile@@YA_NPEBG@Z`
- size: `62`
- prototype: `bool __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18002d8f0`

## callees

- `0x18002d9dc`
- `0x18004a668`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18002d9ea`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18002d9ea`

## string_xrefs

- `0x18002da03`: `-manifest.ini`

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
0x18002d9dc  sub     rsp, 28h
0x18002d9e0  test    rcx, rcx
0x18002d9e3  jz      short loc_18002D9FB
0x18002d9e5  mov     edx, 2Dh ; '-'; Ch
0x18002d9ea  call    cs:__imp_wcsrchr
0x18002d9f1  nop     dword ptr [rax+rax+00h]
0x18002d9f6  test    rax, rax
0x18002d9f9  jnz     short loc_18002DA03
0x18002d9fb  xor     al, al
0x18002d9fd  add     rsp, 28h
0x18002da01  retn
0x18002da03  lea     rdx, aManifestIni; "-manifest.ini"
0x18002da0a  mov     rcx, rax; String1
0x18002da0d  call    _wcsicmp
0x18002da12  test    eax, eax
0x18002da14  jnz     short loc_18002D9FB
0x18002da16  mov     al, 1
0x18002da18  jmp     short loc_18002D9FD
```
