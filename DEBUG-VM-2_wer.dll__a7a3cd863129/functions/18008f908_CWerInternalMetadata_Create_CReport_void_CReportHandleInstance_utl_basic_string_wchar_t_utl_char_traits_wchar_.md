# CWerInternalMetadata::Create(CReport *,void *,CReportHandleInstance *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)

- ea: `0x18008f908`
- end: `0x18008ff4e`
- name: `?Create@CWerInternalMetadata@@SAJPEAVCReport@@PEAXPEAVCReportHandleInstance@@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z`
- size: `1606`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18001b280`

## callees

- `0x180004bb4`
- `0x18000e7fc`
- `0x18001fe24`
- `0x18003765c`
- `0x180041338`
- `0x18004144c`
- `0x180041588`
- `0x180047c10`
- `0x180048a24`
- `0x18004a12c`
- `0x1800720cc`
- `0x18008f908`
- `0x18008ff54`
- `0x180090194`
- `0x180090324`
- `0x180090540`
- `0x1800905cc`
- `0x180090b44`
- `0x180090d5c`
- `0x180090e7c`
- `0x1800911ac`
- `0x180091488`
- `0x180091cc0`

## string_xrefs

- `0x18008f980`: `CWerInternalMetadata::Create Report == NULL\n`
- `0x18008f9d4`: `xmlWriter.Initialize failed with hr=0x%x\n`
- `0x18008fa62`: `xmlWriter.BeginElement failed with hr=0x%x\n`
- `0x18008fab1`: `WriteOsVersionInformation failed with hr=0x%x\n`
- `0x18008fb10`: `WriteProcessInformation failed with hr=0x%x\n`
- `0x18008fb5f`: `WriteProcessMetadata failed with hr=0x%x\n`
- `0x18008fbae`: `WriteProblemSignatures failed with hr=0x%x\n`
- `0x18008fbfd`: `WriteDynamicSignatures failed with hr=0x%x\n`
- `0x18008fc4c`: `WriteServiceInformation failed with hr=0x%x\n`
- `0x18008fcca`: `WriteSystemInformation failed with hr=0x%x\n`
- `0x18008fd5a`: `WriteSecureBootState failed with hr=0x%x\n`
- `0x18008fdae`: `WriteIntegrator failed with hr=0x%x\n`
- `0x18008fe07`: `WritePhoneInformation failed with hr=0x%x\n`
- `0x18008fe53`: `WriteContainerInformation failed with hr=0x%x\n`
- `0x18008fea2`: `WriteTimelineInformation failed with hr=0x%x\n`
- `0x18008fef1`: `WriteReportInformation failed with hr=0x%x\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CWerInternalMetadata::Create(__int64 a1, void *a2, __int64 a3, __int64 a4)
{
  unsigned int v7; // ebx
  int v8; // eax
  __int64 v10; // [rsp+30h] [rbp-29h] BYREF
  int v11; // [rsp+38h] [rbp-21h]
  const wchar_t *v12; // [rsp+40h] [rbp-19h] BYREF
  __int64 v13; // [rsp+48h] [rbp-11h]
  __int128 v14; // [rsp+50h] [rbp-9h] BYREF
  __int128 v15; // [rsp+60h] [rbp+7h] BYREF
  int v16; // [rsp+70h] [rbp+17h] BYREF
  __int64 v17; // [rsp+78h] [rbp+1Fh] BYREF
  _QWORD v18[6]; // [rsp+80h] [rbp+27h] BYREF

  v10 = -1;
  v11 = 0;
  v16 = 0;
  v17 = 0;
  v18[0] = 0;
  if ( !a1 )
  {
    v7 = -2147024809;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_4a9f1d31f1e33513501ec057b2633f65_Traceguids);
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
      a4,
      L"CWerInternalMetadata::Create Report == NULL\r\n");
    goto LABEL_95;
  }
  v7 = CXMLWriter::Initialize((CXMLWriter *)&v10, a2);
  if ( (v7 & 0x80000000) != 0 )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_4a9f1d31f1e33513501ec057b2633f65_Traceguids, v7);
    tlx::append_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
      a4,
      L"xmlWriter.Initialize failed with hr=0x%x\r\n",
      v7);
    goto LABEL_95;
  }
  v14 = 0;
  v15 = 0;
  v12 = L"WERReportMetadata";
  v13 = 17;
  v7 = CXMLWriter::BeginElement((unsigned int)&v10, (unsigned int)&v12, (unsigned int)&v15, 0, (__int64)&v14);
  if ( (v7 & 0x80000000) != 0 )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_4a9f1d31f1e33513501ec057b2633f65_Traceguids, v7);
    tlx::append_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
      a4,
      L"xmlWriter.BeginElement failed with hr=0x%x\r\n",
      v7);
    goto LABEL_95;
  }
  v7 = CWerInternalMetadata::WriteOsVersionInformation(&v10, a4);
  if ( (v7 & 0x80000000) != 0 )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_4a9f1d31f1e33513501ec057b2633f65_Traceguids, v7);
    tlx::append_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
      a4,
      L"WriteOsVersionInformation failed with hr=0x%x\r\n",
      v7);
    goto LABEL_95;
  }
  if ( *(_DWORD *)(a1 + 5872) != 4 )
  {
    v7 = CWerInternalMetadata::WriteProcessInformation((struct CXMLWriter *)&v10);
    if ( (v7 & 0x80000000) != 0 )
    {
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_4a9f1d31f1e33513501ec057b2633f65_Traceguids, v7);
      tlx::append_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
        a4,
        L"WriteProcessInformation failed with hr=0x%x\r\n",
        v7);
      goto LABEL_95;
    }
    v7 = CWerInternalMetadata::WriteProcessMetadata(&v10, a1);
    if ( (v7 & 0x80000000) != 0 )
    {
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_4a9f1d31f1e33513501ec057b2633f65_Traceguids, v7);
      tlx::append_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
        a4,
        L"WriteProcessMetadata failed with hr=0x%x\r\n",
        v7);
      goto LABEL_95;
    }
  }
  v7 = CWerInternalMetadata::WriteProblemSignatures(&v10, a1);
  if ( (v7 & 0x80000000) != 0 )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_4a9f1d31f1e33513501ec057b2633f65_Traceguids, v7);
    tlx::append_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
      a4,
      L"WriteProblemSignatures failed with hr=0x%x\r\n",
      v7);
    goto LABEL_95;
  }
  v7 = CWerInternalMetadata::WriteDynamicSignatures(&v10, a1);
  if ( (v7 & 0x80000000) != 0 )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_4a9f1d31f1e33513501ec057b2633f65_Traceguids, v7);
    tlx::append_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
      a4,
      L"WriteDynamicSignatures failed with hr=0x%x\r\n",
      v7);
    goto LABEL_95;
  }
  v7 = CWerInternalMetadata::WriteServiceInformation(&v10, a1);
  if ( (v7 & 0x80000000) != 0 )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_4a9f1d31f1e33513501ec057b2633f65_Traceguids, v7);
    tlx::append_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
      a4,
      L"WriteServiceInformation failed with hr=0x%x\r\n",
      v7);
    goto LABEL_95;
  }
  if ( v16 )
  {
    v7 = -2147024809;
    goto LABEL_58;
  }
  v8 = CPhoneInformation::LoadPhoneInfoDll(&v17, v18);
  v7 = v8;
  if ( v8 < 0 )
  {
    if ( v8 != -2147024770 )
    {
LABEL_58:
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_4a9f1d31f1e33513501ec057b2633f65_Traceguids, v7);
      tlx::append_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
        a4,
        L"phoneInformation.Initialize failed with hr=0x%x\r\n",
        v7);
      goto LABEL_95;
    }
  }
  else
  {
    v16 = 1;
  }
  v7 = CWerInternalMetadata::WriteSystemInformation(&v10, &v16, a4);
  if ( (v7 & 0x80000000) == 0 )
  {
    v7 = CWerInternalMetadata::WriteSecureBootState(&v10);
    if ( (v7 & 0x80000000) == 0 )
    {
      if ( a3 && (v7 = CWerInternalMetadata::WriteIntegrator(&v10, a3), (v7 & 0x80000000) != 0) )
      {
        if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_4a9f1d31f1e33513501ec057b2633f65_Traceguids, v7);
        tlx::append_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
          a4,
          L"WriteIntegrator failed with hr=0x%x\r\n",
          v7);
      }
      else if ( v16 && (v7 = CWerInternalMetadata::WritePhoneInformation(&v10, &v16, a4), (v7 & 0x80000000) != 0) )
      {
        if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_4a9f1d31f1e33513501ec057b2633f65_Traceguids, v7);
        tlx::append_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
          a4,
          L"WritePhoneInformation failed with hr=0x%x\r\n",
          v7);
      }
      else
      {
        v7 = CWerInternalMetadata::WriteContainerInformation(&v10);
        if ( (v7 & 0x80000000) == 0 )
        {
          v7 = CWerInternalMetadata::WriteTimelineInformation((struct CXMLWriter *)&v10);
          if ( (v7 & 0x80000000) == 0 )
          {
            v7 = CWerInternalMetadata::WriteReportInformation(&v10, a1);
            if ( (v7 & 0x80000000) == 0 )
            {
              v7 = 0;
            }
            else
            {
              if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_4a9f1d31f1e33513501ec057b2633f65_Traceguids, v7);
              tlx::append_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                a4,
                L"WriteReportInformation failed with hr=0x%x\r\n",
                v7);
            }
          }
          else
          {
            if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_4a9f1d31f1e33513501ec057b2633f65_Traceguids, v7);
            tlx::append_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
              a4,
              L"WriteTimelineInformation failed with hr=0x%x\r\n",
              v7);
          }
        }
        else
        {
          if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_4a9f1d31f1e33513501ec057b2633f65_Traceguids, v7);
          tlx::append_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
            a4,
            L"WriteContainerInformation failed with hr=0x%x\r\n",
            v7);
        }
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_4a9f1d31f1e33513501ec057b2633f65_Traceguids, v7);
      tlx::append_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
        a4,
        L"WriteSecureBootState failed with hr=0x%x\r\n",
        v7);
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_4a9f1d31f1e33513501ec057b2633f65_Traceguids, v7);
    tlx::append_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
      a4,
      L"WriteSystemInformation failed with hr=0x%x\r\n",
      v7);
  }
LABEL_95:
  if ( (unsigned __int64)(v10 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    v12 = L"WERReportMetadata";
    v13 = 17;
    CXMLWriter::EndElement(&v10, &v12);
    v10 = -1;
  }
  CPhoneInformation::~CPhoneInformation((CPhoneInformation *)&v16);
  return v7;
}

```

## disassembly

```asm
0x18008f908  push    rbp
0x18008f90a  push    rbx
0x18008f90b  push    rsi
0x18008f90c  push    rdi
0x18008f90d  push    r14
0x18008f90f  lea     rbp, [rsp-37h]
0x18008f914  sub     rsp, 90h
0x18008f91b  mov     rdi, r9
0x18008f91e  mov     r14, r8
0x18008f921  mov     rsi, rcx
0x18008f924  mov     [rbp+57h+var_80], 0FFFFFFFFFFFFFFFFh
0x18008f92c  mov     [rbp+57h+var_78], 0
0x18008f933  mov     [rbp+57h+var_40], 0
0x18008f93a  mov     [rbp+57h+var_38], 0
0x18008f942  mov     [rbp+57h+var_30], 0
0x18008f94a  test    rcx, rcx
0x18008f94d  jnz     short loc_18008F994
0x18008f94f  mov     ebx, 80070057h
0x18008f954  lea     rax, WPP_GLOBAL_Control
0x18008f95b  mov     rcx, cs:WPP_GLOBAL_Control
0x18008f962  cmp     rcx, rax
0x18008f965  jz      short loc_18008F980
0x18008f967  test    byte ptr [rcx+1Ch], 1
0x18008f96b  jz      short loc_18008F980
0x18008f96d  lea     edx, [rsi+0Fh]
0x18008f970  lea     r8, WPP_4a9f1d31f1e33513501ec057b2633f65_Traceguids
0x18008f977  mov     rcx, [rcx+10h]
0x18008f97b  call    WPP_SF_
0x18008f980  lea     rdx, aCwerinternalme; "CWerInternalMetadata::Create Report == "...
0x18008f987  mov     rcx, rdi
0x18008f98a  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *)
0x18008f98f  jmp     loc_18008FEFF
0x18008f994  lea     rcx, [rbp+57h+var_80]; this
0x18008f998  call    ?Initialize@CXMLWriter@@QEAAJPEAX@Z; CXMLWriter::Initialize(void *)
0x18008f99d  mov     ebx, eax
0x18008f99f  test    eax, eax
0x18008f9a1  jns     short loc_18008F9EB
0x18008f9a3  lea     rax, WPP_GLOBAL_Control
0x18008f9aa  mov     rcx, cs:WPP_GLOBAL_Control
0x18008f9b1  cmp     rcx, rax
0x18008f9b4  jz      short loc_18008F9D4
0x18008f9b6  test    byte ptr [rcx+1Ch], 1
0x18008f9ba  jz      short loc_18008F9D4
0x18008f9bc  mov     edx, 10h
0x18008f9c1  mov     r9d, ebx
0x18008f9c4  lea     r8, WPP_4a9f1d31f1e33513501ec057b2633f65_Traceguids
0x18008f9cb  mov     rcx, [rcx+10h]
0x18008f9cf  call    WPP_SF_d
0x18008f9d4  lea     rdx, aXmlwriterIniti; "xmlWriter.Initialize failed with hr=0x%"...
0x18008f9db  mov     r8d, ebx
0x18008f9de  mov     rcx, rdi
0x18008f9e1  call    ??$append_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::append_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x18008f9e6  jmp     loc_18008FEFF
0x18008f9eb  xorps   xmm0, xmm0
0x18008f9ee  movdqa  [rbp+57h+var_60], xmm0
0x18008f9f3  xorps   xmm1, xmm1
0x18008f9f6  movdqa  [rbp+57h+var_50], xmm1
0x18008f9fb  lea     rax, aWerreportmetad; "WERReportMetadata"
0x18008fa02  mov     [rbp+57h+var_70], rax
0x18008fa06  mov     [rbp+57h+var_68], 11h
0x18008fa0e  lea     rax, [rbp+57h+var_60]
0x18008fa12  mov     [rsp+0B0h+var_90], rax
0x18008fa17  xor     r9d, r9d
0x18008fa1a  lea     r8, [rbp+57h+var_50]
0x18008fa1e  lea     rdx, [rbp+57h+var_70]
0x18008fa22  lea     rcx, [rbp+57h+var_80]
0x18008fa26  call    ?BeginElement@CXMLWriter@@QEAAJV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@0_NV?$span@$$CBUCXMLAttribute@@$0?0@3@@Z; CXMLWriter::BeginElement(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,bool,utl::span<CXMLAttribute const,-1>)
0x18008fa2b  mov     ebx, eax
0x18008fa2d  test    eax, eax
0x18008fa2f  jns     short loc_18008FA6E
0x18008fa31  lea     rax, WPP_GLOBAL_Control
0x18008fa38  mov     rcx, cs:WPP_GLOBAL_Control
0x18008fa3f  cmp     rcx, rax
0x18008fa42  jz      short loc_18008FA62
0x18008fa44  test    byte ptr [rcx+1Ch], 1
0x18008fa48  jz      short loc_18008FA62
0x18008fa4a  mov     edx, 11h
0x18008fa4f  mov     r9d, ebx
0x18008fa52  lea     r8, WPP_4a9f1d31f1e33513501ec057b2633f65_Traceguids
0x18008fa59  mov     rcx, [rcx+10h]
0x18008fa5d  call    WPP_SF_d
0x18008fa62  lea     rdx, aXmlwriterBegin; "xmlWriter.BeginElement failed with hr=0"...
0x18008fa69  jmp     loc_18008F9DB
0x18008fa6e  mov     rdx, rdi
0x18008fa71  lea     rcx, [rbp+57h+var_80]
0x18008fa75  call    ?WriteOsVersionInformation@CWerInternalMetadata@@CAJPEAVCXMLWriter@@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CWerInternalMetadata::WriteOsVersionInformation(CXMLWriter *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x18008fa7a  mov     ebx, eax
0x18008fa7c  test    eax, eax
0x18008fa7e  jns     short loc_18008FABD
0x18008fa80  lea     rax, WPP_GLOBAL_Control
0x18008fa87  mov     rcx, cs:WPP_GLOBAL_Control
0x18008fa8e  cmp     rcx, rax
0x18008fa91  jz      short loc_18008FAB1
0x18008fa93  test    byte ptr [rcx+1Ch], 1
0x18008fa97  jz      short loc_18008FAB1
0x18008fa99  mov     edx, 12h
0x18008fa9e  mov     r9d, ebx
0x18008faa1  lea     r8, WPP_4a9f1d31f1e33513501ec057b2633f65_Traceguids
0x18008faa8  mov     rcx, [rcx+10h]
0x18008faac  call    WPP_SF_d
0x18008fab1  lea     rdx, aWriteosversion; "WriteOsVersionInformation failed with h"...
0x18008fab8  jmp     loc_18008F9DB
0x18008fabd  cmp     dword ptr [rsi+16F0h], 4
0x18008fac4  jz      loc_18008FB6B
0x18008faca  mov     r8, rdi
0x18008facd  mov     rdx, rsi
0x18008fad0  lea     rcx, [rbp+57h+var_80]; struct CXMLWriter *
0x18008fad4  call    ?WriteProcessInformation@CWerInternalMetadata@@CAJPEAVCXMLWriter@@PEAVCReport@@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CWerInternalMetadata::WriteProcessInformation(CXMLWriter *,CReport *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x18008fad9  mov     ebx, eax
0x18008fadb  test    eax, eax
0x18008fadd  jns     short loc_18008FB1C
0x18008fadf  lea     rax, WPP_GLOBAL_Control
0x18008fae6  mov     rcx, cs:WPP_GLOBAL_Control
0x18008faed  cmp     rcx, rax
0x18008faf0  jz      short loc_18008FB10
0x18008faf2  test    byte ptr [rcx+1Ch], 1
0x18008faf6  jz      short loc_18008FB10
0x18008faf8  mov     edx, 13h
0x18008fafd  mov     r9d, ebx
0x18008fb00  lea     r8, WPP_4a9f1d31f1e33513501ec057b2633f65_Traceguids
0x18008fb07  mov     rcx, [rcx+10h]
0x18008fb0b  call    WPP_SF_d
0x18008fb10  lea     rdx, aWriteprocessin; "WriteProcessInformation failed with hr="...
0x18008fb17  jmp     loc_18008F9DB
0x18008fb1c  mov     rdx, rsi
0x18008fb1f  lea     rcx, [rbp+57h+var_80]
0x18008fb23  call    ?WriteProcessMetadata@CWerInternalMetadata@@CAJPEAVCXMLWriter@@PEAVCReport@@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CWerInternalMetadata::WriteProcessMetadata(CXMLWriter *,CReport *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x18008fb28  mov     ebx, eax
0x18008fb2a  test    eax, eax
0x18008fb2c  jns     short loc_18008FB6B
0x18008fb2e  lea     rax, WPP_GLOBAL_Control
0x18008fb35  mov     rcx, cs:WPP_GLOBAL_Control
0x18008fb3c  cmp     rcx, rax
0x18008fb3f  jz      short loc_18008FB5F
0x18008fb41  test    byte ptr [rcx+1Ch], 1
0x18008fb45  jz      short loc_18008FB5F
0x18008fb47  mov     edx, 14h
0x18008fb4c  mov     r9d, ebx
0x18008fb4f  lea     r8, WPP_4a9f1d31f1e33513501ec057b2633f65_Traceguids
0x18008fb56  mov     rcx, [rcx+10h]
0x18008fb5a  call    WPP_SF_d
0x18008fb5f  lea     rdx, aWriteprocessme; "WriteProcessMetadata failed with hr=0x%"...
0x18008fb66  jmp     loc_18008F9DB
0x18008fb6b  mov     rdx, rsi
0x18008fb6e  lea     rcx, [rbp+57h+var_80]
0x18008fb72  call    ?WriteProblemSignatures@CWerInternalMetadata@@CAJPEAVCXMLWriter@@PEAVCReport@@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CWerInternalMetadata::WriteProblemSignatures(CXMLWriter *,CReport *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x18008fb77  mov     ebx, eax
0x18008fb79  test    eax, eax
0x18008fb7b  jns     short loc_18008FBBA
0x18008fb7d  lea     rax, WPP_GLOBAL_Control
0x18008fb84  mov     rcx, cs:WPP_GLOBAL_Control
0x18008fb8b  cmp     rcx, rax
0x18008fb8e  jz      short loc_18008FBAE
0x18008fb90  test    byte ptr [rcx+1Ch], 1
0x18008fb94  jz      short loc_18008FBAE
0x18008fb96  mov     edx, 15h
0x18008fb9b  mov     r9d, ebx
0x18008fb9e  lea     r8, WPP_4a9f1d31f1e33513501ec057b2633f65_Traceguids
0x18008fba5  mov     rcx, [rcx+10h]
0x18008fba9  call    WPP_SF_d
0x18008fbae  lea     rdx, aWriteproblemsi; "WriteProblemSignatures failed with hr=0"...
0x18008fbb5  jmp     loc_18008F9DB
0x18008fbba  mov     rdx, rsi
0x18008fbbd  lea     rcx, [rbp+57h+var_80]
0x18008fbc1  call    ?WriteDynamicSignatures@CWerInternalMetadata@@CAJPEAVCXMLWriter@@PEAVCReport@@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CWerInternalMetadata::WriteDynamicSignatures(CXMLWriter *,CReport *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x18008fbc6  mov     ebx, eax
0x18008fbc8  test    eax, eax
0x18008fbca  jns     short loc_18008FC09
0x18008fbcc  lea     rax, WPP_GLOBAL_Control
0x18008fbd3  mov     rcx, cs:WPP_GLOBAL_Control
0x18008fbda  cmp     rcx, rax
0x18008fbdd  jz      short loc_18008FBFD
0x18008fbdf  test    byte ptr [rcx+1Ch], 1
0x18008fbe3  jz      short loc_18008FBFD
0x18008fbe5  mov     edx, 16h
0x18008fbea  mov     r9d, ebx
0x18008fbed  lea     r8, WPP_4a9f1d31f1e33513501ec057b2633f65_Traceguids
0x18008fbf4  mov     rcx, [rcx+10h]
0x18008fbf8  call    WPP_SF_d
0x18008fbfd  lea     rdx, aWritedynamicsi; "WriteDynamicSignatures failed with hr=0"...
0x18008fc04  jmp     loc_18008F9DB
0x18008fc09  mov     rdx, rsi
0x18008fc0c  lea     rcx, [rbp+57h+var_80]
0x18008fc10  call    ?WriteServiceInformation@CWerInternalMetadata@@CAJPEAVCXMLWriter@@PEAVCReport@@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CWerInternalMetadata::WriteServiceInformation(CXMLWriter *,CReport *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x18008fc15  mov     ebx, eax
0x18008fc17  test    eax, eax
0x18008fc19  jns     short loc_18008FC58
0x18008fc1b  lea     rax, WPP_GLOBAL_Control
0x18008fc22  mov     rcx, cs:WPP_GLOBAL_Control
0x18008fc29  cmp     rcx, rax
0x18008fc2c  jz      short loc_18008FC4C
0x18008fc2e  test    byte ptr [rcx+1Ch], 1
0x18008fc32  jz      short loc_18008FC4C
0x18008fc34  mov     edx, 17h
0x18008fc39  mov     r9d, ebx
0x18008fc3c  lea     r8, WPP_4a9f1d31f1e33513501ec057b2633f65_Traceguids
0x18008fc43  mov     rcx, [rcx+10h]
0x18008fc47  call    WPP_SF_d
0x18008fc4c  lea     rdx, aWriteservicein; "WriteServiceInformation failed with hr="...
0x18008fc53  jmp     loc_18008F9DB
0x18008fc58  cmp     [rbp+57h+var_40], 0
0x18008fc5c  jz      short loc_18008FC65
0x18008fc5e  mov     ebx, 80070057h
0x18008fc63  jmp     short loc_18008FCDD
0x18008fc65  lea     rdx, [rbp+57h+var_30]
0x18008fc69  lea     rcx, [rbp+57h+var_38]
0x18008fc6d  call    ?LoadPhoneInfoDll@CPhoneInformation@@CAJPEAV?$unique_any@U?$handle_traits@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@Z$0A@@tlx@@@tlx@@PEAP6AHW4_PHONE_INFORMATION_KEY@@PEA_W_KPEA_K@Z@Z; CPhoneInformation::LoadPhoneInfoDll(tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),0>> *,int (**)(_PHONE_INFORMATION_KEY,wchar_t *,unsigned __int64,unsigned __int64 *))
0x18008fc72  mov     ebx, eax
0x18008fc74  test    eax, eax
0x18008fc76  js      short loc_18008FCD6
0x18008fc78  mov     [rbp+57h+var_40], 1
0x18008fc7f  mov     r8, rdi
0x18008fc82  lea     rdx, [rbp+57h+var_40]
0x18008fc86  lea     rcx, [rbp+57h+var_80]
0x18008fc8a  call    ?WriteSystemInformation@CWerInternalMetadata@@CAJPEAVCXMLWriter@@PEAVCPhoneInformation@@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CWerInternalMetadata::WriteSystemInformation(CXMLWriter *,CPhoneInformation *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x18008fc8f  mov     ebx, eax
0x18008fc91  test    eax, eax
0x18008fc93  jns     loc_18008FD1A
0x18008fc99  lea     rax, WPP_GLOBAL_Control
0x18008fca0  mov     rcx, cs:WPP_GLOBAL_Control
0x18008fca7  cmp     rcx, rax
0x18008fcaa  jz      short loc_18008FCCA
0x18008fcac  test    byte ptr [rcx+1Ch], 1
0x18008fcb0  jz      short loc_18008FCCA
0x18008fcb2  mov     edx, 19h
0x18008fcb7  mov     r9d, ebx
0x18008fcba  lea     r8, WPP_4a9f1d31f1e33513501ec057b2633f65_Traceguids
0x18008fcc1  mov     rcx, [rcx+10h]
0x18008fcc5  call    WPP_SF_d
0x18008fcca  lea     rdx, aWritesysteminf_0; "WriteSystemInformation failed with hr=0"...
0x18008fcd1  jmp     loc_18008F9DB
0x18008fcd6  cmp     eax, 8007007Eh
0x18008fcdb  jz      short loc_18008FC7F
0x18008fcdd  lea     rax, WPP_GLOBAL_Control
0x18008fce4  mov     rcx, cs:WPP_GLOBAL_Control
0x18008fceb  cmp     rcx, rax
0x18008fcee  jz      short loc_18008FD0E
0x18008fcf0  test    byte ptr [rcx+1Ch], 1
0x18008fcf4  jz      short loc_18008FD0E
0x18008fcf6  mov     edx, 18h
0x18008fcfb  mov     r9d, ebx
0x18008fcfe  lea     r8, WPP_4a9f1d31f1e33513501ec057b2633f65_Traceguids
0x18008fd05  mov     rcx, [rcx+10h]
0x18008fd09  call    WPP_SF_d
0x18008fd0e  lea     rdx, aPhoneinformati_0; "phoneInformation.Initialize failed with"...
0x18008fd15  jmp     loc_18008F9DB
0x18008fd1a  lea     rcx, [rbp+57h+var_80]
0x18008fd1e  call    ?WriteSecureBootState@CWerInternalMetadata@@CAJPEAVCXMLWriter@@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CWerInternalMetadata::WriteSecureBootState(CXMLWriter *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x18008fd23  mov     ebx, eax
0x18008fd25  test    eax, eax
0x18008fd27  jns     short loc_18008FD66
0x18008fd29  lea     rax, WPP_GLOBAL_Control
0x18008fd30  mov     rcx, cs:WPP_GLOBAL_Control
0x18008fd37  cmp     rcx, rax
0x18008fd3a  jz      short loc_18008FD5A
0x18008fd3c  test    byte ptr [rcx+1Ch], 1
0x18008fd40  jz      short loc_18008FD5A
0x18008fd42  mov     edx, 1Ah
0x18008fd47  mov     r9d, ebx
0x18008fd4a  lea     r8, WPP_4a9f1d31f1e33513501ec057b2633f65_Traceguids
0x18008fd51  mov     rcx, [rcx+10h]
0x18008fd55  call    WPP_SF_d
0x18008fd5a  lea     rdx, aWritesecureboo; "WriteSecureBootState failed with hr=0x%"...
0x18008fd61  jmp     loc_18008F9DB
0x18008fd66  test    r14, r14
0x18008fd69  jz      short loc_18008FDBA
0x18008fd6b  mov     rdx, r14
0x18008fd6e  lea     rcx, [rbp+57h+var_80]
0x18008fd72  call    ?WriteIntegrator@CWerInternalMetadata@@CAJPEAVCXMLWriter@@PEAVCReportHandleInstance@@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CWerInternalMetadata::WriteIntegrator(CXMLWriter *,CReportHandleInstance *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x18008fd77  mov     ebx, eax
0x18008fd79  test    eax, eax
0x18008fd7b  jns     short loc_18008FDBA
0x18008fd7d  lea     rax, WPP_GLOBAL_Control
0x18008fd84  mov     rcx, cs:WPP_GLOBAL_Control
0x18008fd8b  cmp     rcx, rax
0x18008fd8e  jz      short loc_18008FDAE
0x18008fd90  test    byte ptr [rcx+1Ch], 1
0x18008fd94  jz      short loc_18008FDAE
0x18008fd96  mov     edx, 1Bh
0x18008fd9b  mov     r9d, ebx
0x18008fd9e  lea     r8, WPP_4a9f1d31f1e33513501ec057b2633f65_Traceguids
0x18008fda5  mov     rcx, [rcx+10h]
0x18008fda9  call    WPP_SF_d
0x18008fdae  lea     rdx, aWriteintegrato; "WriteIntegrator failed with hr=0x%x\r\n"
0x18008fdb5  jmp     loc_18008F9DB
0x18008fdba  cmp     [rbp+57h+var_40], 0
0x18008fdbe  jz      short loc_18008FE13
0x18008fdc0  mov     r8, rdi
0x18008fdc3  lea     rdx, [rbp+57h+var_40]
0x18008fdc7  lea     rcx, [rbp+57h+var_80]
0x18008fdcb  call    ?WritePhoneInformation@CWerInternalMetadata@@CAJPEAVCXMLWriter@@PEAVCPhoneInformation@@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CWerInternalMetadata::WritePhoneInformation(CXMLWriter *,CPhoneInformation *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x18008fdd0  mov     ebx, eax
0x18008fdd2  test    eax, eax
0x18008fdd4  jns     short loc_18008FE13
0x18008fdd6  lea     rax, WPP_GLOBAL_Control
0x18008fddd  mov     rcx, cs:WPP_GLOBAL_Control
0x18008fde4  cmp     rcx, rax
0x18008fde7  jz      short loc_18008FE07
0x18008fde9  test    byte ptr [rcx+1Ch], 1
0x18008fded  jz      short loc_18008FE07
  ... truncated ...
```
