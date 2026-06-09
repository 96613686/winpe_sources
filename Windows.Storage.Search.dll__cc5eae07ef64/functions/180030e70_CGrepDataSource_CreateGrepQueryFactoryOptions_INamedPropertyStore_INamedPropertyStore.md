# CGrepDataSource::_CreateGrepQueryFactoryOptions(INamedPropertyStore *,INamedPropertyStore * *)

- ea: `0x180030e70`
- end: `0x18003108e`
- name: `?_CreateGrepQueryFactoryOptions@CGrepDataSource@@AEAAJPEAUINamedPropertyStore@@PEAPEAU2@@Z`
- size: `542`
- prototype: `int(CGrepDataSource *__hidden this, struct INamedPropertyStore *, struct INamedPropertyStore **)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800309dc`

## callees

- `0x180030e70`
- `0x1800ea010`

## import_xrefs

- `SHCORE!IUnknown_Set` at `0x18003102d`
- `SHCORE!IUnknown_Set` at `0x18003102d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180030f91`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180031037`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180030f91`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180031037`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180030eb5`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180031081`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180030eb5`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180031081`
- `OLEAUT32!__imp_SysFreeString` at `0x180030f9b`
- `OLEAUT32!__imp_SysFreeString` at `0x180030f9b`

## pseudocode

```c
__int64 __fastcall CGrepDataSource::_CreateGrepQueryFactoryOptions(
        CGrepDataSource *this,
        struct INamedPropertyStore *a2,
        IUnknown **a3)
{
  HRESULT i; // ebx
  struct INamedPropertyStoreVtbl *lpVtbl; // rax
  __int64 *v7; // rsi
  void *v8; // r15
  unsigned int v9; // edi
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rdi
  int v13; // eax
  __int64 *v15; // [rsp+20h] [rbp-28h] BYREF
  PROPVARIANT pvar[2]; // [rsp+28h] [rbp-20h] BYREF
  __int64 v17; // [rsp+38h] [rbp-10h]
  CGrepDataSource *v18; // [rsp+80h] [rbp+38h] BYREF
  IUnknown *punk; // [rsp+88h] [rbp+40h] BYREF
  BSTR bstrString; // [rsp+90h] [rbp+48h] BYREF
  void *ppv; // [rsp+98h] [rbp+50h] BYREF

  v18 = this;
  *a3 = 0;
  punk = 0;
  if ( a2 )
  {
    ppv = 0;
    i = PSCreateMemoryPropertyStore(&GUID_71604b0f_97b0_4764_8577_2f13e98a1422, &ppv);
    if ( i >= 0 )
    {
      lpVtbl = a2->lpVtbl;
      v15 = 0;
      i = ((__int64 (__fastcall *)(struct INamedPropertyStore *, GUID *, __int64 **))lpVtbl->QueryInterface)(
            a2,
            &GUID_71604b0f_97b0_4764_8577_2f13e98a1422,
            &v15);
      if ( i >= 0 )
      {
        v7 = v15;
        v8 = ppv;
        LODWORD(v18) = 0;
        v9 = 0;
        for ( i = (*(__int64 (__fastcall **)(__int64 *, CGrepDataSource **))(*v15 + 40))(v15, &v18); i >= 0; ++v9 )
        {
          if ( v9 >= (unsigned int)v18 )
            break;
          v10 = *v7;
          bstrString = 0;
          i = (*(__int64 (__fastcall **)(__int64 *, _QWORD, BSTR *))(v10 + 48))(v7, v9, &bstrString);
          if ( i >= 0 )
          {
            v17 = 0;
            v11 = *v7;
            *(_OWORD *)pvar = 0;
            i = (*(__int64 (__fastcall **)(__int64 *, BSTR, PROPVARIANT *))(v11 + 24))(v7, bstrString, pvar);
            if ( i >= 0 )
            {
              i = (*(__int64 (__fastcall **)(void *, BSTR, PROPVARIANT *))(*(_QWORD *)v8 + 32LL))(v8, bstrString, pvar);
              PropVariantClear(pvar);
            }
            SysFreeString(bstrString);
          }
        }
        if ( i >= 0 )
          i = (**(__int64 (__fastcall ***)(void *, GUID *, IUnknown **))ppv)(
                ppv,
                &GUID_71604b0f_97b0_4764_8577_2f13e98a1422,
                &punk);
        (*(void (__fastcall **)(__int64 *))(*v15 + 16))(v15);
      }
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
    }
  }
  else
  {
    i = PSCreateMemoryPropertyStore(&GUID_71604b0f_97b0_4764_8577_2f13e98a1422, (void **)&punk);
  }
  if ( i >= 0 )
  {
    v17 = 0;
    i = 0;
    *(_OWORD *)pvar = 0;
    LOWORD(pvar[0]) = 11;
    LOWORD(pvar[1]) = -1;
    v12 = 0;
    while ( (unsigned int)v12 < 2 )
    {
      v13 = ((__int64 (__fastcall *)(IUnknown *, wchar_t *, PROPVARIANT *))punk->lpVtbl[1].AddRef)(
              punk,
              off_1800EC580[v12],
              pvar);
      v12 = (unsigned int)(v12 + 1);
      i = v13;
      if ( v13 < 0 )
        goto LABEL_21;
    }
    IUnknown_Set(a3, punk);
LABEL_21:
    PropVariantClear(pvar);
    ((void (__fastcall *)(IUnknown *))punk->lpVtbl->Release)(punk);
  }
  return (unsigned int)i;
}

```

## disassembly

```asm
0x180030e70  mov     [rsp-30h+arg_0], rcx
0x180030e75  push    rbp
0x180030e76  push    rbx
0x180030e77  push    rsi
0x180030e78  push    rdi
0x180030e79  push    r14
0x180030e7b  push    r15
0x180030e7d  mov     rbp, rsp
0x180030e80  sub     rsp, 48h
0x180030e84  mov     qword ptr [r8], 0
0x180030e8b  mov     r14, r8
0x180030e8e  mov     [rbp+punk], 0
0x180030e96  mov     rdi, rdx
0x180030e99  lea     rcx, _GUID_71604b0f_97b0_4764_8577_2f13e98a1422; riid
0x180030ea0  test    rdx, rdx
0x180030ea3  jz      loc_18003107D
0x180030ea9  lea     rdx, [rbp+ppv]; ppv
0x180030ead  mov     [rbp+ppv], 0
0x180030eb5  call    cs:__imp_PSCreateMemoryPropertyStore
0x180030ebb  mov     ebx, eax
0x180030ebd  test    eax, eax
0x180030ebf  js      loc_180030FD3
0x180030ec5  mov     rax, [rdi]
0x180030ec8  lea     r8, [rbp+var_28]
0x180030ecc  lea     rdx, _GUID_71604b0f_97b0_4764_8577_2f13e98a1422
0x180030ed3  mov     [rbp+var_28], 0
0x180030edb  mov     rcx, rdi
0x180030ede  mov     rax, [rax]
0x180030ee1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030ee6  mov     ebx, eax
0x180030ee8  test    eax, eax
0x180030eea  js      loc_180030FC3
0x180030ef0  mov     rsi, [rbp+var_28]
0x180030ef4  lea     rdx, [rbp+arg_0]
0x180030ef8  mov     r15, [rbp+ppv]
0x180030efc  mov     rcx, rsi
0x180030eff  mov     dword ptr [rbp+arg_0], 0
0x180030f06  mov     rax, [rsi]
0x180030f09  mov     rax, [rax+28h]
0x180030f0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030f12  xor     edi, edi
0x180030f14  mov     ebx, eax
0x180030f16  test    eax, eax
0x180030f18  js      loc_180030FAB
0x180030f1e  cmp     edi, dword ptr [rbp+arg_0]
0x180030f21  jnb     loc_180030FAB
0x180030f27  mov     rax, [rsi]
0x180030f2a  lea     r8, [rbp+bstrString]
0x180030f2e  mov     edx, edi
0x180030f30  mov     [rbp+bstrString], 0
0x180030f38  mov     rcx, rsi
0x180030f3b  mov     rax, [rax+30h]
0x180030f3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030f44  mov     ebx, eax
0x180030f46  test    eax, eax
0x180030f48  js      short loc_180030FA1
0x180030f4a  mov     rdx, [rbp+bstrString]
0x180030f4e  lea     r8, [rbp+pvar]
0x180030f52  xor     eax, eax
0x180030f54  xorps   xmm0, xmm0
0x180030f57  mov     [rbp+var_10], rax
0x180030f5b  mov     rcx, rsi
0x180030f5e  mov     rax, [rsi]
0x180030f61  movups  xmmword ptr [rbp+pvar], xmm0
0x180030f65  mov     rax, [rax+18h]
0x180030f69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030f6e  mov     ebx, eax
0x180030f70  test    eax, eax
0x180030f72  js      short loc_180030F97
0x180030f74  mov     rax, [r15]
0x180030f77  lea     r8, [rbp+pvar]
0x180030f7b  mov     rdx, [rbp+bstrString]
0x180030f7f  mov     rcx, r15
0x180030f82  mov     rax, [rax+20h]
0x180030f86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030f8b  lea     rcx, [rbp+pvar]; pvar
0x180030f8f  mov     ebx, eax
0x180030f91  call    cs:__imp_PropVariantClear
0x180030f97  mov     rcx, [rbp+bstrString]; bstrString
0x180030f9b  call    cs:__imp_SysFreeString
0x180030fa1  inc     edi
0x180030fa3  test    ebx, ebx
0x180030fa5  jns     loc_180030F1E
0x180030fab  test    ebx, ebx
0x180030fad  jns     loc_18003105C
0x180030fb3  mov     rcx, [rbp+var_28]
0x180030fb7  mov     rax, [rcx]
0x180030fba  mov     rax, [rax+10h]
0x180030fbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030fc3  mov     rcx, [rbp+ppv]
0x180030fc7  mov     rax, [rcx]
0x180030fca  mov     rax, [rax+10h]
0x180030fce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030fd3  test    ebx, ebx
0x180030fd5  js      short loc_18003104D
0x180030fd7  xor     eax, eax
0x180030fd9  xorps   xmm0, xmm0
0x180030fdc  mov     [rbp+var_10], rax
0x180030fe0  xor     ebx, ebx
0x180030fe2  mov     eax, 0Bh
0x180030fe7  movups  xmmword ptr [rbp+pvar], xmm0
0x180030feb  mov     word ptr [rbp+pvar], ax
0x180030fef  or      eax, 0FFFFFFFFh
0x180030ff2  mov     word ptr [rbp+pvar+8], ax
0x180030ff6  xor     edi, edi
0x180030ff8  cmp     edi, 2
0x180030ffb  jnb     short loc_180031026
0x180030ffd  mov     rcx, [rbp+punk]
0x180031001  lea     r9, off_1800EC580; "AssumeWritable"
0x180031008  mov     rdx, [r9+rdi*8]
0x18003100c  lea     r8, [rbp+pvar]
0x180031010  mov     rax, [rcx]
0x180031013  mov     rax, [rax+20h]
0x180031017  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003101c  inc     edi
0x18003101e  mov     ebx, eax
0x180031020  test    eax, eax
0x180031022  jns     short loc_180030FF8
0x180031024  jmp     short loc_180031033
0x180031026  mov     rdx, [rbp+punk]; punk
0x18003102a  mov     rcx, r14; ppunk
0x18003102d  call    cs:__imp_IUnknown_Set
0x180031033  lea     rcx, [rbp+pvar]; pvar
0x180031037  call    cs:__imp_PropVariantClear
0x18003103d  mov     rcx, [rbp+punk]
0x180031041  mov     rax, [rcx]
0x180031044  mov     rax, [rax+10h]
0x180031048  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003104d  mov     eax, ebx
0x18003104f  add     rsp, 48h
0x180031053  pop     r15
0x180031055  pop     r14
0x180031057  pop     rdi
0x180031058  pop     rsi
0x180031059  pop     rbx
0x18003105a  pop     rbp
0x18003105b  retn
0x18003105c  mov     rcx, [rbp+ppv]
0x180031060  lea     r8, [rbp+punk]
0x180031064  lea     rdx, _GUID_71604b0f_97b0_4764_8577_2f13e98a1422
0x18003106b  mov     rax, [rcx]
0x18003106e  mov     rax, [rax]
0x180031071  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031076  mov     ebx, eax
0x180031078  jmp     loc_180030FB3
0x18003107d  lea     rdx, [rbp+punk]; ppv
0x180031081  call    cs:__imp_PSCreateMemoryPropertyStore
0x180031087  mov     ebx, eax
0x180031089  jmp     loc_180030FD3
```
