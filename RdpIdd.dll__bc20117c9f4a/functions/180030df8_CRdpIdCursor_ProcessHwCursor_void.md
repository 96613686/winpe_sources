# CRdpIdCursor::ProcessHwCursor(void)

- ea: `0x180030df8`
- end: `0x1800317f1`
- name: `?ProcessHwCursor@CRdpIdCursor@@AEAA_NXZ`
- size: `2553`
- prototype: `bool __fastcall(CRdpIdCursor *__hidden this)`
- caller_count: `1`
- callee_count: `23`
- tags: `reparse_path, loader_planting, installer_update`

## callers

- `0x1800303a8`

## callees

- `0x180001974`
- `0x180001af0`
- `0x180001bc4`
- `0x180001cec`
- `0x180006970`
- `0x180006f60`
- `0x18000cc0c`
- `0x18000d614`
- `0x18000e190`
- `0x18000f0a8`
- `0x1800106b8`
- `0x18001072c`
- `0x180010e74`
- `0x180010f88`
- `0x1800115e4`
- `0x180013bb0`
- `0x180017680`
- `0x18001de3c`
- `0x18003086c`
- `0x180030c78`
- `0x180030df8`
- `0x1800317f8`
- `0x18003f010`

## string_xrefs

- `0x180030fea`: `Cursor update: id (%d)->(%d), position (%d,%d)->(%d,%d), type 0x%lx, size %dx%d, hotspot (%d,%d), shapeUpdated %d`
- `0x180031422`: `SessionId %d, MonitorId %d, cursor id (%d) -> (%d), type 0x%lx, size %dx%d, hotspot (%d,%d), shapeUpdated %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
char __fastcall CRdpIdCursor::ProcessHwCursor(CRdpIdCursor *this)
{
  unsigned int v2; // eax
  unsigned __int64 v4; // rdx
  unsigned __int64 v5; // rdx
  _DWORD *v6; // rcx
  int v7; // r8d
  int v8; // r9d
  int v9; // eax
  char v10; // r12
  _DWORD *v11; // r8
  int v12; // r9d
  __int64 v13; // rsi
  int v14; // ecx
  char **v15; // rax
  __int64 *v16; // rdx
  _DWORD *v17; // rcx
  int v18; // r8d
  int v19; // r9d
  bool v20; // r15
  _DWORD *v21; // rcx
  int v22; // r8d
  int v23; // r9d
  int v24; // ecx
  int v25; // r8d
  unsigned int v26; // eax
  int v27; // edx
  int v28; // edx
  bool v29; // r8
  const struct _tlgProvider_t *v30; // rax
  CRdpIdAdapter *v31; // rax
  CRdpIdMonitor *v32; // rax
  __int64 v33; // rax
  int v34; // r8d
  __int64 v35; // r9
  __int64 v36; // r10
  int v37; // r11d
  const struct _tlgProvider_t *v38; // rax
  CRdpIdAdapter *v39; // rax
  CRdpIdMonitor *v40; // rax
  __int64 v41; // rax
  __int64 v42; // r8
  __int64 v43; // r9
  int v44; // r10d
  int v45; // [rsp+20h] [rbp-158h]
  const char *v46; // [rsp+28h] [rbp-150h]
  char **v47; // [rsp+28h] [rbp-150h]
  char **v48; // [rsp+38h] [rbp-140h]
  char **v49; // [rsp+48h] [rbp-130h]
  int v50; // [rsp+80h] [rbp-F8h] BYREF
  char *v51; // [rsp+88h] [rbp-F0h] BYREF
  const char *v52; // [rsp+90h] [rbp-E8h] BYREF
  const char *v53; // [rsp+98h] [rbp-E0h] BYREF
  const char *v54; // [rsp+A0h] [rbp-D8h] BYREF
  char *v55; // [rsp+A8h] [rbp-D0h] BYREF
  __int64 v56; // [rsp+B0h] [rbp-C8h] BYREF
  std::_Ref_count_base *v57; // [rsp+B8h] [rbp-C0h]
  CRdpIdCursor *v58; // [rsp+C0h] [rbp-B8h]
  char *Buffer; // [rsp+C8h] [rbp-B0h] BYREF
  __int64 v60; // [rsp+D0h] [rbp-A8h]
  _DWORD v61[2]; // [rsp+E0h] [rbp-98h] BYREF
  __int64 v62; // [rsp+E8h] [rbp-90h]
  __int128 v63; // [rsp+F0h] [rbp-88h] BYREF
  __int128 v64; // [rsp+100h] [rbp-78h]
  _OWORD v65[2]; // [rsp+110h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+0h]

  v58 = this;
  std::shared_ptr<CRdpIdAdapter>::shared_ptr<CRdpIdAdapter>(&v56, *(_QWORD *)this + 232LL);
  v61[0] = *((_DWORD *)this + 11);
  v62 = *((_QWORD *)this + 19);
  v61[1] = *((_DWORD *)this + 42) - v62;
  v63 = 0;
  v64 = 0;
  memset(v65, 0, 28);
  if ( IddClientVersionHigherThanFramework && (unsigned int)IddFunctionCount <= 0x20 )
  {
    (*(void (__fastcall **)(__int64, _QWORD, wchar_t *))(WdfFunctions_02025 + 2128))(
      WdfDriverGlobals,
      *(_QWORD *)WdfDriverGlobals,
      IddFrameworkExtensionName);
    v2 = 0;
    goto LABEL_8;
  }
  v2 = ((__int64 (__fastcall *)(__int64, _QWORD, _DWORD *, __int128 *))qword_180057C10)(
         IddDriverGlobals,
         *(_QWORD *)(*(_QWORD *)this + 224LL),
         v61,
         &v63);
  if ( v2 != -1071774937 )
  {
LABEL_8:
    wil::details::in1diag3::Throw_IfNtStatusFailedMsg(
      retaddr,
      (void *)0x10D,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\cursor.cpp",
      (const char *)v2,
      (int)"IddCxMonitorQueryHardwareCursor3 failed",
      v46);
    if ( RdpIddLoggingProvider::IsEnabled(5u, v4) )
    {
      std::vector<char>::vector<char>(&Buffer);
      snprintf(
        Buffer,
        v60 - (_QWORD)Buffer,
        "Cursor update: id (%d)->(%d), position (%d,%d)->(%d,%d), type 0x%lx, size %dx%d, hotspot (%d,%d), shapeUpdated %d",
        *((_DWORD *)this + 11),
        DWORD1(v64),
        *((_DWORD *)this + 8),
        *((_DWORD *)this + 9),
        DWORD1(v63),
        DWORD2(v63),
        DWORD2(v64),
        HIDWORD(v64),
        LODWORD(v65[0]),
        DWORD2(v65[0]),
        HIDWORD(v65[0]),
        HIDWORD(v63));
      v6 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
      if ( *v6 > 5u )
      {
        v51 = Buffer;
        v53 = "CRdpIdCursor::ProcessHwCursor";
        v50 = 279;
        v52 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\cursor.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          (_DWORD)v6,
          (unsigned int)byte_18004FB8D,
          v7,
          v8,
          (__int64)&v52,
          (__int64)&v50,
          (__int64)&v53,
          (__int64)&v51);
      }
      std::vector<char>::_Tidy(&Buffer);
    }
    v9 = v63;
    if ( (_DWORD)v63 == *((_DWORD *)this + 64) )
    {
      v10 = 0;
    }
    else
    {
      v10 = 1;
      *((_DWORD *)this + 64) = v63;
      if ( v9 )
      {
        v11 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
        if ( *v11 > 5u )
        {
          v13 = v56;
          v50 = *(_DWORD *)(v56 + 516);
          v14 = *(_DWORD *)(*(_QWORD *)this + 280LL);
          v52 = "Cursor became visible";
          LODWORD(v51) = 294;
          v55 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\cursor.cpp";
          v49 = (char **)&v50;
          v48 = (char **)&v52;
          v47 = &v51;
          v15 = &v55;
          v16 = qword_18004FB40;
LABEL_16:
          v54 = "CRdpIdCursor::ProcessHwCursor";
          LODWORD(v53) = v14;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            (_DWORD)v11,
            (_DWORD)v16,
            (_DWORD)v11,
            v12,
            (__int64)v15,
            (__int64)v47,
            (__int64)&v54,
            (__int64)v48,
            (__int64)&v53,
            (__int64)v49);
          goto LABEL_21;
        }
      }
      else
      {
        v11 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
        if ( *v11 > 5u )
        {
          v13 = v56;
          LODWORD(v51) = *(_DWORD *)(v56 + 516);
          v14 = *(_DWORD *)(*(_QWORD *)this + 280LL);
          v55 = "Cursor became invisible";
          v50 = 301;
          v52 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\cursor.cpp";
          v49 = &v51;
          v48 = &v55;
          v47 = (char **)&v50;
          v15 = (char **)&v52;
          v16 = (__int64 *)byte_18004FAF3;
          goto LABEL_16;
        }
      }
    }
    v13 = v56;
LABEL_21:
    if ( !LODWORD(v65[1]) || DWORD1(v65[1]) == *((_DWORD *)this + 61) )
    {
      v20 = 0;
    }
    else
    {
      if ( RdpIddLoggingProvider::IsEnabled(5u, v5) )
      {
        std::vector<char>::vector<char>(&Buffer);
        snprintf(
          Buffer,
          v60 - (_QWORD)Buffer,
          "SessionId %d, MonitorId %d, cursor position (%d,%d) -> (%d,%d)",
          *(_DWORD *)(v13 + 516),
          *(_DWORD *)(*(_QWORD *)this + 280LL),
          *((_DWORD *)this + 8),
          *((_DWORD *)this + 9),
          DWORD1(v63),
          DWORD2(v63));
        v17 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
        if ( *v17 > 5u )
        {
          v55 = Buffer;
          v54 = "CRdpIdCursor::ProcessHwCursor";
          LODWORD(v51) = 316;
          v52 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\cursor.cpp";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            (_DWORD)v17,
            (unsigned int)&dword_18004FABC,
            v18,
            v19,
            (__int64)&v52,
            (__int64)&v51,
            (__int64)&v54,
            (__int64)&v55);
        }
        std::vector<char>::_Tidy(&Buffer);
      }
      v20 = 1;
      *((_DWORD *)this + 61) = DWORD1(v65[1]);
      *((_QWORD *)this + 4) = *(_QWORD *)((char *)&v63 + 4);
    }
    if ( HIDWORD(v63) )
    {
      if ( RdpIddLoggingProvider::IsEnabled(5u, v5) )
      {
        std::vector<char>::vector<char>(&Buffer);
        snprintf(
          Buffer,
          v60 - (_QWORD)Buffer,
          "SessionId %d, MonitorId %d, cursor id (%d) -> (%d), type 0x%lx, size %dx%d, hotspot (%d,%d), shapeUpdated %d",
          *(_DWORD *)(v13 + 516),
          *(_DWORD *)(*(_QWORD *)this + 280LL),
          *((_DWORD *)this + 11),
          DWORD1(v64),
          DWORD2(v64),
          HIDWORD(v64),
          LODWORD(v65[0]),
          DWORD2(v65[0]),
          HIDWORD(v65[0]),
          HIDWORD(v63));
        v21 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
        if ( *v21 > 5u )
        {
          v55 = Buffer;
          v54 = "CRdpIdCursor::ProcessHwCursor";
          LODWORD(v51) = 336;
          v52 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\cursor.cpp";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            (_DWORD)v21,
            (unsigned int)byte_18004FA85,
            v22,
            v23,
            (__int64)&v52,
            (__int64)&v51,
            (__int64)&v54,
            (__int64)&v55);
        }
        std::vector<char>::_Tidy(&Buffer);
      }
      v24 = DWORD1(v65[0]);
      v25 = v65[0];
      v26 = LODWORD(v65[0]) * DWORD1(v65[0]);
      *((_DWORD *)this + 52) = LODWORD(v65[0]) * DWORD1(v65[0]);
      if ( v26 > *((_DWORD *)this + 68) )
      {
        v30 = RdpIddLoggingProvider::Provider();
        if ( *(_DWORD *)v30 > 2u && (unsigned __int8)tlgKeywordOn(v30, 0) )
        {
          v31 = (CRdpIdAdapter *)std::shared_ptr<CRdpIdMonitor>::operator-><CRdpIdMonitor,0>(&v56);
          LODWORD(v51) = CRdpIdAdapter::GetSessionId(v31);
          v32 = (CRdpIdMonitor *)std::shared_ptr<CRdpIdMonitor>::operator-><CRdpIdMonitor,0>(this);
          LODWORD(v53) = CRdpIdMonitor::GetMonitorId(v32);
          wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
            &v55,
            "Invalid size of the XOR plane buffer");
          wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
            &v54,
            "CRdpIdCursor::ProcessHwCursor");
          v50 = 348;
          v33 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
                  &v52,
                  "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\cursor.cpp");
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v37,
            (unsigned int)qword_18004FA38,
            v34,
            v35,
            v33,
            (__int64)&v50,
            v35,
            v36,
            (__int64)&v53,
            (__int64)&v51);
        }
        wil::details::in1diag3::Throw_NtStatus(
          retaddr,
          (void *)0x15D,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\cursor.cpp",
          (const char *)0xC000000DLL,
          v45);
      }
      *((_QWORD *)this + 5) = v64;
      v27 = DWORD2(v64);
      *((_QWORD *)this + 6) = *((_QWORD *)&v64 + 1);
      *((_DWORD *)this + 14) = v25;
      *((_DWORD *)this + 15) = v24;
      *((_QWORD *)this + 8) = *((_QWORD *)&v65[0] + 1);
      if ( *(_DWORD *)(v13 + 440) == 3 && *(_DWORD *)(*(_QWORD *)(*(_QWORD *)this + 208LL) + 108LL) )
      {
        CRdpIdCursor::NormalizeXORPlane(this);
        v27 = DWORD2(v64);
      }
      if ( !v27 )
      {
        v38 = RdpIddLoggingProvider::Provider();
        if ( *(_DWORD *)v38 > 2u && (unsigned __int8)tlgKeywordOn(v38, 0) )
        {
          v39 = (CRdpIdAdapter *)std::shared_ptr<CRdpIdMonitor>::operator-><CRdpIdMonitor,0>(&v56);
          LODWORD(v51) = CRdpIdAdapter::GetSessionId(v39);
          v40 = (CRdpIdMonitor *)std::shared_ptr<CRdpIdMonitor>::operator-><CRdpIdMonitor,0>(this);
          LODWORD(v53) = CRdpIdMonitor::GetMonitorId(v40);
          wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
            &v55,
            "Uninitialized cursor shape received");
          wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
            &v54,
            "CRdpIdCursor::ProcessHwCursor");
          v50 = 396;
          v41 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
                  &v52,
                  "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\cursor.cpp");
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v44,
            (unsigned int)byte_18004F9EB,
            v42,
            v43,
            v41,
            (__int64)&v50,
            v42,
            v43,
            (__int64)&v53,
            (__int64)&v51);
        }
        wil::details::in1diag3::Throw_NtStatus(
          retaddr,
          (void *)0x18D,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\cursor.cpp",
          (const char *)0xC000000DLL,
          v45);
      }
      v28 = v27 - 1;
      if ( v28 )
      {
        if ( v28 == 1 )
          *((_DWORD *)this + 60) = 0;
      }
      else
      {
        CRdpIdCursor::GenerateANDPlane(this);
      }
      if ( HIDWORD(v63) )
        goto LABEL_44;
    }
    if ( v10 )
LABEL_44:
      v29 = 1;
    else
      v29 = 0;
    CRdpIdCursor::UpdateRdpCursor(this, (_DWORD)v63 != 0, v29, v20, DWORD2(v65[1]));
    if ( v57 )
      std::_Ref_count_base::_Decref(v57);
    return 1;
  }
  if ( v57 )
    std::_Ref_count_base::_Decref(v57);
  return 1;
}

```

## disassembly

```asm
0x180030df8  push    rbx
0x180030dfa  push    rsi
0x180030dfb  push    r12
0x180030dfd  push    r13
0x180030dff  push    r14
0x180030e01  push    r15
0x180030e03  sub     rsp, 148h
0x180030e0a  mov     rax, cs:__security_cookie
0x180030e11  xor     rax, rsp
0x180030e14  mov     [rsp+178h+var_48], rax
0x180030e1c  mov     rbx, rcx
0x180030e1f  mov     [rsp+178h+var_B8], rcx
0x180030e27  mov     rdx, [rcx]
0x180030e2a  add     rdx, 0E8h
0x180030e31  lea     rcx, [rsp+178h+var_C8]
0x180030e39  call    ??0?$shared_ptr@VCRdpIdAdapter@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<CRdpIdAdapter>::shared_ptr<CRdpIdAdapter>(std::shared_ptr<CRdpIdAdapter> const &)
0x180030e3e  nop
0x180030e3f  mov     eax, [rbx+2Ch]
0x180030e42  mov     [rsp+178h+var_98], eax
0x180030e49  mov     rcx, [rbx+98h]
0x180030e50  mov     [rsp+178h+var_90], rcx
0x180030e58  mov     eax, [rbx+0A8h]
0x180030e5e  sub     eax, ecx
0x180030e60  mov     [rsp+178h+var_94], eax
0x180030e67  xorps   xmm0, xmm0
0x180030e6a  xor     eax, eax
0x180030e6c  movups  [rsp+178h+var_88], xmm0
0x180030e74  movups  [rsp+178h+var_78], xmm0
0x180030e7c  movups  [rsp+178h+var_68], xmm0
0x180030e84  movups  [rsp+178h+var_68+0Ch], xmm0
0x180030e8c  cmp     cs:IddClientVersionHigherThanFramework, al
0x180030e92  jz      short loc_180030ECE
0x180030e94  lea     r9d, [rax+20h]
0x180030e98  cmp     cs:IddFunctionCount, r9d
0x180030e9f  ja      short loc_180030ECE
0x180030ea1  mov     rax, cs:WdfFunctions_02025
0x180030ea8  mov     byte ptr [rsp+178h+var_158], 0
0x180030ead  mov     r8, cs:IddFrameworkExtensionName
0x180030eb4  mov     rcx, cs:WdfDriverGlobals
0x180030ebb  mov     rdx, [rcx]
0x180030ebe  mov     rax, [rax+850h]
0x180030ec5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030eca  xor     eax, eax
0x180030ecc  jmp     short loc_180030F1B
0x180030ece  mov     rdx, [rbx]
0x180030ed1  lea     r9, [rsp+178h+var_88]
0x180030ed9  lea     r8, [rsp+178h+var_98]
0x180030ee1  mov     rdx, [rdx+0E0h]
0x180030ee8  mov     rcx, cs:IddDriverGlobals
0x180030eef  mov     rax, cs:qword_180057C10
0x180030ef6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030efb  cmp     eax, 0C01E0327h
0x180030f00  jnz     short loc_180030F1B
0x180030f02  mov     rcx, [rsp+178h+var_C0]; this
0x180030f0a  test    rcx, rcx
0x180030f0d  jz      short loc_180030F14
0x180030f0f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180030f14  mov     al, 1
0x180030f16  jmp     loc_1800315D1
0x180030f1b  mov     rcx, [rsp+178h]; this
0x180030f23  lea     rdx, aIddcxmonitorqu; "IddCxMonitorQueryHardwareCursor3 failed"
0x180030f2a  mov     qword ptr [rsp+178h+var_158], rdx; int
0x180030f2f  mov     r9d, eax; char *
0x180030f32  lea     r13, aOnecoreuapTerm_16; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x180030f39  mov     r8, r13; unsigned int
0x180030f3c  mov     edx, 10Dh; void *
0x180030f41  call    ?Throw_IfNtStatusFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfNtStatusFailedMsg(void *,uint,char const *,long,char const *,...)
0x180030f46  mov     cl, 5; unsigned __int8
0x180030f48  call    ?IsEnabled@RdpIddLoggingProvider@@SA_NE_K@Z; RdpIddLoggingProvider::IsEnabled(uchar,unsigned __int64)
0x180030f4d  test    al, al
0x180030f4f  jz      loc_180031090
0x180030f55  lea     rcx, [rsp+178h+Buffer]
0x180030f5d  call    ??0?$vector@DV?$allocator@D@std@@@std@@QEAA@_KAEBV?$allocator@D@1@@Z; std::vector<char>::vector<char>(unsigned __int64,std::allocator<char> const &)
0x180030f62  mov     rdx, [rsp+178h+var_A8]
0x180030f6a  mov     rcx, [rsp+178h+Buffer]; Buffer
0x180030f72  sub     rdx, rcx; BufferCount
0x180030f75  mov     eax, dword ptr [rsp+178h+var_88+0Ch]
0x180030f7c  mov     [rsp+178h+var_108], eax
0x180030f80  mov     eax, dword ptr [rsp+178h+var_68+0Ch]
0x180030f87  mov     [rsp+178h+var_110], eax
0x180030f8b  mov     eax, dword ptr [rsp+178h+var_68+8]
0x180030f92  mov     [rsp+178h+var_118], eax
0x180030f96  mov     eax, dword ptr [rsp+178h+var_68]
0x180030f9d  mov     [rsp+178h+var_120], eax
0x180030fa1  mov     eax, dword ptr [rsp+178h+var_78+0Ch]
0x180030fa8  mov     [rsp+178h+var_128], eax
0x180030fac  mov     eax, dword ptr [rsp+178h+var_78+8]
0x180030fb3  mov     dword ptr [rsp+178h+var_130], eax
0x180030fb7  mov     eax, dword ptr [rsp+178h+var_88+8]
0x180030fbe  mov     dword ptr [rsp+178h+var_138], eax
0x180030fc2  mov     eax, dword ptr [rsp+178h+var_88+4]
0x180030fc9  mov     dword ptr [rsp+178h+var_140], eax
0x180030fcd  mov     eax, [rbx+24h]
0x180030fd0  mov     dword ptr [rsp+178h+var_148], eax
0x180030fd4  mov     eax, [rbx+20h]
0x180030fd7  mov     dword ptr [rsp+178h+var_150], eax
0x180030fdb  mov     eax, dword ptr [rsp+178h+var_78+4]
0x180030fe2  mov     [rsp+178h+var_158], eax
0x180030fe6  mov     r9d, [rbx+2Ch]
0x180030fea  lea     r8, aCursorUpdateId; "Cursor update: id (%d)->(%d), position "...
0x180030ff1  call    snprintf
0x180030ff6  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x180030ffb  mov     rcx, [rax+8]
0x180030fff  mov     eax, [rcx]
0x180031001  cmp     eax, 5
0x180031004  jbe     short loc_18003107A
0x180031006  mov     rax, [rsp+178h+Buffer]
0x18003100e  mov     [rsp+178h+var_F0], rax
0x180031016  lea     r14, aCrdpidcursorPr; "CRdpIdCursor::ProcessHwCursor"
0x18003101d  mov     [rsp+178h+var_E0], r14
0x180031025  mov     [rsp+178h+var_F8], 117h
0x180031030  mov     [rsp+178h+var_E8], r13
0x180031038  lea     rax, [rsp+178h+var_F0]
0x180031040  mov     [rsp+178h+var_140], rax
0x180031045  lea     rax, [rsp+178h+var_E0]
0x18003104d  mov     [rsp+178h+var_148], rax
0x180031052  lea     rax, [rsp+178h+var_F8]
0x18003105a  mov     [rsp+178h+var_150], rax
0x18003105f  lea     rax, [rsp+178h+var_E8]
0x180031067  mov     qword ptr [rsp+178h+var_158], rax
0x18003106c  lea     rdx, byte_18004FB8D
0x180031073  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180031078  jmp     short loc_180031081
0x18003107a  lea     r14, aCrdpidcursorPr; "CRdpIdCursor::ProcessHwCursor"
0x180031081  lea     rcx, [rsp+178h+Buffer]
0x180031089  call    ?_Tidy@?$vector@DV?$allocator@D@std@@@std@@AEAAXXZ; std::vector<char>::_Tidy(void)
0x18003108e  jmp     short loc_180031097
0x180031090  lea     r14, aCrdpidcursorPr; "CRdpIdCursor::ProcessHwCursor"
0x180031097  mov     eax, dword ptr [rsp+178h+var_88]
0x18003109e  cmp     eax, [rbx+100h]
0x1800310a4  jz      loc_18003122B
0x1800310aa  mov     r12b, 1
0x1800310ad  mov     [rbx+100h], eax
0x1800310b3  test    eax, eax
0x1800310b5  jz      loc_180031181
0x1800310bb  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x1800310c0  mov     r8, [rax+8]
0x1800310c4  mov     eax, [r8]
0x1800310c7  cmp     eax, 5
0x1800310ca  jbe     loc_18003122E
0x1800310d0  mov     rsi, [rsp+178h+var_C8]
0x1800310d8  mov     eax, [rsi+204h]
0x1800310de  mov     [rsp+178h+var_F8], eax
0x1800310e5  mov     rax, [rbx]
0x1800310e8  mov     ecx, [rax+118h]
0x1800310ee  lea     rax, aCursorBecameVi; "Cursor became visible"
0x1800310f5  mov     [rsp+178h+var_E8], rax
0x1800310fd  mov     dword ptr [rsp+178h+var_F0], 126h
0x180031108  mov     [rsp+178h+var_D0], r13
0x180031110  lea     rax, [rsp+178h+var_F8]
0x180031118  mov     [rsp+178h+var_130], rax
0x18003111d  lea     rax, [rsp+178h+var_E0]
0x180031125  mov     [rsp+178h+var_138], rax
0x18003112a  lea     rax, [rsp+178h+var_E8]
0x180031132  mov     [rsp+178h+var_140], rax
0x180031137  lea     rax, [rsp+178h+var_D8]
0x18003113f  mov     [rsp+178h+var_148], rax
0x180031144  lea     rax, [rsp+178h+var_F0]
0x18003114c  mov     [rsp+178h+var_150], rax
0x180031151  lea     rax, [rsp+178h+var_D0]
0x180031159  lea     rdx, qword_18004FB40
0x180031160  mov     qword ptr [rsp+178h+var_158], rax
0x180031165  mov     [rsp+178h+var_D8], r14
0x18003116d  mov     dword ptr [rsp+178h+var_E0], ecx
0x180031174  mov     rcx, r8
0x180031177  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3344@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18003117c  jmp     loc_180031236
0x180031181  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x180031186  mov     r8, [rax+8]
0x18003118a  mov     eax, [r8]
0x18003118d  cmp     eax, 5
0x180031190  jbe     loc_18003122E
0x180031196  mov     rsi, [rsp+178h+var_C8]
0x18003119e  mov     eax, [rsi+204h]
0x1800311a4  mov     dword ptr [rsp+178h+var_F0], eax
0x1800311ab  mov     rax, [rbx]
0x1800311ae  mov     ecx, [rax+118h]
0x1800311b4  lea     rax, aCursorBecameIn; "Cursor became invisible"
0x1800311bb  mov     [rsp+178h+var_D0], rax
0x1800311c3  mov     [rsp+178h+var_F8], 12Dh
0x1800311ce  mov     [rsp+178h+var_E8], r13
0x1800311d6  lea     rax, [rsp+178h+var_F0]
0x1800311de  mov     [rsp+178h+var_130], rax
0x1800311e3  lea     rax, [rsp+178h+var_E0]
0x1800311eb  mov     [rsp+178h+var_138], rax
0x1800311f0  lea     rax, [rsp+178h+var_D0]
0x1800311f8  mov     [rsp+178h+var_140], rax
0x1800311fd  lea     rax, [rsp+178h+var_D8]
0x180031205  mov     [rsp+178h+var_148], rax
0x18003120a  lea     rax, [rsp+178h+var_F8]
0x180031212  mov     [rsp+178h+var_150], rax
0x180031217  lea     rax, [rsp+178h+var_E8]
0x18003121f  lea     rdx, byte_18004FAF3
0x180031226  jmp     loc_180031160
0x18003122b  xor     r12b, r12b
0x18003122e  mov     rsi, [rsp+178h+var_C8]
0x180031236  cmp     [rsp+178h+var_58], 0
0x18003123e  jz      loc_180031379
0x180031244  mov     eax, [rbx+0F4h]
0x18003124a  cmp     [rsp+178h+var_54], eax
0x180031251  jz      loc_180031379
0x180031257  mov     cl, 5; unsigned __int8
0x180031259  call    ?IsEnabled@RdpIddLoggingProvider@@SA_NE_K@Z; RdpIddLoggingProvider::IsEnabled(uchar,unsigned __int64)
0x18003125e  test    al, al
0x180031260  jz      loc_180031353
0x180031266  lea     rcx, [rsp+178h+Buffer]
0x18003126e  call    ??0?$vector@DV?$allocator@D@std@@@std@@QEAA@_KAEBV?$allocator@D@1@@Z; std::vector<char>::vector<char>(unsigned __int64,std::allocator<char> const &)
0x180031273  mov     r8, [rbx]
0x180031276  mov     rdx, [rsp+178h+var_A8]
0x18003127e  mov     rcx, [rsp+178h+Buffer]; Buffer
0x180031286  sub     rdx, rcx; BufferCount
0x180031289  mov     eax, dword ptr [rsp+178h+var_88+8]
0x180031290  mov     dword ptr [rsp+178h+var_138], eax
0x180031294  mov     eax, dword ptr [rsp+178h+var_88+4]
0x18003129b  mov     dword ptr [rsp+178h+var_140], eax
0x18003129f  mov     eax, [rbx+24h]
0x1800312a2  mov     dword ptr [rsp+178h+var_148], eax
0x1800312a6  mov     eax, [rbx+20h]
0x1800312a9  mov     dword ptr [rsp+178h+var_150], eax
0x1800312ad  mov     eax, [r8+118h]
0x1800312b4  mov     [rsp+178h+var_158], eax
0x1800312b8  mov     r9d, [rsi+204h]
0x1800312bf  lea     r8, aSessionidDMoni_0; "SessionId %d, MonitorId %d, cursor posi"...
0x1800312c6  call    snprintf
0x1800312cb  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x1800312d0  mov     rcx, [rax+8]
0x1800312d4  mov     eax, [rcx]
0x1800312d6  cmp     eax, 5
0x1800312d9  jbe     short loc_180031346
0x1800312db  mov     rax, [rsp+178h+Buffer]
0x1800312e3  mov     [rsp+178h+var_D0], rax
0x1800312eb  mov     [rsp+178h+var_D8], r14
0x1800312f3  mov     dword ptr [rsp+178h+var_F0], 13Ch
0x1800312fe  mov     [rsp+178h+var_E8], r13
0x180031306  lea     rax, [rsp+178h+var_D0]
0x18003130e  mov     [rsp+178h+var_140], rax
0x180031313  lea     rax, [rsp+178h+var_D8]
0x18003131b  mov     [rsp+178h+var_148], rax
0x180031320  lea     rax, [rsp+178h+var_F0]
0x180031328  mov     [rsp+178h+var_150], rax
0x18003132d  lea     rax, [rsp+178h+var_E8]
0x180031335  mov     qword ptr [rsp+178h+var_158], rax
0x18003133a  lea     rdx, dword_18004FABC
0x180031341  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180031346  lea     rcx, [rsp+178h+Buffer]
0x18003134e  call    ?_Tidy@?$vector@DV?$allocator@D@std@@@std@@AEAAXXZ; std::vector<char>::_Tidy(void)
0x180031353  mov     r15b, 1
0x180031356  mov     eax, [rsp+178h+var_54]
0x18003135d  mov     [rbx+0F4h], eax
0x180031363  mov     eax, dword ptr [rsp+178h+var_88+4]
0x18003136a  mov     [rbx+20h], eax
0x18003136d  mov     eax, dword ptr [rsp+178h+var_88+8]
0x180031374  mov     [rbx+24h], eax
0x180031377  jmp     short loc_18003137C
0x180031379  xor     r15b, r15b
0x18003137c  cmp     dword ptr [rsp+178h+var_88+0Ch], 0
0x180031384  jz      loc_1800315B3
0x18003138a  mov     cl, 5; unsigned __int8
0x18003138c  call    ?IsEnabled@RdpIddLoggingProvider@@SA_NE_K@Z; RdpIddLoggingProvider::IsEnabled(uchar,unsigned __int64)
0x180031391  test    al, al
0x180031393  jz      loc_1800314B6
0x180031399  lea     rcx, [rsp+178h+Buffer]
0x1800313a1  call    ??0?$vector@DV?$allocator@D@std@@@std@@QEAA@_KAEBV?$allocator@D@1@@Z; std::vector<char>::vector<char>(unsigned __int64,std::allocator<char> const &)
0x1800313a6  mov     r8, [rbx]
0x1800313a9  mov     rdx, [rsp+178h+var_A8]
0x1800313b1  mov     rcx, [rsp+178h+Buffer]; Buffer
0x1800313b9  sub     rdx, rcx; BufferCount
0x1800313bc  mov     eax, dword ptr [rsp+178h+var_88+0Ch]
0x1800313c3  mov     [rsp+178h+var_118], eax
0x1800313c7  mov     eax, dword ptr [rsp+178h+var_68+0Ch]
0x1800313ce  mov     [rsp+178h+var_120], eax
0x1800313d2  mov     eax, dword ptr [rsp+178h+var_68+8]
0x1800313d9  mov     [rsp+178h+var_128], eax
0x1800313dd  mov     eax, dword ptr [rsp+178h+var_68]
0x1800313e4  mov     dword ptr [rsp+178h+var_130], eax
0x1800313e8  mov     eax, dword ptr [rsp+178h+var_78+0Ch]
0x1800313ef  mov     dword ptr [rsp+178h+var_138], eax
0x1800313f3  mov     eax, dword ptr [rsp+178h+var_78+8]
0x1800313fa  mov     dword ptr [rsp+178h+var_140], eax
0x1800313fe  mov     eax, dword ptr [rsp+178h+var_78+4]
0x180031405  mov     dword ptr [rsp+178h+var_148], eax
0x180031409  mov     eax, [rbx+2Ch]
0x18003140c  mov     dword ptr [rsp+178h+var_150], eax
0x180031410  mov     eax, [r8+118h]
0x180031417  mov     [rsp+178h+var_158], eax
0x18003141b  mov     r9d, [rsi+204h]
0x180031422  lea     r8, aSessionidDMoni; "SessionId %d, MonitorId %d, cursor id ("...
0x180031429  call    snprintf
0x18003142e  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x180031433  mov     rcx, [rax+8]
0x180031437  mov     eax, [rcx]
0x180031439  cmp     eax, 5
0x18003143c  jbe     short loc_1800314A9
0x18003143e  mov     rax, [rsp+178h+Buffer]
0x180031446  mov     [rsp+178h+var_D0], rax
0x18003144e  mov     [rsp+178h+var_D8], r14
0x180031456  mov     dword ptr [rsp+178h+var_F0], 150h
0x180031461  mov     [rsp+178h+var_E8], r13
0x180031469  lea     rax, [rsp+178h+var_D0]
0x180031471  mov     [rsp+178h+var_140], rax
  ... truncated ...
```
