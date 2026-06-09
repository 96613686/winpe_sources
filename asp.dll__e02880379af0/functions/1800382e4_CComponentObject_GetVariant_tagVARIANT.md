# CComponentObject::GetVariant(tagVARIANT *)

- ea: `0x1800382e4`
- end: `0x18003839b`
- name: `?GetVariant@CComponentObject@@QEAAJPEAUtagVARIANT@@@Z`
- size: `183`
- prototype: `int(CComponentObject *__hidden this, struct tagVARIANT *)`
- caller_count: `4`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180032df0`
- `0x1800330c0`
- `0x180059540`
- `0x180059950`

## callees

- `0x1800382e4`
- `0x180064010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1800382fc`
- `OLEAUT32!__imp_VariantInit` at `0x1800382fc`
- `OLEAUT32!__imp_VariantCopyInd` at `0x180038312`
- `OLEAUT32!__imp_VariantCopyInd` at `0x180038312`

## pseudocode

```c
__int64 __fastcall CComponentObject::GetVariant(CComponentObject *this, struct tagVARIANT *a2)
{
  int v4; // esi
  __int64 v5; // rcx
  LONGLONG v6; // rax
  __int64 v7; // rdx
  LONGLONG v9; // [rsp+40h] [rbp+8h] BYREF

  VariantInit(a2);
  if ( (*((_DWORD *)this + 10) & 0x40000) != 0 )
    return (unsigned int)VariantCopyInd(a2, (const VARIANTARG *)((char *)this + 64));
  v5 = *((_QWORD *)this + 6);
  if ( v5 )
  {
    v4 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 8LL))(v5);
    a2->vt = 9;
    v6 = *((_QWORD *)this + 6);
LABEL_8:
    a2->llVal = v6;
    return (unsigned int)v4;
  }
  v7 = *((unsigned int *)this + 22);
  if ( (_DWORD)v7 == -1 )
    return (unsigned int)-2147467261;
  v9 = 0;
  v4 = (*(__int64 (__fastcall **)(LPVOID, __int64, GUID *, LONGLONG *))(*(_QWORD *)ppv + 40LL))(
         ppv,
         v7,
         &IID_IDispatch,
         &v9);
  if ( v4 >= 0 )
  {
    v6 = v9;
    a2->vt = 9;
    goto LABEL_8;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800382e4  mov     [rsp+arg_8], rbx
0x1800382e9  mov     [rsp+arg_10], rsi
0x1800382ee  push    rdi
0x1800382ef  sub     rsp, 30h
0x1800382f3  mov     rdi, rcx
0x1800382f6  mov     rbx, rdx
0x1800382f9  mov     rcx, rdx; pvarg
0x1800382fc  call    cs:__imp_VariantInit
0x180038302  test    dword ptr [rdi+28h], 40000h
0x180038309  jz      short loc_18003831C
0x18003830b  lea     rdx, [rdi+40h]; pvargSrc
0x18003830f  mov     rcx, rbx; pvarDest
0x180038312  call    cs:__imp_VariantCopyInd
0x180038318  mov     esi, eax
0x18003831a  jmp     short loc_180038389
0x18003831c  mov     rcx, [rdi+30h]
0x180038320  test    rcx, rcx
0x180038323  jz      short loc_18003833E
0x180038325  mov     rax, [rcx]
0x180038328  xor     esi, esi
0x18003832a  mov     rax, [rax+8]
0x18003832e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038333  mov     word ptr [rbx], 9
0x180038338  mov     rax, [rdi+30h]
0x18003833c  jmp     short loc_18003837E
0x18003833e  mov     edx, [rdi+58h]
0x180038341  cmp     edx, 0FFFFFFFFh
0x180038344  jz      short loc_180038384
0x180038346  mov     rcx, cs:ppv
0x18003834d  lea     r9, [rsp+38h+arg_0]
0x180038352  mov     [rsp+38h+arg_0], 0
0x18003835b  lea     r8, IID_IDispatch
0x180038362  mov     rax, [rcx]
0x180038365  mov     rax, [rax+28h]
0x180038369  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003836e  mov     esi, eax
0x180038370  test    eax, eax
0x180038372  js      short loc_180038389
0x180038374  mov     rax, [rsp+38h+arg_0]
0x180038379  mov     word ptr [rbx], 9
0x18003837e  mov     [rbx+8], rax
0x180038382  jmp     short loc_180038389
0x180038384  mov     esi, 80004003h
0x180038389  mov     rbx, [rsp+38h+arg_8]
0x18003838e  mov     eax, esi
0x180038390  mov     rsi, [rsp+38h+arg_10]
0x180038395  add     rsp, 30h
0x180038399  pop     rdi
0x18003839a  retn
```
