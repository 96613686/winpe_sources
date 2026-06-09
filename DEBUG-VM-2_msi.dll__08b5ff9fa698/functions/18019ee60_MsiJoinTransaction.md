# MsiJoinTransaction

- ea: `0x18019ee60`
- end: `0x18019f444`
- name: `MsiJoinTransaction`
- size: `1508`
- prototype: `UINT __stdcall(MSIHANDLE hTransactionHandle, DWORD dwTransactionAttributes, HANDLE *phChangeOfOwnerEvent)`
- caller_count: `0`
- callee_count: `17`
- tags: `file_ops, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x18001de18`
- `0x18001e9f8`
- `0x180022120`
- `0x1800255e0`
- `0x180025a18`
- `0x180061334`
- `0x1800620e4`
- `0x180066074`
- `0x1800e0bd0`
- `0x180126db8`
- `0x180143d44`
- `0x18017284c`
- `0x18019ee60`
- `0x1801cdbe0`
- `0x1802009c4`
- `0x18025ab80`
- `0x18025c010`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x18019f255`
- `KERNEL32!WaitForSingleObject` at `0x18019f255`
- `KERNEL32!OpenEventW` at `0x18019f082`
- `KERNEL32!OpenEventW` at `0x18019f11f`
- `KERNEL32!OpenEventW` at `0x18019f1ee`
- `KERNEL32!OpenEventW` at `0x18019f082`
- `KERNEL32!OpenEventW` at `0x18019f11f`
- `KERNEL32!OpenEventW` at `0x18019f1ee`
- `KERNEL32!CreateEventW` at `0x18019f266`
- `KERNEL32!CreateEventW` at `0x18019f27e`
- `KERNEL32!CreateEventW` at `0x18019f266`
- `KERNEL32!CreateEventW` at `0x18019f27e`
- `KERNEL32!CreateThread` at `0x18019f2d6`
- `KERNEL32!CreateThread` at `0x18019f2d6`

## string_xrefs

- `0x18019f0de`: `Error occurred in string function, unable to create end transaction event.`
- `0x18019f152`: `Error occured opening event: %s`
- `0x18019f39c`: `Error occured opening event: %s`
- `0x18019f1af`: `Error occurred in string function, unable to create ack event.`
- `0x18019f320`: `Error occurred creating cleanup EEUI on change of owner thread.`
- `0x18019eeaf`: `Entering MsiJoinTransaction. hTransactionHandle: %d, dwTransactionAttributes: %d`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
UINT __stdcall MsiJoinTransaction(
        MSIHANDLE hTransactionHandle,
        DWORD dwTransactionAttributes,
        HANDLE *phChangeOfOwnerEvent)
{
  const bool *v6; // r8
  int v7; // eax
  struct IMsiServer *MsiServer; // rax
  struct IMsiServer *v10; // rbx
  char v11; // al
  char v12; // r12
  CMsiAPIMessage *v13; // rcx
  UINT v14; // edi
  unsigned int v15; // edx
  _QWORD *v16; // rax
  void *v17; // rax
  void *v18; // rdi
  __int64 v19; // rcx
  HANDLE v20; // r14
  WCHAR *v21; // rax
  const unsigned __int16 *v22; // r9
  HANDLE EventW; // rdi
  HANDLE v24; // rsi
  _QWORD *v25; // rax
  void *v26; // rbx
  HANDLE Thread; // rax
  int v28; // ebx
  _BYTE v29[4]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v30; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned int v31; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v32; // [rsp+6Ch] [rbp-94h] BYREF
  _QWORD v33[2]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Name[264]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR v35[264]; // [rsp+290h] [rbp+190h] BYREF

  v6 = L"(NULL)";
  if ( g_dmDiagnosticMode )
    DebugString(
      9,
      0,
      0,
      L"Entering MsiJoinTransaction. hTransactionHandle: %d, dwTransactionAttributes: %d",
      (const unsigned __int16 *)hTransactionHandle,
      (const unsigned __int16 *)dwTransactionAttributes,
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      0,
      0);
  if ( !phChangeOfOwnerEvent || dwTransactionAttributes > 2 )
    return 87;
  v7 = ((__int64 (__fastcall *)(_QWORD, _QWORD, const bool *))OLE32::CoInitialize)(
         0,
         *(_QWORD *)&dwTransactionAttributes,
         v6);
  if ( (int)(v7 + 0x80000000) >= 0 && v7 != -2147417850 )
    return 1603;
  v29[0] = v7 >= 0;
  MsiServer = CreateMsiServer();
  v33[0] = MsiServer;
  v10 = MsiServer;
  if ( MsiServer )
  {
    v11 = (*(__int64 (__fastcall **)(struct IMsiServer *))(*(_QWORD *)MsiServer + 224LL))(MsiServer);
    v30 = 1;
    v12 = v11;
    v14 = (*(__int64 (__fastcall **)(struct IMsiServer *, _QWORD, _QWORD, unsigned int *, WCHAR *))(*(_QWORD *)v10
                                                                                                  + 176LL))(
            v10,
            hTransactionHandle,
            dwTransactionAttributes,
            &v30,
            Name);
    if ( v14 )
    {
LABEL_48:
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(v33);
      CCoUninitialize::~CCoUninitialize((CCoUninitialize *)v29);
      return v14;
    }
    CMsiAPIMessage::SetInternalHandler(v13, v30, 0);
    if ( dwTransactionAttributes != 2 )
      goto LABEL_16;
    if ( g_pEmbeddedUI )
      CMsiEmbeddedUIManager::`scalar deleting destructor'((CMsiEmbeddedUIManager *)g_pEmbeddedUI, v15);
    v16 = operator new(0x448u);
    if ( v16 )
    {
      v16[65] = 0;
      v16[66] = 0;
      *((_WORD *)v16 + 274) = 0;
      *((_DWORD *)v16 + 136) = 0;
      *(_QWORD *)((char *)v16 + 1068) = 0;
      v16[135] = 0;
      v16[67] = &MsiUIMessageHandler::`vftable';
      *((_DWORD *)v16 + 272) = 0;
      *((_BYTE *)v16 + 1092) = 0;
      *(_WORD *)v16 = 0;
      v32 = 0;
      g_pEmbeddedUI = (LPCWSTR)v16;
      v17 = operator new(0x208u);
      v18 = v17;
      if ( v17 )
      {
        v31 = 0;
        (*(void (__fastcall **)(struct IMsiServer *, void *, unsigned int *, unsigned int *))(*(_QWORD *)v10 + 208LL))(
          v10,
          v17,
          &v32,
          &v31);
        CMsiEmbeddedUIManager::JoinExistingEEUI(v19, v18, v32, v31);
        operator delete(v18);
LABEL_16:
        v20 = OpenEventW(0x100000u, 0, Name);
        if ( !v20 )
        {
          if ( g_dmDiagnosticMode )
          {
            v22 = L"Error occured opening event: %s";
            v21 = Name;
            goto LABEL_46;
          }
          goto LABEL_47;
        }
        if ( (int)StringCchPrintfW(v35, 0x105u, L"%s%s", Name, L"ET") < 0 )
        {
          if ( g_dmDiagnosticMode )
          {
            v21 = (WCHAR *)L"(NULL)";
            v22 = L"Error occurred in string function, unable to create end transaction event.";
LABEL_46:
            DebugString(9, 0, 0, v22, v21, L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", 0, 0);
            goto LABEL_47;
          }
          goto LABEL_47;
        }
        g_hEndTransactionEvent = OpenEventW(0x100000u, 0, v35);
        if ( !g_hEndTransactionEvent && g_dmDiagnosticMode )
          DebugString(
            9,
            0,
            0,
            L"Error occured opening event: %s",
            v35,
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            0,
            0);
        if ( (int)StringCchCatW(Name, 0x105u, L"Reset") < 0 )
        {
          if ( g_dmDiagnosticMode )
            DebugString(
              9,
              0,
              0,
              L"Error occurred in string function, unable to create ack event.",
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              0,
              0);
          goto LABEL_47;
        }
        if ( v12 )
        {
          EventW = OpenEventW(0x100002u, 0, Name);
          if ( !EventW )
            goto LABEL_30;
          (*(void (__fastcall **)(struct IMsiServer *))(*(_QWORD *)v10 + 192LL))(v10);
          WaitForSingleObject(EventW, 0xFFFFFFFF);
        }
        else
        {
          EventW = CreateEventW(0, 0, 0, Name);
          if ( !EventW )
          {
LABEL_30:
            if ( g_dmDiagnosticMode )
              DebugString(
                9,
                0,
                0,
                L"Error occured creating event",
                L"(NULL)",
                L"(NULL)",
                L"(NULL)",
                L"(NULL)",
                L"(NULL)",
                L"(NULL)",
                0,
                0);
            goto LABEL_47;
          }
        }
        v24 = CreateEventW(0, 0, 0, 0);
        if ( !v24 )
        {
          if ( g_dmDiagnosticMode )
          {
            v21 = (WCHAR *)L"(NULL)";
            v22 = L"Error occured creating event";
            goto LABEL_46;
          }
LABEL_47:
          v14 = 0;
          goto LABEL_48;
        }
        if ( LoadServices() )
        {
          *phChangeOfOwnerEvent = v24;
          v25 = operator new(0x18u);
          v26 = v25;
          if ( v25 )
          {
            *v25 = v20;
            v25[2] = v24;
            v25[1] = EventW;
            Thread = CreateThread(0, 0, CleanupEEUIOnChangeOfOwnerThread, v25, 0, 0);
            g_hCleanupEEUIThread = Thread;
          }
          else
          {
            Thread = g_hCleanupEEUIThread;
          }
          if ( Thread )
            goto LABEL_47;
          operator delete(v26);
          FreeServices();
          if ( !g_dmDiagnosticMode )
            goto LABEL_47;
          v21 = (WCHAR *)L"(NULL)";
          v22 = L"Error occurred creating cleanup EEUI on change of owner thread.";
          goto LABEL_46;
        }
      }
    }
    else
    {
      g_pEmbeddedUI = 0;
    }
    v14 = 14;
    goto LABEL_48;
  }
  v28 = InSafeMode() ? 0x33 : 0;
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(v33);
  CCoUninitialize::~CCoUninitialize((CCoUninitialize *)v29);
  return v28 + 1601;
}

```

## disassembly

```asm
0x18019ee60  mov     [rsp-8+arg_18], rbx
0x18019ee65  push    rbp
0x18019ee66  push    rsi
0x18019ee67  push    rdi
0x18019ee68  push    r12
0x18019ee6a  push    r13
0x18019ee6c  push    r14
0x18019ee6e  push    r15
0x18019ee70  lea     rbp, [rsp-3B0h]
0x18019ee78  sub     rsp, 4B0h
0x18019ee7f  mov     rax, cs:__security_cookie
0x18019ee86  xor     rax, rsp
0x18019ee89  mov     [rbp+3E0h+var_40], rax
0x18019ee90  xor     r13d, r13d
0x18019ee93  mov     esi, edx
0x18019ee95  cmp     cs:?g_dmDiagnosticMode@@3HA, r13d; int g_dmDiagnosticMode
0x18019ee9c  mov     r15, r8
0x18019ee9f  mov     edi, ecx
0x18019eea1  lea     r8, aNull; "(NULL)"
0x18019eea8  jz      short loc_18019EEE6
0x18019eeaa  mov     [rsp+4E0h+var_488], r13; void *
0x18019eeaf  lea     r9, aEnteringMsijoi; "Entering MsiJoinTransaction. hTransacti"...
0x18019eeb6  mov     [rsp+4E0h+var_490], r13d; unsigned int
0x18019eebb  xor     edx, edx; unsigned __int16
0x18019eebd  mov     [rsp+4E0h+var_498], r8; unsigned __int16 *
0x18019eec2  mov     [rsp+4E0h+var_4A0], r8; unsigned __int16 *
0x18019eec7  mov     [rsp+4E0h+var_4A8], r8; unsigned __int16 *
0x18019eecc  mov     [rsp+4E0h+var_4B0], r8; unsigned __int16 *
0x18019eed1  lea     ecx, [rdx+9]; int
0x18019eed4  mov     [rsp+4E0h+lpThreadId], rsi; unsigned __int16 *
0x18019eed9  xor     r8d, r8d; int
0x18019eedc  mov     qword ptr [rsp+4E0h+dwCreationFlags], rdi; unsigned __int16 *
0x18019eee1  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18019eee6  test    r15, r15
0x18019eee9  jz      loc_18019F415
0x18019eeef  cmp     esi, 2
0x18019eef2  ja      loc_18019F415
0x18019eef8  mov     rax, cs:?CoInitialize@OLE32@@3P6AJPEAX@ZEA; long (*OLE32::CoInitialize)(void *)
0x18019eeff  xor     ecx, ecx
0x18019ef01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019ef06  mov     edx, 80000000h
0x18019ef0b  lea     ecx, [rax+rdx]
0x18019ef0e  test    edx, ecx
0x18019ef10  jnz     short loc_18019EF23
0x18019ef12  cmp     eax, 80010106h
0x18019ef17  jz      short loc_18019EF23
0x18019ef19  mov     eax, 643h
0x18019ef1e  jmp     loc_18019F41A
0x18019ef23  shr     eax, 1Fh
0x18019ef26  xor     al, 1
0x18019ef28  mov     [rsp+4E0h+var_480], al
0x18019ef2c  call    ?CreateMsiServer@@YAPEAUIMsiServer@@XZ; CreateMsiServer(void)
0x18019ef31  mov     [rsp+4E0h+var_470], rax
0x18019ef36  mov     rbx, rax
0x18019ef39  test    rax, rax
0x18019ef3c  jz      loc_18019F3ED
0x18019ef42  mov     rax, [rax]
0x18019ef45  mov     rcx, rbx
0x18019ef48  mov     rax, [rax+0E0h]
0x18019ef4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019ef54  mov     [rsp+4E0h+var_47C], 1
0x18019ef5c  lea     r9, [rsp+4E0h+var_47C]
0x18019ef61  mov     rcx, [rbx]
0x18019ef64  mov     r12b, al
0x18019ef67  mov     r8d, esi
0x18019ef6a  mov     edx, edi
0x18019ef6c  mov     rax, [rcx+0B0h]
0x18019ef73  lea     rcx, [rbp+3E0h+Name]
0x18019ef77  mov     qword ptr [rsp+4E0h+dwCreationFlags], rcx
0x18019ef7c  mov     rcx, rbx
0x18019ef7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019ef84  mov     edi, eax
0x18019ef86  test    eax, eax
0x18019ef88  jnz     loc_18019F3D5
0x18019ef8e  mov     edx, [rsp+4E0h+var_47C]; unsigned int
0x18019ef92  xor     r8d, r8d; HWND *
0x18019ef95  call    ?SetInternalHandler@CMsiAPIMessage@@QEAA?AW4tagINSTALLUILEVEL@@IPEAPEAUHWND__@@@Z; CMsiAPIMessage::SetInternalHandler(uint,HWND__ * *)
0x18019ef9a  cmp     esi, 2
0x18019ef9d  jnz     loc_18019F075
0x18019efa3  mov     rcx, cs:?g_pEmbeddedUI@@3PEAVCMsiEmbeddedUIManager@@EA; this
0x18019efaa  test    rcx, rcx
0x18019efad  jz      short loc_18019EFB4
0x18019efaf  call    ??_GCMsiEmbeddedUIManager@@QEAAPEAXI@Z; CMsiEmbeddedUIManager::`scalar deleting destructor'(uint)
0x18019efb4  mov     ecx, 448h; unsigned __int64
0x18019efb9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18019efbe  mov     rdx, rax
0x18019efc1  test    rax, rax
0x18019efc4  jz      loc_18019F103
0x18019efca  mov     [rax+208h], r13
0x18019efd1  mov     ecx, 208h; unsigned __int64
0x18019efd6  mov     [rax+210h], r13
0x18019efdd  mov     [rax+224h], r13w
0x18019efe5  mov     [rax+220h], r13d
0x18019efec  mov     [rax+42Ch], r13
0x18019eff3  mov     [rax+438h], r13
0x18019effa  lea     rax, ??_7MsiUIMessageHandler@@6B@; const MsiUIMessageHandler::`vftable'
0x18019f001  mov     [rdx+218h], rax
0x18019f008  mov     [rdx+440h], r13d
0x18019f00f  mov     [rdx+444h], r13b
0x18019f016  mov     [rdx], r13w
0x18019f01a  mov     [rsp+4E0h+var_474], r13d
0x18019f01f  mov     cs:?g_pEmbeddedUI@@3PEAVCMsiEmbeddedUIManager@@EA, rdx; CMsiEmbeddedUIManager * g_pEmbeddedUI
0x18019f026  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18019f02b  mov     rdi, rax
0x18019f02e  test    rax, rax
0x18019f031  jz      loc_18019F10A
0x18019f037  mov     [rsp+4E0h+var_478], r13d
0x18019f03c  lea     r9, [rsp+4E0h+var_478]
0x18019f041  mov     rcx, [rbx]
0x18019f044  lea     r8, [rsp+4E0h+var_474]
0x18019f049  mov     rdx, rdi
0x18019f04c  mov     rax, [rcx+0D0h]
0x18019f053  mov     rcx, rbx
0x18019f056  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019f05b  mov     r9d, [rsp+4E0h+var_478]
0x18019f060  mov     rdx, rdi
0x18019f063  mov     r8d, [rsp+4E0h+var_474]
0x18019f068  call    ?JoinExistingEEUI@CMsiEmbeddedUIManager@@QEAAKPEAGKW4icacCustomActionContext@@@Z; CMsiEmbeddedUIManager::JoinExistingEEUI(ushort *,ulong,icacCustomActionContext)
0x18019f06d  mov     rcx, rdi; void *
0x18019f070  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18019f075  mov     edi, 100000h
0x18019f07a  lea     r8, [rbp+3E0h+Name]; lpName
0x18019f07e  mov     ecx, edi; dwDesiredAccess
0x18019f080  xor     edx, edx; bInheritHandle
0x18019f082  call    cs:__imp_OpenEventW
0x18019f088  mov     r14, rax
0x18019f08b  test    rax, rax
0x18019f08e  jz      loc_18019F382
0x18019f094  lea     rax, aEt; "ET"
0x18019f09b  mov     edx, 105h; unsigned __int64
0x18019f0a0  lea     r9, [rbp+3E0h+Name]
0x18019f0a4  mov     qword ptr [rsp+4E0h+dwCreationFlags], rax
0x18019f0a9  lea     r8, aSS_1; "%s%s"
0x18019f0b0  lea     rcx, [rbp+3E0h+var_250]; unsigned __int16 *
0x18019f0b7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18019f0bc  test    eax, eax
0x18019f0be  jns     short loc_18019F114
0x18019f0c0  cmp     cs:?g_dmDiagnosticMode@@3HA, r13d; int g_dmDiagnosticMode
0x18019f0c7  jz      loc_18019F3D2
0x18019f0cd  mov     [rsp+4E0h+var_488], r13
0x18019f0d2  lea     rax, aNull; "(NULL)"
0x18019f0d9  mov     [rsp+4E0h+var_490], r13d
0x18019f0de  lea     r9, aErrorOccurredI; "Error occurred in string function, unab"...
0x18019f0e5  mov     [rsp+4E0h+var_498], rax
0x18019f0ea  mov     [rsp+4E0h+var_4A0], rax
0x18019f0ef  mov     [rsp+4E0h+var_4A8], rax
0x18019f0f4  mov     [rsp+4E0h+var_4B0], rax
0x18019f0f9  mov     [rsp+4E0h+lpThreadId], rax
0x18019f0fe  jmp     loc_18019F3C0
0x18019f103  mov     cs:?g_pEmbeddedUI@@3PEAVCMsiEmbeddedUIManager@@EA, r13; CMsiEmbeddedUIManager * g_pEmbeddedUI
0x18019f10a  mov     edi, 0Eh
0x18019f10f  jmp     loc_18019F3D5
0x18019f114  lea     r8, [rbp+3E0h+var_250]; lpName
0x18019f11b  xor     edx, edx; bInheritHandle
0x18019f11d  mov     ecx, edi; dwDesiredAccess
0x18019f11f  call    cs:__imp_OpenEventW
0x18019f125  mov     cs:?g_hEndTransactionEvent@@3PEAXEA, rax; void * g_hEndTransactionEvent
0x18019f12c  lea     rsi, aNull; "(NULL)"
0x18019f133  test    rax, rax
0x18019f136  jnz     short loc_18019F184
0x18019f138  cmp     cs:?g_dmDiagnosticMode@@3HA, r13d; int g_dmDiagnosticMode
0x18019f13f  jz      short loc_18019F184
0x18019f141  mov     [rsp+4E0h+var_488], r13; void *
0x18019f146  lea     rax, [rbp+3E0h+var_250]
0x18019f14d  mov     [rsp+4E0h+var_490], r13d; unsigned int
0x18019f152  lea     r9, aErrorOccuredOp; "Error occured opening event: %s"
0x18019f159  mov     [rsp+4E0h+var_498], rsi; unsigned __int16 *
0x18019f15e  xor     edx, edx; unsigned __int16
0x18019f160  mov     [rsp+4E0h+var_4A0], rsi; unsigned __int16 *
0x18019f165  xor     r8d, r8d; int
0x18019f168  mov     [rsp+4E0h+var_4A8], rsi; unsigned __int16 *
0x18019f16d  mov     [rsp+4E0h+var_4B0], rsi; unsigned __int16 *
0x18019f172  mov     [rsp+4E0h+lpThreadId], rsi; unsigned __int16 *
0x18019f177  lea     ecx, [rdx+9]; int
0x18019f17a  mov     qword ptr [rsp+4E0h+dwCreationFlags], rax; unsigned __int16 *
0x18019f17f  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18019f184  lea     r8, aReset; "Reset"
0x18019f18b  mov     edx, 105h; unsigned __int64
0x18019f190  lea     rcx, [rbp+3E0h+Name]; unsigned __int16 *
0x18019f194  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18019f199  test    eax, eax
0x18019f19b  jns     short loc_18019F1DE
0x18019f19d  cmp     cs:?g_dmDiagnosticMode@@3HA, r13d; int g_dmDiagnosticMode
0x18019f1a4  jz      loc_18019F3D2
0x18019f1aa  mov     [rsp+4E0h+var_488], r13
0x18019f1af  lea     r9, aErrorOccurredI_0; "Error occurred in string function, unab"...
0x18019f1b6  mov     [rsp+4E0h+var_490], r13d
0x18019f1bb  mov     [rsp+4E0h+var_498], rsi
0x18019f1c0  mov     [rsp+4E0h+var_4A0], rsi
0x18019f1c5  mov     [rsp+4E0h+var_4A8], rsi
0x18019f1ca  mov     [rsp+4E0h+var_4B0], rsi
0x18019f1cf  mov     [rsp+4E0h+lpThreadId], rsi
0x18019f1d4  mov     qword ptr [rsp+4E0h+dwCreationFlags], rsi
0x18019f1d9  jmp     loc_18019F3C5
0x18019f1de  xor     edx, edx; bManualReset
0x18019f1e0  test    r12b, r12b
0x18019f1e3  jz      short loc_18019F25D
0x18019f1e5  lea     r8, [rbp+3E0h+Name]; lpName
0x18019f1e9  mov     ecx, 100002h; dwDesiredAccess
0x18019f1ee  call    cs:__imp_OpenEventW
0x18019f1f4  mov     rdi, rax
0x18019f1f7  test    rax, rax
0x18019f1fa  jnz     short loc_18019F23D
0x18019f1fc  cmp     cs:?g_dmDiagnosticMode@@3HA, r13d; int g_dmDiagnosticMode
0x18019f203  jz      loc_18019F3D2
0x18019f209  mov     [rsp+4E0h+var_488], r13
0x18019f20e  lea     r9, aErrorOccuredCr_1; "Error occured creating event"
0x18019f215  mov     [rsp+4E0h+var_490], r13d
0x18019f21a  mov     [rsp+4E0h+var_498], rsi
0x18019f21f  mov     [rsp+4E0h+var_4A0], rsi
0x18019f224  mov     [rsp+4E0h+var_4A8], rsi
0x18019f229  mov     [rsp+4E0h+var_4B0], rsi
0x18019f22e  mov     [rsp+4E0h+lpThreadId], rsi
0x18019f233  mov     qword ptr [rsp+4E0h+dwCreationFlags], rsi
0x18019f238  jmp     loc_18019F3C5
0x18019f23d  mov     rax, [rbx]
0x18019f240  mov     rcx, rbx
0x18019f243  mov     rax, [rax+0C0h]
0x18019f24a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019f24f  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18019f252  mov     rcx, rdi; hHandle
0x18019f255  call    cs:__imp_WaitForSingleObject
0x18019f25b  jmp     short loc_18019F274
0x18019f25d  lea     r9, [rbp+3E0h+Name]; lpName
0x18019f261  xor     r8d, r8d; bInitialState
0x18019f264  xor     ecx, ecx; lpEventAttributes
0x18019f266  call    cs:__imp_CreateEventW
0x18019f26c  mov     rdi, rax
0x18019f26f  test    rax, rax
0x18019f272  jz      short loc_18019F1FC
0x18019f274  xor     r9d, r9d; lpName
0x18019f277  xor     r8d, r8d; bInitialState
0x18019f27a  xor     edx, edx; bManualReset
0x18019f27c  xor     ecx, ecx; lpEventAttributes
0x18019f27e  call    cs:__imp_CreateEventW
0x18019f284  mov     rsi, rax
0x18019f287  test    rax, rax
0x18019f28a  jz      loc_18019F342
0x18019f290  call    ?LoadServices@@YAPEAVIMsiServices@@XZ; LoadServices(void)
0x18019f295  test    rax, rax
0x18019f298  jz      loc_18019F10A
0x18019f29e  mov     ecx, 18h; unsigned __int64
0x18019f2a3  mov     [r15], rsi
0x18019f2a6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18019f2ab  mov     rbx, rax
0x18019f2ae  test    rax, rax
0x18019f2b1  jz      short loc_18019F2E5
0x18019f2b3  mov     [rsp+4E0h+lpThreadId], r13; lpThreadId
0x18019f2b8  lea     r8, ?CleanupEEUIOnChangeOfOwnerThread@@YAKPEAX@Z; lpStartAddress
0x18019f2bf  mov     r9, rax; lpParameter
0x18019f2c2  mov     [rsp+4E0h+dwCreationFlags], r13d; dwCreationFlags
0x18019f2c7  xor     edx, edx; dwStackSize
0x18019f2c9  mov     [rax], r14
0x18019f2cc  xor     ecx, ecx; lpThreadAttributes
0x18019f2ce  mov     [rax+10h], rsi
0x18019f2d2  mov     [rax+8], rdi
0x18019f2d6  call    cs:__imp_CreateThread
0x18019f2dc  mov     cs:?g_hCleanupEEUIThread@@3PEAXEA, rax; void * g_hCleanupEEUIThread
0x18019f2e3  jmp     short loc_18019F2EC
0x18019f2e5  mov     rax, cs:?g_hCleanupEEUIThread@@3PEAXEA; void * g_hCleanupEEUIThread
0x18019f2ec  test    rax, rax
0x18019f2ef  jnz     loc_18019F3D2
0x18019f2f5  mov     rcx, rbx; void *
0x18019f2f8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18019f2fd  call    ?FreeServices@@YAHXZ; FreeServices(void)
0x18019f302  cmp     cs:?g_dmDiagnosticMode@@3HA, r13d; int g_dmDiagnosticMode
0x18019f309  jz      loc_18019F3D2
0x18019f30f  mov     [rsp+4E0h+var_488], r13
0x18019f314  lea     rax, aNull; "(NULL)"
0x18019f31b  mov     [rsp+4E0h+var_490], r13d
0x18019f320  lea     r9, aErrorOccurredC; "Error occurred creating cleanup EEUI on"...
0x18019f327  mov     [rsp+4E0h+var_498], rax
0x18019f32c  mov     [rsp+4E0h+var_4A0], rax
0x18019f331  mov     [rsp+4E0h+var_4A8], rax
0x18019f336  mov     [rsp+4E0h+var_4B0], rax
0x18019f33b  mov     [rsp+4E0h+lpThreadId], rax
0x18019f340  jmp     short loc_18019F3C0
0x18019f342  cmp     cs:?g_dmDiagnosticMode@@3HA, r13d; int g_dmDiagnosticMode
0x18019f349  jz      loc_18019F3D2
0x18019f34f  mov     [rsp+4E0h+var_488], r13
0x18019f354  lea     rax, aNull; "(NULL)"
0x18019f35b  mov     [rsp+4E0h+var_490], r13d
0x18019f360  lea     r9, aErrorOccuredCr_1; "Error occured creating event"
0x18019f367  mov     [rsp+4E0h+var_498], rax
0x18019f36c  mov     [rsp+4E0h+var_4A0], rax
0x18019f371  mov     [rsp+4E0h+var_4A8], rax
0x18019f376  mov     [rsp+4E0h+var_4B0], rax
0x18019f37b  mov     [rsp+4E0h+lpThreadId], rax
0x18019f380  jmp     short loc_18019F3C0
0x18019f382  cmp     cs:?g_dmDiagnosticMode@@3HA, r13d; int g_dmDiagnosticMode
0x18019f389  jz      short loc_18019F3D2
0x18019f38b  mov     [rsp+4E0h+var_488], r13; void *
0x18019f390  lea     rax, aNull; "(NULL)"
0x18019f397  mov     [rsp+4E0h+var_490], r13d; unsigned int
0x18019f39c  lea     r9, aErrorOccuredOp; "Error occured opening event: %s"
0x18019f3a3  mov     [rsp+4E0h+var_498], rax; unsigned __int16 *
0x18019f3a8  mov     [rsp+4E0h+var_4A0], rax; unsigned __int16 *
0x18019f3ad  mov     [rsp+4E0h+var_4A8], rax; unsigned __int16 *
0x18019f3b2  mov     [rsp+4E0h+var_4B0], rax; unsigned __int16 *
0x18019f3b7  mov     [rsp+4E0h+lpThreadId], rax; unsigned __int16 *
  ... truncated ...
```
