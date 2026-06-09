# CreateScopeFromLibraryDescription(ILibraryDescription *,IShellItem *,IShellItem *,LIBRARY_SCOPE_FLAGS,SCOPE_ITEM_DEPTH,SCOPE_ITEM_FLAGS,ushort const *,IScope * *)

- ea: `0x18002990c`
- end: `0x180029ba9`
- name: `?CreateScopeFromLibraryDescription@@YAJPEAUILibraryDescription@@PEAUIShellItem@@1W4LIBRARY_SCOPE_FLAGS@@W4SCOPE_ITEM_DEPTH@@W4SCOPE_ITEM_FLAGS@@PEBGPEAPEAUIScope@@@Z`
- size: `669`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180032cd0`
- `0x18003435c`

## callees

- `0x1800052b0`
- `0x180019e80`
- `0x18002990c`
- `0x18002cfc4`
- `0x18002e170`
- `0x18002e2e0`
- `0x18002e348`
- `0x18002e3f0`
- `0x18002e50c`
- `0x180031208`
- `0x180051010`

## import_xrefs

- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x180029b69`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x180029b69`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180029960`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180029960`

## pseudocode

```c
__int64 __fastcall CreateScopeFromLibraryDescription(
        struct ILibraryDescription *a1,
        struct ILocationDescription *a2,
        struct IShellItem *a3,
        int a4,
        unsigned int a5,
        int a6,
        unsigned __int16 *a7,
        IUnknown **ppunk)
{
  IUnknown **v8; // rsi
  unsigned int v9; // r14d
  char v10; // bl
  int v13; // edi
  BOOL v14; // r15d
  struct IShellItem v15; // rax
  BOOL v16; // ebx
  __int64 v17; // rax
  __int64 v18; // rax
  BOOL v19; // esi
  int v20; // ebx
  __int64 v21; // r9
  IUnknown *punk; // [rsp+30h] [rbp-20h] BYREF
  __int64 *v24; // [rsp+38h] [rbp-18h] BYREF
  LPVOID v25; // [rsp+40h] [rbp-10h] BYREF
  struct ILocationDescription *v26; // [rsp+98h] [rbp+48h] BYREF
  int v27; // [rsp+A8h] [rbp+58h]

  v27 = a4;
  v26 = a2;
  v8 = ppunk;
  v9 = 0;
  v10 = a4;
  v25 = 0;
  *ppunk = 0;
  v13 = CoCreateInstance(
          &GUID_6746c347_576b_4f73_9012_cdfeea251bc4,
          0,
          1u,
          &GUID_54410b83_6787_4418_9735_5aaaabe83a9a,
          &v25);
  if ( v13 >= 0 )
  {
    punk = 0;
    v13 = (*(__int64 (__fastcall **)(LPVOID, GUID *, IUnknown **))(*(_QWORD *)v25 + 24LL))(
            v25,
            &GUID_655d1685_2bfd_4f7f_ad22_5ab61c8d8798,
            &punk);
    if ( v13 < 0 )
    {
LABEL_36:
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v25 + 16LL))(v25);
      return (unsigned int)v13;
    }
    if ( (unsigned int)IShellItem_IsContainerFile(a3) )
      v14 = IsLibrary(a3);
    else
      v14 = 0;
    if ( (v10 & 4) != 0 && !v14 )
    {
      v15.lpVtbl = a3->lpVtbl;
      v26 = 0;
      if ( ((int (__fastcall *)(struct IShellItem *, _QWORD, const GUID *, GUID *, struct ILocationDescription **))v15.lpVtbl->BindToHandler)(
             a3,
             0,
             &BHID_SFObject,
             &GUID_86187c37_e662_4d1e_a122_7478676d7e6e,
             &v26) >= 0 )
      {
        v16 = (unsigned int)GetUnsupportedPropFromLibrary(v26) - 2 <= 1;
        (*(void (__fastcall **)(struct ILocationDescription *))(*(_QWORD *)v26 + 16LL))(v26);
        if ( v16 )
          goto LABEL_34;
        v10 = v27;
      }
      if ( (unsigned int)IsSlowLibrary(a1) )
        goto LABEL_34;
    }
    v17 = *(_QWORD *)a1;
    a6 |= 0x10u;
    a5 = 0;
    v13 = (*(__int64 (__fastcall **)(struct ILibraryDescription *, unsigned int *))(v17 + 104))(a1, &a5);
    if ( v13 < 0 )
    {
LABEL_35:
      ((void (__fastcall *)(IUnknown *))punk->lpVtbl->Release)(punk);
      goto LABEL_36;
    }
    while ( v9 < a5 )
    {
      v18 = *(_QWORD *)a1;
      v26 = 0;
      v13 = (*(__int64 (__fastcall **)(struct ILibraryDescription *, _QWORD, struct ILocationDescription **))(v18 + 112))(
              a1,
              v9,
              &v26);
      if ( v13 >= 0 )
      {
        v24 = 0;
        v13 = (**(__int64 (__fastcall ***)(struct ILocationDescription *, GUID *, __int64 **))v26)(
                v26,
                &GUID_f8e6532b_c735_4517_bf1d_cbe30df8fe1c,
                &v24);
        if ( v13 >= 0 )
        {
          v19 = (v10 & 1) == 0 && (unsigned int)IsSearchOnlyLocation(v26);
          if ( (v10 & 2) != 0 || (unsigned int)IsProviderLocation(v26) || v14 )
            v20 = 0;
          else
            v20 = IsUnsupportedLocation(v26);
          if ( (unsigned int)IsAccessibleLibraryLocation(v26) && !v19 && !v20 )
            v13 = _AddScopeForLocation(v24, (__int64)punk, a3, v21, a6, a7);
          (*(void (__fastcall **)(__int64 *))(*v24 + 16))(v24);
        }
        (*(void (__fastcall **)(struct ILocationDescription *))(*(_QWORD *)v26 + 16LL))(v26);
      }
      v10 = v27;
      ++v9;
      if ( v13 < 0 )
        goto LABEL_35;
    }
    v8 = ppunk;
LABEL_34:
    IUnknown_Set(v8, punk);
    goto LABEL_35;
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18002990c  mov     r11, rsp
0x18002990f  mov     [r11+8], rbx
0x180029913  mov     [r11+20h], r9d
0x180029917  mov     [r11+10h], rdx
0x18002991b  push    rbp
0x18002991c  push    rsi
0x18002991d  push    rdi
0x18002991e  push    r12
0x180029920  push    r13
0x180029922  push    r14
0x180029924  push    r15
0x180029926  mov     rbp, rsp
0x180029929  sub     rsp, 50h
0x18002992d  mov     rsi, [rbp+ppunk]
0x180029931  lea     rax, [rbp+var_10]
0x180029935  xor     r14d, r14d
0x180029938  mov     [r11-68h], rax
0x18002993c  mov     ebx, r9d
0x18002993f  mov     [rbp+var_10], r14
0x180029943  mov     r12, r8
0x180029946  lea     r9, _GUID_54410b83_6787_4418_9735_5aaaabe83a9a; riid
0x18002994d  mov     r13, rcx
0x180029950  mov     [rsi], r14
0x180029953  lea     r8d, [r14+1]; dwClsContext
0x180029957  xor     edx, edx; pUnkOuter
0x180029959  lea     rcx, _GUID_6746c347_576b_4f73_9012_cdfeea251bc4; rclsid
0x180029960  call    cs:__imp_CoCreateInstance
0x180029966  mov     edi, eax
0x180029968  test    eax, eax
0x18002996a  js      loc_180029B8F
0x180029970  mov     rcx, [rbp+var_10]
0x180029974  lea     r8, [rbp+punk]
0x180029978  mov     [rbp+punk], r14
0x18002997c  lea     rdx, _GUID_655d1685_2bfd_4f7f_ad22_5ab61c8d8798
0x180029983  mov     rax, [rcx]
0x180029986  mov     rax, [rax+18h]
0x18002998a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002998f  mov     edi, eax
0x180029991  test    eax, eax
0x180029993  js      loc_180029B7F
0x180029999  mov     rcx, r12; struct IShellItem *
0x18002999c  call    ?IShellItem_IsContainerFile@@YAHPEAUIShellItem@@@Z; IShellItem_IsContainerFile(IShellItem *)
0x1800299a1  test    eax, eax
0x1800299a3  jz      short loc_1800299B3
0x1800299a5  mov     rcx, r12; struct IShellItem *
0x1800299a8  call    ?IsLibrary@@YA_NPEAUIShellItem@@@Z; IsLibrary(IShellItem *)
0x1800299ad  movzx   r15d, al
0x1800299b1  jmp     short loc_1800299B6
0x1800299b3  mov     r15d, r14d
0x1800299b6  test    bl, 4
0x1800299b9  jz      short loc_180029A31
0x1800299bb  test    r15d, r15d
0x1800299be  jnz     short loc_180029A31
0x1800299c0  mov     rax, [r12]
0x1800299c4  lea     rcx, [rbp+arg_8]
0x1800299c8  mov     [rsp+50h+var_30], rcx
0x1800299cd  lea     r9, _GUID_86187c37_e662_4d1e_a122_7478676d7e6e
0x1800299d4  lea     r8, BHID_SFObject
0x1800299db  mov     [rbp+arg_8], r14
0x1800299df  xor     edx, edx
0x1800299e1  mov     rcx, r12
0x1800299e4  mov     rax, [rax+18h]
0x1800299e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800299ed  test    eax, eax
0x1800299ef  js      short loc_180029A21
0x1800299f1  mov     rcx, [rbp+arg_8]
0x1800299f5  call    ?GetUnsupportedPropFromLibrary@@YA?AW4NONINDEXEDPROP@@PEAUILibraryDescription@@@Z; GetUnsupportedPropFromLibrary(ILibraryDescription *)
0x1800299fa  mov     rcx, [rbp+arg_8]
0x1800299fe  add     eax, 0FFFFFFFEh
0x180029a01  cmp     eax, 1
0x180029a04  mov     ebx, r14d
0x180029a07  setbe   bl
0x180029a0a  mov     rax, [rcx]
0x180029a0d  mov     rax, [rax+10h]
0x180029a11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029a16  test    ebx, ebx
0x180029a18  jnz     loc_180029B62
0x180029a1e  mov     ebx, [rbp+arg_18]
0x180029a21  mov     rcx, r13; struct ILibraryDescription *
0x180029a24  call    ?IsSlowLibrary@@YAHPEAUILibraryDescription@@@Z; IsSlowLibrary(ILibraryDescription *)
0x180029a29  test    eax, eax
0x180029a2b  jnz     loc_180029B62
0x180029a31  mov     rax, [r13+0]
0x180029a35  lea     rdx, [rbp+arg_20]
0x180029a39  or      [rbp+arg_28], 10h
0x180029a3d  mov     rcx, r13
0x180029a40  mov     [rbp+arg_20], r14d
0x180029a44  mov     rax, [rax+68h]
0x180029a48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029a4d  mov     edi, eax
0x180029a4f  test    eax, eax
0x180029a51  js      loc_180029B6F
0x180029a57  cmp     r14d, [rbp+arg_20]
0x180029a5b  jnb     loc_180029B5E
0x180029a61  mov     rax, [r13+0]
0x180029a65  lea     r8, [rbp+arg_8]
0x180029a69  mov     edx, r14d
0x180029a6c  mov     [rbp+arg_8], 0
0x180029a74  mov     rcx, r13
0x180029a77  mov     rax, [rax+70h]
0x180029a7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029a80  mov     edi, eax
0x180029a82  test    eax, eax
0x180029a84  js      loc_180029B4E
0x180029a8a  mov     rcx, [rbp+arg_8]
0x180029a8e  lea     r8, [rbp+var_18]
0x180029a92  mov     [rbp+var_18], 0
0x180029a9a  lea     rdx, _GUID_f8e6532b_c735_4517_bf1d_cbe30df8fe1c
0x180029aa1  mov     rax, [rcx]
0x180029aa4  mov     rax, [rax]
0x180029aa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029aac  mov     edi, eax
0x180029aae  test    eax, eax
0x180029ab0  js      loc_180029B3E
0x180029ab6  test    bl, 1
0x180029ab9  jnz     short loc_180029ACF
0x180029abb  mov     rcx, [rbp+arg_8]; struct ILocationDescription *
0x180029abf  call    ?IsSearchOnlyLocation@@YAHPEAUILocationDescription@@@Z; IsSearchOnlyLocation(ILocationDescription *)
0x180029ac4  test    eax, eax
0x180029ac6  jz      short loc_180029ACF
0x180029ac8  mov     esi, 1
0x180029acd  jmp     short loc_180029AD1
0x180029acf  xor     esi, esi
0x180029ad1  test    bl, 2
0x180029ad4  jnz     short loc_180029AF5
0x180029ad6  mov     rcx, [rbp+arg_8]; struct ILocationDescription *
0x180029ada  call    ?IsProviderLocation@@YAHPEAUILocationDescription@@@Z; IsProviderLocation(ILocationDescription *)
0x180029adf  test    eax, eax
0x180029ae1  jnz     short loc_180029AF5
0x180029ae3  test    r15d, r15d
0x180029ae6  jnz     short loc_180029AF5
0x180029ae8  mov     rcx, [rbp+arg_8]; struct ILocationDescription *
0x180029aec  call    ?IsUnsupportedLocation@@YAHPEAUILocationDescription@@@Z; IsUnsupportedLocation(ILocationDescription *)
0x180029af1  mov     ebx, eax
0x180029af3  jmp     short loc_180029AF7
0x180029af5  xor     ebx, ebx
0x180029af7  mov     rcx, [rbp+arg_8]; struct ILocationDescription *
0x180029afb  call    ?IsAccessibleLibraryLocation@@YAHPEAUILocationDescription@@@Z; IsAccessibleLibraryLocation(ILocationDescription *)
0x180029b00  test    eax, eax
0x180029b02  jz      short loc_180029B2E
0x180029b04  test    esi, esi
0x180029b06  jnz     short loc_180029B2E
0x180029b08  test    ebx, ebx
0x180029b0a  jnz     short loc_180029B2E
0x180029b0c  mov     rax, [rbp+arg_30]
0x180029b10  mov     r8, r12
0x180029b13  mov     rdx, [rbp+punk]
0x180029b17  mov     rcx, [rbp+var_18]
0x180029b1b  mov     [rsp+50h+var_28], rax
0x180029b20  mov     eax, [rbp+arg_28]
0x180029b23  mov     dword ptr [rsp+50h+var_30], eax
0x180029b27  call    ?_AddScopeForLocation@@YAJPEAUILocationDescription2@@PEAUIScope@@PEAUIShellItem@@W4SCOPE_ITEM_DEPTH@@W4SCOPE_ITEM_FLAGS@@PEBG@Z; _AddScopeForLocation(ILocationDescription2 *,IScope *,IShellItem *,SCOPE_ITEM_DEPTH,SCOPE_ITEM_FLAGS,ushort const *)
0x180029b2c  mov     edi, eax
0x180029b2e  mov     rcx, [rbp+var_18]
0x180029b32  mov     rax, [rcx]
0x180029b35  mov     rax, [rax+10h]
0x180029b39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029b3e  mov     rcx, [rbp+arg_8]
0x180029b42  mov     rax, [rcx]
0x180029b45  mov     rax, [rax+10h]
0x180029b49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029b4e  mov     ebx, [rbp+arg_18]
0x180029b51  inc     r14d
0x180029b54  test    edi, edi
0x180029b56  jns     loc_180029A57
0x180029b5c  jmp     short loc_180029B6F
0x180029b5e  mov     rsi, [rbp+ppunk]
0x180029b62  mov     rdx, [rbp+punk]; punk
0x180029b66  mov     rcx, rsi; ppunk
0x180029b69  call    cs:__imp_IUnknown_Set
0x180029b6f  mov     rcx, [rbp+punk]
0x180029b73  mov     rax, [rcx]
0x180029b76  mov     rax, [rax+10h]
0x180029b7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029b7f  mov     rcx, [rbp+var_10]
0x180029b83  mov     rax, [rcx]
0x180029b86  mov     rax, [rax+10h]
0x180029b8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029b8f  mov     rbx, [rsp+50h+arg_0]
0x180029b97  mov     eax, edi
0x180029b99  add     rsp, 50h
0x180029b9d  pop     r15
0x180029b9f  pop     r14
0x180029ba1  pop     r13
0x180029ba3  pop     r12
0x180029ba5  pop     rdi
0x180029ba6  pop     rsi
0x180029ba7  pop     rbp
0x180029ba8  retn
```
