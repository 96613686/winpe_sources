# ConnectedStorage::NtmWebService::DownloadAtomImpl(ConnectedStorage::ContextDesc,_GUID,ulong,Microsoft::WRL::ComPtr<ConnectedStorage::AtomDownloadStream>,std::shared_ptr<ConnectedStorage::NtmCancelCallback>,bool,std::function<void (ConnectedStorage::WebService::Status,ConnectedStorage::Atom)>)

- ea: `0x18004208c`
- end: `0x180042581`
- name: `?DownloadAtomImpl@NtmWebService@ConnectedStorage@@AEBAXVContextDesc@2@U_GUID@@KV?$ComPtr@VAtomDownloadStream@ConnectedStorage@@@WRL@Microsoft@@V?$shared_ptr@VNtmCancelCallback@ConnectedStorage@@@std@@_NV?$function@$$A6AXW4Status@WebService@ConnectedStorage@@VAtom@3@@Z@9@@Z`
- size: `1269`
- prototype: ``
- caller_count: `2`
- callee_count: `27`
- tags: `service_task, broker_com_uri`

## callers

- `0x180040da8`
- `0x180041e40`

## callees

- `0x180003c70`
- `0x18000a040`
- `0x18000c218`
- `0x18000cb9c`
- `0x18000cd1c`
- `0x18000d6bc`
- `0x180011c68`
- `0x1800125ec`
- `0x1800190f0`
- `0x180019128`
- `0x18001c090`
- `0x18001c618`
- `0x18001e504`
- `0x1800271ac`
- `0x180039534`
- `0x18003a278`
- `0x18003d474`
- `0x18003e688`
- `0x18003ee9c`
- `0x18003f0fc`
- `0x18004208c`
- `0x180043580`
- `0x180043758`
- `0x1800449b0`
- `0x180048720`
- `0x18006972c`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004219a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180042519`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004219a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180042519`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004252f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004252f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800423b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800423c8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800423b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800423c8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180042498`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800424a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180042498`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800424a7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800421a5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800421a5`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
__int64 __fastcall ConnectedStorage::NtmWebService::DownloadAtomImpl(
        __int64 a1,
        HSTRING *a2,
        unsigned __int16 *a3,
        unsigned int a4,
        ConnectedStorage::AtomDownloadStream **a5,
        ConnectedStorage::NtmCancelCallback **a6,
        __int64 a7,
        __int64 a8)
{
  HSTRING *v8; // rsi
  ConnectedStorage::AtomDownloadStream **v10; // r14
  ConnectedStorage::NtmCancelCallback **v11; // r15
  __int64 v12; // r12
  __int64 v13; // rax
  struct ConnectedStorage::Mutex *v14; // r13
  char *v15; // r8
  __int64 v16; // rax
  ULONGLONG TickCount64; // rax
  _QWORD *v18; // rbx
  __int64 v19; // rax
  HSTRING *v20; // r13
  HSTRING *v21; // rax
  char *v22; // r8
  const unsigned __int16 *StringRawBuffer; // rbx
  ConnectedStorage *v24; // rax
  __int64 v25; // rax
  std::_Ref_count_base *v26; // rcx
  int v28; // [rsp+28h] [rbp-2C0h]
  unsigned int v29; // [rsp+50h] [rbp-298h] BYREF
  HSTRING v30; // [rsp+58h] [rbp-290h] BYREF
  _QWORD v31[2]; // [rsp+60h] [rbp-288h] BYREF
  struct _GUID v32; // [rsp+70h] [rbp-278h] BYREF
  HSTRING string; // [rsp+80h] [rbp-268h] BYREF
  HSTRING *v34; // [rsp+88h] [rbp-260h]
  ConnectedStorage::AtomDownloadStream **v35; // [rsp+90h] [rbp-258h]
  __int64 v36; // [rsp+98h] [rbp-250h]
  ConnectedStorage::NtmCancelCallback **v37; // [rsp+A0h] [rbp-248h]
  __int64 v38; // [rsp+A8h] [rbp-240h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+B0h] [rbp-238h] BYREF
  std::_Ref_count_base *v40; // [rsp+B8h] [rbp-230h]
  struct ConnectedStorage::Mutex *v41; // [rsp+C0h] [rbp-228h]
  LPCRITICAL_SECTION v42[3]; // [rsp+C8h] [rbp-220h] BYREF
  unsigned __int16 *v43; // [rsp+E0h] [rbp-208h]
  HSTRING__ v44[8]; // [rsp+F0h] [rbp-1F8h] BYREF
  LPCRITICAL_SECTION v45[2]; // [rsp+110h] [rbp-1D8h] BYREF
  unsigned __int16 Src[16]; // [rsp+120h] [rbp-1C8h] BYREF
  _QWORD v47[3]; // [rsp+140h] [rbp-1A8h] BYREF
  _BYTE v48[56]; // [rsp+160h] [rbp-188h] BYREF
  __int64 v49; // [rsp+198h] [rbp-150h]
  _DWORD v50[16]; // [rsp+1A0h] [rbp-148h] BYREF
  int v51[48]; // [rsp+1E0h] [rbp-108h] BYREF

  v30 = (HSTRING)a3;
  v8 = a2;
  v34 = a2;
  v43 = a3;
  v29 = a4;
  v10 = a5;
  v35 = a5;
  v11 = a6;
  v37 = a6;
  v12 = a8;
  v36 = a8;
  if ( !*(_BYTE *)(a1 + 25) && !*(_BYTE *)(a1 + 24) )
  {
    ConnectedStorage::AtomDownloadStream::Abandon(*a5);
    v13 = ConnectedStorage::Atom::Atom((ConnectedStorage::Atom *)v44);
    std::_Func_class<void,enum ConnectedStorage::WebService::Status,ConnectedStorage::Atom>::operator()(v12, 1, v13);
    goto LABEL_17;
  }
  v14 = (struct ConnectedStorage::Mutex *)(a1 + 40);
  v41 = (struct ConnectedStorage::Mutex *)(a1 + 40);
  ConnectedStorage::Mutex::Lock::Lock(
    (ConnectedStorage::Mutex::Lock *)v42,
    (struct _RTL_CRITICAL_SECTION *)(a1 + 40),
    (char *)a3);
  if ( *(_QWORD *)(a1 + 88) )
  {
    TickCount64 = GetTickCount64();
    try
    {
      v38 = TickCount64;
      ConnectedStorage::GuidToString(v47, v30);
      ConnectedStorage::MakeUrl(Src, v8);
      std::wstring::end(v47, &v32);
      std::wstring::_Append<unsigned short>(Src);
      std::wstring::_Append<unsigned short>(Src);
      ConnectedStorage::NtmWebService::MakeHeadersWithContext(a1, v44, Src, v8);
      if ( (_BYTE)a7 )
        std::wstring::_Append<unsigned short>(v44);
      ConnectedStorage::NtmWebService::weak_from_this(a1, &lpCriticalSection);
      v18 = *(_QWORD **)(a1 + 88);
      *(_QWORD *)&v32.Data1 = *v18;
      v19 = lambda_c7fb734662817d6bb866d06e21590e22_::_lambda_c7fb734662817d6bb866d06e21590e22__1(
              (int)v51,
              (int)&lpCriticalSection,
              (int)a5,
              v12,
              (struct ConnectedStorage::ContextDesc *)v8,
              (__int64)v30,
              (__int64)&v38,
              (__int64)a6,
              (__int64)&v29,
              (__int64)&a7);
      v49 = 0;
      v49 = std::_Global_new_std::_Func_impl_no_alloc__lambda_c7fb734662817d6bb866d06e21590e22__void__NTM_TRANSFER_STATUS_const___unsigned_int_long___lambda_c7fb734662817d6bb866d06e21590e22___(v19);
      *(_QWORD *)&v32.Data1 = *(_QWORD *)(*(_QWORD *)&v32.Data1 + 8LL);
      v38 = (__int64)v31;
      v31[0] = *a5;
      Microsoft::WRL::ComPtr<ConnectedStorage::AtomDownloadStream>::InternalAddRef(v31);
      v20 = ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&v30, (__int64)v44);
      v21 = ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&string, (__int64)Src);
      LOWORD(v28) = 30;
      (*(void (__fastcall **)(_QWORD *, LPCRITICAL_SECTION *, HSTRING *, __int64, _DWORD, int, HSTRING *))&v32.Data1)(
        v18,
        v45,
        v21,
        2,
        0,
        v28,
        v20);
      WindowsDeleteString(string);
      string = 0;
      WindowsDeleteString(v30);
      v30 = 0;
      std::function<long (void)>::~function<long (void)>(v48);
      lambda_c7fb734662817d6bb866d06e21590e22_::__lambda_c7fb734662817d6bb866d06e21590e22_(v51);
      v32 = *(struct _GUID *)v45;
      ConnectedStorage::NtmCancelCallback::ReplaceCompletedTransfer(*a6, &v32);
      if ( v40 )
        std::_Ref_count_base::_Decwref(v40);
      std::wstring::_Tidy_deallocate(v44);
      std::wstring::_Tidy_deallocate(Src);
      std::wstring::_Tidy_deallocate(v47);
    }
    catch ( ConnectedStorage::ComError v50 )
    {
      v29 = v50[6];
      ConnectedStorage::ComError::~ComError((ConnectedStorage::ComError *)v50);
      if ( (v29 & 0x80000000) != 0 )
      {
LABEL_14:
        ConnectedStorage::Mutex::Unlock::Unlock((ConnectedStorage::Mutex::Unlock *)v45, v41, v22);
        v8 = v34;
        StringRawBuffer = WindowsGetStringRawBuffer(v34[2], 0);
        v24 = (ConnectedStorage *)WindowsGetStringRawBuffer(v8[3], 0);
        ConnectedStorage::EventWriteWebDownloadAtom(v24, StringRawBuffer, v43, 0, 0, v29, 0, (unsigned int)v31);
        v10 = v35;
        ConnectedStorage::AtomDownloadStream::Abandon(*v35);
        v25 = ConnectedStorage::Atom::Atom((ConnectedStorage::Atom *)v44);
        v12 = v36;
        std::_Func_class<void,enum ConnectedStorage::WebService::Status,ConnectedStorage::Atom>::operator()(v36, 1, v25);
        EnterCriticalSection(v45[0]);
      }
      else
      {
        v8 = v34;
        v10 = v35;
        v12 = v36;
      }
      v11 = v37;
    }
    catch ( std::bad_alloc )
    {
      v29 = -2147024882;
      goto LABEL_14;
    }
    catch ( ... )
    {
      v29 = -2147467259;
      goto LABEL_14;
    }
  }
  else
  {
    ConnectedStorage::Mutex::Unlock::Unlock((ConnectedStorage::Mutex::Unlock *)&lpCriticalSection, v14, v15);
    ConnectedStorage::AtomDownloadStream::Abandon(*a5);
    v16 = ConnectedStorage::Atom::Atom((ConnectedStorage::Atom *)v44);
    std::_Func_class<void,enum ConnectedStorage::WebService::Status,ConnectedStorage::Atom>::operator()(v12, 1, v16);
    EnterCriticalSection(lpCriticalSection);
  }
  LeaveCriticalSection(v42[0]);
LABEL_17:
  ConnectedStorage::ContextDesc::~ContextDesc(v8);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v10);
  v26 = v11[1];
  if ( v26 )
    std::_Ref_count_base::_Decref(v26);
  return std::function<long (void)>::~function<long (void)>(v12);
}

```

## disassembly

```asm
0x18004208c  mov     r11, rsp
0x18004208f  push    rbx
0x180042090  push    rsi
0x180042091  push    r12
0x180042093  push    r13
0x180042095  push    r14
0x180042097  push    r15
0x180042099  sub     rsp, 2B8h
0x1800420a0  mov     rax, cs:__security_cookie
0x1800420a7  xor     rax, rsp
0x1800420aa  mov     [rsp+2E8h+var_48], rax
0x1800420b2  mov     rax, r8
0x1800420b5  mov     [rsp+2E8h+var_290], rax
0x1800420ba  mov     rsi, rdx
0x1800420bd  mov     rbx, rcx
0x1800420c0  mov     [r11-260h], rdx
0x1800420c7  mov     [rsp+2E8h+var_208], rax
0x1800420cf  mov     [rsp+2E8h+var_298], r9d
0x1800420d4  mov     r14, [rsp+2E8h+arg_20]
0x1800420dc  mov     [r11-258h], r14
0x1800420e3  mov     r15, [rsp+2E8h+arg_28]
0x1800420eb  mov     [r11-248h], r15
0x1800420f2  mov     r12, [rsp+2E8h+arg_38]
0x1800420fa  mov     [r11-250h], r12
0x180042101  cmp     byte ptr [rcx+19h], 0
0x180042105  jnz     short loc_180042137
0x180042107  cmp     byte ptr [rcx+18h], 0
0x18004210b  jnz     short loc_180042137
0x18004210d  mov     rcx, [r14]; this
0x180042110  call    ?Abandon@AtomDownloadStream@ConnectedStorage@@QEBAXXZ; ConnectedStorage::AtomDownloadStream::Abandon(void)
0x180042115  lea     rcx, [rsp+2E8h+var_1F8]; this
0x18004211d  call    ??0Atom@ConnectedStorage@@QEAA@XZ; ConnectedStorage::Atom::Atom(void)
0x180042122  mov     r8, rax
0x180042125  mov     edx, 1
0x18004212a  mov     rcx, r12
0x18004212d  call    ??R?$_Func_class@XW4Status@WebService@ConnectedStorage@@VAtom@3@@std@@QEBAXW4Status@WebService@ConnectedStorage@@VAtom@4@@Z; std::_Func_class<void,ConnectedStorage::WebService::Status,ConnectedStorage::Atom>::operator()(ConnectedStorage::WebService::Status,ConnectedStorage::Atom)
0x180042132  jmp     loc_180042536
0x180042137  lea     r13, [rcx+28h]
0x18004213b  mov     [rsp+2E8h+var_228], r13
0x180042143  mov     rdx, r13; struct ConnectedStorage::Mutex *
0x180042146  lea     rcx, [rsp+2E8h+var_220]; this
0x18004214e  call    ??0Lock@Mutex@ConnectedStorage@@QEAA@AEAV12@PEAD@Z; ConnectedStorage::Mutex::Lock::Lock(ConnectedStorage::Mutex &,char *)
0x180042153  nop
0x180042154  cmp     qword ptr [rbx+58h], 0
0x180042159  jnz     short loc_1800421A5
0x18004215b  mov     rdx, r13; struct ConnectedStorage::Mutex *
0x18004215e  lea     rcx, [rsp+2E8h+lpCriticalSection]; this
0x180042166  call    ??0Unlock@Mutex@ConnectedStorage@@QEAA@AEAV12@PEAD@Z; ConnectedStorage::Mutex::Unlock::Unlock(ConnectedStorage::Mutex &,char *)
0x18004216b  nop
0x18004216c  mov     rcx, [r14]; this
0x18004216f  call    ?Abandon@AtomDownloadStream@ConnectedStorage@@QEBAXXZ; ConnectedStorage::AtomDownloadStream::Abandon(void)
0x180042174  lea     rcx, [rsp+2E8h+var_1F8]; this
0x18004217c  call    ??0Atom@ConnectedStorage@@QEAA@XZ; ConnectedStorage::Atom::Atom(void)
0x180042181  mov     r8, rax
0x180042184  mov     edx, 1
0x180042189  mov     rcx, r12
0x18004218c  call    ??R?$_Func_class@XW4Status@WebService@ConnectedStorage@@VAtom@3@@std@@QEBAXW4Status@WebService@ConnectedStorage@@VAtom@4@@Z; std::_Func_class<void,ConnectedStorage::WebService::Status,ConnectedStorage::Atom>::operator()(ConnectedStorage::WebService::Status,ConnectedStorage::Atom)
0x180042191  nop
0x180042192  mov     rcx, [rsp+2E8h+lpCriticalSection]; lpCriticalSection
0x18004219a  call    cs:__imp_EnterCriticalSection
0x1800421a0  jmp     loc_180042527
0x1800421a5  call    cs:__imp_GetTickCount64
0x1800421ab  mov     [rsp+2E8h+var_240], rax
0x1800421b3  mov     r13, [rsp+2E8h+var_290]
0x1800421b8  mov     rdx, r13
0x1800421bb  lea     rcx, [rsp+2E8h+var_1A8]
0x1800421c3  call    ?GuidToString@ConnectedStorage@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@@Z; ConnectedStorage::GuidToString(_GUID const &)
0x1800421c8  nop
0x1800421c9  mov     rdx, rsi
0x1800421cc  lea     rcx, [rsp+2E8h+Src]
0x1800421d4  call    ?MakeUrl@ConnectedStorage@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBVContextDesc@1@@Z; ConnectedStorage::MakeUrl(ConnectedStorage::ContextDesc const &)
0x1800421d9  nop
0x1800421da  lea     rdx, [rsp+2E8h+var_278]
0x1800421df  lea     rcx, [rsp+2E8h+var_1A8]
0x1800421e7  call    ?end@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@XZ; std::wstring::end(void)
0x1800421ec  mov     r8, [rax]
0x1800421ef  add     r8, 0FFFFFFFFFFFFFFFEh
0x1800421f3  lea     rdx, [rsp+2E8h+var_1A8]
0x1800421fb  cmp     [rsp+2E8h+var_190], 7
0x180042204  cmova   rdx, [rsp+2E8h+var_1A8]
0x18004220d  add     rdx, 2
0x180042211  sub     r8, rdx
0x180042214  sar     r8, 1
0x180042217  lea     rcx, [rsp+2E8h+Src]; Src
0x18004221f  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180042224  mov     r8d, 7
0x18004222a  lea     rdx, aBinary; ",binary"
0x180042231  lea     rcx, [rsp+2E8h+Src]; Src
0x180042239  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18004223e  mov     r9, rsi
0x180042241  lea     r8, [rsp+2E8h+Src]
0x180042249  lea     rdx, [rsp+2E8h+var_1F8]
0x180042251  mov     rcx, rbx
0x180042254  call    ?MakeHeadersWithContext@NtmWebService@ConnectedStorage@@AEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV34@AEBVContextDesc@2@@Z; ConnectedStorage::NtmWebService::MakeHeadersWithContext(std::wstring const &,ConnectedStorage::ContextDesc const &)
0x180042259  nop
0x18004225a  cmp     byte ptr [rsp+2E8h+arg_30], 0
0x180042262  jz      short loc_18004227E
0x180042264  mov     r8d, 17h
0x18004226a  lea     rdx, aAcceptEncoding; "Accept-Encoding: gzip\r\n"
0x180042271  lea     rcx, [rsp+2E8h+var_1F8]; Src
0x180042279  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18004227e  lea     rdx, [rsp+2E8h+lpCriticalSection]
0x180042286  mov     rcx, rbx
0x180042289  call    ?weak_from_this@NtmWebService@ConnectedStorage@@AEBA?AV?$weak_ptr@$$CBVNtmWebService@ConnectedStorage@@@std@@XZ; ConnectedStorage::NtmWebService::weak_from_this(void)
0x18004228e  nop
0x18004228f  mov     rbx, [rbx+58h]
0x180042293  mov     rax, [rbx]
0x180042296  mov     qword ptr [rsp+2E8h+var_278.Data1], rax
0x18004229b  lea     rcx, [rsp+2E8h+arg_30]
0x1800422a3  mov     [rsp+2E8h+var_2A0], rcx; __int64
0x1800422a8  lea     rax, [rsp+2E8h+var_298]
0x1800422ad  mov     [rsp+2E8h+var_2A8], rax; __int64
0x1800422b2  mov     [rsp+2E8h+var_2B0], r15; __int64
0x1800422b7  lea     rax, [rsp+2E8h+var_240]
0x1800422bf  mov     qword ptr [rsp+2E8h+var_2B8], rax; __int64
0x1800422c4  mov     qword ptr [rsp+2E8h+var_2C0], r13; __int64
0x1800422c9  mov     [rsp+2E8h+var_2C8], rsi; struct ConnectedStorage::ContextDesc *
0x1800422ce  mov     r9, r12; int
0x1800422d1  mov     r8, r14; int
0x1800422d4  lea     rdx, [rsp+2E8h+lpCriticalSection]; int
0x1800422dc  lea     rcx, [rsp+2E8h+var_108]; int
0x1800422e4  call    _lambda_c7fb734662817d6bb866d06e21590e22____lambda_c7fb734662817d6bb866d06e21590e22__1
0x1800422e9  nop
0x1800422ea  mov     [rsp+2E8h+var_150], 0
0x1800422f6  mov     rcx, rax
0x1800422f9  call    std___Global_new_std___Func_impl_no_alloc__lambda_c7fb734662817d6bb866d06e21590e22__void__NTM_TRANSFER_STATUS_const___unsigned_int_long___lambda_c7fb734662817d6bb866d06e21590e22___
0x1800422fe  mov     [rsp+2E8h+var_150], rax
0x180042306  mov     rax, qword ptr [rsp+2E8h+var_278.Data1]
0x18004230b  mov     rax, [rax+8]
0x18004230f  mov     qword ptr [rsp+2E8h+var_278.Data1], rax
0x180042314  lea     rcx, [rsp+2E8h+var_288]
0x180042319  mov     [rsp+2E8h+var_240], rcx
0x180042321  mov     rax, [r14]
0x180042324  mov     [rsp+2E8h+var_288], rax
0x180042329  lea     rcx, [rsp+2E8h+var_288]
0x18004232e  call    ?InternalAddRef@?$ComPtr@VAtomDownloadStream@ConnectedStorage@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<ConnectedStorage::AtomDownloadStream>::InternalAddRef(void)
0x180042333  nop
0x180042334  lea     rdx, [rsp+2E8h+var_1F8]
0x18004233c  lea     rcx, [rsp+2E8h+var_290]; string
0x180042341  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(std::wstring const &)
0x180042346  mov     r13, rax
0x180042349  lea     rdx, [rsp+2E8h+Src]
0x180042351  lea     rcx, [rsp+2E8h+string]; string
0x180042359  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(std::wstring const &)
0x18004235e  nop
0x18004235f  lea     rcx, [rsp+2E8h+var_188]
0x180042367  mov     [rsp+2E8h+var_2A8], rcx
0x18004236c  lea     rcx, [rsp+2E8h+var_288]
0x180042371  mov     [rsp+2E8h+var_2B0], rcx
0x180042376  mov     qword ptr [rsp+2E8h+var_2B8], r13
0x18004237b  mov     word ptr [rsp+2E8h+var_2C0], 1Eh
0x180042382  mov     dword ptr [rsp+2E8h+var_2C8], 0
0x18004238a  mov     r9d, 2
0x180042390  mov     r8, rax
0x180042393  lea     rdx, [rsp+2E8h+var_1D8]
0x18004239b  mov     rcx, rbx
0x18004239e  mov     rax, qword ptr [rsp+2E8h+var_278.Data1]
0x1800423a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800423a8  nop
0x1800423a9  mov     rcx, [rsp+2E8h+string]; string
0x1800423b1  call    cs:__imp_WindowsDeleteString
0x1800423b7  mov     [rsp+2E8h+string], 0
0x1800423c3  mov     rcx, [rsp+2E8h+var_290]; string
0x1800423c8  call    cs:__imp_WindowsDeleteString
0x1800423ce  mov     [rsp+2E8h+var_290], 0
0x1800423d7  lea     rcx, [rsp+2E8h+var_188]
0x1800423df  call    ??1?$function@$$A6AJXZ@std@@QEAA@XZ; std::function<long (void)>::~function<long (void)>(void)
0x1800423e4  nop
0x1800423e5  lea     rcx, [rsp+2E8h+var_108]
0x1800423ed  call    _lambda_c7fb734662817d6bb866d06e21590e22_____lambda_c7fb734662817d6bb866d06e21590e22_
0x1800423f2  movaps  xmm0, xmmword ptr [rsp+2E8h+var_1D8]
0x1800423fa  movdqa  xmmword ptr [rsp+2E8h+var_278.Data1], xmm0
0x180042400  lea     rdx, [rsp+2E8h+var_278]; struct _GUID
0x180042405  mov     rcx, [r15]; this
0x180042408  call    ?ReplaceCompletedTransfer@NtmCancelCallback@ConnectedStorage@@QEAAXU_GUID@@@Z; ConnectedStorage::NtmCancelCallback::ReplaceCompletedTransfer(_GUID)
0x18004240d  nop
0x18004240e  mov     rcx, [rsp+2E8h+var_230]; this
0x180042416  test    rcx, rcx
0x180042419  jz      short loc_180042421
0x18004241b  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x180042420  nop
0x180042421  lea     rcx, [rsp+2E8h+var_1F8]
0x180042429  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004242e  nop
0x18004242f  lea     rcx, [rsp+2E8h+Src]
0x180042437  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004243c  nop
0x18004243d  lea     rcx, [rsp+2E8h+var_1A8]
0x180042445  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004244a  nop
0x18004244b  jmp     loc_180042527
0x180042450  cmp     [rsp+2E8h+var_298], 0
0x180042455  jl      short loc_180042474
0x180042457  mov     rsi, [rsp+2E8h+var_260]
0x18004245f  mov     r14, [rsp+2E8h+var_258]
0x180042467  mov     r12, [rsp+2E8h+var_250]
0x18004246f  jmp     loc_18004251F
0x180042474  mov     rdx, [rsp+2E8h+var_228]; struct ConnectedStorage::Mutex *
0x18004247c  lea     rcx, [rsp+2E8h+var_1D8]; this
0x180042484  call    ??0Unlock@Mutex@ConnectedStorage@@QEAA@AEAV12@PEAD@Z; ConnectedStorage::Mutex::Unlock::Unlock(ConnectedStorage::Mutex &,char *)
0x180042489  nop
0x18004248a  xor     edx, edx; length
0x18004248c  mov     rsi, [rsp+2E8h+var_260]
0x180042494  mov     rcx, [rsi+10h]; string
0x180042498  call    cs:__imp_WindowsGetStringRawBuffer
0x18004249e  mov     rbx, rax
0x1800424a1  xor     edx, edx; length
0x1800424a3  mov     rcx, [rsi+18h]; string
0x1800424a7  call    cs:__imp_WindowsGetStringRawBuffer
0x1800424ad  mov     [rsp+2E8h+var_2B8], 0; unsigned int
0x1800424b5  mov     ecx, [rsp+2E8h+var_298]
0x1800424b9  mov     [rsp+2E8h+var_2C0], ecx; unsigned int
0x1800424bd  mov     dword ptr [rsp+2E8h+var_2C8], 0; unsigned int
0x1800424c5  xor     r9d, r9d; struct _GUID *
0x1800424c8  mov     r8, [rsp+2E8h+var_208]; unsigned __int16 *
0x1800424d0  mov     rdx, rbx; unsigned __int16 *
0x1800424d3  mov     rcx, rax; this
0x1800424d6  call    ?EventWriteWebDownloadAtom@ConnectedStorage@@YAXQEBG0QEBU_GUID@@IIII@Z; ConnectedStorage::EventWriteWebDownloadAtom(ushort const * const,ushort const * const,_GUID const * const,uint,uint,uint,uint)
0x1800424db  mov     r14, [rsp+2E8h+var_258]
0x1800424e3  mov     rcx, [r14]; this
0x1800424e6  call    ?Abandon@AtomDownloadStream@ConnectedStorage@@QEBAXXZ; ConnectedStorage::AtomDownloadStream::Abandon(void)
0x1800424eb  lea     rcx, [rsp+2E8h+var_1F8]; this
0x1800424f3  call    ??0Atom@ConnectedStorage@@QEAA@XZ; ConnectedStorage::Atom::Atom(void)
0x1800424f8  mov     r8, rax
0x1800424fb  mov     edx, 1
0x180042500  mov     r12, [rsp+2E8h+var_250]
0x180042508  mov     rcx, r12
0x18004250b  call    ??R?$_Func_class@XW4Status@WebService@ConnectedStorage@@VAtom@3@@std@@QEBAXW4Status@WebService@ConnectedStorage@@VAtom@4@@Z; std::_Func_class<void,ConnectedStorage::WebService::Status,ConnectedStorage::Atom>::operator()(ConnectedStorage::WebService::Status,ConnectedStorage::Atom)
0x180042510  nop
0x180042511  mov     rcx, [rsp+2E8h+var_1D8]; lpCriticalSection
0x180042519  call    cs:__imp_EnterCriticalSection
0x18004251f  mov     r15, [rsp+2E8h+var_248]
0x180042527  mov     rcx, [rsp+2E8h+var_220]; lpCriticalSection
0x18004252f  call    cs:__imp_LeaveCriticalSection
0x180042535  nop
0x180042536  mov     rcx, rsi; this
0x180042539  call    ??1ContextDesc@ConnectedStorage@@QEAA@XZ; ConnectedStorage::ContextDesc::~ContextDesc(void)
0x18004253e  nop
0x18004253f  mov     rcx, r14
0x180042542  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180042547  nop
0x180042548  mov     rcx, [r15+8]; this
0x18004254c  test    rcx, rcx
0x18004254f  jz      short loc_180042557
0x180042551  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180042556  nop
0x180042557  mov     rcx, r12
0x18004255a  call    ??1?$function@$$A6AJXZ@std@@QEAA@XZ; std::function<long (void)>::~function<long (void)>(void)
0x18004255f  mov     rcx, [rsp+2E8h+var_48]
0x180042567  xor     rcx, rsp; StackCookie
0x18004256a  call    __security_check_cookie
0x18004256f  add     rsp, 2B8h
0x180042576  pop     r15
0x180042578  pop     r14
0x18004257a  pop     r13
0x18004257c  pop     r12
0x18004257e  pop     rsi
0x18004257f  pop     rbx
0x180042580  retn
```
