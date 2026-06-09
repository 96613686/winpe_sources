# CLogFileMgr::Initialize(LogFileType,ushort const *)

- ea: `0x180010a7c`
- end: `0x180010cc7`
- name: `?Initialize@CLogFileMgr@@QEAAJW4LogFileType@@PEBG@Z`
- size: `587`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18000936c`
- `0x1800094c8`
- `0x18000ef14`
- `0x18000f228`
- `0x18000f648`
- `0x180010118`
- `0x180012840`

## callees

- `0x180001258`
- `0x180001b90`
- `0x18000265c`
- `0x180006498`
- `0x180010a7c`
- `0x180010cd0`
- `0x180010ed4`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180010baa`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180010baa`

## string_xrefs

- `0x180010b12`: `%s\%s_%s.xml`

## pseudocode

```c
__int64 __fastcall CLogFileMgr::Initialize(unsigned __int16 *a1, int a2, const unsigned __int16 *a3)
{
  int v6; // ecx
  int v7; // r8d
  int v8; // r9d
  int v9; // ebx
  int v10; // eax
  int i; // edx
  int v13; // [rsp+50h] [rbp-B0h] BYREF
  int v14; // [rsp+54h] [rbp-ACh] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 v16[32]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v17[264]; // [rsp+B0h] [rbp-50h] BYREF

  memset_0(v17, 0, 0x20Au);
  if ( !a3 )
  {
    v9 = -2147024809;
    goto LABEL_19;
  }
  v9 = CLogFileMgr::InitializeLogFolder();
  if ( v9 >= 0 )
  {
    if ( a2 )
    {
      v6 = a2 - 1;
      if ( a2 != 1 )
      {
        if ( a2 != 2 )
        {
          v9 = -2147467259;
          goto LABEL_19;
        }
        v10 = StringCchPrintfW(
                a1,
                0x401u,
                L"%s\\%s_%s.xml",
                &CLogFileMgr::s_szDeviceStateDataLogFolder,
                L"DiagnosticLogCSP_DeviceStateData",
                a3);
        goto LABEL_9;
      }
      v9 = StringCchPrintfW(v17, 0x105u, a3);
      if ( v9 >= 0 )
      {
        for ( i = 0; v17[i]; ++i )
        {
          if ( v17[i] == 47 )
            v17[i] = 95;
        }
        v10 = StringCchPrintfW(
                a1,
                0x401u,
                L"%s\\%s_%s.evtx",
                &CLogFileMgr::s_szChannelsLogFolder,
                L"DiagnosticLogCSP_Channel",
                v17);
LABEL_9:
        v9 = v10;
      }
    }
    else
    {
      SystemTime = 0;
      GetLocalTime(&SystemTime);
      v9 = StringCchPrintfW(
             v16,
             0x20u,
             L"%d_%d_%d_%d_%d_%d",
             SystemTime.wYear,
             SystemTime.wMonth,
             SystemTime.wDay,
             SystemTime.wHour,
             SystemTime.wMinute,
             SystemTime.wSecond);
      if ( v9 >= 0 )
      {
        v9 = StringCchPrintfW(
               a1,
               0x401u,
               L"%s\\%s_%s_%s.etl",
               &CLogFileMgr::s_szCollectorsLogFolder,
               L"DiagnosticLogCSP_Collector",
               a3,
               v16);
        if ( v9 >= 0 )
          CLogFileMgr::RemoveOlderFiles(a3);
      }
    }
  }
LABEL_19:
  if ( (unsigned int)dword_18004AE90 > 5 )
  {
    v13 = v9;
    v14 = a2;
    if ( !a3 )
      a3 = &String2;
    *(_QWORD *)&SystemTime.wYear = a3;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v6,
      (unsigned int)byte_180041A01,
      v7,
      v8,
      (__int64)&SystemTime,
      (__int64)&v14,
      (__int64)&v13);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180010a7c  mov     [rsp-8+arg_8], rbx
0x180010a81  mov     [rsp-8+arg_18], rsi
0x180010a86  push    rbp
0x180010a87  push    rdi
0x180010a88  push    r14
0x180010a8a  lea     rbp, [rsp-1D0h]
0x180010a92  sub     rsp, 2D0h
0x180010a99  mov     rax, cs:__security_cookie
0x180010aa0  xor     rax, rsp
0x180010aa3  mov     [rbp+1E0h+var_20], rax
0x180010aaa  mov     rdi, r8
0x180010aad  mov     esi, edx
0x180010aaf  mov     r14, rcx
0x180010ab2  xor     edx, edx; Val
0x180010ab4  mov     r8d, 20Ah; Size
0x180010aba  lea     rcx, [rbp+1E0h+var_230]; void *
0x180010abe  call    memset_0
0x180010ac3  test    rdi, rdi
0x180010ac6  jnz     short loc_180010AD2
0x180010ac8  mov     ebx, 80070057h
0x180010acd  jmp     loc_180010C4D
0x180010ad2  call    ?InitializeLogFolder@CLogFileMgr@@CAJXZ; CLogFileMgr::InitializeLogFolder(void)
0x180010ad7  mov     ebx, eax
0x180010ad9  test    eax, eax
0x180010adb  js      loc_180010C4D
0x180010ae1  mov     ecx, esi
0x180010ae3  test    esi, esi
0x180010ae5  jz      loc_180010B9D
0x180010aeb  sub     ecx, 1
0x180010aee  jz      short loc_180010B32
0x180010af0  cmp     ecx, 1
0x180010af3  jz      short loc_180010AFF
0x180010af5  mov     ebx, 80004005h
0x180010afa  jmp     loc_180010C4D
0x180010aff  mov     [rsp+2E0h+var_2B8], rdi
0x180010b04  lea     rax, aDiagnosticlogc_2; "DiagnosticLogCSP_DeviceStateData"
0x180010b0b  lea     r9, ?s_szDeviceStateDataLogFolder@CLogFileMgr@@0PAGA; ushort near * CLogFileMgr::s_szDeviceStateDataLogFolder
0x180010b12  lea     r8, aSSSXml; "%s\\%s_%s.xml"
0x180010b19  mov     edx, 401h; unsigned __int64
0x180010b1e  mov     [rsp+2E0h+var_2C0], rax
0x180010b23  mov     rcx, r14; unsigned __int16 *
0x180010b26  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180010b2b  mov     ebx, eax
0x180010b2d  jmp     loc_180010C4D
0x180010b32  mov     r8, rdi; unsigned __int16 *
0x180010b35  lea     rcx, [rbp+1E0h+var_230]; unsigned __int16 *
0x180010b39  mov     edx, 105h; unsigned __int64
0x180010b3e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180010b43  mov     ebx, eax
0x180010b45  test    eax, eax
0x180010b47  js      loc_180010C4D
0x180010b4d  xor     edx, edx
0x180010b4f  xor     eax, eax
0x180010b51  cmp     ax, [rbp+1E0h+var_230]
0x180010b55  jz      short loc_180010B7A
0x180010b57  movsxd  rax, edx
0x180010b5a  cmp     [rbp+rax*2+1E0h+var_230], 2Fh ; '/'
0x180010b60  jnz     short loc_180010B6C
0x180010b62  mov     ecx, 5Fh ; '_'
0x180010b67  mov     [rbp+rax*2+1E0h+var_230], cx
0x180010b6c  inc     edx
0x180010b6e  xor     eax, eax
0x180010b70  movsxd  rcx, edx
0x180010b73  cmp     ax, [rbp+rcx*2+1E0h+var_230]
0x180010b78  jnz     short loc_180010B57
0x180010b7a  lea     rax, [rbp+1E0h+var_230]
0x180010b7e  mov     [rsp+2E0h+var_2B8], rax
0x180010b83  lea     r9, ?s_szChannelsLogFolder@CLogFileMgr@@0PAGA; ushort near * CLogFileMgr::s_szChannelsLogFolder
0x180010b8a  lea     rax, aDiagnosticlogc_0; "DiagnosticLogCSP_Channel"
0x180010b91  lea     r8, aSSSEvtx; "%s\\%s_%s.evtx"
0x180010b98  jmp     loc_180010B19
0x180010b9d  xorps   xmm0, xmm0
0x180010ba0  lea     rcx, [rsp+2E0h+SystemTime]; lpSystemTime
0x180010ba5  movups  xmmword ptr [rsp+2E0h+SystemTime.wYear], xmm0
0x180010baa  call    cs:__imp_GetLocalTime
0x180010bb1  nop     dword ptr [rax+rax+00h]
0x180010bb6  movzx   ecx, [rsp+2E0h+SystemTime.wMinute]
0x180010bbb  movzx   edx, [rsp+2E0h+SystemTime.wHour]
0x180010bc0  movzx   r8d, [rsp+2E0h+SystemTime.wDay]
0x180010bc6  movzx   eax, [rsp+2E0h+SystemTime.wSecond]
0x180010bcb  movzx   r10d, [rsp+2E0h+SystemTime.wMonth]
0x180010bd1  movzx   r9d, [rsp+2E0h+SystemTime.wYear]
0x180010bd7  mov     [rsp+2E0h+var_2A0], eax
0x180010bdb  mov     [rsp+2E0h+var_2A8], ecx
0x180010bdf  lea     rcx, [rsp+2E0h+var_270]; unsigned __int16 *
0x180010be4  mov     dword ptr [rsp+2E0h+var_2B0], edx
0x180010be8  mov     edx, 20h ; ' '; unsigned __int64
0x180010bed  mov     dword ptr [rsp+2E0h+var_2B8], r8d
0x180010bf2  lea     r8, aDDDDDD; "%d_%d_%d_%d_%d_%d"
0x180010bf9  mov     dword ptr [rsp+2E0h+var_2C0], r10d
0x180010bfe  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180010c03  mov     ebx, eax
0x180010c05  test    eax, eax
0x180010c07  js      short loc_180010C4D
0x180010c09  lea     rax, [rsp+2E0h+var_270]
0x180010c0e  mov     edx, 401h; unsigned __int64
0x180010c13  mov     [rsp+2E0h+var_2B0], rax
0x180010c18  lea     r9, ?s_szCollectorsLogFolder@CLogFileMgr@@0PAGA; ushort near * CLogFileMgr::s_szCollectorsLogFolder
0x180010c1f  lea     rax, aDiagnosticlogc_3; "DiagnosticLogCSP_Collector"
0x180010c26  mov     [rsp+2E0h+var_2B8], rdi
0x180010c2b  lea     r8, aSSSSEtl; "%s\\%s_%s_%s.etl"
0x180010c32  mov     [rsp+2E0h+var_2C0], rax
0x180010c37  mov     rcx, r14; unsigned __int16 *
0x180010c3a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180010c3f  mov     ebx, eax
0x180010c41  test    eax, eax
0x180010c43  js      short loc_180010C4D
0x180010c45  mov     rcx, rdi; unsigned __int16 *
0x180010c48  call    ?RemoveOlderFiles@CLogFileMgr@@CAXPEBG@Z; CLogFileMgr::RemoveOlderFiles(ushort const *)
0x180010c4d  mov     eax, cs:dword_18004AE90
0x180010c53  cmp     eax, 5
0x180010c56  jbe     short loc_180010C9D
0x180010c58  test    rdi, rdi
0x180010c5b  mov     [rsp+2E0h+var_290], ebx
0x180010c5f  lea     rax, String2
0x180010c66  mov     [rsp+2E0h+var_28C], esi
0x180010c6a  cmovz   rdi, rax
0x180010c6e  lea     rdx, byte_180041A01
0x180010c75  lea     rax, [rsp+2E0h+var_290]
0x180010c7a  mov     qword ptr [rsp+2E0h+SystemTime.wYear], rdi
0x180010c7f  mov     [rsp+2E0h+var_2B0], rax
0x180010c84  lea     rax, [rsp+2E0h+var_28C]
0x180010c89  mov     [rsp+2E0h+var_2B8], rax
0x180010c8e  lea     rax, [rsp+2E0h+SystemTime]
0x180010c93  mov     [rsp+2E0h+var_2C0], rax
0x180010c98  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180010c9d  mov     eax, ebx
0x180010c9f  mov     rcx, [rbp+1E0h+var_20]
0x180010ca6  xor     rcx, rsp; StackCookie
0x180010ca9  call    __security_check_cookie
0x180010cae  lea     r11, [rsp+2E0h+var_10]
0x180010cb6  mov     rbx, [r11+28h]
0x180010cba  mov     rsi, [r11+38h]
0x180010cbe  mov     rsp, r11
0x180010cc1  pop     r14
0x180010cc3  pop     rdi
0x180010cc4  pop     rbp
0x180010cc5  retn
```
