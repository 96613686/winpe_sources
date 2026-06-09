# WindowsPerformanceRecorder::CETWProperties::WriteEventProviderId(WindowsPerformanceRecorder::CXmlWriter &,WindowsPerformanceRecorder::CEventProvidersCache const *,WindowsPerformanceRecorder::CETWProperties::CEventSession const *,bool,bool,bool)

- ea: `0x18001b920`
- end: `0x18001bf91`
- name: `?WriteEventProviderId@CETWProperties@WindowsPerformanceRecorder@@CAJAEAVCXmlWriter@2@PEBVCEventProvidersCache@2@PEBUCEventSession@12@_N33@Z`
- size: `1649`
- prototype: `static int(struct WindowsPerformanceRecorder::CXmlWriter *, const struct WindowsPerformanceRecorder::CEventProvidersCache *, const struct WindowsPerformanceRecorder::CETWProperties::CEventSession *, bool, bool, bool)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config`

## callers

- `0x180042638`

## callees

- `0x18000eeb0`
- `0x1800102d8`
- `0x180011280`
- `0x1800128f8`
- `0x180012ba0`
- `0x1800131a0`
- `0x18001b920`
- `0x18001c458`
- `0x18001e6b8`
- `0x18002c9e0`
- `0x180043294`
- `0x180044210`
- `0x180046e98`
- `0x18004b50c`
- `0x18004f8ce`
- `0x18004f964`
- `0x18004f970`
- `0x180082d3c`
- `0x18008c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001beaa`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001bed0`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001beaa`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001bed0`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall WindowsPerformanceRecorder::CETWProperties::WriteEventProviderId(
        struct WindowsPerformanceRecorder::CXmlWriter *a1,
        const struct WindowsPerformanceRecorder::CEventProvidersCache *a2,
        const struct WindowsPerformanceRecorder::CETWProperties::CEventSession *a3,
        char a4,
        bool a5,
        bool a6)
{
  const struct WindowsPerformanceRecorder::CETWProperties::CEventSession *v6; // r13
  char v7; // r10
  char *v8; // rdx
  __int64 v9; // rax
  bool v10; // cl
  char *v11; // r15
  char *v12; // rax
  __int64 v13; // r11
  char *v14; // r12
  char *v15; // r8
  char *v16; // rcx
  __int64 v17; // rax
  __int64 v18; // rax
  const unsigned __int16 *SessionName; // rax
  __int64 v20; // rdx
  __int64 v21; // rdi
  __int64 v22; // rbx
  unsigned __int64 v23; // r14
  int v24; // esi
  unsigned __int64 v25; // rbx
  const wchar_t *v26; // rax
  wchar_t *v27; // rcx
  char *v28; // rbx
  void *v29; // r12
  __int64 v30; // rsi
  unsigned __int64 v31; // r13
  int v32; // r14d
  unsigned __int64 v33; // rsi
  size_t v34; // r8
  void *v35; // rcx
  char v36; // dl
  __int64 v37; // rcx
  int v38; // r14d
  __int64 v39; // rax
  __int64 v40; // rsi
  char v41; // dl
  __int64 v42; // rcx
  int v43; // r14d
  __int64 v44; // rax
  __int64 v45; // rsi
  __int64 v46; // rcx
  __int64 v48; // rax
  __int64 v49; // [rsp+20h] [rbp-D8h]
  __int64 v50; // [rsp+28h] [rbp-D0h]
  __int64 v51; // [rsp+30h] [rbp-C8h]
  __int64 v52; // [rsp+38h] [rbp-C0h]
  __int64 v53; // [rsp+40h] [rbp-B8h]
  __int64 v54; // [rsp+48h] [rbp-B0h]
  __int64 v55; // [rsp+50h] [rbp-A8h]
  __int64 v56; // [rsp+58h] [rbp-A0h]
  __int64 v57; // [rsp+60h] [rbp-98h]
  int v58; // [rsp+70h] [rbp-88h]
  __int64 v59; // [rsp+78h] [rbp-80h] BYREF
  void *Src; // [rsp+80h] [rbp-78h] BYREF
  char *v61; // [rsp+88h] [rbp-70h]
  __int64 v62; // [rsp+90h] [rbp-68h]
  ATL::CAtlException *v63; // [rsp+98h] [rbp-60h] BYREF
  _QWORD pExceptionObject[11]; // [rsp+A0h] [rbp-58h] BYREF
  char v66; // [rsp+108h] [rbp+10h]
  char v68; // [rsp+118h] [rbp+20h]

  v68 = a4;
  v62 = -2;
  v6 = a3;
  v7 = 1;
  v66 = 1;
  v8 = (char *)a6;
  if ( a6 )
  {
    v9 = 48;
    v10 = a5;
  }
  else
  {
    v10 = a5;
    v9 = (!a5 << 7) + 24LL;
  }
  v11 = *(char **)((char *)a3 + v9);
  v12 = *(char **)((char *)a3 + v9 + 8);
  v61 = v12;
  v13 = 0x1000000000000LL;
  while ( v11 != v12 )
  {
    v14 = v11;
    v15 = v11;
    if ( !(_BYTE)v8 && !v10 )
    {
      v16 = (char *)*((_QWORD *)v6 + 3);
      v8 = (char *)*((_QWORD *)v6 + 4);
      if ( v16 != v8 )
      {
        while ( 1 )
        {
          v17 = *(_QWORD *)v16 - *(_QWORD *)v11;
          if ( *(_QWORD *)v16 == *(_QWORD *)v11 )
            v17 = *((_QWORD *)v16 + 1) - *((_QWORD *)v11 + 1);
          if ( !v17 )
            break;
          v16 += 264;
          if ( v16 == v8 )
            goto LABEL_12;
        }
        v15 = v16;
      }
    }
LABEL_12:
    if ( a4 )
    {
      if ( *((_BYTE *)v6 + 208) )
      {
        v48 = *((_QWORD *)v11 + 2);
        if ( v48 != -1 && (v48 & v13) != 0 )
        {
          if ( v7 )
          {
            v14 = ControlGuid_PerfTrack;
          }
          else if ( (v48 & 0xFFFEFFFFFFFFFFFFuLL) == 0 && !*((_QWORD *)v15 + 4) && !*((_QWORD *)v15 + 3) )
          {
            goto LABEL_15;
          }
          v7 = 0;
          v66 = 0;
        }
      }
    }
    if ( (!*((_BYTE *)v6 + 209) || !v15[261])
      && (*(_DWORD *)v6 != 1
       || !WindowsPerformanceRecorder::CETWProperties::CEventProvider::IsSystemMetaProvider((WindowsPerformanceRecorder::CETWProperties::CEventProvider *)v15)) )
    {
      v18 = ((__int64 (__fastcall *)(void ***, char *, char *))ATL::g_strmgr[3])(&ATL::g_strmgr, v8, v15);
      try
      {
        Src = (void *)(v18 + 24);
        LODWORD(v57) = (unsigned __int8)v14[15];
        LODWORD(v56) = (unsigned __int8)v14[14];
        LODWORD(v55) = (unsigned __int8)v14[13];
        LODWORD(v54) = (unsigned __int8)v14[12];
        LODWORD(v53) = (unsigned __int8)v14[11];
        LODWORD(v52) = (unsigned __int8)v14[10];
        LODWORD(v51) = (unsigned __int8)v14[9];
        LODWORD(v50) = (unsigned __int8)v14[8];
        LODWORD(v49) = *((unsigned __int16 *)v14 + 3);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
          &Src,
          L"%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x",
          *(unsigned int *)v14,
          *((unsigned __int16 *)v14 + 2),
          v49,
          v50,
          v51,
          v52,
          v53,
          v54,
          v55,
          v56,
          v57);
        v59 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
        SessionName = (const unsigned __int16 *)*((_QWORD *)v6 + 24);
        if ( !SessionName )
          SessionName = WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName(v6);
        ATL::CSimpleStringT<unsigned short,0>::SetString(&v59, SessionName);
        v21 = v59;
        v22 = (__int64)L"_" - v59;
        v23 = *(unsigned int *)(v59 - 16);
        v24 = v23 + 1;
        if ( (((*(_DWORD *)(v59 - 12) - (v23 + 1)) | (1 - *(_DWORD *)(v59 - 8))) & 0x80000000) != 0LL )
        {
          ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(&v59, v24);
          v21 = v59;
        }
        v25 = v22 >> 1;
        if ( v25 <= v23 )
          v26 = (const wchar_t *)(v21 + 2 * v25);
        else
          v26 = L"_";
        v27 = (wchar_t *)(v21 + 2 * v23);
        if ( v27 )
        {
          if ( v26 )
          {
            *v27 = *v26;
LABEL_28:
            if ( v24 < 0 || v24 > *(_DWORD *)(v21 - 12) )
              ATL::AtlThrowImpl(-2147024809);
            *(_DWORD *)(v21 - 16) = v24;
            *(_WORD *)(v21 + 2LL * v24) = 0;
            v28 = (char *)Src;
            v58 = *((_DWORD *)Src - 4);
            v29 = Src;
            v30 = (__int64)Src - v21;
            v31 = *(unsigned int *)(v21 - 16);
            v32 = v58 + v31;
            if ( (((*(_DWORD *)(v21 - 12) - (v58 + v31)) | (1 - *(_DWORD *)(v21 - 8))) & 0x80000000) != 0LL )
            {
              ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(&v59, v32);
              v21 = v59;
            }
            v33 = v30 >> 1;
            if ( v33 <= v31 )
              v29 = (void *)(v21 + 2 * v33);
            v34 = 2LL * v58;
            if ( v34 )
            {
              v35 = (void *)(v21 + 2 * v31);
              if ( v35 )
              {
                if ( v29 )
                {
                  memcpy_0(v35, v29, v34);
                  goto LABEL_38;
                }
                memset_0(v35, 0, v34);
              }
              *(_DWORD *)_o__errno(v35, v20) = 22;
              invalid_parameter_noinfo();
            }
LABEL_38:
            if ( v32 < 0 || v32 > *(_DWORD *)(v21 - 12) )
              ATL::AtlThrowImpl(-2147024809);
            *(_DWORD *)(v21 - 16) = v32;
            *(_WORD *)(v21 + 2LL * v32) = 0;
            if ( a6 )
            {
              ATL::CSimpleStringT<unsigned short,0>::Append(&v59, L"_CaptureState");
              v21 = v59;
            }
            v36 = 0;
            v37 = v21;
            v38 = *(_DWORD *)(v21 - 16);
            LODWORD(v39) = 0;
            while ( (int)v39 < v38 )
            {
              v40 = 2LL * (int)v39;
              if ( *(_WORD *)(v40 + v37) == 58 )
              {
                if ( !v36 )
                {
                  if ( ((*(_DWORD *)(v21 - 12) - v38) | (1 - *(_DWORD *)(v21 - 8))) < 0 )
                  {
                    ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(&v59, v38);
                    v21 = v59;
                  }
                  v36 = 1;
                  v37 = v21;
                }
                *(_WORD *)(v40 + v37) = 95;
              }
              v39 = (v40 + 2) >> 1;
            }
            if ( v36 )
              ATL::CSimpleStringT<unsigned short,0>::SetLength(&v59, v38);
            v41 = 0;
            v42 = v21;
            v43 = *(_DWORD *)(v21 - 16);
            LODWORD(v44) = 0;
            while ( (int)v44 < v43 )
            {
              v45 = 2LL * (int)v44;
              if ( *(_WORD *)(v45 + v42) == 32 )
              {
                if ( !v41 )
                {
                  if ( ((*(_DWORD *)(v21 - 12) - v43) | (1 - *(_DWORD *)(v21 - 8))) < 0 )
                  {
                    ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(&v59, v43);
                    v21 = v59;
                  }
                  v41 = 1;
                  v42 = v21;
                }
                *(_WORD *)(v45 + v42) = 95;
              }
              v44 = (v45 + 2) >> 1;
            }
            if ( v41 )
              ATL::CSimpleStringT<unsigned short,0>::SetLength(&v59, v43);
            if ( *((_BYTE *)a1 + 16) )
              ATL::CSimpleStringT<unsigned short,0>::Append(a1, L">\n");
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
              a1,
              L"%*ws<%ws",
              *((unsigned int *)a1 + 5),
              &LocaleName,
              L"EventProviderId");
            *((_DWORD *)a1 + 5) += 2;
            *((_BYTE *)a1 + 16) = 1;
            WindowsPerformanceRecorder::CXmlWriter::_CheckAttr(a1);
            WindowsPerformanceRecorder::CXmlWriter::EscapeXml(v46, (char *)a1 + 8, v21);
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
              a1,
              L" %ws=\"%ws\"",
              L"Value",
              *((_QWORD *)a1 + 1));
            *((_DWORD *)a1 + 5) -= 2;
            if ( !*((_BYTE *)a1 + 16) )
            {
              std::exception::exception((std::exception *)pExceptionObject, "wszName");
              pExceptionObject[0] = &std::invalid_argument::`vftable';
              throw (std::invalid_argument *)pExceptionObject;
            }
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
              a1,
              L" />\n");
            *((_BYTE *)a1 + 16) = 0;
            ATL::CStringData::Release((ATL::CStringData *)(v21 - 24));
            ATL::CStringData::Release((ATL::CStringData *)(v28 - 24));
            v6 = a3;
            a4 = v68;
            v7 = v66;
            v13 = 0x1000000000000LL;
            goto LABEL_15;
          }
          *v27 = 0;
        }
        *(_DWORD *)_o__errno(v27, v20) = 22;
        invalid_parameter_noinfo();
        goto LABEL_28;
      }
      catch ( ATL::CAtlException *v63 )
      {
        return *(unsigned int *)v63;
      }
    }
LABEL_15:
    v11 += 264;
    v10 = a5;
    v8 = (char *)a6;
    v12 = v61;
  }
  return 0;
}

```

## disassembly

```asm
0x18001b920  mov     rax, rsp
0x18001b923  mov     [rax+20h], r9b
0x18001b927  mov     [rax+18h], r8
0x18001b92b  mov     [rax+10h], rdx
0x18001b92f  mov     [rax+8], rcx
0x18001b933  push    rbx
0x18001b934  push    rsi
0x18001b935  push    rdi
0x18001b936  push    r12
0x18001b938  push    r13
0x18001b93a  push    r14
0x18001b93c  push    r15
0x18001b93e  sub     rsp, 0C0h
0x18001b945  mov     qword ptr [rax-68h], 0FFFFFFFFFFFFFFFEh
0x18001b94d  mov     r13, r8
0x18001b950  mov     r10b, 1
0x18001b953  mov     [rsp+0F8h+arg_8], r10b
0x18001b95b  movzx   edx, [rsp+0F8h+arg_28]
0x18001b963  test    dl, dl
0x18001b965  jz      loc_18001BE07
0x18001b96b  mov     eax, 30h ; '0'
0x18001b970  movzx   ecx, [rsp+0F8h+arg_20]
0x18001b978  mov     r15, [rax+r8]
0x18001b97c  mov     rax, [rax+r8+8]
0x18001b981  mov     [rsp+0F8h+var_70], rax
0x18001b989  mov     rbx, 0FFFEFFFFFFFFFFFFh
0x18001b993  mov     r11, 1000000000000h
0x18001b99d  nop     dword ptr [rax]
0x18001b9a0  cmp     r15, rax
0x18001b9a3  jz      loc_18001BDF2
0x18001b9a9  mov     r12, r15
0x18001b9ac  mov     r8, r15
0x18001b9af  test    dl, dl
0x18001b9b1  jnz     short loc_18001B9E5
0x18001b9b3  test    cl, cl
0x18001b9b5  jnz     short loc_18001B9E5
0x18001b9b7  mov     rcx, [r13+18h]
0x18001b9bb  mov     rdx, [r13+20h]
0x18001b9bf  cmp     rcx, rdx
0x18001b9c2  jz      short loc_18001B9E5
0x18001b9c4  mov     rax, [rcx]
0x18001b9c7  sub     rax, [r15]
0x18001b9ca  jnz     short loc_18001B9D4
0x18001b9cc  mov     rax, [rcx+8]
0x18001b9d0  sub     rax, [r15+8]
0x18001b9d4  test    rax, rax
0x18001b9d7  jz      short loc_18001BA26
0x18001b9d9  add     rcx, 108h
0x18001b9e0  cmp     rcx, rdx
0x18001b9e3  jnz     short loc_18001B9C4
0x18001b9e5  test    r9b, r9b
0x18001b9e8  jnz     loc_18001BE22
0x18001b9ee  cmp     byte ptr [r13+0D1h], 0
0x18001b9f6  jz      short loc_18001BA2B
0x18001b9f8  cmp     byte ptr [r8+105h], 0
0x18001ba00  jz      short loc_18001BA2B
0x18001ba02  add     r15, 108h
0x18001ba09  movzx   ecx, [rsp+0F8h+arg_20]
0x18001ba11  movzx   edx, [rsp+0F8h+arg_28]
0x18001ba19  mov     rax, [rsp+0F8h+var_70]
0x18001ba21  jmp     loc_18001B9A0
0x18001ba26  mov     r8, rcx
0x18001ba29  jmp     short loc_18001B9E5
0x18001ba2b  cmp     dword ptr [r13+0], 1
0x18001ba30  jz      loc_18001BE7C
0x18001ba36  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001ba3d  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001ba44  mov     rax, [rax+18h]
0x18001ba48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ba4d  add     rax, 18h
0x18001ba51  mov     [rsp+0F8h+Src], rax
0x18001ba59  movzx   eax, byte ptr [r12+0Fh]
0x18001ba5f  movzx   ecx, byte ptr [r12+0Eh]
0x18001ba65  movzx   edx, byte ptr [r12+0Dh]
0x18001ba6b  movzx   r10d, byte ptr [r12+0Ch]
0x18001ba71  movzx   r11d, byte ptr [r12+0Bh]
0x18001ba77  movzx   ebx, byte ptr [r12+0Ah]
0x18001ba7d  movzx   edi, byte ptr [r12+9]
0x18001ba83  movzx   esi, byte ptr [r12+8]
0x18001ba89  movzx   r14d, word ptr [r12+6]
0x18001ba8f  movzx   r9d, word ptr [r12+4]
0x18001ba95  mov     [rsp+0F8h+var_98], eax
0x18001ba99  mov     dword ptr [rsp+0F8h+var_A0], ecx
0x18001ba9d  mov     dword ptr [rsp+0F8h+var_A8], edx
0x18001baa1  mov     dword ptr [rsp+0F8h+var_B0], r10d
0x18001baa6  mov     dword ptr [rsp+0F8h+var_B8], r11d
0x18001baab  mov     dword ptr [rsp+0F8h+var_C0], ebx
0x18001baaf  mov     dword ptr [rsp+0F8h+var_C8], edi
0x18001bab3  mov     dword ptr [rsp+0F8h+var_D0], esi
0x18001bab7  mov     dword ptr [rsp+0F8h+var_D8], r14d
0x18001babc  mov     r8d, [r12]
0x18001bac0  lea     rdx, a08x04x04x02x02_0; "%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02"...
0x18001bac7  lea     rcx, [rsp+0F8h+Src]
0x18001bacf  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x18001bad4  nop
0x18001bad5  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001badc  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001bae3  mov     rax, [rax+18h]
0x18001bae7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001baec  add     rax, 18h
0x18001baf0  mov     [rsp+0F8h+var_80], rax
0x18001baf5  mov     rax, [r13+0C0h]
0x18001bafc  test    rax, rax
0x18001baff  jz      loc_18001BE91
0x18001bb05  mov     rdx, rax
0x18001bb08  lea     rcx, [rsp+0F8h+var_80]
0x18001bb0d  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x18001bb12  lea     rbx, asc_180094964; "_"
0x18001bb19  mov     rdi, [rsp+0F8h+var_80]
0x18001bb1e  sub     rbx, rdi
0x18001bb21  mov     r14d, [rdi-10h]
0x18001bb25  lea     esi, [r14+1]
0x18001bb29  mov     ecx, 1
0x18001bb2e  sub     ecx, [rdi-8]
0x18001bb31  mov     eax, [rdi-0Ch]
0x18001bb34  sub     eax, esi
0x18001bb36  or      ecx, eax
0x18001bb38  jge     short loc_18001BB4B
0x18001bb3a  mov     edx, esi
0x18001bb3c  lea     rcx, [rsp+0F8h+var_80]
0x18001bb41  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x18001bb46  mov     rdi, [rsp+0F8h+var_80]
0x18001bb4b  sar     rbx, 1
0x18001bb4e  cmp     rbx, r14
0x18001bb51  jbe     loc_18001BE9E
0x18001bb57  lea     rax, asc_180094964; "_"
0x18001bb5e  lea     rcx, [rdi+r14*2]
0x18001bb62  test    rcx, rcx
0x18001bb65  jz      loc_18001BEAA
0x18001bb6b  test    rax, rax
0x18001bb6e  jz      loc_18001BEA7
0x18001bb74  movzx   eax, word ptr [rax]
0x18001bb77  mov     [rcx], ax
0x18001bb7a  test    esi, esi
0x18001bb7c  js      loc_18001BF7A
0x18001bb82  cmp     esi, [rdi-0Ch]
0x18001bb85  jg      loc_18001BF7A
0x18001bb8b  mov     [rdi-10h], esi
0x18001bb8e  movsxd  rcx, esi
0x18001bb91  xor     eax, eax
0x18001bb93  mov     [rdi+rcx*2], ax
0x18001bb97  mov     rbx, [rsp+0F8h+Src]
0x18001bb9f  mov     eax, [rbx-10h]
0x18001bba2  mov     [rsp+0F8h+var_88], eax
0x18001bba6  mov     r12, rbx
0x18001bba9  mov     rsi, rbx
0x18001bbac  sub     rsi, rdi
0x18001bbaf  mov     r13d, [rdi-10h]
0x18001bbb3  lea     r14d, [rax+r13]
0x18001bbb7  mov     ecx, 1
0x18001bbbc  sub     ecx, [rdi-8]
0x18001bbbf  mov     eax, [rdi-0Ch]
0x18001bbc2  sub     eax, r14d
0x18001bbc5  or      ecx, eax
0x18001bbc7  jge     short loc_18001BBDB
0x18001bbc9  mov     edx, r14d
0x18001bbcc  lea     rcx, [rsp+0F8h+var_80]
0x18001bbd1  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x18001bbd6  mov     rdi, [rsp+0F8h+var_80]
0x18001bbdb  sar     rsi, 1
0x18001bbde  cmp     rsi, r13
0x18001bbe1  jbe     loc_18001BEC0
0x18001bbe7  movsxd  r8, [rsp+0F8h+var_88]
0x18001bbec  add     r8, r8; Size
0x18001bbef  jz      short loc_18001BC0F
0x18001bbf1  lea     rcx, [rdi+r13*2]; void *
0x18001bbf5  test    rcx, rcx
0x18001bbf8  jz      loc_18001BED0
0x18001bbfe  test    r12, r12
0x18001bc01  jz      loc_18001BEC9
0x18001bc07  mov     rdx, r12; Src
0x18001bc0a  call    memcpy_0
0x18001bc0f  test    r14d, r14d
0x18001bc12  js      loc_18001BF70
0x18001bc18  cmp     r14d, [rdi-0Ch]
0x18001bc1c  jg      loc_18001BF70
0x18001bc22  mov     [rdi-10h], r14d
0x18001bc26  movsxd  rcx, r14d
0x18001bc29  xor     eax, eax
0x18001bc2b  mov     [rdi+rcx*2], ax
0x18001bc2f  cmp     [rsp+0F8h+arg_28], al
0x18001bc36  jnz     loc_18001BEE6
0x18001bc3c  xor     dl, dl
0x18001bc3e  mov     rcx, rdi
0x18001bc41  mov     r14d, [rdi-10h]
0x18001bc45  xor     eax, eax
0x18001bc47  cmp     eax, r14d
0x18001bc4a  jge     short loc_18001BC66
0x18001bc4c  cdqe
0x18001bc4e  lea     rsi, [rax+rax]
0x18001bc52  cmp     word ptr [rsi+rcx], 3Ah ; ':'
0x18001bc57  jz      loc_18001BD82
0x18001bc5d  lea     rax, [rsi+2]
0x18001bc61  sar     rax, 1
0x18001bc64  jmp     short loc_18001BC47
0x18001bc66  test    dl, dl
0x18001bc68  jnz     loc_18001BF01
0x18001bc6e  xor     dl, dl
0x18001bc70  mov     rcx, rdi
0x18001bc73  mov     r14d, [rdi-10h]
0x18001bc77  xor     eax, eax
0x18001bc79  nop     dword ptr [rax+00000000h]
0x18001bc80  cmp     eax, r14d
0x18001bc83  jge     short loc_18001BC9F
0x18001bc85  cdqe
0x18001bc87  lea     rsi, [rax+rax]
0x18001bc8b  cmp     word ptr [rsi+rcx], 20h ; ' '
0x18001bc90  jz      loc_18001BDBA
0x18001bc96  lea     rax, [rsi+2]
0x18001bc9a  sar     rax, 1
0x18001bc9d  jmp     short loc_18001BC80
0x18001bc9f  test    dl, dl
0x18001bca1  jnz     loc_18001BF13
0x18001bca7  mov     r14, [rsp+0F8h+arg_0]
0x18001bcaf  cmp     byte ptr [r14+10h], 0
0x18001bcb4  jnz     loc_18001BF25
0x18001bcba  lea     rax, aEventprovideri; "EventProviderId"
0x18001bcc1  mov     [rsp+0F8h+var_D8], rax
0x18001bcc6  lea     r9, LocaleName
0x18001bccd  mov     r8d, [r14+14h]
0x18001bcd1  lea     rdx, aWsWs_2; "%*ws<%ws"
0x18001bcd8  mov     rcx, r14
0x18001bcdb  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x18001bce0  add     dword ptr [r14+14h], 2
0x18001bce5  mov     byte ptr [r14+10h], 1
0x18001bcea  mov     rcx, r14; this
0x18001bced  call    ?_CheckAttr@CXmlWriter@WindowsPerformanceRecorder@@AEAAXXZ; WindowsPerformanceRecorder::CXmlWriter::_CheckAttr(void)
0x18001bcf2  mov     r8, rdi
0x18001bcf5  lea     rdx, [r14+8]
0x18001bcf9  call    ?EscapeXml@CXmlWriter@WindowsPerformanceRecorder@@AEAAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBGK@Z; WindowsPerformanceRecorder::CXmlWriter::EscapeXml(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ushort const *,ulong)
0x18001bcfe  mov     r9, [r14+8]
0x18001bd02  lea     r8, aValue; "Value"
0x18001bd09  lea     rdx, aWsWs; " %ws=\"%ws\""
0x18001bd10  mov     rcx, r14
0x18001bd13  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x18001bd18  add     dword ptr [r14+14h], 0FFFFFFFEh
0x18001bd1d  cmp     byte ptr [r14+10h], 0
0x18001bd22  jz      loc_18001BF39
0x18001bd28  lea     rdx, asc_180094A18; " />\n"
0x18001bd2f  mov     rcx, r14
0x18001bd32  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x18001bd37  mov     byte ptr [r14+10h], 0
0x18001bd3c  lea     rcx, [rdi-18h]; this
0x18001bd40  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001bd45  nop
0x18001bd46  lea     rcx, [rbx-18h]; this
0x18001bd4a  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001bd4f  mov     r13, [rsp+0F8h+arg_10]
0x18001bd57  movzx   r9d, [rsp+0F8h+arg_18]
0x18001bd60  movzx   r10d, [rsp+0F8h+arg_8]
0x18001bd69  mov     rbx, 0FFFEFFFFFFFFFFFFh
0x18001bd73  mov     r11, 1000000000000h
0x18001bd7d  jmp     loc_18001BA02
0x18001bd82  test    dl, dl
0x18001bd84  jnz     short loc_18001BDAF
0x18001bd86  mov     ecx, 1
0x18001bd8b  sub     ecx, [rdi-8]
0x18001bd8e  mov     eax, [rdi-0Ch]
0x18001bd91  sub     eax, r14d
0x18001bd94  or      ecx, eax
0x18001bd96  jge     short loc_18001BDAA
0x18001bd98  mov     edx, r14d
0x18001bd9b  lea     rcx, [rsp+0F8h+var_80]
0x18001bda0  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x18001bda5  mov     rdi, [rsp+0F8h+var_80]
0x18001bdaa  mov     dl, 1
0x18001bdac  mov     rcx, rdi
0x18001bdaf  mov     word ptr [rsi+rcx], 5Fh ; '_'
0x18001bdb5  jmp     loc_18001BC5D
0x18001bdba  test    dl, dl
0x18001bdbc  jnz     short loc_18001BDE7
0x18001bdbe  mov     ecx, 1
0x18001bdc3  sub     ecx, [rdi-8]
0x18001bdc6  mov     eax, [rdi-0Ch]
0x18001bdc9  sub     eax, r14d
0x18001bdcc  or      ecx, eax
0x18001bdce  jge     short loc_18001BDE2
0x18001bdd0  mov     edx, r14d
0x18001bdd3  lea     rcx, [rsp+0F8h+var_80]
0x18001bdd8  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x18001bddd  mov     rdi, [rsp+0F8h+var_80]
0x18001bde2  mov     dl, 1
0x18001bde4  mov     rcx, rdi
0x18001bde7  mov     word ptr [rsi+rcx], 5Fh ; '_'
0x18001bded  jmp     loc_18001BC96
0x18001bdf2  xor     eax, eax
0x18001bdf4  add     rsp, 0C0h
0x18001bdfb  pop     r15
0x18001bdfd  pop     r14
0x18001bdff  pop     r13
0x18001be01  pop     r12
0x18001be03  pop     rdi
0x18001be04  pop     rsi
0x18001be05  pop     rbx
0x18001be06  retn
0x18001be07  movzx   ecx, [rsp+0F8h+arg_20]
0x18001be0f  mov     eax, ecx
0x18001be11  xor     rax, 1
0x18001be15  shl     rax, 7
0x18001be19  add     rax, 18h
  ... truncated ...
```
