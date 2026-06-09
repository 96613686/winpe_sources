# ConnectedStorage::NtmWebService::TrustedDeviceRequest(ConnectedStorage::SimpleHStringWrapper const &,ulong,std::function<void (ConnectedStorage::WebService::Status)>)

- ea: `0x180045f24`
- end: `0x180046371`
- name: `?TrustedDeviceRequest@NtmWebService@ConnectedStorage@@AEBAXAEBVSimpleHStringWrapper@2@KV?$function@$$A6AXW4Status@WebService@ConnectedStorage@@@Z@std@@@Z`
- size: `1101`
- prototype: ``
- caller_count: `2`
- callee_count: `20`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800445b0`
- `0x180046380`

## callees

- `0x180003c70`
- `0x18000aae4`
- `0x18000c218`
- `0x18000cb9c`
- `0x18000cd1c`
- `0x18000d6bc`
- `0x180010e30`
- `0x180011c0c`
- `0x180011c68`
- `0x1800136a8`
- `0x18001c090`
- `0x18001ea44`
- `0x180022dec`
- `0x18003c420`
- `0x18003d2f0`
- `0x18003e3c8`
- `0x18003ee9c`
- `0x18003f0b0`
- `0x180045f24`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004631d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004631d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004632c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004632c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004610c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004621d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180046230`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004627f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004628f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004610c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004621d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180046230`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004627f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004628f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004600c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800462e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004600c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800462e1`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180045fe4`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180045fe4`
- `ntdll!RtlIsMultiSessionSku` at `0x180045f79`
- `ntdll!RtlIsMultiSessionSku` at `0x180045f79`

## string_xrefs

- `0x180045ff2`: `https://titlestorage.xboxlive.com/connectedstorage/users/xuid(`
- `0x18004635e`: `NtmWebService::TrustedDeviceRequest UserManager is not present`

## pseudocode

```c
// Hidden C++ exception states: #wind=20
__int64 __fastcall ConnectedStorage::NtmWebService::TrustedDeviceRequest(__int64 a1, HSTRING *a2, char *a3, __int64 a4)
{
  __int64 v4; // rdi
  char *v7; // r8
  __int64 v8; // r8
  struct _RTL_CRITICAL_SECTION *v9; // rcx
  ULONGLONG TickCount64; // rax
  PCWSTR StringRawBuffer; // rax
  __int64 v12; // r8
  const unsigned __int16 *v13; // r8
  __int64 v14; // r14
  void (__fastcall *v15)(__int64, HSTRING *, HSTRING *, HSTRING *, _BYTE *, __int64 *); // r13
  HSTRING *AddressOf; // r12
  HSTRING *v17; // rax
  __int64 v18; // r14
  void (__fastcall *v19)(__int64, _BYTE *, HSTRING *, HSTRING *, HSTRING *); // r12
  const WCHAR *v20; // rdx
  HSTRING *v21; // rax
  __int64 *v22; // r12
  __int64 v23; // rsi
  __int64 v24; // rax
  void (__fastcall *v25)(__int64 *, _BYTE *, HSTRING *, _QWORD, int); // r15
  __int64 v26; // rsi
  unsigned int v27; // r13d
  HSTRING *v28; // rax
  char *v29; // r8
  ConnectedStorage *v30; // rax
  __int64 v31; // r8
  unsigned int v33; // [rsp+28h] [rbp-230h]
  _BYTE v34[4]; // [rsp+50h] [rbp-208h] BYREF
  unsigned int v35; // [rsp+54h] [rbp-204h]
  unsigned __int16 *v36; // [rsp+58h] [rbp-200h] BYREF
  HSTRING v37; // [rsp+60h] [rbp-1F8h] BYREF
  HSTRING string; // [rsp+68h] [rbp-1F0h] BYREF
  __int64 v39; // [rsp+70h] [rbp-1E8h] BYREF
  HSTRING v40; // [rsp+78h] [rbp-1E0h] BYREF
  __int64 v41; // [rsp+80h] [rbp-1D8h] BYREF
  HSTRING v42; // [rsp+88h] [rbp-1D0h] BYREF
  __int64 v43; // [rsp+90h] [rbp-1C8h]
  __int64 *v44; // [rsp+98h] [rbp-1C0h] BYREF
  __int64 v45; // [rsp+A0h] [rbp-1B8h] BYREF
  LPCRITICAL_SECTION lpCriticalSection[2]; // [rsp+A8h] [rbp-1B0h] BYREF
  HSTRING *v47; // [rsp+B8h] [rbp-1A0h] BYREF
  LPCRITICAL_SECTION v48[2]; // [rsp+C8h] [rbp-190h] BYREF
  _QWORD Src[4]; // [rsp+D8h] [rbp-180h] BYREF
  _BYTE v50[32]; // [rsp+F8h] [rbp-160h] BYREF
  _BYTE v51[24]; // [rsp+118h] [rbp-140h] BYREF
  _BYTE v52[56]; // [rsp+130h] [rbp-128h] BYREF
  __int64 v53; // [rsp+168h] [rbp-F0h]
  _DWORD v54[16]; // [rsp+170h] [rbp-E8h] BYREF
  _BYTE v55[96]; // [rsp+1B0h] [rbp-A8h] BYREF

  v4 = a4;
  v35 = (unsigned int)a3;
  v47 = a2;
  LODWORD(v36) = (_DWORD)a3;
  v43 = a4;
  if ( (*(_BYTE *)(a1 + 25) || *(_BYTE *)(a1 + 24)) && !(unsigned __int8)RtlIsMultiSessionSku() )
  {
    lpCriticalSection[0] = (LPCRITICAL_SECTION)(a1 + 40);
    ConnectedStorage::Mutex::Lock::Lock(
      (ConnectedStorage::Mutex::Lock *)v48,
      (struct _RTL_CRITICAL_SECTION *)(a1 + 40),
      a3);
    if ( !*(_QWORD *)(a1 + 88) )
    {
      ConnectedStorage::Mutex::Unlock::Unlock(
        (ConnectedStorage::Mutex::Unlock *)&v47,
        (struct ConnectedStorage::Mutex *)(a1 + 40),
        v7);
      std::_Func_class<void,enum ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &>::operator()(
        v4,
        1,
        v8);
      v9 = (struct _RTL_CRITICAL_SECTION *)v47;
LABEL_18:
      EnterCriticalSection(v9);
      goto LABEL_19;
    }
    TickCount64 = GetTickCount64();
    try
    {
      v44 = (__int64 *)TickCount64;
      std::wstring::wstring((__int64)Src, (__int64)L"https://titlestorage.xboxlive.com/connectedstorage/users/xuid(");
      StringRawBuffer = WindowsGetStringRawBuffer(*a2, 0);
      v12 = -1;
      do
        ++v12;
      while ( StringRawBuffer[v12] );
      std::wstring::_Append<unsigned short>(Src);
      std::wstring::_Append<unsigned short>(Src);
      v37 = 0;
      v40 = 0;
      v45 = 0;
      v34[0] = 0;
      v14 = *(_QWORD *)(a1 + 32);
      if ( !v14 )
        ConnectedStorage::ReportErrorAndThrow(
          (ConnectedStorage *)0x8000FFFFLL,
          (int)L"NtmWebService::TrustedDeviceRequest UserManager is not present",
          v13);
      v15 = *(void (__fastcall **)(__int64, HSTRING *, HSTRING *, HSTRING *, _BYTE *, __int64 *))(*(_QWORD *)v14 + 16LL);
      AddressOf = ConnectedStorage::SimpleHStringWrapper::GetAddressOf((ConnectedStorage::SimpleHStringWrapper *)&v40);
      v17 = ConnectedStorage::SimpleHStringWrapper::GetAddressOf((ConnectedStorage::SimpleHStringWrapper *)&v37);
      v15(v14, a2, v17, AddressOf, v34, &v45);
      v18 = *(_QWORD *)(a1 + 32);
      v19 = *(void (__fastcall **)(__int64, _BYTE *, HSTRING *, HSTRING *, HSTRING *))(*(_QWORD *)v18 + 40LL);
      v20 = (const WCHAR *)Src;
      if ( Src[3] > 7u )
        v20 = (const WCHAR *)Src[0];
      v21 = ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&string, v20);
      v19(v18, v50, v21, &v37, a2);
      WindowsDeleteString(string);
      Microsoft::WRL::Details::Make<ConnectedStorage::StringStream,>(&v41);
      v22 = *(__int64 **)(a1 + 88);
      v23 = *v22;
      v24 = lambda_9d611b5a6b86de457d3c0c1de4f49ded_::_lambda_9d611b5a6b86de457d3c0c1de4f49ded_(
              v55,
              v4,
              &v41,
              a2,
              &v36,
              &v44);
      v53 = 0;
      v53 = std::_Global_new_std::_Func_impl_no_alloc__lambda_9d611b5a6b86de457d3c0c1de4f49ded__void__NTM_TRANSFER_STATUS_const___unsigned_int_long___lambda_9d611b5a6b86de457d3c0c1de4f49ded___(v24);
      v25 = *(void (__fastcall **)(__int64 *, _BYTE *, HSTRING *, _QWORD, int))(v23 + 8);
      v44 = &v39;
      v26 = v41;
      v39 = v41;
      Microsoft::WRL::ComPtr<ConnectedStorage::AtomDownloadStream>::InternalAddRef(&v39);
      ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&string, (__int64)v50);
      v27 = v35 | 0x40;
      v28 = ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&v42, (__int64)Src);
      LOWORD(v33) = 30;
      v25(v22, v51, v28, v27, 1);
      WindowsDeleteString(v42);
      v42 = 0;
      WindowsDeleteString(string);
      string = 0;
      std::function<long (void)>::~function<long (void)>(v52);
      lambda_9d611b5a6b86de457d3c0c1de4f49ded_::__lambda_9d611b5a6b86de457d3c0c1de4f49ded_(v55);
      if ( v26 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
      std::wstring::_Tidy_deallocate(v50);
      WindowsDeleteString(v40);
      v40 = 0;
      WindowsDeleteString(v37);
      v37 = 0;
      std::wstring::_Tidy_deallocate(Src);
    }
    catch ( ConnectedStorage::ComError v54 )
    {
      v35 = v54[6];
      ConnectedStorage::ComError::~ComError((ConnectedStorage::ComError *)v54);
      if ( (v35 & 0x80000000) != 0 )
      {
LABEL_17:
        ConnectedStorage::Mutex::Unlock::Unlock(
          (ConnectedStorage::Mutex::Unlock *)lpCriticalSection,
          (struct ConnectedStorage::Mutex *)lpCriticalSection[0],
          v29);
        v30 = (ConnectedStorage *)WindowsGetStringRawBuffer(*v47, 0);
        ConnectedStorage::EventWriteWebTrustedDevice(
          v30,
          (const unsigned __int16 *const)(unsigned int)v36,
          0,
          v35,
          0,
          v33);
        v4 = v43;
        std::_Func_class<void,enum ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &>::operator()(
          v43,
          1,
          v31);
        v9 = lpCriticalSection[0];
        goto LABEL_18;
      }
      v4 = v43;
    }
    catch ( std::bad_alloc )
    {
      v35 = -2147024882;
      goto LABEL_17;
    }
    catch ( ... )
    {
      v35 = -2147467259;
      goto LABEL_17;
    }
LABEL_19:
    LeaveCriticalSection(v48[0]);
    return std::function<long (void)>::~function<long (void)>(v4);
  }
  std::_Func_class<void,enum ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &>::operator()(
    v4,
    1,
    a3);
  return std::function<long (void)>::~function<long (void)>(v4);
}

```

## disassembly

```asm
0x180045f24  push    rbx
0x180045f26  push    rsi
0x180045f27  push    rdi
0x180045f28  push    r12
0x180045f2a  push    r13
0x180045f2c  push    r14
0x180045f2e  push    r15
0x180045f30  sub     rsp, 220h
0x180045f37  mov     rax, cs:__security_cookie
0x180045f3e  xor     rax, rsp
0x180045f41  mov     [rsp+258h+var_48], rax
0x180045f49  mov     rdi, r9
0x180045f4c  mov     eax, r8d
0x180045f4f  mov     [rsp+258h+var_204], eax
0x180045f53  mov     r15, rdx
0x180045f56  mov     rsi, rcx
0x180045f59  mov     [rsp+258h+var_1A0], rdx
0x180045f61  mov     dword ptr [rsp+258h+var_200], eax
0x180045f65  mov     [rsp+258h+var_1C8], r9
0x180045f6d  xor     ebx, ebx
0x180045f6f  cmp     [rcx+19h], bl
0x180045f72  jnz     short loc_180045F79
0x180045f74  cmp     [rcx+18h], bl
0x180045f77  jz      short loc_180045F83
0x180045f79  call    cs:__imp_RtlIsMultiSessionSku
0x180045f7f  test    al, al
0x180045f81  jz      short loc_180045F95
0x180045f83  mov     edx, 1
0x180045f88  mov     rcx, rdi
0x180045f8b  call    ??R?$_Func_class@XW4Status@WebService@ConnectedStorage@@AEBVSimpleHStringWrapper@3@@std@@QEBAXW4Status@WebService@ConnectedStorage@@AEBVSimpleHStringWrapper@4@@Z; std::_Func_class<void,ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &>::operator()(ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &)
0x180045f90  jmp     loc_180046333
0x180045f95  lea     r14, [rsi+28h]
0x180045f99  mov     [rsp+258h+lpCriticalSection], r14
0x180045fa1  mov     rdx, r14; struct ConnectedStorage::Mutex *
0x180045fa4  lea     rcx, [rsp+258h+var_190]; this
0x180045fac  call    ??0Lock@Mutex@ConnectedStorage@@QEAA@AEAV12@PEAD@Z; ConnectedStorage::Mutex::Lock::Lock(ConnectedStorage::Mutex &,char *)
0x180045fb1  nop
0x180045fb2  cmp     [rsi+58h], rbx
0x180045fb6  jnz     short loc_180045FE4
0x180045fb8  mov     rdx, r14; struct ConnectedStorage::Mutex *
0x180045fbb  lea     rcx, [rsp+258h+var_1A0]; this
0x180045fc3  call    ??0Unlock@Mutex@ConnectedStorage@@QEAA@AEAV12@PEAD@Z; ConnectedStorage::Mutex::Unlock::Unlock(ConnectedStorage::Mutex &,char *)
0x180045fc8  nop
0x180045fc9  mov     edx, 1
0x180045fce  mov     rcx, rdi
0x180045fd1  call    ??R?$_Func_class@XW4Status@WebService@ConnectedStorage@@AEBVSimpleHStringWrapper@3@@std@@QEBAXW4Status@WebService@ConnectedStorage@@AEBVSimpleHStringWrapper@4@@Z; std::_Func_class<void,ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &>::operator()(ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &)
0x180045fd6  nop
0x180045fd7  mov     rcx, [rsp+258h+var_1A0]
0x180045fdf  jmp     loc_18004631D
0x180045fe4  call    cs:__imp_GetTickCount64
0x180045fea  mov     [rsp+258h+var_1C0], rax
0x180045ff2  lea     rdx, aHttpsTitlestor; "https://titlestorage.xboxlive.com/conne"...
0x180045ff9  lea     rcx, [rsp+258h+Src]
0x180046001  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180046006  nop
0x180046007  xor     edx, edx; length
0x180046009  mov     rcx, [r15]; string
0x18004600c  call    cs:__imp_WindowsGetStringRawBuffer
0x180046012  or      r8, 0FFFFFFFFFFFFFFFFh
0x180046016  inc     r8
0x180046019  cmp     [rax+r8*2], bx
0x18004601e  jnz     short loc_180046016
0x180046020  mov     rdx, rax
0x180046023  lea     rcx, [rsp+258h+Src]; Src
0x18004602b  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180046030  mov     r8d, 0Fh
0x180046036  lea     rdx, aTrusteddevice; ")/trusteddevice"
0x18004603d  lea     rcx, [rsp+258h+Src]; Src
0x180046045  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18004604a  mov     [rsp+258h+var_1F8], rbx
0x18004604f  mov     [rsp+258h+var_1E0], rbx
0x180046054  mov     [rsp+258h+var_1B8], rbx
0x18004605c  mov     [rsp+258h+var_208], bl
0x180046060  mov     r14, [rsi+20h]
0x180046064  test    r14, r14
0x180046067  jz      loc_18004635E
0x18004606d  mov     rax, [r14]
0x180046070  mov     r13, [rax+10h]
0x180046074  lea     rcx, [rsp+258h+var_1E0]; this
0x180046079  call    ?GetAddressOf@SimpleHStringWrapper@ConnectedStorage@@QEAAPEAPEAUHSTRING__@@XZ; ConnectedStorage::SimpleHStringWrapper::GetAddressOf(void)
0x18004607e  mov     r12, rax
0x180046081  lea     rcx, [rsp+258h+var_1F8]; this
0x180046086  call    ?GetAddressOf@SimpleHStringWrapper@ConnectedStorage@@QEAAPEAPEAUHSTRING__@@XZ; ConnectedStorage::SimpleHStringWrapper::GetAddressOf(void)
0x18004608b  lea     rcx, [rsp+258h+var_1B8]
0x180046093  mov     [rsp+258h+var_230], rcx
0x180046098  lea     rcx, [rsp+258h+var_208]
0x18004609d  mov     qword ptr [rsp+258h+var_238], rcx
0x1800460a2  mov     r9, r12
0x1800460a5  mov     r8, rax
0x1800460a8  mov     rdx, r15
0x1800460ab  mov     rcx, r14
0x1800460ae  mov     rax, r13
0x1800460b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800460b6  mov     r14, [rsi+20h]
0x1800460ba  mov     rax, [r14]
0x1800460bd  mov     r12, [rax+28h]
0x1800460c1  lea     rdx, [rsp+258h+Src]
0x1800460c9  cmp     [rsp+258h+var_168], 7
0x1800460d2  cmova   rdx, [rsp+258h+Src]; sourceString
0x1800460db  lea     rcx, [rsp+258h+string]; string
0x1800460e0  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@PEBG@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(ushort const *)
0x1800460e5  nop
0x1800460e6  mov     qword ptr [rsp+258h+var_238], r15
0x1800460eb  lea     r9, [rsp+258h+var_1F8]
0x1800460f0  mov     r8, rax
0x1800460f3  lea     rdx, [rsp+258h+var_160]
0x1800460fb  mov     rcx, r14
0x1800460fe  mov     rax, r12
0x180046101  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046106  nop
0x180046107  mov     rcx, [rsp+258h+string]; string
0x18004610c  call    cs:__imp_WindowsDeleteString
0x180046112  lea     rcx, [rsp+258h+var_1D8]
0x18004611a  call    ??$Make@VStringStream@ConnectedStorage@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VStringStream@ConnectedStorage@@@12@XZ; Microsoft::WRL::Details::Make<ConnectedStorage::StringStream,>(void)
0x18004611f  nop
0x180046120  mov     r12, [rsi+58h]
0x180046124  mov     rsi, [r12]
0x180046128  lea     rax, [rsp+258h+var_1C0]
0x180046130  mov     [rsp+258h+var_230], rax
0x180046135  lea     rax, [rsp+258h+var_200]
0x18004613a  mov     qword ptr [rsp+258h+var_238], rax
0x18004613f  mov     r9, r15
0x180046142  lea     r8, [rsp+258h+var_1D8]
0x18004614a  mov     rdx, rdi
0x18004614d  lea     rcx, [rsp+258h+var_A8]
0x180046155  call    _lambda_9d611b5a6b86de457d3c0c1de4f49ded____lambda_9d611b5a6b86de457d3c0c1de4f49ded_
0x18004615a  nop
0x18004615b  mov     [rsp+258h+var_F0], rbx
0x180046163  mov     rcx, rax
0x180046166  call    std___Global_new_std___Func_impl_no_alloc__lambda_9d611b5a6b86de457d3c0c1de4f49ded__void__NTM_TRANSFER_STATUS_const___unsigned_int_long___lambda_9d611b5a6b86de457d3c0c1de4f49ded___
0x18004616b  mov     [rsp+258h+var_F0], rax
0x180046173  mov     r15, [rsi+8]
0x180046177  lea     rax, [rsp+258h+var_1E8]
0x18004617c  mov     [rsp+258h+var_1C0], rax
0x180046184  mov     rsi, [rsp+258h+var_1D8]
0x18004618c  mov     [rsp+258h+var_1E8], rsi
0x180046191  lea     rcx, [rsp+258h+var_1E8]
0x180046196  call    ?InternalAddRef@?$ComPtr@VAtomDownloadStream@ConnectedStorage@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<ConnectedStorage::AtomDownloadStream>::InternalAddRef(void)
0x18004619b  nop
0x18004619c  lea     rdx, [rsp+258h+var_160]
0x1800461a4  lea     rcx, [rsp+258h+string]; string
0x1800461a9  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(std::wstring const &)
0x1800461ae  mov     r14, rax
0x1800461b1  mov     r13d, [rsp+258h+var_204]
0x1800461b6  or      r13d, 40h
0x1800461ba  lea     rdx, [rsp+258h+Src]
0x1800461c2  lea     rcx, [rsp+258h+var_1D0]; string
0x1800461ca  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(std::wstring const &)
0x1800461cf  nop
0x1800461d0  lea     rcx, [rsp+258h+var_128]
0x1800461d8  mov     [rsp+258h+var_218], rcx
0x1800461dd  lea     rcx, [rsp+258h+var_1E8]
0x1800461e2  mov     [rsp+258h+var_220], rcx
0x1800461e7  mov     [rsp+258h+var_228], r14
0x1800461ec  mov     word ptr [rsp+258h+var_230], 1Eh
0x1800461f3  mov     [rsp+258h+var_238], 1
0x1800461fb  mov     r9d, r13d
0x1800461fe  mov     r8, rax
0x180046201  lea     rdx, [rsp+258h+var_140]
0x180046209  mov     rcx, r12
0x18004620c  mov     rax, r15
0x18004620f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046214  nop
0x180046215  mov     rcx, [rsp+258h+var_1D0]; string
0x18004621d  call    cs:__imp_WindowsDeleteString
0x180046223  mov     [rsp+258h+var_1D0], rbx
0x18004622b  mov     rcx, [rsp+258h+string]; string
0x180046230  call    cs:__imp_WindowsDeleteString
0x180046236  mov     [rsp+258h+string], rbx
0x18004623b  lea     rcx, [rsp+258h+var_128]
0x180046243  call    ??1?$function@$$A6AJXZ@std@@QEAA@XZ; std::function<long (void)>::~function<long (void)>(void)
0x180046248  nop
0x180046249  lea     rcx, [rsp+258h+var_A8]
0x180046251  call    _lambda_9d611b5a6b86de457d3c0c1de4f49ded_____lambda_9d611b5a6b86de457d3c0c1de4f49ded_
0x180046256  nop
0x180046257  test    rsi, rsi
0x18004625a  jz      short loc_18004626C
0x18004625c  mov     rax, [rsi]
0x18004625f  mov     rcx, rsi
0x180046262  mov     rax, [rax+10h]
0x180046266  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004626b  nop
0x18004626c  lea     rcx, [rsp+258h+var_160]
0x180046274  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180046279  nop
0x18004627a  mov     rcx, [rsp+258h+var_1E0]; string
0x18004627f  call    cs:__imp_WindowsDeleteString
0x180046285  mov     [rsp+258h+var_1E0], rbx
0x18004628a  mov     rcx, [rsp+258h+var_1F8]; string
0x18004628f  call    cs:__imp_WindowsDeleteString
0x180046295  mov     [rsp+258h+var_1F8], rbx
0x18004629a  lea     rcx, [rsp+258h+Src]
0x1800462a2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800462a7  nop
0x1800462a8  jmp     short loc_180046324
0x1800462aa  xor     ebx, ebx
0x1800462ac  cmp     [rsp+258h+var_204], ebx
0x1800462b0  jl      short loc_1800462BE
0x1800462b2  mov     rdi, [rsp+258h+var_1C8]
0x1800462ba  jmp     short loc_180046324
0x1800462bc  xor     ebx, ebx
0x1800462be  mov     rdx, [rsp+258h+lpCriticalSection]; struct ConnectedStorage::Mutex *
0x1800462c6  lea     rcx, [rsp+258h+lpCriticalSection]; this
0x1800462ce  call    ??0Unlock@Mutex@ConnectedStorage@@QEAA@AEAV12@PEAD@Z; ConnectedStorage::Mutex::Unlock::Unlock(ConnectedStorage::Mutex &,char *)
0x1800462d3  nop
0x1800462d4  xor     edx, edx; length
0x1800462d6  mov     rcx, [rsp+258h+var_1A0]
0x1800462de  mov     rcx, [rcx]; string
0x1800462e1  call    cs:__imp_WindowsGetStringRawBuffer
0x1800462e7  mov     [rsp+258h+var_238], ebx; unsigned int
0x1800462eb  mov     r9d, [rsp+258h+var_204]; unsigned int
0x1800462f0  xor     r8d, r8d; unsigned int
0x1800462f3  mov     edx, dword ptr [rsp+258h+var_200]; unsigned __int16 *
0x1800462f7  mov     rcx, rax; this
0x1800462fa  call    ?EventWriteWebTrustedDevice@ConnectedStorage@@YAXQEBGIIII@Z; ConnectedStorage::EventWriteWebTrustedDevice(ushort const * const,uint,uint,uint,uint)
0x1800462ff  mov     edx, 1
0x180046304  mov     rdi, [rsp+258h+var_1C8]
0x18004630c  mov     rcx, rdi
0x18004630f  call    ??R?$_Func_class@XW4Status@WebService@ConnectedStorage@@AEBVSimpleHStringWrapper@3@@std@@QEBAXW4Status@WebService@ConnectedStorage@@AEBVSimpleHStringWrapper@4@@Z; std::_Func_class<void,ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &>::operator()(ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &)
0x180046314  nop
0x180046315  mov     rcx, [rsp+258h+lpCriticalSection]; lpCriticalSection
0x18004631d  call    cs:__imp_EnterCriticalSection
0x180046323  nop
0x180046324  mov     rcx, [rsp+258h+var_190]; lpCriticalSection
0x18004632c  call    cs:__imp_LeaveCriticalSection
0x180046332  nop
0x180046333  mov     rcx, rdi
0x180046336  call    ??1?$function@$$A6AJXZ@std@@QEAA@XZ; std::function<long (void)>::~function<long (void)>(void)
0x18004633b  mov     rcx, [rsp+258h+var_48]
0x180046343  xor     rcx, rsp; StackCookie
0x180046346  call    __security_check_cookie
0x18004634b  add     rsp, 220h
0x180046352  pop     r15
0x180046354  pop     r14
0x180046356  pop     r13
0x180046358  pop     r12
0x18004635a  pop     rdi
0x18004635b  pop     rsi
0x18004635c  pop     rbx
0x18004635d  retn
0x18004635e  lea     rdx, aNtmwebserviceT; "NtmWebService::TrustedDeviceRequest Use"...
0x180046365  mov     ecx, 8000FFFFh; this
0x18004636a  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
```
