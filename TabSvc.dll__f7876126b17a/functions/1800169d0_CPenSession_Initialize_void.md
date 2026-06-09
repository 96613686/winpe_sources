# CPenSession::Initialize(void)

- ea: `0x1800169d0`
- end: `0x180017baa`
- name: `?Initialize@CPenSession@@QEAAHXZ`
- size: `4570`
- prototype: `_BOOL8 __fastcall(CPenSession *this)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001506c`

## callees

- `0x180002940`
- `0x180010d90`
- `0x180011400`
- `0x1800117c0`
- `0x1800119b0`
- `0x180013950`
- `0x1800169d0`
- `0x180017bb0`
- `0x18001bbe0`
- `0x18001bc04`
- `0x18001c04c`
- `0x18002b404`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x180016af1`
- `ntdll!EtwEventWriteTransfer` at `0x180016c19`
- `ntdll!EtwEventWriteTransfer` at `0x180016af1`
- `ntdll!EtwEventWriteTransfer` at `0x180016c19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016b26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016b8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016d99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016e01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016fd6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001703e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001718d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800171ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800173b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017420`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800175f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001765d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017832`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001789a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017a6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017ad2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016b26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016b8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016d99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016e01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016fd6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001703e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001718d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800171ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800173b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017420`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800175f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001765d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017832`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001789a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017a6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017ad2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017b2c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017b2c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016db6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016e1e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016ff3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001705b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800171aa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017209`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800173d5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001743d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017612`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001767a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001784f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800178b7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017a8a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017aef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017b6e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016db6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016e1e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016ff3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001705b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800171aa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017209`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800173d5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001743d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017612`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001767a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001784f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800178b7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017a8a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017aef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017b6e`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180016d8f`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180016fcc`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180017183`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800173ae`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800175eb`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180017828`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180017a63`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180016d8f`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180016fcc`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180017183`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800173ae`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800175eb`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180017828`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180017a63`
- `WTSAPI32!WTSQueryUserToken` at `0x180016b06`
- `WTSAPI32!WTSQueryUserToken` at `0x180016b06`

## string_xrefs

- `0x180016a20`: `PENSERVICE_CPenSession::Initialize`
- `0x180016b35`: `PENSERVICE_CPenSession::Initialize`
- `0x180017b4d`: `PENSERVICE_CPenSession::Initialize`

## pseudocode

```c
_BOOL8 __fastcall CPenSession::Initialize(CPenSession *this)
{
  char LastError; // al
  const unsigned __int16 *v4; // rdx
  signed int LogonSessionSid; // esi
  unsigned int v6; // r8d
  const unsigned __int16 *v7; // rax
  const struct std::nothrow_t *v8; // rdx
  unsigned __int16 *v9; // rbx
  const unsigned __int16 *v10; // rdx
  const struct std::nothrow_t *v11; // rdx
  unsigned int v12; // r8d
  const unsigned __int16 *v13; // rax
  const struct std::nothrow_t *v14; // rdx
  unsigned __int16 *v15; // rdi
  const unsigned __int16 *v16; // rdx
  const struct std::nothrow_t *v17; // rdx
  void *v18; // r14
  __int64 v19; // r8
  signed int v20; // eax
  void *EventInSession; // rax
  signed int v22; // eax
  const struct std::nothrow_t *v23; // rdx
  const struct std::nothrow_t *v24; // rdx
  unsigned int v25; // r8d
  const unsigned __int16 *v26; // rax
  const struct std::nothrow_t *v27; // rdx
  const unsigned __int16 *v28; // rdx
  const struct std::nothrow_t *v29; // rdx
  unsigned int v30; // r8d
  const unsigned __int16 *v31; // rax
  const struct std::nothrow_t *v32; // rdx
  const unsigned __int16 *v33; // rdx
  const struct std::nothrow_t *v34; // rdx
  __int64 v35; // r8
  signed int v36; // eax
  void *v37; // rax
  signed int v38; // eax
  const struct std::nothrow_t *v39; // rdx
  const struct std::nothrow_t *v40; // rdx
  unsigned int v41; // r8d
  const unsigned __int16 *v42; // rax
  const unsigned __int16 *v43; // rdx
  void *v44; // rdi
  __int64 v45; // r8
  signed int v46; // eax
  const struct std::nothrow_t *v47; // rdx
  void *v48; // rax
  signed int v49; // eax
  const struct std::nothrow_t *v50; // rdx
  unsigned int v51; // r8d
  const unsigned __int16 *v52; // rax
  const unsigned __int16 *v53; // rdx
  unsigned int v54; // r8d
  const unsigned __int16 *v55; // rax
  const unsigned __int16 *v56; // rdx
  __int64 v57; // r8
  signed int v58; // eax
  void *v59; // rax
  signed int v60; // eax
  const struct std::nothrow_t *v61; // rdx
  const struct std::nothrow_t *v62; // rdx
  unsigned int v63; // r8d
  const unsigned __int16 *v64; // rax
  const unsigned __int16 *v65; // rdx
  unsigned int v66; // r8d
  const unsigned __int16 *v67; // rax
  const unsigned __int16 *v68; // rdx
  __int64 v69; // r8
  signed int v70; // eax
  void *v71; // rax
  signed int v72; // eax
  const struct std::nothrow_t *v73; // rdx
  const struct std::nothrow_t *v74; // rdx
  unsigned int v75; // r8d
  const unsigned __int16 *v76; // rax
  const unsigned __int16 *v77; // rdx
  unsigned int v78; // r8d
  const unsigned __int16 *v79; // rax
  const unsigned __int16 *v80; // rdx
  __int64 v81; // r8
  signed int v82; // eax
  void *v83; // rax
  signed int v84; // eax
  const struct std::nothrow_t *v85; // rdx
  const struct std::nothrow_t *v86; // rdx
  unsigned int v87; // r8d
  const unsigned __int16 *v88; // rax
  const unsigned __int16 *v89; // rdx
  unsigned int v90; // r8d
  const unsigned __int16 *v91; // rax
  const struct std::nothrow_t *v92; // rdx
  const unsigned __int16 *v93; // rdx
  const struct std::nothrow_t *v94; // rdx
  __int64 v95; // r8
  signed int v96; // eax
  const struct std::nothrow_t *v97; // rdx
  const struct std::nothrow_t *v98; // rdx
  void *v99; // rax
  signed int v100; // eax
  const struct std::nothrow_t *v101; // rdx
  const struct std::nothrow_t *v102; // rdx
  int v103; // [rsp+20h] [rbp-69h]
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+30h] [rbp-59h] BYREF
  const unsigned __int16 *v105; // [rsp+38h] [rbp-51h] BYREF
  HLOCAL hMem; // [rsp+40h] [rbp-49h] BYREF
  __int64 v107; // [rsp+48h] [rbp-41h] BYREF
  __int64 v108; // [rsp+50h] [rbp-39h]
  void *phToken; // [rsp+58h] [rbp-31h] BYREF
  void *Block; // [rsp+60h] [rbp-29h] BYREF
  __int64 v111; // [rsp+68h] [rbp-21h]
  __int16 *v112; // [rsp+70h] [rbp-19h]
  int v113; // [rsp+78h] [rbp-11h]
  int v114; // [rsp+7Ch] [rbp-Dh]
  const unsigned __int16 **v115; // [rsp+80h] [rbp-9h]
  __int64 v116; // [rsp+88h] [rbp-1h]

  if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
    WPP_SF_sd(
      *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
      10,
      (unsigned int)WPP_c659a2668e88300a995919efad269855_Traceguids,
      (unsigned int)"PENSERVICE_CPenSession::Initialize",
      *((_DWORD *)this + 1));
  if ( (unsigned int)dword_1800411A8 > 5
    && (qword_1800411B8 & 0x4000000) != 0
    && (qword_1800411C0 & 0x4000000) == qword_1800411C0 )
  {
    v107 = 0x50B000000LL;
    v108 = 0x4000000;
    Block = off_1800411B0;
    v111 = *(unsigned __int16 *)off_1800411B0 | 0x200000000LL;
    v112 = &word_18003B15E;
    v113 = 34;
    v114 = 1;
    LODWORD(v105) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EtwEventWriteTransfer(qword_1800411C8, &v107, 0, 0, 2, &Block);
  }
  phToken = 0;
  if ( !WTSQueryUserToken(*((_DWORD *)this + 1), &phToken) )
  {
    if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_sd(
        *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
        11,
        (unsigned int)WPP_c659a2668e88300a995919efad269855_Traceguids,
        (unsigned int)"PENSERVICE_CPenSession::Initialize",
        LastError);
    }
    if ( (unsigned int)dword_1800411A8 > 5
      && (qword_1800411B8 & 0x4000000) != 0
      && (qword_1800411C0 & 0x4000000) == qword_1800411C0 )
    {
      LODWORD(v105) = GetLastError();
      v115 = &v105;
      v116 = 4;
      v107 = 0x50B000000LL;
      v108 = 0x4000000;
      Block = off_1800411B0;
      v111 = *(unsigned __int16 *)off_1800411B0 | 0x200000000LL;
      v112 = (__int16 *)&dword_18003B18C;
      v113 = 61;
      v114 = 1;
      LODWORD(SecurityDescriptor) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EtwEventWriteTransfer(qword_1800411C8, &v107, 0, 0, 3, &Block);
    }
    return 0;
  }
  hMem = 0;
  LogonSessionSid = GetLogonSessionSid(phToken, (LPWSTR *)&hMem);
  if ( LogonSessionSid >= 0 )
  {
    if ( !*((_QWORD *)this + 2) )
    {
      Block = 0;
      v111 = 0;
      LOWORD(v112) = 0;
      LogonSessionSid = StringSd::SetOwner((StringSd *)&Block, v4);
      if ( LogonSessionSid < 0 )
      {
        operator delete(Block);
        goto LABEL_212;
      }
      if ( StringBuffer::Append((StringBuffer *)&Block, L"G:") < 0
        || StringBuffer::Append((StringBuffer *)&Block, L"SY") < 0 )
      {
        LogonSessionSid = -2147467259;
        operator delete(Block);
        goto LABEL_212;
      }
      v7 = StringAce::Allow((StringAce *)L"SY", (const unsigned __int16 *)0x1F0003, v6);
      v9 = (unsigned __int16 *)v7;
      v105 = v7;
      if ( !v7 )
      {
        LogonSessionSid = -2147024882;
        operator delete(0, v8);
        operator delete(Block);
        goto LABEL_212;
      }
      if ( (_BYTE)v112 )
      {
        v10 = 0;
      }
      else
      {
        LOBYTE(v112) = 1;
        v10 = L"D";
      }
      LogonSessionSid = StringSd::_AddAcl((StringSd *)&Block, v10, v7);
      if ( LogonSessionSid < 0 )
      {
LABEL_29:
        operator delete(v9, v11);
        operator delete(Block);
        goto LABEL_212;
      }
      v13 = StringAce::Allow((StringAce *)hMem, (const unsigned __int16 *)2, v12);
      v15 = (unsigned __int16 *)v13;
      v107 = (__int64)v13;
      if ( !v13 )
      {
        LogonSessionSid = -2147024882;
        operator delete(0, v14);
        goto LABEL_29;
      }
      if ( (_BYTE)v112 )
      {
        v16 = 0;
      }
      else
      {
        LOBYTE(v112) = 1;
        v16 = L"D";
      }
      LogonSessionSid = StringSd::_AddAcl((StringSd *)&Block, v16, v13);
      if ( LogonSessionSid < 0 )
      {
        operator delete(v15, v17);
        goto LABEL_29;
      }
      SecurityDescriptor = 0;
      v18 = Block;
      if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW((LPCWSTR)Block, 1u, &SecurityDescriptor, 0) )
      {
        v20 = GetLastError();
        LogonSessionSid = v20;
        if ( v20 > 0 )
          LogonSessionSid = (unsigned __int16)v20 | 0x80070000;
        if ( LogonSessionSid < 0 )
          goto LABEL_204;
      }
      EventInSession = CreateEventInSession(
                         *((_DWORD *)this + 1),
                         L"{DFFDE213-8CB4-46a9-90EB-3DA843AF66F9}-request",
                         v19,
                         0,
                         v103,
                         SecurityDescriptor);
      *((_QWORD *)this + 2) = EventInSession;
      if ( !EventInSession )
      {
        v22 = GetLastError();
        LogonSessionSid = v22;
        if ( v22 > 0 )
          LogonSessionSid = (unsigned __int16)v22 | 0x80070000;
        if ( LogonSessionSid < 0 )
          goto LABEL_204;
      }
      LocalFree(SecurityDescriptor);
      operator delete(v15, v23);
      operator delete(v9, v24);
      operator delete(v18);
    }
    if ( !*((_QWORD *)this + 3) )
    {
      Block = 0;
      v111 = 0;
      LOWORD(v112) = 0;
      LogonSessionSid = StringSd::SetOwner((StringSd *)&Block, v4);
      if ( LogonSessionSid < 0 )
        goto LABEL_182;
      if ( StringBuffer::Append((StringBuffer *)&Block, L"G:") < 0
        || StringBuffer::Append((StringBuffer *)&Block, L"SY") < 0 )
      {
        goto LABEL_218;
      }
      v26 = StringAce::Allow((StringAce *)L"SY", (const unsigned __int16 *)0x1F0003, v25);
      v9 = (unsigned __int16 *)v26;
      v107 = (__int64)v26;
      if ( !v26 )
        goto LABEL_187;
      if ( (_BYTE)v112 )
      {
        v28 = 0;
      }
      else
      {
        LOBYTE(v112) = 1;
        v28 = L"D";
      }
      LogonSessionSid = StringSd::_AddAcl((StringSd *)&Block, v28, v26);
      if ( LogonSessionSid < 0 )
      {
LABEL_192:
        operator delete(v9, v29);
        operator delete(Block);
        goto LABEL_212;
      }
      v31 = StringAce::Allow((StringAce *)hMem, (const unsigned __int16 *)0x100000, v30);
      v15 = (unsigned __int16 *)v31;
      v105 = v31;
      if ( !v31 )
      {
LABEL_194:
        LogonSessionSid = -2147024882;
        operator delete(0, v32);
        operator delete(v9, v92);
        operator delete(Block);
        goto LABEL_212;
      }
      if ( (_BYTE)v112 )
      {
        v33 = 0;
      }
      else
      {
        LOBYTE(v112) = 1;
        v33 = L"D";
      }
      LogonSessionSid = StringSd::_AddAcl((StringSd *)&Block, v33, v31);
      if ( LogonSessionSid < 0 )
      {
LABEL_199:
        operator delete(v15, v34);
        operator delete(v9, v94);
        operator delete(Block);
        goto LABEL_212;
      }
      SecurityDescriptor = 0;
      v18 = Block;
      if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW((LPCWSTR)Block, 1u, &SecurityDescriptor, 0) )
      {
        v36 = GetLastError();
        LogonSessionSid = v36;
        if ( v36 > 0 )
          LogonSessionSid = (unsigned __int16)v36 | 0x80070000;
        if ( LogonSessionSid < 0 )
          goto LABEL_204;
      }
      v37 = CreateEventInSession(
              *((_DWORD *)this + 1),
              L"{DFFDE213-8CB4-46a9-90EB-3DA843AF66F9}-show",
              v35,
              0,
              v103,
              SecurityDescriptor);
      *((_QWORD *)this + 3) = v37;
      if ( !v37 )
      {
        v38 = GetLastError();
        LogonSessionSid = v38;
        if ( v38 > 0 )
          LogonSessionSid = (unsigned __int16)v38 | 0x80070000;
        if ( LogonSessionSid < 0 )
          goto LABEL_204;
      }
      LocalFree(SecurityDescriptor);
      operator delete(v15, v39);
      operator delete(v9, v40);
      operator delete(v18);
    }
    if ( !*((_QWORD *)this + 6) )
    {
      Block = 0;
      v111 = 0;
      LOWORD(v112) = 0;
      LogonSessionSid = StringSd::SetOwner((StringSd *)&Block, v4);
      if ( LogonSessionSid < 0 )
        goto LABEL_182;
      if ( StringBuffer::Append((StringBuffer *)&Block, L"G:") < 0
        || StringBuffer::Append((StringBuffer *)&Block, L"SY") < 0 )
      {
        goto LABEL_218;
      }
      v42 = StringAce::Allow((StringAce *)L"SY", (const unsigned __int16 *)0x1F0003, v41);
      v9 = (unsigned __int16 *)v42;
      v107 = (__int64)v42;
      if ( !v42 )
        goto LABEL_187;
      if ( (_BYTE)v112 )
      {
        v43 = 0;
      }
      else
      {
        LOBYTE(v112) = 1;
        v43 = L"D";
      }
      LogonSessionSid = StringSd::_AddAcl((StringSd *)&Block, v43, v42);
      if ( LogonSessionSid < 0 )
        goto LABEL_192;
      SecurityDescriptor = 0;
      v44 = Block;
      if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW((LPCWSTR)Block, 1u, &SecurityDescriptor, 0) )
      {
        v46 = GetLastError();
        LogonSessionSid = v46;
        if ( v46 > 0 )
          LogonSessionSid = (unsigned __int16)v46 | 0x80070000;
        if ( LogonSessionSid < 0 )
          goto LABEL_92;
      }
      v48 = CreateEventInSession(
              *((_DWORD *)this + 1),
              L"{773F1B9A-35B9-4E95-83A0-A210F2DE3B37}-uds",
              v45,
              0,
              v103,
              SecurityDescriptor);
      *((_QWORD *)this + 6) = v48;
      if ( !v48 )
      {
        v49 = GetLastError();
        LogonSessionSid = v49;
        if ( v49 > 0 )
          LogonSessionSid = (unsigned __int16)v49 | 0x80070000;
        if ( LogonSessionSid < 0 )
        {
LABEL_92:
          LocalFree(SecurityDescriptor);
          operator delete(v9, v47);
          operator delete(v44);
          goto LABEL_212;
        }
      }
      LocalFree(SecurityDescriptor);
      operator delete(v9, v50);
      operator delete(v44);
    }
    if ( !*((_QWORD *)this + 8) )
    {
      Block = 0;
      v111 = 0;
      LOWORD(v112) = 0;
      LogonSessionSid = StringSd::SetOwner((StringSd *)&Block, v4);
      if ( LogonSessionSid < 0 )
        goto LABEL_182;
      if ( StringBuffer::Append((StringBuffer *)&Block, L"G:") < 0
        || StringBuffer::Append((StringBuffer *)&Block, L"SY") < 0 )
      {
        goto LABEL_218;
      }
      v52 = StringAce::Allow((StringAce *)L"SY", (const unsigned __int16 *)0x1F0003, v51);
      v9 = (unsigned __int16 *)v52;
      v107 = (__int64)v52;
      if ( !v52 )
        goto LABEL_187;
      if ( (_BYTE)v112 )
      {
        v53 = 0;
      }
      else
      {
        LOBYTE(v112) = 1;
        v53 = L"D";
      }
      LogonSessionSid = StringSd::_AddAcl((StringSd *)&Block, v53, v52);
      if ( LogonSessionSid < 0 )
        goto LABEL_192;
      v55 = StringAce::Allow((StringAce *)hMem, (const unsigned __int16 *)2, v54);
      v15 = (unsigned __int16 *)v55;
      v105 = v55;
      if ( !v55 )
        goto LABEL_194;
      if ( (_BYTE)v112 )
      {
        v56 = 0;
      }
      else
      {
        LOBYTE(v112) = 1;
        v56 = L"D";
      }
      LogonSessionSid = StringSd::_AddAcl((StringSd *)&Block, v56, v55);
      if ( LogonSessionSid < 0 )
        goto LABEL_199;
      SecurityDescriptor = 0;
      v18 = Block;
      if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW((LPCWSTR)Block, 1u, &SecurityDescriptor, 0) )
      {
        v58 = GetLastError();
        LogonSessionSid = v58;
        if ( v58 > 0 )
          LogonSessionSid = (unsigned __int16)v58 | 0x80070000;
        if ( LogonSessionSid < 0 )
          goto LABEL_204;
      }
      v59 = CreateEventInSession(
              *((_DWORD *)this + 1),
              L"{DFFDE213-8CB4-46a9-90EB-3DA843AF66F9}-crashed",
              v57,
              0,
              v103,
              SecurityDescriptor);
      *((_QWORD *)this + 8) = v59;
      if ( !v59 )
      {
        v60 = GetLastError();
        LogonSessionSid = v60;
        if ( v60 > 0 )
          LogonSessionSid = (unsigned __int16)v60 | 0x80070000;
        if ( LogonSessionSid < 0 )
          goto LABEL_204;
      }
      LocalFree(SecurityDescriptor);
      operator delete(v15, v61);
      operator delete(v9, v62);
      operator delete(v18);
    }
    if ( !*((_QWORD *)this + 9) )
    {
      Block = 0;
      v111 = 0;
      LOWORD(v112) = 0;
      LogonSessionSid = StringSd::SetOwner((StringSd *)&Block, v4);
      if ( LogonSessionSid < 0 )
        goto LABEL_182;
      if ( StringBuffer::Append((StringBuffer *)&Block, L"G:") < 0
        || StringBuffer::Append((StringBuffer *)&Block, L"SY") < 0 )
      {
        goto LABEL_218;
      }
      v64 = StringAce::Allow((StringAce *)L"SY", (const unsigned __int16 *)0x1F0003, v63);
      v9 = (unsigned __int16 *)v64;
      v107 = (__int64)v64;
      if ( !v64 )
        goto LABEL_187;
      if ( (_BYTE)v112 )
      {
        v65 = 0;
      }
      else
      {
        LOBYTE(v112) = 1;
        v65 = L"D";
      }
      LogonSessionSid = StringSd::_AddAcl((StringSd *)&Block, v65, v64);
      if ( LogonSessionSid < 0 )
        goto LABEL_192;
      v67 = StringAce::Allow((StringAce *)hMem, (const unsigned __int16 *)2, v66);
      v15 = (unsigned __int16 *)v67;
      v105 = v67;
      if ( !v67 )
        goto LABEL_194;
      if ( (_BYTE)v112 )
      {
        v68 = 0;
      }
      else
      {
        LOBYTE(v112) = 1;
        v68 = L"D";
      }
      LogonSessionSid = StringSd::_AddAcl((StringSd *)&Block, v68, v67);
      if ( LogonSessionSid < 0 )
        goto LABEL_199;
      SecurityDescriptor = 0;
      v18 = Block;
      if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW((LPCWSTR)Block, 1u, &SecurityDescriptor, 0) )
      {
        v70 = GetLastError();
        LogonSessionSid = v70;
        if ( v70 > 0 )
          LogonSessionSid = (unsigned __int16)v70 | 0x80070000;
        if ( LogonSessionSid < 0 )
          goto LABEL_204;
      }
      v71 = CreateEventInSession(
              *((_DWORD *)this + 1),
              L"{DFFDE213-8CB4-46a9-90EB-3DA843AF66F9}-digitizer",
              v69,
              0,
              v103,
              SecurityDescriptor);
      *((_QWORD *)this + 9) = v71;
      if ( !v71 )
      {
        v72 = GetLastError();
        LogonSessionSid = v72;
        if ( v72 > 0 )
          LogonSessionSid = (unsigned __int16)v72 | 0x80070000;
        if ( LogonSessionSid < 0 )
          goto LABEL_204;
      }
      LocalFree(SecurityDescriptor);
      operator delete(v15, v73);
      operator delete(v9, v74);
      operator delete(v18);
    }
    if ( !*((_QWORD *)this + 10) )
    {
      Block = 0;
      v111 = 0;
      LOWORD(v112) = 0;
      LogonSessionSid = StringSd::SetOwner((StringSd *)&Block, v4);
      if ( LogonSessionSid < 0 )
        goto LABEL_182;
      if ( StringBuffer::Append((StringBuffer *)&Block, L"G:") < 0
        || StringBuffer::Append((StringBuffer *)&Block, L"SY") < 0 )
      {
        goto LABEL_218;
      }
      v76 = StringAce::Allow((StringAce *)L"SY", (const unsigned __int16 *)0x1F0003, v75);
      v9 = (unsigned __int16 *)v76;
      v107 = (__int64)v76;
      if ( !v76 )
      {
LABEL_187:
        LogonSessionSid = -2147024882;
        operator delete(0, v27);
        operator delete(Block);
        goto LABEL_212;
      }
      if ( (_BYTE)v112 )
      {
        v77 = 0;
      }
      else
      {
        LOBYTE(v112) = 1;
        v77 = L"D";
      }
      LogonSessionSid = StringSd::_AddAcl((StringSd *)&Block, v77, v76);
      if ( LogonSessionSid < 0 )
        goto LABEL_192;
      v79 = StringAce::Allow((StringAce *)hMem, (const unsigned __int16 *)2, v78);
      v15 = (unsigned __int16 *)v79;
      v105 = v79;
      if ( !v79 )
        goto LABEL_194;
      if ( (_BYTE)v112 )
      {
        v80 = 0;
      }
      else
      {
        LOBYTE(v112) = 1;
        v80 = L"D";
      }
      LogonSessionSid = StringSd::_AddAcl((StringSd *)&Block, v80, v79);
      if ( LogonSessionSid < 0 )
        goto LABEL_199;
      SecurityDescriptor = 0;
      v18 = Block;
      if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW((LPCWSTR)Block, 1u, &SecurityDescriptor, 0) )
      {
        v82 = GetLastError();
        LogonSessionSid = v82;
        if ( v82 > 0 )
          LogonSessionSid = (unsigned __int16)v82 | 0x80070000;
        if ( LogonSessionSid < 0 )
          goto LABEL_204;
      }
      v83 = CreateEventInSession(
              *((_DWORD *)this + 1),
              L"{DFFDE213-8CB4-46a9-90EB-3DA843AF66F9}-NoDigitizer",
              v81,
              0,
              v103,
              SecurityDescriptor);
      *((_QWORD *)this + 10) = v83;
      if ( !v83 )
      {
        v84 = GetLastError();
        LogonSessionSid = v84;
        if ( v84 > 0 )
          LogonSessionSid = (unsigned __int16)v84 | 0x80070000;
        if ( LogonSessionSid < 0 )
          goto LABEL_204;
      }
      LocalFree(SecurityDescriptor);
      operator delete(v15, v85);
      operator delete(v9, v86);
      operator delete(v18);
    }
    if ( *((_QWORD *)this + 11) )
      goto LABEL_210;
    Block = 0;
    v111 = 0;
    LOWORD(v112) = 0;
    LogonSessionSid = StringSd::SetOwner((StringSd *)&Block, v4);
    if ( LogonSessionSid < 0 )
    {
LABEL_182:
      operator delete(Block);
      goto LABEL_212;
    }
    if ( StringBuffer::Append((StringBuffer *)&Block, L"G:") >= 0
      && StringBuffer::Append((StringBuffer *)&Block, L"SY") >= 0 )
    {
      v88 = StringAce::Allow((StringAce *)L"SY", (const unsigned __int16 *)0x1F0003, v87);
      v9 = (unsigned __int16 *)v88;
      v107 = (__int64)v88;
      if ( !v88 )
        goto LABEL_187;
      if ( (_BYTE)v112 )
      {
        v89 = 0;
      }
      else
      {
        LOBYTE(v112) = 1;
        v89 = L"D";
      }
      LogonSessionSid = StringSd::_AddAcl((StringSd *)&Block, v89, v88);
      if ( LogonSessionSid < 0 )
        goto LABEL_192;
      v91 = StringAce::Allow((StringAce *)hMem, (const unsigned __int16 *)2, v90);
      v15 = (unsigned __int16 *)v91;
      v105 = v91;
      if ( !v91 )
        goto LABEL_194;
      if ( (_BYTE)v112 )
      {
        v93 = 0;
      }
      else
      {
        LOBYTE(v112) = 1;
        v93 = L"D";
      }
      LogonSessionSid = StringSd::_AddAcl((StringSd *)&Block, v93, v91);
      if ( LogonSessionSid < 0 )
        goto LABEL_199;
      SecurityDescriptor = 0;
      v18 = Block;
      if ( ConvertStringSecurityDescriptorToSecurityDescriptorW((LPCWSTR)Block, 1u, &SecurityDescriptor, 0) )
        goto LABEL_208;
      v96 = GetLastError();
      LogonSessionSid = v96;
      if ( v96 > 0 )
        LogonSessionSid = (unsigned __int16)v96 | 0x80070000;
      if ( LogonSessionSid >= 0 )
      {
LABEL_208:
        v99 = CreateEventInSession(
                *((_DWORD *)this + 1),
                L"{958DA730-EDB5-43CE-8A56-776CCC5AB7E1}-request",
                v95,
                0,
                v103,
                SecurityDescriptor);
        *((_QWORD *)this + 11) = v99;
        if ( v99 )
          goto LABEL_209;
        v100 = GetLastError();
        LogonSessionSid = v100;
        if ( v100 > 0 )
          LogonSessionSid = (unsigned __int16)v100 | 0x80070000;
        if ( LogonSessionSid >= 0 )
        {
LABEL_209:
          LocalFree(SecurityDescriptor);
          operator delete(v15, v101);
          operator delete(v9, v102);
          operator delete(v18);
LABEL_210:
          LogonSessionSid = -2147467259;
          if ( (unsigned int)CPenSession::SystemInitialize(this) )
            LogonSessionSid = 0;
          goto LABEL_212;
        }
      }
LABEL_204:
      LocalFree(SecurityDescriptor);
      operator delete(v15, v97);
      operator delete(v9, v98);
      operator delete(v18);
      goto LABEL_212;
    }
LABEL_218:
    LogonSessionSid = -2147467259;
    operator delete(Block);
  }
LABEL_212:
  if ( phToken )
    CloseHandle(phToken);
  if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
    WPP_SF_sd(
      *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
      12,
      (unsigned int)WPP_c659a2668e88300a995919efad269855_Traceguids,
      (unsigned int)"PENSERVICE_CPenSession::Initialize",
      LogonSessionSid);
  LocalFree(hMem);
  return LogonSessionSid >= 0;
}

```

## disassembly

```asm
0x1800169d0  push    rbp
0x1800169d2  push    rbx
0x1800169d3  push    rsi
0x1800169d4  push    rdi
0x1800169d5  push    r12
0x1800169d7  push    r13
0x1800169d9  push    r14
0x1800169db  push    r15
0x1800169dd  lea     rbp, [rsp-1Fh]
0x1800169e2  sub     rsp, 0A8h
0x1800169e9  mov     rax, cs:__security_cookie
0x1800169f0  xor     rax, rsp
0x1800169f3  mov     [rbp+57h+var_50], rax
0x1800169f7  mov     r15, rcx
0x1800169fa  lea     r13, WPP_GLOBAL_Control
0x180016a01  mov     rcx, cs:WPP_GLOBAL_Control
0x180016a08  cmp     rcx, r13
0x180016a0b  jz      short loc_180016A37
0x180016a0d  test    byte ptr [rcx+1Ch], 10h
0x180016a11  jz      short loc_180016A37
0x180016a13  mov     edx, 0Ah
0x180016a18  mov     eax, [r15+4]
0x180016a1c  mov     [rsp+0E0h+var_C0], eax
0x180016a20  lea     r9, aPenserviceCpen_4; "PENSERVICE_CPenSession::Initialize"
0x180016a27  lea     r8, WPP_c659a2668e88300a995919efad269855_Traceguids
0x180016a2e  mov     rcx, [rcx+10h]
0x180016a32  call    WPP_SF_sd
0x180016a37  mov     eax, cs:dword_1800411A8
0x180016a3d  lea     rbx, _TraceLoggingMetadataEnd
0x180016a44  lea     rdi, _TraceLoggingMetadata
0x180016a4b  cmp     eax, 5
0x180016a4e  jbe     loc_180016AF7
0x180016a54  mov     rcx, cs:qword_1800411C0
0x180016a5b  mov     rax, cs:qword_1800411B8
0x180016a62  bt      rax, 1Ah
0x180016a67  jnb     loc_180016AF7
0x180016a6d  mov     rax, rcx
0x180016a70  and     eax, 4000000h
0x180016a75  cmp     rax, rcx
0x180016a78  jnz     short loc_180016AF7
0x180016a7a  mov     dword ptr [rbp+57h+var_98], 0B000000h
0x180016a81  movzx   eax, cs:word_18003B154
0x180016a88  mov     dword ptr [rbp+57h+var_98+4], eax
0x180016a8b  mov     [rbp+57h+var_90], 4000000h
0x180016a93  mov     rax, cs:off_1800411B0
0x180016a9a  mov     [rbp+57h+Block], rax
0x180016a9e  movzx   eax, word ptr [rax]
0x180016aa1  mov     dword ptr [rbp+57h+var_78], eax
0x180016aa4  mov     dword ptr [rbp+57h+var_78+4], 2
0x180016aab  lea     rax, word_18003B15E
0x180016ab2  mov     [rbp+57h+var_70], rax
0x180016ab6  mov     [rbp+57h+var_68], 22h ; '"'
0x180016abd  mov     [rbp+57h+var_64], 1
0x180016ac4  mov     rax, rbx
0x180016ac7  sub     eax, edi
0x180016ac9  mov     dword ptr [rbp+57h+var_A8], eax
0x180016acc  mov     eax, dword ptr [rbp+57h+var_A8]
0x180016acf  lea     rax, [rbp+57h+Block]
0x180016ad3  mov     [rsp+0E0h+var_B8], rax
0x180016ad8  mov     [rsp+0E0h+var_C0], 2; int
0x180016ae0  xor     r9d, r9d
0x180016ae3  xor     r8d, r8d
0x180016ae6  lea     rdx, [rbp+57h+var_98]
0x180016aea  mov     rcx, cs:qword_1800411C8
0x180016af1  call    cs:__imp_EtwEventWriteTransfer
0x180016af7  xor     r12d, r12d
0x180016afa  mov     [rbp+57h+phToken], r12
0x180016afe  lea     rdx, [rbp+57h+phToken]; phToken
0x180016b02  mov     ecx, [r15+4]; SessionId
0x180016b06  call    cs:__imp_WTSQueryUserToken
0x180016b0c  test    eax, eax
0x180016b0e  jnz     loc_180016C26
0x180016b14  mov     rax, cs:WPP_GLOBAL_Control
0x180016b1b  cmp     rax, r13
0x180016b1e  jz      short loc_180016B53
0x180016b20  test    byte ptr [rax+1Ch], 10h
0x180016b24  jz      short loc_180016B53
0x180016b26  call    cs:__imp_GetLastError
0x180016b2c  mov     edx, 0Bh
0x180016b31  mov     [rsp+0E0h+var_C0], eax
0x180016b35  lea     r9, aPenserviceCpen_4; "PENSERVICE_CPenSession::Initialize"
0x180016b3c  lea     r8, WPP_c659a2668e88300a995919efad269855_Traceguids
0x180016b43  mov     rcx, cs:WPP_GLOBAL_Control
0x180016b4a  mov     rcx, [rcx+10h]
0x180016b4e  call    WPP_SF_sd
0x180016b53  mov     eax, cs:dword_1800411A8
0x180016b59  cmp     eax, 5
0x180016b5c  jbe     loc_180016C1F
0x180016b62  mov     rcx, cs:qword_1800411C0
0x180016b69  mov     rax, cs:qword_1800411B8
0x180016b70  bt      rax, 1Ah
0x180016b75  jnb     loc_180016C1F
0x180016b7b  mov     rax, rcx
0x180016b7e  and     eax, 4000000h
0x180016b83  cmp     rax, rcx
0x180016b86  jnz     loc_180016C1F
0x180016b8c  call    cs:__imp_GetLastError
0x180016b92  mov     dword ptr [rbp+57h+var_A8], eax
0x180016b95  lea     rax, [rbp+57h+var_A8]
0x180016b99  mov     [rbp+57h+var_60], rax
0x180016b9d  mov     [rbp+57h+var_58], 4
0x180016ba5  mov     dword ptr [rbp+57h+var_98], 0B000000h
0x180016bac  movzx   eax, cs:word_18003B182
0x180016bb3  mov     dword ptr [rbp+57h+var_98+4], eax
0x180016bb6  mov     [rbp+57h+var_90], 4000000h
0x180016bbe  mov     rax, cs:off_1800411B0
0x180016bc5  mov     [rbp+57h+Block], rax
0x180016bc9  movzx   eax, word ptr [rax]
0x180016bcc  mov     dword ptr [rbp+57h+var_78], eax
0x180016bcf  mov     dword ptr [rbp+57h+var_78+4], 2
0x180016bd6  lea     rax, dword_18003B18C
0x180016bdd  mov     [rbp+57h+var_70], rax
0x180016be1  mov     [rbp+57h+var_68], 3Dh ; '='
0x180016be8  mov     [rbp+57h+var_64], 1
0x180016bef  sub     ebx, edi
0x180016bf1  mov     dword ptr [rbp+57h+SecurityDescriptor], ebx
0x180016bf4  mov     eax, dword ptr [rbp+57h+SecurityDescriptor]
0x180016bf7  lea     rax, [rbp+57h+Block]
0x180016bfb  mov     [rsp+0E0h+var_B8], rax
0x180016c00  mov     [rsp+0E0h+var_C0], 3
0x180016c08  xor     r9d, r9d
0x180016c0b  xor     r8d, r8d
0x180016c0e  lea     rdx, [rbp+57h+var_98]
0x180016c12  mov     rcx, cs:qword_1800411C8
0x180016c19  call    cs:__imp_EtwEventWriteTransfer
0x180016c1f  xor     eax, eax
0x180016c21  jmp     loc_180017B76
0x180016c26  mov     [rbp+57h+hMem], r12
0x180016c2a  lea     rdx, [rbp+57h+hMem]; StringSid
0x180016c2e  mov     rcx, [rbp+57h+phToken]; TokenHandle
0x180016c32  call    ?GetLogonSessionSid@@YAJPEAXPEAPEAG@Z; GetLogonSessionSid(void *,ushort * *)
0x180016c37  mov     esi, eax
0x180016c39  test    eax, eax
0x180016c3b  js      loc_180017B23
0x180016c41  cmp     qword ptr [r15+10h], 0
0x180016c46  jnz     loc_180016E3F
0x180016c4c  mov     [rbp+57h+Block], r12
0x180016c50  mov     [rbp+57h+var_78], r12
0x180016c54  mov     word ptr [rbp+57h+var_70], 0
0x180016c5a  lea     rcx, [rbp+57h+Block]; this
0x180016c5e  call    ?SetOwner@StringSd@@QEAAJPEBG@Z; StringSd::SetOwner(ushort const *)
0x180016c63  mov     esi, eax
0x180016c65  test    eax, eax
0x180016c67  jns     short loc_180016C77
0x180016c69  mov     rcx, [rbp+57h+Block]; Block
0x180016c6d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180016c72  jmp     loc_180017B23
0x180016c77  lea     rdx, aG; "G:"
0x180016c7e  lea     rcx, [rbp+57h+Block]; this
0x180016c82  call    ?Append@StringBuffer@@QEAAJPEBG@Z; StringBuffer::Append(ushort const *)
0x180016c87  test    eax, eax
0x180016c89  js      loc_180016E75
0x180016c8f  lea     rdx, aSy; "SY"
0x180016c96  lea     rcx, [rbp+57h+Block]; this
0x180016c9a  call    ?Append@StringBuffer@@QEAAJPEBG@Z; StringBuffer::Append(ushort const *)
0x180016c9f  test    eax, eax
0x180016ca1  js      loc_180016E75
0x180016ca7  mov     edx, 1F0003h; unsigned __int16 *
0x180016cac  lea     rcx, aSy; "SY"
0x180016cb3  call    ?Allow@StringAce@@YAPEAGPEBGK@Z; StringAce::Allow(ushort const *,ulong)
0x180016cb8  mov     rbx, rax
0x180016cbb  mov     [rbp+57h+var_A8], rax
0x180016cbf  test    rax, rax
0x180016cc2  jnz     short loc_180016CDF
0x180016cc4  mov     esi, 8007000Eh
0x180016cc9  xor     ecx, ecx; void *
0x180016ccb  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180016cd0  nop
0x180016cd1  mov     rcx, [rbp+57h+Block]; Block
0x180016cd5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180016cda  jmp     loc_180017B23
0x180016cdf  cmp     byte ptr [rbp+57h+var_70], 0
0x180016ce3  jz      short loc_180016CEA
0x180016ce5  mov     rdx, r12
0x180016ce8  jmp     short loc_180016CF5
0x180016cea  mov     byte ptr [rbp+57h+var_70], 1
0x180016cee  lea     rdx, aD; "D"
0x180016cf5  mov     r8, rbx; unsigned __int16 *
0x180016cf8  lea     rcx, [rbp+57h+Block]; this
0x180016cfc  call    ?_AddAcl@StringSd@@AEAAJPEBG0@Z; StringSd::_AddAcl(ushort const *,ushort const *)
0x180016d01  mov     esi, eax
0x180016d03  test    eax, eax
0x180016d05  jns     short loc_180016D1E
0x180016d07  mov     rcx, rbx; void *
0x180016d0a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180016d0f  nop
0x180016d10  mov     rcx, [rbp+57h+Block]; Block
0x180016d14  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180016d19  jmp     loc_180017B23
0x180016d1e  mov     edx, 2; unsigned __int16 *
0x180016d23  mov     rcx, [rbp+57h+hMem]; this
0x180016d27  call    ?Allow@StringAce@@YAPEAGPEBGK@Z; StringAce::Allow(ushort const *,ulong)
0x180016d2c  mov     rdi, rax
0x180016d2f  mov     [rbp+57h+var_98], rax
0x180016d33  test    rax, rax
0x180016d36  jnz     short loc_180016D46
0x180016d38  mov     esi, 8007000Eh
0x180016d3d  xor     ecx, ecx; void *
0x180016d3f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180016d44  jmp     short loc_180016D07
0x180016d46  cmp     byte ptr [rbp+57h+var_70], 0
0x180016d4a  jz      short loc_180016D51
0x180016d4c  mov     rdx, r12
0x180016d4f  jmp     short loc_180016D5C
0x180016d51  mov     byte ptr [rbp+57h+var_70], 1
0x180016d55  lea     rdx, aD; "D"
0x180016d5c  mov     r8, rdi; unsigned __int16 *
0x180016d5f  lea     rcx, [rbp+57h+Block]; this
0x180016d63  call    ?_AddAcl@StringSd@@AEAAJPEBG0@Z; StringSd::_AddAcl(ushort const *,ushort const *)
0x180016d68  mov     esi, eax
0x180016d6a  test    eax, eax
0x180016d6c  jns     short loc_180016D78
0x180016d6e  mov     rcx, rdi; void *
0x180016d71  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180016d76  jmp     short loc_180016D07
0x180016d78  mov     [rbp+57h+SecurityDescriptor], r12
0x180016d7c  xor     r9d, r9d; SecurityDescriptorSize
0x180016d7f  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x180016d83  mov     edx, 1; StringSDRevision
0x180016d88  mov     r14, [rbp+57h+Block]
0x180016d8c  mov     rcx, r14; StringSecurityDescriptor
0x180016d8f  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180016d95  test    eax, eax
0x180016d97  jnz     short loc_180016DDC
0x180016d99  call    cs:__imp_GetLastError
0x180016d9f  mov     esi, eax
0x180016da1  test    eax, eax
0x180016da3  jle     short loc_180016DAE
0x180016da5  movzx   esi, ax
0x180016da8  or      esi, 80070000h
0x180016dae  test    esi, esi
0x180016db0  jns     short loc_180016DDC
0x180016db2  mov     rcx, [rbp+57h+SecurityDescriptor]; hMem
0x180016db6  call    cs:__imp_LocalFree
0x180016dbc  nop
0x180016dbd  mov     rcx, rdi; void *
0x180016dc0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180016dc5  nop
0x180016dc6  mov     rcx, rbx; void *
0x180016dc9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180016dce  nop
0x180016dcf  mov     rcx, r14; Block
0x180016dd2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180016dd7  jmp     loc_180017B23
0x180016ddc  mov     rax, [rbp+57h+SecurityDescriptor]
0x180016de0  mov     [rsp+0E0h+var_B8], rax; void *
0x180016de5  xor     r9d, r9d; int
0x180016de8  lea     rdx, SourceString; "{DFFDE213-8CB4-46a9-90EB-3DA843AF66F9}-"...
0x180016def  mov     ecx, [r15+4]; unsigned int
0x180016df3  call    ?CreateEventInSession@@YAPEAXKPEAGKHHPEAX@Z; CreateEventInSession(ulong,ushort *,ulong,int,int,void *)
0x180016df8  mov     [r15+10h], rax
0x180016dfc  test    rax, rax
0x180016dff  jnz     short loc_180016E1A
0x180016e01  call    cs:__imp_GetLastError
0x180016e07  mov     esi, eax
0x180016e09  test    eax, eax
0x180016e0b  jle     short loc_180016E16
0x180016e0d  movzx   esi, ax
0x180016e10  or      esi, 80070000h
0x180016e16  test    esi, esi
0x180016e18  js      short loc_180016DB2
0x180016e1a  mov     rcx, [rbp+57h+SecurityDescriptor]; hMem
0x180016e1e  call    cs:__imp_LocalFree
0x180016e24  nop
0x180016e25  mov     rcx, rdi; void *
0x180016e28  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180016e2d  nop
0x180016e2e  mov     rcx, rbx; void *
0x180016e31  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180016e36  nop
0x180016e37  mov     rcx, r14; Block
0x180016e3a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180016e3f  cmp     qword ptr [r15+18h], 0
0x180016e44  jnz     loc_18001707C
0x180016e4a  mov     [rbp+57h+Block], r12
0x180016e4e  mov     [rbp+57h+var_78], r12
0x180016e52  mov     word ptr [rbp+57h+var_70], 0
0x180016e58  lea     rcx, [rbp+57h+Block]; this
0x180016e5c  call    ?SetOwner@StringSd@@QEAAJPEBG@Z; StringSd::SetOwner(ushort const *)
0x180016e61  mov     esi, eax
0x180016e63  test    eax, eax
0x180016e65  jns     short loc_180016E88
0x180016e67  mov     rcx, [rbp+57h+Block]; Block
0x180016e6b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180016e70  jmp     loc_180017B23
0x180016e75  mov     esi, 80004005h
0x180016e7a  mov     rcx, [rbp+57h+Block]; Block
0x180016e7e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180016e83  jmp     loc_180017B23
0x180016e88  lea     rdx, aG; "G:"
0x180016e8f  lea     rcx, [rbp+57h+Block]; this
0x180016e93  call    ?Append@StringBuffer@@QEAAJPEBG@Z; StringBuffer::Append(ushort const *)
0x180016e98  test    eax, eax
0x180016e9a  js      loc_1800170B2
0x180016ea0  lea     rdx, aSy; "SY"
0x180016ea7  lea     rcx, [rbp+57h+Block]; this
0x180016eab  call    ?Append@StringBuffer@@QEAAJPEBG@Z; StringBuffer::Append(ushort const *)
0x180016eb0  test    eax, eax
0x180016eb2  js      loc_1800170B2
0x180016eb8  mov     edx, 1F0003h; unsigned __int16 *
  ... truncated ...
```
