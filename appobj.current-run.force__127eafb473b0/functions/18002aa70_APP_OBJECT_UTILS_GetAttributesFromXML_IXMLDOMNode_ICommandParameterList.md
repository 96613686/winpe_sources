# APP_OBJECT_UTILS::GetAttributesFromXML(IXMLDOMNode *,ICommandParameterList * *)

- ea: `0x18002aa70`
- end: `0x18002ac92`
- name: `?GetAttributesFromXML@APP_OBJECT_UTILS@@QEAAJPEAUIXMLDOMNode@@PEAPEAVICommandParameterList@@@Z`
- size: `546`
- prototype: `__int64 __fastcall(APP_OBJECT_UTILS *__hidden this, struct IXMLDOMNode *, struct ICommandParameterList **)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000774c`
- `0x180026aec`

## callees

- `0x180001044`
- `0x18002aa70`
- `0x180036010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18002ac68`
- `OLEAUT32!__imp_SysFreeString` at `0x18002ac68`
- `OLEAUT32!__imp_VariantInit` at `0x18002aab2`
- `OLEAUT32!__imp_VariantInit` at `0x18002ab4a`
- `OLEAUT32!__imp_VariantInit` at `0x18002aab2`
- `OLEAUT32!__imp_VariantInit` at `0x18002ab4a`
- `OLEAUT32!__imp_VariantClear` at `0x18002abe4`
- `OLEAUT32!__imp_VariantClear` at `0x18002ac76`
- `OLEAUT32!__imp_VariantClear` at `0x18002abe4`
- `OLEAUT32!__imp_VariantClear` at `0x18002ac76`

## pseudocode

```c
__int64 __fastcall APP_OBJECT_UTILS::GetAttributesFromXML(
        APP_OBJECT_UTILS *this,
        struct IXMLDOMNode *a2,
        struct ICommandParameterList **a3)
{
  struct ICommandParameterList *v5; // rax
  struct ICommandParameterList *v6; // rbx
  HRESULT v7; // edi
  unsigned int i; // esi
  BSTR bstrString; // [rsp+20h] [rbp-20h] BYREF
  VARIANTARG pvarg; // [rsp+28h] [rbp-18h] BYREF
  int v12; // [rsp+70h] [rbp+30h] BYREF
  int v13; // [rsp+74h] [rbp+34h]
  __int64 v14; // [rsp+78h] [rbp+38h] BYREF
  __int64 v15; // [rsp+88h] [rbp+48h] BYREF

  v13 = HIDWORD(this);
  v15 = 0;
  v14 = 0;
  v12 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  bstrString = 0;
  VariantInit(&pvarg);
  if ( !a2 || !a3 )
  {
    v7 = -2147024809;
    goto LABEL_20;
  }
  v5 = (struct ICommandParameterList *)operator new(0x28u);
  v6 = v5;
  if ( !v5 )
  {
    v7 = -2147024888;
LABEL_20:
    v6 = 0;
    goto LABEL_21;
  }
  *((_DWORD *)v5 + 2) = 1;
  *(_QWORD *)v5 = &PARAMETER_LIST::`vftable';
  *((_QWORD *)v5 + 2) = 0;
  *((_QWORD *)v5 + 3) = 0;
  *((_DWORD *)v5 + 8) = 0;
  v7 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, __int64 *))a2->lpVtbl->get_attributes)(a2, &v15);
  if ( v7 >= 0 )
  {
    v7 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v15 + 88LL))(v15, &v12);
    if ( v7 >= 0 )
    {
      for ( i = 0; (int)i < v12; ++i )
      {
        VariantInit(&pvarg);
        v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v15 + 80LL))(v15, i, &v14);
        if ( v7 < 0 )
          goto LABEL_21;
        v7 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v14 + 56LL))(v14, &bstrString);
        if ( v7 < 0 )
          goto LABEL_21;
        v7 = (*(__int64 (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)v14 + 64LL))(v14, &pvarg);
        if ( v7 < 0 )
          goto LABEL_21;
        if ( pvarg.vt != 8 )
        {
          v7 = -2147024883;
          goto LABEL_21;
        }
        v7 = (*(__int64 (__fastcall **)(struct ICommandParameterList *, BSTR, LONGLONG))(*(_QWORD *)v6 + 56LL))(
               v6,
               bstrString,
               pvarg.llVal);
        if ( v7 < 0 )
          goto LABEL_21;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
        v14 = 0;
        v7 = VariantClear(&pvarg);
        if ( v7 < 0 )
        {
          pvarg.vt = 0;
          goto LABEL_21;
        }
      }
      *a3 = v6;
      goto LABEL_20;
    }
  }
LABEL_21:
  if ( v15 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    v15 = 0;
  }
  if ( v14 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    v14 = 0;
  }
  if ( v6 )
    (*(void (__fastcall **)(struct ICommandParameterList *))(*(_QWORD *)v6 + 16LL))(v6);
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  VariantClear(&pvarg);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18002aa70  mov     [rsp-28h+arg_10], rbx
0x18002aa75  mov     [rsp-28h+arg_0], rcx
0x18002aa7a  push    rbp
0x18002aa7b  push    rsi
0x18002aa7c  push    rdi
0x18002aa7d  push    r14
0x18002aa7f  push    r15
0x18002aa81  mov     rbp, rsp
0x18002aa84  sub     rsp, 40h
0x18002aa88  xor     r15d, r15d
0x18002aa8b  lea     rcx, [rbp+pvarg]; pvarg
0x18002aa8f  xorps   xmm0, xmm0
0x18002aa92  mov     [rbp+arg_18], r15
0x18002aa96  xor     eax, eax
0x18002aa98  mov     [rbp+arg_8], r15
0x18002aa9c  mov     dword ptr [rbp+arg_0], r15d
0x18002aaa0  mov     r14, r8
0x18002aaa3  movups  xmmword ptr [rbp+pvarg], xmm0
0x18002aaa7  mov     qword ptr [rbp+pvarg+10h], rax
0x18002aaab  mov     rdi, rdx
0x18002aaae  mov     [rbp+bstrString], r15
0x18002aab2  call    cs:__imp_VariantInit
0x18002aab8  test    rdi, rdi
0x18002aabb  jz      loc_18002AC11
0x18002aac1  test    r14, r14
0x18002aac4  jz      loc_18002AC11
0x18002aaca  lea     ecx, [r15+28h]; Size
0x18002aace  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002aad3  mov     rbx, rax
0x18002aad6  test    rax, rax
0x18002aad9  jz      loc_18002AC0A
0x18002aadf  mov     dword ptr [rbx+8], 1
0x18002aae6  lea     rax, ??_7PARAMETER_LIST@@6B@; const PARAMETER_LIST::`vftable'
0x18002aaed  mov     [rbx], rax
0x18002aaf0  lea     rdx, [rbp+arg_18]
0x18002aaf4  mov     [rbx+10h], r15
0x18002aaf8  mov     rcx, rdi
0x18002aafb  mov     [rbx+18h], r15
0x18002aaff  mov     [rbx+20h], r15d
0x18002ab03  mov     rax, [rdi]
0x18002ab06  mov     rax, [rax+88h]
0x18002ab0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ab12  mov     edi, eax
0x18002ab14  test    eax, eax
0x18002ab16  js      loc_18002AC19
0x18002ab1c  mov     rcx, [rbp+arg_18]
0x18002ab20  lea     rdx, [rbp+arg_0]
0x18002ab24  mov     rax, [rcx]
0x18002ab27  mov     rax, [rax+58h]
0x18002ab2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ab30  mov     edi, eax
0x18002ab32  test    eax, eax
0x18002ab34  js      loc_18002AC19
0x18002ab3a  mov     esi, r15d
0x18002ab3d  cmp     esi, dword ptr [rbp+arg_0]
0x18002ab40  jge     loc_18002AC05
0x18002ab46  lea     rcx, [rbp+pvarg]; pvarg
0x18002ab4a  call    cs:__imp_VariantInit
0x18002ab50  mov     rcx, [rbp+arg_18]
0x18002ab54  lea     r8, [rbp+arg_8]
0x18002ab58  mov     edx, esi
0x18002ab5a  mov     rax, [rcx]
0x18002ab5d  mov     rax, [rax+50h]
0x18002ab61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ab66  mov     edi, eax
0x18002ab68  test    eax, eax
0x18002ab6a  js      loc_18002AC19
0x18002ab70  mov     rcx, [rbp+arg_8]
0x18002ab74  lea     rdx, [rbp+bstrString]
0x18002ab78  mov     rax, [rcx]
0x18002ab7b  mov     rax, [rax+38h]
0x18002ab7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ab84  mov     edi, eax
0x18002ab86  test    eax, eax
0x18002ab88  js      loc_18002AC19
0x18002ab8e  mov     rcx, [rbp+arg_8]
0x18002ab92  lea     rdx, [rbp+pvarg]
0x18002ab96  mov     rax, [rcx]
0x18002ab99  mov     rax, [rax+40h]
0x18002ab9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aba2  mov     edi, eax
0x18002aba4  test    eax, eax
0x18002aba6  js      short loc_18002AC19
0x18002aba8  cmp     word ptr [rbp+pvarg], 8
0x18002abad  jnz     short loc_18002ABFE
0x18002abaf  mov     rax, [rbx]
0x18002abb2  mov     rcx, rbx
0x18002abb5  mov     r8, qword ptr [rbp+pvarg+8]
0x18002abb9  mov     rdx, [rbp+bstrString]
0x18002abbd  mov     rax, [rax+38h]
0x18002abc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002abc6  mov     edi, eax
0x18002abc8  test    eax, eax
0x18002abca  js      short loc_18002AC19
0x18002abcc  mov     rcx, [rbp+arg_8]
0x18002abd0  mov     rax, [rcx]
0x18002abd3  mov     rax, [rax+10h]
0x18002abd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002abdc  lea     rcx, [rbp+pvarg]; pvarg
0x18002abe0  mov     [rbp+arg_8], r15
0x18002abe4  call    cs:__imp_VariantClear
0x18002abea  mov     edi, eax
0x18002abec  test    eax, eax
0x18002abee  js      short loc_18002ABF7
0x18002abf0  inc     esi
0x18002abf2  jmp     loc_18002AB3D
0x18002abf7  mov     word ptr [rbp+pvarg], r15w
0x18002abfc  jmp     short loc_18002AC19
0x18002abfe  mov     edi, 8007000Dh
0x18002ac03  jmp     short loc_18002AC19
0x18002ac05  mov     [r14], rbx
0x18002ac08  jmp     short loc_18002AC16
0x18002ac0a  mov     edi, 80070008h
0x18002ac0f  jmp     short loc_18002AC16
0x18002ac11  mov     edi, 80070057h
0x18002ac16  mov     rbx, r15
0x18002ac19  mov     rcx, [rbp+arg_18]
0x18002ac1d  test    rcx, rcx
0x18002ac20  jz      short loc_18002AC32
0x18002ac22  mov     rax, [rcx]
0x18002ac25  mov     rax, [rax+10h]
0x18002ac29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ac2e  mov     [rbp+arg_18], r15
0x18002ac32  mov     rcx, [rbp+arg_8]
0x18002ac36  test    rcx, rcx
0x18002ac39  jz      short loc_18002AC4B
0x18002ac3b  mov     rax, [rcx]
0x18002ac3e  mov     rax, [rax+10h]
0x18002ac42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ac47  mov     [rbp+arg_8], r15
0x18002ac4b  test    rbx, rbx
0x18002ac4e  jz      short loc_18002AC5F
0x18002ac50  mov     rax, [rbx]
0x18002ac53  mov     rcx, rbx
0x18002ac56  mov     rax, [rax+10h]
0x18002ac5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ac5f  mov     rcx, [rbp+bstrString]; bstrString
0x18002ac63  test    rcx, rcx
0x18002ac66  jz      short loc_18002AC72
0x18002ac68  call    cs:__imp_SysFreeString
0x18002ac6e  mov     [rbp+bstrString], r15
0x18002ac72  lea     rcx, [rbp+pvarg]; pvarg
0x18002ac76  call    cs:__imp_VariantClear
0x18002ac7c  mov     rbx, [rsp+40h+arg_10]
0x18002ac84  mov     eax, edi
0x18002ac86  add     rsp, 40h
0x18002ac8a  pop     r15
0x18002ac8c  pop     r14
0x18002ac8e  pop     rdi
0x18002ac8f  pop     rsi
0x18002ac90  pop     rbp
0x18002ac91  retn
```
