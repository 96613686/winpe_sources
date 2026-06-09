# XcLoadFrom(IXMLDOMDocument2 *,ushort const *,int *)

- ea: `0x180013280`
- end: `0x18001332d`
- name: `?XcLoadFrom@@YAKPEAUIXMLDOMDocument2@@PEBGPEAH@Z`
- size: `173`
- prototype: `__int64 __fastcall(struct IXMLDOMDocument2 *, OLECHAR *, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000b5a0`

## callees

- `0x180011eb8`
- `0x180013280`
- `0x180014010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180013299`
- `OLEAUT32!__imp_VariantInit` at `0x180013299`
- `OLEAUT32!__imp_VariantClear` at `0x18001331c`
- `OLEAUT32!__imp_VariantClear` at `0x18001331c`

## pseudocode

```c
__int64 __fastcall XcLoadFrom(struct IXMLDOMDocument2 *a1, OLECHAR *a2, int *a3)
{
  unsigned int v6; // ebx
  HRESULT (__stdcall *load)(IXMLDOMDocument2 *, VARIANT, VARIANT_BOOL *); // rax
  int v8; // eax
  VARIANTARG pvarg; // [rsp+20h] [rbp-48h] BYREF
  VARIANTARG v11; // [rsp+40h] [rbp-28h] BYREF
  __int16 v12; // [rsp+A8h] [rbp+40h] BYREF

  VariantInit(&pvarg);
  v12 = 0;
  AtlAssignNoThrow(&pvarg, a2);
  v6 = 8;
  if ( pvarg.vt == 8 && pvarg.llVal )
  {
    load = a1->lpVtbl->load;
    v11 = pvarg;
    v8 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, VARIANTARG *, __int16 *))load)(a1, &v11, &v12);
    v6 = v8;
    if ( v8 >= 0 )
    {
      v6 = 0;
LABEL_8:
      *a3 = v12 == -1;
      goto LABEL_9;
    }
    if ( (v8 & 0x1FFF0000) == 0x70000 )
      v6 = (unsigned __int16)v8;
    if ( !v6 )
      goto LABEL_8;
  }
LABEL_9:
  VariantClear(&pvarg);
  return v6;
}

```

## disassembly

```asm
0x180013280  push    rbp
0x180013282  push    rbx
0x180013283  push    rsi
0x180013284  push    rdi
0x180013285  mov     rbp, rsp
0x180013288  sub     rsp, 68h
0x18001328c  mov     rsi, rcx
0x18001328f  mov     rdi, r8
0x180013292  lea     rcx, [rbp+pvarg]; pvarg
0x180013296  mov     rbx, rdx
0x180013299  call    cs:__imp_VariantInit
0x18001329f  xor     eax, eax
0x1800132a1  lea     rcx, [rbp+pvarg]; Destination
0x1800132a5  mov     rdx, rbx; psz
0x1800132a8  mov     [rbp+arg_18], ax
0x1800132ac  call    ?AtlAssignNoThrow@@YAXAEAVCComVariant@ATL@@PEBG@Z; AtlAssignNoThrow(ATL::CComVariant &,ushort const *)
0x1800132b1  mov     ebx, 8
0x1800132b6  cmp     word ptr [rbp+pvarg], bx
0x1800132ba  jnz     short loc_180013318
0x1800132bc  cmp     qword ptr [rbp+pvarg+8], 0
0x1800132c1  jz      short loc_180013318
0x1800132c3  mov     rax, [rsi]
0x1800132c6  lea     r8, [rbp+arg_18]
0x1800132ca  movups  xmm0, xmmword ptr [rbp+pvarg]
0x1800132ce  lea     rdx, [rbp+var_28]
0x1800132d2  mov     rcx, rsi
0x1800132d5  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x1800132da  mov     rax, [rax+1D0h]
0x1800132e1  movaps  [rbp+var_28], xmm0
0x1800132e5  movsd   [rbp+var_18], xmm1
0x1800132ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800132ef  mov     ebx, eax
0x1800132f1  test    eax, eax
0x1800132f3  js      short loc_1800132F9
0x1800132f5  xor     ebx, ebx
0x1800132f7  jmp     short loc_18001330C
0x1800132f9  and     eax, 1FFF0000h
0x1800132fe  cmp     eax, 70000h
0x180013303  jnz     short loc_180013308
0x180013305  movzx   ebx, bx
0x180013308  test    ebx, ebx
0x18001330a  jnz     short loc_180013318
0x18001330c  xor     eax, eax
0x18001330e  cmp     [rbp+arg_18], 0FFFFh
0x180013313  setz    al
0x180013316  mov     [rdi], eax
0x180013318  lea     rcx, [rbp+pvarg]; pvarg
0x18001331c  call    cs:__imp_VariantClear
0x180013322  mov     eax, ebx
0x180013324  add     rsp, 68h
0x180013328  pop     rdi
0x180013329  pop     rsi
0x18001332a  pop     rbx
0x18001332b  pop     rbp
0x18001332c  retn
```
