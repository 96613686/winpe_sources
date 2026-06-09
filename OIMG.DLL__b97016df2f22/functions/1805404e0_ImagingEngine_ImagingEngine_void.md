# ImagingEngine::~ImagingEngine(void)

- ea: `0x1805404e0`
- end: `0x18054072f`
- name: `??1ImagingEngine@@IEAA@XZ`
- size: `591`
- prototype: `void __fastcall(ImagingEngine *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18053c930`

## callees

- `0x1803e23f0`
- `0x18051b3f0`
- `0x18051c554`
- `0x1805404e0`
- `0x180540cd0`
- `0x180540d88`
- `0x18056dce0`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180540505`
- `KERNEL32!EnterCriticalSection` at `0x180540505`
- `KERNEL32!LeaveCriticalSection` at `0x18054052a`
- `KERNEL32!LeaveCriticalSection` at `0x18054052a`
- `KERNEL32!DeleteCriticalSection` at `0x18054055a`
- `KERNEL32!DeleteCriticalSection` at `0x18054058c`
- `KERNEL32!DeleteCriticalSection` at `0x1805406a2`
- `KERNEL32!DeleteCriticalSection` at `0x18054071f`
- `KERNEL32!DeleteCriticalSection` at `0x18054055a`
- `KERNEL32!DeleteCriticalSection` at `0x18054058c`
- `KERNEL32!DeleteCriticalSection` at `0x1805406a2`
- `KERNEL32!DeleteCriticalSection` at `0x18054071f`
- `OLEAUT32!__imp_SysFreeString` at `0x18054070b`
- `OLEAUT32!__imp_SysFreeString` at `0x18054070b`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180540563`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180540595`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180540563`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180540595`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall ImagingEngine::~ImagingEngine(LPCRITICAL_SECTION *this)
{
  LPCRITICAL_SECTION *v1; // rdi
  LPCRITICAL_SECTION *v2; // rsi
  __int64 v3; // rdx
  struct _RTL_CRITICAL_SECTION *v4; // r14
  struct _RTL_CRITICAL_SECTION *v5; // r14
  LPCRITICAL_SECTION v6; // rcx
  int (__fastcall ***v7)(_QWORD, _QWORD, _QWORD); // rcx
  LPCRITICAL_SECTION v8; // rcx
  LPCRITICAL_SECTION v9; // rcx
  LPCRITICAL_SECTION v10; // rcx
  LPCRITICAL_SECTION v11; // rcx
  LPCRITICAL_SECTION v12; // rcx
  LPCRITICAL_SECTION v13; // rcx
  LPCRITICAL_SECTION v14; // rcx
  __int64 v15; // [rsp+30h] [rbp-38h] BYREF
  __int64 v16; // [rsp+40h] [rbp-28h] BYREF
  __int64 v19; // [rsp+78h] [rbp+10h] BYREF
  LPCRITICAL_SECTION *v20; // [rsp+80h] [rbp+18h]
  char *v21; // [rsp+88h] [rbp+20h]

  v1 = this;
  v2 = this + 14;
  v20 = this + 14;
  EnterCriticalSection(this[19]);
  try
  {
    v21 = (char *)(v2 + 6);
    ATL::CAtlMap<_GUID,ATL::CComPtr<IEffectInfo>,ATL::CElementTraits<_GUID>,ATL::CElementTraits<ATL::CComPtr<IEffectInfo>>>::RemoveAll(
      v2 + 6,
      v3);
    if ( v2 )
      LeaveCriticalSection(v2[5]);
    v4 = v1[29];
    if ( v4 )
    {
      Base::Ptr<ColorProfileSRGB>::Release(&v4[1].OwningThread);
      Base::Ptr<PatchPoints>::Release(&v4[1].LockCount);
      Base::Ptr<PatchPoints>::Release(&v4[1]);
      DeleteCriticalSection(v4);
      free(v4);
    }
    v1[29] = 0;
    v5 = v1[30];
    if ( v5 )
    {
      ATL::CAtlList<Base::Ptr<ColorTransformManager::ColorTransformEntry>,ATL::CElementTraits<Base::Ptr<ColorTransformManager::ColorTransformEntry>>>::RemoveAll(&v5[1].LockCount);
      DeleteCriticalSection(v5);
      free(v5);
    }
    v1[30] = 0;
    v6 = v1[12];
    if ( v6 )
    {
      v1[12] = 0;
      ((void (__fastcall *)(LPCRITICAL_SECTION))v6->DebugInfo->ProcessLocksList.Flink)(v6);
    }
    v7 = (int (__fastcall ***)(_QWORD, _QWORD, _QWORD))v1[10];
    if ( v7 )
    {
      v19 = 0;
      if ( (**v7)(v7, &GUID_8726e29a_64f5_45ea_9037_b3922d4fd33a, &v19) < 0 )
        v19 = 0;
      ((void (__fastcall *)(LPCRITICAL_SECTION))v1[11]->DebugInfo[1].ProcessLocksList.Flink)(v1[11]);
      if ( v19 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    }
    v8 = v1[10];
    if ( v8 )
    {
      v1[10] = 0;
      ((void (__fastcall *)(LPCRITICAL_SECTION))v8->DebugInfo->ProcessLocksList.Flink)(v8);
    }
    v9 = v1[11];
    if ( v9 )
    {
      v1[11] = 0;
      ((void (__fastcall *)(LPCRITICAL_SECTION))v9->DebugInfo->ProcessLocksList.Flink)(v9);
    }
    v10 = v1[13];
    if ( v10 )
    {
      v1[13] = 0;
      ((void (__fastcall *)(LPCRITICAL_SECTION))v10->DebugInfo->ProcessLocksList.Flink)(v10);
    }
  }
  catch ( Base::Exception v15 )
  {
    v2 = v20;
    v1 = this;
  }
  catch ( long v16 )
  {
    v2 = v20;
    v1 = this;
  }
  ATL::CAtlMap<_GUID,ATL::CComPtr<IEffectInfo>,ATL::CElementTraits<_GUID>,ATL::CElementTraits<ATL::CComPtr<IEffectInfo>>>::~CAtlMap<_GUID,ATL::CComPtr<IEffectInfo>,ATL::CElementTraits<_GUID>,ATL::CElementTraits<ATL::CComPtr<IEffectInfo>>>(v21);
  DeleteCriticalSection((LPCRITICAL_SECTION)v2);
  v11 = v1[13];
  if ( v11 )
    ((void (__fastcall *)(LPCRITICAL_SECTION))v11->DebugInfo->ProcessLocksList.Flink)(v11);
  v12 = v1[12];
  if ( v12 )
    ((void (__fastcall *)(LPCRITICAL_SECTION))v12->DebugInfo->ProcessLocksList.Flink)(v12);
  v13 = v1[11];
  if ( v13 )
    ((void (__fastcall *)(LPCRITICAL_SECTION))v13->DebugInfo->ProcessLocksList.Flink)(v13);
  v14 = v1[10];
  if ( v14 )
    ((void (__fastcall *)(LPCRITICAL_SECTION))v14->DebugInfo->ProcessLocksList.Flink)(v14);
  SysFreeString((BSTR)v1[9]);
  if ( *((_BYTE *)v1 + 64) )
  {
    *((_BYTE *)v1 + 64) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)(v1 + 3));
  }
}

```

## disassembly

```asm
0x1805404e0  mov     [rsp+arg_0], rcx
0x1805404e5  push    rsi
0x1805404e6  push    rdi
0x1805404e7  push    r14
0x1805404e9  sub     rsp, 50h
0x1805404ed  mov     rdi, rcx
0x1805404f0  lea     rsi, [rcx+70h]
0x1805404f4  mov     [rsp+68h+arg_10], rsi
0x1805404fc  mov     [rsp+68h+var_48], rsi
0x180540501  mov     rcx, [rsi+28h]; lpCriticalSection
0x180540505  call    cs:__imp_EnterCriticalSection
0x18054050b  lea     rcx, [rsi+30h]
0x18054050f  mov     [rsp+68h+arg_18], rcx
0x180540517  mov     [rsp+68h+var_40], rcx
0x18054051c  call    ?RemoveAll@?$CAtlMap@U_GUID@@V?$CComPtr@UIEffectInfo@@@ATL@@V?$CElementTraits@U_GUID@@@3@V?$CElementTraits@V?$CComPtr@UIEffectInfo@@@ATL@@@3@@ATL@@QEAAXXZ; ATL::CAtlMap<_GUID,ATL::CComPtr<IEffectInfo>,ATL::CElementTraits<_GUID>,ATL::CElementTraits<ATL::CComPtr<IEffectInfo>>>::RemoveAll(void)
0x180540521  test    rsi, rsi
0x180540524  jz      short loc_180540530
0x180540526  mov     rcx, [rsi+28h]; lpCriticalSection
0x18054052a  call    cs:__imp_LeaveCriticalSection
0x180540530  mov     r14, [rdi+0E8h]
0x180540537  test    r14, r14
0x18054053a  jz      short loc_180540569
0x18054053c  lea     rcx, [r14+38h]
0x180540540  call    ?Release@?$Ptr@VColorProfileSRGB@@@Base@@QEAAXXZ; Base::Ptr<ColorProfileSRGB>::Release(void)
0x180540545  lea     rcx, [r14+30h]
0x180540549  call    ?Release@?$Ptr@VPatchPoints@@@Base@@QEAAXXZ; Base::Ptr<PatchPoints>::Release(void)
0x18054054e  lea     rcx, [r14+28h]
0x180540552  call    ?Release@?$Ptr@VPatchPoints@@@Base@@QEAAXXZ; Base::Ptr<PatchPoints>::Release(void)
0x180540557  mov     rcx, r14; lpCriticalSection
0x18054055a  call    cs:__imp_DeleteCriticalSection
0x180540560  mov     rcx, r14; Block
0x180540563  call    cs:__imp_free
0x180540569  mov     qword ptr [rdi+0E8h], 0
0x180540574  mov     r14, [rdi+0F0h]
0x18054057b  test    r14, r14
0x18054057e  jz      short loc_18054059B
0x180540580  lea     rcx, [r14+30h]
0x180540584  call    ?RemoveAll@?$CAtlList@V?$Ptr@UColorTransformEntry@ColorTransformManager@@@Base@@V?$CElementTraits@V?$Ptr@UColorTransformEntry@ColorTransformManager@@@Base@@@ATL@@@ATL@@QEAAXXZ; ATL::CAtlList<Base::Ptr<ColorTransformManager::ColorTransformEntry>,ATL::CElementTraits<Base::Ptr<ColorTransformManager::ColorTransformEntry>>>::RemoveAll(void)
0x180540589  mov     rcx, r14; lpCriticalSection
0x18054058c  call    cs:__imp_DeleteCriticalSection
0x180540592  mov     rcx, r14; Block
0x180540595  call    cs:__imp_free
0x18054059b  mov     qword ptr [rdi+0F0h], 0
0x1805405a6  mov     rcx, [rdi+60h]
0x1805405aa  test    rcx, rcx
0x1805405ad  jz      short loc_1805405C4
0x1805405af  mov     qword ptr [rdi+60h], 0
0x1805405b7  mov     rax, [rcx]
0x1805405ba  mov     rax, [rax+10h]
0x1805405be  call    cs:__guard_dispatch_icall_fptr
0x1805405c4  mov     rcx, [rdi+50h]
0x1805405c8  test    rcx, rcx
0x1805405cb  jz      short loc_180540628
0x1805405cd  mov     [rsp+68h+arg_8], 0
0x1805405d6  mov     rax, [rcx]
0x1805405d9  lea     r8, [rsp+68h+arg_8]
0x1805405de  lea     rdx, _GUID_8726e29a_64f5_45ea_9037_b3922d4fd33a
0x1805405e5  mov     rax, [rax]
0x1805405e8  call    cs:__guard_dispatch_icall_fptr
0x1805405ee  test    eax, eax
0x1805405f0  jns     short loc_1805405FB
0x1805405f2  xor     edx, edx
0x1805405f4  mov     [rsp+68h+arg_8], rdx
0x1805405f9  jmp     short loc_180540600
0x1805405fb  mov     rdx, [rsp+68h+arg_8]
0x180540600  mov     rcx, [rdi+58h]
0x180540604  mov     rax, [rcx]
0x180540607  mov     rax, [rax+40h]
0x18054060b  call    cs:__guard_dispatch_icall_fptr
0x180540611  mov     rcx, [rsp+68h+arg_8]
0x180540616  test    rcx, rcx
0x180540619  jz      short loc_180540628
0x18054061b  mov     rax, [rcx]
0x18054061e  mov     rax, [rax+10h]
0x180540622  call    cs:__guard_dispatch_icall_fptr
0x180540628  mov     rcx, [rdi+50h]
0x18054062c  test    rcx, rcx
0x18054062f  jz      short loc_180540646
0x180540631  mov     qword ptr [rdi+50h], 0
0x180540639  mov     rax, [rcx]
0x18054063c  mov     rax, [rax+10h]
0x180540640  call    cs:__guard_dispatch_icall_fptr
0x180540646  mov     rcx, [rdi+58h]
0x18054064a  test    rcx, rcx
0x18054064d  jz      short loc_180540664
0x18054064f  mov     qword ptr [rdi+58h], 0
0x180540657  mov     rax, [rcx]
0x18054065a  mov     rax, [rax+10h]
0x18054065e  call    cs:__guard_dispatch_icall_fptr
0x180540664  mov     rcx, [rdi+68h]
0x180540668  test    rcx, rcx
0x18054066b  jz      short loc_180540683
0x18054066d  mov     qword ptr [rdi+68h], 0
0x180540675  mov     rax, [rcx]
0x180540678  mov     rax, [rax+10h]
0x18054067c  call    cs:__guard_dispatch_icall_fptr
0x180540682  nop
0x180540683  jmp     short loc_180540692
0x180540685  mov     rsi, [rsp+68h+arg_10]
0x18054068d  mov     rdi, [rsp+68h+arg_0]
0x180540692  mov     rcx, [rsp+68h+arg_18]
0x18054069a  call    ??1?$CAtlMap@U_GUID@@V?$CComPtr@UIEffectInfo@@@ATL@@V?$CElementTraits@U_GUID@@@3@V?$CElementTraits@V?$CComPtr@UIEffectInfo@@@ATL@@@3@@ATL@@QEAA@XZ; ATL::CAtlMap<_GUID,ATL::CComPtr<IEffectInfo>,ATL::CElementTraits<_GUID>,ATL::CElementTraits<ATL::CComPtr<IEffectInfo>>>::~CAtlMap<_GUID,ATL::CComPtr<IEffectInfo>,ATL::CElementTraits<_GUID>,ATL::CElementTraits<ATL::CComPtr<IEffectInfo>>>(void)
0x18054069f  mov     rcx, rsi; lpCriticalSection
0x1805406a2  call    cs:__imp_DeleteCriticalSection
0x1805406a8  mov     rcx, [rdi+68h]
0x1805406ac  test    rcx, rcx
0x1805406af  jz      short loc_1805406BF
0x1805406b1  mov     rax, [rcx]
0x1805406b4  mov     rax, [rax+10h]
0x1805406b8  call    cs:__guard_dispatch_icall_fptr
0x1805406be  nop
0x1805406bf  mov     rcx, [rdi+60h]
0x1805406c3  test    rcx, rcx
0x1805406c6  jz      short loc_1805406D6
0x1805406c8  mov     rax, [rcx]
0x1805406cb  mov     rax, [rax+10h]
0x1805406cf  call    cs:__guard_dispatch_icall_fptr
0x1805406d5  nop
0x1805406d6  mov     rcx, [rdi+58h]
0x1805406da  test    rcx, rcx
0x1805406dd  jz      short loc_1805406F0
0x1805406df  mov     rax, [rcx]
0x1805406e2  mov     rax, [rax+10h]
0x1805406e6  call    cs:__guard_dispatch_icall_fptr
0x1805406ec  nop
0x1805406ed  nop     dword ptr [rax]
0x1805406f0  mov     rcx, [rdi+50h]
0x1805406f4  test    rcx, rcx
0x1805406f7  jz      short loc_180540707
0x1805406f9  mov     rax, [rcx]
0x1805406fc  mov     rax, [rax+10h]
0x180540700  call    cs:__guard_dispatch_icall_fptr
0x180540706  nop
0x180540707  mov     rcx, [rdi+48h]; bstrString
0x18054070b  call    cs:__imp_SysFreeString
0x180540711  lea     rcx, [rdi+18h]; lpCriticalSection
0x180540715  cmp     byte ptr [rcx+28h], 0
0x180540719  jz      short loc_180540726
0x18054071b  mov     byte ptr [rcx+28h], 0
0x18054071f  call    cs:__imp_DeleteCriticalSection
0x180540725  nop
0x180540726  add     rsp, 50h
0x18054072a  pop     r14
0x18054072c  pop     rdi
0x18054072d  pop     rsi
0x18054072e  retn
```
