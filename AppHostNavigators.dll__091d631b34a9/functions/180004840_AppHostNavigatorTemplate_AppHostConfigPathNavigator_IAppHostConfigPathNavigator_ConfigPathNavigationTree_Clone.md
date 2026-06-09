# AppHostNavigatorTemplate<AppHostConfigPathNavigator,IAppHostConfigPathNavigator,ConfigPathNavigationTree>::Clone(AppHostConfigPathNavigator * *)

- ea: `0x180004840`
- end: `0x1800048f5`
- name: `?Clone@?$AppHostNavigatorTemplate@VAppHostConfigPathNavigator@@UIAppHostConfigPathNavigator@@VConfigPathNavigationTree@@@@QEAAJPEAPEAVAppHostConfigPathNavigator@@@Z`
- size: `181`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180004900`
- `0x1800098a0`
- `0x18000eac0`
- `0x18000ec40`
- `0x18001076c`

## callees

- `0x180001194`
- `0x1800039ec`
- `0x1800040fc`
- `0x180004840`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall AppHostNavigatorTemplate<AppHostConfigPathNavigator,IAppHostConfigPathNavigator,ConfigPathNavigationTree>::Clone(
        __int64 a1,
        AppHostConfigPathNavigator **a2)
{
  _OWORD *v4; // rax
  AppHostConfigPathNavigator *v5; // rbx
  int v6; // edi
  AppHostConfigPathNavigator *v8; // [rsp+40h] [rbp+18h] BYREF
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
    v5 = AppHostConfigPathNavigator::AppHostConfigPathNavigator((AppHostConfigPathNavigator *)v4);
  }
  else
  {
    v5 = 0;
  }
  InvasivePtr<AppHostConfigPathNavigator>::Reset((__int64 *)&v8);
  v8 = v5;
  if ( v5 )
  {
    v6 = (*(__int64 (__fastcall **)(AppHostConfigPathNavigator *, __int64))(*(_QWORD *)v5 + 168LL))(v5, a1);
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
0x180004840  mov     [rsp+arg_0], rbx
0x180004845  mov     [rsp+arg_8], rsi
0x18000484a  push    rdi
0x18000484b  sub     rsp, 20h
0x18000484f  mov     rsi, rdx
0x180004852  mov     rdi, rcx
0x180004855  mov     [rsp+28h+arg_10], 0
0x18000485e  mov     ecx, 38h ; '8'; Size
0x180004863  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004868  mov     [rsp+28h+arg_18], rax
0x18000486d  test    rax, rax
0x180004870  jz      short loc_180004893
0x180004872  xorps   xmm0, xmm0
0x180004875  xor     ecx, ecx
0x180004877  movups  xmmword ptr [rax], xmm0
0x18000487a  movups  xmmword ptr [rax+10h], xmm0
0x18000487e  movups  xmmword ptr [rax+20h], xmm0
0x180004882  mov     [rax+30h], rcx
0x180004886  mov     rcx, rax; this
0x180004889  call    ??0AppHostConfigPathNavigator@@QEAA@XZ; AppHostConfigPathNavigator::AppHostConfigPathNavigator(void)
0x18000488e  mov     rbx, rax
0x180004891  jmp     short loc_180004895
0x180004893  xor     ebx, ebx
0x180004895  lea     rcx, [rsp+28h+arg_10]
0x18000489a  call    ?Reset@?$InvasivePtr@VAppHostConfigPathNavigator@@@@QEAAXXZ; InvasivePtr<AppHostConfigPathNavigator>::Reset(void)
0x18000489f  mov     [rsp+28h+arg_10], rbx
0x1800048a4  test    rbx, rbx
0x1800048a7  jnz     short loc_1800048B0
0x1800048a9  mov     edi, 8007000Eh
0x1800048ae  jmp     short loc_1800048D9
0x1800048b0  mov     rax, [rbx]
0x1800048b3  mov     rdx, rdi
0x1800048b6  mov     rcx, rbx
0x1800048b9  mov     rax, [rax+0A8h]
0x1800048c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048c5  mov     edi, eax
0x1800048c7  test    eax, eax
0x1800048c9  js      short loc_1800048D9
0x1800048cb  mov     [rsp+28h+arg_10], 0
0x1800048d4  mov     [rsi], rbx
0x1800048d7  xor     edi, edi
0x1800048d9  lea     rcx, [rsp+28h+arg_10]
0x1800048de  call    ?Reset@?$InvasivePtr@VAppHostConfigPathNavigator@@@@QEAAXXZ; InvasivePtr<AppHostConfigPathNavigator>::Reset(void)
0x1800048e3  mov     eax, edi
0x1800048e5  mov     rbx, [rsp+28h+arg_0]
0x1800048ea  mov     rsi, [rsp+28h+arg_8]
0x1800048ef  add     rsp, 20h
0x1800048f3  pop     rdi
0x1800048f4  retn
```
