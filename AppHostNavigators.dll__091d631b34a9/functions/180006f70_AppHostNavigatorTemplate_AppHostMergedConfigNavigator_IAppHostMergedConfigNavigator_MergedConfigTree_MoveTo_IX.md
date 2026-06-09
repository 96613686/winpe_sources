# AppHostNavigatorTemplate<AppHostMergedConfigNavigator,IAppHostMergedConfigNavigator,MergedConfigTree>::MoveTo(IXPathNavigator *)

- ea: `0x180006f70`
- end: `0x180007028`
- name: `?MoveTo@?$AppHostNavigatorTemplate@VAppHostMergedConfigNavigator@@UIAppHostMergedConfigNavigator@@VMergedConfigTree@@@@UEAAJPEAUIXPathNavigator@@@Z`
- size: `184`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x1800039ec`
- `0x180003a1c`
- `0x180006f70`
- `0x180007160`

## pseudocode

```c
__int64 __fastcall AppHostNavigatorTemplate<AppHostMergedConfigNavigator,IAppHostMergedConfigNavigator,MergedConfigTree>::MoveTo(
        __int64 a1,
        __int64 (__fastcall ***a2)(_QWORD, GUID *, __int64 *))
{
  int v4; // ebx
  __int64 v5; // r14
  __int64 v6; // rbx
  __int64 v7; // [rsp+68h] [rbp+10h] BYREF

  if ( !a2 )
    return 2147942487LL;
  v7 = 0;
  v4 = AppHostNavigatorTemplate<AppHostMergedConfigNavigator,IAppHostMergedConfigNavigator,MergedConfigTree>::TryCastAsDerivedType(
         a2,
         &v7);
  if ( v4 >= 0 )
  {
    if ( v7 )
    {
      v5 = *(_QWORD *)(v7 + 48);
      v6 = *(_QWORD *)(v7 + 40);
      *(_DWORD *)(a1 + 32) = *(_DWORD *)(v7 + 32);
      if ( *(_QWORD *)(a1 + 40) != v6 )
      {
        if ( v6 )
          _InterlockedIncrement((volatile signed __int32 *)(v6 + 8));
        InvasivePtr<ConfigLocationsTree>::Reset((InvasivePtrObject **)(a1 + 40));
        *(_QWORD *)(a1 + 40) = v6;
      }
      *(_QWORD *)(a1 + 48) = v5;
      InvasivePtr<AppHostConfigPathNavigator>::Reset(&v7);
      return 0;
    }
    else
    {
      InvasivePtr<AppHostConfigPathNavigator>::Reset(&v7);
      return 1;
    }
  }
  else
  {
    InvasivePtr<AppHostConfigPathNavigator>::Reset(&v7);
    return (unsigned int)v4;
  }
}

```

## disassembly

```asm
0x180006f70  push    rbx
0x180006f72  push    rsi
0x180006f73  push    rdi
0x180006f74  push    r14
0x180006f76  sub     rsp, 38h
0x180006f7a  mov     rax, rdx
0x180006f7d  mov     rsi, rcx
0x180006f80  test    rdx, rdx
0x180006f83  jnz     short loc_180006F8F
0x180006f85  mov     eax, 80070057h
0x180006f8a  jmp     loc_18000701D
0x180006f8f  mov     [rsp+58h+arg_8], 0
0x180006f98  lea     rdx, [rsp+58h+arg_8]
0x180006f9d  mov     rcx, rax
0x180006fa0  call    ?TryCastAsDerivedType@?$AppHostNavigatorTemplate@VAppHostMergedConfigNavigator@@UIAppHostMergedConfigNavigator@@VMergedConfigTree@@@@SAJPEAUIXPathNavigator@@PEAPEAVAppHostMergedConfigNavigator@@@Z; AppHostNavigatorTemplate<AppHostMergedConfigNavigator,IAppHostMergedConfigNavigator,MergedConfigTree>::TryCastAsDerivedType(IXPathNavigator *,AppHostMergedConfigNavigator * *)
0x180006fa5  mov     ebx, eax
0x180006fa7  test    eax, eax
0x180006fa9  jns     short loc_180006FB9
0x180006fab  lea     rcx, [rsp+58h+arg_8]
0x180006fb0  call    ?Reset@?$InvasivePtr@VAppHostConfigPathNavigator@@@@QEAAXXZ; InvasivePtr<AppHostConfigPathNavigator>::Reset(void)
0x180006fb5  mov     eax, ebx
0x180006fb7  jmp     short loc_18000701D
0x180006fb9  mov     rax, [rsp+58h+arg_8]
0x180006fbe  test    rax, rax
0x180006fc1  jnz     short loc_180006FD4
0x180006fc3  lea     rcx, [rsp+58h+arg_8]
0x180006fc8  call    ?Reset@?$InvasivePtr@VAppHostConfigPathNavigator@@@@QEAAXXZ; InvasivePtr<AppHostConfigPathNavigator>::Reset(void)
0x180006fcd  mov     eax, 1
0x180006fd2  jmp     short loc_18000701D
0x180006fd4  mov     r14, [rax+30h]
0x180006fd8  mov     rbx, [rax+28h]
0x180006fdc  mov     ecx, [rax+20h]
0x180006fdf  mov     [rsi+20h], ecx
0x180006fe2  lea     rdi, [rsi+28h]
0x180006fe6  cmp     [rdi], rbx
0x180006fe9  jz      short loc_180006FFF
0x180006feb  test    rbx, rbx
0x180006fee  jz      short loc_180006FF4
0x180006ff0  lock inc dword ptr [rbx+8]
0x180006ff4  mov     rcx, rdi
0x180006ff7  call    ?Reset@?$InvasivePtr@VConfigLocationsTree@@@@QEAAXXZ; InvasivePtr<ConfigLocationsTree>::Reset(void)
0x180006ffc  mov     [rdi], rbx
0x180006fff  mov     [rsi+30h], r14
0x180007003  lea     rcx, [rsp+58h+arg_8]
0x180007008  call    ?Reset@?$InvasivePtr@VAppHostConfigPathNavigator@@@@QEAAXXZ; InvasivePtr<AppHostConfigPathNavigator>::Reset(void)
0x18000700d  nop
0x18000700e  xor     eax, eax
0x180007010  jmp     short loc_18000701D
0x180007012  mov     eax, [rsp+58h+var_38]
0x180007016  jmp     short loc_18000701D
0x180007018  mov     eax, 8000FFFFh
0x18000701d  add     rsp, 38h
0x180007021  pop     r14
0x180007023  pop     rdi
0x180007024  pop     rsi
0x180007025  pop     rbx
0x180007026  retn
```
