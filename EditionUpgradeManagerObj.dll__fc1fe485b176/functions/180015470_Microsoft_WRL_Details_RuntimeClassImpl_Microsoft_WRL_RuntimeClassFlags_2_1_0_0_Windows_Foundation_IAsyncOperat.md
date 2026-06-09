# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Microsoft::WRL::FtmBase>::QueryInterface(_GUID const &,void * *)

- ea: `0x180015470`
- end: `0x18001554d`
- name: `?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$IAsyncOperationCompletedHandler@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `221`
- prototype: `__int64 __fastcall(__int64, _DWORD *, __int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180015560`

## callees

- `0x180015470`
- `0x180023010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Microsoft::WRL::FtmBase>::QueryInterface(
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
    if ( *a2 == -558544094
      && a2[1] == *(_DWORD *)&GUID_deb54b22_70f2_55ab_97c0_6cbdc5ddb6f0.Data2
      && a2[2] == *(_DWORD *)GUID_deb54b22_70f2_55ab_97c0_6cbdc5ddb6f0.Data4
      && a2[3] == *(_DWORD *)&GUID_deb54b22_70f2_55ab_97c0_6cbdc5ddb6f0.Data4[4] )
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
0x180015470  push    rbx
0x180015472  sub     rsp, 20h
0x180015476  xor     ebx, ebx
0x180015478  mov     [r8], rbx
0x18001547b  cmp     [rdx], ebx
0x18001547d  jnz     short loc_1800154B4
0x18001547f  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data2
0x180015485  cmp     [rdx+4], eax
0x180015488  jnz     short loc_1800154E2
0x18001548a  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x180015490  cmp     [rdx+8], eax
0x180015493  jnz     short loc_1800154E2
0x180015495  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4+4
0x18001549b  cmp     [rdx+0Ch], eax
0x18001549e  jnz     short loc_1800154E2
0x1800154a0  mov     [r8], rcx
0x1800154a3  mov     rax, [rcx]
0x1800154a6  mov     rax, [rax+8]
0x1800154aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800154af  jmp     loc_180015545
0x1800154b4  cmp     dword ptr [rdx], 0DEB54B22h
0x1800154ba  jnz     short loc_1800154E2
0x1800154bc  mov     eax, dword ptr cs:_GUID_deb54b22_70f2_55ab_97c0_6cbdc5ddb6f0.Data2
0x1800154c2  cmp     [rdx+4], eax
0x1800154c5  jnz     short loc_1800154E2
0x1800154c7  mov     eax, dword ptr cs:_GUID_deb54b22_70f2_55ab_97c0_6cbdc5ddb6f0.Data4
0x1800154cd  cmp     [rdx+8], eax
0x1800154d0  jnz     short loc_1800154E2
0x1800154d2  mov     eax, dword ptr cs:_GUID_deb54b22_70f2_55ab_97c0_6cbdc5ddb6f0.Data4+4
0x1800154d8  cmp     [rdx+0Ch], eax
0x1800154db  jnz     short loc_1800154E2
0x1800154dd  mov     [r8], rcx
0x1800154e0  jmp     short loc_180015538
0x1800154e2  add     rcx, 8
0x1800154e6  cmp     dword ptr [rdx], 94EA2B94h
0x1800154ec  jnz     short loc_18001550C
0x1800154ee  mov     eax, dword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data2
0x1800154f4  cmp     [rdx+4], eax
0x1800154f7  jnz     short loc_180015540
0x1800154f9  mov     eax, dword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4
0x1800154ff  cmp     [rdx+8], eax
0x180015502  jnz     short loc_180015540
0x180015504  mov     eax, dword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4+4
0x18001550a  jmp     short loc_18001552D
0x18001550c  cmp     dword ptr [rdx], 3
0x18001550f  jnz     short loc_180015540
0x180015511  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data2
0x180015517  cmp     [rdx+4], eax
0x18001551a  jnz     short loc_180015540
0x18001551c  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data4
0x180015522  cmp     [rdx+8], eax
0x180015525  jnz     short loc_180015540
0x180015527  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data4+4
0x18001552d  cmp     [rdx+0Ch], eax
0x180015530  jnz     short loc_180015540
0x180015532  mov     rax, r8
0x180015535  mov     [rax], rcx
0x180015538  mov     rcx, [r8]
0x18001553b  jmp     loc_1800154A3
0x180015540  mov     ebx, 80004002h
0x180015545  mov     eax, ebx
0x180015547  add     rsp, 20h
0x18001554b  pop     rbx
0x18001554c  retn
```
