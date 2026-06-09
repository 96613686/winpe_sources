# CRowset::CheckThreadModel(IUnknown *)

- ea: `0x18002010c`
- end: `0x1800201ee`
- name: `?CheckThreadModel@CRowset@@QEAAXPEAUIUnknown@@@Z`
- size: `226`
- prototype: `void __fastcall(CRowset *__hidden this, struct IUnknown *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18000f2f8`
- `0x180026028`

## callees

- `0x18002010c`
- `0x18002ca58`
- `0x18002e02a`
- `0x18002e060`
- `0x180030010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180020194`
- `OLEAUT32!__imp_VariantInit` at `0x180020194`

## pseudocode

```c
void __fastcall CRowset::CheckThreadModel(CRowset *this, struct IUnknown *a2)
{
  struct IUnknownVtbl *lpVtbl; // rax
  unsigned int v4; // edx
  __int64 v5; // [rsp+30h] [rbp-39h] BYREF
  struct tagDBPROPSET v6; // [rsp+38h] [rbp-31h] BYREF
  _QWORD v7[6]; // [rsp+60h] [rbp-9h] BYREF
  VARIANTARG pvarg; // [rsp+90h] [rbp+27h] BYREF

  lpVtbl = a2->lpVtbl;
  v5 = 0;
  if ( ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))lpVtbl->QueryInterface)(
         a2,
         &IID_IAsyncAllowed,
         &v5) < 0 )
  {
    *((_DWORD *)&v6.guidPropertySet + 4) = 0;
    memset_0(v7, 0, 0x48u);
    v6.cProperties = 1;
    v6.rgProperties = (DBPROP *)v7;
    v6.guidPropertySet = DBPROPSET_ROWSET;
    v7[0] = 105;
    VariantInit(&pvarg);
    pvarg.vt = 3;
    pvarg.lVal = 4;
    CUtlProps::utlSetProperties((CRowset *)((char *)this + 400), v4, 1u, &v6, (CRowset *)((char *)this + 112), 1);
  }
}

```

## disassembly

```asm
0x18002010c  mov     [rsp-8+arg_10], rbx
0x180020111  push    rbp
0x180020112  lea     rbp, [rsp-57h]
0x180020117  sub     rsp, 0C0h
0x18002011e  mov     rax, cs:__security_cookie
0x180020125  xor     rax, rsp
0x180020128  mov     [rbp+57h+var_10], rax
0x18002012c  mov     rax, [rdx]
0x18002012f  lea     r8, [rbp+57h+var_90]
0x180020133  mov     r9, rdx
0x180020136  mov     [rbp+57h+var_90], 0
0x18002013e  mov     rbx, rcx
0x180020141  lea     rdx, ?IID_IAsyncAllowed@@3U_GUID@@B; _GUID const IID_IAsyncAllowed
0x180020148  mov     rcx, r9
0x18002014b  mov     rax, [rax]
0x18002014e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020153  test    eax, eax
0x180020155  jns     short loc_1800201D1
0x180020157  xor     edx, edx; Val
0x180020159  mov     dword ptr [rbp+57h+var_88+1Ch], 0
0x180020160  lea     rcx, [rbp+57h+var_60]; void *
0x180020164  lea     r8d, [rdx+48h]; Size
0x180020168  call    memset_0
0x18002016d  movups  xmm0, xmmword ptr cs:DBPROPSET_ROWSET.Data1
0x180020174  lea     rax, [rbp+57h+var_60]
0x180020178  mov     [rbp+57h+var_88.cProperties], 1
0x18002017f  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180020183  mov     [rbp+57h+var_88.rgProperties], rax
0x180020187  movdqu  xmmword ptr [rbp+57h+var_88.guidPropertySet.Data1], xmm0
0x18002018c  mov     [rbp+57h+var_60], 69h ; 'i'
0x180020194  call    cs:__imp_VariantInit
0x18002019a  mov     eax, 3
0x18002019f  mov     [rsp+0C0h+var_98], 1; int
0x1800201a7  mov     word ptr [rbp+57h+pvarg], ax
0x1800201ab  lea     rcx, [rbx+190h]; this
0x1800201b2  lea     rax, [rbx+70h]
0x1800201b6  mov     dword ptr [rbp+57h+pvarg+8], 4
0x1800201bd  lea     r9, [rbp+57h+var_88]; struct tagDBPROPSET *
0x1800201c1  mov     [rsp+0C0h+var_A0], rax; struct CBidGenericBase *
0x1800201c6  mov     r8d, 1; unsigned int
0x1800201cc  call    ?utlSetProperties@CUtlProps@@QEAAJKKQEBUtagDBPROPSET@@AEBVCBidGenericBase@@H@Z; CUtlProps::utlSetProperties(ulong,ulong,tagDBPROPSET const * const,CBidGenericBase const &,int)
0x1800201d1  mov     rcx, [rbp+57h+var_10]
0x1800201d5  xor     rcx, rsp; StackCookie
0x1800201d8  call    __security_check_cookie
0x1800201dd  mov     rbx, [rsp+0C0h+arg_10]
0x1800201e5  add     rsp, 0C0h
0x1800201ec  pop     rbp
0x1800201ed  retn
```
