# AppHostMergedConfigNavigator::CreateInstance(ConfigSystemContext *,ConfigNameTablePair *,AppHostConfigPathNavigator *,AppHostMergedConfigNavigator * *)

- ea: `0x180006cf4`
- end: `0x180006dfe`
- name: `?CreateInstance@AppHostMergedConfigNavigator@@SAJPEAVConfigSystemContext@@PEAVConfigNameTablePair@@PEAVAppHostConfigPathNavigator@@PEAPEAV1@@Z`
- size: `266`
- prototype: `__int64 __fastcall(struct ConfigSystemContext *, struct ConfigNameTablePair *, struct AppHostConfigPathNavigator *, struct AppHostMergedConfigNavigator **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180004af0`

## callees

- `0x180001194`
- `0x180003a1c`
- `0x18000697c`
- `0x180006cf4`
- `0x18001076c`

## pseudocode

```c
__int64 __fastcall AppHostMergedConfigNavigator::CreateInstance(
        struct ConfigSystemContext *a1,
        struct ConfigNameTablePair *a2,
        struct AppHostConfigPathNavigator *a3,
        struct AppHostMergedConfigNavigator **a4)
{
  InvasivePtrObject *v8; // rax
  volatile signed __int32 *v9; // rbx
  _OWORD *v10; // rax
  AppHostMergedConfigNavigator *v11; // rax
  struct AppHostMergedConfigNavigator *v12; // rdi
  volatile signed __int32 **v13; // rsi
  InvasivePtrObject *v15[8]; // [rsp+28h] [rbp-40h] BYREF

  v15[0] = 0;
  v8 = (InvasivePtrObject *)operator new(0x90u);
  v15[1] = v8;
  if ( v8 )
    v9 = (volatile signed __int32 *)MergedConfigTree::MergedConfigTree(v8, a1, a2, a3);
  else
    v9 = 0;
  InvasivePtr<ConfigLocationsTree>::Reset(v15);
  v15[0] = (InvasivePtrObject *)v9;
  if ( v9
    && (v10 = operator new(0x38u)) != 0
    && (*v10 = 0,
        v10[1] = 0,
        v10[2] = 0,
        *((_QWORD *)v10 + 6) = 0,
        v11 = AppHostMergedConfigNavigator::AppHostMergedConfigNavigator((AppHostMergedConfigNavigator *)v10),
        (v12 = v11) != 0) )
  {
    *((_DWORD *)v11 + 8) = 0;
    v13 = (volatile signed __int32 **)((char *)v11 + 40);
    if ( *((volatile signed __int32 **)v11 + 5) != v9 )
    {
      _InterlockedIncrement(v9 + 2);
      InvasivePtr<ConfigLocationsTree>::Reset((InvasivePtrObject **)v11 + 5);
      *v13 = v9;
    }
    *((_QWORD *)v12 + 6) = v9 + 8;
    *a4 = v12;
    InvasivePtr<ConfigLocationsTree>::Reset(v15);
    return 0;
  }
  else
  {
    InvasivePtr<ConfigLocationsTree>::Reset(v15);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x180006cf4  push    rbx
0x180006cf6  push    rsi
0x180006cf7  push    rdi
0x180006cf8  push    r14
0x180006cfa  push    r15
0x180006cfc  sub     rsp, 40h
0x180006d00  mov     r15, r9
0x180006d03  mov     rbx, r8
0x180006d06  mov     rdi, rdx
0x180006d09  mov     rsi, rcx
0x180006d0c  mov     [rsp+68h+var_40], 0
0x180006d15  mov     ecx, 90h; Size
0x180006d1a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006d1f  mov     [rsp+68h+var_38], rax
0x180006d24  test    rax, rax
0x180006d27  jz      short loc_180006D3F
0x180006d29  mov     r9, rbx; struct AppHostConfigPathNavigator *
0x180006d2c  mov     r8, rdi; struct ConfigNameTablePair *
0x180006d2f  mov     rdx, rsi; struct ConfigSystemContext *
0x180006d32  mov     rcx, rax; this
0x180006d35  call    ??0MergedConfigTree@@QEAA@PEAVConfigSystemContext@@PEAVConfigNameTablePair@@PEAVAppHostConfigPathNavigator@@@Z; MergedConfigTree::MergedConfigTree(ConfigSystemContext *,ConfigNameTablePair *,AppHostConfigPathNavigator *)
0x180006d3a  mov     rbx, rax
0x180006d3d  jmp     short loc_180006D41
0x180006d3f  xor     ebx, ebx
0x180006d41  lea     rcx, [rsp+68h+var_40]
0x180006d46  call    ?Reset@?$InvasivePtr@VConfigLocationsTree@@@@QEAAXXZ; InvasivePtr<ConfigLocationsTree>::Reset(void)
0x180006d4b  mov     [rsp+68h+var_40], rbx
0x180006d50  test    rbx, rbx
0x180006d53  jnz     short loc_180006D69
0x180006d55  lea     rcx, [rsp+68h+var_40]
0x180006d5a  call    ?Reset@?$InvasivePtr@VConfigLocationsTree@@@@QEAAXXZ; InvasivePtr<ConfigLocationsTree>::Reset(void)
0x180006d5f  mov     eax, 8007000Eh
0x180006d64  jmp     loc_180006DF1
0x180006d69  mov     ecx, 38h ; '8'; Size
0x180006d6e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006d73  test    rax, rax
0x180006d76  jz      short loc_180006DD5
0x180006d78  xorps   xmm0, xmm0
0x180006d7b  xor     ecx, ecx
0x180006d7d  movups  xmmword ptr [rax], xmm0
0x180006d80  movups  xmmword ptr [rax+10h], xmm0
0x180006d84  movups  xmmword ptr [rax+20h], xmm0
0x180006d88  mov     [rax+30h], rcx
0x180006d8c  mov     rcx, rax; this
0x180006d8f  call    ??0AppHostMergedConfigNavigator@@QEAA@XZ; AppHostMergedConfigNavigator::AppHostMergedConfigNavigator(void)
0x180006d94  mov     rdi, rax
0x180006d97  test    rax, rax
0x180006d9a  jz      short loc_180006DD5
0x180006d9c  lea     r14, [rbx+20h]
0x180006da0  mov     dword ptr [rax+20h], 0
0x180006da7  lea     rsi, [rax+28h]
0x180006dab  cmp     [rsi], rbx
0x180006dae  jz      short loc_180006DBF
0x180006db0  lock inc dword ptr [rbx+8]
0x180006db4  mov     rcx, rsi
0x180006db7  call    ?Reset@?$InvasivePtr@VConfigLocationsTree@@@@QEAAXXZ; InvasivePtr<ConfigLocationsTree>::Reset(void)
0x180006dbc  mov     [rsi], rbx
0x180006dbf  mov     [rdi+30h], r14
0x180006dc3  mov     [r15], rdi
0x180006dc6  lea     rcx, [rsp+68h+var_40]
0x180006dcb  call    ?Reset@?$InvasivePtr@VConfigLocationsTree@@@@QEAAXXZ; InvasivePtr<ConfigLocationsTree>::Reset(void)
0x180006dd0  nop
0x180006dd1  xor     eax, eax
0x180006dd3  jmp     short loc_180006DF1
0x180006dd5  lea     rcx, [rsp+68h+var_40]
0x180006dda  call    ?Reset@?$InvasivePtr@VConfigLocationsTree@@@@QEAAXXZ; InvasivePtr<ConfigLocationsTree>::Reset(void)
0x180006ddf  mov     eax, 8007000Eh
0x180006de4  jmp     short loc_180006DF1
0x180006de6  mov     eax, [rsp+68h+var_48]
0x180006dea  jmp     short loc_180006DF1
0x180006dec  mov     eax, 8000FFFFh
0x180006df1  add     rsp, 40h
0x180006df5  pop     r15
0x180006df7  pop     r14
0x180006df9  pop     rdi
0x180006dfa  pop     rsi
0x180006dfb  pop     rbx
0x180006dfc  retn
```
