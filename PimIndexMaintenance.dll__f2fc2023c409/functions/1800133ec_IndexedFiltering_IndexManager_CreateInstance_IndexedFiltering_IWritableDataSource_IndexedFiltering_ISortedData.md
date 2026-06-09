# IndexedFiltering::IndexManager::CreateInstance(IndexedFiltering::IWritableDataSource *,IndexedFiltering::ISortedDataSource * *,IndexedFiltering::_IndexSourceData const *,uint,ushort const *,int,IndexedFiltering::IndexManager * *)

- ea: `0x1800133ec`
- end: `0x180013499`
- name: `?CreateInstance@IndexManager@IndexedFiltering@@SAJPEAUIWritableDataSource@2@PEAPEAUISortedDataSource@2@PEBU_IndexSourceData@2@IPEBGHPEAPEAV12@@Z`
- size: `173`
- prototype: `__int64 __fastcall(struct IndexedFiltering::IWritableDataSource *, struct IndexedFiltering::ISortedDataSource **, const struct IndexedFiltering::_IndexSourceData *, __int64, const unsigned __int16 *, unsigned int, struct IndexedFiltering::IndexManager **)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180013254`

## callees

- `0x1800012fc`
- `0x180002da8`
- `0x180012af8`
- `0x180012b94`
- `0x1800133ec`
- `0x180013768`

## string_xrefs

- `0x180013445`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\indexmanager.cpp`
- `0x180013478`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\indexmanager.cpp`

## pseudocode

```c
__int64 __fastcall IndexedFiltering::IndexManager::CreateInstance(
        struct IndexedFiltering::IWritableDataSource *a1,
        struct IndexedFiltering::ISortedDataSource **a2,
        const struct IndexedFiltering::_IndexSourceData *a3,
        __int64 a4,
        const unsigned __int16 *a5,
        unsigned int a6,
        struct IndexedFiltering::IndexManager **a7)
{
  IndexedFiltering::IndexManager *v10; // rax
  ESESession **v11; // rax
  struct IndexedFiltering::IndexManager *v12; // rbx
  int v13; // eax
  unsigned int v14; // edi
  unsigned int v16; // [rsp+20h] [rbp-48h]
  const unsigned __int16 *v17; // [rsp+28h] [rbp-40h]

  v10 = (IndexedFiltering::IndexManager *)operator new(0xE0u);
  if ( v10
    && (v11 = (ESESession **)IndexedFiltering::IndexManager::IndexManager(v10),
        (v12 = (struct IndexedFiltering::IndexManager *)v11) != 0) )
  {
    v13 = IndexedFiltering::IndexManager::Init(v11, a1, a2, a3, v16, v17, a6);
    v14 = v13;
    if ( v13 >= 0 )
    {
      *a7 = v12;
      return 0;
    }
    else
    {
      Log_HREvent(
        (unsigned int)v13,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\indexmanager.cpp",
        135);
      tlx::_delete<IndexedFiltering::IndexManager>((__int64)v12);
      return v14;
    }
  }
  else
  {
    Log_HREvent(
      2147942414LL,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\indexmanager.cpp",
      128);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x1800133ec  push    rbx
0x1800133ee  push    rbp
0x1800133ef  push    rsi
0x1800133f0  push    rdi
0x1800133f1  sub     rsp, 48h
0x1800133f5  mov     rbp, rcx
0x1800133f8  mov     rdi, r8
0x1800133fb  mov     ecx, 0E0h; Size
0x180013400  mov     rsi, rdx
0x180013403  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180013408  test    rax, rax
0x18001340b  jz      short loc_180013473
0x18001340d  mov     rcx, rax; this
0x180013410  call    ??0IndexManager@IndexedFiltering@@IEAA@XZ; IndexedFiltering::IndexManager::IndexManager(void)
0x180013415  mov     rbx, rax
0x180013418  test    rax, rax
0x18001341b  jz      short loc_180013473
0x18001341d  mov     ecx, [rsp+68h+arg_28]
0x180013424  mov     r9, rdi; struct IndexedFiltering::_IndexSourceData *
0x180013427  mov     [rsp+68h+var_38], ecx; int
0x18001342b  mov     r8, rsi; struct IndexedFiltering::ISortedDataSource **
0x18001342e  mov     rcx, rax; this
0x180013431  mov     rdx, rbp; struct IndexedFiltering::IWritableDataSource *
0x180013434  call    ?Init@IndexManager@IndexedFiltering@@IEAAJPEAUIWritableDataSource@2@PEAPEAUISortedDataSource@2@PEBU_IndexSourceData@2@IPEBGH@Z; IndexedFiltering::IndexManager::Init(IndexedFiltering::IWritableDataSource *,IndexedFiltering::ISortedDataSource * *,IndexedFiltering::_IndexSourceData const *,uint,ushort const *,int)
0x180013439  mov     edi, eax
0x18001343b  test    eax, eax
0x18001343d  jns     short loc_180013464
0x18001343f  mov     r9d, 87h
0x180013445  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18001344c  mov     edx, 1
0x180013451  mov     ecx, eax
0x180013453  call    Log_HREvent
0x180013458  mov     rcx, rbx
0x18001345b  call    ??$_delete@VIndexManager@IndexedFiltering@@@tlx@@YAXPEAVIndexManager@IndexedFiltering@@@Z; tlx::_delete<IndexedFiltering::IndexManager>(IndexedFiltering::IndexManager *)
0x180013460  mov     eax, edi
0x180013462  jmp     short loc_180013490
0x180013464  mov     rax, [rsp+68h+arg_30]
0x18001346c  mov     [rax], rbx
0x18001346f  xor     eax, eax
0x180013471  jmp     short loc_180013490
0x180013473  mov     ebx, 8007000Eh
0x180013478  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18001347f  mov     ecx, ebx
0x180013481  mov     r9d, 80h
0x180013487  xor     edx, edx
0x180013489  call    Log_HREvent
0x18001348e  mov     eax, ebx
0x180013490  add     rsp, 48h
0x180013494  pop     rdi
0x180013495  pop     rsi
0x180013496  pop     rbp
0x180013497  pop     rbx
0x180013498  retn
```
