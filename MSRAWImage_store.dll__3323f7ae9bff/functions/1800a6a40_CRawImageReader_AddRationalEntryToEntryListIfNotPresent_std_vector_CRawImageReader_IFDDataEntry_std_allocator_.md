# CRawImageReader::AddRationalEntryToEntryListIfNotPresent(std::vector<CRawImageReader::IFDDataEntry,std::allocator<CRawImageReader::IFDDataEntry>> *,uint *,ushort,float)

- ea: `0x1800a6a40`
- end: `0x1800a6ca5`
- name: `?AddRationalEntryToEntryListIfNotPresent@CRawImageReader@@AEAAJPEAV?$vector@UIFDDataEntry@CRawImageReader@@V?$allocator@UIFDDataEntry@CRawImageReader@@@std@@@std@@PEAIGM@Z`
- size: `613`
- prototype: `__int64 __usercall@<rax>(CRawImageReader *this@<rcx>, int)`
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x1800a5b90`

## callees

- `0x180002040`
- `0x1800020a0`
- `0x1800023a0`
- `0x180002590`
- `0x180002a00`
- `0x18009b9e4`
- `0x18009e8b8`
- `0x1800a34f8`
- `0x1800a6784`
- `0x1800a6a40`
- `0x1800ac564`
- `0x1800adc5c`
- `0x1800b4010`

## string_xrefs

- `0x1800a6a82`: `CRawImageReader::AddRationalEntryToEntryListIfNotPresent`
- `0x1800a6b11`: `CRawImageReader::AddRationalEntryToEntryListIfNotPresent`
- `0x1800a6c56`: `CRawImageReader::AddRationalEntryToEntryListIfNotPresent`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CRawImageReader::AddRationalEntryToEntryListIfNotPresent(
        CRawImageReader *this,
        __int64 a2,
        _DWORD *a3,
        unsigned __int16 a4,
        int a5)
{
  int *v9; // r9
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v11; // ebx
  int v12; // ebx
  unsigned int v13; // edx
  unsigned int v14; // ebx
  bool v15; // r8
  CallStackTracing *v16; // rcx
  struct CallStackContext *v17; // rax
  int v19; // [rsp+20h] [rbp-A8h]
  size_t v20; // [rsp+38h] [rbp-90h]
  _BYTE v21[8]; // [rsp+50h] [rbp-78h] BYREF
  __int64 v22; // [rsp+58h] [rbp-70h]
  unsigned __int8 v23[32]; // [rsp+60h] [rbp-68h] BYREF
  unsigned __int8 v24[4]; // [rsp+80h] [rbp-48h] BYREF
  unsigned __int8 v25[12]; // [rsp+84h] [rbp-44h] BYREF

  v22 = -2;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v21,
    "CRawImageReader::AddRationalEntryToEntryListIfNotPresent",
    2037);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 34) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v11 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 34) + 296LL))(*((_QWORD *)this + 34));
    *((_OWORD *)ThreadRelativeContext + 125) = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, unsigned __int8 *))(**((_QWORD **)this + 34) + 280LL))(
                                                            *((_QWORD *)this + 34),
                                                            v24);
    *((_DWORD *)ThreadRelativeContext + 504) = v11;
  }
  v12 = 0;
  CTraceBase::CAutoTrace::CAutoTrace(
    (CTraceBase::CAutoTrace *)v23,
    (struct CTraceBase *)(((unsigned __int64)this + 56) & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64)),
    "CRawImageReader::AddRationalEntryToEntryListIfNotPresent",
    v9,
    v19);
  if ( !(unsigned __int8)CRawImageReader::IsTagInEntryList(this, a2, a4) && *(float *)&a5 > 0.0 )
  {
    if ( *(float *)&a5 >= 1.0 )
    {
      v13 = (int)(float)(*(float *)&a5 * 1000.0);
      v14 = 1000;
    }
    else
    {
      v13 = 1;
      v14 = (int)(float)(1.0 / *(float *)&a5);
    }
    Write4Bytes(v24, v13, *((_BYTE *)this + 107));
    Write4Bytes(v25, v14, v15);
    LODWORD(v20) = 8;
    v12 = CRawImageReader::AddOneIFDEntryToEntryList(this, a2, a3, a4, 5u, 1u, 0, v20, v24);
    if ( v12 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          168,
          &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
          *((unsigned int *)this + 14),
          v12);
      }
      v16 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v16 = (CallStackTracing *)&off_1800E5190;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
      }
      if ( *((_BYTE *)v16 + 8) )
      {
        v17 = CallStackTracing::GetThreadRelativeContext(v16);
        if ( *((_DWORD *)v17 + 499) != v12 )
          CallStackContext::TraceFailure(v17, "CRawImageReader::AddRationalEntryToEntryListIfNotPresent", 2059, v12);
      }
    }
  }
  CTraceBase::CAutoTrace::~CAutoTrace((CTraceBase::CAutoTrace *)v23);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v21);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800a6a40  mov     r11, rsp
0x1800a6a43  push    rbp
0x1800a6a44  push    rsi
0x1800a6a45  push    rdi
0x1800a6a46  push    r14
0x1800a6a48  push    r15
0x1800a6a4a  sub     rsp, 0A0h
0x1800a6a51  mov     qword ptr [r11-70h], 0FFFFFFFFFFFFFFFEh
0x1800a6a59  mov     [r11+18h], rbx
0x1800a6a5d  mov     rax, cs:__security_cookie
0x1800a6a64  xor     rax, rsp
0x1800a6a67  mov     [rsp+0C8h+var_38], rax
0x1800a6a6f  movzx   ebp, r9w
0x1800a6a73  mov     r15, r8
0x1800a6a76  mov     r14, rdx
0x1800a6a79  mov     rsi, rcx
0x1800a6a7c  mov     r8d, 7F5h; int
0x1800a6a82  lea     rdx, aCrawimagereade_21; "CRawImageReader::AddRationalEntryToEntr"...
0x1800a6a89  lea     rcx, [r11-78h]; this
0x1800a6a8d  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800a6a92  nop
0x1800a6a93  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800a6a9a  cmp     byte ptr [rcx+8], 0
0x1800a6a9e  jz      short loc_1800A6AFF
0x1800a6aa0  cmp     qword ptr [rsi+110h], 0
0x1800a6aa8  jz      short loc_1800A6AFF
0x1800a6aaa  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a6aaf  mov     rdi, rax
0x1800a6ab2  mov     rdx, [rsi+110h]
0x1800a6ab9  mov     rcx, [rdx]
0x1800a6abc  mov     rax, [rcx+128h]
0x1800a6ac3  mov     rcx, rdx
0x1800a6ac6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6acb  mov     ebx, eax
0x1800a6acd  mov     r8, [rsi+110h]
0x1800a6ad4  mov     rcx, [r8]
0x1800a6ad7  mov     rax, [rcx+118h]
0x1800a6ade  lea     rdx, [rsp+0C8h+var_48]
0x1800a6ae6  mov     rcx, r8
0x1800a6ae9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6aee  movups  xmm0, xmmword ptr [rax]
0x1800a6af1  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x1800a6af9  mov     [rdi+7E0h], ebx
0x1800a6aff  xor     ebx, ebx
0x1800a6b01  lea     rdi, [rsi+38h]
0x1800a6b05  mov     rax, rsi
0x1800a6b08  neg     rax
0x1800a6b0b  sbb     rdx, rdx
0x1800a6b0e  and     rdx, rdi; struct CTraceBase *
0x1800a6b11  lea     r8, aCrawimagereade_21; "CRawImageReader::AddRationalEntryToEntr"...
0x1800a6b18  lea     rcx, [rsp+0C8h+var_68]; this
0x1800a6b1d  call    ??0CAutoTrace@CTraceBase@@QEAA@PEAV1@PEBDPEAJH@Z; CTraceBase::CAutoTrace::CAutoTrace(CTraceBase *,char const *,long *,int)
0x1800a6b22  nop
0x1800a6b23  movzx   r8d, bp
0x1800a6b27  mov     rdx, r14
0x1800a6b2a  mov     rcx, rsi
0x1800a6b2d  call    ?IsTagInEntryList@CRawImageReader@@AEAA_NPEAV?$vector@UIFDDataEntry@CRawImageReader@@V?$allocator@UIFDDataEntry@CRawImageReader@@@std@@@std@@G@Z; CRawImageReader::IsTagInEntryList(std::vector<CRawImageReader::IFDDataEntry> *,ushort)
0x1800a6b32  test    al, al
0x1800a6b34  jnz     loc_1800A6C66
0x1800a6b3a  movss   xmm0, [rsp+0C8h+arg_20]
0x1800a6b43  comiss  xmm0, cs:__real@00000000
0x1800a6b4a  jbe     loc_1800A6C66
0x1800a6b50  movss   xmm1, cs:__real@3f800000
0x1800a6b58  comiss  xmm1, xmm0
0x1800a6b5b  jbe     short loc_1800A6B6B
0x1800a6b5d  lea     edx, [rbx+1]
0x1800a6b60  divss   xmm1, xmm0
0x1800a6b64  cvttss2si rbx, xmm1
0x1800a6b69  jmp     short loc_1800A6B7D
0x1800a6b6b  mulss   xmm0, cs:__real@447a0000
0x1800a6b73  cvttss2si rdx, xmm0; unsigned int
0x1800a6b78  mov     ebx, 3E8h
0x1800a6b7d  mov     r8b, [rsi+6Bh]; bool
0x1800a6b81  lea     rcx, [rsp+0C8h+var_48]; unsigned __int8 *
0x1800a6b89  call    ?Write4Bytes@@YAXPEAEI_N@Z; Write4Bytes(uchar *,uint,bool)
0x1800a6b8e  mov     edx, ebx; unsigned int
0x1800a6b90  lea     rcx, [rsp+0C8h+var_44]; unsigned __int8 *
0x1800a6b98  call    ?Write4Bytes@@YAXPEAEI_N@Z; Write4Bytes(uchar *,uint,bool)
0x1800a6b9d  lea     rax, [rsp+0C8h+var_48]
0x1800a6ba5  mov     [rsp+0C8h+var_88], rax; unsigned __int8 *
0x1800a6baa  mov     dword ptr [rsp+0C8h+var_90], 8; size_t
0x1800a6bb2  mov     [rsp+0C8h+var_98], 0; unsigned int
0x1800a6bba  mov     [rsp+0C8h+var_A0], 1; unsigned int
0x1800a6bc2  mov     [rsp+0C8h+var_A8], 5; __int16
0x1800a6bc9  movzx   r9d, bp
0x1800a6bcd  mov     r8, r15
0x1800a6bd0  mov     rdx, r14
0x1800a6bd3  mov     rcx, rsi; this
0x1800a6bd6  call    ?AddOneIFDEntryToEntryList@CRawImageReader@@AEAAJPEAV?$vector@UIFDDataEntry@CRawImageReader@@V?$allocator@UIFDDataEntry@CRawImageReader@@@std@@@std@@PEAIGGIIIPEBE@Z; CRawImageReader::AddOneIFDEntryToEntryList(std::vector<CRawImageReader::IFDDataEntry> *,uint *,ushort,ushort,uint,uint,uint,uchar const *)
0x1800a6bdb  mov     ebx, eax
0x1800a6bdd  test    eax, eax
0x1800a6bdf  jns     loc_1800A6C66
0x1800a6be5  lea     rax, WPP_GLOBAL_Control
0x1800a6bec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a6bf3  cmp     rcx, rax
0x1800a6bf6  jz      short loc_1800A6C20
0x1800a6bf8  test    byte ptr [rcx+1Ch], 1
0x1800a6bfc  jz      short loc_1800A6C20
0x1800a6bfe  cmp     byte ptr [rcx+19h], 4
0x1800a6c02  jb      short loc_1800A6C20
0x1800a6c04  mov     edx, 0A8h
0x1800a6c09  mov     dword ptr [rsp+0C8h+var_A8], ebx
0x1800a6c0d  mov     r9d, [rdi]
0x1800a6c10  lea     r8, WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids
0x1800a6c17  mov     rcx, [rcx+10h]
0x1800a6c1b  call    WPP_SF_Dd
0x1800a6c20  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a6c27  test    rcx, rcx
0x1800a6c2a  jnz     short loc_1800A6C3A
0x1800a6c2c  lea     rcx, off_1800E5190; this
0x1800a6c33  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a6c3a  cmp     byte ptr [rcx+8], 0
0x1800a6c3e  jz      short loc_1800A6C66
0x1800a6c40  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a6c45  cmp     [rax+7CCh], ebx
0x1800a6c4b  jz      short loc_1800A6C66
0x1800a6c4d  mov     r9d, ebx; int
0x1800a6c50  mov     r8d, 80Bh; int
0x1800a6c56  lea     rdx, aCrawimagereade_21; "CRawImageReader::AddRationalEntryToEntr"...
0x1800a6c5d  mov     rcx, rax; this
0x1800a6c60  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a6c65  nop
0x1800a6c66  lea     rcx, [rsp+0C8h+var_68]; this
0x1800a6c6b  call    ??1CAutoTrace@CTraceBase@@QEAA@XZ; CTraceBase::CAutoTrace::~CAutoTrace(void)
0x1800a6c70  nop
0x1800a6c71  lea     rcx, [rsp+0C8h+var_78]; this
0x1800a6c76  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800a6c7b  mov     eax, ebx
0x1800a6c7d  mov     rcx, [rsp+0C8h+var_38]
0x1800a6c85  xor     rcx, rsp; StackCookie
0x1800a6c88  call    __security_check_cookie
0x1800a6c8d  mov     rbx, [rsp+0C8h+arg_10]
0x1800a6c95  add     rsp, 0A0h
0x1800a6c9c  pop     r15
0x1800a6c9e  pop     r14
0x1800a6ca0  pop     rdi
0x1800a6ca1  pop     rsi
0x1800a6ca2  pop     rbp
0x1800a6ca3  retn
```
