# MsiBeginTransactionW

- ea: `0x18019b560`
- end: `0x18019b9fc`
- name: `MsiBeginTransactionW`
- size: `1180`
- prototype: `UINT __stdcall(LPCWSTR szName, DWORD dwTransactionAttributes, MSIHANDLE *phTransactionHandle, HANDLE *phChangeOfOwnerEvent)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x18019b430`

## callees

- `0x18001de18`
- `0x18001e9f8`
- `0x180022120`
- `0x1800255e0`
- `0x180025a18`
- `0x180061334`
- `0x1800620e4`
- `0x180066074`
- `0x180074bd0`
- `0x180126db8`
- `0x180143d44`
- `0x18019b560`
- `0x1801cdbe0`
- `0x18025ab80`
- `0x18025c010`

## import_xrefs

- `KERNEL32!OpenEventW` at `0x18019b6c6`
- `KERNEL32!OpenEventW` at `0x18019b755`
- `KERNEL32!OpenEventW` at `0x18019b6c6`
- `KERNEL32!OpenEventW` at `0x18019b755`
- `KERNEL32!CreateEventW` at `0x18019b81f`
- `KERNEL32!CreateEventW` at `0x18019b832`
- `KERNEL32!CreateEventW` at `0x18019b81f`
- `KERNEL32!CreateEventW` at `0x18019b832`
- `KERNEL32!CreateThread` at `0x18019b898`
- `KERNEL32!CreateThread` at `0x18019b898`

## string_xrefs

- `0x18019b5c1`: `Entering MsiBeginTransactionW. szTransactionName: %s, dwTransactionAttributes: %d`
- `0x18019b725`: `Error occurred in string function, unable to create end transaction event.`
- `0x18019b788`: `Error occured opening event: %s`
- `0x18019b95c`: `Error occured opening event: %s`
- `0x18019b7e4`: `Error occurred in string function, unable to create ack event.`
- `0x18019b8e2`: `Error occurred creating cleanup EEUI on change of owner thread.`

## pseudocode

```c
UINT __stdcall MsiBeginTransactionW(
        LPCWSTR szName,
        DWORD dwTransactionAttributes,
        MSIHANDLE *phTransactionHandle,
        HANDLE *phChangeOfOwnerEvent)
{
  const unsigned __int16 *v8; // rax
  int v9; // eax
  struct IMsiServer *MsiServer; // rax
  UINT v12; // r14d
  HANDLE v13; // r12
  WCHAR *v14; // rax
  const unsigned __int16 *v15; // r9
  HANDLE EventW; // rsi
  HANDLE v17; // rdi
  _QWORD *v18; // rax
  void *v19; // rbx
  HANDLE Thread; // rax
  int v21; // ebx
  bool v22[8]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int64 v23; // [rsp+68h] [rbp-98h] BYREF
  WCHAR Name[264]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR v25[264]; // [rsp+280h] [rbp+180h] BYREF

  v23 = 0;
  if ( g_dmDiagnosticMode )
  {
    v8 = szName;
    if ( !szName )
      v8 = L"(null)";
    DebugString(
      9,
      0,
      0,
      L"Entering MsiBeginTransactionW. szTransactionName: %s, dwTransactionAttributes: %d",
      v8,
      (const unsigned __int16 *)dwTransactionAttributes,
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      0,
      0);
  }
  if ( (int)StringCchLengthW(szName, 0x7FFFFFFFu, &v23) < 0
    || !szName
    || !v23
    || !phTransactionHandle
    || !phChangeOfOwnerEvent
    || dwTransactionAttributes > 1 )
  {
    return 87;
  }
  v9 = ((__int64 (__fastcall *)(_QWORD))OLE32::CoInitialize)(0);
  if ( (int)(v9 + 0x80000000) >= 0 && v9 != -2147417850 )
    return 1603;
  v22[0] = v9 >= 0;
  MsiServer = CreateMsiServer();
  v23 = (unsigned __int64)MsiServer;
  if ( MsiServer )
  {
    v12 = (*(__int64 (__fastcall **)(struct IMsiServer *, LPCWSTR, _QWORD, MSIHANDLE *, WCHAR *))(*(_QWORD *)MsiServer
                                                                                                + 160LL))(
            MsiServer,
            szName,
            dwTransactionAttributes,
            phTransactionHandle,
            Name);
    v13 = OpenEventW(0x100000u, 0, Name);
    if ( v13 )
    {
      if ( (int)StringCchPrintfW(v25, 0x105u, L"%s%s", Name, L"ET") >= 0 )
      {
        g_hEndTransactionEvent = OpenEventW(0x100000u, 0, v25);
        if ( !g_hEndTransactionEvent && g_dmDiagnosticMode )
          DebugString(
            9,
            0,
            0,
            L"Error occured opening event: %s",
            v25,
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
          goto LABEL_40;
        }
        EventW = CreateEventW(0, 0, 0, Name);
        v17 = CreateEventW(0, 0, 0, 0);
        if ( !v17 || !EventW )
        {
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
          goto LABEL_40;
        }
        if ( LoadServices() )
        {
          *phChangeOfOwnerEvent = v17;
          v18 = operator new(0x18u);
          v19 = v18;
          if ( v18 )
          {
            *v18 = v13;
            v18[2] = v17;
            v18[1] = EventW;
            Thread = CreateThread(0, 0, CleanupEEUIOnChangeOfOwnerThread, v18, 0, 0);
            g_hCleanupEEUIThread = Thread;
          }
          else
          {
            Thread = g_hCleanupEEUIThread;
          }
          if ( Thread )
            goto LABEL_40;
          operator delete(v19);
          FreeServices();
          if ( !g_dmDiagnosticMode )
            goto LABEL_40;
          v14 = (WCHAR *)L"(NULL)";
          v15 = L"Error occurred creating cleanup EEUI on change of owner thread.";
          goto LABEL_39;
        }
        v12 = 14;
      }
      else if ( g_dmDiagnosticMode )
      {
        v14 = (WCHAR *)L"(NULL)";
        v15 = L"Error occurred in string function, unable to create end transaction event.";
LABEL_39:
        DebugString(9, 0, 0, v15, v14, L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", 0, 0);
      }
    }
    else if ( g_dmDiagnosticMode )
    {
      v15 = L"Error occured opening event: %s";
      v14 = Name;
      goto LABEL_39;
    }
LABEL_40:
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v23);
    CCoUninitialize::~CCoUninitialize((CCoUninitialize *)v22);
    return v12;
  }
  v21 = InSafeMode() ? 0x33 : 0;
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v23);
  CCoUninitialize::~CCoUninitialize((CCoUninitialize *)v22);
  return v21 + 1601;
}

```

## disassembly

```asm
0x18019b560  push    rbp
0x18019b562  push    rbx
0x18019b563  push    rsi
0x18019b564  push    rdi
0x18019b565  push    r12
0x18019b567  push    r13
0x18019b569  push    r14
0x18019b56b  push    r15
0x18019b56d  lea     rbp, [rsp-3A8h]
0x18019b575  sub     rsp, 4A8h
0x18019b57c  mov     rax, cs:__security_cookie
0x18019b583  xor     rax, rsp
0x18019b586  mov     [rbp+3E0h+var_50], rax
0x18019b58d  xor     r13d, r13d
0x18019b590  mov     edi, edx
0x18019b592  cmp     cs:?g_dmDiagnosticMode@@3HA, r13d; int g_dmDiagnosticMode
0x18019b599  mov     rsi, r8
0x18019b59c  mov     r15, r9
0x18019b59f  mov     [rsp+4E0h+var_478], r13
0x18019b5a4  mov     rbx, rcx
0x18019b5a7  lea     r8, aNull; "(NULL)"
0x18019b5ae  jz      short loc_18019B5FD
0x18019b5b0  mov     [rsp+4E0h+var_488], r13; void *
0x18019b5b5  lea     rdx, aNull_4; "(null)"
0x18019b5bc  mov     [rsp+4E0h+var_490], r13d; unsigned int
0x18019b5c1  lea     r9, aEnteringMsibeg_0; "Entering MsiBeginTransactionW. szTransa"...
0x18019b5c8  mov     [rsp+4E0h+var_498], r8; unsigned __int16 *
0x18019b5cd  test    rcx, rcx
0x18019b5d0  mov     [rsp+4E0h+var_4A0], r8; unsigned __int16 *
0x18019b5d5  mov     rax, rcx
0x18019b5d8  mov     [rsp+4E0h+var_4A8], r8; unsigned __int16 *
0x18019b5dd  cmovz   rax, rdx
0x18019b5e1  mov     [rsp+4E0h+var_4B0], r8; unsigned __int16 *
0x18019b5e6  xor     edx, edx; unsigned __int16
0x18019b5e8  mov     [rsp+4E0h+lpThreadId], rdi; unsigned __int16 *
0x18019b5ed  xor     r8d, r8d; int
0x18019b5f0  mov     qword ptr [rsp+4E0h+dwCreationFlags], rax; unsigned __int16 *
0x18019b5f5  lea     ecx, [rdx+9]; int
0x18019b5f8  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18019b5fd  lea     r8, [rsp+4E0h+var_478]; unsigned __int64 *
0x18019b602  mov     edx, 7FFFFFFFh; unsigned __int64
0x18019b607  mov     rcx, rbx; unsigned __int16 *
0x18019b60a  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18019b60f  test    eax, eax
0x18019b611  js      loc_18019B9D4
0x18019b617  test    rbx, rbx
0x18019b61a  jz      loc_18019B9D4
0x18019b620  cmp     [rsp+4E0h+var_478], r13
0x18019b625  jz      loc_18019B9D4
0x18019b62b  test    rsi, rsi
0x18019b62e  jz      loc_18019B9D4
0x18019b634  test    r15, r15
0x18019b637  jz      loc_18019B9D4
0x18019b63d  cmp     edi, 1
0x18019b640  ja      loc_18019B9D4
0x18019b646  mov     rax, cs:?CoInitialize@OLE32@@3P6AJPEAX@ZEA; long (*OLE32::CoInitialize)(void *)
0x18019b64d  xor     ecx, ecx
0x18019b64f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019b654  mov     edx, 80000000h
0x18019b659  lea     ecx, [rax+rdx]
0x18019b65c  test    edx, ecx
0x18019b65e  jnz     short loc_18019B671
0x18019b660  cmp     eax, 80010106h
0x18019b665  jz      short loc_18019B671
0x18019b667  mov     eax, 643h
0x18019b66c  jmp     loc_18019B9D9
0x18019b671  shr     eax, 1Fh
0x18019b674  xor     al, 1
0x18019b676  mov     [rsp+4E0h+var_480], al
0x18019b67a  call    ?CreateMsiServer@@YAPEAUIMsiServer@@XZ; CreateMsiServer(void)
0x18019b67f  mov     [rsp+4E0h+var_478], rax
0x18019b684  mov     r10, rax
0x18019b687  test    rax, rax
0x18019b68a  jz      loc_18019B9AC
0x18019b690  mov     rcx, [rax]
0x18019b693  mov     r9, rsi
0x18019b696  mov     r8d, edi
0x18019b699  mov     rdx, rbx
0x18019b69c  mov     rax, [rcx+0A0h]
0x18019b6a3  lea     rcx, [rsp+4E0h+Name]
0x18019b6a8  mov     qword ptr [rsp+4E0h+dwCreationFlags], rcx
0x18019b6ad  mov     rcx, r10
0x18019b6b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019b6b5  mov     ebx, 100000h
0x18019b6ba  lea     r8, [rsp+4E0h+Name]; lpName
0x18019b6bf  mov     ecx, ebx; dwDesiredAccess
0x18019b6c1  xor     edx, edx; bInheritHandle
0x18019b6c3  mov     r14d, eax
0x18019b6c6  call    cs:__imp_OpenEventW
0x18019b6cc  mov     r12, rax
0x18019b6cf  test    rax, rax
0x18019b6d2  jz      loc_18019B942
0x18019b6d8  lea     rax, aEt; "ET"
0x18019b6df  mov     edi, 105h
0x18019b6e4  mov     edx, edi; unsigned __int64
0x18019b6e6  mov     qword ptr [rsp+4E0h+dwCreationFlags], rax
0x18019b6eb  lea     r9, [rsp+4E0h+Name]
0x18019b6f0  lea     r8, aSS_1; "%s%s"
0x18019b6f7  lea     rcx, [rbp+3E0h+var_260]; unsigned __int16 *
0x18019b6fe  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18019b703  test    eax, eax
0x18019b705  jns     short loc_18019B74A
0x18019b707  cmp     cs:?g_dmDiagnosticMode@@3HA, r13d; int g_dmDiagnosticMode
0x18019b70e  jz      loc_18019B993
0x18019b714  mov     [rsp+4E0h+var_488], r13
0x18019b719  lea     rax, aNull; "(NULL)"
0x18019b720  mov     [rsp+4E0h+var_490], r13d
0x18019b725  lea     r9, aErrorOccurredI; "Error occurred in string function, unab"...
0x18019b72c  mov     [rsp+4E0h+var_498], rax
0x18019b731  mov     [rsp+4E0h+var_4A0], rax
0x18019b736  mov     [rsp+4E0h+var_4A8], rax
0x18019b73b  mov     [rsp+4E0h+var_4B0], rax
0x18019b740  mov     [rsp+4E0h+lpThreadId], rax
0x18019b745  jmp     loc_18019B981
0x18019b74a  lea     r8, [rbp+3E0h+var_260]; lpName
0x18019b751  xor     edx, edx; bInheritHandle
0x18019b753  mov     ecx, ebx; dwDesiredAccess
0x18019b755  call    cs:__imp_OpenEventW
0x18019b75b  mov     cs:?g_hEndTransactionEvent@@3PEAXEA, rax; void * g_hEndTransactionEvent
0x18019b762  lea     rbx, aNull; "(NULL)"
0x18019b769  test    rax, rax
0x18019b76c  jnz     short loc_18019B7BA
0x18019b76e  cmp     cs:?g_dmDiagnosticMode@@3HA, r13d; int g_dmDiagnosticMode
0x18019b775  jz      short loc_18019B7BA
0x18019b777  mov     [rsp+4E0h+var_488], r13; void *
0x18019b77c  lea     rax, [rbp+3E0h+var_260]
0x18019b783  mov     [rsp+4E0h+var_490], r13d; unsigned int
0x18019b788  lea     r9, aErrorOccuredOp; "Error occured opening event: %s"
0x18019b78f  mov     [rsp+4E0h+var_498], rbx; unsigned __int16 *
0x18019b794  xor     edx, edx; unsigned __int16
0x18019b796  mov     [rsp+4E0h+var_4A0], rbx; unsigned __int16 *
0x18019b79b  xor     r8d, r8d; int
0x18019b79e  mov     [rsp+4E0h+var_4A8], rbx; unsigned __int16 *
0x18019b7a3  mov     [rsp+4E0h+var_4B0], rbx; unsigned __int16 *
0x18019b7a8  mov     [rsp+4E0h+lpThreadId], rbx; unsigned __int16 *
0x18019b7ad  lea     ecx, [rdx+9]; int
0x18019b7b0  mov     qword ptr [rsp+4E0h+dwCreationFlags], rax; unsigned __int16 *
0x18019b7b5  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18019b7ba  lea     r8, aReset; "Reset"
0x18019b7c1  mov     rdx, rdi; unsigned __int64
0x18019b7c4  lea     rcx, [rsp+4E0h+Name]; unsigned __int16 *
0x18019b7c9  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18019b7ce  test    eax, eax
0x18019b7d0  jns     short loc_18019B813
0x18019b7d2  cmp     cs:?g_dmDiagnosticMode@@3HA, r13d; int g_dmDiagnosticMode
0x18019b7d9  jz      loc_18019B993
0x18019b7df  mov     [rsp+4E0h+var_488], r13
0x18019b7e4  lea     r9, aErrorOccurredI_0; "Error occurred in string function, unab"...
0x18019b7eb  mov     [rsp+4E0h+var_490], r13d
0x18019b7f0  mov     [rsp+4E0h+var_498], rbx
0x18019b7f5  mov     [rsp+4E0h+var_4A0], rbx
0x18019b7fa  mov     [rsp+4E0h+var_4A8], rbx
0x18019b7ff  mov     [rsp+4E0h+var_4B0], rbx
0x18019b804  mov     [rsp+4E0h+lpThreadId], rbx
0x18019b809  mov     qword ptr [rsp+4E0h+dwCreationFlags], rbx
0x18019b80e  jmp     loc_18019B986
0x18019b813  lea     r9, [rsp+4E0h+Name]; lpName
0x18019b818  xor     r8d, r8d; bInitialState
0x18019b81b  xor     edx, edx; bManualReset
0x18019b81d  xor     ecx, ecx; lpEventAttributes
0x18019b81f  call    cs:__imp_CreateEventW
0x18019b825  xor     r9d, r9d; lpName
0x18019b828  xor     r8d, r8d; bInitialState
0x18019b82b  xor     edx, edx; bManualReset
0x18019b82d  xor     ecx, ecx; lpEventAttributes
0x18019b82f  mov     rsi, rax
0x18019b832  call    cs:__imp_CreateEventW
0x18019b838  mov     rdi, rax
0x18019b83b  test    rax, rax
0x18019b83e  jz      loc_18019B904
0x18019b844  test    rsi, rsi
0x18019b847  jz      loc_18019B904
0x18019b84d  call    ?LoadServices@@YAPEAVIMsiServices@@XZ; LoadServices(void)
0x18019b852  test    rax, rax
0x18019b855  jnz     short loc_18019B860
0x18019b857  lea     r14d, [rax+0Eh]
0x18019b85b  jmp     loc_18019B993
0x18019b860  mov     ecx, 18h; unsigned __int64
0x18019b865  mov     [r15], rdi
0x18019b868  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18019b86d  mov     rbx, rax
0x18019b870  test    rax, rax
0x18019b873  jz      short loc_18019B8A7
0x18019b875  mov     [rsp+4E0h+lpThreadId], r13; lpThreadId
0x18019b87a  lea     r8, ?CleanupEEUIOnChangeOfOwnerThread@@YAKPEAX@Z; lpStartAddress
0x18019b881  mov     r9, rax; lpParameter
0x18019b884  mov     [rsp+4E0h+dwCreationFlags], r13d; dwCreationFlags
0x18019b889  xor     edx, edx; dwStackSize
0x18019b88b  mov     [rax], r12
0x18019b88e  xor     ecx, ecx; lpThreadAttributes
0x18019b890  mov     [rax+10h], rdi
0x18019b894  mov     [rax+8], rsi
0x18019b898  call    cs:__imp_CreateThread
0x18019b89e  mov     cs:?g_hCleanupEEUIThread@@3PEAXEA, rax; void * g_hCleanupEEUIThread
0x18019b8a5  jmp     short loc_18019B8AE
0x18019b8a7  mov     rax, cs:?g_hCleanupEEUIThread@@3PEAXEA; void * g_hCleanupEEUIThread
0x18019b8ae  test    rax, rax
0x18019b8b1  jnz     loc_18019B993
0x18019b8b7  mov     rcx, rbx; void *
0x18019b8ba  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18019b8bf  call    ?FreeServices@@YAHXZ; FreeServices(void)
0x18019b8c4  cmp     cs:?g_dmDiagnosticMode@@3HA, r13d; int g_dmDiagnosticMode
0x18019b8cb  jz      loc_18019B993
0x18019b8d1  mov     [rsp+4E0h+var_488], r13
0x18019b8d6  lea     rax, aNull; "(NULL)"
0x18019b8dd  mov     [rsp+4E0h+var_490], r13d
0x18019b8e2  lea     r9, aErrorOccurredC; "Error occurred creating cleanup EEUI on"...
0x18019b8e9  mov     [rsp+4E0h+var_498], rax
0x18019b8ee  mov     [rsp+4E0h+var_4A0], rax
0x18019b8f3  mov     [rsp+4E0h+var_4A8], rax
0x18019b8f8  mov     [rsp+4E0h+var_4B0], rax
0x18019b8fd  mov     [rsp+4E0h+lpThreadId], rax
0x18019b902  jmp     short loc_18019B981
0x18019b904  cmp     cs:?g_dmDiagnosticMode@@3HA, r13d; int g_dmDiagnosticMode
0x18019b90b  jz      loc_18019B993
0x18019b911  mov     [rsp+4E0h+var_488], r13
0x18019b916  lea     r9, aErrorOccuredCr_1; "Error occured creating event"
0x18019b91d  mov     [rsp+4E0h+var_490], r13d
0x18019b922  mov     [rsp+4E0h+var_498], rbx
0x18019b927  mov     [rsp+4E0h+var_4A0], rbx
0x18019b92c  mov     [rsp+4E0h+var_4A8], rbx
0x18019b931  mov     [rsp+4E0h+var_4B0], rbx
0x18019b936  mov     [rsp+4E0h+lpThreadId], rbx
0x18019b93b  mov     qword ptr [rsp+4E0h+dwCreationFlags], rbx
0x18019b940  jmp     short loc_18019B986
0x18019b942  cmp     cs:?g_dmDiagnosticMode@@3HA, r13d; int g_dmDiagnosticMode
0x18019b949  jz      short loc_18019B993
0x18019b94b  mov     [rsp+4E0h+var_488], r13; void *
0x18019b950  lea     rax, aNull; "(NULL)"
0x18019b957  mov     [rsp+4E0h+var_490], r13d; unsigned int
0x18019b95c  lea     r9, aErrorOccuredOp; "Error occured opening event: %s"
0x18019b963  mov     [rsp+4E0h+var_498], rax; unsigned __int16 *
0x18019b968  mov     [rsp+4E0h+var_4A0], rax; unsigned __int16 *
0x18019b96d  mov     [rsp+4E0h+var_4A8], rax; unsigned __int16 *
0x18019b972  mov     [rsp+4E0h+var_4B0], rax; unsigned __int16 *
0x18019b977  mov     [rsp+4E0h+lpThreadId], rax; unsigned __int16 *
0x18019b97c  lea     rax, [rsp+4E0h+Name]
0x18019b981  mov     qword ptr [rsp+4E0h+dwCreationFlags], rax; unsigned __int16 *
0x18019b986  xor     edx, edx; unsigned __int16
0x18019b988  xor     r8d, r8d; int
0x18019b98b  lea     ecx, [rdx+9]; int
0x18019b98e  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18019b993  lea     rcx, [rsp+4E0h+var_478]
0x18019b998  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x18019b99d  lea     rcx, [rsp+4E0h+var_480]; this
0x18019b9a2  call    ??1CCoUninitialize@@QEAA@XZ; CCoUninitialize::~CCoUninitialize(void)
0x18019b9a7  mov     eax, r14d
0x18019b9aa  jmp     short loc_18019B9D9
0x18019b9ac  call    ?InSafeMode@@YA_NXZ; InSafeMode(void)
0x18019b9b1  neg     al
0x18019b9b3  lea     rcx, [rsp+4E0h+var_478]
0x18019b9b8  sbb     ebx, ebx
0x18019b9ba  and     ebx, 33h
0x18019b9bd  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x18019b9c2  lea     rcx, [rsp+4E0h+var_480]; this
0x18019b9c7  call    ??1CCoUninitialize@@QEAA@XZ; CCoUninitialize::~CCoUninitialize(void)
0x18019b9cc  lea     eax, [rbx+641h]
0x18019b9d2  jmp     short loc_18019B9D9
0x18019b9d4  mov     eax, 57h ; 'W'
0x18019b9d9  mov     rcx, [rbp+3E0h+var_50]
0x18019b9e0  xor     rcx, rsp; StackCookie
0x18019b9e3  call    __security_check_cookie
0x18019b9e8  add     rsp, 4A8h
0x18019b9ef  pop     r15
0x18019b9f1  pop     r14
0x18019b9f3  pop     r13
0x18019b9f5  pop     r12
0x18019b9f7  pop     rdi
0x18019b9f8  pop     rsi
0x18019b9f9  pop     rbx
0x18019b9fa  pop     rbp
0x18019b9fb  retn
```
