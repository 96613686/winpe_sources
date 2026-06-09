# CWICRAWDecoderFrame::CopyPixels(WICRect const *,uint,uint,uchar *)

- ea: `0x1800a13d0`
- end: `0x1800a178f`
- name: `?CopyPixels@CWICRAWDecoderFrame@@UEAAJPEBUWICRect@@IIPEAE@Z`
- size: `959`
- prototype: `int(CWICRAWDecoderFrame *__hidden this, const struct WICRect *, unsigned int, unsigned int, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `13`
- tags: ``

## callees

- `0x1800023a0`
- `0x180002590`
- `0x180002a00`
- `0x18009860c`
- `0x18009b9e4`
- `0x18009cd18`
- `0x18009e8b8`
- `0x1800a0f4c`
- `0x1800a13d0`
- `0x1800a22f4`
- `0x1800a27cc`
- `0x1800a34f8`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a175a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a175a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a1420`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a1420`

## string_xrefs

- `0x1800a1433`: `CWICRAWDecoderFrame::CopyPixels`
- `0x1800a14ac`: `CWICRAWDecoderFrame::CopyPixels`
- `0x1800a1520`: `CWICRAWDecoderFrame::CopyPixels`
- `0x1800a1731`: `CWICRAWDecoderFrame::CopyPixels`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CWICRAWDecoderFrame::CopyPixels(
        CWICRAWDecoderFrame *this,
        const struct WICRect *a2,
        unsigned int a3,
        unsigned int a4,
        unsigned __int8 *a5)
{
  unsigned __int8 *v9; // r15
  struct _RTL_CRITICAL_SECTION *v10; // rbx
  struct CallStackContext *ThreadRelativeContext; // r14
  int v12; // r15d
  int v13; // edi
  void ***v14; // rcx
  struct CallStackContext *v15; // rax
  int v16; // r8d
  void ***v17; // rcx
  void ***v18; // rcx
  CWICRAWDecoderFrame *v19; // rcx
  void ***v20; // rcx
  struct CallStackContext *v21; // rax
  const char *v22; // r9
  __int64 result; // rax
  _BYTE v24[8]; // [rsp+30h] [rbp-88h] BYREF
  __int64 v25; // [rsp+38h] [rbp-80h]
  char *v26; // [rsp+40h] [rbp-78h]
  tagRECT v27; // [rsp+48h] [rbp-70h] BYREF
  _QWORD v28[2]; // [rsp+58h] [rbp-60h] BYREF
  int v29; // [rsp+68h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  v25 = -2;
  v9 = a5;
  *(_QWORD *)&v27.left = a5;
  v10 = (struct _RTL_CRITICAL_SECTION *)((char *)this - 96);
  v26 = (char *)this - 96;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this - 96));
  try
  {
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v24, "CWICRAWDecoderFrame::CopyPixels", 194);
    if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 6) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
      v12 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 296LL))(*((_QWORD *)this + 6));
      *((_OWORD *)ThreadRelativeContext + 125) = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _QWORD *))(**((_QWORD **)this + 6) + 280LL))(
                                                              *((_QWORD *)this + 6),
                                                              v28);
      *((_DWORD *)ThreadRelativeContext + 504) = v12;
      v9 = *(unsigned __int8 **)&v27.left;
    }
    v28[0] = "CWICRAWDecoderFrame::CopyPixels";
    v28[1] = 0;
    v29 = 15;
    OutputMsg(0, 0xFu, "=>%s", "CWICRAWDecoderFrame::CopyPixels");
    if ( v9 )
    {
      *(_QWORD *)&v27.left = 0;
      v27.right = *((_DWORD *)this + 14);
      v27.bottom = *((_DWORD *)this + 15);
      if ( a2 )
      {
        v27.left = a2->X;
        v27.top = a2->Y;
        v27.right = a2->Width + v27.left;
        v27.bottom = v27.top + a2->Height;
      }
      v13 = CWICRAWDecoderFrame::ValidateCrop((CWICRAWDecoderFrame *)((char *)this - 112), &v27);
      if ( v13 >= 0 )
      {
        v13 = CWICRAWDecoderFrame::CheckBufferSize((CWICRAWDecoderFrame *)((char *)this - 112), a3, &v27, a4);
        if ( v13 >= 0 )
        {
          v13 = (*(__int64 (__fastcall **)(_QWORD, tagRECT *, _QWORD, _QWORD, unsigned __int8 *))(**((_QWORD **)this - 6)
                                                                                                + 48LL))(
                  *((_QWORD *)this - 6),
                  &v27,
                  a3,
                  a4,
                  v9);
          if ( v13 < 0 )
          {
            CWICRAWDecoderFrame::LogMemoryStatus(v19);
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            {
              WPP_SF_Dd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                25,
                &WPP_84b1ab63a72c33758566b4fd7a583c4d_Traceguids,
                0,
                v13);
            }
            v20 = (void ***)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v20 = &off_1800E5190;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
            }
            if ( *((_BYTE *)v20 + 8) )
            {
              v21 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v20);
              if ( *((_DWORD *)v21 + 499) != v13 )
                CallStackContext::TraceFailure(v21, "CWICRAWDecoderFrame::CopyPixels", 215, v13);
            }
          }
          goto LABEL_44;
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_84b1ab63a72c33758566b4fd7a583c4d_Traceguids, 0, v13);
        }
        v18 = (void ***)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v18 = &off_1800E5190;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
        }
        if ( !*((_BYTE *)v18 + 8)
          || (v15 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v18), *((_DWORD *)v15 + 499) == v13) )
        {
LABEL_44:
          CAutoTraceStatic::~CAutoTraceStatic((CAutoTraceStatic *)v28);
          CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v24);
          LeaveCriticalSection(v10);
          return (unsigned int)v13;
        }
        v16 = 208;
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_84b1ab63a72c33758566b4fd7a583c4d_Traceguids, 0, v13);
        }
        v17 = (void ***)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v17 = &off_1800E5190;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
        }
        if ( !*((_BYTE *)v17 + 8) )
          goto LABEL_44;
        v15 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v17);
        if ( *((_DWORD *)v15 + 499) == v13 )
          goto LABEL_44;
        v16 = 207;
      }
    }
    else
    {
      v13 = -2147467261;
      v14 = (void ***)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v14 = &off_1800E5190;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
      }
      if ( !*((_BYTE *)v14 + 8) )
        goto LABEL_44;
      v15 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v14);
      if ( *((_DWORD *)v15 + 499) == -2147467261 )
        goto LABEL_44;
      v16 = 195;
    }
    CallStackContext::TraceFailure(v15, "CWICRAWDecoderFrame::CopyPixels", v16, v13);
    goto LABEL_44;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xDB,
                           (unsigned int)"avcore\\mf\\rawimage\\rawimagewicdecoder\\rawimagedecoderframe.cpp",
                           v22);
  }
  return result;
}

```

## disassembly

```asm
0x1800a13d0  push    rbx
0x1800a13d2  push    rsi
0x1800a13d3  push    rdi
0x1800a13d4  push    r12
0x1800a13d6  push    r13
0x1800a13d8  push    r14
0x1800a13da  push    r15
0x1800a13dc  sub     rsp, 80h
0x1800a13e3  mov     [rsp+0B8h+var_80], 0FFFFFFFFFFFFFFFEh
0x1800a13ec  mov     rax, cs:__security_cookie
0x1800a13f3  xor     rax, rsp
0x1800a13f6  mov     [rsp+0B8h+var_48], rax
0x1800a13fb  mov     r13d, r9d
0x1800a13fe  mov     r12d, r8d
0x1800a1401  mov     rdi, rdx
0x1800a1404  mov     rsi, rcx
0x1800a1407  mov     r15, [rsp+0B8h+arg_20]
0x1800a140f  mov     qword ptr [rsp+0B8h+var_70.left], r15
0x1800a1414  lea     rbx, [rcx-60h]
0x1800a1418  mov     [rsp+0B8h+var_78], rbx
0x1800a141d  mov     rcx, rbx; lpCriticalSection
0x1800a1420  call    cs:__imp_EnterCriticalSection
0x1800a1427  nop     dword ptr [rax+rax+00h]
0x1800a142c  nop
0x1800a142d  mov     r8d, 0C2h; int
0x1800a1433  lea     rdx, aCwicrawdecoder; "CWICRAWDecoderFrame::CopyPixels"
0x1800a143a  lea     rcx, [rsp+0B8h+var_88]; this
0x1800a143f  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800a1444  nop
0x1800a1445  xor     r14d, r14d
0x1800a1448  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800a144f  cmp     [rcx+8], r14b
0x1800a1453  jz      short loc_1800A14AC
0x1800a1455  cmp     [rsi+30h], r14
0x1800a1459  jz      short loc_1800A14AC
0x1800a145b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a1460  mov     r14, rax
0x1800a1463  mov     rcx, [rsi+30h]
0x1800a1467  mov     rdx, [rcx]
0x1800a146a  mov     rax, [rdx+128h]
0x1800a1471  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1476  mov     r15d, eax
0x1800a1479  mov     rcx, [rsi+30h]
0x1800a147d  mov     rdx, [rcx]
0x1800a1480  mov     rax, [rdx+118h]
0x1800a1487  lea     rdx, [rsp+0B8h+var_60]
0x1800a148c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1491  movups  xmm0, xmmword ptr [rax]
0x1800a1494  movdqu  xmmword ptr [r14+7D0h], xmm0
0x1800a149d  mov     [r14+7E0h], r15d
0x1800a14a4  mov     r15, qword ptr [rsp+0B8h+var_70.left]
0x1800a14a9  xor     r14d, r14d
0x1800a14ac  lea     rax, aCwicrawdecoder; "CWICRAWDecoderFrame::CopyPixels"
0x1800a14b3  mov     [rsp+0B8h+var_60], rax
0x1800a14b8  mov     [rsp+0B8h+var_58], r14
0x1800a14bd  mov     edx, 0Fh; unsigned int
0x1800a14c2  mov     [rsp+0B8h+var_50], edx
0x1800a14c6  mov     r9, rax
0x1800a14c9  lea     r8, ?_szEntering@@3QBDB; "=>%s"
0x1800a14d0  xor     ecx, ecx; unsigned int
0x1800a14d2  call    ?OutputMsg@@YAXKKPEBDZZ; OutputMsg(ulong,ulong,char const *,...)
0x1800a14d7  nop
0x1800a14d8  test    r15, r15
0x1800a14db  jnz     short loc_1800A1534
0x1800a14dd  mov     edi, 80004003h
0x1800a14e2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a14e9  test    rcx, rcx
0x1800a14ec  jnz     short loc_1800A14FC
0x1800a14ee  lea     rcx, off_1800E5190; this
0x1800a14f5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a14fc  cmp     [rcx+8], r14b
0x1800a1500  jz      loc_1800A1741
0x1800a1506  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a150b  cmp     [rax+7CCh], edi
0x1800a1511  jz      loc_1800A1741
0x1800a1517  mov     r8d, 0C3h; int
0x1800a151d  mov     r9d, edi; int
0x1800a1520  lea     rdx, aCwicrawdecoder; "CWICRAWDecoderFrame::CopyPixels"
0x1800a1527  mov     rcx, rax; this
0x1800a152a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a152f  jmp     loc_1800A1741
0x1800a1534  mov     qword ptr [rsp+0B8h+var_70.left], 0
0x1800a153d  mov     eax, [rsi+38h]
0x1800a1540  mov     [rsp+0B8h+var_70.right], eax
0x1800a1544  mov     eax, [rsi+3Ch]
0x1800a1547  mov     [rsp+0B8h+var_70.bottom], eax
0x1800a154b  test    rdi, rdi
0x1800a154e  jz      short loc_1800A156D
0x1800a1550  mov     ecx, [rdi]
0x1800a1552  mov     [rsp+0B8h+var_70.left], ecx
0x1800a1556  mov     edx, [rdi+4]
0x1800a1559  mov     [rsp+0B8h+var_70.top], edx
0x1800a155d  add     ecx, [rdi+8]
0x1800a1560  mov     [rsp+0B8h+var_70.right], ecx
0x1800a1564  mov     ecx, [rdi+0Ch]
0x1800a1567  add     ecx, edx
0x1800a1569  mov     [rsp+0B8h+var_70.bottom], ecx
0x1800a156d  lea     rdx, [rsp+0B8h+var_70]; struct tagRECT *
0x1800a1572  lea     rcx, [rsi-70h]; this
0x1800a1576  call    ?ValidateCrop@CWICRAWDecoderFrame@@AEAAJAEBUtagRECT@@@Z; CWICRAWDecoderFrame::ValidateCrop(tagRECT const &)
0x1800a157b  mov     edi, eax
0x1800a157d  test    eax, eax
0x1800a157f  jns     short loc_1800A15FC
0x1800a1581  lea     rax, WPP_GLOBAL_Control
0x1800a1588  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a158f  cmp     rcx, rax
0x1800a1592  jz      short loc_1800A15BC
0x1800a1594  test    byte ptr [rcx+1Ch], 1
0x1800a1598  jz      short loc_1800A15BC
0x1800a159a  cmp     byte ptr [rcx+19h], 4
0x1800a159e  jb      short loc_1800A15BC
0x1800a15a0  mov     edx, 17h
0x1800a15a5  mov     dword ptr [rsp+0B8h+var_98], edi
0x1800a15a9  xor     r9d, r9d
0x1800a15ac  lea     r8, WPP_84b1ab63a72c33758566b4fd7a583c4d_Traceguids
0x1800a15b3  mov     rcx, [rcx+10h]
0x1800a15b7  call    WPP_SF_Dd
0x1800a15bc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a15c3  test    rcx, rcx
0x1800a15c6  jnz     short loc_1800A15D6
0x1800a15c8  lea     rcx, off_1800E5190; this
0x1800a15cf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a15d6  cmp     byte ptr [rcx+8], 0
0x1800a15da  jz      loc_1800A1741
0x1800a15e0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a15e5  cmp     [rax+7CCh], edi
0x1800a15eb  jz      loc_1800A1741
0x1800a15f1  mov     r8d, 0CFh
0x1800a15f7  jmp     loc_1800A151D
0x1800a15fc  mov     r9d, r13d; unsigned int
0x1800a15ff  lea     r8, [rsp+0B8h+var_70]; struct tagRECT *
0x1800a1604  mov     edx, r12d; unsigned int
0x1800a1607  lea     rcx, [rsi-70h]; this
0x1800a160b  call    ?CheckBufferSize@CWICRAWDecoderFrame@@AEAAJIPEBUtagRECT@@I@Z; CWICRAWDecoderFrame::CheckBufferSize(uint,tagRECT const *,uint)
0x1800a1610  mov     edi, eax
0x1800a1612  test    eax, eax
0x1800a1614  jns     short loc_1800A1691
0x1800a1616  lea     rax, WPP_GLOBAL_Control
0x1800a161d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a1624  cmp     rcx, rax
0x1800a1627  jz      short loc_1800A1651
0x1800a1629  test    byte ptr [rcx+1Ch], 1
0x1800a162d  jz      short loc_1800A1651
0x1800a162f  cmp     byte ptr [rcx+19h], 4
0x1800a1633  jb      short loc_1800A1651
0x1800a1635  mov     edx, 18h
0x1800a163a  mov     dword ptr [rsp+0B8h+var_98], edi
0x1800a163e  xor     r9d, r9d
0x1800a1641  lea     r8, WPP_84b1ab63a72c33758566b4fd7a583c4d_Traceguids
0x1800a1648  mov     rcx, [rcx+10h]
0x1800a164c  call    WPP_SF_Dd
0x1800a1651  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a1658  test    rcx, rcx
0x1800a165b  jnz     short loc_1800A166B
0x1800a165d  lea     rcx, off_1800E5190; this
0x1800a1664  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a166b  cmp     byte ptr [rcx+8], 0
0x1800a166f  jz      loc_1800A1741
0x1800a1675  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a167a  cmp     [rax+7CCh], edi
0x1800a1680  jz      loc_1800A1741
0x1800a1686  mov     r8d, 0D0h
0x1800a168c  jmp     loc_1800A151D
0x1800a1691  mov     rcx, [rsi-30h]
0x1800a1695  mov     rax, [rcx]
0x1800a1698  mov     [rsp+0B8h+var_98], r15
0x1800a169d  mov     r9d, r13d
0x1800a16a0  mov     r8d, r12d
0x1800a16a3  lea     rdx, [rsp+0B8h+var_70]
0x1800a16a8  mov     rax, [rax+30h]
0x1800a16ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a16b1  mov     edi, eax
0x1800a16b3  test    eax, eax
0x1800a16b5  jns     loc_1800A1741
0x1800a16bb  call    ?LogMemoryStatus@CWICRAWDecoderFrame@@AEAAXXZ; CWICRAWDecoderFrame::LogMemoryStatus(void)
0x1800a16c0  lea     rax, WPP_GLOBAL_Control
0x1800a16c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a16ce  cmp     rcx, rax
0x1800a16d1  jz      short loc_1800A16FB
0x1800a16d3  test    byte ptr [rcx+1Ch], 1
0x1800a16d7  jz      short loc_1800A16FB
0x1800a16d9  cmp     byte ptr [rcx+19h], 4
0x1800a16dd  jb      short loc_1800A16FB
0x1800a16df  mov     edx, 19h
0x1800a16e4  mov     dword ptr [rsp+0B8h+var_98], edi
0x1800a16e8  xor     r9d, r9d
0x1800a16eb  lea     r8, WPP_84b1ab63a72c33758566b4fd7a583c4d_Traceguids
0x1800a16f2  mov     rcx, [rcx+10h]
0x1800a16f6  call    WPP_SF_Dd
0x1800a16fb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a1702  test    rcx, rcx
0x1800a1705  jnz     short loc_1800A1715
0x1800a1707  lea     rcx, off_1800E5190; this
0x1800a170e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a1715  cmp     byte ptr [rcx+8], 0
0x1800a1719  jz      short loc_1800A1741
0x1800a171b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a1720  cmp     [rax+7CCh], edi
0x1800a1726  jz      short loc_1800A1741
0x1800a1728  mov     r9d, edi; int
0x1800a172b  mov     r8d, 0D7h; int
0x1800a1731  lea     rdx, aCwicrawdecoder; "CWICRAWDecoderFrame::CopyPixels"
0x1800a1738  mov     rcx, rax; this
0x1800a173b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a1740  nop
0x1800a1741  lea     rcx, [rsp+0B8h+var_60]; this
0x1800a1746  call    ??1CAutoTraceStatic@@QEAA@XZ; CAutoTraceStatic::~CAutoTraceStatic(void)
0x1800a174b  nop
0x1800a174c  lea     rcx, [rsp+0B8h+var_88]; this
0x1800a1751  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800a1756  nop
0x1800a1757  mov     rcx, rbx; lpCriticalSection
0x1800a175a  call    cs:__imp_LeaveCriticalSection
0x1800a1761  nop     dword ptr [rax+rax+00h]
0x1800a1766  mov     eax, edi
0x1800a1768  jmp     short loc_1800A176E
0x1800a176a  mov     eax, [rsp+0B8h+var_70.left]
0x1800a176e  mov     rcx, [rsp+0B8h+var_48]
0x1800a1773  xor     rcx, rsp; StackCookie
0x1800a1776  call    __security_check_cookie
0x1800a177b  add     rsp, 80h
0x1800a1782  pop     r15
0x1800a1784  pop     r14
0x1800a1786  pop     r13
0x1800a1788  pop     r12
0x1800a178a  pop     rdi
0x1800a178b  pop     rsi
0x1800a178c  pop     rbx
0x1800a178d  retn
```
