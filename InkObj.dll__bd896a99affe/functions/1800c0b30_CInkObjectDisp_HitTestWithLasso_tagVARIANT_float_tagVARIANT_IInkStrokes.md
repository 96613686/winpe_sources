# CInkObjectDisp::HitTestWithLasso(tagVARIANT,float,tagVARIANT *,IInkStrokes * *)

- ea: `0x1800c0b30`
- end: `0x1800c0eb4`
- name: `?HitTestWithLasso@CInkObjectDisp@@UEAAJUtagVARIANT@@MPEAU2@PEAPEAUIInkStrokes@@@Z`
- size: `900`
- prototype: `int(CInkObjectDisp *__hidden this, struct tagVARIANT *__struct_ptr, float, struct tagVARIANT *, struct IInkStrokes **)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x180009b64`
- `0x18000a730`
- `0x180034e08`
- `0x180039098`
- `0x180039398`
- `0x1800410b0`
- `0x18007cccc`
- `0x1800c0b30`
- `0x1800c2c1c`
- `0x18010c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800c0c1c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800c0e5e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800c0e76`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800c0e91`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800c0c1c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800c0e5e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800c0e76`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800c0e91`
- `OLEAUT32!__imp_VariantClear` at `0x1800c0c02`
- `OLEAUT32!__imp_VariantClear` at `0x1800c0c02`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800c0e29`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800c0e29`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800c0cc4`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800c0cc4`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800c0dd8`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800c0dd8`
- `OLEAUT32!__imp_SafeArrayRedim` at `0x1800c0e0c`
- `OLEAUT32!__imp_SafeArrayRedim` at `0x1800c0e0c`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800c0caa`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800c0caa`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800c0b97`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800c0b97`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CInkObjectDisp::HitTestWithLasso(
        CInkObjectDisp *this,
        struct tagVARIANT *a2,
        float a3,
        struct tagVARIANT *a4,
        struct IInkStrokes **a5)
{
  _QWORD *v7; // r12
  SAFEARRAY *v8; // rsi
  HANDLE *v9; // rdi
  struct IInkStrokes **v10; // r13
  HRESULT v11; // ebx
  int cElements; // ebx
  unsigned int v14; // r15d
  void *v15; // rcx
  SAFEARRAY *Vector; // rax
  __int64 v17; // rax
  int v18; // eax
  SAFEARRAYBOUND v19; // rax
  SAFEARRAYBOUND v20; // r15
  HRESULT v21; // eax
  struct CStrokeSetImpl *v22; // [rsp+40h] [rbp-78h] BYREF
  __int64 v23; // [rsp+48h] [rbp-70h] BYREF
  unsigned __int8 *v24; // [rsp+50h] [rbp-68h] BYREF
  void *ppvData; // [rsp+58h] [rbp-60h] BYREF
  HANDLE *v26; // [rsp+60h] [rbp-58h]
  unsigned __int64 v27; // [rsp+68h] [rbp-50h]
  SAFEARRAYBOUND psaboundNew; // [rsp+C0h] [rbp+8h] BYREF
  struct tagVARIANT *v29; // [rsp+C8h] [rbp+10h]
  unsigned int lpdwindex; // [rsp+D8h] [rbp+20h] BYREF

  v29 = a2;
  psaboundNew = (SAFEARRAYBOUND)this;
  v7 = (_QWORD *)((char *)this - 8);
  v27 = ((unsigned __int64)this + 80) & -(__int64)(this != (CInkObjectDisp *)8);
  v8 = 0;
  lpdwindex = 0;
  v9 = (HANDLE *)(v27 + 8);
  v26 = (HANDLE *)(v27 + 8);
  CoWaitForMultipleHandles(0, 0xFFFFFFFF, 1u, (LPHANDLE)(v27 + 8), &lpdwindex);
  v23 = v7[14];
  InkObj_Lock();
  v10 = a5;
  if ( a5 )
  {
    if ( a3 <= 100.0 && a3 >= 0.0 && (((a2->vt & 0xBFFF) - 8195) & 0xFFEF) == 0 )
    {
      if ( a4 )
      {
        v11 = VariantClear(a4);
        if ( v11 < 0 )
        {
          CInkAutoInkLock::~CInkAutoInkLock((CInkAutoInkLock *)&v23);
          ReleaseMutex(*v9);
          return (unsigned int)v11;
        }
      }
      lpdwindex = 0;
      LODWORD(v22) = 0;
      v24 = 0;
      cElements = AccessVariantData(a2, &v24, &lpdwindex, (unsigned int *)&v22, 0, 0);
      if ( cElements < 0 )
        goto LABEL_42;
      try
      {
        if ( ((lpdwindex / (unsigned int)v22) & 1) != 0 )
        {
          cElements = -2147024809;
          goto LABEL_35;
        }
        v14 = (lpdwindex / (unsigned int)v22) >> 1;
        lpdwindex = v14 + 1;
        v15 = 0;
        ppvData = 0;
        if ( a4 )
        {
          Vector = SafeArrayCreateVector(3u, 0, 2 * (v14 + 1));
          v8 = Vector;
          if ( !Vector )
          {
            cElements = -2147024882;
            goto LABEL_35;
          }
          cElements = SafeArrayAccessData(Vector, &ppvData);
          if ( cElements < 0 )
          {
LABEL_35:
            UnaccessVariantData(v29, v24);
            goto LABEL_42;
          }
          v15 = ppvData;
        }
        v22 = 0;
        v17 = 0;
        if ( a4 )
          v17 = (__int64)v15;
        v18 = InkObj_SelectWithLasso(
                *(_QWORD *)(*(_QWORD *)&psaboundNew + 104LL),
                v14,
                (_DWORD)v24,
                (int)a3,
                0,
                v17,
                (__int64)&lpdwindex,
                (__int64)&v22);
        cElements = v18;
        psaboundNew = 0;
        if ( v18 )
        {
          if ( v18 == 1 )
          {
            cElements = ATL::CComObject<CInkStrokes>::CreateInstance(&psaboundNew);
            if ( cElements >= 0 )
            {
              (*(void (__fastcall **)(_QWORD *))(*v7 + 8LL))(v7);
              v20 = psaboundNew;
              *(_QWORD *)(*(_QWORD *)&psaboundNew + 96LL) = v7;
              (*(void (__fastcall **)(SAFEARRAYBOUND))(**(_QWORD **)&v20 + 8LL))(v20);
              *v10 = (struct IInkStrokes *)(*(_QWORD *)&v20 + 8LL);
            }
          }
        }
        else
        {
          cElements = CInkObjectDisp::_CreateStrokesFromStrokeset(v7, v22, &psaboundNew);
          if ( cElements >= 0 )
          {
            v19 = psaboundNew;
            if ( psaboundNew )
              v19 = (SAFEARRAYBOUND)(*(_QWORD *)&psaboundNew + 8LL);
            *v10 = (struct IInkStrokes *)v19;
          }
          DeleteStrokeSet(v22);
        }
        if ( !a4 )
          goto LABEL_35;
        v21 = SafeArrayUnaccessData(v8);
        if ( cElements >= 0 )
        {
          if ( v21 < 0 )
          {
            cElements = v21;
          }
          else
          {
            psaboundNew.cElements = 2 * lpdwindex;
            psaboundNew.lLbound = 0;
            cElements = SafeArrayRedim(v8, &psaboundNew);
            if ( cElements >= 0 )
            {
              a4->vt = 8195;
              a4->llVal = (LONGLONG)v8;
              goto LABEL_35;
            }
          }
        }
        SafeArrayDestroy(v8);
        goto LABEL_35;
      }
      catch ( ... )
      {
        psaboundNew.cElements = ReportWispException();
        cElements = psaboundNew.cElements;
        v9 = v26;
      }
LABEL_42:
      CInkAutoInkLock::~CInkAutoInkLock((CInkAutoInkLock *)&v23);
      ReleaseMutex(*v9);
      return (unsigned int)cElements;
    }
    CInkAutoInkLock::~CInkAutoInkLock((CInkAutoInkLock *)&v23);
    ReleaseMutex(*v9);
    return 2147942487LL;
  }
  else
  {
    CInkAutoInkLock::~CInkAutoInkLock((CInkAutoInkLock *)&v23);
    ReleaseMutex(*v9);
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x1800c0b30  mov     r11, rsp
0x1800c0b33  mov     [r11+10h], rdx
0x1800c0b37  mov     [r11+8], rcx
0x1800c0b3b  push    rbx
0x1800c0b3c  push    rsi
0x1800c0b3d  push    rdi
0x1800c0b3e  push    r12
0x1800c0b40  push    r13
0x1800c0b42  push    r14
0x1800c0b44  push    r15
0x1800c0b46  sub     rsp, 80h
0x1800c0b4d  movaps  [rsp+0B8h+var_48], xmm6
0x1800c0b52  mov     r14, r9
0x1800c0b55  movaps  xmm6, xmm2
0x1800c0b58  mov     r15, rdx
0x1800c0b5b  lea     r12, [rcx-8]
0x1800c0b5f  mov     rax, r12
0x1800c0b62  lea     r8, [rcx+50h]
0x1800c0b66  neg     rax
0x1800c0b69  sbb     r10, r10
0x1800c0b6c  and     r10, r8
0x1800c0b6f  mov     [r11-50h], r10
0x1800c0b73  xor     esi, esi
0x1800c0b75  mov     [r11+20h], esi
0x1800c0b79  lea     rdi, [r10+8]
0x1800c0b7d  mov     [rsp+0B8h+var_58], rdi
0x1800c0b82  lea     rax, [r11+20h]
0x1800c0b86  mov     [rsp+0B8h+lpdwindex], rax; lpdwindex
0x1800c0b8b  mov     r9, rdi; pHandles
0x1800c0b8e  lea     r8d, [rsi+1]; cHandles
0x1800c0b92  or      edx, 0FFFFFFFFh; dwTimeout
0x1800c0b95  xor     ecx, ecx; dwFlags
0x1800c0b97  call    cs:__imp_CoWaitForMultipleHandles
0x1800c0b9d  nop
0x1800c0b9e  mov     rcx, [r12+70h]
0x1800c0ba3  mov     [rsp+0B8h+var_70], rcx
0x1800c0ba8  call    InkObj_Lock
0x1800c0bad  nop
0x1800c0bae  mov     r13, [rsp+0B8h+arg_20]
0x1800c0bb6  test    r13, r13
0x1800c0bb9  jz      loc_1800C0E83
0x1800c0bbf  comiss  xmm6, cs:__real@42c80000
0x1800c0bc6  ja      loc_1800C0E68
0x1800c0bcc  xorps   xmm0, xmm0
0x1800c0bcf  comiss  xmm0, xmm6
0x1800c0bd2  ja      loc_1800C0E68
0x1800c0bd8  movzx   eax, word ptr [r15]
0x1800c0bdc  mov     ecx, 0BFFFh
0x1800c0be1  and     ax, cx
0x1800c0be4  mov     ecx, 2003h
0x1800c0be9  sub     ax, cx
0x1800c0bec  mov     ecx, 0FFEFh
0x1800c0bf1  test    cx, ax
0x1800c0bf4  jnz     loc_1800C0E68
0x1800c0bfa  test    r14, r14
0x1800c0bfd  jz      short loc_1800C0C29
0x1800c0bff  mov     rcx, r14; pvarg
0x1800c0c02  call    cs:__imp_VariantClear
0x1800c0c08  mov     ebx, eax
0x1800c0c0a  test    eax, eax
0x1800c0c0c  jns     short loc_1800C0C29
0x1800c0c0e  lea     rcx, [rsp+0B8h+var_70]; this
0x1800c0c13  call    ??1CInkAutoInkLock@@QEAA@XZ; CInkAutoInkLock::~CInkAutoInkLock(void)
0x1800c0c18  nop
0x1800c0c19  mov     rcx, [rdi]; hMutex
0x1800c0c1c  call    cs:__imp_ReleaseMutex
0x1800c0c22  mov     eax, ebx
0x1800c0c24  jmp     loc_1800C0E9C
0x1800c0c29  mov     [rsp+0B8h+arg_18], esi
0x1800c0c30  mov     dword ptr [rsp+0B8h+var_78], esi
0x1800c0c34  mov     [rsp+0B8h+var_68], rsi
0x1800c0c39  mov     [rsp+0B8h+var_90], rsi; unsigned __int16 *
0x1800c0c3e  mov     [rsp+0B8h+lpdwindex], rsi; bool *
0x1800c0c43  lea     r9, [rsp+0B8h+var_78]; unsigned int *
0x1800c0c48  lea     r8, [rsp+0B8h+arg_18]; unsigned int *
0x1800c0c50  lea     rdx, [rsp+0B8h+var_68]; unsigned __int8 **
0x1800c0c55  mov     rcx, r15; struct tagVARIANT *
0x1800c0c58  call    ?AccessVariantData@@YAJPEBUtagVARIANT@@PEAPEAEPEAK2PEA_NPEAG@Z; AccessVariantData(tagVARIANT const *,uchar * *,ulong *,ulong *,bool *,ushort *)
0x1800c0c5d  mov     ebx, eax
0x1800c0c5f  test    eax, eax
0x1800c0c61  js      loc_1800C0E42
0x1800c0c67  xor     edx, edx
0x1800c0c69  mov     eax, [rsp+0B8h+arg_18]
0x1800c0c70  div     dword ptr [rsp+0B8h+var_78]
0x1800c0c74  mov     r15d, eax
0x1800c0c77  test    al, 1
0x1800c0c79  jz      short loc_1800C0C85
0x1800c0c7b  mov     ebx, 80070057h
0x1800c0c80  jmp     loc_1800C0E2F
0x1800c0c85  shr     r15d, 1
0x1800c0c88  lea     r8d, [r15+1]
0x1800c0c8c  mov     [rsp+0B8h+arg_18], r8d
0x1800c0c94  xor     ecx, ecx
0x1800c0c96  mov     [rsp+0B8h+ppvData], rcx
0x1800c0c9b  test    r14, r14
0x1800c0c9e  jz      short loc_1800C0CD9
0x1800c0ca0  add     r8d, r8d; cElements
0x1800c0ca3  mov     ecx, 3; vt
0x1800c0ca8  xor     edx, edx; lLbound
0x1800c0caa  call    cs:__imp_SafeArrayCreateVector
0x1800c0cb0  mov     rsi, rax
0x1800c0cb3  test    rax, rax
0x1800c0cb6  jz      loc_1800C0D7B
0x1800c0cbc  lea     rdx, [rsp+0B8h+ppvData]; ppvData
0x1800c0cc1  mov     rcx, rax; psa
0x1800c0cc4  call    cs:__imp_SafeArrayAccessData
0x1800c0cca  mov     ebx, eax
0x1800c0ccc  test    eax, eax
0x1800c0cce  js      loc_1800C0E2F
0x1800c0cd4  mov     rcx, [rsp+0B8h+ppvData]
0x1800c0cd9  mov     [rsp+0B8h+var_78], 0
0x1800c0ce2  xor     eax, eax
0x1800c0ce4  test    r14, r14
0x1800c0ce7  cmovnz  rax, rcx
0x1800c0ceb  cvttss2si r9, xmm6
0x1800c0cf0  lea     rcx, [rsp+0B8h+var_78]
0x1800c0cf5  mov     [rsp+0B8h+var_80], rcx
0x1800c0cfa  lea     rcx, [rsp+0B8h+arg_18]
0x1800c0d02  mov     [rsp+0B8h+var_88], rcx
0x1800c0d07  mov     [rsp+0B8h+var_90], rax
0x1800c0d0c  mov     dword ptr [rsp+0B8h+lpdwindex], 0
0x1800c0d14  mov     r8, [rsp+0B8h+var_68]
0x1800c0d19  mov     edx, r15d
0x1800c0d1c  mov     rcx, qword ptr [rsp+0B8h+psaboundNew.cElements]
0x1800c0d24  mov     rcx, [rcx+68h]
0x1800c0d28  call    InkObj_SelectWithLasso
0x1800c0d2d  mov     ebx, eax
0x1800c0d2f  mov     qword ptr [rsp+0B8h+psaboundNew.cElements], 0
0x1800c0d3b  test    eax, eax
0x1800c0d3d  jnz     short loc_1800C0D85
0x1800c0d3f  lea     r8, [rsp+0B8h+psaboundNew]
0x1800c0d47  mov     rdx, [rsp+0B8h+var_78]
0x1800c0d4c  mov     rcx, r12
0x1800c0d4f  call    ?_CreateStrokesFromStrokeset@CInkObjectDisp@@QEAAJPEAXPEAPEAV?$CComObject@VCInkStrokes@@@ATL@@@Z; CInkObjectDisp::_CreateStrokesFromStrokeset(void *,ATL::CComObject<CInkStrokes> * *)
0x1800c0d54  mov     ebx, eax
0x1800c0d56  test    eax, eax
0x1800c0d58  js      short loc_1800C0D6F
0x1800c0d5a  mov     rax, qword ptr [rsp+0B8h+psaboundNew.cElements]
0x1800c0d62  test    rax, rax
0x1800c0d65  jz      short loc_1800C0D6B
0x1800c0d67  add     rax, 8
0x1800c0d6b  mov     [r13+0], rax
0x1800c0d6f  mov     rcx, [rsp+0B8h+var_78]; this
0x1800c0d74  call    DeleteStrokeSet
0x1800c0d79  jmp     short loc_1800C0DD0
0x1800c0d7b  mov     ebx, 8007000Eh
0x1800c0d80  jmp     loc_1800C0E2F
0x1800c0d85  cmp     eax, 1
0x1800c0d88  jnz     short loc_1800C0DD0
0x1800c0d8a  lea     rcx, [rsp+0B8h+psaboundNew]
0x1800c0d92  call    ?CreateInstance@?$CComObject@VCInkStrokes@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CInkStrokes>::CreateInstance(ATL::CComObject<CInkStrokes> * *)
0x1800c0d97  mov     ebx, eax
0x1800c0d99  test    eax, eax
0x1800c0d9b  js      short loc_1800C0DD0
0x1800c0d9d  mov     rax, [r12]
0x1800c0da1  mov     rcx, r12
0x1800c0da4  mov     rax, [rax+8]
0x1800c0da8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c0dad  mov     r15, qword ptr [rsp+0B8h+psaboundNew.cElements]
0x1800c0db5  mov     [r15+60h], r12
0x1800c0db9  mov     rax, [r15]
0x1800c0dbc  mov     rcx, r15
0x1800c0dbf  mov     rax, [rax+8]
0x1800c0dc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c0dc8  lea     rax, [r15+8]
0x1800c0dcc  mov     [r13+0], rax
0x1800c0dd0  test    r14, r14
0x1800c0dd3  jz      short loc_1800C0E2F
0x1800c0dd5  mov     rcx, rsi; psa
0x1800c0dd8  call    cs:__imp_SafeArrayUnaccessData
0x1800c0dde  test    ebx, ebx
0x1800c0de0  js      short loc_1800C0E26
0x1800c0de2  test    eax, eax
0x1800c0de4  js      short loc_1800C0E24
0x1800c0de6  mov     eax, [rsp+0B8h+arg_18]
0x1800c0ded  add     eax, eax
0x1800c0def  mov     [rsp+0B8h+psaboundNew.cElements], eax
0x1800c0df6  mov     [rsp+0B8h+psaboundNew.lLbound], 0
0x1800c0e01  lea     rdx, [rsp+0B8h+psaboundNew]; psaboundNew
0x1800c0e09  mov     rcx, rsi; psa
0x1800c0e0c  call    cs:__imp_SafeArrayRedim
0x1800c0e12  mov     ebx, eax
0x1800c0e14  test    eax, eax
0x1800c0e16  js      short loc_1800C0E26
0x1800c0e18  mov     word ptr [r14], 2003h
0x1800c0e1e  mov     [r14+8], rsi
0x1800c0e22  jmp     short loc_1800C0E2F
0x1800c0e24  mov     ebx, eax
0x1800c0e26  mov     rcx, rsi; psa
0x1800c0e29  call    cs:__imp_SafeArrayDestroy
0x1800c0e2f  mov     rdx, [rsp+0B8h+var_68]; unsigned __int8 *
0x1800c0e34  mov     rcx, [rsp+0B8h+arg_8]; struct tagVARIANT *
0x1800c0e3c  call    ?UnaccessVariantData@@YAXPEBUtagVARIANT@@PEAE@Z; UnaccessVariantData(tagVARIANT const *,uchar *)
0x1800c0e41  nop
0x1800c0e42  jmp     short loc_1800C0E50
0x1800c0e44  mov     ebx, [rsp+0B8h+psaboundNew.cElements]
0x1800c0e4b  mov     rdi, [rsp+0B8h+var_58]
0x1800c0e50  lea     rcx, [rsp+0B8h+var_70]; this
0x1800c0e55  call    ??1CInkAutoInkLock@@QEAA@XZ; CInkAutoInkLock::~CInkAutoInkLock(void)
0x1800c0e5a  nop
0x1800c0e5b  mov     rcx, [rdi]; hMutex
0x1800c0e5e  call    cs:__imp_ReleaseMutex
0x1800c0e64  mov     eax, ebx
0x1800c0e66  jmp     short loc_1800C0E9C
0x1800c0e68  lea     rcx, [rsp+0B8h+var_70]; this
0x1800c0e6d  call    ??1CInkAutoInkLock@@QEAA@XZ; CInkAutoInkLock::~CInkAutoInkLock(void)
0x1800c0e72  nop
0x1800c0e73  mov     rcx, [rdi]; hMutex
0x1800c0e76  call    cs:__imp_ReleaseMutex
0x1800c0e7c  mov     eax, 80070057h
0x1800c0e81  jmp     short loc_1800C0E9C
0x1800c0e83  lea     rcx, [rsp+0B8h+var_70]; this
0x1800c0e88  call    ??1CInkAutoInkLock@@QEAA@XZ; CInkAutoInkLock::~CInkAutoInkLock(void)
0x1800c0e8d  nop
0x1800c0e8e  mov     rcx, [rdi]; hMutex
0x1800c0e91  call    cs:__imp_ReleaseMutex
0x1800c0e97  mov     eax, 80004003h
0x1800c0e9c  movaps  xmm6, [rsp+0B8h+var_48]
0x1800c0ea1  add     rsp, 80h
0x1800c0ea8  pop     r15
0x1800c0eaa  pop     r14
0x1800c0eac  pop     r13
0x1800c0eae  pop     r12
0x1800c0eb0  pop     rdi
0x1800c0eb1  pop     rsi
0x1800c0eb2  pop     rbx
0x1800c0eb3  retn
```
