# Microsoft::WRL::Details::RuntimeClassImpl_Microsoft::WRL::RuntimeClassFlags_1__1_1_0_Windows::Foundation::IAsyncOperation_bool__Windows::Internal::AsyncBaseFTM_Windows::Foundation::IAsyncOperationCompletedHandler_bool__1_Microsoft::WRL::AsyncCausalityOptions_&launchForActiveCallAsyncName_&GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2_____::QueryInterface

- ea: `0x18000da10`
- end: `0x18000db90`
- name: `Microsoft::WRL::Details::RuntimeClassImpl_Microsoft::WRL::RuntimeClassFlags_1__1_1_0_Windows::Foundation::IAsyncOperation_bool__Windows::Internal::AsyncBaseFTM_Windows::Foundation::IAsyncOperationCompletedHandler_bool__1_Microsoft::WRL::AsyncCausalityOptions_&launchForActiveCallAsyncName_&GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2_____::QueryInterface`
- size: `384`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000d9d0`
- `0x18000dba0`
- `0x18000dbb0`
- `0x18000dbc0`

## callees

- `0x18000da10`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl_Microsoft::WRL::RuntimeClassFlags_1__1_1_0_Windows::Foundation::IAsyncOperation_bool__Windows::Internal::AsyncBaseFTM_Windows::Foundation::IAsyncOperationCompletedHandler_bool__1_Microsoft::WRL::AsyncCausalityOptions__launchForActiveCallAsyncName__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2_____::QueryInterface(
        __int64 a1,
        _DWORD *a2,
        _QWORD *a3)
{
  int v3; // eax
  int v4; // ebx
  __int64 v5; // rcx
  __int64 v6; // rcx
  int v7; // eax
  int v8; // eax

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
      if ( *a2 == 54
        && a2[1] == *(_DWORD *)&GUID_00000036_0000_0000_c000_000000000046.Data2
        && a2[2] == *(_DWORD *)GUID_00000036_0000_0000_c000_000000000046.Data4
        && a2[3] == *(_DWORD *)&GUID_00000036_0000_0000_c000_000000000046.Data4[4] )
      {
        *a3 = v5;
        v4 = 0;
        goto LABEL_38;
      }
      v6 = v5 + 80;
      v4 = -2147467262;
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
        *a3 = v6;
        v8 = 0;
        goto LABEL_36;
      }
LABEL_35:
      v8 = -2147467262;
LABEL_36:
      if ( v8 != -2147467262 )
        v4 = v8;
LABEL_38:
      if ( v4 < 0 )
        return (unsigned int)v4;
LABEL_39:
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a3 + 8LL))(*a3);
      return (unsigned int)v4;
    }
LABEL_15:
    *a3 = a1;
    v4 = 0;
    goto LABEL_39;
  }
  if ( *a2 != -1350114592 )
  {
    if ( *a2 == -843714637
      && a2[1] == *(_DWORD *)&GUID_cdb5efb3_5788_509d_9be1_71ccb8a3362a.Data2
      && a2[2] == *(_DWORD *)GUID_cdb5efb3_5788_509d_9be1_71ccb8a3362a.Data4
      && a2[3] == *(_DWORD *)&GUID_cdb5efb3_5788_509d_9be1_71ccb8a3362a.Data4[4] )
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
0x18000da10  push    rbx
0x18000da12  sub     rsp, 20h
0x18000da16  mov     qword ptr [r8], 0
0x18000da1d  cmp     dword ptr [rdx], 0
0x18000da20  jnz     short loc_18000DA44
0x18000da22  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data2
0x18000da28  cmp     [rdx+4], eax
0x18000da2b  jnz     loc_18000DAB6
0x18000da31  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x18000da37  cmp     [rdx+8], eax
0x18000da3a  jnz     short loc_18000DAB6
0x18000da3c  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4+4
0x18000da42  jmp     short loc_18000DA68
0x18000da44  cmp     dword ptr [rdx], 0AF86E2E0h
0x18000da4a  jnz     short loc_18000DA83
0x18000da4c  mov     eax, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data2
0x18000da52  cmp     [rdx+4], eax
0x18000da55  jnz     short loc_18000DAB6
0x18000da57  mov     eax, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4
0x18000da5d  cmp     [rdx+8], eax
0x18000da60  jnz     short loc_18000DAB6
0x18000da62  mov     eax, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4+4
0x18000da68  cmp     [rdx+0Ch], eax
0x18000da6b  jnz     short loc_18000DAB6
0x18000da6d  mov     [r8], rcx
0x18000da70  mov     rax, [rcx]
0x18000da73  mov     rax, [rax+8]
0x18000da77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da7c  xor     ebx, ebx
0x18000da7e  jmp     loc_18000DB88
0x18000da83  cmp     dword ptr [rdx], 0CDB5EFB3h
0x18000da89  jnz     short loc_18000DAB6
0x18000da8b  mov     eax, dword ptr cs:_GUID_cdb5efb3_5788_509d_9be1_71ccb8a3362a.Data2
0x18000da91  cmp     [rdx+4], eax
0x18000da94  jnz     short loc_18000DAB6
0x18000da96  mov     eax, dword ptr cs:_GUID_cdb5efb3_5788_509d_9be1_71ccb8a3362a.Data4
0x18000da9c  cmp     [rdx+8], eax
0x18000da9f  jnz     short loc_18000DAB6
0x18000daa1  mov     eax, dword ptr cs:_GUID_cdb5efb3_5788_509d_9be1_71ccb8a3362a.Data4+4
0x18000daa7  cmp     [rdx+0Ch], eax
0x18000daaa  jnz     short loc_18000DAB6
0x18000daac  mov     [r8], rcx
0x18000daaf  xor     ebx, ebx
0x18000dab1  jmp     loc_18000DB79
0x18000dab6  add     rcx, 8
0x18000daba  cmp     dword ptr [rdx], 38h ; '8'
0x18000dabd  jnz     short loc_18000DAE0
0x18000dabf  mov     eax, dword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data2
0x18000dac5  cmp     [rdx+4], eax
0x18000dac8  jnz     short loc_18000DAE0
0x18000daca  mov     eax, dword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data4
0x18000dad0  cmp     [rdx+8], eax
0x18000dad3  jnz     short loc_18000DAE0
0x18000dad5  mov     eax, dword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data4+4
0x18000dadb  cmp     [rdx+0Ch], eax
0x18000dade  jz      short loc_18000DAAC
0x18000dae0  add     rcx, 8
0x18000dae4  cmp     dword ptr [rdx], 36h ; '6'
0x18000dae7  jnz     short loc_18000DB11
0x18000dae9  mov     eax, dword ptr cs:_GUID_00000036_0000_0000_c000_000000000046.Data2
0x18000daef  cmp     [rdx+4], eax
0x18000daf2  jnz     short loc_18000DB11
0x18000daf4  mov     eax, dword ptr cs:_GUID_00000036_0000_0000_c000_000000000046.Data4
0x18000dafa  cmp     [rdx+8], eax
0x18000dafd  jnz     short loc_18000DB11
0x18000daff  mov     eax, dword ptr cs:_GUID_00000036_0000_0000_c000_000000000046.Data4+4
0x18000db05  cmp     [rdx+0Ch], eax
0x18000db08  jnz     short loc_18000DB11
0x18000db0a  mov     [r8], rcx
0x18000db0d  xor     ebx, ebx
0x18000db0f  jmp     short loc_18000DB75
0x18000db11  add     rcx, 50h ; 'P'
0x18000db15  mov     ebx, 80004002h
0x18000db1a  cmp     dword ptr [rdx], 94EA2B94h
0x18000db20  jnz     short loc_18000DB40
0x18000db22  mov     eax, dword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data2
0x18000db28  cmp     [rdx+4], eax
0x18000db2b  jnz     short loc_18000DB6D
0x18000db2d  mov     eax, dword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4
0x18000db33  cmp     [rdx+8], eax
0x18000db36  jnz     short loc_18000DB6D
0x18000db38  mov     eax, dword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4+4
0x18000db3e  jmp     short loc_18000DB61
0x18000db40  cmp     dword ptr [rdx], 3
0x18000db43  jnz     short loc_18000DB6D
0x18000db45  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data2
0x18000db4b  cmp     [rdx+4], eax
0x18000db4e  jnz     short loc_18000DB6D
0x18000db50  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data4
0x18000db56  cmp     [rdx+8], eax
0x18000db59  jnz     short loc_18000DB6D
0x18000db5b  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data4+4
0x18000db61  cmp     [rdx+0Ch], eax
0x18000db64  jnz     short loc_18000DB6D
0x18000db66  mov     [r8], rcx
0x18000db69  xor     eax, eax
0x18000db6b  jmp     short loc_18000DB6F
0x18000db6d  mov     eax, ebx
0x18000db6f  cmp     eax, ebx
0x18000db71  jz      short loc_18000DB75
0x18000db73  mov     ebx, eax
0x18000db75  test    ebx, ebx
0x18000db77  js      short loc_18000DB88
0x18000db79  mov     rcx, [r8]
0x18000db7c  mov     rdx, [rcx]
0x18000db7f  mov     rax, [rdx+8]
0x18000db83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db88  mov     eax, ebx
0x18000db8a  add     rsp, 20h
0x18000db8e  pop     rbx
0x18000db8f  retn
```
