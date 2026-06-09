# TRACE_OBJECT_EXTENSION::CreateFrebLogObject(IExtensionContext *,ushort const *,ushort const *,TRACE_OBJECT * *)

- ea: `0x180026f78`
- end: `0x18002717b`
- name: `?CreateFrebLogObject@TRACE_OBJECT_EXTENSION@@AEAAJPEAVIExtensionContext@@PEBG1PEAPEAVTRACE_OBJECT@@@Z`
- size: `515`
- prototype: `int(TRACE_OBJECT_EXTENSION *__hidden this, struct IExtensionContext *, const unsigned __int16 *, const unsigned __int16 *, struct TRACE_OBJECT **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180027190`

## callees

- `0x180001044`
- `0x180005440`
- `0x180026aec`
- `0x180026f78`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180027008`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180027008`
- `OLEAUT32!__imp_SysAllocString` at `0x180027025`
- `OLEAUT32!__imp_SysAllocString` at `0x180027025`
- `OLEAUT32!__imp_VariantInit` at `0x180026fbd`
- `OLEAUT32!__imp_VariantInit` at `0x180026fbd`
- `OLEAUT32!__imp_VariantClear` at `0x180027132`
- `OLEAUT32!__imp_VariantClear` at `0x180027132`

## pseudocode

```c
__int64 __fastcall TRACE_OBJECT_EXTENSION::CreateFrebLogObject(
        TRACE_OBJECT_EXTENSION *this,
        struct IExtensionContext *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        struct TRACE_OBJECT **a5)
{
  COMMAND_OBJECT *v5; // rdi
  struct TRACE_OBJECT **v9; // r14
  HRESULT Instance; // ebx
  BSTR v11; // rax
  struct IXMLDOMDocumentVtbl *lpVtbl; // rax
  COMMAND_OBJECT *v13; // rax
  __int64 v14; // rax
  VARIANTARG pvarg; // [rsp+30h] [rbp-40h] BYREF
  VARIANTARG v17; // [rsp+50h] [rbp-20h] BYREF
  TRACE_OBJECT_EXTENSION *v18; // [rsp+B0h] [rbp+40h] BYREF
  struct IXMLDOMDocument *ppv; // [rsp+B8h] [rbp+48h] BYREF

  v18 = this;
  ppv = 0;
  LOWORD(v18) = 0;
  v5 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  if ( !a2 || !a3 || !a4 || (v9 = a5) == 0 )
  {
    Instance = -2147024809;
    goto LABEL_18;
  }
  Instance = CoCreateInstance(&CLSID_DOMDocument60, 0, 1u, &IID_IXMLDOMDocument, (LPVOID *)&ppv);
  if ( Instance < 0 )
    goto LABEL_18;
  if ( !ppv )
    goto LABEL_16;
  v11 = SysAllocString(a4);
  if ( !v11 )
  {
    Instance = -2147024888;
    goto LABEL_18;
  }
  pvarg.llVal = (LONGLONG)v11;
  pvarg.vt = 8;
  Instance = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, _QWORD))ppv->lpVtbl->put_async)(ppv, 0);
  if ( Instance >= 0 )
  {
    lpVtbl = ppv->lpVtbl;
    v17 = pvarg;
    Instance = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, VARIANTARG *, TRACE_OBJECT_EXTENSION **))lpVtbl->load)(
                 ppv,
                 &v17,
                 &v18);
    if ( Instance >= 0 )
    {
      if ( (_WORD)v18 )
      {
        v13 = (COMMAND_OBJECT *)operator new(0xF8u);
        v5 = v13;
        if ( v13 )
        {
          COMMAND_OBJECT::COMMAND_OBJECT(v13);
          *((_DWORD *)v5 + 54) = 0;
          *(_QWORD *)v5 = &TRACE_OBJECT::`vftable';
          *((_QWORD *)v5 + 28) = 0;
          *((_QWORD *)v5 + 29) = 0;
          *((_QWORD *)v5 + 30) = 0;
          Instance = TRACE_OBJECT::Create(v5, a2, a4, a3, ppv);
          if ( Instance >= 0 )
          {
            v14 = *(_QWORD *)v5;
            *v9 = v5;
            (*(void (__fastcall **)(COMMAND_OBJECT *))(v14 + 8))(v5);
          }
        }
        else
        {
          Instance = -2147024888;
          v5 = 0;
        }
        goto LABEL_18;
      }
LABEL_16:
      Instance = -2147467259;
    }
  }
LABEL_18:
  VariantClear(&pvarg);
  if ( v5 )
    (*(void (__fastcall **)(COMMAND_OBJECT *))(*(_QWORD *)v5 + 16LL))(v5);
  if ( ppv )
    ((void (__fastcall *)(struct IXMLDOMDocument *))ppv->lpVtbl->Release)(ppv);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180026f78  mov     [rsp-38h+arg_10], rbx
0x180026f7d  mov     [rsp-38h+arg_0], rcx
0x180026f82  push    rbp
0x180026f83  push    rsi
0x180026f84  push    rdi
0x180026f85  push    r12
0x180026f87  push    r13
0x180026f89  push    r14
0x180026f8b  push    r15
0x180026f8d  mov     rbp, rsp
0x180026f90  sub     rsp, 70h
0x180026f94  xor     r13d, r13d
0x180026f97  lea     rcx, [rbp+pvarg]; pvarg
0x180026f9b  xorps   xmm0, xmm0
0x180026f9e  mov     [rbp+arg_8], r13
0x180026fa2  xor     eax, eax
0x180026fa4  mov     word ptr [rbp+arg_0], r13w
0x180026fa9  mov     edi, r13d
0x180026fac  mov     qword ptr [rbp+pvarg+10h], rax
0x180026fb0  movups  xmmword ptr [rbp+pvarg], xmm0
0x180026fb4  mov     rsi, r9
0x180026fb7  mov     r15, r8
0x180026fba  mov     r12, rdx
0x180026fbd  call    cs:__imp_VariantInit
0x180026fc3  test    r12, r12
0x180026fc6  jz      loc_180027129
0x180026fcc  test    r15, r15
0x180026fcf  jz      loc_180027129
0x180026fd5  test    rsi, rsi
0x180026fd8  jz      loc_180027129
0x180026fde  mov     r14, [rbp+arg_20]
0x180026fe2  test    r14, r14
0x180026fe5  jz      loc_180027129
0x180026feb  lea     rax, [rbp+arg_8]
0x180026fef  xor     edx, edx; pUnkOuter
0x180026ff1  lea     r9, IID_IXMLDOMDocument; riid
0x180026ff8  mov     [rsp+70h+ppv], rax; ppv
0x180026ffd  lea     r8d, [r13+1]; dwClsContext
0x180027001  lea     rcx, CLSID_DOMDocument60; rclsid
0x180027008  call    cs:__imp_CoCreateInstance
0x18002700e  mov     ebx, eax
0x180027010  test    eax, eax
0x180027012  js      loc_18002712E
0x180027018  cmp     [rbp+arg_8], r13
0x18002701c  jz      loc_180027122
0x180027022  mov     rcx, rsi; psz
0x180027025  call    cs:__imp_SysAllocString
0x18002702b  test    rax, rax
0x18002702e  jnz     short loc_18002703A
0x180027030  mov     ebx, 80070008h
0x180027035  jmp     loc_18002712E
0x18002703a  mov     qword ptr [rbp+pvarg+8], rax
0x18002703e  mov     ecx, 8
0x180027043  mov     word ptr [rbp+pvarg], cx
0x180027047  xor     edx, edx
0x180027049  mov     rcx, [rbp+arg_8]
0x18002704d  mov     rax, [rcx]
0x180027050  mov     rax, [rax+1F8h]
0x180027057  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002705c  mov     ebx, eax
0x18002705e  test    eax, eax
0x180027060  js      loc_18002712E
0x180027066  mov     rcx, [rbp+arg_8]
0x18002706a  lea     r8, [rbp+arg_0]
0x18002706e  movups  xmm0, xmmword ptr [rbp+pvarg]
0x180027072  lea     rdx, [rbp+var_20]
0x180027076  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x18002707b  mov     rax, [rcx]
0x18002707e  movaps  [rbp+var_20], xmm0
0x180027082  movsd   [rbp+var_10], xmm1
0x180027087  mov     rax, [rax+1D0h]
0x18002708e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027093  mov     ebx, eax
0x180027095  test    eax, eax
0x180027097  js      loc_18002712E
0x18002709d  cmp     word ptr [rbp+arg_0], r13w
0x1800270a2  jz      short loc_180027122
0x1800270a4  mov     ecx, 0F8h; Size
0x1800270a9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800270ae  mov     rdi, rax
0x1800270b1  test    rax, rax
0x1800270b4  jz      short loc_180027118
0x1800270b6  mov     rcx, rax; this
0x1800270b9  call    ??0COMMAND_OBJECT@@QEAA@XZ; COMMAND_OBJECT::COMMAND_OBJECT(void)
0x1800270be  mov     [rdi+0D8h], r13d
0x1800270c5  lea     rcx, ??_7TRACE_OBJECT@@6B@; const TRACE_OBJECT::`vftable'
0x1800270cc  mov     [rdi], rcx
0x1800270cf  mov     r9, r15; unsigned __int16 *
0x1800270d2  mov     [rdi+0E0h], r13
0x1800270d9  mov     r8, rsi; unsigned __int16 *
0x1800270dc  mov     [rdi+0E8h], r13
0x1800270e3  mov     rdx, r12; struct IExtensionContext *
0x1800270e6  mov     [rdi+0F0h], r13
0x1800270ed  mov     rcx, rdi; this
0x1800270f0  mov     rax, [rbp+arg_8]
0x1800270f4  mov     [rsp+70h+ppv], rax; struct IXMLDOMDocument *
0x1800270f9  call    ?Create@TRACE_OBJECT@@QEAAJPEAVIExtensionContext@@PEBG1PEAUIXMLDOMDocument@@@Z; TRACE_OBJECT::Create(IExtensionContext *,ushort const *,ushort const *,IXMLDOMDocument *)
0x1800270fe  mov     ebx, eax
0x180027100  test    eax, eax
0x180027102  js      short loc_18002712E
0x180027104  mov     rax, [rdi]
0x180027107  mov     rcx, rdi
0x18002710a  mov     [r14], rdi
0x18002710d  mov     rax, [rax+8]
0x180027111  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027116  jmp     short loc_18002712E
0x180027118  mov     ebx, 80070008h
0x18002711d  mov     rdi, r13
0x180027120  jmp     short loc_18002712E
0x180027122  mov     ebx, 80004005h
0x180027127  jmp     short loc_18002712E
0x180027129  mov     ebx, 80070057h
0x18002712e  lea     rcx, [rbp+pvarg]; pvarg
0x180027132  call    cs:__imp_VariantClear
0x180027138  test    rdi, rdi
0x18002713b  jz      short loc_18002714C
0x18002713d  mov     rax, [rdi]
0x180027140  mov     rcx, rdi
0x180027143  mov     rax, [rax+10h]
0x180027147  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002714c  mov     rcx, [rbp+arg_8]
0x180027150  test    rcx, rcx
0x180027153  jz      short loc_180027161
0x180027155  mov     rax, [rcx]
0x180027158  mov     rax, [rax+10h]
0x18002715c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027161  mov     eax, ebx
0x180027163  mov     rbx, [rsp+70h+arg_10]
0x18002716b  add     rsp, 70h
0x18002716f  pop     r15
0x180027171  pop     r14
0x180027173  pop     r13
0x180027175  pop     r12
0x180027177  pop     rdi
0x180027178  pop     rsi
0x180027179  pop     rbp
0x18002717a  retn
```
