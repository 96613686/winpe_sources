# CFilterCondition::Save(IStream *,int)

- ea: `0x1800240e0`
- end: `0x1800242fc`
- name: `?Save@CFilterCondition@@UEAAJPEAUIStream@@H@Z`
- size: `540`
- prototype: `int(CFilterCondition *__hidden this, struct IStream *, int)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180003790`
- `0x180023214`
- `0x180023300`
- `0x1800240e0`
- `0x180051010`

## import_xrefs

- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180024241`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180024241`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x1800241d1`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x180024283`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x1800241d1`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x180024283`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x1800241aa`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x180024222`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x1800241aa`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x180024222`
- `PROPSYS!PSPropertyBag_WriteBSTR` at `0x180024134`
- `PROPSYS!PSPropertyBag_WriteBSTR` at `0x180024158`
- `PROPSYS!PSPropertyBag_WriteBSTR` at `0x180024134`
- `PROPSYS!PSPropertyBag_WriteBSTR` at `0x180024158`
- `PROPSYS!PSPropertyBag_WritePropertyKey` at `0x180024177`
- `PROPSYS!PSPropertyBag_WritePropertyKey` at `0x180024177`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x180024196`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x180024196`
- `PROPSYS!PSPropertyBag_WriteStream` at `0x1800241e5`
- `PROPSYS!PSPropertyBag_WriteStream` at `0x180024297`
- `PROPSYS!PSPropertyBag_WriteStream` at `0x1800241e5`
- `PROPSYS!PSPropertyBag_WriteStream` at `0x180024297`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180024115`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180024115`

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
0x1800240e0  mov     [rsp-28h+arg_0], rbx
0x1800240e5  mov     [rsp-28h+arg_8], rsi
0x1800240ea  push    rbp
0x1800240eb  push    rdi
0x1800240ec  push    r12
0x1800240ee  push    r14
0x1800240f0  push    r15
0x1800240f2  mov     rbp, rsp
0x1800240f5  sub     rsp, 30h
0x1800240f9  mov     r12, rdx
0x1800240fc  mov     [rbp+ppv], 0
0x180024104  mov     rdi, rcx
0x180024107  lea     rdx, [rbp+ppv]; ppv
0x18002410b  lea     rcx, _GUID_55272a00_42cb_11ce_8135_00aa004bb851; riid
0x180024112  mov     r15d, r8d
0x180024115  call    cs:__imp_PSCreateMemoryPropertyStore
0x18002411b  mov     ebx, eax
0x18002411d  test    eax, eax
0x18002411f  js      loc_1800242E3
0x180024125  mov     r8, [rdi+18h]; value
0x180024129  lea     rdx, aName; "Name"
0x180024130  mov     rcx, [rbp+ppv]; propBag
0x180024134  call    cs:__imp_PSPropertyBag_WriteBSTR
0x18002413a  mov     ebx, eax
0x18002413c  test    eax, eax
0x18002413e  js      loc_1800242D3
0x180024144  mov     r8, [rdi+20h]; value
0x180024148  test    r8, r8
0x18002414b  jz      short loc_180024168
0x18002414d  mov     rcx, [rbp+ppv]; propBag
0x180024151  lea     rdx, aInfolder; "InFolder"
0x180024158  call    cs:__imp_PSPropertyBag_WriteBSTR
0x18002415e  mov     ebx, eax
0x180024160  test    eax, eax
0x180024162  js      loc_1800242D3
0x180024168  mov     rcx, [rbp+ppv]; propBag
0x18002416c  lea     r8, [rdi+28h]; value
0x180024170  lea     rdx, aKey; "Key"
0x180024177  call    cs:__imp_PSPropertyBag_WritePropertyKey
0x18002417d  mov     ebx, eax
0x18002417f  test    eax, eax
0x180024181  js      loc_1800242D3
0x180024187  mov     r8d, [rdi+3Ch]; value
0x18002418b  lea     rdx, aType; "Type"
0x180024192  mov     rcx, [rbp+ppv]; propBag
0x180024196  call    cs:__imp_PSPropertyBag_WriteDWORD
0x18002419c  mov     ebx, eax
0x18002419e  test    eax, eax
0x1800241a0  js      loc_1800242D3
0x1800241a6  xor     edx, edx; cbInit
0x1800241a8  xor     ecx, ecx; pInit
0x1800241aa  call    cs:__imp_SHCreateMemStream
0x1800241b0  mov     rsi, rax
0x1800241b3  test    rax, rax
0x1800241b6  jz      loc_1800242CE
0x1800241bc  mov     r9, [rdi+40h]; struct IUnknown *
0x1800241c0  mov     rcx, rax; pstm
0x1800241c3  call    ?IUnknown_SaveKnownImplToStream@@YAJPEAUIStream@@PEBQEBU_GUID@@IPEAUIUnknown@@@Z; IUnknown_SaveKnownImplToStream(IStream *,_GUID const * const *,uint,IUnknown *)
0x1800241c8  mov     ebx, eax
0x1800241ca  test    eax, eax
0x1800241cc  js      short loc_1800241ED
0x1800241ce  mov     rcx, rsi; pstm
0x1800241d1  call    cs:__imp_IStream_Reset
0x1800241d7  mov     rcx, [rbp+ppv]; propBag
0x1800241db  lea     rdx, aCondition; "Condition"
0x1800241e2  mov     r8, rsi; value
0x1800241e5  call    cs:__imp_PSPropertyBag_WriteStream
0x1800241eb  mov     ebx, eax
0x1800241ed  mov     rax, [rsi]
0x1800241f0  mov     rcx, rsi
0x1800241f3  mov     rax, [rax+10h]
0x1800241f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800241fc  test    ebx, ebx
0x1800241fe  js      loc_1800242D3
0x180024204  mov     rax, [rdi+48h]
0x180024208  test    rax, rax
0x18002420b  jz      loc_1800242B4
0x180024211  mov     eax, [rax]
0x180024213  mov     [rbp+pv], eax
0x180024216  test    eax, eax
0x180024218  jz      loc_1800242BB
0x18002421e  xor     edx, edx; cbInit
0x180024220  xor     ecx, ecx; pInit
0x180024222  call    cs:__imp_SHCreateMemStream
0x180024228  mov     rsi, rax
0x18002422b  test    rax, rax
0x18002422e  jz      loc_1800242CE
0x180024234  mov     r8d, 4; cb
0x18002423a  lea     rdx, [rbp+pv]; pv
0x18002423e  mov     rcx, rax; pstm
0x180024241  call    cs:__imp_IStream_Write
0x180024247  xor     r14d, r14d
0x18002424a  mov     ebx, eax
0x18002424c  cmp     [rbp+pv], r14d
0x180024250  jbe     short loc_18002427C
0x180024252  test    ebx, ebx
0x180024254  js      short loc_18002429F
0x180024256  mov     rcx, [rdi+48h]; hdpa
0x18002425a  mov     edx, r14d; i
0x18002425d  call    cs:g_pfn_DPA_GetPtr
0x180024263  mov     edx, r15d; int
0x180024266  mov     rcx, rsi; struct IStream *
0x180024269  mov     r8, rax; struct IUnknown *
0x18002426c  call    ?IUnknown_SaveToStream@@YAJPEAUIStream@@HPEAUIUnknown@@@Z; IUnknown_SaveToStream(IStream *,int,IUnknown *)
0x180024271  inc     r14d
0x180024274  mov     ebx, eax
0x180024276  cmp     r14d, [rbp+pv]
0x18002427a  jb      short loc_180024252
0x18002427c  test    ebx, ebx
0x18002427e  js      short loc_18002429F
0x180024280  mov     rcx, rsi; pstm
0x180024283  call    cs:__imp_IStream_Reset
0x180024289  mov     rcx, [rbp+ppv]; propBag
0x18002428d  lea     rdx, aFilters; "Filters"
0x180024294  mov     r8, rsi; value
0x180024297  call    cs:__imp_PSPropertyBag_WriteStream
0x18002429d  mov     ebx, eax
0x18002429f  mov     rax, [rsi]
0x1800242a2  mov     rcx, rsi
0x1800242a5  mov     rax, [rax+10h]
0x1800242a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800242ae  test    ebx, ebx
0x1800242b0  jns     short loc_1800242BB
0x1800242b2  jmp     short loc_1800242D3
0x1800242b4  mov     [rbp+pv], 0
0x1800242bb  mov     r8, [rbp+ppv]; struct IUnknown *
0x1800242bf  mov     edx, r15d; int
0x1800242c2  mov     rcx, r12; struct IStream *
0x1800242c5  call    ?IUnknown_SaveToStream@@YAJPEAUIStream@@HPEAUIUnknown@@@Z; IUnknown_SaveToStream(IStream *,int,IUnknown *)
0x1800242ca  mov     ebx, eax
0x1800242cc  jmp     short loc_1800242D3
0x1800242ce  mov     ebx, 8007000Eh
0x1800242d3  mov     rcx, [rbp+ppv]
0x1800242d7  mov     rax, [rcx]
0x1800242da  mov     rax, [rax+10h]
0x1800242de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800242e3  mov     rsi, [rsp+30h+arg_8]
0x1800242e8  mov     eax, ebx
0x1800242ea  mov     rbx, [rsp+30h+arg_0]
0x1800242ef  add     rsp, 30h
0x1800242f3  pop     r15
0x1800242f5  pop     r14
0x1800242f7  pop     r12
0x1800242f9  pop     rdi
0x1800242fa  pop     rbp
0x1800242fb  retn
```
