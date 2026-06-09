# ATL::CComEnumImpl<IEnumVARIANT,&_GUID const IID_IEnumVARIANT,tagVARIANT,ATL::_Copy<tagVARIANT>>::Init(tagVARIANT *,tagVARIANT *,IUnknown *,ATL::CComEnumFlags)

- ea: `0x180073598`
- end: `0x1800736fd`
- name: `?Init@?$CComEnumImpl@UIEnumVARIANT@@$1?IID_IEnumVARIANT@@3U_GUID@@BUtagVARIANT@@V?$_Copy@UtagVARIANT@@@ATL@@@ATL@@QEAAJPEAUtagVARIANT@@0PEAUIUnknown@@W4CComEnumFlags@2@@Z`
- size: `357`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18003f160`
- `0x180072f80`

## callees

- `0x18001fa70`
- `0x180073598`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x180073694`
- `OLEAUT32!__imp_VariantClear` at `0x180073694`
- `OLEAUT32!__imp_VariantCopy` at `0x18007366b`
- `OLEAUT32!__imp_VariantCopy` at `0x18007366b`
- `PhotoBase!?Delete@BasePrivate@@YAXPEAX@Z` at `0x1800736a4`
- `PhotoBase!?Delete@BasePrivate@@YAXPEAX@Z` at `0x1800736a4`
- `PhotoBase!?New@BasePrivate@@YAPEAX_K_N@Z` at `0x18007360d`
- `PhotoBase!?New@BasePrivate@@YAPEAX_K_N@Z` at `0x18007360d`

## pseudocode

```c
__int64 __fastcall ATL::CComEnumImpl<IEnumVARIANT,&_GUID const IID_IEnumVARIANT,tagVARIANT,ATL::_Copy<tagVARIANT>>::Init(
        __int64 a1,
        const VARIANTARG *a2,
        _BOOL8 a3,
        __int64 a4,
        int a5)
{
  __int64 v5; // r15
  __int64 v6; // rsi
  const VARIANTARG *v7; // rdi
  __int64 v8; // rbx
  int v9; // r12d
  unsigned __int64 v10; // r14
  unsigned __int128 v11; // rax
  _WORD *v12; // rcx
  VARIANTARG *v14; // rcx
  void *v15; // rdx
  HRESULT v16; // r13d
  VARIANTARG *i; // rdi
  VARIANTARG *v18; // rcx

  v5 = a4;
  v6 = a3;
  v7 = a2;
  v8 = a1;
  v9 = a5;
  if ( a5 == 3 )
  {
    v10 = 0xAAAAAAAAAAAAAAABuLL * ((a3 - (__int64)a2) >> 3);
    v11 = v10 * (unsigned __int128)0x18u;
    if ( !is_mul_ok(v10, 0x18u) )
      *(_QWORD *)&v11 = -1;
    try
    {
      BYTE8(v11) = 1;
      *(_QWORD *)(a1 + 16) = BasePrivate::New((BasePrivate *)v11, *((unsigned __int64 *)&v11 + 1), a3);
    }
    catch ( ... )
    {
      v8 = a1;
      v9 = 3;
      v5 = a4;
      v6 = a3;
      v7 = a2;
    }
    v12 = *(_WORD **)(v8 + 16);
    *(_QWORD *)(v8 + 32) = v12;
    if ( v12 )
    {
      while ( 1 )
      {
        if ( v7 == (const VARIANTARG *)v6 )
        {
          v6 = *(_QWORD *)(v8 + 16) + 24 * v10;
          goto LABEL_15;
        }
        *v12 = 0;
        v14 = *(VARIANTARG **)(v8 + 32);
        v14->vt = 0;
        v16 = VariantCopy(v14, v7);
        if ( v16 < 0 )
          break;
        *(_QWORD *)(v8 + 32) += 24LL;
        v12 = *(_WORD **)(v8 + 32);
        ++v7;
      }
      for ( i = *(VARIANTARG **)(v8 + 16); (unsigned __int64)i < *(_QWORD *)(v8 + 32); ++i )
      {
        v18 = i;
        VariantClear(v18);
      }
      BasePrivate::Delete(*(BasePrivate **)(v8 + 16), v15);
      *(_QWORD *)(v8 + 32) = 0;
      *(_QWORD *)(v8 + 24) = 0;
      *(_QWORD *)(v8 + 16) = 0;
      return (unsigned int)v16;
    }
    else
    {
      return 2147942414LL;
    }
  }
  else
  {
    *(_QWORD *)(a1 + 16) = a2;
LABEL_15:
    *(_QWORD *)(v8 + 24) = v6;
    ATL::CComPtr<IUnknown>::operator=(v8 + 8, v5);
    *(_QWORD *)(v8 + 32) = *(_QWORD *)(v8 + 16);
    *(_DWORD *)(v8 + 40) = v9;
    return 0;
  }
}

```

## disassembly

```asm
0x180073598  mov     rax, rsp
0x18007359b  mov     [rax+20h], r9
0x18007359f  mov     [rax+18h], r8
0x1800735a3  mov     [rax+10h], rdx
0x1800735a7  mov     [rax+8], rcx
0x1800735ab  push    rbx
0x1800735ac  push    rsi
0x1800735ad  push    rdi
0x1800735ae  push    r12
0x1800735b0  push    r13
0x1800735b2  push    r14
0x1800735b4  push    r15
0x1800735b6  sub     rsp, 30h
0x1800735ba  mov     r15, r9
0x1800735bd  mov     rsi, r8
0x1800735c0  mov     rdi, rdx
0x1800735c3  mov     rbx, rcx
0x1800735c6  mov     r12d, [rsp+68h+arg_20]
0x1800735ce  cmp     r12d, 3
0x1800735d2  jnz     loc_1800736CB
0x1800735d8  mov     r14, r8
0x1800735db  sub     r14, rdx
0x1800735de  sar     r14, 3
0x1800735e2  mov     rax, 0AAAAAAAAAAAAAAABh
0x1800735ec  imul    r14, rax
0x1800735f0  mov     [rsp+68h+var_48], r14
0x1800735f5  lea     eax, [r12+15h]
0x1800735fa  mul     r14
0x1800735fd  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180073604  cmovb   rax, rcx
0x180073608  mov     dl, 1
0x18007360a  mov     rcx, rax
0x18007360d  call    cs:__imp_?New@BasePrivate@@YAPEAX_K_N@Z; BasePrivate::New(unsigned __int64,bool)
0x180073613  mov     [rbx+10h], rax
0x180073617  jmp     short loc_180073640
0x180073619  mov     rbx, [rsp+68h+arg_0]
0x18007361e  mov     r12d, [rsp+68h+arg_20]
0x180073626  mov     r15, [rsp+68h+arg_18]
0x18007362e  mov     rsi, [rsp+68h+arg_10]
0x180073636  mov     rdi, [rsp+68h+arg_8]
0x18007363b  mov     r14, [rsp+68h+var_48]
0x180073640  mov     rcx, [rbx+10h]
0x180073644  mov     [rbx+20h], rcx
0x180073648  test    rcx, rcx
0x18007364b  jnz     short loc_180073657
0x18007364d  mov     eax, 8007000Eh
0x180073652  jmp     loc_1800736ED
0x180073657  cmp     rdi, rsi
0x18007365a  jz      short loc_1800736BD
0x18007365c  xor     eax, eax
0x18007365e  mov     [rcx], ax
0x180073661  mov     rcx, [rbx+20h]; pvargDest
0x180073665  mov     [rcx], ax
0x180073668  mov     rdx, rdi; pvargSrc
0x18007366b  call    cs:__imp_VariantCopy
0x180073671  mov     r13d, eax
0x180073674  test    eax, eax
0x180073676  js      short loc_180073687
0x180073678  add     qword ptr [rbx+20h], 18h
0x18007367d  mov     rcx, [rbx+20h]
0x180073681  add     rdi, 18h
0x180073685  jmp     short loc_180073657
0x180073687  mov     rdi, [rbx+10h]
0x18007368b  jmp     short loc_18007369A
0x18007368d  mov     rcx, rdi; pvarg
0x180073690  add     rdi, 18h
0x180073694  call    cs:__imp_VariantClear
0x18007369a  cmp     rdi, [rbx+20h]
0x18007369e  jb      short loc_18007368D
0x1800736a0  mov     rcx, [rbx+10h]
0x1800736a4  call    cs:__imp_?Delete@BasePrivate@@YAXPEAX@Z; BasePrivate::Delete(void *)
0x1800736aa  xor     eax, eax
0x1800736ac  mov     [rbx+20h], rax
0x1800736b0  mov     [rbx+18h], rax
0x1800736b4  mov     [rbx+10h], rax
0x1800736b8  mov     eax, r13d
0x1800736bb  jmp     short loc_1800736ED
0x1800736bd  lea     rcx, [r14+r14*2]
0x1800736c1  mov     rax, [rbx+10h]
0x1800736c5  lea     rsi, [rax+rcx*8]
0x1800736c9  jmp     short loc_1800736CF
0x1800736cb  mov     [rcx+10h], rdx
0x1800736cf  mov     [rbx+18h], rsi
0x1800736d3  lea     rcx, [rbx+8]
0x1800736d7  mov     rdx, r15
0x1800736da  call    ??4?$CComPtr@UIUnknown@@@ATL@@QEAAPEAUIUnknown@@PEAU2@@Z; ATL::CComPtr<IUnknown>::operator=(IUnknown *)
0x1800736df  mov     rax, [rbx+10h]
0x1800736e3  mov     [rbx+20h], rax
0x1800736e7  mov     [rbx+28h], r12d
0x1800736eb  xor     eax, eax
0x1800736ed  add     rsp, 30h
0x1800736f1  pop     r15
0x1800736f3  pop     r14
0x1800736f5  pop     r13
0x1800736f7  pop     r12
0x1800736f9  pop     rdi
0x1800736fa  pop     rsi
0x1800736fb  pop     rbx
0x1800736fc  retn
```
