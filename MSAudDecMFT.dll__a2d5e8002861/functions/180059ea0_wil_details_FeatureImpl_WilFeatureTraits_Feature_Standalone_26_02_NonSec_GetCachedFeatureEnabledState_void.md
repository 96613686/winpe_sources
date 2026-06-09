# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x180059ea0`
- end: `0x18005a114`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_02_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `628`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18005ae40`

## callees

- `0x180059ea0`
- `0x18005cdc0`
- `0x1800960c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180059f1d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180059f84`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005a0c6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180059f1d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180059f84`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005a0c6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180059efa`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005a07d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180059efa`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005a07d`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCachedFeatureEnabledState(
        __int64 a1,
        _QWORD *a2)
{
  int v3; // eax
  int v4; // esi
  void (__fastcall *v5)(__int64 *, __int64 (__fastcall *)(void *), void *); // rax
  __int64 (__fastcall *v6)(__int64, __int64, __int64 *); // rax
  int v7; // eax
  unsigned int v8; // r8d
  __int16 v9; // di
  __int16 v10; // ax
  unsigned __int16 v11; // di
  int v12; // eax
  signed __int32 v13; // edx
  signed __int32 v14; // ecx
  unsigned __int64 v15; // r8
  int v16; // ecx
  _QWORD Source[5]; // [rsp+20h] [rbp-28h] BYREF
  __int64 v19; // [rsp+50h] [rbp+8h] BYREF

  v19 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_Standalone_26_02_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_26_02_NonSec__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = dword_1800E5E64;
  if ( !dword_1800E5E64 )
  {
    if ( wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      if ( qword_1800E5EA8 )
      {
        v4 = dword_1800E5E64;
LABEL_6:
        ReleaseSRWLockExclusive(&SRWLock);
        goto LABEL_13;
      }
      qword_1800E5EA8 = 0;
      v5 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v5 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v5(
          &qword_1800E5EA8,
          _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_,
          &wil::details::g_enabledStateManager);
        if ( qword_1800E5EA8 )
        {
          v4 = 1;
          dword_1800E5E64 = 1;
          goto LABEL_6;
        }
      }
      ReleaseSRWLockExclusive(&SRWLock);
    }
    v4 = 0;
  }
LABEL_13:
  LODWORD(v19) = 0;
  v6 = (__int64 (__fastcall *)(__int64, __int64, __int64 *))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v6 = (__int64 (__fastcall *)(__int64, __int64, __int64 *))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v7 = v6(58599550, 3, &v19);
    v8 = v7 & 0xFFFFFF3F;
    v9 = 8 * (v7 & 0x80 | (4 * (v7 & 0x40 | (4 * (v7 & 3)))));
    if ( (v7 & 0xFFFFFF3F) != 0 )
    {
      v10 = 0;
      if ( v8 == 2 )
        v10 = 64;
      goto LABEL_21;
    }
  }
  else
  {
    v9 = 0;
  }
  v10 = 64;
LABEL_21:
  v11 = v10 | v9;
  v12 = *(_DWORD *)a2;
  do
  {
    v13 = v12;
    *(_DWORD *)a2 = v12;
    if ( (_DWORD)v19 && (v12 & 2) == 0 )
    {
      v12 = (v12
           ^ (v11
            ^ (unsigned __int16)v12)
           & 0x180
           ^ ((unsigned __int8)v11
            ^ (unsigned __int8)(v12 ^ (v11 ^ v12) & 0x80))
           & 0x40
           | 1)
          ^ (v11
           ^ ((unsigned __int16)(v12
                               ^ (v11
                                ^ v12)
                               & 0x180
                               ^ ((unsigned __int8)v11
                                ^ (unsigned __int8)(v12 ^ (v11 ^ v12) & 0x80))
                               & 0x40)
            | 1))
          & 0x800
          | 2;
      *(_DWORD *)a2 = v12;
    }
    v14 = v12;
    if ( (v13 & 4) == 0 )
    {
      v14 = v12 ^ (v11 ^ (unsigned __int16)v12) & 0x400 | 4;
      *(_DWORD *)a2 = v14;
    }
    v12 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_26_02_NonSec__descriptor, v14, v13);
  }
  while ( v13 != v12 );
  if ( (v13 & 4) == 0 && wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&SRWLock);
    if ( !v4
      || v4 != dword_1800E5E64
      || (Source[0] = 3,
          Source[1] = Feature_Standalone_26_02_NonSec__descriptor,
          !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)&::Source, Source, v15)) )
    {
      _InterlockedAnd((volatile signed __int32 *)Feature_Standalone_26_02_NonSec__descriptor, 0xFFFFFFFB);
    }
    ReleaseSRWLockExclusive(&SRWLock);
  }
  if ( (*(_DWORD *)a2 & 2) == 0 )
  {
    v16 = *(_DWORD *)a2
        ^ (v11
         ^ (unsigned __int16)*(_DWORD *)a2)
        & 0x180
        ^ ((unsigned __int8)v11
         ^ (unsigned __int8)(*(_DWORD *)a2 ^ (v11 ^ *(_DWORD *)a2) & 0x80))
        & 0x40
        | 1;
    *(_DWORD *)a2 = v16 ^ (v11 ^ (unsigned __int16)v16) & 0x800;
  }
  return a2;
}

```

## disassembly

```asm
0x180059ea0  mov     [rsp+arg_8], rbx
0x180059ea5  mov     [rsp+arg_10], rbp
0x180059eaa  mov     [rsp+arg_0], rcx
0x180059eaf  push    rsi
0x180059eb0  push    rdi
0x180059eb1  push    r14
0x180059eb3  sub     rsp, 30h
0x180059eb7  mov     rbx, rdx
0x180059eba  mov     r14, cs:Feature_Standalone_26_02_NonSec__descriptor
0x180059ec1  xor     ebp, ebp
0x180059ec3  mov     [rdx], rbp
0x180059ec6  mov     eax, [r14]
0x180059ec9  mov     [rdx], eax
0x180059ecb  and     eax, 6
0x180059ece  cmp     al, 6
0x180059ed0  jz      loc_18005A0FD
0x180059ed6  mov     esi, cs:dword_1800E5E64
0x180059edc  nop
0x180059edd  test    esi, esi
0x180059edf  jnz     loc_180059F92
0x180059ee5  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180059eeb  test    eax, eax
0x180059eed  jz      loc_180059F90
0x180059ef3  lea     rcx, SRWLock; SRWLock
0x180059efa  call    cs:__imp_AcquireSRWLockExclusive
0x180059f01  nop     dword ptr [rax+rax+00h]
0x180059f06  cmp     cs:qword_1800E5EA8, rbp
0x180059f0d  jz      short loc_180059F2B
0x180059f0f  mov     esi, cs:dword_1800E5E64
0x180059f15  nop
0x180059f16  lea     rcx, SRWLock; SRWLock
0x180059f1d  call    cs:__imp_ReleaseSRWLockExclusive
0x180059f24  nop     dword ptr [rax+rax+00h]
0x180059f29  jmp     short loc_180059F92
0x180059f2b  mov     cs:qword_1800E5EA8, rbp
0x180059f32  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x180059f39  test    rax, rax
0x180059f3c  jnz     short loc_180059F4A
0x180059f3e  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x180059f45  test    rax, rax
0x180059f48  jz      short loc_180059F7D
0x180059f4a  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180059f51  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x180059f58  lea     rcx, qword_1800E5EA8
0x180059f5f  call    cs:__guard_dispatch_icall_fptr
0x180059f65  cmp     cs:qword_1800E5EA8, 0
0x180059f6d  jz      short loc_180059F7D
0x180059f6f  nop
0x180059f70  mov     esi, 1
0x180059f75  mov     cs:dword_1800E5E64, esi
0x180059f7b  jmp     short loc_180059F16
0x180059f7d  lea     rcx, SRWLock; SRWLock
0x180059f84  call    cs:__imp_ReleaseSRWLockExclusive
0x180059f8b  nop     dword ptr [rax+rax+00h]
0x180059f90  mov     esi, ebp
0x180059f92  mov     dword ptr [rsp+48h+arg_0], ebp
0x180059f96  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180059f9d  test    rax, rax
0x180059fa0  jnz     short loc_180059FAE
0x180059fa2  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180059fa9  test    rax, rax
0x180059fac  jz      short loc_18005A004
0x180059fae  lea     r8, [rsp+48h+arg_0]
0x180059fb3  mov     edx, 3
0x180059fb8  mov     ecx, 37E287Eh
0x180059fbd  call    cs:__guard_dispatch_icall_fptr
0x180059fc3  mov     edx, eax
0x180059fc5  mov     r8d, eax
0x180059fc8  and     r8d, 0FFFFFF3Fh
0x180059fcf  mov     ecx, r8d
0x180059fd2  and     ecx, 3
0x180059fd5  shl     ecx, 2
0x180059fd8  and     eax, 40h
0x180059fdb  or      ecx, eax
0x180059fdd  shl     ecx, 2
0x180059fe0  and     edx, 80h
0x180059fe6  or      ecx, edx
0x180059fe8  lea     edi, ds:0[rcx*8]
0x180059fef  test    r8d, r8d
0x180059ff2  jz      short loc_18005A006
0x180059ff4  mov     eax, ebp
0x180059ff6  mov     ecx, 40h ; '@'
0x180059ffb  cmp     r8d, 2
0x180059fff  cmovz   eax, ecx
0x18005a002  jmp     short loc_18005A00B
0x18005a004  mov     edi, ebp
0x18005a006  mov     eax, 40h ; '@'
0x18005a00b  or      edi, eax
0x18005a00d  mov     eax, [rbx]
0x18005a00f  mov     edx, eax
0x18005a011  mov     [rbx], eax
0x18005a013  cmp     dword ptr [rsp+48h+arg_0], 0
0x18005a018  jz      short loc_18005A044
0x18005a01a  test    dl, 2
0x18005a01d  jnz     short loc_18005A044
0x18005a01f  xor     eax, edi
0x18005a021  and     eax, 180h
0x18005a026  xor     eax, edx
0x18005a028  mov     ecx, eax
0x18005a02a  xor     ecx, edi
0x18005a02c  and     ecx, 40h
0x18005a02f  xor     ecx, eax
0x18005a031  or      ecx, 1
0x18005a034  mov     eax, ecx
0x18005a036  xor     eax, edi
0x18005a038  and     eax, 800h
0x18005a03d  xor     eax, ecx
0x18005a03f  or      eax, 2
0x18005a042  mov     [rbx], eax
0x18005a044  mov     r8d, edx
0x18005a047  and     r8d, 4
0x18005a04b  mov     ecx, eax
0x18005a04d  jnz     short loc_18005A05E
0x18005a04f  xor     ecx, edi
0x18005a051  and     ecx, 400h
0x18005a057  xor     ecx, eax
0x18005a059  or      ecx, 4
0x18005a05c  mov     [rbx], ecx
0x18005a05e  mov     eax, edx
0x18005a060  lock cmpxchg [r14], ecx
0x18005a065  jnz     short loc_18005A00F
0x18005a067  test    r8d, r8d
0x18005a06a  jnz     short loc_18005A0D2
0x18005a06c  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18005a072  test    eax, eax
0x18005a074  jz      short loc_18005A0D2
0x18005a076  lea     rcx, SRWLock; SRWLock
0x18005a07d  call    cs:__imp_AcquireSRWLockExclusive
0x18005a084  nop     dword ptr [rax+rax+00h]
0x18005a089  mov     eax, cs:dword_1800E5E64
0x18005a08f  test    esi, esi
0x18005a091  jz      short loc_18005A0BA
0x18005a093  cmp     esi, eax
0x18005a095  jnz     short loc_18005A0BA
0x18005a097  mov     [rsp+48h+Source], 3
0x18005a0a0  mov     [rsp+48h+var_20], r14
0x18005a0a5  lea     rdx, [rsp+48h+Source]; Source
0x18005a0aa  lea     rcx, Source; this
0x18005a0b1  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18005a0b6  test    al, al
0x18005a0b8  jnz     short loc_18005A0BF
0x18005a0ba  lock and dword ptr [r14], 0FFFFFFFBh
0x18005a0bf  lea     rcx, SRWLock; SRWLock
0x18005a0c6  call    cs:__imp_ReleaseSRWLockExclusive
0x18005a0cd  nop     dword ptr [rax+rax+00h]
0x18005a0d2  mov     ecx, [rbx]
0x18005a0d4  test    cl, 2
0x18005a0d7  jnz     short loc_18005A0FD
0x18005a0d9  mov     eax, ecx
0x18005a0db  xor     eax, edi
0x18005a0dd  and     eax, 180h
0x18005a0e2  xor     eax, ecx
0x18005a0e4  mov     ecx, eax
0x18005a0e6  xor     ecx, edi
0x18005a0e8  and     ecx, 40h
0x18005a0eb  xor     ecx, eax
0x18005a0ed  or      ecx, 1
0x18005a0f0  mov     eax, ecx
0x18005a0f2  xor     eax, edi
0x18005a0f4  and     eax, 800h
0x18005a0f9  xor     eax, ecx
0x18005a0fb  mov     [rbx], eax
0x18005a0fd  mov     rax, rbx
0x18005a100  mov     rbx, [rsp+48h+arg_8]
0x18005a105  mov     rbp, [rsp+48h+arg_10]
0x18005a10a  add     rsp, 30h
0x18005a10e  pop     r14
0x18005a110  pop     rdi
0x18005a111  pop     rsi
0x18005a112  retn
```
