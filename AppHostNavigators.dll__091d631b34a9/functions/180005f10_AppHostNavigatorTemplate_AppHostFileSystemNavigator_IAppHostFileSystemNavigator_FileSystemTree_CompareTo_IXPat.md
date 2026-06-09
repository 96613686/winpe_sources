# AppHostNavigatorTemplate<AppHostFileSystemNavigator,IAppHostFileSystemNavigator,FileSystemTree>::CompareTo(IXPathNavigator *,long *)

- ea: `0x180005f10`
- end: `0x180005fd5`
- name: `?CompareTo@?$AppHostNavigatorTemplate@VAppHostFileSystemNavigator@@UIAppHostFileSystemNavigator@@VFileSystemTree@@@@UEAAJPEAUIXPathNavigator@@PEAJ@Z`
- size: `197`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800039ec`
- `0x180005f10`
- `0x180006630`
- `0x18000fbe8`
- `0x180011064`

## pseudocode

```c
__int64 __fastcall AppHostNavigatorTemplate<AppHostFileSystemNavigator,IAppHostFileSystemNavigator,FileSystemTree>::CompareTo(
        __int64 a1,
        __int64 a2,
        _DWORD *a3)
{
  HINSTANCE v5; // rcx
  int v6; // edi
  __int64 v8; // r9
  unsigned int v9; // ebx
  struct NavigationNodeBase *v10; // r8
  struct NavigationNodeBase *v11; // rcx
  __int64 v12; // [rsp+48h] [rbp+10h] BYREF

  if ( !a2 || !a3 )
    return 2147942487LL;
  v12 = 0;
  v6 = AppHostNavigatorTemplate<AppHostFileSystemNavigator,IAppHostFileSystemNavigator,FileSystemTree>::TryCastAsDerivedType(
         a2,
         &v12);
  if ( v6 >= 0 )
  {
    v8 = v12;
    if ( v12 )
    {
      *a3 = 0;
      v10 = *(struct NavigationNodeBase **)(v8 + 48);
      v11 = *(struct NavigationNodeBase **)(a1 + 48);
      if ( v11 != v10 )
        *a3 = NavigationNodeBase::ComparePositions(v11, *(_DWORD *)(a1 + 32), v10, *(_DWORD *)(v8 + 32));
      InvasivePtr<AppHostConfigPathNavigator>::Reset(&v12);
      return 0;
    }
    else
    {
      v9 = AppHostNavigatorException::SetCannotComparePositionOfDifferentTypesException(v5);
      InvasivePtr<AppHostConfigPathNavigator>::Reset(&v12);
      return v9;
    }
  }
  else
  {
    InvasivePtr<AppHostConfigPathNavigator>::Reset(&v12);
    return (unsigned int)v6;
  }
}

```

## disassembly

```asm
0x180005f10  mov     r11, rsp
0x180005f13  mov     [r11+8], rbx
0x180005f17  mov     [r11+18h], rsi
0x180005f1b  push    rdi
0x180005f1c  sub     rsp, 30h
0x180005f20  mov     rbx, r8
0x180005f23  mov     rax, rdx
0x180005f26  mov     rsi, rcx
0x180005f29  test    rdx, rdx
0x180005f2c  jz      loc_180005FBF
0x180005f32  test    rbx, rbx
0x180005f35  jz      loc_180005FBF
0x180005f3b  mov     qword ptr [r11+10h], 0
0x180005f43  lea     rdx, [r11+10h]
0x180005f47  mov     rcx, rax
0x180005f4a  call    ?TryCastAsDerivedType@?$AppHostNavigatorTemplate@VAppHostFileSystemNavigator@@UIAppHostFileSystemNavigator@@VFileSystemTree@@@@SAJPEAUIXPathNavigator@@PEAPEAVAppHostFileSystemNavigator@@@Z; AppHostNavigatorTemplate<AppHostFileSystemNavigator,IAppHostFileSystemNavigator,FileSystemTree>::TryCastAsDerivedType(IXPathNavigator *,AppHostFileSystemNavigator * *)
0x180005f4f  mov     edi, eax
0x180005f51  test    eax, eax
0x180005f53  jns     short loc_180005F63
0x180005f55  lea     rcx, [rsp+38h+arg_8]
0x180005f5a  call    ?Reset@?$InvasivePtr@VAppHostConfigPathNavigator@@@@QEAAXXZ; InvasivePtr<AppHostConfigPathNavigator>::Reset(void)
0x180005f5f  mov     eax, edi
0x180005f61  jmp     short loc_180005FC4
0x180005f63  mov     r9, [rsp+38h+arg_8]
0x180005f68  test    r9, r9
0x180005f6b  jnz     short loc_180005F82
0x180005f6d  call    ?SetCannotComparePositionOfDifferentTypesException@AppHostNavigatorException@@SAJXZ; AppHostNavigatorException::SetCannotComparePositionOfDifferentTypesException(void)
0x180005f72  mov     ebx, eax
0x180005f74  lea     rcx, [rsp+38h+arg_8]
0x180005f79  call    ?Reset@?$InvasivePtr@VAppHostConfigPathNavigator@@@@QEAAXXZ; InvasivePtr<AppHostConfigPathNavigator>::Reset(void)
0x180005f7e  mov     eax, ebx
0x180005f80  jmp     short loc_180005FC4
0x180005f82  mov     dword ptr [rbx], 0
0x180005f88  mov     r8, [r9+30h]; struct NavigationNodeBase *
0x180005f8c  mov     rcx, [rsi+30h]; struct NavigationNodeBase *
0x180005f90  cmp     rcx, r8
0x180005f93  jz      short loc_180005FA3
0x180005f95  mov     r9d, [r9+20h]; unsigned int
0x180005f99  mov     edx, [rsi+20h]; unsigned int
0x180005f9c  call    ?ComparePositions@NavigationNodeBase@@SAJPEAV1@K0K@Z; NavigationNodeBase::ComparePositions(NavigationNodeBase *,ulong,NavigationNodeBase *,ulong)
0x180005fa1  mov     [rbx], eax
0x180005fa3  lea     rcx, [rsp+38h+arg_8]
0x180005fa8  call    ?Reset@?$InvasivePtr@VAppHostConfigPathNavigator@@@@QEAAXXZ; InvasivePtr<AppHostConfigPathNavigator>::Reset(void)
0x180005fad  nop
0x180005fae  xor     eax, eax
0x180005fb0  jmp     short loc_180005FC4
0x180005fb2  mov     eax, [rsp+38h+var_18]
0x180005fb6  jmp     short loc_180005FBD
0x180005fb8  mov     eax, 8000FFFFh
0x180005fbd  jmp     short loc_180005FC4
0x180005fbf  mov     eax, 80070057h
0x180005fc4  mov     rbx, [rsp+38h+arg_0]
0x180005fc9  mov     rsi, [rsp+38h+arg_10]
0x180005fce  add     rsp, 30h
0x180005fd2  pop     rdi
0x180005fd3  retn
```
