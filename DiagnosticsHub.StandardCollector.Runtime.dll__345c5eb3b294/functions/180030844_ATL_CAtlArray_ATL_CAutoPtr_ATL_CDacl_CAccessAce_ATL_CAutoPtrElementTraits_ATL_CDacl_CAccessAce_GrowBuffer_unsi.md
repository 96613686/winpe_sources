# ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::GrowBuffer(unsigned __int64)

- ea: `0x180030844`
- end: `0x180030933`
- name: `?GrowBuffer@?$CAtlArray@V?$CAutoPtr@VCAccessAce@CDacl@ATL@@@ATL@@V?$CAutoPtrElementTraits@VCAccessAce@CDacl@ATL@@@2@@ATL@@AEAA_N_K@Z`
- size: `239`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18002fb2c`
- `0x180030260`

## callees

- `0x180002604`
- `0x180030844`

## import_xrefs

- `VCRUNTIME140!memmove` at `0x1800308ee`
- `VCRUNTIME140!memmove` at `0x1800308ee`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180030916`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180030916`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x180030922`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x180030922`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800308f7`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800308f7`
- `api-ms-win-crt-heap-l1-1-0!calloc` at `0x180030882`
- `api-ms-win-crt-heap-l1-1-0!calloc` at `0x1800308c1`
- `api-ms-win-crt-heap-l1-1-0!calloc` at `0x180030882`
- `api-ms-win-crt-heap-l1-1-0!calloc` at `0x1800308c1`

## pseudocode

```c
char __fastcall ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::GrowBuffer(
        __int64 a1,
        size_t a2)
{
  size_t v4; // rdx
  bool v5; // zf
  void *v6; // rax
  size_t v7; // rcx
  void *v8; // rax
  void *v9; // rsi
  const void *v11; // rdx
  size_t v12; // r8

  v4 = *(_QWORD *)(a1 + 16);
  if ( a2 <= v4 )
    return 1;
  v5 = *(_QWORD *)a1 == 0;
  _mm_lfence();
  if ( !v5 )
  {
    v7 = *(int *)(a1 + 24);
    if ( !v7 )
    {
      v7 = v4 >> 1;
      if ( a2 - v4 > v4 >> 1 )
        v7 = a2 - v4;
    }
    if ( a2 < v4 + v7 )
      a2 = v4 + v7;
    v8 = calloc(a2, 8u);
    v9 = v8;
    if ( v8 )
    {
      v11 = *(const void **)a1;
      v12 = 8LL * *(_QWORD *)(a1 + 8);
      if ( v12 )
      {
        if ( !v11 )
        {
          *_errno() = 22;
          _invalid_parameter_noinfo();
          ATL::AtlThrowImpl(-2147024809);
        }
        _mm_lfence();
        memmove(v8, v11, v12);
      }
      free(*(void **)a1);
      *(_QWORD *)a1 = v9;
      goto LABEL_18;
    }
    return 0;
  }
  if ( *(int *)(a1 + 24) > a2 )
    a2 = *(int *)(a1 + 24);
  v6 = calloc(a2, 8u);
  *(_QWORD *)a1 = v6;
  if ( !v6 )
    return 0;
LABEL_18:
  *(_QWORD *)(a1 + 16) = a2;
  return 1;
}

```

## disassembly

```asm
0x180030844  mov     [rsp+arg_0], rbx
0x180030849  mov     [rsp+arg_8], rsi
0x18003084e  push    rdi
0x18003084f  sub     rsp, 20h
0x180030853  mov     rdi, rdx
0x180030856  mov     rbx, rcx
0x180030859  mov     rdx, [rcx+10h]
0x18003085d  cmp     rdi, rdx
0x180030860  jbe     loc_180030904
0x180030866  cmp     qword ptr [rcx], 0
0x18003086a  lfence
0x18003086d  jnz     short loc_180030892
0x18003086f  movsxd  rax, dword ptr [rcx+18h]
0x180030873  mov     edx, 8; Size
0x180030878  cmp     rax, rdi
0x18003087b  cmova   rdi, rax
0x18003087f  mov     rcx, rdi; Count
0x180030882  call    cs:__imp_calloc
0x180030888  mov     [rbx], rax
0x18003088b  test    rax, rax
0x18003088e  jz      short loc_1800308CF
0x180030890  jmp     short loc_180030900
0x180030892  movsxd  rcx, dword ptr [rcx+18h]
0x180030896  test    rcx, rcx
0x180030899  jnz     short loc_1800308AE
0x18003089b  mov     rcx, rdx
0x18003089e  mov     rax, rdi
0x1800308a1  shr     rcx, 1
0x1800308a4  sub     rax, rdx
0x1800308a7  cmp     rax, rcx
0x1800308aa  cmova   rcx, rax
0x1800308ae  lea     rax, [rdx+rcx]
0x1800308b2  mov     edx, 8; Size
0x1800308b7  cmp     rdi, rax
0x1800308ba  cmovb   rdi, rax
0x1800308be  mov     rcx, rdi; Count
0x1800308c1  call    cs:__imp_calloc
0x1800308c7  mov     rsi, rax
0x1800308ca  test    rax, rax
0x1800308cd  jnz     short loc_1800308D3
0x1800308cf  xor     al, al
0x1800308d1  jmp     short loc_180030906
0x1800308d3  mov     r8, [rbx+8]
0x1800308d7  mov     rdx, [rbx]; Src
0x1800308da  shl     r8, 3; Size
0x1800308de  test    r8, r8
0x1800308e1  jz      short loc_1800308F4
0x1800308e3  test    rdx, rdx
0x1800308e6  jz      short loc_180030916
0x1800308e8  lfence
0x1800308eb  mov     rcx, rsi; void *
0x1800308ee  call    cs:__imp_memmove
0x1800308f4  mov     rcx, [rbx]; Block
0x1800308f7  call    cs:__imp_free
0x1800308fd  mov     [rbx], rsi
0x180030900  mov     [rbx+10h], rdi
0x180030904  mov     al, 1
0x180030906  mov     rbx, [rsp+28h+arg_0]
0x18003090b  mov     rsi, [rsp+28h+arg_8]
0x180030910  add     rsp, 20h
0x180030914  pop     rdi
0x180030915  retn
0x180030916  call    cs:__imp__errno
0x18003091c  mov     dword ptr [rax], 16h
0x180030922  call    cs:__imp__invalid_parameter_noinfo
0x180030928  mov     ecx, 80070057h; int
0x18003092d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
