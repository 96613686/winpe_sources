# CInkStrokeDisp::get_BezierPoints(tagVARIANT *)

- ea: `0x1800d1b40`
- end: `0x1800d1c98`
- name: `?get_BezierPoints@CInkStrokeDisp@@UEAAJPEAUtagVARIANT@@@Z`
- size: `344`
- prototype: `int(CInkStrokeDisp *__hidden this, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18007da7c`
- `0x1800d1b40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800d1c74`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800d1c81`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800d1c74`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800d1c81`
- `OLEAUT32!__imp_VariantInit` at `0x1800d1b9b`
- `OLEAUT32!__imp_VariantInit` at `0x1800d1b9b`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800d1c59`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800d1c59`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800d1c0e`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800d1c0e`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800d1c3a`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800d1c3a`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800d1bf8`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800d1bf8`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800d1b89`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800d1b89`

## pseudocode

```c
__int64 __fastcall CInkStrokeDisp::get_BezierPoints(CInkStrokeDisp *this, struct tagVARIANT *a2)
{
  __int64 v4; // rdi
  HRESULT BezierPoints; // ebx
  SAFEARRAY *Vector; // rax
  SAFEARRAY *v7; // rsi
  HRESULT v8; // eax
  DWORD dwindex; // [rsp+60h] [rbp+8h] BYREF
  void *ppvData; // [rsp+68h] [rbp+10h] BYREF
  __int64 v12; // [rsp+70h] [rbp+18h]

  dwindex = 0;
  v4 = (__int64)this + 32;
  if ( this == (CInkStrokeDisp *)8 )
    v4 = 8;
  v12 = v4;
  CoWaitForMultipleHandles(0, 0xFFFFFFFF, 1u, (LPHANDLE)v4, &dwindex);
  if ( a2 )
  {
    VariantInit(a2);
    dwindex = 0;
    BezierPoints = InkStroke_GetBezierPoints(
                     *(CInkStroke **)(*(_QWORD *)(*((_QWORD *)this + 6) + 16LL) + 16LL),
                     &dwindex,
                     0);
    if ( BezierPoints >= 0 )
    {
      ppvData = 0;
      if ( 2 * dwindex >= 2 * (unsigned __int64)dwindex )
      {
        Vector = SafeArrayCreateVector(3u, 0, 2 * dwindex);
        v7 = Vector;
        if ( Vector )
        {
          BezierPoints = SafeArrayAccessData(Vector, &ppvData);
          if ( BezierPoints < 0
            || (BezierPoints = InkStroke_GetBezierPoints(
                                 *(CInkStroke **)(*(_QWORD *)(*((_QWORD *)this + 6) + 16LL) + 16LL),
                                 &dwindex,
                                 (struct tagPOINT *)ppvData),
                v8 = SafeArrayUnaccessData(v7),
                BezierPoints < 0)
            || (BezierPoints = v8, v8 < 0) )
          {
            SafeArrayDestroy(v7);
          }
          else
          {
            a2->vt = 8195;
            a2->llVal = (LONGLONG)v7;
          }
        }
        else
        {
          BezierPoints = -2147024882;
        }
      }
      else
      {
        BezierPoints = -2147418113;
      }
    }
    ReleaseMutex(*(HANDLE *)v4);
    return (unsigned int)BezierPoints;
  }
  else
  {
    ReleaseMutex(*(HANDLE *)v4);
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x1800d1b40  push    rbx
0x1800d1b42  push    rsi
0x1800d1b43  push    rdi
0x1800d1b44  push    r14
0x1800d1b46  push    r15
0x1800d1b48  sub     rsp, 30h
0x1800d1b4c  mov     r14, rdx
0x1800d1b4f  mov     r15, rcx
0x1800d1b52  mov     [rsp+58h+dwindex], 0
0x1800d1b5a  lea     rax, [rcx-8]
0x1800d1b5e  lea     rdi, [rcx+20h]
0x1800d1b62  mov     ecx, 8
0x1800d1b67  test    rax, rax
0x1800d1b6a  cmovz   rdi, rcx
0x1800d1b6e  mov     [rsp+58h+arg_10], rdi
0x1800d1b73  lea     rax, [rsp+58h+dwindex]
0x1800d1b78  mov     [rsp+58h+lpdwindex], rax; lpdwindex
0x1800d1b7d  mov     r9, rdi; pHandles
0x1800d1b80  lea     r8d, [rcx-7]; cHandles
0x1800d1b84  or      edx, 0FFFFFFFFh; dwTimeout
0x1800d1b87  xor     ecx, ecx; dwFlags
0x1800d1b89  call    cs:__imp_CoWaitForMultipleHandles
0x1800d1b8f  test    r14, r14
0x1800d1b92  jz      loc_1800D1C7E
0x1800d1b98  mov     rcx, r14; pvarg
0x1800d1b9b  call    cs:__imp_VariantInit
0x1800d1ba1  mov     [rsp+58h+dwindex], 0
0x1800d1ba9  mov     rax, [r15+30h]
0x1800d1bad  mov     rcx, [rax+10h]
0x1800d1bb1  xor     r8d, r8d; struct tagPOINT *
0x1800d1bb4  lea     rdx, [rsp+58h+dwindex]; unsigned int *
0x1800d1bb9  mov     rcx, [rcx+10h]; this
0x1800d1bbd  call    InkStroke_GetBezierPoints
0x1800d1bc2  mov     ebx, eax
0x1800d1bc4  test    eax, eax
0x1800d1bc6  js      loc_1800D1C66
0x1800d1bcc  mov     [rsp+58h+ppvData], 0
0x1800d1bd5  mov     eax, [rsp+58h+dwindex]
0x1800d1bd9  lea     r8d, [rax+rax]; cElements
0x1800d1bdd  mov     ecx, eax
0x1800d1bdf  add     rcx, rcx
0x1800d1be2  mov     eax, r8d
0x1800d1be5  cmp     rax, rcx
0x1800d1be8  jnb     short loc_1800D1BF1
0x1800d1bea  mov     ebx, 8000FFFFh
0x1800d1bef  jmp     short loc_1800D1C66
0x1800d1bf1  mov     ecx, 3; vt
0x1800d1bf6  xor     edx, edx; lLbound
0x1800d1bf8  call    cs:__imp_SafeArrayCreateVector
0x1800d1bfe  mov     rsi, rax
0x1800d1c01  test    rax, rax
0x1800d1c04  jz      short loc_1800D1C61
0x1800d1c06  lea     rdx, [rsp+58h+ppvData]; ppvData
0x1800d1c0b  mov     rcx, rax; psa
0x1800d1c0e  call    cs:__imp_SafeArrayAccessData
0x1800d1c14  mov     ebx, eax
0x1800d1c16  test    eax, eax
0x1800d1c18  js      short loc_1800D1C56
0x1800d1c1a  mov     rcx, [r15+30h]
0x1800d1c1e  mov     rcx, [rcx+10h]
0x1800d1c22  mov     r8, [rsp+58h+ppvData]; struct tagPOINT *
0x1800d1c27  lea     rdx, [rsp+58h+dwindex]; unsigned int *
0x1800d1c2c  mov     rcx, [rcx+10h]; this
0x1800d1c30  call    InkStroke_GetBezierPoints
0x1800d1c35  mov     ebx, eax
0x1800d1c37  mov     rcx, rsi; psa
0x1800d1c3a  call    cs:__imp_SafeArrayUnaccessData
0x1800d1c40  test    ebx, ebx
0x1800d1c42  js      short loc_1800D1C56
0x1800d1c44  mov     ebx, eax
0x1800d1c46  test    eax, eax
0x1800d1c48  js      short loc_1800D1C56
0x1800d1c4a  mov     word ptr [r14], 2003h
0x1800d1c50  mov     [r14+8], rsi
0x1800d1c54  jmp     short loc_1800D1C66
0x1800d1c56  mov     rcx, rsi; psa
0x1800d1c59  call    cs:__imp_SafeArrayDestroy
0x1800d1c5f  jmp     short loc_1800D1C66
0x1800d1c61  mov     ebx, 8007000Eh
0x1800d1c66  jmp     short loc_1800D1C71
0x1800d1c68  mov     ebx, [rsp+58h+dwindex]
0x1800d1c6c  mov     rdi, [rsp+58h+arg_10]
0x1800d1c71  mov     rcx, [rdi]; hMutex
0x1800d1c74  call    cs:__imp_ReleaseMutex
0x1800d1c7a  mov     eax, ebx
0x1800d1c7c  jmp     short loc_1800D1C8C
0x1800d1c7e  mov     rcx, [rdi]; hMutex
0x1800d1c81  call    cs:__imp_ReleaseMutex
0x1800d1c87  mov     eax, 80004003h
0x1800d1c8c  add     rsp, 30h
0x1800d1c90  pop     r15
0x1800d1c92  pop     r14
0x1800d1c94  pop     rdi
0x1800d1c95  pop     rsi
0x1800d1c96  pop     rbx
0x1800d1c97  retn
```
