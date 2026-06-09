# IsAutoList(IShellItem *,ICompositionProcessor *,int *)

- ea: `0x180025fac`
- end: `0x1800260f9`
- name: `?IsAutoList@@YAJPEAUIShellItem@@PEAUICompositionProcessor@@PEAH@Z`
- size: `333`
- prototype: `__int64 __fastcall(struct IShellItem *, struct ICompositionProcessor *, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180026470`

## callees

- `0x180004a50`
- `0x180025fac`
- `0x180051010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180025ff2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180025ff2`
- `ext-ms-win-ole32-bindctx-l1-1-0!CreateBindCtx` at `0x180026010`
- `ext-ms-win-ole32-bindctx-l1-1-0!CreateBindCtx` at `0x180026010`

## string_xrefs

- `0x180026024`: `Composition Processor`

## pseudocode

```c
__int64 __fastcall IsAutoList(struct IShellItem *a1, IBindCtx *a2, int *a3)
{
  HRESULT v5; // ebx
  struct IShellItemVtbl *lpVtbl; // rax
  void *v7; // rcx
  void *v9; // [rsp+30h] [rbp-10h] BYREF
  LPBC ppbc; // [rsp+68h] [rbp+28h] BYREF
  struct IUnknown *v11; // [rsp+70h] [rbp+30h] BYREF
  LPVOID ppv; // [rsp+78h] [rbp+38h] BYREF

  ppbc = a2;
  *a3 = 0;
  ppv = 0;
  v5 = CoCreateInstance(
         &GUID_db6efb73_5153_43b7_8078_c6ffc4c0238c,
         0,
         1u,
         &GUID_ea69859a_db5b_4c4a_8a8f_ae9759027534,
         &ppv);
  if ( v5 >= 0 )
  {
    ppbc = 0;
    v5 = CreateBindCtx(0, &ppbc);
    if ( v5 >= 0 )
    {
      v5 = ((__int64 (__fastcall *)(LPBC, const wchar_t *, LPVOID))ppbc->lpVtbl->RegisterObjectParam)(
             ppbc,
             L"Composition Processor",
             ppv);
      if ( v5 >= 0 )
      {
        lpVtbl = a1->lpVtbl;
        v11 = 0;
        v5 = ((__int64 (__fastcall *)(struct IShellItem *, LPBC, const GUID *, GUID *, struct IUnknown **))lpVtbl->BindToHandler)(
               a1,
               ppbc,
               &BHID_SFObject,
               &GUID_000214e6_0000_0000_c000_000000000046,
               &v11);
        if ( v5 >= 0 )
        {
          v9 = 0;
          if ( (int)IUnknown_QueryObject(
                      v11,
                      &GUID_c3be0d61_c82a_4abe_bf10_330f84a45c82,
                      &GUID_607c87f7_0696_4558_a368_de5e59cfe456,
                      &v9) >= 0 )
          {
            v7 = v9;
            *a3 = 1;
            (*(void (__fastcall **)(void *))(*(_QWORD *)v7 + 16LL))(v7);
          }
          ((void (__fastcall *)(struct IUnknown *))v11->lpVtbl->Release)(v11);
        }
      }
      ((void (__fastcall *)(LPBC))ppbc->lpVtbl->Release)(ppbc);
    }
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180025fac  mov     [rsp-18h+arg_0], rbx
0x180025fb1  mov     [rsp-18h+ppbc], rdx
0x180025fb6  push    rbp
0x180025fb7  push    rsi
0x180025fb8  push    rdi
0x180025fb9  mov     rbp, rsp
0x180025fbc  sub     rsp, 40h
0x180025fc0  xor     edx, edx; pUnkOuter
0x180025fc2  mov     dword ptr [r8], 0
0x180025fc9  mov     rdi, r8
0x180025fcc  mov     [rbp+arg_18], 0
0x180025fd4  mov     rsi, rcx
0x180025fd7  lea     rax, [rbp+arg_18]
0x180025fdb  lea     r9, _GUID_ea69859a_db5b_4c4a_8a8f_ae9759027534; riid
0x180025fe2  mov     [rsp+40h+ppv], rax; ppv
0x180025fe7  lea     r8d, [rdx+1]; dwClsContext
0x180025feb  lea     rcx, _GUID_db6efb73_5153_43b7_8078_c6ffc4c0238c; rclsid
0x180025ff2  call    cs:__imp_CoCreateInstance
0x180025ff8  mov     ebx, eax
0x180025ffa  test    eax, eax
0x180025ffc  js      loc_1800260EA
0x180026002  lea     rdx, [rbp+ppbc]; ppbc
0x180026006  mov     [rbp+ppbc], 0
0x18002600e  xor     ecx, ecx; reserved
0x180026010  call    cs:__imp_CreateBindCtx
0x180026016  mov     ebx, eax
0x180026018  test    eax, eax
0x18002601a  js      loc_1800260DA
0x180026020  mov     rcx, [rbp+ppbc]
0x180026024  lea     rdx, aCompositionPro; "Composition Processor"
0x18002602b  mov     r8, [rbp+arg_18]
0x18002602f  mov     rax, [rcx]
0x180026032  mov     rax, [rax+48h]
0x180026036  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002603b  mov     ebx, eax
0x18002603d  test    eax, eax
0x18002603f  js      loc_1800260CA
0x180026045  mov     rax, [rsi]
0x180026048  lea     rcx, [rbp+arg_10]
0x18002604c  mov     rdx, [rbp+ppbc]
0x180026050  lea     r9, _GUID_000214e6_0000_0000_c000_000000000046
0x180026057  mov     [rsp+40h+ppv], rcx
0x18002605c  lea     r8, BHID_SFObject
0x180026063  mov     rcx, rsi
0x180026066  mov     [rbp+arg_10], 0
0x18002606e  mov     rax, [rax+18h]
0x180026072  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026077  mov     ebx, eax
0x180026079  test    eax, eax
0x18002607b  js      short loc_1800260CA
0x18002607d  mov     rcx, [rbp+arg_10]; struct IUnknown *
0x180026081  lea     r9, [rbp+var_10]; void **
0x180026085  lea     r8, _GUID_607c87f7_0696_4558_a368_de5e59cfe456; struct _GUID *
0x18002608c  mov     [rbp+var_10], 0
0x180026094  lea     rdx, _GUID_c3be0d61_c82a_4abe_bf10_330f84a45c82; struct _GUID *
0x18002609b  call    ?IUnknown_QueryObject@@YAJPEAUIUnknown@@AEBU_GUID@@1PEAPEAX@Z; IUnknown_QueryObject(IUnknown *,_GUID const &,_GUID const &,void * *)
0x1800260a0  test    eax, eax
0x1800260a2  js      short loc_1800260BA
0x1800260a4  mov     rcx, [rbp+var_10]
0x1800260a8  mov     dword ptr [rdi], 1
0x1800260ae  mov     rax, [rcx]
0x1800260b1  mov     rax, [rax+10h]
0x1800260b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800260ba  mov     rcx, [rbp+arg_10]
0x1800260be  mov     rax, [rcx]
0x1800260c1  mov     rax, [rax+10h]
0x1800260c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800260ca  mov     rcx, [rbp+ppbc]
0x1800260ce  mov     rax, [rcx]
0x1800260d1  mov     rax, [rax+10h]
0x1800260d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800260da  mov     rcx, [rbp+arg_18]
0x1800260de  mov     rax, [rcx]
0x1800260e1  mov     rax, [rax+10h]
0x1800260e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800260ea  mov     eax, ebx
0x1800260ec  mov     rbx, [rsp+40h+arg_0]
0x1800260f1  add     rsp, 40h
0x1800260f5  pop     rdi
0x1800260f6  pop     rsi
0x1800260f7  pop     rbp
0x1800260f8  retn
```
