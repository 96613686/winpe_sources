# IISCryptoDestroyHash

- ea: `0x180006a98`
- end: `0x180006ad2`
- name: `IISCryptoDestroyHash`
- size: `58`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x180005650`
- `0x180005bd8`
- `0x180006104`
- `0x180006508`
- `0x180006704`
- `0x180006918`

## callees

- `0x180004870`
- `0x180006a98`

## import_xrefs

- `ADVAPI32!CryptDestroyHash` at `0x180006ab8`
- `ADVAPI32!CryptDestroyHash` at `0x180006ab8`

## pseudocode

```c
signed int __fastcall IISCryptoDestroyHash(HCRYPTHASH a1)
{
  if ( !dword_18000FC34 )
  {
    if ( a1 != 1750294856 )
      return -2147024809;
    return 0;
  }
  if ( CryptDestroyHash(a1) )
    return 0;
  return IcpGetLastError();
}

```

## disassembly

```asm
0x180006a98  sub     rsp, 28h
0x180006a9c  cmp     cs:dword_18000FC34, 0
0x180006aa3  jnz     short loc_180006AB8
0x180006aa5  cmp     rcx, 68536148h
0x180006aac  jz      short loc_180006AC2
0x180006aae  mov     eax, 80070057h
0x180006ab3  add     rsp, 28h
0x180006ab7  retn
0x180006ab8  call    cs:__imp_CryptDestroyHash
0x180006abe  test    eax, eax
0x180006ac0  jz      short loc_180006AC9
0x180006ac2  xor     eax, eax
0x180006ac4  add     rsp, 28h
0x180006ac8  retn
0x180006ac9  add     rsp, 28h
0x180006acd  jmp     ?IcpGetLastError@@YAJXZ; IcpGetLastError(void)
```
