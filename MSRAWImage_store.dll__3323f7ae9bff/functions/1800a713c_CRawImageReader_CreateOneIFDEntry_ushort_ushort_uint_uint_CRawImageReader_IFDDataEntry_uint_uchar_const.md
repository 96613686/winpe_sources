# CRawImageReader::CreateOneIFDEntry(ushort,ushort,uint,uint,CRawImageReader::IFDDataEntry &,uint,uchar const *)

- ea: `0x1800a713c`
- end: `0x1800a7518`
- name: `?CreateOneIFDEntry@CRawImageReader@@AEAAJGGIIAEAUIFDDataEntry@1@IPEBE@Z`
- size: `988`
- prototype: `__int64 __fastcall(CRawImageReader *this, __int16, unsigned __int16, int, unsigned int, struct CRawImageReader::IFDDataEntry *, size_t Size, const unsigned __int8 *Src)`
- caller_count: `2`
- callee_count: `12`
- tags: ``

## callers

- `0x1800a6784`
- `0x1800ae6b8`

## callees

- `0x180002040`
- `0x1800020a0`
- `0x1800023a0`
- `0x180002590`
- `0x180002a00`
- `0x18009b9e4`
- `0x18009e8b8`
- `0x1800a34f8`
- `0x1800a41a4`
- `0x1800a713c`
- `0x1800b0460`
- `0x1800b4010`

## string_xrefs

- `0x1800a719a`: `CRawImageReader::CreateOneIFDEntry`
- `0x1800a7225`: `CRawImageReader::CreateOneIFDEntry`
- `0x1800a74c2`: `CRawImageReader::CreateOneIFDEntry`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CRawImageReader::CreateOneIFDEntry(
        CRawImageReader *this,
        __int16 a2,
        unsigned __int16 a3,
        int a4,
        unsigned int a5,
        struct CRawImageReader::IFDDataEntry *a6,
        size_t Size,
        const unsigned __int8 *Src)
{
  unsigned int v9; // r15d
  __int16 v10; // di
  int *v12; // r9
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v14; // ebx
  int v15; // ebx
  unsigned int *v16; // r13
  char v17; // r8
  char v18; // cl
  char v19; // al
  char v20; // r8
  char v21; // cl
  char v22; // al
  char v23; // r10
  char v24; // dl
  char v25; // r8
  char v26; // al
  char v27; // al
  unsigned int i; // edi
  void ***v29; // rcx
  struct CallStackContext *v30; // rax
  int v31; // r8d
  __int64 v32; // rcx
  char v33; // al
  char v34; // r11
  char v35; // cl
  char v36; // r8
  char v37; // al
  char v38; // cl
  void ***v39; // rcx
  int v41; // [rsp+20h] [rbp-88h]
  _BYTE v42[2]; // [rsp+30h] [rbp-78h] BYREF
  __int16 v43; // [rsp+32h] [rbp-76h]
  __int64 v44; // [rsp+38h] [rbp-70h]
  _BYTE v45[32]; // [rsp+40h] [rbp-68h] BYREF
  _QWORD v46[2]; // [rsp+60h] [rbp-48h] BYREF
  unsigned int v47; // [rsp+70h] [rbp-38h]

  v44 = -2;
  v9 = a3;
  v10 = a2;
  v43 = a2;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v42, "CRawImageReader::CreateOneIFDEntry", 1386);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 34) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v14 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 34) + 296LL))(*((_QWORD *)this + 34));
    *((_OWORD *)ThreadRelativeContext + 125) = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _QWORD *))(**((_QWORD **)this + 34) + 280LL))(
                                                            *((_QWORD *)this + 34),
                                                            v46);
    *((_DWORD *)ThreadRelativeContext + 504) = v14;
    v10 = v43;
  }
  v15 = 0;
  v16 = (unsigned int *)((char *)this + 56);
  CTraceBase::CAutoTrace::CAutoTrace(
    (CTraceBase::CAutoTrace *)v45,
    (struct CTraceBase *)(((unsigned __int64)this + 56) & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64)),
    "CRawImageReader::CreateOneIFDEntry",
    v12,
    v41);
  v17 = *((_BYTE *)this + 107);
  v18 = v10;
  v19 = HIBYTE(v10);
  if ( v17 )
    v19 = v10;
  *((_BYTE *)a6 + 1) = v19;
  if ( v17 )
    v18 = HIBYTE(v10);
  *(_BYTE *)a6 = v18;
  v20 = *((_BYTE *)this + 107);
  v21 = v9;
  v22 = BYTE1(v9);
  if ( v20 )
    v22 = v9;
  *((_BYTE *)a6 + 3) = v22;
  if ( v20 )
    v21 = BYTE1(v9);
  *((_BYTE *)a6 + 2) = v21;
  v23 = *((_BYTE *)this + 107);
  v24 = BYTE2(a4);
  v25 = a4;
  v26 = BYTE1(a4);
  if ( v23 )
    v26 = BYTE2(a4);
  *((_BYTE *)a6 + 5) = v26;
  v27 = HIBYTE(a4);
  if ( v23 )
    v27 = a4;
  *((_BYTE *)a6 + 7) = v27;
  if ( v23 )
    v24 = BYTE1(a4);
  *((_BYTE *)a6 + 6) = v24;
  if ( v23 )
    v25 = HIBYTE(a4);
  *((_BYTE *)a6 + 4) = v25;
  if ( Src )
  {
    if ( (unsigned int)Size <= 4 )
    {
      memmove((char *)a6 + 8, Src, (unsigned int)Size);
    }
    else
    {
      for ( i = 0; i < (unsigned int)Size; ++i )
      {
        v46[0] = a6;
        v46[1] = Src;
        v47 = i;
        v15 = MF::ExceptionBoundary__lambda_0d23f471152425a12633981a0454cd02___(v46);
        if ( v15 < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              124,
              &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
              *v16,
              v15);
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
            if ( *((_DWORD *)v30 + 499) != v15 )
            {
              v31 = 1405;
              goto LABEL_64;
            }
          }
          break;
        }
      }
    }
  }
  else
  {
    v32 = v9 < 0xE ? v9 : 0;
    if ( *((_DWORD *)qword_1800D53E8 + v32) <= 4u && a4 == 1 )
    {
      if ( *((_DWORD *)qword_1800D53E8 + v32) == 1 )
      {
        v33 = a5;
      }
      else
      {
        v34 = *((_BYTE *)this + 107);
        if ( *((_DWORD *)qword_1800D53E8 + v32) == 2 )
        {
          v35 = BYTE1(a5);
          if ( v34 )
            v35 = a5;
          *((_BYTE *)a6 + 9) = v35;
          v33 = a5;
          if ( v34 )
            v33 = BYTE1(a5);
        }
        else
        {
          v36 = BYTE2(a5);
          v37 = BYTE1(a5);
          if ( v34 )
            v37 = BYTE2(a5);
          *((_BYTE *)a6 + 9) = v37;
          v38 = HIBYTE(a5);
          if ( v34 )
            v38 = a5;
          *((_BYTE *)a6 + 11) = v38;
          if ( v34 )
            v36 = BYTE1(a5);
          *((_BYTE *)a6 + 10) = v36;
          v33 = a5;
          if ( v34 )
            v33 = HIBYTE(a5);
        }
      }
      *((_BYTE *)a6 + 8) = v33;
    }
    else
    {
      v15 = -2147418113;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          125,
          &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
          *v16,
          -2147418113);
      }
      v39 = (void ***)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v39 = &off_1800E5190;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
      }
      if ( *((_BYTE *)v39 + 8) )
      {
        v30 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v39);
        if ( *((_DWORD *)v30 + 499) != -2147418113 )
        {
          v31 = 1417;
LABEL_64:
          CallStackContext::TraceFailure(v30, "CRawImageReader::CreateOneIFDEntry", v31, v15);
        }
      }
    }
  }
  CTraceBase::CAutoTrace::~CAutoTrace((CTraceBase::CAutoTrace *)v45);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v42);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x1800a713c  mov     r11, rsp
0x1800a713f  push    rdi
0x1800a7140  push    r12
0x1800a7142  push    r13
0x1800a7144  push    r14
0x1800a7146  push    r15
0x1800a7148  sub     rsp, 80h
0x1800a714f  mov     qword ptr [r11-70h], 0FFFFFFFFFFFFFFFEh
0x1800a7157  mov     [r11+10h], rbx
0x1800a715b  mov     [r11+18h], rbp
0x1800a715f  mov     [r11+20h], rsi
0x1800a7163  mov     rax, cs:__security_cookie
0x1800a716a  xor     rax, rsp
0x1800a716d  mov     [rsp+0A8h+var_30], rax
0x1800a7172  mov     r12d, r9d
0x1800a7175  movzx   r15d, r8w
0x1800a7179  movzx   edi, dx
0x1800a717c  mov     [rsp+0A8h+var_76], dx
0x1800a7181  mov     rbp, rcx
0x1800a7184  mov     rsi, [rsp+0A8h+arg_28]
0x1800a718c  mov     r14, [rsp+0A8h+Src]
0x1800a7194  mov     r8d, 56Ah; int
0x1800a719a  lea     rdx, aCrawimagereade_23; "CRawImageReader::CreateOneIFDEntry"
0x1800a71a1  lea     rcx, [r11-78h]; this
0x1800a71a5  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800a71aa  nop
0x1800a71ab  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800a71b2  cmp     byte ptr [rcx+8], 0
0x1800a71b6  jz      short loc_1800A7213
0x1800a71b8  cmp     qword ptr [rbp+110h], 0
0x1800a71c0  jz      short loc_1800A7213
0x1800a71c2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a71c7  mov     rdi, rax
0x1800a71ca  mov     rcx, [rbp+110h]
0x1800a71d1  mov     rdx, [rcx]
0x1800a71d4  mov     rax, [rdx+128h]
0x1800a71db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a71e0  mov     ebx, eax
0x1800a71e2  mov     rcx, [rbp+110h]
0x1800a71e9  mov     rdx, [rcx]
0x1800a71ec  mov     rax, [rdx+118h]
0x1800a71f3  lea     rdx, [rsp+0A8h+var_48]
0x1800a71f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a71fd  movups  xmm0, xmmword ptr [rax]
0x1800a7200  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x1800a7208  mov     [rdi+7E0h], ebx
0x1800a720e  movzx   edi, [rsp+0A8h+var_76]
0x1800a7213  xor     ebx, ebx
0x1800a7215  lea     r13, [rbp+38h]
0x1800a7219  mov     rax, rbp
0x1800a721c  neg     rax
0x1800a721f  sbb     rdx, rdx
0x1800a7222  and     rdx, r13; struct CTraceBase *
0x1800a7225  lea     r8, aCrawimagereade_23; "CRawImageReader::CreateOneIFDEntry"
0x1800a722c  lea     rcx, [rsp+0A8h+var_68]; this
0x1800a7231  call    ??0CAutoTrace@CTraceBase@@QEAA@PEAV1@PEBDPEAJH@Z; CTraceBase::CAutoTrace::CAutoTrace(CTraceBase *,char const *,long *,int)
0x1800a7236  nop
0x1800a7237  mov     r8b, [rbp+6Bh]
0x1800a723b  movzx   eax, di
0x1800a723e  shr     ax, 8
0x1800a7242  movzx   edx, al
0x1800a7245  movzx   ecx, dil
0x1800a7249  mov     eax, edx
0x1800a724b  test    r8b, r8b
0x1800a724e  cmovnz  eax, ecx
0x1800a7251  mov     [rsi+1], al
0x1800a7254  cmovnz  ecx, edx
0x1800a7257  mov     [rsi], cl
0x1800a7259  mov     r8b, [rbp+6Bh]
0x1800a725d  movzx   eax, r15w
0x1800a7261  shr     ax, 8
0x1800a7265  movzx   edx, al
0x1800a7268  movzx   ecx, r15b
0x1800a726c  mov     eax, edx
0x1800a726e  test    r8b, r8b
0x1800a7271  cmovnz  eax, ecx
0x1800a7274  mov     [rsi+3], al
0x1800a7277  cmovnz  ecx, edx
0x1800a727a  mov     [rsi+2], cl
0x1800a727d  mov     r10b, [rbp+6Bh]
0x1800a7281  mov     r9d, r12d
0x1800a7284  shr     r9d, 18h
0x1800a7288  mov     eax, r12d
0x1800a728b  shr     eax, 10h
0x1800a728e  movzx   edx, al
0x1800a7291  mov     eax, r12d
0x1800a7294  shr     eax, 8
0x1800a7297  movzx   ecx, al
0x1800a729a  movzx   r8d, r12b
0x1800a729e  mov     eax, ecx
0x1800a72a0  test    r10b, r10b
0x1800a72a3  cmovnz  eax, edx
0x1800a72a6  mov     [rsi+5], al
0x1800a72a9  mov     eax, r9d
0x1800a72ac  cmovnz  eax, r8d
0x1800a72b0  mov     [rsi+7], al
0x1800a72b3  cmovnz  edx, ecx
0x1800a72b6  mov     [rsi+6], dl
0x1800a72b9  cmovnz  r8d, r9d
0x1800a72bd  mov     [rsi+4], r8b
0x1800a72c1  test    r14, r14
0x1800a72c4  jz      loc_1800A7396
0x1800a72ca  mov     ebp, dword ptr [rsp+0A8h+Size]
0x1800a72d1  cmp     ebp, 4
0x1800a72d4  jbe     loc_1800A7382
0x1800a72da  xor     edi, edi
0x1800a72dc  cmp     edi, ebp
0x1800a72de  jnb     loc_1800A74D2
0x1800a72e4  mov     [rsp+0A8h+var_48], rsi
0x1800a72e9  mov     [rsp+0A8h+var_40], r14
0x1800a72ee  mov     [rsp+0A8h+var_38], edi
0x1800a72f2  lea     rcx, [rsp+0A8h+var_48]
0x1800a72f7  call    MF__ExceptionBoundary__lambda_0d23f471152425a12633981a0454cd02___
0x1800a72fc  mov     ebx, eax
0x1800a72fe  test    eax, eax
0x1800a7300  js      short loc_1800A7306
0x1800a7302  inc     edi
0x1800a7304  jmp     short loc_1800A72DC
0x1800a7306  lea     rax, WPP_GLOBAL_Control
0x1800a730d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a7314  cmp     rcx, rax
0x1800a7317  jz      short loc_1800A7342
0x1800a7319  test    byte ptr [rcx+1Ch], 1
0x1800a731d  jz      short loc_1800A7342
0x1800a731f  cmp     byte ptr [rcx+19h], 4
0x1800a7323  jb      short loc_1800A7342
0x1800a7325  mov     edx, 7Ch ; '|'
0x1800a732a  mov     [rsp+0A8h+var_88], ebx
0x1800a732e  mov     r9d, [r13+0]
0x1800a7332  lea     r8, WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids
0x1800a7339  mov     rcx, [rcx+10h]
0x1800a733d  call    WPP_SF_Dd
0x1800a7342  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a7349  test    rcx, rcx
0x1800a734c  jnz     short loc_1800A735C
0x1800a734e  lea     rcx, off_1800E5190; this
0x1800a7355  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a735c  cmp     byte ptr [rcx+8], 0
0x1800a7360  jz      loc_1800A74D2
0x1800a7366  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a736b  cmp     [rax+7CCh], ebx
0x1800a7371  jz      loc_1800A74D2
0x1800a7377  mov     r8d, 57Dh
0x1800a737d  jmp     loc_1800A74BF
0x1800a7382  mov     r8, rbp; Size
0x1800a7385  lea     rcx, [rsi+8]; void *
0x1800a7389  mov     rdx, r14; Src
0x1800a738c  call    memmove
0x1800a7391  jmp     loc_1800A74D2
0x1800a7396  mov     ecx, r15d
0x1800a7399  cmp     r15d, 0Eh
0x1800a739d  sbb     eax, eax
0x1800a739f  and     ecx, eax
0x1800a73a1  lea     rax, qword_1800D53E8
0x1800a73a8  cmp     dword ptr [rax+rcx*4], 4
0x1800a73ac  ja      loc_1800A744B
0x1800a73b2  cmp     r12d, 1
0x1800a73b6  jnz     loc_1800A744B
0x1800a73bc  cmp     [rax+rcx*4], r12d
0x1800a73c0  jnz     short loc_1800A73CB
0x1800a73c2  mov     al, byte ptr [rsp+0A8h+arg_20]
0x1800a73c9  jmp     short loc_1800A73FE
0x1800a73cb  mov     r10d, [rsp+0A8h+arg_20]
0x1800a73d3  mov     r11b, [rbp+6Bh]
0x1800a73d7  cmp     dword ptr [rax+rcx*4], 2
0x1800a73db  jnz     short loc_1800A7406
0x1800a73dd  movzx   eax, r10w
0x1800a73e1  shr     ax, 8
0x1800a73e5  movzx   edx, al
0x1800a73e8  mov     ecx, edx
0x1800a73ea  movzx   eax, r10b
0x1800a73ee  test    r11b, r11b
0x1800a73f1  cmovnz  ecx, eax
0x1800a73f4  mov     [rsi+9], cl
0x1800a73f7  movzx   eax, r10b
0x1800a73fb  cmovnz  eax, edx
0x1800a73fe  mov     [rsi+8], al
0x1800a7401  jmp     loc_1800A74D2
0x1800a7406  mov     r9d, r10d
0x1800a7409  shr     r9d, 18h
0x1800a740d  mov     eax, r10d
0x1800a7410  shr     eax, 10h
0x1800a7413  movzx   r8d, al
0x1800a7417  mov     eax, r10d
0x1800a741a  shr     eax, 8
0x1800a741d  movzx   edx, al
0x1800a7420  mov     eax, edx
0x1800a7422  test    r11b, r11b
0x1800a7425  cmovnz  eax, r8d
0x1800a7429  mov     [rsi+9], al
0x1800a742c  mov     ecx, r9d
0x1800a742f  movzx   eax, r10b
0x1800a7433  cmovnz  ecx, eax
0x1800a7436  mov     [rsi+0Bh], cl
0x1800a7439  cmovnz  r8d, edx
0x1800a743d  mov     [rsi+0Ah], r8b
0x1800a7441  movzx   eax, r10b
0x1800a7445  cmovnz  eax, r9d
0x1800a7449  jmp     short loc_1800A73FE
0x1800a744b  mov     ebx, 8000FFFFh
0x1800a7450  lea     rax, WPP_GLOBAL_Control
0x1800a7457  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a745e  cmp     rcx, rax
0x1800a7461  jz      short loc_1800A748C
0x1800a7463  test    byte ptr [rcx+1Ch], 1
0x1800a7467  jz      short loc_1800A748C
0x1800a7469  cmp     byte ptr [rcx+19h], 4
0x1800a746d  jb      short loc_1800A748C
0x1800a746f  mov     edx, 7Dh ; '}'
0x1800a7474  mov     [rsp+0A8h+var_88], ebx
0x1800a7478  mov     r9d, [r13+0]
0x1800a747c  lea     r8, WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids
0x1800a7483  mov     rcx, [rcx+10h]
0x1800a7487  call    WPP_SF_Dd
0x1800a748c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a7493  test    rcx, rcx
0x1800a7496  jnz     short loc_1800A74A6
0x1800a7498  lea     rcx, off_1800E5190; this
0x1800a749f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a74a6  cmp     byte ptr [rcx+8], 0
0x1800a74aa  jz      short loc_1800A74D2
0x1800a74ac  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a74b1  cmp     [rax+7CCh], ebx
0x1800a74b7  jz      short loc_1800A74D2
0x1800a74b9  mov     r8d, 589h; int
0x1800a74bf  mov     r9d, ebx; int
0x1800a74c2  lea     rdx, aCrawimagereade_23; "CRawImageReader::CreateOneIFDEntry"
0x1800a74c9  mov     rcx, rax; this
0x1800a74cc  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a74d1  nop
0x1800a74d2  lea     rcx, [rsp+0A8h+var_68]; this
0x1800a74d7  call    ??1CAutoTrace@CTraceBase@@QEAA@XZ; CTraceBase::CAutoTrace::~CAutoTrace(void)
0x1800a74dc  nop
0x1800a74dd  lea     rcx, [rsp+0A8h+var_78]; this
0x1800a74e2  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800a74e7  mov     eax, ebx
0x1800a74e9  mov     rcx, [rsp+0A8h+var_30]
0x1800a74ee  xor     rcx, rsp; StackCookie
0x1800a74f1  call    __security_check_cookie
0x1800a74f6  lea     r11, [rsp+0A8h+var_28]
0x1800a74fe  mov     rbx, [r11+38h]
0x1800a7502  mov     rbp, [r11+40h]
0x1800a7506  mov     rsi, [r11+48h]
0x1800a750a  mov     rsp, r11
0x1800a750d  pop     r15
0x1800a750f  pop     r14
0x1800a7511  pop     r13
0x1800a7513  pop     r12
0x1800a7515  pop     rdi
0x1800a7516  retn
```
