# TrackActivity_NetSetupTraceLogging::EvaluatePluginFilter__lambda_3575f476b5c9e84ddc39a50f92ca086b___GUID_const_&_wchar_t_const___unsigned_long_

- ea: `0x18000d860`
- end: `0x18000dcd5`
- name: `TrackActivity_NetSetupTraceLogging::EvaluatePluginFilter__lambda_3575f476b5c9e84ddc39a50f92ca086b___GUID_const_&_wchar_t_const___unsigned_long_`
- size: `1141`
- prototype: `__int64 __fastcall(unsigned int **, const struct _GUID *, const wchar_t **, unsigned int *)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x18000d720`

## callees

- `0x18000c740`
- `0x18000d660`
- `0x18000d694`
- `0x18000d860`
- `0x18000dcdc`
- `0x18000dd40`
- `0x18000e580`
- `0x180033720`
- `0x1800350c0`
- `0x18003a618`
- `0x18003aa44`
- `0x180046978`
- `0x18005097c`
- `0x18005c848`
- `0x180064704`
- `0x180065035`
- `0x180073bac`
- `0x1800810d0`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000dc18`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000dc18`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000dc9c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000dc9c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000dc8e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000dc8e`

## string_xrefs

- `0x18000d8b2`: `EvaluatePluginFilter`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall TrackActivity_NetSetupTraceLogging::EvaluatePluginFilter__lambda_3575f476b5c9e84ddc39a50f92ca086b___GUID_const___wchar_t_const___unsigned_long_(
        unsigned int **a1,
        const struct _GUID *a2,
        const wchar_t **a3,
        unsigned int *a4)
{
  unsigned int *v5; // rbx
  unsigned __int8 v6; // di
  __int64 v8; // rcx
  unsigned int v9; // ebx
  _DWORD *v10; // rsi
  __int64 v11; // r14
  __int64 v12; // r15
  __int64 v13; // r12
  unsigned int *v14; // r13
  unsigned int j; // edi
  unsigned int i; // edx
  char v17; // bl
  int v18; // eax
  __int64 v19; // rdx
  void *v20; // rbx
  void *v21; // rbx
  HANDLE ProcessHeap; // rax
  const struct _tlgProvider_t *v23; // rax
  PSRWLOCK SRWLock; // [rsp+40h] [rbp-298h] BYREF
  char v25[8]; // [rsp+48h] [rbp-290h] BYREF
  char *v26; // [rsp+50h] [rbp-288h]
  void ***v27; // [rsp+58h] [rbp-280h]
  __int64 v28; // [rsp+60h] [rbp-278h]
  _BYTE pExceptionObject[208]; // [rsp+68h] [rbp-270h] BYREF
  char v30; // [rsp+138h] [rbp-1A0h] BYREF
  void **v31; // [rsp+140h] [rbp-198h] BYREF
  int v32; // [rsp+148h] [rbp-190h] BYREF
  char v33; // [rsp+14Ch] [rbp-18Ch]
  char v34[32]; // [rsp+150h] [rbp-188h] BYREF
  int v35; // [rsp+170h] [rbp-168h] BYREF
  const char *v36; // [rsp+178h] [rbp-160h]
  LPVOID lpMem; // [rsp+180h] [rbp-158h]
  char v38; // [rsp+188h] [rbp-150h]
  int v39; // [rsp+190h] [rbp-148h]
  __int128 v40; // [rsp+198h] [rbp-140h]
  __int128 v41; // [rsp+1A8h] [rbp-130h]
  __int128 v42; // [rsp+1B8h] [rbp-120h]
  __int128 v43; // [rsp+1C8h] [rbp-110h]
  __int128 v44; // [rsp+1D8h] [rbp-100h]
  __int128 v45; // [rsp+1E8h] [rbp-F0h]
  __int128 v46; // [rsp+1F8h] [rbp-E0h]
  __int128 v47; // [rsp+208h] [rbp-D0h]
  __int128 v48; // [rsp+218h] [rbp-C0h]
  __int64 v49; // [rsp+228h] [rbp-B0h]
  __int128 v50; // [rsp+230h] [rbp-A8h] BYREF
  int v51; // [rsp+240h] [rbp-98h]
  __int64 v52; // [rsp+248h] [rbp-90h]
  int *v53; // [rsp+250h] [rbp-88h]
  void *Block; // [rsp+258h] [rbp-80h] BYREF
  _QWORD v55[3]; // [rsp+260h] [rbp-78h] BYREF
  int v56; // [rsp+278h] [rbp-60h]
  int *v57; // [rsp+280h] [rbp-58h]
  char v58; // [rsp+288h] [rbp-50h]

  v28 = -2;
  v32 = 0;
  v33 = 0;
  v38 = 0;
  v35 = 0;
  v36 = "EvaluatePluginFilter";
  lpMem = 0;
  v39 = 0;
  v50 = 0;
  v40 = 0;
  v41 = 0;
  v42 = 0;
  v43 = 0;
  v44 = 0;
  v45 = 0;
  v46 = 0;
  v47 = 0;
  v48 = 0;
  v49 = 0;
  v51 = 1;
  v52 = 0;
  v53 = &v32;
  Block = 0;
  v55[0] = 0;
  v55[1] = &v31;
  v55[2] = 0;
  v56 = 0;
  v57 = &v35;
  v58 = 0;
  v31 = &NetSetupTraceLogging::EvaluatePluginFilter::`vftable';
  NetSetupTraceLogging::EvaluatePluginFilter::StartActivity(
    (NetSetupTraceLogging::EvaluatePluginFilter *)&v31,
    a2,
    *a3,
    *a4);
  v30 = 1;
  v25[0] = 0;
  v26 = &v30;
  v27 = &v31;
  if ( **a1 == -1
    || (v5 = *a1,
        *(_QWORD *)((*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)a1[1] + 4) + 8LL))(*((_QWORD *)a1[1] + 4))
                  + 8LL * *v5)) )
  {
    v8 = *((_QWORD *)a1[1] + 3);
    v9 = *(_DWORD *)(v8 + 16);
    if ( v9 )
    {
      v10 = *(_DWORD **)(v8 + 24);
      if ( (*v10 & 0xFFFFF) != 0 )
      {
        for ( i = 0; i < v9; ++i )
        {
          if ( (v10[14 * i] & 0xFF00000) != 0 )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_869677332b1638c6b4c8d3aba28d3900_Traceguids);
            HResultException::HResultException((HResultException *)pExceptionObject, -2147024809);
            throw (HResultException *)pExceptionObject;
          }
        }
      }
      v11 = *(_QWORD *)a1[5];
      v12 = *(_QWORD *)a1[4];
      v13 = *(_QWORD *)a1[3];
      v14 = a1[2];
      LODWORD(SRWLock) = 0;
      for ( j = 0; j < v9; j += (unsigned int)SRWLock )
      {
        if ( !(unsigned __int8)EvaluateExpression(
                                 (_DWORD)v14,
                                 v13,
                                 v12,
                                 v11,
                                 v9 - j,
                                 (__int64)&v10[14 * j],
                                 (__int64)&SRWLock) )
        {
          v6 = 0;
          goto LABEL_4;
        }
      }
    }
    v6 = 1;
  }
  else
  {
    v6 = 0;
  }
LABEL_4:
  ScopeGuardImplBase::SafeExecute_ScopeGuardImpl0__lambda_df32225d18b11561a94d7d4071e4b314_____(v25);
  v31 = &NetSetupTraceLogging::EvaluatePluginFilter::`vftable';
  if ( !Block )
    goto LABEL_5;
  wil::ActivityBase<NetSetupTraceLogging,0,2,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(&v31, &SRWLock);
  if ( Block && *(_DWORD *)Block == 1 )
  {
    v17 = 1;
  }
  else
  {
    v17 = 0;
    wil::details::shared_object<wil::ActivityBase<NetSetupTraceLogging,0,2,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<NetSetupTraceLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(&Block);
  }
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  if ( v17 )
  {
LABEL_5:
    if ( *v53 == 1 )
    {
      v18 = v53[22];
      LODWORD(SRWLock) = v18;
      v19 = 2147942974LL;
      if ( v18 < 0 )
        v19 = (unsigned int)v18;
      wil::ActivityBase<NetSetupTraceLogging,0,4,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<NetSetupTraceLogging,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
        v53,
        v19,
        &SRWLock);
      wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(&v31);
    }
  }
  if ( v56 )
    wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)v55);
  if ( Block )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)Block, 0xFFFFFFFF) == 1 )
    {
      v20 = Block;
      if ( Block )
      {
        wil::ActivityBase<NetSetupTraceLogging,0,2,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<NetSetupTraceLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<NetSetupTraceLogging,_TlgReflectorTag_Param0IsProviderType>((char *)Block + 8);
        operator delete(v20);
      }
    }
    Block = 0;
  }
  wil::details::shared_buffer::reset((wil::details::shared_buffer *)&v50);
  if ( v38 )
  {
    v21 = lpMem;
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v21);
    v38 = 0;
  }
  lpMem = 0;
  if ( v32 == 1 )
  {
    v32 = 2;
    v23 = NetSetupTraceLogging::Provider();
    _tlgWriteActivityAutoStop<2,5>(v23, v34);
  }
  v32 = 3;
  return v6;
}

```

## disassembly

```asm
0x18000d860  mov     r11, rsp
0x18000d863  push    rbx
0x18000d864  push    rsi
0x18000d865  push    rdi
0x18000d866  push    r12
0x18000d868  push    r13
0x18000d86a  push    r14
0x18000d86c  push    r15
0x18000d86e  sub     rsp, 2A0h
0x18000d875  mov     [rsp+2D8h+var_278], 0FFFFFFFFFFFFFFFEh
0x18000d87e  mov     rax, cs:__security_cookie
0x18000d885  xor     rax, rsp
0x18000d888  mov     [rsp+2D8h+var_48], rax
0x18000d890  mov     rdi, rcx
0x18000d893  xor     r14d, r14d
0x18000d896  mov     [r11-190h], r14d
0x18000d89d  mov     [r11-18Ch], r14b
0x18000d8a4  mov     [r11-150h], r14b
0x18000d8ab  mov     [r11-168h], r14d
0x18000d8b2  lea     rax, aEvaluateplugin; "EvaluatePluginFilter"
0x18000d8b9  mov     [r11-160h], rax
0x18000d8c0  mov     [r11-158h], r14
0x18000d8c7  mov     [r11-148h], r14d
0x18000d8ce  xorps   xmm0, xmm0
0x18000d8d1  movdqa  [rsp+2D8h+var_A8], xmm0
0x18000d8da  xorps   xmm1, xmm1
0x18000d8dd  xor     eax, eax
0x18000d8df  movups  [rsp+2D8h+var_140], xmm1
0x18000d8e7  movups  [rsp+2D8h+var_130], xmm1
0x18000d8ef  movups  [rsp+2D8h+var_120], xmm1
0x18000d8f7  movups  [rsp+2D8h+var_110], xmm1
0x18000d8ff  movups  [rsp+2D8h+var_100], xmm1
0x18000d907  movups  [rsp+2D8h+var_F0], xmm1
0x18000d90f  movups  [rsp+2D8h+var_E0], xmm1
0x18000d917  movups  [rsp+2D8h+var_D0], xmm1
0x18000d91f  movups  [rsp+2D8h+var_C0], xmm1
0x18000d927  mov     [r11-0B0h], rax
0x18000d92e  mov     [rsp+2D8h+var_98], 1
0x18000d939  mov     [r11-90h], rax
0x18000d940  lea     rax, [r11-190h]
0x18000d947  mov     [r11-88h], rax
0x18000d94e  mov     [r11-80h], r14
0x18000d952  mov     [r11-78h], r14
0x18000d956  lea     rax, [r11-198h]
0x18000d95d  mov     [r11-70h], rax
0x18000d961  mov     [r11-68h], r14
0x18000d965  mov     [r11-60h], r14d
0x18000d969  lea     rax, [r11-168h]
0x18000d970  mov     [r11-58h], rax
0x18000d974  mov     [r11-50h], r14b
0x18000d978  lea     r15, ??_7EvaluatePluginFilter@NetSetupTraceLogging@@6B@; const NetSetupTraceLogging::EvaluatePluginFilter::`vftable'
0x18000d97f  mov     [r11-198h], r15
0x18000d986  mov     r9d, [r9]; unsigned int
0x18000d989  mov     r8, [r8]; wchar_t *
0x18000d98c  lea     rcx, [r11-198h]; this
0x18000d993  call    ?StartActivity@EvaluatePluginFilter@NetSetupTraceLogging@@QEAAXAEBU_GUID@@PEB_WK@Z; NetSetupTraceLogging::EvaluatePluginFilter::StartActivity(_GUID const &,wchar_t const *,ulong)
0x18000d998  nop
0x18000d999  mov     [rsp+2D8h+var_1A0], 1
0x18000d9a1  mov     [rsp+2D8h+var_290], r14b
0x18000d9a6  lea     rax, [rsp+2D8h+var_1A0]
0x18000d9ae  mov     [rsp+2D8h+var_288], rax
0x18000d9b3  lea     rax, [rsp+2D8h+var_198]
0x18000d9bb  mov     [rsp+2D8h+var_280], rax
0x18000d9c0  mov     rbx, [rdi]
0x18000d9c3  cmp     dword ptr [rbx], 0FFFFFFFFh
0x18000d9c6  jz      loc_18000DAA4
0x18000d9cc  mov     rax, [rdi+8]
0x18000d9d0  mov     rcx, [rax+20h]
0x18000d9d4  mov     rax, [rcx]
0x18000d9d7  mov     rax, [rax+8]
0x18000d9db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d9e0  mov     ecx, [rbx]
0x18000d9e2  cmp     [rax+rcx*8], r14
0x18000d9e6  jnz     loc_18000DAA4
0x18000d9ec  xor     dil, dil
0x18000d9ef  lea     rcx, [rsp+2D8h+var_290]
0x18000d9f4  call    ScopeGuardImplBase__SafeExecute_ScopeGuardImpl0__lambda_df32225d18b11561a94d7d4071e4b314_____
0x18000d9f9  nop
0x18000d9fa  mov     [rsp+2D8h+var_198], r15
0x18000da02  cmp     [rsp+2D8h+Block], 0
0x18000da0b  jnz     loc_18000DBDF
0x18000da11  mov     rcx, [rsp+2D8h+var_88]
0x18000da19  cmp     dword ptr [rcx], 1
0x18000da1c  jz      loc_18000DC20
0x18000da22  cmp     [rsp+2D8h+var_60], 0
0x18000da2a  jnz     loc_18000DB37
0x18000da30  mov     rcx, [rsp+2D8h+Block]
0x18000da38  test    rcx, rcx
0x18000da3b  jnz     loc_18000DC4D
0x18000da41  lea     rcx, [rsp+2D8h+var_A8]; this
0x18000da49  call    ?reset@shared_buffer@details@wil@@QEAAXXZ; wil::details::shared_buffer::reset(void)
0x18000da4e  cmp     [rsp+2D8h+var_150], 0
0x18000da56  jnz     loc_18000DC86
0x18000da5c  mov     [rsp+2D8h+lpMem], r14
0x18000da64  cmp     [rsp+2D8h+var_190], 1
0x18000da6c  jz      loc_18000DCAF
0x18000da72  mov     [rsp+2D8h+var_190], 3
0x18000da7d  movzx   eax, dil
0x18000da81  mov     rcx, [rsp+2D8h+var_48]
0x18000da89  xor     rcx, rsp; StackCookie
0x18000da8c  call    __security_check_cookie
0x18000da91  add     rsp, 2A0h
0x18000da98  pop     r15
0x18000da9a  pop     r14
0x18000da9c  pop     r13
0x18000da9e  pop     r12
0x18000daa0  pop     rdi
0x18000daa1  pop     rsi
0x18000daa2  pop     rbx
0x18000daa3  retn
0x18000daa4  mov     rax, [rdi+8]
0x18000daa8  mov     rcx, [rax+18h]
0x18000daac  mov     ebx, [rcx+10h]
0x18000daaf  test    ebx, ebx
0x18000dab1  jz      short loc_18000DB2F
0x18000dab3  mov     rsi, [rcx+18h]
0x18000dab7  test    dword ptr [rsi], 0FFFFFh
0x18000dabd  jnz     loc_18000DB49
0x18000dac3  mov     rax, [rdi+28h]
0x18000dac7  mov     r14, [rax]
0x18000daca  mov     rax, [rdi+20h]
0x18000dace  mov     r15, [rax]
0x18000dad1  mov     rax, [rdi+18h]
0x18000dad5  mov     r12, [rax]
0x18000dad8  mov     r13, [rdi+10h]
0x18000dadc  mov     dword ptr [rsp+2D8h+SRWLock], 0
0x18000dae4  xor     edi, edi
0x18000dae6  cmp     edi, ebx
0x18000dae8  jnb     short loc_18000DB25
0x18000daea  mov     eax, edi
0x18000daec  imul    rcx, rax, 38h ; '8'
0x18000daf0  add     rcx, rsi
0x18000daf3  mov     eax, ebx
0x18000daf5  sub     eax, edi
0x18000daf7  lea     rdx, [rsp+2D8h+SRWLock]
0x18000dafc  mov     [rsp+2D8h+var_2A8], rdx
0x18000db01  mov     [rsp+2D8h+var_2B0], rcx
0x18000db06  mov     [rsp+2D8h+var_2B8], eax
0x18000db0a  mov     r9, r14
0x18000db0d  mov     r8, r15
0x18000db10  mov     rdx, r12
0x18000db13  mov     rcx, r13
0x18000db16  call    EvaluateExpression
0x18000db1b  test    al, al
0x18000db1d  jz      short loc_18000DB67
0x18000db1f  add     edi, dword ptr [rsp+2D8h+SRWLock]
0x18000db23  jmp     short loc_18000DAE6
0x18000db25  xor     r14d, r14d
0x18000db28  lea     r15, ??_7EvaluatePluginFilter@NetSetupTraceLogging@@6B@; const NetSetupTraceLogging::EvaluatePluginFilter::`vftable'
0x18000db2f  mov     dil, 1
0x18000db32  jmp     loc_18000D9EF
0x18000db37  lea     rcx, [rsp+2D8h+var_78]; this
0x18000db3f  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x18000db44  jmp     loc_18000DA30
0x18000db49  mov     edx, r14d
0x18000db4c  cmp     edx, ebx
0x18000db4e  jnb     loc_18000DAC3
0x18000db54  mov     eax, edx
0x18000db56  imul    rcx, rax, 38h ; '8'
0x18000db5a  test    dword ptr [rcx+rsi], 0FF00000h
0x18000db61  jnz     short loc_18000DB79
0x18000db63  inc     edx
0x18000db65  jmp     short loc_18000DB4C
0x18000db67  xor     dil, dil
0x18000db6a  xor     r14d, r14d
0x18000db6d  lea     r15, ??_7EvaluatePluginFilter@NetSetupTraceLogging@@6B@; const NetSetupTraceLogging::EvaluatePluginFilter::`vftable'
0x18000db74  jmp     loc_18000D9EF
0x18000db79  lea     rax, WPP_GLOBAL_Control
0x18000db80  mov     rcx, cs:WPP_GLOBAL_Control
0x18000db87  cmp     rcx, rax
0x18000db8a  jz      short loc_18000DBA7
0x18000db8c  cmp     byte ptr [rcx+19h], 2
0x18000db90  jb      short loc_18000DBA7
0x18000db92  mov     edx, 1Fh
0x18000db97  lea     r8, WPP_869677332b1638c6b4c8d3aba28d3900_Traceguids
0x18000db9e  mov     rcx, [rcx+10h]
0x18000dba2  call    WPP_SF_
0x18000dba7  mov     edx, 80070057h; int
0x18000dbac  lea     rcx, [rsp+2D8h+pExceptionObject]; this
0x18000dbb1  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x18000dbb6  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x18000dbbd  lea     rcx, [rsp+2D8h+pExceptionObject]; pExceptionObject
0x18000dbc2  call    _CxxThrowException_0
0x18000dbc8  mov     rcx, [rsp+2D8h+SRWLock]; SRWLock
0x18000dbcd  test    rcx, rcx
0x18000dbd0  jnz     short loc_18000DC18
0x18000dbd2  test    bl, bl
0x18000dbd4  jnz     loc_18000DA11
0x18000dbda  jmp     loc_18000DA22
0x18000dbdf  lea     rdx, [rsp+2D8h+SRWLock]
0x18000dbe4  lea     rcx, [rsp+2D8h+var_198]
0x18000dbec  call    ?LockExclusive@?$ActivityBase@VNetSetupTraceLogging@@$0A@$01$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<NetSetupTraceLogging,0,2,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000dbf1  mov     rax, [rsp+2D8h+Block]
0x18000dbf9  test    rax, rax
0x18000dbfc  jz      short loc_18000DC07
0x18000dbfe  cmp     dword ptr [rax], 1
0x18000dc01  jnz     short loc_18000DC07
0x18000dc03  mov     bl, 1
0x18000dc05  jmp     short loc_18000DBC8
0x18000dc07  xor     bl, bl
0x18000dc09  lea     rcx, [rsp+2D8h+Block]
0x18000dc11  call    ?reset@?$shared_object@V?$ActivityData@VNetSetupTraceLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VNetSetupTraceLogging@@$0A@$01$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<NetSetupTraceLogging,0,2,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<NetSetupTraceLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x18000dc16  jmp     short loc_18000DBC8
0x18000dc18  call    cs:__imp_ReleaseSRWLockExclusive
0x18000dc1e  jmp     short loc_18000DBD2
0x18000dc20  mov     eax, [rcx+58h]
0x18000dc23  mov     dword ptr [rsp+2D8h+SRWLock], eax
0x18000dc27  mov     edx, 8007023Eh
0x18000dc2c  test    eax, eax
0x18000dc2e  cmovs   edx, eax
0x18000dc31  lea     r8, [rsp+2D8h+SRWLock]
0x18000dc36  call    ?SetStopResult@?$ActivityData@VNetSetupTraceLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VNetSetupTraceLogging@@$0A@$03$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA_NJPEAJ@Z; wil::ActivityBase<NetSetupTraceLogging,0,4,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<NetSetupTraceLogging,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)
0x18000dc3b  lea     rcx, [rsp+2D8h+var_198]
0x18000dc43  call    ?ReportStopActivity@?$ActivityBase@VNetSetupTraceLogging@@$0A@$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAAXJ@Z; wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(long)
0x18000dc48  jmp     loc_18000DA22
0x18000dc4d  mov     eax, 0FFFFFFFFh
0x18000dc52  lock xadd [rcx], eax
0x18000dc56  cmp     eax, 1
0x18000dc59  jnz     short loc_18000DC79
0x18000dc5b  mov     rbx, [rsp+2D8h+Block]
0x18000dc63  test    rbx, rbx
0x18000dc66  jz      short loc_18000DC79
0x18000dc68  lea     rcx, [rbx+8]
0x18000dc6c  call    ??1?$ActivityData@VNetSetupTraceLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VNetSetupTraceLogging@@$0A@$01$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<NetSetupTraceLogging,0,2,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<NetSetupTraceLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<NetSetupTraceLogging,_TlgReflectorTag_Param0IsProviderType>(void)
0x18000dc71  mov     rcx, rbx; Block
0x18000dc74  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000dc79  mov     [rsp+2D8h+Block], r14
0x18000dc81  jmp     loc_18000DA41
0x18000dc86  mov     rbx, [rsp+2D8h+lpMem]
0x18000dc8e  call    cs:__imp_GetProcessHeap
0x18000dc94  mov     r8, rbx; lpMem
0x18000dc97  xor     edx, edx; dwFlags
0x18000dc99  mov     rcx, rax; hHeap
0x18000dc9c  call    cs:__imp_HeapFree
0x18000dca2  mov     [rsp+2D8h+var_150], 0
0x18000dcaa  jmp     loc_18000DA5C
0x18000dcaf  mov     [rsp+2D8h+var_190], 2
0x18000dcba  call    ?Provider@NetSetupTraceLogging@@SAPEBU_tlgProvider_t@@XZ; NetSetupTraceLogging::Provider(void)
0x18000dcbf  lea     rdx, [rsp+2D8h+var_188]
0x18000dcc7  mov     rcx, rax
0x18000dcca  call    ??$_tlgWriteActivityAutoStop@$01$04@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z; _tlgWriteActivityAutoStop<2,5>(_tlgProvider_t const *,_GUID const *)
0x18000dccf  jmp     loc_18000DA72
```
