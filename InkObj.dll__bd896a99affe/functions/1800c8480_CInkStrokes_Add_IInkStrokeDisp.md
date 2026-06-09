# CInkStrokes::_Add(IInkStrokeDisp *)

- ea: `0x1800c8480`
- end: `0x1800c87b3`
- name: `?_Add@CInkStrokes@@UEAAJPEAUIInkStrokeDisp@@@Z`
- size: `819`
- prototype: `__int64 __fastcall(CInkStrokes *__hidden this, struct IInkStrokeDisp *)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180001c20`
- `0x180009b64`
- `0x180010350`
- `0x180034e08`
- `0x1800a38dc`
- `0x1800bdbb8`
- `0x1800c10d0`
- `0x1800c5f20`
- `0x1800c8480`
- `0x18010c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800c8676`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800c8676`
- `OLEAUT32!__imp_VariantInit` at `0x1800c871c`
- `OLEAUT32!__imp_VariantInit` at `0x1800c871c`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800c876b`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800c876b`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800c86b6`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800c86b6`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800c86e2`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800c86e2`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800c868d`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800c868d`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800c863d`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800c863d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CInkStrokes::_Add(CInkStrokes *this, struct IInkStrokeDisp *a2)
{
  int inserted; // edi
  __int64 v5; // r8
  const unsigned __int16 *v6; // r9
  __int64 v7; // rbx
  __int64 v8; // rdx
  GUID *v9; // rcx
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rcx
  volatile signed __int32 *v13; // rdi
  __int64 v14; // rcx
  __int64 v15; // rax
  __int64 v16; // rbx
  SAFEARRAY *Vector; // rax
  SAFEARRAY *v18; // rbx
  HRESULT v19; // eax
  HRESULT v20; // esi
  void (__fastcall ***v21)(_QWORD, VARIANTARG *); // rcx
  unsigned int v23; // [rsp+28h] [rbp-70h]
  HINSTANCE v24; // [rsp+30h] [rbp-68h]
  VARIANTARG pvarg; // [rsp+40h] [rbp-58h] BYREF
  VARIANTARG v26; // [rsp+60h] [rbp-38h] BYREF
  volatile signed __int32 *dwindex; // [rsp+A8h] [rbp+10h] BYREF
  __int64 v28; // [rsp+B0h] [rbp+18h] BYREF

  if ( !a2 )
    return 2147500035LL;
  try
  {
    v28 = 0;
    inserted = ((__int64 (__fastcall *)(struct IInkStrokeDisp *, __int64 *))a2->lpVtbl->get_Ink)(a2, &v28);
    v7 = 0;
    if ( v28 == ((*((_QWORD *)this + 10) + 8LL) & -(__int64)(*((_QWORD *)this + 10) != 0)) )
    {
      v10 = InkDynamicCast<CInkStrokeDisp *,IInkStrokeDisp *>(a2);
      if ( v10 )
      {
        v7 = *(_QWORD *)(v10 + 56);
LABEL_10:
        if ( inserted >= 0 )
        {
          if ( *((_QWORD *)this + 10)
            && v7
            && (v11 = *(_QWORD *)(v7 + 24)) != 0
            && (v12 = *(_QWORD *)(v7 + 16)) != 0
            && *(_QWORD *)(v11 + 112)
            && *(_QWORD *)(v12 + 16) )
          {
            v13 = (volatile signed __int32 *)WinMalloc(0x28u);
            dwindex = v13;
            if ( !v13 )
              goto LABEL_29;
            v14 = *(_QWORD *)(v7 + 24);
            v15 = *(_QWORD *)(v7 + 16);
            *(_QWORD *)v13 = &CRefCountedObject::`vftable';
            *((_DWORD *)v13 + 2) = 0;
            _InterlockedIncrement(v13 + 2);
            *(_QWORD *)v13 = &CStrokeWithInk::`vftable';
            *((_QWORD *)v13 + 2) = v15;
            *((_QWORD *)v13 + 3) = v14;
            (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v7 + 24) + 8LL))(*(_QWORD *)(v7 + 24));
            _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(v7 + 16) + 8LL));
            LODWORD(dwindex) = 0;
            v16 = (__int64)this + 64;
            if ( this == (CInkStrokes *)16 )
              v16 = 8;
            CoWaitForMultipleHandles(0, 0xFFFFFFFF, 1u, (LPHANDLE)v16, (LPDWORD)&dwindex);
            dwindex = *(volatile signed __int32 **)(*((_QWORD *)this + 10) + 112LL);
            InkObj_Lock();
            inserted = CInkBasicQueue<CStrokeWithInk,1,1,1>::InsertSortedUnique((char *)this + 88, v13);
            CInkAutoInkLock::~CInkAutoInkLock((CInkAutoInkLock *)&dwindex);
            ReleaseMutex(*(HANDLE *)v16);
            if ( inserted )
              goto LABEL_31;
            Vector = SafeArrayCreateVector(3u, 0, 1u);
            v18 = Vector;
            if ( Vector )
            {
              dwindex = 0;
              inserted = SafeArrayAccessData(Vector, (void **)&dwindex);
              if ( inserted >= 0 )
              {
                inserted = ((__int64 (__fastcall *)(struct IInkStrokeDisp *, volatile signed __int32 *))a2->lpVtbl->get_ID)(
                             a2,
                             dwindex);
                v19 = SafeArrayUnaccessData(v18);
                v20 = v19;
                if ( inserted >= 0 )
                {
                  if ( v19 >= 0
                    && (CProxy_IInkStrokesEvents<CInkStrokes>::Fire_StrokesAdded((char *)this + 24, v18),
                        *((_QWORD *)this + 16)) )
                  {
                    memset(&pvarg, 0, sizeof(pvarg));
                    VariantInit(&pvarg);
                    pvarg.vt = 8195;
                    pvarg.llVal = (LONGLONG)v18;
                    v21 = (void (__fastcall ***)(_QWORD, VARIANTARG *))(*((_QWORD *)this + 16) + 16LL);
                    v26 = pvarg;
                    (**v21)(v21, &v26);
                    inserted = v20;
                  }
                  else
                  {
                    inserted = v20;
                  }
                }
              }
              SafeArrayDestroy(v18);
            }
            else
            {
LABEL_29:
              inserted = -2147024882;
            }
          }
          else
          {
            inserted = -2147418113;
          }
        }
LABEL_31:
        ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(&v28);
        return (unsigned int)inserted;
      }
      v24 = hInstance;
      v23 = -2144862204;
      v8 = 1105;
      v9 = &GUID_NULL;
    }
    else
    {
      if ( inserted < 0 )
        goto LABEL_31;
      v24 = hInstance;
      v23 = -2144862206;
      v8 = 1107;
      v9 = &CLSID_InkStrokes;
    }
    inserted = ATL::AtlSetErrorInfo(v9, (WCHAR *)v8, v5, v6, &IID_IInkStrokes, v23, v24);
    goto LABEL_10;
  }
  catch ( ... )
  {
    LODWORD(dwindex) = ReportWispException();
    return (unsigned int)dwindex;
  }
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x1800c8480  mov     r11, rsp
0x1800c8483  mov     [r11+8], rbx
0x1800c8487  push    rsi
0x1800c8488  push    rdi
0x1800c8489  push    r14
0x1800c848b  sub     rsp, 80h
0x1800c8492  mov     rsi, rdx
0x1800c8495  mov     r14, rcx
0x1800c8498  test    rdx, rdx
0x1800c849b  jz      loc_1800C879A
0x1800c84a1  mov     qword ptr [r11+18h], 0
0x1800c84a9  mov     rax, [rdx]
0x1800c84ac  lea     rdx, [r11+18h]
0x1800c84b0  mov     rcx, rsi
0x1800c84b3  mov     rax, [rax+58h]
0x1800c84b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c84bc  mov     edi, eax
0x1800c84be  mov     rax, [r14+50h]
0x1800c84c2  xor     ebx, ebx
0x1800c84c4  lea     rcx, [rax+8]
0x1800c84c8  neg     rax
0x1800c84cb  sbb     rax, rax
0x1800c84ce  and     rax, rcx
0x1800c84d1  cmp     [rsp+98h+arg_10], rax
0x1800c84d9  jz      short loc_1800C8505
0x1800c84db  test    edi, edi
0x1800c84dd  js      loc_1800C877F
0x1800c84e3  mov     rax, cs:hInstance
0x1800c84ea  mov     [rsp+98h+var_68], rax
0x1800c84ef  mov     [rsp+98h+var_70], 80280002h
0x1800c84f7  mov     edx, 453h
0x1800c84fc  lea     rcx, CLSID_InkStrokes
0x1800c8503  jmp     short loc_1800C8532
0x1800c8505  mov     rcx, rsi
0x1800c8508  call    ??$InkDynamicCast@PEAVCInkStrokeDisp@@PEAUIInkStrokeDisp@@@@YAPEAVCInkStrokeDisp@@PEAUIInkStrokeDisp@@@Z; InkDynamicCast<CInkStrokeDisp *,IInkStrokeDisp *>(IInkStrokeDisp *)
0x1800c850d  test    rax, rax
0x1800c8510  jnz     short loc_1800C8547
0x1800c8512  mov     rax, cs:hInstance
0x1800c8519  mov     [rsp+98h+var_68], rax; HINSTANCE
0x1800c851e  mov     [rsp+98h+var_70], 80280004h; int
0x1800c8526  mov     edx, 451h; unsigned __int16 *
0x1800c852b  lea     rcx, GUID_NULL; clsid
0x1800c8532  lea     rax, IID_IInkStrokes
0x1800c8539  mov     [rsp+98h+lpdwindex], rax; struct _GUID *
0x1800c853e  call    ?AtlSetErrorInfo@ATL@@YAJAEBU_GUID@@PEBGK10JPEAUHINSTANCE__@@@Z; ATL::AtlSetErrorInfo(_GUID const &,ushort const *,ulong,ushort const *,_GUID const &,long,HINSTANCE__ *)
0x1800c8543  mov     edi, eax
0x1800c8545  jmp     short loc_1800C854B
0x1800c8547  mov     rbx, [rax+38h]
0x1800c854b  test    edi, edi
0x1800c854d  js      loc_1800C877F
0x1800c8553  cmp     qword ptr [r14+50h], 0
0x1800c8558  jz      loc_1800C877A
0x1800c855e  test    rbx, rbx
0x1800c8561  jz      loc_1800C877A
0x1800c8567  mov     rax, [rbx+18h]
0x1800c856b  test    rax, rax
0x1800c856e  jz      loc_1800C877A
0x1800c8574  mov     rcx, [rbx+10h]
0x1800c8578  test    rcx, rcx
0x1800c857b  jz      loc_1800C877A
0x1800c8581  cmp     qword ptr [rax+70h], 0
0x1800c8586  jz      loc_1800C877A
0x1800c858c  cmp     qword ptr [rcx+10h], 0
0x1800c8591  jz      loc_1800C877A
0x1800c8597  mov     ecx, 28h ; '('; unsigned __int64
0x1800c859c  call    ?WinMalloc@@YAPEAX_K@Z; WinMalloc(unsigned __int64)
0x1800c85a1  mov     rdi, rax
0x1800c85a4  mov     [rsp+98h+dwindex], rax
0x1800c85ac  test    rax, rax
0x1800c85af  jz      loc_1800C8773
0x1800c85b5  mov     rcx, [rbx+18h]
0x1800c85b9  mov     rax, [rbx+10h]
0x1800c85bd  lea     rdx, ??_7CRefCountedObject@@6B@; const CRefCountedObject::`vftable'
0x1800c85c4  mov     [rdi], rdx
0x1800c85c7  mov     dword ptr [rdi+8], 0
0x1800c85ce  lock inc dword ptr [rdi+8]
0x1800c85d2  lea     rdx, ??_7CStrokeWithInk@@6B@; const CStrokeWithInk::`vftable'
0x1800c85d9  mov     [rdi], rdx
0x1800c85dc  mov     [rdi+10h], rax
0x1800c85e0  mov     [rdi+18h], rcx
0x1800c85e4  test    rdi, rdi
0x1800c85e7  jz      loc_1800C8773
0x1800c85ed  mov     rcx, [rbx+18h]
0x1800c85f1  mov     rax, [rcx]
0x1800c85f4  mov     rax, [rax+8]
0x1800c85f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c85fd  mov     rax, [rbx+10h]
0x1800c8601  mov     ecx, 8
0x1800c8606  lock inc dword ptr [rax+rcx]
0x1800c860a  mov     dword ptr [rsp+98h+dwindex], 0
0x1800c8615  lea     rax, [r14-10h]
0x1800c8619  lea     rbx, [r14+40h]
0x1800c861d  test    rax, rax
0x1800c8620  cmovz   rbx, rcx
0x1800c8624  lea     rax, [rsp+98h+dwindex]
0x1800c862c  mov     [rsp+98h+lpdwindex], rax; lpdwindex
0x1800c8631  mov     r9, rbx; pHandles
0x1800c8634  lea     r8d, [rcx-7]; cHandles
0x1800c8638  or      edx, 0FFFFFFFFh; dwTimeout
0x1800c863b  xor     ecx, ecx; dwFlags
0x1800c863d  call    cs:__imp_CoWaitForMultipleHandles
0x1800c8643  mov     rcx, [r14+50h]
0x1800c8647  mov     rcx, [rcx+70h]
0x1800c864b  mov     [rsp+98h+dwindex], rcx
0x1800c8653  call    InkObj_Lock
0x1800c8658  lea     rcx, [r14+58h]
0x1800c865c  mov     rdx, rdi
0x1800c865f  call    ?InsertSortedUnique@?$CInkBasicQueue@VCStrokeWithInk@@$00$00$00@@QEAAJPEAVCStrokeWithInk@@@Z; CInkBasicQueue<CStrokeWithInk,1,1,1>::InsertSortedUnique(CStrokeWithInk *)
0x1800c8664  mov     edi, eax
0x1800c8666  lea     rcx, [rsp+98h+dwindex]; this
0x1800c866e  call    ??1CInkAutoInkLock@@QEAA@XZ; CInkAutoInkLock::~CInkAutoInkLock(void)
0x1800c8673  mov     rcx, [rbx]; hMutex
0x1800c8676  call    cs:__imp_ReleaseMutex
0x1800c867c  test    edi, edi
0x1800c867e  jnz     loc_1800C877F
0x1800c8684  lea     ecx, [rdi+3]; vt
0x1800c8687  xor     edx, edx; lLbound
0x1800c8689  lea     r8d, [rdi+1]; cElements
0x1800c868d  call    cs:__imp_SafeArrayCreateVector
0x1800c8693  mov     rbx, rax
0x1800c8696  test    rax, rax
0x1800c8699  jz      loc_1800C8773
0x1800c869f  mov     [rsp+98h+dwindex], 0
0x1800c86ab  lea     rdx, [rsp+98h+dwindex]; ppvData
0x1800c86b3  mov     rcx, rax; psa
0x1800c86b6  call    cs:__imp_SafeArrayAccessData
0x1800c86bc  mov     edi, eax
0x1800c86be  test    eax, eax
0x1800c86c0  js      loc_1800C8768
0x1800c86c6  mov     rcx, [rsi]
0x1800c86c9  mov     rax, [rcx+38h]
0x1800c86cd  mov     rdx, [rsp+98h+dwindex]
0x1800c86d5  mov     rcx, rsi
0x1800c86d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c86dd  mov     edi, eax
0x1800c86df  mov     rcx, rbx; psa
0x1800c86e2  call    cs:__imp_SafeArrayUnaccessData
0x1800c86e8  mov     esi, eax
0x1800c86ea  test    edi, edi
0x1800c86ec  js      short loc_1800C8768
0x1800c86ee  test    eax, eax
0x1800c86f0  js      short loc_1800C8766
0x1800c86f2  lea     rcx, [r14+18h]
0x1800c86f6  mov     rdx, rbx
0x1800c86f9  call    ?Fire_StrokesAdded@?$CProxy_IInkStrokesEvents@VCInkStrokes@@@@QEAAJPEAUtagSAFEARRAY@@@Z; CProxy_IInkStrokesEvents<CInkStrokes>::Fire_StrokesAdded(tagSAFEARRAY *)
0x1800c86fe  cmp     qword ptr [r14+80h], 0
0x1800c8706  jz      short loc_1800C8766
0x1800c8708  xorps   xmm0, xmm0
0x1800c870b  xor     eax, eax
0x1800c870d  movups  xmmword ptr [rsp+98h+pvarg], xmm0
0x1800c8712  mov     qword ptr [rsp+98h+pvarg+10h], rax
0x1800c8717  lea     rcx, [rsp+98h+pvarg]; pvarg
0x1800c871c  call    cs:__imp_VariantInit
0x1800c8722  mov     eax, 2003h
0x1800c8727  mov     word ptr [rsp+98h+pvarg], ax
0x1800c872c  mov     qword ptr [rsp+98h+pvarg+8], rbx
0x1800c8731  mov     rcx, [r14+80h]
0x1800c8738  add     rcx, 10h
0x1800c873c  movups  xmm0, xmmword ptr [rsp+98h+pvarg]
0x1800c8741  movaps  [rsp+98h+var_38], xmm0
0x1800c8746  movsd   xmm1, qword ptr [rsp+98h+pvarg+10h]
0x1800c874c  movsd   [rsp+98h+var_28], xmm1
0x1800c8752  mov     rax, [rcx]
0x1800c8755  lea     rdx, [rsp+98h+var_38]
0x1800c875a  mov     rax, [rax]
0x1800c875d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c8762  mov     edi, esi
0x1800c8764  jmp     short loc_1800C8768
0x1800c8766  mov     edi, esi
0x1800c8768  mov     rcx, rbx; psa
0x1800c876b  call    cs:__imp_SafeArrayDestroy
0x1800c8771  jmp     short loc_1800C877F
0x1800c8773  mov     edi, 8007000Eh
0x1800c8778  jmp     short loc_1800C877F
0x1800c877a  mov     edi, 8000FFFFh
0x1800c877f  lea     rcx, [rsp+98h+arg_10]; void *
0x1800c8787  call    ??1?$CComPtr@UITablet2@@@ATL@@QEAA@XZ; ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(void)
0x1800c878c  nop
0x1800c878d  jmp     short loc_1800C8796
0x1800c878f  mov     edi, dword ptr [rsp+98h+dwindex]
0x1800c8796  mov     eax, edi
0x1800c8798  jmp     short loc_1800C879F
0x1800c879a  mov     eax, 80004003h
0x1800c879f  mov     rbx, [rsp+98h+arg_0]
0x1800c87a7  add     rsp, 80h
0x1800c87ae  pop     r14
0x1800c87b0  pop     rdi
0x1800c87b1  pop     rsi
0x1800c87b2  retn
```
