# WalletEncrypter::Decrypt(unsigned __int64,uchar *,ulong,std::unique_ptr<uchar [0],std::default_delete<uchar [0]>> &,ulong &,int)

- ea: `0x18001b760`
- end: `0x18001b8b2`
- name: `?Decrypt@WalletEncrypter@@QEAAJ_KPEAEKAEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@AEAKH@Z`
- size: `338`
- prototype: `__int64 __fastcall(BCRYPT_KEY_HANDLE *, unsigned __int64, UCHAR *, ULONG, void **, ULONG *pcbResult, int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180012fe0`

## callees

- `0x180002e48`
- `0x18001b458`
- `0x18001b760`
- `0x18001bb7c`
- `0x180043090`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18001b83e`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001b83e`
- `bcrypt!BCryptDecrypt` at `0x18001b810`
- `bcrypt!BCryptDecrypt` at `0x18001b881`
- `bcrypt!BCryptDecrypt` at `0x18001b810`
- `bcrypt!BCryptDecrypt` at `0x18001b881`

## pseudocode

```c

```
