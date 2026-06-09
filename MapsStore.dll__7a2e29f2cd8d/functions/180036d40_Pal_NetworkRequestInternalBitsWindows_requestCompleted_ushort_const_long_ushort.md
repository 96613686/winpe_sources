# Pal::NetworkRequestInternalBitsWindows::requestCompleted(ushort const *,long,ushort *)

- ea: `0x180036d40`
- end: `0x180037242`
- name: `?requestCompleted@NetworkRequestInternalBitsWindows@Pal@@AEAAXPEBGJPEAG@Z`
- size: `1282`
- prototype: `void(Pal::NetworkRequestInternalBitsWindows *__hidden this, const unsigned __int16 *, int, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `30`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180032af0`

## callees

- `0x18000d090`
- `0x18000dcb0`
- `0x18000dce0`
- `0x1800126c4`
- `0x1800141d8`
- `0x180017318`
- `0x180017aa8`
- `0x180017cf4`
- `0x18001b9e0`
- `0x18001cd64`
- `0x180021da8`
- `0x180025398`
- `0x180025bbc`
- `0x18002d9d8`
- `0x18002de70`
- `0x18002df50`
- `0x18002e024`
- `0x180031ffc`
- `0x18003221c`
- `0x180032b0c`
- `0x1800331b8`
- `0x18003399c`
- `0x180033a68`
- `0x180033ab0`
- `0x180033bd8`
- `0x180034724`
- `0x1800349c8`
- `0x180034e24`
- `0x1800367e4`
- `0x180036d40`

## import_xrefs

- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z` at `0x180037046`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z` at `0x180037046`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180037103`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180037103`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800371c2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800371c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036e2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036e72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036e2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036e72`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180036e26`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180036e26`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800370ee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800370ee`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180036f2d`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180036f2d`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x180036e5e`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x180036e5e`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180036e3a`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180036e3a`

## string_xrefs

- `0x180036f37`: `Failed to read the file`
- `0x180036e81`: `Failed to open file`

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
  char *v27; // rsi
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
  int v40; // [rsp+48h] [rbp-1F0h] BYREF
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
    (struct Pal::PerformanceEventId *)&dword_1800F1D50);
  try
  {
    std::make_unique<std::vector<unsigned char>,,0>(&v42);
    if ( a3 < 0 )
    {
      v29 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v9);
      Pal::PalPerformanceTracer::traceNetworkRequestError(v29, a3);
      std::ostringstream::ostringstream(v53);
      v30 = std::operator<<<std::char_traits<char>>(v53, "Network request failed with error code 0x");
      std::ostream::operator<<(v30, (unsigned int)a3);
      if ( NetworkRequestWindowsTelemetry::IsEnabled(v32, v31) )
      {
        wil::details::static_lazy<NetworkRequestWindowsTelemetry>::get(
          v33,
          _lambda_e3c00d5e223e442e613a1a5c804f6f5c_::_lambda_invoker_cdecl_);
        NetworkRequestWindowsTelemetry::TraceBingBitsHttpRequest_(v34, v9, (unsigned int)a3);
      }
      std::stringbuf::str(v54, v52);
      v35 = (__int64 *)std::make_unique<Pal::NetworkException,std::string,0>(&v41, v52);
      std::unique_ptr<Pal::NetworkException>::operator=<std::default_delete<Pal::NetworkException>,0>(&v45, v35);
      std::unique_ptr<Pal::NetworkRequestImpl>::~unique_ptr<Pal::NetworkRequestImpl>(&v41);
      std::string::_Tidy_deallocate(v52);
      std::ostringstream::`vbase destructor'(v53);
      v27 = v46;
      goto LABEL_34;
    }
    if ( a4 )
    {
      v11 = (__int64 *)std::make_unique<Pal::NetworkResponseHeadersBits,unsigned short * &,0>(&v40, &v41);
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
      File2 = CreateFile2(a2, 0x80000000LL, 1, 3, 0);
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
        v40 = v13;
        v27 = v46;
        v41 = (unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v46);
        v28 = (RTL_SRWLOCK *)Pal::PerformanceTracerSingleton<Pal::PalPerformanceTracer>::getInstance();
        Pal::PerformanceTracer::traceEvent<unsigned short const * &,unsigned int &>(
          v28,
          (struct Pal::PerformanceEventId *)&dword_1800F1CC0);
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
    v38 = (__int64 *)std::make_unique<Pal::NetworkException,char const *,0>(&v40, &v41);
    std::unique_ptr<Pal::NetworkException>::operator=<std::default_delete<Pal::NetworkException>,0>(&v45, v38);
    std::unique_ptr<Pal::NetworkRequestImpl>::~unique_ptr<Pal::NetworkRequestImpl>(&v40);
    File2 = v43;
    v7 = v47[0];
    v27 = v46;
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
    Pal::NetworkResponse::NetworkResponse((unsigned int)v53, (_DWORD)v27, (unsigned int)v48, (unsigned int)&v43, v45, 0);
    std::_Func_class<void,>::operator()((char *)v7 + 208, v53);
    v40 = 1;
    v47[0] = (std::_Ref_count_base *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v27);
    v37 = (RTL_SRWLOCK *)Pal::PerformanceTracerSingleton<Pal::PalPerformanceTracer>::getInstance();
    Pal::PerformanceTracer::traceEvent<unsigned short const * &,unsigned int &>(
      v37,
      (struct Pal::PerformanceEventId *)&dword_1800F1D80);
    Pal::NetworkResponse::~NetworkResponse((Pal::NetworkResponse *)v53);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)v7 + 4);
  *(_OWORD *)v47 = 0;
  std::shared_ptr<MapControl::LocalIndex>::operator=((char *)v7 + 80, v47);
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
0x180036d40  push    rsi
0x180036d42  push    rdi
0x180036d43  push    r12
0x180036d45  push    r13
0x180036d47  push    r14
0x180036d49  push    r15
0x180036d4b  sub     rsp, 208h
0x180036d52  mov     rax, cs:__security_cookie
0x180036d59  xor     rax, rsp
0x180036d5c  mov     [rsp+238h+var_48], rax
0x180036d64  mov     r14, r9
0x180036d67  mov     edi, r8d
0x180036d6a  mov     r12, rdx
0x180036d6d  mov     r13, rcx
0x180036d70  mov     [rsp+238h+var_1B8], rcx
0x180036d78  mov     [rsp+238h+var_1E8], r9
0x180036d7d  or      r15, 0FFFFFFFFFFFFFFFFh
0x180036d81  mov     [rsp+238h+var_1D8], r15
0x180036d86  xorps   xmm0, xmm0
0x180036d89  movdqu  xmmword ptr [rsp+238h+var_1A8], xmm0
0x180036d92  mov     [rsp+238h+var_1C8], 0
0x180036d9b  mov     [rsp+238h+var_1D0], 0
0x180036da4  mov     [rsp+238h+NumberOfBytesRead], 1
0x180036dac  lea     rsi, [rcx+60h]
0x180036db0  mov     [rsp+238h+var_1C0], rsi
0x180036db5  mov     rcx, rsi
0x180036db8  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180036dbd  mov     [rsp+238h+var_1E0], rax
0x180036dc2  call    ?getInstance@?$PerformanceTracerSingleton@VPalPerformanceTracer@Pal@@@Pal@@KAAEAVPalPerformanceTracer@2@XZ; Pal::PerformanceTracerSingleton<Pal::PalPerformanceTracer>::getInstance(void)
0x180036dc7  lea     r9, [rsp+238h+NumberOfBytesRead]
0x180036dcc  lea     r8, [rsp+238h+var_1E0]
0x180036dd1  lea     rdx, dword_1800F1D50; struct Pal::PerformanceEventId *
0x180036dd8  mov     rcx, rax; SRWLock
0x180036ddb  call    ??$traceEvent@AEAPEBGAEAI@PerformanceTracer@Pal@@QEAAXAEBVPerformanceEventId@1@AEAPEBGAEAI@Z; Pal::PerformanceTracer::traceEvent<ushort const * &,uint &>(Pal::PerformanceEventId const &,ushort const * &,uint &)
0x180036de0  nop
0x180036de1  lea     rcx, [rsp+238h+var_1E0]
0x180036de6  call    ??$make_unique@V?$vector@EV?$allocator@E@std@@@std@@$$V$0A@@std@@YA?AV?$unique_ptr@V?$vector@EV?$allocator@E@std@@@std@@U?$default_delete@V?$vector@EV?$allocator@E@std@@@std@@@2@@0@XZ; std::make_unique<std::vector<uchar>,,0>(void)
0x180036deb  nop
0x180036dec  test    edi, edi
0x180036dee  js      loc_18003700D
0x180036df4  test    r14, r14
0x180036df7  jz      short loc_180036E1F
0x180036df9  lea     rdx, [rsp+238h+var_1E8]
0x180036dfe  lea     rcx, [rsp+238h+var_1F0]
0x180036e03  call    ??$make_unique@VNetworkResponseHeadersBits@Pal@@AEAPEAG$0A@@std@@YA?AV?$unique_ptr@VNetworkResponseHeadersBits@Pal@@U?$default_delete@VNetworkResponseHeadersBits@Pal@@@std@@@0@AEAPEAG@Z; std::make_unique<Pal::NetworkResponseHeadersBits,ushort * &,0>(ushort * &)
0x180036e08  mov     rdx, rax
0x180036e0b  lea     rcx, [rsp+238h+var_1D0]
0x180036e10  call    ??$?4U?$default_delete@VNetworkException@Pal@@@std@@$0A@@?$unique_ptr@VNetworkException@Pal@@U?$default_delete@VNetworkException@Pal@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<Pal::NetworkException>::operator=<std::default_delete<Pal::NetworkException>,0>(std::unique_ptr<Pal::NetworkException> &&)
0x180036e15  lea     rcx, [rsp+238h+var_1F0]
0x180036e1a  call    ??1?$unique_ptr@VNetworkRequestImpl@Pal@@U?$default_delete@VNetworkRequestImpl@Pal@@@std@@@std@@QEAA@XZ; std::unique_ptr<Pal::NetworkRequestImpl>::~unique_ptr<Pal::NetworkRequestImpl>(void)
0x180036e1f  mov     edi, 3E8h
0x180036e24  xor     ecx, ecx; dwErrCode
0x180036e26  call    cs:__imp_SetLastError
0x180036e2c  call    cs:__imp_GetLastError
0x180036e32  cmp     eax, 20h ; ' '
0x180036e35  jnz     short loc_180036E43
0x180036e37  lea     ecx, [rax+44h]; dwMilliseconds
0x180036e3a  call    cs:__imp_Sleep
0x180036e40  sub     edi, 64h ; 'd'
0x180036e43  mov     [rsp+238h+lpOverlapped], 0
0x180036e4c  mov     edx, 80000000h
0x180036e51  mov     r9d, 3
0x180036e57  lea     r8d, [r9-2]
0x180036e5b  mov     rcx, r12
0x180036e5e  call    cs:__imp_CreateFile2
0x180036e64  mov     r15, rax
0x180036e67  mov     [rsp+238h+var_1D8], rax
0x180036e6c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180036e70  jnz     short loc_180036EA9
0x180036e72  call    cs:__imp_GetLastError
0x180036e78  cmp     eax, 20h ; ' '
0x180036e7b  jnz     short loc_180036E81
0x180036e7d  test    edi, edi
0x180036e7f  jg      short loc_180036E2C
0x180036e81  lea     rdx, aFailedToOpenFi; "Failed to open file"
0x180036e88  lea     rcx, [rsp+238h+pExceptionObject]; this
0x180036e90  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x180036e95  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x180036e9c  lea     rcx, [rsp+238h+pExceptionObject]; pExceptionObject
0x180036ea4  call    _CxxThrowException_0
0x180036ea9  xor     r14d, r14d
0x180036eac  mov     [rsp+238h+NumberOfBytesRead], r14d
0x180036eb1  mov     rsi, [rsp+238h+var_1E0]
0x180036eb6  lea     eax, [r14+2000h]
0x180036ebd  mov     edi, eax
0x180036ebf  mov     rdx, [rsi]
0x180036ec2  mov     r12, [rsi+8]
0x180036ec6  mov     rcx, r12
0x180036ec9  sub     rcx, rdx
0x180036ecc  cmp     rdi, rcx
0x180036ecf  jnb     short loc_180036ED6
0x180036ed1  add     rax, rdx
0x180036ed4  jmp     short loc_180036F05
0x180036ed6  jbe     short loc_180036F09
0x180036ed8  mov     rax, [rsi+10h]
0x180036edc  sub     rax, rdx
0x180036edf  cmp     rdi, rax
0x180036ee2  jbe     short loc_180036EF1
0x180036ee4  mov     rdx, rdi
0x180036ee7  mov     rcx, rsi
0x180036eea  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180036eef  jmp     short loc_180036F09
0x180036ef1  sub     rdi, rcx
0x180036ef4  mov     r8, rdi; Size
0x180036ef7  xor     edx, edx; Val
0x180036ef9  mov     rcx, r12; void *
0x180036efc  call    memset_0
0x180036f01  lea     rax, [rdi+r12]
0x180036f05  mov     [rsi+8], rax
0x180036f09  mov     edx, r14d
0x180036f0c  mov     rax, [rsp+238h+var_1E0]
0x180036f11  add     rdx, [rax]; lpBuffer
0x180036f14  mov     [rsp+238h+lpOverlapped], 0; lpOverlapped
0x180036f1d  lea     r9, [rsp+238h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180036f22  mov     edi, 2000h
0x180036f27  mov     r8d, edi; nNumberOfBytesToRead
0x180036f2a  mov     rcx, r15; hFile
0x180036f2d  call    cs:__imp_ReadFile
0x180036f33  test    eax, eax
0x180036f35  jnz     short loc_180036F5F
0x180036f37  lea     rdx, aFailedToReadTh; "Failed to read the file"
0x180036f3e  lea     rcx, [rsp+238h+var_178]; this
0x180036f46  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x180036f4b  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x180036f52  lea     rcx, [rsp+238h+var_178]; pExceptionObject
0x180036f5a  call    _CxxThrowException_0
0x180036f5f  add     r14d, [rsp+238h+NumberOfBytesRead]
0x180036f64  cmp     [rsp+238h+NumberOfBytesRead], edi
0x180036f68  jz      loc_180036EB1
0x180036f6e  mov     rsi, [rsp+238h+var_1E0]
0x180036f73  mov     rdx, [rsi]
0x180036f76  mov     r12, [rsi+8]
0x180036f7a  mov     rcx, r12
0x180036f7d  sub     rcx, rdx
0x180036f80  mov     edi, r14d
0x180036f83  cmp     rdi, rcx
0x180036f86  jnb     short loc_180036F8E
0x180036f88  lea     rax, [rdx+r14]
0x180036f8c  jmp     short loc_180036FBD
0x180036f8e  jbe     short loc_180036FC1
0x180036f90  mov     rax, [rsi+10h]
0x180036f94  sub     rax, rdx
0x180036f97  cmp     rdi, rax
0x180036f9a  jbe     short loc_180036FA9
0x180036f9c  mov     rdx, rdi
0x180036f9f  mov     rcx, rsi
0x180036fa2  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180036fa7  jmp     short loc_180036FC1
0x180036fa9  sub     rdi, rcx
0x180036fac  mov     r8, rdi; Size
0x180036faf  xor     edx, edx; Val
0x180036fb1  mov     rcx, r12; void *
0x180036fb4  call    memset_0
0x180036fb9  lea     rax, [rdi+r12]
0x180036fbd  mov     [rsi+8], rax
0x180036fc1  lea     rdx, [rsp+238h+var_1E0]
0x180036fc6  lea     rcx, [rsp+238h+var_1A8]
0x180036fce  call    ??$?4V?$vector@EV?$allocator@E@std@@@std@@U?$default_delete@V?$vector@EV?$allocator@E@std@@@std@@@1@$0A@@?$shared_ptr@$$CBV?$vector@EV?$allocator@E@std@@@std@@@std@@QEAAAEAV01@$$QEAV?$unique_ptr@V?$vector@EV?$allocator@E@std@@@std@@U?$default_delete@V?$vector@EV?$allocator@E@std@@@std@@@2@@1@@Z; std::shared_ptr<std::vector<uchar> const>::operator=<std::vector<uchar>,std::default_delete<std::vector<uchar>>,0>(std::unique_ptr<std::vector<uchar>> &&)
0x180036fd3  mov     [rsp+238h+var_1F0], r14d
0x180036fd8  mov     rsi, [rsp+238h+var_1C0]
0x180036fdd  mov     rcx, rsi
0x180036fe0  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180036fe5  mov     [rsp+238h+var_1E8], rax
0x180036fea  call    ?getInstance@?$PerformanceTracerSingleton@VPalPerformanceTracer@Pal@@@Pal@@KAAEAVPalPerformanceTracer@2@XZ; Pal::PerformanceTracerSingleton<Pal::PalPerformanceTracer>::getInstance(void)
0x180036fef  lea     r9, [rsp+238h+var_1F0]
0x180036ff4  lea     r8, [rsp+238h+var_1E8]
0x180036ff9  lea     rdx, dword_1800F1CC0; struct Pal::PerformanceEventId *
0x180037000  mov     rcx, rax; SRWLock
0x180037003  call    ??$traceEvent@AEAPEBGAEAI@PerformanceTracer@Pal@@QEAAXAEBVPerformanceEventId@1@AEAPEBGAEAI@Z; Pal::PerformanceTracer::traceEvent<ushort const * &,uint &>(Pal::PerformanceEventId const &,ushort const * &,uint &)
0x180037008  jmp     loc_1800370CC
0x18003700d  mov     rcx, rsi
0x180037010  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180037015  mov     edx, edi; int
0x180037017  mov     rcx, rax; unsigned __int16 *
0x18003701a  call    ?traceNetworkRequestError@PalPerformanceTracer@Pal@@SAXPEBGH@Z; Pal::PalPerformanceTracer::traceNetworkRequestError(ushort const *,int)
0x18003701f  lea     rcx, [rsp+238h+var_138]
0x180037027  call    ??0?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::ostringstream::ostringstream(void)
0x18003702c  nop
0x18003702d  lea     rdx, aNetworkRequest; "Network request failed with error code "...
0x180037034  lea     rcx, [rsp+238h+var_138]
0x18003703c  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180037041  mov     edx, edi
0x180037043  mov     rcx, rax
0x180037046  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z; std::ostream::operator<<(long)
0x18003704c  call    ?IsEnabled@NetworkRequestWindowsTelemetry@@SA_NE_K@Z; NetworkRequestWindowsTelemetry::IsEnabled(uchar,unsigned __int64)
0x180037051  test    al, al
0x180037053  jz      short loc_18003706C
0x180037055  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_e3c00d5e223e442e613a1a5c804f6f5c_@@CA@XZ; _lambda_e3c00d5e223e442e613a1a5c804f6f5c_::_lambda_invoker_cdecl_(void)
0x18003705c  call    ?get@?$static_lazy@VNetworkRequestWindowsTelemetry@@@details@wil@@QEAAPEAVNetworkRequestWindowsTelemetry@@P6AXXZ@Z; wil::details::static_lazy<NetworkRequestWindowsTelemetry>::get(void (*)(void))
0x180037061  mov     r8d, edi
0x180037064  mov     rdx, rsi
0x180037067  call    ?TraceBingBitsHttpRequest_@NetworkRequestWindowsTelemetry@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@J@Z; NetworkRequestWindowsTelemetry::TraceBingBitsHttpRequest_(std::wstring const &,long)
0x18003706c  lea     rdx, [rsp+238h+var_160]
0x180037074  lea     rcx, [rsp+238h+var_130]
0x18003707c  call    ?str@?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::stringbuf::str(void)
0x180037081  nop
0x180037082  lea     rdx, [rsp+238h+var_160]
0x18003708a  lea     rcx, [rsp+238h+var_1E8]
0x18003708f  call    ??$make_unique@VNetworkException@Pal@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@$0A@@std@@YA?AV?$unique_ptr@VNetworkException@Pal@@U?$default_delete@VNetworkException@Pal@@@std@@@0@$$QEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@@Z; std::make_unique<Pal::NetworkException,std::string,0>(std::string &&)
0x180037094  mov     rdx, rax
0x180037097  lea     rcx, [rsp+238h+var_1C8]
0x18003709c  call    ??$?4U?$default_delete@VNetworkException@Pal@@@std@@$0A@@?$unique_ptr@VNetworkException@Pal@@U?$default_delete@VNetworkException@Pal@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<Pal::NetworkException>::operator=<std::default_delete<Pal::NetworkException>,0>(std::unique_ptr<Pal::NetworkException> &&)
0x1800370a1  lea     rcx, [rsp+238h+var_1E8]
0x1800370a6  call    ??1?$unique_ptr@VNetworkRequestImpl@Pal@@U?$default_delete@VNetworkRequestImpl@Pal@@@std@@@std@@QEAA@XZ; std::unique_ptr<Pal::NetworkRequestImpl>::~unique_ptr<Pal::NetworkRequestImpl>(void)
0x1800370ab  nop
0x1800370ac  lea     rcx, [rsp+238h+var_160]
0x1800370b4  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800370b9  nop
0x1800370ba  lea     rcx, [rsp+238h+var_138]
0x1800370c2  call    ??_D?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXXZ; std::ostringstream::`vbase destructor'(void)
0x1800370c7  mov     rsi, [rsp+238h+var_1C0]
0x1800370cc  lea     rcx, [rsp+238h+var_1E0]
0x1800370d1  call    ??1?$unique_ptr@V?$vector@EV?$allocator@E@std@@@std@@U?$default_delete@V?$vector@EV?$allocator@E@std@@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::vector<uchar>>::~unique_ptr<std::vector<uchar>>(void)
0x1800370d6  nop
0x1800370d7  jmp     short loc_1800370EB
0x1800370d9  mov     r15, [rsp+238h+var_1D8]
0x1800370de  mov     r13, [rsp+238h+var_1B8]
0x1800370e6  mov     rsi, [rsp+238h+var_1C0]
0x1800370eb  mov     rcx, r15; hObject
0x1800370ee  call    cs:__imp_CloseHandle
0x1800370f4  lea     rdi, [r13+0A0h]
0x1800370fb  mov     [rsp+238h+var_1E8], rdi
0x180037100  mov     rcx, rdi; lpCriticalSection
0x180037103  call    cs:__imp_EnterCriticalSection
0x180037109  nop
0x18003710a  cmp     dword ptr [r13+0C8h], 2
0x180037112  jz      loc_1800371BF
0x180037118  mov     dword ptr [r13+0C8h], 3
0x180037123  mov     rax, [rsp+238h+var_1D0]
0x180037128  mov     [rsp+238h+var_1D0], 0
0x180037131  mov     [rsp+238h+var_1D8], rax
0x180037136  mov     [rsp+238h+var_210], 0
0x18003713b  mov     rax, [rsp+238h+var_1C8]
0x180037140  mov     [rsp+238h+lpOverlapped], rax
0x180037145  lea     r9, [rsp+238h+var_1D8]
0x18003714a  lea     r8, [rsp+238h+var_1A8]
0x180037152  mov     rdx, rsi
0x180037155  lea     rcx, [rsp+238h+var_138]
0x18003715d  call    ??0NetworkResponse@Pal@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$shared_ptr@$$CBV?$vector@EV?$allocator@E@std@@@std@@@3@V?$unique_ptr@VNetworkResponseHeaders@Pal@@U?$default_delete@VNetworkResponseHeaders@Pal@@@std@@@3@PEBVNetworkException@1@_N4@Z; Pal::NetworkResponse::NetworkResponse(std::wstring const &,std::shared_ptr<std::vector<uchar> const> const &,std::unique_ptr<Pal::NetworkResponseHeaders>,Pal::NetworkException const *,bool,bool)
0x180037162  nop
0x180037163  lea     rcx, [r13+0D0h]
0x18003716a  lea     rdx, [rsp+238h+var_138]
0x180037172  call    ??R?$_Func_class@X$$V@std@@QEBAXXZ; std::_Func_class<void,>::operator()(void)
0x180037177  mov     [rsp+238h+var_1F0], 1
0x18003717f  mov     rcx, rsi
0x180037182  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180037187  mov     [rsp+238h+var_1B8], rax
0x18003718f  call    ?getInstance@?$PerformanceTracerSingleton@VPalPerformanceTracer@Pal@@@Pal@@KAAEAVPalPerformanceTracer@2@XZ; Pal::PerformanceTracerSingleton<Pal::PalPerformanceTracer>::getInstance(void)
0x180037194  lea     r9, [rsp+238h+var_1F0]
0x180037199  lea     r8, [rsp+238h+var_1B8]
0x1800371a1  lea     rdx, dword_1800F1D80; struct Pal::PerformanceEventId *
0x1800371a8  mov     rcx, rax; SRWLock
0x1800371ab  call    ??$traceEvent@AEAPEBGAEAI@PerformanceTracer@Pal@@QEAAXAEBVPerformanceEventId@1@AEAPEBGAEAI@Z; Pal::PerformanceTracer::traceEvent<ushort const * &,uint &>(Pal::PerformanceEventId const &,ushort const * &,uint &)
0x1800371b0  nop
0x1800371b1  lea     rcx, [rsp+238h+var_138]; this
0x1800371b9  call    ??1NetworkResponse@Pal@@QEAA@XZ; Pal::NetworkResponse::~NetworkResponse(void)
0x1800371be  nop
0x1800371bf  mov     rcx, rdi; lpCriticalSection
0x1800371c2  call    cs:__imp_LeaveCriticalSection
0x1800371c8  xorps   xmm0, xmm0
0x1800371cb  movdqu  xmmword ptr [rsp+238h+var_1B8], xmm0
0x1800371d4  lea     rcx, [r13+50h]
0x1800371d8  lea     rdx, [rsp+238h+var_1B8]
0x1800371e0  call    ??4?$shared_ptr@VLocalIndex@MapControl@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<MapControl::LocalIndex>::operator=(std::shared_ptr<MapControl::LocalIndex> &&)
0x1800371e5  mov     rcx, [rsp+238h+var_1B8+8]; this
0x1800371ed  test    rcx, rcx
0x1800371f0  jz      short loc_1800371F8
0x1800371f2  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800371f7  nop
0x1800371f8  lea     rcx, [rsp+238h+var_1D0]
0x1800371fd  call    ??1?$unique_ptr@VNetworkRequestImpl@Pal@@U?$default_delete@VNetworkRequestImpl@Pal@@@std@@@std@@QEAA@XZ; std::unique_ptr<Pal::NetworkRequestImpl>::~unique_ptr<Pal::NetworkRequestImpl>(void)
0x180037202  nop
0x180037203  lea     rcx, [rsp+238h+var_1C8]
0x180037208  call    ??1?$unique_ptr@VNetworkRequestImpl@Pal@@U?$default_delete@VNetworkRequestImpl@Pal@@@std@@@std@@QEAA@XZ; std::unique_ptr<Pal::NetworkRequestImpl>::~unique_ptr<Pal::NetworkRequestImpl>(void)
0x18003720d  nop
0x18003720e  mov     rcx, [rsp+238h+var_1A8+8]; this
0x180037216  test    rcx, rcx
0x180037219  jz      short loc_180037220
0x18003721b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180037220  mov     rcx, [rsp+238h+var_48]
0x180037228  xor     rcx, rsp; StackCookie
0x18003722b  call    __security_check_cookie
0x180037230  add     rsp, 208h
0x180037237  pop     r15
0x180037239  pop     r14
0x18003723b  pop     r13
0x18003723d  pop     r12
0x18003723f  pop     rdi
0x180037240  pop     rsi
0x180037241  retn
```
