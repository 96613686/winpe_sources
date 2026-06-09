# CFilterCondition::Load(IStream *)

- ea: `0x1800233f0`
- end: `0x180023626`
- name: `?Load@CFilterCondition@@UEAAJPEAUIStream@@@Z`
- size: `566`
- prototype: `int(CFilterCondition *__hidden this, struct IStream *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180022400`
- `0x180023074`
- `0x1800230e8`
- `0x1800233f0`
- `0x180023e68`
- `0x180051010`

## import_xrefs

- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18002359f`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18002359f`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x1800234f9`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x1800234f9`
- `PROPSYS!PSPropertyBag_ReadPropertyKey` at `0x1800234c2`
- `PROPSYS!PSPropertyBag_ReadPropertyKey` at `0x1800234c2`
- `PROPSYS!PSPropertyBag_ReadInt` at `0x1800234a3`
- `PROPSYS!PSPropertyBag_ReadInt` at `0x1800234a3`
- `PROPSYS!PSPropertyBag_ReadBSTR` at `0x18002346f`
- `PROPSYS!PSPropertyBag_ReadBSTR` at `0x18002348e`
- `PROPSYS!PSPropertyBag_ReadBSTR` at `0x18002346f`
- `PROPSYS!PSPropertyBag_ReadBSTR` at `0x18002348e`
- `PROPSYS!PSPropertyBag_ReadStream` at `0x1800234e9`
- `PROPSYS!PSPropertyBag_ReadStream` at `0x180023580`
- `PROPSYS!PSPropertyBag_ReadStream` at `0x1800234e9`
- `PROPSYS!PSPropertyBag_ReadStream` at `0x180023580`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18002343a`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18002343a`

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
0x1800233f0  mov     [rsp-28h+arg_8], rbx
0x1800233f5  push    rbp
0x1800233f6  push    rsi
0x1800233f7  push    rdi
0x1800233f8  push    r14
0x1800233fa  push    r15
0x1800233fc  mov     rbp, rsp
0x1800233ff  sub     rsp, 40h
0x180023403  cmp     qword ptr [rcx+18h], 0
0x180023408  mov     r15, rdx
0x18002340b  mov     rdi, rcx
0x18002340e  mov     ebx, 8000FFFFh
0x180023413  jnz     loc_180023613
0x180023419  lea     rsi, [rcx+40h]
0x18002341d  cmp     qword ptr [rsi], 0
0x180023421  jnz     loc_180023613
0x180023427  lea     rdx, [rbp+ppv]; ppv
0x18002342b  mov     [rbp+ppv], 0
0x180023433  lea     rcx, _GUID_55272a00_42cb_11ce_8135_00aa004bb851; riid
0x18002343a  call    cs:__imp_PSCreateMemoryPropertyStore
0x180023440  mov     ebx, eax
0x180023442  test    eax, eax
0x180023444  js      loc_180023613
0x18002344a  mov     rdx, [rbp+ppv]; struct IUnknown *
0x18002344e  mov     rcx, r15; struct IStream *
0x180023451  call    ?IUnknown_LoadFromStream@@YAJPEAUIStream@@PEAUIUnknown@@@Z; IUnknown_LoadFromStream(IStream *,IUnknown *)
0x180023456  mov     ebx, eax
0x180023458  test    eax, eax
0x18002345a  js      loc_180023603
0x180023460  mov     rcx, [rbp+ppv]; propBag
0x180023464  lea     r8, [rdi+18h]; value
0x180023468  lea     rdx, aName; "Name"
0x18002346f  call    cs:__imp_PSPropertyBag_ReadBSTR
0x180023475  mov     ebx, eax
0x180023477  test    eax, eax
0x180023479  js      loc_180023603
0x18002347f  mov     rcx, [rbp+ppv]; propBag
0x180023483  lea     r8, [rdi+20h]; value
0x180023487  lea     rdx, aInfolder; "InFolder"
0x18002348e  call    cs:__imp_PSPropertyBag_ReadBSTR
0x180023494  mov     rcx, [rbp+ppv]; propBag
0x180023498  lea     r8, [rdi+3Ch]; value
0x18002349c  lea     rdx, aType; "Type"
0x1800234a3  call    cs:__imp_PSPropertyBag_ReadInt
0x1800234a9  mov     ebx, eax
0x1800234ab  test    eax, eax
0x1800234ad  js      loc_180023603
0x1800234b3  mov     rcx, [rbp+ppv]; propBag
0x1800234b7  lea     r8, [rdi+28h]; value
0x1800234bb  lea     rdx, aKey; "Key"
0x1800234c2  call    cs:__imp_PSPropertyBag_ReadPropertyKey
0x1800234c8  mov     ebx, eax
0x1800234ca  test    eax, eax
0x1800234cc  js      loc_180023603
0x1800234d2  mov     rcx, [rbp+ppv]; propBag
0x1800234d6  lea     r8, [rbp+value]; value
0x1800234da  lea     rdx, aCondition; "Condition"
0x1800234e1  mov     [rbp+value], 0
0x1800234e9  call    cs:__imp_PSPropertyBag_ReadStream
0x1800234ef  mov     ebx, eax
0x1800234f1  test    eax, eax
0x1800234f3  js      short loc_180023561
0x1800234f5  mov     rcx, [rbp+value]; pstm
0x1800234f9  call    cs:__imp_IStream_Reset
0x1800234ff  mov     rcx, [rbp+value]; struct IStream *
0x180023503  lea     rax, [rbp+pv]
0x180023507  mov     [rsp+40h+var_20], rax; void **
0x18002350c  mov     qword ptr [rsi], 0
0x180023513  mov     [rbp+pv], 0
0x18002351b  call    ?IUnknown_LoadKnownImplFromStream@@YAJPEAUIStream@@PEBQEBU_GUID@@IAEBU2@PEAPEAX@Z; IUnknown_LoadKnownImplFromStream(IStream *,_GUID const * const *,uint,_GUID const &,void * *)
0x180023520  mov     ebx, eax
0x180023522  test    eax, eax
0x180023524  js      short loc_180023551
0x180023526  mov     rcx, [rbp+pv]
0x18002352a  lea     rdx, _GUID_0fc988d4_c935_4b97_a973_46282ea175c8
0x180023531  mov     r8, rsi
0x180023534  mov     rax, [rcx]
0x180023537  mov     rax, [rax]
0x18002353a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002353f  mov     rcx, [rbp+pv]
0x180023543  mov     ebx, eax
0x180023545  mov     rax, [rcx]
0x180023548  mov     rax, [rax+10h]
0x18002354c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023551  mov     rcx, [rbp+value]
0x180023555  mov     rax, [rcx]
0x180023558  mov     rax, [rax+10h]
0x18002355c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023561  mov     [rbp+pstm], 0
0x180023569  test    ebx, ebx
0x18002356b  js      loc_180023603
0x180023571  mov     rcx, [rbp+ppv]; propBag
0x180023575  lea     r8, [rbp+pstm]; value
0x180023579  lea     rdx, aFilters; "Filters"
0x180023580  call    cs:__imp_PSPropertyBag_ReadStream
0x180023586  test    eax, eax
0x180023588  js      short loc_180023603
0x18002358a  mov     rcx, [rbp+pstm]; pstm
0x18002358e  lea     rdx, [rbp+pv]; pv
0x180023592  mov     r8d, 4; cb
0x180023598  mov     dword ptr [rbp+pv], 0
0x18002359f  call    cs:__imp_IStream_Read
0x1800235a5  xor     esi, esi
0x1800235a7  mov     ebx, eax
0x1800235a9  cmp     dword ptr [rbp+pv], esi
0x1800235ac  jbe     short loc_1800235F3
0x1800235ae  test    ebx, ebx
0x1800235b0  js      short loc_1800235F3
0x1800235b2  mov     rcx, [rbp+pstm]; struct IStream *
0x1800235b6  lea     r8, [rbp+var_8]; void **
0x1800235ba  mov     [rbp+var_8], 0
0x1800235c2  call    ?SHLoadFilterFromStream@@YAJPEAUIStream@@AEBU_GUID@@PEAPEAX@Z; SHLoadFilterFromStream(IStream *,_GUID const &,void * *)
0x1800235c7  mov     ebx, eax
0x1800235c9  test    eax, eax
0x1800235cb  js      short loc_1800235EC
0x1800235cd  mov     rdx, [rbp+var_8]; struct IUnknown *
0x1800235d1  lea     rcx, [rdi+8]; this
0x1800235d5  call    ?AddObject@CFilterCondition@@UEAAJPEAUIUnknown@@@Z; CFilterCondition::AddObject(IUnknown *)
0x1800235da  mov     rcx, [rbp+var_8]
0x1800235de  mov     ebx, eax
0x1800235e0  mov     rax, [rcx]
0x1800235e3  mov     rax, [rax+10h]
0x1800235e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800235ec  inc     esi
0x1800235ee  cmp     esi, dword ptr [rbp+pv]
0x1800235f1  jb      short loc_1800235AE
0x1800235f3  mov     rcx, [rbp+pstm]
0x1800235f7  mov     rax, [rcx]
0x1800235fa  mov     rax, [rax+10h]
0x1800235fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023603  mov     rcx, [rbp+ppv]
0x180023607  mov     rax, [rcx]
0x18002360a  mov     rax, [rax+10h]
0x18002360e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023613  mov     eax, ebx
0x180023615  mov     rbx, [rsp+40h+arg_8]
0x18002361a  add     rsp, 40h
0x18002361e  pop     r15
0x180023620  pop     r14
0x180023622  pop     rdi
0x180023623  pop     rsi
0x180023624  pop     rbp
0x180023625  retn
```
