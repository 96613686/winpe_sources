# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<int>,Microsoft::WRL::FtmBase>::QueryInterface(_GUID const &,void * *)

- ea: `0x180015070`
- end: `0x18001514d`
- name: `?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$IAsyncOperationCompletedHandler@H@Foundation@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `221`
- prototype: `__int64 __fastcall(__int64, _DWORD *, __int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180015160`

## callees

- `0x180015070`
- `0x180023010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<int>,Microsoft::WRL::FtmBase>::QueryInterface(
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
    if ( *a2 == -703811939
      && a2[1] == *(_DWORD *)&GUID_d60cae9d_88cb_59f1_8576_3fba44796be8.Data2
      && a2[2] == *(_DWORD *)GUID_d60cae9d_88cb_59f1_8576_3fba44796be8.Data4
      && a2[3] == *(_DWORD *)&GUID_d60cae9d_88cb_59f1_8576_3fba44796be8.Data4[4] )
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
0x180015070  push    rbx
0x180015072  sub     rsp, 20h
0x180015076  xor     ebx, ebx
0x180015078  mov     [r8], rbx
0x18001507b  cmp     [rdx], ebx
0x18001507d  jnz     short loc_1800150B4
0x18001507f  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data2
0x180015085  cmp     [rdx+4], eax
0x180015088  jnz     short loc_1800150E2
0x18001508a  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x180015090  cmp     [rdx+8], eax
0x180015093  jnz     short loc_1800150E2
0x180015095  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4+4
0x18001509b  cmp     [rdx+0Ch], eax
0x18001509e  jnz     short loc_1800150E2
0x1800150a0  mov     [r8], rcx
0x1800150a3  mov     rax, [rcx]
0x1800150a6  mov     rax, [rax+8]
0x1800150aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800150af  jmp     loc_180015145
0x1800150b4  cmp     dword ptr [rdx], 0D60CAE9Dh
0x1800150ba  jnz     short loc_1800150E2
0x1800150bc  mov     eax, dword ptr cs:_GUID_d60cae9d_88cb_59f1_8576_3fba44796be8.Data2
0x1800150c2  cmp     [rdx+4], eax
0x1800150c5  jnz     short loc_1800150E2
0x1800150c7  mov     eax, dword ptr cs:_GUID_d60cae9d_88cb_59f1_8576_3fba44796be8.Data4
0x1800150cd  cmp     [rdx+8], eax
0x1800150d0  jnz     short loc_1800150E2
0x1800150d2  mov     eax, dword ptr cs:_GUID_d60cae9d_88cb_59f1_8576_3fba44796be8.Data4+4
0x1800150d8  cmp     [rdx+0Ch], eax
0x1800150db  jnz     short loc_1800150E2
0x1800150dd  mov     [r8], rcx
0x1800150e0  jmp     short loc_180015138
0x1800150e2  add     rcx, 8
0x1800150e6  cmp     dword ptr [rdx], 94EA2B94h
0x1800150ec  jnz     short loc_18001510C
0x1800150ee  mov     eax, dword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data2
0x1800150f4  cmp     [rdx+4], eax
0x1800150f7  jnz     short loc_180015140
0x1800150f9  mov     eax, dword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4
0x1800150ff  cmp     [rdx+8], eax
0x180015102  jnz     short loc_180015140
0x180015104  mov     eax, dword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4+4
0x18001510a  jmp     short loc_18001512D
0x18001510c  cmp     dword ptr [rdx], 3
0x18001510f  jnz     short loc_180015140
0x180015111  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data2
0x180015117  cmp     [rdx+4], eax
0x18001511a  jnz     short loc_180015140
0x18001511c  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data4
0x180015122  cmp     [rdx+8], eax
0x180015125  jnz     short loc_180015140
0x180015127  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data4+4
0x18001512d  cmp     [rdx+0Ch], eax
0x180015130  jnz     short loc_180015140
0x180015132  mov     rax, r8
0x180015135  mov     [rax], rcx
0x180015138  mov     rcx, [r8]
0x18001513b  jmp     loc_1800150A3
0x180015140  mov     ebx, 80004002h
0x180015145  mov     eax, ebx
0x180015147  add     rsp, 20h
0x18001514b  pop     rbx
0x18001514c  retn
```
