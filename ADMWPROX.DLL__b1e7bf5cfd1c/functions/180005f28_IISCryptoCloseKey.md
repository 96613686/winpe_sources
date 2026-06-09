# IISCryptoCloseKey

- ea: `0x180005f28`
- end: `0x180005f74`
- name: `IISCryptoCloseKey`
- size: `76`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180004e6c`
- `0x180005094`
- `0x18000560c`
- `0x180005b90`

## callees

- `0x180004870`
- `0x180005f28`

## import_xrefs

- `ADVAPI32!CryptDestroyKey` at `0x180005f5a`
- `ADVAPI32!CryptDestroyKey` at `0x180005f5a`

## pseudocode

```c
signed int __fastcall IISCryptoCloseKey(HCRYPTKEY a1)
{
  if ( !dword_18000FC34 )
  {
    if ( a1 != 1800627539 && a1 != 1799842131 && a1 != 1801020747 )
      return -2147024809;
    return 0;
  }
  if ( CryptDestroyKey(a1) )
    return 0;
  return IcpGetLastError();
}

```

## disassembly

```asm
0x180005f28  sub     rsp, 28h
0x180005f2c  cmp     cs:dword_18000FC34, 0
0x180005f33  jnz     short loc_180005F5A
0x180005f35  cmp     rcx, 6B536553h
0x180005f3c  jz      short loc_180005F64
0x180005f3e  cmp     rcx, 6B476953h
0x180005f45  jz      short loc_180005F64
0x180005f47  cmp     rcx, 6B59654Bh
0x180005f4e  jz      short loc_180005F64
0x180005f50  mov     eax, 80070057h
0x180005f55  add     rsp, 28h
0x180005f59  retn
0x180005f5a  call    cs:__imp_CryptDestroyKey
0x180005f60  test    eax, eax
0x180005f62  jz      short loc_180005F6B
0x180005f64  xor     eax, eax
0x180005f66  add     rsp, 28h
0x180005f6a  retn
0x180005f6b  add     rsp, 28h
0x180005f6f  jmp     ?IcpGetLastError@@YAJXZ; IcpGetLastError(void)
```
