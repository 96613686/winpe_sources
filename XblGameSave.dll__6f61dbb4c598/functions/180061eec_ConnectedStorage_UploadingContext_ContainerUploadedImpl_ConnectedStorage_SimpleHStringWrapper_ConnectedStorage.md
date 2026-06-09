# ConnectedStorage::UploadingContext::ContainerUploadedImpl(ConnectedStorage::SimpleHStringWrapper,ConnectedStorage::SimpleHStringWrapper,bool)

- ea: `0x180061eec`
- end: `0x1800620e2`
- name: `?ContainerUploadedImpl@UploadingContext@ConnectedStorage@@AEAAXVSimpleHStringWrapper@2@0_N@Z`
- size: `502`
- prototype: `void __high(struct ConnectedStorage::SimpleHStringWrapper, struct ConnectedStorage::SimpleHStringWrapper, bool)`
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, installer_update`

## callers

- `0x1800614c8`

## callees

- `0x180003c70`
- `0x18000aae4`
- `0x18000b67c`
- `0x18000cb9c`
- `0x18000d2f4`
- `0x180012278`
- `0x180012f7c`
- `0x180012ff8`
- `0x18001ca7c`
- `0x180061eec`
- `0x18006268c`
- `0x180065924`
- `0x18006b8f8`
- `0x180076f34`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180062095`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180062095`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006209f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800620af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006209f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800620af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180061f5e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180061fac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180061fba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180061f5e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180061fac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180061fba`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18006203b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180062048`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18006203b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180062048`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
HRESULT __fastcall ConnectedStorage::UploadingContext::ContainerUploadedImpl(
        __int64 a1,
        struct _RTL_CRITICAL_SECTION *a2,
        struct _RTL_CRITICAL_SECTION *a3,
        bool a4)
{
  ConnectedStorage::Container **v8; // r14
  PCWSTR StringRawBuffer; // rax
  const unsigned __int16 *v10; // r8
  PCWSTR v11; // rbx
  PCWSTR v12; // rax
  const unsigned __int16 *v13; // r8
  ConnectedStorage::ContainerIndex *v14; // rax
  HRESULT result; // eax
  struct ConnectedStorage::MultiFileWrite *v16[2]; // [rsp+30h] [rbp-D0h] BYREF
  LPCRITICAL_SECTION lpCriticalSection[4]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 v18[1024]; // [rsp+60h] [rbp-A0h] BYREF

  lpCriticalSection[2] = a2;
  lpCriticalSection[3] = a3;
  ConnectedStorage::Mutex::Lock::Lock(
    (ConnectedStorage::Mutex::Lock *)lpCriticalSection,
    (struct _RTL_CRITICAL_SECTION *)(a1 + 168),
    (char *)a3);
  ++*(_DWORD *)(a1 + 336);
  v8 = (ConnectedStorage::Container **)(a1 + 304);
  if ( !(unsigned __int8)std::shared_ptr<ConnectedStorage::WebService>::operator bool(a1 + 304) )
  {
    StringRawBuffer = WindowsGetStringRawBuffer((HSTRING)a2->DebugInfo, 0);
    StringCchPrintfW(
      v18,
      0x400u,
      L"UploadingContext - ContainerUploaded %s, but not expecting any upload",
      StringRawBuffer);
    ConnectedStorage::ReportErrorAndThrow((ConnectedStorage *)0x8000FFFFLL, (int)v18, v10);
  }
  if ( !(unsigned __int8)ConnectedStorage::SimpleHStringWrapper::operator==(a2, *((_QWORD *)*v8 + 6)) )
  {
    v11 = WindowsGetStringRawBuffer(**((HSTRING **)*v8 + 6), 0);
    v12 = WindowsGetStringRawBuffer((HSTRING)a2->DebugInfo, 0);
    StringCchPrintfW(v18, 0x400u, L"UploadingContext - ContainerUploaded %s, but expected %s", v12, v11);
    ConnectedStorage::ReportErrorAndThrow((ConnectedStorage *)0x8000FFFFLL, (int)v18, v13);
  }
  ConnectedStorage::MultiFileWrite::Create(v16);
  ConnectedStorage::Container::UpdateAfterUpload(
    *v8,
    v16[0],
    (const struct ConnectedStorage::SimpleHStringWrapper *)a3,
    a4);
  v14 = (ConnectedStorage::ContainerIndex *)std::shared_ptr<ConnectedStorage::UploadingContext const>::operator-><ConnectedStorage::UploadingContext const,0>(a1 + 288);
  ConnectedStorage::ContainerIndex::SaveAfterContainerUpdate(v14, v16[0], 0, *((_QWORD *)*v8 + 6));
  *(_QWORD *)(a1 + 392) = GetTickCount64();
  *(_QWORD *)(a1 + 368) = GetTickCount64();
  std::shared_ptr<ConnectedStorage::File>::reset(a1 + 304);
  if ( *(_DWORD *)(a1 + 216) != 8 )
  {
    ++*(_DWORD *)(a1 + 340);
    ConnectedStorage::UploadingContext::TransitionToState(a1);
  }
  std::shared_ptr<std::vector<ConnectedStorage::ContainerQueryInfoWrapper>>::~shared_ptr<std::vector<ConnectedStorage::ContainerQueryInfoWrapper>>(v16);
  LeaveCriticalSection(lpCriticalSection[0]);
  WindowsDeleteString((HSTRING)a2->DebugInfo);
  a2->DebugInfo = 0;
  result = WindowsDeleteString((HSTRING)a3->DebugInfo);
  a3->DebugInfo = 0;
  return result;
}

```

## disassembly

```asm
0x180061eec  mov     [rsp-8+arg_18], rbx
0x180061ef1  push    rbp
0x180061ef2  push    rsi
0x180061ef3  push    rdi
0x180061ef4  push    r14
0x180061ef6  push    r15
0x180061ef8  lea     rbp, [rsp-770h]
0x180061f00  sub     rsp, 870h
0x180061f07  mov     rax, cs:__security_cookie
0x180061f0e  xor     rax, rsp
0x180061f11  mov     [rbp+790h+var_30], rax
0x180061f18  mov     r15b, r9b
0x180061f1b  mov     rsi, r8
0x180061f1e  mov     rdi, rdx
0x180061f21  mov     rbx, rcx
0x180061f24  mov     [rsp+890h+var_840], rdx
0x180061f29  mov     [rsp+890h+var_838], r8
0x180061f2e  lea     rdx, [rcx+0A8h]; struct ConnectedStorage::Mutex *
0x180061f35  lea     rcx, [rsp+890h+lpCriticalSection]; this
0x180061f3a  call    ??0Lock@Mutex@ConnectedStorage@@QEAA@AEAV12@PEAD@Z; ConnectedStorage::Mutex::Lock::Lock(ConnectedStorage::Mutex &,char *)
0x180061f3f  nop
0x180061f40  inc     dword ptr [rbx+150h]
0x180061f46  lea     r14, [rbx+130h]
0x180061f4d  mov     rcx, r14
0x180061f50  call    ??B?$shared_ptr@VWebService@ConnectedStorage@@@std@@QEBA_NXZ; std::shared_ptr<ConnectedStorage::WebService>::operator bool(void)
0x180061f55  test    al, al
0x180061f57  jnz     short loc_180061F8D
0x180061f59  xor     edx, edx; length
0x180061f5b  mov     rcx, [rdi]; string
0x180061f5e  call    cs:__imp_WindowsGetStringRawBuffer
0x180061f64  mov     r9, rax
0x180061f67  lea     r8, aUploadingconte; "UploadingContext - ContainerUploaded %s"...
0x180061f6e  mov     edx, 400h; unsigned __int64
0x180061f73  lea     rcx, [rsp+890h+var_830]; unsigned __int16 *
0x180061f78  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180061f7d  lea     rdx, [rsp+890h+var_830]; int
0x180061f82  mov     ecx, 8000FFFFh; this
0x180061f87  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x180061f8d  mov     rdx, [r14]
0x180061f90  mov     rdx, [rdx+30h]
0x180061f94  mov     rcx, rdi
0x180061f97  call    ??8SimpleHStringWrapper@ConnectedStorage@@QEBA_NAEBV01@@Z; ConnectedStorage::SimpleHStringWrapper::operator==(ConnectedStorage::SimpleHStringWrapper const &)
0x180061f9c  test    al, al
0x180061f9e  jnz     short loc_180061FEE
0x180061fa0  mov     rax, [r14]
0x180061fa3  mov     rcx, [rax+30h]
0x180061fa7  xor     edx, edx; length
0x180061fa9  mov     rcx, [rcx]; string
0x180061fac  call    cs:__imp_WindowsGetStringRawBuffer
0x180061fb2  mov     rbx, rax
0x180061fb5  xor     edx, edx; length
0x180061fb7  mov     rcx, [rdi]; string
0x180061fba  call    cs:__imp_WindowsGetStringRawBuffer
0x180061fc0  mov     [rsp+890h+var_870], rbx
0x180061fc5  mov     r9, rax
0x180061fc8  lea     r8, aUploadingconte_1; "UploadingContext - ContainerUploaded %s"...
0x180061fcf  mov     edx, 400h; unsigned __int64
0x180061fd4  lea     rcx, [rsp+890h+var_830]; unsigned __int16 *
0x180061fd9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180061fde  lea     rdx, [rsp+890h+var_830]; int
0x180061fe3  mov     ecx, 8000FFFFh; this
0x180061fe8  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x180061fee  lea     rcx, [rsp+890h+var_860]
0x180061ff3  call    ?Create@MultiFileWrite@ConnectedStorage@@SA?AV?$shared_ptr@VMultiFileWrite@ConnectedStorage@@@std@@XZ; ConnectedStorage::MultiFileWrite::Create(void)
0x180061ff8  nop
0x180061ff9  mov     r9b, r15b; bool
0x180061ffc  mov     r8, rsi; struct ConnectedStorage::SimpleHStringWrapper *
0x180061fff  mov     rdx, [rsp+890h+var_860]; struct ConnectedStorage::MultiFileWrite *
0x180062004  mov     rcx, [r14]; this
0x180062007  call    ?UpdateAfterUpload@Container@ConnectedStorage@@QEAAXPEAVMultiFileWrite@2@AEBVSimpleHStringWrapper@2@_N@Z; ConnectedStorage::Container::UpdateAfterUpload(ConnectedStorage::MultiFileWrite *,ConnectedStorage::SimpleHStringWrapper const &,bool)
0x18006200c  lea     rcx, [rbx+120h]
0x180062013  call    ??$?C$$CBVUploadingContext@ConnectedStorage@@$0A@@?$shared_ptr@$$CBVUploadingContext@ConnectedStorage@@@std@@QEBAPEBVUploadingContext@ConnectedStorage@@XZ; std::shared_ptr<ConnectedStorage::UploadingContext const>::operator-><ConnectedStorage::UploadingContext const,0>(void)
0x180062018  mov     rcx, [r14]
0x18006201b  lea     r9, [rbx+100h]
0x180062022  mov     rcx, [rcx+30h]
0x180062026  mov     [rsp+890h+var_870], rcx; __int64
0x18006202b  xor     r8d, r8d; struct ConnectedStorage::CallerInfo *
0x18006202e  mov     rdx, [rsp+890h+var_860]; ConnectedStorage::MultiFileWrite *
0x180062033  mov     rcx, rax; this
0x180062036  call    ?SaveAfterContainerUpdate@ContainerIndex@ConnectedStorage@@QEBAXPEAVMultiFileWrite@2@PEBVCallerInfo@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBVContainerIndexEntry@2@@Z; ConnectedStorage::ContainerIndex::SaveAfterContainerUpdate(ConnectedStorage::MultiFileWrite *,ConnectedStorage::CallerInfo const *,std::wstring const &,ConnectedStorage::ContainerIndexEntry const *)
0x18006203b  call    cs:__imp_GetTickCount64
0x180062041  mov     [rbx+188h], rax
0x180062048  call    cs:__imp_GetTickCount64
0x18006204e  mov     [rbx+170h], rax
0x180062055  mov     rcx, r14
0x180062058  call    ?reset@?$shared_ptr@VFile@ConnectedStorage@@@std@@QEAAXXZ; std::shared_ptr<ConnectedStorage::File>::reset(void)
0x18006205d  mov     eax, [rbx+0D8h]
0x180062063  mov     edx, 8
0x180062068  cmp     eax, edx
0x18006206a  jz      short loc_180062085
0x18006206c  inc     dword ptr [rbx+154h]
0x180062072  mov     rcx, rbx
0x180062075  cmp     eax, 9
0x180062078  jz      short loc_18006207F
0x18006207a  mov     edx, 5
0x18006207f  call    ?TransitionToState@UploadingContext@ConnectedStorage@@AEBAXW4State@12@@Z; ConnectedStorage::UploadingContext::TransitionToState(ConnectedStorage::UploadingContext::State)
0x180062084  nop
0x180062085  lea     rcx, [rsp+890h+var_860]
0x18006208a  call    ??1?$shared_ptr@V?$vector@VContainerQueryInfoWrapper@ConnectedStorage@@V?$allocator@VContainerQueryInfoWrapper@ConnectedStorage@@@std@@@std@@@std@@QEAA@XZ; std::shared_ptr<std::vector<ConnectedStorage::ContainerQueryInfoWrapper>>::~shared_ptr<std::vector<ConnectedStorage::ContainerQueryInfoWrapper>>(void)
0x18006208f  nop
0x180062090  mov     rcx, [rsp+890h+lpCriticalSection]; lpCriticalSection
0x180062095  call    cs:__imp_LeaveCriticalSection
0x18006209b  nop
0x18006209c  mov     rcx, [rdi]; string
0x18006209f  call    cs:__imp_WindowsDeleteString
0x1800620a5  mov     qword ptr [rdi], 0
0x1800620ac  mov     rcx, [rsi]; string
0x1800620af  call    cs:__imp_WindowsDeleteString
0x1800620b5  mov     qword ptr [rsi], 0
0x1800620bc  mov     rcx, [rbp+790h+var_30]
0x1800620c3  xor     rcx, rsp; StackCookie
0x1800620c6  call    __security_check_cookie
0x1800620cb  mov     rbx, [rsp+890h+arg_18]
0x1800620d3  add     rsp, 870h
0x1800620da  pop     r15
0x1800620dc  pop     r14
0x1800620de  pop     rdi
0x1800620df  pop     rsi
0x1800620e0  pop     rbp
0x1800620e1  retn
```
