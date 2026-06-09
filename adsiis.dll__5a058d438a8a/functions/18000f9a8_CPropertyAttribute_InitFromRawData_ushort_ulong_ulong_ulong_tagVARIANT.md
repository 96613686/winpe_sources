# CPropertyAttribute::InitFromRawData(ushort *,ulong,ulong,ulong,tagVARIANT *)

- ea: `0x18000f9a8`
- end: `0x18000fa37`
- name: `?InitFromRawData@CPropertyAttribute@@QEAAJPEAGKKKPEAUtagVARIANT@@@Z`
- size: `143`
- prototype: `int(CPropertyAttribute *__hidden this, unsigned __int16 *, unsigned int, unsigned int, unsigned int, struct tagVARIANT *)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180006240`
- `0x180008a50`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x18000f9cc`
- `msvcrt!wcscpy_s` at `0x18000f9cc`
- `OLEAUT32!__imp_VariantCopy` at `0x18000fa30`

## pseudocode

```c
HRESULT __fastcall CPropertyAttribute::InitFromRawData(
        VARIANTARG *this,
        unsigned __int16 *a2,
        LONG a3,
        int a4,
        unsigned int a5,
        struct tagVARIANT *a6)
{
  wcscpy_s(&this[2].wReserved2, 0x104u, a2);
  *((_DWORD *)&this->decVal + 5) = a5;
  this->cyVal.Hi = a3;
  *(_DWORD *)&this[1].vt = a5 & 1;
  *((_DWORD *)&this->decVal + 4) = a4;
  this[1].decVal.Hi32 = a5 & 2;
  this[1].lVal = a5 & 4;
  this[1].cyVal.Hi = a5 & 8;
  *((_DWORD *)&this[1].decVal + 4) = a5 & 0x10;
  *(_DWORD *)&this[2].vt = a5 & 0x40;
  *((_DWORD *)&this[1].decVal + 5) = a5 & 0x20;
  return VariantCopy(this + 24, a6);
}

```

## disassembly

```asm
0x18000f9a8  mov     [rsp+arg_0], rbx
0x18000f9ad  mov     [rsp+arg_8], rsi
0x18000f9b2  push    rdi
0x18000f9b3  sub     rsp, 20h
0x18000f9b7  mov     ebx, r8d
0x18000f9ba  mov     rsi, rcx
0x18000f9bd  mov     r8, rdx; Source
0x18000f9c0  add     rcx, 34h ; '4'; Destination
0x18000f9c4  mov     edx, 104h; SizeInWords
0x18000f9c9  mov     edi, r9d
0x18000f9cc  call    cs:__imp_wcscpy_s
0x18000f9d2  mov     edx, [rsp+28h+arg_20]
0x18000f9d6  lea     rcx, [rsi+240h]
0x18000f9dd  mov     eax, edx
0x18000f9df  mov     [rsi+14h], edx
0x18000f9e2  and     eax, 1
0x18000f9e5  mov     [rsi+0Ch], ebx
0x18000f9e8  mov     [rsi+18h], eax
0x18000f9eb  mov     eax, edx
0x18000f9ed  and     eax, 2
0x18000f9f0  mov     [rsi+10h], edi
0x18000f9f3  mov     [rsi+1Ch], eax
0x18000f9f6  mov     eax, edx
0x18000f9f8  and     eax, 4
0x18000f9fb  mov     [rsi+20h], eax
0x18000f9fe  mov     eax, edx
0x18000fa00  and     eax, 8
0x18000fa03  mov     [rsi+24h], eax
0x18000fa06  mov     eax, edx
0x18000fa08  and     eax, 10h
0x18000fa0b  mov     [rsi+28h], eax
0x18000fa0e  mov     eax, edx
0x18000fa10  and     edx, 40h
0x18000fa13  and     eax, 20h
0x18000fa16  mov     [rsi+30h], edx
0x18000fa19  mov     rdx, [rsp+28h+arg_28]
0x18000fa1e  mov     [rsi+2Ch], eax
0x18000fa21  mov     rbx, [rsp+28h+arg_0]
0x18000fa26  mov     rsi, [rsp+28h+arg_8]
0x18000fa2b  add     rsp, 20h
0x18000fa2f  pop     rdi
0x18000fa30  jmp     cs:__imp_VariantCopy
```
