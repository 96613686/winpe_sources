# CMPEG2Demultiplexer::CreatePin_(ushort const *,_PinDirection,_AMMediaType *,long,int,ulong,ulong,DEMUX_PIN_RECORD * *)

- ea: `0x1800140bc`
- end: `0x18001436a`
- name: `?CreatePin_@CMPEG2Demultiplexer@@AEAAJPEBGW4_PinDirection@@PEAU_AMMediaType@@JHKKPEAPEAUDEMUX_PIN_RECORD@@@Z`
- size: `686`
- prototype: `__int64 __usercall@<rax>(CMPEG2Demultiplexer *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, enum _PinDirection@<r8d>, struct _AMMediaType *@<r9>, int, int, unsigned int, unsigned int, struct DEMUX_PIN_RECORD **)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180013f9c`

## callees

- `0x180001008`
- `0x180001048`
- `0x180001054`
- `0x1800140bc`
- `0x180014998`
- `0x1800154d0`
- `0x180021eac`
- `0x180034010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x1800142fc`
- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x1800142fc`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180014245`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180014245`
- `KERNEL32!LeaveCriticalSection` at `0x18001434a`
- `KERNEL32!LeaveCriticalSection` at `0x18001434a`
- `KERNEL32!EnterCriticalSection` at `0x1800140e8`
- `KERNEL32!EnterCriticalSection` at `0x1800140e8`

## pseudocode

```c
__int64 __fastcall CMPEG2Demultiplexer::CreatePin_(
        CMPEG2Demultiplexer *this,
        const unsigned __int16 *a2,
        enum _PinDirection a3,
        struct _AMMediaType *a4,
        int a5,
        int a6,
        unsigned int a7,
        unsigned int a8,
        struct DEMUX_PIN_RECORD **a9)
{
  int v10; // edi
  struct _RTL_CRITICAL_SECTION *v11; // rcx
  void **v14; // rbx
  CMPEG2DemuxOutputPin *v15; // rax
  const unsigned __int16 *v16; // r9
  CMPEG2DemuxOutputPin *v17; // r13
  volatile signed __int32 *v18; // rbx
  __int64 v19; // rax
  void *v20; // rax
  int v22; // [rsp+48h] [rbp-60h]
  int v23; // [rsp+50h] [rbp-58h]
  int *v24; // [rsp+68h] [rbp-40h]
  struct DEMUX_PIN_RECORD *v25; // [rsp+B0h] [rbp+8h] BYREF
  size_t NumOfElements; // [rsp+C0h] [rbp+18h] BYREF

  LODWORD(NumOfElements) = a3;
  v10 = 0;
  v11 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 10);
  LODWORD(NumOfElements) = 0;
  EnterCriticalSection(v11);
  v25 = 0;
  if ( (int)CMPEG2Demultiplexer::FindPinRecordLocked_(this, a2, &v25, 0) >= 0 )
  {
    v14 = (void **)v25;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v25 + 2, 0xFFFFFFFF) == 1 && v14 )
    {
      operator delete(v14[2]);
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)*v14 + 1) + 16LL))(*((_QWORD *)*v14 + 1));
      operator delete(v14);
    }
    v10 = -2147220947;
    goto LABEL_27;
  }
  v15 = (CMPEG2DemuxOutputPin *)operator new(0x230u);
  if ( !v15 )
    goto LABEL_26;
  v17 = CMPEG2DemuxOutputPin::CMPEG2DemuxOutputPin(
          v15,
          a4,
          a2,
          v16,
          this,
          *((struct CRefCountedCritSec **)this + 10),
          *((struct CMpeg2DemuxMediaSeekingCore **)this + 43),
          *((struct CRefCountedCritSec **)this + 44),
          *((struct CMpeg2Stats **)this + 33),
          v22,
          v23,
          a7,
          a8,
          v24);
  if ( !v17 )
    goto LABEL_26;
  v18 = (volatile signed __int32 *)operator new(0x18u);
  if ( v18 )
  {
    *((_DWORD *)v18 + 2) = 1;
    *((_DWORD *)v18 + 3) = 1;
    v19 = -1;
    *(_QWORD *)v18 = v17;
    *((_QWORD *)v18 + 2) = 0;
    do
      ++v19;
    while ( a2[v19] );
    v25 = (struct DEMUX_PIN_RECORD *)(v19 + 1);
    v20 = operator new[](saturated_mul(v19 + 1, 2u));
    *((_QWORD *)v18 + 2) = v20;
    if ( v20 )
      _o_wcscpy_s(v20, v25, a2);
    else
      v10 = -2147024882;
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)v18 + 8LL) + 8LL))(*(_QWORD *)(*(_QWORD *)v18 + 8LL));
  }
  (*(void (__fastcall **)(__int64))(*((_QWORD *)v17 + 3) + 16LL))((__int64)v17 + 24);
  if ( v10 < 0 )
  {
    if ( !v18 || _InterlockedExchangeAdd(v18 + 2, 0xFFFFFFFF) != 1 )
      goto LABEL_27;
LABEL_19:
    operator delete(*((void **)v18 + 2));
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)v18 + 8LL) + 16LL))(*(_QWORD *)(*(_QWORD *)v18 + 8LL));
    operator delete((void *)v18);
    goto LABEL_27;
  }
  if ( !v18 )
  {
LABEL_26:
    v10 = -2147024882;
    goto LABEL_27;
  }
  v10 = TSimpleVector<DEMUX_PIN_RECORD *>::Insert((char *)this + 184, *((unsigned int *)this + 48), v18, &NumOfElements);
  if ( v10 < 0 )
  {
    if ( _InterlockedExchangeAdd(v18 + 2, 0xFFFFFFFF) != 1 )
      goto LABEL_27;
    goto LABEL_19;
  }
  qsort(*((void **)this + 23), (unsigned int)NumOfElements, 8u, DEMUX_PIN_RECORD::Compare);
  if ( a9 )
  {
    *a9 = (struct DEMUX_PIN_RECORD *)v18;
    _InterlockedIncrement(v18 + 2);
  }
  _InterlockedIncrement((volatile signed __int32 *)this + 28);
LABEL_27:
  LeaveCriticalSection(*((LPCRITICAL_SECTION *)this + 10));
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800140bc  mov     rax, rsp
0x1800140bf  mov     [rax+10h], rbx
0x1800140c3  mov     [rax+18h], r8d
0x1800140c7  push    rbp
0x1800140c8  push    rsi
0x1800140c9  push    rdi
0x1800140ca  push    r12
0x1800140cc  push    r13
0x1800140ce  push    r14
0x1800140d0  push    r15
0x1800140d2  sub     rsp, 70h
0x1800140d6  mov     rbp, rcx
0x1800140d9  xor     edi, edi
0x1800140db  mov     rcx, [rcx+50h]; lpCriticalSection
0x1800140df  mov     rbx, r9
0x1800140e2  mov     [rax+18h], edi
0x1800140e5  mov     r14, rdx
0x1800140e8  call    cs:__imp_EnterCriticalSection
0x1800140ee  xor     r9d, r9d; unsigned int *
0x1800140f1  mov     [rsp+0A8h+arg_0], rdi
0x1800140f9  lea     r8, [rsp+0A8h+arg_0]; struct DEMUX_PIN_RECORD **
0x180014101  mov     rdx, r14; unsigned __int16 *
0x180014104  mov     rcx, rbp; this
0x180014107  call    ?FindPinRecordLocked_@CMPEG2Demultiplexer@@AEAAJPEBGPEAPEAUDEMUX_PIN_RECORD@@PEAK@Z; CMPEG2Demultiplexer::FindPinRecordLocked_(ushort const *,DEMUX_PIN_RECORD * *,ulong *)
0x18001410c  test    eax, eax
0x18001410e  js      short loc_180014160
0x180014110  mov     rbx, [rsp+0A8h+arg_0]
0x180014118  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18001411c  mov     eax, esi
0x18001411e  lock xadd [rbx+8], eax
0x180014123  add     eax, esi
0x180014125  jnz     short loc_180014156
0x180014127  test    rbx, rbx
0x18001412a  jz      short loc_180014156
0x18001412c  mov     rcx, [rbx+10h]; void *
0x180014130  lea     edx, [rdi+2]; unsigned __int64
0x180014133  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180014138  mov     rax, [rbx]
0x18001413b  mov     rcx, [rax+8]
0x18001413f  mov     rax, [rcx]
0x180014142  mov     rax, [rax+10h]
0x180014146  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001414b  lea     edx, [rdi+18h]; unsigned __int64
0x18001414e  mov     rcx, rbx; void *
0x180014151  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180014156  mov     edi, 8004022Dh
0x18001415b  jmp     loc_180014346
0x180014160  mov     ecx, 230h; Size
0x180014165  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001416a  test    rax, rax
0x18001416d  jz      loc_180014341
0x180014173  mov     ecx, [rsp+0A8h+arg_38]
0x18001417a  mov     r8, r14; unsigned __int16 *
0x18001417d  mov     [rsp+0A8h+var_48], ecx; unsigned int
0x180014181  mov     rdx, rbx; struct _AMMediaType *
0x180014184  mov     ecx, [rsp+0A8h+arg_30]
0x18001418b  mov     [rsp+0A8h+var_50], ecx; unsigned int
0x18001418f  mov     rcx, [rbp+108h]
0x180014196  mov     [rsp+0A8h+var_68], rcx; struct CMpeg2Stats *
0x18001419b  mov     rcx, [rbp+160h]
0x1800141a2  mov     [rsp+0A8h+var_70], rcx; struct CRefCountedCritSec *
0x1800141a7  mov     rcx, [rbp+158h]
0x1800141ae  mov     [rsp+0A8h+var_78], rcx; struct CMpeg2DemuxMediaSeekingCore *
0x1800141b3  mov     rcx, [rbp+50h]
0x1800141b7  mov     [rsp+0A8h+var_80], rcx; struct CRefCountedCritSec *
0x1800141bc  mov     rcx, rax; this
0x1800141bf  mov     [rsp+0A8h+var_88], rbp; struct CMPEG2Demultiplexer *
0x1800141c4  call    ??0CMPEG2DemuxOutputPin@@QEAA@PEAU_AMMediaType@@PEBG1PEAVCMPEG2Demultiplexer@@PEAVCRefCountedCritSec@@PEAVCMpeg2DemuxMediaSeekingCore@@3PEAVCMpeg2Stats@@JHKKPEAJ@Z; CMPEG2DemuxOutputPin::CMPEG2DemuxOutputPin(_AMMediaType *,ushort const *,ushort const *,CMPEG2Demultiplexer *,CRefCountedCritSec *,CMpeg2DemuxMediaSeekingCore *,CRefCountedCritSec *,CMpeg2Stats *,long,int,ulong,ulong,long *)
0x1800141c9  mov     r13, rax
0x1800141cc  test    rax, rax
0x1800141cf  jz      loc_180014341
0x1800141d5  mov     r15d, 18h
0x1800141db  mov     ecx, r15d; Size
0x1800141de  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800141e3  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800141e7  lea     r12d, [r15-16h]
0x1800141eb  mov     rbx, rax
0x1800141ee  lea     eax, [rsi+2]
0x1800141f1  test    rbx, rbx
0x1800141f4  jz      short loc_180014265
0x1800141f6  mov     [rbx+8], eax
0x1800141f9  mov     [rbx+0Ch], eax
0x1800141fc  mov     rax, rsi
0x1800141ff  mov     [rbx], r13
0x180014202  mov     [rbx+10h], rdi
0x180014206  inc     rax
0x180014209  cmp     [r14+rax*2], di
0x18001420e  jnz     short loc_180014206
0x180014210  lea     rcx, [rax+1]
0x180014214  mov     rax, r12
0x180014217  mul     rcx
0x18001421a  mov     [rsp+0A8h+arg_0], rcx
0x180014222  cmovb   rax, rsi
0x180014226  mov     rcx, rax; unsigned __int64
0x180014229  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001422e  mov     [rbx+10h], rax
0x180014232  test    rax, rax
0x180014235  jz      short loc_18001424D
0x180014237  mov     rdx, [rsp+0A8h+arg_0]
0x18001423f  mov     r8, r14
0x180014242  mov     rcx, rax
0x180014245  call    cs:__imp__o_wcscpy_s
0x18001424b  jmp     short loc_180014252
0x18001424d  mov     edi, 8007000Eh
0x180014252  mov     rax, [rbx]
0x180014255  mov     rcx, [rax+8]
0x180014259  mov     rax, [rcx]
0x18001425c  mov     rax, [rax+8]
0x180014260  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014265  lea     rcx, [r13+18h]
0x180014269  mov     rax, [rcx]
0x18001426c  mov     rax, [rax+10h]
0x180014270  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014275  test    edi, edi
0x180014277  js      loc_18001431C
0x18001427d  test    rbx, rbx
0x180014280  jz      loc_180014341
0x180014286  lea     r14, [rbp+0B8h]
0x18001428d  mov     r8, rbx
0x180014290  mov     edx, [r14+8]
0x180014294  lea     r9, [rsp+0A8h+NumOfElements]
0x18001429c  mov     rcx, r14
0x18001429f  call    ?Insert@?$TSimpleVector@PEAUDEMUX_PIN_RECORD@@@@QEAAJKPEAUDEMUX_PIN_RECORD@@PEAK@Z; TSimpleVector<DEMUX_PIN_RECORD *>::Insert(ulong,DEMUX_PIN_RECORD *,ulong *)
0x1800142a4  mov     edi, eax
0x1800142a6  test    eax, eax
0x1800142a8  jns     short loc_1800142E5
0x1800142aa  mov     ecx, esi
0x1800142ac  lock xadd [rbx+8], ecx
0x1800142b1  add     ecx, esi
0x1800142b3  jnz     loc_180014346
0x1800142b9  mov     rcx, [rbx+10h]; void *
0x1800142bd  mov     rdx, r12; unsigned __int64
0x1800142c0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800142c5  mov     rdx, [rbx]
0x1800142c8  mov     rcx, [rdx+8]
0x1800142cc  mov     rax, [rcx]
0x1800142cf  mov     rax, [rax+10h]
0x1800142d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800142d8  mov     rdx, r15; unsigned __int64
0x1800142db  mov     rcx, rbx; void *
0x1800142de  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800142e3  jmp     short loc_180014346
0x1800142e5  mov     edx, dword ptr [rsp+0A8h+NumOfElements]; NumOfElements
0x1800142ec  lea     r9, ?Compare@DEMUX_PIN_RECORD@@SAHPEBX0@Z; CompareFunction
0x1800142f3  mov     rcx, [r14]; Base
0x1800142f6  mov     r8d, 8; SizeOfElements
0x1800142fc  call    cs:__imp_qsort
0x180014302  mov     rax, [rsp+0A8h+arg_40]
0x18001430a  test    rax, rax
0x18001430d  jz      short loc_180014316
0x18001430f  mov     [rax], rbx
0x180014312  lock inc dword ptr [rbx+8]
0x180014316  lock inc dword ptr [rbp+70h]
0x18001431a  jmp     short loc_180014346
0x18001431c  test    rbx, rbx
0x18001431f  jz      short loc_180014346
0x180014321  mov     eax, esi
0x180014323  lock xadd [rbx+8], eax
0x180014328  add     eax, esi
0x18001432a  jnz     short loc_180014346
0x18001432c  mov     rcx, [rbx+10h]; void *
0x180014330  mov     rdx, r12; unsigned __int64
0x180014333  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180014338  mov     rax, [rbx]
0x18001433b  mov     rcx, [rax+8]
0x18001433f  jmp     short loc_1800142CC
0x180014341  mov     edi, 8007000Eh
0x180014346  mov     rcx, [rbp+50h]; lpCriticalSection
0x18001434a  call    cs:__imp_LeaveCriticalSection
0x180014350  mov     rbx, [rsp+0A8h+arg_8]
0x180014358  mov     eax, edi
0x18001435a  add     rsp, 70h
0x18001435e  pop     r15
0x180014360  pop     r14
0x180014362  pop     r13
0x180014364  pop     r12
0x180014366  pop     rdi
0x180014367  pop     rsi
0x180014368  pop     rbp
0x180014369  retn
```
