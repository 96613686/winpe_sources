# Microsoft::Bluetooth::Foundation::Details::DeviceInterfaceImpl::DeviceIoControlSynchronous(ulong,void const *,unsigned __int64,void *,unsigned __int64,unsigned __int64 *)

- ea: `0x1800542d0`
- end: `0x180054586`
- name: `?DeviceIoControlSynchronous@DeviceInterfaceImpl@Details@Foundation@Bluetooth@Microsoft@@UEAAJKPEBX_KPEAX1PEA_K@Z`
- size: `694`
- prototype: `__int64 __fastcall(Microsoft::Bluetooth::Foundation::Details::DeviceInterfaceImpl *__hidden this, DWORD dwIoControlCode, const void *lpInBuffer, DWORD nInBufferSize, void *, DWORD, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180004040`
- `0x1800040d8`
- `0x180005308`
- `0x18000751c`
- `0x180008d08`
- `0x18000e1cc`
- `0x180012554`
- `0x1800542d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180054349`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800544a7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180054349`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800544a7`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180054313`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180054313`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054321`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054449`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054534`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054321`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054449`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054534`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18005452a`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18005452a`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18005442c`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18005442c`

## pseudocode

```c
__int64 __fastcall Microsoft::Bluetooth::Foundation::Details::DeviceInterfaceImpl::DeviceIoControlSynchronous(
        Microsoft::Bluetooth::Foundation::Details::DeviceInterfaceImpl *this,
        DWORD dwIoControlCode,
        void *lpInBuffer,
        DWORD nInBufferSize,
        void *a5,
        DWORD nOutBufferSize,
        unsigned __int64 *a7)
{
  wil *v11; // rbx
  wil::details *v12; // rcx
  HANDLE Event; // rdi
  int v14; // edx
  int v15; // r8d
  void *v16; // rcx
  int LastErrorFailHr; // eax
  unsigned int v18; // edi
  __int64 v19; // r9
  __int64 v20; // rdx
  BOOL v21; // eax
  signed int LastError; // eax
  void *v23; // rdx
  unsigned int v24; // r8d
  int v25; // r9d
  int v26; // edx
  int v27; // r8d
  void *v28; // rcx
  signed int v29; // eax
  int lpOutBuffer; // [rsp+20h] [rbp-71h]
  DWORD BytesReturned; // [rsp+50h] [rbp-41h] BYREF
  char *v33; // [rsp+58h] [rbp-39h] BYREF
  wil *v34; // [rsp+60h] [rbp-31h] BYREF
  struct _OVERLAPPED Overlapped; // [rsp+68h] [rbp-29h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+47h]

  v11 = 0;
  v34 = 0;
  memset(&Overlapped, 0, sizeof(Overlapped));
  Event = CreateEventExW(0, 0, 0, 0x1F0003u);
  if ( Event )
  {
    GetLastError();
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      &v34,
      Event);
    v11 = v34;
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v12);
    v18 = LastErrorFailHr;
    if ( LastErrorFailHr < 0 )
    {
      v19 = (unsigned int)LastErrorFailHr;
      v20 = 314;
LABEL_23:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v20,
        (unsigned int)"onecore\\drivers\\bluetooth\\foundation\\lib\\deviceinterface.cpp",
        (const char *)v19,
        lpOutBuffer);
      goto LABEL_40;
    }
  }
  Overlapped.hEvent = v11;
  BytesReturned = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
  v16 = (void *)*((_QWORD *)this + 17);
  v33 = (char *)this + 96;
  if ( v16 == (void *)-1LL )
  {
    LOBYTE(v14) = WPP_GLOBAL_Control != &WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u;
    if ( (_BYTE)v14 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v15) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_q(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v14,
        v15,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        3,
        2,
        17,
        &WPP_e62633feb1923f1d4e65c173e11b2cbc_Traceguids,
        (char)this);
    }
LABEL_14:
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v33);
    v18 = -2147020577;
    goto LABEL_40;
  }
  v21 = DeviceIoControl(
          v16,
          dwIoControlCode,
          lpInBuffer,
          nInBufferSize,
          a5,
          nOutBufferSize,
          &BytesReturned,
          &Overlapped);
  if ( a7 )
    *a7 = BytesReturned;
  if ( v21 )
    goto LABEL_39;
  LastError = GetLastError();
  v18 = LastError;
  if ( LastError > 0 )
    v18 = (unsigned __int16)LastError | 0x80070000;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v33);
  if ( v18 == -2147023899 )
  {
    if ( !wil::handle_wait(v11, v23, v24, v25) )
    {
      v18 = -2147467259;
      v20 = 356;
      v19 = 2147500037LL;
      goto LABEL_23;
    }
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
    v28 = (void *)*((_QWORD *)this + 17);
    v33 = (char *)this + 96;
    if ( v28 == (void *)-1LL )
    {
      LOBYTE(v26) = WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
                 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u;
      if ( (_BYTE)v26 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v27) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_q(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v26,
          v27,
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          3,
          2,
          18,
          &WPP_e62633feb1923f1d4e65c173e11b2cbc_Traceguids,
          (char)this);
      }
      goto LABEL_14;
    }
    if ( !GetOverlappedResult(v28, &Overlapped, &BytesReturned, 0) )
    {
      v29 = GetLastError();
      v18 = v29;
      if ( v29 > 0 )
        v18 = (unsigned __int16)v29 | 0x80070000;
      wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v33);
      goto LABEL_40;
    }
    if ( a7 )
      *a7 = BytesReturned;
LABEL_39:
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v33);
    v18 = 0;
  }
LABEL_40:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v34);
  return v18;
}

```

## disassembly

```asm
0x1800542d0  push    rbp
0x1800542d2  push    rbx
0x1800542d3  push    rsi
0x1800542d4  push    rdi
0x1800542d5  push    r12
0x1800542d7  push    r13
0x1800542d9  push    r14
0x1800542db  push    r15
0x1800542dd  lea     rbp, [rsp-7]
0x1800542e2  sub     rsp, 98h
0x1800542e9  xorps   xmm0, xmm0
0x1800542ec  mov     r14, r9
0x1800542ef  mov     r12, r8
0x1800542f2  mov     r13d, edx
0x1800542f5  mov     r15, rcx
0x1800542f8  xor     ebx, ebx
0x1800542fa  mov     r9d, 1F0003h; dwDesiredAccess
0x180054300  mov     [rbp+3Fh+var_70], rbx
0x180054304  xor     r8d, r8d; dwFlags
0x180054307  xor     edx, edx; lpName
0x180054309  xor     ecx, ecx; lpEventAttributes
0x18005430b  movups  xmmword ptr [rbp+3Fh+Overlapped.Internal], xmm0
0x18005430f  movups  xmmword ptr [rbp+3Fh+Overlapped.10h], xmm0
0x180054313  call    cs:__imp_CreateEventExW
0x180054319  mov     rdi, rax
0x18005431c  test    rax, rax
0x18005431f  jz      short loc_180054387
0x180054321  call    cs:__imp_GetLastError
0x180054327  mov     rdx, rdi
0x18005432a  lea     rcx, [rbp+3Fh+var_70]
0x18005432e  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180054333  mov     rbx, [rbp+3Fh+var_70]
0x180054337  lea     rsi, [r15+60h]
0x18005433b  mov     [rbp+3Fh+Overlapped.hEvent], rbx
0x18005433f  mov     rcx, rsi; lpCriticalSection
0x180054342  mov     [rbp+3Fh+BytesReturned], 0
0x180054349  call    cs:__imp_EnterCriticalSection
0x18005434f  mov     rcx, [r15+88h]; hDevice
0x180054356  mov     [rbp+3Fh+var_78], rsi
0x18005435a  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18005435e  jnz     loc_180054401
0x180054364  mov     rcx, cs:WPP_GLOBAL_Control
0x18005436b  lea     rax, WPP_GLOBAL_Control
0x180054372  cmp     rcx, rax
0x180054375  jz      short loc_18005439F
0x180054377  test    byte ptr [rcx+1Ch], 2
0x18005437b  jz      short loc_18005439F
0x18005437d  cmp     byte ptr [rcx+19h], 3
0x180054381  jb      short loc_18005439F
0x180054383  mov     dl, 1
0x180054385  jmp     short loc_1800543A1
0x180054387  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18005438c  mov     edi, eax
0x18005438e  test    eax, eax
0x180054390  jns     short loc_180054337
0x180054392  mov     r9d, eax
0x180054395  mov     edx, 13Ah
0x18005439a  jmp     loc_18005448F
0x18005439f  xor     dl, dl; int
0x1800543a1  lea     rax, WPP_RECORDER_INITIALIZED
0x1800543a8  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1800543af  setnz   r8b; int
0x1800543b3  test    dl, dl
0x1800543b5  jnz     short loc_1800543BC
0x1800543b7  test    r8b, r8b
0x1800543ba  jz      short loc_1800543EE
0x1800543bc  mov     qword ptr [rsp+0D0h+var_90], r15; char
0x1800543c1  lea     rax, WPP_e62633feb1923f1d4e65c173e11b2cbc_Traceguids
0x1800543c8  mov     [rsp+0D0h+lpOverlapped], rax; MessageGuid
0x1800543cd  mov     word ptr [rsp+0D0h+lpBytesReturned], 11h; __int16
0x1800543d4  mov     r9, [rcx+28h]; int
0x1800543d8  mov     rcx, [rcx+10h]; int
0x1800543dc  mov     [rsp+0D0h+nOutBufferSize], 2; int
0x1800543e4  mov     byte ptr [rsp+0D0h+lpOutBuffer], 3; char
0x1800543e9  call    WPP_RECORDER_AND_TRACE_SF_q
0x1800543ee  lea     rcx, [rbp+3Fh+var_78]
0x1800543f2  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x1800543f7  mov     edi, 800710DFh
0x1800543fc  jmp     loc_180054567
0x180054401  mov     eax, [rbp+3Fh+arg_28]
0x180054404  lea     rdx, [rbp+3Fh+Overlapped]
0x180054408  mov     [rsp+0D0h+lpOverlapped], rdx; lpOverlapped
0x18005440d  mov     r9d, r14d; nInBufferSize
0x180054410  lea     rdx, [rbp+3Fh+BytesReturned]
0x180054414  mov     r8, r12; lpInBuffer
0x180054417  mov     [rsp+0D0h+lpBytesReturned], rdx; lpBytesReturned
0x18005441c  mov     edx, r13d; dwIoControlCode
0x18005441f  mov     [rsp+0D0h+nOutBufferSize], eax; nOutBufferSize
0x180054423  mov     rax, [rbp+3Fh+arg_20]
0x180054427  mov     [rsp+0D0h+lpOutBuffer], rax; int
0x18005442c  call    cs:__imp_DeviceIoControl
0x180054432  mov     r14, [rbp+3Fh+arg_30]
0x180054436  test    r14, r14
0x180054439  jz      short loc_180054441
0x18005443b  mov     ecx, [rbp+3Fh+BytesReturned]
0x18005443e  mov     [r14], rcx
0x180054441  test    eax, eax
0x180054443  jnz     loc_18005455C
0x180054449  call    cs:__imp_GetLastError
0x18005444f  mov     edi, eax
0x180054451  mov     r12d, 80070000h
0x180054457  test    eax, eax
0x180054459  jle     short loc_180054461
0x18005445b  movzx   edi, ax
0x18005445e  or      edi, r12d
0x180054461  lea     rcx, [rbp+3Fh+var_78]
0x180054465  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18005446a  cmp     edi, 800703E5h
0x180054470  jnz     loc_180054567
0x180054476  mov     rcx, rbx; this
0x180054479  call    ?handle_wait@wil@@YA_NPEAXKH@Z; wil::handle_wait(void *,ulong,int)
0x18005447e  test    al, al
0x180054480  jnz     short loc_1800544A4
0x180054482  mov     edi, 80004005h
0x180054487  mov     edx, 164h; void *
0x18005448c  mov     r9d, edi; char *
0x18005448f  mov     rcx, [rbp+47h]; this
0x180054493  lea     r8, aOnecoreDrivers_16; "onecore\\drivers\\bluetooth\\foundation"...
0x18005449a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005449f  jmp     loc_180054567
0x1800544a4  mov     rcx, rsi; lpCriticalSection
0x1800544a7  call    cs:__imp_EnterCriticalSection
0x1800544ad  mov     rcx, [r15+88h]; hFile
0x1800544b4  mov     [rbp+3Fh+var_78], rsi
0x1800544b8  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800544bc  jnz     short loc_18005451F
0x1800544be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800544c5  lea     rax, WPP_GLOBAL_Control
0x1800544cc  cmp     rcx, rax
0x1800544cf  jz      short loc_1800544E1
0x1800544d1  test    byte ptr [rcx+1Ch], 2
0x1800544d5  jz      short loc_1800544E1
0x1800544d7  cmp     byte ptr [rcx+19h], 3
0x1800544db  jb      short loc_1800544E1
0x1800544dd  mov     dl, 1
0x1800544df  jmp     short loc_1800544E3
0x1800544e1  xor     dl, dl
0x1800544e3  lea     rax, WPP_RECORDER_INITIALIZED
0x1800544ea  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1800544f1  setnz   r8b
0x1800544f5  test    dl, dl
0x1800544f7  jnz     short loc_180054502
0x1800544f9  test    r8b, r8b
0x1800544fc  jz      loc_1800543EE
0x180054502  mov     qword ptr [rsp+0D0h+var_90], r15
0x180054507  lea     rax, WPP_e62633feb1923f1d4e65c173e11b2cbc_Traceguids
0x18005450e  mov     [rsp+0D0h+lpOverlapped], rax
0x180054513  mov     word ptr [rsp+0D0h+lpBytesReturned], 12h
0x18005451a  jmp     loc_1800543D4
0x18005451f  xor     r9d, r9d; bWait
0x180054522  lea     r8, [rbp+3Fh+BytesReturned]; lpNumberOfBytesTransferred
0x180054526  lea     rdx, [rbp+3Fh+Overlapped]; lpOverlapped
0x18005452a  call    cs:__imp_GetOverlappedResult
0x180054530  test    eax, eax
0x180054532  jnz     short loc_180054551
0x180054534  call    cs:__imp_GetLastError
0x18005453a  mov     edi, eax
0x18005453c  test    eax, eax
0x18005453e  jle     short loc_180054546
0x180054540  movzx   edi, ax
0x180054543  or      edi, r12d
0x180054546  lea     rcx, [rbp+3Fh+var_78]
0x18005454a  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18005454f  jmp     short loc_180054567
0x180054551  test    r14, r14
0x180054554  jz      short loc_18005455C
0x180054556  mov     eax, [rbp+3Fh+BytesReturned]
0x180054559  mov     [r14], rax
0x18005455c  lea     rcx, [rbp+3Fh+var_78]
0x180054560  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180054565  xor     edi, edi
0x180054567  lea     rcx, [rbp+3Fh+var_70]
0x18005456b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180054570  mov     eax, edi
0x180054572  add     rsp, 98h
0x180054579  pop     r15
0x18005457b  pop     r14
0x18005457d  pop     r13
0x18005457f  pop     r12
0x180054581  pop     rdi
0x180054582  pop     rsi
0x180054583  pop     rbx
0x180054584  pop     rbp
0x180054585  retn
```
