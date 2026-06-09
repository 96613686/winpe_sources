# CInkStrokeDisp::GetRectangleIntersections(IInkRectangle *,tagVARIANT *)

- ea: `0x1800d0130`
- end: `0x1800d02fe`
- name: `?GetRectangleIntersections@CInkStrokeDisp@@UEAAJPEAUIInkRectangle@@PEAUtagVARIANT@@@Z`
- size: `462`
- prototype: `int(CInkStrokeDisp *__hidden this, struct IInkRectangle *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180001c20`
- `0x18000b78c`
- `0x180036888`
- `0x18007e0a4`
- `0x1800acf04`
- `0x1800d0130`
- `0x180104f30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800d02cd`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800d02da`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800d02cd`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800d02da`
- `OLEAUT32!__imp_VariantInit` at `0x1800d01af`
- `OLEAUT32!__imp_VariantInit` at `0x1800d01af`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800d02a7`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800d02a7`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800d0257`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800d0257`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800d0288`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800d0288`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800d0241`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800d0241`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800d0193`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800d0193`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall CInkStrokeDisp::GetRectangleIntersections(
        struct CStrokeWithInk **this,
        struct IInkRectangle *a2,
        struct tagVARIANT *a3)
{
  HANDLE *v6; // rsi
  HRESULT RectangleIntersections; // ebx
  SAFEARRAY *Vector; // rax
  SAFEARRAY *v9; // rdi
  HRESULT v10; // eax
  DWORD dwindex; // [rsp+30h] [rbp-68h] BYREF
  void *ppvData; // [rsp+38h] [rbp-60h] BYREF
  _BYTE v14[8]; // [rsp+40h] [rbp-58h] BYREF
  char *v15; // [rsp+48h] [rbp-50h]
  struct tagRECT v16; // [rsp+50h] [rbp-48h] BYREF

  ppvData = (void *)((unsigned __int64)(this + 3) & -(__int64)(this != (struct CStrokeWithInk **)8));
  dwindex = 0;
  v6 = (HANDLE *)((char *)ppvData + 8);
  v15 = (char *)ppvData + 8;
  CoWaitForMultipleHandles(0, 0xFFFFFFFF, 1u, (LPHANDLE)ppvData + 1, &dwindex);
  if ( a2 && a3 )
  {
    VariantInit(a3);
    RectangleIntersections = ValidateStroke(this[6]);
    if ( RectangleIntersections >= 0 )
    {
      CIRect::CIRect((CIRect *)v14, a2);
      CIRect::GetRect((CIRect *)v14, &v16);
      dwindex = 0;
      RectangleIntersections = InkStroke_GetRectangleIntersections(
                                 *(CInkStroke **)(*((_QWORD *)this[6] + 2) + 16LL),
                                 &v16);
      if ( RectangleIntersections >= 0 )
      {
        ppvData = 0;
        if ( 2 * dwindex >= 2 * (unsigned __int64)dwindex )
        {
          Vector = SafeArrayCreateVector(4u, 0, 2 * dwindex);
          v9 = Vector;
          if ( Vector )
          {
            RectangleIntersections = SafeArrayAccessData(Vector, &ppvData);
            if ( RectangleIntersections < 0
              || (RectangleIntersections = InkStroke_GetRectangleIntersections(
                                             *(CInkStroke **)(*((_QWORD *)this[6] + 2) + 16LL),
                                             &v16),
                  v10 = SafeArrayUnaccessData(v9),
                  RectangleIntersections < 0)
              || (RectangleIntersections = v10, v10 < 0) )
            {
              SafeArrayDestroy(v9);
            }
            else
            {
              a3->vt = 8196;
              a3->llVal = (LONGLONG)v9;
            }
          }
          else
          {
            RectangleIntersections = -2147024882;
          }
        }
        else
        {
          RectangleIntersections = -2147418113;
        }
      }
      ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(v14);
    }
    ReleaseMutex(*v6);
    return (unsigned int)RectangleIntersections;
  }
  else
  {
    ReleaseMutex(*v6);
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x1800d0130  push    rbx
0x1800d0132  push    rsi
0x1800d0133  push    rdi
0x1800d0134  push    r14
0x1800d0136  push    r15
0x1800d0138  sub     rsp, 70h
0x1800d013c  mov     rax, cs:__security_cookie
0x1800d0143  xor     rax, rsp
0x1800d0146  mov     [rsp+98h+var_38], rax
0x1800d014b  mov     r14, r8
0x1800d014e  mov     rdi, rdx
0x1800d0151  mov     r15, rcx
0x1800d0154  lea     rax, [rcx-8]
0x1800d0158  lea     rdx, [rcx+18h]
0x1800d015c  neg     rax
0x1800d015f  sbb     r9, r9
0x1800d0162  and     r9, rdx
0x1800d0165  mov     [rsp+98h+ppvData], r9
0x1800d016a  mov     [rsp+98h+dwindex], 0
0x1800d0172  lea     rsi, [r9+8]
0x1800d0176  mov     [rsp+98h+var_50], rsi
0x1800d017b  lea     rax, [rsp+98h+dwindex]
0x1800d0180  mov     [rsp+98h+lpdwindex], rax; lpdwindex
0x1800d0185  mov     r9, rsi; pHandles
0x1800d0188  mov     r8d, 1; cHandles
0x1800d018e  or      edx, 0FFFFFFFFh; dwTimeout
0x1800d0191  xor     ecx, ecx; dwFlags
0x1800d0193  call    cs:__imp_CoWaitForMultipleHandles
0x1800d0199  nop
0x1800d019a  test    rdi, rdi
0x1800d019d  jz      loc_1800D02D7
0x1800d01a3  test    r14, r14
0x1800d01a6  jz      loc_1800D02D7
0x1800d01ac  mov     rcx, r14; pvarg
0x1800d01af  call    cs:__imp_VariantInit
0x1800d01b5  mov     rcx, [r15+30h]; struct CStrokeWithInk *
0x1800d01b9  call    ?ValidateStroke@@YAJPEAVCStrokeWithInk@@@Z; ValidateStroke(CStrokeWithInk *)
0x1800d01be  mov     ebx, eax
0x1800d01c0  test    eax, eax
0x1800d01c2  js      loc_1800D02BF
0x1800d01c8  mov     rdx, rdi; struct IInkRectangle *
0x1800d01cb  lea     rcx, [rsp+98h+var_58]; this
0x1800d01d0  call    ??0CIRect@@QEAA@PEAUIInkRectangle@@@Z; CIRect::CIRect(IInkRectangle *)
0x1800d01d5  nop
0x1800d01d6  lea     rdx, [rsp+98h+var_48]; retstr
0x1800d01db  lea     rcx, [rsp+98h+var_58]; this
0x1800d01e0  call    ?GetRect@CIRect@@QEBA?AUtagRECT@@XZ; CIRect::GetRect(void)
0x1800d01e5  mov     [rsp+98h+dwindex], 0
0x1800d01ed  mov     rax, [r15+30h]
0x1800d01f1  mov     rcx, [rax+10h]
0x1800d01f5  xor     r9d, r9d
0x1800d01f8  lea     r8, [rsp+98h+dwindex]
0x1800d01fd  lea     rdx, [rsp+98h+var_48]; struct tagRECT *
0x1800d0202  mov     rcx, [rcx+10h]; this
0x1800d0206  call    InkStroke_GetRectangleIntersections
0x1800d020b  mov     ebx, eax
0x1800d020d  test    eax, eax
0x1800d020f  js      loc_1800D02B4
0x1800d0215  mov     [rsp+98h+ppvData], 0
0x1800d021e  mov     eax, [rsp+98h+dwindex]
0x1800d0222  lea     r8d, [rax+rax]; cElements
0x1800d0226  mov     ecx, eax
0x1800d0228  add     rcx, rcx
0x1800d022b  mov     eax, r8d
0x1800d022e  cmp     rax, rcx
0x1800d0231  jnb     short loc_1800D023A
0x1800d0233  mov     ebx, 8000FFFFh
0x1800d0238  jmp     short loc_1800D02B4
0x1800d023a  mov     ecx, 4; vt
0x1800d023f  xor     edx, edx; lLbound
0x1800d0241  call    cs:__imp_SafeArrayCreateVector
0x1800d0247  mov     rdi, rax
0x1800d024a  test    rax, rax
0x1800d024d  jz      short loc_1800D02AF
0x1800d024f  lea     rdx, [rsp+98h+ppvData]; ppvData
0x1800d0254  mov     rcx, rax; psa
0x1800d0257  call    cs:__imp_SafeArrayAccessData
0x1800d025d  mov     ebx, eax
0x1800d025f  test    eax, eax
0x1800d0261  js      short loc_1800D02A4
0x1800d0263  mov     rcx, [r15+30h]
0x1800d0267  mov     rcx, [rcx+10h]
0x1800d026b  mov     r9, [rsp+98h+ppvData]
0x1800d0270  lea     r8, [rsp+98h+dwindex]
0x1800d0275  lea     rdx, [rsp+98h+var_48]; struct tagRECT *
0x1800d027a  mov     rcx, [rcx+10h]; this
0x1800d027e  call    InkStroke_GetRectangleIntersections
0x1800d0283  mov     ebx, eax
0x1800d0285  mov     rcx, rdi; psa
0x1800d0288  call    cs:__imp_SafeArrayUnaccessData
0x1800d028e  test    ebx, ebx
0x1800d0290  js      short loc_1800D02A4
0x1800d0292  mov     ebx, eax
0x1800d0294  test    eax, eax
0x1800d0296  js      short loc_1800D02A4
0x1800d0298  mov     word ptr [r14], 2004h
0x1800d029e  mov     [r14+8], rdi
0x1800d02a2  jmp     short loc_1800D02B4
0x1800d02a4  mov     rcx, rdi; psa
0x1800d02a7  call    cs:__imp_SafeArrayDestroy
0x1800d02ad  jmp     short loc_1800D02B4
0x1800d02af  mov     ebx, 8007000Eh
0x1800d02b4  lea     rcx, [rsp+98h+var_58]; void *
0x1800d02b9  call    ??1?$CComPtr@UITablet2@@@ATL@@QEAA@XZ; ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(void)
0x1800d02be  nop
0x1800d02bf  jmp     short loc_1800D02CA
0x1800d02c1  mov     ebx, [rsp+98h+dwindex]
0x1800d02c5  mov     rsi, [rsp+98h+var_50]
0x1800d02ca  mov     rcx, [rsi]; hMutex
0x1800d02cd  call    cs:__imp_ReleaseMutex
0x1800d02d3  mov     eax, ebx
0x1800d02d5  jmp     short loc_1800D02E5
0x1800d02d7  mov     rcx, [rsi]; hMutex
0x1800d02da  call    cs:__imp_ReleaseMutex
0x1800d02e0  mov     eax, 80004003h
0x1800d02e5  mov     rcx, [rsp+98h+var_38]
0x1800d02ea  xor     rcx, rsp; StackCookie
0x1800d02ed  call    __security_check_cookie
0x1800d02f2  add     rsp, 70h
0x1800d02f6  pop     r15
0x1800d02f8  pop     r14
0x1800d02fa  pop     rdi
0x1800d02fb  pop     rsi
0x1800d02fc  pop     rbx
0x1800d02fd  retn
```
