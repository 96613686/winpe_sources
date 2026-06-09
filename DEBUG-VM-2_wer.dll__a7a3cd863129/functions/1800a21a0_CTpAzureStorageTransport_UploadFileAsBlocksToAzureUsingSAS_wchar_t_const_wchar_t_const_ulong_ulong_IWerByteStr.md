# CTpAzureStorageTransport::UploadFileAsBlocksToAzureUsingSAS(wchar_t const *,wchar_t const *,ulong,ulong,IWerByteStream *,unsigned __int64,void *,ulong &,unsigned __int64 &,ITpCallbacks *)

- ea: `0x1800a21a0`
- end: `0x1800a285c`
- name: `?UploadFileAsBlocksToAzureUsingSAS@CTpAzureStorageTransport@@CAJPEB_W0KKPEAUIWerByteStream@@_KPEAXAEAKAEA_KPEAUITpCallbacks@@@Z`
- size: `1724`
- prototype: `__int64 __fastcall(const wchar_t *, const wchar_t *, unsigned int, unsigned int, struct IWerByteStream *, unsigned __int64, void *, unsigned int *, unsigned __int64 *, struct ITpCallbacks *)`
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800a2864`

## callees

- `0x18000bc10`
- `0x18000cc74`
- `0x18000dad0`
- `0x18000e7fc`
- `0x180013a20`
- `0x18001fe24`
- `0x180026560`
- `0x18002b7a4`
- `0x18002fff4`
- `0x18003941c`
- `0x18003c1e4`
- `0x180046674`
- `0x18004a12c`
- `0x180050db0`
- `0x1800517cc`
- `0x180051ff8`
- `0x18009a348`
- `0x18009a49c`
- `0x1800a1aa0`
- `0x1800a1ad0`
- `0x1800a1d88`
- `0x1800a21a0`
- `0x1800ac010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800a2325`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800a262f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800a2325`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800a262f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a2504`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a2649`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a2504`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a2649`
- `ext-ms-win-wer-xbox-l1-1-0!XerTpUpload` at `0x1800a248c`
- `ext-ms-win-wer-xbox-l1-1-0!XerTpUpload` at `0x1800a2799`
- `ext-ms-win-wer-xbox-l1-1-0!XerTpUpload` at `0x1800a248c`
- `ext-ms-win-wer-xbox-l1-1-0!XerTpUpload` at `0x1800a2799`
- `ext-ms-win-wer-xbox-l1-1-0!XerTpCompleteUpload` at `0x1800a249b`
- `ext-ms-win-wer-xbox-l1-1-0!XerTpCompleteUpload` at `0x1800a27a8`
- `ext-ms-win-wer-xbox-l1-1-0!XerTpCompleteUpload` at `0x1800a249b`
- `ext-ms-win-wer-xbox-l1-1-0!XerTpCompleteUpload` at `0x1800a27a8`

## string_xrefs

- `0x1800a22c0`: `%ls&comp=blocklist`
- `0x1800a23c5`: `%ls&comp=block&blockid=%ls`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CTpAzureStorageTransport::UploadFileAsBlocksToAzureUsingSAS(
        const wchar_t *a1,
        const wchar_t *a2,
        int a3,
        unsigned int a4,
        struct IWerByteStream *a5,
        unsigned __int64 a6,
        void *a7,
        unsigned int *a8,
        unsigned __int64 *a9,
        struct ITpCallbacks *a10)
{
  __int128 v12; // xmm0
  __int64 v14; // rdi
  signed int PutBlockListXml; // ebx
  wchar_t *v16; // rcx
  __int64 v17; // rdx
  unsigned int v19; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v20[4]; // [rsp+38h] [rbp-C8h] BYREF
  const wchar_t *v21; // [rsp+58h] [rbp-A8h]
  struct ITpCallbacks *v22; // [rsp+60h] [rbp-A0h]
  void *v23; // [rsp+68h] [rbp-98h]
  __int128 v24; // [rsp+70h] [rbp-90h] BYREF
  __int64 v25; // [rsp+80h] [rbp-80h]
  void **v26; // [rsp+88h] [rbp-78h] BYREF
  __int128 v27; // [rsp+90h] [rbp-70h]
  __int64 v28; // [rsp+A0h] [rbp-60h]
  int v29; // [rsp+A8h] [rbp-58h]
  const wchar_t *v30; // [rsp+B0h] [rbp-50h]
  __int64 v31; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v32; // [rsp+C0h] [rbp-40h]
  void *v33; // [rsp+D8h] [rbp-28h] BYREF
  int v34; // [rsp+E0h] [rbp-20h]
  _QWORD v35[4]; // [rsp+F8h] [rbp-8h] BYREF
  _QWORD v36[4]; // [rsp+118h] [rbp+18h] BYREF
  _QWORD v37[4]; // [rsp+138h] [rbp+38h] BYREF
  _QWORD v38[5]; // [rsp+158h] [rbp+58h] BYREF
  _QWORD v39[3]; // [rsp+180h] [rbp+80h] BYREF
  __int16 v40; // [rsp+198h] [rbp+98h]
  __int128 *v41; // [rsp+1A0h] [rbp+A0h]
  int v42; // [rsp+1A8h] [rbp+A8h]
  BOOL v43; // [rsp+1B0h] [rbp+B0h]
  unsigned __int64 v44; // [rsp+1B8h] [rbp+B8h]
  __int64 v45; // [rsp+1C0h] [rbp+C0h]
  int v46; // [rsp+1C8h] [rbp+C8h]
  __int64 v47; // [rsp+1D0h] [rbp+D0h]
  void *v48; // [rsp+1D8h] [rbp+D8h]
  struct ITpCallbacks *v49; // [rsp+1E8h] [rbp+E8h]
  _QWORD v50[3]; // [rsp+230h] [rbp+130h] BYREF
  __int16 v51; // [rsp+248h] [rbp+148h]
  __int128 *v52; // [rsp+250h] [rbp+150h]
  int v53; // [rsp+258h] [rbp+158h]
  BOOL v54; // [rsp+260h] [rbp+160h]
  int v55; // [rsp+278h] [rbp+178h]
  __int64 v56; // [rsp+280h] [rbp+180h]
  void *v57; // [rsp+288h] [rbp+188h]
  struct ITpCallbacks *v58; // [rsp+298h] [rbp+198h]
  struct _SYSTEMTIME SystemTime; // [rsp+2E0h] [rbp+1E0h] BYREF

  v19 = a4;
  v30 = a2;
  v21 = a1;
  v23 = a7;
  v22 = a10;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v20);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&v31);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v38);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v35);
  v12 = 0;
  SystemTime = 0;
  *(double *)&v12 = utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::basic_string<char,utl::char_traits<char>,utl::allocator<char>>(&v33);
  v26 = &CMemoryByteStream::`vftable';
  v27 = v12;
  v28 = 0;
  v29 = 0;
  memset_0(v39, 0, 0xB0u);
  memset_0(v50, 0, 0xB0u);
  v24 = 0;
  v25 = 0;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v37);
  *a9 = 0;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v36);
  tlx::append_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v36, L"%ls&comp=blocklist", a2);
  *(_QWORD *)&v24 = a10;
  while ( 1 )
  {
    if ( a6 >= (*(__int64 (__fastcall **)(struct IWerByteStream *))(*(_QWORD *)a5 + 32LL))(a5) )
    {
      PutBlockListXml = CTpAzureStorageTransport::GetPutBlockListXml(*a8, v35);
      if ( PutBlockListXml >= 0 )
      {
        PutBlockListXml = tlx::_AppendWideImpl<utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>,wchar_t>(
                            &v33,
                            v35[0],
                            (__int64)(v35[1] - v35[0]) >> 1);
        if ( PutBlockListXml >= 0 )
        {
          CMemoryByteStream::OpenForReadWrite((CMemoryByteStream *)&v26);
          PutBlockListXml = CMemoryByteStream::Write((CMemoryByteStream *)&v26, v33, v34 - (_DWORD)v33, &v19, 0);
          if ( PutBlockListXml >= 0 )
          {
            GetSystemTime(&SystemTime);
            if ( (int)CTpAzureStorageTransport::GetInternetTime(&SystemTime, &v31) >= 0 )
            {
              *((_QWORD *)&v24 + 1) = (unsigned int)v28;
              LOBYTE(v25) = 0;
              v20[1] = v20[0];
              *(_WORD *)v20[0] = 0;
              tlx::append_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                v20,
                L"Content-Length: %llu\n",
                (unsigned int)v28);
              utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                v20,
                L"x-ms-version: 2017-04-17\n");
              utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(v20, L"x-ms-date: ");
              utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                v20,
                v31,
                (v32 - v31) >> 1);
              utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(v20, 10);
              v50[0] = v21;
              v50[1] = v36[0];
              v50[2] = &v26;
              v51 = 0;
              v52 = &v24;
              v53 = 1;
              v54 = (a3 & 1) == 0;
              v55 = a3;
              v56 = v20[0];
              v58 = v22;
              v57 = v23;
              if ( (unsigned __int8)IsXerGetMachineIdPresent() )
              {
                PutBlockListXml = XerTpUpload(v50);
                XerTpCompleteUpload(v39);
              }
              else
              {
                PutBlockListXml = TpUpload((struct _WER_TP_UPLOAD_STATE *)v50, 0);
                TpCompleteUpload((struct _WER_TP_UPLOAD_STATE *)v39);
              }
              if ( PutBlockListXml >= 0 )
              {
                PutBlockListXml = 0;
              }
              else if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  24,
                  WPP_2630288230103b96da97e4a7a3753ae6_Traceguids,
                  (unsigned int)PutBlockListXml);
              }
            }
            else
            {
              PutBlockListXml = GetLastError();
              v16 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
              {
                v17 = 23;
                goto LABEL_21;
              }
            }
          }
          else
          {
            v16 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
            {
              v17 = 22;
              goto LABEL_21;
            }
          }
        }
        else
        {
          v16 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          {
            v17 = 21;
            goto LABEL_21;
          }
        }
      }
      else
      {
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          v17 = 20;
          goto LABEL_21;
        }
      }
      goto LABEL_46;
    }
    v14 = v19;
    if ( v19 + a6 >= (*(__int64 (__fastcall **)(struct IWerByteStream *))(*(_QWORD *)a5 + 32LL))(a5) )
      v14 = (*(__int64 (__fastcall **)(struct IWerByteStream *))(*(_QWORD *)a5 + 32LL))(a5) - a6;
    GetSystemTime(&SystemTime);
    if ( (int)CTpAzureStorageTransport::GetInternetTime(&SystemTime, &v31) < 0 )
      break;
    tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v20, L"Content-Length: %llu\n", v14);
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
      v20,
      L"x-ms-version: 2017-04-17\n");
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(v20, L"x-ms-date: ");
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(v20, v31, (v32 - v31) >> 1);
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(v20, 10);
    PutBlockListXml = CTpAzureStorageTransport::GetBlockId(*a8 + 1, 1, v37);
    if ( PutBlockListXml < 0 )
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_46;
      v17 = 18;
LABEL_21:
      WPP_SF_d(
        *((_QWORD *)v16 + 2),
        v17,
        WPP_2630288230103b96da97e4a7a3753ae6_Traceguids,
        (unsigned int)PutBlockListXml);
      goto LABEL_46;
    }
    tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
      v38,
      L"%ls&comp=block&blockid=%ls",
      v30,
      v37[0]);
    *((_QWORD *)&v24 + 1) = v14;
    LOBYTE(v25) = 0;
    v39[0] = v21;
    v39[1] = v38[0];
    v39[2] = a5;
    v40 = 0;
    v41 = &v24;
    v42 = 1;
    v43 = (a3 & 1) == 0;
    v46 = a3;
    v47 = v20[0];
    v44 = a6;
    v45 = v14;
    v49 = v22;
    v48 = v23;
    if ( (unsigned __int8)IsXerGetMachineIdPresent() )
    {
      PutBlockListXml = XerTpUpload(v39);
      XerTpCompleteUpload(v39);
    }
    else
    {
      PutBlockListXml = TpUpload((struct _WER_TP_UPLOAD_STATE *)v39, 0);
      TpCompleteUpload((struct _WER_TP_UPLOAD_STATE *)v39);
    }
    if ( PutBlockListXml < 0 )
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
        goto LABEL_46;
      v17 = 19;
      goto LABEL_21;
    }
    ++*a8;
    *a9 += v14;
    a6 += v14;
  }
  PutBlockListXml = GetLastError();
  v16 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    v17 = 17;
    goto LABEL_21;
  }
LABEL_46:
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v36);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v37);
  CMemoryByteStream::~CMemoryByteStream((CMemoryByteStream *)&v26);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&v33);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v35);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v38);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&v31);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v20);
  return (unsigned int)PutBlockListXml;
}

```

## disassembly

```asm
0x1800a21a0  push    rbp
0x1800a21a2  push    rbx
0x1800a21a3  push    rsi
0x1800a21a4  push    rdi
0x1800a21a5  push    r12
0x1800a21a7  push    r13
0x1800a21a9  push    r14
0x1800a21ab  push    r15
0x1800a21ad  lea     rbp, [rsp-208h]
0x1800a21b5  sub     rsp, 308h
0x1800a21bc  mov     rax, cs:__security_cookie
0x1800a21c3  xor     rax, rsp
0x1800a21c6  mov     [rbp+240h+var_50], rax
0x1800a21cd  mov     [rsp+340h+var_310], r9d
0x1800a21d2  mov     r13d, r8d
0x1800a21d5  mov     rbx, rdx
0x1800a21d8  mov     [rbp+240h+var_290], rdx
0x1800a21dc  mov     [rsp+340h+var_2E8], rcx
0x1800a21e1  mov     rsi, [rbp+240h+arg_20]
0x1800a21e8  mov     rax, [rbp+240h+arg_30]
0x1800a21ef  mov     [rsp+340h+var_2D8], rax
0x1800a21f4  mov     r15, [rbp+240h+arg_38]
0x1800a21fb  mov     r12, [rbp+240h+arg_40]
0x1800a2202  mov     rdi, [rbp+240h+arg_48]
0x1800a2209  mov     [rsp+340h+var_2E0], rdi
0x1800a220e  lea     rcx, [rsp+340h+var_308]; void *
0x1800a2213  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800a2218  nop
0x1800a2219  lea     rcx, [rbp+240h+var_288]; void *
0x1800a221d  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800a2222  nop
0x1800a2223  lea     rcx, [rbp+240h+var_1E8]; void *
0x1800a2227  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800a222c  nop
0x1800a222d  lea     rcx, [rbp+240h+var_248]; void *
0x1800a2231  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800a2236  nop
0x1800a2237  xorps   xmm0, xmm0
0x1800a223a  movups  xmmword ptr [rbp+240h+SystemTime.wYear], xmm0
0x1800a2241  lea     rcx, [rbp+240h+var_268]
0x1800a2245  call    ??0?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@QEAA@XZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::basic_string<char,utl::char_traits<char>,utl::allocator<char>>(void)
0x1800a224a  nop
0x1800a224b  lea     rax, ??_7CMemoryByteStream@@6B@; const CMemoryByteStream::`vftable'
0x1800a2252  mov     [rbp+240h+var_2B8], rax
0x1800a2256  movdqu  [rbp+240h+var_2B0], xmm0
0x1800a225b  xor     eax, eax
0x1800a225d  mov     [rbp+240h+var_2A0], rax
0x1800a2261  mov     [rbp+240h+var_298], eax
0x1800a2264  mov     r14d, 0B0h
0x1800a226a  mov     r8d, r14d; Size
0x1800a226d  xor     edx, edx; Val
0x1800a226f  lea     rcx, [rbp+240h+var_1C0]; void *
0x1800a2276  call    memset_0
0x1800a227b  mov     r8d, r14d; Size
0x1800a227e  xor     edx, edx; Val
0x1800a2280  lea     rcx, [rbp+240h+var_110]; void *
0x1800a2287  call    memset_0
0x1800a228c  xorps   xmm0, xmm0
0x1800a228f  xor     eax, eax
0x1800a2291  movups  [rsp+340h+var_2D0], xmm0
0x1800a2296  mov     [rbp+240h+var_2C0], rax
0x1800a229a  mov     r14, [rbp+240h+arg_28]
0x1800a22a1  lea     rcx, [rbp+240h+var_208]; void *
0x1800a22a5  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800a22aa  nop
0x1800a22ab  mov     qword ptr [r12], 0
0x1800a22b3  lea     rcx, [rbp+240h+var_228]; void *
0x1800a22b7  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800a22bc  nop
0x1800a22bd  mov     r8, rbx
0x1800a22c0  lea     rdx, aLsCompBlocklis; "%ls&comp=blocklist"
0x1800a22c7  lea     rcx, [rbp+240h+var_228]
0x1800a22cb  call    ??$append_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::append_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x1800a22d0  mov     qword ptr [rsp+340h+var_2D0], rdi
0x1800a22d5  mov     rax, [rsi]
0x1800a22d8  mov     rcx, rsi
0x1800a22db  mov     rax, [rax+20h]
0x1800a22df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a22e4  cmp     r14, rax
0x1800a22e7  jnb     loc_1800A254A
0x1800a22ed  mov     edi, [rsp+340h+var_310]
0x1800a22f1  mov     rax, [rsi]
0x1800a22f4  mov     rcx, rsi
0x1800a22f7  mov     rax, [rax+20h]
0x1800a22fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2300  lea     rcx, [rdi+r14]
0x1800a2304  cmp     rcx, rax
0x1800a2307  jb      short loc_1800A231E
0x1800a2309  mov     rax, [rsi]
0x1800a230c  mov     rcx, rsi
0x1800a230f  mov     rax, [rax+20h]
0x1800a2313  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2318  mov     rdi, rax
0x1800a231b  sub     rdi, r14
0x1800a231e  lea     rcx, [rbp+240h+SystemTime]; lpSystemTime
0x1800a2325  call    cs:__imp_GetSystemTime
0x1800a232b  lea     rdx, [rbp+240h+var_288]
0x1800a232f  lea     rcx, [rbp+240h+SystemTime]
0x1800a2336  call    ?GetInternetTime@CTpAzureStorageTransport@@CAJAEBU_SYSTEMTIME@@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CTpAzureStorageTransport::GetInternetTime(_SYSTEMTIME const &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x1800a233b  test    eax, eax
0x1800a233d  js      loc_1800A2504
0x1800a2343  mov     r8, rdi
0x1800a2346  lea     rdx, aContentLengthL; "Content-Length: %llu\n"
0x1800a234d  lea     rcx, [rsp+340h+var_308]
0x1800a2352  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x1800a2357  lea     rdx, aXMsVersion2017; "x-ms-version: 2017-04-17\n"
0x1800a235e  lea     rcx, [rsp+340h+var_308]
0x1800a2363  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *)
0x1800a2368  lea     rdx, aXMsDate; "x-ms-date: "
0x1800a236f  lea     rcx, [rsp+340h+var_308]
0x1800a2374  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *)
0x1800a2379  mov     r8, [rbp+240h+var_280]
0x1800a237d  mov     rdx, [rbp+240h+var_288]
0x1800a2381  sub     r8, rdx
0x1800a2384  sar     r8, 1
0x1800a2387  lea     rcx, [rsp+340h+var_308]
0x1800a238c  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x1800a2391  mov     edx, 0Ah
0x1800a2396  lea     rcx, [rsp+340h+var_308]
0x1800a239b  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x1800a23a0  mov     ecx, [r15]
0x1800a23a3  inc     ecx
0x1800a23a5  lea     r8, [rbp+240h+var_208]
0x1800a23a9  mov     edx, 1
0x1800a23ae  call    ?GetBlockId@CTpAzureStorageTransport@@CAJKHPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CTpAzureStorageTransport::GetBlockId(ulong,int,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x1800a23b3  mov     ebx, eax
0x1800a23b5  test    eax, eax
0x1800a23b7  js      loc_1800A24DC
0x1800a23bd  mov     r9, [rbp+240h+var_208]
0x1800a23c1  mov     r8, [rbp+240h+var_290]
0x1800a23c5  lea     rdx, aLsCompBlockBlo; "%ls&comp=block&blockid=%ls"
0x1800a23cc  lea     rcx, [rbp+240h+var_1E8]
0x1800a23d0  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x1800a23d5  mov     qword ptr [rsp+340h+var_2D0+8], rdi
0x1800a23da  mov     byte ptr [rbp+240h+var_2C0], 0
0x1800a23de  mov     rax, [rsp+340h+var_2E8]
0x1800a23e3  mov     [rbp+240h+var_1C0], rax
0x1800a23ea  mov     rax, [rbp+240h+var_1E8]
0x1800a23ee  mov     [rbp+240h+var_1B8], rax
0x1800a23f5  mov     [rbp+240h+var_1B0], rsi
0x1800a23fc  xor     eax, eax
0x1800a23fe  mov     [rbp+240h+var_1A8], ax
0x1800a2405  lea     rax, [rsp+340h+var_2D0]
0x1800a240a  mov     [rbp+240h+var_1A0], rax
0x1800a2411  mov     [rbp+240h+var_198], 1
0x1800a241b  mov     al, r13b
0x1800a241e  not     al
0x1800a2420  movzx   ecx, al
0x1800a2423  and     ecx, 1
0x1800a2426  mov     [rbp+240h+var_190], ecx
0x1800a242c  mov     [rbp+240h+var_178], r13d
0x1800a2433  mov     rax, [rsp+340h+var_308]
0x1800a2438  mov     [rbp+240h+var_170], rax
0x1800a243f  mov     [rbp+240h+var_188], r14
0x1800a2446  mov     [rbp+240h+var_180], rdi
0x1800a244d  mov     rax, [rsp+340h+var_2E0]
0x1800a2452  mov     [rbp+240h+var_158], rax
0x1800a2459  mov     rax, [rsp+340h+var_2D8]
0x1800a245e  mov     [rbp+240h+var_168], rax
0x1800a2465  call    IsXerGetMachineIdPresent
0x1800a246a  lea     rcx, [rbp+240h+var_1C0]; struct _WER_TP_UPLOAD_STATE *
0x1800a2471  test    al, al
0x1800a2473  jnz     short loc_1800A248C
0x1800a2475  xor     edx, edx; struct WINHTTP_TIMEOUTS *
0x1800a2477  call    ?TpUpload@@YAJPEAU_WER_TP_UPLOAD_STATE@@PEAUWINHTTP_TIMEOUTS@@@Z; TpUpload(_WER_TP_UPLOAD_STATE *,WINHTTP_TIMEOUTS *)
0x1800a247c  mov     ebx, eax
0x1800a247e  lea     rcx, [rbp+240h+var_1C0]; struct _WER_TP_UPLOAD_STATE *
0x1800a2485  call    ?TpCompleteUpload@@YAXPEAU_WER_TP_UPLOAD_STATE@@@Z; TpCompleteUpload(_WER_TP_UPLOAD_STATE *)
0x1800a248a  jmp     short loc_1800A24A1
0x1800a248c  call    cs:__imp_XerTpUpload
0x1800a2492  mov     ebx, eax
0x1800a2494  lea     rcx, [rbp+240h+var_1C0]
0x1800a249b  call    cs:__imp_XerTpCompleteUpload
0x1800a24a1  test    ebx, ebx
0x1800a24a3  js      short loc_1800A24B4
0x1800a24a5  inc     dword ptr [r15]
0x1800a24a8  add     [r12], rdi
0x1800a24ac  add     r14, rdi
0x1800a24af  jmp     loc_1800A22D5
0x1800a24b4  lea     rax, WPP_GLOBAL_Control
0x1800a24bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a24c2  cmp     rcx, rax
0x1800a24c5  jz      loc_1800A27E7
0x1800a24cb  test    byte ptr [rcx+1Ch], 4
0x1800a24cf  jz      loc_1800A27E7
0x1800a24d5  mov     edx, 13h
0x1800a24da  jmp     short loc_1800A2532
0x1800a24dc  lea     rax, WPP_GLOBAL_Control
0x1800a24e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a24ea  cmp     rcx, rax
0x1800a24ed  jz      loc_1800A27E7
0x1800a24f3  test    byte ptr [rcx+1Ch], 1
0x1800a24f7  jz      loc_1800A27E7
0x1800a24fd  mov     edx, 12h
0x1800a2502  jmp     short loc_1800A2532
0x1800a2504  call    cs:__imp_GetLastError
0x1800a250a  mov     ebx, eax
0x1800a250c  lea     rax, WPP_GLOBAL_Control
0x1800a2513  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a251a  cmp     rcx, rax
0x1800a251d  jz      loc_1800A27E7
0x1800a2523  test    byte ptr [rcx+1Ch], 1
0x1800a2527  jz      loc_1800A27E7
0x1800a252d  mov     edx, 11h
0x1800a2532  mov     r9d, ebx
0x1800a2535  lea     r8, WPP_2630288230103b96da97e4a7a3753ae6_Traceguids
0x1800a253c  mov     rcx, [rcx+10h]
0x1800a2540  call    WPP_SF_d
0x1800a2545  jmp     loc_1800A27E7
0x1800a254a  lea     rdx, [rbp+240h+var_248]
0x1800a254e  mov     ecx, [r15]
0x1800a2551  call    ?GetPutBlockListXml@CTpAzureStorageTransport@@CAJKPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CTpAzureStorageTransport::GetPutBlockListXml(ulong,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x1800a2556  mov     ebx, eax
0x1800a2558  test    eax, eax
0x1800a255a  jns     short loc_1800A2584
0x1800a255c  lea     rax, WPP_GLOBAL_Control
0x1800a2563  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a256a  cmp     rcx, rax
0x1800a256d  jz      loc_1800A27E7
0x1800a2573  test    byte ptr [rcx+1Ch], 1
0x1800a2577  jz      loc_1800A27E7
0x1800a257d  mov     edx, 14h
0x1800a2582  jmp     short loc_1800A2532
0x1800a2584  mov     rdx, [rbp+240h+var_248]
0x1800a2588  mov     r8, [rbp+240h+var_240]
0x1800a258c  sub     r8, rdx
0x1800a258f  sar     r8, 1
0x1800a2592  lea     rcx, [rbp+240h+var_268]
0x1800a2596  call    ??$_AppendWideImpl@V?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@_W@tlx@@YAJAEAV?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@PEB_W_KII@Z; tlx::_AppendWideImpl<utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>,wchar_t>(utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>> &,wchar_t const *,unsigned __int64,uint,uint)
0x1800a259b  mov     ebx, eax
0x1800a259d  test    eax, eax
0x1800a259f  jns     short loc_1800A25CC
0x1800a25a1  lea     rax, WPP_GLOBAL_Control
0x1800a25a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a25af  cmp     rcx, rax
0x1800a25b2  jz      loc_1800A27E7
0x1800a25b8  test    byte ptr [rcx+1Ch], 1
0x1800a25bc  jz      loc_1800A27E7
0x1800a25c2  mov     edx, 15h
0x1800a25c7  jmp     loc_1800A2532
0x1800a25cc  lea     rcx, [rbp+240h+var_2B8]; this
0x1800a25d0  call    ?OpenForReadWrite@CMemoryByteStream@@QEAAXXZ; CMemoryByteStream::OpenForReadWrite(void)
0x1800a25d5  mov     rdx, [rbp+240h+var_268]; void *
0x1800a25d9  mov     r8d, [rbp+240h+var_260]
0x1800a25dd  sub     r8d, edx; unsigned int
0x1800a25e0  mov     [rsp+340h+var_320], 0; void *
0x1800a25e9  lea     r9, [rsp+340h+var_310]; unsigned int *
0x1800a25ee  lea     rcx, [rbp+240h+var_2B8]; this
0x1800a25f2  call    ?Write@CMemoryByteStream@@UEAAJPEAXKPEAK0@Z; CMemoryByteStream::Write(void *,ulong,ulong *,void *)
0x1800a25f7  mov     ebx, eax
0x1800a25f9  test    eax, eax
0x1800a25fb  jns     short loc_1800A2628
0x1800a25fd  lea     rax, WPP_GLOBAL_Control
0x1800a2604  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a260b  cmp     rcx, rax
0x1800a260e  jz      loc_1800A27E7
0x1800a2614  test    byte ptr [rcx+1Ch], 1
0x1800a2618  jz      loc_1800A27E7
0x1800a261e  mov     edx, 16h
0x1800a2623  jmp     loc_1800A2532
0x1800a2628  lea     rcx, [rbp+240h+SystemTime]; lpSystemTime
0x1800a262f  call    cs:__imp_GetSystemTime
0x1800a2635  lea     rdx, [rbp+240h+var_288]
0x1800a2639  lea     rcx, [rbp+240h+SystemTime]
0x1800a2640  call    ?GetInternetTime@CTpAzureStorageTransport@@CAJAEBU_SYSTEMTIME@@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CTpAzureStorageTransport::GetInternetTime(_SYSTEMTIME const &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x1800a2645  test    eax, eax
0x1800a2647  jns     short loc_1800A267C
0x1800a2649  call    cs:__imp_GetLastError
0x1800a264f  mov     ebx, eax
0x1800a2651  lea     rax, WPP_GLOBAL_Control
0x1800a2658  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a265f  cmp     rcx, rax
0x1800a2662  jz      loc_1800A27E7
0x1800a2668  test    byte ptr [rcx+1Ch], 1
0x1800a266c  jz      loc_1800A27E7
0x1800a2672  mov     edx, 17h
0x1800a2677  jmp     loc_1800A2532
0x1800a267c  mov     eax, dword ptr [rbp+240h+var_2A0]
0x1800a267f  mov     qword ptr [rsp+340h+var_2D0+8], rax
0x1800a2684  mov     byte ptr [rbp+240h+var_2C0], 0
0x1800a2688  mov     rcx, [rsp+340h+var_308]
0x1800a268d  mov     [rsp+340h+var_300], rcx
0x1800a2692  xor     eax, eax
0x1800a2694  mov     [rcx], ax
0x1800a2697  mov     r8d, dword ptr [rbp+240h+var_2A0]
0x1800a269b  lea     rdx, aContentLengthL; "Content-Length: %llu\n"
0x1800a26a2  lea     rcx, [rsp+340h+var_308]
0x1800a26a7  call    ??$append_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::append_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x1800a26ac  lea     rdx, aXMsVersion2017; "x-ms-version: 2017-04-17\n"
0x1800a26b3  lea     rcx, [rsp+340h+var_308]
0x1800a26b8  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *)
0x1800a26bd  lea     rdx, aXMsDate; "x-ms-date: "
0x1800a26c4  lea     rcx, [rsp+340h+var_308]
0x1800a26c9  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *)
0x1800a26ce  mov     r8, [rbp+240h+var_280]
0x1800a26d2  mov     rdx, [rbp+240h+var_288]
0x1800a26d6  sub     r8, rdx
0x1800a26d9  sar     r8, 1
0x1800a26dc  lea     rcx, [rsp+340h+var_308]
0x1800a26e1  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
  ... truncated ...
```
