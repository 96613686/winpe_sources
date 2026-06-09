# AppHostConfigLocationsNavigator::CreateInstance(ConfigSystemContext *,ConfigNameTablePair *,AppHostConfigPathNavigator *,AppHostConfigLocationsNavigator * *)

- ea: `0x18000280c`
- end: `0x180002916`
- name: `?CreateInstance@AppHostConfigLocationsNavigator@@SAJPEAVConfigSystemContext@@PEAVConfigNameTablePair@@PEAVAppHostConfigPathNavigator@@PEAPEAV1@@Z`
- size: `266`
- prototype: `__int64 __fastcall(struct ConfigSystemContext *, struct ConfigNameTablePair *, struct AppHostConfigPathNavigator *, struct AppHostConfigLocationsNavigator **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180004a50`

## callees

- `0x180001194`
- `0x180002068`
- `0x18000280c`
- `0x180003a1c`
- `0x1800098a0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall AppHostConfigLocationsNavigator::CreateInstance(
        struct ConfigSystemContext *a1,
        struct ConfigNameTablePair *a2,
        ConfigPathNode **a3,
        struct AppHostConfigLocationsNavigator **a4)
{
  InvasivePtrObject *v8; // rax
  volatile signed __int32 *v9; // rbx
  __int64 result; // rax
  _OWORD *v11; // rax
  AppHostConfigLocationsNavigator *v12; // rax
  struct AppHostConfigLocationsNavigator *v13; // rdi
  volatile signed __int32 **v14; // rsi
  unsigned int v15; // [rsp+20h] [rbp-48h] BYREF
  InvasivePtrObject *v16[8]; // [rsp+28h] [rbp-40h] BYREF

  v16[0] = 0;
  try
  {
    v8 = (InvasivePtrObject *)operator new(0x88u);
    v16[1] = v8;
    if ( v8 )
      v9 = (volatile signed __int32 *)ConfigLocationsTree::ConfigLocationsTree(v8, a1, a2, a3);
    else
      v9 = 0;
    InvasivePtr<ConfigLocationsTree>::Reset(v16);
    v16[0] = (InvasivePtrObject *)v9;
    if ( v9
      && (v11 = operator new(0x38u)) != 0
      && (*v11 = 0,
          v11[1] = 0,
          v11[2] = 0,
          *((_QWORD *)v11 + 6) = 0,
          v12 = AppHostConfigLocationsNavigator::AppHostConfigLocationsNavigator((AppHostConfigLocationsNavigator *)v11),
          (v13 = v12) != 0) )
    {
      *((_DWORD *)v12 + 8) = 0;
      v14 = (volatile signed __int32 **)((char *)v12 + 40);
      if ( *((volatile signed __int32 **)v12 + 5) != v9 )
      {
        _InterlockedIncrement(v9 + 2);
        InvasivePtr<ConfigLocationsTree>::Reset((InvasivePtrObject **)v12 + 5);
        *v14 = v9;
      }
      *((_QWORD *)v13 + 6) = v9 + 12;
      *a4 = v13;
      InvasivePtr<ConfigLocationsTree>::Reset(v16);
      result = 0;
    }
    else
    {
      InvasivePtr<ConfigLocationsTree>::Reset(v16);
      result = 2147942414LL;
    }
  }
  catch ( long v15 )
  {
    return v15;
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
0x18000280c  push    rbx
0x18000280e  push    rsi
0x18000280f  push    rdi
0x180002810  push    r14
0x180002812  push    r15
0x180002814  sub     rsp, 40h
0x180002818  mov     r15, r9
0x18000281b  mov     rbx, r8
0x18000281e  mov     rdi, rdx
0x180002821  mov     rsi, rcx
0x180002824  mov     [rsp+68h+var_40], 0
0x18000282d  mov     ecx, 88h; Size
0x180002832  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002837  mov     [rsp+68h+var_38], rax
0x18000283c  test    rax, rax
0x18000283f  jz      short loc_180002857
0x180002841  mov     r9, rbx; struct AppHostConfigPathNavigator *
0x180002844  mov     r8, rdi; struct ConfigNameTablePair *
0x180002847  mov     rdx, rsi; struct ConfigSystemContext *
0x18000284a  mov     rcx, rax; this
0x18000284d  call    ??0ConfigLocationsTree@@QEAA@PEAVConfigSystemContext@@PEAVConfigNameTablePair@@PEAVAppHostConfigPathNavigator@@@Z; ConfigLocationsTree::ConfigLocationsTree(ConfigSystemContext *,ConfigNameTablePair *,AppHostConfigPathNavigator *)
0x180002852  mov     rbx, rax
0x180002855  jmp     short loc_180002859
0x180002857  xor     ebx, ebx
0x180002859  lea     rcx, [rsp+68h+var_40]
0x18000285e  call    ?Reset@?$InvasivePtr@VConfigLocationsTree@@@@QEAAXXZ; InvasivePtr<ConfigLocationsTree>::Reset(void)
0x180002863  mov     [rsp+68h+var_40], rbx
0x180002868  test    rbx, rbx
0x18000286b  jnz     short loc_180002881
0x18000286d  lea     rcx, [rsp+68h+var_40]
0x180002872  call    ?Reset@?$InvasivePtr@VConfigLocationsTree@@@@QEAAXXZ; InvasivePtr<ConfigLocationsTree>::Reset(void)
0x180002877  mov     eax, 8007000Eh
0x18000287c  jmp     loc_180002909
0x180002881  mov     ecx, 38h ; '8'; Size
0x180002886  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000288b  test    rax, rax
0x18000288e  jz      short loc_1800028ED
0x180002890  xorps   xmm0, xmm0
0x180002893  xor     ecx, ecx
0x180002895  movups  xmmword ptr [rax], xmm0
0x180002898  movups  xmmword ptr [rax+10h], xmm0
0x18000289c  movups  xmmword ptr [rax+20h], xmm0
0x1800028a0  mov     [rax+30h], rcx
0x1800028a4  mov     rcx, rax; this
0x1800028a7  call    ??0AppHostConfigLocationsNavigator@@QEAA@XZ; AppHostConfigLocationsNavigator::AppHostConfigLocationsNavigator(void)
0x1800028ac  mov     rdi, rax
0x1800028af  test    rax, rax
0x1800028b2  jz      short loc_1800028ED
0x1800028b4  lea     r14, [rbx+30h]
0x1800028b8  mov     dword ptr [rax+20h], 0
0x1800028bf  lea     rsi, [rax+28h]
0x1800028c3  cmp     [rsi], rbx
0x1800028c6  jz      short loc_1800028D7
0x1800028c8  lock inc dword ptr [rbx+8]
0x1800028cc  mov     rcx, rsi
0x1800028cf  call    ?Reset@?$InvasivePtr@VConfigLocationsTree@@@@QEAAXXZ; InvasivePtr<ConfigLocationsTree>::Reset(void)
0x1800028d4  mov     [rsi], rbx
0x1800028d7  mov     [rdi+30h], r14
0x1800028db  mov     [r15], rdi
0x1800028de  lea     rcx, [rsp+68h+var_40]
0x1800028e3  call    ?Reset@?$InvasivePtr@VConfigLocationsTree@@@@QEAAXXZ; InvasivePtr<ConfigLocationsTree>::Reset(void)
0x1800028e8  nop
0x1800028e9  xor     eax, eax
0x1800028eb  jmp     short loc_180002909
0x1800028ed  lea     rcx, [rsp+68h+var_40]
0x1800028f2  call    ?Reset@?$InvasivePtr@VConfigLocationsTree@@@@QEAAXXZ; InvasivePtr<ConfigLocationsTree>::Reset(void)
0x1800028f7  mov     eax, 8007000Eh
0x1800028fc  jmp     short loc_180002909
0x1800028fe  mov     eax, [rsp+68h+var_48]
0x180002902  jmp     short loc_180002909
0x180002904  mov     eax, 8000FFFFh
0x180002909  add     rsp, 40h
0x18000290d  pop     r15
0x18000290f  pop     r14
0x180002911  pop     rdi
0x180002912  pop     rsi
0x180002913  pop     rbx
0x180002914  retn
```
