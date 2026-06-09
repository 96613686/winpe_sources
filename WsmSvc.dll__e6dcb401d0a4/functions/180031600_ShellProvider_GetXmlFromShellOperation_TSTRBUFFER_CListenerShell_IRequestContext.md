# ShellProvider::GetXmlFromShellOperation(TSTRBUFFER *,CListenerShell *,IRequestContext *)

- ea: `0x180031600`
- end: `0x180032f4a`
- name: `?GetXmlFromShellOperation@ShellProvider@@QEAAHPEAVTSTRBUFFER@@PEAVCListenerShell@@PEAVIRequestContext@@@Z`
- size: `6474`
- prototype: `int(ShellProvider *__hidden this, struct TSTRBUFFER *, struct CListenerShell *, struct IRequestContext *)`
- caller_count: `4`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180049860`
- `0x180094470`
- `0x1801b5140`
- `0x1801b5e7c`

## callees

- `0x18002b7a0`
- `0x180031350`
- `0x180031600`
- `0x180032f50`
- `0x1800330d0`
- `0x1800339d0`
- `0x180033b40`
- `0x180077490`
- `0x1800ed744`
- `0x180112380`
- `0x1801123a8`
- `0x1801ba1b0`
- `0x1801c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032bec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032d10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032bec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032d10`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180031b2b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180031b2b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180032bc5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180032bc5`

## string_xrefs

- `0x180031f38`: `WorkingDirectory`
- `0x180031f6f`: `WorkingDirectory`
- `0x1800318d4`: `ResourceUri`
- `0x180031913`: `ResourceUri`
- `0x180031bb9`: `ProcessId`
- `0x180031bf1`: `ProcessId`
- `0x18003287a`: `XpressCompression`
- `0x18003285b`: `CompressionMode`
- `0x1800328a9`: `CompressionMode`
- `0x18003288e`: `NoCompression`

## pseudocode

```c
__int64 __fastcall ShellProvider::GetXmlFromShellOperation(
        ShellProvider *this,
        struct TSTRBUFFER *a2,
        struct CListenerShell *a3,
        struct IRequestContext *a4)
{
  char v7; // r12
  int appended; // eax
  unsigned int v9; // eax
  __int64 v10; // rdx
  int v11; // eax
  int v12; // ecx
  __int64 v13; // rdx
  const unsigned __int16 *v14; // rsi
  int v15; // ecx
  __int64 v16; // rdx
  const unsigned __int16 *Value; // rsi
  int v18; // eax
  int v19; // ecx
  __int64 v20; // rdx
  const unsigned __int16 *v21; // rsi
  int v22; // eax
  int v23; // ecx
  __int64 v24; // rdx
  const unsigned __int16 *v25; // rsi
  int v26; // eax
  int v27; // ecx
  __int64 v28; // rdx
  DWORD CurrentProcessId; // eax
  int v30; // eax
  int v31; // ecx
  __int64 v32; // rdx
  int v33; // ecx
  __int64 v34; // rdx
  unsigned int i; // esi
  __int64 v36; // rcx
  const unsigned __int16 *v37; // r14
  int v38; // eax
  int v39; // ecx
  __int64 v40; // rdx
  int v41; // ecx
  __int64 v42; // rdx
  const unsigned __int16 *v43; // rsi
  int v44; // ecx
  __int64 v45; // rdx
  unsigned int v46; // ecx
  int v47; // eax
  int v48; // ecx
  __int64 v49; // rdx
  __int64 v50; // r14
  int v51; // ecx
  __int64 v52; // rdx
  unsigned int j; // esi
  int v54; // ecx
  __int64 v55; // rdx
  __int64 v56; // r14
  int v57; // ecx
  __int64 v58; // rdx
  unsigned int k; // esi
  int v60; // ecx
  __int64 v61; // rdx
  unsigned int v62; // ecx
  int v63; // ecx
  const unsigned __int16 *v64; // rsi
  int v65; // eax
  const unsigned __int16 *v66; // rsi
  int v67; // eax
  const unsigned __int16 *v68; // rdx
  const unsigned __int16 *v69; // rsi
  const unsigned __int16 *v70; // rsi
  const unsigned __int16 *v71; // rsi
  int v72; // ecx
  __int64 v73; // rdx
  const unsigned __int16 *v74; // rsi
  int v75; // ecx
  __int64 v76; // rdx
  __int64 v77; // rdx
  ULONGLONG TickCount64; // rsi
  ShellProvider *v79; // rcx
  void (__fastcall *v80)(struct IRequestContext *, _QWORD); // rbx
  DWORD LastError; // eax
  int v82; // ecx
  int v83; // eax
  __int64 v84; // rdx
  void (__fastcall *v85)(struct IRequestContext *, _QWORD); // rbx
  DWORD v86; // eax
  int v87; // ecx
  __int64 v88; // rdx
  int v89; // ecx
  __int64 v90; // rdx
  struct _XML_NAMESPACE_PREFIX *v92; // [rsp+20h] [rbp-E0h]
  struct _XML_NAMESPACE_PREFIX *v93; // [rsp+20h] [rbp-E0h]
  _QWORD v94[20]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 v95[24]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int16 v96[20]; // [rsp+110h] [rbp+10h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, WPP_b60bdead82443c7f6980630edf2d3038_Traceguids);
  v7 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)a3 + 312) + 8LL))((char *)a3 + 2496);
  appended = TSTRBUFFER::AppendXmlStartElemWithNamespacesAndPrefixes(
               a2,
               L"Shell",
               L"rsp",
               1u,
               (struct _XML_NAMESPACE_PREFIX *)off_1801C40C8,
               0,
               0,
               0);
  if ( appended < 0 )
  {
    if ( (appended & 0x1FFF0000) == 0x70000 )
      appended = (unsigned __int16)appended;
    (*(void (__fastcall **)(struct IRequestContext *, _QWORD))(*(_QWORD *)a4 + 72LL))(a4, (unsigned int)appended);
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
      return 0;
    v9 = (*(__int64 (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a4 + 152LL))(a4);
    v10 = 56;
    goto LABEL_299;
  }
  if ( a3 == (struct CListenerShell *)-2334LL )
  {
    v11 = TSTRBUFFER::AppendXmlStartElemWithPrefix(a2, L"ShellId", L"rsp", 1, 0, 0);
  }
  else
  {
    v12 = TSTRBUFFER::AppendXmlStartElemWithPrefix(a2, L"ShellId", L"rsp", 0, 0, 0);
    if ( v12 < 0 )
      goto LABEL_16;
    v12 = TSTRBUFFER::AppendEscapeXmlContent(a2, (const unsigned __int16 *)a3 + 1167, 0);
    if ( v12 < 0 )
      goto LABEL_16;
    v11 = TSTRBUFFER::AppendXmlEndElemWithPrefix(a2, L"ShellId", L"rsp");
  }
  v12 = v11;
  if ( v11 < 0 )
  {
LABEL_16:
    v13 = (unsigned __int16)v12;
    if ( (v12 & 0x1FFF0000) != 0x70000 )
      v13 = (unsigned int)v12;
    (*(void (__fastcall **)(struct IRequestContext *, __int64))(*(_QWORD *)a4 + 72LL))(a4, v13);
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
      return 0;
    v9 = (*(__int64 (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a4 + 152LL))(a4);
    v10 = 57;
    goto LABEL_299;
  }
  if ( v7 )
  {
    v14 = (const unsigned __int16 *)*((_QWORD *)a3 + 840);
    if ( v14 )
    {
      v15 = TSTRBUFFER::AppendXmlStartElemWithPrefix(a2, L"Name", L"rsp", 0, 0, 0);
      if ( v15 < 0
        || (v15 = TSTRBUFFER::AppendEscapeXmlContent(a2, v14, 0), v15 < 0)
        || (v15 = TSTRBUFFER::AppendXmlEndElemWithPrefix(a2, L"Name", L"rsp"), v15 < 0) )
      {
        v16 = (unsigned __int16)v15;
        if ( (v15 & 0x1FFF0000) != 0x70000 )
          v16 = (unsigned int)v15;
        (*(void (__fastcall **)(struct IRequestContext *, __int64))(*(_QWORD *)a4 + 72LL))(a4, v16);
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
          return 0;
        v9 = (*(__int64 (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a4 + 152LL))(a4);
        v10 = 58;
        goto LABEL_299;
      }
    }
  }
  Value = (const unsigned __int16 *)PacketParser::PacketElement<unsigned short const *>::GetValue(*((_QWORD *)a3 + 32) + 3024LL);
  if ( Value )
  {
    v19 = TSTRBUFFER::AppendXmlStartElemWithPrefix(a2, L"ResourceUri", L"rsp", 0, 0, 0);
    if ( v19 < 0 )
      goto LABEL_37;
    v19 = TSTRBUFFER::AppendEscapeXmlContent(a2, Value, 0);
    if ( v19 < 0 )
      goto LABEL_37;
    v18 = TSTRBUFFER::AppendXmlEndElemWithPrefix(a2, L"ResourceUri", L"rsp");
  }
  else
  {
    v18 = TSTRBUFFER::AppendXmlStartElemWithPrefix(a2, L"ResourceUri", L"rsp", 1, 0, 0);
  }
  v19 = v18;
  if ( v18 < 0 )
  {
LABEL_37:
    v20 = (unsigned __int16)v19;
    if ( (v19 & 0x1FFF0000) != 0x70000 )
      v20 = (unsigned int)v19;
    (*(void (__fastcall **)(struct IRequestContext *, __int64))(*(_QWORD *)a4 + 72LL))(a4, v20);
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
      return 0;
    v9 = (*(__int64 (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a4 + 152LL))(a4);
    v10 = 59;
    goto LABEL_299;
  }
  v21 = *(const unsigned __int16 **)(*((_QWORD *)a3 + 139) + 8LL);
  if ( v21 )
  {
    v23 = TSTRBUFFER::AppendXmlStartElemWithPrefix(a2, L"Owner", L"rsp", 0, 0, 0);
    if ( v23 < 0 )
      goto LABEL_48;
    v23 = TSTRBUFFER::AppendEscapeXmlContent(a2, v21, 0);
    if ( v23 < 0 )
      goto LABEL_48;
    v22 = TSTRBUFFER::AppendXmlEndElemWithPrefix(a2, L"Owner", L"rsp");
  }
  else
  {
    v22 = TSTRBUFFER::AppendXmlStartElemWithPrefix(a2, L"Owner", L"rsp", 1, 0, 0);
  }
  v23 = v22;
  if ( v22 < 0 )
  {
LABEL_48:
    v24 = (unsigned __int16)v23;
    if ( (v23 & 0x1FFF0000) != 0x70000 )
      v24 = (unsigned int)v23;
    (*(void (__fastcall **)(struct IRequestContext *, __int64))(*(_QWORD *)a4 + 72LL))(a4, v24);
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
      return 0;
    v9 = (*(__int64 (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a4 + 152LL))(a4);
    v10 = 60;
    goto LABEL_299;
  }
  v25 = (const unsigned __int16 *)(*((_QWORD *)a3 + 264) + 120LL);
  if ( *((_QWORD *)a3 + 264) == -120 )
  {
    v26 = TSTRBUFFER::AppendXmlStartElemWithPrefix(a2, L"ClientIP", L"rsp", 1, 0, 0);
  }
  else
  {
    v27 = TSTRBUFFER::AppendXmlStartElemWithPrefix(a2, L"ClientIP", L"rsp", 0, 0, 0);
    if ( v27 < 0 )
      goto LABEL_59;
    v27 = TSTRBUFFER::AppendEscapeXmlContent(a2, v25, 0);
    if ( v27 < 0 )
      goto LABEL_59;
    v26 = TSTRBUFFER::AppendXmlEndElemWithPrefix(a2, L"ClientIP", L"rsp");
  }
  v27 = v26;
  if ( v26 < 0 )
  {
LABEL_59:
    v28 = (unsigned __int16)v27;
    if ( (v27 & 0x1FFF0000) != 0x70000 )
      v28 = (unsigned int)v27;
    (*(void (__fastcall **)(struct IRequestContext *, __int64))(*(_QWORD *)a4 + 72LL))(a4, v28);
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
      return 0;
    v9 = (*(__int64 (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a4 + 152LL))(a4);
    v10 = 61;
    goto LABEL_299;
  }
  if ( v7 )
  {
    CurrentProcessId = GetCurrentProcessId();
    v30 = StringCchPrintfW(v95, 0xBu, L"%d", CurrentProcessId);
    if ( v30 < 0 )
    {
      if ( (v30 & 0x1FFF0000) == 0x70000 )
        v30 = (unsigned __int16)v30;
      (*(void (__fastcall **)(struct IRequestContext *, _QWORD))(*(_QWORD *)a4 + 72LL))(a4, (unsigned int)v30);
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
        return 0;
      v9 = (*(__int64 (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a4 + 152LL))(a4);
      v10 = 62;
      goto LABEL_299;
    }
    v31 = TSTRBUFFER::AppendXmlStartElemWithPrefix(a2, L"ProcessId", L"rsp", 0, 0, 0);
    if ( v31 < 0
      || (v31 = TSTRBUFFER::AppendEscapeXmlContent(a2, v95, 0), v31 < 0)
      || (v31 = TSTRBUFFER::AppendXmlEndElemWithPrefix(a2, L"ProcessId", L"rsp"), v31 < 0) )
    {
      v32 = (unsigned __int16)v31;
      if ( (v31 & 0x1FFF0000) != 0x70000 )
        v32 = (unsigned int)v31;
      (*(void (__fastcall **)(struct IRequestContext *, __int64))(*(_QWORD *)a4 + 72LL))(a4, v32);
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
        return 0;
      v9 = (*(__int64 (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a4 + 152LL))(a4);
      v10 = 63;
      goto LABEL_299;
    }
  }
  if ( *((_DWORD *)a3 + 1682) )
  {
    v33 = TSTRBUFFER::Append(a2, L"<");
    if ( v33 >= 0 )
    {
      v33 = TSTRBUFFER::Append(a2, L"rsp");
      if ( v33 >= 0 )
      {
        v33 = TSTRBUFFER::Append(a2, L":");
        if ( v33 >= 0 )
        {
          v33 = TSTRBUFFER::Append(a2, L"Environment");
          if ( v33 >= 0 )
          {
            v33 = TSTRBUFFER::Append(a2, L">");
            if ( v33 >= 0 )
            {
              for ( i = 0; i < *((_DWORD *)a3 + 1682); ++i )
              {
                v36 = *((_QWORD *)a3 + 842);
                v94[0] = L"Name";
                v37 = *(const unsigned __int16 **)(v36 + 16LL * i + 8);
                v94[1] = *(_QWORD *)(v36 + 16LL * i);
                if ( v37 )
                {
                  v39 = TSTRBUFFER::AppendXmlStartElemWithPrefix(
                          a2,
                          L"Variable",
                          L"rsp",
                          0,
                          1u,
                          (struct _XML_ATTRIB *)v94);
                  if ( v39 < 0 || (v39 = TSTRBUFFER::AppendEscapeXmlContent(a2, v37, 0), v39 < 0) )
                  {
LABEL_99:
                    v40 = (unsigned __int16)v39;
                    if ( (v39 & 0x1FFF0000) != 0x70000 )
                      v40 = (unsigned int)v39;
                    (*(void (__fastcall **)(struct IRequestContext *, __int64))(*(_QWORD *)a4 + 72LL))(a4, v40);
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
                    {
                      v9 = (*(__int64 (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a4 + 152LL))(a4);
                      v10 = 65;
                      goto LABEL_299;
                    }
                    return 0;
                  }
                  v38 = TSTRBUFFER::AppendXmlEndElemWithPrefix(a2, L"Variable", L"rsp");
                }
                else
                {
                  v38 = TSTRBUFFER::AppendXmlStartElemWithPrefix(
                          a2,
                          L"Variable",
                          L"rsp",
                          1,
                          1u,
                          (struct _XML_ATTRIB *)v94);
                }
                v39 = v38;
                if ( v38 < 0 )
                  goto LABEL_99;
              }
              v41 = TSTRBUFFER::Append(a2, L"</");
              if ( v41 >= 0 )
              {
                v41 = TSTRBUFFER::Append(a2, L"rsp");
                if ( v41 >= 0 )
                {
                  v41 = TSTRBUFFER::Append(a2, L":");
                  if ( v41 >= 0 )
                  {
                    v41 = TSTRBUFFER::Append(a2, L"Environment");
                    if ( v41 >= 0 )
                    {
                      v41 = TSTRBUFFER::Append(a2, L">");
                      if ( v41 >= 0 )
                        goto LABEL_114;
                    }
                  }
                }
              }
              v42 = (unsigned __int16)v41;
              if ( (v41 & 0x1FFF0000) != 0x70000 )
                v42 = (unsigned int)v41;
              (*(void (__fastcall **)(struct IRequestContext *, __int64))(*(_QWORD *)a4 + 72LL))(a4, v42);
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
              {
                v9 = (*(__int64 (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a4 + 152LL))(a4);
                v10 = 66;
                goto LABEL_299;
              }
              return 0;
            }
          }
        }
      }
    }
    v34 = (unsigned __int16)v33;
    if ( (v33 & 0x1FFF0000) != 0x70000 )
      v34 = (unsigned int)v33;
    (*(void (__fastcall **)(struct IRequestContext *, __int64))(*(_QWORD *)a4 + 72LL))(a4, v34);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      v9 = (*(__int64 (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a4 + 152LL))(a4);
      v10 = 64;
LABEL_299:
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, WPP_b60bdead82443c7f6980630edf2d3038_Traceguids, v9);
      return 0;
    }
    return 0;
  }
LABEL_114:
  v43 = (const unsigned __int16 *)*((_QWORD *)a3 + 838);
  if ( v43 )
  {
    v44 = TSTRBUFFER::AppendXmlStartElemWithPrefix(a2, L"WorkingDirectory", L"rsp", 0, 0, 0);
    if ( v44 < 0
      || (v44 = TSTRBUFFER::AppendEscapeXmlContent(a2, v43, 0), v44 < 0)
      || (v44 = TSTRBUFFER::AppendXmlEndElemWithPrefix(a2, L"WorkingDirectory", L"rsp"), v44 < 0) )
    {
      v45 = (unsigned __int16)v44;
      if ( (v44 & 0x1FFF0000) != 0x70000 )
        v45 = (unsigned int)v44;
      (*(void (__fastcall **)(struct IRequestContext *, __int64))(*(_QWORD *)a4 + 72LL))(a4, v45);
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
        return 0;
      v9 = (*(__int64 (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a4 + 152LL))(a4);
      v10 = 67;
      goto LABEL_299;
    }
  }
  v46 = *((_DWORD *)a3 + 1674);
  LODWORD(v92) = v46 % 0x3E8;
  v47 = StringCchPrintfW(v95, 0x14u, L"PT%u.%03uS", v46 / 0x3E8, v92);
  if ( v47 < 0 )
  {
    if ( (v47 & 0x1FFF0000) == 0x70000 )
      v47 = (unsigned __int16)v47;
    (*(void (__fastcall **)(struct IRequestContext *, _QWORD))(*(_QWORD *)a4 + 72LL))(a4, (unsigned int)v47);
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
      return 0;
    v9 = (*(__int64 (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a4 + 152LL))(a4);
    v10 = 68;
    goto LABEL_299;
  }
  v48 = TSTRBUFFER::AppendXmlStartElemWithPrefix(a2, L"IdleTimeOut", L"rsp", 0, 0, (struct _XML_ATTRIB *)v94);
  if ( v48 < 0
    || (v48 = TSTRBUFFER::AppendEscapeXmlContent(a2, v95, 0), v48 < 0)
    || (v48 = TSTRBUFFER::AppendXmlEndElemWithPrefix(a2, L"IdleTimeOut", L"rsp"), v48 < 0) )
  {
    v49 = (unsigned __int16)v48;
    if ( (v48 & 0x1FFF0000) != 0x70000 )
      v49 = (unsigned int)v48;
    (*(void (__fastcall **)(struct IRequestContext *, __int64))(*(_QWORD *)a4 + 72LL))(a4, v49);
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
      return 0;
    v9 = (*(__int64 (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a4 + 152LL))(a4);
    v10 = 69;
    goto LABEL_299;
  }
  v50 = *((_QWORD *)a3 + 835);
  if ( v50 && *(_DWORD *)v50 )
  {
    v51 = TSTRBUFFER::Append(a2, L"<");
    if ( v51 >= 0 )
    {
      v51 = TSTRBUFFER::Append(a2, L"rsp");
      if ( v51 >= 0 )
      {
        v51 = TSTRBUFFER::Append(a2, L":");
        if ( v51 >= 0 )
        {
          v51 = TSTRBUFFER::Append(a2, L"InputStreams");
          if ( v51 >= 0 )
          {
            v51 = TSTRBUFFER::Append(a2, L">");
            if ( v51 >= 0 )
            {
              for ( j = 0; j < *(_DWORD *)v50; ++j )
              {
                if ( (int)TSTRBUFFER::Append(a2, *(const unsigned __int16 **)(*(_QWORD *)(v50 + 8) + 8LL * j)) < 0 )
                {
                  (*(void (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a4 + 72LL))(a4);
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
                  {
                    v9 = (*(__int64 (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a4 + 152LL))(a4);
                    v10 = 71;
                    goto LABEL_299;
                  }
                  return 0;
                }
                if ( j != *(_DWORD *)v50 - 1 && (int)TSTRBUFFER::Append(a2, L" ") < 0 )
                {
                  (*(void (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a4 + 72LL))(a4);
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
                  {
                    v9 = (*(__int64 (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a4 + 152LL))(a4);
                    v10 = 72;
                    goto LABEL_299;
                  }
                  return 0;
                }
              }
              v54 = TSTRBUFFER::Append(a2, L"</");
              if ( v54 >= 0 )
              {
                v54 = TSTRBUFFER::Append(a2, L"rsp");
                if ( v54 >= 0 )
                {
                  v54 = TSTRBUFFER::Append(a2, L":");
                  if ( v54 >= 0 )
                  {
                    v54 = TSTRBUFFER::Append(a2, L"InputStreams");
                    if ( v54 >= 0 )
                    {
                      v54 = TSTRBUFFER::Append(a2, L">");
                      if ( v54 >= 0 )
                        goto LABEL_171;
                    }
                  }
                }
              }
              v55 = (unsigned __int16)v54;
              if ( (v54 & 0x1FFF0000) != 0x70000 )
                v55 = (unsigned int)v54;
              (*(void (__fastcall **)(struct IRequestContext *, __int64))(*(_QWORD *)a4 + 72LL))(a4, v55);
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
              {
                v9 = (*(__int64 (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a4 + 152LL))(a4);
                v10 = 73;
                goto LABEL_299;
              }
              return 0;
            }
          }
        }
      }
    }
    v52 = (unsigned __int16)v51;
    if ( (v51 & 0x1FFF0000) != 0x70000 )
      v52 = (unsigned int)v51;
    (*(void (__fastcall **)(struct IRequestContext *, __int64))(*(_QWORD *)a4 + 72LL))(a4, v52);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      v9 = (*(__int64 (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a4 + 152LL))(a4);
      v10 = 70;
      goto LABEL_299;
    }
    return 0;
  }
LABEL_171:
  v56 = *((_QWORD *)a3 + 836);
  if ( v56 && *(_DWORD *)v56 )
  {
    v57 = TSTRBUFFER::Append(a2, L"<");
    if ( v57 >= 0 )
    {
      v57 = TSTRBUFFER::Append(a2, L"rsp");
      if ( v57 >= 0 )
      {
        v57 = TSTRBUFFER::Append(a2, L":");
        if ( v57 >= 0 )
        {
          v57 = TSTRBUFFER::Append(a2, L"OutputStreams");
          if ( v57 >= 0 )
          {
            v57 = TSTRBUFFER::Append(a2, L">");
            if ( v57 >= 0 )
            {
              for ( k = 0; k < *(_DWORD *)v56; ++k )
              {
                if ( (int)TSTRBUFFER::Append(a2, *(const unsigned __int16 **)(*(_QWORD *)(v56 + 8) + 8LL * k)) < 0 )
                {
                  (*(void (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a4 + 72LL))(a4);
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
                  {
                    v9 = (*(__int64 (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a4 + 152LL))(a4);
                    v10 = 75;
                    goto LABEL_299;
                  }
                  return 0;
                }
                if ( k != *(_DWORD *)v56 - 1 && (int)TSTRBUFFER::Append(a2, L" ") < 0 )
                {
                  (*(void (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a4 + 72LL))(a4);
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
                  {
                    v9 = (*(__int64 (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a4 + 152LL))(a4);
                    v10 = 76;
                    goto LABEL_299;
                  }
                  return 0;
                }
              }
              v60 = TSTRBUFFER::Append(a2, L"</");
              if ( v60 >= 0 )
              {
                v60 = TSTRBUFFER::Append(a2, L"rsp");
                if ( v60 >= 0 )
                {
                  v60 = TSTRBUFFER::Append(a2, L":");
                  if ( v60 >= 0 )
                  {
                    v60 = TSTRBUFFER::Append(a2, L"OutputStreams");
                    if ( v60 >= 0 )
                    {
                      v60 = TSTRBUFFER::Append(a2, L">");
                      if ( v60 >= 0 )
                        goto LABEL_205;
                    }
                  }
                }
              }
              v61 = (unsigned __int16)v60;
              if ( (v60 & 0x1FFF0000) != 0x70000 )
                v61 = (unsigned int)v60;
              (*(void (__fastcall **)(struct IRequestContext *, __int64))(*(_QWORD *)a4 + 72LL))(a4, v61);
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
              {
                v9 = (*(__int64 (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a4 + 152LL))(a4);
                v10 = 77;
                goto LABEL_299;
              }
              return 0;
            }
          }
        }
      }
    }
    v58 = (unsigned __int16)v57;
    if ( (v57 & 0x1FFF0000) != 0x70000 )
      v58 = (unsigned int)v57;
    (*(void (__fastcall **)(struct IRequestContext *, __int64))(*(_QWORD *)a4 + 72LL))(a4, v58);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      v9 = (*(__int64 (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a4 + 152LL))(a4);
      v10 = 74;
      goto LABEL_299;
    }
    return 0;
  }
LABEL_205:
  if ( v7 )
  {
    v62 = *((_DWORD *)a3 + 1828);
    LODWORD(v93) = v62 % 0x3E8;
    v63 = StringCchPrintfW(v95, 0x14u, L"PT%u.%03uS", v62 / 0x3E8, v93);
    if ( v63 < 0 )
      goto LABEL_260;
    v63 = TSTRBUFFER::AppendXmlStartElemWithPrefix(a2, L"MaxIdleTimeOut", L"rsp", 0, 0, (struct _XML_ATTRIB *)v94);
    if ( v63 < 0 )
      goto LABEL_260;
    v63 = TSTRBUFFER::AppendEscapeXmlContent(a2, v95, 0);
    if ( v63 < 0 )
      goto LABEL_260;
    v63 = TSTRBUFFER::AppendXmlEndElemWithPrefix(a2, L"MaxIdleTimeOut", L"rsp");
    if ( v63 < 0 )
      goto LABEL_260;
    v64 = (const unsigned __int16 *)*((_QWORD *)a3 + 15);
    if ( v64 )
    {
      v63 = TSTRBUFFER::AppendXmlStartElemWithPrefix(a2, L"Locale", L"rsp", 0, 0, 0);
      if ( v63 < 0 )
        goto LABEL_260;
      v63 = TSTRBUFFER::AppendEscapeXmlContent(a2, v64, 0);
      if ( v63 < 0 )
        goto LABEL_260;
      v65 = TSTRBUFFER::AppendXmlEndElemWithPrefix(a2, L"Locale", L"rsp");
    }
    else
    {
      v65 = TSTRBUFFER::AppendXmlStartElemWithPrefix(a2, L"Locale", L"rsp", 1, 0, 0);
    }
    v63 = v65;
    if ( v65 < 0 )
      goto LABEL_260;
    v66 = (const unsigned __int16 *)*((_QWORD *)a3 + 20);
    if ( v66 )
    {
      v63 = TSTRBUFFER::AppendXmlStartElemWithPrefix(a2, L"DataLocale", L"rsp", 0, 0, 0);
      if ( v63 < 0 )
        goto LABEL_260;
      v63 = TSTRBUFFER::AppendEscapeXmlContent(a2, v66, 0);
      if ( v63 < 0 )
        goto LABEL_260;
      v67 = TSTRBUFFER::AppendXmlEndElemWithPrefix(a2, L"DataLocale", L"rsp");
    }
    else
    {
      v67 = TSTRBUFFER::AppendXmlStartElemWithPrefix(a2, L"DataLocale", L"rsp", 1, 0, 0);
    }
    v63 = v67;
    if ( v67 < 0 )
    {
LABEL_260:
      v77 = (unsigned __int16)v63;
      if ( (v63 & 0x1FFF0000) != 0x70000 )
        v77 = (unsigned int)v63;
      (*(void (__fastcall **)(struct IRequestContext *, __int64))(*(_QWORD *)a4 + 72LL))(a4, v77);
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
        return 0;
      v9 = (*(__int64 (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a4 + 152LL))(a4);
      v10 = 78;
      goto LABEL_299;
    }
    if ( *((_DWORD *)a3 + 1870) == 1 )
    {
      v63 = TSTRBUFFER::AppendXmlStartElemWithPrefix(a2, L"CompressionMode", L"rsp", 0, 0, 0);
      if ( v63 < 0 )
        goto LABEL_229;
      v68 = L"XpressCompression";
    }
    else
    {
      v63 = TSTRBUFFER::AppendXmlStartElemWithPrefix(a2, L"CompressionMode", L"rsp", 0, 0, 0);
      if ( v63 < 0 )
        goto LABEL_229;
      v68 = L"NoCompression";
    }
    v63 = TSTRBUFFER::AppendEscapeXmlContent(a2, v68, 0);
    if ( v63 >= 0 )
      v63 = TSTRBUFFER::AppendXmlEndElemWithPrefix(a2, L"CompressionMode", L"rsp");
LABEL_229:
    if ( v63 >= 0 )
    {
      v69 = L"Yes";
      if ( !*(_BYTE *)(*((_QWORD *)a3 + 264) + 484LL) )
        v69 = L"No";
      v63 = TSTRBUFFER::AppendXmlStartElemWithPrefix(a2, L"ProfileLoaded", L"rsp", 0, 0, 0);
      if ( v63 >= 0 )
      {
        v63 = TSTRBUFFER::AppendEscapeXmlContent(a2, v69, 0);
        if ( v63 >= 0 )
        {
          v63 = TSTRBUFFER::AppendXmlEndElemWithPrefix(a2, L"ProfileLoaded", L"rsp");
          if ( v63 >= 0 )
          {
            v70 = L"UTF16";
            if ( *(_DWORD *)(*((_QWORD *)a3 + 264) + 680LL) != 2 )
              v70 = L"UTF8";
            v63 = TSTRBUFFER::AppendXmlStartElemWithPrefix(a2, L"Encoding", L"rsp", 0, 0, 0);
            if ( v63 >= 0 )
            {
              v63 = TSTRBUFFER::AppendEscapeXmlContent(a2, v70, 0);
              if ( v63 >= 0 )
              {
                v63 = TSTRBUFFER::AppendXmlEndElemWithPrefix(a2, L"Encoding", L"rsp");
                if ( v63 >= 0 )
                {
                  v71 = L"Drop";
                  if ( *((_DWORD *)a3 + 2043) != 3 )
                    v71 = L"Block";
                  v72 = TSTRBUFFER::AppendXmlStartElemWithPrefix(a2, L"BufferMode", L"rsp", 0, 0, 0);
                  if ( v72 < 0
                    || (v72 = TSTRBUFFER::AppendEscapeXmlContent(a2, v71, 0), v72 < 0)
                    || (v72 = TSTRBUFFER::AppendXmlEndElemWithPrefix(a2, L"BufferMode", L"rsp"), v72 < 0) )
                  {
                    v73 = (unsigned __int16)v72;
                    if ( (v72 & 0x1FFF0000) != 0x70000 )
                      v73 = (unsigned int)v72;
                    (*(void (__fastcall **)(struct IRequestContext *, __int64))(*(_QWORD *)a4 + 72LL))(a4, v73);
                    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
                      return 0;
                    v9 = (*(__int64 (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a4 + 152LL))(a4);
                    v10 = 79;
                    goto LABEL_299;
                  }
                  v74 = L"Disconnected";
                  if ( ((*((_DWORD *)a3 + 2012) - 4) & 0xFFFFFFFD) != 0 )
                    v74 = L"Connected";
                  v75 = TSTRBUFFER::AppendXmlStartElemWithPrefix(a2, L"State", L"rsp", 0, 0, 0);
                  if ( v75 < 0
                    || (v75 = TSTRBUFFER::AppendEscapeXmlContent(a2, v74, 0), v75 < 0)
                    || (v75 = TSTRBUFFER::AppendXmlEndElemWithPrefix(a2, L"State", L"rsp"), v75 < 0) )
                  {
                    v76 = (unsigned __int16)v75;
                    if ( (v75 & 0x1FFF0000) != 0x70000 )
                      v76 = (unsigned int)v75;
                    (*(void (__fastcall **)(struct IRequestContext *, __int64))(*(_QWORD *)a4 + 72LL))(a4, v76);
                    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
                      return 0;
                    v9 = (*(__int64 (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a4 + 152LL))(a4);
                    v10 = 80;
                    goto LABEL_299;
                  }
                  goto LABEL_265;
                }
              }
            }
          }
        }
      }
    }
    goto LABEL_260;
  }
LABEL_265:
  TickCount64 = GetTickCount64();
  if ( !ShellProvider::FormatTimeDifference(v79, *((_QWORD *)a3 + 933), TickCount64, v96) )
  {
    v80 = *(void (__fastcall **)(struct IRequestContext *, _QWORD))(*(_QWORD *)a4 + 72LL);
    LastError = GetLastError();
    v80(a4, LastError);
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
      return 0;
    v9 = (*(__int64 (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a4 + 152LL))(a4);
    v10 = 81;
    goto LABEL_299;
  }
  v82 = TSTRBUFFER::AppendXmlStartElemWithPrefix(a2, L"ShellRunTime", L"rsp", 0, 0, 0);
  if ( v82 < 0
    || (v82 = TSTRBUFFER::AppendEscapeXmlContent(a2, v96, 0), v82 < 0)
    || (v83 = TSTRBUFFER::AppendXmlEndElemWithPrefix(a2, L"ShellRunTime", L"rsp"), v82 = v83, v83 < 0) )
  {
    v84 = (unsigned __int16)v82;
    if ( (v82 & 0x1FFF0000) != 0x70000 )
      v84 = (unsigned int)v82;
    (*(void (__fastcall **)(struct IRequestContext *, __int64))(*(_QWORD *)a4 + 72LL))(a4, v84);
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
      return 0;
    v9 = (*(__int64 (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a4 + 152LL))(a4);
    v10 = 82;
    goto LABEL_299;
  }
  if ( !ShellProvider::FormatTimeDifference((ShellProvider *)(unsigned int)v83, *((_QWORD *)a3 + 934), TickCount64, v96) )
  {
    v85 = *(void (__fastcall **)(struct IRequestContext *, _QWORD))(*(_QWORD *)a4 + 72LL);
    v86 = GetLastError();
    v85(a4, v86);
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
      return 0;
    v9 = (*(__int64 (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a4 + 152LL))(a4);
    v10 = 83;
    goto LABEL_299;
  }
  v87 = TSTRBUFFER::AppendXmlStartElemWithPrefix(a2, L"ShellInactivity", L"rsp", 0, 0, 0);
  if ( v87 < 0
    || (v87 = TSTRBUFFER::AppendEscapeXmlContent(a2, v96, 0), v87 < 0)
    || (v87 = TSTRBUFFER::AppendXmlEndElemWithPrefix(a2, L"ShellInactivity", L"rsp"), v87 < 0) )
  {
    v88 = (unsigned __int16)v87;
    if ( (v87 & 0x1FFF0000) != 0x70000 )
      v88 = (unsigned int)v87;
    (*(void (__fastcall **)(struct IRequestContext *, __int64))(*(_QWORD *)a4 + 72LL))(a4, v88);
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
      return 0;
    v9 = (*(__int64 (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a4 + 152LL))(a4);
    v10 = 84;
    goto LABEL_299;
  }
  v89 = TSTRBUFFER::Append(a2, L"</");
  if ( v89 < 0
    || (v89 = TSTRBUFFER::Append(a2, L"rsp"), v89 < 0)
    || (v89 = TSTRBUFFER::Append(a2, L":"), v89 < 0)
    || (v89 = TSTRBUFFER::Append(a2, L"Shell"), v89 < 0)
    || (v89 = TSTRBUFFER::Append(a2, L">"), v89 < 0) )
  {
    v90 = (unsigned __int16)v89;
    if ( (v89 & 0x1FFF0000) != 0x70000 )
      v90 = (unsigned int)v89;
    (*(void (__fastcall **)(struct IRequestContext *, __int64))(*(_QWORD *)a4 + 72LL))(a4, v90);
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
      return 0;
    v9 = (*(__int64 (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a4 + 152LL))(a4);
    v10 = 85;
    goto LABEL_299;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 86, WPP_b60bdead82443c7f6980630edf2d3038_Traceguids);
  return 1;
}

```

## disassembly

```asm
0x180031600  mov     [rsp-8+arg_0], rbx
0x180031605  push    rbp
0x180031606  push    rsi
0x180031607  push    rdi
0x180031608  push    r12
0x18003160a  push    r13
0x18003160c  push    r14
0x18003160e  push    r15
0x180031610  lea     rbp, [rsp-40h]
0x180031615  sub     rsp, 140h
0x18003161c  mov     rax, cs:__security_cookie
0x180031623  xor     rax, rsp
0x180031626  mov     [rbp+70h+var_38], rax
0x18003162a  mov     rdi, r9
0x18003162d  mov     r15, r8
0x180031630  mov     rbx, rdx
0x180031633  mov     rcx, cs:WPP_GLOBAL_Control
0x18003163a  lea     rax, WPP_GLOBAL_Control
0x180031641  mov     esi, 400h
0x180031646  cmp     rcx, rax
0x180031649  jz      short loc_180031665
0x18003164b  test    [rcx+1Ch], esi
0x18003164e  jz      short loc_180031665
0x180031650  mov     rcx, [rcx+10h]
0x180031654  lea     r8, WPP_b60bdead82443c7f6980630edf2d3038_Traceguids
0x18003165b  mov     edx, 37h ; '7'
0x180031660  call    WPP_SF_
0x180031665  lea     rcx, [r15+9C0h]
0x18003166c  mov     rax, [rcx]
0x18003166f  mov     rax, [rax+8]
0x180031673  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031678  xor     r13d, r13d
0x18003167b  lea     r14, aRsp_0; "rsp"
0x180031682  mov     [rsp+170h+var_138], r13; struct _XML_ATTRIB *
0x180031687  lea     rdx, aShell; "Shell"
0x18003168e  mov     r12b, al
0x180031691  mov     [rsp+170h+var_140], r13d; unsigned int
0x180031696  lea     rax, off_1801C40C8; "http://schemas.microsoft.com/wbem/wsman"...
0x18003169d  mov     dword ptr [rsp+170h+var_148], r13d; int
0x1800316a2  lea     r9d, [r13+1]; unsigned int
0x1800316a6  mov     [rsp+170h+var_150], rax; struct _XML_NAMESPACE_PREFIX *
0x1800316ab  mov     r8, r14; unsigned __int16 *
0x1800316ae  mov     rcx, rbx; this
0x1800316b1  call    ?AppendXmlStartElemWithNamespacesAndPrefixes@TSTRBUFFER@@QEAAJPEBG0KPEAU_XML_NAMESPACE_PREFIX@@HKPEAU_XML_ATTRIB@@@Z; TSTRBUFFER::AppendXmlStartElemWithNamespacesAndPrefixes(ushort const *,ushort const *,ulong,_XML_NAMESPACE_PREFIX *,int,ulong,_XML_ATTRIB *)
0x1800316b6  test    eax, eax
0x1800316b8  jns     short loc_18003171D
0x1800316ba  mov     rcx, [rdi]
0x1800316bd  mov     r8, [rcx+48h]
0x1800316c1  mov     ecx, eax
0x1800316c3  and     ecx, 1FFF0000h
0x1800316c9  cmp     ecx, 70000h
0x1800316cf  jnz     short loc_1800316D4
0x1800316d1  movzx   eax, ax
0x1800316d4  mov     edx, eax
0x1800316d6  mov     rcx, rdi
0x1800316d9  mov     rax, r8
0x1800316dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800316e1  mov     rax, cs:WPP_GLOBAL_Control
0x1800316e8  lea     rdx, WPP_GLOBAL_Control
0x1800316ef  cmp     rax, rdx
0x1800316f2  jz      loc_180032EE9
0x1800316f8  test    [rax+1Ch], esi
0x1800316fb  jz      loc_180032EE9
0x180031701  mov     rax, [rdi]
0x180031704  mov     rcx, rdi
0x180031707  mov     rax, [rax+98h]
0x18003170e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031713  mov     edx, 38h ; '8'
0x180031718  jmp     loc_180032ECF
0x18003171d  lea     rsi, [r15+91Eh]
0x180031724  mov     [rsp+170h+var_148], r13; struct _XML_ATTRIB *
0x180031729  mov     dword ptr [rsp+170h+var_150], r13d; unsigned int
0x18003172e  mov     r8, r14; unsigned __int16 *
0x180031731  lea     rdx, aShellid_0; "ShellId"
0x180031738  mov     rcx, rbx; this
0x18003173b  test    rsi, rsi
0x18003173e  jnz     short loc_18003174B
0x180031740  lea     r9d, [rsi+1]; int
0x180031744  call    ?AppendXmlStartElemWithPrefix@TSTRBUFFER@@QEAAJPEBG0HKPEAU_XML_ATTRIB@@@Z; TSTRBUFFER::AppendXmlStartElemWithPrefix(ushort const *,ushort const *,int,ulong,_XML_ATTRIB *)
0x180031749  jmp     short loc_18003177F
0x18003174b  xor     r9d, r9d; int
0x18003174e  call    ?AppendXmlStartElemWithPrefix@TSTRBUFFER@@QEAAJPEBG0HKPEAU_XML_ATTRIB@@@Z; TSTRBUFFER::AppendXmlStartElemWithPrefix(ushort const *,ushort const *,int,ulong,_XML_ATTRIB *)
0x180031753  mov     ecx, eax
0x180031755  test    eax, eax
0x180031757  js      short loc_180031785
0x180031759  xor     r8d, r8d; bool
0x18003175c  mov     rdx, rsi; unsigned __int16 *
0x18003175f  mov     rcx, rbx; this
0x180031762  call    ?AppendEscapeXmlContent@TSTRBUFFER@@QEAAJPEBG_N@Z; TSTRBUFFER::AppendEscapeXmlContent(ushort const *,bool)
0x180031767  mov     ecx, eax
0x180031769  test    eax, eax
0x18003176b  js      short loc_180031785
0x18003176d  mov     r8, r14; unsigned __int16 *
0x180031770  lea     rdx, aShellid_0; "ShellId"
0x180031777  mov     rcx, rbx; this
0x18003177a  call    ?AppendXmlEndElemWithPrefix@TSTRBUFFER@@QEAAJPEBG0@Z; TSTRBUFFER::AppendXmlEndElemWithPrefix(ushort const *,ushort const *)
0x18003177f  mov     ecx, eax
0x180031781  test    eax, eax
0x180031783  jns     short loc_1800317E6
0x180031785  mov     r8, [rdi]
0x180031788  mov     eax, ecx
0x18003178a  and     eax, 1FFF0000h
0x18003178f  movzx   edx, cx
0x180031792  cmp     eax, 70000h
0x180031797  mov     rax, [r8+48h]
0x18003179b  cmovnz  edx, ecx
0x18003179e  mov     rcx, rdi
0x1800317a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800317a6  mov     rax, cs:WPP_GLOBAL_Control
0x1800317ad  lea     rdx, WPP_GLOBAL_Control
0x1800317b4  cmp     rax, rdx
0x1800317b7  jz      loc_180032EE9
0x1800317bd  test    dword ptr [rax+1Ch], 400h
0x1800317c4  jz      loc_180032EE9
0x1800317ca  mov     rax, [rdi]
0x1800317cd  mov     rcx, rdi
0x1800317d0  mov     rax, [rax+98h]
0x1800317d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800317dc  mov     edx, 39h ; '9'
0x1800317e1  jmp     loc_180032ECF
0x1800317e6  test    r12b, r12b
0x1800317e9  jz      loc_1800318B1
0x1800317ef  mov     rsi, [r15+1A40h]
0x1800317f6  test    rsi, rsi
0x1800317f9  jz      loc_1800318B1
0x1800317ff  mov     [rsp+170h+var_148], r13; struct _XML_ATTRIB *
0x180031804  lea     rdx, aName; "Name"
0x18003180b  xor     r9d, r9d; int
0x18003180e  mov     dword ptr [rsp+170h+var_150], r13d; unsigned int
0x180031813  mov     r8, r14; unsigned __int16 *
0x180031816  mov     rcx, rbx; this
0x180031819  call    ?AppendXmlStartElemWithPrefix@TSTRBUFFER@@QEAAJPEBG0HKPEAU_XML_ATTRIB@@@Z; TSTRBUFFER::AppendXmlStartElemWithPrefix(ushort const *,ushort const *,int,ulong,_XML_ATTRIB *)
0x18003181e  mov     ecx, eax
0x180031820  test    eax, eax
0x180031822  js      short loc_180031850
0x180031824  xor     r8d, r8d; bool
0x180031827  mov     rdx, rsi; unsigned __int16 *
0x18003182a  mov     rcx, rbx; this
0x18003182d  call    ?AppendEscapeXmlContent@TSTRBUFFER@@QEAAJPEBG_N@Z; TSTRBUFFER::AppendEscapeXmlContent(ushort const *,bool)
0x180031832  mov     ecx, eax
0x180031834  test    eax, eax
0x180031836  js      short loc_180031850
0x180031838  mov     r8, r14; unsigned __int16 *
0x18003183b  lea     rdx, aName; "Name"
0x180031842  mov     rcx, rbx; this
0x180031845  call    ?AppendXmlEndElemWithPrefix@TSTRBUFFER@@QEAAJPEBG0@Z; TSTRBUFFER::AppendXmlEndElemWithPrefix(ushort const *,ushort const *)
0x18003184a  mov     ecx, eax
0x18003184c  test    eax, eax
0x18003184e  jns     short loc_1800318B1
0x180031850  mov     r8, [rdi]
0x180031853  mov     eax, ecx
0x180031855  and     eax, 1FFF0000h
0x18003185a  movzx   edx, cx
0x18003185d  cmp     eax, 70000h
0x180031862  mov     rax, [r8+48h]
0x180031866  cmovnz  edx, ecx
0x180031869  mov     rcx, rdi
0x18003186c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031871  mov     rax, cs:WPP_GLOBAL_Control
0x180031878  lea     rdx, WPP_GLOBAL_Control
0x18003187f  cmp     rax, rdx
0x180031882  jz      loc_180032EE9
0x180031888  test    dword ptr [rax+1Ch], 400h
0x18003188f  jz      loc_180032EE9
0x180031895  mov     rax, [rdi]
0x180031898  mov     rcx, rdi
0x18003189b  mov     rax, [rax+98h]
0x1800318a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800318a7  mov     edx, 3Ah ; ':'
0x1800318ac  jmp     loc_180032ECF
0x1800318b1  mov     rcx, [r15+100h]
0x1800318b8  add     rcx, 0BD0h
0x1800318bf  call    ?GetValue@?$PacketElement@PEBG@PacketParser@@QEBAPEBGXZ; PacketParser::PacketElement<ushort const *>::GetValue(void)
0x1800318c4  mov     [rsp+170h+var_148], r13; struct _XML_ATTRIB *
0x1800318c9  mov     rsi, rax
0x1800318cc  mov     dword ptr [rsp+170h+var_150], r13d; unsigned int
0x1800318d1  mov     r8, r14; unsigned __int16 *
0x1800318d4  lea     rdx, aResourceuri; "ResourceUri"
0x1800318db  mov     rcx, rbx; this
0x1800318de  test    rax, rax
0x1800318e1  jnz     short loc_1800318EE
0x1800318e3  lea     r9d, [rax+1]; int
0x1800318e7  call    ?AppendXmlStartElemWithPrefix@TSTRBUFFER@@QEAAJPEBG0HKPEAU_XML_ATTRIB@@@Z; TSTRBUFFER::AppendXmlStartElemWithPrefix(ushort const *,ushort const *,int,ulong,_XML_ATTRIB *)
0x1800318ec  jmp     short loc_180031922
0x1800318ee  xor     r9d, r9d; int
0x1800318f1  call    ?AppendXmlStartElemWithPrefix@TSTRBUFFER@@QEAAJPEBG0HKPEAU_XML_ATTRIB@@@Z; TSTRBUFFER::AppendXmlStartElemWithPrefix(ushort const *,ushort const *,int,ulong,_XML_ATTRIB *)
0x1800318f6  mov     ecx, eax
0x1800318f8  test    eax, eax
0x1800318fa  js      short loc_180031928
0x1800318fc  xor     r8d, r8d; bool
0x1800318ff  mov     rdx, rsi; unsigned __int16 *
0x180031902  mov     rcx, rbx; this
0x180031905  call    ?AppendEscapeXmlContent@TSTRBUFFER@@QEAAJPEBG_N@Z; TSTRBUFFER::AppendEscapeXmlContent(ushort const *,bool)
0x18003190a  mov     ecx, eax
0x18003190c  test    eax, eax
0x18003190e  js      short loc_180031928
0x180031910  mov     r8, r14; unsigned __int16 *
0x180031913  lea     rdx, aResourceuri; "ResourceUri"
0x18003191a  mov     rcx, rbx; this
0x18003191d  call    ?AppendXmlEndElemWithPrefix@TSTRBUFFER@@QEAAJPEBG0@Z; TSTRBUFFER::AppendXmlEndElemWithPrefix(ushort const *,ushort const *)
0x180031922  mov     ecx, eax
0x180031924  test    eax, eax
0x180031926  jns     short loc_180031989
0x180031928  mov     r8, [rdi]
0x18003192b  mov     eax, ecx
0x18003192d  and     eax, 1FFF0000h
0x180031932  movzx   edx, cx
0x180031935  cmp     eax, 70000h
0x18003193a  mov     rax, [r8+48h]
0x18003193e  cmovnz  edx, ecx
0x180031941  mov     rcx, rdi
0x180031944  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031949  mov     rax, cs:WPP_GLOBAL_Control
0x180031950  lea     rdx, WPP_GLOBAL_Control
0x180031957  cmp     rax, rdx
0x18003195a  jz      loc_180032EE9
0x180031960  test    dword ptr [rax+1Ch], 400h
0x180031967  jz      loc_180032EE9
0x18003196d  mov     rax, [rdi]
0x180031970  mov     rcx, rdi
0x180031973  mov     rax, [rax+98h]
0x18003197a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003197f  mov     edx, 3Bh ; ';'
0x180031984  jmp     loc_180032ECF
0x180031989  mov     rax, [r15+458h]
0x180031990  lea     rdx, aOwner; "Owner"
0x180031997  mov     [rsp+170h+var_148], r13; struct _XML_ATTRIB *
0x18003199c  mov     r8, r14; unsigned __int16 *
0x18003199f  mov     rcx, rbx; this
0x1800319a2  mov     dword ptr [rsp+170h+var_150], r13d; unsigned int
0x1800319a7  mov     rsi, [rax+8]
0x1800319ab  test    rsi, rsi
0x1800319ae  jnz     short loc_1800319BB
0x1800319b0  lea     r9d, [rsi+1]; int
0x1800319b4  call    ?AppendXmlStartElemWithPrefix@TSTRBUFFER@@QEAAJPEBG0HKPEAU_XML_ATTRIB@@@Z; TSTRBUFFER::AppendXmlStartElemWithPrefix(ushort const *,ushort const *,int,ulong,_XML_ATTRIB *)
0x1800319b9  jmp     short loc_1800319EF
0x1800319bb  xor     r9d, r9d; int
0x1800319be  call    ?AppendXmlStartElemWithPrefix@TSTRBUFFER@@QEAAJPEBG0HKPEAU_XML_ATTRIB@@@Z; TSTRBUFFER::AppendXmlStartElemWithPrefix(ushort const *,ushort const *,int,ulong,_XML_ATTRIB *)
0x1800319c3  mov     ecx, eax
0x1800319c5  test    eax, eax
0x1800319c7  js      short loc_1800319F5
0x1800319c9  xor     r8d, r8d; bool
0x1800319cc  mov     rdx, rsi; unsigned __int16 *
0x1800319cf  mov     rcx, rbx; this
0x1800319d2  call    ?AppendEscapeXmlContent@TSTRBUFFER@@QEAAJPEBG_N@Z; TSTRBUFFER::AppendEscapeXmlContent(ushort const *,bool)
0x1800319d7  mov     ecx, eax
0x1800319d9  test    eax, eax
0x1800319db  js      short loc_1800319F5
0x1800319dd  mov     r8, r14; unsigned __int16 *
0x1800319e0  lea     rdx, aOwner; "Owner"
0x1800319e7  mov     rcx, rbx; this
0x1800319ea  call    ?AppendXmlEndElemWithPrefix@TSTRBUFFER@@QEAAJPEBG0@Z; TSTRBUFFER::AppendXmlEndElemWithPrefix(ushort const *,ushort const *)
0x1800319ef  mov     ecx, eax
0x1800319f1  test    eax, eax
0x1800319f3  jns     short loc_180031A56
0x1800319f5  mov     r8, [rdi]
0x1800319f8  mov     eax, ecx
0x1800319fa  and     eax, 1FFF0000h
0x1800319ff  movzx   edx, cx
0x180031a02  cmp     eax, 70000h
0x180031a07  mov     rax, [r8+48h]
0x180031a0b  cmovnz  edx, ecx
0x180031a0e  mov     rcx, rdi
0x180031a11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031a16  mov     rax, cs:WPP_GLOBAL_Control
0x180031a1d  lea     rdx, WPP_GLOBAL_Control
0x180031a24  cmp     rax, rdx
0x180031a27  jz      loc_180032EE9
0x180031a2d  test    dword ptr [rax+1Ch], 400h
0x180031a34  jz      loc_180032EE9
0x180031a3a  mov     rax, [rdi]
0x180031a3d  mov     rcx, rdi
0x180031a40  mov     rax, [rax+98h]
0x180031a47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031a4c  mov     edx, 3Ch ; '<'
0x180031a51  jmp     loc_180032ECF
0x180031a56  mov     rsi, [r15+840h]
0x180031a5d  lea     rdx, aClientip; "ClientIP"
0x180031a64  mov     [rsp+170h+var_148], r13; struct _XML_ATTRIB *
0x180031a69  mov     r8, r14; unsigned __int16 *
0x180031a6c  mov     dword ptr [rsp+170h+var_150], r13d; unsigned int
0x180031a71  mov     rcx, rbx; this
0x180031a74  add     rsi, 78h ; 'x'
0x180031a78  jnz     short loc_180031A87
0x180031a7a  mov     r9d, 1; int
0x180031a80  call    ?AppendXmlStartElemWithPrefix@TSTRBUFFER@@QEAAJPEBG0HKPEAU_XML_ATTRIB@@@Z; TSTRBUFFER::AppendXmlStartElemWithPrefix(ushort const *,ushort const *,int,ulong,_XML_ATTRIB *)
0x180031a85  jmp     short loc_180031ABB
0x180031a87  xor     r9d, r9d; int
0x180031a8a  call    ?AppendXmlStartElemWithPrefix@TSTRBUFFER@@QEAAJPEBG0HKPEAU_XML_ATTRIB@@@Z; TSTRBUFFER::AppendXmlStartElemWithPrefix(ushort const *,ushort const *,int,ulong,_XML_ATTRIB *)
0x180031a8f  mov     ecx, eax
0x180031a91  test    eax, eax
0x180031a93  js      short loc_180031AC1
0x180031a95  xor     r8d, r8d; bool
0x180031a98  mov     rdx, rsi; unsigned __int16 *
0x180031a9b  mov     rcx, rbx; this
0x180031a9e  call    ?AppendEscapeXmlContent@TSTRBUFFER@@QEAAJPEBG_N@Z; TSTRBUFFER::AppendEscapeXmlContent(ushort const *,bool)
0x180031aa3  mov     ecx, eax
0x180031aa5  test    eax, eax
0x180031aa7  js      short loc_180031AC1
0x180031aa9  mov     r8, r14; unsigned __int16 *
  ... truncated ...
```
