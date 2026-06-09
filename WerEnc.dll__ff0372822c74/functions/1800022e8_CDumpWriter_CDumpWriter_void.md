# CDumpWriter::~CDumpWriter(void)

- ea: `0x1800022e8`
- end: `0x180002337`
- name: `??1CDumpWriter@@QEAA@XZ`
- size: `79`
- prototype: `void __fastcall(CDumpWriter *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800022b8`
- `0x180002440`

## callees

- `0x1800022e8`

## import_xrefs

- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800022fc`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18000230d`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800022fc`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18000230d`
- `bcrypt!BCryptDestroyKey` at `0x18000231c`
- `bcrypt!BCryptDestroyKey` at `0x18000232b`
- `bcrypt!BCryptDestroyKey` at `0x18000231c`
- `bcrypt!BCryptDestroyKey` at `0x18000232b`

## pseudocode

```c
void __fastcall CDumpWriter::~CDumpWriter(CDumpWriter *this)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx

  v2 = (void *)*((_QWORD *)this + 10);
  if ( v2 )
    BCryptCloseAlgorithmProvider(v2, 0);
  v3 = (void *)*((_QWORD *)this + 9);
  if ( v3 )
    BCryptCloseAlgorithmProvider(v3, 0);
  v4 = (void *)*((_QWORD *)this + 11);
  if ( v4 )
    BCryptDestroyKey(v4);
  v5 = (void *)*((_QWORD *)this + 12);
  if ( v5 )
    BCryptDestroyKey(v5);
}

```

## disassembly

```asm
0x1800022e8  push    rbx
0x1800022ea  sub     rsp, 20h
0x1800022ee  mov     rbx, rcx
0x1800022f1  mov     rcx, [rcx+50h]; hAlgorithm
0x1800022f5  test    rcx, rcx
0x1800022f8  jz      short loc_180002302
0x1800022fa  xor     edx, edx; dwFlags
0x1800022fc  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180002302  mov     rcx, [rbx+48h]; hAlgorithm
0x180002306  test    rcx, rcx
0x180002309  jz      short loc_180002313
0x18000230b  xor     edx, edx; dwFlags
0x18000230d  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180002313  mov     rcx, [rbx+58h]; hKey
0x180002317  test    rcx, rcx
0x18000231a  jz      short loc_180002322
0x18000231c  call    cs:__imp_BCryptDestroyKey
0x180002322  mov     rcx, [rbx+60h]; hKey
0x180002326  test    rcx, rcx
0x180002329  jz      short loc_180002331
0x18000232b  call    cs:__imp_BCryptDestroyKey
0x180002331  add     rsp, 20h
0x180002335  pop     rbx
0x180002336  retn
```
