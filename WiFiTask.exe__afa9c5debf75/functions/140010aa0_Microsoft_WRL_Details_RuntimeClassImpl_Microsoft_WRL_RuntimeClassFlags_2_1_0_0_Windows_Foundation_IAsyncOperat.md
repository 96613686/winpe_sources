# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::FtmBase>::QueryInterface(_GUID const &,void * *)

- ea: `0x140010aa0`
- end: `0x140010b7d`
- name: `?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `221`
- prototype: `__int64 __fastcall(__int64, _DWORD *, __int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140010b90`

## callees

- `0x140010aa0`
- `0x140012010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::FtmBase>::QueryInterface(
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
    if ( *a2 == -1043082846
      && a2[1] == *(_DWORD *)&GUID_c1d3d1a2_ae17_5a5f_b5a2_bdcc8844889a.Data2
      && a2[2] == *(_DWORD *)GUID_c1d3d1a2_ae17_5a5f_b5a2_bdcc8844889a.Data4
      && a2[3] == *(_DWORD *)&GUID_c1d3d1a2_ae17_5a5f_b5a2_bdcc8844889a.Data4[4] )
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
0x140010aa0  push    rbx
0x140010aa2  sub     rsp, 20h
0x140010aa6  xor     ebx, ebx
0x140010aa8  mov     [r8], rbx
0x140010aab  cmp     [rdx], ebx
0x140010aad  jnz     short loc_140010AE4
0x140010aaf  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data2
0x140010ab5  cmp     [rdx+4], eax
0x140010ab8  jnz     short loc_140010B12
0x140010aba  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x140010ac0  cmp     [rdx+8], eax
0x140010ac3  jnz     short loc_140010B12
0x140010ac5  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4+4
0x140010acb  cmp     [rdx+0Ch], eax
0x140010ace  jnz     short loc_140010B12
0x140010ad0  mov     [r8], rcx
0x140010ad3  mov     rax, [rcx]
0x140010ad6  mov     rax, [rax+8]
0x140010ada  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010adf  jmp     loc_140010B75
0x140010ae4  cmp     dword ptr [rdx], 0C1D3D1A2h
0x140010aea  jnz     short loc_140010B12
0x140010aec  mov     eax, dword ptr cs:_GUID_c1d3d1a2_ae17_5a5f_b5a2_bdcc8844889a.Data2
0x140010af2  cmp     [rdx+4], eax
0x140010af5  jnz     short loc_140010B12
0x140010af7  mov     eax, dword ptr cs:_GUID_c1d3d1a2_ae17_5a5f_b5a2_bdcc8844889a.Data4
0x140010afd  cmp     [rdx+8], eax
0x140010b00  jnz     short loc_140010B12
0x140010b02  mov     eax, dword ptr cs:_GUID_c1d3d1a2_ae17_5a5f_b5a2_bdcc8844889a.Data4+4
0x140010b08  cmp     [rdx+0Ch], eax
0x140010b0b  jnz     short loc_140010B12
0x140010b0d  mov     [r8], rcx
0x140010b10  jmp     short loc_140010B68
0x140010b12  add     rcx, 8
0x140010b16  cmp     dword ptr [rdx], 94EA2B94h
0x140010b1c  jnz     short loc_140010B3C
0x140010b1e  mov     eax, dword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data2
0x140010b24  cmp     [rdx+4], eax
0x140010b27  jnz     short loc_140010B70
0x140010b29  mov     eax, dword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4
0x140010b2f  cmp     [rdx+8], eax
0x140010b32  jnz     short loc_140010B70
0x140010b34  mov     eax, dword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4+4
0x140010b3a  jmp     short loc_140010B5D
0x140010b3c  cmp     dword ptr [rdx], 3
0x140010b3f  jnz     short loc_140010B70
0x140010b41  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data2
0x140010b47  cmp     [rdx+4], eax
0x140010b4a  jnz     short loc_140010B70
0x140010b4c  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data4
0x140010b52  cmp     [rdx+8], eax
0x140010b55  jnz     short loc_140010B70
0x140010b57  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data4+4
0x140010b5d  cmp     [rdx+0Ch], eax
0x140010b60  jnz     short loc_140010B70
0x140010b62  mov     rax, r8
0x140010b65  mov     [rax], rcx
0x140010b68  mov     rcx, [r8]
0x140010b6b  jmp     loc_140010AD3
0x140010b70  mov     ebx, 80004002h
0x140010b75  mov     eax, ebx
0x140010b77  add     rsp, 20h
0x140010b7b  pop     rbx
0x140010b7c  retn
```
