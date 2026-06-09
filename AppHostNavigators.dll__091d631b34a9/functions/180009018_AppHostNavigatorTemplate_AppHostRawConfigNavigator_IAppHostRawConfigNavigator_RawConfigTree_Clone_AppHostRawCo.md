# AppHostNavigatorTemplate<AppHostRawConfigNavigator,IAppHostRawConfigNavigator,RawConfigTree>::Clone(AppHostRawConfigNavigator * *)

- ea: `0x180009018`
- end: `0x1800090cd`
- name: `?Clone@?$AppHostNavigatorTemplate@VAppHostRawConfigNavigator@@UIAppHostRawConfigNavigator@@VRawConfigTree@@@@QEAAJPEAPEAVAppHostRawConfigNavigator@@@Z`
- size: `181`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800090e0`

## callees

- `0x180001194`
- `0x1800039ec`
- `0x180008f18`
- `0x180009018`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall AppHostNavigatorTemplate<AppHostRawConfigNavigator,IAppHostRawConfigNavigator,RawConfigTree>::Clone(
        __int64 a1,
        AppHostRawConfigNavigator **a2)
{
  _OWORD *v4; // rax
  AppHostRawConfigNavigator *v5; // rbx
  int v6; // edi
  AppHostRawConfigNavigator *v8; // [rsp+40h] [rbp+18h] BYREF
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
    v5 = AppHostRawConfigNavigator::AppHostRawConfigNavigator((AppHostRawConfigNavigator *)v4);
  }
  else
  {
    v5 = 0;
  }
  InvasivePtr<AppHostConfigPathNavigator>::Reset((__int64 *)&v8);
  v8 = v5;
  if ( v5 )
  {
    v6 = (*(__int64 (__fastcall **)(AppHostRawConfigNavigator *, __int64))(*(_QWORD *)v5 + 168LL))(v5, a1);
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
0x180009018  mov     [rsp+arg_0], rbx
0x18000901d  mov     [rsp+arg_8], rsi
0x180009022  push    rdi
0x180009023  sub     rsp, 20h
0x180009027  mov     rsi, rdx
0x18000902a  mov     rdi, rcx
0x18000902d  mov     [rsp+28h+arg_10], 0
0x180009036  mov     ecx, 38h ; '8'; Size
0x18000903b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009040  mov     [rsp+28h+arg_18], rax
0x180009045  test    rax, rax
0x180009048  jz      short loc_18000906B
0x18000904a  xorps   xmm0, xmm0
0x18000904d  xor     ecx, ecx
0x18000904f  movups  xmmword ptr [rax], xmm0
0x180009052  movups  xmmword ptr [rax+10h], xmm0
0x180009056  movups  xmmword ptr [rax+20h], xmm0
0x18000905a  mov     [rax+30h], rcx
0x18000905e  mov     rcx, rax; this
0x180009061  call    ??0AppHostRawConfigNavigator@@QEAA@XZ; AppHostRawConfigNavigator::AppHostRawConfigNavigator(void)
0x180009066  mov     rbx, rax
0x180009069  jmp     short loc_18000906D
0x18000906b  xor     ebx, ebx
0x18000906d  lea     rcx, [rsp+28h+arg_10]
0x180009072  call    ?Reset@?$InvasivePtr@VAppHostConfigPathNavigator@@@@QEAAXXZ; InvasivePtr<AppHostConfigPathNavigator>::Reset(void)
0x180009077  mov     [rsp+28h+arg_10], rbx
0x18000907c  test    rbx, rbx
0x18000907f  jnz     short loc_180009088
0x180009081  mov     edi, 8007000Eh
0x180009086  jmp     short loc_1800090B1
0x180009088  mov     rax, [rbx]
0x18000908b  mov     rdx, rdi
0x18000908e  mov     rcx, rbx
0x180009091  mov     rax, [rax+0A8h]
0x180009098  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000909d  mov     edi, eax
0x18000909f  test    eax, eax
0x1800090a1  js      short loc_1800090B1
0x1800090a3  mov     [rsp+28h+arg_10], 0
0x1800090ac  mov     [rsi], rbx
0x1800090af  xor     edi, edi
0x1800090b1  lea     rcx, [rsp+28h+arg_10]
0x1800090b6  call    ?Reset@?$InvasivePtr@VAppHostConfigPathNavigator@@@@QEAAXXZ; InvasivePtr<AppHostConfigPathNavigator>::Reset(void)
0x1800090bb  mov     eax, edi
0x1800090bd  mov     rbx, [rsp+28h+arg_0]
0x1800090c2  mov     rsi, [rsp+28h+arg_8]
0x1800090c7  add     rsp, 20h
0x1800090cb  pop     rdi
0x1800090cc  retn
```
