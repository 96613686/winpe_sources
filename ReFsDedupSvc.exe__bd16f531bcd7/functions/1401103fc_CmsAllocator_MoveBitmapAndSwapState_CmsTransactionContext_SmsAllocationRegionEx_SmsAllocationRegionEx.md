# CmsAllocator::MoveBitmapAndSwapState(CmsTransactionContext *,SmsAllocationRegionEx &,SmsAllocationRegionEx &)

- ea: `0x1401103fc`
- end: `0x140110504`
- name: `?MoveBitmapAndSwapState@CmsAllocator@@QEAAXPEAVCmsTransactionContext@@AEAUSmsAllocationRegionEx@@1@Z`
- size: `264`
- prototype: `void __fastcall(CmsAllocator *__hidden this, struct CmsTransactionContext *, struct SmsAllocationRegionEx *, struct SmsAllocationRegionEx *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1400c977c`

## callees

- `0x140094f58`
- `0x1400970ac`
- `0x1400a2180`
- `0x1401103fc`
- `0x140114a3c`

## import_xrefs

- `ntdll!RtlCopyBitMap` at `0x14011048a`
- `ntdll!RtlCopyBitMap` at `0x14011048a`
- `ntdll!RtlInitializeBitMap` at `0x140110434`
- `ntdll!RtlInitializeBitMap` at `0x14011044d`
- `ntdll!RtlInitializeBitMap` at `0x140110434`
- `ntdll!RtlInitializeBitMap` at `0x14011044d`
- `ntdll!RtlReleaseSRWLockShared` at `0x1401104c8`
- `ntdll!RtlReleaseSRWLockShared` at `0x1401104c8`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1401104d6`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1401104d6`
- `ntdll!RtlAcquireSRWLockShared` at `0x140110471`
- `ntdll!RtlAcquireSRWLockShared` at `0x140110471`

## pseudocode

```c
void __fastcall CmsAllocator::MoveBitmapAndSwapState(
        CmsAllocator *this,
        struct CmsTransactionContext *a2,
        struct SmsAllocationRegionEx *a3,
        struct SmsAllocationRegionEx *a4)
{
  __int64 v4; // rbx
  ULONG v6; // r8d
  ULONG *v9; // rdx
  __int64 v10; // rdx
  __int64 v11; // rcx
  struct CmsTransactionContext *v12; // rdx
  struct _RTL_BITMAP v13; // [rsp+40h] [rbp-48h] BYREF
  struct _RTL_BITMAP BitMapHeader; // [rsp+50h] [rbp-38h] BYREF

  v4 = *((_QWORD *)this + 56);
  v6 = *((_DWORD *)a3 + 2);
  v9 = (ULONG *)*((_QWORD *)a3 + 7);
  BitMapHeader = 0;
  v13 = 0;
  RtlInitializeBitMap(&BitMapHeader, v9, v6);
  RtlInitializeBitMap(&v13, *((PULONG *)a4 + 7), *((_DWORD *)a4 + 2));
  SmsAllocationRegionEx::Lock(a3, 1, 1);
  RtlAcquireSRWLockShared(v4 + 3544);
  RtlCopyBitMap(&BitMapHeader, &v13, 0);
  CmsVolume::MaskUnmaskRecentlyDeallocatedTrim(v4, v10, this, a3, 0, &v13, 32);
  v11 = v4 + 3544;
  if ( *(_QWORD *)(v4 + 3544) < 0x10u )
    RtlReleaseSRWLockExclusive(v11);
  else
    RtlReleaseSRWLockShared(v11);
  SmsAllocationRegionEx::Unlock(a3);
  CmsAllocator::SwapBitmapRegionStates(this, v12, a3, a4);
}

```

## disassembly

```asm
0x1401103fc  push    rbx
0x1401103fe  push    rbp
0x1401103ff  push    rsi
0x140110400  push    rdi
0x140110401  push    r14
0x140110403  sub     rsp, 60h
0x140110407  mov     rbx, [rcx+1C0h]
0x14011040e  mov     rdi, r8
0x140110411  mov     r8d, [r8+8]; SizeOfBitMap
0x140110415  mov     r14, rcx
0x140110418  xorps   xmm0, xmm0
0x14011041b  lea     rcx, [rsp+88h+BitMapHeader]; BitMapHeader
0x140110420  xorps   xmm1, xmm1
0x140110423  mov     rbp, r9
0x140110426  mov     rdx, [rdi+38h]; BitMapBuffer
0x14011042a  movups  xmmword ptr [rsp+88h+BitMapHeader.SizeOfBitMap], xmm0
0x14011042f  movups  xmmword ptr [rsp+88h+var_48.SizeOfBitMap], xmm1
0x140110434  call    cs:__imp_RtlInitializeBitMap
0x14011043b  nop     dword ptr [rax+rax+00h]
0x140110440  mov     r8d, [rbp+8]; SizeOfBitMap
0x140110444  lea     rcx, [rsp+88h+var_48]; BitMapHeader
0x140110449  mov     rdx, [rbp+38h]; BitMapBuffer
0x14011044d  call    cs:__imp_RtlInitializeBitMap
0x140110454  nop     dword ptr [rax+rax+00h]
0x140110459  mov     r8b, 1; bool
0x14011045c  mov     rcx, rdi; this
0x14011045f  mov     dl, r8b; bool
0x140110462  call    ?Lock@SmsAllocationRegionEx@@AEAA_N_N0@Z; SmsAllocationRegionEx::Lock(bool,bool)
0x140110467  lea     rsi, [rbx+0DD8h]
0x14011046e  mov     rcx, rsi
0x140110471  call    cs:__imp_RtlAcquireSRWLockShared
0x140110478  nop     dword ptr [rax+rax+00h]
0x14011047d  xor     r8d, r8d
0x140110480  lea     rdx, [rsp+88h+var_48]
0x140110485  lea     rcx, [rsp+88h+BitMapHeader]
0x14011048a  call    cs:__imp_RtlCopyBitMap
0x140110491  nop     dword ptr [rax+rax+00h]
0x140110496  lea     rax, [rsp+88h+var_48]
0x14011049b  mov     [rsp+88h+var_58], 20h ; ' '
0x1401104a3  mov     [rsp+88h+var_60], rax
0x1401104a8  mov     r9, rdi
0x1401104ab  mov     r8, r14
0x1401104ae  mov     [rsp+88h+var_68], 0
0x1401104b7  mov     rcx, rbx
0x1401104ba  call    ?MaskUnmaskRecentlyDeallocatedTrim@CmsVolume@@QEAAXPEAVCmsTransactionContext@@PEAVCmsAllocator@@AEBU_RANGE@@PEA_NPEAU_RTL_BITMAP@@W4MaskUnmaskFlags@@@Z; CmsVolume::MaskUnmaskRecentlyDeallocatedTrim(CmsTransactionContext *,CmsAllocator *,_RANGE const &,bool *,_RTL_BITMAP *,MaskUnmaskFlags)
0x1401104bf  cmp     qword ptr [rsi], 10h
0x1401104c3  mov     rcx, rsi
0x1401104c6  jb      short loc_1401104D6
0x1401104c8  call    cs:__imp_RtlReleaseSRWLockShared
0x1401104cf  nop     dword ptr [rax+rax+00h]
0x1401104d4  jmp     short loc_1401104E2
0x1401104d6  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1401104dd  nop     dword ptr [rax+rax+00h]
0x1401104e2  mov     rcx, rdi; this
0x1401104e5  call    ?Unlock@SmsAllocationRegionEx@@AEAAXXZ; SmsAllocationRegionEx::Unlock(void)
0x1401104ea  mov     r9, rbp; struct SmsAllocationRegionEx *
0x1401104ed  mov     r8, rdi; struct SmsAllocationRegionEx *
0x1401104f0  mov     rcx, r14; this
0x1401104f3  call    ?SwapBitmapRegionStates@CmsAllocator@@QEAAXPEAVCmsTransactionContext@@AEAUSmsAllocationRegionEx@@1@Z; CmsAllocator::SwapBitmapRegionStates(CmsTransactionContext *,SmsAllocationRegionEx &,SmsAllocationRegionEx &)
0x1401104f8  add     rsp, 60h
0x1401104fc  pop     r14
0x1401104fe  pop     rdi
0x1401104ff  pop     rsi
0x140110500  pop     rbp
0x140110501  pop     rbx
0x140110502  retn
```
