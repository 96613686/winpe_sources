# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enumeration::DeviceInformation *>,Microsoft::WRL::FtmBase>::QueryInterface(_GUID const &,void * *)

- ea: `0x180006970`
- end: `0x180006a4e`
- name: `?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$IAsyncOperationCompletedHandler@PEAVDeviceInformation@Enumeration@Devices@Windows@@@Foundation@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `222`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180006a60`

## callees

- `0x180006970`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enumeration::DeviceInformation *>,Microsoft::WRL::FtmBase>::QueryInterface(
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
    if ( *a2 == -1152893454
      && a2[1] == *(_DWORD *)&GUID_bb483df2_7bb6_5923_a28d_8342ec30046b.Data2
      && a2[2] == *(_DWORD *)GUID_bb483df2_7bb6_5923_a28d_8342ec30046b.Data4
      && a2[3] == *(_DWORD *)&GUID_bb483df2_7bb6_5923_a28d_8342ec30046b.Data4[4] )
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
0x180006970  push    rbx
0x180006972  sub     rsp, 20h
0x180006976  xor     ebx, ebx
0x180006978  mov     [r8], rbx
0x18000697b  cmp     [rdx], ebx
0x18000697d  jnz     short loc_1800069B4
0x18000697f  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data2
0x180006985  cmp     [rdx+4], eax
0x180006988  jnz     short loc_1800069E2
0x18000698a  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x180006990  cmp     [rdx+8], eax
0x180006993  jnz     short loc_1800069E2
0x180006995  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4+4
0x18000699b  cmp     [rdx+0Ch], eax
0x18000699e  jnz     short loc_1800069E2
0x1800069a0  mov     [r8], rcx
0x1800069a3  mov     rax, [rcx]
0x1800069a6  mov     rax, [rax+8]
0x1800069aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069af  jmp     loc_180006A45
0x1800069b4  cmp     dword ptr [rdx], 0BB483DF2h
0x1800069ba  jnz     short loc_1800069E2
0x1800069bc  mov     eax, dword ptr cs:_GUID_bb483df2_7bb6_5923_a28d_8342ec30046b.Data2
0x1800069c2  cmp     [rdx+4], eax
0x1800069c5  jnz     short loc_1800069E2
0x1800069c7  mov     eax, dword ptr cs:_GUID_bb483df2_7bb6_5923_a28d_8342ec30046b.Data4
0x1800069cd  cmp     [rdx+8], eax
0x1800069d0  jnz     short loc_1800069E2
0x1800069d2  mov     eax, dword ptr cs:_GUID_bb483df2_7bb6_5923_a28d_8342ec30046b.Data4+4
0x1800069d8  cmp     [rdx+0Ch], eax
0x1800069db  jnz     short loc_1800069E2
0x1800069dd  mov     [r8], rcx
0x1800069e0  jmp     short loc_180006A38
0x1800069e2  add     rcx, 8
0x1800069e6  cmp     dword ptr [rdx], 94EA2B94h
0x1800069ec  jnz     short loc_180006A0C
0x1800069ee  mov     eax, dword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data2
0x1800069f4  cmp     [rdx+4], eax
0x1800069f7  jnz     short loc_180006A40
0x1800069f9  mov     eax, dword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4
0x1800069ff  cmp     [rdx+8], eax
0x180006a02  jnz     short loc_180006A40
0x180006a04  mov     eax, dword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4+4
0x180006a0a  jmp     short loc_180006A2D
0x180006a0c  cmp     dword ptr [rdx], 3
0x180006a0f  jnz     short loc_180006A40
0x180006a11  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data2
0x180006a17  cmp     [rdx+4], eax
0x180006a1a  jnz     short loc_180006A40
0x180006a1c  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data4
0x180006a22  cmp     [rdx+8], eax
0x180006a25  jnz     short loc_180006A40
0x180006a27  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data4+4
0x180006a2d  cmp     [rdx+0Ch], eax
0x180006a30  jnz     short loc_180006A40
0x180006a32  mov     rax, r8
0x180006a35  mov     [rax], rcx
0x180006a38  mov     rcx, [r8]
0x180006a3b  jmp     loc_1800069A3
0x180006a40  mov     ebx, 80004002h
0x180006a45  mov     eax, ebx
0x180006a47  add     rsp, 20h
0x180006a4b  pop     rbx
0x180006a4c  retn
```
