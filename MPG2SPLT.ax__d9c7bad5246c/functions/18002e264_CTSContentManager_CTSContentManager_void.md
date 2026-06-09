# CTSContentManager::~CTSContentManager(void)

- ea: `0x18002e264`
- end: `0x18002e41c`
- name: `??1CTSContentManager@@UEAA@XZ`
- size: `440`
- prototype: `void __fastcall(CTSContentManager *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callers

- `0x18002e760`

## callees

- `0x180001048`
- `0x18002e144`
- `0x18002e264`
- `0x18002ecc0`
- `0x180034010`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18002e307`
- `KERNEL32!HeapFree` at `0x18002e307`
- `KERNEL32!DeleteCriticalSection` at `0x18002e2ec`
- `KERNEL32!DeleteCriticalSection` at `0x18002e314`
- `KERNEL32!DeleteCriticalSection` at `0x18002e32f`
- `KERNEL32!DeleteCriticalSection` at `0x18002e373`
- `KERNEL32!DeleteCriticalSection` at `0x18002e3b0`
- `KERNEL32!DeleteCriticalSection` at `0x18002e2ec`
- `KERNEL32!DeleteCriticalSection` at `0x18002e314`
- `KERNEL32!DeleteCriticalSection` at `0x18002e32f`
- `KERNEL32!DeleteCriticalSection` at `0x18002e373`
- `KERNEL32!DeleteCriticalSection` at `0x18002e3b0`

## pseudocode

```c
void __fastcall CTSContentManager::~CTSContentManager(CTSContentManager *this)
{
  void (__fastcall ***v2)(_QWORD, __int64); // rcx
  __int64 **v3; // rdi
  __int64 v4; // rdx
  __int64 *v5; // rax
  __int64 *v6; // rcx
  void *v7; // r8
  __int64 **v8; // rdi
  __int64 *v9; // rcx
  __int64 v10; // rdx
  __int64 *v11; // rax
  __int64 **v12; // rdi
  __int64 *v13; // rcx
  __int64 v14; // rdx
  __int64 *v15; // rax
  __int64 **v16; // rdi
  __int64 *v17; // rcx
  __int64 v18; // rdx
  __int64 *v19; // rax
  __int64 **v20; // rdi
  __int64 *v21; // rcx
  __int64 v22; // rdx
  __int64 *v23; // rax

  *(_QWORD *)this = &CTSContentManager::`vftable'{for `CIAVStreamNotify'};
  *((_QWORD *)this + 1) = &CTSContentManager::`vftable'{for `CIProgramInfo'};
  *((_QWORD *)this + 5) = &CTSContentManager::`vftable'{for `CIPCRValueNotify'};
  *((_QWORD *)this + 6) = &CTSContentManager::`vftable'{for `CISectionEventCallback'};
  CTSContentManager::ClearConfig_(this);
  v2 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 7);
  if ( v2 )
    (**v2)(v2, 1);
  v3 = (__int64 **)((char *)this + 72);
  while ( 1 )
  {
    v6 = *v3;
    if ( *v3 == (__int64 *)v3 )
      break;
    v4 = *v6;
    v5 = (__int64 *)v6[1];
    *v5 = *v6;
    *(_QWORD *)(v4 + 8) = v5;
    operator delete(v6, 0x20u);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 168));
  v7 = (void *)*((_QWORD *)this + 187);
  if ( v7 )
    HeapFree(*((HANDLE *)this + 190), 0, v7);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 1536));
  *((_QWORD *)this + 134) = &TGenericMap<unsigned __int64,unsigned long,1,10,19>::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 1456));
  v8 = (__int64 **)((char *)this + 1080);
  while ( 1 )
  {
    v9 = *v8;
    if ( *v8 == (__int64 *)v8 )
      break;
    v10 = *v9;
    v11 = (__int64 *)v9[1];
    *v11 = *v9;
    *(_QWORD *)(v10 + 8) = v11;
    operator delete(v9, 0x338u);
  }
  *((_QWORD *)this + 81) = &TGenericMap<unsigned __int64,unsigned long,0,5,19>::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 1032));
  v12 = (__int64 **)((char *)this + 656);
  while ( 1 )
  {
    v13 = *v12;
    if ( *v12 == (__int64 *)v12 )
      break;
    v14 = *v13;
    v15 = (__int64 *)v13[1];
    *v15 = *v13;
    *(_QWORD *)(v14 + 8) = v15;
    operator delete(v13, 0x1A8u);
  }
  *((_QWORD *)this + 28) = &TGenericMap<unsigned __int64,unsigned long,0,5,19>::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 608));
  v16 = (__int64 **)((char *)this + 232);
  while ( 1 )
  {
    v17 = *v16;
    if ( *v16 == (__int64 *)v16 )
      break;
    v18 = *v17;
    v19 = (__int64 *)v17[1];
    *v19 = *v17;
    *(_QWORD *)(v18 + 8) = v19;
    operator delete(v17, 0x1A8u);
  }
  v20 = (__int64 **)((char *)this + 112);
  while ( 1 )
  {
    v21 = *v20;
    if ( *v20 == (__int64 *)v20 )
      break;
    v22 = *v21;
    v23 = (__int64 *)v21[1];
    *v23 = *v21;
    *(_QWORD *)(v22 + 8) = v23;
    operator delete(v21, 0x108u);
  }
  CMpeg2StreamContentManager::~CMpeg2StreamContentManager(this);
}

```

## disassembly

```asm
0x18002e264  mov     [rsp+arg_0], rbx
0x18002e269  mov     [rsp+arg_8], rsi
0x18002e26e  push    rdi
0x18002e26f  sub     rsp, 20h
0x18002e273  lea     rax, ??_7CTSContentManager@@6BCIAVStreamNotify@@@; const CTSContentManager::`vftable'{for `CIAVStreamNotify'}
0x18002e27a  mov     rbx, rcx
0x18002e27d  mov     [rcx], rax
0x18002e280  lea     rax, ??_7CTSContentManager@@6BCIProgramInfo@@@; const CTSContentManager::`vftable'{for `CIProgramInfo'}
0x18002e287  mov     [rcx+8], rax
0x18002e28b  lea     rax, ??_7CTSContentManager@@6BCIPCRValueNotify@@@; const CTSContentManager::`vftable'{for `CIPCRValueNotify'}
0x18002e292  mov     [rcx+28h], rax
0x18002e296  lea     rax, ??_7CTSContentManager@@6BCISectionEventCallback@@@; const CTSContentManager::`vftable'{for `CISectionEventCallback'}
0x18002e29d  mov     [rcx+30h], rax
0x18002e2a1  call    ?ClearConfig_@CTSContentManager@@MEAAXXZ; CTSContentManager::ClearConfig_(void)
0x18002e2a6  mov     rcx, [rbx+38h]
0x18002e2aa  test    rcx, rcx
0x18002e2ad  jz      short loc_18002E2BF
0x18002e2af  mov     rax, [rcx]
0x18002e2b2  mov     edx, 1
0x18002e2b7  mov     rax, [rax]
0x18002e2ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e2bf  lea     rdi, [rbx+48h]
0x18002e2c3  jmp     short loc_18002E2DD
0x18002e2c5  mov     rdx, [rcx]
0x18002e2c8  mov     rax, [rcx+8]
0x18002e2cc  mov     [rax], rdx
0x18002e2cf  mov     [rdx+8], rax
0x18002e2d3  mov     edx, 20h ; ' '; unsigned __int64
0x18002e2d8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002e2dd  mov     rcx, [rdi]; void *
0x18002e2e0  cmp     rcx, rdi
0x18002e2e3  jnz     short loc_18002E2C5
0x18002e2e5  lea     rcx, [rbx+0A8h]; lpCriticalSection
0x18002e2ec  call    cs:__imp_DeleteCriticalSection
0x18002e2f2  mov     r8, [rbx+5D8h]; lpMem
0x18002e2f9  test    r8, r8
0x18002e2fc  jz      short loc_18002E30D
0x18002e2fe  mov     rcx, [rbx+5F0h]; hHeap
0x18002e305  xor     edx, edx; dwFlags
0x18002e307  call    cs:__imp_HeapFree
0x18002e30d  lea     rcx, [rbx+600h]; lpCriticalSection
0x18002e314  call    cs:__imp_DeleteCriticalSection
0x18002e31a  lea     rax, ??_7?$TGenericMap@_KK$00$09$0BD@@@6B@; const TGenericMap<unsigned __int64,ulong,1,10,19>::`vftable'
0x18002e321  lea     rcx, [rbx+5B0h]; lpCriticalSection
0x18002e328  mov     [rbx+430h], rax
0x18002e32f  call    cs:__imp_DeleteCriticalSection
0x18002e335  lea     rdi, [rbx+438h]
0x18002e33c  mov     rcx, [rdi]; void *
0x18002e33f  cmp     rcx, rdi
0x18002e342  jz      short loc_18002E35E
0x18002e344  mov     rdx, [rcx]
0x18002e347  mov     rax, [rcx+8]
0x18002e34b  mov     [rax], rdx
0x18002e34e  mov     [rdx+8], rax
0x18002e352  mov     edx, 338h; unsigned __int64
0x18002e357  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002e35c  jmp     short loc_18002E33C
0x18002e35e  lea     rsi, ??_7?$TGenericMap@_KK$0A@$04$0BD@@@6B@; const TGenericMap<unsigned __int64,ulong,0,5,19>::`vftable'
0x18002e365  lea     rcx, [rbx+408h]; lpCriticalSection
0x18002e36c  mov     [rbx+288h], rsi
0x18002e373  call    cs:__imp_DeleteCriticalSection
0x18002e379  lea     rdi, [rbx+290h]
0x18002e380  mov     rcx, [rdi]; void *
0x18002e383  cmp     rcx, rdi
0x18002e386  jz      short loc_18002E3A2
0x18002e388  mov     rdx, [rcx]
0x18002e38b  mov     rax, [rcx+8]
0x18002e38f  mov     [rax], rdx
0x18002e392  mov     [rdx+8], rax
0x18002e396  mov     edx, 1A8h; unsigned __int64
0x18002e39b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002e3a0  jmp     short loc_18002E380
0x18002e3a2  lea     rcx, [rbx+260h]; lpCriticalSection
0x18002e3a9  mov     [rbx+0E0h], rsi
0x18002e3b0  call    cs:__imp_DeleteCriticalSection
0x18002e3b6  lea     rdi, [rbx+0E8h]
0x18002e3bd  mov     rcx, [rdi]; void *
0x18002e3c0  cmp     rcx, rdi
0x18002e3c3  jz      short loc_18002E3DF
0x18002e3c5  mov     rdx, [rcx]
0x18002e3c8  mov     rax, [rcx+8]
0x18002e3cc  mov     [rax], rdx
0x18002e3cf  mov     [rdx+8], rax
0x18002e3d3  mov     edx, 1A8h; unsigned __int64
0x18002e3d8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002e3dd  jmp     short loc_18002E3BD
0x18002e3df  lea     rdi, [rbx+70h]
0x18002e3e3  mov     rcx, [rdi]; void *
0x18002e3e6  cmp     rcx, rdi
0x18002e3e9  jz      short loc_18002E405
0x18002e3eb  mov     rdx, [rcx]
0x18002e3ee  mov     rax, [rcx+8]
0x18002e3f2  mov     [rax], rdx
0x18002e3f5  mov     [rdx+8], rax
0x18002e3f9  mov     edx, 108h; unsigned __int64
0x18002e3fe  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002e403  jmp     short loc_18002E3E3
0x18002e405  mov     rcx, rbx; this
0x18002e408  mov     rbx, [rsp+28h+arg_0]
0x18002e40d  mov     rsi, [rsp+28h+arg_8]
0x18002e412  add     rsp, 20h
0x18002e416  pop     rdi
0x18002e417  jmp     ??1CMpeg2StreamContentManager@@UEAA@XZ; CMpeg2StreamContentManager::~CMpeg2StreamContentManager(void)
```
