# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,Windows::Foundation::IAsyncOperation<bool>,Windows::Internal::IAsyncOperationLocal,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncDeferral>,Microsoft::WRL::CloakedIid<Windows::Internal::IComPoolTask>,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncFireCompletion>>::QueryInterface(_GUID const &,void * *)

- ea: `0x18000de30`
- end: `0x18000df88`
- name: `?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@V?$AsyncBaseWithProgressFTM@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@UINilDelegate@Internal@3@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@U?$IAsyncOperation@_N@Foundation@6@UIAsyncOperationLocal@56@U?$CloakedIid@UIAsyncDeferral@Internal@Windows@@@23@U?$CloakedIid@UIComPoolTask@Internal@Windows@@@23@U?$CloakedIid@UIAsyncFireCompletion@Internal@Windows@@@23@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `344`
- prototype: ``
- caller_count: `7`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000df90`
- `0x18000dfa0`
- `0x18000dfc0`
- `0x18000dfe0`
- `0x18000e000`
- `0x18000e020`
- `0x18000e040`

## callees

- `0x1800085d4`
- `0x18000de30`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,Windows::Foundation::IAsyncOperation<bool>,Windows::Internal::IAsyncOperationLocal,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncDeferral>,Microsoft::WRL::CloakedIid<Windows::Internal::IComPoolTask>,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncFireCompletion>>::QueryInterface(
        __int64 a1,
        _DWORD *a2,
        _QWORD *a3)
{
  int v3; // eax
  int CanCastTo; // ebx
  int v5; // eax

  *a3 = 0;
  if ( !*a2 )
  {
    if ( a2[1] != *(_DWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data2
      || a2[2] != *(_DWORD *)GUID_00000000_0000_0000_c000_000000000046.Data4 )
    {
      goto LABEL_15;
    }
    v3 = *(_DWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data4[4];
LABEL_9:
    if ( a2[3] == v3 )
    {
      *a3 = a1;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
      return 0;
    }
    goto LABEL_15;
  }
  if ( *a2 == -1350114592 )
  {
    if ( a2[1] != *(_DWORD *)&GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data2
      || a2[2] != *(_DWORD *)GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4 )
    {
      goto LABEL_15;
    }
    v3 = *(_DWORD *)&GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4[4];
    goto LABEL_9;
  }
  if ( *a2 == 54
    && a2[1] == *(_DWORD *)&GUID_00000036_0000_0000_c000_000000000046.Data2
    && a2[2] == *(_DWORD *)GUID_00000036_0000_0000_c000_000000000046.Data4
    && a2[3] == *(_DWORD *)&GUID_00000036_0000_0000_c000_000000000046.Data4[4] )
  {
LABEL_31:
    *a3 = a1;
    CanCastTo = 0;
    goto LABEL_33;
  }
LABEL_15:
  if ( *a2 == -1796592748 )
  {
    if ( a2[1] != *(_DWORD *)&GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data2
      || a2[2] != *(_DWORD *)GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4 )
    {
      goto LABEL_25;
    }
    v5 = *(_DWORD *)&GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4[4];
  }
  else
  {
    if ( *a2 != 3
      || a2[1] != *(_DWORD *)&GUID_00000003_0000_0000_c000_000000000046.Data2
      || a2[2] != *(_DWORD *)GUID_00000003_0000_0000_c000_000000000046.Data4 )
    {
      goto LABEL_25;
    }
    v5 = *(_DWORD *)&GUID_00000003_0000_0000_c000_000000000046.Data4[4];
  }
  if ( a2[3] == v5 )
  {
    *a3 = a1 + 80;
    CanCastTo = 0;
    goto LABEL_26;
  }
LABEL_25:
  CanCastTo = -2147467262;
LABEL_26:
  if ( CanCastTo != -2147467262 )
    goto LABEL_33;
  a1 += 168;
  if ( *a2 == 56
    && a2[1] == *(_DWORD *)&GUID_00000038_0000_0000_c000_000000000046.Data2
    && a2[2] == *(_DWORD *)GUID_00000038_0000_0000_c000_000000000046.Data4
    && a2[3] == *(_DWORD *)&GUID_00000038_0000_0000_c000_000000000046.Data4[4] )
  {
    goto LABEL_31;
  }
  CanCastTo = Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::Foundation::IAsyncOperation<bool>,Windows::Internal::IAsyncOperationLocal,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncDeferral>,Microsoft::WRL::CloakedIid<Windows::Internal::IComPoolTask>,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncFireCompletion>>::CanCastTo(a1 + 8);
LABEL_33:
  if ( CanCastTo >= 0 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a3 + 8LL))(*a3);
  return (unsigned int)CanCastTo;
}

```

## disassembly

```asm
0x18000de30  push    rbx
0x18000de32  sub     rsp, 20h
0x18000de36  mov     qword ptr [r8], 0
0x18000de3d  cmp     dword ptr [rdx], 0
0x18000de40  jnz     short loc_18000DE60
0x18000de42  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data2
0x18000de48  cmp     [rdx+4], eax
0x18000de4b  jnz     short loc_18000DEC9
0x18000de4d  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x18000de53  cmp     [rdx+8], eax
0x18000de56  jnz     short loc_18000DEC9
0x18000de58  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4+4
0x18000de5e  jmp     short loc_18000DE84
0x18000de60  cmp     dword ptr [rdx], 0AF86E2E0h
0x18000de66  jnz     short loc_18000DE9F
0x18000de68  mov     eax, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data2
0x18000de6e  cmp     [rdx+4], eax
0x18000de71  jnz     short loc_18000DEC9
0x18000de73  mov     eax, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4
0x18000de79  cmp     [rdx+8], eax
0x18000de7c  jnz     short loc_18000DEC9
0x18000de7e  mov     eax, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4+4
0x18000de84  cmp     [rdx+0Ch], eax
0x18000de87  jnz     short loc_18000DEC9
0x18000de89  mov     [r8], rcx
0x18000de8c  mov     rax, [rcx]
0x18000de8f  mov     rax, [rax+8]
0x18000de93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de98  xor     ebx, ebx
0x18000de9a  jmp     loc_18000DF80
0x18000de9f  cmp     dword ptr [rdx], 36h ; '6'
0x18000dea2  jnz     short loc_18000DEC9
0x18000dea4  mov     eax, dword ptr cs:_GUID_00000036_0000_0000_c000_000000000046.Data2
0x18000deaa  cmp     [rdx+4], eax
0x18000dead  jnz     short loc_18000DEC9
0x18000deaf  mov     eax, dword ptr cs:_GUID_00000036_0000_0000_c000_000000000046.Data4
0x18000deb5  cmp     [rdx+8], eax
0x18000deb8  jnz     short loc_18000DEC9
0x18000deba  mov     eax, dword ptr cs:_GUID_00000036_0000_0000_c000_000000000046.Data4+4
0x18000dec0  cmp     [rdx+0Ch], eax
0x18000dec3  jz      loc_18000DF5B
0x18000dec9  cmp     dword ptr [rdx], 94EA2B94h
0x18000decf  lea     r9, [rcx+50h]
0x18000ded3  mov     r10d, 80004002h
0x18000ded9  jnz     short loc_18000DEF9
0x18000dedb  mov     eax, dword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data2
0x18000dee1  cmp     [rdx+4], eax
0x18000dee4  jnz     short loc_18000DF26
0x18000dee6  mov     eax, dword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4
0x18000deec  cmp     [rdx+8], eax
0x18000deef  jnz     short loc_18000DF26
0x18000def1  mov     eax, dword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4+4
0x18000def7  jmp     short loc_18000DF1A
0x18000def9  cmp     dword ptr [rdx], 3
0x18000defc  jnz     short loc_18000DF26
0x18000defe  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data2
0x18000df04  cmp     [rdx+4], eax
0x18000df07  jnz     short loc_18000DF26
0x18000df09  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data4
0x18000df0f  cmp     [rdx+8], eax
0x18000df12  jnz     short loc_18000DF26
0x18000df14  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data4+4
0x18000df1a  cmp     [rdx+0Ch], eax
0x18000df1d  jnz     short loc_18000DF26
0x18000df1f  mov     [r8], r9
0x18000df22  xor     ebx, ebx
0x18000df24  jmp     short loc_18000DF29
0x18000df26  mov     ebx, r10d
0x18000df29  cmp     ebx, r10d
0x18000df2c  jnz     short loc_18000DF6D
0x18000df2e  add     rcx, 0A8h
0x18000df35  cmp     dword ptr [rdx], 38h ; '8'
0x18000df38  jnz     short loc_18000DF62
0x18000df3a  mov     eax, dword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data2
0x18000df40  cmp     [rdx+4], eax
0x18000df43  jnz     short loc_18000DF62
0x18000df45  mov     eax, dword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data4
0x18000df4b  cmp     [rdx+8], eax
0x18000df4e  jnz     short loc_18000DF62
0x18000df50  mov     eax, dword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data4+4
0x18000df56  cmp     [rdx+0Ch], eax
0x18000df59  jnz     short loc_18000DF62
0x18000df5b  mov     [r8], rcx
0x18000df5e  xor     ebx, ebx
0x18000df60  jmp     short loc_18000DF6D
0x18000df62  add     rcx, 8
0x18000df66  call    ?CanCastTo@?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$IAsyncOperation@_N@Foundation@Windows@@UIAsyncOperationLocal@Internal@6@U?$CloakedIid@UIAsyncDeferral@Internal@Windows@@@23@U?$CloakedIid@UIComPoolTask@Internal@Windows@@@23@U?$CloakedIid@UIAsyncFireCompletion@Internal@Windows@@@23@@Details@WRL@Microsoft@@IEAAJAEBU_GUID@@PEAPEAXPEA_N@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::Foundation::IAsyncOperation<bool>,Windows::Internal::IAsyncOperationLocal,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncDeferral>,Microsoft::WRL::CloakedIid<Windows::Internal::IComPoolTask>,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncFireCompletion>>::CanCastTo(_GUID const &,void * *,bool *)
0x18000df6b  mov     ebx, eax
0x18000df6d  test    ebx, ebx
0x18000df6f  js      short loc_18000DF80
0x18000df71  mov     rcx, [r8]
0x18000df74  mov     rdx, [rcx]
0x18000df77  mov     rax, [rdx+8]
0x18000df7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000df80  mov     eax, ebx
0x18000df82  add     rsp, 20h
0x18000df86  pop     rbx
0x18000df87  retn
```
