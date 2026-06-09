# AppHostConfigNavigatorTemplate<AppHostMergedConfigNavigator,IAppHostMergedConfigNavigator,MergedConfigTree>::GetConfiguration<IAppHostElement>(IAppHostElement * *)

- ea: `0x1800066bc`
- end: `0x180006764`
- name: `??$GetConfiguration@UIAppHostElement@@@?$AppHostConfigNavigatorTemplate@VAppHostMergedConfigNavigator@@UIAppHostMergedConfigNavigator@@VMergedConfigTree@@@@AEAAJPEAPEAUIAppHostElement@@@Z`
- size: `168`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800071f0`

## callees

- `0x1800021a4`
- `0x1800066bc`
- `0x180014010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AppHostConfigNavigatorTemplate<AppHostMergedConfigNavigator,IAppHostMergedConfigNavigator,MergedConfigTree>::GetConfiguration<IAppHostElement>(
        __int64 a1,
        _QWORD *a2)
{
  int v4; // ebx
  int v5; // [rsp+30h] [rbp-18h] BYREF
  __int64 (__fastcall ***v6)(_QWORD, GUID *, _QWORD *); // [rsp+58h] [rbp+10h] BYREF

  if ( !a2 )
    return 2147942487LL;
  try
  {
    v6 = 0;
    (*(void (__fastcall **)(_QWORD, _QWORD, GUID *, __int64 (__fastcall ****)(_QWORD, GUID *, _QWORD *)))(**(_QWORD **)(a1 + 48) + 88LL))(
      *(_QWORD *)(a1 + 48),
      *(_QWORD *)(a1 + 40),
      &GUID_64ff8ccc_b287_4dae_b08a_a72cbf45f453,
      &v6);
  }
  catch ( long v5 )
  {
    v4 = v5;
    goto LABEL_8;
  }
  catch ( ... )
  {
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v6);
    return 2147549183LL;
  }
  if ( !v6 )
  {
    *a2 = 0;
    goto LABEL_7;
  }
  v4 = (**v6)(v6, &GUID_64ff8ccc_b287_4dae_b08a_a72cbf45f453, a2);
  if ( v4 >= 0 )
  {
LABEL_7:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v6);
    return 0;
  }
LABEL_8:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v6);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800066bc  push    rbx
0x1800066be  sub     rsp, 40h
0x1800066c2  mov     rbx, rdx
0x1800066c5  mov     rdx, rcx
0x1800066c8  test    rbx, rbx
0x1800066cb  jnz     short loc_1800066D7
0x1800066cd  mov     eax, 80070057h
0x1800066d2  jmp     loc_18000675E
0x1800066d7  mov     [rsp+48h+arg_8], 0
0x1800066e0  mov     rcx, [rcx+30h]
0x1800066e4  mov     rax, [rcx]
0x1800066e7  lea     r9, [rsp+48h+arg_8]
0x1800066ec  lea     r8, _GUID_64ff8ccc_b287_4dae_b08a_a72cbf45f453
0x1800066f3  mov     rdx, [rdx+28h]
0x1800066f7  mov     rax, [rax+58h]
0x1800066fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006700  nop
0x180006701  mov     rcx, [rsp+48h+arg_8]
0x180006706  test    rcx, rcx
0x180006709  jz      short loc_180006728
0x18000670b  mov     rax, [rcx]
0x18000670e  mov     r8, rbx
0x180006711  lea     rdx, _GUID_64ff8ccc_b287_4dae_b08a_a72cbf45f453
0x180006718  mov     rax, [rax]
0x18000671b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006720  mov     ebx, eax
0x180006722  test    eax, eax
0x180006724  jns     short loc_18000672F
0x180006726  jmp     short loc_180006741
0x180006728  mov     qword ptr [rbx], 0
0x18000672f  lea     rcx, [rsp+48h+arg_8]
0x180006734  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180006739  xor     eax, eax
0x18000673b  jmp     short loc_18000675E
0x18000673d  mov     ebx, [rsp+48h+var_18]
0x180006741  lea     rcx, [rsp+48h+arg_8]
0x180006746  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000674b  mov     eax, ebx
0x18000674d  jmp     short loc_18000675E
0x18000674f  lea     rcx, [rsp+48h+arg_8]
0x180006754  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180006759  mov     eax, 8000FFFFh
0x18000675e  add     rsp, 40h
0x180006762  pop     rbx
0x180006763  retn
```
