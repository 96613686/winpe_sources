# FltpFreeInstance

- ea: `0x180063b40`
- end: `0x180063f60`
- name: `FltpFreeInstance`
- size: `1056`
- prototype: `__int64 __fastcall(PVOID FltObject)`
- caller_count: `5`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x18004d410`
- `0x18004f240`
- `0x180060430`
- `0x180068e20`
- `0x180069c90`

## callees

- `0x180009f20`
- `0x180010400`
- `0x1800117c0`
- `0x180014340`
- `0x180018690`
- `0x180018b50`
- `0x18001ae50`
- `0x18001c910`
- `0x180021ee0`
- `0x180024880`
- `0x18005dcc0`
- `0x180062ba0`
- `0x180063b40`
- `0x180063f70`
- `0x180064540`
- `0x1800648b0`
- `0x180064920`
- `0x180064b40`

## import_xrefs

- `ntoskrnl!IoGetStackLimits` at `0x180063d6a`
- `ntoskrnl!IoGetStackLimits` at `0x180063d6a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180063d9e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180063d9e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180063e02`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180063e02`
- `ntoskrnl!ExReleaseFastResource` at `0x180063df6`
- `ntoskrnl!ExReleaseFastResource` at `0x180063df6`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x180063db3`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x180063db3`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x180063e52`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x180063e52`
- `ntoskrnl!ExRundownCompleted` at `0x180063e42`
- `ntoskrnl!ExRundownCompleted` at `0x180063e42`
- `HAL!KeQueryPerformanceCounter` at `0x180063bef`
- `HAL!KeQueryPerformanceCounter` at `0x180063c10`
- `HAL!KeQueryPerformanceCounter` at `0x180063c35`
- `HAL!KeQueryPerformanceCounter` at `0x180063c75`
- `HAL!KeQueryPerformanceCounter` at `0x180063c9a`
- `HAL!KeQueryPerformanceCounter` at `0x180063cc5`
- `HAL!KeQueryPerformanceCounter` at `0x180063cea`
- `HAL!KeQueryPerformanceCounter` at `0x180063bef`
- `HAL!KeQueryPerformanceCounter` at `0x180063c10`
- `HAL!KeQueryPerformanceCounter` at `0x180063c35`
- `HAL!KeQueryPerformanceCounter` at `0x180063c75`
- `HAL!KeQueryPerformanceCounter` at `0x180063c9a`
- `HAL!KeQueryPerformanceCounter` at `0x180063cc5`
- `HAL!KeQueryPerformanceCounter` at `0x180063cea`

## pseudocode

```c
void __fastcall FltpFreeInstance(char *FltObject, __int64 a2, int a3)
{
  __int64 v3; // r15
  __int64 v4; // rsi
  unsigned int v5; // r14d
  unsigned int v7; // eax
  __int64 v8; // r8
  LARGE_INTEGER PerformanceCounter; // rbx
  void (__fastcall *v10)(__int128 *, _QWORD); // rax
  LARGE_INTEGER v11; // rbx
  LARGE_INTEGER v12; // rbx
  void (__fastcall *v13)(__int128 *, _QWORD); // rax
  char *v14; // rbx
  __int64 v15; // r8
  __int64 v16; // rdx
  char **v17; // rcx
  __int64 v18; // rcx
  unsigned __int64 HighLimit; // [rsp+60h] [rbp-19h] BYREF
  LONGLONG v20; // [rsp+68h] [rbp-11h] BYREF
  __int128 v21; // [rsp+70h] [rbp-9h] BYREF
  __int128 v22; // [rsp+80h] [rbp+7h]
  __int128 v23; // [rsp+90h] [rbp+17h]
  LONGLONG v24; // [rsp+E0h] [rbp+67h] BYREF
  unsigned __int64 LowLimit; // [rsp+F0h] [rbp+77h] BYREF
  LONGLONG v26; // [rsp+F8h] [rbp+7Fh] BYREF

  v3 = *((_QWORD *)FltObject + 8);
  v4 = *((_QWORD *)FltObject + 9);
  v5 = a2;
  v20 = 0;
  v21 = 0;
  v26 = 0;
  v22 = 0;
  v24 = 0;
  v23 = 0;
  if ( (byte_1800404C2 & 0x20) != 0 )
    McTemplateU0spwppwd_EtwWriteTransfer(
      *(unsigned __int16 *)(v3 + 112) >> 1,
      *(unsigned __int16 *)(v4 + 64) >> 1,
      a3,
      v4,
      *(_WORD *)(v4 + 64) >> 1,
      *(_QWORD *)(v4 + 72),
      (char)FltObject,
      v3,
      *(_WORD *)(v3 + 112) >> 1,
      *(_QWORD *)(v3 + 120),
      a2);
  v7 = FltpStartingToDrainObject(FltObject, a2, 2087);
  if ( (int)FltpDbgStatus(v7, "minkernel\\fs\\filtermgr\\filter\\instancesup.c", v8, 3223060491LL) < 0 )
  {
    FltObjectDereference(FltObject);
  }
  else
  {
    *(_QWORD *)&v22 = *((_QWORD *)FltObject + 8);
    v23 = 0;
    LODWORD(v21) = 48;
    *((_QWORD *)&v21 + 1) = v4;
    *((_QWORD *)&v22 + 1) = FltObject;
    FltpMarkAllCallbacksForDeletion(FltObject);
    PerformanceCounter = KeQueryPerformanceCounter(0);
    v10 = *(void (__fastcall **)(__int128 *, _QWORD))(v4 + 288);
    if ( v10 && v5 != -1 )
      v10(&v21, v5);
    v20 = 1000
        * (*(_QWORD *)&KeQueryPerformanceCounter(0) - PerformanceCounter.QuadPart)
        / PerformanceFrequency.QuadPart;
    v11 = KeQueryPerformanceCounter(0);
    if ( *((_QWORD *)FltObject + 37) )
    {
      FltpDrainActiveCompletions(FltObject);
      FltpWaitForRundownProtectionReleaseInternal(*((PEX_RUNDOWN_REF *)FltObject + 7));
      FltpFreeCompletionNodeTracking(*((_QWORD *)FltObject + 37));
      *((_QWORD *)FltObject + 37) = 0;
    }
    v24 = 1000 * (*(_QWORD *)&KeQueryPerformanceCounter(0) - v11.QuadPart) / PerformanceFrequency.QuadPart;
    v12 = KeQueryPerformanceCounter(0);
    if ( (v5 & 8) == 0 )
    {
      v18 = *(_QWORD *)(v3 + 88);
      if ( (*(_DWORD *)(v18 + 56) & 0x400) != 0 )
        _InterlockedAnd((volatile signed __int32 *)(v18 + 56), 0xFFFFFBFF);
    }
    v13 = *(void (__fastcall **)(__int128 *, _QWORD))(v4 + 296);
    if ( v13 && v5 != -1 )
      v13(&v21, v5);
    v26 = 1000 * (*(_QWORD *)&KeQueryPerformanceCounter(0) - v12.QuadPart) / PerformanceFrequency.QuadPart;
    KeQueryPerformanceCounter(0);
    FltObjectDereference(FltObject);
    FltpObjectRundownWait(FltObject);
    FltpDeleteContextList(FltObject + 160, FltObject + 136, -1);
    FltpCleanupStreamListCtrlForInstanceRemoval(FltObject);
    FltpCleanupFileListCtrlForInstanceRemoval(FltObject);
    FltDeleteInstanceContext((PFLT_INSTANCE)FltObject, 0);
    FltpRemoveCallbacksForInstance(FltObject);
    IoPerfFreeEntityData((struct _IO_PERF_ENTITY_DATA *)FltObject + 4);
    if ( (unsigned int)dword_18003DAA8 > 5 )
    {
      HighLimit = 0;
      LowLimit = 0;
      IoGetStackLimits(&LowLimit, &HighLimit);
      if ( (unsigned __int64)&HighLimit - LowLimit >= 0x200 )
      {
        if ( *(_DWORD *)(*((_QWORD *)FltObject + 8) + 60LL) != 1 && (v24 > 60000 || (v5 & 1) != 0) )
          ((void (__fastcall *)(char *, _QWORD, LONGLONG *, LONGLONG *, LONGLONG *))FltpLogFreeInstanceFunction)(
            FltObject,
            v5,
            &v20,
            &v26,
            &v24);
      }
      else
      {
        _InterlockedIncrement(&dword_18003FFB0);
      }
    }
    if ( *((_QWORD *)FltObject + 15) )
    {
      v14 = FltObject + 120;
      KeEnterCriticalRegion();
      LOBYTE(v15) = 1;
      ExAcquireFastResourceExclusive(v4 + 112, 0, v15);
      _InterlockedDecrement((volatile signed __int32 *)(v4 + 232));
      v16 = *((_QWORD *)FltObject + 15);
      v17 = (char **)*((_QWORD *)FltObject + 16);
      if ( *(char **)(*(_QWORD *)v14 + 8LL) != v14 || *v17 != v14 )
        __fastfail(3u);
      *v17 = (char *)v16;
      *(_QWORD *)(v16 + 8) = v17;
      *(_QWORD *)v14 = 0;
      ExReleaseFastResource(v4 + 112, 0);
      KeLeaveCriticalRegion();
    }
    FltObjectDereference((PVOID)v4);
    *((_QWORD *)FltObject + 9) = 0;
    if ( *((_QWORD *)FltObject + 2) )
      _InterlockedIncrement((volatile signed __int32 *)(v3 + 4));
    else
      *((_QWORD *)FltObject + 8) = 0;
    FltObjectDereference((PVOID)v3);
    if ( (*(_DWORD *)FltObject & 2) == 0 )
      _InterlockedOr((volatile signed __int32 *)FltObject, 2u);
    ExRundownCompleted((PEX_RUNDOWN_REF)FltObject + 1);
    ExFreeCacheAwareRundownProtection(*((PEX_RUNDOWN_REF_CACHE_AWARE *)FltObject + 7));
    *((_QWORD *)FltObject + 7) = 0;
    FltpObjectPointerDereference(FltObject);
  }
}

```

## disassembly

```asm
0x180063b40  push    rbp
0x180063b42  push    rsi
0x180063b43  push    rdi
0x180063b44  push    r12
0x180063b46  push    r14
0x180063b48  push    r15
0x180063b4a  lea     rbp, [rsp-2Fh]
0x180063b4f  sub     rsp, 0A8h
0x180063b56  mov     r15, [rcx+40h]
0x180063b5a  xor     r12d, r12d
0x180063b5d  test    cs:byte_1800404C2, 20h
0x180063b64  xorps   xmm0, xmm0
0x180063b67  mov     rsi, [rcx+48h]
0x180063b6b  mov     r14d, edx
0x180063b6e  mov     rdi, rcx
0x180063b71  mov     [rbp+57h+var_68], r12
0x180063b75  movups  [rbp+57h+var_60], xmm0
0x180063b79  mov     [rbp+57h+arg_18], r12
0x180063b7d  movups  [rbp+57h+var_50], xmm0
0x180063b81  mov     [rbp+57h+arg_0], r12
0x180063b85  movups  [rbp+57h+var_40], xmm0
0x180063b89  jnz     loc_180063EE8
0x180063b8f  mov     rcx, rdi
0x180063b92  mov     r8d, 827h
0x180063b98  call    FltpStartingToDrainObject
0x180063b9d  mov     ecx, eax
0x180063b9f  mov     [rsp+0D0h+var_B0], r12
0x180063ba4  lea     rdx, aMinkernelFsFil_19; "minkernel\\fs\\filtermgr\\filter\\insta"...
0x180063bab  mov     r9d, 0C01C000Bh
0x180063bb1  call    FltpDbgStatus
0x180063bb6  mov     rcx, rdi; FltObject
0x180063bb9  test    eax, eax
0x180063bbb  js      loc_180063F2B
0x180063bc1  mov     rax, [rdi+40h]
0x180063bc5  xorps   xmm0, xmm0
0x180063bc8  mov     qword ptr [rbp+57h+var_50], rax
0x180063bcc  movdqu  [rbp+57h+var_40], xmm0
0x180063bd1  mov     [rsp+0D0h+var_30], rbx
0x180063bd9  mov     dword ptr [rbp+57h+var_60], 30h ; '0'
0x180063be0  mov     qword ptr [rbp+57h+var_60+8], rsi
0x180063be4  mov     qword ptr [rbp+57h+var_50+8], rdi
0x180063be8  call    FltpMarkAllCallbacksForDeletion
0x180063bed  xor     ecx, ecx; PerformanceFrequency
0x180063bef  call    cs:__imp_KeQueryPerformanceCounter
0x180063bf6  nop     dword ptr [rax+rax+00h]
0x180063bfb  mov     rbx, rax
0x180063bfe  mov     rax, [rsi+120h]
0x180063c05  test    rax, rax
0x180063c08  jnz     loc_180063F35
0x180063c0e  xor     ecx, ecx; PerformanceFrequency
0x180063c10  call    cs:__imp_KeQueryPerformanceCounter
0x180063c17  nop     dword ptr [rax+rax+00h]
0x180063c1c  sub     rax, rbx
0x180063c1f  xor     ecx, ecx; PerformanceFrequency
0x180063c21  imul    rax, 3E8h
0x180063c28  cqo
0x180063c2a  idiv    qword ptr cs:PerformanceFrequency
0x180063c31  mov     [rbp+57h+var_68], rax
0x180063c35  call    cs:__imp_KeQueryPerformanceCounter
0x180063c3c  nop     dword ptr [rax+rax+00h]
0x180063c41  mov     rbx, rax
0x180063c44  cmp     [rdi+128h], r12
0x180063c4b  jz      short loc_180063C73
0x180063c4d  mov     rcx, rdi
0x180063c50  call    FltpDrainActiveCompletions
0x180063c55  mov     rcx, [rdi+38h]; RunRef
0x180063c59  mov     dl, 1
0x180063c5b  call    FltpWaitForRundownProtectionReleaseInternal
0x180063c60  mov     rcx, [rdi+128h]
0x180063c67  call    FltpFreeCompletionNodeTracking
0x180063c6c  mov     [rdi+128h], r12
0x180063c73  xor     ecx, ecx; PerformanceFrequency
0x180063c75  call    cs:__imp_KeQueryPerformanceCounter
0x180063c7c  nop     dword ptr [rax+rax+00h]
0x180063c81  sub     rax, rbx
0x180063c84  xor     ecx, ecx; PerformanceFrequency
0x180063c86  imul    rax, 3E8h
0x180063c8d  cqo
0x180063c8f  idiv    qword ptr cs:PerformanceFrequency
0x180063c96  mov     [rbp+57h+arg_0], rax
0x180063c9a  call    cs:__imp_KeQueryPerformanceCounter
0x180063ca1  nop     dword ptr [rax+rax+00h]
0x180063ca6  mov     rbx, rax
0x180063ca9  test    r14b, 8
0x180063cad  jz      loc_180063ECA
0x180063cb3  mov     rax, [rsi+128h]
0x180063cba  test    rax, rax
0x180063cbd  jnz     loc_180063EAF
0x180063cc3  xor     ecx, ecx; PerformanceFrequency
0x180063cc5  call    cs:__imp_KeQueryPerformanceCounter
0x180063ccc  nop     dword ptr [rax+rax+00h]
0x180063cd1  sub     rax, rbx
0x180063cd4  xor     ecx, ecx; PerformanceFrequency
0x180063cd6  imul    rax, 3E8h
0x180063cdd  cqo
0x180063cdf  idiv    qword ptr cs:PerformanceFrequency
0x180063ce6  mov     [rbp+57h+arg_18], rax
0x180063cea  call    cs:__imp_KeQueryPerformanceCounter
0x180063cf1  nop     dword ptr [rax+rax+00h]
0x180063cf6  mov     rcx, rdi; FltObject
0x180063cf9  call    FltObjectDereference
0x180063cfe  mov     rcx, rdi
0x180063d01  call    FltpObjectRundownWait
0x180063d06  mov     r9, 0FFFFFFFFFFFFFFFFh
0x180063d0d  lea     rdx, [rdi+88h]
0x180063d14  mov     r8, r9
0x180063d17  lea     rcx, [rdi+0A0h]
0x180063d1e  call    FltpDeleteContextList
0x180063d23  mov     rcx, rdi
0x180063d26  call    FltpCleanupStreamListCtrlForInstanceRemoval
0x180063d2b  mov     rcx, rdi
0x180063d2e  call    FltpCleanupFileListCtrlForInstanceRemoval
0x180063d33  xor     edx, edx; OldContext
0x180063d35  mov     rcx, rdi; Instance
0x180063d38  call    FltDeleteInstanceContext
0x180063d3d  mov     rcx, rdi
0x180063d40  call    FltpRemoveCallbacksForInstance
0x180063d45  lea     rcx, [rdi+300h]; struct _IO_PERF_ENTITY_DATA *
0x180063d4c  call    IoPerfFreeEntityData
0x180063d51  cmp     cs:dword_18003DAA8, 5
0x180063d58  jbe     short loc_180063D91
0x180063d5a  lea     rdx, [rbp+57h+HighLimit]; HighLimit
0x180063d5e  mov     [rbp+57h+HighLimit], r12
0x180063d62  lea     rcx, [rbp+57h+LowLimit]; LowLimit
0x180063d66  mov     [rbp+57h+LowLimit], r12
0x180063d6a  call    cs:__imp_IoGetStackLimits
0x180063d71  nop     dword ptr [rax+rax+00h]
0x180063d76  lea     rax, [rbp+57h+HighLimit]
0x180063d7a  sub     rax, [rbp+57h+LowLimit]
0x180063d7e  cmp     rax, 200h
0x180063d84  jnb     loc_180063E84
0x180063d8a  lock inc cs:dword_18003FFB0
0x180063d91  mov     rax, [rdi+78h]
0x180063d95  test    rax, rax
0x180063d98  jz      short loc_180063E0E
0x180063d9a  lea     rbx, [rdi+78h]
0x180063d9e  call    cs:__imp_KeEnterCriticalRegion
0x180063da5  nop     dword ptr [rax+rax+00h]
0x180063daa  mov     r8b, 1
0x180063dad  lea     rcx, [rsi+70h]
0x180063db1  xor     edx, edx
0x180063db3  call    cs:__imp_ExAcquireFastResourceExclusive
0x180063dba  nop     dword ptr [rax+rax+00h]
0x180063dbf  lock dec dword ptr [rsi+0E8h]
0x180063dc6  mov     rdx, [rbx]
0x180063dc9  mov     rcx, [rbx+8]
0x180063dcd  mov     rax, [rdx+8]
0x180063dd1  cmp     rax, rbx
0x180063dd4  jnz     loc_180063F50
0x180063dda  mov     rax, [rcx]
0x180063ddd  cmp     rax, rbx
0x180063de0  jnz     loc_180063F50
0x180063de6  mov     [rcx], rdx
0x180063de9  mov     [rdx+8], rcx
0x180063ded  xor     edx, edx
0x180063def  lea     rcx, [rsi+70h]
0x180063df3  mov     [rbx], r12
0x180063df6  call    cs:__imp_ExReleaseFastResource
0x180063dfd  nop     dword ptr [rax+rax+00h]
0x180063e02  call    cs:__imp_KeLeaveCriticalRegion
0x180063e09  nop     dword ptr [rax+rax+00h]
0x180063e0e  mov     rcx, rsi; FltObject
0x180063e11  call    FltObjectDereference
0x180063e16  mov     [rdi+48h], r12
0x180063e1a  mov     rax, [rdi+10h]
0x180063e1e  test    rax, rax
0x180063e21  jz      loc_180063F57
0x180063e27  lock inc dword ptr [r15+4]
0x180063e2c  mov     rcx, r15; FltObject
0x180063e2f  call    FltObjectDereference
0x180063e34  mov     eax, [rdi]
0x180063e36  test    al, 2
0x180063e38  jnz     short loc_180063E3E
0x180063e3a  lock or dword ptr [rdi], 2
0x180063e3e  lea     rcx, [rdi+8]; RunRef
0x180063e42  call    cs:__imp_ExRundownCompleted
0x180063e49  nop     dword ptr [rax+rax+00h]
0x180063e4e  mov     rcx, [rdi+38h]; RunRefCacheAware
0x180063e52  call    cs:__imp_ExFreeCacheAwareRundownProtection
0x180063e59  nop     dword ptr [rax+rax+00h]
0x180063e5e  mov     rcx, rdi
0x180063e61  mov     [rdi+38h], r12
0x180063e65  call    FltpObjectPointerDereference
0x180063e6a  mov     rbx, [rsp+0D0h+var_30]
0x180063e72  add     rsp, 0A8h
0x180063e79  pop     r15
0x180063e7b  pop     r14
0x180063e7d  pop     r12
0x180063e7f  pop     rdi
0x180063e80  pop     rsi
0x180063e81  pop     rbp
0x180063e82  retn
0x180063e84  mov     rax, [rdi+40h]
0x180063e88  cmp     dword ptr [rax+3Ch], 1
0x180063e8c  jz      loc_180063D91
0x180063e92  cmp     [rbp+57h+arg_0], 0EA60h
0x180063e9a  jg      loc_18007A3AE
0x180063ea0  test    r14b, 1
0x180063ea4  jz      loc_180063D91
0x180063eaa  jmp     loc_18007A3AE
0x180063eaf  cmp     r14d, 0FFFFFFFFh
0x180063eb3  jz      loc_180063CC3
0x180063eb9  mov     edx, r14d
0x180063ebc  lea     rcx, [rbp+57h+var_60]
0x180063ec0  call    _guard_dispatch_icall
0x180063ec5  jmp     loc_180063CC3
0x180063eca  mov     rcx, [r15+58h]
0x180063ece  mov     eax, [rcx+38h]
0x180063ed1  bt      eax, 0Ah
0x180063ed5  jnb     loc_180063CB3
0x180063edb  lock and dword ptr [rcx+38h], 0FFFFFBFFh
0x180063ee3  jmp     loc_180063CB3
0x180063ee8  mov     rax, [r15+78h]
0x180063eec  mov     r9, rsi
0x180063eef  movzx   ecx, word ptr [r15+70h]
0x180063ef4  movzx   edx, word ptr [rsi+40h]
0x180063ef8  mov     [rsp+0D0h+var_80], r14d
0x180063efd  mov     [rsp+0D0h+var_88], rax
0x180063f02  mov     rax, [rsi+48h]
0x180063f06  shr     ecx, 1
0x180063f08  mov     [rsp+0D0h+var_90], ecx
0x180063f0c  mov     [rsp+0D0h+var_98], r15
0x180063f11  mov     [rsp+0D0h+var_A0], rdi
0x180063f16  shr     edx, 1
0x180063f18  mov     [rsp+0D0h+var_A8], rax
0x180063f1d  mov     dword ptr [rsp+0D0h+var_B0], edx
0x180063f21  call    McTemplateU0spwppwd_EtwWriteTransfer
0x180063f26  jmp     loc_180063B8F
0x180063f2b  call    FltObjectDereference
0x180063f30  jmp     loc_180063E72
0x180063f35  cmp     r14d, 0FFFFFFFFh
0x180063f39  jz      loc_180063C0E
0x180063f3f  mov     edx, r14d
0x180063f42  lea     rcx, [rbp+57h+var_60]
0x180063f46  call    _guard_dispatch_icall
0x180063f4b  jmp     loc_180063C0E
0x180063f50  mov     ecx, 3
0x180063f55  int     29h; Win8: RtlFailFast(ecx)
0x180063f57  mov     [rdi+40h], r12
0x180063f5b  jmp     loc_180063E2C
0x18007a3ae  mov     rax, cs:FltpLogFreeInstanceFunction
0x18007a3b5  lea     rcx, [rbp+57h+arg_0]
0x18007a3b9  mov     [rsp+0D0h+var_B0], rcx
0x18007a3be  lea     r9, [rbp+57h+arg_18]
0x18007a3c2  mov     rcx, rdi
0x18007a3c5  lea     r8, [rbp+57h+var_68]
0x18007a3c9  mov     edx, r14d
0x18007a3cc  call    _guard_dispatch_icall
0x18007a3d1  nop
0x18007a3d2  jmp     loc_180063D91
```
