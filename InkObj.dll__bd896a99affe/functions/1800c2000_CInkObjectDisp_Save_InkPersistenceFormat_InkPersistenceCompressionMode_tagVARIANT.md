# CInkObjectDisp::Save(InkPersistenceFormat,InkPersistenceCompressionMode,tagVARIANT *)

- ea: `0x1800c2000`
- end: `0x1800c22ee`
- name: `?Save@CInkObjectDisp@@UEAAJW4InkPersistenceFormat@@W4InkPersistenceCompressionMode@@PEAUtagVARIANT@@@Z`
- size: `750`
- prototype: `int(CInkObjectDisp *__hidden this, enum InkPersistenceFormat, enum InkPersistenceCompressionMode, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180009b64`
- `0x180034e08`
- `0x18003eb2c`
- `0x180044ac6`
- `0x18007cf68`
- `0x1800c2000`
- `0x1800c3800`
- `0x18010c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800c22c5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800c22c5`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800c217e`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800c2242`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800c217e`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800c2242`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800c21c8`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800c225f`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800c21c8`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800c225f`
- `OLEAUT32!__imp_VariantInit` at `0x1800c2089`
- `OLEAUT32!__imp_VariantInit` at `0x1800c2089`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800c227c`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800c227c`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800c2207`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800c2207`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800c2271`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800c2271`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x1800c2194`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x1800c2194`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800c21e8`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800c21e8`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800c20e7`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800c20e7`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800c2070`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800c2070`
- `api-ms-win-core-com-l1-1-0!GetHGlobalFromStream` at `0x1800c2160`
- `api-ms-win-core-com-l1-1-0!GetHGlobalFromStream` at `0x1800c222c`
- `api-ms-win-core-com-l1-1-0!GetHGlobalFromStream` at `0x1800c2160`
- `api-ms-win-core-com-l1-1-0!GetHGlobalFromStream` at `0x1800c222c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CInkObjectDisp::Save(
        CInkObjectDisp *this,
        enum InkPersistenceFormat a2,
        enum InkPersistenceCompressionMode a3,
        struct tagVARIANT *a4)
{
  HANDLE *v7; // r15
  unsigned int v8; // edi
  HRESULT HGlobalFromStream; // ebx
  char *v10; // rdi
  BSTR v11; // r14
  _BYTE *v12; // rdx
  ULONG i; // r8d
  char v14; // cl
  SAFEARRAY *Vector; // rax
  SAFEARRAY *v16; // rdi
  const void *v17; // rax
  ULONG cElements[2]; // [rsp+30h] [rbp-58h] BYREF
  HGLOBAL phglobal; // [rsp+38h] [rbp-50h] BYREF
  HGLOBAL hMem; // [rsp+40h] [rbp-48h] BYREF
  HANDLE *v22; // [rsp+48h] [rbp-40h]
  __int64 v23; // [rsp+50h] [rbp-38h] BYREF
  unsigned __int64 v24; // [rsp+58h] [rbp-30h]
  LPSTREAM dwindex; // [rsp+A8h] [rbp+20h] BYREF

  if ( !a4 )
    return 2147500035LL;
  v24 = ((unsigned __int64)this + 80) & -(__int64)(this != (CInkObjectDisp *)8);
  LODWORD(dwindex) = 0;
  v7 = (HANDLE *)(v24 + 8);
  v22 = (HANDLE *)(v24 + 8);
  CoWaitForMultipleHandles(0, 0xFFFFFFFF, 1u, (LPHANDLE)(v24 + 8), (LPDWORD)&dwindex);
  v23 = *((_QWORD *)this + 13);
  InkObj_Lock();
  VariantInit(a4);
  dwindex = 0;
  if ( (a2 == IPF_GIF || (v8 = 0, a2 == IPF_Base64GIF)) && (v8 = 1, a2 == IPF_Base64GIF)
    || a2 == IPF_Base64InkSerializedFormat )
  {
    v8 |= 0x10000u;
  }
  hMem = 0;
  if ( (int)InkObj_SetPersistentFormat(*((CWispInk **)this + 13), v8, 0) >= 0 )
    CreateStreamOnHGlobal(0, 1, &dwindex);
  try
  {
    HGlobalFromStream = CInkObjectDisp::_Save();
    if ( HGlobalFromStream >= 0 )
    {
      hMem = 0;
      *(_QWORD *)cElements = 0;
      HGlobalFromStream = (*(__int64 (__fastcall **)(LPSTREAM, _QWORD, __int64, ULONG *))(*(_QWORD *)dwindex + 40LL))(
                            dwindex,
                            0,
                            2,
                            cElements);
      if ( HGlobalFromStream >= 0 )
      {
        if ( (v8 & 0x10000) != 0 )
        {
          phglobal = 0;
          HGlobalFromStream = GetHGlobalFromStream(dwindex, &phglobal);
          if ( HGlobalFromStream >= 0 && phglobal )
          {
            v10 = (char *)GlobalLock(phglobal);
            v11 = SysAllocStringByteLen(0, 2 * cElements[0] + 2);
            v12 = v11;
            for ( i = cElements[0]; i; --i )
            {
              v14 = *v10++;
              *v12 = v14;
              v12[1] = 0;
              v12 += 2;
            }
            *(_WORD *)v12 = 0;
            GlobalUnlock(phglobal);
            a4->vt = 8;
            a4->llVal = (LONGLONG)v11;
          }
        }
        else
        {
          Vector = SafeArrayCreateVector(0x11u, 0, cElements[0]);
          v16 = Vector;
          if ( Vector )
          {
            phglobal = 0;
            HGlobalFromStream = SafeArrayAccessData(Vector, &phglobal);
            if ( HGlobalFromStream >= 0 && phglobal )
            {
              hMem = 0;
              HGlobalFromStream = GetHGlobalFromStream(dwindex, &hMem);
              if ( HGlobalFromStream >= 0 && hMem )
              {
                v17 = GlobalLock(hMem);
                memcpy_0(phglobal, v17, cElements[0]);
                GlobalUnlock(hMem);
                a4->vt = 8209;
                a4->llVal = (LONGLONG)v16;
              }
              SafeArrayUnaccessData(v16);
            }
            else
            {
              SafeArrayDestroy(v16);
            }
          }
          else
          {
            HGlobalFromStream = -2147024882;
          }
        }
      }
      InkObj_SetDirty(*((_QWORD *)this + 13), 0);
      (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)dwindex + 16LL))(dwindex);
    }
  }
  catch ( ... )
  {
    LODWORD(dwindex) = ReportWispException();
    HGlobalFromStream = (int)dwindex;
    v7 = v22;
  }
  CInkAutoInkLock::~CInkAutoInkLock((CInkAutoInkLock *)&v23);
  ReleaseMutex(*v7);
  return (unsigned int)HGlobalFromStream;
}

```

## disassembly

```asm
0x1800c2000  mov     [rsp+arg_0], rbx
0x1800c2005  mov     [rsp+arg_8], rsi
0x1800c200a  push    rdi
0x1800c200b  push    r12
0x1800c200d  push    r13
0x1800c200f  push    r14
0x1800c2011  push    r15
0x1800c2013  sub     rsp, 60h
0x1800c2017  mov     rsi, r9
0x1800c201a  mov     r14d, r8d
0x1800c201d  mov     ebx, edx
0x1800c201f  mov     r13, rcx
0x1800c2022  test    r9, r9
0x1800c2025  jz      loc_1800C22CF
0x1800c202b  lea     rax, [rcx-8]
0x1800c202f  lea     r10, [rcx+50h]
0x1800c2033  neg     rax
0x1800c2036  sbb     r11, r11
0x1800c2039  and     r11, r10
0x1800c203c  mov     [rsp+88h+var_30], r11
0x1800c2041  mov     dword ptr [rsp+88h+dwindex], 0
0x1800c204c  lea     r15, [r11+8]
0x1800c2050  mov     [rsp+88h+var_40], r15
0x1800c2055  lea     rax, [rsp+88h+dwindex]
0x1800c205d  mov     [rsp+88h+lpdwindex], rax; lpdwindex
0x1800c2062  mov     r9, r15; pHandles
0x1800c2065  mov     r8d, 1; cHandles
0x1800c206b  or      edx, 0FFFFFFFFh; dwTimeout
0x1800c206e  xor     ecx, ecx; dwFlags
0x1800c2070  call    cs:__imp_CoWaitForMultipleHandles
0x1800c2076  nop
0x1800c2077  mov     rcx, [r13+68h]
0x1800c207b  mov     [rsp+88h+var_38], rcx
0x1800c2080  call    InkObj_Lock
0x1800c2085  nop
0x1800c2086  mov     rcx, rsi; pvarg
0x1800c2089  call    cs:__imp_VariantInit
0x1800c208f  nop
0x1800c2090  mov     [rsp+88h+dwindex], 0
0x1800c209c  cmp     ebx, 2
0x1800c209f  jz      short loc_1800C20A8
0x1800c20a1  xor     edi, edi
0x1800c20a3  cmp     ebx, 3
0x1800c20a6  jnz     short loc_1800C20B2
0x1800c20a8  mov     edi, 1
0x1800c20ad  cmp     ebx, 3
0x1800c20b0  jz      short loc_1800C20B7
0x1800c20b2  cmp     ebx, 1
0x1800c20b5  jnz     short loc_1800C20BB
0x1800c20b7  bts     edi, 10h
0x1800c20bb  mov     [rsp+88h+hMem], 0
0x1800c20c4  mov     r8, [rsp+88h+hMem]; struct tagSIZE
0x1800c20c9  mov     edx, edi; unsigned int
0x1800c20cb  mov     rcx, [r13+68h]; this
0x1800c20cf  call    InkObj_SetPersistentFormat
0x1800c20d4  test    eax, eax
0x1800c20d6  js      short loc_1800C20ED
0x1800c20d8  lea     r8, [rsp+88h+dwindex]; ppstm
0x1800c20e0  mov     edx, 1; fDeleteOnRelease
0x1800c20e5  xor     ecx, ecx; hGlobal
0x1800c20e7  call    cs:__imp_CreateStreamOnHGlobal
0x1800c20ed  lea     r8d, [r14+1]
0x1800c20f1  mov     rdx, [rsp+88h+dwindex]
0x1800c20f9  lea     rcx, [r13-8]
0x1800c20fd  call    ?_Save@CInkObjectDisp@@AEAAJPEAUIStream@@W4enumINK_COMPRESSION_MODE@@@Z; CInkObjectDisp::_Save(IStream *,enumINK_COMPRESSION_MODE)
0x1800c2102  mov     ebx, eax
0x1800c2104  xor     r12d, r12d
0x1800c2107  test    eax, eax
0x1800c2109  js      loc_1800C22A9
0x1800c210f  mov     [rsp+88h+hMem], r12
0x1800c2114  mov     qword ptr [rsp+88h+cElements], r12
0x1800c2119  mov     rcx, [rsp+88h+dwindex]
0x1800c2121  mov     rax, [rcx]
0x1800c2124  lea     r9, [rsp+88h+cElements]
0x1800c2129  lea     r8d, [r12+2]
0x1800c212e  mov     edx, r12d
0x1800c2131  mov     rax, [rax+28h]
0x1800c2135  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c213a  mov     ebx, eax
0x1800c213c  test    eax, eax
0x1800c213e  js      loc_1800C2289
0x1800c2144  bt      edi, 10h
0x1800c2148  jnb     loc_1800C21DC
0x1800c214e  mov     [rsp+88h+phglobal], r12
0x1800c2153  lea     rdx, [rsp+88h+phglobal]; phglobal
0x1800c2158  mov     rcx, [rsp+88h+dwindex]; pstm
0x1800c2160  call    cs:__imp_GetHGlobalFromStream
0x1800c2166  mov     ebx, eax
0x1800c2168  test    eax, eax
0x1800c216a  js      loc_1800C2289
0x1800c2170  mov     rcx, [rsp+88h+phglobal]; hMem
0x1800c2175  test    rcx, rcx
0x1800c2178  jz      loc_1800C2289
0x1800c217e  call    cs:__imp_GlobalLock
0x1800c2184  mov     rdi, rax
0x1800c2187  mov     edx, [rsp+88h+cElements]
0x1800c218b  lea     edx, ds:2[rdx*2]; len
0x1800c2192  xor     ecx, ecx; psz
0x1800c2194  call    cs:__imp_SysAllocStringByteLen
0x1800c219a  mov     r14, rax
0x1800c219d  mov     rdx, rax
0x1800c21a0  mov     r8d, [rsp+88h+cElements]
0x1800c21a5  test    r8d, r8d
0x1800c21a8  jz      short loc_1800C21BF
0x1800c21aa  mov     cl, [rdi]
0x1800c21ac  inc     rdi
0x1800c21af  mov     [rdx], cl
0x1800c21b1  mov     [rdx+1], r12b
0x1800c21b5  add     rdx, 2
0x1800c21b9  sub     r8d, 1
0x1800c21bd  jnz     short loc_1800C21AA
0x1800c21bf  mov     [rdx], r12w
0x1800c21c3  mov     rcx, [rsp+88h+phglobal]; hMem
0x1800c21c8  call    cs:__imp_GlobalUnlock
0x1800c21ce  mov     word ptr [rsi], 8
0x1800c21d3  mov     [rsi+8], r14
0x1800c21d7  jmp     loc_1800C2289
0x1800c21dc  mov     ecx, 11h; vt
0x1800c21e1  mov     r8d, [rsp+88h+cElements]; cElements
0x1800c21e6  xor     edx, edx; lLbound
0x1800c21e8  call    cs:__imp_SafeArrayCreateVector
0x1800c21ee  mov     rdi, rax
0x1800c21f1  test    rax, rax
0x1800c21f4  jz      loc_1800C2284
0x1800c21fa  mov     [rsp+88h+phglobal], r12
0x1800c21ff  lea     rdx, [rsp+88h+phglobal]; ppvData
0x1800c2204  mov     rcx, rax; psa
0x1800c2207  call    cs:__imp_SafeArrayAccessData
0x1800c220d  mov     ebx, eax
0x1800c220f  test    eax, eax
0x1800c2211  js      short loc_1800C2279
0x1800c2213  cmp     [rsp+88h+phglobal], r12
0x1800c2218  jz      short loc_1800C2279
0x1800c221a  mov     [rsp+88h+hMem], r12
0x1800c221f  lea     rdx, [rsp+88h+hMem]; phglobal
0x1800c2224  mov     rcx, [rsp+88h+dwindex]; pstm
0x1800c222c  call    cs:__imp_GetHGlobalFromStream
0x1800c2232  mov     ebx, eax
0x1800c2234  test    eax, eax
0x1800c2236  js      short loc_1800C226E
0x1800c2238  mov     rcx, [rsp+88h+hMem]; hMem
0x1800c223d  test    rcx, rcx
0x1800c2240  jz      short loc_1800C226E
0x1800c2242  call    cs:__imp_GlobalLock
0x1800c2248  mov     r8d, [rsp+88h+cElements]; Size
0x1800c224d  mov     rdx, rax; Src
0x1800c2250  mov     rcx, [rsp+88h+phglobal]; void *
0x1800c2255  call    memcpy_0
0x1800c225a  mov     rcx, [rsp+88h+hMem]; hMem
0x1800c225f  call    cs:__imp_GlobalUnlock
0x1800c2265  mov     word ptr [rsi], 2011h
0x1800c226a  mov     [rsi+8], rdi
0x1800c226e  mov     rcx, rdi; psa
0x1800c2271  call    cs:__imp_SafeArrayUnaccessData
0x1800c2277  jmp     short loc_1800C2289
0x1800c2279  mov     rcx, rdi; psa
0x1800c227c  call    cs:__imp_SafeArrayDestroy
0x1800c2282  jmp     short loc_1800C2289
0x1800c2284  mov     ebx, 8007000Eh
0x1800c2289  xor     edx, edx
0x1800c228b  mov     rcx, [r13+68h]
0x1800c228f  call    InkObj_SetDirty
0x1800c2294  mov     rcx, [rsp+88h+dwindex]
0x1800c229c  mov     rax, [rcx]
0x1800c229f  mov     rax, [rax+10h]
0x1800c22a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c22a8  nop
0x1800c22a9  jmp     short loc_1800C22B7
0x1800c22ab  mov     ebx, dword ptr [rsp+88h+dwindex]
0x1800c22b2  mov     r15, [rsp+88h+var_40]
0x1800c22b7  lea     rcx, [rsp+88h+var_38]; this
0x1800c22bc  call    ??1CInkAutoInkLock@@QEAA@XZ; CInkAutoInkLock::~CInkAutoInkLock(void)
0x1800c22c1  nop
0x1800c22c2  mov     rcx, [r15]; hMutex
0x1800c22c5  call    cs:__imp_ReleaseMutex
0x1800c22cb  mov     eax, ebx
0x1800c22cd  jmp     short loc_1800C22D4
0x1800c22cf  mov     eax, 80004003h
0x1800c22d4  lea     r11, [rsp+88h+var_28]
0x1800c22d9  mov     rbx, [r11+30h]
0x1800c22dd  mov     rsi, [r11+38h]
0x1800c22e1  mov     rsp, r11
0x1800c22e4  pop     r15
0x1800c22e6  pop     r14
0x1800c22e8  pop     r13
0x1800c22ea  pop     r12
0x1800c22ec  pop     rdi
0x1800c22ed  retn
```
