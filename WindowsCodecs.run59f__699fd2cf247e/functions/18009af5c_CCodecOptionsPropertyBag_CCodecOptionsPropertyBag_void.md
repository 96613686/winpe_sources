# CCodecOptionsPropertyBag::~CCodecOptionsPropertyBag(void)

- ea: `0x18009af5c`
- end: `0x18009b012`
- name: `??1CCodecOptionsPropertyBag@@MEAA@XZ`
- size: `182`
- prototype: `void __fastcall(CCodecOptionsPropertyBag *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18009af00`
- `0x1801a5340`

## callees

- `0x18002b724`
- `0x18002c6e8`
- `0x18002cb08`
- `0x18009af5c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009b004`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009b004`
- `OLEAUT32!__imp_VariantClear` at `0x18009afac`
- `OLEAUT32!__imp_VariantClear` at `0x18009afac`

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
0x18009af5c  push    rbx
0x18009af5e  push    rbp
0x18009af5f  push    rsi
0x18009af60  push    rdi
0x18009af61  push    r14
0x18009af63  sub     rsp, 20h
0x18009af67  lea     rax, ??_7CCodecOptionsPropertyBag@@6BCMILCOMBase@@@; const CCodecOptionsPropertyBag::`vftable'{for `CMILCOMBase'}
0x18009af6e  xor     edi, edi
0x18009af70  mov     rbx, rcx
0x18009af73  mov     [rcx], rax
0x18009af76  lea     rax, ??_7CCodecOptionsPropertyBag@@6BCMTALock@@@; const CCodecOptionsPropertyBag::`vftable'{for `CMTALock'}
0x18009af7d  mov     [rcx+10h], rax
0x18009af81  lea     rax, ??_7CCodecOptionsPropertyBag@@6BIPropertyBag2@@@; const CCodecOptionsPropertyBag::`vftable'{for `IPropertyBag2'}
0x18009af88  mov     [rcx+48h], rax
0x18009af8c  cmp     [rcx+68h], edi
0x18009af8f  jbe     short loc_18009AFF4
0x18009af91  lea     rsi, [rbx+50h]
0x18009af95  mov     r14, [rsi]
0x18009af98  lea     rbp, [rdi+rdi*8]
0x18009af9c  cmp     dword ptr [r14+rbp*8+40h], 0
0x18009afa2  jz      short loc_18009AFFA
0x18009afa4  lea     rcx, [r14+28h]
0x18009afa8  lea     rcx, [rcx+rbp*8]; pvarg
0x18009afac  call    cs:__imp_VariantClear
0x18009afb3  nop     dword ptr [rax+rax+00h]
0x18009afb8  inc     edi
0x18009afba  cmp     edi, [rbx+68h]
0x18009afbd  jb      short loc_18009AF91
0x18009afbf  mov     rcx, rsi
0x18009afc2  call    ??1?$DynArrayImpl@$00@@IEAA@XZ; DynArrayImpl<1>::~DynArrayImpl<1>(void)
0x18009afc7  lea     rax, ??_7CMTALock@@6B@; const CMTALock::`vftable'
0x18009afce  lea     rcx, [rbx+18h]; this
0x18009afd2  mov     [rbx+10h], rax
0x18009afd6  call    ?DeInit@CCriticalSection@@QEAAXXZ; CCriticalSection::DeInit(void)
0x18009afdb  lea     rax, ??_7CMILCOMBase@@6B@; const CMILCOMBase::`vftable'
0x18009afe2  mov     [rbx], rax
0x18009afe5  add     rsp, 20h
0x18009afe9  pop     r14
0x18009afeb  pop     rdi
0x18009afec  pop     rsi
0x18009afed  pop     rbp
0x18009afee  pop     rbx
0x18009afef  jmp     ?MILCOMUnlock@@YAJXZ; MILCOMUnlock(void)
0x18009aff4  lea     rsi, [rcx+50h]
0x18009aff8  jmp     short loc_18009AFBF
0x18009affa  mov     rcx, [r14+rbp*8+10h]; pv
0x18009afff  test    rcx, rcx
0x18009b002  jz      short loc_18009AFA4
0x18009b004  call    cs:__imp_CoTaskMemFree
0x18009b00b  nop     dword ptr [rax+rax+00h]
0x18009b010  jmp     short loc_18009AFA4
```
