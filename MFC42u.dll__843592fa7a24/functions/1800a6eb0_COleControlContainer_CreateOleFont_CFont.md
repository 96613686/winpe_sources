# COleControlContainer::CreateOleFont(CFont *)

- ea: `0x1800a6eb0`
- end: `0x1800a7039`
- name: `?CreateOleFont@COleControlContainer@@QEAAXPEAVCFont@@@Z`
- size: `393`
- prototype: `void __fastcall(COleControlContainer *__hidden this, struct CFont *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800a72a0`

## callees

- `0x180009550`
- `0x18000a150`
- `0x18000e790`
- `0x18002a0e0`
- `0x1800a6eb0`
- `0x1800a7040`
- `0x1800d1f92`
- `0x1800d1fe0`

## import_xrefs

- `GDI32!GetDeviceCaps` at `0x1800a6fb2`
- `GDI32!GetDeviceCaps` at `0x1800a6fb2`
- `GDI32!GetObjectW` at `0x1800a6f4f`
- `GDI32!GetObjectW` at `0x1800a6f4f`
- `OLEAUT32!__imp_OleCreateFontIndirect` at `0x1800a6feb`
- `OLEAUT32!__imp_OleCreateFontIndirect` at `0x1800a6feb`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall COleControlContainer::CreateOleFont(COleControlContainer *this, struct CFont *a2)
{
  struct CFont *v2; // rbx
  int v4; // ebx
  _QWORD v5[2]; // [rsp+20h] [rbp-89h] BYREF
  struct tagFONTDESC FontDesc; // [rsp+30h] [rbp-79h] BYREF
  _BYTE v7[16]; // [rsp+58h] [rbp-51h] BYREF
  HDC hdc; // [rsp+68h] [rbp-41h]
  _DWORD pv[4]; // [rsp+80h] [rbp-29h] BYREF
  SHORT v10; // [rsp+90h] [rbp-19h]
  unsigned __int8 v11; // [rsp+94h] [rbp-15h]
  unsigned __int8 v12; // [rsp+95h] [rbp-14h]
  unsigned __int8 v13; // [rsp+96h] [rbp-13h]
  unsigned __int8 v14; // [rsp+97h] [rbp-12h]
  char v15; // [rsp+9Ch] [rbp-Dh] BYREF

  v2 = a2;
  v5[1] = 0;
  v5[0] = &CFont::`vftable';
  if ( !a2 || !*((_QWORD *)a2 + 1) )
  {
    if ( !CGdiObject::CreateStockObject((CGdiObject *)v5, 17) && !CGdiObject::CreateStockObject((CGdiObject *)v5, 13) )
    {
      *((_QWORD *)this + 17) = 0;
      goto LABEL_12;
    }
    v2 = (struct CFont *)v5;
  }
  memset_0(pv, 0, 0x5Cu);
  GetObjectW(*((HANDLE *)v2 + 1), 92, pv);
  *(_QWORD *)&FontDesc.cbSizeofstruct = 40;
  FontDesc.cySize.int64 = 0;
  FontDesc.lpstrName = (LPOLESTR)&v15;
  FontDesc.sWeight = v10;
  FontDesc.sCharset = v14;
  FontDesc.fItalic = v11;
  FontDesc.fUnderline = v12;
  FontDesc.fStrikethrough = v13;
  v4 = -pv[0];
  if ( pv[0] > 0 )
    v4 = pv[0];
  CWindowDC::CWindowDC((CWindowDC *)v7, *((struct CWnd **)this + 8));
  FontDesc.cySize.int64 = (unsigned int)(720000 * v4 / GetDeviceCaps(hdc, 90));
  _AfxRelease((struct IUnknown **)this + 17);
  if ( OleCreateFontIndirect(&FontDesc, &IID_IFontDisp, (LPVOID *)this + 17) < 0 )
    *((_QWORD *)this + 17) = 0;
  CWindowDC::~CWindowDC((CWindowDC *)v7);
LABEL_12:
  v5[0] = &CFont::`vftable';
  CGdiObject::~CGdiObject((CGdiObject *)v5);
}

```

## disassembly

```asm
0x1800a6eb0  mov     [rsp-8+arg_10], rbx
0x1800a6eb5  push    rbp
0x1800a6eb6  push    rdi
0x1800a6eb7  push    r15
0x1800a6eb9  lea     rbp, [rsp-47h]
0x1800a6ebe  sub     rsp, 0F0h
0x1800a6ec5  mov     rax, cs:__security_cookie
0x1800a6ecc  xor     rax, rsp
0x1800a6ecf  mov     [rbp+57h+var_20], rax
0x1800a6ed3  mov     rbx, rdx
0x1800a6ed6  mov     rdi, rcx
0x1800a6ed9  mov     [rsp+100h+var_D8], 0
0x1800a6ee2  lea     r15, ??_7CFont@@6B@; const CFont::`vftable'
0x1800a6ee9  mov     [rsp+100h+var_E0], r15
0x1800a6eee  test    rdx, rdx
0x1800a6ef1  jz      short loc_1800A6EFA
0x1800a6ef3  cmp     qword ptr [rdx+8], 0
0x1800a6ef8  jnz     short loc_1800A6F33
0x1800a6efa  mov     edx, 11h; int
0x1800a6eff  lea     rcx, [rsp+100h+var_E0]; this
0x1800a6f04  call    ?CreateStockObject@CGdiObject@@QEAAHH@Z; CGdiObject::CreateStockObject(int)
0x1800a6f09  test    eax, eax
0x1800a6f0b  jnz     short loc_1800A6F2E
0x1800a6f0d  lea     edx, [rax+0Dh]; int
0x1800a6f10  lea     rcx, [rsp+100h+var_E0]; this
0x1800a6f15  call    ?CreateStockObject@CGdiObject@@QEAAHH@Z; CGdiObject::CreateStockObject(int)
0x1800a6f1a  test    eax, eax
0x1800a6f1c  jnz     short loc_1800A6F2E
0x1800a6f1e  mov     qword ptr [rdi+88h], 0
0x1800a6f29  jmp     loc_1800A700A
0x1800a6f2e  lea     rbx, [rsp+100h+var_E0]
0x1800a6f33  xor     edx, edx; Val
0x1800a6f35  lea     r8d, [rdx+5Ch]; Size
0x1800a6f39  lea     rcx, [rbp+57h+pv]; void *
0x1800a6f3d  call    memset_0
0x1800a6f42  lea     r8, [rbp+57h+pv]; pv
0x1800a6f46  mov     edx, 5Ch ; '\'; c
0x1800a6f4b  mov     rcx, [rbx+8]; h
0x1800a6f4f  call    cs:__imp_GetObjectW
0x1800a6f55  mov     qword ptr [rbp+57h+FontDesc.cbSizeofstruct], 28h ; '('
0x1800a6f5d  mov     qword ptr [rbp+57h+FontDesc.cySize], 0
0x1800a6f65  lea     rax, [rbp+57h+var_64]
0x1800a6f69  mov     [rbp+57h+FontDesc.lpstrName], rax
0x1800a6f6d  movzx   eax, [rbp+57h+var_70]
0x1800a6f71  mov     [rbp+57h+FontDesc.sWeight], ax
0x1800a6f75  movzx   eax, [rbp+57h+var_69]
0x1800a6f79  mov     [rbp+57h+FontDesc.sCharset], ax
0x1800a6f7d  movzx   eax, [rbp+57h+var_6C]
0x1800a6f81  mov     [rbp+57h+FontDesc.fItalic], eax
0x1800a6f84  movzx   eax, [rbp+57h+var_6B]
0x1800a6f88  mov     [rbp+57h+FontDesc.fUnderline], eax
0x1800a6f8b  movzx   eax, [rbp+57h+var_6A]
0x1800a6f8f  mov     [rbp+57h+FontDesc.fStrikethrough], eax
0x1800a6f92  mov     ebx, [rbp+57h+pv]
0x1800a6f95  neg     ebx
0x1800a6f97  cmovs   ebx, [rbp+57h+pv]
0x1800a6f9b  mov     rdx, [rdi+40h]; struct CWnd *
0x1800a6f9f  lea     rcx, [rbp+57h+var_A8]; this
0x1800a6fa3  call    ??0CWindowDC@@QEAA@PEAVCWnd@@@Z; CWindowDC::CWindowDC(CWnd *)
0x1800a6fa8  nop
0x1800a6fa9  mov     edx, 5Ah ; 'Z'; index
0x1800a6fae  mov     rcx, [rbp+57h+hdc]; hdc
0x1800a6fb2  call    cs:__imp_GetDeviceCaps
0x1800a6fb8  mov     ecx, eax
0x1800a6fba  imul    eax, ebx, 0AFC80h
0x1800a6fc0  cdq
0x1800a6fc1  idiv    ecx
0x1800a6fc3  mov     dword ptr [rbp+57h+FontDesc.cySize], eax
0x1800a6fc6  mov     dword ptr [rbp+57h+FontDesc.cySize+4], 0
0x1800a6fcd  lea     rcx, [rdi+88h]; struct IUnknown **
0x1800a6fd4  call    ?_AfxRelease@@YAKPEAPEAUIUnknown@@@Z; _AfxRelease(IUnknown * *)
0x1800a6fd9  lea     r8, [rdi+88h]; lplpvObj
0x1800a6fe0  lea     rdx, IID_IFontDisp; riid
0x1800a6fe7  lea     rcx, [rbp+57h+FontDesc]; lpFontDesc
0x1800a6feb  call    cs:__imp_OleCreateFontIndirect
0x1800a6ff1  test    eax, eax
0x1800a6ff3  jns     short loc_1800A7000
0x1800a6ff5  mov     qword ptr [rdi+88h], 0
0x1800a7000  lea     rcx, [rbp+57h+var_A8]; this
0x1800a7004  call    ??1CWindowDC@@UEAA@XZ; CWindowDC::~CWindowDC(void)
0x1800a7009  nop
0x1800a700a  mov     [rsp+100h+var_E0], r15
0x1800a700f  lea     rcx, [rsp+100h+var_E0]; this
0x1800a7014  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x1800a7019  mov     rcx, [rbp+57h+var_20]
0x1800a701d  xor     rcx, rsp; StackCookie
0x1800a7020  call    __security_check_cookie
0x1800a7025  mov     rbx, [rsp+100h+arg_10]
0x1800a702d  add     rsp, 0F0h
0x1800a7034  pop     r15
0x1800a7036  pop     rdi
0x1800a7037  pop     rbp
0x1800a7038  retn
```
