# RWCString::replace(uint,uint,char const *,uint)

- ea: `0x1801342d0`
- end: `0x180134463`
- name: `?replace@RWCString@@QEAAAEAV1@IIPEBDI@Z`
- size: `403`
- prototype: `struct RWCString *(RWCString *__hidden this, unsigned int, unsigned int, const char *, unsigned int)`
- caller_count: `149`
- callee_count: `5`
- tags: ``

## callers

- `0x18000f3e0`
- `0x18000f5d0`
- `0x18000f600`
- `0x18000f630`
- `0x180017800`
- `0x180017d84`
- `0x180018050`
- `0x1800332f0`
- `0x180033b34`
- `0x180037394`
- `0x180038eb0`
- `0x180038ed0`
- `0x180038f00`
- `0x180039490`
- `0x18003b080`
- `0x18003b670`
- `0x18003c014`
- `0x18003ca20`
- `0x18003dc48`
- `0x18003df90`
- `0x18003ede8`
- `0x18003fcd0`
- `0x180040180`
- `0x1800406b0`
- `0x180041860`
- `0x180041e50`
- `0x180041ef0`
- `0x1800421b0`
- `0x1800442d0`
- `0x180044eb0`
- `0x180045880`
- `0x180045aa0`
- `0x180045f30`
- `0x180046130`
- `0x1800466fc`
- `0x180046890`
- `0x180046bd0`
- `0x180046d64`
- `0x180047940`
- `0x18004870c`
- `0x18004c140`
- `0x18004c220`
- `0x18004cf20`
- `0x18004d30c`
- `0x18004dc30`
- `0x18004deb0`
- `0x18004e0cc`
- `0x18004ea40`
- `0x18004f150`
- `0x180057670`

## callees

- `0x1800838f0`
- `0x180133b20`
- `0x1801342d0`
- `0x180134b70`
- `0x18015197d`

## import_xrefs

- `VCRUNTIME140!memmove` at `0x180134375`
- `VCRUNTIME140!memmove` at `0x18013438a`
- `VCRUNTIME140!memmove` at `0x180134375`
- `VCRUNTIME140!memmove` at `0x18013438a`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180134434`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180134434`

## pseudocode

```c
struct RWCString *__fastcall RWCString::replace(
        RWCString *this,
        unsigned int a2,
        unsigned int a3,
        const char *a4,
        unsigned int a5)
{
  int v7; // r8d
  unsigned int v8; // edi
  unsigned __int64 v10; // r9
  unsigned int v11; // r15d
  unsigned int v12; // r12d
  unsigned int v13; // esi
  unsigned int v14; // r15d
  __int64 v15; // rbp
  unsigned int v16; // eax
  struct RWCStringRef *Rep; // rax
  struct RWCStringRef *v18; // rbp
  int *v19; // rcx

  v7 = 0;
  v8 = a2;
  if ( a2 == -1 )
  {
    v8 = 0;
    v7 = 1;
  }
  v10 = *(_QWORD *)this;
  v11 = *(_DWORD *)(*(_QWORD *)this - 4LL) - v8;
  v12 = v11;
  if ( a3 < v11 )
    v12 = a3;
  v13 = a4 != 0 ? a5 : 0;
  v14 = v11 - v12;
  v15 = v13 + *(_DWORD *)(*(_QWORD *)this - 4LL) - v12;
  if ( *(_DWORD *)(v10 - 12) > 1u
    || *(_DWORD *)(v10 - 8) < (unsigned int)v15
    || a4 && (unsigned __int64)a4 >= v10 && (unsigned __int64)a4 < v10 + *(unsigned int *)(v10 - 4) )
  {
    v16 = RWCString::adjustCapacity(this, v15, v7);
    Rep = RWCStringRef::getRep(v16, v15);
    v18 = Rep;
    if ( v8 )
      memcpy((char *)Rep + 12, *(const void **)this, v8);
    if ( v13 )
      memcpy((char *)v18 + v8 + 12, a4, v13);
    if ( v14 )
      memcpy((char *)v18 + v13 + v8 + 12, (const void *)(*(_QWORD *)this + v8 + (unsigned __int64)v12), v14);
    v19 = (int *)(*(_QWORD *)this - 12LL);
    if ( _InterlockedExchangeAdd(v19, 0xFFFFFFFF) == 1 && v19 != &dword_1802AFD50 )
    {
      if ( dword_1802B0018 )
        COWSAllocator::Free(v19);
      else
        free(v19);
    }
    *(_QWORD *)this = (char *)v18 + 12;
  }
  else
  {
    if ( v12 != v13 && v14 )
      memmove((void *)(v10 + v8 + (unsigned __int64)v13), (const void *)(v10 + v8 + (unsigned __int64)v12), v14);
    if ( v13 )
      memmove((void *)(*(_QWORD *)this + v8), a4, v13);
    *(_DWORD *)(*(_QWORD *)this - 4LL) = v15;
    *(_BYTE *)(v15 + *(_QWORD *)this) = 0;
  }
  return this;
}

```

## disassembly

```asm
0x1801342d0  mov     rax, rsp
0x1801342d3  mov     [rax+8], rbx
0x1801342d7  mov     [rax+10h], rbp
0x1801342db  mov     [rax+18h], rsi
0x1801342df  mov     [rax+20h], rdi
0x1801342e3  push    r12
0x1801342e5  push    r14
0x1801342e7  push    r15
0x1801342e9  sub     rsp, 20h
0x1801342ed  mov     eax, r8d
0x1801342f0  mov     r14, r9
0x1801342f3  xor     r8d, r8d
0x1801342f6  mov     edi, edx
0x1801342f8  mov     rbx, rcx
0x1801342fb  cmp     edx, 0FFFFFFFFh
0x1801342fe  jnz     short loc_180134306
0x180134300  xor     edi, edi
0x180134302  lea     r8d, [rdi+1]; int
0x180134306  mov     r9, [rcx]
0x180134309  mov     r15d, [r9-4]
0x18013430d  mov     ebp, [r9-4]
0x180134311  sub     r15d, edi
0x180134314  cmp     eax, r15d
0x180134317  mov     r12d, r15d
0x18013431a  cmovb   r12d, eax
0x18013431e  mov     rax, r14
0x180134321  neg     rax
0x180134324  sbb     esi, esi
0x180134326  sub     ebp, r12d
0x180134329  and     esi, [rsp+38h+arg_20]
0x18013432d  sub     r15d, r12d
0x180134330  add     ebp, esi
0x180134332  cmp     dword ptr [r9-0Ch], 1
0x180134337  ja      short loc_1801343A3
0x180134339  cmp     [r9-8], ebp
0x18013433d  jb      short loc_1801343A3
0x18013433f  test    r14, r14
0x180134342  jz      short loc_180134355
0x180134344  cmp     r14, r9
0x180134347  jb      short loc_180134355
0x180134349  mov     eax, [r9-4]
0x18013434d  add     rax, r9
0x180134350  cmp     r14, rax
0x180134353  jb      short loc_1801343A3
0x180134355  cmp     r12d, esi
0x180134358  jz      short loc_18013437B
0x18013435a  test    r15d, r15d
0x18013435d  jz      short loc_18013437B
0x18013435f  mov     eax, edi
0x180134361  mov     edx, r12d
0x180134364  add     rdx, rax
0x180134367  mov     ecx, esi
0x180134369  add     rcx, rax
0x18013436c  mov     r8d, r15d; Size
0x18013436f  add     rdx, r9; Src
0x180134372  add     rcx, r9; void *
0x180134375  call    cs:memmove
0x18013437b  test    esi, esi
0x18013437d  jz      short loc_180134390
0x18013437f  mov     ecx, edi
0x180134381  mov     rdx, r14; Src
0x180134384  add     rcx, [rbx]; void *
0x180134387  mov     r8d, esi; Size
0x18013438a  call    cs:memmove
0x180134390  mov     rax, [rbx]
0x180134393  mov     [rax-4], ebp
0x180134396  mov     rax, [rbx]
0x180134399  mov     byte ptr [rbp+rax+0], 0
0x18013439e  jmp     loc_180134441
0x1801343a3  mov     edx, ebp; unsigned int
0x1801343a5  call    ?adjustCapacity@RWCString@@IEAAIIH@Z; RWCString::adjustCapacity(uint,int)
0x1801343aa  mov     ecx, eax; unsigned int
0x1801343ac  mov     edx, ebp; unsigned int
0x1801343ae  call    ?getRep@RWCStringRef@@CAPEAV1@II@Z; RWCStringRef::getRep(uint,uint)
0x1801343b3  mov     rbp, rax
0x1801343b6  test    edi, edi
0x1801343b8  jz      short loc_1801343C9
0x1801343ba  mov     rdx, [rbx]; Src
0x1801343bd  lea     rcx, [rax+0Ch]; void *
0x1801343c1  mov     r8d, edi; Size
0x1801343c4  call    memcpy
0x1801343c9  test    esi, esi
0x1801343cb  jz      short loc_1801343E1
0x1801343cd  mov     ecx, edi
0x1801343cf  mov     rdx, r14; Src
0x1801343d2  add     rcx, 0Ch
0x1801343d6  mov     r8d, esi; Size
0x1801343d9  add     rcx, rbp; void *
0x1801343dc  call    memcpy
0x1801343e1  test    r15d, r15d
0x1801343e4  jz      short loc_180134405
0x1801343e6  mov     ecx, edi
0x1801343e8  mov     eax, esi
0x1801343ea  add     rax, 0Ch
0x1801343ee  mov     edx, r12d
0x1801343f1  add     rdx, rcx
0x1801343f4  mov     r8d, r15d; Size
0x1801343f7  add     rdx, [rbx]; Src
0x1801343fa  add     rcx, rax
0x1801343fd  add     rcx, rbp; void *
0x180134400  call    memcpy
0x180134405  mov     rcx, [rbx]
0x180134408  sub     rcx, 0Ch; void *
0x18013440c  or      eax, 0FFFFFFFFh
0x18013440f  lock xadd [rcx], eax
0x180134413  cmp     eax, 1
0x180134416  jnz     short loc_18013443A
0x180134418  lea     rax, dword_1802AFD50
0x18013441f  cmp     rcx, rax
0x180134422  jz      short loc_18013443A
0x180134424  cmp     cs:dword_1802B0018, 0
0x18013442b  jz      short loc_180134434
0x18013442d  call    ?Free@COWSAllocator@@SAXPEAX@Z; COWSAllocator::Free(void *)
0x180134432  jmp     short loc_18013443A
0x180134434  call    cs:free
0x18013443a  lea     rax, [rbp+0Ch]
0x18013443e  mov     [rbx], rax
0x180134441  mov     rbp, [rsp+38h+arg_8]
0x180134446  mov     rax, rbx
0x180134449  mov     rbx, [rsp+38h+arg_0]
0x18013444e  mov     rsi, [rsp+38h+arg_10]
0x180134453  mov     rdi, [rsp+38h+arg_18]
0x180134458  add     rsp, 20h
0x18013445c  pop     r15
0x18013445e  pop     r14
0x180134460  pop     r12
0x180134462  retn
```
