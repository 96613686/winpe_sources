# Concurrency::details::_AsyncTaskGeneratorThunk__lambda_012995b310defc0ef83a366488a71671___::[Platform::Object]::__abi_QueryInterface

- ea: `0x140020670`
- end: `0x1400209b6`
- name: `Concurrency::details::_AsyncTaskGeneratorThunk__lambda_012995b310defc0ef83a366488a71671___::[Platform::Object]::__abi_QueryInterface`
- size: `838`
- prototype: ``
- caller_count: `12`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x1400209c0`
- `0x1400209d0`
- `0x1400209e0`
- `0x1400209f0`
- `0x140020a00`
- `0x140020a10`
- `0x140020a20`
- `0x140020a30`
- `0x140020a40`
- `0x140020a60`
- `0x140020a80`
- `0x140020aa0`

## callees

- `0x140008470`
- `0x140020670`
- `0x140020ac0`

## pseudocode

```c
__int64 __fastcall Concurrency::details::_AsyncTaskGeneratorThunk__lambda_012995b310defc0ef83a366488a71671___::_Platform::Object_::__abi_QueryInterface(
        _QWORD *a1,
        __int64 a2,
        void **a3)
{
  unsigned __int64 v6; // rdx
  __int64 v7; // rax
  unsigned __int64 v8; // rdx

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
  if ( *(_DWORD *)a2 == 1101930199
    && *(_DWORD *)(a2 + 4) == 1021442379
    && *(_DWORD *)(a2 + 8) == 1693275798
    && *(_DWORD *)(a2 + 12) == -442324011 )
  {
LABEL_18:
    *a3 = a1;
    if ( a1[22] )
    {
      v7 = a1[22];
      goto LABEL_62;
    }
    return 0;
  }
LABEL_13:
  v6 = (unsigned __int64)(a1 + 22);
  if ( (-(__int64)(a1[23] != 0) & (unsigned __int64)(a1 + 22)) != 0
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
          goto LABEL_64;
        v8 = (unsigned __int64)(a1 + 6);
        break;
      case 0x36:
        if ( *(_DWORD *)(a2 + 4) || *(_DWORD *)(a2 + 8) != 192 || *(_DWORD *)(a2 + 12) != 1174405120 )
          goto LABEL_64;
        v8 = (unsigned __int64)(a1 + 7);
        break;
      case 0x867A7A8E:
        if ( *(_DWORD *)(a2 + 4) != 954167318 || *(_DWORD *)(a2 + 8) != -1350084429 || *(_DWORD *)(a2 + 12) != 466931300 )
          goto LABEL_64;
        v8 = (unsigned __int64)(a1 + 5);
        break;
      case 0xC74B4D82:
        if ( *(_DWORD *)(a2 + 4) != 885402115 || *(_DWORD *)(a2 + 8) != -457647979 || *(_DWORD *)(a2 + 12) != 99325659 )
          goto LABEL_64;
        v8 = (unsigned __int64)(a1 + 4);
        break;
      case 0x1098A456:
        if ( *(_DWORD *)(a2 + 4) != 1012174578 || *(_DWORD *)(a2 + 8) != 705789622 || *(_DWORD *)(a2 + 12) != 934095704 )
          goto LABEL_64;
        v8 = (unsigned __int64)(a1 + 3);
        break;
      case 0x61B53907:
        if ( *(_DWORD *)(a2 + 4) != 1036916168
          || *(_DWORD *)(a2 + 8) != -1551608134
          || *(_DWORD *)(a2 + 12) != -1355282966 )
        {
          goto LABEL_64;
        }
        v8 = (unsigned __int64)(a1 + 2);
        break;
      default:
        if ( *(_DWORD *)a2 != 712966143
          || *(_DWORD *)(a2 + 4) != 873057582
          || *(_DWORD *)(a2 + 8) != 207100334
          || *(_DWORD *)(a2 + 12) != -10681234 )
        {
          goto LABEL_64;
        }
        v8 = (unsigned __int64)(a1 + 1);
        break;
    }
LABEL_60:
    *a3 = (void *)(v8 & -(__int64)(a1 != 0));
    if ( a1[22] )
    {
      v7 = a1[22];
LABEL_62:
      if ( *(int *)(v7 + 12) >= 0 )
        _InterlockedIncrement((volatile signed __int32 *)(a1[22] + 12LL));
    }
    return 0;
  }
  if ( !*(_DWORD *)(a2 + 4) && *(_DWORD *)(a2 + 8) == 192 && *(_DWORD *)(a2 + 12) == 1174405120 )
  {
    v8 = (unsigned __int64)(a1 + 25);
    goto LABEL_60;
  }
LABEL_64:
  if ( (-(__int64)(a1[23] != 0) & v6) != 0
    && !(unsigned int)__abi_FTMWeakRefData::__abi_QueryInterface(
                        (__abi_FTMWeakRefData *)(v6 & -(__int64)(a1[23] != 0)),
                        (struct Platform::Guid *)a2,
                        a3) )
  {
    return 0;
  }
  return Concurrency::details::_AsyncTaskThunk_Concurrency::details::_AsyncAttributes__lambda_012995b310defc0ef83a366488a71671__void_void_Concurrency::details::_TaskTypeTraits_void_0__0_0___::_Platform::Object_::__abi_QueryInterface(
           a1 + 1,
           a2,
           a3);
}

```

## disassembly

```asm
0x140020670  mov     [rsp+arg_0], rbx
0x140020675  mov     [rsp+arg_8], rsi
0x14002067a  push    rdi
0x14002067b  sub     rsp, 20h
0x14002067f  cmp     dword ptr [rdx], 0
0x140020682  mov     rsi, r8
0x140020685  mov     rdi, rdx
0x140020688  mov     rbx, rcx
0x14002068b  jnz     short loc_1400206B2
0x14002068d  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data2
0x140020693  cmp     [rdx+4], eax
0x140020696  jnz     short loc_140020704
0x140020698  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x14002069e  cmp     [rdx+8], eax
0x1400206a1  jnz     short loc_140020704
0x1400206a3  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4+4
0x1400206a9  cmp     [rdx+0Ch], eax
0x1400206ac  jz      loc_140020746
0x1400206b2  cmp     dword ptr [rdx], 0AF86E2E0h
0x1400206b8  jnz     short loc_1400206DB
0x1400206ba  mov     eax, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data2
0x1400206c0  cmp     [rdx+4], eax
0x1400206c3  jnz     short loc_140020704
0x1400206c5  mov     eax, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4
0x1400206cb  cmp     [rdx+8], eax
0x1400206ce  jnz     short loc_140020704
0x1400206d0  mov     eax, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4+4
0x1400206d6  cmp     [rdx+0Ch], eax
0x1400206d9  jz      short loc_140020746
0x1400206db  cmp     dword ptr [rdx], 41AE1ED7h
0x1400206e1  jnz     short loc_140020704
0x1400206e3  mov     eax, cs:dword_14003B8FC
0x1400206e9  cmp     [rdx+4], eax
0x1400206ec  jnz     short loc_140020704
0x1400206ee  mov     eax, cs:dword_14003B900
0x1400206f4  cmp     [rdx+8], eax
0x1400206f7  jnz     short loc_140020704
0x1400206f9  mov     eax, cs:dword_14003B904
0x1400206ff  cmp     [rdx+0Ch], eax
0x140020702  jz      short loc_140020746
0x140020704  mov     rax, [rcx+0B8h]
0x14002070b  lea     rdx, [rcx+0B0h]
0x140020712  neg     rax
0x140020715  sbb     rax, rax
0x140020718  test    rdx, rax
0x14002071b  jz      short loc_140020765
0x14002071d  cmp     dword ptr [rdi], 94EA2B94h
0x140020723  jnz     short loc_140020765
0x140020725  mov     eax, cs:dword_140039C6C
0x14002072b  cmp     [rdi+4], eax
0x14002072e  jnz     short loc_140020765
0x140020730  mov     eax, cs:dword_140039C70
0x140020736  cmp     [rdi+8], eax
0x140020739  jnz     short loc_140020765
0x14002073b  mov     eax, cs:dword_140039C74
0x140020741  cmp     [rdi+0Ch], eax
0x140020744  jnz     short loc_140020765
0x140020746  mov     [r8], rbx
0x140020749  mov     rax, [rcx+0B0h]
0x140020750  test    rax, rax
0x140020753  jz      loc_140020993
0x140020759  mov     rax, [rcx+0B0h]
0x140020760  jmp     loc_140020951
0x140020765  cmp     dword ptr [rdi], 38h ; '8'
0x140020768  jnz     short loc_1400207A3
0x14002076a  mov     eax, cs:dword_140039C24
0x140020770  cmp     [rdi+4], eax
0x140020773  jnz     loc_140020965
0x140020779  mov     eax, cs:dword_140039C28
0x14002077f  cmp     [rdi+8], eax
0x140020782  jnz     loc_140020965
0x140020788  mov     eax, cs:dword_140039C2C
0x14002078e  cmp     [rdi+0Ch], eax
0x140020791  jnz     loc_140020965
0x140020797  lea     rdx, [rcx+0C8h]
0x14002079e  jmp     loc_14002092F
0x1400207a3  cmp     dword ptr [rdi], 5A648006h
0x1400207a9  jnz     short loc_1400207E1
0x1400207ab  mov     eax, cs:dword_14003B81C
0x1400207b1  cmp     [rdi+4], eax
0x1400207b4  jnz     loc_140020965
0x1400207ba  mov     eax, cs:dword_14003B820
0x1400207c0  cmp     [rdi+8], eax
0x1400207c3  jnz     loc_140020965
0x1400207c9  mov     eax, cs:dword_14003B824
0x1400207cf  cmp     [rdi+0Ch], eax
0x1400207d2  jnz     loc_140020965
0x1400207d8  lea     rdx, [rcx+30h]
0x1400207dc  jmp     loc_14002092F
0x1400207e1  cmp     dword ptr [rdi], 36h ; '6'
0x1400207e4  jnz     short loc_14002081C
0x1400207e6  mov     eax, cs:dword_14003B80C
0x1400207ec  cmp     [rdi+4], eax
0x1400207ef  jnz     loc_140020965
0x1400207f5  mov     eax, cs:dword_14003B810
0x1400207fb  cmp     [rdi+8], eax
0x1400207fe  jnz     loc_140020965
0x140020804  mov     eax, cs:dword_14003B814
0x14002080a  cmp     [rdi+0Ch], eax
0x14002080d  jnz     loc_140020965
0x140020813  lea     rdx, [rcx+38h]
0x140020817  jmp     loc_14002092F
0x14002081c  cmp     dword ptr [rdi], 867A7A8Eh
0x140020822  jnz     short loc_14002085A
0x140020824  mov     eax, cs:dword_14003B94C
0x14002082a  cmp     [rdi+4], eax
0x14002082d  jnz     loc_140020965
0x140020833  mov     eax, cs:dword_14003B950
0x140020839  cmp     [rdi+8], eax
0x14002083c  jnz     loc_140020965
0x140020842  mov     eax, cs:dword_14003B954
0x140020848  cmp     [rdi+0Ch], eax
0x14002084b  jnz     loc_140020965
0x140020851  lea     rdx, [rcx+28h]
0x140020855  jmp     loc_14002092F
0x14002085a  cmp     dword ptr [rdi], 0C74B4D82h
0x140020860  jnz     short loc_140020898
0x140020862  mov     eax, cs:dword_14003B93C
0x140020868  cmp     [rdi+4], eax
0x14002086b  jnz     loc_140020965
0x140020871  mov     eax, cs:dword_14003B940
0x140020877  cmp     [rdi+8], eax
0x14002087a  jnz     loc_140020965
0x140020880  mov     eax, cs:dword_14003B944
0x140020886  cmp     [rdi+0Ch], eax
0x140020889  jnz     loc_140020965
0x14002088f  lea     rdx, [rcx+20h]
0x140020893  jmp     loc_14002092F
0x140020898  cmp     dword ptr [rdi], 1098A456h
0x14002089e  jnz     short loc_1400208D3
0x1400208a0  mov     eax, cs:dword_14003B92C
0x1400208a6  cmp     [rdi+4], eax
0x1400208a9  jnz     loc_140020965
0x1400208af  mov     eax, cs:dword_14003B930
0x1400208b5  cmp     [rdi+8], eax
0x1400208b8  jnz     loc_140020965
0x1400208be  mov     eax, cs:dword_14003B934
0x1400208c4  cmp     [rdi+0Ch], eax
0x1400208c7  jnz     loc_140020965
0x1400208cd  lea     rdx, [rcx+18h]
0x1400208d1  jmp     short loc_14002092F
0x1400208d3  cmp     dword ptr [rdi], 61B53907h
0x1400208d9  jnz     short loc_140020902
0x1400208db  mov     eax, cs:dword_14003B91C
0x1400208e1  cmp     [rdi+4], eax
0x1400208e4  jnz     short loc_140020965
0x1400208e6  mov     eax, cs:dword_14003B920
0x1400208ec  cmp     [rdi+8], eax
0x1400208ef  jnz     short loc_140020965
0x1400208f1  mov     eax, cs:dword_14003B924
0x1400208f7  cmp     [rdi+0Ch], eax
0x1400208fa  jnz     short loc_140020965
0x1400208fc  lea     rdx, [rcx+10h]
0x140020900  jmp     short loc_14002092F
0x140020902  cmp     dword ptr [rdi], 2A7EFFFFh
0x140020908  jnz     short loc_140020965
0x14002090a  mov     eax, cs:dword_14003B90C
0x140020910  cmp     [rdi+4], eax
0x140020913  jnz     short loc_140020965
0x140020915  mov     eax, cs:dword_14003B910
0x14002091b  cmp     [rdi+8], eax
0x14002091e  jnz     short loc_140020965
0x140020920  mov     eax, cs:dword_14003B914
0x140020926  cmp     [rdi+0Ch], eax
0x140020929  jnz     short loc_140020965
0x14002092b  lea     rdx, [rcx+8]
0x14002092f  mov     rax, rbx
0x140020932  neg     rax
0x140020935  sbb     rcx, rcx
0x140020938  and     rcx, rdx
0x14002093b  mov     [r8], rcx
0x14002093e  mov     rax, [rbx+0B0h]
0x140020945  test    rax, rax
0x140020948  jz      short loc_140020993
0x14002094a  mov     rax, [rbx+0B0h]
0x140020951  mov     ecx, [rax+0Ch]
0x140020954  test    ecx, ecx
0x140020956  js      short loc_140020993
0x140020958  mov     rax, [rbx+0B0h]
0x14002095f  lock inc dword ptr [rax+0Ch]
0x140020963  jmp     short loc_140020993
0x140020965  mov     rax, [rcx+0B8h]
0x14002096c  neg     rax
0x14002096f  sbb     rax, rax
0x140020972  test    rdx, rax
0x140020975  jz      short loc_140020997
0x140020977  mov     rax, [rcx+0B8h]
0x14002097e  neg     rax
0x140020981  sbb     rcx, rcx
0x140020984  and     rcx, rdx; this
0x140020987  mov     rdx, rdi; struct Platform::Guid *
0x14002098a  call    ?__abi_QueryInterface@__abi_FTMWeakRefData@@QEAAJAEAVGuid@Platform@@PEAPEAX@Z; __abi_FTMWeakRefData::__abi_QueryInterface(Platform::Guid &,void * *)
0x14002098f  test    eax, eax
0x140020991  jnz     short loc_140020997
0x140020993  xor     eax, eax
0x140020995  jmp     short loc_1400209A6
0x140020997  lea     rcx, [rbx+8]
0x14002099b  mov     r8, rsi
0x14002099e  mov     rdx, rdi
0x1400209a1  call    Concurrency__details___AsyncTaskThunk_Concurrency__details___AsyncAttributes__lambda_012995b310defc0ef83a366488a71671__void_void_Concurrency__details___TaskTypeTraits_void_0__0_0______Platform__Object_____abi_QueryInterface
0x1400209a6  mov     rbx, [rsp+28h+arg_0]
0x1400209ab  mov     rsi, [rsp+28h+arg_8]
0x1400209b0  add     rsp, 20h
0x1400209b4  pop     rdi
0x1400209b5  retn
```
