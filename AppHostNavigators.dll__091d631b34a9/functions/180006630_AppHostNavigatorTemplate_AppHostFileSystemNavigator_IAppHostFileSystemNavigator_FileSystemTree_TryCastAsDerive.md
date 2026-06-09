# AppHostNavigatorTemplate<AppHostFileSystemNavigator,IAppHostFileSystemNavigator,FileSystemTree>::TryCastAsDerivedType(IXPathNavigator *,AppHostFileSystemNavigator * *)

- ea: `0x180006630`
- end: `0x1800066b5`
- name: `?TryCastAsDerivedType@?$AppHostNavigatorTemplate@VAppHostFileSystemNavigator@@UIAppHostFileSystemNavigator@@VFileSystemTree@@@@SAJPEAUIXPathNavigator@@PEAPEAVAppHostFileSystemNavigator@@@Z`
- size: `133`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180005f10`
- `0x1800062a0`

## callees

- `0x1800021a4`
- `0x180006630`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall AppHostNavigatorTemplate<AppHostFileSystemNavigator,IAppHostFileSystemNavigator,FileSystemTree>::TryCastAsDerivedType(
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
  v4 = (**a1)(a1, &GUID_355bd6c9_0a2e_42fa_ba7e_b4495b9dbeae, &v6);
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
0x180006630  mov     [rsp+arg_8], rbx
0x180006635  push    rdi
0x180006636  sub     rsp, 20h
0x18000663a  mov     rdi, rdx
0x18000663d  mov     qword ptr [rdx], 0
0x180006644  test    rcx, rcx
0x180006647  jnz     short loc_18000664D
0x180006649  xor     eax, eax
0x18000664b  jmp     short loc_1800066AA
0x18000664d  mov     [rsp+28h+arg_0], 0
0x180006656  mov     rax, [rcx]
0x180006659  lea     r8, [rsp+28h+arg_0]
0x18000665e  lea     rdx, _GUID_355bd6c9_0a2e_42fa_ba7e_b4495b9dbeae
0x180006665  mov     rax, [rax]
0x180006668  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000666d  mov     ebx, eax
0x18000666f  test    eax, eax
0x180006671  js      short loc_180006693
0x180006673  mov     rcx, [rsp+28h+arg_0]
0x180006678  mov     [rsp+28h+arg_0], 0
0x180006681  lea     rdx, [rcx-8]
0x180006685  neg     rcx
0x180006688  sbb     rcx, rcx
0x18000668b  and     rcx, rdx
0x18000668e  mov     [rdi], rcx
0x180006691  jmp     short loc_18000669E
0x180006693  xor     eax, eax
0x180006695  cmp     ebx, 80004002h
0x18000669b  cmovz   ebx, eax
0x18000669e  lea     rcx, [rsp+28h+arg_0]
0x1800066a3  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800066a8  mov     eax, ebx
0x1800066aa  mov     rbx, [rsp+28h+arg_8]
0x1800066af  add     rsp, 20h
0x1800066b3  pop     rdi
0x1800066b4  retn
```
