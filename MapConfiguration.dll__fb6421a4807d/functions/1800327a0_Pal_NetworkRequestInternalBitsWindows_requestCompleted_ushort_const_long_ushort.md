# Pal::NetworkRequestInternalBitsWindows::requestCompleted(ushort const *,long,ushort *)

- ea: `0x1800327a0`
- end: `0x180032ca2`
- name: `?requestCompleted@NetworkRequestInternalBitsWindows@Pal@@AEAAXPEBGJPEAG@Z`
- size: `1282`
- prototype: `void(Pal::NetworkRequestInternalBitsWindows *__hidden this, const unsigned __int16 *, int, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `30`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18002e8e0`

## callees

- `0x1800094a0`
- `0x18000a074`
- `0x18000a080`
- `0x18000c2f8`
- `0x18000cd80`
- `0x180010b50`
- `0x180011500`
- `0x18001154c`
- `0x180011f04`
- `0x180012438`
- `0x180013da8`
- `0x180014de4`
- `0x18001a7a8`
- `0x18001bd20`
- `0x18001be00`
- `0x18001bed4`
- `0x18002a30c`
- `0x18002c330`
- `0x18002dd88`
- `0x18002dfa8`
- `0x18002e8fc`
- `0x18002f61c`
- `0x18002f6e8`
- `0x18002f730`
- `0x18002f858`
- `0x180030298`
- `0x180030548`
- `0x1800309a4`
- `0x18003224c`
- `0x1800327a0`

## import_xrefs

- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z` at `0x180032aa6`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z` at `0x180032aa6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003288c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800328d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003288c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800328d2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180032886`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180032886`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18003298d`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18003298d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180032b63`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180032b63`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180032c22`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180032c22`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x1800328be`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x1800328be`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180032b4e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180032b4e`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18003289a`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18003289a`

## string_xrefs

- `0x180032997`: `Failed to read the file`
- `0x1800328e1`: `Failed to open file`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall Pal::NetworkRequestInternalBitsWindows::requestCompleted(
        Pal::NetworkRequestInternalBitsWindows *this,
        const unsigned __int16 *a2,
        int a3,
        unsigned __int16 *a4)
{
  std::_Ref_count_base *v7; // r13
  __int64 File2; // r15
  char *v9; // rsi
  RTL_SRWLOCK *Instance; // rax
  __int64 *v11; // rax
  int v12; // edi
  __int64 v13; // r14
  __int64 v14; // rsi
  unsigned __int64 v15; // rdi
  __int64 v16; // rdx
  __int64 v17; // r12
  unsigned __int64 v18; // rcx
  size_t v19; // rax
  size_t v20; // rdi
  __int64 v21; // rsi
  __int64 v22; // rdx
  __int64 v23; // r12
  unsigned __int64 v24; // rcx
  size_t v25; // rax
  size_t v26; // rdi
  __int64 v27; // rsi
  RTL_SRWLOCK *v28; // rax
  const unsigned __int16 *v29; // rax
  __int64 v30; // rax
  unsigned __int64 v31; // rdx
  unsigned __int8 v32; // cl
  __int64 v33; // rcx
  __int64 v34; // rcx
  __int64 *v35; // rax
  __int64 v36; // rax
  RTL_SRWLOCK *v37; // rax
  __int64 *v38; // rax
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp-1F8h] BYREF
  __int64 v40; // [rsp+48h] [rbp-1F0h] BYREF
  unsigned __int16 *v41; // [rsp+50h] [rbp-1E8h] BYREF
  __int64 *v42; // [rsp+58h] [rbp-1E0h] BYREF
  __int64 v43; // [rsp+60h] [rbp-1D8h] BYREF
  __int64 v44; // [rsp+68h] [rbp-1D0h] BYREF
  __int64 v45; // [rsp+70h] [rbp-1C8h] BYREF
  char *v46; // [rsp+78h] [rbp-1C0h]
  std::_Ref_count_base *v47[2]; // [rsp+80h] [rbp-1B8h] BYREF
  std::_Ref_count_base *v48[2]; // [rsp+90h] [rbp-1A8h] BYREF
  const std::exception *v49; // [rsp+A0h] [rbp-198h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+A8h] [rbp-190h] BYREF
  _BYTE v51[24]; // [rsp+C0h] [rbp-178h] BYREF
  _BYTE v52[40]; // [rsp+D8h] [rbp-160h] BYREF
  _BYTE v53[8]; // [rsp+100h] [rbp-138h] BYREF
  _BYTE v54[232]; // [rsp+108h] [rbp-130h] BYREF

  v7 = this;
  v47[0] = this;
  v41 = a4;
  File2 = -1;
  v43 = -1;
  *(_OWORD *)v48 = 0;
  v45 = 0;
  v44 = 0;
  NumberOfBytesRead = 1;
  v9 = (char *)this + 96;
  v46 = (char *)this + 96;
  v42 = (__int64 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 96);
  Instance = (RTL_SRWLOCK *)Pal::PerformanceTracerSingleton<Pal::PalPerformanceTracer>::getInstance();
  Pal::PerformanceTracer::traceEvent<unsigned short const * &,unsigned int &>(
    Instance,
    (struct Pal::PerformanceEventId *)&dword_18007B9C0);
  try
  {
    std::make_unique<std::vector<unsigned char>,,0>(&v42);
    if ( a3 < 0 )
    {
      v29 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v9);
      Pal::PalPerformanceTracer::traceNetworkRequestError(v29, a3);
      std::ostringstream::ostringstream((__int64)v53);
      v30 = std::operator<<<std::char_traits<char>>((__int64)v53, (__int64)"Network request failed with error code 0x");
      std::ostream::operator<<(v30, (unsigned int)a3);
      if ( NetworkRequestWindowsTelemetry::IsEnabled(v32, v31) )
      {
        wil::details::static_lazy<NetworkRequestWindowsTelemetry>::get(
          v33,
          _lambda_e3c00d5e223e442e613a1a5c804f6f5c_::_lambda_invoker_cdecl_);
        NetworkRequestWindowsTelemetry::TraceBingBitsHttpRequest_(v34, v9, (unsigned int)a3);
      }
      std::stringbuf::str(v54, v52);
      v35 = std::make_unique<Pal::NetworkException,std::string,0>(&v41, (__int64)v52);
      std::unique_ptr<Pal::NetworkException>::operator=<std::default_delete<Pal::NetworkException>,0>(&v45, v35);
      std::unique_ptr<Pal::NetworkRequestImpl>::~unique_ptr<Pal::NetworkRequestImpl>(&v41);
      std::string::_Tidy_deallocate(v52);
      std::ostringstream::`vbase destructor'(v53);
      v27 = (__int64)v46;
      goto LABEL_34;
    }
    if ( a4 )
    {
      v11 = std::make_unique<Pal::NetworkResponseHeadersBits,unsigned short * &,0>(&v40, &v41);
      std::unique_ptr<Pal::NetworkException>::operator=<std::default_delete<Pal::NetworkException>,0>(&v44, v11);
      std::unique_ptr<Pal::NetworkRequestImpl>::~unique_ptr<Pal::NetworkRequestImpl>(&v40);
    }
    v12 = 1000;
    SetLastError(0);
    while ( 1 )
    {
      if ( GetLastError() == 32 )
      {
        Sleep(0x64u);
        v12 -= 100;
      }
      File2 = CreateFile2(a2, 0x80000000LL, 1);
      v43 = File2;
      if ( File2 != -1 )
        break;
      if ( GetLastError() != 32 || v12 <= 0 )
      {
        std::runtime_error::runtime_error((std::runtime_error *)pExceptionObject, "Failed to open file");
        throw (std::runtime_error *)pExceptionObject;
      }
    }
    LODWORD(v13) = 0;
    NumberOfBytesRead = 0;
    while ( 1 )
    {
      v14 = (__int64)v42;
      v15 = (unsigned int)(v13 + 0x2000);
      v16 = *v42;
      v17 = v42[1];
      v18 = v17 - *v42;
      if ( v15 < v18 )
        break;
      if ( v15 > v18 )
      {
        if ( v15 <= v42[2] - v16 )
        {
          v20 = v15 - v18;
          memset_0((void *)v42[1], 0, v20);
          v19 = v20 + v17;
          goto LABEL_19;
        }
        std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(v42, (unsigned int)(v13 + 0x2000));
      }
LABEL_20:
      if ( !ReadFile((HANDLE)File2, (LPVOID)(*v42 + (unsigned int)v13), 0x2000u, &NumberOfBytesRead, 0) )
      {
        std::runtime_error::runtime_error((std::runtime_error *)v51, "Failed to read the file");
        throw (std::runtime_error *)v51;
      }
      v13 = NumberOfBytesRead + (unsigned int)v13;
      if ( NumberOfBytesRead != 0x2000 )
      {
        v21 = (__int64)v42;
        v22 = *v42;
        v23 = v42[1];
        v24 = v23 - *v42;
        if ( (unsigned int)v13 < v24 )
        {
          v25 = v22 + v13;
          goto LABEL_29;
        }
        if ( (unsigned int)v13 > v24 )
        {
          if ( (unsigned int)v13 <= (unsigned __int64)(v42[2] - v22) )
          {
            v26 = (unsigned int)v13 - v24;
            memset_0((void *)v42[1], 0, v26);
            v25 = v26 + v23;
LABEL_29:
            *(_QWORD *)(v21 + 8) = v25;
          }
          else
          {
            std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(v42, (unsigned int)v13);
          }
        }
        std::shared_ptr<std::vector<unsigned char> const>::operator=<std::vector<unsigned char>,std::default_delete<std::vector<unsigned char>>,0>(
          v48,
          (__int64 *)&v42);
        LODWORD(v40) = v13;
        v27 = (__int64)v46;
        v41 = (unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v46);
        v28 = (RTL_SRWLOCK *)Pal::PerformanceTracerSingleton<Pal::PalPerformanceTracer>::getInstance();
        Pal::PerformanceTracer::traceEvent<unsigned short const * &,unsigned int &>(
          v28,
          (struct Pal::PerformanceEventId *)&dword_18007B930);
LABEL_34:
        std::unique_ptr<std::vector<unsigned char>>::~unique_ptr<std::vector<unsigned char>>(&v42);
        goto LABEL_44;
      }
    }
    v19 = v16 + (unsigned int)(v13 + 0x2000);
LABEL_19:
    *(_QWORD *)(v14 + 8) = v19;
    goto LABEL_20;
  }
  catch ( const std::exception *v49 )
  {
    v41 = (unsigned __int16 *)(*(__int64 (__fastcall **)(const std::exception *))(*(_QWORD *)v49 + 8LL))(v49);
    v38 = std::make_unique<Pal::NetworkException,char const *,0>(&v40, &v41);
    std::unique_ptr<Pal::NetworkException>::operator=<std::default_delete<Pal::NetworkException>,0>(&v45, v38);
    std::unique_ptr<Pal::NetworkRequestImpl>::~unique_ptr<Pal::NetworkRequestImpl>(&v40);
    File2 = v43;
    v7 = v47[0];
    v27 = (__int64)v46;
  }
LABEL_44:
  CloseHandle((HANDLE)File2);
  v41 = (unsigned __int16 *)((char *)v7 + 160);
  EnterCriticalSection((LPCRITICAL_SECTION)v7 + 4);
  if ( *((_DWORD *)v7 + 50) != 2 )
  {
    *((_DWORD *)v7 + 50) = 3;
    v36 = v44;
    v44 = 0;
    v43 = v36;
    Pal::NetworkResponse::NetworkResponse((__int64)v53, v27, v48, &v43, v45, 0);
    std::_Func_class<void,>::operator()((char *)v7 + 208, v53);
    LODWORD(v40) = 1;
    v47[0] = (std::_Ref_count_base *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v27);
    v37 = (RTL_SRWLOCK *)Pal::PerformanceTracerSingleton<Pal::PalPerformanceTracer>::getInstance();
    Pal::PerformanceTracer::traceEvent<unsigned short const * &,unsigned int &>(
      v37,
      (struct Pal::PerformanceEventId *)&dword_18007B9F0);
    Pal::NetworkResponse::~NetworkResponse((Pal::NetworkResponse *)v53);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)v7 + 4);
  *(_OWORD *)v47 = 0;
  std::shared_ptr<Pal::NetworkRequestInternalWinHttp>::operator=((char *)v7 + 80, v47);
  if ( v47[1] )
    std::_Ref_count_base::_Decref(v47[1]);
  std::unique_ptr<Pal::NetworkRequestImpl>::~unique_ptr<Pal::NetworkRequestImpl>(&v44);
  std::unique_ptr<Pal::NetworkRequestImpl>::~unique_ptr<Pal::NetworkRequestImpl>(&v45);
  if ( v48[1] )
    std::_Ref_count_base::_Decref(v48[1]);
}

```

## disassembly

```asm
0x1800327a0  push    rsi
0x1800327a2  push    rdi
0x1800327a3  push    r12
0x1800327a5  push    r13
0x1800327a7  push    r14
0x1800327a9  push    r15
0x1800327ab  sub     rsp, 208h
0x1800327b2  mov     rax, cs:__security_cookie
0x1800327b9  xor     rax, rsp
0x1800327bc  mov     [rsp+238h+var_48], rax
0x1800327c4  mov     r14, r9
0x1800327c7  mov     edi, r8d
0x1800327ca  mov     r12, rdx
0x1800327cd  mov     r13, rcx
0x1800327d0  mov     [rsp+238h+var_1B8], rcx
0x1800327d8  mov     [rsp+238h+var_1E8], r9
0x1800327dd  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800327e1  mov     [rsp+238h+var_1D8], r15
0x1800327e6  xorps   xmm0, xmm0
0x1800327e9  movdqu  xmmword ptr [rsp+238h+var_1A8], xmm0
0x1800327f2  mov     [rsp+238h+var_1C8], 0
0x1800327fb  mov     [rsp+238h+var_1D0], 0
0x180032804  mov     [rsp+238h+NumberOfBytesRead], 1
0x18003280c  lea     rsi, [rcx+60h]
0x180032810  mov     [rsp+238h+var_1C0], rsi
0x180032815  mov     rcx, rsi
0x180032818  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003281d  mov     [rsp+238h+var_1E0], rax
0x180032822  call    ?getInstance@?$PerformanceTracerSingleton@VPalPerformanceTracer@Pal@@@Pal@@KAAEAVPalPerformanceTracer@2@XZ; Pal::PerformanceTracerSingleton<Pal::PalPerformanceTracer>::getInstance(void)
0x180032827  lea     r9, [rsp+238h+NumberOfBytesRead]
0x18003282c  lea     r8, [rsp+238h+var_1E0]
0x180032831  lea     rdx, dword_18007B9C0; struct Pal::PerformanceEventId *
0x180032838  mov     rcx, rax; SRWLock
0x18003283b  call    ??$traceEvent@AEAPEBGAEAI@PerformanceTracer@Pal@@QEAAXAEBVPerformanceEventId@1@AEAPEBGAEAI@Z; Pal::PerformanceTracer::traceEvent<ushort const * &,uint &>(Pal::PerformanceEventId const &,ushort const * &,uint &)
0x180032840  nop
0x180032841  lea     rcx, [rsp+238h+var_1E0]
0x180032846  call    ??$make_unique@V?$vector@EV?$allocator@E@std@@@std@@$$V$0A@@std@@YA?AV?$unique_ptr@V?$vector@EV?$allocator@E@std@@@std@@U?$default_delete@V?$vector@EV?$allocator@E@std@@@std@@@2@@0@XZ; std::make_unique<std::vector<uchar>,,0>(void)
0x18003284b  nop
0x18003284c  test    edi, edi
0x18003284e  js      loc_180032A6D
0x180032854  test    r14, r14
0x180032857  jz      short loc_18003287F
0x180032859  lea     rdx, [rsp+238h+var_1E8]
0x18003285e  lea     rcx, [rsp+238h+var_1F0]
0x180032863  call    ??$make_unique@VNetworkResponseHeadersBits@Pal@@AEAPEAG$0A@@std@@YA?AV?$unique_ptr@VNetworkResponseHeadersBits@Pal@@U?$default_delete@VNetworkResponseHeadersBits@Pal@@@std@@@0@AEAPEAG@Z; std::make_unique<Pal::NetworkResponseHeadersBits,ushort * &,0>(ushort * &)
0x180032868  mov     rdx, rax
0x18003286b  lea     rcx, [rsp+238h+var_1D0]
0x180032870  call    ??$?4U?$default_delete@VNetworkException@Pal@@@std@@$0A@@?$unique_ptr@VNetworkException@Pal@@U?$default_delete@VNetworkException@Pal@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<Pal::NetworkException>::operator=<std::default_delete<Pal::NetworkException>,0>(std::unique_ptr<Pal::NetworkException> &&)
0x180032875  lea     rcx, [rsp+238h+var_1F0]
0x18003287a  call    ??1?$unique_ptr@VNetworkRequestImpl@Pal@@U?$default_delete@VNetworkRequestImpl@Pal@@@std@@@std@@QEAA@XZ; std::unique_ptr<Pal::NetworkRequestImpl>::~unique_ptr<Pal::NetworkRequestImpl>(void)
0x18003287f  mov     edi, 3E8h
0x180032884  xor     ecx, ecx; dwErrCode
0x180032886  call    cs:__imp_SetLastError
0x18003288c  call    cs:__imp_GetLastError
0x180032892  cmp     eax, 20h ; ' '
0x180032895  jnz     short loc_1800328A3
0x180032897  lea     ecx, [rax+44h]; dwMilliseconds
0x18003289a  call    cs:__imp_Sleep
0x1800328a0  sub     edi, 64h ; 'd'
0x1800328a3  mov     [rsp+238h+lpOverlapped], 0
0x1800328ac  mov     edx, 80000000h
0x1800328b1  mov     r9d, 3
0x1800328b7  lea     r8d, [r9-2]
0x1800328bb  mov     rcx, r12
0x1800328be  call    cs:__imp_CreateFile2
0x1800328c4  mov     r15, rax
0x1800328c7  mov     [rsp+238h+var_1D8], rax
0x1800328cc  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800328d0  jnz     short loc_180032909
0x1800328d2  call    cs:__imp_GetLastError
0x1800328d8  cmp     eax, 20h ; ' '
0x1800328db  jnz     short loc_1800328E1
0x1800328dd  test    edi, edi
0x1800328df  jg      short loc_18003288C
0x1800328e1  lea     rdx, aFailedToOpenFi; "Failed to open file"
0x1800328e8  lea     rcx, [rsp+238h+pExceptionObject]; this
0x1800328f0  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x1800328f5  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x1800328fc  lea     rcx, [rsp+238h+pExceptionObject]; pExceptionObject
0x180032904  call    _CxxThrowException_0
0x180032909  xor     r14d, r14d
0x18003290c  mov     [rsp+238h+NumberOfBytesRead], r14d
0x180032911  mov     rsi, [rsp+238h+var_1E0]
0x180032916  lea     eax, [r14+2000h]
0x18003291d  mov     edi, eax
0x18003291f  mov     rdx, [rsi]
0x180032922  mov     r12, [rsi+8]
0x180032926  mov     rcx, r12
0x180032929  sub     rcx, rdx
0x18003292c  cmp     rdi, rcx
0x18003292f  jnb     short loc_180032936
0x180032931  add     rax, rdx
0x180032934  jmp     short loc_180032965
0x180032936  jbe     short loc_180032969
0x180032938  mov     rax, [rsi+10h]
0x18003293c  sub     rax, rdx
0x18003293f  cmp     rdi, rax
0x180032942  jbe     short loc_180032951
0x180032944  mov     rdx, rdi
0x180032947  mov     rcx, rsi
0x18003294a  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18003294f  jmp     short loc_180032969
0x180032951  sub     rdi, rcx
0x180032954  mov     r8, rdi; Size
0x180032957  xor     edx, edx; Val
0x180032959  mov     rcx, r12; void *
0x18003295c  call    memset_0
0x180032961  lea     rax, [rdi+r12]
0x180032965  mov     [rsi+8], rax
0x180032969  mov     edx, r14d
0x18003296c  mov     rax, [rsp+238h+var_1E0]
0x180032971  add     rdx, [rax]; lpBuffer
0x180032974  mov     [rsp+238h+lpOverlapped], 0; lpOverlapped
0x18003297d  lea     r9, [rsp+238h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180032982  mov     edi, 2000h
0x180032987  mov     r8d, edi; nNumberOfBytesToRead
0x18003298a  mov     rcx, r15; hFile
0x18003298d  call    cs:__imp_ReadFile
0x180032993  test    eax, eax
0x180032995  jnz     short loc_1800329BF
0x180032997  lea     rdx, aFailedToReadTh; "Failed to read the file"
0x18003299e  lea     rcx, [rsp+238h+var_178]; this
0x1800329a6  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x1800329ab  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x1800329b2  lea     rcx, [rsp+238h+var_178]; pExceptionObject
0x1800329ba  call    _CxxThrowException_0
0x1800329bf  add     r14d, [rsp+238h+NumberOfBytesRead]
0x1800329c4  cmp     [rsp+238h+NumberOfBytesRead], edi
0x1800329c8  jz      loc_180032911
0x1800329ce  mov     rsi, [rsp+238h+var_1E0]
0x1800329d3  mov     rdx, [rsi]
0x1800329d6  mov     r12, [rsi+8]
0x1800329da  mov     rcx, r12
0x1800329dd  sub     rcx, rdx
0x1800329e0  mov     edi, r14d
0x1800329e3  cmp     rdi, rcx
0x1800329e6  jnb     short loc_1800329EE
0x1800329e8  lea     rax, [rdx+r14]
0x1800329ec  jmp     short loc_180032A1D
0x1800329ee  jbe     short loc_180032A21
0x1800329f0  mov     rax, [rsi+10h]
0x1800329f4  sub     rax, rdx
0x1800329f7  cmp     rdi, rax
0x1800329fa  jbe     short loc_180032A09
0x1800329fc  mov     rdx, rdi
0x1800329ff  mov     rcx, rsi
0x180032a02  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180032a07  jmp     short loc_180032A21
0x180032a09  sub     rdi, rcx
0x180032a0c  mov     r8, rdi; Size
0x180032a0f  xor     edx, edx; Val
0x180032a11  mov     rcx, r12; void *
0x180032a14  call    memset_0
0x180032a19  lea     rax, [rdi+r12]
0x180032a1d  mov     [rsi+8], rax
0x180032a21  lea     rdx, [rsp+238h+var_1E0]
0x180032a26  lea     rcx, [rsp+238h+var_1A8]
0x180032a2e  call    ??$?4V?$vector@EV?$allocator@E@std@@@std@@U?$default_delete@V?$vector@EV?$allocator@E@std@@@std@@@1@$0A@@?$shared_ptr@$$CBV?$vector@EV?$allocator@E@std@@@std@@@std@@QEAAAEAV01@$$QEAV?$unique_ptr@V?$vector@EV?$allocator@E@std@@@std@@U?$default_delete@V?$vector@EV?$allocator@E@std@@@std@@@2@@1@@Z; std::shared_ptr<std::vector<uchar> const>::operator=<std::vector<uchar>,std::default_delete<std::vector<uchar>>,0>(std::unique_ptr<std::vector<uchar>> &&)
0x180032a33  mov     dword ptr [rsp+238h+var_1F0], r14d
0x180032a38  mov     rsi, [rsp+238h+var_1C0]
0x180032a3d  mov     rcx, rsi
0x180032a40  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180032a45  mov     [rsp+238h+var_1E8], rax
0x180032a4a  call    ?getInstance@?$PerformanceTracerSingleton@VPalPerformanceTracer@Pal@@@Pal@@KAAEAVPalPerformanceTracer@2@XZ; Pal::PerformanceTracerSingleton<Pal::PalPerformanceTracer>::getInstance(void)
0x180032a4f  lea     r9, [rsp+238h+var_1F0]
0x180032a54  lea     r8, [rsp+238h+var_1E8]
0x180032a59  lea     rdx, dword_18007B930; struct Pal::PerformanceEventId *
0x180032a60  mov     rcx, rax; SRWLock
0x180032a63  call    ??$traceEvent@AEAPEBGAEAI@PerformanceTracer@Pal@@QEAAXAEBVPerformanceEventId@1@AEAPEBGAEAI@Z; Pal::PerformanceTracer::traceEvent<ushort const * &,uint &>(Pal::PerformanceEventId const &,ushort const * &,uint &)
0x180032a68  jmp     loc_180032B2C
0x180032a6d  mov     rcx, rsi
0x180032a70  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180032a75  mov     edx, edi; int
0x180032a77  mov     rcx, rax; unsigned __int16 *
0x180032a7a  call    ?traceNetworkRequestError@PalPerformanceTracer@Pal@@SAXPEBGH@Z; Pal::PalPerformanceTracer::traceNetworkRequestError(ushort const *,int)
0x180032a7f  lea     rcx, [rsp+238h+var_138]
0x180032a87  call    ??0?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::ostringstream::ostringstream(void)
0x180032a8c  nop
0x180032a8d  lea     rdx, aNetworkRequest; "Network request failed with error code "...
0x180032a94  lea     rcx, [rsp+238h+var_138]
0x180032a9c  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180032aa1  mov     edx, edi
0x180032aa3  mov     rcx, rax
0x180032aa6  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z; std::ostream::operator<<(long)
0x180032aac  call    ?IsEnabled@NetworkRequestWindowsTelemetry@@SA_NE_K@Z; NetworkRequestWindowsTelemetry::IsEnabled(uchar,unsigned __int64)
0x180032ab1  test    al, al
0x180032ab3  jz      short loc_180032ACC
0x180032ab5  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_e3c00d5e223e442e613a1a5c804f6f5c_@@CA@XZ; _lambda_e3c00d5e223e442e613a1a5c804f6f5c_::_lambda_invoker_cdecl_(void)
0x180032abc  call    ?get@?$static_lazy@VNetworkRequestWindowsTelemetry@@@details@wil@@QEAAPEAVNetworkRequestWindowsTelemetry@@P6AXXZ@Z; wil::details::static_lazy<NetworkRequestWindowsTelemetry>::get(void (*)(void))
0x180032ac1  mov     r8d, edi
0x180032ac4  mov     rdx, rsi
0x180032ac7  call    ?TraceBingBitsHttpRequest_@NetworkRequestWindowsTelemetry@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@J@Z; NetworkRequestWindowsTelemetry::TraceBingBitsHttpRequest_(std::wstring const &,long)
0x180032acc  lea     rdx, [rsp+238h+var_160]
0x180032ad4  lea     rcx, [rsp+238h+var_130]
0x180032adc  call    ?str@?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::stringbuf::str(void)
0x180032ae1  nop
0x180032ae2  lea     rdx, [rsp+238h+var_160]
0x180032aea  lea     rcx, [rsp+238h+var_1E8]
0x180032aef  call    ??$make_unique@VNetworkException@Pal@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@$0A@@std@@YA?AV?$unique_ptr@VNetworkException@Pal@@U?$default_delete@VNetworkException@Pal@@@std@@@0@$$QEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@@Z; std::make_unique<Pal::NetworkException,std::string,0>(std::string &&)
0x180032af4  mov     rdx, rax
0x180032af7  lea     rcx, [rsp+238h+var_1C8]
0x180032afc  call    ??$?4U?$default_delete@VNetworkException@Pal@@@std@@$0A@@?$unique_ptr@VNetworkException@Pal@@U?$default_delete@VNetworkException@Pal@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<Pal::NetworkException>::operator=<std::default_delete<Pal::NetworkException>,0>(std::unique_ptr<Pal::NetworkException> &&)
0x180032b01  lea     rcx, [rsp+238h+var_1E8]
0x180032b06  call    ??1?$unique_ptr@VNetworkRequestImpl@Pal@@U?$default_delete@VNetworkRequestImpl@Pal@@@std@@@std@@QEAA@XZ; std::unique_ptr<Pal::NetworkRequestImpl>::~unique_ptr<Pal::NetworkRequestImpl>(void)
0x180032b0b  nop
0x180032b0c  lea     rcx, [rsp+238h+var_160]
0x180032b14  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180032b19  nop
0x180032b1a  lea     rcx, [rsp+238h+var_138]
0x180032b22  call    ??_D?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXXZ; std::ostringstream::`vbase destructor'(void)
0x180032b27  mov     rsi, [rsp+238h+var_1C0]
0x180032b2c  lea     rcx, [rsp+238h+var_1E0]
0x180032b31  call    ??1?$unique_ptr@V?$vector@EV?$allocator@E@std@@@std@@U?$default_delete@V?$vector@EV?$allocator@E@std@@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::vector<uchar>>::~unique_ptr<std::vector<uchar>>(void)
0x180032b36  nop
0x180032b37  jmp     short loc_180032B4B
0x180032b39  mov     r15, [rsp+238h+var_1D8]
0x180032b3e  mov     r13, [rsp+238h+var_1B8]
0x180032b46  mov     rsi, [rsp+238h+var_1C0]
0x180032b4b  mov     rcx, r15; hObject
0x180032b4e  call    cs:__imp_CloseHandle
0x180032b54  lea     rdi, [r13+0A0h]
0x180032b5b  mov     [rsp+238h+var_1E8], rdi
0x180032b60  mov     rcx, rdi; lpCriticalSection
0x180032b63  call    cs:__imp_EnterCriticalSection
0x180032b69  nop
0x180032b6a  cmp     dword ptr [r13+0C8h], 2
0x180032b72  jz      loc_180032C1F
0x180032b78  mov     dword ptr [r13+0C8h], 3
0x180032b83  mov     rax, [rsp+238h+var_1D0]
0x180032b88  mov     [rsp+238h+var_1D0], 0
0x180032b91  mov     [rsp+238h+var_1D8], rax
0x180032b96  mov     [rsp+238h+var_210], 0
0x180032b9b  mov     rax, [rsp+238h+var_1C8]
0x180032ba0  mov     [rsp+238h+lpOverlapped], rax
0x180032ba5  lea     r9, [rsp+238h+var_1D8]
0x180032baa  lea     r8, [rsp+238h+var_1A8]
0x180032bb2  mov     rdx, rsi
0x180032bb5  lea     rcx, [rsp+238h+var_138]
0x180032bbd  call    ??0NetworkResponse@Pal@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$shared_ptr@$$CBV?$vector@EV?$allocator@E@std@@@std@@@3@V?$unique_ptr@VNetworkResponseHeaders@Pal@@U?$default_delete@VNetworkResponseHeaders@Pal@@@std@@@3@PEBVNetworkException@1@_N4@Z; Pal::NetworkResponse::NetworkResponse(std::wstring const &,std::shared_ptr<std::vector<uchar> const> const &,std::unique_ptr<Pal::NetworkResponseHeaders>,Pal::NetworkException const *,bool,bool)
0x180032bc2  nop
0x180032bc3  lea     rcx, [r13+0D0h]
0x180032bca  lea     rdx, [rsp+238h+var_138]
0x180032bd2  call    ??R?$_Func_class@X$$V@std@@QEBAXXZ; std::_Func_class<void,>::operator()(void)
0x180032bd7  mov     dword ptr [rsp+238h+var_1F0], 1
0x180032bdf  mov     rcx, rsi
0x180032be2  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180032be7  mov     [rsp+238h+var_1B8], rax
0x180032bef  call    ?getInstance@?$PerformanceTracerSingleton@VPalPerformanceTracer@Pal@@@Pal@@KAAEAVPalPerformanceTracer@2@XZ; Pal::PerformanceTracerSingleton<Pal::PalPerformanceTracer>::getInstance(void)
0x180032bf4  lea     r9, [rsp+238h+var_1F0]
0x180032bf9  lea     r8, [rsp+238h+var_1B8]
0x180032c01  lea     rdx, dword_18007B9F0; struct Pal::PerformanceEventId *
0x180032c08  mov     rcx, rax; SRWLock
0x180032c0b  call    ??$traceEvent@AEAPEBGAEAI@PerformanceTracer@Pal@@QEAAXAEBVPerformanceEventId@1@AEAPEBGAEAI@Z; Pal::PerformanceTracer::traceEvent<ushort const * &,uint &>(Pal::PerformanceEventId const &,ushort const * &,uint &)
0x180032c10  nop
0x180032c11  lea     rcx, [rsp+238h+var_138]; this
0x180032c19  call    ??1NetworkResponse@Pal@@QEAA@XZ; Pal::NetworkResponse::~NetworkResponse(void)
0x180032c1e  nop
0x180032c1f  mov     rcx, rdi; lpCriticalSection
0x180032c22  call    cs:__imp_LeaveCriticalSection
0x180032c28  xorps   xmm0, xmm0
0x180032c2b  movdqu  xmmword ptr [rsp+238h+var_1B8], xmm0
0x180032c34  lea     rcx, [r13+50h]
0x180032c38  lea     rdx, [rsp+238h+var_1B8]
0x180032c40  call    ??4?$shared_ptr@VNetworkRequestInternalWinHttp@Pal@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Pal::NetworkRequestInternalWinHttp>::operator=(std::shared_ptr<Pal::NetworkRequestInternalWinHttp> &&)
0x180032c45  mov     rcx, [rsp+238h+var_1B8+8]; this
0x180032c4d  test    rcx, rcx
0x180032c50  jz      short loc_180032C58
0x180032c52  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180032c57  nop
0x180032c58  lea     rcx, [rsp+238h+var_1D0]
0x180032c5d  call    ??1?$unique_ptr@VNetworkRequestImpl@Pal@@U?$default_delete@VNetworkRequestImpl@Pal@@@std@@@std@@QEAA@XZ; std::unique_ptr<Pal::NetworkRequestImpl>::~unique_ptr<Pal::NetworkRequestImpl>(void)
0x180032c62  nop
0x180032c63  lea     rcx, [rsp+238h+var_1C8]
0x180032c68  call    ??1?$unique_ptr@VNetworkRequestImpl@Pal@@U?$default_delete@VNetworkRequestImpl@Pal@@@std@@@std@@QEAA@XZ; std::unique_ptr<Pal::NetworkRequestImpl>::~unique_ptr<Pal::NetworkRequestImpl>(void)
0x180032c6d  nop
0x180032c6e  mov     rcx, [rsp+238h+var_1A8+8]; this
0x180032c76  test    rcx, rcx
0x180032c79  jz      short loc_180032C80
0x180032c7b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180032c80  mov     rcx, [rsp+238h+var_48]
0x180032c88  xor     rcx, rsp; StackCookie
0x180032c8b  call    __security_check_cookie
0x180032c90  add     rsp, 208h
0x180032c97  pop     r15
0x180032c99  pop     r14
0x180032c9b  pop     r13
0x180032c9d  pop     r12
0x180032c9f  pop     rdi
0x180032ca0  pop     rsi
0x180032ca1  retn
```
