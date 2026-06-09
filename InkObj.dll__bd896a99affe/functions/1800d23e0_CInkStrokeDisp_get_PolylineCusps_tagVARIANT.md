# CInkStrokeDisp::get_PolylineCusps(tagVARIANT *)

- ea: `0x1800d23e0`
- end: `0x1800d2539`
- name: `?get_PolylineCusps@CInkStrokeDisp@@UEAAJPEAUtagVARIANT@@@Z`
- size: `345`
- prototype: `int(CInkStrokeDisp *__hidden this, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000b78c`
- `0x18007db84`
- `0x1800d23e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800d2515`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800d2522`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800d2515`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800d2522`
- `OLEAUT32!__imp_VariantInit` at `0x1800d243b`
- `OLEAUT32!__imp_VariantInit` at `0x1800d243b`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800d24fa`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800d24fa`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800d24aa`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800d24aa`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800d24db`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800d24db`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800d2494`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800d2494`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800d2429`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800d2429`

## pseudocode

```c
__int64 __fastcall CInkStrokeDisp::get_PolylineCusps(struct CStrokeWithInk **this, struct tagVARIANT *a2)
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
      Cusps = InkStroke_GetCusps(*(_QWORD *)(*(_QWORD *)(v5 + 16) + 16LL), 1, &dwindex);
      if ( Cusps >= 0 )
      {
        ppvData = 0;
        Vector = SafeArrayCreateVector(3u, 0, dwindex);
        v8 = Vector;
        if ( Vector )
        {
          Cusps = SafeArrayAccessData(Vector, &ppvData);
          if ( Cusps < 0
            || (Cusps = InkStroke_GetCusps(*(_QWORD *)(*((_QWORD *)this[6] + 2) + 16LL), 1, &dwindex),
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
0x1800d23e0  push    rbx
0x1800d23e2  push    rsi
0x1800d23e3  push    rdi
0x1800d23e4  push    r14
0x1800d23e6  push    r15
0x1800d23e8  sub     rsp, 30h
0x1800d23ec  mov     r14, rdx
0x1800d23ef  mov     r15, rcx
0x1800d23f2  mov     [rsp+58h+dwindex], 0
0x1800d23fa  lea     rax, [rcx-8]
0x1800d23fe  lea     rdi, [rcx+20h]
0x1800d2402  mov     ecx, 8
0x1800d2407  test    rax, rax
0x1800d240a  cmovz   rdi, rcx
0x1800d240e  mov     [rsp+58h+arg_10], rdi
0x1800d2413  lea     rax, [rsp+58h+dwindex]
0x1800d2418  mov     [rsp+58h+lpdwindex], rax; lpdwindex
0x1800d241d  mov     r9, rdi; pHandles
0x1800d2420  lea     r8d, [rcx-7]; cHandles
0x1800d2424  or      edx, 0FFFFFFFFh; dwTimeout
0x1800d2427  xor     ecx, ecx; dwFlags
0x1800d2429  call    cs:__imp_CoWaitForMultipleHandles
0x1800d242f  test    r14, r14
0x1800d2432  jz      loc_1800D251F
0x1800d2438  mov     rcx, r14; pvarg
0x1800d243b  call    cs:__imp_VariantInit
0x1800d2441  mov     rcx, [r15+30h]; struct CStrokeWithInk *
0x1800d2445  call    ?ValidateStroke@@YAJPEAVCStrokeWithInk@@@Z; ValidateStroke(CStrokeWithInk *)
0x1800d244a  mov     ebx, eax
0x1800d244c  test    eax, eax
0x1800d244e  js      loc_1800D2507
0x1800d2454  mov     [rsp+58h+dwindex], 0
0x1800d245c  mov     rcx, [rcx+10h]
0x1800d2460  xor     r9d, r9d
0x1800d2463  lea     r8, [rsp+58h+dwindex]
0x1800d2468  lea     edx, [r9+1]
0x1800d246c  mov     rcx, [rcx+10h]
0x1800d2470  call    InkStroke_GetCusps
0x1800d2475  mov     ebx, eax
0x1800d2477  test    eax, eax
0x1800d2479  js      loc_1800D2507
0x1800d247f  mov     [rsp+58h+ppvData], 0
0x1800d2488  mov     ecx, 3; vt
0x1800d248d  mov     r8d, [rsp+58h+dwindex]; cElements
0x1800d2492  xor     edx, edx; lLbound
0x1800d2494  call    cs:__imp_SafeArrayCreateVector
0x1800d249a  mov     rsi, rax
0x1800d249d  test    rax, rax
0x1800d24a0  jz      short loc_1800D2502
0x1800d24a2  lea     rdx, [rsp+58h+ppvData]; ppvData
0x1800d24a7  mov     rcx, rax; psa
0x1800d24aa  call    cs:__imp_SafeArrayAccessData
0x1800d24b0  mov     ebx, eax
0x1800d24b2  test    eax, eax
0x1800d24b4  js      short loc_1800D24F7
0x1800d24b6  mov     rcx, [r15+30h]
0x1800d24ba  mov     rcx, [rcx+10h]
0x1800d24be  mov     r9, [rsp+58h+ppvData]
0x1800d24c3  lea     r8, [rsp+58h+dwindex]
0x1800d24c8  mov     edx, 1
0x1800d24cd  mov     rcx, [rcx+10h]
0x1800d24d1  call    InkStroke_GetCusps
0x1800d24d6  mov     ebx, eax
0x1800d24d8  mov     rcx, rsi; psa
0x1800d24db  call    cs:__imp_SafeArrayUnaccessData
0x1800d24e1  test    ebx, ebx
0x1800d24e3  js      short loc_1800D24F7
0x1800d24e5  mov     ebx, eax
0x1800d24e7  test    eax, eax
0x1800d24e9  js      short loc_1800D24F7
0x1800d24eb  mov     word ptr [r14], 2003h
0x1800d24f1  mov     [r14+8], rsi
0x1800d24f5  jmp     short loc_1800D2507
0x1800d24f7  mov     rcx, rsi; psa
0x1800d24fa  call    cs:__imp_SafeArrayDestroy
0x1800d2500  jmp     short loc_1800D2507
0x1800d2502  mov     ebx, 8007000Eh
0x1800d2507  jmp     short loc_1800D2512
0x1800d2509  mov     ebx, [rsp+58h+dwindex]
0x1800d250d  mov     rdi, [rsp+58h+arg_10]
0x1800d2512  mov     rcx, [rdi]; hMutex
0x1800d2515  call    cs:__imp_ReleaseMutex
0x1800d251b  mov     eax, ebx
0x1800d251d  jmp     short loc_1800D252D
0x1800d251f  mov     rcx, [rdi]; hMutex
0x1800d2522  call    cs:__imp_ReleaseMutex
0x1800d2528  mov     eax, 80004003h
0x1800d252d  add     rsp, 30h
0x1800d2531  pop     r15
0x1800d2533  pop     r14
0x1800d2535  pop     rdi
0x1800d2536  pop     rsi
0x1800d2537  pop     rbx
0x1800d2538  retn
```
