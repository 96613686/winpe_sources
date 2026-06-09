# MemoryBlock::CreateMemoryBlock(void *,_VID_MEMORY_BLOCK_CONFIG *,MemoryBlock::_ADDITIONAL_MB_ATTRIBUTES,unsigned __int64,PoisonedPageContainer *,_VID_FILE_MAPPING *,MemoryTraceTracker &)

- ea: `0x1402134e8`
- end: `0x1402139d3`
- name: `?CreateMemoryBlock@MemoryBlock@@KAPEAV1@PEAXPEAU_VID_MEMORY_BLOCK_CONFIG@@T_ADDITIONAL_MB_ATTRIBUTES@1@_KPEAVPoisonedPageContainer@@PEAU_VID_FILE_MAPPING@@AEAUMemoryTraceTracker@@@Z`
- size: `1259`
- prototype: `MemoryBlock *(__int64, _QWORD *, char, ...)`
- caller_count: `3`
- callee_count: `15`
- tags: `registry_config`

## callers

- `0x1400bfa30`
- `0x1400d6150`
- `0x140205928`

## callees

- `0x14001f374`
- `0x1400205ac`
- `0x14002c730`
- `0x140033950`
- `0x14004d800`
- `0x140051ad8`
- `0x14005b628`
- `0x1400db668`
- `0x140132940`
- `0x140132cec`
- `0x1401335fc`
- `0x1401feaa0`
- `0x140212104`
- `0x1402130d8`
- `0x1402134e8`

## import_xrefs

- `vid!VidQueryMemoryBlockInformation` at `0x14021382b`
- `vid!VidQueryMemoryBlockInformation` at `0x14021382b`
- `vid!VidCreateMemoryBlock` at `0x140213789`
- `vid!VidCreateMemoryBlock` at `0x140213789`
- `vid!VidCreateDaxFileMemoryBlock` at `0x140213718`
- `vid!VidCreateDaxFileMemoryBlock` at `0x140213718`

## string_xrefs

- `0x14021373f`: `PageCountTotal = %I64x, MbCreateFlags = %I64x, VirtualNode = %u, PersistId = %I64u`
- `0x1402137bf`: `PageCountTotal = %I64x, PageCountValid = %I64x, MbCreateFlags = %I64x, BackingBitmapBufferSizeInBytes = %I64u, VirtualNode = %u, PersistId = %I64u`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
MemoryBlock *MemoryBlock::CreateMemoryBlock(__int64 a1, _QWORD *a2, char a3, ...)
{
  PoisonedPageContainer *v6; // r13
  __int64 v7; // rsi
  __int64 v8; // r14
  __int64 v9; // rax
  __int64 *v10; // rdi
  __int64 v11; // rax
  _BYTE *v12; // rsi
  _BYTE *v13; // r14
  __int64 v14; // r9
  __int64 v15; // r15
  __int64 v16; // rdi
  int v17; // ebx
  const char *v18; // rsi
  unsigned int DaxFileMemoryBlock; // eax
  __int64 v20; // rbx
  int v21; // edi
  __int64 v22; // rsi
  __int64 v23; // r14
  const char *v24; // r15
  unsigned int MemoryBlock; // eax
  const char *v26; // r9
  wil *v27; // rcx
  char *v28; // rbx
  double v29; // xmm0_8
  MemoryBlock *v30; // rbx
  double v31; // xmm0_8
  double v32; // xmm0_8
  unsigned __int64 v33; // rax
  unsigned int v35; // ebx
  __int64 v36; // r9
  __int64 v37; // r9
  int v38; // r9d
  __int64 v39; // [rsp+38h] [rbp-2C0h]
  __int64 v40; // [rsp+48h] [rbp-2B0h]
  __int64 v41; // [rsp+60h] [rbp-298h] BYREF
  __int64 v42; // [rsp+68h] [rbp-290h] BYREF
  __int64 v43; // [rsp+70h] [rbp-288h] BYREF
  __int64 v44; // [rsp+78h] [rbp-280h]
  RTL_SRWLOCK *v45; // [rsp+80h] [rbp-278h]
  _QWORD *v46; // [rsp+90h] [rbp-268h]
  MemoryBlock **v47; // [rsp+A0h] [rbp-258h]
  char v48; // [rsp+A8h] [rbp-250h]
  MemoryBlock *v49; // [rsp+B0h] [rbp-248h] BYREF
  struct _GUID v50; // [rsp+C0h] [rbp-238h] BYREF
  char v51; // [rsp+102h] [rbp-1F6h]
  double v52; // [rsp+118h] [rbp-1E0h]
  __int64 v53; // [rsp+270h] [rbp-88h] BYREF
  __int64 v54; // [rsp+290h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2F8h] [rbp+0h]
  __int64 v56; // [rsp+318h] [rbp+20h] BYREF
  va_list va; // [rsp+318h] [rbp+20h]
  PoisonedPageContainer *v58; // [rsp+320h] [rbp+28h]
  __int64 v59; // [rsp+328h] [rbp+30h]
  RTL_SRWLOCK *v60; // [rsp+330h] [rbp+38h]
  va_list va1; // [rsp+338h] [rbp+40h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v56 = va_arg(va1, _QWORD);
  v58 = va_arg(va1, PoisonedPageContainer *);
  v59 = va_arg(va1, _QWORD);
  v60 = va_arg(va1, RTL_SRWLOCK *);
  v46 = a2;
  v6 = v58;
  v7 = v59;
  v44 = v59;
  v8 = (__int64)v60;
  v45 = v60;
  v41 = (__int64)operator new(0xF8u);
  memset_0((void *)v41, 0, 0xF8u);
  v49 = MemoryBlock::MemoryBlock((MemoryBlock *)v41);
  v47 = &v49;
  v48 = 1;
  memset_0(&v50, 0, 0x1B0u);
  MemoryTrace<VmWorkerTrace::CreateRamMemoryBlock>::MemoryTrace<VmWorkerTrace::CreateRamMemoryBlock>((__int64)&v50, v8);
  if ( v7 )
    v9 = *(_QWORD *)(v7 + 8);
  else
    v9 = 0;
  v43 = v9;
  v10 = a2 + 9;
  if ( v6 )
    v11 = *((_QWORD *)v6 + 1);
  else
    v11 = 0;
  v41 = v11;
  v12 = (char *)a2 + 65;
  LODWORD(v42) = a3 & 1;
  v13 = a2 + 2;
  MemoryTrace<VmWorkerTrace::CreateRamMemoryBlock>::Start<unsigned __int64 &,unsigned __int64 &,unsigned __int64 &,unsigned __int64 &,int,unsigned __int64 &,unsigned __int64 &,unsigned char &,unsigned __int64,unsigned __int64 &,unsigned __int64>(
    &v50,
    (__int64)(a2 + 3),
    (__int64)&v42,
    (__int64)(a2 + 5),
    (__int64)va,
    (__int64)a2 + 65,
    (__int64)&v41,
    (__int64)(a2 + 9),
    (__int64)&v43);
  try
  {
    *((_QWORD *)v49 + 20) = a1;
    *(_BYTE *)v49 = *v13 & 1;
    *((_BYTE *)v49 + 1) = a3 & 1;
    *((_BYTE *)v49 + 2) = (a3 & 2) != 0;
    *((_BYTE *)v49 + 3) = (a3 & 4) != 0;
    *((_QWORD *)v49 + 21) = *(_QWORD *)v13;
    *((_BYTE *)v49 + 184) = *v12;
    v15 = *(_QWORD *)v13;
    v41 = v15;
    if ( (v15 & 0x40) != 0 )
    {
      v16 = *v10;
      v17 = (unsigned __int8)*v12;
      v18 = (const char *)*a2;
      LOBYTE(v14) = v17;
      DaxFileMemoryBlock = VidCreateDaxFileMemoryBlock(
                             *((_QWORD *)v49 + 20),
                             *a2,
                             v15,
                             v14,
                             v16,
                             v44,
                             (char *)v49 + 152);
      LODWORD(v39) = v17;
      wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(
        retaddr,
        (void *)0xD0,
        (unsigned int)"onecore\\vm\\worker\\memory\\memoryblock.cpp",
        (const char *)DaxFileMemoryBlock,
        (int)"PageCountTotal = %I64x, MbCreateFlags = %I64x, VirtualNode = %u, PersistId = %I64u",
        v18,
        v15,
        v39,
        v16);
    }
    else
    {
      v20 = *v10;
      v21 = (unsigned __int8)*v12;
      v22 = a2[5];
      v23 = a2[1];
      v24 = (const char *)*a2;
      MemoryBlock = VidCreateMemoryBlock(*((_QWORD *)v49 + 20), a2, (char *)v49 + 152);
      LODWORD(v40) = v21;
      wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(
        retaddr,
        (void *)0xE1,
        (unsigned int)"onecore\\vm\\worker\\memory\\memoryblock.cpp",
        (const char *)MemoryBlock,
        (int)"PageCountTotal = %I64x, PageCountValid = %I64x, MbCreateFlags = %I64x, BackingBitmapBufferSizeInBytes = %I6"
             "4u, VirtualNode = %u, PersistId = %I64u",
        v24,
        v23,
        v41,
        v22,
        v40,
        v20);
      v13 = a2 + 2;
    }
    if ( (*v13 & 8) != 0
      && !(unsigned int)VidQueryMemoryBlockInformation(
                          *((_QWORD *)v49 + 20),
                          *((_QWORD *)v49 + 19),
                          0,
                          0,
                          0,
                          (char *)v49 + 240,
                          8,
                          0) )
    {
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0xF2,
        (unsigned int)"onecore\\vm\\worker\\memory\\memoryblock.cpp",
        v26);
    }
    *((_QWORD *)v49 + 14) = *a2;
    v27 = (wil *)a2[1];
    *((_QWORD *)v49 + 15) = v27;
  }
  catch ( ... )
  {
    v35 = wil::ResultFromCaughtException(v27);
    v36 = v35;
    LODWORD(v36) = v35 & 0xEFFFFFFF;
    _snwprintf_s<16>(&v53, 16, L"%%%%%u", v36);
    v37 = v35;
    LODWORD(v37) = v35 & 0xEFFFFFFF;
    _snwprintf_s<16>(&v54, 16, L"0x%08X", v37);
    if ( v35 == -2147023446 || v35 + 1070137301 <= 1 )
    {
      if ( v35 == -1070137301 )
      {
        v38 = 2;
      }
      else
      {
        v38 = 1;
        if ( v35 == -1070137300 )
          v38 = 3;
      }
      MemoryManager::VmStartOutOfMemoryErrorPopulateCache(
        (__int64)&MemoryManager::m_Instance,
        0,
        2,
        v38,
        *((_BYTE *)v46 + 65),
        v46[1],
        v46[2]);
      SetLastError(0x5AAu);
    }
    throw;
  }
  *((_QWORD *)v49 + 16) = v56;
  if ( v6 )
  {
    if ( (*v13 & 0x44) == 0 )
      PoisonedPageContainer::Mark((__int64 **)v6, *((void **)v49 + 20), *((void **)v49 + 19));
    v28 = (char *)v49 + 192;
    if ( (MemoryBlock *)((char *)v49 + 192) != v6 )
    {
      std::_Tree<std::_Tset_traits<HyperVStorageObjectTable *,std::less<HyperVStorageObjectTable *>,std::allocator<HyperVStorageObjectTable *>,0>>::clear((char *)v49 + 192);
      std::_Tree<std::_Tset_traits<unsigned __int64,std::less<unsigned __int64>,std::allocator<unsigned __int64>,0>>::_Copy<0>(
        v28,
        v6);
    }
  }
  if ( (*v13 & 4) != 0 )
    *((_QWORD *)v49 + 26) = a2[9];
  v29 = MemoryTrace<VmWorkerTrace::CreateRamMemoryBlock>::Stop(&v50);
  MemoryTraceTracker::IncreaseTimeSpentInOperation(v45, (__int64)&off_1402DACF8, v29);
  v30 = v49;
  if ( *(_BYTE *)v49 )
  {
    v31 = v51 ? v52 : 0.0;
    if ( *(_QWORD *)MemoryManagerStats::gm_SingletonInstance )
    {
      v32 = v31 * 1000000.0;
      v33 = 0;
      if ( v32 >= 9.223372036854776e18 )
      {
        v32 = v32 - 9.223372036854776e18;
        if ( v32 < 9.223372036854776e18 )
          v33 = 0x8000000000000000uLL;
      }
      _InterlockedAdd64(
        (volatile signed __int64 *)(**(_QWORD **)MemoryManagerStats::gm_SingletonInstance
                                  + *(unsigned int *)(*((_QWORD *)MemoryManagerStats::gm_SingletonInstance + 1) + 220LL)),
        v33 + (unsigned int)(int)v32);
      v30 = v49;
    }
  }
  MemoryTrace<VmWorkerTrace::CreateRamMemoryBlock>::~MemoryTrace<VmWorkerTrace::CreateRamMemoryBlock>(&v50);
  return v30;
}

```

## disassembly

```asm
0x1402134e8  mov     [rsp+arg_18], r9
0x1402134ed  push    rbx
0x1402134ee  push    rsi
0x1402134ef  push    rdi
0x1402134f0  push    r12
0x1402134f2  push    r13
0x1402134f4  push    r14
0x1402134f6  push    r15
0x1402134f8  sub     rsp, 2C0h
0x1402134ff  mov     rax, cs:__security_cookie
0x140213506  xor     rax, rsp
0x140213509  mov     [rsp+2F8h+var_48], rax
0x140213511  mov     ebx, r8d
0x140213514  mov     r12, rdx
0x140213517  mov     r15, rcx
0x14021351a  mov     [rsp+2F8h+var_268], rdx
0x140213522  mov     r13, [rsp+2F8h+arg_20]
0x14021352a  mov     rsi, [rsp+2F8h+arg_28]
0x140213532  mov     [rsp+2F8h+var_280], rsi
0x140213537  mov     r14, [rsp+2F8h+arg_30]
0x14021353f  mov     [rsp+2F8h+var_278], r14
0x140213547  mov     ecx, 0F8h; Size
0x14021354c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140213551  mov     rdi, rax
0x140213554  mov     [rsp+2F8h+var_298], rax
0x140213559  xor     edx, edx; Val
0x14021355b  mov     r8d, 0F8h; Size
0x140213561  mov     rcx, rax; void *
0x140213564  call    memset_0
0x140213569  mov     rcx, rdi; this
0x14021356c  call    ??0MemoryBlock@@AEAA@XZ; MemoryBlock::MemoryBlock(void)
0x140213571  nop
0x140213572  mov     [rsp+2F8h+var_248], rax
0x14021357a  lea     rax, [rsp+2F8h+var_248]
0x140213582  mov     [rsp+2F8h+var_258], rax
0x14021358a  mov     [rsp+2F8h+var_250], 1
0x140213592  xor     edx, edx; Val
0x140213594  mov     r8d, 1B0h; Size
0x14021359a  lea     rcx, [rsp+2F8h+var_238]; void *
0x1402135a2  call    memset_0
0x1402135a7  mov     rdx, r14
0x1402135aa  lea     rcx, [rsp+2F8h+var_238]
0x1402135b2  call    ??0?$MemoryTrace@VCreateRamMemoryBlock@VmWorkerTrace@@@@QEAA@AEBUMemoryTraceTracker@@@Z; MemoryTrace<VmWorkerTrace::CreateRamMemoryBlock>::MemoryTrace<VmWorkerTrace::CreateRamMemoryBlock>(MemoryTraceTracker const &)
0x1402135b7  nop
0x1402135b8  test    rsi, rsi
0x1402135bb  jz      short loc_1402135C3
0x1402135bd  mov     rax, [rsi+8]
0x1402135c1  jmp     short loc_1402135C5
0x1402135c3  xor     eax, eax
0x1402135c5  mov     [rsp+2F8h+var_288], rax
0x1402135ca  lea     rdi, [r12+48h]
0x1402135cf  test    r13, r13
0x1402135d2  jz      short loc_1402135DA
0x1402135d4  mov     rax, [r13+8]
0x1402135d8  jmp     short loc_1402135DC
0x1402135da  xor     eax, eax
0x1402135dc  mov     [rsp+2F8h+var_298], rax
0x1402135e1  lea     rsi, [r12+41h]
0x1402135e6  lea     rdx, [r12+28h]
0x1402135eb  mov     eax, ebx
0x1402135ed  and     eax, 1
0x1402135f0  mov     dword ptr [rsp+2F8h+var_290], eax
0x1402135f4  lea     r14, [r12+10h]
0x1402135f9  lea     rax, [r12+18h]
0x1402135fe  lea     r8, [rsp+2F8h+var_288]
0x140213603  mov     [rsp+2F8h+var_2A0], r8; __int64
0x140213608  mov     [rsp+2F8h+var_2A8], rdi; __int64
0x14021360d  lea     r8, [rsp+2F8h+var_298]
0x140213612  mov     [rsp+2F8h+var_2B0], r8; __int64
0x140213617  mov     [rsp+2F8h+var_2B8], rsi; __int64
0x14021361c  lea     r8, [rsp+2F8h+arg_18]
0x140213624  mov     [rsp+2F8h+var_2C0], r8; __int64
0x140213629  mov     [rsp+2F8h+var_2C8], rdx; __int64
0x14021362e  lea     rdx, [rsp+2F8h+var_290]
0x140213633  mov     [rsp+2F8h+var_2D0], rdx; __int64
0x140213638  mov     [rsp+2F8h+var_2D8], rax; __int64
0x14021363d  mov     r9, r14
0x140213640  lea     r8, [r12+8]
0x140213645  mov     rdx, r12
0x140213648  lea     rcx, [rsp+2F8h+var_238]; struct _GUID *
0x140213650  call    ??$Start@AEA_KAEA_KAEA_KAEA_KHAEA_KAEA_KAEAE_KAEA_K_K@?$MemoryTrace@VCreateRamMemoryBlock@VmWorkerTrace@@@@QEAAXAEA_K000$$QEAH00AEAE$$QEA_K03@Z; MemoryTrace<VmWorkerTrace::CreateRamMemoryBlock>::Start<unsigned __int64 &,unsigned __int64 &,unsigned __int64 &,unsigned __int64 &,int,unsigned __int64 &,unsigned __int64 &,uchar &,unsigned __int64,unsigned __int64 &,unsigned __int64>(unsigned __int64 &,unsigned __int64 &,unsigned __int64 &,unsigned __int64 &,int &&,unsigned __int64 &,unsigned __int64 &,uchar &,unsigned __int64 &&,unsigned __int64 &,unsigned __int64 &&)
0x140213655  mov     rax, [rsp+2F8h+var_248]
0x14021365d  mov     [rax+0A0h], r15
0x140213664  mov     cl, [r14]
0x140213667  and     cl, 1
0x14021366a  mov     rax, [rsp+2F8h+var_248]
0x140213672  mov     [rax], cl
0x140213674  mov     cl, bl
0x140213676  and     cl, 1
0x140213679  mov     rax, [rsp+2F8h+var_248]
0x140213681  mov     [rax+1], cl
0x140213684  mov     ecx, ebx
0x140213686  shr     ecx, 1
0x140213688  and     cl, 1
0x14021368b  mov     rax, [rsp+2F8h+var_248]
0x140213693  mov     [rax+2], cl
0x140213696  shr     ebx, 2
0x140213699  and     bl, 1
0x14021369c  mov     rax, [rsp+2F8h+var_248]
0x1402136a4  mov     [rax+3], bl
0x1402136a7  mov     rcx, [r14]
0x1402136aa  mov     rax, [rsp+2F8h+var_248]
0x1402136b2  mov     [rax+0A8h], rcx
0x1402136b9  mov     cl, [rsi]
0x1402136bb  mov     rax, [rsp+2F8h+var_248]
0x1402136c3  mov     [rax+0B8h], cl
0x1402136c9  mov     r15, [r14]
0x1402136cc  mov     [rsp+2F8h+var_298], r15
0x1402136d1  mov     rcx, [rsp+2F8h+var_248]
0x1402136d9  test    r15b, 40h
0x1402136dd  jz      loc_140213764
0x1402136e3  mov     rdi, [rdi]
0x1402136e6  movzx   ebx, byte ptr [rsi]
0x1402136e9  mov     rsi, [r12]
0x1402136ed  lea     rax, [rcx+98h]
0x1402136f4  mov     [rsp+2F8h+var_2C8], rax
0x1402136f9  mov     rax, [rsp+2F8h+var_280]
0x1402136fe  mov     [rsp+2F8h+var_2D0], rax
0x140213703  mov     [rsp+2F8h+var_2D8], rdi
0x140213708  mov     r9b, bl
0x14021370b  mov     r8, r15
0x14021370e  mov     rdx, rsi
0x140213711  mov     rcx, [rcx+0A0h]
0x140213718  call    cs:__imp_VidCreateDaxFileMemoryBlock
0x14021371f  nop     dword ptr [rax+rax+00h]
0x140213724  mov     rcx, [rsp+2F8h]; this
0x14021372c  mov     [rsp+2F8h+var_2B8], rdi
0x140213731  mov     dword ptr [rsp+2F8h+var_2C0], ebx
0x140213735  mov     [rsp+2F8h+var_2C8], r15
0x14021373a  mov     [rsp+2F8h+var_2D0], rsi; char *
0x14021373f  lea     rdx, aPagecounttotal_1; "PageCountTotal = %I64x, MbCreateFlags ="...
0x140213746  mov     [rsp+2F8h+var_2D8], rdx; int
0x14021374b  mov     r9d, eax; char *
0x14021374e  lea     r8, aOnecoreVmWorke_68; "onecore\\vm\\worker\\memory\\memorybloc"...
0x140213755  mov     edx, 0D0h; void *
0x14021375a  call    ?Throw_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x14021375f  jmp     loc_1402137E4
0x140213764  mov     rbx, [rdi]
0x140213767  movzx   edi, byte ptr [rsi]
0x14021376a  mov     rsi, [r12+28h]
0x14021376f  mov     r14, [r12+8]
0x140213774  mov     r15, [r12]
0x140213778  lea     r8, [rcx+98h]
0x14021377f  mov     rdx, r12
0x140213782  mov     rcx, [rcx+0A0h]
0x140213789  call    cs:__imp_VidCreateMemoryBlock
0x140213790  nop     dword ptr [rax+rax+00h]
0x140213795  mov     rcx, [rsp+2F8h]; this
0x14021379d  mov     [rsp+2F8h+var_2A8], rbx
0x1402137a2  mov     dword ptr [rsp+2F8h+var_2B0], edi
0x1402137a6  mov     [rsp+2F8h+var_2B8], rsi
0x1402137ab  mov     rdx, [rsp+2F8h+var_298]
0x1402137b0  mov     [rsp+2F8h+var_2C0], rdx
0x1402137b5  mov     [rsp+2F8h+var_2C8], r14
0x1402137ba  mov     [rsp+2F8h+var_2D0], r15; char *
0x1402137bf  lea     rdx, aPagecounttotal; "PageCountTotal = %I64x, PageCountValid "...
0x1402137c6  mov     [rsp+2F8h+var_2D8], rdx; int
0x1402137cb  mov     r9d, eax; char *
0x1402137ce  lea     r8, aOnecoreVmWorke_68; "onecore\\vm\\worker\\memory\\memorybloc"...
0x1402137d5  mov     edx, 0E1h; void *
0x1402137da  call    ?Throw_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x1402137df  lea     r14, [r12+10h]
0x1402137e4  test    byte ptr [r14], 8
0x1402137e8  jz      short loc_140213854
0x1402137ea  mov     rcx, [rsp+2F8h+var_248]
0x1402137f2  lea     rax, [rcx+0F0h]
0x1402137f9  mov     [rsp+2F8h+var_2C0], 0
0x140213802  mov     dword ptr [rsp+2F8h+var_2C8], 8
0x14021380a  mov     [rsp+2F8h+var_2D0], rax
0x14021380f  mov     dword ptr [rsp+2F8h+var_2D8], 0
0x140213817  xor     r9d, r9d
0x14021381a  xor     r8d, r8d
0x14021381d  mov     rdx, [rcx+98h]
0x140213824  mov     rcx, [rcx+0A0h]
0x14021382b  call    cs:__imp_VidQueryMemoryBlockInformation
0x140213832  nop     dword ptr [rax+rax+00h]
0x140213837  mov     rcx, [rsp+2F8h]; this
0x14021383f  test    eax, eax
0x140213841  jnz     short loc_140213854
0x140213843  lea     r8, aOnecoreVmWorke_68; "onecore\\vm\\worker\\memory\\memorybloc"...
0x14021384a  mov     edx, 0F2h; void *
0x14021384f  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140213854  mov     rcx, [r12]
0x140213858  mov     rax, [rsp+2F8h+var_248]
0x140213860  mov     [rax+70h], rcx
0x140213864  mov     rcx, [r12+8]
0x140213869  mov     rax, [rsp+2F8h+var_248]
0x140213871  mov     [rax+78h], rcx
0x140213875  mov     rax, [rsp+2F8h+var_248]
0x14021387d  mov     rcx, [rsp+2F8h+arg_18]
0x140213885  mov     [rax+80h], rcx
0x14021388c  test    r13, r13
0x14021388f  jz      short loc_1402138DC
0x140213891  test    byte ptr [r14], 44h
0x140213895  jnz     short loc_1402138B5
0x140213897  mov     rdx, [rsp+2F8h+var_248]
0x14021389f  mov     r8, [rdx+98h]; void *
0x1402138a6  mov     rdx, [rdx+0A0h]; void *
0x1402138ad  mov     rcx, r13; this
0x1402138b0  call    ?Mark@PoisonedPageContainer@@QEAAXPEAX0@Z; PoisonedPageContainer::Mark(void *,void *)
0x1402138b5  mov     rbx, [rsp+2F8h+var_248]
0x1402138bd  add     rbx, 0C0h
0x1402138c4  cmp     rbx, r13
0x1402138c7  jz      short loc_1402138DC
0x1402138c9  mov     rcx, rbx
0x1402138cc  call    ?clear@?$_Tree@V?$_Tset_traits@PEAVHyperVStorageObjectTable@@U?$less@PEAVHyperVStorageObjectTable@@@std@@V?$allocator@PEAVHyperVStorageObjectTable@@@3@$0A@@std@@@std@@QEAAXXZ; std::_Tree<std::_Tset_traits<HyperVStorageObjectTable *,std::less<HyperVStorageObjectTable *>,std::allocator<HyperVStorageObjectTable *>,0>>::clear(void)
0x1402138d1  mov     rdx, r13
0x1402138d4  mov     rcx, rbx
0x1402138d7  call    ??$_Copy@$0A@@?$_Tree@V?$_Tset_traits@_KU?$less@_K@std@@V?$allocator@_K@2@$0A@@std@@@std@@IEAAXAEBV01@@Z; std::_Tree<std::_Tset_traits<unsigned __int64,std::less<unsigned __int64>,std::allocator<unsigned __int64>,0>>::_Copy<0>(std::_Tree<std::_Tset_traits<unsigned __int64,std::less<unsigned __int64>,std::allocator<unsigned __int64>,0>> const &)
0x1402138dc  test    byte ptr [r14], 4
0x1402138e0  jz      short loc_1402138F6
0x1402138e2  mov     rdx, [r12+48h]
0x1402138e7  mov     rax, [rsp+2F8h+var_248]
0x1402138ef  mov     [rax+0D0h], rdx
0x1402138f6  lea     rcx, [rsp+2F8h+var_238]
0x1402138fe  call    ?Stop@?$MemoryTrace@VCreateRamMemoryBlock@VmWorkerTrace@@@@QEAANXZ; MemoryTrace<VmWorkerTrace::CreateRamMemoryBlock>::Stop(void)
0x140213903  movaps  xmm2, xmm0
0x140213906  lea     rdx, off_1402DACF8; "CreatingRamMemoryBlocks"
0x14021390d  mov     rcx, [rsp+2F8h+var_278]
0x140213915  call    ?IncreaseTimeSpentInOperation@MemoryTraceTracker@@QEAAXAEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@N@Z; MemoryTraceTracker::IncreaseTimeSpentInOperation(std::basic_string_view<ushort> const &,double)
0x14021391a  mov     rbx, [rsp+2F8h+var_248]
0x140213922  cmp     byte ptr [rbx], 0
0x140213925  jz      short loc_14021399E
0x140213927  mov     rcx, cs:?gm_SingletonInstance@MemoryManagerStats@@0PEAV1@EA; MemoryManagerStats * MemoryManagerStats::gm_SingletonInstance
0x14021392e  cmp     [rsp+2F8h+var_1F6], 0
0x140213936  jz      short loc_140213943
0x140213938  movsd   xmm0, [rsp+2F8h+var_1E0]
0x140213941  jmp     short loc_140213946
0x140213943  xorps   xmm0, xmm0
0x140213946  mov     r8, [rcx]
0x140213949  test    r8, r8
0x14021394c  jz      short loc_14021399E
0x14021394e  mulsd   xmm0, cs:__real@412e848000000000
0x140213956  xor     eax, eax
0x140213958  movsd   xmm1, cs:__real@43e0000000000000
0x140213960  comisd  xmm0, xmm1
0x140213964  jb      short loc_14021397D
0x140213966  subsd   xmm0, xmm1
0x14021396a  comisd  xmm0, xmm1
0x14021396e  jnb     short loc_14021397D
0x140213970  mov     rdx, 8000000000000000h
0x14021397a  mov     rax, rdx
0x14021397d  cvttsd2si rdx, xmm0
0x140213982  add     rdx, rax
0x140213985  mov     rax, [rcx+8]
0x140213989  mov     ecx, [rax+0DCh]
0x14021398f  add     rcx, [r8]
0x140213992  lock add [rcx], rdx
0x140213996  mov     rbx, [rsp+2F8h+var_248]
0x14021399e  lea     rcx, [rsp+2F8h+var_238]
0x1402139a6  call    ??1?$MemoryTrace@VCreateRamMemoryBlock@VmWorkerTrace@@@@QEAA@XZ; MemoryTrace<VmWorkerTrace::CreateRamMemoryBlock>::~MemoryTrace<VmWorkerTrace::CreateRamMemoryBlock>(void)
0x1402139ab  nop
0x1402139ac  mov     rax, rbx
0x1402139af  mov     rcx, [rsp+2F8h+var_48]
0x1402139b7  xor     rcx, rsp; StackCookie
0x1402139ba  call    __security_check_cookie
0x1402139bf  add     rsp, 2C0h
0x1402139c6  pop     r15
0x1402139c8  pop     r14
0x1402139ca  pop     r13
0x1402139cc  pop     r12
0x1402139ce  pop     rdi
0x1402139cf  pop     rsi
0x1402139d0  pop     rbx
0x1402139d1  retn
```
