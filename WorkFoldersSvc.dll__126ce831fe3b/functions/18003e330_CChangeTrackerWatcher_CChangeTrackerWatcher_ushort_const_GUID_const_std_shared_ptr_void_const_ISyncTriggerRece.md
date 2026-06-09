# CChangeTrackerWatcher::CChangeTrackerWatcher(ushort const *,_GUID const &,std::shared_ptr<void> const &,ISyncTriggerReceiver *,long,long,long)

- ea: `0x18003e330`
- end: `0x18003e6d5`
- name: `??0CChangeTrackerWatcher@@QEAA@PEBGAEBU_GUID@@AEBV?$shared_ptr@X@std@@PEAVISyncTriggerReceiver@@JJJ@Z`
- size: `933`
- prototype: `char *__fastcall(char *pv, __int64, void *, _QWORD *, __int64, int, int pExceptionObject, int)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18002f050`

## callees

- `0x180003604`
- `0x18000430d`
- `0x180007b9c`
- `0x180007e10`
- `0x1800110fc`
- `0x180011314`
- `0x180014a94`
- `0x18003e330`
- `0x18003f2d0`

## import_xrefs

- `KERNEL32!CreateThreadpoolWait` at `0x18003e53d`
- `KERNEL32!CreateThreadpoolWait` at `0x18003e53d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003e57a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003e57a`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18003e3d1`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18003e3d1`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
char *__fastcall CChangeTrackerWatcher::CChangeTrackerWatcher(
        char *pv,
        __int64 a2,
        void *a3,
        _QWORD *a4,
        __int64 a5,
        int a6,
        int pExceptionObject,
        int a8)
{
  _QWORD *v11; // r15
  int v12; // r13d
  __int64 v13; // r12
  __int64 v14; // rax
  char v15; // di
  void *v16; // r9
  _BYTE *v17; // rax
  __int64 v18; // r8
  int v20; // [rsp+20h] [rbp-20h] BYREF
  int v21; // [rsp+24h] [rbp-1Ch]
  char v22; // [rsp+28h] [rbp-18h]
  const char *v23; // [rsp+30h] [rbp-10h]
  __int64 v24; // [rsp+38h] [rbp-8h]
  void *Buf1; // [rsp+90h] [rbp+50h] BYREF

  Buf1 = a3;
  *(_QWORD *)pv = &ILocalChangeWatcher::`vftable';
  *(_QWORD *)pv = &CChangeTrackerWatcher::`vftable';
  v11 = pv + 8;
  *((_QWORD *)pv + 1) = 0;
  *((_QWORD *)pv + 2) = 0;
  v12 = a8;
  *((_DWORD *)pv + 6) = a8;
  *((_DWORD *)pv + 7) = pExceptionObject;
  *((_QWORD *)pv + 4) = 0;
  *((_QWORD *)pv + 5) = 0;
  v13 = a5;
  *((_QWORD *)pv + 6) = a5;
  *((_DWORD *)pv + 14) = a6;
  *((_QWORD *)pv + 8) = 0;
  *((_QWORD *)pv + 9) = 0;
  v14 = a4[1];
  v15 = 1;
  if ( v14 )
    _InterlockedAdd((volatile signed __int32 *)(v14 + 8), 1u);
  *((_QWORD *)pv + 8) = *a4;
  *((_QWORD *)pv + 9) = a4[1];
  InitializeCriticalSection((LPCRITICAL_SECTION)pv + 2);
  *(_OWORD *)(pv + 120) = 0;
  *((_QWORD *)pv + 17) = 0;
  *((_QWORD *)pv + 18) = 7;
  *((_WORD *)pv + 60) = 0;
  v16 = Buf1;
  *(_OWORD *)(pv + 152) = *(_OWORD *)Buf1;
  pv[168] = 1;
  v17 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) == 0 )
    {
LABEL_9:
      v15 = 0;
      goto LABEL_10;
    }
    if ( *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 10, WPP_80060c42e9283c9fa2e2881e1fba40a3_Traceguids);
      v17 = WPP_GLOBAL_Control;
      v16 = Buf1;
    }
  }
  if ( (v17[68] & 8) == 0 || v17[65] < 6u )
    goto LABEL_9;
LABEL_10:
  v21 = 23;
  v22 = v15;
  v23 = "CChangeTrackerWatcher::CChangeTrackerWatcher";
  v24 = 0;
  v20 = 0;
  if ( !a2 )
  {
    v20 = -2147024809;
    HIWORD(v21) = 25;
    pExceptionObject = -2147024809;
    throw (long *)&pExceptionObject;
  }
  LOWORD(v21) = 25;
  v20 = 0;
  if ( !v13 )
  {
    v20 = -2147024809;
    HIWORD(v21) = 26;
    pExceptionObject = -2147024809;
    throw (long *)&pExceptionObject;
  }
  LOWORD(v21) = 26;
  v20 = 0;
  if ( !*a4 )
  {
    v20 = -2147024809;
    HIWORD(v21) = 27;
    pExceptionObject = -2147024809;
    throw (long *)&pExceptionObject;
  }
  LOWORD(v21) = 27;
  v20 = 0;
  if ( !memcmp_0(v16, &GUID_NULL, 0x10u) )
  {
    v20 = -2147024809;
    HIWORD(v21) = 28;
    pExceptionObject = -2147024809;
    throw (long *)&pExceptionObject;
  }
  LOWORD(v21) = 28;
  v20 = 0;
  if ( v12 < 0 )
  {
    v20 = -2147024809;
    HIWORD(v21) = 29;
    pExceptionObject = -2147024809;
    throw (long *)&pExceptionObject;
  }
  LOWORD(v21) = 29;
  v20 = 0;
  if ( pExceptionObject < 0 )
  {
    v20 = -2147024809;
    HIWORD(v21) = 30;
    pExceptionObject = -2147024809;
    throw (long *)&pExceptionObject;
  }
  v20 = 0;
  LOWORD(v21) = 30;
  v18 = -1;
  do
    ++v18;
  while ( *(_WORD *)(a2 + 2 * v18) );
  std::wstring::_Assign<unsigned short>(pv + 120, a2);
  Buf1 = CreateThreadpoolWait(CChangeTrackerWatcher::ChangeTrackerEventCallback, pv, 0);
  EcsUniqueHandle<_TP_WAIT *,Win32ThreadPoolWaitDeleter,0>::reset(pv + 16, &Buf1);
  if ( !*((_QWORD *)pv + 2) )
  {
    HIWORD(v21) = 36;
    pExceptionObject = EcsGetLastFailureAsHRESULT();
    throw (long *)&pExceptionObject;
  }
  v20 = 0;
  LOWORD(v21) = 36;
  Buf1 = CreateEventW(0, 0, 0, 0);
  EcsUniqueHandle<void *,Win32HandleDeleter,0>::reset(v11, &Buf1);
  if ( !*v11 )
  {
    HIWORD(v21) = 39;
    pExceptionObject = EcsGetLastFailureAsHRESULT();
    throw (long *)&pExceptionObject;
  }
  v20 = 0;
  LOWORD(v21) = 39;
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&v20);
  return pv;
}

```

## disassembly

```asm
0x18003e330  mov     [rsp-38h+arg_18], rbx
0x18003e335  mov     [rsp-38h+Buf1], r8
0x18003e33a  mov     [rsp-38h+arg_0], rcx
0x18003e33f  push    rbp
0x18003e340  push    rsi
0x18003e341  push    rdi
0x18003e342  push    r12
0x18003e344  push    r13
0x18003e346  push    r14
0x18003e348  push    r15
0x18003e34a  mov     rbp, rsp
0x18003e34d  sub     rsp, 40h
0x18003e351  mov     r14, r9
0x18003e354  mov     rsi, rdx
0x18003e357  mov     rbx, rcx
0x18003e35a  lea     rax, ??_7ILocalChangeWatcher@@6B@; const ILocalChangeWatcher::`vftable'
0x18003e361  mov     [rcx], rax
0x18003e364  lea     rax, ??_7CChangeTrackerWatcher@@6B@; const CChangeTrackerWatcher::`vftable'
0x18003e36b  mov     [rcx], rax
0x18003e36e  lea     r15, [rcx+8]
0x18003e372  xor     ecx, ecx
0x18003e374  mov     [r15], rcx
0x18003e377  mov     [rbx+10h], rcx
0x18003e37b  mov     r13d, [rbp+arg_38]
0x18003e37f  mov     [rbx+18h], r13d
0x18003e383  mov     eax, [rbp+pExceptionObject]
0x18003e386  mov     [rbx+1Ch], eax
0x18003e389  mov     [rbx+20h], rcx
0x18003e38d  lea     rax, [rbx+28h]
0x18003e391  mov     [rbp+arg_8], rax
0x18003e395  mov     [rax], rcx
0x18003e398  mov     r12, [rbp+arg_20]
0x18003e39c  mov     [rbx+30h], r12
0x18003e3a0  mov     eax, [rbp+arg_28]
0x18003e3a3  mov     [rbx+38h], eax
0x18003e3a6  mov     [rbx+40h], rcx
0x18003e3aa  mov     [rbx+48h], rcx
0x18003e3ae  mov     rax, [r9+8]
0x18003e3b2  lea     edi, [rcx+1]
0x18003e3b5  test    rax, rax
0x18003e3b8  jz      short loc_18003E3BE
0x18003e3ba  lock add [rax+8], edi
0x18003e3be  mov     rax, [r9]
0x18003e3c1  mov     [rbx+40h], rax
0x18003e3c5  mov     rax, [r9+8]
0x18003e3c9  mov     [rbx+48h], rax
0x18003e3cd  lea     rcx, [rbx+50h]; lpCriticalSection
0x18003e3d1  call    cs:__imp_InitializeCriticalSection
0x18003e3d7  nop
0x18003e3d8  xorps   xmm0, xmm0
0x18003e3db  movups  xmmword ptr [rbx+78h], xmm0
0x18003e3df  xor     edx, edx
0x18003e3e1  mov     [rbx+88h], rdx
0x18003e3e8  mov     qword ptr [rbx+90h], 7
0x18003e3f3  mov     [rbx+78h], dx
0x18003e3f7  mov     r9, [rbp+Buf1]
0x18003e3fb  movups  xmm0, xmmword ptr [r9]
0x18003e3ff  movdqu  xmmword ptr [rbx+98h], xmm0
0x18003e407  mov     [rbx+0A8h], dil
0x18003e40e  lea     rcx, WPP_GLOBAL_Control
0x18003e415  mov     rax, cs:WPP_GLOBAL_Control
0x18003e41c  cmp     rax, rcx
0x18003e41f  jz      short loc_18003E44F
0x18003e421  test    byte ptr [rax+44h], 8
0x18003e425  jz      short loc_18003E45B
0x18003e427  cmp     byte ptr [rax+41h], 6
0x18003e42b  jb      short loc_18003E44F
0x18003e42d  mov     edx, 0Ah
0x18003e432  lea     r8, WPP_80060c42e9283c9fa2e2881e1fba40a3_Traceguids
0x18003e439  mov     rcx, [rax+38h]
0x18003e43d  call    WPP_SF_
0x18003e442  mov     rax, cs:WPP_GLOBAL_Control
0x18003e449  mov     r9, [rbp+Buf1]
0x18003e44d  xor     edx, edx
0x18003e44f  test    byte ptr [rax+44h], 8
0x18003e453  jz      short loc_18003E45B
0x18003e455  cmp     byte ptr [rax+41h], 6
0x18003e459  jnb     short loc_18003E45E
0x18003e45b  mov     dil, dl
0x18003e45e  mov     [rbp+var_20], edx
0x18003e461  mov     [rbp+var_1C], 17h
0x18003e468  mov     [rbp+var_18], dil
0x18003e46c  lea     rax, aCchangetracker_10; "CChangeTrackerWatcher::CChangeTrackerWa"...
0x18003e473  mov     [rbp+var_10], rax
0x18003e477  xor     edi, edi
0x18003e479  mov     [rbp+var_8], rdi
0x18003e47d  mov     eax, [rbp+var_20]
0x18003e480  mov     [rbp+var_20], eax
0x18003e483  lea     ecx, [rdi+19h]
0x18003e486  test    rsi, rsi
0x18003e489  jz      loc_18003E5F0
0x18003e48f  mov     [rbp+var_20], edi
0x18003e492  mov     word ptr [rbp+var_1C], cx
0x18003e496  mov     [rbp+var_20], edi
0x18003e499  lea     ecx, [rdi+1Ah]
0x18003e49c  test    r12, r12
0x18003e49f  jz      loc_18003E610
0x18003e4a5  mov     [rbp+var_20], edi
0x18003e4a8  mov     word ptr [rbp+var_1C], cx
0x18003e4ac  mov     [rbp+var_20], edi
0x18003e4af  lea     ecx, [rdi+1Bh]
0x18003e4b2  cmp     [r14], rdi
0x18003e4b5  jz      loc_18003E630
0x18003e4bb  mov     [rbp+var_20], edi
0x18003e4be  mov     word ptr [rbp+var_1C], cx
0x18003e4c2  mov     [rbp+var_20], edi
0x18003e4c5  lea     r8d, [rdi+10h]; Size
0x18003e4c9  lea     rdx, GUID_NULL; Buf2
0x18003e4d0  mov     rcx, r9; Buf1
0x18003e4d3  call    memcmp_0
0x18003e4d8  lea     ecx, [rdi+1Ch]
0x18003e4db  test    eax, eax
0x18003e4dd  jz      loc_18003E650
0x18003e4e3  mov     [rbp+var_20], edi
0x18003e4e6  mov     word ptr [rbp+var_1C], cx
0x18003e4ea  mov     [rbp+var_20], edi
0x18003e4ed  lea     ecx, [rdi+1Dh]
0x18003e4f0  test    r13d, r13d
0x18003e4f3  js      loc_18003E670
0x18003e4f9  mov     [rbp+var_20], edi
0x18003e4fc  mov     word ptr [rbp+var_1C], cx
0x18003e500  mov     [rbp+var_20], edi
0x18003e503  lea     ecx, [rdi+1Eh]
0x18003e506  cmp     [rbp+pExceptionObject], edi
0x18003e509  jl      loc_18003E690
0x18003e50f  mov     [rbp+var_20], edi
0x18003e512  mov     word ptr [rbp+var_1C], cx
0x18003e516  or      r8, 0FFFFFFFFFFFFFFFFh
0x18003e51a  inc     r8
0x18003e51d  cmp     [rsi+r8*2], di
0x18003e522  jnz     short loc_18003E51A
0x18003e524  mov     rdx, rsi
0x18003e527  lea     rcx, [rbx+78h]
0x18003e52b  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18003e530  xor     r8d, r8d; pcbe
0x18003e533  mov     rdx, rbx; pv
0x18003e536  lea     rcx, ?ChangeTrackerEventCallback@CChangeTrackerWatcher@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x18003e53d  call    cs:__imp_CreateThreadpoolWait
0x18003e543  mov     [rbp+Buf1], rax
0x18003e547  lea     rdx, [rbp+Buf1]
0x18003e54b  lea     rcx, [rbx+10h]
0x18003e54f  call    ?reset@?$EcsUniqueHandle@PEAU_TP_WAIT@@UWin32ThreadPoolWaitDeleter@@$0A@@@QEAAXAEBQEAU_TP_WAIT@@@Z; EcsUniqueHandle<_TP_WAIT *,Win32ThreadPoolWaitDeleter,0>::reset(_TP_WAIT * const &)
0x18003e554  mov     eax, [rbp+var_20]
0x18003e557  mov     [rbp+var_20], eax
0x18003e55a  xor     esi, esi
0x18003e55c  cmp     [rbx+10h], rsi
0x18003e560  jz      loc_18003E6B0
0x18003e566  mov     [rbp+var_20], esi
0x18003e569  lea     ecx, [rsi+24h]
0x18003e56c  mov     word ptr [rbp+var_1C], cx
0x18003e570  xor     r9d, r9d; lpName
0x18003e573  xor     r8d, r8d; bInitialState
0x18003e576  xor     edx, edx; bManualReset
0x18003e578  xor     ecx, ecx; lpEventAttributes
0x18003e57a  call    cs:__imp_CreateEventW
0x18003e580  mov     [rbp+Buf1], rax
0x18003e584  lea     rdx, [rbp+Buf1]
0x18003e588  mov     rcx, r15
0x18003e58b  call    ?reset@?$EcsUniqueHandle@PEAXUWin32HandleDeleter@@$0A@@@QEAAXAEBQEAX@Z; EcsUniqueHandle<void *,Win32HandleDeleter,0>::reset(void * const &)
0x18003e590  mov     eax, [rbp+var_20]
0x18003e593  mov     [rbp+var_20], eax
0x18003e596  cmp     [r15], rsi
0x18003e599  jz      short loc_18003E5CA
0x18003e59b  mov     [rbp+var_20], esi
0x18003e59e  lea     ecx, [rsi+27h]
0x18003e5a1  mov     word ptr [rbp+var_1C], cx
0x18003e5a5  lea     rcx, [rbp+var_20]; this
0x18003e5a9  call    ??1CEcsFunctionTracer@@QEAA@XZ; CEcsFunctionTracer::~CEcsFunctionTracer(void)
0x18003e5ae  nop
0x18003e5af  mov     rax, rbx
0x18003e5b2  mov     rbx, [rsp+40h+arg_18]
0x18003e5ba  add     rsp, 40h
0x18003e5be  pop     r15
0x18003e5c0  pop     r14
0x18003e5c2  pop     r13
0x18003e5c4  pop     r12
0x18003e5c6  pop     rdi
0x18003e5c7  pop     rsi
0x18003e5c8  pop     rbp
0x18003e5c9  retn
0x18003e5ca  call    ?EcsGetLastFailureAsHRESULT@@YAJXZ; EcsGetLastFailureAsHRESULT(void)
0x18003e5cf  nop
0x18003e5d0  mov     [rbp+var_20], eax
0x18003e5d3  mov     ecx, 27h ; '''
0x18003e5d8  mov     word ptr [rbp+var_1C+2], cx
0x18003e5dc  mov     [rbp+pExceptionObject], eax
0x18003e5df  lea     rdx, _TI1J; pThrowInfo
0x18003e5e6  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18003e5ea  call    _CxxThrowException_0
0x18003e5f0  mov     eax, 80070057h
0x18003e5f5  mov     [rbp+var_20], eax
0x18003e5f8  mov     word ptr [rbp+var_1C+2], cx
0x18003e5fc  mov     [rbp+pExceptionObject], eax
0x18003e5ff  lea     rdx, _TI1J; pThrowInfo
0x18003e606  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18003e60a  call    _CxxThrowException_0
0x18003e610  mov     eax, 80070057h
0x18003e615  mov     [rbp+var_20], eax
0x18003e618  mov     word ptr [rbp+var_1C+2], cx
0x18003e61c  mov     [rbp+pExceptionObject], eax
0x18003e61f  lea     rdx, _TI1J; pThrowInfo
0x18003e626  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18003e62a  call    _CxxThrowException_0
0x18003e630  mov     eax, 80070057h
0x18003e635  mov     [rbp+var_20], eax
0x18003e638  mov     word ptr [rbp+var_1C+2], cx
0x18003e63c  mov     [rbp+pExceptionObject], eax
0x18003e63f  lea     rdx, _TI1J; pThrowInfo
0x18003e646  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18003e64a  call    _CxxThrowException_0
0x18003e650  mov     eax, 80070057h
0x18003e655  mov     [rbp+var_20], eax
0x18003e658  mov     word ptr [rbp+var_1C+2], cx
0x18003e65c  mov     [rbp+pExceptionObject], eax
0x18003e65f  lea     rdx, _TI1J; pThrowInfo
0x18003e666  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18003e66a  call    _CxxThrowException_0
0x18003e670  mov     eax, 80070057h
0x18003e675  mov     [rbp+var_20], eax
0x18003e678  mov     word ptr [rbp+var_1C+2], cx
0x18003e67c  mov     [rbp+pExceptionObject], eax
0x18003e67f  lea     rdx, _TI1J; pThrowInfo
0x18003e686  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18003e68a  call    _CxxThrowException_0
0x18003e690  mov     eax, 80070057h
0x18003e695  mov     [rbp+var_20], eax
0x18003e698  mov     word ptr [rbp+var_1C+2], cx
0x18003e69c  mov     [rbp+pExceptionObject], eax
0x18003e69f  lea     rdx, _TI1J; pThrowInfo
0x18003e6a6  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18003e6aa  call    _CxxThrowException_0
0x18003e6b0  call    ?EcsGetLastFailureAsHRESULT@@YAJXZ; EcsGetLastFailureAsHRESULT(void)
0x18003e6b5  mov     [rbp+var_20], eax
0x18003e6b8  mov     ecx, 24h ; '$'
0x18003e6bd  mov     word ptr [rbp+var_1C+2], cx
0x18003e6c1  mov     [rbp+pExceptionObject], eax
0x18003e6c4  lea     rdx, _TI1J; pThrowInfo
0x18003e6cb  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18003e6cf  call    _CxxThrowException_0
```
