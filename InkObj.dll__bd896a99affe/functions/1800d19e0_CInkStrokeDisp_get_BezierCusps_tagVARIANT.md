# CInkStrokeDisp::get_BezierCusps(tagVARIANT *)

- ea: `0x1800d19e0`
- end: `0x1800d1b39`
- name: `?get_BezierCusps@CInkStrokeDisp@@UEAAJPEAUtagVARIANT@@@Z`
- size: `345`
- prototype: `int(CInkStrokeDisp *__hidden this, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000b78c`
- `0x18007db84`
- `0x1800d19e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800d1b15`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800d1b22`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800d1b15`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800d1b22`
- `OLEAUT32!__imp_VariantInit` at `0x1800d1a3b`
- `OLEAUT32!__imp_VariantInit` at `0x1800d1a3b`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800d1afa`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800d1afa`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800d1aaa`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800d1aaa`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800d1adb`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800d1adb`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800d1a94`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800d1a94`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800d1a29`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800d1a29`

## pseudocode

```c
__int64 __fastcall CInkStrokeDisp::get_BezierCusps(struct CStrokeWithInk **this, struct tagVARIANT *a2)
{
  __int64 v4; // rdi
  __int64 v5; // rcx
  HRESULT Cusps; // ebx
  SAFEARRAY *Vector; // rax
  SAFEARRAY *v8; // rsi
  HRESULT v9; // eax
  DWORD dwindex; // [rsp+60h] [rbp+8h] BYREF
  void *ppvData; // [rsp+68h] [rbp+10h] BYREF
  __int64 v13; // [rsp+70h] [rbp+18h]

  dwindex = 0;
  v4 = (__int64)(this + 4);
  if ( this == (struct CStrokeWithInk **)8 )
    v4 = 8;
  v13 = v4;
  CoWaitForMultipleHandles(0, 0xFFFFFFFF, 1u, (LPHANDLE)v4, &dwindex);
  if ( a2 )
  {
    VariantInit(a2);
    Cusps = ValidateStroke(this[6]);
    if ( Cusps >= 0 )
    {
      dwindex = 0;
      Cusps = InkStroke_GetCusps(*(_QWORD *)(*(_QWORD *)(v5 + 16) + 16LL), 2, &dwindex);
      if ( Cusps >= 0 )
      {
        ppvData = 0;
        Vector = SafeArrayCreateVector(3u, 0, dwindex);
        v8 = Vector;
        if ( Vector )
        {
          Cusps = SafeArrayAccessData(Vector, &ppvData);
          if ( Cusps < 0
            || (Cusps = InkStroke_GetCusps(*(_QWORD *)(*((_QWORD *)this[6] + 2) + 16LL), 2, &dwindex),
                v9 = SafeArrayUnaccessData(v8),
                Cusps < 0)
            || (Cusps = v9, v9 < 0) )
          {
            SafeArrayDestroy(v8);
          }
          else
          {
            a2->vt = 8195;
            a2->llVal = (LONGLONG)v8;
          }
        }
        else
        {
          Cusps = -2147024882;
        }
      }
    }
    ReleaseMutex(*(HANDLE *)v4);
    return (unsigned int)Cusps;
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
0x1800d19e0  push    rbx
0x1800d19e2  push    rsi
0x1800d19e3  push    rdi
0x1800d19e4  push    r14
0x1800d19e6  push    r15
0x1800d19e8  sub     rsp, 30h
0x1800d19ec  mov     r14, rdx
0x1800d19ef  mov     r15, rcx
0x1800d19f2  mov     [rsp+58h+dwindex], 0
0x1800d19fa  lea     rax, [rcx-8]
0x1800d19fe  lea     rdi, [rcx+20h]
0x1800d1a02  mov     ecx, 8
0x1800d1a07  test    rax, rax
0x1800d1a0a  cmovz   rdi, rcx
0x1800d1a0e  mov     [rsp+58h+arg_10], rdi
0x1800d1a13  lea     rax, [rsp+58h+dwindex]
0x1800d1a18  mov     [rsp+58h+lpdwindex], rax; lpdwindex
0x1800d1a1d  mov     r9, rdi; pHandles
0x1800d1a20  lea     r8d, [rcx-7]; cHandles
0x1800d1a24  or      edx, 0FFFFFFFFh; dwTimeout
0x1800d1a27  xor     ecx, ecx; dwFlags
0x1800d1a29  call    cs:__imp_CoWaitForMultipleHandles
0x1800d1a2f  test    r14, r14
0x1800d1a32  jz      loc_1800D1B1F
0x1800d1a38  mov     rcx, r14; pvarg
0x1800d1a3b  call    cs:__imp_VariantInit
0x1800d1a41  mov     rcx, [r15+30h]; struct CStrokeWithInk *
0x1800d1a45  call    ?ValidateStroke@@YAJPEAVCStrokeWithInk@@@Z; ValidateStroke(CStrokeWithInk *)
0x1800d1a4a  mov     ebx, eax
0x1800d1a4c  test    eax, eax
0x1800d1a4e  js      loc_1800D1B07
0x1800d1a54  mov     [rsp+58h+dwindex], 0
0x1800d1a5c  mov     rcx, [rcx+10h]
0x1800d1a60  xor     r9d, r9d
0x1800d1a63  lea     r8, [rsp+58h+dwindex]
0x1800d1a68  lea     edx, [r9+2]
0x1800d1a6c  mov     rcx, [rcx+10h]
0x1800d1a70  call    InkStroke_GetCusps
0x1800d1a75  mov     ebx, eax
0x1800d1a77  test    eax, eax
0x1800d1a79  js      loc_1800D1B07
0x1800d1a7f  mov     [rsp+58h+ppvData], 0
0x1800d1a88  mov     ecx, 3; vt
0x1800d1a8d  mov     r8d, [rsp+58h+dwindex]; cElements
0x1800d1a92  xor     edx, edx; lLbound
0x1800d1a94  call    cs:__imp_SafeArrayCreateVector
0x1800d1a9a  mov     rsi, rax
0x1800d1a9d  test    rax, rax
0x1800d1aa0  jz      short loc_1800D1B02
0x1800d1aa2  lea     rdx, [rsp+58h+ppvData]; ppvData
0x1800d1aa7  mov     rcx, rax; psa
0x1800d1aaa  call    cs:__imp_SafeArrayAccessData
0x1800d1ab0  mov     ebx, eax
0x1800d1ab2  test    eax, eax
0x1800d1ab4  js      short loc_1800D1AF7
0x1800d1ab6  mov     rcx, [r15+30h]
0x1800d1aba  mov     rcx, [rcx+10h]
0x1800d1abe  mov     r9, [rsp+58h+ppvData]
0x1800d1ac3  lea     r8, [rsp+58h+dwindex]
0x1800d1ac8  mov     edx, 2
0x1800d1acd  mov     rcx, [rcx+10h]
0x1800d1ad1  call    InkStroke_GetCusps
0x1800d1ad6  mov     ebx, eax
0x1800d1ad8  mov     rcx, rsi; psa
0x1800d1adb  call    cs:__imp_SafeArrayUnaccessData
0x1800d1ae1  test    ebx, ebx
0x1800d1ae3  js      short loc_1800D1AF7
0x1800d1ae5  mov     ebx, eax
0x1800d1ae7  test    eax, eax
0x1800d1ae9  js      short loc_1800D1AF7
0x1800d1aeb  mov     word ptr [r14], 2003h
0x1800d1af1  mov     [r14+8], rsi
0x1800d1af5  jmp     short loc_1800D1B07
0x1800d1af7  mov     rcx, rsi; psa
0x1800d1afa  call    cs:__imp_SafeArrayDestroy
0x1800d1b00  jmp     short loc_1800D1B07
0x1800d1b02  mov     ebx, 8007000Eh
0x1800d1b07  jmp     short loc_1800D1B12
0x1800d1b09  mov     ebx, [rsp+58h+dwindex]
0x1800d1b0d  mov     rdi, [rsp+58h+arg_10]
0x1800d1b12  mov     rcx, [rdi]; hMutex
0x1800d1b15  call    cs:__imp_ReleaseMutex
0x1800d1b1b  mov     eax, ebx
0x1800d1b1d  jmp     short loc_1800D1B2D
0x1800d1b1f  mov     rcx, [rdi]; hMutex
0x1800d1b22  call    cs:__imp_ReleaseMutex
0x1800d1b28  mov     eax, 80004003h
0x1800d1b2d  add     rsp, 30h
0x1800d1b31  pop     r15
0x1800d1b33  pop     r14
0x1800d1b35  pop     rdi
0x1800d1b36  pop     rsi
0x1800d1b37  pop     rbx
0x1800d1b38  retn
```
