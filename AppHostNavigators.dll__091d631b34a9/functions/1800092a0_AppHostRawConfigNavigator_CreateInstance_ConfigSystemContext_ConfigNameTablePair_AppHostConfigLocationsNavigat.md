# AppHostRawConfigNavigator::CreateInstance(ConfigSystemContext *,ConfigNameTablePair *,AppHostConfigLocationsNavigator *,AppHostRawConfigNavigator * *)

- ea: `0x1800092a0`
- end: `0x1800093aa`
- name: `?CreateInstance@AppHostRawConfigNavigator@@SAJPEAVConfigSystemContext@@PEAVConfigNameTablePair@@PEAVAppHostConfigLocationsNavigator@@PEAPEAV1@@Z`
- size: `266`
- prototype: `__int64 __fastcall(struct ConfigSystemContext *, struct ConfigNameTablePair *, struct AppHostConfigLocationsNavigator *, struct AppHostRawConfigNavigator **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180002920`

## callees

- `0x180001194`
- `0x180003a1c`
- `0x180008f18`
- `0x1800092a0`
- `0x1800113b0`

## pseudocode

```c
__int64 __fastcall AppHostRawConfigNavigator::CreateInstance(
        struct ConfigSystemContext *a1,
        struct ConfigNameTablePair *a2,
        struct AppHostConfigLocationsNavigator *a3,
        struct AppHostRawConfigNavigator **a4)
{
  RawConfigTree *v8; // rax
  RawConfigTree *v9; // rbx
  _OWORD *v10; // rax
  AppHostRawConfigNavigator *v11; // rax
  struct AppHostRawConfigNavigator *v12; // rdi
  RawConfigTree **v13; // rsi
  _QWORD v15[8]; // [rsp+28h] [rbp-40h] BYREF

  v15[0] = 0;
  v8 = (RawConfigTree *)operator new(0xA0u);
  v15[1] = v8;
  if ( v8 )
    v9 = RawConfigTree::RawConfigTree(v8, a1, a2, a3);
  else
    v9 = 0;
  InvasivePtr<ConfigLocationsTree>::Reset(v15);
  v15[0] = v9;
  if ( v9
    && (v10 = operator new(0x38u)) != 0
    && (*v10 = 0,
        v10[1] = 0,
        v10[2] = 0,
        *((_QWORD *)v10 + 6) = 0,
        v11 = AppHostRawConfigNavigator::AppHostRawConfigNavigator((AppHostRawConfigNavigator *)v10),
        (v12 = v11) != 0) )
  {
    *((_DWORD *)v11 + 8) = 0;
    v13 = (RawConfigTree **)((char *)v11 + 40);
    if ( *((RawConfigTree **)v11 + 5) != v9 )
    {
      _InterlockedIncrement((volatile signed __int32 *)v9 + 2);
      InvasivePtr<ConfigLocationsTree>::Reset((char *)v11 + 40);
      *v13 = v9;
    }
    *((_QWORD *)v12 + 6) = (char *)v9 + 32;
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
0x1800092a0  push    rbx
0x1800092a2  push    rsi
0x1800092a3  push    rdi
0x1800092a4  push    r14
0x1800092a6  push    r15
0x1800092a8  sub     rsp, 40h
0x1800092ac  mov     r15, r9
0x1800092af  mov     rbx, r8
0x1800092b2  mov     rdi, rdx
0x1800092b5  mov     rsi, rcx
0x1800092b8  mov     [rsp+68h+var_40], 0
0x1800092c1  mov     ecx, 0A0h; Size
0x1800092c6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800092cb  mov     [rsp+68h+var_38], rax
0x1800092d0  test    rax, rax
0x1800092d3  jz      short loc_1800092EB
0x1800092d5  mov     r9, rbx; struct AppHostConfigLocationsNavigator *
0x1800092d8  mov     r8, rdi; struct ConfigNameTablePair *
0x1800092db  mov     rdx, rsi; struct ConfigSystemContext *
0x1800092de  mov     rcx, rax; this
0x1800092e1  call    ??0RawConfigTree@@QEAA@PEAVConfigSystemContext@@PEAVConfigNameTablePair@@PEAVAppHostConfigLocationsNavigator@@@Z; RawConfigTree::RawConfigTree(ConfigSystemContext *,ConfigNameTablePair *,AppHostConfigLocationsNavigator *)
0x1800092e6  mov     rbx, rax
0x1800092e9  jmp     short loc_1800092ED
0x1800092eb  xor     ebx, ebx
0x1800092ed  lea     rcx, [rsp+68h+var_40]
0x1800092f2  call    ?Reset@?$InvasivePtr@VConfigLocationsTree@@@@QEAAXXZ; InvasivePtr<ConfigLocationsTree>::Reset(void)
0x1800092f7  mov     [rsp+68h+var_40], rbx
0x1800092fc  test    rbx, rbx
0x1800092ff  jnz     short loc_180009315
0x180009301  lea     rcx, [rsp+68h+var_40]
0x180009306  call    ?Reset@?$InvasivePtr@VConfigLocationsTree@@@@QEAAXXZ; InvasivePtr<ConfigLocationsTree>::Reset(void)
0x18000930b  mov     eax, 8007000Eh
0x180009310  jmp     loc_18000939D
0x180009315  mov     ecx, 38h ; '8'; Size
0x18000931a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000931f  test    rax, rax
0x180009322  jz      short loc_180009381
0x180009324  xorps   xmm0, xmm0
0x180009327  xor     ecx, ecx
0x180009329  movups  xmmword ptr [rax], xmm0
0x18000932c  movups  xmmword ptr [rax+10h], xmm0
0x180009330  movups  xmmword ptr [rax+20h], xmm0
0x180009334  mov     [rax+30h], rcx
0x180009338  mov     rcx, rax; this
0x18000933b  call    ??0AppHostRawConfigNavigator@@QEAA@XZ; AppHostRawConfigNavigator::AppHostRawConfigNavigator(void)
0x180009340  mov     rdi, rax
0x180009343  test    rax, rax
0x180009346  jz      short loc_180009381
0x180009348  lea     r14, [rbx+20h]
0x18000934c  mov     dword ptr [rax+20h], 0
0x180009353  lea     rsi, [rax+28h]
0x180009357  cmp     [rsi], rbx
0x18000935a  jz      short loc_18000936B
0x18000935c  lock inc dword ptr [rbx+8]
0x180009360  mov     rcx, rsi
0x180009363  call    ?Reset@?$InvasivePtr@VConfigLocationsTree@@@@QEAAXXZ; InvasivePtr<ConfigLocationsTree>::Reset(void)
0x180009368  mov     [rsi], rbx
0x18000936b  mov     [rdi+30h], r14
0x18000936f  mov     [r15], rdi
0x180009372  lea     rcx, [rsp+68h+var_40]
0x180009377  call    ?Reset@?$InvasivePtr@VConfigLocationsTree@@@@QEAAXXZ; InvasivePtr<ConfigLocationsTree>::Reset(void)
0x18000937c  nop
0x18000937d  xor     eax, eax
0x18000937f  jmp     short loc_18000939D
0x180009381  lea     rcx, [rsp+68h+var_40]
0x180009386  call    ?Reset@?$InvasivePtr@VConfigLocationsTree@@@@QEAAXXZ; InvasivePtr<ConfigLocationsTree>::Reset(void)
0x18000938b  mov     eax, 8007000Eh
0x180009390  jmp     short loc_18000939D
0x180009392  mov     eax, [rsp+68h+var_48]
0x180009396  jmp     short loc_18000939D
0x180009398  mov     eax, 8000FFFFh
0x18000939d  add     rsp, 40h
0x1800093a1  pop     r15
0x1800093a3  pop     r14
0x1800093a5  pop     rdi
0x1800093a6  pop     rsi
0x1800093a7  pop     rbx
0x1800093a8  retn
```
