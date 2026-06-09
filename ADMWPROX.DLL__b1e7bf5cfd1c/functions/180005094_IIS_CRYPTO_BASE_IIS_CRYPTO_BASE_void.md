# IIS_CRYPTO_BASE::~IIS_CRYPTO_BASE(void)

- ea: `0x180005094`
- end: `0x1800050e9`
- name: `??1IIS_CRYPTO_BASE@@QEAA@XZ`
- size: `85`
- prototype: `void __fastcall(IIS_CRYPTO_BASE *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000560c`
- `0x180005b90`

## callees

- `0x180004e28`
- `0x180005094`
- `0x180005f28`

## pseudocode

```c
void __fastcall IIS_CRYPTO_BASE::~IIS_CRYPTO_BASE(IIS_CRYPTO_BASE *this)
{
  HCRYPTKEY v2; // rcx
  HCRYPTKEY v3; // rcx

  v2 = *((_QWORD *)this + 3);
  if ( v2 )
  {
    IISCryptoCloseKey(v2);
    *((_QWORD *)this + 3) = 0;
  }
  v3 = *((_QWORD *)this + 2);
  if ( v3 )
  {
    IISCryptoCloseKey(v3);
    *((_QWORD *)this + 2) = 0;
  }
  if ( *((_DWORD *)this + 2) )
  {
    if ( *(_QWORD *)this )
    {
      IISCryptoCloseContainer();
      *(_QWORD *)this = 0;
    }
  }
}

```

## disassembly

```asm
0x180005094  push    rbx
0x180005096  sub     rsp, 20h
0x18000509a  mov     rbx, rcx
0x18000509d  mov     rcx, [rcx+18h]
0x1800050a1  test    rcx, rcx
0x1800050a4  jz      short loc_1800050B3
0x1800050a6  call    IISCryptoCloseKey
0x1800050ab  mov     qword ptr [rbx+18h], 0
0x1800050b3  mov     rcx, [rbx+10h]
0x1800050b7  test    rcx, rcx
0x1800050ba  jz      short loc_1800050C9
0x1800050bc  call    IISCryptoCloseKey
0x1800050c1  mov     qword ptr [rbx+10h], 0
0x1800050c9  cmp     dword ptr [rbx+8], 0
0x1800050cd  jz      short loc_1800050E3
0x1800050cf  mov     rcx, [rbx]
0x1800050d2  test    rcx, rcx
0x1800050d5  jz      short loc_1800050E3
0x1800050d7  call    IISCryptoCloseContainer
0x1800050dc  mov     qword ptr [rbx], 0
0x1800050e3  add     rsp, 20h
0x1800050e7  pop     rbx
0x1800050e8  retn
```
