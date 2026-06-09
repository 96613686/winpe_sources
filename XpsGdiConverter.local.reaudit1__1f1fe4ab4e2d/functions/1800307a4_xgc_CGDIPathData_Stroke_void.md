# xgc::CGDIPathData::Stroke(void)

- ea: `0x1800307a4`
- end: `0x180030892`
- name: `?Stroke@CGDIPathData@xgc@@QEBAXXZ`
- size: `238`
- prototype: `void __fastcall(xgc::CGDIPathData *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18002e550`

## callees

- `0x1800307a4`
- `0x180037278`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800307e3`
- `KERNEL32!GetLastError` at `0x180030828`
- `KERNEL32!GetLastError` at `0x180030868`
- `KERNEL32!GetLastError` at `0x1800307e3`
- `KERNEL32!GetLastError` at `0x180030828`
- `KERNEL32!GetLastError` at `0x180030868`
- `GDI32!PolyDraw` at `0x1800307d5`
- `GDI32!PolyDraw` at `0x1800307d5`
- `GDI32!LineTo` at `0x18003085e`
- `GDI32!LineTo` at `0x18003085e`
- `GDI32!MoveToEx` at `0x18003081e`
- `GDI32!MoveToEx` at `0x18003081e`

## pseudocode

```c
void __fastcall xgc::CGDIPathData::Stroke(xgc::CGDIPathData *this)
{
  const POINT *v1; // rdx
  unsigned __int64 v3; // rax
  signed int v4; // eax
  int v5; // edx
  const char *v6; // r8
  int v7; // r9d
  signed int LastError; // eax
  int v9; // edx
  const char *v10; // r8
  int v11; // r9d
  signed int v12; // eax
  int v13; // edx
  const char *v14; // r8
  int v15; // r9d

  v1 = (const POINT *)*((_QWORD *)this + 5);
  v3 = (__int64)(*((_QWORD *)this + 6) - (_QWORD)v1) >> 3;
  if ( v3 < 2 )
  {
    if ( v3 == 1 )
    {
      if ( !MoveToEx(*(HDC *)(*((_QWORD *)this + 2) + 32LL), v1->x, v1->y, 0) )
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        if ( LastError >= 0 )
          LastError = -2147467259;
        xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)LastError, v9, v10, v11);
      }
      if ( !LineTo(
              *(HDC *)(*((_QWORD *)this + 2) + 32LL),
              **((_DWORD **)this + 5),
              *(_DWORD *)(*((_QWORD *)this + 5) + 4LL)) )
      {
        v12 = GetLastError();
        if ( v12 > 0 )
          v12 = (unsigned __int16)v12 | 0x80070000;
        if ( v12 >= 0 )
          v12 = -2147467259;
        xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v12, v13, v14, v15);
      }
    }
  }
  else if ( !PolyDraw(
               *(HDC *)(*((_QWORD *)this + 2) + 32LL),
               v1,
               *((const BYTE **)this + 8),
               *((_DWORD *)this + 18) - *((_QWORD *)this + 8)) )
  {
    v4 = GetLastError();
    if ( v4 > 0 )
      v4 = (unsigned __int16)v4 | 0x80070000;
    if ( v4 >= 0 )
      v4 = -2147467259;
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v4, v5, v6, v7);
  }
}

```

## disassembly

```asm
0x1800307a4  push    rbx
0x1800307a6  sub     rsp, 20h
0x1800307aa  mov     rdx, [rcx+28h]; apt
0x1800307ae  mov     rbx, rcx
0x1800307b1  mov     rax, [rcx+30h]
0x1800307b5  sub     rax, rdx
0x1800307b8  sar     rax, 3
0x1800307bc  cmp     rax, 2
0x1800307c0  jb      short loc_180030807
0x1800307c2  mov     r8, [rcx+40h]; aj
0x1800307c6  mov     r9d, [rcx+48h]
0x1800307ca  mov     rcx, [rcx+10h]
0x1800307ce  sub     r9d, r8d; cpt
0x1800307d1  mov     rcx, [rcx+20h]; hdc
0x1800307d5  call    cs:__imp_PolyDraw
0x1800307db  test    eax, eax
0x1800307dd  jnz     loc_18003088C
0x1800307e3  call    cs:__imp_GetLastError
0x1800307e9  test    eax, eax
0x1800307eb  jle     short loc_1800307F5
0x1800307ed  movzx   eax, ax
0x1800307f0  or      eax, 80070000h
0x1800307f5  mov     ecx, 80004005h
0x1800307fa  test    eax, eax
0x1800307fc  cmovns  eax, ecx
0x1800307ff  mov     ecx, eax; this
0x180030801  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x180030807  cmp     rax, 1
0x18003080b  jnz     short loc_18003088C
0x18003080d  mov     rcx, [rcx+10h]
0x180030811  xor     r9d, r9d; lppt
0x180030814  mov     r8d, [rdx+4]; y
0x180030818  mov     edx, [rdx]; x
0x18003081a  mov     rcx, [rcx+20h]; hdc
0x18003081e  call    cs:__imp_MoveToEx
0x180030824  test    eax, eax
0x180030826  jnz     short loc_18003084C
0x180030828  call    cs:__imp_GetLastError
0x18003082e  test    eax, eax
0x180030830  jle     short loc_18003083A
0x180030832  movzx   eax, ax
0x180030835  or      eax, 80070000h
0x18003083a  mov     ecx, 80004005h
0x18003083f  test    eax, eax
0x180030841  cmovns  eax, ecx
0x180030844  mov     ecx, eax; this
0x180030846  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18003084c  mov     rdx, [rbx+28h]
0x180030850  mov     rcx, [rbx+10h]
0x180030854  mov     r8d, [rdx+4]; y
0x180030858  mov     edx, [rdx]; x
0x18003085a  mov     rcx, [rcx+20h]; hdc
0x18003085e  call    cs:__imp_LineTo
0x180030864  test    eax, eax
0x180030866  jnz     short loc_18003088C
0x180030868  call    cs:__imp_GetLastError
0x18003086e  test    eax, eax
0x180030870  jle     short loc_18003087A
0x180030872  movzx   eax, ax
0x180030875  or      eax, 80070000h
0x18003087a  mov     ecx, 80004005h
0x18003087f  test    eax, eax
0x180030881  cmovns  eax, ecx
0x180030884  mov     ecx, eax; this
0x180030886  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18003088c  add     rsp, 20h
0x180030890  pop     rbx
0x180030891  retn
```
