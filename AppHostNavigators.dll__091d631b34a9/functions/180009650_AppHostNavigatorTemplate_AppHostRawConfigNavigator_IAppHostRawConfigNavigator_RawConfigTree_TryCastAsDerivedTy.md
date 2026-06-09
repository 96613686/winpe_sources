# AppHostNavigatorTemplate<AppHostRawConfigNavigator,IAppHostRawConfigNavigator,RawConfigTree>::TryCastAsDerivedType(IXPathNavigator *,AppHostRawConfigNavigator * *)

- ea: `0x180009650`
- end: `0x1800096d5`
- name: `?TryCastAsDerivedType@?$AppHostNavigatorTemplate@VAppHostRawConfigNavigator@@UIAppHostRawConfigNavigator@@VRawConfigTree@@@@SAJPEAUIXPathNavigator@@PEAPEAVAppHostRawConfigNavigator@@@Z`
- size: `133`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009160`
- `0x180009460`
- `0x18000e368`

## callees

- `0x1800021a4`
- `0x180009650`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall AppHostNavigatorTemplate<AppHostRawConfigNavigator,IAppHostRawConfigNavigator,RawConfigTree>::TryCastAsDerivedType(
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
  v4 = (**a1)(a1, &GUID_4f29aa5f_4a59_4e88_bc5a_a902f6ff1d86, &v6);
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
0x180009650  mov     [rsp+arg_8], rbx
0x180009655  push    rdi
0x180009656  sub     rsp, 20h
0x18000965a  mov     rdi, rdx
0x18000965d  mov     qword ptr [rdx], 0
0x180009664  test    rcx, rcx
0x180009667  jnz     short loc_18000966D
0x180009669  xor     eax, eax
0x18000966b  jmp     short loc_1800096CA
0x18000966d  mov     [rsp+28h+arg_0], 0
0x180009676  mov     rax, [rcx]
0x180009679  lea     r8, [rsp+28h+arg_0]
0x18000967e  lea     rdx, _GUID_4f29aa5f_4a59_4e88_bc5a_a902f6ff1d86
0x180009685  mov     rax, [rax]
0x180009688  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000968d  mov     ebx, eax
0x18000968f  test    eax, eax
0x180009691  js      short loc_1800096B3
0x180009693  mov     rcx, [rsp+28h+arg_0]
0x180009698  mov     [rsp+28h+arg_0], 0
0x1800096a1  lea     rdx, [rcx-8]
0x1800096a5  neg     rcx
0x1800096a8  sbb     rcx, rcx
0x1800096ab  and     rcx, rdx
0x1800096ae  mov     [rdi], rcx
0x1800096b1  jmp     short loc_1800096BE
0x1800096b3  xor     eax, eax
0x1800096b5  cmp     ebx, 80004002h
0x1800096bb  cmovz   ebx, eax
0x1800096be  lea     rcx, [rsp+28h+arg_0]
0x1800096c3  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800096c8  mov     eax, ebx
0x1800096ca  mov     rbx, [rsp+28h+arg_8]
0x1800096cf  add     rsp, 20h
0x1800096d3  pop     rdi
0x1800096d4  retn
```
