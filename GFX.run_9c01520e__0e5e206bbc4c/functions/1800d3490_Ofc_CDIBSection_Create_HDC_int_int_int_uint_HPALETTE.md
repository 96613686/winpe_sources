# Ofc::CDIBSection::Create(HDC__ *,int,int,int,uint,HPALETTE__ *)

- ea: `0x1800d3490`
- end: `0x1800d35b9`
- name: `?Create@CDIBSection@Ofc@@QEAAXPEAUHDC__@@HHHIPEAUHPALETTE__@@@Z`
- size: `297`
- prototype: `void __fastcall(Ofc::CDIBSection *__hidden this, HDC, int, int, int, unsigned int, HPALETTE)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800c05c0`
- `0x1800d2150`
- `0x180169c14`

## callees

- `0x180020198`
- `0x180092a58`
- `0x1800d3490`
- `0x1800d35c0`

## import_xrefs

- `GDI32!GetPaletteEntries` at `0x1800d353f`
- `GDI32!GetPaletteEntries` at `0x1800d353f`
- `GDI32!CreateDIBSection` at `0x1800d3592`
- `GDI32!CreateDIBSection` at `0x1800d3592`
- `GDI32!GetStockObject` at `0x1800d352e`
- `GDI32!GetStockObject` at `0x1800d352e`

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
0x1800d3490  mov     [rsp+arg_0], rbx
0x1800d3495  mov     [rsp+arg_10], rbp
0x1800d349a  mov     [rsp+arg_8], rdx
0x1800d349f  push    rsi
0x1800d34a0  push    rdi
0x1800d34a1  push    r12
0x1800d34a3  push    r14
0x1800d34a5  push    r15
0x1800d34a7  sub     rsp, 30h
0x1800d34ab  mov     ebx, r9d
0x1800d34ae  mov     edi, r8d
0x1800d34b1  mov     r15, rcx
0x1800d34b4  call    ?Reset@CDIBSection@Ofc@@QEAAXXZ; Ofc::CDIBSection::Reset(void)
0x1800d34b9  mov     ecx, edi
0x1800d34bb  mov     r12d, 1
0x1800d34c1  mov     esi, r12d
0x1800d34c4  shl     esi, cl
0x1800d34c6  xor     ebp, ebp
0x1800d34c8  cmp     edi, 8
0x1800d34cb  cmovg   esi, ebp
0x1800d34ce  lea     eax, ds:28h[rsi*4]
0x1800d34d5  movsxd  rcx, eax; this
0x1800d34d8  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x1800d34dd  mov     r14, rax
0x1800d34e0  mov     [rsp+58h+arg_8], rax
0x1800d34e5  mov     dword ptr [rax], 28h ; '('
0x1800d34eb  mov     [rax+4], ebx
0x1800d34ee  mov     ecx, [rsp+58h+arg_20]
0x1800d34f5  neg     ecx
0x1800d34f7  mov     [rax+8], ecx
0x1800d34fa  mov     [rax+0Ch], r12w
0x1800d34ff  mov     [rax+10h], rbp
0x1800d3503  mov     [rax+18h], rbp
0x1800d3507  mov     [rax+20h], rbp
0x1800d350b  mov     [rax+0Eh], di
0x1800d350f  movsxd  rdi, esi
0x1800d3512  lea     eax, [rbp+4]
0x1800d3515  mul     rdi
0x1800d3518  lea     rcx, [rbp-1]
0x1800d351c  cmovb   rax, rcx
0x1800d3520  mov     rcx, rax; this
0x1800d3523  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x1800d3528  mov     rbx, rax
0x1800d352b  lea     ecx, [rbp+0Fh]; i
0x1800d352e  call    cs:__imp_GetStockObject
0x1800d3534  mov     r9, rbx; pPalEntries
0x1800d3537  mov     r8d, esi; cEntries
0x1800d353a  xor     edx, edx; iStart
0x1800d353c  mov     rcx, rax; hpal
0x1800d353f  call    cs:__imp_GetPaletteEntries
0x1800d3545  test    esi, esi
0x1800d3547  jle     short loc_1800D3575
0x1800d3549  lea     rcx, [rbx+1]
0x1800d354d  mov     rdx, r14
0x1800d3550  sub     rdx, rbx
0x1800d3553  mov     al, [rcx-1]
0x1800d3556  mov     [rcx+rdx+29h], al
0x1800d355a  mov     al, [rcx]
0x1800d355c  mov     [rcx+rdx+28h], al
0x1800d3560  mov     al, [rcx+1]
0x1800d3563  mov     [rcx+rdx+27h], al
0x1800d3567  mov     [rcx+rdx+2Ah], bpl
0x1800d356c  lea     rcx, [rcx+4]
0x1800d3570  sub     rdi, r12
0x1800d3573  jnz     short loc_1800D3553
0x1800d3575  mov     rcx, rbx; void *
0x1800d3578  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800d357d  lea     r9, [r15+8]; ppvBits
0x1800d3581  mov     [rsp+58h+offset], ebp; offset
0x1800d3585  mov     [rsp+58h+hSection], rbp; hSection
0x1800d358a  xor     r8d, r8d; usage
0x1800d358d  mov     rdx, r14; pbmi
0x1800d3590  xor     ecx, ecx; hdc
0x1800d3592  call    cs:__imp_CreateDIBSection
0x1800d3598  mov     [r15], rax
0x1800d359b  mov     rcx, r14; void *
0x1800d359e  mov     rbx, [rsp+58h+arg_0]
0x1800d35a3  mov     rbp, [rsp+58h+arg_10]
0x1800d35a8  add     rsp, 30h
0x1800d35ac  pop     r15
0x1800d35ae  pop     r14
0x1800d35b0  pop     r12
0x1800d35b2  pop     rdi
0x1800d35b3  pop     rsi
0x1800d35b4  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
