# CLogFileMgr::Initialize(LogFileType,ushort const *)

- ea: `0x180010230`
- end: `0x180010474`
- name: `?Initialize@CLogFileMgr@@QEAAJW4LogFileType@@PEBG@Z`
- size: `580`
- prototype: `__int64 __fastcall(unsigned __int16 *, int, const unsigned __int16 *)`
- caller_count: `7`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18000911c`
- `0x180009260`
- `0x18000e7e8`
- `0x18000eaf8`
- `0x18000ef04`
- `0x18000f924`
- `0x180011e94`

## callees

- `0x180001250`
- `0x180001b60`
- `0x18000262c`
- `0x180006518`
- `0x180010230`
- `0x18001047c`
- `0x180010678`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18001035e`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18001035e`

## string_xrefs

- `0x1800102c6`: `%s\%s_%s.xml`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
  if ( (unsigned int)dword_180048E90 > 5 )
  {
    v13 = v9;
    v14 = a2;
    if ( !a3 )
      a3 = &String2;
    *(_QWORD *)&SystemTime.wYear = a3;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v6,
      (unsigned int)byte_18003FA01,
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
0x180010230  mov     [rsp-8+arg_8], rbx
0x180010235  mov     [rsp-8+arg_18], rsi
0x18001023a  push    rbp
0x18001023b  push    rdi
0x18001023c  push    r14
0x18001023e  lea     rbp, [rsp-1D0h]
0x180010246  sub     rsp, 2D0h
0x18001024d  mov     rax, cs:__security_cookie
0x180010254  xor     rax, rsp
0x180010257  mov     [rbp+1E0h+var_20], rax
0x18001025e  mov     rdi, r8
0x180010261  mov     esi, edx
0x180010263  mov     r14, rcx
0x180010266  xor     edx, edx; Val
0x180010268  mov     r8d, 20Ah; Size
0x18001026e  lea     rcx, [rbp+1E0h+var_230]; void *
0x180010272  call    memset_0
0x180010277  test    rdi, rdi
0x18001027a  jnz     short loc_180010286
0x18001027c  mov     ebx, 80070057h
0x180010281  jmp     loc_1800103FB
0x180010286  call    ?InitializeLogFolder@CLogFileMgr@@CAJXZ; CLogFileMgr::InitializeLogFolder(void)
0x18001028b  mov     ebx, eax
0x18001028d  test    eax, eax
0x18001028f  js      loc_1800103FB
0x180010295  mov     ecx, esi
0x180010297  test    esi, esi
0x180010299  jz      loc_180010351
0x18001029f  sub     ecx, 1
0x1800102a2  jz      short loc_1800102E6
0x1800102a4  cmp     ecx, 1
0x1800102a7  jz      short loc_1800102B3
0x1800102a9  mov     ebx, 80004005h
0x1800102ae  jmp     loc_1800103FB
0x1800102b3  mov     [rsp+2E0h+var_2B8], rdi
0x1800102b8  lea     rax, aDiagnosticlogc_2; "DiagnosticLogCSP_DeviceStateData"
0x1800102bf  lea     r9, ?s_szDeviceStateDataLogFolder@CLogFileMgr@@0PAGA; ushort near * CLogFileMgr::s_szDeviceStateDataLogFolder
0x1800102c6  lea     r8, aSSSXml; "%s\\%s_%s.xml"
0x1800102cd  mov     edx, 401h; unsigned __int64
0x1800102d2  mov     [rsp+2E0h+var_2C0], rax
0x1800102d7  mov     rcx, r14; unsigned __int16 *
0x1800102da  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800102df  mov     ebx, eax
0x1800102e1  jmp     loc_1800103FB
0x1800102e6  mov     r8, rdi; unsigned __int16 *
0x1800102e9  lea     rcx, [rbp+1E0h+var_230]; unsigned __int16 *
0x1800102ed  mov     edx, 105h; unsigned __int64
0x1800102f2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800102f7  mov     ebx, eax
0x1800102f9  test    eax, eax
0x1800102fb  js      loc_1800103FB
0x180010301  xor     edx, edx
0x180010303  xor     eax, eax
0x180010305  cmp     ax, [rbp+1E0h+var_230]
0x180010309  jz      short loc_18001032E
0x18001030b  movsxd  rax, edx
0x18001030e  cmp     [rbp+rax*2+1E0h+var_230], 2Fh ; '/'
0x180010314  jnz     short loc_180010320
0x180010316  mov     ecx, 5Fh ; '_'
0x18001031b  mov     [rbp+rax*2+1E0h+var_230], cx
0x180010320  inc     edx
0x180010322  xor     eax, eax
0x180010324  movsxd  rcx, edx
0x180010327  cmp     ax, [rbp+rcx*2+1E0h+var_230]
0x18001032c  jnz     short loc_18001030B
0x18001032e  lea     rax, [rbp+1E0h+var_230]
0x180010332  mov     [rsp+2E0h+var_2B8], rax
0x180010337  lea     r9, ?s_szChannelsLogFolder@CLogFileMgr@@0PAGA; ushort near * CLogFileMgr::s_szChannelsLogFolder
0x18001033e  lea     rax, aDiagnosticlogc_0; "DiagnosticLogCSP_Channel"
0x180010345  lea     r8, aSSSEvtx; "%s\\%s_%s.evtx"
0x18001034c  jmp     loc_1800102CD
0x180010351  xorps   xmm0, xmm0
0x180010354  lea     rcx, [rsp+2E0h+SystemTime]; lpSystemTime
0x180010359  movups  xmmword ptr [rsp+2E0h+SystemTime.wYear], xmm0
0x18001035e  call    cs:__imp_GetLocalTime
0x180010364  movzx   ecx, [rsp+2E0h+SystemTime.wMinute]
0x180010369  movzx   edx, [rsp+2E0h+SystemTime.wHour]
0x18001036e  movzx   r8d, [rsp+2E0h+SystemTime.wDay]
0x180010374  movzx   eax, [rsp+2E0h+SystemTime.wSecond]
0x180010379  movzx   r10d, [rsp+2E0h+SystemTime.wMonth]
0x18001037f  movzx   r9d, [rsp+2E0h+SystemTime.wYear]
0x180010385  mov     [rsp+2E0h+var_2A0], eax
0x180010389  mov     [rsp+2E0h+var_2A8], ecx
0x18001038d  lea     rcx, [rsp+2E0h+var_270]; unsigned __int16 *
0x180010392  mov     dword ptr [rsp+2E0h+var_2B0], edx
0x180010396  mov     edx, 20h ; ' '; unsigned __int64
0x18001039b  mov     dword ptr [rsp+2E0h+var_2B8], r8d
0x1800103a0  lea     r8, aDDDDDD; "%d_%d_%d_%d_%d_%d"
0x1800103a7  mov     dword ptr [rsp+2E0h+var_2C0], r10d
0x1800103ac  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800103b1  mov     ebx, eax
0x1800103b3  test    eax, eax
0x1800103b5  js      short loc_1800103FB
0x1800103b7  lea     rax, [rsp+2E0h+var_270]
0x1800103bc  mov     edx, 401h; unsigned __int64
0x1800103c1  mov     [rsp+2E0h+var_2B0], rax
0x1800103c6  lea     r9, ?s_szCollectorsLogFolder@CLogFileMgr@@0PAGA; ushort near * CLogFileMgr::s_szCollectorsLogFolder
0x1800103cd  lea     rax, aDiagnosticlogc_3; "DiagnosticLogCSP_Collector"
0x1800103d4  mov     [rsp+2E0h+var_2B8], rdi
0x1800103d9  lea     r8, aSSSSEtl; "%s\\%s_%s_%s.etl"
0x1800103e0  mov     [rsp+2E0h+var_2C0], rax
0x1800103e5  mov     rcx, r14; unsigned __int16 *
0x1800103e8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800103ed  mov     ebx, eax
0x1800103ef  test    eax, eax
0x1800103f1  js      short loc_1800103FB
0x1800103f3  mov     rcx, rdi; unsigned __int16 *
0x1800103f6  call    ?RemoveOlderFiles@CLogFileMgr@@CAXPEBG@Z; CLogFileMgr::RemoveOlderFiles(ushort const *)
0x1800103fb  mov     eax, cs:dword_180048E90
0x180010401  cmp     eax, 5
0x180010404  jbe     short loc_18001044B
0x180010406  test    rdi, rdi
0x180010409  mov     [rsp+2E0h+var_290], ebx
0x18001040d  lea     rax, String2
0x180010414  mov     [rsp+2E0h+var_28C], esi
0x180010418  cmovz   rdi, rax
0x18001041c  lea     rdx, byte_18003FA01
0x180010423  lea     rax, [rsp+2E0h+var_290]
0x180010428  mov     qword ptr [rsp+2E0h+SystemTime.wYear], rdi
0x18001042d  mov     [rsp+2E0h+var_2B0], rax
0x180010432  lea     rax, [rsp+2E0h+var_28C]
0x180010437  mov     [rsp+2E0h+var_2B8], rax
0x18001043c  lea     rax, [rsp+2E0h+SystemTime]
0x180010441  mov     [rsp+2E0h+var_2C0], rax
0x180010446  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001044b  mov     eax, ebx
0x18001044d  mov     rcx, [rbp+1E0h+var_20]
0x180010454  xor     rcx, rsp; StackCookie
0x180010457  call    __security_check_cookie
0x18001045c  lea     r11, [rsp+2E0h+var_10]
0x180010464  mov     rbx, [r11+28h]
0x180010468  mov     rsi, [r11+38h]
0x18001046c  mov     rsp, r11
0x18001046f  pop     r14
0x180010471  pop     rdi
0x180010472  pop     rbp
0x180010473  retn
```
