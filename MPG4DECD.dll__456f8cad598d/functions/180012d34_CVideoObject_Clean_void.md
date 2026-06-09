# CVideoObject::Clean(void)

- ea: `0x180012d34`
- end: `0x180012dec`
- name: `?Clean@CVideoObject@@QEAAXXZ`
- size: `184`
- prototype: `void __fastcall(CVideoObject *__hidden this)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180009b88`
- `0x180012cf0`
- `0x180012df4`

## callees

- `0x180001450`
- `0x180002388`
- `0x18000b160`
- `0x180012d34`
- `0x18001fc6c`

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
0x180012d34  push    rbx
0x180012d36  push    rsi
0x180012d37  push    rdi
0x180012d38  push    r14
0x180012d3a  sub     rsp, 28h
0x180012d3e  mov     rdi, [rcx+0E0h]
0x180012d45  mov     rbx, rcx
0x180012d48  test    rdi, rdi
0x180012d4b  jz      short loc_180012D62
0x180012d4d  mov     rcx, rdi; this
0x180012d50  call    ?Clean@CPictureCYUV420@@QEAAXXZ; CPictureCYUV420::Clean(void)
0x180012d55  mov     edx, 68h ; 'h'; unsigned __int64
0x180012d5a  mov     rcx, rdi; void *
0x180012d5d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180012d62  mov     rcx, [rbx+0C0h]
0x180012d69  mov     qword ptr [rbx+0E0h], 0
0x180012d74  test    rcx, rcx
0x180012d77  jz      short loc_180012DB6
0x180012d79  lea     r14, [rcx-8]
0x180012d7d  mov     rdi, [r14]
0x180012d80  lea     rax, [rdi+rdi*8]
0x180012d84  lea     rsi, [rcx+rax*8]
0x180012d88  test    rdi, rdi
0x180012d8b  jz      short loc_180012D9F
0x180012d8d  sub     rsi, 48h ; 'H'
0x180012d91  mov     rcx, rsi; this
0x180012d94  call    ?encode@CVideoObject@@UEAAXXZ; CVideoObject::encode(void)
0x180012d99  sub     rdi, 1
0x180012d9d  jnz     short loc_180012D8D
0x180012d9f  mov     rax, [r14]
0x180012da2  mov     rcx, r14; void *
0x180012da5  lea     rdx, [rax+rax*8]
0x180012da9  lea     rdx, ds:8[rdx*8]; unsigned __int64
0x180012db1  call    ??_V@YAXPEAX_K@Z; operator delete[](void *,unsigned __int64)
0x180012db6  mov     rcx, [rbx+0D0h]; void *
0x180012dbd  mov     qword ptr [rbx+0C0h], 0
0x180012dc8  test    rcx, rcx
0x180012dcb  jz      short loc_180012DD7
0x180012dcd  mov     edx, 48h ; 'H'; unsigned __int64
0x180012dd2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180012dd7  mov     qword ptr [rbx+0D0h], 0
0x180012de2  add     rsp, 28h
0x180012de6  pop     r14
0x180012de8  pop     rdi
0x180012de9  pop     rsi
0x180012dea  pop     rbx
0x180012deb  retn
```
