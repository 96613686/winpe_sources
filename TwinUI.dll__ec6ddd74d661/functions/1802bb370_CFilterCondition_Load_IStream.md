# CFilterCondition::Load(IStream *)

- ea: `0x1802bb370`
- end: `0x1802bb5dd`
- name: `?Load@CFilterCondition@@UEAAJPEAUIStream@@@Z`
- size: `621`
- prototype: `int(CFilterCondition *__hidden this, struct IStream *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1802b8f40`
- `0x1802bac00`
- `0x1802bac74`
- `0x1802bb370`
- `0x1802bbee8`
- `0x1803bb010`

## import_xrefs

- `PROPSYS!PSCreateMemoryPropertyStore` at `0x1802bb3ba`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x1802bb3ba`
- `PROPSYS!PSPropertyBag_ReadStream` at `0x1802bb487`
- `PROPSYS!PSPropertyBag_ReadStream` at `0x1802bb52a`
- `PROPSYS!PSPropertyBag_ReadStream` at `0x1802bb487`
- `PROPSYS!PSPropertyBag_ReadStream` at `0x1802bb52a`
- `PROPSYS!PSPropertyBag_ReadPropertyKey` at `0x1802bb45a`
- `PROPSYS!PSPropertyBag_ReadPropertyKey` at `0x1802bb45a`
- `PROPSYS!PSPropertyBag_ReadInt` at `0x1802bb435`
- `PROPSYS!PSPropertyBag_ReadInt` at `0x1802bb435`
- `PROPSYS!PSPropertyBag_ReadBSTR` at `0x1802bb3f5`
- `PROPSYS!PSPropertyBag_ReadBSTR` at `0x1802bb41a`
- `PROPSYS!PSPropertyBag_ReadBSTR` at `0x1802bb3f5`
- `PROPSYS!PSPropertyBag_ReadBSTR` at `0x1802bb41a`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x1802bb49d`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x1802bb49d`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x1802bb54f`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x1802bb54f`

## pseudocode

```c
__int64 __fastcall CFilterCondition::Load(CFilterCondition *this, struct IStream *a2)
{
  HRESULT BSTR; // ebx
  _QWORD *v5; // rsi
  struct IStream *v6; // rcx
  const struct _GUID *const *v7; // rdx
  unsigned int v8; // r8d
  const struct _GUID *v9; // r9
  unsigned int v10; // esi
  const struct _GUID *v11; // rdx
  IStream *pstm; // [rsp+30h] [rbp-10h] BYREF
  struct IUnknown *v14; // [rsp+38h] [rbp-8h] BYREF
  void *pv; // [rsp+70h] [rbp+30h] BYREF
  void *ppv; // [rsp+80h] [rbp+40h] BYREF
  IStream *value; // [rsp+88h] [rbp+48h] BYREF

  BSTR = -2147418113;
  if ( !*((_QWORD *)this + 3) )
  {
    v5 = (_QWORD *)((char *)this + 64);
    if ( !*((_QWORD *)this + 8) )
    {
      ppv = 0;
      BSTR = PSCreateMemoryPropertyStore(&GUID_55272a00_42cb_11ce_8135_00aa004bb851, &ppv);
      if ( BSTR >= 0 )
      {
        BSTR = IUnknown_LoadFromStream(a2, (struct IUnknown *)ppv);
        if ( BSTR >= 0 )
        {
          BSTR = PSPropertyBag_ReadBSTR((IPropertyBag *)ppv, L"Name", (BSTR *)this + 3);
          if ( BSTR >= 0 )
          {
            PSPropertyBag_ReadBSTR((IPropertyBag *)ppv, L"InFolder", (BSTR *)this + 4);
            BSTR = PSPropertyBag_ReadInt((IPropertyBag *)ppv, L"Type", (INT *)this + 15);
            if ( BSTR >= 0 )
            {
              BSTR = PSPropertyBag_ReadPropertyKey((IPropertyBag *)ppv, L"Key", (PROPERTYKEY *)this + 2);
              if ( BSTR >= 0 )
              {
                value = 0;
                BSTR = PSPropertyBag_ReadStream((IPropertyBag *)ppv, L"Condition", &value);
                if ( BSTR >= 0 )
                {
                  IStream_Reset(value);
                  v6 = value;
                  *v5 = 0;
                  pv = 0;
                  BSTR = IUnknown_LoadKnownImplFromStream(v6, v7, v8, v9, &pv);
                  if ( BSTR >= 0 )
                  {
                    BSTR = (**(__int64 (__fastcall ***)(void *, GUID *, _QWORD *))pv)(
                             pv,
                             &GUID_0fc988d4_c935_4b97_a973_46282ea175c8,
                             v5);
                    (*(void (__fastcall **)(void *))(*(_QWORD *)pv + 16LL))(pv);
                  }
                  (*(void (__fastcall **)(IStream *))(*(_QWORD *)value + 16LL))(value);
                }
                pstm = 0;
                if ( BSTR >= 0 && PSPropertyBag_ReadStream((IPropertyBag *)ppv, L"Filters", &pstm) >= 0 )
                {
                  LODWORD(pv) = 0;
                  v10 = 0;
                  for ( BSTR = IStream_Read(pstm, &pv, 4u); v10 < (unsigned int)pv; ++v10 )
                  {
                    if ( BSTR < 0 )
                      break;
                    v14 = 0;
                    BSTR = SHLoadFilterFromStream(pstm, v11, (void **)&v14);
                    if ( BSTR >= 0 )
                    {
                      BSTR = CFilterCondition::AddObject((CFilterCondition *)((char *)this + 8), v14);
                      ((void (__fastcall *)(struct IUnknown *))v14->lpVtbl->Release)(v14);
                    }
                  }
                  (*(void (__fastcall **)(IStream *))(*(_QWORD *)pstm + 16LL))(pstm);
                }
              }
            }
          }
        }
        (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
      }
    }
  }
  return (unsigned int)BSTR;
}

```

## disassembly

```asm
0x1802bb370  mov     [rsp-28h+arg_8], rbx
0x1802bb375  push    rbp
0x1802bb376  push    rsi
0x1802bb377  push    rdi
0x1802bb378  push    r14
0x1802bb37a  push    r15
0x1802bb37c  mov     rbp, rsp
0x1802bb37f  sub     rsp, 40h
0x1802bb383  cmp     qword ptr [rcx+18h], 0
0x1802bb388  mov     r15, rdx
0x1802bb38b  mov     rdi, rcx
0x1802bb38e  mov     ebx, 8000FFFFh
0x1802bb393  jnz     loc_1802BB5C9
0x1802bb399  lea     rsi, [rcx+40h]
0x1802bb39d  cmp     qword ptr [rsi], 0
0x1802bb3a1  jnz     loc_1802BB5C9
0x1802bb3a7  lea     rdx, [rbp+ppv]; ppv
0x1802bb3ab  mov     [rbp+ppv], 0
0x1802bb3b3  lea     rcx, _GUID_55272a00_42cb_11ce_8135_00aa004bb851; riid
0x1802bb3ba  call    cs:__imp_PSCreateMemoryPropertyStore
0x1802bb3c1  nop     dword ptr [rax+rax+00h]
0x1802bb3c6  mov     ebx, eax
0x1802bb3c8  test    eax, eax
0x1802bb3ca  js      loc_1802BB5C9
0x1802bb3d0  mov     rdx, [rbp+ppv]; struct IUnknown *
0x1802bb3d4  mov     rcx, r15; struct IStream *
0x1802bb3d7  call    ?IUnknown_LoadFromStream@@YAJPEAUIStream@@PEAUIUnknown@@@Z; IUnknown_LoadFromStream(IStream *,IUnknown *)
0x1802bb3dc  mov     ebx, eax
0x1802bb3de  test    eax, eax
0x1802bb3e0  js      loc_1802BB5B9
0x1802bb3e6  mov     rcx, [rbp+ppv]; propBag
0x1802bb3ea  lea     r8, [rdi+18h]; value
0x1802bb3ee  lea     rdx, propName; "Name"
0x1802bb3f5  call    cs:__imp_PSPropertyBag_ReadBSTR
0x1802bb3fc  nop     dword ptr [rax+rax+00h]
0x1802bb401  mov     ebx, eax
0x1802bb403  test    eax, eax
0x1802bb405  js      loc_1802BB5B9
0x1802bb40b  mov     rcx, [rbp+ppv]; propBag
0x1802bb40f  lea     r8, [rdi+20h]; value
0x1802bb413  lea     rdx, aInfolder; "InFolder"
0x1802bb41a  call    cs:__imp_PSPropertyBag_ReadBSTR
0x1802bb421  nop     dword ptr [rax+rax+00h]
0x1802bb426  mov     rcx, [rbp+ppv]; propBag
0x1802bb42a  lea     r8, [rdi+3Ch]; value
0x1802bb42e  lea     rdx, aType; "Type"
0x1802bb435  call    cs:__imp_PSPropertyBag_ReadInt
0x1802bb43c  nop     dword ptr [rax+rax+00h]
0x1802bb441  mov     ebx, eax
0x1802bb443  test    eax, eax
0x1802bb445  js      loc_1802BB5B9
0x1802bb44b  mov     rcx, [rbp+ppv]; propBag
0x1802bb44f  lea     r8, [rdi+28h]; value
0x1802bb453  lea     rdx, aKey; "Key"
0x1802bb45a  call    cs:__imp_PSPropertyBag_ReadPropertyKey
0x1802bb461  nop     dword ptr [rax+rax+00h]
0x1802bb466  mov     ebx, eax
0x1802bb468  test    eax, eax
0x1802bb46a  js      loc_1802BB5B9
0x1802bb470  mov     rcx, [rbp+ppv]; propBag
0x1802bb474  lea     r8, [rbp+value]; value
0x1802bb478  lea     rdx, aCondition; "Condition"
0x1802bb47f  mov     [rbp+value], 0
0x1802bb487  call    cs:__imp_PSPropertyBag_ReadStream
0x1802bb48e  nop     dword ptr [rax+rax+00h]
0x1802bb493  mov     ebx, eax
0x1802bb495  test    eax, eax
0x1802bb497  js      short loc_1802BB50B
0x1802bb499  mov     rcx, [rbp+value]; pstm
0x1802bb49d  call    cs:__imp_IStream_Reset
0x1802bb4a4  nop     dword ptr [rax+rax+00h]
0x1802bb4a9  mov     rcx, [rbp+value]; struct IStream *
0x1802bb4ad  lea     rax, [rbp+pv]
0x1802bb4b1  mov     [rsp+40h+var_20], rax; void **
0x1802bb4b6  mov     qword ptr [rsi], 0
0x1802bb4bd  mov     [rbp+pv], 0
0x1802bb4c5  call    ?IUnknown_LoadKnownImplFromStream@@YAJPEAUIStream@@PEBQEBU_GUID@@IAEBU2@PEAPEAX@Z; IUnknown_LoadKnownImplFromStream(IStream *,_GUID const * const *,uint,_GUID const &,void * *)
0x1802bb4ca  mov     ebx, eax
0x1802bb4cc  test    eax, eax
0x1802bb4ce  js      short loc_1802BB4FB
0x1802bb4d0  mov     rcx, [rbp+pv]
0x1802bb4d4  lea     rdx, _GUID_0fc988d4_c935_4b97_a973_46282ea175c8
0x1802bb4db  mov     r8, rsi
0x1802bb4de  mov     rax, [rcx]
0x1802bb4e1  mov     rax, [rax]
0x1802bb4e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802bb4e9  mov     rcx, [rbp+pv]
0x1802bb4ed  mov     ebx, eax
0x1802bb4ef  mov     rax, [rcx]
0x1802bb4f2  mov     rax, [rax+10h]
0x1802bb4f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802bb4fb  mov     rcx, [rbp+value]
0x1802bb4ff  mov     rax, [rcx]
0x1802bb502  mov     rax, [rax+10h]
0x1802bb506  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802bb50b  mov     [rbp+pstm], 0
0x1802bb513  test    ebx, ebx
0x1802bb515  js      loc_1802BB5B9
0x1802bb51b  mov     rcx, [rbp+ppv]; propBag
0x1802bb51f  lea     r8, [rbp+pstm]; value
0x1802bb523  lea     rdx, aFilters; "Filters"
0x1802bb52a  call    cs:__imp_PSPropertyBag_ReadStream
0x1802bb531  nop     dword ptr [rax+rax+00h]
0x1802bb536  test    eax, eax
0x1802bb538  js      short loc_1802BB5B9
0x1802bb53a  mov     rcx, [rbp+pstm]; pstm
0x1802bb53e  lea     rdx, [rbp+pv]; pv
0x1802bb542  mov     r8d, 4; cb
0x1802bb548  mov     dword ptr [rbp+pv], 0
0x1802bb54f  call    cs:__imp_IStream_Read
0x1802bb556  nop     dword ptr [rax+rax+00h]
0x1802bb55b  xor     esi, esi
0x1802bb55d  mov     ebx, eax
0x1802bb55f  cmp     dword ptr [rbp+pv], esi
0x1802bb562  jbe     short loc_1802BB5A9
0x1802bb564  test    ebx, ebx
0x1802bb566  js      short loc_1802BB5A9
0x1802bb568  mov     rcx, [rbp+pstm]; struct IStream *
0x1802bb56c  lea     r8, [rbp+var_8]; void **
0x1802bb570  mov     [rbp+var_8], 0
0x1802bb578  call    ?SHLoadFilterFromStream@@YAJPEAUIStream@@AEBU_GUID@@PEAPEAX@Z; SHLoadFilterFromStream(IStream *,_GUID const &,void * *)
0x1802bb57d  mov     ebx, eax
0x1802bb57f  test    eax, eax
0x1802bb581  js      short loc_1802BB5A2
0x1802bb583  mov     rdx, [rbp+var_8]; struct IUnknown *
0x1802bb587  lea     rcx, [rdi+8]; this
0x1802bb58b  call    ?AddObject@CFilterCondition@@UEAAJPEAUIUnknown@@@Z; CFilterCondition::AddObject(IUnknown *)
0x1802bb590  mov     rcx, [rbp+var_8]
0x1802bb594  mov     ebx, eax
0x1802bb596  mov     rax, [rcx]
0x1802bb599  mov     rax, [rax+10h]
0x1802bb59d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802bb5a2  inc     esi
0x1802bb5a4  cmp     esi, dword ptr [rbp+pv]
0x1802bb5a7  jb      short loc_1802BB564
0x1802bb5a9  mov     rcx, [rbp+pstm]
0x1802bb5ad  mov     rax, [rcx]
0x1802bb5b0  mov     rax, [rax+10h]
0x1802bb5b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802bb5b9  mov     rcx, [rbp+ppv]
0x1802bb5bd  mov     rax, [rcx]
0x1802bb5c0  mov     rax, [rax+10h]
0x1802bb5c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802bb5c9  mov     eax, ebx
0x1802bb5cb  mov     rbx, [rsp+40h+arg_8]
0x1802bb5d0  add     rsp, 40h
0x1802bb5d4  pop     r15
0x1802bb5d6  pop     r14
0x1802bb5d8  pop     rdi
0x1802bb5d9  pop     rsi
0x1802bb5da  pop     rbp
0x1802bb5db  retn
```
