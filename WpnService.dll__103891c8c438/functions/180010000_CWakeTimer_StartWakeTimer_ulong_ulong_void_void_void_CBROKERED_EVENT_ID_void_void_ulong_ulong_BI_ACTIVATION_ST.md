# CWakeTimer::StartWakeTimer(ulong,ulong,void *,void (*)(void *,_CBROKERED_EVENT_ID,void *,void *,ulong,ulong,_BI_ACTIVATION_STATUS *),void * *)

- ea: `0x180010000`
- end: `0x18001060f`
- name: `?StartWakeTimer@CWakeTimer@@SAJKKPEAXP6AX0U_CBROKERED_EVENT_ID@@00KKPEAW4_BI_ACTIVATION_STATUS@@@ZPEAPEAX@Z`
- size: `1551`
- prototype: `__int64 __fastcall(unsigned int, unsigned int, void *, void (__high *)(void *, struct _CBROKERED_EVENT_ID, void *, void *, unsigned int, unsigned int, enum _BI_ACTIVATION_STATUS *), void **)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000ff28`

## callees

- `0x180010000`
- `0x1800109d4`
- `0x180026200`
- `0x1800265d0`
- `0x180026630`
- `0x180026cd0`
- `0x1800341b4`
- `0x1800341f4`
- `0x180034224`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800100d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010195`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800102da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800100d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010195`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800102da`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800100cb`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800100cb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800100b8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800100b8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800105b6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800105b6`
- `ntdll!RtlNtStatusToDosError` at `0x180010505`
- `ntdll!RtlNtStatusToDosError` at `0x180010505`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800103ee`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800103ee`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180010187`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800102cc`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180010187`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800102cc`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180010365`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180010365`
- `EventAggregation!EaCreateAggregatedEvent` at `0x1800104f5`
- `EventAggregation!EaCreateAggregatedEvent` at `0x1800104f5`

## string_xrefs

- `0x180010122`: `onecoreuap\base\diagnosis\platform\notifications\prov\common\waketimerwrapper.cpp`
- `0x1800101e3`: `onecoreuap\base\diagnosis\platform\notifications\prov\common\waketimerwrapper.cpp`
- `0x180010272`: `onecoreuap\base\diagnosis\platform\notifications\prov\common\waketimerwrapper.cpp`
- `0x18001032a`: `onecoreuap\base\diagnosis\platform\notifications\prov\common\waketimerwrapper.cpp`
- `0x1800103ab`: `onecoreuap\base\diagnosis\platform\notifications\prov\common\waketimerwrapper.cpp`
- `0x180010555`: `onecoreuap\base\diagnosis\platform\notifications\prov\common\waketimerwrapper.cpp`

## pseudocode

```c
__int64 __fastcall CWakeTimer::StartWakeTimer(
        unsigned int a1,
        unsigned int a2,
        void *a3,
        void (__high *a4)(void *, struct _CBROKERED_EVENT_ID, void *, void *, unsigned int, unsigned int, enum _BI_ACTIVATION_STATUS *),
        void **a5)
{
  __int64 v7; // r15
  unsigned int v8; // edi
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  __int64 v11; // r8
  __int64 v12; // r8
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // r9
  signed int v16; // eax
  __int64 v17; // r8
  PSID *v18; // rbx
  __int64 v19; // r8
  signed int v20; // eax
  __int64 v21; // r8
  _QWORD *v22; // rcx
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // r9
  NTSTATUS AggregatedEvent; // eax
  signed int v27; // eax
  __int64 v28; // r8
  DWORD TokenInformationLength; // [rsp+50h] [rbp-B0h] BYREF
  void *TokenHandle; // [rsp+58h] [rbp-A8h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v33[10]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v34[4]; // [rsp+C0h] [rbp-40h] BYREF
  const wchar_t *v35; // [rsp+E0h] [rbp-20h] BYREF
  _DWORD v36[6]; // [rsp+E8h] [rbp-18h] BYREF
  const wchar_t *v37; // [rsp+100h] [rbp+0h]
  int v38; // [rsp+108h] [rbp+8h]
  __int64 v39; // [rsp+110h] [rbp+10h]
  const wchar_t *v40; // [rsp+120h] [rbp+20h]
  int v41; // [rsp+128h] [rbp+28h]
  int v42; // [rsp+130h] [rbp+30h]
  const wchar_t *v43; // [rsp+140h] [rbp+40h]
  int v44; // [rsp+148h] [rbp+48h]
  unsigned int v45; // [rsp+150h] [rbp+50h]
  const wchar_t *v46; // [rsp+160h] [rbp+60h]
  int v47; // [rsp+168h] [rbp+68h]
  const wchar_t *v48; // [rsp+170h] [rbp+70h]
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+D8h]

  v7 = a1;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10);
  }
  TokenHandle = 0;
  TokenInformationLength = 0;
  v8 = 0;
  SystemTimeAsFileTime = 0;
  memset_0(v33, 0, 0x48u);
  memset(v34, 0, sizeof(v34));
  v35 = 0;
  memset_0(v36, 0, 0x98u);
  *a5 = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 0x20008u, &TokenHandle) )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    if ( (v8 & 0x80000000) != 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, v11, v8);
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x25,
        (int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\common\\waketimerwrapper.cpp",
        (const char *)v8);
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
      {
        v14 = 12;
LABEL_16:
        v15 = v8;
LABEL_17:
        WPP_SF_D(v13[2], v14, &WPP_03ea58026b6b32dbcd789d1e98aae4a4_Traceguids, v15);
LABEL_72:
        v13 = WPP_GLOBAL_Control;
        goto LABEL_73;
      }
      goto LABEL_73;
    }
  }
  if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) )
    goto LABEL_31;
  v16 = GetLastError();
  v8 = v16;
  if ( v16 == 122 )
  {
    v8 = 0;
    goto LABEL_31;
  }
  if ( v16 > 0 )
    v8 = (unsigned __int16)v16 | 0x80070000;
  if ( (v8 & 0x80000000) == 0 )
  {
LABEL_31:
    v18 = (PSID *)operator new[](TokenInformationLength, (const struct std::nothrow_t *)&std::nothrow);
    if ( !v18 )
    {
      v8 = -2147024882;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, v19, 2147942414LL);
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x3D,
        (int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\common\\waketimerwrapper.cpp",
        (const char *)0x8007000ELL);
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
      {
        v14 = 16;
        v15 = 2147942414LL;
        goto LABEL_17;
      }
      goto LABEL_73;
    }
    if ( GetTokenInformation(TokenHandle, TokenUser, v18, TokenInformationLength, &TokenInformationLength) )
      goto LABEL_82;
    v20 = GetLastError();
    v8 = v20;
    if ( v20 > 0 )
      v8 = (unsigned __int16)v20 | 0x80070000;
    if ( (v8 & 0x80000000) == 0 )
    {
LABEL_82:
      if ( !IsValidSid(*v18) )
      {
        v8 = -2147467259;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, v24, 2147500037LL);
        }
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x4D,
          (int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\common\\waketimerwrapper.cpp",
          (const char *)0x80004005LL);
        v22 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
          goto LABEL_71;
        v23 = 20;
        v25 = 2147500037LL;
        goto LABEL_70;
      }
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      v35 = L"Type";
      v37 = L"InitialDueTime";
      *(_QWORD *)((char *)v34 + 4) = *(_QWORD *)&GUID_TIME_BROKER.Data2;
      v40 = L"WakeEnabled";
      v39 = 10000 * v7 + *(_QWORD *)&SystemTimeAsFileTime;
      v43 = L"WindowInSeconds";
      v48 = L"WnsClientConnectionProvider";
      v33[7] = L"WnsClientConnectionProvider";
      v46 = L"ClientId";
      HIDWORD(v34[1]) = *(_DWORD *)&GUID_TIME_BROKER.Data4[4];
      LOWORD(v34[2]) = 5;
      v34[3] = &v35;
      v45 = a2 / 0x3E8;
      v33[0] = v34;
      v36[0] = 0;
      v36[2] = 4;
      v38 = 1;
      v41 = 0;
      v42 = 1;
      v44 = 0;
      v47 = 2;
      LODWORD(v34[0]) = -1244867089;
      v33[8] = *v18;
      AggregatedEvent = EaCreateAggregatedEvent(v33, 0, &Wns::WakeTimerCallback, 0, 0, 0, a3, 0, a5);
      if ( AggregatedEvent >= 0 )
        goto LABEL_71;
      v27 = RtlNtStatusToDosError(AggregatedEvent);
      v8 = v27;
      if ( v27 > 0 )
        v8 = (unsigned __int16)v27 | 0x80070000;
      if ( (v8 & 0x80000000) == 0 )
        goto LABEL_71;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, v28, v8);
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x88,
        (int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\common\\waketimerwrapper.cpp",
        (const char *)v8);
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
        goto LABEL_71;
      v23 = 22;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, v21, v8);
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x45,
        (int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\common\\waketimerwrapper.cpp",
        (const char *)v8);
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
        goto LABEL_71;
      v23 = 18;
    }
    v25 = v8;
LABEL_70:
    WPP_SF_D(v22[2], v23, &WPP_03ea58026b6b32dbcd789d1e98aae4a4_Traceguids, v25);
LABEL_71:
    operator delete(v18);
    goto LABEL_72;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, v17, v8);
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x30,
    (int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\common\\waketimerwrapper.cpp",
    (const char *)v8);
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
  {
    v14 = 14;
    goto LABEL_16;
  }
LABEL_73:
  if ( TokenHandle )
  {
    CloseHandle(TokenHandle);
    v13 = WPP_GLOBAL_Control;
    TokenHandle = 0;
  }
  if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 8) != 0 && *((_BYTE *)v13 + 25) >= 6u )
    WPP_SF_d(v13[2], 23, v12, v8);
  return v8;
}

```

## disassembly

```asm
0x180010000  push    rbp
0x180010002  push    rbx
0x180010003  push    rsi
0x180010004  push    rdi
0x180010005  push    r12
0x180010007  push    r13
0x180010009  push    r14
0x18001000b  push    r15
0x18001000d  lea     rbp, [rsp-98h]
0x180010015  sub     rsp, 198h
0x18001001c  mov     rax, cs:__security_cookie
0x180010023  xor     rax, rsp
0x180010026  mov     [rbp+0D0h+var_50], rax
0x18001002d  mov     rsi, [rbp+0D0h+arg_20]
0x180010034  mov     r12, r8
0x180010037  mov     r14d, edx
0x18001003a  mov     r15d, ecx
0x18001003d  mov     rcx, cs:WPP_GLOBAL_Control
0x180010044  lea     rbx, WPP_GLOBAL_Control
0x18001004b  cmp     rcx, rbx
0x18001004e  jz      short loc_18001006A
0x180010050  test    byte ptr [rcx+1Ch], 8
0x180010054  jz      short loc_18001006A
0x180010056  cmp     byte ptr [rcx+19h], 6
0x18001005a  jb      short loc_18001006A
0x18001005c  mov     rcx, [rcx+10h]
0x180010060  mov     edx, 0Ah
0x180010065  call    WPP_SF_
0x18001006a  xor     r13d, r13d
0x18001006d  lea     rcx, [rsp+1D0h+var_160]; void *
0x180010072  xor     edx, edx; Val
0x180010074  mov     [rsp+1D0h+TokenHandle], r13
0x180010079  mov     r8d, 48h ; 'H'; Size
0x18001007f  mov     [rsp+1D0h+TokenInformationLength], r13d
0x180010084  mov     edi, r13d
0x180010087  mov     qword ptr [rsp+1D0h+SystemTimeAsFileTime.dwLowDateTime], r13
0x18001008c  call    memset_0
0x180010091  xorps   xmm0, xmm0
0x180010094  mov     [rbp+0D0h+var_110], r13d
0x180010098  movups  [rbp+0D0h+var_10C], xmm0
0x18001009c  xor     edx, edx; Val
0x18001009e  mov     [rbp+0D0h+var_F0], r13
0x1800100a2  mov     r8d, 98h; Size
0x1800100a8  lea     rcx, [rbp+0D0h+var_E8]; void *
0x1800100ac  movups  [rbp+0D0h+var_10C+0Ch], xmm0
0x1800100b0  call    memset_0
0x1800100b5  mov     [rsi], r13
0x1800100b8  call    cs:__imp_GetCurrentProcess
0x1800100be  lea     r8, [rsp+1D0h+TokenHandle]; TokenHandle
0x1800100c3  mov     edx, 20008h; DesiredAccess
0x1800100c8  mov     rcx, rax; ProcessHandle
0x1800100cb  call    cs:__imp_OpenProcessToken
0x1800100d1  test    eax, eax
0x1800100d3  jnz     loc_18001016D
0x1800100d9  call    cs:__imp_GetLastError
0x1800100df  mov     edi, eax
0x1800100e1  test    eax, eax
0x1800100e3  jle     short loc_1800100EE
0x1800100e5  movzx   edi, ax
0x1800100e8  or      edi, 80070000h
0x1800100ee  test    edi, edi
0x1800100f0  jns     short loc_18001016D
0x1800100f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800100f9  cmp     rcx, rbx
0x1800100fc  jz      short loc_18001011B
0x1800100fe  test    byte ptr [rcx+1Ch], 8
0x180010102  jz      short loc_18001011B
0x180010104  cmp     byte ptr [rcx+19h], 2
0x180010108  jb      short loc_18001011B
0x18001010a  mov     rcx, [rcx+10h]
0x18001010e  mov     edx, 0Bh
0x180010113  mov     r9d, edi
0x180010116  call    WPP_SF_d
0x18001011b  mov     rcx, [rbp+0D8h]; this
0x180010122  lea     r8, aOnecoreuapBase_7; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180010129  mov     r9d, edi; char *
0x18001012c  mov     edx, 25h ; '%'; void *
0x180010131  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180010136  mov     rcx, cs:WPP_GLOBAL_Control
0x18001013d  cmp     rcx, rbx
0x180010140  jz      loc_1800105A9
0x180010146  test    byte ptr [rcx+1Ch], 80h
0x18001014a  jz      loc_1800105A9
0x180010150  mov     edx, 0Ch
0x180010155  mov     r9d, edi
0x180010158  mov     rcx, [rcx+10h]
0x18001015c  lea     r8, WPP_03ea58026b6b32dbcd789d1e98aae4a4_Traceguids
0x180010163  call    WPP_SF_D
0x180010168  jmp     loc_1800105A2
0x18001016d  mov     rcx, [rsp+1D0h+TokenHandle]; TokenHandle
0x180010172  lea     rax, [rsp+1D0h+TokenInformationLength]
0x180010177  xor     r9d, r9d; TokenInformationLength
0x18001017a  mov     [rsp+1D0h+ReturnLength], rax; int
0x18001017f  xor     r8d, r8d; TokenInformation
0x180010182  mov     edx, 1; TokenInformationClass
0x180010187  call    cs:__imp_GetTokenInformation
0x18001018d  test    eax, eax
0x18001018f  jnz     loc_18001021E
0x180010195  call    cs:__imp_GetLastError
0x18001019b  mov     edi, eax
0x18001019d  cmp     eax, 7Ah ; 'z'
0x1800101a0  jz      short loc_18001021B
0x1800101a2  test    eax, eax
0x1800101a4  jle     short loc_1800101AF
0x1800101a6  movzx   edi, ax
0x1800101a9  or      edi, 80070000h
0x1800101af  test    edi, edi
0x1800101b1  jns     short loc_18001021E
0x1800101b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800101ba  cmp     rcx, rbx
0x1800101bd  jz      short loc_1800101DC
0x1800101bf  test    byte ptr [rcx+1Ch], 8
0x1800101c3  jz      short loc_1800101DC
0x1800101c5  cmp     byte ptr [rcx+19h], 2
0x1800101c9  jb      short loc_1800101DC
0x1800101cb  mov     rcx, [rcx+10h]
0x1800101cf  mov     edx, 0Dh
0x1800101d4  mov     r9d, edi
0x1800101d7  call    WPP_SF_d
0x1800101dc  mov     rcx, [rbp+0D8h]; this
0x1800101e3  lea     r8, aOnecoreuapBase_7; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800101ea  mov     r9d, edi; char *
0x1800101ed  mov     edx, 30h ; '0'; void *
0x1800101f2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800101f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800101fe  cmp     rcx, rbx
0x180010201  jz      loc_1800105A9
0x180010207  test    byte ptr [rcx+1Ch], 80h
0x18001020b  jz      loc_1800105A9
0x180010211  mov     edx, 0Eh
0x180010216  jmp     loc_180010155
0x18001021b  mov     edi, r13d
0x18001021e  mov     ecx, [rsp+1D0h+TokenInformationLength]; unsigned __int64
0x180010222  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180010229  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001022e  mov     rbx, rax
0x180010231  test    rax, rax
0x180010234  jnz     short loc_1800102B0
0x180010236  mov     edi, 8007000Eh
0x18001023b  mov     rcx, cs:WPP_GLOBAL_Control
0x180010242  lea     rbx, WPP_GLOBAL_Control
0x180010249  cmp     rcx, rbx
0x18001024c  jz      short loc_18001026B
0x18001024e  test    byte ptr [rcx+1Ch], 8
0x180010252  jz      short loc_18001026B
0x180010254  cmp     byte ptr [rcx+19h], 2
0x180010258  jb      short loc_18001026B
0x18001025a  mov     rcx, [rcx+10h]
0x18001025e  mov     edx, 0Fh
0x180010263  mov     r9d, edi
0x180010266  call    WPP_SF_d
0x18001026b  mov     rcx, [rbp+0D8h]; this
0x180010272  lea     r8, aOnecoreuapBase_7; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180010279  mov     r9d, edi; char *
0x18001027c  mov     edx, 3Dh ; '='; void *
0x180010281  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180010286  mov     rcx, cs:WPP_GLOBAL_Control
0x18001028d  cmp     rcx, rbx
0x180010290  jz      loc_1800105A9
0x180010296  test    byte ptr [rcx+1Ch], 80h
0x18001029a  jz      loc_1800105A9
0x1800102a0  mov     edx, 10h
0x1800102a5  mov     r9d, 8007000Eh
0x1800102ab  jmp     loc_180010158
0x1800102b0  mov     r9d, [rsp+1D0h+TokenInformationLength]; TokenInformationLength
0x1800102b5  lea     rax, [rsp+1D0h+TokenInformationLength]
0x1800102ba  mov     rcx, [rsp+1D0h+TokenHandle]; TokenHandle
0x1800102bf  mov     r8, rbx; TokenInformation
0x1800102c2  mov     edx, 1; TokenInformationClass
0x1800102c7  mov     [rsp+1D0h+ReturnLength], rax; int
0x1800102cc  call    cs:__imp_GetTokenInformation
0x1800102d2  test    eax, eax
0x1800102d4  jnz     loc_180010362
0x1800102da  call    cs:__imp_GetLastError
0x1800102e0  mov     edi, eax
0x1800102e2  test    eax, eax
0x1800102e4  jle     short loc_1800102EF
0x1800102e6  movzx   edi, ax
0x1800102e9  or      edi, 80070000h
0x1800102ef  test    edi, edi
0x1800102f1  jns     short loc_180010362
0x1800102f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800102fa  lea     rsi, WPP_GLOBAL_Control
0x180010301  cmp     rcx, rsi
0x180010304  jz      short loc_180010323
0x180010306  test    byte ptr [rcx+1Ch], 8
0x18001030a  jz      short loc_180010323
0x18001030c  cmp     byte ptr [rcx+19h], 2
0x180010310  jb      short loc_180010323
0x180010312  mov     rcx, [rcx+10h]
0x180010316  mov     edx, 11h
0x18001031b  mov     r9d, edi
0x18001031e  call    WPP_SF_d
0x180010323  mov     rcx, [rbp+0D8h]; this
0x18001032a  lea     r8, aOnecoreuapBase_7; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180010331  mov     r9d, edi; char *
0x180010334  mov     edx, 45h ; 'E'; void *
0x180010339  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001033e  mov     rcx, cs:WPP_GLOBAL_Control
0x180010345  cmp     rcx, rsi
0x180010348  jz      loc_180010593
0x18001034e  test    byte ptr [rcx+1Ch], 80h
0x180010352  jz      loc_180010593
0x180010358  mov     edx, 12h
0x18001035d  jmp     loc_180010580
0x180010362  mov     rcx, [rbx]; pSid
0x180010365  call    cs:__imp_IsValidSid
0x18001036b  test    eax, eax
0x18001036d  jnz     short loc_1800103E9
0x18001036f  mov     edi, 80004005h
0x180010374  mov     rcx, cs:WPP_GLOBAL_Control
0x18001037b  lea     rsi, WPP_GLOBAL_Control
0x180010382  cmp     rcx, rsi
0x180010385  jz      short loc_1800103A4
0x180010387  test    byte ptr [rcx+1Ch], 8
0x18001038b  jz      short loc_1800103A4
0x18001038d  cmp     byte ptr [rcx+19h], 2
0x180010391  jb      short loc_1800103A4
0x180010393  mov     rcx, [rcx+10h]
0x180010397  mov     edx, 13h
0x18001039c  mov     r9d, edi
0x18001039f  call    WPP_SF_d
0x1800103a4  mov     rcx, [rbp+0D8h]; this
0x1800103ab  lea     r8, aOnecoreuapBase_7; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800103b2  mov     r9d, edi; char *
0x1800103b5  mov     edx, 4Dh ; 'M'; void *
0x1800103ba  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800103bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800103c6  cmp     rcx, rsi
0x1800103c9  jz      loc_180010593
0x1800103cf  test    byte ptr [rcx+1Ch], 80h
0x1800103d3  jz      loc_180010593
0x1800103d9  mov     edx, 14h
0x1800103de  mov     r9d, 80004005h
0x1800103e4  jmp     loc_180010583
0x1800103e9  lea     rcx, [rsp+1D0h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800103ee  call    cs:__imp_GetSystemTimeAsFileTime
0x1800103f4  mov     edx, [rsp+1D0h+SystemTimeAsFileTime.dwHighDateTime]
0x1800103f8  lea     rax, aType; "Type"
0x1800103ff  movsd   xmm0, qword ptr cs:GUID_TIME_BROKER.Data2
0x180010407  lea     r8, ?WakeTimerCallback@Wns@@YAXPEAXU_CBROKERED_EVENT_ID@@00KKPEAW4_BI_ACTIVATION_STATUS@@@Z; Wns::WakeTimerCallback(void *,_CBROKERED_EVENT_ID,void *,void *,ulong,ulong,_BI_ACTIVATION_STATUS *)
0x18001040e  mov     [rbp+0D0h+var_F0], rax
0x180010412  xor     r9d, r9d
0x180010415  shl     rdx, 20h
0x180010419  lea     rax, aInitialduetime; "InitialDueTime"
0x180010420  mov     [rbp+0D0h+var_D0], rax
0x180010424  mov     eax, [rsp+1D0h+SystemTimeAsFileTime.dwLowDateTime]
0x180010428  or      rdx, rax
0x18001042b  mov     [rsp+1D0h+var_190], rsi
0x180010430  imul    rcx, r15, 2710h
0x180010437  movsd   qword ptr [rbp+0D0h+var_10C], xmm0
0x18001043c  mov     [rsp+1D0h+var_198], r13d
0x180010441  lea     rax, aWakeenabled; "WakeEnabled"
0x180010448  mov     [rbp+0D0h+var_B0], rax
0x18001044c  add     rdx, rcx
0x18001044f  mov     [rbp+0D0h+var_C0], rdx
0x180010453  lea     rax, aWindowinsecond; "WindowInSeconds"
0x18001045a  mov     [rbp+0D0h+var_90], rax
0x18001045e  lea     rcx, aWnsclientconne; "WnsClientConnectionProvider"
0x180010465  mov     [rbp+0D0h+var_60], rcx
0x180010469  mov     eax, 10624DD3h
0x18001046e  mul     r14d
0x180010471  lea     rax, aClientid; "ClientId"
0x180010478  mov     [rbp+0D0h+var_128], rcx
0x18001047c  mov     [rbp+0D0h+var_70], rax
0x180010480  lea     rcx, [rsp+1D0h+var_160]
0x180010485  mov     eax, dword ptr cs:GUID_TIME_BROKER.Data4+4
0x18001048b  mov     dword ptr [rbp+0D0h+var_10C+8], eax
0x18001048e  mov     eax, 5
0x180010493  mov     word ptr [rbp+0D0h+var_10C+0Ch], ax
0x180010497  lea     rax, [rbp+0D0h+var_F0]
0x18001049b  mov     [rbp+0D0h+var_F8], rax
0x18001049f  lea     rax, [rbp+0D0h+var_110]
0x1800104a3  shr     edx, 6
0x1800104a6  mov     [rbp+0D0h+var_80], edx
0x1800104a9  xor     edx, edx
0x1800104ab  mov     [rsp+1D0h+var_160], rax
0x1800104b0  mov     [rbp+0D0h+var_E8], r13d
0x1800104b4  mov     [rbp+0D0h+var_E0], 4
0x1800104bb  mov     [rbp+0D0h+var_C8], 1
0x1800104c2  mov     [rbp+0D0h+var_A8], r13d
0x1800104c6  mov     [rbp+0D0h+var_A0], 1
0x1800104cd  mov     [rbp+0D0h+var_88], r13d
0x1800104d1  mov     [rbp+0D0h+var_68], 2
0x1800104d8  mov     [rbp+0D0h+var_110], 0B5CCD5EFh
0x1800104df  mov     rax, [rbx]
0x1800104e2  mov     [rsp+1D0h+var_1A0], r12
0x1800104e7  mov     [rsp+1D0h+var_1A8], r13
0x1800104ec  mov     [rbp+0D0h+var_120], rax
0x1800104f0  mov     [rsp+1D0h+ReturnLength], r13; int
0x1800104f5  call    cs:__imp_EaCreateAggregatedEvent
0x1800104fb  test    eax, eax
0x1800104fd  jns     loc_180010593
0x180010503  mov     ecx, eax; Status
0x180010505  call    cs:__imp_RtlNtStatusToDosError
0x18001050b  mov     edi, eax
0x18001050d  test    eax, eax
0x18001050f  jle     short loc_18001051A
0x180010511  movzx   edi, ax
0x180010514  or      edi, 80070000h
  ... truncated ...
```
