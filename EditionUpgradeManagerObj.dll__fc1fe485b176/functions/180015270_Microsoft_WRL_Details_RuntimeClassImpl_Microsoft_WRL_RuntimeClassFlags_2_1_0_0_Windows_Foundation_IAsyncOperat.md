# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Licensing::ProductKeyRedemptionResult *>,Microsoft::WRL::FtmBase>::QueryInterface(_GUID const &,void * *)

- ea: `0x180015270`
- end: `0x18001534d`
- name: `?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$IAsyncOperationCompletedHandler@PEAVProductKeyRedemptionResult@Licensing@System@Windows@@@Foundation@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `221`
- prototype: `__int64 __fastcall(__int64, _DWORD *, __int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180015360`

## callees

- `0x180015270`
- `0x180023010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Licensing::ProductKeyRedemptionResult *>,Microsoft::WRL::FtmBase>::QueryInterface(
        __int64 a1,
        _DWORD *a2,
        __int64 *a3)
{
  unsigned int v3; // ebx
  __int64 v4; // rcx
  int v5; // eax

  v3 = 0;
  *a3 = 0;
  if ( *a2 )
  {
    if ( *a2 == -1734456067
      && a2[1] == *(_DWORD *)&GUID_989e4cfd_47ca_5a01_8675_282d33871899.Data2
      && a2[2] == *(_DWORD *)GUID_989e4cfd_47ca_5a01_8675_282d33871899.Data4
      && a2[3] == *(_DWORD *)&GUID_989e4cfd_47ca_5a01_8675_282d33871899.Data4[4] )
    {
      *a3 = a1;
LABEL_22:
      a1 = *a3;
      goto LABEL_6;
    }
LABEL_12:
    v4 = a1 + 8;
    if ( *a2 == -1796592748 )
    {
      if ( a2[1] != *(_DWORD *)&GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data2
        || a2[2] != *(_DWORD *)GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4 )
      {
        return (unsigned int)-2147467262;
      }
      v5 = *(_DWORD *)&GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4[4];
    }
    else
    {
      if ( *a2 != 3
        || a2[1] != *(_DWORD *)&GUID_00000003_0000_0000_c000_000000000046.Data2
        || a2[2] != *(_DWORD *)GUID_00000003_0000_0000_c000_000000000046.Data4 )
      {
        return (unsigned int)-2147467262;
      }
      v5 = *(_DWORD *)&GUID_00000003_0000_0000_c000_000000000046.Data4[4];
    }
    if ( a2[3] == v5 )
    {
      *a3 = v4;
      goto LABEL_22;
    }
    return (unsigned int)-2147467262;
  }
  if ( a2[1] != *(_DWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data2
    || a2[2] != *(_DWORD *)GUID_00000000_0000_0000_c000_000000000046.Data4
    || a2[3] != *(_DWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data4[4] )
  {
    goto LABEL_12;
  }
  *a3 = a1;
LABEL_6:
  (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
  return v3;
}

```

## disassembly

```asm
0x180015270  push    rbx
0x180015272  sub     rsp, 20h
0x180015276  xor     ebx, ebx
0x180015278  mov     [r8], rbx
0x18001527b  cmp     [rdx], ebx
0x18001527d  jnz     short loc_1800152B4
0x18001527f  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data2
0x180015285  cmp     [rdx+4], eax
0x180015288  jnz     short loc_1800152E2
0x18001528a  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x180015290  cmp     [rdx+8], eax
0x180015293  jnz     short loc_1800152E2
0x180015295  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4+4
0x18001529b  cmp     [rdx+0Ch], eax
0x18001529e  jnz     short loc_1800152E2
0x1800152a0  mov     [r8], rcx
0x1800152a3  mov     rax, [rcx]
0x1800152a6  mov     rax, [rax+8]
0x1800152aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800152af  jmp     loc_180015345
0x1800152b4  cmp     dword ptr [rdx], 989E4CFDh
0x1800152ba  jnz     short loc_1800152E2
0x1800152bc  mov     eax, dword ptr cs:_GUID_989e4cfd_47ca_5a01_8675_282d33871899.Data2
0x1800152c2  cmp     [rdx+4], eax
0x1800152c5  jnz     short loc_1800152E2
0x1800152c7  mov     eax, dword ptr cs:_GUID_989e4cfd_47ca_5a01_8675_282d33871899.Data4
0x1800152cd  cmp     [rdx+8], eax
0x1800152d0  jnz     short loc_1800152E2
0x1800152d2  mov     eax, dword ptr cs:_GUID_989e4cfd_47ca_5a01_8675_282d33871899.Data4+4
0x1800152d8  cmp     [rdx+0Ch], eax
0x1800152db  jnz     short loc_1800152E2
0x1800152dd  mov     [r8], rcx
0x1800152e0  jmp     short loc_180015338
0x1800152e2  add     rcx, 8
0x1800152e6  cmp     dword ptr [rdx], 94EA2B94h
0x1800152ec  jnz     short loc_18001530C
0x1800152ee  mov     eax, dword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data2
0x1800152f4  cmp     [rdx+4], eax
0x1800152f7  jnz     short loc_180015340
0x1800152f9  mov     eax, dword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4
0x1800152ff  cmp     [rdx+8], eax
0x180015302  jnz     short loc_180015340
0x180015304  mov     eax, dword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4+4
0x18001530a  jmp     short loc_18001532D
0x18001530c  cmp     dword ptr [rdx], 3
0x18001530f  jnz     short loc_180015340
0x180015311  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data2
0x180015317  cmp     [rdx+4], eax
0x18001531a  jnz     short loc_180015340
0x18001531c  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data4
0x180015322  cmp     [rdx+8], eax
0x180015325  jnz     short loc_180015340
0x180015327  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data4+4
0x18001532d  cmp     [rdx+0Ch], eax
0x180015330  jnz     short loc_180015340
0x180015332  mov     rax, r8
0x180015335  mov     [rax], rcx
0x180015338  mov     rcx, [r8]
0x18001533b  jmp     loc_1800152A3
0x180015340  mov     ebx, 80004002h
0x180015345  mov     eax, ebx
0x180015347  add     rsp, 20h
0x18001534b  pop     rbx
0x18001534c  retn
```
