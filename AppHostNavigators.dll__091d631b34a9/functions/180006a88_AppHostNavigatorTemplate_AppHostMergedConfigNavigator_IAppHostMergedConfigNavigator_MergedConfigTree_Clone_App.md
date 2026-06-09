# AppHostNavigatorTemplate<AppHostMergedConfigNavigator,IAppHostMergedConfigNavigator,MergedConfigTree>::Clone(AppHostMergedConfigNavigator * *)

- ea: `0x180006a88`
- end: `0x180006b3d`
- name: `?Clone@?$AppHostNavigatorTemplate@VAppHostMergedConfigNavigator@@UIAppHostMergedConfigNavigator@@VMergedConfigTree@@@@QEAAJPEAPEAVAppHostMergedConfigNavigator@@@Z`
- size: `181`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180006b50`

## callees

- `0x180001194`
- `0x1800039ec`
- `0x18000697c`
- `0x180006a88`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall AppHostNavigatorTemplate<AppHostMergedConfigNavigator,IAppHostMergedConfigNavigator,MergedConfigTree>::Clone(
        __int64 a1,
        AppHostMergedConfigNavigator **a2)
{
  _OWORD *v4; // rax
  AppHostMergedConfigNavigator *v5; // rbx
  int v6; // edi
  AppHostMergedConfigNavigator *v8; // [rsp+40h] [rbp+18h] BYREF
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
    v5 = AppHostMergedConfigNavigator::AppHostMergedConfigNavigator((AppHostMergedConfigNavigator *)v4);
  }
  else
  {
    v5 = 0;
  }
  InvasivePtr<AppHostConfigPathNavigator>::Reset((__int64 *)&v8);
  v8 = v5;
  if ( v5 )
  {
    v6 = (*(__int64 (__fastcall **)(AppHostMergedConfigNavigator *, __int64))(*(_QWORD *)v5 + 168LL))(v5, a1);
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
0x180006a88  mov     [rsp+arg_0], rbx
0x180006a8d  mov     [rsp+arg_8], rsi
0x180006a92  push    rdi
0x180006a93  sub     rsp, 20h
0x180006a97  mov     rsi, rdx
0x180006a9a  mov     rdi, rcx
0x180006a9d  mov     [rsp+28h+arg_10], 0
0x180006aa6  mov     ecx, 38h ; '8'; Size
0x180006aab  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006ab0  mov     [rsp+28h+arg_18], rax
0x180006ab5  test    rax, rax
0x180006ab8  jz      short loc_180006ADB
0x180006aba  xorps   xmm0, xmm0
0x180006abd  xor     ecx, ecx
0x180006abf  movups  xmmword ptr [rax], xmm0
0x180006ac2  movups  xmmword ptr [rax+10h], xmm0
0x180006ac6  movups  xmmword ptr [rax+20h], xmm0
0x180006aca  mov     [rax+30h], rcx
0x180006ace  mov     rcx, rax; this
0x180006ad1  call    ??0AppHostMergedConfigNavigator@@QEAA@XZ; AppHostMergedConfigNavigator::AppHostMergedConfigNavigator(void)
0x180006ad6  mov     rbx, rax
0x180006ad9  jmp     short loc_180006ADD
0x180006adb  xor     ebx, ebx
0x180006add  lea     rcx, [rsp+28h+arg_10]
0x180006ae2  call    ?Reset@?$InvasivePtr@VAppHostConfigPathNavigator@@@@QEAAXXZ; InvasivePtr<AppHostConfigPathNavigator>::Reset(void)
0x180006ae7  mov     [rsp+28h+arg_10], rbx
0x180006aec  test    rbx, rbx
0x180006aef  jnz     short loc_180006AF8
0x180006af1  mov     edi, 8007000Eh
0x180006af6  jmp     short loc_180006B21
0x180006af8  mov     rax, [rbx]
0x180006afb  mov     rdx, rdi
0x180006afe  mov     rcx, rbx
0x180006b01  mov     rax, [rax+0A8h]
0x180006b08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b0d  mov     edi, eax
0x180006b0f  test    eax, eax
0x180006b11  js      short loc_180006B21
0x180006b13  mov     [rsp+28h+arg_10], 0
0x180006b1c  mov     [rsi], rbx
0x180006b1f  xor     edi, edi
0x180006b21  lea     rcx, [rsp+28h+arg_10]
0x180006b26  call    ?Reset@?$InvasivePtr@VAppHostConfigPathNavigator@@@@QEAAXXZ; InvasivePtr<AppHostConfigPathNavigator>::Reset(void)
0x180006b2b  mov     eax, edi
0x180006b2d  mov     rbx, [rsp+28h+arg_0]
0x180006b32  mov     rsi, [rsp+28h+arg_8]
0x180006b37  add     rsp, 20h
0x180006b3b  pop     rdi
0x180006b3c  retn
```
