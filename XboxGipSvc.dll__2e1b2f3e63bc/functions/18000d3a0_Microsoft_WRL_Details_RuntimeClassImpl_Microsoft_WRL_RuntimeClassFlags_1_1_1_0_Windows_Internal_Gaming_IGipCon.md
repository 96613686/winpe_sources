# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::Gaming::IGipControllerWatcher,Microsoft::WRL::FtmBase,Microsoft::WRL::CloakedIid<Windows::Internal::Gaming::Private::Inproc::ISystemButtonsSingletonPrivate>>::QueryInterface(_GUID const &,void * *)

- ea: `0x18000d3a0`
- end: `0x18000d51a`
- name: `?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIGipControllerWatcher@Gaming@Internal@Windows@@VFtmBase@23@U?$CloakedIid@UISystemButtonsSingletonPrivate@Inproc@Private@Gaming@Internal@Windows@@@23@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `378`
- prototype: `__int64 __fastcall(__int64, _DWORD *, _QWORD *)`
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000d520`
- `0x18000d530`
- `0x18000d540`
- `0x18000dd6c`
- `0x18000df30`
- `0x18000e110`

## callees

- `0x18000d3a0`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::Gaming::IGipControllerWatcher,Microsoft::WRL::FtmBase,Microsoft::WRL::CloakedIid<Windows::Internal::Gaming::Private::Inproc::ISystemButtonsSingletonPrivate>>::QueryInterface(
        __int64 a1,
        _DWORD *a2,
        _QWORD *a3)
{
  int v3; // eax
  int v4; // ebx
  __int64 v5; // rcx
  int v6; // eax

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
      if ( *a2 == -1796592748 )
      {
        if ( a2[1] != *(_DWORD *)&GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data2
          || a2[2] != *(_DWORD *)GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4 )
        {
          goto LABEL_31;
        }
        v6 = *(_DWORD *)&GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4[4];
      }
      else
      {
        if ( *a2 != 3
          || a2[1] != *(_DWORD *)&GUID_00000003_0000_0000_c000_000000000046.Data2
          || a2[2] != *(_DWORD *)GUID_00000003_0000_0000_c000_000000000046.Data4 )
        {
          goto LABEL_31;
        }
        v6 = *(_DWORD *)&GUID_00000003_0000_0000_c000_000000000046.Data4[4];
      }
      if ( a2[3] == v6 )
      {
        *a3 = v5;
        goto LABEL_30;
      }
LABEL_31:
      if ( *a2 != -47932379
        || a2[1] != *(_DWORD *)&GUID_fd249c25_76f6_448c_bcee_290d15598124.Data2
        || a2[2] != *(_DWORD *)GUID_fd249c25_76f6_448c_bcee_290d15598124.Data4
        || a2[3] != *(_DWORD *)&GUID_fd249c25_76f6_448c_bcee_290d15598124.Data4[4] )
      {
        v4 = -2147467262;
LABEL_37:
        if ( v4 < 0 )
          return (unsigned int)v4;
LABEL_38:
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a3 + 8LL))(*a3);
        return (unsigned int)v4;
      }
      *a3 = v5 + 32;
LABEL_30:
      v4 = 0;
      goto LABEL_37;
    }
LABEL_15:
    *a3 = a1;
    v4 = 0;
    goto LABEL_38;
  }
  if ( *a2 != -1350114592 )
  {
    if ( *a2 == 557341865
      && a2[1] == *(_DWORD *)&GUID_21385ca9_48ba_4169_a86a_5d3ec004eedb.Data2
      && a2[2] == *(_DWORD *)GUID_21385ca9_48ba_4169_a86a_5d3ec004eedb.Data4
      && a2[3] == *(_DWORD *)&GUID_21385ca9_48ba_4169_a86a_5d3ec004eedb.Data4[4] )
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
0x18000d3a0  push    rbx
0x18000d3a2  sub     rsp, 20h
0x18000d3a6  mov     qword ptr [r8], 0
0x18000d3ad  cmp     dword ptr [rdx], 0
0x18000d3b0  jnz     short loc_18000D3D4
0x18000d3b2  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data2
0x18000d3b8  cmp     [rdx+4], eax
0x18000d3bb  jnz     loc_18000D446
0x18000d3c1  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x18000d3c7  cmp     [rdx+8], eax
0x18000d3ca  jnz     short loc_18000D446
0x18000d3cc  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4+4
0x18000d3d2  jmp     short loc_18000D3F8
0x18000d3d4  cmp     dword ptr [rdx], 0AF86E2E0h
0x18000d3da  jnz     short loc_18000D413
0x18000d3dc  mov     eax, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data2
0x18000d3e2  cmp     [rdx+4], eax
0x18000d3e5  jnz     short loc_18000D446
0x18000d3e7  mov     eax, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4
0x18000d3ed  cmp     [rdx+8], eax
0x18000d3f0  jnz     short loc_18000D446
0x18000d3f2  mov     eax, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4+4
0x18000d3f8  cmp     [rdx+0Ch], eax
0x18000d3fb  jnz     short loc_18000D446
0x18000d3fd  mov     [r8], rcx
0x18000d400  mov     rax, [rcx]
0x18000d403  mov     rax, [rax+8]
0x18000d407  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d40c  xor     ebx, ebx
0x18000d40e  jmp     loc_18000D512
0x18000d413  cmp     dword ptr [rdx], 21385CA9h
0x18000d419  jnz     short loc_18000D446
0x18000d41b  mov     eax, dword ptr cs:_GUID_21385ca9_48ba_4169_a86a_5d3ec004eedb.Data2
0x18000d421  cmp     [rdx+4], eax
0x18000d424  jnz     short loc_18000D446
0x18000d426  mov     eax, dword ptr cs:_GUID_21385ca9_48ba_4169_a86a_5d3ec004eedb.Data4
0x18000d42c  cmp     [rdx+8], eax
0x18000d42f  jnz     short loc_18000D446
0x18000d431  mov     eax, dword ptr cs:_GUID_21385ca9_48ba_4169_a86a_5d3ec004eedb.Data4+4
0x18000d437  cmp     [rdx+0Ch], eax
0x18000d43a  jnz     short loc_18000D446
0x18000d43c  mov     [r8], rcx
0x18000d43f  xor     ebx, ebx
0x18000d441  jmp     loc_18000D502
0x18000d446  add     rcx, 8
0x18000d44a  cmp     dword ptr [rdx], 38h ; '8'
0x18000d44d  jnz     short loc_18000D470
0x18000d44f  mov     eax, dword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data2
0x18000d455  cmp     [rdx+4], eax
0x18000d458  jnz     short loc_18000D470
0x18000d45a  mov     eax, dword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data4
0x18000d460  cmp     [rdx+8], eax
0x18000d463  jnz     short loc_18000D470
0x18000d465  mov     eax, dword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data4+4
0x18000d46b  cmp     [rdx+0Ch], eax
0x18000d46e  jz      short loc_18000D43C
0x18000d470  add     rcx, 8
0x18000d474  cmp     dword ptr [rdx], 94EA2B94h
0x18000d47a  jnz     short loc_18000D49A
0x18000d47c  mov     eax, dword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data2
0x18000d482  cmp     [rdx+4], eax
0x18000d485  jnz     short loc_18000D4C7
0x18000d487  mov     eax, dword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4
0x18000d48d  cmp     [rdx+8], eax
0x18000d490  jnz     short loc_18000D4C7
0x18000d492  mov     eax, dword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4+4
0x18000d498  jmp     short loc_18000D4BB
0x18000d49a  cmp     dword ptr [rdx], 3
0x18000d49d  jnz     short loc_18000D4C7
0x18000d49f  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data2
0x18000d4a5  cmp     [rdx+4], eax
0x18000d4a8  jnz     short loc_18000D4C7
0x18000d4aa  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data4
0x18000d4b0  cmp     [rdx+8], eax
0x18000d4b3  jnz     short loc_18000D4C7
0x18000d4b5  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data4+4
0x18000d4bb  cmp     [rdx+0Ch], eax
0x18000d4be  jnz     short loc_18000D4C7
0x18000d4c0  mov     [r8], rcx
0x18000d4c3  xor     ebx, ebx
0x18000d4c5  jmp     short loc_18000D4FE
0x18000d4c7  cmp     dword ptr [rdx], 0FD249C25h
0x18000d4cd  jnz     short loc_18000D4F9
0x18000d4cf  mov     eax, dword ptr cs:_GUID_fd249c25_76f6_448c_bcee_290d15598124.Data2
0x18000d4d5  cmp     [rdx+4], eax
0x18000d4d8  jnz     short loc_18000D4F9
0x18000d4da  mov     eax, dword ptr cs:_GUID_fd249c25_76f6_448c_bcee_290d15598124.Data4
0x18000d4e0  cmp     [rdx+8], eax
0x18000d4e3  jnz     short loc_18000D4F9
0x18000d4e5  mov     eax, dword ptr cs:_GUID_fd249c25_76f6_448c_bcee_290d15598124.Data4+4
0x18000d4eb  cmp     [rdx+0Ch], eax
0x18000d4ee  jnz     short loc_18000D4F9
0x18000d4f0  lea     rax, [rcx+20h]
0x18000d4f4  mov     [r8], rax
0x18000d4f7  jmp     short loc_18000D4C3
0x18000d4f9  mov     ebx, 80004002h
0x18000d4fe  test    ebx, ebx
0x18000d500  js      short loc_18000D512
0x18000d502  mov     rcx, [r8]
0x18000d505  mov     rdx, [rcx]
0x18000d508  mov     rax, [rdx+8]
0x18000d50c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d511  nop
0x18000d512  mov     eax, ebx
0x18000d514  add     rsp, 20h
0x18000d518  pop     rbx
0x18000d519  retn
```
