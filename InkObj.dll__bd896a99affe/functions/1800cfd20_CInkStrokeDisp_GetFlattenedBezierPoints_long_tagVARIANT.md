# CInkStrokeDisp::GetFlattenedBezierPoints(long,tagVARIANT *)

- ea: `0x1800cfd20`
- end: `0x1800cfeca`
- name: `?GetFlattenedBezierPoints@CInkStrokeDisp@@UEAAJJPEAUtagVARIANT@@@Z`
- size: `426`
- prototype: `int(CInkStrokeDisp *__hidden this, int, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000b78c`
- `0x18007dc88`
- `0x1800cfd20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800cfd7f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800cfea0`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800cfead`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800cfd7f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800cfea0`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800cfead`
- `OLEAUT32!__imp_VariantInit` at `0x1800cfd9b`
- `OLEAUT32!__imp_VariantInit` at `0x1800cfd9b`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800cfe7f`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800cfe7f`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800cfe2c`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800cfe2c`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800cfe5b`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800cfe5b`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800cfe16`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800cfe16`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800cfd71`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800cfd71`

## pseudocode

```c
__int64 __fastcall CInkStrokeDisp::GetFlattenedBezierPoints(
        struct CStrokeWithInk **this,
        signed int a2,
        struct tagVARIANT *a3)
{
  __int64 v6; // rdi
  __int64 v8; // rcx
  HRESULT v9; // ebx
  HRESULT FlattenedBezierPoints; // eax
  SAFEARRAY *Vector; // rax
  SAFEARRAY *v12; // rsi
  HRESULT v13; // eax
  void *ppvData; // [rsp+60h] [rbp+8h] BYREF
  DWORD dwindex; // [rsp+68h] [rbp+10h] BYREF
  __int64 v16; // [rsp+78h] [rbp+20h]

  dwindex = 0;
  v6 = (__int64)(this + 4);
  if ( this == (struct CStrokeWithInk **)8 )
    v6 = 8;
  v16 = v6;
  CoWaitForMultipleHandles(0, 0xFFFFFFFF, 1u, (LPHANDLE)v6, &dwindex);
  if ( a2 < 0 )
  {
    ReleaseMutex(*(HANDLE *)v6);
    return 2147942487LL;
  }
  if ( a3 )
  {
    VariantInit(a3);
    v9 = ValidateStroke(this[6]);
    if ( v9 >= 0 )
    {
      dwindex = 0;
      FlattenedBezierPoints = InkStroke_GetFlattenedBezierPoints(
                                *(CInkStroke **)(*(_QWORD *)(v8 + 16) + 16LL),
                                a2,
                                &dwindex,
                                0);
      v9 = FlattenedBezierPoints;
      if ( FlattenedBezierPoints == 1 )
        goto LABEL_18;
      if ( !FlattenedBezierPoints )
      {
        ppvData = 0;
        if ( 2 * dwindex < 2 * (unsigned __int64)dwindex )
        {
          v9 = -2147418113;
          goto LABEL_20;
        }
        Vector = SafeArrayCreateVector(3u, 0, 2 * dwindex);
        v12 = Vector;
        if ( !Vector )
        {
          v9 = -2147024882;
          goto LABEL_20;
        }
        v9 = SafeArrayAccessData(Vector, &ppvData);
        if ( v9 >= 0 )
        {
          v9 = InkStroke_GetFlattenedBezierPoints(
                 *(CInkStroke **)(*((_QWORD *)this[6] + 2) + 16LL),
                 a2,
                 &dwindex,
                 (struct tagPOINT *)ppvData);
          v13 = SafeArrayUnaccessData(v12);
          if ( v9 >= 0 )
          {
            v9 = v13;
            if ( v13 >= 0 && v13 != 1 )
            {
              a3->vt = 8195;
              a3->llVal = (LONGLONG)v12;
              goto LABEL_20;
            }
          }
        }
        SafeArrayDestroy(v12);
        if ( v9 < 0 )
          goto LABEL_20;
LABEL_18:
        v9 = 0;
      }
    }
LABEL_20:
    ReleaseMutex(*(HANDLE *)v6);
    return (unsigned int)v9;
  }
  ReleaseMutex(*(HANDLE *)v6);
  return 2147500035LL;
}

```

## disassembly

```asm
0x1800cfd20  mov     [rsp+arg_10], rbx
0x1800cfd25  push    rsi
0x1800cfd26  push    rdi
0x1800cfd27  push    r12
0x1800cfd29  push    r14
0x1800cfd2b  push    r15
0x1800cfd2d  sub     rsp, 30h
0x1800cfd31  mov     r14, r8
0x1800cfd34  mov     r12d, edx
0x1800cfd37  mov     r15, rcx
0x1800cfd3a  mov     [rsp+58h+dwindex], 0
0x1800cfd42  lea     rax, [rcx-8]
0x1800cfd46  lea     rdi, [rcx+20h]
0x1800cfd4a  mov     ecx, 8
0x1800cfd4f  test    rax, rax
0x1800cfd52  cmovz   rdi, rcx
0x1800cfd56  mov     [rsp+58h+arg_18], rdi
0x1800cfd5b  lea     rax, [rsp+58h+dwindex]
0x1800cfd60  mov     [rsp+58h+lpdwindex], rax; lpdwindex
0x1800cfd65  mov     r9, rdi; pHandles
0x1800cfd68  lea     r8d, [rcx-7]; cHandles
0x1800cfd6c  or      edx, 0FFFFFFFFh; dwTimeout
0x1800cfd6f  xor     ecx, ecx; dwFlags
0x1800cfd71  call    cs:__imp_CoWaitForMultipleHandles
0x1800cfd77  test    r12d, r12d
0x1800cfd7a  jns     short loc_1800CFD8F
0x1800cfd7c  mov     rcx, [rdi]; hMutex
0x1800cfd7f  call    cs:__imp_ReleaseMutex
0x1800cfd85  mov     eax, 80070057h
0x1800cfd8a  jmp     loc_1800CFEB8
0x1800cfd8f  test    r14, r14
0x1800cfd92  jz      loc_1800CFEAA
0x1800cfd98  mov     rcx, r14; pvarg
0x1800cfd9b  call    cs:__imp_VariantInit
0x1800cfda1  mov     rcx, [r15+30h]; struct CStrokeWithInk *
0x1800cfda5  call    ?ValidateStroke@@YAJPEAVCStrokeWithInk@@@Z; ValidateStroke(CStrokeWithInk *)
0x1800cfdaa  mov     ebx, eax
0x1800cfdac  test    eax, eax
0x1800cfdae  js      loc_1800CFE92
0x1800cfdb4  mov     [rsp+58h+dwindex], 0
0x1800cfdbc  mov     rcx, [rcx+10h]
0x1800cfdc0  xor     r9d, r9d; struct tagPOINT *
0x1800cfdc3  lea     r8, [rsp+58h+dwindex]; unsigned int *
0x1800cfdc8  mov     edx, r12d; unsigned int
0x1800cfdcb  mov     rcx, [rcx+10h]; this
0x1800cfdcf  call    InkStroke_GetFlattenedBezierPoints
0x1800cfdd4  mov     ebx, eax
0x1800cfdd6  cmp     eax, 1
0x1800cfdd9  jz      loc_1800CFE89
0x1800cfddf  test    eax, eax
0x1800cfde1  jnz     loc_1800CFE92
0x1800cfde7  mov     [rsp+58h+ppvData], 0
0x1800cfdf0  mov     eax, [rsp+58h+dwindex]
0x1800cfdf4  lea     r8d, [rax+rax]; cElements
0x1800cfdf8  mov     ecx, eax
0x1800cfdfa  add     rcx, rcx
0x1800cfdfd  mov     eax, r8d
0x1800cfe00  cmp     rax, rcx
0x1800cfe03  jnb     short loc_1800CFE0F
0x1800cfe05  mov     ebx, 8000FFFFh
0x1800cfe0a  jmp     loc_1800CFE92
0x1800cfe0f  mov     ecx, 3; vt
0x1800cfe14  xor     edx, edx; lLbound
0x1800cfe16  call    cs:__imp_SafeArrayCreateVector
0x1800cfe1c  mov     rsi, rax
0x1800cfe1f  test    rax, rax
0x1800cfe22  jz      short loc_1800CFE8D
0x1800cfe24  lea     rdx, [rsp+58h+ppvData]; ppvData
0x1800cfe29  mov     rcx, rax; psa
0x1800cfe2c  call    cs:__imp_SafeArrayAccessData
0x1800cfe32  mov     ebx, eax
0x1800cfe34  test    eax, eax
0x1800cfe36  js      short loc_1800CFE7C
0x1800cfe38  mov     rcx, [r15+30h]
0x1800cfe3c  mov     rcx, [rcx+10h]
0x1800cfe40  mov     r9, [rsp+58h+ppvData]; struct tagPOINT *
0x1800cfe45  lea     r8, [rsp+58h+dwindex]; unsigned int *
0x1800cfe4a  mov     edx, r12d; unsigned int
0x1800cfe4d  mov     rcx, [rcx+10h]; this
0x1800cfe51  call    InkStroke_GetFlattenedBezierPoints
0x1800cfe56  mov     ebx, eax
0x1800cfe58  mov     rcx, rsi; psa
0x1800cfe5b  call    cs:__imp_SafeArrayUnaccessData
0x1800cfe61  test    ebx, ebx
0x1800cfe63  js      short loc_1800CFE7C
0x1800cfe65  mov     ebx, eax
0x1800cfe67  test    eax, eax
0x1800cfe69  js      short loc_1800CFE7C
0x1800cfe6b  cmp     eax, 1
0x1800cfe6e  jz      short loc_1800CFE7C
0x1800cfe70  mov     word ptr [r14], 2003h
0x1800cfe76  mov     [r14+8], rsi
0x1800cfe7a  jmp     short loc_1800CFE92
0x1800cfe7c  mov     rcx, rsi; psa
0x1800cfe7f  call    cs:__imp_SafeArrayDestroy
0x1800cfe85  test    ebx, ebx
0x1800cfe87  js      short loc_1800CFE92
0x1800cfe89  xor     ebx, ebx
0x1800cfe8b  jmp     short loc_1800CFE92
0x1800cfe8d  mov     ebx, 8007000Eh
0x1800cfe92  jmp     short loc_1800CFE9D
0x1800cfe94  mov     ebx, [rsp+58h+dwindex]
0x1800cfe98  mov     rdi, [rsp+58h+arg_18]
0x1800cfe9d  mov     rcx, [rdi]; hMutex
0x1800cfea0  call    cs:__imp_ReleaseMutex
0x1800cfea6  mov     eax, ebx
0x1800cfea8  jmp     short loc_1800CFEB8
0x1800cfeaa  mov     rcx, [rdi]; hMutex
0x1800cfead  call    cs:__imp_ReleaseMutex
0x1800cfeb3  mov     eax, 80004003h
0x1800cfeb8  mov     rbx, [rsp+58h+arg_10]
0x1800cfebd  add     rsp, 30h
0x1800cfec1  pop     r15
0x1800cfec3  pop     r14
0x1800cfec5  pop     r12
0x1800cfec7  pop     rdi
0x1800cfec8  pop     rsi
0x1800cfec9  retn
```
