# Comms::SecureRpcClient::`vector deleting destructor'(uint)

- ea: `0x1800032b0`
- end: `0x180003321`
- name: `??_ESecureRpcClient@Comms@@UEAAPEAXI@Z`
- size: `113`
- prototype: `Comms::SecureRpcClient *__fastcall(Comms::SecureRpcClient *this, char)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001160`
- `0x180001178`
- `0x180003270`
- `0x1800032b0`

## pseudocode

```c
Comms::SecureRpcClient *__fastcall Comms::SecureRpcClient::`vector deleting destructor'(
        Comms::SecureRpcClient *this,
        char a2)
{
  char *v4; // r14
  __int64 v5; // rbp
  Comms::SecureRpcClient *i; // rdi

  if ( (a2 & 2) != 0 )
  {
    v4 = (char *)this - 8;
    v5 = *((_QWORD *)this - 1);
    for ( i = (Comms::SecureRpcClient *)((char *)this + 16 * v5); v5; --v5 )
    {
      i = (Comms::SecureRpcClient *)((char *)i - 16);
      Comms::SecureRpcClient::~SecureRpcClient(i);
    }
    if ( (a2 & 1) != 0 )
      operator delete(v4);
    return (Comms::SecureRpcClient *)v4;
  }
  else
  {
    Comms::SecureRpcClient::~SecureRpcClient(this);
    if ( (a2 & 1) != 0 )
      operator delete(this);
    return this;
  }
}

```

## disassembly

```asm
0x1800032b0  push    rbx
0x1800032b2  push    rbp
0x1800032b3  push    rsi
0x1800032b4  push    rdi
0x1800032b5  push    r14
0x1800032b7  sub     rsp, 20h
0x1800032bb  mov     esi, edx
0x1800032bd  mov     rbx, rcx
0x1800032c0  test    dl, 2
0x1800032c3  jz      short loc_180003300
0x1800032c5  lea     r14, [rcx-8]
0x1800032c9  mov     rbp, [r14]
0x1800032cc  mov     rdi, rbp
0x1800032cf  shl     rdi, 4
0x1800032d3  add     rdi, rcx
0x1800032d6  test    rbp, rbp
0x1800032d9  jz      short loc_1800032ED
0x1800032db  sub     rdi, 10h
0x1800032df  mov     rcx, rdi; this
0x1800032e2  call    ??1SecureRpcClient@Comms@@UEAA@XZ; Comms::SecureRpcClient::~SecureRpcClient(void)
0x1800032e7  sub     rbp, 1
0x1800032eb  jnz     short loc_1800032DB
0x1800032ed  test    sil, 1
0x1800032f1  jz      short loc_1800032FB
0x1800032f3  mov     rcx, r14; Block
0x1800032f6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800032fb  mov     rax, r14
0x1800032fe  jmp     short loc_180003316
0x180003300  call    ??1SecureRpcClient@Comms@@UEAA@XZ; Comms::SecureRpcClient::~SecureRpcClient(void)
0x180003305  test    sil, 1
0x180003309  jz      short loc_180003313
0x18000330b  mov     rcx, rbx; Block
0x18000330e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003313  mov     rax, rbx
0x180003316  add     rsp, 20h
0x18000331a  pop     r14
0x18000331c  pop     rdi
0x18000331d  pop     rsi
0x18000331e  pop     rbp
0x18000331f  pop     rbx
0x180003320  retn
```
