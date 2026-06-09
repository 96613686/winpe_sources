# CDCOMInterfaceMashallerHelper::UnMarshalInterface(CBinaryReader &,_GUID const &,void * *)

- ea: `0x1801c1ed4`
- end: `0x1801c2521`
- name: `?UnMarshalInterface@CDCOMInterfaceMashallerHelper@@SAJAEAVCBinaryReader@@AEBU_GUID@@PEAPEAX@Z`
- size: `1613`
- prototype: `__int64 __fastcall(struct CBinaryReader *this, IID *riid, LPVOID *ppv)`
- caller_count: `11`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x1801ac5a0`
- `0x1801c08e0`
- `0x1801e7a50`
- `0x18020b284`
- `0x1802c8800`
- `0x1802c8b30`
- `0x1802cab8c`
- `0x180326484`
- `0x180328174`
- `0x180328370`
- `0x18032de50`

## callees

- `0x18002fee0`
- `0x18003ecb0`
- `0x1800402c0`
- `0x180050d6c`
- `0x180063f00`
- `0x1800ec0e0`
- `0x1801338f8`
- `0x1801c1ed4`
- `0x180344d40`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801c243a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801c243a`
- `api-ms-win-core-com-l1-1-0!CoUnmarshalInterface` at `0x1801c2376`
- `api-ms-win-core-com-l1-1-0!CoUnmarshalInterface` at `0x1801c2376`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801c208e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801c208e`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1801c1f2a`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1801c1f2a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801c1f4c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801c1ff4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801c20b7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801c216c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801c2227`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801c22e2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801c2398`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801c245c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801c1f4c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801c1ff4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801c20b7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801c216c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801c2227`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801c22e2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801c2398`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801c245c`

## string_xrefs

- `0x1801c1eeb`: `CDCOMInterfaceMashallerHelper::UnMarshalInterface`
- `0x1801c2115`: `CDCOMInterfaceMashallerHelper::UnMarshalInterface`
- `0x1801c21ca`: `CDCOMInterfaceMashallerHelper::UnMarshalInterface`
- `0x1801c2285`: `CDCOMInterfaceMashallerHelper::UnMarshalInterface`
- `0x1801c2340`: `CDCOMInterfaceMashallerHelper::UnMarshalInterface`
- `0x1801c23f6`: `CDCOMInterfaceMashallerHelper::UnMarshalInterface`
- `0x1801c24ba`: `CDCOMInterfaceMashallerHelper::UnMarshalInterface`

## pseudocode

```c
__int64 __fastcall CDCOMInterfaceMashallerHelper::UnMarshalInterface(
        struct CBinaryReader *this,
        IID *riid,
        LPVOID *ppv)
{
  __int64 v6; // rdx
  HRESULT v7; // ebx
  __int64 v8; // r8
  __int64 *v9; // rcx
  CallStackTracing *v10; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v12; // rdx
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  unsigned int v18; // edi
  LPVOID v19; // rax
  __int64 v20; // rdx
  __int64 v21; // r8
  void *v22; // r14
  __int64 *v23; // rcx
  CallStackTracing *v24; // rax
  struct CallStackContext *v25; // rax
  __int64 v26; // rdx
  __int64 v27; // r8
  __int64 *v28; // rcx
  CallStackTracing *v29; // rax
  struct CallStackContext *v30; // rax
  __int64 v31; // rdx
  __int64 v32; // rdx
  __int64 v33; // r8
  __int64 *v34; // rcx
  CallStackTracing *v35; // rax
  struct CallStackContext *v36; // rax
  __int64 v37; // rdx
  __int64 v38; // r8
  __int64 *v39; // rcx
  CallStackTracing *v40; // rax
  struct CallStackContext *v41; // rax
  __int64 v42; // rdx
  __int64 v43; // r8
  __int64 *v44; // rcx
  CallStackTracing *v45; // rax
  struct CallStackContext *v46; // rax
  __int64 *v47; // rcx
  CallStackTracing *v48; // rax
  struct CallStackContext *v49; // rax
  int v51; // [rsp+30h] [rbp-28h] BYREF
  LPSTREAM ppstm; // [rsp+38h] [rbp-20h] BYREF
  SIZE_T cb; // [rsp+40h] [rbp-18h] BYREF
  __int64 v54; // [rsp+48h] [rbp-10h]
  char v55; // [rsp+B8h] [rbp+60h] BYREF

  ppstm = 0;
  cb = 0;
  v51 = 0;
  v54 = 0;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v55,
    "CDCOMInterfaceMashallerHelper::UnMarshalInterface",
    1293);
  v7 = CreateStreamOnHGlobal(0, 1, &ppstm);
  if ( v7 < 0 )
  {
    v9 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v10 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6, v8);
      CallStackTracing::s_wpInstance = v10;
      if ( v10 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v10 + 8LL))(v10, 2032) )
      {
        v9 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v9 = &qword_1803CE250;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
      }
    }
    if ( *((_BYTE *)v9 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v9);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != v7 )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CDCOMInterfaceMashallerHelper::UnMarshalInterface",
          1293,
          v7);
    }
    if ( g_wppLevels )
    {
      v12 = 99;
LABEL_91:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, &WPP_9f8a26c46d5635c487300a376c0e4004_Traceguids, 0, v7);
      goto LABEL_92;
    }
    goto LABEL_92;
  }
  v7 = CBinaryReader::ReadUInt64(this, &cb);
  if ( v7 >= 0 )
  {
    v18 = cb;
    if ( cb > 0xFFFFFFFF )
    {
      v47 = (__int64 *)CallStackTracing::s_wpInstance;
      v7 = -2147024362;
      if ( !CallStackTracing::s_wpInstance )
      {
        v48 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v13, v14);
        CallStackTracing::s_wpInstance = v48;
        if ( v48 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v48 + 8LL))(v48, 2032) )
        {
          v47 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v47 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v47 + 8) )
      {
        v49 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v47);
        if ( *((_DWORD *)v49 + 499) != -2147024362 )
          CallStackContext::TraceFailure(v49, "CDCOMInterfaceMashallerHelper::UnMarshalInterface", 1297, -2147024362);
      }
      if ( g_wppLevels )
      {
        v12 = 101;
        goto LABEL_91;
      }
      goto LABEL_92;
    }
    v19 = CoTaskMemAlloc((unsigned int)cb);
    v22 = v19;
    if ( !v19 )
    {
      v23 = (__int64 *)CallStackTracing::s_wpInstance;
      v7 = -2147418113;
      if ( !CallStackTracing::s_wpInstance )
      {
        v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v20, v21);
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
        if ( *((_DWORD *)v25 + 499) != -2147418113 )
          CallStackContext::TraceFailure(v25, "CDCOMInterfaceMashallerHelper::UnMarshalInterface", 1300, -2147418113);
      }
      if ( g_wppLevels )
      {
        v12 = 102;
        goto LABEL_91;
      }
      goto LABEL_92;
    }
    v7 = (**(__int64 (__fastcall ***)(struct CBinaryReader *, LPVOID, _QWORD))this)(this, v19, v18);
    if ( v7 >= 0 )
    {
      v7 = (*(__int64 (__fastcall **)(LPSTREAM, void *, _QWORD, int *))(*(_QWORD *)ppstm + 32LL))(ppstm, v22, v18, &v51);
      if ( v7 >= 0 )
      {
        v7 = (*(__int64 (__fastcall **)(LPSTREAM, __int64, _QWORD, _QWORD))(*(_QWORD *)ppstm + 40LL))(ppstm, v54, 0, 0);
        if ( v7 >= 0 )
        {
          v7 = CoUnmarshalInterface(ppstm, riid, ppv);
          if ( v7 >= 0 )
            goto LABEL_80;
          v44 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v45 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v42, v43);
            CallStackTracing::s_wpInstance = v45;
            if ( v45 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v45 + 8LL))(v45, 2032) )
            {
              v44 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v44 = &qword_1803CE250;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
            }
          }
          if ( *((_BYTE *)v44 + 8) )
          {
            v46 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v44);
            if ( *((_DWORD *)v46 + 499) != v7 )
              CallStackContext::TraceFailure(v46, "CDCOMInterfaceMashallerHelper::UnMarshalInterface", 1308, v7);
          }
          if ( !g_wppLevels )
            goto LABEL_80;
          v31 = 106;
        }
        else
        {
          v39 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v40 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v37, v38);
            CallStackTracing::s_wpInstance = v40;
            if ( v40 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v40 + 8LL))(v40, 2032) )
            {
              v39 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v39 = &qword_1803CE250;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
            }
          }
          if ( *((_BYTE *)v39 + 8) )
          {
            v41 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v39);
            if ( *((_DWORD *)v41 + 499) != v7 )
              CallStackContext::TraceFailure(v41, "CDCOMInterfaceMashallerHelper::UnMarshalInterface", 1306, v7);
          }
          if ( !g_wppLevels )
            goto LABEL_80;
          v31 = 105;
        }
      }
      else
      {
        v34 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v35 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v32, v33);
          CallStackTracing::s_wpInstance = v35;
          if ( v35 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v35 + 8LL))(v35, 2032) )
          {
            v34 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v34 = &qword_1803CE250;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
          }
        }
        if ( *((_BYTE *)v34 + 8) )
        {
          v36 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v34);
          if ( *((_DWORD *)v36 + 499) != v7 )
            CallStackContext::TraceFailure(v36, "CDCOMInterfaceMashallerHelper::UnMarshalInterface", 1304, v7);
        }
        if ( !g_wppLevels )
          goto LABEL_80;
        v31 = 104;
      }
    }
    else
    {
      v28 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v29 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v26, v27);
        CallStackTracing::s_wpInstance = v29;
        if ( v29 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v29 + 8LL))(v29, 2032) )
        {
          v28 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v28 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v28 + 8) )
      {
        v30 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v28);
        if ( *((_DWORD *)v30 + 499) != v7 )
          CallStackContext::TraceFailure(v30, "CDCOMInterfaceMashallerHelper::UnMarshalInterface", 1302, v7);
      }
      if ( !g_wppLevels )
        goto LABEL_80;
      v31 = 103;
    }
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v31, &WPP_9f8a26c46d5635c487300a376c0e4004_Traceguids, 0, v7);
LABEL_80:
    CoTaskMemFree(v22);
    goto LABEL_92;
  }
  v15 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v13, v14);
    CallStackTracing::s_wpInstance = v16;
    if ( v16 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
    {
      v15 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v15 = &qword_1803CE250;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
    }
  }
  if ( *((_BYTE *)v15 + 8) )
  {
    v17 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v15);
    if ( *((_DWORD *)v17 + 499) != v7 )
      CallStackContext::TraceFailure(v17, "CDCOMInterfaceMashallerHelper::UnMarshalInterface", 1295, v7);
  }
  if ( g_wppLevels )
  {
    v12 = 100;
    goto LABEL_91;
  }
LABEL_92:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v55);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&ppstm);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1801c1ed4  push    rbp
0x1801c1ed6  push    rbx
0x1801c1ed7  push    rsi
0x1801c1ed8  push    rdi
0x1801c1ed9  push    r12
0x1801c1edb  push    r13
0x1801c1edd  push    r14
0x1801c1edf  push    r15
0x1801c1ee1  mov     rbp, rsp
0x1801c1ee4  sub     rsp, 58h
0x1801c1ee8  xor     r13d, r13d
0x1801c1eeb  lea     rdi, aCdcominterface; "CDCOMInterfaceMashallerHelper::UnMarsha"...
0x1801c1ef2  mov     r15, r8
0x1801c1ef5  mov     [rbp+ppstm], r13
0x1801c1ef9  mov     r12, rdx
0x1801c1efc  mov     [rbp+cb], r13
0x1801c1f00  mov     rsi, rcx
0x1801c1f03  mov     [rbp+var_28], r13d
0x1801c1f07  mov     rdx, rdi; char *
0x1801c1f0a  mov     [rbp+var_10], r13
0x1801c1f0e  mov     r8d, 50Dh; int
0x1801c1f14  lea     rcx, [rbp+arg_18]; this
0x1801c1f18  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1801c1f1d  lea     r14d, [r13+1]
0x1801c1f21  xor     ecx, ecx; hGlobal
0x1801c1f23  mov     edx, r14d; fDeleteOnRelease
0x1801c1f26  lea     r8, [rbp+ppstm]; ppstm
0x1801c1f2a  call    cs:__imp_CreateStreamOnHGlobal
0x1801c1f31  nop     dword ptr [rax+rax+00h]
0x1801c1f36  mov     ebx, eax
0x1801c1f38  test    eax, eax
0x1801c1f3a  jns     loc_1801C1FD2
0x1801c1f40  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801c1f47  test    rcx, rcx
0x1801c1f4a  jnz     short loc_1801C1F94
0x1801c1f4c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801c1f53  nop     dword ptr [rax+rax+00h]
0x1801c1f58  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801c1f5f  mov     rcx, rax
0x1801c1f62  test    rax, rax
0x1801c1f65  jz      short loc_1801C1F86
0x1801c1f67  mov     rax, [rax]
0x1801c1f6a  mov     edx, 7F0h
0x1801c1f6f  mov     rax, [rax+8]
0x1801c1f73  call    cs:__guard_dispatch_icall_fptr
0x1801c1f79  test    eax, eax
0x1801c1f7b  jz      short loc_1801C1F86
0x1801c1f7d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801c1f84  jmp     short loc_1801C1F94
0x1801c1f86  lea     rcx, qword_1803CE250; this
0x1801c1f8d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801c1f94  cmp     [rcx+8], r13b
0x1801c1f98  jz      short loc_1801C1FBB
0x1801c1f9a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801c1f9f  cmp     [rax+7CCh], ebx
0x1801c1fa5  jz      short loc_1801C1FBB
0x1801c1fa7  mov     r9d, ebx; int
0x1801c1faa  mov     r8d, 50Dh; int
0x1801c1fb0  mov     rdx, rdi; char *
0x1801c1fb3  mov     rcx, rax; this
0x1801c1fb6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801c1fbb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r14b; MFWppLevels g_wppLevels
0x1801c1fc2  jb      loc_1801C24FB
0x1801c1fc8  mov     edx, 63h ; 'c'
0x1801c1fcd  jmp     loc_1801C24DD
0x1801c1fd2  lea     rdx, [rbp+cb]; unsigned __int64 *
0x1801c1fd6  mov     rcx, rsi; this
0x1801c1fd9  call    ?ReadUInt64@CBinaryReader@@QEAAJAEA_K@Z; CBinaryReader::ReadUInt64(unsigned __int64 &)
0x1801c1fde  mov     ebx, eax
0x1801c1fe0  test    eax, eax
0x1801c1fe2  jns     loc_1801C207A
0x1801c1fe8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801c1fef  test    rcx, rcx
0x1801c1ff2  jnz     short loc_1801C203C
0x1801c1ff4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801c1ffb  nop     dword ptr [rax+rax+00h]
0x1801c2000  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801c2007  mov     rcx, rax
0x1801c200a  test    rax, rax
0x1801c200d  jz      short loc_1801C202E
0x1801c200f  mov     rax, [rax]
0x1801c2012  mov     edx, 7F0h
0x1801c2017  mov     rax, [rax+8]
0x1801c201b  call    cs:__guard_dispatch_icall_fptr
0x1801c2021  test    eax, eax
0x1801c2023  jz      short loc_1801C202E
0x1801c2025  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801c202c  jmp     short loc_1801C203C
0x1801c202e  lea     rcx, qword_1803CE250; this
0x1801c2035  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801c203c  cmp     [rcx+8], r13b
0x1801c2040  jz      short loc_1801C2063
0x1801c2042  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801c2047  cmp     [rax+7CCh], ebx
0x1801c204d  jz      short loc_1801C2063
0x1801c204f  mov     r9d, ebx; int
0x1801c2052  mov     r8d, 50Fh; int
0x1801c2058  mov     rdx, rdi; char *
0x1801c205b  mov     rcx, rax; this
0x1801c205e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801c2063  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r14b; MFWppLevels g_wppLevels
0x1801c206a  jb      loc_1801C24FB
0x1801c2070  mov     edx, 64h ; 'd'
0x1801c2075  jmp     loc_1801C24DD
0x1801c207a  mov     rdi, [rbp+cb]
0x1801c207e  mov     eax, 0FFFFFFFFh
0x1801c2083  cmp     rdi, rax
0x1801c2086  ja      loc_1801C244B
0x1801c208c  mov     ecx, edi; cb
0x1801c208e  call    cs:__imp_CoTaskMemAlloc
0x1801c2095  nop     dword ptr [rax+rax+00h]
0x1801c209a  mov     r14, rax
0x1801c209d  test    rax, rax
0x1801c20a0  jnz     loc_1801C2141
0x1801c20a6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801c20ad  mov     ebx, 8000FFFFh
0x1801c20b2  test    rcx, rcx
0x1801c20b5  jnz     short loc_1801C20FF
0x1801c20b7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801c20be  nop     dword ptr [rax+rax+00h]
0x1801c20c3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801c20ca  mov     rcx, rax
0x1801c20cd  test    rax, rax
0x1801c20d0  jz      short loc_1801C20F1
0x1801c20d2  mov     rax, [rax]
0x1801c20d5  mov     edx, 7F0h
0x1801c20da  mov     rax, [rax+8]
0x1801c20de  call    cs:__guard_dispatch_icall_fptr
0x1801c20e4  test    eax, eax
0x1801c20e6  jz      short loc_1801C20F1
0x1801c20e8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801c20ef  jmp     short loc_1801C20FF
0x1801c20f1  lea     rcx, qword_1803CE250; this
0x1801c20f8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801c20ff  cmp     [rcx+8], r13b
0x1801c2103  jz      short loc_1801C212A
0x1801c2105  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801c210a  cmp     [rax+7CCh], ebx
0x1801c2110  jz      short loc_1801C212A
0x1801c2112  mov     r9d, ebx; int
0x1801c2115  lea     rdx, aCdcominterface; "CDCOMInterfaceMashallerHelper::UnMarsha"...
0x1801c211c  mov     r8d, 514h; int
0x1801c2122  mov     rcx, rax; this
0x1801c2125  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801c212a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801c2131  jb      loc_1801C24FB
0x1801c2137  mov     edx, 66h ; 'f'
0x1801c213c  jmp     loc_1801C24DD
0x1801c2141  mov     rax, [rsi]
0x1801c2144  mov     r8d, edi
0x1801c2147  mov     rdx, r14
0x1801c214a  mov     rcx, rsi
0x1801c214d  mov     rax, [rax]
0x1801c2150  call    cs:__guard_dispatch_icall_fptr
0x1801c2156  mov     ebx, eax
0x1801c2158  test    eax, eax
0x1801c215a  jns     loc_1801C21F6
0x1801c2160  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801c2167  test    rcx, rcx
0x1801c216a  jnz     short loc_1801C21B4
0x1801c216c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801c2173  nop     dword ptr [rax+rax+00h]
0x1801c2178  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801c217f  mov     rcx, rax
0x1801c2182  test    rax, rax
0x1801c2185  jz      short loc_1801C21A6
0x1801c2187  mov     rax, [rax]
0x1801c218a  mov     edx, 7F0h
0x1801c218f  mov     rax, [rax+8]
0x1801c2193  call    cs:__guard_dispatch_icall_fptr
0x1801c2199  test    eax, eax
0x1801c219b  jz      short loc_1801C21A6
0x1801c219d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801c21a4  jmp     short loc_1801C21B4
0x1801c21a6  lea     rcx, qword_1803CE250; this
0x1801c21ad  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801c21b4  cmp     [rcx+8], r13b
0x1801c21b8  jz      short loc_1801C21DF
0x1801c21ba  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801c21bf  cmp     [rax+7CCh], ebx
0x1801c21c5  jz      short loc_1801C21DF
0x1801c21c7  mov     r9d, ebx; int
0x1801c21ca  lea     rdx, aCdcominterface; "CDCOMInterfaceMashallerHelper::UnMarsha"...
0x1801c21d1  mov     r8d, 516h; int
0x1801c21d7  mov     rcx, rax; this
0x1801c21da  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801c21df  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801c21e6  jb      loc_1801C2437
0x1801c21ec  mov     edx, 67h ; 'g'
0x1801c21f1  jmp     loc_1801C2419
0x1801c21f6  mov     rcx, [rbp+ppstm]
0x1801c21fa  lea     r9, [rbp+var_28]
0x1801c21fe  mov     r8d, edi
0x1801c2201  mov     rdx, r14
0x1801c2204  mov     rax, [rcx]
0x1801c2207  mov     rax, [rax+20h]
0x1801c220b  call    cs:__guard_dispatch_icall_fptr
0x1801c2211  mov     ebx, eax
0x1801c2213  test    eax, eax
0x1801c2215  jns     loc_1801C22B1
0x1801c221b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801c2222  test    rcx, rcx
0x1801c2225  jnz     short loc_1801C226F
0x1801c2227  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801c222e  nop     dword ptr [rax+rax+00h]
0x1801c2233  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801c223a  mov     rcx, rax
0x1801c223d  test    rax, rax
0x1801c2240  jz      short loc_1801C2261
0x1801c2242  mov     rax, [rax]
0x1801c2245  mov     edx, 7F0h
0x1801c224a  mov     rax, [rax+8]
0x1801c224e  call    cs:__guard_dispatch_icall_fptr
0x1801c2254  test    eax, eax
0x1801c2256  jz      short loc_1801C2261
0x1801c2258  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801c225f  jmp     short loc_1801C226F
0x1801c2261  lea     rcx, qword_1803CE250; this
0x1801c2268  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801c226f  cmp     [rcx+8], r13b
0x1801c2273  jz      short loc_1801C229A
0x1801c2275  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801c227a  cmp     [rax+7CCh], ebx
0x1801c2280  jz      short loc_1801C229A
0x1801c2282  mov     r9d, ebx; int
0x1801c2285  lea     rdx, aCdcominterface; "CDCOMInterfaceMashallerHelper::UnMarsha"...
0x1801c228c  mov     r8d, 518h; int
0x1801c2292  mov     rcx, rax; this
0x1801c2295  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801c229a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801c22a1  jb      loc_1801C2437
0x1801c22a7  mov     edx, 68h ; 'h'
0x1801c22ac  jmp     loc_1801C2419
0x1801c22b1  mov     rcx, [rbp+ppstm]
0x1801c22b5  xor     r9d, r9d
0x1801c22b8  mov     rdx, [rbp+var_10]
0x1801c22bc  xor     r8d, r8d
0x1801c22bf  mov     rax, [rcx]
0x1801c22c2  mov     rax, [rax+28h]
0x1801c22c6  call    cs:__guard_dispatch_icall_fptr
0x1801c22cc  mov     ebx, eax
0x1801c22ce  test    eax, eax
0x1801c22d0  jns     loc_1801C236C
0x1801c22d6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801c22dd  test    rcx, rcx
0x1801c22e0  jnz     short loc_1801C232A
0x1801c22e2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801c22e9  nop     dword ptr [rax+rax+00h]
0x1801c22ee  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801c22f5  mov     rcx, rax
0x1801c22f8  test    rax, rax
0x1801c22fb  jz      short loc_1801C231C
0x1801c22fd  mov     rax, [rax]
0x1801c2300  mov     edx, 7F0h
0x1801c2305  mov     rax, [rax+8]
0x1801c2309  call    cs:__guard_dispatch_icall_fptr
0x1801c230f  test    eax, eax
0x1801c2311  jz      short loc_1801C231C
0x1801c2313  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801c231a  jmp     short loc_1801C232A
0x1801c231c  lea     rcx, qword_1803CE250; this
0x1801c2323  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801c232a  cmp     [rcx+8], r13b
0x1801c232e  jz      short loc_1801C2355
0x1801c2330  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801c2335  cmp     [rax+7CCh], ebx
0x1801c233b  jz      short loc_1801C2355
0x1801c233d  mov     r9d, ebx; int
0x1801c2340  lea     rdx, aCdcominterface; "CDCOMInterfaceMashallerHelper::UnMarsha"...
0x1801c2347  mov     r8d, 51Ah; int
0x1801c234d  mov     rcx, rax; this
0x1801c2350  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801c2355  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801c235c  jb      loc_1801C2437
0x1801c2362  mov     edx, 69h ; 'i'
0x1801c2367  jmp     loc_1801C2419
0x1801c236c  mov     rcx, [rbp+ppstm]; pStm
0x1801c2370  mov     r8, r15; ppv
0x1801c2373  mov     rdx, r12; riid
0x1801c2376  call    cs:__imp_CoUnmarshalInterface
0x1801c237d  nop     dword ptr [rax+rax+00h]
0x1801c2382  mov     ebx, eax
0x1801c2384  test    eax, eax
0x1801c2386  jns     loc_1801C2437
0x1801c238c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801c2393  test    rcx, rcx
0x1801c2396  jnz     short loc_1801C23E0
0x1801c2398  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801c239f  nop     dword ptr [rax+rax+00h]
0x1801c23a4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801c23ab  mov     rcx, rax
0x1801c23ae  test    rax, rax
0x1801c23b1  jz      short loc_1801C23D2
0x1801c23b3  mov     rax, [rax]
0x1801c23b6  mov     edx, 7F0h
0x1801c23bb  mov     rax, [rax+8]
0x1801c23bf  call    cs:__guard_dispatch_icall_fptr
0x1801c23c5  test    eax, eax
0x1801c23c7  jz      short loc_1801C23D2
0x1801c23c9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
  ... truncated ...
```
