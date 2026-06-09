# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Licensing::ProductKeyProperties *>,Microsoft::WRL::FtmBase>::QueryInterface(_GUID const &,void * *)

- ea: `0x180015170`
- end: `0x18001524d`
- name: `?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$IAsyncOperationCompletedHandler@PEAVProductKeyProperties@Licensing@System@Windows@@@Foundation@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `221`
- prototype: `__int64 __fastcall(__int64, _DWORD *, __int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180015260`

## callees

- `0x180015170`
- `0x180023010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Licensing::ProductKeyProperties *>,Microsoft::WRL::FtmBase>::QueryInterface(
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
    if ( *a2 == 1655780520
      && a2[1] == *(_DWORD *)&GUID_62b134a8_8bee_5d02_bb20_b995df455a40.Data2
      && a2[2] == *(_DWORD *)GUID_62b134a8_8bee_5d02_bb20_b995df455a40.Data4
      && a2[3] == *(_DWORD *)&GUID_62b134a8_8bee_5d02_bb20_b995df455a40.Data4[4] )
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
0x180015170  push    rbx
0x180015172  sub     rsp, 20h
0x180015176  xor     ebx, ebx
0x180015178  mov     [r8], rbx
0x18001517b  cmp     [rdx], ebx
0x18001517d  jnz     short loc_1800151B4
0x18001517f  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data2
0x180015185  cmp     [rdx+4], eax
0x180015188  jnz     short loc_1800151E2
0x18001518a  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x180015190  cmp     [rdx+8], eax
0x180015193  jnz     short loc_1800151E2
0x180015195  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4+4
0x18001519b  cmp     [rdx+0Ch], eax
0x18001519e  jnz     short loc_1800151E2
0x1800151a0  mov     [r8], rcx
0x1800151a3  mov     rax, [rcx]
0x1800151a6  mov     rax, [rax+8]
0x1800151aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800151af  jmp     loc_180015245
0x1800151b4  cmp     dword ptr [rdx], 62B134A8h
0x1800151ba  jnz     short loc_1800151E2
0x1800151bc  mov     eax, dword ptr cs:_GUID_62b134a8_8bee_5d02_bb20_b995df455a40.Data2
0x1800151c2  cmp     [rdx+4], eax
0x1800151c5  jnz     short loc_1800151E2
0x1800151c7  mov     eax, dword ptr cs:_GUID_62b134a8_8bee_5d02_bb20_b995df455a40.Data4
0x1800151cd  cmp     [rdx+8], eax
0x1800151d0  jnz     short loc_1800151E2
0x1800151d2  mov     eax, dword ptr cs:_GUID_62b134a8_8bee_5d02_bb20_b995df455a40.Data4+4
0x1800151d8  cmp     [rdx+0Ch], eax
0x1800151db  jnz     short loc_1800151E2
0x1800151dd  mov     [r8], rcx
0x1800151e0  jmp     short loc_180015238
0x1800151e2  add     rcx, 8
0x1800151e6  cmp     dword ptr [rdx], 94EA2B94h
0x1800151ec  jnz     short loc_18001520C
0x1800151ee  mov     eax, dword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data2
0x1800151f4  cmp     [rdx+4], eax
0x1800151f7  jnz     short loc_180015240
0x1800151f9  mov     eax, dword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4
0x1800151ff  cmp     [rdx+8], eax
0x180015202  jnz     short loc_180015240
0x180015204  mov     eax, dword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4+4
0x18001520a  jmp     short loc_18001522D
0x18001520c  cmp     dword ptr [rdx], 3
0x18001520f  jnz     short loc_180015240
0x180015211  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data2
0x180015217  cmp     [rdx+4], eax
0x18001521a  jnz     short loc_180015240
0x18001521c  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data4
0x180015222  cmp     [rdx+8], eax
0x180015225  jnz     short loc_180015240
0x180015227  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data4+4
0x18001522d  cmp     [rdx+0Ch], eax
0x180015230  jnz     short loc_180015240
0x180015232  mov     rax, r8
0x180015235  mov     [rax], rcx
0x180015238  mov     rcx, [r8]
0x18001523b  jmp     loc_1800151A3
0x180015240  mov     ebx, 80004002h
0x180015245  mov     eax, ebx
0x180015247  add     rsp, 20h
0x18001524b  pop     rbx
0x18001524c  retn
```
