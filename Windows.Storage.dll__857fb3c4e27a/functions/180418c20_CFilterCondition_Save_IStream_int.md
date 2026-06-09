# CFilterCondition::Save(IStream *,int)

- ea: `0x180418c20`
- end: `0x180418e53`
- name: `?Save@CFilterCondition@@UEAAJPEAUIStream@@H@Z`
- size: `563`
- prototype: `int(CFilterCondition *__hidden this, struct IStream *, int)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180046930`
- `0x18011f47c`
- `0x18011f648`
- `0x1803a4cb0`
- `0x180418c20`
- `0x18065a010`

## import_xrefs

- `PROPSYS!PSPropertyBag_WriteStream` at `0x180418d39`
- `PROPSYS!PSPropertyBag_WriteStream` at `0x180418dea`
- `PROPSYS!PSPropertyBag_WriteStream` at `0x180418d39`
- `PROPSYS!PSPropertyBag_WriteStream` at `0x180418dea`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x180418cdd`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x180418cdd`
- `PROPSYS!PSPropertyBag_WritePropertyKey` at `0x180418cbe`
- `PROPSYS!PSPropertyBag_WritePropertyKey` at `0x180418cbe`
- `PROPSYS!PSPropertyBag_WriteBSTR` at `0x180418c7b`
- `PROPSYS!PSPropertyBag_WriteBSTR` at `0x180418c9f`
- `PROPSYS!PSPropertyBag_WriteBSTR` at `0x180418c7b`
- `PROPSYS!PSPropertyBag_WriteBSTR` at `0x180418c9f`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180418c5c`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180418c5c`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x180418d25`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x180418dd6`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x180418d25`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x180418dd6`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180418d95`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180418d95`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x180418cf1`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x180418d76`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x180418cf1`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x180418d76`

## pseudocode

```c
__int64 __fastcall CFilterCondition::Save(CFilterCondition *this, struct IStream *a2, int a3)
{
  HRESULT v6; // ebx
  OLECHAR *v7; // r8
  struct IStream *v8; // rax
  IStream *v9; // rdi
  unsigned int *v10; // rax
  IStream *v11; // rax
  struct IStream *v12; // rdi
  unsigned int v13; // r14d
  struct IUnknown *Ptr; // rax
  void *ppv; // [rsp+20h] [rbp-20h] BYREF
  unsigned int pv; // [rsp+28h] [rbp-18h] BYREF

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
           (const struct _GUID *const *)&off_1806771E0,
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
              Ptr = (struct IUnknown *)DPA_GetPtr(*((HDPA *)this + 9), v13++);
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
0x180418c20  push    rbp
0x180418c22  push    rbx
0x180418c23  push    rsi
0x180418c24  push    rdi
0x180418c25  push    r12
0x180418c27  push    r14
0x180418c29  push    r15
0x180418c2b  mov     rbp, rsp
0x180418c2e  sub     rsp, 40h
0x180418c32  mov     rax, cs:__security_cookie
0x180418c39  xor     rax, rsp
0x180418c3c  mov     [rbp+var_10], rax
0x180418c40  mov     r12, rdx
0x180418c43  mov     [rbp+ppv], 0
0x180418c4b  mov     rsi, rcx
0x180418c4e  lea     rdx, [rbp+ppv]; ppv
0x180418c52  lea     rcx, _GUID_55272a00_42cb_11ce_8135_00aa004bb851; riid
0x180418c59  mov     r15d, r8d
0x180418c5c  call    cs:__imp_PSCreateMemoryPropertyStore
0x180418c62  mov     ebx, eax
0x180418c64  test    eax, eax
0x180418c66  js      loc_180418E36
0x180418c6c  mov     r8, [rsi+18h]; value
0x180418c70  lea     rdx, aName; "Name"
0x180418c77  mov     rcx, [rbp+ppv]; propBag
0x180418c7b  call    cs:__imp_PSPropertyBag_WriteBSTR
0x180418c81  mov     ebx, eax
0x180418c83  test    eax, eax
0x180418c85  js      loc_180418E26
0x180418c8b  mov     r8, [rsi+20h]; value
0x180418c8f  test    r8, r8
0x180418c92  jz      short loc_180418CAF
0x180418c94  mov     rcx, [rbp+ppv]; propBag
0x180418c98  lea     rdx, aInfolder; "InFolder"
0x180418c9f  call    cs:__imp_PSPropertyBag_WriteBSTR
0x180418ca5  mov     ebx, eax
0x180418ca7  test    eax, eax
0x180418ca9  js      loc_180418E26
0x180418caf  mov     rcx, [rbp+ppv]; propBag
0x180418cb3  lea     r8, [rsi+28h]; value
0x180418cb7  lea     rdx, aKey; "Key"
0x180418cbe  call    cs:__imp_PSPropertyBag_WritePropertyKey
0x180418cc4  mov     ebx, eax
0x180418cc6  test    eax, eax
0x180418cc8  js      loc_180418E26
0x180418cce  mov     r8d, [rsi+3Ch]; value
0x180418cd2  lea     rdx, aType_1; "Type"
0x180418cd9  mov     rcx, [rbp+ppv]; propBag
0x180418cdd  call    cs:__imp_PSPropertyBag_WriteDWORD
0x180418ce3  mov     ebx, eax
0x180418ce5  test    eax, eax
0x180418ce7  js      loc_180418E26
0x180418ced  xor     edx, edx; cbInit
0x180418cef  xor     ecx, ecx; pInit
0x180418cf1  call    cs:__imp_SHCreateMemStream
0x180418cf7  mov     rdi, rax
0x180418cfa  test    rax, rax
0x180418cfd  jz      loc_180418E21
0x180418d03  mov     r9, [rsi+40h]; struct IUnknown *
0x180418d07  lea     rdx, off_1806771E0; struct _GUID **
0x180418d0e  mov     r8d, 3; unsigned int
0x180418d14  mov     rcx, rax; pstm
0x180418d17  call    ?IUnknown_SaveKnownImplToStream@@YAJPEAUIStream@@PEBQEBU_GUID@@IPEAUIUnknown@@@Z; IUnknown_SaveKnownImplToStream(IStream *,_GUID const * const *,uint,IUnknown *)
0x180418d1c  mov     ebx, eax
0x180418d1e  test    eax, eax
0x180418d20  js      short loc_180418D41
0x180418d22  mov     rcx, rdi; pstm
0x180418d25  call    cs:__imp_IStream_Reset
0x180418d2b  mov     rcx, [rbp+ppv]; propBag
0x180418d2f  lea     rdx, aCondition; "Condition"
0x180418d36  mov     r8, rdi; value
0x180418d39  call    cs:__imp_PSPropertyBag_WriteStream
0x180418d3f  mov     ebx, eax
0x180418d41  mov     rax, [rdi]
0x180418d44  mov     rcx, rdi
0x180418d47  mov     rax, [rax+10h]
0x180418d4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180418d50  test    ebx, ebx
0x180418d52  js      loc_180418E26
0x180418d58  mov     rax, [rsi+48h]
0x180418d5c  test    rax, rax
0x180418d5f  jz      loc_180418E07
0x180418d65  mov     eax, [rax]
0x180418d67  mov     [rbp+pv], eax
0x180418d6a  test    eax, eax
0x180418d6c  jz      loc_180418E0E
0x180418d72  xor     edx, edx; cbInit
0x180418d74  xor     ecx, ecx; pInit
0x180418d76  call    cs:__imp_SHCreateMemStream
0x180418d7c  mov     rdi, rax
0x180418d7f  test    rax, rax
0x180418d82  jz      loc_180418E21
0x180418d88  mov     r8d, 4; cb
0x180418d8e  lea     rdx, [rbp+pv]; pv
0x180418d92  mov     rcx, rax; pstm
0x180418d95  call    cs:__imp_IStream_Write
0x180418d9b  xor     r14d, r14d
0x180418d9e  mov     ebx, eax
0x180418da0  cmp     [rbp+pv], r14d
0x180418da4  jbe     short loc_180418DCF
0x180418da6  test    ebx, ebx
0x180418da8  js      short loc_180418DF2
0x180418daa  mov     rcx, [rsi+48h]; hdpa
0x180418dae  mov     edx, r14d; i
0x180418db1  call    DPA_GetPtr
0x180418db6  mov     r8, rax; struct IUnknown *
0x180418db9  mov     edx, r15d; int
0x180418dbc  mov     rcx, rdi; struct IStream *
0x180418dbf  call    ?IUnknown_SaveToStream@@YAJPEAUIStream@@HPEAUIUnknown@@@Z; IUnknown_SaveToStream(IStream *,int,IUnknown *)
0x180418dc4  inc     r14d
0x180418dc7  mov     ebx, eax
0x180418dc9  cmp     r14d, [rbp+pv]
0x180418dcd  jb      short loc_180418DA6
0x180418dcf  test    ebx, ebx
0x180418dd1  js      short loc_180418DF2
0x180418dd3  mov     rcx, rdi; pstm
0x180418dd6  call    cs:__imp_IStream_Reset
0x180418ddc  mov     rcx, [rbp+ppv]; propBag
0x180418de0  lea     rdx, aFilters; "Filters"
0x180418de7  mov     r8, rdi; value
0x180418dea  call    cs:__imp_PSPropertyBag_WriteStream
0x180418df0  mov     ebx, eax
0x180418df2  mov     rax, [rdi]
0x180418df5  mov     rcx, rdi
0x180418df8  mov     rax, [rax+10h]
0x180418dfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180418e01  test    ebx, ebx
0x180418e03  jns     short loc_180418E0E
0x180418e05  jmp     short loc_180418E26
0x180418e07  mov     [rbp+pv], 0
0x180418e0e  mov     r8, [rbp+ppv]; struct IUnknown *
0x180418e12  mov     edx, r15d; int
0x180418e15  mov     rcx, r12; struct IStream *
0x180418e18  call    ?IUnknown_SaveToStream@@YAJPEAUIStream@@HPEAUIUnknown@@@Z; IUnknown_SaveToStream(IStream *,int,IUnknown *)
0x180418e1d  mov     ebx, eax
0x180418e1f  jmp     short loc_180418E26
0x180418e21  mov     ebx, 8007000Eh
0x180418e26  mov     rcx, [rbp+ppv]
0x180418e2a  mov     rax, [rcx]
0x180418e2d  mov     rax, [rax+10h]
0x180418e31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180418e36  mov     eax, ebx
0x180418e38  mov     rcx, [rbp+var_10]
0x180418e3c  xor     rcx, rsp; StackCookie
0x180418e3f  call    __security_check_cookie
0x180418e44  add     rsp, 40h
0x180418e48  pop     r15
0x180418e4a  pop     r14
0x180418e4c  pop     r12
0x180418e4e  pop     rdi
0x180418e4f  pop     rsi
0x180418e50  pop     rbx
0x180418e51  pop     rbp
0x180418e52  retn
```
