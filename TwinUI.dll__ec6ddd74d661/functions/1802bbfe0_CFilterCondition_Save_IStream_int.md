# CFilterCondition::Save(IStream *,int)

- ea: `0x1802bbfe0`
- end: `0x1802bc24b`
- name: `?Save@CFilterCondition@@UEAAJPEAUIStream@@H@Z`
- size: `619`
- prototype: `int(CFilterCondition *__hidden this, struct IStream *, int)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800b39b0`
- `0x1802badac`
- `0x1802bae9c`
- `0x1802bbfe0`
- `0x1803bb010`

## import_xrefs

- `PROPSYS!PSCreateMemoryPropertyStore` at `0x1802bc015`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x1802bc015`
- `PROPSYS!PSPropertyBag_WriteStream` at `0x1802bc10f`
- `PROPSYS!PSPropertyBag_WriteStream` at `0x1802bc1df`
- `PROPSYS!PSPropertyBag_WriteStream` at `0x1802bc10f`
- `PROPSYS!PSPropertyBag_WriteStream` at `0x1802bc1df`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x1802bc0ae`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x1802bc0ae`
- `PROPSYS!PSPropertyBag_WritePropertyKey` at `0x1802bc089`
- `PROPSYS!PSPropertyBag_WritePropertyKey` at `0x1802bc089`
- `PROPSYS!PSPropertyBag_WriteBSTR` at `0x1802bc03a`
- `PROPSYS!PSPropertyBag_WriteBSTR` at `0x1802bc064`
- `PROPSYS!PSPropertyBag_WriteBSTR` at `0x1802bc03a`
- `PROPSYS!PSPropertyBag_WriteBSTR` at `0x1802bc064`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x1802bc0f5`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x1802bc1c5`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x1802bc0f5`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x1802bc1c5`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x1802bc177`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x1802bc177`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x1802bc0c8`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x1802bc152`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x1802bc0c8`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x1802bc152`

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
              Ptr = (struct IUnknown *)g_pfn_DPA_GetPtr(*((HDPA *)this + 9), v15++);
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
0x1802bbfe0  mov     [rsp-28h+arg_0], rbx
0x1802bbfe5  mov     [rsp-28h+arg_8], rsi
0x1802bbfea  push    rbp
0x1802bbfeb  push    rdi
0x1802bbfec  push    r12
0x1802bbfee  push    r14
0x1802bbff0  push    r15
0x1802bbff2  mov     rbp, rsp
0x1802bbff5  sub     rsp, 30h
0x1802bbff9  mov     r12, rdx
0x1802bbffc  mov     [rbp+ppv], 0
0x1802bc004  mov     rdi, rcx
0x1802bc007  lea     rdx, [rbp+ppv]; ppv
0x1802bc00b  lea     rcx, _GUID_55272a00_42cb_11ce_8135_00aa004bb851; riid
0x1802bc012  mov     r15d, r8d
0x1802bc015  call    cs:__imp_PSCreateMemoryPropertyStore
0x1802bc01c  nop     dword ptr [rax+rax+00h]
0x1802bc021  mov     ebx, eax
0x1802bc023  test    eax, eax
0x1802bc025  js      loc_1802BC231
0x1802bc02b  mov     r8, [rdi+18h]; value
0x1802bc02f  lea     rdx, propName; "Name"
0x1802bc036  mov     rcx, [rbp+ppv]; propBag
0x1802bc03a  call    cs:__imp_PSPropertyBag_WriteBSTR
0x1802bc041  nop     dword ptr [rax+rax+00h]
0x1802bc046  mov     ebx, eax
0x1802bc048  test    eax, eax
0x1802bc04a  js      loc_1802BC221
0x1802bc050  mov     r8, [rdi+20h]; value
0x1802bc054  test    r8, r8
0x1802bc057  jz      short loc_1802BC07A
0x1802bc059  mov     rcx, [rbp+ppv]; propBag
0x1802bc05d  lea     rdx, aInfolder; "InFolder"
0x1802bc064  call    cs:__imp_PSPropertyBag_WriteBSTR
0x1802bc06b  nop     dword ptr [rax+rax+00h]
0x1802bc070  mov     ebx, eax
0x1802bc072  test    eax, eax
0x1802bc074  js      loc_1802BC221
0x1802bc07a  mov     rcx, [rbp+ppv]; propBag
0x1802bc07e  lea     r8, [rdi+28h]; value
0x1802bc082  lea     rdx, aKey; "Key"
0x1802bc089  call    cs:__imp_PSPropertyBag_WritePropertyKey
0x1802bc090  nop     dword ptr [rax+rax+00h]
0x1802bc095  mov     ebx, eax
0x1802bc097  test    eax, eax
0x1802bc099  js      loc_1802BC221
0x1802bc09f  mov     r8d, [rdi+3Ch]; value
0x1802bc0a3  lea     rdx, aType; "Type"
0x1802bc0aa  mov     rcx, [rbp+ppv]; propBag
0x1802bc0ae  call    cs:__imp_PSPropertyBag_WriteDWORD
0x1802bc0b5  nop     dword ptr [rax+rax+00h]
0x1802bc0ba  mov     ebx, eax
0x1802bc0bc  test    eax, eax
0x1802bc0be  js      loc_1802BC221
0x1802bc0c4  xor     edx, edx; cbInit
0x1802bc0c6  xor     ecx, ecx; pInit
0x1802bc0c8  call    cs:__imp_SHCreateMemStream
0x1802bc0cf  nop     dword ptr [rax+rax+00h]
0x1802bc0d4  mov     rsi, rax
0x1802bc0d7  test    rax, rax
0x1802bc0da  jz      loc_1802BC21C
0x1802bc0e0  mov     r9, [rdi+40h]; struct IUnknown *
0x1802bc0e4  mov     rcx, rax; pstm
0x1802bc0e7  call    ?IUnknown_SaveKnownImplToStream@@YAJPEAUIStream@@PEBQEBU_GUID@@IPEAUIUnknown@@@Z; IUnknown_SaveKnownImplToStream(IStream *,_GUID const * const *,uint,IUnknown *)
0x1802bc0ec  mov     ebx, eax
0x1802bc0ee  test    eax, eax
0x1802bc0f0  js      short loc_1802BC11D
0x1802bc0f2  mov     rcx, rsi; pstm
0x1802bc0f5  call    cs:__imp_IStream_Reset
0x1802bc0fc  nop     dword ptr [rax+rax+00h]
0x1802bc101  mov     rcx, [rbp+ppv]; propBag
0x1802bc105  lea     rdx, aCondition; "Condition"
0x1802bc10c  mov     r8, rsi; value
0x1802bc10f  call    cs:__imp_PSPropertyBag_WriteStream
0x1802bc116  nop     dword ptr [rax+rax+00h]
0x1802bc11b  mov     ebx, eax
0x1802bc11d  mov     rax, [rsi]
0x1802bc120  mov     rcx, rsi
0x1802bc123  mov     rax, [rax+10h]
0x1802bc127  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802bc12c  test    ebx, ebx
0x1802bc12e  js      loc_1802BC221
0x1802bc134  mov     rax, [rdi+48h]
0x1802bc138  test    rax, rax
0x1802bc13b  jz      loc_1802BC202
0x1802bc141  mov     eax, [rax]
0x1802bc143  mov     [rbp+pv], eax
0x1802bc146  test    eax, eax
0x1802bc148  jz      loc_1802BC209
0x1802bc14e  xor     edx, edx; cbInit
0x1802bc150  xor     ecx, ecx; pInit
0x1802bc152  call    cs:__imp_SHCreateMemStream
0x1802bc159  nop     dword ptr [rax+rax+00h]
0x1802bc15e  mov     rsi, rax
0x1802bc161  test    rax, rax
0x1802bc164  jz      loc_1802BC21C
0x1802bc16a  mov     r8d, 4; cb
0x1802bc170  lea     rdx, [rbp+pv]; pv
0x1802bc174  mov     rcx, rax; pstm
0x1802bc177  call    cs:__imp_IStream_Write
0x1802bc17e  nop     dword ptr [rax+rax+00h]
0x1802bc183  xor     r14d, r14d
0x1802bc186  mov     ebx, eax
0x1802bc188  cmp     [rbp+pv], r14d
0x1802bc18c  jbe     short loc_1802BC1BE
0x1802bc18e  test    ebx, ebx
0x1802bc190  js      short loc_1802BC1ED
0x1802bc192  mov     rcx, [rdi+48h]; hdpa
0x1802bc196  mov     edx, r14d; i
0x1802bc199  call    cs:g_pfn_DPA_GetPtr
0x1802bc1a0  nop     dword ptr [rax+rax+00h]
0x1802bc1a5  mov     edx, r15d; int
0x1802bc1a8  mov     rcx, rsi; struct IStream *
0x1802bc1ab  mov     r8, rax; struct IUnknown *
0x1802bc1ae  call    ?IUnknown_SaveToStream@@YAJPEAUIStream@@HPEAUIUnknown@@@Z; IUnknown_SaveToStream(IStream *,int,IUnknown *)
0x1802bc1b3  inc     r14d
0x1802bc1b6  mov     ebx, eax
0x1802bc1b8  cmp     r14d, [rbp+pv]
0x1802bc1bc  jb      short loc_1802BC18E
0x1802bc1be  test    ebx, ebx
0x1802bc1c0  js      short loc_1802BC1ED
0x1802bc1c2  mov     rcx, rsi; pstm
0x1802bc1c5  call    cs:__imp_IStream_Reset
0x1802bc1cc  nop     dword ptr [rax+rax+00h]
0x1802bc1d1  mov     rcx, [rbp+ppv]; propBag
0x1802bc1d5  lea     rdx, aFilters; "Filters"
0x1802bc1dc  mov     r8, rsi; value
0x1802bc1df  call    cs:__imp_PSPropertyBag_WriteStream
0x1802bc1e6  nop     dword ptr [rax+rax+00h]
0x1802bc1eb  mov     ebx, eax
0x1802bc1ed  mov     rax, [rsi]
0x1802bc1f0  mov     rcx, rsi
0x1802bc1f3  mov     rax, [rax+10h]
0x1802bc1f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802bc1fc  test    ebx, ebx
0x1802bc1fe  jns     short loc_1802BC209
0x1802bc200  jmp     short loc_1802BC221
0x1802bc202  mov     [rbp+pv], 0
0x1802bc209  mov     r8, [rbp+ppv]; struct IUnknown *
0x1802bc20d  mov     edx, r15d; int
0x1802bc210  mov     rcx, r12; struct IStream *
0x1802bc213  call    ?IUnknown_SaveToStream@@YAJPEAUIStream@@HPEAUIUnknown@@@Z; IUnknown_SaveToStream(IStream *,int,IUnknown *)
0x1802bc218  mov     ebx, eax
0x1802bc21a  jmp     short loc_1802BC221
0x1802bc21c  mov     ebx, 8007000Eh
0x1802bc221  mov     rcx, [rbp+ppv]
0x1802bc225  mov     rax, [rcx]
0x1802bc228  mov     rax, [rax+10h]
0x1802bc22c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802bc231  mov     rsi, [rsp+30h+arg_8]
0x1802bc236  mov     eax, ebx
0x1802bc238  mov     rbx, [rsp+30h+arg_0]
0x1802bc23d  add     rsp, 30h
0x1802bc241  pop     r15
0x1802bc243  pop     r14
0x1802bc245  pop     r12
0x1802bc247  pop     rdi
0x1802bc248  pop     rbp
0x1802bc249  retn
```
