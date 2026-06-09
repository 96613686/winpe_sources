# CFilterCondition::Save(IStream *,int)

- ea: `0x1801c46d0`
- end: `0x1801c48eb`
- name: `?Save@CFilterCondition@@UEAAJPEAUIStream@@H@Z`
- size: `539`
- prototype: `int(CFilterCondition *__hidden this, struct IStream *, int)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180045c60`
- `0x1801b1480`
- `0x1801c3c68`
- `0x1801c46d0`
- `0x180210010`

## import_xrefs

- `SHCORE!SHCreateMemStream` at `0x1801c479a`
- `SHCORE!SHCreateMemStream` at `0x1801c4812`
- `SHCORE!SHCreateMemStream` at `0x1801c479a`
- `SHCORE!SHCreateMemStream` at `0x1801c4812`
- `SHCORE!IStream_Write` at `0x1801c4831`
- `SHCORE!IStream_Write` at `0x1801c4831`
- `SHCORE!IStream_Reset` at `0x1801c47c1`
- `SHCORE!IStream_Reset` at `0x1801c4872`
- `SHCORE!IStream_Reset` at `0x1801c47c1`
- `SHCORE!IStream_Reset` at `0x1801c4872`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x1801c4786`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x1801c4786`
- `PROPSYS!PSPropertyBag_WriteStream` at `0x1801c47d5`
- `PROPSYS!PSPropertyBag_WriteStream` at `0x1801c4886`
- `PROPSYS!PSPropertyBag_WriteStream` at `0x1801c47d5`
- `PROPSYS!PSPropertyBag_WriteStream` at `0x1801c4886`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x1801c4705`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x1801c4705`
- `PROPSYS!PSPropertyBag_WriteBSTR` at `0x1801c4724`
- `PROPSYS!PSPropertyBag_WriteBSTR` at `0x1801c4748`
- `PROPSYS!PSPropertyBag_WriteBSTR` at `0x1801c4724`
- `PROPSYS!PSPropertyBag_WriteBSTR` at `0x1801c4748`
- `PROPSYS!PSPropertyBag_WritePropertyKey` at `0x1801c4767`
- `PROPSYS!PSPropertyBag_WritePropertyKey` at `0x1801c4767`

## pseudocode

```c
__int64 __fastcall CFilterCondition::Save(CFilterCondition *this, struct IStream *a2, int a3)
{
  HRESULT v6; // ebx
  OLECHAR *v7; // r8
  struct IStream *v8; // rax
  const struct _GUID *const *v9; // rdx
  unsigned int v10; // r8d
  IStream *v11; // rsi
  unsigned int *v12; // rax
  IStream *v13; // rax
  struct IStream *v14; // rsi
  unsigned int v15; // r14d
  struct IUnknown *Ptr; // rax
  void *ppv; // [rsp+20h] [rbp-10h] BYREF
  unsigned int pv; // [rsp+78h] [rbp+48h] BYREF

  ppv = 0;
  v6 = PSCreateMemoryPropertyStore(&GUID_55272a00_42cb_11ce_8135_00aa004bb851, &ppv);
  if ( v6 >= 0 )
  {
    v6 = PSPropertyBag_WriteBSTR((IPropertyBag *)ppv, L"Name", *((BSTR *)this + 3));
    if ( v6 < 0 )
      goto LABEL_24;
    v7 = (OLECHAR *)*((_QWORD *)this + 4);
    if ( v7 )
    {
      v6 = PSPropertyBag_WriteBSTR((IPropertyBag *)ppv, L"InFolder", v7);
      if ( v6 < 0 )
        goto LABEL_24;
    }
    v6 = PSPropertyBag_WritePropertyKey((IPropertyBag *)ppv, L"Key", (const PROPERTYKEY *const)this + 2);
    if ( v6 < 0 )
      goto LABEL_24;
    v6 = PSPropertyBag_WriteDWORD((IPropertyBag *)ppv, L"Type", *((_DWORD *)this + 15));
    if ( v6 < 0 )
      goto LABEL_24;
    v8 = SHCreateMemStream(0, 0);
    v11 = v8;
    if ( !v8 )
      goto LABEL_23;
    v6 = IUnknown_SaveKnownImplToStream(v8, v9, v10, *((struct IUnknown **)this + 8));
    if ( v6 >= 0 )
    {
      IStream_Reset(v11);
      v6 = PSPropertyBag_WriteStream((IPropertyBag *)ppv, L"Condition", v11);
    }
    (*(void (__fastcall **)(IStream *))(*(_QWORD *)v11 + 16LL))(v11);
    if ( v6 < 0 )
      goto LABEL_24;
    v12 = (unsigned int *)*((_QWORD *)this + 9);
    if ( v12 )
    {
      pv = *v12;
      if ( pv )
      {
        v13 = SHCreateMemStream(0, 0);
        v14 = v13;
        if ( v13 )
        {
          v15 = 0;
          v6 = IStream_Write(v13, &pv, 4u);
          if ( pv )
          {
            while ( v6 >= 0 )
            {
              Ptr = (struct IUnknown *)DPA_GetPtr(*((HDPA *)this + 9), v15++);
              v6 = IUnknown_SaveToStream(v14, a3, Ptr);
              if ( v15 >= pv )
                goto LABEL_17;
            }
          }
          else
          {
LABEL_17:
            if ( v6 >= 0 )
            {
              IStream_Reset(v14);
              v6 = PSPropertyBag_WriteStream((IPropertyBag *)ppv, L"Filters", v14);
            }
          }
          (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v14 + 16LL))(v14);
          if ( v6 < 0 )
            goto LABEL_24;
          goto LABEL_22;
        }
LABEL_23:
        v6 = -2147024882;
        goto LABEL_24;
      }
    }
    else
    {
      pv = 0;
    }
LABEL_22:
    v6 = IUnknown_SaveToStream(a2, a3, (struct IUnknown *)ppv);
LABEL_24:
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1801c46d0  mov     [rsp-28h+arg_0], rbx
0x1801c46d5  mov     [rsp-28h+arg_8], rsi
0x1801c46da  push    rbp
0x1801c46db  push    rdi
0x1801c46dc  push    r12
0x1801c46de  push    r14
0x1801c46e0  push    r15
0x1801c46e2  mov     rbp, rsp
0x1801c46e5  sub     rsp, 30h
0x1801c46e9  mov     r12, rdx
0x1801c46ec  mov     [rbp+ppv], 0
0x1801c46f4  mov     rdi, rcx
0x1801c46f7  lea     rdx, [rbp+ppv]; ppv
0x1801c46fb  lea     rcx, _GUID_55272a00_42cb_11ce_8135_00aa004bb851; riid
0x1801c4702  mov     r15d, r8d
0x1801c4705  call    cs:__imp_PSCreateMemoryPropertyStore
0x1801c470b  mov     ebx, eax
0x1801c470d  test    eax, eax
0x1801c470f  js      loc_1801C48D2
0x1801c4715  mov     r8, [rdi+18h]; value
0x1801c4719  lea     rdx, aName; "Name"
0x1801c4720  mov     rcx, [rbp+ppv]; propBag
0x1801c4724  call    cs:__imp_PSPropertyBag_WriteBSTR
0x1801c472a  mov     ebx, eax
0x1801c472c  test    eax, eax
0x1801c472e  js      loc_1801C48C2
0x1801c4734  mov     r8, [rdi+20h]; value
0x1801c4738  test    r8, r8
0x1801c473b  jz      short loc_1801C4758
0x1801c473d  mov     rcx, [rbp+ppv]; propBag
0x1801c4741  lea     rdx, aInfolder; "InFolder"
0x1801c4748  call    cs:__imp_PSPropertyBag_WriteBSTR
0x1801c474e  mov     ebx, eax
0x1801c4750  test    eax, eax
0x1801c4752  js      loc_1801C48C2
0x1801c4758  mov     rcx, [rbp+ppv]; propBag
0x1801c475c  lea     r8, [rdi+28h]; value
0x1801c4760  lea     rdx, aKey; "Key"
0x1801c4767  call    cs:__imp_PSPropertyBag_WritePropertyKey
0x1801c476d  mov     ebx, eax
0x1801c476f  test    eax, eax
0x1801c4771  js      loc_1801C48C2
0x1801c4777  mov     r8d, [rdi+3Ch]; value
0x1801c477b  lea     rdx, aType; "Type"
0x1801c4782  mov     rcx, [rbp+ppv]; propBag
0x1801c4786  call    cs:__imp_PSPropertyBag_WriteDWORD
0x1801c478c  mov     ebx, eax
0x1801c478e  test    eax, eax
0x1801c4790  js      loc_1801C48C2
0x1801c4796  xor     edx, edx; cbInit
0x1801c4798  xor     ecx, ecx; pInit
0x1801c479a  call    cs:__imp_SHCreateMemStream
0x1801c47a0  mov     rsi, rax
0x1801c47a3  test    rax, rax
0x1801c47a6  jz      loc_1801C48BD
0x1801c47ac  mov     r9, [rdi+40h]; struct IUnknown *
0x1801c47b0  mov     rcx, rax; pstm
0x1801c47b3  call    ?IUnknown_SaveKnownImplToStream@@YAJPEAUIStream@@PEBQEBU_GUID@@IPEAUIUnknown@@@Z; IUnknown_SaveKnownImplToStream(IStream *,_GUID const * const *,uint,IUnknown *)
0x1801c47b8  mov     ebx, eax
0x1801c47ba  test    eax, eax
0x1801c47bc  js      short loc_1801C47DD
0x1801c47be  mov     rcx, rsi; pstm
0x1801c47c1  call    cs:__imp_IStream_Reset
0x1801c47c7  mov     rcx, [rbp+ppv]; propBag
0x1801c47cb  lea     rdx, aCondition; "Condition"
0x1801c47d2  mov     r8, rsi; value
0x1801c47d5  call    cs:__imp_PSPropertyBag_WriteStream
0x1801c47db  mov     ebx, eax
0x1801c47dd  mov     rax, [rsi]
0x1801c47e0  mov     rcx, rsi
0x1801c47e3  mov     rax, [rax+10h]
0x1801c47e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c47ec  test    ebx, ebx
0x1801c47ee  js      loc_1801C48C2
0x1801c47f4  mov     rax, [rdi+48h]
0x1801c47f8  test    rax, rax
0x1801c47fb  jz      loc_1801C48A3
0x1801c4801  mov     eax, [rax]
0x1801c4803  mov     [rbp+pv], eax
0x1801c4806  test    eax, eax
0x1801c4808  jz      loc_1801C48AA
0x1801c480e  xor     edx, edx; cbInit
0x1801c4810  xor     ecx, ecx; pInit
0x1801c4812  call    cs:__imp_SHCreateMemStream
0x1801c4818  mov     rsi, rax
0x1801c481b  test    rax, rax
0x1801c481e  jz      loc_1801C48BD
0x1801c4824  mov     r8d, 4; cb
0x1801c482a  lea     rdx, [rbp+pv]; pv
0x1801c482e  mov     rcx, rax; pstm
0x1801c4831  call    cs:__imp_IStream_Write
0x1801c4837  xor     r14d, r14d
0x1801c483a  mov     ebx, eax
0x1801c483c  cmp     [rbp+pv], r14d
0x1801c4840  jbe     short loc_1801C486B
0x1801c4842  test    ebx, ebx
0x1801c4844  js      short loc_1801C488E
0x1801c4846  mov     rcx, [rdi+48h]; hdpa
0x1801c484a  mov     edx, r14d; i
0x1801c484d  call    DPA_GetPtr
0x1801c4852  mov     r8, rax; struct IUnknown *
0x1801c4855  mov     edx, r15d; int
0x1801c4858  mov     rcx, rsi; struct IStream *
0x1801c485b  call    ?IUnknown_SaveToStream@@YAJPEAUIStream@@HPEAUIUnknown@@@Z; IUnknown_SaveToStream(IStream *,int,IUnknown *)
0x1801c4860  inc     r14d
0x1801c4863  mov     ebx, eax
0x1801c4865  cmp     r14d, [rbp+pv]
0x1801c4869  jb      short loc_1801C4842
0x1801c486b  test    ebx, ebx
0x1801c486d  js      short loc_1801C488E
0x1801c486f  mov     rcx, rsi; pstm
0x1801c4872  call    cs:__imp_IStream_Reset
0x1801c4878  mov     rcx, [rbp+ppv]; propBag
0x1801c487c  lea     rdx, aFilters; "Filters"
0x1801c4883  mov     r8, rsi; value
0x1801c4886  call    cs:__imp_PSPropertyBag_WriteStream
0x1801c488c  mov     ebx, eax
0x1801c488e  mov     rax, [rsi]
0x1801c4891  mov     rcx, rsi
0x1801c4894  mov     rax, [rax+10h]
0x1801c4898  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c489d  test    ebx, ebx
0x1801c489f  jns     short loc_1801C48AA
0x1801c48a1  jmp     short loc_1801C48C2
0x1801c48a3  mov     [rbp+pv], 0
0x1801c48aa  mov     r8, [rbp+ppv]; struct IUnknown *
0x1801c48ae  mov     edx, r15d; int
0x1801c48b1  mov     rcx, r12; struct IStream *
0x1801c48b4  call    ?IUnknown_SaveToStream@@YAJPEAUIStream@@HPEAUIUnknown@@@Z; IUnknown_SaveToStream(IStream *,int,IUnknown *)
0x1801c48b9  mov     ebx, eax
0x1801c48bb  jmp     short loc_1801C48C2
0x1801c48bd  mov     ebx, 8007000Eh
0x1801c48c2  mov     rcx, [rbp+ppv]
0x1801c48c6  mov     rax, [rcx]
0x1801c48c9  mov     rax, [rax+10h]
0x1801c48cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c48d2  mov     rsi, [rsp+30h+arg_8]
0x1801c48d7  mov     eax, ebx
0x1801c48d9  mov     rbx, [rsp+30h+arg_0]
0x1801c48de  add     rsp, 30h
0x1801c48e2  pop     r15
0x1801c48e4  pop     r14
0x1801c48e6  pop     r12
0x1801c48e8  pop     rdi
0x1801c48e9  pop     rbp
0x1801c48ea  retn
```
