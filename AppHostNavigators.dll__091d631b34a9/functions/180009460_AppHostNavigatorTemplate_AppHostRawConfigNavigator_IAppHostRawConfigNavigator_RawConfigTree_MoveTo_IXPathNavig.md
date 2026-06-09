# AppHostNavigatorTemplate<AppHostRawConfigNavigator,IAppHostRawConfigNavigator,RawConfigTree>::MoveTo(IXPathNavigator *)

- ea: `0x180009460`
- end: `0x180009518`
- name: `?MoveTo@?$AppHostNavigatorTemplate@VAppHostRawConfigNavigator@@UIAppHostRawConfigNavigator@@VRawConfigTree@@@@UEAAJPEAUIXPathNavigator@@@Z`
- size: `184`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x1800039ec`
- `0x180003a1c`
- `0x180009460`
- `0x180009650`

## pseudocode

```c
__int64 __fastcall AppHostNavigatorTemplate<AppHostRawConfigNavigator,IAppHostRawConfigNavigator,RawConfigTree>::MoveTo(
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
  v4 = AppHostNavigatorTemplate<AppHostRawConfigNavigator,IAppHostRawConfigNavigator,RawConfigTree>::TryCastAsDerivedType(
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
0x180009460  push    rbx
0x180009462  push    rsi
0x180009463  push    rdi
0x180009464  push    r14
0x180009466  sub     rsp, 38h
0x18000946a  mov     rax, rdx
0x18000946d  mov     rsi, rcx
0x180009470  test    rdx, rdx
0x180009473  jnz     short loc_18000947F
0x180009475  mov     eax, 80070057h
0x18000947a  jmp     loc_18000950D
0x18000947f  mov     [rsp+58h+arg_8], 0
0x180009488  lea     rdx, [rsp+58h+arg_8]
0x18000948d  mov     rcx, rax
0x180009490  call    ?TryCastAsDerivedType@?$AppHostNavigatorTemplate@VAppHostRawConfigNavigator@@UIAppHostRawConfigNavigator@@VRawConfigTree@@@@SAJPEAUIXPathNavigator@@PEAPEAVAppHostRawConfigNavigator@@@Z; AppHostNavigatorTemplate<AppHostRawConfigNavigator,IAppHostRawConfigNavigator,RawConfigTree>::TryCastAsDerivedType(IXPathNavigator *,AppHostRawConfigNavigator * *)
0x180009495  mov     ebx, eax
0x180009497  test    eax, eax
0x180009499  jns     short loc_1800094A9
0x18000949b  lea     rcx, [rsp+58h+arg_8]
0x1800094a0  call    ?Reset@?$InvasivePtr@VAppHostConfigPathNavigator@@@@QEAAXXZ; InvasivePtr<AppHostConfigPathNavigator>::Reset(void)
0x1800094a5  mov     eax, ebx
0x1800094a7  jmp     short loc_18000950D
0x1800094a9  mov     rax, [rsp+58h+arg_8]
0x1800094ae  test    rax, rax
0x1800094b1  jnz     short loc_1800094C4
0x1800094b3  lea     rcx, [rsp+58h+arg_8]
0x1800094b8  call    ?Reset@?$InvasivePtr@VAppHostConfigPathNavigator@@@@QEAAXXZ; InvasivePtr<AppHostConfigPathNavigator>::Reset(void)
0x1800094bd  mov     eax, 1
0x1800094c2  jmp     short loc_18000950D
0x1800094c4  mov     r14, [rax+30h]
0x1800094c8  mov     rbx, [rax+28h]
0x1800094cc  mov     ecx, [rax+20h]
0x1800094cf  mov     [rsi+20h], ecx
0x1800094d2  lea     rdi, [rsi+28h]
0x1800094d6  cmp     [rdi], rbx
0x1800094d9  jz      short loc_1800094EF
0x1800094db  test    rbx, rbx
0x1800094de  jz      short loc_1800094E4
0x1800094e0  lock inc dword ptr [rbx+8]
0x1800094e4  mov     rcx, rdi
0x1800094e7  call    ?Reset@?$InvasivePtr@VConfigLocationsTree@@@@QEAAXXZ; InvasivePtr<ConfigLocationsTree>::Reset(void)
0x1800094ec  mov     [rdi], rbx
0x1800094ef  mov     [rsi+30h], r14
0x1800094f3  lea     rcx, [rsp+58h+arg_8]
0x1800094f8  call    ?Reset@?$InvasivePtr@VAppHostConfigPathNavigator@@@@QEAAXXZ; InvasivePtr<AppHostConfigPathNavigator>::Reset(void)
0x1800094fd  nop
0x1800094fe  xor     eax, eax
0x180009500  jmp     short loc_18000950D
0x180009502  mov     eax, [rsp+58h+var_38]
0x180009506  jmp     short loc_18000950D
0x180009508  mov     eax, 8000FFFFh
0x18000950d  add     rsp, 38h
0x180009511  pop     r14
0x180009513  pop     rdi
0x180009514  pop     rsi
0x180009515  pop     rbx
0x180009516  retn
```
