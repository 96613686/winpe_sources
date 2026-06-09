# CVideoObject::Clean(void)

- ea: `0x180012c74`
- end: `0x180012d2c`
- name: `?Clean@CVideoObject@@QEAAXXZ`
- size: `184`
- prototype: `void __fastcall(CVideoObject *__hidden this)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180009ac8`
- `0x180012c30`
- `0x180012d34`

## callees

- `0x180001420`
- `0x1800022cc`
- `0x18000b0a0`
- `0x180012c74`
- `0x18001fbac`

## pseudocode

```c
void __fastcall CVideoObject::Clean(CVideoObject *this)
{
  void *v1; // rdi
  __int64 v3; // rcx
  void *v4; // r14
  __int64 v5; // rdi
  CVideoObject *i; // rsi
  void *v7; // rcx

  v1 = (void *)*((_QWORD *)this + 28);
  if ( v1 )
  {
    CPictureCYUV420::Clean(*((CPictureCYUV420 **)this + 28));
    operator delete(v1);
  }
  v3 = *((_QWORD *)this + 24);
  *((_QWORD *)this + 28) = 0;
  if ( v3 )
  {
    v4 = (void *)(v3 - 8);
    v5 = *(_QWORD *)(v3 - 8);
    for ( i = (CVideoObject *)(v3 + 72 * v5); v5; --v5 )
    {
      i = (CVideoObject *)((char *)i - 72);
      CVideoObject::encode(i);
    }
    operator delete[](v4);
  }
  v7 = (void *)*((_QWORD *)this + 26);
  *((_QWORD *)this + 24) = 0;
  if ( v7 )
    operator delete(v7);
  *((_QWORD *)this + 26) = 0;
}

```

## disassembly

```asm
0x180012c74  push    rbx
0x180012c76  push    rsi
0x180012c77  push    rdi
0x180012c78  push    r14
0x180012c7a  sub     rsp, 28h
0x180012c7e  mov     rdi, [rcx+0E0h]
0x180012c85  mov     rbx, rcx
0x180012c88  test    rdi, rdi
0x180012c8b  jz      short loc_180012CA2
0x180012c8d  mov     rcx, rdi; this
0x180012c90  call    ?Clean@CPictureCYUV420@@QEAAXXZ; CPictureCYUV420::Clean(void)
0x180012c95  mov     edx, 68h ; 'h'; unsigned __int64
0x180012c9a  mov     rcx, rdi; void *
0x180012c9d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180012ca2  mov     rcx, [rbx+0C0h]
0x180012ca9  mov     qword ptr [rbx+0E0h], 0
0x180012cb4  test    rcx, rcx
0x180012cb7  jz      short loc_180012CF6
0x180012cb9  lea     r14, [rcx-8]
0x180012cbd  mov     rdi, [r14]
0x180012cc0  lea     rax, [rdi+rdi*8]
0x180012cc4  lea     rsi, [rcx+rax*8]
0x180012cc8  test    rdi, rdi
0x180012ccb  jz      short loc_180012CDF
0x180012ccd  sub     rsi, 48h ; 'H'
0x180012cd1  mov     rcx, rsi; this
0x180012cd4  call    ?encode@CVideoObject@@UEAAXXZ; CVideoObject::encode(void)
0x180012cd9  sub     rdi, 1
0x180012cdd  jnz     short loc_180012CCD
0x180012cdf  mov     rax, [r14]
0x180012ce2  mov     rcx, r14; void *
0x180012ce5  lea     rdx, [rax+rax*8]
0x180012ce9  lea     rdx, ds:8[rdx*8]; unsigned __int64
0x180012cf1  call    ??_V@YAXPEAX_K@Z; operator delete[](void *,unsigned __int64)
0x180012cf6  mov     rcx, [rbx+0D0h]; void *
0x180012cfd  mov     qword ptr [rbx+0C0h], 0
0x180012d08  test    rcx, rcx
0x180012d0b  jz      short loc_180012D17
0x180012d0d  mov     edx, 48h ; 'H'; unsigned __int64
0x180012d12  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180012d17  mov     qword ptr [rbx+0D0h], 0
0x180012d22  add     rsp, 28h
0x180012d26  pop     r14
0x180012d28  pop     rdi
0x180012d29  pop     rsi
0x180012d2a  pop     rbx
0x180012d2b  retn
```
