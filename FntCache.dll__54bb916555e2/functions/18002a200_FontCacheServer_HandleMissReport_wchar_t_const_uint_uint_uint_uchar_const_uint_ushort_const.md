# FontCacheServer::HandleMissReport(wchar_t const *,uint,uint,uint,uchar const *,uint,ushort const *)

- ea: `0x18002a200`
- end: `0x18002a375`
- name: `?HandleMissReport@FontCacheServer@@UEAAJPEB_WIIIPEBEIPEBG@Z`
- size: `373`
- prototype: `__int64 __usercall@<rax>(FontCacheServer *__hidden this@<rcx>, const wchar_t *Src@<rdx>, unsigned int@<r8d>, unsigned int@<r9d>, unsigned int, const unsigned __int8 *, unsigned int, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `19`
- tags: `loader_planting`

## callees

- `0x180028c50`
- `0x18002a200`
- `0x18002a37c`
- `0x18006c760`
- `0x18006c870`
- `0x18006c9f0`
- `0x18006cc20`
- `0x18008bec0`
- `0x18008ced0`
- `0x180091a50`
- `0x18009e420`
- `0x1800a6e00`
- `0x1800a7f30`
- `0x1800a8db0`
- `0x1800aaa58`
- `0x1800ab0aa`
- `0x1800ab168`
- `0x1800c7d10`
- `0x1800e6010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18002a2a0`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18002a2a0`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall FontCacheServer::HandleMissReport(
        struct IDWriteFontFileLoader **this,
        const wchar_t *Src,
        __int64 a3,
        __int64 a4,
        unsigned int a5,
        const unsigned __int8 *a6,
        unsigned int a7,
        const unsigned __int16 *a8)
{
  int v8; // r13d
  unsigned __int64 v11; // rbx
  __int64 v12; // rcx
  unsigned __int64 v13; // rax
  unsigned __int64 v14; // rcx
  _DWORD *v15; // rax
  __int64 v16; // rdx
  struct DWrite::RefString::Data *v17; // rdi
  size_t v18; // r8
  void *v19; // rcx
  unsigned __int64 v20; // rax
  struct IExceptionHandler *v21; // rcx
  struct DWrite::RefString::Data *v23; // [rsp+30h] [rbp-48h] BYREF
  ServerCacheContext *v24; // [rsp+38h] [rbp-40h] BYREF

  v8 = a3;
  v11 = -1;
  do
    ++v11;
  while ( Src[v11] );
  try
  {
    if ( v11 )
    {
      if ( v11 > 0xFFFFFFFF )
        SafeIntExceptionHandler<Exception>::SafeIntOnOverflow(this, 0xFFFFFFFFLL, a3, a4);
      v12 = 2LL * (unsigned int)v11;
      if ( !is_mul_ok(2u, v11) )
        SafeIntExceptionHandler<Exception>::SafeIntOnOverflow(v12, 0xFFFFFFFFLL, a3, a4);
      v13 = (unsigned int)v12;
      v14 = (unsigned int)v12 + 10LL;
      if ( v14 < v13 || v14 > 0xFFFFFFFF )
        SafeIntExceptionHandler<Exception>::SafeIntOnOverflow(v14, 0xFFFFFFFFLL, a3, a4);
      v15 = operator new((unsigned int)v14);
      v17 = (struct DWrite::RefString::Data *)v15;
      *v15 = 1;
      v15[1] = v11;
      if ( Src )
      {
        v18 = 2 * v11;
        if ( 2 * v11 )
        {
          v19 = v15 + 2;
          if ( v15 == (_DWORD *)-8LL )
          {
            *(_DWORD *)_o__errno(v19, v16, v18) = 22;
            invalid_parameter_noinfo();
          }
          else
          {
            memcpy_0(v19, Src, v18);
          }
        }
      }
      *((_WORD *)v17 + v11 + 4) = 0;
    }
    else
    {
      v17 = (struct DWrite::RefString::Data *)&DWrite::RefString::empty_;
    }
    v23 = v17;
    FontCacheServer::GetPerUserContext(this, &v24, (__int64)&v23);
    DWrite::RefString::DecrementRef(v23);
    v20 = (unsigned int)(v8 - 1);
    if ( v20 < 0xB )
      ((void (__fastcall *)(ServerCacheContext *, const unsigned __int8 *, _QWORD, const unsigned __int16 *, unsigned int))(&g_asyncElementConstructionProcedures)[v20])(
        v24,
        a6,
        a5,
        a8,
        a7);
    v21 = v24;
    if ( v24 )
      (*(void (__fastcall **)(ServerCacheContext *))(*(_QWORD *)v24 + 16LL))(v24);
  }
  catch ( ... )
  {
    MapExceptionToHresult(v21);
  }
  return 0;
}

```

## disassembly

```asm
0x18002a200  push    rbx
0x18002a202  push    rsi
0x18002a203  push    rdi
0x18002a204  push    r12
0x18002a206  push    r13
0x18002a208  push    r14
0x18002a20a  push    r15
0x18002a20c  sub     rsp, 40h
0x18002a210  mov     r13d, r8d
0x18002a213  mov     r14, rdx
0x18002a216  mov     r12, rcx
0x18002a219  xor     esi, esi
0x18002a21b  mov     r15d, esi
0x18002a21e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002a222  inc     rbx
0x18002a225  cmp     [rdx+rbx*2], si
0x18002a229  jnz     short loc_18002A222
0x18002a22b  test    rbx, rbx
0x18002a22e  jz      loc_18002A357
0x18002a234  mov     edx, 0FFFFFFFFh
0x18002a239  cmp     rbx, rdx
0x18002a23c  ja      loc_18002A368
0x18002a242  mov     esi, ebx
0x18002a244  mov     ecx, ebx
0x18002a246  add     rcx, rcx
0x18002a249  mov     rax, rcx
0x18002a24c  shr     rax, 20h
0x18002a250  test    eax, eax
0x18002a252  jnz     loc_18002A363
0x18002a258  mov     eax, ecx
0x18002a25a  lea     rcx, [rax+0Ah]
0x18002a25e  cmp     rcx, rax
0x18002a261  jb      loc_18002A352
0x18002a267  cmp     rcx, rdx
0x18002a26a  ja      loc_18002A352
0x18002a270  mov     ecx, ecx; Size
0x18002a272  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002a277  mov     rdi, rax
0x18002a27a  mov     dword ptr [rax], 1
0x18002a280  mov     [rax+4], esi
0x18002a283  xor     esi, esi
0x18002a285  test    r14, r14
0x18002a288  jz      short loc_18002A2B1
0x18002a28a  lea     r8, [rbx+rbx]; Size
0x18002a28e  test    r8, r8
0x18002a291  jz      short loc_18002A2B1
0x18002a293  lea     rcx, [rax+8]; void *
0x18002a297  test    rcx, rcx
0x18002a29a  jnz     loc_18002A345
0x18002a2a0  call    cs:__imp__o__errno
0x18002a2a6  mov     dword ptr [rax], 16h
0x18002a2ac  call    _invalid_parameter_noinfo
0x18002a2b1  mov     [rdi+rbx*2+8], si
0x18002a2b6  mov     [rsp+78h+var_48], rdi
0x18002a2bb  lea     r8, [rsp+78h+var_48]
0x18002a2c0  lea     rdx, [rsp+78h+var_40]
0x18002a2c5  mov     rcx, r12; this
0x18002a2c8  call    ?GetPerUserContext@FontCacheServer@@AEAA?AV?$ComPtr@VServerSidePerUserContext@@@@AEBVRefString@DWrite@@@Z; FontCacheServer::GetPerUserContext(DWrite::RefString const &)
0x18002a2cd  nop
0x18002a2ce  mov     rcx, [rsp+78h+var_48]; struct DWrite::RefString::Data *
0x18002a2d3  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x18002a2d8  lea     eax, [r13-1]
0x18002a2dc  cmp     rax, 0Bh
0x18002a2e0  jnb     short loc_18002A31B
0x18002a2e2  lea     r10, ?g_asyncElementConstructionProcedures@@3QBQ6AJPEAVServerCacheContext@@PEBXIPEBGI@ZB; long (*const near * const g_asyncElementConstructionProcedures)(ServerCacheContext *,void const *,uint,ushort const *,uint)
0x18002a2e9  mov     ecx, [rsp+78h+arg_30]
0x18002a2f0  mov     [rsp+78h+var_58], ecx; unsigned int
0x18002a2f4  mov     r9, [rsp+78h+arg_38]
0x18002a2fc  mov     r8d, [rsp+78h+arg_20]
0x18002a304  mov     rdx, [rsp+78h+arg_28]; unsigned int *
0x18002a30c  mov     rcx, [rsp+78h+var_40]; this
0x18002a311  mov     rax, ds:(?g_asyncElementConstructionProcedures@@3QBQ6AJPEAVServerCacheContext@@PEBXIPEBGI@ZB - 1800E7340h)[r10+rax*8]; long (*const near * const g_asyncElementConstructionProcedures)(ServerCacheContext *,void const *,uint,ushort const *,uint)
0x18002a315  call    _guard_dispatch_icall$thunk$10345483385596137414; GlyphDataElement<GlyphOutlineLayout,GlyphOutlineRasterizationParameters,GlyphOutlineRasterizationState>::BeginAddElementFromKey(ServerCacheContext *,void const *,uint,ushort const *,uint)
0x18002a31a  nop
0x18002a31b  mov     rcx, [rsp+78h+var_40]
0x18002a320  test    rcx, rcx
0x18002a323  jz      short loc_18002A332
0x18002a325  mov     rax, [rcx]
0x18002a328  mov     rax, [rax+10h]
0x18002a32c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a331  nop
0x18002a332  mov     eax, r15d
0x18002a335  add     rsp, 40h
0x18002a339  pop     r15
0x18002a33b  pop     r14
0x18002a33d  pop     r13
0x18002a33f  pop     r12
0x18002a341  pop     rdi
0x18002a342  pop     rsi
0x18002a343  pop     rbx
0x18002a344  retn
0x18002a345  mov     rdx, r14; Src
0x18002a348  call    memcpy_0
0x18002a34d  jmp     loc_18002A2B1
0x18002a352  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VException@@@@SAXXZ; SafeIntExceptionHandler<Exception>::SafeIntOnOverflow(void)
0x18002a357  lea     rdi, ?empty_@RefString@DWrite@@0UData@12@A; DWrite::RefString::Data DWrite::RefString::empty_
0x18002a35e  jmp     loc_18002A2B6
0x18002a363  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VException@@@@SAXXZ; SafeIntExceptionHandler<Exception>::SafeIntOnOverflow(void)
0x18002a368  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VException@@@@SAXXZ; SafeIntExceptionHandler<Exception>::SafeIntOnOverflow(void)
0x18002a36e  mov     r15d, dword ptr [rsp+78h+var_48]
0x18002a373  jmp     short loc_18002A332
```
