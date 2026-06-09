# Concurrency::details::_AsyncTaskThunk_Concurrency::details::_AsyncAttributes__lambda_012995b310defc0ef83a366488a71671__void_void_Concurrency::details::_TaskTypeTraits_void_0__0_0___::[Platform::Object]::__abi_QueryInterface

- ea: `0x140020ac0`
- end: `0x140020d9f`
- name: `Concurrency::details::_AsyncTaskThunk_Concurrency::details::_AsyncAttributes__lambda_012995b310defc0ef83a366488a71671__void_void_Concurrency::details::_TaskTypeTraits_void_0__0_0___::[Platform::Object]::__abi_QueryInterface`
- size: `735`
- prototype: ``
- caller_count: `10`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x140020670`
- `0x140020db0`
- `0x140020dc0`
- `0x140020dd0`
- `0x140020de0`
- `0x140020df0`
- `0x140020e00`
- `0x140020e10`
- `0x140020e20`
- `0x140020e40`

## callees

- `0x140008470`
- `0x140020ac0`

## pseudocode

```c
__int64 __fastcall Concurrency::details::_AsyncTaskThunk_Concurrency::details::_AsyncAttributes__lambda_012995b310defc0ef83a366488a71671__void_void_Concurrency::details::_TaskTypeTraits_void_0__0_0___::_Platform::Object_::__abi_QueryInterface(
        _QWORD *a1,
        __int64 a2,
        void **a3)
{
  unsigned __int64 v3; // r10
  __int64 v4; // rax
  unsigned __int64 v5; // rdx

  if ( !*(_DWORD *)a2 )
  {
    if ( *(_DWORD *)(a2 + 4) != *(_DWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data2
      || *(_DWORD *)(a2 + 8) != *(_DWORD *)GUID_00000000_0000_0000_c000_000000000046.Data4 )
    {
      goto LABEL_13;
    }
    if ( *(_DWORD *)(a2 + 12) == *(_DWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data4[4] )
      goto LABEL_18;
  }
  if ( *(_DWORD *)a2 == -1350114592 )
  {
    if ( *(_DWORD *)(a2 + 4) != *(_DWORD *)&GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data2
      || *(_DWORD *)(a2 + 8) != *(_DWORD *)GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4 )
    {
      goto LABEL_13;
    }
    if ( *(_DWORD *)(a2 + 12) == *(_DWORD *)&GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4[4] )
      goto LABEL_18;
  }
  if ( *(_DWORD *)a2 == 712966143
    && *(_DWORD *)(a2 + 4) == 873057582
    && *(_DWORD *)(a2 + 8) == 207100334
    && *(_DWORD *)(a2 + 12) == -10681234 )
  {
LABEL_18:
    *a3 = a1;
    if ( a1[21] )
    {
      v4 = a1[21];
      goto LABEL_57;
    }
    return 0;
  }
LABEL_13:
  v3 = (unsigned __int64)(a1 + 21);
  if ( (-(__int64)(a1[22] != 0) & (unsigned __int64)(a1 + 21)) != 0
    && *(_DWORD *)a2 == -1796592748
    && *(_DWORD *)(a2 + 4) == 1239476684
    && *(_DWORD *)(a2 + 8) == 1693384640
    && *(_DWORD *)(a2 + 12) == -1873047606 )
  {
    goto LABEL_18;
  }
  if ( *(_DWORD *)a2 != 56 )
  {
    switch ( *(_DWORD *)a2 )
    {
      case 0x5A648006:
        if ( *(_DWORD *)(a2 + 4) != 1302955066 || *(_DWORD *)(a2 + 8) != 647846790 || *(_DWORD *)(a2 + 12) != 2074992613 )
          goto LABEL_59;
        v5 = (unsigned __int64)(a1 + 5);
        break;
      case 0x36:
        if ( *(_DWORD *)(a2 + 4) || *(_DWORD *)(a2 + 8) != 192 || *(_DWORD *)(a2 + 12) != 1174405120 )
          goto LABEL_59;
        v5 = (unsigned __int64)(a1 + 6);
        break;
      case 0x867A7A8E:
        if ( *(_DWORD *)(a2 + 4) != 954167318 || *(_DWORD *)(a2 + 8) != -1350084429 || *(_DWORD *)(a2 + 12) != 466931300 )
          goto LABEL_59;
        v5 = (unsigned __int64)(a1 + 4);
        break;
      case 0xC74B4D82:
        if ( *(_DWORD *)(a2 + 4) != 885402115 || *(_DWORD *)(a2 + 8) != -457647979 || *(_DWORD *)(a2 + 12) != 99325659 )
          goto LABEL_59;
        v5 = (unsigned __int64)(a1 + 3);
        break;
      case 0x1098A456:
        if ( *(_DWORD *)(a2 + 4) != 1012174578 || *(_DWORD *)(a2 + 8) != 705789622 || *(_DWORD *)(a2 + 12) != 934095704 )
          goto LABEL_59;
        v5 = (unsigned __int64)(a1 + 2);
        break;
      default:
        if ( *(_DWORD *)a2 != 1639266567
          || *(_DWORD *)(a2 + 4) != 1036916168
          || *(_DWORD *)(a2 + 8) != -1551608134
          || *(_DWORD *)(a2 + 12) != -1355282966 )
        {
          goto LABEL_59;
        }
        v5 = (unsigned __int64)(a1 + 1);
        break;
    }
LABEL_55:
    *a3 = (void *)(v5 & -(__int64)(a1 != 0));
    if ( a1[21] )
    {
      v4 = a1[21];
LABEL_57:
      if ( *(int *)(v4 + 12) >= 0 )
        _InterlockedIncrement((volatile signed __int32 *)(a1[21] + 12LL));
    }
    return 0;
  }
  if ( !*(_DWORD *)(a2 + 4) && *(_DWORD *)(a2 + 8) == 192 && *(_DWORD *)(a2 + 12) == 1174405120 )
  {
    v5 = (unsigned __int64)(a1 + 19);
    goto LABEL_55;
  }
LABEL_59:
  if ( (-(__int64)(a1[22] != 0) & v3) != 0
    && !(unsigned int)__abi_FTMWeakRefData::__abi_QueryInterface(
                        (__abi_FTMWeakRefData *)(v3 & -(__int64)(a1[22] != 0)),
                        (struct Platform::Guid *)a2,
                        a3) )
  {
    return 0;
  }
  return 2147500034LL;
}

```

## disassembly

```asm
0x140020ac0  sub     rsp, 28h
0x140020ac4  cmp     dword ptr [rdx], 0
0x140020ac7  mov     r9, rcx
0x140020aca  jnz     short loc_140020AF1
0x140020acc  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data2
0x140020ad2  cmp     [rdx+4], eax
0x140020ad5  jnz     short loc_140020B43
0x140020ad7  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x140020add  cmp     [rdx+8], eax
0x140020ae0  jnz     short loc_140020B43
0x140020ae2  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4+4
0x140020ae8  cmp     [rdx+0Ch], eax
0x140020aeb  jz      loc_140020B85
0x140020af1  cmp     dword ptr [rdx], 0AF86E2E0h
0x140020af7  jnz     short loc_140020B1A
0x140020af9  mov     eax, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data2
0x140020aff  cmp     [rdx+4], eax
0x140020b02  jnz     short loc_140020B43
0x140020b04  mov     eax, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4
0x140020b0a  cmp     [rdx+8], eax
0x140020b0d  jnz     short loc_140020B43
0x140020b0f  mov     eax, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4+4
0x140020b15  cmp     [rdx+0Ch], eax
0x140020b18  jz      short loc_140020B85
0x140020b1a  cmp     dword ptr [rdx], 2A7EFFFFh
0x140020b20  jnz     short loc_140020B43
0x140020b22  mov     eax, cs:dword_14003B90C
0x140020b28  cmp     [rdx+4], eax
0x140020b2b  jnz     short loc_140020B43
0x140020b2d  mov     eax, cs:dword_14003B910
0x140020b33  cmp     [rdx+8], eax
0x140020b36  jnz     short loc_140020B43
0x140020b38  mov     eax, cs:dword_14003B914
0x140020b3e  cmp     [rdx+0Ch], eax
0x140020b41  jz      short loc_140020B85
0x140020b43  mov     rax, [rcx+0B0h]
0x140020b4a  lea     r10, [rcx+0A8h]
0x140020b51  neg     rax
0x140020b54  sbb     rax, rax
0x140020b57  test    r10, rax
0x140020b5a  jz      short loc_140020BA4
0x140020b5c  cmp     dword ptr [rdx], 94EA2B94h
0x140020b62  jnz     short loc_140020BA4
0x140020b64  mov     eax, cs:dword_140039C6C
0x140020b6a  cmp     [rdx+4], eax
0x140020b6d  jnz     short loc_140020BA4
0x140020b6f  mov     eax, cs:dword_140039C70
0x140020b75  cmp     [rdx+8], eax
0x140020b78  jnz     short loc_140020BA4
0x140020b7a  mov     eax, cs:dword_140039C74
0x140020b80  cmp     [rdx+0Ch], eax
0x140020b83  jnz     short loc_140020BA4
0x140020b85  mov     [r8], r9
0x140020b88  mov     rax, [rcx+0A8h]
0x140020b8f  test    rax, rax
0x140020b92  jz      loc_140020D91
0x140020b98  mov     rax, [rcx+0A8h]
0x140020b9f  jmp     loc_140020D52
0x140020ba4  cmp     dword ptr [rdx], 38h ; '8'
0x140020ba7  jnz     short loc_140020BE2
0x140020ba9  mov     eax, cs:dword_140039C24
0x140020baf  cmp     [rdx+4], eax
0x140020bb2  jnz     loc_140020D66
0x140020bb8  mov     eax, cs:dword_140039C28
0x140020bbe  cmp     [rdx+8], eax
0x140020bc1  jnz     loc_140020D66
0x140020bc7  mov     eax, cs:dword_140039C2C
0x140020bcd  cmp     [rdx+0Ch], eax
0x140020bd0  jnz     loc_140020D66
0x140020bd6  lea     rdx, [rcx+98h]
0x140020bdd  jmp     loc_140020D30
0x140020be2  cmp     dword ptr [rdx], 5A648006h
0x140020be8  jnz     short loc_140020C20
0x140020bea  mov     eax, cs:dword_14003B81C
0x140020bf0  cmp     [rdx+4], eax
0x140020bf3  jnz     loc_140020D66
0x140020bf9  mov     eax, cs:dword_14003B820
0x140020bff  cmp     [rdx+8], eax
0x140020c02  jnz     loc_140020D66
0x140020c08  mov     eax, cs:dword_14003B824
0x140020c0e  cmp     [rdx+0Ch], eax
0x140020c11  jnz     loc_140020D66
0x140020c17  lea     rdx, [rcx+28h]
0x140020c1b  jmp     loc_140020D30
0x140020c20  cmp     dword ptr [rdx], 36h ; '6'
0x140020c23  jnz     short loc_140020C5B
0x140020c25  mov     eax, cs:dword_14003B80C
0x140020c2b  cmp     [rdx+4], eax
0x140020c2e  jnz     loc_140020D66
0x140020c34  mov     eax, cs:dword_14003B810
0x140020c3a  cmp     [rdx+8], eax
0x140020c3d  jnz     loc_140020D66
0x140020c43  mov     eax, cs:dword_14003B814
0x140020c49  cmp     [rdx+0Ch], eax
0x140020c4c  jnz     loc_140020D66
0x140020c52  lea     rdx, [rcx+30h]
0x140020c56  jmp     loc_140020D30
0x140020c5b  cmp     dword ptr [rdx], 867A7A8Eh
0x140020c61  jnz     short loc_140020C99
0x140020c63  mov     eax, cs:dword_14003B94C
0x140020c69  cmp     [rdx+4], eax
0x140020c6c  jnz     loc_140020D66
0x140020c72  mov     eax, cs:dword_14003B950
0x140020c78  cmp     [rdx+8], eax
0x140020c7b  jnz     loc_140020D66
0x140020c81  mov     eax, cs:dword_14003B954
0x140020c87  cmp     [rdx+0Ch], eax
0x140020c8a  jnz     loc_140020D66
0x140020c90  lea     rdx, [rcx+20h]
0x140020c94  jmp     loc_140020D30
0x140020c99  cmp     dword ptr [rdx], 0C74B4D82h
0x140020c9f  jnz     short loc_140020CD4
0x140020ca1  mov     eax, cs:dword_14003B93C
0x140020ca7  cmp     [rdx+4], eax
0x140020caa  jnz     loc_140020D66
0x140020cb0  mov     eax, cs:dword_14003B940
0x140020cb6  cmp     [rdx+8], eax
0x140020cb9  jnz     loc_140020D66
0x140020cbf  mov     eax, cs:dword_14003B944
0x140020cc5  cmp     [rdx+0Ch], eax
0x140020cc8  jnz     loc_140020D66
0x140020cce  lea     rdx, [rcx+18h]
0x140020cd2  jmp     short loc_140020D30
0x140020cd4  cmp     dword ptr [rdx], 1098A456h
0x140020cda  jnz     short loc_140020D03
0x140020cdc  mov     eax, cs:dword_14003B92C
0x140020ce2  cmp     [rdx+4], eax
0x140020ce5  jnz     short loc_140020D66
0x140020ce7  mov     eax, cs:dword_14003B930
0x140020ced  cmp     [rdx+8], eax
0x140020cf0  jnz     short loc_140020D66
0x140020cf2  mov     eax, cs:dword_14003B934
0x140020cf8  cmp     [rdx+0Ch], eax
0x140020cfb  jnz     short loc_140020D66
0x140020cfd  lea     rdx, [rcx+10h]
0x140020d01  jmp     short loc_140020D30
0x140020d03  cmp     dword ptr [rdx], 61B53907h
0x140020d09  jnz     short loc_140020D66
0x140020d0b  mov     eax, cs:dword_14003B91C
0x140020d11  cmp     [rdx+4], eax
0x140020d14  jnz     short loc_140020D66
0x140020d16  mov     eax, cs:dword_14003B920
0x140020d1c  cmp     [rdx+8], eax
0x140020d1f  jnz     short loc_140020D66
0x140020d21  mov     eax, cs:dword_14003B924
0x140020d27  cmp     [rdx+0Ch], eax
0x140020d2a  jnz     short loc_140020D66
0x140020d2c  lea     rdx, [rcx+8]; struct Platform::Guid *
0x140020d30  mov     rax, r9
0x140020d33  neg     rax
0x140020d36  sbb     rcx, rcx
0x140020d39  and     rcx, rdx
0x140020d3c  mov     [r8], rcx
0x140020d3f  mov     rax, [r9+0A8h]
0x140020d46  test    rax, rax
0x140020d49  jz      short loc_140020D91
0x140020d4b  mov     rax, [r9+0A8h]
0x140020d52  mov     ecx, [rax+0Ch]
0x140020d55  test    ecx, ecx
0x140020d57  js      short loc_140020D91
0x140020d59  mov     rax, [r9+0A8h]
0x140020d60  lock inc dword ptr [rax+0Ch]
0x140020d64  jmp     short loc_140020D91
0x140020d66  mov     rax, [rcx+0B0h]
0x140020d6d  neg     rax
0x140020d70  sbb     rax, rax
0x140020d73  test    r10, rax
0x140020d76  jz      short loc_140020D95
0x140020d78  mov     rax, [rcx+0B0h]
0x140020d7f  neg     rax
0x140020d82  sbb     rcx, rcx
0x140020d85  and     rcx, r10; this
0x140020d88  call    ?__abi_QueryInterface@__abi_FTMWeakRefData@@QEAAJAEAVGuid@Platform@@PEAPEAX@Z; __abi_FTMWeakRefData::__abi_QueryInterface(Platform::Guid &,void * *)
0x140020d8d  test    eax, eax
0x140020d8f  jnz     short loc_140020D95
0x140020d91  xor     eax, eax
0x140020d93  jmp     short loc_140020D9A
0x140020d95  mov     eax, 80004002h
0x140020d9a  add     rsp, 28h
0x140020d9e  retn
```
