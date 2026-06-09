# CERT_1TO1_MAP_RULE::~CERT_1TO1_MAP_RULE(void)

- ea: `0x180001af8`
- end: `0x180001b67`
- name: `??1CERT_1TO1_MAP_RULE@@QEAA@XZ`
- size: `111`
- prototype: `void __fastcall(CERT_1TO1_MAP_RULE *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180003470`
- `0x180003f3c`
- `0x1800041f0`

## callees

- `0x180001af8`

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x180001b4c`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180001b4c`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180001b60`
- `CRYPT32!CertFreeCertificateContext` at `0x180001b38`
- `CRYPT32!CertFreeCertificateContext` at `0x180001b38`

## pseudocode

```c
void __fastcall CERT_1TO1_MAP_RULE::~CERT_1TO1_MAP_RULE(CERT_1TO1_MAP_RULE *this)
{
  STRU *v1; // rdi
  int v3; // eax
  bool v4; // zf
  __int64 v5; // rdx
  _BYTE *v6; // rax
  const CERT_CONTEXT *v7; // rcx

  v1 = (CERT_1TO1_MAP_RULE *)((char *)this + 128);
  v3 = *((_DWORD *)this + 44);
  if ( v3 )
  {
    v4 = 2 * v3 == 0;
    v5 = (unsigned int)(2 * v3);
    v6 = (_BYTE *)*((_QWORD *)this + 20);
    if ( !v4 )
    {
      do
      {
        *v6++ = 0;
        --v5;
      }
      while ( v5 );
    }
  }
  v7 = (const CERT_CONTEXT *)*((_QWORD *)this + 34);
  if ( v7 )
  {
    CertFreeCertificateContext(v7);
    *((_QWORD *)this + 34) = 0;
  }
  STRU::~STRU(v1);
  STRU::~STRU((CERT_1TO1_MAP_RULE *)((char *)this + 8));
}

```

## disassembly

```asm
0x180001af8  mov     [rsp+arg_0], rbx
0x180001afd  push    rdi
0x180001afe  sub     rsp, 20h
0x180001b02  lea     rdi, [rcx+80h]
0x180001b09  mov     rbx, rcx
0x180001b0c  mov     eax, [rdi+30h]
0x180001b0f  test    eax, eax
0x180001b11  jz      short loc_180001B2C
0x180001b13  add     eax, eax
0x180001b15  mov     edx, eax
0x180001b17  mov     rax, [rcx+0A0h]
0x180001b1e  jz      short loc_180001B2C
0x180001b20  mov     byte ptr [rax], 0
0x180001b23  inc     rax
0x180001b26  sub     rdx, 1
0x180001b2a  jnz     short loc_180001B20
0x180001b2c  mov     rcx, [rcx+110h]; pCertContext
0x180001b33  test    rcx, rcx
0x180001b36  jz      short loc_180001B49
0x180001b38  call    cs:__imp_CertFreeCertificateContext
0x180001b3e  mov     qword ptr [rbx+110h], 0
0x180001b49  mov     rcx, rdi
0x180001b4c  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180001b52  lea     rcx, [rbx+8]
0x180001b56  mov     rbx, [rsp+28h+arg_0]
0x180001b5b  add     rsp, 20h
0x180001b5f  pop     rdi
0x180001b60  jmp     cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
```
