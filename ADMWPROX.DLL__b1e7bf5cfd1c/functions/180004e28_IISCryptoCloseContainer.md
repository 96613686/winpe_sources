# IISCryptoCloseContainer

- ea: `0x180004e28`
- end: `0x180004e64`
- name: `IISCryptoCloseContainer`
- size: `60`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180004468`
- `0x180005094`

## callees

- `0x180004870`
- `0x180004e28`

## import_xrefs

- `ADVAPI32!CryptReleaseContext` at `0x180004e4a`
- `ADVAPI32!CryptReleaseContext` at `0x180004e4a`

## pseudocode

```c
signed int __fastcall IISCryptoCloseContainer(HCRYPTPROV a1)
{
  if ( !dword_18000FC34 )
  {
    if ( a1 != 1984918096 )
      return -2147024809;
    return 0;
  }
  if ( CryptReleaseContext(a1, 0) )
    return 0;
  return IcpGetLastError();
}

```

## disassembly

```asm
0x180004e28  sub     rsp, 28h
0x180004e2c  cmp     cs:dword_18000FC34, 0
0x180004e33  jnz     short loc_180004E48
0x180004e35  cmp     rcx, 764F7250h
0x180004e3c  jz      short loc_180004E54
0x180004e3e  mov     eax, 80070057h
0x180004e43  add     rsp, 28h
0x180004e47  retn
0x180004e48  xor     edx, edx; dwFlags
0x180004e4a  call    cs:__imp_CryptReleaseContext
0x180004e50  test    eax, eax
0x180004e52  jz      short loc_180004E5B
0x180004e54  xor     eax, eax
0x180004e56  add     rsp, 28h
0x180004e5a  retn
0x180004e5b  add     rsp, 28h
0x180004e5f  jmp     ?IcpGetLastError@@YAJXZ; IcpGetLastError(void)
```
