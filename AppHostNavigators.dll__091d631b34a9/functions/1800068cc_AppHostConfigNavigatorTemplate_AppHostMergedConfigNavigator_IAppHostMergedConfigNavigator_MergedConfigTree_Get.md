# AppHostConfigNavigatorTemplate<AppHostMergedConfigNavigator,IAppHostMergedConfigNavigator,MergedConfigTree>::GetConfiguration<IAppHostSectionGroup>(IAppHostSectionGroup * *)

- ea: `0x1800068cc`
- end: `0x180006974`
- name: `??$GetConfiguration@UIAppHostSectionGroup@@@?$AppHostConfigNavigatorTemplate@VAppHostMergedConfigNavigator@@UIAppHostMergedConfigNavigator@@VMergedConfigTree@@@@AEAAJPEAPEAUIAppHostSectionGroup@@@Z`
- size: `168`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800072c0`
- `0x1800096f0`

## callees

- `0x1800021a4`
- `0x1800068cc`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall AppHostConfigNavigatorTemplate<AppHostMergedConfigNavigator,IAppHostMergedConfigNavigator,MergedConfigTree>::GetConfiguration<IAppHostSectionGroup>(
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
    &GUID_0dd8a158_ebe6_4008_a1d9_b7ecc8f1104b,
    &v5);
  if ( v5 )
  {
    v4 = (**v5)(v5, &GUID_0dd8a158_ebe6_4008_a1d9_b7ecc8f1104b, a2);
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
0x1800068cc  push    rbx
0x1800068ce  sub     rsp, 40h
0x1800068d2  mov     rbx, rdx
0x1800068d5  mov     rdx, rcx
0x1800068d8  test    rbx, rbx
0x1800068db  jnz     short loc_1800068E7
0x1800068dd  mov     eax, 80070057h
0x1800068e2  jmp     loc_18000696E
0x1800068e7  mov     [rsp+48h+arg_8], 0
0x1800068f0  mov     rcx, [rcx+30h]
0x1800068f4  mov     rax, [rcx]
0x1800068f7  lea     r9, [rsp+48h+arg_8]
0x1800068fc  lea     r8, _GUID_0dd8a158_ebe6_4008_a1d9_b7ecc8f1104b
0x180006903  mov     rdx, [rdx+28h]
0x180006907  mov     rax, [rax+58h]
0x18000690b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006910  nop
0x180006911  mov     rcx, [rsp+48h+arg_8]
0x180006916  test    rcx, rcx
0x180006919  jz      short loc_180006938
0x18000691b  mov     rax, [rcx]
0x18000691e  mov     r8, rbx
0x180006921  lea     rdx, _GUID_0dd8a158_ebe6_4008_a1d9_b7ecc8f1104b
0x180006928  mov     rax, [rax]
0x18000692b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006930  mov     ebx, eax
0x180006932  test    eax, eax
0x180006934  jns     short loc_18000693F
0x180006936  jmp     short loc_180006951
0x180006938  mov     qword ptr [rbx], 0
0x18000693f  lea     rcx, [rsp+48h+arg_8]
0x180006944  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180006949  xor     eax, eax
0x18000694b  jmp     short loc_18000696E
0x18000694d  mov     ebx, [rsp+48h+var_18]
0x180006951  lea     rcx, [rsp+48h+arg_8]
0x180006956  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000695b  mov     eax, ebx
0x18000695d  jmp     short loc_18000696E
0x18000695f  lea     rcx, [rsp+48h+arg_8]
0x180006964  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180006969  mov     eax, 8000FFFFh
0x18000696e  add     rsp, 40h
0x180006972  pop     rbx
0x180006973  retn
```
