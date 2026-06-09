# CWSStream::Initialize(void)

- ea: `0x18010cf60`
- end: `0x18010d6e6`
- name: `?Initialize@CWSStream@@UEAAJXZ`
- size: `1926`
- prototype: `__int64 __fastcall(CWSStream *__hidden this)`
- caller_count: `0`
- callee_count: `17`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001aa0`
- `0x1800025dc`
- `0x180004a94`
- `0x180005090`
- `0x180038984`
- `0x1800480a0`
- `0x18006ce24`
- `0x18007813c`
- `0x180078c20`
- `0x18007969c`
- `0x1800888d8`
- `0x1800dd6a0`
- `0x180108788`
- `0x1801088a0`
- `0x180108e04`
- `0x18010cf60`
- `0x18015e498`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18010d344`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18010d344`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18010d325`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18010d325`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18010d26f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18010d26f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010d0cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010d190`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010d27d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010d456`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010d5ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010d0cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010d190`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010d27d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010d456`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010d5ca`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18010d0b9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18010d17a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18010d0b9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18010d17a`
- `api-ms-win-core-synch-l1-2-0!InitializeConditionVariable` at `0x18010d236`
- `api-ms-win-core-synch-l1-2-0!InitializeConditionVariable` at `0x18010d236`

## string_xrefs

- `0x18010d0f3`: `Failed to create the read worker event`
- `0x18010d1b4`: `Failed to create the read worker termination event`
- `0x18010d37c`: `StringCchCat of file path failed`
- `0x18010d34a`: `rdpnanoTransport.dll`
- `0x18010d3eb`: `Loading dll`
- `0x18010d3b5`: `StringCchCopy of file path failed`
- `0x18010d514`: `LoadLibrary failed for RdpNano.dll used for websocket.`
- `0x18010d473`: `Failed to create RdpNanoTransport loader object.`
- `0x18010d580`: `Failed to create metrics bridge object.`

## pseudocode

```c
__int64 __fastcall CWSStream::Initialize(CWSStream *this)
{
  __int64 v2; // r8
  __int64 v3; // rdx
  __int64 v4; // rdx
  __int64 v5; // r8
  __int64 v6; // rdx
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // rdx
  __int64 v10; // rdx
  HANDLE EventW; // rax
  signed int LastError; // eax
  int v13; // ecx
  int v14; // r8d
  int v15; // r9d
  unsigned int v16; // ebx
  HANDLE v17; // rax
  signed int v18; // eax
  int v19; // ecx
  int v20; // r8d
  int v21; // r9d
  char *v22; // rdx
  const char **v23; // rax
  signed int v24; // eax
  DWORD ModuleFileNameW; // eax
  wchar_t *v26; // rax
  const char *v27; // rax
  Microsoft::RdpNano::Dll **v28; // r14
  __int64 v29; // rax
  unsigned int v30; // r8d
  signed int v31; // eax
  int v32; // ecx
  int v33; // r8d
  int v34; // r9d
  unsigned int TLSLoggerInstance; // eax
  int v36; // eax
  int v37; // r8d
  int v38; // r9d
  int v39; // eax
  int v40; // r8d
  int v41; // r9d
  signed int v42; // eax
  const char *v43; // rax
  unsigned int v44; // eax
  const char **v46; // [rsp+30h] [rbp-D0h]
  const char **v47; // [rsp+40h] [rbp-C0h]
  const char **v48; // [rsp+48h] [rbp-B8h]
  int v49; // [rsp+50h] [rbp-B0h] BYREF
  int v50; // [rsp+54h] [rbp-ACh] BYREF
  const char *v51; // [rsp+58h] [rbp-A8h] BYREF
  const char *v52; // [rsp+60h] [rbp-A0h] BYREF
  const char *v53; // [rsp+68h] [rbp-98h] BYREF
  const char *v54; // [rsp+70h] [rbp-90h] BYREF
  utl::_RefCountBase *v55; // [rsp+78h] [rbp-88h]
  HMODULE phModule[2]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR Filename[264]; // [rsp+90h] [rbp-70h] BYREF

  *((_DWORD *)this + 5) |= 2u;
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 71) = 0;
  *((_DWORD *)this + 42) = 10;
  v2 = 0;
  *((_QWORD *)this + 20) = (char *)this + 176;
  *((_QWORD *)this + 22) = 0;
  do
  {
    v3 = v2 + 2 * v2 + 1;
    ++v2;
    v4 = *((_QWORD *)this + 20) + 8 * v3;
    *(_QWORD *)(v4 + 8) = *((_QWORD *)this + 19);
    *((_QWORD *)this + 19) = v4;
  }
  while ( v2 != 16 );
  *((_QWORD *)this + 129) = 0;
  *((_QWORD *)this + 78) = (char *)this + 640;
  v5 = 0;
  *((_DWORD *)this + 158) = 10;
  *((_QWORD *)this + 80) = 0;
  do
  {
    v6 = v5 + 2 * v5 + 1;
    ++v5;
    v7 = *((_QWORD *)this + 78) + 8 * v6;
    *(_QWORD *)(v7 + 8) = *((_QWORD *)this + 77);
    *((_QWORD *)this + 77) = v7;
  }
  while ( v5 != 16 );
  *((_QWORD *)this + 212) = 0;
  *((_QWORD *)this + 161) = (char *)this + 1304;
  v8 = 0;
  *((_DWORD *)this + 324) = 10;
  *((_QWORD *)this + 163) = 0;
  do
  {
    v9 = v8 + 2 * v8 + 1;
    ++v8;
    v10 = *((_QWORD *)this + 161) + 8 * v9;
    *(_QWORD *)(v10 + 8) = *((_QWORD *)this + 160);
    *((_QWORD *)this + 160) = v10;
  }
  while ( v8 != 16 );
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 217) = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    v16 = LastError;
    if ( LastError > 0 )
      v16 = (unsigned __int16)LastError | 0x80070000;
    if ( (unsigned int)CallbackContext > 2 )
    {
      v50 = 112;
      phModule[0] = (HMODULE)"Failed to create the read worker event";
      v53 = "Initialize";
      v52 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\websocketstream\\websocketstream.cpp";
      v49 = v16;
      v51 = "Error condition failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v13,
        (unsigned int)&word_1801CAA8E,
        v14,
        v15,
        (__int64)&v51,
        (__int64)&v49,
        (__int64)&v52,
        (__int64)&v50,
        (__int64)&v53,
        (__int64)phModule);
    }
    return v16;
  }
  v17 = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 218) = v17;
  if ( !v17 )
  {
    v18 = GetLastError();
    v16 = v18;
    if ( v18 > 0 )
      v16 = (unsigned __int16)v18 | 0x80070000;
    if ( (unsigned int)CallbackContext > 2 )
    {
      v49 = 115;
      v51 = "Failed to create the read worker termination event";
      v52 = "Initialize";
      v53 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\websocketstream\\websocketstream.cpp";
      v22 = byte_1801CAA3D;
      phModule[0] = (HMODULE)"Error condition failed";
      v48 = &v51;
      v47 = &v52;
      v46 = &v53;
      v23 = (const char **)phModule;
LABEL_62:
      v50 = v16;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v19,
        (_DWORD)v22,
        v20,
        v21,
        (__int64)v23,
        (__int64)&v50,
        (__int64)v46,
        (__int64)&v49,
        (__int64)v47,
        (__int64)v48);
      return v16;
    }
    return v16;
  }
  v16 = 0;
  InitializeConditionVariable((PCONDITION_VARIABLE)this + 219);
  if ( *((_DWORD *)this + 30) )
    goto LABEL_41;
  phModule[0] = 0;
  memset_0(Filename, 0, 0x20Au);
  if ( GetModuleHandleExW(6u, (LPCWSTR)CWSStream::STATIC_ReadCompletionWorker, phModule) )
  {
    ModuleFileNameW = GetModuleFileNameW(phModule[0], Filename, 0x105u);
    if ( !ModuleFileNameW || ModuleFileNameW == 261 )
    {
      v42 = GetLastError();
      v16 = v42;
      if ( v42 > 0 )
        v16 = (unsigned __int16)v42 | 0x80070000;
      if ( (unsigned int)CallbackContext <= 2 )
        return v16;
      v49 = 137;
      v54 = "Failed to get the module file name";
      v22 = &byte_1801CA9EF;
      v52 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\websocketstream\\websocketstream.cpp";
      v43 = "Error condition failed";
LABEL_61:
      v53 = v43;
      v48 = &v54;
      v47 = &v51;
      v46 = &v52;
      v23 = &v53;
      v51 = "Initialize";
      goto LABEL_62;
    }
    v26 = wcsrchr(Filename, 0x5Cu);
    if ( v26 )
    {
      v26[1] = 0;
      v16 = StringCchCatW(Filename, 0x105u, L"rdpnanoTransport.dll");
      if ( (v16 & 0x80000000) != 0 )
      {
        v19 = (int)CallbackContext;
        if ( (unsigned int)CallbackContext <= 2 )
          return v16;
        v27 = "StringCchCat of file path failed";
        v49 = 145;
        v22 = byte_1801CA905;
        goto LABEL_60;
      }
    }
    else
    {
      v16 = StringCchCopyW(Filename, 0x105u, L"rdpnanoTransport.dll");
      if ( (v16 & 0x80000000) != 0 )
      {
        if ( (unsigned int)CallbackContext <= 2 )
          return v16;
        v27 = "StringCchCopy of file path failed";
        v49 = 150;
        v22 = byte_1801CA953;
LABEL_60:
        v54 = v27;
        v52 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\websocketstream\\websocketstream.cpp";
        v43 = "Error HResult failed";
        goto LABEL_61;
      }
    }
    if ( (unsigned int)CallbackContext > 4 )
    {
      v54 = (const char *)Filename;
      v51 = "Loading dll";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v19,
        (unsigned int)qword_1801CA8B0,
        v20,
        v21,
        (__int64)&v51,
        (__int64)&v54);
    }
    v28 = (Microsoft::RdpNano::Dll **)((char *)this + 1760);
    v29 = utl::make_shared<Microsoft::RdpNano::Dll,int &>(&v54, (char *)this + 120);
    utl::shared_ptr<Microsoft::RdpNano::Dll>::operator=((char *)this + 1760, v29);
    if ( v55 )
      utl::_RefCountBase::_DecStrong(v55);
    if ( *v28 )
    {
      v36 = Microsoft::RdpNano::Dll::Load(*v28, Filename, v30);
      if ( v36 < 0 && (unsigned int)CallbackContext > 3 )
      {
        v49 = v36;
        v54 = "Initialize";
        v51 = "LoadLibrary failed for RdpNano.dll used for websocket.";
        v52 = "HResult failed but continue";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          (_DWORD)CallbackContext,
          (unsigned int)qword_1801CA838,
          v37,
          v38,
          (__int64)&v52,
          (__int64)&v51,
          (__int64)&v49,
          (__int64)&v54);
      }
      v39 = Microsoft::RdpNano::Dll::CreateRdpNanoMetricsBridge<utl::shared_ptr>(*v28, (char *)this + 1776);
      if ( v39 < 0 && (unsigned int)CallbackContext > 3 )
      {
        v49 = v39;
        v54 = "Initialize";
        v51 = "Failed to create metrics bridge object.";
        v52 = "HResult failed but continue";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          (_DWORD)CallbackContext,
          (unsigned int)&dword_1801CA874,
          v40,
          v41,
          (__int64)&v52,
          (__int64)&v51,
          (__int64)&v49,
          (__int64)&v54);
      }
      v16 = 0;
    }
    else if ( (unsigned int)CallbackContext > 3 )
    {
      v31 = GetLastError();
      if ( v31 > 0 )
        v31 = (unsigned __int16)v31 | 0x80070000;
      v49 = v31;
      v54 = "Failed to create RdpNanoTransport loader object.";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v32,
        (unsigned int)byte_1801CA8DB,
        v33,
        v34,
        (__int64)&v54,
        (__int64)&v49);
    }
LABEL_41:
    if ( (unsigned int)IsTLSLoggerEnabled(0) != 1 )
      return v16;
    TLSLoggerInstance = CreateTLSLoggerInstance(0, (char *)this + 1800);
    v16 = MapXResultToHR(TLSLoggerInstance);
    if ( (v16 & 0x80000000) == 0 )
    {
      v44 = CreateTLSLoggerInstance(0, (char *)this + 1808);
      v16 = MapXResultToHR(v44);
      if ( (v16 & 0x80000000) == 0 || (unsigned int)CallbackContext <= 2 )
        return v16;
      v49 = 181;
      v22 = &byte_1801CA7E7;
    }
    else
    {
      if ( (unsigned int)CallbackContext <= 2 )
        return v16;
      v49 = 178;
      v22 = (char *)&word_1801CA796;
    }
    v27 = "Failed to initialize TLSLogger in CWSStream!";
    goto LABEL_60;
  }
  v24 = GetLastError();
  v16 = v24;
  if ( v24 > 0 )
    v16 = (unsigned __int16)v24 | 0x80070000;
  if ( (unsigned int)CallbackContext > 2 )
  {
    v52 = "Initialize";
    v51 = "Failed to get module handle to itself.";
    v22 = byte_1801CA9A1;
    v49 = 134;
    v53 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\websocketstream\\websocketstream.cpp";
    v54 = "Error condition failed";
    v48 = &v51;
    v47 = &v52;
    v46 = &v53;
    v23 = &v54;
    goto LABEL_62;
  }
  return v16;
}

```

## disassembly

```asm
0x18010cf60  push    rbp
0x18010cf62  push    rbx
0x18010cf63  push    rsi
0x18010cf64  push    rdi
0x18010cf65  push    r14
0x18010cf67  push    r15
0x18010cf69  lea     rbp, [rsp-1B8h]
0x18010cf71  sub     rsp, 2B8h
0x18010cf78  mov     rax, cs:__security_cookie
0x18010cf7f  xor     rax, rsp
0x18010cf82  mov     [rbp+1E0h+var_40], rax
0x18010cf89  or      dword ptr [rcx+14h], 2
0x18010cf8d  lea     rax, [rcx+0B0h]
0x18010cf94  mov     qword ptr [rcx+70h], 0
0x18010cf9c  mov     r9d, 0Ah
0x18010cfa2  mov     qword ptr [rcx+238h], 0
0x18010cfad  mov     rdi, rcx
0x18010cfb0  mov     [rcx+0A8h], r9d
0x18010cfb7  xor     r8d, r8d
0x18010cfba  mov     [rcx+0A0h], rax
0x18010cfc1  mov     qword ptr [rax], 0
0x18010cfc8  mov     rax, [rcx+0A0h]
0x18010cfcf  lea     rdx, ds:1[r8*2]
0x18010cfd7  add     rdx, r8
0x18010cfda  inc     r8
0x18010cfdd  lea     rdx, [rax+rdx*8]
0x18010cfe1  mov     rax, [rcx+98h]
0x18010cfe8  mov     [rdx+8], rax
0x18010cfec  mov     [rcx+98h], rdx
0x18010cff3  cmp     r8, 10h
0x18010cff7  jnz     short loc_18010CFC8
0x18010cff9  lea     rax, [rcx+280h]
0x18010d000  mov     qword ptr [rcx+408h], 0
0x18010d00b  mov     [rcx+270h], rax
0x18010d012  xor     r8d, r8d
0x18010d015  mov     [rcx+278h], r9d
0x18010d01c  mov     qword ptr [rax], 0
0x18010d023  mov     rax, [rcx+270h]
0x18010d02a  lea     rdx, ds:1[r8*2]
0x18010d032  add     rdx, r8
0x18010d035  inc     r8
0x18010d038  lea     rdx, [rax+rdx*8]
0x18010d03c  mov     rax, [rcx+268h]
0x18010d043  mov     [rdx+8], rax
0x18010d047  mov     [rcx+268h], rdx
0x18010d04e  cmp     r8, 10h
0x18010d052  jnz     short loc_18010D023
0x18010d054  lea     rax, [rcx+518h]
0x18010d05b  mov     qword ptr [rcx+6A0h], 0
0x18010d066  mov     [rcx+508h], rax
0x18010d06d  xor     r8d, r8d
0x18010d070  mov     [rcx+510h], r9d
0x18010d077  mov     qword ptr [rax], 0
0x18010d07e  mov     rax, [rcx+508h]
0x18010d085  lea     rdx, ds:1[r8*2]
0x18010d08d  add     rdx, r8
0x18010d090  inc     r8
0x18010d093  lea     rdx, [rax+rdx*8]
0x18010d097  mov     rax, [rcx+500h]
0x18010d09e  mov     [rdx+8], rax
0x18010d0a2  mov     [rcx+500h], rdx
0x18010d0a9  cmp     r8, 10h
0x18010d0ad  jnz     short loc_18010D07E
0x18010d0af  xor     r9d, r9d; lpName
0x18010d0b2  xor     r8d, r8d; bInitialState
0x18010d0b5  xor     edx, edx; bManualReset
0x18010d0b7  xor     ecx, ecx; lpEventAttributes
0x18010d0b9  call    cs:__imp_CreateEventW
0x18010d0bf  mov     [rdi+6C8h], rax
0x18010d0c6  test    rax, rax
0x18010d0c9  jnz     loc_18010D170
0x18010d0cf  call    cs:__imp_GetLastError
0x18010d0d5  mov     ebx, eax
0x18010d0d7  test    eax, eax
0x18010d0d9  jle     short loc_18010D0E4
0x18010d0db  movzx   ebx, ax
0x18010d0de  or      ebx, 80070000h
0x18010d0e4  mov     eax, cs:CallbackContext
0x18010d0ea  cmp     eax, 2
0x18010d0ed  jbe     loc_18010D6C5
0x18010d0f3  lea     rax, aFailedToCreate_77; "Failed to create the read worker event"
0x18010d0fa  mov     [rsp+2E0h+var_28C], 70h ; 'p'
0x18010d102  mov     [rbp+1E0h+phModule], rax
0x18010d106  lea     rsi, aInitialize; "Initialize"
0x18010d10d  lea     rax, aOnecoreTermsrv_54; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18010d114  mov     [rsp+2E0h+var_278], rsi
0x18010d119  mov     [rsp+2E0h+var_280], rax
0x18010d11e  lea     rdx, word_1801CAA8E
0x18010d125  lea     rax, aErrorCondition; "Error condition failed"
0x18010d12c  mov     [rsp+2E0h+var_290], ebx
0x18010d130  mov     [rsp+2E0h+var_288], rax
0x18010d135  lea     rax, [rbp+1E0h+phModule]
0x18010d139  mov     [rsp+2E0h+var_298], rax
0x18010d13e  lea     rax, [rsp+2E0h+var_278]
0x18010d143  mov     [rsp+2E0h+var_2A0], rax
0x18010d148  lea     rax, [rsp+2E0h+var_28C]
0x18010d14d  mov     [rsp+2E0h+var_2A8], rax
0x18010d152  lea     rax, [rsp+2E0h+var_280]
0x18010d157  mov     [rsp+2E0h+var_2B0], rax
0x18010d15c  lea     rax, [rsp+2E0h+var_290]
0x18010d161  mov     [rsp+2E0h+var_2B8], rax
0x18010d166  lea     rax, [rsp+2E0h+var_288]
0x18010d16b  jmp     loc_18010D6BB
0x18010d170  xor     r9d, r9d; lpName
0x18010d173  xor     r8d, r8d; bInitialState
0x18010d176  xor     edx, edx; bManualReset
0x18010d178  xor     ecx, ecx; lpEventAttributes
0x18010d17a  call    cs:__imp_CreateEventW
0x18010d180  mov     [rdi+6D0h], rax
0x18010d187  test    rax, rax
0x18010d18a  jnz     loc_18010D22D
0x18010d190  call    cs:__imp_GetLastError
0x18010d196  mov     ebx, eax
0x18010d198  test    eax, eax
0x18010d19a  jle     short loc_18010D1A5
0x18010d19c  movzx   ebx, ax
0x18010d19f  or      ebx, 80070000h
0x18010d1a5  mov     eax, cs:CallbackContext
0x18010d1ab  cmp     eax, 2
0x18010d1ae  jbe     loc_18010D6C5
0x18010d1b4  lea     rax, aFailedToCreate_74; "Failed to create the read worker termin"...
0x18010d1bb  mov     [rsp+2E0h+var_290], 73h ; 's'
0x18010d1c3  mov     [rsp+2E0h+var_288], rax
0x18010d1c8  lea     rsi, aInitialize; "Initialize"
0x18010d1cf  lea     rax, aOnecoreTermsrv_54; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18010d1d6  mov     [rsp+2E0h+var_280], rsi
0x18010d1db  mov     [rsp+2E0h+var_278], rax
0x18010d1e0  lea     rdx, byte_1801CAA3D
0x18010d1e7  lea     rax, aErrorCondition; "Error condition failed"
0x18010d1ee  mov     [rbp+1E0h+phModule], rax
0x18010d1f2  lea     rax, [rsp+2E0h+var_288]
0x18010d1f7  mov     [rsp+2E0h+var_298], rax
0x18010d1fc  lea     rax, [rsp+2E0h+var_280]
0x18010d201  mov     [rsp+2E0h+var_2A0], rax
0x18010d206  lea     rax, [rsp+2E0h+var_290]
0x18010d20b  mov     [rsp+2E0h+var_2A8], rax
0x18010d210  lea     rax, [rsp+2E0h+var_278]
0x18010d215  mov     [rsp+2E0h+var_2B0], rax
0x18010d21a  lea     rax, [rsp+2E0h+var_28C]
0x18010d21f  mov     [rsp+2E0h+var_2B8], rax
0x18010d224  lea     rax, [rbp+1E0h+phModule]
0x18010d228  jmp     loc_18010D6B7
0x18010d22d  lea     rcx, [rdi+6D8h]; ConditionVariable
0x18010d234  xor     ebx, ebx
0x18010d236  call    cs:__imp_InitializeConditionVariable
0x18010d23c  lea     rsi, aInitialize; "Initialize"
0x18010d243  cmp     [rdi+78h], ebx
0x18010d246  jnz     loc_18010D498
0x18010d24c  xor     edx, edx; Val
0x18010d24e  mov     [rbp+1E0h+phModule], rbx
0x18010d252  mov     r8d, 20Ah; Size
0x18010d258  lea     rcx, [rbp+1E0h+Filename]; void *
0x18010d25c  call    memset_0
0x18010d261  lea     r8, [rbp+1E0h+phModule]; phModule
0x18010d265  lea     rdx, ?STATIC_ReadCompletionWorker@CWSStream@@CAKPEAX@Z; lpModuleName
0x18010d26c  lea     ecx, [rbx+6]; dwFlags
0x18010d26f  call    cs:__imp_GetModuleHandleExW
0x18010d275  test    eax, eax
0x18010d277  jnz     loc_18010D315
0x18010d27d  call    cs:__imp_GetLastError
0x18010d283  mov     ebx, eax
0x18010d285  test    eax, eax
0x18010d287  jle     short loc_18010D292
0x18010d289  movzx   ebx, ax
0x18010d28c  or      ebx, 80070000h
0x18010d292  mov     eax, cs:CallbackContext
0x18010d298  cmp     eax, 2
0x18010d29b  jbe     loc_18010D6C5
0x18010d2a1  lea     rax, aFailedToGetMod_0; "Failed to get module handle to itself."
0x18010d2a8  mov     [rsp+2E0h+var_280], rsi
0x18010d2ad  mov     [rsp+2E0h+var_288], rax
0x18010d2b2  lea     rdx, byte_1801CA9A1
0x18010d2b9  lea     rax, aOnecoreTermsrv_54; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18010d2c0  mov     [rsp+2E0h+var_290], 86h
0x18010d2c8  mov     [rsp+2E0h+var_278], rax
0x18010d2cd  lea     rax, aErrorCondition; "Error condition failed"
0x18010d2d4  mov     [rsp+2E0h+var_270], rax
0x18010d2d9  lea     rax, [rsp+2E0h+var_288]
0x18010d2de  mov     [rsp+2E0h+var_298], rax
0x18010d2e3  lea     rax, [rsp+2E0h+var_280]
0x18010d2e8  mov     [rsp+2E0h+var_2A0], rax
0x18010d2ed  lea     rax, [rsp+2E0h+var_290]
0x18010d2f2  mov     [rsp+2E0h+var_2A8], rax
0x18010d2f7  lea     rax, [rsp+2E0h+var_278]
0x18010d2fc  mov     [rsp+2E0h+var_2B0], rax
0x18010d301  lea     rax, [rsp+2E0h+var_28C]
0x18010d306  mov     [rsp+2E0h+var_2B8], rax
0x18010d30b  lea     rax, [rsp+2E0h+var_270]
0x18010d310  jmp     loc_18010D6B7
0x18010d315  mov     rcx, [rbp+1E0h+phModule]; hModule
0x18010d319  lea     rdx, [rbp+1E0h+Filename]; lpFilename
0x18010d31d  mov     ebx, 105h
0x18010d322  mov     r8d, ebx; nSize
0x18010d325  call    cs:__imp_GetModuleFileNameW
0x18010d32b  test    eax, eax
0x18010d32d  jz      loc_18010D5CA
0x18010d333  cmp     eax, ebx
0x18010d335  jz      loc_18010D5CA
0x18010d33b  mov     edx, 5Ch ; '\'; Ch
0x18010d340  lea     rcx, [rbp+1E0h+Filename]; Str
0x18010d344  call    cs:__imp_wcsrchr
0x18010d34a  lea     r8, aRdpnanotranspo; "rdpnanoTransport.dll"
0x18010d351  mov     edx, ebx; unsigned __int64
0x18010d353  test    rax, rax
0x18010d356  jz      short loc_18010D397
0x18010d358  xor     ecx, ecx
0x18010d35a  mov     [rax+2], cx
0x18010d35e  lea     rcx, [rbp+1E0h+Filename]; unsigned __int16 *
0x18010d362  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18010d367  mov     ebx, eax
0x18010d369  test    eax, eax
0x18010d36b  jns     short loc_18010D3D0
0x18010d36d  mov     ecx, cs:CallbackContext
0x18010d373  cmp     ecx, 2
0x18010d376  jbe     loc_18010D6C5
0x18010d37c  lea     rax, aStringcchcatOf; "StringCchCat of file path failed"
0x18010d383  mov     [rsp+2E0h+var_290], 91h
0x18010d38b  lea     rdx, byte_1801CA905
0x18010d392  jmp     loc_18010D65E
0x18010d397  lea     rcx, [rbp+1E0h+Filename]; unsigned __int16 *
0x18010d39b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18010d3a0  mov     ebx, eax
0x18010d3a2  test    eax, eax
0x18010d3a4  jns     short loc_18010D3D0
0x18010d3a6  mov     eax, cs:CallbackContext
0x18010d3ac  cmp     eax, 2
0x18010d3af  jbe     loc_18010D6C5
0x18010d3b5  lea     rax, aStringcchcopyO_2; "StringCchCopy of file path failed"
0x18010d3bc  mov     [rsp+2E0h+var_290], 96h
0x18010d3c4  lea     rdx, byte_1801CA953
0x18010d3cb  jmp     loc_18010D65E
0x18010d3d0  mov     eax, cs:CallbackContext
0x18010d3d6  cmp     eax, 4
0x18010d3d9  jbe     short loc_18010D410
0x18010d3db  lea     rax, [rbp+1E0h+Filename]
0x18010d3df  mov     [rsp+2E0h+var_270], rax
0x18010d3e4  lea     rdx, qword_1801CA8B0
0x18010d3eb  lea     rax, aLoadingDll; "Loading dll"
0x18010d3f2  mov     [rsp+2E0h+var_288], rax
0x18010d3f7  lea     rax, [rsp+2E0h+var_270]
0x18010d3fc  mov     [rsp+2E0h+var_2B8], rax
0x18010d401  lea     rax, [rsp+2E0h+var_288]
0x18010d406  mov     [rsp+2E0h+var_2C0], rax
0x18010d40b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18010d410  lea     rdx, [rdi+78h]
0x18010d414  lea     rcx, [rsp+2E0h+var_270]
0x18010d419  lea     r14, [rdi+6E0h]
0x18010d420  call    ??$make_shared@VDll@RdpNano@Microsoft@@AEAH@utl@@YA?AV?$shared_ptr@VDll@RdpNano@Microsoft@@@0@AEAH@Z; utl::make_shared<Microsoft::RdpNano::Dll,int &>(int &)
0x18010d425  mov     rdx, rax
0x18010d428  mov     rcx, r14
0x18010d42b  call    ??4?$shared_ptr@VDll@RdpNano@Microsoft@@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::shared_ptr<Microsoft::RdpNano::Dll>::operator=(utl::shared_ptr<Microsoft::RdpNano::Dll> &&)
0x18010d430  mov     rcx, [rsp+2E0h+var_268]; this
0x18010d435  test    rcx, rcx
0x18010d438  jz      short loc_18010D43F
0x18010d43a  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x18010d43f  mov     rcx, [r14]; this
0x18010d442  test    rcx, rcx
0x18010d445  jnz     loc_18010D4EA
0x18010d44b  mov     eax, cs:CallbackContext
0x18010d451  cmp     eax, 3
0x18010d454  jbe     short loc_18010D498
0x18010d456  call    cs:__imp_GetLastError
0x18010d45c  test    eax, eax
0x18010d45e  jle     short loc_18010D468
0x18010d460  movzx   eax, ax
0x18010d463  or      eax, 80070000h
0x18010d468  mov     [rsp+2E0h+var_290], eax
0x18010d46c  lea     rdx, byte_1801CA8DB
0x18010d473  lea     rax, aFailedToCreate_80; "Failed to create RdpNanoTransport loade"...
0x18010d47a  mov     [rsp+2E0h+var_270], rax
0x18010d47f  lea     rax, [rsp+2E0h+var_290]
0x18010d484  mov     [rsp+2E0h+var_2B8], rax
0x18010d489  lea     rax, [rsp+2E0h+var_270]
0x18010d48e  mov     [rsp+2E0h+var_2C0], rax
0x18010d493  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18010d498  xor     ecx, ecx
0x18010d49a  call    ?IsTLSLoggerEnabled@@YA?AW4_XBool32@@W4RdpXPlatTLSLoggerType@@@Z; IsTLSLoggerEnabled(RdpXPlatTLSLoggerType)
0x18010d49f  cmp     eax, 1
0x18010d4a2  jnz     loc_18010D6C5
0x18010d4a8  lea     rdx, [rdi+708h]
0x18010d4af  xor     ecx, ecx
0x18010d4b1  call    ?CreateTLSLoggerInstance@@YA?AW4_XResult32@@W4RdpXPlatTLSLoggerType@@PEAPEAVRdpXPlatTLSLogger@@@Z; CreateTLSLoggerInstance(RdpXPlatTLSLoggerType,RdpXPlatTLSLogger * *)
0x18010d4b6  mov     ecx, eax
0x18010d4b8  call    ?MapXResultToHR@@YAJW4_XResult32@@@Z; MapXResultToHR(_XResult32)
0x18010d4bd  mov     ebx, eax
0x18010d4bf  test    eax, eax
0x18010d4c1  jns     loc_18010D61E
0x18010d4c7  mov     eax, cs:CallbackContext
0x18010d4cd  cmp     eax, 2
0x18010d4d0  jbe     loc_18010D6C5
0x18010d4d6  mov     [rsp+2E0h+var_290], 0B2h
0x18010d4de  lea     rdx, word_1801CA796
0x18010d4e5  jmp     loc_18010D657
0x18010d4ea  lea     rdx, [rbp+1E0h+Filename]; lpLibFileName
0x18010d4ee  call    ?Load@Dll@RdpNano@Microsoft@@QEAAJPEBGK@Z; Microsoft::RdpNano::Dll::Load(ushort const *,ulong)
0x18010d4f3  lea     rbx, aHresultFailedB; "HResult failed but continue"
0x18010d4fa  test    eax, eax
0x18010d4fc  jns     short loc_18010D557
0x18010d4fe  mov     ecx, cs:CallbackContext
0x18010d504  cmp     ecx, 3
  ... truncated ...
```
