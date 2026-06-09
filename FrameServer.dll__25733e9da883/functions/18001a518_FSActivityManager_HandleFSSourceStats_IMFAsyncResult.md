# FSActivityManager::HandleFSSourceStats(IMFAsyncResult *)

- ea: `0x18001a518`
- end: `0x18001a840`
- name: `?HandleFSSourceStats@FSActivityManager@@IEAAXPEAUIMFAsyncResult@@@Z`
- size: `808`
- prototype: `void __fastcall(FSActivityManager *__hidden this, struct IMFAsyncResult *)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001afc0`

## callees

- `0x18000920c`
- `0x1800095c8`
- `0x180009608`
- `0x1800096f4`
- `0x18000a460`
- `0x1800180c8`
- `0x180019a9c`
- `0x18001a518`
- `0x18001b7a8`
- `0x180023174`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a621`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a6b9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a788`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a7ec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a621`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a6b9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a788`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a7ec`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a579`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a68c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a6fa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a579`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a68c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a6fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a6de`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a6de`
- `MFPlat!MFScheduleWorkItem` at `0x18001a74d`
- `MFPlat!MFScheduleWorkItem` at `0x18001a74d`

## pseudocode

```c
void __fastcall FSActivityManager::HandleFSSourceStats(FSActivityManager *this, struct IMFAsyncResult *a2)
{
  unsigned int v3; // r14d
  struct _RTL_CRITICAL_SECTION *v4; // rdi
  void *v5; // rdx
  int v6; // esi
  __int64 v7; // rdx
  unsigned int v8; // r15d
  _QWORD *v9; // rdi
  unsigned int i; // r12d
  __int64 v11; // r13
  const unsigned __int16 *v12; // r13
  void *v13; // rdx
  HRESULT v14; // eax
  __int64 v15; // rdx
  __int64 v16; // [rsp+20h] [rbp-38h]
  struct __MIDL___MIDL_itf_mfdeviceinternal_0000_0047_0004 *v17; // [rsp+30h] [rbp-28h]
  _QWORD *v18; // [rsp+38h] [rbp-20h] BYREF
  unsigned int v19; // [rsp+40h] [rbp-18h]
  __int64 v20; // [rsp+44h] [rbp-14h]
  struct IMFAsyncResult *v21; // [rsp+A8h] [rbp+50h] BYREF
  LPVOID pv; // [rsp+B0h] [rbp+58h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+B8h] [rbp+60h]

  v21 = a2;
  v18 = 0;
  v3 = 0;
  v20 = 0;
  v19 = 0;
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), 73, &WPP_47229f29bd5f33e3e7f2581ae6977b5e_Traceguids, this);
  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 176);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 176));
  --*((_DWORD *)this + 56);
  *((_QWORD *)this + 29) = 0;
  if ( *((_BYTE *)this + 240) )
  {
    v6 = 0;
    if ( *((_DWORD *)this + 56) )
      goto LABEL_32;
    wil::details::SetEvent(*((wil::details **)this + 27), v5);
    if ( (unsigned __int8)byte_18010EC4D < 8u )
      goto LABEL_32;
    v7 = 74;
LABEL_7:
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), v7, &WPP_47229f29bd5f33e3e7f2581ae6977b5e_Traceguids, this);
LABEL_32:
    LeaveCriticalSection(v4);
LABEL_33:
    if ( (unsigned __int8)byte_18010EC4D >= 8u )
    {
      v15 = 80;
      goto LABEL_35;
    }
    goto LABEL_36;
  }
  if ( (unsigned int)CTUnkArray<FSCallback<IFSSourceMediaEventCallback,unsigned __int64,enum __MIDL___MIDL_itf_fsclienttypes_0000_0000_0001>>::Add(
                       &v18,
                       (char *)this + 368) )
  {
    v6 = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 176));
    v3 = v19;
    v8 = 0;
    if ( !v19 )
      goto LABEL_33;
    v9 = v18;
    do
    {
      pv = 0;
      LODWORD(v21) = 0;
      if ( (int)FSActivityObject::GetFSSourceHealthStats(
                  (FSActivityObject *)v9[v8],
                  (struct __MIDL___MIDL_itf_mfdeviceinternal_0000_0047_0004 **)&pv,
                  (unsigned int *)&v21) >= 0 )
      {
        for ( i = 0; i < (unsigned int)v21; ++i )
        {
          v11 = v9[v8];
          v17 = (struct __MIDL___MIDL_itf_mfdeviceinternal_0000_0047_0004 *)((char *)pv + 352 * i);
          lpCriticalSection = (LPCRITICAL_SECTION)(v11 + 24);
          EnterCriticalSection((LPCRITICAL_SECTION)(v11 + 24));
          if ( *(_BYTE *)(v11 + 64) )
            v12 = L"<shutdown>";
          else
            v12 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v11 + 88) + 32LL))(*(_QWORD *)(v11 + 88));
          LeaveCriticalSection(lpCriticalSection);
          FSActivityManager::PostStatsToETW(this, v12, v17);
        }
        CoTaskMemFree(pv);
      }
      ++v8;
    }
    while ( v8 < v3 );
    v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 176);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 176));
    v6 = 0;
    if ( *((_BYTE *)this + 240) )
    {
      if ( *((_DWORD *)this + 56) )
        goto LABEL_32;
      wil::details::SetEvent(*((wil::details **)this + 27), v13);
      if ( (unsigned __int8)byte_18010EC4D < 8u )
        goto LABEL_32;
      v7 = 76;
      goto LABEL_7;
    }
    v14 = MFScheduleWorkItem((IMFAsyncCallback *)this + 1, 0, -500, (MFWORKITEM_KEY *)this + 29);
    v6 = v14;
    if ( v14 >= 0 )
    {
      ++*((_DWORD *)this + 56);
      if ( (unsigned __int8)byte_18010EC4D >= 8u )
        WPP_SF_qqD(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          78,
          &WPP_47229f29bd5f33e3e7f2581ae6977b5e_Traceguids,
          this,
          *((_QWORD *)this + 29),
          *((_DWORD *)this + 56));
      goto LABEL_32;
    }
    if ( g_wppLevels )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 77, &WPP_47229f29bd5f33e3e7f2581ae6977b5e_Traceguids, this, v14);
  }
  else
  {
    v6 = -2147024882;
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        75,
        &WPP_47229f29bd5f33e3e7f2581ae6977b5e_Traceguids,
        this,
        -2147024882);
  }
  LeaveCriticalSection(v4);
  if ( byte_18010EC4D )
  {
    v15 = 79;
LABEL_35:
    LODWORD(v16) = v6;
    WPP_SF_qDD(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      v15,
      &WPP_47229f29bd5f33e3e7f2581ae6977b5e_Traceguids,
      this,
      v16,
      v3);
  }
LABEL_36:
  CTUnkArray<SensorTransformContextStream>::~CTUnkArray<SensorTransformContextStream>((void **)&v18);
}

```

## disassembly

```asm
0x18001a518  mov     [rsp-40h+arg_8], rdx
0x18001a51d  push    rbp
0x18001a51e  push    rbx
0x18001a51f  push    rsi
0x18001a520  push    rdi
0x18001a521  push    r12
0x18001a523  push    r13
0x18001a525  push    r14
0x18001a527  push    r15
0x18001a529  mov     rbp, rsp
0x18001a52c  sub     rsp, 58h
0x18001a530  xor     r13d, r13d
0x18001a533  mov     rbx, rcx
0x18001a536  mov     [rbp+var_20], r13
0x18001a53a  mov     r14d, r13d
0x18001a53d  mov     [rbp+var_14], r13
0x18001a541  mov     [rbp+var_18], r13d
0x18001a545  cmp     cs:byte_18010EC4D, 8
0x18001a54c  jb      short loc_18001A56F
0x18001a54e  mov     r9, rcx
0x18001a551  lea     edx, [r13+49h]
0x18001a555  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a55c  lea     r8, WPP_47229f29bd5f33e3e7f2581ae6977b5e_Traceguids
0x18001a563  mov     rcx, [rcx+0D8h]
0x18001a56a  call    WPP_SF_q
0x18001a56f  lea     rdi, [rbx+0B0h]
0x18001a576  mov     rcx, rdi; lpCriticalSection
0x18001a579  call    cs:__imp_EnterCriticalSection
0x18001a57f  dec     dword ptr [rbx+0E0h]
0x18001a585  mov     [rbx+0E8h], r13
0x18001a58c  cmp     [rbx+0F0h], r13b
0x18001a593  jz      short loc_18001A5E5
0x18001a595  mov     esi, r13d
0x18001a598  cmp     [rbx+0E0h], r13d
0x18001a59f  jnz     loc_18001A7E9
0x18001a5a5  mov     rcx, [rbx+0D8h]; this
0x18001a5ac  call    ?SetEvent@details@wil@@YAXPEAX@Z; wil::details::SetEvent(void *)
0x18001a5b1  cmp     cs:byte_18010EC4D, 8
0x18001a5b8  jb      loc_18001A7E9
0x18001a5be  mov     edx, 4Ah ; 'J'
0x18001a5c3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a5ca  lea     r8, WPP_47229f29bd5f33e3e7f2581ae6977b5e_Traceguids
0x18001a5d1  mov     r9, rbx
0x18001a5d4  mov     rcx, [rcx+0D8h]
0x18001a5db  call    WPP_SF_q
0x18001a5e0  jmp     loc_18001A7E9
0x18001a5e5  lea     rdx, [rbx+170h]
0x18001a5ec  lea     rcx, [rbp+var_20]
0x18001a5f0  call    ?Add@?$CTUnkArray@V?$FSCallback@UIFSSourceMediaEventCallback@@_KW4__MIDL___MIDL_itf_fsclienttypes_0000_0000_0001@@@@@@QEAAHAEAV1@@Z; CTUnkArray<FSCallback<IFSSourceMediaEventCallback,unsigned __int64,__MIDL___MIDL_itf_fsclienttypes_0000_0000_0001>>::Add(CTUnkArray<FSCallback<IFSSourceMediaEventCallback,unsigned __int64,__MIDL___MIDL_itf_fsclienttypes_0000_0000_0001>> &)
0x18001a5f5  test    eax, eax
0x18001a5f7  jnz     short loc_18001A617
0x18001a5f9  mov     esi, 8007000Eh
0x18001a5fe  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001a605  jb      loc_18001A785
0x18001a60b  lea     edx, [rax+4Bh]
0x18001a60e  mov     dword ptr [rsp+58h+var_38], esi
0x18001a612  jmp     loc_18001A76B
0x18001a617  mov     rcx, rdi; lpCriticalSection
0x18001a61a  mov     [rbp+arg_0], r13d
0x18001a61e  mov     esi, r13d
0x18001a621  call    cs:__imp_LeaveCriticalSection
0x18001a627  mov     r14d, [rbp+var_18]
0x18001a62b  mov     r15d, r13d
0x18001a62e  test    r14d, r14d
0x18001a631  jz      loc_18001A7F2
0x18001a637  mov     rdi, [rbp+var_20]
0x18001a63b  mov     [rbp+pv], r13
0x18001a63f  lea     r8, [rbp+arg_8]; unsigned int *
0x18001a643  mov     dword ptr [rbp+arg_8], r13d
0x18001a647  lea     rdx, [rbp+pv]; struct __MIDL___MIDL_itf_mfdeviceinternal_0000_0047_0004 **
0x18001a64b  mov     esi, r15d
0x18001a64e  mov     rcx, [rdi+rsi*8]; this
0x18001a652  call    ?GetFSSourceHealthStats@FSActivityObject@@QEAAJPEAPEAU__MIDL___MIDL_itf_mfdeviceinternal_0000_0047_0004@@PEAK@Z; FSActivityObject::GetFSSourceHealthStats(__MIDL___MIDL_itf_mfdeviceinternal_0000_0047_0004 * *,ulong *)
0x18001a657  test    eax, eax
0x18001a659  js      loc_18001A6E4
0x18001a65f  mov     r12d, r13d
0x18001a662  cmp     dword ptr [rbp+arg_8], r13d
0x18001a666  jbe     short loc_18001A6DA
0x18001a668  mov     r13, [rdi+rsi*8]
0x18001a66c  mov     eax, r12d
0x18001a66f  imul    rcx, rax, 160h
0x18001a676  mov     rax, [rbp+pv]
0x18001a67a  add     rax, rcx
0x18001a67d  mov     [rbp+var_28], rax
0x18001a681  lea     rax, [r13+18h]
0x18001a685  mov     rcx, rax; lpCriticalSection
0x18001a688  mov     [rbp+lpCriticalSection], rax
0x18001a68c  call    cs:__imp_EnterCriticalSection
0x18001a692  cmp     byte ptr [r13+40h], 0
0x18001a697  jz      short loc_18001A6A2
0x18001a699  lea     r13, aShutdown; "<shutdown>"
0x18001a6a0  jmp     short loc_18001A6B5
0x18001a6a2  mov     rcx, [r13+58h]
0x18001a6a6  mov     rax, [rcx]
0x18001a6a9  mov     rax, [rax+20h]
0x18001a6ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a6b2  mov     r13, rax
0x18001a6b5  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x18001a6b9  call    cs:__imp_LeaveCriticalSection
0x18001a6bf  mov     r8, [rbp+var_28]; struct __MIDL___MIDL_itf_mfdeviceinternal_0000_0047_0004 *
0x18001a6c3  mov     rdx, r13; unsigned __int16 *
0x18001a6c6  mov     rcx, rbx; this
0x18001a6c9  call    ?PostStatsToETW@FSActivityManager@@IEAAXPEBGAEBU__MIDL___MIDL_itf_mfdeviceinternal_0000_0047_0004@@@Z; FSActivityManager::PostStatsToETW(ushort const *,__MIDL___MIDL_itf_mfdeviceinternal_0000_0047_0004 const &)
0x18001a6ce  inc     r12d
0x18001a6d1  cmp     r12d, dword ptr [rbp+arg_8]
0x18001a6d5  jb      short loc_18001A668
0x18001a6d7  xor     r13d, r13d
0x18001a6da  mov     rcx, [rbp+pv]; pv
0x18001a6de  call    cs:__imp_CoTaskMemFree
0x18001a6e4  inc     r15d
0x18001a6e7  cmp     r15d, r14d
0x18001a6ea  jb      loc_18001A63B
0x18001a6f0  lea     rdi, [rbx+0B0h]
0x18001a6f7  mov     rcx, rdi; lpCriticalSection
0x18001a6fa  call    cs:__imp_EnterCriticalSection
0x18001a700  mov     esi, [rbp+arg_0]
0x18001a703  cmp     [rbx+0F0h], r13b
0x18001a70a  jz      short loc_18001A73C
0x18001a70c  cmp     [rbx+0E0h], r13d
0x18001a713  jnz     loc_18001A7E9
0x18001a719  mov     rcx, [rbx+0D8h]; this
0x18001a720  call    ?SetEvent@details@wil@@YAXPEAX@Z; wil::details::SetEvent(void *)
0x18001a725  cmp     cs:byte_18010EC4D, 8
0x18001a72c  jb      loc_18001A7E9
0x18001a732  mov     edx, 4Ch ; 'L'
0x18001a737  jmp     loc_18001A5C3
0x18001a73c  lea     r9, [rdi+38h]; pKey
0x18001a740  xor     edx, edx; pState
0x18001a742  lea     rcx, [rbx+8]; pCallback
0x18001a746  mov     r8, 0FFFFFFFFFFFFFE0Ch; Timeout
0x18001a74d  call    cs:__imp_MFScheduleWorkItem
0x18001a753  mov     esi, eax
0x18001a755  test    eax, eax
0x18001a757  jns     short loc_18001A7A2
0x18001a759  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001a760  jb      short loc_18001A785
0x18001a762  mov     edx, 4Dh ; 'M'
0x18001a767  mov     dword ptr [rsp+58h+var_38], eax
0x18001a76b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a772  lea     r8, WPP_47229f29bd5f33e3e7f2581ae6977b5e_Traceguids
0x18001a779  mov     r9, rbx
0x18001a77c  mov     rcx, [rcx+10h]
0x18001a780  call    WPP_SF_qD
0x18001a785  mov     rcx, rdi; lpCriticalSection
0x18001a788  call    cs:__imp_LeaveCriticalSection
0x18001a78e  cmp     cs:byte_18010EC4D, 1
0x18001a795  jb      loc_18001A826
0x18001a79b  mov     edx, 4Fh ; 'O'
0x18001a7a0  jmp     short loc_18001A800
0x18001a7a2  inc     dword ptr [rbx+0E0h]
0x18001a7a8  mov     eax, [rbx+0E0h]
0x18001a7ae  cmp     cs:byte_18010EC4D, 8
0x18001a7b5  jb      short loc_18001A7E9
0x18001a7b7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a7be  lea     r8, WPP_47229f29bd5f33e3e7f2581ae6977b5e_Traceguids
0x18001a7c5  mov     [rsp+58h+var_30], eax
0x18001a7c9  mov     edx, 4Eh ; 'N'
0x18001a7ce  mov     rax, [rbx+0E8h]
0x18001a7d5  mov     r9, rbx
0x18001a7d8  mov     [rsp+58h+var_38], rax
0x18001a7dd  mov     rcx, [rcx+0D8h]
0x18001a7e4  call    WPP_SF_qqD
0x18001a7e9  mov     rcx, rdi; lpCriticalSection
0x18001a7ec  call    cs:__imp_LeaveCriticalSection
0x18001a7f2  cmp     cs:byte_18010EC4D, 8
0x18001a7f9  jb      short loc_18001A826
0x18001a7fb  mov     edx, 50h ; 'P'
0x18001a800  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a807  lea     r8, WPP_47229f29bd5f33e3e7f2581ae6977b5e_Traceguids
0x18001a80e  mov     [rsp+58h+var_30], r14d
0x18001a813  mov     r9, rbx
0x18001a816  mov     dword ptr [rsp+58h+var_38], esi
0x18001a81a  mov     rcx, [rcx+0D8h]
0x18001a821  call    WPP_SF_qDD
0x18001a826  lea     rcx, [rbp+var_20]; void *
0x18001a82a  call    ??1?$CTUnkArray@VSensorTransformContextStream@@@@QEAA@XZ; CTUnkArray<SensorTransformContextStream>::~CTUnkArray<SensorTransformContextStream>(void)
0x18001a82f  add     rsp, 58h
0x18001a833  pop     r15
0x18001a835  pop     r14
0x18001a837  pop     r13
0x18001a839  pop     r12
0x18001a83b  pop     rdi
0x18001a83c  pop     rsi
0x18001a83d  pop     rbx
0x18001a83e  pop     rbp
0x18001a83f  retn
```
