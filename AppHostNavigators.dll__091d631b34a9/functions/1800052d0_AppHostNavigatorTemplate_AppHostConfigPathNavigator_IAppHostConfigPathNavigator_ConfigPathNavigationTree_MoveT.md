# AppHostNavigatorTemplate<AppHostConfigPathNavigator,IAppHostConfigPathNavigator,ConfigPathNavigationTree>::MoveTo(IXPathNavigator *)

- ea: `0x1800052d0`
- end: `0x180005388`
- name: `?MoveTo@?$AppHostNavigatorTemplate@VAppHostConfigPathNavigator@@UIAppHostConfigPathNavigator@@VConfigPathNavigationTree@@@@UEAAJPEAUIXPathNavigator@@@Z`
- size: `184`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x1800039ec`
- `0x180003a1c`
- `0x1800052d0`
- `0x180005920`

## pseudocode

```c
__int64 __fastcall AppHostNavigatorTemplate<AppHostConfigPathNavigator,IAppHostConfigPathNavigator,ConfigPathNavigationTree>::MoveTo(
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
  v4 = AppHostNavigatorTemplate<AppHostConfigPathNavigator,IAppHostConfigPathNavigator,ConfigPathNavigationTree>::TryCastAsDerivedType(
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
0x1800052d0  push    rbx
0x1800052d2  push    rsi
0x1800052d3  push    rdi
0x1800052d4  push    r14
0x1800052d6  sub     rsp, 38h
0x1800052da  mov     rax, rdx
0x1800052dd  mov     rsi, rcx
0x1800052e0  test    rdx, rdx
0x1800052e3  jnz     short loc_1800052EF
0x1800052e5  mov     eax, 80070057h
0x1800052ea  jmp     loc_18000537D
0x1800052ef  mov     [rsp+58h+arg_8], 0
0x1800052f8  lea     rdx, [rsp+58h+arg_8]
0x1800052fd  mov     rcx, rax
0x180005300  call    ?TryCastAsDerivedType@?$AppHostNavigatorTemplate@VAppHostConfigPathNavigator@@UIAppHostConfigPathNavigator@@VConfigPathNavigationTree@@@@SAJPEAUIXPathNavigator@@PEAPEAVAppHostConfigPathNavigator@@@Z; AppHostNavigatorTemplate<AppHostConfigPathNavigator,IAppHostConfigPathNavigator,ConfigPathNavigationTree>::TryCastAsDerivedType(IXPathNavigator *,AppHostConfigPathNavigator * *)
0x180005305  mov     ebx, eax
0x180005307  test    eax, eax
0x180005309  jns     short loc_180005319
0x18000530b  lea     rcx, [rsp+58h+arg_8]
0x180005310  call    ?Reset@?$InvasivePtr@VAppHostConfigPathNavigator@@@@QEAAXXZ; InvasivePtr<AppHostConfigPathNavigator>::Reset(void)
0x180005315  mov     eax, ebx
0x180005317  jmp     short loc_18000537D
0x180005319  mov     rax, [rsp+58h+arg_8]
0x18000531e  test    rax, rax
0x180005321  jnz     short loc_180005334
0x180005323  lea     rcx, [rsp+58h+arg_8]
0x180005328  call    ?Reset@?$InvasivePtr@VAppHostConfigPathNavigator@@@@QEAAXXZ; InvasivePtr<AppHostConfigPathNavigator>::Reset(void)
0x18000532d  mov     eax, 1
0x180005332  jmp     short loc_18000537D
0x180005334  mov     r14, [rax+30h]
0x180005338  mov     rbx, [rax+28h]
0x18000533c  mov     ecx, [rax+20h]
0x18000533f  mov     [rsi+20h], ecx
0x180005342  lea     rdi, [rsi+28h]
0x180005346  cmp     [rdi], rbx
0x180005349  jz      short loc_18000535F
0x18000534b  test    rbx, rbx
0x18000534e  jz      short loc_180005354
0x180005350  lock inc dword ptr [rbx+8]
0x180005354  mov     rcx, rdi
0x180005357  call    ?Reset@?$InvasivePtr@VConfigLocationsTree@@@@QEAAXXZ; InvasivePtr<ConfigLocationsTree>::Reset(void)
0x18000535c  mov     [rdi], rbx
0x18000535f  mov     [rsi+30h], r14
0x180005363  lea     rcx, [rsp+58h+arg_8]
0x180005368  call    ?Reset@?$InvasivePtr@VAppHostConfigPathNavigator@@@@QEAAXXZ; InvasivePtr<AppHostConfigPathNavigator>::Reset(void)
0x18000536d  nop
0x18000536e  xor     eax, eax
0x180005370  jmp     short loc_18000537D
0x180005372  mov     eax, [rsp+58h+var_38]
0x180005376  jmp     short loc_18000537D
0x180005378  mov     eax, 8000FFFFh
0x18000537d  add     rsp, 38h
0x180005381  pop     r14
0x180005383  pop     rdi
0x180005384  pop     rsi
0x180005385  pop     rbx
0x180005386  retn
```
