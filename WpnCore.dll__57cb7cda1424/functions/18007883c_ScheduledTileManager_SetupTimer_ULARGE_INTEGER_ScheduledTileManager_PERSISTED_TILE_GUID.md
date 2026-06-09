# ScheduledTileManager::SetupTimer(_ULARGE_INTEGER,ScheduledTileManager::_PERSISTED_TILE *,_GUID *)

- ea: `0x18007883c`
- end: `0x180078ccd`
- name: `?SetupTimer@ScheduledTileManager@@AEAAJT_ULARGE_INTEGER@@PEAU_PERSISTED_TILE@1@PEAU_GUID@@@Z`
- size: `1169`
- prototype: `int(ScheduledTileManager *__hidden this, union _ULARGE_INTEGER, struct ScheduledTileManager::_PERSISTED_TILE *, struct _GUID *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18008e7b0`

## callees

- `0x18002ee38`
- `0x18007883c`
- `0x180078cd4`
- `0x1800af0a4`
- `0x1800b99f0`
- `0x1800ba574`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078bb1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078bb1`
- `ntdll!RtlNtStatusToDosError` at `0x180078ac1`
- `ntdll!RtlNtStatusToDosError` at `0x180078b96`
- `ntdll!RtlNtStatusToDosError` at `0x180078ac1`
- `ntdll!RtlNtStatusToDosError` at `0x180078b96`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800788c4`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800788c4`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtCreateEventForPackageName` at `0x180078afd`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtCreateEventForPackageName` at `0x180078afd`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtAssociateActivationProxy` at `0x180078a20`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtAssociateActivationProxy` at `0x180078a20`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtDisassociateWorkItemEx` at `0x180078cc2`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtDisassociateWorkItemEx` at `0x180078cc2`
- `TimeBrokerClient!TbCreateEvent` at `0x1800789cb`
- `TimeBrokerClient!TbCreateEvent` at `0x1800789cb`
- `TimeBrokerClient!TbDeleteEvent` at `0x180078a9b`
- `TimeBrokerClient!TbDeleteEvent` at `0x180078a9b`
- `SystemEventsBrokerClient!SebDeleteEvent` at `0x180078ab7`
- `SystemEventsBrokerClient!SebDeleteEvent` at `0x180078ab7`

## string_xrefs

- `0x180078a45`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\scheduledtilemanager.cpp`
- `0x180078b55`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\scheduledtilemanager.cpp`
- `0x180078bcd`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\scheduledtilemanager.cpp`
- `0x180078c1a`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\scheduledtilemanager.cpp`
- `0x180078c73`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\scheduledtilemanager.cpp`

## pseudocode

```c
__int64 __fastcall ScheduledTileManager::SetupTimer(
        ScheduledTileManager *this,
        union _ULARGE_INTEGER a2,
        struct ScheduledTileManager::_PERSISTED_TILE *a3,
        struct _GUID *a4)
{
  DWORD HighPart; // edi
  DWORD LowPart; // ebx
  int v8; // eax
  int v9; // edi
  unsigned __int64 v10; // r15
  int v11; // eax
  SebEvents *v12; // rcx
  unsigned int v13; // ebx
  int DisplayOnEvent; // eax
  NTSTATUS v15; // eax
  _QWORD *v16; // rcx
  __int64 v17; // rdx
  signed int v18; // eax
  NTSTATUS v19; // eax
  signed int v21; // eax
  signed int LastError; // eax
  _QWORD *v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // rdx
  __int64 v26; // r8
  int v27; // [rsp+20h] [rbp-E0h]
  FILETIME FileTime; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v29; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v30; // [rsp+60h] [rbp-A0h] BYREF
  __m256i v31; // [rsp+70h] [rbp-90h] BYREF
  __int128 v32; // [rsp+90h] [rbp-70h]
  __int128 v33; // [rsp+A0h] [rbp-60h]
  __int128 v34; // [rsp+B0h] [rbp-50h]
  __int128 v35; // [rsp+C0h] [rbp-40h]
  __int128 v36; // [rsp+D0h] [rbp-30h]
  __int128 v37; // [rsp+E0h] [rbp-20h]
  __int128 v38; // [rsp+F0h] [rbp-10h]
  __int128 v39; // [rsp+100h] [rbp+0h]
  __int128 v40; // [rsp+110h] [rbp+10h]
  __int128 v41; // [rsp+120h] [rbp+20h]
  __int128 v42; // [rsp+130h] [rbp+30h]
  __int128 v43; // [rsp+140h] [rbp+40h]
  __int128 v44; // [rsp+150h] [rbp+50h]
  __int64 v45; // [rsp+160h] [rbp+60h]
  __m256i v46; // [rsp+170h] [rbp+70h] BYREF
  __int128 v47; // [rsp+190h] [rbp+90h]
  __int128 v48; // [rsp+1A0h] [rbp+A0h]
  __int128 v49; // [rsp+1B0h] [rbp+B0h]
  __int128 v50; // [rsp+1C0h] [rbp+C0h]
  __int128 v51; // [rsp+1D0h] [rbp+D0h]
  __int128 v52; // [rsp+1E0h] [rbp+E0h]
  __int128 v53; // [rsp+1F0h] [rbp+F0h]
  __int128 v54; // [rsp+200h] [rbp+100h]
  __int128 v55; // [rsp+210h] [rbp+110h]
  __int128 v56; // [rsp+220h] [rbp+120h]
  __int128 v57; // [rsp+230h] [rbp+130h]
  __int128 v58; // [rsp+240h] [rbp+140h]
  __int128 v59; // [rsp+250h] [rbp+150h]
  __int64 v60; // [rsp+260h] [rbp+160h]
  struct _SYSTEMTIME SystemTime; // [rsp+270h] [rbp+170h] BYREF
  struct _GUID v62; // [rsp+280h] [rbp+180h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+1D8h]

  HighPart = a2.HighPart;
  LowPart = a2.LowPart;
  v31.m256i_i32[1] = 0;
  SystemTime = 0;
  v62 = 0;
  memset_0(&v31.m256i_u64[1], 0, 0xF0u);
  FileTime.dwLowDateTime = LowPart;
  FileTime.dwHighDateTime = HighPart;
  v29 = 0;
  if ( !FileTimeToSystemTime(&FileTime, &SystemTime) )
  {
    LastError = GetLastError();
    v13 = LastError;
    if ( LastError > 0 )
      v13 = (unsigned __int16)LastError | 0x80070000;
    if ( (v13 & 0x80000000) == 0 )
      v13 = -2147467259;
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x512,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\scheduledtilemanager.cpp",
      (const char *)v13,
      v27);
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      return v13;
    v24 = 53;
LABEL_35:
    WPP_SF_d(v23[2], v24, WPP_91456f608371345bae03279a5fee97df_Traceguids, v13);
    return v13;
  }
  v31.m256i_i64[3] = 0x100000000LL;
  v8 = *((_DWORD *)a3 + 20);
  *(struct _SYSTEMTIME *)&v31.m256i_u64[1] = SystemTime;
  LODWORD(v32) = 525600;
  v9 = 1;
  BYTE5(v33) = 0;
  v31.m256i_i32[0] = 1;
  v10 = ((unsigned __int64)a3 + 344) & -(__int64)(v8 != 0);
  v46 = v31;
  v47 = v32;
  v60 = v45;
  v49 = v34;
  v48 = v33;
  v51 = v36;
  v50 = v35;
  v53 = v38;
  v52 = v37;
  v55 = v40;
  v54 = v39;
  v57 = v42;
  v56 = v41;
  v59 = v44;
  v58 = v43;
  v11 = TbCreateEvent(v10, &v46, (char *)a3 + 4);
  v13 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x526,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\scheduledtilemanager.cpp",
      (const char *)(unsigned int)v11,
      v27);
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      return v13;
    v24 = 54;
    goto LABEL_35;
  }
  DisplayOnEvent = SebEvents::GetDisplayOnEvent(v12, (struct _GUID *)((char *)a3 + 36));
  v13 = DisplayOnEvent;
  if ( DisplayOnEvent < 0 )
  {
    v9 = 0;
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x52E,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\scheduledtilemanager.cpp",
      (const char *)(unsigned int)DisplayOnEvent,
      v27);
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    {
      v17 = 55;
      goto LABEL_10;
    }
LABEL_11:
    v30 = *(_OWORD *)((char *)a3 + 4);
    TbDeleteEvent(v10, &v30);
    if ( v9 )
    {
      v30 = *(_OWORD *)((char *)a3 + 36);
      SebDeleteEvent(&v30, 0);
    }
    return v13;
  }
  *(_QWORD *)&v29 = (char *)a3 + 36;
  BYTE8(v29) = 1;
  v15 = BiPtAssociateActivationProxy((char *)a3 + 20, (char *)a3 + 72, (char *)a3 + 4, &v29);
  if ( v15 < 0 )
  {
    v18 = RtlNtStatusToDosError(v15);
    v13 = v18;
    if ( v18 > 0 )
      v13 = (unsigned __int16)v18 | 0x80070000;
  }
  else
  {
    v13 = 0;
  }
  if ( (v13 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x540,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\scheduledtilemanager.cpp",
      (const char *)v13,
      1);
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    {
      v17 = 56;
LABEL_10:
      WPP_SF_d(v16[2], v17, WPP_91456f608371345bae03279a5fee97df_Traceguids, v13);
      goto LABEL_11;
    }
    goto LABEL_11;
  }
  v19 = BiPtCreateEventForPackageName(&v62, qword_180127CB0, 0, 0);
  if ( v19 < 0 )
  {
    v21 = RtlNtStatusToDosError(v19);
    v13 = v21;
    if ( v21 > 0 )
      v13 = (unsigned __int16)v21 | 0x80070000;
  }
  else
  {
    v13 = 0;
  }
  if ( (v13 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x54E,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\scheduledtilemanager.cpp",
      (const char *)v13,
      (int)a3);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, WPP_91456f608371345bae03279a5fee97df_Traceguids, v13);
    LOBYTE(v26) = 1;
    LOBYTE(v25) = 1;
    BiPtDisassociateWorkItemEx((char *)a3 + 20, v25, v26);
  }
  else
  {
    *a4 = v62;
  }
  return v13;
}

```

## disassembly

```asm
0x18007883c  mov     [rsp-8+arg_0], rbx
0x180078841  push    rbp
0x180078842  push    rsi
0x180078843  push    rdi
0x180078844  push    r12
0x180078846  push    r13
0x180078848  push    r14
0x18007884a  push    r15
0x18007884c  lea     rbp, [rsp-1A0h]
0x180078854  sub     rsp, 2A0h
0x18007885b  mov     rax, cs:__security_cookie
0x180078862  xor     rax, rsp
0x180078865  mov     [rbp+1D0h+var_40], rax
0x18007886c  mov     rdi, rdx
0x18007886f  lea     rcx, [rsp+2D0h+var_260+8]; void *
0x180078874  mov     r13, r8
0x180078877  shr     rdi, 20h
0x18007887b  mov     rbx, rdx
0x18007887e  xorps   xmm0, xmm0
0x180078881  xorps   xmm1, xmm1
0x180078884  xor     eax, eax
0x180078886  xor     edx, edx; Val
0x180078888  mov     dword ptr [rsp+2D0h+var_260+4], eax
0x18007888c  mov     r8d, 0F0h; Size
0x180078892  mov     r12, r9
0x180078895  movups  xmmword ptr [rbp+1D0h+SystemTime.wYear], xmm0
0x18007889c  movups  [rbp+1D0h+var_50], xmm1
0x1800788a3  call    memset_0
0x1800788a8  xorps   xmm0, xmm0
0x1800788ab  mov     [rsp+2D0h+FileTime.dwLowDateTime], ebx
0x1800788af  lea     rdx, [rbp+1D0h+SystemTime]; lpSystemTime
0x1800788b6  mov     [rsp+2D0h+FileTime.dwHighDateTime], edi
0x1800788ba  lea     rcx, [rsp+2D0h+FileTime]; lpFileTime
0x1800788bf  movups  [rsp+2D0h+var_288], xmm0
0x1800788c4  call    cs:__imp_FileTimeToSystemTime
0x1800788ca  test    eax, eax
0x1800788cc  jz      loc_180078BB1
0x1800788d2  movups  xmm0, xmmword ptr [rbp+1D0h+SystemTime.wYear]
0x1800788d9  lea     rsi, [r13+4]
0x1800788dd  mov     [rbp+1D0h+var_248], 0
0x1800788e4  mov     eax, [rsi+4Ch]
0x1800788e7  lea     rcx, [rsi+154h]
0x1800788ee  movdqu  [rsp+2D0h+var_260+8], xmm0
0x1800788f4  neg     eax
0x1800788f6  mov     dword ptr [rbp+1D0h+var_240], 80520h
0x1800788fd  mov     rax, [rbp+1D0h+var_170]
0x180078901  lea     rdx, [rbp+1D0h+var_160]
0x180078905  mov     edi, 1
0x18007890a  mov     [rbp+1D0h+var_22B], 0
0x18007890e  sbb     r15, r15
0x180078911  mov     dword ptr [rsp+2D0h+var_260], edi
0x180078915  movaps  xmm0, [rsp+2D0h+var_260]
0x18007891a  and     r15, rcx
0x18007891d  movups  [rbp+1D0h+var_160], xmm0
0x180078921  mov     r8, rsi
0x180078924  mov     [rbp+1D0h+var_244], edi
0x180078927  movaps  xmm0, [rbp+1D0h+var_240]
0x18007892b  mov     rcx, r15
0x18007892e  movaps  xmm1, xmmword ptr [rbp-80h]
0x180078932  movups  [rbp+1D0h+var_140], xmm0
0x180078939  mov     [rbp+1D0h+var_70], rax
0x180078940  movaps  xmm0, [rbp+1D0h+var_220]
0x180078944  movups  [rbp+1D0h+var_150], xmm1
0x18007894b  movaps  xmm1, xmmword ptr [rbp-60h]
0x18007894f  movups  [rbp+1D0h+var_120], xmm0
0x180078956  movaps  xmm0, [rbp+1D0h+var_200]
0x18007895a  movups  [rbp+1D0h+var_130], xmm1
0x180078961  movaps  xmm1, [rbp+1D0h+var_210]
0x180078965  movups  [rbp+1D0h+var_100], xmm0
0x18007896c  movaps  xmm0, [rbp+1D0h+var_1E0]
0x180078970  movups  [rbp+1D0h+var_110], xmm1
0x180078977  movaps  xmm1, [rbp+1D0h+var_1F0]
0x18007897b  movups  [rbp+1D0h+var_E0], xmm0
0x180078982  movaps  xmm0, [rbp+1D0h+var_1C0]
0x180078986  movups  [rbp+1D0h+var_F0], xmm1
0x18007898d  movaps  xmm1, [rbp+1D0h+var_1D0]
0x180078991  movups  [rbp+1D0h+var_C0], xmm0
0x180078998  movaps  xmm0, [rbp+1D0h+var_1A0]
0x18007899c  movups  [rbp+1D0h+var_D0], xmm1
0x1800789a3  movaps  xmm1, [rbp+1D0h+var_1B0]
0x1800789a7  movups  [rbp+1D0h+var_A0], xmm0
0x1800789ae  movaps  xmm0, [rbp+1D0h+var_180]
0x1800789b2  movups  [rbp+1D0h+var_B0], xmm1
0x1800789b9  movaps  xmm1, [rbp+1D0h+var_190]
0x1800789bd  movups  [rbp+1D0h+var_80], xmm0
0x1800789c4  movups  [rbp+1D0h+var_90], xmm1
0x1800789cb  call    cs:__imp_TbCreateEvent
0x1800789d1  mov     ebx, eax
0x1800789d3  test    eax, eax
0x1800789d5  js      loc_180078C13
0x1800789db  lea     r14, [rsi+20h]
0x1800789df  mov     rdx, r14; struct _GUID *
0x1800789e2  call    ?GetDisplayOnEvent@SebEvents@@QEAAJPEAU_GUID@@@Z; SebEvents::GetDisplayOnEvent(_GUID *)
0x1800789e7  mov     ebx, eax
0x1800789e9  test    eax, eax
0x1800789eb  js      loc_180078B4E
0x1800789f1  mov     [rsp+2D0h+var_2A0], 0
0x1800789fa  lea     rdx, [rsi+44h]
0x1800789fe  mov     [rsp+2D0h+var_2A8], 0
0x180078a06  lea     rcx, [rsi+10h]
0x180078a0a  lea     r9, [rsp+2D0h+var_288]
0x180078a0f  mov     [rsp+2D0h+var_2B0], edi; int
0x180078a13  mov     r8, rsi
0x180078a16  mov     qword ptr [rsp+2D0h+var_288], r14
0x180078a1b  mov     byte ptr [rsp+2D0h+var_288+8], dil
0x180078a20  call    cs:__imp_BiPtAssociateActivationProxy
0x180078a26  mov     r14d, 80070000h
0x180078a2c  test    eax, eax
0x180078a2e  js      loc_180078ABF
0x180078a34  xor     ebx, ebx
0x180078a36  test    ebx, ebx
0x180078a38  jns     loc_180078ADC
0x180078a3e  mov     rcx, [rbp+1D8h]; this
0x180078a45  lea     r8, aOnecoreuapBase_39; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180078a4c  mov     r9d, ebx; char *
0x180078a4f  mov     edx, 540h; void *
0x180078a54  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180078a59  mov     rcx, cs:WPP_GLOBAL_Control
0x180078a60  lea     rax, WPP_GLOBAL_Control
0x180078a67  cmp     rcx, rax
0x180078a6a  jz      short loc_180078A8A
0x180078a6c  test    byte ptr [rcx+1Ch], 80h
0x180078a70  jz      short loc_180078A8A
0x180078a72  mov     edx, 38h ; '8'
0x180078a77  mov     rcx, [rcx+10h]
0x180078a7b  lea     r8, WPP_91456f608371345bae03279a5fee97df_Traceguids
0x180078a82  mov     r9d, ebx
0x180078a85  call    WPP_SF_d
0x180078a8a  movups  xmm0, xmmword ptr [rsi]
0x180078a8d  lea     rdx, [rsp+2D0h+var_270]
0x180078a92  mov     rcx, r15
0x180078a95  movdqu  [rsp+2D0h+var_270], xmm0
0x180078a9b  call    cs:__imp_TbDeleteEvent
0x180078aa1  test    edi, edi
0x180078aa3  jz      short loc_180078B22
0x180078aa5  movups  xmm0, xmmword ptr [r13+24h]
0x180078aaa  xor     edx, edx
0x180078aac  lea     rcx, [rsp+2D0h+var_270]
0x180078ab1  movdqu  [rsp+2D0h+var_270], xmm0
0x180078ab7  call    cs:__imp_SebDeleteEvent
0x180078abd  jmp     short loc_180078B22
0x180078abf  mov     ecx, eax; Status
0x180078ac1  call    cs:__imp_RtlNtStatusToDosError
0x180078ac7  mov     ebx, eax
0x180078ac9  test    eax, eax
0x180078acb  jle     loc_180078A36
0x180078ad1  movzx   ebx, ax
0x180078ad4  or      ebx, r14d
0x180078ad7  jmp     loc_180078A36
0x180078adc  mov     [rsp+2D0h+var_2A8], 1710h
0x180078ae4  lea     rdx, qword_180127CB0
0x180078aeb  xor     r9d, r9d
0x180078aee  mov     qword ptr [rsp+2D0h+var_2B0], r13; int
0x180078af3  xor     r8d, r8d
0x180078af6  lea     rcx, [rbp+1D0h+var_50]
0x180078afd  call    cs:__imp_BiPtCreateEventForPackageName
0x180078b03  test    eax, eax
0x180078b05  js      loc_180078B94
0x180078b0b  xor     ebx, ebx
0x180078b0d  test    ebx, ebx
0x180078b0f  js      loc_180078C6C
0x180078b15  movups  xmm0, [rbp+1D0h+var_50]
0x180078b1c  movdqu  xmmword ptr [r12], xmm0
0x180078b22  mov     eax, ebx
0x180078b24  mov     rcx, [rbp+1D0h+var_40]
0x180078b2b  xor     rcx, rsp; StackCookie
0x180078b2e  call    __security_check_cookie
0x180078b33  mov     rbx, [rsp+2D0h+arg_0]
0x180078b3b  add     rsp, 2A0h
0x180078b42  pop     r15
0x180078b44  pop     r14
0x180078b46  pop     r13
0x180078b48  pop     r12
0x180078b4a  pop     rdi
0x180078b4b  pop     rsi
0x180078b4c  pop     rbp
0x180078b4d  retn
0x180078b4e  mov     rcx, [rbp+1D8h]; this
0x180078b55  lea     r8, aOnecoreuapBase_39; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180078b5c  xor     edi, edi
0x180078b5e  mov     r9d, ebx; char *
0x180078b61  mov     edx, 52Eh; void *
0x180078b66  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180078b6b  mov     rcx, cs:WPP_GLOBAL_Control
0x180078b72  lea     rax, WPP_GLOBAL_Control
0x180078b79  cmp     rcx, rax
0x180078b7c  jz      loc_180078A8A
0x180078b82  test    byte ptr [rcx+1Ch], 80h
0x180078b86  jz      loc_180078A8A
0x180078b8c  lea     edx, [rdi+37h]
0x180078b8f  jmp     loc_180078A77
0x180078b94  mov     ecx, eax; Status
0x180078b96  call    cs:__imp_RtlNtStatusToDosError
0x180078b9c  mov     ebx, eax
0x180078b9e  test    eax, eax
0x180078ba0  jle     loc_180078B0D
0x180078ba6  movzx   ebx, ax
0x180078ba9  or      ebx, r14d
0x180078bac  jmp     loc_180078B0D
0x180078bb1  call    cs:__imp_GetLastError
0x180078bb7  mov     ebx, eax
0x180078bb9  test    eax, eax
0x180078bbb  jle     short loc_180078BC6
0x180078bbd  movzx   ebx, ax
0x180078bc0  or      ebx, 80070000h
0x180078bc6  mov     rcx, [rbp+1D8h]; this
0x180078bcd  lea     r8, aOnecoreuapBase_39; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180078bd4  test    ebx, ebx
0x180078bd6  mov     eax, 80004005h
0x180078bdb  mov     edx, 512h; void *
0x180078be0  cmovns  ebx, eax
0x180078be3  mov     r9d, ebx; char *
0x180078be6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180078beb  mov     rcx, cs:WPP_GLOBAL_Control
0x180078bf2  lea     rax, WPP_GLOBAL_Control
0x180078bf9  cmp     rcx, rax
0x180078bfc  jz      loc_180078B22
0x180078c02  test    byte ptr [rcx+1Ch], 80h
0x180078c06  jz      loc_180078B22
0x180078c0c  mov     edx, 35h ; '5'
0x180078c11  jmp     short loc_180078C54
0x180078c13  mov     rcx, [rbp+1D8h]; this
0x180078c1a  lea     r8, aOnecoreuapBase_39; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180078c21  mov     r9d, ebx; char *
0x180078c24  mov     edx, 526h; void *
0x180078c29  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180078c2e  mov     rcx, cs:WPP_GLOBAL_Control
0x180078c35  lea     rax, WPP_GLOBAL_Control
0x180078c3c  cmp     rcx, rax
0x180078c3f  jz      loc_180078B22
0x180078c45  test    byte ptr [rcx+1Ch], 80h
0x180078c49  jz      loc_180078B22
0x180078c4f  mov     edx, 36h ; '6'
0x180078c54  mov     rcx, [rcx+10h]
0x180078c58  lea     r8, WPP_91456f608371345bae03279a5fee97df_Traceguids
0x180078c5f  mov     r9d, ebx
0x180078c62  call    WPP_SF_d
0x180078c67  jmp     loc_180078B22
0x180078c6c  mov     rcx, [rbp+1D8h]; this
0x180078c73  lea     r8, aOnecoreuapBase_39; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180078c7a  mov     r9d, ebx; char *
0x180078c7d  mov     edx, 54Eh; void *
0x180078c82  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180078c87  mov     rcx, cs:WPP_GLOBAL_Control
0x180078c8e  lea     rax, WPP_GLOBAL_Control
0x180078c95  cmp     rcx, rax
0x180078c98  jz      short loc_180078CB8
0x180078c9a  test    byte ptr [rcx+1Ch], 80h
0x180078c9e  jz      short loc_180078CB8
0x180078ca0  mov     rcx, [rcx+10h]
0x180078ca4  lea     r8, WPP_91456f608371345bae03279a5fee97df_Traceguids
0x180078cab  mov     edx, 39h ; '9'
0x180078cb0  mov     r9d, ebx
0x180078cb3  call    WPP_SF_d
0x180078cb8  lea     rcx, [rsi+10h]
0x180078cbc  mov     r8b, dil
0x180078cbf  mov     dl, dil
0x180078cc2  call    cs:__imp_BiPtDisassociateWorkItemEx
0x180078cc8  jmp     loc_180078B22
```
