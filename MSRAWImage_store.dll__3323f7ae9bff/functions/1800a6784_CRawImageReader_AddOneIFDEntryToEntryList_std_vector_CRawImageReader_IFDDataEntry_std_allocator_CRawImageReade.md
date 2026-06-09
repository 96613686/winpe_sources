# CRawImageReader::AddOneIFDEntryToEntryList(std::vector<CRawImageReader::IFDDataEntry,std::allocator<CRawImageReader::IFDDataEntry>> *,uint *,ushort,ushort,uint,uint,uint,uchar const *)

- ea: `0x1800a6784`
- end: `0x1800a6a38`
- name: `?AddOneIFDEntryToEntryList@CRawImageReader@@AEAAJPEAV?$vector@UIFDDataEntry@CRawImageReader@@V?$allocator@UIFDDataEntry@CRawImageReader@@@std@@@std@@PEAIGGIIIPEBE@Z`
- size: `692`
- prototype: `__int64 __usercall@<rax>(CRawImageReader *this@<rcx>, __int16, unsigned int, unsigned int, size_t, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `14`
- tags: ``

## callers

- `0x1800a58b4`
- `0x1800a5b90`
- `0x1800a6a40`

## callees

- `0x180002040`
- `0x1800020a0`
- `0x1800023a0`
- `0x180002590`
- `0x180002a00`
- `0x18009b9e4`
- `0x18009e8b8`
- `0x1800a34f8`
- `0x1800a427c`
- `0x1800a5160`
- `0x1800a6784`
- `0x1800a713c`
- `0x1800af278`
- `0x1800b4010`

## string_xrefs

- `0x1800a67d2`: `CRawImageReader::AddOneIFDEntryToEntryList`
- `0x1800a685e`: `CRawImageReader::AddOneIFDEntryToEntryList`
- `0x1800a6938`: `CRawImageReader::AddOneIFDEntryToEntryList`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CRawImageReader::AddOneIFDEntryToEntryList(
        CRawImageReader *this,
        __int64 a2,
        _DWORD *a3,
        __int16 a4,
        unsigned __int16 a5,
        unsigned int a6,
        unsigned int a7,
        size_t a8,
        unsigned __int8 *Src)
{
  int *v13; // r9
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v15; // ebx
  unsigned int *v16; // rdi
  int OneIFDEntry; // ebx
  CallStackTracing *v18; // rcx
  struct CallStackContext *v19; // rax
  int v20; // r8d
  CallStackTracing *v21; // rcx
  int v23; // [rsp+28h] [rbp-A9h]
  size_t Size; // [rsp+38h] [rbp-99h]
  _QWORD v25[2]; // [rsp+48h] [rbp-89h] BYREF
  _BYTE v26[8]; // [rsp+58h] [rbp-79h] BYREF
  int v27; // [rsp+60h] [rbp-71h]
  __int128 v28; // [rsp+68h] [rbp-69h] BYREF
  __int64 v29; // [rsp+78h] [rbp-59h]
  _BYTE v30[32]; // [rsp+80h] [rbp-51h] BYREF
  __int64 v31; // [rsp+A0h] [rbp-31h] BYREF
  _BYTE v32[16]; // [rsp+A8h] [rbp-29h] BYREF
  _BYTE v33[24]; // [rsp+B8h] [rbp-19h] BYREF

  v25[1] = -2;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v25,
    "CRawImageReader::AddOneIFDEntryToEntryList",
    1974);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 34) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v15 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 34) + 296LL))(*((_QWORD *)this + 34));
    *((_OWORD *)ThreadRelativeContext + 125) = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 34) + 280LL))(
                                                            *((_QWORD *)this + 34),
                                                            v30);
    *((_DWORD *)ThreadRelativeContext + 504) = v15;
  }
  v16 = (unsigned int *)((char *)this + 56);
  CTraceBase::CAutoTrace::CAutoTrace(
    (CTraceBase::CAutoTrace *)v30,
    (struct CTraceBase *)(((unsigned __int64)this + 56) & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64)),
    "CRawImageReader::AddOneIFDEntryToEntryList",
    v13,
    v23);
  v27 = 0;
  v28 = 0;
  v29 = 0;
  LODWORD(Size) = a8;
  OneIFDEntry = CRawImageReader::CreateOneIFDEntry(
                  this,
                  a4,
                  a5,
                  a6,
                  a7,
                  (struct CRawImageReader::IFDDataEntry *)v26,
                  Size,
                  Src);
  if ( OneIFDEntry >= 0 )
  {
    v31 = a2;
    CRawImageReader::IFDDataEntry::IFDDataEntry(
      (CRawImageReader::IFDDataEntry *)v32,
      (const struct CRawImageReader::IFDDataEntry *)v26);
    OneIFDEntry = MF::ExceptionBoundary__lambda_d01e290712e0a6d52430fc96ee8f154f___(&v31);
    std::vector<unsigned char>::_Tidy(v33);
    if ( OneIFDEntry >= 0 )
    {
      *a3 += a8 + 12;
      goto LABEL_26;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        165,
        &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
        *v16,
        OneIFDEntry);
    }
    v21 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v21 = (CallStackTracing *)&off_1800E5190;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
    }
    if ( *((_BYTE *)v21 + 8) )
    {
      v19 = CallStackTracing::GetThreadRelativeContext(v21);
      if ( *((_DWORD *)v19 + 499) != OneIFDEntry )
      {
        v20 = 1980;
        goto LABEL_14;
      }
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        164,
        &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
        *v16,
        OneIFDEntry);
    }
    v18 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v18 = (CallStackTracing *)&off_1800E5190;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
    }
    if ( *((_BYTE *)v18 + 8) )
    {
      v19 = CallStackTracing::GetThreadRelativeContext(v18);
      if ( *((_DWORD *)v19 + 499) != OneIFDEntry )
      {
        v20 = 1976;
LABEL_14:
        CallStackContext::TraceFailure(v19, "CRawImageReader::AddOneIFDEntryToEntryList", v20, OneIFDEntry);
      }
    }
  }
LABEL_26:
  std::vector<unsigned char>::_Tidy(&v28);
  CTraceBase::CAutoTrace::~CAutoTrace((CTraceBase::CAutoTrace *)v30);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v25);
  return (unsigned int)OneIFDEntry;
}

```

## disassembly

```asm
0x1800a6784  mov     rax, rsp
0x1800a6787  push    rbp
0x1800a6788  push    rsi
0x1800a6789  push    rdi
0x1800a678a  push    r12
0x1800a678c  push    r13
0x1800a678e  push    r14
0x1800a6790  push    r15
0x1800a6792  lea     rbp, [rax-3Fh]
0x1800a6796  sub     rsp, 0D0h
0x1800a679d  mov     qword ptr [rsp+48h], 0FFFFFFFFFFFFFFFEh
0x1800a67a6  mov     [rax+10h], rbx
0x1800a67aa  mov     rax, cs:__security_cookie
0x1800a67b1  xor     rax, rsp
0x1800a67b4  mov     [rbp+37h+var_38], rax
0x1800a67b8  movzx   r13d, r9w
0x1800a67bc  mov     r14, r8
0x1800a67bf  mov     r12, rdx
0x1800a67c2  mov     rsi, rcx
0x1800a67c5  mov     r15, [rbp+37h+arg_40]
0x1800a67cc  mov     r8d, 7B6h; int
0x1800a67d2  lea     rdx, aCrawimagereade_17; "CRawImageReader::AddOneIFDEntryToEntryL"...
0x1800a67d9  lea     rcx, [rsp+100h+var_C0]; this
0x1800a67de  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800a67e3  nop
0x1800a67e4  xor     ebx, ebx
0x1800a67e6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800a67ed  cmp     [rcx+8], bl
0x1800a67f0  jz      short loc_1800A684E
0x1800a67f2  cmp     [rsi+110h], rbx
0x1800a67f9  jz      short loc_1800A684E
0x1800a67fb  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a6800  mov     rdi, rax
0x1800a6803  mov     rdx, [rsi+110h]
0x1800a680a  mov     rcx, [rdx]
0x1800a680d  mov     rax, [rcx+128h]
0x1800a6814  mov     rcx, rdx
0x1800a6817  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a681c  mov     ebx, eax
0x1800a681e  mov     r8, [rsi+110h]
0x1800a6825  mov     rcx, [r8]
0x1800a6828  mov     rax, [rcx+118h]
0x1800a682f  lea     rdx, [rbp+37h+var_88]
0x1800a6833  mov     rcx, r8
0x1800a6836  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a683b  movups  xmm0, xmmword ptr [rax]
0x1800a683e  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x1800a6846  mov     [rdi+7E0h], ebx
0x1800a684c  xor     ebx, ebx
0x1800a684e  lea     rdi, [rsi+38h]
0x1800a6852  mov     rax, rsi
0x1800a6855  neg     rax
0x1800a6858  sbb     rdx, rdx
0x1800a685b  and     rdx, rdi; struct CTraceBase *
0x1800a685e  lea     r8, aCrawimagereade_17; "CRawImageReader::AddOneIFDEntryToEntryL"...
0x1800a6865  lea     rcx, [rbp+37h+var_88]; this
0x1800a6869  call    ??0CAutoTrace@CTraceBase@@QEAA@PEAV1@PEBDPEAJH@Z; CTraceBase::CAutoTrace::CAutoTrace(CTraceBase *,char const *,long *,int)
0x1800a686e  nop
0x1800a686f  mov     [rbp+37h+var_A8], 0
0x1800a6876  xorps   xmm0, xmm0
0x1800a6879  movdqu  [rbp+37h+var_A0], xmm0
0x1800a687e  mov     [rbp+37h+var_90], rbx
0x1800a6882  mov     [rsp+100h+Src], r15; Src
0x1800a6887  mov     r15d, dword ptr [rbp+37h+arg_38]
0x1800a688b  mov     dword ptr [rsp+100h+Size], r15d; Size
0x1800a6890  lea     rax, [rbp+37h+var_B0]
0x1800a6894  mov     [rsp+100h+var_D8], rax; struct CRawImageReader::IFDDataEntry *
0x1800a6899  mov     eax, [rbp+37h+arg_30]
0x1800a689c  mov     [rsp+100h+var_E0], eax; unsigned int
0x1800a68a0  mov     r9d, [rbp+37h+arg_28]; unsigned int
0x1800a68a4  movzx   r8d, [rbp+37h+arg_20]; unsigned __int16
0x1800a68a9  movzx   edx, r13w; unsigned __int16
0x1800a68ad  mov     rcx, rsi; this
0x1800a68b0  call    ?CreateOneIFDEntry@CRawImageReader@@AEAAJGGIIAEAUIFDDataEntry@1@IPEBE@Z; CRawImageReader::CreateOneIFDEntry(ushort,ushort,uint,uint,CRawImageReader::IFDDataEntry &,uint,uchar const *)
0x1800a68b5  mov     ebx, eax
0x1800a68b7  test    eax, eax
0x1800a68b9  jns     loc_1800A694C
0x1800a68bf  lea     rax, WPP_GLOBAL_Control
0x1800a68c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a68cd  cmp     rcx, rax
0x1800a68d0  jz      short loc_1800A68FA
0x1800a68d2  test    byte ptr [rcx+1Ch], 1
0x1800a68d6  jz      short loc_1800A68FA
0x1800a68d8  cmp     byte ptr [rcx+19h], 4
0x1800a68dc  jb      short loc_1800A68FA
0x1800a68de  mov     edx, 0A4h
0x1800a68e3  mov     [rsp+100h+var_E0], ebx
0x1800a68e7  mov     r9d, [rdi]
0x1800a68ea  lea     r8, WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids
0x1800a68f1  mov     rcx, [rcx+10h]
0x1800a68f5  call    WPP_SF_Dd
0x1800a68fa  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a6901  test    rcx, rcx
0x1800a6904  jnz     short loc_1800A6914
0x1800a6906  lea     rcx, off_1800E5190; this
0x1800a690d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a6914  cmp     byte ptr [rcx+8], 0
0x1800a6918  jz      loc_1800A69F0
0x1800a691e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a6923  cmp     [rax+7CCh], ebx
0x1800a6929  jz      loc_1800A69F0
0x1800a692f  mov     r8d, 7B8h; int
0x1800a6935  mov     r9d, ebx; int
0x1800a6938  lea     rdx, aCrawimagereade_17; "CRawImageReader::AddOneIFDEntryToEntryL"...
0x1800a693f  mov     rcx, rax; this
0x1800a6942  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a6947  jmp     loc_1800A69F0
0x1800a694c  mov     [rbp+37h+var_68], r12
0x1800a6950  lea     rdx, [rbp+37h+var_B0]; struct CRawImageReader::IFDDataEntry *
0x1800a6954  lea     rcx, [rbp+37h+var_60]; this
0x1800a6958  call    ??0IFDDataEntry@CRawImageReader@@QEAA@AEBU01@@Z; CRawImageReader::IFDDataEntry::IFDDataEntry(CRawImageReader::IFDDataEntry const &)
0x1800a695d  nop
0x1800a695e  lea     rcx, [rbp+37h+var_68]
0x1800a6962  call    MF__ExceptionBoundary__lambda_d01e290712e0a6d52430fc96ee8f154f___
0x1800a6967  mov     ebx, eax
0x1800a6969  lea     rcx, [rbp+37h+var_50]
0x1800a696d  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800a6972  test    ebx, ebx
0x1800a6974  jns     short loc_1800A69E9
0x1800a6976  lea     rax, WPP_GLOBAL_Control
0x1800a697d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a6984  cmp     rcx, rax
0x1800a6987  jz      short loc_1800A69B1
0x1800a6989  test    byte ptr [rcx+1Ch], 1
0x1800a698d  jz      short loc_1800A69B1
0x1800a698f  cmp     byte ptr [rcx+19h], 4
0x1800a6993  jb      short loc_1800A69B1
0x1800a6995  mov     edx, 0A5h
0x1800a699a  mov     [rsp+100h+var_E0], ebx
0x1800a699e  mov     r9d, [rdi]
0x1800a69a1  lea     r8, WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids
0x1800a69a8  mov     rcx, [rcx+10h]
0x1800a69ac  call    WPP_SF_Dd
0x1800a69b1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a69b8  test    rcx, rcx
0x1800a69bb  jnz     short loc_1800A69CB
0x1800a69bd  lea     rcx, off_1800E5190; this
0x1800a69c4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a69cb  cmp     byte ptr [rcx+8], 0
0x1800a69cf  jz      short loc_1800A69F0
0x1800a69d1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a69d6  cmp     [rax+7CCh], ebx
0x1800a69dc  jz      short loc_1800A69F0
0x1800a69de  mov     r8d, 7BCh
0x1800a69e4  jmp     loc_1800A6935
0x1800a69e9  lea     eax, [r15+0Ch]
0x1800a69ed  add     [r14], eax
0x1800a69f0  lea     rcx, [rbp+37h+var_A0]
0x1800a69f4  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800a69f9  nop
0x1800a69fa  lea     rcx, [rbp+37h+var_88]; this
0x1800a69fe  call    ??1CAutoTrace@CTraceBase@@QEAA@XZ; CTraceBase::CAutoTrace::~CAutoTrace(void)
0x1800a6a03  nop
0x1800a6a04  lea     rcx, [rsp+100h+var_C0]; this
0x1800a6a09  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800a6a0e  mov     eax, ebx
0x1800a6a10  mov     rcx, [rbp+37h+var_38]
0x1800a6a14  xor     rcx, rsp; StackCookie
0x1800a6a17  call    __security_check_cookie
0x1800a6a1c  mov     rbx, [rsp+100h+arg_8]
0x1800a6a24  add     rsp, 0D0h
0x1800a6a2b  pop     r15
0x1800a6a2d  pop     r14
0x1800a6a2f  pop     r13
0x1800a6a31  pop     r12
0x1800a6a33  pop     rdi
0x1800a6a34  pop     rsi
0x1800a6a35  pop     rbp
0x1800a6a36  retn
```
