# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::System::Diagnostics::IDiagnosticInvoker,Windows::System::Diagnostics::IDiagnosticInvoker2,Microsoft::WRL::FtmBase>::QueryInterface(_GUID const &,void * *)

- ea: `0x18000cfc0`
- end: `0x18000d13f`
- name: `?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIDiagnosticInvoker@Diagnostics@System@Windows@@UIDiagnosticInvoker2@567@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `383`
- prototype: `__int64 __fastcall(__int64, _DWORD *, _QWORD *)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000d150`
- `0x18000d160`
- `0x18000d170`
- `0x18000d4b0`

## callees

- `0x18000cfc0`
- `0x180011010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::System::Diagnostics::IDiagnosticInvoker,Windows::System::Diagnostics::IDiagnosticInvoker2,Microsoft::WRL::FtmBase>::QueryInterface(
        __int64 a1,
        _DWORD *a2,
        _QWORD *a3)
{
  int v3; // eax
  int v4; // ebx
  __int64 v5; // rcx
  __int64 v6; // rcx
  int v7; // eax

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
      if ( *a2 == -473983908
        && a2[1] == *(_DWORD *)&GUID_e3bf945c_155a_4b52_a8ec_070c44f95000.Data2
        && a2[2] == *(_DWORD *)GUID_e3bf945c_155a_4b52_a8ec_070c44f95000.Data4
        && a2[3] == *(_DWORD *)&GUID_e3bf945c_155a_4b52_a8ec_070c44f95000.Data4[4] )
      {
        *a3 = v5;
        v4 = 0;
        goto LABEL_36;
      }
      v6 = v5 + 8;
      if ( *a2 == -1796592748 )
      {
        if ( a2[1] != *(_DWORD *)&GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data2
          || a2[2] != *(_DWORD *)GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4 )
        {
          goto LABEL_35;
        }
        v7 = *(_DWORD *)&GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4[4];
      }
      else
      {
        if ( *a2 != 3
          || a2[1] != *(_DWORD *)&GUID_00000003_0000_0000_c000_000000000046.Data2
          || a2[2] != *(_DWORD *)GUID_00000003_0000_0000_c000_000000000046.Data4 )
        {
          goto LABEL_35;
        }
        v7 = *(_DWORD *)&GUID_00000003_0000_0000_c000_000000000046.Data4[4];
      }
      if ( a2[3] == v7 )
      {
        v4 = 0;
        *a3 = v6;
        goto LABEL_36;
      }
LABEL_35:
      v4 = -2147467262;
LABEL_36:
      if ( v4 < 0 )
        return (unsigned int)v4;
LABEL_37:
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a3 + 8LL))(*a3);
      return (unsigned int)v4;
    }
LABEL_15:
    *a3 = a1;
    v4 = 0;
    goto LABEL_37;
  }
  if ( *a2 != -1350114592 )
  {
    if ( *a2 == 410724106
      && a2[1] == *(_DWORD *)&GUID_187b270a_02e3_4f86_84fc_fdd892b5940f.Data2
      && a2[2] == *(_DWORD *)GUID_187b270a_02e3_4f86_84fc_fdd892b5940f.Data4
      && a2[3] == *(_DWORD *)&GUID_187b270a_02e3_4f86_84fc_fdd892b5940f.Data4[4] )
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
0x18000cfc0  push    rbx
0x18000cfc2  sub     rsp, 20h
0x18000cfc6  mov     qword ptr [r8], 0
0x18000cfcd  cmp     dword ptr [rdx], 0
0x18000cfd0  jnz     short loc_18000CFF4
0x18000cfd2  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data2
0x18000cfd8  cmp     [rdx+4], eax
0x18000cfdb  jnz     loc_18000D066
0x18000cfe1  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x18000cfe7  cmp     [rdx+8], eax
0x18000cfea  jnz     short loc_18000D066
0x18000cfec  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4+4
0x18000cff2  jmp     short loc_18000D018
0x18000cff4  cmp     dword ptr [rdx], 0AF86E2E0h
0x18000cffa  jnz     short loc_18000D033
0x18000cffc  mov     eax, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data2
0x18000d002  cmp     [rdx+4], eax
0x18000d005  jnz     short loc_18000D066
0x18000d007  mov     eax, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4
0x18000d00d  cmp     [rdx+8], eax
0x18000d010  jnz     short loc_18000D066
0x18000d012  mov     eax, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4+4
0x18000d018  cmp     [rdx+0Ch], eax
0x18000d01b  jnz     short loc_18000D066
0x18000d01d  mov     [r8], rcx
0x18000d020  mov     rax, [rcx]
0x18000d023  mov     rax, [rax+8]
0x18000d027  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d02c  xor     ebx, ebx
0x18000d02e  jmp     loc_18000D137
0x18000d033  cmp     dword ptr [rdx], 187B270Ah
0x18000d039  jnz     short loc_18000D066
0x18000d03b  mov     eax, dword ptr cs:_GUID_187b270a_02e3_4f86_84fc_fdd892b5940f.Data2
0x18000d041  cmp     [rdx+4], eax
0x18000d044  jnz     short loc_18000D066
0x18000d046  mov     eax, dword ptr cs:_GUID_187b270a_02e3_4f86_84fc_fdd892b5940f.Data4
0x18000d04c  cmp     [rdx+8], eax
0x18000d04f  jnz     short loc_18000D066
0x18000d051  mov     eax, dword ptr cs:_GUID_187b270a_02e3_4f86_84fc_fdd892b5940f.Data4+4
0x18000d057  cmp     [rdx+0Ch], eax
0x18000d05a  jnz     short loc_18000D066
0x18000d05c  mov     [r8], rcx
0x18000d05f  xor     ebx, ebx
0x18000d061  jmp     loc_18000D127
0x18000d066  add     rcx, 8
0x18000d06a  cmp     dword ptr [rdx], 38h ; '8'
0x18000d06d  jnz     short loc_18000D090
0x18000d06f  mov     eax, dword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data2
0x18000d075  cmp     [rdx+4], eax
0x18000d078  jnz     short loc_18000D090
0x18000d07a  mov     eax, dword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data4
0x18000d080  cmp     [rdx+8], eax
0x18000d083  jnz     short loc_18000D090
0x18000d085  mov     eax, dword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data4+4
0x18000d08b  cmp     [rdx+0Ch], eax
0x18000d08e  jz      short loc_18000D05C
0x18000d090  add     rcx, 8
0x18000d094  cmp     dword ptr [rdx], 0E3BF945Ch
0x18000d09a  jnz     short loc_18000D0C4
0x18000d09c  mov     eax, dword ptr cs:_GUID_e3bf945c_155a_4b52_a8ec_070c44f95000.Data2
0x18000d0a2  cmp     [rdx+4], eax
0x18000d0a5  jnz     short loc_18000D0C4
0x18000d0a7  mov     eax, dword ptr cs:_GUID_e3bf945c_155a_4b52_a8ec_070c44f95000.Data4
0x18000d0ad  cmp     [rdx+8], eax
0x18000d0b0  jnz     short loc_18000D0C4
0x18000d0b2  mov     eax, dword ptr cs:_GUID_e3bf945c_155a_4b52_a8ec_070c44f95000.Data4+4
0x18000d0b8  cmp     [rdx+0Ch], eax
0x18000d0bb  jnz     short loc_18000D0C4
0x18000d0bd  mov     [r8], rcx
0x18000d0c0  xor     ebx, ebx
0x18000d0c2  jmp     short loc_18000D123
0x18000d0c4  add     rcx, 8
0x18000d0c8  cmp     dword ptr [rdx], 94EA2B94h
0x18000d0ce  jnz     short loc_18000D0EE
0x18000d0d0  mov     eax, dword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data2
0x18000d0d6  cmp     [rdx+4], eax
0x18000d0d9  jnz     short loc_18000D11E
0x18000d0db  mov     eax, dword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4
0x18000d0e1  cmp     [rdx+8], eax
0x18000d0e4  jnz     short loc_18000D11E
0x18000d0e6  mov     eax, dword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4+4
0x18000d0ec  jmp     short loc_18000D10F
0x18000d0ee  cmp     dword ptr [rdx], 3
0x18000d0f1  jnz     short loc_18000D11E
0x18000d0f3  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data2
0x18000d0f9  cmp     [rdx+4], eax
0x18000d0fc  jnz     short loc_18000D11E
0x18000d0fe  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data4
0x18000d104  cmp     [rdx+8], eax
0x18000d107  jnz     short loc_18000D11E
0x18000d109  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data4+4
0x18000d10f  cmp     [rdx+0Ch], eax
0x18000d112  jnz     short loc_18000D11E
0x18000d114  mov     rax, r8
0x18000d117  xor     ebx, ebx
0x18000d119  mov     [rax], rcx
0x18000d11c  jmp     short loc_18000D123
0x18000d11e  mov     ebx, 80004002h
0x18000d123  test    ebx, ebx
0x18000d125  js      short loc_18000D137
0x18000d127  mov     rcx, [r8]
0x18000d12a  mov     rdx, [rcx]
0x18000d12d  mov     rax, [rdx+8]
0x18000d131  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d136  nop
0x18000d137  mov     eax, ebx
0x18000d139  add     rsp, 20h
0x18000d13d  pop     rbx
0x18000d13e  retn
```
