# AppHostNavigatorTemplate<AppHostFileSystemNavigator,IAppHostFileSystemNavigator,FileSystemTree>::Clone(AppHostFileSystemNavigator * *)

- ea: `0x180005dc8`
- end: `0x180005e7d`
- name: `?Clone@?$AppHostNavigatorTemplate@VAppHostFileSystemNavigator@@UIAppHostFileSystemNavigator@@VFileSystemTree@@@@QEAAJPEAPEAVAppHostFileSystemNavigator@@@Z`
- size: `181`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180005e90`
- `0x18000c770`
- `0x18000cc48`

## callees

- `0x180001194`
- `0x1800039ec`
- `0x180005abc`
- `0x180005dc8`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall AppHostNavigatorTemplate<AppHostFileSystemNavigator,IAppHostFileSystemNavigator,FileSystemTree>::Clone(
        __int64 a1,
        AppHostFileSystemNavigator **a2)
{
  _OWORD *v4; // rax
  AppHostFileSystemNavigator *v5; // rbx
  int v6; // edi
  AppHostFileSystemNavigator *v8; // [rsp+40h] [rbp+18h] BYREF
  _OWORD *v9; // [rsp+48h] [rbp+20h]

  v8 = 0;
  v4 = operator new(0x38u);
  v9 = v4;
  if ( v4 )
  {
    *v4 = 0;
    v4[1] = 0;
    v4[2] = 0;
    *((_QWORD *)v4 + 6) = 0;
    v5 = AppHostFileSystemNavigator::AppHostFileSystemNavigator((AppHostFileSystemNavigator *)v4);
  }
  else
  {
    v5 = 0;
  }
  InvasivePtr<AppHostConfigPathNavigator>::Reset((__int64 *)&v8);
  v8 = v5;
  if ( v5 )
  {
    v6 = (*(__int64 (__fastcall **)(AppHostFileSystemNavigator *, __int64))(*(_QWORD *)v5 + 168LL))(v5, a1);
    if ( v6 >= 0 )
    {
      v8 = 0;
      *a2 = v5;
      v6 = 0;
    }
  }
  else
  {
    v6 = -2147024882;
  }
  InvasivePtr<AppHostConfigPathNavigator>::Reset((__int64 *)&v8);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180005dc8  mov     [rsp+arg_0], rbx
0x180005dcd  mov     [rsp+arg_8], rsi
0x180005dd2  push    rdi
0x180005dd3  sub     rsp, 20h
0x180005dd7  mov     rsi, rdx
0x180005dda  mov     rdi, rcx
0x180005ddd  mov     [rsp+28h+arg_10], 0
0x180005de6  mov     ecx, 38h ; '8'; Size
0x180005deb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005df0  mov     [rsp+28h+arg_18], rax
0x180005df5  test    rax, rax
0x180005df8  jz      short loc_180005E1B
0x180005dfa  xorps   xmm0, xmm0
0x180005dfd  xor     ecx, ecx
0x180005dff  movups  xmmword ptr [rax], xmm0
0x180005e02  movups  xmmword ptr [rax+10h], xmm0
0x180005e06  movups  xmmword ptr [rax+20h], xmm0
0x180005e0a  mov     [rax+30h], rcx
0x180005e0e  mov     rcx, rax; this
0x180005e11  call    ??0AppHostFileSystemNavigator@@QEAA@XZ; AppHostFileSystemNavigator::AppHostFileSystemNavigator(void)
0x180005e16  mov     rbx, rax
0x180005e19  jmp     short loc_180005E1D
0x180005e1b  xor     ebx, ebx
0x180005e1d  lea     rcx, [rsp+28h+arg_10]
0x180005e22  call    ?Reset@?$InvasivePtr@VAppHostConfigPathNavigator@@@@QEAAXXZ; InvasivePtr<AppHostConfigPathNavigator>::Reset(void)
0x180005e27  mov     [rsp+28h+arg_10], rbx
0x180005e2c  test    rbx, rbx
0x180005e2f  jnz     short loc_180005E38
0x180005e31  mov     edi, 8007000Eh
0x180005e36  jmp     short loc_180005E61
0x180005e38  mov     rax, [rbx]
0x180005e3b  mov     rdx, rdi
0x180005e3e  mov     rcx, rbx
0x180005e41  mov     rax, [rax+0A8h]
0x180005e48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e4d  mov     edi, eax
0x180005e4f  test    eax, eax
0x180005e51  js      short loc_180005E61
0x180005e53  mov     [rsp+28h+arg_10], 0
0x180005e5c  mov     [rsi], rbx
0x180005e5f  xor     edi, edi
0x180005e61  lea     rcx, [rsp+28h+arg_10]
0x180005e66  call    ?Reset@?$InvasivePtr@VAppHostConfigPathNavigator@@@@QEAAXXZ; InvasivePtr<AppHostConfigPathNavigator>::Reset(void)
0x180005e6b  mov     eax, edi
0x180005e6d  mov     rbx, [rsp+28h+arg_0]
0x180005e72  mov     rsi, [rsp+28h+arg_8]
0x180005e77  add     rsp, 20h
0x180005e7b  pop     rdi
0x180005e7c  retn
```
