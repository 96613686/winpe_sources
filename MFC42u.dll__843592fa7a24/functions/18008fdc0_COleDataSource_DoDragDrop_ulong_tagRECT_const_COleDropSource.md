# COleDataSource::DoDragDrop(ulong,tagRECT const *,COleDropSource *)

- ea: `0x18008fdc0`
- end: `0x18008ff0b`
- name: `?DoDragDrop@COleDataSource@@QEAAKKPEBUtagRECT@@PEAVCOleDropSource@@@Z`
- size: `331`
- prototype: `unsigned int __fastcall(COleDataSource *__hidden this, DWORD dwOKEffects, RECT *lprcSrc, struct COleDropSource *)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x180086050`
- `0x18009a470`

## callees

- `0x180014a00`
- `0x180017960`
- `0x18001fdf0`
- `0x180041c00`
- `0x18008fcd0`
- `0x18008fdc0`
- `0x1800d1fe0`
- `0x1800d7010`

## import_xrefs

- `USER32!CopyRect` at `0x18008fe19`
- `USER32!CopyRect` at `0x18008fe19`
- `USER32!GetCursorPos` at `0x18008fe26`
- `USER32!GetCursorPos` at `0x18008fe26`
- `USER32!InflateRect` at `0x18008fe75`
- `USER32!InflateRect` at `0x18008fe75`
- `USER32!SetRect` at `0x18008fe41`
- `USER32!SetRect` at `0x18008fe41`
- `USER32!IsRectEmpty` at `0x18008fe5f`
- `USER32!IsRectEmpty` at `0x18008fe5f`
- `OLE32!DoDragDrop` at `0x18008fed7`
- `OLE32!DoDragDrop` at `0x18008fed7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall COleDataSource::DoDragDrop(
        COleDataSource *this,
        DWORD dwOKEffects,
        RECT *lprcSrc,
        struct COleDropSource *a4)
{
  CCmdTarget *v8; // rdi
  unsigned int (__fastcall *v9)(CCmdTarget *, struct CWnd *); // rbx
  struct CWnd *MainWnd; // rax
  DWORD v11; // ebx
  IDataObject *Interface; // rbx
  IDropSource *v13; // rax
  DWORD pdwEffect; // [rsp+30h] [rbp-B8h] BYREF
  struct tagPOINT Point; // [rsp+38h] [rbp-B0h] BYREF
  _BYTE v17[112]; // [rsp+40h] [rbp-A8h] BYREF

  COleDropSource::COleDropSource((COleDropSource *)v17);
  v8 = (CCmdTarget *)v17;
  if ( a4 )
    v8 = a4;
  *((_DWORD *)v8 + 22) = 0;
  if ( lprcSrc )
  {
    CopyRect((LPRECT)((char *)v8 + 72), lprcSrc);
  }
  else
  {
    GetCursorPos(&Point);
    SetRect((LPRECT)((char *)v8 + 72), Point.x, Point.y, Point.x, Point.y);
  }
  if ( (unsigned int)CRect::IsRectNull((CCmdTarget *)((char *)v8 + 72)) )
  {
    *((_DWORD *)v8 + 22) = 1;
  }
  else if ( IsRectEmpty((const RECT *)((char *)v8 + 72)) )
  {
    InflateRect((LPRECT)((char *)v8 + 72), COleDropSource::nDragMinDist, COleDropSource::nDragMinDist);
  }
  v9 = *(unsigned int (__fastcall **)(CCmdTarget *, struct CWnd *))(*(_QWORD *)v8 + 192LL);
  MainWnd = AfxGetMainWnd();
  if ( v9(v8, MainWnd) )
  {
    Interface = (IDataObject *)CCmdTarget::GetInterface(this, &IID_IDataObject);
    v13 = (IDropSource *)CCmdTarget::GetInterface(v8, &IID_IDropSource);
    pdwEffect = 0;
    DoDragDrop(Interface, v13, dwOKEffects, &pdwEffect);
    v11 = pdwEffect;
  }
  else
  {
    v11 = 0;
  }
  CCmdTarget::~CCmdTarget((CCmdTarget *)v17);
  return v11;
}

```

## disassembly

```asm
0x18008fdc0  push    rbx
0x18008fdc2  push    rbp
0x18008fdc3  push    rsi
0x18008fdc4  push    rdi
0x18008fdc5  push    r14
0x18008fdc7  sub     rsp, 0C0h
0x18008fdce  mov     rax, cs:__security_cookie
0x18008fdd5  xor     rax, rsp
0x18008fdd8  mov     [rsp+0E8h+var_38], rax
0x18008fde0  mov     rbx, r9
0x18008fde3  mov     rsi, r8
0x18008fde6  mov     r14d, edx
0x18008fde9  mov     rbp, rcx
0x18008fdec  lea     rcx, [rsp+0E8h+var_A8]; this
0x18008fdf1  call    ??0COleDropSource@@QEAA@XZ; COleDropSource::COleDropSource(void)
0x18008fdf6  nop
0x18008fdf7  lea     rdi, [rsp+0E8h+var_A8]
0x18008fdfc  test    rbx, rbx
0x18008fdff  cmovnz  rdi, rbx
0x18008fe03  mov     dword ptr [rdi+58h], 0
0x18008fe0a  lea     rbx, [rdi+48h]
0x18008fe0e  test    rsi, rsi
0x18008fe11  jz      short loc_18008FE21
0x18008fe13  mov     rdx, rsi; lprcSrc
0x18008fe16  mov     rcx, rbx; lprcDst
0x18008fe19  call    cs:__imp_CopyRect
0x18008fe1f  jmp     short loc_18008FE47
0x18008fe21  lea     rcx, [rsp+0E8h+Point]; lpPoint
0x18008fe26  call    cs:__imp_GetCursorPos
0x18008fe2c  mov     r8d, [rsp+0E8h+Point.y]; yTop
0x18008fe31  mov     [rsp+0E8h+yBottom], r8d; yBottom
0x18008fe36  mov     rdx, qword ptr [rsp+0E8h+Point.x]; xLeft
0x18008fe3b  mov     r9d, edx; xRight
0x18008fe3e  mov     rcx, rbx; lprc
0x18008fe41  call    cs:__imp_SetRect
0x18008fe47  mov     rcx, rbx; this
0x18008fe4a  call    ?IsRectNull@CRect@@QEBAHXZ; CRect::IsRectNull(void)
0x18008fe4f  test    eax, eax
0x18008fe51  jz      short loc_18008FE5C
0x18008fe53  mov     dword ptr [rdi+58h], 1
0x18008fe5a  jmp     short loc_18008FE7B
0x18008fe5c  mov     rcx, rbx; lprc
0x18008fe5f  call    cs:__imp_IsRectEmpty
0x18008fe65  test    eax, eax
0x18008fe67  jz      short loc_18008FE7B
0x18008fe69  mov     edx, cs:?nDragMinDist@COleDropSource@@1IA; dx
0x18008fe6f  mov     r8d, edx; dy
0x18008fe72  mov     rcx, rbx; lprc
0x18008fe75  call    cs:__imp_InflateRect
0x18008fe7b  mov     rax, [rdi]
0x18008fe7e  mov     rbx, [rax+0C0h]
0x18008fe85  call    ?AfxGetMainWnd@@YAPEAVCWnd@@XZ; AfxGetMainWnd(void)
0x18008fe8a  mov     rdx, rax
0x18008fe8d  mov     rcx, rdi
0x18008fe90  mov     rax, rbx
0x18008fe93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008fe98  test    eax, eax
0x18008fe9a  jnz     short loc_18008FEA0
0x18008fe9c  xor     ebx, ebx
0x18008fe9e  jmp     short loc_18008FEE1
0x18008fea0  lea     rdx, IID_IDataObject; void *
0x18008fea7  mov     rcx, rbp; this
0x18008feaa  call    ?GetInterface@CCmdTarget@@QEAAPEAUIUnknown@@PEBX@Z; CCmdTarget::GetInterface(void const *)
0x18008feaf  mov     rbx, rax
0x18008feb2  lea     rdx, IID_IDropSource; void *
0x18008feb9  mov     rcx, rdi; this
0x18008febc  call    ?GetInterface@CCmdTarget@@QEAAPEAUIUnknown@@PEBX@Z; CCmdTarget::GetInterface(void const *)
0x18008fec1  mov     [rsp+0E8h+pdwEffect], 0
0x18008fec9  lea     r9, [rsp+0E8h+pdwEffect]; pdwEffect
0x18008fece  mov     r8d, r14d; dwOKEffects
0x18008fed1  mov     rdx, rax; pDropSource
0x18008fed4  mov     rcx, rbx; pDataObj
0x18008fed7  call    cs:__imp_DoDragDrop
0x18008fedd  mov     ebx, [rsp+0E8h+pdwEffect]
0x18008fee1  lea     rcx, [rsp+0E8h+var_A8]; this
0x18008fee6  call    ??1CCmdTarget@@UEAA@XZ; CCmdTarget::~CCmdTarget(void)
0x18008feeb  mov     eax, ebx
0x18008feed  mov     rcx, [rsp+0E8h+var_38]
0x18008fef5  xor     rcx, rsp; StackCookie
0x18008fef8  call    __security_check_cookie
0x18008fefd  add     rsp, 0C0h
0x18008ff04  pop     r14
0x18008ff06  pop     rdi
0x18008ff07  pop     rsi
0x18008ff08  pop     rbp
0x18008ff09  pop     rbx
0x18008ff0a  retn
```
