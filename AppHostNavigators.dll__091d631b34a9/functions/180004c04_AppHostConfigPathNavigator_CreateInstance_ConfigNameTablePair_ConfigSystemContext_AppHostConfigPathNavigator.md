# AppHostConfigPathNavigator::CreateInstance(ConfigNameTablePair *,ConfigSystemContext *,AppHostConfigPathNavigator * *)

- ea: `0x180004c04`
- end: `0x180004d17`
- name: `?CreateInstance@AppHostConfigPathNavigator@@SAJPEAVConfigNameTablePair@@PEAVConfigSystemContext@@PEAPEAV1@@Z`
- size: `275`
- prototype: `__int64 __fastcall(struct ConfigNameTablePair *, struct ConfigSystemContext *, struct AppHostConfigPathNavigator **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180008190`

## callees

- `0x180001194`
- `0x180003a1c`
- `0x1800040fc`
- `0x180004164`
- `0x180004c04`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall AppHostConfigPathNavigator::CreateInstance(
        struct ConfigNameTablePair *a1,
        struct ConfigSystemContext *a2,
        struct AppHostConfigPathNavigator **a3)
{
  ConfigPathNavigationTree *v6; // rax
  ConfigPathNavigationTree *v7; // rbx
  __int64 result; // rax
  _OWORD *v9; // rax
  AppHostConfigPathNavigator *v10; // rax
  struct AppHostConfigPathNavigator *v11; // rdi
  ConfigPathNavigationTree **v12; // rsi
  unsigned int v13; // [rsp+20h] [rbp-28h] BYREF
  ConfigPathNavigationTree *v14; // [rsp+28h] [rbp-20h]
  ConfigPathNavigationTree *v15; // [rsp+68h] [rbp+20h] BYREF

  v15 = 0;
  try
  {
    v6 = (ConfigPathNavigationTree *)operator new(0xC8u);
    v14 = v6;
    if ( v6 )
      v7 = ConfigPathNavigationTree::ConfigPathNavigationTree(v6, a1, a2);
    else
      v7 = 0;
    InvasivePtr<ConfigLocationsTree>::Reset(&v15);
    v15 = v7;
    if ( v7
      && (v9 = operator new(0x38u)) != 0
      && (*v9 = 0,
          v9[1] = 0,
          v9[2] = 0,
          *((_QWORD *)v9 + 6) = 0,
          v10 = AppHostConfigPathNavigator::AppHostConfigPathNavigator((AppHostConfigPathNavigator *)v9),
          (v11 = v10) != 0) )
    {
      *((_DWORD *)v10 + 8) = 0;
      v12 = (ConfigPathNavigationTree **)((char *)v10 + 40);
      if ( *((ConfigPathNavigationTree **)v10 + 5) != v7 )
      {
        _InterlockedIncrement((volatile signed __int32 *)v7 + 2);
        InvasivePtr<ConfigLocationsTree>::Reset((char *)v10 + 40);
        *v12 = v7;
      }
      *((_QWORD *)v11 + 6) = (char *)v7 + 24;
      *a3 = v11;
      InvasivePtr<ConfigLocationsTree>::Reset(&v15);
      result = 0;
    }
    else
    {
      InvasivePtr<ConfigLocationsTree>::Reset(&v15);
      result = 2147942414LL;
    }
  }
  catch ( long v13 )
  {
    return v13;
  }
  catch ( ... )
  {
    return 2147549183LL;
  }
  return result;
}

```

## disassembly

```asm
0x180004c04  mov     [rsp+arg_0], rbx
0x180004c09  mov     [rsp+arg_8], rsi
0x180004c0e  push    rdi
0x180004c0f  push    r14
0x180004c11  push    r15
0x180004c13  sub     rsp, 30h
0x180004c17  mov     r15, r8
0x180004c1a  mov     rbx, rdx
0x180004c1d  mov     rdi, rcx
0x180004c20  mov     [rsp+48h+arg_18], 0
0x180004c29  mov     ecx, 0C8h; Size
0x180004c2e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004c33  mov     [rsp+48h+var_20], rax
0x180004c38  test    rax, rax
0x180004c3b  jz      short loc_180004C50
0x180004c3d  mov     r8, rbx; struct ConfigSystemContext *
0x180004c40  mov     rdx, rdi; struct ConfigNameTablePair *
0x180004c43  mov     rcx, rax; this
0x180004c46  call    ??0ConfigPathNavigationTree@@QEAA@PEAVConfigNameTablePair@@PEAVConfigSystemContext@@@Z; ConfigPathNavigationTree::ConfigPathNavigationTree(ConfigNameTablePair *,ConfigSystemContext *)
0x180004c4b  mov     rbx, rax
0x180004c4e  jmp     short loc_180004C52
0x180004c50  xor     ebx, ebx
0x180004c52  lea     rcx, [rsp+48h+arg_18]
0x180004c57  call    ?Reset@?$InvasivePtr@VConfigLocationsTree@@@@QEAAXXZ; InvasivePtr<ConfigLocationsTree>::Reset(void)
0x180004c5c  mov     [rsp+48h+arg_18], rbx
0x180004c61  test    rbx, rbx
0x180004c64  jnz     short loc_180004C7A
0x180004c66  lea     rcx, [rsp+48h+arg_18]
0x180004c6b  call    ?Reset@?$InvasivePtr@VConfigLocationsTree@@@@QEAAXXZ; InvasivePtr<ConfigLocationsTree>::Reset(void)
0x180004c70  mov     eax, 8007000Eh
0x180004c75  jmp     loc_180004D02
0x180004c7a  mov     ecx, 38h ; '8'; Size
0x180004c7f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004c84  test    rax, rax
0x180004c87  jz      short loc_180004CE6
0x180004c89  xorps   xmm0, xmm0
0x180004c8c  xor     ecx, ecx
0x180004c8e  movups  xmmword ptr [rax], xmm0
0x180004c91  movups  xmmword ptr [rax+10h], xmm0
0x180004c95  movups  xmmword ptr [rax+20h], xmm0
0x180004c99  mov     [rax+30h], rcx
0x180004c9d  mov     rcx, rax; this
0x180004ca0  call    ??0AppHostConfigPathNavigator@@QEAA@XZ; AppHostConfigPathNavigator::AppHostConfigPathNavigator(void)
0x180004ca5  mov     rdi, rax
0x180004ca8  test    rax, rax
0x180004cab  jz      short loc_180004CE6
0x180004cad  lea     r14, [rbx+18h]
0x180004cb1  mov     dword ptr [rax+20h], 0
0x180004cb8  lea     rsi, [rax+28h]
0x180004cbc  cmp     [rsi], rbx
0x180004cbf  jz      short loc_180004CD0
0x180004cc1  lock inc dword ptr [rbx+8]
0x180004cc5  mov     rcx, rsi
0x180004cc8  call    ?Reset@?$InvasivePtr@VConfigLocationsTree@@@@QEAAXXZ; InvasivePtr<ConfigLocationsTree>::Reset(void)
0x180004ccd  mov     [rsi], rbx
0x180004cd0  mov     [rdi+30h], r14
0x180004cd4  mov     [r15], rdi
0x180004cd7  lea     rcx, [rsp+48h+arg_18]
0x180004cdc  call    ?Reset@?$InvasivePtr@VConfigLocationsTree@@@@QEAAXXZ; InvasivePtr<ConfigLocationsTree>::Reset(void)
0x180004ce1  nop
0x180004ce2  xor     eax, eax
0x180004ce4  jmp     short loc_180004D02
0x180004ce6  lea     rcx, [rsp+48h+arg_18]
0x180004ceb  call    ?Reset@?$InvasivePtr@VConfigLocationsTree@@@@QEAAXXZ; InvasivePtr<ConfigLocationsTree>::Reset(void)
0x180004cf0  mov     eax, 8007000Eh
0x180004cf5  jmp     short loc_180004D02
0x180004cf7  mov     eax, [rsp+48h+var_28]
0x180004cfb  jmp     short loc_180004D02
0x180004cfd  mov     eax, 8000FFFFh
0x180004d02  mov     rbx, [rsp+48h+arg_0]
0x180004d07  mov     rsi, [rsp+48h+arg_8]
0x180004d0c  add     rsp, 30h
0x180004d10  pop     r15
0x180004d12  pop     r14
0x180004d14  pop     rdi
0x180004d15  retn
```
