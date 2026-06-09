# CInkStrokes::RemoveStrokes(IInkStrokes *)

- ea: `0x1800c6db0`
- end: `0x1800c71de`
- name: `?RemoveStrokes@CInkStrokes@@UEAAJPEAUIInkStrokes@@@Z`
- size: `1070`
- prototype: `__int64 __fastcall(CInkStrokes *__hidden this, struct IInkStrokes *)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180001c20`
- `0x180009b64`
- `0x180026fcc`
- `0x180030950`
- `0x180034e08`
- `0x18007dcf4`
- `0x1800a38dc`
- `0x1800bdbec`
- `0x1800c51d4`
- `0x1800c5a74`
- `0x1800c60e4`
- `0x1800c66b0`
- `0x1800c6db0`
- `0x18010c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800c6f2a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800c70c1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800c6f2a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800c70c1`
- `OLEAUT32!__imp_VariantInit` at `0x1800c7139`
- `OLEAUT32!__imp_VariantInit` at `0x1800c7139`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800c7190`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800c7190`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800c6f66`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800c6f66`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800c70ca`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800c70ca`
- `OLEAUT32!__imp_SafeArrayRedim` at `0x1800c70fb`
- `OLEAUT32!__imp_SafeArrayRedim` at `0x1800c70fb`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800c6f4c`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800c6f4c`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800c6eda`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800c6fb4`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800c6eda`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800c6fb4`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CInkStrokes::RemoveStrokes(CInkStrokes *this, struct IInkStrokes *a2)
{
  __int64 v4; // r12
  int Id; // ebx
  __int64 v6; // r8
  const unsigned __int16 *v7; // r9
  __int64 v8; // rdx
  GUID *v9; // rcx
  __int64 v10; // rax
  __int64 v11; // rbx
  HANDLE *v12; // r14
  int v13; // eax
  unsigned int v14; // esi
  SAFEARRAY *Vector; // rax
  SAFEARRAY *v16; // rsi
  ULONG v17; // r15d
  __int64 v18; // rax
  __int64 v19; // r13
  __int64 v20; // r14
  CRefCountedObject *v21; // rax
  __int64 v22; // r14
  ULONG v23; // r12d
  HRESULT v24; // eax
  __int64 v25; // rcx
  unsigned int v27; // [rsp+28h] [rbp-C0h]
  HINSTANCE v28; // [rsp+30h] [rbp-B8h]
  VARIANTARG pvarg; // [rsp+40h] [rbp-A8h] BYREF
  void *ppvData; // [rsp+58h] [rbp-90h] BYREF
  __int128 v31; // [rsp+60h] [rbp-88h] BYREF
  ULONG cElements; // [rsp+70h] [rbp-78h]
  __int64 v33; // [rsp+78h] [rbp-70h] BYREF
  HANDLE *v34; // [rsp+80h] [rbp-68h]
  VARIANTARG v35; // [rsp+90h] [rbp-58h] BYREF
  SAFEARRAYBOUND dwindex; // [rsp+F8h] [rbp+10h] BYREF
  __int64 v37; // [rsp+100h] [rbp+18h]
  __int64 v38; // [rsp+108h] [rbp+20h] BYREF

  v4 = 0;
  if ( !a2 )
    return 2147500035LL;
  try
  {
    v38 = 0;
    Id = ((__int64 (__fastcall *)(struct IInkStrokes *, __int64 *))a2->lpVtbl->get_Ink)(a2, &v38);
    if ( v38 == ((*((_QWORD *)this + 11) + 8LL) & -(__int64)(*((_QWORD *)this + 11) != 0)) )
    {
      v10 = InkDynamicCast<CInkStrokes *,IInkStrokes *>(a2);
      v11 = v10;
      if ( v10 )
      {
        if ( *((_QWORD *)this + 11) && *(_QWORD *)(v10 + 96) )
        {
          ppvData = 0;
          v31 = 0;
          cElements = 0;
          v37 = v10 + 72;
          dwindex.cElements = 0;
          v12 = (HANDLE *)(v10 + 80);
          CoWaitForMultipleHandles(0, 0xFFFFFFFF, 1u, (LPHANDLE)(v10 + 80), (LPDWORD)&dwindex);
          dwindex = *(SAFEARRAYBOUND *)(*((_QWORD *)this + 11) + 112LL);
          InkObj_Lock();
          v13 = CInkBasicQueue<CStrokeWithInk,1,1,1>::CopyAllToUnique(v11 + 104, &v31, 0);
          Id = -2147024882;
          v14 = v13 != 1 ? 0x8007000E : 0;
          CInkAutoInkLock::~CInkAutoInkLock((CInkAutoInkLock *)&dwindex);
          ReleaseMutex(*v12);
          LODWORD(v37) = cElements;
          if ( cElements )
          {
            Vector = SafeArrayCreateVector(3u, 0, cElements);
            v16 = Vector;
            if ( Vector )
            {
              Id = SafeArrayAccessData(Vector, &ppvData);
              if ( Id >= 0 )
              {
                v17 = 0;
                dwindex.cElements = 0;
                v18 = (__int64)this + 72;
                if ( this == (CInkStrokes *)8 )
                  v18 = 8;
                v34 = (HANDLE *)v18;
                CoWaitForMultipleHandles(0, 0xFFFFFFFF, 1u, (LPHANDLE)v18, (LPDWORD)&dwindex);
                v33 = *(_QWORD *)(*((_QWORD *)this + 11) + 112LL);
                InkObj_Lock();
                memset(&pvarg, 0, 20);
                v19 = *((_QWORD *)this + 12);
                if ( v19 )
                {
                  do
                  {
                    if ( !(_QWORD)v31 )
                      break;
                    v20 = *(_QWORD *)(v19 + 32);
                    v21 = (CRefCountedObject *)CInkBasicQueue<CStrokeWithInk,1,1,1>::FindAndRemove<CStrokeWithInk>(
                                                 &v31,
                                                 v19);
                    if ( v21 )
                    {
                      CRefCountedObject::ReleaseReference(v21);
                      if ( *((_QWORD *)this + 12) == v19 )
                        *((_QWORD *)this + 12) = v20;
                      if ( !v20 )
                        *((_QWORD *)this + 13) = v4;
                      if ( v4 )
                        *(_QWORD *)(v4 + 32) = v20;
                      CInkBasicQueue<CStrokeWithInk,1,1,1>::InsertTail(&pvarg, v19);
                      --*((_DWORD *)this + 28);
                    }
                    else
                    {
                      v4 = v19;
                    }
                    v19 = v20;
                  }
                  while ( v20 );
                }
                v22 = *(_QWORD *)&pvarg.vt;
                if ( *(_QWORD *)&pvarg.vt )
                {
                  v23 = v37;
                  do
                  {
                    if ( v17 >= v23 || Id < 0 )
                      break;
                    dwindex.cElements = 0;
                    Id = InkStroke_GetId(*(_QWORD *)(*(_QWORD *)(v22 + 16) + 16LL), &dwindex);
                    if ( Id >= 0 )
                    {
                      *((_DWORD *)ppvData + v17++) = dwindex.cElements;
                      v22 = *(_QWORD *)(v22 + 32);
                    }
                  }
                  while ( v22 );
                }
                CInkBasicQueue<CStrokeWithInk,1,1,1>::~CInkBasicQueue<CStrokeWithInk,1,1,1>(&pvarg);
                CInkAutoInkLock::~CInkAutoInkLock((CInkAutoInkLock *)&v33);
                ReleaseMutex(*v34);
                v24 = SafeArrayUnaccessData(v16);
                if ( Id >= 0 )
                {
                  if ( v24 < 0 )
                  {
                    Id = v24;
                  }
                  else
                  {
                    dwindex.cElements = v17;
                    dwindex.lLbound = 0;
                    Id = SafeArrayRedim(v16, &dwindex);
                    if ( Id >= 0 )
                    {
                      if ( v17 )
                        CProxy_IInkStrokesEvents<CInkStrokes>::Fire_StrokesRemoved((char *)this + 32, v16);
                      if ( *((_QWORD *)this + 17) )
                      {
                        memset(&pvarg, 0, sizeof(pvarg));
                        VariantInit(&pvarg);
                        pvarg.vt = 8195;
                        pvarg.llVal = (LONGLONG)v16;
                        v25 = *((_QWORD *)this + 17) + 16LL;
                        v35 = pvarg;
                        (*(void (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)v25 + 8LL))(v25, &v35);
                      }
                    }
                  }
                }
              }
              SafeArrayDestroy(v16);
            }
          }
          else
          {
            Id = v14;
          }
          CInkBasicQueue<CStrokeWithInk,1,1,1>::~CInkBasicQueue<CStrokeWithInk,1,1,1>(&v31);
        }
        else
        {
          Id = -2147418113;
        }
        goto LABEL_47;
      }
      v28 = hInstance;
      v27 = -2144862204;
      v8 = 1105;
      v9 = &GUID_NULL;
    }
    else
    {
      if ( Id < 0 )
      {
LABEL_47:
        ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(&v38);
        return (unsigned int)Id;
      }
      v28 = hInstance;
      v27 = -2144862206;
      v8 = 1107;
      v9 = &CLSID_InkStrokes;
    }
    Id = ATL::AtlSetErrorInfo(v9, (WCHAR *)v8, v6, v7, &IID_IInkStrokes, v27, v28);
    goto LABEL_47;
  }
  catch ( ... )
  {
    dwindex.cElements = ReportWispException();
    return dwindex.cElements;
  }
  return (unsigned int)Id;
}

```

## disassembly

```asm
0x1800c6db0  mov     r11, rsp
0x1800c6db3  push    rbx
0x1800c6db4  push    rsi
0x1800c6db5  push    rdi
0x1800c6db6  push    r12
0x1800c6db8  push    r13
0x1800c6dba  push    r14
0x1800c6dbc  push    r15
0x1800c6dbe  sub     rsp, 0B0h
0x1800c6dc5  mov     rsi, rdx
0x1800c6dc8  mov     rdi, rcx
0x1800c6dcb  xor     r12d, r12d
0x1800c6dce  test    rdx, rdx
0x1800c6dd1  jz      loc_1800C71C6
0x1800c6dd7  mov     [r11+20h], r12
0x1800c6ddb  mov     rax, [rdx]
0x1800c6dde  lea     rdx, [r11+20h]
0x1800c6de2  mov     rcx, rsi
0x1800c6de5  mov     rax, [rax+48h]
0x1800c6de9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6dee  mov     ebx, eax
0x1800c6df0  mov     rax, [rdi+58h]
0x1800c6df4  lea     rcx, [rax+8]
0x1800c6df8  neg     rax
0x1800c6dfb  sbb     rax, rax
0x1800c6dfe  and     rax, rcx
0x1800c6e01  cmp     [rsp+0E8h+arg_18], rax
0x1800c6e09  jz      short loc_1800C6E35
0x1800c6e0b  test    ebx, ebx
0x1800c6e0d  js      loc_1800C71AB
0x1800c6e13  mov     rax, cs:hInstance
0x1800c6e1a  mov     [rsp+0E8h+var_B8], rax
0x1800c6e1f  mov     [rsp+0E8h+var_C0], 80280002h
0x1800c6e27  mov     edx, 453h
0x1800c6e2c  lea     rcx, CLSID_InkStrokes
0x1800c6e33  jmp     short loc_1800C6E65
0x1800c6e35  mov     rcx, rsi
0x1800c6e38  call    ??$InkDynamicCast@PEAVCInkStrokes@@PEAUIInkStrokes@@@@YAPEAVCInkStrokes@@PEAUIInkStrokes@@@Z; InkDynamicCast<CInkStrokes *,IInkStrokes *>(IInkStrokes *)
0x1800c6e3d  mov     rbx, rax
0x1800c6e40  test    rax, rax
0x1800c6e43  jnz     short loc_1800C6E7D
0x1800c6e45  mov     rax, cs:hInstance
0x1800c6e4c  mov     [rsp+0E8h+var_B8], rax; HINSTANCE
0x1800c6e51  mov     [rsp+0E8h+var_C0], 80280004h; int
0x1800c6e59  mov     edx, 451h; unsigned __int16 *
0x1800c6e5e  lea     rcx, GUID_NULL; clsid
0x1800c6e65  lea     rax, IID_IInkStrokes
0x1800c6e6c  mov     [rsp+0E8h+lpdwindex], rax; struct _GUID *
0x1800c6e71  call    ?AtlSetErrorInfo@ATL@@YAJAEBU_GUID@@PEBGK10JPEAUHINSTANCE__@@@Z; ATL::AtlSetErrorInfo(_GUID const &,ushort const *,ulong,ushort const *,_GUID const &,long,HINSTANCE__ *)
0x1800c6e76  mov     ebx, eax
0x1800c6e78  jmp     loc_1800C71AB
0x1800c6e7d  cmp     [rdi+58h], r12
0x1800c6e81  jz      loc_1800C71A6
0x1800c6e87  cmp     [rax+60h], r12
0x1800c6e8b  jz      loc_1800C71A6
0x1800c6e91  mov     [rsp+0E8h+ppvData], r12
0x1800c6e96  xorps   xmm0, xmm0
0x1800c6e99  movdqu  [rsp+0E8h+var_88], xmm0
0x1800c6e9f  mov     [rsp+0E8h+cElements], r12d
0x1800c6ea4  add     rax, 48h ; 'H'
0x1800c6ea8  mov     [rsp+0E8h+arg_10], rax
0x1800c6eb0  mov     dword ptr [rsp+0E8h+dwindex], r12d
0x1800c6eb8  lea     r14, [rbx+50h]
0x1800c6ebc  lea     rax, [rsp+0E8h+dwindex]
0x1800c6ec4  mov     [rsp+0E8h+lpdwindex], rax; lpdwindex
0x1800c6ec9  mov     r9, r14; pHandles
0x1800c6ecc  mov     r13d, 1
0x1800c6ed2  mov     r8d, r13d; cHandles
0x1800c6ed5  or      edx, 0FFFFFFFFh; dwTimeout
0x1800c6ed8  xor     ecx, ecx; dwFlags
0x1800c6eda  call    cs:__imp_CoWaitForMultipleHandles
0x1800c6ee0  nop
0x1800c6ee1  mov     rcx, [rdi+58h]
0x1800c6ee5  mov     rcx, [rcx+70h]
0x1800c6ee9  mov     [rsp+0E8h+dwindex], rcx
0x1800c6ef1  call    InkObj_Lock
0x1800c6ef6  nop
0x1800c6ef7  lea     rcx, [rbx+68h]
0x1800c6efb  xor     r8d, r8d
0x1800c6efe  lea     rdx, [rsp+0E8h+var_88]
0x1800c6f03  call    ?CopyAllToUnique@?$CInkBasicQueue@VCStrokeWithInk@@$00$00$00@@QEAAHAEAV1@PEAV1@@Z; CInkBasicQueue<CStrokeWithInk,1,1,1>::CopyAllToUnique(CInkBasicQueue<CStrokeWithInk,1,1,1> &,CInkBasicQueue<CStrokeWithInk,1,1,1> *)
0x1800c6f08  nop
0x1800c6f09  mov     edx, r13d
0x1800c6f0c  sub     edx, eax
0x1800c6f0e  neg     edx
0x1800c6f10  sbb     esi, esi
0x1800c6f12  mov     ebx, 8007000Eh
0x1800c6f17  and     esi, ebx
0x1800c6f19  lea     rcx, [rsp+0E8h+dwindex]; this
0x1800c6f21  call    ??1CInkAutoInkLock@@QEAA@XZ; CInkAutoInkLock::~CInkAutoInkLock(void)
0x1800c6f26  nop
0x1800c6f27  mov     rcx, [r14]; hMutex
0x1800c6f2a  call    cs:__imp_ReleaseMutex
0x1800c6f30  mov     eax, [rsp+0E8h+cElements]
0x1800c6f34  mov     dword ptr [rsp+0E8h+arg_10], eax
0x1800c6f3b  test    eax, eax
0x1800c6f3d  jz      loc_1800C7198
0x1800c6f43  lea     ecx, [r13+2]; vt
0x1800c6f47  mov     r8d, eax; cElements
0x1800c6f4a  xor     edx, edx; lLbound
0x1800c6f4c  call    cs:__imp_SafeArrayCreateVector
0x1800c6f52  mov     rsi, rax
0x1800c6f55  test    rax, rax
0x1800c6f58  jz      loc_1800C719A
0x1800c6f5e  lea     rdx, [rsp+0E8h+ppvData]; ppvData
0x1800c6f63  mov     rcx, rax; psa
0x1800c6f66  call    cs:__imp_SafeArrayAccessData
0x1800c6f6c  mov     ebx, eax
0x1800c6f6e  test    eax, eax
0x1800c6f70  js      loc_1800C718D
0x1800c6f76  mov     r15d, r12d
0x1800c6f79  mov     dword ptr [rsp+0E8h+dwindex], r12d
0x1800c6f81  lea     rcx, [rdi-8]
0x1800c6f85  lea     rax, [rdi+48h]
0x1800c6f89  lea     edx, [r13+7]
0x1800c6f8d  test    rcx, rcx
0x1800c6f90  cmovz   rax, rdx
0x1800c6f94  mov     [rsp+0E8h+var_68], rax
0x1800c6f9c  lea     rcx, [rsp+0E8h+dwindex]
0x1800c6fa4  mov     [rsp+0E8h+lpdwindex], rcx; lpdwindex
0x1800c6fa9  mov     r9, rax; pHandles
0x1800c6fac  mov     r8d, r13d; cHandles
0x1800c6faf  or      edx, 0FFFFFFFFh; dwTimeout
0x1800c6fb2  xor     ecx, ecx; dwFlags
0x1800c6fb4  call    cs:__imp_CoWaitForMultipleHandles
0x1800c6fba  mov     rcx, [rdi+58h]
0x1800c6fbe  mov     rcx, [rcx+70h]
0x1800c6fc2  mov     [rsp+0E8h+var_70], rcx
0x1800c6fc7  call    InkObj_Lock
0x1800c6fcc  xorps   xmm0, xmm0
0x1800c6fcf  movdqu  xmmword ptr [rsp+0E8h+pvarg], xmm0
0x1800c6fd5  mov     dword ptr [rsp+0E8h+pvarg+10h], r12d
0x1800c6fda  mov     r13, [rdi+60h]
0x1800c6fde  test    r13, r13
0x1800c6fe1  jz      short loc_1800C7042
0x1800c6fe3  cmp     qword ptr [rsp+0E8h+var_88], r15
0x1800c6fe8  jz      short loc_1800C7042
0x1800c6fea  mov     r14, [r13+20h]
0x1800c6fee  mov     rdx, r13
0x1800c6ff1  lea     rcx, [rsp+0E8h+var_88]
0x1800c6ff6  call    ??$FindAndRemove@VCStrokeWithInk@@@?$CInkBasicQueue@VCStrokeWithInk@@$00$00$00@@QEAAPEAVCStrokeWithInk@@AEAV1@@Z; CInkBasicQueue<CStrokeWithInk,1,1,1>::FindAndRemove<CStrokeWithInk>(CStrokeWithInk &)
0x1800c6ffb  test    rax, rax
0x1800c6ffe  jz      short loc_1800C7037
0x1800c7000  mov     rcx, rax; this
0x1800c7003  call    ?ReleaseReference@CRefCountedObject@@QEAAXXZ; CRefCountedObject::ReleaseReference(void)
0x1800c7008  cmp     [rdi+60h], r13
0x1800c700c  jnz     short loc_1800C7012
0x1800c700e  mov     [rdi+60h], r14
0x1800c7012  test    r14, r14
0x1800c7015  jnz     short loc_1800C701B
0x1800c7017  mov     [rdi+68h], r12
0x1800c701b  test    r12, r12
0x1800c701e  jz      short loc_1800C7025
0x1800c7020  mov     [r12+20h], r14
0x1800c7025  mov     rdx, r13
0x1800c7028  lea     rcx, [rsp+0E8h+pvarg]
0x1800c702d  call    ?InsertTail@?$CInkBasicQueue@VCStrokeWithInk@@$00$00$00@@QEAAXPEAVCStrokeWithInk@@@Z; CInkBasicQueue<CStrokeWithInk,1,1,1>::InsertTail(CStrokeWithInk *)
0x1800c7032  dec     dword ptr [rdi+70h]
0x1800c7035  jmp     short loc_1800C703A
0x1800c7037  mov     r12, r13
0x1800c703a  mov     r13, r14
0x1800c703d  test    r14, r14
0x1800c7040  jnz     short loc_1800C6FE3
0x1800c7042  mov     r14, qword ptr [rsp+0E8h+pvarg]
0x1800c7047  xor     r13d, r13d
0x1800c704a  test    r14, r14
0x1800c704d  jz      short loc_1800C70A2
0x1800c704f  mov     r12d, dword ptr [rsp+0E8h+arg_10]
0x1800c7057  cmp     r15d, r12d
0x1800c705a  jnb     short loc_1800C70A2
0x1800c705c  test    ebx, ebx
0x1800c705e  js      short loc_1800C70A2
0x1800c7060  mov     dword ptr [rsp+0E8h+dwindex], r13d
0x1800c7068  mov     rcx, [r14+10h]
0x1800c706c  lea     rdx, [rsp+0E8h+dwindex]
0x1800c7074  mov     rcx, [rcx+10h]
0x1800c7078  call    InkStroke_GetId
0x1800c707d  mov     ebx, eax
0x1800c707f  test    eax, eax
0x1800c7081  js      short loc_1800C709D
0x1800c7083  mov     r8d, r15d
0x1800c7086  mov     rdx, [rsp+0E8h+ppvData]
0x1800c708b  mov     eax, dword ptr [rsp+0E8h+dwindex]
0x1800c7092  mov     [rdx+r8*4], eax
0x1800c7096  inc     r15d
0x1800c7099  mov     r14, [r14+20h]
0x1800c709d  test    r14, r14
0x1800c70a0  jnz     short loc_1800C7057
0x1800c70a2  lea     rcx, [rsp+0E8h+pvarg]
0x1800c70a7  call    ??1?$CInkBasicQueue@VCStrokeWithInk@@$00$00$00@@QEAA@XZ; CInkBasicQueue<CStrokeWithInk,1,1,1>::~CInkBasicQueue<CStrokeWithInk,1,1,1>(void)
0x1800c70ac  lea     rcx, [rsp+0E8h+var_70]; this
0x1800c70b1  call    ??1CInkAutoInkLock@@QEAA@XZ; CInkAutoInkLock::~CInkAutoInkLock(void)
0x1800c70b6  mov     rcx, [rsp+0E8h+var_68]
0x1800c70be  mov     rcx, [rcx]; hMutex
0x1800c70c1  call    cs:__imp_ReleaseMutex
0x1800c70c7  mov     rcx, rsi; psa
0x1800c70ca  call    cs:__imp_SafeArrayUnaccessData
0x1800c70d0  test    ebx, ebx
0x1800c70d2  js      loc_1800C718D
0x1800c70d8  test    eax, eax
0x1800c70da  js      loc_1800C718B
0x1800c70e0  mov     dword ptr [rsp+0E8h+dwindex], r15d
0x1800c70e8  mov     dword ptr [rsp+0E8h+dwindex+4], r13d
0x1800c70f0  lea     rdx, [rsp+0E8h+dwindex]; psaboundNew
0x1800c70f8  mov     rcx, rsi; psa
0x1800c70fb  call    cs:__imp_SafeArrayRedim
0x1800c7101  mov     ebx, eax
0x1800c7103  test    eax, eax
0x1800c7105  js      loc_1800C718D
0x1800c710b  test    r15d, r15d
0x1800c710e  jz      short loc_1800C711C
0x1800c7110  lea     rcx, [rdi+20h]
0x1800c7114  mov     rdx, rsi
0x1800c7117  call    ?Fire_StrokesRemoved@?$CProxy_IInkStrokesEvents@VCInkStrokes@@@@QEAAJPEAUtagSAFEARRAY@@@Z; CProxy_IInkStrokesEvents<CInkStrokes>::Fire_StrokesRemoved(tagSAFEARRAY *)
0x1800c711c  cmp     [rdi+88h], r13
0x1800c7123  jz      short loc_1800C718D
0x1800c7125  xorps   xmm0, xmm0
0x1800c7128  xor     eax, eax
0x1800c712a  movups  xmmword ptr [rsp+0E8h+pvarg], xmm0
0x1800c712f  mov     qword ptr [rsp+0E8h+pvarg+10h], rax
0x1800c7134  lea     rcx, [rsp+0E8h+pvarg]; pvarg
0x1800c7139  call    cs:__imp_VariantInit
0x1800c713f  mov     eax, 2003h
0x1800c7144  mov     word ptr [rsp+0E8h+pvarg], ax
0x1800c7149  mov     qword ptr [rsp+0E8h+pvarg+8], rsi
0x1800c714e  mov     rcx, [rdi+88h]
0x1800c7155  add     rcx, 10h
0x1800c7159  movups  xmm0, xmmword ptr [rsp+0E8h+pvarg]
0x1800c715e  movaps  [rsp+0E8h+var_58], xmm0
0x1800c7166  movsd   xmm1, qword ptr [rsp+0E8h+pvarg+10h]
0x1800c716c  movsd   [rsp+0E8h+var_48], xmm1
0x1800c7175  mov     rax, [rcx]
0x1800c7178  lea     rdx, [rsp+0E8h+var_58]
0x1800c7180  mov     rax, [rax+8]
0x1800c7184  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c7189  jmp     short loc_1800C718D
0x1800c718b  mov     ebx, eax
0x1800c718d  mov     rcx, rsi; psa
0x1800c7190  call    cs:__imp_SafeArrayDestroy
0x1800c7196  jmp     short loc_1800C719A
0x1800c7198  mov     ebx, esi
0x1800c719a  lea     rcx, [rsp+0E8h+var_88]
0x1800c719f  call    ??1?$CInkBasicQueue@VCStrokeWithInk@@$00$00$00@@QEAA@XZ; CInkBasicQueue<CStrokeWithInk,1,1,1>::~CInkBasicQueue<CStrokeWithInk,1,1,1>(void)
0x1800c71a4  jmp     short loc_1800C71AB
0x1800c71a6  mov     ebx, 8000FFFFh
0x1800c71ab  lea     rcx, [rsp+0E8h+arg_18]; void *
0x1800c71b3  call    ??1?$CComPtr@UITablet2@@@ATL@@QEAA@XZ; ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(void)
0x1800c71b8  nop
0x1800c71b9  jmp     short loc_1800C71C2
0x1800c71bb  mov     ebx, dword ptr [rsp+0E8h+dwindex]
0x1800c71c2  mov     eax, ebx
0x1800c71c4  jmp     short loc_1800C71CB
0x1800c71c6  mov     eax, 80004003h
0x1800c71cb  add     rsp, 0B0h
0x1800c71d2  pop     r15
0x1800c71d4  pop     r14
0x1800c71d6  pop     r13
0x1800c71d8  pop     r12
0x1800c71da  pop     rdi
0x1800c71db  pop     rsi
0x1800c71dc  pop     rbx
0x1800c71dd  retn
```
