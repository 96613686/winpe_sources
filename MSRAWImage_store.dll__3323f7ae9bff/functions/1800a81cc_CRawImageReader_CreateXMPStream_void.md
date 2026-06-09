# CRawImageReader::CreateXMPStream(void)

- ea: `0x1800a81cc`
- end: `0x1800a857f`
- name: `?CreateXMPStream@CRawImageReader@@AEAAJXZ`
- size: `947`
- prototype: `__int64 __fastcall(CRawImageReader *__hidden this)`
- caller_count: `2`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x1800a8588`
- `0x1800aba40`

## callees

- `0x180002040`
- `0x1800020a0`
- `0x1800023a0`
- `0x180002590`
- `0x180002a00`
- `0x18009b9e4`
- `0x18009c44c`
- `0x18009e8b8`
- `0x1800a34f8`
- `0x1800a81cc`
- `0x1800afee4`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800a8338`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800a8338`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800a83d1`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800a83d1`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800a8300`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800a8300`

## string_xrefs

- `0x1800a8202`: `CRawImageReader::CreateXMPStream`
- `0x1800a8288`: `CRawImageReader::CreateXMPStream`
- `0x1800a83bf`: `CRawImageReader::CreateXMPStream`
- `0x1800a8532`: `CRawImageReader::CreateXMPStream`

## pseudocode

```c
__int64 __fastcall CRawImageReader::CreateXMPStream(CRawImageReader *this)
{
  int *v2; // r9
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v4; // ebx
  HRESULT StreamOnHGlobal; // ebx
  unsigned int *v6; // rdi
  __int64 v7; // r8
  HGLOBAL v8; // rbp
  _QWORD *v9; // r14
  void ***v10; // rcx
  struct CallStackContext *v11; // rax
  void ***v12; // rcx
  struct CallStackContext *v13; // rax
  int v14; // r8d
  __int64 v15; // rcx
  void ***v16; // rcx
  int v18; // [rsp+20h] [rbp-78h]
  _BYTE v19[4]; // [rsp+30h] [rbp-68h] BYREF
  int v20; // [rsp+34h] [rbp-64h] BYREF
  __int64 v21; // [rsp+38h] [rbp-60h]
  _BYTE v22[32]; // [rsp+40h] [rbp-58h] BYREF
  __int64 v23; // [rsp+60h] [rbp-38h] BYREF

  v21 = -2;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v19, "CRawImageReader::CreateXMPStream", 1041);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 34) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v4 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 34) + 296LL))(*((_QWORD *)this + 34));
    *((_OWORD *)ThreadRelativeContext + 125) = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 34) + 280LL))(
                                                            *((_QWORD *)this + 34),
                                                            &v23);
    *((_DWORD *)ThreadRelativeContext + 504) = v4;
  }
  StreamOnHGlobal = 0;
  v6 = (unsigned int *)((char *)this + 56);
  CTraceBase::CAutoTrace::CAutoTrace(
    (CTraceBase::CAutoTrace *)v22,
    (struct CTraceBase *)(((unsigned __int64)this + 56) & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64)),
    "CRawImageReader::CreateXMPStream",
    v2,
    v18);
  if ( !*((_BYTE *)this + 106) )
  {
    *((_BYTE *)this + 106) = 1;
    v7 = *(unsigned int *)(*((_QWORD *)this + 18) + 628LL);
    if ( (_DWORD)v7 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_DD(*((_QWORD *)WPP_GLOBAL_Control + 2), 95, v7, *v6, v7);
      }
      v8 = GlobalAlloc(0, *(unsigned int *)(*((_QWORD *)this + 18) + 628LL));
      if ( !v8 )
      {
        StreamOnHGlobal = -2147024882;
        goto LABEL_44;
      }
      v9 = (_QWORD *)((char *)this + 240);
      Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease((char *)this + 240);
      StreamOnHGlobal = CreateStreamOnHGlobal(v8, 1, (LPSTREAM *)this + 30);
      if ( StreamOnHGlobal < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            96,
            &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
            *v6,
            StreamOnHGlobal);
        }
        v10 = (void ***)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v10 = &off_1800E5190;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
        }
        if ( *((_BYTE *)v10 + 8) )
        {
          v11 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v10);
          if ( *((_DWORD *)v11 + 499) != StreamOnHGlobal )
            CallStackContext::TraceFailure(v11, "CRawImageReader::CreateXMPStream", 1054, StreamOnHGlobal);
        }
        GlobalFree(v8);
        goto LABEL_44;
      }
      v20 = 0;
      StreamOnHGlobal = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, int *))(*(_QWORD *)*v9 + 32LL))(
                          *v9,
                          *(_QWORD *)(*((_QWORD *)this + 18) + 632LL),
                          *(unsigned int *)(*((_QWORD *)this + 18) + 628LL),
                          &v20);
      if ( StreamOnHGlobal >= 0 )
      {
        v15 = *v9;
        v23 = 0;
        StreamOnHGlobal = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v15 + 40LL))(
                            v15,
                            0,
                            0,
                            0);
        if ( StreamOnHGlobal < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              98,
              &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
              *v6,
              StreamOnHGlobal);
          }
          v16 = (void ***)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v16 = &off_1800E5190;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
          }
          if ( *((_BYTE *)v16 + 8) )
          {
            v13 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v16);
            if ( *((_DWORD *)v13 + 499) != StreamOnHGlobal )
            {
              v14 = 1060;
              goto LABEL_43;
            }
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
            97,
            &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
            *v6,
            StreamOnHGlobal);
        }
        v12 = (void ***)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v12 = &off_1800E5190;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
        }
        if ( *((_BYTE *)v12 + 8) )
        {
          v13 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v12);
          if ( *((_DWORD *)v13 + 499) != StreamOnHGlobal )
          {
            v14 = 1059;
LABEL_43:
            CallStackContext::TraceFailure(v13, "CRawImageReader::CreateXMPStream", v14, StreamOnHGlobal);
          }
        }
      }
    }
  }
LABEL_44:
  CTraceBase::CAutoTrace::~CAutoTrace((CTraceBase::CAutoTrace *)v22);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v19);
  return (unsigned int)StreamOnHGlobal;
}

```

## disassembly

```asm
0x1800a81cc  mov     r11, rsp
0x1800a81cf  push    rsi
0x1800a81d0  push    rdi
0x1800a81d1  push    r14
0x1800a81d3  sub     rsp, 80h
0x1800a81da  mov     qword ptr [r11-60h], 0FFFFFFFFFFFFFFFEh
0x1800a81e2  mov     [r11+10h], rbx
0x1800a81e6  mov     [r11+18h], rbp
0x1800a81ea  mov     rax, cs:__security_cookie
0x1800a81f1  xor     rax, rsp
0x1800a81f4  mov     [rsp+98h+var_28], rax
0x1800a81f9  mov     rsi, rcx
0x1800a81fc  mov     r8d, 411h; int
0x1800a8202  lea     rdx, aCrawimagereade_13; "CRawImageReader::CreateXMPStream"
0x1800a8209  lea     rcx, [r11-68h]; this
0x1800a820d  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800a8212  nop
0x1800a8213  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800a821a  cmp     byte ptr [rcx+8], 0
0x1800a821e  jz      short loc_1800A8276
0x1800a8220  cmp     qword ptr [rsi+110h], 0
0x1800a8228  jz      short loc_1800A8276
0x1800a822a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a822f  mov     rdi, rax
0x1800a8232  mov     rcx, [rsi+110h]
0x1800a8239  mov     rdx, [rcx]
0x1800a823c  mov     rax, [rdx+128h]
0x1800a8243  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a8248  mov     ebx, eax
0x1800a824a  mov     rcx, [rsi+110h]
0x1800a8251  mov     rdx, [rcx]
0x1800a8254  mov     rax, [rdx+118h]
0x1800a825b  lea     rdx, [rsp+98h+var_38]
0x1800a8260  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a8265  movups  xmm0, xmmword ptr [rax]
0x1800a8268  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x1800a8270  mov     [rdi+7E0h], ebx
0x1800a8276  xor     ebx, ebx
0x1800a8278  lea     rdi, [rsi+38h]
0x1800a827c  mov     rax, rsi
0x1800a827f  neg     rax
0x1800a8282  sbb     rdx, rdx
0x1800a8285  and     rdx, rdi; struct CTraceBase *
0x1800a8288  lea     r8, aCrawimagereade_13; "CRawImageReader::CreateXMPStream"
0x1800a828f  lea     rcx, [rsp+98h+var_58]; this
0x1800a8294  call    ??0CAutoTrace@CTraceBase@@QEAA@PEAV1@PEBDPEAJH@Z; CTraceBase::CAutoTrace::CAutoTrace(CTraceBase *,char const *,long *,int)
0x1800a8299  nop
0x1800a829a  cmp     [rsi+6Ah], bl
0x1800a829d  jnz     loc_1800A8542
0x1800a82a3  mov     byte ptr [rsi+6Ah], 1
0x1800a82a7  mov     rax, [rsi+90h]
0x1800a82ae  mov     r8d, [rax+274h]
0x1800a82b5  test    r8d, r8d
0x1800a82b8  jz      loc_1800A8542
0x1800a82be  lea     rax, WPP_GLOBAL_Control
0x1800a82c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a82cc  cmp     rcx, rax
0x1800a82cf  jz      short loc_1800A82F1
0x1800a82d1  test    byte ptr [rcx+1Ch], 1
0x1800a82d5  jz      short loc_1800A82F1
0x1800a82d7  cmp     byte ptr [rcx+19h], 4
0x1800a82db  jb      short loc_1800A82F1
0x1800a82dd  lea     edx, [rbx+5Fh]
0x1800a82e0  mov     [rsp+98h+var_78], r8d
0x1800a82e5  mov     r9d, [rdi]
0x1800a82e8  mov     rcx, [rcx+10h]
0x1800a82ec  call    WPP_SF_DD
0x1800a82f1  mov     rax, [rsi+90h]
0x1800a82f8  mov     edx, [rax+274h]; dwBytes
0x1800a82fe  xor     ecx, ecx; uFlags
0x1800a8300  call    cs:__imp_GlobalAlloc
0x1800a8307  nop     dword ptr [rax+rax+00h]
0x1800a830c  mov     rbp, rax
0x1800a830f  test    rax, rax
0x1800a8312  jnz     short loc_1800A831E
0x1800a8314  mov     ebx, 8007000Eh
0x1800a8319  jmp     loc_1800A8542
0x1800a831e  lea     r14, [rsi+0F0h]
0x1800a8325  mov     rcx, r14
0x1800a8328  call    ?InternalRelease@?$ComPtr@UIWICMetadataBlockReader@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease(void)
0x1800a832d  mov     r8, r14; ppstm
0x1800a8330  mov     edx, 1; fDeleteOnRelease
0x1800a8335  mov     rcx, rbp; hGlobal
0x1800a8338  call    cs:__imp_CreateStreamOnHGlobal
0x1800a833f  nop     dword ptr [rax+rax+00h]
0x1800a8344  mov     ebx, eax
0x1800a8346  test    eax, eax
0x1800a8348  jns     loc_1800A83E2
0x1800a834e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a8355  lea     rax, WPP_GLOBAL_Control
0x1800a835c  cmp     rcx, rax
0x1800a835f  jz      short loc_1800A8389
0x1800a8361  test    byte ptr [rcx+1Ch], 1
0x1800a8365  jz      short loc_1800A8389
0x1800a8367  cmp     byte ptr [rcx+19h], 4
0x1800a836b  jb      short loc_1800A8389
0x1800a836d  mov     edx, 60h ; '`'
0x1800a8372  mov     [rsp+98h+var_78], ebx
0x1800a8376  mov     r9d, [rdi]
0x1800a8379  lea     r8, WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids
0x1800a8380  mov     rcx, [rcx+10h]
0x1800a8384  call    WPP_SF_Dd
0x1800a8389  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a8390  test    rcx, rcx
0x1800a8393  jnz     short loc_1800A83A3
0x1800a8395  lea     rcx, off_1800E5190; this
0x1800a839c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a83a3  cmp     byte ptr [rcx+8], 0
0x1800a83a7  jz      short loc_1800A83CE
0x1800a83a9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a83ae  cmp     [rax+7CCh], ebx
0x1800a83b4  jz      short loc_1800A83CE
0x1800a83b6  mov     r9d, ebx; int
0x1800a83b9  mov     r8d, 41Eh; int
0x1800a83bf  lea     rdx, aCrawimagereade_13; "CRawImageReader::CreateXMPStream"
0x1800a83c6  mov     rcx, rax; this
0x1800a83c9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a83ce  mov     rcx, rbp; hMem
0x1800a83d1  call    cs:__imp_GlobalFree
0x1800a83d8  nop     dword ptr [rax+rax+00h]
0x1800a83dd  jmp     loc_1800A8542
0x1800a83e2  mov     [rsp+98h+var_64], 0
0x1800a83ea  mov     rcx, [r14]
0x1800a83ed  mov     rdx, [rsi+90h]
0x1800a83f4  mov     rax, [rcx]
0x1800a83f7  lea     r9, [rsp+98h+var_64]
0x1800a83fc  mov     r8d, [rdx+274h]
0x1800a8403  mov     rdx, [rdx+278h]
0x1800a840a  mov     rax, [rax+20h]
0x1800a840e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a8413  mov     ebx, eax
0x1800a8415  test    eax, eax
0x1800a8417  jns     short loc_1800A8494
0x1800a8419  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a8420  lea     rax, WPP_GLOBAL_Control
0x1800a8427  cmp     rcx, rax
0x1800a842a  jz      short loc_1800A8454
0x1800a842c  test    byte ptr [rcx+1Ch], 1
0x1800a8430  jz      short loc_1800A8454
0x1800a8432  cmp     byte ptr [rcx+19h], 4
0x1800a8436  jb      short loc_1800A8454
0x1800a8438  mov     edx, 61h ; 'a'
0x1800a843d  mov     [rsp+98h+var_78], ebx
0x1800a8441  mov     r9d, [rdi]
0x1800a8444  lea     r8, WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids
0x1800a844b  mov     rcx, [rcx+10h]
0x1800a844f  call    WPP_SF_Dd
0x1800a8454  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a845b  test    rcx, rcx
0x1800a845e  jnz     short loc_1800A846E
0x1800a8460  lea     rcx, off_1800E5190; this
0x1800a8467  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a846e  cmp     byte ptr [rcx+8], 0
0x1800a8472  jz      loc_1800A8542
0x1800a8478  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a847d  cmp     [rax+7CCh], ebx
0x1800a8483  jz      loc_1800A8542
0x1800a8489  mov     r8d, 423h
0x1800a848f  jmp     loc_1800A852F
0x1800a8494  mov     rcx, [r14]
0x1800a8497  mov     [rsp+98h+var_38], 0
0x1800a84a0  mov     rax, [rcx]
0x1800a84a3  xor     r9d, r9d
0x1800a84a6  xor     r8d, r8d
0x1800a84a9  mov     rdx, [rsp+98h+var_38]
0x1800a84ae  mov     rax, [rax+28h]
0x1800a84b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a84b7  mov     ebx, eax
0x1800a84b9  test    eax, eax
0x1800a84bb  jns     loc_1800A8542
0x1800a84c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a84c8  lea     rax, WPP_GLOBAL_Control
0x1800a84cf  cmp     rcx, rax
0x1800a84d2  jz      short loc_1800A84FC
0x1800a84d4  test    byte ptr [rcx+1Ch], 1
0x1800a84d8  jz      short loc_1800A84FC
0x1800a84da  cmp     byte ptr [rcx+19h], 4
0x1800a84de  jb      short loc_1800A84FC
0x1800a84e0  mov     edx, 62h ; 'b'
0x1800a84e5  mov     [rsp+98h+var_78], ebx
0x1800a84e9  mov     r9d, [rdi]
0x1800a84ec  lea     r8, WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids
0x1800a84f3  mov     rcx, [rcx+10h]
0x1800a84f7  call    WPP_SF_Dd
0x1800a84fc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a8503  test    rcx, rcx
0x1800a8506  jnz     short loc_1800A8516
0x1800a8508  lea     rcx, off_1800E5190; this
0x1800a850f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a8516  cmp     byte ptr [rcx+8], 0
0x1800a851a  jz      short loc_1800A8542
0x1800a851c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a8521  cmp     [rax+7CCh], ebx
0x1800a8527  jz      short loc_1800A8542
0x1800a8529  mov     r8d, 424h; int
0x1800a852f  mov     r9d, ebx; int
0x1800a8532  lea     rdx, aCrawimagereade_13; "CRawImageReader::CreateXMPStream"
0x1800a8539  mov     rcx, rax; this
0x1800a853c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a8541  nop
0x1800a8542  lea     rcx, [rsp+98h+var_58]; this
0x1800a8547  call    ??1CAutoTrace@CTraceBase@@QEAA@XZ; CTraceBase::CAutoTrace::~CAutoTrace(void)
0x1800a854c  nop
0x1800a854d  lea     rcx, [rsp+98h+var_68]; this
0x1800a8552  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800a8557  mov     eax, ebx
0x1800a8559  mov     rcx, [rsp+98h+var_28]
0x1800a855e  xor     rcx, rsp; StackCookie
0x1800a8561  call    __security_check_cookie
0x1800a8566  lea     r11, [rsp+98h+var_18]
0x1800a856e  mov     rbx, [r11+28h]
0x1800a8572  mov     rbp, [r11+30h]
0x1800a8576  mov     rsp, r11
0x1800a8579  pop     r14
0x1800a857b  pop     rdi
0x1800a857c  pop     rsi
0x1800a857d  retn
```
