# ConnectedStorage::NtmWebService::DownloadContainerComplete(std::weak_ptr<ConnectedStorage::NtmWebService const>,ConnectedStorage::ContextDesc,ConnectedStorage::SimpleHStringWrapper const &,std::function<void (ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &)>,ConnectedStorage::Timer,ulong,Microsoft::WRL::ComPtr<ConnectedStorage::StringStream>,std::shared_ptr<ConnectedStorage::NtmCancelCallback>,_NTM_TRANSFER_STATUS const &,uint,long)

- ea: `0x180042800`
- end: `0x180042c13`
- name: `?DownloadContainerComplete@NtmWebService@ConnectedStorage@@CAXV?$weak_ptr@$$CBVNtmWebService@ConnectedStorage@@@std@@VContextDesc@2@AEBVSimpleHStringWrapper@2@V?$function@$$A6AXW4Status@WebService@ConnectedStorage@@AEBVSimpleHStringWrapper@3@1@Z@4@VTimer@2@KV?$ComPtr@VStringStream@ConnectedStorage@@@WRL@Microsoft@@V?$shared_ptr@VNtmCancelCallback@ConnectedStorage@@@4@AEBU_NTM_TRANSFER_STATUS@@IJ@Z`
- size: `1043`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003fc6c`

## callees

- `0x180003c70`
- `0x18000c218`
- `0x180010e90`
- `0x180010f28`
- `0x1800113bc`
- `0x180011c0c`
- `0x1800125ec`
- `0x180012ed8`
- `0x180014fdc`
- `0x1800190f0`
- `0x180019128`
- `0x18001c090`
- `0x18001c8f0`
- `0x18001e678`
- `0x18002a2a0`
- `0x18002d880`
- `0x180042800`
- `0x180042c1c`
- `0x18004319c`
- `0x180043758`
- `0x180047324`
- `0x18007cd60`
- `0x1800852fc`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042abe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042ace`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042b34`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042b68`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042b74`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042abe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042ace`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042b34`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042b68`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042b74`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180042888`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180042897`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800428a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180042888`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180042897`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800428a6`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
void __fastcall ConnectedStorage::NtmWebService::DownloadContainerComplete(
        __int64 a1,
        HSTRING *a2,
        char *a3,
        __int64 a4,
        char a5,
        int a6,
        __int64 *a7,
        _QWORD *a8,
        HSTRING a9,
        unsigned int a10,
        unsigned int a11)
{
  __int64 v11; // r13
  HSTRING *v13; // r15
  __int64 *v15; // r12
  unsigned int TimeMs; // esi
  const unsigned __int16 *StringRawBuffer; // rdi
  const unsigned __int16 *v18; // rbx
  ConnectedStorage *v19; // rax
  __int64 v20; // rsi
  unsigned int v21; // eax
  char v22; // di
  ConnectedStorage::NtmCancelCallback **Quota; // r14
  HSTRING *v24; // rax
  std::_Ref_count_base *v25; // rcx
  __int64 v26; // rcx
  HSTRING v27; // rdi
  __int64 v28; // rax
  std::_Ref_count_base *v29; // rcx
  __int64 v30; // rcx
  std::_Ref_count_base *v31; // rcx
  unsigned int v32; // [rsp+38h] [rbp-190h]
  HSTRING newString; // [rsp+40h] [rbp-188h] BYREF
  HSTRING string; // [rsp+48h] [rbp-180h] BYREF
  HSTRING v35; // [rsp+50h] [rbp-178h] BYREF
  HSTRING *v36; // [rsp+58h] [rbp-170h]
  __int64 v37; // [rsp+60h] [rbp-168h]
  __int64 *v38; // [rsp+68h] [rbp-160h]
  _QWORD *v39; // [rsp+70h] [rbp-158h]
  __int64 v40; // [rsp+78h] [rbp-150h]
  char *v41; // [rsp+80h] [rbp-148h]
  __int64 v42; // [rsp+88h] [rbp-140h] BYREF
  std::_Ref_count_base *v43; // [rsp+90h] [rbp-138h]
  _QWORD v44[2]; // [rsp+A0h] [rbp-128h] BYREF
  HSTRING v45; // [rsp+B0h] [rbp-118h] BYREF
  _BYTE v46[64]; // [rsp+E0h] [rbp-E8h] BYREF
  _BYTE v47[32]; // [rsp+120h] [rbp-A8h] BYREF
  _DWORD v48[16]; // [rsp+140h] [rbp-88h] BYREF

  v11 = a4;
  v41 = a3;
  v13 = a2;
  v40 = a1;
  v36 = a2;
  v37 = a4;
  v15 = a7;
  v38 = a7;
  v39 = a8;
  v35 = a9;
  LODWORD(newString) = a9[22];
  TimeMs = ConnectedStorage::Timer::GetTimeMs((ConnectedStorage::Timer *)&a5);
  StringRawBuffer = WindowsGetStringRawBuffer(*(HSTRING *)a3, 0);
  v18 = WindowsGetStringRawBuffer(v13[2], 0);
  v19 = (ConnectedStorage *)WindowsGetStringRawBuffer(v13[3], 0);
  ConnectedStorage::EventWriteWebDownloadContainer(
    v19,
    v18,
    StringRawBuffer,
    (const unsigned __int16 *const)(unsigned int)newString,
    TimeMs,
    a11,
    a10,
    v32);
  std::weak_ptr<ConnectedStorage::UploadingContext>::lock(a1, &v42);
  v20 = v42;
  if ( v42 )
  {
    v21 = ConnectedStorage::Timer::GetTimeMs((ConnectedStorage::Timer *)&a5);
    ConnectedStorage::NtmWebService::WriteTelemetry(v20, 3, v13 + 3, v13 + 2, (unsigned int)newString, 0, v21, a10);
  }
  if ( (a11 & 0x80000000) == 0 )
  {
    string = 0;
    newString = 0;
    v27 = v35;
    if ( *((_QWORD *)v35 + 9) )
    {
      ConnectedStorage::TaskMem<unsigned short>::Release(&string);
      if ( (int)GetHttpHeaderFromRawHttpHeaders(
                  *((const unsigned __int16 **)v27 + 9),
                  L"ETag",
                  (unsigned __int16 **)&string) >= 0 )
      {
        ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&v35, (PCNZWCH)string);
        ConnectedStorage::SimpleHStringWrapper::operator=(&newString);
        WindowsDeleteString(v35);
      }
    }
    v28 = ConnectedStorage::FromUtf8(&v35);
    std::_Func_class<void,enum ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &>::operator()(
      v11,
      11,
      &newString,
      v28);
    WindowsDeleteString(v35);
    WindowsDeleteString(newString);
    newString = 0;
    ConnectedStorage::TaskMem<unsigned short>::Release(&string);
    goto LABEL_21;
  }
  if ( v20 )
  {
    if ( a11 == -2145844847 )
    {
      v22 = a6 - 1;
      if ( a6 != 1 )
      {
        try
        {
          ConnectedStorage::MakeUrl(v47, v13);
          ConnectedStorage::NtmWebService::InvalidateToken(v20, v47, v13);
          v35 = (HSTRING)v44;
          Quota = (ConnectedStorage::NtmCancelCallback **)std::shared_ptr<ConnectedStorage::GetQuotaData>::shared_ptr<ConnectedStorage::GetQuotaData>(
                                                            v44,
                                                            v39);
          newString = (HSTRING)v46;
          string = (HSTRING)std::function<void (enum ConnectedStorage::WebService::Status,ConnectedStorage::Atom)>::function<void (enum ConnectedStorage::WebService::Status,ConnectedStorage::Atom)>(
                              (__int64)v46,
                              v11);
          v24 = ConnectedStorage::ContextDesc::ContextDesc(&v45, (const struct ConnectedStorage::ContextDesc *)v13);
          ConnectedStorage::NtmWebService::DownloadContainerImpl(v20, v24, v41, (__int64)string, v22, Quota);
          std::wstring::_Tidy_deallocate(v47);
        }
        catch ( ConnectedStorage::ComError v48 )
        {
          LODWORD(newString) = v48[6];
          ConnectedStorage::ComError::~ComError((ConnectedStorage::ComError *)v48);
          v13 = v36;
          v11 = v37;
          v15 = v38;
          if ( (int)newString >= 0 )
            goto LABEL_9;
          goto LABEL_16;
        }
        catch ( std::bad_alloc )
        {
          v15 = v38;
          v11 = v37;
          v13 = v36;
          goto LABEL_16;
        }
        catch ( ... )
        {
          v15 = v38;
          v11 = v37;
          v13 = v36;
          goto LABEL_16;
        }
LABEL_9:
        if ( v43 )
          std::_Ref_count_base::_Decref(v43);
        v25 = *(std::_Ref_count_base **)(v40 + 8);
        if ( v25 )
          std::_Ref_count_base::_Decwref(v25);
        ConnectedStorage::ContextDesc::~ContextDesc((ConnectedStorage::ContextDesc *)v13);
        std::function<long (void)>::~function<long (void)>(v11);
        v26 = *v15;
        if ( *v15 )
        {
          *v15 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
        }
        goto LABEL_27;
      }
    }
  }
LABEL_16:
  newString = 0;
  string = 0;
  std::_Func_class<void,enum ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &>::operator()(
    v11,
    1,
    &string,
    &newString);
  WindowsDeleteString(string);
  string = 0;
  WindowsDeleteString(newString);
LABEL_21:
  if ( v43 )
    std::_Ref_count_base::_Decref(v43);
  v29 = *(std::_Ref_count_base **)(v40 + 8);
  if ( v29 )
    std::_Ref_count_base::_Decwref(v29);
  ConnectedStorage::ContextDesc::~ContextDesc((ConnectedStorage::ContextDesc *)v13);
  std::function<long (void)>::~function<long (void)>(v11);
  v30 = *v15;
  if ( *v15 )
  {
    *v15 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
  }
LABEL_27:
  v31 = (std::_Ref_count_base *)v39[1];
  if ( v31 )
    std::_Ref_count_base::_Decref(v31);
}

```

## disassembly

```asm
0x180042800  mov     r11, rsp
0x180042803  push    rbx
0x180042804  push    rsi
0x180042805  push    rdi
0x180042806  push    r12
0x180042808  push    r13
0x18004280a  push    r14
0x18004280c  push    r15
0x18004280e  sub     rsp, 190h
0x180042815  mov     rax, cs:__security_cookie
0x18004281c  xor     rax, rsp
0x18004281f  mov     [rsp+1C8h+var_48], rax
0x180042827  mov     r13, r9
0x18004282a  mov     rbx, r8
0x18004282d  mov     [rsp+1C8h+var_148], rbx
0x180042835  mov     r15, rdx
0x180042838  mov     r14, rcx
0x18004283b  mov     [rsp+1C8h+var_150], rcx
0x180042840  mov     [rsp+1C8h+var_170], rdx
0x180042845  mov     [rsp+1C8h+var_168], r9
0x18004284a  mov     r12, [rsp+1C8h+arg_30]
0x180042852  mov     [rsp+1C8h+var_160], r12
0x180042857  mov     rax, [rsp+1C8h+arg_38]
0x18004285f  mov     [rsp+1C8h+var_158], rax
0x180042864  mov     rax, [rsp+1C8h+arg_40]
0x18004286c  mov     [rsp+1C8h+var_178], rax
0x180042871  mov     eax, [rax+58h]
0x180042874  mov     dword ptr [rsp+1C8h+newString], eax
0x180042878  lea     rcx, [r11+28h]; this
0x18004287c  call    ?GetTimeMs@Timer@ConnectedStorage@@QEBAIXZ; ConnectedStorage::Timer::GetTimeMs(void)
0x180042881  mov     esi, eax
0x180042883  xor     edx, edx; length
0x180042885  mov     rcx, [rbx]; string
0x180042888  call    cs:__imp_WindowsGetStringRawBuffer
0x18004288e  mov     rdi, rax
0x180042891  xor     edx, edx; length
0x180042893  mov     rcx, [r15+10h]; string
0x180042897  call    cs:__imp_WindowsGetStringRawBuffer
0x18004289d  mov     rbx, rax
0x1800428a0  xor     edx, edx; length
0x1800428a2  mov     rcx, [r15+18h]; string
0x1800428a6  call    cs:__imp_WindowsGetStringRawBuffer
0x1800428ac  mov     ecx, [rsp+1C8h+arg_48]
0x1800428b3  mov     [rsp+1C8h+var_198], ecx; unsigned int
0x1800428b7  mov     ecx, [rsp+1C8h+arg_50]
0x1800428be  mov     [rsp+1C8h+var_1A0], ecx; unsigned int
0x1800428c2  mov     [rsp+1C8h+var_1A8], esi; unsigned int
0x1800428c6  mov     r9d, dword ptr [rsp+1C8h+newString]; unsigned __int16 *
0x1800428cb  mov     r8, rdi; unsigned __int16 *
0x1800428ce  mov     rdx, rbx; unsigned __int16 *
0x1800428d1  mov     rcx, rax; this
0x1800428d4  call    ?EventWriteWebDownloadContainer@ConnectedStorage@@YAXQEBG00IIII@Z; ConnectedStorage::EventWriteWebDownloadContainer(ushort const * const,ushort const * const,ushort const * const,uint,uint,uint,uint)
0x1800428d9  lea     rdx, [rsp+1C8h+var_140]
0x1800428e1  mov     rcx, r14
0x1800428e4  call    ?lock@?$weak_ptr@VUploadingContext@ConnectedStorage@@@std@@QEBA?AV?$shared_ptr@VUploadingContext@ConnectedStorage@@@2@XZ; std::weak_ptr<ConnectedStorage::UploadingContext>::lock(void)
0x1800428e9  nop
0x1800428ea  mov     rsi, [rsp+1C8h+var_140]
0x1800428f2  xor     ebx, ebx
0x1800428f4  test    rsi, rsi
0x1800428f7  jz      short loc_180042939
0x1800428f9  lea     rcx, [rsp+1C8h+arg_20]; this
0x180042901  call    ?GetTimeMs@Timer@ConnectedStorage@@QEBAIXZ; ConnectedStorage::Timer::GetTimeMs(void)
0x180042906  mov     eax, eax
0x180042908  mov     ecx, dword ptr [rsp+1C8h+newString]
0x18004290c  mov     edx, [rsp+1C8h+arg_48]
0x180042913  mov     [rsp+1C8h+var_190], edx
0x180042917  mov     qword ptr [rsp+1C8h+var_198], rax
0x18004291c  mov     qword ptr [rsp+1C8h+var_1A0], rbx
0x180042921  mov     qword ptr [rsp+1C8h+var_1A8], rcx
0x180042926  lea     r9, [r15+10h]
0x18004292a  lea     r8, [r15+18h]
0x18004292e  lea     edx, [rbx+3]
0x180042931  mov     rcx, rsi
0x180042934  call    ?WriteTelemetry@NtmWebService@ConnectedStorage@@AEBAXW4TelemetryType@WebService@2@AEBVSimpleHStringWrapper@2@1_K22I@Z; ConnectedStorage::NtmWebService::WriteTelemetry(ConnectedStorage::WebService::TelemetryType,ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &,unsigned __int64,unsigned __int64,unsigned __int64,uint)
0x180042939  mov     eax, [rsp+1C8h+arg_50]
0x180042940  test    eax, eax
0x180042942  jns     loc_180042AD9
0x180042948  test    rsi, rsi
0x18004294b  jz      loc_180042A97
0x180042951  cmp     eax, 80190191h
0x180042956  jnz     loc_180042A97
0x18004295c  mov     edi, [rsp+1C8h+arg_28]
0x180042963  add     edi, 0FFFFFFFFh
0x180042966  jz      loc_180042A97
0x18004296c  mov     rdx, r15
0x18004296f  lea     rcx, [rsp+1C8h+var_A8]
0x180042977  call    ?MakeUrl@ConnectedStorage@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBVContextDesc@1@@Z; ConnectedStorage::MakeUrl(ConnectedStorage::ContextDesc const &)
0x18004297c  nop
0x18004297d  mov     r8, r15
0x180042980  lea     rdx, [rsp+1C8h+var_A8]
0x180042988  mov     rcx, rsi
0x18004298b  call    ?InvalidateToken@NtmWebService@ConnectedStorage@@AEBAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBVContextDesc@2@@Z; ConnectedStorage::NtmWebService::InvalidateToken(std::wstring const &,ConnectedStorage::ContextDesc const &)
0x180042990  lea     rax, [rsp+1C8h+var_128]
0x180042998  mov     [rsp+1C8h+var_178], rax
0x18004299d  mov     rdx, [rsp+1C8h+var_158]
0x1800429a2  lea     rcx, [rsp+1C8h+var_128]
0x1800429aa  call    ??0?$shared_ptr@UGetQuotaData@ConnectedStorage@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<ConnectedStorage::GetQuotaData>::shared_ptr<ConnectedStorage::GetQuotaData>(std::shared_ptr<ConnectedStorage::GetQuotaData> const &)
0x1800429af  mov     r14, rax
0x1800429b2  lea     rax, [rsp+1C8h+var_E8]
0x1800429ba  mov     [rsp+1C8h+newString], rax
0x1800429bf  mov     rdx, r13
0x1800429c2  lea     rcx, [rsp+1C8h+var_E8]
0x1800429ca  call    ??0?$function@$$A6AXW4Status@WebService@ConnectedStorage@@VAtom@3@@Z@std@@QEAA@AEBV01@@Z; std::function<void (ConnectedStorage::WebService::Status,ConnectedStorage::Atom)>::function<void (ConnectedStorage::WebService::Status,ConnectedStorage::Atom)>(std::function<void (ConnectedStorage::WebService::Status,ConnectedStorage::Atom)> const &)
0x1800429cf  mov     [rsp+1C8h+string], rax
0x1800429d4  mov     rdx, r15; struct ConnectedStorage::ContextDesc *
0x1800429d7  lea     rcx, [rsp+1C8h+var_118]; this
0x1800429df  call    ??0ContextDesc@ConnectedStorage@@QEAA@AEBV01@@Z; ConnectedStorage::ContextDesc::ContextDesc(ConnectedStorage::ContextDesc const &)
0x1800429e4  nop
0x1800429e5  mov     qword ptr [rsp+1C8h+var_1A0], r14
0x1800429ea  mov     [rsp+1C8h+var_1A8], edi
0x1800429ee  mov     r9, [rsp+1C8h+string]
0x1800429f3  mov     r8, [rsp+1C8h+var_148]
0x1800429fb  mov     rdx, rax
0x1800429fe  mov     rcx, rsi
0x180042a01  call    ?DownloadContainerImpl@NtmWebService@ConnectedStorage@@AEBAXVContextDesc@2@AEBVSimpleHStringWrapper@2@V?$function@$$A6AXW4Status@WebService@ConnectedStorage@@AEBVSimpleHStringWrapper@3@1@Z@std@@KV?$shared_ptr@VNtmCancelCallback@ConnectedStorage@@@6@@Z; ConnectedStorage::NtmWebService::DownloadContainerImpl(ConnectedStorage::ContextDesc,ConnectedStorage::SimpleHStringWrapper const &,std::function<void (ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &)>,ulong,std::shared_ptr<ConnectedStorage::NtmCancelCallback>)
0x180042a06  nop
0x180042a07  lea     rcx, [rsp+1C8h+var_A8]
0x180042a0f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180042a14  nop
0x180042a15  jmp     short loc_180042A2E
0x180042a17  xor     ebx, ebx
0x180042a19  mov     r15, [rsp+1C8h+var_170]
0x180042a1e  mov     r13, [rsp+1C8h+var_168]
0x180042a23  mov     r12, [rsp+1C8h+var_160]
0x180042a28  cmp     dword ptr [rsp+1C8h+newString], ebx
0x180042a2c  jl      short loc_180042A97
0x180042a2e  mov     rcx, [rsp+1C8h+var_138]; this
0x180042a36  test    rcx, rcx
0x180042a39  jz      short loc_180042A41
0x180042a3b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180042a40  nop
0x180042a41  mov     rax, [rsp+1C8h+var_150]
0x180042a46  mov     rcx, [rax+8]; this
0x180042a4a  test    rcx, rcx
0x180042a4d  jz      short loc_180042A55
0x180042a4f  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x180042a54  nop
0x180042a55  mov     rcx, r15; this
0x180042a58  call    ??1ContextDesc@ConnectedStorage@@QEAA@XZ; ConnectedStorage::ContextDesc::~ContextDesc(void)
0x180042a5d  nop
0x180042a5e  mov     rcx, r13
0x180042a61  call    ??1?$function@$$A6AJXZ@std@@QEAA@XZ; std::function<long (void)>::~function<long (void)>(void)
0x180042a66  nop
0x180042a67  mov     rcx, [r12]
0x180042a6b  test    rcx, rcx
0x180042a6e  jz      short loc_180042A81
0x180042a70  mov     [r12], rbx
0x180042a74  mov     rax, [rcx]
0x180042a77  mov     rax, [rax+10h]
0x180042a7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042a80  nop
0x180042a81  jmp     loc_180042BDD
0x180042a86  mov     r12, [rsp+1C8h+var_160]
0x180042a8b  mov     r13, [rsp+1C8h+var_168]
0x180042a90  mov     r15, [rsp+1C8h+var_170]
0x180042a95  xor     ebx, ebx
0x180042a97  mov     [rsp+1C8h+newString], rbx
0x180042a9c  mov     [rsp+1C8h+string], rbx
0x180042aa1  lea     r9, [rsp+1C8h+newString]
0x180042aa6  lea     r8, [rsp+1C8h+string]
0x180042aab  mov     edx, 1
0x180042ab0  mov     rcx, r13
0x180042ab3  call    ??R?$_Func_class@XW4Status@WebService@ConnectedStorage@@AEBVSimpleHStringWrapper@3@AEBV43@@std@@QEBAXW4Status@WebService@ConnectedStorage@@AEBVSimpleHStringWrapper@4@1@Z; std::_Func_class<void,ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &>::operator()(ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &)
0x180042ab8  nop
0x180042ab9  mov     rcx, [rsp+1C8h+string]; string
0x180042abe  call    cs:__imp_WindowsDeleteString
0x180042ac4  mov     [rsp+1C8h+string], rbx
0x180042ac9  mov     rcx, [rsp+1C8h+newString]; string
0x180042ace  call    cs:__imp_WindowsDeleteString
0x180042ad4  jmp     loc_180042B8A
0x180042ad9  mov     [rsp+1C8h+string], rbx
0x180042ade  mov     [rsp+1C8h+newString], rbx
0x180042ae3  mov     rdi, [rsp+1C8h+var_178]
0x180042ae8  cmp     [rdi+48h], rbx
0x180042aec  jz      short loc_180042B3A
0x180042aee  lea     rcx, [rsp+1C8h+string]
0x180042af3  call    ?Release@?$TaskMem@G@ConnectedStorage@@QEAAXXZ; ConnectedStorage::TaskMem<ushort>::Release(void)
0x180042af8  lea     r8, [rsp+1C8h+string]; unsigned __int16 **
0x180042afd  lea     rdx, aEtag_0; "ETag"
0x180042b04  mov     rcx, [rdi+48h]; unsigned __int16 *
0x180042b08  call    ?GetHttpHeaderFromRawHttpHeaders@@YAJPEBG0PEAPEAG@Z; GetHttpHeaderFromRawHttpHeaders(ushort const *,ushort const *,ushort * *)
0x180042b0d  test    eax, eax
0x180042b0f  js      short loc_180042B3A
0x180042b11  mov     rdx, [rsp+1C8h+string]; sourceString
0x180042b16  lea     rcx, [rsp+1C8h+var_178]; string
0x180042b1b  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@PEBG@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(ushort const *)
0x180042b20  nop
0x180042b21  mov     rdx, rax
0x180042b24  lea     rcx, [rsp+1C8h+newString]; newString
0x180042b29  call    ??4SimpleHStringWrapper@ConnectedStorage@@QEAAAEAV01@AEBV01@@Z; ConnectedStorage::SimpleHStringWrapper::operator=(ConnectedStorage::SimpleHStringWrapper const &)
0x180042b2e  nop
0x180042b2f  mov     rcx, [rsp+1C8h+var_178]; string
0x180042b34  call    cs:__imp_WindowsDeleteString
0x180042b3a  mov     rdx, [r12]
0x180042b3e  add     rdx, 10h
0x180042b42  lea     rcx, [rsp+1C8h+var_178]; string
0x180042b47  call    ?FromUtf8@ConnectedStorage@@YA?AVSimpleHStringWrapper@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; ConnectedStorage::FromUtf8(std::string const &)
0x180042b4c  nop
0x180042b4d  mov     r9, rax
0x180042b50  lea     r8, [rsp+1C8h+newString]
0x180042b55  mov     edx, 0Bh
0x180042b5a  mov     rcx, r13
0x180042b5d  call    ??R?$_Func_class@XW4Status@WebService@ConnectedStorage@@AEBVSimpleHStringWrapper@3@AEBV43@@std@@QEBAXW4Status@WebService@ConnectedStorage@@AEBVSimpleHStringWrapper@4@1@Z; std::_Func_class<void,ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &>::operator()(ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &)
0x180042b62  nop
0x180042b63  mov     rcx, [rsp+1C8h+var_178]; string
0x180042b68  call    cs:__imp_WindowsDeleteString
0x180042b6e  nop
0x180042b6f  mov     rcx, [rsp+1C8h+newString]; string
0x180042b74  call    cs:__imp_WindowsDeleteString
0x180042b7a  mov     [rsp+1C8h+newString], rbx
0x180042b7f  lea     rcx, [rsp+1C8h+string]
0x180042b84  call    ?Release@?$TaskMem@G@ConnectedStorage@@QEAAXXZ; ConnectedStorage::TaskMem<ushort>::Release(void)
0x180042b89  nop
0x180042b8a  mov     rcx, [rsp+1C8h+var_138]; this
0x180042b92  test    rcx, rcx
0x180042b95  jz      short loc_180042B9D
0x180042b97  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180042b9c  nop
0x180042b9d  mov     rax, [rsp+1C8h+var_150]
0x180042ba2  mov     rcx, [rax+8]; this
0x180042ba6  test    rcx, rcx
0x180042ba9  jz      short loc_180042BB1
0x180042bab  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x180042bb0  nop
0x180042bb1  mov     rcx, r15; this
0x180042bb4  call    ??1ContextDesc@ConnectedStorage@@QEAA@XZ; ConnectedStorage::ContextDesc::~ContextDesc(void)
0x180042bb9  nop
0x180042bba  mov     rcx, r13
0x180042bbd  call    ??1?$function@$$A6AJXZ@std@@QEAA@XZ; std::function<long (void)>::~function<long (void)>(void)
0x180042bc2  nop
0x180042bc3  mov     rcx, [r12]
0x180042bc7  test    rcx, rcx
0x180042bca  jz      short loc_180042BDD
0x180042bcc  mov     [r12], rbx
0x180042bd0  mov     rax, [rcx]
0x180042bd3  mov     rax, [rax+10h]
0x180042bd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042bdc  nop
0x180042bdd  mov     rax, [rsp+1C8h+var_158]
0x180042be2  mov     rcx, [rax+8]; this
0x180042be6  test    rcx, rcx
0x180042be9  jz      short loc_180042BF0
0x180042beb  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180042bf0  mov     rcx, [rsp+1C8h+var_48]
0x180042bf8  xor     rcx, rsp; StackCookie
0x180042bfb  call    __security_check_cookie
0x180042c00  add     rsp, 190h
0x180042c07  pop     r15
0x180042c09  pop     r14
0x180042c0b  pop     r13
0x180042c0d  pop     r12
0x180042c0f  pop     rdi
0x180042c10  pop     rsi
0x180042c11  pop     rbx
0x180042c12  retn
```
