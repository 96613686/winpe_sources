# CPDBinaryWriter::Serialize(IMFPresentationDescriptor *,int)

- ea: `0x180191ee0`
- end: `0x1801924eb`
- name: `?Serialize@CPDBinaryWriter@@QEAAJPEAUIMFPresentationDescriptor@@H@Z`
- size: `1547`
- prototype: `__int64 __fastcall(CPDBinaryWriter *__hidden this, struct IMFPresentationDescriptor *, int)`
- caller_count: `3`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x1801a3360`
- `0x1801d4b10`
- `0x1802d5ed0`

## callees

- `0x18002fee0`
- `0x18003ecb0`
- `0x1800402c0`
- `0x180050d6c`
- `0x180063f00`
- `0x1800ec0e0`
- `0x18012649c`
- `0x180191ee0`
- `0x1801e40fc`
- `0x1802354ec`
- `0x180325914`
- `0x180326a88`
- `0x180344d40`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180191fa4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801920dd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180192173`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180192209`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801922d7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180192389`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019243b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180191fa4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801920dd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180192173`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180192209`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801922d7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180192389`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019243b`

## string_xrefs

- `0x180191f26`: `CPDBinaryWriter::Serialize`
- `0x180192002`: `CPDBinaryWriter::Serialize`
- `0x18019213b`: `CPDBinaryWriter::Serialize`
- `0x1801921d1`: `CPDBinaryWriter::Serialize`
- `0x180192267`: `CPDBinaryWriter::Serialize`
- `0x180192335`: `CPDBinaryWriter::Serialize`
- `0x1801923e7`: `CPDBinaryWriter::Serialize`
- `0x180192499`: `CPDBinaryWriter::Serialize`

## pseudocode

```c
__int64 __fastcall CPDBinaryWriter::Serialize(CPDBinaryWriter *this, IUnknown *a2, int a3)
{
  CBinaryWriter *v3; // rdi
  CBinaryWriter *v5; // rcx
  __int64 v8; // rdx
  int v9; // ebx
  __int64 v10; // r8
  __int64 *v11; // rcx
  CallStackTracing *v12; // rax
  struct CallStackContext *v13; // rax
  __int64 v14; // rdx
  unsigned int i; // r15d
  struct IMFPresentationDescriptorVtbl *lpVtbl; // rax
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 *v23; // rcx
  CallStackTracing *v24; // rax
  struct CallStackContext *v25; // rax
  __int64 v26; // rdx
  __int64 *v27; // rcx
  CallStackTracing *v28; // rax
  struct CallStackContext *v29; // rax
  __int64 *v30; // rcx
  CallStackTracing *v31; // rax
  struct CallStackContext *v32; // rax
  __int64 v33; // rdx
  __int64 v34; // r8
  __int64 *v35; // rcx
  CallStackTracing *v36; // rax
  struct CallStackContext *v37; // rax
  __int64 v38; // rdx
  __int64 v39; // r8
  __int64 *v40; // rcx
  CallStackTracing *v41; // rax
  struct CallStackContext *v42; // rax
  __int64 v43; // rdx
  __int64 v44; // r8
  __int64 *v45; // rcx
  CallStackTracing *v46; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  int v49; // [rsp+30h] [rbp-10h] BYREF
  struct IMFStreamDescriptor *v50; // [rsp+38h] [rbp-8h] BYREF
  char v51; // [rsp+78h] [rbp+38h] BYREF
  int v52; // [rsp+88h] [rbp+48h] BYREF

  v52 = 0;
  v3 = (CPDBinaryWriter *)((char *)this + 520);
  v5 = (CPDBinaryWriter *)((char *)this + 520);
  if ( !a2 )
  {
    CBinaryWriter::WriteBool(v5, 0);
    return 0;
  }
  CBinaryWriter::WriteBool(v5, 1);
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v51, "CPDBinaryWriter::Serialize", 37);
  if ( (unsigned __int8)byte_1803CECE9 >= 0x10u )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 7), 10, &WPP_363825162bad371b7f2cc59a20a496c3_Traceguids, this, a3);
  CBinaryWriter::WriteBool(v3, a3);
  if ( a3 )
  {
    v9 = CDCOMInterfaceMashallerHelper::MarshalInterface(v3, &IID_IMFPresentationDescriptor, a2);
    if ( v9 < 0 )
    {
      v45 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v46 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v43, v44);
        CallStackTracing::s_wpInstance = v46;
        if ( v46 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v46 + 8LL))(v46, 2032) )
        {
          v45 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v45 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v45 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v45);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != v9 )
          CallStackContext::TraceFailure(ThreadRelativeContext, "CPDBinaryWriter::Serialize", 71, v9);
      }
      if ( !g_wppLevels )
        goto LABEL_17;
      v14 = 17;
      goto LABEL_16;
    }
    goto LABEL_89;
  }
  v9 = ((__int64 (__fastcall *)(IUnknown *, int *))a2->lpVtbl[11].QueryInterface)(a2, &v52);
  if ( v9 >= 0 )
  {
    CBinaryWriter::WriteBool(v3, v52);
    for ( i = 0; i < v52; ++i )
    {
      lpVtbl = (struct IMFPresentationDescriptorVtbl *)a2->lpVtbl;
      v50 = 0;
      v49 = 0;
      v9 = ((__int64 (__fastcall *)(IUnknown *, _QWORD, int *, struct IMFStreamDescriptor **))lpVtbl->GetStreamDescriptorByIndex)(
             a2,
             i,
             &v49,
             &v50);
      if ( v9 < 0 )
      {
        v30 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v31 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v17, v18);
          CallStackTracing::s_wpInstance = v31;
          if ( v31 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v31 + 8LL))(v31, 2032) )
          {
            v30 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v30 = &qword_1803CE250;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
          }
        }
        if ( *((_BYTE *)v30 + 8) )
        {
          v32 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v30);
          if ( *((_DWORD *)v32 + 499) != v9 )
            CallStackContext::TraceFailure(v32, "CPDBinaryWriter::Serialize", 55, v9);
        }
        if ( !g_wppLevels )
          goto LABEL_55;
        v26 = 12;
LABEL_54:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v26, &WPP_363825162bad371b7f2cc59a20a496c3_Traceguids, this, v9);
        goto LABEL_55;
      }
      v9 = CBinaryWriter::WriteBool(v3, v49);
      if ( v9 < 0 )
      {
        v27 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v28 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v19, v20);
          CallStackTracing::s_wpInstance = v28;
          if ( v28 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v28 + 8LL))(v28, 2032) )
          {
            v27 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v27 = &qword_1803CE250;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
          }
        }
        if ( *((_BYTE *)v27 + 8) )
        {
          v29 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v27);
          if ( *((_DWORD *)v29 + 499) != v9 )
            CallStackContext::TraceFailure(v29, "CPDBinaryWriter::Serialize", 57, v9);
        }
        if ( !g_wppLevels )
          goto LABEL_55;
        v26 = 13;
        goto LABEL_54;
      }
      v9 = CPDBinaryWriter::SerializeSD(this, v50);
      if ( v9 < 0 )
      {
        v23 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v21, v22);
          CallStackTracing::s_wpInstance = v24;
          if ( v24 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v24 + 8LL))(v24, 2032) )
          {
            v23 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v23 = &qword_1803CE250;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
          }
        }
        if ( *((_BYTE *)v23 + 8) )
        {
          v25 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v23);
          if ( *((_DWORD *)v25 + 499) != v9 )
            CallStackContext::TraceFailure(v25, "CPDBinaryWriter::Serialize", 59, v9);
        }
        if ( g_wppLevels )
        {
          v26 = 14;
          goto LABEL_54;
        }
LABEL_55:
        ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v50);
        goto LABEL_17;
      }
      ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v50);
    }
    v9 = CBinaryWriter::WriteAttributes(v3, (IMFAttributes *)a2);
    if ( v9 < 0 )
    {
      v35 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v36 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v33, v34);
        CallStackTracing::s_wpInstance = v36;
        if ( v36 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v36 + 8LL))(v36, 2032) )
        {
          v35 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v35 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v35 + 8) )
      {
        v37 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v35);
        if ( *((_DWORD *)v37 + 499) != v9 )
          CallStackContext::TraceFailure(v37, "CPDBinaryWriter::Serialize", 65, v9);
      }
      if ( !g_wppLevels )
        goto LABEL_17;
      v14 = 15;
      goto LABEL_16;
    }
    v9 = CBinaryWriter::WriteUnknownAttributes(v3, (struct IMFAttributes *)a2);
    if ( v9 < 0 )
    {
      v40 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v41 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v38, v39);
        CallStackTracing::s_wpInstance = v41;
        if ( v41 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v41 + 8LL))(v41, 2032) )
        {
          v40 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v40 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v40 + 8) )
      {
        v42 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v40);
        if ( *((_DWORD *)v42 + 499) != v9 )
          CallStackContext::TraceFailure(v42, "CPDBinaryWriter::Serialize", 67, v9);
      }
      if ( !g_wppLevels )
        goto LABEL_17;
      v14 = 16;
      goto LABEL_16;
    }
LABEL_89:
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v51);
    return 0;
  }
  v11 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8, v10);
    CallStackTracing::s_wpInstance = v12;
    if ( v12 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v12 + 8LL))(v12, 2032) )
    {
      v11 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v11 = &qword_1803CE250;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
    }
  }
  if ( *((_BYTE *)v11 + 8) )
  {
    v13 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
    if ( *((_DWORD *)v13 + 499) != v9 )
      CallStackContext::TraceFailure(v13, "CPDBinaryWriter::Serialize", 44, v9);
  }
  if ( !g_wppLevels )
    goto LABEL_17;
  v14 = 11;
LABEL_16:
  WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, &WPP_363825162bad371b7f2cc59a20a496c3_Traceguids, this, v9);
LABEL_17:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v51);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180191ee0  mov     [rsp-28h+arg_0], rbx
0x180191ee5  push    rbp
0x180191ee6  push    rsi
0x180191ee7  push    rdi
0x180191ee8  push    r14
0x180191eea  push    r15
0x180191eec  mov     rbp, rsp
0x180191eef  sub     rsp, 40h
0x180191ef3  mov     [rbp+arg_18], 0
0x180191efa  lea     rdi, [rcx+208h]
0x180191f01  mov     r14, rcx
0x180191f04  mov     rcx, rdi; this
0x180191f07  mov     ebx, r8d
0x180191f0a  mov     rsi, rdx
0x180191f0d  test    rdx, rdx
0x180191f10  jz      loc_1801924D0
0x180191f16  mov     edx, 1; int
0x180191f1b  call    ?WriteBool@CBinaryWriter@@QEAAJH@Z; CBinaryWriter::WriteBool(int)
0x180191f20  mov     r8d, 25h ; '%'; int
0x180191f26  lea     rdx, aCpdbinarywrite; "CPDBinaryWriter::Serialize"
0x180191f2d  lea     rcx, [rbp+arg_8]; this
0x180191f31  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180191f36  cmp     cs:byte_1803CECE9, 10h
0x180191f3d  lea     r15, WPP_363825162bad371b7f2cc59a20a496c3_Traceguids
0x180191f44  jb      short loc_180191F65
0x180191f46  mov     rcx, cs:WPP_GLOBAL_Control
0x180191f4d  mov     edx, 0Ah
0x180191f52  mov     r9, r14
0x180191f55  mov     [rsp+40h+var_20], ebx
0x180191f59  mov     r8, r15
0x180191f5c  mov     rcx, [rcx+38h]
0x180191f60  call    WPP_SF_qD
0x180191f65  mov     edx, ebx; int
0x180191f67  mov     rcx, rdi; this
0x180191f6a  call    ?WriteBool@CBinaryWriter@@QEAAJH@Z; CBinaryWriter::WriteBool(int)
0x180191f6f  test    ebx, ebx
0x180191f71  jnz     loc_180192413
0x180191f77  mov     rax, [rsi]
0x180191f7a  lea     rdx, [rbp+arg_18]
0x180191f7e  mov     rcx, rsi
0x180191f81  mov     rax, [rax+108h]
0x180191f88  call    cs:__guard_dispatch_icall_fptr
0x180191f8e  mov     ebx, eax
0x180191f90  test    eax, eax
0x180191f92  jns     loc_18019204D
0x180191f98  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180191f9f  test    rcx, rcx
0x180191fa2  jnz     short loc_180191FEC
0x180191fa4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180191fab  nop     dword ptr [rax+rax+00h]
0x180191fb0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180191fb7  mov     rcx, rax
0x180191fba  test    rax, rax
0x180191fbd  jz      short loc_180191FDE
0x180191fbf  mov     rax, [rax]
0x180191fc2  mov     edx, 7F0h
0x180191fc7  mov     rax, [rax+8]
0x180191fcb  call    cs:__guard_dispatch_icall_fptr
0x180191fd1  test    eax, eax
0x180191fd3  jz      short loc_180191FDE
0x180191fd5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180191fdc  jmp     short loc_180191FEC
0x180191fde  lea     rcx, qword_1803CE250; this
0x180191fe5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180191fec  cmp     byte ptr [rcx+8], 0
0x180191ff0  jz      short loc_180192017
0x180191ff2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180191ff7  cmp     [rax+7CCh], ebx
0x180191ffd  jz      short loc_180192017
0x180191fff  mov     r9d, ebx; int
0x180192002  lea     rdx, aCpdbinarywrite; "CPDBinaryWriter::Serialize"
0x180192009  mov     r8d, 2Ch ; ','; int
0x18019200f  mov     rcx, rax; this
0x180192012  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180192017  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18019201e  jb      short loc_18019203F
0x180192020  mov     edx, 0Bh
0x180192025  mov     r8, r15
0x180192028  mov     rcx, cs:WPP_GLOBAL_Control
0x18019202f  mov     r9, r14
0x180192032  mov     [rsp+40h+var_20], ebx
0x180192036  mov     rcx, [rcx+10h]
0x18019203a  call    WPP_SF_qD
0x18019203f  lea     rcx, [rbp+arg_8]; this
0x180192043  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180192048  jmp     loc_1801924D7
0x18019204d  mov     edx, [rbp+arg_18]; int
0x180192050  mov     rcx, rdi; this
0x180192053  call    ?WriteBool@CBinaryWriter@@QEAAJH@Z; CBinaryWriter::WriteBool(int)
0x180192058  xor     r15d, r15d
0x18019205b  cmp     r15d, [rbp+arg_18]
0x18019205f  jnb     loc_1801922B6
0x180192065  mov     rax, [rsi]
0x180192068  lea     r9, [rbp+var_8]
0x18019206c  lea     r8, [rbp+var_10]
0x180192070  mov     [rbp+var_8], 0
0x180192078  mov     edx, r15d
0x18019207b  mov     [rbp+var_10], 0
0x180192082  mov     rcx, rsi
0x180192085  mov     rax, [rax+110h]
0x18019208c  call    cs:__guard_dispatch_icall_fptr
0x180192092  mov     ebx, eax
0x180192094  test    eax, eax
0x180192096  js      loc_1801921FD
0x18019209c  mov     edx, [rbp+var_10]; int
0x18019209f  mov     rcx, rdi; this
0x1801920a2  call    ?WriteBool@CBinaryWriter@@QEAAJH@Z; CBinaryWriter::WriteBool(int)
0x1801920a7  mov     ebx, eax
0x1801920a9  test    eax, eax
0x1801920ab  js      loc_180192167
0x1801920b1  mov     rdx, [rbp+var_8]; struct IMFStreamDescriptor *
0x1801920b5  mov     rcx, r14; this
0x1801920b8  call    ?SerializeSD@CPDBinaryWriter@@QEAAJPEAUIMFStreamDescriptor@@@Z; CPDBinaryWriter::SerializeSD(IMFStreamDescriptor *)
0x1801920bd  mov     ebx, eax
0x1801920bf  test    eax, eax
0x1801920c1  js      short loc_1801920D1
0x1801920c3  lea     rcx, [rbp+var_8]
0x1801920c7  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x1801920cc  inc     r15d
0x1801920cf  jmp     short loc_18019205B
0x1801920d1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801920d8  test    rcx, rcx
0x1801920db  jnz     short loc_180192125
0x1801920dd  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801920e4  nop     dword ptr [rax+rax+00h]
0x1801920e9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801920f0  mov     rcx, rax
0x1801920f3  test    rax, rax
0x1801920f6  jz      short loc_180192117
0x1801920f8  mov     rax, [rax]
0x1801920fb  mov     edx, 7F0h
0x180192100  mov     rax, [rax+8]
0x180192104  call    cs:__guard_dispatch_icall_fptr
0x18019210a  test    eax, eax
0x18019210c  jz      short loc_180192117
0x18019210e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180192115  jmp     short loc_180192125
0x180192117  lea     rcx, qword_1803CE250; this
0x18019211e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180192125  cmp     byte ptr [rcx+8], 0
0x180192129  jz      short loc_180192150
0x18019212b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180192130  cmp     [rax+7CCh], ebx
0x180192136  jz      short loc_180192150
0x180192138  mov     r9d, ebx; int
0x18019213b  lea     rdx, aCpdbinarywrite; "CPDBinaryWriter::Serialize"
0x180192142  mov     r8d, 3Bh ; ';'; int
0x180192148  mov     rcx, rax; this
0x18019214b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180192150  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180192157  jb      loc_1801922A8
0x18019215d  mov     edx, 0Eh
0x180192162  jmp     loc_18019228A
0x180192167  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18019216e  test    rcx, rcx
0x180192171  jnz     short loc_1801921BB
0x180192173  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18019217a  nop     dword ptr [rax+rax+00h]
0x18019217f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180192186  mov     rcx, rax
0x180192189  test    rax, rax
0x18019218c  jz      short loc_1801921AD
0x18019218e  mov     rax, [rax]
0x180192191  mov     edx, 7F0h
0x180192196  mov     rax, [rax+8]
0x18019219a  call    cs:__guard_dispatch_icall_fptr
0x1801921a0  test    eax, eax
0x1801921a2  jz      short loc_1801921AD
0x1801921a4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801921ab  jmp     short loc_1801921BB
0x1801921ad  lea     rcx, qword_1803CE250; this
0x1801921b4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801921bb  cmp     byte ptr [rcx+8], 0
0x1801921bf  jz      short loc_1801921E6
0x1801921c1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801921c6  cmp     [rax+7CCh], ebx
0x1801921cc  jz      short loc_1801921E6
0x1801921ce  mov     r9d, ebx; int
0x1801921d1  lea     rdx, aCpdbinarywrite; "CPDBinaryWriter::Serialize"
0x1801921d8  mov     r8d, 39h ; '9'; int
0x1801921de  mov     rcx, rax; this
0x1801921e1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801921e6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801921ed  jb      loc_1801922A8
0x1801921f3  mov     edx, 0Dh
0x1801921f8  jmp     loc_18019228A
0x1801921fd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180192204  test    rcx, rcx
0x180192207  jnz     short loc_180192251
0x180192209  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180192210  nop     dword ptr [rax+rax+00h]
0x180192215  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18019221c  mov     rcx, rax
0x18019221f  test    rax, rax
0x180192222  jz      short loc_180192243
0x180192224  mov     rax, [rax]
0x180192227  mov     edx, 7F0h
0x18019222c  mov     rax, [rax+8]
0x180192230  call    cs:__guard_dispatch_icall_fptr
0x180192236  test    eax, eax
0x180192238  jz      short loc_180192243
0x18019223a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180192241  jmp     short loc_180192251
0x180192243  lea     rcx, qword_1803CE250; this
0x18019224a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180192251  cmp     byte ptr [rcx+8], 0
0x180192255  jz      short loc_18019227C
0x180192257  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18019225c  cmp     [rax+7CCh], ebx
0x180192262  jz      short loc_18019227C
0x180192264  mov     r9d, ebx; int
0x180192267  lea     rdx, aCpdbinarywrite; "CPDBinaryWriter::Serialize"
0x18019226e  mov     r8d, 37h ; '7'; int
0x180192274  mov     rcx, rax; this
0x180192277  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18019227c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180192283  jb      short loc_1801922A8
0x180192285  mov     edx, 0Ch
0x18019228a  mov     rcx, cs:WPP_GLOBAL_Control
0x180192291  lea     r8, WPP_363825162bad371b7f2cc59a20a496c3_Traceguids
0x180192298  mov     r9, r14
0x18019229b  mov     [rsp+40h+var_20], ebx
0x18019229f  mov     rcx, [rcx+10h]
0x1801922a3  call    WPP_SF_qD
0x1801922a8  lea     rcx, [rbp+var_8]
0x1801922ac  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x1801922b1  jmp     loc_18019203F
0x1801922b6  mov     rdx, rsi; pAttributes
0x1801922b9  mov     rcx, rdi; this
0x1801922bc  call    ?WriteAttributes@CBinaryWriter@@QEAAJPEAUIMFAttributes@@@Z; CBinaryWriter::WriteAttributes(IMFAttributes *)
0x1801922c1  mov     ebx, eax
0x1801922c3  test    eax, eax
0x1801922c5  jns     loc_180192368
0x1801922cb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801922d2  test    rcx, rcx
0x1801922d5  jnz     short loc_18019231F
0x1801922d7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801922de  nop     dword ptr [rax+rax+00h]
0x1801922e3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801922ea  mov     rcx, rax
0x1801922ed  test    rax, rax
0x1801922f0  jz      short loc_180192311
0x1801922f2  mov     rax, [rax]
0x1801922f5  mov     edx, 7F0h
0x1801922fa  mov     rax, [rax+8]
0x1801922fe  call    cs:__guard_dispatch_icall_fptr
0x180192304  test    eax, eax
0x180192306  jz      short loc_180192311
0x180192308  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18019230f  jmp     short loc_18019231F
0x180192311  lea     rcx, qword_1803CE250; this
0x180192318  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18019231f  cmp     byte ptr [rcx+8], 0
0x180192323  jz      short loc_18019234A
0x180192325  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18019232a  cmp     [rax+7CCh], ebx
0x180192330  jz      short loc_18019234A
0x180192332  mov     r9d, ebx; int
0x180192335  lea     rdx, aCpdbinarywrite; "CPDBinaryWriter::Serialize"
0x18019233c  mov     r8d, 41h ; 'A'; int
0x180192342  mov     rcx, rax; this
0x180192345  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18019234a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180192351  jb      loc_18019203F
0x180192357  mov     edx, 0Fh
0x18019235c  lea     r8, WPP_363825162bad371b7f2cc59a20a496c3_Traceguids
0x180192363  jmp     loc_180192028
0x180192368  mov     rdx, rsi; struct IMFAttributes *
0x18019236b  mov     rcx, rdi; this
0x18019236e  call    ?WriteUnknownAttributes@CBinaryWriter@@QEAAJPEAUIMFAttributes@@@Z; CBinaryWriter::WriteUnknownAttributes(IMFAttributes *)
0x180192373  mov     ebx, eax
0x180192375  test    eax, eax
0x180192377  jns     loc_1801924C5
0x18019237d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180192384  test    rcx, rcx
0x180192387  jnz     short loc_1801923D1
0x180192389  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180192390  nop     dword ptr [rax+rax+00h]
0x180192395  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18019239c  mov     rcx, rax
0x18019239f  test    rax, rax
0x1801923a2  jz      short loc_1801923C3
0x1801923a4  mov     rax, [rax]
0x1801923a7  mov     edx, 7F0h
0x1801923ac  mov     rax, [rax+8]
0x1801923b0  call    cs:__guard_dispatch_icall_fptr
0x1801923b6  test    eax, eax
0x1801923b8  jz      short loc_1801923C3
0x1801923ba  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801923c1  jmp     short loc_1801923D1
0x1801923c3  lea     rcx, qword_1803CE250; this
0x1801923ca  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801923d1  cmp     byte ptr [rcx+8], 0
0x1801923d5  jz      short loc_1801923FC
0x1801923d7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801923dc  cmp     [rax+7CCh], ebx
0x1801923e2  jz      short loc_1801923FC
0x1801923e4  mov     r9d, ebx; int
0x1801923e7  lea     rdx, aCpdbinarywrite; "CPDBinaryWriter::Serialize"
0x1801923ee  mov     r8d, 43h ; 'C'; int
  ... truncated ...
```
