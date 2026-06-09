# StartList::Start(Accommodation *,void *,int,int)

- ea: `0x140010244`
- end: `0x14001070c`
- name: `?Start@StartList@@QEAAJPEAVAccommodation@@PEAXHH@Z`
- size: `1224`
- prototype: `Start *__fastcall(Start *this, const wchar_t **, void *, int, int)`
- caller_count: `5`
- callee_count: `22`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400048b8`
- `0x14000b250`
- `0x140010244`
- `0x140010714`
- `0x140010960`

## callees

- `0x1400053cc`
- `0x140006a78`
- `0x14000bd60`
- `0x14000bdf4`
- `0x14000c340`
- `0x14000c420`
- `0x14000ced0`
- `0x14000cfd0`
- `0x14000d498`
- `0x14000d778`
- `0x14000ee8c`
- `0x14000f9c0`
- `0x14000fe74`
- `0x140010194`
- `0x140010244`
- `0x1400116c4`
- `0x140012640`
- `0x1400143ac`
- `0x140015644`
- `0x1400157f8`
- `0x140015ace`
- `0x140017010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x140010500`
- `KERNEL32!CloseHandle` at `0x140010500`
- `KERNEL32!IsProcessInJob` at `0x1400104f4`
- `KERNEL32!IsProcessInJob` at `0x1400104f4`
- `KERNEL32!OpenJobObjectW` at `0x1400104d0`
- `KERNEL32!OpenJobObjectW` at `0x1400104d0`
- `KERNEL32!GetCurrentProcess` at `0x1400104e1`
- `KERNEL32!GetCurrentProcess` at `0x1400104e1`
- `msvcrt!_wtoi` at `0x14001032a`
- `msvcrt!_wtoi` at `0x14001032a`
- `msvcrt!wcsrchr` at `0x1400105ba`
- `msvcrt!wcsrchr` at `0x1400105ba`
- `ntdll!WinSqmAddToStream` at `0x140010609`
- `ntdll!WinSqmAddToStream` at `0x140010609`
- `ntdll!WinSqmIsOptedIn` at `0x14001059f`
- `ntdll!WinSqmIsOptedIn` at `0x14001059f`

## string_xrefs

- `0x1400104c4`: `WinlogonAccess`

## pseudocode

```c
Start *__fastcall StartList::Start(Start *this, const wchar_t **a2, void *a3, int a4, int a5)
{
  BOOL v8; // r15d
  char v9; // r12
  Start *result; // rax
  unsigned int v11; // edi
  struct Accommodation *v12; // rax
  int v13; // eax
  const unsigned __int16 *v14; // r14
  unsigned int v15; // eax
  __int64 v16; // rax
  _BYTE *v17; // r11
  __int64 v18; // rax
  volatile signed __int32 *v19; // r11
  __int64 v20; // r15
  volatile signed __int32 *v21; // rbx
  StartList *v22; // rcx
  HANDLE v23; // rdi
  HANDLE CurrentProcess; // rax
  int ATProcess; // eax
  const wchar_t *v26; // r14
  wchar_t *v27; // rax
  const wchar_t *v28; // rcx
  __int64 v29; // rax
  volatile signed __int32 *v30; // r11
  __int64 v31; // r15
  volatile signed __int32 *v32; // r15
  __int128 v33; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v34[416]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE *Result; // [rsp+200h] [rbp+100h] BYREF

  HIDWORD(Result) = HIDWORD(a3);
  v8 = 0;
  v9 = 0;
  LODWORD(Result) = 0;
  if ( !a2 )
    return (Start *)2147942487LL;
  result = (Start *)StartList::LoadSettings(this);
  v11 = (unsigned int)result;
  if ( (int)result >= 0 )
  {
    if ( (unsigned __int8)ATL::operator!=(a2 + 9) && !IsInteractiveUser() )
    {
      if ( CATUtils::IsDesktopOOBEUserSessionActive() && !wcscmp_0(a2[5], L"SystemSetting") )
        StartList::Add(this, (struct Accommodation *)a2);
      v12 = Accommodation::Open(a2[9]);
      if ( v12 )
        return (Start *)StartList::Start(this, v12, 0, 0, 0);
      else
        return (Start *)2147942414LL;
    }
    v13 = wcscmp_0(a2[5], L"SystemSetting");
    v14 = a2[3];
    if ( !v13 )
    {
      v15 = _wtoi(a2[3]);
      if ( v15 < 0x16 )
      {
        v11 = SystemSettings::TurnOn(a2, v15, 0, *((unsigned int *)this + 73));
        if ( (v11 & 0x80000000) == 0 )
        {
          if ( IsInteractiveUser() )
          {
            v16 = ATL::CSimpleStringT<unsigned short,0>::CloneData(*a2 - 12);
            v9 = 1;
            if ( ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::Find(
                   this,
                   v16 + 24) )
            {
              LOBYTE(v8) = 1;
            }
          }
          else
          {
            v17 = Result;
          }
          if ( (v9 & 1) != 0 && _InterlockedDecrement((volatile signed __int32 *)v17 - 2) <= 0 )
            (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v17 - 3) + 8LL))(*((_QWORD *)v17 - 3));
          if ( v8 )
          {
            v18 = ATL::CSimpleStringT<unsigned short,0>::CloneData(*a2 - 12);
            v20 = ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::Find(
                    (char *)this + 48,
                    v18 + 24);
            if ( _InterlockedDecrement(v19 + 4) <= 0 )
              (*(void (__fastcall **)(_QWORD, volatile signed __int32 *))(**(_QWORD **)v19 + 8LL))(*(_QWORD *)v19, v19);
            if ( !v20 )
            {
              v21 = (volatile signed __int32 *)ATL::CSimpleStringT<unsigned short,0>::CloneData(*a2 - 12);
              Result = v21 + 6;
              ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::AddTail(
                (char *)this + 48,
                v21 + 6);
              if ( _InterlockedDecrement(v21 + 4) <= 0 )
                (*(void (__fastcall **)(_QWORD, volatile signed __int32 *))(**(_QWORD **)v21 + 8LL))(
                  *(_QWORD *)v21,
                  v21);
            }
            StartList::SaveSessionKey(this);
          }
          else if ( CATUtils::IsDesktopOOBEUserSessionActive() )
          {
            StartList::Add(this, (struct Accommodation *)a2);
          }
        }
      }
      return (Start *)v11;
    }
    if ( !v14 )
      return (Start *)2147500037LL;
    if ( a5 || !wcscmp_0(*a2, L"colorfiltering") )
    {
      if ( !wcscmp_0(*a2, L"colorfiltering") )
        ColorFiltering::ColorFilterHelper::UpdateActiveFilter();
    }
    else
    {
      if ( IsInteractiveUser() )
      {
        LODWORD(Result) = 0;
        v23 = OpenJobObjectW(4u, 0, L"WinlogonAccess");
        if ( v23 )
        {
          CurrentProcess = GetCurrentProcess();
          v8 = IsProcessInJob(CurrentProcess, v23, (PBOOL)&Result);
          CloseHandle(v23);
        }
        if ( !(_DWORD)Result || !v8 )
        {
          if ( *((_DWORD *)a2 + 16) )
          {
            StartList::SetTempValueToStart(v22, (struct Accommodation *)a2);
            SendWinkeyPlusU();
          }
          else if ( a4 )
          {
            StartList::CreateBreakawayATProcess(v22, (struct Accommodation *)a2, 1);
          }
          else
          {
            StartList::CreateATProcess(v22, v14, (struct Accommodation *)a2);
          }
          return 0;
        }
      }
      if ( *((_DWORD *)a2 + 16) || !IsInteractiveUser() )
        ATProcess = StartList::CreateATProcess(v22, v14, (struct Accommodation *)a2);
      else
        ATProcess = StartList::CreateBreakawayATProcess(v22, (struct Accommodation *)a2, 0);
      v11 = ATProcess;
      if ( ATProcess < 0 )
        return (Start *)v11;
    }
    if ( (unsigned int)WinSqmIsOptedIn() )
    {
      v26 = a2[3];
      if ( v26 )
      {
        v27 = wcsrchr(a2[3], 0x5Cu);
        v28 = v27 + 1;
        if ( !v27 )
          v28 = v26;
        v33 = 0;
        if ( v28 && *v28 )
          *((_QWORD *)&v33 + 1) = v28;
        else
          *((_QWORD *)&v33 + 1) = L"(null)";
        LODWORD(v33) = 2;
        WinSqmAddToStream(0, 4221, 1, &v33);
      }
    }
    if ( IsInteractiveUser() )
    {
      v29 = ATL::CSimpleStringT<unsigned short,0>::CloneData(*a2 - 12);
      v31 = ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::Find(
              (char *)this + 48,
              v29 + 24);
      if ( _InterlockedDecrement(v30 + 4) <= 0 )
        (*(void (__fastcall **)(_QWORD, volatile signed __int32 *))(**(_QWORD **)v30 + 8LL))(*(_QWORD *)v30, v30);
      if ( !v31 )
      {
        v32 = (volatile signed __int32 *)ATL::CSimpleStringT<unsigned short,0>::CloneData(*a2 - 12);
        Result = v32 + 6;
        ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::AddTail(
          (char *)this + 48,
          v32 + 6);
        if ( _InterlockedDecrement(v32 + 4) <= 0 )
          (*(void (__fastcall **)(_QWORD, volatile signed __int32 *))(**(_QWORD **)v32 + 8LL))(*(_QWORD *)v32, v32);
      }
      StartList::SaveSessionKey(this);
      if ( *((_DWORD *)a2 + 17) || !*((_DWORD *)a2 + 16) )
      {
        ATManager::ATManager((ATManager *)v34, 1);
        Result = v34;
        SettingsCopier::InteractiveDesktopCopy((SettingsCopier *)&Result);
        ATManager::~ATManager((ATManager *)v34);
      }
    }
    return (Start *)v11;
  }
  return result;
}

```

## disassembly

```asm
0x140010244  mov     [rsp-8+Result], r8
0x140010249  push    rbp
0x14001024a  push    rbx
0x14001024b  push    rsi
0x14001024c  push    rdi
0x14001024d  push    r12
0x14001024f  push    r13
0x140010251  push    r14
0x140010253  push    r15
0x140010255  lea     rbp, [rsp-0A8h]
0x14001025d  sub     rsp, 1A8h
0x140010264  mov     r13d, r9d
0x140010267  mov     rbx, rdx
0x14001026a  mov     rsi, rcx
0x14001026d  xor     r15d, r15d
0x140010270  mov     r12d, r15d
0x140010273  mov     dword ptr [rbp+0E0h+Result], r15d
0x14001027a  test    rdx, rdx
0x14001027d  jnz     short loc_140010289
0x14001027f  mov     eax, 80070057h
0x140010284  jmp     loc_1400106F8
0x140010289  call    ?LoadSettings@StartList@@AEAAJXZ; StartList::LoadSettings(void)
0x14001028e  mov     edi, eax
0x140010290  test    eax, eax
0x140010292  js      loc_1400106F8
0x140010298  lea     rcx, [rbx+48h]
0x14001029c  call    ??9ATL@@YA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@0@PEBD@Z; ATL::operator!=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,char const *)
0x1400102a1  test    al, al
0x1400102a3  jz      short loc_14001030A
0x1400102a5  call    ?IsInteractiveUser@@YAHXZ; IsInteractiveUser(void)
0x1400102aa  test    eax, eax
0x1400102ac  jnz     short loc_14001030A
0x1400102ae  call    ?IsDesktopOOBEUserSessionActive@CATUtils@@SA_NXZ; CATUtils::IsDesktopOOBEUserSessionActive(void)
0x1400102b3  test    al, al
0x1400102b5  jz      short loc_1400102D7
0x1400102b7  lea     rdx, aSystemsetting; "SystemSetting"
0x1400102be  mov     rcx, [rbx+28h]; String1
0x1400102c2  call    wcscmp_0
0x1400102c7  nop
0x1400102c8  test    eax, eax
0x1400102ca  jnz     short loc_1400102D7
0x1400102cc  mov     rdx, rbx; struct Accommodation *
0x1400102cf  mov     rcx, rsi; this
0x1400102d2  call    ?Add@StartList@@QEAAJPEAVAccommodation@@@Z; StartList::Add(Accommodation *)
0x1400102d7  mov     rcx, [rbx+48h]; unsigned __int16 *
0x1400102db  call    ?Open@Accommodation@@SAPEAV1@PEBG@Z; Accommodation::Open(ushort const *)
0x1400102e0  test    rax, rax
0x1400102e3  jnz     short loc_1400102EF
0x1400102e5  mov     eax, 8007000Eh
0x1400102ea  jmp     loc_1400106F8
0x1400102ef  mov     [rsp+1E0h+var_1C0], r15d; int
0x1400102f4  xor     r9d, r9d; int
0x1400102f7  xor     r8d, r8d; void *
0x1400102fa  mov     rdx, rax; struct Accommodation *
0x1400102fd  mov     rcx, rsi; this
0x140010300  call    ?Start@StartList@@QEAAJPEAVAccommodation@@PEAXHH@Z; StartList::Start(Accommodation *,void *,int,int)
0x140010305  jmp     loc_1400106F8
0x14001030a  lea     rdx, aSystemsetting; "SystemSetting"
0x140010311  mov     rcx, [rbx+28h]; String1
0x140010315  call    wcscmp_0
0x14001031a  nop
0x14001031b  mov     r14, [rbx+18h]
0x14001031f  test    eax, eax
0x140010321  jnz     loc_14001047C
0x140010327  mov     rcx, r14; String
0x14001032a  call    cs:__imp__wtoi
0x140010330  cmp     eax, 16h
0x140010333  jnb     loc_1400106F6
0x140010339  mov     r9d, [rsi+124h]
0x140010340  xor     r8d, r8d
0x140010343  mov     edx, eax
0x140010345  mov     rcx, rbx
0x140010348  call    ?TurnOn@SystemSettings@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@IPEAXH@Z; SystemSettings::TurnOn(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,uint,void *,int)
0x14001034d  mov     edi, eax
0x14001034f  test    eax, eax
0x140010351  js      loc_1400106F6
0x140010357  call    ?IsInteractiveUser@@YAHXZ; IsInteractiveUser(void)
0x14001035c  test    eax, eax
0x14001035e  jz      short loc_14001038B
0x140010360  mov     rcx, [rbx]
0x140010363  sub     rcx, 18h
0x140010367  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x14001036c  lea     r11, [rax+18h]
0x140010370  mov     r12d, 1
0x140010376  mov     rdx, r11
0x140010379  mov     rcx, rsi
0x14001037c  call    ?Find@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEBAPEAU__POSITION@@PEBGPEAU3@@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::Find(ushort const *,__POSITION *)
0x140010381  test    rax, rax
0x140010384  jz      short loc_140010392
0x140010386  mov     r15b, r12b
0x140010389  jmp     short loc_140010392
0x14001038b  mov     r11, [rbp+0E0h+Result]
0x140010392  or      r14d, 0FFFFFFFFh
0x140010396  test    r12b, 1
0x14001039a  jz      short loc_1400103BE
0x14001039c  lea     rdx, [r11-18h]
0x1400103a0  mov     eax, r14d
0x1400103a3  lock xadd [rdx+10h], eax
0x1400103a8  add     eax, r14d
0x1400103ab  test    eax, eax
0x1400103ad  jg      short loc_1400103BE
0x1400103af  mov     rcx, [rdx]
0x1400103b2  mov     rax, [rcx]
0x1400103b5  mov     rax, [rax+8]
0x1400103b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400103be  test    r15b, r15b
0x1400103c1  jz      loc_14001045F
0x1400103c7  mov     rcx, [rbx]
0x1400103ca  sub     rcx, 18h
0x1400103ce  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x1400103d3  mov     r11, rax
0x1400103d6  lea     rdx, [rax+18h]
0x1400103da  lea     rcx, [rsi+30h]
0x1400103de  call    ?Find@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEBAPEAU__POSITION@@PEBGPEAU3@@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::Find(ushort const *,__POSITION *)
0x1400103e3  mov     r15, rax
0x1400103e6  mov     ecx, r14d
0x1400103e9  lock xadd [r11+10h], ecx
0x1400103ef  add     ecx, r14d
0x1400103f2  test    ecx, ecx
0x1400103f4  jg      short loc_140010408
0x1400103f6  mov     rcx, [r11]
0x1400103f9  mov     rdx, [rcx]
0x1400103fc  mov     rax, [rdx+8]
0x140010400  mov     rdx, r11
0x140010403  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010408  test    r15, r15
0x14001040b  jnz     short loc_140010452
0x14001040d  mov     rcx, [rbx]
0x140010410  sub     rcx, 18h
0x140010414  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x140010419  mov     rbx, rax
0x14001041c  lea     rdx, [rax+18h]
0x140010420  mov     [rbp+0E0h+Result], rdx
0x140010427  lea     rcx, [rsi+30h]
0x14001042b  call    ?AddTail@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAPEAU__POSITION@@PEBG@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::AddTail(ushort const *)
0x140010430  nop
0x140010431  mov     ecx, r14d
0x140010434  lock xadd [rbx+10h], ecx
0x140010439  add     ecx, r14d
0x14001043c  test    ecx, ecx
0x14001043e  jg      short loc_140010452
0x140010440  mov     rcx, [rbx]
0x140010443  mov     rax, [rcx]
0x140010446  mov     rdx, rbx
0x140010449  mov     rax, [rax+8]
0x14001044d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010452  mov     rcx, rsi; this
0x140010455  call    ?SaveSessionKey@StartList@@AEAAXXZ; StartList::SaveSessionKey(void)
0x14001045a  jmp     loc_1400106F6
0x14001045f  call    ?IsDesktopOOBEUserSessionActive@CATUtils@@SA_NXZ; CATUtils::IsDesktopOOBEUserSessionActive(void)
0x140010464  test    al, al
0x140010466  jz      loc_1400106F6
0x14001046c  mov     rdx, rbx; struct Accommodation *
0x14001046f  mov     rcx, rsi; this
0x140010472  call    ?Add@StartList@@QEAAJPEAVAccommodation@@@Z; StartList::Add(Accommodation *)
0x140010477  jmp     loc_1400106F6
0x14001047c  test    r14, r14
0x14001047f  jnz     short loc_14001048B
0x140010481  mov     eax, 80004005h
0x140010486  jmp     loc_1400106F8
0x14001048b  cmp     [rbp+0E0h+arg_20], r15d
0x140010492  jnz     loc_140010586
0x140010498  lea     rdx, aColorfiltering_0; "colorfiltering"
0x14001049f  mov     rcx, [rbx]; String1
0x1400104a2  call    wcscmp_0
0x1400104a7  nop
0x1400104a8  test    eax, eax
0x1400104aa  jz      loc_140010586
0x1400104b0  call    ?IsInteractiveUser@@YAHXZ; IsInteractiveUser(void)
0x1400104b5  test    eax, eax
0x1400104b7  jz      loc_140010553
0x1400104bd  mov     dword ptr [rbp+0E0h+Result], r15d
0x1400104c4  lea     r8, aWinlogonaccess; "WinlogonAccess"
0x1400104cb  xor     edx, edx; bInheritHandle
0x1400104cd  lea     ecx, [rdx+4]; dwDesiredAccess
0x1400104d0  call    cs:__imp_OpenJobObjectW
0x1400104d6  mov     rdi, rax
0x1400104d9  xor     r12d, r12d
0x1400104dc  test    rax, rax
0x1400104df  jz      short loc_140010506
0x1400104e1  call    cs:__imp_GetCurrentProcess
0x1400104e7  lea     r8, [rbp+0E0h+Result]; Result
0x1400104ee  mov     rdx, rdi; JobHandle
0x1400104f1  mov     rcx, rax; ProcessHandle
0x1400104f4  call    cs:__imp_IsProcessInJob
0x1400104fa  mov     r15d, eax
0x1400104fd  mov     rcx, rdi; hObject
0x140010500  call    cs:__imp_CloseHandle
0x140010506  cmp     dword ptr [rbp+0E0h+Result], r12d
0x14001050d  jz      short loc_140010514
0x14001050f  test    r15d, r15d
0x140010512  jnz     short loc_140010550
0x140010514  cmp     [rbx+40h], r12d
0x140010518  jnz     short loc_14001053C
0x14001051a  test    r13d, r13d
0x14001051d  jz      short loc_14001052F
0x14001051f  mov     r8d, 1; int
0x140010525  mov     rdx, rbx; struct Accommodation *
0x140010528  call    ?CreateBreakawayATProcess@StartList@@AEAAJPEAVAccommodation@@H@Z; StartList::CreateBreakawayATProcess(Accommodation *,int)
0x14001052d  jmp     short loc_140010549
0x14001052f  mov     r8, rbx; struct Accommodation *
0x140010532  mov     rdx, r14; unsigned __int16 *
0x140010535  call    ?CreateATProcess@StartList@@AEAAJPEBGPEAVAccommodation@@H@Z; StartList::CreateATProcess(ushort const *,Accommodation *,int)
0x14001053a  jmp     short loc_140010549
0x14001053c  mov     rdx, rbx; struct Accommodation *
0x14001053f  call    ?SetTempValueToStart@StartList@@AEAAXPEAVAccommodation@@@Z; StartList::SetTempValueToStart(Accommodation *)
0x140010544  call    ?SendWinkeyPlusU@@YAXXZ; SendWinkeyPlusU(void)
0x140010549  xor     eax, eax
0x14001054b  jmp     loc_1400106F8
0x140010550  xor     r15d, r15d
0x140010553  cmp     [rbx+40h], r15d
0x140010557  jnz     short loc_14001056F
0x140010559  call    ?IsInteractiveUser@@YAHXZ; IsInteractiveUser(void)
0x14001055e  test    eax, eax
0x140010560  jz      short loc_14001056F
0x140010562  xor     r8d, r8d; int
0x140010565  mov     rdx, rbx; struct Accommodation *
0x140010568  call    ?CreateBreakawayATProcess@StartList@@AEAAJPEAVAccommodation@@H@Z; StartList::CreateBreakawayATProcess(Accommodation *,int)
0x14001056d  jmp     short loc_14001057A
0x14001056f  mov     r8, rbx; struct Accommodation *
0x140010572  mov     rdx, r14; unsigned __int16 *
0x140010575  call    ?CreateATProcess@StartList@@AEAAJPEBGPEAVAccommodation@@H@Z; StartList::CreateATProcess(ushort const *,Accommodation *,int)
0x14001057a  mov     edi, eax
0x14001057c  test    eax, eax
0x14001057e  js      loc_1400106F6
0x140010584  jmp     short loc_14001059F
0x140010586  lea     rdx, aColorfiltering_0; "colorfiltering"
0x14001058d  mov     rcx, [rbx]; String1
0x140010590  call    wcscmp_0
0x140010595  nop
0x140010596  test    eax, eax
0x140010598  jnz     short loc_14001059F
0x14001059a  call    ?UpdateActiveFilter@ColorFilterHelper@ColorFiltering@@SAXXZ; ColorFiltering::ColorFilterHelper::UpdateActiveFilter(void)
0x14001059f  call    cs:__imp_WinSqmIsOptedIn
0x1400105a5  test    eax, eax
0x1400105a7  jz      short loc_14001060F
0x1400105a9  mov     r14, [rbx+18h]
0x1400105ad  test    r14, r14
0x1400105b0  jz      short loc_14001060F
0x1400105b2  mov     edx, 5Ch ; '\'; Ch
0x1400105b7  mov     rcx, r14; Str
0x1400105ba  call    cs:__imp_wcsrchr
0x1400105c0  lea     rcx, [rax+2]
0x1400105c4  test    rax, rax
0x1400105c7  cmovz   rcx, r14
0x1400105cb  xorps   xmm0, xmm0
0x1400105ce  movups  [rsp+1E0h+var_1B0], xmm0
0x1400105d3  test    rcx, rcx
0x1400105d6  jz      short loc_1400105E5
0x1400105d8  cmp     [rcx], r15w
0x1400105dc  jz      short loc_1400105E5
0x1400105de  mov     qword ptr [rsp+1E0h+var_1B0+8], rcx
0x1400105e3  jmp     short loc_1400105F1
0x1400105e5  lea     rax, aNull; "(null)"
0x1400105ec  mov     qword ptr [rsp+1E0h+var_1B0+8], rax
0x1400105f1  mov     dword ptr [rsp+1E0h+var_1B0], 2
0x1400105f9  lea     r9, [rsp+1E0h+var_1B0]
0x1400105fe  mov     edx, 107Dh
0x140010603  xor     ecx, ecx
0x140010605  lea     r8d, [rcx+1]
0x140010609  call    cs:__imp_WinSqmAddToStream
0x14001060f  call    ?IsInteractiveUser@@YAHXZ; IsInteractiveUser(void)
0x140010614  test    eax, eax
0x140010616  jz      loc_1400106F6
0x14001061c  mov     rcx, [rbx]
0x14001061f  sub     rcx, 18h
0x140010623  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x140010628  mov     r11, rax
0x14001062b  lea     rdx, [rax+18h]
0x14001062f  lea     rcx, [rsi+30h]
0x140010633  call    ?Find@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEBAPEAU__POSITION@@PEBGPEAU3@@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::Find(ushort const *,__POSITION *)
0x140010638  mov     r15, rax
0x14001063b  or      r14d, 0FFFFFFFFh
0x14001063f  mov     ecx, r14d
0x140010642  lock xadd [r11+10h], ecx
0x140010648  add     ecx, r14d
0x14001064b  xor     r13d, r13d
0x14001064e  test    ecx, ecx
0x140010650  jg      short loc_140010664
0x140010652  mov     rcx, [r11]
0x140010655  mov     rdx, [rcx]
0x140010658  mov     rax, [rdx+8]
0x14001065c  mov     rdx, r11
0x14001065f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010664  test    r15, r15
0x140010667  jnz     short loc_1400106AF
0x140010669  mov     rcx, [rbx]
0x14001066c  sub     rcx, 18h
0x140010670  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x140010675  mov     r15, rax
0x140010678  lea     rdx, [rax+18h]
0x14001067c  mov     [rbp+0E0h+Result], rdx
0x140010683  lea     rcx, [rsi+30h]
0x140010687  call    ?AddTail@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAPEAU__POSITION@@PEBG@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::AddTail(ushort const *)
0x14001068c  nop
0x14001068d  mov     ecx, r14d
0x140010690  lock xadd [r15+10h], ecx
0x140010696  add     ecx, r14d
0x140010699  test    ecx, ecx
0x14001069b  jg      short loc_1400106AF
  ... truncated ...
```
