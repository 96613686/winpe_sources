# IIS_CRYPTO_EXCHANGE_SERVER::~IIS_CRYPTO_EXCHANGE_SERVER(void)

- ea: `0x180004e6c`
- end: `0x180004eae`
- name: `??1IIS_CRYPTO_EXCHANGE_SERVER@@QEAA@XZ`
- size: `66`
- prototype: `void __fastcall(IIS_CRYPTO_EXCHANGE_SERVER *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180003298`
- `0x180003538`
- `0x1800039d4`

## callees

- `0x180004e6c`
- `0x180005b90`
- `0x180005f28`

## pseudocode

```c
void __fastcall IIS_CRYPTO_EXCHANGE_SERVER::~IIS_CRYPTO_EXCHANGE_SERVER(IIS_CRYPTO_EXCHANGE_SERVER *this)
{
  if ( *((_QWORD *)this + 6) )
  {
    IISCryptoCloseKey();
    *((_QWORD *)this + 6) = 0;
  }
  if ( *((_QWORD *)this + 7) )
  {
    IISCryptoCloseKey();
    *((_QWORD *)this + 7) = 0;
  }
  IIS_CRYPTO_EXCHANGE_BASE::~IIS_CRYPTO_EXCHANGE_BASE(this);
}

```

## disassembly

```asm
0x180004e6c  push    rbx
0x180004e6e  sub     rsp, 20h
0x180004e72  mov     rbx, rcx
0x180004e75  mov     rcx, [rcx+30h]
0x180004e79  test    rcx, rcx
0x180004e7c  jz      short loc_180004E8B
0x180004e7e  call    IISCryptoCloseKey
0x180004e83  mov     qword ptr [rbx+30h], 0
0x180004e8b  mov     rcx, [rbx+38h]
0x180004e8f  test    rcx, rcx
0x180004e92  jz      short loc_180004EA1
0x180004e94  call    IISCryptoCloseKey
0x180004e99  mov     qword ptr [rbx+38h], 0
0x180004ea1  mov     rcx, rbx; this
0x180004ea4  add     rsp, 20h
0x180004ea8  pop     rbx
0x180004ea9  jmp     ??1IIS_CRYPTO_EXCHANGE_BASE@@QEAA@XZ; IIS_CRYPTO_EXCHANGE_BASE::~IIS_CRYPTO_EXCHANGE_BASE(void)
```
