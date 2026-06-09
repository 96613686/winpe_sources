# StartList::Start(Accommodation *,void *,int,int)

- ea: `0x1800241b0`
- end: `0x1800245c0`
- name: `?Start@StartList@@QEAAJPEAVAccommodation@@PEAXHH@Z`
- size: `1040`
- prototype: `__int64 __fastcall(StartList *__hidden this, struct Accommodation *, void *, int, int)`
- caller_count: `21`
- callee_count: `26`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800143a0`
- `0x180016054`
- `0x180016108`
- `0x1800161f0`
- `0x18001636c`
- `0x180016494`
- `0x180016694`
- `0x180016750`
- `0x180016800`
- `0x180016b44`
- `0x180016ee4`
- `0x180017114`
- `0x1800172b0`
- `0x180017464`
- `0x180017670`
- `0x1800178c0`
- `0x180017cc0`
- `0x180017d78`
- `0x180017eb8`
- `0x18001aab0`
- `0x1800241b0`

## callees

- `0x180005340`
- `0x180005534`
- `0x1800055c0`
- `0x1800057d4`
- `0x1800063c0`
- `0x180015780`
- `0x180018260`
- `0x180020edc`
- `0x1800215c0`
- `0x180021610`
- `0x180021a8c`
- `0x180021d44`
- `0x180022ef4`
- `0x180023090`
- `0x180023518`
- `0x180023bc0`
- `0x180023ef8`
- `0x1800241b0`
- `0x180024fd4`
- `0x180025068`
- `0x180025fdc`
- `0x180027808`
- `0x180029144`
- `0x1800295d4`
- `0x1800295f4`
- `0x18002d1fa`

## import_xrefs

- `msvcrt!_wtoi` at `0x180024290`
- `msvcrt!_wtoi` at `0x180024290`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800243ec`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800243ec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002440b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002440b`
- `KERNEL32!OpenJobObjectW` at `0x1800243de`
- `KERNEL32!OpenJobObjectW` at `0x1800243de`
- `KERNEL32!IsProcessInJob` at `0x1800243ff`
- `KERNEL32!IsProcessInJob` at `0x1800243ff`

## string_xrefs

- `0x18002446f`: `Software\Microsoft\Windows NT\CurrentVersion\AccessibilityTemp`
- `0x1800243d2`: `WinlogonAccess`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
Start *__fastcall StartList::Start(Start *this, const wchar_t **a2, UINT *a3, int a4, int a5)
{
  BOOL v9; // r15d
  Start *result; // rax
  unsigned int v11; // esi
  struct Accommodation *v12; // rax
  int v13; // eax
  StartList *v14; // rcx
  const unsigned __int16 *v15; // rbx
  unsigned int v16; // eax
  __int64 v17; // rax
  _BYTE *v18; // r11
  char v19; // bl
  __int64 v20; // rax
  __int64 v21; // rbx
  ATL::CStringData *v22; // r11
  ATL::CStringData *v23; // rbx
  WCHAR *v24; // rcx
  unsigned __int16 *v25; // r9
  HANDLE v26; // rsi
  HANDLE CurrentProcess; // rax
  int ATProcess; // eax
  StartList *v29; // rcx
  __int64 v30; // rax
  __int64 v31; // rbx
  ATL::CStringData *v32; // r11
  ATL::CStringData *v33; // rbx
  HKEY v34; // [rsp+30h] [rbp-D0h]
  _QWORD v35[4]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v36[416]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE *Result; // [rsp+218h] [rbp+118h] BYREF

  v9 = 0;
  LODWORD(Result) = 0;
  if ( !a2 )
    return (Start *)2147942487LL;
  result = (Start *)StartList::LoadSettings(this);
  v11 = (unsigned int)result;
  if ( (int)result >= 0 )
  {
    if ( (unsigned __int8)ATL::operator!=(a2 + 9) && !(unsigned int)CATUtils::IsInteractiveUser() )
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
    v15 = a2[3];
    if ( !v13 )
    {
      v16 = _wtoi(a2[3]);
      if ( v16 < 0x16 )
      {
        v11 = SystemSettings::TurnOn(a2, v16, a3, *((_DWORD *)this + 73));
        if ( (v11 & 0x80000000) == 0 )
        {
          if ( (unsigned int)CATUtils::IsInteractiveUser() )
          {
            v17 = ATL::CSimpleStringT<unsigned short,0>::CloneData(*a2 - 12);
            LOBYTE(v9) = 1;
            if ( ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::Find(
                   this,
                   v17 + 24) )
            {
              v19 = 1;
LABEL_20:
              if ( v9 )
                ATL::CStringData::Release((ATL::CStringData *)(v18 - 24));
              if ( v19 )
              {
                v20 = ATL::CSimpleStringT<unsigned short,0>::CloneData(*a2 - 12);
                v21 = ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::Find(
                        (char *)this + 48,
                        v20 + 24);
                ATL::CStringData::Release(v22);
                if ( !v21 )
                {
                  v23 = (ATL::CStringData *)ATL::CSimpleStringT<unsigned short,0>::CloneData(*a2 - 12);
                  Result = (char *)v23 + 24;
                  ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::AddTail(
                    (char *)this + 48,
                    (char *)v23 + 24);
                  ATL::CStringData::Release(v23);
                }
                StartList::SaveSessionKey(this);
              }
              else if ( CATUtils::IsDesktopOOBEUserSessionActive() )
              {
                StartList::Add(this, (struct Accommodation *)a2);
              }
              return (Start *)v11;
            }
          }
          else
          {
            v18 = Result;
          }
          v19 = 0;
          goto LABEL_20;
        }
      }
      return (Start *)v11;
    }
    if ( !v15 )
      return (Start *)2147500037LL;
    if ( a5 || StartList::IsColorFiltering(v14, (struct Accommodation *)a2) )
    {
      if ( StartList::IsColorFiltering(v14, (struct Accommodation *)a2) )
        ColorFiltering::ColorFilterHelper::UpdateActiveFilter();
    }
    else
    {
      if ( (unsigned int)CATUtils::IsInteractiveUser() )
      {
        LODWORD(Result) = 0;
        v26 = OpenJobObjectW(4u, 0, L"WinlogonAccess");
        if ( v26 )
        {
          CurrentProcess = GetCurrentProcess();
          v9 = IsProcessInJob(CurrentProcess, v26, (PBOOL)&Result);
          CloseHandle(v26);
        }
        if ( !(_DWORD)Result || !v9 )
        {
          if ( *((_DWORD *)a2 + 16) )
          {
            memset(v35, 0, 24);
            if ( !(unsigned int)ATL::CRegKey::Create(
                                  (ATL::CRegKey *)v35,
                                  HKEY_CURRENT_USER,
                                  L"Software\\Microsoft\\Windows NT\\CurrentVersion\\AccessibilityTemp",
                                  v25,
                                  1u,
                                  0x2001Fu,
                                  v34,
                                  0) )
              ATL::CRegKey::SetDWORDValue((ATL::CRegKey *)v35, *a2, 3u);
            ATL::CRegKey::Close((ATL::CRegKey *)v35);
            SendWinkeyPlusU();
          }
          else if ( a4 )
          {
            StartList::CreateBreakawayATProcess(v24, (struct Accommodation *)a2, 1);
          }
          else
          {
            StartList::CreateATProcess((StartList *)v24, v15, (struct Accommodation *)a2, (int)v25);
          }
          return 0;
        }
      }
      if ( *((_DWORD *)a2 + 16) || !(unsigned int)CATUtils::IsInteractiveUser() )
        ATProcess = StartList::CreateATProcess((StartList *)v24, v15, (struct Accommodation *)a2, (int)v25);
      else
        ATProcess = StartList::CreateBreakawayATProcess(v24, (struct Accommodation *)a2, 0);
      v11 = ATProcess;
      if ( ATProcess < 0 )
        return (Start *)v11;
    }
    StartList::LogAccomodationToSQM(v29, (struct Accommodation *)a2);
    if ( (unsigned int)CATUtils::IsInteractiveUser() )
    {
      v30 = ATL::CSimpleStringT<unsigned short,0>::CloneData(*a2 - 12);
      v31 = ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::Find(
              (char *)this + 48,
              v30 + 24);
      ATL::CStringData::Release(v32);
      if ( !v31 )
      {
        v33 = (ATL::CStringData *)ATL::CSimpleStringT<unsigned short,0>::CloneData(*a2 - 12);
        Result = (char *)v33 + 24;
        ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::AddTail(
          (char *)this + 48,
          (char *)v33 + 24);
        ATL::CStringData::Release(v33);
      }
      StartList::SaveSessionKey(this);
      if ( *((_DWORD *)a2 + 17) || !*((_DWORD *)a2 + 16) )
      {
        ATManager::ATManager((ATManager *)v36, 1);
        Result = v36;
        SettingsCopier::InteractiveDesktopCopy((SettingsCopier *)&Result);
        ATManager::~ATManager((ATManager *)v36);
      }
    }
    return (Start *)v11;
  }
  return result;
}

```

## disassembly

```asm
0x1800241b0  push    rbp
0x1800241b2  push    rbx
0x1800241b3  push    rsi
0x1800241b4  push    rdi
0x1800241b5  push    r12
0x1800241b7  push    r13
0x1800241b9  push    r14
0x1800241bb  push    r15
0x1800241bd  lea     rbp, [rsp-0C8h]
0x1800241c5  sub     rsp, 1C8h
0x1800241cc  mov     r12d, r9d
0x1800241cf  mov     r13, r8
0x1800241d2  mov     rdi, rdx
0x1800241d5  mov     r14, rcx
0x1800241d8  xor     r15d, r15d
0x1800241db  mov     dword ptr [rbp+100h+Result], r15d
0x1800241e2  test    rdx, rdx
0x1800241e5  jnz     short loc_1800241F1
0x1800241e7  mov     eax, 80070057h
0x1800241ec  jmp     loc_1800245AC
0x1800241f1  call    ?LoadSettings@StartList@@AEAAJXZ; StartList::LoadSettings(void)
0x1800241f6  mov     esi, eax
0x1800241f8  test    eax, eax
0x1800241fa  js      loc_1800245AC
0x180024200  lea     rcx, [rdi+48h]
0x180024204  call    ??9ATL@@YA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@0@PEBD@Z; ATL::operator!=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,char const *)
0x180024209  test    al, al
0x18002420b  jz      short loc_180024271
0x18002420d  call    ?IsInteractiveUser@CATUtils@@SAHXZ; CATUtils::IsInteractiveUser(void)
0x180024212  test    eax, eax
0x180024214  jnz     short loc_180024271
0x180024216  call    ?IsDesktopOOBEUserSessionActive@CATUtils@@SA_NXZ; CATUtils::IsDesktopOOBEUserSessionActive(void)
0x18002421b  test    al, al
0x18002421d  jz      short loc_18002423E
0x18002421f  lea     rdx, aSystemsetting; "SystemSetting"
0x180024226  mov     rcx, [rdi+28h]; String1
0x18002422a  call    wcscmp_0
0x18002422f  test    eax, eax
0x180024231  jnz     short loc_18002423E
0x180024233  mov     rdx, rdi; struct Accommodation *
0x180024236  mov     rcx, r14; this
0x180024239  call    ?Add@StartList@@QEAAJPEAVAccommodation@@@Z; StartList::Add(Accommodation *)
0x18002423e  mov     rcx, [rdi+48h]; unsigned __int16 *
0x180024242  call    ?Open@Accommodation@@SAPEAV1@PEBG@Z; Accommodation::Open(ushort const *)
0x180024247  test    rax, rax
0x18002424a  jnz     short loc_180024256
0x18002424c  mov     eax, 8007000Eh
0x180024251  jmp     loc_1800245AC
0x180024256  mov     [rsp+200h+var_1E0], r15d; int
0x18002425b  xor     r9d, r9d; int
0x18002425e  xor     r8d, r8d; void *
0x180024261  mov     rdx, rax; struct Accommodation *
0x180024264  mov     rcx, r14; this
0x180024267  call    ?Start@StartList@@QEAAJPEAVAccommodation@@PEAXHH@Z; StartList::Start(Accommodation *,void *,int,int)
0x18002426c  jmp     loc_1800245AC
0x180024271  lea     rdx, aSystemsetting; "SystemSetting"
0x180024278  mov     rcx, [rdi+28h]; String1
0x18002427c  call    wcscmp_0
0x180024281  mov     rbx, [rdi+18h]
0x180024285  test    eax, eax
0x180024287  jnz     loc_18002438F
0x18002428d  mov     rcx, rbx; String
0x180024290  call    cs:__imp__wtoi
0x180024296  cmp     eax, 16h
0x180024299  jnb     loc_1800245AA
0x18002429f  mov     r9d, [r14+124h]
0x1800242a6  mov     r8, r13
0x1800242a9  mov     edx, eax
0x1800242ab  mov     rcx, rdi
0x1800242ae  call    ?TurnOn@SystemSettings@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@IPEAXH@Z; SystemSettings::TurnOn(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,uint,void *,int)
0x1800242b3  mov     esi, eax
0x1800242b5  test    eax, eax
0x1800242b7  js      loc_1800245AA
0x1800242bd  call    ?IsInteractiveUser@CATUtils@@SAHXZ; CATUtils::IsInteractiveUser(void)
0x1800242c2  test    eax, eax
0x1800242c4  jz      short loc_1800242F1
0x1800242c6  mov     rcx, [rdi]
0x1800242c9  sub     rcx, 18h
0x1800242cd  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x1800242d2  lea     r11, [rax+18h]
0x1800242d6  mov     r15d, 1
0x1800242dc  mov     rdx, r11
0x1800242df  mov     rcx, r14
0x1800242e2  call    ?Find@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEBAPEAU__POSITION@@PEBGPEAU3@@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::Find(ushort const *,__POSITION *)
0x1800242e7  test    rax, rax
0x1800242ea  jz      short loc_1800242F8
0x1800242ec  mov     bl, r15b
0x1800242ef  jmp     short loc_1800242FA
0x1800242f1  mov     r11, [rbp+100h+Result]
0x1800242f8  xor     bl, bl
0x1800242fa  test    r15b, 1
0x1800242fe  jz      short loc_180024309
0x180024300  lea     rcx, [r11-18h]; this
0x180024304  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180024309  test    bl, bl
0x18002430b  jz      short loc_180024372
0x18002430d  mov     rcx, [rdi]
0x180024310  sub     rcx, 18h
0x180024314  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x180024319  mov     r11, rax
0x18002431c  lea     rdx, [rax+18h]
0x180024320  lea     rcx, [r14+30h]
0x180024324  call    ?Find@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEBAPEAU__POSITION@@PEBGPEAU3@@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::Find(ushort const *,__POSITION *)
0x180024329  mov     rbx, rax
0x18002432c  mov     rcx, r11; this
0x18002432f  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180024334  test    rbx, rbx
0x180024337  jnz     short loc_180024365
0x180024339  mov     rcx, [rdi]
0x18002433c  sub     rcx, 18h
0x180024340  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x180024345  mov     rbx, rax
0x180024348  lea     rdx, [rax+18h]
0x18002434c  mov     [rbp+100h+Result], rdx
0x180024353  lea     rcx, [r14+30h]
0x180024357  call    ?AddTail@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAPEAU__POSITION@@PEBG@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::AddTail(ushort const *)
0x18002435c  nop
0x18002435d  mov     rcx, rbx; this
0x180024360  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180024365  mov     rcx, r14; this
0x180024368  call    ?SaveSessionKey@StartList@@AEAAXXZ; StartList::SaveSessionKey(void)
0x18002436d  jmp     loc_1800245AA
0x180024372  call    ?IsDesktopOOBEUserSessionActive@CATUtils@@SA_NXZ; CATUtils::IsDesktopOOBEUserSessionActive(void)
0x180024377  test    al, al
0x180024379  jz      loc_1800245AA
0x18002437f  mov     rdx, rdi; struct Accommodation *
0x180024382  mov     rcx, r14; this
0x180024385  call    ?Add@StartList@@QEAAJPEAVAccommodation@@@Z; StartList::Add(Accommodation *)
0x18002438a  jmp     loc_1800245AA
0x18002438f  xor     r13d, r13d
0x180024392  test    rbx, rbx
0x180024395  jnz     short loc_1800243A1
0x180024397  mov     eax, 80004005h
0x18002439c  jmp     loc_1800245AC
0x1800243a1  cmp     [rbp+100h+arg_20], r13d
0x1800243a8  jnz     loc_1800244E5
0x1800243ae  mov     rdx, rdi; struct Accommodation *
0x1800243b1  call    ?IsColorFiltering@StartList@@AEAA_NPEAVAccommodation@@@Z; StartList::IsColorFiltering(Accommodation *)
0x1800243b6  test    al, al
0x1800243b8  jnz     loc_1800244E5
0x1800243be  call    ?IsInteractiveUser@CATUtils@@SAHXZ; CATUtils::IsInteractiveUser(void)
0x1800243c3  test    eax, eax
0x1800243c5  jz      loc_1800244B2
0x1800243cb  mov     dword ptr [rbp+100h+Result], r13d
0x1800243d2  lea     r8, aWinlogonaccess; "WinlogonAccess"
0x1800243d9  xor     edx, edx; bInheritHandle
0x1800243db  lea     ecx, [rdx+4]; dwDesiredAccess
0x1800243de  call    cs:__imp_OpenJobObjectW
0x1800243e4  mov     rsi, rax
0x1800243e7  test    rax, rax
0x1800243ea  jz      short loc_180024411
0x1800243ec  call    cs:__imp_GetCurrentProcess
0x1800243f2  lea     r8, [rbp+100h+Result]; Result
0x1800243f9  mov     rdx, rsi; JobHandle
0x1800243fc  mov     rcx, rax; ProcessHandle
0x1800243ff  call    cs:__imp_IsProcessInJob
0x180024405  mov     r15d, eax
0x180024408  mov     rcx, rsi; hObject
0x18002440b  call    cs:__imp_CloseHandle
0x180024411  cmp     dword ptr [rbp+100h+Result], r13d
0x180024418  jz      short loc_180024423
0x18002441a  test    r15d, r15d
0x18002441d  jnz     loc_1800244B2
0x180024423  cmp     [rdi+40h], r13d
0x180024427  jnz     short loc_18002444B
0x180024429  test    r12d, r12d
0x18002442c  jz      short loc_18002443E
0x18002442e  mov     r8d, 1; int
0x180024434  mov     rdx, rdi; struct Accommodation *
0x180024437  call    ?CreateBreakawayATProcess@StartList@@AEAAJPEAVAccommodation@@H@Z; StartList::CreateBreakawayATProcess(Accommodation *,int)
0x18002443c  jmp     short loc_1800244AB
0x18002443e  mov     r8, rdi; struct Accommodation *
0x180024441  mov     rdx, rbx; unsigned __int16 *
0x180024444  call    ?CreateATProcess@StartList@@AEAAJPEBGPEAVAccommodation@@H@Z; StartList::CreateATProcess(ushort const *,Accommodation *,int)
0x180024449  jmp     short loc_1800244AB
0x18002444b  mov     [rsp+200h+var_1C0], r13
0x180024450  mov     [rsp+200h+var_1B8], r13
0x180024455  mov     [rsp+200h+var_1B0], r13
0x18002445a  mov     [rsp+200h+var_1C8], r13; unsigned int *
0x18002445f  mov     [rsp+200h+var_1D8], 2001Fh; REGSAM
0x180024467  mov     [rsp+200h+var_1E0], 1; DWORD
0x18002446f  lea     r8, aSoftwareMicros_2; "Software\\Microsoft\\Windows NT\\Curren"...
0x180024476  mov     rdx, 0FFFFFFFF80000001h; hKey
0x18002447d  lea     rcx, [rsp+200h+var_1C0]; this
0x180024482  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x180024487  test    eax, eax
0x180024489  jnz     short loc_18002449C
0x18002448b  lea     r8d, [rax+3]; unsigned int
0x18002448f  mov     rdx, [rdi]; unsigned __int16 *
0x180024492  lea     rcx, [rsp+200h+var_1C0]; this
0x180024497  call    ?SetDWORDValue@CRegKey@ATL@@QEAAJPEBGK@Z; ATL::CRegKey::SetDWORDValue(ushort const *,ulong)
0x18002449c  lea     rcx, [rsp+200h+var_1C0]; this
0x1800244a1  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800244a6  call    ?SendWinkeyPlusU@@YAXXZ; SendWinkeyPlusU(void)
0x1800244ab  xor     eax, eax
0x1800244ad  jmp     loc_1800245AC
0x1800244b2  cmp     [rdi+40h], r13d
0x1800244b6  jnz     short loc_1800244CE
0x1800244b8  call    ?IsInteractiveUser@CATUtils@@SAHXZ; CATUtils::IsInteractiveUser(void)
0x1800244bd  test    eax, eax
0x1800244bf  jz      short loc_1800244CE
0x1800244c1  xor     r8d, r8d; int
0x1800244c4  mov     rdx, rdi; struct Accommodation *
0x1800244c7  call    ?CreateBreakawayATProcess@StartList@@AEAAJPEAVAccommodation@@H@Z; StartList::CreateBreakawayATProcess(Accommodation *,int)
0x1800244cc  jmp     short loc_1800244D9
0x1800244ce  mov     r8, rdi; struct Accommodation *
0x1800244d1  mov     rdx, rbx; unsigned __int16 *
0x1800244d4  call    ?CreateATProcess@StartList@@AEAAJPEBGPEAVAccommodation@@H@Z; StartList::CreateATProcess(ushort const *,Accommodation *,int)
0x1800244d9  mov     esi, eax
0x1800244db  test    eax, eax
0x1800244dd  js      loc_1800245AA
0x1800244e3  jmp     short loc_1800244F6
0x1800244e5  mov     rdx, rdi; struct Accommodation *
0x1800244e8  call    ?IsColorFiltering@StartList@@AEAA_NPEAVAccommodation@@@Z; StartList::IsColorFiltering(Accommodation *)
0x1800244ed  test    al, al
0x1800244ef  jz      short loc_1800244F6
0x1800244f1  call    ?UpdateActiveFilter@ColorFilterHelper@ColorFiltering@@SAXXZ; ColorFiltering::ColorFilterHelper::UpdateActiveFilter(void)
0x1800244f6  mov     rdx, rdi; struct Accommodation *
0x1800244f9  call    ?LogAccomodationToSQM@StartList@@AEAAXPEAVAccommodation@@@Z; StartList::LogAccomodationToSQM(Accommodation *)
0x1800244fe  call    ?IsInteractiveUser@CATUtils@@SAHXZ; CATUtils::IsInteractiveUser(void)
0x180024503  test    eax, eax
0x180024505  jz      loc_1800245AA
0x18002450b  mov     rcx, [rdi]
0x18002450e  sub     rcx, 18h
0x180024512  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x180024517  mov     r11, rax
0x18002451a  lea     rdx, [rax+18h]
0x18002451e  lea     rcx, [r14+30h]
0x180024522  call    ?Find@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEBAPEAU__POSITION@@PEBGPEAU3@@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::Find(ushort const *,__POSITION *)
0x180024527  mov     rbx, rax
0x18002452a  mov     rcx, r11; this
0x18002452d  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180024532  test    rbx, rbx
0x180024535  jnz     short loc_180024563
0x180024537  mov     rcx, [rdi]
0x18002453a  sub     rcx, 18h
0x18002453e  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x180024543  mov     rbx, rax
0x180024546  lea     rdx, [rax+18h]
0x18002454a  mov     [rbp+100h+Result], rdx
0x180024551  lea     rcx, [r14+30h]
0x180024555  call    ?AddTail@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAPEAU__POSITION@@PEBG@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::AddTail(ushort const *)
0x18002455a  nop
0x18002455b  mov     rcx, rbx; this
0x18002455e  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180024563  mov     rcx, r14; this
0x180024566  call    ?SaveSessionKey@StartList@@AEAAXXZ; StartList::SaveSessionKey(void)
0x18002456b  cmp     [rdi+44h], r13d
0x18002456f  jnz     short loc_180024577
0x180024571  cmp     [rdi+40h], r13d
0x180024575  jnz     short loc_1800245AA
0x180024577  mov     edx, 1; int
0x18002457c  lea     rcx, [rsp+200h+var_1A0]; this
0x180024581  call    ??0ATManager@@QEAA@H@Z; ATManager::ATManager(int)
0x180024586  nop
0x180024587  lea     rax, [rsp+200h+var_1A0]
0x18002458c  mov     [rbp+100h+Result], rax
0x180024593  lea     rcx, [rbp+100h+Result]; this
0x18002459a  call    ?InteractiveDesktopCopy@SettingsCopier@@QEAAJXZ; SettingsCopier::InteractiveDesktopCopy(void)
0x18002459f  nop
0x1800245a0  lea     rcx, [rsp+200h+var_1A0]; this
0x1800245a5  call    ??1ATManager@@QEAA@XZ; ATManager::~ATManager(void)
0x1800245aa  mov     eax, esi
0x1800245ac  add     rsp, 1C8h
0x1800245b3  pop     r15
0x1800245b5  pop     r14
0x1800245b7  pop     r13
0x1800245b9  pop     r12
0x1800245bb  pop     rdi
0x1800245bc  pop     rsi
0x1800245bd  pop     rbx
0x1800245be  pop     rbp
0x1800245bf  retn
```
