# CProfileCache_CreateInstance(_ITEMIDLIST const *,CNetworkItemFactory *,CProfileCache * *)

- ea: `0x18000636c`
- end: `0x180006431`
- name: `?CProfileCache_CreateInstance@@YAJPEFBU_ITEMIDLIST@@PEAVCNetworkItemFactory@@PEAPEAVCProfileCache@@@Z`
- size: `197`
- prototype: `__int64 __fastcall(LPCITEMIDLIST pidl, struct CNetworkItemFactory *, struct CProfileCache **)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180004ba0`

## callees

- `0x18000636c`
- `0x1800065ac`
- `0x1800070c8`
- `0x18000a7a7`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall CProfileCache_CreateInstance(
        LPCITEMIDLIST pidl,
        struct CNetworkItemFactory *a2,
        struct CProfileCache **a3)
{
  _QWORD *v6; // rax
  _QWORD *v7; // rbx
  int v8; // edi

  *a3 = 0;
  v6 = operator new(0x78u);
  v7 = v6;
  if ( v6 )
  {
    memset_0(v6, 0, 0x78u);
    _InterlockedIncrement(&g_cRefThisDll);
    v7[1] = 0;
    *v7 = &CProfileCache::`vftable';
    v7[3] = 0;
    v7[4] = 0;
    v7[5] = 0;
    *((_DWORD *)v7 + 12) = 0;
    *((_DWORD *)v7 + 13) = 0;
    *((_DWORD *)v7 + 18) = 1;
    v7[12] = 0;
    v8 = CProfileCache::Initialize((CProfileCache *)v7, pidl, a2);
    if ( v8 < 0 )
      (*(void (__fastcall **)(_QWORD *))(*v7 + 16LL))(v7);
    else
      *a3 = (struct CProfileCache *)v7;
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000636c  push    rbx
0x18000636e  push    rbp
0x18000636f  push    rsi
0x180006370  push    rdi
0x180006371  sub     rsp, 28h
0x180006375  mov     rbp, rcx
0x180006378  mov     qword ptr [r8], 0
0x18000637f  mov     ecx, 78h ; 'x'; unsigned __int64
0x180006384  mov     rsi, r8
0x180006387  mov     rdi, rdx
0x18000638a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000638f  mov     rbx, rax
0x180006392  test    rax, rax
0x180006395  jz      loc_180006421
0x18000639b  xor     edx, edx; Val
0x18000639d  mov     rcx, rax; void *
0x1800063a0  lea     r8d, [rdx+78h]; Size
0x1800063a4  call    memset_0
0x1800063a9  lock inc cs:?g_cRefThisDll@@3JA; long g_cRefThisDll
0x1800063b0  mov     qword ptr [rbx+8], 0
0x1800063b8  lea     rax, ??_7CProfileCache@@6B@; const CProfileCache::`vftable'
0x1800063bf  mov     [rbx], rax
0x1800063c2  mov     r8, rdi; struct CNetworkItemFactory *
0x1800063c5  mov     qword ptr [rbx+18h], 0
0x1800063cd  mov     rdx, rbp; pidl
0x1800063d0  mov     qword ptr [rbx+20h], 0
0x1800063d8  mov     rcx, rbx; this
0x1800063db  mov     qword ptr [rbx+28h], 0
0x1800063e3  mov     dword ptr [rbx+30h], 0
0x1800063ea  mov     dword ptr [rbx+34h], 0
0x1800063f1  mov     dword ptr [rbx+48h], 1
0x1800063f8  mov     qword ptr [rbx+60h], 0
0x180006400  call    ?Initialize@CProfileCache@@QEAAJPEFBU_ITEMIDLIST@@PEAVCNetworkItemFactory@@@Z; CProfileCache::Initialize(_ITEMIDLIST const *,CNetworkItemFactory *)
0x180006405  mov     edi, eax
0x180006407  test    eax, eax
0x180006409  js      short loc_180006410
0x18000640b  mov     [rsi], rbx
0x18000640e  jmp     short loc_180006426
0x180006410  mov     rax, [rbx]
0x180006413  mov     rcx, rbx
0x180006416  mov     rax, [rax+10h]
0x18000641a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000641f  jmp     short loc_180006426
0x180006421  mov     edi, 8007000Eh
0x180006426  mov     eax, edi
0x180006428  add     rsp, 28h
0x18000642c  pop     rdi
0x18000642d  pop     rsi
0x18000642e  pop     rbp
0x18000642f  pop     rbx
0x180006430  retn
```
