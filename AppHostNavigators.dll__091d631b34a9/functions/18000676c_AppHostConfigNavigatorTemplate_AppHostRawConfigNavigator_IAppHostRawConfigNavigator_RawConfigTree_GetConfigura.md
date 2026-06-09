# AppHostConfigNavigatorTemplate<AppHostRawConfigNavigator,IAppHostRawConfigNavigator,RawConfigTree>::GetConfiguration<IAppHostProperty>(IAppHostProperty * *)

- ea: `0x18000676c`
- end: `0x180006814`
- name: `??$GetConfiguration@UIAppHostProperty@@@?$AppHostConfigNavigatorTemplate@VAppHostRawConfigNavigator@@UIAppHostRawConfigNavigator@@VRawConfigTree@@@@AEAAJPEAPEAUIAppHostProperty@@@Z`
- size: `168`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800072a0`

## callees

- `0x1800021a4`
- `0x18000676c`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall AppHostConfigNavigatorTemplate<AppHostRawConfigNavigator,IAppHostRawConfigNavigator,RawConfigTree>::GetConfiguration<IAppHostProperty>(
        __int64 a1,
        _QWORD *a2)
{
  int v4; // ebx
  __int64 (__fastcall ***v5)(_QWORD, GUID *, _QWORD *); // [rsp+58h] [rbp+10h] BYREF

  if ( !a2 )
    return 2147942487LL;
  v5 = 0;
  (*(void (__fastcall **)(_QWORD, _QWORD, GUID *, __int64 (__fastcall ****)(_QWORD, GUID *, _QWORD *)))(**(_QWORD **)(a1 + 48) + 88LL))(
    *(_QWORD *)(a1 + 48),
    *(_QWORD *)(a1 + 40),
    &GUID_ed35f7a1_5024_4e7b_a44d_07ddaf4b524d,
    &v5);
  if ( v5 )
  {
    v4 = (**v5)(v5, &GUID_ed35f7a1_5024_4e7b_a44d_07ddaf4b524d, a2);
    if ( v4 < 0 )
    {
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v5);
      return (unsigned int)v4;
    }
  }
  else
  {
    *a2 = 0;
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v5);
  return 0;
}

```

## disassembly

```asm
0x18000676c  push    rbx
0x18000676e  sub     rsp, 40h
0x180006772  mov     rbx, rdx
0x180006775  mov     rdx, rcx
0x180006778  test    rbx, rbx
0x18000677b  jnz     short loc_180006787
0x18000677d  mov     eax, 80070057h
0x180006782  jmp     loc_18000680E
0x180006787  mov     [rsp+48h+arg_8], 0
0x180006790  mov     rcx, [rcx+30h]
0x180006794  mov     rax, [rcx]
0x180006797  lea     r9, [rsp+48h+arg_8]
0x18000679c  lea     r8, _GUID_ed35f7a1_5024_4e7b_a44d_07ddaf4b524d
0x1800067a3  mov     rdx, [rdx+28h]
0x1800067a7  mov     rax, [rax+58h]
0x1800067ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800067b0  nop
0x1800067b1  mov     rcx, [rsp+48h+arg_8]
0x1800067b6  test    rcx, rcx
0x1800067b9  jz      short loc_1800067D8
0x1800067bb  mov     rax, [rcx]
0x1800067be  mov     r8, rbx
0x1800067c1  lea     rdx, _GUID_ed35f7a1_5024_4e7b_a44d_07ddaf4b524d
0x1800067c8  mov     rax, [rax]
0x1800067cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800067d0  mov     ebx, eax
0x1800067d2  test    eax, eax
0x1800067d4  jns     short loc_1800067DF
0x1800067d6  jmp     short loc_1800067F1
0x1800067d8  mov     qword ptr [rbx], 0
0x1800067df  lea     rcx, [rsp+48h+arg_8]
0x1800067e4  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800067e9  xor     eax, eax
0x1800067eb  jmp     short loc_18000680E
0x1800067ed  mov     ebx, [rsp+48h+var_18]
0x1800067f1  lea     rcx, [rsp+48h+arg_8]
0x1800067f6  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800067fb  mov     eax, ebx
0x1800067fd  jmp     short loc_18000680E
0x1800067ff  lea     rcx, [rsp+48h+arg_8]
0x180006804  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180006809  mov     eax, 8000FFFFh
0x18000680e  add     rsp, 40h
0x180006812  pop     rbx
0x180006813  retn
```
