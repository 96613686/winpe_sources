# CRawImageReader::CopyBuffer(uchar *,uint,tagRECT *,uint,uint,uchar *)

- ea: `0x1800a6d94`
- end: `0x1800a7121`
- name: `?CopyBuffer@CRawImageReader@@AEAAJPEAEIPEAUtagRECT@@II0@Z`
- size: `909`
- prototype: `int(CRawImageReader *__hidden this, unsigned __int8 *, unsigned int, struct tagRECT *, unsigned int, unsigned int, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1800aa7f0`

## callees

- `0x180002040`
- `0x1800020a0`
- `0x1800023a0`
- `0x180002590`
- `0x180002a00`
- `0x18009b9e4`
- `0x18009e8b8`
- `0x1800a34f8`
- `0x1800a6d94`
- `0x1800b4010`

## import_xrefs

- `MFPlat!MFCopyImage` at `0x1800a6fd7`
- `MFPlat!MFCopyImage` at `0x1800a6fd7`

## string_xrefs

- `0x1800a6dd7`: `CRawImageReader::CopyBuffer`
- `0x1800a6e59`: `CRawImageReader::CopyBuffer`
- `0x1800a70db`: `CRawImageReader::CopyBuffer`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CRawImageReader::CopyBuffer(
        CRawImageReader *this,
        unsigned __int8 *a2,
        LONG a3,
        struct tagRECT *a4,
        LONG lDestStride,
        unsigned int a6,
        unsigned __int8 *pDest)
{
  int *v11; // r9
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v13; // ebx
  unsigned int *v14; // rsi
  LONG left; // r8d
  LONG right; // eax
  HRESULT v17; // ebx
  void ***v18; // rcx
  struct CallStackContext *v19; // rax
  int v20; // r9d
  int v21; // r8d
  LONG top; // ecx
  LONG bottom; // r9d
  void ***v24; // rcx
  unsigned __int64 v25; // r10
  void ***v26; // rcx
  void ***v27; // rcx
  DWORD dwWidthInBytes; // [rsp+20h] [rbp-98h]
  _BYTE v30[8]; // [rsp+30h] [rbp-88h] BYREF
  __int64 v31; // [rsp+38h] [rbp-80h]
  _BYTE v32[32]; // [rsp+40h] [rbp-78h] BYREF

  v31 = -2;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v30, "CRawImageReader::CopyBuffer", 1088);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 34) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v13 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 34) + 296LL))(*((_QWORD *)this + 34));
    *((_OWORD *)ThreadRelativeContext + 125) = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 34) + 280LL))(
                                                            *((_QWORD *)this + 34),
                                                            v32);
    *((_DWORD *)ThreadRelativeContext + 504) = v13;
  }
  v14 = (unsigned int *)((char *)this + 56);
  CTraceBase::CAutoTrace::CAutoTrace(
    (CTraceBase::CAutoTrace *)v32,
    (struct CTraceBase *)(((unsigned __int64)this + 56) & -(__int64)(this != 0)),
    "CRawImageReader::CopyBuffer",
    v11,
    dwWidthInBytes);
  left = a4->left;
  right = a4->right;
  if ( right >= a4->left )
  {
    top = a4->top;
    bottom = a4->bottom;
    if ( bottom >= top )
    {
      v25 = 3LL * (unsigned int)(right - left);
      if ( v25 > 0xFFFFFFFF )
      {
        v17 = -2147024362;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            101,
            &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
            *v14,
            -2147024362);
        }
        v27 = (void ***)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v27 = &off_1800E5190;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
        }
        if ( !*((_BYTE *)v27 + 8) )
          goto LABEL_46;
        v19 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v27);
        if ( *((_DWORD *)v19 + 499) == -2147024362 )
          goto LABEL_46;
        v21 = 1094;
      }
      else
      {
        v17 = MFCopyImage(pDest, lDestStride, &a2[3 * left + a3 * top], a3, v25, bottom - top);
        if ( v17 >= 0 )
          goto LABEL_46;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            102,
            &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
            *v14,
            v17);
        }
        v26 = (void ***)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v26 = &off_1800E5190;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
        }
        if ( !*((_BYTE *)v26 + 8) )
          goto LABEL_46;
        v19 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v26);
        if ( *((_DWORD *)v19 + 499) == v17 )
          goto LABEL_46;
        v21 = 1095;
      }
      v20 = v17;
      goto LABEL_45;
    }
    v17 = -2147418113;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        100,
        &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
        *v14,
        -2147418113);
    }
    v24 = (void ***)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v24 = &off_1800E5190;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
    }
    if ( *((_BYTE *)v24 + 8) )
    {
      v19 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v24);
      if ( *((_DWORD *)v19 + 499) != -2147418113 )
      {
        v20 = -2147418113;
        v21 = 1090;
        goto LABEL_45;
      }
    }
  }
  else
  {
    v17 = -2147418113;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        99,
        &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
        *v14,
        -2147418113);
    }
    v18 = (void ***)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v18 = &off_1800E5190;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
    }
    if ( *((_BYTE *)v18 + 8) )
    {
      v19 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v18);
      if ( *((_DWORD *)v19 + 499) != -2147418113 )
      {
        v20 = -2147418113;
        v21 = 1089;
LABEL_45:
        CallStackContext::TraceFailure(v19, "CRawImageReader::CopyBuffer", v21, v20);
      }
    }
  }
LABEL_46:
  CTraceBase::CAutoTrace::~CAutoTrace((CTraceBase::CAutoTrace *)v32);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v30);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x1800a6d94  push    rbx
0x1800a6d96  push    rbp
0x1800a6d97  push    rsi
0x1800a6d98  push    rdi
0x1800a6d99  push    r12
0x1800a6d9b  push    r13
0x1800a6d9d  push    r14
0x1800a6d9f  push    r15
0x1800a6da1  sub     rsp, 78h
0x1800a6da5  mov     [rsp+0B8h+var_80], 0FFFFFFFFFFFFFFFEh
0x1800a6dae  mov     rax, cs:__security_cookie
0x1800a6db5  xor     rax, rsp
0x1800a6db8  mov     [rsp+0B8h+var_58], rax
0x1800a6dbd  mov     r14, r9
0x1800a6dc0  mov     r15d, r8d
0x1800a6dc3  mov     r12, rdx
0x1800a6dc6  mov     rbp, rcx
0x1800a6dc9  mov     r13, [rsp+0B8h+pDest]
0x1800a6dd1  mov     r8d, 440h; int
0x1800a6dd7  lea     rdx, aCrawimagereade_25; "CRawImageReader::CopyBuffer"
0x1800a6dde  lea     rcx, [rsp+0B8h+var_88]; this
0x1800a6de3  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800a6de8  nop
0x1800a6de9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800a6df0  cmp     byte ptr [rcx+8], 0
0x1800a6df4  jz      short loc_1800A6E4C
0x1800a6df6  cmp     qword ptr [rbp+110h], 0
0x1800a6dfe  jz      short loc_1800A6E4C
0x1800a6e00  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a6e05  mov     rdi, rax
0x1800a6e08  mov     rcx, [rbp+110h]
0x1800a6e0f  mov     rdx, [rcx]
0x1800a6e12  mov     rax, [rdx+128h]
0x1800a6e19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6e1e  mov     ebx, eax
0x1800a6e20  mov     rcx, [rbp+110h]
0x1800a6e27  mov     rdx, [rcx]
0x1800a6e2a  mov     rax, [rdx+118h]
0x1800a6e31  lea     rdx, [rsp+0B8h+var_78]
0x1800a6e36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6e3b  movups  xmm0, xmmword ptr [rax]
0x1800a6e3e  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x1800a6e46  mov     [rdi+7E0h], ebx
0x1800a6e4c  lea     rsi, [rbp+38h]
0x1800a6e50  neg     rbp
0x1800a6e53  sbb     rdx, rdx
0x1800a6e56  and     rdx, rsi; struct CTraceBase *
0x1800a6e59  lea     r8, aCrawimagereade_25; "CRawImageReader::CopyBuffer"
0x1800a6e60  lea     rcx, [rsp+0B8h+var_78]; this
0x1800a6e65  call    ??0CAutoTrace@CTraceBase@@QEAA@PEAV1@PEBDPEAJH@Z; CTraceBase::CAutoTrace::CAutoTrace(CTraceBase *,char const *,long *,int)
0x1800a6e6a  nop
0x1800a6e6b  mov     r8d, [r14]
0x1800a6e6e  mov     eax, [r14+8]
0x1800a6e72  cmp     eax, r8d
0x1800a6e75  jge     loc_1800A6F00
0x1800a6e7b  mov     edi, 8000FFFFh
0x1800a6e80  mov     ebx, edi
0x1800a6e82  lea     rax, WPP_GLOBAL_Control
0x1800a6e89  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a6e90  cmp     rcx, rax
0x1800a6e93  jz      short loc_1800A6EBD
0x1800a6e95  test    byte ptr [rcx+1Ch], 1
0x1800a6e99  jz      short loc_1800A6EBD
0x1800a6e9b  cmp     byte ptr [rcx+19h], 4
0x1800a6e9f  jb      short loc_1800A6EBD
0x1800a6ea1  mov     edx, 63h ; 'c'
0x1800a6ea6  mov     [rsp+0B8h+dwWidthInBytes], edi
0x1800a6eaa  mov     r9d, [rsi]
0x1800a6ead  lea     r8, WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids
0x1800a6eb4  mov     rcx, [rcx+10h]
0x1800a6eb8  call    WPP_SF_Dd
0x1800a6ebd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a6ec4  test    rcx, rcx
0x1800a6ec7  jnz     short loc_1800A6ED7
0x1800a6ec9  lea     rcx, off_1800E5190; this
0x1800a6ed0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a6ed7  cmp     byte ptr [rcx+8], 0
0x1800a6edb  jz      loc_1800A70EB
0x1800a6ee1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a6ee6  cmp     [rax+7CCh], edi
0x1800a6eec  jz      loc_1800A70EB
0x1800a6ef2  mov     r9d, edi
0x1800a6ef5  mov     r8d, 441h
0x1800a6efb  jmp     loc_1800A70DB
0x1800a6f00  mov     ecx, [r14+4]
0x1800a6f04  mov     r9d, [r14+0Ch]
0x1800a6f08  cmp     r9d, ecx
0x1800a6f0b  jge     loc_1800A6F96
0x1800a6f11  mov     edi, 8000FFFFh
0x1800a6f16  mov     ebx, edi
0x1800a6f18  lea     rax, WPP_GLOBAL_Control
0x1800a6f1f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a6f26  cmp     rcx, rax
0x1800a6f29  jz      short loc_1800A6F53
0x1800a6f2b  test    byte ptr [rcx+1Ch], 1
0x1800a6f2f  jz      short loc_1800A6F53
0x1800a6f31  cmp     byte ptr [rcx+19h], 4
0x1800a6f35  jb      short loc_1800A6F53
0x1800a6f37  mov     edx, 64h ; 'd'
0x1800a6f3c  mov     [rsp+0B8h+dwWidthInBytes], edi
0x1800a6f40  mov     r9d, [rsi]
0x1800a6f43  lea     r8, WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids
0x1800a6f4a  mov     rcx, [rcx+10h]
0x1800a6f4e  call    WPP_SF_Dd
0x1800a6f53  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a6f5a  test    rcx, rcx
0x1800a6f5d  jnz     short loc_1800A6F6D
0x1800a6f5f  lea     rcx, off_1800E5190; this
0x1800a6f66  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a6f6d  cmp     byte ptr [rcx+8], 0
0x1800a6f71  jz      loc_1800A70EB
0x1800a6f77  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a6f7c  cmp     [rax+7CCh], edi
0x1800a6f82  jz      loc_1800A70EB
0x1800a6f88  mov     r9d, edi
0x1800a6f8b  mov     r8d, 442h
0x1800a6f91  jmp     loc_1800A70DB
0x1800a6f96  sub     eax, r8d
0x1800a6f99  lea     r10, [rax+rax*2]
0x1800a6f9d  mov     eax, 0FFFFFFFFh
0x1800a6fa2  cmp     r10, rax
0x1800a6fa5  ja      loc_1800A7065
0x1800a6fab  sub     r9d, ecx
0x1800a6fae  imul    ecx, r15d
0x1800a6fb2  lea     eax, [r8+r8*2]
0x1800a6fb6  movsxd  r8, eax
0x1800a6fb9  lea     rax, [r12+rcx]
0x1800a6fbd  add     r8, rax; pSrc
0x1800a6fc0  mov     [rsp+0B8h+dwLines], r9d; dwLines
0x1800a6fc5  mov     [rsp+0B8h+dwWidthInBytes], r10d; dwWidthInBytes
0x1800a6fca  mov     r9d, r15d; lSrcStride
0x1800a6fcd  mov     edx, [rsp+0B8h+lDestStride]; lDestStride
0x1800a6fd4  mov     rcx, r13; pDest
0x1800a6fd7  call    cs:__imp_MFCopyImage
0x1800a6fde  nop     dword ptr [rax+rax+00h]
0x1800a6fe3  mov     ebx, eax
0x1800a6fe5  test    eax, eax
0x1800a6fe7  jns     loc_1800A70EB
0x1800a6fed  lea     rax, WPP_GLOBAL_Control
0x1800a6ff4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a6ffb  cmp     rcx, rax
0x1800a6ffe  jz      short loc_1800A7028
0x1800a7000  test    byte ptr [rcx+1Ch], 1
0x1800a7004  jz      short loc_1800A7028
0x1800a7006  cmp     byte ptr [rcx+19h], 4
0x1800a700a  jb      short loc_1800A7028
0x1800a700c  mov     edx, 66h ; 'f'
0x1800a7011  mov     [rsp+0B8h+dwWidthInBytes], ebx
0x1800a7015  mov     r9d, [rsi]
0x1800a7018  lea     r8, WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids
0x1800a701f  mov     rcx, [rcx+10h]
0x1800a7023  call    WPP_SF_Dd
0x1800a7028  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a702f  test    rcx, rcx
0x1800a7032  jnz     short loc_1800A7042
0x1800a7034  lea     rcx, off_1800E5190; this
0x1800a703b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a7042  cmp     byte ptr [rcx+8], 0
0x1800a7046  jz      loc_1800A70EB
0x1800a704c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a7051  cmp     [rax+7CCh], ebx
0x1800a7057  jz      loc_1800A70EB
0x1800a705d  mov     r8d, 447h
0x1800a7063  jmp     short loc_1800A70D8
0x1800a7065  mov     ebx, 80070216h
0x1800a706a  lea     rax, WPP_GLOBAL_Control
0x1800a7071  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a7078  cmp     rcx, rax
0x1800a707b  jz      short loc_1800A70A5
0x1800a707d  test    byte ptr [rcx+1Ch], 1
0x1800a7081  jz      short loc_1800A70A5
0x1800a7083  cmp     byte ptr [rcx+19h], 4
0x1800a7087  jb      short loc_1800A70A5
0x1800a7089  mov     edx, 65h ; 'e'
0x1800a708e  mov     [rsp+0B8h+dwWidthInBytes], ebx
0x1800a7092  mov     r9d, [rsi]
0x1800a7095  lea     r8, WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids
0x1800a709c  mov     rcx, [rcx+10h]
0x1800a70a0  call    WPP_SF_Dd
0x1800a70a5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a70ac  test    rcx, rcx
0x1800a70af  jnz     short loc_1800A70BF
0x1800a70b1  lea     rcx, off_1800E5190; this
0x1800a70b8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a70bf  cmp     byte ptr [rcx+8], 0
0x1800a70c3  jz      short loc_1800A70EB
0x1800a70c5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a70ca  cmp     [rax+7CCh], ebx
0x1800a70d0  jz      short loc_1800A70EB
0x1800a70d2  mov     r8d, 446h; int
0x1800a70d8  mov     r9d, ebx; int
0x1800a70db  lea     rdx, aCrawimagereade_25; "CRawImageReader::CopyBuffer"
0x1800a70e2  mov     rcx, rax; this
0x1800a70e5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a70ea  nop
0x1800a70eb  lea     rcx, [rsp+0B8h+var_78]; this
0x1800a70f0  call    ??1CAutoTrace@CTraceBase@@QEAA@XZ; CTraceBase::CAutoTrace::~CAutoTrace(void)
0x1800a70f5  nop
0x1800a70f6  lea     rcx, [rsp+0B8h+var_88]; this
0x1800a70fb  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800a7100  mov     eax, ebx
0x1800a7102  mov     rcx, [rsp+0B8h+var_58]
0x1800a7107  xor     rcx, rsp; StackCookie
0x1800a710a  call    __security_check_cookie
0x1800a710f  add     rsp, 78h
0x1800a7113  pop     r15
0x1800a7115  pop     r14
0x1800a7117  pop     r13
0x1800a7119  pop     r12
0x1800a711b  pop     rdi
0x1800a711c  pop     rsi
0x1800a711d  pop     rbp
0x1800a711e  pop     rbx
0x1800a711f  retn
```
