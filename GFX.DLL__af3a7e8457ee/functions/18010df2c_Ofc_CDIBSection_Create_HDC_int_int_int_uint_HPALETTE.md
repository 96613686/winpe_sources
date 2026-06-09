# Ofc::CDIBSection::Create(HDC__ *,int,int,int,uint,HPALETTE__ *)

- ea: `0x18010df2c`
- end: `0x18010e055`
- name: `?Create@CDIBSection@Ofc@@QEAAXPEAUHDC__@@HHHIPEAUHPALETTE__@@@Z`
- size: `297`
- prototype: `void __fastcall(Ofc::CDIBSection *__hidden this, HDC, int, int, int, unsigned int, HPALETTE)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800b0f44`
- `0x18010de18`
- `0x18010e69c`

## callees

- `0x18001ffb4`
- `0x1800786fc`
- `0x18010df2c`
- `0x18010e060`

## import_xrefs

- `GDI32!GetPaletteEntries` at `0x18010dfdb`
- `GDI32!GetPaletteEntries` at `0x18010dfdb`
- `GDI32!CreateDIBSection` at `0x18010e02e`
- `GDI32!CreateDIBSection` at `0x18010e02e`
- `GDI32!GetStockObject` at `0x18010dfca`
- `GDI32!GetStockObject` at `0x18010dfca`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Ofc::CDIBSection::Create(void **this, HDC a2, int a3, LONG a4, int a5)
{
  unsigned __int64 v8; // rdx
  unsigned int v9; // r8d
  signed int v10; // esi
  unsigned int v11; // r8d
  BITMAPINFO *v12; // r14
  __int64 v13; // rdi
  unsigned __int128 v14; // rax
  struct tagPALETTEENTRY *v15; // rbx
  HPALETTE StockObject; // rax
  BYTE *p_peGreen; // rcx
  signed __int64 v18; // rdx

  Ofc::CDIBSection::Reset((Ofc::CDIBSection *)this);
  v10 = 1 << a3;
  if ( a3 > 8 )
    v10 = 0;
  v12 = (BITMAPINFO *)Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)(4 * v10 + 40), v8, v9);
  v12->bmiHeader.biSize = 40;
  v12->bmiHeader.biWidth = a4;
  v12->bmiHeader.biHeight = -a5;
  v12->bmiHeader.biPlanes = 1;
  *(_QWORD *)&v12->bmiHeader.biCompression = 0;
  *(_QWORD *)&v12->bmiHeader.biXPelsPerMeter = 0;
  *(_QWORD *)&v12->bmiHeader.biClrUsed = 0;
  v12->bmiHeader.biBitCount = a3;
  v13 = v10;
  v14 = (unsigned __int64)v10 * (unsigned __int128)4u;
  if ( !is_mul_ok(v10, 4u) )
    *(_QWORD *)&v14 = -1;
  v15 = (struct tagPALETTEENTRY *)Mso::Memory::Throw::AllocateEx(
                                    (Mso::Memory::Throw *)v14,
                                    *((unsigned __int64 *)&v14 + 1),
                                    v11);
  StockObject = (HPALETTE)GetStockObject(15);
  GetPaletteEntries(StockObject, 0, v10, v15);
  if ( v10 > 0 )
  {
    p_peGreen = &v15->peGreen;
    v18 = (char *)v12 - (char *)v15;
    do
    {
      p_peGreen[v18 + 41] = *(p_peGreen - 1);
      p_peGreen[v18 + 40] = *p_peGreen;
      p_peGreen[v18 + 39] = p_peGreen[1];
      p_peGreen[v18 + 42] = 0;
      p_peGreen += 4;
      --v13;
    }
    while ( v13 );
  }
  operator delete(v15);
  *this = CreateDIBSection(0, v12, 0, this + 1, 0, 0);
  operator delete(v12);
}

```

## disassembly

```asm
0x18010df2c  mov     [rsp+arg_0], rbx
0x18010df31  mov     [rsp+arg_10], rbp
0x18010df36  mov     [rsp+arg_8], rdx
0x18010df3b  push    rsi
0x18010df3c  push    rdi
0x18010df3d  push    r12
0x18010df3f  push    r14
0x18010df41  push    r15
0x18010df43  sub     rsp, 30h
0x18010df47  mov     ebx, r9d
0x18010df4a  mov     edi, r8d
0x18010df4d  mov     r15, rcx
0x18010df50  call    ?Reset@CDIBSection@Ofc@@QEAAXXZ; Ofc::CDIBSection::Reset(void)
0x18010df55  mov     ecx, edi
0x18010df57  mov     r12d, 1
0x18010df5d  mov     esi, r12d
0x18010df60  shl     esi, cl
0x18010df62  xor     ebp, ebp
0x18010df64  cmp     edi, 8
0x18010df67  cmovg   esi, ebp
0x18010df6a  lea     eax, ds:28h[rsi*4]
0x18010df71  movsxd  rcx, eax; this
0x18010df74  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x18010df79  mov     r14, rax
0x18010df7c  mov     [rsp+58h+arg_8], rax
0x18010df81  mov     dword ptr [rax], 28h ; '('
0x18010df87  mov     [rax+4], ebx
0x18010df8a  mov     ecx, [rsp+58h+arg_20]
0x18010df91  neg     ecx
0x18010df93  mov     [rax+8], ecx
0x18010df96  mov     [rax+0Ch], r12w
0x18010df9b  mov     [rax+10h], rbp
0x18010df9f  mov     [rax+18h], rbp
0x18010dfa3  mov     [rax+20h], rbp
0x18010dfa7  mov     [rax+0Eh], di
0x18010dfab  movsxd  rdi, esi
0x18010dfae  lea     eax, [rbp+4]
0x18010dfb1  mul     rdi
0x18010dfb4  lea     rcx, [rbp-1]
0x18010dfb8  cmovb   rax, rcx
0x18010dfbc  mov     rcx, rax; this
0x18010dfbf  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x18010dfc4  mov     rbx, rax
0x18010dfc7  lea     ecx, [rbp+0Fh]; i
0x18010dfca  call    cs:__imp_GetStockObject
0x18010dfd0  mov     r9, rbx; pPalEntries
0x18010dfd3  mov     r8d, esi; cEntries
0x18010dfd6  xor     edx, edx; iStart
0x18010dfd8  mov     rcx, rax; hpal
0x18010dfdb  call    cs:__imp_GetPaletteEntries
0x18010dfe1  test    esi, esi
0x18010dfe3  jle     short loc_18010E011
0x18010dfe5  lea     rcx, [rbx+1]
0x18010dfe9  mov     rdx, r14
0x18010dfec  sub     rdx, rbx
0x18010dfef  mov     al, [rcx-1]
0x18010dff2  mov     [rcx+rdx+29h], al
0x18010dff6  mov     al, [rcx]
0x18010dff8  mov     [rcx+rdx+28h], al
0x18010dffc  mov     al, [rcx+1]
0x18010dfff  mov     [rcx+rdx+27h], al
0x18010e003  mov     [rcx+rdx+2Ah], bpl
0x18010e008  lea     rcx, [rcx+4]
0x18010e00c  sub     rdi, r12
0x18010e00f  jnz     short loc_18010DFEF
0x18010e011  mov     rcx, rbx; void *
0x18010e014  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18010e019  lea     r9, [r15+8]; ppvBits
0x18010e01d  mov     [rsp+58h+offset], ebp; offset
0x18010e021  mov     [rsp+58h+hSection], rbp; hSection
0x18010e026  xor     r8d, r8d; usage
0x18010e029  mov     rdx, r14; pbmi
0x18010e02c  xor     ecx, ecx; hdc
0x18010e02e  call    cs:__imp_CreateDIBSection
0x18010e034  mov     [r15], rax
0x18010e037  mov     rcx, r14; void *
0x18010e03a  mov     rbx, [rsp+58h+arg_0]
0x18010e03f  mov     rbp, [rsp+58h+arg_10]
0x18010e044  add     rsp, 30h
0x18010e048  pop     r15
0x18010e04a  pop     r14
0x18010e04c  pop     r12
0x18010e04e  pop     rdi
0x18010e04f  pop     rsi
0x18010e050  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
