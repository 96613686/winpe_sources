# AppHostNavigatorTemplate<AppHostConfigPathNavigator,IAppHostConfigPathNavigator,ConfigPathNavigationTree>::TryCastAsDerivedType(IXPathNavigator *,AppHostConfigPathNavigator * *)

- ea: `0x180005920`
- end: `0x1800059a5`
- name: `?TryCastAsDerivedType@?$AppHostNavigatorTemplate@VAppHostConfigPathNavigator@@UIAppHostConfigPathNavigator@@VConfigPathNavigationTree@@@@SAJPEAUIXPathNavigator@@PEAPEAVAppHostConfigPathNavigator@@@Z`
- size: `133`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180004980`
- `0x1800052d0`
- `0x180008838`
- `0x18000eef0`

## callees

- `0x1800021a4`
- `0x180005920`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall AppHostNavigatorTemplate<AppHostConfigPathNavigator,IAppHostConfigPathNavigator,ConfigPathNavigationTree>::TryCastAsDerivedType(
        __int64 (__fastcall ***a1)(_QWORD, GUID *, __int64 *),
        __int64 *a2)
{
  int v4; // ebx
  __int64 v5; // rcx
  __int64 v6; // [rsp+30h] [rbp+8h] BYREF

  *a2 = 0;
  if ( !a1 )
    return 0;
  v6 = 0;
  v4 = (**a1)(a1, &GUID_a0601362_def3_4571_809b_5b856e5e5521, &v6);
  if ( v4 < 0 )
  {
    if ( v4 == -2147467262 )
      v4 = 0;
  }
  else
  {
    v5 = v6;
    v6 = 0;
    *a2 = (v5 - 8) & -(__int64)(v5 != 0);
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v6);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180005920  mov     [rsp+arg_8], rbx
0x180005925  push    rdi
0x180005926  sub     rsp, 20h
0x18000592a  mov     rdi, rdx
0x18000592d  mov     qword ptr [rdx], 0
0x180005934  test    rcx, rcx
0x180005937  jnz     short loc_18000593D
0x180005939  xor     eax, eax
0x18000593b  jmp     short loc_18000599A
0x18000593d  mov     [rsp+28h+arg_0], 0
0x180005946  mov     rax, [rcx]
0x180005949  lea     r8, [rsp+28h+arg_0]
0x18000594e  lea     rdx, _GUID_a0601362_def3_4571_809b_5b856e5e5521
0x180005955  mov     rax, [rax]
0x180005958  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000595d  mov     ebx, eax
0x18000595f  test    eax, eax
0x180005961  js      short loc_180005983
0x180005963  mov     rcx, [rsp+28h+arg_0]
0x180005968  mov     [rsp+28h+arg_0], 0
0x180005971  lea     rdx, [rcx-8]
0x180005975  neg     rcx
0x180005978  sbb     rcx, rcx
0x18000597b  and     rcx, rdx
0x18000597e  mov     [rdi], rcx
0x180005981  jmp     short loc_18000598E
0x180005983  xor     eax, eax
0x180005985  cmp     ebx, 80004002h
0x18000598b  cmovz   ebx, eax
0x18000598e  lea     rcx, [rsp+28h+arg_0]
0x180005993  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180005998  mov     eax, ebx
0x18000599a  mov     rbx, [rsp+28h+arg_8]
0x18000599f  add     rsp, 20h
0x1800059a3  pop     rdi
0x1800059a4  retn
```
