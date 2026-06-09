# DIGEST_SSPI_SECURITY_CONTEXT::~DIGEST_SSPI_SECURITY_CONTEXT(void)

- ea: `0x180001a38`
- end: `0x180001aca`
- name: `??1DIGEST_SSPI_SECURITY_CONTEXT@@UEAA@XZ`
- size: `146`
- prototype: `void __fastcall(DIGEST_SSPI_SECURITY_CONTEXT *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180001c30`

## callees

- `0x180001a38`
- `0x18000445c`
- `0x1800048d0`

## pseudocode

```c
void __fastcall DIGEST_SSPI_SECURITY_CONTEXT::~DIGEST_SSPI_SECURITY_CONTEXT(DIGEST_SSPI_SECURITY_CONTEXT *this)
{
  struct _SecHandle v2; // xmm6
  struct _SecHandle v3; // [rsp+20h] [rbp-28h] BYREF

  v2 = (struct _SecHandle)*((_OWORD *)this + 2);
  *((_DWORD *)this + 6) = 0;
  *(_QWORD *)this = &DIGEST_SSPI_SECURITY_CONTEXT::`vftable';
  *((_QWORD *)this + 5) = -1;
  *((_QWORD *)this + 4) = -1;
  v3 = v2;
  if ( v2.dwLower != -1
    && _mm_srli_si128((__m128i)v2, 8).m128i_u64[0] != -1
    && (int)DIGEST_CONTEXT_CACHE::AddContextCacheEntry(*((DIGEST_CONTEXT_CACHE **)s_pDigestAuthProvider + 2), &v3) < 0 )
  {
    *((_DWORD *)this + 6) = 1;
    *((struct _SecHandle *)this + 2) = v2;
  }
  *(_QWORD *)this = &SSPI_SECURITY_CONTEXT::`vftable';
  SSPI_SECURITY_CONTEXT::Reset((struct _SecHandle *)this);
}

```

## disassembly

```asm
0x180001a38  push    rbx
0x180001a3a  sub     rsp, 40h
0x180001a3e  mov     rbx, rcx
0x180001a41  movaps  [rsp+48h+var_18], xmm6
0x180001a46  movups  xmm6, xmmword ptr [rcx+20h]
0x180001a4a  lea     rax, ??_7DIGEST_SSPI_SECURITY_CONTEXT@@6B@; const DIGEST_SSPI_SECURITY_CONTEXT::`vftable'
0x180001a51  mov     dword ptr [rcx+18h], 0
0x180001a58  mov     [rcx], rax
0x180001a5b  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180001a5f  movq    rax, xmm6
0x180001a64  mov     [rbx+28h], rcx
0x180001a68  mov     [rbx+20h], rcx
0x180001a6c  movups  xmmword ptr [rsp+48h+var_28.dwLower], xmm6
0x180001a71  cmp     rax, rcx
0x180001a74  jz      short loc_180001AAE
0x180001a76  movdqa  xmm0, xmm6
0x180001a7a  psrldq  xmm0, 8
0x180001a7f  movq    rax, xmm0
0x180001a84  cmp     rax, rcx
0x180001a87  jz      short loc_180001AAE
0x180001a89  mov     rcx, cs:?s_pDigestAuthProvider@@3PEAVDIGEST_AUTH_PROVIDER@@EA; DIGEST_AUTH_PROVIDER * s_pDigestAuthProvider
0x180001a90  lea     rdx, [rsp+48h+var_28]; struct _SecHandle *
0x180001a95  mov     rcx, [rcx+10h]; this
0x180001a99  call    ?AddContextCacheEntry@DIGEST_CONTEXT_CACHE@@QEAAJPEAU_SecHandle@@@Z; DIGEST_CONTEXT_CACHE::AddContextCacheEntry(_SecHandle *)
0x180001a9e  test    eax, eax
0x180001aa0  jns     short loc_180001AAE
0x180001aa2  mov     dword ptr [rbx+18h], 1
0x180001aa9  movdqu  xmmword ptr [rbx+20h], xmm6
0x180001aae  lea     rax, ??_7SSPI_SECURITY_CONTEXT@@6B@; const SSPI_SECURITY_CONTEXT::`vftable'
0x180001ab5  mov     rcx, rbx; this
0x180001ab8  mov     [rbx], rax
0x180001abb  movaps  xmm6, [rsp+48h+var_18]
0x180001ac0  add     rsp, 40h
0x180001ac4  pop     rbx
0x180001ac5  jmp     ?Reset@SSPI_SECURITY_CONTEXT@@QEAAXXZ; SSPI_SECURITY_CONTEXT::Reset(void)
```
