# AppHostNavigatorTemplate<AppHostConfigLocationsNavigator,IAppHostConfigLocationsNavigator,ConfigLocationsTree>::TryCastAsDerivedType(IXPathNavigator *,AppHostConfigLocationsNavigator * *)

- ea: `0x180003a48`
- end: `0x180003acd`
- name: `?TryCastAsDerivedType@?$AppHostNavigatorTemplate@VAppHostConfigLocationsNavigator@@UIAppHostConfigLocationsNavigator@@VConfigLocationsTree@@@@SAJPEAUIXPathNavigator@@PEAPEAVAppHostConfigLocationsNavigator@@@Z`
- size: `133`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180002700`
- `0x1800033d0`
- `0x180008b20`

## callees

- `0x1800021a4`
- `0x180003a48`
- `0x180014010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AppHostNavigatorTemplate<AppHostConfigLocationsNavigator,IAppHostConfigLocationsNavigator,ConfigLocationsTree>::TryCastAsDerivedType(
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
  v4 = (**a1)(a1, &GUID_9dfa9beb_c15f_450e_bf3a_1d56c67b5c0b, &v6);
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
0x180003a48  mov     [rsp+arg_8], rbx
0x180003a4d  push    rdi
0x180003a4e  sub     rsp, 20h
0x180003a52  mov     rdi, rdx
0x180003a55  mov     qword ptr [rdx], 0
0x180003a5c  test    rcx, rcx
0x180003a5f  jnz     short loc_180003A65
0x180003a61  xor     eax, eax
0x180003a63  jmp     short loc_180003AC2
0x180003a65  mov     [rsp+28h+arg_0], 0
0x180003a6e  mov     rax, [rcx]
0x180003a71  lea     r8, [rsp+28h+arg_0]
0x180003a76  lea     rdx, _GUID_9dfa9beb_c15f_450e_bf3a_1d56c67b5c0b
0x180003a7d  mov     rax, [rax]
0x180003a80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a85  mov     ebx, eax
0x180003a87  test    eax, eax
0x180003a89  js      short loc_180003AAB
0x180003a8b  mov     rcx, [rsp+28h+arg_0]
0x180003a90  mov     [rsp+28h+arg_0], 0
0x180003a99  lea     rdx, [rcx-8]
0x180003a9d  neg     rcx
0x180003aa0  sbb     rcx, rcx
0x180003aa3  and     rcx, rdx
0x180003aa6  mov     [rdi], rcx
0x180003aa9  jmp     short loc_180003AB6
0x180003aab  xor     eax, eax
0x180003aad  cmp     ebx, 80004002h
0x180003ab3  cmovz   ebx, eax
0x180003ab6  lea     rcx, [rsp+28h+arg_0]
0x180003abb  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180003ac0  mov     eax, ebx
0x180003ac2  mov     rbx, [rsp+28h+arg_8]
0x180003ac7  add     rsp, 20h
0x180003acb  pop     rdi
0x180003acc  retn
```
