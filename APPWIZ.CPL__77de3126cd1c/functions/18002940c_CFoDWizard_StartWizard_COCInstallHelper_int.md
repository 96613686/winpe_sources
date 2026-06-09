# CFoDWizard::StartWizard(COCInstallHelper *,int &)

- ea: `0x18002940c`
- end: `0x180029566`
- name: `?StartWizard@CFoDWizard@@QEAAJPEAVCOCInstallHelper@@AEAH@Z`
- size: `346`
- prototype: `__int64 __fastcall(CFoDWizard *__hidden this, struct COCInstallHelper *, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180032a90`

## callees

- `0x1800227c8`
- `0x180022c94`
- `0x180022e20`
- `0x180024c44`
- `0x180027f18`
- `0x180028610`
- `0x18002940c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800294c4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800294c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800294e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800294fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800294e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800294fc`
- `USER32!GetActiveWindow` at `0x180029548`
- `USER32!GetActiveWindow` at `0x180029548`

## string_xrefs

- `0x180029493`: `Windows Optional Component Manager`

## pseudocode

```c
__int64 __fastcall CFoDWizard::StartWizard(CFoDWizard *this, struct COCInstallHelper *a2, int *a3)
{
  int *v3; // rdi
  unsigned int v6; // ebx
  _QWORD *v7; // r14
  _DWORD *v8; // rsi
  _QWORD *v9; // rbx
  HANDLE EventW; // r15
  signed int LastError; // eax
  bool v12; // sf
  signed int v13; // eax
  HWND ActiveWindow; // rax

  v3 = (int *)((char *)this + 264);
  if ( a2 )
  {
    v7 = (_QWORD *)((char *)this + 384);
    *((_QWORD *)this + 31) = 0;
    v8 = (_DWORD *)((char *)this + 392);
    *((_QWORD *)this + 32) = 5;
    *(_QWORD *)((char *)this + 268) = 0;
    *(_QWORD *)((char *)this + 276) = 0;
    *(_QWORD *)((char *)this + 284) = 0;
    *((_QWORD *)this + 48) = a2;
    *v3 = 0;
    *((_DWORD *)this + 98) = 0;
    ATL::CSimpleStringT<unsigned short,0>::SetString((char *)a2 + 32, L"Windows Optional Component Manager", 34);
    *v8 = 0;
    CFoDCommandLineOptions::InitOptions((char *)this + 192);
    v9 = (_QWORD *)((char *)this + 328);
    EventW = CreateEventW(0, 1, 0, L"CONFIRM_DOWNLOAD_EVENT");
    SH<void *,SH_HANDLE>::Reset((char *)this + 328);
    if ( EventW )
    {
      *v9 = EventW;
      ActiveWindow = GetActiveWindow();
      if ( WTL::CPropertySheetImpl<CFoDWizard,WTL::CPropertySheetWindow>::DoModal(this, ActiveWindow) >= 0 )
      {
        v6 = *((_DWORD *)this + 65);
        goto LABEL_10;
      }
    }
    else
    {
      *v9 = 0;
    }
    LastError = GetLastError();
    v12 = LastError < 0;
    if ( LastError > 0 )
      v12 = 1;
    if ( !v12 )
    {
      v6 = -2147467259;
      goto LABEL_11;
    }
    v13 = GetLastError();
    v6 = v13;
    if ( v13 > 0 )
      v6 = (unsigned __int16)v13 | 0x80070000;
LABEL_10:
    if ( (v6 & 0x80000000) == 0 )
      goto LABEL_12;
LABEL_11:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v6);
    goto LABEL_12;
  }
  v6 = -2147024809;
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942487LL);
  v7 = (_QWORD *)((char *)this + 384);
  v8 = (_DWORD *)((char *)this + 392);
LABEL_12:
  *a3 = *v3;
  *v7 = 0;
  *v8 = 0;
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v6);
  return v6;
}

```

## disassembly

```asm
0x18002940c  push    rbx
0x18002940e  push    rbp
0x18002940f  push    rsi
0x180029410  push    rdi
0x180029411  push    r12
0x180029413  push    r13
0x180029415  push    r14
0x180029417  push    r15
0x180029419  sub     rsp, 28h
0x18002941d  xor     r13d, r13d
0x180029420  lea     rdi, [rcx+108h]
0x180029427  mov     r12, r8
0x18002942a  mov     rbp, rcx
0x18002942d  test    rdx, rdx
0x180029430  jnz     short loc_180029451
0x180029432  mov     ebx, 80070057h
0x180029437  mov     ecx, ebx
0x180029439  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18002943e  lea     r14, [rbp+180h]
0x180029445  lea     rsi, [rbp+188h]
0x18002944c  jmp     loc_180029518
0x180029451  lea     r14, [rcx+180h]
0x180029458  mov     [rcx+0F8h], r13
0x18002945f  lea     rsi, [rcx+188h]
0x180029466  mov     qword ptr [rcx+100h], 5
0x180029471  mov     [rcx+10Ch], r13
0x180029478  mov     r8d, 22h ; '"'
0x18002947e  mov     [rcx+114h], r13
0x180029485  mov     [rcx+11Ch], r13
0x18002948c  lea     rcx, [rdx+20h]
0x180029490  mov     [r14], rdx
0x180029493  lea     rdx, aWindowsOptiona_0; "Windows Optional Component Manager"
0x18002949a  mov     [rdi], r13d
0x18002949d  mov     [rsi], r13d
0x1800294a0  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1800294a5  lea     rcx, [rbp+0C0h]
0x1800294ac  mov     [rsi], r13d
0x1800294af  call    ?InitOptions@CFoDCommandLineOptions@@QEAAJW4HideUxOption@@HH@Z; CFoDCommandLineOptions::InitOptions(HideUxOption,int,int)
0x1800294b4  xor     r8d, r8d; bInitialState
0x1800294b7  lea     r9, aConfirmDownloa; "CONFIRM_DOWNLOAD_EVENT"
0x1800294be  xor     ecx, ecx; lpEventAttributes
0x1800294c0  lea     edx, [r8+1]; bManualReset
0x1800294c4  call    cs:__imp_CreateEventW
0x1800294ca  lea     rbx, [rbp+148h]
0x1800294d1  mov     r15, rax
0x1800294d4  mov     rcx, rbx
0x1800294d7  call    ?Reset@?$SH@PEAXVSH_HANDLE@@@@QEAAXXZ; SH<void *,SH_HANDLE>::Reset(void)
0x1800294dc  test    r15, r15
0x1800294df  jnz     short loc_180029545
0x1800294e1  mov     [rbx], r13
0x1800294e4  call    cs:__imp_GetLastError
0x1800294ea  mov     ebp, 80070000h
0x1800294ef  test    eax, eax
0x1800294f1  jle     short loc_1800294FA
0x1800294f3  movzx   eax, ax
0x1800294f6  or      eax, ebp
0x1800294f8  test    eax, eax
0x1800294fa  jns     short loc_18002953E
0x1800294fc  call    cs:__imp_GetLastError
0x180029502  mov     ebx, eax
0x180029504  test    eax, eax
0x180029506  jle     short loc_18002950D
0x180029508  movzx   ebx, ax
0x18002950b  or      ebx, ebp
0x18002950d  test    ebx, ebx
0x18002950f  jns     short loc_180029518
0x180029511  mov     ecx, ebx
0x180029513  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180029518  mov     ecx, [rdi]
0x18002951a  mov     [r12], ecx
0x18002951e  mov     ecx, ebx
0x180029520  mov     [r14], r13
0x180029523  mov     [rsi], r13d
0x180029526  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002952b  mov     eax, ebx
0x18002952d  add     rsp, 28h
0x180029531  pop     r15
0x180029533  pop     r14
0x180029535  pop     r13
0x180029537  pop     r12
0x180029539  pop     rdi
0x18002953a  pop     rsi
0x18002953b  pop     rbp
0x18002953c  pop     rbx
0x18002953d  retn
0x18002953e  mov     ebx, 80004005h
0x180029543  jmp     short loc_180029511
0x180029545  mov     [rbx], r15
0x180029548  call    cs:__imp_GetActiveWindow
0x18002954e  mov     rdx, rax
0x180029551  mov     rcx, rbp
0x180029554  call    ?DoModal@?$CPropertySheetImpl@VCFoDWizard@@VCPropertySheetWindow@WTL@@@WTL@@QEAA_JPEAUHWND__@@@Z; WTL::CPropertySheetImpl<CFoDWizard,WTL::CPropertySheetWindow>::DoModal(HWND__ *)
0x180029559  test    rax, rax
0x18002955c  js      short loc_1800294E4
0x18002955e  mov     ebx, [rbp+104h]
0x180029564  jmp     short loc_18002950D
```
