# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::System::Diagnostics::IDiagnosticActionResult,Microsoft::WRL::FtmBase>::QueryInterface(_GUID const &,void * *)

- ea: `0x18000f1f0`
- end: `0x18000f33b`
- name: `?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIDiagnosticActionResult@Diagnostics@System@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `331`
- prototype: `__int64 __fastcall(__int64, _DWORD *, _QWORD *)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000f350`
- `0x18000f360`
- `0x18000f370`

## callees

- `0x18000f1f0`
- `0x180011010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::System::Diagnostics::IDiagnosticActionResult,Microsoft::WRL::FtmBase>::QueryInterface(
        __int64 a1,
        _DWORD *a2,
        _QWORD *a3)
{
  int v3; // eax
  int v4; // ebx
  __int64 v5; // rcx
  int v6; // eax

  *a3 = 0;
  if ( !*a2 )
  {
    if ( a2[1] == *(_DWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data2
      && a2[2] == *(_DWORD *)GUID_00000000_0000_0000_c000_000000000046.Data4 )
    {
      v3 = *(_DWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data4[4];
      goto LABEL_9;
    }
LABEL_16:
    a1 += 8;
    if ( *a2 != 56
      || a2[1] != *(_DWORD *)&GUID_00000038_0000_0000_c000_000000000046.Data2
      || a2[2] != *(_DWORD *)GUID_00000038_0000_0000_c000_000000000046.Data4
      || a2[3] != *(_DWORD *)&GUID_00000038_0000_0000_c000_000000000046.Data4[4] )
    {
      v5 = a1 + 8;
      if ( *a2 == -1796592748 )
      {
        if ( a2[1] != *(_DWORD *)&GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data2
          || a2[2] != *(_DWORD *)GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4 )
        {
          goto LABEL_30;
        }
        v6 = *(_DWORD *)&GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4[4];
      }
      else
      {
        if ( *a2 != 3
          || a2[1] != *(_DWORD *)&GUID_00000003_0000_0000_c000_000000000046.Data2
          || a2[2] != *(_DWORD *)GUID_00000003_0000_0000_c000_000000000046.Data4 )
        {
          goto LABEL_30;
        }
        v6 = *(_DWORD *)&GUID_00000003_0000_0000_c000_000000000046.Data4[4];
      }
      if ( a2[3] == v6 )
      {
        v4 = 0;
        *a3 = v5;
        goto LABEL_31;
      }
LABEL_30:
      v4 = -2147467262;
LABEL_31:
      if ( v4 < 0 )
        return (unsigned int)v4;
LABEL_32:
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a3 + 8LL))(*a3);
      return (unsigned int)v4;
    }
LABEL_15:
    *a3 = a1;
    v4 = 0;
    goto LABEL_32;
  }
  if ( *a2 != -1350114592 )
  {
    if ( *a2 == -1033526634
      && a2[1] == *(_DWORD *)&GUID_c265a296_e73b_4097_b28f_3442f03dd831.Data2
      && a2[2] == *(_DWORD *)GUID_c265a296_e73b_4097_b28f_3442f03dd831.Data4
      && a2[3] == *(_DWORD *)&GUID_c265a296_e73b_4097_b28f_3442f03dd831.Data4[4] )
    {
      goto LABEL_15;
    }
    goto LABEL_16;
  }
  if ( a2[1] != *(_DWORD *)&GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data2
    || a2[2] != *(_DWORD *)GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4 )
  {
    goto LABEL_16;
  }
  v3 = *(_DWORD *)&GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4[4];
LABEL_9:
  if ( a2[3] != v3 )
    goto LABEL_16;
  *a3 = a1;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
  return 0;
}

```

## disassembly

```asm
0x18000f1f0  push    rbx
0x18000f1f2  sub     rsp, 20h
0x18000f1f6  mov     qword ptr [r8], 0
0x18000f1fd  cmp     dword ptr [rdx], 0
0x18000f200  jnz     short loc_18000F224
0x18000f202  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data2
0x18000f208  cmp     [rdx+4], eax
0x18000f20b  jnz     loc_18000F296
0x18000f211  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x18000f217  cmp     [rdx+8], eax
0x18000f21a  jnz     short loc_18000F296
0x18000f21c  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4+4
0x18000f222  jmp     short loc_18000F248
0x18000f224  cmp     dword ptr [rdx], 0AF86E2E0h
0x18000f22a  jnz     short loc_18000F263
0x18000f22c  mov     eax, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data2
0x18000f232  cmp     [rdx+4], eax
0x18000f235  jnz     short loc_18000F296
0x18000f237  mov     eax, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4
0x18000f23d  cmp     [rdx+8], eax
0x18000f240  jnz     short loc_18000F296
0x18000f242  mov     eax, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4+4
0x18000f248  cmp     [rdx+0Ch], eax
0x18000f24b  jnz     short loc_18000F296
0x18000f24d  mov     [r8], rcx
0x18000f250  mov     rax, [rcx]
0x18000f253  mov     rax, [rax+8]
0x18000f257  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f25c  xor     ebx, ebx
0x18000f25e  jmp     loc_18000F333
0x18000f263  cmp     dword ptr [rdx], 0C265A296h
0x18000f269  jnz     short loc_18000F296
0x18000f26b  mov     eax, dword ptr cs:_GUID_c265a296_e73b_4097_b28f_3442f03dd831.Data2
0x18000f271  cmp     [rdx+4], eax
0x18000f274  jnz     short loc_18000F296
0x18000f276  mov     eax, dword ptr cs:_GUID_c265a296_e73b_4097_b28f_3442f03dd831.Data4
0x18000f27c  cmp     [rdx+8], eax
0x18000f27f  jnz     short loc_18000F296
0x18000f281  mov     eax, dword ptr cs:_GUID_c265a296_e73b_4097_b28f_3442f03dd831.Data4+4
0x18000f287  cmp     [rdx+0Ch], eax
0x18000f28a  jnz     short loc_18000F296
0x18000f28c  mov     [r8], rcx
0x18000f28f  xor     ebx, ebx
0x18000f291  jmp     loc_18000F323
0x18000f296  add     rcx, 8
0x18000f29a  cmp     dword ptr [rdx], 38h ; '8'
0x18000f29d  jnz     short loc_18000F2C0
0x18000f29f  mov     eax, dword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data2
0x18000f2a5  cmp     [rdx+4], eax
0x18000f2a8  jnz     short loc_18000F2C0
0x18000f2aa  mov     eax, dword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data4
0x18000f2b0  cmp     [rdx+8], eax
0x18000f2b3  jnz     short loc_18000F2C0
0x18000f2b5  mov     eax, dword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data4+4
0x18000f2bb  cmp     [rdx+0Ch], eax
0x18000f2be  jz      short loc_18000F28C
0x18000f2c0  add     rcx, 8
0x18000f2c4  cmp     dword ptr [rdx], 94EA2B94h
0x18000f2ca  jnz     short loc_18000F2EA
0x18000f2cc  mov     eax, dword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data2
0x18000f2d2  cmp     [rdx+4], eax
0x18000f2d5  jnz     short loc_18000F31A
0x18000f2d7  mov     eax, dword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4
0x18000f2dd  cmp     [rdx+8], eax
0x18000f2e0  jnz     short loc_18000F31A
0x18000f2e2  mov     eax, dword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4+4
0x18000f2e8  jmp     short loc_18000F30B
0x18000f2ea  cmp     dword ptr [rdx], 3
0x18000f2ed  jnz     short loc_18000F31A
0x18000f2ef  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data2
0x18000f2f5  cmp     [rdx+4], eax
0x18000f2f8  jnz     short loc_18000F31A
0x18000f2fa  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data4
0x18000f300  cmp     [rdx+8], eax
0x18000f303  jnz     short loc_18000F31A
0x18000f305  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data4+4
0x18000f30b  cmp     [rdx+0Ch], eax
0x18000f30e  jnz     short loc_18000F31A
0x18000f310  mov     rax, r8
0x18000f313  xor     ebx, ebx
0x18000f315  mov     [rax], rcx
0x18000f318  jmp     short loc_18000F31F
0x18000f31a  mov     ebx, 80004002h
0x18000f31f  test    ebx, ebx
0x18000f321  js      short loc_18000F333
0x18000f323  mov     rcx, [r8]
0x18000f326  mov     rdx, [rcx]
0x18000f329  mov     rax, [rdx+8]
0x18000f32d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f332  nop
0x18000f333  mov     eax, ebx
0x18000f335  add     rsp, 20h
0x18000f339  pop     rbx
0x18000f33a  retn
```
