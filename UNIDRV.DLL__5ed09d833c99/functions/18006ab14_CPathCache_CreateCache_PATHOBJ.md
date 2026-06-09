# CPathCache::CreateCache(_PATHOBJ *)

- ea: `0x18006ab14`
- end: `0x18006abc9`
- name: `?CreateCache@CPathCache@@QEAAHPEAU_PATHOBJ@@@Z`
- size: `181`
- prototype: `__int64 __fastcall(CPathCache *__hidden this, PATHOBJ *ppo)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18006b2b0`

## callees

- `0x18006ab14`
- `0x18006acbc`
- `0x18006ad7c`

## import_xrefs

- `GDI32!PATHOBJ_bEnum` at `0x18006ab69`
- `GDI32!PATHOBJ_bEnum` at `0x18006ab69`
- `GDI32!PATHOBJ_vEnumStart` at `0x18006ab55`
- `GDI32!PATHOBJ_vEnumStart` at `0x18006ab55`

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
0x18006ab14  mov     [rsp+arg_0], rbx
0x18006ab19  mov     [rsp+arg_8], rsi
0x18006ab1e  push    rdi
0x18006ab1f  sub     rsp, 30h
0x18006ab23  cmp     dword ptr [rcx+10h], 0
0x18006ab27  mov     rdi, rdx
0x18006ab2a  mov     rbx, rcx
0x18006ab2d  jz      short loc_18006AB34
0x18006ab2f  call    ?DeleteCache@CPathCache@@QEAAHXZ; CPathCache::DeleteCache(void)
0x18006ab34  xorps   xmm0, xmm0
0x18006ab37  mov     qword ptr [rbx], 0
0x18006ab3e  mov     rcx, rdi; ppo
0x18006ab41  mov     qword ptr [rbx+8], 0
0x18006ab49  movups  xmmword ptr [rsp+38h+ppd.flags], xmm0
0x18006ab4e  mov     dword ptr [rbx+10h], 1
0x18006ab55  call    cs:__imp_PATHOBJ_vEnumStart
0x18006ab5c  nop     dword ptr [rax+rax+00h]
0x18006ab61  lea     rdx, [rsp+38h+ppd]; ppd
0x18006ab66  mov     rcx, rdi; ppo
0x18006ab69  call    cs:__imp_PATHOBJ_bEnum
0x18006ab70  nop     dword ptr [rax+rax+00h]
0x18006ab75  lea     rdx, [rsp+38h+ppd]; struct _PATHDATA *
0x18006ab7a  mov     esi, eax
0x18006ab7c  call    ?CreateSubPath@CPathCache@@AEAAPEAUCSubPath@1@PEAU_PATHDATA@@@Z; CPathCache::CreateSubPath(_PATHDATA *)
0x18006ab81  test    rax, rax
0x18006ab84  jz      short loc_18006ABAE
0x18006ab86  cmp     qword ptr [rbx], 0
0x18006ab8a  jnz     short loc_18006AB91
0x18006ab8c  mov     [rbx], rax
0x18006ab8f  jmp     short loc_18006AB99
0x18006ab91  mov     rcx, [rbx+8]
0x18006ab95  mov     [rcx+10h], rax
0x18006ab99  mov     [rbx+8], rax
0x18006ab9d  test    esi, esi
0x18006ab9f  jnz     short loc_18006AB61
0x18006aba1  mov     qword ptr [rbx+8], 0
0x18006aba9  lea     eax, [rsi+1]
0x18006abac  jmp     short loc_18006ABB8
0x18006abae  mov     rcx, rbx; this
0x18006abb1  call    ?DeleteCache@CPathCache@@QEAAHXZ; CPathCache::DeleteCache(void)
0x18006abb6  xor     eax, eax
0x18006abb8  mov     rbx, [rsp+38h+arg_0]
0x18006abbd  mov     rsi, [rsp+38h+arg_8]
0x18006abc2  add     rsp, 30h
0x18006abc6  pop     rdi
0x18006abc7  retn
```
