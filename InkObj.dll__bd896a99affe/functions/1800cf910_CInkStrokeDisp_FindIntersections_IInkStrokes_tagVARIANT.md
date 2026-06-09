# CInkStrokeDisp::FindIntersections(IInkStrokes *,tagVARIANT *)

- ea: `0x1800cf910`
- end: `0x1800cfbc1`
- name: `?FindIntersections@CInkStrokeDisp@@UEAAJPEAUIInkStrokes@@PEAUtagVARIANT@@@Z`
- size: `689`
- prototype: `int(CInkStrokeDisp *__hidden this, struct IInkStrokes *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x180001c20`
- `0x180009b64`
- `0x180009be8`
- `0x18000b78c`
- `0x180034e08`
- `0x1800410b0`
- `0x18007dd28`
- `0x1800a38dc`
- `0x1800bdbec`
- `0x1800cf910`
- `0x18010c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800cfb98`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800cfba6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800cfb98`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800cfba6`
- `OLEAUT32!__imp_VariantInit` at `0x1800cf976`
- `OLEAUT32!__imp_VariantInit` at `0x1800cf976`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800cfb5e`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800cfb5e`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800cfb09`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800cfb09`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800cfb3e`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800cfb3e`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800cfaf0`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800cfaf0`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800cf963`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800cf963`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall CInkStrokeDisp::FindIntersections(
        struct CStrokeWithInk **this,
        struct IInkStrokes *a2,
        struct tagVARIANT *a3)
{
  struct CStrokeSetImpl *v6; // rdi
  HANDLE *v7; // r12
  int Intersections; // ebx
  CInkStrokes *v9; // rsi
  __int64 v10; // r8
  const unsigned __int16 *v11; // r9
  __int64 v12; // rdx
  SAFEARRAY *Vector; // rax
  SAFEARRAY *v14; // rsi
  HRESULT v15; // eax
  unsigned int v17; // [rsp+28h] [rbp-60h]
  HINSTANCE v18; // [rsp+30h] [rbp-58h]
  __int64 cElements; // [rsp+90h] [rbp+8h] BYREF
  void *ppvData; // [rsp+98h] [rbp+10h] BYREF
  __int64 v21; // [rsp+A8h] [rbp+20h] BYREF

  ppvData = (void *)((unsigned __int64)(this + 3) & -(__int64)(this != (struct CStrokeWithInk **)8));
  v6 = 0;
  LODWORD(cElements) = 0;
  v7 = (HANDLE *)((char *)ppvData + 8);
  CoWaitForMultipleHandles(0, 0xFFFFFFFF, 1u, (LPHANDLE)ppvData + 1, (LPDWORD)&cElements);
  if ( a3 )
  {
    VariantInit(a3);
    Intersections = ValidateStroke(this[6]);
    if ( Intersections < 0 )
      goto LABEL_26;
    v9 = 0;
    if ( !a2 )
      goto LABEL_12;
    cElements = 0;
    ((void (__fastcall *)(struct IInkStrokes *, __int64 *))a2->lpVtbl->get_Ink)(a2, &cElements);
    if ( cElements == ((*((_QWORD *)this[6] + 3) + 8LL) & -(__int64)(*((_QWORD *)this[6] + 3) != 0)) )
    {
      v9 = (CInkStrokes *)InkDynamicCast<CInkStrokes *,IInkStrokes *>(a2);
      if ( v9 )
      {
        if ( !*((_QWORD *)v9 + 12) )
          Intersections = -2147418113;
LABEL_11:
        ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(&cElements);
        if ( Intersections >= 0 )
        {
LABEL_12:
          v21 = *(_QWORD *)(*((_QWORD *)this[6] + 3) + 112LL);
          InkObj_Lock();
          ppvData = 0;
          if ( a2 )
          {
            Intersections = CInkStrokes::ToStrokeSet(v9, &ppvData);
            if ( Intersections < 0 )
            {
LABEL_25:
              CInkAutoInkLock::~CInkAutoInkLock((CInkAutoInkLock *)&v21);
              goto LABEL_26;
            }
            v6 = (struct CStrokeSetImpl *)ppvData;
          }
          LODWORD(cElements) = 0;
          Intersections = InkStroke_GetIntersections(
                            *(CInkStroke **)(*((_QWORD *)this[6] + 2) + 16LL),
                            v6,
                            (unsigned int *)&cElements,
                            0);
          if ( Intersections >= 0 )
          {
            ppvData = 0;
            Vector = SafeArrayCreateVector(4u, 0, cElements);
            v14 = Vector;
            if ( Vector )
            {
              Intersections = SafeArrayAccessData(Vector, &ppvData);
              if ( Intersections < 0
                || (Intersections = InkStroke_GetIntersections(
                                      *(CInkStroke **)(*((_QWORD *)this[6] + 2) + 16LL),
                                      v6,
                                      (unsigned int *)&cElements,
                                      (float *)ppvData),
                    v15 = SafeArrayUnaccessData(v14),
                    Intersections < 0)
                || (Intersections = v15, v15 < 0) )
              {
                SafeArrayDestroy(v14);
              }
              else
              {
                a3->vt = 8196;
                a3->llVal = (LONGLONG)v14;
              }
            }
            else
            {
              Intersections = -2147024882;
            }
          }
          if ( v6 )
            DeleteStrokeSet(v6);
          goto LABEL_25;
        }
LABEL_26:
        ReleaseMutex(*v7);
        return (unsigned int)Intersections;
      }
      v18 = hInstance;
      v17 = -2144862204;
      v12 = 1105;
    }
    else
    {
      v18 = hInstance;
      v17 = -2144862206;
      v12 = 1107;
    }
    Intersections = ATL::AtlSetErrorInfo(&GUID_NULL, (WCHAR *)v12, v10, v11, &IID_IInkStrokeDisp, v17, v18);
    goto LABEL_11;
  }
  ReleaseMutex(*v7);
  return 2147500035LL;
}

```

## disassembly

```asm
0x1800cf910  mov     r11, rsp
0x1800cf913  push    rbx
0x1800cf914  push    rsi
0x1800cf915  push    rdi
0x1800cf916  push    r12
0x1800cf918  push    r13
0x1800cf91a  push    r14
0x1800cf91c  push    r15
0x1800cf91e  sub     rsp, 50h
0x1800cf922  mov     r13, r8
0x1800cf925  mov     r14, rdx
0x1800cf928  mov     r15, rcx
0x1800cf92b  lea     rax, [rcx-8]
0x1800cf92f  lea     r9, [rcx+18h]
0x1800cf933  neg     rax
0x1800cf936  sbb     r10, r10
0x1800cf939  and     r10, r9
0x1800cf93c  mov     [r11+10h], r10
0x1800cf940  xor     edi, edi
0x1800cf942  mov     [r11+8], edi
0x1800cf946  lea     r12, [r10+8]
0x1800cf94a  mov     [rsp+88h+var_48], r12
0x1800cf94f  lea     rax, [r11+8]
0x1800cf953  mov     [r11-68h], rax
0x1800cf957  mov     r9, r12; pHandles
0x1800cf95a  lea     r8d, [rdi+1]; cHandles
0x1800cf95e  or      edx, 0FFFFFFFFh; dwTimeout
0x1800cf961  xor     ecx, ecx; dwFlags
0x1800cf963  call    cs:__imp_CoWaitForMultipleHandles
0x1800cf969  nop
0x1800cf96a  test    r13, r13
0x1800cf96d  jz      loc_1800CFBA2
0x1800cf973  mov     rcx, r13; pvarg
0x1800cf976  call    cs:__imp_VariantInit
0x1800cf97c  mov     rcx, [r15+30h]; struct CStrokeWithInk *
0x1800cf980  call    ?ValidateStroke@@YAJPEAVCStrokeWithInk@@@Z; ValidateStroke(CStrokeWithInk *)
0x1800cf985  mov     ebx, eax
0x1800cf987  test    eax, eax
0x1800cf989  js      loc_1800CFB86
0x1800cf98f  mov     esi, edi
0x1800cf991  test    r14, r14
0x1800cf994  jz      loc_1800CFA59
0x1800cf99a  mov     [rsp+88h+cElements], rdi
0x1800cf9a2  mov     rcx, [r14]
0x1800cf9a5  mov     rax, [rcx+48h]
0x1800cf9a9  lea     rdx, [rsp+88h+cElements]
0x1800cf9b1  mov     rcx, r14
0x1800cf9b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cf9b9  mov     rax, [r15+30h]
0x1800cf9bd  mov     rcx, [rax+18h]
0x1800cf9c1  lea     rdx, [rcx+8]
0x1800cf9c5  neg     rcx
0x1800cf9c8  sbb     rax, rax
0x1800cf9cb  and     rax, rdx
0x1800cf9ce  cmp     [rsp+88h+cElements], rax
0x1800cf9d6  jz      short loc_1800CF9F3
0x1800cf9d8  mov     rax, cs:hInstance
0x1800cf9df  mov     [rsp+88h+var_58], rax
0x1800cf9e4  mov     [rsp+88h+var_60], 80280002h
0x1800cf9ec  mov     edx, 453h
0x1800cf9f1  jmp     short loc_1800CFA1C
0x1800cf9f3  mov     rcx, r14
0x1800cf9f6  call    ??$InkDynamicCast@PEAVCInkStrokes@@PEAUIInkStrokes@@@@YAPEAVCInkStrokes@@PEAUIInkStrokes@@@Z; InkDynamicCast<CInkStrokes *,IInkStrokes *>(IInkStrokes *)
0x1800cf9fb  mov     rsi, rax
0x1800cf9fe  test    rax, rax
0x1800cfa01  jnz     short loc_1800CFA38
0x1800cfa03  mov     rax, cs:hInstance
0x1800cfa0a  mov     [rsp+88h+var_58], rax; HINSTANCE
0x1800cfa0f  mov     [rsp+88h+var_60], 80280004h; int
0x1800cfa17  mov     edx, 451h; unsigned __int16 *
0x1800cfa1c  lea     rax, IID_IInkStrokeDisp
0x1800cfa23  mov     [rsp+88h+var_68], rax; struct _GUID *
0x1800cfa28  lea     rcx, GUID_NULL; clsid
0x1800cfa2f  call    ?AtlSetErrorInfo@ATL@@YAJAEBU_GUID@@PEBGK10JPEAUHINSTANCE__@@@Z; ATL::AtlSetErrorInfo(_GUID const &,ushort const *,ulong,ushort const *,_GUID const &,long,HINSTANCE__ *)
0x1800cfa34  mov     ebx, eax
0x1800cfa36  jmp     short loc_1800CFA44
0x1800cfa38  mov     eax, 8000FFFFh
0x1800cfa3d  cmp     [rsi+60h], rdi
0x1800cfa41  cmovz   ebx, eax
0x1800cfa44  lea     rcx, [rsp+88h+cElements]; void *
0x1800cfa4c  call    ??1?$CComPtr@UITablet2@@@ATL@@QEAA@XZ; ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(void)
0x1800cfa51  test    ebx, ebx
0x1800cfa53  js      loc_1800CFB86
0x1800cfa59  mov     rax, [r15+30h]
0x1800cfa5d  mov     rcx, [rax+18h]
0x1800cfa61  mov     rcx, [rcx+70h]
0x1800cfa65  mov     [rsp+88h+arg_18], rcx
0x1800cfa6d  call    InkObj_Lock
0x1800cfa72  mov     [rsp+88h+ppvData], rdi
0x1800cfa7a  test    r14, r14
0x1800cfa7d  jz      short loc_1800CFAA1
0x1800cfa7f  lea     rdx, [rsp+88h+ppvData]; void **
0x1800cfa87  mov     rcx, rsi; this
0x1800cfa8a  call    ?ToStrokeSet@CInkStrokes@@QEAAJAEAPEAX@Z; CInkStrokes::ToStrokeSet(void * &)
0x1800cfa8f  mov     ebx, eax
0x1800cfa91  test    eax, eax
0x1800cfa93  js      loc_1800CFB78
0x1800cfa99  mov     rdi, [rsp+88h+ppvData]
0x1800cfaa1  mov     dword ptr [rsp+88h+cElements], 0
0x1800cfaac  mov     rax, [r15+30h]
0x1800cfab0  mov     rcx, [rax+10h]
0x1800cfab4  xor     r9d, r9d; float *
0x1800cfab7  lea     r8, [rsp+88h+cElements]; unsigned int *
0x1800cfabf  mov     rdx, rdi; struct CStrokeSetImpl *
0x1800cfac2  mov     rcx, [rcx+10h]; this
0x1800cfac6  call    InkStroke_GetIntersections
0x1800cfacb  mov     ebx, eax
0x1800cfacd  test    eax, eax
0x1800cfacf  js      loc_1800CFB6B
0x1800cfad5  mov     [rsp+88h+ppvData], 0
0x1800cfae1  mov     ecx, 4; vt
0x1800cfae6  mov     r8d, dword ptr [rsp+88h+cElements]; cElements
0x1800cfaee  xor     edx, edx; lLbound
0x1800cfaf0  call    cs:__imp_SafeArrayCreateVector
0x1800cfaf6  mov     rsi, rax
0x1800cfaf9  test    rax, rax
0x1800cfafc  jz      short loc_1800CFB66
0x1800cfafe  lea     rdx, [rsp+88h+ppvData]; ppvData
0x1800cfb06  mov     rcx, rax; psa
0x1800cfb09  call    cs:__imp_SafeArrayAccessData
0x1800cfb0f  mov     ebx, eax
0x1800cfb11  test    eax, eax
0x1800cfb13  js      short loc_1800CFB5B
0x1800cfb15  mov     rcx, [r15+30h]
0x1800cfb19  mov     rcx, [rcx+10h]
0x1800cfb1d  mov     r9, [rsp+88h+ppvData]; float *
0x1800cfb25  lea     r8, [rsp+88h+cElements]; unsigned int *
0x1800cfb2d  mov     rdx, rdi; struct CStrokeSetImpl *
0x1800cfb30  mov     rcx, [rcx+10h]; this
0x1800cfb34  call    InkStroke_GetIntersections
0x1800cfb39  mov     ebx, eax
0x1800cfb3b  mov     rcx, rsi; psa
0x1800cfb3e  call    cs:__imp_SafeArrayUnaccessData
0x1800cfb44  test    ebx, ebx
0x1800cfb46  js      short loc_1800CFB5B
0x1800cfb48  mov     ebx, eax
0x1800cfb4a  test    eax, eax
0x1800cfb4c  js      short loc_1800CFB5B
0x1800cfb4e  mov     word ptr [r13+0], 2004h
0x1800cfb55  mov     [r13+8], rsi
0x1800cfb59  jmp     short loc_1800CFB6B
0x1800cfb5b  mov     rcx, rsi; psa
0x1800cfb5e  call    cs:__imp_SafeArrayDestroy
0x1800cfb64  jmp     short loc_1800CFB6B
0x1800cfb66  mov     ebx, 8007000Eh
0x1800cfb6b  test    rdi, rdi
0x1800cfb6e  jz      short loc_1800CFB78
0x1800cfb70  mov     rcx, rdi; this
0x1800cfb73  call    DeleteStrokeSet
0x1800cfb78  lea     rcx, [rsp+88h+arg_18]; this
0x1800cfb80  call    ??1CInkAutoInkLock@@QEAA@XZ; CInkAutoInkLock::~CInkAutoInkLock(void)
0x1800cfb85  nop
0x1800cfb86  jmp     short loc_1800CFB94
0x1800cfb88  mov     ebx, dword ptr [rsp+88h+cElements]
0x1800cfb8f  mov     r12, [rsp+88h+var_48]
0x1800cfb94  mov     rcx, [r12]; hMutex
0x1800cfb98  call    cs:__imp_ReleaseMutex
0x1800cfb9e  mov     eax, ebx
0x1800cfba0  jmp     short loc_1800CFBB1
0x1800cfba2  mov     rcx, [r12]; hMutex
0x1800cfba6  call    cs:__imp_ReleaseMutex
0x1800cfbac  mov     eax, 80004003h
0x1800cfbb1  add     rsp, 50h
0x1800cfbb5  pop     r15
0x1800cfbb7  pop     r14
0x1800cfbb9  pop     r13
0x1800cfbbb  pop     r12
0x1800cfbbd  pop     rdi
0x1800cfbbe  pop     rsi
0x1800cfbbf  pop     rbx
0x1800cfbc0  retn
```
