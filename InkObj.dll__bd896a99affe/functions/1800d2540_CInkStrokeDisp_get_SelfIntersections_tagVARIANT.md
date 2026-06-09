# CInkStrokeDisp::get_SelfIntersections(tagVARIANT *)

- ea: `0x1800d2540`
- end: `0x1800d2690`
- name: `?get_SelfIntersections@CInkStrokeDisp@@UEAAJPEAUtagVARIANT@@@Z`
- size: `336`
- prototype: `int(CInkStrokeDisp *__hidden this, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000b78c`
- `0x18007e178`
- `0x1800d2540`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800d266c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800d2679`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800d266c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800d2679`
- `OLEAUT32!__imp_VariantInit` at `0x1800d259b`
- `OLEAUT32!__imp_VariantInit` at `0x1800d259b`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800d2651`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800d2651`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800d2606`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800d2606`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800d2632`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800d2632`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800d25f0`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800d25f0`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800d2589`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800d2589`

## pseudocode

```c
__int64 __fastcall CInkStrokeDisp::get_SelfIntersections(struct CStrokeWithInk **this, struct tagVARIANT *a2)
{
  __int64 v4; // rdi
  __int64 v5; // rcx
  HRESULT SelfIntersections; // ebx
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
    SelfIntersections = ValidateStroke(this[6]);
    if ( SelfIntersections >= 0 )
    {
      dwindex = 0;
      SelfIntersections = InkStroke_GetSelfIntersections(*(CInkStroke **)(*(_QWORD *)(v5 + 16) + 16LL), &dwindex, 0);
      if ( SelfIntersections >= 0 )
      {
        ppvData = 0;
        Vector = SafeArrayCreateVector(4u, 0, dwindex);
        v8 = Vector;
        if ( Vector )
        {
          SelfIntersections = SafeArrayAccessData(Vector, &ppvData);
          if ( SelfIntersections < 0
            || (SelfIntersections = InkStroke_GetSelfIntersections(
                                      *(CInkStroke **)(*((_QWORD *)this[6] + 2) + 16LL),
                                      &dwindex,
                                      (float *)ppvData),
                v9 = SafeArrayUnaccessData(v8),
                SelfIntersections < 0)
            || (SelfIntersections = v9, v9 < 0) )
          {
            SafeArrayDestroy(v8);
          }
          else
          {
            a2->vt = 8196;
            a2->llVal = (LONGLONG)v8;
          }
        }
        else
        {
          SelfIntersections = -2147024882;
        }
      }
    }
    ReleaseMutex(*(HANDLE *)v4);
    return (unsigned int)SelfIntersections;
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
0x1800d2540  push    rbx
0x1800d2542  push    rsi
0x1800d2543  push    rdi
0x1800d2544  push    r14
0x1800d2546  push    r15
0x1800d2548  sub     rsp, 30h
0x1800d254c  mov     r14, rdx
0x1800d254f  mov     r15, rcx
0x1800d2552  mov     [rsp+58h+dwindex], 0
0x1800d255a  lea     rax, [rcx-8]
0x1800d255e  lea     rdi, [rcx+20h]
0x1800d2562  mov     ecx, 8
0x1800d2567  test    rax, rax
0x1800d256a  cmovz   rdi, rcx
0x1800d256e  mov     [rsp+58h+arg_10], rdi
0x1800d2573  lea     rax, [rsp+58h+dwindex]
0x1800d2578  mov     [rsp+58h+lpdwindex], rax; lpdwindex
0x1800d257d  mov     r9, rdi; pHandles
0x1800d2580  lea     r8d, [rcx-7]; cHandles
0x1800d2584  or      edx, 0FFFFFFFFh; dwTimeout
0x1800d2587  xor     ecx, ecx; dwFlags
0x1800d2589  call    cs:__imp_CoWaitForMultipleHandles
0x1800d258f  test    r14, r14
0x1800d2592  jz      loc_1800D2676
0x1800d2598  mov     rcx, r14; pvarg
0x1800d259b  call    cs:__imp_VariantInit
0x1800d25a1  mov     rcx, [r15+30h]; struct CStrokeWithInk *
0x1800d25a5  call    ?ValidateStroke@@YAJPEAVCStrokeWithInk@@@Z; ValidateStroke(CStrokeWithInk *)
0x1800d25aa  mov     ebx, eax
0x1800d25ac  test    eax, eax
0x1800d25ae  js      loc_1800D265E
0x1800d25b4  mov     [rsp+58h+dwindex], 0
0x1800d25bc  mov     rcx, [rcx+10h]
0x1800d25c0  xor     r8d, r8d; float *
0x1800d25c3  lea     rdx, [rsp+58h+dwindex]; unsigned int *
0x1800d25c8  mov     rcx, [rcx+10h]; this
0x1800d25cc  call    InkStroke_GetSelfIntersections
0x1800d25d1  mov     ebx, eax
0x1800d25d3  test    eax, eax
0x1800d25d5  js      loc_1800D265E
0x1800d25db  mov     [rsp+58h+ppvData], 0
0x1800d25e4  mov     ecx, 4; vt
0x1800d25e9  mov     r8d, [rsp+58h+dwindex]; cElements
0x1800d25ee  xor     edx, edx; lLbound
0x1800d25f0  call    cs:__imp_SafeArrayCreateVector
0x1800d25f6  mov     rsi, rax
0x1800d25f9  test    rax, rax
0x1800d25fc  jz      short loc_1800D2659
0x1800d25fe  lea     rdx, [rsp+58h+ppvData]; ppvData
0x1800d2603  mov     rcx, rax; psa
0x1800d2606  call    cs:__imp_SafeArrayAccessData
0x1800d260c  mov     ebx, eax
0x1800d260e  test    eax, eax
0x1800d2610  js      short loc_1800D264E
0x1800d2612  mov     rcx, [r15+30h]
0x1800d2616  mov     rcx, [rcx+10h]
0x1800d261a  mov     r8, [rsp+58h+ppvData]; float *
0x1800d261f  lea     rdx, [rsp+58h+dwindex]; unsigned int *
0x1800d2624  mov     rcx, [rcx+10h]; this
0x1800d2628  call    InkStroke_GetSelfIntersections
0x1800d262d  mov     ebx, eax
0x1800d262f  mov     rcx, rsi; psa
0x1800d2632  call    cs:__imp_SafeArrayUnaccessData
0x1800d2638  test    ebx, ebx
0x1800d263a  js      short loc_1800D264E
0x1800d263c  mov     ebx, eax
0x1800d263e  test    eax, eax
0x1800d2640  js      short loc_1800D264E
0x1800d2642  mov     word ptr [r14], 2004h
0x1800d2648  mov     [r14+8], rsi
0x1800d264c  jmp     short loc_1800D265E
0x1800d264e  mov     rcx, rsi; psa
0x1800d2651  call    cs:__imp_SafeArrayDestroy
0x1800d2657  jmp     short loc_1800D265E
0x1800d2659  mov     ebx, 8007000Eh
0x1800d265e  jmp     short loc_1800D2669
0x1800d2660  mov     ebx, [rsp+58h+dwindex]
0x1800d2664  mov     rdi, [rsp+58h+arg_10]
0x1800d2669  mov     rcx, [rdi]; hMutex
0x1800d266c  call    cs:__imp_ReleaseMutex
0x1800d2672  mov     eax, ebx
0x1800d2674  jmp     short loc_1800D2684
0x1800d2676  mov     rcx, [rdi]; hMutex
0x1800d2679  call    cs:__imp_ReleaseMutex
0x1800d267f  mov     eax, 80004003h
0x1800d2684  add     rsp, 30h
0x1800d2688  pop     r15
0x1800d268a  pop     r14
0x1800d268c  pop     rdi
0x1800d268d  pop     rsi
0x1800d268e  pop     rbx
0x1800d268f  retn
```
