# OpenWithHelper::AssociatedAppInfo::Create(IAssocHandler *)

- ea: `0x18006a948`
- end: `0x18006aa67`
- name: `?Create@AssociatedAppInfo@OpenWithHelper@@SAPEAV12@PEAUIAssocHandler@@@Z`
- size: `287`
- prototype: `struct OpenWithHelper::AssociatedAppInfo *__fastcall(struct IAssocHandler *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callers

- `0x18006ab2c`

## callees

- `0x18002d540`
- `0x18006a948`
- `0x180073e48`
- `0x180080010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18006a975`
- `ole32!CoTaskMemFree` at `0x18006aa33`
- `ole32!CoTaskMemFree` at `0x18006aa45`
- `ole32!CoTaskMemFree` at `0x18006aa57`
- `ole32!CoTaskMemFree` at `0x18006a975`
- `ole32!CoTaskMemFree` at `0x18006aa33`
- `ole32!CoTaskMemFree` at `0x18006aa45`
- `ole32!CoTaskMemFree` at `0x18006aa57`
- `PhotoBase!?New@BasePrivate@@YAPEAX_K_N@Z` at `0x18006a9ff`
- `PhotoBase!?New@BasePrivate@@YAPEAX_K_N@Z` at `0x18006a9ff`

## string_xrefs

- `0x18006a9e9`: `shell32.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
struct OpenWithHelper::AssociatedAppInfo *__fastcall OpenWithHelper::AssociatedAppInfo::Create(
        struct IAssocHandler *a1)
{
  __int64 v3; // rbx
  unsigned __int64 v4; // rdx
  bool v5; // r8
  OpenWithHelper::AssociatedAppInfo *v6; // rax
  int CacheIndex; // [rsp+60h] [rbp+18h] BYREF
  unsigned __int16 *v8; // [rsp+68h] [rbp+20h] BYREF
  unsigned __int16 *v9; // [rsp+70h] [rbp+28h] BYREF
  LPVOID pv; // [rsp+78h] [rbp+30h] BYREF

  pv = 0;
  if ( ((int (__fastcall *)(struct IAssocHandler *, LPVOID *))a1->lpVtbl->GetName)(a1, &pv) >= 0 )
  {
    v9 = 0;
    if ( ((int (__fastcall *)(struct IAssocHandler *, unsigned __int16 **))a1->lpVtbl->GetUIName)(a1, &v9) >= 0 )
    {
      v8 = 0;
      CacheIndex = -1;
      if ( ((int (__fastcall *)(struct IAssocHandler *, unsigned __int16 **, int *))a1->lpVtbl->GetIconLocation)(
             a1,
             &v8,
             &CacheIndex) >= 0 )
      {
        CacheIndex = UIBase::IconFromShellCache::GetCacheIndex(v8, CacheIndex);
        if ( CacheIndex == -1 )
          CacheIndex = UIBase::IconFromShellCache::GetCacheIndex(L"shell32.dll", 2);
      }
      LOBYTE(v4) = 1;
      v6 = (OpenWithHelper::AssociatedAppInfo *)BasePrivate::New((BasePrivate *)0x38, v4, v5);
      if ( v6 )
        v3 = OpenWithHelper::AssociatedAppInfo::AssociatedAppInfo(v6, a1, v9, (const unsigned __int16 *)pv, CacheIndex);
      else
        v3 = 0;
      CoTaskMemFree(v8);
      v8 = 0;
    }
    else
    {
      v3 = 0;
    }
    CoTaskMemFree(v9);
    v9 = 0;
    CoTaskMemFree(pv);
    return (struct OpenWithHelper::AssociatedAppInfo *)v3;
  }
  else
  {
    CoTaskMemFree(pv);
    return 0;
  }
}

```

## disassembly

```asm
0x18006a948  push    rbp
0x18006a94a  push    rbx
0x18006a94b  mov     rbp, rsp
0x18006a94e  sub     rsp, 48h
0x18006a952  mov     rbx, rcx
0x18006a955  mov     [rbp+pv], 0
0x18006a95d  mov     rax, [rcx]
0x18006a960  lea     rdx, [rbp+pv]
0x18006a964  mov     rax, [rax+18h]
0x18006a968  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a96d  test    eax, eax
0x18006a96f  jns     short loc_18006A982
0x18006a971  mov     rcx, [rbp+pv]; pv
0x18006a975  call    cs:__imp_CoTaskMemFree
0x18006a97b  xor     eax, eax
0x18006a97d  jmp     loc_18006AA60
0x18006a982  mov     [rbp+arg_10], 0
0x18006a98a  mov     rax, [rbx]
0x18006a98d  lea     rdx, [rbp+arg_10]
0x18006a991  mov     rcx, rbx
0x18006a994  mov     rax, [rax+20h]
0x18006a998  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a99d  test    eax, eax
0x18006a99f  jns     short loc_18006A9A8
0x18006a9a1  xor     ebx, ebx
0x18006a9a3  jmp     loc_18006AA41
0x18006a9a8  mov     [rbp+arg_8], 0
0x18006a9b0  mov     [rbp+arg_0], 0FFFFFFFFh
0x18006a9b7  mov     rax, [rbx]
0x18006a9ba  lea     r8, [rbp+arg_0]
0x18006a9be  lea     rdx, [rbp+arg_8]
0x18006a9c2  mov     rcx, rbx
0x18006a9c5  mov     rax, [rax+28h]
0x18006a9c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a9ce  test    eax, eax
0x18006a9d0  js      short loc_18006A9F8
0x18006a9d2  mov     edx, [rbp+arg_0]; int
0x18006a9d5  mov     rcx, [rbp+arg_8]; unsigned __int16 *
0x18006a9d9  call    ?GetCacheIndex@IconFromShellCache@UIBase@@SAHPEBGH@Z; UIBase::IconFromShellCache::GetCacheIndex(ushort const *,int)
0x18006a9de  mov     [rbp+arg_0], eax
0x18006a9e1  cmp     eax, 0FFFFFFFFh
0x18006a9e4  jnz     short loc_18006A9F8
0x18006a9e6  lea     edx, [rax+3]; int
0x18006a9e9  lea     rcx, aShell32Dll_0; "shell32.dll"
0x18006a9f0  call    ?GetCacheIndex@IconFromShellCache@UIBase@@SAHPEBGH@Z; UIBase::IconFromShellCache::GetCacheIndex(ushort const *,int)
0x18006a9f5  mov     [rbp+arg_0], eax
0x18006a9f8  mov     dl, 1
0x18006a9fa  mov     ecx, 38h ; '8'
0x18006a9ff  call    cs:__imp_?New@BasePrivate@@YAPEAX_K_N@Z; BasePrivate::New(unsigned __int64,bool)
0x18006aa05  mov     [rbp+var_18], rax
0x18006aa09  test    rax, rax
0x18006aa0c  jz      short loc_18006AA2D
0x18006aa0e  mov     ecx, [rbp+arg_0]
0x18006aa11  mov     [rsp+48h+var_28], ecx; int
0x18006aa15  mov     r9, [rbp+pv]; unsigned __int16 *
0x18006aa19  mov     r8, [rbp+arg_10]; unsigned __int16 *
0x18006aa1d  mov     rdx, rbx; struct IAssocHandler *
0x18006aa20  mov     rcx, rax; this
0x18006aa23  call    ??0AssociatedAppInfo@OpenWithHelper@@AEAA@PEAUIAssocHandler@@PEBG1H@Z; OpenWithHelper::AssociatedAppInfo::AssociatedAppInfo(IAssocHandler *,ushort const *,ushort const *,int)
0x18006aa28  mov     rbx, rax
0x18006aa2b  jmp     short loc_18006AA2F
0x18006aa2d  xor     ebx, ebx
0x18006aa2f  mov     rcx, [rbp+arg_8]; pv
0x18006aa33  call    cs:__imp_CoTaskMemFree
0x18006aa39  mov     [rbp+arg_8], 0
0x18006aa41  mov     rcx, [rbp+arg_10]; pv
0x18006aa45  call    cs:__imp_CoTaskMemFree
0x18006aa4b  mov     [rbp+arg_10], 0
0x18006aa53  mov     rcx, [rbp+pv]; pv
0x18006aa57  call    cs:__imp_CoTaskMemFree
0x18006aa5d  mov     rax, rbx
0x18006aa60  add     rsp, 48h
0x18006aa64  pop     rbx
0x18006aa65  pop     rbp
0x18006aa66  retn
```
