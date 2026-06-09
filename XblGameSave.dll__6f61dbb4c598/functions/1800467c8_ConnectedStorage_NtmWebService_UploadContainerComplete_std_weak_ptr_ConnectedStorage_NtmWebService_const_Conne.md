# ConnectedStorage::NtmWebService::UploadContainerComplete(std::weak_ptr<ConnectedStorage::NtmWebService const>,ConnectedStorage::ContextDesc,ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &,_FILETIME const &,ConnectedStorage::SimpleHStringWrapper const &,std::function<void (ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &)>,ConnectedStorage::Timer,ulong,std::shared_ptr<ConnectedStorage::NtmCancelCallback>,_NTM_TRANSFER_STATUS const &,uint,long)

- ea: `0x1800467c8`
- end: `0x180046be6`
- name: `?UploadContainerComplete@NtmWebService@ConnectedStorage@@CAXV?$weak_ptr@$$CBVNtmWebService@ConnectedStorage@@@std@@VContextDesc@2@AEBVSimpleHStringWrapper@2@2AEBU_FILETIME@@2V?$function@$$A6AXW4Status@WebService@ConnectedStorage@@AEBVSimpleHStringWrapper@3@@Z@4@VTimer@2@KV?$shared_ptr@VNtmCancelCallback@ConnectedStorage@@@4@AEBU_NTM_TRANSFER_STATUS@@IJ@Z`
- size: `1054`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003fd70`

## callees

- `0x180003c70`
- `0x18000c218`
- `0x180010e90`
- `0x180010f28`
- `0x1800113bc`
- `0x180011c0c`
- `0x1800125ec`
- `0x180012ed8`
- `0x1800136a8`
- `0x180014fdc`
- `0x1800190f0`
- `0x180019128`
- `0x18001c090`
- `0x18001c8f0`
- `0x18001ec34`
- `0x18002d880`
- `0x18004319c`
- `0x180043758`
- `0x1800467c8`
- `0x180046bec`
- `0x180047324`
- `0x18007cd60`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180046a60`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180046aa6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180046b49`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180046b67`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180046a60`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180046aa6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180046b49`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180046b67`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180046876`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180046885`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180046894`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180046876`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180046885`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180046894`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
void __fastcall ConnectedStorage::NtmWebService::UploadContainerComplete(
        __int64 a1,
        ConnectedStorage::ContextDesc *a2,
        char *a3,
        ConnectedStorage::SimpleHStringWrapper *a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        char a8,
        int a9,
        _QWORD *a10,
        HSTRING a11,
        unsigned int a12,
        unsigned int a13)
{
  HSTRING *v14; // r15
  __int64 v15; // r14
  _QWORD *v16; // r13
  unsigned int TimeMs; // esi
  const unsigned __int16 *StringRawBuffer; // rdi
  const unsigned __int16 *v19; // rbx
  ConnectedStorage *v20; // rax
  signed int v21; // r12d
  __int64 v22; // rsi
  unsigned int v23; // eax
  char v24; // di
  ConnectedStorage::NtmCancelCallback **Quota; // r12
  HSTRING *v26; // rax
  __int64 v27; // rdi
  HSTRING v28; // rdi
  std::_Ref_count_base *v29; // rcx
  std::_Ref_count_base *v30; // rcx
  unsigned int v31; // [rsp+38h] [rbp-1C0h]
  HSTRING string; // [rsp+50h] [rbp-1A8h] BYREF
  HSTRING newString; // [rsp+58h] [rbp-1A0h] BYREF
  __int64 v34; // [rsp+60h] [rbp-198h]
  HSTRING v35; // [rsp+68h] [rbp-190h] BYREF
  __int64 v36; // [rsp+70h] [rbp-188h]
  __int64 v37; // [rsp+78h] [rbp-180h]
  ConnectedStorage::ContextDesc *v38; // [rsp+80h] [rbp-178h]
  _QWORD *v39; // [rsp+88h] [rbp-170h]
  __int64 v40; // [rsp+90h] [rbp-168h]
  __int64 v41; // [rsp+98h] [rbp-160h]
  ConnectedStorage::SimpleHStringWrapper *v42; // [rsp+A0h] [rbp-158h]
  char *v43; // [rsp+A8h] [rbp-150h]
  __int64 v44; // [rsp+B0h] [rbp-148h] BYREF
  std::_Ref_count_base *v45; // [rsp+B8h] [rbp-140h]
  _QWORD v46[2]; // [rsp+C8h] [rbp-130h] BYREF
  HSTRING v47; // [rsp+D8h] [rbp-120h] BYREF
  _BYTE v48[64]; // [rsp+108h] [rbp-F0h] BYREF
  _BYTE v49[40]; // [rsp+148h] [rbp-B0h] BYREF
  _DWORD v50[16]; // [rsp+170h] [rbp-88h] BYREF

  v42 = a4;
  v43 = a3;
  v14 = (HSTRING *)a2;
  v34 = a1;
  v37 = a1;
  v38 = a2;
  v41 = a5;
  v40 = a6;
  v15 = a7;
  v36 = a7;
  v16 = a10;
  v39 = a10;
  v35 = a11;
  LODWORD(newString) = a11[22];
  TimeMs = ConnectedStorage::Timer::GetTimeMs((ConnectedStorage::Timer *)&a8);
  StringRawBuffer = WindowsGetStringRawBuffer(*(HSTRING *)a3, 0);
  v19 = WindowsGetStringRawBuffer(v14[2], 0);
  v20 = (ConnectedStorage *)WindowsGetStringRawBuffer(v14[3], 0);
  v21 = a13;
  ConnectedStorage::EventWriteWebUploadContainer(
    v20,
    v19,
    StringRawBuffer,
    (const unsigned __int16 *const)(unsigned int)newString,
    TimeMs,
    a13,
    a12,
    v31);
  std::weak_ptr<ConnectedStorage::UploadingContext>::lock(v34, &v44);
  v22 = v44;
  if ( v44 )
  {
    v23 = ConnectedStorage::Timer::GetTimeMs((ConnectedStorage::Timer *)&a8);
    ConnectedStorage::NtmWebService::WriteTelemetry(v22, 2, v14 + 3, v14 + 2, (unsigned int)newString, 0, v23, a12);
  }
  if ( v21 >= 0 )
  {
    string = 0;
    newString = 0;
    v28 = v35;
    if ( *((_QWORD *)v35 + 9) )
    {
      ConnectedStorage::TaskMem<unsigned short>::Release(&string);
      if ( (int)GetHttpHeaderFromRawHttpHeaders(
                  *((const unsigned __int16 **)v28 + 9),
                  L"ETag",
                  (unsigned __int16 **)&string) >= 0 )
      {
        ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&v35, (PCNZWCH)string);
        ConnectedStorage::SimpleHStringWrapper::operator=(&newString);
        WindowsDeleteString(v35);
      }
    }
    std::_Func_class<void,enum ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &>::operator()(
      a7,
      10,
      &newString);
    WindowsDeleteString(newString);
    newString = 0;
    ConnectedStorage::TaskMem<unsigned short>::Release(&string);
    goto LABEL_22;
  }
  if ( !v22 || v21 != -2145844847 )
  {
    if ( v21 == -2145844839 )
    {
      string = 0;
      std::_Func_class<void,enum ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &>::operator()(
        a7,
        6,
        &string);
    }
    else
    {
      if ( v21 != -2145844848 )
        goto LABEL_17;
      string = 0;
      std::_Func_class<void,enum ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &>::operator()(
        a7,
        16,
        &string);
    }
LABEL_14:
    WindowsDeleteString(string);
    goto LABEL_22;
  }
  v24 = a9 - 1;
  if ( a9 == 1 )
  {
LABEL_17:
    string = 0;
    std::_Func_class<void,enum ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &>::operator()(
      a7,
      1,
      &string);
    goto LABEL_14;
  }
  try
  {
    ConnectedStorage::MakeUrl(v49, v14);
    ConnectedStorage::NtmWebService::InvalidateToken(v22, v49, v14);
    v35 = (HSTRING)v46;
    Quota = (ConnectedStorage::NtmCancelCallback **)std::shared_ptr<ConnectedStorage::GetQuotaData>::shared_ptr<ConnectedStorage::GetQuotaData>(
                                                      v46,
                                                      v16);
    newString = (HSTRING)v48;
    string = (HSTRING)std::function<void (enum ConnectedStorage::WebService::Status,ConnectedStorage::Atom)>::function<void (enum ConnectedStorage::WebService::Status,ConnectedStorage::Atom)>(
                        (__int64)v48,
                        a7);
    v26 = ConnectedStorage::ContextDesc::ContextDesc(&v47, (const struct ConnectedStorage::ContextDesc *)v14);
    ConnectedStorage::NtmWebService::UploadContainerImpl(v22, v26, v43, v42, v41, v40, (__int64)string, v24, Quota);
    std::wstring::_Tidy_deallocate(v49);
  }
  catch ( ConnectedStorage::ComError v50 )
  {
    LODWORD(newString) = v50[6];
    ConnectedStorage::ComError::~ComError((ConnectedStorage::ComError *)v50);
    if ( (int)newString < 0 )
    {
LABEL_10:
      string = 0;
      v15 = v36;
      std::_Func_class<void,enum ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &>::operator()(
        v36,
        1,
        &string);
      WindowsDeleteString(string);
    }
    else
    {
      v15 = v36;
    }
    v14 = (HSTRING *)v38;
    v27 = v37;
    v16 = v39;
LABEL_23:
    if ( v45 )
      std::_Ref_count_base::_Decref(v45);
    v29 = *(std::_Ref_count_base **)(v27 + 8);
    if ( v29 )
      std::_Ref_count_base::_Decwref(v29);
    ConnectedStorage::ContextDesc::~ContextDesc(v14);
    std::function<long (void)>::~function<long (void)>(v15);
    v30 = (std::_Ref_count_base *)v16[1];
    if ( v30 )
      std::_Ref_count_base::_Decref(v30);
  }
  catch ( std::bad_alloc )
  {
    goto LABEL_10;
  }
  catch ( ... )
  {
    goto LABEL_10;
  }
LABEL_22:
  v27 = v34;
  goto LABEL_23;
}

```

## disassembly

```asm
0x1800467c8  mov     r11, rsp
0x1800467cb  push    rbx
0x1800467cc  push    rsi
0x1800467cd  push    rdi
0x1800467ce  push    r12
0x1800467d0  push    r13
0x1800467d2  push    r14
0x1800467d4  push    r15
0x1800467d6  sub     rsp, 1C0h
0x1800467dd  mov     rax, cs:__security_cookie
0x1800467e4  xor     rax, rsp
0x1800467e7  mov     [rsp+1F8h+var_48], rax
0x1800467ef  mov     [rsp+1F8h+var_158], r9
0x1800467f7  mov     rbx, r8
0x1800467fa  mov     [rsp+1F8h+var_150], rbx
0x180046802  mov     r15, rdx
0x180046805  mov     [rsp+1F8h+var_198], rcx
0x18004680a  mov     [rsp+1F8h+var_180], rcx
0x18004680f  mov     [r11-178h], rdx
0x180046816  mov     rax, [rsp+1F8h+arg_20]
0x18004681e  mov     [rsp+1F8h+var_160], rax
0x180046826  mov     rax, [rsp+1F8h+arg_28]
0x18004682e  mov     [rsp+1F8h+var_168], rax
0x180046836  mov     r14, [rsp+1F8h+arg_30]
0x18004683e  mov     [rsp+1F8h+var_188], r14
0x180046843  mov     r13, [rsp+1F8h+arg_48]
0x18004684b  mov     [r11-170h], r13
0x180046852  mov     rax, [rsp+1F8h+arg_50]
0x18004685a  mov     [rsp+1F8h+var_190], rax
0x18004685f  mov     eax, [rax+58h]
0x180046862  mov     dword ptr [rsp+1F8h+newString], eax
0x180046866  lea     rcx, [r11+40h]; this
0x18004686a  call    ?GetTimeMs@Timer@ConnectedStorage@@QEBAIXZ; ConnectedStorage::Timer::GetTimeMs(void)
0x18004686f  mov     esi, eax
0x180046871  xor     edx, edx; length
0x180046873  mov     rcx, [rbx]; string
0x180046876  call    cs:__imp_WindowsGetStringRawBuffer
0x18004687c  mov     rdi, rax
0x18004687f  xor     edx, edx; length
0x180046881  mov     rcx, [r15+10h]; string
0x180046885  call    cs:__imp_WindowsGetStringRawBuffer
0x18004688b  mov     rbx, rax
0x18004688e  xor     edx, edx; length
0x180046890  mov     rcx, [r15+18h]; string
0x180046894  call    cs:__imp_WindowsGetStringRawBuffer
0x18004689a  mov     ecx, [rsp+1F8h+arg_58]
0x1800468a1  mov     [rsp+1F8h+var_1C8], ecx; unsigned int
0x1800468a5  mov     r12d, [rsp+1F8h+arg_60]
0x1800468ad  mov     [rsp+1F8h+var_1D0], r12d; unsigned int
0x1800468b2  mov     [rsp+1F8h+var_1D8], esi; unsigned int
0x1800468b6  mov     r9d, dword ptr [rsp+1F8h+newString]; unsigned __int16 *
0x1800468bb  mov     r8, rdi; unsigned __int16 *
0x1800468be  mov     rdx, rbx; unsigned __int16 *
0x1800468c1  mov     rcx, rax; this
0x1800468c4  call    ?EventWriteWebUploadContainer@ConnectedStorage@@YAXQEBG00IIII@Z; ConnectedStorage::EventWriteWebUploadContainer(ushort const * const,ushort const * const,ushort const * const,uint,uint,uint,uint)
0x1800468c9  lea     rdx, [rsp+1F8h+var_148]
0x1800468d1  mov     rcx, [rsp+1F8h+var_198]
0x1800468d6  call    ?lock@?$weak_ptr@VUploadingContext@ConnectedStorage@@@std@@QEBA?AV?$shared_ptr@VUploadingContext@ConnectedStorage@@@2@XZ; std::weak_ptr<ConnectedStorage::UploadingContext>::lock(void)
0x1800468db  nop
0x1800468dc  mov     rsi, [rsp+1F8h+var_148]
0x1800468e4  xor     ebx, ebx
0x1800468e6  test    rsi, rsi
0x1800468e9  jz      short loc_18004692B
0x1800468eb  lea     rcx, [rsp+1F8h+arg_38]; this
0x1800468f3  call    ?GetTimeMs@Timer@ConnectedStorage@@QEBAIXZ; ConnectedStorage::Timer::GetTimeMs(void)
0x1800468f8  mov     eax, eax
0x1800468fa  mov     ecx, dword ptr [rsp+1F8h+newString]
0x1800468fe  mov     edx, [rsp+1F8h+arg_58]
0x180046905  mov     [rsp+1F8h+var_1C0], edx
0x180046909  mov     qword ptr [rsp+1F8h+var_1C8], rax
0x18004690e  mov     qword ptr [rsp+1F8h+var_1D0], rbx
0x180046913  mov     qword ptr [rsp+1F8h+var_1D8], rcx
0x180046918  lea     r9, [r15+10h]
0x18004691c  lea     r8, [r15+18h]
0x180046920  lea     edx, [rbx+2]
0x180046923  mov     rcx, rsi
0x180046926  call    ?WriteTelemetry@NtmWebService@ConnectedStorage@@AEBAXW4TelemetryType@WebService@2@AEBVSimpleHStringWrapper@2@1_K22I@Z; ConnectedStorage::NtmWebService::WriteTelemetry(ConnectedStorage::WebService::TelemetryType,ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &,unsigned __int64,unsigned __int64,unsigned __int64,uint)
0x18004692b  test    r12d, r12d
0x18004692e  jns     loc_180046AEE
0x180046934  test    rsi, rsi
0x180046937  jz      loc_180046A80
0x18004693d  cmp     r12d, 80190191h
0x180046944  jnz     loc_180046A80
0x18004694a  mov     edi, [rsp+1F8h+arg_40]
0x180046951  add     edi, 0FFFFFFFFh
0x180046954  jz      loc_180046AD4
0x18004695a  mov     rdx, r15
0x18004695d  lea     rcx, [rsp+1F8h+var_B0]
0x180046965  call    ?MakeUrl@ConnectedStorage@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBVContextDesc@1@@Z; ConnectedStorage::MakeUrl(ConnectedStorage::ContextDesc const &)
0x18004696a  nop
0x18004696b  mov     r8, r15
0x18004696e  lea     rdx, [rsp+1F8h+var_B0]
0x180046976  mov     rcx, rsi
0x180046979  call    ?InvalidateToken@NtmWebService@ConnectedStorage@@AEBAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBVContextDesc@2@@Z; ConnectedStorage::NtmWebService::InvalidateToken(std::wstring const &,ConnectedStorage::ContextDesc const &)
0x18004697e  lea     rax, [rsp+1F8h+var_130]
0x180046986  mov     [rsp+1F8h+var_190], rax
0x18004698b  mov     rdx, r13
0x18004698e  lea     rcx, [rsp+1F8h+var_130]
0x180046996  call    ??0?$shared_ptr@UGetQuotaData@ConnectedStorage@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<ConnectedStorage::GetQuotaData>::shared_ptr<ConnectedStorage::GetQuotaData>(std::shared_ptr<ConnectedStorage::GetQuotaData> const &)
0x18004699b  mov     r12, rax
0x18004699e  lea     rax, [rsp+1F8h+var_F0]
0x1800469a6  mov     [rsp+1F8h+newString], rax
0x1800469ab  mov     rdx, r14
0x1800469ae  lea     rcx, [rsp+1F8h+var_F0]
0x1800469b6  call    ??0?$function@$$A6AXW4Status@WebService@ConnectedStorage@@VAtom@3@@Z@std@@QEAA@AEBV01@@Z; std::function<void (ConnectedStorage::WebService::Status,ConnectedStorage::Atom)>::function<void (ConnectedStorage::WebService::Status,ConnectedStorage::Atom)>(std::function<void (ConnectedStorage::WebService::Status,ConnectedStorage::Atom)> const &)
0x1800469bb  mov     [rsp+1F8h+string], rax
0x1800469c0  mov     rdx, r15; struct ConnectedStorage::ContextDesc *
0x1800469c3  lea     rcx, [rsp+1F8h+var_120]; this
0x1800469cb  call    ??0ContextDesc@ConnectedStorage@@QEAA@AEBV01@@Z; ConnectedStorage::ContextDesc::ContextDesc(ConnectedStorage::ContextDesc const &)
0x1800469d0  nop
0x1800469d1  mov     [rsp+1F8h+var_1B8], r12
0x1800469d6  mov     [rsp+1F8h+var_1C0], edi
0x1800469da  mov     rcx, [rsp+1F8h+string]
0x1800469df  mov     qword ptr [rsp+1F8h+var_1C8], rcx
0x1800469e4  mov     rcx, [rsp+1F8h+var_168]
0x1800469ec  mov     qword ptr [rsp+1F8h+var_1D0], rcx
0x1800469f1  mov     rcx, [rsp+1F8h+var_160]
0x1800469f9  mov     qword ptr [rsp+1F8h+var_1D8], rcx
0x1800469fe  mov     r9, [rsp+1F8h+var_158]
0x180046a06  mov     r8, [rsp+1F8h+var_150]
0x180046a0e  mov     rdx, rax
0x180046a11  mov     rcx, rsi
0x180046a14  call    ?UploadContainerImpl@NtmWebService@ConnectedStorage@@AEBAXVContextDesc@2@AEBVSimpleHStringWrapper@2@1AEBU_FILETIME@@1V?$function@$$A6AXW4Status@WebService@ConnectedStorage@@AEBVSimpleHStringWrapper@3@@Z@std@@KV?$shared_ptr@VNtmCancelCallback@ConnectedStorage@@@7@@Z; ConnectedStorage::NtmWebService::UploadContainerImpl(ConnectedStorage::ContextDesc,ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &,_FILETIME const &,ConnectedStorage::SimpleHStringWrapper const &,std::function<void (ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &)>,ulong,std::shared_ptr<ConnectedStorage::NtmCancelCallback>)
0x180046a19  nop
0x180046a1a  lea     rcx, [rsp+1F8h+var_B0]
0x180046a22  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180046a27  nop
0x180046a28  jmp     loc_180046B7C
0x180046a2d  xor     ebx, ebx
0x180046a2f  cmp     dword ptr [rsp+1F8h+newString], ebx
0x180046a33  jl      short loc_180046A3E
0x180046a35  mov     r14, [rsp+1F8h+var_188]
0x180046a3a  jmp     short loc_180046A66
0x180046a3c  xor     ebx, ebx
0x180046a3e  mov     [rsp+1F8h+string], rbx
0x180046a43  lea     r8, [rsp+1F8h+string]
0x180046a48  mov     edx, 1
0x180046a4d  mov     r14, [rsp+1F8h+var_188]
0x180046a52  mov     rcx, r14
0x180046a55  call    ??R?$_Func_class@XW4Status@WebService@ConnectedStorage@@AEBVSimpleHStringWrapper@3@@std@@QEBAXW4Status@WebService@ConnectedStorage@@AEBVSimpleHStringWrapper@4@@Z; std::_Func_class<void,ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &>::operator()(ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &)
0x180046a5a  nop
0x180046a5b  mov     rcx, [rsp+1F8h+string]; string
0x180046a60  call    cs:__imp_WindowsDeleteString
0x180046a66  mov     r15, [rsp+1F8h+var_178]
0x180046a6e  mov     rdi, [rsp+1F8h+var_180]
0x180046a73  mov     r13, [rsp+1F8h+var_170]
0x180046a7b  jmp     loc_180046B81
0x180046a80  cmp     r12d, 80190199h
0x180046a87  jnz     short loc_180046AB1
0x180046a89  mov     [rsp+1F8h+string], rbx
0x180046a8e  lea     r8, [rsp+1F8h+string]
0x180046a93  mov     edx, 6
0x180046a98  mov     rcx, r14
0x180046a9b  call    ??R?$_Func_class@XW4Status@WebService@ConnectedStorage@@AEBVSimpleHStringWrapper@3@@std@@QEBAXW4Status@WebService@ConnectedStorage@@AEBVSimpleHStringWrapper@4@@Z; std::_Func_class<void,ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &>::operator()(ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &)
0x180046aa0  nop
0x180046aa1  mov     rcx, [rsp+1F8h+string]; string
0x180046aa6  call    cs:__imp_WindowsDeleteString
0x180046aac  jmp     loc_180046B7C
0x180046ab1  cmp     r12d, 80190190h
0x180046ab8  jnz     short loc_180046AD4
0x180046aba  mov     [rsp+1F8h+string], rbx
0x180046abf  lea     r8, [rsp+1F8h+string]
0x180046ac4  mov     edx, 10h
0x180046ac9  mov     rcx, r14
0x180046acc  call    ??R?$_Func_class@XW4Status@WebService@ConnectedStorage@@AEBVSimpleHStringWrapper@3@@std@@QEBAXW4Status@WebService@ConnectedStorage@@AEBVSimpleHStringWrapper@4@@Z; std::_Func_class<void,ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &>::operator()(ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &)
0x180046ad1  nop
0x180046ad2  jmp     short loc_180046AA1
0x180046ad4  mov     [rsp+1F8h+string], rbx
0x180046ad9  lea     r8, [rsp+1F8h+string]
0x180046ade  mov     edx, 1
0x180046ae3  mov     rcx, r14
0x180046ae6  call    ??R?$_Func_class@XW4Status@WebService@ConnectedStorage@@AEBVSimpleHStringWrapper@3@@std@@QEBAXW4Status@WebService@ConnectedStorage@@AEBVSimpleHStringWrapper@4@@Z; std::_Func_class<void,ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &>::operator()(ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &)
0x180046aeb  nop
0x180046aec  jmp     short loc_180046AA1
0x180046aee  mov     [rsp+1F8h+string], rbx
0x180046af3  mov     [rsp+1F8h+newString], rbx
0x180046af8  mov     rdi, [rsp+1F8h+var_190]
0x180046afd  cmp     [rdi+48h], rbx
0x180046b01  jz      short loc_180046B4F
0x180046b03  lea     rcx, [rsp+1F8h+string]
0x180046b08  call    ?Release@?$TaskMem@G@ConnectedStorage@@QEAAXXZ; ConnectedStorage::TaskMem<ushort>::Release(void)
0x180046b0d  lea     r8, [rsp+1F8h+string]; unsigned __int16 **
0x180046b12  lea     rdx, aEtag_0; "ETag"
0x180046b19  mov     rcx, [rdi+48h]; unsigned __int16 *
0x180046b1d  call    ?GetHttpHeaderFromRawHttpHeaders@@YAJPEBG0PEAPEAG@Z; GetHttpHeaderFromRawHttpHeaders(ushort const *,ushort const *,ushort * *)
0x180046b22  test    eax, eax
0x180046b24  js      short loc_180046B4F
0x180046b26  mov     rdx, [rsp+1F8h+string]; sourceString
0x180046b2b  lea     rcx, [rsp+1F8h+var_190]; string
0x180046b30  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@PEBG@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(ushort const *)
0x180046b35  nop
0x180046b36  mov     rdx, rax
0x180046b39  lea     rcx, [rsp+1F8h+newString]; newString
0x180046b3e  call    ??4SimpleHStringWrapper@ConnectedStorage@@QEAAAEAV01@AEBV01@@Z; ConnectedStorage::SimpleHStringWrapper::operator=(ConnectedStorage::SimpleHStringWrapper const &)
0x180046b43  nop
0x180046b44  mov     rcx, [rsp+1F8h+var_190]; string
0x180046b49  call    cs:__imp_WindowsDeleteString
0x180046b4f  lea     r8, [rsp+1F8h+newString]
0x180046b54  mov     edx, 0Ah
0x180046b59  mov     rcx, r14
0x180046b5c  call    ??R?$_Func_class@XW4Status@WebService@ConnectedStorage@@AEBVSimpleHStringWrapper@3@@std@@QEBAXW4Status@WebService@ConnectedStorage@@AEBVSimpleHStringWrapper@4@@Z; std::_Func_class<void,ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &>::operator()(ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &)
0x180046b61  nop
0x180046b62  mov     rcx, [rsp+1F8h+newString]; string
0x180046b67  call    cs:__imp_WindowsDeleteString
0x180046b6d  mov     [rsp+1F8h+newString], rbx
0x180046b72  lea     rcx, [rsp+1F8h+string]
0x180046b77  call    ?Release@?$TaskMem@G@ConnectedStorage@@QEAAXXZ; ConnectedStorage::TaskMem<ushort>::Release(void)
0x180046b7c  mov     rdi, [rsp+1F8h+var_198]
0x180046b81  mov     rcx, [rsp+1F8h+var_140]; this
0x180046b89  test    rcx, rcx
0x180046b8c  jz      short loc_180046B94
0x180046b8e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180046b93  nop
0x180046b94  mov     rcx, [rdi+8]; this
0x180046b98  test    rcx, rcx
0x180046b9b  jz      short loc_180046BA3
0x180046b9d  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x180046ba2  nop
0x180046ba3  mov     rcx, r15; this
0x180046ba6  call    ??1ContextDesc@ConnectedStorage@@QEAA@XZ; ConnectedStorage::ContextDesc::~ContextDesc(void)
0x180046bab  nop
0x180046bac  mov     rcx, r14
0x180046baf  call    ??1?$function@$$A6AJXZ@std@@QEAA@XZ; std::function<long (void)>::~function<long (void)>(void)
0x180046bb4  nop
0x180046bb5  mov     rcx, [r13+8]; this
0x180046bb9  test    rcx, rcx
0x180046bbc  jz      short loc_180046BC3
0x180046bbe  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180046bc3  mov     rcx, [rsp+1F8h+var_48]
0x180046bcb  xor     rcx, rsp; StackCookie
0x180046bce  call    __security_check_cookie
0x180046bd3  add     rsp, 1C0h
0x180046bda  pop     r15
0x180046bdc  pop     r14
0x180046bde  pop     r13
0x180046be0  pop     r12
0x180046be2  pop     rdi
0x180046be3  pop     rsi
0x180046be4  pop     rbx
0x180046be5  retn
```
