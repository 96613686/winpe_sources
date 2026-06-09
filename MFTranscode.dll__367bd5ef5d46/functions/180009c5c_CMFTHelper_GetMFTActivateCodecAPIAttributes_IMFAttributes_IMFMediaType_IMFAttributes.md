# CMFTHelper::GetMFTActivateCodecAPIAttributes(IMFAttributes *,IMFMediaType *,IMFAttributes * *)

- ea: `0x180009c5c`
- end: `0x18000a0c6`
- name: `?GetMFTActivateCodecAPIAttributes@CMFTHelper@@CAJPEAUIMFAttributes@@PEAUIMFMediaType@@PEAPEAU2@@Z`
- size: `1130`
- prototype: `static int(struct IMFAttributes *, struct IMFMediaType *, struct IMFAttributes **)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x1800377fc`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x180009c5c`
- `0x18000a3f4`
- `0x1800174c0`
- `0x18001a330`
- `0x18001c280`
- `0x1800371e8`
- `0x18004f410`
- `0x1800594b0`
- `0x18005a010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180009cd4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180009d9d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180009e51`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180009f15`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000a008`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180009cd4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180009d9d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180009e51`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180009f15`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000a008`
- `MFPlat!MFCreateAttributes` at `0x180009d81`
- `MFPlat!MFCreateAttributes` at `0x180009d81`

## pseudocode

```c
__int64 __fastcall CMFTHelper::GetMFTActivateCodecAPIAttributes(
        struct IMFAttributes *a1,
        struct IMFMediaType *a2,
        struct IMFAttributes **a3)
{
  __int64 v6; // rdx
  __int64 *v7; // rcx
  HRESULT v8; // ebx
  CallStackTracing *v9; // rax
  struct CallStackContext *v10; // rax
  __int64 v11; // rdx
  __int64 v12; // rdx
  __int64 *v13; // rcx
  CallStackTracing *v14; // rax
  struct CallStackContext *v15; // rax
  __int64 v16; // rdx
  __int64 *v17; // rcx
  CallStackTracing *v18; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v20; // rdx
  __int64 *v21; // rcx
  CallStackTracing *v22; // rax
  struct CallStackContext *v23; // rax
  __int64 v24; // rdx
  __int64 *v25; // rcx
  CallStackTracing *v26; // rax
  struct CallStackContext *v27; // rax
  _BYTE v29[8]; // [rsp+30h] [rbp-30h] BYREF
  IMFAttributes *ppMFAttributes; // [rsp+38h] [rbp-28h] BYREF
  int v31; // [rsp+40h] [rbp-20h] BYREF
  GUID Buf1; // [rsp+48h] [rbp-18h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v29,
    "CMFTHelper::GetMFTActivateCodecAPIAttributes",
    142);
  ppMFAttributes = 0;
  v31 = 0;
  Buf1 = GUID_00000000_0000_0000_0000_000000000000;
  if ( a3 )
  {
    *a3 = 0;
    v8 = MFCreateAttributes(&ppMFAttributes, 0xAu);
    if ( v8 >= 0 )
    {
      if ( a1
        && (v8 = ((__int64 (__fastcall *)(struct IMFAttributes *, IMFAttributes *))a1->lpVtbl->CopyAllItems)(
                   a1,
                   ppMFAttributes),
            v8 < 0) )
      {
        v17 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v16);
          CallStackTracing::s_wpInstance = v18;
          if ( v18 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
          {
            v17 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v17 = &qword_180069A90;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
          }
        }
        if ( *((_BYTE *)v17 + 8) )
        {
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v17);
          if ( *((_DWORD *)ThreadRelativeContext + 499) != v8 )
            CallStackContext::TraceFailure(
              ThreadRelativeContext,
              "CMFTHelper::GetMFTActivateCodecAPIAttributes",
              160,
              v8);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v11 = 25;
          goto LABEL_12;
        }
      }
      else if ( a2
             && (((void (__fastcall *)(struct IMFMediaType *, const GUID *, GUID *))a2->lpVtbl->GetGUID)(
                   a2,
                   &MF_MT_MAJOR_TYPE,
                   &Buf1),
                 v8 = CMFTHelper::AddMFTActivateCodecAPIAttributes(a2, ppMFAttributes),
                 v8 < 0) )
      {
        v21 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v20);
          CallStackTracing::s_wpInstance = v22;
          if ( v22 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v22 + 8LL))(v22, 2032) )
          {
            v21 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v21 = &qword_180069A90;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
          }
        }
        if ( *((_BYTE *)v21 + 8) )
        {
          v23 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v21);
          if ( *((_DWORD *)v23 + 499) != v8 )
            CallStackContext::TraceFailure(v23, "CMFTHelper::GetMFTActivateCodecAPIAttributes", 169, v8);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v11 = 26;
          goto LABEL_12;
        }
      }
      else
      {
        if ( memcmp_0(&Buf1, &MFMediaType_Video, 0x10u)
          || ((int (__fastcall *)(IMFAttributes *, GUID *, int *))ppMFAttributes->lpVtbl->GetUINT32)(
               ppMFAttributes,
               &GUID_1c0608e9_370c_4710_8a58_cb6181c42423,
               &v31) >= 0
          || (v8 = ((__int64 (__fastcall *)(IMFAttributes *, GUID *, _QWORD))ppMFAttributes->lpVtbl->SetUINT32)(
                     ppMFAttributes,
                     &GUID_1c0608e9_370c_4710_8a58_cb6181c42423,
                     0),
              v8 >= 0) )
        {
          *a3 = ppMFAttributes;
          ppMFAttributes = 0;
          goto LABEL_62;
        }
        v25 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v26 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v24);
          CallStackTracing::s_wpInstance = v26;
          if ( v26 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v26 + 8LL))(v26, 2032) )
          {
            v25 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v25 = &qword_180069A90;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
          }
        }
        if ( *((_BYTE *)v25 + 8) )
        {
          v27 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v25);
          if ( *((_DWORD *)v27 + 499) != v8 )
            CallStackContext::TraceFailure(v27, "CMFTHelper::GetMFTActivateCodecAPIAttributes", 176, v8);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v11 = 27;
          goto LABEL_12;
        }
      }
    }
    else
    {
      v13 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v14 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v12);
        CallStackTracing::s_wpInstance = v14;
        if ( v14 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v14 + 8LL))(v14, 2032) )
        {
          v13 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v13 = &qword_180069A90;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
        }
      }
      if ( *((_BYTE *)v13 + 8) )
      {
        v15 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v13);
        if ( *((_DWORD *)v15 + 499) != v8 )
          CallStackContext::TraceFailure(v15, "CMFTHelper::GetMFTActivateCodecAPIAttributes", 156, v8);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v11 = 24;
        goto LABEL_12;
      }
    }
  }
  else
  {
    v7 = (__int64 *)CallStackTracing::s_wpInstance;
    v8 = -2147467261;
    if ( !CallStackTracing::s_wpInstance )
    {
      v9 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6);
      CallStackTracing::s_wpInstance = v9;
      if ( v9 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v9 + 8LL))(v9, 2032) )
      {
        v7 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v7 = &qword_180069A90;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
      }
    }
    if ( *((_BYTE *)v7 + 8) )
    {
      v10 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v7);
      if ( *((_DWORD *)v10 + 499) != -2147467261 )
        CallStackContext::TraceFailure(v10, "CMFTHelper::GetMFTActivateCodecAPIAttributes", 149, -2147467261);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v11 = 23;
LABEL_12:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, WPP_51ca0e26e9bc306247403b211e8b86d4_Traceguids, 0, v8);
    }
  }
LABEL_62:
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&ppMFAttributes);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v29);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180009c5c  mov     [rsp-28h+arg_18], rbx
0x180009c61  push    rbp
0x180009c62  push    rsi
0x180009c63  push    rdi
0x180009c64  push    r12
0x180009c66  push    r14
0x180009c68  mov     rbp, rsp
0x180009c6b  sub     rsp, 60h
0x180009c6f  mov     rax, cs:__security_cookie
0x180009c76  xor     rax, rsp
0x180009c79  mov     [rbp+var_8], rax
0x180009c7d  mov     r14, r8
0x180009c80  lea     r12, aCmfthelperGetm; "CMFTHelper::GetMFTActivateCodecAPIAttri"...
0x180009c87  mov     rdi, rdx
0x180009c8a  mov     rsi, rcx
0x180009c8d  mov     rdx, r12; char *
0x180009c90  lea     rcx, [rbp+var_30]; this
0x180009c94  mov     r8d, 8Eh; int
0x180009c9a  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180009c9f  mov     [rbp+ppMFAttributes], 0
0x180009ca7  mov     [rbp+var_20], 0
0x180009cae  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180009cb5  movdqu  [rbp+Buf1], xmm0
0x180009cba  test    r14, r14
0x180009cbd  jnz     loc_180009D71
0x180009cc3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180009cca  mov     ebx, 80004003h
0x180009ccf  test    rcx, rcx
0x180009cd2  jnz     short loc_180009D15
0x180009cd4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180009cda  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180009ce1  mov     rcx, rax
0x180009ce4  test    rax, rax
0x180009ce7  jz      short loc_180009D07
0x180009ce9  mov     rax, [rax]
0x180009cec  mov     edx, 7F0h
0x180009cf1  mov     rax, [rax+8]
0x180009cf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009cfa  test    eax, eax
0x180009cfc  jz      short loc_180009D07
0x180009cfe  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180009d05  jmp     short loc_180009D15
0x180009d07  lea     rcx, qword_180069A90; this
0x180009d0e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180009d15  cmp     byte ptr [rcx+8], 0
0x180009d19  jz      short loc_180009D3C
0x180009d1b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180009d20  cmp     [rax+7CCh], ebx
0x180009d26  jz      short loc_180009D3C
0x180009d28  mov     r9d, ebx; int
0x180009d2b  mov     r8d, 95h; int
0x180009d31  mov     rdx, r12; char *
0x180009d34  mov     rcx, rax; this
0x180009d37  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180009d3c  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180009d41  cmp     al, 1
0x180009d43  jb      loc_18000A092
0x180009d49  mov     edx, 17h
0x180009d4e  mov     rcx, cs:WPP_GLOBAL_Control
0x180009d55  lea     r8, WPP_51ca0e26e9bc306247403b211e8b86d4_Traceguids
0x180009d5c  xor     r9d, r9d
0x180009d5f  mov     [rsp+60h+var_40], ebx
0x180009d63  mov     rcx, [rcx+10h]
0x180009d67  call    WPP_SF_qd
0x180009d6c  jmp     loc_18000A092
0x180009d71  mov     edx, 0Ah; cInitialSize
0x180009d76  mov     qword ptr [r14], 0
0x180009d7d  lea     rcx, [rbp+ppMFAttributes]; ppMFAttributes
0x180009d81  call    cs:__imp_MFCreateAttributes
0x180009d87  mov     ebx, eax
0x180009d89  test    eax, eax
0x180009d8b  jns     loc_180009E1C
0x180009d91  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180009d98  test    rcx, rcx
0x180009d9b  jnz     short loc_180009DDE
0x180009d9d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180009da3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180009daa  mov     rcx, rax
0x180009dad  test    rax, rax
0x180009db0  jz      short loc_180009DD0
0x180009db2  mov     rax, [rax]
0x180009db5  mov     edx, 7F0h
0x180009dba  mov     rax, [rax+8]
0x180009dbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009dc3  test    eax, eax
0x180009dc5  jz      short loc_180009DD0
0x180009dc7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180009dce  jmp     short loc_180009DDE
0x180009dd0  lea     rcx, qword_180069A90; this
0x180009dd7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180009dde  cmp     byte ptr [rcx+8], 0
0x180009de2  jz      short loc_180009E05
0x180009de4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180009de9  cmp     [rax+7CCh], ebx
0x180009def  jz      short loc_180009E05
0x180009df1  mov     r9d, ebx; int
0x180009df4  mov     r8d, 9Ch; int
0x180009dfa  mov     rdx, r12; char *
0x180009dfd  mov     rcx, rax; this
0x180009e00  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180009e05  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180009e0a  cmp     al, 1
0x180009e0c  jb      loc_18000A092
0x180009e12  mov     edx, 18h
0x180009e17  jmp     loc_180009D4E
0x180009e1c  test    rsi, rsi
0x180009e1f  jz      loc_180009ED0
0x180009e25  mov     rax, [rsi]
0x180009e28  mov     rcx, rsi
0x180009e2b  mov     rdx, [rbp+ppMFAttributes]
0x180009e2f  mov     rax, [rax+100h]
0x180009e36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e3b  mov     ebx, eax
0x180009e3d  test    eax, eax
0x180009e3f  jns     loc_180009ED0
0x180009e45  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180009e4c  test    rcx, rcx
0x180009e4f  jnz     short loc_180009E92
0x180009e51  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180009e57  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180009e5e  mov     rcx, rax
0x180009e61  test    rax, rax
0x180009e64  jz      short loc_180009E84
0x180009e66  mov     rax, [rax]
0x180009e69  mov     edx, 7F0h
0x180009e6e  mov     rax, [rax+8]
0x180009e72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e77  test    eax, eax
0x180009e79  jz      short loc_180009E84
0x180009e7b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180009e82  jmp     short loc_180009E92
0x180009e84  lea     rcx, qword_180069A90; this
0x180009e8b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180009e92  cmp     byte ptr [rcx+8], 0
0x180009e96  jz      short loc_180009EB9
0x180009e98  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180009e9d  cmp     [rax+7CCh], ebx
0x180009ea3  jz      short loc_180009EB9
0x180009ea5  mov     r9d, ebx; int
0x180009ea8  mov     r8d, 0A0h; int
0x180009eae  mov     rdx, r12; char *
0x180009eb1  mov     rcx, rax; this
0x180009eb4  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180009eb9  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180009ebe  cmp     al, 1
0x180009ec0  jb      loc_18000A092
0x180009ec6  mov     edx, 19h
0x180009ecb  jmp     loc_180009D4E
0x180009ed0  test    rdi, rdi
0x180009ed3  jz      loc_180009F94
0x180009ed9  mov     rax, [rdi]
0x180009edc  lea     r8, [rbp+Buf1]
0x180009ee0  lea     rdx, MF_MT_MAJOR_TYPE
0x180009ee7  mov     rcx, rdi
0x180009eea  mov     rax, [rax+50h]
0x180009eee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ef3  mov     rdx, [rbp+ppMFAttributes]; struct IMFAttributes *
0x180009ef7  mov     rcx, rdi; struct IMFMediaType *
0x180009efa  call    ?AddMFTActivateCodecAPIAttributes@CMFTHelper@@CAJPEAUIMFMediaType@@PEAUIMFAttributes@@@Z; CMFTHelper::AddMFTActivateCodecAPIAttributes(IMFMediaType *,IMFAttributes *)
0x180009eff  mov     ebx, eax
0x180009f01  test    eax, eax
0x180009f03  jns     loc_180009F94
0x180009f09  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180009f10  test    rcx, rcx
0x180009f13  jnz     short loc_180009F56
0x180009f15  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180009f1b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180009f22  mov     rcx, rax
0x180009f25  test    rax, rax
0x180009f28  jz      short loc_180009F48
0x180009f2a  mov     rax, [rax]
0x180009f2d  mov     edx, 7F0h
0x180009f32  mov     rax, [rax+8]
0x180009f36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f3b  test    eax, eax
0x180009f3d  jz      short loc_180009F48
0x180009f3f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180009f46  jmp     short loc_180009F56
0x180009f48  lea     rcx, qword_180069A90; this
0x180009f4f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180009f56  cmp     byte ptr [rcx+8], 0
0x180009f5a  jz      short loc_180009F7D
0x180009f5c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180009f61  cmp     [rax+7CCh], ebx
0x180009f67  jz      short loc_180009F7D
0x180009f69  mov     r9d, ebx; int
0x180009f6c  mov     r8d, 0A9h; int
0x180009f72  mov     rdx, r12; char *
0x180009f75  mov     rcx, rax; this
0x180009f78  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180009f7d  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180009f82  cmp     al, 1
0x180009f84  jb      loc_18000A092
0x180009f8a  mov     edx, 1Ah
0x180009f8f  jmp     loc_180009D4E
0x180009f94  mov     r8d, 10h; Size
0x180009f9a  lea     rdx, MFMediaType_Video; Buf2
0x180009fa1  lea     rcx, [rbp+Buf1]; Buf1
0x180009fa5  call    memcmp_0
0x180009faa  test    eax, eax
0x180009fac  jnz     loc_18000A083
0x180009fb2  mov     rcx, [rbp+ppMFAttributes]
0x180009fb6  lea     r8, [rbp+var_20]
0x180009fba  lea     rdx, _GUID_1c0608e9_370c_4710_8a58_cb6181c42423
0x180009fc1  mov     rax, [rcx]
0x180009fc4  mov     rax, [rax+38h]
0x180009fc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009fcd  test    eax, eax
0x180009fcf  jns     loc_18000A083
0x180009fd5  mov     rcx, [rbp+ppMFAttributes]
0x180009fd9  lea     rdx, _GUID_1c0608e9_370c_4710_8a58_cb6181c42423
0x180009fe0  xor     r8d, r8d
0x180009fe3  mov     rax, [rcx]
0x180009fe6  mov     rax, [rax+0A8h]
0x180009fed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ff2  mov     ebx, eax
0x180009ff4  test    eax, eax
0x180009ff6  jns     loc_18000A083
0x180009ffc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000a003  test    rcx, rcx
0x18000a006  jnz     short loc_18000A049
0x18000a008  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18000a00e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18000a015  mov     rcx, rax
0x18000a018  test    rax, rax
0x18000a01b  jz      short loc_18000A03B
0x18000a01d  mov     rax, [rax]
0x18000a020  mov     edx, 7F0h
0x18000a025  mov     rax, [rax+8]
0x18000a029  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a02e  test    eax, eax
0x18000a030  jz      short loc_18000A03B
0x18000a032  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000a039  jmp     short loc_18000A049
0x18000a03b  lea     rcx, qword_180069A90; this
0x18000a042  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18000a049  cmp     byte ptr [rcx+8], 0
0x18000a04d  jz      short loc_18000A070
0x18000a04f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18000a054  cmp     [rax+7CCh], ebx
0x18000a05a  jz      short loc_18000A070
0x18000a05c  mov     r9d, ebx; int
0x18000a05f  mov     r8d, 0B0h; int
0x18000a065  mov     rdx, r12; char *
0x18000a068  mov     rcx, rax; this
0x18000a06b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18000a070  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18000a075  cmp     al, 1
0x18000a077  jb      short loc_18000A092
0x18000a079  mov     edx, 1Bh
0x18000a07e  jmp     loc_180009D4E
0x18000a083  mov     rax, [rbp+ppMFAttributes]
0x18000a087  mov     [r14], rax
0x18000a08a  mov     [rbp+ppMFAttributes], 0
0x18000a092  lea     rcx, [rbp+ppMFAttributes]
0x18000a096  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x18000a09b  lea     rcx, [rbp+var_30]; this
0x18000a09f  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18000a0a4  mov     eax, ebx
0x18000a0a6  mov     rcx, [rbp+var_8]
0x18000a0aa  xor     rcx, rsp; StackCookie
0x18000a0ad  call    __security_check_cookie
0x18000a0b2  mov     rbx, [rsp+60h+arg_18]
0x18000a0ba  add     rsp, 60h
0x18000a0be  pop     r14
0x18000a0c0  pop     r12
0x18000a0c2  pop     rdi
0x18000a0c3  pop     rsi
0x18000a0c4  pop     rbp
0x18000a0c5  retn
```
