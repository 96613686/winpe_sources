# ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::GrowBuffer(unsigned __int64)

- ea: `0x140012844`
- end: `0x140012930`
- name: `?GrowBuffer@?$CAtlArray@V?$CAutoPtr@VCAccessAce@CDacl@ATL@@@ATL@@V?$CAutoPtrElementTraits@VCAccessAce@CDacl@ATL@@@2@@ATL@@AEAA_N_K@Z`
- size: `236`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x140012610`

## callees

- `0x140002e74`
- `0x140012844`
- `0x140014bc0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x140012913`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x140012913`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x14001291f`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x14001291f`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1400128f4`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1400128f4`
- `api-ms-win-crt-heap-l1-1-0!calloc` at `0x140012882`
- `api-ms-win-crt-heap-l1-1-0!calloc` at `0x1400128c1`
- `api-ms-win-crt-heap-l1-1-0!calloc` at `0x140012882`
- `api-ms-win-crt-heap-l1-1-0!calloc` at `0x1400128c1`

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
  size_t v11; // r8

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
      v11 = 8LL * *(_QWORD *)(a1 + 8);
      if ( v11 )
      {
        if ( !*(_QWORD *)a1 )
        {
          *_errno() = 22;
          _invalid_parameter_noinfo();
          ATL::AtlThrowImpl(-2147024809);
        }
        memcpy_0(v8, *(const void **)a1, v11);
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
0x140012844  mov     [rsp+arg_0], rbx
0x140012849  mov     [rsp+arg_8], rsi
0x14001284e  push    rdi
0x14001284f  sub     rsp, 20h
0x140012853  mov     rdi, rdx
0x140012856  mov     rbx, rcx
0x140012859  mov     rdx, [rcx+10h]
0x14001285d  cmp     rdi, rdx
0x140012860  jbe     loc_140012901
0x140012866  cmp     qword ptr [rcx], 0
0x14001286a  lfence
0x14001286d  jnz     short loc_140012892
0x14001286f  movsxd  rax, dword ptr [rcx+18h]
0x140012873  mov     edx, 8; Size
0x140012878  cmp     rax, rdi
0x14001287b  cmova   rdi, rax
0x14001287f  mov     rcx, rdi; Count
0x140012882  call    cs:__imp_calloc
0x140012888  mov     [rbx], rax
0x14001288b  test    rax, rax
0x14001288e  jz      short loc_1400128CF
0x140012890  jmp     short loc_1400128FD
0x140012892  movsxd  rcx, dword ptr [rcx+18h]
0x140012896  test    rcx, rcx
0x140012899  jnz     short loc_1400128AE
0x14001289b  mov     rcx, rdx
0x14001289e  mov     rax, rdi
0x1400128a1  shr     rcx, 1
0x1400128a4  sub     rax, rdx
0x1400128a7  cmp     rax, rcx
0x1400128aa  cmova   rcx, rax
0x1400128ae  lea     rax, [rdx+rcx]
0x1400128b2  mov     edx, 8; Size
0x1400128b7  cmp     rdi, rax
0x1400128ba  cmovb   rdi, rax
0x1400128be  mov     rcx, rdi; Count
0x1400128c1  call    cs:__imp_calloc
0x1400128c7  mov     rsi, rax
0x1400128ca  test    rax, rax
0x1400128cd  jnz     short loc_1400128D3
0x1400128cf  xor     al, al
0x1400128d1  jmp     short loc_140012903
0x1400128d3  mov     r8, [rbx+8]
0x1400128d7  shl     r8, 3; Size
0x1400128db  test    r8, r8
0x1400128de  jz      short loc_1400128F1
0x1400128e0  cmp     qword ptr [rbx], 0
0x1400128e4  jz      short loc_140012913
0x1400128e6  mov     rdx, [rbx]; Src
0x1400128e9  mov     rcx, rsi; void *
0x1400128ec  call    memcpy_0
0x1400128f1  mov     rcx, [rbx]; Block
0x1400128f4  call    cs:__imp_free
0x1400128fa  mov     [rbx], rsi
0x1400128fd  mov     [rbx+10h], rdi
0x140012901  mov     al, 1
0x140012903  mov     rbx, [rsp+28h+arg_0]
0x140012908  mov     rsi, [rsp+28h+arg_8]
0x14001290d  add     rsp, 20h
0x140012911  pop     rdi
0x140012912  retn
0x140012913  call    cs:__imp__errno
0x140012919  mov     dword ptr [rax], 16h
0x14001291f  call    cs:__imp__invalid_parameter_noinfo
0x140012925  mov     ecx, 80070057h; int
0x14001292a  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
