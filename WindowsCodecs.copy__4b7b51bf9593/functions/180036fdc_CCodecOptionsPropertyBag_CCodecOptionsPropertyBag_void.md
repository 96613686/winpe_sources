# CCodecOptionsPropertyBag::~CCodecOptionsPropertyBag(void)

- ea: `0x180036fdc`
- end: `0x180037086`
- name: `??1CCodecOptionsPropertyBag@@MEAA@XZ`
- size: `170`
- prototype: `void __fastcall(CCodecOptionsPropertyBag *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180036f80`
- `0x1801a2090`

## callees

- `0x180035678`
- `0x180036fdc`
- `0x18003baa0`
- `0x18003cad8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003707e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003707e`
- `OLEAUT32!__imp_VariantClear` at `0x18003702c`
- `OLEAUT32!__imp_VariantClear` at `0x18003702c`

## pseudocode

```c
void __fastcall CCodecOptionsPropertyBag::~CCodecOptionsPropertyBag(CCodecOptionsPropertyBag *this)
{
  __int64 v1; // rdi
  char *v3; // rsi
  __int64 v4; // r14
  void *v5; // rcx

  v1 = 0;
  *(_QWORD *)this = &CCodecOptionsPropertyBag::`vftable'{for `CMILCOMBase'};
  *((_QWORD *)this + 2) = &CCodecOptionsPropertyBag::`vftable'{for `CMTALock'};
  *((_QWORD *)this + 9) = &CCodecOptionsPropertyBag::`vftable'{for `IPropertyBag2'};
  if ( *((_DWORD *)this + 26) )
  {
    do
    {
      v3 = (char *)this + 80;
      v4 = *((_QWORD *)this + 10);
      if ( !*(_DWORD *)(v4 + 72 * v1 + 64) )
      {
        v5 = *(void **)(v4 + 72 * v1 + 16);
        if ( v5 )
          CoTaskMemFree(v5);
      }
      VariantClear((VARIANTARG *)(v4 + 40 + 72 * v1));
      v1 = (unsigned int)(v1 + 1);
    }
    while ( (unsigned int)v1 < *((_DWORD *)this + 26) );
  }
  else
  {
    v3 = (char *)this + 80;
  }
  DynArrayImpl<1>::~DynArrayImpl<1>(v3);
  *((_QWORD *)this + 2) = &CMTALock::`vftable';
  CCriticalSection::DeInit((CCodecOptionsPropertyBag *)((char *)this + 24));
  *(_QWORD *)this = &CMILCOMBase::`vftable';
  MILCOMUnlock();
}

```

## disassembly

```asm
0x180036fdc  push    rbx
0x180036fde  push    rbp
0x180036fdf  push    rsi
0x180036fe0  push    rdi
0x180036fe1  push    r14
0x180036fe3  sub     rsp, 20h
0x180036fe7  lea     rax, ??_7CCodecOptionsPropertyBag@@6BCMILCOMBase@@@; const CCodecOptionsPropertyBag::`vftable'{for `CMILCOMBase'}
0x180036fee  xor     edi, edi
0x180036ff0  mov     rbx, rcx
0x180036ff3  mov     [rcx], rax
0x180036ff6  lea     rax, ??_7CCodecOptionsPropertyBag@@6BCMTALock@@@; const CCodecOptionsPropertyBag::`vftable'{for `CMTALock'}
0x180036ffd  mov     [rcx+10h], rax
0x180037001  lea     rax, ??_7CCodecOptionsPropertyBag@@6BIPropertyBag2@@@; const CCodecOptionsPropertyBag::`vftable'{for `IPropertyBag2'}
0x180037008  mov     [rcx+48h], rax
0x18003700c  cmp     [rcx+68h], edi
0x18003700f  jbe     short loc_18003706E
0x180037011  lea     rsi, [rbx+50h]
0x180037015  mov     r14, [rsi]
0x180037018  lea     rbp, [rdi+rdi*8]
0x18003701c  cmp     dword ptr [r14+rbp*8+40h], 0
0x180037022  jz      short loc_180037074
0x180037024  lea     rcx, [r14+28h]
0x180037028  lea     rcx, [rcx+rbp*8]; pvarg
0x18003702c  call    cs:__imp_VariantClear
0x180037032  inc     edi
0x180037034  cmp     edi, [rbx+68h]
0x180037037  jb      short loc_180037011
0x180037039  mov     rcx, rsi
0x18003703c  call    ??1?$DynArrayImpl@$00@@IEAA@XZ; DynArrayImpl<1>::~DynArrayImpl<1>(void)
0x180037041  lea     rax, ??_7CMTALock@@6B@; const CMTALock::`vftable'
0x180037048  lea     rcx, [rbx+18h]; this
0x18003704c  mov     [rbx+10h], rax
0x180037050  call    ?DeInit@CCriticalSection@@QEAAXXZ; CCriticalSection::DeInit(void)
0x180037055  lea     rax, ??_7CMILCOMBase@@6B@; const CMILCOMBase::`vftable'
0x18003705c  mov     [rbx], rax
0x18003705f  add     rsp, 20h
0x180037063  pop     r14
0x180037065  pop     rdi
0x180037066  pop     rsi
0x180037067  pop     rbp
0x180037068  pop     rbx
0x180037069  jmp     ?MILCOMUnlock@@YAJXZ; MILCOMUnlock(void)
0x18003706e  lea     rsi, [rcx+50h]
0x180037072  jmp     short loc_180037039
0x180037074  mov     rcx, [r14+rbp*8+10h]; pv
0x180037079  test    rcx, rcx
0x18003707c  jz      short loc_180037024
0x18003707e  call    cs:__imp_CoTaskMemFree
0x180037084  jmp     short loc_180037024
```
