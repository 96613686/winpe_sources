# CPathCache::CreateCache(_PATHOBJ *)

- ea: `0x180069264`
- end: `0x18006930c`
- name: `?CreateCache@CPathCache@@QEAAHPEAU_PATHOBJ@@@Z`
- size: `168`
- prototype: `__int64 __fastcall(CPathCache *__hidden this, PATHOBJ *ppo)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800699c0`

## callees

- `0x180069264`
- `0x180069400`
- `0x1800694a4`

## import_xrefs

- `GDI32!PATHOBJ_bEnum` at `0x1800692b3`
- `GDI32!PATHOBJ_bEnum` at `0x1800692b3`
- `GDI32!PATHOBJ_vEnumStart` at `0x1800692a5`
- `GDI32!PATHOBJ_vEnumStart` at `0x1800692a5`

## pseudocode

```c
__int64 __fastcall CPathCache::CreateCache(CPathCache *this, PATHOBJ *ppo)
{
  BOOL v4; // esi
  CPathCache *v5; // rcx
  struct CPathCache::CSubPath *v6; // rax
  PATHDATA ppd; // [rsp+20h] [rbp-18h] BYREF

  if ( *((_DWORD *)this + 4) )
    CPathCache::DeleteCache(this);
  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  ppd = 0;
  *((_DWORD *)this + 4) = 1;
  PATHOBJ_vEnumStart(ppo);
  while ( 1 )
  {
    v4 = PATHOBJ_bEnum(ppo, &ppd);
    v6 = CPathCache::CreateSubPath(v5, &ppd);
    if ( !v6 )
      break;
    if ( *(_QWORD *)this )
      *(_QWORD *)(*((_QWORD *)this + 1) + 16LL) = v6;
    else
      *(_QWORD *)this = v6;
    *((_QWORD *)this + 1) = v6;
    if ( !v4 )
    {
      *((_QWORD *)this + 1) = 0;
      return 1;
    }
  }
  CPathCache::DeleteCache(this);
  return 0;
}

```

## disassembly

```asm
0x180069264  mov     [rsp+arg_0], rbx
0x180069269  mov     [rsp+arg_8], rsi
0x18006926e  push    rdi
0x18006926f  sub     rsp, 30h
0x180069273  cmp     dword ptr [rcx+10h], 0
0x180069277  mov     rdi, rdx
0x18006927a  mov     rbx, rcx
0x18006927d  jz      short loc_180069284
0x18006927f  call    ?DeleteCache@CPathCache@@QEAAHXZ; CPathCache::DeleteCache(void)
0x180069284  xorps   xmm0, xmm0
0x180069287  mov     qword ptr [rbx], 0
0x18006928e  mov     rcx, rdi; ppo
0x180069291  mov     qword ptr [rbx+8], 0
0x180069299  movups  xmmword ptr [rsp+38h+ppd.flags], xmm0
0x18006929e  mov     dword ptr [rbx+10h], 1
0x1800692a5  call    cs:__imp_PATHOBJ_vEnumStart
0x1800692ab  lea     rdx, [rsp+38h+ppd]; ppd
0x1800692b0  mov     rcx, rdi; ppo
0x1800692b3  call    cs:__imp_PATHOBJ_bEnum
0x1800692b9  lea     rdx, [rsp+38h+ppd]; struct _PATHDATA *
0x1800692be  mov     esi, eax
0x1800692c0  call    ?CreateSubPath@CPathCache@@AEAAPEAUCSubPath@1@PEAU_PATHDATA@@@Z; CPathCache::CreateSubPath(_PATHDATA *)
0x1800692c5  test    rax, rax
0x1800692c8  jz      short loc_1800692F2
0x1800692ca  cmp     qword ptr [rbx], 0
0x1800692ce  jnz     short loc_1800692D5
0x1800692d0  mov     [rbx], rax
0x1800692d3  jmp     short loc_1800692DD
0x1800692d5  mov     rcx, [rbx+8]
0x1800692d9  mov     [rcx+10h], rax
0x1800692dd  mov     [rbx+8], rax
0x1800692e1  test    esi, esi
0x1800692e3  jnz     short loc_1800692AB
0x1800692e5  mov     qword ptr [rbx+8], 0
0x1800692ed  lea     eax, [rsi+1]
0x1800692f0  jmp     short loc_1800692FC
0x1800692f2  mov     rcx, rbx; this
0x1800692f5  call    ?DeleteCache@CPathCache@@QEAAHXZ; CPathCache::DeleteCache(void)
0x1800692fa  xor     eax, eax
0x1800692fc  mov     rbx, [rsp+38h+arg_0]
0x180069301  mov     rsi, [rsp+38h+arg_8]
0x180069306  add     rsp, 30h
0x18006930a  pop     rdi
0x18006930b  retn
```
