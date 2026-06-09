# ADM_SECURE_DATA::CleanupCryptoData(void)

- ea: `0x180003298`
- end: `0x180003334`
- name: `?CleanupCryptoData@ADM_SECURE_DATA@@AEAAXXZ`
- size: `156`
- prototype: `void __fastcall(ADM_SECURE_DATA *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1800031f4`
- `0x180003538`
- `0x180003b9c`

## callees

- `0x180001124`
- `0x180003298`
- `0x180004e6c`
- `0x18000560c`

## pseudocode

```c
void __fastcall ADM_SECURE_DATA::CleanupCryptoData(ADM_SECURE_DATA *this)
{
  void *v1; // rdi
  IIS_CRYPTO_EXCHANGE_SERVER *v3; // rdi
  IIS_CRYPTO_STORAGE *v4; // rdi
  IIS_CRYPTO_STORAGE *v5; // rdi

  v1 = (void *)*((_QWORD *)this + 4);
  if ( v1 )
  {
    IIS_CRYPTO_EXCHANGE_SERVER::~IIS_CRYPTO_EXCHANGE_SERVER(*((IIS_CRYPTO_EXCHANGE_SERVER **)this + 4));
    operator delete(v1);
  }
  v3 = (IIS_CRYPTO_EXCHANGE_SERVER *)*((_QWORD *)this + 5);
  *((_QWORD *)this + 4) = 0;
  if ( v3 )
  {
    IIS_CRYPTO_EXCHANGE_SERVER::~IIS_CRYPTO_EXCHANGE_SERVER(v3);
    operator delete(v3);
  }
  v4 = (IIS_CRYPTO_STORAGE *)*((_QWORD *)this + 6);
  *((_QWORD *)this + 5) = 0;
  if ( v4 )
  {
    IIS_CRYPTO_STORAGE::~IIS_CRYPTO_STORAGE(v4);
    operator delete(v4);
  }
  v5 = (IIS_CRYPTO_STORAGE *)*((_QWORD *)this + 7);
  *((_QWORD *)this + 6) = 0;
  if ( v5 )
  {
    IIS_CRYPTO_STORAGE::~IIS_CRYPTO_STORAGE(v5);
    operator delete(v5);
  }
  *((_QWORD *)this + 7) = 0;
}

```

## disassembly

```asm
0x180003298  mov     [rsp+arg_0], rbx
0x18000329d  push    rdi
0x18000329e  sub     rsp, 20h
0x1800032a2  mov     rdi, [rcx+20h]
0x1800032a6  mov     rbx, rcx
0x1800032a9  test    rdi, rdi
0x1800032ac  jz      short loc_1800032BE
0x1800032ae  mov     rcx, rdi; this
0x1800032b1  call    ??1IIS_CRYPTO_EXCHANGE_SERVER@@QEAA@XZ; IIS_CRYPTO_EXCHANGE_SERVER::~IIS_CRYPTO_EXCHANGE_SERVER(void)
0x1800032b6  mov     rcx, rdi; Block
0x1800032b9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800032be  mov     rdi, [rbx+28h]
0x1800032c2  mov     qword ptr [rbx+20h], 0
0x1800032ca  test    rdi, rdi
0x1800032cd  jz      short loc_1800032DF
0x1800032cf  mov     rcx, rdi; this
0x1800032d2  call    ??1IIS_CRYPTO_EXCHANGE_SERVER@@QEAA@XZ; IIS_CRYPTO_EXCHANGE_SERVER::~IIS_CRYPTO_EXCHANGE_SERVER(void)
0x1800032d7  mov     rcx, rdi; Block
0x1800032da  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800032df  mov     rdi, [rbx+30h]
0x1800032e3  mov     qword ptr [rbx+28h], 0
0x1800032eb  test    rdi, rdi
0x1800032ee  jz      short loc_180003300
0x1800032f0  mov     rcx, rdi; this
0x1800032f3  call    ??1IIS_CRYPTO_STORAGE@@QEAA@XZ; IIS_CRYPTO_STORAGE::~IIS_CRYPTO_STORAGE(void)
0x1800032f8  mov     rcx, rdi; Block
0x1800032fb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003300  mov     rdi, [rbx+38h]
0x180003304  mov     qword ptr [rbx+30h], 0
0x18000330c  test    rdi, rdi
0x18000330f  jz      short loc_180003321
0x180003311  mov     rcx, rdi; this
0x180003314  call    ??1IIS_CRYPTO_STORAGE@@QEAA@XZ; IIS_CRYPTO_STORAGE::~IIS_CRYPTO_STORAGE(void)
0x180003319  mov     rcx, rdi; Block
0x18000331c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003321  mov     qword ptr [rbx+38h], 0
0x180003329  mov     rbx, [rsp+28h+arg_0]
0x18000332e  add     rsp, 20h
0x180003332  pop     rdi
0x180003333  retn
```
