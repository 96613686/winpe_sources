# CFilterCondition::Load(IStream *)

- ea: `0x18004c3d0`
- end: `0x18004c669`
- name: `?Load@CFilterCondition@@UEAAJPEAUIStream@@@Z`
- size: `665`
- prototype: `__int64 __fastcall(CFilterCondition *__hidden this, struct IStream *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x18000f894`
- `0x18001989c`
- `0x18004c3d0`
- `0x1800835c0`
- `0x1800ea010`

## import_xrefs

- `SHCORE!IStream_Reset` at `0x18004c520`
- `SHCORE!IStream_Reset` at `0x18004c520`
- `SHCORE!IStream_Read` at `0x18004c5f9`
- `SHCORE!IStream_Read` at `0x18004c5f9`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18004c41a`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18004c41a`
- `PROPSYS!PSPropertyBag_ReadInt` at `0x18004c4c6`
- `PROPSYS!PSPropertyBag_ReadInt` at `0x18004c4c6`
- `PROPSYS!PSPropertyBag_ReadPropertyKey` at `0x18004c4e5`
- `PROPSYS!PSPropertyBag_ReadPropertyKey` at `0x18004c4e5`
- `PROPSYS!PSPropertyBag_ReadStream` at `0x18004c50c`
- `PROPSYS!PSPropertyBag_ReadStream` at `0x18004c5b7`
- `PROPSYS!PSPropertyBag_ReadStream` at `0x18004c50c`
- `PROPSYS!PSPropertyBag_ReadStream` at `0x18004c5b7`
- `PROPSYS!PSPropertyBag_ReadBSTR` at `0x18004c492`
- `PROPSYS!PSPropertyBag_ReadBSTR` at `0x18004c4b1`
- `PROPSYS!PSPropertyBag_ReadBSTR` at `0x18004c492`
- `PROPSYS!PSPropertyBag_ReadBSTR` at `0x18004c4b1`

## pseudocode

```c
__int64 __fastcall CFilterCondition::Load(CFilterCondition *this, struct IStream *a2)
{
  HRESULT BSTR; // ebx
  _QWORD *v5; // r14
  struct IStream *v6; // rcx
  unsigned int v8; // esi
  IStream *pstm; // [rsp+30h] [rbp-10h] BYREF
  struct IUnknown *v10; // [rsp+38h] [rbp-8h] BYREF
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
        pv = 0;
        BSTR = (**(__int64 (__fastcall ***)(void *, GUID *, void **))ppv)(
                 ppv,
                 &GUID_00000109_0000_0000_c000_000000000046,
                 &pv);
        if ( BSTR >= 0 )
        {
          BSTR = (*(__int64 (__fastcall **)(void *, struct IStream *))(*(_QWORD *)pv + 40LL))(pv, a2);
          (*(void (__fastcall **)(void *))(*(_QWORD *)pv + 16LL))(pv);
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
                    BSTR = IUnknown_LoadKnownImplFromStream(
                             v6,
                             (const struct _GUID *const *)&off_1800EB310,
                             3u,
                             &GUID_0fc988d4_c935_4b97_a973_46282ea175c8,
                             &pv);
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
                    v8 = 0;
                    for ( BSTR = IStream_Read(pstm, &pv, 4u); v8 < (unsigned int)pv; ++v8 )
                    {
                      if ( BSTR < 0 )
                        break;
                      v10 = 0;
                      BSTR = SHLoadFilterFromStream(pstm, &GUID_fca2857d_1760_4ad3_8c63_c9b602fcbaea, (void **)&v10);
                      if ( BSTR >= 0 )
                      {
                        BSTR = CFilterCondition::AddObject((CFilterCondition *)((char *)this + 8), v10);
                        ((void (__fastcall *)(struct IUnknown *))v10->lpVtbl->Release)(v10);
                      }
                    }
                    (*(void (__fastcall **)(IStream *))(*(_QWORD *)pstm + 16LL))(pstm);
                  }
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
0x18004c3d0  mov     [rsp-28h+arg_8], rbx
0x18004c3d5  push    rbp
0x18004c3d6  push    rsi
0x18004c3d7  push    rdi
0x18004c3d8  push    r14
0x18004c3da  push    r15
0x18004c3dc  mov     rbp, rsp
0x18004c3df  sub     rsp, 40h
0x18004c3e3  cmp     qword ptr [rcx+18h], 0
0x18004c3e8  mov     r15, rdx
0x18004c3eb  mov     rdi, rcx
0x18004c3ee  mov     ebx, 8000FFFFh
0x18004c3f3  jnz     loc_18004C5D1
0x18004c3f9  lea     r14, [rcx+40h]
0x18004c3fd  cmp     qword ptr [r14], 0
0x18004c401  jnz     loc_18004C5D1
0x18004c407  lea     rdx, [rbp+ppv]; ppv
0x18004c40b  mov     [rbp+ppv], 0
0x18004c413  lea     rcx, _GUID_55272a00_42cb_11ce_8135_00aa004bb851; riid
0x18004c41a  call    cs:__imp_PSCreateMemoryPropertyStore
0x18004c420  mov     ebx, eax
0x18004c422  test    eax, eax
0x18004c424  js      loc_18004C5D1
0x18004c42a  mov     rcx, [rbp+ppv]
0x18004c42e  lea     r8, [rbp+pv]
0x18004c432  lea     rdx, _GUID_00000109_0000_0000_c000_000000000046
0x18004c439  mov     [rbp+pv], 0
0x18004c441  mov     rax, [rcx]
0x18004c444  mov     rax, [rax]
0x18004c447  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c44c  mov     ebx, eax
0x18004c44e  test    eax, eax
0x18004c450  js      loc_18004C5C1
0x18004c456  mov     rcx, [rbp+pv]
0x18004c45a  mov     rdx, r15
0x18004c45d  mov     rax, [rcx]
0x18004c460  mov     rax, [rax+28h]
0x18004c464  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c469  mov     rcx, [rbp+pv]
0x18004c46d  mov     ebx, eax
0x18004c46f  mov     rax, [rcx]
0x18004c472  mov     rax, [rax+10h]
0x18004c476  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c47b  test    ebx, ebx
0x18004c47d  js      loc_18004C5C1
0x18004c483  mov     rcx, [rbp+ppv]; propBag
0x18004c487  lea     r8, [rdi+18h]; value
0x18004c48b  lea     rdx, aName; "Name"
0x18004c492  call    cs:__imp_PSPropertyBag_ReadBSTR
0x18004c498  mov     ebx, eax
0x18004c49a  test    eax, eax
0x18004c49c  js      loc_18004C5C1
0x18004c4a2  mov     rcx, [rbp+ppv]; propBag
0x18004c4a6  lea     r8, [rdi+20h]; value
0x18004c4aa  lea     rdx, aInfolder; "InFolder"
0x18004c4b1  call    cs:__imp_PSPropertyBag_ReadBSTR
0x18004c4b7  mov     rcx, [rbp+ppv]; propBag
0x18004c4bb  lea     r8, [rdi+3Ch]; value
0x18004c4bf  lea     rdx, aType_0; "Type"
0x18004c4c6  call    cs:__imp_PSPropertyBag_ReadInt
0x18004c4cc  mov     ebx, eax
0x18004c4ce  test    eax, eax
0x18004c4d0  js      loc_18004C5C1
0x18004c4d6  mov     rcx, [rbp+ppv]; propBag
0x18004c4da  lea     r8, [rdi+28h]; value
0x18004c4de  lea     rdx, aKey; "Key"
0x18004c4e5  call    cs:__imp_PSPropertyBag_ReadPropertyKey
0x18004c4eb  mov     ebx, eax
0x18004c4ed  test    eax, eax
0x18004c4ef  js      loc_18004C5C1
0x18004c4f5  mov     rcx, [rbp+ppv]; propBag
0x18004c4f9  lea     r8, [rbp+value]; value
0x18004c4fd  lea     rdx, aCondition_0; "Condition"
0x18004c504  mov     [rbp+value], 0
0x18004c50c  call    cs:__imp_PSPropertyBag_ReadStream
0x18004c512  mov     ebx, eax
0x18004c514  test    eax, eax
0x18004c516  js      loc_18004C59C
0x18004c51c  mov     rcx, [rbp+value]; pstm
0x18004c520  call    cs:__imp_IStream_Reset
0x18004c526  mov     rcx, [rbp+value]; struct IStream *
0x18004c52a  lea     rax, [rbp+pv]
0x18004c52e  lea     r9, _GUID_0fc988d4_c935_4b97_a973_46282ea175c8; struct _GUID *
0x18004c535  mov     [rsp+40h+var_20], rax; void **
0x18004c53a  mov     r8d, 3; unsigned int
0x18004c540  mov     qword ptr [r14], 0
0x18004c547  lea     rdx, off_1800EB310; struct _GUID **
0x18004c54e  mov     [rbp+pv], 0
0x18004c556  call    ?IUnknown_LoadKnownImplFromStream@@YAJPEAUIStream@@PEBQEBU_GUID@@IAEBU2@PEAPEAX@Z; IUnknown_LoadKnownImplFromStream(IStream *,_GUID const * const *,uint,_GUID const &,void * *)
0x18004c55b  mov     ebx, eax
0x18004c55d  test    eax, eax
0x18004c55f  js      short loc_18004C58C
0x18004c561  mov     rcx, [rbp+pv]
0x18004c565  lea     rdx, _GUID_0fc988d4_c935_4b97_a973_46282ea175c8
0x18004c56c  mov     r8, r14
0x18004c56f  mov     rax, [rcx]
0x18004c572  mov     rax, [rax]
0x18004c575  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c57a  mov     rcx, [rbp+pv]
0x18004c57e  mov     ebx, eax
0x18004c580  mov     rax, [rcx]
0x18004c583  mov     rax, [rax+10h]
0x18004c587  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c58c  mov     rcx, [rbp+value]
0x18004c590  mov     rax, [rcx]
0x18004c593  mov     rax, [rax+10h]
0x18004c597  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c59c  mov     [rbp+pstm], 0
0x18004c5a4  test    ebx, ebx
0x18004c5a6  js      short loc_18004C5C1
0x18004c5a8  mov     rcx, [rbp+ppv]; propBag
0x18004c5ac  lea     r8, [rbp+pstm]; value
0x18004c5b0  lea     rdx, aFilters; "Filters"
0x18004c5b7  call    cs:__imp_PSPropertyBag_ReadStream
0x18004c5bd  test    eax, eax
0x18004c5bf  jns     short loc_18004C5E4
0x18004c5c1  mov     rcx, [rbp+ppv]
0x18004c5c5  mov     rax, [rcx]
0x18004c5c8  mov     rax, [rax+10h]
0x18004c5cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c5d1  mov     eax, ebx
0x18004c5d3  mov     rbx, [rsp+40h+arg_8]
0x18004c5d8  add     rsp, 40h
0x18004c5dc  pop     r15
0x18004c5de  pop     r14
0x18004c5e0  pop     rdi
0x18004c5e1  pop     rsi
0x18004c5e2  pop     rbp
0x18004c5e3  retn
0x18004c5e4  mov     rcx, [rbp+pstm]; pstm
0x18004c5e8  lea     rdx, [rbp+pv]; pv
0x18004c5ec  mov     r8d, 4; cb
0x18004c5f2  mov     dword ptr [rbp+pv], 0
0x18004c5f9  call    cs:__imp_IStream_Read
0x18004c5ff  xor     esi, esi
0x18004c601  mov     ebx, eax
0x18004c603  cmp     dword ptr [rbp+pv], esi
0x18004c606  jbe     short loc_18004C654
0x18004c608  test    ebx, ebx
0x18004c60a  js      short loc_18004C654
0x18004c60c  mov     rcx, [rbp+pstm]; struct IStream *
0x18004c610  lea     r8, [rbp+var_8]; void **
0x18004c614  lea     rdx, _GUID_fca2857d_1760_4ad3_8c63_c9b602fcbaea; struct _GUID *
0x18004c61b  mov     [rbp+var_8], 0
0x18004c623  call    ?SHLoadFilterFromStream@@YAJPEAUIStream@@AEBU_GUID@@PEAPEAX@Z; SHLoadFilterFromStream(IStream *,_GUID const &,void * *)
0x18004c628  mov     ebx, eax
0x18004c62a  test    eax, eax
0x18004c62c  js      short loc_18004C64D
0x18004c62e  mov     rdx, [rbp+var_8]; struct IUnknown *
0x18004c632  lea     rcx, [rdi+8]; this
0x18004c636  call    ?AddObject@CFilterCondition@@UEAAJPEAUIUnknown@@@Z; CFilterCondition::AddObject(IUnknown *)
0x18004c63b  mov     rcx, [rbp+var_8]
0x18004c63f  mov     ebx, eax
0x18004c641  mov     rax, [rcx]
0x18004c644  mov     rax, [rax+10h]
0x18004c648  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c64d  inc     esi
0x18004c64f  cmp     esi, dword ptr [rbp+pv]
0x18004c652  jb      short loc_18004C608
0x18004c654  mov     rcx, [rbp+pstm]
0x18004c658  mov     rax, [rcx]
0x18004c65b  mov     rax, [rax+10h]
0x18004c65f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c664  jmp     loc_18004C5C1
```
