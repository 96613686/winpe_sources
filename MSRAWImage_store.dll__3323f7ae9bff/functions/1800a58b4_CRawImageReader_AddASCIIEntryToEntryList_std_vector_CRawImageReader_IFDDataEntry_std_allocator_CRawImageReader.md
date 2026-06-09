# CRawImageReader::AddASCIIEntryToEntryList(std::vector<CRawImageReader::IFDDataEntry,std::allocator<CRawImageReader::IFDDataEntry>> *,uint *,bool,ushort,char const *)

- ea: `0x1800a58b4`
- end: `0x1800a5b8a`
- name: `?AddASCIIEntryToEntryList@CRawImageReader@@AEAAJPEAV?$vector@UIFDDataEntry@CRawImageReader@@V?$allocator@UIFDDataEntry@CRawImageReader@@@std@@@std@@PEAI_NGPEBD@Z`
- size: `726`
- prototype: `__int64 __usercall@<rax>(CRawImageReader *this@<rcx>, __int16, __int64)`
- caller_count: `1`
- callee_count: `14`
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
- `0x1800a58b4`
- `0x1800a6784`
- `0x1800ac564`
- `0x1800ad348`
- `0x1800b020c`
- `0x1800b4010`

## string_xrefs

- `0x1800a5902`: `CRawImageReader::AddASCIIEntryToEntryList`
- `0x1800a598f`: `CRawImageReader::AddASCIIEntryToEntryList`
- `0x1800a5b37`: `CRawImageReader::AddASCIIEntryToEntryList`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CRawImageReader::AddASCIIEntryToEntryList(
        CRawImageReader *this,
        __int64 a2,
        _DWORD *a3,
        char a4,
        unsigned __int16 a5,
        const char *a6)
{
  int *v10; // r9
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v12; // ebx
  int v13; // ebx
  unsigned int *v14; // r14
  int v15; // r13d
  CallStackTracing *v16; // rcx
  struct CallStackContext *v17; // rax
  int v18; // r8d
  CallStackTracing *v19; // rcx
  int v21; // [rsp+20h] [rbp-F8h]
  size_t v22; // [rsp+38h] [rbp-E0h]
  _BYTE v23[8]; // [rsp+50h] [rbp-C8h] BYREF
  __int64 v24; // [rsp+58h] [rbp-C0h]
  char v25[32]; // [rsp+60h] [rbp-B8h] BYREF
  char Buffer[80]; // [rsp+80h] [rbp-98h] BYREF

  v24 = -2;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v23,
    "CRawImageReader::AddASCIIEntryToEntryList",
    2002);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 34) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v12 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 34) + 296LL))(*((_QWORD *)this + 34));
    *((_OWORD *)ThreadRelativeContext + 125) = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 34) + 280LL))(
                                                            *((_QWORD *)this + 34),
                                                            v25);
    *((_DWORD *)ThreadRelativeContext + 504) = v12;
  }
  v13 = 0;
  v14 = (unsigned int *)((char *)this + 56);
  CTraceBase::CAutoTrace::CAutoTrace(
    (CTraceBase::CAutoTrace *)v25,
    (struct CTraceBase *)(((unsigned __int64)this + 56) & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64)),
    "CRawImageReader::AddASCIIEntryToEntryList",
    v10,
    v21);
  v15 = sprintf_s(Buffer, 0x41u, "%s", a6);
  if ( v15 <= 0 )
    goto LABEL_29;
  if ( a4 )
  {
    v13 = CRawImageReader::RemoveTagInEntryListIfExists(this, a2, a3, a5);
    if ( v13 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 166, &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids, *v14, v13);
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
        if ( *((_DWORD *)v17 + 499) != v13 )
        {
          v18 = 2010;
LABEL_28:
          CallStackContext::TraceFailure(v17, "CRawImageReader::AddASCIIEntryToEntryList", v18, v13);
          goto LABEL_29;
        }
      }
      goto LABEL_29;
    }
  }
  else if ( (unsigned __int8)CRawImageReader::IsTagInEntryList(this, a2, a5) )
  {
    v13 = 0;
    goto LABEL_29;
  }
  LODWORD(v22) = v15 + 1;
  v13 = CRawImageReader::AddOneIFDEntryToEntryList(this, a2, a3, a5, 2u, v15 + 1, 0, v22, (unsigned __int8 *)Buffer);
  if ( v13 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 167, &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids, *v14, v13);
    }
    v19 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v19 = (CallStackTracing *)&off_1800E5190;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
    }
    if ( *((_BYTE *)v19 + 8) )
    {
      v17 = CallStackTracing::GetThreadRelativeContext(v19);
      if ( *((_DWORD *)v17 + 499) != v13 )
      {
        v18 = 2019;
        goto LABEL_28;
      }
    }
  }
LABEL_29:
  CTraceBase::CAutoTrace::~CAutoTrace((CTraceBase::CAutoTrace *)v25);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v23);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1800a58b4  mov     rax, rsp
0x1800a58b7  push    rbp
0x1800a58b8  push    rsi
0x1800a58b9  push    rdi
0x1800a58ba  push    r12
0x1800a58bc  push    r13
0x1800a58be  push    r14
0x1800a58c0  push    r15
0x1800a58c2  sub     rsp, 0E0h
0x1800a58c9  mov     [rsp+118h+var_C0], 0FFFFFFFFFFFFFFFEh
0x1800a58d2  mov     [rax+18h], rbx
0x1800a58d6  mov     rax, cs:__security_cookie
0x1800a58dd  xor     rax, rsp
0x1800a58e0  mov     [rsp+118h+var_48], rax
0x1800a58e8  mov     r12b, r9b
0x1800a58eb  mov     r15, r8
0x1800a58ee  mov     rbp, rdx
0x1800a58f1  mov     rsi, rcx
0x1800a58f4  mov     r13, [rsp+118h+arg_28]
0x1800a58fc  mov     r8d, 7D2h; int
0x1800a5902  lea     rdx, aCrawimagereade_1; "CRawImageReader::AddASCIIEntryToEntryLi"...
0x1800a5909  lea     rcx, [rsp+118h+var_C8]; this
0x1800a590e  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800a5913  nop
0x1800a5914  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800a591b  cmp     byte ptr [rcx+8], 0
0x1800a591f  jz      short loc_1800A597D
0x1800a5921  cmp     qword ptr [rsi+110h], 0
0x1800a5929  jz      short loc_1800A597D
0x1800a592b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a5930  mov     rdi, rax
0x1800a5933  mov     rdx, [rsi+110h]
0x1800a593a  mov     rcx, [rdx]
0x1800a593d  mov     rax, [rcx+128h]
0x1800a5944  mov     rcx, rdx
0x1800a5947  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a594c  mov     ebx, eax
0x1800a594e  mov     r8, [rsi+110h]
0x1800a5955  mov     rcx, [r8]
0x1800a5958  mov     rax, [rcx+118h]
0x1800a595f  lea     rdx, [rsp+118h+var_B8]
0x1800a5964  mov     rcx, r8
0x1800a5967  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a596c  movups  xmm0, xmmword ptr [rax]
0x1800a596f  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x1800a5977  mov     [rdi+7E0h], ebx
0x1800a597d  xor     ebx, ebx
0x1800a597f  lea     r14, [rsi+38h]
0x1800a5983  mov     rax, rsi
0x1800a5986  neg     rax
0x1800a5989  sbb     rdx, rdx
0x1800a598c  and     rdx, r14; struct CTraceBase *
0x1800a598f  lea     r8, aCrawimagereade_1; "CRawImageReader::AddASCIIEntryToEntryLi"...
0x1800a5996  lea     rcx, [rsp+118h+var_B8]; this
0x1800a599b  call    ??0CAutoTrace@CTraceBase@@QEAA@PEAV1@PEBDPEAJH@Z; CTraceBase::CAutoTrace::CAutoTrace(CTraceBase *,char const *,long *,int)
0x1800a59a0  nop
0x1800a59a1  mov     r9, r13
0x1800a59a4  lea     r8, aS_0; "%s"
0x1800a59ab  lea     edx, [rbx+41h]; BufferCount
0x1800a59ae  lea     rcx, [rsp+118h+Buffer]; Buffer
0x1800a59b6  call    sprintf_s
0x1800a59bb  mov     r13d, eax
0x1800a59be  test    eax, eax
0x1800a59c0  jle     loc_1800A5B47
0x1800a59c6  movzx   edi, [rsp+118h+arg_20]
0x1800a59ce  mov     rdx, rbp
0x1800a59d1  mov     rcx, rsi
0x1800a59d4  test    r12b, r12b
0x1800a59d7  jz      loc_1800A5A6E
0x1800a59dd  movzx   r9d, di
0x1800a59e1  mov     r8, r15
0x1800a59e4  call    ?RemoveTagInEntryListIfExists@CRawImageReader@@AEAAJPEAV?$vector@UIFDDataEntry@CRawImageReader@@V?$allocator@UIFDDataEntry@CRawImageReader@@@std@@@std@@PEAIG@Z; CRawImageReader::RemoveTagInEntryListIfExists(std::vector<CRawImageReader::IFDDataEntry> *,uint *,ushort)
0x1800a59e9  mov     ebx, eax
0x1800a59eb  test    eax, eax
0x1800a59ed  jns     loc_1800A5A82
0x1800a59f3  lea     rax, WPP_GLOBAL_Control
0x1800a59fa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a5a01  cmp     rcx, rax
0x1800a5a04  jz      short loc_1800A5A2E
0x1800a5a06  test    byte ptr [rcx+1Ch], 1
0x1800a5a0a  jz      short loc_1800A5A2E
0x1800a5a0c  cmp     byte ptr [rcx+19h], 4
0x1800a5a10  jb      short loc_1800A5A2E
0x1800a5a12  mov     edx, 0A6h
0x1800a5a17  mov     dword ptr [rsp+118h+var_F8], ebx
0x1800a5a1b  mov     r9d, [r14]
0x1800a5a1e  lea     r8, WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids
0x1800a5a25  mov     rcx, [rcx+10h]
0x1800a5a29  call    WPP_SF_Dd
0x1800a5a2e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a5a35  test    rcx, rcx
0x1800a5a38  jnz     short loc_1800A5A48
0x1800a5a3a  lea     rcx, off_1800E5190; this
0x1800a5a41  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a5a48  cmp     byte ptr [rcx+8], 0
0x1800a5a4c  jz      loc_1800A5B47
0x1800a5a52  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a5a57  cmp     [rax+7CCh], ebx
0x1800a5a5d  jz      loc_1800A5B47
0x1800a5a63  mov     r8d, 7DAh
0x1800a5a69  jmp     loc_1800A5B34
0x1800a5a6e  movzx   r8d, di
0x1800a5a72  call    ?IsTagInEntryList@CRawImageReader@@AEAA_NPEAV?$vector@UIFDDataEntry@CRawImageReader@@V?$allocator@UIFDDataEntry@CRawImageReader@@@std@@@std@@G@Z; CRawImageReader::IsTagInEntryList(std::vector<CRawImageReader::IFDDataEntry> *,ushort)
0x1800a5a77  test    al, al
0x1800a5a79  jz      short loc_1800A5A82
0x1800a5a7b  xor     ebx, ebx
0x1800a5a7d  jmp     loc_1800A5B47
0x1800a5a82  lea     eax, [r13+1]
0x1800a5a86  lea     rcx, [rsp+118h+Buffer]
0x1800a5a8e  mov     [rsp+118h+var_D8], rcx; unsigned __int8 *
0x1800a5a93  mov     dword ptr [rsp+118h+var_E0], eax; size_t
0x1800a5a97  mov     [rsp+118h+var_E8], 0; unsigned int
0x1800a5a9f  mov     [rsp+118h+var_F0], eax; unsigned int
0x1800a5aa3  mov     [rsp+118h+var_F8], 2; __int16
0x1800a5aaa  movzx   r9d, di
0x1800a5aae  mov     r8, r15
0x1800a5ab1  mov     rdx, rbp
0x1800a5ab4  mov     rcx, rsi; this
0x1800a5ab7  call    ?AddOneIFDEntryToEntryList@CRawImageReader@@AEAAJPEAV?$vector@UIFDDataEntry@CRawImageReader@@V?$allocator@UIFDDataEntry@CRawImageReader@@@std@@@std@@PEAIGGIIIPEBE@Z; CRawImageReader::AddOneIFDEntryToEntryList(std::vector<CRawImageReader::IFDDataEntry> *,uint *,ushort,ushort,uint,uint,uint,uchar const *)
0x1800a5abc  mov     ebx, eax
0x1800a5abe  test    eax, eax
0x1800a5ac0  jns     loc_1800A5B47
0x1800a5ac6  lea     rax, WPP_GLOBAL_Control
0x1800a5acd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a5ad4  cmp     rcx, rax
0x1800a5ad7  jz      short loc_1800A5B01
0x1800a5ad9  test    byte ptr [rcx+1Ch], 1
0x1800a5add  jz      short loc_1800A5B01
0x1800a5adf  cmp     byte ptr [rcx+19h], 4
0x1800a5ae3  jb      short loc_1800A5B01
0x1800a5ae5  mov     edx, 0A7h
0x1800a5aea  mov     dword ptr [rsp+118h+var_F8], ebx
0x1800a5aee  mov     r9d, [r14]
0x1800a5af1  lea     r8, WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids
0x1800a5af8  mov     rcx, [rcx+10h]
0x1800a5afc  call    WPP_SF_Dd
0x1800a5b01  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a5b08  test    rcx, rcx
0x1800a5b0b  jnz     short loc_1800A5B1B
0x1800a5b0d  lea     rcx, off_1800E5190; this
0x1800a5b14  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a5b1b  cmp     byte ptr [rcx+8], 0
0x1800a5b1f  jz      short loc_1800A5B47
0x1800a5b21  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a5b26  cmp     [rax+7CCh], ebx
0x1800a5b2c  jz      short loc_1800A5B47
0x1800a5b2e  mov     r8d, 7E3h; int
0x1800a5b34  mov     r9d, ebx; int
0x1800a5b37  lea     rdx, aCrawimagereade_1; "CRawImageReader::AddASCIIEntryToEntryLi"...
0x1800a5b3e  mov     rcx, rax; this
0x1800a5b41  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a5b46  nop
0x1800a5b47  lea     rcx, [rsp+118h+var_B8]; this
0x1800a5b4c  call    ??1CAutoTrace@CTraceBase@@QEAA@XZ; CTraceBase::CAutoTrace::~CAutoTrace(void)
0x1800a5b51  nop
0x1800a5b52  lea     rcx, [rsp+118h+var_C8]; this
0x1800a5b57  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800a5b5c  mov     eax, ebx
0x1800a5b5e  mov     rcx, [rsp+118h+var_48]
0x1800a5b66  xor     rcx, rsp; StackCookie
0x1800a5b69  call    __security_check_cookie
0x1800a5b6e  mov     rbx, [rsp+118h+arg_10]
0x1800a5b76  add     rsp, 0E0h
0x1800a5b7d  pop     r15
0x1800a5b7f  pop     r14
0x1800a5b81  pop     r13
0x1800a5b83  pop     r12
0x1800a5b85  pop     rdi
0x1800a5b86  pop     rsi
0x1800a5b87  pop     rbp
0x1800a5b88  retn
```
