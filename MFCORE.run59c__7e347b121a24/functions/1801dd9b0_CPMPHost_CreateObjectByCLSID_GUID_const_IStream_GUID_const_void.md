# CPMPHost::CreateObjectByCLSID(_GUID const &,IStream *,_GUID const &,void * *)

- ea: `0x1801dd9b0`
- end: `0x1801de650`
- name: `?CreateObjectByCLSID@CPMPHost@@UEAAJAEBU_GUID@@PEAUIStream@@0PEAPEAX@Z`
- size: `3232`
- prototype: `int(CPMPHost *__hidden this, const struct _GUID *, struct IStream *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `23`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18002fee0`
- `0x18003ecb0`
- `0x1800402c0`
- `0x18004d118`
- `0x180050d6c`
- `0x180063f00`
- `0x18007626c`
- `0x180093088`
- `0x1800ec0e0`
- `0x18012add8`
- `0x1801a5230`
- `0x1801dd9b0`
- `0x1801efeec`
- `0x180258480`
- `0x18029b110`
- `0x18029cc4c`
- `0x18029dc10`
- `0x18029df58`
- `0x18029dfc8`
- `0x1802b5328`
- `0x180325540`
- `0x1803255cc`
- `0x180344d40`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801ddf20`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801ddf75`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801ddf20`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801ddf75`
- `api-ms-win-core-com-l1-1-0!CoUnmarshalInterface` at `0x1801de2ca`
- `api-ms-win-core-com-l1-1-0!CoUnmarshalInterface` at `0x1801de383`
- `api-ms-win-core-com-l1-1-0!CoUnmarshalInterface` at `0x1801de2ca`
- `api-ms-win-core-com-l1-1-0!CoUnmarshalInterface` at `0x1801de383`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801ddacb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801ddbba`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801ddc6d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801ddd22`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801dde01`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801ddfbd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801de079`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801de159`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801de210`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801de2ec`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801de3a5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801de455`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801de50a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801ddacb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801ddbba`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801ddc6d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801ddd22`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801dde01`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801ddfbd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801de079`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801de159`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801de210`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801de2ec`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801de3a5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801de455`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801de50a`

## string_xrefs

- `0x1801dd9db`: `CPMPHost::CreateObjectByCLSID`
- `0x1801dde5f`: `CPMPHost::CreateObjectByCLSID`
- `0x1801de01b`: `CPMPHost::CreateObjectByCLSID`
- `0x1801de0d7`: `CPMPHost::CreateObjectByCLSID`
- `0x1801de1b7`: `CPMPHost::CreateObjectByCLSID`
- `0x1801de26e`: `CPMPHost::CreateObjectByCLSID`

## pseudocode

```c
__int64 __fastcall CPMPHost::CreateObjectByCLSID(
        CPMPHost *this,
        const struct _GUID *a2,
        struct IStream *a3,
        struct IMFMediaStream *a4,
        void **a5)
{
  struct IMFMediaStream *v8; // r13
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rcx
  char *v12; // r14
  __int64 v13; // rdx
  int String; // ebx
  __int64 v15; // r8
  __int64 *v16; // rcx
  CallStackTracing *v17; // rax
  struct CallStackContext *v18; // rax
  __int64 v19; // rdx
  __int64 v20; // rdx
  __int64 v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 *v24; // rcx
  CallStackTracing *v25; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v27; // rdx
  __int64 v28; // r8
  __int64 *v29; // rcx
  CallStackTracing *v30; // rax
  struct CallStackContext *v31; // rax
  __int64 v32; // rdx
  __int64 v33; // r8
  __int64 *v34; // rcx
  CallStackTracing *v35; // rax
  struct CallStackContext *v36; // rax
  __int64 v37; // rax
  char *v38; // r12
  __int64 v39; // rdx
  __int64 v40; // r8
  __int64 *v41; // rcx
  CallStackTracing *v42; // rax
  struct CallStackContext *v43; // rax
  __int64 v44; // rdx
  const unsigned __int16 *v45; // r15
  int v46; // r13d
  int v47; // ebx
  int v48; // r14d
  __int64 v49; // rdx
  const WCHAR *v50; // r8
  int v51; // ecx
  __int64 v52; // rdx
  __int64 v53; // r8
  __int64 *v54; // rcx
  CallStackTracing *v55; // rax
  struct CallStackContext *v56; // rax
  __int64 v57; // rdx
  __int64 v58; // r8
  __int64 *v59; // rcx
  CallStackTracing *v60; // rax
  struct CallStackContext *v61; // rax
  __int64 v62; // rdx
  __int64 v63; // r8
  __int64 *v64; // rcx
  CallStackTracing *v65; // rax
  struct CallStackContext *v66; // rax
  __int64 v67; // rdx
  __int64 v68; // r8
  __int64 *v69; // rcx
  CallStackTracing *v70; // rax
  struct CallStackContext *v71; // rax
  __int64 v72; // rdx
  __int64 v73; // r8
  __int64 *v74; // rcx
  CallStackTracing *v75; // rax
  struct CallStackContext *v76; // rax
  __int64 v77; // rdx
  __int64 v78; // rdx
  __int64 v79; // r8
  __int64 *v80; // rcx
  CallStackTracing *v81; // rax
  struct CallStackContext *v82; // rax
  __int64 v83; // rdx
  __int64 v84; // r8
  __int64 *v85; // rcx
  CallStackTracing *v86; // rax
  struct CallStackContext *v87; // rax
  __int64 v88; // rdx
  __int64 v89; // r8
  __int64 *v90; // rcx
  CallStackTracing *v91; // rax
  struct CallStackContext *v92; // rax
  __int64 v93; // rax
  __int64 v94; // rax
  __int64 v95; // rcx
  LPVOID ppv; // [rsp+30h] [rbp-71h] BYREF
  struct IMFMediaStream *v98; // [rsp+38h] [rbp-69h] BYREF
  struct IMFSequencerRemoteStreamCallback *v99; // [rsp+40h] [rbp-61h] BYREF
  _BYTE v100[8]; // [rsp+48h] [rbp-59h] BYREF
  int v101; // [rsp+50h] [rbp-51h] BYREF
  __int64 v102; // [rsp+54h] [rbp-4Dh]
  int v103; // [rsp+5Ch] [rbp-45h]
  __int64 v104; // [rsp+60h] [rbp-41h]
  _BYTE v105[16]; // [rsp+68h] [rbp-39h] BYREF
  void **v106; // [rsp+78h] [rbp-29h]
  const struct _GUID *v107; // [rsp+80h] [rbp-21h]
  HSTRING v108[4]; // [rsp+88h] [rbp-19h] BYREF

  v101 &= 0xFFFFFFF8;
  v107 = a2;
  v98 = a4;
  v106 = a5;
  v102 = 0;
  v104 = 0;
  v103 = 0;
  v8 = a4;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v100, "CPMPHost::CreateObjectByCLSID", 1256);
  if ( (unsigned __int8)byte_1803CECE9 >= 8u )
    WPP_SF_qq(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      77,
      &WPP_1ede33fc6d933efc25e43a6be7416609_Traceguids,
      (char *)this - 8,
      a3);
  v9 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&CLSID_SequencerSourceRemoteStream.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&CLSID_SequencerSourceRemoteStream.Data1 )
    v9 = *(_QWORD *)a2->Data4 - *(_QWORD *)CLSID_SequencerSourceRemoteStream.Data4;
  if ( v9 )
  {
    v10 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&CLSID_CreateMediaExtensionObject.Data1;
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&CLSID_CreateMediaExtensionObject.Data1 )
      v10 = *(_QWORD *)a2->Data4 - *(_QWORD *)CLSID_CreateMediaExtensionObject.Data4;
    if ( v10 )
    {
      v11 = *((_QWORD *)this + 10);
      v12 = (char *)this - 8;
      ppv = 0;
      v98 = 0;
      String = CPMPComponentCreator::CreateObject((CPMPComponentCreator *)(v11 + 16), a2, (struct _GUID *)v8, &ppv);
      if ( String >= 0 )
      {
        if ( !a3 )
          goto LABEL_45;
        String = (**(__int64 (__fastcall ***)(LPVOID, GUID *, struct IMFMediaStream **))ppv)(
                   ppv,
                   &IID_IPersistStream,
                   &v98);
        if ( String < 0 )
        {
          v24 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v22, v23);
            CallStackTracing::s_wpInstance = v25;
            if ( v25 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
            {
              v24 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v24 = &qword_1803CE250;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
            }
          }
          if ( *((_BYTE *)v24 + 8) )
          {
            ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v24);
            if ( *((_DWORD *)ThreadRelativeContext + 499) != String )
              CallStackContext::TraceFailure(ThreadRelativeContext, "CPMPHost::CreateObjectByCLSID", 1268, String);
          }
          if ( !g_wppLevels )
            goto LABEL_21;
          v19 = 79;
          goto LABEL_20;
        }
        String = ((__int64 (__fastcall *)(struct IMFMediaStream *, struct IStream *))v98->lpVtbl->EndGetEvent)(v98, a3);
        if ( String < 0 )
        {
          v29 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v30 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v27, v28);
            CallStackTracing::s_wpInstance = v30;
            if ( v30 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v30 + 8LL))(v30, 2032) )
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
            if ( *((_DWORD *)v31 + 499) != String )
              CallStackContext::TraceFailure(v31, "CPMPHost::CreateObjectByCLSID", 1270, String);
          }
          if ( !g_wppLevels )
            goto LABEL_21;
          v19 = 80;
        }
        else
        {
LABEL_45:
          String = (**(__int64 (__fastcall ***)(LPVOID, struct IMFMediaStream *, void **))ppv)(ppv, v8, a5);
          if ( String >= 0 )
            goto LABEL_21;
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
            if ( *((_DWORD *)v36 + 499) != String )
              CallStackContext::TraceFailure(v36, "CPMPHost::CreateObjectByCLSID", 1273, String);
          }
          if ( !g_wppLevels )
            goto LABEL_21;
          v19 = 81;
        }
      }
      else
      {
        v16 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v17 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v13, v15);
          CallStackTracing::s_wpInstance = v17;
          if ( v17 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v17 + 8LL))(v17, 2032) )
          {
            v16 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v16 = &qword_1803CE250;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
          }
        }
        if ( *((_BYTE *)v16 + 8) )
        {
          v18 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v16);
          if ( *((_DWORD *)v18 + 499) != String )
            CallStackContext::TraceFailure(v18, "CPMPHost::CreateObjectByCLSID", 1264, String);
        }
        if ( !g_wppLevels )
          goto LABEL_21;
        v19 = 78;
      }
LABEL_20:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v19, &WPP_1ede33fc6d933efc25e43a6be7416609_Traceguids, v12, String);
LABEL_21:
      ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v98);
      ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&ppv);
      goto LABEL_182;
    }
  }
  v37 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&CLSID_CreateMediaExtensionObject.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&CLSID_CreateMediaExtensionObject.Data1 )
    v37 = *(_QWORD *)a2->Data4 - *(_QWORD *)CLSID_CreateMediaExtensionObject.Data4;
  if ( !v37 )
  {
    CStreamReader::CStreamReader((CStreamReader *)v105, a3, 0);
    ppv = 0;
    v99 = 0;
    v38 = (char *)this - 8;
    String = CStreamReader::ReadString((CBinaryReader *)v105);
    if ( String >= 0 )
    {
      v45 = (const unsigned __int16 *)CMFBaseStringT<unsigned short>::PContents(&v101);
      Windows::Internal::StringReference::_ConstructorHelper((Windows::Internal::StringReference *)v108, v45);
      if ( (unsigned int)CPMPHost::TryActivateObjectFromStoreContext(
                           (CPMPHost *)((char *)this - 8),
                           v108[0],
                           (struct IInspectable **)&ppv) )
      {
        v46 = v102;
        if ( (int)v102 < 0 || SHIDWORD(v102) < 8 || (v47 = 0, CompareStringOrdinal(v45, 8, L"Windows.", 8, 1) != 2) )
          v47 = 1;
        v48 = 0;
        while ( !v47 )
        {
          v49 = -1;
          v50 = off_180357BA0[v48];
          do
            ++v49;
          while ( v50[v49] );
          v51 = HIDWORD(v102);
          if ( v46 < 0 )
            v51 = 0;
          if ( v51 >= (int)v49 && CompareStringOrdinal(v45, v49, v50, v49, 1) == 2 )
            v47 = 1;
          if ( ++v48 )
          {
            if ( !v47 )
            {
              String = MF::OriginateError((MF *)0x80070005LL, v49);
              if ( String < 0 )
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
                  if ( *((_DWORD *)v56 + 499) != String )
                    CallStackContext::TraceFailure(v56, "CPMPHost::CreateObjectByCLSID", 1314, String);
                }
                if ( g_wppLevels )
                {
                  v44 = 83;
                  goto LABEL_70;
                }
                goto LABEL_71;
              }
            }
            break;
          }
        }
        Windows::Internal::StringReference::_ConstructorHelper((Windows::Internal::StringReference *)v108, v45);
        String = Windows::Foundation::ActivateInstance<IInspectable>(v108[0], &ppv);
        if ( String >= 0 )
        {
          v8 = v98;
          goto LABEL_111;
        }
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
          v61 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v59);
          if ( *((_DWORD *)v61 + 499) != String )
            CallStackContext::TraceFailure(v61, "CPMPHost::CreateObjectByCLSID", 1317, String);
        }
        if ( g_wppLevels )
        {
          v44 = 84;
          goto LABEL_70;
        }
        goto LABEL_71;
      }
LABEL_111:
      if ( (**(int (__fastcall ***)(LPVOID, GUID *, struct IMFSequencerRemoteStreamCallback **))ppv)(
             ppv,
             &GUID_00000109_0000_0000_c000_000000000046,
             &v99) < 0
        || (String = (*(__int64 (__fastcall **)(struct IMFSequencerRemoteStreamCallback *, struct IStream *))(*(_QWORD *)v99 + 40LL))(
                       v99,
                       a3),
            String >= 0) )
      {
        String = (**(__int64 (__fastcall ***)(LPVOID, struct IMFMediaStream *, void **))ppv)(ppv, v8, v106);
        if ( String >= 0 )
          goto LABEL_71;
        v69 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v70 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v67, v68);
          CallStackTracing::s_wpInstance = v70;
          if ( v70 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v70 + 8LL))(v70, 2032) )
          {
            v69 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v69 = &qword_1803CE250;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
          }
        }
        if ( *((_BYTE *)v69 + 8) )
        {
          v71 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v69);
          if ( *((_DWORD *)v71 + 499) != String )
            CallStackContext::TraceFailure(v71, "CPMPHost::CreateObjectByCLSID", 1324, String);
        }
        if ( !g_wppLevels )
          goto LABEL_71;
        v44 = 86;
      }
      else
      {
        v64 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v65 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v62, v63);
          CallStackTracing::s_wpInstance = v65;
          if ( v65 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v65 + 8LL))(v65, 2032) )
          {
            v64 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v64 = &qword_1803CE250;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
          }
        }
        if ( *((_BYTE *)v64 + 8) )
        {
          v66 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v64);
          if ( *((_DWORD *)v66 + 499) != String )
            CallStackContext::TraceFailure(v66, "CPMPHost::CreateObjectByCLSID", 1321, String);
        }
        if ( !g_wppLevels )
          goto LABEL_71;
        v44 = 85;
      }
    }
    else
    {
      v41 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v42 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v39, v40);
        CallStackTracing::s_wpInstance = v42;
        if ( v42 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v42 + 8LL))(v42, 2032) )
        {
          v41 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v41 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v41 + 8) )
      {
        v43 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v41);
        if ( *((_DWORD *)v43 + 499) != String )
          CallStackContext::TraceFailure(v43, "CPMPHost::CreateObjectByCLSID", 1284, String);
      }
      if ( !g_wppLevels )
        goto LABEL_71;
      v44 = 82;
    }
LABEL_70:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v44, &WPP_1ede33fc6d933efc25e43a6be7416609_Traceguids, v38, String);
LABEL_71:
    ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v99);
    ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&ppv);
    CStreamReader::~CStreamReader((CStreamReader *)v105);
    goto LABEL_182;
  }
  v98 = 0;
  ppv = 0;
  v99 = 0;
  if ( a3 )
  {
    String = CoUnmarshalInterface(a3, &IID_IMFMediaStream, &ppv);
    if ( String >= 0 )
    {
      String = CoUnmarshalInterface(a3, &IID_IMFSequencerRemoteStreamCallback, (LPVOID *)&v99);
      if ( String >= 0 )
      {
        String = CSeqSourceRemoteStream::CreateInstance((struct IMFMediaStream *)ppv, v99, &v98);
        if ( String >= 0 )
        {
          String = ((__int64 (__fastcall *)(struct IMFMediaStream *, struct IMFMediaStream *, void **))v98->lpVtbl->QueryInterface)(
                     v98,
                     v8,
                     a5);
          if ( String >= 0 )
            goto LABEL_181;
          v90 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v91 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v88, v89);
            CallStackTracing::s_wpInstance = v91;
            if ( v91 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v91 + 8LL))(v91, 2032) )
            {
              v90 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v90 = &qword_1803CE250;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
            }
          }
          if ( *((_BYTE *)v90 + 8) )
          {
            v92 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v90);
            if ( *((_DWORD *)v92 + 499) != String )
              CallStackContext::TraceFailure(v92, "CPMPHost::CreateObjectByCLSID", 1344, String);
          }
          if ( !g_wppLevels )
            goto LABEL_181;
          v77 = 90;
        }
        else
        {
          v85 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v86 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v83, v84);
            CallStackTracing::s_wpInstance = v86;
            if ( v86 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v86 + 8LL))(v86, 2032) )
            {
              v85 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v85 = &qword_1803CE250;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
            }
          }
          if ( *((_BYTE *)v85 + 8) )
          {
            v87 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v85);
            if ( *((_DWORD *)v87 + 499) != String )
              CallStackContext::TraceFailure(v87, "CPMPHost::CreateObjectByCLSID", 1342, String);
          }
          if ( !g_wppLevels )
            goto LABEL_181;
          v77 = 89;
        }
      }
      else
      {
        v80 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v81 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v78, v79);
          CallStackTracing::s_wpInstance = v81;
          if ( v81 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v81 + 8LL))(v81, 2032) )
          {
            v80 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v80 = &qword_1803CE250;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
          }
        }
        if ( *((_BYTE *)v80 + 8) )
        {
          v82 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v80);
          if ( *((_DWORD *)v82 + 499) != String )
            CallStackContext::TraceFailure(v82, "CPMPHost::CreateObjectByCLSID", 1340, String);
        }
        if ( !g_wppLevels )
          goto LABEL_181;
        v77 = 88;
      }
    }
    else
    {
      v74 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v75 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v72, v73);
        CallStackTracing::s_wpInstance = v75;
        if ( v75 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v75 + 8LL))(v75, 2032) )
        {
          v74 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v74 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v74 + 8) )
      {
        v76 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v74);
        if ( *((_DWORD *)v76 + 499) != String )
          CallStackContext::TraceFailure(v76, "CPMPHost::CreateObjectByCLSID", 1338, String);
      }
      if ( !g_wppLevels )
        goto LABEL_181;
      v77 = 87;
    }
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v77,
      &WPP_1ede33fc6d933efc25e43a6be7416609_Traceguids,
      (char *)this - 8,
      String);
  }
  else
  {
    String = MF::OriginateError((MF *)0x80070057LL, *(int *)CLSID_CreateMediaExtensionObject.Data4);
  }
LABEL_181:
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v99);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&ppv);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v98);
LABEL_182:
  v93 = *(_QWORD *)&CLSID_CreateMediaExtensionObject.Data1 - *(_QWORD *)&v107->Data1;
  if ( *(_QWORD *)&CLSID_CreateMediaExtensionObject.Data1 == *(_QWORD *)&v107->Data1 )
    v93 = *(_QWORD *)CLSID_CreateMediaExtensionObject.Data4 - *(_QWORD *)v107->Data4;
  if ( v93 )
  {
    if ( (Microsoft_Windows_MFEnableBits & 0x10) != 0 )
      McTemplateU0jd_EventWriteTransfer(v21, v20, v107, (unsigned int)String);
  }
  else if ( (Microsoft_Windows_MFEnableBits & 8) != 0 )
  {
    v94 = CMFBaseStringT<unsigned short>::PContents(&v101);
    McTemplateU0zd_EventWriteTransfer(v95, &IMFPMPHostApp_ActivateClassById, v94, (unsigned int)String);
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v100);
  CMFBaseStringT<char>::~CMFBaseStringT<char>(&v101);
  return (unsigned int)String;
}

```

## disassembly

```asm
0x1801dd9b0  push    rbp
0x1801dd9b2  push    rbx
0x1801dd9b3  push    rsi
0x1801dd9b4  push    rdi
0x1801dd9b5  push    r12
0x1801dd9b7  push    r13
0x1801dd9b9  push    r14
0x1801dd9bb  push    r15
0x1801dd9bd  lea     rbp, [rsp-17h]
0x1801dd9c2  sub     rsp, 0B8h
0x1801dd9c9  mov     rax, cs:__security_cookie
0x1801dd9d0  xor     rax, rsp
0x1801dd9d3  mov     [rbp+4Fh+var_48], rax
0x1801dd9d7  mov     rdi, [rbp+4Fh+arg_20]
0x1801dd9db  lea     r12, aCpmphostCreate_1; "CPMPHost::CreateObjectByCLSID"
0x1801dd9e2  and     [rbp+4Fh+var_A0], 0FFFFFFF8h
0x1801dd9e6  xor     r15d, r15d
0x1801dd9e9  mov     rsi, r8
0x1801dd9ec  mov     [rbp+4Fh+var_70], rdx
0x1801dd9f0  mov     rbx, rdx
0x1801dd9f3  mov     [rbp+4Fh+var_B8], r9
0x1801dd9f7  mov     r14, rcx
0x1801dd9fa  mov     [rbp+4Fh+var_78], rdi
0x1801dd9fe  mov     rdx, r12; char *
0x1801dda01  mov     [rbp+4Fh+var_9C], r15
0x1801dda05  mov     r8d, 4E8h; int
0x1801dda0b  mov     [rbp+4Fh+var_90], r15
0x1801dda0f  lea     rcx, [rbp+4Fh+var_A8]; this
0x1801dda13  mov     [rbp+4Fh+var_94], r15d
0x1801dda17  mov     r13, r9
0x1801dda1a  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1801dda1f  cmp     cs:byte_1803CECE9, 8
0x1801dda26  jb      short loc_1801DDA4C
0x1801dda28  mov     rcx, cs:WPP_GLOBAL_Control
0x1801dda2f  lea     r9, [r14-8]
0x1801dda33  lea     edx, [r15+4Dh]
0x1801dda37  mov     qword ptr [rsp+0F0h+bIgnoreCase], rsi
0x1801dda3c  lea     r8, WPP_1ede33fc6d933efc25e43a6be7416609_Traceguids
0x1801dda43  mov     rcx, [rcx+38h]
0x1801dda47  call    WPP_SF_qq
0x1801dda4c  mov     rax, [rbx]
0x1801dda4f  sub     rax, qword ptr cs:CLSID_SequencerSourceRemoteStream.Data1
0x1801dda56  jnz     short loc_1801DDA63
0x1801dda58  mov     rax, [rbx+8]
0x1801dda5c  sub     rax, qword ptr cs:CLSID_SequencerSourceRemoteStream.Data4
0x1801dda63  mov     rdx, qword ptr cs:CLSID_CreateMediaExtensionObject.Data4; int
0x1801dda6a  mov     rcx, qword ptr cs:CLSID_CreateMediaExtensionObject.Data1
0x1801dda71  test    rax, rax
0x1801dda74  jz      loc_1801DDDAB
0x1801dda7a  mov     rax, [rbx]
0x1801dda7d  sub     rax, rcx
0x1801dda80  jnz     short loc_1801DDA89
0x1801dda82  mov     rax, [rbx+8]
0x1801dda86  sub     rax, rdx
0x1801dda89  test    rax, rax
0x1801dda8c  jz      loc_1801DDDAB
0x1801dda92  mov     rcx, [r14+50h]
0x1801dda96  lea     r9, [rbp+4Fh+ppv]; void **
0x1801dda9a  add     r14, 0FFFFFFFFFFFFFFF8h
0x1801dda9e  mov     [rbp+4Fh+ppv], r15
0x1801ddaa2  add     rcx, 10h; this
0x1801ddaa6  mov     [rbp+4Fh+var_B8], r15
0x1801ddaaa  mov     r8, r13; struct _GUID *
0x1801ddaad  mov     rdx, rbx; struct _GUID *
0x1801ddab0  call    ?CreateObject@CPMPComponentCreator@@UEAAJAEBU_GUID@@0PEAPEAX@Z; CPMPComponentCreator::CreateObject(_GUID const &,_GUID const &,void * *)
0x1801ddab5  mov     ebx, eax
0x1801ddab7  test    eax, eax
0x1801ddab9  jns     loc_1801DDB80
0x1801ddabf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801ddac6  test    rcx, rcx
0x1801ddac9  jnz     short loc_1801DDB13
0x1801ddacb  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801ddad2  nop     dword ptr [rax+rax+00h]
0x1801ddad7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801ddade  mov     rcx, rax
0x1801ddae1  test    rax, rax
0x1801ddae4  jz      short loc_1801DDB05
0x1801ddae6  mov     rax, [rax]
0x1801ddae9  mov     edx, 7F0h
0x1801ddaee  mov     rax, [rax+8]
0x1801ddaf2  call    cs:__guard_dispatch_icall_fptr
0x1801ddaf8  test    eax, eax
0x1801ddafa  jz      short loc_1801DDB05
0x1801ddafc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801ddb03  jmp     short loc_1801DDB13
0x1801ddb05  lea     rcx, qword_1803CE250; this
0x1801ddb0c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801ddb13  cmp     [rcx+8], r15b
0x1801ddb17  jz      short loc_1801DDB3A
0x1801ddb19  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801ddb1e  cmp     [rax+7CCh], ebx
0x1801ddb24  jz      short loc_1801DDB3A
0x1801ddb26  mov     r9d, ebx; int
0x1801ddb29  mov     r8d, 4F0h; int
0x1801ddb2f  mov     rdx, r12; char *
0x1801ddb32  mov     rcx, rax; this
0x1801ddb35  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801ddb3a  mov     edi, 1
0x1801ddb3f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x1801ddb46  jb      short loc_1801DDB69
0x1801ddb48  lea     edx, [rdi+4Dh]
0x1801ddb4b  mov     rcx, cs:WPP_GLOBAL_Control
0x1801ddb52  lea     r8, WPP_1ede33fc6d933efc25e43a6be7416609_Traceguids
0x1801ddb59  mov     r9, r14
0x1801ddb5c  mov     [rsp+0F0h+bIgnoreCase], ebx
0x1801ddb60  mov     rcx, [rcx+10h]
0x1801ddb64  call    WPP_SF_qD
0x1801ddb69  lea     rcx, [rbp+4Fh+var_B8]
0x1801ddb6d  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x1801ddb72  lea     rcx, [rbp+4Fh+ppv]
0x1801ddb76  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x1801ddb7b  jmp     loc_1801DE5C4
0x1801ddb80  test    rsi, rsi
0x1801ddb83  jz      loc_1801DDCF6
0x1801ddb89  mov     rcx, [rbp+4Fh+ppv]
0x1801ddb8d  lea     r8, [rbp+4Fh+var_B8]
0x1801ddb91  lea     rdx, IID_IPersistStream
0x1801ddb98  mov     rax, [rcx]
0x1801ddb9b  mov     rax, [rax]
0x1801ddb9e  call    cs:__guard_dispatch_icall_fptr
0x1801ddba4  mov     ebx, eax
0x1801ddba6  test    eax, eax
0x1801ddba8  jns     loc_1801DDC43
0x1801ddbae  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801ddbb5  test    rcx, rcx
0x1801ddbb8  jnz     short loc_1801DDC02
0x1801ddbba  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801ddbc1  nop     dword ptr [rax+rax+00h]
0x1801ddbc6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801ddbcd  mov     rcx, rax
0x1801ddbd0  test    rax, rax
0x1801ddbd3  jz      short loc_1801DDBF4
0x1801ddbd5  mov     rax, [rax]
0x1801ddbd8  mov     edx, 7F0h
0x1801ddbdd  mov     rax, [rax+8]
0x1801ddbe1  call    cs:__guard_dispatch_icall_fptr
0x1801ddbe7  test    eax, eax
0x1801ddbe9  jz      short loc_1801DDBF4
0x1801ddbeb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801ddbf2  jmp     short loc_1801DDC02
0x1801ddbf4  lea     rcx, qword_1803CE250; this
0x1801ddbfb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801ddc02  cmp     [rcx+8], r15b
0x1801ddc06  jz      short loc_1801DDC29
0x1801ddc08  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801ddc0d  cmp     [rax+7CCh], ebx
0x1801ddc13  jz      short loc_1801DDC29
0x1801ddc15  mov     r9d, ebx; int
0x1801ddc18  mov     r8d, 4F4h; int
0x1801ddc1e  mov     rdx, r12; char *
0x1801ddc21  mov     rcx, rax; this
0x1801ddc24  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801ddc29  mov     edi, 1
0x1801ddc2e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x1801ddc35  jb      loc_1801DDB69
0x1801ddc3b  lea     edx, [rdi+4Eh]
0x1801ddc3e  jmp     loc_1801DDB4B
0x1801ddc43  mov     rcx, [rbp+4Fh+var_B8]
0x1801ddc47  mov     rdx, rsi
0x1801ddc4a  mov     rax, [rcx]
0x1801ddc4d  mov     rax, [rax+28h]
0x1801ddc51  call    cs:__guard_dispatch_icall_fptr
0x1801ddc57  mov     ebx, eax
0x1801ddc59  test    eax, eax
0x1801ddc5b  jns     loc_1801DDCF6
0x1801ddc61  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801ddc68  test    rcx, rcx
0x1801ddc6b  jnz     short loc_1801DDCB5
0x1801ddc6d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801ddc74  nop     dword ptr [rax+rax+00h]
0x1801ddc79  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801ddc80  mov     rcx, rax
0x1801ddc83  test    rax, rax
0x1801ddc86  jz      short loc_1801DDCA7
0x1801ddc88  mov     rax, [rax]
0x1801ddc8b  mov     edx, 7F0h
0x1801ddc90  mov     rax, [rax+8]
0x1801ddc94  call    cs:__guard_dispatch_icall_fptr
0x1801ddc9a  test    eax, eax
0x1801ddc9c  jz      short loc_1801DDCA7
0x1801ddc9e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801ddca5  jmp     short loc_1801DDCB5
0x1801ddca7  lea     rcx, qword_1803CE250; this
0x1801ddcae  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801ddcb5  cmp     [rcx+8], r15b
0x1801ddcb9  jz      short loc_1801DDCDC
0x1801ddcbb  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801ddcc0  cmp     [rax+7CCh], ebx
0x1801ddcc6  jz      short loc_1801DDCDC
0x1801ddcc8  mov     r9d, ebx; int
0x1801ddccb  mov     r8d, 4F6h; int
0x1801ddcd1  mov     rdx, r12; char *
0x1801ddcd4  mov     rcx, rax; this
0x1801ddcd7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801ddcdc  mov     edi, 1
0x1801ddce1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x1801ddce8  jb      loc_1801DDB69
0x1801ddcee  lea     edx, [rdi+4Fh]
0x1801ddcf1  jmp     loc_1801DDB4B
0x1801ddcf6  mov     rcx, [rbp+4Fh+ppv]
0x1801ddcfa  mov     r8, rdi
0x1801ddcfd  mov     rdx, r13
0x1801ddd00  mov     rax, [rcx]
0x1801ddd03  mov     rax, [rax]
0x1801ddd06  call    cs:__guard_dispatch_icall_fptr
0x1801ddd0c  mov     ebx, eax
0x1801ddd0e  test    eax, eax
0x1801ddd10  jns     loc_1801DDB69
0x1801ddd16  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801ddd1d  test    rcx, rcx
0x1801ddd20  jnz     short loc_1801DDD6A
0x1801ddd22  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801ddd29  nop     dword ptr [rax+rax+00h]
0x1801ddd2e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801ddd35  mov     rcx, rax
0x1801ddd38  test    rax, rax
0x1801ddd3b  jz      short loc_1801DDD5C
0x1801ddd3d  mov     rax, [rax]
0x1801ddd40  mov     edx, 7F0h
0x1801ddd45  mov     rax, [rax+8]
0x1801ddd49  call    cs:__guard_dispatch_icall_fptr
0x1801ddd4f  test    eax, eax
0x1801ddd51  jz      short loc_1801DDD5C
0x1801ddd53  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801ddd5a  jmp     short loc_1801DDD6A
0x1801ddd5c  lea     rcx, qword_1803CE250; this
0x1801ddd63  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801ddd6a  cmp     [rcx+8], r15b
0x1801ddd6e  jz      short loc_1801DDD91
0x1801ddd70  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801ddd75  cmp     [rax+7CCh], ebx
0x1801ddd7b  jz      short loc_1801DDD91
0x1801ddd7d  mov     r9d, ebx; int
0x1801ddd80  mov     r8d, 4F9h; int
0x1801ddd86  mov     rdx, r12; char *
0x1801ddd89  mov     rcx, rax; this
0x1801ddd8c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801ddd91  mov     edi, 1
0x1801ddd96  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x1801ddd9d  jb      loc_1801DDB69
0x1801ddda3  lea     edx, [rdi+50h]
0x1801ddda6  jmp     loc_1801DDB4B
0x1801dddab  mov     rax, [rbx]
0x1801dddae  sub     rax, rcx
0x1801dddb1  jnz     short loc_1801DDDBA
0x1801dddb3  mov     rax, [rbx+8]
0x1801dddb7  sub     rax, rdx
0x1801dddba  test    rax, rax
0x1801dddbd  jnz     loc_1801DE29A
0x1801dddc3  xor     r8d, r8d; int *
0x1801dddc6  lea     rcx, [rbp+4Fh+var_88]; this
0x1801dddca  mov     rdx, rsi; struct IStream *
0x1801dddcd  call    ??0CStreamReader@@QEAA@PEAUIStream@@PEAJ@Z; CStreamReader::CStreamReader(IStream *,long *)
0x1801dddd2  lea     rdx, [rbp+4Fh+var_A0]
0x1801dddd6  mov     [rbp+4Fh+ppv], r15
0x1801dddda  lea     rcx, [rbp+4Fh+var_88]; this
0x1801dddde  mov     [rbp+4Fh+var_B0], r15
0x1801ddde2  call    ?ReadString@CStreamReader@@QEAAJAEAV?$CMFBaseStringT@G@@@Z; CStreamReader::ReadString(CMFBaseStringT<ushort> &)
0x1801ddde7  lea     r12, [r14-8]
0x1801dddeb  mov     ebx, eax
0x1801ddded  test    eax, eax
0x1801dddef  jns     loc_1801DDEC3
0x1801dddf5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801dddfc  test    rcx, rcx
0x1801dddff  jnz     short loc_1801DDE49
0x1801dde01  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801dde08  nop     dword ptr [rax+rax+00h]
0x1801dde0d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801dde14  mov     rcx, rax
0x1801dde17  test    rax, rax
0x1801dde1a  jz      short loc_1801DDE3B
0x1801dde1c  mov     rax, [rax]
0x1801dde1f  mov     edx, 7F0h
0x1801dde24  mov     rax, [rax+8]
0x1801dde28  call    cs:__guard_dispatch_icall_fptr
0x1801dde2e  test    eax, eax
0x1801dde30  jz      short loc_1801DDE3B
0x1801dde32  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801dde39  jmp     short loc_1801DDE49
0x1801dde3b  lea     rcx, qword_1803CE250; this
0x1801dde42  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801dde49  cmp     [rcx+8], r15b
0x1801dde4d  jz      short loc_1801DDE74
0x1801dde4f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801dde54  cmp     [rax+7CCh], ebx
0x1801dde5a  jz      short loc_1801DDE74
0x1801dde5c  mov     r9d, ebx; int
0x1801dde5f  lea     rdx, aCpmphostCreate_1; "CPMPHost::CreateObjectByCLSID"
0x1801dde66  mov     r8d, 504h; int
0x1801dde6c  mov     rcx, rax; this
0x1801dde6f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801dde74  mov     edi, 1
0x1801dde79  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x1801dde80  jb      short loc_1801DDEA3
0x1801dde82  lea     edx, [rdi+51h]
0x1801dde85  mov     rcx, cs:WPP_GLOBAL_Control
0x1801dde8c  lea     r8, WPP_1ede33fc6d933efc25e43a6be7416609_Traceguids
0x1801dde93  mov     r9, r12
0x1801dde96  mov     [rsp+0F0h+bIgnoreCase], ebx
0x1801dde9a  mov     rcx, [rcx+10h]
  ... truncated ...
```
