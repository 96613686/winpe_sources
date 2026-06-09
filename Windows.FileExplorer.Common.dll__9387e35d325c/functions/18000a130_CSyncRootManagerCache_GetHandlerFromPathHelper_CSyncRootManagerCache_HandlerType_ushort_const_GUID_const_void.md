# CSyncRootManagerCache::GetHandlerFromPathHelper(CSyncRootManagerCache::HandlerType,ushort const *,_GUID const &,void * *)

- ea: `0x18000a130`
- end: `0x18000a3fd`
- name: `?GetHandlerFromPathHelper@CSyncRootManagerCache@@AEAAJW4HandlerType@1@PEBGAEBU_GUID@@PEAPEAX@Z`
- size: `717`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *, int, const unsigned __int16 *, __int64, __int64)`
- caller_count: `6`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180020bc0`
- `0x180023270`
- `0x180023650`
- `0x1800652f0`
- `0x180065380`
- `0x1800656b0`

## callees

- `0x180004a54`
- `0x1800077c8`
- `0x1800092d0`
- `0x18000964c`
- `0x18000a130`
- `0x18000a410`
- `0x18000a6e0`
- `0x180089010`

## import_xrefs

- `Windows.Storage!__imp_PathComparePaths` at `0x18000a1e4`
- `Windows.Storage!__imp_PathComparePaths` at `0x18000a1e4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000a243`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000a243`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000a188`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000a188`

## string_xrefs

- `0x18000a3d1`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSyncRootManagerCache::GetHandlerFromPathHelper(
        RTL_SRWLOCK *a1,
        int a2,
        const unsigned __int16 *a3,
        __int64 a4,
        __int64 a5)
{
  wil *v6; // rdi
  RTL_SRWLOCK *v8; // rbx
  char *v9; // r13
  __int64 v10; // r15
  int StorageProviderInfo; // esi
  __int64 v12; // rax
  unsigned __int64 v13; // rbx
  wil *v14; // rbx
  const unsigned __int16 *v15; // rdi
  const unsigned __int16 *v16; // rax
  CStorageProviderRootsCache *v17; // rcx
  const unsigned __int16 *v18; // rdx
  CStorageProviderRootsCache *v19; // rbx
  struct IStorageProviderInfo *v20; // rcx
  int v22; // eax
  struct IStorageProviderInfo *v23; // rdi
  __int64 (__fastcall *v24)(struct IStorageProviderInfo *, GUID *, __int64 *); // rbx
  int v25; // eax
  unsigned int v26; // ebx
  __int64 v27; // rcx
  int v28; // [rsp+20h] [rbp-30h]
  struct IStorageProviderInfo *v29; // [rsp+30h] [rbp-20h] BYREF
  unsigned __int64 v30; // [rsp+38h] [rbp-18h]
  __int64 v31; // [rsp+40h] [rbp-10h]
  PSRWLOCK SRWLock; // [rsp+48h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+38h]

  v6 = (wil *)a3;
  v8 = a1;
  v9 = 0;
  v10 = a5;
  *(_QWORD *)a5 = 0;
  StorageProviderInfo = CSyncRootManagerCache::_EnsureCachedValuesReaderModeWrapper(a1, 0xFFFFFFFFLL);
  if ( StorageProviderInfo < 0 )
    return (unsigned int)StorageProviderInfo;
  v29 = 0;
  SRWLock = v8 + 3;
  AcquireSRWLockShared(v8 + 3);
  StorageProviderInfo = -2147023728;
  while ( v9 < v8[5].Ptr )
  {
    v12 = *((_QWORD *)v8[4].Ptr + (_QWORD)v9);
    v31 = v12;
    v13 = 0;
    while ( 1 )
    {
      v30 = v13;
      if ( v13 >= *(_QWORD *)(v12 + 568) )
        break;
      v14 = *(wil **)(*(_QWORD *)(*(_QWORD *)(v12 + 560) + 8 * v13) + 24LL);
      v15 = SkipExtendedLengthDosDevicePathPrefix(v6);
      v16 = SkipExtendedLengthDosDevicePathPrefix(v14);
      LODWORD(a5) = PathComparePaths(v16, v15);
      v6 = (wil *)a3;
      if ( (a5 & 0xE) != 0
        || (v17 = *(CStorageProviderRootsCache **)(*(_QWORD *)(v31 + 560) + 8 * v30),
            (v18 = (const unsigned __int16 *)*((_QWORD *)v17 + 6)) != 0)
        && *v18
        && CStorageProviderRootsCache::_PathIsEqualOrSubFolder(v17, v18, a3, (unsigned int *)&a5) )
      {
        v19 = (CStorageProviderRootsCache *)*((_QWORD *)a1[4].Ptr + (_QWORD)v9);
        Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v29);
        StorageProviderInfo = CStorageProviderRootsCache::GetStorageProviderInfo(v19, &v29);
        goto LABEL_10;
      }
      v13 = v30 + 1;
      v12 = v31;
    }
    ++v9;
    v8 = a1;
  }
LABEL_10:
  ReleaseSRWLockShared(SRWLock);
  if ( StorageProviderInfo < 0 )
  {
LABEL_11:
    v20 = v29;
    if ( v29 )
    {
      v29 = 0;
      (*(void (__fastcall **)(struct IStorageProviderInfo *))(*(_QWORD *)v20 + 16LL))(v20);
    }
    return (unsigned int)StorageProviderInfo;
  }
  switch ( a2 )
  {
    case 0:
      v22 = (*(__int64 (__fastcall **)(struct IStorageProviderInfo *, __int64, __int64))(*(_QWORD *)v29 + 112LL))(
              v29,
              a4,
              v10);
      goto LABEL_22;
    case 1:
      v22 = (*(__int64 (__fastcall **)(struct IStorageProviderInfo *, __int64, __int64))(*(_QWORD *)v29 + 128LL))(
              v29,
              a4,
              v10);
      goto LABEL_22;
    case 2:
      v22 = (*(__int64 (__fastcall **)(struct IStorageProviderInfo *, __int64, __int64))(*(_QWORD *)v29 + 144LL))(
              v29,
              a4,
              v10);
      goto LABEL_22;
    case 3:
      v22 = (*(__int64 (__fastcall **)(struct IStorageProviderInfo *, wil *, __int64, __int64))(*(_QWORD *)v29 + 160LL))(
              v29,
              v6,
              a4,
              v10);
LABEL_22:
      StorageProviderInfo = v22;
      goto LABEL_11;
    case 5:
      v22 = (*(__int64 (__fastcall **)(struct IStorageProviderInfo *, __int64, __int64))(*(_QWORD *)v29 + 272LL))(
              v29,
              a4,
              v10);
      goto LABEL_22;
  }
  StorageProviderInfo = -2147418113;
  if ( a2 != 6 )
    goto LABEL_11;
  a5 = 0;
  v23 = v29;
  v24 = **(__int64 (__fastcall ***)(struct IStorageProviderInfo *, GUID *, __int64 *))v29;
  Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&a5);
  v25 = v24(v23, &GUID_884abcd3_5446_45ff_9226_e95d8e2a7006, &a5);
  v26 = v25;
  if ( v25 >= 0 )
  {
    StorageProviderInfo = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, __int64, __int64))(*(_QWORD *)a5 + 32LL))(
                            a5,
                            a3,
                            a4,
                            v10);
    v27 = a5;
    if ( a5 )
    {
      a5 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    }
    goto LABEL_11;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x11AE,
    (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
    (const char *)(unsigned int)v25,
    v28);
  Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&a5);
  Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v29);
  return v26;
}

```

## disassembly

```asm
0x18000a130  mov     [rsp-38h+arg_8], rbx
0x18000a135  mov     [rsp-38h+arg_10], r8
0x18000a13a  mov     [rsp-38h+arg_0], rcx
0x18000a13f  push    rbp
0x18000a140  push    rsi
0x18000a141  push    rdi
0x18000a142  push    r12
0x18000a144  push    r13
0x18000a146  push    r14
0x18000a148  push    r15
0x18000a14a  mov     rbp, rsp
0x18000a14d  sub     rsp, 50h
0x18000a151  mov     r12, r9
0x18000a154  mov     rdi, r8
0x18000a157  mov     r14d, edx
0x18000a15a  mov     rbx, rcx
0x18000a15d  xor     r13d, r13d
0x18000a160  mov     r15, [rbp+arg_20]
0x18000a164  mov     [r15], r13
0x18000a167  or      edx, 0FFFFFFFFh
0x18000a16a  call    ?_EnsureCachedValuesReaderModeWrapper@CSyncRootManagerCache@@AEAAJW4SPGSP_FLAGS@@@Z; CSyncRootManagerCache::_EnsureCachedValuesReaderModeWrapper(SPGSP_FLAGS)
0x18000a16f  mov     esi, eax
0x18000a171  test    eax, eax
0x18000a173  js      loc_18000A26A
0x18000a179  mov     [rbp+var_20], r13
0x18000a17d  lea     rax, [rbx+18h]
0x18000a181  mov     [rbp+SRWLock], rax
0x18000a185  mov     rcx, rax; SRWLock
0x18000a188  call    cs:__imp_AcquireSRWLockShared
0x18000a18e  mov     esi, 80070490h
0x18000a193  cmp     r13, [rbx+28h]
0x18000a197  jnb     loc_18000A23F
0x18000a19d  mov     rax, [rbx+20h]
0x18000a1a1  mov     rax, [rax+r13*8]
0x18000a1a5  mov     [rbp+var_10], rax
0x18000a1a9  xor     ebx, ebx
0x18000a1ab  mov     [rbp+var_18], rbx
0x18000a1af  cmp     rbx, [rax+238h]
0x18000a1b6  jnb     loc_18000A391
0x18000a1bc  mov     rax, [rax+230h]
0x18000a1c3  mov     rcx, [rax+rbx*8]
0x18000a1c7  mov     rbx, [rcx+18h]
0x18000a1cb  mov     rcx, rdi; this
0x18000a1ce  call    ?SkipExtendedLengthDosDevicePathPrefix@@YAPEBGPEBG@Z; SkipExtendedLengthDosDevicePathPrefix(ushort const *)
0x18000a1d3  mov     rdi, rax
0x18000a1d6  mov     rcx, rbx; this
0x18000a1d9  call    ?SkipExtendedLengthDosDevicePathPrefix@@YAPEBGPEBG@Z; SkipExtendedLengthDosDevicePathPrefix(ushort const *)
0x18000a1de  mov     rdx, rdi
0x18000a1e1  mov     rcx, rax
0x18000a1e4  call    cs:__imp_PathComparePaths
0x18000a1ea  mov     dword ptr [rbp+arg_20], eax
0x18000a1ed  mov     rdi, [rbp+arg_10]
0x18000a1f1  test    al, 0Eh
0x18000a1f3  jnz     short loc_18000A21C
0x18000a1f5  mov     rax, [rbp+var_10]
0x18000a1f9  mov     rax, [rax+230h]
0x18000a200  mov     rbx, [rbp+var_18]
0x18000a204  mov     rcx, [rax+rbx*8]; this
0x18000a208  mov     rdx, [rcx+30h]; unsigned __int16 *
0x18000a20c  xor     eax, eax
0x18000a20e  test    rdx, rdx
0x18000a211  jnz     short loc_18000A284
0x18000a213  inc     rbx
0x18000a216  mov     rax, [rbp+var_10]
0x18000a21a  jmp     short loc_18000A1AB
0x18000a21c  mov     rax, [rbp+arg_0]
0x18000a220  mov     rax, [rax+20h]
0x18000a224  mov     rbx, [rax+r13*8]
0x18000a228  lea     rcx, [rbp+var_20]
0x18000a22c  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x18000a231  lea     rdx, [rbp+var_20]; struct IStorageProviderInfo **
0x18000a235  mov     rcx, rbx; this
0x18000a238  call    ?GetStorageProviderInfo@CStorageProviderRootsCache@@QEAAJPEAPEAUIStorageProviderInfo@@@Z; CStorageProviderRootsCache::GetStorageProviderInfo(IStorageProviderInfo * *)
0x18000a23d  mov     esi, eax
0x18000a23f  mov     rcx, [rbp+SRWLock]; SRWLock
0x18000a243  call    cs:__imp_ReleaseSRWLockShared
0x18000a249  xor     r13d, r13d
0x18000a24c  test    esi, esi
0x18000a24e  jns     short loc_18000A2A2
0x18000a250  mov     rcx, [rbp+var_20]
0x18000a254  test    rcx, rcx
0x18000a257  jz      short loc_18000A26A
0x18000a259  mov     [rbp+var_20], r13
0x18000a25d  mov     rax, [rcx]
0x18000a260  mov     rax, [rax+10h]
0x18000a264  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a269  nop
0x18000a26a  mov     eax, esi
0x18000a26c  mov     rbx, [rsp+50h+arg_8]
0x18000a274  add     rsp, 50h
0x18000a278  pop     r15
0x18000a27a  pop     r14
0x18000a27c  pop     r13
0x18000a27e  pop     r12
0x18000a280  pop     rdi
0x18000a281  pop     rsi
0x18000a282  pop     rbp
0x18000a283  retn
0x18000a284  cmp     [rdx], ax
0x18000a287  jz      short loc_18000A213
0x18000a289  lea     r9, [rbp+arg_20]; unsigned int *
0x18000a28d  mov     r8, rdi; unsigned __int16 *
0x18000a290  call    ?_PathIsEqualOrSubFolder@CStorageProviderRootsCache@@AEAA_NPEBG0PEAK@Z; CStorageProviderRootsCache::_PathIsEqualOrSubFolder(ushort const *,ushort const *,ulong *)
0x18000a295  test    al, al
0x18000a297  jz      loc_18000A213
0x18000a29d  jmp     loc_18000A21C
0x18000a2a2  test    r14d, r14d
0x18000a2a5  jz      loc_18000A39D
0x18000a2ab  cmp     r14d, 1
0x18000a2af  jz      loc_18000A3AA
0x18000a2b5  cmp     r14d, 2
0x18000a2b9  jz      loc_18000A3BA
0x18000a2bf  cmp     r14d, 3
0x18000a2c3  jnz     short loc_18000A2E8
0x18000a2c5  mov     rcx, [rbp+var_20]
0x18000a2c9  mov     rax, [rcx]
0x18000a2cc  mov     r9, r15
0x18000a2cf  mov     r8, r12
0x18000a2d2  mov     rdx, rdi
0x18000a2d5  mov     rax, [rax+0A0h]
0x18000a2dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a2e1  mov     esi, eax
0x18000a2e3  jmp     loc_18000A250
0x18000a2e8  cmp     r14d, 5
0x18000a2ec  jz      loc_18000A373
0x18000a2f2  mov     esi, 8000FFFFh
0x18000a2f7  cmp     r14d, 6
0x18000a2fb  jnz     loc_18000A250
0x18000a301  mov     [rbp+arg_20], r13
0x18000a305  mov     rdi, [rbp+var_20]
0x18000a309  mov     rax, [rdi]
0x18000a30c  mov     rbx, [rax]
0x18000a30f  lea     rcx, [rbp+arg_20]
0x18000a313  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x18000a318  lea     r8, [rbp+arg_20]
0x18000a31c  lea     rdx, _GUID_884abcd3_5446_45ff_9226_e95d8e2a7006
0x18000a323  mov     rcx, rdi
0x18000a326  mov     rax, rbx
0x18000a329  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a32e  mov     ebx, eax
0x18000a330  test    eax, eax
0x18000a332  js      loc_18000A3CA
0x18000a338  mov     rcx, [rbp+arg_20]
0x18000a33c  mov     rax, [rcx]
0x18000a33f  mov     r9, r15
0x18000a342  mov     r8, r12
0x18000a345  mov     rdx, [rbp+arg_10]
0x18000a349  mov     rax, [rax+20h]
0x18000a34d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a352  mov     esi, eax
0x18000a354  mov     rcx, [rbp+arg_20]
0x18000a358  test    rcx, rcx
0x18000a35b  jz      short loc_18000A36E
0x18000a35d  mov     [rbp+arg_20], r13
0x18000a361  mov     rax, [rcx]
0x18000a364  mov     rax, [rax+10h]
0x18000a368  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a36d  nop
0x18000a36e  jmp     loc_18000A250
0x18000a373  mov     rcx, [rbp+var_20]
0x18000a377  mov     rax, [rcx]
0x18000a37a  mov     rax, [rax+110h]
0x18000a381  mov     rdx, r12
0x18000a384  mov     r8, r15
0x18000a387  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a38c  jmp     loc_18000A2E1
0x18000a391  inc     r13
0x18000a394  mov     rbx, [rbp+arg_0]
0x18000a398  jmp     loc_18000A193
0x18000a39d  mov     rcx, [rbp+var_20]
0x18000a3a1  mov     rax, [rcx]
0x18000a3a4  mov     rax, [rax+70h]
0x18000a3a8  jmp     short loc_18000A381
0x18000a3aa  mov     rcx, [rbp+var_20]
0x18000a3ae  mov     rax, [rcx]
0x18000a3b1  mov     rax, [rax+80h]
0x18000a3b8  jmp     short loc_18000A381
0x18000a3ba  mov     rcx, [rbp+var_20]
0x18000a3be  mov     rax, [rcx]
0x18000a3c1  mov     rax, [rax+90h]
0x18000a3c8  jmp     short loc_18000A381
0x18000a3ca  mov     rcx, [rbp+38h]; this
0x18000a3ce  mov     r9d, ebx; char *
0x18000a3d1  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\fileexplorer\\windo"...
0x18000a3d8  mov     edx, 11AEh; void *
0x18000a3dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a3e2  nop
0x18000a3e3  lea     rcx, [rbp+arg_20]
0x18000a3e7  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x18000a3ec  nop
0x18000a3ed  lea     rcx, [rbp+var_20]
0x18000a3f1  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x18000a3f6  mov     eax, ebx
0x18000a3f8  jmp     loc_18000A26C
```
