# CPDBinaryReader::Deserialize(IMFPresentationDescriptor * *)

- ea: `0x1801e7a50`
- end: `0x1801e835d`
- name: `?Deserialize@CPDBinaryReader@@QEAAJPEAPEAUIMFPresentationDescriptor@@@Z`
- size: `2317`
- prototype: `__int64 __fastcall(CPDBinaryReader *__hidden this, struct IMFPresentationDescriptor **)`
- caller_count: `2`
- callee_count: `18`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1801ebb70`
- `0x180255b50`

## callees

- `0x18002fee0`
- `0x18003ecb0`
- `0x1800402c0`
- `0x18004d118`
- `0x180050d6c`
- `0x180063f00`
- `0x1800ec0e0`
- `0x180101744`
- `0x1801356cc`
- `0x1801c1ed4`
- `0x1801e7a50`
- `0x1802464a0`
- `0x180258390`
- `0x180326484`
- `0x1803272d8`
- `0x180327778`
- `0x180327d44`
- `0x180344d40`

## import_xrefs

- `MFPlat!MFCreatePresentationDescriptor` at `0x1801e7f55`
- `MFPlat!MFCreatePresentationDescriptor` at `0x1801e7f55`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801e7ae5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801e7be8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801e7ccc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801e7e0b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801e7ea1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801e7f7a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801e8053`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801e80ff`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801e81cd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801e827d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801e7ae5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801e7be8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801e7ccc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801e7e0b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801e7ea1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801e7f7a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801e8053`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801e80ff`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801e81cd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801e827d`

## string_xrefs

- `0x1801e7a83`: `CPDBinaryReader::Deserialize`
- `0x1801e7b43`: `CPDBinaryReader::Deserialize`
- `0x1801e7c46`: `CPDBinaryReader::Deserialize`
- `0x1801e7d2a`: `CPDBinaryReader::Deserialize`
- `0x1801e7e69`: `CPDBinaryReader::Deserialize`
- `0x1801e7eff`: `CPDBinaryReader::Deserialize`
- `0x1801e7fd8`: `CPDBinaryReader::Deserialize`
- `0x1801e80b1`: `CPDBinaryReader::Deserialize`
- `0x1801e815d`: `CPDBinaryReader::Deserialize`
- `0x1801e822b`: `CPDBinaryReader::Deserialize`
- `0x1801e82db`: `CPDBinaryReader::Deserialize`

## pseudocode

```c
__int64 __fastcall CPDBinaryReader::Deserialize(CPDBinaryReader *this, struct IMFPresentationDescriptor **a2)
{
  unsigned int v2; // r14d
  DWORD v4; // r12d
  unsigned int v5; // r13d
  __int64 v6; // rdx
  HRESULT Attributes; // ebx
  __int64 v8; // r8
  __int64 *v9; // rcx
  CallStackTracing *v10; // rax
  struct CallStackContext *v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  struct CBinaryReader *v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 *v21; // rcx
  CallStackTracing *v22; // rax
  struct CallStackContext *v23; // rax
  __int64 v24; // rdx
  __int64 v25; // r8
  __int64 v26; // rdx
  __int64 v27; // r8
  struct IMFStreamDescriptor *v28; // rbx
  __int64 *v29; // rcx
  CallStackTracing *v30; // rax
  struct CallStackContext *v31; // rax
  __int64 v32; // rdx
  __int64 *v33; // rcx
  CallStackTracing *v34; // rax
  struct CallStackContext *v35; // rax
  __int64 v36; // rdx
  __int64 v37; // r8
  __int64 *v38; // rcx
  CallStackTracing *v39; // rax
  struct CallStackContext *v40; // rax
  __int64 v41; // rdx
  __int64 v42; // r8
  __int64 *v43; // rcx
  CallStackTracing *v44; // rax
  struct CallStackContext *v45; // rax
  __int64 v46; // rdx
  __int64 v47; // r8
  __int64 *v48; // rcx
  CallStackTracing *v49; // rax
  struct CallStackContext *v50; // rax
  unsigned int i; // edi
  __int64 v52; // rdx
  __int64 v53; // r8
  __int64 *v54; // rcx
  CallStackTracing *v55; // rax
  struct CallStackContext *v56; // rax
  __int64 v57; // rdx
  __int64 v58; // r8
  __int64 *v59; // rcx
  CallStackTracing *v60; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  IMFPresentationDescriptor *v62; // rcx
  int v64; // [rsp+30h] [rbp-39h] BYREF
  IMFPresentationDescriptor *ppPresentationDescriptor; // [rsp+38h] [rbp-31h] BYREF
  struct IMFStreamDescriptor *v66; // [rsp+40h] [rbp-29h] BYREF
  struct IMFStreamDescriptor *v67; // [rsp+48h] [rbp-21h] BYREF
  void *Block; // [rsp+50h] [rbp-19h] BYREF
  unsigned int v69; // [rsp+58h] [rbp-11h]
  __int64 v70; // [rsp+5Ch] [rbp-Dh]
  IMFStreamDescriptor **apStreamDescriptors; // [rsp+68h] [rbp-1h] BYREF
  DWORD v72; // [rsp+70h] [rbp+7h]
  __int64 v73; // [rsp+74h] [rbp+Bh]
  int v74; // [rsp+D0h] [rbp+67h] BYREF
  struct IMFPresentationDescriptor **v75; // [rsp+D8h] [rbp+6Fh]
  int v76; // [rsp+E0h] [rbp+77h] BYREF
  int v77; // [rsp+E8h] [rbp+7Fh] BYREF

  v75 = a2;
  v2 = 0;
  *a2 = 0;
  v64 = 0;
  v76 = 0;
  v77 = 0;
  apStreamDescriptors = 0;
  v4 = 0;
  v73 = 0;
  v5 = 0;
  v72 = 0;
  Block = 0;
  v70 = 0;
  v69 = 0;
  ppPresentationDescriptor = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v74, "CPDBinaryReader::Deserialize", 157);
  Attributes = CBinaryReader::ReadInt32((CPDBinaryReader *)((char *)this + 520), &v76);
  if ( Attributes >= 0 )
  {
    if ( (unsigned __int8)byte_1803CECE9 >= 0x10u )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 7), 28, &WPP_363825162bad371b7f2cc59a20a496c3_Traceguids, this, v76);
    if ( !v76 )
    {
      Attributes = -2147467259;
      goto LABEL_135;
    }
    Attributes = CBinaryReader::ReadInt32((CPDBinaryReader *)((char *)this + 520), &v77);
    if ( Attributes >= 0 )
    {
      if ( (unsigned __int8)byte_1803CECE9 >= 0x10u )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 7), 30, &WPP_363825162bad371b7f2cc59a20a496c3_Traceguids, this, v77);
      v18 = (CPDBinaryReader *)((char *)this + 520);
      if ( v77 )
      {
        Attributes = CDCOMInterfaceMashallerHelper::UnMarshalInterface(
                       v18,
                       &IID_IMFPresentationDescriptor,
                       (LPVOID *)&ppPresentationDescriptor);
        if ( Attributes < 0 )
        {
          v59 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v60 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v57, v58);
            CallStackTracing::s_wpInstance = v60;
            if ( v60 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v60 + 8LL))(v60, 2032) )
            {
              v59 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v59 = &qword_1803CE250;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
            }
          }
          if ( *((_BYTE *)v59 + 8) )
          {
            ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v59);
            if ( *((_DWORD *)ThreadRelativeContext + 499) != Attributes )
              CallStackContext::TraceFailure(ThreadRelativeContext, "CPDBinaryReader::Deserialize", 219, Attributes);
          }
          if ( g_wppLevels )
          {
            v12 = 39;
            goto LABEL_12;
          }
          goto LABEL_135;
        }
      }
      else
      {
        Attributes = CBinaryReader::ReadInt32(v18, &v64);
        if ( Attributes < 0 )
        {
          v21 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v19, v20);
            CallStackTracing::s_wpInstance = v22;
            if ( v22 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v22 + 8LL))(v22, 2032) )
            {
              v21 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v21 = &qword_1803CE250;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
            }
          }
          if ( *((_BYTE *)v21 + 8) )
          {
            v23 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v21);
            if ( *((_DWORD *)v23 + 499) != Attributes )
              CallStackContext::TraceFailure(v23, "CPDBinaryReader::Deserialize", 175, Attributes);
          }
          if ( g_wppLevels )
          {
            v12 = 31;
            goto LABEL_12;
          }
          goto LABEL_135;
        }
        while ( v2 < v64 )
        {
          v66 = 0;
          v74 = 0;
          Attributes = CBinaryReader::ReadInt32((CPDBinaryReader *)((char *)this + 520), &v74);
          if ( Attributes < 0 )
          {
            v33 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v34 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v24, v25);
              CallStackTracing::s_wpInstance = v34;
              if ( v34
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v34 + 8LL))(v34, 2032) )
              {
                v33 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v33 = &qword_1803CE250;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
              }
            }
            if ( *((_BYTE *)v33 + 8) )
            {
              v35 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v33);
              if ( *((_DWORD *)v35 + 499) != Attributes )
                CallStackContext::TraceFailure(v35, "CPDBinaryReader::Deserialize", 181, Attributes);
            }
            if ( g_wppLevels )
            {
              v32 = 32;
LABEL_70:
              WPP_SF_qD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                v32,
                &WPP_363825162bad371b7f2cc59a20a496c3_Traceguids,
                this,
                Attributes);
            }
LABEL_71:
            ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v66);
            goto LABEL_135;
          }
          Attributes = CPDBinaryReader::DeserializeSD(this, &v66);
          if ( Attributes < 0 )
          {
            v29 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v30 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v26, v27);
              CallStackTracing::s_wpInstance = v30;
              if ( v30
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v30 + 8LL))(v30, 2032) )
              {
                v29 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v29 = &qword_1803CE250;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
              }
            }
            if ( *((_BYTE *)v29 + 8) )
            {
              v31 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v29);
              if ( *((_DWORD *)v31 + 499) != Attributes )
                CallStackContext::TraceFailure(v31, "CPDBinaryReader::Deserialize", 183, Attributes);
            }
            if ( g_wppLevels )
            {
              v32 = 33;
              goto LABEL_70;
            }
            goto LABEL_71;
          }
          v28 = v66;
          v67 = v66;
          if ( (unsigned int)CTEntryArray<IMFStreamDescriptor *>::SetAtGrow(&apStreamDescriptors, v4, &v67) && v28 )
            ((void (__fastcall *)(struct IMFStreamDescriptor *))v28->lpVtbl->AddRef)(v28);
          if ( (unsigned int)CTEntryArray<int>::SetSize(&Block, v5 + 1) )
            *((_DWORD *)Block + v5) = v74;
          ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v66);
          v4 = v72;
          ++v2;
          v5 = v69;
        }
        Attributes = MFCreatePresentationDescriptor(v4, apStreamDescriptors, &ppPresentationDescriptor);
        if ( Attributes < 0 )
        {
          v38 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v39 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v36, v37);
            CallStackTracing::s_wpInstance = v39;
            if ( v39 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v39 + 8LL))(v39, 2032) )
            {
              v38 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v38 = &qword_1803CE250;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
            }
          }
          if ( *((_BYTE *)v38 + 8) )
          {
            v40 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v38);
            if ( *((_DWORD *)v40 + 499) != Attributes )
              CallStackContext::TraceFailure(v40, "CPDBinaryReader::Deserialize", 195, Attributes);
          }
          if ( g_wppLevels )
          {
            v12 = 34;
            goto LABEL_12;
          }
          goto LABEL_135;
        }
        if ( (unsigned __int8)byte_1803CECE9 >= 0x10u )
          WPP_SF_qq(
            *((_QWORD *)WPP_GLOBAL_Control + 7),
            35,
            &WPP_363825162bad371b7f2cc59a20a496c3_Traceguids,
            this,
            ppPresentationDescriptor);
        Attributes = CBinaryReader::ReadAttributes(
                       (CPDBinaryReader *)((char *)this + 520),
                       (IMFAttributes *)ppPresentationDescriptor);
        if ( Attributes < 0 )
        {
          v43 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v44 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v41, v42);
            CallStackTracing::s_wpInstance = v44;
            if ( v44 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v44 + 8LL))(v44, 2032) )
            {
              v43 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v43 = &qword_1803CE250;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
            }
          }
          if ( *((_BYTE *)v43 + 8) )
          {
            v45 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v43);
            if ( *((_DWORD *)v45 + 499) != Attributes )
              CallStackContext::TraceFailure(v45, "CPDBinaryReader::Deserialize", 203, Attributes);
          }
          if ( g_wppLevels )
          {
            v12 = 36;
            goto LABEL_12;
          }
          goto LABEL_135;
        }
        Attributes = CBinaryReader::ReadUnknownAttributes(
                       (CPDBinaryReader *)((char *)this + 520),
                       (struct IMFAttributes *)ppPresentationDescriptor);
        if ( Attributes < 0 )
        {
          v48 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v49 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v46, v47);
            CallStackTracing::s_wpInstance = v49;
            if ( v49 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v49 + 8LL))(v49, 2032) )
            {
              v48 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v48 = &qword_1803CE250;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
            }
          }
          if ( *((_BYTE *)v48 + 8) )
          {
            v50 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v48);
            if ( *((_DWORD *)v50 + 499) != Attributes )
              CallStackContext::TraceFailure(v50, "CPDBinaryReader::Deserialize", 204, Attributes);
          }
          if ( g_wppLevels )
          {
            v12 = 37;
            goto LABEL_12;
          }
          goto LABEL_135;
        }
        for ( i = 0; i < v64; ++i )
        {
          if ( *((_DWORD *)Block + i) )
          {
            Attributes = ((__int64 (__fastcall *)(IMFPresentationDescriptor *, _QWORD))ppPresentationDescriptor->lpVtbl->SelectStream)(
                           ppPresentationDescriptor,
                           i);
            if ( Attributes < 0 )
            {
              v54 = (__int64 *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v55 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v52, v53);
                CallStackTracing::s_wpInstance = v55;
                if ( v55
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v55 + 8LL))(v55, 2032) )
                {
                  v54 = (__int64 *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v54 = &qword_1803CE250;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
                }
              }
              if ( *((_BYTE *)v54 + 8) )
              {
                v56 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v54);
                if ( *((_DWORD *)v56 + 499) != Attributes )
                  CallStackContext::TraceFailure(v56, "CPDBinaryReader::Deserialize", 213, Attributes);
              }
              if ( g_wppLevels )
              {
                v12 = 38;
                goto LABEL_12;
              }
              goto LABEL_135;
            }
          }
        }
      }
      v62 = ppPresentationDescriptor;
      *v75 = ppPresentationDescriptor;
      ((void (__fastcall *)(IMFPresentationDescriptor *))v62->lpVtbl->AddRef)(v62);
      goto LABEL_135;
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
      if ( *((_DWORD *)v17 + 499) != Attributes )
        CallStackContext::TraceFailure(v17, "CPDBinaryReader::Deserialize", 166, Attributes);
    }
    if ( g_wppLevels )
    {
      v12 = 29;
      goto LABEL_12;
    }
  }
  else
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
      v11 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v9);
      if ( *((_DWORD *)v11 + 499) != Attributes )
        CallStackContext::TraceFailure(v11, "CPDBinaryReader::Deserialize", 157, Attributes);
    }
    if ( g_wppLevels )
    {
      v12 = 27;
LABEL_12:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v12,
        &WPP_363825162bad371b7f2cc59a20a496c3_Traceguids,
        this,
        Attributes);
    }
  }
LABEL_135:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v74);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&ppPresentationDescriptor);
  operator delete(Block);
  CTUnkArray<IMFStreamDescriptor>::~CTUnkArray<IMFStreamDescriptor>(&apStreamDescriptors);
  return (unsigned int)Attributes;
}

```

## disassembly

```asm
0x1801e7a50  mov     [rsp-8+arg_8], rdx
0x1801e7a55  push    rbp
0x1801e7a56  push    rbx
0x1801e7a57  push    rsi
0x1801e7a58  push    rdi
0x1801e7a59  push    r12
0x1801e7a5b  push    r13
0x1801e7a5d  push    r14
0x1801e7a5f  push    r15
0x1801e7a61  lea     rbp, [rsp-1Fh]
0x1801e7a66  sub     rsp, 88h
0x1801e7a6d  xor     r14d, r14d
0x1801e7a70  mov     r15, rcx
0x1801e7a73  mov     [rdx], r14
0x1801e7a76  lea     rcx, [rbp+57h+arg_0]; this
0x1801e7a7a  mov     esi, 9Dh
0x1801e7a7f  mov     [rbp+57h+var_90], r14d
0x1801e7a83  lea     rdx, aCpdbinaryreade_0; "CPDBinaryReader::Deserialize"
0x1801e7a8a  mov     [rbp+57h+arg_10], r14d
0x1801e7a8e  mov     r8d, esi; int
0x1801e7a91  mov     [rbp+57h+arg_18], r14d
0x1801e7a95  mov     [rbp+57h+apStreamDescriptors], r14
0x1801e7a99  mov     r12d, r14d
0x1801e7a9c  mov     [rbp+57h+var_4C], r14
0x1801e7aa0  mov     r13d, r14d
0x1801e7aa3  mov     [rbp+57h+var_50], r14d
0x1801e7aa7  mov     [rbp+57h+Block], r14
0x1801e7aab  mov     [rbp+57h+var_64], r14
0x1801e7aaf  mov     [rbp+57h+var_68], r14d
0x1801e7ab3  mov     [rbp+57h+ppPresentationDescriptor], r14
0x1801e7ab7  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1801e7abc  lea     rdi, [r15+208h]
0x1801e7ac3  mov     rcx, rdi; this
0x1801e7ac6  lea     rdx, [rbp+57h+arg_10]; int *
0x1801e7aca  call    ?ReadInt32@CBinaryReader@@QEAAJAEAJ@Z; CBinaryReader::ReadInt32(long &)
0x1801e7acf  mov     ebx, eax
0x1801e7ad1  test    eax, eax
0x1801e7ad3  jns     loc_1801E7B8A
0x1801e7ad9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801e7ae0  test    rcx, rcx
0x1801e7ae3  jnz     short loc_1801E7B2D
0x1801e7ae5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801e7aec  nop     dword ptr [rax+rax+00h]
0x1801e7af1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801e7af8  mov     rcx, rax
0x1801e7afb  test    rax, rax
0x1801e7afe  jz      short loc_1801E7B1F
0x1801e7b00  mov     rax, [rax]
0x1801e7b03  mov     edx, 7F0h
0x1801e7b08  mov     rax, [rax+8]
0x1801e7b0c  call    cs:__guard_dispatch_icall_fptr
0x1801e7b12  test    eax, eax
0x1801e7b14  jz      short loc_1801E7B1F
0x1801e7b16  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801e7b1d  jmp     short loc_1801E7B2D
0x1801e7b1f  lea     rcx, qword_1803CE250; this
0x1801e7b26  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801e7b2d  cmp     [rcx+8], r14b
0x1801e7b31  jz      short loc_1801E7B55
0x1801e7b33  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801e7b38  cmp     [rax+7CCh], ebx
0x1801e7b3e  jz      short loc_1801E7B55
0x1801e7b40  mov     r9d, ebx; int
0x1801e7b43  lea     rdx, aCpdbinaryreade_0; "CPDBinaryReader::Deserialize"
0x1801e7b4a  mov     r8d, esi; int
0x1801e7b4d  mov     rcx, rax; this
0x1801e7b50  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801e7b55  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801e7b5c  jb      loc_1801E8322
0x1801e7b62  mov     edx, 1Bh
0x1801e7b67  lea     r8, WPP_363825162bad371b7f2cc59a20a496c3_Traceguids
0x1801e7b6e  mov     rcx, cs:WPP_GLOBAL_Control
0x1801e7b75  mov     r9, r15
0x1801e7b78  mov     dword ptr [rsp+0C0h+var_A0], ebx
0x1801e7b7c  mov     rcx, [rcx+10h]
0x1801e7b80  call    WPP_SF_qD
0x1801e7b85  jmp     loc_1801E8322
0x1801e7b8a  cmp     cs:byte_1803CECE9, 10h
0x1801e7b91  lea     rsi, WPP_363825162bad371b7f2cc59a20a496c3_Traceguids
0x1801e7b98  jb      short loc_1801E7BBC
0x1801e7b9a  mov     rcx, cs:WPP_GLOBAL_Control
0x1801e7ba1  mov     edx, 1Ch
0x1801e7ba6  mov     eax, [rbp+57h+arg_10]
0x1801e7ba9  mov     r9, r15
0x1801e7bac  mov     r8, rsi
0x1801e7baf  mov     dword ptr [rsp+0C0h+var_A0], eax
0x1801e7bb3  mov     rcx, [rcx+38h]
0x1801e7bb7  call    WPP_SF_qD
0x1801e7bbc  cmp     [rbp+57h+arg_10], r14d
0x1801e7bc0  jz      loc_1801E831D
0x1801e7bc6  lea     rdx, [rbp+57h+arg_18]; int *
0x1801e7bca  mov     rcx, rdi; this
0x1801e7bcd  call    ?ReadInt32@CBinaryReader@@QEAAJAEAJ@Z; CBinaryReader::ReadInt32(long &)
0x1801e7bd2  mov     ebx, eax
0x1801e7bd4  test    eax, eax
0x1801e7bd6  jns     loc_1801E7C75
0x1801e7bdc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801e7be3  test    rcx, rcx
0x1801e7be6  jnz     short loc_1801E7C30
0x1801e7be8  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801e7bef  nop     dword ptr [rax+rax+00h]
0x1801e7bf4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801e7bfb  mov     rcx, rax
0x1801e7bfe  test    rax, rax
0x1801e7c01  jz      short loc_1801E7C22
0x1801e7c03  mov     rax, [rax]
0x1801e7c06  mov     edx, 7F0h
0x1801e7c0b  mov     rax, [rax+8]
0x1801e7c0f  call    cs:__guard_dispatch_icall_fptr
0x1801e7c15  test    eax, eax
0x1801e7c17  jz      short loc_1801E7C22
0x1801e7c19  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801e7c20  jmp     short loc_1801E7C30
0x1801e7c22  lea     rcx, qword_1803CE250; this
0x1801e7c29  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801e7c30  cmp     [rcx+8], r14b
0x1801e7c34  jz      short loc_1801E7C5B
0x1801e7c36  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801e7c3b  cmp     [rax+7CCh], ebx
0x1801e7c41  jz      short loc_1801E7C5B
0x1801e7c43  mov     r9d, ebx; int
0x1801e7c46  lea     rdx, aCpdbinaryreade_0; "CPDBinaryReader::Deserialize"
0x1801e7c4d  mov     r8d, 0A6h; int
0x1801e7c53  mov     rcx, rax; this
0x1801e7c56  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801e7c5b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801e7c62  jb      loc_1801E8322
0x1801e7c68  mov     edx, 1Dh
0x1801e7c6d  mov     r8, rsi
0x1801e7c70  jmp     loc_1801E7B6E
0x1801e7c75  cmp     cs:byte_1803CECE9, 10h
0x1801e7c7c  jb      short loc_1801E7CA0
0x1801e7c7e  mov     rcx, cs:WPP_GLOBAL_Control
0x1801e7c85  mov     edx, 1Eh
0x1801e7c8a  mov     eax, [rbp+57h+arg_18]
0x1801e7c8d  mov     r9, r15
0x1801e7c90  mov     r8, rsi
0x1801e7c93  mov     dword ptr [rsp+0C0h+var_A0], eax
0x1801e7c97  mov     rcx, [rcx+38h]
0x1801e7c9b  call    WPP_SF_qD
0x1801e7ca0  mov     rcx, rdi; this
0x1801e7ca3  cmp     [rbp+57h+arg_18], r14d
0x1801e7ca7  jnz     loc_1801E8257
0x1801e7cad  lea     rdx, [rbp+57h+var_90]; int *
0x1801e7cb1  call    ?ReadInt32@CBinaryReader@@QEAAJAEAJ@Z; CBinaryReader::ReadInt32(long &)
0x1801e7cb6  mov     ebx, eax
0x1801e7cb8  test    eax, eax
0x1801e7cba  jns     loc_1801E7D56
0x1801e7cc0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801e7cc7  test    rcx, rcx
0x1801e7cca  jnz     short loc_1801E7D14
0x1801e7ccc  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801e7cd3  nop     dword ptr [rax+rax+00h]
0x1801e7cd8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801e7cdf  mov     rcx, rax
0x1801e7ce2  test    rax, rax
0x1801e7ce5  jz      short loc_1801E7D06
0x1801e7ce7  mov     rax, [rax]
0x1801e7cea  mov     edx, 7F0h
0x1801e7cef  mov     rax, [rax+8]
0x1801e7cf3  call    cs:__guard_dispatch_icall_fptr
0x1801e7cf9  test    eax, eax
0x1801e7cfb  jz      short loc_1801E7D06
0x1801e7cfd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801e7d04  jmp     short loc_1801E7D14
0x1801e7d06  lea     rcx, qword_1803CE250; this
0x1801e7d0d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801e7d14  cmp     [rcx+8], r14b
0x1801e7d18  jz      short loc_1801E7D3F
0x1801e7d1a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801e7d1f  cmp     [rax+7CCh], ebx
0x1801e7d25  jz      short loc_1801E7D3F
0x1801e7d27  mov     r9d, ebx; int
0x1801e7d2a  lea     rdx, aCpdbinaryreade_0; "CPDBinaryReader::Deserialize"
0x1801e7d31  mov     r8d, 0AFh; int
0x1801e7d37  mov     rcx, rax; this
0x1801e7d3a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801e7d3f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801e7d46  jb      loc_1801E8322
0x1801e7d4c  mov     edx, 1Fh
0x1801e7d51  jmp     loc_1801E7C6D
0x1801e7d56  cmp     r14d, [rbp+57h+var_90]
0x1801e7d5a  jnb     loc_1801E7F4A
0x1801e7d60  lea     rdx, [rbp+57h+arg_0]; int *
0x1801e7d64  mov     [rbp+57h+var_80], 0
0x1801e7d6c  mov     rcx, rdi; this
0x1801e7d6f  mov     [rbp+57h+arg_0], 0
0x1801e7d76  call    ?ReadInt32@CBinaryReader@@QEAAJAEAJ@Z; CBinaryReader::ReadInt32(long &)
0x1801e7d7b  mov     ebx, eax
0x1801e7d7d  test    eax, eax
0x1801e7d7f  js      loc_1801E7E95
0x1801e7d85  lea     rdx, [rbp+57h+var_80]; struct IMFStreamDescriptor **
0x1801e7d89  mov     rcx, r15; this
0x1801e7d8c  call    ?DeserializeSD@CPDBinaryReader@@QEAAJPEAPEAUIMFStreamDescriptor@@@Z; CPDBinaryReader::DeserializeSD(IMFStreamDescriptor * *)
0x1801e7d91  mov     ebx, eax
0x1801e7d93  test    eax, eax
0x1801e7d95  js      short loc_1801E7DFF
0x1801e7d97  mov     rbx, [rbp+57h+var_80]
0x1801e7d9b  lea     r8, [rbp+57h+var_78]
0x1801e7d9f  mov     edx, r12d
0x1801e7da2  mov     [rbp+57h+var_78], rbx
0x1801e7da6  lea     rcx, [rbp+57h+apStreamDescriptors]
0x1801e7daa  call    ?SetAtGrow@?$CTEntryArray@PEAUIMFStreamDescriptor@@@@QEAAHKAEBQEAUIMFStreamDescriptor@@@Z; CTEntryArray<IMFStreamDescriptor *>::SetAtGrow(ulong,IMFStreamDescriptor * const &)
0x1801e7daf  test    eax, eax
0x1801e7db1  jz      short loc_1801E7DC8
0x1801e7db3  test    rbx, rbx
0x1801e7db6  jz      short loc_1801E7DC8
0x1801e7db8  mov     rax, [rbx]
0x1801e7dbb  mov     rcx, rbx
0x1801e7dbe  mov     rax, [rax+8]
0x1801e7dc2  call    cs:__guard_dispatch_icall_fptr
0x1801e7dc8  lea     edx, [r13+1]
0x1801e7dcc  lea     rcx, [rbp+57h+Block]
0x1801e7dd0  call    ?SetSize@?$CTEntryArray@H@@QEAAHKK@Z; CTEntryArray<int>::SetSize(ulong,ulong)
0x1801e7dd5  test    eax, eax
0x1801e7dd7  jz      short loc_1801E7DE6
0x1801e7dd9  mov     rdx, [rbp+57h+Block]
0x1801e7ddd  mov     eax, [rbp+57h+arg_0]
0x1801e7de0  mov     ecx, r13d
0x1801e7de3  mov     [rdx+rcx*4], eax
0x1801e7de6  lea     rcx, [rbp+57h+var_80]
0x1801e7dea  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x1801e7def  mov     r12d, [rbp+57h+var_50]
0x1801e7df3  inc     r14d
0x1801e7df6  mov     r13d, [rbp+57h+var_68]
0x1801e7dfa  jmp     loc_1801E7D56
0x1801e7dff  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801e7e06  test    rcx, rcx
0x1801e7e09  jnz     short loc_1801E7E53
0x1801e7e0b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801e7e12  nop     dword ptr [rax+rax+00h]
0x1801e7e17  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801e7e1e  mov     rcx, rax
0x1801e7e21  test    rax, rax
0x1801e7e24  jz      short loc_1801E7E45
0x1801e7e26  mov     rax, [rax]
0x1801e7e29  mov     edx, 7F0h
0x1801e7e2e  mov     rax, [rax+8]
0x1801e7e32  call    cs:__guard_dispatch_icall_fptr
0x1801e7e38  test    eax, eax
0x1801e7e3a  jz      short loc_1801E7E45
0x1801e7e3c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801e7e43  jmp     short loc_1801E7E53
0x1801e7e45  lea     rcx, qword_1803CE250; this
0x1801e7e4c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801e7e53  cmp     byte ptr [rcx+8], 0
0x1801e7e57  jz      short loc_1801E7E7E
0x1801e7e59  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801e7e5e  cmp     [rax+7CCh], ebx
0x1801e7e64  jz      short loc_1801E7E7E
0x1801e7e66  mov     r9d, ebx; int
0x1801e7e69  lea     rdx, aCpdbinaryreade_0; "CPDBinaryReader::Deserialize"
0x1801e7e70  mov     r8d, 0B7h; int
0x1801e7e76  mov     rcx, rax; this
0x1801e7e79  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801e7e7e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801e7e85  jb      loc_1801E7F3C
0x1801e7e8b  mov     edx, 21h ; '!'
0x1801e7e90  jmp     loc_1801E7F22
0x1801e7e95  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801e7e9c  test    rcx, rcx
0x1801e7e9f  jnz     short loc_1801E7EE9
0x1801e7ea1  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801e7ea8  nop     dword ptr [rax+rax+00h]
0x1801e7ead  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801e7eb4  mov     rcx, rax
0x1801e7eb7  test    rax, rax
0x1801e7eba  jz      short loc_1801E7EDB
0x1801e7ebc  mov     rax, [rax]
0x1801e7ebf  mov     edx, 7F0h
0x1801e7ec4  mov     rax, [rax+8]
0x1801e7ec8  call    cs:__guard_dispatch_icall_fptr
0x1801e7ece  test    eax, eax
0x1801e7ed0  jz      short loc_1801E7EDB
0x1801e7ed2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801e7ed9  jmp     short loc_1801E7EE9
0x1801e7edb  lea     rcx, qword_1803CE250; this
0x1801e7ee2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801e7ee9  cmp     byte ptr [rcx+8], 0
0x1801e7eed  jz      short loc_1801E7F14
0x1801e7eef  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801e7ef4  cmp     [rax+7CCh], ebx
0x1801e7efa  jz      short loc_1801E7F14
0x1801e7efc  mov     r9d, ebx; int
0x1801e7eff  lea     rdx, aCpdbinaryreade_0; "CPDBinaryReader::Deserialize"
0x1801e7f06  mov     r8d, 0B5h; int
0x1801e7f0c  mov     rcx, rax; this
0x1801e7f0f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801e7f14  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801e7f1b  jb      short loc_1801E7F3C
0x1801e7f1d  mov     edx, 20h ; ' '
0x1801e7f22  mov     rcx, cs:WPP_GLOBAL_Control
0x1801e7f29  mov     r9, r15
0x1801e7f2c  mov     r8, rsi
0x1801e7f2f  mov     dword ptr [rsp+0C0h+var_A0], ebx
0x1801e7f33  mov     rcx, [rcx+10h]
0x1801e7f37  call    WPP_SF_qD
0x1801e7f3c  lea     rcx, [rbp+57h+var_80]
0x1801e7f40  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x1801e7f45  jmp     loc_1801E8322
  ... truncated ...
```
