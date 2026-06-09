# ConnectedStorage::NtmWebService::AtomDownloadComplete(std::weak_ptr<ConnectedStorage::NtmWebService const>,ConnectedStorage::ContextDesc,_GUID,ConnectedStorage::Timer,ulong,Microsoft::WRL::ComPtr<ConnectedStorage::AtomDownloadStream>,std::shared_ptr<ConnectedStorage::NtmCancelCallback>,std::function<void (ConnectedStorage::WebService::Status,ConnectedStorage::Atom)>,_NTM_TRANSFER_STATUS const &,uint,long,bool)

- ea: `0x180040da8`
- end: `0x1800414c9`
- name: `?AtomDownloadComplete@NtmWebService@ConnectedStorage@@CAXV?$weak_ptr@$$CBVNtmWebService@ConnectedStorage@@@std@@VContextDesc@2@U_GUID@@VTimer@2@KV?$ComPtr@VAtomDownloadStream@ConnectedStorage@@@WRL@Microsoft@@V?$shared_ptr@VNtmCancelCallback@ConnectedStorage@@@4@V?$function@$$A6AXW4Status@WebService@ConnectedStorage@@VAtom@3@@Z@4@AEBU_NTM_TRANSFER_STATUS@@IJ_N@Z`
- size: `1825`
- prototype: ``
- caller_count: `1`
- callee_count: `33`
- tags: `service_task, broker_com_uri`

## callers

- `0x180040030`

## callees

- `0x180003c70`
- `0x18000a040`
- `0x18000aae4`
- `0x18000c218`
- `0x18000cb9c`
- `0x18000cd1c`
- `0x180010e90`
- `0x180010f28`
- `0x1800113bc`
- `0x180011c0c`
- `0x1800124d0`
- `0x1800125ec`
- `0x180012ed8`
- `0x180014fdc`
- `0x1800190f0`
- `0x180019128`
- `0x18001c090`
- `0x18001c8f0`
- `0x18001e504`
- `0x18002d880`
- `0x180039534`
- `0x18003a278`
- `0x18003ea50`
- `0x18003f9d8`
- `0x180040da8`
- `0x18004208c`
- `0x18004319c`
- `0x180043758`
- `0x180047324`
- `0x18006972c`
- `0x18006977c`
- `0x18007cd60`
- `0x18008e010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180040f83`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180040fa5`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180040f83`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180040fa5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180041200`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180041200`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180040f65`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004140d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180040f65`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004140d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180040e55`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180040e6f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180040f72`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180040f94`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180040e55`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180040e6f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180040f72`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180040f94`

## pseudocode

```c
// Hidden C++ exception states: #wind=20
__int64 ConnectedStorage::NtmWebService::AtomDownloadComplete(__int64 a1, HSTRING *a2, unsigned __int16 *a3, ...)
{
  __int64 v4; // r13
  char v5; // r14
  __int64 v6; // r12
  unsigned int TimeMs; // edi
  const unsigned __int16 *StringRawBuffer; // rbx
  ConnectedStorage *v9; // rax
  int v10; // esi
  int v11; // r15d
  PCWSTR v12; // rax
  PCWSTR v13; // rax
  int v14; // ebx
  __int64 v15; // rdi
  ConnectedStorage::ContextDesc *v16; // rsi
  int v17; // eax
  const unsigned __int16 *v18; // r8
  __int64 v19; // rsi
  _QWORD *v20; // r14
  __int128 v21; // xmm6
  HSTRING *v22; // rax
  __int64 v23; // r8
  __int64 Atom; // rdx
  __int64 v25; // r14
  __int64 v26; // rdi
  HSTRING v27; // rbx
  char *v28; // r8
  __int64 v29; // rbx
  __int64 v30; // rax
  __int64 v31; // rbx
  int v32; // eax
  const unsigned __int16 *v33; // r8
  __int64 v34; // rdi
  _QWORD *Quota; // rsi
  __int128 v36; // xmm6
  HSTRING *v37; // rax
  __int64 v38; // rax
  std::_Ref_count_base *v39; // rcx
  std::_Ref_count_base *v40; // rcx
  int v42; // [rsp+30h] [rbp-298h]
  unsigned int v43; // [rsp+38h] [rbp-290h]
  char v44; // [rsp+40h] [rbp-288h]
  char v45; // [rsp+41h] [rbp-287h]
  HSTRING string; // [rsp+48h] [rbp-280h] BYREF
  HSTRING *v47; // [rsp+50h] [rbp-278h]
  unsigned __int16 *p_string; // [rsp+58h] [rbp-270h]
  HSTRING newString; // [rsp+60h] [rbp-268h] BYREF
  __int64 v50; // [rsp+68h] [rbp-260h]
  PCNZWCH sourceString; // [rsp+70h] [rbp-258h] BYREF
  __int64 v52; // [rsp+78h] [rbp-250h]
  ConnectedStorage::ContextDesc *v53; // [rsp+80h] [rbp-248h]
  __int64 v54; // [rsp+88h] [rbp-240h] BYREF
  std::_Ref_count_base *v55; // [rsp+90h] [rbp-238h]
  _QWORD *v56; // [rsp+98h] [rbp-230h]
  void *v57; // [rsp+A0h] [rbp-228h]
  LPCRITICAL_SECTION *v58; // [rsp+A8h] [rbp-220h]
  HSTRING v59[8]; // [rsp+B0h] [rbp-218h] BYREF
  _BYTE v60[64]; // [rsp+F0h] [rbp-1D8h] BYREF
  __int128 v61; // [rsp+130h] [rbp-198h] BYREF
  LPCRITICAL_SECTION lpCriticalSection[4]; // [rsp+140h] [rbp-188h] BYREF
  _DWORD v63[16]; // [rsp+160h] [rbp-168h] BYREF
  _BYTE v64[64]; // [rsp+1A0h] [rbp-128h] BYREF
  _BYTE v65[64]; // [rsp+1E0h] [rbp-E8h] BYREF
  unsigned __int16 v66[8]; // [rsp+220h] [rbp-A8h] BYREF
  __int128 v67; // [rsp+230h] [rbp-98h]
  wchar_t v68; // [rsp+240h] [rbp-88h]
  __int64 v69; // [rsp+250h] [rbp-78h] BYREF
  wchar_t v70; // [rsp+258h] [rbp-70h]
  __int128 v71; // [rsp+260h] [rbp-68h] BYREF
  __int64 v72; // [rsp+2E8h] [rbp+20h] BYREF
  va_list va; // [rsp+2E8h] [rbp+20h]
  __int64 v74; // [rsp+2F0h] [rbp+28h]
  HSTRING *v75; // [rsp+2F8h] [rbp+30h]
  _QWORD *v76; // [rsp+300h] [rbp+38h]
  __int64 v77; // [rsp+308h] [rbp+40h]
  __int64 v78; // [rsp+310h] [rbp+48h]
  __int64 v79; // [rsp+318h] [rbp+50h]
  __int64 v80; // [rsp+320h] [rbp+58h]
  __int64 v81; // [rsp+328h] [rbp+60h]
  va_list va1; // [rsp+330h] [rbp+68h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v72 = va_arg(va1, _QWORD);
  v74 = va_arg(va1, _QWORD);
  v75 = va_arg(va1, HSTRING *);
  v76 = va_arg(va1, _QWORD *);
  v77 = va_arg(va1, _QWORD);
  v78 = va_arg(va1, _QWORD);
  v79 = va_arg(va1, _QWORD);
  v80 = va_arg(va1, _QWORD);
  v81 = va_arg(va1, _QWORD);
  p_string = a3;
  v52 = a1;
  v53 = (ConnectedStorage::ContextDesc *)a2;
  *(_QWORD *)&v61 = a3;
  v47 = v75;
  v56 = v76;
  v50 = v77;
  v4 = v78;
  v44 = 1;
  v5 = 0;
  v45 = 0;
  v6 = *(unsigned int *)(v78 + 88);
  TimeMs = ConnectedStorage::Timer::GetTimeMs((ConnectedStorage::Timer *)va);
  v57 = a2 + 2;
  StringRawBuffer = WindowsGetStringRawBuffer(a2[2], 0);
  v58 = (LPCRITICAL_SECTION *)(a2 + 3);
  v9 = (ConnectedStorage *)WindowsGetStringRawBuffer(a2[3], 0);
  v10 = v79;
  v11 = v80;
  ConnectedStorage::EventWriteWebDownloadAtom(
    v9,
    StringRawBuffer,
    p_string,
    (const struct _GUID *const)(unsigned int)v6,
    TimeMs,
    v80,
    v79,
    v43);
  sourceString = 0;
  newString = 0;
  *(_OWORD *)v66 = *(_OWORD *)L"Content-Encoding";
  v67 = *(_OWORD *)L"Encoding";
  v68 = aContentEncodin[16];
  v69 = *(_QWORD *)L"gzip";
  v70 = aGzip[4];
  v71 = *(_OWORD *)L"deflate";
  if ( *(_QWORD *)(v4 + 72) )
  {
    ConnectedStorage::TaskMem<unsigned short>::Release(&sourceString);
    if ( (int)GetHttpHeaderFromRawHttpHeaders(
                *(const unsigned __int16 **)(v4 + 72),
                v66,
                (unsigned __int16 **)&sourceString) >= 0 )
    {
      ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&string, sourceString);
      ConnectedStorage::SimpleHStringWrapper::operator=(&newString);
      WindowsDeleteString(string);
      v12 = WindowsGetStringRawBuffer(newString, 0);
      if ( !(unsigned int)_o__wcsicmp(v12, &v69)
        || (v13 = WindowsGetStringRawBuffer(newString, 0), !(unsigned int)_o__wcsicmp(v13, &v71)) )
      {
        v5 = 1;
        v45 = 1;
      }
    }
  }
  if ( v11 >= 0 )
  {
    try
    {
      ConnectedStorage::Atom::Atom((ConnectedStorage::Atom *)v66);
      LOBYTE(v23) = v5;
      Atom = ConnectedStorage::AtomDownloadStream::GetAtom(*v47, lpCriticalSection, v23);
      ConnectedStorage::Atom::operator=(v66, Atom);
      ConnectedStorage::Atom::~Atom((ConnectedStorage::Atom *)lpCriticalSection);
      std::weak_ptr<ConnectedStorage::UploadingContext>::lock(v52, &v54);
      v25 = v54;
      if ( v54 )
      {
        if ( !v10 )
          v10 = 2 - v74;
        v26 = ConnectedStorage::Timer::GetTimeMs((ConnectedStorage::Timer *)va);
        v27 = *v47;
        ConnectedStorage::Mutex::Lock::Lock(
          (ConnectedStorage::Mutex::Lock *)lpCriticalSection,
          (struct _RTL_CRITICAL_SECTION *)(*v47 + 12),
          v28);
        v29 = *((unsigned int *)v27 + 28);
        LeaveCriticalSection(lpCriticalSection[0]);
        ConnectedStorage::NtmWebService::WriteTelemetry(v25, 1, v58, v57, v6, v29, v26, v10);
      }
      if ( v55 )
        std::_Ref_count_base::_Decref(v55);
    }
    catch ( ConnectedStorage::ComError v63 )
    {
      LODWORD(string) = v63[6];
      ConnectedStorage::ComError::~ComError((ConnectedStorage::ComError *)v63);
      if ( (int)string < 0 )
      {
LABEL_25:
        if ( v45 )
        {
          std::weak_ptr<ConnectedStorage::UploadingContext>::lock(v52, &v54);
          v31 = v54;
          if ( v54 )
          {
            try
            {
              p_string = 0;
              v32 = (*(__int64 (__fastcall **)(HSTRING, _QWORD, _QWORD, _QWORD))(*(_QWORD *)*v47 + 40LL))(*v47, 0, 0, 0);
              if ( v32 < 0 )
                ConnectedStorage::ReportErrorAndThrow(
                  (ConnectedStorage *)(unsigned int)v32,
                  (int)L"stream->Seek(seek, STREAM_SEEK_SET, nullptr)",
                  v33);
              v58 = (LPCRITICAL_SECTION *)v60;
              v34 = std::function<void (enum ConnectedStorage::WebService::Status,ConnectedStorage::Atom)>::function<void (enum ConnectedStorage::WebService::Status,ConnectedStorage::Atom)>(
                      (__int64)v60,
                      v50);
              v57 = lpCriticalSection;
              Quota = std::shared_ptr<ConnectedStorage::GetQuotaData>::shared_ptr<ConnectedStorage::GetQuotaData>(
                        lpCriticalSection,
                        v56);
              p_string = (unsigned __int16 *)&string;
              string = *v47;
              Microsoft::WRL::ComPtr<ConnectedStorage::AtomDownloadStream>::InternalAddRef(&string);
              v36 = *(_OWORD *)v61;
              v37 = ConnectedStorage::ContextDesc::ContextDesc(v59, v53);
              v61 = v36;
              LOBYTE(v42) = 0;
              ConnectedStorage::NtmWebService::DownloadAtomImpl(
                v31,
                v37,
                &v61,
                (unsigned int)v74,
                &string,
                Quota,
                v42,
                v34);
              v44 = 0;
            }
            catch ( ConnectedStorage::ComError v65 )
            {
              ConnectedStorage::ComError::~ComError((ConnectedStorage::ComError *)v65);
            }
            catch ( std::bad_alloc )
            {
            }
            catch ( ... )
            {
            }
          }
          if ( v55 )
            std::_Ref_count_base::_Decref(v55);
        }
        goto LABEL_32;
      }
    }
    catch ( std::bad_alloc )
    {
      goto LABEL_25;
    }
    catch ( ... )
    {
      goto LABEL_25;
    }
    v44 = 0;
    v30 = ConnectedStorage::Atom::Atom(
            (ConnectedStorage::Atom *)lpCriticalSection,
            (const struct ConnectedStorage::Atom *)v66);
    std::_Func_class<void,enum ConnectedStorage::WebService::Status,ConnectedStorage::Atom>::operator()(v50, 9, v30);
LABEL_32:
    ConnectedStorage::Atom::~Atom((ConnectedStorage::Atom *)v66);
    goto LABEL_33;
  }
  std::weak_ptr<ConnectedStorage::UploadingContext>::lock(v52, &v54);
  v14 = v74;
  if ( (_DWORD)v74 )
  {
    v15 = v54;
    if ( v54 )
    {
      try
      {
        if ( v11 == -2145844847 )
        {
          v16 = v53;
          ConnectedStorage::MakeUrl(v66, v53);
          ConnectedStorage::NtmWebService::InvalidateToken(v15, v66, v16);
          std::wstring::_Tidy_deallocate(v66);
        }
        string = 0;
        v17 = (*(__int64 (__fastcall **)(HSTRING, _QWORD, _QWORD, _QWORD))(*(_QWORD *)*v47 + 40LL))(*v47, 0, 0, 0);
        if ( v17 < 0 )
          ConnectedStorage::ReportErrorAndThrow(
            (ConnectedStorage *)(unsigned int)v17,
            (int)L"stream->Seek(seek, STREAM_SEEK_SET, nullptr)",
            v18);
        *(_QWORD *)&v61 = v59;
        v19 = std::function<void (enum ConnectedStorage::WebService::Status,ConnectedStorage::Atom)>::function<void (enum ConnectedStorage::WebService::Status,ConnectedStorage::Atom)>(
                (__int64)v59,
                v50);
        v58 = lpCriticalSection;
        v20 = std::shared_ptr<ConnectedStorage::GetQuotaData>::shared_ptr<ConnectedStorage::GetQuotaData>(
                lpCriticalSection,
                v56);
        v57 = &string;
        string = *v47;
        Microsoft::WRL::ComPtr<ConnectedStorage::AtomDownloadStream>::InternalAddRef(&string);
        v21 = *(_OWORD *)p_string;
        v22 = ConnectedStorage::ContextDesc::ContextDesc((HSTRING *)v66, v53);
        v61 = v21;
        LOBYTE(v42) = v81;
        ConnectedStorage::NtmWebService::DownloadAtomImpl(
          v15,
          v22,
          &v61,
          (unsigned int)(v14 - 1),
          &string,
          v20,
          v42,
          v19);
        v44 = 0;
      }
      catch ( ConnectedStorage::ComError v64 )
      {
        ConnectedStorage::ComError::~ComError((ConnectedStorage::ComError *)v64);
      }
      catch ( std::bad_alloc )
      {
      }
      catch ( ... )
      {
      }
    }
  }
  if ( v55 )
    std::_Ref_count_base::_Decref(v55);
LABEL_33:
  if ( v44 )
  {
    ConnectedStorage::AtomDownloadStream::Abandon((ConnectedStorage::AtomDownloadStream *)*v47);
    v38 = ConnectedStorage::Atom::Atom((ConnectedStorage::Atom *)v66);
    std::_Func_class<void,enum ConnectedStorage::WebService::Status,ConnectedStorage::Atom>::operator()(v50, 1, v38);
  }
  WindowsDeleteString(newString);
  newString = 0;
  ConnectedStorage::TaskMem<unsigned short>::Release(&sourceString);
  v39 = *(std::_Ref_count_base **)(v52 + 8);
  if ( v39 )
    std::_Ref_count_base::_Decwref(v39);
  ConnectedStorage::ContextDesc::~ContextDesc((HSTRING *)v53);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v47);
  v40 = (std::_Ref_count_base *)v56[1];
  if ( v40 )
    std::_Ref_count_base::_Decref(v40);
  return std::function<long (void)>::~function<long (void)>(v50);
}

```

## disassembly

```asm
0x180040da8  mov     r11, rsp
0x180040dab  mov     [r11+20h], r9
0x180040daf  push    rbx
0x180040db0  push    rsi
0x180040db1  push    rdi
0x180040db2  push    r12
0x180040db4  push    r13
0x180040db6  push    r14
0x180040db8  push    r15
0x180040dba  sub     rsp, 290h
0x180040dc1  movaps  xmmword ptr [r11-48h], xmm6
0x180040dc6  mov     rax, cs:__security_cookie
0x180040dcd  xor     rax, rsp
0x180040dd0  mov     [rsp+2C8h+var_58], rax
0x180040dd8  mov     rax, r8
0x180040ddb  mov     [rsp+2C8h+var_270], rax
0x180040de0  mov     rsi, rdx
0x180040de3  mov     [rsp+2C8h+var_250], rcx
0x180040de8  mov     [r11-248h], rdx
0x180040def  mov     qword ptr [rsp+2C8h+var_198], rax
0x180040df7  mov     rax, [rsp+2C8h+arg_28]
0x180040dff  mov     [rsp+2C8h+var_278], rax
0x180040e04  mov     rax, [rsp+2C8h+arg_30]
0x180040e0c  mov     [r11-230h], rax
0x180040e13  mov     rax, [rsp+2C8h+arg_38]
0x180040e1b  mov     [rsp+2C8h+var_260], rax
0x180040e20  mov     r13, [rsp+2C8h+arg_40]
0x180040e28  mov     [rsp+2C8h+var_288], 1
0x180040e2d  xor     r14b, r14b
0x180040e30  mov     [rsp+2C8h+var_287], r14b
0x180040e35  mov     r12d, [r13+58h]
0x180040e39  lea     rcx, [r11+20h]; this
0x180040e3d  call    ?GetTimeMs@Timer@ConnectedStorage@@QEBAIXZ; ConnectedStorage::Timer::GetTimeMs(void)
0x180040e42  mov     edi, eax
0x180040e44  lea     rax, [rsi+10h]
0x180040e48  mov     [rsp+2C8h+var_228], rax
0x180040e50  xor     edx, edx; length
0x180040e52  mov     rcx, [rax]; string
0x180040e55  call    cs:__imp_WindowsGetStringRawBuffer
0x180040e5b  mov     rbx, rax
0x180040e5e  lea     rax, [rsi+18h]
0x180040e62  mov     [rsp+2C8h+var_220], rax
0x180040e6a  xor     edx, edx; length
0x180040e6c  mov     rcx, [rax]; string
0x180040e6f  call    cs:__imp_WindowsGetStringRawBuffer
0x180040e75  mov     esi, dword ptr [rsp+2C8h+arg_48]
0x180040e7c  mov     [rsp+2C8h+var_298], esi; unsigned int
0x180040e80  mov     r15d, dword ptr [rsp+2C8h+arg_50]
0x180040e88  mov     [rsp+2C8h+var_2A0], r15d; unsigned int
0x180040e8d  mov     [rsp+2C8h+var_2A8], edi; unsigned int
0x180040e91  mov     r9d, r12d; struct _GUID *
0x180040e94  mov     r8, [rsp+2C8h+var_270]; unsigned __int16 *
0x180040e99  mov     rdx, rbx; unsigned __int16 *
0x180040e9c  mov     rcx, rax; this
0x180040e9f  call    ?EventWriteWebDownloadAtom@ConnectedStorage@@YAXQEBG0QEBU_GUID@@IIII@Z; ConnectedStorage::EventWriteWebDownloadAtom(ushort const * const,ushort const * const,_GUID const * const,uint,uint,uint,uint)
0x180040ea4  mov     [rsp+2C8h+sourceString], 0
0x180040ead  mov     [rsp+2C8h+newString], 0
0x180040eb6  movups  xmm0, xmmword ptr cs:aContentEncodin; "Content-Encoding"
0x180040ebd  movups  xmmword ptr [rsp+2C8h+var_A8], xmm0
0x180040ec5  movups  xmm1, xmmword ptr cs:aContentEncodin+10h; "Encoding"
0x180040ecc  movups  [rsp+2C8h+var_98], xmm1
0x180040ed4  movzx   eax, word ptr cs:aContentEncodin+20h; ""
0x180040edb  mov     [rsp+2C8h+var_88], ax
0x180040ee3  movsd   xmm0, qword ptr cs:aGzip; "gzip"
0x180040eeb  movsd   [rsp+2C8h+var_78], xmm0
0x180040ef4  movzx   eax, word ptr cs:aGzip+8; ""
0x180040efb  mov     [rsp+2C8h+var_70], ax
0x180040f03  movups  xmm0, xmmword ptr cs:aDeflate; "deflate"
0x180040f0a  movdqu  [rsp+2C8h+var_68], xmm0
0x180040f13  cmp     qword ptr [r13+48h], 0
0x180040f18  jz      loc_180040FB7
0x180040f1e  lea     rcx, [rsp+2C8h+sourceString]
0x180040f23  call    ?Release@?$TaskMem@G@ConnectedStorage@@QEAAXXZ; ConnectedStorage::TaskMem<ushort>::Release(void)
0x180040f28  lea     r8, [rsp+2C8h+sourceString]; unsigned __int16 **
0x180040f2d  lea     rdx, [rsp+2C8h+var_A8]; unsigned __int16 *
0x180040f35  mov     rcx, [r13+48h]; unsigned __int16 *
0x180040f39  call    ?GetHttpHeaderFromRawHttpHeaders@@YAJPEBG0PEAPEAG@Z; GetHttpHeaderFromRawHttpHeaders(ushort const *,ushort const *,ushort * *)
0x180040f3e  test    eax, eax
0x180040f40  js      short loc_180040FB7
0x180040f42  mov     rdx, [rsp+2C8h+sourceString]; sourceString
0x180040f47  lea     rcx, [rsp+2C8h+string]; string
0x180040f4c  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@PEBG@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(ushort const *)
0x180040f51  nop
0x180040f52  mov     rdx, rax
0x180040f55  lea     rcx, [rsp+2C8h+newString]; newString
0x180040f5a  call    ??4SimpleHStringWrapper@ConnectedStorage@@QEAAAEAV01@AEBV01@@Z; ConnectedStorage::SimpleHStringWrapper::operator=(ConnectedStorage::SimpleHStringWrapper const &)
0x180040f5f  nop
0x180040f60  mov     rcx, [rsp+2C8h+string]; string
0x180040f65  call    cs:__imp_WindowsDeleteString
0x180040f6b  xor     edx, edx; length
0x180040f6d  mov     rcx, [rsp+2C8h+newString]; string
0x180040f72  call    cs:__imp_WindowsGetStringRawBuffer
0x180040f78  lea     rdx, [rsp+2C8h+var_78]
0x180040f80  mov     rcx, rax
0x180040f83  call    cs:__imp__o__wcsicmp
0x180040f89  test    eax, eax
0x180040f8b  jz      short loc_180040FAF
0x180040f8d  xor     edx, edx; length
0x180040f8f  mov     rcx, [rsp+2C8h+newString]; string
0x180040f94  call    cs:__imp_WindowsGetStringRawBuffer
0x180040f9a  lea     rdx, [rsp+2C8h+var_68]
0x180040fa2  mov     rcx, rax
0x180040fa5  call    cs:__imp__o__wcsicmp
0x180040fab  test    eax, eax
0x180040fad  jnz     short loc_180040FB7
0x180040faf  mov     r14b, 1
0x180040fb2  mov     [rsp+2C8h+var_287], r14b
0x180040fb7  test    r15d, r15d
0x180040fba  jns     loc_180041158
0x180040fc0  lea     rdx, [rsp+2C8h+var_240]
0x180040fc8  mov     rcx, [rsp+2C8h+var_250]
0x180040fcd  call    ?lock@?$weak_ptr@VUploadingContext@ConnectedStorage@@@std@@QEBA?AV?$shared_ptr@VUploadingContext@ConnectedStorage@@@2@XZ; std::weak_ptr<ConnectedStorage::UploadingContext>::lock(void)
0x180040fd2  nop
0x180040fd3  mov     ebx, dword ptr [rsp+2C8h+arg_20]
0x180040fda  test    ebx, ebx
0x180040fdc  jz      loc_180041139
0x180040fe2  mov     rdi, [rsp+2C8h+var_240]
0x180040fea  test    rdi, rdi
0x180040fed  jz      loc_180041139
0x180040ff3  cmp     r15d, 80190191h
0x180040ffa  jnz     short loc_180041036
0x180040ffc  mov     rsi, [rsp+2C8h+var_248]
0x180041004  mov     rdx, rsi
0x180041007  lea     rcx, [rsp+2C8h+var_A8]
0x18004100f  call    ?MakeUrl@ConnectedStorage@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBVContextDesc@1@@Z; ConnectedStorage::MakeUrl(ConnectedStorage::ContextDesc const &)
0x180041014  nop
0x180041015  mov     r8, rsi
0x180041018  lea     rdx, [rsp+2C8h+var_A8]
0x180041020  mov     rcx, rdi
0x180041023  call    ?InvalidateToken@NtmWebService@ConnectedStorage@@AEBAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBVContextDesc@2@@Z; ConnectedStorage::NtmWebService::InvalidateToken(std::wstring const &,ConnectedStorage::ContextDesc const &)
0x180041028  nop
0x180041029  lea     rcx, [rsp+2C8h+var_A8]
0x180041031  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180041036  mov     [rsp+2C8h+string], 0
0x18004103f  mov     rax, [rsp+2C8h+var_278]
0x180041044  mov     rcx, [rax]
0x180041047  mov     rax, [rcx]
0x18004104a  xor     r9d, r9d
0x18004104d  xor     r8d, r8d
0x180041050  mov     rdx, [rsp+2C8h+string]
0x180041055  mov     rax, [rax+28h]
0x180041059  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004105e  test    eax, eax
0x180041060  js      loc_1800414AA
0x180041066  lea     rax, [rsp+2C8h+var_218]
0x18004106e  mov     qword ptr [rsp+2C8h+var_198], rax
0x180041076  mov     rdx, [rsp+2C8h+var_260]
0x18004107b  lea     rcx, [rsp+2C8h+var_218]
0x180041083  call    ??0?$function@$$A6AXW4Status@WebService@ConnectedStorage@@VAtom@3@@Z@std@@QEAA@AEBV01@@Z; std::function<void (ConnectedStorage::WebService::Status,ConnectedStorage::Atom)>::function<void (ConnectedStorage::WebService::Status,ConnectedStorage::Atom)>(std::function<void (ConnectedStorage::WebService::Status,ConnectedStorage::Atom)> const &)
0x180041088  mov     rsi, rax
0x18004108b  lea     rax, [rsp+2C8h+lpCriticalSection]
0x180041093  mov     [rsp+2C8h+var_220], rax
0x18004109b  mov     rdx, [rsp+2C8h+var_230]
0x1800410a3  lea     rcx, [rsp+2C8h+lpCriticalSection]
0x1800410ab  call    ??0?$shared_ptr@UGetQuotaData@ConnectedStorage@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<ConnectedStorage::GetQuotaData>::shared_ptr<ConnectedStorage::GetQuotaData>(std::shared_ptr<ConnectedStorage::GetQuotaData> const &)
0x1800410b0  mov     r14, rax
0x1800410b3  lea     rax, [rsp+2C8h+string]
0x1800410b8  mov     [rsp+2C8h+var_228], rax
0x1800410c0  mov     rcx, [rsp+2C8h+var_278]
0x1800410c5  mov     rdx, [rcx]
0x1800410c8  mov     [rsp+2C8h+string], rdx
0x1800410cd  lea     rcx, [rsp+2C8h+string]
0x1800410d2  call    ?InternalAddRef@?$ComPtr@VAtomDownloadStream@ConnectedStorage@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<ConnectedStorage::AtomDownloadStream>::InternalAddRef(void)
0x1800410d7  nop
0x1800410d8  mov     rax, [rsp+2C8h+var_270]
0x1800410dd  movaps  xmm6, xmmword ptr [rax]
0x1800410e0  mov     rdx, [rsp+2C8h+var_248]; struct ConnectedStorage::ContextDesc *
0x1800410e8  lea     rcx, [rsp+2C8h+var_A8]; this
0x1800410f0  call    ??0ContextDesc@ConnectedStorage@@QEAA@AEBV01@@Z; ConnectedStorage::ContextDesc::ContextDesc(ConnectedStorage::ContextDesc const &)
0x1800410f5  movdqu  [rsp+2C8h+var_198], xmm6
0x1800410fe  mov     [rsp+2C8h+var_290], rsi
0x180041103  mov     dl, byte ptr [rsp+2C8h+arg_58]
0x18004110a  mov     byte ptr [rsp+2C8h+var_298], dl
0x18004110e  mov     qword ptr [rsp+2C8h+var_2A0], r14
0x180041113  lea     rcx, [rsp+2C8h+string]
0x180041118  mov     qword ptr [rsp+2C8h+var_2A8], rcx
0x18004111d  lea     r9d, [rbx-1]
0x180041121  lea     r8, [rsp+2C8h+var_198]
0x180041129  mov     rdx, rax
0x18004112c  mov     rcx, rdi
0x18004112f  call    ?DownloadAtomImpl@NtmWebService@ConnectedStorage@@AEBAXVContextDesc@2@U_GUID@@KV?$ComPtr@VAtomDownloadStream@ConnectedStorage@@@WRL@Microsoft@@V?$shared_ptr@VNtmCancelCallback@ConnectedStorage@@@std@@_NV?$function@$$A6AXW4Status@WebService@ConnectedStorage@@VAtom@3@@Z@9@@Z; ConnectedStorage::NtmWebService::DownloadAtomImpl(ConnectedStorage::ContextDesc,_GUID,ulong,Microsoft::WRL::ComPtr<ConnectedStorage::AtomDownloadStream>,std::shared_ptr<ConnectedStorage::NtmCancelCallback>,bool,std::function<void (ConnectedStorage::WebService::Status,ConnectedStorage::Atom)>)
0x180041134  mov     [rsp+2C8h+var_288], 0
0x180041139  mov     rcx, [rsp+2C8h+var_238]; this
0x180041141  test    rcx, rcx
0x180041144  jz      loc_1800413D4
0x18004114a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18004114f  jmp     loc_1800413D4
0x180041154  jmp     short loc_180041139
0x180041156  jmp     short loc_180041139
0x180041158  lea     rcx, [rsp+2C8h+var_A8]; this
0x180041160  call    ??0Atom@ConnectedStorage@@QEAA@XZ; ConnectedStorage::Atom::Atom(void)
0x180041165  nop
0x180041166  mov     r8b, r14b
0x180041169  lea     rdx, [rsp+2C8h+lpCriticalSection]
0x180041171  mov     rcx, [rsp+2C8h+var_278]
0x180041176  mov     rcx, [rcx]
0x180041179  call    ?GetAtom@AtomDownloadStream@ConnectedStorage@@QEBA?AVAtom@2@_N@Z; ConnectedStorage::AtomDownloadStream::GetAtom(bool)
0x18004117e  nop
0x18004117f  mov     rdx, rax
0x180041182  lea     rcx, [rsp+2C8h+var_A8]
0x18004118a  call    ??4Atom@ConnectedStorage@@QEAAAEAV01@AEBV01@@Z; ConnectedStorage::Atom::operator=(ConnectedStorage::Atom const &)
0x18004118f  nop
0x180041190  lea     rcx, [rsp+2C8h+lpCriticalSection]; this
0x180041198  call    ??1Atom@ConnectedStorage@@QEAA@XZ; ConnectedStorage::Atom::~Atom(void)
0x18004119d  lea     rdx, [rsp+2C8h+var_240]
0x1800411a5  mov     rcx, [rsp+2C8h+var_250]
0x1800411aa  call    ?lock@?$weak_ptr@VUploadingContext@ConnectedStorage@@@std@@QEBA?AV?$shared_ptr@VUploadingContext@ConnectedStorage@@@2@XZ; std::weak_ptr<ConnectedStorage::UploadingContext>::lock(void)
0x1800411af  nop
0x1800411b0  mov     r14, [rsp+2C8h+var_240]
0x1800411b8  test    r14, r14
0x1800411bb  jz      short loc_180041237
0x1800411bd  test    esi, esi
0x1800411bf  jnz     short loc_1800411CD
0x1800411c1  mov     esi, 2
0x1800411c6  sub     esi, dword ptr [rsp+2C8h+arg_20]
0x1800411cd  lea     rcx, [rsp+2C8h+arg_18]; this
0x1800411d5  call    ?GetTimeMs@Timer@ConnectedStorage@@QEBAIXZ; ConnectedStorage::Timer::GetTimeMs(void)
0x1800411da  mov     edi, eax
0x1800411dc  mov     rax, [rsp+2C8h+var_278]
0x1800411e1  mov     rbx, [rax]
0x1800411e4  lea     rdx, [rbx+30h]; struct ConnectedStorage::Mutex *
0x1800411e8  lea     rcx, [rsp+2C8h+lpCriticalSection]; this
0x1800411f0  call    ??0Lock@Mutex@ConnectedStorage@@QEAA@AEAV12@PEAD@Z; ConnectedStorage::Mutex::Lock::Lock(ConnectedStorage::Mutex &,char *)
0x1800411f5  mov     ebx, [rbx+70h]
0x1800411f8  mov     rcx, [rsp+2C8h+lpCriticalSection]; lpCriticalSection
0x180041200  call    cs:__imp_LeaveCriticalSection
0x180041206  mov     dword ptr [rsp+2C8h+var_290], esi
0x18004120a  mov     qword ptr [rsp+2C8h+var_298], rdi
0x18004120f  mov     qword ptr [rsp+2C8h+var_2A0], rbx
0x180041214  mov     qword ptr [rsp+2C8h+var_2A8], r12
0x180041219  mov     r9, [rsp+2C8h+var_228]
0x180041221  mov     r8, [rsp+2C8h+var_220]
0x180041229  mov     edx, 1
0x18004122e  mov     rcx, r14
0x180041231  call    ?WriteTelemetry@NtmWebService@ConnectedStorage@@AEBAXW4TelemetryType@WebService@2@AEBVSimpleHStringWrapper@2@1_K22I@Z; ConnectedStorage::NtmWebService::WriteTelemetry(ConnectedStorage::WebService::TelemetryType,ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &,unsigned __int64,unsigned __int64,unsigned __int64,uint)
0x180041236  nop
0x180041237  mov     rcx, [rsp+2C8h+var_238]; this
0x18004123f  test    rcx, rcx
0x180041242  jz      short loc_18004124A
0x180041244  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180041249  nop
0x18004124a  jmp     short loc_180041253
0x18004124c  cmp     dword ptr [rsp+2C8h+string], 0
0x180041251  jl      short loc_180041284
0x180041253  mov     [rsp+2C8h+var_288], 0
0x180041258  lea     rdx, [rsp+2C8h+var_A8]; struct ConnectedStorage::Atom *
0x180041260  lea     rcx, [rsp+2C8h+lpCriticalSection]; this
0x180041268  call    ??0Atom@ConnectedStorage@@QEAA@AEBV01@@Z; ConnectedStorage::Atom::Atom(ConnectedStorage::Atom const &)
0x18004126d  mov     r8, rax
0x180041270  mov     edx, 9
0x180041275  mov     rcx, [rsp+2C8h+var_260]
0x18004127a  call    ??R?$_Func_class@XW4Status@WebService@ConnectedStorage@@VAtom@3@@std@@QEBAXW4Status@WebService@ConnectedStorage@@VAtom@4@@Z; std::_Func_class<void,ConnectedStorage::WebService::Status,ConnectedStorage::Atom>::operator()(ConnectedStorage::WebService::Status,ConnectedStorage::Atom)
0x18004127f  jmp     loc_1800413C7
0x180041284  cmp     [rsp+2C8h+var_287], 0
0x180041289  jz      loc_1800413C7
0x18004128f  lea     rdx, [rsp+2C8h+var_240]
0x180041297  mov     rcx, [rsp+2C8h+var_250]
0x18004129c  call    ?lock@?$weak_ptr@VUploadingContext@ConnectedStorage@@@std@@QEBA?AV?$shared_ptr@VUploadingContext@ConnectedStorage@@@2@XZ; std::weak_ptr<ConnectedStorage::UploadingContext>::lock(void)
0x1800412a1  nop
0x1800412a2  mov     rbx, [rsp+2C8h+var_240]
0x1800412aa  test    rbx, rbx
0x1800412ad  jz      loc_1800413B4
0x1800412b3  mov     [rsp+2C8h+var_270], 0
0x1800412bc  mov     rax, [rsp+2C8h+var_278]
0x1800412c1  mov     rcx, [rax]
0x1800412c4  mov     rax, [rcx]
0x1800412c7  xor     r9d, r9d
0x1800412ca  xor     r8d, r8d
0x1800412cd  mov     rdx, [rsp+2C8h+var_270]
0x1800412d2  mov     rax, [rax+28h]
0x1800412d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800412db  test    eax, eax
0x1800412dd  js      loc_1800414B9
0x1800412e3  lea     rax, [rsp+2C8h+var_1D8]
0x1800412eb  mov     [rsp+2C8h+var_220], rax
0x1800412f3  mov     rdx, [rsp+2C8h+var_260]
0x1800412f8  lea     rcx, [rsp+2C8h+var_1D8]
0x180041300  call    ??0?$function@$$A6AXW4Status@WebService@ConnectedStorage@@VAtom@3@@Z@std@@QEAA@AEBV01@@Z; std::function<void (ConnectedStorage::WebService::Status,ConnectedStorage::Atom)>::function<void (ConnectedStorage::WebService::Status,ConnectedStorage::Atom)>(std::function<void (ConnectedStorage::WebService::Status,ConnectedStorage::Atom)> const &)
0x180041305  mov     rdi, rax
0x180041308  lea     rax, [rsp+2C8h+lpCriticalSection]
0x180041310  mov     [rsp+2C8h+var_228], rax
0x180041318  mov     rdx, [rsp+2C8h+var_230]
0x180041320  lea     rcx, [rsp+2C8h+lpCriticalSection]
0x180041328  call    ??0?$shared_ptr@UGetQuotaData@ConnectedStorage@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<ConnectedStorage::GetQuotaData>::shared_ptr<ConnectedStorage::GetQuotaData>(std::shared_ptr<ConnectedStorage::GetQuotaData> const &)
0x18004132d  mov     rsi, rax
0x180041330  lea     rax, [rsp+2C8h+string]
0x180041335  mov     [rsp+2C8h+var_270], rax
0x18004133a  mov     rcx, [rsp+2C8h+var_278]
0x18004133f  mov     rdx, [rcx]
0x180041342  mov     [rsp+2C8h+string], rdx
0x180041347  lea     rcx, [rsp+2C8h+string]
0x18004134c  call    ?InternalAddRef@?$ComPtr@VAtomDownloadStream@ConnectedStorage@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<ConnectedStorage::AtomDownloadStream>::InternalAddRef(void)
0x180041351  nop
0x180041352  mov     rcx, qword ptr [rsp+2C8h+var_198]
0x18004135a  movaps  xmm6, xmmword ptr [rcx]
0x18004135d  mov     rdx, [rsp+2C8h+var_248]; struct ConnectedStorage::ContextDesc *
0x180041365  lea     rcx, [rsp+2C8h+var_218]; this
0x18004136d  call    ??0ContextDesc@ConnectedStorage@@QEAA@AEBV01@@Z; ConnectedStorage::ContextDesc::ContextDesc(ConnectedStorage::ContextDesc const &)
0x180041372  movdqu  [rsp+2C8h+var_198], xmm6
0x18004137b  mov     [rsp+2C8h+var_290], rdi
  ... truncated ...
```
