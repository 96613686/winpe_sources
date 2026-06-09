# Windows::System::CMemoryManager::QueryInterface(_GUID const &,void * *)

- ea: `0x18000b220`
- end: `0x18000b4a1`
- name: `?QueryInterface@CMemoryManager@System@Windows@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `641`
- prototype: `__int64 __fastcall(Windows::System::CMemoryManager *this, const struct _GUID *, void **)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x180015120`
- `0x180015130`
- `0x180015140`
- `0x180015150`
- `0x180015160`

## callees

- `0x18000b220`
- `0x18000c070`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall Windows::System::CMemoryManager::QueryInterface(
        Windows::System::CMemoryManager *this,
        const struct _GUID *a2,
        void **a3)
{
  unsigned int Data1; // edx
  char *v5; // rcx
  const struct _GUID *v6; // rcx
  void *v7; // r10
  unsigned int v8; // ebx
  int v9; // eax
  __int64 v11; // r10

  *a3 = 0;
  Data1 = a2->Data1;
  if ( Data1 )
  {
    if ( Data1 != -1350114592 )
    {
      if ( Data1 == 53
        && *(_DWORD *)&a2->Data2 == *(_DWORD *)&GUID_00000035_0000_0000_c000_000000000046.Data2
        && *(_DWORD *)a2->Data4 == *(_DWORD *)GUID_00000035_0000_0000_c000_000000000046.Data4
        && *(_DWORD *)&a2->Data4[4] == *(_DWORD *)&GUID_00000035_0000_0000_c000_000000000046.Data4[4] )
      {
        *a3 = this;
        v8 = 0;
        goto LABEL_14;
      }
LABEL_4:
      v5 = (char *)this + 8;
      if ( Data1 == -1796592748 )
      {
        if ( *(_DWORD *)&a2->Data2 == *(_DWORD *)&GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data2
          && *(_DWORD *)a2->Data4 == *(_DWORD *)GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4
          && *(_DWORD *)&a2->Data4[4] == *(_DWORD *)&GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4[4] )
        {
          *a3 = v5;
          v8 = 0;
          goto LABEL_14;
        }
      }
      else if ( Data1 == 3
             && *(_DWORD *)&a2->Data2 == *(_DWORD *)&GUID_00000003_0000_0000_c000_000000000046.Data2
             && *(_DWORD *)a2->Data4 == *(_DWORD *)GUID_00000003_0000_0000_c000_000000000046.Data4
             && *(_DWORD *)&a2->Data4[4] == *(_DWORD *)&GUID_00000003_0000_0000_c000_000000000046.Data4[4] )
      {
        *a3 = v5;
        v8 = 0;
        goto LABEL_14;
      }
      if ( a2->Data1 == 1550591900
        && *(_DWORD *)&a2->Data2 == *(_DWORD *)&GUID_5c6c279c_d7ca_4779_9188_4057219ce64c.Data2
        && *(_DWORD *)a2->Data4 == *(_DWORD *)GUID_5c6c279c_d7ca_4779_9188_4057219ce64c.Data4
        && *(_DWORD *)&a2->Data4[4] == *(_DWORD *)&GUID_5c6c279c_d7ca_4779_9188_4057219ce64c.Data4[4] )
      {
        *a3 = v5 + 32;
        v9 = 0;
        v8 = -2147467262;
      }
      else if ( a2->Data1 == 1861104927
             && *(_DWORD *)&a2->Data2 == *(_DWORD *)&GUID_6eee351f_6d62_423f_9479_b01f9c9f7669.Data2
             && *(_DWORD *)a2->Data4 == *(_DWORD *)GUID_6eee351f_6d62_423f_9479_b01f9c9f7669.Data4
             && *(_DWORD *)&a2->Data4[4] == *(_DWORD *)&GUID_6eee351f_6d62_423f_9479_b01f9c9f7669.Data4[4] )
      {
        *a3 = v5 + 40;
        v9 = 0;
        v8 = -2147467262;
      }
      else
      {
        v8 = -2147467262;
        if ( InlineIsEqualGUID(a2, &GUID_149b59ce_92ad_4e35_89eb_50dfb4c0d91c) )
        {
          *a3 = v7;
          v9 = 0;
        }
        else if ( InlineIsEqualGUID(v6, &GUID_c5a94828_e84e_4886_8a0d_44b3190e3b72) )
        {
          *a3 = (void *)(v11 + 8);
          v9 = 0;
        }
        else
        {
          v9 = -2147467262;
        }
        if ( v9 != -2147467262 )
        {
LABEL_13:
          v8 = v9;
LABEL_14:
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a3 + 8LL))(*a3);
          return v8;
        }
        v9 = -2147467262;
      }
      if ( v9 == -2147467262 )
        return v8;
      goto LABEL_13;
    }
    if ( *(_DWORD *)&a2->Data2 != *(_DWORD *)&GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data2
      || *(_DWORD *)a2->Data4 != *(_DWORD *)GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4
      || *(_DWORD *)&a2->Data4[4] != *(_DWORD *)&GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4[4] )
    {
      goto LABEL_4;
    }
  }
  else if ( *(_DWORD *)&a2->Data2 != *(_DWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data2
         || *(_DWORD *)a2->Data4 != *(_DWORD *)GUID_00000000_0000_0000_c000_000000000046.Data4
         || *(_DWORD *)&a2->Data4[4] != *(_DWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data4[4] )
  {
    goto LABEL_4;
  }
  *a3 = this;
  (*(void (__fastcall **)(Windows::System::CMemoryManager *))(*(_QWORD *)this + 8LL))(this);
  return 0;
}

```

## disassembly

```asm
0x18000b220  push    rbx
0x18000b222  sub     rsp, 20h
0x18000b226  mov     r9, rdx
0x18000b229  mov     qword ptr [r8], 0
0x18000b230  mov     edx, [rdx]
0x18000b232  test    edx, edx
0x18000b234  jz      loc_18000B2D7
0x18000b23a  cmp     edx, 0AF86E2E0h
0x18000b240  jz      loc_18000B31E
0x18000b246  cmp     edx, 35h ; '5'
0x18000b249  jz      loc_18000B350
0x18000b24f  add     rcx, 8
0x18000b253  cmp     edx, 94EA2B94h
0x18000b259  jz      loc_18000B38A
0x18000b25f  cmp     edx, 3
0x18000b262  jz      loc_18000B403
0x18000b268  lea     rdx, [rcx+20h]
0x18000b26c  mov     ecx, [r9]
0x18000b26f  cmp     ecx, 5C6C279Ch
0x18000b275  jz      loc_18000B3C4
0x18000b27b  add     rdx, 8
0x18000b27f  cmp     ecx, 6EEE351Fh
0x18000b285  jz      loc_18000B43D
0x18000b28b  lea     r10, [rdx+8]
0x18000b28f  mov     rcx, r9; struct _GUID *
0x18000b292  lea     rdx, _GUID_149b59ce_92ad_4e35_89eb_50dfb4c0d91c; struct _GUID *
0x18000b299  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x18000b29e  mov     ebx, 80004002h
0x18000b2a3  test    eax, eax
0x18000b2a5  jz      loc_18000B47C
0x18000b2ab  mov     [r8], r10
0x18000b2ae  xor     eax, eax
0x18000b2b0  cmp     eax, ebx
0x18000b2b2  jnz     short loc_18000B2BA
0x18000b2b4  mov     eax, ebx
0x18000b2b6  cmp     eax, ebx
0x18000b2b8  jz      short loc_18000B2CF
0x18000b2ba  mov     ebx, eax
0x18000b2bc  test    ebx, ebx
0x18000b2be  js      short loc_18000B2CF
0x18000b2c0  mov     rcx, [r8]
0x18000b2c3  mov     rax, [rcx]
0x18000b2c6  mov     rax, [rax+8]
0x18000b2ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b2cf  mov     eax, ebx
0x18000b2d1  add     rsp, 20h
0x18000b2d5  pop     rbx
0x18000b2d6  retn
0x18000b2d7  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data2
0x18000b2dd  cmp     [r9+4], eax
0x18000b2e1  jnz     loc_18000B24F
0x18000b2e7  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x18000b2ed  cmp     [r9+8], eax
0x18000b2f1  jnz     loc_18000B24F
0x18000b2f7  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4+4
0x18000b2fd  cmp     [r9+0Ch], eax
0x18000b301  jnz     loc_18000B24F
0x18000b307  mov     [r8], rcx
0x18000b30a  mov     rax, [rcx]
0x18000b30d  mov     rax, [rax+8]
0x18000b311  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b316  xor     eax, eax
0x18000b318  add     rsp, 20h
0x18000b31c  pop     rbx
0x18000b31d  retn
0x18000b31e  mov     eax, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data2
0x18000b324  cmp     [r9+4], eax
0x18000b328  jnz     loc_18000B24F
0x18000b32e  mov     eax, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4
0x18000b334  cmp     [r9+8], eax
0x18000b338  jnz     loc_18000B24F
0x18000b33e  mov     eax, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4+4
0x18000b344  cmp     [r9+0Ch], eax
0x18000b348  jnz     loc_18000B24F
0x18000b34e  jmp     short loc_18000B307
0x18000b350  mov     eax, dword ptr cs:_GUID_00000035_0000_0000_c000_000000000046.Data2
0x18000b356  cmp     [r9+4], eax
0x18000b35a  jnz     loc_18000B24F
0x18000b360  mov     eax, dword ptr cs:_GUID_00000035_0000_0000_c000_000000000046.Data4
0x18000b366  cmp     [r9+8], eax
0x18000b36a  jnz     loc_18000B24F
0x18000b370  mov     eax, dword ptr cs:_GUID_00000035_0000_0000_c000_000000000046.Data4+4
0x18000b376  cmp     [r9+0Ch], eax
0x18000b37a  jnz     loc_18000B24F
0x18000b380  mov     [r8], rcx
0x18000b383  xor     ebx, ebx
0x18000b385  jmp     loc_18000B2C0
0x18000b38a  mov     eax, dword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data2
0x18000b390  cmp     [r9+4], eax
0x18000b394  jnz     loc_18000B268
0x18000b39a  mov     eax, dword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4
0x18000b3a0  cmp     [r9+8], eax
0x18000b3a4  jnz     loc_18000B268
0x18000b3aa  mov     eax, dword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4+4
0x18000b3b0  cmp     [r9+0Ch], eax
0x18000b3b4  jnz     loc_18000B268
0x18000b3ba  mov     [r8], rcx
0x18000b3bd  xor     ebx, ebx
0x18000b3bf  jmp     loc_18000B2BC
0x18000b3c4  mov     eax, dword ptr cs:_GUID_5c6c279c_d7ca_4779_9188_4057219ce64c.Data2
0x18000b3ca  cmp     [r9+4], eax
0x18000b3ce  jnz     loc_18000B27B
0x18000b3d4  mov     eax, dword ptr cs:_GUID_5c6c279c_d7ca_4779_9188_4057219ce64c.Data4
0x18000b3da  cmp     [r9+8], eax
0x18000b3de  jnz     loc_18000B27B
0x18000b3e4  mov     eax, dword ptr cs:_GUID_5c6c279c_d7ca_4779_9188_4057219ce64c.Data4+4
0x18000b3ea  cmp     [r9+0Ch], eax
0x18000b3ee  jnz     loc_18000B27B
0x18000b3f4  mov     [r8], rdx
0x18000b3f7  xor     eax, eax
0x18000b3f9  mov     ebx, 80004002h
0x18000b3fe  jmp     loc_18000B2B6
0x18000b403  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data2
0x18000b409  cmp     [r9+4], eax
0x18000b40d  jnz     loc_18000B268
0x18000b413  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data4
0x18000b419  cmp     [r9+8], eax
0x18000b41d  jnz     loc_18000B268
0x18000b423  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data4+4
0x18000b429  cmp     [r9+0Ch], eax
0x18000b42d  jnz     loc_18000B268
0x18000b433  mov     [r8], rcx
0x18000b436  xor     ebx, ebx
0x18000b438  jmp     loc_18000B2BC
0x18000b43d  mov     eax, dword ptr cs:_GUID_6eee351f_6d62_423f_9479_b01f9c9f7669.Data2
0x18000b443  cmp     [r9+4], eax
0x18000b447  jnz     loc_18000B28B
0x18000b44d  mov     eax, dword ptr cs:_GUID_6eee351f_6d62_423f_9479_b01f9c9f7669.Data4
0x18000b453  cmp     [r9+8], eax
0x18000b457  jnz     loc_18000B28B
0x18000b45d  mov     eax, dword ptr cs:_GUID_6eee351f_6d62_423f_9479_b01f9c9f7669.Data4+4
0x18000b463  cmp     [r9+0Ch], eax
0x18000b467  jnz     loc_18000B28B
0x18000b46d  mov     [r8], rdx
0x18000b470  xor     eax, eax
0x18000b472  mov     ebx, 80004002h
0x18000b477  jmp     loc_18000B2B6
0x18000b47c  lea     rdx, _GUID_c5a94828_e84e_4886_8a0d_44b3190e3b72; struct _GUID *
0x18000b483  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x18000b488  test    eax, eax
0x18000b48a  jz      short loc_18000B49A
0x18000b48c  lea     rax, [r10+8]
0x18000b490  mov     [r8], rax
0x18000b493  xor     eax, eax
0x18000b495  jmp     loc_18000B2B0
0x18000b49a  mov     eax, ebx
0x18000b49c  jmp     loc_18000B2B0
```
