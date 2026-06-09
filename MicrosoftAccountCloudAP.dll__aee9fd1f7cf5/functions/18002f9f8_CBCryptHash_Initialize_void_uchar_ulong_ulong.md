# CBCryptHash::Initialize(void *,uchar *,ulong,ulong)

- ea: `0x18002f9f8`
- end: `0x18002fa34`
- name: `?Initialize@CBCryptHash@@QEAAJPEAXPEAEKK@Z`
- size: `60`
- prototype: `NTSTATUS __fastcall(BCRYPT_HASH_HANDLE *phHash, BCRYPT_ALG_HANDLE hAlgorithm, PUCHAR pbSecret, ULONG cbSecret)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18002f3d4`
- `0x18002f6cc`

## callees

- `0x18002f9f8`

## import_xrefs

- `bcrypt!BCryptCreateHash` at `0x18002fa1d`
- `bcrypt!BCryptCreateHash` at `0x18002fa1d`

## pseudocode

```c
NTSTATUS __fastcall CBCryptHash::Initialize(
        BCRYPT_HASH_HANDLE *phHash,
        BCRYPT_ALG_HANDLE hAlgorithm,
        PUCHAR pbSecret,
        ULONG cbSecret)
{
  NTSTATUS result; // eax

  result = BCryptCreateHash(hAlgorithm, phHash, 0, 0, pbSecret, cbSecret, 0);
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18002f9f8  sub     rsp, 48h
0x18002f9fc  mov     rax, rdx
0x18002f9ff  mov     [rsp+48h+dwFlags], 0; dwFlags
0x18002fa07  mov     [rsp+48h+cbSecret], r9d; cbSecret
0x18002fa0c  mov     rdx, rcx; phHash
0x18002fa0f  mov     [rsp+48h+pbSecret], r8; pbSecret
0x18002fa14  xor     r9d, r9d; cbHashObject
0x18002fa17  xor     r8d, r8d; pbHashObject
0x18002fa1a  mov     rcx, rax; hAlgorithm
0x18002fa1d  call    cs:__imp_BCryptCreateHash
0x18002fa23  test    eax, eax
0x18002fa25  jle     short loc_18002FA2F
0x18002fa27  movzx   eax, ax
0x18002fa2a  or      eax, 80070000h
0x18002fa2f  add     rsp, 48h
0x18002fa33  retn
```
