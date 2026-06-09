# AppHostNavigatorTemplate<AppHostFileSystemNavigator,IAppHostFileSystemNavigator,FileSystemTree>::MoveTo(IXPathNavigator *)

- ea: `0x1800062a0`
- end: `0x180006358`
- name: `?MoveTo@?$AppHostNavigatorTemplate@VAppHostFileSystemNavigator@@UIAppHostFileSystemNavigator@@VFileSystemTree@@@@UEAAJPEAUIXPathNavigator@@@Z`
- size: `184`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x1800039ec`
- `0x180003a1c`
- `0x1800062a0`
- `0x180006630`

## pseudocode

```c
__int64 __fastcall AppHostNavigatorTemplate<AppHostFileSystemNavigator,IAppHostFileSystemNavigator,FileSystemTree>::MoveTo(
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
  v4 = AppHostNavigatorTemplate<AppHostFileSystemNavigator,IAppHostFileSystemNavigator,FileSystemTree>::TryCastAsDerivedType(
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
0x1800062a0  push    rbx
0x1800062a2  push    rsi
0x1800062a3  push    rdi
0x1800062a4  push    r14
0x1800062a6  sub     rsp, 38h
0x1800062aa  mov     rax, rdx
0x1800062ad  mov     rsi, rcx
0x1800062b0  test    rdx, rdx
0x1800062b3  jnz     short loc_1800062BF
0x1800062b5  mov     eax, 80070057h
0x1800062ba  jmp     loc_18000634D
0x1800062bf  mov     [rsp+58h+arg_8], 0
0x1800062c8  lea     rdx, [rsp+58h+arg_8]
0x1800062cd  mov     rcx, rax
0x1800062d0  call    ?TryCastAsDerivedType@?$AppHostNavigatorTemplate@VAppHostFileSystemNavigator@@UIAppHostFileSystemNavigator@@VFileSystemTree@@@@SAJPEAUIXPathNavigator@@PEAPEAVAppHostFileSystemNavigator@@@Z; AppHostNavigatorTemplate<AppHostFileSystemNavigator,IAppHostFileSystemNavigator,FileSystemTree>::TryCastAsDerivedType(IXPathNavigator *,AppHostFileSystemNavigator * *)
0x1800062d5  mov     ebx, eax
0x1800062d7  test    eax, eax
0x1800062d9  jns     short loc_1800062E9
0x1800062db  lea     rcx, [rsp+58h+arg_8]
0x1800062e0  call    ?Reset@?$InvasivePtr@VAppHostConfigPathNavigator@@@@QEAAXXZ; InvasivePtr<AppHostConfigPathNavigator>::Reset(void)
0x1800062e5  mov     eax, ebx
0x1800062e7  jmp     short loc_18000634D
0x1800062e9  mov     rax, [rsp+58h+arg_8]
0x1800062ee  test    rax, rax
0x1800062f1  jnz     short loc_180006304
0x1800062f3  lea     rcx, [rsp+58h+arg_8]
0x1800062f8  call    ?Reset@?$InvasivePtr@VAppHostConfigPathNavigator@@@@QEAAXXZ; InvasivePtr<AppHostConfigPathNavigator>::Reset(void)
0x1800062fd  mov     eax, 1
0x180006302  jmp     short loc_18000634D
0x180006304  mov     r14, [rax+30h]
0x180006308  mov     rbx, [rax+28h]
0x18000630c  mov     ecx, [rax+20h]
0x18000630f  mov     [rsi+20h], ecx
0x180006312  lea     rdi, [rsi+28h]
0x180006316  cmp     [rdi], rbx
0x180006319  jz      short loc_18000632F
0x18000631b  test    rbx, rbx
0x18000631e  jz      short loc_180006324
0x180006320  lock inc dword ptr [rbx+8]
0x180006324  mov     rcx, rdi
0x180006327  call    ?Reset@?$InvasivePtr@VConfigLocationsTree@@@@QEAAXXZ; InvasivePtr<ConfigLocationsTree>::Reset(void)
0x18000632c  mov     [rdi], rbx
0x18000632f  mov     [rsi+30h], r14
0x180006333  lea     rcx, [rsp+58h+arg_8]
0x180006338  call    ?Reset@?$InvasivePtr@VAppHostConfigPathNavigator@@@@QEAAXXZ; InvasivePtr<AppHostConfigPathNavigator>::Reset(void)
0x18000633d  nop
0x18000633e  xor     eax, eax
0x180006340  jmp     short loc_18000634D
0x180006342  mov     eax, [rsp+58h+var_38]
0x180006346  jmp     short loc_18000634D
0x180006348  mov     eax, 8000FFFFh
0x18000634d  add     rsp, 38h
0x180006351  pop     r14
0x180006353  pop     rdi
0x180006354  pop     rsi
0x180006355  pop     rbx
0x180006356  retn
```
