# RestorePlaceholder::GetRestorePlaceholderParameters(RestorePlaceholder::PlaceholderParameters *,char const *)

- ea: `0x18018260c`
- end: `0x1801828e0`
- name: `?GetRestorePlaceholderParameters@RestorePlaceholder@@YAJPEAUPlaceholderParameters@1@PEBD@Z`
- size: `724`
- prototype: `__int64 __fastcall(RestorePlaceholder *__hidden this, struct RestorePlaceholder::PlaceholderParameters *, const char *)`
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, installer_update`

## callers

- `0x1800b8010`

## callees

- `0x180010b74`
- `0x18001af10`
- `0x18018260c`
- `0x180182df0`
- `0x180185688`
- `0x1801856d4`
- `0x180185814`
- `0x180186fa8`
- `0x18018708c`
- `0x1801876b8`
- `0x1801877e8`
- `0x180187c2c`
- `0x180187f44`
- `0x1801880b0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180182679`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18018268c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801826d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801826e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180182713`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180182723`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18018275a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18018276d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801827a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801827d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801827e5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180182819`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18018284a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18018285a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180182891`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801828a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180182679`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18018268c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801826d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801826e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180182713`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180182723`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18018275a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18018276d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801827a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801827d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801827e5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180182819`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18018284a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18018285a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180182891`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801828a4`

## string_xrefs

- `0x18018262e`: `onecoreuap\enduser\winstore\installservice\libqueue2\restore.cpp`

## pseudocode

```c
__int64 __fastcall RestorePlaceholder::GetRestorePlaceholderParameters(
        HSTRING *this,
        struct RestorePlaceholder::PlaceholderParameters *a2,
        const char *a3)
{
  bool *v5; // rdx
  int IsDefaultWebAccountAad; // eax
  int MSATicketAndAccount; // ebx
  __int64 v8; // rdx
  int LanguageAndMarket; // eax
  int OemIdAndScmId; // eax
  int IsSMode; // eax
  int FamilyAndFamilyVersion; // eax
  int AppModels; // eax
  int HardwareCapabilitiesAndArchitecture; // eax
  int L3CacheSizeAndProcessor; // eax
  int v17; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  char v19; // [rsp+70h] [rbp+18h] BYREF

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_59268366>::__private_IsEnabled(
                          `wil::Feature<__WilFeatureTraits_Feature_59268366>::GetImpl'::`2'::impl,
                          a2,
                          a3) )
  {
    v19 = 0;
    IsDefaultWebAccountAad = AccountTypeHelper::IsDefaultWebAccountAad((AccountTypeHelper *)&v19, v5);
    if ( IsDefaultWebAccountAad >= 0 )
    {
      if ( v19 )
        goto LABEL_11;
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x2C5,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\restore.cpp",
        (const char *)(unsigned int)IsDefaultWebAccountAad,
        v17);
    }
    WindowsDeleteString(this[15]);
    this[15] = 0;
    WindowsDeleteString(this[17]);
    this[17] = 0;
    MSATicketAndAccount = _GetMSATicketAndAccount(this + 17, this + 15, (const char *)a2);
    if ( MSATicketAndAccount < 0 )
    {
      v8 = 712;
LABEL_7:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\restore.cpp",
        (const char *)(unsigned int)MSATicketAndAccount,
        v17);
      return (unsigned int)MSATicketAndAccount;
    }
  }
  else if ( !_IsAADAccount() )
  {
    WindowsDeleteString(this[15]);
    this[15] = 0;
    WindowsDeleteString(this[17]);
    this[17] = 0;
    MSATicketAndAccount = _GetMSATicketAndAccount(this + 17, this + 15, (const char *)a2);
    if ( MSATicketAndAccount < 0 )
    {
      v8 = 722;
      goto LABEL_7;
    }
  }
LABEL_11:
  WindowsDeleteString(this[13]);
  this[13] = 0;
  WindowsDeleteString(this[11]);
  this[11] = 0;
  LanguageAndMarket = _GetLanguageAndMarket(this + 11, this + 13);
  if ( LanguageAndMarket < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x2D5,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\restore.cpp",
      (const char *)(unsigned int)LanguageAndMarket,
      v17);
  WindowsDeleteString(this[23]);
  this[23] = 0;
  WindowsDeleteString(this[19]);
  this[19] = 0;
  OemIdAndScmId = _GetOemIdAndScmId(this + 19, this + 23);
  if ( OemIdAndScmId < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x2D6,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\restore.cpp",
      (const char *)(unsigned int)OemIdAndScmId,
      v17);
  WindowsDeleteString(this[27]);
  this[27] = 0;
  IsSMode = _GetIsSMode(this + 27);
  if ( IsSMode < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x2D7,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\restore.cpp",
      (const char *)(unsigned int)IsSMode,
      v17);
  WindowsDeleteString(this[7]);
  this[7] = 0;
  WindowsDeleteString(this[5]);
  this[5] = 0;
  FamilyAndFamilyVersion = _GetFamilyAndFamilyVersion(this + 5, this + 7);
  if ( FamilyAndFamilyVersion < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x2D8,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\restore.cpp",
      (const char *)(unsigned int)FamilyAndFamilyVersion,
      v17);
  WindowsDeleteString(this[1]);
  this[1] = 0;
  AppModels = _GetAppModels(this + 1);
  if ( AppModels < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x2D9,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\restore.cpp",
      (const char *)(unsigned int)AppModels,
      v17);
  WindowsDeleteString(this[3]);
  this[3] = 0;
  WindowsDeleteString(this[9]);
  this[9] = 0;
  HardwareCapabilitiesAndArchitecture = _GetHardwareCapabilitiesAndArchitecture(this + 9, this + 3);
  if ( HardwareCapabilitiesAndArchitecture < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x2DA,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\restore.cpp",
      (const char *)(unsigned int)HardwareCapabilitiesAndArchitecture,
      v17);
  WindowsDeleteString(this[21]);
  this[21] = 0;
  WindowsDeleteString(this[25]);
  this[25] = 0;
  L3CacheSizeAndProcessor = _GetL3CacheSizeAndProcessor(this + 25, this + 21);
  if ( L3CacheSizeAndProcessor < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x2DB,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\restore.cpp",
      (const char *)(unsigned int)L3CacheSizeAndProcessor,
      v17);
  return 0;
}

```

## disassembly

```asm
0x18018260c  push    rbx
0x18018260e  push    rbp
0x18018260f  push    rsi
0x180182610  push    rdi
0x180182611  push    r14
0x180182613  push    r15
0x180182615  sub     rsp, 28h
0x180182619  mov     rbp, rdx
0x18018261c  mov     rsi, rcx
0x18018261f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_59268366@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_59268366@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59268366> `wil::Feature<__WilFeatureTraits_Feature_59268366>::GetImpl(void)'::`2'::impl
0x180182626  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_59268366@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59268366>::__private_IsEnabled(void)
0x18018262b  xor     r14d, r14d
0x18018262e  lea     r15, aOnecoreuapEndu_24; "onecoreuap\\enduser\\winstore\\installs"...
0x180182635  test    al, al
0x180182637  jz      loc_1801826C5
0x18018263d  lea     rcx, [rsp+58h+arg_10]; this
0x180182642  mov     [rsp+58h+arg_10], r14b
0x180182647  call    ?IsDefaultWebAccountAad@AccountTypeHelper@@YAJPEA_N@Z; AccountTypeHelper::IsDefaultWebAccountAad(bool *)
0x18018264c  test    eax, eax
0x18018264e  jns     short loc_180182667
0x180182650  mov     rcx, [rsp+58h]; this
0x180182655  mov     r9d, eax; char *
0x180182658  mov     r8, r15; unsigned int
0x18018265b  mov     edx, 2C5h; void *
0x180182660  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180182665  jmp     short loc_180182672
0x180182667  cmp     [rsp+58h+arg_10], r14b
0x18018266c  jnz     loc_18018270C
0x180182672  lea     rdi, [rsi+78h]
0x180182676  mov     rcx, [rdi]; string
0x180182679  call    cs:__imp_WindowsDeleteString
0x18018267f  mov     [rdi], r14
0x180182682  lea     rbx, [rsi+88h]
0x180182689  mov     rcx, [rbx]; string
0x18018268c  call    cs:__imp_WindowsDeleteString
0x180182692  mov     r8, rbp; char *
0x180182695  mov     [rbx], r14
0x180182698  mov     rdx, rdi; HSTRING *
0x18018269b  mov     rcx, rbx; string
0x18018269e  call    ?_GetMSATicketAndAccount@@YAJPEAPEAUHSTRING__@@0PEBD@Z; _GetMSATicketAndAccount(HSTRING__ * *,HSTRING__ * *,char const *)
0x1801826a3  mov     ebx, eax
0x1801826a5  test    eax, eax
0x1801826a7  jns     short loc_18018270C
0x1801826a9  mov     edx, 2C8h; void *
0x1801826ae  mov     rcx, [rsp+58h]; this
0x1801826b3  mov     r8, r15; unsigned int
0x1801826b6  mov     r9d, ebx; char *
0x1801826b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801826be  mov     eax, ebx
0x1801826c0  jmp     loc_1801828D3
0x1801826c5  call    ?_IsAADAccount@@YA_NXZ; _IsAADAccount(void)
0x1801826ca  test    al, al
0x1801826cc  jnz     short loc_18018270C
0x1801826ce  lea     rdi, [rsi+78h]
0x1801826d2  mov     rcx, [rdi]; string
0x1801826d5  call    cs:__imp_WindowsDeleteString
0x1801826db  mov     [rdi], r14
0x1801826de  lea     rbx, [rsi+88h]
0x1801826e5  mov     rcx, [rbx]; string
0x1801826e8  call    cs:__imp_WindowsDeleteString
0x1801826ee  mov     r8, rbp; char *
0x1801826f1  mov     [rbx], r14
0x1801826f4  mov     rdx, rdi; HSTRING *
0x1801826f7  mov     rcx, rbx; string
0x1801826fa  call    ?_GetMSATicketAndAccount@@YAJPEAPEAUHSTRING__@@0PEBD@Z; _GetMSATicketAndAccount(HSTRING__ * *,HSTRING__ * *,char const *)
0x1801826ff  mov     ebx, eax
0x180182701  test    eax, eax
0x180182703  jns     short loc_18018270C
0x180182705  mov     edx, 2D2h
0x18018270a  jmp     short loc_1801826AE
0x18018270c  lea     rdi, [rsi+68h]
0x180182710  mov     rcx, [rdi]; string
0x180182713  call    cs:__imp_WindowsDeleteString
0x180182719  mov     [rdi], r14
0x18018271c  lea     rbx, [rsi+58h]
0x180182720  mov     rcx, [rbx]; string
0x180182723  call    cs:__imp_WindowsDeleteString
0x180182729  mov     rdx, rdi; HSTRING *
0x18018272c  mov     [rbx], r14
0x18018272f  mov     rcx, rbx; string
0x180182732  call    ?_GetLanguageAndMarket@@YAJPEAPEAUHSTRING__@@0@Z; _GetLanguageAndMarket(HSTRING__ * *,HSTRING__ * *)
0x180182737  test    eax, eax
0x180182739  jns     short loc_180182750
0x18018273b  mov     rcx, [rsp+58h]; this
0x180182740  mov     r9d, eax; char *
0x180182743  mov     r8, r15; unsigned int
0x180182746  mov     edx, 2D5h; void *
0x18018274b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180182750  lea     rdi, [rsi+0B8h]
0x180182757  mov     rcx, [rdi]; string
0x18018275a  call    cs:__imp_WindowsDeleteString
0x180182760  mov     [rdi], r14
0x180182763  lea     rbx, [rsi+98h]
0x18018276a  mov     rcx, [rbx]; string
0x18018276d  call    cs:__imp_WindowsDeleteString
0x180182773  mov     rdx, rdi; HSTRING *
0x180182776  mov     [rbx], r14
0x180182779  mov     rcx, rbx; string
0x18018277c  call    ?_GetOemIdAndScmId@@YAJPEAPEAUHSTRING__@@0@Z; _GetOemIdAndScmId(HSTRING__ * *,HSTRING__ * *)
0x180182781  test    eax, eax
0x180182783  jns     short loc_18018279A
0x180182785  mov     rcx, [rsp+58h]; this
0x18018278a  mov     r9d, eax; char *
0x18018278d  mov     r8, r15; unsigned int
0x180182790  mov     edx, 2D6h; void *
0x180182795  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18018279a  lea     rbx, [rsi+0D8h]
0x1801827a1  mov     rcx, [rbx]; string
0x1801827a4  call    cs:__imp_WindowsDeleteString
0x1801827aa  mov     rcx, rbx; string
0x1801827ad  mov     [rbx], r14
0x1801827b0  call    ?_GetIsSMode@@YAJPEAPEAUHSTRING__@@@Z; _GetIsSMode(HSTRING__ * *)
0x1801827b5  test    eax, eax
0x1801827b7  jns     short loc_1801827CE
0x1801827b9  mov     rcx, [rsp+58h]; this
0x1801827be  mov     r9d, eax; char *
0x1801827c1  mov     r8, r15; unsigned int
0x1801827c4  mov     edx, 2D7h; void *
0x1801827c9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1801827ce  lea     rdi, [rsi+38h]
0x1801827d2  mov     rcx, [rdi]; string
0x1801827d5  call    cs:__imp_WindowsDeleteString
0x1801827db  mov     [rdi], r14
0x1801827de  lea     rbx, [rsi+28h]
0x1801827e2  mov     rcx, [rbx]; string
0x1801827e5  call    cs:__imp_WindowsDeleteString
0x1801827eb  mov     rdx, rdi; HSTRING *
0x1801827ee  mov     [rbx], r14
0x1801827f1  mov     rcx, rbx; string
0x1801827f4  call    ?_GetFamilyAndFamilyVersion@@YAJPEAPEAUHSTRING__@@0@Z; _GetFamilyAndFamilyVersion(HSTRING__ * *,HSTRING__ * *)
0x1801827f9  test    eax, eax
0x1801827fb  jns     short loc_180182812
0x1801827fd  mov     rcx, [rsp+58h]; this
0x180182802  mov     r9d, eax; char *
0x180182805  mov     r8, r15; unsigned int
0x180182808  mov     edx, 2D8h; void *
0x18018280d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180182812  lea     rbx, [rsi+8]
0x180182816  mov     rcx, [rbx]; string
0x180182819  call    cs:__imp_WindowsDeleteString
0x18018281f  mov     rcx, rbx; string
0x180182822  mov     [rbx], r14
0x180182825  call    ?_GetAppModels@@YAJPEAPEAUHSTRING__@@@Z; _GetAppModels(HSTRING__ * *)
0x18018282a  test    eax, eax
0x18018282c  jns     short loc_180182843
0x18018282e  mov     rcx, [rsp+58h]; this
0x180182833  mov     r9d, eax; char *
0x180182836  mov     r8, r15; unsigned int
0x180182839  mov     edx, 2D9h; void *
0x18018283e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180182843  lea     rdi, [rsi+18h]
0x180182847  mov     rcx, [rdi]; string
0x18018284a  call    cs:__imp_WindowsDeleteString
0x180182850  mov     [rdi], r14
0x180182853  lea     rbx, [rsi+48h]
0x180182857  mov     rcx, [rbx]; string
0x18018285a  call    cs:__imp_WindowsDeleteString
0x180182860  mov     rdx, rdi; HSTRING *
0x180182863  mov     [rbx], r14
0x180182866  mov     rcx, rbx; HSTRING *
0x180182869  call    ?_GetHardwareCapabilitiesAndArchitecture@@YAJPEAPEAUHSTRING__@@0@Z; _GetHardwareCapabilitiesAndArchitecture(HSTRING__ * *,HSTRING__ * *)
0x18018286e  test    eax, eax
0x180182870  jns     short loc_180182887
0x180182872  mov     rcx, [rsp+58h]; this
0x180182877  mov     r9d, eax; char *
0x18018287a  mov     r8, r15; unsigned int
0x18018287d  mov     edx, 2DAh; void *
0x180182882  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180182887  lea     rdi, [rsi+0A8h]
0x18018288e  mov     rcx, [rdi]; string
0x180182891  call    cs:__imp_WindowsDeleteString
0x180182897  mov     [rdi], r14
0x18018289a  lea     rbx, [rsi+0C8h]
0x1801828a1  mov     rcx, [rbx]; string
0x1801828a4  call    cs:__imp_WindowsDeleteString
0x1801828aa  mov     rdx, rdi; HSTRING *
0x1801828ad  mov     [rbx], r14
0x1801828b0  mov     rcx, rbx; string
0x1801828b3  call    ?_GetL3CacheSizeAndProcessor@@YAJPEAPEAUHSTRING__@@0@Z; _GetL3CacheSizeAndProcessor(HSTRING__ * *,HSTRING__ * *)
0x1801828b8  test    eax, eax
0x1801828ba  jns     short loc_1801828D1
0x1801828bc  mov     rcx, [rsp+58h]; this
0x1801828c1  mov     r9d, eax; char *
0x1801828c4  mov     r8, r15; unsigned int
0x1801828c7  mov     edx, 2DBh; void *
0x1801828cc  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1801828d1  xor     eax, eax
0x1801828d3  add     rsp, 28h
0x1801828d7  pop     r15
0x1801828d9  pop     r14
0x1801828db  pop     rdi
0x1801828dc  pop     rsi
0x1801828dd  pop     rbp
0x1801828de  pop     rbx
0x1801828df  retn
```
