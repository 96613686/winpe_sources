# CFoDWizard::StartWizard(HWND__ *,ushort const *,int,int &)

- ea: `0x180029208`
- end: `0x180029404`
- name: `?StartWizard@CFoDWizard@@QEAAJPEAUHWND__@@PEBGHAEAH@Z`
- size: `508`
- prototype: `__int64 __fastcall(CFoDWizard *this, unsigned __int64, const unsigned __int16 *, int, int *)`
- caller_count: `1`
- callee_count: `15`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800298e4`

## callees

- `0x18000b2dc`
- `0x1800227c8`
- `0x180022e20`
- `0x180022ed4`
- `0x180024880`
- `0x180024c44`
- `0x1800260e4`
- `0x180027f18`
- `0x180028610`
- `0x180028bec`
- `0x180028e14`
- `0x180028eac`
- `0x180028ef4`
- `0x180029208`
- `0x18002fd88`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002931a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002931a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002933a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029352`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002933a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029352`

## string_xrefs

- `0x1800292f1`: `Windows Optional Component Manager Command-Line`

## pseudocode

```c
__int64 __fastcall CFoDWizard::StartWizard(
        CFoDWizard *this,
        unsigned __int64 a2,
        const unsigned __int16 *a3,
        int a4,
        int *a5)
{
  CFoDCommandLineOptions *v6; // rcx
  int v9; // ebx
  COCInstallHelper *v10; // rax
  COCInstallHelper *v11; // rax
  bool v12; // zf
  _QWORD *v13; // rbx
  HANDLE EventW; // rsi
  signed int LastError; // eax
  bool v16; // sf
  signed int v17; // eax
  int inited; // eax
  __int64 v19; // rcx

  v6 = (CFoDWizard *)((char *)this + 192);
  if ( !*(_DWORD *)v6 )
  {
    v9 = CFoDCommandLineOptions::Parse(v6, a3, (int)a3, a4);
    if ( v9 == -2147024809 )
    {
      if ( !a4 )
        ShowHelpMessage();
      goto LABEL_34;
    }
    if ( v9 < 0 )
      goto LABEL_34;
  }
  if ( *((_DWORD *)this + 57) )
  {
    if ( !a4 )
    {
      ShowHelpMessage();
      v9 = 0;
      goto LABEL_36;
    }
    v9 = -2147024809;
LABEL_34:
    v19 = (unsigned int)v9;
    goto LABEL_35;
  }
  *((_QWORD *)this + 31) = 0;
  *(_QWORD *)((char *)this + 260) = 0;
  *(_QWORD *)((char *)this + 268) = 0;
  *((_DWORD *)this + 69) = 0;
  *(_QWORD *)((char *)this + 284) = 0;
  *((_QWORD *)this + 48) = 0;
  *((_DWORD *)this + 98) = 0;
  *((_DWORD *)this + 70) = 1;
  *((_DWORD *)this + 64) = 5;
  v10 = (COCInstallHelper *)DirectUI::HAllocAndZero((DirectUI *)0x28, a2);
  if ( !v10 )
  {
    *((_QWORD *)this + 48) = 0;
    goto LABEL_33;
  }
  v11 = COCInstallHelper::COCInstallHelper(v10);
  *((_QWORD *)this + 48) = v11;
  if ( !v11 )
  {
LABEL_33:
    v9 = -2147024882;
    goto LABEL_34;
  }
  ATL::CSimpleStringT<unsigned short,0>::SetString(
    (char *)v11 + 32,
    L"Windows Optional Component Manager Command-Line",
    47);
  v12 = *((_DWORD *)this + 56) == 2;
  *((_DWORD *)this + 98) = 1;
  if ( v12 )
  {
    inited = CFoDWizard::InitFeatureListText(this);
    v9 = inited;
    if ( inited < 0 )
      goto LABEL_26;
    if ( !a4 )
    {
      CFoDWizard::SqmStartSession(this);
      CFoDWizard::SqmRecordCommandLine(this);
      CFoDWizard::SqmRecordUserChoice(this, 3u);
    }
    inited = CFoDWizard::CbsInstallThreadProc(this);
    v9 = inited;
    if ( inited < 0 )
    {
LABEL_26:
      v19 = (unsigned int)inited;
LABEL_35:
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v19);
      goto LABEL_36;
    }
    goto LABEL_30;
  }
  v13 = (_QWORD *)((char *)this + 328);
  EventW = CreateEventW(0, 1, 0, L"CONFIRM_DOWNLOAD_EVENT");
  SH<void *,SH_HANDLE>::Reset((char *)this + 328);
  if ( !EventW )
  {
    *v13 = 0;
    goto LABEL_15;
  }
  *v13 = EventW;
  if ( WTL::CPropertySheetImpl<CFoDWizard,WTL::CPropertySheetWindow>::DoModal(this, a2) >= 0 )
  {
LABEL_30:
    v9 = *((_DWORD *)this + 65);
    if ( v9 >= 0 )
      goto LABEL_36;
    goto LABEL_34;
  }
LABEL_15:
  LastError = GetLastError();
  v16 = LastError < 0;
  if ( LastError > 0 )
    v16 = 1;
  if ( !v16 )
  {
    v9 = -2147467259;
    goto LABEL_34;
  }
  v17 = GetLastError();
  v9 = v17;
  if ( v17 > 0 )
    v9 = (unsigned __int16)v17 | 0x80070000;
  if ( v9 < 0 )
    goto LABEL_34;
LABEL_36:
  *a5 = *((_DWORD *)this + 66);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v9);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180029208  push    rbx
0x18002920a  push    rbp
0x18002920b  push    rsi
0x18002920c  push    rdi
0x18002920d  push    r14
0x18002920f  sub     rsp, 20h
0x180029213  mov     rdi, rcx
0x180029216  xor     r14d, r14d
0x180029219  add     rcx, 0C0h; this
0x180029220  mov     esi, r9d
0x180029223  mov     rbp, rdx
0x180029226  cmp     [rcx], r14d
0x180029229  jnz     short loc_180029256
0x18002922b  mov     rdx, r8; unsigned __int16 *
0x18002922e  call    ?Parse@CFoDCommandLineOptions@@QEAAJPEBGHH@Z; CFoDCommandLineOptions::Parse(ushort const *,int,int)
0x180029233  mov     ebx, eax
0x180029235  cmp     eax, 80070057h
0x18002923a  jnz     short loc_18002924E
0x18002923c  test    esi, esi
0x18002923e  jnz     loc_1800293DC
0x180029244  call    ?ShowHelpMessage@@YAXXZ; ShowHelpMessage(void)
0x180029249  jmp     loc_1800293DC
0x18002924e  test    ebx, ebx
0x180029250  js      loc_1800293DC
0x180029256  cmp     [rdi+0E4h], r14d
0x18002925d  jz      short loc_18002927A
0x18002925f  test    esi, esi
0x180029261  jnz     short loc_180029270
0x180029263  call    ?ShowHelpMessage@@YAXXZ; ShowHelpMessage(void)
0x180029268  mov     ebx, r14d
0x18002926b  jmp     loc_1800293E3
0x180029270  mov     ebx, 80070057h
0x180029275  jmp     loc_1800293DC
0x18002927a  mov     ebx, 1
0x18002927f  mov     [rdi+0F8h], r14
0x180029286  mov     [rdi+104h], r14
0x18002928d  mov     [rdi+10Ch], r14
0x180029294  mov     [rdi+114h], r14d
0x18002929b  lea     ecx, [rbx+27h]; this
0x18002929e  mov     [rdi+11Ch], r14
0x1800292a5  mov     [rdi+180h], r14
0x1800292ac  mov     [rdi+188h], r14d
0x1800292b3  mov     [rdi+118h], ebx
0x1800292b9  mov     dword ptr [rdi+100h], 5
0x1800292c3  call    ?HAllocAndZero@DirectUI@@YAPEAX_K@Z; DirectUI::HAllocAndZero(unsigned __int64)
0x1800292c8  test    rax, rax
0x1800292cb  jz      loc_1800293D0
0x1800292d1  mov     rcx, rax; this
0x1800292d4  call    ??0COCInstallHelper@@QEAA@XZ; COCInstallHelper::COCInstallHelper(void)
0x1800292d9  mov     [rdi+180h], rax
0x1800292e0  test    rax, rax
0x1800292e3  jz      loc_1800293D7
0x1800292e9  lea     rcx, [rax+20h]
0x1800292ed  lea     r8d, [rbx+2Eh]
0x1800292f1  lea     rdx, aWindowsOptiona; "Windows Optional Component Manager Comm"...
0x1800292f8  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1800292fd  cmp     dword ptr [rdi+0E0h], 2
0x180029304  mov     [rdi+188h], ebx
0x18002930a  jz      short loc_180029385
0x18002930c  lea     r9, aConfirmDownloa; "CONFIRM_DOWNLOAD_EVENT"
0x180029313  xor     r8d, r8d; bInitialState
0x180029316  mov     edx, ebx; bManualReset
0x180029318  xor     ecx, ecx; lpEventAttributes
0x18002931a  call    cs:__imp_CreateEventW
0x180029320  lea     rbx, [rdi+148h]
0x180029327  mov     rsi, rax
0x18002932a  mov     rcx, rbx
0x18002932d  call    ?Reset@?$SH@PEAXVSH_HANDLE@@@@QEAAXXZ; SH<void *,SH_HANDLE>::Reset(void)
0x180029332  test    rsi, rsi
0x180029335  jnz     short loc_180029370
0x180029337  mov     [rbx], r14
0x18002933a  call    cs:__imp_GetLastError
0x180029340  mov     esi, 80070000h
0x180029345  test    eax, eax
0x180029347  jle     short loc_180029350
0x180029349  movzx   eax, ax
0x18002934c  or      eax, esi
0x18002934e  test    eax, eax
0x180029350  jns     short loc_180029369
0x180029352  call    cs:__imp_GetLastError
0x180029358  mov     ebx, eax
0x18002935a  test    eax, eax
0x18002935c  jle     short loc_180029363
0x18002935e  movzx   ebx, ax
0x180029361  or      ebx, esi
0x180029363  test    ebx, ebx
0x180029365  js      short loc_1800293DC
0x180029367  jmp     short loc_1800293E3
0x180029369  mov     ebx, 80004005h
0x18002936e  jmp     short loc_1800293DC
0x180029370  mov     rdx, rbp
0x180029373  mov     [rbx], rsi
0x180029376  mov     rcx, rdi
0x180029379  call    ?DoModal@?$CPropertySheetImpl@VCFoDWizard@@VCPropertySheetWindow@WTL@@@WTL@@QEAA_JPEAUHWND__@@@Z; WTL::CPropertySheetImpl<CFoDWizard,WTL::CPropertySheetWindow>::DoModal(HWND__ *)
0x18002937e  test    rax, rax
0x180029381  jns     short loc_1800293C4
0x180029383  jmp     short loc_18002933A
0x180029385  mov     rcx, rdi; this
0x180029388  call    ?InitFeatureListText@CFoDWizard@@AEAAJXZ; CFoDWizard::InitFeatureListText(void)
0x18002938d  mov     ebx, eax
0x18002938f  test    eax, eax
0x180029391  jns     short loc_180029397
0x180029393  mov     ecx, eax
0x180029395  jmp     short loc_1800293DE
0x180029397  test    esi, esi
0x180029399  jnz     short loc_1800293B6
0x18002939b  mov     rcx, rdi; this
0x18002939e  call    ?SqmStartSession@CFoDWizard@@QEAAJXZ; CFoDWizard::SqmStartSession(void)
0x1800293a3  mov     rcx, rdi; this
0x1800293a6  call    ?SqmRecordCommandLine@CFoDWizard@@QEAAJXZ; CFoDWizard::SqmRecordCommandLine(void)
0x1800293ab  lea     edx, [rsi+3]; unsigned int
0x1800293ae  mov     rcx, rdi; this
0x1800293b1  call    ?SqmRecordUserChoice@CFoDWizard@@QEAAJK@Z; CFoDWizard::SqmRecordUserChoice(ulong)
0x1800293b6  mov     rcx, rdi; Parameter
0x1800293b9  call    ?CbsInstallThreadProc@CFoDWizard@@CAKPEAX@Z; CFoDWizard::CbsInstallThreadProc(void *)
0x1800293be  mov     ebx, eax
0x1800293c0  test    eax, eax
0x1800293c2  js      short loc_180029393
0x1800293c4  mov     ebx, [rdi+104h]
0x1800293ca  test    ebx, ebx
0x1800293cc  jns     short loc_1800293E3
0x1800293ce  jmp     short loc_1800293DC
0x1800293d0  mov     [rdi+180h], r14
0x1800293d7  mov     ebx, 8007000Eh
0x1800293dc  mov     ecx, ebx
0x1800293de  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800293e3  mov     ecx, [rdi+108h]
0x1800293e9  mov     rax, [rsp+48h+arg_20]
0x1800293ee  mov     [rax], ecx
0x1800293f0  mov     ecx, ebx
0x1800293f2  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800293f7  mov     eax, ebx
0x1800293f9  add     rsp, 20h
0x1800293fd  pop     r14
0x1800293ff  pop     rdi
0x180029400  pop     rsi
0x180029401  pop     rbp
0x180029402  pop     rbx
0x180029403  retn
```
