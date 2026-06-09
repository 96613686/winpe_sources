# CTieringEngineService::Run(int)

- ea: `0x140003e38`
- end: `0x140004338`
- name: `?Run@CTieringEngineService@@QEAAJH@Z`
- size: `1280`
- prototype: `__int64 __fastcall(CTieringEngineService *this)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x140004440`

## callees

- `0x140001a00`
- `0x140001a18`
- `0x140002db0`
- `0x1400038c0`
- `0x140003e38`
- `0x1400045d0`
- `0x1400049d8`
- `0x140004a40`
- `0x140004a68`
- `0x140004aa8`
- `0x140004fa0`
- `0x140005504`
- `0x140006720`
- `0x140008c04`
- `0x14003fbb0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400040eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004110`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004145`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400040eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004110`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004145`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x1400041bb`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x1400041bb`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140004186`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140004274`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140004186`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140004274`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140003e6f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14000413a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140003e6f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14000413a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140004222`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140004222`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1400041dc`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1400041dc`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1400040c1`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1400040c1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004122`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004122`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x140003f06`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x140003f06`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x140003f25`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x140003f25`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x140003fb0`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x140003fb0`

## string_xrefs

- `0x140003fc3`: `TieringEngineService`

## pseudocode

```c
__int64 __fastcall CTieringEngineService::Run(CTieringEngineService *this)
{
  HANDLE EventW; // rax
  unsigned int v4; // eax
  RTL_SRWLOCK *v5; // rax
  __int64 v6; // rbx
  __int64 v7; // rax
  const wchar_t *v8; // rcx
  WCHAR *v9; // rdx
  wchar_t v10; // r8
  WCHAR *v11; // rcx
  int v12; // eax
  unsigned int v13; // ebx
  HANDLE Thread; // rax
  DWORD LastError; // eax
  DWORD v16; // eax
  HANDLE v17; // rax
  DWORD v18; // edx
  signed int v19; // eax
  int v20; // ebx
  struct ATL::_ATL_OBJMAP_ENTRY30 **v21; // rdi
  __int64 *v22; // rax
  DWORD v23; // ecx
  CTieringEngineLib *v24; // rdi
  CTieringEngineLib *v25; // rcx
  GUID ProviderId; // [rsp+30h] [rbp-108h] BYREF
  WCHAR Buffer[104]; // [rsp+40h] [rbp-F8h] BYREF

  EventW = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)this + 85) = EventW;
  if ( !EventW )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_ef66010c4da23316be47f4e1f0858c5c_Traceguids);
    }
    return 2147942414LL;
  }
  ProviderId = (GUID)*((_OWORD *)off_14004C0A0 - 1);
  if ( RegHandle )
    __fastfail(5u);
  xmmword_14004C0C0 = 0;
  if ( !EventRegister(&ProviderId, tlgEnableCallback, &dword_14004C098, &RegHandle) )
    EventSetInformation(RegHandle, 2, off_14004C0A0, (unsigned __int16)*off_14004C0A0);
  v4 = McGenEventRegister_EventRegister();
  *((_QWORD *)this + 86) = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_ef66010c4da23316be47f4e1f0858c5c_Traceguids, v4);
  }
  v5 = (RTL_SRWLOCK *)operator new(0x1A8u);
  if ( v5 )
  {
    TieringEngineLibInstance = CTieringEngineLib::CTieringEngineLib(v5);
    if ( TieringEngineLibInstance )
    {
      v6 = 100;
      if ( !LoadStringW(g_hInstance, 0x66u, Buffer, 100) )
      {
        v7 = 2147483646;
        v8 = L"TieringEngineService";
        v9 = Buffer;
        do
        {
          if ( !v7 )
            break;
          v10 = *v8;
          if ( !*v8 )
            break;
          ++v8;
          *v9++ = v10;
          --v7;
          --v6;
        }
        while ( v6 );
        v11 = v9 - 1;
        if ( v6 )
          v11 = v9;
        *v11 = 0;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        {
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            14,
            WPP_ef66010c4da23316be47f4e1f0858c5c_Traceguids,
            200,
            v6 == 0 ? 0x8007007A : 0);
        }
      }
      v12 = CTieringEngineLib::Initialize(
              (CTieringEngineLib *)TieringEngineLibInstance,
              Buffer,
              L"Storage Tiers Optimization",
              L"\\Microsoft\\Windows\\Storage Tiers Management");
      v13 = v12;
      if ( v12 < 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            15,
            WPP_ef66010c4da23316be47f4e1f0858c5c_Traceguids,
            (unsigned int)v12);
        }
        return v13;
      }
      Thread = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)RunTieringEngineThread, this, 0, 0);
      *((_QWORD *)this + 86) = Thread;
      if ( !Thread )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          LastError = GetLastError();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_ef66010c4da23316be47f4e1f0858c5c_Traceguids, LastError);
        }
        v16 = GetLastError();
        return ATL::AtlHresultFromWin32(v16);
      }
      *((_DWORD *)this + 163) = GetCurrentThreadId();
      v17 = CreateEventW(0, 1, 0, 0);
      if ( v17 )
      {
        *((_QWORD *)this + 84) = v17;
        v20 = ATL::CAtlExeModuleT<CTieringEngineService>::PreMessageLoop(this, v18);
      }
      else
      {
        v19 = GetLastError();
        v20 = v19;
        if ( v19 > 0 )
          v20 = (unsigned __int16)v19 | 0x80070000;
      }
      if ( v20 )
      {
        if ( v20 < 0 )
        {
LABEL_57:
          v24 = (CTieringEngineLib *)TieringEngineLibInstance;
          if ( TieringEngineLibInstance )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_ef66010c4da23316be47f4e1f0858c5c_Traceguids);
            }
            SetEvent(*((HANDLE *)this + 85));
            CTieringEngineLib::SignalShutdownAndWait(v25);
            v24 = (CTieringEngineLib *)TieringEngineLibInstance;
          }
          if ( *((_QWORD *)this + 86) )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_ef66010c4da23316be47f4e1f0858c5c_Traceguids);
            }
            WaitForSingleObject(*((HANDLE *)this + 86), 0xFFFFFFFF);
            v24 = (CTieringEngineLib *)TieringEngineLibInstance;
          }
          if ( v24 )
          {
            CTieringEngineLib::~CTieringEngineLib(v24);
            operator delete(v24);
            TieringEngineLibInstance = 0;
          }
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_ef66010c4da23316be47f4e1f0858c5c_Traceguids);
          }
          return (unsigned int)v20;
        }
      }
      else
      {
        CMyAtlServiceModuleT<CTieringEngineService,102>::SetServiceStatus(this, 4);
        WaitForSingleObject(*((HANDLE *)this + 84), 0xFFFFFFFF);
      }
      v20 = 0;
      v21 = off_14004C200;
      v22 = off_14004C208;
      while ( v21 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)v22 && !v20 )
      {
        if ( *v21 )
        {
          v23 = *((_DWORD *)*v21 + 10);
          if ( v23 )
          {
            v20 = CoRevokeClassObject(v23);
            v22 = off_14004C208;
          }
          else
          {
            v20 = 0;
          }
        }
        ++v21;
      }
      if ( *((_BYTE *)this + 96) )
        Sleep(*((_DWORD *)this + 23));
      goto LABEL_57;
    }
  }
  else
  {
    TieringEngineLibInstance = 0;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_ef66010c4da23316be47f4e1f0858c5c_Traceguids);
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x140003e38  mov     [rsp+arg_8], rbx
0x140003e3d  mov     [rsp+arg_10], rsi
0x140003e42  push    rdi
0x140003e43  push    r14
0x140003e45  push    r15
0x140003e47  sub     rsp, 120h
0x140003e4e  mov     rax, cs:__security_cookie
0x140003e55  xor     rax, rsp
0x140003e58  mov     [rsp+138h+var_28], rax
0x140003e60  mov     rsi, rcx
0x140003e63  xor     r9d, r9d; lpName
0x140003e66  xor     r8d, r8d; bInitialState
0x140003e69  lea     edx, [r9+1]; bManualReset
0x140003e6d  xor     ecx, ecx; lpEventAttributes
0x140003e6f  call    cs:__imp_CreateEventW
0x140003e75  mov     [rsi+2A8h], rax
0x140003e7c  xor     r15d, r15d
0x140003e7f  test    rax, rax
0x140003e82  jnz     short loc_140003EC0
0x140003e84  lea     r14, WPP_GLOBAL_Control
0x140003e8b  mov     rcx, cs:WPP_GLOBAL_Control
0x140003e92  cmp     rcx, r14
0x140003e95  jz      short loc_140003EB6
0x140003e97  test    byte ptr [rcx+1Ch], 1
0x140003e9b  jz      short loc_140003EB6
0x140003e9d  cmp     byte ptr [rcx+19h], 2
0x140003ea1  jb      short loc_140003EB6
0x140003ea3  lea     edx, [rax+0Bh]
0x140003ea6  lea     r8, WPP_ef66010c4da23316be47f4e1f0858c5c_Traceguids
0x140003ead  mov     rcx, [rcx+10h]
0x140003eb1  call    WPP_SF_
0x140003eb6  mov     eax, 8007000Eh
0x140003ebb  jmp     loc_14000430E
0x140003ec0  mov     rax, cs:off_14004C0A0
0x140003ec7  movups  xmm0, xmmword ptr [rax-10h]
0x140003ecb  movdqu  xmmword ptr [rsp+138h+ProviderId.Data1], xmm0
0x140003ed1  cmp     cs:RegHandle, r15
0x140003ed8  jz      short loc_140003EE1
0x140003eda  mov     ecx, 5
0x140003edf  int     29h; Win8: RtlFailFast(ecx)
0x140003ee1  xorps   xmm0, xmm0
0x140003ee4  movdqu  cs:xmmword_14004C0C0, xmm0
0x140003eec  lea     r9, RegHandle; RegHandle
0x140003ef3  lea     r8, dword_14004C098; CallbackContext
0x140003efa  lea     rdx, _tlgEnableCallback; EnableCallback
0x140003f01  lea     rcx, [rsp+138h+ProviderId]; ProviderId
0x140003f06  call    cs:__imp_EventRegister
0x140003f0c  test    eax, eax
0x140003f0e  jnz     short loc_140003F2B
0x140003f10  mov     r8, cs:off_14004C0A0
0x140003f17  movzx   r9d, word ptr [r8]
0x140003f1b  lea     edx, [rax+2]
0x140003f1e  mov     rcx, cs:RegHandle
0x140003f25  call    cs:__imp_EventSetInformation
0x140003f2b  call    McGenEventRegister_EventRegister
0x140003f30  mov     [rsi+2B0h], r15
0x140003f37  lea     r14, WPP_GLOBAL_Control
0x140003f3e  mov     rcx, cs:WPP_GLOBAL_Control
0x140003f45  cmp     rcx, r14
0x140003f48  jz      short loc_140003F6E
0x140003f4a  test    byte ptr [rcx+1Ch], 1
0x140003f4e  jz      short loc_140003F6E
0x140003f50  cmp     byte ptr [rcx+19h], 4
0x140003f54  jb      short loc_140003F6E
0x140003f56  mov     edx, 0Ch
0x140003f5b  mov     r9d, eax
0x140003f5e  lea     r8, WPP_ef66010c4da23316be47f4e1f0858c5c_Traceguids
0x140003f65  mov     rcx, [rcx+10h]
0x140003f69  call    WPP_SF_d
0x140003f6e  mov     ecx, 1A8h; Size
0x140003f73  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140003f78  test    rax, rax
0x140003f7b  jz      loc_1400042CE
0x140003f81  mov     rcx, rax; SRWLock
0x140003f84  call    ??0CTieringEngineLib@@QEAA@XZ; CTieringEngineLib::CTieringEngineLib(void)
0x140003f89  mov     cs:?TieringEngineLibInstance@@3PEAVCTieringEngineLib@@EA, rax; CTieringEngineLib * TieringEngineLibInstance
0x140003f90  test    rax, rax
0x140003f93  jz      loc_1400042D5
0x140003f99  mov     ebx, 64h ; 'd'
0x140003f9e  mov     r9d, ebx; cchBufferMax
0x140003fa1  lea     r8, [rsp+138h+Buffer]; lpBuffer
0x140003fa6  lea     edx, [rbx+2]; uID
0x140003fa9  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x140003fb0  call    cs:__imp_LoadStringW
0x140003fb6  test    eax, eax
0x140003fb8  jnz     loc_14000404D
0x140003fbe  mov     eax, 7FFFFFFEh
0x140003fc3  lea     rcx, aTieringengines; "TieringEngineService"
0x140003fca  lea     rdx, [rsp+138h+Buffer]
0x140003fcf  test    rax, rax
0x140003fd2  jz      short loc_140003FF3
0x140003fd4  movzx   r8d, word ptr [rcx]
0x140003fd8  test    r8w, r8w
0x140003fdc  jz      short loc_140003FF3
0x140003fde  add     rcx, 2
0x140003fe2  mov     [rdx], r8w
0x140003fe6  add     rdx, 2
0x140003fea  dec     rax
0x140003fed  sub     rbx, 1
0x140003ff1  jnz     short loc_140003FCF
0x140003ff3  mov     rax, rbx
0x140003ff6  neg     rax
0x140003ff9  sbb     r8d, r8d
0x140003ffc  not     r8d
0x140003fff  and     r8d, 8007007Ah
0x140004006  lea     rcx, [rdx-2]
0x14000400a  test    rbx, rbx
0x14000400d  cmovnz  rcx, rdx
0x140004011  mov     [rcx], r15w
0x140004015  mov     rcx, cs:WPP_GLOBAL_Control
0x14000401c  cmp     rcx, r14
0x14000401f  jz      short loc_14000404D
0x140004021  test    byte ptr [rcx+1Ch], 1
0x140004025  jz      short loc_14000404D
0x140004027  cmp     byte ptr [rcx+19h], 3
0x14000402b  jb      short loc_14000404D
0x14000402d  mov     edx, 0Eh
0x140004032  mov     [rsp+138h+dwCreationFlags], r8d
0x140004037  mov     r9d, 0C8h
0x14000403d  lea     r8, WPP_ef66010c4da23316be47f4e1f0858c5c_Traceguids
0x140004044  mov     rcx, [rcx+10h]
0x140004048  call    WPP_SF_Dd
0x14000404d  lea     r9, aMicrosoftWindo; "\\Microsoft\\Windows\\Storage Tiers Man"...
0x140004054  lea     r8, aStorageTiersOp; "Storage Tiers Optimization"
0x14000405b  lea     rdx, [rsp+138h+Buffer]; unsigned __int16 *
0x140004060  mov     rcx, cs:?TieringEngineLibInstance@@3PEAVCTieringEngineLib@@EA; this
0x140004067  call    ?Initialize@CTieringEngineLib@@QEAAJPEBG00@Z; CTieringEngineLib::Initialize(ushort const *,ushort const *,ushort const *)
0x14000406c  mov     ebx, eax
0x14000406e  test    eax, eax
0x140004070  jns     short loc_1400040A9
0x140004072  mov     rcx, cs:WPP_GLOBAL_Control
0x140004079  cmp     rcx, r14
0x14000407c  jz      short loc_1400040A2
0x14000407e  test    byte ptr [rcx+1Ch], 1
0x140004082  jz      short loc_1400040A2
0x140004084  cmp     byte ptr [rcx+19h], 2
0x140004088  jb      short loc_1400040A2
0x14000408a  mov     edx, 0Fh
0x14000408f  mov     r9d, eax
0x140004092  lea     r8, WPP_ef66010c4da23316be47f4e1f0858c5c_Traceguids
0x140004099  mov     rcx, [rcx+10h]
0x14000409d  call    WPP_SF_d
0x1400040a2  mov     eax, ebx
0x1400040a4  jmp     loc_14000430E
0x1400040a9  mov     [rsp+138h+lpThreadId], r15; lpThreadId
0x1400040ae  mov     [rsp+138h+dwCreationFlags], r15d; dwCreationFlags
0x1400040b3  mov     r9, rsi; lpParameter
0x1400040b6  lea     r8, ?RunTieringEngineThread@@YAKPEAX@Z; lpStartAddress
0x1400040bd  xor     edx, edx; dwStackSize
0x1400040bf  xor     ecx, ecx; lpThreadAttributes
0x1400040c1  call    cs:__imp_CreateThread
0x1400040c7  mov     [rsi+2B0h], rax
0x1400040ce  test    rax, rax
0x1400040d1  jnz     short loc_140004122
0x1400040d3  mov     rax, cs:WPP_GLOBAL_Control
0x1400040da  cmp     rax, r14
0x1400040dd  jz      short loc_140004110
0x1400040df  test    byte ptr [rax+1Ch], 1
0x1400040e3  jz      short loc_140004110
0x1400040e5  cmp     byte ptr [rax+19h], 2
0x1400040e9  jb      short loc_140004110
0x1400040eb  call    cs:__imp_GetLastError
0x1400040f1  mov     edx, 10h
0x1400040f6  mov     r9d, eax
0x1400040f9  lea     r8, WPP_ef66010c4da23316be47f4e1f0858c5c_Traceguids
0x140004100  mov     rcx, cs:WPP_GLOBAL_Control
0x140004107  mov     rcx, [rcx+10h]
0x14000410b  call    WPP_SF_d
0x140004110  call    cs:__imp_GetLastError
0x140004116  mov     ecx, eax; unsigned int
0x140004118  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x14000411d  jmp     loc_14000430E
0x140004122  call    cs:__imp_GetCurrentThreadId
0x140004128  mov     [rsi+28Ch], eax
0x14000412e  xor     r9d, r9d; lpName
0x140004131  xor     r8d, r8d; bInitialState
0x140004134  lea     edx, [r9+1]; bManualReset
0x140004138  xor     ecx, ecx; lpEventAttributes
0x14000413a  call    cs:__imp_CreateEventW
0x140004140  test    rax, rax
0x140004143  jnz     short loc_14000415C
0x140004145  call    cs:__imp_GetLastError
0x14000414b  mov     ebx, eax
0x14000414d  test    eax, eax
0x14000414f  jle     short loc_14000416D
0x140004151  movzx   ebx, ax
0x140004154  or      ebx, 80070000h
0x14000415a  jmp     short loc_14000416D
0x14000415c  mov     [rsi+2A0h], rax
0x140004163  mov     rcx, rsi; lpParameter
0x140004166  call    ?PreMessageLoop@?$CAtlExeModuleT@VCTieringEngineService@@@ATL@@QEAAJH@Z; ATL::CAtlExeModuleT<CTieringEngineService>::PreMessageLoop(int)
0x14000416b  mov     ebx, eax
0x14000416d  test    ebx, ebx
0x14000416f  jnz     short loc_14000418E
0x140004171  lea     edx, [rbx+4]
0x140004174  mov     rcx, rsi
0x140004177  call    ?SetServiceStatus@?$CMyAtlServiceModuleT@VCTieringEngineService@@$0GG@@@QEAAXK@Z; CMyAtlServiceModuleT<CTieringEngineService,102>::SetServiceStatus(ulong)
0x14000417c  or      edx, 0FFFFFFFFh; dwMilliseconds
0x14000417f  mov     rcx, [rsi+2A0h]; hHandle
0x140004186  call    cs:__imp_WaitForSingleObject
0x14000418c  jmp     short loc_140004190
0x14000418e  js      short loc_1400041E2
0x140004190  mov     ebx, r15d
0x140004193  mov     rdi, cs:off_14004C200
0x14000419a  mov     rax, cs:off_14004C208
0x1400041a1  jmp     short loc_1400041CE
0x1400041a3  test    ebx, ebx
0x1400041a5  jnz     short loc_1400041D3
0x1400041a7  mov     rcx, [rdi]
0x1400041aa  test    rcx, rcx
0x1400041ad  jz      short loc_1400041CA
0x1400041af  mov     ecx, [rcx+28h]; dwRegister
0x1400041b2  test    ecx, ecx
0x1400041b4  jnz     short loc_1400041BB
0x1400041b6  mov     ebx, r15d
0x1400041b9  jmp     short loc_1400041CA
0x1400041bb  call    cs:__imp_CoRevokeClassObject
0x1400041c1  mov     ebx, eax
0x1400041c3  mov     rax, cs:off_14004C208
0x1400041ca  add     rdi, 8
0x1400041ce  cmp     rdi, rax
0x1400041d1  jb      short loc_1400041A3
0x1400041d3  cmp     [rsi+60h], r15b
0x1400041d7  jz      short loc_1400041E2
0x1400041d9  mov     ecx, [rsi+5Ch]; dwMilliseconds
0x1400041dc  call    cs:__imp_Sleep
0x1400041e2  mov     rdi, cs:?TieringEngineLibInstance@@3PEAVCTieringEngineLib@@EA; CTieringEngineLib * TieringEngineLibInstance
0x1400041e9  test    rdi, rdi
0x1400041ec  jz      short loc_140004234
0x1400041ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1400041f5  cmp     rcx, r14
0x1400041f8  jz      short loc_14000421B
0x1400041fa  test    byte ptr [rcx+1Ch], 1
0x1400041fe  jz      short loc_14000421B
0x140004200  cmp     byte ptr [rcx+19h], 4
0x140004204  jb      short loc_14000421B
0x140004206  mov     edx, 11h
0x14000420b  lea     r8, WPP_ef66010c4da23316be47f4e1f0858c5c_Traceguids
0x140004212  mov     rcx, [rcx+10h]
0x140004216  call    WPP_SF_
0x14000421b  mov     rcx, [rsi+2A8h]; hEvent
0x140004222  call    cs:__imp_SetEvent
0x140004228  call    ?SignalShutdownAndWait@CTieringEngineLib@@QEAAXXZ; CTieringEngineLib::SignalShutdownAndWait(void)
0x14000422d  mov     rdi, cs:?TieringEngineLibInstance@@3PEAVCTieringEngineLib@@EA; CTieringEngineLib * TieringEngineLibInstance
0x140004234  cmp     [rsi+2B0h], r15
0x14000423b  jz      short loc_140004281
0x14000423d  mov     rcx, cs:WPP_GLOBAL_Control
0x140004244  cmp     rcx, r14
0x140004247  jz      short loc_14000426A
0x140004249  test    byte ptr [rcx+1Ch], 1
0x14000424d  jz      short loc_14000426A
0x14000424f  cmp     byte ptr [rcx+19h], 4
0x140004253  jb      short loc_14000426A
0x140004255  mov     edx, 12h
0x14000425a  lea     r8, WPP_ef66010c4da23316be47f4e1f0858c5c_Traceguids
0x140004261  mov     rcx, [rcx+10h]
0x140004265  call    WPP_SF_
0x14000426a  or      edx, 0FFFFFFFFh; dwMilliseconds
0x14000426d  mov     rcx, [rsi+2B0h]; hHandle
0x140004274  call    cs:__imp_WaitForSingleObject
0x14000427a  mov     rdi, cs:?TieringEngineLibInstance@@3PEAVCTieringEngineLib@@EA; CTieringEngineLib * TieringEngineLibInstance
0x140004281  test    rdi, rdi
0x140004284  jz      short loc_14000429D
0x140004286  mov     rcx, rdi; this
0x140004289  call    ??1CTieringEngineLib@@QEAA@XZ; CTieringEngineLib::~CTieringEngineLib(void)
0x14000428e  mov     rcx, rdi; Block
0x140004291  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140004296  mov     cs:?TieringEngineLibInstance@@3PEAVCTieringEngineLib@@EA, r15; CTieringEngineLib * TieringEngineLibInstance
0x14000429d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400042a4  cmp     rcx, r14
0x1400042a7  jz      short loc_1400042CA
0x1400042a9  test    byte ptr [rcx+1Ch], 1
0x1400042ad  jz      short loc_1400042CA
0x1400042af  cmp     byte ptr [rcx+19h], 4
0x1400042b3  jb      short loc_1400042CA
0x1400042b5  mov     edx, 13h
0x1400042ba  lea     r8, WPP_ef66010c4da23316be47f4e1f0858c5c_Traceguids
0x1400042c1  mov     rcx, [rcx+10h]
0x1400042c5  call    WPP_SF_
0x1400042ca  mov     eax, ebx
0x1400042cc  jmp     short loc_14000430E
0x1400042ce  mov     cs:?TieringEngineLibInstance@@3PEAVCTieringEngineLib@@EA, r15; CTieringEngineLib * TieringEngineLibInstance
0x1400042d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400042dc  cmp     rcx, r14
0x1400042df  jz      short loc_140004302
0x1400042e1  test    byte ptr [rcx+1Ch], 1
0x1400042e5  jz      short loc_140004302
0x1400042e7  cmp     byte ptr [rcx+19h], 2
0x1400042eb  jb      short loc_140004302
0x1400042ed  mov     edx, 0Dh
0x1400042f2  lea     r8, WPP_ef66010c4da23316be47f4e1f0858c5c_Traceguids
0x1400042f9  mov     rcx, [rcx+10h]
0x1400042fd  call    WPP_SF_
0x140004302  mov     eax, 8007000Eh
0x140004307  jmp     short loc_14000430E
0x140004309  mov     eax, 8007000Eh
0x14000430e  mov     rcx, [rsp+138h+var_28]
0x140004316  xor     rcx, rsp; StackCookie
0x140004319  call    __security_check_cookie
0x14000431e  lea     r11, [rsp+138h+var_18]
  ... truncated ...
```
