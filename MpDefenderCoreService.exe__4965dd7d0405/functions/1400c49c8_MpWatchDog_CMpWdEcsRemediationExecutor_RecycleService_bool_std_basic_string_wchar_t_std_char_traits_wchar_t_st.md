# MpWatchDog::CMpWdEcsRemediationExecutor::RecycleService(bool,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,ulong)

- ea: `0x1400c49c8`
- end: `0x1400c4dc0`
- name: `?RecycleService@CMpWdEcsRemediationExecutor@MpWatchDog@@AEAAJ_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@Z`
- size: `1016`
- prototype: `__int64 __fastcall(__int64, char, struct SC_HANDLE__ *, int)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1400c2370`

## callees

- `0x14000d658`
- `0x140013ab0`
- `0x140016064`
- `0x1400160cc`
- `0x140016f34`
- `0x14003a5c0`
- `0x140085d38`
- `0x140085d94`
- `0x14008d178`
- `0x1400c49c8`
- `0x1400f5998`
- `0x1400f60dc`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x1400c4c51`
- `KERNEL32!WaitForSingleObject` at `0x1400c4c51`
- `KERNEL32!TerminateProcess` at `0x1400c4bd2`
- `KERNEL32!TerminateProcess` at `0x1400c4bd2`
- `KERNEL32!Sleep` at `0x1400c4d1e`
- `KERNEL32!Sleep` at `0x1400c4d1e`
- `KERNEL32!CloseHandle` at `0x1400c4bc2`
- `KERNEL32!CloseHandle` at `0x1400c4c3d`
- `KERNEL32!CloseHandle` at `0x1400c4cfc`
- `KERNEL32!CloseHandle` at `0x1400c4bc2`
- `KERNEL32!CloseHandle` at `0x1400c4c3d`
- `KERNEL32!CloseHandle` at `0x1400c4cfc`
- `KERNEL32!GetLastError` at `0x1400c4b6d`
- `KERNEL32!GetLastError` at `0x1400c4c1b`
- `KERNEL32!GetLastError` at `0x1400c4c5d`
- `KERNEL32!GetLastError` at `0x1400c4b6d`
- `KERNEL32!GetLastError` at `0x1400c4c1b`
- `KERNEL32!GetLastError` at `0x1400c4c5d`
- `ADVAPI32!QueryServiceStatusEx` at `0x1400c4b63`
- `ADVAPI32!QueryServiceStatusEx` at `0x1400c4b63`
- `ADVAPI32!CloseServiceHandle` at `0x1400c4a21`
- `ADVAPI32!CloseServiceHandle` at `0x1400c4a65`
- `ADVAPI32!CloseServiceHandle` at `0x1400c4d0b`
- `ADVAPI32!CloseServiceHandle` at `0x1400c4d3b`
- `ADVAPI32!CloseServiceHandle` at `0x1400c4d85`
- `ADVAPI32!CloseServiceHandle` at `0x1400c4d94`
- `ADVAPI32!CloseServiceHandle` at `0x1400c4a21`
- `ADVAPI32!CloseServiceHandle` at `0x1400c4a65`
- `ADVAPI32!CloseServiceHandle` at `0x1400c4d0b`
- `ADVAPI32!CloseServiceHandle` at `0x1400c4d3b`
- `ADVAPI32!CloseServiceHandle` at `0x1400c4d85`
- `ADVAPI32!CloseServiceHandle` at `0x1400c4d94`

## pseudocode

```c
__int64 __fastcall MpWatchDog::CMpWdEcsRemediationExecutor::RecycleService(
        __int64 a1,
        char a2,
        struct SC_HANDLE__ *a3,
        int a4)
{
  int v7; // edi
  bool v9; // cc
  struct SC_HANDLE__ *v10; // r8
  SC_HANDLE v11; // rsi
  int IsWindows8OrGreater; // eax
  unsigned int v13; // r8d
  struct SC_HANDLE__ *v14; // rdx
  int v15; // eax
  struct SC_HANDLE__ *v16; // r9
  struct SC_HANDLE__ *v17; // r9
  unsigned int v18; // r9d
  signed int LastError; // eax
  unsigned int started; // ebx
  signed int v21; // eax
  DWORD v22; // eax
  char v23; // di
  signed int v24; // eax
  char v25; // cl
  struct SC_HANDLE__ *v26; // r9
  struct SC_HANDLE__ *v27; // r9
  struct SC_HANDLE__ **v28; // rdi
  int v29; // eax
  SC_HANDLE v30; // rcx
  const wchar_t *pcbBytesNeeded; // [rsp+20h] [rbp-60h]
  unsigned int pcbBytesNeededa; // [rsp+20h] [rbp-60h]
  unsigned int pcbBytesNeededb; // [rsp+20h] [rbp-60h]
  const wchar_t *const *pcbBytesNeededc; // [rsp+20h] [rbp-60h]
  SC_HANDLE hService; // [rsp+30h] [rbp-50h] BYREF
  SC_HANDLE hSCObject; // [rsp+38h] [rbp-48h] BYREF
  HANDLE hObject; // [rsp+40h] [rbp-40h] BYREF
  DWORD v38; // [rsp+48h] [rbp-38h] BYREF
  BYTE Buffer[16]; // [rsp+50h] [rbp-30h] BYREF
  void **v40[2]; // [rsp+60h] [rbp-20h]
  int v41; // [rsp+70h] [rbp-10h]

  hSCObject = 0;
  v7 = CommonUtil::HrOpenSCManager((CommonUtil *)&hSCObject, (struct SC_HANDLE__ **)1, 0, 0, pcbBytesNeeded);
  if ( v7 < 0 )
  {
LABEL_2:
    if ( hSCObject )
      CloseServiceHandle(hSCObject);
    return (unsigned int)v7;
  }
  v9 = *((_QWORD *)a3 + 3) <= 7u;
  v10 = a3;
  hService = 0;
  if ( !v9 )
    v10 = *(struct SC_HANDLE__ **)a3;
  v7 = CommonUtil::HrOpenService(
         (CommonUtil *)&hService,
         (struct SC_HANDLE__ **)hSCObject,
         v10,
         (const wchar_t *)0x34,
         pcbBytesNeededa);
  if ( v7 < 0 )
  {
LABEL_8:
    if ( hService )
      CloseServiceHandle(hService);
    goto LABEL_2;
  }
  if ( a2 )
  {
    v11 = hService;
    IsWindows8OrGreater = MpIsWindows8OrGreater();
    v14 = (struct SC_HANDLE__ *)(unsigned int)(1000 * a4);
    if ( IsWindows8OrGreater )
      v15 = CommonUtil::UtilStopServiceWin8Plus(v11, v14, v13);
    else
      v15 = CommonUtil::UtilStopServiceWin7((struct _QUERY_SERVICE_CONFIGW **)v11, v14, v13);
    if ( v15 >= 0 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
      {
        v17 = a3;
        if ( *((_QWORD *)a3 + 3) > 7u )
          v17 = *(struct SC_HANDLE__ **)a3;
        WPP_SF_S(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 72, &WPP_5083a01b0eaf30ea0f7f8169c36bccb6_Traceguids, v17);
      }
    }
    else if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      LODWORD(v16) = (_DWORD)a3;
      if ( *((_QWORD *)a3 + 3) > 7u )
        v16 = *(struct SC_HANDLE__ **)a3;
      WPP_SF_Sd(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        71,
        (unsigned int)&WPP_5083a01b0eaf30ea0f7f8169c36bccb6_Traceguids,
        (_DWORD)v16,
        v15);
    }
  }
  else
  {
    v41 = 0;
    v38 = 0;
    *(_OWORD *)Buffer = 0;
    *(_OWORD *)v40 = 0;
    if ( !QueryServiceStatusEx(hService, SC_STATUS_PROCESS_INFO, Buffer, 0x24u, &v38) )
    {
      LastError = GetLastError();
      started = LastError;
      if ( LastError > 0 )
        started = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_65;
    }
    if ( *(_DWORD *)&Buffer[4] != 1 )
    {
      hObject = 0;
      v7 = CommonUtil::UtilOpenProcess((CommonUtil *)&hObject, (void **)HIDWORD(v40[1]), 1u, v18);
      if ( v7 < 0 )
      {
        if ( hObject )
          CloseHandle(hObject);
        goto LABEL_8;
      }
      if ( !TerminateProcess(hObject, 0x42Bu) )
      {
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        {
          if ( *((_QWORD *)a3 + 3) > 7u )
            a3 = *(struct SC_HANDLE__ **)a3;
          WPP_SF_Sd(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            73,
            (unsigned int)&WPP_5083a01b0eaf30ea0f7f8169c36bccb6_Traceguids,
            (_DWORD)a3,
            v7);
        }
        v21 = GetLastError();
        started = v21;
        if ( v21 > 0 )
          started = (unsigned __int16)v21 | 0x80070000;
        if ( hObject )
          CloseHandle(hObject);
        goto LABEL_65;
      }
      v22 = WaitForSingleObject(hObject, 0xEA60u);
      v23 = v22;
      if ( v22 )
      {
        v24 = GetLastError();
        v25 = v24;
        if ( v24 > 0 )
          v25 = v24;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        {
          LODWORD(v26) = (_DWORD)a3;
          if ( *((_QWORD *)a3 + 3) > 7u )
            v26 = *(struct SC_HANDLE__ **)a3;
          WPP_SF_SLd(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            74,
            (unsigned int)&WPP_5083a01b0eaf30ea0f7f8169c36bccb6_Traceguids,
            (_DWORD)v26,
            v23,
            v25);
        }
      }
      else if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
      {
        v27 = a3;
        if ( *((_QWORD *)a3 + 3) > 7u )
          v27 = *(struct SC_HANDLE__ **)a3;
        WPP_SF_S(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 75, &WPP_5083a01b0eaf30ea0f7f8169c36bccb6_Traceguids, v27);
      }
      if ( hObject )
        CloseHandle(hObject);
    }
  }
  if ( hService )
  {
    CloseServiceHandle(hService);
    hService = 0;
  }
  Sleep(0x1388u);
  if ( *((_QWORD *)a3 + 3) > 7u )
    a3 = *(struct SC_HANDLE__ **)a3;
  v28 = (struct SC_HANDLE__ **)hSCObject;
  if ( hService )
  {
    CloseServiceHandle(hService);
    hService = 0;
  }
  v29 = CommonUtil::HrOpenService((CommonUtil *)&hService, v28, a3, (const wchar_t *)0x34, pcbBytesNeededb);
  v30 = hService;
  started = v29;
  if ( v29 < 0 )
    goto LABEL_66;
  started = CommonUtil::UtilStartService(
              hService,
              (struct SC_HANDLE__ *)(unsigned int)(1000 * a4),
              0,
              0,
              pcbBytesNeededc);
LABEL_65:
  v30 = hService;
LABEL_66:
  if ( v30 )
    CloseServiceHandle(v30);
  if ( hSCObject )
    CloseServiceHandle(hSCObject);
  return started;
}

```

## disassembly

```asm
0x1400c49c8  mov     [rsp-18h+arg_0], rbx
0x1400c49cd  mov     [rsp-18h+arg_8], rsi
0x1400c49d2  push    rbp
0x1400c49d3  push    rdi
0x1400c49d4  push    r14
0x1400c49d6  mov     rbp, rsp
0x1400c49d9  sub     rsp, 80h
0x1400c49e0  mov     rax, cs:__security_cookie
0x1400c49e7  xor     rax, rsp
0x1400c49ea  mov     [rbp+var_8], rax
0x1400c49ee  mov     r14d, r9d
0x1400c49f1  mov     [rbp+hSCObject], 0
0x1400c49f9  xor     r9d, r9d; wchar_t *
0x1400c49fc  lea     rcx, [rbp+hSCObject]; this
0x1400c4a00  mov     rbx, r8
0x1400c4a03  mov     sil, dl
0x1400c4a06  xor     r8d, r8d; unsigned int
0x1400c4a09  lea     edx, [r9+1]; struct SC_HANDLE__ **
0x1400c4a0d  call    ?HrOpenSCManager@CommonUtil@@YAJPEAPEAUSC_HANDLE__@@KPEB_W1@Z; CommonUtil::HrOpenSCManager(SC_HANDLE__ * *,ulong,wchar_t const *,wchar_t const *)
0x1400c4a12  mov     edi, eax
0x1400c4a14  test    eax, eax
0x1400c4a16  jns     short loc_1400C4A2E
0x1400c4a18  mov     rcx, [rbp+hSCObject]; hSCObject
0x1400c4a1c  test    rcx, rcx
0x1400c4a1f  jz      short loc_1400C4A27
0x1400c4a21  call    cs:__imp_CloseServiceHandle
0x1400c4a27  mov     eax, edi
0x1400c4a29  jmp     loc_1400C4D9C
0x1400c4a2e  cmp     qword ptr [rbx+18h], 7
0x1400c4a33  mov     r8, rbx
0x1400c4a36  mov     [rbp+hService], 0
0x1400c4a3e  jbe     short loc_1400C4A43
0x1400c4a40  mov     r8, [rbx]; struct SC_HANDLE__ *
0x1400c4a43  mov     rdx, [rbp+hSCObject]; struct SC_HANDLE__ **
0x1400c4a47  lea     rcx, [rbp+hService]; this
0x1400c4a4b  mov     r9d, 34h ; '4'; wchar_t *
0x1400c4a51  call    ?HrOpenService@CommonUtil@@YAJPEAPEAUSC_HANDLE__@@PEAU2@PEB_WK@Z; CommonUtil::HrOpenService(SC_HANDLE__ * *,SC_HANDLE__ *,wchar_t const *,ulong)
0x1400c4a56  mov     edi, eax
0x1400c4a58  test    eax, eax
0x1400c4a5a  jns     short loc_1400C4A6D
0x1400c4a5c  mov     rcx, [rbp+hService]; hSCObject
0x1400c4a60  test    rcx, rcx
0x1400c4a63  jz      short loc_1400C4A18
0x1400c4a65  call    cs:__imp_CloseServiceHandle
0x1400c4a6b  jmp     short loc_1400C4A18
0x1400c4a6d  test    sil, sil
0x1400c4a70  jz      loc_1400C4B37
0x1400c4a76  mov     rsi, [rbp+hService]
0x1400c4a7a  imul    edi, r14d, 3E8h
0x1400c4a81  call    MpIsWindows8OrGreater
0x1400c4a86  mov     edx, edi; struct SC_HANDLE__ *
0x1400c4a88  mov     rcx, rsi; this
0x1400c4a8b  test    eax, eax
0x1400c4a8d  jz      short loc_1400C4A96
0x1400c4a8f  call    ?UtilStopServiceWin8Plus@CommonUtil@@YAJPEAUSC_HANDLE__@@K@Z; CommonUtil::UtilStopServiceWin8Plus(SC_HANDLE__ *,ulong)
0x1400c4a94  jmp     short loc_1400C4A9B
0x1400c4a96  call    ?UtilStopServiceWin7@CommonUtil@@YAJPEAUSC_HANDLE__@@K@Z; CommonUtil::UtilStopServiceWin7(SC_HANDLE__ *,ulong)
0x1400c4a9b  mov     r8d, eax
0x1400c4a9e  test    eax, eax
0x1400c4aa0  jns     short loc_1400C4AEF
0x1400c4aa2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c4aa9  lea     rax, WPP_GLOBAL_Control
0x1400c4ab0  cmp     rcx, rax
0x1400c4ab3  jz      loc_1400C4D02
0x1400c4ab9  test    byte ptr [rcx+1Ch], 1
0x1400c4abd  jz      loc_1400C4D02
0x1400c4ac3  cmp     qword ptr [rbx+18h], 7
0x1400c4ac8  mov     r9, rbx
0x1400c4acb  jbe     short loc_1400C4AD0
0x1400c4acd  mov     r9, [rbx]
0x1400c4ad0  mov     rcx, [rcx+10h]
0x1400c4ad4  mov     edx, 47h ; 'G'
0x1400c4ad9  mov     dword ptr [rsp+80h+pcbBytesNeeded], r8d
0x1400c4ade  lea     r8, WPP_5083a01b0eaf30ea0f7f8169c36bccb6_Traceguids
0x1400c4ae5  call    WPP_SF_Sd
0x1400c4aea  jmp     loc_1400C4D02
0x1400c4aef  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c4af6  lea     rax, WPP_GLOBAL_Control
0x1400c4afd  cmp     rcx, rax
0x1400c4b00  jz      loc_1400C4D02
0x1400c4b06  test    byte ptr [rcx+1Ch], 4
0x1400c4b0a  jz      loc_1400C4D02
0x1400c4b10  cmp     qword ptr [rbx+18h], 7
0x1400c4b15  mov     r9, rbx
0x1400c4b18  jbe     short loc_1400C4B1D
0x1400c4b1a  mov     r9, [rbx]
0x1400c4b1d  mov     rcx, [rcx+10h]
0x1400c4b21  lea     r8, WPP_5083a01b0eaf30ea0f7f8169c36bccb6_Traceguids
0x1400c4b28  mov     edx, 48h ; 'H'
0x1400c4b2d  call    WPP_SF_S
0x1400c4b32  jmp     loc_1400C4D02
0x1400c4b37  mov     rcx, [rbp+hService]; hService
0x1400c4b3b  lea     r8, [rbp+Buffer]; lpBuffer
0x1400c4b3f  xor     eax, eax
0x1400c4b41  xorps   xmm0, xmm0
0x1400c4b44  mov     [rbp+var_10], eax
0x1400c4b47  mov     r9d, 24h ; '$'; cbBufSize
0x1400c4b4d  mov     [rbp+var_38], eax
0x1400c4b50  xor     edx, edx; InfoLevel
0x1400c4b52  lea     rax, [rbp+var_38]
0x1400c4b56  mov     [rsp+80h+pcbBytesNeeded], rax; wchar_t **
0x1400c4b5b  movups  xmmword ptr [rbp+Buffer], xmm0
0x1400c4b5f  movups  xmmword ptr [rbp+var_20], xmm0
0x1400c4b63  call    cs:__imp_QueryServiceStatusEx
0x1400c4b69  test    eax, eax
0x1400c4b6b  jnz     short loc_1400C4B8B
0x1400c4b6d  call    cs:__imp_GetLastError
0x1400c4b73  mov     ebx, eax
0x1400c4b75  test    eax, eax
0x1400c4b77  jle     loc_1400C4D7C
0x1400c4b7d  movzx   ebx, ax
0x1400c4b80  or      ebx, 80070000h
0x1400c4b86  jmp     loc_1400C4D7C
0x1400c4b8b  cmp     dword ptr [rbp+Buffer+4], 1
0x1400c4b8f  jz      loc_1400C4D02
0x1400c4b95  mov     edx, dword ptr [rbp+var_20+0Ch]; void **
0x1400c4b98  lea     rcx, [rbp+hObject]; this
0x1400c4b9c  mov     r8d, 1; unsigned int
0x1400c4ba2  mov     [rbp+hObject], 0
0x1400c4baa  call    ?UtilOpenProcess@CommonUtil@@YAJPEAPEAXKK@Z; CommonUtil::UtilOpenProcess(void * *,ulong,ulong)
0x1400c4baf  mov     rcx, [rbp+hObject]; hProcess
0x1400c4bb3  mov     edi, eax
0x1400c4bb5  test    eax, eax
0x1400c4bb7  jns     short loc_1400C4BCD
0x1400c4bb9  test    rcx, rcx
0x1400c4bbc  jz      loc_1400C4A5C
0x1400c4bc2  call    cs:__imp_CloseHandle
0x1400c4bc8  jmp     loc_1400C4A5C
0x1400c4bcd  mov     edx, 42Bh; uExitCode
0x1400c4bd2  call    cs:__imp_TerminateProcess
0x1400c4bd8  test    eax, eax
0x1400c4bda  jnz     short loc_1400C4C48
0x1400c4bdc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c4be3  lea     rax, WPP_GLOBAL_Control
0x1400c4bea  cmp     rcx, rax
0x1400c4bed  jz      short loc_1400C4C1B
0x1400c4bef  test    byte ptr [rcx+1Ch], 1
0x1400c4bf3  jz      short loc_1400C4C1B
0x1400c4bf5  cmp     qword ptr [rbx+18h], 7
0x1400c4bfa  jbe     short loc_1400C4BFF
0x1400c4bfc  mov     rbx, [rbx]
0x1400c4bff  mov     rcx, [rcx+10h]
0x1400c4c03  lea     r8, WPP_5083a01b0eaf30ea0f7f8169c36bccb6_Traceguids
0x1400c4c0a  mov     edx, 49h ; 'I'
0x1400c4c0f  mov     dword ptr [rsp+80h+pcbBytesNeeded], edi
0x1400c4c13  mov     r9, rbx
0x1400c4c16  call    WPP_SF_Sd
0x1400c4c1b  call    cs:__imp_GetLastError
0x1400c4c21  mov     ebx, eax
0x1400c4c23  test    eax, eax
0x1400c4c25  jle     short loc_1400C4C30
0x1400c4c27  movzx   ebx, ax
0x1400c4c2a  or      ebx, 80070000h
0x1400c4c30  mov     rcx, [rbp+hObject]; hObject
0x1400c4c34  test    rcx, rcx
0x1400c4c37  jz      loc_1400C4D7C
0x1400c4c3d  call    cs:__imp_CloseHandle
0x1400c4c43  jmp     loc_1400C4D7C
0x1400c4c48  mov     rcx, [rbp+hObject]; hHandle
0x1400c4c4c  mov     edx, 0EA60h; dwMilliseconds
0x1400c4c51  call    cs:__imp_WaitForSingleObject
0x1400c4c57  mov     edi, eax
0x1400c4c59  test    eax, eax
0x1400c4c5b  jz      short loc_1400C4CB8
0x1400c4c5d  call    cs:__imp_GetLastError
0x1400c4c63  mov     ecx, eax
0x1400c4c65  test    eax, eax
0x1400c4c67  jle     short loc_1400C4C72
0x1400c4c69  movzx   ecx, ax
0x1400c4c6c  or      ecx, 80070000h
0x1400c4c72  mov     r10, cs:WPP_GLOBAL_Control
0x1400c4c79  lea     rax, WPP_GLOBAL_Control
0x1400c4c80  cmp     r10, rax
0x1400c4c83  jz      short loc_1400C4CF3
0x1400c4c85  test    byte ptr [r10+1Ch], 1
0x1400c4c8a  jz      short loc_1400C4CF3
0x1400c4c8c  cmp     qword ptr [rbx+18h], 7
0x1400c4c91  mov     r9, rbx
0x1400c4c94  jbe     short loc_1400C4C99
0x1400c4c96  mov     r9, [rbx]
0x1400c4c99  mov     [rsp+80h+var_58], ecx
0x1400c4c9d  lea     r8, WPP_5083a01b0eaf30ea0f7f8169c36bccb6_Traceguids
0x1400c4ca4  mov     rcx, [r10+10h]
0x1400c4ca8  mov     edx, 4Ah ; 'J'
0x1400c4cad  mov     dword ptr [rsp+80h+pcbBytesNeeded], edi
0x1400c4cb1  call    WPP_SF_SLd
0x1400c4cb6  jmp     short loc_1400C4CF3
0x1400c4cb8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c4cbf  lea     rax, WPP_GLOBAL_Control
0x1400c4cc6  cmp     rcx, rax
0x1400c4cc9  jz      short loc_1400C4CF3
0x1400c4ccb  test    byte ptr [rcx+1Ch], 4
0x1400c4ccf  jz      short loc_1400C4CF3
0x1400c4cd1  cmp     qword ptr [rbx+18h], 7
0x1400c4cd6  mov     r9, rbx
0x1400c4cd9  jbe     short loc_1400C4CDE
0x1400c4cdb  mov     r9, [rbx]
0x1400c4cde  mov     rcx, [rcx+10h]
0x1400c4ce2  lea     r8, WPP_5083a01b0eaf30ea0f7f8169c36bccb6_Traceguids
0x1400c4ce9  mov     edx, 4Bh ; 'K'
0x1400c4cee  call    WPP_SF_S
0x1400c4cf3  mov     rcx, [rbp+hObject]; hObject
0x1400c4cf7  test    rcx, rcx
0x1400c4cfa  jz      short loc_1400C4D02
0x1400c4cfc  call    cs:__imp_CloseHandle
0x1400c4d02  mov     rcx, [rbp+hService]; hSCObject
0x1400c4d06  test    rcx, rcx
0x1400c4d09  jz      short loc_1400C4D19
0x1400c4d0b  call    cs:__imp_CloseServiceHandle
0x1400c4d11  mov     [rbp+hService], 0
0x1400c4d19  mov     ecx, 1388h; dwMilliseconds
0x1400c4d1e  call    cs:__imp_Sleep
0x1400c4d24  cmp     qword ptr [rbx+18h], 7
0x1400c4d29  jbe     short loc_1400C4D2E
0x1400c4d2b  mov     rbx, [rbx]
0x1400c4d2e  mov     rcx, [rbp+hService]; hSCObject
0x1400c4d32  mov     rdi, [rbp+hSCObject]
0x1400c4d36  test    rcx, rcx
0x1400c4d39  jz      short loc_1400C4D49
0x1400c4d3b  call    cs:__imp_CloseServiceHandle
0x1400c4d41  mov     [rbp+hService], 0
0x1400c4d49  mov     r9d, 34h ; '4'; wchar_t *
0x1400c4d4f  lea     rcx, [rbp+hService]; this
0x1400c4d53  mov     r8, rbx; struct SC_HANDLE__ *
0x1400c4d56  mov     rdx, rdi; struct SC_HANDLE__ **
0x1400c4d59  call    ?HrOpenService@CommonUtil@@YAJPEAPEAUSC_HANDLE__@@PEAU2@PEB_WK@Z; CommonUtil::HrOpenService(SC_HANDLE__ * *,SC_HANDLE__ *,wchar_t const *,ulong)
0x1400c4d5e  mov     rcx, [rbp+hService]; hService
0x1400c4d62  mov     ebx, eax
0x1400c4d64  test    eax, eax
0x1400c4d66  js      short loc_1400C4D80
0x1400c4d68  imul    edx, r14d, 3E8h; struct SC_HANDLE__ *
0x1400c4d6f  xor     r9d, r9d; unsigned __int64
0x1400c4d72  xor     r8d, r8d; struct SC_HANDLE__ *
0x1400c4d75  call    ?UtilStartService@CommonUtil@@YAJPEAUSC_HANDLE__@@K_KPEBQEB_W@Z; CommonUtil::UtilStartService(SC_HANDLE__ *,ulong,unsigned __int64,wchar_t const * const *)
0x1400c4d7a  mov     ebx, eax
0x1400c4d7c  mov     rcx, [rbp+hService]; hSCObject
0x1400c4d80  test    rcx, rcx
0x1400c4d83  jz      short loc_1400C4D8B
0x1400c4d85  call    cs:__imp_CloseServiceHandle
0x1400c4d8b  mov     rcx, [rbp+hSCObject]; hSCObject
0x1400c4d8f  test    rcx, rcx
0x1400c4d92  jz      short loc_1400C4D9A
0x1400c4d94  call    cs:__imp_CloseServiceHandle
0x1400c4d9a  mov     eax, ebx
0x1400c4d9c  mov     rcx, [rbp+var_8]
0x1400c4da0  xor     rcx, rsp; StackCookie
0x1400c4da3  call    __security_check_cookie
0x1400c4da8  lea     r11, [rsp+80h+var_s0]
0x1400c4db0  mov     rbx, [r11+20h]
0x1400c4db4  mov     rsi, [r11+28h]
0x1400c4db8  mov     rsp, r11
0x1400c4dbb  pop     r14
0x1400c4dbd  pop     rdi
0x1400c4dbe  pop     rbp
0x1400c4dbf  retn
```
