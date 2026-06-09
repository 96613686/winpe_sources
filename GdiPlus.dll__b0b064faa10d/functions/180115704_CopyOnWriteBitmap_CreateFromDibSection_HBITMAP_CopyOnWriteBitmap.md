# CopyOnWriteBitmap::CreateFromDibSection(HBITMAP__ *,CopyOnWriteBitmap * *)

- ea: `0x180115704`
- end: `0x18011593b`
- name: `?CreateFromDibSection@CopyOnWriteBitmap@@CA?AW4Status@@PEAUHBITMAP__@@PEAPEAV1@@Z`
- size: `567`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180115944`

## callees

- `0x1800067bc`
- `0x18000952c`
- `0x18001ec80`
- `0x1800f0e40`
- `0x1800fe680`
- `0x1800ff04c`
- `0x180115704`
- `0x180168478`
- `0x180169010`

## import_xrefs

- `GDI32!GetDIBColorTable` at `0x18011581d`
- `GDI32!GetDIBColorTable` at `0x18011581d`
- `GDI32!DeleteDC` at `0x180115834`
- `GDI32!DeleteDC` at `0x180115834`
- `GDI32!SelectObject` at `0x180115805`
- `GDI32!SelectObject` at `0x18011582b`
- `GDI32!SelectObject` at `0x180115805`
- `GDI32!SelectObject` at `0x18011582b`
- `GDI32!CreateCompatibleDC` at `0x1801157ed`
- `GDI32!CreateCompatibleDC` at `0x1801157ed`
- `GDI32!GetObjectA` at `0x18011576f`
- `GDI32!GetObjectA` at `0x18011576f`

## pseudocode

```c
__int64 __fastcall CopyOnWriteBitmap::CreateFromDibSection(void *a1, CopyOnWriteBitmap **a2)
{
  unsigned int v4; // r14d
  unsigned int v5; // esi
  HDC CompatibleDC; // rax
  HDC v7; // r12
  HGDIOBJ v8; // rdi
  UINT DIBColorTable; // ebx
  void *v11; // rax
  void *v12; // rbx
  CopyOnWriteBitmap *v13; // rax
  CopyOnWriteBitmap *v14; // rax
  _BYTE pv[4]; // [rsp+20h] [rbp-E0h] BYREF
  int v16; // [rsp+24h] [rbp-DCh]
  int v17; // [rsp+28h] [rbp-D8h]
  unsigned __int16 v18; // [rsp+30h] [rbp-D0h]
  unsigned __int16 v19; // [rsp+32h] [rbp-CEh]
  void *Src; // [rsp+38h] [rbp-C8h]
  __int64 v21; // [rsp+40h] [rbp-C0h]
  LONG v22; // [rsp+48h] [rbp-B8h]
  WORD v23; // [rsp+4Ch] [rbp-B4h]
  WORD v24; // [rsp+4Eh] [rbp-B2h]
  DWORD v25; // [rsp+50h] [rbp-B0h]
  _DWORD Size[15]; // [rsp+54h] [rbp-ACh]
  struct tagBITMAPINFO v27; // [rsp+90h] [rbp-70h] BYREF
  int v28; // [rsp+BCh] [rbp-44h]
  int v29; // [rsp+C0h] [rbp-40h]

  v4 = 7;
  memset_0(pv, 0, 0x68u);
  memset_0(&v27, 0, 0x428u);
  if ( GetObjectA(a1, 104, pv) != 104 )
    return v4;
  v5 = Size[0];
  if ( !Size[0] )
    v5 = v17 * v18 * (((v16 * v19 + 31) >> 3) & 0xFFFFFFFC);
  v27.bmiHeader.biHeight = v22;
  *(_QWORD *)&v27.bmiHeader.biSize = v21;
  v27.bmiHeader.biPlanes = v23;
  v27.bmiHeader.biBitCount = v24;
  v27.bmiHeader.biCompression = v25;
  v27.bmiHeader.biSizeImage = Size[0];
  *(_OWORD *)&v27.bmiHeader.biXPelsPerMeter = *(_OWORD *)&Size[1];
  if ( v24 > 8u )
  {
    if ( v24 == 16 && v25 == 3 )
    {
      v27.bmiColors[0] = (RGBQUAD)Size[5];
      v28 = Size[6];
      v29 = Size[7];
    }
  }
  else
  {
    CompatibleDC = CreateCompatibleDC(0);
    v7 = CompatibleDC;
    if ( CompatibleDC )
    {
      v8 = SelectObject(CompatibleDC, a1);
      DIBColorTable = GetDIBColorTable(v7, 0, 0x100u, v27.bmiColors);
      SelectObject(v7, v8);
      DeleteDC(v7);
      if ( !DIBColorTable )
        return v4;
    }
  }
  v11 = (void *)GpMallocEx(v5, 0);
  v12 = v11;
  if ( v11 )
  {
    memcpy_0(v11, Src, v5);
    v13 = (CopyOnWriteBitmap *)GpMallocEx(264, 0);
    if ( v13 )
    {
      v14 = CopyOnWriteBitmap::CopyOnWriteBitmap(v13, &v27, v12, 1);
      *a2 = v14;
      if ( v14 )
      {
        if ( (*(unsigned int (__fastcall **)(CopyOnWriteBitmap *))(*(_QWORD *)v14 + 16LL))(v14) )
        {
          return 0;
        }
        else
        {
          CopyOnWriteBitmap::Dispose(*a2);
          *a2 = 0;
          return 2;
        }
      }
    }
    else
    {
      *a2 = 0;
    }
    GpFree(v12);
    return 3;
  }
  return 3;
}

```

## disassembly

```asm
0x180115704  mov     [rsp-8+arg_10], rbx
0x180115709  mov     [rsp-8+arg_18], rsi
0x18011570e  push    rbp
0x18011570f  push    rdi
0x180115710  push    r12
0x180115712  push    r14
0x180115714  push    r15
0x180115716  lea     rbp, [rsp-3D0h]
0x18011571e  sub     rsp, 4D0h
0x180115725  mov     rax, cs:__security_cookie
0x18011572c  xor     rax, rsp
0x18011572f  mov     [rbp+3F0h+var_30], rax
0x180115736  mov     edi, 68h ; 'h'
0x18011573b  mov     r15, rdx
0x18011573e  mov     rbx, rcx
0x180115741  mov     r8d, edi; Size
0x180115744  xor     edx, edx; Val
0x180115746  lea     rcx, [rsp+4F0h+pv]; void *
0x18011574b  lea     r14d, [rdi-61h]
0x18011574f  call    memset_0
0x180115754  xor     edx, edx; Val
0x180115756  lea     rcx, [rbp+3F0h+var_460]; void *
0x18011575a  mov     r8d, 428h; Size
0x180115760  call    memset_0
0x180115765  lea     r8, [rsp+4F0h+pv]; pv
0x18011576a  mov     edx, edi; c
0x18011576c  mov     rcx, rbx; h
0x18011576f  call    cs:__imp_GetObjectA
0x180115775  cmp     eax, edi
0x180115777  jnz     loc_18011583E
0x18011577d  mov     ecx, dword ptr [rsp+4F0h+Size]
0x180115781  mov     esi, ecx
0x180115783  test    ecx, ecx
0x180115785  jnz     short loc_1801157A7
0x180115787  movzx   esi, [rsp+4F0h+var_4BE]
0x18011578c  imul    esi, [rsp+4F0h+var_4CC]
0x180115791  movzx   eax, [rsp+4F0h+var_4C0]
0x180115796  add     esi, 1Fh
0x180115799  sar     esi, 3
0x18011579c  and     esi, 0FFFFFFFCh
0x18011579f  imul    esi, eax
0x1801157a2  imul    esi, [rsp+4F0h+var_4C8]
0x1801157a7  mov     eax, [rsp+4F0h+var_4A8]
0x1801157ab  movsd   xmm0, [rsp+4F0h+var_4B0]
0x1801157b1  mov     r8d, [rsp+4F0h+var_4A0]
0x1801157b6  mov     [rbp+3F0h+var_460.bmiHeader.biHeight], eax
0x1801157b9  movzx   eax, [rsp+4F0h+var_4A4]
0x1801157be  movsd   qword ptr [rbp+3F0h+var_460.bmiHeader.biSize], xmm0
0x1801157c3  movups  xmm0, xmmword ptr [rsp+4F0h+Size+4]
0x1801157c8  mov     [rbp+3F0h+var_460.bmiHeader.biPlanes], ax
0x1801157cc  movzx   eax, [rsp+4F0h+var_4A2]
0x1801157d1  mov     [rbp+3F0h+var_460.bmiHeader.biBitCount], ax
0x1801157d5  mov     [rbp+3F0h+var_460.bmiHeader.biCompression], r8d
0x1801157d9  mov     [rbp+3F0h+var_460.bmiHeader.biSizeImage], ecx
0x1801157dc  movdqu  xmmword ptr [rbp+3F0h+var_460.bmiHeader.biXPelsPerMeter], xmm0
0x1801157e1  cmp     ax, 8
0x1801157e5  ja      loc_18011586C
0x1801157eb  xor     ecx, ecx; hdc
0x1801157ed  call    cs:__imp_CreateCompatibleDC
0x1801157f3  mov     r12, rax
0x1801157f6  test    rax, rax
0x1801157f9  jz      loc_18011588D
0x1801157ff  mov     rdx, rbx; h
0x180115802  mov     rcx, rax; hdc
0x180115805  call    cs:__imp_SelectObject
0x18011580b  lea     r9, [rbp+3F0h+var_460.bmiColors]; prgbq
0x18011580f  xor     edx, edx; iStart
0x180115811  mov     r8d, 100h; cEntries
0x180115817  mov     rcx, r12; hdc
0x18011581a  mov     rdi, rax
0x18011581d  call    cs:__imp_GetDIBColorTable
0x180115823  mov     rdx, rdi; h
0x180115826  mov     rcx, r12; hdc
0x180115829  mov     ebx, eax
0x18011582b  call    cs:__imp_SelectObject
0x180115831  mov     rcx, r12; hdc
0x180115834  call    cs:__imp_DeleteDC
0x18011583a  test    ebx, ebx
0x18011583c  jnz     short loc_18011588D
0x18011583e  mov     eax, r14d
0x180115841  mov     rcx, [rbp+3F0h+var_30]
0x180115848  xor     rcx, rsp; StackCookie
0x18011584b  call    __security_check_cookie
0x180115850  lea     r11, [rsp+4F0h+var_20]
0x180115858  mov     rbx, [r11+40h]
0x18011585c  mov     rsi, [r11+48h]
0x180115860  mov     rsp, r11
0x180115863  pop     r15
0x180115865  pop     r14
0x180115867  pop     r12
0x180115869  pop     rdi
0x18011586a  pop     rbp
0x18011586b  retn
0x18011586c  cmp     ax, 10h
0x180115870  jnz     short loc_18011588D
0x180115872  cmp     r8d, 3
0x180115876  jnz     short loc_18011588D
0x180115878  mov     eax, [rsp+4F0h+var_488]
0x18011587c  mov     dword ptr [rbp+3F0h+var_460.bmiColors.rgbBlue], eax
0x18011587f  mov     eax, [rsp+4F0h+var_484]
0x180115883  mov     [rbp+3F0h+var_434], eax
0x180115886  mov     eax, [rsp+4F0h+var_480]
0x18011588a  mov     [rbp+3F0h+var_430], eax
0x18011588d  xor     edx, edx
0x18011588f  mov     ecx, esi
0x180115891  mov     edi, esi
0x180115893  call    GpMallocEx
0x180115898  mov     rbx, rax
0x18011589b  test    rax, rax
0x18011589e  jz      loc_180115931
0x1801158a4  mov     rdx, [rsp+4F0h+Src]; Src
0x1801158a9  mov     r8d, edi; Size
0x1801158ac  mov     rcx, rax; void *
0x1801158af  call    memcpy_0
0x1801158b4  xor     edx, edx
0x1801158b6  mov     ecx, 108h
0x1801158bb  call    GpMallocEx
0x1801158c0  test    rax, rax
0x1801158c3  jz      short loc_180115917
0x1801158c5  mov     r9d, 1; int
0x1801158cb  lea     rdx, [rbp+3F0h+var_460]; struct tagBITMAPINFO *
0x1801158cf  mov     r8, rbx; void *
0x1801158d2  mov     rcx, rax; this
0x1801158d5  call    ??0CopyOnWriteBitmap@@AEAA@PEAUtagBITMAPINFO@@PEAXH@Z; CopyOnWriteBitmap::CopyOnWriteBitmap(tagBITMAPINFO *,void *,int)
0x1801158da  mov     [r15], rax
0x1801158dd  mov     rcx, rax
0x1801158e0  test    rax, rax
0x1801158e3  jz      short loc_18011591E
0x1801158e5  mov     rax, [rax]
0x1801158e8  mov     rax, [rax+10h]
0x1801158ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801158f1  test    eax, eax
0x1801158f3  jz      short loc_1801158FD
0x1801158f5  xor     r14d, r14d
0x1801158f8  jmp     loc_18011583E
0x1801158fd  mov     rcx, [r15]; this
0x180115900  call    ?Dispose@CopyOnWriteBitmap@@AEAAXXZ; CopyOnWriteBitmap::Dispose(void)
0x180115905  mov     qword ptr [r15], 0
0x18011590c  mov     r14d, 2
0x180115912  jmp     loc_18011583E
0x180115917  mov     qword ptr [r15], 0
0x18011591e  mov     rcx, rbx
0x180115921  call    GpFree
0x180115926  mov     r14d, 3
0x18011592c  jmp     loc_18011583E
0x180115931  mov     eax, 3
0x180115936  jmp     loc_180115841
```
