# CGnssDriverWrapper::InternalDeviceIoControl(ulong,void *,ulong,void *,ulong,int,ulong)

- ea: `0x1800642a8`
- end: `0x1800646cd`
- name: `?InternalDeviceIoControl@CGnssDriverWrapper@@AEAAJKPEAXK0KHK@Z`
- size: `1061`
- prototype: `__int64 __fastcall(CGnssDriverWrapper *this, DWORD, void *, DWORD, _BYTE *, unsigned int, int, unsigned int)`
- caller_count: `28`
- callee_count: `9`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180064220`
- `0x180098200`
- `0x1800e5084`
- `0x1800e5198`
- `0x1800e52b8`
- `0x1800e53e4`
- `0x1800e56cc`
- `0x1800e5a00`
- `0x1800e5aa0`
- `0x1800e5b60`
- `0x1800e5c00`
- `0x1800e5d90`
- `0x1800e5f90`
- `0x1800e6140`
- `0x1800e6350`
- `0x1800e63b0`
- `0x1800e6410`
- `0x1800e6470`
- `0x1800e64d0`
- `0x1800e6530`
- `0x1800e6590`
- `0x1800e6650`
- `0x1800e6850`
- `0x1800e6a30`
- `0x1800e6b50`
- `0x1800e6bc0`
- `0x1800e6c80`
- `0x1800e6cf0`

## callees

- `0x1800043d8`
- `0x1800359f0`
- `0x1800642a8`
- `0x18006807c`
- `0x18009543c`
- `0x180098c58`
- `0x1800a98c0`
- `0x1800e01fc`
- `0x1800e6e18`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18006455a`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18006455a`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x1800645c6`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x1800645c6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800645fa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800645fa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180064687`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180064695`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180064687`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180064695`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800645b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800645cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064632`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800645b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800645cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064632`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800642f1`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180064335`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800642f1`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180064335`
- `ntdll!RtlNtStatusToDosError` at `0x1800646bb`
- `ntdll!RtlNtStatusToDosError` at `0x1800646bb`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18006466f`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18006466f`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x180064650`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x180064650`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800645a2`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800645a2`
- `api-ms-win-core-io-l1-1-1!GetOverlappedResultEx` at `0x180064625`
- `api-ms-win-core-io-l1-1-1!GetOverlappedResultEx` at `0x180064625`

## pseudocode

```c
__int64 __fastcall CGnssDriverWrapper::InternalDeviceIoControl(
        CGnssDriverWrapper *this,
        DWORD a2,
        void *a3,
        DWORD a4,
        _BYTE *a5,
        unsigned int a6,
        int a7,
        unsigned int a8)
{
  LPOVERLAPPED lpOverlapped; // rdi
  __int64 v11; // rax
  _BYTE *v12; // rcx
  int LastError; // ebx
  DWORD v14; // r13d
  unsigned __int64 v15; // rsi
  int v16; // ecx
  int v17; // r8d
  int v18; // r9d
  int v19; // ecx
  int v20; // r8d
  int v21; // r9d
  int NewOverlapped; // eax
  void **v24; // rax
  void *v25; // rcx
  void *v26; // r8
  signed int v27; // eax
  void **v28; // rax
  void *v29; // rcx
  _QWORD *v30; // rcx
  _QWORD *v31; // rcx
  NTSTATUS Internal; // eax
  bool v33[4]; // [rsp+60h] [rbp-41h] BYREF
  DWORD dwIoControlCode; // [rsp+64h] [rbp-3Dh] BYREF
  unsigned int v35; // [rsp+68h] [rbp-39h] BYREF
  BOOL OverlappedResult; // [rsp+6Ch] [rbp-35h] BYREF
  DWORD nInBufferSize; // [rsp+70h] [rbp-31h] BYREF
  LPOVERLAPPED v38; // [rsp+78h] [rbp-29h] BYREF
  ULONGLONG TickCount64; // [rsp+80h] [rbp-21h] BYREF
  DWORD BytesReturned; // [rsp+88h] [rbp-19h] BYREF

  nInBufferSize = a4;
  v35 = 0;
  lpOverlapped = 0;
  v38 = 0;
  BytesReturned = 0;
  dwIoControlCode = a2;
  OverlappedResult = 1;
  TickCount64 = GetTickCount64();
  if ( a5 )
  {
    v11 = a6;
    v12 = a5;
    if ( a6 )
    {
      do
      {
        *v12++ = 0;
        --v11;
      }
      while ( v11 );
    }
  }
  if ( *((_DWORD *)this + 12) )
  {
    LastError = -2147023673;
LABEL_6:
    v14 = dwIoControlCode;
    goto LABEL_7;
  }
  NewOverlapped = COverlappedList::CreateNewOverlapped(
                    (CGnssDriverWrapper *)((char *)this + 88),
                    a7,
                    (struct GNSS_OVERLAPPED **)&v38);
  lpOverlapped = v38;
  LastError = NewOverlapped;
  if ( NewOverlapped < 0 )
    goto LABEL_6;
  LODWORD(v38[1].Internal) = dwIoControlCode;
  HIDWORD(lpOverlapped[1].Internal) = a7;
  LODWORD(lpOverlapped[1].InternalHigh) = a8;
  if ( a7 )
  {
    lpOverlapped[89].Internal = (ULONG_PTR)a5;
    LODWORD(lpOverlapped[89].InternalHigh) = a6;
    lpOverlapped->hEvent = (HANDLE)((unsigned __int64)lpOverlapped->hEvent | 1);
  }
  else
  {
    lpOverlapped[89].Internal = (ULONG_PTR)&lpOverlapped[1].Pointer;
    LODWORD(lpOverlapped[89].InternalHigh) = *((_DWORD *)this + 33) < 6u ? 2736 : 2800;
    StartThreadpoolIo(*((PTP_IO *)this + 10));
  }
  v24 = (void **)*((_QWORD *)this + 8);
  if ( v24 )
    v25 = *v24;
  else
    v25 = 0;
  v26 = a3;
  v14 = dwIoControlCode;
  if ( DeviceIoControl(
         v25,
         dwIoControlCode,
         v26,
         nInBufferSize,
         (LPVOID)lpOverlapped[89].Internal,
         lpOverlapped[89].InternalHigh,
         &BytesReturned,
         lpOverlapped) )
  {
    goto LABEL_52;
  }
  if ( GetLastError() == 997 )
  {
    if ( a7 )
    {
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
      v28 = (void **)*((_QWORD *)this + 8);
      if ( v28 )
        v29 = *v28;
      else
        v29 = 0;
      OverlappedResult = GetOverlappedResultEx(v29, lpOverlapped, &BytesReturned, 0x4E20u, 1);
      if ( !OverlappedResult )
      {
        LastError = GetLastError();
        if ( LastError == 258 )
        {
          v30 = (_QWORD *)*((_QWORD *)this + 8);
          if ( v30 )
            v30 = (_QWORD *)*v30;
          CancelIoEx(v30, lpOverlapped);
          v31 = (_QWORD *)*((_QWORD *)this + 8);
          if ( v31 )
            v31 = (_QWORD *)*v31;
          GetOverlappedResult(v31, lpOverlapped, &BytesReturned, 1);
        }
        else if ( LastError <= 0 )
        {
LABEL_50:
          EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
          goto LABEL_7;
        }
        LastError = (unsigned __int16)LastError | 0x80070000;
        goto LABEL_50;
      }
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
    }
LABEL_52:
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Location_Fix_GnssAdapterStatusTranslation>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Location_Fix_GnssAdapterStatusTranslation>::GetImpl'::`2'::impl)
      || !a7
      || (Internal = lpOverlapped->Internal, v35 = Internal, Internal >= 0) )
    {
      LastError = 0;
      goto LABEL_7;
    }
    v27 = RtlNtStatusToDosError(Internal);
    goto LABEL_35;
  }
  if ( !a7 )
    CancelThreadpoolIo(*((PTP_IO *)this + 10));
  v27 = GetLastError();
LABEL_35:
  LastError = v27;
  if ( v27 > 0 )
    LastError = (unsigned __int16)v27 | 0x80070000;
LABEL_7:
  v15 = GetTickCount64() - TickCount64;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Location_Fix_GnssAdapterStatusTranslation>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Location_Fix_GnssAdapterStatusTranslation>::GetImpl'::`2'::impl)
    && a7
    && (unsigned int)dword_1801DDF30 > 5
    && (unsigned __int8)tlgKeywordOn(&dword_1801DDF30, 0x400000000000LL) )
  {
    v33[0] = OverlappedResult;
    LODWORD(v38) = a8;
    TickCount64 = 0x1000000;
    nInBufferSize = LastError;
    dwIoControlCode = v15;
    OverlappedResult = v14;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
      v16,
      (unsigned int)byte_1801B001B,
      v17,
      v18,
      (__int64)&v38,
      (__int64)&OverlappedResult,
      (__int64)v33,
      (__int64)&v35,
      (__int64)&dwIoControlCode,
      (__int64)&nInBufferSize,
      (__int64)&TickCount64);
  }
  if ( LastError < 0 || v15 > 0x3A98 )
  {
    if ( (Microsoft_Windows_LocationServiceProviderEnableBits & 0x40) != 0 )
      McTemplateU0qqqq_EventWriteTransfer(v16, (unsigned int)GnssDriverIoctlResult, a8, v14, LastError, v15);
    if ( (unsigned int)dword_1801DDF30 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1801DDF30, 0x200000000000LL) )
    {
      TickCount64 = 0x1000000;
      LODWORD(v38) = LastError;
      nInBufferSize = v15;
      OverlappedResult = v14;
      v35 = a8;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        v19,
        (unsigned int)byte_1801B009B,
        v20,
        v21,
        (__int64)&v35,
        (__int64)&OverlappedResult,
        (__int64)&nInBufferSize,
        (__int64)&v38,
        (__int64)&TickCount64);
    }
  }
  if ( a7 && lpOverlapped )
  {
    lpOverlapped->hEvent = (HANDLE)((unsigned __int64)lpOverlapped->hEvent & ~1uLL);
    COverlappedList::DeleteOverlapped((CGnssDriverWrapper *)((char *)this + 88), (struct GNSS_OVERLAPPED *)lpOverlapped);
  }
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1800642a8  push    rbp
0x1800642aa  push    rbx
0x1800642ab  push    rsi
0x1800642ac  push    rdi
0x1800642ad  push    r12
0x1800642af  push    r13
0x1800642b1  push    r14
0x1800642b3  push    r15
0x1800642b5  lea     rbp, [rsp-7]
0x1800642ba  sub     rsp, 0A8h
0x1800642c1  mov     rax, cs:__security_cookie
0x1800642c8  xor     rax, rsp
0x1800642cb  mov     [rbp+3Fh+var_50], rax
0x1800642cf  xor     ebx, ebx
0x1800642d1  mov     [rbp+3Fh+nInBufferSize], r9d
0x1800642d5  mov     [rbp+3Fh+var_78], ebx
0x1800642d8  mov     edi, ebx
0x1800642da  mov     [rbp+3Fh+var_68], rbx
0x1800642de  mov     r13, r8
0x1800642e1  mov     [rbp+3Fh+BytesReturned], ebx
0x1800642e4  mov     r14, rcx
0x1800642e7  mov     [rbp+3Fh+dwIoControlCode], edx
0x1800642ea  mov     [rbp+3Fh+var_74], 1
0x1800642f1  call    cs:__imp_GetTickCount64
0x1800642f7  mov     rsi, [rbp+3Fh+arg_20]
0x1800642fb  mov     r12d, [rbp+3Fh+arg_28]
0x1800642ff  mov     [rbp+3Fh+var_60], rax
0x180064303  test    rsi, rsi
0x180064306  jz      short loc_18006431E
0x180064308  mov     eax, r12d
0x18006430b  mov     rcx, rsi
0x18006430e  test    r12d, r12d
0x180064311  jz      short loc_18006431E
0x180064313  mov     [rcx], bl
0x180064315  inc     rcx
0x180064318  sub     rax, 1
0x18006431c  jnz     short loc_180064313
0x18006431e  mov     r15d, [rbp+3Fh+arg_30]
0x180064322  cmp     [r14+30h], ebx
0x180064326  jz      loc_1800644E8
0x18006432c  mov     ebx, 800704C7h
0x180064331  mov     r13d, [rbp+3Fh+dwIoControlCode]
0x180064335  call    cs:__imp_GetTickCount64
0x18006433b  mov     rsi, rax
0x18006433e  sub     rsi, [rbp+3Fh+var_60]
0x180064342  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Location_Fix_GnssAdapterStatusTranslation@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Location_Fix_GnssAdapterStatusTranslation@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Location_Fix_GnssAdapterStatusTranslation> `wil::Feature<__WilFeatureTraits_Feature_Location_Fix_GnssAdapterStatusTranslation>::GetImpl(void)'::`2'::impl
0x180064349  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Location_Fix_GnssAdapterStatusTranslation@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Location_Fix_GnssAdapterStatusTranslation>::__private_IsEnabled(void)
0x18006434e  test    al, al
0x180064350  jz      loc_1800643FC
0x180064356  test    r15d, r15d
0x180064359  jz      loc_1800643FC
0x18006435f  mov     eax, cs:dword_1801DDF30
0x180064365  cmp     eax, 5
0x180064368  jbe     loc_1800643FC
0x18006436e  mov     rdx, 400000000000h
0x180064378  lea     rcx, dword_1801DDF30
0x18006437f  call    _tlgKeywordOn
0x180064384  test    al, al
0x180064386  jz      short loc_1800643FC
0x180064388  mov     eax, [rbp+3Fh+var_78]
0x18006438b  lea     rdx, byte_1801B001B
0x180064392  cmp     [rbp+3Fh+var_74], 0
0x180064396  mov     [rbp+3Fh+var_78], eax
0x180064399  mov     eax, [rbp+3Fh+arg_38]
0x18006439f  setnz   [rbp+3Fh+var_80]
0x1800643a3  mov     dword ptr [rbp+3Fh+var_68], eax
0x1800643a6  lea     rax, [rbp+3Fh+var_60]
0x1800643aa  mov     [rsp+0E0h+var_90], rax
0x1800643af  lea     rax, [rbp+3Fh+nInBufferSize]
0x1800643b3  mov     [rsp+0E0h+var_98], rax
0x1800643b8  lea     rax, [rbp+3Fh+dwIoControlCode]
0x1800643bc  mov     [rsp+0E0h+var_A0], rax
0x1800643c1  lea     rax, [rbp+3Fh+var_78]
0x1800643c5  mov     [rsp+0E0h+lpOverlapped], rax
0x1800643ca  lea     rax, [rbp+3Fh+var_80]
0x1800643ce  mov     [rsp+0E0h+lpBytesReturned], rax
0x1800643d3  lea     rax, [rbp+3Fh+var_74]
0x1800643d7  mov     qword ptr [rsp+0E0h+nOutBufferSize], rax
0x1800643dc  lea     rax, [rbp+3Fh+var_68]
0x1800643e0  mov     [rsp+0E0h+lpOutBuffer], rax
0x1800643e5  mov     [rbp+3Fh+var_60], 1000000h
0x1800643ed  mov     [rbp+3Fh+nInBufferSize], ebx
0x1800643f0  mov     [rbp+3Fh+dwIoControlCode], esi
0x1800643f3  mov     [rbp+3Fh+var_74], r13d
0x1800643f7  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$00@@U1@U1@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$00@@333AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x1800643fc  test    ebx, ebx
0x1800643fe  js      short loc_18006440D
0x180064400  cmp     rsi, 3A98h
0x180064407  jbe     loc_1800644AB
0x18006440d  test    cs:Microsoft_Windows_LocationServiceProviderEnableBits, 40h
0x180064414  mov     r12d, [rbp+3Fh+arg_38]
0x18006441b  jz      short loc_180064437
0x18006441d  mov     [rsp+0E0h+nOutBufferSize], esi
0x180064421  lea     rdx, GnssDriverIoctlResult
0x180064428  mov     r9d, r13d
0x18006442b  mov     dword ptr [rsp+0E0h+lpOutBuffer], ebx
0x18006442f  mov     r8d, r12d
0x180064432  call    McTemplateU0qqqq_EventWriteTransfer
0x180064437  mov     eax, cs:dword_1801DDF30
0x18006443d  cmp     eax, 4
0x180064440  jbe     short loc_1800644AB
0x180064442  mov     rdx, 200000000000h
0x18006444c  lea     rcx, dword_1801DDF30
0x180064453  call    _tlgKeywordOn
0x180064458  test    al, al
0x18006445a  jz      short loc_1800644AB
0x18006445c  lea     rax, [rbp+3Fh+var_60]
0x180064460  mov     [rbp+3Fh+var_60], 1000000h
0x180064468  mov     [rsp+0E0h+var_A0], rax
0x18006446d  lea     rdx, byte_1801B009B
0x180064474  lea     rax, [rbp+3Fh+var_68]
0x180064478  mov     dword ptr [rbp+3Fh+var_68], ebx
0x18006447b  mov     [rsp+0E0h+lpOverlapped], rax
0x180064480  lea     rax, [rbp+3Fh+nInBufferSize]
0x180064484  mov     [rsp+0E0h+lpBytesReturned], rax
0x180064489  lea     rax, [rbp+3Fh+var_74]
0x18006448d  mov     qword ptr [rsp+0E0h+nOutBufferSize], rax
0x180064492  lea     rax, [rbp+3Fh+var_78]
0x180064496  mov     [rsp+0E0h+lpOutBuffer], rax
0x18006449b  mov     [rbp+3Fh+nInBufferSize], esi
0x18006449e  mov     [rbp+3Fh+var_74], r13d
0x1800644a2  mov     [rbp+3Fh+var_78], r12d
0x1800644a6  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x1800644ab  test    r15d, r15d
0x1800644ae  jz      short loc_1800644C6
0x1800644b0  test    rdi, rdi
0x1800644b3  jz      short loc_1800644C6
0x1800644b5  and     qword ptr [rdi+18h], 0FFFFFFFFFFFFFFFEh
0x1800644ba  lea     rcx, [r14+58h]; this
0x1800644be  mov     rdx, rdi; Block
0x1800644c1  call    ?DeleteOverlapped@COverlappedList@@QEAAXPEAUGNSS_OVERLAPPED@@@Z; COverlappedList::DeleteOverlapped(GNSS_OVERLAPPED *)
0x1800644c6  mov     eax, ebx
0x1800644c8  mov     rcx, [rbp+3Fh+var_50]
0x1800644cc  xor     rcx, rsp; StackCookie
0x1800644cf  call    __security_check_cookie
0x1800644d4  add     rsp, 0A8h
0x1800644db  pop     r15
0x1800644dd  pop     r14
0x1800644df  pop     r13
0x1800644e1  pop     r12
0x1800644e3  pop     rdi
0x1800644e4  pop     rsi
0x1800644e5  pop     rbx
0x1800644e6  pop     rbp
0x1800644e7  retn
0x1800644e8  lea     rcx, [r14+58h]; this
0x1800644ec  mov     edx, r15d; int
0x1800644ef  lea     r8, [rbp+3Fh+var_68]; struct GNSS_OVERLAPPED **
0x1800644f3  call    ?CreateNewOverlapped@COverlappedList@@QEAAJHPEAPEAUGNSS_OVERLAPPED@@@Z; COverlappedList::CreateNewOverlapped(int,GNSS_OVERLAPPED * *)
0x1800644f8  mov     rdi, [rbp+3Fh+var_68]
0x1800644fc  mov     ebx, eax
0x1800644fe  test    eax, eax
0x180064500  js      loc_180064331
0x180064506  mov     eax, [rbp+3Fh+dwIoControlCode]
0x180064509  mov     [rdi+20h], eax
0x18006450c  mov     eax, [rbp+3Fh+arg_38]
0x180064512  mov     [rdi+24h], r15d
0x180064516  mov     [rdi+28h], eax
0x180064519  test    r15d, r15d
0x18006451c  jz      short loc_180064533
0x18006451e  mov     [rdi+0B20h], rsi
0x180064525  mov     [rdi+0B28h], r12d
0x18006452c  or      qword ptr [rdi+18h], 1
0x180064531  jmp     short loc_180064560
0x180064533  lea     rax, [rdi+30h]
0x180064537  mov     [rdi+0B20h], rax
0x18006453e  cmp     dword ptr [r14+84h], 6
0x180064546  sbb     eax, eax
0x180064548  and     eax, 0FFFFFFC0h
0x18006454b  add     eax, 0AF0h
0x180064550  mov     [rdi+0B28h], eax
0x180064556  mov     rcx, [r14+50h]; pio
0x18006455a  call    cs:__imp_StartThreadpoolIo
0x180064560  mov     rax, [r14+40h]
0x180064564  mov     edx, [rdi+0B28h]
0x18006456a  mov     r8, [rdi+0B20h]
0x180064571  test    rax, rax
0x180064574  jz      short loc_18006457B
0x180064576  mov     rcx, [rax]
0x180064579  jmp     short loc_18006457D
0x18006457b  xor     ecx, ecx; hDevice
0x18006457d  mov     r9d, [rbp+3Fh+nInBufferSize]; nInBufferSize
0x180064581  lea     rax, [rbp+3Fh+BytesReturned]
0x180064585  mov     [rsp+0E0h+lpOverlapped], rdi; lpOverlapped
0x18006458a  mov     [rsp+0E0h+lpBytesReturned], rax; lpBytesReturned
0x18006458f  mov     [rsp+0E0h+nOutBufferSize], edx; nOutBufferSize
0x180064593  mov     [rsp+0E0h+lpOutBuffer], r8; lpOutBuffer
0x180064598  mov     r8, r13; lpInBuffer
0x18006459b  mov     r13d, [rbp+3Fh+dwIoControlCode]
0x18006459f  mov     edx, r13d; dwIoControlCode
0x1800645a2  call    cs:__imp_DeviceIoControl
0x1800645a8  test    eax, eax
0x1800645aa  jnz     loc_18006469B
0x1800645b0  call    cs:__imp_GetLastError
0x1800645b6  cmp     eax, 3E5h
0x1800645bb  jz      short loc_1800645EA
0x1800645bd  test    r15d, r15d
0x1800645c0  jnz     short loc_1800645CC
0x1800645c2  mov     rcx, [r14+50h]; pio
0x1800645c6  call    cs:__imp_CancelThreadpoolIo
0x1800645cc  call    cs:__imp_GetLastError
0x1800645d2  mov     ebx, eax
0x1800645d4  test    eax, eax
0x1800645d6  jle     loc_180064335
0x1800645dc  movzx   ebx, ax
0x1800645df  or      ebx, 80070000h
0x1800645e5  jmp     loc_180064335
0x1800645ea  test    r15d, r15d
0x1800645ed  jz      loc_18006469B
0x1800645f3  lea     rsi, [r14+8]
0x1800645f7  mov     rcx, rsi; lpCriticalSection
0x1800645fa  call    cs:__imp_LeaveCriticalSection
0x180064600  mov     rax, [r14+40h]
0x180064604  test    rax, rax
0x180064607  jz      short loc_18006460E
0x180064609  mov     rcx, [rax]
0x18006460c  jmp     short loc_180064610
0x18006460e  xor     ecx, ecx; hFile
0x180064610  mov     r9d, 4E20h; dwMilliseconds
0x180064616  mov     dword ptr [rsp+0E0h+lpOutBuffer], 1; bAlertable
0x18006461e  lea     r8, [rbp+3Fh+BytesReturned]; lpNumberOfBytesTransferred
0x180064622  mov     rdx, rdi; lpOverlapped
0x180064625  call    cs:__imp_GetOverlappedResultEx
0x18006462b  mov     [rbp+3Fh+var_74], eax
0x18006462e  test    eax, eax
0x180064630  jnz     short loc_180064692
0x180064632  call    cs:__imp_GetLastError
0x180064638  mov     ebx, eax
0x18006463a  cmp     eax, 102h
0x18006463f  jnz     short loc_180064677
0x180064641  mov     rcx, [r14+40h]
0x180064645  test    rcx, rcx
0x180064648  jz      short loc_18006464D
0x18006464a  mov     rcx, [rcx]; hFile
0x18006464d  mov     rdx, rdi; lpOverlapped
0x180064650  call    cs:__imp_CancelIoEx
0x180064656  mov     rcx, [r14+40h]
0x18006465a  test    rcx, rcx
0x18006465d  jz      short loc_180064662
0x18006465f  mov     rcx, [rcx]; hFile
0x180064662  mov     r9d, 1; bWait
0x180064668  lea     r8, [rbp+3Fh+BytesReturned]; lpNumberOfBytesTransferred
0x18006466c  mov     rdx, rdi; lpOverlapped
0x18006466f  call    cs:__imp_GetOverlappedResult
0x180064675  jmp     short loc_18006467B
0x180064677  test    ebx, ebx
0x180064679  jle     short loc_180064684
0x18006467b  movzx   ebx, bx
0x18006467e  or      ebx, 80070000h
0x180064684  mov     rcx, rsi; lpCriticalSection
0x180064687  call    cs:__imp_EnterCriticalSection
0x18006468d  jmp     loc_180064335
0x180064692  mov     rcx, rsi; lpCriticalSection
0x180064695  call    cs:__imp_EnterCriticalSection
0x18006469b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Location_Fix_GnssAdapterStatusTranslation@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Location_Fix_GnssAdapterStatusTranslation@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Location_Fix_GnssAdapterStatusTranslation> `wil::Feature<__WilFeatureTraits_Feature_Location_Fix_GnssAdapterStatusTranslation>::GetImpl(void)'::`2'::impl
0x1800646a2  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Location_Fix_GnssAdapterStatusTranslation@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Location_Fix_GnssAdapterStatusTranslation>::__private_IsEnabled(void)
0x1800646a7  test    al, al
0x1800646a9  jz      short loc_1800646C6
0x1800646ab  test    r15d, r15d
0x1800646ae  jz      short loc_1800646C6
0x1800646b0  mov     eax, [rdi]
0x1800646b2  mov     [rbp+3Fh+var_78], eax
0x1800646b5  test    eax, eax
0x1800646b7  jns     short loc_1800646C6
0x1800646b9  mov     ecx, eax; Status
0x1800646bb  call    cs:__imp_RtlNtStatusToDosError
0x1800646c1  jmp     loc_1800645D2
0x1800646c6  xor     ebx, ebx
0x1800646c8  jmp     loc_180064335
```
