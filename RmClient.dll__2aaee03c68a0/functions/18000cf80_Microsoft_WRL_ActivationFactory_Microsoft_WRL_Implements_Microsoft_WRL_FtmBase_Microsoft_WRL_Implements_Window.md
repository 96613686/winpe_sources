# Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Microsoft::WRL::Implements<Windows::System::IMemoryManagerStatics,Windows::System::IMemoryManagerStatics2,Windows::System::IMemoryManagerStatics3,Windows::System::IMemoryManagerStatics4>>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::QueryInterface(_GUID const &,void * *)

- ea: `0x18000cf80`
- end: `0x18000d1ab`
- name: `?QueryInterface@?$ActivationFactory@U?$Implements@VFtmBase@WRL@Microsoft@@U?$Implements@UIMemoryManagerStatics@System@Windows@@UIMemoryManagerStatics2@23@UIMemoryManagerStatics3@23@UIMemoryManagerStatics4@23@@23@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `555`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `5`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800150d0`
- `0x1800150e0`
- `0x1800150f0`
- `0x180015100`
- `0x180015110`

## callees

- `0x18000c070`
- `0x18000cf80`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Microsoft::WRL::Implements<Windows::System::IMemoryManagerStatics,Windows::System::IMemoryManagerStatics2,Windows::System::IMemoryManagerStatics3,Windows::System::IMemoryManagerStatics4>>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::QueryInterface(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  __int64 v3; // rcx
  __int64 v4; // r10
  unsigned int v5; // ebx
  const struct _GUID *v6; // rcx
  __int64 v7; // r10
  int v8; // eax
  int v10; // eax
  int v11; // eax
  __int64 v12; // r10

  *a3 = 0;
  if ( *(_DWORD *)a2 )
  {
    if ( *(_DWORD *)a2 != -1350114592 )
    {
      if ( *(_DWORD *)a2 == 53
        && *(_DWORD *)(a2 + 4) == *(_DWORD *)&GUID_00000035_0000_0000_c000_000000000046.Data2
        && *(_DWORD *)(a2 + 8) == *(_DWORD *)GUID_00000035_0000_0000_c000_000000000046.Data4
        && *(_DWORD *)(a2 + 12) == *(_DWORD *)&GUID_00000035_0000_0000_c000_000000000046.Data4[4] )
      {
        *a3 = a1;
        v5 = 0;
LABEL_23:
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a3 + 8LL))(*a3);
        return v5;
      }
LABEL_4:
      v3 = a1 + 8;
      if ( *(_DWORD *)a2 == -1796592748 )
      {
        if ( *(_DWORD *)(a2 + 4) != *(_DWORD *)&GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data2
          || *(_DWORD *)(a2 + 8) != *(_DWORD *)GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4 )
        {
          goto LABEL_6;
        }
        v10 = *(_DWORD *)&GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4[4];
      }
      else
      {
        if ( *(_DWORD *)a2 != 3
          || *(_DWORD *)(a2 + 4) != *(_DWORD *)&GUID_00000003_0000_0000_c000_000000000046.Data2
          || *(_DWORD *)(a2 + 8) != *(_DWORD *)GUID_00000003_0000_0000_c000_000000000046.Data4 )
        {
          goto LABEL_6;
        }
        v10 = *(_DWORD *)&GUID_00000003_0000_0000_c000_000000000046.Data4[4];
      }
      if ( *(_DWORD *)(a2 + 12) == v10 )
      {
        *a3 = v3;
        v5 = 0;
        goto LABEL_23;
      }
LABEL_6:
      v4 = v3 + 32;
      v5 = -2147467262;
      if ( *(_DWORD *)a2 == 1550591900
        && *(_DWORD *)(a2 + 4) == *(_DWORD *)&GUID_5c6c279c_d7ca_4779_9188_4057219ce64c.Data2
        && *(_DWORD *)(a2 + 8) == *(_DWORD *)GUID_5c6c279c_d7ca_4779_9188_4057219ce64c.Data4
        && *(_DWORD *)(a2 + 12) == *(_DWORD *)&GUID_5c6c279c_d7ca_4779_9188_4057219ce64c.Data4[4]
        || (v4 = v3 + 40, *(_DWORD *)a2 == 1861104927)
        && *(_DWORD *)(a2 + 4) == *(_DWORD *)&GUID_6eee351f_6d62_423f_9479_b01f9c9f7669.Data2
        && *(_DWORD *)(a2 + 8) == *(_DWORD *)GUID_6eee351f_6d62_423f_9479_b01f9c9f7669.Data4
        && *(_DWORD *)(a2 + 12) == *(_DWORD *)&GUID_6eee351f_6d62_423f_9479_b01f9c9f7669.Data4[4] )
      {
        *a3 = v4;
        v11 = 0;
        goto LABEL_36;
      }
      if ( InlineIsEqualGUID((const struct _GUID *)a2, &GUID_149b59ce_92ad_4e35_89eb_50dfb4c0d91c) )
      {
        *a3 = v7;
      }
      else
      {
        if ( !InlineIsEqualGUID(v6, &GUID_c5a94828_e84e_4886_8a0d_44b3190e3b72) )
        {
          v11 = -2147467262;
          goto LABEL_34;
        }
        *a3 = v12 + 8;
      }
      v11 = 0;
LABEL_34:
      if ( v11 != -2147467262 )
      {
LABEL_22:
        v5 = v11;
        goto LABEL_23;
      }
      v11 = -2147467262;
LABEL_36:
      if ( v11 == -2147467262 )
        return v5;
      goto LABEL_22;
    }
    if ( *(_DWORD *)(a2 + 4) != *(_DWORD *)&GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data2
      || *(_DWORD *)(a2 + 8) != *(_DWORD *)GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4 )
    {
      goto LABEL_4;
    }
    v8 = *(_DWORD *)&GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4[4];
  }
  else
  {
    if ( *(_DWORD *)(a2 + 4) != *(_DWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data2
      || *(_DWORD *)(a2 + 8) != *(_DWORD *)GUID_00000000_0000_0000_c000_000000000046.Data4 )
    {
      goto LABEL_4;
    }
    v8 = *(_DWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data4[4];
  }
  if ( *(_DWORD *)(a2 + 12) != v8 )
    goto LABEL_4;
  *a3 = a1;
  (*(void (__fastcall **)(__int64, __int64, _QWORD *, __int64))(*(_QWORD *)a1 + 8LL))(a1, a2, a3, a2);
  return 0;
}

```

## disassembly

```asm
0x18000cf80  push    rbx
0x18000cf82  sub     rsp, 20h
0x18000cf86  mov     qword ptr [r8], 0
0x18000cf8d  mov     r9, rdx
0x18000cf90  cmp     dword ptr [rdx], 0
0x18000cf93  jz      short loc_18000D00B
0x18000cf95  cmp     dword ptr [rdx], 0AF86E2E0h
0x18000cf9b  jz      loc_18000D043
0x18000cfa1  cmp     dword ptr [rdx], 35h ; '5'
0x18000cfa4  jz      loc_18000D069
0x18000cfaa  add     rcx, 8
0x18000cfae  cmp     dword ptr [rdx], 94EA2B94h
0x18000cfb4  jz      loc_18000D0BA
0x18000cfba  cmp     dword ptr [rdx], 3
0x18000cfbd  jz      loc_18000D135
0x18000cfc3  cmp     dword ptr [rdx], 5C6C279Ch
0x18000cfc9  lea     r10, [rcx+20h]
0x18000cfcd  mov     ebx, 80004002h
0x18000cfd2  jz      loc_18000D0EE
0x18000cfd8  add     r10, 8
0x18000cfdc  cmp     dword ptr [rdx], 6EEE351Fh
0x18000cfe2  jz      loc_18000D15B
0x18000cfe8  lea     rdx, _GUID_149b59ce_92ad_4e35_89eb_50dfb4c0d91c; struct _GUID *
0x18000cfef  mov     rcx, r9; struct _GUID *
0x18000cff2  add     r10, 8
0x18000cff6  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x18000cffb  test    eax, eax
0x18000cffd  jz      loc_18000D194
0x18000d003  mov     [r8], r10
0x18000d006  jmp     loc_18000D190
0x18000d00b  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data2
0x18000d011  cmp     [rdx+4], eax
0x18000d014  jnz     short loc_18000CFAA
0x18000d016  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x18000d01c  cmp     [rdx+8], eax
0x18000d01f  jnz     short loc_18000CFAA
0x18000d021  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4+4
0x18000d027  cmp     [rdx+0Ch], eax
0x18000d02a  jnz     loc_18000CFAA
0x18000d030  mov     [r8], rcx
0x18000d033  mov     rax, [rcx]
0x18000d036  mov     rax, [rax+8]
0x18000d03a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d03f  xor     ebx, ebx
0x18000d041  jmp     short loc_18000D0B2
0x18000d043  mov     eax, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data2
0x18000d049  cmp     [rdx+4], eax
0x18000d04c  jnz     loc_18000CFAA
0x18000d052  mov     eax, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4
0x18000d058  cmp     [rdx+8], eax
0x18000d05b  jnz     loc_18000CFAA
0x18000d061  mov     eax, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4+4
0x18000d067  jmp     short loc_18000D027
0x18000d069  mov     eax, dword ptr cs:_GUID_00000035_0000_0000_c000_000000000046.Data2
0x18000d06f  cmp     [rdx+4], eax
0x18000d072  jnz     loc_18000CFAA
0x18000d078  mov     eax, dword ptr cs:_GUID_00000035_0000_0000_c000_000000000046.Data4
0x18000d07e  cmp     [rdx+8], eax
0x18000d081  jnz     loc_18000CFAA
0x18000d087  mov     eax, dword ptr cs:_GUID_00000035_0000_0000_c000_000000000046.Data4+4
0x18000d08d  cmp     [rdx+0Ch], eax
0x18000d090  jnz     loc_18000CFAA
0x18000d096  mov     [r8], rcx
0x18000d099  xor     ebx, ebx
0x18000d09b  jmp     short loc_18000D0A3
0x18000d09d  mov     ebx, eax
0x18000d09f  test    ebx, ebx
0x18000d0a1  js      short loc_18000D0B2
0x18000d0a3  mov     rcx, [r8]
0x18000d0a6  mov     rdx, [rcx]
0x18000d0a9  mov     rax, [rdx+8]
0x18000d0ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d0b2  mov     eax, ebx
0x18000d0b4  add     rsp, 20h
0x18000d0b8  pop     rbx
0x18000d0b9  retn
0x18000d0ba  mov     eax, dword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data2
0x18000d0c0  cmp     [rdx+4], eax
0x18000d0c3  jnz     loc_18000CFC3
0x18000d0c9  mov     eax, dword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4
0x18000d0cf  cmp     [rdx+8], eax
0x18000d0d2  jnz     loc_18000CFC3
0x18000d0d8  mov     eax, dword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4+4
0x18000d0de  cmp     [rdx+0Ch], eax
0x18000d0e1  jnz     loc_18000CFC3
0x18000d0e7  mov     [r8], rcx
0x18000d0ea  xor     ebx, ebx
0x18000d0ec  jmp     short loc_18000D09F
0x18000d0ee  mov     eax, dword ptr cs:_GUID_5c6c279c_d7ca_4779_9188_4057219ce64c.Data2
0x18000d0f4  cmp     [rdx+4], eax
0x18000d0f7  jnz     loc_18000CFD8
0x18000d0fd  mov     eax, dword ptr cs:_GUID_5c6c279c_d7ca_4779_9188_4057219ce64c.Data4
0x18000d103  cmp     [rdx+8], eax
0x18000d106  jnz     loc_18000CFD8
0x18000d10c  mov     eax, dword ptr cs:_GUID_5c6c279c_d7ca_4779_9188_4057219ce64c.Data4+4
0x18000d112  cmp     [rdx+0Ch], eax
0x18000d115  jnz     loc_18000CFD8
0x18000d11b  mov     [r8], r10
0x18000d11e  xor     eax, eax
0x18000d120  jmp     short loc_18000D12C
0x18000d122  cmp     eax, ebx
0x18000d124  jnz     loc_18000D09D
0x18000d12a  mov     eax, ebx
0x18000d12c  cmp     eax, ebx
0x18000d12e  jz      short loc_18000D0B2
0x18000d130  jmp     loc_18000D09D
0x18000d135  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data2
0x18000d13b  cmp     [rdx+4], eax
0x18000d13e  jnz     loc_18000CFC3
0x18000d144  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data4
0x18000d14a  cmp     [rdx+8], eax
0x18000d14d  jnz     loc_18000CFC3
0x18000d153  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data4+4
0x18000d159  jmp     short loc_18000D0DE
0x18000d15b  mov     eax, dword ptr cs:_GUID_6eee351f_6d62_423f_9479_b01f9c9f7669.Data2
0x18000d161  cmp     [rdx+4], eax
0x18000d164  jnz     loc_18000CFE8
0x18000d16a  mov     eax, dword ptr cs:_GUID_6eee351f_6d62_423f_9479_b01f9c9f7669.Data4
0x18000d170  cmp     [rdx+8], eax
0x18000d173  jnz     loc_18000CFE8
0x18000d179  mov     eax, dword ptr cs:_GUID_6eee351f_6d62_423f_9479_b01f9c9f7669.Data4+4
0x18000d17f  cmp     [rdx+0Ch], eax
0x18000d182  jz      short loc_18000D11B
0x18000d184  jmp     loc_18000CFE8
0x18000d189  lea     rax, [r10+8]
0x18000d18d  mov     [r8], rax
0x18000d190  xor     eax, eax
0x18000d192  jmp     short loc_18000D122
0x18000d194  lea     rdx, _GUID_c5a94828_e84e_4886_8a0d_44b3190e3b72; struct _GUID *
0x18000d19b  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x18000d1a0  test    eax, eax
0x18000d1a2  jnz     short loc_18000D189
0x18000d1a4  mov     eax, ebx
0x18000d1a6  jmp     loc_18000D122
```
