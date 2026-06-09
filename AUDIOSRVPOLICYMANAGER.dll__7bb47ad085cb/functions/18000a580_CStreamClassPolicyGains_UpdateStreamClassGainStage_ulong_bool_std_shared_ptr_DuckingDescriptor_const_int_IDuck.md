# CStreamClassPolicyGains::UpdateStreamClassGainStage(ulong,bool,std::shared_ptr<DuckingDescriptor> const &,int,IDuckingController *,int *)

- ea: `0x18000a580`
- end: `0x18000ab8b`
- name: `?UpdateStreamClassGainStage@CStreamClassPolicyGains@@QEAAJK_NAEBV?$shared_ptr@VDuckingDescriptor@@@std@@HPEAUIDuckingController@@PEAH@Z`
- size: `1547`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection, unsigned int, char, _QWORD *, int, __int64, __int64)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180009090`

## callees

- `0x1800088a0`
- `0x180008d20`
- `0x180008d80`
- `0x18000a384`
- `0x18000a580`
- `0x18000ab94`
- `0x18000ac00`
- `0x18000bbb0`
- `0x18001cd68`
- `0x18001cdd0`
- `0x18001f284`
- `0x180023e14`
- `0x180025b5c`
- `0x180031eb0`
- `0x180038f0c`
- `0x180044fdc`
- `0x18004c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a5a7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a5a7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a689`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a8fd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a963`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000aa71`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a689`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a8fd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a963`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000aa71`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a6e6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a6e6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a6d5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a6d5`

## string_xrefs

- `0x18000aaa5`: `Category = %d, DescriptorGain = %f`

## pseudocode

```c
__int64 __fastcall CStreamClassPolicyGains::UpdateStreamClassGainStage(
        LPCRITICAL_SECTION lpCriticalSection,
        unsigned int a2,
        char a3,
        _QWORD *a4,
        int a5,
        __int64 a6,
        __int64 a7)
{
  __int64 v9; // r14
  const char *v11; // r9
  int v12; // r12d
  int *v13; // r13
  __int64 v14; // rax
  char *v15; // rax
  char *v16; // rsi
  char *v17; // rdi
  _QWORD *v18; // rsi
  _QWORD *v19; // rdi
  __int64 result; // rax
  HANDLE ProcessHeap; // rax
  _DWORD *v22; // rax
  _DWORD *v23; // r14
  int v24; // r12d
  __int64 v25; // rcx
  __int64 v26; // rax
  CPBMStreamClassVolumeGainStage *v27; // rax
  CPBMStreamClassVolumeGainStage *v28; // rax
  CPBMStreamClassVolumeGainStage *v29; // rdi
  std::_Ref_count_base *v30; // rcx
  signed __int32 i; // eax
  volatile int *v32; // rdx
  _QWORD *v33; // r8
  char **j; // rax
  __int64 v35; // rax
  int v36; // edi
  char *v37; // rcx
  int v38; // [rsp+20h] [rbp-98h]
  char *v39; // [rsp+28h] [rbp-90h]
  __int64 *v40; // [rsp+50h] [rbp-68h] BYREF
  std::_Ref_count_base *v41; // [rsp+58h] [rbp-60h]
  char *v42; // [rsp+60h] [rbp-58h]
  _QWORD *v43; // [rsp+68h] [rbp-50h] BYREF
  _QWORD *v44; // [rsp+70h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]
  __int128 *v46; // [rsp+C0h] [rbp+8h] BYREF

  v9 = a2;
  EnterCriticalSection(lpCriticalSection);
  v12 = 0;
  v13 = (int *)a7;
  *(_DWORD *)a7 = 0;
  v14 = 232;
  if ( !a3 )
    v14 = 40;
  try
  {
    v15 = (char *)lpCriticalSection + v14;
    v16 = &v15[8 * v9];
    if ( a6 )
    {
      if ( a5 )
      {
        a7 = 0;
        v40 = &a6;
        v41 = (std::_Ref_count_base *)&a7;
        v42 = &v15[8 * v9];
        v43 = 0;
        v44 = &v43;
        v17 = *(char **)v16;
        while ( v17 )
        {
          if ( (unsigned __int8)lambda_d29f8cb166960269749b8c0ea722c7d7_::operator()(&v40, v17 + 8) )
          {
            v37 = *(char **)v16;
            v17 = **(char ***)v16;
            *(_QWORD *)v37 = 0;
            *(_QWORD *)v16 = v17;
            *v44 = v37;
            v44 = v37;
          }
          else
          {
            v16 = v17;
            v17 = *(char **)v17;
          }
        }
        v18 = v43;
        if ( v43 )
        {
          do
          {
            v19 = (_QWORD *)*v18;
            wil::com_ptr_t<CPBMStreamClassVolumeGainStage,wil::err_returncode_policy>::~com_ptr_t<CPBMStreamClassVolumeGainStage,wil::err_returncode_policy>(v18 + 1);
            std::_Deallocate<16>(v18, 16);
            v18 = v19;
          }
          while ( v19 );
        }
        if ( a7 )
        {
          if ( (***(float (__fastcall ****)(_QWORD))(a7 + 56))(*(_QWORD *)(a7 + 56)) != 0.0 )
            v12 = 1;
          *v13 = v12;
        }
        if ( a7 )
          Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,CGainStage>::Release(a7);
        goto LABEL_12;
      }
      ProcessHeap = GetProcessHeap();
      v22 = HeapAlloc(ProcessHeap, 0, 0x30u);
      v23 = v22;
      if ( v22 )
      {
        v24 = 1;
        v22[2] = 1;
        v22[3] = 1;
        *(_QWORD *)v22 = &std::_Ref_count_obj2<DeactivatableDuckingDescriptor>::`vftable';
        v25 = a6;
        *((_QWORD *)v22 + 2) = &DeactivatableDuckingDescriptor::`vftable';
        *((_QWORD *)v22 + 3) = 0;
        *((_QWORD *)v22 + 4) = 0;
        v26 = a4[1];
        if ( v26 )
          _InterlockedIncrement((volatile signed __int32 *)(v26 + 8));
        *((_QWORD *)v23 + 3) = *a4;
        *((_QWORD *)v23 + 4) = a4[1];
        *((_QWORD *)v23 + 5) = v25;
        if ( v25 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 8LL))(v25);
      }
      else
      {
        v23 = 0;
        v24 = 1;
      }
      v40 = (__int64 *)(v23 + 4);
      v41 = (std::_Ref_count_base *)v23;
      if ( v23 == (_DWORD *)-16LL )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5C,
          (unsigned int)"avcore\\audiocore\\server\\audiosrv\\streamclasspolicygains\\streamclasspolicygains.cpp",
          (const char *)0x8007000ELL,
          v38);
        std::_Ref_count_base::_Decref((std::_Ref_count_base *)0xFFFFFFFFFFFFFFF0LL);
        if ( lpCriticalSection )
          LeaveCriticalSection(lpCriticalSection);
        result = 2147942414LL;
      }
      else
      {
        if ( v23 )
          _InterlockedIncrement(v23 + 2);
        v46 = 0;
        v27 = (CPBMStreamClassVolumeGainStage *)operator new[](0x48u, (const struct std::nothrow_t *)&std::nothrow);
        if ( v27 )
        {
          v28 = CPBMStreamClassVolumeGainStage::CPBMStreamClassVolumeGainStage(v27);
          v29 = v28;
          if ( v23 )
            _InterlockedIncrement(v23 + 2);
          *((_QWORD *)v28 + 7) = v23 + 4;
          v30 = (std::_Ref_count_base *)*((_QWORD *)v28 + 8);
          *((_QWORD *)v28 + 8) = v23;
          if ( v30 )
            std::_Ref_count_base::_Decref(v30);
          *((_OWORD *)v29 + 1) = StreamClassVolumePolicyGuid;
          *((_BYTE *)v29 + 32) = 0;
          *((_QWORD *)v29 + 5) = 0;
          if ( v23 )
            std::_Ref_count_base::_Decref((std::_Ref_count_base *)v23);
          for ( i = *((_DWORD *)v29 + 13); i != 0x7FFFFFFF; i = *((_DWORD *)v29 + 13) )
          {
            if ( i == _InterlockedCompareExchange((volatile signed __int32 *)v29 + 13, i + 1, i) )
              break;
          }
          v46 = (__int128 *)v29;
          Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,CGainStage>::Release(v29);
          v33 = operator new(0x10u);
          v33[1] = v29;
          if ( v29 )
            Microsoft::WRL::Details::SafeUnknownIncrementReference(
              (CPBMStreamClassVolumeGainStage *)((char *)v29 + 52),
              v32);
          *v33 = *(_QWORD *)v16;
          *(_QWORD *)v16 = v33;
          if ( !(*(unsigned __int8 (__fastcall **)(_QWORD))(**((_QWORD **)v23 + 5) + 24LL))(*((_QWORD *)v23 + 5))
            || *(float *)(*((_QWORD *)v23 + 3) + 8LL) == 0.0 )
          {
            v24 = 0;
          }
          *(_DWORD *)a7 = v24;
          if ( v29 )
            Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,CGainStage>::Release(v29);
          if ( v23 )
            std::_Ref_count_base::_Decref((std::_Ref_count_base *)v23);
          goto LABEL_12;
        }
        if ( v23 )
          std::_Ref_count_base::_Decref((std::_Ref_count_base *)v23);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5F,
          (unsigned int)"avcore\\audiocore\\server\\audiosrv\\streamclasspolicygains\\streamclasspolicygains.cpp",
          (const char *)0x8007000ELL,
          v38);
        wil::com_ptr_t<CPBMStreamClassVolumeGainStage,wil::err_returncode_policy>::~com_ptr_t<CPBMStreamClassVolumeGainStage,wil::err_returncode_policy>(&v46);
        if ( v23 )
          std::_Ref_count_base::_Decref((std::_Ref_count_base *)v23);
        if ( lpCriticalSection )
          LeaveCriticalSection(lpCriticalSection);
        result = 2147942414LL;
      }
    }
    else
    {
      for ( j = *(char ***)v16; j && *a4 != *((_QWORD *)j[1] + 7); j = (char **)*j )
        ;
      if ( a5 )
      {
        if ( j )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)j[1] + 9, 0xFFFFFFFF) == 1 )
          {
            std::forward_list_wil::com_ptr_t_CPBMStreamClassVolumeGainStage_wil::err_returncode_policy__std::allocator_wil::com_ptr_t_CPBMStreamClassVolumeGainStage_wil::err_returncode_policy_____::remove_if__lambda_165499ea39685c5d8e5f507cce42e944___(
              v16,
              a4);
            if ( *(float *)(*a4 + 8LL) != 0.0 )
              v12 = 1;
            *v13 = v12;
          }
        }
        else
        {
          LODWORD(v39) = v9;
          wil::details::in1diag3::Log_HrMsg(
            retaddr,
            (void *)0xA7,
            (unsigned int)"avcore\\audiocore\\server\\audiosrv\\streamclasspolicygains\\streamclasspolicygains.cpp",
            (const char *)0x8000FFFFLL,
            (int)"Category = %d, DescriptorGain = %f",
            v39,
            *(float *)(*a4 + 8LL));
        }
        goto LABEL_12;
      }
      if ( j )
      {
        _InterlockedIncrement((volatile signed __int32 *)j[1] + 9);
LABEL_12:
        if ( lpCriticalSection )
          LeaveCriticalSection(lpCriticalSection);
        return 0;
      }
      v35 = std::static_pointer_cast<IDuckingDescriptor,DeactivatableDuckingDescriptor>(&v40, a4);
      v46 = &StreamClassVolumePolicyGuid;
      a7 = 0;
      v36 = Microsoft::WRL::Details::MakeAndInitialize<CPBMStreamClassVolumeGainStage,CPBMStreamClassVolumeGainStage,_GUID const *,std::shared_ptr<IDuckingDescriptor>>(
              &a7,
              &v46,
              v35);
      if ( v41 )
        std::_Ref_count_base::_Decref(v41);
      if ( v36 >= 0 )
      {
        std::forward_list<wil::com_ptr_t<CPBMStreamClassVolumeGainStage,wil::err_returncode_policy>>::push_front(
          v16,
          &a7);
        if ( *(float *)(*a4 + 8LL) != 0.0 )
          v12 = 1;
        *v13 = v12;
        wil::com_ptr_t<CPBMStreamClassVolumeGainStage,wil::err_returncode_policy>::~com_ptr_t<CPBMStreamClassVolumeGainStage,wil::err_returncode_policy>(&a7);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8F,
        (unsigned int)"avcore\\audiocore\\server\\audiosrv\\streamclasspolicygains\\streamclasspolicygains.cpp",
        (const char *)(unsigned int)v36,
        v38);
      wil::com_ptr_t<CPBMStreamClassVolumeGainStage,wil::err_returncode_policy>::~com_ptr_t<CPBMStreamClassVolumeGainStage,wil::err_returncode_policy>(&a7);
      if ( lpCriticalSection )
        LeaveCriticalSection(lpCriticalSection);
      result = (unsigned int)v36;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xAE,
                           (unsigned int)"avcore\\audiocore\\server\\audiosrv\\streamclasspolicygains\\streamclasspolicygains.cpp",
                           v11);
  }
  return result;
}

```

## disassembly

```asm
0x18000a580  mov     [rsp+arg_8], rbx
0x18000a585  mov     [rsp+arg_18], rsi
0x18000a58a  push    rdi
0x18000a58b  push    r12
0x18000a58d  push    r13
0x18000a58f  push    r14
0x18000a591  push    r15
0x18000a593  sub     rsp, 90h
0x18000a59a  mov     r15, r9
0x18000a59d  movzx   edi, r8b
0x18000a5a1  mov     r14d, edx
0x18000a5a4  mov     rbx, rcx
0x18000a5a7  call    cs:__imp_EnterCriticalSection
0x18000a5ad  mov     [rsp+0B8h+var_78], rbx
0x18000a5b2  xor     r12d, r12d
0x18000a5b5  mov     r13, [rsp+0B8h+arg_30]
0x18000a5bd  mov     [r13+0], r12d
0x18000a5c1  mov     eax, 0E8h
0x18000a5c6  mov     ecx, 28h ; '('
0x18000a5cb  test    dil, dil
0x18000a5ce  cmovz   eax, ecx
0x18000a5d1  add     rax, rbx
0x18000a5d4  lea     rsi, [rax+r14*8]
0x18000a5d8  cmp     [rsp+0B8h+arg_28], r12
0x18000a5e0  jz      loc_18000AB21
0x18000a5e6  cmp     [rsp+0B8h+arg_20], r12d
0x18000a5ee  jz      loc_18000A6D5
0x18000a5f4  mov     [rsp+0B8h+arg_30], r12
0x18000a5fc  lea     rax, [rsp+0B8h+arg_28]
0x18000a604  mov     [rsp+0B8h+var_68], rax
0x18000a609  lea     rax, [rsp+0B8h+arg_30]
0x18000a611  mov     [rsp+0B8h+var_60], rax
0x18000a616  mov     [rsp+0B8h+var_58], rsi
0x18000a61b  mov     [rsp+0B8h+var_50], r12
0x18000a620  lea     rax, [rsp+0B8h+var_50]
0x18000a625  mov     [rsp+0B8h+var_48], rax
0x18000a62a  mov     rdi, [rsi]
0x18000a62d  test    rdi, rdi
0x18000a630  jnz     loc_18000AADB
0x18000a636  mov     rsi, [rsp+0B8h+var_50]
0x18000a63b  test    rsi, rsi
0x18000a63e  jz      short loc_18000A661
0x18000a640  mov     rdi, [rsi]
0x18000a643  lea     rcx, [rsi+8]
0x18000a647  call    ??1?$com_ptr_t@VCPBMStreamClassVolumeGainStage@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CPBMStreamClassVolumeGainStage,wil::err_returncode_policy>::~com_ptr_t<CPBMStreamClassVolumeGainStage,wil::err_returncode_policy>(void)
0x18000a64c  mov     edx, 10h
0x18000a651  mov     rcx, rsi
0x18000a654  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000a659  mov     rsi, rdi
0x18000a65c  test    rdi, rdi
0x18000a65f  jnz     short loc_18000A640
0x18000a661  mov     rcx, [rsp+0B8h+arg_30]
0x18000a669  test    rcx, rcx
0x18000a66c  jnz     short loc_18000A6AE
0x18000a66e  mov     rcx, [rsp+0B8h+arg_30]
0x18000a676  test    rcx, rcx
0x18000a679  jz      short loc_18000A681
0x18000a67b  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@VCGainStage@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,CGainStage>::Release(void)
0x18000a680  nop
0x18000a681  test    rbx, rbx
0x18000a684  jz      short loc_18000A68F
0x18000a686  mov     rcx, rbx; lpCriticalSection
0x18000a689  call    cs:__imp_LeaveCriticalSection
0x18000a68f  xor     eax, eax
0x18000a691  lea     r11, [rsp+0B8h+var_28]
0x18000a699  mov     rbx, [r11+38h]
0x18000a69d  mov     rsi, [r11+48h]
0x18000a6a1  mov     rsp, r11
0x18000a6a4  pop     r15
0x18000a6a6  pop     r14
0x18000a6a8  pop     r13
0x18000a6aa  pop     r12
0x18000a6ac  pop     rdi
0x18000a6ad  retn
0x18000a6ae  mov     rcx, [rcx+38h]
0x18000a6b2  mov     rax, [rcx]
0x18000a6b5  mov     rax, [rax]
0x18000a6b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a6bd  xorps   xmm1, xmm1
0x18000a6c0  ucomiss xmm0, xmm1
0x18000a6c3  jp      loc_18000AB16
0x18000a6c9  jnz     loc_18000AB16
0x18000a6cf  mov     [r13+0], r12d
0x18000a6d3  jmp     short loc_18000A66E
0x18000a6d5  call    cs:__imp_GetProcessHeap
0x18000a6db  mov     rcx, rax; hHeap
0x18000a6de  xor     edx, edx; dwFlags
0x18000a6e0  mov     r8d, 30h ; '0'; dwBytes
0x18000a6e6  call    cs:__imp_HeapAlloc
0x18000a6ec  mov     r14, rax
0x18000a6ef  test    rax, rax
0x18000a6f2  jz      loc_18000A90A
0x18000a6f8  mov     r12d, 1
0x18000a6fe  mov     [rax+8], r12d
0x18000a702  mov     [rax+0Ch], r12d
0x18000a706  lea     rax, ??_7?$_Ref_count_obj2@VDeactivatableDuckingDescriptor@@@std@@6B@; const std::_Ref_count_obj2<DeactivatableDuckingDescriptor>::`vftable'
0x18000a70d  mov     [r14], rax
0x18000a710  mov     rcx, [rsp+0B8h+arg_28]
0x18000a718  lea     rax, ??_7DeactivatableDuckingDescriptor@@6B@; const DeactivatableDuckingDescriptor::`vftable'
0x18000a71f  mov     [r14+10h], rax
0x18000a723  mov     qword ptr [r14+18h], 0
0x18000a72b  mov     qword ptr [r14+20h], 0
0x18000a733  mov     rax, [r15+8]
0x18000a737  test    rax, rax
0x18000a73a  jz      short loc_18000A740
0x18000a73c  lock inc dword ptr [rax+8]
0x18000a740  mov     rax, [r15]
0x18000a743  mov     [r14+18h], rax
0x18000a747  mov     rax, [r15+8]
0x18000a74b  mov     [r14+20h], rax
0x18000a74f  mov     [r14+28h], rcx
0x18000a753  test    rcx, rcx
0x18000a756  jz      short loc_18000A765
0x18000a758  mov     rax, [rcx]
0x18000a75b  mov     rax, [rax+8]
0x18000a75f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a764  nop
0x18000a765  lea     r13, [r14+10h]
0x18000a769  mov     [rsp+0B8h+var_68], r13
0x18000a76e  mov     [rsp+0B8h+var_60], r14
0x18000a773  test    r13, r13
0x18000a776  jz      loc_18000A8C5
0x18000a77c  test    r14, r14
0x18000a77f  jz      short loc_18000A786
0x18000a781  lock inc dword ptr [r14+8]
0x18000a786  mov     [rsp+0B8h+arg_0], 0
0x18000a792  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000a799  mov     ecx, 48h ; 'H'; unsigned __int64
0x18000a79e  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000a7a3  test    rax, rax
0x18000a7a6  jz      loc_18000A918
0x18000a7ac  mov     rcx, rax; this
0x18000a7af  call    ??0CPBMStreamClassVolumeGainStage@@QEAA@XZ; CPBMStreamClassVolumeGainStage::CPBMStreamClassVolumeGainStage(void)
0x18000a7b4  mov     rdi, rax
0x18000a7b7  test    r14, r14
0x18000a7ba  jz      short loc_18000A7C1
0x18000a7bc  lock inc dword ptr [r14+8]
0x18000a7c1  mov     [rax+38h], r13
0x18000a7c5  mov     rcx, [rax+40h]; this
0x18000a7c9  mov     [rax+40h], r14
0x18000a7cd  test    rcx, rcx
0x18000a7d0  jnz     loc_18000A89B
0x18000a7d6  movups  xmm0, cs:StreamClassVolumePolicyGuid
0x18000a7dd  movups  xmmword ptr [rdi+10h], xmm0
0x18000a7e1  mov     byte ptr [rdi+20h], 0
0x18000a7e5  mov     qword ptr [rdi+28h], 0
0x18000a7ed  test    r14, r14
0x18000a7f0  jnz     loc_18000A8A5
0x18000a7f6  mov     eax, [rdi+34h]
0x18000a7f9  cmp     eax, 7FFFFFFFh
0x18000a7fe  jz      short loc_18000A80E
0x18000a800  lea     ecx, [rax+1]
0x18000a803  lock cmpxchg [rdi+34h], ecx
0x18000a808  jnz     loc_18000A8B2
0x18000a80e  mov     [rsp+0B8h+arg_0], rdi
0x18000a816  mov     rcx, rdi
0x18000a819  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@VCGainStage@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,CGainStage>::Release(void)
0x18000a81e  nop
0x18000a81f  mov     ecx, 10h; unsigned __int64
0x18000a824  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a829  mov     r8, rax
0x18000a82c  mov     [rax+8], rdi
0x18000a830  test    rdi, rdi
0x18000a833  jnz     loc_18000AACD
0x18000a839  mov     rcx, [rsi]
0x18000a83c  mov     [r8], rcx
0x18000a83f  mov     [rsi], r8
0x18000a842  mov     rcx, [r13+18h]
0x18000a846  mov     rax, [rcx]
0x18000a849  mov     rax, [rax+18h]
0x18000a84d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a852  test    al, al
0x18000a854  jz      short loc_18000A869
0x18000a856  mov     rax, [r13+8]
0x18000a85a  movss   xmm1, dword ptr [rax+8]
0x18000a85f  xorps   xmm0, xmm0
0x18000a862  ucomiss xmm1, xmm0
0x18000a865  jp      short loc_18000A86C
0x18000a867  jnz     short loc_18000A86C
0x18000a869  xor     r12d, r12d
0x18000a86c  mov     rax, [rsp+0B8h+arg_30]
0x18000a874  mov     [rax], r12d
0x18000a877  test    rdi, rdi
0x18000a87a  jz      short loc_18000A885
0x18000a87c  mov     rcx, rdi
0x18000a87f  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@VCGainStage@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,CGainStage>::Release(void)
0x18000a884  nop
0x18000a885  test    r14, r14
0x18000a888  jz      loc_18000A681
0x18000a88e  mov     rcx, r14; this
0x18000a891  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000a896  jmp     loc_18000A681
0x18000a89b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000a8a0  jmp     loc_18000A7D6
0x18000a8a5  mov     rcx, r14; this
0x18000a8a8  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000a8ad  jmp     loc_18000A7F6
0x18000a8b2  mov     eax, [rdi+34h]
0x18000a8b5  cmp     eax, 7FFFFFFFh
0x18000a8ba  jnz     loc_18000A800
0x18000a8c0  jmp     loc_18000A80E
0x18000a8c5  mov     rcx, [rsp+0B8h]; this
0x18000a8cd  mov     edi, 8007000Eh
0x18000a8d2  mov     r9d, edi; char *
0x18000a8d5  lea     r8, aAvcoreAudiocor_1; "avcore\\audiocore\\server\\audiosrv\\st"...
0x18000a8dc  mov     edx, 5Ch ; '\'; void *
0x18000a8e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a8e6  nop
0x18000a8e7  test    r14, r14
0x18000a8ea  jz      short loc_18000A8F5
0x18000a8ec  mov     rcx, r14; this
0x18000a8ef  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000a8f4  nop
0x18000a8f5  test    rbx, rbx
0x18000a8f8  jz      short loc_18000A903
0x18000a8fa  mov     rcx, rbx; lpCriticalSection
0x18000a8fd  call    cs:__imp_LeaveCriticalSection
0x18000a903  mov     eax, edi
0x18000a905  jmp     loc_18000A691
0x18000a90a  mov     r14, r12
0x18000a90d  mov     r12d, 1
0x18000a913  jmp     loc_18000A765
0x18000a918  mov     edi, 8007000Eh
0x18000a91d  test    r14, r14
0x18000a920  jnz     short loc_18000A98F
0x18000a922  mov     rcx, [rsp+0B8h]; this
0x18000a92a  mov     r9d, edi; char *
0x18000a92d  lea     r8, aAvcoreAudiocor_1; "avcore\\audiocore\\server\\audiosrv\\st"...
0x18000a934  mov     edx, 5Fh ; '_'; void *
0x18000a939  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a93e  nop
0x18000a93f  lea     rcx, [rsp+0B8h+arg_0]
0x18000a947  call    ??1?$com_ptr_t@VCPBMStreamClassVolumeGainStage@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CPBMStreamClassVolumeGainStage,wil::err_returncode_policy>::~com_ptr_t<CPBMStreamClassVolumeGainStage,wil::err_returncode_policy>(void)
0x18000a94c  nop
0x18000a94d  test    r14, r14
0x18000a950  jz      short loc_18000A95B
0x18000a952  mov     rcx, r14; this
0x18000a955  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000a95a  nop
0x18000a95b  test    rbx, rbx
0x18000a95e  jz      short loc_18000A969
0x18000a960  mov     rcx, rbx; lpCriticalSection
0x18000a963  call    cs:__imp_LeaveCriticalSection
0x18000a969  mov     eax, edi
0x18000a96b  jmp     loc_18000A691
0x18000a970  test    rax, rax
0x18000a973  jz      loc_18000AB29
0x18000a979  mov     rcx, [rax+8]
0x18000a97d  mov     rdx, [rcx+38h]
0x18000a981  cmp     [r15], rdx
0x18000a984  jz      loc_18000AB29
0x18000a98a  mov     rax, [rax]
0x18000a98d  jmp     short loc_18000A970
0x18000a98f  mov     rcx, r14; this
0x18000a992  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000a997  jmp     short loc_18000A922
0x18000a999  test    rax, rax
0x18000a99c  jnz     loc_18000AA31
0x18000a9a2  mov     rdx, r15
0x18000a9a5  lea     rcx, [rsp+0B8h+var_68]
0x18000a9aa  call    ??$static_pointer_cast@UIDuckingDescriptor@@VDeactivatableDuckingDescriptor@@@std@@YA?AV?$shared_ptr@UIDuckingDescriptor@@@0@AEBV?$shared_ptr@VDeactivatableDuckingDescriptor@@@0@@Z; std::static_pointer_cast<IDuckingDescriptor,DeactivatableDuckingDescriptor>(std::shared_ptr<DeactivatableDuckingDescriptor> const &)
0x18000a9af  lea     rcx, StreamClassVolumePolicyGuid
0x18000a9b6  mov     [rsp+0B8h+arg_0], rcx
0x18000a9be  mov     [rsp+0B8h+arg_30], r12
0x18000a9c6  mov     r8, rax
0x18000a9c9  lea     rdx, [rsp+0B8h+arg_0]
0x18000a9d1  lea     rcx, [rsp+0B8h+arg_30]
0x18000a9d9  call    ??$MakeAndInitialize@VCPBMStreamClassVolumeGainStage@@V1@PEBU_GUID@@V?$shared_ptr@UIDuckingDescriptor@@@std@@@Details@WRL@Microsoft@@YAJPEAPEAVCPBMStreamClassVolumeGainStage@@$$QEAPEBU_GUID@@$$QEAV?$shared_ptr@UIDuckingDescriptor@@@std@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CPBMStreamClassVolumeGainStage,CPBMStreamClassVolumeGainStage,_GUID const *,std::shared_ptr<IDuckingDescriptor>>(CPBMStreamClassVolumeGainStage * *,_GUID const * &&,std::shared_ptr<IDuckingDescriptor> &&)
0x18000a9de  mov     edi, eax
0x18000a9e0  mov     rcx, [rsp+0B8h+var_60]; this
0x18000a9e5  test    rcx, rcx
0x18000a9e8  jz      short loc_18000A9EF
0x18000a9ea  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000a9ef  test    edi, edi
0x18000a9f1  js      short loc_18000AA3E
0x18000a9f3  lea     rdx, [rsp+0B8h+arg_30]
0x18000a9fb  mov     rcx, rsi
0x18000a9fe  call    ?push_front@?$forward_list@V?$com_ptr_t@VCPBMStreamClassVolumeGainStage@@Uerr_returncode_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@VCPBMStreamClassVolumeGainStage@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@QEAAXAEBV?$com_ptr_t@VCPBMStreamClassVolumeGainStage@@Uerr_returncode_policy@wil@@@wil@@@Z; std::forward_list<wil::com_ptr_t<CPBMStreamClassVolumeGainStage,wil::err_returncode_policy>>::push_front(wil::com_ptr_t<CPBMStreamClassVolumeGainStage,wil::err_returncode_policy> const &)
0x18000aa03  mov     rax, [r15]
0x18000aa06  movss   xmm1, dword ptr [rax+8]
0x18000aa0b  xorps   xmm0, xmm0
0x18000aa0e  ucomiss xmm1, xmm0
0x18000aa11  jp      short loc_18000AA15
0x18000aa13  jz      short loc_18000AA1B
0x18000aa15  mov     r12d, 1
0x18000aa1b  mov     [r13+0], r12d
0x18000aa1f  lea     rcx, [rsp+0B8h+arg_30]
0x18000aa27  call    ??1?$com_ptr_t@VCPBMStreamClassVolumeGainStage@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CPBMStreamClassVolumeGainStage,wil::err_returncode_policy>::~com_ptr_t<CPBMStreamClassVolumeGainStage,wil::err_returncode_policy>(void)
0x18000aa2c  jmp     loc_18000A681
0x18000aa31  mov     rax, [rax+8]
0x18000aa35  lock inc dword ptr [rax+24h]
0x18000aa39  jmp     loc_18000A681
0x18000aa3e  mov     rcx, [rsp+0B8h]; this
0x18000aa46  mov     r9d, edi; char *
0x18000aa49  lea     r8, aAvcoreAudiocor_1; "avcore\\audiocore\\server\\audiosrv\\st"...
0x18000aa50  mov     edx, 8Fh; void *
0x18000aa55  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000aa5a  nop
0x18000aa5b  lea     rcx, [rsp+0B8h+arg_30]
0x18000aa63  call    ??1?$com_ptr_t@VCPBMStreamClassVolumeGainStage@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CPBMStreamClassVolumeGainStage,wil::err_returncode_policy>::~com_ptr_t<CPBMStreamClassVolumeGainStage,wil::err_returncode_policy>(void)
  ... truncated ...
```
