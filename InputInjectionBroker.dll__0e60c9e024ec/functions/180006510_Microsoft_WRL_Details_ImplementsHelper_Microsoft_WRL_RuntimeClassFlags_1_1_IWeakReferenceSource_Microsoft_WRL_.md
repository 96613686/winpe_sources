# Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Microsoft::WRL::FtmBase>::CanCastTo(_GUID const &,void * *,bool *)

- ea: `0x180006510`
- end: `0x180006598`
- name: `?CanCastTo@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAJAEBU_GUID@@PEAPEAXPEA_N@Z`
- size: `136`
- prototype: `__int64 __fastcall(__int64, _DWORD *, _QWORD *)`
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180006f10`
- `0x1800087d0`
- `0x18000f7d0`
- `0x18000fcd0`
- `0x1800101f0`
- `0x180010480`
- `0x180011130`

## callees

- `0x180006510`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Microsoft::WRL::FtmBase>::CanCastTo(
        __int64 a1,
        _DWORD *a2,
        _QWORD *a3)
{
  __int64 result; // rax
  __int64 v4; // rcx
  int v5; // eax

  if ( *a2 == 56
    && a2[1] == *(_DWORD *)&GUID_00000038_0000_0000_c000_000000000046.Data2
    && a2[2] == *(_DWORD *)GUID_00000038_0000_0000_c000_000000000046.Data4
    && a2[3] == *(_DWORD *)&GUID_00000038_0000_0000_c000_000000000046.Data4[4] )
  {
    *a3 = a1;
    return 0;
  }
  v4 = a1 + 8;
  if ( *a2 == -1796592748 )
  {
    if ( a2[1] != *(_DWORD *)&GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data2
      || a2[2] != *(_DWORD *)GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4 )
    {
      return 2147500034LL;
    }
    v5 = *(_DWORD *)&GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4[4];
  }
  else
  {
    if ( *a2 != 3
      || a2[1] != *(_DWORD *)&GUID_00000003_0000_0000_c000_000000000046.Data2
      || a2[2] != *(_DWORD *)GUID_00000003_0000_0000_c000_000000000046.Data4 )
    {
      return 2147500034LL;
    }
    v5 = *(_DWORD *)&GUID_00000003_0000_0000_c000_000000000046.Data4[4];
  }
  if ( a2[3] == v5 )
  {
    result = 0;
    *a3 = v4;
    return result;
  }
  return 2147500034LL;
}

```

## disassembly

```asm
0x180006510  cmp     dword ptr [rdx], 38h ; '8'
0x180006513  jnz     short loc_18000653C
0x180006515  mov     eax, dword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data2
0x18000651b  cmp     [rdx+4], eax
0x18000651e  jnz     short loc_18000653C
0x180006520  mov     eax, dword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data4
0x180006526  cmp     [rdx+8], eax
0x180006529  jnz     short loc_18000653C
0x18000652b  mov     eax, dword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data4+4
0x180006531  cmp     [rdx+0Ch], eax
0x180006534  jnz     short loc_18000653C
0x180006536  mov     [r8], rcx
0x180006539  xor     eax, eax
0x18000653b  retn
0x18000653c  add     rcx, 8
0x180006540  cmp     dword ptr [rdx], 94EA2B94h
0x180006546  jnz     short loc_180006566
0x180006548  mov     eax, dword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data2
0x18000654e  cmp     [rdx+4], eax
0x180006551  jnz     short loc_180006592
0x180006553  mov     eax, dword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4
0x180006559  cmp     [rdx+8], eax
0x18000655c  jnz     short loc_180006592
0x18000655e  mov     eax, dword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4+4
0x180006564  jmp     short loc_180006587
0x180006566  cmp     dword ptr [rdx], 3
0x180006569  jnz     short loc_180006592
0x18000656b  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data2
0x180006571  cmp     [rdx+4], eax
0x180006574  jnz     short loc_180006592
0x180006576  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data4
0x18000657c  cmp     [rdx+8], eax
0x18000657f  jnz     short loc_180006592
0x180006581  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data4+4
0x180006587  cmp     [rdx+0Ch], eax
0x18000658a  jnz     short loc_180006592
0x18000658c  xor     eax, eax
0x18000658e  mov     [r8], rcx
0x180006591  retn
0x180006592  mov     eax, 80004002h
0x180006597  retn
```
