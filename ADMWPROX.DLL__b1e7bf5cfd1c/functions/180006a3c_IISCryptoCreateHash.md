# IISCryptoCreateHash

- ea: `0x180006a3c`
- end: `0x180006a92`
- name: `IISCryptoCreateHash`
- size: `86`
- prototype: `__int64 __fastcall(HCRYPTHASH *phHash, HCRYPTPROV hProv)`
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
- `0x180006a3c`

## import_xrefs

- `ADVAPI32!CryptCreateHash` at `0x180006a7f`
- `ADVAPI32!CryptCreateHash` at `0x180006a7f`

## pseudocode

```c
__int64 __fastcall IISCryptoCreateHash(HCRYPTHASH *phHash, HCRYPTPROV hProv)
{
  if ( dword_18000FC34 )
  {
    if ( CryptCreateHash(hProv, 0x8003u, 0, 0, phHash) )
      return 0;
    return IcpGetLastError();
  }
  else
  {
    if ( hProv == 1984918096 )
    {
      *phHash = 1750294856;
      return 0;
    }
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180006a3c  sub     rsp, 38h
0x180006a40  cmp     cs:dword_18000FC34, 0
0x180006a47  mov     rax, rdx
0x180006a4a  jnz     short loc_180006A6C
0x180006a4c  cmp     rax, 764F7250h
0x180006a52  jnz     short loc_180006A62
0x180006a54  mov     qword ptr [rcx], 68536148h
0x180006a5b  xor     eax, eax
0x180006a5d  add     rsp, 38h
0x180006a61  retn
0x180006a62  mov     eax, 80070057h
0x180006a67  add     rsp, 38h
0x180006a6b  retn
0x180006a6c  mov     [rsp+38h+phHash], rcx; phHash
0x180006a71  xor     r9d, r9d; dwFlags
0x180006a74  mov     rcx, rax; hProv
0x180006a77  xor     r8d, r8d; hKey
0x180006a7a  mov     edx, 8003h; Algid
0x180006a7f  call    cs:__imp_CryptCreateHash
0x180006a85  test    eax, eax
0x180006a87  jnz     short loc_180006A5B
0x180006a89  add     rsp, 38h
0x180006a8d  jmp     ?IcpGetLastError@@YAJXZ; IcpGetLastError(void)
```
