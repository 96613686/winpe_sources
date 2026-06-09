# Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,0,IActivationFactory,Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::System::Diagnostics::TraceReporting::IPlatformDiagnosticActionsStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::CanCastTo(_GUID const &,void * *,bool *)

- ea: `0x180007520`
- end: `0x1800075e7`
- name: `?CanCastTo@?$ImplementsHelper@U?$RuntimeClassFlags@$0N@@WRL@Microsoft@@$0A@UIActivationFactory@@U?$Implements@VFtmBase@WRL@Microsoft@@UIPlatformDiagnosticActionsStatics@TraceReporting@Diagnostics@System@Windows@@@23@VNil@Details@23@V6723@V6723@@Details@WRL@Microsoft@@IEAAJAEBU_GUID@@PEAPEAXPEA_N@Z`
- size: `199`
- prototype: `__int64 __fastcall(__int64, _DWORD *, _QWORD *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180006730`
- `0x180008680`

## callees

- `0x180007520`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,0,IActivationFactory,Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::System::Diagnostics::TraceReporting::IPlatformDiagnosticActionsStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::CanCastTo(
        __int64 a1,
        _DWORD *a2,
        _QWORD *a3)
{
  __int64 v4; // r9
  int v5; // eax
  unsigned int v6; // eax
  unsigned int v7; // ecx

  if ( *a2 == 53
    && a2[1] == *(_DWORD *)&GUID_00000035_0000_0000_c000_000000000046.Data2
    && a2[2] == *(_DWORD *)GUID_00000035_0000_0000_c000_000000000046.Data4
    && a2[3] == *(_DWORD *)&GUID_00000035_0000_0000_c000_000000000046.Data4[4] )
  {
    *a3 = a1;
    return 0;
  }
  v4 = a1 + 8;
  if ( *a2 == -1796592748 )
  {
    if ( a2[1] == *(_DWORD *)&GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data2
      && a2[2] == *(_DWORD *)GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4 )
    {
      v5 = *(_DWORD *)&GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4[4];
      goto LABEL_14;
    }
LABEL_16:
    v7 = -2147467262;
    if ( *a2 == -1055630086
      && a2[1] == *(_DWORD *)&GUID_c1145cfa_9292_4267_890a_9ea3ed072312.Data2
      && a2[2] == *(_DWORD *)GUID_c1145cfa_9292_4267_890a_9ea3ed072312.Data4
      && a2[3] == *(_DWORD *)&GUID_c1145cfa_9292_4267_890a_9ea3ed072312.Data4[4] )
    {
      *a3 = v4 + 32;
      v6 = 0;
    }
    else
    {
      v6 = -2147467262;
    }
    if ( v6 == -2147467262 )
      return v7;
    return v6;
  }
  if ( *a2 != 3
    || a2[1] != *(_DWORD *)&GUID_00000003_0000_0000_c000_000000000046.Data2
    || a2[2] != *(_DWORD *)GUID_00000003_0000_0000_c000_000000000046.Data4 )
  {
    goto LABEL_16;
  }
  v5 = *(_DWORD *)&GUID_00000003_0000_0000_c000_000000000046.Data4[4];
LABEL_14:
  if ( a2[3] != v5 )
    goto LABEL_16;
  v6 = 0;
  *a3 = v4;
  return v6;
}

```

## disassembly

```asm
0x180007520  cmp     dword ptr [rdx], 35h ; '5'
0x180007523  jnz     short loc_18000754C
0x180007525  mov     eax, dword ptr cs:_GUID_00000035_0000_0000_c000_000000000046.Data2
0x18000752b  cmp     [rdx+4], eax
0x18000752e  jnz     short loc_18000754C
0x180007530  mov     eax, dword ptr cs:_GUID_00000035_0000_0000_c000_000000000046.Data4
0x180007536  cmp     [rdx+8], eax
0x180007539  jnz     short loc_18000754C
0x18000753b  mov     eax, dword ptr cs:_GUID_00000035_0000_0000_c000_000000000046.Data4+4
0x180007541  cmp     [rdx+0Ch], eax
0x180007544  jnz     short loc_18000754C
0x180007546  mov     [r8], rcx
0x180007549  xor     eax, eax
0x18000754b  retn
0x18000754c  cmp     dword ptr [rdx], 94EA2B94h
0x180007552  lea     r9, [rcx+8]
0x180007556  jnz     short loc_180007576
0x180007558  mov     eax, dword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data2
0x18000755e  cmp     [rdx+4], eax
0x180007561  jnz     short loc_1800075A3
0x180007563  mov     eax, dword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4
0x180007569  cmp     [rdx+8], eax
0x18000756c  jnz     short loc_1800075A3
0x18000756e  mov     eax, dword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4+4
0x180007574  jmp     short loc_180007597
0x180007576  cmp     dword ptr [rdx], 3
0x180007579  jnz     short loc_1800075A3
0x18000757b  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data2
0x180007581  cmp     [rdx+4], eax
0x180007584  jnz     short loc_1800075A3
0x180007586  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data4
0x18000758c  cmp     [rdx+8], eax
0x18000758f  jnz     short loc_1800075A3
0x180007591  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data4+4
0x180007597  cmp     [rdx+0Ch], eax
0x18000759a  jnz     short loc_1800075A3
0x18000759c  xor     eax, eax
0x18000759e  mov     [r8], r9
0x1800075a1  jmp     short loc_1800075E2
0x1800075a3  cmp     dword ptr [rdx], 0C1145CFAh
0x1800075a9  mov     ecx, 80004002h
0x1800075ae  jnz     short loc_1800075DC
0x1800075b0  mov     eax, dword ptr cs:_GUID_c1145cfa_9292_4267_890a_9ea3ed072312.Data2
0x1800075b6  cmp     [rdx+4], eax
0x1800075b9  jnz     short loc_1800075DC
0x1800075bb  mov     eax, dword ptr cs:_GUID_c1145cfa_9292_4267_890a_9ea3ed072312.Data4
0x1800075c1  cmp     [rdx+8], eax
0x1800075c4  jnz     short loc_1800075DC
0x1800075c6  mov     eax, dword ptr cs:_GUID_c1145cfa_9292_4267_890a_9ea3ed072312.Data4+4
0x1800075cc  cmp     [rdx+0Ch], eax
0x1800075cf  jnz     short loc_1800075DC
0x1800075d1  lea     rax, [r9+20h]
0x1800075d5  mov     [r8], rax
0x1800075d8  xor     eax, eax
0x1800075da  jmp     short loc_1800075DE
0x1800075dc  mov     eax, ecx
0x1800075de  cmp     eax, ecx
0x1800075e0  jz      short loc_1800075E4
0x1800075e2  mov     ecx, eax
0x1800075e4  mov     eax, ecx
0x1800075e6  retn
```
