# CRawImageReader::CopyEXIFData(int,int,int,uint,void *)

- ea: `0x180001a40`
- end: `0x180002030`
- name: `?CopyEXIFData@CRawImageReader@@AEAAXHHHIPEAX@Z`
- size: `1520`
- prototype: `void __fastcall(CRawImageReader *this, int, unsigned __int16, unsigned int, unsigned int, void *)`
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x1800a9850`

## callees

- `0x180001a40`
- `0x1800020f0`
- `0x180002470`
- `0x180002a00`
- `0x18009b9e4`
- `0x18009e8b8`
- `0x1800a34f8`
- `0x1800a41f0`
- `0x1800a422c`
- `0x1800a4d48`
- `0x1800af278`
- `0x1800afee4`
- `0x1800b4010`

## string_xrefs

- `0x180001a9d`: `CRawImageReader::CopyEXIFData`
- `0x180001ac0`: `CRawImageReader::CopyEXIFData`
- `0x180001ae0`: `CRawImageReader::CopyEXIFData`
- `0x180001b45`: `CRawImageReader::CopyEXIFData`
- `0x180001c35`: `CRawImageReader::CopyEXIFData`
- `0x180001d9d`: `CRawImageReader::CopyEXIFData`
- `0x180001e59`: `CRawImageReader::CopyEXIFData`
- `0x180001f5c`: `CRawImageReader::CopyEXIFData`
- `0x180001fbb`: `CRawImageReader::CopyEXIFData`

## pseudocode

```c
void __fastcall CRawImageReader::CopyEXIFData(
        CRawImageReader *this,
        int a2,
        unsigned __int16 a3,
        unsigned int a4,
        unsigned int a5,
        void *a6)
{
  __int64 v6; // r13
  __int16 v8; // di
  void ***v10; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v12; // rcx
  __int64 v13; // rcx
  struct CallStackContext *v14; // rdi
  int v15; // ebx
  CTraceBase *v16; // rbx
  __int64 v17; // r8
  int v18; // r12d
  void ***v19; // rcx
  struct CallStackContext *v20; // rax
  unsigned int v21; // eax
  int v22; // edi
  int v23; // eax
  void ***v24; // rcx
  struct CallStackContext *v25; // rax
  void ***v26; // rcx
  struct CallStackContext *v27; // rax
  __int64 v28; // rax
  void ***v29; // rcx
  struct CallStackContext *v30; // rax
  struct CallStackContext *v31; // rax
  int v32; // ecx
  int v33; // ecx
  int v34; // [rsp+30h] [rbp-B9h] BYREF
  unsigned __int16 v35; // [rsp+34h] [rbp-B5h] BYREF
  _WORD v36[2]; // [rsp+38h] [rbp-B1h] BYREF
  unsigned int v37; // [rsp+3Ch] [rbp-ADh]
  __int64 v38; // [rsp+40h] [rbp-A9h]
  const char *v39; // [rsp+48h] [rbp-A1h]
  CTraceBase *v40; // [rsp+50h] [rbp-99h]
  __int64 v41; // [rsp+58h] [rbp-91h]
  int v42; // [rsp+60h] [rbp-89h]
  __int16 v43; // [rsp+68h] [rbp-81h] BYREF
  unsigned __int16 v44; // [rsp+6Ah] [rbp-7Fh]
  __int16 v45; // [rsp+6Ch] [rbp-7Dh]
  char v46; // [rsp+6Eh] [rbp-7Bh]
  char v47; // [rsp+6Fh] [rbp-7Ah]
  int v48; // [rsp+70h] [rbp-79h] BYREF
  __int128 v49; // [rsp+78h] [rbp-71h] BYREF
  __int64 v50; // [rsp+88h] [rbp-61h]
  __int16 *v51; // [rsp+90h] [rbp-59h] BYREF
  int v52; // [rsp+98h] [rbp-51h]
  unsigned int v53; // [rsp+9Ch] [rbp-4Dh]
  _BYTE v54[32]; // [rsp+A0h] [rbp-49h] BYREF
  _BYTE v55[40]; // [rsp+C0h] [rbp-29h] BYREF

  v38 = -2;
  v6 = a4;
  v8 = a2;
  v34 = a2;
  v10 = (void ***)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v10 = &off_1800E5190;
    CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
  }
  if ( *((_BYTE *)v10 + 8) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v10);
    v12 = *((unsigned int *)ThreadRelativeContext + 497);
    if ( (unsigned int)v12 < *((_DWORD *)ThreadRelativeContext + 498) )
    {
      v13 = 2 * v12;
      *((_QWORD *)ThreadRelativeContext + v13) = "CRawImageReader::CopyEXIFData";
      *((_DWORD *)ThreadRelativeContext + 2 * v13 + 2) = 1177;
    }
    ++*((_DWORD *)ThreadRelativeContext + 497);
    v10 = (void ***)CallStackTracing::s_wpInstance;
  }
  if ( *((_BYTE *)v10 + 8) && *((_QWORD *)this + 34) )
  {
    v14 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v10);
    v15 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 34) + 296LL))(*((_QWORD *)this + 34));
    *((_OWORD *)v14 + 125) = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, __int16 **))(**((_QWORD **)this + 34) + 280LL))(
                                          *((_QWORD *)this + 34),
                                          &v51);
    *((_DWORD *)v14 + 504) = v15;
    v8 = v34;
  }
  v39 = "CRawImageReader::CopyEXIFData";
  v16 = (CRawImageReader *)((char *)this + 56);
  if ( !this )
    v16 = 0;
  v40 = v16;
  v41 = 0;
  v42 = 15;
  CTraceBase::OutputMsg(v16, 0, 0xFu, "=>%s", "CRawImageReader::CopyEXIFData");
  if ( !a6 )
  {
    v18 = -2147467261;
    goto LABEL_64;
  }
  v36[0] = v8;
  v35 = a3;
  if ( a3 >= 0xEu )
  {
    v18 = -2147418113;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        104,
        &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
        *((unsigned int *)this + 14),
        -2147418113);
    }
    v19 = (void ***)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v19 = &off_1800E5190;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
    }
    if ( *((_BYTE *)v19 + 8) )
    {
      v20 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v19);
      if ( *((_DWORD *)v20 + 499) != -2147418113 )
        CallStackContext::TraceFailure(v20, "CRawImageReader::CopyEXIFData", 1185, -2147418113);
    }
    goto LABEL_64;
  }
  v34 = 12;
  *((_BYTE *)this + 107) = a5 != 18761;
  v48 = 0;
  v49 = 0;
  v50 = 0;
  if ( a5 == 18761 )
  {
    v43 = v8;
    v44 = a3;
    v47 = BYTE3(v6);
    v46 = BYTE2(v6);
    v45 = v6;
  }
  else
  {
    LOBYTE(v43) = HIBYTE(v8);
    HIBYTE(v43) = v8;
    LOBYTE(v44) = HIBYTE(a3);
    HIBYTE(v44) = a3;
    LOBYTE(v45) = BYTE3(v6);
    HIBYTE(v45) = BYTE2(v6);
    v46 = BYTE1(v6);
    v47 = v6;
  }
  v21 = *((_DWORD *)qword_1800D53E8 + a3);
  v37 = v21;
  v22 = v6 * v21;
  if ( (unsigned int)v6 * v21 <= 4 )
  {
    (*(void (__fastcall **)(void *, int *, __int64, __int64))(*(_QWORD *)a6 + 16LL))(a6, &v48, 1, 4);
  }
  else
  {
    v51 = &v43;
    v52 = v6;
    v53 = v21;
    v23 = MF::ExceptionBoundary__lambda_3df30705b6ca250c854580252d1deb7d___(&v51);
    v18 = v23;
    if ( v23 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          105,
          &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
          *((unsigned int *)this + 14),
          v23);
      }
      v24 = (void ***)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v24 = &off_1800E5190;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
      }
      if ( *((_BYTE *)v24 + 8) )
      {
        v25 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v24);
        if ( *((_DWORD *)v25 + 499) != v18 )
          CallStackContext::TraceFailure(v25, "CRawImageReader::CopyEXIFData", 1207, v18);
      }
LABEL_38:
      std::vector<unsigned char>::_Tidy(&v49);
      goto LABEL_64;
    }
    if ( (*(unsigned int (__fastcall **)(void *, _QWORD, _QWORD, __int64))(*(_QWORD *)a6 + 16LL))(a6, v49, v37, v6) != (_DWORD)v6 )
    {
      v18 = -2147418113;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          106,
          &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
          *((unsigned int *)this + 14),
          -2147418113);
      }
      v26 = (void ***)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v26 = &off_1800E5190;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
      }
      if ( *((_BYTE *)v26 + 8) )
      {
        v27 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v26);
        if ( *((_DWORD *)v27 + 499) != -2147418113 )
          CallStackContext::TraceFailure(v27, "CRawImageReader::CopyEXIFData", 1209, -2147418113);
      }
      goto LABEL_38;
    }
    v34 = v22 + 12;
  }
  v28 = ((__int64 (__fastcall *)(_BYTE *, CRawImageReader *, _WORD *, __int16 *, int *, unsigned __int16 *))lambda_1d541eaf7e68fe0bd2d703f7f4ef1bc9_::_lambda_1d541eaf7e68fe0bd2d703f7f4ef1bc9_)(
          v54,
          this,
          v36,
          &v43,
          &v34,
          &v35);
  v18 = MF::ExceptionBoundary__lambda_1d541eaf7e68fe0bd2d703f7f4ef1bc9___(v28);
  std::vector<unsigned char>::_Tidy(v55);
  if ( v18 >= 0 )
  {
    std::vector<unsigned char>::_Tidy(&v49);
    if ( !v18 )
      goto LABEL_68;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        107,
        &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
        *((unsigned int *)this + 14),
        v18);
    }
    v29 = (void ***)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v29 = &off_1800E5190;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
    }
    if ( *((_BYTE *)v29 + 8) )
    {
      v30 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v29);
      if ( *((_DWORD *)v30 + 499) != v18 )
        CallStackContext::TraceFailure(v30, "CRawImageReader::CopyEXIFData", 1241, v18);
    }
    std::vector<unsigned char>::_Tidy(&v49);
  }
LABEL_64:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_DD(*((_QWORD *)WPP_GLOBAL_Control + 2), 108, v17, *((unsigned int *)this + 14), v18);
  }
LABEL_68:
  CTraceBase::OutputMsg(v16, 0, 0xFu, "<=%s", "CRawImageReader::CopyEXIFData");
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
  {
    v31 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v32 = *((_DWORD *)v31 + 497);
    if ( v32 )
    {
      v33 = v32 - 1;
      *((_DWORD *)v31 + 497) = v33;
      if ( !v33 )
        CallStackContext::ClearState(v31);
    }
  }
}

```

## disassembly

```asm
0x180001a40  push    rbp
0x180001a42  push    rbx
0x180001a43  push    rsi
0x180001a44  push    rdi
0x180001a45  push    r12
0x180001a47  push    r13
0x180001a49  push    r14
0x180001a4b  push    r15
0x180001a4d  lea     rbp, [rsp-0Fh]
0x180001a52  sub     rsp, 0F8h
0x180001a59  mov     [rsp+130h+var_F0], 0FFFFFFFFFFFFFFFEh
0x180001a62  mov     rax, cs:__security_cookie
0x180001a69  xor     rax, rsp
0x180001a6c  mov     [rbp+47h+var_48], rax
0x180001a70  mov     r13d, r9d
0x180001a73  mov     r12d, r8d
0x180001a76  mov     edi, edx
0x180001a78  mov     [rsp+130h+var_100], edx
0x180001a7c  mov     rsi, rcx
0x180001a7f  mov     r14, [rbp+47h+arg_28]
0x180001a83  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180001a8a  test    rcx, rcx
0x180001a8d  jnz     short loc_180001A9D
0x180001a8f  lea     rcx, off_1800E5190; this
0x180001a96  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180001a9d  lea     rax, aCrawimagereade_10; "CRawImageReader::CopyEXIFData"
0x180001aa4  cmp     byte ptr [rcx+8], 0
0x180001aa8  jz      short loc_180001AE7
0x180001aaa  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180001aaf  mov     ecx, [rax+7C4h]
0x180001ab5  cmp     ecx, [rax+7C8h]
0x180001abb  jnb     short loc_180001AD3
0x180001abd  add     rcx, rcx
0x180001ac0  lea     rdx, aCrawimagereade_10; "CRawImageReader::CopyEXIFData"
0x180001ac7  mov     [rax+rcx*8], rdx
0x180001acb  mov     dword ptr [rax+rcx*8+8], 499h
0x180001ad3  inc     dword ptr [rax+7C4h]
0x180001ad9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180001ae0  lea     rax, aCrawimagereade_10; "CRawImageReader::CopyEXIFData"
0x180001ae7  cmp     byte ptr [rcx+8], 0
0x180001aeb  jz      short loc_180001B4C
0x180001aed  cmp     qword ptr [rsi+110h], 0
0x180001af5  jz      short loc_180001B4C
0x180001af7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180001afc  mov     rdi, rax
0x180001aff  mov     rcx, [rsi+110h]
0x180001b06  mov     rdx, [rcx]
0x180001b09  mov     rax, [rdx+128h]
0x180001b10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b15  mov     ebx, eax
0x180001b17  mov     rcx, [rsi+110h]
0x180001b1e  mov     rdx, [rcx]
0x180001b21  mov     rax, [rdx+118h]
0x180001b28  lea     rdx, [rbp+47h+var_A0]
0x180001b2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b31  movups  xmm0, xmmword ptr [rax]
0x180001b34  movups  xmmword ptr [rdi+7D0h], xmm0
0x180001b3b  mov     [rdi+7E0h], ebx
0x180001b41  mov     edi, [rsp+130h+var_100]
0x180001b45  lea     rax, aCrawimagereade_10; "CRawImageReader::CopyEXIFData"
0x180001b4c  mov     [rsp+130h+var_E8], rax
0x180001b51  lea     rbx, [rsi+38h]
0x180001b55  xor     ecx, ecx
0x180001b57  test    rsi, rsi
0x180001b5a  cmovz   rbx, rcx
0x180001b5e  mov     [rsp+130h+var_E0], rbx
0x180001b63  mov     [rsp+130h+var_D8], rcx
0x180001b68  mov     [rsp+130h+var_D0], 0Fh
0x180001b70  mov     [rsp+130h+var_110], rax
0x180001b75  lea     r9, ?_szEntering@@3QBDB; "=>%s"
0x180001b7c  xor     edx, edx; unsigned int
0x180001b7e  mov     r8d, 0Fh; unsigned int
0x180001b84  mov     rcx, rbx; this
0x180001b87  call    ?OutputMsg@CTraceBase@@QEAA_NKKPEBDZZ; CTraceBase::OutputMsg(ulong,ulong,char const *,...)
0x180001b8c  nop
0x180001b8d  test    r14, r14
0x180001b90  jnz     short loc_180001B9D
0x180001b92  mov     r12d, 80004003h
0x180001b98  jmp     loc_180001F84
0x180001b9d  mov     [rsp+130h+var_F8], di
0x180001ba2  mov     [rsp+130h+var_FC], r12w
0x180001ba8  cmp     r12w, 0Eh
0x180001bad  jb      loc_180001C49
0x180001bb3  mov     r12d, 8000FFFFh
0x180001bb9  lea     rdi, WPP_GLOBAL_Control
0x180001bc0  mov     rcx, cs:WPP_GLOBAL_Control
0x180001bc7  cmp     rcx, rdi
0x180001bca  jz      short loc_180001BF6
0x180001bcc  test    byte ptr [rcx+1Ch], 1
0x180001bd0  jz      short loc_180001BF6
0x180001bd2  cmp     byte ptr [rcx+19h], 4
0x180001bd6  jb      short loc_180001BF6
0x180001bd8  mov     edx, 68h ; 'h'
0x180001bdd  mov     dword ptr [rsp+130h+var_110], r12d
0x180001be2  mov     r9d, [rsi+38h]
0x180001be6  lea     r8, WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids
0x180001bed  mov     rcx, [rcx+10h]
0x180001bf1  call    WPP_SF_Dd
0x180001bf6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180001bfd  test    rcx, rcx
0x180001c00  jnz     short loc_180001C10
0x180001c02  lea     rcx, off_1800E5190; this
0x180001c09  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180001c10  cmp     byte ptr [rcx+8], 0
0x180001c14  jz      loc_180001F8B
0x180001c1a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180001c1f  cmp     [rax+7CCh], r12d
0x180001c26  jz      loc_180001F8B
0x180001c2c  mov     r9d, r12d; int
0x180001c2f  mov     r8d, 4A1h; int
0x180001c35  lea     rdx, aCrawimagereade_10; "CRawImageReader::CopyEXIFData"
0x180001c3c  mov     rcx, rax; this
0x180001c3f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180001c44  jmp     loc_180001F8B
0x180001c49  mov     [rsp+130h+var_100], 0Ch
0x180001c51  cmp     [rbp+47h+arg_20], 4949h
0x180001c58  setnz   al
0x180001c5b  mov     [rsi+6Bh], al
0x180001c5e  mov     [rbp+47h+var_C0], 0
0x180001c65  xorps   xmm0, xmm0
0x180001c68  movdqu  [rbp+47h+var_B8], xmm0
0x180001c6d  mov     [rbp+47h+var_A8], 0
0x180001c75  movzx   eax, di
0x180001c78  shr     ax, 8
0x180001c7c  movzx   edx, r12w
0x180001c80  shr     dx, 8
0x180001c84  mov     ecx, r13d
0x180001c87  shr     ecx, 10h
0x180001c8a  cmp     [rbp+47h+arg_20], 4949h
0x180001c91  jnz     short loc_180001CBD
0x180001c93  mov     [rbp+47h+var_C7], al
0x180001c96  mov     [rsp+130h+var_C8], dil
0x180001c9b  mov     [rbp+47h+var_C5], dl
0x180001c9e  mov     [rbp+47h+var_C6], r12b
0x180001ca2  mov     edx, r13d
0x180001ca5  shr     edx, 18h
0x180001ca8  mov     eax, r13d
0x180001cab  shr     eax, 8
0x180001cae  mov     [rbp+47h+var_C1], dl
0x180001cb1  mov     [rbp+47h+var_C2], cl
0x180001cb4  mov     [rbp+47h+var_C3], al
0x180001cb7  mov     [rbp+47h+var_C4], r13b
0x180001cbb  jmp     short loc_180001CE5
0x180001cbd  mov     [rsp+130h+var_C8], al
0x180001cc1  mov     [rbp+47h+var_C7], dil
0x180001cc5  mov     [rbp+47h+var_C6], dl
0x180001cc8  mov     [rbp+47h+var_C5], r12b
0x180001ccc  mov     edx, r13d
0x180001ccf  shr     edx, 18h
0x180001cd2  mov     eax, r13d
0x180001cd5  shr     eax, 8
0x180001cd8  mov     [rbp+47h+var_C4], dl
0x180001cdb  mov     [rbp+47h+var_C3], cl
0x180001cde  mov     [rbp+47h+var_C2], al
0x180001ce1  mov     [rbp+47h+var_C1], r13b
0x180001ce5  movzx   eax, r12w
0x180001ce9  lea     rcx, qword_1800D53E8
0x180001cf0  mov     eax, [rcx+rax*4]
0x180001cf3  mov     [rsp+130h+var_F4], eax
0x180001cf7  mov     edi, eax
0x180001cf9  imul    edi, r13d
0x180001cfd  cmp     edi, 4
0x180001d00  jbe     loc_180001E80
0x180001d06  lea     rcx, [rsp+130h+var_C8]
0x180001d0b  mov     [rbp+47h+var_A0], rcx
0x180001d0f  mov     [rbp+47h+var_98], r13d
0x180001d13  mov     [rbp+47h+var_94], eax
0x180001d16  lea     rcx, [rbp+47h+var_A0]
0x180001d1a  call    MF__ExceptionBoundary__lambda_3df30705b6ca250c854580252d1deb7d___
0x180001d1f  mov     r12d, eax
0x180001d22  test    eax, eax
0x180001d24  jns     loc_180001DBB
0x180001d2a  lea     rdi, WPP_GLOBAL_Control
0x180001d31  mov     rcx, cs:WPP_GLOBAL_Control
0x180001d38  cmp     rcx, rdi
0x180001d3b  jz      short loc_180001D66
0x180001d3d  test    byte ptr [rcx+1Ch], 1
0x180001d41  jz      short loc_180001D66
0x180001d43  cmp     byte ptr [rcx+19h], 4
0x180001d47  jb      short loc_180001D66
0x180001d49  mov     edx, 69h ; 'i'
0x180001d4e  mov     dword ptr [rsp+130h+var_110], eax
0x180001d52  mov     r9d, [rsi+38h]
0x180001d56  lea     r8, WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids
0x180001d5d  mov     rcx, [rcx+10h]
0x180001d61  call    WPP_SF_Dd
0x180001d66  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180001d6d  test    rcx, rcx
0x180001d70  jnz     short loc_180001D80
0x180001d72  lea     rcx, off_1800E5190; this
0x180001d79  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180001d80  cmp     byte ptr [rcx+8], 0
0x180001d84  jz      short loc_180001DAD
0x180001d86  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180001d8b  cmp     [rax+7CCh], r12d
0x180001d92  jz      short loc_180001DAD
0x180001d94  mov     r9d, r12d; int
0x180001d97  mov     r8d, 4B7h; int
0x180001d9d  lea     rdx, aCrawimagereade_10; "CRawImageReader::CopyEXIFData"
0x180001da4  mov     rcx, rax; this
0x180001da7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180001dac  nop
0x180001dad  lea     rcx, [rbp+47h+var_B8]
0x180001db1  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180001db6  jmp     loc_180001F8B
0x180001dbb  mov     r9, r13
0x180001dbe  mov     r8d, [rsp+130h+var_F4]
0x180001dc3  mov     rax, [r14]
0x180001dc6  mov     rdx, qword ptr [rbp+47h+var_B8]
0x180001dca  mov     rcx, r14
0x180001dcd  mov     rax, [rax+10h]
0x180001dd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001dd6  cmp     eax, r13d
0x180001dd9  jz      loc_180001E77
0x180001ddf  mov     r12d, 8000FFFFh
0x180001de5  lea     rdi, WPP_GLOBAL_Control
0x180001dec  mov     rcx, cs:WPP_GLOBAL_Control
0x180001df3  cmp     rcx, rdi
0x180001df6  jz      short loc_180001E22
0x180001df8  test    byte ptr [rcx+1Ch], 1
0x180001dfc  jz      short loc_180001E22
0x180001dfe  cmp     byte ptr [rcx+19h], 4
0x180001e02  jb      short loc_180001E22
0x180001e04  mov     edx, 6Ah ; 'j'
0x180001e09  mov     dword ptr [rsp+130h+var_110], r12d
0x180001e0e  mov     r9d, [rsi+38h]
0x180001e12  lea     r8, WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids
0x180001e19  mov     rcx, [rcx+10h]
0x180001e1d  call    WPP_SF_Dd
0x180001e22  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180001e29  test    rcx, rcx
0x180001e2c  jnz     short loc_180001E3C
0x180001e2e  lea     rcx, off_1800E5190; this
0x180001e35  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180001e3c  cmp     byte ptr [rcx+8], 0
0x180001e40  jz      short loc_180001E69
0x180001e42  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180001e47  cmp     [rax+7CCh], r12d
0x180001e4e  jz      short loc_180001E69
0x180001e50  mov     r9d, r12d; int
0x180001e53  mov     r8d, 4B9h; int
0x180001e59  lea     rdx, aCrawimagereade_10; "CRawImageReader::CopyEXIFData"
0x180001e60  mov     rcx, rax; this
0x180001e63  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180001e68  nop
0x180001e69  lea     rcx, [rbp+47h+var_B8]
0x180001e6d  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180001e72  jmp     loc_180001F8B
0x180001e77  lea     eax, [rdi+0Ch]
0x180001e7a  mov     [rsp+130h+var_100], eax
0x180001e7e  jmp     short loc_180001E9F
0x180001e80  mov     rax, [r14]
0x180001e83  mov     r9d, 4
0x180001e89  mov     r8d, 1
0x180001e8f  lea     rdx, [rbp+47h+var_C0]
0x180001e93  mov     rcx, r14
0x180001e96  mov     rax, [rax+10h]
0x180001e9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e9f  lea     rax, [rsp+130h+var_FC]
0x180001ea4  mov     [rsp+130h+var_108], rax
0x180001ea9  lea     rax, [rsp+130h+var_100]
0x180001eae  mov     [rsp+130h+var_110], rax
0x180001eb3  lea     r9, [rsp+130h+var_C8]
0x180001eb8  lea     r8, [rsp+130h+var_F8]
0x180001ebd  mov     rdx, rsi
0x180001ec0  lea     rcx, [rbp+47h+var_90]
0x180001ec4  call    _lambda_1d541eaf7e68fe0bd2d703f7f4ef1bc9____lambda_1d541eaf7e68fe0bd2d703f7f4ef1bc9_
0x180001ec9  nop
0x180001eca  mov     rcx, rax
0x180001ecd  call    MF__ExceptionBoundary__lambda_1d541eaf7e68fe0bd2d703f7f4ef1bc9___
0x180001ed2  mov     r12d, eax
0x180001ed5  mov     edi, eax
0x180001ed7  lea     rcx, [rbp+47h+var_70]
0x180001edb  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180001ee0  test    edi, edi
0x180001ee2  jns     loc_180001F77
0x180001ee8  lea     rdi, WPP_GLOBAL_Control
0x180001eef  mov     rcx, cs:WPP_GLOBAL_Control
0x180001ef6  cmp     rcx, rdi
0x180001ef9  jz      short loc_180001F25
0x180001efb  test    byte ptr [rcx+1Ch], 1
0x180001eff  jz      short loc_180001F25
0x180001f01  cmp     byte ptr [rcx+19h], 4
0x180001f05  jb      short loc_180001F25
0x180001f07  mov     edx, 6Bh ; 'k'
0x180001f0c  mov     dword ptr [rsp+130h+var_110], r12d
0x180001f11  mov     r9d, [rsi+38h]
0x180001f15  lea     r8, WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids
0x180001f1c  mov     rcx, [rcx+10h]
0x180001f20  call    WPP_SF_Dd
0x180001f25  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180001f2c  test    rcx, rcx
0x180001f2f  jnz     short loc_180001F3F
0x180001f31  lea     rcx, off_1800E5190; this
0x180001f38  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180001f3f  cmp     byte ptr [rcx+8], 0
0x180001f43  jz      short loc_180001F6C
0x180001f45  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180001f4a  cmp     [rax+7CCh], r12d
0x180001f51  jz      short loc_180001F6C
  ... truncated ...
```
