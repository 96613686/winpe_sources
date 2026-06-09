# CFilterCondition::Save(IStream *,int)

- ea: `0x18005eeb0`
- end: `0x18005f0d9`
- name: `?Save@CFilterCondition@@UEAAJPEAUIStream@@H@Z`
- size: `553`
- prototype: `int(CFilterCondition *__hidden this, struct IStream *, int)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800448b4`
- `0x180047ae0`
- `0x18004e270`
- `0x18005eeb0`
- `0x1800ea010`

## import_xrefs

- `SHCORE!IStream_Reset` at `0x18005efae`
- `SHCORE!IStream_Reset` at `0x18005f060`
- `SHCORE!IStream_Reset` at `0x18005efae`
- `SHCORE!IStream_Reset` at `0x18005f060`
- `SHCORE!SHCreateMemStream` at `0x18005ef7a`
- `SHCORE!SHCreateMemStream` at `0x18005efff`
- `SHCORE!SHCreateMemStream` at `0x18005ef7a`
- `SHCORE!SHCreateMemStream` at `0x18005efff`
- `SHCORE!IStream_Write` at `0x18005f01e`
- `SHCORE!IStream_Write` at `0x18005f01e`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18005eee5`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18005eee5`
- `PROPSYS!PSPropertyBag_WriteBSTR` at `0x18005ef04`
- `PROPSYS!PSPropertyBag_WriteBSTR` at `0x18005ef28`
- `PROPSYS!PSPropertyBag_WriteBSTR` at `0x18005ef04`
- `PROPSYS!PSPropertyBag_WriteBSTR` at `0x18005ef28`
- `PROPSYS!PSPropertyBag_WritePropertyKey` at `0x18005ef47`
- `PROPSYS!PSPropertyBag_WritePropertyKey` at `0x18005ef47`
- `PROPSYS!PSPropertyBag_WriteStream` at `0x18005efc2`
- `PROPSYS!PSPropertyBag_WriteStream` at `0x18005f074`
- `PROPSYS!PSPropertyBag_WriteStream` at `0x18005efc2`
- `PROPSYS!PSPropertyBag_WriteStream` at `0x18005f074`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x18005ef66`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x18005ef66`

## pseudocode

```c
__int64 __fastcall CFilterCondition::Save(CFilterCondition *this, struct IStream *a2, int a3)
{
  HRESULT v6; // ebx
  OLECHAR *v7; // r8
  struct IStream *v8; // rax
  IStream *v9; // rsi
  unsigned int *v10; // rax
  IStream *v11; // rax
  struct IStream *v12; // rsi
  unsigned int v13; // r14d
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
    v9 = v8;
    if ( !v8 )
      goto LABEL_23;
    v6 = IUnknown_SaveKnownImplToStream(
           v8,
           (const struct _GUID *const *)&off_1800EB310,
           3u,
           *((struct IUnknown **)this + 8));
    if ( v6 >= 0 )
    {
      IStream_Reset(v9);
      v6 = PSPropertyBag_WriteStream((IPropertyBag *)ppv, L"Condition", v9);
    }
    (*(void (__fastcall **)(IStream *))(*(_QWORD *)v9 + 16LL))(v9);
    if ( v6 < 0 )
      goto LABEL_24;
    v10 = (unsigned int *)*((_QWORD *)this + 9);
    if ( v10 )
    {
      pv = *v10;
      if ( pv )
      {
        v11 = SHCreateMemStream(0, 0);
        v12 = v11;
        if ( v11 )
        {
          v13 = 0;
          v6 = IStream_Write(v11, &pv, 4u);
          if ( pv )
          {
            while ( v6 >= 0 )
            {
              Ptr = (struct IUnknown *)g_pfn_DPA_GetPtr(*((HDPA *)this + 9), v13++);
              v6 = IUnknown_SaveToStream(v12, a3, Ptr);
              if ( v13 >= pv )
                goto LABEL_17;
            }
          }
          else
          {
LABEL_17:
            if ( v6 >= 0 )
            {
              IStream_Reset(v12);
              v6 = PSPropertyBag_WriteStream((IPropertyBag *)ppv, L"Filters", v12);
            }
          }
          (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v12 + 16LL))(v12);
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
0x18005eeb0  mov     [rsp-28h+arg_0], rbx
0x18005eeb5  mov     [rsp-28h+arg_8], rsi
0x18005eeba  push    rbp
0x18005eebb  push    rdi
0x18005eebc  push    r12
0x18005eebe  push    r14
0x18005eec0  push    r15
0x18005eec2  mov     rbp, rsp
0x18005eec5  sub     rsp, 30h
0x18005eec9  mov     r12, rdx
0x18005eecc  mov     [rbp+ppv], 0
0x18005eed4  mov     rdi, rcx
0x18005eed7  lea     rdx, [rbp+ppv]; ppv
0x18005eedb  lea     rcx, _GUID_55272a00_42cb_11ce_8135_00aa004bb851; riid
0x18005eee2  mov     r15d, r8d
0x18005eee5  call    cs:__imp_PSCreateMemoryPropertyStore
0x18005eeeb  mov     ebx, eax
0x18005eeed  test    eax, eax
0x18005eeef  js      loc_18005F0C0
0x18005eef5  mov     r8, [rdi+18h]; value
0x18005eef9  lea     rdx, aName; "Name"
0x18005ef00  mov     rcx, [rbp+ppv]; propBag
0x18005ef04  call    cs:__imp_PSPropertyBag_WriteBSTR
0x18005ef0a  mov     ebx, eax
0x18005ef0c  test    eax, eax
0x18005ef0e  js      loc_18005F0B0
0x18005ef14  mov     r8, [rdi+20h]; value
0x18005ef18  test    r8, r8
0x18005ef1b  jz      short loc_18005EF38
0x18005ef1d  mov     rcx, [rbp+ppv]; propBag
0x18005ef21  lea     rdx, aInfolder; "InFolder"
0x18005ef28  call    cs:__imp_PSPropertyBag_WriteBSTR
0x18005ef2e  mov     ebx, eax
0x18005ef30  test    eax, eax
0x18005ef32  js      loc_18005F0B0
0x18005ef38  mov     rcx, [rbp+ppv]; propBag
0x18005ef3c  lea     r8, [rdi+28h]; value
0x18005ef40  lea     rdx, aKey; "Key"
0x18005ef47  call    cs:__imp_PSPropertyBag_WritePropertyKey
0x18005ef4d  mov     ebx, eax
0x18005ef4f  test    eax, eax
0x18005ef51  js      loc_18005F0B0
0x18005ef57  mov     r8d, [rdi+3Ch]; value
0x18005ef5b  lea     rdx, aType_0; "Type"
0x18005ef62  mov     rcx, [rbp+ppv]; propBag
0x18005ef66  call    cs:__imp_PSPropertyBag_WriteDWORD
0x18005ef6c  mov     ebx, eax
0x18005ef6e  test    eax, eax
0x18005ef70  js      loc_18005F0B0
0x18005ef76  xor     edx, edx; cbInit
0x18005ef78  xor     ecx, ecx; pInit
0x18005ef7a  call    cs:__imp_SHCreateMemStream
0x18005ef80  mov     rsi, rax
0x18005ef83  test    rax, rax
0x18005ef86  jz      loc_18005F0AB
0x18005ef8c  mov     r9, [rdi+40h]; struct IUnknown *
0x18005ef90  lea     rdx, off_1800EB310; struct _GUID **
0x18005ef97  mov     r8d, 3; unsigned int
0x18005ef9d  mov     rcx, rax; pstm
0x18005efa0  call    ?IUnknown_SaveKnownImplToStream@@YAJPEAUIStream@@PEBQEBU_GUID@@IPEAUIUnknown@@@Z; IUnknown_SaveKnownImplToStream(IStream *,_GUID const * const *,uint,IUnknown *)
0x18005efa5  mov     ebx, eax
0x18005efa7  test    eax, eax
0x18005efa9  js      short loc_18005EFCA
0x18005efab  mov     rcx, rsi; pstm
0x18005efae  call    cs:__imp_IStream_Reset
0x18005efb4  mov     rcx, [rbp+ppv]; propBag
0x18005efb8  lea     rdx, aCondition_0; "Condition"
0x18005efbf  mov     r8, rsi; value
0x18005efc2  call    cs:__imp_PSPropertyBag_WriteStream
0x18005efc8  mov     ebx, eax
0x18005efca  mov     rax, [rsi]
0x18005efcd  mov     rcx, rsi
0x18005efd0  mov     rax, [rax+10h]
0x18005efd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005efd9  test    ebx, ebx
0x18005efdb  js      loc_18005F0B0
0x18005efe1  mov     rax, [rdi+48h]
0x18005efe5  test    rax, rax
0x18005efe8  jz      loc_18005F091
0x18005efee  mov     eax, [rax]
0x18005eff0  mov     [rbp+pv], eax
0x18005eff3  test    eax, eax
0x18005eff5  jz      loc_18005F098
0x18005effb  xor     edx, edx; cbInit
0x18005effd  xor     ecx, ecx; pInit
0x18005efff  call    cs:__imp_SHCreateMemStream
0x18005f005  mov     rsi, rax
0x18005f008  test    rax, rax
0x18005f00b  jz      loc_18005F0AB
0x18005f011  mov     r8d, 4; cb
0x18005f017  lea     rdx, [rbp+pv]; pv
0x18005f01b  mov     rcx, rax; pstm
0x18005f01e  call    cs:__imp_IStream_Write
0x18005f024  xor     r14d, r14d
0x18005f027  mov     ebx, eax
0x18005f029  cmp     [rbp+pv], r14d
0x18005f02d  jbe     short loc_18005F059
0x18005f02f  test    ebx, ebx
0x18005f031  js      short loc_18005F07C
0x18005f033  mov     rcx, [rdi+48h]; hdpa
0x18005f037  mov     edx, r14d; i
0x18005f03a  call    cs:g_pfn_DPA_GetPtr
0x18005f040  mov     edx, r15d; int
0x18005f043  mov     rcx, rsi; struct IStream *
0x18005f046  mov     r8, rax; struct IUnknown *
0x18005f049  call    ?IUnknown_SaveToStream@@YAJPEAUIStream@@HPEAUIUnknown@@@Z; IUnknown_SaveToStream(IStream *,int,IUnknown *)
0x18005f04e  inc     r14d
0x18005f051  mov     ebx, eax
0x18005f053  cmp     r14d, [rbp+pv]
0x18005f057  jb      short loc_18005F02F
0x18005f059  test    ebx, ebx
0x18005f05b  js      short loc_18005F07C
0x18005f05d  mov     rcx, rsi; pstm
0x18005f060  call    cs:__imp_IStream_Reset
0x18005f066  mov     rcx, [rbp+ppv]; propBag
0x18005f06a  lea     rdx, aFilters; "Filters"
0x18005f071  mov     r8, rsi; value
0x18005f074  call    cs:__imp_PSPropertyBag_WriteStream
0x18005f07a  mov     ebx, eax
0x18005f07c  mov     rax, [rsi]
0x18005f07f  mov     rcx, rsi
0x18005f082  mov     rax, [rax+10h]
0x18005f086  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f08b  test    ebx, ebx
0x18005f08d  js      short loc_18005F0B0
0x18005f08f  jmp     short loc_18005F098
0x18005f091  mov     [rbp+pv], 0
0x18005f098  mov     r8, [rbp+ppv]; struct IUnknown *
0x18005f09c  mov     edx, r15d; int
0x18005f09f  mov     rcx, r12; struct IStream *
0x18005f0a2  call    ?IUnknown_SaveToStream@@YAJPEAUIStream@@HPEAUIUnknown@@@Z; IUnknown_SaveToStream(IStream *,int,IUnknown *)
0x18005f0a7  mov     ebx, eax
0x18005f0a9  jmp     short loc_18005F0B0
0x18005f0ab  mov     ebx, 8007000Eh
0x18005f0b0  mov     rcx, [rbp+ppv]
0x18005f0b4  mov     rax, [rcx]
0x18005f0b7  mov     rax, [rax+10h]
0x18005f0bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f0c0  mov     rsi, [rsp+30h+arg_8]
0x18005f0c5  mov     eax, ebx
0x18005f0c7  mov     rbx, [rsp+30h+arg_0]
0x18005f0cc  add     rsp, 30h
0x18005f0d0  pop     r15
0x18005f0d2  pop     r14
0x18005f0d4  pop     r12
0x18005f0d6  pop     rdi
0x18005f0d7  pop     rbp
0x18005f0d8  retn
```
