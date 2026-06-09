# AppHostConfigNavigatorTemplate<AppHostMergedConfigNavigator,IAppHostMergedConfigNavigator,MergedConfigTree>::GetConfiguration<IAppHostSectionDefinition>(IAppHostSectionDefinition * *)

- ea: `0x18000681c`
- end: `0x1800068c4`
- name: `??$GetConfiguration@UIAppHostSectionDefinition@@@?$AppHostConfigNavigatorTemplate@VAppHostMergedConfigNavigator@@UIAppHostMergedConfigNavigator@@VMergedConfigTree@@@@AEAAJPEAPEAUIAppHostSectionDefinition@@@Z`
- size: `168`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800072b0`
- `0x1800096e0`

## callees

- `0x1800021a4`
- `0x18000681c`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall AppHostConfigNavigatorTemplate<AppHostMergedConfigNavigator,IAppHostMergedConfigNavigator,MergedConfigTree>::GetConfiguration<IAppHostSectionDefinition>(
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
    &GUID_c5c04795_321c_4014_8fd6_d44658799393,
    &v5);
  if ( v5 )
  {
    v4 = (**v5)(v5, &GUID_c5c04795_321c_4014_8fd6_d44658799393, a2);
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
0x18000681c  push    rbx
0x18000681e  sub     rsp, 40h
0x180006822  mov     rbx, rdx
0x180006825  mov     rdx, rcx
0x180006828  test    rbx, rbx
0x18000682b  jnz     short loc_180006837
0x18000682d  mov     eax, 80070057h
0x180006832  jmp     loc_1800068BE
0x180006837  mov     [rsp+48h+arg_8], 0
0x180006840  mov     rcx, [rcx+30h]
0x180006844  mov     rax, [rcx]
0x180006847  lea     r9, [rsp+48h+arg_8]
0x18000684c  lea     r8, _GUID_c5c04795_321c_4014_8fd6_d44658799393
0x180006853  mov     rdx, [rdx+28h]
0x180006857  mov     rax, [rax+58h]
0x18000685b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006860  nop
0x180006861  mov     rcx, [rsp+48h+arg_8]
0x180006866  test    rcx, rcx
0x180006869  jz      short loc_180006888
0x18000686b  mov     rax, [rcx]
0x18000686e  mov     r8, rbx
0x180006871  lea     rdx, _GUID_c5c04795_321c_4014_8fd6_d44658799393
0x180006878  mov     rax, [rax]
0x18000687b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006880  mov     ebx, eax
0x180006882  test    eax, eax
0x180006884  jns     short loc_18000688F
0x180006886  jmp     short loc_1800068A1
0x180006888  mov     qword ptr [rbx], 0
0x18000688f  lea     rcx, [rsp+48h+arg_8]
0x180006894  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180006899  xor     eax, eax
0x18000689b  jmp     short loc_1800068BE
0x18000689d  mov     ebx, [rsp+48h+var_18]
0x1800068a1  lea     rcx, [rsp+48h+arg_8]
0x1800068a6  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800068ab  mov     eax, ebx
0x1800068ad  jmp     short loc_1800068BE
0x1800068af  lea     rcx, [rsp+48h+arg_8]
0x1800068b4  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800068b9  mov     eax, 8000FFFFh
0x1800068be  add     rsp, 40h
0x1800068c2  pop     rbx
0x1800068c3  retn
```
