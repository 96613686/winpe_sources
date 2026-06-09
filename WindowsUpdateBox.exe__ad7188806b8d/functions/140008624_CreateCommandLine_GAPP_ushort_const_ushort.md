# CreateCommandLine(_GAPP *,ushort const *,ushort * *)

- ea: `0x140008624`
- end: `0x140008dcc`
- name: `?CreateCommandLine@@YAJPEAU_GAPP@@PEBGPEAPEAG@Z`
- size: `1960`
- prototype: `__int64 __fastcall(struct _GAPP *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140013894`

## callees

- `0x140002a98`
- `0x140005e4c`
- `0x1400076c8`
- `0x140008624`
- `0x140009f00`
- `0x1400135b8`
- `0x140016bb4`
- `0x14001d4ac`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140008b53`
- `KERNEL32!HeapFree` at `0x140008c8b`
- `KERNEL32!HeapFree` at `0x140008d70`
- `KERNEL32!HeapFree` at `0x140008d9d`
- `KERNEL32!HeapFree` at `0x140008b53`
- `KERNEL32!HeapFree` at `0x140008c8b`
- `KERNEL32!HeapFree` at `0x140008d70`
- `KERNEL32!HeapFree` at `0x140008d9d`
- `KERNEL32!GetProcessHeap` at `0x140008b3e`
- `KERNEL32!GetProcessHeap` at `0x140008c76`
- `KERNEL32!GetProcessHeap` at `0x140008d5c`
- `KERNEL32!GetProcessHeap` at `0x140008d88`
- `KERNEL32!GetProcessHeap` at `0x140008b3e`
- `KERNEL32!GetProcessHeap` at `0x140008c76`
- `KERNEL32!GetProcessHeap` at `0x140008d5c`
- `KERNEL32!GetProcessHeap` at `0x140008d88`

## string_xrefs

- `0x1400086ca`: `%s /InstallFile "%s"`
- `0x140008708`: `%s /progressCLSID %s`
- `0x140008ab9`: `/Update %s`
- `0x140008cea`: `/Install %s`
- `0x140008ccf`: `/RollbackSys %s`
- `0x140008ca0`: `/RollbackUser %s`
- `0x140008cfc`: `/Product ComputeHost %s`
- `0x140008c2c`: `CreateCommandLine`

## pseudocode

```c
__int64 __fastcall CreateCommandLine(struct _GAPP *a1, const unsigned __int16 *a2, unsigned __int16 **a3)
{
  __int64 v3; // r12
  __int64 v7; // rsi
  unsigned int v8; // edi
  __int64 v9; // rcx
  int StringCch; // eax
  int Internal; // eax
  int v12; // eax
  unsigned __int16 *v13; // rdx
  unsigned __int16 *v14; // rdx
  unsigned __int16 *v15; // rdx
  unsigned __int16 *v16; // rdx
  unsigned __int16 *v17; // rdx
  unsigned __int16 *v18; // rdx
  unsigned __int16 *v19; // rdx
  unsigned __int16 *v20; // rdx
  unsigned __int16 *v21; // rdx
  unsigned __int16 *v22; // rdx
  unsigned __int16 *v23; // rdx
  unsigned __int16 *v24; // rdx
  unsigned __int16 *v25; // rdx
  unsigned __int16 *v26; // rdx
  unsigned __int16 *v27; // rdi
  unsigned __int16 *v28; // rbx
  int v29; // eax
  int v30; // eax
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v32; // rbx
  int v33; // ecx
  int v34; // ecx
  int v35; // ecx
  int v36; // ecx
  int v37; // ecx
  const unsigned __int16 *v38; // rdx
  __int64 v39; // r9
  HANDLE v40; // rcx
  __int64 v41; // rcx
  HANDLE v42; // rax
  const unsigned __int16 *v43; // rdx
  unsigned __int16 *v44; // rdx
  unsigned __int16 *v45; // rbx
  HANDLE v46; // rax
  HANDLE v47; // rax
  _QWORD v49[2]; // [rsp+30h] [rbp-10h] BYREF
  unsigned __int16 *v50; // [rsp+70h] [rbp+30h] BYREF
  unsigned __int16 *v51; // [rsp+88h] [rbp+48h] BYREF

  v3 = 0;
  v49[0] = 0;
  v51 = 0;
  v7 = 0;
  if ( !a1 || !a3 )
  {
    v8 = -2147024809;
LABEL_3:
    v9 = v8;
LABEL_102:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v9);
    goto LABEL_103;
  }
  LODWORD(v50) = 0;
  StringCch = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(&dword_1400860C4, &v50, 0x7FFFFFFF);
  v8 = StringCch;
  if ( StringCch >= 0 )
  {
    Internal = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal((void *)&dword_1400860C4);
    v8 = Internal;
    if ( Internal < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)Internal);
    v7 = v49[0];
  }
  else
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)StringCch);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v8);
  if ( (v8 & 0x80000000) != 0 )
    goto LABEL_3;
  if ( a2 )
  {
    v12 = STRAPI_Format(&v51, L"%s /InstallFile \"%s\"", v7, a2);
    v8 = v12;
    if ( v12 < 0 )
      goto LABEL_101;
    v13 = v51;
    v51 = 0;
    SH<unsigned short *,SH_SSTRING>::Attach(v49, v13);
    v7 = v49[0];
  }
  if ( *((_QWORD *)a1 + 2) )
  {
    v12 = STRAPI_Format(&v51, L"%s /progressCLSID %s", v7);
    v8 = v12;
    if ( v12 < 0 )
      goto LABEL_101;
    v14 = v51;
    v51 = 0;
    SH<unsigned short *,SH_SSTRING>::Attach(v49, v14);
    v7 = v49[0];
  }
  if ( *((_QWORD *)a1 + 3) )
  {
    v12 = STRAPI_Format(&v51, L"%s /ReportId %s", v7);
    v8 = v12;
    if ( v12 < 0 )
      goto LABEL_101;
    v15 = v51;
    v51 = 0;
    SH<unsigned short *,SH_SSTRING>::Attach(v49, v15);
    v7 = v49[0];
  }
  if ( *((_QWORD *)a1 + 5) )
  {
    v12 = STRAPI_Format(&v51, L"%s /FlightData \"%s\"", v7);
    v8 = v12;
    if ( v12 < 0 )
      goto LABEL_101;
    v16 = v51;
    v51 = 0;
    SH<unsigned short *,SH_SSTRING>::Attach(v49, v16);
    v7 = v49[0];
  }
  if ( *((_DWORD *)a1 + 18) )
  {
    v12 = STRAPI_Format(&v51, L"/Override %s", v7);
    v8 = v12;
    if ( v12 < 0 )
      goto LABEL_101;
    v17 = v51;
    v51 = 0;
    SH<unsigned short *,SH_SSTRING>::Attach(v49, v17);
    v7 = v49[0];
  }
  if ( *((_DWORD *)a1 + 19) )
  {
    v12 = STRAPI_Format(&v51, L"/Selfhost %s", v7);
    v8 = v12;
    if ( v12 < 0 )
      goto LABEL_101;
    v18 = v51;
    v51 = 0;
    SH<unsigned short *,SH_SSTRING>::Attach(v49, v18);
    v7 = v49[0];
  }
  if ( *((_DWORD *)a1 + 17) )
  {
    v12 = STRAPI_Format(&v51, L"/Console %s", v7);
    v8 = v12;
    if ( v12 < 0 )
      goto LABEL_101;
    v19 = v51;
    v51 = 0;
    SH<unsigned short *,SH_SSTRING>::Attach(v49, v19);
    v7 = v49[0];
  }
  if ( *((_DWORD *)a1 + 20) )
  {
    v12 = STRAPI_Format(&v51, L"/Quiet %s", v7);
    v8 = v12;
    if ( v12 < 0 )
      goto LABEL_101;
    v20 = v51;
    v51 = 0;
    SH<unsigned short *,SH_SSTRING>::Attach(v49, v20);
    v7 = v49[0];
  }
  if ( *((_DWORD *)a1 + 21) )
  {
    v12 = STRAPI_Format(&v51, L"/ExpressPackage %s", v7);
    v8 = v12;
    if ( v12 < 0 )
      goto LABEL_101;
    v21 = v51;
    v51 = 0;
    SH<unsigned short *,SH_SSTRING>::Attach(v49, v21);
    v7 = v49[0];
  }
  if ( *((_DWORD *)a1 + 23) )
  {
    v12 = STRAPI_Format(&v51, L"/Prompt Defer %s", v7);
    v8 = v12;
    if ( v12 < 0 )
      goto LABEL_101;
    v22 = v51;
    v51 = 0;
    SH<unsigned short *,SH_SSTRING>::Attach(v49, v22);
    v7 = v49[0];
  }
  if ( *((_DWORD *)a1 + 24) )
  {
    v12 = STRAPI_Format(&v51, L"/Eula Accept %s", v7);
    v8 = v12;
    if ( v12 < 0 )
      goto LABEL_101;
    v23 = v51;
    v51 = 0;
    SH<unsigned short *,SH_SSTRING>::Attach(v49, v23);
    v7 = v49[0];
  }
  if ( *((_DWORD *)a1 + 25) )
  {
    v12 = STRAPI_Format(&v51, L"/Eula Defer %s", v7);
    v8 = v12;
    if ( v12 < 0 )
      goto LABEL_101;
    v24 = v51;
    v51 = 0;
    SH<unsigned short *,SH_SSTRING>::Attach(v49, v24);
    v7 = v49[0];
  }
  if ( *((_DWORD *)a1 + 26) )
  {
    v12 = STRAPI_Format(&v51, L"/Priority Normal %s", v7);
    v8 = v12;
    if ( v12 < 0 )
      goto LABEL_101;
    v25 = v51;
    v51 = 0;
    SH<unsigned short *,SH_SSTRING>::Attach(v49, v25);
    v7 = v49[0];
  }
  switch ( *((_DWORD *)a1 + 29) )
  {
    case 1:
      v12 = STRAPI_Format(&v51, L"/Media %s", v7);
      break;
    case 2:
      v12 = STRAPI_Format(&v51, L"/Recovery %s", v7);
      break;
    case 4:
      v12 = STRAPI_Format(&v51, L"/Boot %s", v7);
      break;
    case 5:
      v12 = STRAPI_Format(&v51, L"/Update %s", v7);
      break;
    case 6:
      v12 = STRAPI_Format(&v51, L"/Package %s", v7);
      break;
    case 7:
      v12 = STRAPI_Format(&v51, L"/Web %s", v7);
      break;
    case 8:
      v12 = STRAPI_Format(&v51, L"/AzureHost %s", v7);
      break;
    case 9:
      v12 = STRAPI_Format(&v51, L"/Servicing %s", v7);
      break;
    default:
      goto LABEL_60;
  }
  v8 = v12;
  if ( v12 < 0 )
    goto LABEL_101;
LABEL_60:
  v26 = v51;
  v51 = 0;
  v27 = 0;
  SH<unsigned short *,SH_SSTRING>::Attach(v49, v26);
  switch ( *((_DWORD *)a1 + 30) )
  {
    case 1:
      v43 = L"/PreDownload %s";
      goto LABEL_111;
    case 2:
      v43 = L"/Install %s";
      goto LABEL_111;
    case 3:
      v43 = L"/Finalize %s";
      goto LABEL_111;
    case 4:
      v43 = L"/Success %s";
      goto LABEL_111;
    case 5:
      v43 = L"/RollbackSys %s";
      goto LABEL_111;
    case 8:
      v43 = L"/Download %s";
      goto LABEL_111;
    case 0xA:
      v43 = L"/RollbackUser %s";
LABEL_111:
      v7 = v49[0];
      v12 = STRAPI_Format(&v51, v43, v49[0]);
      v8 = v12;
      if ( v12 < 0 )
        goto LABEL_101;
LABEL_87:
      v27 = v51;
      goto LABEL_88;
  }
  if ( *((_DWORD *)a1 + 30) != 11 )
  {
LABEL_88:
    v32 = 0;
    v51 = 0;
    SH<unsigned short *,SH_SSTRING>::Attach(v49, v27);
    v33 = *((_DWORD *)a1 + 32);
    if ( !v33 )
      goto LABEL_98;
    v34 = v33 - 1;
    if ( v34 )
    {
      v35 = v34 - 1;
      if ( v35 )
      {
        v36 = v35 - 2;
        if ( v36 )
        {
          v37 = v36 - 2;
          if ( v37 )
          {
            if ( v37 != 1 )
            {
LABEL_97:
              v51 = 0;
              SH<unsigned short *,SH_SSTRING>::Attach(v49, v32);
LABEL_98:
              v39 = *((_QWORD *)a1 + 1);
              v7 = v49[0];
              if ( !v39 )
                v39 = 0;
              v12 = STRAPI_Format(&v51, L"%s%s", v49[0], v39);
              v8 = v12;
              if ( v12 >= 0 )
              {
                v44 = v51;
                v51 = 0;
                SH<unsigned short *,SH_SSTRING>::Attach(v49, v44);
                v7 = 0;
                *a3 = (unsigned __int16 *)v49[0];
                goto LABEL_124;
              }
              goto LABEL_101;
            }
            v38 = L"/Product CloudHost %s";
          }
          else
          {
            v38 = L"/Product ComputeHost %s";
          }
        }
        else
        {
          v38 = L"/Product AzsHci %s";
        }
      }
      else
      {
        v38 = L"/Product Server %s";
      }
    }
    else
    {
      v38 = L"/Product Client %s";
    }
    v7 = v49[0];
    v12 = STRAPI_Format(&v51, v38, v49[0]);
    v8 = v12;
    if ( v12 >= 0 )
    {
      v32 = v51;
      goto LABEL_97;
    }
LABEL_101:
    v9 = (unsigned int)v12;
    goto LABEL_102;
  }
  v7 = v49[0];
  while ( 1 )
  {
    if ( (*((_DWORD *)a1 + 31) & (unsigned int)v3) == 0 )
      goto LABEL_86;
    v28 = 0;
    v50 = 0;
    if ( (_DWORD)v3 == 1 )
    {
      v29 = STRAPI_Format(&v50, L"DowntimeLevel");
      v8 = v29;
      if ( v29 < 0 )
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v29);
      v28 = v50;
    }
    else
    {
      v8 = -2147024809;
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942487LL);
    }
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v8);
    if ( (v8 & 0x80000000) != 0 )
      break;
    v30 = STRAPI_Format(&v51, L"/Query %s %s", v28, v7);
    v8 = v30;
    if ( v30 < 0 )
    {
      v41 = (unsigned int)v30;
      goto LABEL_108;
    }
    if ( v28 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v28 - 2);
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    }
LABEL_86:
    if ( (unsigned __int64)++v3 >= 2 )
      goto LABEL_87;
  }
  v41 = v8;
LABEL_108:
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v41);
  if ( v28 )
  {
    v42 = GetProcessHeap();
    HeapFree(v42, 0, v28 - 2);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
LABEL_103:
  v40 = 0;
  if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    v40 = g_shLogFile;
  OutputMsg(v40, g_shLogEvent, L"%s: Error = 0x%X", L"CreateCommandLine", v8);
LABEL_124:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v8);
  if ( v51 )
  {
    v45 = v51 - 2;
    v46 = GetProcessHeap();
    HeapFree(v46, 0, v45);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v7 )
  {
    v47 = GetProcessHeap();
    HeapFree(v47, 0, (LPVOID)(v7 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  return v8;
}

```

## disassembly

```asm
0x140008624  mov     [rsp-28h+arg_8], rbx
0x140008629  mov     [rsp-28h+arg_10], rsi
0x14000862e  push    rbp
0x14000862f  push    rdi
0x140008630  push    r12
0x140008632  push    r13
0x140008634  push    r14
0x140008636  mov     rbp, rsp
0x140008639  sub     rsp, 40h
0x14000863d  xor     r12d, r12d
0x140008640  mov     r13, r8
0x140008643  mov     [rbp+var_10], r12
0x140008647  mov     rbx, rdx
0x14000864a  mov     [rbp+arg_18], r12
0x14000864e  mov     r14, rcx
0x140008651  mov     esi, r12d
0x140008654  test    rcx, rcx
0x140008657  jnz     short loc_140008665
0x140008659  mov     edi, 80070057h
0x14000865e  mov     ecx, edi
0x140008660  jmp     loc_140008C20
0x140008665  test    r13, r13
0x140008668  jz      short loc_140008659
0x14000866a  mov     r8d, 7FFFFFFFh
0x140008670  mov     dword ptr [rbp+arg_0], r12d
0x140008674  lea     rdx, [rbp+arg_0]
0x140008678  lea     rcx, dword_1400860C4
0x14000867f  call    ??$GetStringCchLength@K@?$CGlobalHelpersT@VCEmptyType@@@@SAJPEBGPEAKK@Z; CGlobalHelpersT<CEmptyType>::GetStringCchLength<ulong>(ushort const *,ulong *,ulong)
0x140008684  mov     edi, eax
0x140008686  test    eax, eax
0x140008688  jns     short loc_140008693
0x14000868a  mov     ecx, eax
0x14000868c  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x140008691  jmp     short loc_1400086B7
0x140008693  mov     edx, dword ptr [rbp+arg_0]
0x140008696  lea     r8, [rbp+var_10]
0x14000869a  lea     rcx, dword_1400860C4; Src
0x1400086a1  call    ?CreateInternal@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@KAJPEBGKPEAPEAG@Z; CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::CreateInternal(ushort const *,ulong,ushort * *)
0x1400086a6  mov     edi, eax
0x1400086a8  test    eax, eax
0x1400086aa  jns     short loc_1400086B3
0x1400086ac  mov     ecx, eax
0x1400086ae  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1400086b3  mov     rsi, [rbp+var_10]
0x1400086b7  mov     ecx, edi
0x1400086b9  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1400086be  test    edi, edi
0x1400086c0  js      short loc_14000865E
0x1400086c2  test    rbx, rbx
0x1400086c5  jz      short loc_1400086FC
0x1400086c7  mov     r9, rbx
0x1400086ca  lea     rdx, aSInstallfileS; "%s /InstallFile \"%s\""
0x1400086d1  mov     r8, rsi
0x1400086d4  lea     rcx, [rbp+arg_18]; unsigned __int16 **
0x1400086d8  call    ?STRAPI_Format@@YAJPEAPEAGPEBGZZ; STRAPI_Format(ushort * *,ushort const *,...)
0x1400086dd  mov     edi, eax
0x1400086df  test    eax, eax
0x1400086e1  js      loc_140008C1E
0x1400086e7  mov     rdx, [rbp+arg_18]
0x1400086eb  lea     rcx, [rbp+var_10]
0x1400086ef  mov     [rbp+arg_18], r12
0x1400086f3  call    ?Attach@?$SH@PEAGVSH_SSTRING@@@@QEAAXPEAG@Z; SH<ushort *,SH_SSTRING>::Attach(ushort *)
0x1400086f8  mov     rsi, [rbp+var_10]
0x1400086fc  mov     r9, [r14+10h]
0x140008700  test    r9, r9
0x140008703  jz      short loc_140008737
0x140008705  mov     r8, rsi
0x140008708  lea     rdx, aSProgressclsid; "%s /progressCLSID %s"
0x14000870f  lea     rcx, [rbp+arg_18]; unsigned __int16 **
0x140008713  call    ?STRAPI_Format@@YAJPEAPEAGPEBGZZ; STRAPI_Format(ushort * *,ushort const *,...)
0x140008718  mov     edi, eax
0x14000871a  test    eax, eax
0x14000871c  js      loc_140008C1E
0x140008722  mov     rdx, [rbp+arg_18]
0x140008726  lea     rcx, [rbp+var_10]
0x14000872a  mov     [rbp+arg_18], r12
0x14000872e  call    ?Attach@?$SH@PEAGVSH_SSTRING@@@@QEAAXPEAG@Z; SH<ushort *,SH_SSTRING>::Attach(ushort *)
0x140008733  mov     rsi, [rbp+var_10]
0x140008737  mov     r9, [r14+18h]
0x14000873b  test    r9, r9
0x14000873e  jz      short loc_140008772
0x140008740  mov     r8, rsi
0x140008743  lea     rdx, aSReportidS; "%s /ReportId %s"
0x14000874a  lea     rcx, [rbp+arg_18]; unsigned __int16 **
0x14000874e  call    ?STRAPI_Format@@YAJPEAPEAGPEBGZZ; STRAPI_Format(ushort * *,ushort const *,...)
0x140008753  mov     edi, eax
0x140008755  test    eax, eax
0x140008757  js      loc_140008C1E
0x14000875d  mov     rdx, [rbp+arg_18]
0x140008761  lea     rcx, [rbp+var_10]
0x140008765  mov     [rbp+arg_18], r12
0x140008769  call    ?Attach@?$SH@PEAGVSH_SSTRING@@@@QEAAXPEAG@Z; SH<ushort *,SH_SSTRING>::Attach(ushort *)
0x14000876e  mov     rsi, [rbp+var_10]
0x140008772  mov     r9, [r14+28h]
0x140008776  test    r9, r9
0x140008779  jz      short loc_1400087AD
0x14000877b  mov     r8, rsi
0x14000877e  lea     rdx, aSFlightdataS; "%s /FlightData \"%s\""
0x140008785  lea     rcx, [rbp+arg_18]; unsigned __int16 **
0x140008789  call    ?STRAPI_Format@@YAJPEAPEAGPEBGZZ; STRAPI_Format(ushort * *,ushort const *,...)
0x14000878e  mov     edi, eax
0x140008790  test    eax, eax
0x140008792  js      loc_140008C1E
0x140008798  mov     rdx, [rbp+arg_18]
0x14000879c  lea     rcx, [rbp+var_10]
0x1400087a0  mov     [rbp+arg_18], r12
0x1400087a4  call    ?Attach@?$SH@PEAGVSH_SSTRING@@@@QEAAXPEAG@Z; SH<ushort *,SH_SSTRING>::Attach(ushort *)
0x1400087a9  mov     rsi, [rbp+var_10]
0x1400087ad  cmp     [r14+48h], r12d
0x1400087b1  jz      short loc_1400087E5
0x1400087b3  mov     r8, rsi
0x1400087b6  lea     rdx, aOverrideS; "/Override %s"
0x1400087bd  lea     rcx, [rbp+arg_18]; unsigned __int16 **
0x1400087c1  call    ?STRAPI_Format@@YAJPEAPEAGPEBGZZ; STRAPI_Format(ushort * *,ushort const *,...)
0x1400087c6  mov     edi, eax
0x1400087c8  test    eax, eax
0x1400087ca  js      loc_140008C1E
0x1400087d0  mov     rdx, [rbp+arg_18]
0x1400087d4  lea     rcx, [rbp+var_10]
0x1400087d8  mov     [rbp+arg_18], r12
0x1400087dc  call    ?Attach@?$SH@PEAGVSH_SSTRING@@@@QEAAXPEAG@Z; SH<ushort *,SH_SSTRING>::Attach(ushort *)
0x1400087e1  mov     rsi, [rbp+var_10]
0x1400087e5  cmp     [r14+4Ch], r12d
0x1400087e9  jz      short loc_14000881D
0x1400087eb  mov     r8, rsi
0x1400087ee  lea     rdx, aSelfhostS; "/Selfhost %s"
0x1400087f5  lea     rcx, [rbp+arg_18]; unsigned __int16 **
0x1400087f9  call    ?STRAPI_Format@@YAJPEAPEAGPEBGZZ; STRAPI_Format(ushort * *,ushort const *,...)
0x1400087fe  mov     edi, eax
0x140008800  test    eax, eax
0x140008802  js      loc_140008C1E
0x140008808  mov     rdx, [rbp+arg_18]
0x14000880c  lea     rcx, [rbp+var_10]
0x140008810  mov     [rbp+arg_18], r12
0x140008814  call    ?Attach@?$SH@PEAGVSH_SSTRING@@@@QEAAXPEAG@Z; SH<ushort *,SH_SSTRING>::Attach(ushort *)
0x140008819  mov     rsi, [rbp+var_10]
0x14000881d  cmp     [r14+44h], r12d
0x140008821  jz      short loc_140008855
0x140008823  mov     r8, rsi
0x140008826  lea     rdx, aConsoleS; "/Console %s"
0x14000882d  lea     rcx, [rbp+arg_18]; unsigned __int16 **
0x140008831  call    ?STRAPI_Format@@YAJPEAPEAGPEBGZZ; STRAPI_Format(ushort * *,ushort const *,...)
0x140008836  mov     edi, eax
0x140008838  test    eax, eax
0x14000883a  js      loc_140008C1E
0x140008840  mov     rdx, [rbp+arg_18]
0x140008844  lea     rcx, [rbp+var_10]
0x140008848  mov     [rbp+arg_18], r12
0x14000884c  call    ?Attach@?$SH@PEAGVSH_SSTRING@@@@QEAAXPEAG@Z; SH<ushort *,SH_SSTRING>::Attach(ushort *)
0x140008851  mov     rsi, [rbp+var_10]
0x140008855  cmp     [r14+50h], r12d
0x140008859  jz      short loc_14000888D
0x14000885b  mov     r8, rsi
0x14000885e  lea     rdx, aQuietS; "/Quiet %s"
0x140008865  lea     rcx, [rbp+arg_18]; unsigned __int16 **
0x140008869  call    ?STRAPI_Format@@YAJPEAPEAGPEBGZZ; STRAPI_Format(ushort * *,ushort const *,...)
0x14000886e  mov     edi, eax
0x140008870  test    eax, eax
0x140008872  js      loc_140008C1E
0x140008878  mov     rdx, [rbp+arg_18]
0x14000887c  lea     rcx, [rbp+var_10]
0x140008880  mov     [rbp+arg_18], r12
0x140008884  call    ?Attach@?$SH@PEAGVSH_SSTRING@@@@QEAAXPEAG@Z; SH<ushort *,SH_SSTRING>::Attach(ushort *)
0x140008889  mov     rsi, [rbp+var_10]
0x14000888d  cmp     [r14+54h], r12d
0x140008891  jz      short loc_1400088C5
0x140008893  mov     r8, rsi
0x140008896  lea     rdx, aExpresspackage_0; "/ExpressPackage %s"
0x14000889d  lea     rcx, [rbp+arg_18]; unsigned __int16 **
0x1400088a1  call    ?STRAPI_Format@@YAJPEAPEAGPEBGZZ; STRAPI_Format(ushort * *,ushort const *,...)
0x1400088a6  mov     edi, eax
0x1400088a8  test    eax, eax
0x1400088aa  js      loc_140008C1E
0x1400088b0  mov     rdx, [rbp+arg_18]
0x1400088b4  lea     rcx, [rbp+var_10]
0x1400088b8  mov     [rbp+arg_18], r12
0x1400088bc  call    ?Attach@?$SH@PEAGVSH_SSTRING@@@@QEAAXPEAG@Z; SH<ushort *,SH_SSTRING>::Attach(ushort *)
0x1400088c1  mov     rsi, [rbp+var_10]
0x1400088c5  cmp     [r14+5Ch], r12d
0x1400088c9  jz      short loc_1400088FD
0x1400088cb  mov     r8, rsi
0x1400088ce  lea     rdx, aPromptDeferS; "/Prompt Defer %s"
0x1400088d5  lea     rcx, [rbp+arg_18]; unsigned __int16 **
0x1400088d9  call    ?STRAPI_Format@@YAJPEAPEAGPEBGZZ; STRAPI_Format(ushort * *,ushort const *,...)
0x1400088de  mov     edi, eax
0x1400088e0  test    eax, eax
0x1400088e2  js      loc_140008C1E
0x1400088e8  mov     rdx, [rbp+arg_18]
0x1400088ec  lea     rcx, [rbp+var_10]
0x1400088f0  mov     [rbp+arg_18], r12
0x1400088f4  call    ?Attach@?$SH@PEAGVSH_SSTRING@@@@QEAAXPEAG@Z; SH<ushort *,SH_SSTRING>::Attach(ushort *)
0x1400088f9  mov     rsi, [rbp+var_10]
0x1400088fd  cmp     [r14+60h], r12d
0x140008901  jz      short loc_140008935
0x140008903  mov     r8, rsi
0x140008906  lea     rdx, aEulaAcceptS; "/Eula Accept %s"
0x14000890d  lea     rcx, [rbp+arg_18]; unsigned __int16 **
0x140008911  call    ?STRAPI_Format@@YAJPEAPEAGPEBGZZ; STRAPI_Format(ushort * *,ushort const *,...)
0x140008916  mov     edi, eax
0x140008918  test    eax, eax
0x14000891a  js      loc_140008C1E
0x140008920  mov     rdx, [rbp+arg_18]
0x140008924  lea     rcx, [rbp+var_10]
0x140008928  mov     [rbp+arg_18], r12
0x14000892c  call    ?Attach@?$SH@PEAGVSH_SSTRING@@@@QEAAXPEAG@Z; SH<ushort *,SH_SSTRING>::Attach(ushort *)
0x140008931  mov     rsi, [rbp+var_10]
0x140008935  cmp     [r14+64h], r12d
0x140008939  jz      short loc_14000896D
0x14000893b  mov     r8, rsi
0x14000893e  lea     rdx, aEulaDeferS; "/Eula Defer %s"
0x140008945  lea     rcx, [rbp+arg_18]; unsigned __int16 **
0x140008949  call    ?STRAPI_Format@@YAJPEAPEAGPEBGZZ; STRAPI_Format(ushort * *,ushort const *,...)
0x14000894e  mov     edi, eax
0x140008950  test    eax, eax
0x140008952  js      loc_140008C1E
0x140008958  mov     rdx, [rbp+arg_18]
0x14000895c  lea     rcx, [rbp+var_10]
0x140008960  mov     [rbp+arg_18], r12
0x140008964  call    ?Attach@?$SH@PEAGVSH_SSTRING@@@@QEAAXPEAG@Z; SH<ushort *,SH_SSTRING>::Attach(ushort *)
0x140008969  mov     rsi, [rbp+var_10]
0x14000896d  cmp     [r14+68h], r12d
0x140008971  jz      short loc_1400089A5
0x140008973  mov     r8, rsi
0x140008976  lea     rdx, aPriorityNormal; "/Priority Normal %s"
0x14000897d  lea     rcx, [rbp+arg_18]; unsigned __int16 **
0x140008981  call    ?STRAPI_Format@@YAJPEAPEAGPEBGZZ; STRAPI_Format(ushort * *,ushort const *,...)
0x140008986  mov     edi, eax
0x140008988  test    eax, eax
0x14000898a  js      loc_140008C1E
0x140008990  mov     rdx, [rbp+arg_18]
0x140008994  lea     rcx, [rbp+var_10]
0x140008998  mov     [rbp+arg_18], r12
0x14000899c  call    ?Attach@?$SH@PEAGVSH_SSTRING@@@@QEAAXPEAG@Z; SH<ushort *,SH_SSTRING>::Attach(ushort *)
0x1400089a1  mov     rsi, [rbp+var_10]
0x1400089a5  mov     ecx, [r14+74h]
0x1400089a9  sub     ecx, 1
0x1400089ac  jz      loc_140008ADD
0x1400089b2  sub     ecx, 1
0x1400089b5  jz      loc_140008AD1
0x1400089bb  sub     ecx, 2
0x1400089be  jz      loc_140008AC5
0x1400089c4  sub     ecx, 1
0x1400089c7  jz      loc_140008AB9
0x1400089cd  sub     ecx, 1
0x1400089d0  jz      loc_140008AAD
0x1400089d6  sub     ecx, 1
0x1400089d9  jz      loc_140008AA1
0x1400089df  sub     ecx, 1
0x1400089e2  jz      loc_140008A95
0x1400089e8  cmp     ecx, 1
0x1400089eb  jnz     short loc_140008A0A
0x1400089ed  lea     rdx, aServicingS; "/Servicing %s"
0x1400089f4  mov     r8, rsi
0x1400089f7  lea     rcx, [rbp+arg_18]; unsigned __int16 **
0x1400089fb  call    ?STRAPI_Format@@YAJPEAPEAGPEBGZZ; STRAPI_Format(ushort * *,ushort const *,...)
0x140008a00  mov     edi, eax
0x140008a02  test    eax, eax
0x140008a04  js      loc_140008C1E
0x140008a0a  mov     rdx, [rbp+arg_18]
0x140008a0e  lea     rcx, [rbp+var_10]
0x140008a12  mov     [rbp+arg_18], r12
0x140008a16  mov     rdi, r12
0x140008a19  call    ?Attach@?$SH@PEAGVSH_SSTRING@@@@QEAAXPEAG@Z; SH<ushort *,SH_SSTRING>::Attach(ushort *)
0x140008a1e  mov     ecx, [r14+78h]
0x140008a22  sub     ecx, 1
0x140008a25  jz      loc_140008CF3
0x140008a2b  sub     ecx, 1
0x140008a2e  jz      loc_140008CEA
0x140008a34  sub     ecx, 1
0x140008a37  jz      loc_140008CE1
0x140008a3d  sub     ecx, 1
0x140008a40  jz      loc_140008CD8
0x140008a46  sub     ecx, 1
0x140008a49  jz      loc_140008CCF
0x140008a4f  sub     ecx, 3
0x140008a52  jz      loc_140008CC6
0x140008a58  sub     ecx, 2
0x140008a5b  jz      loc_140008CA0
0x140008a61  cmp     ecx, 1
0x140008a64  jnz     loc_140008B7A
0x140008a6a  mov     rsi, [rbp+var_10]
0x140008a6e  mov     eax, [r14+7Ch]
0x140008a72  test    r12, rax
0x140008a75  jz      loc_140008B66
0x140008a7b  xor     ebx, ebx
0x140008a7d  mov     [rbp+arg_0], rbx
0x140008a81  cmp     r12d, 1
0x140008a85  jz      short loc_140008AE9
0x140008a87  mov     edi, 80070057h
0x140008a8c  mov     ecx, edi
0x140008a8e  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x140008a93  jmp     short loc_140008B0A
0x140008a95  lea     rdx, aAzurehostS; "/AzureHost %s"
0x140008a9c  jmp     loc_1400089F4
0x140008aa1  lea     rdx, aWebS; "/Web %s"
0x140008aa8  jmp     loc_1400089F4
0x140008aad  lea     rdx, aPackageS; "/Package %s"
0x140008ab4  jmp     loc_1400089F4
0x140008ab9  lea     rdx, aUpdateS; "/Update %s"
0x140008ac0  jmp     loc_1400089F4
  ... truncated ...
```
