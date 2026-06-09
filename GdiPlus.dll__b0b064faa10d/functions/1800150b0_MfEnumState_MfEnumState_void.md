# MfEnumState::~MfEnumState(void)

- ea: `0x1800150b0`
- end: `0x180015136`
- name: `??1MfEnumState@@UEAA@XZ`
- size: `134`
- prototype: `void __fastcall(MfEnumState *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180014fec`
- `0x1800e374c`
- `0x1800e5b5c`
- `0x180128f60`

## callees

- `0x1800150b0`

## import_xrefs

- `GDI32!GetStockObject` at `0x1800150cc`
- `GDI32!GetStockObject` at `0x1800150cc`
- `GDI32!SelectObject` at `0x1800150d9`
- `GDI32!SelectObject` at `0x1800150d9`
- `GDI32!DeleteObject` at `0x1800150e8`
- `GDI32!DeleteObject` at `0x180015126`
- `GDI32!DeleteObject` at `0x18001512e`
- `GDI32!DeleteObject` at `0x1800150e8`
- `GDI32!DeleteObject` at `0x180015126`
- `GDI32!DeleteObject` at `0x18001512e`

## pseudocode

```c
void __fastcall MfEnumState::~MfEnumState(HDC *this)
{
  HGDIOBJ StockObject; // rax
  HDC v3; // rcx
  __int64 i; // rbx
  HDC v5; // rcx
  __int64 j; // rbx
  HDC v7; // rcx

  *this = (HDC)&MfEnumState::`vftable';
  StockObject = GetStockObject(13);
  SelectObject(this[2], StockObject);
  v3 = this[8];
  if ( v3 )
    DeleteObject(v3);
  for ( i = 0; i != 8; ++i )
  {
    v5 = this[i + 9];
    if ( v5 )
      DeleteObject(v5);
  }
  for ( j = 0; j != 7; ++j )
  {
    v7 = this[j + 289];
    if ( v7 )
      DeleteObject(v7);
  }
}

```

## disassembly

```asm
0x1800150b0  mov     [rsp+arg_0], rbx
0x1800150b5  push    rdi
0x1800150b6  sub     rsp, 20h
0x1800150ba  lea     rax, ??_7MfEnumState@@6B@; const MfEnumState::`vftable'
0x1800150c1  mov     rdi, rcx
0x1800150c4  mov     [rcx], rax
0x1800150c7  mov     ecx, 0Dh; i
0x1800150cc  call    cs:__imp_GetStockObject
0x1800150d2  mov     rcx, [rdi+10h]; hdc
0x1800150d6  mov     rdx, rax; h
0x1800150d9  call    cs:__imp_SelectObject
0x1800150df  mov     rcx, [rdi+40h]; ho
0x1800150e3  test    rcx, rcx
0x1800150e6  jz      short loc_1800150EE
0x1800150e8  call    cs:__imp_DeleteObject
0x1800150ee  xor     ebx, ebx
0x1800150f0  mov     rcx, [rdi+rbx*8+48h]; ho
0x1800150f5  test    rcx, rcx
0x1800150f8  jnz     short loc_180015126
0x1800150fa  inc     rbx
0x1800150fd  cmp     rbx, 8
0x180015101  jnz     short loc_1800150F0
0x180015103  xor     ebx, ebx
0x180015105  mov     rcx, [rdi+rbx*8+908h]; ho
0x18001510d  test    rcx, rcx
0x180015110  jnz     short loc_18001512E
0x180015112  inc     rbx
0x180015115  cmp     rbx, 7
0x180015119  jnz     short loc_180015105
0x18001511b  mov     rbx, [rsp+28h+arg_0]
0x180015120  add     rsp, 20h
0x180015124  pop     rdi
0x180015125  retn
0x180015126  call    cs:__imp_DeleteObject
0x18001512c  jmp     short loc_1800150FA
0x18001512e  call    cs:__imp_DeleteObject
0x180015134  jmp     short loc_180015112
```
