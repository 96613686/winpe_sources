# DIGEST_AUTH_PROVIDER::DoesApply(IHttpContext *,int *,INativeSectionException * *)

- ea: `0x180002d90`
- end: `0x180002f3c`
- name: `?DoesApply@DIGEST_AUTH_PROVIDER@@UEAAJPEAVIHttpContext@@PEAHPEAPEAVINativeSectionException@@@Z`
- size: `428`
- prototype: `__int64 __fastcall(DIGEST_AUTH_PROVIDER *__hidden this, struct IHttpContext *, int *, struct INativeSectionException **)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x180002d90`
- `0x180007010`

## import_xrefs

- `msvcrt!_strnicmp` at `0x180002dfd`
- `msvcrt!_strnicmp` at `0x180002dfd`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180002e3c`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180002e46`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180002e3c`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180002e46`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x180002e94`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x180002e94`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180002e53`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180002e53`

## pseudocode

```c
__int64 __fastcall DIGEST_AUTH_PROVIDER::DoesApply(
        DIGEST_AUTH_PROVIDER *this,
        struct IHttpContext *a2,
        int *a3,
        struct INativeSectionException **a4)
{
  __int64 v7; // rax
  const char *v8; // rax
  const char *v9; // rbp
  __int64 v10; // rbx
  int v11; // r14d
  _BYTE *i; // rcx
  __int64 v13; // rdx
  __int64 v14; // rax
  int v15; // esi

  if ( !a3 )
    return 2147942487LL;
  v7 = (*(__int64 (__fastcall **)(struct IHttpContext *, struct IHttpContext *, int *, struct INativeSectionException **))(*(_QWORD *)a2 + 24LL))(
         a2,
         a2,
         a3,
         a4);
  *a3 = 0;
  v8 = (const char *)(*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v7 + 16LL))(v7, 24);
  v9 = v8;
  if ( v8 && !_strnicmp(v8, "Digest", 6u) )
  {
    v10 = (*(__int64 (__fastcall **)(struct IHttpContext *, __int64))(*(_QWORD *)a2 + 144LL))(a2, 216);
    if ( !v10 )
      return 2147942408LL;
    *(_QWORD *)v10 = &AUTH_REQUEST_CONTEXT::`vftable';
    STRA::STRA((STRA *)(v10 + 8));
    STRA::STRA((STRA *)(v10 + 72));
    STRU::STRU((STRU *)(v10 + 136));
    *(_QWORD *)(v10 + 64) = 0;
    *(_QWORD *)v10 = &AUTH_REQUEST_CONTEXT::`vftable';
    *(_DWORD *)(v10 + 128) = 0;
    *(_QWORD *)(v10 + 192) = 0;
    *(_DWORD *)(v10 + 208) = 0;
    v11 = STRA::Copy((STRA *)(v10 + 8), v9, 6u);
    if ( v11 < 0 )
    {
      (**(void (__fastcall ***)(__int64))v10)(v10);
      return (unsigned int)v11;
    }
    for ( i = v9 + 6; *i <= 0x20u; ++i )
    {
      v13 = 0x100002200LL;
      if ( !_bittest64(&v13, (char)*i) )
        break;
    }
    *(_QWORD *)(v10 + 64) = i;
    v14 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 56LL))(a2);
    v15 = (*(__int64 (__fastcall **)(__int64, __int64, void *))(*(_QWORD *)v14 + 8LL))(v14, v10, s_pModuleContext);
    if ( v15 < 0 )
    {
      (**(void (__fastcall ***)(__int64))v10)(v10);
      return (unsigned int)v15;
    }
    *a3 = 1;
  }
  else
  {
    *a3 = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x180002d90  push    rbx
0x180002d92  push    rbp
0x180002d93  push    rsi
0x180002d94  push    rdi
0x180002d95  push    r14
0x180002d97  sub     rsp, 20h
0x180002d9b  mov     rdi, r8
0x180002d9e  mov     rsi, rdx
0x180002da1  test    r8, r8
0x180002da4  jnz     short loc_180002DB0
0x180002da6  mov     eax, 80070057h
0x180002dab  jmp     loc_180002F31
0x180002db0  mov     rax, [rdx]
0x180002db3  mov     rcx, rsi
0x180002db6  mov     rax, [rax+18h]
0x180002dba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002dbf  mov     r9, rax
0x180002dc2  mov     dword ptr [rdi], 0
0x180002dc8  xor     r8d, r8d
0x180002dcb  mov     rcx, [rax]
0x180002dce  lea     edx, [r8+18h]
0x180002dd2  mov     rax, [rcx+10h]
0x180002dd6  mov     rcx, r9
0x180002dd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002dde  mov     rbp, rax
0x180002de1  test    rax, rax
0x180002de4  jz      loc_180002F29
0x180002dea  mov     r14d, 6
0x180002df0  lea     rdx, String2; "Digest"
0x180002df7  mov     r8d, r14d; MaxCount
0x180002dfa  mov     rcx, rax; String1
0x180002dfd  call    cs:__imp__strnicmp
0x180002e03  test    eax, eax
0x180002e05  jnz     loc_180002F29
0x180002e0b  mov     rcx, [rsi]
0x180002e0e  mov     edx, 0D8h
0x180002e13  mov     rax, [rcx+90h]
0x180002e1a  mov     rcx, rsi
0x180002e1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e22  mov     rbx, rax
0x180002e25  test    rax, rax
0x180002e28  jz      loc_180002F22
0x180002e2e  lea     rax, ??_7AUTH_REQUEST_CONTEXT@@6B@; const AUTH_REQUEST_CONTEXT::`vftable'
0x180002e35  lea     rcx, [rbx+8]
0x180002e39  mov     [rbx], rax
0x180002e3c  call    cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x180002e42  lea     rcx, [rbx+48h]
0x180002e46  call    cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x180002e4c  lea     rcx, [rbx+88h]
0x180002e53  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180002e59  lea     rax, ??_7AUTH_REQUEST_CONTEXT@@6B@; const AUTH_REQUEST_CONTEXT::`vftable'
0x180002e60  mov     qword ptr [rbx+40h], 0
0x180002e68  lea     rcx, [rbx+8]
0x180002e6c  mov     [rbx], rax
0x180002e6f  mov     r8d, r14d
0x180002e72  mov     dword ptr [rbx+80h], 0
0x180002e7c  mov     rdx, rbp
0x180002e7f  mov     qword ptr [rbx+0C0h], 0
0x180002e8a  mov     dword ptr [rbx+0D0h], 0
0x180002e94  call    cs:__imp_?Copy@STRA@@QEAAJPEBDK@Z; STRA::Copy(char const *,ulong)
0x180002e9a  mov     r14d, eax
0x180002e9d  test    eax, eax
0x180002e9f  jns     short loc_180002EB4
0x180002ea1  mov     rcx, [rbx]
0x180002ea4  mov     rax, [rcx]
0x180002ea7  mov     rcx, rbx
0x180002eaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002eaf  mov     eax, r14d
0x180002eb2  jmp     short loc_180002F31
0x180002eb4  lea     rcx, [rbp+6]
0x180002eb8  cmp     byte ptr [rcx], 20h ; ' '
0x180002ebb  ja      short loc_180002ED6
0x180002ebd  movsx   rax, byte ptr [rcx]
0x180002ec1  mov     rdx, 100002200h
0x180002ecb  bt      rdx, rax
0x180002ecf  jnb     short loc_180002ED6
0x180002ed1  inc     rcx
0x180002ed4  jmp     short loc_180002EB8
0x180002ed6  mov     [rbx+40h], rcx
0x180002eda  mov     rcx, rsi
0x180002edd  mov     rax, [rsi]
0x180002ee0  mov     rax, [rax+38h]
0x180002ee4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ee9  mov     r8, cs:?s_pModuleContext@@3PEAXEA; void * s_pModuleContext
0x180002ef0  mov     rcx, rax
0x180002ef3  mov     rdx, [rax]
0x180002ef6  mov     rax, [rdx+8]
0x180002efa  mov     rdx, rbx
0x180002efd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f02  mov     esi, eax
0x180002f04  test    eax, eax
0x180002f06  jns     short loc_180002F1A
0x180002f08  mov     rdx, [rbx]
0x180002f0b  mov     rcx, rbx
0x180002f0e  mov     rax, [rdx]
0x180002f11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f16  mov     eax, esi
0x180002f18  jmp     short loc_180002F31
0x180002f1a  mov     dword ptr [rdi], 1
0x180002f20  jmp     short loc_180002F2F
0x180002f22  mov     eax, 80070008h
0x180002f27  jmp     short loc_180002F31
0x180002f29  mov     dword ptr [rdi], 0
0x180002f2f  xor     eax, eax
0x180002f31  add     rsp, 20h
0x180002f35  pop     r14
0x180002f37  pop     rdi
0x180002f38  pop     rsi
0x180002f39  pop     rbp
0x180002f3a  pop     rbx
0x180002f3b  retn
```
