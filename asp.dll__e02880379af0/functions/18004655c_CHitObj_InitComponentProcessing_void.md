# CHitObj::InitComponentProcessing(void)

- ea: `0x18004655c`
- end: `0x18004667e`
- name: `?InitComponentProcessing@CHitObj@@QEAAJXZ`
- size: `290`
- prototype: `__int64 __fastcall(CHitObj *__hidden this)`
- caller_count: `3`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180045f00`
- `0x180045ffc`
- `0x1800473b0`

## callees

- `0x1800060ec`
- `0x180006920`
- `0x180006998`
- `0x180030df0`
- `0x180045ecc`
- `0x18004655c`

## import_xrefs

- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x180046570`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x1800465df`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x180046570`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x1800465df`

## pseudocode

```c
__int64 __fastcall CHitObj::InitComponentProcessing(CHitObj *this)
{
  CComponentCollection *v2; // rax
  CComponentCollection *v3; // rcx
  __int64 v5; // r8
  unsigned int v6; // edx
  int v7; // edi
  CComponentCollection *v8; // rcx
  CIdHashTable *v9; // rax
  unsigned int v10; // edx
  CIdHashTable *v11; // r10
  CComponentCollection *v12; // rcx
  unsigned int v13; // edx
  __int64 v14; // r10
  CComponentCollection *v15; // rcx
  CPageComponentManager *v16; // rcx

  v2 = (CComponentCollection *)ALLOC_CACHE_HANDLER::Alloc(CComponentCollection::sm_pach);
  if ( v2 )
    v3 = CComponentCollection::CComponentCollection(v2);
  else
    v3 = 0;
  *((_QWORD *)this + 10) = v3;
  if ( !v3 )
    return 2147942414LL;
  v5 = *((_QWORD *)this + 29);
  if ( !v5 )
    v5 = *(_QWORD *)(*((_QWORD *)this + 3) + 152LL);
  v7 = CComponentCollection::Init(v3, 4u, *(_DWORD *)(v5 + 92));
  if ( v7 < 0 )
  {
    v8 = (CComponentCollection *)*((_QWORD *)this + 10);
    if ( v8 )
      CComponentCollection::`scalar deleting destructor'(v8, v6);
LABEL_18:
    *((_QWORD *)this + 10) = 0;
    return (unsigned int)v7;
  }
  v9 = (CIdHashTable *)ALLOC_CACHE_HANDLER::Alloc(CPageComponentManager::sm_pach);
  v11 = v9;
  if ( v9 )
  {
    *(_WORD *)v9 = 0;
    *((_QWORD *)v9 + 1) = 0;
    *((_QWORD *)v9 + 2) = 0;
  }
  else
  {
    v11 = 0;
  }
  *((_QWORD *)this + 11) = v11;
  if ( !v11 )
  {
    v12 = (CComponentCollection *)*((_QWORD *)this + 10);
    if ( v12 )
      CComponentCollection::`scalar deleting destructor'(v12, v10);
    v7 = -2147024882;
    goto LABEL_18;
  }
  v7 = CIdHashTable::Init(v11, 0x11u, 0, 0);
  if ( v7 >= 0 )
  {
    *(_QWORD *)(v14 + 16) = this;
    return 0;
  }
  v15 = (CComponentCollection *)*((_QWORD *)this + 10);
  if ( v15 )
    CComponentCollection::`scalar deleting destructor'(v15, v13);
  v16 = (CPageComponentManager *)*((_QWORD *)this + 11);
  *((_QWORD *)this + 10) = 0;
  if ( v16 )
    CPageComponentManager::`scalar deleting destructor'(v16, v13);
  *((_QWORD *)this + 11) = 0;
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18004655c  mov     [rsp+arg_0], rbx
0x180046561  push    rdi
0x180046562  sub     rsp, 20h
0x180046566  mov     rbx, rcx
0x180046569  mov     rcx, cs:?sm_pach@CComponentCollection@@2PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * CComponentCollection::sm_pach
0x180046570  call    cs:__imp_?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ; ALLOC_CACHE_HANDLER::Alloc(void)
0x180046576  test    rax, rax
0x180046579  jz      short loc_180046588
0x18004657b  mov     rcx, rax; this
0x18004657e  call    ??0CComponentCollection@@QEAA@XZ; CComponentCollection::CComponentCollection(void)
0x180046583  mov     rcx, rax
0x180046586  jmp     short loc_18004658A
0x180046588  xor     ecx, ecx; this
0x18004658a  mov     [rbx+50h], rcx
0x18004658e  test    rcx, rcx
0x180046591  jnz     short loc_18004659D
0x180046593  mov     eax, 8007000Eh
0x180046598  jmp     loc_180046673
0x18004659d  mov     r8, [rbx+0E8h]
0x1800465a4  test    r8, r8
0x1800465a7  jnz     short loc_1800465B4
0x1800465a9  mov     rax, [rbx+18h]
0x1800465ad  mov     r8, [rax+98h]
0x1800465b4  mov     r8d, [r8+5Ch]; int
0x1800465b8  mov     edx, 4; unsigned int
0x1800465bd  call    ?Init@CComponentCollection@@QEAAJKH@Z; CComponentCollection::Init(ulong,int)
0x1800465c2  mov     edi, eax
0x1800465c4  test    eax, eax
0x1800465c6  jns     short loc_1800465D8
0x1800465c8  mov     rcx, [rbx+50h]; this
0x1800465cc  test    rcx, rcx
0x1800465cf  jz      short loc_18004661B
0x1800465d1  call    ??_GCComponentCollection@@QEAAPEAXI@Z; CComponentCollection::`scalar deleting destructor'(uint)
0x1800465d6  jmp     short loc_18004661B
0x1800465d8  mov     rcx, cs:?sm_pach@CPageComponentManager@@2PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * CPageComponentManager::sm_pach
0x1800465df  call    cs:__imp_?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ; ALLOC_CACHE_HANDLER::Alloc(void)
0x1800465e5  mov     r10, rax
0x1800465e8  test    rax, rax
0x1800465eb  jz      short loc_1800465FC
0x1800465ed  xor     ecx, ecx
0x1800465ef  mov     [rax], cx
0x1800465f2  mov     [rax+8], rcx
0x1800465f6  mov     [rax+10h], rcx
0x1800465fa  jmp     short loc_1800465FF
0x1800465fc  xor     r10d, r10d
0x1800465ff  mov     [rbx+58h], r10
0x180046603  test    r10, r10
0x180046606  jnz     short loc_180046625
0x180046608  mov     rcx, [rbx+50h]; this
0x18004660c  test    rcx, rcx
0x18004660f  jz      short loc_180046616
0x180046611  call    ??_GCComponentCollection@@QEAAPEAXI@Z; CComponentCollection::`scalar deleting destructor'(uint)
0x180046616  mov     edi, 8007000Eh
0x18004661b  mov     qword ptr [rbx+50h], 0
0x180046623  jmp     short loc_180046671
0x180046625  xor     r9d, r9d; unsigned __int16
0x180046628  xor     r8d, r8d; unsigned __int16
0x18004662b  mov     rcx, r10; this
0x18004662e  lea     edx, [r9+11h]; unsigned __int16
0x180046632  call    ?Init@CIdHashTable@@QEAAJGGG@Z; CIdHashTable::Init(ushort,ushort,ushort)
0x180046637  mov     edi, eax
0x180046639  test    eax, eax
0x18004663b  js      short loc_180046645
0x18004663d  mov     [r10+10h], rbx
0x180046641  xor     eax, eax
0x180046643  jmp     short loc_180046673
0x180046645  mov     rcx, [rbx+50h]; this
0x180046649  test    rcx, rcx
0x18004664c  jz      short loc_180046653
0x18004664e  call    ??_GCComponentCollection@@QEAAPEAXI@Z; CComponentCollection::`scalar deleting destructor'(uint)
0x180046653  mov     rcx, [rbx+58h]; this
0x180046657  mov     qword ptr [rbx+50h], 0
0x18004665f  test    rcx, rcx
0x180046662  jz      short loc_180046669
0x180046664  call    ??_GCPageComponentManager@@QEAAPEAXI@Z; CPageComponentManager::`scalar deleting destructor'(uint)
0x180046669  mov     qword ptr [rbx+58h], 0
0x180046671  mov     eax, edi
0x180046673  mov     rbx, [rsp+28h+arg_0]
0x180046678  add     rsp, 20h
0x18004667c  pop     rdi
0x18004667d  retn
```
