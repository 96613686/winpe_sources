# CacheWriter::AddElement(IBaseCacheContext *,IElementConstructionTask *,CachedElementData *,uint)

- ea: `0x18001112c`
- end: `0x18001131c`
- name: `?AddElement@CacheWriter@@QEAAXPEAUIBaseCacheContext@@PEAVIElementConstructionTask@@PEAUCachedElementData@@I@Z`
- size: `496`
- prototype: `void __usercall(CacheWriter *__hidden this@<rcx>, struct IBaseCacheContext *@<rdx>, struct IElementConstructionTask *@<r8>, struct CachedElementData *@<r9>, unsigned int)`
- caller_count: `8`
- callee_count: `15`
- tags: `registry_config, service_task`

## callers

- `0x180011020`
- `0x1800412c0`
- `0x180041d18`
- `0x1800b7840`
- `0x1800c6c00`
- `0x1800c6d10`
- `0x1800c6e20`
- `0x1800c6f30`

## callees

- `0x1800047d4`
- `0x18001112c`
- `0x180011840`
- `0x1800548a0`
- `0x180054930`
- `0x180054970`
- `0x1800549b0`
- `0x180054d30`
- `0x180076620`
- `0x180076ca4`
- `0x18007b2b0`
- `0x18008f4dc`
- `0x1800ab1b0`
- `0x1800b7db0`
- `0x1800e6010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800112d6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800112d6`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CacheWriter::AddElement(
        LPCRITICAL_SECTION *this,
        struct IBaseCacheContext *a2,
        struct IElementConstructionTask *a3,
        struct CachedElementData *a4,
        unsigned int a5)
{
  unsigned int v9; // eax
  __int128 *Range; // rax
  __int128 v11; // xmm6
  unsigned int v12; // ebx
  LPCRITICAL_SECTION v13; // rax
  unsigned int OwningThread_high; // ecx
  unsigned int v15; // r14d
  unsigned __int64 v16; // rdx
  __int64 v17; // r15
  LPCRITICAL_SECTION v18; // r12
  __int64 v19; // r9
  __int64 v20; // r8
  LPCRITICAL_SECTION v21; // rcx
  LPCRITICAL_SECTION v22; // rax
  LPCRITICAL_SECTION v23; // rax
  LPCRITICAL_SECTION lpCriticalSection[2]; // [rsp+30h] [rbp-50h] BYREF
  __int128 v25; // [rsp+40h] [rbp-40h] BYREF
  _OWORD pExceptionObject[2]; // [rsp+50h] [rbp-30h] BYREF
  unsigned int v27; // [rsp+C0h] [rbp+40h] BYREF
  __int64 v28; // [rsp+D0h] [rbp+50h] BYREF

  v27 = 0;
  *(_QWORD *)&v25 = 0;
  DWORD2(v25) = 0;
  LowMemoryPriority::LowMemoryPriority((LowMemoryPriority *)&v28);
  v9 = (*(__int64 (__fastcall **)(struct IElementConstructionTask *, struct IBaseCacheContext *, LPCRITICAL_SECTION *, unsigned int *, __int128 *))(*(_QWORD *)a3 + 16LL))(
         a3,
         a2,
         this,
         &v27,
         &v25);
  lpCriticalSection[0] = this[2];
  LODWORD(lpCriticalSection[1]) = *((_DWORD *)this + 31);
  Range = (__int128 *)CheckedPtr<unsigned char const,FailAsExceptionPolicy<InvalidCacheDataException>,unsigned int>::GetRange(
                        lpCriticalSection,
                        pExceptionObject,
                        v27,
                        v9);
  v11 = *Range;
  v12 = a5;
  if ( this[13] && !a5 )
  {
    pExceptionObject[0] = *Range;
    v12 = ((__int64 (__fastcall *)(LPCRITICAL_SECTION *, _OWORD *))g_elementCheckSumProcedures[*((_DWORD *)a3 + 12) - 1])(
            lpCriticalSection,
            pExceptionObject);
  }
  LowMemoryPriority::~LowMemoryPriority((LowMemoryPriority *)&v28);
  LockHolder::LockHolder((LockHolder *)lpCriticalSection, (struct Lock *)(this + 4));
  v13 = this[9];
  OwningThread_high = HIDWORD(v13->OwningThread);
  if ( OwningThread_high >= LODWORD(v13->LockSemaphore) )
  {
    CacheOverflowException::CacheOverflowException(
      (CacheOverflowException *)pExceptionObject,
      (struct CacheWriter *)this,
      0);
    throw (CacheOverflowException *)pExceptionObject;
  }
  v15 = OwningThread_high + 1;
  HIDWORD(v13->OwningThread) = OwningThread_high + 1;
  v16 = OwningThread_high;
  v17 = 2LL * OwningThread_high;
  v18 = this[11];
  v19 = *((unsigned int *)a3 + 10);
  v28 = v19;
  v20 = (unsigned int)v19 & (this[9]->LockCount - 1);
  v21 = this[10];
  *((_DWORD *)&v18->DebugInfo + 2 * v17) = *((_DWORD *)&v21->DebugInfo + v20);
  *((_DWORD *)&v18->DebugInfo + 2 * v17 + 1) = v19;
  *(&v18->LockCount + 2 * v17) = *((_DWORD *)a3 + 12);
  *(&v18->RecursionCount + 2 * v17) = v27;
  v22 = this[13];
  if ( v22 )
    *((_DWORD *)&v22->DebugInfo + v16) = v12;
  v23 = this[14];
  if ( v23 )
    *((_BYTE *)&v23->DebugInfo + v16) = 1;
  _mm_sfence();
  *((_DWORD *)&v21->DebugInfo + v20) = v15;
  if ( this[12] )
  {
    CacheWriter::MarkRecentElement((CacheWriter *)this, (const struct LockHolder *)v16, v15);
    LODWORD(v19) = v28;
  }
  *(_DWORD *)a4 = v19;
  *((_DWORD *)a4 + 2) = *(&v18->LockCount + 2 * v17);
  *((_DWORD *)a4 + 1) = v15;
  *((_OWORD *)a4 + 1) = v11;
  *((_OWORD *)a4 + 2) = v25;
  IntrusivePtr<ICacheReference>::Assign((char *)a4 + 48, this);
  *((_BYTE *)a4 + 56) = 1;
  *((_BYTE *)a4 + 57) = *((_BYTE *)a3 + 97);
  LeaveCriticalSection(lpCriticalSection[0]);
}

```

## disassembly

```asm
0x18001112c  mov     [rsp-38h+arg_8], rbx
0x180011131  push    rbp
0x180011132  push    rsi
0x180011133  push    rdi
0x180011134  push    r12
0x180011136  push    r13
0x180011138  push    r14
0x18001113a  push    r15
0x18001113c  mov     rbp, rsp
0x18001113f  sub     rsp, 80h
0x180011146  movaps  [rsp+80h+var_10], xmm6
0x18001114b  mov     rsi, r9
0x18001114e  mov     r13, r8
0x180011151  mov     rbx, rdx
0x180011154  mov     rdi, rcx
0x180011157  xor     r14d, r14d
0x18001115a  mov     [rbp+arg_0], r14d
0x18001115e  mov     qword ptr [rbp+var_40], r14
0x180011162  mov     dword ptr [rbp+var_40+8], r14d
0x180011166  lea     rcx, [rbp+arg_10]; this
0x18001116a  call    ??0LowMemoryPriority@@QEAA@XZ; LowMemoryPriority::LowMemoryPriority(void)
0x18001116f  nop
0x180011170  mov     rax, [r13+0]
0x180011174  lea     rcx, [rbp+var_40]
0x180011178  mov     [rsp+80h+var_60], rcx
0x18001117d  lea     r9, [rbp+arg_0]
0x180011181  mov     r8, rdi
0x180011184  mov     rdx, rbx
0x180011187  mov     rcx, r13
0x18001118a  mov     rax, [rax+10h]
0x18001118e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011193  mov     rcx, [rdi+10h]
0x180011197  mov     [rbp+lpCriticalSection], rcx
0x18001119b  mov     ecx, [rdi+7Ch]
0x18001119e  mov     dword ptr [rbp+lpCriticalSection+8], ecx
0x1800111a1  mov     r9d, eax
0x1800111a4  mov     r8d, [rbp+arg_0]
0x1800111a8  lea     rdx, [rbp+pExceptionObject]
0x1800111ac  lea     rcx, [rbp+lpCriticalSection]
0x1800111b0  call    ?GetRange@?$CheckedPtr@$$CBEV?$FailAsExceptionPolicy@VInvalidCacheDataException@@@@I@@QEBA?AV1@_K0@Z; CheckedPtr<uchar const,FailAsExceptionPolicy<InvalidCacheDataException>,uint>::GetRange(unsigned __int64,unsigned __int64)
0x1800111b5  movups  xmm6, xmmword ptr [rax]
0x1800111b8  mov     ebx, [rbp+arg_20]
0x1800111bb  cmp     [rdi+68h], r14
0x1800111bf  jz      short loc_1800111F3
0x1800111c1  test    ebx, ebx
0x1800111c3  jnz     short loc_1800111F3
0x1800111c5  movdqu  [rbp+pExceptionObject], xmm6
0x1800111ca  movaps  xmm1, xmmword ptr [rbp+lpCriticalSection]
0x1800111ce  movdqa  xmmword ptr [rbp+lpCriticalSection], xmm1
0x1800111d3  mov     ecx, [r13+30h]
0x1800111d7  dec     ecx
0x1800111d9  lea     rax, ?g_elementCheckSumProcedures@@3QBQ6AIV?$CheckedPtr@$$CBEV?$FailAsExceptionPolicy@VInvalidCacheDataException@@@@I@@0@ZB; uint (*const near * const g_elementCheckSumProcedures)(CheckedPtr<uchar const,FailAsExceptionPolicy<InvalidCacheDataException>,uint>,CheckedPtr<uchar const,FailAsExceptionPolicy<InvalidCacheDataException>,uint>)
0x1800111e0  mov     rax, ds:(?g_elementCheckSumProcedures@@3QBQ6AIV?$CheckedPtr@$$CBEV?$FailAsExceptionPolicy@VInvalidCacheDataException@@@@I@@0@ZB - 1800E8C30h)[rax+rcx*8]; uint (*const near * const g_elementCheckSumProcedures)(CheckedPtr<uchar const,FailAsExceptionPolicy<InvalidCacheDataException>,uint>,CheckedPtr<uchar const,FailAsExceptionPolicy<InvalidCacheDataException>,uint>)
0x1800111e4  lea     rdx, [rbp+pExceptionObject]
0x1800111e8  lea     rcx, [rbp+lpCriticalSection]
0x1800111ec  call    _guard_dispatch_icall$thunk$10345483385596137414; GlyphDataElement<GlyphPaintLayout,GlyphPaintRasterizationParameters,GlyphPaintRasterizationState>::ComputeCheckSum(CheckedPtr<uchar const,FailAsExceptionPolicy<InvalidCacheDataException>,uint>,CheckedPtr<uchar const,FailAsExceptionPolicy<InvalidCacheDataException>,uint>)
0x1800111f1  mov     ebx, eax
0x1800111f3  lea     rcx, [rbp+arg_10]; this
0x1800111f7  call    ??1LowMemoryPriority@@QEAA@XZ; LowMemoryPriority::~LowMemoryPriority(void)
0x1800111fc  lea     rdx, [rdi+20h]; struct Lock *
0x180011200  lea     rcx, [rbp+lpCriticalSection]; this
0x180011204  call    ??0LockHolder@@QEAA@AEAVLock@@@Z; LockHolder::LockHolder(Lock &)
0x180011209  nop
0x18001120a  mov     rax, [rdi+48h]
0x18001120e  mov     ecx, [rax+14h]
0x180011211  cmp     ecx, [rax+18h]
0x180011214  jnb     loc_1800112FC
0x18001121a  lea     r14d, [rcx+1]
0x18001121e  mov     [rax+14h], r14d
0x180011222  mov     edx, ecx; struct LockHolder *
0x180011224  mov     r15d, ecx
0x180011227  add     r15, r15
0x18001122a  mov     r12, [rdi+58h]
0x18001122e  mov     r9d, [r13+28h]
0x180011232  mov     [rbp+arg_10], r9
0x180011236  mov     rax, [rdi+48h]
0x18001123a  mov     r8d, [rax+8]
0x18001123e  dec     r8d
0x180011241  and     r8, r9
0x180011244  mov     rcx, [rdi+50h]
0x180011248  mov     eax, [rcx+r8*4]
0x18001124c  mov     [r12+r15*8], eax
0x180011250  mov     [r12+r15*8+4], r9d
0x180011255  mov     eax, [r13+30h]
0x180011259  mov     [r12+r15*8+8], eax
0x18001125e  mov     eax, [rbp+arg_0]
0x180011261  mov     [r12+r15*8+0Ch], eax
0x180011266  mov     rax, [rdi+68h]
0x18001126a  test    rax, rax
0x18001126d  jz      short loc_180011272
0x18001126f  mov     [rax+rdx*4], ebx
0x180011272  mov     rax, [rdi+70h]
0x180011276  test    rax, rax
0x180011279  jz      short loc_18001127F
0x18001127b  mov     byte ptr [rax+rdx], 1
0x18001127f  nop
0x180011280  sfence
0x180011283  nop
0x180011284  mov     [rcx+r8*4], r14d
0x180011288  cmp     qword ptr [rdi+60h], 0
0x18001128d  jz      short loc_18001129E
0x18001128f  mov     r8d, r14d; unsigned int
0x180011292  mov     rcx, rdi; this
0x180011295  call    ?MarkRecentElement@CacheWriter@@AEAAXAEBVLockHolder@@I@Z; CacheWriter::MarkRecentElement(LockHolder const &,uint)
0x18001129a  mov     r9, [rbp+arg_10]
0x18001129e  mov     [rsi], r9d
0x1800112a1  mov     eax, [r12+r15*8+8]
0x1800112a6  mov     [rsi+8], eax
0x1800112a9  mov     [rsi+4], r14d
0x1800112ad  movdqu  xmmword ptr [rsi+10h], xmm6
0x1800112b2  movups  xmm0, [rbp+var_40]
0x1800112b6  movdqu  xmmword ptr [rsi+20h], xmm0
0x1800112bb  lea     rcx, [rsi+30h]
0x1800112bf  mov     rdx, rdi
0x1800112c2  call    ?Assign@?$IntrusivePtr@VICacheReference@@@@QEAAXPEAVICacheReference@@@Z; IntrusivePtr<ICacheReference>::Assign(ICacheReference *)
0x1800112c7  mov     byte ptr [rsi+38h], 1
0x1800112cb  mov     al, [r13+61h]
0x1800112cf  mov     [rsi+39h], al
0x1800112d2  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x1800112d6  call    cs:__imp_LeaveCriticalSection
0x1800112dc  mov     rbx, [rsp+80h+arg_8]
0x1800112e4  movaps  xmm6, [rsp+80h+var_10]
0x1800112e9  add     rsp, 80h
0x1800112f0  pop     r15
0x1800112f2  pop     r14
0x1800112f4  pop     r13
0x1800112f6  pop     r12
0x1800112f8  pop     rdi
0x1800112f9  pop     rsi
0x1800112fa  pop     rbp
0x1800112fb  retn
0x1800112fc  xor     r8d, r8d; unsigned __int64
0x1800112ff  mov     rdx, rdi; struct CacheWriter *
0x180011302  lea     rcx, [rbp+pExceptionObject]; this
0x180011306  call    ??0CacheOverflowException@@QEAA@PEAVCacheWriter@@_K@Z; CacheOverflowException::CacheOverflowException(CacheWriter *,unsigned __int64)
0x18001130b  lea     rdx, _TI2?AVCacheOverflowException@@; pThrowInfo
0x180011312  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180011316  call    _CxxThrowException_0
```
