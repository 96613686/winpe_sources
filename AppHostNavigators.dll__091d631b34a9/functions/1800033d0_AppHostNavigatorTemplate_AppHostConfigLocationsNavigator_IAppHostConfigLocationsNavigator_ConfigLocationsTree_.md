# AppHostNavigatorTemplate<AppHostConfigLocationsNavigator,IAppHostConfigLocationsNavigator,ConfigLocationsTree>::MoveTo(IXPathNavigator *)

- ea: `0x1800033d0`
- end: `0x180003488`
- name: `?MoveTo@?$AppHostNavigatorTemplate@VAppHostConfigLocationsNavigator@@UIAppHostConfigLocationsNavigator@@VConfigLocationsTree@@@@UEAAJPEAUIXPathNavigator@@@Z`
- size: `184`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x1800033d0`
- `0x1800039ec`
- `0x180003a1c`
- `0x180003a48`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AppHostNavigatorTemplate<AppHostConfigLocationsNavigator,IAppHostConfigLocationsNavigator,ConfigLocationsTree>::MoveTo(
        __int64 a1,
        __int64 (__fastcall ***a2)(_QWORD, GUID *, __int64 *))
{
  __int64 result; // rax
  int v4; // ebx
  __int64 v5; // r14
  __int64 v6; // rbx
  unsigned int v7; // [rsp+20h] [rbp-38h] BYREF
  __int64 v8; // [rsp+68h] [rbp+10h] BYREF

  if ( !a2 )
    return 2147942487LL;
  v8 = 0;
  try
  {
    v4 = AppHostNavigatorTemplate<AppHostConfigLocationsNavigator,IAppHostConfigLocationsNavigator,ConfigLocationsTree>::TryCastAsDerivedType(
           a2,
           &v8);
    if ( v4 >= 0 )
    {
      if ( v8 )
      {
        v5 = *(_QWORD *)(v8 + 48);
        v6 = *(_QWORD *)(v8 + 40);
        *(_DWORD *)(a1 + 32) = *(_DWORD *)(v8 + 32);
        if ( *(_QWORD *)(a1 + 40) != v6 )
        {
          if ( v6 )
            _InterlockedIncrement((volatile signed __int32 *)(v6 + 8));
          InvasivePtr<ConfigLocationsTree>::Reset((InvasivePtrObject **)(a1 + 40));
          *(_QWORD *)(a1 + 40) = v6;
        }
        *(_QWORD *)(a1 + 48) = v5;
        InvasivePtr<AppHostConfigPathNavigator>::Reset(&v8);
        result = 0;
      }
      else
      {
        InvasivePtr<AppHostConfigPathNavigator>::Reset(&v8);
        result = 1;
      }
    }
    else
    {
      InvasivePtr<AppHostConfigPathNavigator>::Reset(&v8);
      result = (unsigned int)v4;
    }
  }
  catch ( long v7 )
  {
    return v7;
  }
  catch ( ... )
  {
    return 2147549183LL;
  }
  return result;
}

```

## disassembly

```asm
0x1800033d0  push    rbx
0x1800033d2  push    rsi
0x1800033d3  push    rdi
0x1800033d4  push    r14
0x1800033d6  sub     rsp, 38h
0x1800033da  mov     rax, rdx
0x1800033dd  mov     rsi, rcx
0x1800033e0  test    rdx, rdx
0x1800033e3  jnz     short loc_1800033EF
0x1800033e5  mov     eax, 80070057h
0x1800033ea  jmp     loc_18000347D
0x1800033ef  mov     [rsp+58h+arg_8], 0
0x1800033f8  lea     rdx, [rsp+58h+arg_8]
0x1800033fd  mov     rcx, rax
0x180003400  call    ?TryCastAsDerivedType@?$AppHostNavigatorTemplate@VAppHostConfigLocationsNavigator@@UIAppHostConfigLocationsNavigator@@VConfigLocationsTree@@@@SAJPEAUIXPathNavigator@@PEAPEAVAppHostConfigLocationsNavigator@@@Z; AppHostNavigatorTemplate<AppHostConfigLocationsNavigator,IAppHostConfigLocationsNavigator,ConfigLocationsTree>::TryCastAsDerivedType(IXPathNavigator *,AppHostConfigLocationsNavigator * *)
0x180003405  mov     ebx, eax
0x180003407  test    eax, eax
0x180003409  jns     short loc_180003419
0x18000340b  lea     rcx, [rsp+58h+arg_8]
0x180003410  call    ?Reset@?$InvasivePtr@VAppHostConfigPathNavigator@@@@QEAAXXZ; InvasivePtr<AppHostConfigPathNavigator>::Reset(void)
0x180003415  mov     eax, ebx
0x180003417  jmp     short loc_18000347D
0x180003419  mov     rax, [rsp+58h+arg_8]
0x18000341e  test    rax, rax
0x180003421  jnz     short loc_180003434
0x180003423  lea     rcx, [rsp+58h+arg_8]
0x180003428  call    ?Reset@?$InvasivePtr@VAppHostConfigPathNavigator@@@@QEAAXXZ; InvasivePtr<AppHostConfigPathNavigator>::Reset(void)
0x18000342d  mov     eax, 1
0x180003432  jmp     short loc_18000347D
0x180003434  mov     r14, [rax+30h]
0x180003438  mov     rbx, [rax+28h]
0x18000343c  mov     ecx, [rax+20h]
0x18000343f  mov     [rsi+20h], ecx
0x180003442  lea     rdi, [rsi+28h]
0x180003446  cmp     [rdi], rbx
0x180003449  jz      short loc_18000345F
0x18000344b  test    rbx, rbx
0x18000344e  jz      short loc_180003454
0x180003450  lock inc dword ptr [rbx+8]
0x180003454  mov     rcx, rdi
0x180003457  call    ?Reset@?$InvasivePtr@VConfigLocationsTree@@@@QEAAXXZ; InvasivePtr<ConfigLocationsTree>::Reset(void)
0x18000345c  mov     [rdi], rbx
0x18000345f  mov     [rsi+30h], r14
0x180003463  lea     rcx, [rsp+58h+arg_8]
0x180003468  call    ?Reset@?$InvasivePtr@VAppHostConfigPathNavigator@@@@QEAAXXZ; InvasivePtr<AppHostConfigPathNavigator>::Reset(void)
0x18000346d  nop
0x18000346e  xor     eax, eax
0x180003470  jmp     short loc_18000347D
0x180003472  mov     eax, [rsp+58h+var_38]
0x180003476  jmp     short loc_18000347D
0x180003478  mov     eax, 8000FFFFh
0x18000347d  add     rsp, 38h
0x180003481  pop     r14
0x180003483  pop     rdi
0x180003484  pop     rsi
0x180003485  pop     rbx
0x180003486  retn
```
