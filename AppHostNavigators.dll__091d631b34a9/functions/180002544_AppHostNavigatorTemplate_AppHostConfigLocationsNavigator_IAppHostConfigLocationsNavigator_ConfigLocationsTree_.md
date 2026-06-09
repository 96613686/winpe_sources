# AppHostNavigatorTemplate<AppHostConfigLocationsNavigator,IAppHostConfigLocationsNavigator,ConfigLocationsTree>::Clone(AppHostConfigLocationsNavigator * *)

- ea: `0x180002544`
- end: `0x1800025f9`
- name: `?Clone@?$AppHostNavigatorTemplate@VAppHostConfigLocationsNavigator@@UIAppHostConfigLocationsNavigator@@VConfigLocationsTree@@@@QEAAJPEAPEAVAppHostConfigLocationsNavigator@@@Z`
- size: `181`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180002600`
- `0x1800113b0`

## callees

- `0x180001194`
- `0x180002068`
- `0x180002544`
- `0x1800039ec`
- `0x180014010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AppHostNavigatorTemplate<AppHostConfigLocationsNavigator,IAppHostConfigLocationsNavigator,ConfigLocationsTree>::Clone(
        __int64 a1,
        AppHostConfigLocationsNavigator **a2)
{
  _OWORD *v4; // rax
  AppHostConfigLocationsNavigator *v5; // rbx
  int v6; // edi
  AppHostConfigLocationsNavigator *v8; // [rsp+40h] [rbp+18h] BYREF
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
    v5 = AppHostConfigLocationsNavigator::AppHostConfigLocationsNavigator((AppHostConfigLocationsNavigator *)v4);
  }
  else
  {
    v5 = 0;
  }
  InvasivePtr<AppHostConfigPathNavigator>::Reset((__int64 *)&v8);
  v8 = v5;
  if ( v5 )
  {
    v6 = (*(__int64 (__fastcall **)(AppHostConfigLocationsNavigator *, __int64))(*(_QWORD *)v5 + 168LL))(v5, a1);
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
0x180002544  mov     [rsp+arg_0], rbx
0x180002549  mov     [rsp+arg_8], rsi
0x18000254e  push    rdi
0x18000254f  sub     rsp, 20h
0x180002553  mov     rsi, rdx
0x180002556  mov     rdi, rcx
0x180002559  mov     [rsp+28h+arg_10], 0
0x180002562  mov     ecx, 38h ; '8'; Size
0x180002567  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000256c  mov     [rsp+28h+arg_18], rax
0x180002571  test    rax, rax
0x180002574  jz      short loc_180002597
0x180002576  xorps   xmm0, xmm0
0x180002579  xor     ecx, ecx
0x18000257b  movups  xmmword ptr [rax], xmm0
0x18000257e  movups  xmmword ptr [rax+10h], xmm0
0x180002582  movups  xmmword ptr [rax+20h], xmm0
0x180002586  mov     [rax+30h], rcx
0x18000258a  mov     rcx, rax; this
0x18000258d  call    ??0AppHostConfigLocationsNavigator@@QEAA@XZ; AppHostConfigLocationsNavigator::AppHostConfigLocationsNavigator(void)
0x180002592  mov     rbx, rax
0x180002595  jmp     short loc_180002599
0x180002597  xor     ebx, ebx
0x180002599  lea     rcx, [rsp+28h+arg_10]
0x18000259e  call    ?Reset@?$InvasivePtr@VAppHostConfigPathNavigator@@@@QEAAXXZ; InvasivePtr<AppHostConfigPathNavigator>::Reset(void)
0x1800025a3  mov     [rsp+28h+arg_10], rbx
0x1800025a8  test    rbx, rbx
0x1800025ab  jnz     short loc_1800025B4
0x1800025ad  mov     edi, 8007000Eh
0x1800025b2  jmp     short loc_1800025DD
0x1800025b4  mov     rax, [rbx]
0x1800025b7  mov     rdx, rdi
0x1800025ba  mov     rcx, rbx
0x1800025bd  mov     rax, [rax+0A8h]
0x1800025c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800025c9  mov     edi, eax
0x1800025cb  test    eax, eax
0x1800025cd  js      short loc_1800025DD
0x1800025cf  mov     [rsp+28h+arg_10], 0
0x1800025d8  mov     [rsi], rbx
0x1800025db  xor     edi, edi
0x1800025dd  lea     rcx, [rsp+28h+arg_10]
0x1800025e2  call    ?Reset@?$InvasivePtr@VAppHostConfigPathNavigator@@@@QEAAXXZ; InvasivePtr<AppHostConfigPathNavigator>::Reset(void)
0x1800025e7  mov     eax, edi
0x1800025e9  mov     rbx, [rsp+28h+arg_0]
0x1800025ee  mov     rsi, [rsp+28h+arg_8]
0x1800025f3  add     rsp, 20h
0x1800025f7  pop     rdi
0x1800025f8  retn
```
