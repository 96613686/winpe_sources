# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncActionWithProgressCompletedHandler<double>,Microsoft::WRL::FtmBase>::QueryInterface(_GUID const &,void * *)

- ea: `0x180014f70`
- end: `0x18001504d`
- name: `?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$IAsyncActionWithProgressCompletedHandler@N@Foundation@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `221`
- prototype: `__int64 __fastcall(__int64, _DWORD *, __int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180015060`

## callees

- `0x180014f70`
- `0x180023010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncActionWithProgressCompletedHandler<double>,Microsoft::WRL::FtmBase>::QueryInterface(
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
    if ( *a2 == -1797895482
      && a2[1] == *(_DWORD *)&GUID_94d64ac6_4491_53ef_8be8_36481f3ff1e8.Data2
      && a2[2] == *(_DWORD *)GUID_94d64ac6_4491_53ef_8be8_36481f3ff1e8.Data4
      && a2[3] == *(_DWORD *)&GUID_94d64ac6_4491_53ef_8be8_36481f3ff1e8.Data4[4] )
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
0x180014f70  push    rbx
0x180014f72  sub     rsp, 20h
0x180014f76  xor     ebx, ebx
0x180014f78  mov     [r8], rbx
0x180014f7b  cmp     [rdx], ebx
0x180014f7d  jnz     short loc_180014FB4
0x180014f7f  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data2
0x180014f85  cmp     [rdx+4], eax
0x180014f88  jnz     short loc_180014FE2
0x180014f8a  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x180014f90  cmp     [rdx+8], eax
0x180014f93  jnz     short loc_180014FE2
0x180014f95  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4+4
0x180014f9b  cmp     [rdx+0Ch], eax
0x180014f9e  jnz     short loc_180014FE2
0x180014fa0  mov     [r8], rcx
0x180014fa3  mov     rax, [rcx]
0x180014fa6  mov     rax, [rax+8]
0x180014faa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014faf  jmp     loc_180015045
0x180014fb4  cmp     dword ptr [rdx], 94D64AC6h
0x180014fba  jnz     short loc_180014FE2
0x180014fbc  mov     eax, dword ptr cs:_GUID_94d64ac6_4491_53ef_8be8_36481f3ff1e8.Data2
0x180014fc2  cmp     [rdx+4], eax
0x180014fc5  jnz     short loc_180014FE2
0x180014fc7  mov     eax, dword ptr cs:_GUID_94d64ac6_4491_53ef_8be8_36481f3ff1e8.Data4
0x180014fcd  cmp     [rdx+8], eax
0x180014fd0  jnz     short loc_180014FE2
0x180014fd2  mov     eax, dword ptr cs:_GUID_94d64ac6_4491_53ef_8be8_36481f3ff1e8.Data4+4
0x180014fd8  cmp     [rdx+0Ch], eax
0x180014fdb  jnz     short loc_180014FE2
0x180014fdd  mov     [r8], rcx
0x180014fe0  jmp     short loc_180015038
0x180014fe2  add     rcx, 8
0x180014fe6  cmp     dword ptr [rdx], 94EA2B94h
0x180014fec  jnz     short loc_18001500C
0x180014fee  mov     eax, dword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data2
0x180014ff4  cmp     [rdx+4], eax
0x180014ff7  jnz     short loc_180015040
0x180014ff9  mov     eax, dword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4
0x180014fff  cmp     [rdx+8], eax
0x180015002  jnz     short loc_180015040
0x180015004  mov     eax, dword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4+4
0x18001500a  jmp     short loc_18001502D
0x18001500c  cmp     dword ptr [rdx], 3
0x18001500f  jnz     short loc_180015040
0x180015011  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data2
0x180015017  cmp     [rdx+4], eax
0x18001501a  jnz     short loc_180015040
0x18001501c  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data4
0x180015022  cmp     [rdx+8], eax
0x180015025  jnz     short loc_180015040
0x180015027  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data4+4
0x18001502d  cmp     [rdx+0Ch], eax
0x180015030  jnz     short loc_180015040
0x180015032  mov     rax, r8
0x180015035  mov     [rax], rcx
0x180015038  mov     rcx, [r8]
0x18001503b  jmp     loc_180014FA3
0x180015040  mov     ebx, 80004002h
0x180015045  mov     eax, ebx
0x180015047  add     rsp, 20h
0x18001504b  pop     rbx
0x18001504c  retn
```
