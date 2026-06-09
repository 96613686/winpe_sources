# CInkStrokes::Remove(IInkStrokeDisp *)

- ea: `0x1800c6a10`
- end: `0x1800c6cf7`
- name: `?Remove@CInkStrokes@@UEAAJPEAUIInkStrokeDisp@@@Z`
- size: `743`
- prototype: `__int64 __fastcall(CInkStrokes *__hidden this, struct IInkStrokeDisp *)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x180001c20`
- `0x180009b64`
- `0x180026fcc`
- `0x180034e08`
- `0x1800a38dc`
- `0x1800bdbb8`
- `0x1800c51d4`
- `0x1800c60e4`
- `0x1800c6a10`
- `0x18010c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800c6ba6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800c6ba6`
- `OLEAUT32!__imp_VariantInit` at `0x1800c6c58`
- `OLEAUT32!__imp_VariantInit` at `0x1800c6c58`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800c6caa`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800c6caa`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800c6bf1`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800c6bf1`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800c6c1d`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800c6c1d`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800c6bc8`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800c6bc8`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800c6b6c`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800c6b6c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CInkStrokes::Remove(CInkStrokes *this, struct IInkStrokeDisp *a2)
{
  int v4; // edi
  __int64 v5; // r8
  const unsigned __int16 *v6; // r9
  __int64 v7; // r15
  GUID *v8; // rax
  __int64 v9; // rdx
  GUID *v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rcx
  __int64 v14; // rbx
  CRefCountedObject *v15; // r15
  SAFEARRAY *Vector; // rax
  SAFEARRAY *v17; // rbx
  HRESULT v18; // eax
  HRESULT v19; // r14d
  __int64 v20; // rcx
  unsigned int v22; // [rsp+28h] [rbp-70h]
  HINSTANCE v23; // [rsp+30h] [rbp-68h]
  VARIANTARG pvarg; // [rsp+40h] [rbp-58h] BYREF
  VARIANTARG v25; // [rsp+60h] [rbp-38h] BYREF
  void *dwindex; // [rsp+A8h] [rbp+10h] BYREF
  __int64 v27; // [rsp+B0h] [rbp+18h] BYREF

  if ( !a2 )
    return 2147500035LL;
  try
  {
    v27 = 0;
    v4 = ((__int64 (__fastcall *)(struct IInkStrokeDisp *, __int64 *))a2->lpVtbl->get_Ink)(a2, &v27);
    v7 = 0;
    if ( v27 == ((*((_QWORD *)this + 11) + 8LL) & -(__int64)(*((_QWORD *)this + 11) != 0)) )
    {
      v11 = InkDynamicCast<CInkStrokeDisp *,IInkStrokeDisp *>(a2);
      if ( v11 )
      {
        v7 = *(_QWORD *)(v11 + 56);
LABEL_10:
        if ( v4 >= 0 )
        {
          if ( *((_QWORD *)this + 11)
            && v7
            && (v12 = *(_QWORD *)(v7 + 24)) != 0
            && (v13 = *(_QWORD *)(v7 + 16)) != 0
            && *(_QWORD *)(v12 + 112)
            && *(_QWORD *)(v13 + 16) )
          {
            LODWORD(dwindex) = 0;
            v14 = (__int64)this + 72;
            if ( this == (CInkStrokes *)8 )
              v14 = 8;
            CoWaitForMultipleHandles(0, 0xFFFFFFFF, 1u, (LPHANDLE)v14, (LPDWORD)&dwindex);
            dwindex = *(void **)(*((_QWORD *)this + 11) + 112LL);
            InkObj_Lock();
            v15 = (CRefCountedObject *)CInkBasicQueue<CStrokeWithInk,1,1,1>::FindAndRemove<CStrokeWithInk>(
                                         (char *)this + 96,
                                         v7);
            CInkAutoInkLock::~CInkAutoInkLock((CInkAutoInkLock *)&dwindex);
            ReleaseMutex(*(HANDLE *)v14);
            if ( v15 )
            {
              CRefCountedObject::ReleaseReference(v15);
              Vector = SafeArrayCreateVector(3u, 0, 1u);
              v17 = Vector;
              if ( Vector )
              {
                dwindex = 0;
                v4 = SafeArrayAccessData(Vector, &dwindex);
                if ( v4 >= 0 )
                {
                  v4 = ((__int64 (__fastcall *)(struct IInkStrokeDisp *, void *))a2->lpVtbl->get_ID)(a2, dwindex);
                  v18 = SafeArrayUnaccessData(v17);
                  v19 = v18;
                  if ( v4 >= 0 )
                  {
                    if ( v18 >= 0
                      && (CProxy_IInkStrokesEvents<CInkStrokes>::Fire_StrokesRemoved((char *)this + 32, v17),
                          *((_QWORD *)this + 17)) )
                    {
                      memset(&pvarg, 0, sizeof(pvarg));
                      VariantInit(&pvarg);
                      pvarg.vt = 8195;
                      pvarg.llVal = (LONGLONG)v17;
                      v20 = *((_QWORD *)this + 17) + 16LL;
                      v25 = pvarg;
                      (*(void (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)v20 + 8LL))(v20, &v25);
                      v4 = v19;
                    }
                    else
                    {
                      v4 = v19;
                    }
                  }
                }
                SafeArrayDestroy(v17);
              }
              else
              {
                v4 = -2147024882;
              }
            }
          }
          else
          {
            v4 = -2147418113;
          }
        }
        goto LABEL_30;
      }
      v23 = hInstance;
      v22 = -2144862204;
      v8 = &IID_IInkStrokes;
      v9 = 1105;
      v10 = &GUID_NULL;
    }
    else
    {
      if ( v4 < 0 )
      {
LABEL_30:
        ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(&v27);
        return (unsigned int)v4;
      }
      v23 = hInstance;
      v22 = -2144862206;
      v8 = &IID_IInkDisp;
      v9 = 1107;
      v10 = &CLSID_InkDisp;
    }
    v4 = ATL::AtlSetErrorInfo(v10, (WCHAR *)v9, v5, v6, v8, v22, v23);
    goto LABEL_10;
  }
  catch ( ... )
  {
    LODWORD(dwindex) = ReportWispException();
    return (unsigned int)dwindex;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800c6a10  mov     r11, rsp
0x1800c6a13  mov     [r11+8], rbx
0x1800c6a17  mov     [r11+20h], rsi
0x1800c6a1b  push    rdi
0x1800c6a1c  push    r14
0x1800c6a1e  push    r15
0x1800c6a20  sub     rsp, 80h
0x1800c6a27  mov     r14, rdx
0x1800c6a2a  mov     rsi, rcx
0x1800c6a2d  test    rdx, rdx
0x1800c6a30  jz      loc_1800C6CD9
0x1800c6a36  mov     qword ptr [r11+18h], 0
0x1800c6a3e  mov     rax, [rdx]
0x1800c6a41  lea     rdx, [r11+18h]
0x1800c6a45  mov     rcx, r14
0x1800c6a48  mov     rax, [rax+58h]
0x1800c6a4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6a51  mov     edi, eax
0x1800c6a53  mov     rax, [rsi+58h]
0x1800c6a57  xor     r15d, r15d
0x1800c6a5a  lea     rcx, [rax+8]
0x1800c6a5e  neg     rax
0x1800c6a61  sbb     rax, rax
0x1800c6a64  and     rax, rcx
0x1800c6a67  cmp     [rsp+98h+arg_10], rax
0x1800c6a6f  jz      short loc_1800C6AA2
0x1800c6a71  test    edi, edi
0x1800c6a73  js      loc_1800C6CBE
0x1800c6a79  mov     rax, cs:hInstance
0x1800c6a80  mov     [rsp+98h+var_68], rax
0x1800c6a85  mov     [rsp+98h+var_70], 80280002h
0x1800c6a8d  lea     rax, IID_IInkDisp
0x1800c6a94  mov     edx, 453h
0x1800c6a99  lea     rcx, CLSID_InkDisp
0x1800c6aa0  jmp     short loc_1800C6AD6
0x1800c6aa2  mov     rcx, r14
0x1800c6aa5  call    ??$InkDynamicCast@PEAVCInkStrokeDisp@@PEAUIInkStrokeDisp@@@@YAPEAVCInkStrokeDisp@@PEAUIInkStrokeDisp@@@Z; InkDynamicCast<CInkStrokeDisp *,IInkStrokeDisp *>(IInkStrokeDisp *)
0x1800c6aaa  test    rax, rax
0x1800c6aad  jnz     short loc_1800C6AE4
0x1800c6aaf  mov     rax, cs:hInstance
0x1800c6ab6  mov     [rsp+98h+var_68], rax; HINSTANCE
0x1800c6abb  mov     [rsp+98h+var_70], 80280004h; int
0x1800c6ac3  lea     rax, IID_IInkStrokes
0x1800c6aca  mov     edx, 451h; unsigned __int16 *
0x1800c6acf  lea     rcx, GUID_NULL; clsid
0x1800c6ad6  mov     [rsp+98h+lpdwindex], rax; struct _GUID *
0x1800c6adb  call    ?AtlSetErrorInfo@ATL@@YAJAEBU_GUID@@PEBGK10JPEAUHINSTANCE__@@@Z; ATL::AtlSetErrorInfo(_GUID const &,ushort const *,ulong,ushort const *,_GUID const &,long,HINSTANCE__ *)
0x1800c6ae0  mov     edi, eax
0x1800c6ae2  jmp     short loc_1800C6AE8
0x1800c6ae4  mov     r15, [rax+38h]
0x1800c6ae8  test    edi, edi
0x1800c6aea  js      loc_1800C6CBE
0x1800c6af0  cmp     qword ptr [rsi+58h], 0
0x1800c6af5  jz      loc_1800C6CB9
0x1800c6afb  test    r15, r15
0x1800c6afe  jz      loc_1800C6CB9
0x1800c6b04  mov     rax, [r15+18h]
0x1800c6b08  test    rax, rax
0x1800c6b0b  jz      loc_1800C6CB9
0x1800c6b11  mov     rcx, [r15+10h]
0x1800c6b15  test    rcx, rcx
0x1800c6b18  jz      loc_1800C6CB9
0x1800c6b1e  cmp     qword ptr [rax+70h], 0
0x1800c6b23  jz      loc_1800C6CB9
0x1800c6b29  cmp     qword ptr [rcx+10h], 0
0x1800c6b2e  jz      loc_1800C6CB9
0x1800c6b34  mov     dword ptr [rsp+98h+dwindex], 0
0x1800c6b3f  lea     rax, [rsi-8]
0x1800c6b43  lea     rbx, [rsi+48h]
0x1800c6b47  mov     ecx, 8
0x1800c6b4c  test    rax, rax
0x1800c6b4f  cmovz   rbx, rcx
0x1800c6b53  lea     rax, [rsp+98h+dwindex]
0x1800c6b5b  mov     [rsp+98h+lpdwindex], rax; lpdwindex
0x1800c6b60  mov     r9, rbx; pHandles
0x1800c6b63  lea     r8d, [rcx-7]; cHandles
0x1800c6b67  or      edx, 0FFFFFFFFh; dwTimeout
0x1800c6b6a  xor     ecx, ecx; dwFlags
0x1800c6b6c  call    cs:__imp_CoWaitForMultipleHandles
0x1800c6b72  mov     rcx, [rsi+58h]
0x1800c6b76  mov     rcx, [rcx+70h]
0x1800c6b7a  mov     [rsp+98h+dwindex], rcx
0x1800c6b82  call    InkObj_Lock
0x1800c6b87  lea     rcx, [rsi+60h]
0x1800c6b8b  mov     rdx, r15
0x1800c6b8e  call    ??$FindAndRemove@VCStrokeWithInk@@@?$CInkBasicQueue@VCStrokeWithInk@@$00$00$00@@QEAAPEAVCStrokeWithInk@@AEAV1@@Z; CInkBasicQueue<CStrokeWithInk,1,1,1>::FindAndRemove<CStrokeWithInk>(CStrokeWithInk &)
0x1800c6b93  mov     r15, rax
0x1800c6b96  lea     rcx, [rsp+98h+dwindex]; this
0x1800c6b9e  call    ??1CInkAutoInkLock@@QEAA@XZ; CInkAutoInkLock::~CInkAutoInkLock(void)
0x1800c6ba3  mov     rcx, [rbx]; hMutex
0x1800c6ba6  call    cs:__imp_ReleaseMutex
0x1800c6bac  test    r15, r15
0x1800c6baf  jz      loc_1800C6CBE
0x1800c6bb5  mov     rcx, r15; this
0x1800c6bb8  call    ?ReleaseReference@CRefCountedObject@@QEAAXXZ; CRefCountedObject::ReleaseReference(void)
0x1800c6bbd  mov     ecx, 3; vt
0x1800c6bc2  xor     edx, edx; lLbound
0x1800c6bc4  lea     r8d, [rcx-2]; cElements
0x1800c6bc8  call    cs:__imp_SafeArrayCreateVector
0x1800c6bce  mov     rbx, rax
0x1800c6bd1  test    rax, rax
0x1800c6bd4  jz      loc_1800C6CB2
0x1800c6bda  mov     [rsp+98h+dwindex], 0
0x1800c6be6  lea     rdx, [rsp+98h+dwindex]; ppvData
0x1800c6bee  mov     rcx, rax; psa
0x1800c6bf1  call    cs:__imp_SafeArrayAccessData
0x1800c6bf7  mov     edi, eax
0x1800c6bf9  test    eax, eax
0x1800c6bfb  js      loc_1800C6CA7
0x1800c6c01  mov     rcx, [r14]
0x1800c6c04  mov     rax, [rcx+38h]
0x1800c6c08  mov     rdx, [rsp+98h+dwindex]
0x1800c6c10  mov     rcx, r14
0x1800c6c13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6c18  mov     edi, eax
0x1800c6c1a  mov     rcx, rbx; psa
0x1800c6c1d  call    cs:__imp_SafeArrayUnaccessData
0x1800c6c23  mov     r14d, eax
0x1800c6c26  test    edi, edi
0x1800c6c28  js      short loc_1800C6CA7
0x1800c6c2a  test    eax, eax
0x1800c6c2c  js      short loc_1800C6CA4
0x1800c6c2e  lea     rcx, [rsi+20h]
0x1800c6c32  mov     rdx, rbx
0x1800c6c35  call    ?Fire_StrokesRemoved@?$CProxy_IInkStrokesEvents@VCInkStrokes@@@@QEAAJPEAUtagSAFEARRAY@@@Z; CProxy_IInkStrokesEvents<CInkStrokes>::Fire_StrokesRemoved(tagSAFEARRAY *)
0x1800c6c3a  cmp     qword ptr [rsi+88h], 0
0x1800c6c42  jz      short loc_1800C6CA4
0x1800c6c44  xorps   xmm0, xmm0
0x1800c6c47  xor     eax, eax
0x1800c6c49  movups  xmmword ptr [rsp+98h+pvarg], xmm0
0x1800c6c4e  mov     qword ptr [rsp+98h+pvarg+10h], rax
0x1800c6c53  lea     rcx, [rsp+98h+pvarg]; pvarg
0x1800c6c58  call    cs:__imp_VariantInit
0x1800c6c5e  mov     eax, 2003h
0x1800c6c63  mov     word ptr [rsp+98h+pvarg], ax
0x1800c6c68  mov     qword ptr [rsp+98h+pvarg+8], rbx
0x1800c6c6d  mov     rcx, [rsi+88h]
0x1800c6c74  add     rcx, 10h
0x1800c6c78  movups  xmm0, xmmword ptr [rsp+98h+pvarg]
0x1800c6c7d  movaps  [rsp+98h+var_38], xmm0
0x1800c6c82  movsd   xmm1, qword ptr [rsp+98h+pvarg+10h]
0x1800c6c88  movsd   [rsp+98h+var_28], xmm1
0x1800c6c8e  mov     rax, [rcx]
0x1800c6c91  lea     rdx, [rsp+98h+var_38]
0x1800c6c96  mov     rax, [rax+8]
0x1800c6c9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6c9f  mov     edi, r14d
0x1800c6ca2  jmp     short loc_1800C6CA7
0x1800c6ca4  mov     edi, r14d
0x1800c6ca7  mov     rcx, rbx; psa
0x1800c6caa  call    cs:__imp_SafeArrayDestroy
0x1800c6cb0  jmp     short loc_1800C6CBE
0x1800c6cb2  mov     edi, 8007000Eh
0x1800c6cb7  jmp     short loc_1800C6CBE
0x1800c6cb9  mov     edi, 8000FFFFh
0x1800c6cbe  lea     rcx, [rsp+98h+arg_10]; void *
0x1800c6cc6  call    ??1?$CComPtr@UITablet2@@@ATL@@QEAA@XZ; ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(void)
0x1800c6ccb  nop
0x1800c6ccc  jmp     short loc_1800C6CD5
0x1800c6cce  mov     edi, dword ptr [rsp+98h+dwindex]
0x1800c6cd5  mov     eax, edi
0x1800c6cd7  jmp     short loc_1800C6CDE
0x1800c6cd9  mov     eax, 80004003h
0x1800c6cde  lea     r11, [rsp+98h+var_18]
0x1800c6ce6  mov     rbx, [r11+20h]
0x1800c6cea  mov     rsi, [r11+38h]
0x1800c6cee  mov     rsp, r11
0x1800c6cf1  pop     r15
0x1800c6cf3  pop     r14
0x1800c6cf5  pop     rdi
0x1800c6cf6  retn
```
